# BuildSiufLocPathForXbox(ushort * *)

- ea: `0x140014e08`
- end: `0x140015055`
- name: `?BuildSiufLocPathForXbox@@YAJPEAPEAG@Z`
- size: `589`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001522c`

## callees

- `0x140001418`
- `0x14000b904`
- `0x140014e08`
- `0x14001505c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014e4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140014e4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015005`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001502a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014e31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015005`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001502a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001501a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001503e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001501a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001503e`

## string_xrefs

- `0x140014edf`: `GetDiagTrackStorePath failed.`
- `0x140014ebb`: `BuildSiufLocPathForXbox`
- `0x140014f89`: `BuildSiufLocPathForXbox`

## pseudocode

```c
__int64 __fastcall BuildSiufLocPathForXbox(unsigned __int16 **a1)
{
  int DiagTrackStorePath; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rsi
  int v4; // r9d
  int v5; // r8d
  int v6; // ecx
  char *v7; // rdx
  const char **v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  const char **v12; // [rsp+38h] [rbp-38h]
  const char *v13; // [rsp+50h] [rbp-20h] BYREF
  const char *v14; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-10h] BYREF
  int v16; // [rsp+90h] [rbp+20h] BYREF
  int v17; // [rsp+98h] [rbp+28h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+38h] BYREF

  lpMem = 0;
  if ( !a1 )
    return (unsigned int)-2147467261;
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  if ( !v3 )
    return (unsigned int)-2147024882;
  DiagTrackStorePath = GetDiagTrackStorePath((unsigned __int16 **)&lpMem);
  if ( DiagTrackStorePath >= 0 )
  {
    DiagTrackStorePath = StringCchPrintfW(v3, 0x104u, L"%s\\%s", lpMem, L"siufloc");
    if ( DiagTrackStorePath >= 0 )
      goto LABEL_16;
    if ( (unsigned int)dword_140028000 <= 2 )
      goto LABEL_16;
    v6 = qword_140028018;
    if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      goto LABEL_16;
    v16 = 551;
    v15[0] = "BuildSiufLocPathForXbox";
    v7 = byte_140023EE9;
    v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufutil\\siufutil.cpp";
    v13 = "StringCchPrintfW failed to build loc folder string.";
    v12 = (const char **)v15;
    v8 = &v13;
  }
  else
  {
    if ( (unsigned int)dword_140028000 <= 2 )
      goto LABEL_16;
    v5 = qword_140028018;
    v6 = qword_140028010;
    if ( (qword_140028010 & 0x400000000000LL) == 0 || (qword_140028018 & 0x400000000000LL) != qword_140028018 )
      goto LABEL_16;
    v16 = 539;
    v13 = "BuildSiufLocPathForXbox";
    v7 = byte_140023F6B;
    v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufutil\\siufutil.cpp";
    v15[0] = "GetDiagTrackStorePath failed.";
    v12 = &v13;
    v8 = (const char **)v15;
  }
  v19 = 0x1000000;
  v17 = DiagTrackStorePath;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
    v6,
    (_DWORD)v7,
    v5,
    v4,
    (__int64)v8,
    (__int64)&v17,
    (__int64)&v14,
    (__int64)v12,
    (__int64)&v16,
    (__int64)&v19);
LABEL_16:
  if ( lpMem )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, lpMem);
  }
  if ( DiagTrackStorePath < 0 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v3);
  }
  return (unsigned int)DiagTrackStorePath;
}

```

## disassembly

```asm
0x140014e08  push    rbp
0x140014e0a  push    rbx
0x140014e0b  push    rsi
0x140014e0c  mov     rbp, rsp
0x140014e0f  sub     rsp, 70h
0x140014e13  mov     [rbp+lpMem], 0
0x140014e1b  test    rcx, rcx
0x140014e1e  jnz     short loc_140014E2A
0x140014e20  mov     ebx, 80004003h
0x140014e25  jmp     loc_14001504A
0x140014e2a  mov     qword ptr [rcx], 0
0x140014e31  call    cs:__imp_GetProcessHeap
0x140014e38  nop     dword ptr [rax+rax+00h]
0x140014e3d  mov     edx, 8; dwFlags
0x140014e42  mov     r8d, 208h; dwBytes
0x140014e48  mov     rcx, rax; hHeap
0x140014e4b  call    cs:__imp_HeapAlloc
0x140014e52  nop     dword ptr [rax+rax+00h]
0x140014e57  mov     rsi, rax
0x140014e5a  test    rax, rax
0x140014e5d  jnz     short loc_140014E69
0x140014e5f  mov     ebx, 8007000Eh
0x140014e64  jmp     loc_14001504A
0x140014e69  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x140014e6d  call    ?GetDiagTrackStorePath@@YAJPEAPEAG@Z; GetDiagTrackStorePath(ushort * *)
0x140014e72  mov     ebx, eax
0x140014e74  test    eax, eax
0x140014e76  jns     loc_140014F20
0x140014e7c  mov     ecx, cs:dword_140028000
0x140014e82  cmp     ecx, 2
0x140014e85  jbe     loc_140014FFE
0x140014e8b  mov     r8, cs:qword_140028018
0x140014e92  mov     rdx, 400000000000h
0x140014e9c  mov     rcx, cs:qword_140028010
0x140014ea3  test    rdx, rcx
0x140014ea6  jz      loc_140014FFE
0x140014eac  mov     rax, r8
0x140014eaf  and     rax, rdx
0x140014eb2  cmp     rax, r8
0x140014eb5  jnz     loc_140014FFE
0x140014ebb  lea     rax, aBuildsiuflocpa_0; "BuildSiufLocPathForXbox"
0x140014ec2  mov     [rbp+arg_0], 21Bh
0x140014ec9  mov     [rbp+var_20], rax
0x140014ecd  lea     rdx, byte_140023F6B
0x140014ed4  lea     rax, aOnecoreBaseDia_2; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014edb  mov     [rbp+var_18], rax
0x140014edf  lea     rax, aGetdiagtrackst; "GetDiagTrackStorePath failed."
0x140014ee6  mov     [rbp+var_10], rax
0x140014eea  lea     rax, [rbp+arg_18]
0x140014eee  mov     [rsp+70h+var_28], rax
0x140014ef3  lea     rax, [rbp+arg_0]
0x140014ef7  mov     [rsp+70h+var_30], rax
0x140014efc  lea     rax, [rbp+var_20]
0x140014f00  mov     [rsp+70h+var_38], rax
0x140014f05  lea     rax, [rbp+var_18]
0x140014f09  mov     [rsp+70h+var_40], rax
0x140014f0e  lea     rax, [rbp+arg_8]
0x140014f12  mov     [rsp+70h+var_48], rax
0x140014f17  lea     rax, [rbp+var_10]
0x140014f1b  jmp     loc_140014FE9
0x140014f20  mov     r9, [rbp+lpMem]
0x140014f24  lea     rax, aSiufloc; "siufloc"
0x140014f2b  lea     r8, aSS_0; "%s\\%s"
0x140014f32  mov     [rsp+70h+var_50], rax
0x140014f37  mov     edx, 104h; unsigned __int64
0x140014f3c  mov     rcx, rsi; unsigned __int16 *
0x140014f3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014f44  mov     ebx, eax
0x140014f46  test    eax, eax
0x140014f48  jns     loc_140014FFE
0x140014f4e  mov     eax, cs:dword_140028000
0x140014f54  cmp     eax, 2
0x140014f57  jbe     loc_140014FFE
0x140014f5d  mov     rcx, cs:qword_140028018
0x140014f64  mov     rdx, 400000000000h
0x140014f6e  mov     rax, cs:qword_140028010
0x140014f75  test    rdx, rax
0x140014f78  jz      loc_140014FFE
0x140014f7e  mov     rax, rcx
0x140014f81  and     rax, rdx
0x140014f84  cmp     rax, rcx
0x140014f87  jnz     short loc_140014FFE
0x140014f89  lea     rax, aBuildsiuflocpa_0; "BuildSiufLocPathForXbox"
0x140014f90  mov     [rbp+arg_0], 227h
0x140014f97  mov     [rbp+var_10], rax
0x140014f9b  lea     rdx, byte_140023EE9
0x140014fa2  lea     rax, aOnecoreBaseDia_2; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140014fa9  mov     [rbp+var_18], rax
0x140014fad  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x140014fb4  mov     [rbp+var_20], rax
0x140014fb8  lea     rax, [rbp+arg_18]
0x140014fbc  mov     [rsp+70h+var_28], rax
0x140014fc1  lea     rax, [rbp+arg_0]
0x140014fc5  mov     [rsp+70h+var_30], rax
0x140014fca  lea     rax, [rbp+var_10]
0x140014fce  mov     [rsp+70h+var_38], rax
0x140014fd3  lea     rax, [rbp+var_18]
0x140014fd7  mov     [rsp+70h+var_40], rax
0x140014fdc  lea     rax, [rbp+arg_8]
0x140014fe0  mov     [rsp+70h+var_48], rax
0x140014fe5  lea     rax, [rbp+var_20]
0x140014fe9  mov     [rsp+70h+var_50], rax
0x140014fee  mov     [rbp+arg_18], 1000000h
0x140014ff6  mov     [rbp+arg_8], ebx
0x140014ff9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140014ffe  cmp     [rbp+lpMem], 0
0x140015003  jz      short loc_140015026
0x140015005  call    cs:__imp_GetProcessHeap
0x14001500c  nop     dword ptr [rax+rax+00h]
0x140015011  mov     r8, [rbp+lpMem]; lpMem
0x140015015  xor     edx, edx; dwFlags
0x140015017  mov     rcx, rax; hHeap
0x14001501a  call    cs:__imp_HeapFree
0x140015021  nop     dword ptr [rax+rax+00h]
0x140015026  test    ebx, ebx
0x140015028  jns     short loc_14001504A
0x14001502a  call    cs:__imp_GetProcessHeap
0x140015031  nop     dword ptr [rax+rax+00h]
0x140015036  mov     r8, rsi; lpMem
0x140015039  xor     edx, edx; dwFlags
0x14001503b  mov     rcx, rax; hHeap
0x14001503e  call    cs:__imp_HeapFree
0x140015045  nop     dword ptr [rax+rax+00h]
0x14001504a  mov     eax, ebx
0x14001504c  add     rsp, 70h
0x140015050  pop     rsi
0x140015051  pop     rbx
0x140015052  pop     rbp
0x140015053  retn
```
