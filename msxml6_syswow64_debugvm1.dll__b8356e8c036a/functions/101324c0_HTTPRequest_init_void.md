# HTTPRequest::init(void)

- ea: `0x101324c0`
- end: `0x1013259d`
- name: `?init@HTTPRequest@@UAEJXZ`
- size: `221`
- prototype: `HRESULT __thiscall(HTTPRequest *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x101325b0`

## callees

- `0x10067bc0`
- `0x101324c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101324e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x101324e8`

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
0x101324c0  mov     edi, edi
0x101324c2  push    ebp
0x101324c3  mov     ebp, esp
0x101324c5  push    this
0x101324c6  push    ebx
0x101324c7  mov     ebx, this
0x101324c9  push    esi
0x101324ca  push    edi
0x101324cb  xor     edi, edi
0x101324cd  lea     esi, [ebx+0B0h]
0x101324d3  mov     [ebp+pIConnectionPointContainer], edi
0x101324d6  cmp     [esi], edi
0x101324d8  jnz     short loc_1013250B
0x101324da  push    esi; ppv
0x101324db  push    offset _IID_IWinHttpRequest; riid
0x101324e0  push    1; dwClsContext
0x101324e2  push    edi; pUnkOuter
0x101324e3  push    offset ?CLSID_WinHttpRequest51@@3U_GUID@@B; rclsid
0x101324e8  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x101324ee  mov     edi, eax
0x101324f0  test    edi, edi
0x101324f2  jns     short loc_1013250B
0x101324f4  cmp     edi, 80040154h
0x101324fa  jz      short loc_10132504
0x101324fc  cmp     edi, 8007007Eh
0x10132502  jnz     short CleanUp_455
0x10132504  mov     edi, 0C00CE23Bh
0x10132509  jmp     short CleanUp_455
0x1013250b  cmp     dword ptr [ebx+0B8h], 0
0x10132512  jnz     short CleanUp_455
0x10132514  mov     this, [esi]
0x10132516  mov     eax, [this]
0x10132518  mov     esi, [eax]
0x1013251a  lea     eax, [ebp+pIConnectionPointContainer]
0x1013251d  push    eax
0x1013251e  push    offset _IID_IConnectionPointContainer
0x10132523  push    this
0x10132524  mov     this, esi; this
0x10132526  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013252c  call    esi
0x1013252e  mov     edi, eax
0x10132530  test    edi, edi
0x10132532  js      short CleanUp_455
0x10132534  mov     this, [ebp+pIConnectionPointContainer]
0x10132537  mov     eax, [this]
0x10132539  mov     esi, [eax+10h]
0x1013253c  lea     eax, [ebx+0B4h]
0x10132542  push    eax
0x10132543  push    offset _IID_IWinHttpRequestEvents
0x10132548  push    this
0x10132549  mov     this, esi; this
0x1013254b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10132551  call    esi
0x10132553  mov     edi, eax
0x10132555  test    edi, edi
0x10132557  js      short CleanUp_455
0x10132559  mov     this, [ebx+0B4h]
0x1013255f  mov     eax, [this]
0x10132561  mov     esi, [eax+14h]
0x10132564  lea     eax, [ebx+0B8h]
0x1013256a  push    eax
0x1013256b  lea     eax, [ebx+0BCh]
0x10132571  push    eax
0x10132572  push    this
0x10132573  mov     this, esi; this
0x10132575  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013257b  call    esi
0x1013257d  mov     edi, eax
0x1013257f  mov     this, [ebp+pIConnectionPointContainer]
0x10132582  test    this, this
0x10132584  jz      short loc_10132596
0x10132586  mov     eax, [this]
0x10132588  push    this
0x10132589  mov     esi, [eax+8]
0x1013258c  mov     this, esi; this
0x1013258e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10132594  call    esi
0x10132596  mov     eax, edi
0x10132598  pop     edi
0x10132599  pop     esi
0x1013259a  pop     ebx
0x1013259b  leave
0x1013259c  retn
```
