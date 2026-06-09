# CTdsParser::InitParser(void)

- ea: `0x1004610b8`
- end: `0x1004611ca`
- name: `?InitParser@CTdsParser@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(CTdsParser *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1004e7330`

## callees

- `0x1004610b8`
- `0x100468718`
- `0x10046c37c`
- `0x10046c3c8`
- `0x100546894`
- `0x100546a24`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1004610eb`
- `KERNEL32!CreateEventW` at `0x100461115`
- `KERNEL32!CreateEventW` at `0x1004610eb`
- `KERNEL32!CreateEventW` at `0x100461115`
- `KERNEL32!GetLastError` at `0x1004610fa`
- `KERNEL32!GetLastError` at `0x100461124`
- `KERNEL32!GetLastError` at `0x1004610fa`
- `KERNEL32!GetLastError` at `0x100461124`

## pseudocode

```c
__int64 __fastcall CTdsParser::InitParser(CTdsParser *this)
{
  unsigned int v2; // ebx
  HANDLE EventW; // rax
  __int64 v4; // r9
  HANDLE v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdx

  v2 = 0;
  *((_DWORD *)this + 15) = bidObtainItemIDW(off_1005E8388[0], this, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 12) = EventW;
  if ( EventW )
  {
    *((_QWORD *)this + 11) = 0;
  }
  else if ( GetLastError() )
  {
    goto LABEL_7;
  }
  v5 = CreateEventW(0, 0, 1, 0);
  *((_QWORD *)this + 14) = v5;
  if ( v5 )
  {
    *((_QWORD *)this + 13) = 0;
LABEL_11:
    *((_QWORD *)this + 9) = (char *)this + 64;
    *((_QWORD *)this + 8) = (char *)this + 64;
    if ( (unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 1) )
    {
      if ( (unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)this + 10) )
      {
        GetNode((BYTE *)this + 52, 6u);
        return v2;
      }
      MPDeleteCriticalSection((char *)this + 8, v7);
      if ( (bidGblFlags & 2) != 0 )
      {
        v6 = 204809;
        return (unsigned int)bidTraceHR(0, v6, 2147942414LL, v4);
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      v6 = 196617;
      return (unsigned int)bidTraceHR(0, v6, 2147942414LL, v4);
    }
    return (unsigned int)-2147024882;
  }
  if ( !GetLastError() )
    goto LABEL_11;
LABEL_7:
  if ( (bidGblFlags & 2) == 0 )
    return (unsigned int)-2147024882;
  v6 = 186377;
  return (unsigned int)bidTraceHR(0, v6, 2147942414LL, v4);
}

```

## disassembly

```asm
0x1004610b8  mov     [rsp+arg_0], rbx
0x1004610bd  mov     [rsp+arg_8], rsi
0x1004610c2  push    rdi
0x1004610c3  sub     rsp, 20h
0x1004610c7  mov     rdi, rcx
0x1004610ca  mov     rdx, rcx
0x1004610cd  mov     rcx, cs:off_1005E8388; "<CTdsParser::InitParser|ID|TDS> %p{.}"
0x1004610d4  xor     r8d, r8d
0x1004610d7  xor     ebx, ebx
0x1004610d9  call    _bidObtainItemIDW
0x1004610de  xor     r9d, r9d; lpName
0x1004610e1  mov     [rdi+3Ch], eax
0x1004610e4  xor     r8d, r8d; bInitialState
0x1004610e7  xor     edx, edx; bManualReset
0x1004610e9  xor     ecx, ecx; lpEventAttributes
0x1004610eb  call    cs:__imp_CreateEventW
0x1004610f1  mov     [rdi+60h], rax
0x1004610f5  test    rax, rax
0x1004610f8  jnz     short loc_100461106
0x1004610fa  call    cs:__imp_GetLastError
0x100461100  test    eax, eax
0x100461102  jnz     short loc_10046112E
0x100461104  jmp     short loc_10046110A
0x100461106  mov     [rdi+58h], rbx
0x10046110a  xor     r9d, r9d; lpName
0x10046110d  xor     edx, edx; bManualReset
0x10046110f  xor     ecx, ecx; lpEventAttributes
0x100461111  lea     r8d, [r9+1]; bInitialState
0x100461115  call    cs:__imp_CreateEventW
0x10046111b  mov     [rdi+70h], rax
0x10046111f  test    rax, rax
0x100461122  jnz     short loc_10046114D
0x100461124  call    cs:__imp_GetLastError
0x10046112a  test    eax, eax
0x10046112c  jz      short loc_100461151
0x10046112e  test    byte ptr cs:_bidGblFlags, 2
0x100461135  jz      short loc_10046117B
0x100461137  mov     edx, 2D809h
0x10046113c  xor     ecx, ecx
0x10046113e  mov     r8d, 8007000Eh
0x100461144  call    _bidTraceHR
0x100461149  mov     ebx, eax
0x10046114b  jmp     short loc_1004611B8
0x10046114d  mov     [rdi+68h], rbx
0x100461151  lea     rax, [rdi+40h]
0x100461155  xor     edx, edx
0x100461157  lea     rcx, [rdi+8]; struct CCriticalSection **
0x10046115b  mov     [rax+8], rax
0x10046115f  mov     [rax], rax
0x100461162  call    MPInitializeCriticalSectionAndSpinCount
0x100461167  test    eax, eax
0x100461169  jnz     short loc_100461182
0x10046116b  test    byte ptr cs:_bidGblFlags, 2
0x100461172  jz      short loc_10046117B
0x100461174  mov     edx, 30009h
0x100461179  jmp     short loc_10046113C
0x10046117b  mov     ebx, 8007000Eh
0x100461180  jmp     short loc_1004611B8
0x100461182  lea     rcx, [rdi+50h]; struct CCriticalSection **
0x100461186  xor     edx, edx
0x100461188  call    MPInitializeCriticalSectionAndSpinCount
0x10046118d  test    eax, eax
0x10046118f  jnz     short loc_1004611AA
0x100461191  lea     rcx, [rdi+8]
0x100461195  call    MPDeleteCriticalSection
0x10046119a  test    byte ptr cs:_bidGblFlags, 2
0x1004611a1  jz      short loc_10046117B
0x1004611a3  mov     edx, 32009h
0x1004611a8  jmp     short loc_10046113C
0x1004611aa  mov     edx, 6; unsigned __int16
0x1004611af  lea     rcx, [rdi+34h]; lpData
0x1004611b3  call    ?GetNode@@YAJPEAEG@Z; GetNode(uchar *,ushort)
0x1004611b8  mov     rsi, [rsp+28h+arg_8]
0x1004611bd  mov     eax, ebx
0x1004611bf  mov     rbx, [rsp+28h+arg_0]
0x1004611c4  add     rsp, 20h
0x1004611c8  pop     rdi
0x1004611c9  retn
```
