# Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::RetrieveServiceDisplayName

- ea: `0xbfc0`
- end: `0xc032`
- name: `Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::RetrieveServiceDisplayName`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbdf0`

## callees

- `0xbfc0`

## string_xrefs

- `0xbfdf`: `Could not retrieve service information for {0}: {1}`
- `0xc002`: `Could not retrieve service information for {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xbfc0  ldnull
0xbfc1  stloc.0
0xbfc2  ldarg.1
0xbfc3  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0xbfc8  stloc.1
0xbfc9  ldloc.1
0xbfca  callvirt instance string [System.ServiceProcess]System.ServiceProcess.ServiceController::get_DisplayName()
0xbfcf  stloc.0
0xbfd0  leave.s  loc_BFDC
0xbfd2  ldloc.1
0xbfd3  brfalse.s loc_BFDB
0xbfd5  ldloc.1
0xbfd6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbfdb  endfinally
0xbfdc  leave.s  loc_C024
0xbfde  stloc.2
0xbfdf  ldstr    aCouldNotRetrie// "Could not retrieve service information "...
0xbfe4  ldc.i4.2
0xbfe5  newarr   [mscorlib]System.Object
0xbfea  dup
0xbfeb  ldc.i4.0
0xbfec  ldarg.1
0xbfed  stelem.ref
0xbfee  dup
0xbfef  ldc.i4.1
0xbff0  ldloc.2
0xbff1  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbff6  stelem.ref
0xbff7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xbffc  ldnull
0xbffd  stloc.3
0xbffe  leave.s  loc_C030
0xc000  stloc.s  4
0xc002  ldstr    aCouldNotRetrie// "Could not retrieve service information "...
0xc007  ldc.i4.2
0xc008  newarr   [mscorlib]System.Object
0xc00d  dup
0xc00e  ldc.i4.0
0xc00f  ldarg.1
0xc010  stelem.ref
0xc011  dup
0xc012  ldc.i4.1
0xc013  ldloc.s  4
0xc015  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc01a  stelem.ref
0xc01b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xc020  ldnull
0xc021  stloc.3
0xc022  leave.s  loc_C030
0xc024  ldloc.0
0xc025  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc02a  brfalse.s loc_C02E
0xc02c  ldarg.1
0xc02d  stloc.0
0xc02e  ldloc.0
0xc02f  ret
0xc030  ldloc.3
0xc031  ret
```
