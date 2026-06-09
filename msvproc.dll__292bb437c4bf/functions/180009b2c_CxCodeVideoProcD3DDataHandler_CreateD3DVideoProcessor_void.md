# CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor(void)

- ea: `0x180009b2c`
- end: `0x180009fb5`
- name: `?CreateD3DVideoProcessor@CxCodeVideoProcD3DDataHandler@@QEAAJXZ`
- size: `1161`
- prototype: `__int64 __fastcall(CxCodeVideoProcD3DDataHandler *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800244c4`
- `0x180029350`
- `0x1800a2b64`

## callees

- `0x180005f40`
- `0x180008148`
- `0x180009b2c`
- `0x18000a09c`
- `0x18000a954`
- `0x18000ac20`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014be0`
- `0x180036268`
- `0x18003639c`
- `0x18004c980`
- `0x180053c54`
- `0x1800d1010`

## import_xrefs

- `ext-ms-mf-pal-l2-1-0!XboxVPBltPlatform` at `0x180009b91`
- `ext-ms-mf-pal-l2-1-0!XboxVPBltPlatform` at `0x180009b91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009e2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009eee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009e2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009eee`

## string_xrefs

- `0x180009b44`: `CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor`
- `0x180009e81`: `CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor`
- `0x180009f45`: `CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor(CxCodeVideoProcD3DDataHandler *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  unsigned int v4; // ebx
  unsigned int v5; // esi
  int v6; // eax
  char v7; // cl
  int v8; // edx
  int v9; // ecx
  CxCodeVideoProcMFTDataHandler *v10; // rbx
  int Attributes; // eax
  enum DXGI_COLOR_SPACE_TYPE *v12; // r8
  struct IMFAttributes *v13; // rsi
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  __m128i si128; // xmm3
  __m128i v18; // xmm2
  __int128 v19; // xmm0
  __int64 v20; // rax
  __int128 v21; // xmm1
  __int64 v22; // rax
  int D3DSampleAllocator; // ebx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _OWORD v33[8]; // [rsp+50h] [rbp-29h] BYREF
  struct IMFAttributes *v34; // [rsp+E0h] [rbp+67h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v34,
    "CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor",
    2045);
  v2 = *(_QWORD *)this;
  v34 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(v2 + 56))(this) )
    goto LABEL_14;
  v3 = *((_QWORD *)this + 2);
  v4 = *(_DWORD *)(v3 + 564);
  v5 = *(_DWORD *)(v3 + 328);
  if ( !(unsigned __int8)IsMFXboxVPBltPlatformSupportsHDR8Present() || (v6 = XboxVPBltPlatform(), v7 = 1, !v6) )
    v7 = 0;
  if ( ((v8 = 285212673, v5 <= 0x1C) && _bittest(&v8, v5) || v5 - 87 <= 1)
    && (v4 <= 0x1C && _bittest(&v8, v4) || v4 - 87 <= 1)
    && !v7
    && *(_DWORD *)(*((_QWORD *)this + 2) + 1256LL) != 2
    || (v9 = 0, (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 2) + 1256LL) - 3) <= 1) )
  {
LABEL_14:
    v9 = 1;
  }
  *(_DWORD *)(*((_QWORD *)this + 2) + 984LL) = v9;
  v10 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)this + 4);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Attributes = CxCodeVideoProcMFTDataHandler::GetAttributes(v10, &v34);
  v13 = v34;
  if ( Attributes >= 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 892LL) = MFGetAttributeUINT32(v34, MF_XVP_ENABLE_444_IN_ROLLING_420, 0);
    v14 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v14 + 892) )
      *(_DWORD *)(v14 + 984) = 1;
  }
  if ( !(unsigned int)MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ConvertTypeToDXGIColorSpace(
                        (MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper *)(*((_QWORD *)this + 2) + 288LL),
                        (const struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *)(*((_QWORD *)this + 2) + 312LL),
                        v12) )
  {
    v15 = IsTypeRGB(*(_DWORD *)(*((_QWORD *)this + 2) + 4LL));
    *(_DWORD *)(v16 + 312) = v15 == 0 ? 6 : 0;
    *(_DWORD *)(*((_QWORD *)this + 2) + 316LL) = 1;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      98,
      &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
      this,
      *(_DWORD *)(*((_QWORD *)this + 2) + 312LL),
      *(_DWORD *)(*((_QWORD *)this + 2) + 316LL));
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v18 = _mm_load_si128((const __m128i *)&_xmm);
  memset((char *)&v33[1] + 12, 0, 36);
  *(_DWORD *)(*((_QWORD *)this + 2) + 988LL) = 0;
  DWORD2(v33[0]) = -1;
  *(_OWORD *)((char *)v33 + 12) = 0;
  *(_DWORD *)(*((_QWORD *)this + 2) + 992LL) = 0;
  *(_QWORD *)&v33[0] = 0;
  v19 = v33[0];
  *(_DWORD *)(*((_QWORD *)this + 2) + 920LL) = 0;
  DWORD2(v33[0]) = -1;
  *(_QWORD *)&v33[0] = 0;
  *(_DWORD *)(*((_QWORD *)this + 2) + 120LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 2) + 2144LL) = 1;
  *(_DWORD *)(*((_QWORD *)this + 2) + 1272LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 2) + 1196LL) = *(_DWORD *)(*((_QWORD *)this + 2) + 564LL);
  *(_DWORD *)(*((_QWORD *)this + 2) + 1200LL) = *(_DWORD *)(*((_QWORD *)this + 2) + 564LL);
  v20 = *((_QWORD *)this + 2);
  *(__m128i *)(v20 + 996) = si128;
  *(__m128i *)(v20 + 1012) = v18;
  *(_OWORD *)(v20 + 1028) = v19;
  *(_OWORD *)(v20 + 1044) = v33[1];
  v21 = v33[3];
  *((_QWORD *)&v33[3] + 1) = 0;
  *(_OWORD *)(v20 + 1060) = v33[2];
  *(_OWORD *)(v20 + 1076) = v21;
  *(_DWORD *)(v20 + 1092) = 0;
  v22 = *((_QWORD *)this + 2);
  memset((char *)v33 + 12, 0, 32);
  *(__m128i *)(v22 + 1096) = si128;
  *(__m128i *)(v22 + 1112) = v18;
  *(_OWORD *)((char *)&v33[2] + 8) = 0;
  *(_OWORD *)(v22 + 1128) = v33[0];
  *(_OWORD *)(v22 + 1144) = v33[1];
  *(_OWORD *)(v22 + 1160) = v33[2];
  *(_OWORD *)(v22 + 1176) = v33[3];
  *(_DWORD *)(v22 + 1192) = 0;
  D3DSampleAllocator = (*(__int64 (__fastcall **)(CxCodeVideoProcD3DDataHandler *))(*(_QWORD *)this + 200LL))(this);
  if ( D3DSampleAllocator >= 0 )
  {
    v28 = *((_QWORD *)this + 2);
    if ( (!v28 || !*(_DWORD *)(v28 + 876)) && !*(_DWORD *)(v28 + 884) )
    {
      D3DSampleAllocator = CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator(this);
      if ( D3DSampleAllocator < 0 )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != D3DSampleAllocator )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor",
              2097,
              D3DSampleAllocator);
        }
        if ( g_wppLevels )
        {
          v27 = 100;
          goto LABEL_47;
        }
      }
    }
  }
  else
  {
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != D3DSampleAllocator )
        CallStackContext::TraceFailure(
          v26,
          "CxCodeVideoProcD3DDataHandler::CreateD3DVideoProcessor",
          2090,
          D3DSampleAllocator);
    }
    if ( g_wppLevels )
    {
      v27 = 99;
LABEL_47:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        D3DSampleAllocator);
    }
  }
  if ( v13 )
    ((void (__fastcall *)(struct IMFAttributes *))v13->lpVtbl->Release)(v13);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  return (unsigned int)D3DSampleAllocator;
}

```

## disassembly

```asm
0x180009b2c  push    rbp
0x180009b2e  push    rbx
0x180009b2f  push    rsi
0x180009b30  push    rdi
0x180009b31  push    r14
0x180009b33  push    r15
0x180009b35  lea     rbp, [rsp-2Fh]
0x180009b3a  sub     rsp, 0A8h
0x180009b41  mov     rdi, rcx
0x180009b44  lea     rdx, aCxcodevideopro_86; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x180009b4b  lea     rcx, [rbp+57h+arg_0]; this
0x180009b4f  mov     r8d, 7FDh; int
0x180009b55  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180009b5a  mov     rax, [rdi]
0x180009b5d  xor     r14d, r14d
0x180009b60  mov     rcx, rdi
0x180009b63  mov     [rbp+57h+arg_0], r14
0x180009b67  mov     rax, [rax+38h]
0x180009b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b70  lea     r15d, [r14+1]
0x180009b74  test    al, al
0x180009b76  jz      short loc_180009BF0
0x180009b78  mov     rax, [rdi+10h]
0x180009b7c  mov     ebx, [rax+234h]
0x180009b82  mov     esi, [rax+148h]
0x180009b88  call    IsMFXboxVPBltPlatformSupportsHDR8Present
0x180009b8d  test    al, al
0x180009b8f  jz      short loc_180009B9E
0x180009b91  call    cs:__imp_XboxVPBltPlatform
0x180009b97  mov     cl, r15b
0x180009b9a  test    eax, eax
0x180009b9c  jnz     short loc_180009BA1
0x180009b9e  mov     cl, r14b
0x180009ba1  mov     edx, 11000001h
0x180009ba6  cmp     esi, 1Ch
0x180009ba9  ja      short loc_180009BB0
0x180009bab  bt      edx, esi
0x180009bae  jb      short loc_180009BB8
0x180009bb0  lea     eax, [rsi-57h]
0x180009bb3  cmp     eax, r15d
0x180009bb6  ja      short loc_180009BDB
0x180009bb8  cmp     ebx, 1Ch
0x180009bbb  ja      short loc_180009BC2
0x180009bbd  bt      edx, ebx
0x180009bc0  jb      short loc_180009BCA
0x180009bc2  lea     eax, [rbx-57h]
0x180009bc5  cmp     eax, r15d
0x180009bc8  ja      short loc_180009BDB
0x180009bca  test    cl, cl
0x180009bcc  jnz     short loc_180009BDB
0x180009bce  mov     rax, [rdi+10h]
0x180009bd2  cmp     dword ptr [rax+4E8h], 2
0x180009bd9  jnz     short loc_180009BF0
0x180009bdb  mov     rax, [rdi+10h]
0x180009bdf  mov     ecx, [rax+4E8h]
0x180009be5  sub     ecx, 3
0x180009be8  cmp     ecx, r15d
0x180009beb  mov     ecx, r14d
0x180009bee  ja      short loc_180009BF3
0x180009bf0  mov     ecx, r15d
0x180009bf3  mov     rax, [rdi+10h]
0x180009bf7  mov     [rax+3D8h], ecx
0x180009bfd  lea     rcx, [rbp+57h+arg_0]
0x180009c01  mov     rbx, [rdi+20h]
0x180009c05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180009c0a  lea     rdx, [rbp+57h+arg_0]; struct IMFAttributes **
0x180009c0e  mov     rcx, rbx; this
0x180009c11  call    ?GetAttributes@CxCodeVideoProcMFTDataHandler@@UEAAJPEAPEAUIMFAttributes@@@Z; CxCodeVideoProcMFTDataHandler::GetAttributes(IMFAttributes * *)
0x180009c16  mov     rsi, [rbp+57h+arg_0]
0x180009c1a  test    eax, eax
0x180009c1c  js      short loc_180009C4E
0x180009c1e  xor     r8d, r8d
0x180009c21  lea     rdx, MF_XVP_ENABLE_444_IN_ROLLING_420
0x180009c28  mov     rcx, rsi
0x180009c2b  call    MFGetAttributeUINT32
0x180009c30  mov     rcx, [rdi+10h]
0x180009c34  mov     [rcx+37Ch], eax
0x180009c3a  mov     rax, [rdi+10h]
0x180009c3e  cmp     [rax+37Ch], r14d
0x180009c45  jz      short loc_180009C4E
0x180009c47  mov     [rax+3D8h], r15d
0x180009c4e  mov     rcx, [rdi+10h]
0x180009c52  lea     rdx, [rcx+138h]; struct MFMEDIATYPEUtils::VideoColorSpaceAttributes *
0x180009c59  add     rcx, 120h; this
0x180009c60  call    ?ConvertTypeToDXGIColorSpace@MFMEDIATYPEUtilsHelper@MFMEDIATYPEUtils@@YAHAEBUVideoColorSpaceAttributes@2@PEAW4DXGI_COLOR_SPACE_TYPE@@@Z; MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ConvertTypeToDXGIColorSpace(MFMEDIATYPEUtils::VideoColorSpaceAttributes const &,DXGI_COLOR_SPACE_TYPE *)
0x180009c65  test    eax, eax
0x180009c67  jnz     short loc_180009C8F
0x180009c69  mov     rdx, [rdi+10h]
0x180009c6d  mov     ecx, [rdx+4]; unsigned int
0x180009c70  call    ?IsTypeRGB@@YAHK@Z; IsTypeRGB(ulong)
0x180009c75  neg     eax
0x180009c77  sbb     ecx, ecx
0x180009c79  not     ecx
0x180009c7b  and     ecx, 6
0x180009c7e  mov     [rdx+138h], ecx
0x180009c84  mov     rax, [rdi+10h]
0x180009c88  mov     [rax+13Ch], r15d
0x180009c8f  cmp     cs:byte_180153DE0, 20h ; ' '
0x180009c96  jb      short loc_180009CD2
0x180009c98  mov     rcx, [rdi+10h]
0x180009c9c  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180009ca3  mov     edx, 62h ; 'b'
0x180009ca8  mov     r9, rdi
0x180009cab  mov     eax, [rcx+13Ch]
0x180009cb1  mov     [rsp+0D0h+var_A8], eax
0x180009cb5  mov     eax, [rcx+138h]
0x180009cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc2  mov     [rsp+0D0h+var_B0], eax
0x180009cc6  mov     rcx, [rcx+150h]
0x180009ccd  call    WPP_SF_qdd
0x180009cd2  mov     rax, [rdi+10h]
0x180009cd6  xorps   xmm0, xmm0
0x180009cd9  movdqa  xmm3, cs:__xmm@00000001000000000000000000000002
0x180009ce1  or      edx, 0FFFFFFFFh
0x180009ce4  movdqa  xmm2, cs:__xmm@00000000000000010000000000000000
0x180009cec  movups  [rbp+57h+var_64], xmm0
0x180009cf0  mov     [rax+3DCh], r14d
0x180009cf7  mov     rax, [rdi+10h]
0x180009cfb  movups  [rbp+57h+var_64+0Ch], xmm0
0x180009cff  mov     dword ptr [rbp+57h+var_80+8], edx
0x180009d02  movups  [rbp+57h+var_80+0Ch], xmm0
0x180009d06  mov     [rax+3E0h], r14d
0x180009d0d  mov     rax, [rdi+10h]
0x180009d11  movups  xmm1, xmmword ptr [rbp-19h]
0x180009d15  mov     qword ptr [rbp+57h+var_80], r14
0x180009d19  movups  xmm0, [rbp+57h+var_80]
0x180009d1d  mov     [rax+398h], r14d
0x180009d24  mov     rax, [rdi+10h]
0x180009d28  mov     dword ptr [rbp+57h+var_80+8], edx
0x180009d2b  mov     qword ptr [rbp+57h+var_80], r14
0x180009d2f  mov     [rax+78h], r14d
0x180009d33  mov     rax, [rdi+10h]
0x180009d37  mov     [rax+860h], r15d
0x180009d3e  mov     rax, [rdi+10h]
0x180009d42  mov     [rax+4F8h], r14d
0x180009d49  mov     rcx, [rdi+10h]
0x180009d4d  mov     eax, [rcx+234h]
0x180009d53  mov     [rcx+4ACh], eax
0x180009d59  mov     rcx, [rdi+10h]
0x180009d5d  mov     eax, [rcx+234h]
0x180009d63  mov     [rcx+4B0h], eax
0x180009d69  xor     ecx, ecx
0x180009d6b  mov     rax, [rdi+10h]
0x180009d6f  mov     [rbp+57h+var_48], rcx
0x180009d73  movups  xmmword ptr [rax+3E4h], xmm3
0x180009d7a  movups  xmmword ptr [rax+3F4h], xmm2
0x180009d81  movups  xmmword ptr [rax+404h], xmm0
0x180009d88  movups  xmm0, [rbp+57h+var_64+4]
0x180009d8c  movups  xmmword ptr [rax+414h], xmm1
0x180009d93  movups  xmm1, xmmword ptr [rbp+7]
0x180009d97  mov     [rbp+57h+var_48], rcx
0x180009d9b  movups  xmmword ptr [rax+424h], xmm0
0x180009da2  movups  xmmword ptr [rax+434h], xmm1
0x180009da9  mov     [rax+444h], ecx
0x180009daf  mov     rax, [rdi+10h]
0x180009db3  xorps   xmm0, xmm0
0x180009db6  movups  [rbp+57h+var_64], xmm0
0x180009dba  movups  [rbp+57h+var_80+0Ch], xmm0
0x180009dbe  movups  xmm1, xmmword ptr [rbp-19h]
0x180009dc2  movups  xmmword ptr [rax+448h], xmm3
0x180009dc9  movups  xmmword ptr [rax+458h], xmm2
0x180009dd0  movups  [rbp+57h+var_64+0Ch], xmm0
0x180009dd4  movups  xmm0, [rbp+57h+var_80]
0x180009dd8  movups  xmmword ptr [rax+468h], xmm0
0x180009ddf  movups  xmm0, [rbp+57h+var_64+4]
0x180009de3  movups  xmmword ptr [rax+478h], xmm1
0x180009dea  movups  xmm1, xmmword ptr [rbp+7]
0x180009dee  movups  xmmword ptr [rax+488h], xmm0
0x180009df5  movups  xmmword ptr [rax+498h], xmm1
0x180009dfc  mov     [rax+4A8h], ecx
0x180009e02  mov     rcx, rdi
0x180009e05  mov     rax, [rdi]
0x180009e08  mov     rax, [rax+0C8h]
0x180009e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e14  mov     ebx, eax
0x180009e16  test    eax, eax
0x180009e18  jns     loc_180009EAD
0x180009e1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e25  test    rcx, rcx
0x180009e28  jnz     short loc_180009E6B
0x180009e2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009e30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e37  mov     rcx, rax
0x180009e3a  test    rax, rax
0x180009e3d  jz      short loc_180009E5D
0x180009e3f  mov     rax, [rax]
0x180009e42  mov     edx, 7F0h
0x180009e47  mov     rax, [rax+8]
0x180009e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e50  test    eax, eax
0x180009e52  jz      short loc_180009E5D
0x180009e54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e5b  jmp     short loc_180009E6B
0x180009e5d  lea     rcx, qword_180153440; this
0x180009e64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009e6b  cmp     [rcx+8], r14b
0x180009e6f  jz      short loc_180009E96
0x180009e71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009e76  cmp     [rax+7CCh], ebx
0x180009e7c  jz      short loc_180009E96
0x180009e7e  mov     r9d, ebx; int
0x180009e81  lea     rdx, aCxcodevideopro_86; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x180009e88  mov     r8d, 82Ah; int
0x180009e8e  mov     rcx, rax; this
0x180009e91  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009e96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180009e9d  jb      loc_180009F86
0x180009ea3  mov     edx, 63h ; 'c'
0x180009ea8  jmp     loc_180009F68
0x180009ead  mov     rax, [rdi+10h]
0x180009eb1  test    rax, rax
0x180009eb4  jz      short loc_180009EC3
0x180009eb6  cmp     [rax+36Ch], r14d
0x180009ebd  jnz     loc_180009F86
0x180009ec3  cmp     [rax+374h], r14d
0x180009eca  jnz     loc_180009F86
0x180009ed0  mov     rcx, rdi; this
0x180009ed3  call    ?CreateD3DSampleAllocator@CxCodeVideoProcD3DDataHandler@@IEAAJXZ; CxCodeVideoProcD3DDataHandler::CreateD3DSampleAllocator(void)
0x180009ed8  mov     ebx, eax
0x180009eda  test    eax, eax
0x180009edc  jns     loc_180009F86
0x180009ee2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009ee9  test    rcx, rcx
0x180009eec  jnz     short loc_180009F2F
0x180009eee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009ef4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180009efb  mov     rcx, rax
0x180009efe  test    rax, rax
0x180009f01  jz      short loc_180009F21
0x180009f03  mov     rax, [rax]
0x180009f06  mov     edx, 7F0h
0x180009f0b  mov     rax, [rax+8]
0x180009f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f14  test    eax, eax
0x180009f16  jz      short loc_180009F21
0x180009f18  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f1f  jmp     short loc_180009F2F
0x180009f21  lea     rcx, qword_180153440; this
0x180009f28  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009f2f  cmp     [rcx+8], r14b
0x180009f33  jz      short loc_180009F5A
0x180009f35  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009f3a  cmp     [rax+7CCh], ebx
0x180009f40  jz      short loc_180009F5A
0x180009f42  mov     r9d, ebx; int
0x180009f45  lea     rdx, aCxcodevideopro_86; "CxCodeVideoProcD3DDataHandler::CreateD3"...
0x180009f4c  mov     r8d, 831h; int
0x180009f52  mov     rcx, rax; this
0x180009f55  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009f5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r15b; MFWppLevels g_wppLevels
0x180009f61  jb      short loc_180009F86
0x180009f63  mov     edx, 64h ; 'd'
0x180009f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f6f  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180009f76  mov     r9, rdi
0x180009f79  mov     [rsp+0D0h+var_B0], ebx
0x180009f7d  mov     rcx, [rcx+10h]
0x180009f81  call    WPP_SF_qD
0x180009f86  test    rsi, rsi
0x180009f89  jz      short loc_180009F9A
0x180009f8b  mov     rdx, [rsi]
0x180009f8e  mov     rcx, rsi
0x180009f91  mov     rax, [rdx+10h]
0x180009f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f9a  lea     rcx, [rbp+57h+arg_0]; this
0x180009f9e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180009fa3  mov     eax, ebx
0x180009fa5  add     rsp, 0A8h
0x180009fac  pop     r15
0x180009fae  pop     r14
0x180009fb0  pop     rdi
0x180009fb1  pop     rsi
0x180009fb2  pop     rbx
0x180009fb3  pop     rbp
0x180009fb4  retn
```
