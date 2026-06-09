# CdpGetDisplaySize

- ea: `0x140008da4`
- end: `0x140008e4b`
- name: `CdpGetDisplaySize`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008cd0`

## callees

- `0x140001500`
- `0x1400081a0`
- `0x140008da4`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140008dfb`
- `ntoskrnl!ProbeForWrite` at `0x140008dfb`

## pseudocode

```c
__int64 __fastcall CdpGetDisplaySize(char a1, volatile void *a2, unsigned int a3, _QWORD *a4)
{
  __int64 Src; // [rsp+28h] [rbp-10h] BYREF

  if ( a3 < 8 )
    return 3221225990LL;
  Src = qword_1400051A8;
  if ( a1 )
  {
    ProbeForWrite(a2, a3, 4u);
    RtlWriteULong64ToUser(a2, Src);
  }
  else
  {
    RtlCopyVolatileMemory((void *)a2, &Src, 8u);
  }
  *a4 = 8;
  return 0;
}

```

## disassembly

```asm
0x140008da4  mov     [rsp+arg_8], rbx
0x140008da9  mov     [rsp+arg_10], rsi
0x140008dae  mov     [rsp+arg_0], cl
0x140008db2  push    rdi
0x140008db3  sub     rsp, 30h
0x140008db7  mov     rsi, r9
0x140008dba  mov     rbx, rdx
0x140008dbd  mov     dil, cl
0x140008dc0  cmp     r8d, 8
0x140008dc4  jnb     short loc_140008DCD
0x140008dc6  mov     eax, 0C0000206h
0x140008dcb  jmp     short loc_140008E3A
0x140008dcd  mov     [rsp+38h+Src], 0
0x140008dd6  mov     eax, dword ptr cs:qword_1400051A8
0x140008ddc  mov     dword ptr [rsp+38h+Src], eax
0x140008de0  mov     eax, dword ptr cs:qword_1400051A8+4
0x140008de6  mov     dword ptr [rsp+38h+Src+4], eax
0x140008dea  test    dil, dil
0x140008ded  jz      short loc_140008E1B
0x140008def  mov     edx, r8d; Length
0x140008df2  mov     r8d, 4; Alignment
0x140008df8  mov     rcx, rbx; Address
0x140008dfb  call    cs:__imp_ProbeForWrite
0x140008e02  nop     dword ptr [rax+rax+00h]
0x140008e07  test    dil, dil
0x140008e0a  jz      short loc_140008E1B
0x140008e0c  mov     rdx, [rsp+38h+Src]
0x140008e11  mov     rcx, rbx
0x140008e14  call    RtlWriteULong64ToUser
0x140008e19  jmp     short loc_140008E2F
0x140008e1b  mov     r8d, 8; Size
0x140008e21  lea     rdx, [rsp+38h+Src]; Src
0x140008e26  mov     rcx, rbx; void *
0x140008e29  call    RtlCopyVolatileMemory
0x140008e2e  nop
0x140008e2f  mov     qword ptr [rsi], 8
0x140008e36  xor     eax, eax
0x140008e38  jmp     short $+2
0x140008e3a  mov     rbx, [rsp+38h+arg_8]
0x140008e3f  mov     rsi, [rsp+38h+arg_10]
0x140008e44  add     rsp, 30h
0x140008e48  pop     rdi
0x140008e49  retn
0x14000e7c7  push    rbp
0x14000e7c9  sub     rsp, 20h
0x14000e7cd  mov     rbp, rdx
0x14000e7d0  xor     eax, eax
0x14000e7d2  cmp     [rbp+40h], al
0x14000e7d5  setnz   al
0x14000e7d8  mov     [rbp+20h], eax
0x14000e7db  mov     eax, [rbp+20h]
0x14000e7de  add     rsp, 20h
0x14000e7e2  pop     rbp
0x14000e7e3  retn
```
