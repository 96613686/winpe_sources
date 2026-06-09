# Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginAssemblyContent

- ea: `0x35c0`
- end: `0x362d`
- name: `Microsoft.Crm.Sandbox.SandboxPluginHelper::GetPluginAssemblyContent`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23d0`

## callees

- `0x3630`

## string_xrefs

- `0x35c1`: `pluginAssemblyId`
- `0x35de`: `SandboxPluginHelper.GetPluginAssemblyContent: enter`
- `0x3611`: `pluginassembly`

## pseudocode

```c

```

## disassembly

```asm
0x35c0  ldarg.0
0x35c1  ldstr    aPluginassembly// "pluginAssemblyId"
0x35c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x35cb  ldarg.1
0x35cc  ldstr    aContext// "context"
0x35d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x35d6  ldarg.1
0x35d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x35dc  ldc.i4.s 0x21
0x35de  ldstr    aSandboxpluginh// "SandboxPluginHelper.GetPluginAssemblyCo"...
0x35e3  ldc.i4.0
0x35e4  newarr   [mscorlib]System.Object
0x35e9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35ee  ldarg.1
0x35ef  ldarg.1
0x35f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x35f5  ldc.i4.0
0x35f6  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Sandbox.SandboxPluginHelper::GetOrganizationService(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, valuetype [mscorlib]System.Guid userId, bool forReports)
0x35fb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x3600  stloc.0
0x3601  ldloc.0
0x3602  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<string> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::get_Columns()
0x3607  ldstr    aContent// "content"
0x360c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x3611  ldstr    aPluginassembly_0// "pluginassembly"
0x3616  ldarg.0
0x3617  ldloc.0
0x3618  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x361d  ldstr    aContent// "content"
0x3622  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3627  castclass [mscorlib]System.String
0x362c  ret
```
