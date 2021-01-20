# ShippyPro-API
Integrate ShippyPro with Odoo version 14


```json
{
"OrderID":"",
"Message":"What happened",
}

[
{

"identifier": 
}

https://www.youtube.com/watch?v=4T5Gnrmzjak

]





//-------------------------------------------------------------------------------------------------
// http requests
const axios = require('axios');

// import api key
// const {dottApiKey} = require('../config');

// init
const baseUrl = 'https://roast-staging.dott.pt/api/order/merchant';

// request shape
const config = (apiKey) => ({
    method: 'GET',
    url: baseUrl,
    headers: {
        'accept': 'application/json',
        'Authorization': apiKey
    }
});

module.exports = async(apiKey) => {
    console.log('dott call');
    const res = await axios(config(apiKey));
    console.log(res.data.data);
    return res.data.data;
};

/*
sample of an order
{
   "id":"1099536",
   "orderNr":"210105B110790167",
   "orderItems":[
      {
         "id":"1203946",
         "offerId":6765737,
         "gtin":"886543433150",
         "name":"Timberland Stormbuck Plain Toe Oxford Shoes",
         "sku":"Vinuus1",
         "quantity":2,
         "amount":24.6,
         "amountTaxTaxExcl":20,
         "marketplaceDiscount":0,
         "imageUrl":"https://d1uyhd0hkrx9pt.cloudfront.net/assets/images/1856/main/none_c51e9d0c491c4fc4074614caaffea7f5_c51e9d0.JPEG",
         "status":"AuthorizedPayment",
         "statusDesc":"Pagamento autorizado",
         "attributes":{
            "requireSerialNumber":true
         }
      }
   ],
   "status":"AuthorizedPayment",
   "incidentStatus":"no_incident",
   "shippingAddress":{
      "address":"Morada teste",
      "address2":"",
      "city":"Chaves",
      "countryCode":"PT",
      "country":"Portugal",
      "firstName":"António",
      "fiscalNumber":"",
      "lastName":"Ferreira",
      "name":"Dott",
      "status":"10",
      "zipcode":"5400-837"
   },
   "billingAddress":{
      "address":"Morada teste",
      "address2":"",
      "city":"Chaves",
      "countryCode":"PT",
      "country":"Portugal",
      "firstName":"António",
      "fiscalNumber":"",
      "lastName":"Ferreira",
      "name":"Dott",
      "status":"10",
      "zipcode":"5400-837"
   },
   "createdOn":"2021-01-05T17:29:54.67168Z",
   "modifiedOn":"2021-01-05T17:29:59.503901Z",
   "customer":{
      "id":49697,
      "username":"antonio_ferreira666",
      "firstName":"António",
      "lastName":"Ferreira"
   },
   "merchantId":"1025440",
   "merchantOrderPayment":{
      "itemsTotal":49.2,
      "itemsTotalTaxExcl":40,
      "billed":49.2,
      "billedTaxExcl":40,
      "shipping":0,
      "shippingTaxExcl":0,
      "marketplaceDiscount":0,
      "marketplaceDiscountTaxExcl":0,
      "paymentMethod":"card"
   }
}
*/
