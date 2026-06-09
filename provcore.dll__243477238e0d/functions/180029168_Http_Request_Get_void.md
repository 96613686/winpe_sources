# Http::Request::Get(void)

- ea: `0x180029168`
- end: `0x18002994c`
- name: `?Get@Request@Http@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `2020`
- prototype: `std::vector<unsigned char> *__fastcall(Http::Request *this, std::vector<unsigned char> *result)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003af80`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x1800032f4`
- `0x18000b178`
- `0x180011844`
- `0x180012748`
- `0x180012770`
- `0x18001282c`
- `0x180012bc8`
- `0x180013bdc`
- `0x18001a0d4`
- `0x180028c4c`
- `0x180028e1c`
- `0x180028fc8`
- `0x180029168`
- `0x180029e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002925b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002930b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002925b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800292c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002930b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ef`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800291e8`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800296f0`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800296f0`
- `WINHTTP!WinHttpReadData` at `0x180029794`
- `WINHTTP!WinHttpReadData` at `0x180029794`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800295b3`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800295b3`
- `WINHTTP!WinHttpReceiveResponse` at `0x180029528`
- `WINHTTP!WinHttpReceiveResponse` at `0x180029528`
- `WINHTTP!WinHttpOpenRequest` at `0x1800293ad`
- `WINHTTP!WinHttpOpenRequest` at `0x1800293ad`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18002923f`
- `WINHTTP!WinHttpGetProxyForUrl` at `0x18002923f`
- `WINHTTP!WinHttpCloseHandle` at `0x180029362`
- `WINHTTP!WinHttpSendRequest` at `0x1800294c0`
- `WINHTTP!WinHttpSendRequest` at `0x1800294c0`
- `WINHTTP!WinHttpSetOption` at `0x1800292a6`
- `WINHTTP!WinHttpSetOption` at `0x180029438`
- `WINHTTP!WinHttpSetOption` at `0x1800292a6`
- `WINHTTP!WinHttpSetOption` at `0x180029438`
- `WINHTTP!WinHttpConnect` at `0x1800292fd`
- `WINHTTP!WinHttpConnect` at `0x1800292fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
std::vector<_GUID> *__fastcall Http::Request::Get(Http::Request *this, std::vector<_GUID> *result)
{
  const WCHAR *v4; // rax
  const wchar_t *v5; // rax
  int _a2; // r8d
  DWORD LastError; // eax
  const WCHAR *v8; // rax
  HINTERNET v9; // rax
  DWORD v10; // eax
  HRESULT v11; // ebx
  const WCHAR *v12; // rax
  HINTERNET v13; // r10
  HINTERNET v14; // rax
  void *v15; // rsi
  DWORD v16; // eax
  HRESULT v17; // ebx
  DWORD v18; // eax
  DWORD v19; // eax
  HRESULT v20; // ebx
  DWORD v21; // eax
  HRESULT v22; // ebx
  DWORD v23; // eax
  HRESULT v24; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v25; // rcx
  int v26; // ebx
  const std::allocator<unsigned char> *v27; // r8
  unsigned __int64 v28; // rax
  DWORD v29; // r8d
  unsigned __int64 v30; // rcx
  unsigned __int8 *Mylast; // rdi
  size_t v32; // rbx
  const std::_Value_init_tag *v33; // r8
  unsigned __int8 *v34; // rbx
  size_t v35; // rdi
  DWORD v37; // eax
  HRESULT v38; // ebx
  DWORD v39; // eax
  HRESULT v40; // ebx
  HrException v41; // [rsp+48h] [rbp-B8h] BYREF
  HrException pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+88h] [rbp-78h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v44; // [rsp+A0h] [rbp-60h] BYREF
  std::vector<_GUID> *v45; // [rsp+B8h] [rbp-48h]
  _WINHTTP_PROXY_INFO proxyInfo; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int bytesAvailable; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int bytesRead; // [rsp+DCh] [rbp-24h] BYREF
  unsigned int statusCode; // [rsp+E0h] [rbp-20h] BYREF
  std::vector<unsigned char> tmp; // [rsp+E8h] [rbp-18h] BYREF
  unsigned int statusCodeSize; // [rsp+100h] [rbp+0h] BYREF
  _WINHTTP_AUTOPROXY_OPTIONS options; // [rsp+108h] [rbp+8h] BYREF

  v45 = result;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids);
  }
  memset(&proxyInfo, 0, sizeof(proxyInfo));
  proxyInfo.dwAccessType = 1;
  v44.dismissed_ = 1;
  v44.fun_ = (void (__fastcall *)(void *))GlobalFree;
  v44.p1_ = 0;
  j.dismissed_ = 1;
  j.fun_ = (void (__fastcall *)(void *))GlobalFree;
  j.p1_ = 0;
  if ( this->m_useAutoProxy )
  {
    memset(&options.lpszAutoConfigUrl, 0, 20);
    options.dwFlags = 1;
    options.dwAutoDetectFlags = 3;
    options.fAutoLogonIfChallenged = 1;
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_url._Mypair._Myval2);
    if ( !WinHttpGetProxyForUrl(this->m_session, v4, &options, &proxyInfo)
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      GetLastError();
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_url._Mypair._Myval2);
      WPP_SF_Sd(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v5, _a2);
    }
    bytesRead = 256;
    if ( !WinHttpSetOption(this->m_session, 0xC1u, &bytesRead, 4u)
      && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, LastError);
    }
  }
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_host._Mypair._Myval2);
  v9 = WinHttpConnect(this->m_session, v8, this->m_port, 0);
  if ( !v9 )
  {
    v10 = GetLastError();
    v11 = v10;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Bu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v10);
    }
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    HrException::HrException((HrException *)&options, v11);
    throw (HrException *)&options;
  }
  LOBYTE(options.dwFlags) = 0;
  options.lpszAutoConfigUrl = (const wchar_t *)WinHttpCloseHandle;
  options.lpvReserved = v9;
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_path._Mypair._Myval2);
  v14 = WinHttpOpenRequest(v13, L"GET", v12, 0, 0, 0, this->m_secure ? 0x800000 : 0);
  v15 = v14;
  if ( !v14 )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v16);
    }
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    HrException::HrException(&pExceptionObject, v17);
    throw &pExceptionObject;
  }
  LOBYTE(pExceptionObject.__vftable) = 0;
  pExceptionObject._Data._What = (const char *)WinHttpCloseHandle;
  *(_QWORD *)&pExceptionObject._Data._DoFree = v14;
  if ( proxyInfo.dwAccessType == 3
    && !WinHttpSetOption(v14, 0x26u, &proxyInfo, 0x18u)
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    v18 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Du, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v18);
  }
  if ( this->m_username._Mypair._Myval2._Mysize )
    SetStringOption(v15, 0x1000u, &this->m_username);
  if ( this->m_password._Mypair._Myval2._Mysize )
    SetStringOption(v15, 0x1001u, &this->m_password);
  if ( !WinHttpSendRequest(v15, 0, 0, 0, 0, 0, 0) )
  {
    v19 = GetLastError();
    v20 = v19;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Eu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v19);
    }
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    HrException::HrException(&v41, v20);
    throw &v41;
  }
  if ( !WinHttpReceiveResponse(v15, 0) )
  {
    v21 = GetLastError();
    v22 = v21;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Fu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v21);
    }
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    HrException::HrException(&v41, v22);
    throw &v41;
  }
  statusCode = 0;
  statusCodeSize = 4;
  if ( !WinHttpQueryHeaders(v15, 0x20000013u, 0, &statusCode, &statusCodeSize, 0) )
  {
    v23 = GetLastError();
    v24 = v23;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v23);
    }
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    HrException::HrException(&v41, v24);
    throw &v41;
  }
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x21u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, statusCode);
    v25 = WPP_GLOBAL_Control;
  }
  if ( statusCode != 200 )
  {
    if ( statusCode == 401 )
    {
      v26 = -2147024891;
    }
    else if ( statusCode == 404 || statusCode == 410 )
    {
      v26 = -2147024894;
    }
    else
    {
      v26 = -2147418113;
    }
    if ( v25 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v25->ReserveSpace[28] & 2) != 0 )
      WPP_SF_d(v25->Control.Logger, 0x22u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v26);
    HrException::HrException(&v41, v26);
    throw &v41;
  }
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  memset(&tmp, 0, sizeof(tmp));
  std::vector<unsigned char>::vector<unsigned char>(&tmp, 0x2000u, v27);
  do
  {
    bytesAvailable = 0;
    if ( !WinHttpQueryDataAvailable(v15, &bytesAvailable) )
    {
      v39 = GetLastError();
      v40 = v39;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x23u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v39);
      }
      if ( v40 > 0 )
        v40 = (unsigned __int16)v40 | 0x80070000;
      HrException::HrException(&v41, v40);
      throw &v41;
    }
    v28 = (char *)result->_Mypair._Myval2._Mylast - (char *)result->_Mypair._Myval2._Myfirst;
    v29 = bytesAvailable;
    v30 = bytesAvailable + v28;
    if ( v30 < v28 || v30 > this->m_downloadLimit )
    {
      HrException::HrException(&v41, -2147024774);
      throw &v41;
    }
    if ( !bytesAvailable )
      break;
    Mylast = tmp._Mypair._Myval2._Mylast;
    if ( (unsigned __int8 *)bytesAvailable >= (unsigned __int8 *)(tmp._Mypair._Myval2._Mylast
                                                                - tmp._Mypair._Myval2._Myfirst) )
    {
      if ( (unsigned __int8 *)bytesAvailable <= (unsigned __int8 *)(tmp._Mypair._Myval2._Mylast
                                                                  - tmp._Mypair._Myval2._Myfirst) )
        goto LABEL_83;
      if ( (unsigned __int8 *)bytesAvailable > (unsigned __int8 *)(tmp._Mypair._Myval2._Myend
                                                                 - tmp._Mypair._Myval2._Myfirst) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
          &tmp,
          bytesAvailable,
          (const std::_Value_init_tag *)bytesAvailable);
        LODWORD(Mylast) = tmp._Mypair._Myval2._Mylast;
        v29 = bytesAvailable;
        goto LABEL_83;
      }
      v32 = bytesAvailable - (unsigned __int64)(tmp._Mypair._Myval2._Mylast - tmp._Mypair._Myval2._Myfirst);
      memset_0(tmp._Mypair._Myval2._Mylast, 0, v32);
      Mylast += v32;
      v29 = bytesAvailable;
    }
    else
    {
      Mylast = &tmp._Mypair._Myval2._Myfirst[bytesAvailable];
    }
    tmp._Mypair._Myval2._Mylast = Mylast;
LABEL_83:
    bytesRead = (_DWORD)Mylast - LODWORD(tmp._Mypair._Myval2._Myfirst);
    if ( !WinHttpReadData(v15, tmp._Mypair._Myval2._Myfirst, v29, &bytesRead) )
    {
      v37 = GetLastError();
      v38 = v37;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v37);
      }
      if ( v38 > 0 )
        v38 = (unsigned __int16)v38 | 0x80070000;
      HrException::HrException(&v41, v38);
      throw &v41;
    }
    v34 = tmp._Mypair._Myval2._Mylast;
    if ( (unsigned __int8 *)bytesRead < (unsigned __int8 *)(tmp._Mypair._Myval2._Mylast - tmp._Mypair._Myval2._Myfirst) )
    {
      v34 = &tmp._Mypair._Myval2._Myfirst[bytesRead];
LABEL_90:
      tmp._Mypair._Myval2._Mylast = v34;
      goto LABEL_91;
    }
    if ( (unsigned __int8 *)bytesRead > (unsigned __int8 *)(tmp._Mypair._Myval2._Mylast - tmp._Mypair._Myval2._Myfirst) )
    {
      if ( (unsigned __int8 *)bytesRead <= (unsigned __int8 *)(tmp._Mypair._Myval2._Myend - tmp._Mypair._Myval2._Myfirst) )
      {
        v35 = bytesRead - (unsigned __int64)(tmp._Mypair._Myval2._Mylast - tmp._Mypair._Myval2._Myfirst);
        memset_0(tmp._Mypair._Myval2._Mylast, 0, v35);
        v34 += v35;
        goto LABEL_90;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&tmp, bytesRead, v33);
      v34 = tmp._Mypair._Myval2._Mylast;
    }
LABEL_91:
    std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(
      (std::vector<unsigned char> *)result,
      (std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned char> > >)result->_Mypair._Myval2._Mylast,
      tmp._Mypair._Myval2._Myfirst,
      v34 - tmp._Mypair._Myval2._Myfirst);
  }
  while ( bytesAvailable );
  std::vector<unsigned char>::_Tidy((std::vector<char> *)&tmp);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&pExceptionObject);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>((ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> *)&options);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v44);
  return result;
}

```

## disassembly

```asm
0x180029168  mov     [rsp-8+arg_10], rbx
0x18002916d  push    rbp
0x18002916e  push    rsi
0x18002916f  push    rdi
0x180029170  push    r12
0x180029172  push    r13
0x180029174  push    r14
0x180029176  push    r15
0x180029178  lea     rbp, [rsp-30h]
0x18002917d  sub     rsp, 130h
0x180029184  mov     rax, cs:__security_cookie
0x18002918b  xor     rax, rsp
0x18002918e  mov     [rbp+60h+var_38], rax
0x180029192  mov     r14, rdx
0x180029195  mov     r15, this
0x180029198  mov     [rbp+60h+var_A8], rdx
0x18002919c  xor     r12d, r12d
0x18002919f  mov     [rsp+160h+var_120], r12d
0x1800291a4  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800291ab  lea     rdi, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids
0x1800291b2  mov     this, cs:WPP_GLOBAL_Control
0x1800291b9  cmp     this, r13
0x1800291bc  jz      short loc_1800291D5
0x1800291be  test    byte ptr [this+1Ch], 10h
0x1800291c2  jz      short loc_1800291D5
0x1800291c4  lea     edx, [r12+18h]; id
0x1800291c9  mov     r8, rdi; TraceGuid
0x1800291cc  mov     this, [this+10h]; Logger
0x1800291d0  call    WPP_SF_
0x1800291d5  xorps   xmm0, xmm0
0x1800291d8  xor     eax, eax
0x1800291da  movups  xmmword ptr [rbp+60h+proxyInfo.dwAccessType], xmm0
0x1800291de  mov     [rbp+60h+proxyInfo.lpszProxyBypass], rax
0x1800291e2  lea     ecx, [rax+1]
0x1800291e5  mov     [rbp+60h+proxyInfo.dwAccessType], ecx
0x1800291e8  mov     rax, cs:__imp_GlobalFree
0x1800291ef  mov     [rbp+60h+var_C0.dismissed_], cl
0x1800291f2  mov     [rbp+60h+var_C0.fun_], rax
0x1800291f6  mov     [rbp+60h+var_C0.p1_], r12
0x1800291fa  mov     [rbp+60h+j.dismissed_], cl
0x1800291fd  mov     [rbp+60h+j.fun_], rax
0x180029201  mov     [rbp+60h+j.p1_], r12
0x180029205  cmp     [r15+0B3h], r12b
0x18002920c  jz      loc_1800292E3
0x180029212  movdqu  xmmword ptr [rbp+60h+options.lpszAutoConfigUrl], xmm0
0x180029217  mov     [rbp+60h+options.dwReserved], r12d
0x18002921b  mov     [rbp+60h+options.dwFlags], ecx
0x18002921e  mov     [rbp+60h+options.dwAutoDetectFlags], 3
0x180029225  mov     [rbp+60h+options.fAutoLogonIfChallenged], ecx
0x180029228  lea     this, [r15+10h]; this
0x18002922c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029231  lea     r9, [rbp+60h+proxyInfo]; pProxyInfo
0x180029235  lea     r8, [rbp+60h+options]; pAutoProxyOptions
0x180029239  mov     rdx, rax; lpcwszUrl
0x18002923c  mov     this, [r15]; hSession
0x18002923f  call    cs:__imp_WinHttpGetProxyForUrl
0x180029245  test    eax, eax
0x180029247  jnz     short loc_18002928D
0x180029249  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180029250  cmp     rax, r13
0x180029253  jz      short loc_18002928D
0x180029255  test    byte ptr [rax+1Ch], 4
0x180029259  jz      short loc_18002928D
0x18002925b  call    cs:__imp_GetLastError
0x180029261  mov     r8d, eax
0x180029264  lea     this, [r15+10h]; this
0x180029268  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002926d  mov     edx, 19h; id
0x180029272  mov     [rsp+160h+_a2], r8d; _a2
0x180029277  mov     r9, rax; _a1
0x18002927a  mov     r8, rdi; TraceGuid
0x18002927d  mov     this, cs:WPP_GLOBAL_Control
0x180029284  mov     this, [this+10h]; Logger
0x180029288  call    WPP_SF_Sd
0x18002928d  mov     [rbp+60h+bytesRead], 100h
0x180029294  mov     r9d, 4; dwBufferLength
0x18002929a  lea     r8, [rbp+60h+bytesRead]; lpBuffer
0x18002929e  mov     edx, 0C1h; dwOption
0x1800292a3  mov     this, [r15]; hInternet
0x1800292a6  call    cs:__imp_WinHttpSetOption
0x1800292ac  test    eax, eax
0x1800292ae  jnz     short loc_1800292E3
0x1800292b0  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800292b7  cmp     rax, r13
0x1800292ba  jz      short loc_1800292E3
0x1800292bc  test    byte ptr [rax+1Ch], 4
0x1800292c0  jz      short loc_1800292E3
0x1800292c2  call    cs:__imp_GetLastError
0x1800292c8  mov     edx, 1Ah; id
0x1800292cd  mov     r9d, eax; _a1
0x1800292d0  mov     r8, rdi; TraceGuid
0x1800292d3  mov     this, cs:WPP_GLOBAL_Control
0x1800292da  mov     this, [this+10h]; Logger
0x1800292de  call    WPP_SF_d
0x1800292e3  lea     this, [r15+30h]; this
0x1800292e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800292ec  xor     r9d, r9d; dwReserved
0x1800292ef  movzx   r8d, word ptr [r15+0B0h]; nServerPort
0x1800292f7  mov     rdx, rax; pswzServerName
0x1800292fa  mov     this, [r15]; hSession
0x1800292fd  call    cs:__imp_WinHttpConnect
0x180029303  mov     r10, rax
0x180029306  test    rax, rax
0x180029309  jnz     short loc_180029362
0x18002930b  call    cs:__imp_GetLastError
0x180029311  mov     ebx, eax
0x180029313  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002931a  cmp     this, r13
0x18002931d  jz      short loc_180029339
0x18002931f  test    byte ptr [this+1Ch], 2
0x180029323  jz      short loc_180029339
0x180029325  mov     edx, 1Bh; id
0x18002932a  mov     r9d, eax; _a1
0x18002932d  mov     r8, rdi; TraceGuid
0x180029330  mov     this, [this+10h]; Logger
0x180029334  call    WPP_SF_d
0x180029339  test    ebx, ebx
0x18002933b  jle     short loc_180029346
0x18002933d  movzx   ebx, bx
0x180029340  or      ebx, 80070000h
0x180029346  mov     edx, ebx; ErrorCode
0x180029348  lea     this, [rbp+60h+options]; this
0x18002934c  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029351  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x180029358  lea     this, [rbp+60h+options]; pExceptionObject
0x18002935c  call    _CxxThrowException_0
0x180029362  mov     rbx, cs:__imp_WinHttpCloseHandle
0x180029369  mov     byte ptr [rbp+60h+options.dwFlags], r12b
0x18002936d  mov     [rbp+60h+options.lpszAutoConfigUrl], rbx
0x180029371  mov     [rbp+60h+options.lpvReserved], r10
0x180029375  lea     this, [r15+50h]; this
0x180029379  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002937e  mov     r8, rax; pwszObjectName
0x180029381  mov     al, [r15+0B2h]
0x180029388  neg     al
0x18002938a  sbb     ecx, ecx
0x18002938c  and     ecx, 800000h
0x180029392  mov     [rsp+160h+dwFlags], ecx; dwFlags
0x180029396  mov     [rsp+160h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x18002939b  mov     qword ptr [rsp+160h+_a2], r12; pwszReferrer
0x1800293a0  xor     r9d, r9d; pwszVersion
0x1800293a3  lea     rdx, pwszVerb; "GET"
0x1800293aa  mov     this, r10; hConnect
0x1800293ad  call    cs:__imp_WinHttpOpenRequest
0x1800293b3  mov     rsi, rax
0x1800293b6  test    rax, rax
0x1800293b9  jnz     short loc_180029412
0x1800293bb  call    cs:__imp_GetLastError
0x1800293c1  mov     ebx, eax
0x1800293c3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800293ca  cmp     this, r13
0x1800293cd  jz      short loc_1800293E7
0x1800293cf  test    byte ptr [this+1Ch], 2
0x1800293d3  jz      short loc_1800293E7
0x1800293d5  lea     edx, [rsi+1Ch]; id
0x1800293d8  mov     r9d, eax; _a1
0x1800293db  mov     r8, rdi; TraceGuid
0x1800293de  mov     this, [this+10h]; Logger
0x1800293e2  call    WPP_SF_d
0x1800293e7  test    ebx, ebx
0x1800293e9  jle     short loc_1800293F4
0x1800293eb  movzx   ebx, bx
0x1800293ee  or      ebx, 80070000h
0x1800293f4  mov     edx, ebx; ErrorCode
0x1800293f6  lea     this, [rsp+160h+pExceptionObject]; this
0x1800293fb  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029400  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x180029407  lea     this, [rsp+160h+pExceptionObject]; pExceptionObject
0x18002940c  call    _CxxThrowException_0
0x180029412  mov     byte ptr [rsp+160h+pExceptionObject.__vftable], r12b
0x180029417  mov     [rsp+160h+pExceptionObject._Data._What], rbx
0x18002941c  mov     qword ptr [rsp+160h+pExceptionObject._Data._DoFree], rsi
0x180029421  cmp     [rbp+60h+proxyInfo.dwAccessType], 3
0x180029425  jnz     short loc_180029475
0x180029427  mov     r9d, 18h; dwBufferLength
0x18002942d  lea     r8, [rbp+60h+proxyInfo]; lpBuffer
0x180029431  lea     edx, [r9+0Eh]; dwOption
0x180029435  mov     this, rsi; hInternet
0x180029438  call    cs:__imp_WinHttpSetOption
0x18002943e  test    eax, eax
0x180029440  jnz     short loc_180029475
0x180029442  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180029449  cmp     rax, r13
0x18002944c  jz      short loc_180029475
0x18002944e  test    byte ptr [rax+1Ch], 4
0x180029452  jz      short loc_180029475
0x180029454  call    cs:__imp_GetLastError
0x18002945a  mov     edx, 1Dh; id
0x18002945f  mov     r9d, eax; _a1
0x180029462  mov     r8, rdi; TraceGuid
0x180029465  mov     this, cs:WPP_GLOBAL_Control
0x18002946c  mov     this, [this+10h]; Logger
0x180029470  call    WPP_SF_d
0x180029475  lea     r8, [r15+70h]; Str
0x180029479  cmp     [r8+10h], r12
0x18002947d  jz      short loc_18002948C
0x18002947f  mov     edx, 1000h; Option
0x180029484  mov     this, rsi; hInternet
0x180029487  call    ?SetStringOption@@YAXPEAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SetStringOption(void *,ulong,std::wstring const &)
0x18002948c  lea     r8, [r15+90h]; Str
0x180029493  cmp     [r8+10h], r12
0x180029497  jz      short loc_1800294A6
0x180029499  mov     edx, 1001h; Option
0x18002949e  mov     this, rsi; hInternet
0x1800294a1  call    ?SetStringOption@@YAXPEAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SetStringOption(void *,ulong,std::wstring const &)
0x1800294a6  mov     qword ptr [rsp+160h+dwFlags], r12; dwContext
0x1800294ab  mov     dword ptr [rsp+160h+ppwszAcceptTypes], r12d; dwTotalLength
0x1800294b0  mov     [rsp+160h+_a2], r12d; dwOptionalLength
0x1800294b5  xor     r9d, r9d; lpOptional
0x1800294b8  xor     r8d, r8d; dwHeadersLength
0x1800294bb  xor     edx, edx; lpszHeaders
0x1800294bd  mov     this, rsi; hRequest
0x1800294c0  call    cs:__imp_WinHttpSendRequest
0x1800294c6  test    eax, eax
0x1800294c8  jnz     short loc_180029523
0x1800294ca  call    cs:__imp_GetLastError
0x1800294d0  mov     ebx, eax
0x1800294d2  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800294d9  cmp     this, r13
0x1800294dc  jz      short loc_1800294F8
0x1800294de  test    byte ptr [this+1Ch], 2
0x1800294e2  jz      short loc_1800294F8
0x1800294e4  mov     edx, 1Eh; id
0x1800294e9  mov     r9d, eax; _a1
0x1800294ec  mov     r8, rdi; TraceGuid
0x1800294ef  mov     this, [this+10h]; Logger
0x1800294f3  call    WPP_SF_d
0x1800294f8  test    ebx, ebx
0x1800294fa  jle     short loc_180029505
0x1800294fc  movzx   ebx, bx
0x1800294ff  or      ebx, 80070000h
0x180029505  mov     edx, ebx; ErrorCode
0x180029507  lea     this, [rsp+160h+var_118]; this
0x18002950c  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029511  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x180029518  lea     this, [rsp+160h+var_118]; pExceptionObject
0x18002951d  call    _CxxThrowException_0
0x180029523  xor     edx, edx; lpReserved
0x180029525  mov     this, rsi; hRequest
0x180029528  call    cs:__imp_WinHttpReceiveResponse
0x18002952e  test    eax, eax
0x180029530  jnz     short loc_18002958B
0x180029532  call    cs:__imp_GetLastError
0x180029538  mov     ebx, eax
0x18002953a  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180029541  cmp     this, r13
0x180029544  jz      short loc_180029560
0x180029546  test    byte ptr [this+1Ch], 2
0x18002954a  jz      short loc_180029560
0x18002954c  mov     edx, 1Fh; id
0x180029551  mov     r9d, eax; _a1
0x180029554  mov     r8, rdi; TraceGuid
0x180029557  mov     this, [this+10h]; Logger
0x18002955b  call    WPP_SF_d
0x180029560  test    ebx, ebx
0x180029562  jle     short loc_18002956D
0x180029564  movzx   ebx, bx
0x180029567  or      ebx, 80070000h
0x18002956d  mov     edx, ebx; ErrorCode
0x18002956f  lea     this, [rsp+160h+var_118]; this
0x180029574  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029579  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x180029580  lea     this, [rsp+160h+var_118]; pExceptionObject
0x180029585  call    _CxxThrowException_0
0x18002958b  mov     [rbp+60h+statusCode], r12d
0x18002958f  mov     [rbp+60h+statusCodeSize], 4
0x180029596  mov     [rsp+160h+ppwszAcceptTypes], r12; lpdwIndex
0x18002959b  lea     rax, [rbp+60h+statusCodeSize]
0x18002959f  mov     qword ptr [rsp+160h+_a2], rax; lpdwBufferLength
0x1800295a4  lea     r9, [rbp+60h+statusCode]; lpBuffer
0x1800295a8  xor     r8d, r8d; pwszName
0x1800295ab  mov     edx, 20000013h; dwInfoLevel
0x1800295b0  mov     this, rsi; hRequest
0x1800295b3  call    cs:__imp_WinHttpQueryHeaders
0x1800295b9  test    eax, eax
0x1800295bb  jnz     short loc_180029616
0x1800295bd  call    cs:__imp_GetLastError
0x1800295c3  mov     ebx, eax
0x1800295c5  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800295cc  cmp     this, r13
0x1800295cf  jz      short loc_1800295EB
0x1800295d1  test    byte ptr [this+1Ch], 2
0x1800295d5  jz      short loc_1800295EB
0x1800295d7  mov     edx, 20h ; ' '; id
0x1800295dc  mov     r9d, eax; _a1
0x1800295df  mov     r8, rdi; TraceGuid
0x1800295e2  mov     this, [this+10h]; Logger
0x1800295e6  call    WPP_SF_d
0x1800295eb  test    ebx, ebx
0x1800295ed  jle     short loc_1800295F8
0x1800295ef  movzx   ebx, bx
0x1800295f2  or      ebx, 80070000h
0x1800295f8  mov     edx, ebx; ErrorCode
0x1800295fa  lea     this, [rsp+160h+var_118]; this
0x1800295ff  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029604  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x18002960b  lea     this, [rsp+160h+var_118]; pExceptionObject
0x180029610  call    _CxxThrowException_0
0x180029616  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002961d  cmp     this, r13
  ... truncated ...
```
