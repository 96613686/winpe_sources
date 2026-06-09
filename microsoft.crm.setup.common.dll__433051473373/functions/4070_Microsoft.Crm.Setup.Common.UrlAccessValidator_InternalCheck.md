# Microsoft.Crm.Setup.Common.UrlAccessValidator::InternalCheck

- ea: `0x4070`
- end: `0x417a`
- name: `Microsoft.Crm.Setup.Common.UrlAccessValidator::InternalCheck`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x4060`
- `0x4070`
- `0x4180`

## string_xrefs

- `0x40c1`: `UrlAccessValidator.Failure.TrustFailure`
- `0x40ec`: `UrlAccessValidator.Failure.SecureChannelFailure`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldarg.0
0x4071  ldc.i4.0
0x4072  call     instance void Microsoft.Crm.Setup.Common.UrlAccessValidator::set_HttpResponseForbidden(bool value)
0x4077  ldarg.0
0x4078  ldfld    class [System]System.Uri Microsoft.Crm.Setup.Common.UrlAccessValidator::_testUrl
0x407d  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x4082  castclass [System]System.Net.HttpWebRequest
0x4087  dup
0x4088  call     class [System]System.Net.ICredentials [System]System.Net.CredentialCache::get_DefaultCredentials()
0x408d  callvirt instance void [System]System.Net.WebRequest::set_Credentials(class [System]System.Net.ICredentials)
0x4092  dup
0x4093  ldc.i4   0x493E0
0x4098  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0x409d  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x40a2  pop
0x40a3  leave    loc_4171
0x40a8  stloc.0
0x40a9  ldarg.0
0x40aa  ldfld    class [System]System.Uri Microsoft.Crm.Setup.Common.UrlAccessValidator::_urlBase
0x40af  callvirt instance string [mscorlib]System.Object::ToString()
0x40b4  stloc.1
0x40b5  ldc.i4.s 9
0x40b7  ldloc.0
0x40b8  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x40bd  bne.un.s loc_40E0
0x40bf  ldc.i4.2
0x40c0  ldarg.0
0x40c1  ldstr    aUrlaccessvalid// "UrlAccessValidator.Failure.TrustFailure"
0x40c6  ldc.i4.1
0x40c7  newarr   [mscorlib]System.Object
0x40cc  dup
0x40cd  ldc.i4.0
0x40ce  ldloc.1
0x40cf  stelem.ref
0x40d0  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x40d5  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x40da  stloc.2
0x40db  leave    loc_4178
0x40e0  ldc.i4.s 0xA
0x40e2  ldloc.0
0x40e3  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x40e8  bne.un.s loc_4108
0x40ea  ldc.i4.2
0x40eb  ldarg.0
0x40ec  ldstr    aUrlaccessvalid_0// "UrlAccessValidator.Failure.SecureChanne"...
0x40f1  ldc.i4.1
0x40f2  newarr   [mscorlib]System.Object
0x40f7  dup
0x40f8  ldc.i4.0
0x40f9  ldloc.1
0x40fa  stelem.ref
0x40fb  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x4100  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x4105  stloc.2
0x4106  leave.s  loc_4178
0x4108  ldc.i4.2
0x4109  ldloc.0
0x410a  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x410f  bne.un.s loc_413C
0x4111  ldc.i4.2
0x4112  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4117  ldstr    a01// "{0} {1}"
0x411c  ldc.i4.2
0x411d  newarr   [mscorlib]System.Object
0x4122  dup
0x4123  ldc.i4.0
0x4124  ldloc.0
0x4125  callvirt instance string [mscorlib]System.Exception::get_Message()
0x412a  stelem.ref
0x412b  dup
0x412c  ldc.i4.1
0x412d  ldloc.1
0x412e  stelem.ref
0x412f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4134  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x4139  stloc.2
0x413a  leave.s  loc_4178
0x413c  ldloc.0
0x413d  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x4142  isinst   [System]System.Net.HttpWebResponse
0x4147  brfalse.s loc_4167
0x4149  ldc.i4   0x193
0x414e  ldloc.0
0x414f  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x4154  castclass [System]System.Net.HttpWebResponse
0x4159  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x415e  bne.un.s loc_4167
0x4160  ldarg.0
0x4161  ldc.i4.1
0x4162  call     instance void Microsoft.Crm.Setup.Common.UrlAccessValidator::set_HttpResponseForbidden(bool value)
0x4167  ldarg.0
0x4168  ldloc.0
0x4169  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo Microsoft.Crm.Setup.Common.UrlAccessValidator::ProcessWebException(class [System]System.Net.WebException e)
0x416e  stloc.2
0x416f  leave.s  loc_4178
0x4171  ldc.i4.0
0x4172  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x4177  ret
0x4178  ldloc.2
0x4179  ret
```
