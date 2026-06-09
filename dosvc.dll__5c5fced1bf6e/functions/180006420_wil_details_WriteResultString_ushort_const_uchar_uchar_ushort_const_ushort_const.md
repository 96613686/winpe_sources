# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180006420`
- end: `0x180006487`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007a4c`
- `0x180007b88`

## callees

- `0x180002e70`
- `0x180006420`
- `0x1800079bc`

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
    memcpy_s_0(Destination, v9, v7, v6);
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
0x180006420  push    rbx
0x180006422  push    rbp
0x180006423  push    rsi
0x180006424  push    rdi
0x180006425  sub     rsp, 28h
0x180006429  xor     ebp, ebp
0x18000642b  mov     rbx, r9
0x18000642e  mov     r10, rdx
0x180006431  mov     rdi, rcx
0x180006434  cmp     rcx, rdx
0x180006437  jz      short loc_180006473
0x180006439  test    r8, r8
0x18000643c  jz      short loc_180006473
0x18000643e  cmp     [r8], bp
0x180006442  jz      short loc_180006473
0x180006444  mov     rcx, r8; this
0x180006447  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000644c  sub     r10, rdi
0x18000644f  mov     rsi, rax
0x180006452  cmp     r10, rax
0x180006455  jb      short loc_180006473
0x180006457  mov     r9, rax; SourceSize
0x18000645a  mov     rdx, r10; DestinationSize
0x18000645d  mov     rcx, rdi; Destination
0x180006460  call    memcpy_s_0
0x180006465  test    rbx, rbx
0x180006468  jz      short loc_18000646D
0x18000646a  mov     [rbx], rdi
0x18000646d  lea     rax, [rsi+rdi]
0x180006471  jmp     short loc_18000647E
0x180006473  test    rbx, rbx
0x180006476  jz      short loc_18000647B
0x180006478  mov     [r9], rbp
0x18000647b  mov     rax, rdi
0x18000647e  add     rsp, 28h
0x180006482  pop     rdi
0x180006483  pop     rsi
0x180006484  pop     rbp
0x180006485  pop     rbx
0x180006486  retn
```
