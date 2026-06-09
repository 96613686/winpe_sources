# Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl

- ea: `0xe650`
- end: `0xe6ac`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl`
- size: `92`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdf40`
- `0xdfb0`
- `0xe120`
- `0xe650`

## callees

- `0xe650`

## pseudocode

```c

```

## disassembly

```asm
0xe650  ldarg.1
0xe651  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xe656  ldarg.2
0xe657  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe65c  brfalse.s loc_E660
0xe65e  ldarg.1
0xe65f  ret
0xe660  ldarg.1
0xe661  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xe666  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0xe66b  stloc.0
0xe66c  br.s     loc_E68A
0xe66e  ldloc.0
0xe66f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe674  castclass [System.Web]System.Web.UI.Control
0xe679  stloc.1
0xe67a  ldarg.0
0xe67b  ldloc.1
0xe67c  ldarg.2
0xe67d  call     instance class [System.Web]System.Web.UI.Control Microsoft.Crm.Common.Web.Activities.Dialogs.RecurrenceDialog::FindChildControl(class [System.Web]System.Web.UI.Control control, string id)
0xe682  stloc.2
0xe683  ldloc.2
0xe684  brfalse.s loc_E68A
0xe686  ldloc.2
0xe687  stloc.3
0xe688  leave.s  loc_E6AA
0xe68a  ldloc.0
0xe68b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe690  brtrue.s loc_E66E
0xe692  leave.s  loc_E6A8
0xe694  ldloc.0
0xe695  isinst   [mscorlib]System.IDisposable
0xe69a  stloc.s  4
0xe69c  ldloc.s  4
0xe69e  brfalse.s loc_E6A7
0xe6a0  ldloc.s  4
0xe6a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe6a7  endfinally
0xe6a8  ldnull
0xe6a9  ret
0xe6aa  ldloc.3
0xe6ab  ret
```
