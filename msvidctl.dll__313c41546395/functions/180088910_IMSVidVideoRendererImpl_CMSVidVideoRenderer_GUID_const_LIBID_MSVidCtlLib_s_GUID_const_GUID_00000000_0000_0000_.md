# IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::PostStop(void)

- ea: `0x180088910`
- end: `0x1800889bd`
- name: `?PostStop@?$IMSVidVideoRendererImpl@VCMSVidVideoRenderer@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig@@$1?_GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl@@$1?_GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator@@$1?_GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl@@$1?_GUID_1c1a17b0_bed0_415d_974b_dc6696131599@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify@@$1?_GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@7@UIMSVidVideoRenderer2@@@@UEAAJXZ`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180088910`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x180088965`
- `KERNEL32!SetThreadExecutionState` at `0x180088965`
- `USER32!SystemParametersInfoW` at `0x18008893e`
- `USER32!SystemParametersInfoW` at `0x180088954`
- `USER32!SystemParametersInfoW` at `0x18008893e`
- `USER32!SystemParametersInfoW` at `0x180088954`

## pseudocode

```c
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::PostStop(
        __int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // [rsp+20h] [rbp-28h] BYREF
  ComException *v4; // [rsp+28h] [rbp-20h] BYREF
  std::bad_alloc *v5; // [rsp+30h] [rbp-18h] BYREF
  std::exception *v6; // [rsp+38h] [rbp-10h] BYREF

  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  if ( *(_BYTE *)(a1 + 73) )
  {
    SystemParametersInfoW(0x1025u, 0, (PVOID)(a1 + 76), 0);
    SystemParametersInfoW(0x4Bu, *(_DWORD *)(a1 + 80), 0, 3u);
  }
  if ( *(_BYTE *)(a1 + 92) )
    SetThreadExecutionState(0x80000000);
  try
  {
    result = (*(__int64 (**)(void))(*(_QWORD *)(a1 - 16) + 440LL))();
    if ( (int)result >= 0 )
      result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 200LL))(a1, 0);
  }
  catch ( long v3 )
  {
    return v3;
  }
  catch ( ComException *v4 )
  {
    return *(unsigned int *)v4;
  }
  catch ( std::bad_alloc *v5 )
  {
    return 2147942414LL;
  }
  catch ( std::exception *v6 )
  {
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x180088910  mov     [rsp+arg_8], rbx
0x180088915  push    rdi
0x180088916  sub     rsp, 40h
0x18008891a  mov     rbx, rcx
0x18008891d  xorps   xmm0, xmm0
0x180088920  movdqu  xmmword ptr [rcx+30h], xmm0
0x180088925  movdqu  xmmword ptr [rcx+20h], xmm0
0x18008892a  cmp     byte ptr [rcx+49h], 0
0x18008892e  jz      short loc_18008895A
0x180088930  lea     r8, [rcx+4Ch]; pvParam
0x180088934  xor     r9d, r9d; fWinIni
0x180088937  xor     edx, edx; uiParam
0x180088939  mov     ecx, 1025h; uiAction
0x18008893e  call    cs:__imp_SystemParametersInfoW
0x180088944  mov     r9d, 3; fWinIni
0x18008894a  xor     r8d, r8d; pvParam
0x18008894d  mov     edx, [rbx+50h]; uiParam
0x180088950  lea     ecx, [r9+48h]; uiAction
0x180088954  call    cs:__imp_SystemParametersInfoW
0x18008895a  cmp     byte ptr [rbx+5Ch], 0
0x18008895e  jz      short loc_18008896B
0x180088960  mov     ecx, 80000000h; esFlags
0x180088965  call    cs:__imp_SetThreadExecutionState
0x18008896b  mov     rax, [rbx-10h]
0x18008896f  lea     rcx, [rbx-10h]
0x180088973  mov     rax, [rax+1B8h]
0x18008897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008897f  test    eax, eax
0x180088981  js      short loc_1800889B1
0x180088983  mov     rax, [rbx]
0x180088986  xor     edx, edx
0x180088988  mov     rcx, rbx
0x18008898b  mov     rax, [rax+0C8h]
0x180088992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088997  jmp     short loc_1800889B1
0x180088999  mov     eax, [rsp+48h+var_28]
0x18008899d  jmp     short loc_1800889B1
0x18008899f  mov     eax, [rsp+48h+arg_0]
0x1800889a3  jmp     short loc_1800889B1
0x1800889a5  mov     eax, 8007000Eh
0x1800889aa  jmp     short loc_1800889B1
0x1800889ac  mov     eax, 8000FFFFh
0x1800889b1  mov     rbx, [rsp+48h+arg_8]
0x1800889b6  add     rsp, 40h
0x1800889ba  pop     rdi
0x1800889bb  retn
```
