# CIEUserBrokerObject::QueueExtTelWorker(ushort const *,ulong,ushort const *)

- ea: `0x1804f0850`
- end: `0x1804f0eba`
- name: `?QueueExtTelWorker@CIEUserBrokerObject@@AEAAJPEBGK0@Z`
- size: `1642`
- prototype: `int(CIEUserBrokerObject *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1804ef6a0`
- `0x1804f0f60`
- `0x1804f1000`

## callees

- `0x18000b9e0`
- `0x18000c530`
- `0x18000f3d0`
- `0x180053590`
- `0x18005ef58`
- `0x180093ec0`
- `0x18009a024`
- `0x1804e04d4`
- `0x1804efec0`
- `0x1804f0850`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1804f0be8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1804f0be8`
- `USER32!GetForegroundWindow` at `0x1804f08ef`
- `USER32!GetForegroundWindow` at `0x1804f08ef`
- `USER32!GetWindowThreadProcessId` at `0x1804f0a4e`
- `USER32!GetWindowThreadProcessId` at `0x1804f0a4e`
- `USER32!GetAncestor` at `0x1804f08fc`
- `USER32!GetAncestor` at `0x1804f08fc`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e29`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e36`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e44`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e29`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e36`
- `OLEAUT32!__imp_SysFreeString` at `0x1804f0e44`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1804f08e1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x1804f08e1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1804f0da8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x1804f0da8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0b32`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0cd2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e0d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e66`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0b32`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0cd2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e0d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1804f0e66`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1804f09e9`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1804f09e9`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x1804f0a76`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x1804f0a76`
- `msIso!__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z` at `0x1804f0a62`
- `msIso!__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z` at `0x1804f0a62`

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
    ModulePath = Ext_GetModulePath((const struct _GUID *)&qword_180606280[2 * j], pszPath, 0x104u, 0x13u, 0);
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
0x1804f0850  push    rbp
0x1804f0852  push    rbx
0x1804f0853  push    rsi
0x1804f0854  push    rdi
0x1804f0855  push    r12
0x1804f0857  push    r13
0x1804f0859  push    r14
0x1804f085b  push    r15
0x1804f085d  lea     rbp, [rsp-0E38h]
0x1804f0865  sub     rsp, 0F38h
0x1804f086c  mov     rax, cs:__security_cookie
0x1804f0873  xor     rax, rsp
0x1804f0876  mov     [rbp+0E70h+var_50], rax
0x1804f087d  mov     al, cs:?g_extTelWrapperIsInitialized@@3_NA; bool g_extTelWrapperIsInitialized
0x1804f0883  mov     r13, r9
0x1804f0886  neg     al
0x1804f0888  sbb     r14, r14
0x1804f088b  and     r14, cs:?g_pExtTelWrapper@@3PEAVCExtTelWrapper@@EA; CExtTelWrapper * g_pExtTelWrapper
0x1804f0892  jz      loc_1804F0E90
0x1804f0898  xor     r15d, r15d
0x1804f089b  mov     [rbp+0E70h+var_EC8], 0Bh
0x1804f08a2  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x1804f08a9  mov     [rbp+0E70h+var_ED0], r15
0x1804f08ad  mov     [rbp+0E70h+var_ED8], rax
0x1804f08b1  lea     r9, _GUID_e66a412d_14b3_425c_82ac_5b7716cca5a7; riid
0x1804f08b8  xorps   xmm0, xmm0
0x1804f08bb  mov     [rbp+0E70h+var_EB0], r15d
0x1804f08bf  lea     rax, [rbp+0E70h+var_EE0]
0x1804f08c3  mov     [rbp+0E70h+var_EE0], r15
0x1804f08c7  lea     r12d, [r15+1]
0x1804f08cb  mov     [rsp+0F70h+ppv], rax; ppv
0x1804f08d0  mov     r8d, r12d; dwClsContext
0x1804f08d3  lea     rcx, CLSID_BrowserApplicationState; rclsid
0x1804f08da  xor     edx, edx; pUnkOuter
0x1804f08dc  movdqu  [rbp+0E70h+var_EC0], xmm0
0x1804f08e1  call    cs:__imp_CoCreateInstance
0x1804f08e7  test    eax, eax
0x1804f08e9  js      loc_1804F0B38
0x1804f08ef  call    cs:__imp_GetForegroundWindow
0x1804f08f5  mov     rcx, rax; hwnd
0x1804f08f8  lea     edx, [r15+3]; gaFlags
0x1804f08fc  call    cs:__imp_GetAncestor
0x1804f0902  mov     rcx, [rbp+0E70h+var_EE0]
0x1804f0906  lea     r8, [rsp+0F70h+var_F28]
0x1804f090b  mov     [rsp+0F70h+pv], r15
0x1804f0910  mov     rdi, rax
0x1804f0913  mov     [rsp+0F70h+var_F28], r15d
0x1804f0918  mov     rdx, [rcx]
0x1804f091b  mov     rax, [rdx+80h]
0x1804f0922  lea     rdx, [rsp+0F70h+pv]
0x1804f0927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f092c  test    eax, eax
0x1804f092e  js      loc_1804F0B38
0x1804f0934  mov     edx, [rsp+0F70h+var_F28]
0x1804f0938  mov     ebx, r15d
0x1804f093b  cmp     ebx, edx
0x1804f093d  jge     loc_1804F0B2D
0x1804f0943  mov     rax, [rsp+0F70h+pv]
0x1804f0948  movsxd  rcx, ebx
0x1804f094b  mov     r9, [rax+rcx*8]
0x1804f094f  cmp     r9, rdi
0x1804f0952  jz      short loc_1804F095F
0x1804f0954  lea     eax, [rdx-1]
0x1804f0957  cmp     ebx, eax
0x1804f0959  jnz     loc_1804F0AF5
0x1804f095f  mov     rcx, [rbp+0E70h+var_EE0]
0x1804f0963  lea     r8, [rsp+0F70h+var_F00]
0x1804f0968  mov     [rsp+0F70h+var_F00], r15
0x1804f096d  mov     rdx, r9
0x1804f0970  mov     rax, [rcx]
0x1804f0973  mov     rax, [rax+18h]
0x1804f0977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f097c  test    eax, eax
0x1804f097e  js      loc_1804F0AE7
0x1804f0984  mov     rcx, [rsp+0F70h+var_F00]
0x1804f0989  lea     rdx, [rsp+0F70h+var_F1C]
0x1804f098e  mov     [rsp+0F70h+var_F1C], r15d
0x1804f0993  mov     rax, [rcx]
0x1804f0996  mov     rax, [rax+40h]
0x1804f099a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f099f  test    eax, eax
0x1804f09a1  js      loc_1804F0AE7
0x1804f09a7  mov     rcx, [rsp+0F70h+var_F00]
0x1804f09ac  lea     r8, [rbp+0E70h+punk]
0x1804f09b0  mov     edx, [rsp+0F70h+var_F1C]
0x1804f09b4  mov     [rbp+0E70h+punk], r15
0x1804f09b8  mov     rax, [rcx]
0x1804f09bb  mov     rax, [rax+0D8h]
0x1804f09c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f09c7  test    eax, eax
0x1804f09c9  js      loc_1804F0ADE
0x1804f09cf  mov     rcx, [rbp+0E70h+punk]; punk
0x1804f09d3  lea     r9, [rbp+0E70h+ppvOut]; ppvOut
0x1804f09d7  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1; riid
0x1804f09de  mov     [rbp+0E70h+ppvOut], r15
0x1804f09e2  lea     rdx, SID_STabWindowManager; guidService
0x1804f09e9  call    cs:__imp_IUnknown_QueryService
0x1804f09ef  test    eax, eax
0x1804f09f1  js      loc_1804F0AD5
0x1804f09f7  mov     rcx, [rbp+0E70h+ppvOut]
0x1804f09fb  lea     rdx, [rsp+0F70h+var_F08]
0x1804f0a00  mov     [rsp+0F70h+var_F08], r15
0x1804f0a05  mov     rax, [rcx]
0x1804f0a08  mov     rax, [rax+38h]
0x1804f0a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f0a11  test    eax, eax
0x1804f0a13  js      loc_1804F0ACB
0x1804f0a19  mov     rcx, [rsp+0F70h+var_F08]
0x1804f0a1e  lea     rdx, [rsp+0F70h+hWnd]
0x1804f0a23  mov     [rsp+0F70h+hWnd], r15
0x1804f0a28  mov     rax, [rcx]
0x1804f0a2b  mov     rax, [rax+108h]
0x1804f0a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f0a37  test    eax, eax
0x1804f0a39  js      loc_1804F0ACB
0x1804f0a3f  mov     rcx, [rsp+0F70h+hWnd]; hWnd
0x1804f0a44  lea     rdx, [rsp+0F70h+dwProcessId]; lpdwProcessId
0x1804f0a49  mov     [rsp+0F70h+dwProcessId], r15d
0x1804f0a4e  call    cs:__imp_GetWindowThreadProcessId
0x1804f0a54  mov     ecx, [rsp+0F70h+dwProcessId]
0x1804f0a58  lea     rdx, [rsp+0F70h+var_F20]
0x1804f0a5d  mov     [rsp+0F70h+var_F20], r15d
0x1804f0a62  call    cs:__imp_?IsoGetProcessIdIsoIntegrity@@YAJKPEAW4_IsoIntegrity@@@Z; IsoGetProcessIdIsoIntegrity(ulong,_IsoIntegrity *)
0x1804f0a68  test    eax, eax
0x1804f0a6a  js      short loc_1804F0ACB
0x1804f0a6c  lea     rcx, [rsp+0F70h+var_F24]
0x1804f0a71  mov     [rsp+0F70h+var_F24], r15d
0x1804f0a76  call    cs:__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z; IEGetCOMCallerIntegrity(_IsoIntegrity *)
0x1804f0a7c  test    eax, eax
0x1804f0a7e  js      short loc_1804F0ACB
0x1804f0a80  mov     eax, [rsp+0F70h+var_F24]
0x1804f0a84  cmp     [rsp+0F70h+var_F20], eax
0x1804f0a88  jnz     short loc_1804F0ACB
0x1804f0a8a  mov     rcx, [rsp+0F70h+var_F08]
0x1804f0a8f  lea     rdx, [rsp+0F70h+var_EF8]
0x1804f0a94  mov     [rsp+0F70h+var_EF8], r15
0x1804f0a99  mov     rax, [rcx]
0x1804f0a9c  mov     rax, [rax+0A8h]
0x1804f0aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804f0aa8  test    eax, eax
0x1804f0aaa  js      short loc_1804F0AC1
0x1804f0aac  mov     rdx, [rsp+0F70h+var_EF8]; struct IUri *
0x1804f0ab1  lea     rcx, [rbp+0E70h+var_ED8]; this
0x1804f0ab5  xor     r8d, r8d; enum __MIDL_IUri_0001
0x1804f0ab8  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x1804f0abd  test    eax, eax
0x1804f0abf  jns     short loc_1804F0AFD
0x1804f0ac1  lea     rcx, [rsp+0F70h+var_EF8]; void *
0x1804f0ac6  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0acb  lea     rcx, [rsp+0F70h+var_F08]; void *
0x1804f0ad0  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0ad5  lea     rcx, [rbp+0E70h+ppvOut]; void *
0x1804f0ad9  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0ade  lea     rcx, [rbp+0E70h+punk]; void *
0x1804f0ae2  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0ae7  lea     rcx, [rsp+0F70h+var_F00]; void *
0x1804f0aec  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0af1  mov     edx, [rsp+0F70h+var_F28]
0x1804f0af5  add     ebx, r12d
0x1804f0af8  jmp     loc_1804F093B
0x1804f0afd  lea     rcx, [rsp+0F70h+var_EF8]; void *
0x1804f0b02  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0b07  lea     rcx, [rsp+0F70h+var_F08]; void *
0x1804f0b0c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0b11  lea     rcx, [rbp+0E70h+ppvOut]; void *
0x1804f0b15  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0b1a  lea     rcx, [rbp+0E70h+punk]; void *
0x1804f0b1e  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0b23  lea     rcx, [rsp+0F70h+var_F00]; void *
0x1804f0b28  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1804f0b2d  mov     rcx, [rsp+0F70h+pv]; pv
0x1804f0b32  call    cs:__imp_CoTaskMemFree
0x1804f0b38  xor     edx, edx; Val
0x1804f0b3a  lea     rcx, [rbp+0E70h+var_870]; void *
0x1804f0b41  mov     r8d, 820h; Size
0x1804f0b47  call    memset_0
0x1804f0b4c  mov     rbx, r15
0x1804f0b4f  xor     edx, edx; Val
0x1804f0b51  lea     rcx, [rbp+0E70h+pszPath]; void *
0x1804f0b55  mov     r8d, 208h; Size
0x1804f0b5b  call    memset_0
0x1804f0b60  lea     rax, qword_180606280
0x1804f0b67  mov     [rsp+0F70h+ppv], r15; enum _EXT_ARCHITECTURE *
0x1804f0b6c  mov     rcx, rbx
0x1804f0b6f  lea     rdx, [rbp+0E70h+pszPath]; unsigned __int16 *
0x1804f0b73  shl     rcx, 4
0x1804f0b77  mov     r9d, 13h; unsigned int
0x1804f0b7d  add     rcx, rax; struct _GUID *
0x1804f0b80  mov     r8d, 104h; unsigned __int64
0x1804f0b86  call    ?Ext_GetModulePath@@YAJAEBU_GUID@@PEAG_KKPEAW4_EXT_ARCHITECTURE@@@Z; Ext_GetModulePath(_GUID const &,ushort *,unsigned __int64,ulong,_EXT_ARCHITECTURE *)
0x1804f0b8b  mov     edi, eax
0x1804f0b8d  test    eax, eax
0x1804f0b8f  js      loc_1804F0CDB
0x1804f0b95  lea     rax, [rsp+0F70h+dwProcessId]
0x1804f0b9a  mov     [rsp+0F70h+var_F24], r15d
0x1804f0b9f  mov     [rsp+0F70h+var_F48], rax; unsigned int *
0x1804f0ba4  lea     r9, [rsp+0F70h+var_F28]; unsigned int *
0x1804f0ba9  lea     rax, [rsp+0F70h+var_F1C]
0x1804f0bae  mov     [rsp+0F70h+var_F20], r15d
0x1804f0bb3  lea     r8, [rsp+0F70h+var_F20]; unsigned int *
0x1804f0bb8  mov     [rsp+0F70h+ppv], rax; unsigned int *
0x1804f0bbd  lea     rdx, [rsp+0F70h+var_F24]; unsigned int *
0x1804f0bc2  mov     [rsp+0F70h+var_F28], r15d
0x1804f0bc7  lea     rcx, [rbp+0E70h+pszPath]; lpwstrFilename
0x1804f0bcb  mov     [rsp+0F70h+var_F1C], r15d
0x1804f0bd0  mov     [rsp+0F70h+dwProcessId], r15d
0x1804f0bd5  call    ?Ext_GetFileVersion@@YAJPEBGPEAK1111@Z; Ext_GetFileVersion(ushort const *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x1804f0bda  mov     edi, eax
0x1804f0bdc  test    eax, eax
0x1804f0bde  js      loc_1804F0CDB
0x1804f0be4  lea     rcx, [rbp+0E70h+pszPath]; pszPath
0x1804f0be8  call    cs:__imp_PathFindFileNameW
0x1804f0bee  mov     rsi, rax
0x1804f0bf1  lea     rax, [rbp+0E70h+pszPath]
0x1804f0bf5  cmp     rsi, rax
0x1804f0bf8  jz      loc_1804F0CDB
0x1804f0bfe  xor     edx, edx; Val
0x1804f0c00  lea     rcx, [rbp+0E70h+var_C90]; void *
0x1804f0c07  mov     r8d, 208h; Size
0x1804f0c0d  call    memset_0
0x1804f0c12  mov     edx, [rsp+0F70h+var_F20]
0x1804f0c16  lea     r8, aDDDD; "%d.%d.%d.%d"
0x1804f0c1d  mov     r9d, [rsp+0F70h+var_F24]
0x1804f0c22  movzx   ecx, dx
0x1804f0c25  mov     [rsp+0F70h+var_F40], ecx
0x1804f0c29  lea     rcx, [rbp+0E70h+var_C90]; unsigned __int16 *
0x1804f0c30  shr     edx, 10h
0x1804f0c33  mov     dword ptr [rsp+0F70h+var_F48], edx
0x1804f0c37  mov     edx, 104h; unsigned __int64
0x1804f0c3c  movzx   eax, r9w
0x1804f0c40  shr     r9d, 10h
0x1804f0c44  mov     dword ptr [rsp+0F70h+ppv], eax
0x1804f0c48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1804f0c4d  mov     edi, eax
0x1804f0c4f  test    eax, eax
0x1804f0c51  js      loc_1804F0CDB
0x1804f0c57  xor     r9d, r9d; unsigned __int64 *
0x1804f0c5a  mov     [rsp+0F70h+hWnd], r15
0x1804f0c5f  lea     r8, [rsp+0F70h+hWnd]; unsigned __int16 **
0x1804f0c64  lea     rdx, [rbp+0E70h+var_C90]; unsigned __int16 *
0x1804f0c6b  call    ?EncodeValue@CIEUserBrokerObject@@IEAAJPEAGPEAPEAGPEA_K@Z; CIEUserBrokerObject::EncodeValue(ushort *,ushort * *,unsigned __int64 *)
0x1804f0c70  mov     edi, eax
0x1804f0c72  test    eax, eax
0x1804f0c74  js      short loc_1804F0CDB
0x1804f0c76  xor     edx, edx; Val
0x1804f0c78  lea     rcx, [rbp+0E70h+var_A80]; void *
0x1804f0c7f  mov     r8d, 208h; Size
0x1804f0c85  call    memset_0
0x1804f0c8a  mov     r15, [rsp+0F70h+hWnd]
0x1804f0c8f  lea     r8, aSS_15; "%s:%s;"
0x1804f0c96  mov     r9, rsi
0x1804f0c99  mov     [rsp+0F70h+ppv], r15
0x1804f0c9e  mov     edx, 104h; unsigned __int64
0x1804f0ca3  lea     rcx, [rbp+0E70h+var_A80]; unsigned __int16 *
0x1804f0caa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1804f0caf  mov     edi, eax
0x1804f0cb1  test    eax, eax
0x1804f0cb3  js      short loc_1804F0CCF
0x1804f0cb5  lea     r8, [rbp+0E70h+var_A80]; unsigned __int16 *
0x1804f0cbc  mov     edx, 410h; unsigned __int64
0x1804f0cc1  lea     rcx, [rbp+0E70h+var_870]; unsigned __int16 *
0x1804f0cc8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1804f0ccd  mov     edi, eax
0x1804f0ccf  mov     rcx, r15; pv
0x1804f0cd2  call    cs:__imp_CoTaskMemFree
0x1804f0cd8  xor     r15d, r15d
0x1804f0cdb  add     rbx, r12
0x1804f0cde  cmp     rbx, 3
0x1804f0ce2  jnz     loc_1804F0B4F
0x1804f0ce8  mov     [rsp+0F70h+hWnd], r15
0x1804f0ced  mov     rsi, r15
0x1804f0cf0  mov     [rsp+0F70h+pv], r15
0x1804f0cf5  mov     r11, r15
0x1804f0cf8  test    r13, r13
0x1804f0cfb  jz      short loc_1804F0D1B
0x1804f0cfd  lea     r9, [rsp+0F70h+pv]; unsigned __int64 *
0x1804f0d02  mov     rdx, r13; unsigned __int16 *
0x1804f0d05  lea     r8, [rsp+0F70h+hWnd]; unsigned __int16 **
0x1804f0d0a  call    ?EncodeValue@CIEUserBrokerObject@@IEAAJPEAGPEAPEAGPEA_K@Z; CIEUserBrokerObject::EncodeValue(ushort *,ushort * *,unsigned __int64 *)
0x1804f0d0f  mov     r11, [rsp+0F70h+pv]
0x1804f0d14  mov     edi, eax
0x1804f0d16  mov     rsi, [rsp+0F70h+hWnd]
0x1804f0d1b  mov     rbx, r15
0x1804f0d1e  test    edi, edi
0x1804f0d20  js      loc_1804F0E20
0x1804f0d26  lea     r8, [rsp+0F70h+hWnd]; unsigned __int64 *
0x1804f0d2b  mov     [rsp+0F70h+hWnd], r15
0x1804f0d30  mov     edx, 410h; unsigned __int64
0x1804f0d35  lea     rcx, [rbp+0E70h+var_870]; unsigned __int16 *
0x1804f0d3c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1804f0d41  test    eax, eax
0x1804f0d43  js      loc_1804F0E20
0x1804f0d49  mov     r15, [rsp+0F70h+hWnd]
0x1804f0d4e  test    r15, r15
0x1804f0d51  jnz     short loc_1804F0D5C
0x1804f0d53  test    r11, r11
0x1804f0d56  jz      loc_1804F0E1D
0x1804f0d5c  lea     rcx, [r15+r11]
0x1804f0d60  mov     r13d, 0Bh
0x1804f0d66  cmp     rcx, r11
  ... truncated ...
```
