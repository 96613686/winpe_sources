# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::AuthorWorkflow

- ea: `0x72d60`
- end: `0x72e3e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::AuthorWorkflow`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x72c30`

## callees

- `0x72d60`

## string_xrefs

- `0x72d69`: `WRPCTokenState`
- `0x72d7a`: `WRPCTokenState`
- `0x72d93`: `WRPCTokenState`
- `0x72daa`: `WRPCTokenState`
- `0x72e19`: `WRPCTokenState`
- `0x72e2b`: `WRPCTokenState`
- `0x72dbe`: `Microsoft.Crm.Common.Application.Platform.WorkflowLibrary.ProfileRuleWorkflowAuthoringHelper,Microsoft.Crm.Common.Application.Platform`

## pseudocode

```c

```

## disassembly

```asm
0x72d60  ldc.i4.0
0x72d61  stloc.0
0x72d62  ldc.i4.0
0x72d63  stloc.1
0x72d64  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72d69  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72d6e  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x72d73  brtrue.s loc_72D8E
0x72d75  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72d7a  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72d7f  ldc.i4.0
0x72d80  box      Microsoft.Crm.Tools.ImportExportPublish.WrpcTokenState
0x72d85  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x72d8a  ldc.i4.1
0x72d8b  stloc.0
0x72d8c  br.s     loc_72DBC
0x72d8e  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72d93  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72d98  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x72d9d  unbox.any [mscorlib]System.Int32
0x72da2  ldc.i4.1
0x72da3  bne.un.s loc_72DBC
0x72da5  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72daa  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72daf  ldc.i4.0
0x72db0  box      Microsoft.Crm.Tools.ImportExportPublish.WrpcTokenState
0x72db5  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x72dba  ldc.i4.1
0x72dbb  stloc.1
0x72dbc  ldnull
0x72dbd  stloc.2
0x72dbe  ldstr    aMicrosoftCrmCo// "Microsoft.Crm.Common.Application.Platfo"...
0x72dc3  ldc.i4.1
0x72dc4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x72dc9  dup
0x72dca  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x72dcf  stloc.3
0x72dd0  ldstr    aAuthorworkflow// "AuthorWorkflow"
0x72dd5  ldc.i4   0x100
0x72dda  ldnull
0x72ddb  ldloc.3
0x72ddc  ldc.i4.3
0x72ddd  newarr   [mscorlib]System.Object
0x72de2  dup
0x72de3  ldc.i4.0
0x72de4  ldarg.0
0x72de5  callvirt instance string [mscorlib]System.Object::ToString()
0x72dea  stelem.ref
0x72deb  dup
0x72dec  ldc.i4.1
0x72ded  ldstr    aIncident// "incident"
0x72df2  stelem.ref
0x72df3  dup
0x72df4  ldc.i4.2
0x72df5  ldarg.1
0x72df6  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowErrorVisitorContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72dfb  stelem.ref
0x72dfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x72e01  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[], class [mscorlib]System.Globalization.CultureInfo)
0x72e06  castclass [mscorlib]System.String
0x72e0b  stloc.2
0x72e0c  leave.s  loc_72E3C
0x72e0e  pop
0x72e0f  rethrow
0x72e11  ldloc.0
0x72e12  brfalse.s loc_72E23
0x72e14  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72e19  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72e1e  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x72e23  ldloc.1
0x72e24  brfalse.s loc_72E3B
0x72e26  call     class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Items()
0x72e2b  ldstr    aWrpctokenstate// "WRPCTokenState"
0x72e30  ldc.i4.1
0x72e31  box      [mscorlib]System.Int32
0x72e36  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x72e3b  endfinally
0x72e3c  ldloc.2
0x72e3d  ret
```
