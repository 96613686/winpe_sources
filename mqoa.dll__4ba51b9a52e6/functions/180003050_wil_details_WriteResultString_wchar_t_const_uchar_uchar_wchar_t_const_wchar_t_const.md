# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180003050`
- end: `0x1800030b8`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006f10`
- `0x180007138`

## callees

- `0x180003050`
- `0x180006da0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003090`
- `msvcrt!memcpy_s` at `0x180003090`

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
0x180003050  push    rbx
0x180003052  push    rbp
0x180003053  push    rsi
0x180003054  push    rdi
0x180003055  sub     rsp, 28h
0x180003059  xor     ebp, ebp
0x18000305b  mov     rbx, r9
0x18000305e  mov     r10, rdx
0x180003061  mov     rdi, rcx
0x180003064  cmp     rcx, rdx
0x180003067  jz      short loc_1800030A4
0x180003069  test    r8, r8
0x18000306c  jz      short loc_1800030A4
0x18000306e  cmp     [r8], bp
0x180003072  jz      short loc_1800030A4
0x180003074  mov     rcx, r8; this
0x180003077  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18000307c  sub     r10, rdi
0x18000307f  mov     rsi, rax
0x180003082  cmp     r10, rax
0x180003085  jb      short loc_1800030A4
0x180003087  mov     r9, rax; SourceSize
0x18000308a  mov     rdx, r10; DestinationSize
0x18000308d  mov     rcx, rdi; Destination
0x180003090  call    cs:__imp_memcpy_s
0x180003096  test    rbx, rbx
0x180003099  jz      short loc_18000309E
0x18000309b  mov     [rbx], rdi
0x18000309e  lea     rax, [rsi+rdi]
0x1800030a2  jmp     short loc_1800030AF
0x1800030a4  test    rbx, rbx
0x1800030a7  jz      short loc_1800030AC
0x1800030a9  mov     [r9], rbp
0x1800030ac  mov     rax, rdi
0x1800030af  add     rsp, 28h
0x1800030b3  pop     rdi
0x1800030b4  pop     rsi
0x1800030b5  pop     rbp
0x1800030b6  pop     rbx
0x1800030b7  retn
```
