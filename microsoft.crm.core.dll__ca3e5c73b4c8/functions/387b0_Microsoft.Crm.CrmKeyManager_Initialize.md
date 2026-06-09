# Microsoft.Crm.CrmKeyManager::Initialize

- ea: `0x387b0`
- end: `0x3886c`
- name: `Microsoft.Crm.CrmKeyManager::Initialize`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x388f0`
- `0x38930`

## callees

- `0x37b30`
- `0x37f00`
- `0x387b0`
- `0x38870`
- `0x397b0`
- `0x3d3c0`
- `0x3d400`

## string_xrefs

- `0x38842`: `Crm Key generator thread.`
- `0x38860`: `Crm Key archiver thread.`

## pseudocode

```c

```

## disassembly

```asm
0x387b0  ldarg.0
0x387b1  ldc.i4.0
0x387b2  stfld    bool Microsoft.Crm.CrmKeyManager::_running
0x387b7  ldarg.0
0x387b8  newobj   instance void Microsoft.Crm.ThreadManager::.ctor()
0x387bd  stfld    class Microsoft.Crm.ThreadManager Microsoft.Crm.CrmKeyManager::_threadManager
0x387c2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType>::.ctor()
0x387c7  stloc.0
0x387c8  newobj   instance void class Microsoft.Crm.EnumEnumerable`1<valuetype Microsoft.Crm.CrmKeyType>::.ctor()
0x387cd  call     instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.Crm.EnumEnumerable`1<valuetype Microsoft.Crm.CrmKeyType>::GetEnumerator()
0x387d2  stloc.3
0x387d3  br.s     loc_387EF
0x387d5  ldloc.3
0x387d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype Microsoft.Crm.CrmKeyType>::get_Current()
0x387db  stloc.s  4
0x387dd  ldarg.1
0x387de  ldloc.s  4
0x387e0  call     valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.CrmKeySetting::GetKeySettingScope(valuetype Microsoft.Crm.CrmKeyType keyType)
0x387e5  bne.un.s loc_387EF
0x387e7  ldloc.0
0x387e8  ldloc.s  4
0x387ea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType>::Add(var<u1>)
0x387ef  ldloc.3
0x387f0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x387f5  brtrue.s loc_387D5
0x387f7  leave.s  loc_38803
0x387f9  ldloc.3
0x387fa  brfalse.s loc_38802
0x387fc  ldloc.3
0x387fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38802  endfinally
0x38803  ldstr    aMscrmkeygenera// "MSCRMKeyGenerator"
0x38808  call     class Microsoft.Crm.CrmEventLog Microsoft.Crm.CrmKeyManager::CreateEventLog(string eventSource)
0x3880d  ldloc.0
0x3880e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType>::ToArray()
0x38813  newobj   instance void Microsoft.Crm.CrmKeyGenerator::.ctor(class Microsoft.Crm.ICrmEventLog eventLog, valuetype Microsoft.Crm.CrmKeyType[] keyTypes)
0x38818  stloc.1
0x38819  ldstr    aMscrmkeyarchiv// "MSCRMKeyArchiveManager"
0x3881e  call     class Microsoft.Crm.CrmEventLog Microsoft.Crm.CrmKeyManager::CreateEventLog(string eventSource)
0x38823  ldloc.0
0x38824  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType>::ToArray()
0x38829  newobj   instance void Microsoft.Crm.CrmKeyArchiveManager::.ctor(class Microsoft.Crm.CrmEventLog eventLog, valuetype Microsoft.Crm.CrmKeyType[] keyTypes)
0x3882e  stloc.2
0x3882f  ldarg.0
0x38830  ldfld    class Microsoft.Crm.ThreadManager Microsoft.Crm.CrmKeyManager::_threadManager
0x38835  ldloc.1
0x38836  ldftn    instance void Microsoft.Crm.CrmKeyGenerator::ManageKeys()
0x3883c  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x38841  ldloc.1
0x38842  ldstr    aCrmKeyGenerato// "Crm Key generator thread."
0x38847  callvirt instance int32 Microsoft.Crm.ThreadManager::AddThread(class [mscorlib]System.Threading.ThreadStart threadStart, class Microsoft.Crm.ThreadControllable threadClass, string name)
0x3884c  pop
0x3884d  ldarg.0
0x3884e  ldfld    class Microsoft.Crm.ThreadManager Microsoft.Crm.CrmKeyManager::_threadManager
0x38853  ldloc.2
0x38854  ldftn    instance void Microsoft.Crm.CrmKeyArchiveManager::ManageArchivedKeys()
0x3885a  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x3885f  ldloc.2
0x38860  ldstr    aCrmKeyArchiver// "Crm Key archiver thread."
0x38865  callvirt instance int32 Microsoft.Crm.ThreadManager::AddThread(class [mscorlib]System.Threading.ThreadStart threadStart, class Microsoft.Crm.ThreadControllable threadClass, string name)
0x3886a  pop
0x3886b  ret
```
