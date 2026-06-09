# InstallLayoutOrTipPrivateWorker(ushort const *,ulong)

- ea: `0x180097ad0`
- end: `0x1800983b0`
- name: `?InstallLayoutOrTipPrivateWorker@@YAHPEBGK@Z`
- size: `2272`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180097a50`

## callees

- `0x18000fac0`
- `0x180026580`
- `0x1800539d8`
- `0x180097ad0`
- `0x18009eaea`
- `0x1800a5de4`
- `0x1800ac4f0`
- `0x1800cd058`
- `0x1800cd150`
- `0x1800cd1a0`
- `0x1800cd334`
- `0x1800cd360`
- `0x1800cd424`
- `0x1800cd6b4`
- `0x1800cda60`
- `0x1800cdbf0`
- `0x1800cdcec`
- `0x1800ce110`
- `0x1800ce4d4`
- `0x1800ce6c4`
- `0x1800ceb24`
- `0x1800cecd8`
- `0x1800cf5a8`
- `0x1800cfa04`
- `0x1800cfc04`
- `0x1800d014c`
- `0x1800d02c4`
- `0x1800d0360`
- `0x1800d0718`
- `0x1800d086c`
- `0x1800d0b9c`
- `0x1800d31bc`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180098277`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180098277`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009825b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009825b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180097d90`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180097d90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800982fd`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180098233`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180098233`

## string_xrefs

- `0x180098252`: `Kernel32.dll`
- `0x180097b74`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180097c52`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180097d15`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180097e86`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`
- `0x180097f91`: `onecore\windows\advcore\ctf\inputsetting\installlayoutortipprivate.cpp`

## pseudocode

```c
__int64 __fastcall InstallLayoutOrTipPrivateWorker(unsigned __int16 *a1, unsigned int a2)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  int v6; // ebx
  int v7; // r12d
  unsigned int v8; // r14d
  bool IsLoaded; // r13
  __int64 v11; // rsi
  char v12; // r15
  unsigned __int16 *v13; // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  unsigned __int16 *v17; // rbx
  int v18; // esi
  int v19; // eax
  int v20; // r12d
  int *v21; // rbx
  int v22; // eax
  unsigned int v23; // edx
  __int64 v24; // rcx
  FARPROC ProcAddress; // rax
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysa; // [rsp+20h] [rbp-E0h]
  bool lpcSubKeysc; // [rsp+20h] [rbp-E0h]
  bool lpcSubKeysd; // [rsp+20h] [rbp-E0h]
  int lpcSubKeysb; // [rsp+20h] [rbp-E0h]
  _DWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v32; // [rsp+68h] [rbp-98h]
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  bool v37[8]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h]
  void **v39; // [rsp+A0h] [rbp-60h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-58h]
  _QWORD v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v42[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v45[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-8h]
  _QWORD v47[2]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v48[2]; // [rsp+110h] [rbp+10h] BYREF
  int v49; // [rsp+120h] [rbp+20h]
  int v50; // [rsp+124h] [rbp+24h]
  __int64 v51; // [rsp+128h] [rbp+28h]
  _BYTE v52[128]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v53[42]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v54[2]; // [rsp+300h] [rbp+200h] BYREF
  unsigned int HKLFromLayout; // [rsp+304h] [rbp+204h]
  int v56; // [rsp+30Ch] [rbp+20Ch]
  unsigned __int16 v57[39]; // [rsp+314h] [rbp+214h] BYREF
  unsigned __int16 v58[303]; // [rsp+362h] [rbp+262h] BYREF
  unsigned __int16 v59[40]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v60[40]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v61[88]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v62[176]; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v63[176]; // [rsp+7C0h] [rbp+6C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8C8h] [rbp+7C8h]

  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v53);
  v53[0] = &InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable';
  InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
  v4 = 1;
  v5 = a2 >> 5;
  v6 = a2 & 0x40;
  LOBYTE(v5) = (a2 & 0x20) == 0;
  v49 = v6;
  LODWORD(pSid) = v5;
  v7 = a2 & 0x100;
  v8 = 0;
  IsLoaded = EnsureBcp47LangsLibraryIsLoaded();
  if ( (a2 & 0x40) != 0 && (a2 & 0x100) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4BD,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      lpcSubKeys);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
LABEL_4:
    InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
    return 0;
  }
  v39 = &CPreloadRegKey::`vftable';
  v48[0] = &CPreloadRegKey::`vftable';
  *(_QWORD *)v37 = &CPreloadRegKey::`vftable';
  v47[0] = &CPreloadRegKey::`vftable';
  *(_QWORD *)v45 = &CPreloadRegKey::`vftable';
  v44[0] = &CPreloadRegKey::`vftable';
  v43[0] = &CPreloadRegKey::`vftable';
  v42[0] = &CPreloadRegKey::`vftable';
  v41[0] = &CPreloadRegKey::`vftable';
  hKey = 0;
  v48[1] = 0;
  v38 = 0;
  v47[1] = 0;
  v46 = 0;
  v44[1] = 0;
  v43[1] = 0;
  v42[1] = 0;
  v41[1] = 0;
  if ( !InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(
          (struct CInputDllRegKey *)&v39,
          (struct CInputDllRegKey *)v48,
          (struct CInputDllRegKey *)v37,
          (struct CInputDllRegKey *)v47,
          (struct CInputDllRegKey *)v45,
          (struct CInputDllRegKey *)v44,
          (struct CInputDllRegKey *)v43,
          (struct CInputDllRegKey *)v42,
          (struct CInputDllRegKey *)v41,
          (a2 & 0x200) != 0) )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x4CE,
      (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
      (const char *)0x80004005LL,
      lpcSubKeysa);
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
    v41[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v41);
    v42[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v42);
    v43[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v43);
    v44[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v44);
    *(_QWORD *)v45 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v45);
    v47[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v47);
    *(_QWORD *)v37 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v37);
    v48[0] = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)v48);
    v39 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v39);
    goto LABEL_4;
  }
  v51 = ParseItemString(a1);
  v11 = v51;
  if ( v51 )
  {
    v50 = a2 & 0x80;
    v12 = a2 & 1;
    cValues = 0;
    RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    CInputList::CInputList((CInputList *)v31, *(_DWORD *)(v11 + 16) + cValues);
    CInputList::CInputList((CInputList *)v35, *(_DWORD *)(v11 + 16) + 4);
    CSortOrder::CSortOrder((CSortOrder *)v52);
    InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(
      (struct CInputList *)v31,
      (struct CInputDllRegKey *)&v39,
      (struct CInputDllRegKey *)v48,
      (struct CInputDllRegKey *)v44,
      (struct CInputDllRegKey *)v37);
    InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
      (struct CInputList *)v35,
      (struct CInputDllRegKey *)v45,
      0,
      0,
      lpcSubKeysc);
    InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(
      (struct CInputList *)v35,
      (struct CInputDllRegKey *)v43,
      1,
      1,
      lpcSubKeysd);
    InstallLayoutOrTipPrivateHelpers::ReadSortOrder(
      (struct CInputDllRegKey *)v42,
      (struct CInputDllRegKey *)v41,
      (struct CSortOrder *)v52);
    if ( v6 || v7 )
    {
      if ( v31[0] )
      {
        v13 = (unsigned __int16 *)v32;
        if ( v32 )
        {
          do
          {
            if ( v8 >= v31[1] )
              break;
            if ( *((_BYTE *)v13 + 16) )
            {
              *((_BYTE *)v13 + 16) = 0;
              if ( IsLoaded )
              {
                v14 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(*v13, v62, 85);
                if ( v14 >= 0 )
                {
                  v15 = *((_DWORD *)v13 + 1);
                  v16 = *v13;
                  v61[0] = 0;
                  lpcSubKeysb = v15;
                  StringCchPrintfW(v61, 0x57u, L"%04X:%08X", v16);
                  ((void (__fastcall *)(_BYTE *, __int64, unsigned __int16 *))pfnRemoveUserLanguageInputMethods)(
                    v62,
                    59,
                    v61);
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x4FF,
                    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                    (const char *)(unsigned int)v14,
                    lpcSubKeysb);
                }
              }
            }
            if ( ++v8 >= v31[0] )
              break;
            v13 = (unsigned __int16 *)((char *)v32 + 700 * v8);
          }
          while ( v13 );
          v8 = 0;
        }
      }
      if ( v35[0] )
      {
        v17 = (unsigned __int16 *)hMem;
        if ( hMem )
        {
          v18 = v49;
          do
          {
            if ( v8 >= v35[1] )
              break;
            if ( v17[10] && v17[49] && *((_BYTE *)v17 + 16) && (v7 && *((_BYTE *)v17 + 19) || v18) )
            {
              *((_BYTE *)v17 + 16) = 0;
              if ( IsLoaded )
              {
                v19 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, __int64))pfnBcp47BufferFromLcid)(*v17, v63, 85);
                if ( v19 >= 0 )
                {
                  lpcSubKeysb = (_DWORD)v17 + 20;
                  StringCchPrintfW(v54, 0x57u, L"%04X:%s%s", *v17);
                  ((void (__fastcall *)(_BYTE *, __int64, unsigned __int16 *))pfnRemoveUserLanguageInputMethods)(
                    v63,
                    59,
                    v54);
                }
                else
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x518,
                    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
                    (const char *)(unsigned int)v19,
                    lpcSubKeysb);
                }
              }
            }
            if ( ++v8 >= v35[0] )
              break;
            v17 = (unsigned __int16 *)((char *)hMem + 700 * v8);
          }
          while ( v17 );
          v11 = v51;
        }
        v8 = 0;
      }
      CSortOrder::Clear((CSortOrder *)v52);
    }
    if ( *(int *)(v11 + 16) > 0 )
    {
      v20 = v50;
      do
      {
        v21 = (int *)(*(_QWORD *)(v11 + 8) + (int)(*(_DWORD *)(v11 + 20) * v8));
        if ( v21 )
        {
          if ( *v21 == 1 )
          {
            if ( v12 || v20 )
              InstallLayoutOrTipPrivateHelpers::DisableKeyboard(
                *((_WORD *)v21 + 2),
                v21[2],
                (struct CInputList *)v31,
                IsLoaded);
            else
              InstallLayoutOrTipPrivateHelpers::EnableKeyboard(
                *((_WORD *)v21 + 2),
                v21[2],
                0,
                (struct CInputList *)v31,
                IsLoaded,
                (struct CInputDllRegKey *)v37,
                (struct CInputDllRegKey *)v47);
          }
          else if ( *v21 == 2 )
          {
            CLSIDToStringW((const struct _GUID *)(v21 + 3), v60);
            CLSIDToStringW((const struct _GUID *)(v21 + 7), v59);
            if ( v12 || v20 )
              InstallLayoutOrTipPrivateHelpers::DisableIme(
                *((_WORD *)v21 + 2),
                v60,
                v59,
                (struct CInputList *)v35,
                (struct CInputList *)v31,
                IsLoaded);
            else
              InstallLayoutOrTipPrivateHelpers::EnableIme(
                *((_WORD *)v21 + 2),
                v60,
                v59,
                (struct CInputList *)v35,
                (struct CInputList *)v31,
                IsLoaded,
                (struct CInputDllRegKey *)v43,
                (struct CInputDllRegKey *)v37,
                (struct CInputDllRegKey *)v47);
          }
          memset_0(v54, 0, 0x2BCu);
          v22 = *v21;
          v23 = v21[2];
          v54[0] = *((_WORD *)v21 + 2);
          v56 = v22;
          HKLFromLayout = (unsigned int)GetHKLFromLayout(v54[0], v23);
          CLSIDToStringW((const struct _GUID *)(v21 + 3), v57);
          CLSIDToStringW((const struct _GUID *)(v21 + 7), v58);
          if ( v12 || v20 )
            CSortOrder::RemoveAssemblyItem((CSortOrder *)v52, (struct InputContainer *)v54);
          else
            CSortOrder::AddAssemblyItem((CSortOrder *)v52, (struct InputContainer *)v54);
        }
        ++v8;
      }
      while ( (signed int)v8 < *(_DWORD *)(v11 + 16) );
    }
    InstallLayoutOrTipPrivateHelpers::WriteKeyboardRegistry(
      (struct CInputList *)v31,
      (bool)pSid,
      (struct CInputDllRegKey *)&v39,
      (struct CInputDllRegKey *)v48,
      (struct CInputDllRegKey *)v44);
    InstallLayoutOrTipPrivateHelpers::WriteImeRegistry((struct CInputList *)v35, (struct CInputDllRegKey *)v45);
    InstallLayoutOrTipPrivateHelpers::WriteSortOrder(
      (struct CInputDllRegKey *)v42,
      (struct CInputDllRegKey *)v41,
      (struct CSortOrder *)v52);
    pSid = 0;
    if ( !GetCurrentUserSid(&pSid) )
      goto LABEL_72;
    if ( !IsWellKnownSid(pSid, WinLocalSystemSid) && EnsureBcp47LangsLibraryIsLoaded() )
    {
      if ( hKernel32Dll )
      {
        ProcAddress = (FARPROC)pfnNotifyUiLanguageChange;
      }
      else
      {
        hKernel32Dll = (__int64)LoadLibraryExW(L"Kernel32.dll", 0, 0);
        v24 = hKernel32Dll;
        if ( hKernel32Dll )
        {
          ProcAddress = GetProcAddress((HMODULE)hKernel32Dll, "NotifyUILanguageChange");
          v24 = hKernel32Dll;
          pfnNotifyUiLanguageChange = (__int64)ProcAddress;
        }
        else
        {
          ProcAddress = (FARPROC)pfnNotifyUiLanguageChange;
        }
        if ( !v24 )
          goto LABEL_71;
      }
      if ( ProcAddress )
        ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(32, 0, 0, 0, 0);
    }
LABEL_71:
    LocalFree(pSid);
LABEL_72:
    wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
    (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
    CSortOrder::~CSortOrder((CSortOrder *)v52);
    LocalFree(hMem);
    LocalFree(v32);
    goto LABEL_73;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x4D4,
    (unsigned int)"onecore\\windows\\advcore\\ctf\\inputsetting\\installlayoutortipprivate.cpp",
    (const char *)0x80004005LL,
    lpcSubKeysa);
  wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 2147500037LL);
  v4 = 0;
LABEL_73:
  v41[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v41);
  v42[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v42);
  v43[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v43);
  v44[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v44);
  *(_QWORD *)v45 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v45);
  v47[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v47);
  *(_QWORD *)v37 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v37);
  v48[0] = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)v48);
  v39 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v39);
  InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker((InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker *)v53);
  return v4;
}

```

## disassembly

```asm
0x180097ad0  push    rbp
0x180097ad2  push    rbx
0x180097ad3  push    rsi
0x180097ad4  push    rdi
0x180097ad5  push    r12
0x180097ad7  push    r13
0x180097ad9  push    r14
0x180097adb  push    r15
0x180097add  lea     rbp, [rsp-788h]
0x180097ae5  sub     rsp, 888h
0x180097aec  mov     rax, cs:__security_cookie
0x180097af3  xor     rax, rsp
0x180097af6  mov     [rbp+7C0h+var_50], rax
0x180097afd  mov     rsi, rcx
0x180097b00  mov     r15d, edx
0x180097b03  lea     rcx, [rbp+7C0h+var_710]; struct wil::details::IFailureCallback *
0x180097b0a  call    ??0?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180097b0f  lea     rax, ??_7InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@6B@; const InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::`vftable'
0x180097b16  lea     rcx, [rbp+7C0h+var_710]; this
0x180097b1d  mov     [rbp+7C0h+var_710], rax
0x180097b24  call    ?StartActivity@InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@QEAAXXZ; InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::StartActivity(void)
0x180097b29  mov     eax, r15d
0x180097b2c  mov     edi, 1
0x180097b31  shr     eax, 5
0x180097b34  mov     ebx, r15d
0x180097b37  not     al
0x180097b39  and     ebx, 40h
0x180097b3c  and     al, dil
0x180097b3f  mov     [rbp+7C0h+var_7A0], ebx
0x180097b42  mov     r12d, r15d
0x180097b45  mov     dword ptr [rsp+8C0h+pSid], eax
0x180097b49  and     r12d, 100h
0x180097b50  call    ?EnsureBcp47LangsLibraryIsLoaded@@YA_NXZ; EnsureBcp47LangsLibraryIsLoaded(void)
0x180097b55  mov     ecx, r15d
0x180097b58  xor     r14d, r14d
0x180097b5b  shr     ecx, 9
0x180097b5e  mov     r13b, al
0x180097b61  and     cl, dil
0x180097b64  test    ebx, ebx
0x180097b66  jz      short loc_180097BAE
0x180097b68  test    r12d, r12d
0x180097b6b  jz      short loc_180097BAE
0x180097b6d  mov     rcx, [rbp+7C8h]; this
0x180097b74  lea     r8, aOnecoreWindows_1; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180097b7b  mov     ebx, 80004005h
0x180097b80  mov     edx, 4BDh; void *
0x180097b85  mov     r9d, ebx; char *
0x180097b88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180097b8d  mov     edx, ebx
0x180097b8f  lea     rcx, [rbp+7C0h+var_710]
0x180097b96  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180097b9b  lea     rcx, [rbp+7C0h+var_710]; this
0x180097ba2  call    ??1InstallLayoutOrTipPrivateWorker@InputTraceLoggingTelemetry@@QEAA@XZ; InputTraceLoggingTelemetry::InstallLayoutOrTipPrivateWorker::~InstallLayoutOrTipPrivateWorker(void)
0x180097ba7  xor     eax, eax
0x180097ba9  jmp     loc_18009838D
0x180097bae  lea     rax, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180097bb5  mov     byte ptr [rsp+8C0h+lpcbMaxValueLen], cl; bool
0x180097bb9  mov     [rbp+7C0h+var_820], rax
0x180097bbd  lea     r9, [rbp+7C0h+var_7C0]; struct CInputDllRegKey *
0x180097bc1  mov     [rbp+7C0h+var_7B0], rax
0x180097bc5  lea     r8, [rbp+7C0h+var_830]; struct CInputDllRegKey *
0x180097bc9  mov     qword ptr [rbp+7C0h+var_830], rax
0x180097bcd  lea     rdx, [rbp+7C0h+var_7B0]; struct CInputDllRegKey *
0x180097bd1  mov     [rbp+7C0h+var_7C0], rax
0x180097bd5  lea     rcx, [rbp+7C0h+var_820]; struct CInputDllRegKey *
0x180097bd9  mov     qword ptr [rbp+7C0h+var_7D0], rax
0x180097bdd  mov     [rbp+7C0h+var_7E0], rax
0x180097be1  mov     [rbp+7C0h+var_7F0], rax
0x180097be5  mov     [rbp+7C0h+var_800], rax
0x180097be9  mov     [rbp+7C0h+var_810], rax
0x180097bed  lea     rax, [rbp+7C0h+var_810]
0x180097bf1  mov     [rsp+8C0h+lpcbMaxValueNameLen], rax; struct CInputDllRegKey *
0x180097bf6  lea     rax, [rbp+7C0h+var_800]
0x180097bfa  mov     [rsp+8C0h+lpcValues], rax; struct CInputDllRegKey *
0x180097bff  lea     rax, [rbp+7C0h+var_7F0]
0x180097c03  mov     [rsp+8C0h+lpcbMaxClassLen], rax; struct CInputDllRegKey *
0x180097c08  lea     rax, [rbp+7C0h+var_7E0]
0x180097c0c  mov     [rsp+8C0h+lpcbMaxSubKeyLen], rax; struct CInputDllRegKey *
0x180097c11  lea     rax, [rbp+7C0h+var_7D0]
0x180097c15  mov     [rsp+8C0h+lpcSubKeys], rax; int
0x180097c1a  mov     [rbp+7C0h+hKey], r14
0x180097c1e  mov     [rbp+7C0h+var_7A8], r14
0x180097c22  mov     [rbp+7C0h+var_828], r14
0x180097c26  mov     [rbp+7C0h+var_7B8], r14
0x180097c2a  mov     [rbp+7C0h+var_7C8], r14
0x180097c2e  mov     [rbp+7C0h+var_7D8], r14
0x180097c32  mov     [rbp+7C0h+var_7E8], r14
0x180097c36  mov     [rbp+7C0h+var_7F8], r14
0x180097c3a  mov     [rbp+7C0h+var_808], r14
0x180097c3e  call    ?OpenRegistryKeys@InstallLayoutOrTipPrivateHelpers@@SA_NAEAVCInputDllRegKey@@00000000_N@Z; InstallLayoutOrTipPrivateHelpers::OpenRegistryKeys(CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,bool)
0x180097c43  test    al, al
0x180097c45  jnz     loc_180097CFA
0x180097c4b  mov     rcx, [rbp+7C8h]; this
0x180097c52  lea     r8, aOnecoreWindows_1; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180097c59  mov     ebx, 80004005h
0x180097c5e  mov     edx, 4CEh; void *
0x180097c63  mov     r9d, ebx; char *
0x180097c66  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180097c6b  mov     edx, ebx
0x180097c6d  lea     rcx, [rbp+7C0h+var_710]
0x180097c74  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180097c79  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x180097c80  lea     rcx, [rbp+7C0h+var_810]; this
0x180097c84  mov     [rbp+7C0h+var_810], rbx
0x180097c88  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097c8d  lea     rcx, [rbp+7C0h+var_800]; this
0x180097c91  mov     [rbp+7C0h+var_800], rbx
0x180097c95  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097c9a  lea     rcx, [rbp+7C0h+var_7F0]; this
0x180097c9e  mov     [rbp+7C0h+var_7F0], rbx
0x180097ca2  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097ca7  lea     rcx, [rbp+7C0h+var_7E0]; this
0x180097cab  mov     [rbp+7C0h+var_7E0], rbx
0x180097caf  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097cb4  lea     rcx, [rbp+7C0h+var_7D0]; this
0x180097cb8  mov     qword ptr [rbp+7C0h+var_7D0], rbx
0x180097cbc  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097cc1  lea     rcx, [rbp+7C0h+var_7C0]; this
0x180097cc5  mov     [rbp+7C0h+var_7C0], rbx
0x180097cc9  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097cce  lea     rcx, [rbp+7C0h+var_830]; this
0x180097cd2  mov     qword ptr [rbp+7C0h+var_830], rbx
0x180097cd6  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097cdb  lea     rcx, [rbp+7C0h+var_7B0]; this
0x180097cdf  mov     [rbp+7C0h+var_7B0], rbx
0x180097ce3  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097ce8  lea     rcx, [rbp+7C0h+var_820]; this
0x180097cec  mov     [rbp+7C0h+var_820], rbx
0x180097cf0  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180097cf5  jmp     loc_180097B9B
0x180097cfa  mov     rcx, rsi; unsigned __int16 *
0x180097cfd  call    ?ParseItemString@@YAPEAV?$CStructArray@Utag_SKEYBOARDTOINSTALLITEM@@@@PEBG@Z; ParseItemString(ushort const *)
0x180097d02  mov     [rbp+7C0h+var_798], rax
0x180097d06  mov     rsi, rax
0x180097d09  test    rax, rax
0x180097d0c  jnz     short loc_180097D44
0x180097d0e  mov     rcx, [rbp+7C8h]; this
0x180097d15  lea     r8, aOnecoreWindows_1; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180097d1c  mov     ebx, 80004005h
0x180097d21  mov     edx, 4D4h; void *
0x180097d26  mov     r9d, ebx; char *
0x180097d29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180097d2e  mov     edx, ebx
0x180097d30  lea     rcx, [rbp+7C0h+var_710]
0x180097d37  call    ?Stop@?$ActivityBase@VInputTraceLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<InputTraceLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180097d3c  mov     edi, r14d
0x180097d3f  jmp     loc_180098303
0x180097d44  mov     rcx, [rbp+7C0h+hKey]; hKey
0x180097d48  mov     eax, r15d
0x180097d4b  mov     [rsp+8C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180097d50  and     eax, 80h
0x180097d55  mov     [rsp+8C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180097d5a  xor     r9d, r9d; lpReserved
0x180097d5d  mov     [rsp+8C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180097d62  xor     r8d, r8d; lpcchClass
0x180097d65  mov     [rsp+8C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180097d6a  xor     edx, edx; lpClass
0x180097d6c  mov     [rbp+7C0h+var_79C], eax
0x180097d6f  and     r15b, dil
0x180097d72  lea     rax, [rsp+8C0h+cValues]
0x180097d77  mov     [rsp+8C0h+cValues], r14d
0x180097d7c  mov     [rsp+8C0h+lpcValues], rax; lpcValues
0x180097d81  mov     [rsp+8C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180097d86  mov     [rsp+8C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180097d8b  mov     [rsp+8C0h+lpcSubKeys], r14; lpcSubKeys
0x180097d90  call    cs:__imp_RegQueryInfoKeyW
0x180097d96  mov     edx, [rsp+8C0h+cValues]
0x180097d9a  lea     rcx, [rsp+8C0h+var_860]; this
0x180097d9f  add     edx, [rsi+10h]; unsigned int
0x180097da2  call    ??0CInputList@@QEAA@I@Z; CInputList::CInputList(uint)
0x180097da7  mov     edx, [rsi+10h]
0x180097daa  lea     rcx, [rbp+7C0h+var_840]; this
0x180097dae  add     edx, 4; unsigned int
0x180097db1  call    ??0CInputList@@QEAA@I@Z; CInputList::CInputList(uint)
0x180097db6  lea     rcx, [rbp+7C0h+var_790]; this
0x180097dba  call    ??0CSortOrder@@QEAA@XZ; CSortOrder::CSortOrder(void)
0x180097dbf  lea     rax, [rbp+7C0h+var_830]
0x180097dc3  lea     r9, [rbp+7C0h+var_7E0]; struct CInputDllRegKey *
0x180097dc7  mov     [rsp+8C0h+lpcSubKeys], rax; int
0x180097dcc  lea     r8, [rbp+7C0h+var_7B0]; struct CInputDllRegKey *
0x180097dd0  lea     rdx, [rbp+7C0h+var_820]; struct CInputDllRegKey *
0x180097dd4  lea     rcx, [rsp+8C0h+var_860]; this
0x180097dd9  call    ?ReadKeyboardRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@111@Z; InstallLayoutOrTipPrivateHelpers::ReadKeyboardRegistry(CInputList &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &,CInputDllRegKey &)
0x180097dde  xor     r9d, r9d; bool
0x180097de1  lea     rdx, [rbp+7C0h+var_7D0]; struct CInputDllRegKey *
0x180097de5  xor     r8d, r8d; bool
0x180097de8  lea     rcx, [rbp+7C0h+var_840]; this
0x180097dec  call    ?EnumCtfRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@_N22@Z; InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(CInputList &,CInputDllRegKey &,bool,bool,bool)
0x180097df1  mov     r9b, dil; bool
0x180097df4  lea     rdx, [rbp+7C0h+var_7F0]; struct CInputDllRegKey *
0x180097df8  mov     r8b, dil; bool
0x180097dfb  lea     rcx, [rbp+7C0h+var_840]; this
0x180097dff  call    ?EnumCtfRegistry@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputList@@AEAVCInputDllRegKey@@_N22@Z; InstallLayoutOrTipPrivateHelpers::EnumCtfRegistry(CInputList &,CInputDllRegKey &,bool,bool,bool)
0x180097e04  lea     r8, [rbp+7C0h+var_790]; struct CSortOrder *
0x180097e08  lea     rdx, [rbp+7C0h+var_810]; struct CInputDllRegKey *
0x180097e0c  lea     rcx, [rbp+7C0h+var_800]; struct CInputDllRegKey *
0x180097e10  call    ?ReadSortOrder@InstallLayoutOrTipPrivateHelpers@@SAXAEAVCInputDllRegKey@@0AEAVCSortOrder@@@Z; InstallLayoutOrTipPrivateHelpers::ReadSortOrder(CInputDllRegKey &,CInputDllRegKey &,CSortOrder &)
0x180097e15  test    ebx, ebx
0x180097e17  jnz     short loc_180097E22
0x180097e19  test    r12d, r12d
0x180097e1c  jz      loc_180098023
0x180097e22  cmp     [rsp+8C0h+var_860], r14d
0x180097e27  jbe     loc_180097F09
0x180097e2d  mov     rbx, [rsp+8C0h+var_858]
0x180097e32  xor     edx, edx
0x180097e34  test    rbx, rbx
0x180097e37  jz      loc_180097F09
0x180097e3d  cmp     r14d, [rsp+8C0h+var_85C]
0x180097e42  jnb     loc_180097F06
0x180097e48  cmp     [rbx+10h], dl
0x180097e4b  jz      loc_180097EE7
0x180097e51  mov     [rbx+10h], dl
0x180097e54  test    r13b, r13b
0x180097e57  jz      loc_180097EE7
0x180097e5d  movzx   ecx, word ptr [rbx]
0x180097e60  lea     rdx, [rbp+7C0h+var_1B0]
0x180097e67  mov     rax, cs:pfnBcp47BufferFromLcid
0x180097e6e  mov     r8d, 55h ; 'U'
0x180097e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e79  xor     ecx, ecx
0x180097e7b  test    eax, eax
0x180097e7d  jns     short loc_180097E9C
0x180097e7f  mov     rcx, [rbp+7C8h]; this
0x180097e86  lea     r8, aOnecoreWindows_1; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180097e8d  mov     r9d, eax; char *
0x180097e90  mov     edx, 4FFh; void *
0x180097e95  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180097e9a  jmp     short loc_180097EE5
0x180097e9c  mov     eax, [rbx+4]
0x180097e9f  lea     r8, a04x08x; "%04X:%08X"
0x180097ea6  movzx   r9d, word ptr [rbx]
0x180097eaa  mov     edx, 57h ; 'W'; unsigned __int64
0x180097eaf  mov     [rbp+7C0h+var_260], cx
0x180097eb6  lea     rcx, [rbp+7C0h+var_260]; unsigned __int16 *
0x180097ebd  mov     dword ptr [rsp+8C0h+lpcSubKeys], eax; int
0x180097ec1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180097ec6  mov     rax, cs:pfnRemoveUserLanguageInputMethods
0x180097ecd  lea     r8, [rbp+7C0h+var_260]
0x180097ed4  mov     edx, 3Bh ; ';'
0x180097ed9  lea     rcx, [rbp+7C0h+var_1B0]
0x180097ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ee5  xor     edx, edx
0x180097ee7  add     r14d, edi
0x180097eea  cmp     r14d, [rsp+8C0h+var_860]
0x180097eef  jnb     short loc_180097F06
0x180097ef1  mov     eax, r14d
0x180097ef4  imul    rbx, rax, 2BCh
0x180097efb  add     rbx, [rsp+8C0h+var_858]
0x180097f00  jnz     loc_180097E3D
0x180097f06  xor     r14d, r14d
0x180097f09  cmp     [rbp+7C0h+var_840], r14d
0x180097f0d  jbe     loc_18009801A
0x180097f13  mov     rbx, [rbp+7C0h+hMem]
0x180097f17  xor     edx, edx
0x180097f19  test    rbx, rbx
0x180097f1c  jz      loc_180098017
0x180097f22  mov     esi, [rbp+7C0h+var_7A0]
0x180097f25  cmp     r14d, [rbp+7C0h+var_83C]
0x180097f29  jnb     loc_180098013
0x180097f2f  cmp     [rbx+14h], dx
0x180097f33  jz      loc_180097FF6
0x180097f39  cmp     [rbx+62h], dx
0x180097f3d  jz      loc_180097FF6
0x180097f43  cmp     [rbx+10h], dl
0x180097f46  jz      loc_180097FF6
0x180097f4c  test    r12d, r12d
0x180097f4f  jz      short loc_180097F56
0x180097f51  cmp     [rbx+13h], dl
0x180097f54  jnz     short loc_180097F5E
0x180097f56  test    esi, esi
0x180097f58  jz      loc_180097FF6
0x180097f5e  mov     [rbx+10h], dl
0x180097f61  test    r13b, r13b
0x180097f64  jz      loc_180097FF6
0x180097f6a  movzx   ecx, word ptr [rbx]
0x180097f6d  lea     rdx, [rbp+7C0h+var_100]
0x180097f74  mov     rax, cs:pfnBcp47BufferFromLcid
0x180097f7b  mov     r8d, 55h ; 'U'
0x180097f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f86  test    eax, eax
0x180097f88  jns     short loc_180097FA7
0x180097f8a  mov     rcx, [rbp+7C8h]; this
0x180097f91  lea     r8, aOnecoreWindows_1; "onecore\\windows\\advcore\\ctf\\inputse"...
0x180097f98  mov     r9d, eax; char *
0x180097f9b  mov     edx, 518h; void *
0x180097fa0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180097fa5  jmp     short loc_180097FF4
0x180097fa7  movzx   r9d, word ptr [rbx]
0x180097fab  lea     rax, [rbx+62h]
0x180097faf  mov     [rsp+8C0h+lpcbMaxSubKeyLen], rax
0x180097fb4  lea     r8, a04xSS; "%04X:%s%s"
0x180097fbb  lea     rax, [rbx+14h]
0x180097fbf  mov     edx, 57h ; 'W'; unsigned __int64
0x180097fc4  lea     rcx, [rbp+7C0h+var_5C0]; unsigned __int16 *
0x180097fcb  mov     [rsp+8C0h+lpcSubKeys], rax
0x180097fd0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180097fd5  mov     rax, cs:pfnRemoveUserLanguageInputMethods
0x180097fdc  lea     r8, [rbp+7C0h+var_5C0]
0x180097fe3  mov     edx, 3Bh ; ';'
0x180097fe8  lea     rcx, [rbp+7C0h+var_100]
  ... truncated ...
```
