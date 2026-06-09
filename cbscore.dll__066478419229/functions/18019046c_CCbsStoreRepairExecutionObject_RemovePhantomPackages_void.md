# CCbsStoreRepairExecutionObject::RemovePhantomPackages(void)

- ea: `0x18019046c`
- end: `0x1801907ac`
- name: `?RemovePhantomPackages@CCbsStoreRepairExecutionObject@@IEAAJXZ`
- size: `832`
- prototype: `__int64 __fastcall(CCbsStoreRepairExecutionObject *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x180189b14`

## callees

- `0x180013018`
- `0x180013250`
- `0x1800132a4`
- `0x1800261e0`
- `0x180042448`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b980c`
- `0x1800d7298`
- `0x1800eb920`
- `0x18019046c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019063c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801906d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019063c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801906d6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019061d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801906b7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18019061d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801906b7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019062c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801906c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18019062c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801906c6`

## string_xrefs

- `0x180190781`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x1801905c6`: `Unable to delete Package key: {}`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::RemovePhantomPackages(CCbsStoreRepairExecutionObject *this)
{
  unsigned int v1; // esi
  __int64 v3; // rcx
  int StoreObject; // eax
  unsigned int v5; // ebx
  int v6; // edx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  const wchar_t **v9; // rdi
  int v10; // r14d
  const wchar_t **v11; // r13
  int v12; // eax
  int v13; // edx
  int v14; // eax
  const wchar_t **v15; // r9
  const char *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  const WCHAR *v19; // rbx
  int v20; // edx
  signed int LastError; // eax
  const WCHAR *v22; // rbx
  int v23; // edx
  signed int v24; // eax
  __int64 *v26; // [rsp+20h] [rbp-60h]
  const WCHAR *v27; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR v28; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-40h] BYREF
  int v30; // [rsp+48h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-30h] BYREF
  int v32; // [rsp+58h] [rbp-28h]
  __int128 v33; // [rsp+60h] [rbp-20h]
  __int64 v34; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v1 = 0;
  lpFileName = 0;
  v3 = *((_QWORD *)this + 6);
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v26 = &v31;
  StoreObject = CCbsSession::GetStoreObject(v3, 0, 2);
  v5 = StoreObject;
  if ( StoreObject >= 0 )
  {
    v9 = (const wchar_t **)*((_QWORD *)this + 40);
    v10 = 0;
    v11 = &v9[*((_QWORD *)this + 38)];
    while ( 1 )
    {
      if ( v9 == v11 )
      {
        if ( v10 < 0 )
          v1 = v10;
        CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v31);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v28);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
        return v1;
      }
      v12 = SczAllocFormatted(&lpFileName, L"%ws%ws.cat", *((_QWORD *)this + 8), *v9, v26);
      v5 = v12;
      if ( v12 < 0 )
      {
        v8 = 2646;
        goto LABEL_38;
      }
      v12 = SczAllocFormatted(&v28, L"%ws%ws.mum", *((_QWORD *)this + 8), *v9);
      v5 = v12;
      if ( v12 < 0 )
      {
        v8 = 2648;
LABEL_38:
        v7 = (unsigned int)v12;
        goto LABEL_39;
      }
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v13) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v13,
          1,
          (unsigned int)"Repr: Removing Phantom Package key: {}",
          (__int64)v9);
      }
      v14 = CCbsStoreObject::DeleteChild((CCbsStoreObject *)&v31, *v9);
      v1 = v14;
      if ( v14 < 0 )
        break;
      v19 = lpFileName;
      if ( (unsigned int)DoesFileExist(lpFileName, 0) )
      {
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v20) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v20,
            1,
            (unsigned int)"Repr: Removing Phantom Package: {}.cat",
            (__int64)v9);
        }
        SetFileAttributesW(v19, 0x80u);
        if ( !DeleteFileW(v19) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v27 = v19;
          if ( LastError < 0 )
            LogAdapter::TraceAtLevelHr<long,wchar_t const *>(3, (unsigned int)LastError, "Failed deleting {}", &v27);
        }
      }
      v22 = v28;
      if ( (unsigned int)DoesFileExist(v28, 0) )
      {
        if ( LogAdapter::g_Logger )
        {
          LOBYTE(v23) = 1;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v23,
            1,
            (unsigned int)"Repr: Removing Phantom Package: {}.mum",
            (__int64)v9);
        }
        SetFileAttributesW(v22, 0x80u);
        if ( !DeleteFileW(v22) )
        {
          v24 = GetLastError();
          if ( v24 > 0 )
            v24 = (unsigned __int16)v24 | 0x80070000;
          v27 = v22;
          if ( v24 < 0 )
          {
            v15 = &v27;
            v17 = (unsigned int)v24;
            v16 = "Failed deleting {}";
            v18 = 3;
            goto LABEL_28;
          }
        }
      }
LABEL_29:
      if ( v10 >= 0 )
        v10 = v1;
      ++v9;
    }
    v15 = v9;
    v16 = "Unable to delete Package key: {}";
    v17 = (unsigned int)v14;
    v18 = 2;
LABEL_28:
    LogAdapter::TraceAtLevelHr<long,wchar_t const *>(v18, v17, v16, v15);
    goto LABEL_29;
  }
  v30 = StoreObject;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting Package object");
    v27 = (const WCHAR *)&v30;
    LOBYTE(v6) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v6,
      3,
      (unsigned int)": {}",
      (__int64)&v27);
  }
  v7 = v5;
  v8 = 2642;
LABEL_39:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)v7,
    (int)v26);
  CCbsStoreObject::~CCbsStoreObject((CCbsStoreObject *)&v31);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v28);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpFileName);
  return v5;
}

```

## disassembly

```asm
0x18019046c  mov     [rsp-28h+arg_8], rbx
0x180190471  mov     [rsp-28h+arg_10], rsi
0x180190476  push    rbp
0x180190477  push    rdi
0x180190478  push    r13
0x18019047a  push    r14
0x18019047c  push    r15
0x18019047e  mov     rbp, rsp
0x180190481  sub     rsp, 80h
0x180190488  mov     rax, cs:__security_cookie
0x18019048f  xor     rax, rsp
0x180190492  mov     [rbp+var_8], rax
0x180190496  xor     esi, esi
0x180190498  lea     rax, [rbp+var_30]
0x18019049c  mov     r15, rcx
0x18019049f  mov     [rbp+lpFileName], rsi
0x1801904a3  mov     rcx, [rcx+30h]
0x1801904a7  xorps   xmm0, xmm0
0x1801904aa  xor     r9d, r9d
0x1801904ad  mov     [rbp+var_48], rsi
0x1801904b1  lea     r8d, [rsi+2]
0x1801904b5  mov     [rbp+var_30], rsi
0x1801904b9  xor     edx, edx
0x1801904bb  mov     [rbp+var_28], esi
0x1801904be  movdqu  [rbp+var_20], xmm0
0x1801904c3  mov     [rbp+var_10], rsi
0x1801904c7  mov     qword ptr [rsp+80h+var_60], rax
0x1801904cc  call    ?GetStoreObject@CCbsSession@@QEAAJPEB_WW4CbsStoreObjectType@@HPEAVCCbsStoreObject@@@Z; CCbsSession::GetStoreObject(wchar_t const *,CbsStoreObjectType,int,CCbsStoreObject *)
0x1801904d1  mov     ebx, eax
0x1801904d3  test    eax, eax
0x1801904d5  jns     short loc_18019052F
0x1801904d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801904de  mov     [rbp+var_38], eax
0x1801904e1  test    rcx, rcx
0x1801904e4  jz      short loc_180190522
0x1801904e6  lea     r9, aFailedGettingP_2; "Failed getting Package object"
0x1801904ed  xor     edx, edx
0x1801904ef  lea     r8d, [rsi+3]
0x1801904f3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801904f8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801904ff  lea     rax, [rbp+var_38]
0x180190503  mov     [rbp+var_50], rax
0x180190507  lea     r9, asc_1802EE7AC; ": {}"
0x18019050e  lea     rax, [rbp+var_50]
0x180190512  mov     dl, 1
0x180190514  lea     r8d, [rsi+3]
0x180190518  mov     qword ptr [rsp+80h+var_60], rax
0x18019051d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180190522  mov     r9d, ebx
0x180190525  mov     edx, 0A52h
0x18019052a  jmp     loc_18019077D
0x18019052f  mov     rdi, [r15+140h]
0x180190536  mov     r14d, esi
0x180190539  mov     rax, [r15+130h]
0x180190540  lea     r13, [rdi+rax*8]
0x180190544  jmp     loc_180190718
0x180190549  mov     r9, [rdi]
0x18019054c  lea     rdx, aWsWsCat; "%ws%ws.cat"
0x180190553  mov     r8, [r15+40h]
0x180190557  lea     rcx, [rbp+lpFileName]
0x18019055b  call    SczAllocFormatted
0x180190560  mov     ebx, eax
0x180190562  test    eax, eax
0x180190564  js      loc_180190775
0x18019056a  mov     r9, [rdi]
0x18019056d  lea     rdx, aWsWsMum; "%ws%ws.mum"
0x180190574  mov     r8, [r15+40h]
0x180190578  lea     rcx, [rbp+var_48]
0x18019057c  call    SczAllocFormatted
0x180190581  mov     ebx, eax
0x180190583  test    eax, eax
0x180190585  js      loc_18019076E
0x18019058b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180190592  test    rcx, rcx
0x180190595  jz      short loc_1801905B1
0x180190597  mov     r8d, 1
0x18019059d  mov     qword ptr [rsp+80h+var_60], rdi
0x1801905a2  mov     dl, r8b
0x1801905a5  lea     r9, aReprRemovingPh_0; "Repr: Removing Phantom Package key: {}"
0x1801905ac  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801905b1  mov     rdx, [rdi]; wchar_t *
0x1801905b4  lea     rcx, [rbp+var_30]; this
0x1801905b8  call    ?DeleteChild@CCbsStoreObject@@QEAAJPEB_W@Z; CCbsStoreObject::DeleteChild(wchar_t const *)
0x1801905bd  mov     esi, eax
0x1801905bf  test    eax, eax
0x1801905c1  jns     short loc_1801905D9
0x1801905c3  mov     r9, rdi
0x1801905c6  lea     r8, aUnableToDelete_0; "Unable to delete Package key: {}"
0x1801905cd  mov     edx, eax
0x1801905cf  mov     ecx, 2
0x1801905d4  jmp     loc_180190708
0x1801905d9  mov     rbx, [rbp+lpFileName]
0x1801905dd  xor     edx, edx
0x1801905df  mov     rcx, rbx
0x1801905e2  call    DoesFileExist
0x1801905e7  test    eax, eax
0x1801905e9  jz      loc_180190673
0x1801905ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801905f6  test    rcx, rcx
0x1801905f9  jz      short loc_180190615
0x1801905fb  mov     r8d, 1
0x180190601  mov     qword ptr [rsp+80h+var_60], rdi
0x180190606  mov     dl, r8b
0x180190609  lea     r9, aReprRemovingPh_1; "Repr: Removing Phantom Package: {}.cat"
0x180190610  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180190615  mov     edx, 80h; dwFileAttributes
0x18019061a  mov     rcx, rbx; lpFileName
0x18019061d  call    cs:__imp_SetFileAttributesW
0x180190624  nop     dword ptr [rax+rax+00h]
0x180190629  mov     rcx, rbx; lpFileName
0x18019062c  call    cs:__imp_DeleteFileW
0x180190633  nop     dword ptr [rax+rax+00h]
0x180190638  test    eax, eax
0x18019063a  jnz     short loc_180190673
0x18019063c  call    cs:__imp_GetLastError
0x180190643  nop     dword ptr [rax+rax+00h]
0x180190648  test    eax, eax
0x18019064a  jle     short loc_180190654
0x18019064c  movzx   eax, ax
0x18019064f  or      eax, 80070000h
0x180190654  mov     [rbp+var_50], rbx
0x180190658  test    eax, eax
0x18019065a  jns     short loc_180190673
0x18019065c  lea     r9, [rbp+var_50]
0x180190660  mov     edx, eax
0x180190662  lea     r8, aFailedDeleting_9; "Failed deleting {}"
0x180190669  mov     ecx, 3
0x18019066e  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x180190673  mov     rbx, [rbp+var_48]
0x180190677  xor     edx, edx
0x180190679  mov     rcx, rbx
0x18019067c  call    DoesFileExist
0x180190681  test    eax, eax
0x180190683  jz      loc_18019070D
0x180190689  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180190690  test    rcx, rcx
0x180190693  jz      short loc_1801906AF
0x180190695  mov     r8d, 1
0x18019069b  mov     qword ptr [rsp+80h+var_60], rdi; int
0x1801906a0  mov     dl, r8b
0x1801906a3  lea     r9, aReprRemovingPh; "Repr: Removing Phantom Package: {}.mum"
0x1801906aa  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801906af  mov     edx, 80h; dwFileAttributes
0x1801906b4  mov     rcx, rbx; lpFileName
0x1801906b7  call    cs:__imp_SetFileAttributesW
0x1801906be  nop     dword ptr [rax+rax+00h]
0x1801906c3  mov     rcx, rbx; lpFileName
0x1801906c6  call    cs:__imp_DeleteFileW
0x1801906cd  nop     dword ptr [rax+rax+00h]
0x1801906d2  test    eax, eax
0x1801906d4  jnz     short loc_18019070D
0x1801906d6  call    cs:__imp_GetLastError
0x1801906dd  nop     dword ptr [rax+rax+00h]
0x1801906e2  test    eax, eax
0x1801906e4  jle     short loc_1801906EE
0x1801906e6  movzx   eax, ax
0x1801906e9  or      eax, 80070000h
0x1801906ee  mov     [rbp+var_50], rbx
0x1801906f2  test    eax, eax
0x1801906f4  jns     short loc_18019070D
0x1801906f6  lea     r9, [rbp+var_50]
0x1801906fa  mov     edx, eax
0x1801906fc  lea     r8, aFailedDeleting_9; "Failed deleting {}"
0x180190703  mov     ecx, 3
0x180190708  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x18019070d  test    r14d, r14d
0x180190710  cmovns  r14d, esi
0x180190714  add     rdi, 8
0x180190718  cmp     rdi, r13
0x18019071b  jnz     loc_180190549
0x180190721  test    r14d, r14d
0x180190724  lea     rcx, [rbp+var_30]; this
0x180190728  cmovs   esi, r14d
0x18019072c  call    ??1CCbsStoreObject@@QEAA@XZ; CCbsStoreObject::~CCbsStoreObject(void)
0x180190731  lea     rcx, [rbp+var_48]
0x180190735  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18019073a  lea     rcx, [rbp+lpFileName]
0x18019073e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180190743  mov     eax, esi
0x180190745  mov     rcx, [rbp+var_8]
0x180190749  xor     rcx, rsp; StackCookie
0x18019074c  call    __security_check_cookie
0x180190751  lea     r11, [rsp+80h+var_s0]
0x180190759  mov     rbx, [r11+38h]
0x18019075d  mov     rsi, [r11+40h]
0x180190761  mov     rsp, r11
0x180190764  pop     r15
0x180190766  pop     r14
0x180190768  pop     r13
0x18019076a  pop     rdi
0x18019076b  pop     rbp
0x18019076c  retn
0x18019076e  mov     edx, 0A58h
0x180190773  jmp     short loc_18019077A
0x180190775  mov     edx, 0A56h; void *
0x18019077a  mov     r9d, eax; char *
0x18019077d  mov     rcx, [rbp+28h]; this
0x180190781  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x180190788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019078d  lea     rcx, [rbp+var_30]; this
0x180190791  call    ??1CCbsStoreObject@@QEAA@XZ; CCbsStoreObject::~CCbsStoreObject(void)
0x180190796  lea     rcx, [rbp+var_48]
0x18019079a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18019079f  lea     rcx, [rbp+lpFileName]
0x1801907a3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801907a8  mov     eax, ebx
0x1801907aa  jmp     short loc_180190745
```
