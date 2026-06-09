# Microsoft.Crm.Setup.Common.UI.Wizard::SetNextButtonDefaultText

- ea: `0xffe0`
- end: `0x10016`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::SetNextButtonDefaultText`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0xffe0`: `Microsoft.Crm.Setup.Common.Wizard`

## pseudocode

```c

```

## disassembly

```asm
0xffe0  ldstr    aMicrosoftCrmSe_8// "Microsoft.Crm.Setup.Common.Wizard"
0xffe5  ldtoken  Microsoft.Crm.Setup.Common.UI.Wizard
0xffea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xffef  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xfff4  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xfff9  stloc.0
0xfffa  ldarg.0
0xfffb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::nextButton
0x10000  ldloc.0
0x10001  ldstr    aNextbuttonText// "nextButton.Text"
0x10006  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x1000b  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x10010  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x10015  ret
```
