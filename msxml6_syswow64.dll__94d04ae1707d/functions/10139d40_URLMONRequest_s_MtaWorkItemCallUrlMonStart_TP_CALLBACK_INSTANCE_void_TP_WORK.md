# URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x10139d40`
- end: `0x10139e2f`
- name: `?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z`
- size: `239`
- prototype: `void __stdcall(_TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10067bc0`
- `0x10136c46`
- `0x101384cb`
- `0x10139d40`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139dd9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139dd9`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139d6b`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139d6b`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x10139d7a`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x10139d7a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139df8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139df8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139d8a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139d8a`

## pseudocode

```c
void __stdcall URLMONRequest::s_MtaWorkItemCallUrlMonStart(
        _TP_CALLBACK_INSTANCE *Instance,
        URLMONRequest *Context,
        _TP_WORK *Work)
{
  int v3; // ebx
  int v4; // eax
  HRESULT v5; // [esp+Ch] [ebp-4h]

  if ( (byte_101857A0[0] & 8) != 0 )
    WPP_SF_q(0x403u, 0x28u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, (int)Context);
  CallbackMayRunLong(Instance);
  FreeLibraryWhenCallbackReturns(Instance, Context->_hModule);
  Context->_hModule = 0;
  v5 = CoInitializeEx(0, 0);
  v3 = v5;
  if ( v5 >= 0 )
  {
    Context->Lock(Context);
    v4 = URLMONRequest::_CallUrlMonStart(Context);
    v3 = v4;
    if ( v4 < 0 )
      URLMONRequest::_ReportResult(Context, v4, v4, 0);
    Context->Unlock(Context);
  }
  CloseThreadpoolWork(Work);
  ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IURLRequestSite *))Context->_pRequestSite->Release)(
    Context->_pRequestSite->Release,
    Context->_pRequestSite);
  if ( v5 >= 0 )
    CoUninitialize();
  if ( (byte_101857A0[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0x29u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
}

```

## disassembly

```asm
0x10139d40  mov     edi, edi
0x10139d42  push    ebp
0x10139d43  mov     ebp, esp
0x10139d45  push    ecx
0x10139d46  push    ebx
0x10139d47  push    esi
0x10139d48  push    edi
0x10139d49  test    byte_101857A0, 8; __annotation("TMF:",
0x10139d50  mov     edi, [ebp+Context]
0x10139d53  jz      short loc_10139D68
0x10139d55  push    edi; _a1
0x10139d56  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139d5b  push    28h ; '('
0x10139d5d  pop     edx; id
0x10139d5e  mov     ecx, 403h; LevelKeyword
0x10139d63  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139d68  push    [ebp+Instance]; pci
0x10139d6b  call    ds:__imp__CallbackMayRunLong@4; CallbackMayRunLong(x)
0x10139d71  push    dword ptr [edi+148h]; mod
0x10139d77  push    [ebp+Instance]; pci
0x10139d7a  call    ds:__imp__FreeLibraryWhenCallbackReturns@8; FreeLibraryWhenCallbackReturns(x,x)
0x10139d80  xor     eax, eax
0x10139d82  push    eax; dwCoInit
0x10139d83  push    eax; pvReserved
0x10139d84  mov     [edi+148h], eax
0x10139d8a  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10139d90  mov     [ebp+var_4], eax
0x10139d93  mov     ebx, eax
0x10139d95  test    eax, eax
0x10139d97  js      short CleanUp_519
0x10139d99  mov     ecx, [edi]
0x10139d9b  mov     esi, [ecx+7Ch]
0x10139d9e  mov     ecx, esi; this
0x10139da0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139da6  mov     ecx, edi
0x10139da8  call    esi
0x10139daa  mov     ecx, edi; this
0x10139dac  call    ?_CallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_CallUrlMonStart(void)
0x10139db1  mov     ebx, eax
0x10139db3  test    ebx, ebx
0x10139db5  jns     short loc_10139DC2
0x10139db7  push    0; pcwszResult
0x10139db9  push    ebx; dwError
0x10139dba  push    ebx; hrResult
0x10139dbb  mov     ecx, edi; this
0x10139dbd  call    ?_ReportResult@URLMONRequest@@IAEJJKPBG@Z; URLMONRequest::_ReportResult(long,ulong,ushort const *)
0x10139dc2  mov     eax, [edi]
0x10139dc4  mov     esi, [eax+80h]
0x10139dca  mov     ecx, esi; this
0x10139dcc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139dd2  mov     ecx, edi
0x10139dd4  call    esi
0x10139dd6  push    [ebp+Work]; pwk
0x10139dd9  call    ds:__imp__CloseThreadpoolWork@4; CloseThreadpoolWork(x)
0x10139ddf  mov     eax, [edi+5Ch]
0x10139de2  push    eax
0x10139de3  mov     ecx, [eax]
0x10139de5  mov     esi, [ecx+8]
0x10139de8  mov     ecx, esi; this
0x10139dea  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139df0  call    esi
0x10139df2  cmp     [ebp+var_4], 0
0x10139df6  jl      short loc_10139DFE
0x10139df8  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10139dfe  mov     ecx, ebx; __annotation("TMF:",
0x10139e00  sar     ecx, 1Fh
0x10139e03  mov     eax, ecx
0x10139e05  shl     eax, 4
0x10139e08  test    byte_101857A0[eax], 8
0x10139e0f  jz      short loc_10139E28
0x10139e11  push    ebx; _a1
0x10139e12  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139e17  add     ecx, 2
0x10139e1a  shl     ecx, 9
0x10139e1d  push    29h ; ')'
0x10139e1f  or      ecx, 3; LevelKeyword
0x10139e22  pop     edx; id
0x10139e23  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139e28  pop     edi
0x10139e29  pop     esi
0x10139e2a  pop     ebx
0x10139e2b  leave
0x10139e2c  retn    0Ch
```
