# Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::PopulateCheckBoxInfoDictionary

- ea: `0x14870`
- end: `0x14972`
- name: `Microsoft.Crm.Application.Components.UI.AccessPrivilegeList::PopulateCheckBoxInfoDictionary`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14720`

## callees

- `0x14590`

## string_xrefs

- `0x14876`: `delete`
- `0x14880`: `Web.Biz.Roles.edit_role.aspx_delete`
- `0x1488a`: `Delete_Access_CheckBox`
- `0x148ae`: `Append_Access_CheckBox`
- `0x148d2`: `AppendTo_Access_CheckBox`
- `0x148f6`: `Assign_Access_CheckBox`
- `0x1491a`: `Share_Access_CheckBox`
- `0x14934`: `Web.Biz.Roles.edit_role.aspx_read`
- `0x1493e`: `Read_Access_CheckBox`
- `0x1494e`: `write`
- `0x14958`: `Web.Biz.Roles.edit_role.aspx_write`
- `0x14962`: `Write_Access_CheckBox`

## pseudocode

```c

```

## disassembly

```asm
0x14870  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::.ctor()
0x14875  dup
0x14876  ldstr    aDelete// "delete"
0x1487b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14880  ldstr    aWebBizRolesEdi// "Web.Biz.Roles.edit_role.aspx_delete"
0x14885  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1488a  ldstr    aDeleteAccessCh// "Delete_Access_CheckBox"
0x1488f  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x14894  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x14899  dup
0x1489a  ldstr    aAppend// "append"
0x1489f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x148a4  ldstr    aWebBizRolesEdi_0// "Web.Biz.Roles.edit_role.aspx_append"
0x148a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x148ae  ldstr    aAppendAccessCh// "Append_Access_CheckBox"
0x148b3  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x148b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x148bd  dup
0x148be  ldstr    aAppendto// "appendto"
0x148c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x148c8  ldstr    aWebBizRolesEdi_1// "Web.Biz.Roles.edit_role.aspx_appendto"
0x148cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x148d2  ldstr    aAppendtoAccess// "AppendTo_Access_CheckBox"
0x148d7  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x148dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x148e1  dup
0x148e2  ldstr    aAssign// "assign"
0x148e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x148ec  ldstr    aWebBizRolesEdi_2// "Web.Biz.Roles.edit_role.aspx_assign"
0x148f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x148f6  ldstr    aAssignAccessCh// "Assign_Access_CheckBox"
0x148fb  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x14900  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x14905  dup
0x14906  ldstr    aShare// "share"
0x1490b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14910  ldstr    aWebBizRolesEdi_3// "Web.Biz.Roles.edit_role.aspx_share"
0x14915  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1491a  ldstr    aShareAccessChe// "Share_Access_CheckBox"
0x1491f  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x14924  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x14929  dup
0x1492a  ldstr    aRead// "read"
0x1492f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14934  ldstr    aWebBizRolesEdi_4// "Web.Biz.Roles.edit_role.aspx_read"
0x14939  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1493e  ldstr    aReadAccessChec// "Read_Access_CheckBox"
0x14943  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x14948  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x1494d  dup
0x1494e  ldstr    aWrite// "write"
0x14953  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x14958  ldstr    aWebBizRolesEdi_5// "Web.Biz.Roles.edit_role.aspx_write"
0x1495d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14962  ldstr    aWriteAccessChe// "Write_Access_CheckBox"
0x14967  newobj   instance void Microsoft.Crm.Application.Components.UI.CheckBoxInfo::.ctor(string title, string id)
0x1496c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.CheckBoxInfo>::Add(var<u1>, !!T0)
0x14971  ret
```
