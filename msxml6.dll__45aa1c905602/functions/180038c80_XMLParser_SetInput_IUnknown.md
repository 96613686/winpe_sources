# XMLParser::SetInput(IUnknown *)

- ea: `0x180038c80`
- end: `0x180038f76`
- name: `?SetInput@XMLParser@@UEAAJPEAUIUnknown@@@Z`
- size: `758`
- prototype: `HRESULT __fastcall(XMLParser *this, IUnknown *pStm)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180017480`
- `0x1800376a8`
- `0x180038c80`
- `0x180038f7c`
- `0x180039544`
- `0x18005084c`
- `0x180082dd0`
- `0x180083f24`
- `0x1800cc6c0`
- `0x1800cd3e4`
- `0x1801639d0`
- `0x180163c50`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038cd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038cd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038e6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f3c`

## pseudocode

```c
__int64 __fastcall XMLParser::SetInput(XMLParser *this, IUnknown *pStm)
{
  int v4; // esi
  IUnknown_vtbl *v5; // rax
  int v6; // eax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rsi
  int v8; // ebx
  wchar_t *SecureBaseURL; // rax
  wchar_t *pwcsName; // rcx
  const wchar_t *v12; // rsi
  IStream *pStream; // [rsp+30h] [rbp-59h] BYREF
  IUnknown *pUnk; // [rsp+38h] [rbp-51h] BYREF
  ISequentialStream *pSequentialStream; // [rsp+40h] [rbp-49h] BYREF
  IXMLDOMDocument *pDoc; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *resolvedURL; // [rsp+50h] [rbp-39h] BYREF
  tagSTATSTG stat; // [rsp+60h] [rbp-29h] BYREF

  if ( !pStm )
    return 2147942487LL;
  if ( !(__int64)g_pfnEntry() )
    return 2147500037LL;
  EnterCriticalSection(&this->_cs._cs);
  if ( !this->_fStarted )
    XMLParser::init(this);
  v4 = XMLParser::PushTokenizer(this, 0);
  if ( v4 < 0 )
  {
    LeaveCriticalSection(&this->_cs._cs);
    return (unsigned int)v4;
  }
  v5 = pStm->__vftable;
  pStream = 0;
  pSequentialStream = 0;
  v6 = v5->QueryInterface(pStm, &IID_IStream, (void **)&pStream);
  QueryInterface = pStm->QueryInterface;
  if ( v6 >= 0 )
  {
    memset_0(&stat, 0, sizeof(stat));
    pDoc = 0;
    pUnk = 0;
    v8 = QueryInterface(pStm, &IID_IUnknown, (void **)&pUnk);
    if ( v8 >= 0 )
    {
      v8 = pUnk->QueryInterface(pUnk, &IID_IXMLDOMDocument, (void **)&pDoc);
      if ( v8 >= 0 )
        v8 = pStream->Stat(pStream, &stat, 0);
    }
    if ( pDoc )
    {
      pDoc->Release(pDoc);
      pDoc = 0;
    }
    if ( pUnk )
    {
      pUnk->Release(pUnk);
      pUnk = 0;
    }
    if ( v8 >= 0 && stat.pwcsName )
    {
      XMLParser::SetCurrentURL(this, stat.pwcsName);
      SecureBaseURL = XMLParser::getSecureBaseURL(this);
      pwcsName = stat.pwcsName;
      v12 = SecureBaseURL;
      if ( *stat.pwcsName && SecureBaseURL && *SecureBaseURL )
      {
        resolvedURL = 0;
        v8 = URL::resolveURL(stat.pwcsName, 0, 0, &resolvedURL, 0);
        if ( v8 >= 0 )
        {
          v8 = URL::accessAllowed(this->_dwSafetyOptions != 0, this->_pSecMgr._p, resolvedURL, 0, v12, 0);
          MemFree(resolvedURL);
        }
        pwcsName = stat.pwcsName;
      }
      CoTaskMemFree(pwcsName);
    }
    else
    {
      v8 = 0;
    }
    goto LABEL_16;
  }
  v8 = pStm->QueryInterface(pStm, &IID_ISequentialStream, (void **)&pSequentialStream);
  if ( v8 >= 0 )
  {
    v8 = StreamWrapper::New(pSequentialStream, &pStream);
LABEL_16:
    if ( v8 >= 0 )
      v8 = XMLParser::PushStream(this, pStream, 0);
  }
  if ( pSequentialStream )
  {
    pSequentialStream->Release(pSequentialStream);
    pSequentialStream = 0;
  }
  if ( pStream )
  {
    pStream->Release(pStream);
    pStream = 0;
  }
  LeaveCriticalSection(&this->_cs._cs);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038c80  mov     [rsp-8+arg_10], rbx
0x180038c85  push    rbp
0x180038c86  push    rsi
0x180038c87  push    rdi
0x180038c88  push    r14
0x180038c8a  push    r15
0x180038c8c  lea     rbp, [rsp-37h]
0x180038c91  sub     rsp, 0C0h
0x180038c98  mov     rax, cs:__security_cookie
0x180038c9f  xor     rax, rsp
0x180038ca2  mov     [rbp+57h+var_30], rax
0x180038ca6  xor     r15d, r15d
0x180038ca9  mov     rbx, pStm
0x180038cac  mov     rdi, this
0x180038caf  test    pStm, pStm
0x180038cb2  jz      loc_180038E3E
0x180038cb8  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x180038cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cc4  test    rax, rax
0x180038cc7  jz      loc_180038E7A
0x180038ccd  lea     r14, [rdi+0E0h]
0x180038cd4  mov     this, r14; lpCriticalSection
0x180038cd7  call    cs:__imp_EnterCriticalSection
0x180038cde  nop     dword ptr [rax+rax+00h]
0x180038ce3  cmp     [rdi+3Bh], r15b
0x180038ce7  jz      loc_180038E45
0x180038ced  xor     edx, edx; stream
0x180038cef  mov     this, rdi; this
0x180038cf2  call    ?PushTokenizer@XMLParser@@IEAAJPEAUIURLStream@@@Z; XMLParser::PushTokenizer(IURLStream *)
0x180038cf7  mov     esi, eax
0x180038cf9  test    eax, eax
0x180038cfb  js      loc_180038E67
0x180038d01  mov     rax, [rbx]
0x180038d04  lea     r8, [rbp+57h+pStream]
0x180038d08  lea     pStm, IID_IStream
0x180038d0f  mov     [rbp+57h+pStream], r15
0x180038d13  mov     this, rbx
0x180038d16  mov     [rbp+57h+pSequentialStream], r15
0x180038d1a  mov     rax, [rax]
0x180038d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d22  mov     this, [rbx]
0x180038d25  mov     rsi, [this]
0x180038d28  test    eax, eax
0x180038d2a  js      loc_180038DC3
0x180038d30  xor     edx, edx; Val
0x180038d32  lea     this, [rbp+57h+stat]; void *
0x180038d36  lea     r8d, [pStm+50h]; Size
0x180038d3a  call    memset_0
0x180038d3f  lea     r8, [rbp+57h+pUnk]
0x180038d43  mov     [rbp+57h+pDoc], r15
0x180038d47  lea     pStm, IID_IUnknown
0x180038d4e  mov     [rbp+57h+pUnk], r15
0x180038d52  mov     this, rbx
0x180038d55  mov     rax, rsi
0x180038d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d5d  mov     ebx, eax
0x180038d5f  test    eax, eax
0x180038d61  js      short loc_180038D87
0x180038d63  mov     this, [rbp+57h+pUnk]
0x180038d67  lea     r8, [rbp+57h+pDoc]
0x180038d6b  lea     pStm, IID_IXMLDOMDocument
0x180038d72  mov     rax, [this]
0x180038d75  mov     rax, [rax]
0x180038d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d7d  mov     ebx, eax
0x180038d7f  test    eax, eax
0x180038d81  jns     loc_180038E81
0x180038d87  mov     this, [rbp+57h+pDoc]
0x180038d8b  test    this, this
0x180038d8e  jnz     loc_180038E9F
0x180038d94  mov     this, [rbp+57h+pUnk]
0x180038d98  test    this, this
0x180038d9b  jnz     loc_180038E52
0x180038da1  test    ebx, ebx
0x180038da3  jns     loc_180038EB4
0x180038da9  mov     ebx, r15d
0x180038dac  test    ebx, ebx
0x180038dae  js      short loc_180038DE3
0x180038db0  mov     pStm, [rbp+57h+pStream]; pStm
0x180038db4  xor     r8d, r8d; fpe
0x180038db7  mov     this, rdi; this
0x180038dba  call    ?PushStream@XMLParser@@IEAAJPEAUIStream@@_N@Z; XMLParser::PushStream(IStream *,bool)
0x180038dbf  mov     ebx, eax
0x180038dc1  jmp     short loc_180038DE3
0x180038dc3  lea     r8, [rbp+57h+pSequentialStream]
0x180038dc7  mov     this, rbx
0x180038dca  lea     pStm, IID_ISequentialStream
0x180038dd1  mov     rax, rsi
0x180038dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dd9  mov     ebx, eax
0x180038ddb  test    eax, eax
0x180038ddd  jns     loc_180038F4D
0x180038de3  mov     this, [rbp+57h+pSequentialStream]
0x180038de7  test    this, this
0x180038dea  jnz     loc_180038F61
0x180038df0  mov     this, [rbp+57h+pStream]
0x180038df4  test    this, this
0x180038df7  jz      short loc_180038E09
0x180038df9  mov     rax, [this]
0x180038dfc  mov     rax, [rax+10h]
0x180038e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e05  mov     [rbp+57h+pStream], r15
0x180038e09  mov     this, r14; lpCriticalSection
0x180038e0c  call    cs:__imp_LeaveCriticalSection
0x180038e13  nop     dword ptr [rax+rax+00h]
0x180038e18  mov     eax, ebx
0x180038e1a  mov     this, [rbp+57h+var_30]
0x180038e1e  xor     this, rsp; StackCookie
0x180038e21  call    __security_check_cookie
0x180038e26  mov     rbx, [rsp+0E0h+arg_10]
0x180038e2e  add     rsp, 0C0h
0x180038e35  pop     r15
0x180038e37  pop     r14
0x180038e39  pop     rdi
0x180038e3a  pop     rsi
0x180038e3b  pop     rbp
0x180038e3c  retn
0x180038e3e  mov     eax, 80070057h
0x180038e43  jmp     short loc_180038E1A
0x180038e45  mov     this, rdi; this
0x180038e48  call    ?init@XMLParser@@IEAAJXZ; XMLParser::init(void)
0x180038e4d  jmp     loc_180038CED
0x180038e52  mov     rax, [this]
0x180038e55  mov     rax, [rax+10h]
0x180038e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e5e  mov     [rbp+57h+pUnk], r15
0x180038e62  jmp     loc_180038DA1
0x180038e67  mov     this, r14; lpCriticalSection
0x180038e6a  call    cs:__imp_LeaveCriticalSection
0x180038e71  nop     dword ptr [rax+rax+00h]
0x180038e76  mov     eax, esi
0x180038e78  jmp     short loc_180038E1A
0x180038e7a  mov     eax, 80004005h
0x180038e7f  jmp     short loc_180038E1A
0x180038e81  mov     this, [rbp+57h+pStream]
0x180038e85  lea     pStm, [rbp+57h+stat]
0x180038e89  xor     r8d, r8d
0x180038e8c  mov     rax, [this]
0x180038e8f  mov     rax, [rax+60h]
0x180038e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e98  mov     ebx, eax
0x180038e9a  jmp     loc_180038D87
0x180038e9f  mov     rax, [this]
0x180038ea2  mov     rax, [rax+10h]
0x180038ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eab  mov     [rbp+57h+pDoc], r15
0x180038eaf  jmp     loc_180038D94
0x180038eb4  mov     pStm, [rbp+57h+stat.pwcsName]; pszCurrentUrl
0x180038eb8  test    pStm, pStm
0x180038ebb  jz      loc_180038DA9
0x180038ec1  mov     this, rdi; this
0x180038ec4  call    ?SetCurrentURL@XMLParser@@QEAAJPEBG@Z; XMLParser::SetCurrentURL(ushort const *)
0x180038ec9  mov     this, rdi; this
0x180038ecc  call    ?getSecureBaseURL@XMLParser@@IEAAPEAGXZ; XMLParser::getSecureBaseURL(void)
0x180038ed1  mov     this, [rbp+57h+stat.pwcsName]; relativeURL
0x180038ed5  mov     rsi, rax
0x180038ed8  cmp     [this], r15w
0x180038edc  jz      short loc_180038F3C
0x180038ede  test    rax, rax
0x180038ee1  jz      short loc_180038F3C
0x180038ee3  cmp     [rax], r15w
0x180038ee7  jz      short loc_180038F3C
0x180038ee9  lea     r9, [rbp+57h+resolvedURL]; resolvedURL
0x180038eed  mov     [rbp+57h+resolvedURL], r15
0x180038ef1  xor     r8d, r8d; baseURL2
0x180038ef4  mov     [rsp+0E0h+resolvedBase], r15; resolvedBase
0x180038ef9  xor     edx, edx; baseURL1
0x180038efb  call    ?resolveURL@URL@@SAJPEBG00PEAPEAG1@Z; URL::resolveURL(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180038f00  mov     ebx, eax
0x180038f02  test    eax, eax
0x180038f04  js      short loc_180038F38
0x180038f06  cmp     [rdi+130h], r15d
0x180038f0d  mov     r8, [rbp+57h+resolvedURL]; pwszReqUrl
0x180038f11  mov     pStm, [rdi+110h]; pSecMgr
0x180038f18  setnz   cl; fSecure
0x180038f1b  xor     r9d, r9d; pwszBaseUrl
0x180038f1e  mov     [rsp+0E0h+fZoneRelaxed], r15b; fZoneRelaxed
0x180038f23  mov     [rsp+0E0h+resolvedBase], rsi; pwszSecureUrl
0x180038f28  call    ?accessAllowed@URL@@SAJ_NPEAUIInternetSecurityManager@@PEBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x180038f2d  mov     this, [rbp+57h+resolvedURL]; pv
0x180038f31  mov     ebx, eax
0x180038f33  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180038f38  mov     this, [rbp+57h+stat.pwcsName]; pv
0x180038f3c  call    cs:__imp_CoTaskMemFree
0x180038f43  nop     dword ptr [rax+rax+00h]
0x180038f48  jmp     loc_180038DAC
0x180038f4d  mov     this, [rbp+57h+pSequentialStream]; seqstream
0x180038f51  lea     pStm, [rbp+57h+pStream]; ppStm
0x180038f55  call    ?New@StreamWrapper@@SAJPEAUISequentialStream@@PEAPEAUIStream@@@Z; StreamWrapper::New(ISequentialStream *,IStream * *)
0x180038f5a  mov     ebx, eax
0x180038f5c  jmp     loc_180038DAC
0x180038f61  mov     rax, [this]
0x180038f64  mov     rax, [rax+10h]
0x180038f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f6d  mov     [rbp+57h+pSequentialStream], r15
0x180038f71  jmp     loc_180038DF0
```
