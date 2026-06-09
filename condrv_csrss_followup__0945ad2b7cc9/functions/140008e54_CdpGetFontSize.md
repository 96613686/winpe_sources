# CdpGetFontSize

- ea: `0x140008e54`
- end: `0x140008efb`
- name: `CdpGetFontSize`
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
- `0x140008e54`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140008eab`
- `ntoskrnl!ProbeForWrite` at `0x140008eab`

## pseudocode

```c
__int64 __fastcall CdpGetFontSize(char a1, volatile void *a2, unsigned int a3, _QWORD *a4)
{
  __int64 Src; // [rsp+28h] [rbp-10h] BYREF

  if ( a3 < 8 )
    return 3221225990LL;
  Src = qword_1400051B0;
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
0x140008e54  mov     [rsp+arg_8], rbx
0x140008e59  mov     [rsp+arg_10], rsi
0x140008e5e  mov     [rsp+arg_0], cl
0x140008e62  push    rdi
0x140008e63  sub     rsp, 30h
0x140008e67  mov     rsi, r9
0x140008e6a  mov     rbx, rdx
0x140008e6d  mov     dil, cl
0x140008e70  cmp     r8d, 8
0x140008e74  jnb     short loc_140008E7D
0x140008e76  mov     eax, 0C0000206h
0x140008e7b  jmp     short loc_140008EEA
0x140008e7d  mov     [rsp+38h+Src], 0
0x140008e86  mov     eax, dword ptr cs:qword_1400051B0
0x140008e8c  mov     dword ptr [rsp+38h+Src], eax
0x140008e90  mov     eax, dword ptr cs:qword_1400051B0+4
0x140008e96  mov     dword ptr [rsp+38h+Src+4], eax
0x140008e9a  test    dil, dil
0x140008e9d  jz      short loc_140008ECB
0x140008e9f  mov     edx, r8d; Length
0x140008ea2  mov     r8d, 4; Alignment
0x140008ea8  mov     rcx, rbx; Address
0x140008eab  call    cs:__imp_ProbeForWrite
0x140008eb2  nop     dword ptr [rax+rax+00h]
0x140008eb7  test    dil, dil
0x140008eba  jz      short loc_140008ECB
0x140008ebc  mov     rdx, [rsp+38h+Src]
0x140008ec1  mov     rcx, rbx
0x140008ec4  call    RtlWriteULong64ToUser
0x140008ec9  jmp     short loc_140008EDF
0x140008ecb  mov     r8d, 8; Size
0x140008ed1  lea     rdx, [rsp+38h+Src]; Src
0x140008ed6  mov     rcx, rbx; void *
0x140008ed9  call    RtlCopyVolatileMemory
0x140008ede  nop
0x140008edf  mov     qword ptr [rsi], 8
0x140008ee6  xor     eax, eax
0x140008ee8  jmp     short $+2
0x140008eea  mov     rbx, [rsp+38h+arg_8]
0x140008eef  mov     rsi, [rsp+38h+arg_10]
0x140008ef4  add     rsp, 30h
0x140008ef8  pop     rdi
0x140008ef9  retn
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
