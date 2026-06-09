# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003d70`
- end: `0x180003de0`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007038`
- `0x180007174`

## callees

- `0x180003d70`
- `0x180006c78`
- `0x180008660`

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
0x180003d70  mov     [rsp+arg_0], rbx
0x180003d75  mov     [rsp+arg_8], rsi
0x180003d7a  push    rdi
0x180003d7b  sub     rsp, 20h
0x180003d7f  mov     rbx, r9
0x180003d82  mov     rdi, rcx
0x180003d85  cmp     rcx, rdx
0x180003d88  jz      short loc_180003DC1
0x180003d8a  test    r8, r8
0x180003d8d  jz      short loc_180003DC1
0x180003d8f  cmp     byte ptr [r8], 0
0x180003d93  jz      short loc_180003DC1
0x180003d95  mov     rcx, r8; this
0x180003d98  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003d9d  sub     rdx, rdi; DestinationSize
0x180003da0  mov     rsi, rax
0x180003da3  cmp     rdx, rax
0x180003da6  jb      short loc_180003DC1
0x180003da8  mov     r9, rax; SourceSize
0x180003dab  mov     rcx, rdi; Destination
0x180003dae  call    memcpy_s
0x180003db3  test    rbx, rbx
0x180003db6  jz      short loc_180003DBB
0x180003db8  mov     [rbx], rdi
0x180003dbb  lea     rax, [rsi+rdi]
0x180003dbf  jmp     short loc_180003DD0
0x180003dc1  test    rbx, rbx
0x180003dc4  jz      short loc_180003DCD
0x180003dc6  mov     qword ptr [r9], 0
0x180003dcd  mov     rax, rdi
0x180003dd0  mov     rbx, [rsp+28h+arg_0]
0x180003dd5  mov     rsi, [rsp+28h+arg_8]
0x180003dda  add     rsp, 20h
0x180003dde  pop     rdi
0x180003ddf  retn
```
