# Microsoft.Crm.Extensibility.ODataV4.Throttling.ConfigParser::ParseThrottlingConfigFromSettings

- ea: `0x2a360`
- end: `0x2a4c2`
- name: `Microsoft.Crm.Extensibility.ODataV4.Throttling.ConfigParser::ParseThrottlingConfigFromSettings`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2b620`
- `0x2b640`

## callees

- `0x2a360`
- `0x2b690`
- `0x2b6b0`
- `0x2b6d0`
- `0x2b6f0`
- `0x2b710`
- `0x2b730`

## pseudocode

```c

```

## disassembly

```asm
0x2a360  ldarg.1
0x2a361  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a366  brtrue   loc_2A4C1
0x2a36b  ldarg.1
0x2a36c  callvirt instance string [mscorlib]System.String::Trim()
0x2a371  starg.s  1
0x2a373  ldarg.1
0x2a374  ldc.i4.1
0x2a375  newarr   [mscorlib]System.Char
0x2a37a  dup
0x2a37b  ldc.i4.0
0x2a37c  ldc.i4.s 0x3B
0x2a37e  stelem.i2
0x2a37f  ldc.i4.1
0x2a380  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x2a385  stloc.0
0x2a386  ldloc.0
0x2a387  ldlen
0x2a388  brfalse  loc_2A4C1
0x2a38d  ldloc.0
0x2a38e  stloc.1
0x2a38f  ldc.i4.0
0x2a390  stloc.2
0x2a391  br       loc_2A4B8
0x2a396  ldloc.1
0x2a397  ldloc.2
0x2a398  ldelem.ref
0x2a399  ldc.i4.1
0x2a39a  newarr   [mscorlib]System.Char
0x2a39f  dup
0x2a3a0  ldc.i4.0
0x2a3a1  ldc.i4.s 0x3D
0x2a3a3  stelem.i2
0x2a3a4  ldc.i4.1
0x2a3a5  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x2a3aa  stloc.3
0x2a3ab  ldloc.3
0x2a3ac  ldlen
0x2a3ad  conv.i4
0x2a3ae  ldc.i4.2
0x2a3af  bne.un   loc_2A49E
0x2a3b4  ldloc.3
0x2a3b5  ldc.i4.0
0x2a3b6  ldelem.ref
0x2a3b7  callvirt instance string [mscorlib]System.String::ToLower()
0x2a3bc  stloc.s  4
0x2a3be  ldloc.3
0x2a3bf  ldc.i4.1
0x2a3c0  ldelem.ref
0x2a3c1  stloc.s  5
0x2a3c3  ldloc.s  4
0x2a3c5  ldstr    aBurstthreshold// "burstthreshold"
0x2a3ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a3cf  brtrue.s loc_2A419
0x2a3d1  ldloc.s  4
0x2a3d3  ldstr    aTimethresholdi// "timethresholdinmins"
0x2a3d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a3dd  brtrue.s loc_2A42B
0x2a3df  ldloc.s  4
0x2a3e1  ldstr    aOverflowcapaci// "overflowcapacitylimit"
0x2a3e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a3eb  brtrue.s loc_2A44A
0x2a3ed  ldloc.s  4
0x2a3ef  ldstr    aPostponecapaci// "postponecapacitylimit"
0x2a3f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a3f9  brtrue.s loc_2A459
0x2a3fb  ldloc.s  4
0x2a3fd  ldstr    aThrowbursterro// "throwbursterror"
0x2a402  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a407  brtrue.s loc_2A468
0x2a409  ldloc.s  4
0x2a40b  ldstr    aThrowtimeerror// "throwtimeerror"
0x2a410  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2a415  brtrue.s loc_2A477
0x2a417  br.s     loc_2A486
0x2a419  ldarg.0
0x2a41a  ldloc.s  5
0x2a41c  call     int64 [mscorlib]System.Int64::Parse(string)
0x2a421  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_BurstThreshold(int64 value)
0x2a426  br       loc_2A4B4
0x2a42b  ldarg.0
0x2a42c  ldloc.s  5
0x2a42e  call     int32 [mscorlib]System.Int32::Parse(string)
0x2a433  conv.r8
0x2a434  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x2a439  stloc.s  6
0x2a43b  ldloca.s 6
0x2a43d  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x2a442  conv.i8
0x2a443  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_TimeThreshold(int64 value)
0x2a448  br.s     loc_2A4B4
0x2a44a  ldarg.0
0x2a44b  ldloc.s  5
0x2a44d  call     float64 [mscorlib]System.Double::Parse(string)
0x2a452  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_ThrottleOverflowCapacityLimit(float64 value)
0x2a457  br.s     loc_2A4B4
0x2a459  ldarg.0
0x2a45a  ldloc.s  5
0x2a45c  call     float64 [mscorlib]System.Double::Parse(string)
0x2a461  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_ThrottlePostponeCapacityLimit(float64 value)
0x2a466  br.s     loc_2A4B4
0x2a468  ldarg.0
0x2a469  ldloc.s  5
0x2a46b  call     bool [mscorlib]System.Boolean::Parse(string)
0x2a470  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_ThrowBurstError(bool value)
0x2a475  br.s     loc_2A4B4
0x2a477  ldarg.0
0x2a478  ldloc.s  5
0x2a47a  call     bool [mscorlib]System.Boolean::Parse(string)
0x2a47f  callvirt instance void Microsoft.Crm.Extensibility.ODataV4.Throttling.ThrottlingConfiguration::set_ThrowTimeError(bool value)
0x2a484  br.s     loc_2A4B4
0x2a486  ldsfld   class [mscorlib]System.Action`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.Extensibility.ODataV4.Throttling.ConfigParser::WriteError
0x2a48b  ldarg.2
0x2a48c  ldstr    aInvalidKeySpec// "Invalid key specified: "
0x2a491  ldarg.1
0x2a492  call     string [mscorlib]System.String::Concat(string, string)
0x2a497  callvirt instance void class [mscorlib]System.Action`2<valuetype [mscorlib]System.Guid, string>::Invoke(var<u1>, !!T0)
0x2a49c  br.s     loc_2A4B4
0x2a49e  ldsfld   class [mscorlib]System.Action`2<valuetype [mscorlib]System.Guid, string> Microsoft.Crm.Extensibility.ODataV4.Throttling.ConfigParser::WriteError
0x2a4a3  ldarg.2
0x2a4a4  ldstr    aInvalidKeyvalu// "Invalid keyvalue pair specified: "
0x2a4a9  ldarg.1
0x2a4aa  call     string [mscorlib]System.String::Concat(string, string)
0x2a4af  callvirt instance void class [mscorlib]System.Action`2<valuetype [mscorlib]System.Guid, string>::Invoke(var<u1>, !!T0)
0x2a4b4  ldloc.2
0x2a4b5  ldc.i4.1
0x2a4b6  add
0x2a4b7  stloc.2
0x2a4b8  ldloc.2
0x2a4b9  ldloc.1
0x2a4ba  ldlen
0x2a4bb  conv.i4
0x2a4bc  blt      loc_2A396
0x2a4c1  ret
```
