# CHttpBase::HandlePostRedirects(ushort const *)

- ea: `0x180045c78`
- end: `0x18004617e`
- name: `?HandlePostRedirects@CHttpBase@@IEAAJPEBG@Z`
- size: `1286`
- prototype: `__int64 __fastcall(CHttpBase *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180046c7c`

## callees

- `0x180001284`
- `0x180001290`
- `0x1800046c8`
- `0x180015438`
- `0x180043964`
- `0x180043ab0`
- `0x180044828`
- `0x1800454ec`
- `0x180045c78`
- `0x180046184`
- `0x1800463f4`
- `0x180046d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045d39`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f85`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004612a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004612a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045ce7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045ce7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045d73`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045dfe`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045d73`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180045dfe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180045f06`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180045f7b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180045f06`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180045f7b`

## string_xrefs

- `0x180045fb3`: `[msdrm]:Posting token to %ws\n`
- `0x1800460a8`: `[msdrm]:HandlePostRedirects: m_wszLastRequestURI: %ws\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CHttpBase::HandlePostRedirects(CHttpBase *this, const unsigned __int16 *a2)
{
  OLECHAR *v3; // r15
  unsigned __int8 *v4; // r14
  int DataFromResponse; // ebx
  __int64 v6; // rcx
  void *v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 cchWideChar; // rbx
  unsigned int v11; // eax
  WCHAR *lpWideCharStr; // rax
  __int64 v13; // rcx
  signed int LastError; // eax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r12
  unsigned int v20; // eax
  CHAR *v21; // rax
  __int64 v22; // rcx
  signed int v23; // eax
  int v24; // r12d
  LPCWCH v26; // [rsp+40h] [rbp-78h] BYREF
  WCHAR *v27; // [rsp+48h] [rbp-70h]
  CHAR *v28; // [rsp+50h] [rbp-68h]
  _QWORD *v29; // [rsp+58h] [rbp-60h]
  __int64 v30; // [rsp+60h] [rbp-58h]
  __int64 v31; // [rsp+68h] [rbp-50h]
  int v32; // [rsp+C0h] [rbp+8h]
  __int64 v34; // [rsp+D0h] [rbp+18h]
  void *Block; // [rsp+D8h] [rbp+20h] BYREF

  v31 = -2;
  v32 = 0;
  Block = 0;
  v26 = 0;
  v3 = 0;
  v27 = 0;
  v4 = 0;
  v28 = 0;
  v29 = (_QWORD *)((char *)this + 48);
  v34 = *((_QWORD *)this + 6);
  v30 = v34;
  _RTLTRACE("+[msdrm]:CHttpBase::HandlePostRedirects\n");
  DataFromResponse = CoInitializeEx(0, 2u);
  if ( DataFromResponse >= 0 )
  {
    v32 = 1;
    v24 = CheckForPostForm(*((_QWORD *)this + 16), *((unsigned int *)this + 34));
    while ( v24 == 1 )
    {
      v7 = (void *)*((_QWORD *)this + 10);
      if ( v7 && !WaitForSingleObject(v7, 0) )
      {
        DataFromResponse = -2147168447;
        v6 = v34;
        goto LABEL_43;
      }
      v8 = MultiByteToWideChar(0xFDE9u, 0, *((LPCCH *)this + 16), *((_DWORD *)this + 34), 0, 0);
      cchWideChar = (unsigned int)v8;
      if ( v8 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
      v11 = v8 + 1;
      if ( (unsigned __int64)(cchWideChar + 1) > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0xFFFFFFFFLL);
      lpWideCharStr = (WCHAR *)operator new[](saturated_mul(v11, 2u));
      v3 = lpWideCharStr;
      v27 = lpWideCharStr;
      if ( !lpWideCharStr )
      {
        DataFromResponse = -2147024882;
        v6 = v34;
        goto LABEL_43;
      }
      if ( (unsigned int)cchWideChar > 0x7FFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v13);
      if ( !MultiByteToWideChar(0xFDE9u, 0, *((LPCCH *)this + 16), *((_DWORD *)this + 34), lpWideCharStr, cchWideChar) )
      {
        _RTLTRACE("[msdrm]:MultiByte Error\n");
        LastError = GetLastError();
        DataFromResponse = LastError;
        if ( LastError > 0 )
          DataFromResponse = (unsigned __int16)LastError | 0x80070000;
        v6 = v34;
        goto LABEL_43;
      }
      v3[cchWideChar] = 0;
      DataFromResponse = GetDataFromResponse(v3, (unsigned __int16 **)&Block, (unsigned __int16 **)&v26);
      if ( DataFromResponse < 0 )
      {
        v6 = v34;
        goto LABEL_43;
      }
      *((_DWORD *)this + 10) &= ~2u;
      *((_QWORD *)this + 1) = 0;
      *((_DWORD *)this + 35) = 0;
      *v29 = L"Content-Type: application/x-www-form-urlencoded";
      DataFromResponse = CHttpBase::CloseHttpRequest(this);
      if ( DataFromResponse < 0 )
      {
        v6 = v34;
        goto LABEL_43;
      }
      DataFromResponse = CHttpBase::InitializeHttpRequest(this, (const unsigned __int16 *)Block);
      if ( DataFromResponse < 0 )
      {
        v6 = v34;
        goto LABEL_43;
      }
      v16 = -1;
      do
        ++v16;
      while ( v26[v16] );
      if ( v16 > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
      if ( (unsigned int)v16 > 0x7FFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v15);
      v17 = WideCharToMultiByte(0xFDE9u, 0, v26, v16, 0, 0, 0, 0);
      v19 = (unsigned int)v17;
      if ( v17 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v18);
      v20 = v17 + 1;
      if ( (unsigned __int64)(v19 + 1) > 0xFFFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v18);
      v21 = (CHAR *)operator new[](v20);
      v4 = (unsigned __int8 *)v21;
      v28 = v21;
      if ( !v21 )
      {
        DataFromResponse = -2147024882;
        v6 = v34;
        goto LABEL_43;
      }
      if ( (unsigned int)v19 > 0x7FFFFFFF )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v22);
      if ( !WideCharToMultiByte(0xFDE9u, 0, v26, v16, v21, v19, 0, 0) )
      {
        v23 = GetLastError();
        DataFromResponse = v23;
        if ( v23 > 0 )
          DataFromResponse = (unsigned __int16)v23 | 0x80070000;
        v6 = v34;
        goto LABEL_43;
      }
      v4[v19] = 0;
      _RTLTRACE("[msdrm]:Posting token to %ws\n", Block);
      DataFromResponse = CHttpBase::SendRequest(this, v4, v19);
      _RTLTRACE("[msdrm]: SendRequest hr = 0x%x, HTTPReturnCode=%d\n", DataFromResponse, *((_DWORD *)this + 30));
      if ( DataFromResponse < 0 )
      {
        v6 = v34;
        goto LABEL_43;
      }
      DataFromResponse = CHttpBase::GetResponse(this);
      if ( DataFromResponse < 0 )
      {
        v6 = v34;
        goto LABEL_43;
      }
      v24 = CheckForPostForm(*((_QWORD *)this + 16), *((unsigned int *)this + 34));
      operator delete(Block);
      Block = 0;
      operator delete((void *)v26);
      v26 = 0;
      operator delete(v3);
      v3 = 0;
      v27 = 0;
      operator delete(v4);
      v4 = 0;
      v28 = 0;
    }
    if ( !(unsigned int)IsResponseFromStartingUrl(a2, *((const unsigned __int16 **)this + 20)) )
    {
      _RTLTRACE("[msdrm]:HandlePostRedirects: When loop ended, response was NOT from starting url.\n");
      _RTLTRACE("[msdrm]:HandlePostRedirects: wszFirstURL: %ws\n", a2);
      _RTLTRACE("[msdrm]:HandlePostRedirects: m_wszLastRequestURI: %ws\n", *((_QWORD *)this + 20));
      DataFromResponse = -2147467259;
    }
    v6 = v34;
  }
  else
  {
    v6 = v34;
  }
LABEL_43:
  *v29 = v6;
  operator delete(Block);
  Block = 0;
  operator delete((void *)v26);
  v26 = 0;
  operator delete(v3);
  operator delete(v4);
  if ( v32 )
    CoUninitialize();
  _RTLTRACE("-[msdrm]:CHttpBase::HandlePostRedirects 0x%x", DataFromResponse);
  return (unsigned int)DataFromResponse;
}

```

## disassembly

```asm
0x180045c78  mov     rax, rsp
0x180045c7b  mov     [rax+10h], rdx
0x180045c7f  push    rbx
0x180045c80  push    rsi
0x180045c81  push    rdi
0x180045c82  push    r12
0x180045c84  push    r13
0x180045c86  push    r14
0x180045c88  push    r15
0x180045c8a  sub     rsp, 80h
0x180045c91  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x180045c99  mov     rsi, rcx
0x180045c9c  xor     edi, edi
0x180045c9e  mov     [rsp+0B8h+arg_0], edi
0x180045ca5  mov     [rax+20h], rdi
0x180045ca9  mov     [rax-78h], rdi
0x180045cad  mov     r15d, edi
0x180045cb0  mov     [rsp+0B8h+var_70], rdi
0x180045cb5  mov     r14d, edi
0x180045cb8  mov     [rsp+0B8h+var_68], rdi
0x180045cbd  lea     rax, [rcx+30h]
0x180045cc1  mov     [rsp+0B8h+var_60], rax
0x180045cc6  mov     rax, [rax]
0x180045cc9  mov     [rsp+0B8h+arg_10], rax
0x180045cd1  mov     [rsp+0B8h+var_58], rax
0x180045cd6  lea     rcx, aMsdrmChttpbase_2; "+[msdrm]:CHttpBase::HandlePostRedirects"...
0x180045cdd  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180045ce2  lea     edx, [rdi+2]; dwCoInit
0x180045ce5  xor     ecx, ecx; pvReserved
0x180045ce7  call    cs:__imp_CoInitializeEx
0x180045ced  mov     ebx, eax
0x180045cef  test    eax, eax
0x180045cf1  jns     short loc_180045D00
0x180045cf3  mov     rcx, [rsp+0B8h+arg_10]
0x180045cfb  jmp     loc_1800460E5
0x180045d00  mov     [rsp+0B8h+arg_0], 1
0x180045d0b  mov     edx, [rsi+88h]
0x180045d11  mov     rcx, [rsi+80h]
0x180045d18  call    ?CheckForPostForm@@YA?AW4_POST_DATA_INFO@@PEBDI@Z; CheckForPostForm(char const *,uint)
0x180045d1d  mov     r12d, eax
0x180045d20  cmp     r12d, [rsp+0B8h+arg_0]
0x180045d28  jnz     loc_18004606B
0x180045d2e  mov     rcx, [rsi+50h]; hHandle
0x180045d32  test    rcx, rcx
0x180045d35  jz      short loc_180045D55
0x180045d37  xor     edx, edx; dwMilliseconds
0x180045d39  call    cs:__imp_WaitForSingleObject
0x180045d3f  test    eax, eax
0x180045d41  jnz     short loc_180045D55
0x180045d43  mov     ebx, 8004CF41h
0x180045d48  mov     rcx, [rsp+0B8h+arg_10]
0x180045d50  jmp     loc_1800460E5
0x180045d55  mov     [rsp+0B8h+cchWideChar], edi; cchWideChar
0x180045d59  mov     [rsp+0B8h+lpWideCharStr], rdi; lpWideCharStr
0x180045d5e  mov     r9d, [rsi+88h]; cbMultiByte
0x180045d65  mov     r8, [rsi+80h]; lpMultiByteStr
0x180045d6c  xor     edx, edx; dwFlags
0x180045d6e  mov     ecx, 0FDE9h; CodePage
0x180045d73  call    cs:__imp_MultiByteToWideChar
0x180045d79  mov     ebx, eax
0x180045d7b  test    eax, eax
0x180045d7d  js      loc_180046153
0x180045d83  lea     rax, [rbx+1]
0x180045d87  mov     ecx, 0FFFFFFFFh
0x180045d8c  cmp     rax, rcx
0x180045d8f  ja      loc_180046177
0x180045d95  mov     ecx, eax
0x180045d97  mov     eax, 2
0x180045d9c  mul     rcx
0x180045d9f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180045da6  cmovb   rax, rcx
0x180045daa  mov     rcx, rax; unsigned __int64
0x180045dad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180045db2  mov     r15, rax
0x180045db5  mov     [rsp+0B8h+var_70], rax
0x180045dba  test    rax, rax
0x180045dbd  jnz     short loc_180045DD1
0x180045dbf  mov     ebx, 8007000Eh
0x180045dc4  mov     rcx, [rsp+0B8h+arg_10]
0x180045dcc  jmp     loc_1800460E5
0x180045dd1  mov     r12d, 7FFFFFFFh
0x180045dd7  cmp     ebx, r12d
0x180045dda  ja      loc_180046159
0x180045de0  mov     [rsp+0B8h+cchWideChar], ebx; cchWideChar
0x180045de4  mov     [rsp+0B8h+lpWideCharStr], r15; lpWideCharStr
0x180045de9  mov     r9d, [rsi+88h]; cbMultiByte
0x180045df0  mov     r8, [rsi+80h]; lpMultiByteStr
0x180045df7  xor     edx, edx; dwFlags
0x180045df9  mov     ecx, 0FDE9h; CodePage
0x180045dfe  call    cs:__imp_MultiByteToWideChar
0x180045e04  test    eax, eax
0x180045e06  jnz     short loc_180045E36
0x180045e08  lea     rcx, aMsdrmMultibyte; "[msdrm]:MultiByte Error\n"
0x180045e0f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180045e14  call    cs:__imp_GetLastError
0x180045e1a  mov     ebx, eax
0x180045e1c  test    eax, eax
0x180045e1e  jle     short loc_180045E29
0x180045e20  movzx   ebx, ax
0x180045e23  or      ebx, 80070000h
0x180045e29  mov     rcx, [rsp+0B8h+arg_10]
0x180045e31  jmp     loc_1800460E5
0x180045e36  mov     [r15+rbx*2], di
0x180045e3b  lea     r8, [rsp+0B8h+var_78]; unsigned __int16 **
0x180045e40  lea     rdx, [rsp+0B8h+Block]; unsigned __int16 **
0x180045e48  mov     rcx, r15; psz
0x180045e4b  call    ?GetDataFromResponse@@YAJPEBGPEAPEAG1@Z; GetDataFromResponse(ushort const *,ushort * *,ushort * *)
0x180045e50  mov     ebx, eax
0x180045e52  test    eax, eax
0x180045e54  jns     short loc_180045E63
0x180045e56  mov     rcx, [rsp+0B8h+arg_10]
0x180045e5e  jmp     loc_1800460E5
0x180045e63  and     dword ptr [rsi+28h], 0FFFFFFFDh
0x180045e67  mov     [rsi+8], rdi
0x180045e6b  mov     [rsi+8Ch], edi
0x180045e71  lea     rcx, aContentTypeApp; "Content-Type: application/x-www-form-ur"...
0x180045e78  mov     rax, [rsp+0B8h+var_60]
0x180045e7d  mov     [rax], rcx
0x180045e80  mov     rcx, rsi; this
0x180045e83  call    ?CloseHttpRequest@CHttpBase@@IEAAJXZ; CHttpBase::CloseHttpRequest(void)
0x180045e88  mov     ebx, eax
0x180045e8a  test    eax, eax
0x180045e8c  jns     short loc_180045E9B
0x180045e8e  mov     rcx, [rsp+0B8h+arg_10]
0x180045e96  jmp     loc_1800460E5
0x180045e9b  mov     rdx, [rsp+0B8h+Block]; unsigned __int16 *
0x180045ea3  mov     rcx, rsi; this
0x180045ea6  call    ?InitializeHttpRequest@CHttpBase@@IEAAJPEBG@Z; CHttpBase::InitializeHttpRequest(ushort const *)
0x180045eab  mov     ebx, eax
0x180045ead  test    eax, eax
0x180045eaf  jns     short loc_180045EBE
0x180045eb1  mov     rcx, [rsp+0B8h+arg_10]
0x180045eb9  jmp     loc_1800460E5
0x180045ebe  mov     r8, [rsp+0B8h+var_78]; lpWideCharStr
0x180045ec3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180045ec7  inc     rbx
0x180045eca  cmp     [r8+rbx*2], di
0x180045ecf  jnz     short loc_180045EC7
0x180045ed1  mov     r14d, 0FFFFFFFFh
0x180045ed7  cmp     rbx, r14
0x180045eda  ja      loc_18004615E
0x180045ee0  cmp     ebx, r12d
0x180045ee3  ja      loc_180046163
0x180045ee9  mov     [rsp+0B8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180045eee  mov     [rsp+0B8h+lpDefaultChar], rdi; lpDefaultChar
0x180045ef3  mov     [rsp+0B8h+cchWideChar], edi; cbMultiByte
0x180045ef7  mov     [rsp+0B8h+lpWideCharStr], rdi; lpMultiByteStr
0x180045efc  mov     r9d, ebx; cchWideChar
0x180045eff  xor     edx, edx; dwFlags
0x180045f01  mov     ecx, 0FDE9h; CodePage
0x180045f06  call    cs:__imp_WideCharToMultiByte
0x180045f0c  mov     r12d, eax
0x180045f0f  test    eax, eax
0x180045f11  js      loc_180046168
0x180045f17  lea     rax, [r12+1]
0x180045f1c  cmp     rax, r14
0x180045f1f  ja      loc_180046172
0x180045f25  mov     ecx, eax; unsigned __int64
0x180045f27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180045f2c  mov     r14, rax
0x180045f2f  mov     [rsp+0B8h+var_68], rax
0x180045f34  test    rax, rax
0x180045f37  jnz     short loc_180045F4B
0x180045f39  mov     ebx, 8007000Eh
0x180045f3e  mov     rcx, [rsp+0B8h+arg_10]
0x180045f46  jmp     loc_1800460E5
0x180045f4b  cmp     r12d, 7FFFFFFFh
0x180045f52  ja      loc_18004616D
0x180045f58  mov     [rsp+0B8h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180045f5d  mov     [rsp+0B8h+lpDefaultChar], rdi; lpDefaultChar
0x180045f62  mov     [rsp+0B8h+cchWideChar], r12d; cbMultiByte
0x180045f67  mov     [rsp+0B8h+lpWideCharStr], r14; lpMultiByteStr
0x180045f6c  mov     r9d, ebx; cchWideChar
0x180045f6f  mov     r8, [rsp+0B8h+var_78]; lpWideCharStr
0x180045f74  xor     edx, edx; dwFlags
0x180045f76  mov     ecx, 0FDE9h; CodePage
0x180045f7b  call    cs:__imp_WideCharToMultiByte
0x180045f81  test    eax, eax
0x180045f83  jnz     short loc_180045FA7
0x180045f85  call    cs:__imp_GetLastError
0x180045f8b  mov     ebx, eax
0x180045f8d  test    eax, eax
0x180045f8f  jle     short loc_180045F9A
0x180045f91  movzx   ebx, ax
0x180045f94  or      ebx, 80070000h
0x180045f9a  mov     rcx, [rsp+0B8h+arg_10]
0x180045fa2  jmp     loc_1800460E5
0x180045fa7  mov     [r14+r12], dil
0x180045fab  mov     rdx, [rsp+0B8h+Block]
0x180045fb3  lea     rcx, aMsdrmPostingTo; "[msdrm]:Posting token to %ws\n"
0x180045fba  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180045fbf  mov     r8d, r12d; unsigned int
0x180045fc2  mov     rdx, r14; unsigned __int8 *
0x180045fc5  mov     rcx, rsi; this
0x180045fc8  call    ?SendRequest@CHttpBase@@IEAAJPEAEI@Z; CHttpBase::SendRequest(uchar *,uint)
0x180045fcd  mov     ebx, eax
0x180045fcf  mov     r8d, [rsi+78h]
0x180045fd3  mov     edx, eax
0x180045fd5  lea     rcx, aMsdrmSendreque; "[msdrm]: SendRequest hr = 0x%x, HTTPRet"...
0x180045fdc  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180045fe1  test    ebx, ebx
0x180045fe3  jns     short loc_180045FF2
0x180045fe5  mov     rcx, [rsp+0B8h+arg_10]
0x180045fed  jmp     loc_1800460E5
0x180045ff2  mov     rcx, rsi; this
0x180045ff5  call    ?GetResponse@CHttpBase@@IEAAJXZ; CHttpBase::GetResponse(void)
0x180045ffa  mov     ebx, eax
0x180045ffc  test    eax, eax
0x180045ffe  jns     short loc_18004600D
0x180046000  mov     rcx, [rsp+0B8h+arg_10]
0x180046008  jmp     loc_1800460E5
0x18004600d  mov     edx, [rsi+88h]
0x180046013  mov     rcx, [rsi+80h]
0x18004601a  call    ?CheckForPostForm@@YA?AW4_POST_DATA_INFO@@PEBDI@Z; CheckForPostForm(char const *,uint)
0x18004601f  mov     r12d, eax
0x180046022  mov     rcx, [rsp+0B8h+Block]; Block
0x18004602a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004602f  mov     [rsp+0B8h+Block], rdi
0x180046037  mov     rcx, [rsp+0B8h+var_78]; Block
0x18004603c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046041  mov     [rsp+0B8h+var_78], rdi
0x180046046  mov     rcx, r15; Block
0x180046049  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004604e  mov     r15, rdi
0x180046051  mov     [rsp+0B8h+var_70], rdi
0x180046056  mov     rcx, r14; Block
0x180046059  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004605e  mov     r14, rdi
0x180046061  mov     [rsp+0B8h+var_68], rdi
0x180046066  jmp     loc_180045D20
0x18004606b  mov     rdx, [rsi+0A0h]; unsigned __int16 *
0x180046072  mov     r13, [rsp+0B8h+arg_8]
0x18004607a  mov     rcx, r13; unsigned __int16 *
0x18004607d  call    ?IsResponseFromStartingUrl@@YAHPEBG0@Z; IsResponseFromStartingUrl(ushort const *,ushort const *)
0x180046082  test    eax, eax
0x180046084  jnz     short loc_1800460C3
0x180046086  lea     rcx, aMsdrmHandlepos_1; "[msdrm]:HandlePostRedirects: When loop "...
0x18004608d  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180046092  mov     rdx, r13
0x180046095  lea     rcx, aMsdrmHandlepos; "[msdrm]:HandlePostRedirects: wszFirstUR"...
0x18004609c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800460a1  mov     rdx, [rsi+0A0h]
0x1800460a8  lea     rcx, aMsdrmHandlepos_0; "[msdrm]:HandlePostRedirects: m_wszLastR"...
0x1800460af  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800460b4  mov     ebx, 80004005h
0x1800460b9  mov     rcx, [rsp+0B8h+arg_10]
0x1800460c1  jmp     short loc_1800460E5
0x1800460c3  mov     rcx, [rsp+0B8h+arg_10]
0x1800460cb  jmp     short loc_1800460E5
0x1800460cd  xor     edi, edi
0x1800460cf  mov     ebx, dword ptr [rsp+0B8h+arg_10]
0x1800460d6  mov     r15, [rsp+0B8h+var_70]
0x1800460db  mov     r14, [rsp+0B8h+var_68]
0x1800460e0  mov     rcx, [rsp+0B8h+var_58]
0x1800460e5  mov     rax, [rsp+0B8h+var_60]
0x1800460ea  mov     [rax], rcx
0x1800460ed  mov     rcx, [rsp+0B8h+Block]; Block
0x1800460f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800460fa  mov     [rsp+0B8h+Block], rdi
0x180046102  mov     rcx, [rsp+0B8h+var_78]; Block
0x180046107  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004610c  mov     [rsp+0B8h+var_78], rdi
0x180046111  mov     rcx, r15; Block
0x180046114  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046119  mov     rcx, r14; Block
0x18004611c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180046121  cmp     [rsp+0B8h+arg_0], edi
0x180046128  jz      short loc_180046130
0x18004612a  call    cs:__imp_CoUninitialize
0x180046130  mov     edx, ebx
0x180046132  lea     rcx, aMsdrmChttpbase_11; "-[msdrm]:CHttpBase::HandlePostRedirects"...
0x180046139  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004613e  mov     eax, ebx
0x180046140  add     rsp, 80h
0x180046147  pop     r15
0x180046149  pop     r14
0x18004614b  pop     r13
0x18004614d  pop     r12
0x18004614f  pop     rdi
0x180046150  pop     rsi
0x180046151  pop     rbx
0x180046152  retn
0x180046153  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046159  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004615e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046163  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046168  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18004616d  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046172  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180046177  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
