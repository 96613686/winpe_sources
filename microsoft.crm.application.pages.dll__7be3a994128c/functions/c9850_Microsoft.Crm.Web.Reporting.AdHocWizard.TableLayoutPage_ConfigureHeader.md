# Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::ConfigureHeader

- ea: `0xc9850`
- end: `0xc9a4f`
- name: `Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::ConfigureHeader`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xc7220`
- `0xc7320`

## string_xrefs

- `0xc98c7`: `Grid.Common.Alt.SortedColumn.Down`
- `0xc98e8`: `Grid.Common.Alt.SortedColumn.Up`
- `0xc98ac`: `/_nav/taskbox.css.aspx`
- `0xc986c`: `/_static/CRMReports/AdHocWizard/AttributeInfoCache.js`
- `0xc985c`: `/_static/CRMReports/AdHocWizard/CacheManager.js`
- `0xc989c`: `/_static/CRMReports/AdHocWizard/WizardXmlBuilder.js`
- `0xc98fe`: `LOCID_FIELDS_REMOVED`
- `0xc9909`: `CustomReporting.AdHocWizard.TableLayoutPage.FieldsRemoved`
- `0xc99c4`: `LOCID_REMOVE_COLUMN_WARNING`
- `0xc99cf`: `CustomReporting.AdHocWizard.TableLayoutPage.RemoveColumnWarning`

## pseudocode

```c

```

## disassembly

```asm
0xc9850  ldarg.0
0xc9851  call     instance void Microsoft.Crm.Web.Reporting.AdHocWizard.AdHocWizardPage::ConfigureHeader()
0xc9856  ldarg.0
0xc9857  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc985c  ldstr    aStaticCrmrepor_1// "/_static/CRMReports/AdHocWizard/CacheMa"...
0xc9861  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc9866  ldarg.0
0xc9867  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc986c  ldstr    aStaticCrmrepor_0// "/_static/CRMReports/AdHocWizard/Attribu"...
0xc9871  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc9876  ldarg.0
0xc9877  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc987c  ldstr    aStaticCrmrepor_4// "/_static/CRMReports/AdHocWizard/FetchBu"...
0xc9881  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc9886  ldarg.0
0xc9887  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc988c  ldstr    aStaticCrmrepor_6// "/_static/CRMReports/AdHocWizard/TableLa"...
0xc9891  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc9896  ldarg.0
0xc9897  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc989c  ldstr    aStaticCrmrepor_5// "/_static/CRMReports/AdHocWizard/WizardX"...
0xc98a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xc98a6  ldarg.0
0xc98a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc98ac  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0xc98b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xc98b6  ldarg.0
0xc98b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc98bc  ldstr    aLocidAltColumn// "LOCID_ALT_COLUMNSORTORDER_DOWN"
0xc98c1  ldarg.0
0xc98c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc98c7  ldstr    aGridCommonAltS// "Grid.Common.Alt.SortedColumn.Down"
0xc98cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc98d1  ldc.i4.0
0xc98d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc98d7  ldarg.0
0xc98d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc98dd  ldstr    aLocidAltColumn_0// "LOCID_ALT_COLUMNSORTORDER_UP"
0xc98e2  ldarg.0
0xc98e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc98e8  ldstr    aGridCommonAltS_0// "Grid.Common.Alt.SortedColumn.Up"
0xc98ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc98f2  ldc.i4.0
0xc98f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc98f8  ldarg.0
0xc98f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc98fe  ldstr    aLocidFieldsRem// "LOCID_FIELDS_REMOVED"
0xc9903  ldarg.0
0xc9904  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9909  ldstr    aCustomreportin_80// "CustomReporting.AdHocWizard.TableLayout"...
0xc990e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9913  ldc.i4.0
0xc9914  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc9919  ldarg.0
0xc991a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc991f  ldstr    aLocidGhostGrou// "LOCID_GHOST_GROUPING"
0xc9924  ldarg.0
0xc9925  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc992a  ldstr    aCustomreportin_81// "CustomReporting.AdHocWizard.TableLayout"...
0xc992f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9934  ldc.i4.0
0xc9935  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc993a  ldarg.0
0xc993b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc9940  ldstr    aLocidNoColumns// "LOCID_NO_COLUMNS_SELECTED"
0xc9945  ldarg.0
0xc9946  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc994b  ldstr    aCustomreportin_82// "CustomReporting.AdHocWizard.TableLayout"...
0xc9950  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9955  ldc.i4.0
0xc9956  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc995b  ldarg.0
0xc995c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc9961  ldstr    aLocidNoFiltera// "LOCID_NO_FILTERABLE_COLUMN"
0xc9966  ldarg.0
0xc9967  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc996c  ldstr    aCustomreportin_83// "CustomReporting.AdHocWizard.TableLayout"...
0xc9971  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9976  ldc.i4.0
0xc9977  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc997c  ldarg.0
0xc997d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc9982  ldstr    aLocidNoFiltera_0// "LOCID_NO_FILTERABLE_GROUPING"
0xc9987  ldarg.0
0xc9988  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc998d  ldstr    aCustomreportin_84// "CustomReporting.AdHocWizard.TableLayout"...
0xc9992  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9997  ldc.i4.0
0xc9998  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc999d  ldarg.0
0xc999e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc99a3  ldstr    aLocidNoSortabl// "LOCID_NO_SORTABLE_COLUMNS"
0xc99a8  ldarg.0
0xc99a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc99ae  ldstr    aCustomreportin_85// "CustomReporting.AdHocWizard.TableLayout"...
0xc99b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc99b8  ldc.i4.0
0xc99b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc99be  ldarg.0
0xc99bf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc99c4  ldstr    aLocidRemoveCol// "LOCID_REMOVE_COLUMN_WARNING"
0xc99c9  ldarg.0
0xc99ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc99cf  ldstr    aCustomreportin_86// "CustomReporting.AdHocWizard.TableLayout"...
0xc99d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc99d9  ldc.i4.0
0xc99da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc99df  ldarg.0
0xc99e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc99e5  ldstr    aLocidTooltipCo// "LOCID_TOOLTIP_COLUMN"
0xc99ea  ldarg.0
0xc99eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc99f0  ldstr    aCustomreportin_87// "CustomReporting.AdHocWizard.TableLayout"...
0xc99f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc99fa  ldc.i4.0
0xc99fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc9a00  ldarg.0
0xc9a01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc9a06  ldstr    aLocidTooltipGr// "LOCID_TOOLTIP_GROUPING"
0xc9a0b  ldarg.0
0xc9a0c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9a11  ldstr    aCustomreportin_88// "CustomReporting.AdHocWizard.TableLayout"...
0xc9a16  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9a1b  ldc.i4.0
0xc9a1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc9a21  ldarg.0
0xc9a22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xc9a27  ldstr    aLocidPagebreak// "LOCID_PAGEBREAK_WARNING"
0xc9a2c  ldarg.0
0xc9a2d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9a32  ldstr    aCustomreportin_89// "CustomReporting.AdHocWizard.TableLayout"...
0xc9a37  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9a3c  ldc.i4.0
0xc9a3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xc9a42  ldarg.0
0xc9a43  ldarg.0
0xc9a44  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::_culture
0xc9a49  call     instance void Microsoft.Crm.Web.Reporting.AdHocWizard.AdHocWizardPage::SetFormatStringArrayResources(class [mscorlib]System.Globalization.CultureInfo culture)
0xc9a4e  ret
```
