# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateOnlineFederation

- ea: `0x1ba00`
- end: `0x1baae`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateOnlineFederation`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x7cb0`
- `0x15590`
- `0x155b0`
- `0x155c0`
- `0x156a0`
- `0x1ba00`

## pseudocode

```c

```

## disassembly

```asm
0x1ba00  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x1ba05  stloc.0
0x1ba06  ldloc.0
0x1ba07  ldarg.0
0x1ba08  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1ba0d  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x1ba12  ldarg.0
0x1ba13  call     instance class [System]System.Uri class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_HomeRealmUri()
0x1ba18  ldnull
0x1ba19  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1ba1e  brfalse.s loc_1BA95
0x1ba20  ldarg.0
0x1ba21  call     instance string class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_UserPrincipalName()
0x1ba26  stloc.2
0x1ba27  ldloc.2
0x1ba28  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ba2d  brfalse.s loc_1BA8E
0x1ba2f  ldarg.0
0x1ba30  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1ba35  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_Windows()
0x1ba3a  callvirt instance class [System]System.Net.NetworkCredential [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential::get_ClientCredential()
0x1ba3f  callvirt instance string [System]System.Net.NetworkCredential::get_UserName()
0x1ba44  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1ba49  brfalse.s loc_1BA78
0x1ba4b  ldarg.0
0x1ba4c  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1ba51  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x1ba56  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x1ba5b  ldstr    aClientcredenti_2// "ClientCredentials.UserName.UserName"
0x1ba60  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0x1ba65  ldarg.0
0x1ba66  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1ba6b  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x1ba70  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x1ba75  stloc.2
0x1ba76  br.s     loc_1BA8E
0x1ba78  ldarg.0
0x1ba79  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1ba7e  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_Windows()
0x1ba83  callvirt instance class [System]System.Net.NetworkCredential [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential::get_ClientCredential()
0x1ba88  callvirt instance string [System]System.Net.NetworkCredential::get_UserName()
0x1ba8d  stloc.2
0x1ba8e  ldloc.0
0x1ba8f  ldloc.2
0x1ba90  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_UserPrincipalName(string value)
0x1ba95  ldarg.0
0x1ba96  call     instance class Microsoft.Xrm.Sdk.Client.IServiceManagement`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceManagement()
0x1ba9b  ldloc.0
0x1ba9c  callvirt instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.IServiceManagement`1<var<u1>>::Authenticate(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x1baa1  stloc.1
0x1baa2  ldloc.1
0x1baa3  brfalse.s loc_1BAAC
0x1baa5  ldloc.1
0x1baa6  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1baab  ret
0x1baac  ldnull
0x1baad  ret
```
