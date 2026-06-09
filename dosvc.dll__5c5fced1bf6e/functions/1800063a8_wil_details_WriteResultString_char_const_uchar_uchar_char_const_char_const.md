# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800063a8`
- end: `0x180006418`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007a4c`
- `0x180007b88`

## callees

- `0x180002e70`
- `0x1800063a8`
- `0x18000799c`

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
    memcpy_s_0(Destination, v9, v7, v6);
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
0x1800063a8  mov     [rsp+arg_0], rbx
0x1800063ad  mov     [rsp+arg_8], rsi
0x1800063b2  push    rdi
0x1800063b3  sub     rsp, 20h
0x1800063b7  mov     rbx, r9
0x1800063ba  mov     rdi, rcx
0x1800063bd  cmp     rcx, rdx
0x1800063c0  jz      short loc_1800063F9
0x1800063c2  test    r8, r8
0x1800063c5  jz      short loc_1800063F9
0x1800063c7  cmp     byte ptr [r8], 0
0x1800063cb  jz      short loc_1800063F9
0x1800063cd  mov     rcx, r8; this
0x1800063d0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800063d5  sub     rdx, rdi; DestinationSize
0x1800063d8  mov     rsi, rax
0x1800063db  cmp     rdx, rax
0x1800063de  jb      short loc_1800063F9
0x1800063e0  mov     r9, rax; SourceSize
0x1800063e3  mov     rcx, rdi; Destination
0x1800063e6  call    memcpy_s_0
0x1800063eb  test    rbx, rbx
0x1800063ee  jz      short loc_1800063F3
0x1800063f0  mov     [rbx], rdi
0x1800063f3  lea     rax, [rsi+rdi]
0x1800063f7  jmp     short loc_180006408
0x1800063f9  test    rbx, rbx
0x1800063fc  jz      short loc_180006405
0x1800063fe  mov     qword ptr [r9], 0
0x180006405  mov     rax, rdi
0x180006408  mov     rbx, [rsp+28h+arg_0]
0x18000640d  mov     rsi, [rsp+28h+arg_8]
0x180006412  add     rsp, 20h
0x180006416  pop     rdi
0x180006417  retn
```
