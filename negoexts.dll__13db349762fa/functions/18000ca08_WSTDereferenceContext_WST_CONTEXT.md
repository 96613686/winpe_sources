# WSTDereferenceContext(_WST_CONTEXT *)

- ea: `0x18000ca08`
- end: `0x18000ca3b`
- name: `?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z`
- size: `51`
- prototype: `void __fastcall(struct _WST_CONTEXT *)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180009db0`
- `0x18000a29c`
- `0x18000b7d0`
- `0x18000c7d0`
- `0x18000cd24`
- `0x180014150`
- `0x180016910`
- `0x1800169d4`
- `0x180016db0`
- `0x180016f70`
- `0x180017b60`
- `0x180017f00`
- `0x180018770`
- `0x18001cf58`
- `0x18001d380`

## callees

- `0x180003500`
- `0x18000ca08`
- `0x18001a390`

## pseudocode

```c
void __fastcall WSTDereferenceContext(struct _WST_CONTEXT *a1)
{
  if ( a1
    && *(_QWORD *)a1 == 0x545854434F545357LL
    && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 3, 0xFFFFFFFF) <= 1 )
  {
    WSTFreeContext(a1);
  }
}

```

## disassembly

```asm
0x18000ca08  sub     rsp, 28h
0x18000ca0c  test    rcx, rcx
0x18000ca0f  jz      short loc_18000CA36
0x18000ca11  mov     rax, 545854434F545357h
0x18000ca1b  cmp     [rcx], rax
0x18000ca1e  jnz     short loc_18000CA36
0x18000ca20  or      eax, 0FFFFFFFFh
0x18000ca23  lock xadd [rcx+0Ch], eax
0x18000ca28  sub     eax, 1
0x18000ca2b  jg      short loc_18000CA36
0x18000ca2d  add     rsp, 28h
0x18000ca31  jmp     ?WSTFreeContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTFreeContext(_WST_CONTEXT *)
0x18000ca36  add     rsp, 28h
0x18000ca3a  retn
0x18001efa4  push    rbp
0x18001efa6  sub     rsp, 20h
0x18001efaa  mov     rbp, rdx
0x18001efad  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001efb2  nop
0x18001efb3  add     rsp, 20h
0x18001efb7  pop     rbp
0x18001efb8  retn
```
