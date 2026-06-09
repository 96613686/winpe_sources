# std::_Copy_memmove_tail<CLocationEnvironmentHelper::BitMetadata *>(char const * const,CLocationEnvironmentHelper::BitMetadata * const,unsigned __int64,unsigned __int64)

- ea: `0x180005898`
- end: `0x1800058c2`
- name: `??$_Copy_memmove_tail@PEAUBitMetadata@CLocationEnvironmentHelper@@@std@@YAPEAUBitMetadata@CLocationEnvironmentHelper@@QEBDQEAU12@_K2@Z`
- size: `42`
- prototype: `__int64 __fastcall(void *Src, void *, size_t)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005880`

## callees

- `0x18000b3cc`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_tail<CLocationEnvironmentHelper::BitMetadata *>(void *Src, void *a2, size_t a3)
{
  memmove_0(a2, Src, a3);
  return (__int64)a2 + a3;
}

```

## disassembly

```asm
0x180005898  mov     [rsp+arg_18], rbx
0x18000589d  push    rdi
0x18000589e  sub     rsp, 20h
0x1800058a2  mov     rbx, rdx
0x1800058a5  mov     rdi, r8
0x1800058a8  mov     rdx, rcx; Src
0x1800058ab  mov     rcx, rbx; void *
0x1800058ae  call    memmove_0
0x1800058b3  lea     rax, [rdi+rbx]
0x1800058b7  mov     rbx, [rsp+28h+arg_18]
0x1800058bc  add     rsp, 20h
0x1800058c0  pop     rdi
0x1800058c1  retn
```
