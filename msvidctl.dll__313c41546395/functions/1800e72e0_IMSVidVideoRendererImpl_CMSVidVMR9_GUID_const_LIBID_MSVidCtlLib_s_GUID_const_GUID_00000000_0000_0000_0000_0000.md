# IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::PostStop(void)

- ea: `0x1800e72e0`
- end: `0x1800e738d`
- name: `?PostStop@?$IMSVidVideoRendererImpl@VCMSVidVMR9@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig9@@$1?_GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl9@@$1?_GUID_8f537d09_f85e_4414_b23b_502e54c79927@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator9@@$1?_GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl9@@$1?_GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify9@@$1?_GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor9@@$1?_GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6@@3U__s_GUID@@B@7@UIMSVidVMR9@@@@UEAAJXZ`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800e72e0`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x1800e7335`
- `KERNEL32!SetThreadExecutionState` at `0x1800e7335`
- `USER32!SystemParametersInfoW` at `0x1800e730e`
- `USER32!SystemParametersInfoW` at `0x1800e7324`
- `USER32!SystemParametersInfoW` at `0x1800e730e`
- `USER32!SystemParametersInfoW` at `0x1800e7324`

## pseudocode

```c
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::PostStop(
        __int64 a1)
{
  __int64 result; // rax

  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  if ( *(_BYTE *)(a1 + 73) )
  {
    SystemParametersInfoW(0x1025u, 0, (PVOID)(a1 + 76), 0);
    SystemParametersInfoW(0x4Bu, *(_DWORD *)(a1 + 80), 0, 3u);
  }
  if ( *(_BYTE *)(a1 + 92) )
    SetThreadExecutionState(0x80000000);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 16) + 424LL))(a1 - 16);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 200LL))(a1, 0);
  return result;
}

```

## disassembly

```asm
0x1800e72e0  mov     [rsp+arg_8], rbx
0x1800e72e5  push    rdi
0x1800e72e6  sub     rsp, 40h
0x1800e72ea  mov     rbx, rcx
0x1800e72ed  xorps   xmm0, xmm0
0x1800e72f0  movdqu  xmmword ptr [rcx+30h], xmm0
0x1800e72f5  movdqu  xmmword ptr [rcx+20h], xmm0
0x1800e72fa  cmp     byte ptr [rcx+49h], 0
0x1800e72fe  jz      short loc_1800E732A
0x1800e7300  lea     r8, [rcx+4Ch]; pvParam
0x1800e7304  xor     r9d, r9d; fWinIni
0x1800e7307  xor     edx, edx; uiParam
0x1800e7309  mov     ecx, 1025h; uiAction
0x1800e730e  call    cs:__imp_SystemParametersInfoW
0x1800e7314  mov     r9d, 3; fWinIni
0x1800e731a  xor     r8d, r8d; pvParam
0x1800e731d  mov     edx, [rbx+50h]; uiParam
0x1800e7320  lea     ecx, [r9+48h]; uiAction
0x1800e7324  call    cs:__imp_SystemParametersInfoW
0x1800e732a  cmp     byte ptr [rbx+5Ch], 0
0x1800e732e  jz      short loc_1800E733B
0x1800e7330  mov     ecx, 80000000h; esFlags
0x1800e7335  call    cs:__imp_SetThreadExecutionState
0x1800e733b  mov     rax, [rbx-10h]
0x1800e733f  lea     rcx, [rbx-10h]
0x1800e7343  mov     rax, [rax+1A8h]
0x1800e734a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e734f  test    eax, eax
0x1800e7351  js      short loc_1800E7381
0x1800e7353  mov     rax, [rbx]
0x1800e7356  xor     edx, edx
0x1800e7358  mov     rcx, rbx
0x1800e735b  mov     rax, [rax+0C8h]
0x1800e7362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7367  jmp     short loc_1800E7381
0x1800e7369  mov     eax, [rsp+48h+var_28]
0x1800e736d  jmp     short loc_1800E7381
0x1800e736f  mov     eax, [rsp+48h+arg_0]
0x1800e7373  jmp     short loc_1800E7381
0x1800e7375  mov     eax, 8007000Eh
0x1800e737a  jmp     short loc_1800E7381
0x1800e737c  mov     eax, 8000FFFFh
0x1800e7381  mov     rbx, [rsp+48h+arg_8]
0x1800e7386  add     rsp, 40h
0x1800e738a  pop     rdi
0x1800e738b  retn
```
