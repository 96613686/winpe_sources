# cdp::GetUserContextTokenFromWebAccount(Windows::Security::Credentials::IWebAccount *)

- ea: `0x1800aeb14`
- end: `0x1800af0b6`
- name: `?GetUserContextTokenFromWebAccount@cdp@@YA_KPEAUIWebAccount@Credentials@Security@Windows@@@Z`
- size: `1442`
- prototype: `unsigned __int64 __fastcall(cdp *__hidden this, struct Windows::Security::Credentials::IWebAccount *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800ae8a4`
- `0x1800e6020`

## callees

- `0x18001ce80`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800aeb14`
- `0x1800af0bc`
- `0x1800af0f0`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aeb7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aec32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aed0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aed90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aee80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aef1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af04e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aeb7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aec32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aed0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aed90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aee80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aef1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800af04e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aee3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aee3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aee27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aee27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aee5f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800aee5f`

## string_xrefs

- `0x1800aeba4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800aec58`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800aed35`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800aedb6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800aeea6`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800aef44`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800af074`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall cdp::GetUserContextTokenFromWebAccount(
        cdp *this,
        struct Windows::Security::Credentials::IWebAccount *a2)
{
  __int64 (__fastcall *v3)(cdp *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  int v13; // eax
  unsigned int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  unsigned __int64 *v22; // rdx
  cdp *v23; // rcx
  int v24; // ebx
  unsigned __int64 *v25; // rdx
  int CurrentUserContextToken; // eax
  unsigned int v27; // ebx
  DWORD v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rax
  int v33; // ecx
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  HRESULT v38; // eax
  HSTRING v39; // rbx
  int ActivationFactory; // eax
  unsigned int v41; // ebx
  DWORD v42; // eax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  int v47; // eax
  unsigned int v48; // ebx
  DWORD v49; // eax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 (__fastcall ***v58)(_QWORD, _QWORD, _QWORD); // rcx
  int v60; // eax
  unsigned int v61; // ebx
  DWORD v62; // eax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rax
  int v67; // [rsp+30h] [rbp-59h] BYREF
  __int64 v68; // [rsp+38h] [rbp-51h] BYREF
  const char *v69; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v70[4]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v71; // [rsp+58h] [rbp-31h] BYREF
  __int64 v72; // [rsp+60h] [rbp-29h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-21h] BYREF
  __int64 v74; // [rsp+70h] [rbp-19h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+27h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+3Fh] BYREF

  v73 = 0;
  v3 = *(__int64 (__fastcall **)(cdp *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)this + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
  v4 = v3(this, &v73);
  v5 = v4;
  if ( v4 < 0 )
  {
    v69 = ".\\platformutils.cpp";
    v70[0] = 222;
    v67 = v4;
    CurrentThreadId = GetCurrentThreadId();
    v68 = CurrentThreadId;
    Log<long &,char const * &,int &,unsigned __int64>(
      CurrentThreadId,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v67,
      (unsigned int)&v69,
      (__int64)v70,
      (__int64)&v68);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v69);
    v10 = cdp::ErrorCodeToString(v5, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, v5, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v72 = 0;
  v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v73;
  v12 = **v73;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v72);
  v13 = v12(v11, &GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe, &v72);
  v14 = v13;
  if ( v13 < 0 )
  {
    v69 = ".\\platformutils.cpp";
    v70[0] = 225;
    v67 = v13;
    v15 = GetCurrentThreadId();
    v68 = v15;
    Log<long &,char const * &,int &,unsigned __int64>(
      v15,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v67,
      (unsigned int)&v69,
      (__int64)v70,
      (__int64)&v68);
    v16 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v69);
    v19 = cdp::ErrorCodeToString(v14, v17, v18, v16);
    ConnectedDevices::Exception::Exception(pExceptionObject, v14, v19);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v71 = 0;
  v20 = v72;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v71);
  v24 = v21(v20, &v71);
  v74 = 0;
  if ( v24 == -2136866037 )
  {
    if ( cdp::IsRunningOnIoT(v23) )
    {
      CurrentUserContextToken = cdp::GetCurrentUserContextToken((cdp *)&v74, v25);
      v27 = CurrentUserContextToken;
      if ( CurrentUserContextToken < 0 )
      {
        v69 = ".\\platformutils.cpp";
        v70[0] = 238;
        v67 = CurrentUserContextToken;
        v28 = GetCurrentThreadId();
        v68 = v28;
        Log<long &,char const * &,int &,unsigned __int64>(
          v28,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v67,
          (unsigned int)&v69,
          (__int64)v70,
          (__int64)&v68);
        v29 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v69);
        v32 = cdp::ErrorCodeToString(v27, v30, v31, v29);
        ConnectedDevices::Exception::Exception(pExceptionObject, v27, v32);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      goto LABEL_20;
    }
LABEL_10:
    v69 = ".\\platformutils.cpp";
    v70[0] = 242;
    v67 = v24;
    v68 = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v33,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v67,
      (unsigned int)&v69,
      (__int64)v70,
      (__int64)&v68);
    v34 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, &v69);
    v37 = cdp::ErrorCodeToString((unsigned int)v24, v35, v36, v34);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v24, v37);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( v24 < 0 )
    goto LABEL_10;
  if ( v71 )
  {
    v68 = 0;
    string = 0;
    v38 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
    if ( v38 < 0 )
    {
      RaiseException(v38, 1u, 0, 0);
      __debugbreak();
    }
    v39 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
    ActivationFactory = RoGetActivationFactory(v39, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v68);
    v41 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      hstringHeader.Reserved.Reserved1 = (PVOID)".\\platformutils.cpp";
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 247;
      v67 = ActivationFactory;
      v42 = GetCurrentThreadId();
      v69 = (const char *)v42;
      Log<long &,char const * &,int &,unsigned __int64>(
        v42,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v67,
        (unsigned int)&hstringHeader,
        (__int64)&hstringHeader.Reserved.Reserved2[8],
        (__int64)&v69);
      v43 = cdp::ExceptionStackFromSourceLocationInfo(&v69, &hstringHeader);
      v46 = cdp::ErrorCodeToString(v41, v44, v45, v43);
      ConnectedDevices::Exception::Exception(pExceptionObject, v41, v46);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v47 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v68 + 136LL))(v68, v71, &v74);
    v48 = v47;
    if ( v47 < 0 )
    {
      hstringHeader.Reserved.Reserved1 = (PVOID)".\\platformutils.cpp";
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 248;
      v67 = v47;
      v49 = GetCurrentThreadId();
      v69 = (const char *)v49;
      Log<long &,char const * &,int &,unsigned __int64>(
        v49,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v67,
        (unsigned int)&hstringHeader,
        (__int64)&hstringHeader.Reserved.Reserved2[8],
        (__int64)&v69);
      v50 = cdp::ExceptionStackFromSourceLocationInfo(&v69, &hstringHeader);
      v53 = cdp::ErrorCodeToString(v48, v51, v52, v50);
      ConnectedDevices::Exception::Exception(pExceptionObject, v48, v53);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v54 = v68;
    if ( v68 )
    {
      v68 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
  }
  else
  {
    v60 = cdp::GetCurrentUserContextToken((cdp *)&v74, v22);
    v61 = v60;
    if ( v60 < 0 )
    {
      hstringHeader.Reserved.Reserved1 = (PVOID)".\\platformutils.cpp";
      *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = 252;
      v67 = v60;
      v62 = GetCurrentThreadId();
      v69 = (const char *)v62;
      Log<long &,char const * &,int &,unsigned __int64>(
        v62,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v67,
        (unsigned int)&hstringHeader,
        (__int64)&hstringHeader.Reserved.Reserved2[8],
        (__int64)&v69);
      v63 = cdp::ExceptionStackFromSourceLocationInfo(&v69, &hstringHeader);
      v66 = cdp::ErrorCodeToString(v61, v64, v65, v63);
      ConnectedDevices::Exception::Exception(pExceptionObject, v61, v66);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
  }
LABEL_20:
  v55 = v74;
  v56 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  v57 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  }
  v58 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v73;
  if ( v73 )
  {
    v73 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v58)[2])(v58);
  }
  return v55;
}

```

## disassembly

```asm
0x1800aeb14  mov     [rsp-8+arg_8], rbx
0x1800aeb19  mov     [rsp-8+arg_10], rdi
0x1800aeb1e  push    rbp
0x1800aeb1f  lea     rbp, [rsp-57h]
0x1800aeb24  sub     rsp, 0E0h
0x1800aeb2b  mov     rax, cs:__security_cookie
0x1800aeb32  xor     rax, rsp
0x1800aeb35  mov     [rbp+57h+var_10], rax
0x1800aeb39  mov     rdi, rcx
0x1800aeb3c  mov     [rbp+57h+var_78], 0
0x1800aeb44  mov     rax, [rcx]
0x1800aeb47  mov     rbx, [rax+30h]
0x1800aeb4b  lea     rcx, [rbp+57h+var_78]
0x1800aeb4f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aeb54  lea     rdx, [rbp+57h+var_78]
0x1800aeb58  mov     rcx, rdi
0x1800aeb5b  mov     rax, rbx
0x1800aeb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb63  mov     ebx, eax
0x1800aeb65  test    eax, eax
0x1800aeb67  jns     short loc_1800AEBE6
0x1800aeb69  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aeb70  mov     [rbp+57h+var_A0], rcx
0x1800aeb74  mov     [rbp+57h+var_98], 0DEh
0x1800aeb7b  mov     [rbp+57h+var_B0], eax
0x1800aeb7e  call    cs:__imp_GetCurrentThreadId
0x1800aeb84  mov     ecx, eax
0x1800aeb86  mov     [rbp+57h+var_A8], rcx
0x1800aeb8a  lea     rax, [rbp+57h+var_A8]
0x1800aeb8e  mov     [rsp+0E0h+var_B8], rax
0x1800aeb93  lea     rax, [rbp+57h+var_98]
0x1800aeb97  mov     [rsp+0E0h+var_C0], rax
0x1800aeb9c  lea     r9, [rbp+57h+var_A0]
0x1800aeba0  lea     r8, [rbp+57h+var_B0]
0x1800aeba4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aebab  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aebb0  lea     rdx, [rbp+57h+var_A0]
0x1800aebb4  lea     rcx, [rbp+57h+hstringHeader]
0x1800aebb8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aebbd  mov     r9, rax
0x1800aebc0  mov     ecx, ebx
0x1800aebc2  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aebc7  mov     r8, rax
0x1800aebca  mov     edx, ebx
0x1800aebcc  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aebd0  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aebd5  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aebdc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aebe0  call    _CxxThrowException_0
0x1800aebe6  mov     [rbp+57h+var_80], 0
0x1800aebee  mov     rbx, [rbp+57h+var_78]
0x1800aebf2  mov     rax, [rbx]
0x1800aebf5  mov     rdi, [rax]
0x1800aebf8  lea     rcx, [rbp+57h+var_80]
0x1800aebfc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aec01  lea     r8, [rbp+57h+var_80]
0x1800aec05  lea     rdx, _GUID_da1c518b_970d_4d49_825c_f2706f8ca7fe
0x1800aec0c  mov     rcx, rbx
0x1800aec0f  mov     rax, rdi
0x1800aec12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec17  mov     ebx, eax
0x1800aec19  test    eax, eax
0x1800aec1b  jns     short loc_1800AEC9A
0x1800aec1d  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aec24  mov     [rbp+57h+var_A0], rcx
0x1800aec28  mov     [rbp+57h+var_98], 0E1h
0x1800aec2f  mov     [rbp+57h+var_B0], eax
0x1800aec32  call    cs:__imp_GetCurrentThreadId
0x1800aec38  mov     ecx, eax
0x1800aec3a  mov     [rbp+57h+var_A8], rcx
0x1800aec3e  lea     rax, [rbp+57h+var_A8]
0x1800aec42  mov     [rsp+0E0h+var_B8], rax
0x1800aec47  lea     rax, [rbp+57h+var_98]
0x1800aec4b  mov     [rsp+0E0h+var_C0], rax
0x1800aec50  lea     r9, [rbp+57h+var_A0]
0x1800aec54  lea     r8, [rbp+57h+var_B0]
0x1800aec58  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aec5f  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aec64  lea     rdx, [rbp+57h+var_A0]
0x1800aec68  lea     rcx, [rbp+57h+hstringHeader]
0x1800aec6c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aec71  mov     r9, rax
0x1800aec74  mov     ecx, ebx
0x1800aec76  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aec7b  mov     r8, rax
0x1800aec7e  mov     edx, ebx
0x1800aec80  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aec84  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aec89  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aec90  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aec94  call    _CxxThrowException_0
0x1800aec9a  mov     [rbp+57h+var_88], 0
0x1800aeca2  mov     rdi, [rbp+57h+var_80]
0x1800aeca6  mov     rax, [rdi]
0x1800aeca9  mov     rbx, [rax+30h]
0x1800aecad  lea     rcx, [rbp+57h+var_88]
0x1800aecb1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aecb6  lea     rdx, [rbp+57h+var_88]
0x1800aecba  mov     rcx, rdi
0x1800aecbd  mov     rax, rbx
0x1800aecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aecc5  mov     ebx, eax
0x1800aecc7  mov     [rbp+57h+var_70], 0
0x1800aeccf  cmp     eax, 80A2030Bh
0x1800aecd4  jnz     loc_1800AED77
0x1800aecda  call    ?IsRunningOnIoT@cdp@@YA_NXZ; cdp::IsRunningOnIoT(void)
0x1800aecdf  test    al, al
0x1800aece1  jz      loc_1800AED7B
0x1800aece7  lea     rcx, [rbp+57h+var_70]; this
0x1800aeceb  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x1800aecf0  mov     ebx, eax
0x1800aecf2  test    eax, eax
0x1800aecf4  jns     loc_1800AEFA4
0x1800aecfa  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aed01  mov     [rbp+57h+var_A0], rcx
0x1800aed05  mov     [rbp+57h+var_98], 0EEh
0x1800aed0c  mov     [rbp+57h+var_B0], eax
0x1800aed0f  call    cs:__imp_GetCurrentThreadId
0x1800aed15  mov     ecx, eax
0x1800aed17  mov     [rbp+57h+var_A8], rcx
0x1800aed1b  lea     rax, [rbp+57h+var_A8]
0x1800aed1f  mov     [rsp+0E0h+var_B8], rax
0x1800aed24  lea     rax, [rbp+57h+var_98]
0x1800aed28  mov     [rsp+0E0h+var_C0], rax
0x1800aed2d  lea     r9, [rbp+57h+var_A0]
0x1800aed31  lea     r8, [rbp+57h+var_B0]
0x1800aed35  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aed3c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aed41  lea     rdx, [rbp+57h+var_A0]
0x1800aed45  lea     rcx, [rbp+57h+hstringHeader]
0x1800aed49  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aed4e  mov     r9, rax
0x1800aed51  mov     ecx, ebx
0x1800aed53  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aed58  mov     r8, rax
0x1800aed5b  mov     edx, ebx
0x1800aed5d  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aed61  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aed66  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aed6d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aed71  call    _CxxThrowException_0
0x1800aed77  test    ebx, ebx
0x1800aed79  jns     short loc_1800AEDF8
0x1800aed7b  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aed82  mov     [rbp+57h+var_A0], rcx
0x1800aed86  mov     [rbp+57h+var_98], 0F2h
0x1800aed8d  mov     [rbp+57h+var_B0], ebx
0x1800aed90  call    cs:__imp_GetCurrentThreadId
0x1800aed96  mov     eax, eax
0x1800aed98  mov     [rbp+57h+var_A8], rax
0x1800aed9c  lea     rax, [rbp+57h+var_A8]
0x1800aeda0  mov     [rsp+0E0h+var_B8], rax
0x1800aeda5  lea     rax, [rbp+57h+var_98]
0x1800aeda9  mov     [rsp+0E0h+var_C0], rax
0x1800aedae  lea     r9, [rbp+57h+var_A0]
0x1800aedb2  lea     r8, [rbp+57h+var_B0]
0x1800aedb6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aedbd  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aedc2  lea     rdx, [rbp+57h+var_A0]
0x1800aedc6  lea     rcx, [rbp+57h+hstringHeader]
0x1800aedca  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aedcf  mov     r9, rax
0x1800aedd2  mov     ecx, ebx
0x1800aedd4  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aedd9  mov     r8, rax
0x1800aeddc  mov     edx, ebx
0x1800aedde  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aede2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aede7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aedee  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aedf2  call    _CxxThrowException_0
0x1800aedf8  cmp     [rbp+57h+var_88], 0
0x1800aedfd  jz      loc_1800AF026
0x1800aee03  mov     [rbp+57h+var_A8], 0
0x1800aee0b  mov     [rbp+57h+string], 0
0x1800aee13  lea     r9, [rbp+57h+string]; string
0x1800aee17  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800aee1b  mov     edx, 23h ; '#'; length
0x1800aee20  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800aee27  call    cs:__imp_WindowsCreateStringReference
0x1800aee2d  test    eax, eax
0x1800aee2f  jns     short loc_1800AEE44
0x1800aee31  xor     r9d, r9d; lpArguments
0x1800aee34  xor     r8d, r8d; nNumberOfArguments
0x1800aee37  lea     edx, [r9+1]; dwExceptionFlags
0x1800aee3b  mov     ecx, eax; dwExceptionCode
0x1800aee3d  call    cs:__imp_RaiseException
0x1800aee43  int     3; Trap to Debugger
0x1800aee44  mov     rbx, [rbp+57h+string]
0x1800aee48  lea     rcx, [rbp+57h+var_A8]
0x1800aee4c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800aee51  lea     r8, [rbp+57h+var_A8]
0x1800aee55  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800aee5c  mov     rcx, rbx
0x1800aee5f  call    cs:__imp_RoGetActivationFactory
0x1800aee65  mov     ebx, eax
0x1800aee67  test    eax, eax
0x1800aee69  jns     short loc_1800AEEE8
0x1800aee6b  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aee72  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x1800aee76  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], 0F7h
0x1800aee7d  mov     [rbp+57h+var_B0], eax
0x1800aee80  call    cs:__imp_GetCurrentThreadId
0x1800aee86  mov     ecx, eax
0x1800aee88  mov     [rbp+57h+var_A0], rcx
0x1800aee8c  lea     rax, [rbp+57h+var_A0]
0x1800aee90  mov     [rsp+0E0h+var_B8], rax
0x1800aee95  lea     rax, [rbp+57h+hstringHeader.Reserved+8]
0x1800aee99  mov     [rsp+0E0h+var_C0], rax
0x1800aee9e  lea     r9, [rbp+57h+hstringHeader]
0x1800aeea2  lea     r8, [rbp+57h+var_B0]
0x1800aeea6  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aeead  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aeeb2  lea     rdx, [rbp+57h+hstringHeader]
0x1800aeeb6  lea     rcx, [rbp+57h+var_A0]
0x1800aeeba  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aeebf  mov     r9, rax
0x1800aeec2  mov     ecx, ebx
0x1800aeec4  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aeec9  mov     r8, rax
0x1800aeecc  mov     edx, ebx
0x1800aeece  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aeed2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aeed7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aeede  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aeee2  call    _CxxThrowException_0
0x1800aeee8  mov     rcx, [rbp+57h+var_A8]
0x1800aeeec  mov     rax, [rcx]
0x1800aeeef  lea     r8, [rbp+57h+var_70]
0x1800aeef3  mov     rdx, [rbp+57h+var_88]
0x1800aeef7  mov     rax, [rax+88h]
0x1800aeefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aef03  mov     ebx, eax
0x1800aef05  test    eax, eax
0x1800aef07  jns     short loc_1800AEF86
0x1800aef09  lea     rcx, aPlatformutilsC; ".\\platformutils.cpp"
0x1800aef10  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x1800aef14  mov     dword ptr [rbp+57h+hstringHeader.Reserved+8], 0F8h
0x1800aef1b  mov     [rbp+57h+var_B0], eax
0x1800aef1e  call    cs:__imp_GetCurrentThreadId
0x1800aef24  mov     ecx, eax
0x1800aef26  mov     [rbp+57h+var_A0], rcx
0x1800aef2a  lea     rax, [rbp+57h+var_A0]
0x1800aef2e  mov     [rsp+0E0h+var_B8], rax
0x1800aef33  lea     rax, [rbp+57h+hstringHeader.Reserved+8]
0x1800aef37  mov     [rsp+0E0h+var_C0], rax
0x1800aef3c  lea     r9, [rbp+57h+hstringHeader]
0x1800aef40  lea     r8, [rbp+57h+var_B0]
0x1800aef44  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800aef4b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800aef50  lea     rdx, [rbp+57h+hstringHeader]
0x1800aef54  lea     rcx, [rbp+57h+var_A0]
0x1800aef58  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800aef5d  mov     r9, rax
0x1800aef60  mov     ecx, ebx
0x1800aef62  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800aef67  mov     r8, rax
0x1800aef6a  mov     edx, ebx
0x1800aef6c  lea     rcx, [rbp+57h+pExceptionObject]
0x1800aef70  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800aef75  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800aef7c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800aef80  call    _CxxThrowException_0
0x1800aef86  mov     rcx, [rbp+57h+var_A8]
0x1800aef8a  test    rcx, rcx
0x1800aef8d  jz      short loc_1800AEFA4
0x1800aef8f  mov     [rbp+57h+var_A8], 0
0x1800aef97  mov     rax, [rcx]
0x1800aef9a  mov     rax, [rax+10h]
0x1800aef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aefa3  nop
0x1800aefa4  mov     rbx, [rbp+57h+var_70]
0x1800aefa8  mov     rcx, [rbp+57h+var_88]
0x1800aefac  test    rcx, rcx
0x1800aefaf  jz      short loc_1800AEFC6
0x1800aefb1  mov     [rbp+57h+var_88], 0
0x1800aefb9  mov     rax, [rcx]
0x1800aefbc  mov     rax, [rax+10h]
0x1800aefc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aefc5  nop
0x1800aefc6  mov     rcx, [rbp+57h+var_80]
0x1800aefca  test    rcx, rcx
0x1800aefcd  jz      short loc_1800AEFE4
0x1800aefcf  mov     [rbp+57h+var_80], 0
0x1800aefd7  mov     rax, [rcx]
0x1800aefda  mov     rax, [rax+10h]
0x1800aefde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aefe3  nop
0x1800aefe4  mov     rcx, [rbp+57h+var_78]
0x1800aefe8  test    rcx, rcx
0x1800aefeb  jz      short loc_1800AF002
0x1800aefed  mov     [rbp+57h+var_78], 0
0x1800aeff5  mov     rdx, [rcx]
0x1800aeff8  mov     rax, [rdx+10h]
0x1800aeffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af001  nop
0x1800af002  mov     rax, rbx
0x1800af005  mov     rcx, [rbp+57h+var_10]
0x1800af009  xor     rcx, rsp; StackCookie
0x1800af00c  call    __security_check_cookie
  ... truncated ...
```
