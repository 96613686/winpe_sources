# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140003a04`
- end: `0x140003a74`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000577c`
- `0x1400058b8`

## callees

- `0x140003a04`
- `0x140005628`
- `0x1400066d8`

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
0x140003a04  mov     [rsp+arg_0], rbx
0x140003a09  mov     [rsp+arg_8], rsi
0x140003a0e  push    rdi
0x140003a0f  sub     rsp, 20h
0x140003a13  mov     rbx, r9
0x140003a16  mov     rdi, rcx
0x140003a19  cmp     rcx, rdx
0x140003a1c  jz      short loc_140003A55
0x140003a1e  test    r8, r8
0x140003a21  jz      short loc_140003A55
0x140003a23  cmp     byte ptr [r8], 0
0x140003a27  jz      short loc_140003A55
0x140003a29  mov     rcx, r8; this
0x140003a2c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140003a31  sub     rdx, rdi; DestinationSize
0x140003a34  mov     rsi, rax
0x140003a37  cmp     rdx, rax
0x140003a3a  jb      short loc_140003A55
0x140003a3c  mov     r9, rax; SourceSize
0x140003a3f  mov     rcx, rdi; Destination
0x140003a42  call    memcpy_s
0x140003a47  test    rbx, rbx
0x140003a4a  jz      short loc_140003A4F
0x140003a4c  mov     [rbx], rdi
0x140003a4f  lea     rax, [rsi+rdi]
0x140003a53  jmp     short loc_140003A64
0x140003a55  test    rbx, rbx
0x140003a58  jz      short loc_140003A61
0x140003a5a  mov     qword ptr [r9], 0
0x140003a61  mov     rax, rdi
0x140003a64  mov     rbx, [rsp+28h+arg_0]
0x140003a69  mov     rsi, [rsp+28h+arg_8]
0x140003a6e  add     rsp, 20h
0x140003a72  pop     rdi
0x140003a73  retn
```
