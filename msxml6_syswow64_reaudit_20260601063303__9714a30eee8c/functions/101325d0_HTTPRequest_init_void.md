# HTTPRequest::init(void)

- ea: `0x101325d0`
- end: `0x101326ad`
- name: `?init@HTTPRequest@@UAEJXZ`
- size: `221`
- prototype: `HRESULT __thiscall(HTTPRequest *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x101326c0`

## callees

- `0x10067b20`
- `0x101325d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101325f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101325f8`

## pseudocode

```c
HRESULT __thiscall HTTPRequest::init(HTTPRequest *this)
{
  int v2; // edi
  IWinHttpRequest **p_pIWinHttpRequest; // esi
  HRESULT Instance; // eax
  HRESULT (__stdcall *Advise)(IConnectionPoint *, IUnknown *, unsigned int *); // ecx
  IConnectionPointContainer *pIConnectionPointContainer; // [esp+Ch] [ebp-4h] BYREF

  v2 = 0;
  p_pIWinHttpRequest = &this->_pIWinHttpRequest;
  pIConnectionPointContainer = 0;
  if ( this->_pIWinHttpRequest
    || (Instance = CoCreateInstance(
                     &CLSID_WinHttpRequest51,
                     0,
                     1u,
                     &IID_IWinHttpRequest,
                     (LPVOID *)&this->_pIWinHttpRequest),
        v2 = Instance,
        Instance >= 0) )
  {
    if ( !this->_dwCookieHttpRequestEvents )
    {
      v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IDispatch *, const _GUID *, void **), IWinHttpRequest *, GUID *, IConnectionPointContainer **))(*p_pIWinHttpRequest)->QueryInterface)(
             (*p_pIWinHttpRequest)->QueryInterface,
             *p_pIWinHttpRequest,
             &IID_IConnectionPointContainer,
             &pIConnectionPointContainer);
      if ( v2 >= 0 )
      {
        v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IConnectionPointContainer *, const _GUID *, IConnectionPoint **), IConnectionPointContainer *, GUID *, IConnectionPoint **))pIConnectionPointContainer->FindConnectionPoint)(
               pIConnectionPointContainer->FindConnectionPoint,
               pIConnectionPointContainer,
               &IID_IWinHttpRequestEvents,
               &this->_pWinHttpConnPt);
        if ( v2 >= 0 )
        {
          Advise = this->_pWinHttpConnPt->Advise;
          v2 = ((int (__thiscall *)(HRESULT (__stdcall *)(IConnectionPoint *, IUnknown *, unsigned int *), IConnectionPoint *, HTTPRequest::HTTPRequestSink *, unsigned int *))Advise)(
                 Advise,
                 this->_pWinHttpConnPt,
                 &this->_WinHttpRequestSink,
                 &this->_dwCookieHttpRequestEvents);
        }
      }
    }
  }
  else if ( Instance == -2147221164 || Instance == -2147024770 )
  {
    v2 = -1072897477;
  }
  if ( pIConnectionPointContainer )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IConnectionPointContainer *))pIConnectionPointContainer->Release)(
      pIConnectionPointContainer->Release,
      pIConnectionPointContainer);
  return v2;
}

```

## disassembly

```asm
0x101325d0  mov     edi, edi
0x101325d2  push    ebp
0x101325d3  mov     ebp, esp
0x101325d5  push    this
0x101325d6  push    ebx
0x101325d7  mov     ebx, this
0x101325d9  push    esi
0x101325da  push    edi
0x101325db  xor     edi, edi
0x101325dd  lea     esi, [ebx+0B0h]
0x101325e3  mov     [ebp+pIConnectionPointContainer], edi
0x101325e6  cmp     [esi], edi
0x101325e8  jnz     short loc_1013261B
0x101325ea  push    esi; ppv
0x101325eb  push    offset _IID_IWinHttpRequest; riid
0x101325f0  push    1; dwClsContext
0x101325f2  push    edi; pUnkOuter
0x101325f3  push    offset ?CLSID_WinHttpRequest51@@3U_GUID@@B; rclsid
0x101325f8  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x101325fe  mov     edi, eax
0x10132600  test    edi, edi
0x10132602  jns     short loc_1013261B
0x10132604  cmp     edi, 80040154h
0x1013260a  jz      short loc_10132614
0x1013260c  cmp     edi, 8007007Eh
0x10132612  jnz     short CleanUp_455
0x10132614  mov     edi, 0C00CE23Bh
0x10132619  jmp     short CleanUp_455
0x1013261b  cmp     dword ptr [ebx+0B8h], 0
0x10132622  jnz     short CleanUp_455
0x10132624  mov     this, [esi]
0x10132626  mov     eax, [this]
0x10132628  mov     esi, [eax]
0x1013262a  lea     eax, [ebp+pIConnectionPointContainer]
0x1013262d  push    eax
0x1013262e  push    offset _IID_IConnectionPointContainer
0x10132633  push    this
0x10132634  mov     this, esi; this
0x10132636  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013263c  call    esi
0x1013263e  mov     edi, eax
0x10132640  test    edi, edi
0x10132642  js      short CleanUp_455
0x10132644  mov     this, [ebp+pIConnectionPointContainer]
0x10132647  mov     eax, [this]
0x10132649  mov     esi, [eax+10h]
0x1013264c  lea     eax, [ebx+0B4h]
0x10132652  push    eax
0x10132653  push    offset _IID_IWinHttpRequestEvents
0x10132658  push    this
0x10132659  mov     this, esi; this
0x1013265b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10132661  call    esi
0x10132663  mov     edi, eax
0x10132665  test    edi, edi
0x10132667  js      short CleanUp_455
0x10132669  mov     this, [ebx+0B4h]
0x1013266f  mov     eax, [this]
0x10132671  mov     esi, [eax+14h]
0x10132674  lea     eax, [ebx+0B8h]
0x1013267a  push    eax
0x1013267b  lea     eax, [ebx+0BCh]
0x10132681  push    eax
0x10132682  push    this
0x10132683  mov     this, esi; this
0x10132685  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013268b  call    esi
0x1013268d  mov     edi, eax
0x1013268f  mov     this, [ebp+pIConnectionPointContainer]
0x10132692  test    this, this
0x10132694  jz      short loc_101326A6
0x10132696  mov     eax, [this]
0x10132698  push    this
0x10132699  mov     esi, [eax+8]
0x1013269c  mov     this, esi; this
0x1013269e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x101326a4  call    esi
0x101326a6  mov     eax, edi
0x101326a8  pop     edi
0x101326a9  pop     esi
0x101326aa  pop     ebx
0x101326ab  leave
0x101326ac  retn
```
