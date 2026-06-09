# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140004c68`
- end: `0x140004cd8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a590`
- `0x14000a7b8`

## callees

- `0x140004c68`
- `0x14000a3b8`
- `0x14000eff0`

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
0x140004c68  mov     [rsp+arg_0], rbx
0x140004c6d  mov     [rsp+arg_8], rsi
0x140004c72  push    rdi
0x140004c73  sub     rsp, 20h
0x140004c77  mov     rbx, r9
0x140004c7a  mov     rdi, rcx
0x140004c7d  cmp     rcx, rdx
0x140004c80  jz      short loc_140004CB9
0x140004c82  test    r8, r8
0x140004c85  jz      short loc_140004CB9
0x140004c87  cmp     byte ptr [r8], 0
0x140004c8b  jz      short loc_140004CB9
0x140004c8d  mov     rcx, r8; this
0x140004c90  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140004c95  sub     rdx, rdi; DestinationSize
0x140004c98  mov     rsi, rax
0x140004c9b  cmp     rdx, rax
0x140004c9e  jb      short loc_140004CB9
0x140004ca0  mov     r9, rax; SourceSize
0x140004ca3  mov     rcx, rdi; Destination
0x140004ca6  call    memcpy_s
0x140004cab  test    rbx, rbx
0x140004cae  jz      short loc_140004CB3
0x140004cb0  mov     [rbx], rdi
0x140004cb3  lea     rax, [rsi+rdi]
0x140004cb7  jmp     short loc_140004CC8
0x140004cb9  test    rbx, rbx
0x140004cbc  jz      short loc_140004CC5
0x140004cbe  mov     qword ptr [r9], 0
0x140004cc5  mov     rax, rdi
0x140004cc8  mov     rbx, [rsp+28h+arg_0]
0x140004ccd  mov     rsi, [rsp+28h+arg_8]
0x140004cd2  add     rsp, 20h
0x140004cd6  pop     rdi
0x140004cd7  retn
```
