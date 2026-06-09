# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000558c`
- end: `0x1800055fd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800088a0`
- `0x180008ac8`

## callees

- `0x18000558c`
- `0x180008710`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800055ca`
- `msvcrt!memcpy_s` at `0x1800055ca`

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
0x18000558c  mov     [rsp+arg_0], rbx
0x180005591  mov     [rsp+arg_8], rsi
0x180005596  push    rdi
0x180005597  sub     rsp, 20h
0x18000559b  mov     rbx, r9
0x18000559e  mov     rdi, rcx
0x1800055a1  cmp     rcx, rdx
0x1800055a4  jz      short loc_1800055DE
0x1800055a6  test    r8, r8
0x1800055a9  jz      short loc_1800055DE
0x1800055ab  cmp     byte ptr [r8], 0
0x1800055af  jz      short loc_1800055DE
0x1800055b1  mov     rcx, r8; this
0x1800055b4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800055b9  sub     rdx, rdi; DestinationSize
0x1800055bc  mov     rsi, rax
0x1800055bf  cmp     rdx, rax
0x1800055c2  jb      short loc_1800055DE
0x1800055c4  mov     r9, rax; SourceSize
0x1800055c7  mov     rcx, rdi; Destination
0x1800055ca  call    cs:__imp_memcpy_s
0x1800055d0  test    rbx, rbx
0x1800055d3  jz      short loc_1800055D8
0x1800055d5  mov     [rbx], rdi
0x1800055d8  lea     rax, [rsi+rdi]
0x1800055dc  jmp     short loc_1800055ED
0x1800055de  test    rbx, rbx
0x1800055e1  jz      short loc_1800055EA
0x1800055e3  mov     qword ptr [r9], 0
0x1800055ea  mov     rax, rdi
0x1800055ed  mov     rbx, [rsp+28h+arg_0]
0x1800055f2  mov     rsi, [rsp+28h+arg_8]
0x1800055f7  add     rsp, 20h
0x1800055fb  pop     rdi
0x1800055fc  retn
```
