# GetLocFileOneSettings(ushort const *,ushort const *)

- ea: `0x140010c40`
- end: `0x140011086`
- name: `?GetLocFileOneSettings@@YAJPEBG0@Z`
- size: `1094`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x14000b904`
- `0x1400103f8`
- `0x140010c40`
- `0x14001108c`
- `0x140012928`
- `0x1400195e2`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010cc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010ecc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010cc4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010ecc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010dbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010eb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010fee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011038`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010dbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010eb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010fee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011013`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011038`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011027`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001104c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011002`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011027`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001104c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010e87`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010e87`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140010e9c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140010e9c`

## string_xrefs

- `0x140010e74`: `BuildSiufLocPath failed.`

## pseudocode

```c
__int64 __fastcall GetLocFileOneSettings(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int UILanguage; // ebx
  WCHAR *v5; // rdi
  unsigned __int16 *v6; // r14
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  unsigned int v9; // edx
  int v10; // r9d
  WCHAR *v11; // rsi
  HANDLE v12; // rax
  unsigned __int16 *v13; // rax
  int v14; // r9d
  const unsigned __int16 *v15; // rdx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  char *v19; // rdx
  const char *v20; // rax
  HANDLE FirstFileW; // rax
  HANDLE v22; // rax
  unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // r8
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  const char *v32; // [rsp+60h] [rbp-A0h] BYREF
  const char *v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-80h] BYREF

  v35 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
    return (unsigned int)-2147467261;
  v5 = 0;
  v6 = 0;
  if ( !a2 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x16u);
    v5 = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    UILanguage = GetUILanguage(v8, v9);
    if ( UILanguage < 0 )
    {
      v11 = 0;
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v31 = 0x1000000;
        v32 = "GetLocFileOneSettings";
        v29 = 684;
        v33 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v34 = (__int64)"GetUILanguage failed.";
        v30 = UILanguage;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)&byte_140022F2F,
          qword_140028018,
          v10,
          (__int64)&v34,
          (__int64)&v30,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v29,
          (__int64)&v31);
      }
      goto LABEL_33;
    }
  }
  v12 = GetProcessHeap();
  v13 = (unsigned __int16 *)HeapAlloc(v12, 8u, 0x208u);
  v11 = v13;
  if ( !v13 )
    goto LABEL_12;
  v15 = v5;
  if ( a2 )
    v15 = a2;
  UILanguage = BuildSiufLocPath(a1, v15, v13, v14);
  if ( UILanguage >= 0 )
  {
    FirstFileW = FindFirstFileW(v11, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      FindClose(FirstFileW);
      UILanguage = 6148297;
      goto LABEL_32;
    }
    v22 = GetProcessHeap();
    v23 = (unsigned __int16 *)HeapAlloc(v22, 8u, 0x208u);
    v6 = v23;
    if ( !v23 )
    {
LABEL_12:
      UILanguage = -2147024882;
      goto LABEL_32;
    }
    UILanguage = StringCchPrintfW(v23, 0x104u, L"?scenarioId=%s", a1);
    if ( UILanguage >= 0 )
    {
      v24 = v5;
      if ( a2 )
        v24 = a2;
      UILanguage = GetFileFromOneSettings(v6, v11, v24, &v35);
      if ( UILanguage < 0 && (unsigned int)dword_140028000 > 2 )
      {
        v18 = qword_140028018;
        if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v30 = 743;
          v33 = "GetLocFileOneSettings";
          v19 = byte_140022ED1;
          v32 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
          v20 = "Failed to get file from web.";
          goto LABEL_31;
        }
      }
    }
  }
  else if ( (unsigned int)dword_140028000 > 2 )
  {
    v18 = qword_140028018;
    if ( (qword_140028010 & 0x400000000000LL) != 0 && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v30 = 700;
      v33 = "GetLocFileOneSettings";
      v19 = byte_140022E15;
      v32 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
      v20 = "BuildSiufLocPath failed.";
LABEL_31:
      v31 = (__int64)v20;
      v34 = 0x1000000;
      v29 = UILanguage;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v18,
        (_DWORD)v19,
        v16,
        v17,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v30,
        (__int64)&v34);
    }
  }
LABEL_32:
  if ( v5 )
  {
LABEL_33:
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v5);
  }
  if ( v11 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v11);
  }
  if ( v6 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v6);
  }
  return (unsigned int)UILanguage;
}

```

## disassembly

```asm
0x140010c40  mov     [rsp-8+arg_10], rbx
0x140010c45  mov     [rsp-8+arg_18], rsi
0x140010c4a  push    rbp
0x140010c4b  push    rdi
0x140010c4c  push    r12
0x140010c4e  push    r14
0x140010c50  push    r15
0x140010c52  lea     rbp, [rsp-1E0h]
0x140010c5a  sub     rsp, 2E0h
0x140010c61  mov     rax, cs:__security_cookie
0x140010c68  xor     rax, rsp
0x140010c6b  mov     [rbp+200h+var_30], rax
0x140010c72  mov     r15, rdx
0x140010c75  mov     [rsp+300h+var_288], 0
0x140010c7d  mov     r12, rcx
0x140010c80  xor     edx, edx; Val
0x140010c82  lea     rcx, [rbp+200h+FindFileData]; void *
0x140010c86  mov     r8d, 250h; Size
0x140010c8c  call    memset_0
0x140010c91  test    r12, r12
0x140010c94  jnz     short loc_140010CA0
0x140010c96  mov     ebx, 80004003h
0x140010c9b  jmp     loc_140011058
0x140010ca0  xor     edi, edi
0x140010ca2  xor     r14d, r14d
0x140010ca5  test    r15, r15
0x140010ca8  jnz     loc_140010DBB
0x140010cae  call    cs:__imp_GetProcessHeap
0x140010cb5  nop     dword ptr [rax+rax+00h]
0x140010cba  mov     rcx, rax; hHeap
0x140010cbd  lea     edx, [rdi+8]; dwFlags
0x140010cc0  lea     r8d, [rdi+16h]; dwBytes
0x140010cc4  call    cs:__imp_HeapAlloc
0x140010ccb  nop     dword ptr [rax+rax+00h]
0x140010cd0  mov     rdi, rax
0x140010cd3  test    rax, rax
0x140010cd6  jnz     short loc_140010CE2
0x140010cd8  mov     ebx, 8007000Eh
0x140010cdd  jmp     loc_140011058
0x140010ce2  mov     rcx, rax; lpsz
0x140010ce5  call    ?GetUILanguage@@YAJPEAGI@Z; GetUILanguage(ushort *,uint)
0x140010cea  mov     ebx, eax
0x140010cec  test    eax, eax
0x140010cee  jns     loc_140010DBB
0x140010cf4  mov     ecx, cs:dword_140028000
0x140010cfa  xor     esi, esi
0x140010cfc  cmp     ecx, 2
0x140010cff  jbe     loc_140010FEE
0x140010d05  mov     r8, cs:qword_140028018
0x140010d0c  mov     rdx, 400000000000h
0x140010d16  mov     rcx, cs:qword_140028010
0x140010d1d  test    rdx, rcx
0x140010d20  jz      loc_140010FEE
0x140010d26  mov     rax, r8
0x140010d29  and     rax, rdx
0x140010d2c  cmp     rax, r8
0x140010d2f  jnz     loc_140010FEE
0x140010d35  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x140010d3c  mov     [rsp+300h+var_2A8], 1000000h
0x140010d45  mov     [rsp+300h+var_2A0], rax
0x140010d4a  lea     rdx, byte_140022F2F
0x140010d51  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010d58  mov     [rsp+300h+var_2B0], 2ACh
0x140010d60  mov     [rsp+300h+var_298], rax
0x140010d65  lea     rax, aGetuilanguageF; "GetUILanguage failed."
0x140010d6c  mov     [rsp+300h+var_290], rax
0x140010d71  lea     rax, [rsp+300h+var_2A8]
0x140010d76  mov     [rsp+300h+var_2B8], rax
0x140010d7b  lea     rax, [rsp+300h+var_2B0]
0x140010d80  mov     [rsp+300h+var_2C0], rax
0x140010d85  lea     rax, [rsp+300h+var_2A0]
0x140010d8a  mov     [rsp+300h+var_2C8], rax
0x140010d8f  lea     rax, [rsp+300h+var_298]
0x140010d94  mov     [rsp+300h+var_2D0], rax
0x140010d99  lea     rax, [rsp+300h+var_2AC]
0x140010d9e  mov     [rsp+300h+var_2D8], rax
0x140010da3  lea     rax, [rsp+300h+var_290]
0x140010da8  mov     [rsp+300h+var_2E0], rax
0x140010dad  mov     [rsp+300h+var_2AC], ebx
0x140010db1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010db6  jmp     loc_140010FEE
0x140010dbb  call    cs:__imp_GetProcessHeap
0x140010dc2  nop     dword ptr [rax+rax+00h]
0x140010dc7  mov     edx, 8; dwFlags
0x140010dcc  mov     r8d, 208h; dwBytes
0x140010dd2  mov     rcx, rax; hHeap
0x140010dd5  call    cs:__imp_HeapAlloc
0x140010ddc  nop     dword ptr [rax+rax+00h]
0x140010de1  mov     rsi, rax
0x140010de4  test    rax, rax
0x140010de7  jnz     short loc_140010DF3
0x140010de9  mov     ebx, 8007000Eh
0x140010dee  jmp     loc_140010FE9
0x140010df3  test    r15, r15
0x140010df6  mov     rdx, rdi
0x140010df9  mov     r8, rsi; unsigned __int16 *
0x140010dfc  mov     rcx, r12; unsigned __int16 *
0x140010dff  cmovnz  rdx, r15; unsigned __int16 *
0x140010e03  call    ?BuildSiufLocPath@@YAJPEBG0PEAGI@Z; BuildSiufLocPath(ushort const *,ushort const *,ushort *,uint)
0x140010e08  mov     ebx, eax
0x140010e0a  test    eax, eax
0x140010e0c  jns     short loc_140010E80
0x140010e0e  mov     eax, cs:dword_140028000
0x140010e14  cmp     eax, 2
0x140010e17  jbe     loc_140010FE9
0x140010e1d  mov     rcx, cs:qword_140028018
0x140010e24  mov     rdx, 400000000000h
0x140010e2e  mov     rax, cs:qword_140028010
0x140010e35  test    rdx, rax
0x140010e38  jz      loc_140010FE9
0x140010e3e  mov     rax, rcx
0x140010e41  and     rax, rdx
0x140010e44  cmp     rax, rcx
0x140010e47  jnz     loc_140010FE9
0x140010e4d  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x140010e54  mov     [rsp+300h+var_2AC], 2BCh
0x140010e5c  mov     [rsp+300h+var_298], rax
0x140010e61  lea     rdx, byte_140022E15
0x140010e68  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010e6f  mov     [rsp+300h+var_2A0], rax
0x140010e74  lea     rax, aBuildsiuflocpa_1; "BuildSiufLocPath failed."
0x140010e7b  jmp     loc_140010F96
0x140010e80  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x140010e84  mov     rcx, rsi; lpFileName
0x140010e87  call    cs:__imp_FindFirstFileW
0x140010e8e  nop     dword ptr [rax+rax+00h]
0x140010e93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010e97  jz      short loc_140010EB2
0x140010e99  mov     rcx, rax; hFindFile
0x140010e9c  call    cs:__imp_FindClose
0x140010ea3  nop     dword ptr [rax+rax+00h]
0x140010ea8  mov     ebx, 5DD0C9h
0x140010ead  jmp     loc_140010FE9
0x140010eb2  call    cs:__imp_GetProcessHeap
0x140010eb9  nop     dword ptr [rax+rax+00h]
0x140010ebe  mov     edx, 8; dwFlags
0x140010ec3  mov     r8d, 208h; dwBytes
0x140010ec9  mov     rcx, rax; hHeap
0x140010ecc  call    cs:__imp_HeapAlloc
0x140010ed3  nop     dword ptr [rax+rax+00h]
0x140010ed8  mov     r14, rax
0x140010edb  test    rax, rax
0x140010ede  jz      loc_140010DE9
0x140010ee4  mov     r9, r12
0x140010ee7  lea     r8, aScenarioidS; "?scenarioId=%s"
0x140010eee  mov     edx, 104h; unsigned __int64
0x140010ef3  mov     rcx, rax; unsigned __int16 *
0x140010ef6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010efb  mov     ebx, eax
0x140010efd  test    eax, eax
0x140010eff  js      loc_140010FE9
0x140010f05  test    r15, r15
0x140010f08  lea     r9, [rsp+300h+var_288]; unsigned int *
0x140010f0d  mov     r8, rdi
0x140010f10  mov     rdx, rsi; unsigned __int16 *
0x140010f13  cmovnz  r8, r15; unsigned __int16 *
0x140010f17  mov     rcx, r14; unsigned __int16 *
0x140010f1a  call    ?GetFileFromOneSettings@@YAJPEBG00PEAK@Z; GetFileFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *)
0x140010f1f  mov     ebx, eax
0x140010f21  test    eax, eax
0x140010f23  jns     loc_140010FE9
0x140010f29  mov     eax, cs:dword_140028000
0x140010f2f  cmp     eax, 2
0x140010f32  jbe     loc_140010FE9
0x140010f38  mov     rcx, cs:qword_140028018
0x140010f3f  mov     rdx, 400000000000h
0x140010f49  mov     rax, cs:qword_140028010
0x140010f50  test    rdx, rax
0x140010f53  jz      loc_140010FE9
0x140010f59  mov     rax, rcx
0x140010f5c  and     rax, rdx
0x140010f5f  cmp     rax, rcx
0x140010f62  jnz     loc_140010FE9
0x140010f68  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x140010f6f  mov     [rsp+300h+var_2AC], 2E7h
0x140010f77  mov     [rsp+300h+var_298], rax
0x140010f7c  lea     rdx, byte_140022ED1
0x140010f83  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140010f8a  mov     [rsp+300h+var_2A0], rax
0x140010f8f  lea     rax, aFailedToGetFil; "Failed to get file from web."
0x140010f96  mov     [rsp+300h+var_2A8], rax
0x140010f9b  lea     rax, [rsp+300h+var_290]
0x140010fa0  mov     [rsp+300h+var_2B8], rax
0x140010fa5  lea     rax, [rsp+300h+var_2AC]
0x140010faa  mov     [rsp+300h+var_2C0], rax
0x140010faf  lea     rax, [rsp+300h+var_298]
0x140010fb4  mov     [rsp+300h+var_2C8], rax
0x140010fb9  lea     rax, [rsp+300h+var_2A0]
0x140010fbe  mov     [rsp+300h+var_2D0], rax
0x140010fc3  lea     rax, [rsp+300h+var_2B0]
0x140010fc8  mov     [rsp+300h+var_2D8], rax
0x140010fcd  lea     rax, [rsp+300h+var_2A8]
0x140010fd2  mov     [rsp+300h+var_2E0], rax
0x140010fd7  mov     [rsp+300h+var_290], 1000000h
0x140010fe0  mov     [rsp+300h+var_2B0], ebx
0x140010fe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010fe9  test    rdi, rdi
0x140010fec  jz      short loc_14001100E
0x140010fee  call    cs:__imp_GetProcessHeap
0x140010ff5  nop     dword ptr [rax+rax+00h]
0x140010ffa  mov     r8, rdi; lpMem
0x140010ffd  xor     edx, edx; dwFlags
0x140010fff  mov     rcx, rax; hHeap
0x140011002  call    cs:__imp_HeapFree
0x140011009  nop     dword ptr [rax+rax+00h]
0x14001100e  test    rsi, rsi
0x140011011  jz      short loc_140011033
0x140011013  call    cs:__imp_GetProcessHeap
0x14001101a  nop     dword ptr [rax+rax+00h]
0x14001101f  mov     r8, rsi; lpMem
0x140011022  xor     edx, edx; dwFlags
0x140011024  mov     rcx, rax; hHeap
0x140011027  call    cs:__imp_HeapFree
0x14001102e  nop     dword ptr [rax+rax+00h]
0x140011033  test    r14, r14
0x140011036  jz      short loc_140011058
0x140011038  call    cs:__imp_GetProcessHeap
0x14001103f  nop     dword ptr [rax+rax+00h]
0x140011044  mov     r8, r14; lpMem
0x140011047  xor     edx, edx; dwFlags
0x140011049  mov     rcx, rax; hHeap
0x14001104c  call    cs:__imp_HeapFree
0x140011053  nop     dword ptr [rax+rax+00h]
0x140011058  mov     eax, ebx
0x14001105a  mov     rcx, [rbp+200h+var_30]
0x140011061  xor     rcx, rsp; StackCookie
0x140011064  call    __security_check_cookie
0x140011069  lea     r11, [rsp+300h+var_20]
0x140011071  mov     rbx, [r11+40h]
0x140011075  mov     rsi, [r11+48h]
0x140011079  mov     rsp, r11
0x14001107c  pop     r15
0x14001107e  pop     r14
0x140011080  pop     r12
0x140011082  pop     rdi
0x140011083  pop     rbp
0x140011084  retn
```
