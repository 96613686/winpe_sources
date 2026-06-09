# MkvMfSourceLib::MkvMfSource::CreateSource(IMFByteStream *,IMFTelemetrySession *,MkvMfSourceLib::MkvMfSource * *)

- ea: `0x180010d70`
- end: `0x180011060`
- name: `?CreateSource@MkvMfSource@MkvMfSourceLib@@SAJPEAUIMFByteStream@@PEAUIMFTelemetrySession@@PEAPEAV12@@Z`
- size: `752`
- prototype: `__int64 __fastcall(struct IMFByteStream *, struct IMFTelemetrySession *, struct MkvMfSourceLib::MkvMfSource **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000b080`
- `0x180050060`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000c440`
- `0x18000d554`
- `0x18000ddc0`
- `0x180010d70`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010dcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010eb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010f8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010dcf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010eb4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180010f8e`

## string_xrefs

- `0x180010d92`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x180010e39`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x180010f1e`: `MkvMfSourceLib::MkvMfSource::CreateSource`
- `0x180010ff8`: `MkvMfSourceLib::MkvMfSource::CreateSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MkvMfSourceLib::MkvMfSource::CreateSource(
        struct IMFByteStream *a1,
        struct IMFTelemetrySession *a2,
        struct MkvMfSourceLib::MkvMfSource **a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct MkvMfSourceLib::MkvMfSource *v22; // rax
  _QWORD v24[4]; // [rsp+30h] [rbp-20h] BYREF
  struct IMFByteStream *v25; // [rsp+70h] [rbp+20h] BYREF
  char v26; // [rsp+80h] [rbp+30h] BYREF
  int v27; // [rsp+88h] [rbp+38h] BYREF

  v25 = a1;
  v27 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "MkvMfSourceLib::MkvMfSource::CreateSource", 47);
  v24[1] = 0;
  v24[2] = &v27;
  if ( a3 )
  {
    v24[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    v27 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfSource,MkvMfSourceLib::MkvMfSource,IMFByteStream * &>(
            v24,
            &v25);
    if ( v27 >= 0 )
    {
      if ( v24[0] )
      {
        (*(void (__fastcall **)(__int64, struct IMFTelemetrySession *))(*(_QWORD *)(v24[0] + 56LL) + 32LL))(
          v24[0] + 56LL,
          a2);
        v22 = (struct MkvMfSourceLib::MkvMfSource *)v24[0];
        v24[0] = 0;
        *a3 = v22;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
        v11 = 0;
        goto LABEL_41;
      }
      v27 = -2147024882;
      v19 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v19 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
        if ( v27 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v27 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfSource::CreateSource", 56, v27);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 13;
    }
    else
    {
      v15 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( v27 < 0 && *((_DWORD *)v17 + 499) != v27 )
          CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::CreateSource", 55, v27);
      }
      if ( !g_wppLevels )
        goto LABEL_27;
      v18 = 12;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, 0, v27);
LABEL_27:
    v11 = v27;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v24);
    goto LABEL_41;
  }
  v27 = -2147467261;
  v8 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v6, v7);
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( v27 < 0 && *((_DWORD *)v10 + 499) != v27 )
      CallStackContext::TraceFailure(v10, "MkvMfSourceLib::MkvMfSource::CreateSource", 51, v27);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, 0, v27);
  v11 = v27;
LABEL_41:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return v11;
}

```

## disassembly

```asm
0x180010d70  mov     [rsp-18h+arg_0], rcx
0x180010d75  push    rbp
0x180010d76  push    rbx
0x180010d77  push    rdi
0x180010d78  mov     rbp, rsp
0x180010d7b  sub     rsp, 50h
0x180010d7f  mov     rbx, r8
0x180010d82  mov     rdi, rdx
0x180010d85  mov     [rbp+arg_18], 0
0x180010d8c  mov     r8d, 2Fh ; '/'; int
0x180010d92  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010d99  lea     rcx, [rbp+arg_10]; this
0x180010d9d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180010da2  nop
0x180010da3  mov     [rbp+var_18], 0
0x180010dab  lea     rax, [rbp+arg_18]
0x180010daf  mov     [rbp+var_10], rax
0x180010db3  test    rbx, rbx
0x180010db6  jnz     loc_180010E7F
0x180010dbc  mov     [rbp+arg_18], 80004003h
0x180010dc3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010dca  test    rcx, rcx
0x180010dcd  jnz     short loc_180010E16
0x180010dcf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010dd6  nop     dword ptr [rax+rax+00h]
0x180010ddb  mov     rcx, rax
0x180010dde  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010de5  test    rax, rax
0x180010de8  jz      short loc_180010E08
0x180010dea  mov     rax, [rax]
0x180010ded  mov     edx, 7F0h
0x180010df2  mov     rax, [rax+8]
0x180010df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dfb  test    eax, eax
0x180010dfd  jz      short loc_180010E08
0x180010dff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e06  jmp     short loc_180010E16
0x180010e08  lea     rcx, qword_1800DBF70; this
0x180010e0f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e16  cmp     byte ptr [rcx+8], 0
0x180010e1a  jz      short loc_180010E48
0x180010e1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010e21  mov     r9d, [rbp+arg_18]; int
0x180010e25  test    r9d, r9d
0x180010e28  jns     short loc_180010E48
0x180010e2a  cmp     [rax+7CCh], r9d
0x180010e31  jz      short loc_180010E48
0x180010e33  mov     r8d, 33h ; '3'; int
0x180010e39  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010e40  mov     rcx, rax; this
0x180010e43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010e48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010e4f  jb      short loc_180010E77
0x180010e51  mov     edx, 0Bh
0x180010e56  mov     eax, [rbp+arg_18]
0x180010e59  mov     [rsp+50h+var_30], eax
0x180010e5d  xor     r9d, r9d
0x180010e60  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180010e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e6e  mov     rcx, [rcx+10h]
0x180010e72  call    WPP_SF_qD
0x180010e77  mov     ebx, [rbp+arg_18]
0x180010e7a  jmp     loc_180010F69
0x180010e7f  mov     [rbp+var_20], 0
0x180010e87  lea     rcx, [rbp+var_20]
0x180010e8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010e90  lea     rdx, [rbp+arg_0]
0x180010e94  lea     rcx, [rbp+var_20]
0x180010e98  call    ??$MakeAndInitialize@VMkvMfSource@MkvMfSourceLib@@V12@AEAPEAUIMFByteStream@@@Details@WRL@Microsoft@@YAJPEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEAUIMFByteStream@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfSource,MkvMfSourceLib::MkvMfSource,IMFByteStream * &>(MkvMfSourceLib::MkvMfSource * *,IMFByteStream * &)
0x180010e9d  mov     [rbp+arg_18], eax
0x180010ea0  test    eax, eax
0x180010ea2  jns     loc_180010F6E
0x180010ea8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010eaf  test    rcx, rcx
0x180010eb2  jnz     short loc_180010EFB
0x180010eb4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010ebb  nop     dword ptr [rax+rax+00h]
0x180010ec0  mov     rcx, rax
0x180010ec3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010eca  test    rax, rax
0x180010ecd  jz      short loc_180010EED
0x180010ecf  mov     rax, [rax]
0x180010ed2  mov     edx, 7F0h
0x180010ed7  mov     rax, [rax+8]
0x180010edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee0  test    eax, eax
0x180010ee2  jz      short loc_180010EED
0x180010ee4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010eeb  jmp     short loc_180010EFB
0x180010eed  lea     rcx, qword_1800DBF70; this
0x180010ef4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010efb  cmp     byte ptr [rcx+8], 0
0x180010eff  jz      short loc_180010F2D
0x180010f01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010f06  mov     r9d, [rbp+arg_18]; int
0x180010f0a  test    r9d, r9d
0x180010f0d  jns     short loc_180010F2D
0x180010f0f  cmp     [rax+7CCh], r9d
0x180010f16  jz      short loc_180010F2D
0x180010f18  mov     r8d, 37h ; '7'; int
0x180010f1e  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010f25  mov     rcx, rax; this
0x180010f28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180010f2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180010f34  jb      short loc_180010F5C
0x180010f36  mov     edx, 0Ch
0x180010f3b  mov     eax, [rbp+arg_18]
0x180010f3e  mov     [rsp+50h+var_30], eax
0x180010f42  xor     r9d, r9d
0x180010f45  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180010f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f53  mov     rcx, [rcx+10h]
0x180010f57  call    WPP_SF_qD
0x180010f5c  mov     ebx, [rbp+arg_18]
0x180010f5f  lea     rcx, [rbp+var_20]
0x180010f63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010f68  nop
0x180010f69  jmp     loc_18001104C
0x180010f6e  mov     rax, [rbp+var_20]
0x180010f72  test    rax, rax
0x180010f75  jnz     loc_18001101E
0x180010f7b  mov     [rbp+arg_18], 8007000Eh
0x180010f82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f89  test    rcx, rcx
0x180010f8c  jnz     short loc_180010FD5
0x180010f8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180010f95  nop     dword ptr [rax+rax+00h]
0x180010f9a  mov     rcx, rax
0x180010f9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180010fa4  test    rax, rax
0x180010fa7  jz      short loc_180010FC7
0x180010fa9  mov     rax, [rax]
0x180010fac  mov     edx, 7F0h
0x180010fb1  mov     rax, [rax+8]
0x180010fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fba  test    eax, eax
0x180010fbc  jz      short loc_180010FC7
0x180010fbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010fc5  jmp     short loc_180010FD5
0x180010fc7  lea     rcx, qword_1800DBF70; this
0x180010fce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180010fd5  cmp     byte ptr [rcx+8], 0
0x180010fd9  jz      short loc_180011007
0x180010fdb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180010fe0  mov     r9d, [rbp+arg_18]; int
0x180010fe4  test    r9d, r9d
0x180010fe7  jns     short loc_180011007
0x180010fe9  cmp     [rax+7CCh], r9d
0x180010ff0  jz      short loc_180011007
0x180010ff2  mov     r8d, 38h ; '8'; int
0x180010ff8  lea     rdx, aMkvmfsourcelib_21; "MkvMfSourceLib::MkvMfSource::CreateSour"...
0x180010fff  mov     rcx, rax; this
0x180011002  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180011007  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001100e  jb      loc_180010F5C
0x180011014  mov     edx, 0Dh
0x180011019  jmp     loc_180010F3B
0x18001101e  lea     rcx, [rax+38h]
0x180011022  mov     rax, [rcx]
0x180011025  mov     rdx, rdi
0x180011028  mov     rax, [rax+20h]
0x18001102c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011031  mov     rax, [rbp+var_20]
0x180011035  mov     [rbp+var_20], 0
0x18001103d  mov     [rbx], rax
0x180011040  lea     rcx, [rbp+var_20]
0x180011044  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011049  nop
0x18001104a  xor     ebx, ebx
0x18001104c  lea     rcx, [rbp+arg_10]; this
0x180011050  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180011055  mov     eax, ebx
0x180011057  add     rsp, 50h
0x18001105b  pop     rdi
0x18001105c  pop     rbx
0x18001105d  pop     rbp
0x18001105e  retn
```
