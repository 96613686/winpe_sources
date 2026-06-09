# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180015a50`
- end: `0x180015ab7`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800194e0`
- `0x18001970c`

## callees

- `0x180015a50`
- `0x180019398`
- `0x18001aea4`

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
0x180015a50  push    rbx
0x180015a52  push    rbp
0x180015a53  push    rsi
0x180015a54  push    rdi
0x180015a55  sub     rsp, 28h
0x180015a59  xor     ebp, ebp
0x180015a5b  mov     rbx, r9
0x180015a5e  mov     r10, rdx
0x180015a61  mov     rdi, rcx
0x180015a64  cmp     rcx, rdx
0x180015a67  jz      short loc_180015AA3
0x180015a69  test    r8, r8
0x180015a6c  jz      short loc_180015AA3
0x180015a6e  cmp     [r8], bp
0x180015a72  jz      short loc_180015AA3
0x180015a74  mov     rcx, r8; this
0x180015a77  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180015a7c  sub     r10, rdi
0x180015a7f  mov     rsi, rax
0x180015a82  cmp     r10, rax
0x180015a85  jb      short loc_180015AA3
0x180015a87  mov     r9, rax; SourceSize
0x180015a8a  mov     rdx, r10; DestinationSize
0x180015a8d  mov     rcx, rdi; Destination
0x180015a90  call    memcpy_s
0x180015a95  test    rbx, rbx
0x180015a98  jz      short loc_180015A9D
0x180015a9a  mov     [rbx], rdi
0x180015a9d  lea     rax, [rsi+rdi]
0x180015aa1  jmp     short loc_180015AAE
0x180015aa3  test    rbx, rbx
0x180015aa6  jz      short loc_180015AAB
0x180015aa8  mov     [r9], rbp
0x180015aab  mov     rax, rdi
0x180015aae  add     rsp, 28h
0x180015ab2  pop     rdi
0x180015ab3  pop     rsi
0x180015ab4  pop     rbp
0x180015ab5  pop     rbx
0x180015ab6  retn
```
