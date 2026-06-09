# Microsoft.Crm.Asynchronous.AsyncHandlerHost::RetrieveOrganizationConfiguration

- ea: `0x620`
- end: `0x66d`
- name: `Microsoft.Crm.Asynchronous.AsyncHandlerHost::RetrieveOrganizationConfiguration`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x480`
- `0x540`

## callees

- `0x620`
- `0xc70`

## string_xrefs

- `0x640`: `Organization {0} under Scalegroup={1} was not found in cache.`

## pseudocode

```c

```

## disassembly

```asm
0x620  ldnull
0x621  stloc.0
0x622  ldarg.0
0x623  ldfld    class Microsoft.Crm.Asynchronous.AsyncService Microsoft.Crm.Asynchronous.AsyncHandlerHost::asyncService
0x628  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::get_Configuration()
0x62d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x632  ldarg.1
0x633  ldloca.s 0
0x635  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::TryGetValue(var<u1>, !!T0)
0x63a  brtrue.s loc_66B
0x63c  ldnull
0x63d  ldarg.1
0x63e  ldc.i4.s 0x15
0x640  ldstr    aOrganization0U// "Organization {0} under Scalegroup={1} w"...
0x645  ldc.i4.2
0x646  newarr   [mscorlib]System.Object
0x64b  dup
0x64c  ldc.i4.0
0x64d  ldarg.1
0x64e  box      [mscorlib]System.Guid
0x653  stelem.ref
0x654  dup
0x655  ldc.i4.1
0x656  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x65b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x660  box      [mscorlib]System.Guid
0x665  stelem.ref
0x666  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x66b  ldloc.0
0x66c  ret
```
