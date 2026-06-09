# Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin

- ea: `0x29080`
- end: `0x291d9`
- name: `Microsoft.Crm.Metadata.AuditHelper::InvokeAuditMetadataPlugin`
- size: `345`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1ba60`
- `0x31880`
- `0x31b10`
- `0x757d0`

## callees

- `0xad20`
- `0xb7e0`
- `0x29080`
- `0x291e0`

## string_xrefs

- `0x29131`: `DeleteAttribute`
- `0x2909d`: `AuditMetadataPlugin is not invoked as we are not in server context`
- `0x290e0`: `AuditMetadataPlugin is not invoked here, as the code is getting executed in SDK path anyway`
- `0x2910a`: `UpdateEntity`
- `0x29117`: `DeleteEntity`
- `0x29124`: `UpdateAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x29080  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInServerContext()
0x29085  brtrue.s loc_290A9
0x29087  ldarg.s  4
0x29089  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2908e  ldc.i4.s 0x14
0x29090  ldstr    a0// "{0}"
0x29095  ldc.i4.1
0x29096  newarr   [mscorlib]System.Object
0x2909b  dup
0x2909c  ldc.i4.0
0x2909d  ldstr    aAuditmetadatap// "AuditMetadataPlugin is not invoked as w"...
0x290a2  stelem.ref
0x290a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x290a8  ret
0x290a9  ldarg.s  4
0x290ab  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x290b0  brfalse.s loc_290EC
0x290b2  ldarg.s  4
0x290b4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x290b9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x290be  ldstr    aImportsolution// "ImportSolution"
0x290c3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x290c8  brfalse.s loc_290EC
0x290ca  ldarg.s  4
0x290cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x290d1  ldc.i4.s 0x14
0x290d3  ldstr    a0// "{0}"
0x290d8  ldc.i4.1
0x290d9  newarr   [mscorlib]System.Object
0x290de  dup
0x290df  ldc.i4.0
0x290e0  ldstr    aAuditmetadatap_0// "AuditMetadataPlugin is not invoked here"...
0x290e5  stelem.ref
0x290e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x290eb  ret
0x290ec  ldsfld   string [mscorlib]System.String::Empty
0x290f1  stloc.0
0x290f2  ldsfld   string [mscorlib]System.String::Empty
0x290f7  stloc.1
0x290f8  ldloca.s 2
0x290fa  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x29100  ldc.i4.1
0x29101  ldarg.s  4
0x29103  newobj   instance void Microsoft.Crm.Sdk.Metadata.MetadataLoader::.ctor(bool retrieveAsIfPublished, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x29108  stloc.3
0x29109  ldarg.1
0x2910a  ldstr    aUpdateentity// "UpdateEntity"
0x2910f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29114  brtrue.s loc_2913F
0x29116  ldarg.1
0x29117  ldstr    aDeleteentity// "DeleteEntity"
0x2911c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x29121  brtrue.s loc_29151
0x29123  ldarg.1
0x29124  ldstr    aUpdateattribut// "UpdateAttribute"
0x29129  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2912e  brtrue.s loc_2915B
0x29130  ldarg.1
0x29131  ldstr    aDeleteattribut// "DeleteAttribute"
0x29136  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2913b  brtrue.s loc_29170
0x2913d  br.s     loc_2917B
0x2913f  ldloc.3
0x29140  ldarg.0
0x29141  callvirt instance string Microsoft.Crm.Sdk.Metadata.MetadataLoader::GetEntityName(valuetype [mscorlib]System.Guid entityId)
0x29146  stloc.0
0x29147  ldloca.s 2
0x29149  ldarg.3
0x2914a  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2914f  br.s     loc_2917B
0x29151  ldloc.3
0x29152  ldarg.0
0x29153  callvirt instance string Microsoft.Crm.Sdk.Metadata.MetadataLoader::GetEntityName(valuetype [mscorlib]System.Guid entityId)
0x29158  stloc.0
0x29159  br.s     loc_2917B
0x2915b  ldloc.3
0x2915c  ldarg.0
0x2915d  ldloca.s 0
0x2915f  ldloca.s 1
0x29161  call     void Microsoft.Crm.Metadata.AuditHelper::GetEntityAndAttributeNames(class Microsoft.Crm.Sdk.Metadata.MetadataLoader loader, valuetype [mscorlib]System.Guid targetId, [out] string& entityLogicalName, [out] string& attributeLogicalName)
0x29166  ldloca.s 2
0x29168  ldarg.3
0x29169  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2916e  br.s     loc_2917B
0x29170  ldloc.3
0x29171  ldarg.0
0x29172  ldloca.s 0
0x29174  ldloca.s 1
0x29176  call     void Microsoft.Crm.Metadata.AuditHelper::GetEntityAndAttributeNames(class Microsoft.Crm.Sdk.Metadata.MetadataLoader loader, valuetype [mscorlib]System.Guid targetId, [out] string& entityLogicalName, [out] string& attributeLogicalName)
0x2917b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x29180  stloc.s  4
0x29182  ldloc.0
0x29183  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29188  brtrue.s loc_29197
0x2918a  ldloc.s  4
0x2918c  ldstr    aEntitylogicaln_0// "EntityLogicalName"
0x29191  ldloc.0
0x29192  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x29197  ldloc.1
0x29198  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2919d  brtrue.s loc_291AC
0x2919f  ldloc.s  4
0x291a1  ldstr    aLogicalname_0// "LogicalName"
0x291a6  ldloc.1
0x291a7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x291ac  ldloca.s 2
0x291ae  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x291b3  brfalse.s loc_291CD
0x291b5  ldloc.s  4
0x291b7  ldstr    aIsauditenabled_0// "IsAuditEnabled"
0x291bc  ldloca.s 2
0x291be  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x291c3  box      [mscorlib]System.Boolean
0x291c8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x291cd  ldloc.s  4
0x291cf  ldarg.1
0x291d0  ldarg.2
0x291d1  ldarg.s  4
0x291d3  call     void [Microsoft.Crm.Audit]Microsoft.Crm.AuditMetadataPlugin::InvokePluginFromCode(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x291d8  ret
```
