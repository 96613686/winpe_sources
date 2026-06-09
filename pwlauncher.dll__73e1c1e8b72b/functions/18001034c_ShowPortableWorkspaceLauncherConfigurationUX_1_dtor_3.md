# _ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$3

- ea: `0x18001034c`
- end: `0x180010358`
- name: `_ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180009974`

## pseudocode

```c
void __fastcall ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)(a2 + 96));
}

```

## disassembly

```asm
0x18001034c  lea     rcx, [rdx+60h]; this
0x180010353  jmp     ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
```
