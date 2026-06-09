# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x18001c378`
- end: `0x18001c3e8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d7d4`

## callees

- `0x18000e10c`
- `0x18001c378`
- `0x18001d778`

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
    memcpy_s_0(Destination, v9, v7, v6);
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
0x18001c378  mov     [rsp+arg_0], rbx
0x18001c37d  mov     [rsp+arg_8], rsi
0x18001c382  push    rdi
0x18001c383  sub     rsp, 20h
0x18001c387  mov     rbx, r9
0x18001c38a  mov     rdi, rcx
0x18001c38d  cmp     rcx, rdx
0x18001c390  jz      short loc_18001C3C9
0x18001c392  test    r8, r8
0x18001c395  jz      short loc_18001C3C9
0x18001c397  cmp     byte ptr [r8], 0
0x18001c39b  jz      short loc_18001C3C9
0x18001c39d  mov     rcx, r8; this
0x18001c3a0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001c3a5  sub     rdx, rdi; DestinationSize
0x18001c3a8  mov     rsi, rax
0x18001c3ab  cmp     rdx, rax
0x18001c3ae  jb      short loc_18001C3C9
0x18001c3b0  mov     r9, rax; SourceSize
0x18001c3b3  mov     rcx, rdi; Destination
0x18001c3b6  call    memcpy_s_0
0x18001c3bb  test    rbx, rbx
0x18001c3be  jz      short loc_18001C3C3
0x18001c3c0  mov     [rbx], rdi
0x18001c3c3  lea     rax, [rsi+rdi]
0x18001c3c7  jmp     short loc_18001C3D8
0x18001c3c9  test    rbx, rbx
0x18001c3cc  jz      short loc_18001C3D5
0x18001c3ce  mov     qword ptr [r9], 0
0x18001c3d5  mov     rax, rdi
0x18001c3d8  mov     rbx, [rsp+28h+arg_0]
0x18001c3dd  mov     rsi, [rsp+28h+arg_8]
0x18001c3e2  add     rsp, 20h
0x18001c3e6  pop     rdi
0x18001c3e7  retn
```
