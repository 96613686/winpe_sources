# Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportSecurityPolicy

- ea: `0x15ab0`
- end: `0x15b1d`
- name: `Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportSecurityPolicy`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15710`

## callees

- `0x15ab0`
- `0x15b20`
- `0x15c60`

## pseudocode

```c

```

## disassembly

```asm
0x15ab0  ldc.i4.1
0x15ab1  stloc.0
0x15ab2  ldarg.2
0x15ab3  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext::get_BindingElements()
0x15ab8  callvirt T0x2B00005C
0x15abd  stloc.1
0x15abe  ldloc.1
0x15abf  brfalse.s loc_15AFB
0x15ac1  ldloc.1
0x15ac2  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x15ac7  ldstr    aAuthentication_0// "AuthenticationType"
0x15acc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x15ad1  brfalse.s loc_15AFB
0x15ad3  ldloc.1
0x15ad4  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x15ad9  ldstr    aAuthentication_0// "AuthenticationType"
0x15ade  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x15ae3  ldloca.s 2
0x15ae5  call     T0x2B00005E
0x15aea  brfalse.s loc_15AFB
0x15aec  ldloc.2
0x15aed  ldc.i4.4
0x15aee  beq.s    loc_15AF9
0x15af0  ldloc.2
0x15af1  ldc.i4.3
0x15af2  ceq
0x15af4  ldc.i4.0
0x15af5  ceq
0x15af7  br.s     loc_15AFA
0x15af9  ldc.i4.0
0x15afa  stloc.0
0x15afb  ldarg.0
0x15afc  ldfld    class [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::_importer
0x15b01  brfalse.s loc_15B1C
0x15b03  ldloc.0
0x15b04  brfalse.s loc_15B14
0x15b06  ldarg.0
0x15b07  ldfld    class [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::_importer
0x15b0c  ldarg.1
0x15b0d  ldarg.2
0x15b0e  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.IPolicyImportExtension::ImportPolicy(class [System.ServiceModel]System.ServiceModel.Description.MetadataImporter, class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext)
0x15b13  ret
0x15b14  ldarg.0
0x15b15  ldarg.1
0x15b16  ldarg.2
0x15b17  call     instance void Microsoft.Xrm.Sdk.Client.AuthenticationPolicyImporter::ImportSecurityPolicyWithoutMetadata(class [System.ServiceModel]System.ServiceModel.Description.MetadataImporter metadataImporter, class [System.ServiceModel]System.ServiceModel.Description.PolicyConversionContext context)
0x15b1c  ret
```
