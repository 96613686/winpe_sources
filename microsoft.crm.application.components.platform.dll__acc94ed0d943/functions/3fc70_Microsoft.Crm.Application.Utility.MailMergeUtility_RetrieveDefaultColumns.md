# Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveDefaultColumns

- ea: `0x3fc70`
- end: `0x403e2`
- name: `Microsoft.Crm.Application.Utility.MailMergeUtility::RetrieveDefaultColumns`
- size: `1906`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3dcf0`
- `0x3de90`
- `0x3e590`
- `0x3e870`
- `0x3ed40`

## callees

- `0x3fc70`

## string_xrefs

- `0x3ff5f`: `companyname`
- `0x40106`: `discountamount`
- `0x40111`: `totallineitemamount`
- `0x4011c`: `totalamountlessfreight`
- `0x40132`: `freightamount`
- `0x4013d`: `totalamount`
- `0x40229`: `volumediscountamount`
- `0x4024a`: `baseamount`
- `0x40255`: `manualdiscountamount`
- `0x40260`: `extendedamount`

## pseudocode

```c

```

## disassembly

```asm
0x3fc70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3fc75  stloc.0
0x3fc76  ldarg.1
0x3fc77  ldc.i4   0x400
0x3fc7c  bgt.s    loc_3FCB6
0x3fc7e  ldarg.1
0x3fc7f  ldc.i4.1
0x3fc80  sub
0x3fc81  switch   loc_3FD65, loc_3FE25, loc_402C1, loc_3FF3D, loc_40394, loc_40394, loc_40394, loc_3FCD1
0x3fca6  ldarg.1
0x3fca7  ldc.i4   0x400
0x3fcac  beq      loc_402B1
0x3fcb1  br       loc_40394
0x3fcb6  ldarg.1
0x3fcb7  ldc.i4   0x43C
0x3fcbc  beq      loc_40013
0x3fcc1  ldarg.1
0x3fcc2  ldc.i4   0x43D
0x3fcc7  beq      loc_401AF
0x3fccc  br       loc_40394
0x3fcd1  ldloc.0
0x3fcd2  ldstr    aBusinessunitid// "businessunitid"
0x3fcd7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fcdc  ldloc.0
0x3fcdd  ldstr    aAddress1Line1// "address1_line1"
0x3fce2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fce7  ldloc.0
0x3fce8  ldstr    aAddress1Line2// "address1_line2"
0x3fced  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fcf2  ldloc.0
0x3fcf3  ldstr    aAddress1Line3// "address1_line3"
0x3fcf8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fcfd  ldloc.0
0x3fcfe  ldstr    aAddress1City// "address1_city"
0x3fd03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd08  ldloc.0
0x3fd09  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x3fd0e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd13  ldloc.0
0x3fd14  ldstr    aAddress1Postal// "address1_postalcode"
0x3fd19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd1e  ldloc.0
0x3fd1f  ldstr    aAddress1Countr// "address1_country"
0x3fd24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd29  ldloc.0
0x3fd2a  ldstr    aAddress1Teleph// "address1_telephone1"
0x3fd2f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd34  ldloc.0
0x3fd35  ldstr    aFirstname// "firstname"
0x3fd3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd3f  ldloc.0
0x3fd40  ldstr    aLastname// "lastname"
0x3fd45  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd4a  ldloc.0
0x3fd4b  ldstr    aTitle_0// "title"
0x3fd50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd55  ldloc.0
0x3fd56  ldstr    aInternalemaila// "internalemailaddress"
0x3fd5b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd60  br       loc_403E0
0x3fd65  ldloc.0
0x3fd66  ldstr    aName// "name"
0x3fd6b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd70  ldloc.0
0x3fd71  ldstr    aAddress1Line1// "address1_line1"
0x3fd76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd7b  ldloc.0
0x3fd7c  ldstr    aAddress1Line2// "address1_line2"
0x3fd81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd86  ldloc.0
0x3fd87  ldstr    aAddress1Line3// "address1_line3"
0x3fd8c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd91  ldloc.0
0x3fd92  ldstr    aAddress1City// "address1_city"
0x3fd97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fd9c  ldloc.0
0x3fd9d  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x3fda2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fda7  ldloc.0
0x3fda8  ldstr    aAddress1Postal// "address1_postalcode"
0x3fdad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdb2  ldloc.0
0x3fdb3  ldstr    aAddress1Countr// "address1_country"
0x3fdb8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdbd  ldloc.0
0x3fdbe  ldstr    aFax// "fax"
0x3fdc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdc8  ldloc.0
0x3fdc9  ldstr    aTelephone1// "telephone1"
0x3fdce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdd3  ldloc.0
0x3fdd4  ldstr    aEmailaddress1// "emailaddress1"
0x3fdd9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdde  ldloc.0
0x3fddf  ldstr    aWebsiteurl// "websiteurl"
0x3fde4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fde9  ldloc.0
0x3fdea  ldstr    aAccountnumber// "accountnumber"
0x3fdef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdf4  ldloc.0
0x3fdf5  ldstr    aCreditlimit// "creditlimit"
0x3fdfa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fdff  ldloc.0
0x3fe00  ldstr    aTickersymbol// "tickersymbol"
0x3fe05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe0a  ldloc.0
0x3fe0b  ldstr    aPrimarycontact// "primarycontactid"
0x3fe10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe15  ldloc.0
0x3fe16  ldstr    aAccountid// "accountid"
0x3fe1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe20  br       loc_403E0
0x3fe25  ldloc.0
0x3fe26  ldstr    aFirstname// "firstname"
0x3fe2b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe30  ldloc.0
0x3fe31  ldstr    aMiddlename// "middlename"
0x3fe36  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe3b  ldloc.0
0x3fe3c  ldstr    aLastname// "lastname"
0x3fe41  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe46  ldloc.0
0x3fe47  ldstr    aSalutation// "salutation"
0x3fe4c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe51  ldloc.0
0x3fe52  ldstr    aParentcustomer// "parentcustomerid"
0x3fe57  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe5c  ldloc.0
0x3fe5d  ldstr    aDepartment// "department"
0x3fe62  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe67  ldloc.0
0x3fe68  ldstr    aJobtitle// "jobtitle"
0x3fe6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe72  ldloc.0
0x3fe73  ldstr    aAddress1Line1// "address1_line1"
0x3fe78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe7d  ldloc.0
0x3fe7e  ldstr    aAddress1Line2// "address1_line2"
0x3fe83  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe88  ldloc.0
0x3fe89  ldstr    aAddress1Line3// "address1_line3"
0x3fe8e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe93  ldloc.0
0x3fe94  ldstr    aAddress1City// "address1_city"
0x3fe99  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fe9e  ldloc.0
0x3fe9f  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x3fea4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fea9  ldloc.0
0x3feaa  ldstr    aAddress1Postal// "address1_postalcode"
0x3feaf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3feb4  ldloc.0
0x3feb5  ldstr    aAddress1Countr// "address1_country"
0x3feba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3febf  ldloc.0
0x3fec0  ldstr    aFax// "fax"
0x3fec5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3feca  ldloc.0
0x3fecb  ldstr    aTelephone1// "telephone1"
0x3fed0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fed5  ldloc.0
0x3fed6  ldstr    aTelephone2// "telephone2"
0x3fedb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fee0  ldloc.0
0x3fee1  ldstr    aEmailaddress1// "emailaddress1"
0x3fee6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3feeb  ldloc.0
0x3feec  ldstr    aSpousesname// "spousesname"
0x3fef1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fef6  ldloc.0
0x3fef7  ldstr    aAnniversary// "anniversary"
0x3fefc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff01  ldloc.0
0x3ff02  ldstr    aBirthdate// "birthdate"
0x3ff07  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff0c  ldloc.0
0x3ff0d  ldstr    aMobilephone// "mobilephone"
0x3ff12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff17  ldloc.0
0x3ff18  ldstr    aAssistantname// "assistantname"
0x3ff1d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff22  ldloc.0
0x3ff23  ldstr    aFullname// "fullname"
0x3ff28  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff2d  ldloc.0
0x3ff2e  ldstr    aContactid// "contactid"
0x3ff33  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff38  br       loc_403E0
0x3ff3d  ldloc.0
0x3ff3e  ldstr    aFirstname// "firstname"
0x3ff43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff48  ldloc.0
0x3ff49  ldstr    aLastname// "lastname"
0x3ff4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff53  ldloc.0
0x3ff54  ldstr    aSalutation// "salutation"
0x3ff59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff5e  ldloc.0
0x3ff5f  ldstr    aCompanyname// "companyname"
0x3ff64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff69  ldloc.0
0x3ff6a  ldstr    aAddress1Line1// "address1_line1"
0x3ff6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff74  ldloc.0
0x3ff75  ldstr    aAddress1Line2// "address1_line2"
0x3ff7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff7f  ldloc.0
0x3ff80  ldstr    aAddress1Line3// "address1_line3"
0x3ff85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff8a  ldloc.0
0x3ff8b  ldstr    aAddress1City// "address1_city"
0x3ff90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ff95  ldloc.0
0x3ff96  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x3ff9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffa0  ldloc.0
0x3ffa1  ldstr    aAddress1Postal// "address1_postalcode"
0x3ffa6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffab  ldloc.0
0x3ffac  ldstr    aAddress1Countr// "address1_country"
0x3ffb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffb6  ldloc.0
0x3ffb7  ldstr    aFax// "fax"
0x3ffbc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffc1  ldloc.0
0x3ffc2  ldstr    aTelephone1// "telephone1"
0x3ffc7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffcc  ldloc.0
0x3ffcd  ldstr    aEmailaddress1// "emailaddress1"
0x3ffd2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffd7  ldloc.0
0x3ffd8  ldstr    aWebsiteurl// "websiteurl"
0x3ffdd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffe2  ldloc.0
0x3ffe3  ldstr    aMobilephone// "mobilephone"
0x3ffe8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3ffed  ldloc.0
0x3ffee  ldstr    aPager// "pager"
0x3fff3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3fff8  ldloc.0
0x3fff9  ldstr    aFullname// "fullname"
0x3fffe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40003  ldloc.0
0x40004  ldstr    aLeadid// "leadid"
0x40009  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4000e  br       loc_403E0
0x40013  ldloc.0
0x40014  ldstr    aQuotenumber// "quotenumber"
0x40019  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4001e  ldloc.0
0x4001f  ldstr    aName// "name"
0x40024  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40029  ldloc.0
0x4002a  ldstr    aCustomerid// "customerid"
0x4002f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40034  ldloc.0
0x40035  ldstr    aBilltoLine1// "billto_line1"
0x4003a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4003f  ldloc.0
0x40040  ldstr    aBilltoLine2// "billto_line2"
0x40045  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4004a  ldloc.0
0x4004b  ldstr    aBilltoLine3// "billto_line3"
0x40050  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40055  ldloc.0
0x40056  ldstr    aBilltoCity// "billto_city"
0x4005b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40060  ldloc.0
0x40061  ldstr    aBilltoStateorp// "billto_stateorprovince"
0x40066  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4006b  ldloc.0
0x4006c  ldstr    aBilltoCountry// "billto_country"
0x40071  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40076  ldloc.0
0x40077  ldstr    aBilltoPostalco// "billto_postalcode"
0x4007c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40081  ldloc.0
0x40082  ldstr    aBilltoTelephon// "billto_telephone"
0x40087  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4008c  ldloc.0
0x4008d  ldstr    aBilltoFax// "billto_fax"
0x40092  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x40097  ldloc.0
0x40098  ldstr    aShiptoLine1// "shipto_line1"
0x4009d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x400a2  ldloc.0
0x400a3  ldstr    aShiptoLine2// "shipto_line2"
0x400a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x400ad  ldloc.0
0x400ae  ldstr    aShiptoLine3// "shipto_line3"
0x400b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x400b8  ldloc.0
0x400b9  ldstr    aShiptoCity// "shipto_city"
0x400be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x400c3  ldloc.0
0x400c4  ldstr    aShiptoStateorp// "shipto_stateorprovince"
0x400c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x400ce  ldloc.0
0x400cf  ldstr    aShiptoCountry// "shipto_country"
0x400d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
  ... truncated ...
```
