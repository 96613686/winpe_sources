# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180005590`
- end: `0x180005611`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009940`
- `0x180009b64`

## callees

- `0x180005590`
- `0x1800097d8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800055e5`
- `msvcrt!memcpy_s` at `0x1800055e5`

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
0x180005590  push    rbx
0x180005592  push    rbp
0x180005593  push    rsi
0x180005594  push    rdi
0x180005595  push    r14
0x180005597  push    r15
0x180005599  sub     rsp, 28h
0x18000559d  xor     r15d, r15d
0x1800055a0  mov     rbx, r9
0x1800055a3  mov     rsi, r8
0x1800055a6  mov     rbp, rdx
0x1800055a9  mov     rdi, rcx
0x1800055ac  cmp     rcx, rdx
0x1800055af  jz      short loc_1800055F9
0x1800055b1  test    r8, r8
0x1800055b4  jz      short loc_1800055F9
0x1800055b6  cmp     [r8], r15w
0x1800055ba  jz      short loc_1800055F9
0x1800055bc  mov     rcx, r8; this
0x1800055bf  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x1800055c4  sub     rbp, rdi
0x1800055c7  mov     r14, rax
0x1800055ca  cmp     rbp, rax
0x1800055cd  jnb     short loc_1800055D9
0x1800055cf  test    rbx, rbx
0x1800055d2  jz      short loc_180005601
0x1800055d4  mov     [rbx], r15
0x1800055d7  jmp     short loc_180005601
0x1800055d9  mov     r9, r14; SourceSize
0x1800055dc  mov     r8, rsi; Source
0x1800055df  mov     rdx, rbp; DestinationSize
0x1800055e2  mov     rcx, rdi; Destination
0x1800055e5  call    cs:__imp_memcpy_s
0x1800055eb  test    rbx, rbx
0x1800055ee  jz      short loc_1800055F3
0x1800055f0  mov     [rbx], rdi
0x1800055f3  lea     rax, [r14+rdi]
0x1800055f7  jmp     short loc_180005604
0x1800055f9  test    rbx, rbx
0x1800055fc  jz      short loc_180005601
0x1800055fe  mov     [r9], r15
0x180005601  mov     rax, rdi
0x180005604  add     rsp, 28h
0x180005608  pop     r15
0x18000560a  pop     r14
0x18000560c  pop     rdi
0x18000560d  pop     rsi
0x18000560e  pop     rbp
0x18000560f  pop     rbx
0x180005610  retn
```
