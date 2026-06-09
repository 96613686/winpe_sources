# Microsoft.Crm.SqmSettings::GetDefaultSettings_0

- ea: `0x16640`
- end: `0x1672f`
- name: `Microsoft.Crm.SqmSettings::GetDefaultSettings_0`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x165d0`

## callees

- `0x16640`
- `0x16730`
- `0x167f0`

## string_xrefs

- `0x166e4`: `http://sqm.microsoft.com/sqm/mbs/sqmserver.dll`

## pseudocode

```c

```

## disassembly

```asm
0x16640  ldarg.1
0x16641  brtrue.s loc_16649
0x16643  call     class Microsoft.Crm.ISqmSettings Microsoft.Crm.SqmSettings::GetDisabledSettings()
0x16648  ret
0x16649  ldstr    aSqmenabled// "SQMEnabled"
0x1664e  ldc.i4.1
0x1664f  box      [mscorlib]System.Int32
0x16654  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x16659  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1665e  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x16663  brtrue.s loc_1666B
0x16665  call     class Microsoft.Crm.ISqmSettings Microsoft.Crm.SqmSettings::GetDisabledSettings()
0x1666a  ret
0x1666b  nop
0x1666c  ldstr    aSqmqueuelocati// "SQMQueueLocation"
0x16671  ldsfld   string [mscorlib]System.String::Empty
0x16676  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1667b  castclass [mscorlib]System.String
0x16680  stloc.0
0x16681  ldarg.3
0x16682  ldc.i4.0
0x16683  bgt.s    loc_16689
0x16685  ldc.i4.s 0x1E
0x16687  br.s     loc_1668A
0x16689  ldarg.3
0x1668a  stloc.1
0x1668b  ldstr    aSqmmaxqueuesiz// "SQMMaxQueueSize"
0x16690  ldloc.1
0x16691  box      [mscorlib]System.Int32
0x16696  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1669b  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x166a0  stloc.1
0x166a1  ldarg.2
0x166a2  ldc.i4.0
0x166a3  bgt.s    loc_166BF
0x166a5  ldc.r8   24.0
0x166ae  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x166b3  stloc.s  5
0x166b5  ldloca.s 5
0x166b7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x166bc  conv.i4
0x166bd  br.s     loc_166C0
0x166bf  ldarg.2
0x166c0  stloc.2
0x166c1  ldstr    aSqminterval// "SQMInterval"
0x166c6  ldloc.2
0x166c7  box      [mscorlib]System.Int32
0x166cc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x166d1  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x166d6  stloc.2
0x166d7  ldarg.s  5
0x166d9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x166de  brtrue.s loc_166E4
0x166e0  ldarg.s  5
0x166e2  br.s     loc_166E9
0x166e4  ldstr    aHttpSqmMicroso// "http://sqm.microsoft.com/sqm/mbs/sqmser"...
0x166e9  stloc.3
0x166ea  ldstr    aSqmuploadurl// "SQMUploadUrl"
0x166ef  ldloc.3
0x166f0  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x166f5  castclass [mscorlib]System.String
0x166fa  stloc.3
0x166fb  ldarg.s  4
0x166fd  ldc.i4.0
0x166fe  bgt.s    loc_16707
0x16700  ldc.i4   0x1E000
0x16705  br.s     loc_16709
0x16707  ldarg.s  4
0x16709  stloc.s  4
0x1670b  ldarg.1
0x1670c  ldloc.0
0x1670d  ldarg.0
0x1670e  ldloc.1
0x1670f  ldloc.s  4
0x16711  ldloc.2
0x16712  conv.r8
0x16713  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x16718  ldloc.3
0x16719  newobj   instance void Microsoft.Crm.SqmSettings::.ctor(bool isEnabled, string queueLocation, string fileNamePatternPrefix, int32 maxQueueSize, int32 maxSessionSize, valuetype [mscorlib]System.TimeSpan sessionInterval, string uploadUrl)
0x1671e  stloc.s  6
0x16720  leave.s  loc_1672C
0x16722  pop
0x16723  call     class Microsoft.Crm.ISqmSettings Microsoft.Crm.SqmSettings::GetDisabledSettings()
0x16728  stloc.s  6
0x1672a  leave.s  loc_1672C
0x1672c  ldloc.s  6
0x1672e  ret
```
