# _ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$1

- ea: `0x18001033a`
- end: `0x180010346`
- name: `_ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x1800099bc`

## pseudocode

```c
void __fastcall ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog((ux::CLauncherMainTaskDialog *)(a2 + 96));
}

```

## disassembly

```asm
0x18001033a  lea     rcx, [rdx+60h]; this
0x180010341  jmp     ??1CLauncherMainTaskDialog@ux@@UEAA@XZ; ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(void)
```
