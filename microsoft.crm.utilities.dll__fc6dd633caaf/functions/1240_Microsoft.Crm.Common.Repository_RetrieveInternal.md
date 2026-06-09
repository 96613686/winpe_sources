# Microsoft.Crm.Common.Repository::RetrieveInternal

- ea: `0x1240`
- end: `0x12be`
- name: `Microsoft.Crm.Common.Repository::RetrieveInternal`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0xb00`
- `0xb50`
- `0xb60`
- `0x1240`
- `0x1e10`
- `0x1e30`
- `0x1e50`

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.0
0x1241  call     T0x2B000004
0x1246  stloc.0
0x1247  ldnull
0x1248  stloc.1
0x1249  ldloc.0
0x124a  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0x124f  brfalse.s loc_127A
0x1251  ldarg.1
0x1252  call     T0x2B00000B
0x1257  stloc.1
0x1258  ldarg.2
0x1259  brfalse.s loc_127A
0x125b  ldloc.0
0x125c  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0x1261  ldloc.1
0x1262  callvirt instance object Microsoft.Crm.Common.ICacheProvider::GetItem(string key)
0x1267  stloc.s  4
0x1269  ldloc.s  4
0x126b  brfalse.s loc_127A
0x126d  ldloc.s  4
0x126f  castclass mvar<u1>[]
0x1274  call     T0x2B00000C
0x1279  ret
0x127a  ldloc.0
0x127b  callvirt instance class Microsoft.Crm.Common.IDataProvider TypeInformation::get_DataProvider()
0x1280  ldarg.1
0x1281  callvirt T0x2B00000D
0x1286  stloc.2
0x1287  ldloc.2
0x1288  brtrue.s loc_1290
0x128a  call     T0x2B00000E
0x128f  stloc.2
0x1290  ldloc.2
0x1291  call     T0x2B00000F
0x1296  stloc.3
0x1297  ldloc.0
0x1298  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0x129d  brfalse.s loc_12B7
0x129f  ldloc.0
0x12a0  callvirt instance class Microsoft.Crm.Common.ICacheProvider TypeInformation::get_CacheProvider()
0x12a5  ldloc.1
0x12a6  ldloc.3
0x12a7  ldloc.0
0x12a8  callvirt instance class Microsoft.Crm.Common.CachePolicy TypeInformation::get_CachePolicy()
0x12ad  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Common.CachePolicy::get_AbsoluteExpiration()
0x12b2  callvirt instance void Microsoft.Crm.Common.ICacheProvider::SetItem(string key, object data, valuetype [mscorlib]System.TimeSpan cacheTime)
0x12b7  ldloc.3
0x12b8  call     T0x2B00000C
0x12bd  ret
```
