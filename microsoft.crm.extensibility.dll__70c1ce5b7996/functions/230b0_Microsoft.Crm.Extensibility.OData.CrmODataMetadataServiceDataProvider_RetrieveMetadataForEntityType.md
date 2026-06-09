# Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType

- ea: `0x230b0`
- end: `0x231fc`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveMetadataForEntityType`
- size: `332`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x218d0`
- `0x21d70`
- `0x21ec0`
- `0x22320`
- `0x22930`
- `0x22a50`
- `0x23610`

## callees

- `0x230b0`
- `0x23200`
- `0x23370`
- `0x245a0`
- `0x245d0`
- `0x24600`
- `0x24620`
- `0x24c40`

## pseudocode

```c

```

## disassembly

```asm
0x230b0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::.ctor()
0x230b5  stloc.0
0x230b6  ldloc.0
0x230b7  ldarg.2
0x230b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression)
0x230bd  ldarg.0
0x230be  ldloc.0
0x230bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request)
0x230c4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse
0x230c9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMetadataChangesResponse::get_EntityMetadata()
0x230ce  stloc.1
0x230cf  ldnull
0x230d0  stloc.2
0x230d1  ldarg.1
0x230d2  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsEntityMetadata(class [mscorlib]System.Type xrmType)
0x230d7  brfalse.s loc_230E7
0x230d9  ldloc.1
0x230da  call     T0x2B0000CE
0x230df  stloc.3
0x230e0  ldloc.3
0x230e1  stloc.2
0x230e2  br       loc_231FA
0x230e7  ldarg.1
0x230e8  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsAttributeMetadata(class [mscorlib]System.Type xrmType)
0x230ed  brfalse.s loc_23169
0x230ef  ldarg.3
0x230f0  brfalse.s loc_23114
0x230f2  ldloc.1
0x230f3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::get_Count()
0x230f8  brtrue.s loc_23114
0x230fa  ldc.i4   0x194
0x230ff  ldstr    aEntityWithId0D// "Entity With Id = {0} does not exist."
0x23104  ldc.i4.1
0x23105  newarr   [mscorlib]System.Object
0x2310a  dup
0x2310b  ldc.i4.0
0x2310c  ldarg.3
0x2310d  stelem.ref
0x2310e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x23113  throw
0x23114  ldloc.1
0x23115  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool> <>c::<>9__35_0
0x2311a  dup
0x2311b  brtrue.s loc_23134
0x2311d  pop
0x2311e  ldsfld   class <>c <>c::<>9
0x23123  ldftn    instance bool <>c::<RetrieveMetadataForEntityType>b__35_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x23129  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool>::.ctor(object, native int)
0x2312e  dup
0x2312f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool> <>c::<>9__35_0
0x23134  call     T0x2B0000CF
0x23139  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[]> <>c::<>9__35_1
0x2313e  dup
0x2313f  brtrue.s loc_23158
0x23141  pop
0x23142  ldsfld   class <>c <>c::<>9
0x23147  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[] <>c::<RetrieveMetadataForEntityType>b__35_1(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x2314d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[]>::.ctor(object, native int)
0x23152  dup
0x23153  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[]> <>c::<>9__35_1
0x23158  call     T0x2B0000D0
0x2315d  ldc.i4.0
0x2315e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetMetadataArrayFromIEnumerable(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[]> metadataArrayCollection, [opt] bool unique)
0x23163  stloc.2
0x23164  br       loc_231FA
0x23169  ldarg.1
0x2316a  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsRelationshipMetadata(class [mscorlib]System.Type xrmType)
0x2316f  brfalse.s loc_2317D
0x23171  ldloc.1
0x23172  ldloc.2
0x23173  ldarg.s  4
0x23175  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetRelationshipMetadataFromEntityMetadataCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadataCollection collection, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] result, string crmRelationshipName)
0x2317a  stloc.2
0x2317b  br.s     loc_231FA
0x2317d  ldarg.1
0x2317e  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsEntityKeyMetadata(class [mscorlib]System.Type xrmType)
0x23183  brfalse.s loc_231FA
0x23185  ldarg.3
0x23186  brfalse.s loc_231AA
0x23188  ldloc.1
0x23189  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata>::get_Count()
0x2318e  brtrue.s loc_231AA
0x23190  ldc.i4   0x194
0x23195  ldstr    aEntityWithId0D// "Entity With Id = {0} does not exist."
0x2319a  ldc.i4.1
0x2319b  newarr   [mscorlib]System.Object
0x231a0  dup
0x231a1  ldc.i4.0
0x231a2  ldarg.3
0x231a3  stelem.ref
0x231a4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x231a9  throw
0x231aa  ldloc.1
0x231ab  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool> <>c::<>9__35_2
0x231b0  dup
0x231b1  brtrue.s loc_231CA
0x231b3  pop
0x231b4  ldsfld   class <>c <>c::<>9
0x231b9  ldftn    instance bool <>c::<RetrieveMetadataForEntityType>b__35_2(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x231bf  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool>::.ctor(object, native int)
0x231c4  dup
0x231c5  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, bool> <>c::<>9__35_2
0x231ca  call     T0x2B0000CF
0x231cf  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityKeyMetadata[]> <>c::<>9__35_3
0x231d4  dup
0x231d5  brtrue.s loc_231EE
0x231d7  pop
0x231d8  ldsfld   class <>c <>c::<>9
0x231dd  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityKeyMetadata[] <>c::<RetrieveMetadataForEntityType>b__35_3(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x231e3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityKeyMetadata[]>::.ctor(object, native int)
0x231e8  dup
0x231e9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityKeyMetadata[]> <>c::<>9__35_3
0x231ee  call     T0x2B0000D1
0x231f3  ldc.i4.0
0x231f4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[] Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::GetMetadataArrayFromIEnumerable(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MetadataBase[]> metadataArrayCollection, [opt] bool unique)
0x231f9  stloc.2
0x231fa  ldloc.2
0x231fb  ret
```
