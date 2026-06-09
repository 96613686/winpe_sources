# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800273a0`
- end: `0x180027408`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cfa0`
- `0x18002d1cc`

## callees

- `0x1800273a0`
- `0x18002ce34`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800273e0`
- `msvcrt!memcpy_s` at `0x1800273e0`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x1800273a0  push    rbx
0x1800273a2  push    rbp
0x1800273a3  push    rsi
0x1800273a4  push    rdi
0x1800273a5  sub     rsp, 28h
0x1800273a9  xor     ebp, ebp
0x1800273ab  mov     rbx, r9
0x1800273ae  mov     r10, rdx
0x1800273b1  mov     rdi, rcx
0x1800273b4  cmp     rcx, rdx
0x1800273b7  jz      short loc_1800273F4
0x1800273b9  test    r8, r8
0x1800273bc  jz      short loc_1800273F4
0x1800273be  cmp     [r8], bp
0x1800273c2  jz      short loc_1800273F4
0x1800273c4  mov     rcx, r8; this
0x1800273c7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800273cc  sub     r10, rdi
0x1800273cf  mov     rsi, rax
0x1800273d2  cmp     r10, rax
0x1800273d5  jb      short loc_1800273F4
0x1800273d7  mov     r9, rax; SourceSize
0x1800273da  mov     rdx, r10; DestinationSize
0x1800273dd  mov     rcx, rdi; Destination
0x1800273e0  call    cs:__imp_memcpy_s
0x1800273e6  test    rbx, rbx
0x1800273e9  jz      short loc_1800273EE
0x1800273eb  mov     [rbx], rdi
0x1800273ee  lea     rax, [rsi+rdi]
0x1800273f2  jmp     short loc_1800273FF
0x1800273f4  test    rbx, rbx
0x1800273f7  jz      short loc_1800273FC
0x1800273f9  mov     [r9], rbp
0x1800273fc  mov     rax, rdi
0x1800273ff  add     rsp, 28h
0x180027403  pop     rdi
0x180027404  pop     rsi
0x180027405  pop     rbp
0x180027406  pop     rbx
0x180027407  retn
```
