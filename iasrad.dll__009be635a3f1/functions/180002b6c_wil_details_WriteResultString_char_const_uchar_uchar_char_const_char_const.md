# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002b6c`
- end: `0x180002bdd`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007060`
- `0x180007288`

## callees

- `0x180002b6c`
- `0x180006ed4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002baa`
- `msvcrt!memcpy_s` at `0x180002baa`

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
0x180002b6c  mov     [rsp+arg_0], rbx
0x180002b71  mov     [rsp+arg_8], rsi
0x180002b76  push    rdi
0x180002b77  sub     rsp, 20h
0x180002b7b  mov     rbx, r9
0x180002b7e  mov     rdi, rcx
0x180002b81  cmp     rcx, rdx
0x180002b84  jz      short loc_180002BBE
0x180002b86  test    r8, r8
0x180002b89  jz      short loc_180002BBE
0x180002b8b  cmp     byte ptr [r8], 0
0x180002b8f  jz      short loc_180002BBE
0x180002b91  mov     rcx, r8; this
0x180002b94  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180002b99  sub     rdx, rdi; DestinationSize
0x180002b9c  mov     rsi, rax
0x180002b9f  cmp     rdx, rax
0x180002ba2  jb      short loc_180002BBE
0x180002ba4  mov     r9, rax; SourceSize
0x180002ba7  mov     rcx, rdi; Destination
0x180002baa  call    cs:__imp_memcpy_s
0x180002bb0  test    rbx, rbx
0x180002bb3  jz      short loc_180002BB8
0x180002bb5  mov     [rbx], rdi
0x180002bb8  lea     rax, [rsi+rdi]
0x180002bbc  jmp     short loc_180002BCD
0x180002bbe  test    rbx, rbx
0x180002bc1  jz      short loc_180002BCA
0x180002bc3  mov     qword ptr [r9], 0
0x180002bca  mov     rax, rdi
0x180002bcd  mov     rbx, [rsp+28h+arg_0]
0x180002bd2  mov     rsi, [rsp+28h+arg_8]
0x180002bd7  add     rsp, 20h
0x180002bdb  pop     rdi
0x180002bdc  retn
```
