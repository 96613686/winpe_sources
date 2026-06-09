# Microsoft.Crm.CrmLive.Services.CrmLiveContext::ToString

- ea: `0xbb30`
- end: `0xbbb8`
- name: `Microsoft.Crm.CrmLive.Services.CrmLiveContext::ToString`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xba80`
- `0xba90`
- `0xbaa0`
- `0xbab0`
- `0xbb30`

## string_xrefs

- `0xbb4a`: `<no config connection>`
- `0xbb89`: `CrmLiveContext {0} ({1} -> {2})\n			CreatedBy: {3}\n			Config connection: {4}`

## pseudocode

```c

```

## disassembly

```asm
0xbb30  ldarg.0
0xbb31  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmLive.ConfigDB.IConfigDBSproc Microsoft.Crm.CrmLive.Services.CrmLiveContext::_configDBSproc
0xbb36  brfalse.s loc_BB4A
0xbb38  ldarg.0
0xbb39  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmLive.ConfigDB.IConfigDBSproc Microsoft.Crm.CrmLive.Services.CrmLiveContext::_configDBSproc
0xbb3e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.CrmLive.ConfigDB.IConfigDBSproc::get_Connection()
0xbb43  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0xbb48  br.s     loc_BB4F
0xbb4a  ldstr    aNoConfigConnec// "<no config connection>"
0xbb4f  stloc.0
0xbb50  ldarg.0
0xbb51  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.CrmLive.Services.CrmLiveContext::get_Created()
0xbb56  stloc.3
0xbb57  ldloca.s 3
0xbb59  ldstr    aO// "o"
0xbb5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb63  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xbb68  stloc.1
0xbb69  ldarg.0
0xbb6a  call     instance class [System]System.Diagnostics.Stopwatch Microsoft.Crm.CrmLive.Services.CrmLiveContext::get_Stopwatch()
0xbb6f  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xbb74  stloc.s  4
0xbb76  ldloca.s 4
0xbb78  constrained. [mscorlib]System.TimeSpan
0xbb7e  callvirt instance string [mscorlib]System.Object::ToString()
0xbb83  stloc.2
0xbb84  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb89  ldstr    aCrmlivecontext// "CrmLiveContext {0} ({1} -> {2})\r\n\t\t"...
0xbb8e  ldc.i4.5
0xbb8f  newarr   [mscorlib]System.Object
0xbb94  dup
0xbb95  ldc.i4.0
0xbb96  ldarg.0
0xbb97  call     instance string Microsoft.Crm.CrmLive.Services.CrmLiveContext::get_Name()
0xbb9c  stelem.ref
0xbb9d  dup
0xbb9e  ldc.i4.1
0xbb9f  ldloc.1
0xbba0  stelem.ref
0xbba1  dup
0xbba2  ldc.i4.2
0xbba3  ldloc.2
0xbba4  stelem.ref
0xbba5  dup
0xbba6  ldc.i4.3
0xbba7  ldarg.0
0xbba8  call     instance string Microsoft.Crm.CrmLive.Services.CrmLiveContext::get_CreatedBy()
0xbbad  stelem.ref
0xbbae  dup
0xbbaf  ldc.i4.4
0xbbb0  ldloc.0
0xbbb1  stelem.ref
0xbbb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbbb7  ret
```
