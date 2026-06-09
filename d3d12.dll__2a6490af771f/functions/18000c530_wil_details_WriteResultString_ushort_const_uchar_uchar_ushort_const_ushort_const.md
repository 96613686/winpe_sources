# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000c530`
- end: `0x18000c597`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d8e0`
- `0x18000da1c`

## callees

- `0x18000463c`
- `0x18000c530`
- `0x18000d854`

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
0x18000c530  push    rbx
0x18000c532  push    rbp
0x18000c533  push    rsi
0x18000c534  push    rdi
0x18000c535  sub     rsp, 28h
0x18000c539  xor     ebp, ebp
0x18000c53b  mov     rbx, r9
0x18000c53e  mov     r10, rdx
0x18000c541  mov     rdi, rcx
0x18000c544  cmp     rcx, rdx
0x18000c547  jz      short loc_18000C583
0x18000c549  test    r8, r8
0x18000c54c  jz      short loc_18000C583
0x18000c54e  cmp     [r8], bp
0x18000c552  jz      short loc_18000C583
0x18000c554  mov     rcx, r8; this
0x18000c557  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c55c  sub     r10, rdi
0x18000c55f  mov     rsi, rax
0x18000c562  cmp     r10, rax
0x18000c565  jb      short loc_18000C583
0x18000c567  mov     r9, rax; SourceSize
0x18000c56a  mov     rdx, r10; DestinationSize
0x18000c56d  mov     rcx, rdi; Destination
0x18000c570  call    memcpy_s
0x18000c575  test    rbx, rbx
0x18000c578  jz      short loc_18000C57D
0x18000c57a  mov     [rbx], rdi
0x18000c57d  lea     rax, [rsi+rdi]
0x18000c581  jmp     short loc_18000C58E
0x18000c583  test    rbx, rbx
0x18000c586  jz      short loc_18000C58B
0x18000c588  mov     [r9], rbp
0x18000c58b  mov     rax, rdi
0x18000c58e  add     rsp, 28h
0x18000c592  pop     rdi
0x18000c593  pop     rsi
0x18000c594  pop     rbp
0x18000c595  pop     rbx
0x18000c596  retn
```
