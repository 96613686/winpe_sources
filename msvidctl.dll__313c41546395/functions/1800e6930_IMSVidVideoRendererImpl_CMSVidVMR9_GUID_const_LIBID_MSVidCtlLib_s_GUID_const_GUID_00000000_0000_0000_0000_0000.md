# IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::Capture(IPictureDisp * *)

- ea: `0x1800e6930`
- end: `0x1800e6aa1`
- name: `?Capture@?$IMSVidVideoRendererImpl@VCMSVidVMR9@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BV?$CComQIPtr@UIVMRFilterConfig9@@$1?_GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8@@3U__s_GUID@@B@ATL@@V?$CComQIPtr@UIVMRWindowlessControl9@@$1?_GUID_8f537d09_f85e_4414_b23b_502e54c79927@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocator9@@$1?_GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRMixerControl9@@$1?_GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRSurfaceAllocatorNotify9@@$1?_GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c@@3U__s_GUID@@B@7@V?$CComQIPtr@UIVMRImageCompositor9@@$1?_GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6@@3U__s_GUID@@B@7@UIMSVidVMR9@@@@UEAAJPEAPEAUIPictureDisp@@@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006b38`
- `0x18001d270`
- `0x1800e6930`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800e6a22`
- `ole32!CoTaskMemFree` at `0x1800e6a22`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x1800e6a5f`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x1800e6a5f`
- `USER32!ReleaseDC` at `0x1800e6a2d`
- `USER32!ReleaseDC` at `0x1800e6a2d`
- `USER32!GetDC` at `0x1800e69ec`
- `USER32!GetDC` at `0x1800e69ec`
- `GDI32!CreateDIBitmap` at `0x1800e6a15`
- `GDI32!CreateDIBitmap` at `0x1800e6a15`

## pseudocode

```c
__int64 __fastcall IMSVidVideoRendererImpl<CMSVidVMR9,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,ATL::CComQIPtr<IVMRFilterConfig9,&__s_GUID const _GUID_5a804648_4f66_4867_9c43_4f5c822cf1b8>,ATL::CComQIPtr<IVMRWindowlessControl9,&__s_GUID const _GUID_8f537d09_f85e_4414_b23b_502e54c79927>,ATL::CComQIPtr<IVMRSurfaceAllocator9,&__s_GUID const _GUID_8d5148ea_3f5d_46cf_9df1_d1b896eedb1f>,ATL::CComQIPtr<IVMRMixerControl9,&__s_GUID const _GUID_1a777eaa_47c8_4930_b2c9_8fee1c1b0f3b>,ATL::CComQIPtr<IVMRSurfaceAllocatorNotify9,&__s_GUID const _GUID_dca3f5df_bb3a_4d03_bd81_84614bfbfa0c>,ATL::CComQIPtr<IVMRImageCompositor9,&__s_GUID const _GUID_4a5c89eb_df51_4654_ac2a_e48e02bbabf6>,IMSVidVMR9>::Capture(
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
  struct tagPICTDESC PictDesc; // [rsp+40h] [rbp-20h] BYREF
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
               &GUID_24dc3975_09bf_4231_8655_3ee71f43837d,
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
0x1800e6930  mov     [rsp-18h+arg_0], rbx
0x1800e6935  push    rbp
0x1800e6936  push    rsi
0x1800e6937  push    rdi
0x1800e6938  mov     rbp, rsp
0x1800e693b  sub     rsp, 60h
0x1800e693f  xor     eax, eax
0x1800e6941  mov     [rbp+lpvObj], 0
0x1800e6949  mov     qword ptr [rbp+PictDesc.8+8], rax
0x1800e694d  xorps   xmm0, xmm0
0x1800e6950  mov     [rbp+arg_8], rax
0x1800e6954  mov     rsi, rdx
0x1800e6957  movups  xmmword ptr [rbp+PictDesc.cbSizeofstruct], xmm0
0x1800e695b  test    rdx, rdx
0x1800e695e  jnz     short loc_1800E696A
0x1800e6960  mov     ebx, 80004003h
0x1800e6965  jmp     loc_1800E6A86
0x1800e696a  cmp     [rcx+0D0h], rax
0x1800e6971  jnz     short loc_1800E697D
0x1800e6973  mov     ebx, 80004005h
0x1800e6978  jmp     loc_1800E6A86
0x1800e697d  mov     rcx, [rcx+0D8h]
0x1800e6984  test    rcx, rcx
0x1800e6987  jnz     short loc_1800E69BF
0x1800e6989  mov     rax, cs:hInstance
0x1800e6990  lea     rcx, _GUID_24dc3975_09bf_4231_8655_3ee71f43837d; clsid
0x1800e6997  mov     [rsp+60h+var_30], rax; HINSTANCE
0x1800e699c  mov     edx, 0C0040590h; dwMessageId
0x1800e69a1  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800e69a8  mov     [rsp+60h+iUsage], 80004005h; int
0x1800e69b0  mov     [rsp+60h+pbmi], rax; struct _GUID *
0x1800e69b5  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800e69ba  jmp     loc_1800E6A84
0x1800e69bf  mov     rax, [rcx]
0x1800e69c2  lea     rdx, [rbp+arg_8]
0x1800e69c6  mov     rax, [rax+68h]
0x1800e69ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e69cf  mov     ebx, eax
0x1800e69d1  test    eax, eax
0x1800e69d3  js      loc_1800E6A86
0x1800e69d9  cmp     [rbp+arg_8], 0
0x1800e69de  jnz     short loc_1800E69EA
0x1800e69e0  mov     ebx, 8000FFFFh
0x1800e69e5  jmp     loc_1800E6A86
0x1800e69ea  xor     ecx, ecx; hWnd
0x1800e69ec  call    cs:__imp_GetDC
0x1800e69f2  mov     rdx, [rbp+arg_8]; pbmih
0x1800e69f6  mov     r8d, 4; flInit
0x1800e69fc  mov     [rsp+60h+iUsage], 0; iUsage
0x1800e6a04  mov     rcx, rax; hdc
0x1800e6a07  mov     rdi, rax
0x1800e6a0a  mov     [rsp+60h+pbmi], rdx; pbmi
0x1800e6a0f  movsxd  r9, dword ptr [rdx]
0x1800e6a12  add     r9, rdx; pjBits
0x1800e6a15  call    cs:__imp_CreateDIBitmap
0x1800e6a1b  mov     rcx, [rbp+arg_8]; pv
0x1800e6a1f  mov     rbx, rax
0x1800e6a22  call    cs:__imp_CoTaskMemFree
0x1800e6a28  mov     rdx, rdi; hDC
0x1800e6a2b  xor     ecx, ecx; hWnd
0x1800e6a2d  call    cs:__imp_ReleaseDC
0x1800e6a33  mov     r8d, 1; fOwn
0x1800e6a39  mov     qword ptr [rbp+PictDesc.8], rbx
0x1800e6a3d  lea     r9, [rbp+lpvObj]; lplpvObj
0x1800e6a41  mov     [rbp+PictDesc.picType], r8d
0x1800e6a45  lea     rdx, IID_IPicture; riid
0x1800e6a4c  mov     qword ptr [rbp+PictDesc.8+8], 0
0x1800e6a54  lea     rcx, [rbp+PictDesc]; lpPictDesc
0x1800e6a58  mov     [rbp+PictDesc.cbSizeofstruct], 18h
0x1800e6a5f  call    cs:__imp_OleCreatePictureIndirect
0x1800e6a65  mov     ebx, eax
0x1800e6a67  test    eax, eax
0x1800e6a69  js      short loc_1800E6A86
0x1800e6a6b  mov     rcx, [rbp+lpvObj]
0x1800e6a6f  lea     rdx, _GUID_7bf80981_bf32_101a_8bbb_00aa00300cab
0x1800e6a76  mov     r8, rsi
0x1800e6a79  mov     rax, [rcx]
0x1800e6a7c  mov     rax, [rax]
0x1800e6a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6a84  mov     ebx, eax
0x1800e6a86  lea     rcx, [rbp+lpvObj]
0x1800e6a8a  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800e6a8f  mov     eax, ebx
0x1800e6a91  mov     rbx, [rsp+60h+arg_0]
0x1800e6a99  add     rsp, 60h
0x1800e6a9d  pop     rdi
0x1800e6a9e  pop     rsi
0x1800e6a9f  pop     rbp
0x1800e6aa0  retn
```
