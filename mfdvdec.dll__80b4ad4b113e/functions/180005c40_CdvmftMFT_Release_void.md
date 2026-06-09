# CdvmftMFT::Release(void)

- ea: `0x180005c40`
- end: `0x180005c50`
- name: `?Release@CdvmftMFT@@UEAAKXZ`
- size: `16`
- prototype: `unsigned int __fastcall(CdvmftMFT *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c60`
- `0x180005c70`
- `0x180005c80`
- `0x180005c90`
- `0x180005ca0`

## callees

- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CdvmftMFT::Release(CdvmftMFT *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 16LL))(*((_QWORD *)this - 2));
}

```

## disassembly

```asm
0x180005c40  mov     rcx, [rcx-10h]
0x180005c44  mov     rax, [rcx]
0x180005c47  mov     rax, [rax+10h]
0x180005c4b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
