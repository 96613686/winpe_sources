# IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::SetupMixerBitmap(IPictureDisp *,long,IMSVidRect *)

- ea: `0x1800895c0`
- end: `0x180089c7f`
- name: `?SetupMixerBitmap@?$IMSVidVideoRendererImpl@VCMSVidVideoRenderer@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig@@$1?_GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl@@$1?_GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator@@$1?_GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl@@$1?_GUID_1c1a17b0_bed0_415d_974b_dc6696131599@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify@@$1?_GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@7@UIMSVidVideoRenderer2@@@@UEAAJPEAUIPictureDisp@@JPEAUIMSVidRect@@@Z`
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
- `0x1800895c0`
- `0x1800f8010`

## import_xrefs

- `GDI32!DeleteDC` at `0x180089bae`
- `GDI32!DeleteDC` at `0x180089bae`
- `GDI32!CreateCompatibleDC` at `0x18008980a`
- `GDI32!CreateCompatibleDC` at `0x18008980a`
- `GDI32!SelectObject` at `0x180089872`
- `GDI32!SelectObject` at `0x180089872`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::SetupMixerBitmap(
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
             &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
             0xC0040589,
             v11,
             v12,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147024809,
             hInstance,
             v31);
  if ( (*(int (__fastcall **)(_QWORD, struct tagSIZE *))(*(_QWORD *)*v10 + 56LL))(*v10, &v34) < 0 )
    return ATL::AtlSetErrorInfo2(
             &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
             0xC0040546,
             v13,
             v14,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147221001,
             hInstance,
             v31);
  if ( (*(int (__fastcall **)(_QWORD, LONG *))(*(_QWORD *)*v10 + 48LL))(*v10, &v34.cy) < 0 )
    return ATL::AtlSetErrorInfo2(
             &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
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
             &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
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
               &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
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
      goto LABEL_18;
    }
  }
  else
  {
    v18 = (float)a3 / 100.0;
    *(float *)(a1 + 128) = v18;
  }
  v46 = LODWORD(v18);
LABEL_18:
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
               &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
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
             &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
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
0x1800895c0  mov     rax, rsp
0x1800895c3  push    rbx
0x1800895c4  push    rsi
0x1800895c5  push    rdi
0x1800895c6  push    r14
0x1800895c8  push    r15
0x1800895ca  sub     rsp, 140h
0x1800895d1  movaps  xmmword ptr [rax-38h], xmm6
0x1800895d5  movaps  xmmword ptr [rax-48h], xmm7
0x1800895d9  movaps  xmmword ptr [rax-58h], xmm8
0x1800895de  movaps  xmmword ptr [rax-68h], xmm9
0x1800895e3  movaps  xmmword ptr [rax-78h], xmm10
0x1800895e8  mov     rax, cs:__security_cookie
0x1800895ef  xor     rax, rsp
0x1800895f2  mov     [rsp+168h+var_88], rax
0x1800895fa  mov     rsi, r9
0x1800895fd  mov     r14d, r8d
0x180089600  mov     rdi, rdx
0x180089603  mov     rbx, rcx
0x180089606  xor     edx, edx; Val
0x180089608  lea     r8d, [rdx+40h]; Size
0x18008960c  lea     rcx, [rsp+168h+var_D8]; void *
0x180089614  call    memset_0
0x180089619  xorps   xmm0, xmm0
0x18008961c  movups  [rsp+168h+var_F0], xmm0
0x180089621  mov     [rsp+168h+var_11C.cx], 0
0x180089629  mov     [rsp+168h+var_11C.cy], 0
0x180089631  test    rdi, rdi
0x180089634  jnz     short loc_18008966B
0x180089636  lea     rcx, [rbx+0C8h]
0x18008963d  call    ?Release@?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@ATL@@QEAAXXZ; ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>::Release(void)
0x180089642  lea     eax, [rdi+1]
0x180089645  mov     [rsp+168h+var_D8], eax
0x18008964c  mov     rax, [rbx]
0x18008964f  lea     rdx, [rsp+168h+var_D8]
0x180089657  mov     rcx, rbx
0x18008965a  mov     rax, [rax+0C8h]
0x180089661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089666  jmp     loc_180089C42
0x18008966b  lea     rcx, [rsp+168h+var_128]
0x180089670  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180089674  jnz     short loc_18008969E
0x180089676  lea     rdi, [rbx+0C8h]
0x18008967d  mov     rdx, rdi
0x180089680  call    ??0?$CComQIPtr@UIMSVidGraphSegment@@$1?_GUID_238dec54_adeb_4005_a349_f772b9afebc4@@3U__s_GUID@@B@ATL@@QEAA@AEBV01@@Z; ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4>(ATL::CComQIPtr<IMSVidGraphSegment,&__s_GUID const _GUID_238dec54_adeb_4005_a349_f772b9afebc4> const &)
0x180089685  lea     rcx, [rsp+168h+var_128]
0x18008968a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18008968f  cmp     qword ptr [rsp+168h+var_128.cx], 0
0x180089695  jnz     short loc_1800896DF
0x180089697  xor     eax, eax
0x180089699  jmp     loc_180089C42
0x18008969e  mov     rdx, rdi
0x1800896a1  call    ??0?$CComQIPtr@UIPicture@@$1?_GUID_7bf80980_bf32_101a_8bbb_00aa00300cab@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>::CComQIPtr<IPicture,&__s_GUID const _GUID_7bf80980_bf32_101a_8bbb_00aa00300cab>(IUnknown *)
0x1800896a6  nop
0x1800896a7  mov     rdx, qword ptr [rsp+168h+var_128.cx]; struct IUnknown *
0x1800896ac  test    rdx, rdx
0x1800896af  jnz     short loc_1800896C5
0x1800896b1  lea     rcx, [rsp+168h+var_128]
0x1800896b6  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800896bb  mov     eax, 80004002h
0x1800896c0  jmp     loc_180089C42
0x1800896c5  lea     rdi, [rbx+0C8h]
0x1800896cc  mov     rcx, rdi; struct IUnknown **
0x1800896cf  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800896d4  nop
0x1800896d5  lea     rcx, [rsp+168h+var_128]
0x1800896da  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800896df  xor     eax, eax
0x1800896e1  mov     [rsp+168h+var_120], ax
0x1800896e6  mov     rcx, [rdi]
0x1800896e9  mov     rax, [rcx]
0x1800896ec  lea     rdx, [rsp+168h+var_120]
0x1800896f1  mov     rax, [rax+28h]
0x1800896f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800896fa  mov     eax, 1
0x1800896ff  cmp     [rsp+168h+var_120], ax
0x180089704  jz      short loc_18008973C
0x180089706  mov     rax, cs:hInstance
0x18008970d  mov     [rsp+168h+var_138], rax; HINSTANCE
0x180089712  mov     [rsp+168h+var_140], 80070057h; int
0x18008971a  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x180089721  mov     [rsp+168h+var_148], rax; struct _GUID *
0x180089726  mov     edx, 0C0040589h; dwMessageId
0x18008972b  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x180089732  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180089737  jmp     loc_180089C42
0x18008973c  mov     rcx, [rdi]
0x18008973f  mov     rax, [rcx]
0x180089742  lea     rdx, [rsp+168h+var_11C]
0x180089747  mov     rax, [rax+38h]
0x18008974b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089750  test    eax, eax
0x180089752  jns     short loc_18008978A
0x180089754  mov     rax, cs:hInstance
0x18008975b  mov     [rsp+168h+var_138], rax; HINSTANCE
0x180089760  mov     [rsp+168h+var_140], 800401F7h; int
0x180089768  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x18008976f  mov     [rsp+168h+var_148], rax; struct _GUID *
0x180089774  mov     edx, 0C0040546h; dwMessageId
0x180089779  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x180089780  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180089785  jmp     loc_180089C42
0x18008978a  mov     rcx, [rdi]
0x18008978d  mov     rax, [rcx]
0x180089790  lea     rdx, [rsp+168h+var_11C.cy]
0x180089795  mov     rax, [rax+30h]
0x180089799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008979e  test    eax, eax
0x1800897a0  jns     short loc_1800897D8
0x1800897a2  mov     rax, cs:hInstance
0x1800897a9  mov     [rsp+168h+var_138], rax; HINSTANCE
0x1800897ae  mov     [rsp+168h+var_140], 800401F7h; int
0x1800897b6  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800897bd  mov     [rsp+168h+var_148], rax; struct _GUID *
0x1800897c2  mov     edx, 0C0040546h; dwMessageId
0x1800897c7  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x1800897ce  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800897d3  jmp     loc_180089C42
0x1800897d8  mov     qword ptr [rsp+168h+var_128.cx], 0
0x1800897e1  mov     qword ptr [rsp+168h+var_108.cx], 0
0x1800897ea  lea     rdx, [rsp+168h+var_128]; struct tagSIZE *
0x1800897ef  lea     rcx, [rsp+168h+var_11C.cy]; struct tagSIZE *
0x1800897f4  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x1800897f9  lea     rdx, [rsp+168h+var_108]; struct tagSIZE *
0x1800897fe  lea     rcx, [rsp+168h+var_11C]; struct tagSIZE *
0x180089803  call    ?AtlHiMetricToPixel@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlHiMetricToPixel(tagSIZE const *,tagSIZE *)
0x180089808  xor     ecx, ecx; hdc
0x18008980a  call    cs:__imp_CreateCompatibleDC
0x180089810  mov     r15, rax
0x180089813  mov     [rsp+168h+h], 0
0x18008981c  mov     rcx, [rdi]
0x18008981f  mov     rdx, [rcx]
0x180089822  mov     rax, [rdx+18h]
0x180089826  lea     rdx, [rsp+168h+h]
0x18008982b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089830  test    eax, eax
0x180089832  jns     short loc_18008986A
0x180089834  mov     rax, cs:hInstance
0x18008983b  mov     [rsp+168h+var_138], rax; HINSTANCE
0x180089840  mov     [rsp+168h+var_140], 800401F7h; int
0x180089848  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x18008984f  mov     [rsp+168h+var_148], rax; struct _GUID *
0x180089854  mov     edx, 0C0040546h; dwMessageId
0x180089859  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x180089860  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180089865  jmp     loc_180089C42
0x18008986a  mov     rdx, [rsp+168h+h]; h
0x18008986f  mov     rcx, r15; hdc
0x180089872  call    cs:__imp_SelectObject
0x180089878  mov     rax, qword ptr [rsp+168h+var_F0]
0x18008987d  mov     [rsp+168h+var_C0], rax
0x180089885  mov     eax, [rsp+168h+var_128.cx]
0x180089889  mov     [rsp+168h+var_B8], eax
0x180089890  mov     eax, [rsp+168h+var_108.cx]
0x180089894  mov     [rsp+168h+var_B4], eax
0x18008989b  mov     [rsp+168h+var_D0], r15
0x1800898a3  mov     [rsp+168h+var_D8], 2
0x1800898ae  cmp     r14d, 64h ; 'd'
0x1800898b2  ja      loc_180089AA3
0x1800898b8  movd    xmm0, r14d
0x1800898bd  cvtdq2ps xmm0, xmm0
0x1800898c0  divss   xmm0, cs:__real@42c80000
0x1800898c8  movss   dword ptr [rbx+80h], xmm0
0x1800898d0  xorps   xmm6, xmm6
0x1800898d3  movss   [rsp+168h+var_A0], xmm0
0x1800898dc  test    rsi, rsi
0x1800898df  jz      loc_180089B07
0x1800898e5  mov     [rsp+168h+var_128.cx], 0
0x1800898ed  movss   xmm7, cs:__real@bf800000
0x1800898f5  movaps  xmm10, xmm7
0x1800898f9  mov     rax, [rsi]
0x1800898fc  lea     rdx, [rsp+168h+var_128]
0x180089901  mov     rcx, rsi
0x180089904  mov     rax, [rax+48h]
0x180089908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008990d  test    eax, eax
0x18008990f  js      short loc_180089936
0x180089911  mov     ecx, [rbx+48h]
0x180089914  sub     ecx, [rbx+40h]
0x180089917  jz      short loc_180089936
0x180089919  mov     eax, [rsp+168h+var_128.cx]
0x18008991d  movd    xmm10, eax
0x180089922  cvtdq2ps xmm10, xmm10
0x180089926  test    eax, eax
0x180089928  jle     short loc_180089936
0x18008992a  movd    xmm0, ecx
0x18008992e  cvtdq2ps xmm0, xmm0
0x180089931  divss   xmm10, xmm0
0x180089936  movaps  xmm8, xmm7
0x18008993a  mov     rax, [rsi]
0x18008993d  lea     rdx, [rsp+168h+var_128]
0x180089942  mov     rcx, rsi
0x180089945  mov     rax, [rax+38h]
0x180089949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008994e  test    eax, eax
0x180089950  js      short loc_180089977
0x180089952  mov     ecx, [rbx+4Ch]
0x180089955  sub     ecx, [rbx+44h]
0x180089958  jz      short loc_180089977
0x18008995a  mov     eax, [rsp+168h+var_128.cx]
0x18008995e  movd    xmm8, eax
0x180089963  cvtdq2ps xmm8, xmm8
0x180089967  test    eax, eax
0x180089969  jle     short loc_180089977
0x18008996b  movd    xmm0, ecx
0x18008996f  cvtdq2ps xmm0, xmm0
0x180089972  divss   xmm8, xmm0
0x180089977  movaps  xmm9, xmm7
0x18008997b  mov     rax, [rsi]
0x18008997e  lea     rdx, [rsp+168h+var_128]
0x180089983  mov     rcx, rsi
0x180089986  mov     rax, [rax+58h]
0x18008998a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008998f  test    eax, eax
0x180089991  js      short loc_1800899BD
0x180089993  mov     eax, [rbx+48h]
0x180089996  sub     eax, [rbx+40h]
0x180089999  jz      short loc_1800899BD
0x18008999b  mov     edx, [rsp+168h+var_128.cx]
0x18008999f  test    edx, edx
0x1800899a1  jle     short loc_1800899BD
0x1800899a3  movd    xmm9, edx
0x1800899a8  cvtdq2ps xmm9, xmm9
0x1800899ac  movd    xmm0, eax
0x1800899b0  cvtdq2ps xmm0, xmm0
0x1800899b3  divss   xmm9, xmm0
0x1800899b8  addss   xmm9, xmm10
0x1800899bd  mov     rax, [rsi]
0x1800899c0  lea     rdx, [rsp+168h+var_128]
0x1800899c5  mov     rcx, rsi
0x1800899c8  mov     rax, [rax+68h]
0x1800899cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800899d1  test    eax, eax
0x1800899d3  js      short loc_180089A02
0x1800899d5  mov     eax, [rbx+48h]
0x1800899d8  cmp     eax, [rbx+40h]
0x1800899db  jz      short loc_180089A02
0x1800899dd  mov     eax, [rsp+168h+var_128.cx]
0x1800899e1  test    eax, eax
0x1800899e3  jle     short loc_180089A02
0x1800899e5  movd    xmm7, eax
0x1800899e9  cvtdq2ps xmm7, xmm7
0x1800899ec  mov     eax, [rbx+4Ch]
0x1800899ef  sub     eax, [rbx+44h]
0x1800899f2  movd    xmm0, eax
0x1800899f6  cvtdq2ps xmm0, xmm0
0x1800899f9  divss   xmm7, xmm0
0x1800899fd  addss   xmm7, xmm8
0x180089a02  comiss  xmm6, xmm8
0x180089a06  ja      loc_180089AD1
0x180089a0c  comiss  xmm6, xmm10
0x180089a10  ja      loc_180089AD1
0x180089a16  movss   xmm0, cs:__real@3f800000
0x180089a1e  comiss  xmm8, xmm0
0x180089a22  ja      loc_180089AD1
0x180089a28  comiss  xmm10, xmm0
0x180089a2c  ja      loc_180089AD1
0x180089a32  comiss  xmm6, xmm9
0x180089a36  ja      loc_180089AD1
0x180089a3c  comiss  xmm6, xmm7
0x180089a3f  ja      loc_180089AD1
0x180089a45  comiss  xmm9, xmm0
0x180089a49  ja      loc_180089AD1
0x180089a4f  comiss  xmm7, xmm0
0x180089a52  ja      short loc_180089AD1
0x180089a54  movss   dword ptr [rbx+84h], xmm10
0x180089a5d  movss   dword ptr [rbx+88h], xmm8
0x180089a66  movss   dword ptr [rbx+8Ch], xmm9
0x180089a6f  movss   dword ptr [rbx+90h], xmm7
0x180089a77  movss   dword ptr [rsp+168h+var_B0], xmm10
0x180089a81  movss   dword ptr [rsp+168h+var_B0+4], xmm8
0x180089a8b  movss   [rsp+168h+var_A8], xmm9
0x180089a95  movss   [rsp+168h+var_A4], xmm7
0x180089a9e  jmp     loc_180089B8F
0x180089aa3  cmp     r14d, 0FFFFFFFFh
0x180089aa7  jnz     loc_180089BF7
0x180089aad  movss   xmm0, dword ptr [rbx+80h]
0x180089ab5  xorps   xmm6, xmm6
0x180089ab8  comiss  xmm6, xmm0
0x180089abb  jbe     loc_1800898D3
0x180089ac1  mov     [rsp+168h+var_A0], 3F000000h
0x180089acc  jmp     loc_1800898DC
0x180089ad1  mov     rax, cs:hInstance
0x180089ad8  mov     [rsp+168h+var_138], rax; HINSTANCE
0x180089add  mov     [rsp+168h+var_140], 800401F7h; int
0x180089ae5  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x180089aec  mov     [rsp+168h+var_148], rax; struct _GUID *
0x180089af1  mov     edx, 0C0040588h; dwMessageId
0x180089af6  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x180089afd  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180089b02  jmp     loc_180089C42
0x180089b07  movss   xmm0, dword ptr [rbx+84h]
0x180089b0f  comiss  xmm6, xmm0
0x180089b12  ja      short loc_180089B6D
0x180089b14  comiss  xmm6, dword ptr [rbx+88h]
0x180089b1b  ja      short loc_180089B6D
0x180089b1d  comiss  xmm6, dword ptr [rbx+8Ch]
0x180089b24  ja      short loc_180089B6D
0x180089b26  comiss  xmm6, dword ptr [rbx+90h]
0x180089b2d  ja      short loc_180089B6D
  ... truncated ...
```
