# CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D(void)

- ea: `0x180031034`
- end: `0x1800319a7`
- name: `?OnInputTypeChangedD3D@CxCodeVideoProcMFTTypeHandler@@QEAAJXZ`
- size: `2419`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *__hidden this)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001abd4`
- `0x1800309c0`

## callees

- `0x180005f64`
- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014be0`
- `0x18001abd4`
- `0x18001be4c`
- `0x180023cbc`
- `0x180031034`
- `0x180032994`
- `0x18003639c`
- `0x180036fe0`
- `0x180054140`
- `0x1800c71f8`
- `0x1800c8548`
- `0x1800cfec0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800314b8`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800314b8`
- `MFPlat!MFCreateMediaType` at `0x18003125f`
- `MFPlat!MFCreateMediaType` at `0x180031422`
- `MFPlat!MFCreateMediaType` at `0x18003125f`
- `MFPlat!MFCreateMediaType` at `0x180031422`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D(CxCodeVideoProcMFTTypeHandler *this)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v3; // ebx
  __int128 v4; // xmm0
  HRESULT inited; // ebx
  unsigned int v6; // r8d
  CallStackTracing *v7; // rcx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  CallStackTracing *v10; // rcx
  struct CallStackContext *v11; // rax
  __int64 v12; // rcx
  struct IMFAttributes *v13; // rcx
  int v14; // eax
  int v15; // r15d
  int v16; // r12d
  CallStackTracing *v17; // rcx
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  unsigned int i; // r14d
  __int64 v24; // rax
  struct IMFMediaType *v25; // rax
  unsigned int v26; // r9d
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *v35; // rax
  CallStackTracing *v36; // rcx
  struct CallStackContext *v37; // rax
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  IMFMediaType *v49; // [rsp+30h] [rbp-49h] BYREF
  char v50[8]; // [rsp+38h] [rbp-41h] BYREF
  IMFMediaType *ppMFType; // [rsp+40h] [rbp-39h] BYREF
  struct IMFAttributes *v52; // [rsp+48h] [rbp-31h] BYREF
  DWORD dwWidth; // [rsp+50h] [rbp-29h] BYREF
  LONG pStride; // [rsp+54h] [rbp-25h] BYREF
  char v55[8]; // [rsp+58h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-19h] BYREF
  __int128 Buf2; // [rsp+70h] [rbp-9h] BYREF

  v52 = 0;
  ppMFType = 0;
  Buf2 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v50,
    "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D",
    8447);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v4 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 48) + 280LL))(
                      *((_QWORD *)this + 48),
                      &Buf1);
    *((_DWORD *)ThreadRelativeContext + 504) = v3;
    *((_OWORD *)ThreadRelativeContext + 125) = v4;
  }
  inited = CxCodeVideoProcMFTTypeHandler::CheckD3DVideoDevice(this);
  if ( inited < 0 )
  {
    v7 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v7 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext(v7);
      if ( *((_DWORD *)v8 + 499) != inited )
        CallStackContext::TraceFailure(v8, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8447, inited);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v9 = 395;
    goto LABEL_12;
  }
  inited = CMFTMultiStreamTypeHandler::InitAvailableOutputTypeArray(this, 0x10u, v6);
  if ( inited < 0 )
  {
    v10 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v11 + 499) != inited )
        CallStackContext::TraceFailure(v11, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8448, inited);
    }
    if ( !g_wppLevels )
      goto LABEL_144;
    v9 = 396;
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v12 = *((_QWORD *)this + 1);
  if ( v12 )
    (*(void (__fastcall **)(__int64, struct IMFAttributes **))(*(_QWORD *)v12 + 64LL))(v12, &v52);
  v13 = v52;
  if ( !v52 || (v14 = IsS3DMultiView(**((struct IMFMediaType ***)this + 8), v52), v13 = v52, v15 = 1, !v14) )
    v15 = 0;
  v16 = MFGetAttributeUINT32(v13, MF_XVP_ENABLE_444_IN_ROLLING_420, 0);
  if ( *(_DWORD *)(*((_QWORD *)this + 47) + 1136LL) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
    inited = MFCreateMediaType(&ppMFType);
    if ( inited < 0 )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v17 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v17 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext(v17);
        if ( *((_DWORD *)v18 + 499) != inited )
          CallStackContext::TraceFailure(v18, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8460, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_144;
      v9 = 397;
      goto LABEL_12;
    }
    inited = CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(
               *((CxCodeVideoProcMFTDataHandler **)this + 47),
               ppMFType);
    if ( inited < 0 )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v19 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext(v19);
        if ( *((_DWORD *)v20 + 499) != inited )
          CallStackContext::TraceFailure(v20, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8463, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_144;
      v9 = 398;
      goto LABEL_12;
    }
    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->GetGUID)(
               ppMFType,
               &MF_MT_SUBTYPE,
               &Buf2);
    if ( inited < 0 )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v21 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v21);
        if ( *((_DWORD *)v22 + 499) != inited )
          CallStackContext::TraceFailure(v22, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8466, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_144;
      v9 = 399;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, inited);
      goto LABEL_144;
    }
  }
  for ( i = 0; i < 0x10; ++i )
  {
    v49 = 0;
    v24 = *((_QWORD *)this + 47);
    Buf1 = xmmword_1801547B0[i];
    if ( *(_DWORD *)(v24 + 1136) )
    {
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        Buf1 = xmmword_1801547B0[0];
      if ( !i )
        Buf1 = Buf2;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    inited = MFCreateMediaType(&v49);
    if ( inited < 0 )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v46 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v47 = CallStackTracing::GetThreadRelativeContext(v46);
        if ( *((_DWORD *)v47 + 499) != inited )
          CallStackContext::TraceFailure(v47, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8491, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_143;
      v31 = 400;
LABEL_142:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v31,
        &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
        this,
        inited);
      goto LABEL_143;
    }
    if ( ppMFType )
      ((void (__fastcall *)(IMFMediaType *, IMFMediaType *))ppMFType->lpVtbl->CopyAllItems)(ppMFType, v49);
    if ( v16 )
    {
      dwWidth = 0;
      pStride = 0;
      v25 = CMFTMultiStreamTypeHandler::PInputType(this, 0);
      inited = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v25->lpVtbl->CopyAllItems)(v25, v49);
      if ( inited < 0 )
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v36 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext(v36);
          if ( *((_DWORD *)v37 + 499) != inited )
            CallStackContext::TraceFailure(v37, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8505, inited);
        }
        if ( g_wppLevels )
        {
          v31 = 401;
          goto LABEL_142;
        }
        goto LABEL_143;
      }
      inited = MFGetAttribute2UINT32asUINT64(v49, &MF_MT_FRAME_SIZE, &dwWidth, v55);
      if ( inited < 0 )
      {
        v34 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v34 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext(v34);
          if ( *((_DWORD *)v35 + 499) != inited )
            CallStackContext::TraceFailure(v35, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8506, inited);
        }
        if ( g_wppLevels )
        {
          v31 = 402;
          goto LABEL_142;
        }
        goto LABEL_143;
      }
      inited = MFGetStrideForBitmapInfoHeader(Buf1, dwWidth, &pStride);
      if ( inited < 0 )
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v32 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext(v32);
          if ( *((_DWORD *)v33 + 499) != inited )
            CallStackContext::TraceFailure(v33, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8510, inited);
        }
        if ( g_wppLevels )
        {
          v31 = 404;
          goto LABEL_142;
        }
        goto LABEL_143;
      }
      inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))v49->lpVtbl->SetUINT32)(
                 v49,
                 &MF_MT_DEFAULT_STRIDE,
                 (unsigned int)pStride);
      if ( inited < 0 )
      {
        v29 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v29 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext(v29);
          if ( *((_DWORD *)v30 + 499) != inited )
            CallStackContext::TraceFailure(v30, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8512, inited);
        }
        if ( g_wppLevels )
        {
          v31 = 405;
          goto LABEL_142;
        }
        goto LABEL_143;
      }
    }
    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))v49->lpVtbl->SetGUID)(
               v49,
               &MF_MT_MAJOR_TYPE,
               &MFMediaType_Video);
    if ( inited < 0 )
    {
      v44 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v44 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(v44);
        if ( *((_DWORD *)v45 + 499) != inited )
          CallStackContext::TraceFailure(v45, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8515, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_143;
      v31 = 406;
      goto LABEL_142;
    }
    inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))v49->lpVtbl->SetGUID)(
               v49,
               &MF_MT_SUBTYPE,
               &Buf1);
    if ( inited < 0 )
    {
      v42 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v42 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext(v42);
        if ( *((_DWORD *)v43 + 499) != inited )
          CallStackContext::TraceFailure(v43, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8516, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_143;
      v31 = 407;
      goto LABEL_142;
    }
    if ( !v15 )
      goto LABEL_70;
    inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))v49->lpVtbl->SetUINT32)(
               v49,
               MF_MT_VIDEO_3D,
               1);
    if ( inited < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v40 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( *((_DWORD *)v41 + 499) != inited )
          CallStackContext::TraceFailure(v41, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8520, inited);
      }
      if ( g_wppLevels )
      {
        v31 = 408;
        goto LABEL_142;
      }
LABEL_143:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      goto LABEL_144;
    }
    inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))v49->lpVtbl->SetUINT32)(
               v49,
               MF_MT_VIDEO_3D_FORMAT,
               1);
    if ( inited < 0 )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v38 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(v38);
        if ( *((_DWORD *)v39 + 499) != inited )
          CallStackContext::TraceFailure(v39, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8521, inited);
      }
      if ( g_wppLevels )
      {
        v31 = 409;
        goto LABEL_142;
      }
      goto LABEL_143;
    }
LABEL_70:
    CMFTMultiStreamTypeHandler::SetAvailableOutputType(this, i, v49, v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  }
  inited = CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D(this, 0);
  if ( inited < 0 )
  {
    v27 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v27 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext(v27);
      if ( *((_DWORD *)v28 + 499) != inited )
        CallStackContext::TraceFailure(v28, "CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D", 8530, inited);
    }
    if ( g_wppLevels )
    {
      v9 = 410;
      goto LABEL_12;
    }
  }
LABEL_144:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180031034  push    rbp
0x180031036  push    rbx
0x180031037  push    rsi
0x180031038  push    rdi
0x180031039  push    r12
0x18003103b  push    r13
0x18003103d  push    r14
0x18003103f  push    r15
0x180031041  lea     rbp, [rsp-1Fh]
0x180031046  sub     rsp, 98h
0x18003104d  mov     rax, cs:__security_cookie
0x180031054  xor     rax, rsp
0x180031057  mov     [rbp+57h+var_50], rax
0x18003105b  mov     rsi, rcx
0x18003105e  lea     r14, aCxcodevideopro_21; "CxCodeVideoProcMFTTypeHandler::OnInputT"...
0x180031065  xor     r13d, r13d
0x180031068  lea     rcx, [rbp+57h+var_98]; this
0x18003106c  xorps   xmm0, xmm0
0x18003106f  mov     [rbp+57h+var_88], r13
0x180031073  mov     r15d, 20FFh
0x180031079  mov     [rbp+57h+ppMFType], r13
0x18003107d  mov     r8d, r15d; int
0x180031080  mov     rdx, r14; char *
0x180031083  movups  [rbp+57h+Buf2], xmm0
0x180031087  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003108c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180031093  cmp     [rcx+8], r13b
0x180031097  jz      short loc_1800310ED
0x180031099  cmp     [rsi+180h], r13
0x1800310a0  jz      short loc_1800310ED
0x1800310a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800310a7  mov     rcx, [rsi+180h]
0x1800310ae  mov     rdi, rax
0x1800310b1  mov     rdx, [rcx]
0x1800310b4  mov     rax, [rdx+128h]
0x1800310bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310c0  mov     rcx, [rsi+180h]
0x1800310c7  mov     ebx, eax
0x1800310c9  mov     rdx, [rcx]
0x1800310cc  mov     rax, [rdx+118h]
0x1800310d3  lea     rdx, [rbp+57h+Buf1]
0x1800310d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310dc  movups  xmm0, xmmword ptr [rax]
0x1800310df  mov     [rdi+7E0h], ebx
0x1800310e5  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800310ed  mov     rcx, rsi; this
0x1800310f0  call    ?CheckD3DVideoDevice@CxCodeVideoProcMFTTypeHandler@@QEAAJXZ; CxCodeVideoProcMFTTypeHandler::CheckD3DVideoDevice(void)
0x1800310f5  mov     ebx, eax
0x1800310f7  test    eax, eax
0x1800310f9  jns     short loc_180031171
0x1800310fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031102  test    rcx, rcx
0x180031105  jnz     short loc_180031113
0x180031107  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003110c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180031113  cmp     [rcx+8], r13b
0x180031117  jz      short loc_180031137
0x180031119  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003111e  cmp     [rax+7CCh], ebx
0x180031124  jz      short loc_180031137
0x180031126  mov     r9d, ebx; int
0x180031129  mov     r8d, r15d; int
0x18003112c  mov     rdx, r14; char *
0x18003112f  mov     rcx, rax; this
0x180031132  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031137  mov     edi, 1
0x18003113c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180031143  jb      loc_18003196A
0x180031149  mov     edx, 18Bh
0x18003114e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031155  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18003115c  mov     r9, rsi
0x18003115f  mov     [rsp+0D0h+var_B0], ebx
0x180031163  mov     rcx, [rcx+10h]
0x180031167  call    WPP_SF_qD
0x18003116c  jmp     loc_18003196A
0x180031171  mov     edx, 10h; unsigned int
0x180031176  mov     rcx, rsi; this
0x180031179  call    ?InitAvailableOutputTypeArray@CMFTMultiStreamTypeHandler@@IEAAJKK@Z; CMFTMultiStreamTypeHandler::InitAvailableOutputTypeArray(ulong,ulong)
0x18003117e  mov     ebx, eax
0x180031180  test    eax, eax
0x180031182  jns     short loc_1800311DF
0x180031184  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003118b  test    rcx, rcx
0x18003118e  jnz     short loc_18003119C
0x180031190  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180031195  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003119c  cmp     [rcx+8], r13b
0x1800311a0  jz      short loc_1800311C3
0x1800311a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800311a7  cmp     [rax+7CCh], ebx
0x1800311ad  jz      short loc_1800311C3
0x1800311af  mov     r9d, ebx; int
0x1800311b2  mov     r8d, 2100h; int
0x1800311b8  mov     rdx, r14; char *
0x1800311bb  mov     rcx, rax; this
0x1800311be  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800311c3  mov     edi, 1
0x1800311c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800311cf  jb      loc_18003196A
0x1800311d5  mov     edx, 18Ch
0x1800311da  jmp     loc_18003114E
0x1800311df  lea     rcx, [rbp+57h+var_88]
0x1800311e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800311e8  mov     rcx, [rsi+8]
0x1800311ec  test    rcx, rcx
0x1800311ef  jz      short loc_180031201
0x1800311f1  mov     rax, [rcx]
0x1800311f4  lea     rdx, [rbp+57h+var_88]
0x1800311f8  mov     rax, [rax+40h]
0x1800311fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031201  mov     rcx, [rbp+57h+var_88]
0x180031205  mov     edi, 1
0x18003120a  test    rcx, rcx
0x18003120d  jz      short loc_180031229
0x18003120f  mov     rax, [rsi+40h]
0x180031213  mov     rdx, rcx; struct IMFAttributes *
0x180031216  mov     rcx, [rax]; struct IMFMediaType *
0x180031219  call    ?IsS3DMultiView@@YAHPEAUIMFMediaType@@PEAUIMFAttributes@@@Z; IsS3DMultiView(IMFMediaType *,IMFAttributes *)
0x18003121e  mov     rcx, [rbp+57h+var_88]
0x180031222  mov     r15d, edi
0x180031225  test    eax, eax
0x180031227  jnz     short loc_18003122C
0x180031229  mov     r15d, r13d
0x18003122c  xor     r8d, r8d
0x18003122f  lea     rdx, MF_XVP_ENABLE_444_IN_ROLLING_420
0x180031236  call    MFGetAttributeUINT32
0x18003123b  mov     rcx, [rsi+178h]
0x180031242  mov     r12d, eax
0x180031245  cmp     [rcx+470h], r13d
0x18003124c  jz      loc_1800313A4
0x180031252  lea     rcx, [rbp+57h+ppMFType]
0x180031256  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003125b  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x18003125f  call    cs:__imp_MFCreateMediaType
0x180031265  mov     ebx, eax
0x180031267  test    eax, eax
0x180031269  jns     short loc_1800312C1
0x18003126b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031272  test    rcx, rcx
0x180031275  jnz     short loc_180031283
0x180031277  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003127c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180031283  cmp     [rcx+8], r13b
0x180031287  jz      short loc_1800312AA
0x180031289  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003128e  cmp     [rax+7CCh], ebx
0x180031294  jz      short loc_1800312AA
0x180031296  mov     r9d, ebx; int
0x180031299  mov     r8d, 210Ch; int
0x18003129f  mov     rdx, r14; char *
0x1800312a2  mov     rcx, rax; this
0x1800312a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800312aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x1800312b1  jb      loc_18003196A
0x1800312b7  mov     edx, 18Dh
0x1800312bc  jmp     loc_18003114E
0x1800312c1  mov     rdx, [rbp+57h+ppMFType]; struct IMFMediaType *
0x1800312c5  mov     rcx, [rsi+178h]; this
0x1800312cc  call    ?GetNaturalOutputType@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUIMFMediaType@@@Z; CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(IMFMediaType *)
0x1800312d1  mov     ebx, eax
0x1800312d3  test    eax, eax
0x1800312d5  jns     short loc_18003132D
0x1800312d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800312de  test    rcx, rcx
0x1800312e1  jnz     short loc_1800312EF
0x1800312e3  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800312e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800312ef  cmp     [rcx+8], r13b
0x1800312f3  jz      short loc_180031316
0x1800312f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800312fa  cmp     [rax+7CCh], ebx
0x180031300  jz      short loc_180031316
0x180031302  mov     r9d, ebx; int
0x180031305  mov     r8d, 210Fh; int
0x18003130b  mov     rdx, r14; char *
0x18003130e  mov     rcx, rax; this
0x180031311  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031316  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x18003131d  jb      loc_18003196A
0x180031323  mov     edx, 18Eh
0x180031328  jmp     loc_18003114E
0x18003132d  mov     rcx, [rbp+57h+ppMFType]
0x180031331  lea     r8, [rbp+57h+Buf2]
0x180031335  lea     rdx, MF_MT_SUBTYPE
0x18003133c  mov     rax, [rcx]
0x18003133f  mov     rax, [rax+50h]
0x180031343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031348  mov     ebx, eax
0x18003134a  test    eax, eax
0x18003134c  jns     short loc_1800313A4
0x18003134e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031355  test    rcx, rcx
0x180031358  jnz     short loc_180031366
0x18003135a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003135f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180031366  cmp     [rcx+8], r13b
0x18003136a  jz      short loc_18003138D
0x18003136c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031371  cmp     [rax+7CCh], ebx
0x180031377  jz      short loc_18003138D
0x180031379  mov     r9d, ebx; int
0x18003137c  mov     r8d, 2112h; int
0x180031382  mov     rdx, r14; char *
0x180031385  mov     rcx, rax; this
0x180031388  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003138d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180031394  jb      loc_18003196A
0x18003139a  mov     edx, 18Fh
0x18003139f  jmp     loc_18003114E
0x1800313a4  mov     r14d, r13d
0x1800313a7  mov     eax, r14d
0x1800313aa  lea     rcx, xmmword_1801547B0
0x1800313b1  add     rax, rax
0x1800313b4  mov     [rbp+57h+var_A0], r13
0x1800313b8  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800313bc  mov     rax, [rsi+178h]
0x1800313c3  movdqu  [rbp+57h+Buf1], xmm0
0x1800313c8  cmp     [rax+470h], r13d
0x1800313cf  jz      short loc_180031415
0x1800313d1  mov     r8d, 10h; Size
0x1800313d7  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800313db  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800313df  call    memcmp_0
0x1800313e4  test    eax, eax
0x1800313e6  jnz     short loc_180031407
0x1800313e8  mov     eax, dword ptr cs:xmmword_1801547B0
0x1800313ee  movsd   xmm0, qword ptr cs:xmmword_1801547B0+4
0x1800313f6  mov     dword ptr [rbp+57h+Buf1], eax
0x1800313f9  mov     eax, dword ptr cs:xmmword_1801547B0+0Ch
0x1800313ff  mov     dword ptr [rbp+57h+Buf1+0Ch], eax
0x180031402  movsd   qword ptr [rbp+57h+Buf1+4], xmm0
0x180031407  test    r14d, r14d
0x18003140a  jnz     short loc_180031415
0x18003140c  movaps  xmm0, [rbp+57h+Buf2]
0x180031410  movdqa  [rbp+57h+Buf1], xmm0
0x180031415  lea     rcx, [rbp+57h+var_A0]
0x180031419  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003141e  lea     rcx, [rbp+57h+var_A0]; ppMFType
0x180031422  call    cs:__imp_MFCreateMediaType
0x180031428  mov     ebx, eax
0x18003142a  test    eax, eax
0x18003142c  js      loc_1800318F2
0x180031432  mov     rcx, [rbp+57h+ppMFType]
0x180031436  test    rcx, rcx
0x180031439  jz      short loc_18003144E
0x18003143b  mov     rax, [rcx]
0x18003143e  mov     rdx, [rbp+57h+var_A0]
0x180031442  mov     rax, [rax+100h]
0x180031449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003144e  test    r12d, r12d
0x180031451  jz      loc_1800314F0
0x180031457  xor     edx, edx; unsigned int
0x180031459  mov     [rbp+57h+dwWidth], r13d
0x18003145d  mov     rcx, rsi; this
0x180031460  mov     [rbp+57h+pStride], r13d
0x180031464  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x180031469  mov     rdx, [rbp+57h+var_A0]
0x18003146d  mov     r10, rax
0x180031470  mov     rcx, [rax]
0x180031473  mov     rax, [rcx+100h]
0x18003147a  mov     rcx, r10
0x18003147d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031482  mov     ebx, eax
0x180031484  test    eax, eax
0x180031486  js      loc_180031737
0x18003148c  mov     rcx, [rbp+57h+var_A0]
0x180031490  lea     r9, [rbp+57h+var_78]
0x180031494  lea     r8, [rbp+57h+dwWidth]
0x180031498  lea     rdx, MF_MT_FRAME_SIZE
0x18003149f  call    MFGetAttribute2UINT32asUINT64
0x1800314a4  mov     ebx, eax
0x1800314a6  test    eax, eax
0x1800314a8  js      loc_1800316DD
0x1800314ae  mov     edx, [rbp+57h+dwWidth]; dwWidth
0x1800314b1  lea     r8, [rbp+57h+pStride]; pStride
0x1800314b5  mov     ecx, dword ptr [rbp+57h+Buf1]; format
0x1800314b8  call    cs:__imp_MFGetStrideForBitmapInfoHeader
0x1800314be  mov     ebx, eax
0x1800314c0  test    eax, eax
0x1800314c2  js      loc_180031683
0x1800314c8  mov     rcx, [rbp+57h+var_A0]
0x1800314cc  lea     rdx, MF_MT_DEFAULT_STRIDE
0x1800314d3  mov     r8d, [rbp+57h+pStride]
0x1800314d7  mov     rax, [rcx]
0x1800314da  mov     rax, [rax+0A8h]
0x1800314e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314e6  mov     ebx, eax
0x1800314e8  test    eax, eax
0x1800314ea  js      loc_180031629
0x1800314f0  mov     rcx, [rbp+57h+var_A0]
0x1800314f4  lea     r8, MFMediaType_Video
0x1800314fb  lea     rdx, MF_MT_MAJOR_TYPE
0x180031502  mov     rax, [rcx]
0x180031505  mov     rax, [rax+0C0h]
0x18003150c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031511  mov     ebx, eax
0x180031513  test    eax, eax
0x180031515  js      loc_18003189F
0x18003151b  mov     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
