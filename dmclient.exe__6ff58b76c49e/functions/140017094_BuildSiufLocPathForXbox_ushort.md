# BuildSiufLocPathForXbox(ushort * *)

- ea: `0x140017094`
- end: `0x1400172bc`
- name: `?BuildSiufLocPathForXbox@@YAJPEAPEAG@Z`
- size: `552`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140017468`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x140017094`
- `0x1400172c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400170d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400170d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400170bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001729e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400170bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001729e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400172ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400172ac`

## string_xrefs

- `0x14001715f`: `GetDiagTrackStorePath failed.`
- `0x14001713b`: `BuildSiufLocPathForXbox`
- `0x140017209`: `BuildSiufLocPathForXbox`

## pseudocode

```c
__int64 __fastcall BuildSiufLocPathForXbox(unsigned __int16 **a1)
{
  int DiagTrackStorePath; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rsi
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v6; // rcx
  char *v7; // rdx
  const unsigned __int16 **v8; // rax
  HANDLE v9; // rax
  HANDLE v10; // rax
  const unsigned __int16 **v12; // [rsp+38h] [rbp-38h]
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
    if ( (unsigned int)dword_140027000 <= 2 )
      goto LABEL_16;
    v6 = qword_140027018;
    if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      goto LABEL_16;
    v16 = 551;
    v15[0] = "BuildSiufLocPathForXbox";
    v7 = byte_140022EE1;
    v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufutil\\siufutil.cpp";
    v13 = "StringCchPrintfW failed to build loc folder string.";
    v12 = (const unsigned __int16 **)v15;
    v8 = (const unsigned __int16 **)&v13;
  }
  else
  {
    if ( (unsigned int)dword_140027000 <= 2 )
      goto LABEL_16;
    v5 = qword_140027018;
    v6 = qword_140027010;
    if ( (qword_140027010 & 0x400000000000LL) == 0 || (qword_140027018 & 0x400000000000LL) != qword_140027018 )
      goto LABEL_16;
    v16 = 539;
    v13 = "BuildSiufLocPathForXbox";
    v7 = byte_140022F63;
    v14 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufutil\\siufutil.cpp";
    v15[0] = "GetDiagTrackStorePath failed.";
    v12 = (const unsigned __int16 **)&v13;
    v8 = (const unsigned __int16 **)v15;
  }
  v19 = 0x1000000;
  v17 = DiagTrackStorePath;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
    v6,
    (__int64)v7,
    v5,
    v4,
    v8,
    (__int64)&v17,
    (const unsigned __int16 **)&v14,
    v12,
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
0x140017094  push    rbp
0x140017096  push    rbx
0x140017097  push    rsi
0x140017098  mov     rbp, rsp
0x14001709b  sub     rsp, 70h
0x14001709f  mov     [rbp+lpMem], 0
0x1400170a7  test    rcx, rcx
0x1400170aa  jnz     short loc_1400170B6
0x1400170ac  mov     ebx, 80004003h
0x1400170b1  jmp     loc_1400172B2
0x1400170b6  mov     qword ptr [rcx], 0
0x1400170bd  call    cs:__imp_GetProcessHeap
0x1400170c3  mov     edx, 8; dwFlags
0x1400170c8  mov     r8d, 208h; dwBytes
0x1400170ce  mov     rcx, rax; hHeap
0x1400170d1  call    cs:__imp_HeapAlloc
0x1400170d7  mov     rsi, rax
0x1400170da  test    rax, rax
0x1400170dd  jnz     short loc_1400170E9
0x1400170df  mov     ebx, 8007000Eh
0x1400170e4  jmp     loc_1400172B2
0x1400170e9  lea     rcx, [rbp+lpMem]; unsigned __int16 **
0x1400170ed  call    ?GetDiagTrackStorePath@@YAJPEAPEAG@Z; GetDiagTrackStorePath(ushort * *)
0x1400170f2  mov     ebx, eax
0x1400170f4  test    eax, eax
0x1400170f6  jns     loc_1400171A0
0x1400170fc  mov     ecx, cs:dword_140027000
0x140017102  cmp     ecx, 2
0x140017105  jbe     loc_14001727E
0x14001710b  mov     r8, cs:qword_140027018
0x140017112  mov     rdx, 400000000000h
0x14001711c  mov     rcx, cs:qword_140027010
0x140017123  test    rdx, rcx
0x140017126  jz      loc_14001727E
0x14001712c  mov     rax, r8
0x14001712f  and     rax, rdx
0x140017132  cmp     rax, r8
0x140017135  jnz     loc_14001727E
0x14001713b  lea     rax, aBuildsiuflocpa_0; "BuildSiufLocPathForXbox"
0x140017142  mov     [rbp+arg_0], 21Bh
0x140017149  mov     [rbp+var_20], rax
0x14001714d  lea     rdx, byte_140022F63
0x140017154  lea     rax, aOnecoreBaseDia_2; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14001715b  mov     [rbp+var_18], rax
0x14001715f  lea     rax, aGetdiagtrackst; "GetDiagTrackStorePath failed."
0x140017166  mov     [rbp+var_10], rax
0x14001716a  lea     rax, [rbp+arg_18]
0x14001716e  mov     [rsp+70h+var_28], rax
0x140017173  lea     rax, [rbp+arg_0]
0x140017177  mov     [rsp+70h+var_30], rax
0x14001717c  lea     rax, [rbp+var_20]
0x140017180  mov     [rsp+70h+var_38], rax
0x140017185  lea     rax, [rbp+var_18]
0x140017189  mov     [rsp+70h+var_40], rax
0x14001718e  lea     rax, [rbp+arg_8]
0x140017192  mov     [rsp+70h+var_48], rax
0x140017197  lea     rax, [rbp+var_10]
0x14001719b  jmp     loc_140017269
0x1400171a0  mov     r9, [rbp+lpMem]
0x1400171a4  lea     rax, aSiufloc; "siufloc"
0x1400171ab  lea     r8, aSS_0; "%s\\%s"
0x1400171b2  mov     [rsp+70h+var_50], rax
0x1400171b7  mov     edx, 104h; unsigned __int64
0x1400171bc  mov     rcx, rsi; unsigned __int16 *
0x1400171bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400171c4  mov     ebx, eax
0x1400171c6  test    eax, eax
0x1400171c8  jns     loc_14001727E
0x1400171ce  mov     eax, cs:dword_140027000
0x1400171d4  cmp     eax, 2
0x1400171d7  jbe     loc_14001727E
0x1400171dd  mov     rcx, cs:qword_140027018
0x1400171e4  mov     rdx, 400000000000h
0x1400171ee  mov     rax, cs:qword_140027010
0x1400171f5  test    rdx, rax
0x1400171f8  jz      loc_14001727E
0x1400171fe  mov     rax, rcx
0x140017201  and     rax, rdx
0x140017204  cmp     rax, rcx
0x140017207  jnz     short loc_14001727E
0x140017209  lea     rax, aBuildsiuflocpa_0; "BuildSiufLocPathForXbox"
0x140017210  mov     [rbp+arg_0], 227h
0x140017217  mov     [rbp+var_10], rax
0x14001721b  lea     rdx, byte_140022EE1
0x140017222  lea     rax, aOnecoreBaseDia_2; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140017229  mov     [rbp+var_18], rax
0x14001722d  lea     rax, aStringcchprint_1; "StringCchPrintfW failed to build loc fo"...
0x140017234  mov     [rbp+var_20], rax
0x140017238  lea     rax, [rbp+arg_18]
0x14001723c  mov     [rsp+70h+var_28], rax
0x140017241  lea     rax, [rbp+arg_0]
0x140017245  mov     [rsp+70h+var_30], rax
0x14001724a  lea     rax, [rbp+var_10]
0x14001724e  mov     [rsp+70h+var_38], rax
0x140017253  lea     rax, [rbp+var_18]
0x140017257  mov     [rsp+70h+var_40], rax
0x14001725c  lea     rax, [rbp+arg_8]
0x140017260  mov     [rsp+70h+var_48], rax
0x140017265  lea     rax, [rbp+var_20]
0x140017269  mov     [rsp+70h+var_50], rax
0x14001726e  mov     [rbp+arg_18], 1000000h
0x140017276  mov     [rbp+arg_8], ebx
0x140017279  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14001727e  cmp     [rbp+lpMem], 0
0x140017283  jz      short loc_14001729A
0x140017285  call    cs:__imp_GetProcessHeap
0x14001728b  mov     r8, [rbp+lpMem]; lpMem
0x14001728f  xor     edx, edx; dwFlags
0x140017291  mov     rcx, rax; hHeap
0x140017294  call    cs:__imp_HeapFree
0x14001729a  test    ebx, ebx
0x14001729c  jns     short loc_1400172B2
0x14001729e  call    cs:__imp_GetProcessHeap
0x1400172a4  mov     r8, rsi; lpMem
0x1400172a7  xor     edx, edx; dwFlags
0x1400172a9  mov     rcx, rax; hHeap
0x1400172ac  call    cs:__imp_HeapFree
0x1400172b2  mov     eax, ebx
0x1400172b4  add     rsp, 70h
0x1400172b8  pop     rsi
0x1400172b9  pop     rbx
0x1400172ba  pop     rbp
0x1400172bb  retn
```
