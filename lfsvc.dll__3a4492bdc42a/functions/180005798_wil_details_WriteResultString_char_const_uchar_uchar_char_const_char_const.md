# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180005798`
- end: `0x180005808`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ca0`
- `0x180008ec8`

## callees

- `0x180003404`
- `0x180005798`
- `0x180008a70`

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
0x180005798  mov     [rsp+arg_0], rbx
0x18000579d  mov     [rsp+arg_8], rsi
0x1800057a2  push    rdi
0x1800057a3  sub     rsp, 20h
0x1800057a7  mov     rbx, r9
0x1800057aa  mov     rdi, rcx
0x1800057ad  cmp     rcx, rdx
0x1800057b0  jz      short loc_1800057E9
0x1800057b2  test    r8, r8
0x1800057b5  jz      short loc_1800057E9
0x1800057b7  cmp     byte ptr [r8], 0
0x1800057bb  jz      short loc_1800057E9
0x1800057bd  mov     rcx, r8; this
0x1800057c0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800057c5  sub     rdx, rdi; DestinationSize
0x1800057c8  mov     rsi, rax
0x1800057cb  cmp     rdx, rax
0x1800057ce  jb      short loc_1800057E9
0x1800057d0  mov     r9, rax; SourceSize
0x1800057d3  mov     rcx, rdi; Destination
0x1800057d6  call    memcpy_s
0x1800057db  test    rbx, rbx
0x1800057de  jz      short loc_1800057E3
0x1800057e0  mov     [rbx], rdi
0x1800057e3  lea     rax, [rsi+rdi]
0x1800057e7  jmp     short loc_1800057F8
0x1800057e9  test    rbx, rbx
0x1800057ec  jz      short loc_1800057F5
0x1800057ee  mov     qword ptr [r9], 0
0x1800057f5  mov     rax, rdi
0x1800057f8  mov     rbx, [rsp+28h+arg_0]
0x1800057fd  mov     rsi, [rsp+28h+arg_8]
0x180005802  add     rsp, 20h
0x180005806  pop     rdi
0x180005807  retn
```
