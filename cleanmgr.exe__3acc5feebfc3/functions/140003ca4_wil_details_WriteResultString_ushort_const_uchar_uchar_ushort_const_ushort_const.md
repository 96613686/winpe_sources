# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140003ca4`
- end: `0x140003d0b`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005ab4`
- `0x140005bf0`

## callees

- `0x140003ca4`
- `0x140005968`
- `0x1400069a8`

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
0x140003ca4  push    rbx
0x140003ca6  push    rbp
0x140003ca7  push    rsi
0x140003ca8  push    rdi
0x140003ca9  sub     rsp, 28h
0x140003cad  xor     ebp, ebp
0x140003caf  mov     rbx, r9
0x140003cb2  mov     r10, rdx
0x140003cb5  mov     rdi, rcx
0x140003cb8  cmp     rcx, rdx
0x140003cbb  jz      short loc_140003CF7
0x140003cbd  test    r8, r8
0x140003cc0  jz      short loc_140003CF7
0x140003cc2  cmp     [r8], bp
0x140003cc6  jz      short loc_140003CF7
0x140003cc8  mov     rcx, r8; this
0x140003ccb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140003cd0  sub     r10, rdi
0x140003cd3  mov     rsi, rax
0x140003cd6  cmp     r10, rax
0x140003cd9  jb      short loc_140003CF7
0x140003cdb  mov     r9, rax; SourceSize
0x140003cde  mov     rdx, r10; DestinationSize
0x140003ce1  mov     rcx, rdi; Destination
0x140003ce4  call    memcpy_s
0x140003ce9  test    rbx, rbx
0x140003cec  jz      short loc_140003CF1
0x140003cee  mov     [rbx], rdi
0x140003cf1  lea     rax, [rsi+rdi]
0x140003cf5  jmp     short loc_140003D02
0x140003cf7  test    rbx, rbx
0x140003cfa  jz      short loc_140003CFF
0x140003cfc  mov     [r9], rbp
0x140003cff  mov     rax, rdi
0x140003d02  add     rsp, 28h
0x140003d06  pop     rdi
0x140003d07  pop     rsi
0x140003d08  pop     rbp
0x140003d09  pop     rbx
0x140003d0a  retn
```
