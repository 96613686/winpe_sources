# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180005810`
- end: `0x180005877`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ca0`
- `0x180008ec8`

## callees

- `0x180003404`
- `0x180005810`
- `0x180008a90`

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
0x180005810  push    rbx
0x180005812  push    rbp
0x180005813  push    rsi
0x180005814  push    rdi
0x180005815  sub     rsp, 28h
0x180005819  xor     ebp, ebp
0x18000581b  mov     rbx, r9
0x18000581e  mov     r10, rdx
0x180005821  mov     rdi, rcx
0x180005824  cmp     rcx, rdx
0x180005827  jz      short loc_180005863
0x180005829  test    r8, r8
0x18000582c  jz      short loc_180005863
0x18000582e  cmp     [r8], bp
0x180005832  jz      short loc_180005863
0x180005834  mov     rcx, r8; this
0x180005837  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000583c  sub     r10, rdi
0x18000583f  mov     rsi, rax
0x180005842  cmp     r10, rax
0x180005845  jb      short loc_180005863
0x180005847  mov     r9, rax; SourceSize
0x18000584a  mov     rdx, r10; DestinationSize
0x18000584d  mov     rcx, rdi; Destination
0x180005850  call    memcpy_s
0x180005855  test    rbx, rbx
0x180005858  jz      short loc_18000585D
0x18000585a  mov     [rbx], rdi
0x18000585d  lea     rax, [rsi+rdi]
0x180005861  jmp     short loc_18000586E
0x180005863  test    rbx, rbx
0x180005866  jz      short loc_18000586B
0x180005868  mov     [r9], rbp
0x18000586b  mov     rax, rdi
0x18000586e  add     rsp, 28h
0x180005872  pop     rdi
0x180005873  pop     rsi
0x180005874  pop     rbp
0x180005875  pop     rbx
0x180005876  retn
```
