# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003de8`
- end: `0x180003e4f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007038`
- `0x180007174`

## callees

- `0x180003de8`
- `0x180006c98`
- `0x180008660`

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
0x180003de8  push    rbx
0x180003dea  push    rbp
0x180003deb  push    rsi
0x180003dec  push    rdi
0x180003ded  sub     rsp, 28h
0x180003df1  xor     ebp, ebp
0x180003df3  mov     rbx, r9
0x180003df6  mov     r10, rdx
0x180003df9  mov     rdi, rcx
0x180003dfc  cmp     rcx, rdx
0x180003dff  jz      short loc_180003E3B
0x180003e01  test    r8, r8
0x180003e04  jz      short loc_180003E3B
0x180003e06  cmp     [r8], bp
0x180003e0a  jz      short loc_180003E3B
0x180003e0c  mov     rcx, r8; this
0x180003e0f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003e14  sub     r10, rdi
0x180003e17  mov     rsi, rax
0x180003e1a  cmp     r10, rax
0x180003e1d  jb      short loc_180003E3B
0x180003e1f  mov     r9, rax; SourceSize
0x180003e22  mov     rdx, r10; DestinationSize
0x180003e25  mov     rcx, rdi; Destination
0x180003e28  call    memcpy_s
0x180003e2d  test    rbx, rbx
0x180003e30  jz      short loc_180003E35
0x180003e32  mov     [rbx], rdi
0x180003e35  lea     rax, [rsi+rdi]
0x180003e39  jmp     short loc_180003E46
0x180003e3b  test    rbx, rbx
0x180003e3e  jz      short loc_180003E43
0x180003e40  mov     [r9], rbp
0x180003e43  mov     rax, rdi
0x180003e46  add     rsp, 28h
0x180003e4a  pop     rdi
0x180003e4b  pop     rsi
0x180003e4c  pop     rbp
0x180003e4d  pop     rbx
0x180003e4e  retn
```
