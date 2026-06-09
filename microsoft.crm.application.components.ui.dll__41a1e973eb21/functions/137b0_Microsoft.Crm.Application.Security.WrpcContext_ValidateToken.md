# Microsoft.Crm.Application.Security.WrpcContext::ValidateToken

- ea: `0x137b0`
- end: `0x13bad`
- name: `Microsoft.Crm.Application.Security.WrpcContext::ValidateToken`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x137b0`
- `0x13bb0`
- `0x13cc0`
- `0x13e90`

## string_xrefs

- `0x137c3`: `WRPCTokenState`
- `0x13aa1`: `WRPCTokenState`
- `0x13ac1`: `WRPCTokenState`
- `0x13ae1`: `WRPCTokenState`
- `0x13b38`: `WRPCTokenState`
- `0x13b5e`: `WRPCTokenState`
- `0x13b7b`: `WRPCTokenState`
- `0x13b9c`: `WRPCTokenState`
- `0x137f6`: `CRMWRPCToken`
- `0x13843`: `CRMWRPCToken`
- `0x13893`: `CRMWRPCToken`
- `0x138fb`: `CRMWRPCToken`
- `0x13957`: `CRMWRPCToken`
- `0x139b3`: `CRMWRPCToken`
- `0x13823`: `CRMWRPCTokenTimeStamp`
- `0x13870`: `CRMWRPCTokenTimeStamp`
- `0x138ae`: `CRMWRPCTokenTimeStamp`
- `0x13918`: `CRMWRPCTokenTimeStamp`
- `0x13974`: `CRMWRPCTokenTimeStamp`
- `0x139d0`: `CRMWRPCTokenTimeStamp`
- `0x138d6`: `WRPC token from '{0}': '{1}' with time stamp '{2}'.`
- `0x13932`: `WRPC token from '{0}': '{1}' with time stamp '{2}'.`
- `0x1398e`: `WRPC token from '{0}': '{1}' with time stamp '{2}'.`
- `0x139ea`: `WRPC token source: '{0}': TimeStamp: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x137b0  ldarg.0
0x137b1  ldfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x137b6  brfalse.s loc_137D4
0x137b8  ldarg.0
0x137b9  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x137be  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x137c3  ldstr    aWrpctokenstate// "WRPCTokenState"
0x137c8  ldc.i4.3
0x137c9  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x137ce  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137d3  ret
0x137d4  ldsfld   string [mscorlib]System.String::Empty
0x137d9  stloc.0
0x137da  ldsfld   string [mscorlib]System.String::Empty
0x137df  stloc.1
0x137e0  ldsfld   string [mscorlib]System.String::Empty
0x137e5  stloc.2
0x137e6  ldarg.0
0x137e7  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x137ec  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x137f1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x137f6  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x137fb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13800  stloc.0
0x13801  ldloc.0
0x13802  brfalse.s loc_13833
0x13804  ldloc.0
0x13805  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1380a  ldc.i4.0
0x1380b  ble.s    loc_13833
0x1380d  ldstr    aForm_0// "Form"
0x13812  stloc.2
0x13813  ldarg.0
0x13814  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13819  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1381e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x13823  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x13828  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1382d  stloc.1
0x1382e  br       loc_138B9
0x13833  ldarg.0
0x13834  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13839  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1383e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x13843  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x13848  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1384d  stloc.0
0x1384e  ldloc.0
0x1384f  brfalse.s loc_1387D
0x13851  ldloc.0
0x13852  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13857  ldc.i4.0
0x13858  ble.s    loc_1387D
0x1385a  ldstr    aHeader// "Header"
0x1385f  stloc.2
0x13860  ldarg.0
0x13861  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13866  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1386b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x13870  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x13875  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1387a  stloc.1
0x1387b  br.s     loc_138B9
0x1387d  ldstr    aQuerystring// "QueryString"
0x13882  stloc.2
0x13883  ldarg.0
0x13884  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13889  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1388e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13893  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x13898  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1389d  stloc.0
0x1389e  ldarg.0
0x1389f  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x138a4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x138a9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x138ae  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x138b3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x138b8  stloc.1
0x138b9  ldloc.1
0x138ba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x138bf  brfalse.s loc_138CC
0x138c1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x138c6  stloc.3
0x138c7  br       loc_13A14
0x138cc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x138d1  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x138d6  ldstr    aWrpcTokenFrom0// "WRPC token from '{0}': '{1}' with time "...
0x138db  ldc.i4.3
0x138dc  newarr   [mscorlib]System.Object
0x138e1  dup
0x138e2  ldc.i4.0
0x138e3  ldstr    aForm_0// "Form"
0x138e8  stelem.ref
0x138e9  dup
0x138ea  ldc.i4.1
0x138eb  ldarg.0
0x138ec  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x138f1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x138f6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x138fb  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x13900  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13905  stelem.ref
0x13906  dup
0x13907  ldc.i4.2
0x13908  ldarg.0
0x13909  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x1390e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13913  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x13918  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x1391d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13922  stelem.ref
0x13923  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13928  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x1392d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x13932  ldstr    aWrpcTokenFrom0// "WRPC token from '{0}': '{1}' with time "...
0x13937  ldc.i4.3
0x13938  newarr   [mscorlib]System.Object
0x1393d  dup
0x1393e  ldc.i4.0
0x1393f  ldstr    aQuerystring// "QueryString"
0x13944  stelem.ref
0x13945  dup
0x13946  ldc.i4.1
0x13947  ldarg.0
0x13948  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x1394d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13952  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13957  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x1395c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13961  stelem.ref
0x13962  dup
0x13963  ldc.i4.2
0x13964  ldarg.0
0x13965  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x1396a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1396f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x13974  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x13979  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1397e  stelem.ref
0x1397f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13984  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x13989  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1398e  ldstr    aWrpcTokenFrom0// "WRPC token from '{0}': '{1}' with time "...
0x13993  ldc.i4.3
0x13994  newarr   [mscorlib]System.Object
0x13999  dup
0x1399a  ldc.i4.0
0x1399b  ldstr    aHeader// "Header"
0x139a0  stelem.ref
0x139a1  dup
0x139a2  ldc.i4.1
0x139a3  ldarg.0
0x139a4  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x139a9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x139ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x139b3  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x139b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x139bd  stelem.ref
0x139be  dup
0x139bf  ldc.i4.2
0x139c0  ldarg.0
0x139c1  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x139c6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x139cb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x139d0  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x139d5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x139da  stelem.ref
0x139db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x139e0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x139e5  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x139ea  ldstr    aWrpcTokenSourc// "WRPC token source: '{0}': TimeStamp: {1"...
0x139ef  ldc.i4.2
0x139f0  newarr   [mscorlib]System.Object
0x139f5  dup
0x139f6  ldc.i4.0
0x139f7  ldloc.2
0x139f8  stelem.ref
0x139f9  dup
0x139fa  ldc.i4.1
0x139fb  ldloc.1
0x139fc  stelem.ref
0x139fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13a02  ldloca.s 3
0x13a04  ldloc.1
0x13a05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13a0a  call     int64 [mscorlib]System.Convert::ToInt64(string, class [mscorlib]System.IFormatProvider)
0x13a0f  call     instance void [mscorlib]System.DateTime::.ctor(int64)
0x13a14  ldloc.0
0x13a15  brfalse  loc_13B91
0x13a1a  ldloc.0
0x13a1b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a20  ldc.i4.0
0x13a21  ble      loc_13B91
0x13a26  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x13a2b  brfalse  loc_13AF6
0x13a30  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookFatClient()
0x13a35  brfalse  loc_13AF6
0x13a3a  ldloc.3
0x13a3b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13a40  stloc.s  4
0x13a42  ldloca.s 4
0x13a44  ldc.i4.m1
0x13a45  ldarg.0
0x13a46  ldfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x13a4b  mul
0x13a4c  conv.r8
0x13a4d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x13a52  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x13a57  ldc.i4.0
0x13a58  blt.s    loc_13AD6
0x13a5a  ldloc.3
0x13a5b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13a60  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x13a65  ldc.i4.0
0x13a66  bgt.s    loc_13AD6
0x13a68  ldloc.0
0x13a69  ldarg.0
0x13a6a  ldarg.0
0x13a6b  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13a70  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13a75  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x13a7a  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x13a7f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13a84  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13a89  ldloc.3
0x13a8a  call     instance string Microsoft.Crm.Application.Security.WrpcContext::GenerateToken(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x13a8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13a94  brfalse.s loc_13AB6
0x13a96  ldarg.0
0x13a97  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13a9c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13aa1  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13aa6  ldc.i4.0
0x13aa7  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13aac  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13ab1  br       loc_13B8B
0x13ab6  ldarg.0
0x13ab7  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13abc  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13ac1  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13ac6  ldc.i4.1
0x13ac7  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13acc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13ad1  br       loc_13B8B
0x13ad6  ldarg.0
0x13ad7  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13adc  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13ae1  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13ae6  ldc.i4.2
0x13ae7  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13aec  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13af1  br       loc_13B8B
0x13af6  ldloc.0
0x13af7  call     unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CryptoRandom::ConvertKeyToBytes(string)
0x13afc  dup
0x13afd  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::GetKeyFromHash(unsigned int8[])
0x13b02  stloc.s  5
0x13b04  ldarg.0
0x13b05  ldloc.s  5
0x13b07  ldarg.0
0x13b08  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13b0d  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x13b12  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x13b17  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x13b1c  ldloc.3
0x13b1d  call     instance unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::ComputeWrpcTokenHash(class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey key, string actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x13b22  stloc.s  6
0x13b24  ldloc.s  6
0x13b26  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::CompareHash(unsigned int8[], unsigned int8[])
0x13b2b  brtrue.s loc_13B4A
0x13b2d  ldarg.0
0x13b2e  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13b33  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13b38  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13b3d  ldc.i4.1
0x13b3e  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13b43  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13b48  br.s     loc_13B8B
0x13b4a  ldloc.s  5
0x13b4c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmKey::get_Expired()
0x13b51  brfalse.s loc_13B70
0x13b53  ldarg.0
0x13b54  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13b59  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13b5e  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13b63  ldc.i4.2
0x13b64  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13b69  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13b6e  br.s     loc_13B8B
0x13b70  ldarg.0
0x13b71  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13b76  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13b7b  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13b80  ldc.i4.0
0x13b81  box      [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13b86  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13b8b  call     void Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState()
0x13b90  ret
0x13b91  ldarg.0
  ... truncated ...
```
