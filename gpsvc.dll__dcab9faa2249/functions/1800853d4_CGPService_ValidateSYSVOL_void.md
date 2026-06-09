# CGPService::ValidateSYSVOL(void)

- ea: `0x1800853d4`
- end: `0x180085c35`
- name: `?ValidateSYSVOL@CGPService@@QEAAXXZ`
- size: `2145`
- prototype: `void __fastcall(CGPService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180085c40`

## callees

- `0x180046de0`
- `0x1800535a0`
- `0x1800585e8`
- `0x18005ce04`
- `0x180075ec0`
- `0x180084e38`
- `0x1800853d4`
- `0x180088574`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800857f1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800857f1`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800858c5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800858c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008542e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18008542e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008555c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008555c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008550a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180085beb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008550a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180085beb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085456`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180085456`
- `OLEAUT32!__imp_SysFreeString` at `0x180085529`
- `OLEAUT32!__imp_SysFreeString` at `0x180085a01`
- `OLEAUT32!__imp_SysFreeString` at `0x180085a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180085b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180085b0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c15`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c20`
- `OLEAUT32!__imp_SysFreeString` at `0x180085529`
- `OLEAUT32!__imp_SysFreeString` at `0x180085a01`
- `OLEAUT32!__imp_SysFreeString` at `0x180085a0f`
- `OLEAUT32!__imp_SysFreeString` at `0x180085b00`
- `OLEAUT32!__imp_SysFreeString` at `0x180085b0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c15`
- `OLEAUT32!__imp_SysFreeString` at `0x180085c20`
- `OLEAUT32!__imp_VariantInit` at `0x180085722`
- `OLEAUT32!__imp_VariantInit` at `0x180085722`
- `srvcli!NetFileClose` at `0x180085937`
- `srvcli!NetFileClose` at `0x180085937`
- `srvcli!NetFileEnum` at `0x180085856`
- `srvcli!NetFileEnum` at `0x180085856`
- `netutils!NetApiBufferFree` at `0x1800859f7`
- `netutils!NetApiBufferFree` at `0x1800859f7`

## string_xrefs

- `0x18008540e`: `SELECT * FROM DfsrReplicationGroupConfig WHERE ReplicationGroupType = 1`
- `0x1800854c7`: `CGPService::ValidateSYSVOL ConnectServer (Namespace: %ws) failed 0x%x`
- `0x1800854f4`: `CGPService::ValidateSYSVOL ConnectServer (Namespace: %ws) failed 0x%x`
- `0x180085bb0`: `CGPService::ValidateSYSVOL CoCreate CLSID_WbemLocator failed 0x%x`
- `0x180085bd5`: `CGPService::ValidateSYSVOL CoCreate CLSID_WbemLocator failed 0x%x`
- `0x18008558d`: `CGPService::ValidateSYSVOL CoSetProxyBlanket failed with 0x%x`
- `0x1800855c3`: `CGPService::ValidateSYSVOL CoSetProxyBlanket failed with 0x%x`
- `0x18008562c`: `CGPService::ValidateSYSVOL ExecQuery(spDFRSSysvolEnum) failed 0x%x`
- `0x180085662`: `CGPService::ValidateSYSVOL ExecQuery(spDFRSSysvolEnum) failed 0x%x`
- `0x180085b63`: `CGPService::ValidateSYSVOL spDFRSSysvolEnum->Next failed 0x%x`
- `0x180085b88`: `CGPService::ValidateSYSVOL spDFRSSysvolEnum->Next failed 0x%x`
- `0x1800856db`: `CGPService::ValidateSYSVOL The SYSVOL Group has been located.`
- `0x180085700`: `CGPService::ValidateSYSVOL The SYSVOL Group has been located.`
- `0x180085ac6`: `CGPService::ValidateSYSVOL: Event Path is NULL.`
- `0x180085aeb`: `CGPService::ValidateSYSVOL: Event Path is NULL.`
- `0x180085979`: `CGPService::ValidateSYSVOL: NetFileClose closed %s`
- `0x1800859a1`: `CGPService::ValidateSYSVOL: NetFileClose closed %s`
- `0x1800859da`: `CGPService::ValidateSYSVOL: NetFileClose failed with %d`
- `0x180085a43`: `CGPService::ValidateSYSVOL: NetFileClose failed with %d`
- `0x1800858ea`: `CGPService::ValidateSYSVOL: NetFileEnum considered %s`
- `0x180085913`: `CGPService::ValidateSYSVOL: NetFileEnum considered %s`
- `0x180085a6b`: `CGPService::ValidateSYSVOL: NetFileEnum failed with %d`
- `0x180085a9b`: `CGPService::ValidateSYSVOL: NetFileEnum failed with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CGPService::ValidateSYSVOL(CGPService *this)
{
  DWORD v1; // r13d
  HRESULT v2; // edi
  HRESULT v3; // eax
  BSTR v4; // rbx
  int v5; // eax
  OLECHAR *v6; // rcx
  unsigned int v7; // eax
  int v8; // eax
  int v9; // r12d
  unsigned int v10; // eax
  CGPService *v11; // rcx
  const unsigned __int16 *LastReplicationIssue; // rax
  wchar_t *v13; // r12
  DWORD v14; // eax
  const WCHAR *GpoPath; // rax
  DWORD v16; // eax
  DWORD v17; // r13d
  OLECHAR *v18; // rcx
  IUnknown *pProxy; // [rsp+50h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-49h] BYREF
  BSTR v22; // [rsp+68h] [rbp-41h] BYREF
  __int64 v23; // [rsp+70h] [rbp-39h] BYREF
  __int64 v24; // [rsp+78h] [rbp-31h] BYREF
  BSTR v25; // [rsp+80h] [rbp-29h] BYREF
  const WCHAR *v26; // [rsp+88h] [rbp-21h]
  LPBYTE bufptr; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG *p_pvarg; // [rsp+98h] [rbp-11h] BYREF
  BSTR v29; // [rsp+A0h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-1h] BYREF
  HRESULT v31; // [rsp+C0h] [rbp+17h]
  wchar_t *Str; // [rsp+C8h] [rbp+1Fh] BYREF
  LPCWCH lpString1; // [rsp+D0h] [rbp+27h]
  __int64 v34; // [rsp+D8h] [rbp+2Fh]
  CGPService *v35; // [rsp+110h] [rbp+67h] BYREF
  DWORD entriesread; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD totalentries; // [rsp+120h] [rbp+77h] BYREF
  int v38; // [rsp+128h] [rbp+7Fh]

  v35 = this;
  XBStr::XBStr((XBStr *)&v22, L"WQL");
  XBStr::XBStr((XBStr *)&v29, L"Root\\MicrosoftDfs");
  XBStr::XBStr((XBStr *)&bstrString, L"SELECT * FROM DfsrReplicationGroupConfig WHERE ReplicationGroupType = 1");
  v1 = 0;
  ppv = 0;
  pProxy = 0;
  v2 = CoInitializeEx(0, 0);
  v31 = v2;
  v3 = CoCreateInstance(&CLSID_WbemLocator, 0, 5u, &IID_IUnknown, &ppv);
  if ( v3 >= 0 )
  {
    v4 = v29;
    v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, int, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
           ppv,
           v29,
           0,
           0,
           0,
           128,
           0,
           0,
           &pProxy);
    if ( v5 >= 0 )
    {
      v7 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
      if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147467262 )
      {
        v24 = 0;
        v8 = ((__int64 (__fastcall *)(IUnknown *, BSTR, BSTR, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
               pProxy,
               v22,
               bstrString,
               32,
               0,
               &v24);
        if ( v8 < 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL ExecQuery(spDFRSSysvolEnum) failed 0x%x", (unsigned int)v8);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(
                2u,
                L"CGPService::ValidateSYSVOL ExecQuery(spDFRSSysvolEnum) failed 0x%x",
                (unsigned int)v8);
            }
          }
LABEL_92:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
          goto LABEL_9;
        }
        v9 = 0;
LABEL_28:
        if ( v9 )
          goto LABEL_92;
        v23 = 0;
        LODWORD(v35) = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, CGPService **))(*(_QWORD *)v24 + 32LL))(
                v24,
                0xFFFFFFFFLL,
                1,
                &v23,
                &v35);
        if ( (v10 & 0x80000000) != 0 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL spDFRSSysvolEnum->Next failed 0x%x", v10);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CGPService::ValidateSYSVOL spDFRSSysvolEnum->Next failed 0x%x", v10);
            }
          }
          goto LABEL_91;
        }
        if ( !(_DWORD)v35 )
          goto LABEL_91;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CGPService::ValidateSYSVOL The SYSVOL Group has been located.", v10);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CGPService::ValidateSYSVOL The SYSVOL Group has been located.", v10);
          }
        }
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        p_pvarg = &pvarg;
        XBStr::XBStr((XBStr *)&v25, L"ReplicationGroupGuid");
        v9 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v23 + 32LL))(
               v23,
               v25,
               0,
               &pvarg,
               0,
               0);
        v38 = v9;
        if ( v9 < 0 || pvarg.vt != 8 )
          goto LABEL_73;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, pvarg.bstrVal);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, pvarg.bstrVal);
          }
        }
        LastReplicationIssue = CGPService::GetLastReplicationIssue(v11, pvarg.bstrVal);
        XBStr::XBStr((XBStr *)&Str, LastReplicationIssue);
        v13 = Str;
        if ( !Str )
        {
          v18 = 0;
LABEL_90:
          SysFreeString(v18);
          SysFreeString(v25);
          XVariant::~XVariant(&p_pvarg);
LABEL_91:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
          goto LABEL_92;
        }
        if ( !wcsstr(Str, L"\\Policies\\{") )
        {
          CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4192, 0, v13);
LABEL_89:
          v18 = v13;
          goto LABEL_90;
        }
        lpString1 = GetGpoPath(v13);
        if ( !lpString1 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"CGPService::ValidateSYSVOL: Event Path is NULL.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"CGPService::ValidateSYSVOL: Event Path is NULL.");
            }
          }
          goto LABEL_89;
        }
        bufptr = 0;
        entriesread = 0;
        totalentries = 0;
        v14 = NetFileEnum(0, 0, 0, 3u, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0);
        if ( v14 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL: NetFileEnum failed with %d", v14);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CGPService::ValidateSYSVOL: NetFileEnum failed with %d", v14);
            }
          }
          goto LABEL_70;
        }
        while ( 1 )
        {
          if ( v1 >= entriesread )
            goto LABEL_69;
          v34 = 32LL * v1;
          GpoPath = GetGpoPath(*(const unsigned __int16 **)&bufptr[v34 + 16]);
          v26 = GpoPath;
          if ( GpoPath )
          {
            if ( CompareStringEx(&DomainName, 1u, lpString1, -1, GpoPath, -1, 0, 0, 0) == 2 )
            {
              v16 = NetFileClose(0, *(_DWORD *)&bufptr[v34]);
              v17 = v16;
              if ( v16 )
              {
                CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4194, v16, v13);
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL: NetFileClose failed with %d", v17);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    RedirectDebugMsg(2u, L"CGPService::ValidateSYSVOL: NetFileClose failed with %d", v17);
                  }
                }
LABEL_69:
                v1 = 0;
                goto LABEL_70;
              }
              CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4193, 0, v13);
              v1 = 0;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"CGPService::ValidateSYSVOL: NetFileClose closed %s", v26);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"CGPService::ValidateSYSVOL: NetFileClose closed %s", v26);
                }
              }
LABEL_70:
              if ( bufptr )
                NetApiBufferFree(bufptr);
              SysFreeString(v13);
              v9 = v38;
LABEL_73:
              SysFreeString(v25);
              XVariant::~XVariant(&p_pvarg);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
              goto LABEL_28;
            }
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"CGPService::ValidateSYSVOL: NetFileEnum considered %s", v26);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"CGPService::ValidateSYSVOL: NetFileEnum considered %s", v26);
              }
            }
          }
          ++v1;
        }
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL CoSetProxyBlanket failed with 0x%x", v7);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CGPService::ValidateSYSVOL CoSetProxyBlanket failed with 0x%x", v7);
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL ConnectServer (Namespace: %ws) failed 0x%x", v4, (unsigned int)v5);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"CGPService::ValidateSYSVOL ConnectServer (Namespace: %ws) failed 0x%x",
          v4,
          (unsigned int)v5);
      }
    }
LABEL_9:
    if ( v2 >= 0 )
      CoUninitialize();
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    SysFreeString(bstrString);
    v6 = v4;
    goto LABEL_110;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CGPService::ValidateSYSVOL CoCreate CLSID_WbemLocator failed 0x%x", (unsigned int)v3);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CGPService::ValidateSYSVOL CoCreate CLSID_WbemLocator failed 0x%x", (unsigned int)v3);
    }
  }
  if ( v2 >= 0 )
    CoUninitialize();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pProxy);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  SysFreeString(bstrString);
  v6 = v29;
LABEL_110:
  SysFreeString(v6);
  SysFreeString(v22);
}

```

## disassembly

```asm
0x1800853d4  mov     [rsp-8+arg_0], rcx
0x1800853d9  push    rbp
0x1800853da  push    rbx
0x1800853db  push    rdi
0x1800853dc  push    r12
0x1800853de  push    r13
0x1800853e0  lea     rbp, [rsp-37h]
0x1800853e5  sub     rsp, 0E0h
0x1800853ec  lea     rdx, aWql; "WQL"
0x1800853f3  lea     rcx, [rbp+57h+var_98]; this
0x1800853f7  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800853fc  nop
0x1800853fd  lea     rdx, aRootMicrosoftd; "Root\\MicrosoftDfs"
0x180085404  lea     rcx, [rbp+57h+var_60]; this
0x180085408  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x18008540d  nop
0x18008540e  lea     rdx, aSelectFromDfsr; "SELECT * FROM DfsrReplicationGroupConfi"...
0x180085415  lea     rcx, [rbp+57h+bstrString]; this
0x180085419  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x18008541e  nop
0x18008541f  xor     r13d, r13d
0x180085422  mov     [rbp+57h+var_A8], r13
0x180085426  mov     [rbp+57h+pProxy], r13
0x18008542a  xor     edx, edx; dwCoInit
0x18008542c  xor     ecx, ecx; pvReserved
0x18008542e  call    cs:__imp_CoInitializeEx
0x180085434  mov     edi, eax
0x180085436  mov     [rbp+57h+var_40], eax
0x180085439  lea     rax, [rbp+57h+var_A8]
0x18008543d  mov     [rsp+100h+ppv], rax; ppv
0x180085442  lea     r9, IID_IUnknown; riid
0x180085449  xor     edx, edx; pUnkOuter
0x18008544b  lea     r8d, [r13+5]; dwClsContext
0x18008544f  lea     rcx, CLSID_WbemLocator; rclsid
0x180085456  call    cs:__imp_CoCreateInstance
0x18008545c  mov     r8d, eax
0x18008545f  test    eax, eax
0x180085461  js      loc_180085B9B
0x180085467  mov     rcx, [rbp+57h+var_A8]
0x18008546b  mov     rax, [rcx]
0x18008546e  lea     rdx, [rbp+57h+pProxy]
0x180085472  mov     [rsp+100h+resume_handle], rdx
0x180085477  mov     qword ptr [rsp+100h+dwCapabilities], r13
0x18008547c  mov     [rsp+100h+pAuthInfo], r13
0x180085481  mov     [rsp+100h+dwImpLevel], 80h
0x180085489  mov     [rsp+100h+ppv], r13
0x18008548e  xor     r9d, r9d
0x180085491  xor     r8d, r8d
0x180085494  mov     rbx, [rbp+57h+var_60]
0x180085498  mov     rdx, rbx
0x18008549b  mov     rax, [rax+18h]
0x18008549f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854a4  test    eax, eax
0x1800854a6  jns     loc_180085538
0x1800854ac  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800854b3  jz      short loc_180085506
0x1800854b5  mov     r10, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800854bc  test    r10, r10
0x1800854bf  jz      short loc_1800854DC
0x1800854c1  mov     r9d, eax
0x1800854c4  mov     r8, rbx
0x1800854c7  lea     rdx, aCgpserviceVali_4; "CGPService::ValidateSYSVOL ConnectServe"...
0x1800854ce  lea     ecx, [r13+2]
0x1800854d2  mov     rax, r10
0x1800854d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854da  jmp     short loc_180085506
0x1800854dc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800854e3  jz      short loc_180085506
0x1800854e5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800854ec  jz      short loc_180085506
0x1800854ee  mov     r9d, eax
0x1800854f1  mov     r8, rbx
0x1800854f4  lea     rdx, aCgpserviceVali_4; "CGPService::ValidateSYSVOL ConnectServe"...
0x1800854fb  mov     ecx, 2; unsigned int
0x180085500  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180085505  nop
0x180085506  test    edi, edi
0x180085508  js      short loc_180085511
0x18008550a  call    cs:__imp_CoUninitialize
0x180085510  nop
0x180085511  lea     rcx, [rbp+57h+pProxy]
0x180085515  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18008551a  nop
0x18008551b  lea     rcx, [rbp+57h+var_A8]
0x18008551f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180085524  nop
0x180085525  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180085529  call    cs:__imp_SysFreeString
0x18008552f  nop
0x180085530  mov     rcx, rbx
0x180085533  jmp     loc_180085C15
0x180085538  mov     [rsp+100h+dwCapabilities], r13d; dwCapabilities
0x18008553d  mov     [rsp+100h+pAuthInfo], r13; pAuthInfo
0x180085542  mov     eax, 3
0x180085547  mov     [rsp+100h+dwImpLevel], eax; dwImpLevel
0x18008554b  mov     dword ptr [rsp+100h+ppv], eax; dwAuthnLevel
0x18008554f  xor     r9d, r9d; pServerPrincName
0x180085552  xor     r8d, r8d; dwAuthzSvc
0x180085555  lea     edx, [rax+7]; dwAuthnSvc
0x180085558  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18008555c  call    cs:__imp_CoSetProxyBlanket
0x180085562  mov     edx, 80000000h
0x180085567  lea     ecx, [rax+rdx]
0x18008556a  test    edx, ecx
0x18008556c  jnz     short loc_1800855D9
0x18008556e  cmp     eax, 80004002h
0x180085573  jz      short loc_1800855D9
0x180085575  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008557c  jz      short loc_180085506
0x18008557e  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180085585  test    r9, r9
0x180085588  jz      short loc_1800855A6
0x18008558a  mov     r8d, eax
0x18008558d  lea     rdx, aCgpserviceVali_1; "CGPService::ValidateSYSVOL CoSetProxyBl"...
0x180085594  mov     ecx, 2
0x180085599  mov     rax, r9
0x18008559c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855a1  jmp     loc_180085506
0x1800855a6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800855ad  jz      loc_180085506
0x1800855b3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800855ba  jz      loc_180085506
0x1800855c0  mov     r8d, eax
0x1800855c3  lea     rdx, aCgpserviceVali_1; "CGPService::ValidateSYSVOL CoSetProxyBl"...
0x1800855ca  mov     ecx, 2; unsigned int
0x1800855cf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800855d4  jmp     loc_180085506
0x1800855d9  mov     [rbp+57h+var_88], r13
0x1800855dd  mov     rcx, [rbp+57h+pProxy]
0x1800855e1  mov     rax, [rcx]
0x1800855e4  lea     rdx, [rbp+57h+var_88]
0x1800855e8  mov     qword ptr [rsp+100h+dwImpLevel], rdx
0x1800855ed  mov     [rsp+100h+ppv], r13
0x1800855f2  mov     r9d, 20h ; ' '
0x1800855f8  mov     r8, [rbp+57h+bstrString]
0x1800855fc  mov     rdx, [rbp+57h+var_98]
0x180085600  mov     rax, [rax+0A0h]
0x180085607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008560c  test    eax, eax
0x18008560e  jns     short loc_180085678
0x180085610  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180085617  jz      loc_180085B26
0x18008561d  mov     r9, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180085624  test    r9, r9
0x180085627  jz      short loc_180085645
0x180085629  mov     r8d, eax
0x18008562c  lea     rdx, aCgpserviceVali_5; "CGPService::ValidateSYSVOL ExecQuery(sp"...
0x180085633  mov     ecx, 2
0x180085638  mov     rax, r9
0x18008563b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085640  jmp     loc_180085B26
0x180085645  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008564c  jz      loc_180085B26
0x180085652  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180085659  jz      loc_180085B26
0x18008565f  mov     r8d, eax
0x180085662  lea     rdx, aCgpserviceVali_5; "CGPService::ValidateSYSVOL ExecQuery(sp"...
0x180085669  mov     ecx, 2; unsigned int
0x18008566e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180085673  jmp     loc_180085B26
0x180085678  mov     r12d, r13d
0x18008567b  test    r12d, r12d
0x18008567e  jnz     loc_180085B26
0x180085684  mov     [rbp+57h+var_90], r13
0x180085688  mov     dword ptr [rbp+57h+arg_0], r13d
0x18008568c  mov     rcx, [rbp+57h+var_88]
0x180085690  mov     rax, [rcx]
0x180085693  lea     rdx, [rbp+57h+arg_0]
0x180085697  mov     [rsp+100h+ppv], rdx
0x18008569c  lea     r9, [rbp+57h+var_90]
0x1800856a0  lea     r8d, [r12+1]
0x1800856a5  or      edx, 0FFFFFFFFh
0x1800856a8  mov     rax, [rax+20h]
0x1800856ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856b1  mov     r8d, eax
0x1800856b4  test    eax, eax
0x1800856b6  js      loc_180085B4E
0x1800856bc  cmp     dword ptr [rbp+57h+arg_0], r13d
0x1800856c0  jz      loc_180085B1C
0x1800856c6  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800856cd  jz      short loc_180085711
0x1800856cf  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800856d6  test    rax, rax
0x1800856d9  jz      short loc_1800856EE
0x1800856db  lea     rdx, aCgpserviceVali_6; "CGPService::ValidateSYSVOL The SYSVOL G"...
0x1800856e2  lea     ecx, [r12+4]
0x1800856e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856ec  jmp     short loc_180085711
0x1800856ee  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800856f5  jz      short loc_180085711
0x1800856f7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800856fe  jz      short loc_180085711
0x180085700  lea     rdx, aCgpserviceVali_6; "CGPService::ValidateSYSVOL The SYSVOL G"...
0x180085707  mov     ecx, 4; unsigned int
0x18008570c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180085711  xorps   xmm0, xmm0
0x180085714  xor     eax, eax
0x180085716  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18008571a  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18008571e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180085722  call    cs:__imp_VariantInit
0x180085728  lea     rax, [rbp+57h+pvarg]
0x18008572c  mov     [rbp+57h+var_68], rax
0x180085730  lea     rdx, aReplicationgro; "ReplicationGroupGuid"
0x180085737  lea     rcx, [rbp+57h+var_80]; this
0x18008573b  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x180085740  nop
0x180085741  mov     rcx, [rbp+57h+var_90]
0x180085745  mov     rax, [rcx]
0x180085748  mov     qword ptr [rsp+100h+dwImpLevel], r13
0x18008574d  mov     [rsp+100h+ppv], r13
0x180085752  lea     r9, [rbp+57h+pvarg]
0x180085756  xor     r8d, r8d
0x180085759  mov     rdx, [rbp+57h+var_80]
0x18008575d  mov     rax, [rax+20h]
0x180085761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085766  mov     r12d, eax
0x180085769  mov     [rbp+57h+arg_18], eax
0x18008576c  test    eax, eax
0x18008576e  js      loc_180085A0B
0x180085774  cmp     word ptr [rbp+57h+pvarg], 8
0x180085779  jnz     loc_180085A0B
0x18008577f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180085786  jz      short loc_1800857C4
0x180085788  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008578f  test    rax, rax
0x180085792  jz      short loc_1800857A4
0x180085794  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x180085798  mov     ecx, 4
0x18008579d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800857a2  jmp     short loc_1800857C4
0x1800857a4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800857ab  jz      short loc_1800857C4
0x1800857ad  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800857b4  jz      short loc_1800857C4
0x1800857b6  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x1800857ba  mov     ecx, 4; unsigned int
0x1800857bf  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800857c4  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 *
0x1800857c8  call    ?GetLastReplicationIssue@CGPService@@AEAAPEAGPEBG@Z; CGPService::GetLastReplicationIssue(ushort const *)
0x1800857cd  mov     rdx, rax; unsigned __int16 *
0x1800857d0  lea     rcx, [rbp+57h+Str]; this
0x1800857d4  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800857d9  nop
0x1800857da  mov     r12, [rbp+57h+Str]
0x1800857de  test    r12, r12
0x1800857e1  jz      loc_180085B4A
0x1800857e7  lea     rdx, aPolicies; "\\Policies\\{"
0x1800857ee  mov     rcx, r12; Str
0x1800857f1  call    cs:__imp_wcsstr
0x1800857f7  test    rax, rax
0x1800857fa  jz      loc_180085B34
0x180085800  mov     rcx, r12; unsigned __int16 *
0x180085803  call    ?GetGpoPath@@YAPEAGPEBG@Z; GetGpoPath(ushort const *)
0x180085808  mov     [rbp+57h+lpString1], rax
0x18008580c  test    rax, rax
0x18008580f  jz      loc_180085AB1
0x180085815  mov     [rbp+57h+bufptr], r13
0x180085819  mov     [rbp+57h+entriesread], r13d
0x18008581d  mov     [rbp+57h+totalentries], r13d
0x180085821  mov     [rsp+100h+resume_handle], r13; resume_handle
0x180085826  lea     rax, [rbp+57h+totalentries]
0x18008582a  mov     qword ptr [rsp+100h+dwCapabilities], rax; totalentries
0x18008582f  lea     rax, [rbp+57h+entriesread]
0x180085833  mov     [rsp+100h+pAuthInfo], rax; entriesread
0x180085838  mov     [rsp+100h+dwImpLevel], 0FFFFFFFFh; prefmaxlen
0x180085840  lea     rax, [rbp+57h+bufptr]
0x180085844  mov     [rsp+100h+ppv], rax; bufptr
0x180085849  mov     r9d, 3; level
0x18008584f  xor     r8d, r8d; username
0x180085852  xor     edx, edx; basepath
0x180085854  xor     ecx, ecx; servername
0x180085856  call    cs:__imp_NetFileEnum
0x18008585c  mov     r8d, eax
0x18008585f  test    eax, eax
0x180085861  jnz     loc_180085A56
0x180085867  cmp     r13d, [rbp+57h+entriesread]
0x18008586b  jnb     loc_1800859EB
0x180085871  mov     eax, r13d
0x180085874  shl     rax, 5
0x180085878  mov     [rbp+57h+var_28], rax
0x18008587c  mov     rcx, [rbp+57h+bufptr]
0x180085880  mov     rcx, [rax+rcx+10h]; unsigned __int16 *
0x180085885  call    ?GetGpoPath@@YAPEAGPEBG@Z; GetGpoPath(ushort const *)
0x18008588a  mov     [rbp+57h+var_78], rax
0x18008588e  xor     ecx, ecx
0x180085890  test    rax, rax
0x180085893  jz      loc_180085924
0x180085899  mov     [rsp+100h+resume_handle], rcx; lParam
0x18008589e  mov     qword ptr [rsp+100h+dwCapabilities], rcx; lpReserved
0x1800858a3  mov     [rsp+100h+pAuthInfo], rcx; lpVersionInformation
0x1800858a8  or      ecx, 0FFFFFFFFh
0x1800858ab  mov     [rsp+100h+dwImpLevel], ecx; cchCount2
0x1800858af  mov     [rsp+100h+ppv], rax; lpString2
0x1800858b4  mov     r9d, ecx; cchCount1
0x1800858b7  mov     r8, [rbp+57h+lpString1]; lpString1
0x1800858bb  lea     edx, [rcx+2]; dwCmpFlags
0x1800858be  lea     rcx, DomainName; lpLocaleName
0x1800858c5  call    cs:__imp_CompareStringEx
0x1800858cb  xor     ecx, ecx; servername
  ... truncated ...
```
