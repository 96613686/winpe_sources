# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180003924`
- end: `0x18000398c`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180005954`
- `0x180005aa0`

## callees

- `0x180003924`
- `0x18000583c`
- `0x180006710`

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
0x180003924  push    rbx
0x180003926  push    rbp
0x180003927  push    rsi
0x180003928  push    rdi
0x180003929  sub     rsp, 28h
0x18000392d  xor     ebp, ebp
0x18000392f  mov     rbx, r9
0x180003932  mov     r10, rdx
0x180003935  mov     rdi, rcx
0x180003938  cmp     rcx, rdx
0x18000393b  jz      short loc_180003977
0x18000393d  test    r8, r8
0x180003940  jz      short loc_180003977
0x180003942  cmp     [r8], bp
0x180003946  jz      short loc_180003977
0x180003948  mov     rcx, r8; this
0x18000394b  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180003950  sub     r10, rdi
0x180003953  mov     rsi, rax
0x180003956  cmp     r10, rax
0x180003959  jb      short loc_180003977
0x18000395b  mov     r9, rax; SourceSize
0x18000395e  mov     rdx, r10; DestinationSize
0x180003961  mov     rcx, rdi; Destination
0x180003964  call    memcpy_s
0x180003969  test    rbx, rbx
0x18000396c  jz      short loc_180003971
0x18000396e  mov     [rbx], rdi
0x180003971  lea     rax, [rsi+rdi]
0x180003975  jmp     short loc_180003982
0x180003977  test    rbx, rbx
0x18000397a  jz      short loc_18000397F
0x18000397c  mov     [r9], rbp
0x18000397f  mov     rax, rdi
0x180003982  add     rsp, 28h
0x180003986  pop     rdi
0x180003987  pop     rsi
0x180003988  pop     rbp
0x180003989  pop     rbx
0x18000398a  retn
```
