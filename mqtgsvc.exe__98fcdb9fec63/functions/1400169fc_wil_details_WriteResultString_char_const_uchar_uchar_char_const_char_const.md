# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1400169fc`
- end: `0x140016a7e`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `130`
- prototype: `char *__fastcall(char *Destination, const char *, wil::details *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a460`
- `0x14001a680`

## callees

- `0x1400169fc`
- `0x14001a2c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140016a50`
- `msvcrt!memcpy_s` at `0x140016a50`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v8; // rax
  rsize_t v9; // rbp
  rsize_t v10; // r14

  if ( Destination == a2 || !a3 || !*(_BYTE *)a3 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  v8 = wil::details::ResultStringSize(a3, a2);
  v9 = a2 - Destination;
  v10 = v8;
  if ( v9 < v8 )
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
  memcpy_s(Destination, v9, a3, v8);
  if ( a4 )
    *a4 = Destination;
  return &Destination[v10];
}

```

## disassembly

```asm
0x1400169fc  push    rbx
0x1400169fe  push    rbp
0x1400169ff  push    rsi
0x140016a00  push    rdi
0x140016a01  push    r14
0x140016a03  sub     rsp, 20h
0x140016a07  mov     rbx, r9
0x140016a0a  mov     rsi, r8
0x140016a0d  mov     rbp, rdx
0x140016a10  mov     rdi, rcx
0x140016a13  cmp     rcx, rdx
0x140016a16  jz      short loc_140016A64
0x140016a18  test    r8, r8
0x140016a1b  jz      short loc_140016A64
0x140016a1d  cmp     byte ptr [r8], 0
0x140016a21  jz      short loc_140016A64
0x140016a23  mov     rcx, r8; this
0x140016a26  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140016a2b  sub     rbp, rdi
0x140016a2e  mov     r14, rax
0x140016a31  cmp     rbp, rax
0x140016a34  jnb     short loc_140016A44
0x140016a36  test    rbx, rbx
0x140016a39  jz      short loc_140016A70
0x140016a3b  mov     qword ptr [rbx], 0
0x140016a42  jmp     short loc_140016A70
0x140016a44  mov     r9, r14; SourceSize
0x140016a47  mov     r8, rsi; Source
0x140016a4a  mov     rdx, rbp; DestinationSize
0x140016a4d  mov     rcx, rdi; Destination
0x140016a50  call    cs:__imp_memcpy_s
0x140016a56  test    rbx, rbx
0x140016a59  jz      short loc_140016A5E
0x140016a5b  mov     [rbx], rdi
0x140016a5e  lea     rax, [r14+rdi]
0x140016a62  jmp     short loc_140016A73
0x140016a64  test    rbx, rbx
0x140016a67  jz      short loc_140016A70
0x140016a69  mov     qword ptr [r9], 0
0x140016a70  mov     rax, rdi
0x140016a73  add     rsp, 20h
0x140016a77  pop     r14
0x140016a79  pop     rdi
0x140016a7a  pop     rsi
0x140016a7b  pop     rbp
0x140016a7c  pop     rbx
0x140016a7d  retn
```
