# _PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$9

- ea: `0x180009b1d`
- end: `0x180009b29`
- name: `_PwrshPlugInMediator::LoadPowerShell_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000521c`

## pseudocode

```c
void __fastcall PwrshPlugInMediator::LoadPowerShell_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  IPowerShellClrHost::~IPowerShellClrHost(*(IPowerShellClrHost **)(a2 + 64));
}

```

## disassembly

```asm
0x180009b1d  mov     rcx, [rdx+40h]; this
0x180009b24  jmp     ??1IPowerShellClrHost@@UEAA@XZ; IPowerShellClrHost::~IPowerShellClrHost(void)
```
