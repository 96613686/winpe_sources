# _ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$0

- ea: `0x180010328`
- end: `0x180010334`
- name: `_ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cb6c`

## pseudocode

```c
void __fastcall ShowPortableWorkspaceLauncherConfigurationUX_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ux::CSingleInstanceApplication::~CSingleInstanceApplication((ux::CSingleInstanceApplication *)(a2 + 64));
}

```

## disassembly

```asm
0x180010328  lea     rcx, [rdx+40h]; this
0x18001032f  jmp     ??1CSingleInstanceApplication@ux@@UEAA@XZ; ux::CSingleInstanceApplication::~CSingleInstanceApplication(void)
```
