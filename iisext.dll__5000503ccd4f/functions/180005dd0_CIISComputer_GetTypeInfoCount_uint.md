# CIISComputer::GetTypeInfoCount(uint *)

- ea: `0x180005dd0`
- end: `0x180005de0`
- name: `?GetTypeInfoCount@CIISComputer@@UEAAJPEAI@Z`
- size: `16`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::GetTypeInfoCount(CIISComputer *this, unsigned int *a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 7) + 24LL))(*((_QWORD *)this + 7), a2);
}

```

## disassembly

```asm
0x180005dd0  mov     rcx, [rcx+38h]
0x180005dd4  mov     rax, [rcx]
0x180005dd7  mov     rax, [rax+18h]
0x180005ddb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
