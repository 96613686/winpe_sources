# CILogWrite::AddRef(void)

- ea: `0x180004d60`
- end: `0x180004d70`
- name: `?AddRef@CILogWrite@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(CILogWrite *this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall CILogWrite::AddRef(CILogWrite *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180004d60  mov     rcx, [rcx+8]
0x180004d64  mov     rax, [rcx]
0x180004d67  mov     rax, [rax+20h]
0x180004d6b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
