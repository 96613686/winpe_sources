# Http::Request::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029954`
- end: `0x180029d63`
- name: `?Initialize@Request@Http@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1039`
- prototype: `void __fastcall(Http::Request *this, const std::wstring *Url)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180028ff4`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x1800032f4`
- `0x180011844`
- `0x180011cfc`
- `0x180011fdc`
- `0x180012040`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180013bdc`
- `0x18001a124`
- `0x180028ef0`
- `0x180028f64`
- `0x180029954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cd5`
- `WINHTTP!WinHttpOpen` at `0x180029cc7`
- `WINHTTP!WinHttpOpen` at `0x180029cc7`
- `WINHTTP!WinHttpCrackUrl` at `0x180029a1c`
- `WINHTTP!WinHttpCrackUrl` at `0x180029a1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Http::Request::Initialize(Http::Request *this, const std::wstring *Url)
{
  const WCHAR *v4; // rax
  DWORD LastError; // eax
  HRESULT v6; // edi
  const wchar_t *v7; // rax
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r8
  unsigned __int16 v10; // r9
  unsigned __int64 v11; // rax
  WPP_PROJECT_CONTROL_BLOCK *v12; // r10
  const wchar_t *v13; // rax
  __int64 v14; // r10
  const wchar_t *v15; // rax
  __int64 v16; // r10
  const wchar_t *v17; // rax
  __int64 v18; // r10
  const wchar_t *v19; // rax
  __int64 v20; // r10
  HINTERNET v21; // rax
  DWORD v22; // eax
  HRESULT v23; // edi
  HrException pExceptionObject; // [rsp+30h] [rbp-89h] BYREF
  _WINHTTP_URL_COMPONENTS urlComponents; // [rsp+50h] [rbp-69h] BYREF
  std::wstring extraInfo; // [rsp+C0h] [rbp+7h] BYREF

  if ( !Url->_Mypair._Myval2._Mysize )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids);
    }
    HrException::HrException(&pExceptionObject, -2147024809);
    throw &pExceptionObject;
  }
  memset_0(&urlComponents, 0, sizeof(urlComponents));
  urlComponents.dwStructSize = 104;
  urlComponents.dwSchemeLength = -1;
  urlComponents.dwHostNameLength = -1;
  urlComponents.dwUserNameLength = -1;
  urlComponents.dwPasswordLength = -1;
  urlComponents.dwUrlPathLength = -1;
  urlComponents.dwExtraInfoLength = -1;
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Url->_Mypair._Myval2);
  if ( !WinHttpCrackUrl(v4, Url->_Mypair._Myval2._Mysize, 0, &urlComponents) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, LastError);
    }
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    HrException::HrException(&pExceptionObject, v6);
    throw &pExceptionObject;
  }
  if ( (unsigned int)(urlComponents.nScheme - 1) > 1 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids);
    }
    HrException::HrException(&pExceptionObject, -2147012890);
    throw &pExceptionObject;
  }
  std::wstring::assign(&this->m_host, urlComponents.lpszHostName, urlComponents.dwHostNameLength);
  std::wstring::assign(&this->m_username, urlComponents.lpszUserName, urlComponents.dwUserNameLength);
  std::wstring::assign(&this->m_password, urlComponents.lpszPassword, urlComponents.dwPasswordLength);
  std::wstring::assign(&this->m_path, urlComponents.lpszUrlPath, urlComponents.dwUrlPathLength);
  this->m_port = urlComponents.nPort;
  this->m_secure = urlComponents.nScheme == 2;
  std::wstring::wstring(&extraInfo, urlComponents.lpszExtraInfo, urlComponents.dwExtraInfoLength);
  if ( extraInfo._Mypair._Myval2._Mysize
    && *std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&extraInfo._Mypair._Myval2) == 63 )
  {
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&extraInfo._Mypair._Myval2);
    v11 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v7, v8, v9, v10);
    if ( v11 != -1 )
      std::wstring::erase(&extraInfo, v11);
    std::wstring::append(&this->m_path, &extraInfo);
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_host._Mypair._Myval2);
      WPP_SF_S(*(_QWORD *)(v14 + 16), 0xFu, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v13);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      if ( (v12->ReserveSpace[28] & 0x10) != 0 )
      {
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_username._Mypair._Myval2);
        WPP_SF_S(*(_QWORD *)(v16 + 16), 0x10u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v15);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        if ( (v12->ReserveSpace[28] & 0x10) != 0 )
        {
          v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_password._Mypair._Myval2);
          WPP_SF_S(*(_QWORD *)(v18 + 16), 0x11u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v17);
          v12 = WPP_GLOBAL_Control;
        }
        if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          if ( (v12->ReserveSpace[28] & 0x10) != 0 )
          {
            v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_path._Mypair._Myval2);
            WPP_SF_S(*(_QWORD *)(v20 + 16), 0x12u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v19);
            v12 = WPP_GLOBAL_Control;
          }
          if ( v12 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v12->ReserveSpace[28] & 0x10) != 0 )
            WPP_SF_d(v12->Control.Logger, 0x13u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, this->m_port);
        }
      }
    }
  }
  v21 = WinHttpOpen(L"MSPROV", 0, 0, 0, 0);
  this->m_session = v21;
  if ( !v21 )
  {
    v22 = GetLastError();
    v23 = v22;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids, v22);
    }
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    HrException::HrException(&pExceptionObject, v23);
    throw &pExceptionObject;
  }
  std::wstring::_Tidy_deallocate(&extraInfo);
}

```

## disassembly

```asm
0x180029954  mov     [rsp-8+arg_10], rbx
0x180029959  mov     [rsp-8+arg_18], rsi
0x18002995e  push    rbp
0x18002995f  push    rdi
0x180029960  push    r12
0x180029962  push    r14
0x180029964  push    r15
0x180029966  lea     rbp, [rsp-37h]
0x18002996b  sub     rsp, 0F0h
0x180029972  mov     rax, cs:__security_cookie
0x180029979  xor     rax, rsp
0x18002997c  mov     [rbp+57h+var_30], rax
0x180029980  mov     rbx, Url
0x180029983  mov     rdi, this
0x180029986  cmp     qword ptr [Url+10h], 0
0x18002998b  jnz     short loc_1800299DC
0x18002998d  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180029994  mov     this, cs:WPP_GLOBAL_Control
0x18002999b  cmp     this, rbx
0x18002999e  jz      short loc_1800299BB
0x1800299a0  test    byte ptr [this+1Ch], 2
0x1800299a4  jz      short loc_1800299BB
0x1800299a6  mov     edx, 0Ch; id
0x1800299ab  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x1800299b2  mov     this, [this+10h]; Logger
0x1800299b6  call    WPP_SF_
0x1800299bb  mov     edx, 80070057h; ErrorCode
0x1800299c0  lea     this, [rsp+110h+pExceptionObject]; this
0x1800299c5  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x1800299ca  lea     Url, _TI2?AVHrException@@; pThrowInfo
0x1800299d1  lea     this, [rsp+110h+pExceptionObject]; pExceptionObject
0x1800299d6  call    _CxxThrowException_0
0x1800299dc  mov     esi, 68h ; 'h'
0x1800299e1  mov     r8d, esi; Size
0x1800299e4  xor     edx, edx; Val
0x1800299e6  lea     this, [rbp+57h+urlComponents]; void *
0x1800299ea  call    memset_0
0x1800299ef  mov     [rbp+57h+urlComponents.dwStructSize], esi
0x1800299f2  or      eax, 0FFFFFFFFh
0x1800299f5  mov     [rbp+57h+urlComponents.dwSchemeLength], eax
0x1800299f8  mov     [rbp+57h+urlComponents.dwHostNameLength], eax
0x1800299fb  mov     [rbp+57h+urlComponents.dwUserNameLength], eax
0x1800299fe  mov     [rbp+57h+urlComponents.dwPasswordLength], eax
0x180029a01  mov     [rbp+57h+urlComponents.dwUrlPathLength], eax
0x180029a04  mov     [rbp+57h+urlComponents.dwExtraInfoLength], eax
0x180029a07  mov     this, rbx; this
0x180029a0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029a0f  lea     r9, [rbp+57h+urlComponents]; lpUrlComponents
0x180029a13  xor     r8d, r8d; dwFlags
0x180029a16  mov     edx, [rbx+10h]; dwUrlLength
0x180029a19  mov     this, rax; pwszUrl
0x180029a1c  call    cs:__imp_WinHttpCrackUrl
0x180029a22  test    eax, eax
0x180029a24  jnz     short loc_180029A88
0x180029a26  call    cs:__imp_GetLastError
0x180029a2c  mov     edi, eax
0x180029a2e  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180029a35  mov     this, cs:WPP_GLOBAL_Control
0x180029a3c  cmp     this, rbx
0x180029a3f  jz      short loc_180029A5D
0x180029a41  test    byte ptr [this+1Ch], 2
0x180029a45  jz      short loc_180029A5D
0x180029a47  lea     edx, [rsi-5Bh]; id
0x180029a4a  mov     r9d, eax; _a1
0x180029a4d  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029a54  mov     this, [this+10h]; Logger
0x180029a58  call    WPP_SF_d
0x180029a5d  test    edi, edi
0x180029a5f  jle     short loc_180029A6A
0x180029a61  movzx   edi, di
0x180029a64  or      edi, 80070000h
0x180029a6a  mov     edx, edi; ErrorCode
0x180029a6c  lea     this, [rsp+110h+pExceptionObject]; this
0x180029a71  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029a76  lea     Url, _TI2?AVHrException@@; pThrowInfo
0x180029a7d  lea     this, [rsp+110h+pExceptionObject]; pExceptionObject
0x180029a82  call    _CxxThrowException_0
0x180029a88  mov     eax, [rbp+57h+urlComponents.nScheme]
0x180029a8b  dec     eax
0x180029a8d  cmp     eax, 1
0x180029a90  jbe     short loc_180029AE1
0x180029a92  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180029a99  mov     this, cs:WPP_GLOBAL_Control
0x180029aa0  cmp     this, rbx
0x180029aa3  jz      short loc_180029AC0
0x180029aa5  test    byte ptr [this+1Ch], 2
0x180029aa9  jz      short loc_180029AC0
0x180029aab  mov     edx, 0Eh; id
0x180029ab0  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029ab7  mov     this, [this+10h]; Logger
0x180029abb  call    WPP_SF_
0x180029ac0  mov     edx, 80072EE6h; ErrorCode
0x180029ac5  lea     this, [rsp+110h+pExceptionObject]; this
0x180029aca  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029acf  lea     Url, _TI2?AVHrException@@; pThrowInfo
0x180029ad6  lea     this, [rsp+110h+pExceptionObject]; pExceptionObject
0x180029adb  call    _CxxThrowException_0
0x180029ae1  mov     r8d, [rbp+57h+urlComponents.dwHostNameLength]; _Count
0x180029ae5  mov     Url, [rbp+57h+urlComponents.lpszHostName]; _Ptr
0x180029ae9  lea     this, [rdi+30h]; this
0x180029aed  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180029af2  mov     r8d, [rbp+57h+urlComponents.dwUserNameLength]; _Count
0x180029af6  mov     Url, [rbp+57h+urlComponents.lpszUserName]; _Ptr
0x180029afa  lea     this, [rdi+70h]; this
0x180029afe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180029b03  lea     r12, [rdi+90h]
0x180029b0a  mov     r8d, [rbp+57h+urlComponents.dwPasswordLength]; _Count
0x180029b0e  mov     Url, [rbp+57h+urlComponents.lpszPassword]; _Ptr
0x180029b12  mov     this, r12; this
0x180029b15  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180029b1a  lea     rsi, [rdi+50h]
0x180029b1e  mov     r8d, [rbp+57h+urlComponents.dwUrlPathLength]; _Count
0x180029b22  mov     Url, [rbp+57h+urlComponents.lpszUrlPath]; _Ptr
0x180029b26  mov     this, rsi; this
0x180029b29  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180029b2e  movzx   eax, [rbp+57h+urlComponents.nPort]
0x180029b32  mov     [rdi+0B0h], ax
0x180029b39  cmp     [rbp+57h+urlComponents.nScheme], 2
0x180029b3d  setz    al
0x180029b40  mov     [rdi+0B2h], al
0x180029b46  mov     r8d, [rbp+57h+urlComponents.dwExtraInfoLength]; _Count
0x180029b4a  mov     Url, [rbp+57h+urlComponents.lpszExtraInfo]; _Ptr
0x180029b4e  lea     this, [rbp+57h+extraInfo]; this
0x180029b52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180029b57  nop
0x180029b58  mov     Url, [rbp+57h+extraInfo._Mypair._Myval2._Mysize]
0x180029b5c  test    Url, Url
0x180029b5f  jz      short loc_180029B9F
0x180029b61  lea     this, [rbp+57h+extraInfo]; this
0x180029b65  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029b6a  cmp     word ptr [rax], 3Fh ; '?'
0x180029b6e  jnz     short loc_180029B9F
0x180029b70  lea     this, [rbp+57h+extraInfo]; this
0x180029b74  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029b79  mov     this, rax; _Haystack
0x180029b7c  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180029b81  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029b85  jz      short loc_180029B93
0x180029b87  mov     Url, rax; _Off
0x180029b8a  lea     this, [rbp+57h+extraInfo]; this
0x180029b8e  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K@Z; std::wstring::erase(unsigned __int64)
0x180029b93  lea     Url, [rbp+57h+extraInfo]; _Right
0x180029b97  mov     this, rsi; this
0x180029b9a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180029b9f  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180029ba6  mov     r10, cs:WPP_GLOBAL_Control
0x180029bad  cmp     r10, rbx
0x180029bb0  jz      loc_180029CB0
0x180029bb6  test    byte ptr [r10+1Ch], 10h
0x180029bbb  jz      short loc_180029BE5
0x180029bbd  lea     this, [rdi+30h]; this
0x180029bc1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029bc6  mov     edx, 0Fh; id
0x180029bcb  mov     r9, rax; _a1
0x180029bce  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029bd5  mov     this, [r10+10h]; Logger
0x180029bd9  call    WPP_SF_S
0x180029bde  mov     r10, cs:WPP_GLOBAL_Control
0x180029be5  cmp     r10, rbx; __annotation("TMF:",
0x180029be8  jz      loc_180029CB0
0x180029bee  test    byte ptr [r10+1Ch], 10h
0x180029bf3  jz      short loc_180029C1D
0x180029bf5  lea     this, [rdi+70h]; this
0x180029bf9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029bfe  mov     edx, 10h; id
0x180029c03  mov     r9, rax; _a1
0x180029c06  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029c0d  mov     this, [r10+10h]; Logger
0x180029c11  call    WPP_SF_S
0x180029c16  mov     r10, cs:WPP_GLOBAL_Control
0x180029c1d  cmp     r10, rbx; __annotation("TMF:",
0x180029c20  jz      loc_180029CB0
0x180029c26  test    byte ptr [r10+1Ch], 10h
0x180029c2b  jz      short loc_180029C54
0x180029c2d  mov     this, r12; this
0x180029c30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029c35  mov     edx, 11h; id
0x180029c3a  mov     r9, rax; _a1
0x180029c3d  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029c44  mov     this, [r10+10h]; Logger
0x180029c48  call    WPP_SF_S
0x180029c4d  mov     r10, cs:WPP_GLOBAL_Control
0x180029c54  cmp     r10, rbx; __annotation("TMF:",
0x180029c57  jz      short loc_180029CB0
0x180029c59  test    byte ptr [r10+1Ch], 10h
0x180029c5e  jz      short loc_180029C87
0x180029c60  mov     this, rsi; this
0x180029c63  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029c68  mov     edx, 12h; id
0x180029c6d  mov     r9, rax; _a1
0x180029c70  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029c77  mov     this, [r10+10h]; Logger
0x180029c7b  call    WPP_SF_S
0x180029c80  mov     r10, cs:WPP_GLOBAL_Control
0x180029c87  cmp     r10, rbx; __annotation("TMF:",
0x180029c8a  jz      short loc_180029CB0
0x180029c8c  test    byte ptr [r10+1Ch], 10h
0x180029c91  jz      short loc_180029CB0
0x180029c93  movzx   r9d, word ptr [rdi+0B0h]; _a1
0x180029c9b  mov     edx, 13h; id
0x180029ca0  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029ca7  mov     this, [r10+10h]; Logger
0x180029cab  call    WPP_SF_d
0x180029cb0  mov     [rsp+110h+dwFlags], 0; dwFlags
0x180029cb8  xor     r9d, r9d; pszProxyBypassW
0x180029cbb  xor     r8d, r8d; pszProxyW
0x180029cbe  xor     edx, edx; dwAccessType
0x180029cc0  lea     this, pszAgentW; "MSPROV"
0x180029cc7  call    cs:__imp_WinHttpOpen
0x180029ccd  mov     [rdi], rax
0x180029cd0  test    rax, rax
0x180029cd3  jnz     short loc_180029D32
0x180029cd5  call    cs:__imp_GetLastError
0x180029cdb  mov     edi, eax
0x180029cdd  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180029ce4  cmp     this, rbx
0x180029ce7  jz      short loc_180029D07
0x180029ce9  test    byte ptr [this+1Ch], 2
0x180029ced  jz      short loc_180029D07
0x180029cef  mov     edx, 14h; id
0x180029cf4  mov     r9d, eax; _a1
0x180029cf7  lea     r8, WPP_24244ae679273d0a4ac5be0b7d145c98_Traceguids; TraceGuid
0x180029cfe  mov     this, [this+10h]; Logger
0x180029d02  call    WPP_SF_d
0x180029d07  test    edi, edi
0x180029d09  jle     short loc_180029D14
0x180029d0b  movzx   edi, di
0x180029d0e  or      edi, 80070000h
0x180029d14  mov     edx, edi; ErrorCode
0x180029d16  lea     this, [rsp+110h+pExceptionObject]; this
0x180029d1b  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x180029d20  lea     Url, _TI2?AVHrException@@; pThrowInfo
0x180029d27  lea     this, [rsp+110h+pExceptionObject]; pExceptionObject
0x180029d2c  call    _CxxThrowException_0
0x180029d32  lea     this, [rbp+57h+extraInfo]; this
0x180029d36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029d3b  mov     this, [rbp+57h+var_30]
0x180029d3f  xor     this, rsp; StackCookie
0x180029d42  call    __security_check_cookie
0x180029d47  lea     r11, [rsp+110h+var_20]
0x180029d4f  mov     rbx, [r11+40h]
0x180029d53  mov     rsi, [r11+48h]
0x180029d57  mov     rsp, r11
0x180029d5a  pop     r15
0x180029d5c  pop     r14
0x180029d5e  pop     r12
0x180029d60  pop     rdi
0x180029d61  pop     rbp
0x180029d62  retn
```
