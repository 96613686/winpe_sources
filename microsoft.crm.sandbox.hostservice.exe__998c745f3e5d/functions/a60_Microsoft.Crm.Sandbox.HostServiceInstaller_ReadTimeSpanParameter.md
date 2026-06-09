# Microsoft.Crm.Sandbox.HostServiceInstaller::ReadTimeSpanParameter

- ea: `0xa60`
- end: `0xa90`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::ReadTimeSpanParameter`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x990`
- `0x9b0`

## callees

- `0xa60`

## pseudocode

```c

```

## disassembly

```asm
0xa60  ldarg.2
0xa61  stloc.0
0xa62  ldarg.0
0xa63  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0xa68  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0xa6d  ldarg.1
0xa6e  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0xa73  stloc.1
0xa74  ldloc.1
0xa75  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa7a  brtrue.s loc_A8E
0xa7c  ldloc.1
0xa7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa82  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xa87  conv.r8
0xa88  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0xa8d  stloc.0
0xa8e  ldloc.0
0xa8f  ret
```
