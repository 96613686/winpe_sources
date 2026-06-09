# CIISComputer::SaveData(void)

- ea: `0x180006fd0`
- end: `0x180006fe3`
- name: `?SaveData@CIISComputer@@UEAAJXZ`
- size: `19`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::SaveData(CIISComputer *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 160LL))(*((_QWORD *)this + 15));
}

```

## disassembly

```asm
0x180006fd0  mov     rcx, [rcx+78h]
0x180006fd4  mov     rax, [rcx]
0x180006fd7  mov     rax, [rax+0A0h]
0x180006fde  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
