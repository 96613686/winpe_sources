# XMLParser::SetInput(IUnknown *)

- ea: `0x10050030`
- end: `0x100502c2`
- name: `?SetInput@XMLParser@@UAGJPAUIUnknown@@@Z`
- size: `658`
- prototype: `HRESULT __stdcall(XMLParser *this, IUnknown *pStm)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x10040d5e`
- `0x10050030`
- `0x100505bc`
- `0x10050928`
- `0x10054d3b`
- `0x100651e1`
- `0x10067b20`
- `0x1006b470`
- `0x1006c2c4`
- `0x1008dede`
- `0x1013104f`
- `0x10144df4`
- `0x1014526e`
- `0x101452e5`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100500a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100502a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100500a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100502a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10050086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10050086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10050218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x10050218`

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
0x10050030  mov     edi, edi
0x10050032  push    ebp
0x10050033  mov     ebp, esp
0x10050035  and     esp, 0FFFFFFF8h
0x10050038  sub     esp, 6Ch
0x1005003b  mov     eax, ___security_cookie
0x10050040  xor     eax, esp
0x10050042  mov     [esp+6Ch+var_4], eax
0x10050046  mov     eax, [ebp+pStm]
0x10050049  mov     [esp+6Ch+pUnk], eax
0x1005004d  push    ebx
0x1005004e  mov     ebx, [ebp+this]
0x10050051  mov     [esp+70h+resolvedURL], ebx
0x10050055  push    esi
0x10050056  push    edi
0x10050057  test    eax, eax
0x10050059  jnz     short loc_10050065
0x1005005b  mov     eax, 80070057h
0x10050060  jmp     loc_100502AE
0x10050065  lea     ecx, [esp+78h+pDoc]; this
0x10050069  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x1005006e  cmp     [esp+78h+pDoc], 0
0x10050073  jnz     short loc_1005007F
0x10050075  mov     eax, 80004005h
0x1005007a  jmp     loc_100502AE
0x1005007f  lea     esi, [ebx+90h]
0x10050085  push    esi; lpCriticalSection
0x10050086  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1005008c  cmp     byte ptr [ebx+1Fh], 0
0x10050090  jnz     short loc_10050099
0x10050092  mov     ecx, ebx; this
0x10050094  call    ?init@XMLParser@@IAEJXZ; XMLParser::init(void)
0x10050099  push    0; stream
0x1005009b  mov     ecx, ebx; this
0x1005009d  call    ?PushTokenizer@XMLParser@@IAEJPAUIURLStream@@@Z; XMLParser::PushTokenizer(IURLStream *)
0x100500a2  mov     edi, eax
0x100500a4  test    edi, edi
0x100500a6  jns     short loc_100500B6
0x100500a8  push    esi; lpCriticalSection
0x100500a9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100500af  mov     eax, edi
0x100500b1  jmp     loc_100502AE
0x100500b6  mov     ebx, [esp+78h+pUnk]
0x100500ba  xor     eax, eax
0x100500bc  mov     [esp+78h+pStream], eax
0x100500c0  mov     [esp+78h+pSequentialStream], eax
0x100500c4  lea     eax, [esp+78h+pStream]
0x100500c8  push    eax
0x100500c9  mov     edi, [ebx]
0x100500cb  push    offset _IID_IStream
0x100500d0  push    ebx
0x100500d1  mov     ecx, [edi]; this
0x100500d3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100500d9  call    dword ptr [edi]
0x100500db  mov     ecx, [ebx]
0x100500dd  mov     edi, [ecx]
0x100500df  test    eax, eax
0x100500e1  js      loc_10050224
0x100500e7  push    48h ; 'H'; Size
0x100500e9  lea     eax, [esp+7Ch+stat]
0x100500ed  push    0; Val
0x100500ef  push    eax; void *
0x100500f0  call    _memset
0x100500f5  add     esp, 0Ch
0x100500f8  xor     eax, eax
0x100500fa  mov     [esp+78h+pDoc], eax
0x100500fe  mov     ecx, edi; this
0x10050100  mov     [esp+78h+pUnk], eax
0x10050104  lea     eax, [esp+78h+pUnk]
0x10050108  push    eax
0x10050109  push    offset _IID_IUnknown
0x1005010e  push    ebx
0x1005010f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050115  call    edi
0x10050117  mov     ebx, eax
0x10050119  test    ebx, ebx
0x1005011b  js      short loc_1005015D
0x1005011d  mov     ecx, [esp+78h+pUnk]
0x10050121  mov     eax, [ecx]
0x10050123  mov     edi, [eax]
0x10050125  lea     eax, [esp+78h+pDoc]
0x10050129  push    eax
0x1005012a  push    offset _IID_IXMLDOMDocument
0x1005012f  push    ecx
0x10050130  mov     ecx, edi; this
0x10050132  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050138  call    edi
0x1005013a  mov     ebx, eax
0x1005013c  test    ebx, ebx
0x1005013e  js      short loc_1005015D
0x10050140  mov     ecx, [esp+78h+pStream]
0x10050144  push    0
0x10050146  mov     eax, [ecx]
0x10050148  mov     edi, [eax+30h]
0x1005014b  lea     eax, [esp+7Ch+stat]
0x1005014f  push    eax
0x10050150  push    ecx
0x10050151  mov     ecx, edi; this
0x10050153  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050159  call    edi
0x1005015b  mov     ebx, eax
0x1005015d  mov     ecx, [esp+78h+pDoc]
0x10050161  test    ecx, ecx
0x10050163  jz      short loc_1005017D
0x10050165  mov     eax, [ecx]
0x10050167  push    ecx
0x10050168  mov     edi, [eax+8]
0x1005016b  mov     ecx, edi; this
0x1005016d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050173  call    edi
0x10050175  mov     [esp+78h+pDoc], 0
0x1005017d  mov     ecx, [esp+78h+pUnk]
0x10050181  test    ecx, ecx
0x10050183  jz      short loc_1005019D
0x10050185  mov     eax, [ecx]
0x10050187  push    ecx
0x10050188  mov     edi, [eax+8]
0x1005018b  mov     ecx, edi; this
0x1005018d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050193  call    edi
0x10050195  mov     [esp+78h+pUnk], 0
0x1005019d  test    ebx, ebx
0x1005019f  js      short loc_10050220
0x100501a1  cmp     [esp+78h+stat.pwcsName], 0
0x100501a6  jz      short loc_10050220
0x100501a8  push    [esp+78h+stat.pwcsName]; pszCurrentUrl
0x100501ac  mov     edi, [esp+7Ch+resolvedURL]
0x100501b0  mov     ecx, edi; this
0x100501b2  call    ?SetCurrentURL@XMLParser@@QAEJPBG@Z; XMLParser::SetCurrentURL(ushort const *)
0x100501b7  mov     ecx, edi; this
0x100501b9  call    ?getSecureBaseURL@XMLParser@@IAEPAGXZ; XMLParser::getSecureBaseURL(void)
0x100501be  mov     ecx, [esp+78h+stat.pwcsName]; relativeURL
0x100501c2  xor     edx, edx; baseURL1
0x100501c4  mov     [esp+78h+pwszSecureUrl], eax
0x100501c8  cmp     [ecx], dx
0x100501cb  jz      short loc_10050217
0x100501cd  test    eax, eax
0x100501cf  jz      short loc_10050217
0x100501d1  cmp     [eax], dx
0x100501d4  jz      short loc_10050217
0x100501d6  push    edx; resolvedBase
0x100501d7  lea     eax, [esp+7Ch+resolvedURL]
0x100501db  push    eax; resolvedURL
0x100501dc  push    edx; baseURL2
0x100501dd  call    ?resolveURL@URL@@SGJPBG00PAPAG1@Z; URL::resolveURL(ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)
0x100501e2  mov     ebx, eax
0x100501e4  test    ebx, ebx
0x100501e6  js      short loc_10050213
0x100501e8  mov     edx, [edi+0ACh]; pSecMgr
0x100501ee  xor     eax, eax
0x100501f0  cmp     [edi+0BCh], eax
0x100501f6  push    eax; fZoneRelaxed
0x100501f7  push    [esp+7Ch+pwszSecureUrl]; pwszSecureUrl
0x100501fb  setnz   cl; fSecure
0x100501fe  push    eax; pwszBaseUrl
0x100501ff  push    [esp+84h+resolvedURL]; pwszReqUrl
0x10050203  call    ?accessAllowed@URL@@SGJ_NPAUIInternetSecurityManager@@PBG220@Z; URL::accessAllowed(bool,IInternetSecurityManager *,ushort const *,ushort const *,ushort const *,bool)
0x10050208  mov     ecx, [esp+78h+resolvedURL]; pv
0x1005020c  mov     ebx, eax
0x1005020e  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10050213  mov     ecx, [esp+78h+stat.pwcsName]
0x10050217  push    ecx; pv
0x10050218  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1005021e  jmp     short loc_10050252
0x10050220  xor     ebx, ebx
0x10050222  jmp     short loc_1005024E
0x10050224  lea     eax, [esp+78h+pSequentialStream]
0x10050228  mov     ecx, edi; this
0x1005022a  push    eax
0x1005022b  push    offset _IID_ISequentialStream
0x10050230  push    ebx
0x10050231  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10050237  call    edi
0x10050239  mov     ebx, eax
0x1005023b  test    ebx, ebx
0x1005023d  js      short loc_10050265
0x1005023f  mov     ecx, [esp+78h+pSequentialStream]; seqstream
0x10050243  lea     edx, [esp+78h+pStream]; ppStm
0x10050247  call    ?New@StreamWrapper@@SGJPAUISequentialStream@@PAPAUIStream@@@Z; StreamWrapper::New(ISequentialStream *,IStream * *)
0x1005024c  mov     ebx, eax
0x1005024e  mov     edi, [esp+78h+resolvedURL]
0x10050252  test    ebx, ebx
0x10050254  js      short loc_10050265
0x10050256  push    0; fpe
0x10050258  push    [esp+7Ch+pStream]; pStm
0x1005025c  mov     ecx, edi; this
0x1005025e  call    ?PushStream@XMLParser@@IAEJPAUIStream@@_N@Z; XMLParser::PushStream(IStream *,bool)
0x10050263  mov     ebx, eax
0x10050265  mov     ecx, [esp+78h+pSequentialStream]
0x10050269  test    ecx, ecx
0x1005026b  jz      short loc_10050285
0x1005026d  mov     eax, [ecx]
0x1005026f  push    ecx
0x10050270  mov     edi, [eax+8]
0x10050273  mov     ecx, edi; this
0x10050275  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005027b  call    edi
0x1005027d  mov     [esp+78h+pSequentialStream], 0
0x10050285  mov     ecx, [esp+78h+pStream]
0x10050289  test    ecx, ecx
0x1005028b  jz      short loc_100502A5
0x1005028d  mov     eax, [ecx]
0x1005028f  push    ecx
0x10050290  mov     edi, [eax+8]
0x10050293  mov     ecx, edi; this
0x10050295  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005029b  call    edi
0x1005029d  mov     [esp+78h+pStream], 0
0x100502a5  push    esi; lpCriticalSection
0x100502a6  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100502ac  mov     eax, ebx
0x100502ae  mov     ecx, [esp+78h+var_4]
0x100502b2  pop     edi
0x100502b3  pop     esi
0x100502b4  pop     ebx
0x100502b5  xor     ecx, esp; cookie
0x100502b7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100502bc  mov     esp, ebp
0x100502be  pop     ebp
0x100502bf  retn    8
```
