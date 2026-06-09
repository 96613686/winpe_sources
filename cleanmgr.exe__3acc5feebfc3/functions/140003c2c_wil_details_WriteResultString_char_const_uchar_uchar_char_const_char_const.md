# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140003c2c`
- end: `0x140003c9c`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005ab4`
- `0x140005bf0`

## callees

- `0x140003c2c`
- `0x140005948`
- `0x1400069a8`

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
0x140003c2c  mov     [rsp+arg_0], rbx
0x140003c31  mov     [rsp+arg_8], rsi
0x140003c36  push    rdi
0x140003c37  sub     rsp, 20h
0x140003c3b  mov     rbx, r9
0x140003c3e  mov     rdi, rcx
0x140003c41  cmp     rcx, rdx
0x140003c44  jz      short loc_140003C7D
0x140003c46  test    r8, r8
0x140003c49  jz      short loc_140003C7D
0x140003c4b  cmp     byte ptr [r8], 0
0x140003c4f  jz      short loc_140003C7D
0x140003c51  mov     rcx, r8; this
0x140003c54  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140003c59  sub     rdx, rdi; DestinationSize
0x140003c5c  mov     rsi, rax
0x140003c5f  cmp     rdx, rax
0x140003c62  jb      short loc_140003C7D
0x140003c64  mov     r9, rax; SourceSize
0x140003c67  mov     rcx, rdi; Destination
0x140003c6a  call    memcpy_s
0x140003c6f  test    rbx, rbx
0x140003c72  jz      short loc_140003C77
0x140003c74  mov     [rbx], rdi
0x140003c77  lea     rax, [rsi+rdi]
0x140003c7b  jmp     short loc_140003C8C
0x140003c7d  test    rbx, rbx
0x140003c80  jz      short loc_140003C89
0x140003c82  mov     qword ptr [r9], 0
0x140003c89  mov     rax, rdi
0x140003c8c  mov     rbx, [rsp+28h+arg_0]
0x140003c91  mov     rsi, [rsp+28h+arg_8]
0x140003c96  add     rsp, 20h
0x140003c9a  pop     rdi
0x140003c9b  retn
```
