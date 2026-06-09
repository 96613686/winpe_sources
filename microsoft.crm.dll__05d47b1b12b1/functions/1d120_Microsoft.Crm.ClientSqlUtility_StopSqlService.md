# Microsoft.Crm.ClientSqlUtility::StopSqlService

- ea: `0x1d120`
- end: `0x1d1c0`
- name: `Microsoft.Crm.ClientSqlUtility::StopSqlService`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cfd0`
- `0x1d120`

## string_xrefs

- `0x1d13e`: `SYSTEM\CurrentControlSet\Services\MSSQL$CRM`

## pseudocode

```c

```

## disassembly

```asm
0x1d120  ldstr    aOfflinedonotst// "OfflineDoNotStopMSDE"
0x1d125  ldc.i4.0
0x1d126  box      [mscorlib]System.Int32
0x1d12b  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1d130  unbox.any [mscorlib]System.Int32
0x1d135  stloc.0
0x1d136  ldloc.0
0x1d137  brtrue.s loc_1D19C
0x1d139  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1d13e  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services\\MS"...
0x1d143  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1d148  stloc.1
0x1d149  ldloc.1
0x1d14a  brtrue.s loc_1D14E
0x1d14c  leave.s  loc_1D1BF
0x1d14e  ldc.i4.3
0x1d14f  ldloc.1
0x1d150  ldstr    aStart// "Start"
0x1d155  ldc.i4.0
0x1d156  box      [mscorlib]System.Int32
0x1d15b  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x1d160  callvirt instance string [mscorlib]System.Object::ToString()
0x1d165  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d16a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1d16f  bne.un.s loc_1D190
0x1d171  ldstr    aGlobalCrmsqlst// "Global\\CrmSqlStartupSvc:SqlShutdownEve"...
0x1d176  ldc.i4.2
0x1d177  call     class [mscorlib]System.Threading.EventWaitHandle [mscorlib]System.Threading.EventWaitHandle::OpenExisting(string, valuetype [mscorlib]System.Security.AccessControl.EventWaitHandleRights)
0x1d17c  stloc.2
0x1d17d  ldloc.2
0x1d17e  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x1d183  pop
0x1d184  leave.s  loc_1D19C
0x1d186  ldloc.2
0x1d187  brfalse.s loc_1D18F
0x1d189  ldloc.2
0x1d18a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d18f  endfinally
0x1d190  leave.s  loc_1D19C
0x1d192  ldloc.1
0x1d193  brfalse.s loc_1D19B
0x1d195  ldloc.1
0x1d196  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d19b  endfinally
0x1d19c  nop
0x1d19d  call     void [System.Data]System.Data.SqlClient.SqlConnection::ClearAllPools()
0x1d1a2  leave.s  loc_1D1BF
0x1d1a4  pop
0x1d1a5  leave.s  loc_1D1BF
0x1d1a7  ldsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d1ac  brfalse.s loc_1D1BE
0x1d1ae  ldsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d1b3  callvirt instance void Microsoft.Crm.ServiceLock::Unlock()
0x1d1b8  ldnull
0x1d1b9  stsfld   class Microsoft.Crm.ServiceLock Microsoft.Crm.ClientSqlUtility::_sqlLock
0x1d1be  endfinally
0x1d1bf  ret
```
