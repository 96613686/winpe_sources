# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800035b0`
- end: `0x180003617`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000558c`
- `0x1800056c8`

## callees

- `0x1800035b0`
- `0x1800054c8`
- `0x180006440`

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
0x1800035b0  push    rbx
0x1800035b2  push    rbp
0x1800035b3  push    rsi
0x1800035b4  push    rdi
0x1800035b5  sub     rsp, 28h
0x1800035b9  xor     ebp, ebp
0x1800035bb  mov     rbx, r9
0x1800035be  mov     r10, rdx
0x1800035c1  mov     rdi, rcx
0x1800035c4  cmp     rcx, rdx
0x1800035c7  jz      short loc_180003603
0x1800035c9  test    r8, r8
0x1800035cc  jz      short loc_180003603
0x1800035ce  cmp     [r8], bp
0x1800035d2  jz      short loc_180003603
0x1800035d4  mov     rcx, r8; this
0x1800035d7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800035dc  sub     r10, rdi
0x1800035df  mov     rsi, rax
0x1800035e2  cmp     r10, rax
0x1800035e5  jb      short loc_180003603
0x1800035e7  mov     r9, rax; SourceSize
0x1800035ea  mov     rdx, r10; DestinationSize
0x1800035ed  mov     rcx, rdi; Destination
0x1800035f0  call    memcpy_s
0x1800035f5  test    rbx, rbx
0x1800035f8  jz      short loc_1800035FD
0x1800035fa  mov     [rbx], rdi
0x1800035fd  lea     rax, [rsi+rdi]
0x180003601  jmp     short loc_18000360E
0x180003603  test    rbx, rbx
0x180003606  jz      short loc_18000360B
0x180003608  mov     [r9], rbp
0x18000360b  mov     rax, rdi
0x18000360e  add     rsp, 28h
0x180003612  pop     rdi
0x180003613  pop     rsi
0x180003614  pop     rbp
0x180003615  pop     rbx
0x180003616  retn
```
