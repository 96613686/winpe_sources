# Microsoft.Crm.WebServices.ImportXmlService::GetComponents

- ea: `0xdfc0`
- end: `0xe00a`
- name: `Microsoft.Crm.WebServices.ImportXmlService::GetComponents`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe0c0`

## callees

- `0xdfc0`
- `0xe130`

## string_xrefs

- `0xdfc1`: `customizationXml`
- `0xdfe0`: `customizationXml`

## pseudocode

```c

```

## disassembly

```asm
0xdfc0  ldarg.1
0xdfc1  ldstr    aCustomizationx// "customizationXml"
0xdfc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xdfcb  ldarg.2
0xdfcc  ldstr    aContext// "context"
0xdfd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xdfd6  ldarg.0
0xdfd7  ldarg.2
0xdfd8  call     instance void Microsoft.Crm.WebServices.ImportXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdfdd  ldarg.1
0xdfde  brtrue.s loc_DFEB
0xdfe0  ldstr    aCustomizationx// "customizationXml"
0xdfe5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdfea  throw
0xdfeb  ldarg.1
0xdfec  ldarg.2
0xdfed  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::.ctor(unsigned int8[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xdff2  stloc.0
0xdff3  ldloc.0
0xdff4  ldc.i4.1
0xdff5  ldc.i4.1
0xdff6  callvirt instance string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetComponentsList(bool, bool)
0xdffb  stloc.1
0xdffc  leave.s  loc_E008
0xdffe  ldloc.0
0xdfff  brfalse.s loc_E007
0xe001  ldloc.0
0xe002  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe007  endfinally
0xe008  ldloc.1
0xe009  ret
```
