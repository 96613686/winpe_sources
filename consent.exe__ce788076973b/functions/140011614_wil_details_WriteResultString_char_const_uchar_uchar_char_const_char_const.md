# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140011614`
- end: `0x140011685`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013070`
- `0x1400131ac`

## callees

- `0x140011614`
- `0x140012f88`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011652`
- `msvcrt!memcpy_s` at `0x140011652`

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
0x140011614  mov     [rsp+arg_0], rbx
0x140011619  mov     [rsp+arg_8], rsi
0x14001161e  push    rdi
0x14001161f  sub     rsp, 20h
0x140011623  mov     rbx, r9
0x140011626  mov     rdi, rcx
0x140011629  cmp     rcx, rdx
0x14001162c  jz      short loc_140011666
0x14001162e  test    r8, r8
0x140011631  jz      short loc_140011666
0x140011633  cmp     byte ptr [r8], 0
0x140011637  jz      short loc_140011666
0x140011639  mov     rcx, r8; this
0x14001163c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140011641  sub     rdx, rdi; DestinationSize
0x140011644  mov     rsi, rax
0x140011647  cmp     rdx, rax
0x14001164a  jb      short loc_140011666
0x14001164c  mov     r9, rax; SourceSize
0x14001164f  mov     rcx, rdi; Destination
0x140011652  call    cs:__imp_memcpy_s
0x140011658  test    rbx, rbx
0x14001165b  jz      short loc_140011660
0x14001165d  mov     [rbx], rdi
0x140011660  lea     rax, [rsi+rdi]
0x140011664  jmp     short loc_140011675
0x140011666  test    rbx, rbx
0x140011669  jz      short loc_140011672
0x14001166b  mov     qword ptr [r9], 0
0x140011672  mov     rax, rdi
0x140011675  mov     rbx, [rsp+28h+arg_0]
0x14001167a  mov     rsi, [rsp+28h+arg_8]
0x14001167f  add     rsp, 20h
0x140011683  pop     rdi
0x140011684  retn
```
