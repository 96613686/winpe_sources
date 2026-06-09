# MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x180030e28`
- end: `0x180031263`
- name: `?CreateStream@MkvMfStreamSubtitle@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180011068`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180030c14`
- `0x180030cec`
- `0x180030e28`
- `0x18004cc60`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030e73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800310eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800311ad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030e73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031036`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800310eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800311ad`

## string_xrefs

- `0x180030e4a`: `MkvMfSourceLib::MkvMfStreamSubtitle::CreateStream`

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
              v22 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v15 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v25 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v29 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v8 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180030e28  mov     [rsp-20h+arg_8], rdx
0x180030e2d  mov     [rsp-20h+arg_0], rcx
0x180030e32  push    rbp
0x180030e33  push    rbx
0x180030e34  push    rdi
0x180030e35  push    r14
0x180030e37  mov     rbp, rsp
0x180030e3a  sub     rsp, 58h
0x180030e3e  mov     rdi, r8
0x180030e41  mov     rbx, rdx
0x180030e44  mov     r8d, 41h ; 'A'; int
0x180030e4a  lea     r14, aMkvmfsourcelib_147
0x180030e51  mov     rdx, r14; char *
0x180030e54  lea     rcx, [rbp+arg_10]; this
0x180030e58  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z
0x180030e5d  nop
0x180030e5e  test    rdi, rdi
0x180030e61  jnz     loc_180030F1B
0x180030e67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180030e6e  test    rcx, rcx
0x180030e71  jnz     short loc_180030EBA
0x180030e73  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030e7a  nop     dword ptr [rax+rax+00h]
0x180030e7f  mov     rcx, rax
0x180030e82  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180030e89  test    rax, rax
0x180030e8c  jz      short loc_180030EAC
0x180030e8e  mov     rax, [rax]
0x180030e91  mov     edx, 7F0h
0x180030e96  mov     rax, [rax+8]
0x180030e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e9f  test    eax, eax
0x180030ea1  jz      short loc_180030EAC
0x180030ea3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180030eaa  jmp     short loc_180030EBA
0x180030eac  lea     rcx, qword_1800DBF70; this
0x180030eb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180030eba  mov     ebx, 80004003h
0x180030ebf  cmp     byte ptr [rcx+8], 0
0x180030ec3  jz      short loc_180030EE6
0x180030ec5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180030eca  cmp     [rax+7CCh], ebx
0x180030ed0  jz      short loc_180030EE6
0x180030ed2  mov     r9d, ebx; int
0x180030ed5  mov     r8d, 49h ; 'I'; int
0x180030edb  mov     rdx, r14; char *
0x180030ede  mov     rcx, rax; this
0x180030ee1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180030ee6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180030eed  jb      loc_18003124D
0x180030ef3  mov     edx, 12h
0x180030ef8  mov     [rsp+58h+var_38], ebx
0x180030efc  xor     r9d, r9d
0x180030eff  lea     r8, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids
0x180030f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f0d  mov     rcx, [rcx+10h]
0x180030f11  call    WPP_SF_qD
0x180030f16  jmp     loc_18003124D
0x180030f1b  mov     qword ptr [rdi], 0
0x180030f22  mov     [rbp+arg_18], 0
0x180030f2a  mov     rdx, [rbx+58h]
0x180030f2e  lea     rcx, [rbp+var_28]
0x180030f32  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z
0x180030f37  mov     ecx, [rbp+var_28]
0x180030f3a  sub     ecx, 29h ; ')'
0x180030f3d  jz      loc_1800310BB
0x180030f43  sub     ecx, 1
0x180030f46  jz      loc_1800310BB
0x180030f4c  sub     ecx, 1
0x180030f4f  jz      loc_180031006
0x180030f55  sub     ecx, 1
0x180030f58  jz      loc_180031006
0x180030f5e  sub     ecx, 2
0x180030f61  jz      loc_180031006
0x180030f67  cmp     ecx, 1
0x180030f6a  jz      loc_1800310BB
0x180030f70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180030f77  test    rcx, rcx
0x180030f7a  jnz     short loc_180030FC3
0x180030f7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030f83  nop     dword ptr [rax+rax+00h]
0x180030f88  mov     rcx, rax
0x180030f8b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180030f92  test    rax, rax
0x180030f95  jz      short loc_180030FB5
0x180030f97  mov     rax, [rax]
0x180030f9a  mov     edx, 7F0h
0x180030f9f  mov     rax, [rax+8]
0x180030fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fa8  test    eax, eax
0x180030faa  jz      short loc_180030FB5
0x180030fac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180030fb3  jmp     short loc_180030FC3
0x180030fb5  lea     rcx, qword_1800DBF70; this
0x180030fbc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180030fc3  mov     ebx, 0C00D36C4h
0x180030fc8  cmp     byte ptr [rcx+8], 0
0x180030fcc  jz      short loc_180030FEF
0x180030fce  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180030fd3  cmp     [rax+7CCh], ebx
0x180030fd9  jz      short loc_180030FEF
0x180030fdb  mov     r9d, ebx; int
0x180030fde  mov     r8d, 62h ; 'b'; int
0x180030fe4  mov     rdx, r14; char *
0x180030fe7  mov     rcx, rax; this
0x180030fea  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180030fef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180030ff6  jb      loc_180031186
0x180030ffc  mov     edx, 15h
0x180031001  jmp     loc_180031167
0x180031006  lea     rcx, [rbp+arg_18]
0x18003100a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18003100f  lea     r8, [rbp+arg_8]
0x180031013  lea     rdx, [rbp+arg_0]
0x180031017  lea     rcx, [rbp+arg_18]
0x18003101b  call    ??$MakeAndInitialize@VMkvMfStreamSubtitleWithInitializationCue@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z
0x180031020  mov     ebx, eax
0x180031022  test    eax, eax
0x180031024  jns     loc_180031194
0x18003102a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180031031  test    rcx, rcx
0x180031034  jnz     short loc_18003107D
0x180031036  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003103d  nop     dword ptr [rax+rax+00h]
0x180031042  mov     rcx, rax
0x180031045  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x18003104c  test    rax, rax
0x18003104f  jz      short loc_18003106F
0x180031051  mov     rax, [rax]
0x180031054  mov     edx, 7F0h
0x180031059  mov     rax, [rax+8]
0x18003105d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031062  test    eax, eax
0x180031064  jz      short loc_18003106F
0x180031066  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18003106d  jmp     short loc_18003107D
0x18003106f  lea     rcx, qword_1800DBF70; this
0x180031076  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18003107d  cmp     byte ptr [rcx+8], 0
0x180031081  jz      short loc_1800310A4
0x180031083  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180031088  cmp     [rax+7CCh], ebx
0x18003108e  jz      short loc_1800310A4
0x180031090  mov     r9d, ebx; int
0x180031093  mov     r8d, 5Fh ; '_'; int
0x180031099  mov     rdx, r14; char *
0x18003109c  mov     rcx, rax; this
0x18003109f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x1800310a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x1800310ab  jb      loc_180031186
0x1800310b1  mov     edx, 14h
0x1800310b6  jmp     loc_180031167
0x1800310bb  lea     rcx, [rbp+arg_18]
0x1800310bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x1800310c4  lea     r8, [rbp+arg_8]
0x1800310c8  lea     rdx, [rbp+arg_0]
0x1800310cc  lea     rcx, [rbp+arg_18]
0x1800310d0  call    ??$MakeAndInitialize@VMkvMfStreamSubtitle@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z
0x1800310d5  mov     ebx, eax
0x1800310d7  test    eax, eax
0x1800310d9  jns     loc_180031194
0x1800310df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x1800310e6  test    rcx, rcx
0x1800310e9  jnz     short loc_180031132
0x1800310eb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800310f2  nop     dword ptr [rax+rax+00h]
0x1800310f7  mov     rcx, rax
0x1800310fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180031101  test    rax, rax
0x180031104  jz      short loc_180031124
0x180031106  mov     rax, [rax]
0x180031109  mov     edx, 7F0h
0x18003110e  mov     rax, [rax+8]
0x180031112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031117  test    eax, eax
0x180031119  jz      short loc_180031124
0x18003111b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180031122  jmp     short loc_180031132
0x180031124  lea     rcx, qword_1800DBF70; this
0x18003112b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x180031132  cmp     byte ptr [rcx+8], 0
0x180031136  jz      short loc_180031159
0x180031138  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x18003113d  cmp     [rax+7CCh], ebx
0x180031143  jz      short loc_180031159
0x180031145  mov     r9d, ebx; int
0x180031148  mov     r8d, 5Ah ; 'Z'; int
0x18003114e  mov     rdx, r14; char *
0x180031151  mov     rcx, rax; this
0x180031154  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180031159  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180031160  jb      short loc_180031186
0x180031162  mov     edx, 13h
0x180031167  mov     [rsp+58h+var_38], ebx
0x18003116b  xor     r9d, r9d
0x18003116e  lea     r8, WPP_ac54f2ccc63f3971ba109cad13a64792_Traceguids
0x180031175  mov     rcx, cs:WPP_GLOBAL_Control
0x18003117c  mov     rcx, [rcx+10h]
0x180031180  call    WPP_SF_qD
0x180031185  nop
0x180031186  lea     rcx, [rbp+arg_18]
0x18003118a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18003118f  jmp     loc_18003124D
0x180031194  mov     rax, [rbp+arg_18]
0x180031198  test    rax, rax
0x18003119b  jnz     loc_180031237
0x1800311a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x1800311a8  test    rcx, rcx
0x1800311ab  jnz     short loc_1800311F4
0x1800311ad  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800311b4  nop     dword ptr [rax+rax+00h]
0x1800311b9  mov     rcx, rax
0x1800311bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x1800311c3  test    rax, rax
0x1800311c6  jz      short loc_1800311E6
0x1800311c8  mov     rax, [rax]
0x1800311cb  mov     edx, 7F0h
0x1800311d0  mov     rax, [rax+8]
0x1800311d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311d9  test    eax, eax
0x1800311db  jz      short loc_1800311E6
0x1800311dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x1800311e4  jmp     short loc_1800311F4
0x1800311e6  lea     rcx, qword_1800DBF70; this
0x1800311ed  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x1800311f4  mov     ebx, 8007000Eh
0x1800311f9  cmp     byte ptr [rcx+8], 0
0x1800311fd  jz      short loc_180031220
0x1800311ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ
0x180031204  cmp     [rax+7CCh], ebx
0x18003120a  jz      short loc_180031220
0x18003120c  mov     r9d, ebx; int
0x18003120f  mov     r8d, 66h ; 'f'; int
0x180031215  mov     rdx, r14; char *
0x180031218  mov     rcx, rax; this
0x18003121b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z
0x180031220  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1
0x180031227  jb      loc_180031186
0x18003122d  mov     edx, 16h
0x180031232  jmp     loc_180031167
0x180031237  mov     [rbp+arg_18], 0
0x18003123f  mov     [rdi], rax
0x180031242  lea     rcx, [rbp+arg_18]
0x180031246  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ
0x18003124b  xor     ebx, ebx
0x18003124d  lea     rcx, [rbp+arg_10]; this
0x180031251  call    ??1CallStackScopeTrace@@QEAA@XZ
0x180031256  mov     eax, ebx
0x180031258  add     rsp, 58h
0x18003125c  pop     r14
0x18003125e  pop     rdi
0x18003125f  pop     rbx
0x180031260  pop     rbp
0x180031261  retn
```
