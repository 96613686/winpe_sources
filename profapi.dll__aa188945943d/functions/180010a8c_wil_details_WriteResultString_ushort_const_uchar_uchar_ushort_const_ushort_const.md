# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180010a8c`
- end: `0x180010af3`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800114c0`
- `0x1800115fc`

## callees

- `0x18000f160`
- `0x180010a8c`
- `0x180011438`

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
0x180010a8c  push    rbx
0x180010a8e  push    rbp
0x180010a8f  push    rsi
0x180010a90  push    rdi
0x180010a91  sub     rsp, 28h
0x180010a95  xor     ebp, ebp
0x180010a97  mov     rbx, r9
0x180010a9a  mov     r10, rdx
0x180010a9d  mov     rdi, rcx
0x180010aa0  cmp     rcx, rdx
0x180010aa3  jz      short loc_180010ADF
0x180010aa5  test    r8, r8
0x180010aa8  jz      short loc_180010ADF
0x180010aaa  cmp     [r8], bp
0x180010aae  jz      short loc_180010ADF
0x180010ab0  mov     rcx, r8; this
0x180010ab3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010ab8  sub     r10, rdi
0x180010abb  mov     rsi, rax
0x180010abe  cmp     r10, rax
0x180010ac1  jb      short loc_180010ADF
0x180010ac3  mov     r9, rax; SourceSize
0x180010ac6  mov     rdx, r10; DestinationSize
0x180010ac9  mov     rcx, rdi; Destination
0x180010acc  call    memcpy_s
0x180010ad1  test    rbx, rbx
0x180010ad4  jz      short loc_180010AD9
0x180010ad6  mov     [rbx], rdi
0x180010ad9  lea     rax, [rsi+rdi]
0x180010add  jmp     short loc_180010AEA
0x180010adf  test    rbx, rbx
0x180010ae2  jz      short loc_180010AE7
0x180010ae4  mov     [r9], rbp
0x180010ae7  mov     rax, rdi
0x180010aea  add     rsp, 28h
0x180010aee  pop     rdi
0x180010aef  pop     rsi
0x180010af0  pop     rbp
0x180010af1  pop     rbx
0x180010af2  retn
```
