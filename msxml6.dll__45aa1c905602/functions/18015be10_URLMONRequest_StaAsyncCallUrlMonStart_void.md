# URLMONRequest::_StaAsyncCallUrlMonStart(void)

- ea: `0x18015be10`
- end: `0x18015c035`
- name: `?_StaAsyncCallUrlMonStart@URLMONRequest@@IEAAJXZ`
- size: `549`
- prototype: `HRESULT __fastcall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180093030`

## callees

- `0x1800101e4`
- `0x18015b448`
- `0x18015be10`
- `0x180189008`
- `0x1801890e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015bf45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015bf45`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18015bf31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18015bf31`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18015bf87`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18015bf87`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015be73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015be73`

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
  if ( (xmmword_1801FAD20 & 8) != 0 )
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
        v1 = (StaPrepareContext *)_MemAlloc(0x18u, 4u);
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
          if ( (xmmword_1801FAD20 & 8) != 0 )
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
0x18015be10  push    rbp
0x18015be12  push    rbx
0x18015be13  push    rsi
0x18015be14  push    rdi
0x18015be15  push    r14
0x18015be17  mov     rbp, rsp
0x18015be1a  sub     rsp, 40h
0x18015be1e  xor     edi, edi
0x18015be20  mov     [rbp+pGIT], 0
0x18015be28  mov     [rbp+pStaPrepareContext], rdi
0x18015be2c  mov     rsi, this
0x18015be2f  mov     [rbp+dwGITCookie], 0
0x18015be36  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015be3d  jz      short loc_18015BE56
0x18015be3f  lea     edx, [rdi+35h]; id
0x18015be42  mov     ecx, 403h; LevelKeyword
0x18015be47  mov     r9, rsi; _a1
0x18015be4a  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015be51  call    WPP_SF_q
0x18015be56  xor     edx, edx; pUnkOuter
0x18015be58  lea     rax, [rbp+pGIT]
0x18015be5c  lea     r9, IID_IGlobalInterfaceTable; riid
0x18015be63  mov     [rsp+40h+ppv], rax; ppv
0x18015be68  lea     this, CLSID_StdGlobalInterfaceTable; rclsid
0x18015be6f  lea     r8d, [rdx+1]; dwClsContext
0x18015be73  call    cs:__imp_CoCreateInstance
0x18015be7a  nop     dword ptr [rax+rax+00h]
0x18015be7f  mov     ebx, eax
0x18015be81  test    eax, eax
0x18015be83  js      $CleanUp_540
0x18015be89  mov     this, [rbp+pGIT]
0x18015be8d  lea     r9, [rbp+dwGITCookie]
0x18015be91  mov     rdx, [rsi+0A0h]
0x18015be98  lea     r8, IID_IXmlHttpRequestInternal
0x18015be9f  mov     rax, [this]
0x18015bea2  mov     rax, [rax+18h]
0x18015bea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015beab  mov     ebx, eax
0x18015bead  test    eax, eax
0x18015beaf  js      $CleanUp_540
0x18015beb5  mov     r14, [rbp+pGIT]
0x18015beb9  mov     [rbp+ppPrepareContext], rdi
0x18015bebd  test    r14, r14
0x18015bec0  jnz     short loc_18015BEC9
0x18015bec2  mov     ebx, 80070057h
0x18015bec7  jmp     short loc_18015BF17
0x18015bec9  mov     rsi, [rsi+0C0h]
0x18015bed0  test    rsi, rsi
0x18015bed3  jz      short loc_18015BEC2
0x18015bed5  xor     ebx, ebx
0x18015bed7  lea     edx, [rbx+4]; dwFlags
0x18015beda  lea     ecx, [rbx+18h]; cb
0x18015bedd  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x18015bee2  mov     rdi, rax
0x18015bee5  mov     this, r14
0x18015bee8  mov     [rax], r14
0x18015beeb  mov     rax, [r14]
0x18015beee  mov     rax, [rax+8]
0x18015bef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bef7  mov     eax, [rbp+dwGITCookie]
0x18015befa  mov     this, rsi
0x18015befd  mov     [rdi+8], eax
0x18015bf00  mov     [rbp+dwGITCookie], ebx
0x18015bf03  mov     [rdi+10h], rsi
0x18015bf07  mov     rax, [rsi]
0x18015bf0a  mov     rax, [rax+8]
0x18015bf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bf13  mov     [rbp+pStaPrepareContext], rdi
0x18015bf17  lea     this, [rbp+ppPrepareContext]; ppPrepareContext
0x18015bf1b  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x18015bf20  test    ebx, ebx
0x18015bf22  js      short $CleanUp_540
0x18015bf24  xor     r8d, r8d; pcbe
0x18015bf27  lea     this, ?s_StaPrepareUrlMon@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18015bf2e  mov     rdx, rdi; pv
0x18015bf31  call    cs:__imp_CreateThreadpoolWork
0x18015bf38  nop     dword ptr [rax+rax+00h]
0x18015bf3d  mov     rsi, rax
0x18015bf40  test    rax, rax
0x18015bf43  jnz     short loc_18015BF62
0x18015bf45  call    cs:__imp_GetLastError
0x18015bf4c  nop     dword ptr [rax+rax+00h]
0x18015bf51  mov     ebx, eax
0x18015bf53  test    eax, eax
0x18015bf55  jle     short $CleanUp_540
0x18015bf57  movzx   ebx, ax
0x18015bf5a  or      ebx, 80070000h
0x18015bf60  jmp     short $CleanUp_540
0x18015bf62  test    byte ptr cs:xmmword_1801FAD20, 8; __annotation("TMF:",
0x18015bf69  jz      short loc_18015BF84
0x18015bf6b  mov     edx, 36h ; '6'; id
0x18015bf70  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015bf77  mov     ecx, 403h; LevelKeyword
0x18015bf7c  mov     r9, rdi; _a1
0x18015bf7f  call    WPP_SF_q
0x18015bf84  mov     this, rsi; pwk
0x18015bf87  call    cs:__imp_SubmitThreadpoolWork
0x18015bf8e  nop     dword ptr [rax+rax+00h]
0x18015bf93  mov     [rbp+pStaPrepareContext], 0
0x18015bf9b  mov     edx, [rbp+dwGITCookie]
0x18015bf9e  test    edx, edx
0x18015bfa0  jz      short loc_18015BFB9
0x18015bfa2  mov     this, [rbp+pGIT]
0x18015bfa6  mov     rax, [this]
0x18015bfa9  mov     rax, [rax+20h]
0x18015bfad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bfb2  mov     [rbp+dwGITCookie], 0
0x18015bfb9  mov     this, [rbp+pGIT]
0x18015bfbd  test    this, this
0x18015bfc0  jz      short loc_18015BFD6
0x18015bfc2  mov     rax, [this]
0x18015bfc5  mov     rax, [rax+10h]
0x18015bfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bfce  mov     [rbp+pGIT], 0
0x18015bfd6  lea     this, [rbp+pStaPrepareContext]; ppPrepareContext
0x18015bfda  call    ?_DeleteStaPrepareContext@@YAXPEAPEAUStaPrepareContext@@@Z; _DeleteStaPrepareContext(StaPrepareContext * *)
0x18015bfdf  mov     r9d, ebx; __annotation("TMF:",
0x18015bfe2  sar     r9d, 1Fh
0x18015bfe6  lea     eax, ds:4[r9*2]
0x18015bfee  movsxd  this, eax
0x18015bff1  lea     rax, g_rgFastWppLevelEnabledFlags
0x18015bff8  test    byte ptr [rax+this*8], 8
0x18015bffc  jz      short loc_18015C027
0x18015bffe  add     r9w, 2
0x18015c003  lea     r8, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x18015c00a  movzx   ecx, r9w
0x18015c00e  mov     eax, 200h
0x18015c013  imul    ecx, eax
0x18015c016  mov     edx, 37h ; '7'; id
0x18015c01b  mov     r9d, ebx; _a1
0x18015c01e  or      cx, 3; LevelKeyword
0x18015c022  call    WPP_SF_d
0x18015c027  mov     eax, ebx
0x18015c029  add     rsp, 40h
0x18015c02d  pop     r14
0x18015c02f  pop     rdi
0x18015c030  pop     rsi
0x18015c031  pop     rbx
0x18015c032  pop     rbp
0x18015c033  retn
```
