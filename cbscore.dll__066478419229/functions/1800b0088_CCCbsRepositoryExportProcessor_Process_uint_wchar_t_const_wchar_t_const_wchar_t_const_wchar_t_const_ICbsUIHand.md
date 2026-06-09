# CCCbsRepositoryExportProcessor::Process(uint,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ICbsUIHandler *,_CbsRequiredAction *,wchar_t * *)

- ea: `0x1800b0088`
- end: `0x1800b0520`
- name: `?Process@CCCbsRepositoryExportProcessor@@UEAAJIPEB_W000PEAUICbsUIHandler@@PEAW4_CbsRequiredAction@@PEAPEA_W@Z`
- size: `1176`
- prototype: `__int64 __fastcall(CCCbsRepositoryExportProcessor *__hidden this, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, struct ICbsUIHandler *, enum _CbsRequiredAction *, wchar_t **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1802b2770`

## callees

- `0x180013250`
- `0x180019bdc`
- `0x180019c10`
- `0x18002a448`
- `0x180049bec`
- `0x180093c4c`
- `0x180095e34`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad1f0`
- `0x1800b0088`
- `0x1800bd218`
- `0x1800c8fbc`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03bf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800b0220`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800b0220`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0238`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800b0238`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b03ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b03ab`

## string_xrefs

- `0x1800b0281`: `Exec: FoD content not found when copying {} to {}; skipping possibly not available FoD`
- `0x1800b02ea`: `Failed to copy {} to {}`

## pseudocode

```c
__int64 __fastcall CCCbsRepositoryExportProcessor::Process(
        CCCbsRepositoryExportProcessor *this,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6,
        struct ICbsUIHandler *a7,
        enum _CbsRequiredAction *a8,
        wchar_t **a9)
{
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // edx
  __int64 v14; // rdx
  __int64 *v15; // rbx
  __int64 v16; // rbx
  __int64 i; // rdi
  int v18; // esi
  WCHAR *v19; // rsi
  LPCWSTR v20; // r14
  signed int v21; // eax
  signed int v22; // r15d
  int v23; // edx
  __int64 v24; // rdx
  signed int LastError; // ebx
  int v26; // edx
  unsigned int v27; // eax
  int v29; // edx
  unsigned int v30; // [rsp+20h] [rbp-89h]
  LPCWSTR lpExistingFileName; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v32[2]; // [rsp+38h] [rbp-71h] BYREF
  void *v33; // [rsp+40h] [rbp-69h] BYREF
  LPCWSTR v34; // [rsp+48h] [rbp-61h] BYREF
  __int128 v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 v36; // [rsp+60h] [rbp-49h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-41h] BYREF
  __int64 v38; // [rsp+70h] [rbp-39h] BYREF
  wchar_t *v39; // [rsp+78h] [rbp-31h] BYREF
  LPCWSTR lpNewFileName; // [rsp+80h] [rbp-29h] BYREF
  _QWORD v41[3]; // [rsp+88h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+3Fh]

  lpFileName = a3;
  if ( a8 )
    *(_DWORD *)a8 = 0;
  if ( a9 )
    *a9 = 0;
  v38 = 0;
  v36 = 0;
  v41[1] = 0;
  v41[0] = &Windows::Rtl::PrivateHeapPool::`vftable';
  v41[2] = 0;
  v35 = 0;
  v11 = ActionListParser::ReadActionList(a3, v41, &v38, &v35);
  v12 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v39) = v11;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to load actions from {}",
        (__int64)&lpFileName);
      lpExistingFileName = (LPCWSTR)&v39;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&lpExistingFileName);
    }
    v14 = 168;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsrepositoryexportexecutionobject.cpp",
      (const char *)v12,
      v30);
    goto LABEL_47;
  }
  v15 = *(__int64 **)(v38 + 112);
  if ( !v15 || !v15[1] )
  {
    v12 = -2146498222;
    LODWORD(lpNewFileName) = -2146498222;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"No download package found in ActionList: {}",
        (__int64)&lpFileName);
      *(_QWORD *)v32 = &lpNewFileName;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v29,
        3,
        (unsigned int)": {}",
        (__int64)v32);
    }
    v14 = 172;
    goto LABEL_46;
  }
  v16 = *v15;
LABEL_12:
  if ( !v16 )
  {
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed deleting {}",
          (__int64)&lpFileName);
        if ( LastError > 0 )
          v27 = (unsigned __int16)LastError | 0x80070000;
        else
          v27 = LastError;
        LODWORD(v39) = v27;
        LOBYTE(v26) = 1;
        *(_QWORD *)v32 = &v39;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {0}",
          (__int64)v32);
      }
      if ( LastError )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xCD,
                (unsigned int)"onecore\\base\\cbs\\core\\cbsrepositoryexportexecutionobject.cpp",
                (const char *)(unsigned int)LastError,
                v30);
        goto LABEL_47;
      }
    }
    Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v41);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v35);
    return 0;
  }
  for ( i = *(_QWORD *)(v16 + 240); ; i = *(_QWORD *)(i + 416) )
  {
    if ( !i )
    {
      v16 = *(_QWORD *)(v16 + 256);
      goto LABEL_12;
    }
    v39 = 0;
    lpExistingFileName = 0;
    lpNewFileName = 0;
    v18 = DuplicateParserString(
            (struct Windows::Rtl::IPoolAllocator *)v41,
            (const struct _LUTF8_STRING *)(i + 72),
            &v39);
    if ( v18 < 0 )
    {
      v24 = 182;
      goto LABEL_33;
    }
    v18 = SczAllocCombinePath2Sz(&lpNewFileName, *((_QWORD *)this - 2), v39);
    if ( v18 < 0 )
    {
      v24 = 183;
      goto LABEL_33;
    }
    v18 = SczAllocCombinePath2Sz(&lpExistingFileName, a4, v39);
    if ( v18 < 0 )
    {
      v24 = 184;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsrepositoryexportexecutionobject.cpp",
        (const char *)(unsigned int)v18,
        v30);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
      v12 = v18;
      goto LABEL_47;
    }
    v19 = (WCHAR *)lpNewFileName;
    v20 = lpExistingFileName;
    if ( CopyFileW(lpExistingFileName, lpNewFileName, 0) )
    {
      SetFileAttributesW(v19, 0x80u);
      goto LABEL_25;
    }
    v21 = GetLastError();
    v22 = v21;
    if ( v21 > 0 )
      v22 = (unsigned __int16)v21 | 0x80070000;
    if ( IsNotFound_HRESULT(v22) )
    {
      v39 = v19;
      v33 = (void *)v20;
      LogAdapter::TraceAtLevelHr<long,wchar_t *,wchar_t const *>(
        1,
        v22,
        (unsigned int)"Exec: FoD content not found when copying {} to {}; skipping possibly not available FoD",
        (unsigned int)&v33,
        (__int64)&v39);
      goto LABEL_25;
    }
    if ( v22 < 0 )
      break;
LABEL_25:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  }
  LODWORD(v39) = v22;
  if ( LogAdapter::g_Logger )
  {
    v33 = v19;
    v34 = v20;
    LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"Failed to copy {} to {}",
      (__int64)&v34,
      (__int64)&v33);
    *(_QWORD *)v32 = &v39;
    LOBYTE(v23) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v23,
      3,
      (unsigned int)": {}",
      (__int64)v32);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC8,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsrepositoryexportexecutionobject.cpp",
    (const char *)(unsigned int)v22,
    v30);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpNewFileName);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpExistingFileName);
  v12 = v22;
LABEL_47:
  Windows::Rtl::PrivateHeapPool::~PrivateHeapPool((Windows::Rtl::PrivateHeapPool *)v41);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v35);
  return v12;
}

```

## disassembly

```asm
0x1800b0088  mov     [rsp-8+arg_8], rbx
0x1800b008d  push    rbp
0x1800b008e  push    rsi
0x1800b008f  push    rdi
0x1800b0090  push    r12
0x1800b0092  push    r13
0x1800b0094  push    r14
0x1800b0096  push    r15
0x1800b0098  lea     rbp, [rsp-7]
0x1800b009d  sub     rsp, 0B0h
0x1800b00a4  mov     rax, cs:__security_cookie
0x1800b00ab  xor     rax, rsp
0x1800b00ae  mov     [rbp+37h+var_40], rax
0x1800b00b2  mov     rdx, [rbp+37h+arg_38]
0x1800b00b6  xor     r15d, r15d
0x1800b00b9  mov     rax, [rbp+37h+arg_40]
0x1800b00c0  mov     r12, r9
0x1800b00c3  mov     [rbp+37h+lpFileName], r8
0x1800b00c7  mov     r10, r8
0x1800b00ca  mov     r13, rcx
0x1800b00cd  test    rdx, rdx
0x1800b00d0  jz      short loc_1800B00D5
0x1800b00d2  mov     [rdx], r15d
0x1800b00d5  test    rax, rax
0x1800b00d8  jz      short loc_1800B00DD
0x1800b00da  mov     [rax], r15
0x1800b00dd  xor     eax, eax
0x1800b00df  mov     [rbp+37h+var_70], r15
0x1800b00e3  mov     [rbp+37h+var_80], rax
0x1800b00e7  lea     r9, [rbp+37h+var_90]
0x1800b00eb  lea     rax, ??_7PrivateHeapPool@Rtl@Windows@@6B@; const Windows::Rtl::PrivateHeapPool::`vftable'
0x1800b00f2  mov     [rbp+37h+var_50], r15
0x1800b00f6  xorps   xmm0, xmm0
0x1800b00f9  mov     [rbp+37h+var_58], rax
0x1800b00fd  lea     r8, [rbp+37h+var_70]
0x1800b0101  mov     [rbp+37h+var_48], r15
0x1800b0105  lea     rdx, [rbp+37h+var_58]
0x1800b0109  mov     rcx, r10
0x1800b010c  movups  [rbp+37h+var_90], xmm0
0x1800b0110  call    ?ReadActionList@ActionListParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUActionListDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; ActionListParser::ReadActionList(wchar_t const * const,Windows::Rtl::IPoolAllocator &,ActionListParser::ActionListDocument * *,Windows::Auto<_LBLOB> *)
0x1800b0115  mov     ebx, eax
0x1800b0117  test    eax, eax
0x1800b0119  jns     short loc_1800B017C
0x1800b011b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0122  mov     dword ptr [rbp+37h+var_68], eax
0x1800b0125  test    rcx, rcx
0x1800b0128  jz      short loc_1800B0172
0x1800b012a  lea     rax, [rbp+37h+lpFileName]
0x1800b012e  mov     edi, 3
0x1800b0133  mov     r8d, edi
0x1800b0136  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b013b  lea     r9, aFailedToLoadAc_2; "Failed to load actions from {}"
0x1800b0142  xor     edx, edx
0x1800b0144  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b0149  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0150  lea     rax, [rbp+37h+var_68]
0x1800b0154  mov     [rbp+37h+lpExistingFileName], rax
0x1800b0158  lea     r9, asc_1802EE7AC; ": {}"
0x1800b015f  lea     rax, [rbp+37h+lpExistingFileName]
0x1800b0163  mov     r8d, edi
0x1800b0166  mov     dl, 1
0x1800b0168  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b016d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0172  mov     edx, 0A8h
0x1800b0177  jmp     loc_1800B04D1
0x1800b017c  mov     rax, [rbp+37h+var_70]
0x1800b0180  mov     rbx, [rax+70h]
0x1800b0184  test    rbx, rbx
0x1800b0187  jz      loc_1800B0470
0x1800b018d  cmp     [rbx+8], r15
0x1800b0191  jz      loc_1800B0470
0x1800b0197  mov     rbx, [rbx]
0x1800b019a  test    rbx, rbx
0x1800b019d  jz      loc_1800B03A7
0x1800b01a3  mov     rdi, [rbx+0F0h]
0x1800b01aa  test    rdi, rdi
0x1800b01ad  jz      loc_1800B02C1
0x1800b01b3  lea     rdx, [rdi+48h]; struct _LUTF8_STRING *
0x1800b01b7  mov     [rbp+37h+var_68], r15
0x1800b01bb  lea     r8, [rbp+37h+var_68]; wchar_t **
0x1800b01bf  mov     [rbp+37h+lpExistingFileName], r15
0x1800b01c3  lea     rcx, [rbp+37h+var_58]; struct Windows::Rtl::IPoolAllocator *
0x1800b01c7  mov     [rbp+37h+lpNewFileName], r15
0x1800b01cb  call    ?DuplicateParserString@@YAJAEAVIPoolAllocator@Rtl@Windows@@AEBU_LUTF8_STRING@@PEAPEA_W@Z; DuplicateParserString(Windows::Rtl::IPoolAllocator &,_LUTF8_STRING const &,wchar_t * *)
0x1800b01d0  mov     esi, eax
0x1800b01d2  test    eax, eax
0x1800b01d4  js      loc_1800B0376
0x1800b01da  mov     r8, [rbp+37h+var_68]
0x1800b01de  lea     rcx, [rbp+37h+lpNewFileName]
0x1800b01e2  mov     rdx, [r13-10h]
0x1800b01e6  call    SczAllocCombinePath2Sz
0x1800b01eb  mov     esi, eax
0x1800b01ed  test    eax, eax
0x1800b01ef  js      loc_1800B036F
0x1800b01f5  mov     r8, [rbp+37h+var_68]
0x1800b01f9  lea     rcx, [rbp+37h+lpExistingFileName]
0x1800b01fd  mov     rdx, r12
0x1800b0200  call    SczAllocCombinePath2Sz
0x1800b0205  mov     esi, eax
0x1800b0207  test    eax, eax
0x1800b0209  js      loc_1800B0368
0x1800b020f  mov     rsi, [rbp+37h+lpNewFileName]
0x1800b0213  xor     r8d, r8d; bFailIfExists
0x1800b0216  mov     r14, [rbp+37h+lpExistingFileName]
0x1800b021a  mov     rdx, rsi; lpNewFileName
0x1800b021d  mov     rcx, r14; lpExistingFileName
0x1800b0220  call    cs:__imp_CopyFileW
0x1800b0227  nop     dword ptr [rax+rax+00h]
0x1800b022c  test    eax, eax
0x1800b022e  jz      short loc_1800B0246
0x1800b0230  mov     edx, 80h; dwFileAttributes
0x1800b0235  mov     rcx, rsi; lpFileName
0x1800b0238  call    cs:__imp_SetFileAttributesW
0x1800b023f  nop     dword ptr [rax+rax+00h]
0x1800b0244  jmp     short loc_1800B02A3
0x1800b0246  call    cs:__imp_GetLastError
0x1800b024d  nop     dword ptr [rax+rax+00h]
0x1800b0252  mov     r15d, eax
0x1800b0255  test    eax, eax
0x1800b0257  jle     short loc_1800B0264
0x1800b0259  movzx   r15d, ax
0x1800b025d  or      r15d, 80070000h
0x1800b0264  mov     ecx, r15d; int
0x1800b0267  call    ?IsNotFound_HRESULT@@YA_NJ@Z; IsNotFound_HRESULT(long)
0x1800b026c  test    al, al
0x1800b026e  jz      short loc_1800B029B
0x1800b0270  lea     rax, [rbp+37h+var_68]
0x1800b0274  mov     [rbp+37h+var_68], rsi
0x1800b0278  lea     r9, [rbp+37h+var_A0]
0x1800b027c  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b0281  lea     r8, aExecFodContent; "Exec: FoD content not found when copyin"...
0x1800b0288  mov     [rbp+37h+var_A0], r14
0x1800b028c  mov     edx, r15d
0x1800b028f  mov     ecx, 1
0x1800b0294  call    ??$TraceAtLevelHr@JPEA_WPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEA_WAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t *,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t * const &,wchar_t const * const &)
0x1800b0299  jmp     short loc_1800B02A0
0x1800b029b  test    r15d, r15d
0x1800b029e  js      short loc_1800B02CD
0x1800b02a0  xor     r15d, r15d
0x1800b02a3  lea     rcx, [rbp+37h+lpNewFileName]
0x1800b02a7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b02ac  lea     rcx, [rbp+37h+lpExistingFileName]
0x1800b02b0  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b02b5  mov     rdi, [rdi+1A0h]
0x1800b02bc  jmp     loc_1800B01AA
0x1800b02c1  mov     rbx, [rbx+100h]
0x1800b02c8  jmp     loc_1800B019A
0x1800b02cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b02d4  mov     dword ptr [rbp+37h+var_68], r15d
0x1800b02d8  test    rcx, rcx
0x1800b02db  jz      short loc_1800B0336
0x1800b02dd  lea     rax, [rbp+37h+var_A0]
0x1800b02e1  mov     [rbp+37h+var_A0], rsi
0x1800b02e5  mov     [rsp+0E0h+var_B8], rax
0x1800b02ea  lea     r9, aFailedToCopyTo; "Failed to copy {} to {}"
0x1800b02f1  lea     rax, [rbp+37h+var_98]
0x1800b02f5  mov     [rbp+37h+var_98], r14
0x1800b02f9  mov     edi, 3
0x1800b02fe  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b0303  mov     r8d, edi
0x1800b0306  xor     edx, edx
0x1800b0308  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1800b030d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0314  lea     rax, [rbp+37h+var_68]
0x1800b0318  mov     qword ptr [rbp+37h+var_A8], rax
0x1800b031c  lea     r9, asc_1802EE7AC; ": {}"
0x1800b0323  lea     rax, [rbp+37h+var_A8]
0x1800b0327  mov     r8d, edi
0x1800b032a  mov     dl, 1
0x1800b032c  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b0331  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0336  mov     rcx, [rbp+3Fh]; this
0x1800b033a  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\core\\cbsrepository"...
0x1800b0341  mov     r9d, r15d; char *
0x1800b0344  mov     edx, 0C8h; void *
0x1800b0349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b034e  lea     rcx, [rbp+37h+lpNewFileName]
0x1800b0352  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b0357  lea     rcx, [rbp+37h+lpExistingFileName]
0x1800b035b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b0360  mov     ebx, r15d
0x1800b0363  jmp     loc_1800B04E4
0x1800b0368  mov     edx, 0B8h
0x1800b036d  jmp     short loc_1800B037B
0x1800b036f  mov     edx, 0B7h
0x1800b0374  jmp     short loc_1800B037B
0x1800b0376  mov     edx, 0B6h; void *
0x1800b037b  mov     rcx, [rbp+3Fh]; this
0x1800b037f  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\core\\cbsrepository"...
0x1800b0386  mov     r9d, esi; char *
0x1800b0389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b038e  lea     rcx, [rbp+37h+lpNewFileName]
0x1800b0392  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b0397  lea     rcx, [rbp+37h+lpExistingFileName]
0x1800b039b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1800b03a0  mov     ebx, esi
0x1800b03a2  jmp     loc_1800B04E4
0x1800b03a7  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x1800b03ab  call    cs:__imp_DeleteFileW
0x1800b03b2  nop     dword ptr [rax+rax+00h]
0x1800b03b7  test    eax, eax
0x1800b03b9  jnz     loc_1800B0457
0x1800b03bf  call    cs:__imp_GetLastError
0x1800b03c6  nop     dword ptr [rax+rax+00h]
0x1800b03cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b03d2  mov     ebx, eax
0x1800b03d4  test    rcx, rcx
0x1800b03d7  jz      short loc_1800B0434
0x1800b03d9  lea     rax, [rbp+37h+lpFileName]
0x1800b03dd  mov     edi, 3
0x1800b03e2  mov     r8d, edi
0x1800b03e5  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b03ea  lea     r9, aFailedDeleting_9; "Failed deleting {}"
0x1800b03f1  xor     edx, edx
0x1800b03f3  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b03f8  test    ebx, ebx
0x1800b03fa  jg      short loc_1800B0400
0x1800b03fc  mov     eax, ebx
0x1800b03fe  jmp     short loc_1800B0408
0x1800b0400  movzx   eax, bx
0x1800b0403  or      eax, 80070000h
0x1800b0408  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b040f  lea     r9, a0; ": {0}"
0x1800b0416  mov     dword ptr [rbp+37h+var_68], eax
0x1800b0419  mov     r8d, edi
0x1800b041c  lea     rax, [rbp+37h+var_68]
0x1800b0420  mov     dl, 1
0x1800b0422  mov     qword ptr [rbp+37h+var_A8], rax
0x1800b0426  lea     rax, [rbp+37h+var_A8]
0x1800b042a  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x1800b042f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b0434  test    ebx, ebx
0x1800b0436  jz      short loc_1800B0457
0x1800b0438  mov     rcx, [rbp+3Fh]; this
0x1800b043c  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\core\\cbsrepository"...
0x1800b0443  mov     r9d, ebx; char *
0x1800b0446  mov     edx, 0CDh; void *
0x1800b044b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b0450  mov     ebx, eax
0x1800b0452  jmp     loc_1800B04E4
0x1800b0457  lea     rcx, [rbp+37h+var_58]; this
0x1800b045b  call    ??1PrivateHeapPool@Rtl@Windows@@UEAA@XZ; Windows::Rtl::PrivateHeapPool::~PrivateHeapPool(void)
0x1800b0460  lea     rcx, [rbp+37h+var_90]
0x1800b0464  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800b0469  xor     eax, eax
0x1800b046b  jmp     loc_1800B04F8
0x1800b0470  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b0477  mov     ebx, 800F0952h
0x1800b047c  mov     dword ptr [rbp+37h+lpNewFileName], ebx
0x1800b047f  test    rcx, rcx
0x1800b0482  jz      short loc_1800B04CC
0x1800b0484  lea     rax, [rbp+37h+lpFileName]
0x1800b0488  mov     edi, 3
0x1800b048d  mov     r8d, edi
0x1800b0490  mov     qword ptr [rsp+0E0h+var_C0], rax
0x1800b0495  lea     r9, aNoDownloadPack; "No download package found in ActionList"...
0x1800b049c  xor     edx, edx
0x1800b049e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800b04a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800b04aa  lea     rax, [rbp+37h+lpNewFileName]
0x1800b04ae  mov     qword ptr [rbp+37h+var_A8], rax
0x1800b04b2  lea     r9, asc_1802EE7AC; ": {}"
0x1800b04b9  lea     rax, [rbp+37h+var_A8]
0x1800b04bd  mov     r8d, edi
0x1800b04c0  mov     dl, 1
0x1800b04c2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800b04c7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800b04cc  mov     edx, 0ACh; void *
0x1800b04d1  mov     rcx, [rbp+3Fh]; this
0x1800b04d5  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\core\\cbsrepository"...
0x1800b04dc  mov     r9d, ebx; char *
0x1800b04df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b04e4  lea     rcx, [rbp+37h+var_58]; this
0x1800b04e8  call    ??1PrivateHeapPool@Rtl@Windows@@UEAA@XZ; Windows::Rtl::PrivateHeapPool::~PrivateHeapPool(void)
0x1800b04ed  lea     rcx, [rbp+37h+var_90]
0x1800b04f1  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800b04f6  mov     eax, ebx
0x1800b04f8  mov     rcx, [rbp+37h+var_40]
0x1800b04fc  xor     rcx, rsp; StackCookie
0x1800b04ff  call    __security_check_cookie
0x1800b0504  mov     rbx, [rsp+0E0h+arg_8]
0x1800b050c  add     rsp, 0B0h
0x1800b0513  pop     r15
0x1800b0515  pop     r14
0x1800b0517  pop     r13
0x1800b0519  pop     r12
0x1800b051b  pop     rdi
0x1800b051c  pop     rsi
0x1800b051d  pop     rbp
0x1800b051e  retn
```
