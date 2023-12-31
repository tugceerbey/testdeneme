python
import unittest
import requests

class TestFlightData(unittest.TestCase):
    def setUp(self):

        self.sample_data = {
            "data": [
    {
      "id": 1,
      "from": "IST",
      "to": "LAX",
      "date": "2022-12-13"
    },
            
    {
      "id": 2,
      "from": "JFK",
      "to": "LHR",
      "date": "2022-12-14"
    },
    {
      "id": 3,
      "from": "CDG",
      "to": "HND",
      "date": "2022-12-15"
    },
    {
      "id": 4,
      "from": "SYD",
      "to": "LAX",
      "date": "2022-12-16"
    },
    {
      "id": 5,
      "from": "ORD",
      "to": "PEK",
      "date": "2022-12-17"
    },
    {
      "id": 6,
      "from": "DXB",
      "to": "SIN",
      "date": "2022-12-18"
    },
    {
      "id": 7,
      "from": "HKG",
      "to": "FRA",
      "date": "2022-12-19"
    },
    {
      "id": 8,
      "from": "MAD",
      "to": "FCO",
      "date": "2022-12-20"
    },
    {
      "id": 9,
      "from": "IST",
      "to": "SIN",
      "date": "2022-12-21"
    },
    {
      "id": 10,
      "from": "JFK",
      "to": "CDG",
      "date": "2022-12-22"
    },
    {
      "id": 11,
      "from": "LAX",
      "to": "SYD",
      "date": "2022-12-23"
    },
    {
      "id": 12,
      "from": "ORD",
      "to": "HKG",
      "date": "2022-12-24"
    },
    {
      "id": 13,
      "from": "IST",
      "to": "MAD",
      "date": "2022-12-25"
    },
    {
      "id": 14,
      "from": "LAX",
      "to": "LHR",
      "date": "2022-12-26"
    },
    {
      "id": 15,
      "from": "PEK",
      "to": "DXB",
      "date": "2022-12-27"
    },
    {
      "id": 16,
      "from": "SIN",
      "to": "FRA",
      "date": "2022-12-28"
    },
    {
      "id": 17,
      "from": "CDG",
      "to": "IST",
      "date": "2022-12-29"
    },
    {
      "id": 18,
      "from": "HND",
      "to": "JFK",
      "date": "2022-12-30"
    },
    {
      "id": 19,
      "from": "LHR",
      "to": "LAX",
      "date": "2022-12-31"
    },
    {
      "id": 20,
      "from": "SYD",
      "to": "ORD",
      "date": "2023-01-01"
    },
    {
      "id": 21,
      "from": "IST",
      "to": "PEK",
      "date": "2023-01-02"
    },
    {
      "id": 22,
      "from": "LAX",
      "to": "DXB",
      "date": "2023-01-03"
    },
    {
      "id": 23,
      "from": "HKG",
      "to": "SIN",
      "date": "2023-01-04"
    },
    {
      "id": 24,
      "from": "FRA",
      "to": "MAD",
      "date": "2023-01-05"
    },
    {
      "id": 25,
      "from": "IST",
      "to": "FCO",
      "date": "2023-01-06"
    },
    {
      "id": 26,
      "from": "JFK",
      "to": "SYD",
      "date": "2023-01-07"
    },
    {
      "id": 27,
      "from": "LAX",
      "to": "ORD",
      "date": "2023-01-08"
    },
    {
      "id": 28,
      "from": "CDG",
      "to": "DXB",
      "date": "2023-01-09"
    },
    {
      "id": 29,
      "from": "HND",
      "to": "MAD",
      "date": "2023-01-10"
    },
    {
      "id": 30,
      "from": "LHR",
      "to": "FCO",
      "date": "2023-01-11"
    },
    {
      "id": 10,
      "from": "IST",
      "to": "LAX",
      "date": "2023-12-13"
    },
    {
      "id": 20,
      "from": "JFK",
      "to": "LHR",
      "date": "2023-12-14"
    },
    {
      "id": 30,
      "from": "CDG",
      "to": "HND",
      "date": "2023-12-15"
    },
    {
      "id": 40,
      "from": "SYD",
      "to": "LAX",
      "date": "2023-12-16"
    },
    {
      "id": 50,
      "from": "ORD",
      "to": "PEK",
      "date": "2023-12-17"
    },
    {
      "id": 60,
      "from": "DXB",
      "to": "SIN",
      "date": "2023-12-18"
    },
    {
      "id": 70,
      "from": "HKG",
      "to": "FRA",
      "date": "2023-12-19"
    },
    {
      "id": 80,
      "from": "MAD",
      "to": "FCO",
      "date": "2023-12-20"
    },
    {
      "id": 90,
      "from": "IST",
      "to": "SIN",
      "date": "2023-12-21"
    },
    {
      "id": 100,
      "from": "JFK",
      "to": "CDG",
      "date": "2023-12-22"
    },
    {
      "id": 110,
      "from": "LAX",
      "to": "SYD",
      "date": "2023-12-23"
    },
    {
      "id": 120,
      "from": "ORD",
      "to": "HKG",
      "date": "2023-12-24"
    },
    {
      "id": 130,
      "from": "IST",
      "to": "MAD",
      "date": "2023-12-25"
    },
    {
      "id": 140,
      "from": "LAX",
      "to": "LHR",
      "date": "2023-12-26"
    },
    {
      "id": 150,
      "from": "PEK",
      "to": "DXB",
      "date": "2023-12-27"
    },
    {
      "id": 160,
      "from": "SIN",
      "to": "FRA",
      "date": "2023-12-28"
    },
    {
      "id": 170,
      "from": "CDG",
      "to": "IST",
      "date": "2023-12-29"
    },
    {
      "id": 180,
      "from": "HND",
      "to": "JFK",
      "date": "2023-12-30"
    },
    {
      "id": 190,
      "from": "LHR",
      "to": "LAX",
      "date": "2023-12-31"
    },
    {
      "id": 200,
      "from": "SYD",
      "to": "ORD",
      "date": "2024-01-01"
    },
    {
      "id": 210,
      "from": "IST",
      "to": "PEK",
      "date": "2024-01-02"
    },
    {
      "id": 220,
      "from": "LAX",
      "to": "DXB",
      "date": "2024-01-03"
    },
    {
      "id": 230,
      "from": "HKG",
      "to": "SIN",
      "date": "2024-01-04"
    },
    {
      "id": 240,
      "from": "FRA",
      "to": "MAD",
      "date": "2024-01-05"
    },
    {
      "id": 250,
      "from": "IST",
      "to": "FCO",
      "date": "2024-01-06"
    },
    {
      "id": 260,
      "from": "JFK",
      "to": "SYD",
      "date": "2024-01-07"
    },
    {
      "id": 270,
      "from": "LAX",
      "to": "ORD",
      "date": "2024-01-08"
    },
    {
      "id": 280,
      "from": "CDG",
      "to": "DXB",
      "date": "2024-01-09"
    },
    {
      "id": 290,
      "from": "HND",
      "to": "MAD",
      "date": "2024-01-10"
    },
    {
      "id": 300,
      "from": "LHR",
      "to": "FCO",
      "date": "2024-01-11"
    }
             
  ]
          
        }
    def test_get_request_status_code(self):
        #API URL
        api_url = "https://flights-api.buraky.workers.dev/"

        # GET isteği gönder
        response = requests.get(api_url)

        #HTTP Durum kontrol et (200 başarılı yanıt)
        self.assertEqual(response.status_code, 200, f"HTTP Status Code: {response.status_code}")

    def test_get_request_response_data_type(self):
        # API URL
        api_url = "https://flights-api.buraky.workers.dev/"

        #GET isteği gönder
        response = requests.get(api_url)

        #Yanıt değerini kontrol et (string veya integer )
        self.assertTrue(isinstance(response.text, (str, int)), f"Response Data Type: {type(response.text)}")

        #Yanıt değerini JSON formatinda kontol et 
        self.assertTrue(isinstance(response.json(), list), "Response Data Type is List")
        def test_content_type_application_json(self):
        # API URL
        api_url = "https://flights-api.buraky.workers.dev/"
        # GET isteği gönder
        response = requests.get(api_url)

        # Content-type başlık kontrol et
       
       content_type_header = 
response.headers.get("Content-Type", "")
        self.assertTrue("application/json" in content_type_header, f"Content-Type is 
        {content_type_header}, expected application/json")

  if __name__ == "__main__":
    unittest.main()





