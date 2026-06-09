# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18000634c`
- end: `0x1800063c4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007cb0`

## callees

- `0x18000634c`
- `0x180007bd4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000638a`
- `msvcrt!memcpy_s` at `0x18000638a`

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
0x18000634c  mov     [rsp+arg_0], rbx
0x180006351  mov     [rsp+arg_8], rsi
0x180006356  push    rdi
0x180006357  sub     rsp, 20h
0x18000635b  mov     rbx, r9
0x18000635e  mov     rdi, rcx
0x180006361  cmp     rcx, rdx
0x180006364  jz      short loc_1800063A4
0x180006366  test    r8, r8
0x180006369  jz      short loc_1800063A4
0x18000636b  cmp     byte ptr [r8], 0
0x18000636f  jz      short loc_1800063A4
0x180006371  mov     rcx, r8; this
0x180006374  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006379  sub     rdx, rdi; DestinationSize
0x18000637c  mov     rsi, rax
0x18000637f  cmp     rdx, rax
0x180006382  jb      short loc_1800063A4
0x180006384  mov     r9, rax; SourceSize
0x180006387  mov     rcx, rdi; Destination
0x18000638a  call    cs:__imp_memcpy_s
0x180006391  nop     dword ptr [rax+rax+00h]
0x180006396  test    rbx, rbx
0x180006399  jz      short loc_18000639E
0x18000639b  mov     [rbx], rdi
0x18000639e  lea     rax, [rsi+rdi]
0x1800063a2  jmp     short loc_1800063B3
0x1800063a4  test    rbx, rbx
0x1800063a7  jz      short loc_1800063B0
0x1800063a9  mov     qword ptr [r9], 0
0x1800063b0  mov     rax, rdi
0x1800063b3  mov     rbx, [rsp+28h+arg_0]
0x1800063b8  mov     rsi, [rsp+28h+arg_8]
0x1800063bd  add     rsp, 20h
0x1800063c1  pop     rdi
0x1800063c2  retn
```
