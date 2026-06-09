# Microsoft.Crm.CrmTraceSettings::ToStringInternal

- ea: `0x223f0`
- end: `0x2254c`
- name: `Microsoft.Crm.CrmTraceSettings::ToStringInternal`
- size: `348`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x21e50`
- `0x223e0`

## callees

- `0x20b40`
- `0x20b60`
- `0x20b80`
- `0x20ba0`
- `0x20bc0`
- `0x20be0`
- `0x20c00`
- `0x20c20`
- `0x20c40`
- `0x20c60`
- `0x20cc0`

## string_xrefs

- `0x22446`: ` ,TraceDirectory:`
- `0x22505`: ` ,RegistryRefreshTraceInt:`

## pseudocode

```c

```

## disassembly

```asm
0x223f0  ldc.i4   0x200
0x223f5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x223fa  dup
0x223fb  ldstr    aFilename// "{Filename: "
0x22400  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22405  pop
0x22406  dup
0x22407  ldarg.0
0x22408  call     instance string Microsoft.Crm.CrmTraceSettings::get_FileName()
0x2240d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22412  pop
0x22413  dup
0x22414  ldstr    aFilecountsuffi// " ,FileCountSuffix:"
0x22419  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2241e  pop
0x2241f  dup
0x22420  ldarg.0
0x22421  call     instance int32 Microsoft.Crm.CrmTraceSettings::get_FileCountSuffix()
0x22426  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x2242b  pop
0x2242c  dup
0x2242d  ldstr    aTracefilesize_0// " ,TraceFileSize:"
0x22432  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22437  pop
0x22438  dup
0x22439  ldarg.0
0x2243a  call     instance int32 Microsoft.Crm.CrmTraceSettings::get_TraceFileSize()
0x2243f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x22444  pop
0x22445  dup
0x22446  ldstr    aTracedirectory_0// " ,TraceDirectory:"
0x2244b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22450  pop
0x22451  dup
0x22452  ldarg.0
0x22453  call     instance string Microsoft.Crm.CrmTraceSettings::get_TraceDirectory()
0x22458  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2245d  pop
0x2245e  dup
0x2245f  ldstr    aTracingcallsta// " ,TracingCallStack:"
0x22464  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22469  pop
0x2246a  dup
0x2246b  ldarg.0
0x2246c  call     instance valuetype TraceBool Microsoft.Crm.CrmTraceSettings::get_TracingCallStack()
0x22471  stloc.0
0x22472  ldloca.s 0
0x22474  constrained. TraceBool
0x2247a  callvirt instance string [mscorlib]System.Object::ToString()
0x2247f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22484  pop
0x22485  dup
0x22486  ldstr    aIstracingoff// " ,IsTracingOff:"
0x2248b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22490  pop
0x22491  dup
0x22492  ldarg.0
0x22493  call     instance valuetype TraceBool Microsoft.Crm.CrmTraceSettings::get_IsTracingOff()
0x22498  stloc.0
0x22499  ldloca.s 0
0x2249b  constrained. TraceBool
0x224a1  callvirt instance string [mscorlib]System.Object::ToString()
0x224a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x224ab  pop
0x224ac  dup
0x224ad  ldstr    aLoadstate// " ,LoadState:"
0x224b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x224b7  pop
0x224b8  dup
0x224b9  ldarg.0
0x224ba  call     instance valuetype LoadStatus Microsoft.Crm.CrmTraceSettings::get_LoadState()
0x224bf  stloc.1
0x224c0  ldloca.s 1
0x224c2  constrained. LoadStatus
0x224c8  callvirt instance string [mscorlib]System.Object::ToString()
0x224cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x224d2  pop
0x224d3  dup
0x224d4  ldstr    aRefreshtracein// " ,RefreshTraceInt:"
0x224d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x224de  pop
0x224df  dup
0x224e0  ldarg.0
0x224e1  call     instance int32 Microsoft.Crm.CrmTraceSettings::get_RefreshTraceInt()
0x224e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x224eb  pop
0x224ec  dup
0x224ed  ldstr    aSitewiderefres// " ,SiteWideRefreshTraceInt:"
0x224f2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x224f7  pop
0x224f8  dup
0x224f9  call     int32 Microsoft.Crm.CrmTraceSettings::get_SiteWideRefreshTraceInt()
0x224fe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x22503  pop
0x22504  dup
0x22505  ldstr    aRegistryrefres// " ,RegistryRefreshTraceInt:"
0x2250a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2250f  pop
0x22510  dup
0x22511  call     int32 Microsoft.Crm.CrmTraceSettings::get_RegistryRefreshTraceInt()
0x22516  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x2251b  pop
0x2251c  dup
0x2251d  ldstr    aPrecedence// " ,Precedence:"
0x22522  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22527  pop
0x22528  dup
0x22529  ldarg.0
0x2252a  call     instance valuetype Microsoft.Crm.SettingsPrecedence Microsoft.Crm.CrmTraceSettings::get_TraceSettingsPrecedence()
0x2252f  box      Microsoft.Crm.SettingsPrecedence
0x22534  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x22539  pop
0x2253a  dup
0x2253b  ldstr    asc_805F6// "}"
0x22540  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22545  pop
0x22546  callvirt instance string [mscorlib]System.Object::ToString()
0x2254b  ret
```
