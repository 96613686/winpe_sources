# Microsoft.Crm.Controls.TaskBox::.ctor

- ea: `0xa970`
- end: `0xa9d5`
- name: `Microsoft.Crm.Controls.TaskBox::.ctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xa9f0`
- `0xaa10`
- `0xaa30`
- `0xaa50`
- `0xaa70`
- `0x24040`

## string_xrefs

- `0xa99c`: `TaskBox_Title_CommonTasks`

## pseudocode

```c

```

## disassembly

```asm
0xa970  ldarg.0
0xa971  ldc.i4   0x3E8
0xa976  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xa97b  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Controls.TaskBox::_topHtml
0xa980  ldarg.0
0xa981  ldc.i4   0x3E8
0xa986  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xa98b  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Controls.TaskBox::_bottomHtml
0xa990  ldarg.0
0xa991  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor()
0xa996  ldarg.0
0xa997  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa99c  ldstr    aTaskboxTitleCo// "TaskBox_Title_CommonTasks"
0xa9a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa9a6  call     instance void Microsoft.Crm.Controls.TaskBox::set_Title(string value)
0xa9ab  ldarg.0
0xa9ac  ldstr    a143px// "143px"
0xa9b1  call     instance void Microsoft.Crm.Controls.TaskBox::set_Width(string value)
0xa9b6  ldarg.0
0xa9b7  ldstr    a100_0// "100%"
0xa9bc  call     instance void Microsoft.Crm.Controls.TaskBox::set_Height(string value)
0xa9c1  ldarg.0
0xa9c2  ldsfld   string [mscorlib]System.String::Empty
0xa9c7  call     instance void Microsoft.Crm.Controls.TaskBox::set_Icon(string value)
0xa9cc  ldarg.0
0xa9cd  ldc.i4.s 0x1A
0xa9cf  call     instance void Microsoft.Crm.Controls.TaskBox::set_ColumnWidth(int32 value)
0xa9d4  ret
```
