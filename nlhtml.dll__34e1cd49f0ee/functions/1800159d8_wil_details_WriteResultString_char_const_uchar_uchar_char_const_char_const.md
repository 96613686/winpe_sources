# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x1800159d8`
- end: `0x180015a48`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `112`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800194e0`
- `0x18001970c`

## callees

- `0x1800159d8`
- `0x180019378`
- `0x18001aea4`

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
0x1800159d8  mov     [rsp+arg_0], rbx
0x1800159dd  mov     [rsp+arg_8], rsi
0x1800159e2  push    rdi
0x1800159e3  sub     rsp, 20h
0x1800159e7  mov     rbx, r9
0x1800159ea  mov     rdi, rcx
0x1800159ed  cmp     rcx, rdx
0x1800159f0  jz      short loc_180015A29
0x1800159f2  test    r8, r8
0x1800159f5  jz      short loc_180015A29
0x1800159f7  cmp     byte ptr [r8], 0
0x1800159fb  jz      short loc_180015A29
0x1800159fd  mov     rcx, r8; this
0x180015a00  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015a05  sub     rdx, rdi; DestinationSize
0x180015a08  mov     rsi, rax
0x180015a0b  cmp     rdx, rax
0x180015a0e  jb      short loc_180015A29
0x180015a10  mov     r9, rax; SourceSize
0x180015a13  mov     rcx, rdi; Destination
0x180015a16  call    memcpy_s
0x180015a1b  test    rbx, rbx
0x180015a1e  jz      short loc_180015A23
0x180015a20  mov     [rbx], rdi
0x180015a23  lea     rax, [rsi+rdi]
0x180015a27  jmp     short loc_180015A38
0x180015a29  test    rbx, rbx
0x180015a2c  jz      short loc_180015A35
0x180015a2e  mov     qword ptr [r9], 0
0x180015a35  mov     rax, rdi
0x180015a38  mov     rbx, [rsp+28h+arg_0]
0x180015a3d  mov     rsi, [rsp+28h+arg_8]
0x180015a42  add     rsp, 20h
0x180015a46  pop     rdi
0x180015a47  retn
```
