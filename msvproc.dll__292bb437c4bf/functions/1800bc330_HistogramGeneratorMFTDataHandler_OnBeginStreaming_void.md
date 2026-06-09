# HistogramGeneratorMFTDataHandler::OnBeginStreaming(void)

- ea: `0x1800bc330`
- end: `0x1800bcbd3`
- name: `?OnBeginStreaming@HistogramGeneratorMFTDataHandler@@UEAAJXZ`
- size: `2211`
- prototype: `__int64 __fastcall(HistogramGeneratorMFTDataHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000c9d0`
- `0x18000ecf0`
- `0x180014be0`
- `0x18001be4c`
- `0x180036268`
- `0x180054140`
- `0x180054de8`
- `0x180072d1c`
- `0x1800ba54c`
- `0x1800bc330`
- `0x1800bcd48`
- `0x1800bf2f8`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1800bc878`
- `MFPlat!MFCreateAttributes` at `0x1800bc893`
- `MFPlat!MFCreateAttributes` at `0x1800bc878`
- `MFPlat!MFCreateAttributes` at `0x1800bc893`
- `MFPlat!MFCreateMediaType` at `0x1800bc966`
- `MFPlat!MFCreateMediaType` at `0x1800bc97f`
- `MFPlat!MFCreateMediaType` at `0x1800bc966`
- `MFPlat!MFCreateMediaType` at `0x1800bc97f`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800bca65`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800bca81`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800bca65`
- `MFPlat!MFCreateVideoSampleAllocatorEx` at `0x1800bca81`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall HistogramGeneratorMFTDataHandler::OnBeginStreaming(HistogramGeneratorMFTDataHandler *this)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int DX11StreamingResources; // eax
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v8; // r12d
  int v9; // r13d
  int v10; // eax
  bool v11; // al
  MFD3D **v12; // r14
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, _DWORD *, _QWORD, char *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _DWORD *, _QWORD, MFD3D **); // rbx
  unsigned int v17; // eax
  IMFAttributes **p_ppMFAttributes; // rcx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, int *, char *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, int *, char *); // rbx
  int (__fastcall *v24)(__int64, _QWORD *, _QWORD, char *); // rbx
  struct ID3D11Buffer **v25; // r14
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD *, _QWORD, struct ID3D11Buffer **); // rbx
  __int64 v28; // rdi
  int (__fastcall *v29)(__int64, struct ID3D11Buffer *, int *, char *); // rbx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, struct ID3D11Buffer *, int *, char *); // rbx
  HRESULT v32; // eax
  int v33; // eax
  void *v34; // rcx
  bool v35; // sf
  __int64 (__fastcall *SetUINT32)(void *, __int64 *, __int64); // rax
  __int64 v37; // r8
  __int64 *v38; // rdx
  int v39; // eax
  int v40; // eax
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  int v42; // eax
  int v43; // eax
  __int64 *v44; // r10
  __int64 v45; // r11
  struct ID3D11ShaderResourceView **v47; // [rsp+38h] [rbp-C8h]
  struct ID3D11ShaderResourceView **v48; // [rsp+38h] [rbp-C8h]
  IMFAttributes *ppMFAttributes; // [rsp+60h] [rbp-A0h] BYREF
  IMFMediaType *ppMFType; // [rsp+68h] [rbp-98h] BYREF
  char v51[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  __int64 v54; // [rsp+88h] [rbp-78h] BYREF
  int v55; // [rsp+90h] [rbp-70h] BYREF
  __int128 v56; // [rsp+94h] [rbp-6Ch]
  _QWORD v57[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v58; // [rsp+B8h] [rbp-48h]
  int v59; // [rsp+BCh] [rbp-44h]
  _DWORD v60[6]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+E8h] [rbp-18h]

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v51,
    "HistogramGeneratorMFTDataHandler::OnBeginStreaming",
    443);
  v2 = MFGetAttribute2UINT32asUINT64(
         *(_QWORD *)(*((_QWORD *)this + 1) + 48LL),
         &MF_MT_FRAME_SIZE,
         (char *)this + 32,
         (char *)this + 36);
  v3 = *(_QWORD *)(*((_QWORD *)this + 1) + 48LL);
  if ( v2 < 0 )
  {
    DX11StreamingResources = MFGetAttribute2UINT32asUINT64(v3, &MF_MT_FRAME_SIZE, (char *)this + 32, (char *)this + 36);
LABEL_5:
    v7 = DX11StreamingResources;
    goto LABEL_62;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, const GUID *, char *))(*(_QWORD *)v3 + 80LL))(
         v3,
         &MF_MT_SUBTYPE,
         (char *)this + 52);
  v6 = *(_QWORD *)(*((_QWORD *)this + 1) + 48LL);
  if ( v5 < 0 )
  {
    DX11StreamingResources = (*(__int64 (__fastcall **)(__int64, const GUID *, char *))(*(_QWORD *)v6 + 80LL))(
                               v6,
                               &MF_MT_SUBTYPE,
                               (char *)this + 52);
    goto LABEL_5;
  }
  *((_DWORD *)this + 17) = MFGetAttributeUINT32(v6, &MF_MT_TRANSFER_FUNCTION, 0);
  v8 = (int)o_ceilf_0((float)*((int *)this + 9) * 0.015625);
  v9 = (int)o_ceilf_0((float)*((int *)this + 8) * 0.015625);
  v10 = MFGetAttributeUINT32(*(_QWORD *)(*((_QWORD *)this + 1) + 80LL), MF_MT_SECURE, 0);
  *((_BYTE *)this + 48) = v10 != 0;
  if ( !v10 )
    *((_BYTE *)this + 48) = (unsigned int)MFGetAttributeUINT32(*((_QWORD *)this + 31), MFT_USING_HARDWARE_DRM, 0) != 0;
  v11 = (unsigned int)MFGetAttributeUINT32(*((_QWORD *)this + 31), qword_1801441A8, 1) != 0;
  *((_BYTE *)this + 76) = v11;
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      11,
      &WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids,
      this,
      *((unsigned __int8 *)this + 48),
      v11);
  v12 = (MFD3D **)((char *)this + 304);
  if ( !*((_QWORD *)this + 38)
    || !*((_QWORD *)this + 35)
    || *((_DWORD *)this + 11) != v9
    || *((_DWORD *)this + 10) != v8 )
  {
    v54 = 0;
    v53 = 0;
    v52 = 0;
    ppMFAttributes = 0;
    LODWORD(ppMFType) = 0;
    *((_DWORD *)this + 10) = v8;
    *((_DWORD *)this + 11) = v9;
    v61 = 0;
    v62 = 136;
    v60[4] = 61;
    v60[0] = 64;
    v60[1] = v8 * v9;
    v60[3] = 1;
    v60[5] = 1;
    v60[2] = 1;
    v63 = *((_BYTE *)this + 48) != 0 ? 0x80000 : 0;
    v13 = *((_QWORD *)this + 30);
    v14 = *(int (__fastcall **)(__int64, _DWORD *, _QWORD, char *))(*(_QWORD *)v13 + 40LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 304);
    if ( v14(v13, v60, 0, (char *)this + 304) < 0 )
    {
      v15 = *((_QWORD *)this + 30);
      v16 = *(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, MFD3D **))(*(_QWORD *)v15 + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 304);
      v17 = v16(v15, v60, 0, v12);
      goto LABEL_17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 312);
    if ( (int)MFD3D::ShaderInputViewFromTexture(
                *v12,
                0,
                *((_QWORD *)this + 30),
                0,
                (__int64)&ppMFType,
                (unsigned int *)this + 78,
                (struct ID3D11ShaderResourceView **)&ppMFAttributes,
                v47) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 312);
      v17 = MFD3D::ShaderInputViewFromTexture(
              *((MFD3D **)this + 38),
              0,
              *((_QWORD *)this + 30),
              0,
              (__int64)&ppMFType,
              (unsigned int *)this + 78,
              (struct ID3D11ShaderResourceView **)&ppMFAttributes,
              v48);
LABEL_17:
      v7 = v17;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
      p_ppMFAttributes = (IMFAttributes **)&v54;
LABEL_18:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(p_ppMFAttributes);
      goto LABEL_62;
    }
    v56 = 4u;
    v55 = 61;
    v19 = *((_QWORD *)this + 30);
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v19 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 320);
    v21 = v20(v19, *((_QWORD *)this + 38), &v55, (char *)this + 320);
    v22 = *((_QWORD *)this + 30);
    if ( v21 < 0 )
    {
      v23 = *(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v22 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 320);
      v17 = v23(v22, *((_QWORD *)this + 38), &v55, (char *)this + 320);
      goto LABEL_17;
    }
    v57[0] = 256;
    v57[1] = 136;
    v58 = *((_BYTE *)this + 48) != 0 ? 0x80000 : 0;
    v59 = 4;
    v24 = *(int (__fastcall **)(__int64, _QWORD *, _QWORD, char *))(*(_QWORD *)v22 + 24LL);
    v25 = (struct ID3D11Buffer **)((char *)this + 280);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 280);
    if ( v24(v22, v57, 0, (char *)this + 280) < 0 )
    {
      v26 = *((_QWORD *)this + 30);
      v27 = *(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, struct ID3D11Buffer **))(*(_QWORD *)v26 + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 280);
      v17 = v27(v26, v57, 0, v25);
      goto LABEL_17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 288);
    if ( (int)SRVFromBuffer(*((struct ID3D11Device **)this + 30), *v25, (struct ID3D11ShaderResourceView **)this + 36) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 288);
      v17 = SRVFromBuffer(*((struct ID3D11Device **)this + 30), *v25, (struct ID3D11ShaderResourceView **)this + 36);
      goto LABEL_17;
    }
    *(_QWORD *)&v56 = 1;
    *((_QWORD *)&v56 + 1) = 64;
    v55 = 42;
    v28 = *((_QWORD *)this + 30);
    v29 = *(int (__fastcall **)(__int64, struct ID3D11Buffer *, int *, char *))(*(_QWORD *)v28 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
    if ( v29(v28, *v25, &v55, (char *)this + 296) < 0 )
    {
      v30 = *((_QWORD *)this + 30);
      v31 = *(__int64 (__fastcall **)(__int64, struct ID3D11Buffer *, int *, char *))(*(_QWORD *)v30 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
      v17 = v31(v30, *v25, &v55, (char *)this + 296);
      goto LABEL_17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
  }
  if ( !*((_QWORD *)this + 68) )
  {
    ppMFAttributes = 0;
    ppMFType = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
    if ( MFCreateAttributes(&ppMFAttributes, 3u) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
      v32 = MFCreateAttributes(&ppMFAttributes, 3u);
LABEL_33:
      v7 = v32;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      p_ppMFAttributes = &ppMFAttributes;
      goto LABEL_18;
    }
    v33 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
            ppMFAttributes,
            MF_SA_D3D11_USAGE,
            0);
    v34 = ppMFAttributes;
    v35 = v33 < 0;
    SetUINT32 = (__int64 (__fastcall *)(void *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32;
    if ( v35 )
    {
      v37 = 0;
      v38 = MF_SA_D3D11_USAGE;
LABEL_36:
      v32 = SetUINT32(v34, v38, v37);
      goto LABEL_33;
    }
    v39 = SetUINT32(ppMFAttributes, MF_SA_D3D11_BINDFLAGS, 40);
    v34 = ppMFAttributes;
    v35 = v39 < 0;
    SetUINT32 = (__int64 (__fastcall *)(void *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32;
    if ( v35 )
    {
      v37 = 40;
      v38 = MF_SA_D3D11_BINDFLAGS;
      goto LABEL_36;
    }
    if ( (int)SetUINT32(ppMFAttributes, MF_SA_D3D11_HW_PROTECTED, *((unsigned __int8 *)this + 48)) < 0 )
    {
      v32 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
              ppMFAttributes,
              MF_SA_D3D11_HW_PROTECTED,
              *((unsigned __int8 *)this + 48));
      goto LABEL_33;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    if ( MFCreateMediaType(&ppMFType) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      v32 = MFCreateMediaType(&ppMFType);
      goto LABEL_33;
    }
    v40 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT64)(
            ppMFType,
            &MF_MT_FRAME_SIZE,
            0x100000001LL);
    v34 = ppMFType;
    v35 = v40 < 0;
    lpVtbl = ppMFType->lpVtbl;
    if ( v35 )
    {
      v37 = 0x100000001LL;
      v38 = (__int64 *)&MF_MT_FRAME_SIZE;
      SetUINT32 = (__int64 (__fastcall *)(void *, __int64 *, __int64))lpVtbl->SetUINT64;
      goto LABEL_36;
    }
    v42 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))lpVtbl->SetGUID)(
            ppMFType,
            &MF_MT_MAJOR_TYPE,
            &MFMediaType_Video);
    v34 = ppMFType;
    v35 = v42 < 0;
    SetUINT32 = (__int64 (__fastcall *)(void *, __int64 *, __int64))ppMFType->lpVtbl->SetGUID;
    if ( v35 )
    {
      v37 = (__int64)&MFMediaType_Video;
      v38 = (__int64 *)&MF_MT_MAJOR_TYPE;
      goto LABEL_36;
    }
    if ( (int)SetUINT32(ppMFType, (__int64 *)&MF_MT_SUBTYPE, (__int64)&MFVideoFormat_ARGB32) < 0 )
    {
      v32 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
              ppMFType,
              &MF_MT_SUBTYPE,
              &MFVideoFormat_ARGB32);
      goto LABEL_33;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 544);
    if ( MFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, (void **)this + 68) < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 544);
      v32 = MFCreateVideoSampleAllocatorEx(&GUID_545b3a48_3283_4f62_866f_a62d8f598f9f, (void **)this + 68);
      goto LABEL_33;
    }
    v43 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 68) + 24LL))(
            *((_QWORD *)this + 68),
            *((_QWORD *)this + 12));
    v44 = (__int64 *)*((_QWORD *)this + 68);
    v45 = *v44;
    if ( v43 < 0 )
    {
      v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v45 + 24))(*((_QWORD *)this + 68), *((_QWORD *)this + 12));
      goto LABEL_33;
    }
    if ( (*(int (__fastcall **)(__int64 *, __int64, __int64, IMFAttributes *, IMFMediaType *))(v45 + 56))(
           v44,
           1,
           20,
           ppMFAttributes,
           ppMFType) < 0 )
    {
      v32 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, IMFAttributes *, IMFMediaType *))(**((_QWORD **)this + 68)
                                                                                                 + 56LL))(
              *((_QWORD *)this + 68),
              1,
              20,
              ppMFAttributes,
              ppMFType);
      goto LABEL_33;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFAttributes);
  }
  if ( *((_QWORD *)this + 30) && (int)HistogramGeneratorMFTDataHandler::CreateDX11StreamingResources(this) < 0 )
  {
    DX11StreamingResources = HistogramGeneratorMFTDataHandler::CreateDX11StreamingResources(this);
    goto LABEL_5;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      12,
      &WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids,
      this,
      v9,
      v8,
      64,
      16,
      16,
      4,
      4);
  v7 = 0;
LABEL_62:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v51);
  return v7;
}

```

## disassembly

```asm
0x1800bc330  push    rbp
0x1800bc332  push    rbx
0x1800bc333  push    rsi
0x1800bc334  push    rdi
0x1800bc335  push    r12
0x1800bc337  push    r13
0x1800bc339  push    r14
0x1800bc33b  push    r15
0x1800bc33d  lea     rbp, [rsp-8]
0x1800bc342  sub     rsp, 108h
0x1800bc349  mov     rax, cs:__security_cookie
0x1800bc350  xor     rax, rsp
0x1800bc353  mov     [rbp+40h+var_50], rax
0x1800bc357  mov     rsi, rcx
0x1800bc35a  mov     r8d, 1BBh; int
0x1800bc360  lea     rdx, aHistogramgener_3; "HistogramGeneratorMFTDataHandler::OnBeg"...
0x1800bc367  lea     rcx, [rsp+140h+var_D0]; this
0x1800bc36c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800bc371  nop
0x1800bc372  lea     rbx, [rsi+24h]
0x1800bc376  lea     rdi, [rsi+20h]
0x1800bc37a  mov     rcx, [rsi+8]
0x1800bc37e  mov     r9, rbx
0x1800bc381  mov     r8, rdi
0x1800bc384  lea     rdx, MF_MT_FRAME_SIZE
0x1800bc38b  mov     rcx, [rcx+30h]
0x1800bc38f  call    MFGetAttribute2UINT32asUINT64
0x1800bc394  mov     rcx, [rsi+8]
0x1800bc398  mov     rcx, [rcx+30h]
0x1800bc39c  xor     r15d, r15d
0x1800bc39f  test    eax, eax
0x1800bc3a1  jns     short loc_1800BC3B7
0x1800bc3a3  mov     r9, rbx
0x1800bc3a6  mov     r8, rdi
0x1800bc3a9  lea     rdx, MF_MT_FRAME_SIZE
0x1800bc3b0  call    MFGetAttribute2UINT32asUINT64
0x1800bc3b5  jmp     short loc_1800BC3F1
0x1800bc3b7  mov     rax, [rcx]
0x1800bc3ba  lea     r8, [rsi+34h]
0x1800bc3be  lea     rdx, MF_MT_SUBTYPE
0x1800bc3c5  mov     rax, [rax+50h]
0x1800bc3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc3ce  mov     rcx, [rsi+8]
0x1800bc3d2  mov     rcx, [rcx+30h]
0x1800bc3d6  test    eax, eax
0x1800bc3d8  jns     short loc_1800BC3F8
0x1800bc3da  mov     rax, [rcx]
0x1800bc3dd  lea     r8, [rsi+34h]
0x1800bc3e1  lea     rdx, MF_MT_SUBTYPE
0x1800bc3e8  mov     rax, [rax+50h]
0x1800bc3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc3f1  mov     ebx, eax
0x1800bc3f3  jmp     loc_1800BCBA7
0x1800bc3f8  xor     r8d, r8d
0x1800bc3fb  lea     rdx, MF_MT_TRANSFER_FUNCTION
0x1800bc402  call    MFGetAttributeUINT32
0x1800bc407  mov     [rsi+44h], eax
0x1800bc40a  mov     eax, [rbx]
0x1800bc40c  xorps   xmm0, xmm0
0x1800bc40f  cvtsi2ss xmm0, rax
0x1800bc414  mulss   xmm0, cs:__real@3c800000; X
0x1800bc41c  call    _o_ceilf_0
0x1800bc421  cvttss2si r12, xmm0
0x1800bc426  mov     eax, [rdi]
0x1800bc428  xorps   xmm0, xmm0
0x1800bc42b  cvtsi2ss xmm0, rax
0x1800bc430  mulss   xmm0, cs:__real@3c800000; X
0x1800bc438  call    _o_ceilf_0
0x1800bc43d  cvttss2si r13, xmm0
0x1800bc442  mov     rcx, [rsi+8]
0x1800bc446  xor     r8d, r8d
0x1800bc449  lea     rdx, MF_MT_SECURE
0x1800bc450  mov     rcx, [rcx+50h]
0x1800bc454  call    MFGetAttributeUINT32
0x1800bc459  test    eax, eax
0x1800bc45b  setnz   cl
0x1800bc45e  mov     [rsi+30h], cl
0x1800bc461  test    eax, eax
0x1800bc463  jnz     short loc_1800BC483
0x1800bc465  xor     r8d, r8d
0x1800bc468  lea     rdx, MFT_USING_HARDWARE_DRM
0x1800bc46f  mov     rcx, [rsi+0F8h]
0x1800bc476  call    MFGetAttributeUINT32
0x1800bc47b  test    eax, eax
0x1800bc47d  setnz   al
0x1800bc480  mov     [rsi+30h], al
0x1800bc483  mov     ebx, 1
0x1800bc488  mov     r8d, ebx
0x1800bc48b  lea     rdx, qword_1801441A8
0x1800bc492  mov     rcx, [rsi+0F8h]
0x1800bc499  call    MFGetAttributeUINT32
0x1800bc49e  test    eax, eax
0x1800bc4a0  setnz   al
0x1800bc4a3  mov     [rsi+4Ch], al
0x1800bc4a6  cmp     cs:byte_180153DE0, 20h ; ' '
0x1800bc4ad  jb      short loc_1800BC4DE
0x1800bc4af  movzx   eax, al
0x1800bc4b2  movzx   ecx, byte ptr [rsi+30h]
0x1800bc4b6  lea     edx, [rbx+0Ah]
0x1800bc4b9  mov     dword ptr [rsp+140h+var_118], eax
0x1800bc4bd  mov     dword ptr [rsp+140h+var_120], ecx
0x1800bc4c1  mov     r9, rsi
0x1800bc4c4  lea     r8, WPP_30d13c7481f9330926eccd3bdf8c4cd0_Traceguids
0x1800bc4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc4d2  mov     rcx, [rcx+150h]
0x1800bc4d9  call    WPP_SF_qdd
0x1800bc4de  lea     r14, [rsi+130h]
0x1800bc4e5  cmp     [r14], r15
0x1800bc4e8  jz      short loc_1800BC503
0x1800bc4ea  cmp     [rsi+118h], r15
0x1800bc4f1  jz      short loc_1800BC503
0x1800bc4f3  cmp     [rsi+2Ch], r13d
0x1800bc4f7  jnz     short loc_1800BC503
0x1800bc4f9  cmp     [rsi+28h], r12d
0x1800bc4fd  jz      loc_1800BC848
0x1800bc503  mov     [rbp+40h+var_B8], r15
0x1800bc507  mov     [rbp+40h+var_C0], r15
0x1800bc50b  mov     [rsp+140h+var_C8], r15
0x1800bc510  mov     [rsp+140h+ppMFAttributes], r15
0x1800bc515  mov     dword ptr [rsp+140h+ppMFType], r15d
0x1800bc51a  mov     [rsi+28h], r12d
0x1800bc51e  mov     [rsi+2Ch], r13d
0x1800bc522  mov     [rbp+40h+var_68], r15
0x1800bc526  mov     [rbp+40h+var_60], 88h
0x1800bc52e  mov     [rbp+40h+var_70], 3Dh ; '='
0x1800bc535  mov     [rbp+40h+var_80], 40h ; '@'
0x1800bc53c  mov     eax, r13d
0x1800bc53f  imul    eax, r12d
0x1800bc543  mov     [rbp+40h+var_7C], eax
0x1800bc546  mov     [rbp+40h+var_74], ebx
0x1800bc549  mov     [rbp+40h+var_6C], ebx
0x1800bc54c  mov     [rbp+40h+var_78], ebx
0x1800bc54f  mov     al, [rsi+30h]
0x1800bc552  neg     al
0x1800bc554  sbb     ecx, ecx
0x1800bc556  and     ecx, 80000h
0x1800bc55c  mov     [rbp+40h+var_58], ecx
0x1800bc55f  mov     rdi, [rsi+0F0h]
0x1800bc566  mov     rax, [rdi]
0x1800bc569  mov     rbx, [rax+28h]
0x1800bc56d  mov     rcx, r14
0x1800bc570  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc575  mov     r9, r14
0x1800bc578  xor     r8d, r8d
0x1800bc57b  lea     rdx, [rbp+40h+var_80]
0x1800bc57f  mov     rcx, rdi
0x1800bc582  mov     rax, rbx
0x1800bc585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc58a  test    eax, eax
0x1800bc58c  jns     short loc_1800BC5E9
0x1800bc58e  mov     rdi, [rsi+0F0h]
0x1800bc595  mov     rax, [rdi]
0x1800bc598  mov     rbx, [rax+28h]
0x1800bc59c  mov     rcx, r14
0x1800bc59f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5a4  lea     rdx, [rbp+40h+var_80]
0x1800bc5a8  xor     r8d, r8d
0x1800bc5ab  mov     r9, r14
0x1800bc5ae  mov     rcx, rdi
0x1800bc5b1  mov     rax, rbx
0x1800bc5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5b9  mov     ebx, eax
0x1800bc5bb  lea     rcx, [rsp+140h+ppMFAttributes]
0x1800bc5c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5c5  nop
0x1800bc5c6  lea     rcx, [rsp+140h+var_C8]
0x1800bc5cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5d0  nop
0x1800bc5d1  lea     rcx, [rbp+40h+var_C0]
0x1800bc5d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5da  nop
0x1800bc5db  lea     rcx, [rbp+40h+var_B8]
0x1800bc5df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5e4  jmp     loc_1800BCBA7
0x1800bc5e9  lea     rcx, [rsp+140h+ppMFAttributes]
0x1800bc5ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc5f3  lea     rbx, [rsi+138h]
0x1800bc5fa  mov     rcx, rbx
0x1800bc5fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc602  lea     rax, [rsp+140h+ppMFAttributes]
0x1800bc607  mov     [rsp+140h+var_110], rax; struct ID3D11ShaderResourceView **
0x1800bc60c  mov     [rsp+140h+var_118], rbx; unsigned int *
0x1800bc611  lea     rax, [rsp+140h+ppMFType]
0x1800bc616  mov     [rsp+140h+var_120], rax; __int64
0x1800bc61b  xor     r9d, r9d; struct ID3D11Device *
0x1800bc61e  mov     r8, [rsi+0F0h]; unsigned int
0x1800bc625  xor     edx, edx; struct ID3D11Texture2D *
0x1800bc627  mov     rcx, [r14]; this
0x1800bc62a  call    ?ShaderInputViewFromTexture@MFD3D@@YAJPEAUID3D11Texture2D@@KPEAUID3D11Device@@HPEAIPEAPEAUID3D11ShaderResourceView@@3@Z; MFD3D::ShaderInputViewFromTexture(ID3D11Texture2D *,ulong,ID3D11Device *,int,uint *,ID3D11ShaderResourceView * *,ID3D11ShaderResourceView * *)
0x1800bc62f  test    eax, eax
0x1800bc631  jns     short loc_1800BC67B
0x1800bc633  lea     rcx, [rsp+140h+ppMFAttributes]
0x1800bc638  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc63d  mov     rcx, rbx
0x1800bc640  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc645  lea     rax, [rsp+140h+ppMFAttributes]
0x1800bc64a  mov     [rsp+140h+var_110], rax; struct ID3D11ShaderResourceView **
0x1800bc64f  mov     [rsp+140h+var_118], rbx; unsigned int *
0x1800bc654  lea     rax, [rsp+140h+ppMFType]
0x1800bc659  mov     [rsp+140h+var_120], rax; __int64
0x1800bc65e  xor     r9d, r9d; struct ID3D11Device *
0x1800bc661  mov     r8, [rsi+0F0h]; unsigned int
0x1800bc668  xor     edx, edx; struct ID3D11Texture2D *
0x1800bc66a  mov     rcx, [rsi+130h]; this
0x1800bc671  call    ?ShaderInputViewFromTexture@MFD3D@@YAJPEAUID3D11Texture2D@@KPEAUID3D11Device@@HPEAIPEAPEAUID3D11ShaderResourceView@@3@Z; MFD3D::ShaderInputViewFromTexture(ID3D11Texture2D *,ulong,ID3D11Device *,int,uint *,ID3D11ShaderResourceView * *,ID3D11ShaderResourceView * *)
0x1800bc676  jmp     loc_1800BC5B9
0x1800bc67b  mov     [rbp+40h+var_AC+4], r15
0x1800bc67f  mov     [rbp+40h+var_A0], r15d
0x1800bc683  mov     [rbp+40h+var_B0], 3Dh ; '='
0x1800bc68a  mov     dword ptr [rbp+40h+var_AC], 4
0x1800bc691  mov     rdi, [rsi+0F0h]
0x1800bc698  mov     rax, [rdi]
0x1800bc69b  mov     rbx, [rax+40h]
0x1800bc69f  lea     r14, [rsi+140h]
0x1800bc6a6  mov     rcx, r14
0x1800bc6a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc6ae  mov     r9, r14
0x1800bc6b1  lea     r8, [rbp+40h+var_B0]
0x1800bc6b5  mov     rdx, [rsi+130h]
0x1800bc6bc  mov     rcx, rdi
0x1800bc6bf  mov     rax, rbx
0x1800bc6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc6c7  mov     rdi, [rsi+0F0h]
0x1800bc6ce  test    eax, eax
0x1800bc6d0  jns     short loc_1800BC6F1
0x1800bc6d2  mov     rax, [rdi]
0x1800bc6d5  mov     rbx, [rax+40h]
0x1800bc6d9  mov     rcx, r14
0x1800bc6dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc6e1  lea     r8, [rbp+40h+var_B0]
0x1800bc6e5  mov     rdx, [rsi+130h]
0x1800bc6ec  jmp     loc_1800BC5AB
0x1800bc6f1  mov     [rbp+40h+var_98], 100h
0x1800bc6f9  mov     [rbp+40h+var_90], 88h
0x1800bc701  mov     al, [rsi+30h]
0x1800bc704  neg     al
0x1800bc706  sbb     ecx, ecx
0x1800bc708  and     ecx, 80000h
0x1800bc70e  mov     [rbp+40h+var_88], ecx
0x1800bc711  mov     [rbp+40h+var_84], 4
0x1800bc718  mov     rax, [rdi]
0x1800bc71b  mov     rbx, [rax+18h]
0x1800bc71f  lea     r14, [rsi+118h]
0x1800bc726  mov     rcx, r14
0x1800bc729  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc72e  mov     r9, r14
0x1800bc731  xor     r8d, r8d
0x1800bc734  lea     rdx, [rbp+40h+var_98]
0x1800bc738  mov     rcx, rdi
0x1800bc73b  mov     rax, rbx
0x1800bc73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc743  test    eax, eax
0x1800bc745  jns     short loc_1800BC766
0x1800bc747  mov     rdi, [rsi+0F0h]
0x1800bc74e  mov     rax, [rdi]
0x1800bc751  mov     rbx, [rax+18h]
0x1800bc755  mov     rcx, r14
0x1800bc758  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc75d  lea     rdx, [rbp+40h+var_98]
0x1800bc761  jmp     loc_1800BC5A8
0x1800bc766  lea     rbx, [rsi+120h]
0x1800bc76d  mov     rcx, rbx
0x1800bc770  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc775  mov     r8, rbx; struct ID3D11ShaderResourceView **
0x1800bc778  mov     rdx, [r14]; struct ID3D11Buffer *
0x1800bc77b  mov     rcx, [rsi+0F0h]; struct ID3D11Device *
0x1800bc782  call    ?SRVFromBuffer@@YAJPEAUID3D11Device@@PEAUID3D11Buffer@@PEAPEAUID3D11ShaderResourceView@@@Z; SRVFromBuffer(ID3D11Device *,ID3D11Buffer *,ID3D11ShaderResourceView * *)
0x1800bc787  test    eax, eax
0x1800bc789  jns     short loc_1800BC7AA
0x1800bc78b  mov     rcx, rbx
0x1800bc78e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc793  mov     r8, rbx; struct ID3D11ShaderResourceView **
0x1800bc796  mov     rdx, [r14]; struct ID3D11Buffer *
0x1800bc799  mov     rcx, [rsi+0F0h]; struct ID3D11Device *
0x1800bc7a0  call    ?SRVFromBuffer@@YAJPEAUID3D11Device@@PEAUID3D11Buffer@@PEAPEAUID3D11ShaderResourceView@@@Z; SRVFromBuffer(ID3D11Device *,ID3D11Buffer *,ID3D11ShaderResourceView * *)
0x1800bc7a5  jmp     loc_1800BC5B9
0x1800bc7aa  mov     [rbp+40h+var_AC], 1
0x1800bc7b2  mov     qword ptr [rbp-64h], 40h ; '@'
0x1800bc7ba  mov     [rbp+40h+var_B0], 2Ah ; '*'
0x1800bc7c1  mov     rdi, [rsi+0F0h]
0x1800bc7c8  mov     rax, [rdi]
0x1800bc7cb  mov     rbx, [rax+40h]
0x1800bc7cf  lea     r15, [rsi+128h]
0x1800bc7d6  mov     rcx, r15
0x1800bc7d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc7de  mov     r9, r15
0x1800bc7e1  lea     r8, [rbp+40h+var_B0]
0x1800bc7e5  mov     rdx, [r14]
0x1800bc7e8  mov     rcx, rdi
0x1800bc7eb  mov     rax, rbx
0x1800bc7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc7f3  test    eax, eax
0x1800bc7f5  jns     short loc_1800BC81C
0x1800bc7f7  mov     rdi, [rsi+0F0h]
0x1800bc7fe  mov     rax, [rdi]
0x1800bc801  mov     rbx, [rax+40h]
0x1800bc805  mov     rcx, r15
0x1800bc808  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bc80d  mov     r9, r15
0x1800bc810  lea     r8, [rbp+40h+var_B0]
  ... truncated ...
```
