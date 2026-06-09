# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180003538`
- end: `0x1800035a8`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000558c`
- `0x1800056c8`

## callees

- `0x180003538`
- `0x1800054a8`
- `0x180006440`

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
0x180003538  mov     [rsp+arg_0], rbx
0x18000353d  mov     [rsp+arg_8], rsi
0x180003542  push    rdi
0x180003543  sub     rsp, 20h
0x180003547  mov     rbx, r9
0x18000354a  mov     rdi, rcx
0x18000354d  cmp     rcx, rdx
0x180003550  jz      short loc_180003589
0x180003552  test    r8, r8
0x180003555  jz      short loc_180003589
0x180003557  cmp     byte ptr [r8], 0
0x18000355b  jz      short loc_180003589
0x18000355d  mov     rcx, r8; this
0x180003560  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180003565  sub     rdx, rdi; DestinationSize
0x180003568  mov     rsi, rax
0x18000356b  cmp     rdx, rax
0x18000356e  jb      short loc_180003589
0x180003570  mov     r9, rax; SourceSize
0x180003573  mov     rcx, rdi; Destination
0x180003576  call    memcpy_s
0x18000357b  test    rbx, rbx
0x18000357e  jz      short loc_180003583
0x180003580  mov     [rbx], rdi
0x180003583  lea     rax, [rsi+rdi]
0x180003587  jmp     short loc_180003598
0x180003589  test    rbx, rbx
0x18000358c  jz      short loc_180003595
0x18000358e  mov     qword ptr [r9], 0
0x180003595  mov     rax, rdi
0x180003598  mov     rbx, [rsp+28h+arg_0]
0x18000359d  mov     rsi, [rsp+28h+arg_8]
0x1800035a2  add     rsp, 20h
0x1800035a6  pop     rdi
0x1800035a7  retn
```
