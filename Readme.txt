
1.Create Collection:

client = boto3.client('rekognition',
region_name='us-east-1'
)
response = client.create_collection(
    CollectionId='photo-Rekognition'			#Collection_Name
)
print(response)

2.Add People into the collection:

client = boto3.client('rekognition',
region_name='us-east-1'
)
response = client.index_faces(
    CollectionId='photo-Rekognition',
    Image={
        'S3Object': {
            'Bucket': 'rekognitionfacestrial',		#Bucket_Name
            'Name': 'IMG_20190915_174052.jpg'		#Image_Bukcet_Key
        }
    },
    ExternalImageId='sooraj'				#Image_Name
)
print(response)

3.Search a new face using WebCam from the collection, converts the output text to mp3 and plays.(Code attached separately)