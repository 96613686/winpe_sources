# EnumerateUserNameSpace(IWbemLocator *,void *,tagSAFEARRAY * *)

- ea: `0x1800ae920`
- end: `0x1800af3ba`
- name: `?EnumerateUserNameSpace@@YAJPEAUIWbemLocator@@PEAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `2714`
- prototype: `__int64 __fastcall(struct IWbemLocator *, void *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x18000a504`
- `0x18001ee6c`
- `0x1800535a0`
- `0x180056168`
- `0x1800585e8`
- `0x180063da4`
- `0x18006b5f0`
- `0x1800709d4`
- `0x180072a08`
- `0x180075ec0`
- `0x1800ae920`
- `0x1800af3c0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af024`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af1f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aece0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aef99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aece0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800aef99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aede1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af342`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af34f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aede1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aeded`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af342`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af34f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800aed82`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800aed82`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800aee35`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800aee35`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800aedf3`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800aedf3`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800aeea1`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800aef3c`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800aeea1`
- `api-ms-win-core-com-l1-1-0!CoSwitchCallContext` at `0x1800aef3c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aeacc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aeae0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aebe9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aebf4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aec08`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af251`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af2c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af370`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af37b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af38f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aeacc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aeae0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aebe9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aebf4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800aec08`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af251`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af2c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af370`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af37b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800af38f`
- `OLEAUT32!__imp_VariantInit` at `0x1800aec80`
- `OLEAUT32!__imp_VariantInit` at `0x1800aec80`
- `OLEAUT32!__imp_VariantClear` at `0x1800aefc5`
- `OLEAUT32!__imp_VariantClear` at `0x1800aefc5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800af19a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800af19a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800af241`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800af241`

## string_xrefs

- `0x1800af070`: `ExecAsyncMethod::CoImpersonateClient failed with 0x%x`
- `0x1800aeb3b`: `EnumerateUserNameSpace: CreateInstanceEnum failed. hr=0x%x`
- `0x1800aeb6e`: `EnumerateUserNameSpace: CreateInstanceEnum failed. hr=0x%x`
- `0x1800aed34`: `EnumerateUserNameSpace: AllocateAndInitSidFromString - %s is not a valid Sid`
- `0x1800aed5b`: `EnumerateUserNameSpace: AllocateAndInitSidFromString - %s is not a valid Sid`
- `0x1800aeda4`: `EnumerateUserNameSpace: %s is not a valid Sid`
- `0x1800aedcc`: `EnumerateUserNameSpace: %s is not a valid Sid`
- `0x1800aee63`: `EnumerateUserNameSpace: OpenNamespace returned 0x%x`
- `0x1800aee8a`: `EnumerateUserNameSpace: OpenNamespace returned 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall EnumerateUserNameSpace(struct IWbemLocator *a1, void *a2, struct tagSAFEARRAY **a3)
{
  OLECHAR *v4; // rdi
  OLECHAR *v5; // rcx
  unsigned int v6; // r15d
  const unsigned __int16 **v7; // r13
  ULONG v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // r15
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rbx
  HRESULT v14; // eax
  int v15; // r13d
  HRESULT v16; // eax
  unsigned __int16 *SOMFromSID; // rax
  int v18; // r9d
  DWORD v19; // eax
  int v20; // eax
  HRESULT v21; // eax
  const unsigned __int16 **v22; // rax
  void (*v23)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v24; // eax
  DWORD v25; // eax
  signed int LastError; // eax
  SAFEARRAY *v27; // rax
  SAFEARRAY **v28; // r15
  void (*v29)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v30; // eax
  DWORD v31; // eax
  unsigned int v32; // eax
  OLECHAR *v33; // rbx
  HLOCAL *v34; // rbx
  HLOCAL *v35; // rcx
  LONG rgIndices; // [rsp+58h] [rbp-69h] BYREF
  const unsigned __int16 *v38; // [rsp+60h] [rbp-61h] BYREF
  int v39; // [rsp+68h] [rbp-59h] BYREF
  __int64 v40; // [rsp+70h] [rbp-51h] BYREF
  __int64 v41; // [rsp+78h] [rbp-49h] BYREF
  BSTR v42; // [rsp+80h] [rbp-41h] BYREF
  PSID pSid; // [rsp+88h] [rbp-39h] BYREF
  void *v44; // [rsp+90h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-29h]
  __int64 v46; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-19h] BYREF
  int v48; // [rsp+B0h] [rbp-11h] BYREF
  BSTR v49; // [rsp+B8h] [rbp-9h] BYREF
  BSTR v50; // [rsp+C0h] [rbp-1h] BYREF
  IUnknown *ppOldObject; // [rsp+C8h] [rbp+7h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+D0h] [rbp+Fh] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp+17h] BYREF
  BSTR bstrString[5]; // [rsp+F0h] [rbp+2Fh] BYREF
  int v55; // [rsp+130h] [rbp+6Fh]
  unsigned int v57; // [rsp+140h] [rbp+7Fh]

  v55 = (int)a2;
  v48 = 0;
  ppOldObject = 0;
  *a3 = 0;
  v47 = 0;
  XBStr::XBStr((XBStr *)bstrString, L"\\\\.\\Root\\Rsop\\User");
  v4 = bstrString[0];
  if ( !bstrString[0] )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(LODWORD(bstrString[0]) + 2, L"EnumerateUserNameSpace: Failed to allocate memory.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory.");
      }
    }
    v5 = 0;
LABEL_24:
    SysFreeString(v5);
    v6 = -2147024882;
    goto LABEL_144;
  }
  v6 = ((__int64 (__fastcall *)(struct IWbemLocator *, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, __int64 *))a1->lpVtbl->ConnectServer)(
         a1,
         bstrString[0],
         0,
         0,
         0,
         0,
         0,
         0,
         &v47);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"EnumerateUserNameSpace: ConnectServer failed. hr=0x%x", v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: ConnectServer failed. hr=0x%x", v6);
      }
    }
    goto LABEL_143;
  }
  v40 = 0;
  XBStr::XBStr((XBStr *)&v42, L"__namespace");
  if ( !v42 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory.");
      }
    }
    SysFreeString(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    v5 = v4;
    goto LABEL_24;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64))(*(_QWORD *)v47 + 144LL))(v47, v42, 33);
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"EnumerateUserNameSpace: CreateInstanceEnum failed. hr=0x%x", v6);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: CreateInstanceEnum failed. hr=0x%x", v6);
      }
    }
    goto LABEL_142;
  }
  XBStr::XBStr((XBStr *)&v49, L"Name");
  if ( !v49 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory");
      }
    }
    SysFreeString(0);
    SysFreeString(v42);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    SysFreeString(v4);
    v6 = -2147467259;
    goto LABEL_144;
  }
  v7 = 0;
  hMem = 0;
  v8 = 0;
  v57 = 0;
  v46 = 0;
  v39 = 1;
  while ( 1 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, int *))(*(_QWORD *)v40 + 32LL))(
           v40,
           0,
           1,
           &v46,
           &v39);
    if ( v9 )
      break;
    if ( !v39 )
      goto LABEL_129;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
           v46,
           v49,
           0,
           &pvarg,
           0,
           0);
    XInterface<IWbemServices>::operator=(&v46);
    if ( (v6 & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EnumerateUserNameSpace: Get failed. hr=0x%x", v6);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EnumerateUserNameSpace: Get failed. hr=0x%x", v6);
        }
      }
      goto LABEL_136;
    }
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(pvarg.llVal + 2 * v10) );
    v11 = v10 + 1;
    v12 = (const unsigned __int16 *)LocalAlloc(0x40u, 2 * (v10 + 1));
    v13 = v12;
    v38 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EnumerateUserNameSpace: AllocMem failed. hr=0x%x", v6);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EnumerateUserNameSpace: AllocMem failed. hr=0x%x", v6);
        }
      }
      goto LABEL_100;
    }
    ConvertWMINameToSid(pvarg.llVal, v11, v12);
    pSid = 0;
    if ( AllocateAndInitSidFromString(v13, &pSid) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EnumerateUserNameSpace: AllocateAndInitSidFromString - %s is not a valid Sid", v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EnumerateUserNameSpace: AllocateAndInitSidFromString - %s is not a valid Sid", v13);
        }
      }
      goto LABEL_54;
    }
    if ( IsValidSid(pSid) )
    {
      LocalFree(pSid);
      v14 = CoImpersonateClient();
      v6 = v14;
      if ( v14 < 0 )
      {
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgRsop,
          2u,
          L"ExecAsyncMethod::CoImpersonateClient failed with 0x%x",
          (unsigned int)v14);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v38);
        goto LABEL_136;
      }
      v41 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, LONGLONG, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v47 + 24LL))(
             v47,
             pvarg.llVal,
             0,
             0,
             &v41,
             0);
      CoRevertToSelf();
      if ( (v6 & 0x80000000) == 0 )
      {
LABEL_81:
        v22 = (const unsigned __int16 **)LocalAlloc(0x40u, 0x10u);
        if ( !v22 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            v23 = g_lpDebugMsg;
            if ( g_lpDebugMsg )
            {
              v24 = GetLastError();
              v23(2u, L"EnumerateUserNameSpace: Couldn't allocate memory Error = %d", v24);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              v25 = GetLastError();
              RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Couldn't allocate memory Error = %d", v25);
            }
          }
          goto LABEL_84;
        }
        v38 = 0;
        *v22 = v13;
        v22[1] = (const unsigned __int16 *)v7;
        v7 = v22;
        hMem = v22;
        v8 = ++v57;
        VariantClear(&pvarg);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v38);
      }
      else
      {
        v15 = 0;
        v50 = 0;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"EnumerateUserNameSpace: OpenNamespace returned 0x%x", v6);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"EnumerateUserNameSpace: OpenNamespace returned 0x%x", v6);
          }
        }
        v16 = CoSwitchCallContext(0, &ppOldObject);
        v6 = v16;
        if ( v16 < 0 )
        {
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"ExecAsyncMethod::CoSwitchCallContext failed with 0x%x",
            (unsigned int)v16);
LABEL_84:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
LABEL_100:
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v38);
          goto LABEL_136;
        }
        v44 = 0;
        SOMFromSID = GetSOMFromSID(v13);
        XPtrLF<unsigned short>::operator=(&v44, SOMFromSID);
        if ( v44 )
        {
          v15 = 1;
          v20 = AuthenticateUser(v55, 0, (_DWORD)v44, v18, (__int64)&v48);
          v6 = v20;
          if ( v20 < 0 )
          {
            CDebugWrapper::Msg(
              (CDebugWrapper *)dbgRsop,
              4u,
              L"ExecAsyncMethod::User is not a delegated admin. Error 0x%x",
              (unsigned int)v20);
            v15 = 0;
          }
        }
        else
        {
          v19 = GetLastError();
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            4u,
            L"ExecAsyncMethod::No User SOM. Probably local account. error %d",
            v19);
        }
        v21 = CoSwitchCallContext(ppOldObject, (IUnknown **)&v50);
        if ( v21 < 0 )
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"ExecAsyncMethod::CoSwitchCallContext failed with 0x%x",
            (unsigned int)v21);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v44);
        if ( v15 )
        {
          v7 = (const unsigned __int16 **)hMem;
          goto LABEL_81;
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v38);
        v7 = (const unsigned __int16 **)hMem;
        v8 = v57;
      }
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"EnumerateUserNameSpace: %s is not a valid Sid", v13);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"EnumerateUserNameSpace: %s is not a valid Sid", v13);
        }
      }
      LocalFree(pSid);
LABEL_54:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v38);
      v8 = v57;
    }
  }
  if ( v9 != 1 || v39 )
  {
LABEL_129:
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"EnumerateUserNameSpace: Get failed. hr=0x%x", v9);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Get failed. hr=0x%x", v9);
      }
    }
    v6 = -2147467259;
  }
  else
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = v8;
    v27 = SafeArrayCreate(8u, 1u, &rgsabound);
    v28 = a3;
    *a3 = v27;
    if ( v27 )
    {
      rgIndices = 0;
      v32 = 0;
      while ( 1 )
      {
        if ( v32 >= v8 )
        {
          v6 = 0;
          goto LABEL_136;
        }
        XBStr::XBStr((XBStr *)&v50, *v7);
        v33 = v50;
        v6 = SafeArrayPutElement(*v28, &rgIndices, v50);
        if ( (v6 & 0x80000000) != 0 )
          break;
        SysFreeString(v33);
        v32 = ++rgIndices;
        v7 = (const unsigned __int16 **)v7[1];
        v28 = a3;
        v8 = v57;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"EnumerateUserNameSpace: SafeArrayPutElement failed. Error = 0x%x", v6);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"EnumerateUserNameSpace: SafeArrayPutElement failed. Error = 0x%x", v6);
        }
      }
      SysFreeString(v33);
    }
    else
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v29 = g_lpDebugMsg;
        if ( g_lpDebugMsg )
        {
          v30 = GetLastError();
          v29(2u, L"EnumerateUserNameSpace: Failed to allocate memory. Error = %d", v30);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          v31 = GetLastError();
          RedirectDebugMsg(2u, L"EnumerateUserNameSpace: Failed to allocate memory. Error = %d", v31);
        }
      }
      v6 = -2147467259;
    }
  }
LABEL_136:
  rgIndices = 0;
  if ( v57 )
  {
    v34 = (HLOCAL *)hMem;
    do
    {
      if ( *v34 )
        LocalFree(*v34);
      v35 = v34;
      v34 = (HLOCAL *)v34[1];
      LocalFree(v35);
      ++rgIndices;
    }
    while ( rgIndices < v57 );
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
  SysFreeString(v49);
LABEL_142:
  SysFreeString(v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
LABEL_143:
  SysFreeString(v4);
LABEL_144:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
  return v6;
}

```

## disassembly

```asm
0x1800ae920  mov     rax, rsp
0x1800ae923  mov     [rax+8], rbx
0x1800ae927  mov     [rax+18h], r8
0x1800ae92b  mov     [rax+10h], rdx
0x1800ae92f  push    rbp
0x1800ae930  push    rdi
0x1800ae931  push    r12
0x1800ae933  push    r13
0x1800ae935  push    r15
0x1800ae937  lea     rbp, [rax-5Fh]
0x1800ae93b  sub     rsp, 0F0h
0x1800ae942  mov     rbx, rcx
0x1800ae945  xor     r12d, r12d
0x1800ae948  mov     [rbp+57h+var_68], r12d
0x1800ae94c  mov     [rbp+57h+ppOldObject], r12
0x1800ae950  mov     [r8], r12
0x1800ae953  mov     [rbp+57h+var_70], r12
0x1800ae957  lea     rdx, aRootRsopUser; "\\\\.\\Root\\Rsop\\User"
0x1800ae95e  lea     rcx, [rbp+57h+bstrString]; this
0x1800ae962  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800ae967  nop
0x1800ae968  mov     rdi, [rbp+57h+bstrString]
0x1800ae96c  test    rdi, rdi
0x1800ae96f  jnz     short loc_1800AE9C2
0x1800ae971  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800ae978  jz      short loc_1800AE9BB
0x1800ae97a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ae981  test    rax, rax
0x1800ae984  jz      short loc_1800AE997
0x1800ae986  lea     rdx, aEnumerateusern; "EnumerateUserNameSpace: Failed to alloc"...
0x1800ae98d  lea     ecx, [rdi+2]
0x1800ae990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae995  jmp     short loc_1800AE9BB
0x1800ae997  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800ae99e  jz      short loc_1800AE9BB
0x1800ae9a0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ae9a7  jz      short loc_1800AE9BB
0x1800ae9a9  lea     rdx, aEnumerateusern; "EnumerateUserNameSpace: Failed to alloc"...
0x1800ae9b0  mov     ecx, 2; unsigned int
0x1800ae9b5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ae9ba  nop
0x1800ae9bb  xor     ecx, ecx
0x1800ae9bd  jmp     loc_1800AEAE0
0x1800ae9c2  mov     rax, [rbx]
0x1800ae9c5  lea     rcx, [rbp+57h+var_70]
0x1800ae9c9  mov     [rsp+40h], rcx
0x1800ae9ce  mov     [rsp+110h+var_D8], r12
0x1800ae9d3  mov     [rsp+110h+var_E0], r12
0x1800ae9d8  mov     dword ptr [rsp+110h+var_E8], r12d
0x1800ae9dd  mov     [rsp+110h+var_F0], r12
0x1800ae9e2  xor     r9d, r9d
0x1800ae9e5  xor     r8d, r8d
0x1800ae9e8  mov     rdx, rdi
0x1800ae9eb  mov     rcx, rbx
0x1800ae9ee  mov     rax, [rax+18h]
0x1800ae9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9f7  mov     r15d, eax
0x1800ae9fa  test    eax, eax
0x1800ae9fc  jns     short loc_1800AEA63
0x1800ae9fe  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800aea05  jz      loc_1800AF38C
0x1800aea0b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aea12  test    rax, rax
0x1800aea15  jz      short loc_1800AEA30
0x1800aea17  mov     r8d, r15d
0x1800aea1a  lea     rdx, aEnumerateusern_0; "EnumerateUserNameSpace: ConnectServer f"...
0x1800aea21  mov     ecx, 2
0x1800aea26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea2b  jmp     loc_1800AF38C
0x1800aea30  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800aea37  jz      loc_1800AF38C
0x1800aea3d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aea44  jz      loc_1800AF38C
0x1800aea4a  mov     r8d, r15d
0x1800aea4d  lea     rdx, aEnumerateusern_0; "EnumerateUserNameSpace: ConnectServer f"...
0x1800aea54  mov     ecx, 2; unsigned int
0x1800aea59  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aea5e  jmp     loc_1800AF38C
0x1800aea63  mov     [rbp+57h+var_A8], r12
0x1800aea67  lea     rdx, aNamespace_0; "__namespace"
0x1800aea6e  lea     rcx, [rbp+57h+var_98]; this
0x1800aea72  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800aea77  nop
0x1800aea78  cmp     [rbp+57h+var_98], r12
0x1800aea7c  jnz     short loc_1800AEAF1
0x1800aea7e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800aea85  jz      short loc_1800AEACA
0x1800aea87  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aea8e  test    rax, rax
0x1800aea91  jz      short loc_1800AEAA6
0x1800aea93  lea     rdx, aEnumerateusern; "EnumerateUserNameSpace: Failed to alloc"...
0x1800aea9a  mov     ecx, 2
0x1800aea9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeaa4  jmp     short loc_1800AEACA
0x1800aeaa6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800aeaad  jz      short loc_1800AEACA
0x1800aeaaf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aeab6  jz      short loc_1800AEACA
0x1800aeab8  lea     rdx, aEnumerateusern; "EnumerateUserNameSpace: Failed to alloc"...
0x1800aeabf  mov     ecx, 2; unsigned int
0x1800aeac4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aeac9  nop
0x1800aeaca  xor     ecx, ecx; bstrString
0x1800aeacc  call    cs:__imp_SysFreeString
0x1800aead2  nop
0x1800aead3  lea     rcx, [rbp+57h+var_A8]
0x1800aead7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800aeadc  nop
0x1800aeadd  mov     rcx, rdi; bstrString
0x1800aeae0  call    cs:__imp_SysFreeString
0x1800aeae6  mov     r15d, 8007000Eh
0x1800aeaec  jmp     loc_1800AF396
0x1800aeaf1  mov     rcx, [rbp+57h+var_70]
0x1800aeaf5  mov     rax, [rcx]
0x1800aeaf8  lea     rdx, [rbp+57h+var_A8]
0x1800aeafc  mov     [rsp+110h+var_F0], rdx
0x1800aeb01  xor     r9d, r9d
0x1800aeb04  lea     r8d, [r9+21h]
0x1800aeb08  mov     rdx, [rbp+57h+var_98]
0x1800aeb0c  mov     rax, [rax+90h]
0x1800aeb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb18  mov     r15d, eax
0x1800aeb1b  test    eax, eax
0x1800aeb1d  jns     short loc_1800AEB84
0x1800aeb1f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800aeb26  jz      loc_1800AF377
0x1800aeb2c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aeb33  test    rax, rax
0x1800aeb36  jz      short loc_1800AEB51
0x1800aeb38  mov     r8d, r15d
0x1800aeb3b  lea     rdx, aEnumerateusern_7; "EnumerateUserNameSpace: CreateInstanceE"...
0x1800aeb42  mov     ecx, 2
0x1800aeb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb4c  jmp     loc_1800AF377
0x1800aeb51  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800aeb58  jz      loc_1800AF377
0x1800aeb5e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aeb65  jz      loc_1800AF377
0x1800aeb6b  mov     r8d, r15d
0x1800aeb6e  lea     rdx, aEnumerateusern_7; "EnumerateUserNameSpace: CreateInstanceE"...
0x1800aeb75  mov     ecx, 2; unsigned int
0x1800aeb7a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aeb7f  jmp     loc_1800AF377
0x1800aeb84  lea     rdx, aName; "Name"
0x1800aeb8b  lea     rcx, [rbp+57h+var_60]; this
0x1800aeb8f  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x1800aeb94  nop
0x1800aeb95  cmp     [rbp+57h+var_60], r12
0x1800aeb99  jnz     short loc_1800AEC19
0x1800aeb9b  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800aeba2  jz      short loc_1800AEBE7
0x1800aeba4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aebab  test    rax, rax
0x1800aebae  jz      short loc_1800AEBC3
0x1800aebb0  lea     rdx, aEnumerateusern_9; "EnumerateUserNameSpace: Failed to alloc"...
0x1800aebb7  mov     ecx, 2
0x1800aebbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aebc1  jmp     short loc_1800AEBE7
0x1800aebc3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800aebca  jz      short loc_1800AEBE7
0x1800aebcc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aebd3  jz      short loc_1800AEBE7
0x1800aebd5  lea     rdx, aEnumerateusern_9; "EnumerateUserNameSpace: Failed to alloc"...
0x1800aebdc  mov     ecx, 2; unsigned int
0x1800aebe1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aebe6  nop
0x1800aebe7  xor     ecx, ecx; bstrString
0x1800aebe9  call    cs:__imp_SysFreeString
0x1800aebef  nop
0x1800aebf0  mov     rcx, [rbp+57h+var_98]; bstrString
0x1800aebf4  call    cs:__imp_SysFreeString
0x1800aebfa  nop
0x1800aebfb  lea     rcx, [rbp+57h+var_A8]
0x1800aebff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800aec04  nop
0x1800aec05  mov     rcx, rdi; bstrString
0x1800aec08  call    cs:__imp_SysFreeString
0x1800aec0e  mov     r15d, 80004005h
0x1800aec14  jmp     loc_1800AF396
0x1800aec19  mov     r13, r12
0x1800aec1c  mov     [rbp+57h+hMem], r12
0x1800aec20  mov     ebx, r12d
0x1800aec23  mov     [rbp+57h+arg_18], ebx
0x1800aec26  mov     [rbp+57h+var_78], r12
0x1800aec2a  mov     [rbp+57h+var_B0], 1
0x1800aec31  mov     r12d, 2
0x1800aec37  xor     r15d, r15d
0x1800aec3a  mov     rcx, [rbp+57h+var_A8]
0x1800aec3e  mov     rax, [rcx]
0x1800aec41  lea     rdx, [rbp+57h+var_B0]
0x1800aec45  mov     [rsp+110h+var_F0], rdx
0x1800aec4a  lea     r9, [rbp+57h+var_78]
0x1800aec4e  xor     edx, edx
0x1800aec50  lea     r8d, [rdx+1]
0x1800aec54  mov     rax, [rax+20h]
0x1800aec58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec5d  test    eax, eax
0x1800aec5f  jnz     loc_1800AF177
0x1800aec65  cmp     [rbp+57h+var_B0], r15d
0x1800aec69  jz      loc_1800AF2D0
0x1800aec6f  xorps   xmm0, xmm0
0x1800aec72  xor     eax, eax
0x1800aec74  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800aec78  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800aec7c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800aec80  call    cs:__imp_VariantInit
0x1800aec86  mov     rcx, [rbp+57h+var_78]
0x1800aec8a  mov     rax, [rcx]
0x1800aec8d  mov     [rsp+110h+var_E8], r15
0x1800aec92  mov     [rsp+110h+var_F0], r15
0x1800aec97  lea     r9, [rbp+57h+pvarg]
0x1800aec9b  xor     r8d, r8d
0x1800aec9e  mov     rdx, [rbp+57h+var_60]
0x1800aeca2  mov     rax, [rax+20h]
0x1800aeca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aecab  mov     r15d, eax
0x1800aecae  lea     rcx, [rbp+57h+var_78]
0x1800aecb2  call    ??4?$XInterface@UIWbemServices@@@@QEAAXPEAUIWbemServices@@@Z; XInterface<IWbemServices>::operator=(IWbemServices *)
0x1800aecb7  xor     edx, edx
0x1800aecb9  test    r15d, r15d
0x1800aecbc  js      loc_1800AF110
0x1800aecc2  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x1800aecc6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800aecca  inc     rax
0x1800aeccd  cmp     [rcx+rax*2], dx
0x1800aecd1  jnz     short loc_1800AECCA
0x1800aecd3  lea     r15, [rax+1]
0x1800aecd7  lea     rdx, [r15+r15]; uBytes
0x1800aecdb  mov     ecx, 40h ; '@'; uFlags
0x1800aece0  call    cs:__imp_LocalAlloc
0x1800aece6  mov     rbx, rax
0x1800aece9  mov     [rbp+57h+var_B8], rax
0x1800aeced  test    rax, rax
0x1800aecf0  jz      loc_1800AF095
0x1800aecf6  mov     r8, rax
0x1800aecf9  mov     rdx, r15
0x1800aecfc  mov     rcx, qword ptr [rbp+57h+pvarg+8]
0x1800aed00  call    ConvertWMINameToSid
0x1800aed05  xor     r15d, r15d
0x1800aed08  mov     [rbp+57h+pSid], r15
0x1800aed0c  lea     rdx, [rbp+57h+pSid]; void **
0x1800aed10  mov     rcx, rbx; unsigned __int16 *
0x1800aed13  call    ?AllocateAndInitSidFromString@@YAJPEBGPEAPEAX@Z; AllocateAndInitSidFromString(ushort const *,void * *)
0x1800aed18  test    eax, eax
0x1800aed1a  jz      short loc_1800AED7E
0x1800aed1c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800aed23  jz      short loc_1800AED6D
0x1800aed25  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aed2c  test    rax, rax
0x1800aed2f  jz      short loc_1800AED46
0x1800aed31  mov     r8, rbx
0x1800aed34  lea     rdx, aEnumerateusern_10; "EnumerateUserNameSpace: AllocateAndInit"...
0x1800aed3b  lea     ecx, [r15+4]
0x1800aed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed44  jmp     short loc_1800AED6D
0x1800aed46  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800aed4d  jz      short loc_1800AED6D
0x1800aed4f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aed56  jz      short loc_1800AED6D
0x1800aed58  mov     r8, rbx
0x1800aed5b  lea     rdx, aEnumerateusern_10; "EnumerateUserNameSpace: AllocateAndInit"...
0x1800aed62  mov     ecx, 4; unsigned int
0x1800aed67  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aed6c  nop
0x1800aed6d  lea     rcx, [rbp+57h+var_B8]
0x1800aed71  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800aed76  mov     ebx, [rbp+57h+arg_18]
0x1800aed79  jmp     loc_1800AEC3A
0x1800aed7e  mov     rcx, [rbp+57h+pSid]; pSid
0x1800aed82  call    cs:__imp_IsValidSid
0x1800aed88  test    eax, eax
0x1800aed8a  jnz     short loc_1800AEDE9
0x1800aed8c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800aed93  jz      short loc_1800AEDDD
0x1800aed95  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800aed9c  test    rax, rax
0x1800aed9f  jz      short loc_1800AEDB7
0x1800aeda1  mov     r8, rbx
0x1800aeda4  lea     rdx, aEnumerateusern_5; "EnumerateUserNameSpace: %s is not a val"...
0x1800aedab  mov     ecx, 4
0x1800aedb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aedb5  jmp     short loc_1800AEDDD
0x1800aedb7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800aedbe  jz      short loc_1800AEDDD
0x1800aedc0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800aedc7  jz      short loc_1800AEDDD
0x1800aedc9  mov     r8, rbx
0x1800aedcc  lea     rdx, aEnumerateusern_5; "EnumerateUserNameSpace: %s is not a val"...
0x1800aedd3  mov     ecx, 4; unsigned int
0x1800aedd8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800aeddd  mov     rcx, [rbp+57h+pSid]; hMem
0x1800aede1  call    cs:__imp_LocalFree
0x1800aede7  jmp     short loc_1800AED6D
0x1800aede9  mov     rcx, [rbp+57h+pSid]; hMem
0x1800aeded  call    cs:__imp_LocalFree
0x1800aedf3  call    cs:__imp_CoImpersonateClient
0x1800aedf9  mov     r15d, eax
0x1800aedfc  xor     edx, edx
0x1800aedfe  test    eax, eax
0x1800aee00  js      loc_1800AF06D
  ... truncated ...
```
