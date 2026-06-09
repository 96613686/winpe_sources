# IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::SetupMixerBitmap(IPictureDisp *,long,IMSVidRect *)

- ea: `0x1800e7960`
- end: `0x1800e801f`
- name: `?SetupMixerBitmap@?$IMSVidVideoRendererImpl@VCMSVidVMR9@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig9@@$1?_GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl9@@$1?_GUID_8f537d09_f85e_4414_b23b_502e54c79927@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator9@@$1?_GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl9@@$1?_GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify9@@$1?_GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor9@@$1?_GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6@@3U__s_GUID@@B@7@UIMSVidVMR9@@@@UEAAJPEAUIPictureDisp@@JPEAUIMSVidRect@@@Z`
- size: `1727`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004640`
- `0x1800054bc`
- `0x180006b38`
- `0x18000e518`
- `0x1800191f0`
- `0x18001d270`
- `0x18002a3f8`
- `0x180085730`
- `0x18008676c`
- `0x1800e7960`
- `0x1800f8010`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800e7f4e`
- `GDI32!DeleteDC` at `0x1800e7f4e`
- `GDI32!CreateCompatibleDC` at `0x1800e7baa`
- `GDI32!CreateCompatibleDC` at `0x1800e7baa`
- `GDI32!SelectObject` at `0x1800e7c12`
- `GDI32!SelectObject` at `0x1800e7c12`

## pseudocode

```c
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::SetupMixerBitmap(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdx
  _QWORD *v10; // rdi
  unsigned int v11; // r8d
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  const unsigned __int16 *v14; // r9
  HDC CompatibleDC; // r15
  unsigned int v16; // r8d
  const unsigned __int16 *v17; // r9
  float v18; // xmm0_4
  float v19; // xmm7_4
  float v20; // xmm10_4
  int v21; // ecx
  float v22; // xmm8_4
  int v23; // ecx
  float v24; // xmm9_4
  int v25; // eax
  unsigned int v26; // r8d
  const unsigned __int16 *v27; // r9
  int v28; // ebx
  unsigned int v29; // r8d
  const unsigned __int16 *v30; // r9
  char **v31; // [rsp+38h] [rbp-130h]
  struct tagSIZE v32; // [rsp+40h] [rbp-128h] BYREF
  _WORD v33[2]; // [rsp+48h] [rbp-120h] BYREF
  struct tagSIZE v34; // [rsp+4Ch] [rbp-11Ch] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-110h] BYREF
  struct tagSIZE v36; // [rsp+60h] [rbp-108h] BYREF
  __int128 v37; // [rsp+78h] [rbp-F0h]
  int v38; // [rsp+90h] [rbp-D8h] BYREF
  HDC v39; // [rsp+98h] [rbp-D0h]
  __int64 v40; // [rsp+A8h] [rbp-C0h]
  LONG cx; // [rsp+B0h] [rbp-B8h]
  LONG v42; // [rsp+B4h] [rbp-B4h]
  unsigned __int64 v43; // [rsp+B8h] [rbp-B0h]
  int v44; // [rsp+C0h] [rbp-A8h]
  int v45; // [rsp+C4h] [rbp-A4h]
  int v46; // [rsp+C8h] [rbp-A0h]

  memset_0(&v38, 0, 0x40u);
  v37 = 0;
  v34.cx = 0;
  v34.cy = 0;
  if ( !a2 )
  {
    ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(
      a1 + 200,
      v8);
    v38 = 1;
    return (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 200LL))(a1, &v38);
  }
  if ( a2 == -1 )
  {
    v10 = (_QWORD *)(a1 + 200);
    ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(
      &v32,
      a1 + 200);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
    if ( !*(_QWORD *)&v32 )
      return 0;
  }
  else
  {
    ATL::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>(
      &v32,
      a2);
    if ( !*(_QWORD *)&v32 )
    {
      ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
      return 2147500034LL;
    }
    v10 = (_QWORD *)(a1 + 200);
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 200), *(struct IUnknown **)&v32);
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v32);
  }
  v33[0] = 0;
  (*(void (__fastcall **)(_QWORD, _WORD *))(*(_QWORD *)*v10 + 40LL))(*v10, v33);
  if ( v33[0] != 1 )
    return ATL::AtlSetErrorInfo2(
             &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
             0xC0040589,
             v11,
             v12,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147024809,
             hInstance,
             v31);
  if ( (*(int (__fastcall **)(_QWORD, struct tagSIZE *))(*(_QWORD *)*v10 + 56LL))(*v10, &v34) < 0 )
    return ATL::AtlSetErrorInfo2(
             &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
             0xC0040546,
             v13,
             v14,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147221001,
             hInstance,
             v31);
  if ( (*(int (__fastcall **)(_QWORD, LONG *))(*(_QWORD *)*v10 + 48LL))(*v10, &v34.cy) < 0 )
    return ATL::AtlSetErrorInfo2(
             &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
             0xC0040546,
             v13,
             v14,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147221001,
             hInstance,
             v31);
  v32 = 0;
  v36 = 0;
  ATL::AtlHiMetricToPixel((const struct tagSIZE *)&v34.cy, &v32);
  ATL::AtlHiMetricToPixel(&v34, &v36);
  CompatibleDC = CreateCompatibleDC(0);
  h = 0;
  if ( (*(int (__fastcall **)(_QWORD, HGDIOBJ *))(*(_QWORD *)*v10 + 24LL))(*v10, &h) < 0 )
    return ATL::AtlSetErrorInfo2(
             &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
             0xC0040546,
             v13,
             v14,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147221001,
             hInstance,
             v31);
  SelectObject(CompatibleDC, h);
  v40 = v37;
  cx = v32.cx;
  v42 = v36.cx;
  v39 = CompatibleDC;
  v38 = 2;
  if ( (unsigned int)a3 > 0x64 )
  {
    if ( a3 != -1 )
      return ATL::AtlSetErrorInfo2(
               &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
               0xC0040587,
               v16,
               v17,
               &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
               -2147221001,
               hInstance,
               v31);
    v18 = *(float *)(a1 + 128);
    if ( v18 < 0.0 )
    {
      v46 = 1056964608;
      goto LABEL_19;
    }
  }
  else
  {
    v18 = (float)a3 / 100.0;
    *(float *)(a1 + 128) = v18;
  }
  v46 = LODWORD(v18);
LABEL_19:
  if ( a4 )
  {
    v32.cx = 0;
    v19 = FLOAT_N1_0;
    v20 = FLOAT_N1_0;
    if ( (*(int (__fastcall **)(__int64, struct tagSIZE *))(*(_QWORD *)a4 + 72LL))(a4, &v32) >= 0 )
    {
      v21 = *(_DWORD *)(a1 + 72) - *(_DWORD *)(a1 + 64);
      if ( v21 )
      {
        v20 = (float)v32.cx;
        if ( v32.cx > 0 )
          v20 = v20 / (float)v21;
      }
    }
    v22 = FLOAT_N1_0;
    if ( (*(int (__fastcall **)(__int64, struct tagSIZE *))(*(_QWORD *)a4 + 56LL))(a4, &v32) >= 0 )
    {
      v23 = *(_DWORD *)(a1 + 76) - *(_DWORD *)(a1 + 68);
      if ( v23 )
      {
        v22 = (float)v32.cx;
        if ( v32.cx > 0 )
          v22 = v22 / (float)v23;
      }
    }
    v24 = FLOAT_N1_0;
    if ( (*(int (__fastcall **)(__int64, struct tagSIZE *))(*(_QWORD *)a4 + 88LL))(a4, &v32) >= 0 )
    {
      v25 = *(_DWORD *)(a1 + 72) - *(_DWORD *)(a1 + 64);
      if ( v25 )
      {
        if ( v32.cx > 0 )
          v24 = (float)((float)v32.cx / (float)v25) + v20;
      }
    }
    if ( (*(int (__fastcall **)(__int64, struct tagSIZE *))(*(_QWORD *)a4 + 104LL))(a4, &v32) >= 0
      && *(_DWORD *)(a1 + 72) != *(_DWORD *)(a1 + 64)
      && v32.cx > 0 )
    {
      v19 = (float)((float)v32.cx / (float)(*(_DWORD *)(a1 + 76) - *(_DWORD *)(a1 + 68))) + v22;
    }
    if ( v22 < 0.0 || v20 < 0.0 || v22 > 1.0 || v20 > 1.0 || v24 < 0.0 || v19 < 0.0 || v24 > 1.0 || v19 > 1.0 )
      return ATL::AtlSetErrorInfo2(
               &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
               0xC0040588,
               v26,
               v27,
               &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
               -2147221001,
               hInstance,
               v31);
    *(float *)(a1 + 132) = v20;
    *(float *)(a1 + 136) = v22;
    *(float *)(a1 + 140) = v24;
    *(float *)(a1 + 144) = v19;
    v43 = __PAIR64__(LODWORD(v22), LODWORD(v20));
    v44 = LODWORD(v24);
    v45 = LODWORD(v19);
  }
  else if ( *(float *)(a1 + 132) < 0.0
         || *(float *)(a1 + 136) < 0.0
         || *(float *)(a1 + 140) < 0.0
         || *(float *)(a1 + 144) < 0.0 )
  {
    v43 = 0;
    v44 = 1065353216;
    v45 = 1065353216;
  }
  else
  {
    v43 = *(_QWORD *)(a1 + 132);
    v44 = *(_DWORD *)(a1 + 140);
    v45 = *(_DWORD *)(a1 + 144);
  }
  v28 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 200LL))(a1, &v38);
  if ( !DeleteDC(CompatibleDC) )
    return ATL::AtlSetErrorInfo2(
             &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
             0xC0040545,
             v29,
             v30,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             8398,
             hInstance,
             v31);
  if ( v28 >= 0 )
    return 0;
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1800e7960  mov     rax, rsp
0x1800e7963  push    rbx
0x1800e7964  push    rsi
0x1800e7965  push    rdi
0x1800e7966  push    r14
0x1800e7968  push    r15
0x1800e796a  sub     rsp, 140h
0x1800e7971  movaps  xmmword ptr [rax-38h], xmm6
0x1800e7975  movaps  xmmword ptr [rax-48h], xmm7
0x1800e7979  movaps  xmmword ptr [rax-58h], xmm8
0x1800e797e  movaps  xmmword ptr [rax-68h], xmm9
0x1800e7983  movaps  xmmword ptr [rax-78h], xmm10
0x1800e7988  mov     rax, cs:__security_cookie
0x1800e798f  xor     rax, rsp
0x1800e7992  mov     [rsp+168h+var_88], rax
0x1800e799a  mov     rsi, r9
0x1800e799d  mov     r14d, r8d
0x1800e79a0  mov     rdi, rdx
0x1800e79a3  mov     rbx, rcx
0x1800e79a6  xor     edx, edx; Val
0x1800e79a8  lea     r8d, [rdx+40h]; Size
0x1800e79ac  lea     rcx, [rsp+168h+var_D8]; void *
0x1800e79b4  call    memset_0
0x1800e79b9  xorps   xmm0, xmm0
0x1800e79bc  movups  [rsp+168h+var_F0], xmm0
0x1800e79c1  mov     [rsp+168h+var_11C.cx], 0
0x1800e79c9  mov     [rsp+168h+var_11C.cy], 0
0x1800e79d1  test    rdi, rdi
0x1800e79d4  jnz     short loc_1800E7A0B
0x1800e79d6  lea     rcx, [rbx+0C8h]
0x1800e79dd  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x1800e79e2  lea     eax, [rdi+1]
0x1800e79e5  mov     [rsp+168h+var_D8], eax
0x1800e79ec  mov     rax, [rbx]
0x1800e79ef  lea     rdx, [rsp+168h+var_D8]
0x1800e79f7  mov     rcx, rbx
0x1800e79fa  mov     rax, [rax+0C8h]
0x1800e7a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7a06  jmp     loc_1800E7FE2
0x1800e7a0b  lea     rcx, [rsp+168h+var_128]
0x1800e7a10  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800e7a14  jnz     short loc_1800E7A3E
0x1800e7a16  lea     rdi, [rbx+0C8h]
0x1800e7a1d  mov     rdx, rdi
0x1800e7a20  call    ??0?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@QEAA@AEBV01@@Z; ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4> const &)
0x1800e7a25  lea     rcx, [rsp+168h+var_128]
0x1800e7a2a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800e7a2f  cmp     qword ptr [rsp+168h+var_128.cx], 0
0x1800e7a35  jnz     short loc_1800E7A7F
0x1800e7a37  xor     eax, eax
0x1800e7a39  jmp     loc_1800E7FE2
0x1800e7a3e  mov     rdx, rdi
0x1800e7a41  call    ??0?$CComQIPtr@UIPicture@@$1?_GUID_7bf80980_bf32_101a_8bbb_00aa00300cab@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>(IUnknown *)
0x1800e7a46  nop
0x1800e7a47  mov     rdx, qword ptr [rsp+168h+var_128.cx]; struct IUnknown *
0x1800e7a4c  test    rdx, rdx
0x1800e7a4f  jnz     short loc_1800E7A65
0x1800e7a51  lea     rcx, [rsp+168h+var_128]
0x1800e7a56  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800e7a5b  mov     eax, 80004002h
0x1800e7a60  jmp     loc_1800E7FE2
0x1800e7a65  lea     rdi, [rbx+0C8h]
0x1800e7a6c  mov     rcx, rdi; struct IUnknown **
0x1800e7a6f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800e7a74  nop
0x1800e7a75  lea     rcx, [rsp+168h+var_128]
0x1800e7a7a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800e7a7f  xor     eax, eax
0x1800e7a81  mov     [rsp+168h+var_120], ax
0x1800e7a86  mov     rcx, [rdi]
0x1800e7a89  mov     rax, [rcx]
0x1800e7a8c  lea     rdx, [rsp+168h+var_120]
0x1800e7a91  mov     rax, [rax+28h]
0x1800e7a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7a9a  mov     eax, 1
0x1800e7a9f  cmp     [rsp+168h+var_120], ax
0x1800e7aa4  jz      short loc_1800E7ADC
0x1800e7aa6  mov     rax, cs:hInstance
0x1800e7aad  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800e7ab2  mov     [rsp+168h+var_140], 80070057h; int
0x1800e7aba  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e7ac1  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800e7ac6  mov     edx, 0C0040589h; dwMessageId
0x1800e7acb  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e7ad2  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e7ad7  jmp     loc_1800E7FE2
0x1800e7adc  mov     rcx, [rdi]
0x1800e7adf  mov     rax, [rcx]
0x1800e7ae2  lea     rdx, [rsp+168h+var_11C]
0x1800e7ae7  mov     rax, [rax+38h]
0x1800e7aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7af0  test    eax, eax
0x1800e7af2  jns     short loc_1800E7B2A
0x1800e7af4  mov     rax, cs:hInstance
0x1800e7afb  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800e7b00  mov     [rsp+168h+var_140], 800401F7h; int
0x1800e7b08  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e7b0f  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800e7b14  mov     edx, 0C0040546h; dwMessageId
0x1800e7b19  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e7b20  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e7b25  jmp     loc_1800E7FE2
0x1800e7b2a  mov     rcx, [rdi]
0x1800e7b2d  mov     rax, [rcx]
0x1800e7b30  lea     rdx, [rsp+168h+var_11C.cy]
0x1800e7b35  mov     rax, [rax+30h]
0x1800e7b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7b3e  test    eax, eax
0x1800e7b40  jns     short loc_1800E7B78
0x1800e7b42  mov     rax, cs:hInstance
0x1800e7b49  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800e7b4e  mov     [rsp+168h+var_140], 800401F7h; int
0x1800e7b56  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e7b5d  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800e7b62  mov     edx, 0C0040546h; dwMessageId
0x1800e7b67  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e7b6e  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e7b73  jmp     loc_1800E7FE2
0x1800e7b78  mov     qword ptr [rsp+168h+var_128.cx], 0
0x1800e7b81  mov     qword ptr [rsp+168h+var_108.cx], 0
0x1800e7b8a  lea     rdx, [rsp+168h+var_128]; struct tagSIZE *
0x1800e7b8f  lea     rcx, [rsp+168h+var_11C.cy]; struct tagSIZE *
0x1800e7b94  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x1800e7b99  lea     rdx, [rsp+168h+var_108]; struct tagSIZE *
0x1800e7b9e  lea     rcx, [rsp+168h+var_11C]; struct tagSIZE *
0x1800e7ba3  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x1800e7ba8  xor     ecx, ecx; hdc
0x1800e7baa  call    cs:__imp_CreateCompatibleDC
0x1800e7bb0  mov     r15, rax
0x1800e7bb3  mov     [rsp+168h+h], 0
0x1800e7bbc  mov     rcx, [rdi]
0x1800e7bbf  mov     rdx, [rcx]
0x1800e7bc2  mov     rax, [rdx+18h]
0x1800e7bc6  lea     rdx, [rsp+168h+h]
0x1800e7bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7bd0  test    eax, eax
0x1800e7bd2  jns     short loc_1800E7C0A
0x1800e7bd4  mov     rax, cs:hInstance
0x1800e7bdb  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800e7be0  mov     [rsp+168h+var_140], 800401F7h; int
0x1800e7be8  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e7bef  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800e7bf4  mov     edx, 0C0040546h; dwMessageId
0x1800e7bf9  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e7c00  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e7c05  jmp     loc_1800E7FE2
0x1800e7c0a  mov     rdx, [rsp+168h+h]; h
0x1800e7c0f  mov     rcx, r15; hdc
0x1800e7c12  call    cs:__imp_SelectObject
0x1800e7c18  mov     rax, qword ptr [rsp+168h+var_F0]
0x1800e7c1d  mov     [rsp+168h+var_C0], rax
0x1800e7c25  mov     eax, [rsp+168h+var_128.cx]
0x1800e7c29  mov     [rsp+168h+var_B8], eax
0x1800e7c30  mov     eax, [rsp+168h+var_108.cx]
0x1800e7c34  mov     [rsp+168h+var_B4], eax
0x1800e7c3b  mov     [rsp+168h+var_D0], r15
0x1800e7c43  mov     [rsp+168h+var_D8], 2
0x1800e7c4e  cmp     r14d, 64h ; 'd'
0x1800e7c52  ja      loc_1800E7E43
0x1800e7c58  movd    xmm0, r14d
0x1800e7c5d  cvtdq2ps xmm0, xmm0
0x1800e7c60  divss   xmm0, cs:__real@42c80000
0x1800e7c68  movss   dword ptr [rbx+80h], xmm0
0x1800e7c70  xorps   xmm6, xmm6
0x1800e7c73  movss   [rsp+168h+var_A0], xmm0
0x1800e7c7c  test    rsi, rsi
0x1800e7c7f  jz      loc_1800E7EA7
0x1800e7c85  mov     [rsp+168h+var_128.cx], 0
0x1800e7c8d  movss   xmm7, cs:__real@bf800000
0x1800e7c95  movaps  xmm10, xmm7
0x1800e7c99  mov     rax, [rsi]
0x1800e7c9c  lea     rdx, [rsp+168h+var_128]
0x1800e7ca1  mov     rcx, rsi
0x1800e7ca4  mov     rax, [rax+48h]
0x1800e7ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7cad  test    eax, eax
0x1800e7caf  js      short loc_1800E7CD6
0x1800e7cb1  mov     ecx, [rbx+48h]
0x1800e7cb4  sub     ecx, [rbx+40h]
0x1800e7cb7  jz      short loc_1800E7CD6
0x1800e7cb9  mov     eax, [rsp+168h+var_128.cx]
0x1800e7cbd  movd    xmm10, eax
0x1800e7cc2  cvtdq2ps xmm10, xmm10
0x1800e7cc6  test    eax, eax
0x1800e7cc8  jle     short loc_1800E7CD6
0x1800e7cca  movd    xmm0, ecx
0x1800e7cce  cvtdq2ps xmm0, xmm0
0x1800e7cd1  divss   xmm10, xmm0
0x1800e7cd6  movaps  xmm8, xmm7
0x1800e7cda  mov     rax, [rsi]
0x1800e7cdd  lea     rdx, [rsp+168h+var_128]
0x1800e7ce2  mov     rcx, rsi
0x1800e7ce5  mov     rax, [rax+38h]
0x1800e7ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7cee  test    eax, eax
0x1800e7cf0  js      short loc_1800E7D17
0x1800e7cf2  mov     ecx, [rbx+4Ch]
0x1800e7cf5  sub     ecx, [rbx+44h]
0x1800e7cf8  jz      short loc_1800E7D17
0x1800e7cfa  mov     eax, [rsp+168h+var_128.cx]
0x1800e7cfe  movd    xmm8, eax
0x1800e7d03  cvtdq2ps xmm8, xmm8
0x1800e7d07  test    eax, eax
0x1800e7d09  jle     short loc_1800E7D17
0x1800e7d0b  movd    xmm0, ecx
0x1800e7d0f  cvtdq2ps xmm0, xmm0
0x1800e7d12  divss   xmm8, xmm0
0x1800e7d17  movaps  xmm9, xmm7
0x1800e7d1b  mov     rax, [rsi]
0x1800e7d1e  lea     rdx, [rsp+168h+var_128]
0x1800e7d23  mov     rcx, rsi
0x1800e7d26  mov     rax, [rax+58h]
0x1800e7d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d2f  test    eax, eax
0x1800e7d31  js      short loc_1800E7D5D
0x1800e7d33  mov     eax, [rbx+48h]
0x1800e7d36  sub     eax, [rbx+40h]
0x1800e7d39  jz      short loc_1800E7D5D
0x1800e7d3b  mov     edx, [rsp+168h+var_128.cx]
0x1800e7d3f  test    edx, edx
0x1800e7d41  jle     short loc_1800E7D5D
0x1800e7d43  movd    xmm9, edx
0x1800e7d48  cvtdq2ps xmm9, xmm9
0x1800e7d4c  movd    xmm0, eax
0x1800e7d50  cvtdq2ps xmm0, xmm0
0x1800e7d53  divss   xmm9, xmm0
0x1800e7d58  addss   xmm9, xmm10
0x1800e7d5d  mov     rax, [rsi]
0x1800e7d60  lea     rdx, [rsp+168h+var_128]
0x1800e7d65  mov     rcx, rsi
0x1800e7d68  mov     rax, [rax+68h]
0x1800e7d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7d71  test    eax, eax
0x1800e7d73  js      short loc_1800E7DA2
0x1800e7d75  mov     eax, [rbx+48h]
0x1800e7d78  cmp     eax, [rbx+40h]
0x1800e7d7b  jz      short loc_1800E7DA2
0x1800e7d7d  mov     eax, [rsp+168h+var_128.cx]
0x1800e7d81  test    eax, eax
0x1800e7d83  jle     short loc_1800E7DA2
0x1800e7d85  movd    xmm7, eax
0x1800e7d89  cvtdq2ps xmm7, xmm7
0x1800e7d8c  mov     eax, [rbx+4Ch]
0x1800e7d8f  sub     eax, [rbx+44h]
0x1800e7d92  movd    xmm0, eax
0x1800e7d96  cvtdq2ps xmm0, xmm0
0x1800e7d99  divss   xmm7, xmm0
0x1800e7d9d  addss   xmm7, xmm8
0x1800e7da2  comiss  xmm6, xmm8
0x1800e7da6  ja      loc_1800E7E71
0x1800e7dac  comiss  xmm6, xmm10
0x1800e7db0  ja      loc_1800E7E71
0x1800e7db6  movss   xmm0, cs:__real@3f800000
0x1800e7dbe  comiss  xmm8, xmm0
0x1800e7dc2  ja      loc_1800E7E71
0x1800e7dc8  comiss  xmm10, xmm0
0x1800e7dcc  ja      loc_1800E7E71
0x1800e7dd2  comiss  xmm6, xmm9
0x1800e7dd6  ja      loc_1800E7E71
0x1800e7ddc  comiss  xmm6, xmm7
0x1800e7ddf  ja      loc_1800E7E71
0x1800e7de5  comiss  xmm9, xmm0
0x1800e7de9  ja      loc_1800E7E71
0x1800e7def  comiss  xmm7, xmm0
0x1800e7df2  ja      short loc_1800E7E71
0x1800e7df4  movss   dword ptr [rbx+84h], xmm10
0x1800e7dfd  movss   dword ptr [rbx+88h], xmm8
0x1800e7e06  movss   dword ptr [rbx+8Ch], xmm9
0x1800e7e0f  movss   dword ptr [rbx+90h], xmm7
0x1800e7e17  movss   dword ptr [rsp+168h+var_B0], xmm10
0x1800e7e21  movss   dword ptr [rsp+168h+var_B0+4], xmm8
0x1800e7e2b  movss   [rsp+168h+var_A8], xmm9
0x1800e7e35  movss   [rsp+168h+var_A4], xmm7
0x1800e7e3e  jmp     loc_1800E7F2F
0x1800e7e43  cmp     r14d, 0FFFFFFFFh
0x1800e7e47  jnz     loc_1800E7F97
0x1800e7e4d  movss   xmm0, dword ptr [rbx+80h]
0x1800e7e55  xorps   xmm6, xmm6
0x1800e7e58  comiss  xmm6, xmm0
0x1800e7e5b  jbe     loc_1800E7C73
0x1800e7e61  mov     [rsp+168h+var_A0], 3F000000h
0x1800e7e6c  jmp     loc_1800E7C7C
0x1800e7e71  mov     rax, cs:hInstance
0x1800e7e78  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800e7e7d  mov     [rsp+168h+var_140], 800401F7h; int
0x1800e7e85  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e7e8c  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800e7e91  mov     edx, 0C0040588h; dwMessageId
0x1800e7e96  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e7e9d  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e7ea2  jmp     loc_1800E7FE2
0x1800e7ea7  movss   xmm0, dword ptr [rbx+84h]
0x1800e7eaf  comiss  xmm6, xmm0
0x1800e7eb2  ja      short loc_1800E7F0D
0x1800e7eb4  comiss  xmm6, dword ptr [rbx+88h]
0x1800e7ebb  ja      short loc_1800E7F0D
0x1800e7ebd  comiss  xmm6, dword ptr [rbx+8Ch]
0x1800e7ec4  ja      short loc_1800E7F0D
0x1800e7ec6  comiss  xmm6, dword ptr [rbx+90h]
0x1800e7ecd  ja      short loc_1800E7F0D
  ... truncated ...
```
