# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1400778b0`
- end: `0x140077917`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14007a6b0`
- `0x14007a8d8`

## callees

- `0x1400778b0`
- `0x14007a564`
- `0x14007bed8`

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
0x1400778b0  push    rbx
0x1400778b2  push    rbp
0x1400778b3  push    rsi
0x1400778b4  push    rdi
0x1400778b5  sub     rsp, 28h
0x1400778b9  xor     ebp, ebp
0x1400778bb  mov     rbx, r9
0x1400778be  mov     r10, rdx
0x1400778c1  mov     rdi, rcx
0x1400778c4  cmp     rcx, rdx
0x1400778c7  jz      short loc_140077903
0x1400778c9  test    r8, r8
0x1400778cc  jz      short loc_140077903
0x1400778ce  cmp     [r8], bp
0x1400778d2  jz      short loc_140077903
0x1400778d4  mov     rcx, r8; this
0x1400778d7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400778dc  sub     r10, rdi
0x1400778df  mov     rsi, rax
0x1400778e2  cmp     r10, rax
0x1400778e5  jb      short loc_140077903
0x1400778e7  mov     r9, rax; SourceSize
0x1400778ea  mov     rdx, r10; DestinationSize
0x1400778ed  mov     rcx, rdi; Destination
0x1400778f0  call    memcpy_s
0x1400778f5  test    rbx, rbx
0x1400778f8  jz      short loc_1400778FD
0x1400778fa  mov     [rbx], rdi
0x1400778fd  lea     rax, [rsi+rdi]
0x140077901  jmp     short loc_14007790E
0x140077903  test    rbx, rbx
0x140077906  jz      short loc_14007790B
0x140077908  mov     [r9], rbp
0x14007790b  mov     rax, rdi
0x14007790e  add     rsp, 28h
0x140077912  pop     rdi
0x140077913  pop     rsi
0x140077914  pop     rbp
0x140077915  pop     rbx
0x140077916  retn
```
