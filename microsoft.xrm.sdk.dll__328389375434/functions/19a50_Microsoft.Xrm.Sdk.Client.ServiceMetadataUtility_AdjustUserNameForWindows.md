# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::AdjustUserNameForWindows

- ea: `0x19a50`
- end: `0x19b8b`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::AdjustUserNameForWindows`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x162a0`
- `0x1bce0`

## callees

- `0x7ca0`
- `0x19a50`

## pseudocode

```c

```

## disassembly

```asm
0x19a50  ldarg.0
0x19a51  ldstr    aClientcredenti_0// "clientCredentials"
0x19a56  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x19a5b  ldarg.0
0x19a5c  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19a61  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19a66  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x19a6b  brfalse.s loc_19A6E
0x19a6d  ret
0x19a6e  ldnull
0x19a6f  stloc.0
0x19a70  ldarg.0
0x19a71  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19a76  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19a7b  ldc.i4.s 0x40
0x19a7d  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x19a82  ldc.i4.m1
0x19a83  ble.s    loc_19ADC
0x19a85  ldarg.0
0x19a86  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19a8b  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19a90  ldc.i4.1
0x19a91  newarr   [mscorlib]System.Char
0x19a96  dup
0x19a97  ldc.i4.0
0x19a98  ldc.i4.s 0x40
0x19a9a  stelem.i2
0x19a9b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x19aa0  stloc.1
0x19aa1  ldloc.1
0x19aa2  ldlen
0x19aa3  conv.i4
0x19aa4  ldc.i4.1
0x19aa5  ble.s    loc_19AC3
0x19aa7  ldloc.1
0x19aa8  ldc.i4.0
0x19aa9  ldelem.ref
0x19aaa  ldarg.0
0x19aab  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19ab0  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_Password()
0x19ab5  ldloc.1
0x19ab6  ldc.i4.1
0x19ab7  ldelem.ref
0x19ab8  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string, string)
0x19abd  stloc.0
0x19abe  br       loc_19B5E
0x19ac3  ldloc.1
0x19ac4  ldc.i4.0
0x19ac5  ldelem.ref
0x19ac6  ldarg.0
0x19ac7  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19acc  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_Password()
0x19ad1  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string)
0x19ad6  stloc.0
0x19ad7  br       loc_19B5E
0x19adc  ldarg.0
0x19add  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19ae2  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19ae7  ldc.i4.s 0x5C
0x19ae9  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x19aee  ldc.i4.m1
0x19aef  ble.s    loc_19B42
0x19af1  ldarg.0
0x19af2  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19af7  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19afc  ldc.i4.1
0x19afd  newarr   [mscorlib]System.Char
0x19b02  dup
0x19b03  ldc.i4.0
0x19b04  ldc.i4.s 0x5C
0x19b06  stelem.i2
0x19b07  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x19b0c  stloc.2
0x19b0d  ldloc.2
0x19b0e  ldlen
0x19b0f  conv.i4
0x19b10  ldc.i4.1
0x19b11  ble.s    loc_19B2C
0x19b13  ldloc.2
0x19b14  ldc.i4.1
0x19b15  ldelem.ref
0x19b16  ldarg.0
0x19b17  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b1c  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_Password()
0x19b21  ldloc.2
0x19b22  ldc.i4.0
0x19b23  ldelem.ref
0x19b24  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string, string)
0x19b29  stloc.0
0x19b2a  br.s     loc_19B5E
0x19b2c  ldloc.2
0x19b2d  ldc.i4.0
0x19b2e  ldelem.ref
0x19b2f  ldarg.0
0x19b30  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b35  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_Password()
0x19b3a  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string)
0x19b3f  stloc.0
0x19b40  br.s     loc_19B5E
0x19b42  ldarg.0
0x19b43  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b48  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_UserName()
0x19b4d  ldarg.0
0x19b4e  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b53  callvirt instance string [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::get_Password()
0x19b58  newobj   instance void [System]System.Net.NetworkCredential::.ctor(string, string)
0x19b5d  stloc.0
0x19b5e  ldarg.0
0x19b5f  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_Windows()
0x19b64  ldloc.0
0x19b65  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.WindowsClientCredential::set_ClientCredential(class [System]System.Net.NetworkCredential)
0x19b6a  ldarg.0
0x19b6b  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b70  ldsfld   string [mscorlib]System.String::Empty
0x19b75  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::set_UserName(string)
0x19b7a  ldarg.0
0x19b7b  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_UserName()
0x19b80  ldsfld   string [mscorlib]System.String::Empty
0x19b85  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.UserNamePasswordClientCredential::set_Password(string)
0x19b8a  ret
```
