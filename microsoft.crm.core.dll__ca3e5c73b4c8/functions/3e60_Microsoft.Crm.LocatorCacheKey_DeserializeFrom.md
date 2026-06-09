# Microsoft.Crm.LocatorCacheKey::DeserializeFrom

- ea: `0x3e60`
- end: `0x3ecf`
- name: `Microsoft.Crm.LocatorCacheKey::DeserializeFrom`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3e20`
- `0x3e30`
- `0x3e50`
- `0x3e60`
- `0x4030`
- `0x4200`
- `0x1c060`

## string_xrefs

- `0x3e91`: `CrmConfigDb:Full:`
- `0x3e99`: `CrmConfigDb:Full:`

## pseudocode

```c

```

## disassembly

```asm
0x3e60  ldarg.0
0x3e61  ldstr    aSerializedkey// "serializedKey"
0x3e66  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x3e6b  newobj   instance void Microsoft.Crm.LocatorCacheKey::.ctor()
0x3e70  stloc.0
0x3e71  ldloc.0
0x3e72  ldarg.0
0x3e73  call     valuetype Microsoft.Crm.LocatorKeyType Microsoft.Crm.LocatorCacheKey::GetKeyType(string key)
0x3e78  callvirt instance void Microsoft.Crm.LocatorCacheKey::set_KeyType(valuetype Microsoft.Crm.LocatorKeyType value)
0x3e7d  ldnull
0x3e7e  stloc.1
0x3e7f  ldloc.0
0x3e80  callvirt instance valuetype Microsoft.Crm.LocatorKeyType Microsoft.Crm.LocatorCacheKey::get_KeyType()
0x3e85  stloc.s  4
0x3e87  ldloc.s  4
0x3e89  ldc.i4.1
0x3e8a  beq.s    loc_3E99
0x3e8c  ldloc.s  4
0x3e8e  ldc.i4.2
0x3e8f  bne.un.s loc_3EA1
0x3e91  ldstr    aCrmconfigdbFul// "CrmConfigDb:Full:"
0x3e96  stloc.1
0x3e97  br.s     loc_3EA3
0x3e99  ldstr    aCrmconfigdbFul// "CrmConfigDb:Full:"
0x3e9e  stloc.1
0x3e9f  br.s     loc_3EA3
0x3ea1  ldloc.0
0x3ea2  ret
0x3ea3  ldarg.0
0x3ea4  ldloc.1
0x3ea5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3eaa  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3eaf  stloc.2
0x3eb0  ldloc.2
0x3eb1  ldc.i4.s 0x3A
0x3eb3  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x3eb8  stloc.3
0x3eb9  ldloc.3
0x3eba  ldc.i4.0
0x3ebb  blt.s    loc_3EC6
0x3ebd  ldloc.2
0x3ebe  ldc.i4.0
0x3ebf  ldloc.3
0x3ec0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x3ec5  stloc.2
0x3ec6  ldloc.0
0x3ec7  ldloc.2
0x3ec8  callvirt instance void Microsoft.Crm.LocatorCacheKey::set_Table(string value)
0x3ecd  ldloc.0
0x3ece  ret
```
