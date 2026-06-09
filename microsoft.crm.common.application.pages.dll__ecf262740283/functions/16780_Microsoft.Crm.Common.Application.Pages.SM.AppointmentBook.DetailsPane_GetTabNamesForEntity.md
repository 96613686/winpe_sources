# Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::GetTabNamesForEntity

- ea: `0x16780`
- end: `0x1689a`
- name: `Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::GetTabNamesForEntity`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16470`

## callees

- `0x16780`
- `0x168a0`

## pseudocode

```c

```

## disassembly

```asm
0x16780  ldarg.1
0x16781  ldc.i4.0
0x16782  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16787  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1678c  stloc.0
0x1678d  ldarg.0
0x1678e  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesScript
0x16793  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x16798  stloc.1
0x16799  ldarg.0
0x1679a  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x1679f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x167a4  stloc.2
0x167a5  ldloc.0
0x167a6  brfalse  loc_16881
0x167ab  ldloc.0
0x167ac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.TabCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_Tabs()
0x167b1  callvirt instance class [mscorlib]System.Collections.IEnumerator class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ReadOnlyListCollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.TabDescriptor>::GetEnumerator()
0x167b6  stloc.3
0x167b7  br       loc_16860
0x167bc  ldloc.3
0x167bd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x167c2  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.TabDescriptor
0x167c7  stloc.s  4
0x167c9  ldloc.1
0x167ca  ldarg.0
0x167cb  call     instance string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::AddDiv()
0x167d0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x167d5  pop
0x167d6  ldarg.0
0x167d7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x167dc  ldloc.s  4
0x167de  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_UserLabel()
0x167e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.LabelDescriptor::get_Description()
0x167e8  ldarg.0
0x167e9  ldflda   int32 Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pageIndex
0x167ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x167f3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x167f8  ldstr    asc_31504// "_"
0x167fd  call     string [mscorlib]System.String::Concat(string, string)
0x16802  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x16807  ldloc.2
0x16808  ldstr    aCustomizablefo// "\"customizableForm.aspx?type="
0x1680d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16812  pop
0x16813  ldloc.2
0x16814  ldarga.s 1
0x16816  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1681b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x16820  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16825  pop
0x16826  ldloc.2
0x16827  ldstr    aId_2// "&id="
0x1682c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16831  pop
0x16832  ldloc.2
0x16833  ldarg.2
0x16834  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16839  pop
0x1683a  ldloc.2
0x1683b  ldstr    aTabid// "&tabID="
0x16840  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16845  pop
0x16846  ldloc.2
0x16847  ldloc.s  4
0x16849  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormPartWithLabelDescriptor::get_Id()
0x1684e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16853  pop
0x16854  ldloc.2
0x16855  ldstr    asc_3193C// "\","
0x1685a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1685f  pop
0x16860  ldloc.3
0x16861  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16866  brtrue   loc_167BC
0x1686b  leave.s  loc_16881
0x1686d  ldloc.3
0x1686e  isinst   [mscorlib]System.IDisposable
0x16873  stloc.s  5
0x16875  ldloc.s  5
0x16877  brfalse.s loc_16880
0x16879  ldloc.s  5
0x1687b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16880  endfinally
0x16881  ldarg.0
0x16882  ldloc.1
0x16883  callvirt instance string [mscorlib]System.Object::ToString()
0x16888  stfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesScript
0x1688d  ldarg.0
0x1688e  ldloc.2
0x1688f  callvirt instance string [mscorlib]System.Object::ToString()
0x16894  stfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x16899  ret
```
