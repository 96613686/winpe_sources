# Microsoft.Crm.CrmKey::GetActiveKey_5

- ea: `0x37260`
- end: `0x373d1`
- name: `Microsoft.Crm.CrmKey::GetActiveKey_5`
- size: `369`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x37240`
- `0x37250`

## callees

- `0x17d70`
- `0x17d90`
- `0x1f510`
- `0x37260`
- `0x37400`
- `0x37590`
- `0x375d0`
- `0x376c0`
- `0x396f0`
- `0x39810`
- `0x398d0`
- `0x39990`
- `0x39a90`
- `0x39ab0`

## string_xrefs

- `0x37291`: `Active Key returned has null Key Value -- KeyType: {0}, KeyLength: {1}, KeyTimeToLive: {2}, \n					KeyGenerationInterval: {3}, scaleGroupId: {4}, useCachedValue: {5}, ActiveKeyId: {6}`
- `0x37389`: `CrmKey.GetActiveKey: Active Key is expired. KeyType: {0}, Key: {1}, KeySetting: {2}, scaleGroupId: {3}, useCachedValue: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x37260  ldnull
0x37261  stloc.0
0x37262  ldnull
0x37263  stloc.1
0x37264  ldarg.0
0x37265  ldarg.2
0x37266  ldarg.1
0x37267  ldarg.s  4
0x37269  call     class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeySetting::LoadKeySetting(valuetype Microsoft.Crm.CrmKeyType keyType, bool useCachedValues, valuetype [mscorlib]System.Guid scaleGroupId, valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x3726e  stloc.0
0x3726f  ldloc.0
0x37270  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x37275  ldarg.2
0x37276  ldarg.s  4
0x37278  call     class Microsoft.Crm.CrmKey Microsoft.Crm.CrmKey::LoadKey(valuetype [mscorlib]System.Guid keyId, bool useCachedValues, valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x3727d  stloc.1
0x3727e  ldloc.1
0x3727f  brfalse.s loc_372F4
0x37281  ldloc.1
0x37282  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.Crm.CrmKey::get_KeyValue()
0x37287  brtrue.s loc_372F4
0x37289  ldnull
0x3728a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3728f  ldc.i4.s 0x14
0x37291  ldstr    aActiveKeyRetur// "Active Key returned has null Key Value "...
0x37296  ldc.i4.7
0x37297  newarr   [mscorlib]System.Object
0x3729c  dup
0x3729d  ldc.i4.0
0x3729e  ldarg.0
0x3729f  box      Microsoft.Crm.CrmKeyType
0x372a4  stelem.ref
0x372a5  dup
0x372a6  ldc.i4.1
0x372a7  ldloc.0
0x372a8  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyLength()
0x372ad  box      [mscorlib]System.Int32
0x372b2  stelem.ref
0x372b3  dup
0x372b4  ldc.i4.2
0x372b5  ldloc.0
0x372b6  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyTimeToLive()
0x372bb  box      [mscorlib]System.Int32
0x372c0  stelem.ref
0x372c1  dup
0x372c2  ldc.i4.3
0x372c3  ldloc.0
0x372c4  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyGenerationInterval()
0x372c9  box      [mscorlib]System.Int32
0x372ce  stelem.ref
0x372cf  dup
0x372d0  ldc.i4.4
0x372d1  ldarg.1
0x372d2  box      [mscorlib]System.Guid
0x372d7  stelem.ref
0x372d8  dup
0x372d9  ldc.i4.5
0x372da  ldarg.2
0x372db  box      [mscorlib]System.Boolean
0x372e0  stelem.ref
0x372e1  dup
0x372e2  ldc.i4.6
0x372e3  ldloc.0
0x372e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x372e9  box      [mscorlib]System.Guid
0x372ee  stelem.ref
0x372ef  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x372f4  leave.s  loc_37339
0x372f6  stloc.2
0x372f7  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
0x372fc  stloc.3
0x372fd  ldloc.3
0x372fe  ldstr    aMscrmkeygenera// "MSCRMKeyGenerator"
0x37303  ldc.i4.1
0x37304  ldc.i4   0xC0004A0E
0x37309  conv.u8
0x3730a  ldc.i4.3
0x3730b  newarr   [mscorlib]System.Object
0x37310  dup
0x37311  ldc.i4.0
0x37312  ldarg.0
0x37313  box      Microsoft.Crm.CrmKeyType
0x37318  stelem.ref
0x37319  dup
0x3731a  ldc.i4.1
0x3731b  ldarg.1
0x3731c  box      [mscorlib]System.Guid
0x37321  stelem.ref
0x37322  dup
0x37323  ldc.i4.2
0x37324  ldloc.2
0x37325  stelem.ref
0x37326  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(string eventSourceName, valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x3732b  leave.s  loc_37337
0x3732d  ldloc.3
0x3732e  brfalse.s loc_37336
0x37330  ldloc.3
0x37331  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37336  endfinally
0x37337  rethrow
0x37339  ldarg.3
0x3733a  ldloc.0
0x3733b  callvirt instance string Microsoft.Crm.CrmKeySetting::get_Algorithm()
0x37340  stind.ref
0x37341  ldloc.1
0x37342  callvirt instance bool Microsoft.Crm.CrmKey::get_Expired()
0x37347  brfalse  loc_373CF
0x3734c  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
0x37351  stloc.s  4
0x37353  ldloc.s  4
0x37355  ldstr    aMscrmkeygenera// "MSCRMKeyGenerator"
0x3735a  ldc.i4.1
0x3735b  ldc.i4   0x80004A05
0x37360  conv.u8
0x37361  ldc.i4.3
0x37362  newarr   [mscorlib]System.Object
0x37367  dup
0x37368  ldc.i4.0
0x37369  ldloc.1
0x3736a  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKey::get_KeyType()
0x3736f  box      Microsoft.Crm.CrmKeyType
0x37374  stelem.ref
0x37375  dup
0x37376  ldc.i4.1
0x37377  ldloc.1
0x37378  stelem.ref
0x37379  dup
0x3737a  ldc.i4.2
0x3737b  ldloc.0
0x3737c  stelem.ref
0x3737d  callvirt instance void Microsoft.Crm.CrmEventLog::WriteEntry(string eventSourceName, valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x37382  ldnull
0x37383  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x37388  ldc.i4.6
0x37389  ldstr    aCrmkeyGetactiv// "CrmKey.GetActiveKey: Active Key is expi"...
0x3738e  ldc.i4.5
0x3738f  newarr   [mscorlib]System.Object
0x37394  dup
0x37395  ldc.i4.0
0x37396  ldloc.1
0x37397  callvirt instance valuetype Microsoft.Crm.CrmKeyType Microsoft.Crm.CrmKey::get_KeyType()
0x3739c  box      Microsoft.Crm.CrmKeyType
0x373a1  stelem.ref
0x373a2  dup
0x373a3  ldc.i4.1
0x373a4  ldloc.1
0x373a5  stelem.ref
0x373a6  dup
0x373a7  ldc.i4.2
0x373a8  ldloc.0
0x373a9  stelem.ref
0x373aa  dup
0x373ab  ldc.i4.3
0x373ac  ldarg.1
0x373ad  box      [mscorlib]System.Guid
0x373b2  stelem.ref
0x373b3  dup
0x373b4  ldc.i4.4
0x373b5  ldarg.2
0x373b6  box      [mscorlib]System.Boolean
0x373bb  stelem.ref
0x373bc  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x373c1  leave.s  loc_373CF
0x373c3  ldloc.s  4
0x373c5  brfalse.s loc_373CE
0x373c7  ldloc.s  4
0x373c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x373ce  endfinally
0x373cf  ldloc.1
0x373d0  ret
```
