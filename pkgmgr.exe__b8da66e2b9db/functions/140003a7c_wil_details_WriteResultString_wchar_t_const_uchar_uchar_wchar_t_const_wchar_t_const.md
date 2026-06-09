# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x140003a7c`
- end: `0x140003ae3`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `103`
- prototype: `char *__fastcall(wchar_t *Destination, const wchar_t *, wil::details *, wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000577c`
- `0x1400058b8`

## callees

- `0x140003a7c`
- `0x140005648`
- `0x1400066d8`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<wchar_t const *>(
        wchar_t *Destination,
        const wchar_t *a2,
        wil::details *a3,
        wchar_t **a4)
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
0x140003a7c  push    rbx
0x140003a7e  push    rbp
0x140003a7f  push    rsi
0x140003a80  push    rdi
0x140003a81  sub     rsp, 28h
0x140003a85  xor     ebp, ebp
0x140003a87  mov     rbx, r9
0x140003a8a  mov     r10, rdx
0x140003a8d  mov     rdi, rcx
0x140003a90  cmp     rcx, rdx
0x140003a93  jz      short loc_140003ACF
0x140003a95  test    r8, r8
0x140003a98  jz      short loc_140003ACF
0x140003a9a  cmp     [r8], bp
0x140003a9e  jz      short loc_140003ACF
0x140003aa0  mov     rcx, r8; this
0x140003aa3  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x140003aa8  sub     r10, rdi
0x140003aab  mov     rsi, rax
0x140003aae  cmp     r10, rax
0x140003ab1  jb      short loc_140003ACF
0x140003ab3  mov     r9, rax; SourceSize
0x140003ab6  mov     rdx, r10; DestinationSize
0x140003ab9  mov     rcx, rdi; Destination
0x140003abc  call    memcpy_s
0x140003ac1  test    rbx, rbx
0x140003ac4  jz      short loc_140003AC9
0x140003ac6  mov     [rbx], rdi
0x140003ac9  lea     rax, [rsi+rdi]
0x140003acd  jmp     short loc_140003ADA
0x140003acf  test    rbx, rbx
0x140003ad2  jz      short loc_140003AD7
0x140003ad4  mov     [r9], rbp
0x140003ad7  mov     rax, rdi
0x140003ada  add     rsp, 28h
0x140003ade  pop     rdi
0x140003adf  pop     rsi
0x140003ae0  pop     rbp
0x140003ae1  pop     rbx
0x140003ae2  retn
```
