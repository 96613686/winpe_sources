# Microsoft.Crm.WebServices.ImportXmlService::RetrieveMissingComponents

- ea: `0xe010`
- end: `0xe04a`
- name: `Microsoft.Crm.WebServices.ImportXmlService::RetrieveMissingComponents`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xe010`
- `0xe130`

## string_xrefs

- `0xe011`: `customizationXml`

## pseudocode

```c

```

## disassembly

```asm
0xe010  ldarg.1
0xe011  ldstr    aCustomizationx// "customizationXml"
0xe016  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe01b  ldarg.2
0xe01c  ldstr    aContext// "context"
0xe021  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe026  ldarg.0
0xe027  ldarg.2
0xe028  call     instance void Microsoft.Crm.WebServices.ImportXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe02d  ldarg.1
0xe02e  ldarg.2
0xe02f  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::.ctor(unsigned int8[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe034  stloc.0
0xe035  ldloc.0
0xe036  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.MissingComponent[] [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::RetrieveMissingComponents()
0xe03b  stloc.1
0xe03c  leave.s  loc_E048
0xe03e  ldloc.0
0xe03f  brfalse.s loc_E047
0xe041  ldloc.0
0xe042  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe047  endfinally
0xe048  ldloc.1
0xe049  ret
```
