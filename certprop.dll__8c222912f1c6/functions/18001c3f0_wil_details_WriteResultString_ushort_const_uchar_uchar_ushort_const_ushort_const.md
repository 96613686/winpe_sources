# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18001c3f0`
- end: `0x18001c457`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d7d4`

## callees

- `0x18000e10c`
- `0x18001c3f0`
- `0x18001d798`

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
0x18001c3f0  push    rbx
0x18001c3f2  push    rbp
0x18001c3f3  push    rsi
0x18001c3f4  push    rdi
0x18001c3f5  sub     rsp, 28h
0x18001c3f9  xor     ebp, ebp
0x18001c3fb  mov     rbx, r9
0x18001c3fe  mov     r10, rdx
0x18001c401  mov     rdi, rcx
0x18001c404  cmp     rcx, rdx
0x18001c407  jz      short loc_18001C443
0x18001c409  test    r8, r8
0x18001c40c  jz      short loc_18001C443
0x18001c40e  cmp     [r8], bp
0x18001c412  jz      short loc_18001C443
0x18001c414  mov     rcx, r8; this
0x18001c417  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001c41c  sub     r10, rdi
0x18001c41f  mov     rsi, rax
0x18001c422  cmp     r10, rax
0x18001c425  jb      short loc_18001C443
0x18001c427  mov     r9, rax; SourceSize
0x18001c42a  mov     rdx, r10; DestinationSize
0x18001c42d  mov     rcx, rdi; Destination
0x18001c430  call    memcpy_s_0
0x18001c435  test    rbx, rbx
0x18001c438  jz      short loc_18001C43D
0x18001c43a  mov     [rbx], rdi
0x18001c43d  lea     rax, [rsi+rdi]
0x18001c441  jmp     short loc_18001C44E
0x18001c443  test    rbx, rbx
0x18001c446  jz      short loc_18001C44B
0x18001c448  mov     [r9], rbp
0x18001c44b  mov     rax, rdi
0x18001c44e  add     rsp, 28h
0x18001c452  pop     rdi
0x18001c453  pop     rsi
0x18001c454  pop     rbp
0x18001c455  pop     rbx
0x18001c456  retn
```
