# _ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog_::_1_::dtor$0

- ea: `0x1800107cd`
- end: `0x1800107d9`
- name: `_ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009974`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::ShowLauncherIncompatibleErrorDialog_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)(a2 + 48));
}

```

## disassembly

```asm
0x1800107cd  lea     rcx, [rdx+30h]; this
0x1800107d4  jmp     ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
```
