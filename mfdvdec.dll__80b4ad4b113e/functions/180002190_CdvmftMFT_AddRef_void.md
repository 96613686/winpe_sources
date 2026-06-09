# CdvmftMFT::AddRef(void)

- ea: `0x180002190`
- end: `0x1800021a0`
- name: `?AddRef@CdvmftMFT@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CdvmftMFT *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021b0`
- `0x1800021c0`
- `0x1800021d0`
- `0x1800021e0`
- `0x1800021f0`

## callees

- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CdvmftMFT::AddRef(CdvmftMFT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 8LL))(*((_QWORD *)this - 2));
}

```

## disassembly

```asm
0x180002190  mov     rcx, [rcx-10h]
0x180002194  mov     rax, [rcx]
0x180002197  mov     rax, [rax+8]
0x18000219b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
