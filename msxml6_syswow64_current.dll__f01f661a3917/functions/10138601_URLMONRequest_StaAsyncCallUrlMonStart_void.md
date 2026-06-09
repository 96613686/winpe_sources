# URLMONRequest::_StaAsyncCallUrlMonStart(void)

- ea: `0x10138601`
- end: `0x10138766`
- name: `?_StaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ`
- size: `357`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x10139ef0`

## callees

- `0x10067bc0`
- `0x101372fd`
- `0x1013738d`
- `0x10138601`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101386a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x101386a9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1013869d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1013869d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101386df`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101386df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10138646`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10138646`

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
  if ( (byte_101857A0[0] & 8) != 0 )
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
          if ( (byte_101857A0[0] & 8) != 0 )
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
  if ( (byte_101857A0[16 * (Instance >> 31)] & 8) != 0 )
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
0x10138601  mov     edi, edi
0x10138603  push    ebp
0x10138604  mov     ebp, esp
0x10138606  sub     esp, 0Ch
0x10138609  push    ebx
0x1013860a  push    esi
0x1013860b  xor     esi, esi
0x1013860d  mov     ebx, this
0x1013860f  push    edi
0x10138610  mov     [ebp+pGIT], esi
0x10138613  mov     [ebp+dwGITCookie], esi
0x10138616  mov     [ebp+pStaPrepareContext], esi
0x10138619  test    byte_101857A0, 8; __annotation("TMF:",
0x10138620  jz      short loc_10138635
0x10138622  push    ebx; _a1
0x10138623  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10138628  push    35h ; '5'
0x1013862a  pop     edx; id
0x1013862b  mov     this, 403h; LevelKeyword
0x10138630  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10138635  lea     eax, [ebp+pGIT]
0x10138638  push    eax; ppv
0x10138639  push    offset _IID_IGlobalInterfaceTable; riid
0x1013863e  push    1; dwClsContext
0x10138640  push    esi; pUnkOuter
0x10138641  push    offset _CLSID_StdGlobalInterfaceTable; rclsid
0x10138646  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1013864c  mov     edi, eax
0x1013864e  test    edi, edi
0x10138650  js      CleanUp_503
0x10138656  mov     this, [ebp+pGIT]
0x10138659  mov     eax, [this]
0x1013865b  mov     esi, [eax+0Ch]
0x1013865e  lea     eax, [ebp+dwGITCookie]
0x10138661  push    eax
0x10138662  push    offset _IID_IXmlHttpRequestInternal
0x10138667  push    dword ptr [ebx+5Ch]
0x1013866a  push    this
0x1013866b  mov     this, esi; this
0x1013866d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138673  call    esi
0x10138675  mov     edi, eax
0x10138677  test    edi, edi
0x10138679  js      short CleanUp_503
0x1013867b  mov     this, [ebp+pGIT]; pGIT
0x1013867e  lea     eax, [ebp+pStaPrepareContext]
0x10138681  push    eax; ppPrepareContext
0x10138682  push    dword ptr [ebx+6Ch]; pUri
0x10138685  lea     edx, [ebp+dwGITCookie]; pdwCookie
0x10138688  call    ?_CreateStaPrepareContext@@YGJPAUIGlobalInterfaceTable@@PAKPAUIUri@@PAPAUStaPrepareContext@@@Z; _CreateStaPrepareContext(IGlobalInterfaceTable *,ulong *,IUri *,StaPrepareContext * *)
0x1013868d  mov     edi, eax
0x1013868f  test    edi, edi
0x10138691  js      short CleanUp_503
0x10138693  push    0; pcbe
0x10138695  push    [ebp+pStaPrepareContext]; pv
0x10138698  push    offset ?s_StaPrepareUrlMon@@YGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z; pfnwk
0x1013869d  call    ds:__imp__CreateThreadpoolWork@12; CreateThreadpoolWork(x,x,x)
0x101386a3  mov     esi, eax
0x101386a5  test    esi, esi
0x101386a7  jnz     short loc_101386C0
0x101386a9  call    ds:__imp__GetLastError@0; GetLastError()
0x101386af  mov     edi, eax
0x101386b1  test    edi, edi
0x101386b3  jle     short CleanUp_503
0x101386b5  movzx   edi, di
0x101386b8  or      edi, 80070000h
0x101386be  jmp     short CleanUp_503
0x101386c0  test    byte_101857A0, 8; __annotation("TMF:",
0x101386c7  jz      short loc_101386DE
0x101386c9  push    [ebp+pStaPrepareContext]; _a1
0x101386cc  mov     this, 403h; LevelKeyword
0x101386d1  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101386d6  push    36h ; '6'
0x101386d8  pop     edx; id
0x101386d9  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101386de  push    esi; pwk
0x101386df  call    ds:__imp__SubmitThreadpoolWork@4; SubmitThreadpoolWork(x)
0x101386e5  mov     [ebp+pStaPrepareContext], 0
0x101386ec  cmp     [ebp+dwGITCookie], 0
0x101386f0  jz      short loc_1013870F
0x101386f2  mov     eax, [ebp+pGIT]
0x101386f5  push    [ebp+dwGITCookie]
0x101386f8  push    eax
0x101386f9  mov     this, [eax]
0x101386fb  mov     esi, [this+10h]
0x101386fe  mov     this, esi; this
0x10138700  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138706  call    esi
0x10138708  mov     [ebp+dwGITCookie], 0
0x1013870f  mov     this, [ebp+pGIT]
0x10138712  test    this, this
0x10138714  jz      short loc_1013872D
0x10138716  mov     eax, [this]
0x10138718  push    this
0x10138719  mov     esi, [eax+8]
0x1013871c  mov     this, esi; this
0x1013871e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10138724  call    esi
0x10138726  mov     [ebp+pGIT], 0
0x1013872d  lea     this, [ebp+pStaPrepareContext]; ppPrepareContext
0x10138730  call    ?_DeleteStaPrepareContext@@YGXPAPAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x10138735  mov     this, edi; __annotation("TMF:",
0x10138737  sar     this, 1Fh
0x1013873a  mov     eax, this
0x1013873c  shl     eax, 4
0x1013873f  test    byte_101857A0[eax], 8
0x10138746  jz      short loc_1013875F
0x10138748  push    edi; _a1
0x10138749  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013874e  add     this, 2
0x10138751  shl     this, 9
0x10138754  push    37h ; '7'
0x10138756  or      this, 3; LevelKeyword
0x10138759  pop     edx; id
0x1013875a  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x1013875f  mov     eax, edi
0x10138761  pop     edi
0x10138762  pop     esi
0x10138763  pop     ebx
0x10138764  leave
0x10138765  retn
```
