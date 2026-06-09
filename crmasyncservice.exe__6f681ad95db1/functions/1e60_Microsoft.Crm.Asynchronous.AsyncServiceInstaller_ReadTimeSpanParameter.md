# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::ReadTimeSpanParameter

- ea: `0x1e60`
- end: `0x1e90`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::ReadTimeSpanParameter`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ca0`
- `0x1cc0`

## callees

- `0x1e60`

## pseudocode

```c

```

## disassembly

```asm
0x1e60  ldarg.2
0x1e61  stloc.0
0x1e62  ldarg.0
0x1e63  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1e68  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1e6d  ldarg.1
0x1e6e  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1e73  stloc.1
0x1e74  ldloc.1
0x1e75  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e7a  brtrue.s loc_1E8E
0x1e7c  ldloc.1
0x1e7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e82  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1e87  conv.r8
0x1e88  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1e8d  stloc.0
0x1e8e  ldloc.0
0x1e8f  ret
```
