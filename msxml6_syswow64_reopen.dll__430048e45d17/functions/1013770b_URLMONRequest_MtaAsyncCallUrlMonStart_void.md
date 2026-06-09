# URLMONRequest::_MtaAsyncCallUrlMonStart(void)

- ea: `0x1013770b`
- end: `0x10137801`
- name: `?_MtaAsyncCallUrlMonStart@URLMONRequest@@IAEJXZ`
- size: `246`
- prototype: `HRESULT __thiscall(URLMONRequest *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1013a000`

## callees

- `0x10067b20`
- `0x1013770b`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101377c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x101377c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x10137744`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x10137744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013774e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1013774e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x10137769`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x10137769`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101377b4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x101377b4`

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
  if ( (byte_10185760[0] & 8) != 0 )
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
    if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[16 * (v1 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v1 >> 31) + 2) << 9) | 3, 0x2Cu, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1013770b  mov     edi, edi
0x1013770d  push    ebp
0x1013770e  mov     ebp, esp
0x10137710  push    this
0x10137711  push    this
0x10137712  push    ebx
0x10137713  push    esi
0x10137714  push    edi
0x10137715  xor     edi, edi
0x10137717  mov     ebx, this
0x10137719  mov     [ebp+hModule], edi
0x1013771c  test    byte_10185760, 8; __annotation("TMF:",
0x10137723  jz      short loc_10137738
0x10137725  push    ebx; _a1
0x10137726  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x1013772b  push    2Ah ; '*'
0x1013772d  pop     edx; id
0x1013772e  mov     this, 403h; LevelKeyword
0x10137733  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10137738  lea     eax, [ebp+hModule]
0x1013773b  mov     esi, offset ?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z; URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x10137740  push    eax; phModule
0x10137741  push    esi; lpModuleName
0x10137742  push    4; dwFlags
0x10137744  call    ds:__imp__GetModuleHandleExW@12; GetModuleHandleExW(x,x,x)
0x1013774a  test    eax, eax
0x1013774c  jnz     short loc_10137765
0x1013774e  call    ds:__imp__GetLastError@0; GetLastError()
0x10137754  mov     edi, eax
0x10137756  test    edi, edi
0x10137758  jle     short CleanUp_496
0x1013775a  movzx   edi, di
0x1013775d  or      edi, 80070000h
0x10137763  jmp     short CleanUp_496
0x10137765  push    0; pcbe
0x10137767  push    ebx; pv
0x10137768  push    esi; pfnwk
0x10137769  call    ds:__imp__CreateThreadpoolWork@12; CreateThreadpoolWork(x,x,x)
0x1013776f  mov     [ebp+pwk], eax
0x10137772  test    eax, eax
0x10137774  jz      short loc_1013774E
0x10137776  mov     eax, [ebp+hModule]
0x10137779  mov     [ebx+148h], eax
0x1013777f  mov     eax, [ebx+5Ch]
0x10137782  mov     [ebp+hModule], edi
0x10137785  push    eax
0x10137786  mov     this, [eax]
0x10137788  mov     esi, [this+4]
0x1013778b  mov     this, esi; this
0x1013778d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10137793  call    esi
0x10137795  test    byte_10185760, 8; __annotation("TMF:",
0x1013779c  jz      short loc_101377B1
0x1013779e  push    ebx; _a1
0x1013779f  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101377a4  push    2Bh ; '+'
0x101377a6  pop     edx; id
0x101377a7  mov     this, 403h; LevelKeyword
0x101377ac  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101377b1  push    [ebp+pwk]; pwk
0x101377b4  call    ds:__imp__SubmitThreadpoolWork@4; SubmitThreadpoolWork(x)
0x101377ba  cmp     [ebp+hModule], 0
0x101377be  jz      short loc_101377D0
0x101377c0  push    [ebp+hModule]; hLibModule
0x101377c3  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x101377c9  mov     [ebp+hModule], 0
0x101377d0  mov     this, edi; __annotation("TMF:",
0x101377d2  sar     this, 1Fh
0x101377d5  mov     eax, this
0x101377d7  shl     eax, 4
0x101377da  test    byte_10185760[eax], 8
0x101377e1  jz      short loc_101377FA
0x101377e3  push    edi; _a1
0x101377e4  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x101377e9  add     this, 2
0x101377ec  shl     this, 9
0x101377ef  push    2Ch ; ','
0x101377f1  or      this, 3; LevelKeyword
0x101377f4  pop     edx; id
0x101377f5  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x101377fa  mov     eax, edi
0x101377fc  pop     edi
0x101377fd  pop     esi
0x101377fe  pop     ebx
0x101377ff  leave
0x10137800  retn
```
