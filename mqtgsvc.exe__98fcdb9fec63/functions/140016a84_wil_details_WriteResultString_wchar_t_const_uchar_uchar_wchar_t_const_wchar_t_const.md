# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x140016a84`
- end: `0x140016b05`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `129`
- prototype: `wchar_t *__fastcall(wchar_t *Destination, const wchar_t *, wil::details *, wchar_t **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a460`
- `0x14001a680`

## callees

- `0x140016a84`
- `0x14001a2f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016ad9`
- `msvcrt!memcpy_s` at `0x140016ad9`

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
0x140016a84  push    rbx
0x140016a86  push    rbp
0x140016a87  push    rsi
0x140016a88  push    rdi
0x140016a89  push    r14
0x140016a8b  push    r15
0x140016a8d  sub     rsp, 28h
0x140016a91  xor     r15d, r15d
0x140016a94  mov     rbx, r9
0x140016a97  mov     rsi, r8
0x140016a9a  mov     rbp, rdx
0x140016a9d  mov     rdi, rcx
0x140016aa0  cmp     rcx, rdx
0x140016aa3  jz      short loc_140016AED
0x140016aa5  test    r8, r8
0x140016aa8  jz      short loc_140016AED
0x140016aaa  cmp     [r8], r15w
0x140016aae  jz      short loc_140016AED
0x140016ab0  mov     rcx, r8; this
0x140016ab3  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x140016ab8  sub     rbp, rdi
0x140016abb  mov     r14, rax
0x140016abe  cmp     rbp, rax
0x140016ac1  jnb     short loc_140016ACD
0x140016ac3  test    rbx, rbx
0x140016ac6  jz      short loc_140016AF5
0x140016ac8  mov     [rbx], r15
0x140016acb  jmp     short loc_140016AF5
0x140016acd  mov     r9, r14; SourceSize
0x140016ad0  mov     r8, rsi; Source
0x140016ad3  mov     rdx, rbp; DestinationSize
0x140016ad6  mov     rcx, rdi; Destination
0x140016ad9  call    cs:__imp_memcpy_s
0x140016adf  test    rbx, rbx
0x140016ae2  jz      short loc_140016AE7
0x140016ae4  mov     [rbx], rdi
0x140016ae7  lea     rax, [r14+rdi]
0x140016aeb  jmp     short loc_140016AF8
0x140016aed  test    rbx, rbx
0x140016af0  jz      short loc_140016AF5
0x140016af2  mov     [r9], r15
0x140016af5  mov     rax, rdi
0x140016af8  add     rsp, 28h
0x140016afc  pop     r15
0x140016afe  pop     r14
0x140016b00  pop     rdi
0x140016b01  pop     rsi
0x140016b02  pop     rbp
0x140016b03  pop     rbx
0x140016b04  retn
```
