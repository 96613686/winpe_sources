# URLMONRequest::_MtaAsyncCallUrlMonStart(void)

- ea: `0x101375fb`
- end: `0x101376f1`
- name: `?_MtaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ`
- size: `246`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10139ef0`

## callees

- `0x10067bc0`
- `0x101375fb`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101376b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101376b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x10137634`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x10137634`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013763e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013763e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x10137659`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x10137659`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101376a4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101376a4`

## pseudocode

```c
HRESULT __thiscall URLMONRequest::_MtaAsyncCallUrlMonStart(URLMONRequest *this)
{
  signed int v1; // edi
  signed int LastError; // eax
  IURLRequestSite *pRequestSite; // eax
  _TP_WORK *pwk; // [esp+Ch] [ebp-8h]
  HINSTANCE__ *hModule; // [esp+10h] [ebp-4h] BYREF

  v1 = 0;
  hModule = 0;
  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x2Au, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
  if ( GetModuleHandleExW(4u, (LPCWSTR)URLMONRequest::s_MtaWorkItemCallUrlMonStart, &hModule)
    && (pwk = CreateThreadpoolWork(URLMONRequest::s_MtaWorkItemCallUrlMonStart, this, 0)) != 0 )
  {
    this->_hModule = hModule;
    pRequestSite = this->_pRequestSite;
    hModule = 0;
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IURLRequestSite *))pRequestSite->AddRef)(
      pRequestSite->AddRef,
      pRequestSite);
    if ( (byte_101857A0[0] & 8) != 0 )
      WPP_SF_q(0x403u, 0x2Bu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)this);
    SubmitThreadpoolWork(pwk);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( hModule )
  {
    FreeLibrary(hModule);
    hModule = 0;
  }
  if ( (byte_101857A0[16 * (v1 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v1 >> 31) + 2) << 9) | 3, 0x2Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x101375fb  mov     edi, edi
0x101375fd  push    ebp
0x101375fe  mov     ebp, esp
0x10137600  push    this
0x10137601  push    this
0x10137602  push    ebx
0x10137603  push    esi
0x10137604  push    edi
0x10137605  xor     edi, edi
0x10137607  mov     ebx, this
0x10137609  mov     [ebp+hModule], edi
0x1013760c  test    byte_101857A0, 8; __annotation("TMF:",
0x10137613  jz      short loc_10137628
0x10137615  push    ebx; _a1
0x10137616  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013761b  push    2Ah ; '*'
0x1013761d  pop     edx; id
0x1013761e  mov     this, 403h; LevelKeyword
0x10137623  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10137628  lea     eax, [ebp+hModule]
0x1013762b  mov     esi, offset ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z; URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x10137630  push    eax; phModule
0x10137631  push    esi; lpModuleName
0x10137632  push    4; dwFlags
0x10137634  call    ds:__imp__GetModuleHandleExW@12; GetModuleHandleExW(x,x,x)
0x1013763a  test    eax, eax
0x1013763c  jnz     short loc_10137655
0x1013763e  call    ds:__imp__GetLastError@0; GetLastError()
0x10137644  mov     edi, eax
0x10137646  test    edi, edi
0x10137648  jle     short CleanUp_496
0x1013764a  movzx   edi, di
0x1013764d  or      edi, 80070000h
0x10137653  jmp     short CleanUp_496
0x10137655  push    0; pcbe
0x10137657  push    ebx; pv
0x10137658  push    esi; pfnwk
0x10137659  call    ds:__imp__CreateThreadpoolWork@12; CreateThreadpoolWork(x,x,x)
0x1013765f  mov     [ebp+pwk], eax
0x10137662  test    eax, eax
0x10137664  jz      short loc_1013763E
0x10137666  mov     eax, [ebp+hModule]
0x10137669  mov     [ebx+148h], eax
0x1013766f  mov     eax, [ebx+5Ch]
0x10137672  mov     [ebp+hModule], edi
0x10137675  push    eax
0x10137676  mov     this, [eax]
0x10137678  mov     esi, [this+4]
0x1013767b  mov     this, esi; this
0x1013767d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10137683  call    esi
0x10137685  test    byte_101857A0, 8; __annotation("TMF:",
0x1013768c  jz      short loc_101376A1
0x1013768e  push    ebx; _a1
0x1013768f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10137694  push    2Bh ; '+'
0x10137696  pop     edx; id
0x10137697  mov     this, 403h; LevelKeyword
0x1013769c  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101376a1  push    [ebp+pwk]; pwk
0x101376a4  call    ds:__imp__SubmitThreadpoolWork@4; SubmitThreadpoolWork(x)
0x101376aa  cmp     [ebp+hModule], 0
0x101376ae  jz      short loc_101376C0
0x101376b0  push    [ebp+hModule]; hLibModule
0x101376b3  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x101376b9  mov     [ebp+hModule], 0
0x101376c0  mov     this, edi; __annotation("TMF:",
0x101376c2  sar     this, 1Fh
0x101376c5  mov     eax, this
0x101376c7  shl     eax, 4
0x101376ca  test    byte_101857A0[eax], 8
0x101376d1  jz      short loc_101376EA
0x101376d3  push    edi; _a1
0x101376d4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101376d9  add     this, 2
0x101376dc  shl     this, 9
0x101376df  push    2Ch ; ','
0x101376e1  or      this, 3; LevelKeyword
0x101376e4  pop     edx; id
0x101376e5  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101376ea  mov     eax, edi
0x101376ec  pop     edi
0x101376ed  pop     esi
0x101376ee  pop     ebx
0x101376ef  leave
0x101376f0  retn
```
