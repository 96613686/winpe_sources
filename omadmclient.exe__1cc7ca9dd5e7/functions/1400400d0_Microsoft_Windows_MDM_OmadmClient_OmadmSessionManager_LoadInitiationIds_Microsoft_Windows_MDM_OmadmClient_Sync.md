# Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::LoadInitiationIds(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &)

- ea: `0x1400400d0`
- end: `0x1400409cf`
- name: `?LoadInitiationIds@OmadmSessionManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@@Z`
- size: `2303`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x14001391c`
- `0x140014744`
- `0x14003fd10`
- `0x14003ff60`
- `0x1400400d0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004065c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004065c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400406fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400406fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040774`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400408f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140040774`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400408f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400405b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004064b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400405b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004064b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400405e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004066a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400405e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004066a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140040385`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140040385`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140040210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004022d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400402fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004031a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400405d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140040210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004022d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400402fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004031a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400405d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400402b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004059d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400402b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004059d`
- `DMCmnUtils!BigStrcat` at `0x140040542`
- `DMCmnUtils!BigStrcat` at `0x140040542`
- `DMCmnUtils!CopyString` at `0x14004072d`
- `DMCmnUtils!CopyString` at `0x14004072d`
- `DMCmnUtils!InvStrCmpIW` at `0x140040423`
- `DMCmnUtils!InvStrCmpIW` at `0x1400404a9`
- `DMCmnUtils!InvStrCmpIW` at `0x1400404e1`
- `DMCmnUtils!InvStrCmpIW` at `0x140040423`
- `DMCmnUtils!InvStrCmpIW` at `0x1400404a9`
- `DMCmnUtils!InvStrCmpIW` at `0x1400404e1`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400405c9`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x1400405c9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140040833`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140040866`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140040833`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x140040866`

## string_xrefs

- `0x1400407a4`: `SessionAutoDeleteKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager::LoadInitiationIds(
        Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2)
{
  Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *v3; // r13
  HLOCAL *v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // r14
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, HLOCAL **); // r15
  HLOCAL *v9; // rsi
  unsigned int v10; // ebx
  unsigned __int64 v11; // rcx
  HLOCAL v12; // r14
  __int64 v13; // rdx
  __int64 v14; // r15
  HLOCAL *v15; // rbx
  HLOCAL *v16; // rsi
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rbx
  const unsigned __int16 *v20; // rdx
  struct COmaDmLogger *v21; // rax
  const unsigned __int16 *v22; // r14
  const unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  _DWORD *v26; // rsi
  void *v27; // r15
  DWORD LastError; // ebx
  int v29; // eax
  __int64 v30; // r12
  __int64 (__fastcall *v31)(__int64, __int64, const unsigned __int16 *, _QWORD, int *, char *); // r13
  _QWORD *v32; // r15
  HKEY v33; // rsi
  DWORD v34; // ebx
  int v35; // eax
  int v36; // eax
  struct COmaDmLogger *Logger; // rax
  int *v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  HLOCAL *v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  int v46; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+68h] [rbp-98h] BYREF
  int v48; // [rsp+6Ch] [rbp-94h] BYREF
  int v49; // [rsp+70h] [rbp-90h] BYREF
  int v50; // [rsp+74h] [rbp-8Ch] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp-88h] BYREF
  FILETIME v52; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v53[3]; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+A0h] [rbp-60h]
  int *v55; // [rsp+A8h] [rbp-58h]
  Microsoft::Windows::MDM::OmadmClient::OmadmSessionManager *v56; // [rsp+B0h] [rbp-50h]
  _QWORD v57[6]; // [rsp+B8h] [rbp-48h] BYREF
  char v58; // [rsp+E8h] [rbp-18h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  int *v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  unsigned __int16 v62[264]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  v3 = this;
  v56 = this;
  v40 = 0;
  v53[0] = 0;
  v53[1] = "LoadInitiationIds";
  v53[2] = COmaDmLogger::GetLogger();
  v54 = 2;
  v55 = &v40;
  v41 = 0;
  v4 = 0;
  v44 = 0;
  v5 = 0;
  v45 = 0;
  memset_0(v62, 0, 0x208u);
  v42 = 0;
  v47 = 0;
  FileTime1 = 0;
  v52 = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v46 = 34;
    v60 = &v46;
    v61 = 4;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v6, 2);
    v5 = v45;
    v4 = v44;
  }
  v57[0] = a2;
  v57[1] = &v40;
  v57[2] = &v41;
  v57[3] = &v42;
  v57[4] = &v47;
  v57[5] = v62;
  v58 = 1;
  v7 = *((_QWORD *)v3 + 3);
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HLOCAL **))(*(_QWORD *)v7 + 8LL);
  if ( v4 )
  {
    v9 = &v4[v5];
    if ( v4 != v9 )
    {
      do
        LocalFree(*v4++);
      while ( v4 != v9 );
      v4 = v44;
    }
    LocalFree(v4);
    v44 = 0;
    v45 = 0;
  }
  v39 = &v41;
  v10 = v8(v7, *(_QWORD *)(*((_QWORD *)a2 + 5) + 16LL), *(unsigned int *)(*((_QWORD *)a2 + 5) + 24LL), &v44);
  v40 = v10;
  if ( v10 == -2147023728 || !v41 )
  {
    v40 = 0;
    wil::details::ScopeExitFn__lambda_74b1be6996b031ce5e7586893d4df09b___::_ScopeExitFn__lambda_74b1be6996b031ce5e7586893d4df09b___(v57);
    wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,unsigned __int64>(&v44);
    Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v53);
    return 0;
  }
  if ( (v10 & 0x80000000) != 0 )
  {
    LODWORD(v53[0]) = 9047;
    goto LABEL_72;
  }
  v11 = 8LL * (unsigned int)(v41 - 1);
  if ( v11 > 0xFFFFFFFF )
  {
    v10 = -2147024362;
    v40 = -2147024362;
    v13 = 227;
    goto LABEL_76;
  }
  v40 = 0;
  v12 = LocalAlloc(0x40u, (unsigned int)v11);
  if ( !v12 )
  {
    v10 = -2147024882;
    v13 = 229;
LABEL_76:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\omadmsessionmanager.cpp",
      (const char *)v10,
      (int)v39);
    goto LABEL_77;
  }
  v14 = (unsigned int)(v41 - 1);
  v15 = (HLOCAL *)*((_QWORD *)a2 + 119);
  if ( v15 )
  {
    v16 = &v15[*((_QWORD *)a2 + 120)];
    while ( v15 != v16 )
      LocalFree(*v15++);
    LocalFree(*((HLOCAL *)a2 + 119));
  }
  *((_QWORD *)a2 + 119) = v12;
  *((_QWORD *)a2 + 120) = v14;
  v17 = *(_QWORD *)(*((_QWORD *)a2 + 5) + 32LL);
  if ( v17 )
    (*(void (__fastcall **)(_QWORD, __int64, __int64, const wchar_t *, unsigned __int16 *, int))(**((_QWORD **)v3 + 3)
                                                                                               + 64LL))(
      *((_QWORD *)v3 + 3),
      -2147483646,
      v17,
      L"ParentInitiationId",
      v62,
      260);
  if ( v41 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    GetAcceptableTime(&SystemTime, 0x708u, &FileTime1);
    GetAcceptableTime(&SystemTime, 0x12Cu, &v52);
  }
  v43 = 0;
  v18 = 0;
  v46 = 0;
  if ( !v41 )
  {
LABEL_66:
    v10 = v40;
    goto LABEL_77;
  }
  while ( 1 )
  {
    v43 = 0;
    v19 = v18;
    v39 = (int *)&v43;
    v40 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, const wchar_t *))(**((_QWORD **)v3 + 3) + 72LL))(
            *((_QWORD *)v3 + 3),
            -2147483646,
            v44[v18],
            L"SessionState");
    if ( v40 < 0 )
    {
      v20 = *(const unsigned __int16 **)(*((_QWORD *)a2 + 5) + 32LL);
      if ( !v20 || !InvStrCmpIW((const unsigned __int16 *)v44[v19], v20) )
      {
        Logger = COmaDmLogger::GetLogger();
        Microsoft::Windows::TelemetryLogger::LogMeasure(Logger, 1, 3011, 0);
        goto LABEL_66;
      }
      (*(void (__fastcall **)(_QWORD, HLOCAL))(**((_QWORD **)v3 + 3) + 24LL))(*((_QWORD *)v3 + 3), v44[v19]);
      ++v42;
      v21 = COmaDmLogger::GetLogger();
      Microsoft::Windows::TelemetryLogger::LogMeasure(v21, 1, 9050, 0);
      goto LABEL_63;
    }
    if ( v43 - 1 > 4 && v43 < 8 )
      break;
    *(_QWORD *)&SystemTime.wYear = 0;
    v50 = 8;
    v40 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, const wchar_t *, struct _SYSTEMTIME *, int *))(**((_QWORD **)v3 + 3) + 88LL))(
            *((_QWORD *)v3 + 3),
            -2147483646,
            v44[v19],
            L"SessionStateTimeStamp",
            &SystemTime,
            &v50);
    if ( v40 < 0 )
      goto LABEL_60;
    if ( v43 == 5 )
    {
      if ( CompareFileTime(&v52, (const FILETIME *)&SystemTime) > 0 )
      {
        (*(void (__fastcall **)(_QWORD, HLOCAL))(**((_QWORD **)v3 + 3) + 24LL))(*((_QWORD *)v3 + 3), v44[v19]);
        ++v47;
      }
      goto LABEL_63;
    }
    if ( CompareFileTime(&FileTime1, (const FILETIME *)&SystemTime) > 0 )
    {
LABEL_60:
      (*(void (__fastcall **)(_QWORD, HLOCAL))(**((_QWORD **)v3 + 3) + 24LL))(*((_QWORD *)v3 + 3), v44[v19]);
      ++v42;
    }
LABEL_63:
    v18 = v46 + 1;
    v46 = v18;
    if ( v18 >= v41 )
      goto LABEL_66;
  }
  v22 = (const unsigned __int16 *)v44[v19];
  v23 = *(const unsigned __int16 **)(*((_QWORD *)a2 + 5) + 32LL);
  if ( v23 )
  {
    if ( InvStrCmpIW((const unsigned __int16 *)v44[v19], v23) )
    {
      v24 = -1;
      do
        ++v24;
      while ( v62[v24] );
      if ( !v24 || InvStrCmpIW((const unsigned __int16 *)v44[v19], v62) )
      {
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v3 + 5) + 440LL))(
                *((_QWORD *)v3 + 5),
                *((_QWORD *)a2 + 65))
          && v43 == 7 )
        {
          if ( *((_DWORD *)a2 + 242) > (unsigned int)(v41 - 1) )
          {
            v10 = -2147418113;
            v13 = 310;
            goto LABEL_76;
          }
          *(_QWORD *)(*((_QWORD *)a2 + 119) + 8LL * *((unsigned int *)a2 + 242)) = BigStrcat(1u, v44[v19]);
          v25 = *((unsigned int *)a2 + 242);
          *((_DWORD *)a2 + 242) = v25 + 1;
          if ( !*(_QWORD *)(*((_QWORD *)a2 + 119) + 8 * v25) )
          {
            v10 = -2147024882;
            v13 = 314;
            goto LABEL_76;
          }
        }
        goto LABEL_63;
      }
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)a2 + 5) + 32LL);
  }
  v26 = LocalAlloc(0x40u, 0x40u);
  v27 = (void *)*((_QWORD *)a2 + 118);
  if ( v27 )
  {
    LastError = GetLastError();
    OmaDmFreeInitiationInfo(v27);
    LocalFree(v27);
    SetLastError(LastError);
  }
  *((_QWORD *)a2 + 118) = v26;
  if ( !v26 )
  {
    v10 = -2147024882;
    v13 = 325;
    goto LABEL_76;
  }
  *v26 = 64;
  v29 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)v3 + 3) + 16LL))(
          *((_QWORD *)v3 + 3),
          v22,
          *((_QWORD *)a2 + 118));
  v10 = v29;
  v40 = v29;
  if ( v29 < 0 )
  {
    LODWORD(v53[0]) = 9049;
    HIDWORD(v53[0]) = v29;
    goto LABEL_77;
  }
  v30 = *((_QWORD *)v3 + 4);
  v31 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, _QWORD, int *, char *))(*(_QWORD *)v30 + 16LL);
  v32 = (_QWORD *)((char *)a2 + 936);
  v33 = (HKEY)*((_QWORD *)a2 + 117);
  if ( v33 )
  {
    v34 = GetLastError();
    RegCloseKey(v33);
    SetLastError(v34);
  }
  *v32 = 0;
  LODWORD(v39) = 131103;
  v35 = v31(v30, -2147483646, v22, 0, v39, (char *)a2 + 936);
  v10 = v35;
  if ( !v35 )
  {
    v49 = 0;
    v3 = v56;
    v40 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *))(**((_QWORD **)v56 + 3) + 72LL))(
            *((_QWORD *)v56 + 3),
            *v32,
            0,
            L"SessionAbort");
    if ( v40 < 0 )
    {
      v40 = 0;
    }
    else
    {
      *(_QWORD *)&SystemTime.wYear = (char *)a2 + 976;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 976));
      *((_DWORD *)a2 + 212) = 1;
      *((_QWORD *)a2 + 107) = -2147483646;
      v36 = CopyString(v22, 0xFFFFFFFF, (unsigned __int16 **)a2 + 108);
      v10 = v36;
      v40 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\omadmsessionmanager.cpp",
          (const char *)(unsigned int)v36,
          (int)&v49);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 976));
        goto LABEL_77;
      }
      *((_QWORD *)a2 + 109) = L"SessionAbort";
      *((_QWORD *)a2 + 110) = 0;
      *((_QWORD *)a2 + 111) = 0;
      *((_QWORD *)a2 + 112) = 0;
      *((_DWORD *)a2 + 226) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 976));
    }
    v48 = 0;
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, int *))(**((_QWORD **)v3 + 3) + 72LL))(
           *((_QWORD *)v3 + 3),
           *v32,
           0,
           L"SessionAutoDeleteKey",
           &v48) >= 0
      && v48 )
    {
      *((_BYTE *)a2 + 928) = 1;
    }
    goto LABEL_63;
  }
  if ( v35 > 0 )
    v10 = (unsigned __int16)v35 | 0x80070000;
  v40 = v10;
  LODWORD(v53[0]) = 9053;
LABEL_72:
  HIDWORD(v53[0]) = v10;
LABEL_77:
  wil::details::ScopeExitFn__lambda_74b1be6996b031ce5e7586893d4df09b___::_ScopeExitFn__lambda_74b1be6996b031ce5e7586893d4df09b___(v57);
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,unsigned __int64>(&v44);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v53);
  return v10;
}

```

## disassembly

```asm
0x1400400d0  mov     [rsp-8+arg_10], rbx
0x1400400d5  push    rbp
0x1400400d6  push    rsi
0x1400400d7  push    rdi
0x1400400d8  push    r12
0x1400400da  push    r13
0x1400400dc  push    r14
0x1400400de  push    r15
0x1400400e0  lea     rbp, [rsp-230h]
0x1400400e8  sub     rsp, 330h
0x1400400ef  mov     rax, cs:__security_cookie
0x1400400f6  xor     rax, rsp
0x1400400f9  mov     [rbp+260h+var_40], rax
0x140040100  mov     rdi, rdx
0x140040103  mov     r13, rcx
0x140040106  mov     [rbp+260h+var_2B0], rcx
0x14004010a  xor     r12d, r12d
0x14004010d  mov     [rsp+360h+var_320], r12d
0x140040112  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140040117  mov     [rbp+260h+var_2D8], r12
0x14004011b  lea     rcx, aLoadinitiation; "LoadInitiationIds"
0x140040122  mov     [rbp+260h+var_2D0], rcx
0x140040126  mov     [rbp+260h+var_2C8], rax
0x14004012a  lea     r14d, [r12+2]
0x14004012f  mov     [rbp+260h+var_2C0], r14d
0x140040133  lea     rax, [rsp+360h+var_320]
0x140040138  mov     [rbp+260h+var_2B8], rax
0x14004013c  mov     [rsp+360h+var_31C], r12d
0x140040141  mov     ebx, r12d
0x140040144  mov     [rsp+360h+var_310], rbx
0x140040149  mov     esi, r12d
0x14004014c  mov     [rsp+360h+var_308], r12
0x140040151  xor     edx, edx; Val
0x140040153  mov     r8d, 208h; Size
0x140040159  lea     rcx, [rbp+260h+var_250]; void *
0x14004015d  call    memset_0
0x140040162  mov     [rsp+360h+var_318], r12d
0x140040167  mov     [rsp+360h+var_2F8], r12d
0x14004016c  mov     qword ptr [rsp+360h+FileTime1.dwLowDateTime], r12
0x140040171  mov     qword ptr [rbp+260h+var_2E0.dwLowDateTime], r12
0x140040175  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14004017c  jz      short loc_1400401C0
0x14004017e  mov     [rsp+360h+var_300], 22h ; '"'
0x140040186  lea     rax, [rsp+360h+var_300]
0x14004018b  mov     [rbp+260h+var_260], rax
0x14004018f  mov     [rbp+260h+var_258], 4
0x140040197  lea     rax, [rbp+260h+SystemTime]
0x14004019b  mov     qword ptr [rsp+360h+var_340], rax
0x1400401a0  mov     r9d, r14d
0x1400401a3  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x1400401aa  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x1400401b1  call    McGenEventWrite_EventWriteTransfer
0x1400401b6  mov     rsi, [rsp+360h+var_308]
0x1400401bb  mov     rbx, [rsp+360h+var_310]
0x1400401c0  mov     [rbp+260h+var_2A8], rdi
0x1400401c4  lea     rax, [rsp+360h+var_320]
0x1400401c9  mov     [rbp+260h+var_2A0], rax
0x1400401cd  lea     rax, [rsp+360h+var_31C]
0x1400401d2  mov     [rbp+260h+var_298], rax
0x1400401d6  lea     rax, [rsp+360h+var_318]
0x1400401db  mov     [rbp+260h+var_290], rax
0x1400401df  lea     rax, [rsp+360h+var_2F8]
0x1400401e4  mov     [rbp+260h+var_288], rax
0x1400401e8  lea     rax, [rbp+260h+var_250]
0x1400401ec  mov     [rbp+260h+var_280], rax
0x1400401f0  mov     [rbp+260h+var_278], 1
0x1400401f4  mov     r14, [r13+18h]
0x1400401f8  mov     rax, [r14]
0x1400401fb  mov     r15, [rax+8]
0x1400401ff  test    rbx, rbx
0x140040202  jz      short loc_140040243
0x140040204  lea     rsi, [rbx+rsi*8]
0x140040208  cmp     rbx, rsi
0x14004020b  jz      short loc_14004022A
0x14004020d  mov     rcx, [rbx]; hMem
0x140040210  call    cs:__imp_LocalFree
0x140040217  nop     dword ptr [rax+rax+00h]
0x14004021c  add     rbx, 8
0x140040220  cmp     rbx, rsi
0x140040223  jnz     short loc_14004020D
0x140040225  mov     rbx, [rsp+360h+var_310]
0x14004022a  mov     rcx, rbx; hMem
0x14004022d  call    cs:__imp_LocalFree
0x140040234  nop     dword ptr [rax+rax+00h]
0x140040239  mov     [rsp+360h+var_310], r12
0x14004023e  mov     [rsp+360h+var_308], r12
0x140040243  mov     rdx, [rdi+28h]
0x140040247  lea     rax, [rsp+360h+var_31C]
0x14004024c  mov     qword ptr [rsp+360h+var_340], rax; int
0x140040251  lea     r9, [rsp+360h+var_310]
0x140040256  mov     r8d, [rdx+18h]
0x14004025a  mov     rdx, [rdx+10h]
0x14004025e  mov     rcx, r14
0x140040261  mov     rax, r15
0x140040264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040269  mov     ebx, eax
0x14004026b  mov     [rsp+360h+var_320], eax
0x14004026f  cmp     eax, 80070490h
0x140040274  jz      loc_14004097F
0x14004027a  mov     eax, [rsp+360h+var_31C]
0x14004027e  test    eax, eax
0x140040280  jz      loc_14004097F
0x140040286  test    ebx, ebx
0x140040288  jns     short loc_140040296
0x14004028a  mov     dword ptr [rbp+260h+var_2D8], 2357h
0x140040291  jmp     loc_14004091B
0x140040296  lea     ecx, [rax-1]
0x140040299  shl     rcx, 3
0x14004029d  mov     eax, 0FFFFFFFFh
0x1400402a2  cmp     rcx, rax
0x1400402a5  ja      loc_140040938
0x1400402ab  mov     [rsp+360h+var_320], r12d
0x1400402b0  mov     edx, ecx; uBytes
0x1400402b2  mov     ecx, 40h ; '@'; uFlags
0x1400402b7  call    cs:__imp_LocalAlloc
0x1400402be  nop     dword ptr [rax+rax+00h]
0x1400402c3  mov     r14, rax
0x1400402c6  test    rax, rax
0x1400402c9  jnz     short loc_1400402DA
0x1400402cb  mov     ebx, 8007000Eh
0x1400402d0  mov     edx, 0E5h
0x1400402d5  jmp     loc_140040946
0x1400402da  mov     r15d, [rsp+360h+var_31C]
0x1400402df  dec     r15d
0x1400402e2  mov     rbx, [rdi+3B8h]
0x1400402e9  test    rbx, rbx
0x1400402ec  jz      short loc_140040326
0x1400402ee  mov     rax, [rdi+3C0h]
0x1400402f5  lea     rsi, [rbx+rax*8]
0x1400402f9  jmp     short loc_14004030E
0x1400402fb  mov     rcx, [rbx]; hMem
0x1400402fe  call    cs:__imp_LocalFree
0x140040305  nop     dword ptr [rax+rax+00h]
0x14004030a  add     rbx, 8
0x14004030e  cmp     rbx, rsi
0x140040311  jnz     short loc_1400402FB
0x140040313  mov     rcx, [rdi+3B8h]; hMem
0x14004031a  call    cs:__imp_LocalFree
0x140040321  nop     dword ptr [rax+rax+00h]
0x140040326  mov     [rdi+3B8h], r14
0x14004032d  mov     [rdi+3C0h], r15
0x140040334  mov     rax, [rdi+28h]
0x140040338  mov     r8, [rax+20h]
0x14004033c  mov     rsi, 0FFFFFFFF80000002h
0x140040343  test    r8, r8
0x140040346  jz      short loc_140040373
0x140040348  mov     rcx, [r13+18h]
0x14004034c  mov     rax, [rcx]
0x14004034f  mov     dword ptr [rsp+360h+var_338], 104h
0x140040357  lea     rdx, [rbp+260h+var_250]
0x14004035b  mov     qword ptr [rsp+360h+var_340], rdx
0x140040360  lea     r9, aParentinitiati; "ParentInitiationId"
0x140040367  mov     rdx, rsi
0x14004036a  mov     rax, [rax+40h]
0x14004036e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040373  cmp     [rsp+360h+var_31C], r12d
0x140040378  jbe     short loc_1400403B6
0x14004037a  xorps   xmm0, xmm0
0x14004037d  movups  xmmword ptr [rbp+260h+SystemTime.wYear], xmm0
0x140040381  lea     rcx, [rbp+260h+SystemTime]; lpSystemTime
0x140040385  call    cs:__imp_GetSystemTime
0x14004038c  nop     dword ptr [rax+rax+00h]
0x140040391  lea     r8, [rsp+360h+FileTime1]; struct _FILETIME *
0x140040396  mov     edx, 708h; unsigned int
0x14004039b  lea     rcx, [rbp+260h+SystemTime]; struct _SYSTEMTIME *
0x14004039f  call    ?GetAcceptableTime@@YAJAEAU_SYSTEMTIME@@KAEAU_FILETIME@@@Z; GetAcceptableTime(_SYSTEMTIME &,ulong,_FILETIME &)
0x1400403a4  lea     r8, [rbp+260h+var_2E0]; struct _FILETIME *
0x1400403a8  mov     edx, 12Ch; unsigned int
0x1400403ad  lea     rcx, [rbp+260h+SystemTime]; struct _SYSTEMTIME *
0x1400403b1  call    ?GetAcceptableTime@@YAJAEAU_SYSTEMTIME@@KAEAU_FILETIME@@@Z; GetAcceptableTime(_SYSTEMTIME &,ulong,_FILETIME &)
0x1400403b6  mov     [rsp+360h+var_314], r12d
0x1400403bb  mov     eax, r12d
0x1400403be  mov     [rsp+360h+var_300], eax
0x1400403c2  cmp     [rsp+360h+var_31C], r12d
0x1400403c7  jbe     loc_1400408C3
0x1400403cd  mov     [rsp+360h+var_314], r12d
0x1400403d2  mov     rcx, [r13+18h]
0x1400403d6  mov     ebx, eax
0x1400403d8  mov     rax, [rcx]
0x1400403db  lea     rdx, [rsp+360h+var_314]
0x1400403e0  mov     qword ptr [rsp+360h+var_340], rdx
0x1400403e5  lea     r9, aSessionstate; "SessionState"
0x1400403ec  mov     r8, [rsp+360h+var_310]
0x1400403f1  mov     r8, [r8+rbx*8]
0x1400403f5  mov     rdx, rsi
0x1400403f8  mov     rax, [rax+48h]
0x1400403fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040401  mov     [rsp+360h+var_320], eax
0x140040405  test    eax, eax
0x140040407  jns     short loc_140040473
0x140040409  mov     rax, [rdi+28h]
0x14004040d  mov     rdx, [rax+20h]
0x140040411  test    rdx, rdx
0x140040414  jz      loc_1400408A9
0x14004041a  mov     rcx, [rsp+360h+var_310]
0x14004041f  mov     rcx, [rcx+rbx*8]
0x140040423  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x14004042a  nop     dword ptr [rax+rax+00h]
0x14004042f  test    eax, eax
0x140040431  jz      loc_1400408A9
0x140040437  mov     rcx, [r13+18h]
0x14004043b  mov     rax, [rcx]
0x14004043e  mov     rdx, [rsp+360h+var_310]
0x140040443  mov     rdx, [rdx+rbx*8]
0x140040447  mov     rax, [rax+18h]
0x14004044b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040450  inc     [rsp+360h+var_318]
0x140040454  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x140040459  xor     r9d, r9d
0x14004045c  lea     edx, [r9+1]
0x140040460  mov     r8d, 235Ah
0x140040466  mov     rcx, rax
0x140040469  call    ?LogMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@KPEBGZZ; Microsoft::Windows::TelemetryLogger::LogMeasure(Microsoft::Windows::TracingLevel,ulong,ushort const *,...)
0x14004046e  jmp     loc_140040893
0x140040473  mov     ecx, [rsp+360h+var_314]
0x140040477  lea     eax, [rcx-1]
0x14004047a  cmp     eax, 4
0x14004047d  jbe     loc_1400407D9
0x140040483  cmp     ecx, 8
0x140040486  jnb     loc_1400407D9
0x14004048c  mov     rax, [rsp+360h+var_310]
0x140040491  mov     r14, [rax+rbx*8]
0x140040495  mov     rax, [rdi+28h]
0x140040499  mov     rdx, [rax+20h]
0x14004049d  test    rdx, rdx
0x1400404a0  jz      loc_140040596
0x1400404a6  mov     rcx, r14
0x1400404a9  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1400404b0  nop     dword ptr [rax+rax+00h]
0x1400404b5  test    eax, eax
0x1400404b7  jz      loc_14004058E
0x1400404bd  lea     rcx, [rbp+260h+var_250]
0x1400404c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400404c5  inc     rax
0x1400404c8  cmp     [rcx+rax*2], r12w
0x1400404cd  jnz     short loc_1400404C5
0x1400404cf  test    rax, rax
0x1400404d2  jz      short loc_1400404F5
0x1400404d4  lea     rdx, [rbp+260h+var_250]
0x1400404d8  mov     rcx, [rsp+360h+var_310]
0x1400404dd  mov     rcx, [rcx+rbx*8]
0x1400404e1  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1400404e8  nop     dword ptr [rax+rax+00h]
0x1400404ed  test    eax, eax
0x1400404ef  jz      loc_14004058E
0x1400404f5  mov     rcx, [r13+28h]
0x1400404f9  mov     rax, [rcx]
0x1400404fc  mov     rdx, [rdi+208h]
0x140040503  mov     rax, [rax+1B8h]
0x14004050a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004050f  test    al, al
0x140040511  jnz     loc_140040893
0x140040517  cmp     [rsp+360h+var_314], 7
0x14004051c  jnz     loc_140040893
0x140040522  mov     eax, [rsp+360h+var_31C]
0x140040526  dec     eax
0x140040528  cmp     [rdi+3C8h], eax
0x14004052e  ja      loc_1400408CC
0x140040534  mov     rdx, [rsp+360h+var_310]
0x140040539  mov     rdx, [rdx+rbx*8]
0x14004053d  mov     ecx, 1
0x140040542  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x140040549  nop     dword ptr [rax+rax+00h]
0x14004054e  mov     edx, [rdi+3C8h]
0x140040554  mov     rcx, [rdi+3B8h]
0x14004055b  mov     [rcx+rdx*8], rax
0x14004055f  mov     ecx, [rdi+3C8h]
0x140040565  lea     eax, [rcx+1]
0x140040568  mov     [rdi+3C8h], eax
0x14004056e  mov     rax, [rdi+3B8h]
0x140040575  cmp     [rax+rcx*8], r12
0x140040579  jnz     loc_140040893
0x14004057f  mov     ebx, 8007000Eh
0x140040584  mov     edx, 13Ah
0x140040589  jmp     loc_140040946
0x14004058e  mov     rax, [rdi+28h]
0x140040592  mov     r14, [rax+20h]
0x140040596  mov     edx, 40h ; '@'; uBytes
0x14004059b  mov     ecx, edx; uFlags
0x14004059d  call    cs:__imp_LocalAlloc
0x1400405a4  nop     dword ptr [rax+rax+00h]
0x1400405a9  mov     rsi, rax
0x1400405ac  mov     r15, [rdi+3B0h]
0x1400405b3  test    r15, r15
0x1400405b6  jz      short loc_1400405F2
0x1400405b8  call    cs:__imp_GetLastError
0x1400405bf  nop     dword ptr [rax+rax+00h]
0x1400405c4  mov     ebx, eax
0x1400405c6  mov     rcx, r15
0x1400405c9  call    cs:__imp_OmaDmFreeInitiationInfo
0x1400405d0  nop     dword ptr [rax+rax+00h]
0x1400405d5  mov     rcx, r15; hMem
0x1400405d8  call    cs:__imp_LocalFree
0x1400405df  nop     dword ptr [rax+rax+00h]
0x1400405e4  mov     ecx, ebx; dwErrCode
0x1400405e6  call    cs:__imp_SetLastError
0x1400405ed  nop     dword ptr [rax+rax+00h]
0x1400405f2  mov     [rdi+3B0h], rsi
0x1400405f9  test    rsi, rsi
0x1400405fc  jz      loc_14004092C
  ... truncated ...
```
