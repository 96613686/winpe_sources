# Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::ServicesToStopPage_PageActivated

- ea: `0xbdf0`
- end: `0xbf7e`
- name: `Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::ServicesToStopPage_PageActivated`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xff0`
- `0xbd90`
- `0xbdf0`
- `0xbfc0`
- `0xfbc0`
- `0x10ff0`

## string_xrefs

- `0xbe00`: `ServiceStopNotificationList should always be non-null.`
- `0xbe10`: `ServiceStopNotificationList should always be non-empty.`
- `0xbe1a`: `Service stop notification -- following services will be stopped or restarted: {0}`
- `0xbec4`: `Service stop notification -- display names of services which will be stopped or restarted: {0}`
- `0xbf26`: `ServiceDisruptionWarningPage.InstructionsLabelText`
- `0xbf55`: `ServiceDisruptionWarningPage.InstructionsLabelText`
- `0xbf33`: `ServiceDisruptionWarningPage.InstructionsLabelUninstall`
- `0xbf62`: `ServiceDisruptionWarningPage.InstructionsLabelInstall`

## pseudocode

```c

```

## disassembly

```asm
0xbdf0  ldarg.0
0xbdf1  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::get_AssociatedSetup()
0xbdf6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupBase::get_ServiceStopNotificationList()
0xbdfb  stloc.0
0xbdfc  ldloc.0
0xbdfd  ldnull
0xbdfe  cgt.un
0xbe00  ldstr    aServicestopnot// "ServiceStopNotificationList should alwa"...
0xbe05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xbe0a  ldloc.0
0xbe0b  call     T0x2B000009
0xbe10  ldstr    aServicestopnot_0// "ServiceStopNotificationList should alwa"...
0xbe15  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xbe1a  ldstr    aServiceStopNot// "Service stop notification -- following "...
0xbe1f  ldc.i4.1
0xbe20  newarr   [mscorlib]System.Object
0xbe25  dup
0xbe26  ldc.i4.0
0xbe27  ldstr    asc_19276// ", "
0xbe2c  ldloc.0
0xbe2d  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xbe32  stelem.ref
0xbe33  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xbe38  ldloc.0
0xbe39  call     T0x2B000001
0xbe3e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0xbe43  stloc.1
0xbe44  ldloc.0
0xbe45  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xbe4a  call     T0x2B00000A
0xbe4f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xbe54  stloc.2
0xbe55  br.s     loc_BE8F
0xbe57  ldloc.2
0xbe58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xbe5d  stloc.3
0xbe5e  ldarg.0
0xbe5f  ldloc.3
0xbe60  call     instance string Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::RetrieveServiceDisplayName(string serviceName)
0xbe65  stloc.s  4
0xbe67  ldloc.s  4
0xbe69  brfalse.s loc_BE8F
0xbe6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xbe70  ldstr    a0_0// "•  {0}"
0xbe75  ldc.i4.1
0xbe76  newarr   [mscorlib]System.Object
0xbe7b  dup
0xbe7c  ldc.i4.0
0xbe7d  ldloc.s  4
0xbe7f  stelem.ref
0xbe80  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbe85  stloc.s  5
0xbe87  ldloc.1
0xbe88  ldloc.s  5
0xbe8a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbe8f  ldloc.2
0xbe90  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbe95  brtrue.s loc_BE57
0xbe97  leave.s  loc_BEA3
0xbe99  ldloc.2
0xbe9a  brfalse.s loc_BEA2
0xbe9c  ldloc.2
0xbe9d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbea2  endfinally
0xbea3  ldloc.1
0xbea4  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_CurrentCulture()
0xbea9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Sort(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0xbeae  ldarg.0
0xbeaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_serviceList
0xbeb4  call     string [mscorlib]System.Environment::get_NewLine()
0xbeb9  ldloc.1
0xbeba  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xbebf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbec4  ldstr    aServiceStopNot_0// "Service stop notification -- display na"...
0xbec9  ldc.i4.1
0xbeca  newarr   [mscorlib]System.Object
0xbecf  dup
0xbed0  ldc.i4.0
0xbed1  ldstr    asc_19276// ", "
0xbed6  ldloc.1
0xbed7  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xbedc  stelem.ref
0xbedd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0xbee2  ldarg.0
0xbee3  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0xbee8  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0xbeed  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xbef2  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0xbef7  stloc.s  6
0xbef9  ldloc.s  6
0xbefb  ldc.i4.1
0xbefc  sub
0xbefd  switch   loc_BF4F, loc_BF4F, loc_BF4F, loc_BF20, loc_BF4F, loc_BF4F, loc_BF4F
0xbf1e  br.s     loc_BF4F
0xbf20  ldarg.0
0xbf21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xbf26  ldstr    aServicedisrupt_1// "ServiceDisruptionWarningPage.Instructio"...
0xbf2b  ldc.i4.1
0xbf2c  newarr   [mscorlib]System.Object
0xbf31  dup
0xbf32  ldc.i4.0
0xbf33  ldstr    aServicedisrupt_2// "ServiceDisruptionWarningPage.Instructio"...
0xbf38  ldc.i4.0
0xbf39  newarr   [mscorlib]System.Object
0xbf3e  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbf43  stelem.ref
0xbf44  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbf49  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbf4e  ret
0xbf4f  ldarg.0
0xbf50  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::_instructionLabel
0xbf55  ldstr    aServicedisrupt_1// "ServiceDisruptionWarningPage.Instructio"...
0xbf5a  ldc.i4.1
0xbf5b  newarr   [mscorlib]System.Object
0xbf60  dup
0xbf61  ldc.i4.0
0xbf62  ldstr    aServicedisrupt_3// "ServiceDisruptionWarningPage.Instructio"...
0xbf67  ldc.i4.0
0xbf68  newarr   [mscorlib]System.Object
0xbf6d  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbf72  stelem.ref
0xbf73  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbf78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xbf7d  ret
```
