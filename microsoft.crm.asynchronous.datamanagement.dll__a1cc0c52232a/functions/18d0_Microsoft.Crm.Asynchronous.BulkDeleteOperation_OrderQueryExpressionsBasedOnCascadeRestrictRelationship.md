# Microsoft.Crm.Asynchronous.BulkDeleteOperation::OrderQueryExpressionsBasedOnCascadeRestrictRelationship

- ea: `0x18d0`
- end: `0x1b9e`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::OrderQueryExpressionsBasedOnCascadeRestrictRelationship`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0x18d0  ldarg.1
0x18d1  ldlen
0x18d2  conv.i4
0x18d3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::.ctor(int32)
0x18d8  stloc.0
0x18d9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x18de  stloc.1
0x18df  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x18e4  stloc.2
0x18e5  ldc.i4.0
0x18e6  stloc.s  6
0x18e8  br.s     loc_194D
0x18ea  ldloc.0
0x18eb  ldarg.1
0x18ec  ldloc.s  6
0x18ee  ldelem.ref
0x18ef  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x18f4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::ContainsKey(var<u1>)
0x18f9  brfalse.s loc_1915
0x18fb  ldloc.0
0x18fc  ldarg.1
0x18fd  ldloc.s  6
0x18ff  ldelem.ref
0x1900  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x1905  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::get_Item(void)
0x190a  ldarg.1
0x190b  ldloc.s  6
0x190d  ldelem.ref
0x190e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::Add(var<u1>)
0x1913  br.s     loc_1947
0x1915  ldloc.1
0x1916  ldarg.1
0x1917  ldloc.s  6
0x1919  ldelem.ref
0x191a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x191f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1924  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::.ctor()
0x1929  stloc.s  7
0x192b  ldloc.s  7
0x192d  ldarg.1
0x192e  ldloc.s  6
0x1930  ldelem.ref
0x1931  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::Add(var<u1>)
0x1936  ldloc.0
0x1937  ldarg.1
0x1938  ldloc.s  6
0x193a  ldelem.ref
0x193b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x1940  ldloc.s  7
0x1942  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::Add(var<u1>, !!T0)
0x1947  ldloc.s  6
0x1949  ldc.i4.1
0x194a  add
0x194b  stloc.s  6
0x194d  ldloc.s  6
0x194f  ldarg.1
0x1950  ldlen
0x1951  conv.i4
0x1952  blt.s    loc_18EA
0x1954  ldloc.1
0x1955  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x195a  ldloc.1
0x195b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1960  newobj   instance void int32[0...,0...]::.ctor(int32, int32)
0x1965  stloc.3
0x1966  ldc.i4.0
0x1967  stloc.s  8
0x1969  br       loc_1A21
0x196e  ldarg.0
0x196f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1974  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1979  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x197e  ldloc.1
0x197f  ldloc.s  8
0x1981  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1986  ldc.i4.1
0x1987  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x198c  stloc.s  9
0x198e  ldloc.s  9
0x1990  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesTo()
0x1995  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x199a  stloc.s  0xA
0x199c  br.s     loc_19FB
0x199e  ldloc.s  0xA
0x19a0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19a5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0x19aa  stloc.s  0xB
0x19ac  ldloc.s  0xB
0x19ae  ldc.i4.1
0x19af  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::GetLinkType(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeActionType)
0x19b4  ldc.i4.3
0x19b5  bne.un.s loc_19FB
0x19b7  ldloc.1
0x19b8  ldloc.s  0xB
0x19ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x19bf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x19c4  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x19c9  brfalse.s loc_19FB
0x19cb  ldloc.s  9
0x19cd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x19d2  ldloc.s  0xB
0x19d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x19d9  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x19de  beq.s    loc_19FB
0x19e0  ldloc.3
0x19e1  ldloc.s  8
0x19e3  ldloc.1
0x19e4  ldloc.s  0xB
0x19e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0x19eb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x19f0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::IndexOf(var<u1>)
0x19f5  ldc.i4.1
0x19f6  call     instance void int32[0...,0...]::Set(int32, int32, int32)
0x19fb  ldloc.s  0xA
0x19fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a02  brtrue.s loc_199E
0x1a04  leave.s  loc_1A1B
0x1a06  ldloc.s  0xA
0x1a08  isinst   [mscorlib]System.IDisposable
0x1a0d  stloc.s  0xC
0x1a0f  ldloc.s  0xC
0x1a11  brfalse.s loc_1A1A
0x1a13  ldloc.s  0xC
0x1a15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a1a  endfinally
0x1a1b  ldloc.s  8
0x1a1d  ldc.i4.1
0x1a1e  add
0x1a1f  stloc.s  8
0x1a21  ldloc.s  8
0x1a23  ldloc.1
0x1a24  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1a29  blt      loc_196E
0x1a2e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1a33  stloc.s  4
0x1a35  ldc.i4.0
0x1a36  stloc.s  0xD
0x1a38  br       loc_1ADD
0x1a3d  ldc.i4.1
0x1a3e  stloc.s  0xE
0x1a40  ldc.i4.0
0x1a41  stloc.s  0xF
0x1a43  br.s     loc_1A5B
0x1a45  ldloc.3
0x1a46  ldloc.s  0xD
0x1a48  ldloc.s  0xF
0x1a4a  call     instance int32 int32[0...,0...]::Get(int32, int32)
0x1a4f  ldc.i4.1
0x1a50  bne.un.s loc_1A55
0x1a52  ldc.i4.0
0x1a53  stloc.s  0xE
0x1a55  ldloc.s  0xF
0x1a57  ldc.i4.1
0x1a58  add
0x1a59  stloc.s  0xF
0x1a5b  ldloc.s  0xF
0x1a5d  ldloc.3
0x1a5e  ldc.i4.1
0x1a5f  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x1a64  ble.s    loc_1A45
0x1a66  ldloc.s  0xE
0x1a68  brfalse.s loc_1AD7
0x1a6a  ldloc.s  4
0x1a6c  ldloc.1
0x1a6d  ldloc.s  0xD
0x1a6f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1a74  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1a79  brtrue.s loc_1AD7
0x1a7b  ldloc.s  4
0x1a7d  ldloc.1
0x1a7e  ldloc.s  0xD
0x1a80  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1a85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1a8a  ldc.i4.0
0x1a8b  stloc.s  0x10
0x1a8d  br.s     loc_1ACC
0x1a8f  ldloc.3
0x1a90  ldloc.s  0x10
0x1a92  ldloc.s  0xD
0x1a94  call     instance int32 int32[0...,0...]::Get(int32, int32)
0x1a99  ldc.i4.1
0x1a9a  bne.un.s loc_1ABB
0x1a9c  ldloc.2
0x1a9d  ldloc.1
0x1a9e  ldloc.s  0xD
0x1aa0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1aa5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1aaa  brfalse.s loc_1ABB
0x1aac  ldloc.2
0x1aad  ldloc.1
0x1aae  ldloc.s  0xD
0x1ab0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1ab5  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x1aba  pop
0x1abb  ldloc.3
0x1abc  ldloc.s  0x10
0x1abe  ldloc.s  0xD
0x1ac0  ldc.i4.0
0x1ac1  call     instance void int32[0...,0...]::Set(int32, int32, int32)
0x1ac6  ldloc.s  0x10
0x1ac8  ldc.i4.1
0x1ac9  add
0x1aca  stloc.s  0x10
0x1acc  ldloc.s  0x10
0x1ace  ldloc.3
0x1acf  ldc.i4.0
0x1ad0  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x1ad5  ble.s    loc_1A8F
0x1ad7  ldloc.s  0xD
0x1ad9  ldc.i4.1
0x1ada  add
0x1adb  stloc.s  0xD
0x1add  ldloc.s  0xD
0x1adf  ldloc.3
0x1ae0  ldc.i4.0
0x1ae1  callvirt instance int32 [mscorlib]System.Array::GetUpperBound(int32)
0x1ae6  ble      loc_1A3D
0x1aeb  ldloc.s  4
0x1aed  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1af2  ldloc.1
0x1af3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1af8  bne.un   loc_1A35
0x1afd  ldarg.0
0x1afe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::.ctor()
0x1b03  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_orderedQueryExpList
0x1b08  ldarg.0
0x1b09  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::.ctor()
0x1b0e  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_notOrderedQueryExpList
0x1b13  ldarg.0
0x1b14  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::.ctor()
0x1b19  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1b1e  ldc.i4.0
0x1b1f  stloc.s  0x11
0x1b21  br.s     loc_1B92
0x1b23  ldloc.2
0x1b24  ldloc.s  4
0x1b26  ldloc.s  0x11
0x1b28  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1b2d  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1b32  brfalse.s loc_1B61
0x1b34  ldloc.0
0x1b35  ldloc.s  4
0x1b37  ldloc.s  0x11
0x1b39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1b3e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::get_Item(void)
0x1b43  stloc.s  5
0x1b45  ldarg.0
0x1b46  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_notOrderedQueryExpList
0x1b4b  ldloc.s  5
0x1b4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b52  ldarg.0
0x1b53  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1b58  ldloc.s  5
0x1b5a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b5f  br.s     loc_1B8C
0x1b61  ldloc.0
0x1b62  ldloc.s  4
0x1b64  ldloc.s  0x11
0x1b66  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x1b6b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>>::get_Item(void)
0x1b70  stloc.s  5
0x1b72  ldarg.0
0x1b73  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_orderedQueryExpList
0x1b78  ldloc.s  5
0x1b7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b7f  ldarg.0
0x1b80  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1b85  ldloc.s  5
0x1b87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1b8c  ldloc.s  0x11
0x1b8e  ldc.i4.1
0x1b8f  add
0x1b90  stloc.s  0x11
0x1b92  ldloc.s  0x11
0x1b94  ldloc.s  4
0x1b96  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x1b9b  blt.s    loc_1B23
0x1b9d  ret
```
