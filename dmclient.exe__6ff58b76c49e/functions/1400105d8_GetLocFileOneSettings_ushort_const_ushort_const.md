# GetLocFileOneSettings(ushort const *,ushort const *)

- ea: `0x1400105d8`
- end: `0x1400109c9`
- name: `?GetLocFileOneSettings@@YAJPEBG0@Z`
- size: `1009`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x14000b5c4`
- `0x14000fe20`
- `0x1400105d8`
- `0x1400109d0`
- `0x140011fec`
- `0x1400187b2`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010656`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001075b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001083a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010656`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001075b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001083a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001096f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001096f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001097d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010996`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010964`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001097d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010996`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010807`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140010807`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140010816`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140010816`

## string_xrefs

- `0x1400107f4`: `BuildSiufLocPath failed.`

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
  unsigned int v14; // r9d
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
      if ( (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v31 = 0x1000000;
        v32 = "GetLocFileOneSettings";
        v29 = 684;
        v33 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
        v34 = (__int64)"GetUILanguage failed.";
        v30 = UILanguage;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (unsigned int)&byte_140021F27,
          qword_140027018,
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
      if ( UILanguage < 0 && (unsigned int)dword_140027000 > 2 )
      {
        v18 = qword_140027018;
        if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v30 = 743;
          v33 = "GetLocFileOneSettings";
          v19 = byte_140021EC9;
          v32 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\siufloc\\siufloc.cpp";
          v20 = "Failed to get file from web.";
          goto LABEL_31;
        }
      }
    }
  }
  else if ( (unsigned int)dword_140027000 > 2 )
  {
    v18 = qword_140027018;
    if ( (qword_140027010 & 0x400000000000LL) != 0 && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v30 = 700;
      v33 = "GetLocFileOneSettings";
      v19 = byte_140021E0D;
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
0x1400105d8  mov     [rsp-8+arg_10], rbx
0x1400105dd  mov     [rsp-8+arg_18], rsi
0x1400105e2  push    rbp
0x1400105e3  push    rdi
0x1400105e4  push    r12
0x1400105e6  push    r14
0x1400105e8  push    r15
0x1400105ea  lea     rbp, [rsp-1E0h]
0x1400105f2  sub     rsp, 2E0h
0x1400105f9  mov     rax, cs:__security_cookie
0x140010600  xor     rax, rsp
0x140010603  mov     [rbp+200h+var_30], rax
0x14001060a  mov     r15, rdx
0x14001060d  mov     [rsp+300h+var_288], 0
0x140010615  mov     r12, rcx
0x140010618  xor     edx, edx; Val
0x14001061a  lea     rcx, [rbp+200h+FindFileData]; void *
0x14001061e  mov     r8d, 250h; Size
0x140010624  call    memset_0
0x140010629  test    r12, r12
0x14001062c  jnz     short loc_140010638
0x14001062e  mov     ebx, 80004003h
0x140010633  jmp     loc_14001099C
0x140010638  xor     edi, edi
0x14001063a  xor     r14d, r14d
0x14001063d  test    r15, r15
0x140010640  jnz     loc_140010747
0x140010646  call    cs:__imp_GetProcessHeap
0x14001064c  mov     rcx, rax; hHeap
0x14001064f  lea     edx, [rdi+8]; dwFlags
0x140010652  lea     r8d, [rdi+16h]; dwBytes
0x140010656  call    cs:__imp_HeapAlloc
0x14001065c  mov     rdi, rax
0x14001065f  test    rax, rax
0x140010662  jnz     short loc_14001066E
0x140010664  mov     ebx, 8007000Eh
0x140010669  jmp     loc_14001099C
0x14001066e  mov     rcx, rax; lpsz
0x140010671  call    ?GetUILanguage@@YAJPEAGI@Z; GetUILanguage(ushort *,uint)
0x140010676  mov     ebx, eax
0x140010678  test    eax, eax
0x14001067a  jns     loc_140010747
0x140010680  mov     ecx, cs:dword_140027000
0x140010686  xor     esi, esi
0x140010688  cmp     ecx, 2
0x14001068b  jbe     loc_140010956
0x140010691  mov     r8, cs:qword_140027018
0x140010698  mov     rdx, 400000000000h
0x1400106a2  mov     rcx, cs:qword_140027010
0x1400106a9  test    rdx, rcx
0x1400106ac  jz      loc_140010956
0x1400106b2  mov     rax, r8
0x1400106b5  and     rax, rdx
0x1400106b8  cmp     rax, r8
0x1400106bb  jnz     loc_140010956
0x1400106c1  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x1400106c8  mov     [rsp+300h+var_2A8], 1000000h
0x1400106d1  mov     [rsp+300h+var_2A0], rax
0x1400106d6  lea     rdx, byte_140021F27
0x1400106dd  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400106e4  mov     [rsp+300h+var_2B0], 2ACh
0x1400106ec  mov     [rsp+300h+var_298], rax
0x1400106f1  lea     rax, aGetuilanguageF; "GetUILanguage failed."
0x1400106f8  mov     [rsp+300h+var_290], rax
0x1400106fd  lea     rax, [rsp+300h+var_2A8]
0x140010702  mov     [rsp+300h+var_2B8], rax
0x140010707  lea     rax, [rsp+300h+var_2B0]
0x14001070c  mov     [rsp+300h+var_2C0], rax
0x140010711  lea     rax, [rsp+300h+var_2A0]
0x140010716  mov     [rsp+300h+var_2C8], rax
0x14001071b  lea     rax, [rsp+300h+var_298]
0x140010720  mov     [rsp+300h+var_2D0], rax
0x140010725  lea     rax, [rsp+300h+var_2AC]
0x14001072a  mov     [rsp+300h+var_2D8], rax
0x14001072f  lea     rax, [rsp+300h+var_290]
0x140010734  mov     [rsp+300h+var_2E0], rax
0x140010739  mov     [rsp+300h+var_2AC], ebx
0x14001073d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010742  jmp     loc_140010956
0x140010747  call    cs:__imp_GetProcessHeap
0x14001074d  mov     edx, 8; dwFlags
0x140010752  mov     r8d, 208h; dwBytes
0x140010758  mov     rcx, rax; hHeap
0x14001075b  call    cs:__imp_HeapAlloc
0x140010761  mov     rsi, rax
0x140010764  test    rax, rax
0x140010767  jnz     short loc_140010773
0x140010769  mov     ebx, 8007000Eh
0x14001076e  jmp     loc_140010951
0x140010773  test    r15, r15
0x140010776  mov     rdx, rdi
0x140010779  mov     r8, rsi; unsigned __int16 *
0x14001077c  mov     rcx, r12; unsigned __int16 *
0x14001077f  cmovnz  rdx, r15; unsigned __int16 *
0x140010783  call    ?BuildSiufLocPath@@YAJPEBG0PEAGI@Z; BuildSiufLocPath(ushort const *,ushort const *,ushort *,uint)
0x140010788  mov     ebx, eax
0x14001078a  test    eax, eax
0x14001078c  jns     short loc_140010800
0x14001078e  mov     eax, cs:dword_140027000
0x140010794  cmp     eax, 2
0x140010797  jbe     loc_140010951
0x14001079d  mov     rcx, cs:qword_140027018
0x1400107a4  mov     rdx, 400000000000h
0x1400107ae  mov     rax, cs:qword_140027010
0x1400107b5  test    rdx, rax
0x1400107b8  jz      loc_140010951
0x1400107be  mov     rax, rcx
0x1400107c1  and     rax, rdx
0x1400107c4  cmp     rax, rcx
0x1400107c7  jnz     loc_140010951
0x1400107cd  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x1400107d4  mov     [rsp+300h+var_2AC], 2BCh
0x1400107dc  mov     [rsp+300h+var_298], rax
0x1400107e1  lea     rdx, byte_140021E0D
0x1400107e8  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400107ef  mov     [rsp+300h+var_2A0], rax
0x1400107f4  lea     rax, aBuildsiuflocpa_1; "BuildSiufLocPath failed."
0x1400107fb  jmp     loc_1400108FE
0x140010800  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x140010804  mov     rcx, rsi; lpFileName
0x140010807  call    cs:__imp_FindFirstFileW
0x14001080d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010811  jz      short loc_140010826
0x140010813  mov     rcx, rax; hFindFile
0x140010816  call    cs:__imp_FindClose
0x14001081c  mov     ebx, 5DD0C9h
0x140010821  jmp     loc_140010951
0x140010826  call    cs:__imp_GetProcessHeap
0x14001082c  mov     edx, 8; dwFlags
0x140010831  mov     r8d, 208h; dwBytes
0x140010837  mov     rcx, rax; hHeap
0x14001083a  call    cs:__imp_HeapAlloc
0x140010840  mov     r14, rax
0x140010843  test    rax, rax
0x140010846  jz      loc_140010769
0x14001084c  mov     r9, r12
0x14001084f  lea     r8, aScenarioidS; "?scenarioId=%s"
0x140010856  mov     edx, 104h; unsigned __int64
0x14001085b  mov     rcx, rax; unsigned __int16 *
0x14001085e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010863  mov     ebx, eax
0x140010865  test    eax, eax
0x140010867  js      loc_140010951
0x14001086d  test    r15, r15
0x140010870  lea     r9, [rsp+300h+var_288]; unsigned int *
0x140010875  mov     r8, rdi
0x140010878  mov     rdx, rsi; unsigned __int16 *
0x14001087b  cmovnz  r8, r15; unsigned __int16 *
0x14001087f  mov     rcx, r14; unsigned __int16 *
0x140010882  call    ?GetFileFromOneSettings@@YAJPEBG00PEAK@Z; GetFileFromOneSettings(ushort const *,ushort const *,ushort const *,ulong *)
0x140010887  mov     ebx, eax
0x140010889  test    eax, eax
0x14001088b  jns     loc_140010951
0x140010891  mov     eax, cs:dword_140027000
0x140010897  cmp     eax, 2
0x14001089a  jbe     loc_140010951
0x1400108a0  mov     rcx, cs:qword_140027018
0x1400108a7  mov     rdx, 400000000000h
0x1400108b1  mov     rax, cs:qword_140027010
0x1400108b8  test    rdx, rax
0x1400108bb  jz      loc_140010951
0x1400108c1  mov     rax, rcx
0x1400108c4  and     rax, rdx
0x1400108c7  cmp     rax, rcx
0x1400108ca  jnz     loc_140010951
0x1400108d0  lea     rax, aGetlocfileones; "GetLocFileOneSettings"
0x1400108d7  mov     [rsp+300h+var_2AC], 2E7h
0x1400108df  mov     [rsp+300h+var_298], rax
0x1400108e4  lea     rdx, byte_140021EC9
0x1400108eb  lea     rax, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400108f2  mov     [rsp+300h+var_2A0], rax
0x1400108f7  lea     rax, aFailedToGetFil; "Failed to get file from web."
0x1400108fe  mov     [rsp+300h+var_2A8], rax
0x140010903  lea     rax, [rsp+300h+var_290]
0x140010908  mov     [rsp+300h+var_2B8], rax
0x14001090d  lea     rax, [rsp+300h+var_2AC]
0x140010912  mov     [rsp+300h+var_2C0], rax
0x140010917  lea     rax, [rsp+300h+var_298]
0x14001091c  mov     [rsp+300h+var_2C8], rax
0x140010921  lea     rax, [rsp+300h+var_2A0]
0x140010926  mov     [rsp+300h+var_2D0], rax
0x14001092b  lea     rax, [rsp+300h+var_2B0]
0x140010930  mov     [rsp+300h+var_2D8], rax
0x140010935  lea     rax, [rsp+300h+var_2A8]
0x14001093a  mov     [rsp+300h+var_2E0], rax
0x14001093f  mov     [rsp+300h+var_290], 1000000h
0x140010948  mov     [rsp+300h+var_2B0], ebx
0x14001094c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140010951  test    rdi, rdi
0x140010954  jz      short loc_14001096A
0x140010956  call    cs:__imp_GetProcessHeap
0x14001095c  mov     r8, rdi; lpMem
0x14001095f  xor     edx, edx; dwFlags
0x140010961  mov     rcx, rax; hHeap
0x140010964  call    cs:__imp_HeapFree
0x14001096a  test    rsi, rsi
0x14001096d  jz      short loc_140010983
0x14001096f  call    cs:__imp_GetProcessHeap
0x140010975  mov     r8, rsi; lpMem
0x140010978  xor     edx, edx; dwFlags
0x14001097a  mov     rcx, rax; hHeap
0x14001097d  call    cs:__imp_HeapFree
0x140010983  test    r14, r14
0x140010986  jz      short loc_14001099C
0x140010988  call    cs:__imp_GetProcessHeap
0x14001098e  mov     r8, r14; lpMem
0x140010991  xor     edx, edx; dwFlags
0x140010993  mov     rcx, rax; hHeap
0x140010996  call    cs:__imp_HeapFree
0x14001099c  mov     eax, ebx
0x14001099e  mov     rcx, [rbp+200h+var_30]
0x1400109a5  xor     rcx, rsp; StackCookie
0x1400109a8  call    __security_check_cookie
0x1400109ad  lea     r11, [rsp+300h+var_20]
0x1400109b5  mov     rbx, [r11+40h]
0x1400109b9  mov     rsi, [r11+48h]
0x1400109bd  mov     rsp, r11
0x1400109c0  pop     r15
0x1400109c2  pop     r14
0x1400109c4  pop     r12
0x1400109c6  pop     rdi
0x1400109c7  pop     rbp
0x1400109c8  retn
```
