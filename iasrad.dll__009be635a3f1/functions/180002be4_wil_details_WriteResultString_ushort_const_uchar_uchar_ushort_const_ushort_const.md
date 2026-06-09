# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002be4`
- end: `0x180002c4c`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007060`
- `0x180007288`

## callees

- `0x180002be4`
- `0x180006ef4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c24`
- `msvcrt!memcpy_s` at `0x180002c24`

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
0x180002be4  push    rbx
0x180002be6  push    rbp
0x180002be7  push    rsi
0x180002be8  push    rdi
0x180002be9  sub     rsp, 28h
0x180002bed  xor     ebp, ebp
0x180002bef  mov     rbx, r9
0x180002bf2  mov     r10, rdx
0x180002bf5  mov     rdi, rcx
0x180002bf8  cmp     rcx, rdx
0x180002bfb  jz      short loc_180002C38
0x180002bfd  test    r8, r8
0x180002c00  jz      short loc_180002C38
0x180002c02  cmp     [r8], bp
0x180002c06  jz      short loc_180002C38
0x180002c08  mov     rcx, r8; this
0x180002c0b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180002c10  sub     r10, rdi
0x180002c13  mov     rsi, rax
0x180002c16  cmp     r10, rax
0x180002c19  jb      short loc_180002C38
0x180002c1b  mov     r9, rax; SourceSize
0x180002c1e  mov     rdx, r10; DestinationSize
0x180002c21  mov     rcx, rdi; Destination
0x180002c24  call    cs:__imp_memcpy_s
0x180002c2a  test    rbx, rbx
0x180002c2d  jz      short loc_180002C32
0x180002c2f  mov     [rbx], rdi
0x180002c32  lea     rax, [rsi+rdi]
0x180002c36  jmp     short loc_180002C43
0x180002c38  test    rbx, rbx
0x180002c3b  jz      short loc_180002C40
0x180002c3d  mov     [r9], rbp
0x180002c40  mov     rax, rdi
0x180002c43  add     rsp, 28h
0x180002c47  pop     rdi
0x180002c48  pop     rsi
0x180002c49  pop     rbp
0x180002c4a  pop     rbx
0x180002c4b  retn
```
