# ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Next(ulong,_GUID *,ulong *)

- ea: `0x18000c9e0`
- end: `0x18000cac8`
- name: `?Next@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJKPEAU_GUID@@PEAK@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c990`

## callees

- `0x180002ac4`
- `0x18000c9e0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ca62`
- `msvcrt!memcpy_s` at `0x18000ca62`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Next(
        __int64 a1,
        unsigned int a2,
        char *a3,
        _DWORD *a4)
{
  char *v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbx
  BOOL v9; // ebp
  errno_t v10; // eax

  v4 = a3;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 || a2 != 1 && !a4 )
    return 2147500035LL;
  if ( !*(_QWORD *)(a1 + 16) )
    return 2147500037LL;
  v7 = *(_QWORD *)(a1 + 24);
  if ( !v7 || !*(_QWORD *)(a1 + 32) )
    return 2147500037LL;
  v8 = (v7 - *(_QWORD *)(a1 + 32)) >> 4;
  v9 = (unsigned int)v8 < a2;
  if ( (unsigned int)v8 > a2 )
    LODWORD(v8) = a2;
  if ( a4 )
    *a4 = v8;
  for ( ; (_DWORD)v8; LODWORD(v8) = v8 - 1 )
  {
    v10 = memcpy_s(v4, 0x10u, *(const void *const *)(a1 + 32), 0x10u);
    if ( v10 )
    {
      if ( v10 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v10 == 22 || v10 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v10 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    *(_QWORD *)(a1 + 32) += 16LL;
    v4 += 16;
  }
  return v9;
}

```

## disassembly

```asm
0x18000c9e0  push    rbx
0x18000c9e2  push    rbp
0x18000c9e3  push    rsi
0x18000c9e4  push    rdi
0x18000c9e5  sub     rsp, 28h
0x18000c9e9  mov     rsi, r8
0x18000c9ec  mov     rdi, rcx
0x18000c9ef  test    r9, r9
0x18000c9f2  jz      short loc_18000C9FB
0x18000c9f4  mov     dword ptr [r9], 0
0x18000c9fb  test    edx, edx
0x18000c9fd  jnz     short loc_18000CA09
0x18000c9ff  mov     eax, 80070057h
0x18000ca04  jmp     loc_18000CA9E
0x18000ca09  test    r8, r8
0x18000ca0c  jz      loc_18000CA99
0x18000ca12  cmp     edx, 1
0x18000ca15  jz      short loc_18000CA1C
0x18000ca17  test    r9, r9
0x18000ca1a  jz      short loc_18000CA99
0x18000ca1c  cmp     qword ptr [rcx+10h], 0
0x18000ca21  jz      short loc_18000CA92
0x18000ca23  mov     rbx, [rcx+18h]
0x18000ca27  test    rbx, rbx
0x18000ca2a  jz      short loc_18000CA92
0x18000ca2c  cmp     qword ptr [rcx+20h], 0
0x18000ca31  jz      short loc_18000CA92
0x18000ca33  sub     rbx, [rcx+20h]
0x18000ca37  xor     ebp, ebp
0x18000ca39  sar     rbx, 4
0x18000ca3d  cmp     ebx, edx
0x18000ca3f  setb    bpl
0x18000ca43  cmova   ebx, edx
0x18000ca46  test    r9, r9
0x18000ca49  jz      short loc_18000CA4E
0x18000ca4b  mov     [r9], ebx
0x18000ca4e  test    ebx, ebx
0x18000ca50  jz      short loc_18000CA8E
0x18000ca52  mov     r8, [rdi+20h]; Source
0x18000ca56  mov     r9d, 10h; SourceSize
0x18000ca5c  mov     edx, r9d; DestinationSize
0x18000ca5f  mov     rcx, rsi; Destination
0x18000ca62  call    cs:__imp_memcpy_s
0x18000ca68  test    eax, eax
0x18000ca6a  jz      short loc_18000CA80
0x18000ca6c  cmp     eax, 0Ch
0x18000ca6f  jz      short loc_18000CABD
0x18000ca71  cmp     eax, 16h
0x18000ca74  jz      short loc_18000CAB2
0x18000ca76  cmp     eax, 22h ; '"'
0x18000ca79  jz      short loc_18000CAB2
0x18000ca7b  cmp     eax, 50h ; 'P'
0x18000ca7e  jnz     short loc_18000CAA7
0x18000ca80  add     qword ptr [rdi+20h], 10h
0x18000ca85  add     rsi, 10h
0x18000ca89  add     ebx, 0FFFFFFFFh
0x18000ca8c  jnz     short loc_18000CA52
0x18000ca8e  mov     eax, ebp
0x18000ca90  jmp     short loc_18000CA9E
0x18000ca92  mov     eax, 80004005h
0x18000ca97  jmp     short loc_18000CA9E
0x18000ca99  mov     eax, 80004003h
0x18000ca9e  add     rsp, 28h
0x18000caa2  pop     rdi
0x18000caa3  pop     rsi
0x18000caa4  pop     rbp
0x18000caa5  pop     rbx
0x18000caa6  retn
0x18000caa7  mov     ecx, 80004005h; int
0x18000caac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000cab2  mov     ecx, 80070057h; int
0x18000cab7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000cabd  mov     ecx, 8007000Eh; int
0x18000cac2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
