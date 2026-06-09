# WSTDereferencePackage(_WST_SSP_PACKAGE *)

- ea: `0x180008c58`
- end: `0x180008c8b`
- name: `?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z`
- size: `51`
- prototype: `void __fastcall(struct _WST_SSP_PACKAGE *)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x1800070d0`
- `0x1800085c0`
- `0x1800087d0`
- `0x180008880`
- `0x18000c7d0`
- `0x18000ea54`
- `0x180014150`
- `0x180016824`
- `0x180016f70`
- `0x180017f00`
- `0x18001a3b4`
- `0x18001b9b0`
- `0x18001bba4`

## callees

- `0x180008c58`
- `0x180018c20`
- `0x18001a390`

## pseudocode

```c
void __fastcall WSTDereferencePackage(struct _WST_SSP_PACKAGE *a1)
{
  if ( *((_QWORD *)a1 + 2) == 0x474B50534F545357LL
    && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 7, 0xFFFFFFFF) == 1 )
  {
    WSTFreePackage(a1);
  }
}

```

## disassembly

```asm
0x180008c58  sub     rsp, 28h
0x180008c5c  mov     rax, 474B50534F545357h
0x180008c66  cmp     [rcx+10h], rax
0x180008c6a  jnz     short loc_180008C7D
0x180008c6c  jmp     short loc_180008C70
0x180008c6e  jmp     short loc_180008C7D
0x180008c70  or      eax, 0FFFFFFFFh
0x180008c73  lock xadd [rcx+1Ch], eax
0x180008c78  cmp     eax, 1
0x180008c7b  jz      short loc_180008C82
0x180008c7d  add     rsp, 28h
0x180008c81  retn
0x180008c82  add     rsp, 28h
0x180008c86  jmp     ?WSTFreePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTFreePackage(_WST_SSP_PACKAGE *)
0x18001eec0  push    rbp
0x18001eec2  sub     rsp, 20h
0x18001eec6  mov     rbp, rdx
0x18001eec9  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001eece  nop
0x18001eecf  add     rsp, 20h
0x18001eed3  pop     rbp
0x18001eed4  retn
```
