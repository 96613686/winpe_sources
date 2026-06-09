# Microsoft.Crm.Platform.Server.VirtualEntityLookupExtension::RetrieveAndPopulatePrimaryFieldOfVirtualEntityOnRetrieveMultiple

- ea: `0x523c0`
- end: `0x525ee`
- name: `Microsoft.Crm.Platform.Server.VirtualEntityLookupExtension::RetrieveAndPopulatePrimaryFieldOfVirtualEntityOnRetrieveMultiple`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x523c0`
- `0x525f0`
- `0x52640`
- `0x526d0`
- `0x66b70`
- `0x66f10`
- `0x68910`
- `0x68940`
- `0x689f0`
- `0x6b3c0`
- `0x6b3d0`
- `0x89ed0`
- `0x89ef0`
- `0x89f10`
- `0x89f30`

## string_xrefs

- `0x524c4`: `Exception in VirtualEntityLookupExtension during RetrieveAndPopulatePrimaryFieldOfVirtualEntityOnRetrieveMultiple for VirtualEntityId:`
- `0x52580`: `Exception in VirtualEntityLookupExtension during RetrieveAndPopulatePrimaryFieldOfVirtualEntityOnRetrieveMultipleand RetrieveMultiple for VirtualEntityId: `

## pseudocode

```c

```

## disassembly

```asm
0x523c0  ldarg.2
0x523c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x523c6  stloc.0
0x523c7  ldarg.2
0x523c8  callvirt instance object Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Data()
0x523cd  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PrimaryFieldLookupInfo>
0x523d2  stloc.1
0x523d3  ldarg.2
0x523d4  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x523d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x523de  isinst   Microsoft.Crm.BusinessEntities.IPipelineExecutionContext
0x523e3  stloc.2
0x523e4  ldloc.2
0x523e5  brfalse.s loc_523FD
0x523e7  ldloc.0
0x523e8  brfalse.s loc_523FD
0x523ea  ldloc.0
0x523eb  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x523f0  brfalse.s loc_523FD
0x523f2  ldloc.1
0x523f3  brfalse.s loc_523FD
0x523f5  ldloc.1
0x523f6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PrimaryFieldLookupInfo>::get_Count()
0x523fb  brtrue.s loc_523FE
0x523fd  ret
0x523fe  ldloc.2
0x523ff  callvirt instance class [mscorlib]System.IServiceProvider Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_ServiceProvider()
0x52404  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x52409  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5240e  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x52413  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory
0x52418  ldarg.2
0x52419  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x5241e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x52423  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x52428  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x5242d  stloc.3
0x5242e  ldloc.1
0x5242f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class PrimaryFieldLookupInfo>::get_Values()
0x52434  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class PrimaryFieldLookupInfo>::GetEnumerator()
0x52439  stloc.s  4
0x5243b  br       loc_525D1
0x52440  ldloca.s 4
0x52442  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class PrimaryFieldLookupInfo>::get_Current()
0x52447  stloc.s  5
0x52449  ldarg.0
0x5244a  ldloc.0
0x5244b  ldloc.s  5
0x5244d  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Platform.Server.VirtualEntityLookupExtension::GetIDsOfEntitiesToLookup(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection entities, class PrimaryFieldLookupInfo column)
0x52452  stloc.s  6
0x52454  ldloc.s  6
0x52456  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x5245b  brfalse  loc_525D1
0x52460  newobj   instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x52465  stloc.s  7
0x52467  ldloc.s  6
0x52469  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x5246e  ldc.i4.1
0x5246f  bne.un.s loc_524EA
0x52471  ldc.i4.2
0x52472  newarr   [mscorlib]System.String
0x52477  dup
0x52478  ldc.i4.0
0x52479  ldloc.s  5
0x5247b  callvirt instance string PrimaryFieldLookupInfo::get_VirtualEntityPrimaryKeyLogicalName()
0x52480  stelem.ref
0x52481  dup
0x52482  ldc.i4.1
0x52483  ldloc.s  5
0x52485  callvirt instance string PrimaryFieldLookupInfo::get_VirtualEntityPrimaryFieldLogicalName()
0x5248a  stelem.ref
0x5248b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x52490  stloc.s  8
0x52492  ldloc.3
0x52493  ldloc.s  5
0x52495  callvirt instance string PrimaryFieldLookupInfo::get_VirtualEntityLogicalName()
0x5249a  ldloc.s  6
0x5249c  call     T0x2B000079
0x524a1  ldloc.s  8
0x524a3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x524a8  stloc.s  9
0x524aa  ldloc.s  7
0x524ac  ldloc.s  9
0x524ae  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x524b3  leave    loc_525C7
0x524b8  ldloc.2
0x524b9  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x524be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x524c3  ldc.i4.6
0x524c4  ldstr    aExceptionInVir_0// "Exception in VirtualEntityLookupExtensi"...
0x524c9  ldloc.s  5
0x524cb  callvirt instance valuetype [mscorlib]System.Guid PrimaryFieldLookupInfo::get_VirtualEntityId()
0x524d0  box      [mscorlib]System.Guid
0x524d5  call     string [mscorlib]System.String::Concat(object, object)
0x524da  ldc.i4.0
0x524db  newarr   [mscorlib]System.Object
0x524e0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x524e5  leave    loc_525C7
0x524ea  ldloc.s  6
0x524ec  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x524f1  ldc.i4   0xFA
0x524f6  bgt      loc_525BC
0x524fb  ldloc.s  6
0x524fd  call     T0x2B00006C
0x52502  stloc.s  0xA
0x52504  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0x52509  stloc.s  0xB
0x5250b  br.s     loc_52532
0x5250d  ldloc.s  0xB
0x5250f  ldloc.s  0xA
0x52511  ldc.i4.s 0x14
0x52513  call     T0x2B00007A
0x52518  call     T0x2B00006C
0x5251d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::Add(var<u1>)
0x52522  ldloc.s  0xA
0x52524  ldc.i4.s 0x14
0x52526  call     T0x2B00007B
0x5252b  call     T0x2B00006C
0x52530  stloc.s  0xA
0x52532  ldloc.s  0xA
0x52534  call     T0x2B00007C
0x52539  brtrue.s loc_5250D
0x5253b  ldloc.s  0xB
0x5253d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::GetEnumerator()
0x52542  stloc.s  0xC
0x52544  br.s     loc_525A3
0x52546  ldloca.s 0xC
0x52548  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Current()
0x5254d  stloc.s  0xD
0x5254f  ldloc.s  5
0x52551  ldloc.s  0xD
0x52553  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression Microsoft.Crm.Platform.Server.VirtualEntityLookupExtension::BuildQuery(class PrimaryFieldLookupInfo column, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids)
0x52558  stloc.s  0xE
0x5255a  ldloc.3
0x5255b  ldloc.s  0xE
0x5255d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x52562  stloc.s  0xF
0x52564  ldloc.s  7
0x52566  ldloc.s  0xF
0x52568  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x5256d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x52572  leave.s  loc_525A3
0x52574  ldloc.2
0x52575  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.IPipelineExecutionContext::get_PlatformContext()
0x5257a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5257f  ldc.i4.6
0x52580  ldstr    aExceptionInVir_1// "Exception in VirtualEntityLookupExtensi"...
0x52585  ldloc.s  5
0x52587  callvirt instance valuetype [mscorlib]System.Guid PrimaryFieldLookupInfo::get_VirtualEntityId()
0x5258c  box      [mscorlib]System.Guid
0x52591  call     string [mscorlib]System.String::Concat(object, object)
0x52596  ldc.i4.0
0x52597  newarr   [mscorlib]System.Object
0x5259c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x525a1  leave.s  loc_525A3
0x525a3  ldloca.s 0xC
0x525a5  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::MoveNext()
0x525aa  brtrue.s loc_52546
0x525ac  leave.s  loc_525C7
0x525ae  ldloca.s 0xC
0x525b0  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>
0x525b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x525bb  endfinally
0x525bc  ldstr    aQueryWithEntit// "Query with entity reference to virtual "...
0x525c1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x525c6  throw
0x525c7  ldloc.0
0x525c8  ldloc.s  5
0x525ca  ldloc.s  7
0x525cc  call     void Microsoft.Crm.Platform.Server.VirtualEntityLookupExtension::PopulatePrimaryFieldToEntityCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class PrimaryFieldLookupInfo column, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> virtualEntities)
0x525d1  ldloca.s 4
0x525d3  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class PrimaryFieldLookupInfo>::MoveNext()
0x525d8  brtrue   loc_52440
0x525dd  leave.s  loc_525ED
0x525df  ldloca.s 4
0x525e1  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class PrimaryFieldLookupInfo>
0x525e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x525ec  endfinally
0x525ed  ret
```
