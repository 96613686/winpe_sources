# Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::InternalExecute

- ea: `0x2060`
- end: `0x2232`
- name: `Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::InternalExecute`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1cf0`
- `0x1d00`
- `0x1d10`
- `0x2060`

## string_xrefs

- `0x20d2`: `/sim /c:"MSCRMServices/2007/crmservice.asmx" "{0}"`
- `0x2188`: `Findstr.exe did not complete successfully within 1 hour. Please check for references to crmservice.asmx in log files.`
- `0x21c1`: `IIS Logs contain calls to the 2007 web service endpoint`
- `0x21e3`: `IIS logs do not contain calls to the 2007 web service endpoint`
- `0x2221`: `Folder specified for IIS logs does not exist or is not accessible.`

## pseudocode

```c

```

## disassembly

```asm
0x2060  ldarg.0
0x2061  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::_logPath
0x2066  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x206b  brfalse.s loc_2080
0x206d  ldarg.0
0x206e  ldarg.1
0x206f  ldstr    aIisLogsFolderN// "IIS logs folder not provided."
0x2074  ldc.i4.0
0x2075  newarr   [mscorlib]System.Object
0x207a  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x207f  ret
0x2080  ldarg.0
0x2081  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::_logPath
0x2086  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x208b  brfalse  loc_221F
0x2090  ldarg.0
0x2091  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::_logPath
0x2096  ldstr    asc_1C98A// "\\"
0x209b  ldc.i4.5
0x209c  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x20a1  brfalse.s loc_20B6
0x20a3  ldarg.0
0x20a4  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::_logPath
0x20a9  ldstr    aLog// "*.log"
0x20ae  call     string [mscorlib]System.String::Concat(string, string)
0x20b3  stloc.0
0x20b4  br.s     loc_20C7
0x20b6  ldarg.0
0x20b7  ldfld    string Microsoft.Crm.LegacyFeatureCheck.Actions.VerifyIISLogsAction::_logPath
0x20bc  ldstr    aLog_0// "\\*.log"
0x20c1  call     string [mscorlib]System.String::Concat(string, string)
0x20c6  stloc.0
0x20c7  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x20cc  stloc.1
0x20cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20d2  ldstr    aSimCMscrmservi// "/sim /c:\"MSCRMServices/2007/crmservice"...
0x20d7  ldc.i4.1
0x20d8  newarr   [mscorlib]System.Object
0x20dd  dup
0x20de  ldc.i4.0
0x20df  ldloc.0
0x20e0  stelem.ref
0x20e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20e6  stloc.2
0x20e7  ldloc.1
0x20e8  ldstr    aFindstrExe// "findstr.exe"
0x20ed  ldloc.2
0x20ee  newobj   instance void [System]System.Diagnostics.ProcessStartInfo::.ctor(string, string)
0x20f3  callvirt instance void [System]System.Diagnostics.Process::set_StartInfo(class [System]System.Diagnostics.ProcessStartInfo)
0x20f8  ldloc.1
0x20f9  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x20fe  ldc.i4.1
0x20ff  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_CreateNoWindow(bool)
0x2104  ldloc.1
0x2105  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x210a  ldc.i4.0
0x210b  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x2110  ldloc.1
0x2111  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2116  ldc.i4.1
0x2117  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardError(bool)
0x211c  ldloc.1
0x211d  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2122  ldc.i4.1
0x2123  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_RedirectStandardOutput(bool)
0x2128  ldloc.1
0x2129  ldsfld   class [System]System.Diagnostics.DataReceivedEventHandler <>c::<>9__2_0
0x212e  dup
0x212f  brtrue.s loc_2148
0x2131  pop
0x2132  ldsfld   class <>c <>c::<>9
0x2137  ldftn    instance void <>c::<InternalExecute>b__2_0(object p, class [System]System.Diagnostics.DataReceivedEventArgs s)
0x213d  newobj   instance void [System]System.Diagnostics.DataReceivedEventHandler::.ctor(object, native int)
0x2142  dup
0x2143  stsfld   class [System]System.Diagnostics.DataReceivedEventHandler <>c::<>9__2_0
0x2148  callvirt instance void [System]System.Diagnostics.Process::add_OutputDataReceived(class [System]System.Diagnostics.DataReceivedEventHandler)
0x214d  ldarg.0
0x214e  ldarg.1
0x214f  ldstr    aRunningFindstr// "Running Findstr.exe to search IIS logs"
0x2154  ldc.i4.0
0x2155  newarr   [mscorlib]System.Object
0x215a  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x215f  ldloc.1
0x2160  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x2165  pop
0x2166  ldloc.1
0x2167  ldc.r8   1.0
0x2170  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x2175  stloc.s  5
0x2177  ldloca.s 5
0x2179  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x217e  conv.i4
0x217f  callvirt instance bool [System]System.Diagnostics.Process::WaitForExit(int32)
0x2184  brtrue.s loc_219E
0x2186  ldarg.0
0x2187  ldarg.1
0x2188  ldstr    aFindstrExeDidN// "Findstr.exe did not complete successful"...
0x218d  ldc.i4.0
0x218e  newarr   [mscorlib]System.Object
0x2193  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x2198  ldloc.1
0x2199  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x219e  ldloc.1
0x219f  callvirt instance class [mscorlib]System.IO.StreamReader [System]System.Diagnostics.Process::get_StandardOutput()
0x21a4  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x21a9  stloc.3
0x21aa  ldloc.1
0x21ab  callvirt instance class [mscorlib]System.IO.StreamReader [System]System.Diagnostics.Process::get_StandardError()
0x21b0  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x21b5  stloc.s  4
0x21b7  ldloc.3
0x21b8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x21bd  brtrue.s loc_21E1
0x21bf  ldarg.0
0x21c0  ldarg.1
0x21c1  ldstr    aIisLogsContain// "IIS Logs contain calls to the 2007 web "...
0x21c6  ldc.i4.0
0x21c7  newarr   [mscorlib]System.Object
0x21cc  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x21d1  ldarg.0
0x21d2  ldarg.1
0x21d3  ldloc.3
0x21d4  ldc.i4.0
0x21d5  newarr   [mscorlib]System.Object
0x21da  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogWarning(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x21df  br.s     loc_21F3
0x21e1  ldarg.0
0x21e2  ldarg.1
0x21e3  ldstr    aIisLogsDoNotCo// "IIS logs do not contain calls to the 20"...
0x21e8  ldc.i4.0
0x21e9  newarr   [mscorlib]System.Object
0x21ee  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogInformation(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x21f3  ldloc.s  4
0x21f5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x21fa  brtrue.s loc_2213
0x21fc  ldarg.0
0x21fd  ldarg.1
0x21fe  ldstr    aErrorWhileRunn// "Error while running findstr.exe: {0}"
0x2203  ldc.i4.1
0x2204  newarr   [mscorlib]System.Object
0x2209  dup
0x220a  ldc.i4.0
0x220b  ldloc.s  4
0x220d  stelem.ref
0x220e  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x2213  leave.s  loc_2231
0x2215  ldloc.1
0x2216  brfalse.s loc_221E
0x2218  ldloc.1
0x2219  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x221e  endfinally
0x221f  ldarg.0
0x2220  ldarg.1
0x2221  ldstr    aFolderSpecifie// "Folder specified for IIS logs does not "...
0x2226  ldc.i4.0
0x2227  newarr   [mscorlib]System.Object
0x222c  call     instance void Microsoft.Crm.LegacyFeatureCheck.Common.DeploymentVerificationAction::LogError(class Microsoft.Crm.LegacyFeatureCheck.CrmDeployment deployment, string messageFormat, object[] values)
0x2231  ret
```
