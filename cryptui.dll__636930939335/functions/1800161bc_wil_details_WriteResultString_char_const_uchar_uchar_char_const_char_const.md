# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800161bc`
- end: `0x18001622d`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bc80`
- `0x18001bea8`

## callees

- `0x1800161bc`
- `0x18001baf0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800161fa`
- `msvcrt!memcpy_s` at `0x1800161fa`

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
0x1800161bc  mov     [rsp+arg_0], rbx
0x1800161c1  mov     [rsp+arg_8], rsi
0x1800161c6  push    rdi
0x1800161c7  sub     rsp, 20h
0x1800161cb  mov     rbx, r9
0x1800161ce  mov     rdi, rcx
0x1800161d1  cmp     rcx, rdx
0x1800161d4  jz      short loc_18001620E
0x1800161d6  test    r8, r8
0x1800161d9  jz      short loc_18001620E
0x1800161db  cmp     byte ptr [r8], 0
0x1800161df  jz      short loc_18001620E
0x1800161e1  mov     rcx, r8; this
0x1800161e4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800161e9  sub     rdx, rdi; DestinationSize
0x1800161ec  mov     rsi, rax
0x1800161ef  cmp     rdx, rax
0x1800161f2  jb      short loc_18001620E
0x1800161f4  mov     r9, rax; SourceSize
0x1800161f7  mov     rcx, rdi; Destination
0x1800161fa  call    cs:__imp_memcpy_s
0x180016200  test    rbx, rbx
0x180016203  jz      short loc_180016208
0x180016205  mov     [rbx], rdi
0x180016208  lea     rax, [rsi+rdi]
0x18001620c  jmp     short loc_18001621D
0x18001620e  test    rbx, rbx
0x180016211  jz      short loc_18001621A
0x180016213  mov     qword ptr [r9], 0
0x18001621a  mov     rax, rdi
0x18001621d  mov     rbx, [rsp+28h+arg_0]
0x180016222  mov     rsi, [rsp+28h+arg_8]
0x180016227  add     rsp, 20h
0x18001622b  pop     rdi
0x18001622c  retn
```
