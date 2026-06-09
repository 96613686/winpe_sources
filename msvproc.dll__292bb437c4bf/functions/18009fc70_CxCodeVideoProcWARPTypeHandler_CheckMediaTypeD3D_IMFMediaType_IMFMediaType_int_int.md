# CxCodeVideoProcWARPTypeHandler::CheckMediaTypeD3D(IMFMediaType *,IMFMediaType *,int,int)

- ea: `0x18009fc70`
- end: `0x1800a0029`
- name: `?CheckMediaTypeD3D@CxCodeVideoProcWARPTypeHandler@@UEAAJPEAUIMFMediaType@@0HH@Z`
- size: `953`
- prototype: `__int64 __fastcall(CxCodeVideoProcWARPTypeHandler *__hidden this, struct IMFMediaType *, struct IMFMediaType *, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006f60`
- `0x18000a09c`
- `0x180017f20`
- `0x18001be4c`
- `0x18001c0a0`
- `0x18003639c`
- `0x18003652c`
- `0x1800370a8`
- `0x180054140`
- `0x1800598b0`
- `0x180075dc4`
- `0x18009e2b4`
- `0x18009fc70`
- `0x1800d1010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x18009fd11`
- `d3d11!D3D11CreateDevice` at `0x18009fd11`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcWARPTypeHandler::CheckMediaTypeD3D(
        CxCodeVideoProcWARPTypeHandler *this,
        struct IMFMediaType *a2,
        struct IMFMediaType *a3,
        __int64 a4,
        int a5)
{
  ID3D11Device **ppDevice; // r15
  unsigned int v9; // ebx
  enum DXGI_FORMAT v10; // r13d
  enum DXGI_FORMAT Data1; // r12d
  HRESULT Device; // eax
  int v13; // eax
  enum DXGI_FORMAT *v14; // r8
  __int64 v15; // rdx
  ID3D11Device *v16; // rcx
  bool v17; // zf
  enum DXGI_FORMAT *v18; // r8
  ID3D11Device *v19; // rcx
  int *pFeatureLevels; // [rsp+20h] [rbp-71h]
  int v22; // [rsp+50h] [rbp-41h] BYREF
  enum DXGI_FORMAT v23; // [rsp+54h] [rbp-3Dh] BYREF
  enum DXGI_FORMAT v24; // [rsp+58h] [rbp-39h] BYREF
  enum DXGI_FORMAT v25; // [rsp+5Ch] [rbp-35h] BYREF
  struct _GUID v26; // [rsp+60h] [rbp-31h] BYREF
  GUID v27; // [rsp+70h] [rbp-21h] BYREF
  GUID v28; // [rsp+80h] [rbp-11h] BYREF
  GUID v29; // [rsp+90h] [rbp-1h] BYREF

  ppDevice = (ID3D11Device **)((char *)this + 24);
  v9 = 0;
  v10 = DXGI_FORMAT_UNKNOWN;
  *(_DWORD *)&v26.Data2 = 0;
  Data1 = DXGI_FORMAT_UNKNOWN;
  v26.Data1 = 0;
  v28 = GUID_00000000_0000_0000_0000_000000000000;
  *(_DWORD *)v26.Data4 = 0;
  v29 = GUID_00000000_0000_0000_0000_000000000000;
  *(_DWORD *)&v26.Data4[4] = 0;
  v23 = DXGI_FORMAT_UNKNOWN;
  v24 = DXGI_FORMAT_UNKNOWN;
  v25 = DXGI_FORMAT_UNKNOWN;
  if ( !*((_QWORD *)this + 3) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 24);
    Device = D3D11CreateDevice(0, D3D_DRIVER_TYPE_WARP, 0, 0, 0, 0, 7u, ppDevice, 0, 0);
    v9 = Device;
    if ( Device < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids,
          this,
          Device);
      return v9;
    }
  }
  if ( a2 )
  {
    v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a2->lpVtbl->GetGUID)(
            a2,
            &MF_MT_SUBTYPE,
            &v28);
    v9 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        return v9;
      v15 = 39;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids, this, v13);
      return v9;
    }
    v27 = v28;
    v9 = MFMEDIATYPEUtils::SubtypeToDXGIFormat((MFMEDIATYPEUtils *)&v27, (struct _GUID *)&v26.Data2, v14);
    if ( (v9 & 0x80000000) != 0 )
      return v9;
    v16 = *ppDevice;
    v10 = *(_DWORD *)&v26.Data2;
    v22 = 0;
    v13 = ((__int64 (__fastcall *)(ID3D11Device *, _QWORD, int *))v16->lpVtbl->CheckFormatSupport)(
            v16,
            *(unsigned int *)&v26.Data2,
            &v22);
    v9 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        return v9;
      v15 = 40;
      goto LABEL_11;
    }
    if ( (v22 & 0x20) == 0 )
    {
      v17 = a5 == 0;
      goto LABEL_18;
    }
    if ( !a3 )
      goto LABEL_34;
  }
  else if ( !a3 )
  {
    return v9;
  }
  v13 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a3->lpVtbl->GetGUID)(
          a3,
          &MF_MT_SUBTYPE,
          &v29);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      return v9;
    v15 = 41;
    goto LABEL_11;
  }
  v27 = v29;
  v9 = MFMEDIATYPEUtils::SubtypeToDXGIFormat((MFMEDIATYPEUtils *)&v27, &v26, v18);
  if ( (v9 & 0x80000000) != 0 )
    return v9;
  v19 = *ppDevice;
  v22 = 0;
  Data1 = v26.Data1;
  v13 = ((__int64 (__fastcall *)(ID3D11Device *, _QWORD, int *))v19->lpVtbl->CheckFormatSupport)(v19, v26.Data1, &v22);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      return v9;
    v15 = 42;
    goto LABEL_11;
  }
  if ( (v22 & 0x20) == 0 )
  {
    v17 = a5 == 0;
LABEL_18:
    v9 = -1072875852;
    if ( v17 )
      MF::OriginateError<21>(3222091444LL, L"Format not supported");
    return v9;
  }
  if ( a2 )
  {
    if ( !(unsigned int)LookupFallbackShaderClass(v10, Data1, (enum FallbackColorConversionShaderClass *)&v26) )
    {
      v9 = -1072875852;
      if ( !a5 )
        MF::OriginateError<25>(3222091444LL, L"Conversion not supported");
      return v9;
    }
LABEL_34:
    if ( (int)MFGetAttribute2UINT32asUINT64(a2, &MF_MT_FRAME_SIZE, v26.Data4, &v26.Data4[4]) >= 0
      && (*(_DWORD *)v26.Data4 > 0x4000u || *(_DWORD *)&v26.Data4[4] > 0x4000u) )
    {
      v9 = -1072875852;
      if ( !a5 )
        MF::OriginateError<22>(3222091444LL, L"Input image too large");
      return v9;
    }
    if ( !a3 )
      goto LABEL_49;
  }
  if ( (int)MFGetAttribute2UINT32asUINT64(a3, &MF_MT_FRAME_SIZE, &v23, &v24) >= 0
    && ((unsigned int)v23 > 0x4000 || (unsigned int)v24 > 0x4000) )
  {
    v9 = -1072875852;
    if ( !a5 )
      MF::OriginateError<23>(3222091444LL, L"Output image too large");
    return v9;
  }
  v9 = MFMEDIATYPEUtils::DXGIFormatToDXGIResourceViewFormat(
         (MFMEDIATYPEUtils *)(unsigned int)Data1,
         (enum DXGI_FORMAT)&v23,
         &v24,
         &v25,
         pFeatureLevels);
  if ( (v9 & 0x80000000) != 0 )
    return v9;
  if ( v25 == DXGI_FORMAT_UNKNOWN )
  {
    v9 = -1072875852;
    if ( !a5 )
      MF::OriginateError<16>(3222091444LL, L"No suitable RTV");
    return v9;
  }
LABEL_49:
  if ( a2 )
    return (unsigned int)MFMEDIATYPEUtils::DXGIFormatToDXGIResourceViewFormat(
                           (MFMEDIATYPEUtils *)(unsigned int)v10,
                           (enum DXGI_FORMAT)&v23,
                           &v24,
                           &v25,
                           pFeatureLevels);
  return v9;
}

```

## disassembly

```asm
0x18009fc70  mov     [rsp-8+arg_18], rbx
0x18009fc75  push    rbp
0x18009fc76  push    rsi
0x18009fc77  push    rdi
0x18009fc78  push    r12
0x18009fc7a  push    r13
0x18009fc7c  push    r14
0x18009fc7e  push    r15
0x18009fc80  lea     rbp, [rsp-1Fh]
0x18009fc85  sub     rsp, 0B0h
0x18009fc8c  mov     rax, cs:__security_cookie
0x18009fc93  xor     rax, rsp
0x18009fc96  mov     [rbp+4Fh+var_40], rax
0x18009fc9a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18009fca1  xor     eax, eax
0x18009fca3  lea     r15, [rcx+18h]
0x18009fca7  mov     r14, r8
0x18009fcaa  mov     rsi, rdx
0x18009fcad  mov     rdi, rcx
0x18009fcb0  mov     ebx, eax
0x18009fcb2  mov     r13d, eax
0x18009fcb5  mov     dword ptr [rbp+4Fh+var_7C], eax
0x18009fcb8  mov     r12d, eax
0x18009fcbb  mov     [rbp+4Fh+var_80], eax
0x18009fcbe  movdqu  [rbp+4Fh+var_60], xmm0
0x18009fcc3  mov     dword ptr [rbp+4Fh+var_7C+4], eax
0x18009fcc6  movdqu  [rbp+4Fh+var_50], xmm0
0x18009fccb  mov     dword ptr [rbp+4Fh+var_7C+8], eax
0x18009fcce  mov     [rbp+4Fh+var_8C], eax
0x18009fcd1  mov     [rbp+4Fh+var_88], eax
0x18009fcd4  mov     [rbp+4Fh+var_84], eax
0x18009fcd7  cmp     [r15], rax
0x18009fcda  jnz     short loc_18009FD52
0x18009fcdc  mov     rcx, r15
0x18009fcdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009fce4  xor     eax, eax
0x18009fce6  xor     r9d, r9d; Flags
0x18009fce9  mov     [rsp+0E0h+ppImmediateContext], rax; ppImmediateContext
0x18009fcee  xor     r8d, r8d; Software
0x18009fcf1  mov     [rsp+0E0h+pFeatureLevel], rax; pFeatureLevel
0x18009fcf6  xor     ecx, ecx; pAdapter
0x18009fcf8  mov     [rsp+0E0h+ppDevice], r15; ppDevice
0x18009fcfd  mov     [rsp+0E0h+SDKVersion], 7; SDKVersion
0x18009fd05  lea     edx, [rax+5]; DriverType
0x18009fd08  mov     [rsp+0E0h+FeatureLevels], eax; FeatureLevels
0x18009fd0c  mov     [rsp+0E0h+pFeatureLevels], rax; pFeatureLevels
0x18009fd11  call    cs:__imp_D3D11CreateDevice
0x18009fd17  mov     ebx, eax
0x18009fd19  test    eax, eax
0x18009fd1b  jns     short loc_18009FD52
0x18009fd1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009fd24  jb      loc_1800A0000
0x18009fd2a  mov     edx, 26h ; '&'
0x18009fd2f  mov     dword ptr [rsp+0E0h+pFeatureLevels], eax
0x18009fd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fd3a  lea     r8, WPP_2ecf8b1eac483ccb03f9c6d0bdefe8d2_Traceguids
0x18009fd41  mov     r9, rdi
0x18009fd44  mov     rcx, [rcx+10h]
0x18009fd48  call    WPP_SF_qD
0x18009fd4d  jmp     loc_1800A0000
0x18009fd52  test    rsi, rsi
0x18009fd55  jnz     short loc_18009FD65
0x18009fd57  test    r14, r14
0x18009fd5a  jz      loc_1800A0000
0x18009fd60  jmp     loc_18009FE29
0x18009fd65  mov     rax, [rsi]
0x18009fd68  lea     r8, [rbp+4Fh+var_60]
0x18009fd6c  lea     rdx, MF_MT_SUBTYPE
0x18009fd73  mov     rcx, rsi
0x18009fd76  mov     rax, [rax+50h]
0x18009fd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fd7f  mov     ebx, eax
0x18009fd81  test    eax, eax
0x18009fd83  jns     short loc_18009FD9D
0x18009fd85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009fd8c  jb      loc_1800A0000
0x18009fd92  mov     edx, 27h ; '''
0x18009fd97  mov     dword ptr [rsp+0E0h+pFeatureLevels], eax
0x18009fd9b  jmp     short loc_18009FD33
0x18009fd9d  movaps  xmm0, [rbp+4Fh+var_60]
0x18009fda1  lea     rdx, [rbp+4Fh+var_7C]; struct _GUID
0x18009fda5  lea     rcx, [rbp+4Fh+var_7C+0Ch]; this
0x18009fda9  movdqa  xmmword ptr [rbp+4Fh+var_7C+0Ch], xmm0
0x18009fdae  call    ?SubtypeToDXGIFormat@MFMEDIATYPEUtils@@YAJU_GUID@@PEAW4DXGI_FORMAT@@@Z; MFMEDIATYPEUtils::SubtypeToDXGIFormat(_GUID,DXGI_FORMAT *)
0x18009fdb3  mov     ebx, eax
0x18009fdb5  test    eax, eax
0x18009fdb7  js      loc_1800A0000
0x18009fdbd  mov     rcx, [r15]
0x18009fdc0  lea     r8, [rbp+4Fh+var_90]
0x18009fdc4  mov     r13d, dword ptr [rbp+4Fh+var_7C]
0x18009fdc8  mov     edx, r13d
0x18009fdcb  mov     [rbp+4Fh+var_90], r12d
0x18009fdcf  mov     rax, [rcx]
0x18009fdd2  mov     rax, [rax+0E8h]
0x18009fdd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fdde  mov     ebx, eax
0x18009fde0  test    eax, eax
0x18009fde2  jns     short loc_18009FDF8
0x18009fde4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009fdeb  jb      loc_1800A0000
0x18009fdf1  mov     edx, 28h ; '('
0x18009fdf6  jmp     short loc_18009FD97
0x18009fdf8  test    byte ptr [rbp+4Fh+var_90], 20h
0x18009fdfc  jnz     short loc_18009FE20
0x18009fdfe  cmp     [rbp+4Fh+arg_20], r12d
0x18009fe02  mov     ecx, 0C00D36B4h
0x18009fe07  mov     ebx, ecx
0x18009fe09  jnz     loc_1800A0000
0x18009fe0f  lea     rdx, aFormatNotSuppo; "Format not supported"
0x18009fe16  call    ??$OriginateError@$0BF@@MF@@YAJJAEAY0BF@$$CBG@Z; MF::OriginateError<21>(long,ushort const (&)[21])
0x18009fe1b  jmp     loc_1800A0000
0x18009fe20  test    r14, r14
0x18009fe23  jz      loc_18009FF0D
0x18009fe29  mov     rax, [r14]
0x18009fe2c  lea     r8, [rbp+4Fh+var_50]
0x18009fe30  lea     rdx, MF_MT_SUBTYPE
0x18009fe37  mov     rcx, r14
0x18009fe3a  mov     rax, [rax+50h]
0x18009fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fe43  mov     ebx, eax
0x18009fe45  test    eax, eax
0x18009fe47  jns     short loc_18009FE60
0x18009fe49  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009fe50  jb      loc_1800A0000
0x18009fe56  mov     edx, 29h ; ')'
0x18009fe5b  jmp     loc_18009FD97
0x18009fe60  movaps  xmm0, [rbp+4Fh+var_50]
0x18009fe64  lea     rdx, [rbp+4Fh+var_80]; struct _GUID
0x18009fe68  lea     rcx, [rbp+4Fh+var_7C+0Ch]; this
0x18009fe6c  movdqa  xmmword ptr [rbp+4Fh+var_7C+0Ch], xmm0
0x18009fe71  call    ?SubtypeToDXGIFormat@MFMEDIATYPEUtils@@YAJU_GUID@@PEAW4DXGI_FORMAT@@@Z; MFMEDIATYPEUtils::SubtypeToDXGIFormat(_GUID,DXGI_FORMAT *)
0x18009fe76  mov     ebx, eax
0x18009fe78  test    eax, eax
0x18009fe7a  js      loc_1800A0000
0x18009fe80  mov     rcx, [r15]
0x18009fe83  lea     r8, [rbp+4Fh+var_90]
0x18009fe87  mov     [rbp+4Fh+var_90], r12d
0x18009fe8b  mov     r12d, [rbp+4Fh+var_80]
0x18009fe8f  mov     edx, r12d
0x18009fe92  mov     rax, [rcx]
0x18009fe95  mov     rax, [rax+0E8h]
0x18009fe9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fea1  xor     r15d, r15d
0x18009fea4  mov     ebx, eax
0x18009fea6  test    eax, eax
0x18009fea8  jns     short loc_18009FEC0
0x18009feaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009feb1  jb      loc_1800A0000
0x18009feb7  lea     edx, [r15+2Ah]
0x18009febb  jmp     loc_18009FD97
0x18009fec0  test    byte ptr [rbp+4Fh+var_90], 20h
0x18009fec4  jnz     short loc_18009FECF
0x18009fec6  cmp     [rbp+4Fh+arg_20], r15d
0x18009feca  jmp     loc_18009FE02
0x18009fecf  test    rsi, rsi
0x18009fed2  jz      loc_18009FF65
0x18009fed8  lea     r8, [rbp+4Fh+var_80]; enum FallbackColorConversionShaderClass *
0x18009fedc  mov     edx, r12d; enum DXGI_FORMAT
0x18009fedf  mov     ecx, r13d; enum DXGI_FORMAT
0x18009fee2  call    ?LookupFallbackShaderClass@@YAHW4DXGI_FORMAT@@0PEAW4FallbackColorConversionShaderClass@@@Z; LookupFallbackShaderClass(DXGI_FORMAT,DXGI_FORMAT,FallbackColorConversionShaderClass *)
0x18009fee7  test    eax, eax
0x18009fee9  jnz     short loc_18009FF10
0x18009feeb  mov     ecx, 0C00D36B4h
0x18009fef0  mov     ebx, ecx
0x18009fef2  cmp     [rbp+4Fh+arg_20], r15d
0x18009fef6  jnz     loc_1800A0000
0x18009fefc  lea     rdx, aConversionNotS; "Conversion not supported"
0x18009ff03  call    ??$OriginateError@$0BJ@@MF@@YAJJAEAY0BJ@$$CBG@Z; MF::OriginateError<25>(long,ushort const (&)[25])
0x18009ff08  jmp     loc_1800A0000
0x18009ff0d  xor     r15d, r15d
0x18009ff10  lea     r9, [rbp+4Fh+var_7C+8]
0x18009ff14  mov     rcx, rsi
0x18009ff17  lea     r8, [rbp+4Fh+var_7C+4]
0x18009ff1b  lea     rdx, MF_MT_FRAME_SIZE
0x18009ff22  call    MFGetAttribute2UINT32asUINT64
0x18009ff27  test    eax, eax
0x18009ff29  js      short loc_18009FF5C
0x18009ff2b  mov     eax, 4000h
0x18009ff30  cmp     dword ptr [rbp+4Fh+var_7C+4], eax
0x18009ff33  ja      short loc_18009FF3A
0x18009ff35  cmp     dword ptr [rbp+4Fh+var_7C+8], eax
0x18009ff38  jbe     short loc_18009FF5C
0x18009ff3a  mov     ecx, 0C00D36B4h
0x18009ff3f  mov     ebx, ecx
0x18009ff41  cmp     [rbp+4Fh+arg_20], r15d
0x18009ff45  jnz     loc_1800A0000
0x18009ff4b  lea     rdx, aInputImageTooL; "Input image too large"
0x18009ff52  call    ??$OriginateError@$0BG@@MF@@YAJJAEAY0BG@$$CBG@Z; MF::OriginateError<22>(long,ushort const (&)[22])
0x18009ff57  jmp     loc_1800A0000
0x18009ff5c  test    r14, r14
0x18009ff5f  jz      loc_18009FFE5
0x18009ff65  lea     r9, [rbp+4Fh+var_88]
0x18009ff69  mov     rcx, r14
0x18009ff6c  lea     r8, [rbp+4Fh+var_8C]
0x18009ff70  lea     rdx, MF_MT_FRAME_SIZE
0x18009ff77  call    MFGetAttribute2UINT32asUINT64
0x18009ff7c  test    eax, eax
0x18009ff7e  js      short loc_18009FFAA
0x18009ff80  mov     eax, 4000h
0x18009ff85  cmp     [rbp+4Fh+var_8C], eax
0x18009ff88  ja      short loc_18009FF8F
0x18009ff8a  cmp     [rbp+4Fh+var_88], eax
0x18009ff8d  jbe     short loc_18009FFAA
0x18009ff8f  mov     ecx, 0C00D36B4h
0x18009ff94  mov     ebx, ecx
0x18009ff96  cmp     [rbp+4Fh+arg_20], r15d
0x18009ff9a  jnz     short loc_1800A0000
0x18009ff9c  lea     rdx, aOutputImageToo; "Output image too large"
0x18009ffa3  call    ??$OriginateError@$0BH@@MF@@YAJJAEAY0BH@$$CBG@Z; MF::OriginateError<23>(long,ushort const (&)[23])
0x18009ffa8  jmp     short loc_1800A0000
0x18009ffaa  lea     r9, [rbp+4Fh+var_84]; enum DXGI_FORMAT *
0x18009ffae  mov     ecx, r12d; this
0x18009ffb1  lea     r8, [rbp+4Fh+var_88]; enum DXGI_FORMAT *
0x18009ffb5  lea     rdx, [rbp+4Fh+var_8C]; enum DXGI_FORMAT
0x18009ffb9  call    ?DXGIFormatToDXGIResourceViewFormat@MFMEDIATYPEUtils@@YAJW4DXGI_FORMAT@@PEAW42@1PEAH@Z; MFMEDIATYPEUtils::DXGIFormatToDXGIResourceViewFormat(DXGI_FORMAT,DXGI_FORMAT *,DXGI_FORMAT *,int *)
0x18009ffbe  mov     ebx, eax
0x18009ffc0  test    eax, eax
0x18009ffc2  js      short loc_1800A0000
0x18009ffc4  cmp     [rbp+4Fh+var_84], r15d
0x18009ffc8  jnz     short loc_18009FFE5
0x18009ffca  mov     ecx, 0C00D36B4h
0x18009ffcf  mov     ebx, ecx
0x18009ffd1  cmp     [rbp+4Fh+arg_20], r15d
0x18009ffd5  jnz     short loc_1800A0000
0x18009ffd7  lea     rdx, aNoSuitableRtv; "No suitable RTV"
0x18009ffde  call    ??$OriginateError@$0BA@@MF@@YAJJAEAY0BA@$$CBG@Z; MF::OriginateError<16>(long,ushort const (&)[16])
0x18009ffe3  jmp     short loc_1800A0000
0x18009ffe5  test    rsi, rsi
0x18009ffe8  jz      short loc_1800A0000
0x18009ffea  lea     r9, [rbp+4Fh+var_84]; enum DXGI_FORMAT *
0x18009ffee  mov     ecx, r13d; this
0x18009fff1  lea     r8, [rbp+4Fh+var_88]; enum DXGI_FORMAT *
0x18009fff5  lea     rdx, [rbp+4Fh+var_8C]; enum DXGI_FORMAT
0x18009fff9  call    ?DXGIFormatToDXGIResourceViewFormat@MFMEDIATYPEUtils@@YAJW4DXGI_FORMAT@@PEAW42@1PEAH@Z; MFMEDIATYPEUtils::DXGIFormatToDXGIResourceViewFormat(DXGI_FORMAT,DXGI_FORMAT *,DXGI_FORMAT *,int *)
0x18009fffe  mov     ebx, eax
0x1800a0000  mov     eax, ebx
0x1800a0002  mov     rcx, [rbp+4Fh+var_40]
0x1800a0006  xor     rcx, rsp; StackCookie
0x1800a0009  call    __security_check_cookie
0x1800a000e  mov     rbx, [rsp+0E0h+arg_18]
0x1800a0016  add     rsp, 0B0h
0x1800a001d  pop     r15
0x1800a001f  pop     r14
0x1800a0021  pop     r13
0x1800a0023  pop     r12
0x1800a0025  pop     rdi
0x1800a0026  pop     rsi
0x1800a0027  pop     rbp
0x1800a0028  retn
```
