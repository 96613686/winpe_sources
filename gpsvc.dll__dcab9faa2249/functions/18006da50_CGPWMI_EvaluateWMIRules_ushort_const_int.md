# CGPWMI::EvaluateWMIRules(ushort const *,int *)

- ea: `0x18006da50`
- end: `0x18006e286`
- name: `?EvaluateWMIRules@CGPWMI@@SAKPEBGPEAH@Z`
- size: `2102`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005e4c`

## callees

- `0x18000a504`
- `0x180044630`
- `0x18006d3c8`
- `0x18006da24`
- `0x18006da50`
- `0x18006e35c`
- `0x180075ec0`
- `0x18007df28`
- `0x1800a43b0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18006db2a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18006db2a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006daa0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006db91`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006db9d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006dba9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006daa0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006db91`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006db9d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18006dba9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006dc5d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006dc5d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006dc95`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006dc95`

## string_xrefs

- `0x18006dcbb`: `CGPWMI::GetWMILocator: failed to create IWbemLocator with error: %d`
- `0x18006dce1`: `CGPWMI::GetWMILocator: failed to create IWbemLocator with error: %d`
- `0x18006df79`: `CGPWMI::ExecWMIQuery: failed to move Next with error: %d`
- `0x18006df9f`: `CGPWMI::ExecWMIQuery: failed to move Next with error: %d`
- `0x18006dd9e`: `CGPWMI::WMIEvaluate: failed to get WMI services with error: %d`
- `0x18006ddc3`: `CGPWMI::WMIEvaluate: failed to get WMI services with error: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CGPWMI::EvaluateWMIRules(const unsigned __int16 *a1, int *a2)
{
  wchar_t *v3; // rdi
  unsigned int WMIServices; // esi
  void (*v5)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rdx
  int v8; // r15d
  int v9; // eax
  int i; // r13d
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  const unsigned __int16 *v13; // rbx
  __int64 v14; // rdi
  const unsigned __int16 *v15; // rbx
  __int64 v16; // rdi
  struct IWbemLocator *v17; // rbx
  __int64 v18; // r9
  PCNZWCH v19; // r12
  int v20; // eax
  unsigned __int16 *v21; // rdi
  HRESULT v22; // eax
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v24; // rdx
  struct IWbemServices *v25; // rbx
  __int64 v26; // rsi
  int v27; // r13d
  HRESULT (__stdcall *ExecQuery)(IWbemServices *, const BSTR, const BSTR, int, IWbemContext *, IEnumWbemClassObject **); // r12
  _bstr_t *v29; // rax
  _bstr_t *v30; // rax
  __int64 v31; // rdx
  int v32; // ebx
  int v33; // eax
  unsigned __int16 v34; // bx
  int v35; // eax
  PCNZWCH lpString1; // [rsp+40h] [rbp-59h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-51h] BYREF
  int v39; // [rsp+50h] [rbp-49h] BYREF
  int v40; // [rsp+54h] [rbp-45h] BYREF
  unsigned __int16 *v41; // [rsp+58h] [rbp-41h] BYREF
  int v42; // [rsp+60h] [rbp-39h]
  struct IWbemServices *v43; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v44; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v45; // [rsp+78h] [rbp-21h] BYREF
  void *v46; // [rsp+80h] [rbp-19h] BYREF
  struct IWbemLocator *v47; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v48[8]; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v49[8]; // [rsp+98h] [rbp-1h] BYREF
  const unsigned __int16 *v50; // [rsp+A0h] [rbp+7h]
  __int64 v51; // [rsp+A8h] [rbp+Fh]
  int v52; // [rsp+100h] [rbp+67h]
  int v54; // [rsp+110h] [rbp+77h] BYREF
  int v55; // [rsp+118h] [rbp+7Fh] BYREF

  v45 = 0;
  v41 = 0;
  v44 = 0;
  lpString1 = 0;
  if ( !a1 || !a2 )
  {
    WMIServices = 87;
    goto LABEL_126;
  }
  *a2 = 0;
  v3 = wcschr(a1, 0x3Bu);
  WMIServices = CopySubString(a1, v3 - a1, &v45);
  if ( WMIServices )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v5 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v6 = L"CGPWMI::EvaluateWMIRules: failed to get szElts.";
LABEL_7:
        v5(2u, v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v7 = L"CGPWMI::EvaluateWMIRules: failed to get szElts.";
LABEL_11:
        RedirectDebugMsg(2u, v7);
      }
    }
    goto LABEL_126;
  }
  v8 = 0;
  v9 = _o__wtoi(v45);
  v42 = v9;
  for ( i = 0; ; ++i )
  {
    v52 = i;
    if ( !v3 || i >= v9 )
      goto LABEL_124;
    v54 = 0;
    v55 = 0;
    v39 = 0;
    if ( swscanf_s(v3 + 1, L"%d;%d;%d;", &v54, &v55, &v39) != 3 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong format.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong format.");
        }
      }
      goto LABEL_124;
    }
    v11 = wcschr(v3 + 1, 0x3Bu);
    v12 = wcschr(v11 + 1, 0x3Bu);
    v13 = wcschr(v12 + 1, 0x3Bu) + 1;
    v14 = v54;
    WMIServices = CopySubString(v13, v54, &v41);
    if ( WMIServices )
      break;
    v15 = &v13[v14 + 1];
    v16 = v55;
    WMIServices = CopySubString(v15, v55, &v44);
    if ( WMIServices )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_126;
      v5 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v6 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong namespace format.";
        goto LABEL_7;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v7 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong namespace format.";
        goto LABEL_11;
      }
      goto LABEL_126;
    }
    v50 = &v15[v16 + 1];
    v51 = v39;
    WMIServices = CopySubString(v50, v39, (unsigned __int16 **)&lpString1);
    if ( WMIServices )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_126;
      v5 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v6 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong query format.";
        goto LABEL_7;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v7 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong query format.";
        goto LABEL_11;
      }
      goto LABEL_126;
    }
    v17 = 0;
    v47 = 0;
    v43 = 0;
    v18 = -1;
    v19 = lpString1;
    WMIServices = 0;
    do
      ++v18;
    while ( lpString1[v18] );
    v20 = CompareStringW(0x7Fu, 1u, lpString1, v18, L"NULL", 4);
    v21 = v44;
    if ( v20 == 2 )
    {
      v8 = 0;
      goto LABEL_82;
    }
    ppv = 0;
    v22 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
    if ( v22 >= 0 )
    {
      WMIServices = 0;
      v17 = (struct IWbemLocator *)ppv;
      ppv = 0;
      v47 = v17;
    }
    else
    {
      WMIServices = (unsigned __int16)v22;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"CGPWMI::GetWMILocator: failed to create IWbemLocator with error: %d",
            (unsigned __int16)v22);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"CGPWMI::GetWMILocator: failed to create IWbemLocator with error: %d",
            (unsigned __int16)v22);
        }
      }
    }
    XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>(&ppv);
    if ( WMIServices )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_82;
      v23 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v24 = L"CGPWMI::WMIEvaluate: failed to get WMI locator with error: %d";
LABEL_35:
        v23(2u, v24, WMIServices);
        goto LABEL_82;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(2u, L"CGPWMI::WMIEvaluate: failed to get WMI locator with error: %d", WMIServices);
    }
    else
    {
      WMIServices = CGPWMI::GetWMIServices(v17, v21, &v43);
      if ( WMIServices )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          v23 = g_lpDebugMsg;
          if ( g_lpDebugMsg )
          {
            v24 = L"CGPWMI::WMIEvaluate: failed to get WMI services with error: %d";
            goto LABEL_35;
          }
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"CGPWMI::WMIEvaluate: failed to get WMI services with error: %d", WMIServices);
        }
      }
      else
      {
        v25 = v43;
        v26 = 0;
        ppv = 0;
        v46 = 0;
        v27 = 0;
        if ( v43 )
        {
          v40 = 0;
          ExecQuery = v43->lpVtbl->ExecQuery;
          v29 = _bstr_t::_bstr_t((_bstr_t *)v49, lpString1);
          if ( *(_QWORD *)v29 )
            v26 = **(_QWORD **)v29;
          v30 = _bstr_t::_bstr_t((_bstr_t *)v48, v41);
          if ( *(_QWORD *)v30 )
            v31 = **(_QWORD **)v30;
          else
            v31 = 0;
          v32 = ((__int64 (__fastcall *)(struct IWbemServices *, __int64, __int64, __int64, _QWORD, LPVOID *))ExecQuery)(
                  v25,
                  v31,
                  v26,
                  48,
                  0,
                  &ppv);
          _bstr_t::_Free((_bstr_t *)v48);
          _bstr_t::_Free((_bstr_t *)v49);
          if ( v32 >= 0 )
          {
            v33 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, void **, int *))(*(_QWORD *)ppv + 32LL))(
                    ppv,
                    30000,
                    1,
                    &v46,
                    &v40);
            v34 = v33;
            if ( v33 >= 0 && v40 )
            {
              WMIServices = 0;
              v27 = 1;
            }
            else
            {
              if ( v33 == 1 )
              {
                v34 = 0;
              }
              else if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"CGPWMI::ExecWMIQuery: failed to move Next with error: %d", 0);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"CGPWMI::ExecWMIQuery: failed to move Next with error: %d", 0);
                }
              }
              WMIServices = v34;
            }
          }
          else
          {
            WMIServices = (unsigned __int16)v32;
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"CGPWMI::ExecWMIQuery: failed to execute query with error: %d", (unsigned __int16)v32);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  2u,
                  L"CGPWMI::ExecWMIQuery: failed to execute query with error: %d",
                  (unsigned __int16)v32);
              }
            }
          }
          v19 = lpString1;
        }
        else
        {
          WMIServices = 87;
        }
        XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>(&v46);
        XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>(&ppv);
        if ( WMIServices )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CGPWMI::WMIEvaluate: failed to execuate WMI query with error: %d", WMIServices);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CGPWMI::WMIEvaluate: failed to execuate WMI query with error: %d", WMIServices);
            }
          }
        }
        else
        {
          v8 = v27;
        }
        i = v52;
      }
    }
LABEL_82:
    v35 = 0;
    if ( !WMIServices )
      v35 = v8;
    v8 = v35;
    XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>((void **)&v43);
    XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&private: static void * CGPWMI::WbemServicesFree(void *)>((void **)&v47);
    if ( WMIServices )
    {
      if ( v8 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"CGPWMI::EvaluateWMIRules: Failed to Evaluate with error %d, NameSpace:%s, Language:%s, Query:%s.",
              WMIServices,
              v21,
              v41,
              v19);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"CGPWMI::EvaluateWMIRules: Failed to Evaluate with error %d, NameSpace:%s, Language:%s, Query:%s.",
              WMIServices,
              v21,
              v41,
              v19);
          }
        }
      }
      else
      {
LABEL_88:
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"CGPWMI::EvaluateWMIRules: not FilterAllowed for query: %s", v19);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"CGPWMI::EvaluateWMIRules: not FilterAllowed for query: %s", v19);
          }
        }
      }
LABEL_124:
      *a2 = v8;
      goto LABEL_126;
    }
    if ( !v8 )
      goto LABEL_88;
    v3 = (wchar_t *)&v50[v51];
    v9 = v42;
  }
  if ( !*(_DWORD *)&g_dwDebugLevel )
    goto LABEL_126;
  v5 = g_lpDebugMsg;
  if ( g_lpDebugMsg )
  {
    v6 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong Language format.";
    goto LABEL_7;
  }
  if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
  {
    v7 = L"CGPWMI::EvaluateWMIRules: szWMIRules has wrong Language format.";
    goto LABEL_11;
  }
LABEL_126:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&lpString1);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v44);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v41);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v45);
  return WMIServices;
}

```

## disassembly

```asm
0x18006da50  mov     [rsp-8+arg_8], rdx
0x18006da55  push    rbp
0x18006da56  push    rbx
0x18006da57  push    rsi
0x18006da58  push    rdi
0x18006da59  push    r12
0x18006da5b  push    r13
0x18006da5d  push    r14
0x18006da5f  push    r15
0x18006da61  lea     rbp, [rsp-1Fh]
0x18006da66  sub     rsp, 0B8h
0x18006da6d  mov     rax, rdx
0x18006da70  mov     rbx, rcx
0x18006da73  xor     r12d, r12d
0x18006da76  mov     [rbp+57h+var_78], r12
0x18006da7a  mov     [rbp+57h+var_98], r12
0x18006da7e  mov     [rbp+57h+var_80], r12
0x18006da82  mov     [rbp+57h+lpString1], r12
0x18006da86  test    rcx, rcx
0x18006da89  jz      loc_18006E244
0x18006da8f  test    rax, rax
0x18006da92  jz      loc_18006E244
0x18006da98  mov     [rdx], r12d
0x18006da9b  lea     edx, [r12+3Bh]; Ch
0x18006daa0  call    cs:__imp_wcschr
0x18006daa6  mov     rdi, rax
0x18006daa9  mov     rdx, rax
0x18006daac  sub     rdx, rbx
0x18006daaf  sar     rdx, 1; int
0x18006dab2  lea     r8, [rbp+57h+var_78]; unsigned __int16 **
0x18006dab6  mov     rcx, rbx; unsigned __int16 *
0x18006dab9  call    ?CopySubString@@YAKPEBGHPEAPEAG@Z; CopySubString(ushort const *,int,ushort * *)
0x18006dabe  mov     esi, eax
0x18006dac0  test    eax, eax
0x18006dac2  jz      short loc_18006DB23
0x18006dac4  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006dacb  jz      loc_18006E249
0x18006dad1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006dad8  test    rax, rax
0x18006dadb  jz      short loc_18006DAF3
0x18006dadd  lea     rdx, aCgpwmiEvaluate_0; "CGPWMI::EvaluateWMIRules: failed to get"...
0x18006dae4  lea     ecx, [r12+2]
0x18006dae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006daee  jmp     loc_18006E249
0x18006daf3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006dafa  jz      loc_18006E249
0x18006db00  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006db07  jz      loc_18006E249
0x18006db0d  lea     rdx, aCgpwmiEvaluate_0; "CGPWMI::EvaluateWMIRules: failed to get"...
0x18006db14  mov     ecx, 2; unsigned int
0x18006db19  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006db1e  jmp     loc_18006E249
0x18006db23  mov     r15d, r12d
0x18006db26  mov     rcx, [rbp+57h+var_78]
0x18006db2a  call    cs:__imp__o__wtoi
0x18006db30  mov     [rbp+57h+var_90], eax
0x18006db33  mov     r13d, r12d
0x18006db36  mov     r14d, 2
0x18006db3c  mov     [rbp+57h+arg_0], r13d
0x18006db40  test    rdi, rdi
0x18006db43  jz      loc_18006E23B
0x18006db49  cmp     r13d, eax
0x18006db4c  jge     loc_18006E23B
0x18006db52  mov     [rbp+57h+arg_10], r12d
0x18006db56  mov     [rbp+57h+arg_18], r12d
0x18006db5a  mov     [rbp+57h+var_A0], r12d
0x18006db5e  lea     rax, [rbp+57h+var_A0]
0x18006db62  mov     [rsp+0F0h+lpString2], rax
0x18006db67  lea     r9, [rbp+57h+arg_18]
0x18006db6b  lea     r8, [rbp+57h+arg_10]
0x18006db6f  lea     rdx, aDDD; "%d;%d;%d;"
0x18006db76  lea     rcx, [rdi+2]; Buffer
0x18006db7a  call    swscanf_s
0x18006db7f  cmp     eax, 3
0x18006db82  jnz     loc_18006E1F4
0x18006db88  lea     ebx, [rax+38h]
0x18006db8b  mov     edx, ebx; Ch
0x18006db8d  lea     rcx, [rdi+2]; Str
0x18006db91  call    cs:__imp_wcschr
0x18006db97  mov     edx, ebx; Ch
0x18006db99  lea     rcx, [rax+2]; Str
0x18006db9d  call    cs:__imp_wcschr
0x18006dba3  mov     edx, ebx; Ch
0x18006dba5  lea     rcx, [rax+2]; Str
0x18006dba9  call    cs:__imp_wcschr
0x18006dbaf  lea     rbx, [rax+2]
0x18006dbb3  movsxd  rdx, [rbp+57h+arg_10]; int
0x18006dbb7  mov     rdi, rdx
0x18006dbba  lea     r8, [rbp+57h+var_98]; unsigned __int16 **
0x18006dbbe  mov     rcx, rbx; unsigned __int16 *
0x18006dbc1  call    ?CopySubString@@YAKPEBGHPEAPEAG@Z; CopySubString(ushort const *,int,ushort * *)
0x18006dbc6  mov     esi, eax
0x18006dbc8  test    eax, eax
0x18006dbca  jnz     loc_18006E1AB
0x18006dbd0  lea     rbx, [rbx+rdi*2]
0x18006dbd4  add     rbx, 2
0x18006dbd8  movsxd  rdx, [rbp+57h+arg_18]; int
0x18006dbdc  mov     rdi, rdx
0x18006dbdf  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x18006dbe3  mov     rcx, rbx; unsigned __int16 *
0x18006dbe6  call    ?CopySubString@@YAKPEBGHPEAPEAG@Z; CopySubString(ushort const *,int,ushort * *)
0x18006dbeb  mov     esi, eax
0x18006dbed  test    eax, eax
0x18006dbef  jnz     loc_18006E166
0x18006dbf5  lea     rax, [rdi+1]
0x18006dbf9  lea     rax, [rbx+rax*2]
0x18006dbfd  mov     [rbp+57h+var_50], rax
0x18006dc01  movsxd  rdx, [rbp+57h+var_A0]; int
0x18006dc05  mov     [rbp+57h+var_48], rdx
0x18006dc09  lea     r8, [rbp+57h+lpString1]; unsigned __int16 **
0x18006dc0d  mov     rcx, rax; unsigned __int16 *
0x18006dc10  call    ?CopySubString@@YAKPEBGHPEAPEAG@Z; CopySubString(ushort const *,int,ushort * *)
0x18006dc15  mov     esi, eax
0x18006dc17  test    eax, eax
0x18006dc19  jnz     loc_18006E11B
0x18006dc1f  mov     rbx, r12
0x18006dc22  mov     [rbp+57h+var_68], rbx
0x18006dc26  mov     [rbp+57h+var_88], r12
0x18006dc2a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18006dc2e  mov     r12, [rbp+57h+lpString1]
0x18006dc32  xor     esi, esi
0x18006dc34  inc     r9; cchCount1
0x18006dc37  cmp     [r12+r9*2], si
0x18006dc3c  jnz     short loc_18006DC34
0x18006dc3e  mov     [rsp+0F0h+cchCount2], 4; cchCount2
0x18006dc46  lea     rax, aNull_1; "NULL"
0x18006dc4d  mov     [rsp+0F0h+lpString2], rax; lpString2
0x18006dc52  mov     r8, r12; lpString1
0x18006dc55  mov     edx, 1; dwCmpFlags
0x18006dc5a  lea     ecx, [rdx+7Eh]; Locale
0x18006dc5d  call    cs:__imp_CompareStringW
0x18006dc63  mov     rdi, [rbp+57h+var_80]
0x18006dc67  cmp     eax, r14d
0x18006dc6a  jnz     short loc_18006DC74
0x18006dc6c  xor     r15d, r15d
0x18006dc6f  jmp     loc_18006DFED
0x18006dc74  mov     [rbp+57h+ppv], rsi
0x18006dc78  lea     rax, [rbp+57h+ppv]
0x18006dc7c  mov     [rsp+0F0h+lpString2], rax; ppv
0x18006dc81  lea     r9, IID_IWbemLocator; riid
0x18006dc88  xor     edx, edx; pUnkOuter
0x18006dc8a  lea     r8d, [rdx+1]; dwClsContext
0x18006dc8e  lea     rcx, CLSID_WbemLocator; rclsid
0x18006dc95  call    cs:__imp_CoCreateInstance
0x18006dc9b  xor     ecx, ecx
0x18006dc9d  test    eax, eax
0x18006dc9f  jns     short loc_18006DCF2
0x18006dca1  movzx   esi, ax
0x18006dca4  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18006dcaa  jz      short loc_18006DD00
0x18006dcac  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006dcb3  test    rax, rax
0x18006dcb6  jz      short loc_18006DCCC
0x18006dcb8  mov     r8d, esi
0x18006dcbb  lea     rdx, aCgpwmiGetwmilo; "CGPWMI::GetWMILocator: failed to create"...
0x18006dcc2  mov     ecx, r14d
0x18006dcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dcca  jmp     short loc_18006DD00
0x18006dccc  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x18006dcd3  jz      short loc_18006DD00
0x18006dcd5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006dcdc  jz      short loc_18006DD00
0x18006dcde  mov     r8d, esi
0x18006dce1  lea     rdx, aCgpwmiGetwmilo; "CGPWMI::GetWMILocator: failed to create"...
0x18006dce8  mov     ecx, r14d; unsigned int
0x18006dceb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006dcf0  jmp     short loc_18006DD00
0x18006dcf2  mov     esi, ecx
0x18006dcf4  mov     rbx, [rbp+57h+ppv]
0x18006dcf8  mov     [rbp+57h+ppv], rcx
0x18006dcfc  mov     [rbp+57h+var_68], rbx
0x18006dd00  lea     rcx, [rbp+57h+ppv]
0x18006dd04  call    ??1?$XPtr@UIWbemServices@@$1?WbemServicesFree@CGPWMI@@CAPEAXPEAX@Z@@QEAA@XZ; XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>(void)
0x18006dd09  test    esi, esi
0x18006dd0b  jz      short loc_18006DD70
0x18006dd0d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18006dd14  jz      loc_18006DFED
0x18006dd1a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006dd21  test    rax, rax
0x18006dd24  jz      short loc_18006DD3D
0x18006dd26  lea     rdx, aCgpwmiWmievalu_1; "CGPWMI::WMIEvaluate: failed to get WMI "...
0x18006dd2d  mov     r8d, esi
0x18006dd30  mov     ecx, r14d
0x18006dd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd38  jmp     loc_18006DFED
0x18006dd3d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18006dd45  jz      loc_18006DFED
0x18006dd4b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006dd53  jz      loc_18006DFED
0x18006dd59  lea     rdx, aCgpwmiWmievalu_1; "CGPWMI::WMIEvaluate: failed to get WMI "...
0x18006dd60  mov     r8d, esi
0x18006dd63  mov     ecx, r14d; unsigned int
0x18006dd66  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006dd6b  jmp     loc_18006DFED
0x18006dd70  lea     r8, [rbp+57h+var_88]; struct IWbemServices **
0x18006dd74  mov     rdx, rdi; unsigned __int16 *
0x18006dd77  mov     rcx, rbx; struct IWbemLocator *
0x18006dd7a  call    ?GetWMIServices@CGPWMI@@CAKPEAUIWbemLocator@@PEBGPEAPEAUIWbemServices@@@Z; CGPWMI::GetWMIServices(IWbemLocator *,ushort const *,IWbemServices * *)
0x18006dd7f  mov     esi, eax
0x18006dd81  test    eax, eax
0x18006dd83  jz      short loc_18006DDCC
0x18006dd85  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18006dd8c  jz      loc_18006DFED
0x18006dd92  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006dd99  test    rax, rax
0x18006dd9c  jz      short loc_18006DDA7
0x18006dd9e  lea     rdx, aCgpwmiWmievalu; "CGPWMI::WMIEvaluate: failed to get WMI "...
0x18006dda5  jmp     short loc_18006DD2D
0x18006dda7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18006ddaf  jz      loc_18006DFED
0x18006ddb5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006ddbd  jz      loc_18006DFED
0x18006ddc3  lea     rdx, aCgpwmiWmievalu; "CGPWMI::WMIEvaluate: failed to get WMI "...
0x18006ddca  jmp     short loc_18006DD60
0x18006ddcc  mov     rbx, [rbp+57h+var_88]
0x18006ddd0  xor     esi, esi
0x18006ddd2  mov     [rbp+57h+ppv], rsi
0x18006ddd6  mov     [rbp+57h+var_70], rsi
0x18006ddda  mov     r13d, esi
0x18006dddd  test    rbx, rbx
0x18006dde0  jz      loc_18006DFB6
0x18006dde6  mov     [rbp+57h+var_9C], esi
0x18006dde9  mov     rax, [rbx]
0x18006ddec  mov     r12, [rax+0A0h]
0x18006ddf3  mov     rdx, [rbp+57h+lpString1]; unsigned __int16 *
0x18006ddf7  lea     rcx, [rbp+57h+var_58]; this
0x18006ddfb  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006de00  nop
0x18006de01  mov     rcx, [rax]
0x18006de04  test    rcx, rcx
0x18006de07  jz      short loc_18006DE0C
0x18006de09  mov     rsi, [rcx]
0x18006de0c  mov     rdx, [rbp+57h+var_98]; unsigned __int16 *
0x18006de10  lea     rcx, [rbp+57h+var_60]; this
0x18006de14  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006de19  nop
0x18006de1a  mov     rcx, [rax]
0x18006de1d  xor     r8d, r8d
0x18006de20  test    rcx, rcx
0x18006de23  jz      short loc_18006DE2A
0x18006de25  mov     rdx, [rcx]
0x18006de28  jmp     short loc_18006DE2D
0x18006de2a  mov     rdx, r8
0x18006de2d  lea     rax, [rbp+57h+ppv]
0x18006de31  mov     qword ptr [rsp+0F0h+cchCount2], rax
0x18006de36  mov     [rsp+0F0h+lpString2], r8
0x18006de3b  mov     r9d, 30h ; '0'
0x18006de41  mov     r8, rsi
0x18006de44  mov     rcx, rbx
0x18006de47  mov     rax, r12
0x18006de4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de4f  mov     ebx, eax
0x18006de51  lea     rcx, [rbp+57h+var_60]; this
0x18006de55  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006de5a  nop
0x18006de5b  lea     rcx, [rbp+57h+var_58]; this
0x18006de5f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006de64  xor     r12d, r12d
0x18006de67  test    ebx, ebx
0x18006de69  jns     loc_18006DF15
0x18006de6f  movzx   esi, bx
0x18006de72  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18006de79  jz      short loc_18006DE99
0x18006de7b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006de82  test    rax, rax
0x18006de85  jz      short loc_18006DEEF
0x18006de87  mov     r8d, esi
0x18006de8a  lea     rdx, aCgpwmiExecwmiq; "CGPWMI::ExecWMIQuery: failed to execute"...
0x18006de91  mov     ecx, r14d
0x18006de94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de99  mov     r12, [rbp+57h+lpString1]
0x18006de9d  lea     rcx, [rbp+57h+var_70]
0x18006dea1  call    ??1?$XPtr@UIWbemServices@@$1?WbemServicesFree@CGPWMI@@CAPEAXPEAX@Z@@QEAA@XZ; XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>(void)
0x18006dea6  nop
0x18006dea7  lea     rcx, [rbp+57h+ppv]
0x18006deab  call    ??1?$XPtr@UIWbemServices@@$1?WbemServicesFree@CGPWMI@@CAPEAXPEAX@Z@@QEAA@XZ; XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>::~XPtr<IWbemServices,&CGPWMI::WbemServicesFree(void *)>(void)
0x18006deb0  test    esi, esi
0x18006deb2  jz      loc_18006DFE6
0x18006deb8  xor     r13d, r13d
0x18006debb  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18006dec2  jz      loc_18006DFE9
0x18006dec8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18006decf  test    rax, rax
0x18006ded2  jz      loc_18006DFC0
0x18006ded8  mov     r8d, esi
0x18006dedb  lea     rdx, aCgpwmiWmievalu_0; "CGPWMI::WMIEvaluate: failed to execuate"...
0x18006dee2  mov     ecx, r14d
0x18006dee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006deea  jmp     loc_18006DFE9
0x18006deef  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18006def6  jz      short loc_18006DE99
0x18006def8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18006deff  jz      short loc_18006DE99
0x18006df01  mov     r8d, esi
0x18006df04  lea     rdx, aCgpwmiExecwmiq; "CGPWMI::ExecWMIQuery: failed to execute"...
0x18006df0b  mov     ecx, r14d; unsigned int
0x18006df0e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18006df13  jmp     short loc_18006DE99
0x18006df15  mov     rcx, [rbp+57h+ppv]
0x18006df19  mov     rax, [rcx]
  ... truncated ...
```
