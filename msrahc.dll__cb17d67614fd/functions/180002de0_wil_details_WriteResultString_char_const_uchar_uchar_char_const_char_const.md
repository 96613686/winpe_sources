# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002de0`
- end: `0x180002e51`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006400`
- `0x18000662c`

## callees

- `0x180002de0`
- `0x180006278`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002e1e`
- `msvcrt!memcpy_s` at `0x180002e1e`

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
0x180002de0  mov     [rsp+arg_0], rbx
0x180002de5  mov     [rsp+arg_8], rsi
0x180002dea  push    rdi
0x180002deb  sub     rsp, 20h
0x180002def  mov     rbx, r9
0x180002df2  mov     rdi, rcx
0x180002df5  cmp     rcx, rdx
0x180002df8  jz      short loc_180002E32
0x180002dfa  test    r8, r8
0x180002dfd  jz      short loc_180002E32
0x180002dff  cmp     byte ptr [r8], 0
0x180002e03  jz      short loc_180002E32
0x180002e05  mov     rcx, r8; this
0x180002e08  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002e0d  sub     rdx, rdi; DestinationSize
0x180002e10  mov     rsi, rax
0x180002e13  cmp     rdx, rax
0x180002e16  jb      short loc_180002E32
0x180002e18  mov     r9, rax; SourceSize
0x180002e1b  mov     rcx, rdi; Destination
0x180002e1e  call    cs:__imp_memcpy_s
0x180002e24  test    rbx, rbx
0x180002e27  jz      short loc_180002E2C
0x180002e29  mov     [rbx], rdi
0x180002e2c  lea     rax, [rsi+rdi]
0x180002e30  jmp     short loc_180002E41
0x180002e32  test    rbx, rbx
0x180002e35  jz      short loc_180002E3E
0x180002e37  mov     qword ptr [r9], 0
0x180002e3e  mov     rax, rdi
0x180002e41  mov     rbx, [rsp+28h+arg_0]
0x180002e46  mov     rsi, [rsp+28h+arg_8]
0x180002e4b  add     rsp, 20h
0x180002e4f  pop     rdi
0x180002e50  retn
```
