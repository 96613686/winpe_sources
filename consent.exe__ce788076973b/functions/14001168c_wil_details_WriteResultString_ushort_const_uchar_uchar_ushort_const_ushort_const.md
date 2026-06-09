# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x14001168c`
- end: `0x1400116f4`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013070`
- `0x1400131ac`

## callees

- `0x14001168c`
- `0x140012fa8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400116cc`
- `msvcrt!memcpy_s` at `0x1400116cc`

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
0x14001168c  push    rbx
0x14001168e  push    rbp
0x14001168f  push    rsi
0x140011690  push    rdi
0x140011691  sub     rsp, 28h
0x140011695  xor     ebp, ebp
0x140011697  mov     rbx, r9
0x14001169a  mov     r10, rdx
0x14001169d  mov     rdi, rcx
0x1400116a0  cmp     rcx, rdx
0x1400116a3  jz      short loc_1400116E0
0x1400116a5  test    r8, r8
0x1400116a8  jz      short loc_1400116E0
0x1400116aa  cmp     [r8], bp
0x1400116ae  jz      short loc_1400116E0
0x1400116b0  mov     rcx, r8; this
0x1400116b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400116b8  sub     r10, rdi
0x1400116bb  mov     rsi, rax
0x1400116be  cmp     r10, rax
0x1400116c1  jb      short loc_1400116E0
0x1400116c3  mov     r9, rax; SourceSize
0x1400116c6  mov     rdx, r10; DestinationSize
0x1400116c9  mov     rcx, rdi; Destination
0x1400116cc  call    cs:__imp_memcpy_s
0x1400116d2  test    rbx, rbx
0x1400116d5  jz      short loc_1400116DA
0x1400116d7  mov     [rbx], rdi
0x1400116da  lea     rax, [rsi+rdi]
0x1400116de  jmp     short loc_1400116EB
0x1400116e0  test    rbx, rbx
0x1400116e3  jz      short loc_1400116E8
0x1400116e5  mov     [r9], rbp
0x1400116e8  mov     rax, rdi
0x1400116eb  add     rsp, 28h
0x1400116ef  pop     rdi
0x1400116f0  pop     rsi
0x1400116f1  pop     rbp
0x1400116f2  pop     rbx
0x1400116f3  retn
```
