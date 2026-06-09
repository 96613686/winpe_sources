# Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::ProcessFailedActions

- ea: `0x171e0`
- end: `0x17235`
- name: `Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::ProcessFailedActions`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17070`

## callees

- `0x9dc0`
- `0x171e0`

## string_xrefs

- `0x171f3`: `Failed to install organization db updates. One or more actions have failed. Failing actions are: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x171e0  ldarg.0
0x171e1  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.Admin.OrganizationAction> Microsoft.Crm.Tools.Admin.OrganizationOperation::GetFailedActions()
0x171e6  stloc.0
0x171e7  ldloc.0
0x171e8  brfalse.s loc_17234
0x171ea  ldloc.0
0x171eb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::get_Count()
0x171f0  ldc.i4.0
0x171f1  ble.s    loc_17234
0x171f3  ldstr    aFailedToInstal_4// "Failed to install organization db updat"...
0x171f8  ldstr    asc_24552// ", "
0x171fd  ldloc.0
0x171fe  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Tools.Admin.OrganizationAction, string> <>c::<>9__11_0
0x17203  dup
0x17204  brtrue.s loc_1721D
0x17206  pop
0x17207  ldsfld   class <>c <>c::<>9
0x1720c  ldftn    instance string <>c::<ProcessFailedActions>b__11_0(class Microsoft.Crm.Tools.Admin.OrganizationAction action)
0x17212  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Tools.Admin.OrganizationAction, string>::.ctor(object, native int)
0x17217  dup
0x17218  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Tools.Admin.OrganizationAction, string> <>c::<>9__11_0
0x1721d  call     T0x2B00001D
0x17222  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x17227  stloc.1
0x17228  ldloc.1
0x17229  call     string [mscorlib]System.String::Format(string, object)
0x1722e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x17233  throw
0x17234  ret
```
