# MkvMfSourceLib::MkvMfStreamVideo::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x180032dbc`
- end: `0x18003367c`
- name: `?CreateStream@MkvMfStreamVideo@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `2240`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180011068`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180032204`
- `0x180032300`
- `0x1800323d8`
- `0x1800324e8`
- `0x1800325c0`
- `0x180032698`
- `0x180032898`
- `0x1800328d8`
- `0x180032dbc`
- `0x18004cc60`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032fe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033098`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003314d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003322f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003344e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003351e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800335c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032e0c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032f37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180032fe3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033098`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003314d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003322f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800332e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180033399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003344e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003351e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800335c7`

## string_xrefs

- `0x180032de0`: `MkvMfSourceLib::MkvMfStreamVideo::CreateStream`

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
                  v37 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v34 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                  v31 = &qword_1800DBF70;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v25 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v22 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v19 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
                v15 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v44 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            v28 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v40 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      v8 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180032dbc  mov     [rsp-28h+arg_8], rdx
0x180032dc1  mov     [rsp-28h+arg_0], rcx
0x180032dc6  push    rbp
0x180032dc7  push    rbx
0x180032dc8  push    rsi
0x180032dc9  push    r14
0x180032dcb  push    r15
0x180032dcd  mov     rbp, rsp
0x180032dd0  sub     rsp, 50h
0x180032dd4  mov     rsi, r8
0x180032dd7  mov     rbx, rdx
0x180032dda  mov     r8d, 0EAh; int
0x180032de0  lea     r15, aMkvmfsourcelib_11; "MkvMfSourceLib::MkvMfStreamVideo::Creat"...
0x180032de7  mov     rdx, r15; char *
0x180032dea  lea     rcx, [rbp+arg_10]; this
0x180032dee  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180032df3  nop
0x180032df4  xor     r14d, r14d
0x180032df7  test    rsi, rsi
0x180032dfa  jnz     loc_180032EB4
0x180032e00  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e07  test    rcx, rcx
0x180032e0a  jnz     short loc_180032E53
0x180032e0c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032e13  nop     dword ptr [rax+rax+00h]
0x180032e18  mov     rcx, rax
0x180032e1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e22  test    rax, rax
0x180032e25  jz      short loc_180032E45
0x180032e27  mov     rax, [rax]
0x180032e2a  mov     edx, 7F0h
0x180032e2f  mov     rax, [rax+8]
0x180032e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e38  test    eax, eax
0x180032e3a  jz      short loc_180032E45
0x180032e3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e43  jmp     short loc_180032E53
0x180032e45  lea     rcx, qword_1800DBF70; this
0x180032e4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032e53  mov     ebx, 80004003h
0x180032e58  cmp     [rcx+8], r14b
0x180032e5c  jz      short loc_180032E7F
0x180032e5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032e63  cmp     [rax+7CCh], ebx
0x180032e69  jz      short loc_180032E7F
0x180032e6b  mov     r9d, ebx; int
0x180032e6e  mov     r8d, 0EAh; int
0x180032e74  mov     rdx, r15; char *
0x180032e77  mov     rcx, rax; this
0x180032e7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032e7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032e86  jb      loc_180033664
0x180032e8c  mov     edx, 21h ; '!'
0x180032e91  mov     [rsp+50h+var_30], ebx
0x180032e95  xor     r9d, r9d
0x180032e98  lea     r8, WPP_b0f450d3db7535e612483e5f7f8b7661_Traceguids
0x180032e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ea6  mov     rcx, [rcx+10h]
0x180032eaa  call    WPP_SF_qD
0x180032eaf  jmp     loc_180033664
0x180032eb4  mov     [rsi], r14
0x180032eb7  mov     [rbp+arg_18], r14
0x180032ebb  mov     rdx, [rbx+58h]
0x180032ebf  lea     rcx, [rbp+var_20]
0x180032ec3  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z; MkvMfSourceLib::CodecFromIdString(char const *)
0x180032ec8  mov     ecx, [rbp+var_20]
0x180032ecb  cmp     ecx, 0Ch
0x180032ece  jg      loc_1800331D2
0x180032ed4  jz      loc_1800334F7
0x180032eda  sub     ecx, 1
0x180032edd  jz      loc_18003311D
0x180032ee3  sub     ecx, 1
0x180032ee6  jz      loc_180033068
0x180032eec  sub     ecx, 4
0x180032eef  jz      loc_180032FBC
0x180032ef5  sub     ecx, 1
0x180032ef8  jz      loc_180032FBC
0x180032efe  cmp     ecx, 1
0x180032f01  jnz     loc_1800331FF
0x180032f07  lea     rcx, [rbp+arg_18]
0x180032f0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032f10  lea     r8, [rbp+arg_8]
0x180032f14  lea     rdx, [rbp+arg_0]
0x180032f18  lea     rcx, [rbp+arg_18]
0x180032f1c  call    ??$MakeAndInitialize@VMkvMfStreamVideoCodecPrivateAsUserData@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoCodecPrivateAsUserData,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180032f21  mov     ebx, eax
0x180032f23  test    eax, eax
0x180032f25  jns     loc_1800335AE
0x180032f2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f32  test    rcx, rcx
0x180032f35  jnz     short loc_180032F7E
0x180032f37  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032f3e  nop     dword ptr [rax+rax+00h]
0x180032f43  mov     rcx, rax
0x180032f46  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f4d  test    rax, rax
0x180032f50  jz      short loc_180032F70
0x180032f52  mov     rax, [rax]
0x180032f55  mov     edx, 7F0h
0x180032f5a  mov     rax, [rax+8]
0x180032f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f63  test    eax, eax
0x180032f65  jz      short loc_180032F70
0x180032f67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f6e  jmp     short loc_180032F7E
0x180032f70  lea     rcx, qword_1800DBF70; this
0x180032f77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180032f7e  cmp     [rcx+8], r14b
0x180032f82  jz      short loc_180032FA5
0x180032f84  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180032f89  cmp     [rax+7CCh], ebx
0x180032f8f  jz      short loc_180032FA5
0x180032f91  mov     r9d, ebx; int
0x180032f94  mov     r8d, 10Eh; int
0x180032f9a  mov     rdx, r15; char *
0x180032f9d  mov     rcx, rax; this
0x180032fa0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180032fa5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180032fac  jb      loc_1800334E9
0x180032fb2  mov     edx, 28h ; '('
0x180032fb7  jmp     loc_1800334CA
0x180032fbc  lea     r8, [rbp+arg_8]
0x180032fc0  lea     rdx, [rbp+arg_0]
0x180032fc4  lea     rcx, [rbp+arg_18]
0x180032fc8  call    ??$MakeAndInitialize@VMkvMfStreamVideoMPEG@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIMFMediaStream@@@WRL@Microsoft@@@012@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoMPEG,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFMediaStream>>,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180032fcd  mov     ebx, eax
0x180032fcf  test    eax, eax
0x180032fd1  jns     loc_1800335AE
0x180032fd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180032fde  test    rcx, rcx
0x180032fe1  jnz     short loc_18003302A
0x180032fe3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180032fea  nop     dword ptr [rax+rax+00h]
0x180032fef  mov     rcx, rax
0x180032ff2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180032ff9  test    rax, rax
0x180032ffc  jz      short loc_18003301C
0x180032ffe  mov     rax, [rax]
0x180033001  mov     edx, 7F0h
0x180033006  mov     rax, [rax+8]
0x18003300a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003300f  test    eax, eax
0x180033011  jz      short loc_18003301C
0x180033013  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003301a  jmp     short loc_18003302A
0x18003301c  lea     rcx, qword_1800DBF70; this
0x180033023  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003302a  cmp     [rcx+8], r14b
0x18003302e  jz      short loc_180033051
0x180033030  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033035  cmp     [rax+7CCh], ebx
0x18003303b  jz      short loc_180033051
0x18003303d  mov     r9d, ebx; int
0x180033040  mov     r8d, 0FFh; int
0x180033046  mov     rdx, r15; char *
0x180033049  mov     rcx, rax; this
0x18003304c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033051  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033058  jb      loc_1800334E9
0x18003305e  mov     edx, 24h ; '$'
0x180033063  jmp     loc_1800334CA
0x180033068  lea     rcx, [rbp+arg_18]
0x18003306c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033071  lea     r8, [rbp+arg_8]
0x180033075  lea     rdx, [rbp+arg_0]
0x180033079  lea     rcx, [rbp+arg_18]
0x18003307d  call    ??$MakeAndInitialize@VMkvMfStreamVFW@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVFW,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180033082  mov     ebx, eax
0x180033084  test    eax, eax
0x180033086  jns     loc_1800335AE
0x18003308c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033093  test    rcx, rcx
0x180033096  jnz     short loc_1800330DF
0x180033098  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003309f  nop     dword ptr [rax+rax+00h]
0x1800330a4  mov     rcx, rax
0x1800330a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800330ae  test    rax, rax
0x1800330b1  jz      short loc_1800330D1
0x1800330b3  mov     rax, [rax]
0x1800330b6  mov     edx, 7F0h
0x1800330bb  mov     rax, [rax+8]
0x1800330bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330c4  test    eax, eax
0x1800330c6  jz      short loc_1800330D1
0x1800330c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800330cf  jmp     short loc_1800330DF
0x1800330d1  lea     rcx, qword_1800DBF70; this
0x1800330d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800330df  cmp     [rcx+8], r14b
0x1800330e3  jz      short loc_180033106
0x1800330e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800330ea  cmp     [rax+7CCh], ebx
0x1800330f0  jz      short loc_180033106
0x1800330f2  mov     r9d, ebx; int
0x1800330f5  mov     r8d, 0FBh; int
0x1800330fb  mov     rdx, r15; char *
0x1800330fe  mov     rcx, rax; this
0x180033101  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180033106  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003310d  jb      loc_1800334E9
0x180033113  mov     edx, 23h ; '#'
0x180033118  jmp     loc_1800334CA
0x18003311d  lea     rcx, [rbp+arg_18]
0x180033121  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033126  lea     r8, [rbp+arg_8]
0x18003312a  lea     rdx, [rbp+arg_0]
0x18003312e  lea     rcx, [rbp+arg_18]
0x180033132  call    ??$MakeAndInitialize@VMkvMfStreamVideoStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideoStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180033137  mov     ebx, eax
0x180033139  test    eax, eax
0x18003313b  jns     loc_1800335AE
0x180033141  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033148  test    rcx, rcx
0x18003314b  jnz     short loc_180033194
0x18003314d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033154  nop     dword ptr [rax+rax+00h]
0x180033159  mov     rcx, rax
0x18003315c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033163  test    rax, rax
0x180033166  jz      short loc_180033186
0x180033168  mov     rax, [rax]
0x18003316b  mov     edx, 7F0h
0x180033170  mov     rax, [rax+8]
0x180033174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033179  test    eax, eax
0x18003317b  jz      short loc_180033186
0x18003317d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033184  jmp     short loc_180033194
0x180033186  lea     rcx, qword_1800DBF70; this
0x18003318d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033194  cmp     [rcx+8], r14b
0x180033198  jz      short loc_1800331BB
0x18003319a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003319f  cmp     [rax+7CCh], ebx
0x1800331a5  jz      short loc_1800331BB
0x1800331a7  mov     r9d, ebx; int
0x1800331aa  mov     r8d, 111h; int
0x1800331b0  mov     rdx, r15; char *
0x1800331b3  mov     rcx, rax; this
0x1800331b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800331bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800331c2  jb      loc_1800334E9
0x1800331c8  mov     edx, 29h ; ')'
0x1800331cd  jmp     loc_1800334CA
0x1800331d2  sub     ecx, 0Dh
0x1800331d5  jz      loc_1800334F7
0x1800331db  sub     ecx, 1
0x1800331de  jz      loc_1800334F7
0x1800331e4  sub     ecx, 1
0x1800331e7  jz      loc_18003341E
0x1800331ed  sub     ecx, 1
0x1800331f0  jz      loc_180033369
0x1800331f6  cmp     ecx, 4
0x1800331f9  jz      loc_1800332B4
0x1800331ff  lea     rcx, [rbp+arg_18]
0x180033203  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180033208  lea     r8, [rbp+arg_8]
0x18003320c  lea     rdx, [rbp+arg_0]
0x180033210  lea     rcx, [rbp+arg_18]
0x180033214  call    ??$MakeAndInitialize@VMkvMfStreamVideo@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamVideo,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x180033219  mov     ebx, eax
0x18003321b  test    eax, eax
0x18003321d  jns     loc_1800335AE
0x180033223  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003322a  test    rcx, rcx
0x18003322d  jnz     short loc_180033276
0x18003322f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180033236  nop     dword ptr [rax+rax+00h]
0x18003323b  mov     rcx, rax
0x18003323e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180033245  test    rax, rax
0x180033248  jz      short loc_180033268
0x18003324a  mov     rax, [rax]
0x18003324d  mov     edx, 7F0h
0x180033252  mov     rax, [rax+8]
0x180033256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003325b  test    eax, eax
0x18003325d  jz      short loc_180033268
0x18003325f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180033266  jmp     short loc_180033276
0x180033268  lea     rcx, qword_1800DBF70; this
0x18003326f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180033276  cmp     [rcx+8], r14b
0x18003327a  jz      short loc_18003329D
0x18003327c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180033281  cmp     [rax+7CCh], ebx
0x180033287  jz      short loc_18003329D
0x180033289  mov     r9d, ebx; int
0x18003328c  mov     r8d, 114h; int
0x180033292  mov     rdx, r15; char *
0x180033295  mov     rcx, rax; this
0x180033298  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003329d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800332a4  jb      loc_1800334E9
0x1800332aa  mov     edx, 2Ah ; '*'
0x1800332af  jmp     loc_1800334CA
0x1800332b4  lea     rcx, [rbp+arg_18]
0x1800332b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800332bd  lea     r8, [rbp+arg_8]
  ... truncated ...
```
