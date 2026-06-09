# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003a40`
- end: `0x180003aa7`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008594`
- `0x180011048`

## callees

- `0x180003a40`
- `0x1800083e8`
- `0x18000a310`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x180003a40  push    rbx
0x180003a42  push    rbp
0x180003a43  push    rsi
0x180003a44  push    rdi
0x180003a45  sub     rsp, 28h
0x180003a49  xor     ebp, ebp
0x180003a4b  mov     rbx, r9
0x180003a4e  mov     r10, rdx
0x180003a51  mov     rdi, rcx
0x180003a54  cmp     rcx, rdx
0x180003a57  jz      short loc_180003A93
0x180003a59  test    r8, r8
0x180003a5c  jz      short loc_180003A93
0x180003a5e  cmp     [r8], bp
0x180003a62  jz      short loc_180003A93
0x180003a64  mov     rcx, r8; this
0x180003a67  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003a6c  sub     r10, rdi
0x180003a6f  mov     rsi, rax
0x180003a72  cmp     r10, rax
0x180003a75  jb      short loc_180003A93
0x180003a77  mov     r9, rax; SourceSize
0x180003a7a  mov     rdx, r10; DestinationSize
0x180003a7d  mov     rcx, rdi; Destination
0x180003a80  call    memcpy_s
0x180003a85  test    rbx, rbx
0x180003a88  jz      short loc_180003A8D
0x180003a8a  mov     [rbx], rdi
0x180003a8d  lea     rax, [rsi+rdi]
0x180003a91  jmp     short loc_180003A9E
0x180003a93  test    rbx, rbx
0x180003a96  jz      short loc_180003A9B
0x180003a98  mov     [r9], rbp
0x180003a9b  mov     rax, rdi
0x180003a9e  add     rsp, 28h
0x180003aa2  pop     rdi
0x180003aa3  pop     rsi
0x180003aa4  pop     rbp
0x180003aa5  pop     rbx
0x180003aa6  retn
```
