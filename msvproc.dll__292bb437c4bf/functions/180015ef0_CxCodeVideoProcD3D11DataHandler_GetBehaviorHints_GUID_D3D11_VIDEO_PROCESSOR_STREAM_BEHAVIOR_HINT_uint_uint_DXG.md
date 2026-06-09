# CxCodeVideoProcD3D11DataHandler::GetBehaviorHints(_GUID,D3D11_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT *,uint,uint,DXGI_FORMAT,uint *)

- ea: `0x180015ef0`
- end: `0x180016494`
- name: `?GetBehaviorHints@CxCodeVideoProcD3D11DataHandler@@UEAAJU_GUID@@PEAUD3D11_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT@@IIW4DXGI_FORMAT@@PEAI@Z`
- size: `1444`
- prototype: `__int64 __usercall@<rax>(CxCodeVideoProcD3D11DataHandler *__hidden this@<rcx>, struct _GUID *__struct_ptr@<rdx>, struct D3D11_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT *@<r8>, unsigned int@<r9d>, unsigned int, enum DXGI_FORMAT, unsigned int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180015ef0`
- `0x18001b3e8`
- `0x18001d3d8`
- `0x18003639c`
- `0x1800364d0`
- `0x18003eb08`
- `0x18006fa30`
- `0x180073488`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001615c`
- `MFPlat!MFCreateMediaType` at `0x18001615c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015fa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016234`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800163a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015fa5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016092`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180016234`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800163a1`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcD3D11DataHandler::GetBehaviorHints(
        CxCodeVideoProcD3D11DataHandler *this,
        struct _GUID *a2,
        struct D3D11_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT *a3,
        unsigned int a4,
        unsigned int a5,
        enum DXGI_FORMAT a6,
        unsigned int *a7)
{
  _QWORD *v11; // rsi
  __int64 *v12; // rcx
  HRESULT v13; // ebx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFMediaType *v23; // rcx
  enum DXGI_COLOR_SPACE_TYPE *v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  _BYTE v34[8]; // [rsp+50h] [rbp-28h] BYREF
  IMFMediaType *ppMFType; // [rsp+58h] [rbp-20h] BYREF
  struct IMFMediaType v36; // [rsp+60h] [rbp-18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v34,
    "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints",
    2438);
  v11 = (_QWORD *)((char *)this + 2352);
  if ( *((_QWORD *)this + 290) && *v11 || (int)CxCodeVideoProcD3D11DataHandler::EnsureD3D11VideoProcessor(this) >= 0 )
  {
    v17 = *((_QWORD *)this + 291);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 592LL))(
        v17,
        *v11,
        0,
        *(unsigned int *)(*((_QWORD *)this + 2) + 312LL));
      if ( a2->Data1 != *(_DWORD *)(*((_QWORD *)this + 2) + 368LL) )
      {
        ppMFType = 0;
        LODWORD(v36.lpVtbl) = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
        v13 = MFCreateMediaType(&ppMFType);
        if ( v13 < 0 )
        {
          v21 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v21 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v21);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints",
                2472,
                v13);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              136,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              v13);
          v23 = ppMFType;
          if ( ppMFType )
          {
            ppMFType = 0;
            ((void (__fastcall *)(IMFMediaType *))v23->lpVtbl->Release)(v23);
          }
          goto LABEL_71;
        }
        v13 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, struct _GUID *))ppMFType->lpVtbl->SetGUID)(
                ppMFType,
                &MF_MT_SUBTYPE,
                a2);
        if ( v13 < 0 )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != v13 )
              CallStackContext::TraceFailure(v27, "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints", 2473, v13);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              137,
              &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
              this,
              v13);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
          goto LABEL_71;
        }
        MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ConvertTypeToDXGIColorSpace(
          (MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper *)ppMFType,
          &v36,
          v24);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 291) + 560LL))(
          *((_QWORD *)this + 291),
          *v11,
          LODWORD(v36.lpVtbl));
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppMFType);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 290) + 104LL))(
        *((_QWORD *)this + 290),
        *v11,
        0,
        0);
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 290) + 248LL))(
        *((_QWORD *)this + 290),
        *v11,
        0,
        0,
        0);
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, enum DXGI_FORMAT, int, struct D3D11_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT *, unsigned int *))(**((_QWORD **)this + 291) + 624LL))(
              *((_QWORD *)this + 291),
              *v11,
              a4,
              a5,
              a6,
              1,
              a3,
              a7);
      if ( v13 >= 0 )
      {
        v31 = *((_QWORD *)this + 2);
        if ( a2->Data1 != *(_DWORD *)(v31 + 368) )
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 291) + 560LL))(
            *((_QWORD *)this + 291),
            *v11,
            *(unsigned int *)(v31 + 556));
        v32 = *((_QWORD *)this + 2);
        if ( *(_DWORD *)(v32 + 992) && *(_DWORD *)(v32 + 748) )
          CxCodeVideoProcD3D11DataHandler::UpdateSphereMapTempTexture(this);
        else
          CxCodeVideoProcD3D11DataHandler::ConfigureD3D11VideoProcessorRects(this);
      }
      else
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v13 )
            CallStackContext::TraceFailure(v30, "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints", 2483, v13);
        }
        if ( g_wppLevels )
        {
          v16 = 138;
          goto LABEL_16;
        }
      }
    }
    else
    {
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 134, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this);
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      v13 = -1072875818;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)v20 + 499) != -1072875818 )
          CallStackContext::TraceFailure(v20, "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints", 2454, -1072875818);
      }
      if ( g_wppLevels )
      {
        v16 = 135;
        goto LABEL_16;
      }
    }
  }
  else
  {
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        132,
        &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids,
        this,
        *((_QWORD *)this + 290),
        *v11);
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v13 = -2147217408;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v15 + 499) != -2147217408 )
        CallStackContext::TraceFailure(v15, "CxCodeVideoProcD3D11DataHandler::GetBehaviorHints", 2447, -2147217408);
    }
    if ( g_wppLevels )
    {
      v16 = 133;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids, this, v13);
    }
  }
LABEL_71:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v34);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180015ef0  push    rbp
0x180015ef2  push    rbx
0x180015ef3  push    rsi
0x180015ef4  push    rdi
0x180015ef5  push    r12
0x180015ef7  push    r13
0x180015ef9  push    r14
0x180015efb  push    r15
0x180015efd  mov     rbp, rsp
0x180015f00  sub     rsp, 78h
0x180015f04  mov     r13, [rbp+arg_30]
0x180015f08  mov     r15, r8
0x180015f0b  mov     r14, rdx
0x180015f0e  mov     rdi, rcx
0x180015f11  mov     r8d, 986h; int
0x180015f17  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x180015f1e  lea     rcx, [rbp+var_28]; this
0x180015f22  mov     r12d, r9d
0x180015f25  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015f2a  xor     ebx, ebx
0x180015f2c  lea     rsi, [rdi+930h]
0x180015f33  cmp     [rdi+910h], rbx
0x180015f3a  jz      short loc_180015F45
0x180015f3c  cmp     [rsi], rbx
0x180015f3f  jnz     loc_180016046
0x180015f45  mov     rcx, rdi; this
0x180015f48  call    ?EnsureD3D11VideoProcessor@CxCodeVideoProcD3D11DataHandler@@IEAAJXZ; CxCodeVideoProcD3D11DataHandler::EnsureD3D11VideoProcessor(void)
0x180015f4d  test    eax, eax
0x180015f4f  jns     loc_180016046
0x180015f55  cmp     cs:byte_180153DE0, 20h ; ' '
0x180015f5c  jb      short loc_180015F94
0x180015f5e  mov     rax, [rsi]
0x180015f61  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180015f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f6f  mov     edx, 84h
0x180015f74  mov     [rsp+78h+var_50], rax
0x180015f79  mov     r9, rdi
0x180015f7c  mov     rax, [rdi+910h]
0x180015f83  mov     [rsp+78h+var_58], rax
0x180015f88  mov     rcx, [rcx+150h]
0x180015f8f  call    WPP_SF_qqq
0x180015f94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015f9b  mov     ebx, 80041000h
0x180015fa0  test    rcx, rcx
0x180015fa3  jnz     short loc_180015FE6
0x180015fa5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015fab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015fb2  mov     rcx, rax
0x180015fb5  test    rax, rax
0x180015fb8  jz      short loc_180015FD8
0x180015fba  mov     rax, [rax]
0x180015fbd  mov     edx, 7F0h
0x180015fc2  mov     rax, [rax+8]
0x180015fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fcb  test    eax, eax
0x180015fcd  jz      short loc_180015FD8
0x180015fcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015fd6  jmp     short loc_180015FE6
0x180015fd8  lea     rcx, qword_180153440; this
0x180015fdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015fe6  cmp     byte ptr [rcx+8], 0
0x180015fea  jz      short loc_180016011
0x180015fec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180015ff1  cmp     [rax+7CCh], ebx
0x180015ff7  jz      short loc_180016011
0x180015ff9  mov     r9d, ebx; int
0x180015ffc  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x180016003  mov     r8d, 98Fh; int
0x180016009  mov     rcx, rax; this
0x18001600c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180016011  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016018  jb      loc_180016478
0x18001601e  mov     edx, 85h
0x180016023  mov     rcx, cs:WPP_GLOBAL_Control
0x18001602a  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x180016031  mov     r9, rdi
0x180016034  mov     dword ptr [rsp+78h+var_58], ebx
0x180016038  mov     rcx, [rcx+10h]
0x18001603c  call    WPP_SF_qD
0x180016041  jmp     loc_180016478
0x180016046  mov     rcx, [rdi+918h]
0x18001604d  test    rcx, rcx
0x180016050  jnz     loc_180016115
0x180016056  cmp     cs:byte_180153DE0, 20h ; ' '
0x18001605d  jb      short loc_180016081
0x18001605f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016066  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x18001606d  mov     edx, 86h
0x180016072  mov     r9, rdi
0x180016075  mov     rcx, [rcx+150h]
0x18001607c  call    WPP_SF_q
0x180016081  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016088  mov     ebx, 0C00D36D6h
0x18001608d  test    rcx, rcx
0x180016090  jnz     short loc_1800160D3
0x180016092  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180016098  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001609f  mov     rcx, rax
0x1800160a2  test    rax, rax
0x1800160a5  jz      short loc_1800160C5
0x1800160a7  mov     rax, [rax]
0x1800160aa  mov     edx, 7F0h
0x1800160af  mov     rax, [rax+8]
0x1800160b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160b8  test    eax, eax
0x1800160ba  jz      short loc_1800160C5
0x1800160bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800160c3  jmp     short loc_1800160D3
0x1800160c5  lea     rcx, qword_180153440; this
0x1800160cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800160d3  cmp     byte ptr [rcx+8], 0
0x1800160d7  jz      short loc_1800160FE
0x1800160d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800160de  cmp     [rax+7CCh], ebx
0x1800160e4  jz      short loc_1800160FE
0x1800160e6  mov     r9d, ebx; int
0x1800160e9  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x1800160f0  mov     r8d, 996h; int
0x1800160f6  mov     rcx, rax; this
0x1800160f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800160fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016105  jb      loc_180016478
0x18001610b  mov     edx, 87h
0x180016110  jmp     loc_180016023
0x180016115  mov     rax, [rcx]
0x180016118  xor     r8d, r8d
0x18001611b  mov     r9, [rdi+10h]
0x18001611f  mov     rdx, [rsi]
0x180016122  mov     rax, [rax+250h]
0x180016129  mov     r9d, [r9+138h]
0x180016130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016135  mov     rax, [rdi+10h]
0x180016139  mov     ecx, [rax+170h]
0x18001613f  cmp     [r14], ecx
0x180016142  jz      loc_18001630F
0x180016148  lea     rcx, [rbp+ppMFType]
0x18001614c  mov     [rbp+ppMFType], rbx
0x180016150  mov     dword ptr [rbp+var_18.lpVtbl], ebx
0x180016153  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016158  lea     rcx, [rbp+ppMFType]; ppMFType
0x18001615c  call    cs:__imp_MFCreateMediaType
0x180016162  mov     ebx, eax
0x180016164  test    eax, eax
0x180016166  jns     loc_180016201
0x18001616c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016173  test    rcx, rcx
0x180016176  jnz     short loc_180016184
0x180016178  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001617d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180016184  cmp     byte ptr [rcx+8], 0
0x180016188  jz      short loc_1800161AF
0x18001618a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001618f  cmp     [rax+7CCh], ebx
0x180016195  jz      short loc_1800161AF
0x180016197  mov     r9d, ebx; int
0x18001619a  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x1800161a1  mov     r8d, 9A8h; int
0x1800161a7  mov     rcx, rax; this
0x1800161aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800161af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800161b6  jb      short loc_1800161DB
0x1800161b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161bf  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x1800161c6  mov     edx, 88h
0x1800161cb  mov     dword ptr [rsp+78h+var_58], ebx
0x1800161cf  mov     r9, rdi
0x1800161d2  mov     rcx, [rcx+10h]
0x1800161d6  call    WPP_SF_qD
0x1800161db  mov     rcx, [rbp+ppMFType]
0x1800161df  test    rcx, rcx
0x1800161e2  jz      loc_180016478
0x1800161e8  mov     [rbp+ppMFType], 0
0x1800161f0  mov     rax, [rcx]
0x1800161f3  mov     rax, [rax+10h]
0x1800161f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161fc  jmp     loc_180016478
0x180016201  mov     rcx, [rbp+ppMFType]
0x180016205  lea     rdx, MF_MT_SUBTYPE
0x18001620c  mov     r8, r14
0x18001620f  mov     rax, [rcx]
0x180016212  mov     rax, [rax+0C0h]
0x180016219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001621e  mov     ebx, eax
0x180016220  test    eax, eax
0x180016222  jns     loc_1800162DA
0x180016228  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001622f  test    rcx, rcx
0x180016232  jnz     short loc_180016275
0x180016234  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001623a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180016241  mov     rcx, rax
0x180016244  test    rax, rax
0x180016247  jz      short loc_180016267
0x180016249  mov     rax, [rax]
0x18001624c  mov     edx, 7F0h
0x180016251  mov     rax, [rax+8]
0x180016255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001625a  test    eax, eax
0x18001625c  jz      short loc_180016267
0x18001625e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180016265  jmp     short loc_180016275
0x180016267  lea     rcx, qword_180153440; this
0x18001626e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180016275  cmp     byte ptr [rcx+8], 0
0x180016279  jz      short loc_1800162A0
0x18001627b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180016280  cmp     [rax+7CCh], ebx
0x180016286  jz      short loc_1800162A0
0x180016288  mov     r9d, ebx; int
0x18001628b  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x180016292  mov     r8d, 9A9h; int
0x180016298  mov     rcx, rax; this
0x18001629b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800162a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800162a7  jb      short loc_1800162CC
0x1800162a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162b0  lea     r8, WPP_da02b715f64a3578031ba0910fa6fd90_Traceguids
0x1800162b7  mov     edx, 89h
0x1800162bc  mov     dword ptr [rsp+78h+var_58], ebx
0x1800162c0  mov     r9, rdi
0x1800162c3  mov     rcx, [rcx+10h]
0x1800162c7  call    WPP_SF_qD
0x1800162cc  lea     rcx, [rbp+ppMFType]
0x1800162d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800162d5  jmp     loc_180016478
0x1800162da  mov     rcx, [rbp+ppMFType]; this
0x1800162de  lea     rdx, [rbp+var_18]; struct IMFMediaType *
0x1800162e2  call    ?ConvertTypeToDXGIColorSpace@MFMEDIATYPEUtilsHelper@MFMEDIATYPEUtils@@YAHPEAUIMFMediaType@@PEAW4DXGI_COLOR_SPACE_TYPE@@@Z; MFMEDIATYPEUtils::MFMEDIATYPEUtilsHelper::ConvertTypeToDXGIColorSpace(IMFMediaType *,DXGI_COLOR_SPACE_TYPE *)
0x1800162e7  mov     rcx, [rdi+918h]
0x1800162ee  mov     r8d, dword ptr [rbp+var_18.lpVtbl]
0x1800162f2  mov     rdx, [rsi]
0x1800162f5  mov     rax, [rcx]
0x1800162f8  mov     rax, [rax+230h]
0x1800162ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016304  lea     rcx, [rbp+ppMFType]
0x180016308  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001630d  xor     ebx, ebx
0x18001630f  mov     rcx, [rdi+910h]
0x180016316  xor     r9d, r9d
0x180016319  mov     rdx, [rsi]
0x18001631c  xor     r8d, r8d
0x18001631f  mov     rax, [rcx]
0x180016322  mov     rax, [rax+68h]
0x180016326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001632b  mov     rcx, [rdi+910h]
0x180016332  xor     r9d, r9d
0x180016335  mov     rdx, [rsi]
0x180016338  xor     r8d, r8d
0x18001633b  mov     [rsp+78h+var_58], rbx
0x180016340  mov     rax, [rcx]
0x180016343  mov     rax, [rax+0F8h]
0x18001634a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001634f  mov     rcx, [rdi+918h]
0x180016356  mov     r8d, r12d
0x180016359  mov     edx, [rbp+arg_28]
0x18001635c  mov     r9d, [rbp+arg_20]
0x180016360  mov     [rsp+78h+var_40], r13
0x180016365  mov     rax, [rcx]
0x180016368  mov     [rsp+78h+var_48], r15
0x18001636d  mov     dword ptr [rsp+78h+var_50], 1
0x180016375  mov     dword ptr [rsp+78h+var_58], edx
0x180016379  mov     rax, [rax+270h]
0x180016380  mov     rdx, [rsi]
0x180016383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016388  xor     r15d, r15d
0x18001638b  mov     ebx, eax
0x18001638d  test    eax, eax
0x18001638f  jns     loc_180016420
0x180016395  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001639c  test    rcx, rcx
0x18001639f  jnz     short loc_1800163E2
0x1800163a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800163a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800163ae  mov     rcx, rax
0x1800163b1  test    rax, rax
0x1800163b4  jz      short loc_1800163D4
0x1800163b6  mov     rax, [rax]
0x1800163b9  mov     edx, 7F0h
0x1800163be  mov     rax, [rax+8]
0x1800163c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c7  test    eax, eax
0x1800163c9  jz      short loc_1800163D4
0x1800163cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800163d2  jmp     short loc_1800163E2
0x1800163d4  lea     rcx, qword_180153440; this
0x1800163db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800163e2  cmp     [rcx+8], r15b
0x1800163e6  jz      short loc_18001640D
0x1800163e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800163ed  cmp     [rax+7CCh], ebx
0x1800163f3  jz      short loc_18001640D
0x1800163f5  mov     r9d, ebx; int
0x1800163f8  lea     rdx, aCxcodevideopro_88; "CxCodeVideoProcD3D11DataHandler::GetBeh"...
0x1800163ff  mov     r8d, 9B3h; int
0x180016405  mov     rcx, rax; this
0x180016408  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001640d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180016414  jb      short loc_180016478
0x180016416  mov     edx, 8Ah
0x18001641b  jmp     loc_180016023
  ... truncated ...
```
