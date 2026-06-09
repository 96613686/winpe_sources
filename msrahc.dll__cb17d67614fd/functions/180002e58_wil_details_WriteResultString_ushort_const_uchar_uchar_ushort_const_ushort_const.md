# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002e58`
- end: `0x180002ec0`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006400`
- `0x18000662c`

## callees

- `0x180002e58`
- `0x180006298`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002e98`
- `msvcrt!memcpy_s` at `0x180002e98`

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
0x180002e58  push    rbx
0x180002e5a  push    rbp
0x180002e5b  push    rsi
0x180002e5c  push    rdi
0x180002e5d  sub     rsp, 28h
0x180002e61  xor     ebp, ebp
0x180002e63  mov     rbx, r9
0x180002e66  mov     r10, rdx
0x180002e69  mov     rdi, rcx
0x180002e6c  cmp     rcx, rdx
0x180002e6f  jz      short loc_180002EAC
0x180002e71  test    r8, r8
0x180002e74  jz      short loc_180002EAC
0x180002e76  cmp     [r8], bp
0x180002e7a  jz      short loc_180002EAC
0x180002e7c  mov     rcx, r8; this
0x180002e7f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180002e84  sub     r10, rdi
0x180002e87  mov     rsi, rax
0x180002e8a  cmp     r10, rax
0x180002e8d  jb      short loc_180002EAC
0x180002e8f  mov     r9, rax; SourceSize
0x180002e92  mov     rdx, r10; DestinationSize
0x180002e95  mov     rcx, rdi; Destination
0x180002e98  call    cs:__imp_memcpy_s
0x180002e9e  test    rbx, rbx
0x180002ea1  jz      short loc_180002EA6
0x180002ea3  mov     [rbx], rdi
0x180002ea6  lea     rax, [rsi+rdi]
0x180002eaa  jmp     short loc_180002EB7
0x180002eac  test    rbx, rbx
0x180002eaf  jz      short loc_180002EB4
0x180002eb1  mov     [r9], rbp
0x180002eb4  mov     rax, rdi
0x180002eb7  add     rsp, 28h
0x180002ebb  pop     rdi
0x180002ebc  pop     rsi
0x180002ebd  pop     rbp
0x180002ebe  pop     rbx
0x180002ebf  retn
```
