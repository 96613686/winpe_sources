# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004158`
- end: `0x1800041c0`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005d70`
- `0x180005eac`

## callees

- `0x180004158`
- `0x180005c68`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004198`
- `msvcrt!memcpy_s` at `0x180004198`

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
0x180004158  push    rbx
0x18000415a  push    rbp
0x18000415b  push    rsi
0x18000415c  push    rdi
0x18000415d  sub     rsp, 28h
0x180004161  xor     ebp, ebp
0x180004163  mov     rbx, r9
0x180004166  mov     r10, rdx
0x180004169  mov     rdi, rcx
0x18000416c  cmp     rcx, rdx
0x18000416f  jz      short loc_1800041AC
0x180004171  test    r8, r8
0x180004174  jz      short loc_1800041AC
0x180004176  cmp     [r8], bp
0x18000417a  jz      short loc_1800041AC
0x18000417c  mov     rcx, r8; this
0x18000417f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004184  sub     r10, rdi
0x180004187  mov     rsi, rax
0x18000418a  cmp     r10, rax
0x18000418d  jb      short loc_1800041AC
0x18000418f  mov     r9, rax; SourceSize
0x180004192  mov     rdx, r10; DestinationSize
0x180004195  mov     rcx, rdi; Destination
0x180004198  call    cs:__imp_memcpy_s
0x18000419e  test    rbx, rbx
0x1800041a1  jz      short loc_1800041A6
0x1800041a3  mov     [rbx], rdi
0x1800041a6  lea     rax, [rsi+rdi]
0x1800041aa  jmp     short loc_1800041B7
0x1800041ac  test    rbx, rbx
0x1800041af  jz      short loc_1800041B4
0x1800041b1  mov     [r9], rbp
0x1800041b4  mov     rax, rdi
0x1800041b7  add     rsp, 28h
0x1800041bb  pop     rdi
0x1800041bc  pop     rsi
0x1800041bd  pop     rbp
0x1800041be  pop     rbx
0x1800041bf  retn
```
