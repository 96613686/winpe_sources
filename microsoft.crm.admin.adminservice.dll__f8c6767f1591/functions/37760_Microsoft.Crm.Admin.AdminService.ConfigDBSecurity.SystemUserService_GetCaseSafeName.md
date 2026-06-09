# Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName

- ea: `0x37760`
- end: `0x37848`
- name: `Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName`
- size: `232`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x374c0`
- `0x381b0`
- `0x38280`
- `0x383f0`
- `0x38860`

## callees

- `0x37760`
- `0x37850`

## string_xrefs

- `0x3776d`: `Normalizing non-case sensitive AD credentials for use on a case sensitive SQL installation. Account name: {0}`
- `0x377e6`: `Error while normalizing non-case sensitive AD credentials for use on a case sensitive SQL installation. Account name: {0}. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x37760  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x37765  stloc.0
0x37766  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3776b  ldc.i4.s 0x39
0x3776d  ldstr    aNormalizingNon// "Normalizing non-case sensitive AD crede"...
0x37772  ldc.i4.1
0x37773  newarr   [mscorlib]System.Object
0x37778  dup
0x37779  ldc.i4.0
0x3777a  ldarg.1
0x3777b  stelem.ref
0x3777c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37781  ldarg.1
0x37782  ldc.i4.1
0x37783  newarr   [mscorlib]System.Char
0x37788  dup
0x37789  ldc.i4.0
0x3778a  ldc.i4.s 0x5C
0x3778c  stelem.i2
0x3778d  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x37792  stloc.1
0x37793  ldloc.1
0x37794  ldlen
0x37795  conv.i4
0x37796  ldc.i4.2
0x37797  bne.un.s loc_377AB
0x37799  ldarg.0
0x3779a  ldloc.1
0x3779b  ldc.i4.0
0x3779c  ldelem.ref
0x3779d  ldloc.1
0x3779e  ldc.i4.1
0x3779f  ldelem.ref
0x377a0  call     instance string Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::GetCaseSafeName(string domain, string accountName)
0x377a5  stloc.2
0x377a6  leave    loc_37846
0x377ab  ldarg.1
0x377ac  newobj   instance void [System]System.Net.Mail.MailAddress::.ctor(string)
0x377b1  stloc.3
0x377b2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x377b7  ldc.i4.s 0x39
0x377b9  ldstr    aTheAccountName// "The account name is in email format. Th"...
0x377be  ldc.i4.1
0x377bf  newarr   [mscorlib]System.Object
0x377c4  dup
0x377c5  ldc.i4.0
0x377c6  ldloc.3
0x377c7  callvirt instance string [System]System.Net.Mail.MailAddress::get_Address()
0x377cc  stelem.ref
0x377cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x377d2  ldloc.3
0x377d3  callvirt instance string [System]System.Net.Mail.MailAddress::get_Address()
0x377d8  stloc.2
0x377d9  leave.s  loc_37846
0x377db  stloc.s  4
0x377dd  ldloc.s  4
0x377df  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x377e4  ldc.i4.s 0x39
0x377e6  ldstr    aErrorWhileNorm// "Error while normalizing non-case sensit"...
0x377eb  ldc.i4.2
0x377ec  newarr   [mscorlib]System.Object
0x377f1  dup
0x377f2  ldc.i4.0
0x377f3  ldarg.1
0x377f4  stelem.ref
0x377f5  dup
0x377f6  ldc.i4.1
0x377f7  ldloc.s  4
0x377f9  stelem.ref
0x377fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x377ff  rethrow
0x37801  ldloc.0
0x37802  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x37807  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3780c  ldc.i4.s 0x39
0x3780e  ldstr    aExecutionTime// "Execution time: "
0x37813  ldloc.0
0x37814  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x37819  stloc.s  5
0x3781b  ldloca.s 5
0x3781d  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x37822  stloc.s  6
0x37824  ldloca.s 6
0x37826  ldstr    a000// "0.00"
0x3782b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37830  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x37835  call     string [mscorlib]System.String::Concat(string, string)
0x3783a  ldc.i4.0
0x3783b  newarr   [mscorlib]System.Object
0x37840  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37845  endfinally
0x37846  ldloc.2
0x37847  ret
```
