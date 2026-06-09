# CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D(uint)

- ea: `0x180032994`
- end: `0x180032e5c`
- name: `?UpdateAvailableOutputTypesD3D@CxCodeVideoProcMFTTypeHandler@@QEAAJI@Z`
- size: `1224`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800309c0`
- `0x180031034`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180032994`
- `0x18003639c`
- `0x1800364d0`
- `0x180036fe0`
- `0x180054140`
- `0x180071720`
- `0x1800cfec0`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180032a50`
- `MFPlat!MFCreateMediaType` at `0x180032a50`

## string_xrefs

- `0x1800329bc`: `CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D(
        CxCodeVideoProcMFTTypeHandler *this,
        unsigned int a2)
{
  unsigned __int64 v2; // r14
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  HRESULT v7; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  struct IMFMediaType *v11; // rax
  struct IMFMediaType *v12; // rdx
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  _QWORD *v17; // rdx
  struct IMFMediaType *v18; // rax
  __int64 v19; // r11
  int v20; // eax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rcx
  struct CallStackContext *v26; // rax
  _BYTE v28[8]; // [rsp+30h] [rbp-30h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-20h] BYREF

  v2 = a2;
  ppMFType = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v28,
    "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D",
    1285);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 48) + 280LL))(
                      *((_QWORD *)this + 48),
                      &Buf1);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  v7 = MFCreateMediaType(&ppMFType);
  if ( v7 < 0 )
  {
    v8 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v8 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)v9 + 499) != v7 )
        CallStackContext::TraceFailure(v9, "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D", 1285, v7);
    }
    if ( !g_wppLevels )
      goto LABEL_64;
    v10 = 47;
    goto LABEL_63;
  }
  v11 = CMFTMultiStreamTypeHandler::PInputType(this, 0);
  v7 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))v11->lpVtbl->CopyAllItems)(v11, ppMFType);
  if ( v7 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v13 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)v14 + 499) != v7 )
        CallStackContext::TraceFailure(v14, "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D", 1286, v7);
    }
    if ( !g_wppLevels )
      goto LABEL_64;
    v10 = 48;
    goto LABEL_63;
  }
  MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ResetVideoColorSpace(
    (MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper *)ppMFType,
    v12);
  v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
         ppMFType,
         &MF_MT_INTERLACE_MODE,
         2);
  if ( v7 < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v15 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v15);
      if ( *((_DWORD *)v16 + 499) != v7 )
        CallStackContext::TraceFailure(v16, "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D", 1289, v7);
    }
    if ( !g_wppLevels )
      goto LABEL_64;
    v10 = 49;
LABEL_63:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v7);
    goto LABEL_64;
  }
  v17 = (_QWORD *)*((_QWORD *)this + 5);
  if ( v2 >= (__int64)(v17[1] - *v17) >> 4 )
    goto LABEL_64;
  while ( 1 )
  {
    Buf1 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int128 *))(**(_QWORD **)(*v17 + 16LL * (unsigned int)v2)
                                                                     + 80LL))(
           *(_QWORD *)(*v17 + 16LL * (unsigned int)v2),
           &MF_MT_SUBTYPE,
           &Buf1);
    if ( v7 < 0 )
      break;
    if ( *(_DWORD *)(*((_QWORD *)this + 47) + 1000LL) && !memcmp_0(&Buf1, &MFVideoFormat_YUY2, 0x10u) )
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 51, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &Buf1);
      if ( v7 < 0 )
      {
        v23 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v23 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v24 = CallStackTracing::GetThreadRelativeContext(v23);
          if ( *((_DWORD *)v24 + 499) != v7 )
            CallStackContext::TraceFailure(
              v24,
              "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D",
              1307,
              v7);
        }
        if ( g_wppLevels )
        {
          v10 = 52;
          goto LABEL_63;
        }
        goto LABEL_64;
      }
      if ( !*((_QWORD *)this + 46)
        || (v18 = CMFTMultiStreamTypeHandler::PInputType(this, 0),
            v20 = (*(__int64 (__fastcall **)(__int64, struct IMFMediaType *, IMFMediaType *, _QWORD, int))(*(_QWORD *)v19 + 8LL))(
                    v19,
                    v18,
                    ppMFType,
                    0,
                    1),
            v20 >= 0) )
      {
        *(_DWORD *)(**((_QWORD **)this + 5) + 16LL * (unsigned int)v2 + 8) = 1;
        goto LABEL_47;
      }
      if ( v20 == -2005270523 )
      {
        v21 = CallStackTracing::s_wpInstance;
        v7 = -2005270523;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v21 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v22 = CallStackTracing::GetThreadRelativeContext(v21);
          if ( *((_DWORD *)v22 + 499) != -2005270523 )
            CallStackContext::TraceFailure(
              v22,
              "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D",
              1326,
              -2005270523);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
            this,
            -2005270523);
        goto LABEL_64;
      }
    }
    *(_DWORD *)(**((_QWORD **)this + 5) + 16LL * (unsigned int)v2 + 8) = 0;
LABEL_47:
    v17 = (_QWORD *)*((_QWORD *)this + 5);
    LODWORD(v2) = v2 + 1;
    if ( (unsigned int)v2 >= (unsigned __int64)((__int64)(v17[1] - *v17) >> 4) )
      goto LABEL_64;
  }
  v25 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v25 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v25 + 8) )
  {
    v26 = CallStackTracing::GetThreadRelativeContext(v25);
    if ( *((_DWORD *)v26 + 499) != v7 )
      CallStackContext::TraceFailure(v26, "CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D", 1300, v7);
  }
  if ( g_wppLevels )
  {
    v10 = 50;
    goto LABEL_63;
  }
LABEL_64:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032994  mov     [rsp-38h+arg_10], rbx
0x180032999  push    rbp
0x18003299a  push    rsi
0x18003299b  push    rdi
0x18003299c  push    r12
0x18003299e  push    r13
0x1800329a0  push    r14
0x1800329a2  push    r15
0x1800329a4  mov     rbp, rsp
0x1800329a7  sub     rsp, 60h
0x1800329ab  mov     rax, cs:__security_cookie
0x1800329b2  xor     rax, rsp
0x1800329b5  mov     [rbp+var_10], rax
0x1800329b9  mov     r14d, edx
0x1800329bc  lea     r12, aCxcodevideopro_103; "CxCodeVideoProcMFTTypeHandler::UpdateAv"...
0x1800329c3  mov     rsi, rcx
0x1800329c6  mov     r13d, 505h
0x1800329cc  xor     r15d, r15d
0x1800329cf  lea     rcx, [rbp+var_30]; this
0x1800329d3  mov     r8d, r13d; int
0x1800329d6  mov     [rbp+ppMFType], r15
0x1800329da  mov     rdx, r12; char *
0x1800329dd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800329e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800329e9  cmp     [rcx+8], r15b
0x1800329ed  jz      short loc_180032A43
0x1800329ef  cmp     [rsi+180h], r15
0x1800329f6  jz      short loc_180032A43
0x1800329f8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800329fd  mov     rcx, [rsi+180h]
0x180032a04  mov     rdi, rax
0x180032a07  mov     rdx, [rcx]
0x180032a0a  mov     rax, [rdx+128h]
0x180032a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a16  mov     rcx, [rsi+180h]
0x180032a1d  mov     ebx, eax
0x180032a1f  mov     rdx, [rcx]
0x180032a22  mov     rax, [rdx+118h]
0x180032a29  lea     rdx, [rbp+Buf1]
0x180032a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a32  movups  xmm0, xmmword ptr [rax]
0x180032a35  mov     [rdi+7E0h], ebx
0x180032a3b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180032a43  lea     rcx, [rbp+ppMFType]
0x180032a47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032a4c  lea     rcx, [rbp+ppMFType]; ppMFType
0x180032a50  call    cs:__imp_MFCreateMediaType
0x180032a56  mov     ebx, eax
0x180032a58  test    eax, eax
0x180032a5a  jns     short loc_180032AAF
0x180032a5c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032a63  test    rcx, rcx
0x180032a66  jnz     short loc_180032A74
0x180032a68  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032a6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032a74  cmp     [rcx+8], r15b
0x180032a78  jz      short loc_180032A98
0x180032a7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032a7f  cmp     [rax+7CCh], ebx
0x180032a85  jz      short loc_180032A98
0x180032a87  mov     r9d, ebx; int
0x180032a8a  mov     r8d, r13d; int
0x180032a8d  mov     rdx, r12; char *
0x180032a90  mov     rcx, rax; this
0x180032a93  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032a98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032a9f  jb      loc_180032E24
0x180032aa5  mov     edx, 2Fh ; '/'
0x180032aaa  jmp     loc_180032E06
0x180032aaf  xor     edx, edx; unsigned int
0x180032ab1  mov     rcx, rsi; this
0x180032ab4  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x180032ab9  mov     rdx, [rbp+ppMFType]
0x180032abd  mov     r10, rax
0x180032ac0  mov     rcx, [rax]
0x180032ac3  mov     rax, [rcx+100h]
0x180032aca  mov     rcx, r10
0x180032acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ad2  mov     ebx, eax
0x180032ad4  test    eax, eax
0x180032ad6  jns     short loc_180032B2E
0x180032ad8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032adf  test    rcx, rcx
0x180032ae2  jnz     short loc_180032AF0
0x180032ae4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032ae9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032af0  cmp     [rcx+8], r15b
0x180032af4  jz      short loc_180032B17
0x180032af6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032afb  cmp     [rax+7CCh], ebx
0x180032b01  jz      short loc_180032B17
0x180032b03  mov     r9d, ebx; int
0x180032b06  mov     r8d, 506h; int
0x180032b0c  mov     rdx, r12; char *
0x180032b0f  mov     rcx, rax; this
0x180032b12  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032b17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032b1e  jb      loc_180032E24
0x180032b24  mov     edx, 30h ; '0'
0x180032b29  jmp     loc_180032E06
0x180032b2e  mov     rcx, [rbp+ppMFType]; this
0x180032b32  call    ?ResetVideoColorSpace@MFMEDIATYPEUtilsHelper@MFMEDIATYPEUtils@@YAXPEAUIMFMediaType@@@Z; MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ResetVideoColorSpace(IMFMediaType *)
0x180032b37  mov     rcx, [rbp+ppMFType]
0x180032b3b  lea     rdx, MF_MT_INTERLACE_MODE
0x180032b42  mov     r8d, 2
0x180032b48  mov     rax, [rcx]
0x180032b4b  mov     rax, [rax+0A8h]
0x180032b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032b57  mov     ebx, eax
0x180032b59  test    eax, eax
0x180032b5b  jns     short loc_180032BB3
0x180032b5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032b64  test    rcx, rcx
0x180032b67  jnz     short loc_180032B75
0x180032b69  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032b6e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032b75  cmp     [rcx+8], r15b
0x180032b79  jz      short loc_180032B9C
0x180032b7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032b80  cmp     [rax+7CCh], ebx
0x180032b86  jz      short loc_180032B9C
0x180032b88  mov     r9d, ebx; int
0x180032b8b  mov     r8d, 509h; int
0x180032b91  mov     rdx, r12; char *
0x180032b94  mov     rcx, rax; this
0x180032b97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032b9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032ba3  jb      loc_180032E24
0x180032ba9  mov     edx, 31h ; '1'
0x180032bae  jmp     loc_180032E06
0x180032bb3  mov     rdx, [rsi+28h]
0x180032bb7  mov     rcx, [rdx+8]
0x180032bbb  sub     rcx, [rdx]
0x180032bbe  sar     rcx, 4
0x180032bc2  cmp     r14, rcx
0x180032bc5  jnb     loc_180032E24
0x180032bcb  mov     r13d, 887A0005h
0x180032bd1  xorps   xmm0, xmm0
0x180032bd4  mov     edi, r14d
0x180032bd7  movups  [rbp+Buf1], xmm0
0x180032bdb  mov     rax, [rdx]
0x180032bde  lea     r8, [rbp+Buf1]
0x180032be2  add     rdi, rdi
0x180032be5  lea     rdx, MF_MT_SUBTYPE
0x180032bec  mov     rcx, [rax+rdi*8]
0x180032bf0  mov     rax, [rcx]
0x180032bf3  mov     rax, [rax+50h]
0x180032bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bfc  mov     ebx, eax
0x180032bfe  test    eax, eax
0x180032c00  js      loc_180032DB9
0x180032c06  mov     rax, [rsi+178h]
0x180032c0d  cmp     [rax+3E8h], r15d
0x180032c14  jz      short loc_180032C6A
0x180032c16  mov     r8d, 10h; Size
0x180032c1c  lea     rdx, MFVideoFormat_YUY2; Buf2
0x180032c23  lea     rcx, [rbp+Buf1]; Buf1
0x180032c27  call    memcmp_0
0x180032c2c  test    eax, eax
0x180032c2e  jnz     short loc_180032C6A
0x180032c30  cmp     cs:byte_180153DE0, 10h
0x180032c37  jb      short loc_180032C59
0x180032c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c40  lea     edx, [rax+33h]
0x180032c43  mov     r9, rsi
0x180032c46  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180032c4d  mov     rcx, [rcx+150h]
0x180032c54  call    WPP_SF_q
0x180032c59  mov     rax, [rsi+28h]
0x180032c5d  mov     rcx, [rax]
0x180032c60  mov     [rcx+rdi*8+8], r15d
0x180032c65  jmp     loc_180032D47
0x180032c6a  mov     rcx, [rbp+ppMFType]
0x180032c6e  lea     r8, [rbp+Buf1]
0x180032c72  lea     rdx, MF_MT_SUBTYPE
0x180032c79  mov     rax, [rcx]
0x180032c7c  mov     rax, [rax+0C0h]
0x180032c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c88  mov     ebx, eax
0x180032c8a  test    eax, eax
0x180032c8c  js      loc_180032D6A
0x180032c92  mov     r11, [rsi+170h]
0x180032c99  test    r11, r11
0x180032c9c  jz      loc_180032D38
0x180032ca2  xor     edx, edx; unsigned int
0x180032ca4  mov     rcx, rsi; this
0x180032ca7  call    ?PInputType@CMFTMultiStreamTypeHandler@@QEAAPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::PInputType(ulong)
0x180032cac  mov     rdx, [r11]
0x180032caf  xor     r9d, r9d
0x180032cb2  mov     r8, [rbp+ppMFType]
0x180032cb6  mov     rcx, r11
0x180032cb9  mov     [rsp+60h+var_40], 1
0x180032cc1  mov     r10, [rdx+8]
0x180032cc5  mov     rdx, rax
0x180032cc8  mov     rax, r10
0x180032ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cd0  test    eax, eax
0x180032cd2  jns     short loc_180032D38
0x180032cd4  cmp     eax, r13d
0x180032cd7  jnz     short loc_180032C59
0x180032cd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032ce0  mov     ebx, r13d
0x180032ce3  test    rcx, rcx
0x180032ce6  jnz     short loc_180032CF4
0x180032ce8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032ced  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032cf4  cmp     [rcx+8], r15b
0x180032cf8  jz      short loc_180032D1C
0x180032cfa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032cff  cmp     [rax+7CCh], r13d
0x180032d06  jz      short loc_180032D1C
0x180032d08  mov     r9d, r13d; int
0x180032d0b  mov     r8d, 52Eh; int
0x180032d11  mov     rdx, r12; char *
0x180032d14  mov     rcx, rax; this
0x180032d17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032d1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032d23  jb      loc_180032E24
0x180032d29  mov     edx, 35h ; '5'
0x180032d2e  mov     [rsp+60h+var_40], r13d
0x180032d33  jmp     loc_180032E0A
0x180032d38  mov     rax, [rsi+28h]
0x180032d3c  mov     rcx, [rax]
0x180032d3f  mov     dword ptr [rcx+rdi*8+8], 1
0x180032d47  mov     rdx, [rsi+28h]
0x180032d4b  inc     r14d
0x180032d4e  mov     eax, r14d
0x180032d51  mov     rcx, [rdx+8]
0x180032d55  sub     rcx, [rdx]
0x180032d58  sar     rcx, 4
0x180032d5c  cmp     rax, rcx
0x180032d5f  jb      loc_180032BD1
0x180032d65  jmp     loc_180032E24
0x180032d6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032d71  test    rcx, rcx
0x180032d74  jnz     short loc_180032D82
0x180032d76  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032d7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032d82  cmp     [rcx+8], r15b
0x180032d86  jz      short loc_180032DA9
0x180032d88  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032d8d  cmp     [rax+7CCh], ebx
0x180032d93  jz      short loc_180032DA9
0x180032d95  mov     r9d, ebx; int
0x180032d98  mov     r8d, 51Bh; int
0x180032d9e  mov     rdx, r12; char *
0x180032da1  mov     rcx, rax; this
0x180032da4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032da9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032db0  jb      short loc_180032E24
0x180032db2  mov     edx, 34h ; '4'
0x180032db7  jmp     short loc_180032E06
0x180032db9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032dc0  test    rcx, rcx
0x180032dc3  jnz     short loc_180032DD1
0x180032dc5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180032dca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180032dd1  cmp     [rcx+8], r15b
0x180032dd5  jz      short loc_180032DF8
0x180032dd7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032ddc  cmp     [rax+7CCh], ebx
0x180032de2  jz      short loc_180032DF8
0x180032de4  mov     r9d, ebx; int
0x180032de7  mov     r8d, 514h; int
0x180032ded  mov     rdx, r12; char *
0x180032df0  mov     rcx, rax; this
0x180032df3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032df8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032dff  jb      short loc_180032E24
0x180032e01  mov     edx, 32h ; '2'
0x180032e06  mov     [rsp+60h+var_40], ebx
0x180032e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e11  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180032e18  mov     r9, rsi
0x180032e1b  mov     rcx, [rcx+10h]
0x180032e1f  call    WPP_SF_qD
0x180032e24  lea     rcx, [rbp+var_30]; this
0x180032e28  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180032e2d  lea     rcx, [rbp+ppMFType]
0x180032e31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032e36  mov     eax, ebx
0x180032e38  mov     rcx, [rbp+var_10]
0x180032e3c  xor     rcx, rsp; StackCookie
0x180032e3f  call    __security_check_cookie
0x180032e44  mov     rbx, [rsp+60h+arg_10]
0x180032e4c  add     rsp, 60h
0x180032e50  pop     r15
0x180032e52  pop     r14
0x180032e54  pop     r13
0x180032e56  pop     r12
0x180032e58  pop     rdi
0x180032e59  pop     rsi
0x180032e5a  pop     rbp
0x180032e5b  retn
```
