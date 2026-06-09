# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140004028`
- end: `0x140004099`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009710`
- `0x14000996c`

## callees

- `0x140004028`
- `0x140009580`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140004066`
- `msvcrt!memcpy_s` at `0x140004066`

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
0x140004028  mov     [rsp+arg_0], rbx
0x14000402d  mov     [rsp+arg_8], rsi
0x140004032  push    rdi
0x140004033  sub     rsp, 20h
0x140004037  mov     rbx, r9
0x14000403a  mov     rdi, rcx
0x14000403d  cmp     rcx, rdx
0x140004040  jz      short loc_14000407A
0x140004042  test    r8, r8
0x140004045  jz      short loc_14000407A
0x140004047  cmp     byte ptr [r8], 0
0x14000404b  jz      short loc_14000407A
0x14000404d  mov     rcx, r8; this
0x140004050  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004055  sub     rdx, rdi; DestinationSize
0x140004058  mov     rsi, rax
0x14000405b  cmp     rdx, rax
0x14000405e  jb      short loc_14000407A
0x140004060  mov     r9, rax; SourceSize
0x140004063  mov     rcx, rdi; Destination
0x140004066  call    cs:__imp_memcpy_s
0x14000406c  test    rbx, rbx
0x14000406f  jz      short loc_140004074
0x140004071  mov     [rbx], rdi
0x140004074  lea     rax, [rsi+rdi]
0x140004078  jmp     short loc_140004089
0x14000407a  test    rbx, rbx
0x14000407d  jz      short loc_140004086
0x14000407f  mov     qword ptr [r9], 0
0x140004086  mov     rax, rdi
0x140004089  mov     rbx, [rsp+28h+arg_0]
0x14000408e  mov     rsi, [rsp+28h+arg_8]
0x140004093  add     rsp, 20h
0x140004097  pop     rdi
0x140004098  retn
```
