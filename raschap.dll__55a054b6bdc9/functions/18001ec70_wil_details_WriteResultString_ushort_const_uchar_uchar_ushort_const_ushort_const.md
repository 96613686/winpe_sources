# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18001ec70`
- end: `0x18001ecd7`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180021c20`
- `0x180021e48`

## callees

- `0x1800118a4`
- `0x18001ec70`
- `0x180021ab0`

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
0x18001ec70  push    rbx
0x18001ec72  push    rbp
0x18001ec73  push    rsi
0x18001ec74  push    rdi
0x18001ec75  sub     rsp, 28h
0x18001ec79  xor     ebp, ebp
0x18001ec7b  mov     rbx, r9
0x18001ec7e  mov     r10, rdx
0x18001ec81  mov     rdi, rcx
0x18001ec84  cmp     rcx, rdx
0x18001ec87  jz      short loc_18001ECC3
0x18001ec89  test    r8, r8
0x18001ec8c  jz      short loc_18001ECC3
0x18001ec8e  cmp     [r8], bp
0x18001ec92  jz      short loc_18001ECC3
0x18001ec94  mov     rcx, r8; this
0x18001ec97  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001ec9c  sub     r10, rdi
0x18001ec9f  mov     rsi, rax
0x18001eca2  cmp     r10, rax
0x18001eca5  jb      short loc_18001ECC3
0x18001eca7  mov     r9, rax; SourceSize
0x18001ecaa  mov     rdx, r10; DestinationSize
0x18001ecad  mov     rcx, rdi; Destination
0x18001ecb0  call    memcpy_s
0x18001ecb5  test    rbx, rbx
0x18001ecb8  jz      short loc_18001ECBD
0x18001ecba  mov     [rbx], rdi
0x18001ecbd  lea     rax, [rsi+rdi]
0x18001ecc1  jmp     short loc_18001ECCE
0x18001ecc3  test    rbx, rbx
0x18001ecc6  jz      short loc_18001ECCB
0x18001ecc8  mov     [r9], rbp
0x18001eccb  mov     rax, rdi
0x18001ecce  add     rsp, 28h
0x18001ecd2  pop     rdi
0x18001ecd3  pop     rsi
0x18001ecd4  pop     rbp
0x18001ecd5  pop     rbx
0x18001ecd6  retn
```
