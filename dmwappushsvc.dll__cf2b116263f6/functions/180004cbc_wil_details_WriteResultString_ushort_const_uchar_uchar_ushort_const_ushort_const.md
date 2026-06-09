# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004cbc`
- end: `0x180004d23`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800057c0`
- `0x18000afc0`

## callees

- `0x180004cbc`
- `0x1800056f4`
- `0x180006094`

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
0x180004cbc  push    rbx
0x180004cbe  push    rbp
0x180004cbf  push    rsi
0x180004cc0  push    rdi
0x180004cc1  sub     rsp, 28h
0x180004cc5  xor     ebp, ebp
0x180004cc7  mov     rbx, r9
0x180004cca  mov     r10, rdx
0x180004ccd  mov     rdi, rcx
0x180004cd0  cmp     rcx, rdx
0x180004cd3  jz      short loc_180004D0F
0x180004cd5  test    r8, r8
0x180004cd8  jz      short loc_180004D0F
0x180004cda  cmp     [r8], bp
0x180004cde  jz      short loc_180004D0F
0x180004ce0  mov     rcx, r8; this
0x180004ce3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004ce8  sub     r10, rdi
0x180004ceb  mov     rsi, rax
0x180004cee  cmp     r10, rax
0x180004cf1  jb      short loc_180004D0F
0x180004cf3  mov     r9, rax; SourceSize
0x180004cf6  mov     rdx, r10; DestinationSize
0x180004cf9  mov     rcx, rdi; Destination
0x180004cfc  call    memcpy_s
0x180004d01  test    rbx, rbx
0x180004d04  jz      short loc_180004D09
0x180004d06  mov     [rbx], rdi
0x180004d09  lea     rax, [rsi+rdi]
0x180004d0d  jmp     short loc_180004D1A
0x180004d0f  test    rbx, rbx
0x180004d12  jz      short loc_180004D17
0x180004d14  mov     [r9], rbp
0x180004d17  mov     rax, rdi
0x180004d1a  add     rsp, 28h
0x180004d1e  pop     rdi
0x180004d1f  pop     rsi
0x180004d20  pop     rbp
0x180004d21  pop     rbx
0x180004d22  retn
```
