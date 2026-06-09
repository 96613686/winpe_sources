# Microsoft.Crm.SpreadsheetMLMetadata::SetNonImportableColumnIndexes

- ea: `0x241f0`
- end: `0x24255`
- name: `Microsoft.Crm.SpreadsheetMLMetadata::SetNonImportableColumnIndexes`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24180`

## callees

- `0x241f0`

## string_xrefs

- `0x24221`: `each of the values in this comma separated list should be a valid integer`

## pseudocode

```c

```

## disassembly

```asm
0x241f0  ldarg.1
0x241f1  ldstr    asc_6B1E0// ","
0x241f6  call     string[] [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::Split(string, string)
0x241fb  stloc.0
0x241fc  ldc.i4.0
0x241fd  stloc.1
0x241fe  br.s     loc_2423C
0x24200  ldloc.0
0x24201  ldloc.1
0x24202  ldelem.ref
0x24203  stloc.2
0x24204  ldloc.2
0x24205  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2420a  brtrue.s loc_24238
0x2420c  ldloc.2
0x2420d  ldc.i4   0x1FF
0x24212  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24217  ldloca.s 3
0x24219  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x2421e  brtrue.s loc_2422B
0x24220  ldc.i4.0
0x24221  ldstr    aEachOfTheValue// "each of the values in this comma separa"...
0x24226  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2422b  ldarg.0
0x2422c  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<int32> Microsoft.Crm.SpreadsheetMLMetadata::_nonImportableColumnIndexes
0x24231  ldloc.3
0x24232  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<int32>::Add(var<u1>)
0x24237  pop
0x24238  ldloc.1
0x24239  ldc.i4.1
0x2423a  add
0x2423b  stloc.1
0x2423c  ldloc.1
0x2423d  ldloc.0
0x2423e  ldlen
0x2423f  conv.i4
0x24240  blt.s    loc_24200
0x24242  leave.s  loc_24254
0x24244  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24249  ldc.i4   0x8004F601
0x2424e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24253  throw
0x24254  ret
```
