# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180010a14`
- end: `0x180010a84`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800114c0`
- `0x1800115fc`

## callees

- `0x18000bed0`
- `0x18000f160`
- `0x180010a14`

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
0x180010a14  mov     [rsp+arg_0], rbx
0x180010a19  mov     [rsp+arg_8], rsi
0x180010a1e  push    rdi
0x180010a1f  sub     rsp, 20h
0x180010a23  mov     rbx, r9
0x180010a26  mov     rdi, rcx
0x180010a29  cmp     rcx, rdx
0x180010a2c  jz      short loc_180010A65
0x180010a2e  test    r8, r8
0x180010a31  jz      short loc_180010A65
0x180010a33  cmp     byte ptr [r8], 0
0x180010a37  jz      short loc_180010A65
0x180010a39  mov     rcx, r8; this
0x180010a3c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010a41  sub     rdx, rdi; DestinationSize
0x180010a44  mov     rsi, rax
0x180010a47  cmp     rdx, rax
0x180010a4a  jb      short loc_180010A65
0x180010a4c  mov     r9, rax; SourceSize
0x180010a4f  mov     rcx, rdi; Destination
0x180010a52  call    memcpy_s
0x180010a57  test    rbx, rbx
0x180010a5a  jz      short loc_180010A5F
0x180010a5c  mov     [rbx], rdi
0x180010a5f  lea     rax, [rsi+rdi]
0x180010a63  jmp     short loc_180010A74
0x180010a65  test    rbx, rbx
0x180010a68  jz      short loc_180010A71
0x180010a6a  mov     qword ptr [r9], 0
0x180010a71  mov     rax, rdi
0x180010a74  mov     rbx, [rsp+28h+arg_0]
0x180010a79  mov     rsi, [rsp+28h+arg_8]
0x180010a7e  add     rsp, 20h
0x180010a82  pop     rdi
0x180010a83  retn
```
