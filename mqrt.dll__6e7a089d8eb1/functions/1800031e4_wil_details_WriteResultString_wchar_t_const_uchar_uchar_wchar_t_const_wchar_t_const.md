# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x1800031e4`
- end: `0x180003265`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006900`
- `0x180006b20`

## callees

- `0x1800031e4`
- `0x180006790`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003239`
- `msvcrt!memcpy_s` at `0x180003239`

## pseudocode

```c
wchar_t *__fastcall wil::details::WriteResultString<wchar_t const *>(
        wchar_t *Destination,
        const wchar_t *a2,
        wil::details *a3,
        wchar_t **a4)
{
  rsize_t v8; // rax
  rsize_t v9; // rbp
  rsize_t v10; // r14

  if ( Destination == a2 || !a3 || !*(_WORD *)a3 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  v8 = wil::details::ResultStringSize(a3, a2);
  v9 = (char *)a2 - (char *)Destination;
  v10 = v8;
  if ( v9 < v8 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  memcpy_s(Destination, v9, a3, v8);
  if ( a4 )
    *a4 = Destination;
  return (wchar_t *)((char *)Destination + v10);
}

```

## disassembly

```asm
0x1800031e4  push    rbx
0x1800031e6  push    rbp
0x1800031e7  push    rsi
0x1800031e8  push    rdi
0x1800031e9  push    r14
0x1800031eb  push    r15
0x1800031ed  sub     rsp, 28h
0x1800031f1  xor     r15d, r15d
0x1800031f4  mov     rbx, r9
0x1800031f7  mov     rsi, r8
0x1800031fa  mov     rbp, rdx
0x1800031fd  mov     rdi, rcx
0x180003200  cmp     rcx, rdx
0x180003203  jz      short loc_18000324D
0x180003205  test    r8, r8
0x180003208  jz      short loc_18000324D
0x18000320a  cmp     [r8], r15w
0x18000320e  jz      short loc_18000324D
0x180003210  mov     rcx, r8; this
0x180003213  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180003218  sub     rbp, rdi
0x18000321b  mov     r14, rax
0x18000321e  cmp     rbp, rax
0x180003221  jnb     short loc_18000322D
0x180003223  test    rbx, rbx
0x180003226  jz      short loc_180003255
0x180003228  mov     [rbx], r15
0x18000322b  jmp     short loc_180003255
0x18000322d  mov     r9, r14; SourceSize
0x180003230  mov     r8, rsi; Source
0x180003233  mov     rdx, rbp; DestinationSize
0x180003236  mov     rcx, rdi; Destination
0x180003239  call    cs:__imp_memcpy_s
0x18000323f  test    rbx, rbx
0x180003242  jz      short loc_180003247
0x180003244  mov     [rbx], rdi
0x180003247  lea     rax, [r14+rdi]
0x18000324b  jmp     short loc_180003258
0x18000324d  test    rbx, rbx
0x180003250  jz      short loc_180003255
0x180003252  mov     [r9], r15
0x180003255  mov     rax, rdi
0x180003258  add     rsp, 28h
0x18000325c  pop     r15
0x18000325e  pop     r14
0x180003260  pop     rdi
0x180003261  pop     rsi
0x180003262  pop     rbp
0x180003263  pop     rbx
0x180003264  retn
```
