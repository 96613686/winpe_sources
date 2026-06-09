# CIEUserBrokerObject::QueueExtTelWorker(ushort const *,ulong,ushort const *)

- ea: `0x18052fb60`
- end: `0x180530235`
- name: `?QueueExtTelWorker@CIEUserBrokerObject@@AEAAJPEBGK0@Z`
- size: `1749`
- prototype: `int(CIEUserBrokerObject *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18052e834`
- `0x1805302e0`
- `0x180530380`

## callees

- `0x180005030`
- `0x180009610`
- `0x1800123f0`
- `0x180056d9c`
- `0x1800631bc`
- `0x18009b248`
- `0x1800a130c`
- `0x18051e1ec`
- `0x18052f0f0`
- `0x18052fb60`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18052ff28`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18052ff28`
- `USER32!GetForegroundWindow` at `0x18052fc05`
- `USER32!GetForegroundWindow` at `0x18052fc05`
- `USER32!GetWindowThreadProcessId` at `0x18052fd76`
- `USER32!GetWindowThreadProcessId` at `0x18052fd76`
- `USER32!GetAncestor` at `0x18052fc18`
- `USER32!GetAncestor` at `0x18052fc18`
- `OLEAUT32!__imp_SysFreeString` at `0x180530185`
- `OLEAUT32!__imp_SysFreeString` at `0x180530198`
- `OLEAUT32!__imp_SysFreeString` at `0x1805301ac`
- `OLEAUT32!__imp_SysFreeString` at `0x180530185`
- `OLEAUT32!__imp_SysFreeString` at `0x180530198`
- `OLEAUT32!__imp_SysFreeString` at `0x1805301ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18052fbf1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18052fbf1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1805300f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1805300f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18052fe6c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180530018`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180530163`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1805301cb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1805301da`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18052fe6c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180530018`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180530163`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1805301cb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1805301da`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18052fd0b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x18052fd0b`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x18052fdaa`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x18052fdaa`
- `msIso!__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z` at `0x18052fd90`
- `msIso!__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z` at `0x18052fd90`

## pseudocode

```c
__int64 __fastcall CIEUserBrokerObject::QueueExtTelWorker(
        CIEUserBrokerObject *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v5; // r14
  char v6; // r12
  HWND ForegroundWindow; // rax
  HWND Ancestor; // rdi
  signed int v9; // edx
  signed int i; // ebx
  HWND v11; // r9
  __int64 j; // rbx
  CIEUserBrokerObject *v13; // rcx
  int ModulePath; // edi
  WCHAR *FileNameW; // rsi
  HWND v16; // r15
  HWND v17; // rsi
  unsigned __int16 *v18; // rbx
  unsigned __int64 v19; // r11
  HWND v20; // r15
  char *v21; // rcx
  __int64 v22; // rdi
  unsigned __int64 v23; // rdi
  unsigned __int16 *v24; // rax
  OLECHAR *v25; // rcx
  OLECHAR *v26; // rcx
  unsigned int v27; // edi
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  unsigned int *v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+30h] [rbp-D0h]
  HWND hWnd; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+54h] [rbp-ACh] BYREF
  DWORD dwProcessId; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  struct IUri *v41; // [rsp+78h] [rbp-88h] BYREF
  void *ppvOut; // [rsp+80h] [rbp-80h] BYREF
  IUnknown *punk; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v44; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v45[2]; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A8h] [rbp-58h]
  __int128 v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+C0h] [rbp-40h]
  WCHAR pszPath[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v50[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v51[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  unsigned __int16 v52[1040]; // [rsp+700h] [rbp+600h] BYREF

  v5 = (unsigned __int64)g_pExtTelWrapper & -(__int64)g_extTelWrapperIsInitialized;
  if ( !v5 )
    return (unsigned int)-2147019873;
  v46 = 11;
  v45[1] = 0;
  v45[0] = &CUString::`vftable';
  v48 = 0;
  v44 = 0;
  v6 = 1;
  v47 = 0;
  if ( CoCreateInstance(&CLSID_BrowserApplicationState, 0, 1u, &GUID_e66a412d_14b3_425c_82ac_5b7716cca5a7, &v44) >= 0 )
  {
    ForegroundWindow = GetForegroundWindow();
    pv = 0;
    Ancestor = GetAncestor(ForegroundWindow, 3u);
    v33 = 0;
    if ( (*(int (__fastcall **)(LPVOID, LPVOID *, unsigned int *))(*(_QWORD *)v44 + 128LL))(v44, &pv, &v33) >= 0 )
    {
      v9 = v33;
      for ( i = 0; i < v9; ++i )
      {
        v11 = (HWND)*((_QWORD *)pv + i);
        if ( v11 == Ancestor || i == v9 - 1 )
        {
          v40 = 0;
          if ( (*(int (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)v44 + 24LL))(v44, v11, &v40) >= 0 )
          {
            v36 = 0;
            if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 64LL))(v40, &v36) >= 0 )
            {
              punk = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, IUnknown **))(*(_QWORD *)v40 + 216LL))(v40, v36, &punk) >= 0 )
              {
                ppvOut = 0;
                if ( IUnknown_QueryService(
                       punk,
                       (const GUID *const)&SID_STabWindowManager,
                       &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
                       &ppvOut) >= 0 )
                {
                  v39 = 0;
                  if ( (*(int (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 56LL))(ppvOut, &v39) >= 0 )
                  {
                    hWnd = 0;
                    if ( (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v39 + 264LL))(v39, &hWnd) >= 0 )
                    {
                      dwProcessId = 0;
                      GetWindowThreadProcessId(hWnd, &dwProcessId);
                      v35 = 0;
                      if ( (int)IsoGetProcessIdIsoIntegrity(dwProcessId, (enum _IsoIntegrity *)&v35) >= 0 )
                      {
                        v34 = 0;
                        if ( (int)IEGetCOMCallerIntegrity((enum _IsoIntegrity *)&v34) >= 0 && v35 == v34 )
                        {
                          v41 = 0;
                          if ( (*(int (__fastcall **)(__int64, struct IUri **))(*(_QWORD *)v39 + 168LL))(v39, &v41) >= 0
                            && (int)CUString::Set((CUString *)v45, v41, Uri_PROPERTY_ABSOLUTE_URI) >= 0 )
                          {
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v41);
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v39);
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&punk);
                            ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v40);
                            break;
                          }
                          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v41);
                        }
                      }
                    }
                  }
                  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v39);
                }
                ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppvOut);
              }
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&punk);
            }
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v40);
          v9 = v33;
        }
      }
      CoTaskMemFree(pv);
    }
  }
  memset_0(v52, 0, sizeof(v52));
  for ( j = 0; j != 3; ++j )
  {
    memset_0(pszPath, 0, 0x208u);
    ModulePath = Ext_GetModulePath((const struct _GUID *)&qword_18064A330[2 * j], pszPath, 0x104u, 0x13u, 0);
    if ( ModulePath >= 0 )
    {
      v34 = 0;
      v35 = 0;
      v33 = 0;
      v36 = 0;
      dwProcessId = 0;
      ModulePath = Ext_GetFileVersion(pszPath, &v34, &v35, &v33, &v36, &dwProcessId);
      if ( ModulePath >= 0 )
      {
        FileNameW = PathFindFileNameW(pszPath);
        if ( FileNameW != pszPath )
        {
          memset_0(v50, 0, 0x208u);
          LODWORD(v31) = (unsigned __int16)v35;
          LODWORD(v30) = HIWORD(v35);
          LODWORD(ppv) = (unsigned __int16)v34;
          ModulePath = StringCchPrintfW(v50, 0x104u, L"%d.%d.%d.%d", HIWORD(v34), ppv, v30, v31);
          if ( ModulePath >= 0 )
          {
            hWnd = 0;
            ModulePath = CIEUserBrokerObject::EncodeValue(v13, v50, (unsigned __int16 **)&hWnd, 0);
            if ( ModulePath >= 0 )
            {
              memset_0(v51, 0, 0x208u);
              v16 = hWnd;
              ModulePath = StringCchPrintfW(v51, 0x104u, L"%s:%s;", FileNameW, hWnd);
              if ( ModulePath >= 0 )
                ModulePath = StringCchCatW(v52, 0x410u, v51);
              CoTaskMemFree(v16);
            }
          }
        }
      }
    }
  }
  hWnd = 0;
  v17 = 0;
  pv = 0;
  if ( a4 )
  {
    ModulePath = CIEUserBrokerObject::EncodeValue(v13, a4, (unsigned __int16 **)&hWnd, (unsigned __int64 *)&pv);
    v17 = hWnd;
  }
  v18 = 0;
  if ( ModulePath >= 0 )
  {
    hWnd = 0;
    if ( (int)StringCchLengthW(v52, 0x410u, (unsigned __int64 *)&hWnd) >= 0 )
    {
      v20 = hWnd;
      if ( hWnd || v19 )
      {
        v21 = (char *)hWnd + v19;
        if ( (unsigned __int64)hWnd + v19 >= v19 )
        {
          v22 = 1;
          if ( v17 )
            v22 = 11;
          v23 = (unsigned __int64)&v21[v22];
          if ( v23 >= (unsigned __int64)v21 )
          {
            hWnd = 0;
            if ( ULongLongMult(2u, v23, (ULONGLONG *)&hWnd) >= 0 )
            {
              v24 = (unsigned __int16 *)CoTaskMemAlloc((SIZE_T)hWnd);
              v18 = v24;
              if ( v24 )
              {
                if ( v17 )
                {
                  if ( (int)StringCchPrintfW(v24, v23, L"%s:%s;", L"CmdLine", v17) < 0 )
                    goto LABEL_56;
                  v6 = 0;
                }
                if ( v20 )
                {
                  if ( (int)StringCchCatW(v18, v23, v52) >= 0 )
                    goto LABEL_57;
                  goto LABEL_56;
                }
                if ( v6 )
                {
LABEL_56:
                  CoTaskMemFree(v18);
                  v18 = 0;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_57:
  SysFreeString(*(BSTR *)v5);
  v25 = *(OLECHAR **)(v5 + 8);
  *(_QWORD *)v5 = 0;
  SysFreeString(v25);
  v26 = *(OLECHAR **)(v5 + 16);
  *(_QWORD *)(v5 + 8) = 0;
  SysFreeString(v26);
  *(_QWORD *)(v5 + 16) = 0;
  _InterlockedExchange((volatile __int32 *)(v5 + 112), 0);
  v27 = -2147024891;
  CoTaskMemFree(v17);
  CoTaskMemFree(v18);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v44);
  v45[0] = &CUString::`vftable';
  CUString::Set((CUString *)v45, 0, Uri_PROPERTY_RAW_URI);
  return v27;
}

```

## disassembly

```asm
0x18052fb60  push    rbp
0x18052fb62  push    rbx
0x18052fb63  push    rsi
0x18052fb64  push    rdi
0x18052fb65  push    r12
0x18052fb67  push    r13
0x18052fb69  push    r14
0x18052fb6b  push    r15
0x18052fb6d  lea     rbp, [rsp-0E38h]
0x18052fb75  sub     rsp, 0F38h
0x18052fb7c  mov     rax, cs:__security_cookie
0x18052fb83  xor     rax, rsp
0x18052fb86  mov     [rbp+0E70h+var_50], rax
0x18052fb8d  mov     al, cs:?g_extTelWrapperIsInitialized@@3_NA; bool g_extTelWrapperIsInitialized
0x18052fb93  mov     r13, r9
0x18052fb96  neg     al
0x18052fb98  sbb     r14, r14
0x18052fb9b  and     r14, cs:?g_pExtTelWrapper@@3PEAVCExtTelWrapper@@EA; CExtTelWrapper * g_pExtTelWrapper
0x18052fba2  jz      loc_18053020A
0x18052fba8  xor     r15d, r15d
0x18052fbab  mov     [rbp+0E70h+var_EC8], 0Bh
0x18052fbb2  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x18052fbb9  mov     [rbp+0E70h+var_ED0], r15
0x18052fbbd  mov     [rbp+0E70h+var_ED8], rax
0x18052fbc1  lea     r9, _GUID_e66a412d_14b3_425c_82ac_5b7716cca5a7; riid
0x18052fbc8  xorps   xmm0, xmm0
0x18052fbcb  mov     [rbp+0E70h+var_EB0], r15d
0x18052fbcf  lea     rax, [rbp+0E70h+var_EE0]
0x18052fbd3  mov     [rbp+0E70h+var_EE0], r15
0x18052fbd7  lea     r12d, [r15+1]
0x18052fbdb  mov     [rsp+0F70h+ppv], rax; ppv
0x18052fbe0  mov     r8d, r12d; dwClsContext
0x18052fbe3  lea     rcx, CLSID_BrowserApplicationState; rclsid
0x18052fbea  xor     edx, edx; pUnkOuter
0x18052fbec  movdqu  [rbp+0E70h+var_EC0], xmm0
0x18052fbf1  call    cs:__imp_CoCreateInstance
0x18052fbf8  nop     dword ptr [rax+rax+00h]
0x18052fbfd  test    eax, eax
0x18052fbff  js      loc_18052FE78
0x18052fc05  call    cs:__imp_GetForegroundWindow
0x18052fc0c  nop     dword ptr [rax+rax+00h]
0x18052fc11  mov     rcx, rax; hwnd
0x18052fc14  lea     edx, [r15+3]; gaFlags
0x18052fc18  call    cs:__imp_GetAncestor
0x18052fc1f  nop     dword ptr [rax+rax+00h]
0x18052fc24  mov     rcx, [rbp+0E70h+var_EE0]
0x18052fc28  lea     r8, [rsp+0F70h+var_F28]
0x18052fc2d  mov     [rsp+0F70h+pv], r15
0x18052fc32  mov     rdi, rax
0x18052fc35  mov     [rsp+0F70h+var_F28], r15d
0x18052fc3a  mov     rdx, [rcx]
0x18052fc3d  mov     rax, [rdx+80h]
0x18052fc44  lea     rdx, [rsp+0F70h+pv]
0x18052fc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fc4e  test    eax, eax
0x18052fc50  js      loc_18052FE78
0x18052fc56  mov     edx, [rsp+0F70h+var_F28]
0x18052fc5a  mov     ebx, r15d
0x18052fc5d  cmp     ebx, edx
0x18052fc5f  jge     loc_18052FE67
0x18052fc65  mov     rax, [rsp+0F70h+pv]
0x18052fc6a  movsxd  rcx, ebx
0x18052fc6d  mov     r9, [rax+rcx*8]
0x18052fc71  cmp     r9, rdi
0x18052fc74  jz      short loc_18052FC81
0x18052fc76  lea     eax, [rdx-1]
0x18052fc79  cmp     ebx, eax
0x18052fc7b  jnz     loc_18052FE2F
0x18052fc81  mov     rcx, [rbp+0E70h+var_EE0]
0x18052fc85  lea     r8, [rsp+0F70h+var_F00]
0x18052fc8a  mov     [rsp+0F70h+var_F00], r15
0x18052fc8f  mov     rdx, r9
0x18052fc92  mov     rax, [rcx]
0x18052fc95  mov     rax, [rax+18h]
0x18052fc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fc9e  test    eax, eax
0x18052fca0  js      loc_18052FE21
0x18052fca6  mov     rcx, [rsp+0F70h+var_F00]
0x18052fcab  lea     rdx, [rsp+0F70h+var_F1C]
0x18052fcb0  mov     [rsp+0F70h+var_F1C], r15d
0x18052fcb5  mov     rax, [rcx]
0x18052fcb8  mov     rax, [rax+40h]
0x18052fcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fcc1  test    eax, eax
0x18052fcc3  js      loc_18052FE21
0x18052fcc9  mov     rcx, [rsp+0F70h+var_F00]
0x18052fcce  lea     r8, [rbp+0E70h+punk]
0x18052fcd2  mov     edx, [rsp+0F70h+var_F1C]
0x18052fcd6  mov     [rbp+0E70h+punk], r15
0x18052fcda  mov     rax, [rcx]
0x18052fcdd  mov     rax, [rax+0D8h]
0x18052fce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fce9  test    eax, eax
0x18052fceb  js      loc_18052FE18
0x18052fcf1  mov     rcx, [rbp+0E70h+punk]; punk
0x18052fcf5  lea     r9, [rbp+0E70h+ppvOut]; ppvOut
0x18052fcf9  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x18052fd00  mov     [rbp+0E70h+ppvOut], r15
0x18052fd04  lea     rdx, SID_STabWindowManager; guidService
0x18052fd0b  call    cs:__imp_IUnknown_QueryService
0x18052fd12  nop     dword ptr [rax+rax+00h]
0x18052fd17  test    eax, eax
0x18052fd19  js      loc_18052FE0F
0x18052fd1f  mov     rcx, [rbp+0E70h+ppvOut]
0x18052fd23  lea     rdx, [rsp+0F70h+var_F08]
0x18052fd28  mov     [rsp+0F70h+var_F08], r15
0x18052fd2d  mov     rax, [rcx]
0x18052fd30  mov     rax, [rax+38h]
0x18052fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fd39  test    eax, eax
0x18052fd3b  js      loc_18052FE05
0x18052fd41  mov     rcx, [rsp+0F70h+var_F08]
0x18052fd46  lea     rdx, [rsp+0F70h+hWnd]
0x18052fd4b  mov     [rsp+0F70h+hWnd], r15
0x18052fd50  mov     rax, [rcx]
0x18052fd53  mov     rax, [rax+108h]
0x18052fd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fd5f  test    eax, eax
0x18052fd61  js      loc_18052FE05
0x18052fd67  mov     rcx, [rsp+0F70h+hWnd]; hWnd
0x18052fd6c  lea     rdx, [rsp+0F70h+dwProcessId]; lpdwProcessId
0x18052fd71  mov     [rsp+0F70h+dwProcessId], r15d
0x18052fd76  call    cs:__imp_GetWindowThreadProcessId
0x18052fd7d  nop     dword ptr [rax+rax+00h]
0x18052fd82  mov     ecx, [rsp+0F70h+dwProcessId]
0x18052fd86  lea     rdx, [rsp+0F70h+var_F20]
0x18052fd8b  mov     [rsp+0F70h+var_F20], r15d
0x18052fd90  call    cs:__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z; IsoGetProcessIdIsoIntegrity(ulong,_IsoIntegrity *)
0x18052fd97  nop     dword ptr [rax+rax+00h]
0x18052fd9c  test    eax, eax
0x18052fd9e  js      short loc_18052FE05
0x18052fda0  lea     rcx, [rsp+0F70h+var_F24]
0x18052fda5  mov     [rsp+0F70h+var_F24], r15d
0x18052fdaa  call    cs:__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z; IEGetCOMCallerIntegrity(_IsoIntegrity *)
0x18052fdb1  nop     dword ptr [rax+rax+00h]
0x18052fdb6  test    eax, eax
0x18052fdb8  js      short loc_18052FE05
0x18052fdba  mov     eax, [rsp+0F70h+var_F24]
0x18052fdbe  cmp     [rsp+0F70h+var_F20], eax
0x18052fdc2  jnz     short loc_18052FE05
0x18052fdc4  mov     rcx, [rsp+0F70h+var_F08]
0x18052fdc9  lea     rdx, [rsp+0F70h+var_EF8]
0x18052fdce  mov     [rsp+0F70h+var_EF8], r15
0x18052fdd3  mov     rax, [rcx]
0x18052fdd6  mov     rax, [rax+0A8h]
0x18052fddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18052fde2  test    eax, eax
0x18052fde4  js      short loc_18052FDFB
0x18052fde6  mov     rdx, [rsp+0F70h+var_EF8]; struct IUri *
0x18052fdeb  lea     rcx, [rbp+0E70h+var_ED8]; this
0x18052fdef  xor     r8d, r8d; enum __MIDL_IUri_0001
0x18052fdf2  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x18052fdf7  test    eax, eax
0x18052fdf9  jns     short loc_18052FE37
0x18052fdfb  lea     rcx, [rsp+0F70h+var_EF8]; void *
0x18052fe00  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe05  lea     rcx, [rsp+0F70h+var_F08]; void *
0x18052fe0a  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe0f  lea     rcx, [rbp+0E70h+ppvOut]; void *
0x18052fe13  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe18  lea     rcx, [rbp+0E70h+punk]; void *
0x18052fe1c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe21  lea     rcx, [rsp+0F70h+var_F00]; void *
0x18052fe26  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe2b  mov     edx, [rsp+0F70h+var_F28]
0x18052fe2f  add     ebx, r12d
0x18052fe32  jmp     loc_18052FC5D
0x18052fe37  lea     rcx, [rsp+0F70h+var_EF8]; void *
0x18052fe3c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe41  lea     rcx, [rsp+0F70h+var_F08]; void *
0x18052fe46  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe4b  lea     rcx, [rbp+0E70h+ppvOut]; void *
0x18052fe4f  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe54  lea     rcx, [rbp+0E70h+punk]; void *
0x18052fe58  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe5d  lea     rcx, [rsp+0F70h+var_F00]; void *
0x18052fe62  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18052fe67  mov     rcx, [rsp+0F70h+pv]; pv
0x18052fe6c  call    cs:__imp_CoTaskMemFree
0x18052fe73  nop     dword ptr [rax+rax+00h]
0x18052fe78  xor     edx, edx; Val
0x18052fe7a  lea     rcx, [rbp+0E70h+var_870]; void *
0x18052fe81  mov     r8d, 820h; Size
0x18052fe87  call    memset_0
0x18052fe8c  mov     rbx, r15
0x18052fe8f  xor     edx, edx; Val
0x18052fe91  lea     rcx, [rbp+0E70h+pszPath]; void *
0x18052fe95  mov     r8d, 208h; Size
0x18052fe9b  call    memset_0
0x18052fea0  lea     rax, qword_18064A330
0x18052fea7  mov     [rsp+0F70h+ppv], r15; enum _EXT_ARCHITECTURE *
0x18052feac  mov     rcx, rbx
0x18052feaf  lea     rdx, [rbp+0E70h+pszPath]; unsigned __int16 *
0x18052feb3  shl     rcx, 4
0x18052feb7  mov     r9d, 13h; unsigned int
0x18052febd  add     rcx, rax; struct _GUID *
0x18052fec0  mov     r8d, 104h; unsigned __int64
0x18052fec6  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x18052fecb  mov     edi, eax
0x18052fecd  test    eax, eax
0x18052fecf  js      loc_180530027
0x18052fed5  lea     rax, [rsp+0F70h+dwProcessId]
0x18052feda  mov     [rsp+0F70h+var_F24], r15d
0x18052fedf  mov     [rsp+0F70h+var_F48], rax; unsigned int *
0x18052fee4  lea     r9, [rsp+0F70h+var_F28]; unsigned int *
0x18052fee9  lea     rax, [rsp+0F70h+var_F1C]
0x18052feee  mov     [rsp+0F70h+var_F20], r15d
0x18052fef3  lea     r8, [rsp+0F70h+var_F20]; unsigned int *
0x18052fef8  mov     [rsp+0F70h+ppv], rax; unsigned int *
0x18052fefd  lea     rdx, [rsp+0F70h+var_F24]; unsigned int *
0x18052ff02  mov     [rsp+0F70h+var_F28], r15d
0x18052ff07  lea     rcx, [rbp+0E70h+pszPath]; lpwstrFilename
0x18052ff0b  mov     [rsp+0F70h+var_F1C], r15d
0x18052ff10  mov     [rsp+0F70h+dwProcessId], r15d
0x18052ff15  call    ?Ext_GetFileVersion@@YAJPEBGPEAK1111@Z; Ext_GetFileVersion(ushort const *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x18052ff1a  mov     edi, eax
0x18052ff1c  test    eax, eax
0x18052ff1e  js      loc_180530027
0x18052ff24  lea     rcx, [rbp+0E70h+pszPath]; pszPath
0x18052ff28  call    cs:__imp_PathFindFileNameW
0x18052ff2f  nop     dword ptr [rax+rax+00h]
0x18052ff34  mov     rsi, rax
0x18052ff37  lea     rax, [rbp+0E70h+pszPath]
0x18052ff3b  cmp     rsi, rax
0x18052ff3e  jz      loc_180530027
0x18052ff44  xor     edx, edx; Val
0x18052ff46  lea     rcx, [rbp+0E70h+var_C90]; void *
0x18052ff4d  mov     r8d, 208h; Size
0x18052ff53  call    memset_0
0x18052ff58  mov     edx, [rsp+0F70h+var_F20]
0x18052ff5c  lea     r8, aDDDD; "%d.%d.%d.%d"
0x18052ff63  mov     r9d, [rsp+0F70h+var_F24]
0x18052ff68  movzx   ecx, dx
0x18052ff6b  mov     [rsp+0F70h+var_F40], ecx
0x18052ff6f  lea     rcx, [rbp+0E70h+var_C90]; unsigned __int16 *
0x18052ff76  shr     edx, 10h
0x18052ff79  mov     dword ptr [rsp+0F70h+var_F48], edx
0x18052ff7d  mov     edx, 104h; unsigned __int64
0x18052ff82  movzx   eax, r9w
0x18052ff86  shr     r9d, 10h
0x18052ff8a  mov     dword ptr [rsp+0F70h+ppv], eax
0x18052ff8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18052ff93  mov     edi, eax
0x18052ff95  test    eax, eax
0x18052ff97  js      loc_180530027
0x18052ff9d  xor     r9d, r9d; unsigned __int64 *
0x18052ffa0  mov     [rsp+0F70h+hWnd], r15
0x18052ffa5  lea     r8, [rsp+0F70h+hWnd]; unsigned __int16 **
0x18052ffaa  lea     rdx, [rbp+0E70h+var_C90]; unsigned __int16 *
0x18052ffb1  call    ?EncodeValue@CIEUserBrokerObject@@IEAAJPEAGPEAPEAGPEA_K@Z; CIEUserBrokerObject::EncodeValue(ushort *,ushort * *,unsigned __int64 *)
0x18052ffb6  mov     edi, eax
0x18052ffb8  test    eax, eax
0x18052ffba  js      short loc_180530027
0x18052ffbc  xor     edx, edx; Val
0x18052ffbe  lea     rcx, [rbp+0E70h+var_A80]; void *
0x18052ffc5  mov     r8d, 208h; Size
0x18052ffcb  call    memset_0
0x18052ffd0  mov     r15, [rsp+0F70h+hWnd]
0x18052ffd5  lea     r8, aSS_15; "%s:%s;"
0x18052ffdc  mov     r9, rsi
0x18052ffdf  mov     [rsp+0F70h+ppv], r15
0x18052ffe4  mov     edx, 104h; unsigned __int64
0x18052ffe9  lea     rcx, [rbp+0E70h+var_A80]; unsigned __int16 *
0x18052fff0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18052fff5  mov     edi, eax
0x18052fff7  test    eax, eax
0x18052fff9  js      short loc_180530015
0x18052fffb  lea     r8, [rbp+0E70h+var_A80]; unsigned __int16 *
0x180530002  mov     edx, 410h; unsigned __int64
0x180530007  lea     rcx, [rbp+0E70h+var_870]; unsigned __int16 *
0x18053000e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180530013  mov     edi, eax
0x180530015  mov     rcx, r15; pv
0x180530018  call    cs:__imp_CoTaskMemFree
0x18053001f  nop     dword ptr [rax+rax+00h]
0x180530024  xor     r15d, r15d
0x180530027  add     rbx, r12
0x18053002a  cmp     rbx, 3
0x18053002e  jnz     loc_18052FE8F
0x180530034  mov     [rsp+0F70h+hWnd], r15
0x180530039  mov     rsi, r15
0x18053003c  mov     [rsp+0F70h+pv], r15
0x180530041  mov     r11, r15
0x180530044  test    r13, r13
0x180530047  jz      short loc_180530067
0x180530049  lea     r9, [rsp+0F70h+pv]; unsigned __int64 *
0x18053004e  mov     rdx, r13; unsigned __int16 *
0x180530051  lea     r8, [rsp+0F70h+hWnd]; unsigned __int16 **
0x180530056  call    ?EncodeValue@CIEUserBrokerObject@@IEAAJPEAGPEAPEAGPEA_K@Z; CIEUserBrokerObject::EncodeValue(ushort *,ushort * *,unsigned __int64 *)
0x18053005b  mov     r11, [rsp+0F70h+pv]
0x180530060  mov     edi, eax
0x180530062  mov     rsi, [rsp+0F70h+hWnd]
0x180530067  mov     rbx, r15
0x18053006a  test    edi, edi
0x18053006c  js      loc_18053017C
0x180530072  lea     r8, [rsp+0F70h+hWnd]; unsigned __int64 *
0x180530077  mov     [rsp+0F70h+hWnd], r15
0x18053007c  mov     edx, 410h; unsigned __int64
0x180530081  lea     rcx, [rbp+0E70h+var_870]; unsigned __int16 *
0x180530088  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
  ... truncated ...
```
