# URLMONRequest::_StaAsyncCallUrlMonStart(void)

- ea: `0x18015870c`
- end: `0x180158918`
- name: `?_StaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ`
- size: `524`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180093060`

## callees

- `0x18003617c`
- `0x180157d70`
- `0x18015870c`
- `0x180185008`
- `0x1801850e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158835`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158835`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180158827`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180158827`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180158871`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180158871`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015876f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015876f`

## pseudocode

```c
__int64 __fastcall URLMONRequest::_StaAsyncCallUrlMonStart(URLMONRequest *this)
{
  StaPrepareContext *v1; // rdi
  int Instance; // ebx
  IGlobalInterfaceTable *v4; // r14
  IUri *pUri; // rsi
  _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  StaPrepareContext *ppPrepareContext; // [rsp+30h] [rbp-10h] BYREF
  unsigned int dwGITCookie; // [rsp+78h] [rbp+38h] BYREF
  IGlobalInterfaceTable *pGIT; // [rsp+80h] [rbp+40h] BYREF
  StaPrepareContext *pStaPrepareContext; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  pGIT = 0;
  pStaPrepareContext = 0;
  dwGITCookie = 0;
  if ( (xmmword_1801F6C20 & 8) != 0 )
    WPP_SF_q(0x403u, 0x35u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)this);
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, (LPVOID *)&pGIT);
  if ( Instance >= 0 )
  {
    Instance = pGIT->RegisterInterfaceInGlobal(pGIT, this->_pRequestSite, &IID_IXmlHttpRequestInternal, &dwGITCookie);
    if ( Instance >= 0 )
    {
      v4 = pGIT;
      ppPrepareContext = 0;
      if ( pGIT && (pUri = this->_pUri) != 0 )
      {
        Instance = 0;
        v1 = (StaPrepareContext *)_MemAlloc(0x18u, 4);
        v1->pGIT = v4;
        v4->AddRef(v4);
        v1->dwCookie = dwGITCookie;
        dwGITCookie = 0;
        v1->pUri = pUri;
        pUri->AddRef(pUri);
        pStaPrepareContext = v1;
      }
      else
      {
        Instance = -2147024809;
      }
      _DeleteStaPrepareContext(&ppPrepareContext);
      if ( Instance >= 0 )
      {
        ThreadpoolWork = CreateThreadpoolWork(s_StaPrepareUrlMon, v1, 0);
        if ( ThreadpoolWork )
        {
          if ( (xmmword_1801F6C20 & 8) != 0 )
            WPP_SF_q(0x403u, 0x36u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (unsigned __int64)v1);
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
    ((void (__fastcall *)(IGlobalInterfaceTable *))pGIT->RevokeInterfaceFromGlobal)(pGIT);
    dwGITCookie = 0;
  }
  if ( pGIT )
  {
    pGIT->Release(pGIT);
    pGIT = 0;
  }
  _DeleteStaPrepareContext(&pStaPrepareContext);
  if ( (g_rgFastWppLevelEnabledFlags[2 * (Instance >> 31) + 4].rgbFlags[0] & 8) != 0 )
    WPP_SF_d(
      (((unsigned __int16)(Instance >> 31) + 2) << 9) | 3,
      0x37u,
      WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids,
      Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18015870c  push    rbp
0x18015870e  push    rbx
0x18015870f  push    rsi
0x180158710  push    rdi
0x180158711  push    r14
0x180158713  mov     rbp, rsp
0x180158716  sub     rsp, 40h
0x18015871a  xor     edi, edi
0x18015871c  mov     [rbp+pGIT], 0
0x180158724  mov     [rbp+pStaPrepareContext], rdi
0x180158728  mov     rsi, this
0x18015872b  mov     [rbp+dwGITCookie], 0
0x180158732  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180158739  jz      short loc_180158752
0x18015873b  lea     edx, [rdi+35h]; id
0x18015873e  mov     ecx, 403h; LevelKeyword
0x180158743  mov     r9, rsi; _a1
0x180158746  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015874d  call    WPP_SF_q
0x180158752  xor     edx, edx; pUnkOuter
0x180158754  lea     rax, [rbp+pGIT]
0x180158758  lea     r9, IID_IGlobalInterfaceTable; riid
0x18015875f  mov     [rsp+40h+ppv], rax; ppv
0x180158764  lea     this, CLSID_StdGlobalInterfaceTable; rclsid
0x18015876b  lea     r8d, [rdx+1]; dwClsContext
0x18015876f  call    cs:__imp_CoCreateInstance
0x180158775  mov     ebx, eax
0x180158777  test    eax, eax
0x180158779  js      $CleanUp_540
0x18015877f  mov     this, [rbp+pGIT]
0x180158783  lea     r9, [rbp+dwGITCookie]
0x180158787  mov     rdx, [rsi+0A0h]
0x18015878e  lea     r8, IID_IXmlHttpRequestInternal
0x180158795  mov     rax, [this]
0x180158798  mov     rax, [rax+18h]
0x18015879c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801587a1  mov     ebx, eax
0x1801587a3  test    eax, eax
0x1801587a5  js      $CleanUp_540
0x1801587ab  mov     r14, [rbp+pGIT]
0x1801587af  mov     [rbp+ppPrepareContext], rdi
0x1801587b3  test    r14, r14
0x1801587b6  jnz     short loc_1801587BF
0x1801587b8  mov     ebx, 80070057h
0x1801587bd  jmp     short loc_18015880D
0x1801587bf  mov     rsi, [rsi+0C0h]
0x1801587c6  test    rsi, rsi
0x1801587c9  jz      short loc_1801587B8
0x1801587cb  xor     ebx, ebx
0x1801587cd  lea     edx, [rbx+4]; dwFlags
0x1801587d0  lea     ecx, [rbx+18h]; cb
0x1801587d3  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801587d8  mov     rdi, rax
0x1801587db  mov     this, r14
0x1801587de  mov     [rax], r14
0x1801587e1  mov     rax, [r14]
0x1801587e4  mov     rax, [rax+8]
0x1801587e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801587ed  mov     eax, [rbp+dwGITCookie]
0x1801587f0  mov     this, rsi
0x1801587f3  mov     [rdi+8], eax
0x1801587f6  mov     [rbp+dwGITCookie], ebx
0x1801587f9  mov     [rdi+10h], rsi
0x1801587fd  mov     rax, [rsi]
0x180158800  mov     rax, [rax+8]
0x180158804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158809  mov     [rbp+pStaPrepareContext], rdi
0x18015880d  lea     this, [rbp+ppPrepareContext]; ppPrepareContext
0x180158811  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x180158816  test    ebx, ebx
0x180158818  js      short $CleanUp_540
0x18015881a  xor     r8d, r8d; pcbe
0x18015881d  lea     this, ?s_StaPrepareUrlMon@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180158824  mov     rdx, rdi; pv
0x180158827  call    cs:__imp_CreateThreadpoolWork
0x18015882d  mov     rsi, rax
0x180158830  test    rax, rax
0x180158833  jnz     short loc_18015884C
0x180158835  call    cs:__imp_GetLastError
0x18015883b  mov     ebx, eax
0x18015883d  test    eax, eax
0x18015883f  jle     short $CleanUp_540
0x180158841  movzx   ebx, ax
0x180158844  or      ebx, 80070000h
0x18015884a  jmp     short $CleanUp_540
0x18015884c  test    byte ptr cs:xmmword_1801F6C20, 8; __annotation("TMF:",
0x180158853  jz      short loc_18015886E
0x180158855  mov     edx, 36h ; '6'; id
0x18015885a  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x180158861  mov     ecx, 403h; LevelKeyword
0x180158866  mov     r9, rdi; _a1
0x180158869  call    WPP_SF_q
0x18015886e  mov     this, rsi; pwk
0x180158871  call    cs:__imp_SubmitThreadpoolWork
0x180158877  mov     [rbp+pStaPrepareContext], 0
0x18015887f  mov     edx, [rbp+dwGITCookie]
0x180158882  test    edx, edx
0x180158884  jz      short loc_18015889D
0x180158886  mov     this, [rbp+pGIT]
0x18015888a  mov     rax, [this]
0x18015888d  mov     rax, [rax+20h]
0x180158891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158896  mov     [rbp+dwGITCookie], 0
0x18015889d  mov     this, [rbp+pGIT]
0x1801588a1  test    this, this
0x1801588a4  jz      short loc_1801588BA
0x1801588a6  mov     rax, [this]
0x1801588a9  mov     rax, [rax+10h]
0x1801588ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801588b2  mov     [rbp+pGIT], 0
0x1801588ba  lea     this, [rbp+pStaPrepareContext]; ppPrepareContext
0x1801588be  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x1801588c3  mov     r9d, ebx; __annotation("TMF:",
0x1801588c6  sar     r9d, 1Fh
0x1801588ca  lea     eax, ds:4[r9*2]
0x1801588d2  movsxd  this, eax
0x1801588d5  lea     rax, g_rgFastWppLevelEnabledFlags
0x1801588dc  test    byte ptr [rax+this*8], 8
0x1801588e0  jz      short loc_18015890B
0x1801588e2  add     r9w, 2
0x1801588e7  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1801588ee  movzx   ecx, r9w
0x1801588f2  mov     eax, 200h
0x1801588f7  imul    ecx, eax
0x1801588fa  mov     edx, 37h ; '7'; id
0x1801588ff  mov     r9d, ebx; _a1
0x180158902  or      cx, 3; LevelKeyword
0x180158906  call    WPP_SF_d
0x18015890b  mov     eax, ebx
0x18015890d  add     rsp, 40h
0x180158911  pop     r14
0x180158913  pop     rdi
0x180158914  pop     rsi
0x180158915  pop     rbx
0x180158916  pop     rbp
0x180158917  retn
```
