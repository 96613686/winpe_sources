# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180016234`
- end: `0x18001629c`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bc80`
- `0x18001bea8`

## callees

- `0x180016234`
- `0x18001bb10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016274`
- `msvcrt!memcpy_s` at `0x180016274`

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
0x180016234  push    rbx
0x180016236  push    rbp
0x180016237  push    rsi
0x180016238  push    rdi
0x180016239  sub     rsp, 28h
0x18001623d  xor     ebp, ebp
0x18001623f  mov     rbx, r9
0x180016242  mov     r10, rdx
0x180016245  mov     rdi, rcx
0x180016248  cmp     rcx, rdx
0x18001624b  jz      short loc_180016288
0x18001624d  test    r8, r8
0x180016250  jz      short loc_180016288
0x180016252  cmp     [r8], bp
0x180016256  jz      short loc_180016288
0x180016258  mov     rcx, r8; this
0x18001625b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180016260  sub     r10, rdi
0x180016263  mov     rsi, rax
0x180016266  cmp     r10, rax
0x180016269  jb      short loc_180016288
0x18001626b  mov     r9, rax; SourceSize
0x18001626e  mov     rdx, r10; DestinationSize
0x180016271  mov     rcx, rdi; Destination
0x180016274  call    cs:__imp_memcpy_s
0x18001627a  test    rbx, rbx
0x18001627d  jz      short loc_180016282
0x18001627f  mov     [rbx], rdi
0x180016282  lea     rax, [rsi+rdi]
0x180016286  jmp     short loc_180016293
0x180016288  test    rbx, rbx
0x18001628b  jz      short loc_180016290
0x18001628d  mov     [r9], rbp
0x180016290  mov     rax, rdi
0x180016293  add     rsp, 28h
0x180016297  pop     rdi
0x180016298  pop     rsi
0x180016299  pop     rbp
0x18001629a  pop     rbx
0x18001629b  retn
```
