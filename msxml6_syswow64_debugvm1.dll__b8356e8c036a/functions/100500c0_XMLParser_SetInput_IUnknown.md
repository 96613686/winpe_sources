# XMLParser::SetInput(IUnknown *)

- ea: `0x100500c0`
- end: `0x10050352`
- name: `?SetInput@XMLParser@@UAGJPAUIUnknown@@@Z`
- size: `658`
- prototype: `HRESULT __stdcall(XMLParser *this, IUnknown *pStm)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x10040dee`
- `0x100500c0`
- `0x1005064c`
- `0x100509b8`
- `0x10054dcb`
- `0x10065281`
- `0x10067bc0`
- `0x1006b510`
- `0x1006c354`
- `0x1008de9e`
- `0x10130f3f`
- `0x10144ce4`
- `0x1014515e`
- `0x101451d5`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10050139`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10050336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10050139`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10050336`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10050116`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10050116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x100502a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x100502a8`

## pseudocode

```c
HRESULT __stdcall XMLParser::SetInput(XMLParser *this, IUnknown *pStm)
{
  int v3; // edi
  IUnknown *v4; // ebx
  int v5; // eax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const _GUID *, void **); // edi
  int v7; // ebx
  XMLParser *v8; // edi
  wchar_t *SecureBaseURL; // eax
  wchar_t *pwcsName; // ecx
  IStream *pStream; // [esp+34h] [ebp-68h] BYREF
  IUnknown *pUnk; // [esp+38h] [ebp-64h] BYREF
  wchar_t *resolvedURL; // [esp+3Ch] [ebp-60h] BYREF
  IXMLDOMDocument *pDoc; // [esp+40h] [ebp-5Ch] BYREF
  ISequentialStream *pSequentialStream; // [esp+44h] [ebp-58h] BYREF
  wchar_t *pwszSecureUrl; // [esp+48h] [ebp-54h]
  tagSTATSTG stat; // [esp+4Ch] [ebp-50h] BYREF

  pUnk = pStm;
  resolvedURL = (wchar_t *)this;
  if ( !pStm )
    return -2147024809;
  EnsureTls::EnsureTls((EnsureTls *)&pDoc);
  if ( !pDoc )
    return -2147467259;
  EnterCriticalSection(&this->_cs._cs);
  if ( !this->_fStarted )
    XMLParser::init(this);
  v3 = XMLParser::PushTokenizer(this, 0);
  if ( v3 < 0 )
  {
    LeaveCriticalSection(&this->_cs._cs);
    return v3;
  }
  v4 = pUnk;
  pStream = 0;
  pSequentialStream = 0;
  v5 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IStream **))pUnk->QueryInterface)(
         pUnk->QueryInterface,
         pUnk,
         &IID_IStream,
         &pStream);
  QueryInterface = v4->QueryInterface;
  if ( v5 >= 0 )
  {
    memset(&stat, 0, sizeof(stat));
    pDoc = 0;
    pUnk = 0;
    v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IUnknown **))QueryInterface)(
           QueryInterface,
           v4,
           &IID_IUnknown,
           &pUnk);
    if ( v7 >= 0 )
    {
      v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, IXMLDOMDocument **))pUnk->QueryInterface)(
             pUnk->QueryInterface,
             pUnk,
             &IID_IXMLDOMDocument,
             &pDoc);
      if ( v7 >= 0 )
        v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(IStream *, tagSTATSTG *, unsigned int), IStream *, tagSTATSTG *, _DWORD))pStream->Stat)(
               pStream->Stat,
               pStream,
               &stat,
               0);
    }
    if ( pDoc )
    {
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IXMLDOMDocument *))pDoc->Release)(
        pDoc->Release,
        pDoc);
      pDoc = 0;
    }
    if ( pUnk )
    {
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *))pUnk->Release)(pUnk->Release, pUnk);
      pUnk = 0;
    }
    if ( v7 >= 0 && stat.pwcsName )
    {
      v8 = (XMLParser *)resolvedURL;
      XMLParser::SetCurrentURL((XMLParser *)resolvedURL, stat.pwcsName);
      SecureBaseURL = XMLParser::getSecureBaseURL(v8);
      pwcsName = stat.pwcsName;
      pwszSecureUrl = SecureBaseURL;
      if ( *stat.pwcsName && SecureBaseURL && *SecureBaseURL )
      {
        v7 = URL::resolveURL(stat.pwcsName, 0, 0, &resolvedURL, 0);
        if ( v7 >= 0 )
        {
          v7 = URL::accessAllowed(v8->_dwSafetyOptions != 0, v8->_pSecMgr._p, resolvedURL, 0, pwszSecureUrl, 0);
          MemFree(resolvedURL);
        }
        pwcsName = stat.pwcsName;
      }
      CoTaskMemFree(pwcsName);
      goto LABEL_30;
    }
    v7 = 0;
LABEL_29:
    v8 = (XMLParser *)resolvedURL;
LABEL_30:
    if ( v7 >= 0 )
      v7 = XMLParser::PushStream(v8, pStream, 0);
    goto LABEL_32;
  }
  v7 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, ISequentialStream **))QueryInterface)(
         v4->QueryInterface,
         v4,
         &IID_ISequentialStream,
         &pSequentialStream);
  if ( v7 >= 0 )
  {
    v7 = StreamWrapper::New(pSequentialStream, &pStream);
    goto LABEL_29;
  }
LABEL_32:
  if ( pSequentialStream )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), ISequentialStream *))pSequentialStream->Release)(
      pSequentialStream->Release,
      pSequentialStream);
    pSequentialStream = 0;
  }
  if ( pStream )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IStream *))pStream->Release)(
      pStream->Release,
      pStream);
    pStream = 0;
  }
  LeaveCriticalSection(&this->_cs._cs);
  return v7;
}

```

## disassembly

```asm
0x100500c0  mov     edi, edi
0x100500c2  push    ebp
0x100500c3  mov     ebp, esp
0x100500c5  and     esp, 0FFFFFFF8h
0x100500c8  sub     esp, 6Ch
0x100500cb  mov     eax, ___security_cookie
0x100500d0  xor     eax, esp
0x100500d2  mov     [esp+6Ch+var_4], eax
0x100500d6  mov     eax, [ebp+pStm]
0x100500d9  mov     [esp+6Ch+pUnk], eax
0x100500dd  push    ebx
0x100500de  mov     ebx, [ebp+this]
0x100500e1  mov     [esp+70h+resolvedURL], ebx
0x100500e5  push    esi
0x100500e6  push    edi
0x100500e7  test    eax, eax
0x100500e9  jnz     short loc_100500F5
0x100500eb  mov     eax, 80070057h
0x100500f0  jmp     loc_1005033E
0x100500f5  lea     ecx, [esp+78h+pDoc]; this
0x100500f9  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100500fe  cmp     [esp+78h+pDoc], 0
0x10050103  jnz     short loc_1005010F
0x10050105  mov     eax, 80004005h
0x1005010a  jmp     loc_1005033E
0x1005010f  lea     esi, [ebx+90h]
0x10050115  push    esi; lpCriticalSection
0x10050116  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005011c  cmp     byte ptr [ebx+1Fh], 0
0x10050120  jnz     short loc_10050129
0x10050122  mov     ecx, ebx; this
0x10050124  call    ?init@XMLParser@@IAEJXZ; XMLParser::init(void)
0x10050129  push    0; stream
0x1005012b  mov     ecx, ebx; this
0x1005012d  call    ?PushTokenizer@XMLParser@@IAEJPAUIURLStream@@@Z; XMLParser::PushTokenizer(IURLStream *)
0x10050132  mov     edi, eax
0x10050134  test    edi, edi
0x10050136  jns     short loc_10050146
0x10050138  push    esi; lpCriticalSection
0x10050139  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005013f  mov     eax, edi
0x10050141  jmp     loc_1005033E
0x10050146  mov     ebx, [esp+78h+pUnk]
0x1005014a  xor     eax, eax
0x1005014c  mov     [esp+78h+pStream], eax
0x10050150  mov     [esp+78h+pSequentialStream], eax
0x10050154  lea     eax, [esp+78h+pStream]
0x10050158  push    eax
0x10050159  mov     edi, [ebx]
0x1005015b  push    offset _IID_IStream
0x10050160  push    ebx
0x10050161  mov     ecx, [edi]; this
0x10050163  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050169  call    dword ptr [edi]
0x1005016b  mov     ecx, [ebx]
0x1005016d  mov     edi, [ecx]
0x1005016f  test    eax, eax
0x10050171  js      loc_100502B4
0x10050177  push    48h ; 'H'; Size
0x10050179  lea     eax, [esp+7Ch+stat]
0x1005017d  push    0; Val
0x1005017f  push    eax; void *
0x10050180  call    _memset
0x10050185  add     esp, 0Ch
0x10050188  xor     eax, eax
0x1005018a  mov     [esp+78h+pDoc], eax
0x1005018e  mov     ecx, edi; this
0x10050190  mov     [esp+78h+pUnk], eax
0x10050194  lea     eax, [esp+78h+pUnk]
0x10050198  push    eax
0x10050199  push    offset _IID_IUnknown
0x1005019e  push    ebx
0x1005019f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100501a5  call    edi
0x100501a7  mov     ebx, eax
0x100501a9  test    ebx, ebx
0x100501ab  js      short loc_100501ED
0x100501ad  mov     ecx, [esp+78h+pUnk]
0x100501b1  mov     eax, [ecx]
0x100501b3  mov     edi, [eax]
0x100501b5  lea     eax, [esp+78h+pDoc]
0x100501b9  push    eax
0x100501ba  push    offset _IID_IXMLDOMDocument
0x100501bf  push    ecx
0x100501c0  mov     ecx, edi; this
0x100501c2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100501c8  call    edi
0x100501ca  mov     ebx, eax
0x100501cc  test    ebx, ebx
0x100501ce  js      short loc_100501ED
0x100501d0  mov     ecx, [esp+78h+pStream]
0x100501d4  push    0
0x100501d6  mov     eax, [ecx]
0x100501d8  mov     edi, [eax+30h]
0x100501db  lea     eax, [esp+7Ch+stat]
0x100501df  push    eax
0x100501e0  push    ecx
0x100501e1  mov     ecx, edi; this
0x100501e3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100501e9  call    edi
0x100501eb  mov     ebx, eax
0x100501ed  mov     ecx, [esp+78h+pDoc]
0x100501f1  test    ecx, ecx
0x100501f3  jz      short loc_1005020D
0x100501f5  mov     eax, [ecx]
0x100501f7  push    ecx
0x100501f8  mov     edi, [eax+8]
0x100501fb  mov     ecx, edi; this
0x100501fd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050203  call    edi
0x10050205  mov     [esp+78h+pDoc], 0
0x1005020d  mov     ecx, [esp+78h+pUnk]
0x10050211  test    ecx, ecx
0x10050213  jz      short loc_1005022D
0x10050215  mov     eax, [ecx]
0x10050217  push    ecx
0x10050218  mov     edi, [eax+8]
0x1005021b  mov     ecx, edi; this
0x1005021d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050223  call    edi
0x10050225  mov     [esp+78h+pUnk], 0
0x1005022d  test    ebx, ebx
0x1005022f  js      short loc_100502B0
0x10050231  cmp     [esp+78h+stat.pwcsName], 0
0x10050236  jz      short loc_100502B0
0x10050238  push    [esp+78h+stat.pwcsName]; pszCurrentUrl
0x1005023c  mov     edi, [esp+7Ch+resolvedURL]
0x10050240  mov     ecx, edi; this
0x10050242  call    ?SetCurrentURL@XMLParser@@QAEJPBG@Z; XMLParser::SetCurrentURL(ushort const *)
0x10050247  mov     ecx, edi; this
0x10050249  call    ?getSecureBaseURL@XMLParser@@IAEPAGXZ; XMLParser::getSecureBaseURL(void)
0x1005024e  mov     ecx, [esp+78h+stat.pwcsName]; relativeURL
0x10050252  xor     edx, edx; baseURL1
0x10050254  mov     [esp+78h+pwszSecureUrl], eax
0x10050258  cmp     [ecx], dx
0x1005025b  jz      short loc_100502A7
0x1005025d  test    eax, eax
0x1005025f  jz      short loc_100502A7
0x10050261  cmp     [eax], dx
0x10050264  jz      short loc_100502A7
0x10050266  push    edx; resolvedBase
0x10050267  lea     eax, [esp+7Ch+resolvedURL]
0x1005026b  push    eax; resolvedURL
0x1005026c  push    edx; baseURL2
0x1005026d  call    ?resolveURL@URL@@SGJPBG00PAPAG1@Z; URL::resolveURL(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x10050272  mov     ebx, eax
0x10050274  test    ebx, ebx
0x10050276  js      short loc_100502A3
0x10050278  mov     edx, [edi+0ACh]; pSecMgr
0x1005027e  xor     eax, eax
0x10050280  cmp     [edi+0BCh], eax
0x10050286  push    eax; fZoneRelaxed
0x10050287  push    [esp+7Ch+pwszSecureUrl]; pwszSecureUrl
0x1005028b  setnz   cl; fSecure
0x1005028e  push    eax; pwszBaseUrl
0x1005028f  push    [esp+84h+resolvedURL]; pwszReqUrl
0x10050293  call    ?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x10050298  mov     ecx, [esp+78h+resolvedURL]; pv
0x1005029c  mov     ebx, eax
0x1005029e  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x100502a3  mov     ecx, [esp+78h+stat.pwcsName]
0x100502a7  push    ecx; pv
0x100502a8  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x100502ae  jmp     short loc_100502E2
0x100502b0  xor     ebx, ebx
0x100502b2  jmp     short loc_100502DE
0x100502b4  lea     eax, [esp+78h+pSequentialStream]
0x100502b8  mov     ecx, edi; this
0x100502ba  push    eax
0x100502bb  push    offset _IID_ISequentialStream
0x100502c0  push    ebx
0x100502c1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100502c7  call    edi
0x100502c9  mov     ebx, eax
0x100502cb  test    ebx, ebx
0x100502cd  js      short loc_100502F5
0x100502cf  mov     ecx, [esp+78h+pSequentialStream]; seqstream
0x100502d3  lea     edx, [esp+78h+pStream]; ppStm
0x100502d7  call    ?New@StreamWrapper@@SGJPAUISequentialStream@@PAPAUIStream@@@Z; StreamWrapper::New(ISequentialStream *,IStream * *)
0x100502dc  mov     ebx, eax
0x100502de  mov     edi, [esp+78h+resolvedURL]
0x100502e2  test    ebx, ebx
0x100502e4  js      short loc_100502F5
0x100502e6  push    0; fpe
0x100502e8  push    [esp+7Ch+pStream]; pStm
0x100502ec  mov     ecx, edi; this
0x100502ee  call    ?PushStream@XMLParser@@IAEJPAUIStream@@_N@Z; XMLParser::PushStream(IStream *,bool)
0x100502f3  mov     ebx, eax
0x100502f5  mov     ecx, [esp+78h+pSequentialStream]
0x100502f9  test    ecx, ecx
0x100502fb  jz      short loc_10050315
0x100502fd  mov     eax, [ecx]
0x100502ff  push    ecx
0x10050300  mov     edi, [eax+8]
0x10050303  mov     ecx, edi; this
0x10050305  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005030b  call    edi
0x1005030d  mov     [esp+78h+pSequentialStream], 0
0x10050315  mov     ecx, [esp+78h+pStream]
0x10050319  test    ecx, ecx
0x1005031b  jz      short loc_10050335
0x1005031d  mov     eax, [ecx]
0x1005031f  push    ecx
0x10050320  mov     edi, [eax+8]
0x10050323  mov     ecx, edi; this
0x10050325  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005032b  call    edi
0x1005032d  mov     [esp+78h+pStream], 0
0x10050335  push    esi; lpCriticalSection
0x10050336  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005033c  mov     eax, ebx
0x1005033e  mov     ecx, [esp+78h+var_4]
0x10050342  pop     edi
0x10050343  pop     esi
0x10050344  pop     ebx
0x10050345  xor     ecx, esp; cookie
0x10050347  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005034c  mov     esp, ebp
0x1005034e  pop     ebp
0x1005034f  retn    8
```
