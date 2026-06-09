# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180004c44`
- end: `0x180004cb4`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800057c0`
- `0x18000afc0`

## callees

- `0x180004c44`
- `0x1800056d4`
- `0x180006094`

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
0x180004c44  mov     [rsp+arg_0], rbx
0x180004c49  mov     [rsp+arg_8], rsi
0x180004c4e  push    rdi
0x180004c4f  sub     rsp, 20h
0x180004c53  mov     rbx, r9
0x180004c56  mov     rdi, rcx
0x180004c59  cmp     rcx, rdx
0x180004c5c  jz      short loc_180004C95
0x180004c5e  test    r8, r8
0x180004c61  jz      short loc_180004C95
0x180004c63  cmp     byte ptr [r8], 0
0x180004c67  jz      short loc_180004C95
0x180004c69  mov     rcx, r8; this
0x180004c6c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004c71  sub     rdx, rdi; DestinationSize
0x180004c74  mov     rsi, rax
0x180004c77  cmp     rdx, rax
0x180004c7a  jb      short loc_180004C95
0x180004c7c  mov     r9, rax; SourceSize
0x180004c7f  mov     rcx, rdi; Destination
0x180004c82  call    memcpy_s
0x180004c87  test    rbx, rbx
0x180004c8a  jz      short loc_180004C8F
0x180004c8c  mov     [rbx], rdi
0x180004c8f  lea     rax, [rsi+rdi]
0x180004c93  jmp     short loc_180004CA4
0x180004c95  test    rbx, rbx
0x180004c98  jz      short loc_180004CA1
0x180004c9a  mov     qword ptr [r9], 0
0x180004ca1  mov     rax, rdi
0x180004ca4  mov     rbx, [rsp+28h+arg_0]
0x180004ca9  mov     rsi, [rsp+28h+arg_8]
0x180004cae  add     rsp, 20h
0x180004cb2  pop     rdi
0x180004cb3  retn
```
