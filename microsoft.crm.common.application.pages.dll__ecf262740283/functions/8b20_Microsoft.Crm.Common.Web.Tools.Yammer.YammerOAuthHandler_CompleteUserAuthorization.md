# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteUserAuthorization

- ea: `0x8b20`
- end: `0x8c11`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::CompleteUserAuthorization`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x8a50`

## callees

- `0x88f0`
- `0x8910`
- `0x8a20`
- `0x8b20`

## pseudocode

```c

```

## disassembly

```asm
0x8b20  ldarg.0
0x8b21  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_OAuthTokenResponse()
0x8b26  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x8b2b  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerContact [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_Contact()
0x8b30  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress> [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerContact::get_EmailAddresses()
0x8b35  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress, bool> <>c::<>9__12_0
0x8b3a  dup
0x8b3b  brtrue.s loc_8B54
0x8b3d  pop
0x8b3e  ldsfld   class <>c <>c::<>9
0x8b43  ldftn    instance bool <>c::<CompleteUserAuthorization>b__12_0(class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress a)
0x8b49  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress, bool>::.ctor(object, native int)
0x8b4e  dup
0x8b4f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress, bool> <>c::<>9__12_0
0x8b54  call     T0x2B000006
0x8b59  stloc.0
0x8b5a  ldloc.0
0x8b5b  brtrue.s loc_8B78
0x8b5d  ldstr    aPrimaryEmailIs// "Primary email is missing in Yammer's re"...
0x8b62  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x8b67  ldc.i4   0x8005F105
0x8b6c  ldc.i4.0
0x8b6d  newarr   [mscorlib]System.Object
0x8b72  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x8b77  throw
0x8b78  ldarg.0
0x8b79  call     instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::get_OAuthTokenResponse()
0x8b7e  callvirt instance class [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AccessTokenResponse::get_User()
0x8b83  callvirt instance int32 [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.AuthenticatedUser::get_Id()
0x8b88  stloc.2
0x8b89  ldloca.s 2
0x8b8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8b90  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8b95  stloc.1
0x8b96  ldloc.1
0x8b97  call     string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::GetCurrentYammerUserId()
0x8b9c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8ba1  brfalse.s loc_8C09
0x8ba3  ldloc.0
0x8ba4  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress::get_Address()
0x8ba9  ldloc.1
0x8baa  call     bool [Microsoft.Crm.Common.Application.WebServices]Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::TrySaveEmailAndUserId(string, string)
0x8baf  brtrue.s loc_8BDB
0x8bb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8bb6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bbb  ldstr    aErrorMessage0x_1// "Error_Message_0x8004b016"
0x8bc0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8bc5  ldc.i4.1
0x8bc6  newarr   [mscorlib]System.Object
0x8bcb  dup
0x8bcc  ldc.i4.0
0x8bcd  ldloc.0
0x8bce  callvirt instance string [Microsoft.Crm.YammerIntegration]Microsoft.Crm.YammerIntegration.YammerEmailAddress::get_Address()
0x8bd3  stelem.ref
0x8bd4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8bd9  br.s     loc_8BE0
0x8bdb  ldsfld   string [mscorlib]System.String::Empty
0x8be0  stloc.3
0x8be1  ldstr    aYamoautherror// "YamOAuthError"
0x8be6  ldloc.3
0x8be7  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string, string)
0x8bec  dup
0x8bed  ldc.i4.1
0x8bee  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0x8bf3  dup
0x8bf4  ldc.i4.1
0x8bf5  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0x8bfa  stloc.s  4
0x8bfc  ldarg.0
0x8bfd  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x8c02  ldloc.s  4
0x8c04  callvirt instance void [System.Web]System.Web.HttpResponse::SetCookie(class [System.Web]System.Web.HttpCookie)
0x8c09  ldarg.0
0x8c0a  ldc.i4.1
0x8c0b  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthHandler::set_CloseWindow(bool value)
0x8c10  ret
```
