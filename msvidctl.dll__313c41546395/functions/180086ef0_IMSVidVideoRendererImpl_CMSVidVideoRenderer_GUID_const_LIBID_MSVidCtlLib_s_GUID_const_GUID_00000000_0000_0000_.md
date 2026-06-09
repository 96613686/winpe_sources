# IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::Capture(IPictureDisp * *)

- ea: `0x180086ef0`
- end: `0x180087061`
- name: `?Capture@?$IMSVidVideoRendererImpl@VCMSVidVideoRenderer@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig@@$1?_GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl@@$1?_GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator@@$1?_GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl@@$1?_GUID_1c1a17b0_bed0_415d_974b_dc6696131599@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify@@$1?_GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor@@$1?_GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82@@3U__s_GUID@@B@7@UIMSVidVideoRenderer2@@@@UEAAJPEAPEAUIPictureDisp@@@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006b38`
- `0x18001d270`
- `0x180086ef0`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180086fe2`
- `ole32!CoTaskMemFree` at `0x180086fe2`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x18008701f`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x18008701f`
- `USER32!ReleaseDC` at `0x180086fed`
- `USER32!ReleaseDC` at `0x180086fed`
- `USER32!GetDC` at `0x180086fac`
- `USER32!GetDC` at `0x180086fac`
- `GDI32!CreateDIBitmap` at `0x180086fd5`
- `GDI32!CreateDIBitmap` at `0x180086fd5`

## pseudocode

```c
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVideoRenderer,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig,&__s_GUID const _GUID_9e5530c5_7034_48b4_bb46_0b8a6efc8e36>,ATL::CComQIPtr<IVMRWindowlessControl,&__s_GUID const _GUID_0eb1088c_4dcd_46f0_878f_39dae86a51b7>,ATL::CComQIPtr<IVMRSurfaceAllocator,&__s_GUID const _GUID_31ce832e_4484_458b_8cca_f4d7e3db0b52>,ATL::CComQIPtr<IVMRMixerControl,&__s_GUID const _GUID_1c1a17b0_bed0_415d_974b_dc6696131599>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify,&__s_GUID const _GUID_aada05a8_5a4e_4729_af0b_cea27aed51e2>,ATL::CComQIPtr<IVMRImageCompositor,&__s_GUID const _GUID_7a4fb5af_479f_4074_bb40_ce6722e43c82>,IMSVidVideoRenderer2>::Capture(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  HRESULT v5; // ebx
  __int64 v6; // rcx
  HRESULT v7; // eax
  HDC DC; // rdi
  HBITMAP DIBitmap; // rbx
  char **v11; // [rsp+38h] [rbp-28h]
  tagPICTDESC PictDesc; // [rsp+40h] [rbp-20h] BYREF
  BITMAPINFO *pbmi; // [rsp+88h] [rbp+28h] BYREF
  LPVOID lpvObj; // [rsp+90h] [rbp+30h] BYREF

  lpvObj = 0;
  pbmi = 0;
  memset(&PictDesc, 0, sizeof(PictDesc));
  if ( a2 )
  {
    if ( *(_QWORD *)(a1 + 208) )
    {
      v6 = *(_QWORD *)(a1 + 216);
      if ( v6 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, BITMAPINFO **))(*(_QWORD *)v6 + 104LL))(v6, &pbmi);
        if ( v5 < 0 )
          goto LABEL_13;
        if ( !pbmi )
        {
          v5 = -2147418113;
          goto LABEL_13;
        }
        DC = GetDC(0);
        DIBitmap = CreateDIBitmap(DC, &pbmi->bmiHeader, 4u, (char *)pbmi + (int)pbmi->bmiHeader.biSize, pbmi, 0);
        CoTaskMemFree(pbmi);
        ReleaseDC(0, DC);
        PictDesc.8 = (union tagPICTDESC::$43BF5684F0E8BAFC8B650B528FAB349D)(unsigned __int64)DIBitmap;
        PictDesc.picType = 1;
        PictDesc.cbSizeofstruct = 24;
        v5 = OleCreatePictureIndirect(&PictDesc, &IID_IPicture, 1, &lpvObj);
        if ( v5 < 0 )
          goto LABEL_13;
        v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))lpvObj)(
               lpvObj,
               &GUID_7bf80981_bf32_101a_8bbb_00aa00300cab,
               a2);
      }
      else
      {
        v7 = ATL::AtlSetErrorInfo2(
               &GUID_37b03543_a4c8_11d2_b634_00c04f79498e,
               0xC0040590,
               a3,
               a4,
               &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
               -2147467259,
               hInstance,
               v11);
      }
      v5 = v7;
      goto LABEL_13;
    }
    v5 = -2147467259;
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_13:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&lpvObj);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180086ef0  mov     [rsp-18h+arg_0], rbx
0x180086ef5  push    rbp
0x180086ef6  push    rsi
0x180086ef7  push    rdi
0x180086ef8  mov     rbp, rsp
0x180086efb  sub     rsp, 60h
0x180086eff  xor     eax, eax
0x180086f01  mov     [rbp+lpvObj], 0
0x180086f09  mov     qword ptr [rbp+PictDesc.8+8], rax
0x180086f0d  xorps   xmm0, xmm0
0x180086f10  mov     [rbp+arg_8], rax
0x180086f14  mov     rsi, rdx
0x180086f17  movups  xmmword ptr [rbp+PictDesc.cbSizeofstruct], xmm0
0x180086f1b  test    rdx, rdx
0x180086f1e  jnz     short loc_180086F2A
0x180086f20  mov     ebx, 80004003h
0x180086f25  jmp     loc_180087046
0x180086f2a  cmp     [rcx+0D0h], rax
0x180086f31  jnz     short loc_180086F3D
0x180086f33  mov     ebx, 80004005h
0x180086f38  jmp     loc_180087046
0x180086f3d  mov     rcx, [rcx+0D8h]
0x180086f44  test    rcx, rcx
0x180086f47  jnz     short loc_180086F7F
0x180086f49  mov     rax, cs:hInstance
0x180086f50  lea     rcx, _GUID_37b03543_a4c8_11d2_b634_00c04f79498e; clsid
0x180086f57  mov     [rsp+60h+var_30], rax; HINSTANCE
0x180086f5c  mov     edx, 0C0040590h; dwMessageId
0x180086f61  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x180086f68  mov     [rsp+60h+iUsage], 80004005h; int
0x180086f70  mov     [rsp+60h+pbmi], rax; struct _GUID *
0x180086f75  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x180086f7a  jmp     loc_180087044
0x180086f7f  mov     rax, [rcx]
0x180086f82  lea     rdx, [rbp+arg_8]
0x180086f86  mov     rax, [rax+68h]
0x180086f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f8f  mov     ebx, eax
0x180086f91  test    eax, eax
0x180086f93  js      loc_180087046
0x180086f99  cmp     [rbp+arg_8], 0
0x180086f9e  jnz     short loc_180086FAA
0x180086fa0  mov     ebx, 8000FFFFh
0x180086fa5  jmp     loc_180087046
0x180086faa  xor     ecx, ecx; hWnd
0x180086fac  call    cs:__imp_GetDC
0x180086fb2  mov     rdx, [rbp+arg_8]; pbmih
0x180086fb6  mov     r8d, 4; flInit
0x180086fbc  mov     [rsp+60h+iUsage], 0; iUsage
0x180086fc4  mov     rcx, rax; hdc
0x180086fc7  mov     rdi, rax
0x180086fca  mov     [rsp+60h+pbmi], rdx; pbmi
0x180086fcf  movsxd  r9, dword ptr [rdx]
0x180086fd2  add     r9, rdx; pjBits
0x180086fd5  call    cs:__imp_CreateDIBitmap
0x180086fdb  mov     rcx, [rbp+arg_8]; pv
0x180086fdf  mov     rbx, rax
0x180086fe2  call    cs:__imp_CoTaskMemFree
0x180086fe8  mov     rdx, rdi; hDC
0x180086feb  xor     ecx, ecx; hWnd
0x180086fed  call    cs:__imp_ReleaseDC
0x180086ff3  mov     r8d, 1; fOwn
0x180086ff9  mov     qword ptr [rbp+PictDesc.8], rbx
0x180086ffd  lea     r9, [rbp+lpvObj]; lplpvObj
0x180087001  mov     [rbp+PictDesc.picType], r8d
0x180087005  lea     rdx, IID_IPicture; riid
0x18008700c  mov     qword ptr [rbp+PictDesc.8+8], 0
0x180087014  lea     rcx, [rbp+PictDesc]; lpPictDesc
0x180087018  mov     [rbp+PictDesc.cbSizeofstruct], 18h
0x18008701f  call    cs:__imp_OleCreatePictureIndirect
0x180087025  mov     ebx, eax
0x180087027  test    eax, eax
0x180087029  js      short loc_180087046
0x18008702b  mov     rcx, [rbp+lpvObj]
0x18008702f  lea     rdx, _GUID_7bf80981_bf32_101a_8bbb_00aa00300cab
0x180087036  mov     r8, rsi
0x180087039  mov     rax, [rcx]
0x18008703c  mov     rax, [rax]
0x18008703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087044  mov     ebx, eax
0x180087046  lea     rcx, [rbp+lpvObj]
0x18008704a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18008704f  mov     eax, ebx
0x180087051  mov     rbx, [rsp+60h+arg_0]
0x180087059  add     rsp, 60h
0x18008705d  pop     rdi
0x18008705e  pop     rsi
0x18008705f  pop     rbp
0x180087060  retn
```
