# XMLParser::SetInput(IUnknown *)

- ea: `0x18005e840`
- end: `0x18005eb1d`
- name: `?SetInput@XMLParser@@UEAAJPEAUIUnknown@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(XMLParser *this, IUnknown *pStm)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ae54`
- `0x180029ad8`
- `0x18005e840`
- `0x18005eb24`
- `0x18005f010`
- `0x18005f298`
- `0x1800837b4`
- `0x1800848b4`
- `0x1800cada0`
- `0x1800cba94`
- `0x18015ff80`
- `0x1801601f0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e897`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e9c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ea1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e9c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ea1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005eae9`

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
0x18005e840  mov     [rsp-8+arg_10], rbx
0x18005e845  push    rbp
0x18005e846  push    rsi
0x18005e847  push    rdi
0x18005e848  push    r14
0x18005e84a  push    r15
0x18005e84c  lea     rbp, [rsp-37h]
0x18005e851  sub     rsp, 0C0h
0x18005e858  mov     rax, cs:__security_cookie
0x18005e85f  xor     rax, rsp
0x18005e862  mov     [rbp+57h+var_30], rax
0x18005e866  xor     r15d, r15d
0x18005e869  mov     rbx, pStm
0x18005e86c  mov     rdi, this
0x18005e86f  test    pStm, pStm
0x18005e872  jz      loc_18005E9F1
0x18005e878  mov     rax, cs:?g_pfnEntry@@3P6APEAUTLSDATA@@XZEA; TLSDATA * (*g_pfnEntry)(void)
0x18005e87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e884  test    rax, rax
0x18005e887  jz      loc_18005EA27
0x18005e88d  lea     r14, [rdi+0E0h]
0x18005e894  mov     this, r14; lpCriticalSection
0x18005e897  call    cs:__imp_EnterCriticalSection
0x18005e89d  cmp     [rdi+3Bh], r15b
0x18005e8a1  jz      loc_18005E9F8
0x18005e8a7  xor     edx, edx; stream
0x18005e8a9  mov     this, rdi; this
0x18005e8ac  call    ?PushTokenizer@XMLParser@@IEAAJPEAUIURLStream@@@Z; XMLParser::PushTokenizer(IURLStream *)
0x18005e8b1  mov     esi, eax
0x18005e8b3  test    eax, eax
0x18005e8b5  js      loc_18005EA1A
0x18005e8bb  mov     rax, [rbx]
0x18005e8be  lea     r8, [rbp+57h+pStream]
0x18005e8c2  lea     pStm, IID_IStream
0x18005e8c9  mov     [rbp+57h+pStream], r15
0x18005e8cd  mov     this, rbx
0x18005e8d0  mov     [rbp+57h+pSequentialStream], r15
0x18005e8d4  mov     rax, [rax]
0x18005e8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8dc  mov     this, [rbx]
0x18005e8df  mov     rsi, [this]
0x18005e8e2  test    eax, eax
0x18005e8e4  js      loc_18005E97D
0x18005e8ea  xor     edx, edx; Val
0x18005e8ec  lea     this, [rbp+57h+stat]; void *
0x18005e8f0  lea     r8d, [pStm+50h]; Size
0x18005e8f4  call    memset_0
0x18005e8f9  lea     r8, [rbp+57h+pUnk]
0x18005e8fd  mov     [rbp+57h+pDoc], r15
0x18005e901  lea     pStm, IID_IUnknown
0x18005e908  mov     [rbp+57h+pUnk], r15
0x18005e90c  mov     this, rbx
0x18005e90f  mov     rax, rsi
0x18005e912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e917  mov     ebx, eax
0x18005e919  test    eax, eax
0x18005e91b  js      short loc_18005E941
0x18005e91d  mov     this, [rbp+57h+pUnk]
0x18005e921  lea     r8, [rbp+57h+pDoc]
0x18005e925  lea     pStm, IID_IXMLDOMDocument
0x18005e92c  mov     rax, [this]
0x18005e92f  mov     rax, [rax]
0x18005e932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e937  mov     ebx, eax
0x18005e939  test    eax, eax
0x18005e93b  jns     loc_18005EA2E
0x18005e941  mov     this, [rbp+57h+pDoc]
0x18005e945  test    this, this
0x18005e948  jnz     loc_18005EA4C
0x18005e94e  mov     this, [rbp+57h+pUnk]
0x18005e952  test    this, this
0x18005e955  jnz     loc_18005EA05
0x18005e95b  test    ebx, ebx
0x18005e95d  jns     loc_18005EA61
0x18005e963  mov     ebx, r15d
0x18005e966  test    ebx, ebx
0x18005e968  js      short loc_18005E99D
0x18005e96a  mov     pStm, [rbp+57h+pStream]; pStm
0x18005e96e  xor     r8d, r8d; fpe
0x18005e971  mov     this, rdi; this
0x18005e974  call    ?PushStream@XMLParser@@IEAAJPEAUIStream@@_N@Z; XMLParser::PushStream(IStream *,bool)
0x18005e979  mov     ebx, eax
0x18005e97b  jmp     short loc_18005E99D
0x18005e97d  lea     r8, [rbp+57h+pSequentialStream]
0x18005e981  mov     this, rbx
0x18005e984  lea     pStm, IID_ISequentialStream
0x18005e98b  mov     rax, rsi
0x18005e98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e993  mov     ebx, eax
0x18005e995  test    eax, eax
0x18005e997  jns     loc_18005EAF4
0x18005e99d  mov     this, [rbp+57h+pSequentialStream]
0x18005e9a1  test    this, this
0x18005e9a4  jnz     loc_18005EB08
0x18005e9aa  mov     this, [rbp+57h+pStream]
0x18005e9ae  test    this, this
0x18005e9b1  jz      short loc_18005E9C3
0x18005e9b3  mov     rax, [this]
0x18005e9b6  mov     rax, [rax+10h]
0x18005e9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e9bf  mov     [rbp+57h+pStream], r15
0x18005e9c3  mov     this, r14; lpCriticalSection
0x18005e9c6  call    cs:__imp_LeaveCriticalSection
0x18005e9cc  mov     eax, ebx
0x18005e9ce  mov     this, [rbp+57h+var_30]
0x18005e9d2  xor     this, rsp; StackCookie
0x18005e9d5  call    __security_check_cookie
0x18005e9da  mov     rbx, [rsp+0E0h+arg_10]
0x18005e9e2  add     rsp, 0C0h
0x18005e9e9  pop     r15
0x18005e9eb  pop     r14
0x18005e9ed  pop     rdi
0x18005e9ee  pop     rsi
0x18005e9ef  pop     rbp
0x18005e9f0  retn
0x18005e9f1  mov     eax, 80070057h
0x18005e9f6  jmp     short loc_18005E9CE
0x18005e9f8  mov     this, rdi; this
0x18005e9fb  call    ?init@XMLParser@@IEAAJXZ; XMLParser::init(void)
0x18005ea00  jmp     loc_18005E8A7
0x18005ea05  mov     rax, [this]
0x18005ea08  mov     rax, [rax+10h]
0x18005ea0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea11  mov     [rbp+57h+pUnk], r15
0x18005ea15  jmp     loc_18005E95B
0x18005ea1a  mov     this, r14; lpCriticalSection
0x18005ea1d  call    cs:__imp_LeaveCriticalSection
0x18005ea23  mov     eax, esi
0x18005ea25  jmp     short loc_18005E9CE
0x18005ea27  mov     eax, 80004005h
0x18005ea2c  jmp     short loc_18005E9CE
0x18005ea2e  mov     this, [rbp+57h+pStream]
0x18005ea32  lea     pStm, [rbp+57h+stat]
0x18005ea36  xor     r8d, r8d
0x18005ea39  mov     rax, [this]
0x18005ea3c  mov     rax, [rax+60h]
0x18005ea40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea45  mov     ebx, eax
0x18005ea47  jmp     loc_18005E941
0x18005ea4c  mov     rax, [this]
0x18005ea4f  mov     rax, [rax+10h]
0x18005ea53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea58  mov     [rbp+57h+pDoc], r15
0x18005ea5c  jmp     loc_18005E94E
0x18005ea61  mov     pStm, [rbp+57h+stat.pwcsName]; pszCurrentUrl
0x18005ea65  test    pStm, pStm
0x18005ea68  jz      loc_18005E963
0x18005ea6e  mov     this, rdi; this
0x18005ea71  call    ?SetCurrentURL@XMLParser@@QEAAJPEBG@Z; XMLParser::SetCurrentURL(ushort const *)
0x18005ea76  mov     this, rdi; this
0x18005ea79  call    ?getSecureBaseURL@XMLParser@@IEAAPEAGXZ; XMLParser::getSecureBaseURL(void)
0x18005ea7e  mov     this, [rbp+57h+stat.pwcsName]; relativeURL
0x18005ea82  mov     rsi, rax
0x18005ea85  cmp     [this], r15w
0x18005ea89  jz      short loc_18005EAE9
0x18005ea8b  test    rax, rax
0x18005ea8e  jz      short loc_18005EAE9
0x18005ea90  cmp     [rax], r15w
0x18005ea94  jz      short loc_18005EAE9
0x18005ea96  lea     r9, [rbp+57h+resolvedURL]; resolvedURL
0x18005ea9a  mov     [rbp+57h+resolvedURL], r15
0x18005ea9e  xor     r8d, r8d; baseURL2
0x18005eaa1  mov     [rsp+0E0h+resolvedBase], r15; resolvedBase
0x18005eaa6  xor     edx, edx; baseURL1
0x18005eaa8  call    ?resolveURL@URL@@SAJPEBG00PEAPEAG1@Z; URL::resolveURL(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x18005eaad  mov     ebx, eax
0x18005eaaf  test    eax, eax
0x18005eab1  js      short loc_18005EAE5
0x18005eab3  cmp     [rdi+130h], r15d
0x18005eaba  mov     r8, [rbp+57h+resolvedURL]; pwszReqUrl
0x18005eabe  mov     pStm, [rdi+110h]; pSecMgr
0x18005eac5  setnz   cl; fSecure
0x18005eac8  xor     r9d, r9d; pwszBaseUrl
0x18005eacb  mov     [rsp+0E0h+fZoneRelaxed], r15b; fZoneRelaxed
0x18005ead0  mov     [rsp+0E0h+resolvedBase], rsi; pwszSecureUrl
0x18005ead5  call    ?accessAllowed@URL@@SAJ_NPEAUIInternetSecurityManager@@PEBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x18005eada  mov     this, [rbp+57h+resolvedURL]; pv
0x18005eade  mov     ebx, eax
0x18005eae0  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18005eae5  mov     this, [rbp+57h+stat.pwcsName]; pv
0x18005eae9  call    cs:__imp_CoTaskMemFree
0x18005eaef  jmp     loc_18005E966
0x18005eaf4  mov     this, [rbp+57h+pSequentialStream]; seqstream
0x18005eaf8  lea     pStm, [rbp+57h+pStream]; ppStm
0x18005eafc  call    ?New@StreamWrapper@@SAJPEAUISequentialStream@@PEAPEAUIStream@@@Z; StreamWrapper::New(ISequentialStream *,IStream * *)
0x18005eb01  mov     ebx, eax
0x18005eb03  jmp     loc_18005E966
0x18005eb08  mov     rax, [this]
0x18005eb0b  mov     rax, [rax+10h]
0x18005eb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eb14  mov     [rbp+57h+pSequentialStream], r15
0x18005eb18  jmp     loc_18005E9AA
```
