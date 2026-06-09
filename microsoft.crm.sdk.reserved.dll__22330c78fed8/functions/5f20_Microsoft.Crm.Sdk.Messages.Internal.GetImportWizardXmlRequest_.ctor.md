# Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlRequest::.ctor

- ea: `0x5f20`
- end: `0x5f48`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlRequest::.ctor`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5ea0`
- `0x5f00`

## string_xrefs

- `0x5f27`: `GetImportWizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x5f20  ldarg.0
0x5f21  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x5f26  ldarg.0
0x5f27  ldstr    aGetimportwizar// "GetImportWizardXml"
0x5f2c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x5f31  ldarg.0
0x5f32  ldnull
0x5f33  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlRequest::set_RequestData(string value)
0x5f38  ldarg.0
0x5f39  ldloca.s 0
0x5f3b  initobj  [mscorlib]System.Guid
0x5f41  ldloc.0
0x5f42  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlRequest::set_ImportId(valuetype [mscorlib]System.Guid value)
0x5f47  ret
```
