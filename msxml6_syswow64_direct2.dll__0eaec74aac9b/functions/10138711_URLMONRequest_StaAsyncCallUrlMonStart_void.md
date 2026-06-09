# URLMONRequest::_StaAsyncCallUrlMonStart(void)

- ea: `0x10138711`
- end: `0x10138876`
- name: `?_StaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ`
- size: `357`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1013a000`

## callees

- `0x10067b20`
- `0x1013740d`
- `0x1013749d`
- `0x10138711`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101387b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101387b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x101387ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x101387ad`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101387ef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101387ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10138756`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10138756`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::_StaAsyncCallUrlMonStart(URLMONRequest *this)
{
  int Instance; // edi
  _TP_WORK *ThreadpoolWork; // esi
  signed int LastError; // eax
  StaPrepareContext *pStaPrepareContext; // [esp+Ch] [ebp-Ch] BYREF
  unsigned int dwGITCookie; // [esp+10h] [ebp-8h] BYREF
  IGlobalInterfaceTable *pGIT; // [esp+14h] [ebp-4h] BYREF

  pGIT = 0;
  dwGITCookie = 0;
  pStaPrepareContext = 0;
  if ( (byte_10185760[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x35u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, (LPVOID *)&pGIT);
  if ( Instance >= 0 )
  {
    Instance = ((int (__thiscall *)(HRESULT (__stdcall *)(IGlobalInterfaceTable *, IUnknown *, const _GUID *, unsigned int *), IGlobalInterfaceTable *, IURLRequestSite *, GUID *, unsigned int *))pGIT->RegisterInterfaceInGlobal)(
                 pGIT->RegisterInterfaceInGlobal,
                 pGIT,
                 this->_pRequestSite,
                 &IID_IXmlHttpRequestInternal,
                 &dwGITCookie);
    if ( Instance >= 0 )
    {
      Instance = _CreateStaPrepareContext(pGIT, &dwGITCookie, this->_pUri, &pStaPrepareContext);
      if ( Instance >= 0 )
      {
        ThreadpoolWork = CreateThreadpoolWork(s_StaPrepareUrlMon, pStaPrepareContext, 0);
        if ( ThreadpoolWork )
        {
          if ( (byte_10185760[0] & 8) != 0 )
            WPP_SF_q(0x403u, 0x36u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)pStaPrepareContext);
          SubmitThreadpoolWork(ThreadpoolWork);
          pStaPrepareContext = 0;
        }
        else
        {
          LastError = GetLastError();
          Instance = LastError;
          if ( LastError > 0 )
            Instance = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  if ( dwGITCookie )
  {
    ((void (__thiscall *)(HRESULT (__stdcall *)(IGlobalInterfaceTable *, unsigned int), IGlobalInterfaceTable *, unsigned int))pGIT->RevokeInterfaceFromGlobal)(
      pGIT->RevokeInterfaceFromGlobal,
      pGIT,
      dwGITCookie);
    dwGITCookie = 0;
  }
  if ( pGIT )
  {
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IGlobalInterfaceTable *))pGIT->Release)(
      pGIT->Release,
      pGIT);
    pGIT = 0;
  }
  _DeleteStaPrepareContext(&pStaPrepareContext);
  if ( (byte_10185760[16 * (Instance >> 31)] & 8) != 0 )
    WPP_SF_q(
      (((unsigned __int16)(Instance >> 31) + 2) << 9) | 3,
      0x37u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      Instance);
  return Instance;
}

```

## disassembly

```asm
0x10138711  mov     edi, edi
0x10138713  push    ebp
0x10138714  mov     ebp, esp
0x10138716  sub     esp, 0Ch
0x10138719  push    ebx
0x1013871a  push    esi
0x1013871b  xor     esi, esi
0x1013871d  mov     ebx, this
0x1013871f  push    edi
0x10138720  mov     [ebp+pGIT], esi
0x10138723  mov     [ebp+dwGITCookie], esi
0x10138726  mov     [ebp+pStaPrepareContext], esi
0x10138729  test    byte_10185760, 8; __annotation("TMF:",
0x10138730  jz      short loc_10138745
0x10138732  push    ebx; _a1
0x10138733  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138738  push    35h ; '5'
0x1013873a  pop     edx; id
0x1013873b  mov     this, 403h; LevelKeyword
0x10138740  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10138745  lea     eax, [ebp+pGIT]
0x10138748  push    eax; ppv
0x10138749  push    offset _IID_IGlobalInterfaceTable; riid
0x1013874e  push    1; dwClsContext
0x10138750  push    esi; pUnkOuter
0x10138751  push    offset _CLSID_StdGlobalInterfaceTable; rclsid
0x10138756  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1013875c  mov     edi, eax
0x1013875e  test    edi, edi
0x10138760  js      CleanUp_503
0x10138766  mov     this, [ebp+pGIT]
0x10138769  mov     eax, [this]
0x1013876b  mov     esi, [eax+0Ch]
0x1013876e  lea     eax, [ebp+dwGITCookie]
0x10138771  push    eax
0x10138772  push    offset _IID_IXmlHttpRequestInternal
0x10138777  push    dword ptr [ebx+5Ch]
0x1013877a  push    this
0x1013877b  mov     this, esi; this
0x1013877d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138783  call    esi
0x10138785  mov     edi, eax
0x10138787  test    edi, edi
0x10138789  js      short CleanUp_503
0x1013878b  mov     this, [ebp+pGIT]; pGIT
0x1013878e  lea     eax, [ebp+pStaPrepareContext]
0x10138791  push    eax; ppPrepareContext
0x10138792  push    dword ptr [ebx+6Ch]; pUri
0x10138795  lea     edx, [ebp+dwGITCookie]; pdwCookie
0x10138798  call    ?_CreateStaPrepareContext@@YGJPAUIGlobalInterfaceTable@@PAKPAUIUri@@PAPAUStaPrepareContext@@@Z; _CreateStaPrepareContext(IGlobalInterfaceTable *,ulong *,IUri *,StaPrepareContext * *)
0x1013879d  mov     edi, eax
0x1013879f  test    edi, edi
0x101387a1  js      short CleanUp_503
0x101387a3  push    0; pcbe
0x101387a5  push    [ebp+pStaPrepareContext]; pv
0x101387a8  push    offset ?s_StaPrepareUrlMon@@YGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z; pfnwk
0x101387ad  call    ds:__imp__CreateThreadpoolWork@12; CreateThreadpoolWork(x,x,x)
0x101387b3  mov     esi, eax
0x101387b5  test    esi, esi
0x101387b7  jnz     short loc_101387D0
0x101387b9  call    ds:__imp__GetLastError@0; GetLastError()
0x101387bf  mov     edi, eax
0x101387c1  test    edi, edi
0x101387c3  jle     short CleanUp_503
0x101387c5  movzx   edi, di
0x101387c8  or      edi, 80070000h
0x101387ce  jmp     short CleanUp_503
0x101387d0  test    byte_10185760, 8; __annotation("TMF:",
0x101387d7  jz      short loc_101387EE
0x101387d9  push    [ebp+pStaPrepareContext]; _a1
0x101387dc  mov     this, 403h; LevelKeyword
0x101387e1  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101387e6  push    36h ; '6'
0x101387e8  pop     edx; id
0x101387e9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101387ee  push    esi; pwk
0x101387ef  call    ds:__imp__SubmitThreadpoolWork@4; SubmitThreadpoolWork(x)
0x101387f5  mov     [ebp+pStaPrepareContext], 0
0x101387fc  cmp     [ebp+dwGITCookie], 0
0x10138800  jz      short loc_1013881F
0x10138802  mov     eax, [ebp+pGIT]
0x10138805  push    [ebp+dwGITCookie]
0x10138808  push    eax
0x10138809  mov     this, [eax]
0x1013880b  mov     esi, [this+10h]
0x1013880e  mov     this, esi; this
0x10138810  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138816  call    esi
0x10138818  mov     [ebp+dwGITCookie], 0
0x1013881f  mov     this, [ebp+pGIT]
0x10138822  test    this, this
0x10138824  jz      short loc_1013883D
0x10138826  mov     eax, [this]
0x10138828  push    this
0x10138829  mov     esi, [eax+8]
0x1013882c  mov     this, esi; this
0x1013882e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138834  call    esi
0x10138836  mov     [ebp+pGIT], 0
0x1013883d  lea     this, [ebp+pStaPrepareContext]; ppPrepareContext
0x10138840  call    ?_DeleteStaPrepareContext@@YGXPAPAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x10138845  mov     this, edi; __annotation("TMF:",
0x10138847  sar     this, 1Fh
0x1013884a  mov     eax, this
0x1013884c  shl     eax, 4
0x1013884f  test    byte_10185760[eax], 8
0x10138856  jz      short loc_1013886F
0x10138858  push    edi; _a1
0x10138859  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013885e  add     this, 2
0x10138861  shl     this, 9
0x10138864  push    37h ; '7'
0x10138866  or      this, 3; LevelKeyword
0x10138869  pop     edx; id
0x1013886a  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013886f  mov     eax, edi
0x10138871  pop     edi
0x10138872  pop     esi
0x10138873  pop     ebx
0x10138874  leave
0x10138875  retn
```
