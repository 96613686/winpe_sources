# RenderPassDx11::CRenderPassQuad::Initialize(bool,DXGI_FORMAT,DXGI_FORMAT,ID3D11Device1 *,unsigned __int64,uchar const *,unsigned __int64,uchar const *)

- ea: `0x1800b253c`
- end: `0x1800b2da8`
- name: `?Initialize@CRenderPassQuad@RenderPassDx11@@QEAAJ_NW4DXGI_FORMAT@@1PEAUID3D11Device1@@_KPEBE34@Z`
- size: `2156`
- prototype: `__int64 __fastcall(RenderPassDx11::CRenderPassQuad *__hidden this, bool, enum DXGI_FORMAT, enum DXGI_FORMAT, struct ID3D11Device1 *, unsigned __int64, const unsigned __int8 *, unsigned __int64, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b2350`

## callees

- `0x180014750`
- `0x180067d2c`
- `0x18006adf4`
- `0x18006f46c`
- `0x180075fa0`
- `0x1800b2018`
- `0x1800b253c`
- `0x1800cb010`

## string_xrefs

- `0x1800b2648`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b26c9`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2752`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b27c5`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b282d`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b289d`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2936`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b29ce`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2a5a`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2ae6`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2b5c`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2bcb`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2c7b`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`
- `0x1800b2cf8`: `onecoreuap\windows\directx\dxg\common\autohdrconverter\lib\hdrconverterdx11.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RenderPassDx11::CRenderPassQuad::Initialize(
        RenderPassDx11::CRenderPassQuad *this,
        char a2,
        enum DXGI_FORMAT a3,
        enum DXGI_FORMAT a4,
        struct ID3D11Device1 *a5,
        unsigned __int64 a6,
        const unsigned __int8 *a7,
        unsigned __int64 a8,
        const unsigned __int8 *a9)
{
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  unsigned int v15; // ebx
  struct IUnknown *v16; // rbx
  int v17; // eax
  struct IUnknown *v18; // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  struct IUnknown *v23; // rbx
  int v24; // eax
  struct IUnknown *v25; // rbx
  int v26; // eax
  struct IUnknown *v27; // rbx
  int v28; // eax
  struct IUnknown *v29; // rbx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int *v35; // [rsp+20h] [rbp-E0h]
  struct IUnknown *v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  int v39[2]; // [rsp+68h] [rbp-98h] BYREF
  int v40[2]; // [rsp+70h] [rbp-90h] BYREF
  struct IUnknown *v41; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown *v42; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v43; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown *v44; // [rsp+90h] [rbp-70h] BYREF
  int v45[2]; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  int v50; // [rsp+C0h] [rbp-40h] BYREF
  struct IUnknown *v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-28h] BYREF
  int v54; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v55; // [rsp+E4h] [rbp-1Ch]
  int v56; // [rsp+ECh] [rbp-14h]
  __int64 v57; // [rsp+F0h] [rbp-10h]
  _QWORD v58[3]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h] BYREF
  int v60; // [rsp+120h] [rbp+20h]
  int v61; // [rsp+124h] [rbp+24h]
  int v62; // [rsp+128h] [rbp+28h]
  __int128 v63; // [rsp+12Ch] [rbp+2Ch]
  int v64; // [rsp+13Ch] [rbp+3Ch]
  int v65; // [rsp+140h] [rbp+40h]
  _DWORD v66[4]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v67; // [rsp+158h] [rbp+58h]
  int v68; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+164h] [rbp+64h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  if ( !a5 )
    return 2147942487LL;
  *((_BYTE *)this + 769) = a2;
  *((_BYTE *)this + 770) = a2;
  *(_DWORD *)this = a3;
  *((_DWORD *)this + 1) = a4;
  if ( *((struct ID3D11Device1 **)this + 2) != a5 )
    *((_QWORD *)this + 2) = a5;
  v11 = ((__int64 (__fastcall *)(struct ID3D11Device1 *))a5->lpVtbl->GetCreationFlags)(a5) & 1 | 2;
  v12 = ((__int64 (__fastcall *)(struct ID3D11Device1 *))a5->lpVtbl->GetFeatureLevel)(a5);
  v13 = 40960;
  if ( v12 >= 40960 )
    v13 = v12;
  v50 = v13;
  v46 = 0;
  v51 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64))(**((_QWORD **)this + 2) + 376LL))(
          *((_QWORD *)this + 2),
          v11,
          &v50,
          1);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v16 = v51;
    if ( v51 )
      UCUseAddReferenceCounter(v51);
    *(_QWORD *)v39 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v16;
    unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(v39);
    if ( v46 < 40960 )
    {
      v15 = -2005270524;
      goto LABEL_63;
    }
    v52 = 0;
    v36 = 0;
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, struct IUnknown **))(**((_QWORD **)this + 2) + 192LL))(
            *((_QWORD *)this + 2),
            &v52,
            &v36);
    v15 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v17,
        7);
LABEL_15:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
      goto LABEL_63;
    }
    v18 = v36;
    if ( v36 )
      UCUseAddReferenceCounter(v36);
    *(_QWORD *)v39 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v18;
    unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(v39);
    *(_QWORD *)v37 = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, unsigned __int64, _QWORD))(**((_QWORD **)this + 2)
                                                                                               + 96LL))(
            *((_QWORD *)this + 2),
            a7,
            a6,
            0);
    v15 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v19,
        (int)v37);
LABEL_20:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v37);
      goto LABEL_15;
    }
    unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 40, v37);
    v38 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, char **, __int64, const unsigned __int8 *))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            &off_1800D2EB0,
            2,
            a7);
    v15 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v20,
        a6);
LABEL_23:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
      goto LABEL_20;
    }
    unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 56, &v38);
    *(_QWORD *)v40 = 0;
    v35 = v40;
    v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, unsigned __int64, _QWORD))(**((_QWORD **)this + 2)
                                                                                               + 120LL))(
            *((_QWORD *)this + 2),
            a9,
            a8,
            0);
    v15 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v21,
        (int)v40);
LABEL_26:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v40);
      goto LABEL_23;
    }
    unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 48, v40);
    v58[0] = 512;
    v58[1] = 4;
    v58[2] = 0;
    v41 = 0;
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, struct IUnknown **))(**((_QWORD **)this + 2) + 24LL))(
            *((_QWORD *)this + 2),
            v58,
            0,
            &v41);
    v15 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v22,
        (int)v40);
LABEL_29:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      goto LABEL_26;
    }
    v23 = v41;
    if ( v41 )
      UCUseAddReferenceCounter(v41);
    *(_QWORD *)v39 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v23;
    unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(v39);
    v69 = 0;
    v66[0] = 32;
    v66[1] = 32;
    v66[2] = 32;
    v66[3] = 1;
    v67 = 10;
    v68 = 40;
    v42 = 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, _QWORD, struct IUnknown **))(**((_QWORD **)this + 2) + 48LL))(
            *((_QWORD *)this + 2),
            v66,
            0,
            &v42);
    v15 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v24,
        (int)v40);
LABEL_34:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
      goto LABEL_29;
    }
    v25 = v42;
    if ( v42 )
      UCUseAddReferenceCounter(v42);
    *(_QWORD *)v39 = *((_QWORD *)this + 97);
    *((_QWORD *)this + 97) = v25;
    unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(v39);
    v55 = 8;
    v57 = 0;
    v54 = 10;
    v56 = 1;
    v43 = 0;
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, struct IUnknown **))(**((_QWORD **)this + 2) + 56LL))(
            *((_QWORD *)this + 2),
            *((_QWORD *)this + 97),
            &v54,
            &v43);
    v15 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v26,
        (int)v40);
LABEL_39:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
      goto LABEL_34;
    }
    v27 = v43;
    if ( v43 )
      UCUseAddReferenceCounter(v43);
    *(_QWORD *)v39 = *((_QWORD *)this + 98);
    *((_QWORD *)this + 98) = v27;
    unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(v39);
    if ( *((_BYTE *)this + 769) )
    {
      v44 = 0;
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IUnknown **))(**((_QWORD **)this + 2) + 72LL))(
              *((_QWORD *)this + 2),
              *((_QWORD *)this + 97),
              0,
              &v44);
      v15 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
          (const char *)(unsigned int)v28,
          (int)v40);
LABEL_45:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
        goto LABEL_39;
      }
      v29 = v44;
      if ( v44 )
        UCUseAddReferenceCounter(v44);
      v53 = *((_QWORD *)this + 99);
      *((_QWORD *)this + 99) = v29;
      unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(&v53);
      *(_QWORD *)v45 = 0;
      v30 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD))(**((_QWORD **)this + 2) + 96LL))(
              *((_QWORD *)this + 2),
              qword_1800E6B80,
              848,
              0);
      v15 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
          (const char *)(unsigned int)v30,
          (int)v45);
LABEL_50:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v45);
        goto LABEL_45;
      }
      unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 800, v45);
      v47 = 0;
      v31 = (*(__int64 (__fastcall **)(_QWORD, char **, __int64, __int64 *))(**((_QWORD **)this + 2) + 88LL))(
              *((_QWORD *)this + 2),
              &off_1800D2E50,
              3,
              qword_1800E6B80);
      v15 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE5,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
          (const char *)(unsigned int)v31,
          848);
LABEL_53:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
        goto LABEL_50;
      }
      unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 816, &v47);
      *(_QWORD *)v39 = 0;
      v35 = v39;
      v32 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD))(**((_QWORD **)this + 2) + 120LL))(
              *((_QWORD *)this + 2),
              qword_1800E6ED0,
              6396,
              0);
      v15 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF1,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
          (const char *)(unsigned int)v32,
          (int)v39);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v39);
        goto LABEL_53;
      }
      unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 808, v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v39);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v45);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
    }
    v60 = 0;
    v63 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v61 = 1;
    v62 = 8;
    v64 = 0;
    v65 = 2139095039;
    v48 = 0;
    v33 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, __int64 *))(**((_QWORD **)this + 2) + 184LL))(
            *((_QWORD *)this + 2),
            &si128,
            &v48);
    v15 = v33;
    if ( v33 >= 0 )
    {
      unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 72, &v48);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v61 = 1;
      v62 = 8;
      v64 = 0;
      v65 = 2139095039;
      v49 = 0;
      v34 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, __int64 *))(**((_QWORD **)this + 2) + 184LL))(
              *((_QWORD *)this + 2),
              &si128,
              &v49);
      v15 = v34;
      if ( v34 >= 0 )
      {
        unique_refcntptr<ID3D11PixelShader,0>::operator=((char *)this + 80, &v49);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v40);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v36);
        v15 = 0;
        goto LABEL_63;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v34,
        (int)v35);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
        (const char *)(unsigned int)v33,
        (int)v35);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    goto LABEL_39;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\autohdrconverter\\lib\\hdrconverterdx11.cpp",
    (const char *)(unsigned int)v14,
    7);
LABEL_63:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  return v15;
}

```

## disassembly

```asm
0x1800b253c  push    rbp
0x1800b253e  push    rbx
0x1800b253f  push    rsi
0x1800b2540  push    rdi
0x1800b2541  push    r12
0x1800b2543  push    r13
0x1800b2545  push    r14
0x1800b2547  push    r15
0x1800b2549  lea     rbp, [rsp-88h]
0x1800b2551  sub     rsp, 188h
0x1800b2558  mov     rax, cs:__security_cookie
0x1800b255f  xor     rax, rsp
0x1800b2562  mov     [rbp+0C0h+var_50], rax
0x1800b2566  mov     rdi, rcx
0x1800b2569  mov     rsi, [rbp+0C0h+arg_20]
0x1800b2570  mov     r14, [rbp+0C0h+arg_30]
0x1800b2577  mov     r15, [rbp+0C0h+arg_40]
0x1800b257e  xor     r12d, r12d
0x1800b2581  test    rsi, rsi
0x1800b2584  jnz     short loc_1800B2590
0x1800b2586  mov     eax, 80070057h
0x1800b258b  jmp     loc_1800B2D88
0x1800b2590  mov     [rcx+301h], dl
0x1800b2596  mov     [rcx+302h], dl
0x1800b259c  mov     [rcx], r8d
0x1800b259f  mov     [rcx+4], r9d
0x1800b25a3  cmp     [rcx+10h], rsi
0x1800b25a7  jz      short loc_1800B25AD
0x1800b25a9  mov     [rcx+10h], rsi
0x1800b25ad  mov     rax, [rsi]
0x1800b25b0  mov     rcx, rsi
0x1800b25b3  mov     rax, [rax+130h]
0x1800b25ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b25bf  mov     ebx, eax
0x1800b25c1  mov     r13d, 1
0x1800b25c7  and     ebx, r13d
0x1800b25ca  or      ebx, 2
0x1800b25cd  mov     rax, [rsi]
0x1800b25d0  mov     rcx, rsi
0x1800b25d3  mov     rax, [rax+128h]
0x1800b25da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b25df  mov     esi, 0A000h
0x1800b25e4  mov     ecx, esi
0x1800b25e6  cmp     eax, esi
0x1800b25e8  cmovge  ecx, eax
0x1800b25eb  mov     [rbp+0C0h+var_100], ecx
0x1800b25ee  mov     [rbp+0C0h+var_120], r12d
0x1800b25f2  mov     [rbp+0C0h+var_F8], r12
0x1800b25f6  mov     rcx, [rdi+10h]
0x1800b25fa  mov     rax, [rcx]
0x1800b25fd  lea     rdx, [rbp+0C0h+var_F8]
0x1800b2601  mov     [rsp+1C0h+var_188], rdx
0x1800b2606  lea     rdx, [rbp+0C0h+var_120]
0x1800b260a  mov     [rsp+1C0h+var_190], rdx
0x1800b260f  lea     rdx, _GUID_a04bfb29_08ef_43d6_a49c_a9bdbdcbe686
0x1800b2616  mov     [rsp+1C0h+var_198], rdx
0x1800b261b  mov     [rsp+1C0h+var_1A0], 7; int
0x1800b2623  mov     r9d, r13d
0x1800b2626  lea     r8, [rbp+0C0h+var_100]
0x1800b262a  mov     edx, ebx
0x1800b262c  mov     rax, [rax+178h]
0x1800b2633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2638  mov     ebx, eax
0x1800b263a  test    eax, eax
0x1800b263c  jns     short loc_1800B265D
0x1800b263e  mov     rcx, [rbp+0C8h]; this
0x1800b2645  mov     r9d, eax; char *
0x1800b2648  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b264f  lea     edx, [r13+52h]; void *
0x1800b2653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2658  jmp     loc_1800B2D7D
0x1800b265d  mov     rbx, [rbp+0C0h+var_F8]
0x1800b2661  test    rbx, rbx
0x1800b2664  jz      short loc_1800B266E
0x1800b2666  mov     rcx, rbx; struct IUnknown *
0x1800b2669  call    ?UCUseAddReferenceCounter@@YAXPEAUIUnknown@@@Z; UCUseAddReferenceCounter(IUnknown *)
0x1800b266e  mov     rax, [rdi+18h]
0x1800b2672  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800b2677  mov     [rdi+18h], rbx
0x1800b267b  lea     rcx, [rsp+1C0h+var_158]
0x1800b2680  call    ??1?$unique_refcntptr@UID3DDeviceContextState@@$0A@@@QEAA@XZ; unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(void)
0x1800b2685  cmp     [rbp+0C0h+var_120], esi
0x1800b2688  jge     short loc_1800B2694
0x1800b268a  mov     ebx, 887A0004h
0x1800b268f  jmp     loc_1800B2D7D
0x1800b2694  mov     [rbp+0C0h+var_F0], r12
0x1800b2698  mov     [rsp+1C0h+var_170], r12
0x1800b269d  mov     rcx, [rdi+10h]
0x1800b26a1  mov     rax, [rcx]
0x1800b26a4  lea     r8, [rsp+1C0h+var_170]
0x1800b26a9  lea     rdx, [rbp+0C0h+var_F0]
0x1800b26ad  mov     rax, [rax+0C0h]
0x1800b26b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b26b9  mov     ebx, eax
0x1800b26bb  test    eax, eax
0x1800b26bd  jns     short loc_1800B26E9
0x1800b26bf  mov     rcx, [rbp+0C8h]; this
0x1800b26c6  mov     r9d, eax; char *
0x1800b26c9  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b26d0  mov     edx, 64h ; 'd'; void *
0x1800b26d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b26da  lea     rcx, [rsp+1C0h+var_170]
0x1800b26df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b26e4  jmp     loc_1800B2D7D
0x1800b26e9  mov     rbx, [rsp+1C0h+var_170]
0x1800b26ee  test    rbx, rbx
0x1800b26f1  jz      short loc_1800B26FB
0x1800b26f3  mov     rcx, rbx; struct IUnknown *
0x1800b26f6  call    ?UCUseAddReferenceCounter@@YAXPEAUIUnknown@@@Z; UCUseAddReferenceCounter(IUnknown *)
0x1800b26fb  mov     rax, [rdi+20h]
0x1800b26ff  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800b2704  mov     [rdi+20h], rbx
0x1800b2708  lea     rcx, [rsp+1C0h+var_158]
0x1800b270d  call    ??1?$unique_refcntptr@UID3DDeviceContextState@@$0A@@@QEAA@XZ; unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(void)
0x1800b2712  nop
0x1800b2713  mov     qword ptr [rsp+1C0h+var_168], r12
0x1800b2718  mov     rcx, [rdi+10h]
0x1800b271c  mov     rax, [rcx]
0x1800b271f  lea     rdx, [rsp+1C0h+var_168]
0x1800b2724  mov     qword ptr [rsp+1C0h+var_1A0], rdx; int
0x1800b2729  xor     r9d, r9d
0x1800b272c  mov     rsi, [rbp+0C0h+arg_28]
0x1800b2733  mov     r8, rsi
0x1800b2736  mov     rdx, r14
0x1800b2739  mov     rax, [rax+60h]
0x1800b273d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2742  mov     ebx, eax
0x1800b2744  test    eax, eax
0x1800b2746  jns     short loc_1800B2772
0x1800b2748  mov     rcx, [rbp+0C8h]; this
0x1800b274f  mov     r9d, eax; char *
0x1800b2752  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b2759  mov     edx, 70h ; 'p'; void *
0x1800b275e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2763  lea     rcx, [rsp+1C0h+var_168]
0x1800b2768  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b276d  jmp     loc_1800B26DA
0x1800b2772  lea     rcx, [rdi+28h]
0x1800b2776  lea     rdx, [rsp+1C0h+var_168]
0x1800b277b  call    ??4?$unique_refcntptr@UID3D11PixelShader@@$0A@@@QEAAPEAUID3D11PixelShader@@AEAV?$CComPtr@UID3D11PixelShader@@@ATL@@@Z; unique_refcntptr<ID3D11PixelShader,0>::operator=(ATL::CComPtr<ID3D11PixelShader> &)
0x1800b2780  nop
0x1800b2781  mov     [rsp+1C0h+var_160], r12
0x1800b2786  mov     rcx, [rdi+10h]
0x1800b278a  mov     rax, [rcx]
0x1800b278d  lea     rdx, [rsp+1C0h+var_160]
0x1800b2792  mov     [rsp+1C0h+var_198], rdx
0x1800b2797  mov     qword ptr [rsp+1C0h+var_1A0], rsi; int
0x1800b279c  mov     r9, r14
0x1800b279f  mov     r8d, 2
0x1800b27a5  lea     rdx, off_1800D2EB0; "POSITION"
0x1800b27ac  mov     rax, [rax+58h]
0x1800b27b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b27b5  mov     ebx, eax
0x1800b27b7  test    eax, eax
0x1800b27b9  jns     short loc_1800B27E2
0x1800b27bb  mov     rcx, [rbp+0C8h]; this
0x1800b27c2  mov     r9d, eax; char *
0x1800b27c5  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b27cc  mov     edx, 7Dh ; '}'; void *
0x1800b27d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b27d6  lea     rcx, [rsp+1C0h+var_160]
0x1800b27db  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b27e0  jmp     short loc_1800B2763
0x1800b27e2  lea     rcx, [rdi+38h]
0x1800b27e6  lea     rdx, [rsp+1C0h+var_160]
0x1800b27eb  call    ??4?$unique_refcntptr@UID3D11PixelShader@@$0A@@@QEAAPEAUID3D11PixelShader@@AEAV?$CComPtr@UID3D11PixelShader@@@ATL@@@Z; unique_refcntptr<ID3D11PixelShader,0>::operator=(ATL::CComPtr<ID3D11PixelShader> &)
0x1800b27f0  nop
0x1800b27f1  mov     qword ptr [rsp+1C0h+var_150], r12
0x1800b27f6  mov     rcx, [rdi+10h]
0x1800b27fa  mov     rax, [rcx]
0x1800b27fd  lea     rdx, [rsp+1C0h+var_150]
0x1800b2802  mov     qword ptr [rsp+1C0h+var_1A0], rdx; int
0x1800b2807  xor     r9d, r9d
0x1800b280a  mov     r8, [rbp+0C0h+arg_38]
0x1800b2811  mov     rdx, r15
0x1800b2814  mov     rax, [rax+78h]
0x1800b2818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b281d  mov     ebx, eax
0x1800b281f  test    eax, eax
0x1800b2821  jns     short loc_1800B284A
0x1800b2823  mov     rcx, [rbp+0C8h]; this
0x1800b282a  mov     r9d, eax; char *
0x1800b282d  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b2834  mov     edx, 89h; void *
0x1800b2839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b283e  lea     rcx, [rsp+1C0h+var_150]
0x1800b2843  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b2848  jmp     short loc_1800B27D6
0x1800b284a  lea     rcx, [rdi+30h]
0x1800b284e  lea     rdx, [rsp+1C0h+var_150]
0x1800b2853  call    ??4?$unique_refcntptr@UID3D11PixelShader@@$0A@@@QEAAPEAUID3D11PixelShader@@AEAV?$CComPtr@UID3D11PixelShader@@@ATL@@@Z; unique_refcntptr<ID3D11PixelShader,0>::operator=(ATL::CComPtr<ID3D11PixelShader> &)
0x1800b2858  mov     [rbp+0C0h+var_C8], 200h
0x1800b2860  mov     [rbp+0C0h+var_C0], 4
0x1800b2868  mov     [rbp+0C0h+var_B8], r12
0x1800b286c  mov     [rsp+1C0h+var_148], r12
0x1800b2871  mov     rcx, [rdi+10h]
0x1800b2875  mov     rax, [rcx]
0x1800b2878  lea     r9, [rsp+1C0h+var_148]
0x1800b287d  xor     r8d, r8d
0x1800b2880  lea     rdx, [rbp+0C0h+var_C8]
0x1800b2884  mov     rax, [rax+18h]
0x1800b2888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b288d  mov     ebx, eax
0x1800b288f  test    eax, eax
0x1800b2891  jns     short loc_1800B28BA
0x1800b2893  mov     rcx, [rbp+0C8h]; this
0x1800b289a  mov     r9d, eax; char *
0x1800b289d  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b28a4  mov     edx, 9Ch; void *
0x1800b28a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b28ae  lea     rcx, [rsp+1C0h+var_148]
0x1800b28b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b28b8  jmp     short loc_1800B283E
0x1800b28ba  mov     rbx, [rsp+1C0h+var_148]
0x1800b28bf  test    rbx, rbx
0x1800b28c2  jz      short loc_1800B28CC
0x1800b28c4  mov     rcx, rbx; struct IUnknown *
0x1800b28c7  call    ?UCUseAddReferenceCounter@@YAXPEAUIUnknown@@@Z; UCUseAddReferenceCounter(IUnknown *)
0x1800b28cc  mov     rax, [rdi+40h]
0x1800b28d0  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800b28d5  mov     [rdi+40h], rbx
0x1800b28d9  lea     rcx, [rsp+1C0h+var_158]
0x1800b28de  call    ??1?$unique_refcntptr@UID3DDeviceContextState@@$0A@@@QEAA@XZ; unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(void)
0x1800b28e3  mov     [rbp+0C0h+var_5C], r12
0x1800b28e7  mov     eax, 20h ; ' '
0x1800b28ec  mov     [rbp+0C0h+var_78], eax
0x1800b28ef  mov     [rbp+0C0h+var_74], eax
0x1800b28f2  mov     [rbp+0C0h+var_70], eax
0x1800b28f5  mov     [rbp+0C0h+var_6C], r13d
0x1800b28f9  lea     esi, [rax-16h]
0x1800b28fc  mov     [rbp+0C0h+var_68], rsi
0x1800b2900  mov     [rbp+0C0h+var_60], 28h ; '('
0x1800b2907  mov     [rbp+0C0h+var_140], r12
0x1800b290b  mov     rcx, [rdi+10h]
0x1800b290f  mov     rax, [rcx]
0x1800b2912  lea     r9, [rbp+0C0h+var_140]
0x1800b2916  xor     r8d, r8d
0x1800b2919  lea     rdx, [rbp+0C0h+var_78]
0x1800b291d  mov     rax, [rax+30h]
0x1800b2921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2926  mov     ebx, eax
0x1800b2928  test    eax, eax
0x1800b292a  jns     short loc_1800B2955
0x1800b292c  mov     rcx, [rbp+0C8h]; this
0x1800b2933  mov     r9d, eax; char *
0x1800b2936  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b293d  mov     edx, 0B2h; void *
0x1800b2942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2947  lea     rcx, [rbp+0C0h+var_140]
0x1800b294b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b2950  jmp     loc_1800B28AE
0x1800b2955  mov     rbx, [rbp+0C0h+var_140]
0x1800b2959  test    rbx, rbx
0x1800b295c  jz      short loc_1800B2966
0x1800b295e  mov     rcx, rbx; struct IUnknown *
0x1800b2961  call    ?UCUseAddReferenceCounter@@YAXPEAUIUnknown@@@Z; UCUseAddReferenceCounter(IUnknown *)
0x1800b2966  mov     rax, [rdi+308h]
0x1800b296d  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800b2972  mov     [rdi+308h], rbx
0x1800b2979  lea     rcx, [rsp+1C0h+var_158]
0x1800b297e  call    ??1?$unique_refcntptr@UID3DDeviceContextState@@$0A@@@QEAA@XZ; unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(void)
0x1800b2983  mov     [rbp+0C0h+var_DC], 8
0x1800b298b  mov     [rbp+0C0h+var_D0], r12
0x1800b298f  mov     [rbp+0C0h+var_E0], esi
0x1800b2992  mov     esi, 8
0x1800b2997  mov     [rbp+0C0h+var_D4], r13d
0x1800b299b  mov     [rbp+0C0h+var_138], r12
0x1800b299f  mov     rcx, [rdi+10h]
0x1800b29a3  mov     rax, [rcx]
0x1800b29a6  lea     r9, [rbp+0C0h+var_138]
0x1800b29aa  lea     r8, [rbp+0C0h+var_E0]
0x1800b29ae  mov     rdx, [rdi+308h]
0x1800b29b5  mov     rax, [rax+38h]
0x1800b29b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b29be  mov     ebx, eax
0x1800b29c0  test    eax, eax
0x1800b29c2  jns     short loc_1800B29ED
0x1800b29c4  mov     rcx, [rbp+0C8h]; this
0x1800b29cb  mov     r9d, eax; char *
0x1800b29ce  lea     r8, aOnecoreuapWind_8; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x1800b29d5  mov     edx, 0BFh; void *
0x1800b29da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b29df  lea     rcx, [rbp+0C0h+var_138]
0x1800b29e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800b29e8  jmp     loc_1800B2947
0x1800b29ed  mov     rbx, [rbp+0C0h+var_138]
0x1800b29f1  test    rbx, rbx
0x1800b29f4  jz      short loc_1800B29FE
0x1800b29f6  mov     rcx, rbx; struct IUnknown *
0x1800b29f9  call    ?UCUseAddReferenceCounter@@YAXPEAUIUnknown@@@Z; UCUseAddReferenceCounter(IUnknown *)
0x1800b29fe  mov     rax, [rdi+310h]
0x1800b2a05  mov     qword ptr [rsp+1C0h+var_158], rax
0x1800b2a0a  mov     [rdi+310h], rbx
0x1800b2a11  lea     rcx, [rsp+1C0h+var_158]
0x1800b2a16  call    ??1?$unique_refcntptr@UID3DDeviceContextState@@$0A@@@QEAA@XZ; unique_refcntptr<ID3DDeviceContextState,0>::~unique_refcntptr<ID3DDeviceContextState,0>(void)
0x1800b2a1b  cmp     [rdi+301h], r12b
0x1800b2a22  jz      loc_1800B2C1E
0x1800b2a28  mov     [rbp+0C0h+var_130], r12
0x1800b2a2c  mov     rcx, [rdi+10h]
0x1800b2a30  mov     rax, [rcx]
  ... truncated ...
```
