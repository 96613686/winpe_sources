# Microsoft.Crm.Controls.PageResourceManager::get_LinkedInstance

- ea: `0x35f0`
- end: `0x3632`
- name: `Microsoft.Crm.Controls.PageResourceManager::get_LinkedInstance`
- size: `66`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3430`
- `0x3680`
- `0x36a0`
- `0x36c0`
- `0x36e0`
- `0x3700`
- `0x3720`
- `0x3740`
- `0x3760`

## callees

- `0x35f0`
- `0xbef0`
- `0xbf00`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  ldarg.0
0x35f1  ldfld    class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.PageResourceManager::_linkedInstance
0x35f6  brfalse.s loc_35FF
0x35f8  ldarg.0
0x35f9  ldfld    class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.PageResourceManager::_linkedInstance
0x35fe  ret
0x35ff  ldarg.0
0x3600  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3605  isinst   Microsoft.Crm.Controls.UIPage
0x360a  stloc.0
0x360b  ldloc.0
0x360c  brtrue.s loc_3610
0x360e  ldnull
0x360f  ret
0x3610  ldarg.0
0x3611  ldloc.0
0x3612  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x3617  bne.un.s loc_3620
0x3619  ldloc.0
0x361a  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x361f  ret
0x3620  ldarg.0
0x3621  ldloc.0
0x3622  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_FooterControl()
0x3627  bne.un.s loc_3630
0x3629  ldloc.0
0x362a  callvirt instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x362f  ret
0x3630  ldnull
0x3631  ret
```
