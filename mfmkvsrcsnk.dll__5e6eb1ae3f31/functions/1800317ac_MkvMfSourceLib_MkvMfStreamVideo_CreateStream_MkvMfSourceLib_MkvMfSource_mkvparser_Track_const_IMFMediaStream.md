# MkvMfSourceLib::MkvMfStreamVideo::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x1800317ac`
- end: `0x180032029`
- name: `?CreateStream@MkvMfStreamVideo@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `2173`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180010940`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180030c04`
- `0x180030d00`
- `0x180030dd8`
- `0x180030ee8`
- `0x180030fc0`
- `0x180031098`
- `0x180031294`
- `0x1800312d4`
- `0x1800317ac`
- `0x18004acfc`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800317fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800319c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031b25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031c01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031cb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031e0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031f7b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800317fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031921`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800319c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031a76`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031b25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031c01`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031cb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031d5f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031e0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031ed8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031f7b`

## string_xrefs

- `0x1800317d0`: `MkvMfSourceLib::MkvMfStreamVideo::CreateStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfStreamVideo::CreateStream(
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
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  struct IMFMediaStream *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  int v48[8]; // [rsp+30h] [rbp-20h] BYREF
  struct MkvMfSourceLib::MkvMfSource *v49; // [rsp+80h] [rbp+30h] BYREF
  const struct mkvparser::Track *v50; // [rsp+88h] [rbp+38h] BYREF
  char v51; // [rsp+90h] [rbp+40h] BYREF
  __int64 v52; // [rsp+98h] [rbp+48h] BYREF

  v50 = a2;
  v49 = a1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v51,
    "MkvMfSourceLib::MkvMfStreamVideo::CreateStream",
    234);
  if ( a3 )
  {
    *a3 = 0;
    v52 = 0;
    MkvMfSourceLib::CodecFromIdString(v48, *((_QWORD *)a2 + 11));
    if ( v48[0] > 12 )
    {
      if ( v48[0] != 13 && v48[0] != 14 )
      {
        switch ( v48[0] )
        {
          case 15:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoAVC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                    &v52,
                    &v49,
                    &v50);
            if ( v10 < 0 )
            {
              v37 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
                CallStackTracing::s_wpInstance = v38;
                if ( v38
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
                {
                  v37 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v37 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v37 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "MkvMfSourceLib::MkvMfStreamVideo::CreateStream",
                    248,
                    v10);
              }
              if ( !g_wppLevels )
                goto LABEL_113;
              v18 = 34;
              goto LABEL_112;
            }
            goto LABEL_126;
          case 16:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoHEVC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                    &v52,
                    &v49,
                    &v50);
            if ( v10 < 0 )
            {
              v34 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
                CallStackTracing::s_wpInstance = v35;
                if ( v35
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
                {
                  v34 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v34 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v34 + 8) )
              {
                v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
                if ( *((_DWORD *)v36 + 499) != v10 )
                  CallStackContext::TraceFailure(v36, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 264, v10);
              }
              if ( !g_wppLevels )
                goto LABEL_113;
              v18 = 38;
              goto LABEL_112;
            }
            goto LABEL_126;
          case 20:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoAV1,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                    &v52,
                    &v49,
                    &v50);
            if ( v10 < 0 )
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
                CallStackTracing::s_wpInstance = v32;
                if ( v32
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v31 = &qword_1800D6F70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
                }
              }
              if ( *((_BYTE *)v31 + 8) )
              {
                v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                if ( *((_DWORD *)v33 + 499) != v10 )
                  CallStackContext::TraceFailure(v33, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 267, v10);
              }
              if ( !g_wppLevels )
                goto LABEL_113;
              v18 = 39;
              goto LABEL_112;
            }
            goto LABEL_126;
        }
        goto LABEL_68;
      }
    }
    else if ( v48[0] != 12 )
    {
      switch ( v48[0] )
      {
        case 1:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                  &v52,
                  &v49,
                  &v50);
          if ( v10 < 0 )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
                CallStackContext::TraceFailure(v27, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 273, v10);
            }
            if ( !g_wppLevels )
              goto LABEL_113;
            v18 = 41;
            goto LABEL_112;
          }
          goto LABEL_126;
        case 2:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVFW,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                  &v52,
                  &v49,
                  &v50);
          if ( v10 < 0 )
          {
            v22 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
              CallStackTracing::s_wpInstance = v23;
              if ( v23
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
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
              v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
              if ( *((_DWORD *)v24 + 499) != v10 )
                CallStackContext::TraceFailure(v24, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 251, v10);
            }
            if ( !g_wppLevels )
              goto LABEL_113;
            v18 = 35;
            goto LABEL_112;
          }
          goto LABEL_126;
        case 6:
        case 7:
          v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoMPEG,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                  &v52,
                  &v49,
                  &v50);
          if ( v10 < 0 )
          {
            v19 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
              CallStackTracing::s_wpInstance = v20;
              if ( v20
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
              {
                v19 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v19 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v19 + 8) )
            {
              v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
              if ( *((_DWORD *)v21 + 499) != v10 )
                CallStackContext::TraceFailure(v21, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 255, v10);
            }
            if ( !g_wppLevels )
              goto LABEL_113;
            v18 = 36;
            goto LABEL_112;
          }
          goto LABEL_126;
        case 8:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
          v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoCodecPrivateAsUserData,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
                  &v52,
                  &v49,
                  &v50);
          if ( v10 < 0 )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
              CallStackTracing::s_wpInstance = v16;
              if ( v16
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
              {
                v15 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v15 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v15 + 8) )
            {
              v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
              if ( *((_DWORD *)v17 + 499) != v10 )
                CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 270, v10);
            }
            if ( !g_wppLevels )
              goto LABEL_113;
            v18 = 40;
LABEL_112:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v18,
              &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids,
              0,
              v10);
LABEL_113:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            goto LABEL_138;
          }
LABEL_126:
          v43 = (struct IMFMediaStream *)v52;
          if ( v52 )
          {
            v52 = 0;
            *a3 = v43;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
            v10 = 0;
            goto LABEL_138;
          }
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
            CallStackTracing::s_wpInstance = v45;
            if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
            {
              v44 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v44 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          v10 = -2147024882;
          if ( *((_BYTE *)v44 + 8) )
          {
            v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
            if ( *((_DWORD *)v46 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v46, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 281, -2147024882);
          }
          if ( !g_wppLevels )
            goto LABEL_113;
          v18 = 43;
          goto LABEL_112;
      }
LABEL_68:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
      v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideo,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
              &v52,
              &v49,
              &v50);
      if ( v10 < 0 )
      {
        v28 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
          if ( *((_DWORD *)v30 + 499) != v10 )
            CallStackContext::TraceFailure(v30, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 276, v10);
        }
        if ( !g_wppLevels )
          goto LABEL_113;
        v18 = 42;
        goto LABEL_112;
      }
      goto LABEL_126;
    }
    v10 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoMPEG,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
            &v52,
            &v49,
            &v50);
    if ( v10 < 0 )
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != v10 )
          CallStackContext::TraceFailure(v42, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 260, v10);
      }
      if ( !g_wppLevels )
        goto LABEL_113;
      v18 = 37;
      goto LABEL_112;
    }
    *(_BYTE *)(v52 + 456) = 1;
    goto LABEL_126;
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
      CallStackContext::TraceFailure(v11, "MkvMfSourceLib::MkvMfStreamVideo::CreateStream", 234, -2147467261);
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids, 0, -2147467261);
LABEL_138:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800317ac  mov     [rsp-28h+arg_8], rdx
0x1800317b1  mov     [rsp-28h+arg_0], rcx
0x1800317b6  push    rbp
0x1800317b7  push    rbx
0x1800317b8  push    rsi
0x1800317b9  push    r14
0x1800317bb  push    r15
0x1800317bd  mov     rbp, rsp
0x1800317c0  sub     rsp, 50h
0x1800317c4  mov     rsi, r8
0x1800317c7  mov     rbx, rdx
0x1800317ca  mov     r8d, 0EAh; int
0x1800317d0  lea     r15, aMkvmfsourcelib_11; "MkvMfSourceLib::MkvMfStreamVideo::Creat"...
0x1800317d7  mov     rdx, r15; char *
0x1800317da  lea     rcx, [rbp+arg_10]; this
0x1800317de  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800317e3  nop
0x1800317e4  xor     r14d, r14d
0x1800317e7  test    rsi, rsi
0x1800317ea  jnz     loc_18003189E
0x1800317f0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800317f7  test    rcx, rcx
0x1800317fa  jnz     short loc_18003183D
0x1800317fc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031802  mov     rcx, rax
0x180031805  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003180c  test    rax, rax
0x18003180f  jz      short loc_18003182F
0x180031811  mov     rax, [rax]
0x180031814  mov     edx, 7F0h
0x180031819  mov     rax, [rax+8]
0x18003181d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031822  test    eax, eax
0x180031824  jz      short loc_18003182F
0x180031826  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003182d  jmp     short loc_18003183D
0x18003182f  lea     rcx, qword_1800D6F70; this
0x180031836  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003183d  mov     ebx, 80004003h
0x180031842  cmp     [rcx+8], r14b
0x180031846  jz      short loc_180031869
0x180031848  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003184d  cmp     [rax+7CCh], ebx
0x180031853  jz      short loc_180031869
0x180031855  mov     r9d, ebx; int
0x180031858  mov     r8d, 0EAh; int
0x18003185e  mov     rdx, r15; char *
0x180031861  mov     rcx, rax; this
0x180031864  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031869  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031870  jb      loc_180032012
0x180031876  mov     edx, 21h ; '!'
0x18003187b  mov     [rsp+50h+var_30], ebx
0x18003187f  xor     r9d, r9d
0x180031882  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180031889  mov     rcx, cs:WPP_GLOBAL_Control
0x180031890  mov     rcx, [rcx+10h]
0x180031894  call    WPP_SF_qD
0x180031899  jmp     loc_180032012
0x18003189e  mov     [rsi], r14
0x1800318a1  mov     [rbp+arg_18], r14
0x1800318a5  mov     rdx, [rbx+58h]
0x1800318a9  lea     rcx, [rbp+var_20]
0x1800318ad  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z; MkvMfSourceLib::CodecFromIdString(char const *)
0x1800318b2  mov     ecx, [rbp+var_20]
0x1800318b5  cmp     ecx, 0Ch
0x1800318b8  jg      loc_180031BA4
0x1800318be  jz      loc_180031EB1
0x1800318c4  sub     ecx, 1
0x1800318c7  jz      loc_180031AF5
0x1800318cd  sub     ecx, 1
0x1800318d0  jz      loc_180031A46
0x1800318d6  sub     ecx, 4
0x1800318d9  jz      loc_1800319A0
0x1800318df  sub     ecx, 1
0x1800318e2  jz      loc_1800319A0
0x1800318e8  cmp     ecx, 1
0x1800318eb  jnz     loc_180031BD1
0x1800318f1  lea     rcx, [rbp+arg_18]
0x1800318f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800318fa  lea     r8, [rbp+arg_8]
0x1800318fe  lea     rdx, [rbp+arg_0]
0x180031902  lea     rcx, [rbp+arg_18]
0x180031906  call    ??$MakeAndInitialize@VMkvMfStreamVideoCodecPrivateAsUserData@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoCodecPrivateAsUserData,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18003190b  mov     ebx, eax
0x18003190d  test    eax, eax
0x18003190f  jns     loc_180031F62
0x180031915  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003191c  test    rcx, rcx
0x18003191f  jnz     short loc_180031962
0x180031921  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031927  mov     rcx, rax
0x18003192a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031931  test    rax, rax
0x180031934  jz      short loc_180031954
0x180031936  mov     rax, [rax]
0x180031939  mov     edx, 7F0h
0x18003193e  mov     rax, [rax+8]
0x180031942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031947  test    eax, eax
0x180031949  jz      short loc_180031954
0x18003194b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031952  jmp     short loc_180031962
0x180031954  lea     rcx, qword_1800D6F70; this
0x18003195b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031962  cmp     [rcx+8], r14b
0x180031966  jz      short loc_180031989
0x180031968  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003196d  cmp     [rax+7CCh], ebx
0x180031973  jz      short loc_180031989
0x180031975  mov     r9d, ebx; int
0x180031978  mov     r8d, 10Eh; int
0x18003197e  mov     rdx, r15; char *
0x180031981  mov     rcx, rax; this
0x180031984  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031989  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031990  jb      loc_180031EA3
0x180031996  mov     edx, 28h ; '('
0x18003199b  jmp     loc_180031E84
0x1800319a0  lea     r8, [rbp+arg_8]
0x1800319a4  lea     rdx, [rbp+arg_0]
0x1800319a8  lea     rcx, [rbp+arg_18]
0x1800319ac  call    ??$MakeAndInitialize@VMkvMfStreamVideoMPEG@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIMFMediaStream@@@WRL@Microsoft@@@012@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoMPEG,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFMediaStream>>,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x1800319b1  mov     ebx, eax
0x1800319b3  test    eax, eax
0x1800319b5  jns     loc_180031F62
0x1800319bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800319c2  test    rcx, rcx
0x1800319c5  jnz     short loc_180031A08
0x1800319c7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800319cd  mov     rcx, rax
0x1800319d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800319d7  test    rax, rax
0x1800319da  jz      short loc_1800319FA
0x1800319dc  mov     rax, [rax]
0x1800319df  mov     edx, 7F0h
0x1800319e4  mov     rax, [rax+8]
0x1800319e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319ed  test    eax, eax
0x1800319ef  jz      short loc_1800319FA
0x1800319f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800319f8  jmp     short loc_180031A08
0x1800319fa  lea     rcx, qword_1800D6F70; this
0x180031a01  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031a08  cmp     [rcx+8], r14b
0x180031a0c  jz      short loc_180031A2F
0x180031a0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031a13  cmp     [rax+7CCh], ebx
0x180031a19  jz      short loc_180031A2F
0x180031a1b  mov     r9d, ebx; int
0x180031a1e  mov     r8d, 0FFh; int
0x180031a24  mov     rdx, r15; char *
0x180031a27  mov     rcx, rax; this
0x180031a2a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031a2f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031a36  jb      loc_180031EA3
0x180031a3c  mov     edx, 24h ; '$'
0x180031a41  jmp     loc_180031E84
0x180031a46  lea     rcx, [rbp+arg_18]
0x180031a4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031a4f  lea     r8, [rbp+arg_8]
0x180031a53  lea     rdx, [rbp+arg_0]
0x180031a57  lea     rcx, [rbp+arg_18]
0x180031a5b  call    ??$MakeAndInitialize@VMkvMfStreamVFW@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVFW,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180031a60  mov     ebx, eax
0x180031a62  test    eax, eax
0x180031a64  jns     loc_180031F62
0x180031a6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031a71  test    rcx, rcx
0x180031a74  jnz     short loc_180031AB7
0x180031a76  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031a7c  mov     rcx, rax
0x180031a7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031a86  test    rax, rax
0x180031a89  jz      short loc_180031AA9
0x180031a8b  mov     rax, [rax]
0x180031a8e  mov     edx, 7F0h
0x180031a93  mov     rax, [rax+8]
0x180031a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a9c  test    eax, eax
0x180031a9e  jz      short loc_180031AA9
0x180031aa0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031aa7  jmp     short loc_180031AB7
0x180031aa9  lea     rcx, qword_1800D6F70; this
0x180031ab0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031ab7  cmp     [rcx+8], r14b
0x180031abb  jz      short loc_180031ADE
0x180031abd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031ac2  cmp     [rax+7CCh], ebx
0x180031ac8  jz      short loc_180031ADE
0x180031aca  mov     r9d, ebx; int
0x180031acd  mov     r8d, 0FBh; int
0x180031ad3  mov     rdx, r15; char *
0x180031ad6  mov     rcx, rax; this
0x180031ad9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031ade  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031ae5  jb      loc_180031EA3
0x180031aeb  mov     edx, 23h ; '#'
0x180031af0  jmp     loc_180031E84
0x180031af5  lea     rcx, [rbp+arg_18]
0x180031af9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031afe  lea     r8, [rbp+arg_8]
0x180031b02  lea     rdx, [rbp+arg_0]
0x180031b06  lea     rcx, [rbp+arg_18]
0x180031b0a  call    ??$MakeAndInitialize@VMkvMfStreamVideoStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180031b0f  mov     ebx, eax
0x180031b11  test    eax, eax
0x180031b13  jns     loc_180031F62
0x180031b19  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031b20  test    rcx, rcx
0x180031b23  jnz     short loc_180031B66
0x180031b25  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031b2b  mov     rcx, rax
0x180031b2e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031b35  test    rax, rax
0x180031b38  jz      short loc_180031B58
0x180031b3a  mov     rax, [rax]
0x180031b3d  mov     edx, 7F0h
0x180031b42  mov     rax, [rax+8]
0x180031b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b4b  test    eax, eax
0x180031b4d  jz      short loc_180031B58
0x180031b4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031b56  jmp     short loc_180031B66
0x180031b58  lea     rcx, qword_1800D6F70; this
0x180031b5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031b66  cmp     [rcx+8], r14b
0x180031b6a  jz      short loc_180031B8D
0x180031b6c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031b71  cmp     [rax+7CCh], ebx
0x180031b77  jz      short loc_180031B8D
0x180031b79  mov     r9d, ebx; int
0x180031b7c  mov     r8d, 111h; int
0x180031b82  mov     rdx, r15; char *
0x180031b85  mov     rcx, rax; this
0x180031b88  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031b8d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031b94  jb      loc_180031EA3
0x180031b9a  mov     edx, 29h ; ')'
0x180031b9f  jmp     loc_180031E84
0x180031ba4  sub     ecx, 0Dh
0x180031ba7  jz      loc_180031EB1
0x180031bad  sub     ecx, 1
0x180031bb0  jz      loc_180031EB1
0x180031bb6  sub     ecx, 1
0x180031bb9  jz      loc_180031DDE
0x180031bbf  sub     ecx, 1
0x180031bc2  jz      loc_180031D2F
0x180031bc8  cmp     ecx, 4
0x180031bcb  jz      loc_180031C80
0x180031bd1  lea     rcx, [rbp+arg_18]
0x180031bd5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031bda  lea     r8, [rbp+arg_8]
0x180031bde  lea     rdx, [rbp+arg_0]
0x180031be2  lea     rcx, [rbp+arg_18]
0x180031be6  call    ??$MakeAndInitialize@VMkvMfStreamVideo@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideo,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180031beb  mov     ebx, eax
0x180031bed  test    eax, eax
0x180031bef  jns     loc_180031F62
0x180031bf5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031bfc  test    rcx, rcx
0x180031bff  jnz     short loc_180031C42
0x180031c01  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031c07  mov     rcx, rax
0x180031c0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c11  test    rax, rax
0x180031c14  jz      short loc_180031C34
0x180031c16  mov     rax, [rax]
0x180031c19  mov     edx, 7F0h
0x180031c1e  mov     rax, [rax+8]
0x180031c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c27  test    eax, eax
0x180031c29  jz      short loc_180031C34
0x180031c2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c32  jmp     short loc_180031C42
0x180031c34  lea     rcx, qword_1800D6F70; this
0x180031c3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c42  cmp     [rcx+8], r14b
0x180031c46  jz      short loc_180031C69
0x180031c48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031c4d  cmp     [rax+7CCh], ebx
0x180031c53  jz      short loc_180031C69
0x180031c55  mov     r9d, ebx; int
0x180031c58  mov     r8d, 114h; int
0x180031c5e  mov     rdx, r15; char *
0x180031c61  mov     rcx, rax; this
0x180031c64  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031c69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180031c70  jb      loc_180031EA3
0x180031c76  mov     edx, 2Ah ; '*'
0x180031c7b  jmp     loc_180031E84
0x180031c80  lea     rcx, [rbp+arg_18]
0x180031c84  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180031c89  lea     r8, [rbp+arg_8]
0x180031c8d  lea     rdx, [rbp+arg_0]
0x180031c91  lea     rcx, [rbp+arg_18]
0x180031c95  call    ??$MakeAndInitialize@VMkvMfStreamVideoAV1@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoAV1,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180031c9a  mov     ebx, eax
0x180031c9c  test    eax, eax
0x180031c9e  jns     loc_180031F62
  ... truncated ...
```
