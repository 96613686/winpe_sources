# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180006a84`
- end: `0x180006aeb`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800087fc`
- `0x180008938`

## callees

- `0x180006a84`
- `0x180008738`
- `0x180009580`

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
0x180006a84  push    rbx
0x180006a86  push    rbp
0x180006a87  push    rsi
0x180006a88  push    rdi
0x180006a89  sub     rsp, 28h
0x180006a8d  xor     ebp, ebp
0x180006a8f  mov     rbx, r9
0x180006a92  mov     r10, rdx
0x180006a95  mov     rdi, rcx
0x180006a98  cmp     rcx, rdx
0x180006a9b  jz      short loc_180006AD7
0x180006a9d  test    r8, r8
0x180006aa0  jz      short loc_180006AD7
0x180006aa2  cmp     [r8], bp
0x180006aa6  jz      short loc_180006AD7
0x180006aa8  mov     rcx, r8; this
0x180006aab  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006ab0  sub     r10, rdi
0x180006ab3  mov     rsi, rax
0x180006ab6  cmp     r10, rax
0x180006ab9  jb      short loc_180006AD7
0x180006abb  mov     r9, rax; SourceSize
0x180006abe  mov     rdx, r10; DestinationSize
0x180006ac1  mov     rcx, rdi; Destination
0x180006ac4  call    memcpy_s
0x180006ac9  test    rbx, rbx
0x180006acc  jz      short loc_180006AD1
0x180006ace  mov     [rbx], rdi
0x180006ad1  lea     rax, [rsi+rdi]
0x180006ad5  jmp     short loc_180006AE2
0x180006ad7  test    rbx, rbx
0x180006ada  jz      short loc_180006ADF
0x180006adc  mov     [r9], rbp
0x180006adf  mov     rax, rdi
0x180006ae2  add     rsp, 28h
0x180006ae6  pop     rdi
0x180006ae7  pop     rsi
0x180006ae8  pop     rbp
0x180006ae9  pop     rbx
0x180006aea  retn
```
