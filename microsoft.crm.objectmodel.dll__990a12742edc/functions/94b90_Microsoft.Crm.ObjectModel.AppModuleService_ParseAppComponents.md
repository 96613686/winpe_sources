# Microsoft.Crm.ObjectModel.AppModuleService::ParseAppComponents

- ea: `0x94b90`
- end: `0x954f4`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::ParseAppComponents`
- size: `2404`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x91820`

## callees

- `0x94930`
- `0x94b90`

## string_xrefs

- `0x94c04`: `componenttype`
- `0x94c37`: `componenttype`
- `0x94c57`: `componenttype`
- `0x94b98`: `AppModuleService.ParseAppComponents(): START`
- `0x94bb6`: `AppModuleService.ParseAppComponents(): appModuleComponents size [{0}].`
- `0x94c19`: `AppModuleService.ParseAppComponents(): [{0}:{1}] [{2}:{3}].`
- `0x94e0d`: `AppModuleService.ParseAppComponents(): AppModuleComponents of [componenttype:{0}] with [objectid:{1}]`
- `0x94fa6`: `AppModuleService.ParseAppComponents(): AppModuleComponents of [componenttype:{0}] with [objectid:{1}]`
- `0x95248`: `AppModuleService.ParseAppComponents(): AppModuleComponents of [componenttype:{0}] with [objectid:{1}]`
- `0x953be`: `AppModuleService.ParseAppComponents(): AppModuleComponents of [componenttype:{0}] with [objectid:{1}]`
- `0x954e3`: `AppModuleService.ParseAppComponents(): END`

## pseudocode

```c

```

## disassembly

```asm
0x94b90  ldarg.3
0x94b91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94b96  ldc.i4.s 0x47
0x94b98  ldstr    aAppmoduleservi_99// "AppModuleService.ParseAppComponents(): "...
0x94b9d  ldc.i4.0
0x94b9e  newarr   [mscorlib]System.Object
0x94ba3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94ba8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::.ctor()
0x94bad  stloc.0
0x94bae  ldarg.3
0x94baf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94bb4  ldc.i4.s 0x47
0x94bb6  ldstr    aAppmoduleservi_100// "AppModuleService.ParseAppComponents(): "...
0x94bbb  ldc.i4.1
0x94bbc  newarr   [mscorlib]System.Object
0x94bc1  dup
0x94bc2  ldc.i4.0
0x94bc3  ldarg.1
0x94bc4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x94bc9  box      [mscorlib]System.Int32
0x94bce  stelem.ref
0x94bcf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94bd4  ldarg.1
0x94bd5  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x94bda  stloc.1
0x94bdb  br       loc_954A9
0x94be0  ldloc.1
0x94be1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x94be6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x94beb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x94bf0  stloc.2
0x94bf1  ldc.i4.m1
0x94bf2  stloc.3
0x94bf3  ldnull
0x94bf4  stloc.s  4
0x94bf6  dup
0x94bf7  ldstr    aObjectid// "objectid"
0x94bfc  ldloca.s 2
0x94bfe  callvirt T0x2B00003B
0x94c03  pop
0x94c04  ldstr    aComponenttype// "componenttype"
0x94c09  ldloca.s 3
0x94c0b  callvirt T0x2B00003C
0x94c10  pop
0x94c11  ldarg.3
0x94c12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94c17  ldc.i4.s 0x47
0x94c19  ldstr    aAppmoduleservi_101// "AppModuleService.ParseAppComponents(): "...
0x94c1e  ldc.i4.4
0x94c1f  newarr   [mscorlib]System.Object
0x94c24  dup
0x94c25  ldc.i4.0
0x94c26  ldstr    aObjectid// "objectid"
0x94c2b  stelem.ref
0x94c2c  dup
0x94c2d  ldc.i4.1
0x94c2e  ldloc.2
0x94c2f  box      [mscorlib]System.Guid
0x94c34  stelem.ref
0x94c35  dup
0x94c36  ldc.i4.2
0x94c37  ldstr    aComponenttype// "componenttype"
0x94c3c  stelem.ref
0x94c3d  dup
0x94c3e  ldc.i4.3
0x94c3f  ldloc.3
0x94c40  box      [mscorlib]System.Int32
0x94c45  stelem.ref
0x94c46  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94c4b  ldloc.2
0x94c4c  ldstr    aObjectid// "objectid"
0x94c51  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x94c56  ldloc.3
0x94c57  ldstr    aComponenttype// "componenttype"
0x94c5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x94c61  ldloc.3
0x94c62  ldc.i4.s 0x1A
0x94c64  bgt.s    loc_94C77
0x94c66  ldloc.3
0x94c67  ldc.i4.1
0x94c68  beq      loc_95418
0x94c6d  ldloc.3
0x94c6e  ldc.i4.s 0x1A
0x94c70  beq.s    loc_94CA8
0x94c72  br       loc_954A9
0x94c77  ldloc.3
0x94c78  ldc.i4.s 0x1D
0x94c7a  beq      loc_94E4D
0x94c7f  ldloc.3
0x94c80  ldc.i4.s 0x3B
0x94c82  sub
0x94c83  switch   loc_94E6A, loc_94FE8, loc_9528A, loc_95400
0x94c98  ldloc.3
0x94c99  ldc.i4   0xA1
0x94c9e  beq      loc_95461
0x94ca3  br       loc_954A9
0x94ca8  ldc.i4.3
0x94ca9  newarr   [mscorlib]System.String
0x94cae  dup
0x94caf  ldc.i4.0
0x94cb0  ldstr    aSavedqueryid// "savedqueryid"
0x94cb5  stelem.ref
0x94cb6  dup
0x94cb7  ldc.i4.1
0x94cb8  ldstr    aReturnedtypeco// "returnedtypecode"
0x94cbd  stelem.ref
0x94cbe  dup
0x94cbf  ldc.i4.2
0x94cc0  ldstr    aQuerytype// "querytype"
0x94cc5  stelem.ref
0x94cc6  stloc.s  5
0x94cc8  ldnull
0x94cc9  stloc.s  6
0x94ccb  ldarg.0
0x94ccc  ldstr    aSavedquery// "SavedQuery"
0x94cd1  ldloc.2
0x94cd2  ldstr    aSavedqueryid// "savedqueryid"
0x94cd7  ldloc.s  5
0x94cd9  ldloca.s 6
0x94cdb  ldarg.3
0x94cdc  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::TryRetrieveData(string platformName, valuetype [mscorlib]System.Guid objectId, string AttrNameObjectID, string[] columns, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection& collection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x94ce1  brfalse  loc_94DD9
0x94ce6  ldloc.s  6
0x94ce8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x94ced  stloc.s  0xB
0x94cef  br       loc_94DB3
0x94cf4  ldloc.s  0xB
0x94cf6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x94cfb  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x94d00  stloc.s  0xC
0x94d02  ldloc.s  0xC
0x94d04  ldstr    aReturnedtypeco// "returnedtypecode"
0x94d09  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94d0e  unbox.any [mscorlib]System.Int32
0x94d13  stloc.s  0xD
0x94d15  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType::.ctor()
0x94d1a  stloc.s  0xE
0x94d1c  ldloc.s  0xE
0x94d1e  ldloca.s 2
0x94d20  constrained. [mscorlib]System.Guid
0x94d26  callvirt instance string [mscorlib]System.Object::ToString()
0x94d2b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType::set_Id(string)
0x94d30  ldloc.s  0xE
0x94d32  ldloc.s  0xC
0x94d34  ldstr    aQuerytype// "querytype"
0x94d39  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94d3e  unbox.any [mscorlib]System.Int32
0x94d43  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType::set_Type(int32)
0x94d48  ldloc.0
0x94d49  ldloc.s  0xD
0x94d4b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::ContainsKey(var<u1>)
0x94d50  brfalse.s loc_94D68
0x94d52  ldloc.0
0x94d53  ldloc.s  0xD
0x94d55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::get_Item(void)
0x94d5a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType> [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::get_Views()
0x94d5f  ldloc.s  0xE
0x94d61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType>::Add(var<u1>)
0x94d66  br.s     loc_94DB3
0x94d68  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::.ctor()
0x94d6d  stloc.s  0xF
0x94d6f  ldarg.3
0x94d70  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x94d75  ldloc.s  0xD
0x94d77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x94d7c  stloc.s  4
0x94d7e  ldloc.s  0xF
0x94d80  ldloc.s  4
0x94d82  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x94d87  stloc.s  0x10
0x94d89  ldloca.s 0x10
0x94d8b  constrained. [mscorlib]System.Guid
0x94d91  callvirt instance string [mscorlib]System.Object::ToString()
0x94d96  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::set_EntityId(string)
0x94d9b  ldloc.s  0xF
0x94d9d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType> [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::get_Views()
0x94da2  ldloc.s  0xE
0x94da4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ArtifactIdType>::Add(var<u1>)
0x94da9  ldloc.0
0x94daa  ldloc.s  0xD
0x94dac  ldloc.s  0xF
0x94dae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::Add(var<u1>, !!T0)
0x94db3  ldloc.s  0xB
0x94db5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x94dba  brtrue   loc_94CF4
0x94dbf  leave    loc_954A9
0x94dc4  ldloc.s  0xB
0x94dc6  isinst   [mscorlib]System.IDisposable
0x94dcb  stloc.s  0x11
0x94dcd  ldloc.s  0x11
0x94dcf  brfalse.s loc_94DD8
0x94dd1  ldloc.s  0x11
0x94dd3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94dd8  endfinally
0x94dd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94dde  ldstr    aViewWithGuid0C// "View with guid {0} could not be found"
0x94de3  ldc.i4.1
0x94de4  newarr   [mscorlib]System.Object
0x94de9  dup
0x94dea  ldc.i4.0
0x94deb  ldloc.2
0x94dec  box      [mscorlib]System.Guid
0x94df1  stelem.ref
0x94df2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x94df7  ldc.i4   0x80040216
0x94dfc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x94e01  stloc.s  0x12
0x94e03  ldloc.s  0x12
0x94e05  ldarg.3
0x94e06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94e0b  ldc.i4.s 0x47
0x94e0d  ldstr    aAppmoduleservi_102// "AppModuleService.ParseAppComponents(): "...
0x94e12  ldc.i4.2
0x94e13  newarr   [mscorlib]System.Object
0x94e18  dup
0x94e19  ldc.i4.0
0x94e1a  ldstr    aSavedquery// "SavedQuery"
0x94e1f  stelem.ref
0x94e20  dup
0x94e21  ldc.i4.1
0x94e22  ldloc.2
0x94e23  box      [mscorlib]System.Guid
0x94e28  stelem.ref
0x94e29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94e2e  ldloc.s  0x12
0x94e30  ldarg.3
0x94e31  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94e36  ldc.i4.s 0x14
0x94e38  ldloc.s  0x12
0x94e3a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x94e3f  ldc.i4.0
0x94e40  newarr   [mscorlib]System.Object
0x94e45  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94e4a  ldloc.s  0x12
0x94e4c  throw
0x94e4d  ldarg.2
0x94e4e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppContext::get_bpfIds()
0x94e53  ldloca.s 2
0x94e55  constrained. [mscorlib]System.Guid
0x94e5b  callvirt instance string [mscorlib]System.Object::ToString()
0x94e60  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x94e65  br       loc_954A9
0x94e6a  ldc.i4.2
0x94e6b  newarr   [mscorlib]System.String
0x94e70  dup
0x94e71  ldc.i4.0
0x94e72  ldstr    aSavedqueryvisu_0// "savedqueryvisualizationid"
0x94e77  stelem.ref
0x94e78  dup
0x94e79  ldc.i4.1
0x94e7a  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x94e7f  stelem.ref
0x94e80  stloc.s  7
0x94e82  ldnull
0x94e83  stloc.s  6
0x94e85  ldarg.0
0x94e86  ldstr    aSavedqueryvisu// "SavedQueryVisualization"
0x94e8b  ldloc.2
0x94e8c  ldstr    aSavedqueryvisu_0// "savedqueryvisualizationid"
0x94e91  ldloc.s  7
0x94e93  ldloca.s 6
0x94e95  ldarg.3
0x94e96  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::TryRetrieveData(string platformName, valuetype [mscorlib]System.Guid objectId, string AttrNameObjectID, string[] columns, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection& collection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x94e9b  brfalse  loc_94F72
0x94ea0  ldloc.s  6
0x94ea2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x94ea7  stloc.s  0xB
0x94ea9  br       loc_94F4C
0x94eae  ldloc.s  0xB
0x94eb0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x94eb5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x94eba  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x94ebf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94ec4  unbox.any [mscorlib]System.Int32
0x94ec9  stloc.s  0x13
0x94ecb  ldloc.0
0x94ecc  ldloc.s  0x13
0x94ece  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::ContainsKey(var<u1>)
0x94ed3  brfalse.s loc_94EF6
0x94ed5  ldloc.0
0x94ed6  ldloc.s  0x13
0x94ed8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo>::get_Item(void)
0x94edd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::get_ChartIds()
0x94ee2  ldloca.s 2
0x94ee4  constrained. [mscorlib]System.Guid
0x94eea  callvirt instance string [mscorlib]System.Object::ToString()
0x94eef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x94ef4  br.s     loc_94F4C
0x94ef6  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppEntityInfo::.ctor()
0x94efb  stloc.s  0x14
0x94efd  ldarg.3
0x94efe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x94f03  ldloc.s  0x13
0x94f05  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x94f0a  stloc.s  4
0x94f0c  ldloc.s  0x14
0x94f0e  ldloc.s  4
0x94f10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x94f15  stloc.s  0x10
0x94f17  ldloca.s 0x10
  ... truncated ...
```
