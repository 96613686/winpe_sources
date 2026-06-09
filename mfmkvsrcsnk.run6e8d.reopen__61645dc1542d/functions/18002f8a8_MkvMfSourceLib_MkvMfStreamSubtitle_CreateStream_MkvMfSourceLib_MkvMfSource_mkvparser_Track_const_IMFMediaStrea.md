# MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x18002f8a8`
- end: `0x18002fcc4`
- name: `?CreateStream@MkvMfStreamSubtitle@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180010940`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18002f694`
- `0x18002f76c`
- `0x18002f8a8`
- `0x18004acfc`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002faaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fb59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f8f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002f9f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002faaa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fb59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002fc15`

## string_xrefs

- `0x18002f8ca`: `MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(
        struct MkvMfSourceLib::MkvMfSource *a1,
        const struct mkvparser::Track *a2,
        struct IMFMediaStream **a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  int v10; // ebx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  struct IMFMediaStream *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  _DWORD v33[10]; // [rsp+30h] [rbp-28h] BYREF
  struct MkvMfSourceLib::MkvMfSource *v34; // [rsp+80h] [rbp+28h] BYREF
  const struct mkvparser::Track *v35; // [rsp+88h] [rbp+30h] BYREF
  char v36; // [rsp+90h] [rbp+38h] BYREF
  struct IMFMediaStream *v37; // [rsp+98h] [rbp+40h] BYREF

  v35 = a2;
  v34 = a1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v36,
    "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream",
    65);
  if ( a3 )
  {
    *a3 = 0;
    v37 = 0;
    MkvMfSourceLib::CodecFromIdString(v33, *((_QWORD *)a2 + 11));
    if ( v33[0] != 41 && v33[0] != 42 )
    {
      if ( v33[0] == 43 || v33[0] == 44 || v33[0] == 46 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamSubtitleWithInitializationCue,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                &v37,
                &v34,
                &v35);
        if ( v10 < 0 )
        {
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream",
                95,
                v10);
          }
          if ( !g_wppLevels )
            goto LABEL_51;
          v18 = 20;
          goto LABEL_50;
        }
        goto LABEL_52;
      }
      if ( v33[0] != 47 )
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
            v15 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        v10 = -1072875836;
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != -1072875836 )
            CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream", 98, -1072875836);
        }
        if ( !g_wppLevels )
          goto LABEL_51;
        v18 = 21;
LABEL_50:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids, 0, v10);
LABEL_51:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        goto LABEL_64;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamSubtitle,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
            &v37,
            &v34,
            &v35);
    if ( v10 < 0 )
    {
      v25 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v26;
        if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v25 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != v10 )
          CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream", 90, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_51;
      v18 = 19;
      goto LABEL_50;
    }
LABEL_52:
    v28 = v37;
    if ( v37 )
    {
      v37 = 0;
      *a3 = v28;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      v10 = 0;
      goto LABEL_64;
    }
    v29 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v10 = -2147024882;
    if ( *((_BYTE *)v29 + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
      if ( *((_DWORD *)v31 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v31, "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream", 102, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_51;
    v18 = 22;
    goto LABEL_50;
  }
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
      v8 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  v10 = -2147467261;
  if ( *((_BYTE *)v8 + 8) )
  {
    v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)v11 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream", 73, -2147467261);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids, 0, -2147467261);
LABEL_64:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f8a8  mov     [rsp-20h+arg_8], rdx
0x18002f8ad  mov     [rsp-20h+arg_0], rcx
0x18002f8b2  push    rbp
0x18002f8b3  push    rbx
0x18002f8b4  push    rdi
0x18002f8b5  push    r14
0x18002f8b7  mov     rbp, rsp
0x18002f8ba  sub     rsp, 58h
0x18002f8be  mov     rdi, r8
0x18002f8c1  mov     rbx, rdx
0x18002f8c4  mov     r8d, 41h ; 'A'; int
0x18002f8ca  lea     r14, aMkvmfsourcelib_147
0x18002f8d1  mov     rdx, r14; char *
0x18002f8d4  lea     rcx, [rbp+arg_10]; this
0x18002f8d8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z
0x18002f8dd  nop
0x18002f8de  test    rdi, rdi
0x18002f8e1  jnz     loc_18002F995
0x18002f8e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002f8ee  test    rcx, rcx
0x18002f8f1  jnz     short loc_18002F934
0x18002f8f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f8f9  mov     rcx, rax
0x18002f8fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18002f903  test    rax, rax
0x18002f906  jz      short loc_18002F926
0x18002f908  mov     rax, [rax]
0x18002f90b  mov     edx, 7F0h
0x18002f910  mov     rax, [rax+8]
0x18002f914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f919  test    eax, eax
0x18002f91b  jz      short loc_18002F926
0x18002f91d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002f924  jmp     short loc_18002F934
0x18002f926  lea     rcx, qword_1800D6F70; this
0x18002f92d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002f934  mov     ebx, 80004003h
0x18002f939  cmp     byte ptr [rcx+8], 0
0x18002f93d  jz      short loc_18002F960
0x18002f93f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18002f944  cmp     [rax+7CCh], ebx
0x18002f94a  jz      short loc_18002F960
0x18002f94c  mov     r9d, ebx; int
0x18002f94f  mov     r8d, 49h ; 'I'; int
0x18002f955  mov     rdx, r14; char *
0x18002f958  mov     rcx, rax; this
0x18002f95b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18002f960  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18002f967  jb      loc_18002FCAF
0x18002f96d  mov     edx, 12h
0x18002f972  mov     [rsp+58h+var_38], ebx
0x18002f976  xor     r9d, r9d
0x18002f979  lea     r8, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids
0x18002f980  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f987  mov     rcx, [rcx+10h]
0x18002f98b  call    WPP_SF_qD
0x18002f990  jmp     loc_18002FCAF
0x18002f995  mov     qword ptr [rdi], 0
0x18002f99c  mov     [rbp+arg_18], 0
0x18002f9a4  mov     rdx, [rbx+58h]
0x18002f9a8  lea     rcx, [rbp+var_28]
0x18002f9ac  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z
0x18002f9b1  mov     ecx, [rbp+var_28]
0x18002f9b4  sub     ecx, 29h ; ')'
0x18002f9b7  jz      loc_18002FB29
0x18002f9bd  sub     ecx, 1
0x18002f9c0  jz      loc_18002FB29
0x18002f9c6  sub     ecx, 1
0x18002f9c9  jz      loc_18002FA7A
0x18002f9cf  sub     ecx, 1
0x18002f9d2  jz      loc_18002FA7A
0x18002f9d8  sub     ecx, 2
0x18002f9db  jz      loc_18002FA7A
0x18002f9e1  cmp     ecx, 1
0x18002f9e4  jz      loc_18002FB29
0x18002f9ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002f9f1  test    rcx, rcx
0x18002f9f4  jnz     short loc_18002FA37
0x18002f9f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002f9fc  mov     rcx, rax
0x18002f9ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18002fa06  test    rax, rax
0x18002fa09  jz      short loc_18002FA29
0x18002fa0b  mov     rax, [rax]
0x18002fa0e  mov     edx, 7F0h
0x18002fa13  mov     rax, [rax+8]
0x18002fa17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa1c  test    eax, eax
0x18002fa1e  jz      short loc_18002FA29
0x18002fa20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fa27  jmp     short loc_18002FA37
0x18002fa29  lea     rcx, qword_1800D6F70; this
0x18002fa30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002fa37  mov     ebx, 0C00D36C4h
0x18002fa3c  cmp     byte ptr [rcx+8], 0
0x18002fa40  jz      short loc_18002FA63
0x18002fa42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18002fa47  cmp     [rax+7CCh], ebx
0x18002fa4d  jz      short loc_18002FA63
0x18002fa4f  mov     r9d, ebx; int
0x18002fa52  mov     r8d, 62h ; 'b'; int
0x18002fa58  mov     rdx, r14; char *
0x18002fa5b  mov     rcx, rax; this
0x18002fa5e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18002fa63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18002fa6a  jb      loc_18002FBEE
0x18002fa70  mov     edx, 15h
0x18002fa75  jmp     loc_18002FBCF
0x18002fa7a  lea     rcx, [rbp+arg_18]
0x18002fa7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18002fa83  lea     r8, [rbp+arg_8]
0x18002fa87  lea     rdx, [rbp+arg_0]
0x18002fa8b  lea     rcx, [rbp+arg_18]
0x18002fa8f  call    ??$MakeAndInitialize@VMkvMfStreamSubtitleWithInitializationCue@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z
0x18002fa94  mov     ebx, eax
0x18002fa96  test    eax, eax
0x18002fa98  jns     loc_18002FBFC
0x18002fa9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002faa5  test    rcx, rcx
0x18002faa8  jnz     short loc_18002FAEB
0x18002faaa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fab0  mov     rcx, rax
0x18002fab3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18002faba  test    rax, rax
0x18002fabd  jz      short loc_18002FADD
0x18002fabf  mov     rax, [rax]
0x18002fac2  mov     edx, 7F0h
0x18002fac7  mov     rax, [rax+8]
0x18002facb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fad0  test    eax, eax
0x18002fad2  jz      short loc_18002FADD
0x18002fad4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fadb  jmp     short loc_18002FAEB
0x18002fadd  lea     rcx, qword_1800D6F70; this
0x18002fae4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002faeb  cmp     byte ptr [rcx+8], 0
0x18002faef  jz      short loc_18002FB12
0x18002faf1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18002faf6  cmp     [rax+7CCh], ebx
0x18002fafc  jz      short loc_18002FB12
0x18002fafe  mov     r9d, ebx; int
0x18002fb01  mov     r8d, 5Fh ; '_'; int
0x18002fb07  mov     rdx, r14; char *
0x18002fb0a  mov     rcx, rax; this
0x18002fb0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18002fb12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18002fb19  jb      loc_18002FBEE
0x18002fb1f  mov     edx, 14h
0x18002fb24  jmp     loc_18002FBCF
0x18002fb29  lea     rcx, [rbp+arg_18]
0x18002fb2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18002fb32  lea     r8, [rbp+arg_8]
0x18002fb36  lea     rdx, [rbp+arg_0]
0x18002fb3a  lea     rcx, [rbp+arg_18]
0x18002fb3e  call    ??$MakeAndInitialize@VMkvMfStreamSubtitle@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z
0x18002fb43  mov     ebx, eax
0x18002fb45  test    eax, eax
0x18002fb47  jns     loc_18002FBFC
0x18002fb4d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fb54  test    rcx, rcx
0x18002fb57  jnz     short loc_18002FB9A
0x18002fb59  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fb5f  mov     rcx, rax
0x18002fb62  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18002fb69  test    rax, rax
0x18002fb6c  jz      short loc_18002FB8C
0x18002fb6e  mov     rax, [rax]
0x18002fb71  mov     edx, 7F0h
0x18002fb76  mov     rax, [rax+8]
0x18002fb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb7f  test    eax, eax
0x18002fb81  jz      short loc_18002FB8C
0x18002fb83  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fb8a  jmp     short loc_18002FB9A
0x18002fb8c  lea     rcx, qword_1800D6F70; this
0x18002fb93  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002fb9a  cmp     byte ptr [rcx+8], 0
0x18002fb9e  jz      short loc_18002FBC1
0x18002fba0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18002fba5  cmp     [rax+7CCh], ebx
0x18002fbab  jz      short loc_18002FBC1
0x18002fbad  mov     r9d, ebx; int
0x18002fbb0  mov     r8d, 5Ah ; 'Z'; int
0x18002fbb6  mov     rdx, r14; char *
0x18002fbb9  mov     rcx, rax; this
0x18002fbbc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18002fbc1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18002fbc8  jb      short loc_18002FBEE
0x18002fbca  mov     edx, 13h
0x18002fbcf  mov     [rsp+58h+var_38], ebx
0x18002fbd3  xor     r9d, r9d
0x18002fbd6  lea     r8, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids
0x18002fbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbe4  mov     rcx, [rcx+10h]
0x18002fbe8  call    WPP_SF_qD
0x18002fbed  nop
0x18002fbee  lea     rcx, [rbp+arg_18]
0x18002fbf2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18002fbf7  jmp     loc_18002FCAF
0x18002fbfc  mov     rax, [rbp+arg_18]
0x18002fc00  test    rax, rax
0x18002fc03  jnz     loc_18002FC99
0x18002fc09  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fc10  test    rcx, rcx
0x18002fc13  jnz     short loc_18002FC56
0x18002fc15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002fc1b  mov     rcx, rax
0x18002fc1e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18002fc25  test    rax, rax
0x18002fc28  jz      short loc_18002FC48
0x18002fc2a  mov     rax, [rax]
0x18002fc2d  mov     edx, 7F0h
0x18002fc32  mov     rax, [rax+8]
0x18002fc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc3b  test    eax, eax
0x18002fc3d  jz      short loc_18002FC48
0x18002fc3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002fc46  jmp     short loc_18002FC56
0x18002fc48  lea     rcx, qword_1800D6F70; this
0x18002fc4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002fc56  mov     ebx, 8007000Eh
0x18002fc5b  cmp     byte ptr [rcx+8], 0
0x18002fc5f  jz      short loc_18002FC82
0x18002fc61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18002fc66  cmp     [rax+7CCh], ebx
0x18002fc6c  jz      short loc_18002FC82
0x18002fc6e  mov     r9d, ebx; int
0x18002fc71  mov     r8d, 66h ; 'f'; int
0x18002fc77  mov     rdx, r14; char *
0x18002fc7a  mov     rcx, rax; this
0x18002fc7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x18002fc82  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x18002fc89  jb      loc_18002FBEE
0x18002fc8f  mov     edx, 16h
0x18002fc94  jmp     loc_18002FBCF
0x18002fc99  mov     [rbp+arg_18], 0
0x18002fca1  mov     [rdi], rax
0x18002fca4  lea     rcx, [rbp+arg_18]
0x18002fca8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18002fcad  xor     ebx, ebx
0x18002fcaf  lea     rcx, [rbp+arg_10]; this
0x18002fcb3  call    ??1CallStackScopeTrace@@QEAA@XZ
0x18002fcb8  mov     eax, ebx
0x18002fcba  add     rsp, 58h
0x18002fcbe  pop     r14
0x18002fcc0  pop     rdi
0x18002fcc1  pop     rbx
0x18002fcc2  pop     rbp
0x18002fcc3  retn
```
