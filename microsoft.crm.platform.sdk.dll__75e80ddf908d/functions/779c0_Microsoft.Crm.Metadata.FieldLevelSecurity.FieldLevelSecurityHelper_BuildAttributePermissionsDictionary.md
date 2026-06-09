# Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityHelper::BuildAttributePermissionsDictionary

- ea: `0x779c0`
- end: `0x77aaa`
- name: `Microsoft.Crm.Metadata.FieldLevelSecurity.FieldLevelSecurityHelper::BuildAttributePermissionsDictionary`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xad690`

## callees

- `0x779c0`
- `0x90a20`

## string_xrefs

- `0x77a25`: `readaccess`
- `0x77a3a`: `updateaccess`

## pseudocode

```c

```

## disassembly

```asm
0x779c0  ldc.i4.8
0x779c1  ldc.i4.s 0xB
0x779c3  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.AttributePermissions>::.ctor(int32, int32)
0x779c8  stloc.0
0x779c9  ldarg.0
0x779ca  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x779cf  call     T0x2B0000BB
0x779d4  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, object> <>c::<>9__14_0
0x779d9  dup
0x779da  brtrue.s loc_779F3
0x779dc  pop
0x779dd  ldsfld   class <>c <>c::<>9
0x779e2  ldftn    instance object <>c::<BuildAttributePermissionsDictionary>b__14_0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity be)
0x779e8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, object>::.ctor(object, native int)
0x779ed  dup
0x779ee  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, object> <>c::<>9__14_0
0x779f3  call     T0x2B0000BC
0x779f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.IGrouping`2<object, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::GetEnumerator()
0x779fd  stloc.1
0x779fe  br       loc_77A91
0x77a03  ldloc.1
0x77a04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<object, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Current()
0x77a09  stloc.2
0x77a0a  ldc.i4.0
0x77a0b  stloc.3
0x77a0c  ldc.i4.0
0x77a0d  stloc.s  4
0x77a0f  ldloc.2
0x77a10  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x77a15  stloc.s  5
0x77a17  br.s     loc_77A54
0x77a19  ldloc.s  5
0x77a1b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x77a20  stloc.s  6
0x77a22  ldloc.3
0x77a23  ldloc.s  6
0x77a25  ldstr    aReadaccess// "readaccess"
0x77a2a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x77a2f  unbox.any [mscorlib]System.Boolean
0x77a34  or
0x77a35  stloc.3
0x77a36  ldloc.s  4
0x77a38  ldloc.s  6
0x77a3a  ldstr    aUpdateaccess// "updateaccess"
0x77a3f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x77a44  unbox.any [mscorlib]System.Boolean
0x77a49  or
0x77a4a  stloc.s  4
0x77a4c  ldloc.3
0x77a4d  ldloc.s  4
0x77a4f  and
0x77a50  brfalse.s loc_77A54
0x77a52  leave.s  loc_77A6B
0x77a54  ldloc.s  5
0x77a56  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x77a5b  brtrue.s loc_77A19
0x77a5d  leave.s  loc_77A6B
0x77a5f  ldloc.s  5
0x77a61  brfalse.s loc_77A6A
0x77a63  ldloc.s  5
0x77a65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77a6a  endfinally
0x77a6b  ldloc.0
0x77a6c  ldloc.2
0x77a6d  callvirt instance var<u1> class [System.Core]System.Linq.IGrouping`2<object, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Key()
0x77a72  unbox.any [mscorlib]System.Guid
0x77a77  ldc.i4.0
0x77a78  ldloc.3
0x77a79  brtrue.s loc_77A7E
0x77a7b  ldc.i4.0
0x77a7c  br.s     loc_77A7F
0x77a7e  ldc.i4.4
0x77a7f  ldloc.s  4
0x77a81  brtrue.s loc_77A86
0x77a83  ldc.i4.0
0x77a84  br.s     loc_77A87
0x77a86  ldc.i4.4
0x77a87  newobj   instance void Microsoft.Crm.Caching.AttributePermissions::.ctor(int32 canCreate, int32 canRead, int32 canUpdate)
0x77a8c  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.AttributePermissions>::set_Item(var<u1>, !!T0)
0x77a91  ldloc.1
0x77a92  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x77a97  brtrue   loc_77A03
0x77a9c  leave.s  loc_77AA8
0x77a9e  ldloc.1
0x77a9f  brfalse.s loc_77AA7
0x77aa1  ldloc.1
0x77aa2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x77aa7  endfinally
0x77aa8  ldloc.0
0x77aa9  ret
```
