# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::SetServiceExecutableParameters

- ea: `0x1bb0`
- end: `0x1c12`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::SetServiceExecutableParameters`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a40`

## callees

- `0x1bb0`
- `0x1ce0`

## string_xrefs

- `0x1bb5`: `System\CurrentControlSet\Services`
- `0x1bcf`: `ImagePath`
- `0x1be0`: `ImagePath`

## pseudocode

```c

```

## disassembly

```asm
0x1bb0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1bb5  ldstr    aSystemCurrentc// "System\\CurrentControlSet\\Services"
0x1bba  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1bbf  stloc.0
0x1bc0  ldloc.0
0x1bc1  ldarg.0
0x1bc2  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName()
0x1bc7  ldc.i4.1
0x1bc8  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1bcd  stloc.1
0x1bce  ldloc.1
0x1bcf  ldstr    aImagepath// "ImagePath"
0x1bd4  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1bd9  castclass [mscorlib]System.String
0x1bde  stloc.2
0x1bdf  ldloc.1
0x1be0  ldstr    aImagepath// "ImagePath"
0x1be5  ldloc.2
0x1be6  ldstr    asc_CF48// " "
0x1beb  ldarg.0
0x1bec  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName()
0x1bf1  call     string [mscorlib]System.String::Concat(string, string, string)
0x1bf6  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1bfb  leave.s  loc_1C11
0x1bfd  ldloc.1
0x1bfe  brfalse.s loc_1C06
0x1c00  ldloc.1
0x1c01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c06  endfinally
0x1c07  ldloc.0
0x1c08  brfalse.s loc_1C10
0x1c0a  ldloc.0
0x1c0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c10  endfinally
0x1c11  ret
```
