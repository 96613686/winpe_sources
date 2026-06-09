# std::_Uninitialized_move<CLocationEnvironmentHelper::BitMetadata *,std::allocator<CLocationEnvironmentHelper::BitMetadata>>(CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata * const,CLocationEnvironmentHelper::BitMetadata *,std::allocator<CLocationEnvironmentHelper::BitMetadata> &)

- ea: `0x180005ad0`
- end: `0x180005b14`
- name: `??$_Uninitialized_move@PEAUBitMetadata@CLocationEnvironmentHelper@@V?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@std@@@std@@YAPEAUBitMetadata@CLocationEnvironmentHelper@@QEAU12@0PEAU12@AEAV?$allocator@UBitMetadata@CLocationEnvironmentHelper@@@0@@Z`
- size: `68`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058fc`

## callees

- `0x180005880`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<CLocationEnvironmentHelper::BitMetadata *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *>(a1, a2, a3);
  return &a3[40 * ((a2 - (__int64)a1) / 40)];
}

```

## disassembly

```asm
0x180005ad0  push    rbx
0x180005ad2  push    rsi
0x180005ad3  push    rdi
0x180005ad4  sub     rsp, 20h
0x180005ad8  mov     rsi, r8
0x180005adb  mov     rdi, rdx
0x180005ade  mov     rbx, rcx
0x180005ae1  call    ??$_Copy_memmove@PEAUBitMetadata@CLocationEnvironmentHelper@@PEAU12@@std@@YAPEAUBitMetadata@CLocationEnvironmentHelper@@PEAU12@00@Z; std::_Copy_memmove<CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *>(CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *,CLocationEnvironmentHelper::BitMetadata *)
0x180005ae6  sub     rdi, rbx
0x180005ae9  mov     rax, 6666666666666667h
0x180005af3  imul    rdi
0x180005af6  sar     rdx, 4
0x180005afa  mov     rax, rdx
0x180005afd  shr     rax, 3Fh
0x180005b01  add     rdx, rax
0x180005b04  lea     rax, [rdx+rdx*4]
0x180005b08  lea     rax, [rsi+rax*8]
0x180005b0c  add     rsp, 20h
0x180005b10  pop     rdi
0x180005b11  pop     rsi
0x180005b12  pop     rbx
0x180005b13  retn
```
