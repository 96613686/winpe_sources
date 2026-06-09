# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800039c8`
- end: `0x180003a38`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008594`
- `0x180011048`

## callees

- `0x1800039c8`
- `0x1800083c8`
- `0x18000a310`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x1800039c8  mov     [rsp+arg_0], rbx
0x1800039cd  mov     [rsp+arg_8], rsi
0x1800039d2  push    rdi
0x1800039d3  sub     rsp, 20h
0x1800039d7  mov     rbx, r9
0x1800039da  mov     rdi, rcx
0x1800039dd  cmp     rcx, rdx
0x1800039e0  jz      short loc_180003A19
0x1800039e2  test    r8, r8
0x1800039e5  jz      short loc_180003A19
0x1800039e7  cmp     byte ptr [r8], 0
0x1800039eb  jz      short loc_180003A19
0x1800039ed  mov     rcx, r8; this
0x1800039f0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800039f5  sub     rdx, rdi; DestinationSize
0x1800039f8  mov     rsi, rax
0x1800039fb  cmp     rdx, rax
0x1800039fe  jb      short loc_180003A19
0x180003a00  mov     r9, rax; SourceSize
0x180003a03  mov     rcx, rdi; Destination
0x180003a06  call    memcpy_s
0x180003a0b  test    rbx, rbx
0x180003a0e  jz      short loc_180003A13
0x180003a10  mov     [rbx], rdi
0x180003a13  lea     rax, [rsi+rdi]
0x180003a17  jmp     short loc_180003A28
0x180003a19  test    rbx, rbx
0x180003a1c  jz      short loc_180003A25
0x180003a1e  mov     qword ptr [r9], 0
0x180003a25  mov     rax, rdi
0x180003a28  mov     rbx, [rsp+28h+arg_0]
0x180003a2d  mov     rsi, [rsp+28h+arg_8]
0x180003a32  add     rsp, 20h
0x180003a36  pop     rdi
0x180003a37  retn
```
