# CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(int,wchar_t const * const,wchar_t const * const,wchar_t const * const,CCbsStoreRepairHistoryCixProcessor *,CCbsStoreRepairDownloadProgress *)

- ea: `0x18018c1b0`
- end: `0x18018c67e`
- name: `?DownloadOrRequestCiXCabForProduct@CCbsStoreRepairExecutionObject@@IEAAJHQEB_W00PEAVCCbsStoreRepairHistoryCixProcessor@@PEAVCCbsStoreRepairDownloadProgress@@@Z`
- size: `1230`
- prototype: `__int64 __usercall@<rax>(CCbsStoreRepairExecutionObject *__hidden this@<rcx>, int@<edx>, const wchar_t *const@<r8>, const wchar_t *const@<r9>, const wchar_t *const, struct CCbsStoreRepairHistoryCixProcessor *, struct CCbsStoreRepairDownloadProgress *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18018add4`

## callees

- `0x180013250`
- `0x1800261e0`
- `0x180042448`
- `0x1800532d4`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800b980c`
- `0x1800eb920`
- `0x18010b5bc`
- `0x1801397a4`
- `0x180185d44`
- `0x18018c1b0`
- `0x18029b07c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18018c59e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18018c5b8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18018c59e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18018c5b8`

## string_xrefs

- `0x18018c318`: `TrustedInstaller ACR`
- `0x18018c31f`: `TrustedInstaller MCR`
- `0x18018c2d6`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c453`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c595`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c5b1`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c5c9`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c62e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018c5d0`: `CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct`
- `0x18018c28f`: `Failed to create sandbox directory for WU scan of {}`
- `0x18018c46b`: `actionlist.xml`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct(
        CCbsSession **this,
        int a2,
        wchar_t *a3,
        const wchar_t *const a4,
        wchar_t *a5,
        struct CCbsStoreRepairHistoryCixProcessor *a6,
        struct CCbsStoreRepairDownloadProgress *a7)
{
  int v9; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  unsigned __int16 *v13; // rbx
  int v14; // eax
  unsigned int v15; // esi
  int v16; // edx
  struct IFCAcquirerCallback *v17; // r10
  unsigned __int16 *v18; // r8
  struct ICbsServicingProcessor *v19; // r9
  int v20; // eax
  int v21; // esi
  CCbsSession *v22; // rax
  int v23; // eax
  int v24; // edx
  CCbsSession *v25; // r8
  int v26; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  char *v29; // rcx
  int v30; // eax
  int v31; // edx
  const char *v33; // rax
  const wchar_t *v34; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v35; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v36; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v37; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+90h] [rbp-70h]
  char v40[2060]; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned __int16 *v41; // [rsp+8A0h] [rbp+7A0h] BYREF
  int v42; // [rsp+8A8h] [rbp+7A8h] BYREF
  int v43[2]; // [rsp+8B0h] [rbp+7B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  v35 = a5;
  v37 = 0;
  v36 = 0;
  v41 = a3;
  v9 = SczAllocFormatted(&v36, L"%ws_history_cix");
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !*((_BYTE *)this + 365) )
    {
      v13 = v36;
      v14 = CCbsSession::CreateSessionSandbox(this[6], 0, v36, &v37);
      v15 = v14;
      if ( v14 < 0 )
      {
        v42 = v14;
        if ( LogAdapter::g_Logger )
        {
          v35 = v13;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to create sandbox directory for WU scan of {}",
            (__int64)&v35);
          *(_QWORD *)v43 = &v42;
          LOBYTE(v16) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v16,
            3,
            (unsigned int)": {}",
            (__int64)v43);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC73,
          (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
          (const char *)v15,
          (int)v34);
        v10 = v15;
        goto LABEL_40;
      }
      if ( a7 )
        v17 = (struct CCbsStoreRepairDownloadProgress *)((char *)a7 + *(int *)(*((_QWORD *)a7 + 1) + 4LL) + 8);
      else
        v17 = 0;
      v18 = L"TrustedInstaller MCR";
      if ( !*((_DWORD *)this + 92) )
        v18 = L"TrustedInstaller ACR";
      if ( a6 )
        v19 = (struct CCbsStoreRepairHistoryCixProcessor *)((char *)a6 + *(int *)(*((_QWORD *)a6 + 1) + 4LL) + 8);
      else
        v19 = 0;
      v20 = ProcessWUClient(5u, a2, *((void **)this[6] + 141), v19, v18, v17, v35, v41);
      v21 = v20;
      if ( v20 < 0 )
        LogAdapter::TraceAtLevelHr<long,wchar_t const *>(
          2,
          (unsigned int)v20,
          "Unable to search WU for history cix cab for {}",
          &v41);
      v22 = this[6];
      if ( !*((_DWORD *)v22 + 402) )
        *((_DWORD *)v22 + 402) = v21;
      v23 = CCbsStoreRepairExecutionObject::AddDownloadResult((CCbsStoreRepairExecutionObject *)this, v13, v21);
      v10 = v23;
      if ( v23 < 0 )
      {
        v42 = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add download result");
          v35 = (unsigned __int16 *)&v42;
          LOBYTE(v24) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v24,
            3,
            (unsigned int)": {}",
            (__int64)&v35);
        }
        v11 = v10;
        v12 = 3205;
        goto LABEL_24;
      }
LABEL_33:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v36);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v37);
      return 0;
    }
    v25 = this[51];
    v42 = 0;
    v35 = 0;
    v26 = SczAllocFormatted(&v35, L"%ws%ws", v25, L"actionlist.xml");
    v10 = v26;
    if ( v26 >= 0 )
    {
      if ( (unsigned int)DoesFileExist(v35, 0) )
      {
        v29 = (char *)a6 + *(int *)(*((_QWORD *)a6 + 1) + 4LL) + 8;
        v34 = L"InlineACR";
        v30 = (*(__int64 (__fastcall **)(char *, _QWORD, unsigned __int16 *, CCbsSession *))(*(_QWORD *)v29 + 24LL))(
                v29,
                0,
                v35,
                this[51]);
        v10 = v30;
        if ( v30 >= 0 )
        {
          Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
          goto LABEL_33;
        }
        v43[0] = v30;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed process the actionlist");
          v38[0] = v43;
          LOBYTE(v31) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v31,
            3,
            (unsigned int)": {}",
            (__int64)v38);
        }
        v28 = 3226;
      }
      else
      {
        if ( strrchr("onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp", 92) )
          v33 = strrchr("onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp", 92) + 1;
        else
          v33 = "onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp";
        v38[1] = v33;
        v38[2] = "CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct";
        v39 = 3230;
        StringCchPrintfA(
          v40,
          0x800u,
          "File: %s(%d) - %s",
          v33,
          3230,
          "CCbsStoreRepairExecutionObject::DownloadOrRequestCiXCabForProduct");
        CbsReportErrorToTelemetry(0, v40, L"Actionlist not found.");
        v28 = 3231;
        v10 = -2146498283;
      }
      v27 = v10;
    }
    else
    {
      v27 = (unsigned int)v26;
      v28 = 3212;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)v27,
      (int)v34);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v35);
    goto LABEL_40;
  }
  v11 = (unsigned int)v9;
  v12 = 3182;
LABEL_24:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)v11,
    (int)v34);
LABEL_40:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v36);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v37);
  return v10;
}

```

## disassembly

```asm
0x18018c1b0  push    rbp
0x18018c1b2  push    rbx
0x18018c1b3  push    rsi
0x18018c1b4  push    rdi
0x18018c1b5  push    r12
0x18018c1b7  push    r13
0x18018c1b9  push    r14
0x18018c1bb  push    r15
0x18018c1bd  lea     rbp, [rsp-7C8h]
0x18018c1c5  sub     rsp, 8C8h
0x18018c1cc  mov     rax, cs:__security_cookie
0x18018c1d3  xor     rax, rsp
0x18018c1d6  mov     [rbp+800h+var_48], rax
0x18018c1dd  mov     rax, [rbp+800h+arg_20]
0x18018c1e4  mov     r12d, edx
0x18018c1e7  mov     r15, [rbp+800h+arg_28]
0x18018c1ee  lea     rdx, aWsHistoryCix; "%ws_history_cix"
0x18018c1f5  mov     r14, [rbp+800h+arg_30]
0x18018c1fc  mov     rdi, rcx
0x18018c1ff  xor     esi, esi
0x18018c201  mov     [rsp+900h+var_8A0], rax
0x18018c206  lea     rcx, [rsp+900h+var_898]
0x18018c20b  mov     [rsp+900h+var_890], rsi
0x18018c210  mov     [rsp+900h+var_898], rsi
0x18018c215  mov     r13, r9
0x18018c218  mov     [rbp+800h+var_60], r8
0x18018c21f  call    SczAllocFormatted
0x18018c224  mov     ebx, eax
0x18018c226  test    eax, eax
0x18018c228  jns     short loc_18018C237
0x18018c22a  mov     r9d, eax
0x18018c22d  mov     edx, 0C6Eh
0x18018c232  jmp     loc_18018C44C
0x18018c237  cmp     [rdi+16Dh], sil
0x18018c23e  jnz     loc_18018C464
0x18018c244  mov     rbx, [rsp+900h+var_898]
0x18018c249  lea     r9, [rsp+900h+var_890]; wchar_t **
0x18018c24e  mov     rcx, [rdi+30h]; this
0x18018c252  mov     r8, rbx; wchar_t *
0x18018c255  xor     edx, edx; void *
0x18018c257  call    ?CreateSessionSandbox@CCbsSession@@QEAAJPEAXPEB_WPEAPEA_W@Z; CCbsSession::CreateSessionSandbox(void *,wchar_t const *,wchar_t * *)
0x18018c25c  mov     esi, eax
0x18018c25e  test    eax, eax
0x18018c260  jns     loc_18018C2F1
0x18018c266  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c26d  mov     [rbp+800h+var_58], eax
0x18018c273  test    rcx, rcx
0x18018c276  jz      short loc_18018C2CF
0x18018c278  lea     rax, [rsp+900h+var_8A0]
0x18018c27d  mov     [rsp+900h+var_8A0], rbx
0x18018c282  mov     edi, 3
0x18018c287  mov     qword ptr [rsp+900h+var_8E0], rax
0x18018c28c  mov     r8d, edi
0x18018c28f  lea     r9, aFailedToCreate_36; "Failed to create sandbox directory for "...
0x18018c296  xor     edx, edx
0x18018c298  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18018c29d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c2a4  lea     rax, [rbp+800h+var_58]
0x18018c2ab  mov     qword ptr [rbp+800h+var_50], rax
0x18018c2b2  lea     r9, asc_1802EE7AC; ": {}"
0x18018c2b9  lea     rax, [rbp+800h+var_50]
0x18018c2c0  mov     r8d, edi
0x18018c2c3  mov     dl, 1
0x18018c2c5  mov     qword ptr [rsp+900h+var_8E0], rax; int
0x18018c2ca  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018c2cf  mov     rcx, [rbp+808h]; this
0x18018c2d6  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c2dd  mov     r9d, esi; char *
0x18018c2e0  mov     edx, 0C73h; void *
0x18018c2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c2ea  mov     ebx, esi
0x18018c2ec  jmp     loc_18018C644
0x18018c2f1  mov     rsi, [rbp+800h+var_60]
0x18018c2f8  test    r14, r14
0x18018c2fb  jnz     short loc_18018C302
0x18018c2fd  xor     r10d, r10d
0x18018c300  jmp     short loc_18018C311
0x18018c302  mov     rax, [r14+8]
0x18018c306  movsxd  r10, dword ptr [rax+4]
0x18018c30a  add     r10, 8
0x18018c30e  add     r10, r14
0x18018c311  cmp     dword ptr [rdi+170h], 0
0x18018c318  lea     rax, aTrustedinstall_2; "TrustedInstaller ACR"
0x18018c31f  lea     r8, aTrustedinstall_0; "TrustedInstaller MCR"
0x18018c326  cmovz   r8, rax
0x18018c32a  test    r15, r15
0x18018c32d  jnz     short loc_18018C334
0x18018c32f  xor     r9d, r9d
0x18018c332  jmp     short loc_18018C343
0x18018c334  mov     rax, [r15+8]
0x18018c338  movsxd  r9, dword ptr [rax+4]
0x18018c33c  add     r9, 8
0x18018c340  add     r9, r15
0x18018c343  mov     rax, [rdi+30h]
0x18018c347  mov     rdx, cs:?pLogger@@3V?$AutoComPtr@VCFacilitatorLogger@@@Windows@@A; Windows::AutoComPtr<CFacilitatorLogger> pLogger
0x18018c34e  mov     r11, [rax+468h]
0x18018c355  test    rdx, rdx
0x18018c358  jz      short loc_18018C369
0x18018c35a  mov     rax, [rdx+8]
0x18018c35e  add     rdx, 8
0x18018c362  movsxd  rcx, dword ptr [rax+4]
0x18018c366  add     rdx, rcx
0x18018c369  mov     rax, [rsp+900h+var_8A0]
0x18018c36e  mov     ecx, 5; unsigned int
0x18018c373  mov     [rsp+900h+var_8B0], rsi; unsigned __int16 *
0x18018c378  mov     [rsp+900h+var_8B8], rax; unsigned __int16 *
0x18018c37d  mov     [rsp+900h+var_8C0], r10; struct IFCAcquirerCallback *
0x18018c382  mov     [rsp+900h+var_8C8], r8; unsigned __int16 *
0x18018c387  mov     r8, r13
0x18018c38a  mov     [rsp+900h+var_8D0], r9; struct ICbsServicingProcessor *
0x18018c38f  mov     r9, [rsp+900h+var_890]
0x18018c394  mov     [rsp+900h+var_8D8], r11; void *
0x18018c399  mov     [rsp+900h+var_8E0], r12d; int
0x18018c39e  call    ProcessWUClient
0x18018c3a3  mov     esi, eax
0x18018c3a5  test    eax, eax
0x18018c3a7  jns     short loc_18018C3C3
0x18018c3a9  lea     r9, [rbp+800h+var_60]
0x18018c3b0  mov     edx, eax
0x18018c3b2  lea     r8, aUnableToSearch; "Unable to search WU for history cix cab"...
0x18018c3b9  mov     ecx, 2
0x18018c3be  call    ??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z; LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)
0x18018c3c3  mov     rax, [rdi+30h]
0x18018c3c7  cmp     dword ptr [rax+648h], 0
0x18018c3ce  jnz     short loc_18018C3D6
0x18018c3d0  mov     [rax+648h], esi
0x18018c3d6  mov     r8d, esi; int
0x18018c3d9  mov     rdx, rbx; wchar_t *
0x18018c3dc  mov     rcx, rdi; this
0x18018c3df  call    ?AddDownloadResult@CCbsStoreRepairExecutionObject@@IEAAJPEB_WJ@Z; CCbsStoreRepairExecutionObject::AddDownloadResult(wchar_t const *,long)
0x18018c3e4  mov     ebx, eax
0x18018c3e6  test    eax, eax
0x18018c3e8  jns     loc_18018C575
0x18018c3ee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c3f5  mov     [rbp+800h+var_58], eax
0x18018c3fb  test    rcx, rcx
0x18018c3fe  jz      short loc_18018C444
0x18018c400  mov     edi, 3
0x18018c405  lea     r9, aFailedToAddDow; "Failed to add download result"
0x18018c40c  mov     r8d, edi
0x18018c40f  xor     edx, edx
0x18018c411  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018c416  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c41d  lea     rax, [rbp+800h+var_58]
0x18018c424  mov     [rsp+900h+var_8A0], rax
0x18018c429  lea     r9, asc_1802EE7AC; ": {}"
0x18018c430  lea     rax, [rsp+900h+var_8A0]
0x18018c435  mov     r8d, edi
0x18018c438  mov     dl, 1
0x18018c43a  mov     qword ptr [rsp+900h+var_8E0], rax; int
0x18018c43f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018c444  mov     r9d, ebx; char *
0x18018c447  mov     edx, 0C85h; void *
0x18018c44c  mov     rcx, [rbp+808h]; this
0x18018c453  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c45a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c45f  jmp     loc_18018C644
0x18018c464  mov     r8, [rdi+198h]
0x18018c46b  lea     r9, aActionlistXml_0; "actionlist.xml"
0x18018c472  lea     rdx, aWsWs_1; "%ws%ws"
0x18018c479  mov     [rbp+800h+var_58], esi
0x18018c47f  lea     rcx, [rsp+900h+var_8A0]
0x18018c484  mov     [rsp+900h+var_8A0], rsi
0x18018c489  call    SczAllocFormatted
0x18018c48e  mov     ebx, eax
0x18018c490  test    eax, eax
0x18018c492  jns     short loc_18018C4A1
0x18018c494  mov     r9d, eax
0x18018c497  mov     edx, 0C8Ch
0x18018c49c  jmp     loc_18018C627
0x18018c4a1  mov     rcx, [rsp+900h+var_8A0]
0x18018c4a6  xor     edx, edx
0x18018c4a8  call    DoesFileExist
0x18018c4ad  test    eax, eax
0x18018c4af  jz      loc_18018C590
0x18018c4b5  mov     rax, [r15+8]
0x18018c4b9  lea     rdx, [rbp+800h+var_58]
0x18018c4c0  mov     r9, [rdi+198h]
0x18018c4c7  mov     r8, [rsp+900h+var_8A0]
0x18018c4cc  mov     [rsp+900h+var_8C0], rsi
0x18018c4d1  movsxd  rcx, dword ptr [rax+4]
0x18018c4d5  mov     [rsp+900h+var_8C8], rdx
0x18018c4da  add     rcx, 8
0x18018c4de  lea     rdx, aInlineacr; "InlineACR"
0x18018c4e5  mov     [rsp+900h+var_8D0], rsi
0x18018c4ea  add     rcx, r15
0x18018c4ed  mov     [rsp+900h+var_8D8], rsi
0x18018c4f2  mov     qword ptr [rsp+900h+var_8E0], rdx
0x18018c4f7  xor     edx, edx
0x18018c4f9  mov     rax, [rcx]
0x18018c4fc  mov     rax, [rax+18h]
0x18018c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018c505  mov     ebx, eax
0x18018c507  test    eax, eax
0x18018c509  jns     short loc_18018C56B
0x18018c50b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c512  mov     [rbp+800h+var_50], eax
0x18018c518  test    rcx, rcx
0x18018c51b  jz      short loc_18018C561
0x18018c51d  mov     edi, 3
0x18018c522  lea     r9, aFailedProcessT; "Failed process the actionlist"
0x18018c529  mov     r8d, edi
0x18018c52c  xor     edx, edx
0x18018c52e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018c533  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018c53a  lea     rax, [rbp+800h+var_50]
0x18018c541  mov     [rsp+900h+var_888], rax
0x18018c546  lea     r9, asc_1802EE7AC; ": {}"
0x18018c54d  lea     rax, [rsp+900h+var_888]
0x18018c552  mov     r8d, edi
0x18018c555  mov     dl, 1
0x18018c557  mov     qword ptr [rsp+900h+var_8E0], rax
0x18018c55c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018c561  mov     edx, 0C9Ah
0x18018c566  jmp     loc_18018C624
0x18018c56b  lea     rcx, [rsp+900h+var_8A0]
0x18018c570  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c575  lea     rcx, [rsp+900h+var_898]
0x18018c57a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c57f  lea     rcx, [rsp+900h+var_890]
0x18018c584  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c589  xor     eax, eax
0x18018c58b  jmp     loc_18018C65A
0x18018c590  mov     ebx, 5Ch ; '\'
0x18018c595  lea     rcx, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c59c  mov     edx, ebx; Ch
0x18018c59e  call    cs:__imp_strrchr
0x18018c5a5  nop     dword ptr [rax+rax+00h]
0x18018c5aa  test    rax, rax
0x18018c5ad  jz      short loc_18018C5C9
0x18018c5af  mov     edx, ebx; Ch
0x18018c5b1  lea     rcx, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c5b8  call    cs:__imp_strrchr
0x18018c5bf  nop     dword ptr [rax+rax+00h]
0x18018c5c4  inc     rax
0x18018c5c7  jmp     short loc_18018C5D0
0x18018c5c9  lea     rax, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c5d0  lea     rdx, aCcbsstorerepai; "CCbsStoreRepairExecutionObject::Downloa"...
0x18018c5d7  mov     [rbp+800h+var_880], rax
0x18018c5db  mov     ecx, 0C9Eh
0x18018c5e0  mov     [rsp+900h+var_8D8], rdx
0x18018c5e5  mov     [rsp+900h+var_8E0], ecx; int
0x18018c5e9  lea     r8, aFileSDS; "File: %s(%d) - %s"
0x18018c5f0  mov     [rbp+800h+var_878], rdx
0x18018c5f4  mov     r9, rax
0x18018c5f7  mov     [rbp+800h+var_870], ecx
0x18018c5fa  mov     edx, 800h; unsigned __int64
0x18018c5ff  lea     rcx, [rbp+800h+var_86C]; char *
0x18018c603  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18018c608  lea     r8, aActionlistNotF; "Actionlist not found."
0x18018c60f  xor     ecx, ecx; int
0x18018c611  lea     rdx, [rbp+800h+var_86C]; char *
0x18018c615  call    ?CbsReportErrorToTelemetry@@YAJJPEBDPEB_WZZ; CbsReportErrorToTelemetry(long,char const *,wchar_t const *,...)
0x18018c61a  mov     edx, 0C9Fh; void *
0x18018c61f  mov     ebx, 800F0915h
0x18018c624  mov     r9d, ebx; char *
0x18018c627  mov     rcx, [rbp+808h]; this
0x18018c62e  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018c635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c63a  lea     rcx, [rsp+900h+var_8A0]
0x18018c63f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c644  lea     rcx, [rsp+900h+var_898]
0x18018c649  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c64e  lea     rcx, [rsp+900h+var_890]
0x18018c653  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018c658  mov     eax, ebx
0x18018c65a  mov     rcx, [rbp+800h+var_48]
0x18018c661  xor     rcx, rsp; StackCookie
0x18018c664  call    __security_check_cookie
0x18018c669  add     rsp, 8C8h
0x18018c670  pop     r15
0x18018c672  pop     r14
0x18018c674  pop     r13
0x18018c676  pop     r12
0x18018c678  pop     rdi
0x18018c679  pop     rsi
0x18018c67a  pop     rbx
0x18018c67b  pop     rbp
0x18018c67c  retn
```
