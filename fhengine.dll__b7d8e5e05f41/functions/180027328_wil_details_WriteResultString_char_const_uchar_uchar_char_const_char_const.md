# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180027328`
- end: `0x180027399`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cfa0`
- `0x18002d1cc`

## callees

- `0x180027328`
- `0x18002ce14`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180027366`
- `msvcrt!memcpy_s` at `0x180027366`

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
0x180027328  mov     [rsp+arg_0], rbx
0x18002732d  mov     [rsp+arg_8], rsi
0x180027332  push    rdi
0x180027333  sub     rsp, 20h
0x180027337  mov     rbx, r9
0x18002733a  mov     rdi, rcx
0x18002733d  cmp     rcx, rdx
0x180027340  jz      short loc_18002737A
0x180027342  test    r8, r8
0x180027345  jz      short loc_18002737A
0x180027347  cmp     byte ptr [r8], 0
0x18002734b  jz      short loc_18002737A
0x18002734d  mov     rcx, r8; this
0x180027350  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027355  sub     rdx, rdi; DestinationSize
0x180027358  mov     rsi, rax
0x18002735b  cmp     rdx, rax
0x18002735e  jb      short loc_18002737A
0x180027360  mov     r9, rax; SourceSize
0x180027363  mov     rcx, rdi; Destination
0x180027366  call    cs:__imp_memcpy_s
0x18002736c  test    rbx, rbx
0x18002736f  jz      short loc_180027374
0x180027371  mov     [rbx], rdi
0x180027374  lea     rax, [rsi+rdi]
0x180027378  jmp     short loc_180027389
0x18002737a  test    rbx, rbx
0x18002737d  jz      short loc_180027386
0x18002737f  mov     qword ptr [r9], 0
0x180027386  mov     rax, rdi
0x180027389  mov     rbx, [rsp+28h+arg_0]
0x18002738e  mov     rsi, [rsp+28h+arg_8]
0x180027393  add     rsp, 20h
0x180027397  pop     rdi
0x180027398  retn
```
