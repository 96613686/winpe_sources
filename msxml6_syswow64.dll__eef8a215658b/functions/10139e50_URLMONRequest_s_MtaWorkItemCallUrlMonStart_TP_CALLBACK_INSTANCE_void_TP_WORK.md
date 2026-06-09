# URLMONRequest::s_MtaWorkItemCallUrlMonStart(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x10139e50`
- end: `0x10139f3f`
- name: `?s_MtaWorkItemCallUrlMonStart@URLMONRequest@@KGXPAU_TP_CALLBACK_INSTANCE@@PAXPAU_TP_WORK@@@Z`
- size: `239`
- prototype: `void __stdcall(struct _TP_CALLBACK_INSTANCE *Instance, void *Context, _TP_WORK *Work)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10067b20`
- `0x10136d56`
- `0x101385db`
- `0x10139e50`
- `0x10180006`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139ee9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x10139ee9`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139e7b`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x10139e7b`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x10139e8a`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x10139e8a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139f08`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x10139f08`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139e9a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x10139e9a`

## pseudocode

```c
void __stdcall URLMONRequest::s_MtaWorkItemCallUrlMonStart(
        struct _TP_CALLBACK_INSTANCE *Instance,
        URLMONRequest *Context,
        _TP_WORK *Work)
{
  int v3; // ebx
  int v4; // eax
  HRESULT v5; // [esp+Ch] [ebp-4h]

  if ( (byte_10185760[0] & 8) != 0 )
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
  if ( (byte_10185760[16 * (v3 >> 31)] & 8) != 0 )
    WPP_SF_q((((unsigned __int16)(v3 >> 31) + 2) << 9) | 3, 0x29u, WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids, v3);
}

```

## disassembly

```asm
0x10139e50  mov     edi, edi
0x10139e52  push    ebp
0x10139e53  mov     ebp, esp
0x10139e55  push    ecx
0x10139e56  push    ebx
0x10139e57  push    esi
0x10139e58  push    edi
0x10139e59  test    byte_10185760, 8; __annotation("TMF:",
0x10139e60  mov     edi, [ebp+Context]
0x10139e63  jz      short loc_10139E78
0x10139e65  push    edi; _a1
0x10139e66  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139e6b  push    28h ; '('
0x10139e6d  pop     edx; id
0x10139e6e  mov     ecx, 403h; LevelKeyword
0x10139e73  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139e78  push    [ebp+Instance]; pci
0x10139e7b  call    ds:__imp__CallbackMayRunLong@4; CallbackMayRunLong(x)
0x10139e81  push    dword ptr [edi+148h]; mod
0x10139e87  push    [ebp+Instance]; pci
0x10139e8a  call    ds:__imp__FreeLibraryWhenCallbackReturns@8; FreeLibraryWhenCallbackReturns(x,x)
0x10139e90  xor     eax, eax
0x10139e92  push    eax; dwCoInit
0x10139e93  push    eax; pvReserved
0x10139e94  mov     [edi+148h], eax
0x10139e9a  call    ds:__imp__CoInitializeEx@8; CoInitializeEx(x,x)
0x10139ea0  mov     [ebp+var_4], eax
0x10139ea3  mov     ebx, eax
0x10139ea5  test    eax, eax
0x10139ea7  js      short CleanUp_519
0x10139ea9  mov     ecx, [edi]
0x10139eab  mov     esi, [ecx+7Ch]
0x10139eae  mov     ecx, esi; this
0x10139eb0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139eb6  mov     ecx, edi
0x10139eb8  call    esi
0x10139eba  mov     ecx, edi; this
0x10139ebc  call    ?_CallUrlMonStart@URLMONRequest@@IAEJXZ; URLMONRequest::_CallUrlMonStart(void)
0x10139ec1  mov     ebx, eax
0x10139ec3  test    ebx, ebx
0x10139ec5  jns     short loc_10139ED2
0x10139ec7  push    0; pcwszResult
0x10139ec9  push    ebx; dwError
0x10139eca  push    ebx; hrResult
0x10139ecb  mov     ecx, edi; this
0x10139ecd  call    ?_ReportResult@URLMONRequest@@IAEJJKPBG@Z; URLMONRequest::_ReportResult(long,ulong,ushort const *)
0x10139ed2  mov     eax, [edi]
0x10139ed4  mov     esi, [eax+80h]
0x10139eda  mov     ecx, esi; this
0x10139edc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139ee2  mov     ecx, edi
0x10139ee4  call    esi
0x10139ee6  push    [ebp+Work]; pwk
0x10139ee9  call    ds:__imp__CloseThreadpoolWork@4; CloseThreadpoolWork(x)
0x10139eef  mov     eax, [edi+5Ch]
0x10139ef2  push    eax
0x10139ef3  mov     ecx, [eax]
0x10139ef5  mov     esi, [ecx+8]
0x10139ef8  mov     ecx, esi; this
0x10139efa  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10139f00  call    esi
0x10139f02  cmp     [ebp+var_4], 0
0x10139f06  jl      short loc_10139F0E
0x10139f08  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x10139f0e  mov     ecx, ebx; __annotation("TMF:",
0x10139f10  sar     ecx, 1Fh
0x10139f13  mov     eax, ecx
0x10139f15  shl     eax, 4
0x10139f18  test    byte_10185760[eax], 8
0x10139f1f  jz      short loc_10139F38
0x10139f21  push    ebx; _a1
0x10139f22  push    offset _WPP_52c971144c0f3826e8bd4eb75d3ad972_Traceguids; TraceGuid
0x10139f27  add     ecx, 2
0x10139f2a  shl     ecx, 9
0x10139f2d  push    29h ; ')'
0x10139f2f  or      ecx, 3; LevelKeyword
0x10139f32  pop     edx; id
0x10139f33  call    _WPP_SF_q@16; WPP_SF_q(x,x,x,x)
0x10139f38  pop     edi
0x10139f39  pop     esi
0x10139f3a  pop     ebx
0x10139f3b  leave
0x10139f3c  retn    0Ch
```
