# Microsoft.Crm.ObjectModel.SavedQueryService::ValidateSavedQuery

- ea: `0x16f750`
- end: `0x16f9d2`
- name: `Microsoft.Crm.ObjectModel.SavedQueryService::ValidateSavedQuery`
- size: `642`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x16e180`
- `0x16e250`
- `0x16ed60`
- `0x16f070`
- `0x16f330`

## callees

- `0x16dd90`
- `0x16de40`
- `0x16f6c0`
- `0x16f750`
- `0x16f9e0`
- `0x16fa40`
- `0x16fc10`
- `0x16fce0`
- `0x16fd00`
- `0x16fdc0`

## string_xrefs

- `0x16f753`: `fetchxml`
- `0x16f769`: `fetchxml`
- `0x16f7bd`: `fetchxml`
- `0x16f7c7`: `fetchxml`
- `0x16f991`: `columnsetxml`
- `0x16f99e`: `columnsetxml`
- `0x16f88c`: `layoutxml`
- `0x16f932`: `layoutxml`
- `0x16f938`: `layoutxml`
- `0x16f954`: `layoutxml`
- `0x16f969`: `layoutxml`
- `0x16f980`: `Layout XML must begin with a node of type 'Element'`
- `0x16f9b5`: `Columnset XML must begin with a node of type 'Element'`

## pseudocode

```c

```

## disassembly

```asm
0x16f750  ldnull
0x16f751  stloc.0
0x16f752  ldarg.1
0x16f753  ldstr    aFetchxml// "fetchxml"
0x16f758  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f75d  brtrue   loc_16F884
0x16f762  ldc.i4.0
0x16f763  stloc.1
0x16f764  ldc.i4.0
0x16f765  stloc.2
0x16f766  ldc.i4.0
0x16f767  stloc.3
0x16f768  ldarg.1
0x16f769  ldstr    aFetchxml// "fetchxml"
0x16f76e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f773  castclass [mscorlib]System.String
0x16f778  stloc.s  4
0x16f77a  ldarg.2
0x16f77b  brfalse.s loc_16F7BC
0x16f77d  ldarg.1
0x16f77e  ldstr    aIsquickfindque// "isquickfindquery"
0x16f783  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f788  brfalse.s loc_16F7A4
0x16f78a  ldarg.1
0x16f78b  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f790  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f795  brfalse.s loc_16F7A4
0x16f797  ldarg.1
0x16f798  ldstr    aQuerytype// "querytype"
0x16f79d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f7a2  brtrue.s loc_16F7BC
0x16f7a4  ldarg.0
0x16f7a5  ldarg.1
0x16f7a6  ldarg.3
0x16f7a7  ldarg.s  4
0x16f7a9  ldloca.s 1
0x16f7ab  ldloca.s 2
0x16f7ad  ldloca.s 3
0x16f7af  ldloca.s 4
0x16f7b1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.SavedQueryService::RetrieveExistingValues(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32& returnedTypeCode, bool& isQuickFindQuery, bool& isLookupView, string& fetchXml)
0x16f7b6  stloc.0
0x16f7b7  br       loc_16F847
0x16f7bc  ldarg.1
0x16f7bd  ldstr    aFetchxml// "fetchxml"
0x16f7c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f7c7  ldstr    aFetchxml// "fetchxml"
0x16f7cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16f7d1  ldarg.1
0x16f7d2  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f7d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f7dc  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f7e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16f7e6  ldarg.1
0x16f7e7  ldstr    aQuerytype// "querytype"
0x16f7ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f7f1  ldstr    aQuerytype// "querytype"
0x16f7f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x16f7fb  ldarg.1
0x16f7fc  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f801  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f806  unbox.any [mscorlib]System.Int32
0x16f80b  stloc.1
0x16f80c  ldarg.1
0x16f80d  ldstr    aIsquickfindque// "isquickfindquery"
0x16f812  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f817  brfalse.s loc_16F826
0x16f819  ldarg.1
0x16f81a  ldstr    aIsquickfindque// "isquickfindquery"
0x16f81f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f824  br.s     loc_16F82C
0x16f826  ldc.i4.0
0x16f827  box      [mscorlib]System.Boolean
0x16f82c  unbox.any [mscorlib]System.Boolean
0x16f831  stloc.2
0x16f832  ldarg.1
0x16f833  ldstr    aQuerytype// "querytype"
0x16f838  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f83d  unbox.any [mscorlib]System.Int32
0x16f842  ldc.i4.s 0x40
0x16f844  ceq
0x16f846  stloc.3
0x16f847  ldloc.1
0x16f848  brfalse.s loc_16F861
0x16f84a  ldloc.2
0x16f84b  brtrue.s loc_16F861
0x16f84d  ldloc.3
0x16f84e  brtrue.s loc_16F861
0x16f850  ldarg.0
0x16f851  ldloc.s  4
0x16f853  ldarg.3
0x16f854  ldloc.1
0x16f855  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x16f85a  ldarg.s  4
0x16f85c  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateFetchXml(string fetchXml, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, valuetype [mscorlib]System.Nullable`1<int32> expectedReturnTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f861  ldarg.1
0x16f862  ldstr    aQuerytype// "querytype"
0x16f867  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f86c  brfalse.s loc_16F884
0x16f86e  ldarg.0
0x16f86f  ldarg.1
0x16f870  ldstr    aQuerytype// "querytype"
0x16f875  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f87a  unbox.any [mscorlib]System.Int32
0x16f87f  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateQueryType(int32 queryType)
0x16f884  ldarg.0
0x16f885  ldarg.1
0x16f886  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateReturnTypeCode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery)
0x16f88b  ldarg.1
0x16f88c  ldstr    aLayoutxml// "layoutxml"
0x16f891  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f896  brtrue   loc_16F990
0x16f89b  ldc.i4.0
0x16f89c  stloc.s  5
0x16f89e  ldarg.2
0x16f89f  brfalse.s loc_16F90E
0x16f8a1  ldarg.s  4
0x16f8a3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x16f8a8  brfalse  loc_16F92D
0x16f8ad  ldarg.0
0x16f8ae  ldarg.s  4
0x16f8b0  call     instance int32 Microsoft.Crm.ObjectModel.SavedQueryService::GetYearFromEndPoint(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f8b5  ldc.i4   0x7D9
0x16f8ba  bge.s    loc_16F92D
0x16f8bc  ldarg.1
0x16f8bd  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f8c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f8c7  brtrue.s loc_16F8FA
0x16f8c9  ldloc.0
0x16f8ca  brtrue.s loc_16F8E6
0x16f8cc  ldarg.0
0x16f8cd  ldarg.1
0x16f8ce  ldstr    aSavedqueryid// "savedqueryid"
0x16f8d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f8d8  unbox.any [mscorlib]System.Guid
0x16f8dd  ldarg.3
0x16f8de  ldarg.s  4
0x16f8e0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.SavedQueryService::RetrieveSavedQueryAsUnpublished(valuetype [mscorlib]System.Guid savedQueryId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16f8e5  stloc.0
0x16f8e6  ldloc.0
0x16f8e7  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f8ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f8f1  unbox.any [mscorlib]System.Int32
0x16f8f6  stloc.s  5
0x16f8f8  br.s     loc_16F92D
0x16f8fa  ldarg.1
0x16f8fb  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f900  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f905  unbox.any [mscorlib]System.Int32
0x16f90a  stloc.s  5
0x16f90c  br.s     loc_16F92D
0x16f90e  ldarg.1
0x16f90f  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f914  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f919  brfalse.s loc_16F92D
0x16f91b  ldarg.1
0x16f91c  ldstr    aReturnedtypeco// "returnedtypecode"
0x16f921  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f926  unbox.any [mscorlib]System.Int32
0x16f92b  stloc.s  5
0x16f92d  ldloc.s  5
0x16f92f  brfalse.s loc_16F953
0x16f931  ldarg.1
0x16f932  ldstr    aLayoutxml// "layoutxml"
0x16f937  ldarg.1
0x16f938  ldstr    aLayoutxml// "layoutxml"
0x16f93d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f942  castclass [mscorlib]System.String
0x16f947  ldloc.s  5
0x16f949  call     string Microsoft.Crm.ObjectModel.LayoutXmlValidator::AddNewAttributesToLayoutXml(string layoutXml, int32 returnedTypeCode)
0x16f94e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x16f953  ldarg.1
0x16f954  ldstr    aLayoutxml// "layoutxml"
0x16f959  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f95e  castclass [mscorlib]System.String
0x16f963  call     void Microsoft.Crm.ObjectModel.LayoutXmlValidator::ValidateLayoutXml(string layoutXml)
0x16f968  ldarg.1
0x16f969  ldstr    aLayoutxml// "layoutxml"
0x16f96e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f973  castclass [mscorlib]System.String
0x16f978  call     valuetype [System.Xml]System.Xml.XmlNodeType [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::GetFirstXmlNodeType(string)
0x16f97d  ldc.i4.1
0x16f97e  beq.s    loc_16F990
0x16f980  ldstr    aLayoutXmlMustB// "Layout XML must begin with a node of ty"...
0x16f985  ldc.i4   0x80040203
0x16f98a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16f98f  throw
0x16f990  ldarg.1
0x16f991  ldstr    aColumnsetxml// "columnsetxml"
0x16f996  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16f99b  brtrue.s loc_16F9C5
0x16f99d  ldarg.1
0x16f99e  ldstr    aColumnsetxml// "columnsetxml"
0x16f9a3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16f9a8  castclass [mscorlib]System.String
0x16f9ad  call     valuetype [System.Xml]System.Xml.XmlNodeType [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::GetFirstXmlNodeType(string)
0x16f9b2  ldc.i4.1
0x16f9b3  beq.s    loc_16F9C5
0x16f9b5  ldstr    aColumnsetXmlMu// "Columnset XML must begin with a node of"...
0x16f9ba  ldc.i4   0x80040203
0x16f9bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16f9c4  throw
0x16f9c5  ldarg.0
0x16f9c6  ldloc.0
0x16f9c7  ldarg.3
0x16f9c8  ldarg.s  4
0x16f9ca  ldarg.2
0x16f9cb  ldarg.1
0x16f9cc  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ValidateDefaultView(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity retrievedEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isForUpdate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity savedquery)
0x16f9d1  ret
```
