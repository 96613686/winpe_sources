# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003628`
- end: `0x180003690`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005afc`
- `0x180005c38`

## callees

- `0x180003628`
- `0x180005a4c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003668`
- `msvcrt!memcpy_s` at `0x180003668`

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
0x180003628  push    rbx
0x18000362a  push    rbp
0x18000362b  push    rsi
0x18000362c  push    rdi
0x18000362d  sub     rsp, 28h
0x180003631  xor     ebp, ebp
0x180003633  mov     rbx, r9
0x180003636  mov     r10, rdx
0x180003639  mov     rdi, rcx
0x18000363c  cmp     rcx, rdx
0x18000363f  jz      short loc_18000367C
0x180003641  test    r8, r8
0x180003644  jz      short loc_18000367C
0x180003646  cmp     [r8], bp
0x18000364a  jz      short loc_18000367C
0x18000364c  mov     rcx, r8; this
0x18000364f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003654  sub     r10, rdi
0x180003657  mov     rsi, rax
0x18000365a  cmp     r10, rax
0x18000365d  jb      short loc_18000367C
0x18000365f  mov     r9, rax; SourceSize
0x180003662  mov     rdx, r10; DestinationSize
0x180003665  mov     rcx, rdi; Destination
0x180003668  call    cs:__imp_memcpy_s
0x18000366e  test    rbx, rbx
0x180003671  jz      short loc_180003676
0x180003673  mov     [rbx], rdi
0x180003676  lea     rax, [rsi+rdi]
0x18000367a  jmp     short loc_180003687
0x18000367c  test    rbx, rbx
0x18000367f  jz      short loc_180003684
0x180003681  mov     [r9], rbp
0x180003684  mov     rax, rdi
0x180003687  add     rsp, 28h
0x18000368b  pop     rdi
0x18000368c  pop     rsi
0x18000368d  pop     rbp
0x18000368e  pop     rbx
0x18000368f  retn
```
