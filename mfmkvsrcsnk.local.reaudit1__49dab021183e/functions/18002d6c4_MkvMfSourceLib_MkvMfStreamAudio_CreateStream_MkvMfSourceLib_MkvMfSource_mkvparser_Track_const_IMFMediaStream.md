# MkvMfSourceLib::MkvMfStreamAudio::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x18002d6c4`
- end: `0x18002dd62`
- name: `?CreateStream@MkvMfStreamAudio@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `1694`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180011068`

## callees

- `0x180005c68`
- `0x180009b04`
- `0x18002d080`
- `0x18002d158`
- `0x18002d254`
- `0x18002d350`
- `0x18002d44c`
- `0x18002d548`
- `0x18002d6c4`
- `0x18004cc60`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d6f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d89a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002db0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dcc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d6f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d89a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d937`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002da71`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002db0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dbab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dc44`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dcc7`

## string_xrefs

- `0x18002d767`: `MkvMfSourceLib::MkvMfStreamAudio::CreateStream`
- `0x18002dd2f`: `MkvMfSourceLib::MkvMfStreamAudio::CreateStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MkvMfSourceLib::MkvMfStreamAudio::CreateStream(
        struct MkvMfSourceLib::MkvMfSource *a1,
        const struct mkvparser::Track *a2,
        struct IMFMediaStream **a3,
        __int64 a4)
{
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  int v7; // ebx
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v16; // r8d
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct IMFMediaStream *v31; // rax
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  _DWORD v35[8]; // [rsp+20h] [rbp-20h] BYREF
  struct MkvMfSourceLib::MkvMfSource *v36; // [rsp+60h] [rbp+20h] BYREF
  const struct mkvparser::Track *v37; // [rsp+68h] [rbp+28h] BYREF
  struct IMFMediaStream *v38; // [rsp+70h] [rbp+30h] BYREF

  v37 = a2;
  v36 = a1;
  if ( a3 )
  {
    *a3 = 0;
    v9 = *((_QWORD *)a2 + 11);
    v38 = 0;
    MkvMfSourceLib::CodecFromIdString(v35, v9);
    switch ( v35[0] )
    {
      case 1:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v29 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
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
          if ( !*((_BYTE *)v29 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 224;
          goto LABEL_98;
        }
        break;
      case 0x16:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v27 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 215;
          goto LABEL_98;
        }
        break;
      case 0x1A:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
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
          if ( !*((_BYTE *)v25 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 218;
          goto LABEL_98;
        }
        break;
      case 0x21:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioVorbis,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v23 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v23 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 209;
          goto LABEL_98;
        }
        break;
      case 0x22:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioFLAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v21 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v21 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v21 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v21 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 212;
          goto LABEL_98;
        }
        break;
      case 0x24:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioAAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
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
          if ( !*((_BYTE *)v19 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 206;
          goto LABEL_98;
        }
        break;
      case 0x26:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioMSACM,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v17 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 221;
          goto LABEL_98;
        }
        break;
      default:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        v7 = Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudio,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(
               &v38,
               &v36,
               &v37);
        if ( v7 < 0 )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
            CallStackTracing::s_wpInstance = v14;
            if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
            {
              v13 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v13 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( !*((_BYTE *)v13 + 8) )
            goto LABEL_100;
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)ThreadRelativeContext + 499) == v7 )
            goto LABEL_100;
          v16 = 227;
          goto LABEL_98;
        }
        break;
    }
    v31 = v38;
    if ( v38 )
    {
      v38 = 0;
      *a3 = v31;
      v7 = 0;
      goto LABEL_100;
    }
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v7 = -2147024882;
    if ( !*((_BYTE *)v32 + 8) )
      goto LABEL_100;
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
    if ( *((_DWORD *)ThreadRelativeContext + 499) == -2147024882 )
      goto LABEL_100;
    v16 = 232;
LABEL_98:
    CallStackContext::TraceFailure(ThreadRelativeContext, "MkvMfSourceLib::MkvMfStreamAudio::CreateStream", v16, v7);
LABEL_100:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    return (unsigned int)v7;
  }
  v5 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, a2, 0, a4);
    CallStackTracing::s_wpInstance = v6;
    if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
    {
      v5 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
    }
  }
  v7 = -2147467261;
  if ( *((_BYTE *)v5 + 8) )
  {
    v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
    if ( *((_DWORD *)v8 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v8, "MkvMfSourceLib::MkvMfStreamAudio::CreateStream", 193, -2147467261);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002d6c4  mov     [rsp-18h+arg_18], rbx
0x18002d6c9  mov     [rsp-18h+arg_8], rdx
0x18002d6ce  mov     [rsp-18h+arg_0], rcx
0x18002d6d3  push    rbp
0x18002d6d4  push    rsi
0x18002d6d5  push    rdi
0x18002d6d6  mov     rbp, rsp
0x18002d6d9  sub     rsp, 40h
0x18002d6dd  mov     rdi, r8
0x18002d6e0  xor     esi, esi
0x18002d6e2  test    r8, r8
0x18002d6e5  jnz     loc_18002D77B
0x18002d6eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d6f2  test    rcx, rcx
0x18002d6f5  jnz     short loc_18002D73E
0x18002d6f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d6fe  nop     dword ptr [rax+rax+00h]
0x18002d703  mov     rcx, rax
0x18002d706  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d70d  test    rax, rax
0x18002d710  jz      short loc_18002D730
0x18002d712  mov     rax, [rax]
0x18002d715  mov     edx, 7F0h
0x18002d71a  mov     rax, [rax+8]
0x18002d71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d723  test    eax, eax
0x18002d725  jz      short loc_18002D730
0x18002d727  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d72e  jmp     short loc_18002D73E
0x18002d730  lea     rcx, qword_1800DBF70; this
0x18002d737  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d73e  mov     ebx, 80004003h
0x18002d743  cmp     [rcx+8], sil
0x18002d747  jz      loc_18002DD52
0x18002d74d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d752  cmp     [rax+7CCh], ebx
0x18002d758  jz      loc_18002DD52
0x18002d75e  mov     r9d, ebx; int
0x18002d761  mov     r8d, 0C1h; int
0x18002d767  lea     rdx, aMkvmfsourcelib_67; "MkvMfSourceLib::MkvMfStreamAudio::Creat"...
0x18002d76e  mov     rcx, rax; this
0x18002d771  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002d776  jmp     loc_18002DD52
0x18002d77b  mov     [r8], rsi
0x18002d77e  mov     rdx, [rdx+58h]
0x18002d782  mov     [rbp+arg_10], rsi
0x18002d786  lea     rcx, [rbp+var_20]
0x18002d78a  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z; MkvMfSourceLib::CodecFromIdString(char const *)
0x18002d78f  mov     ecx, [rbp+var_20]
0x18002d792  sub     ecx, 1
0x18002d795  jz      loc_18002DC18
0x18002d79b  sub     ecx, 15h
0x18002d79e  jz      loc_18002DB7B
0x18002d7a4  sub     ecx, 4
0x18002d7a7  jz      loc_18002DADE
0x18002d7ad  sub     ecx, 7
0x18002d7b0  jz      loc_18002DA41
0x18002d7b6  sub     ecx, 1
0x18002d7b9  jz      loc_18002D9A4
0x18002d7bf  sub     ecx, 2
0x18002d7c2  jz      loc_18002D907
0x18002d7c8  cmp     ecx, 2
0x18002d7cb  lea     rcx, [rbp+arg_10]
0x18002d7cf  jz      loc_18002D86E
0x18002d7d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d7da  lea     r8, [rbp+arg_8]
0x18002d7de  lea     rdx, [rbp+arg_0]
0x18002d7e2  lea     rcx, [rbp+arg_10]
0x18002d7e6  call    ??$MakeAndInitialize@VMkvMfStreamAudio@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudio,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002d7eb  mov     ebx, eax
0x18002d7ed  test    eax, eax
0x18002d7ef  jns     loc_18002DCAE
0x18002d7f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d7fc  test    rcx, rcx
0x18002d7ff  jnz     short loc_18002D848
0x18002d801  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d808  nop     dword ptr [rax+rax+00h]
0x18002d80d  mov     rcx, rax
0x18002d810  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d817  test    rax, rax
0x18002d81a  jz      short loc_18002D83A
0x18002d81c  mov     rax, [rax]
0x18002d81f  mov     edx, 7F0h
0x18002d824  mov     rax, [rax+8]
0x18002d828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d82d  test    eax, eax
0x18002d82f  jz      short loc_18002D83A
0x18002d831  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d838  jmp     short loc_18002D848
0x18002d83a  lea     rcx, qword_1800DBF70; this
0x18002d841  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d848  cmp     [rcx+8], sil
0x18002d84c  jz      loc_18002DD49
0x18002d852  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d857  cmp     [rax+7CCh], ebx
0x18002d85d  jz      loc_18002DD49
0x18002d863  mov     r8d, 0E3h
0x18002d869  jmp     loc_18002DD2C
0x18002d86e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d873  lea     r8, [rbp+arg_8]
0x18002d877  lea     rdx, [rbp+arg_0]
0x18002d87b  lea     rcx, [rbp+arg_10]
0x18002d87f  call    ??$MakeAndInitialize@VMkvMfStreamAudioMSACM@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioMSACM,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002d884  mov     ebx, eax
0x18002d886  test    eax, eax
0x18002d888  jns     loc_18002DCAE
0x18002d88e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d895  test    rcx, rcx
0x18002d898  jnz     short loc_18002D8E1
0x18002d89a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d8a1  nop     dword ptr [rax+rax+00h]
0x18002d8a6  mov     rcx, rax
0x18002d8a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d8b0  test    rax, rax
0x18002d8b3  jz      short loc_18002D8D3
0x18002d8b5  mov     rax, [rax]
0x18002d8b8  mov     edx, 7F0h
0x18002d8bd  mov     rax, [rax+8]
0x18002d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8c6  test    eax, eax
0x18002d8c8  jz      short loc_18002D8D3
0x18002d8ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d8d1  jmp     short loc_18002D8E1
0x18002d8d3  lea     rcx, qword_1800DBF70; this
0x18002d8da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d8e1  cmp     [rcx+8], sil
0x18002d8e5  jz      loc_18002DD49
0x18002d8eb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d8f0  cmp     [rax+7CCh], ebx
0x18002d8f6  jz      loc_18002DD49
0x18002d8fc  mov     r8d, 0DDh
0x18002d902  jmp     loc_18002DD2C
0x18002d907  lea     rcx, [rbp+arg_10]
0x18002d90b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d910  lea     r8, [rbp+arg_8]
0x18002d914  lea     rdx, [rbp+arg_0]
0x18002d918  lea     rcx, [rbp+arg_10]
0x18002d91c  call    ??$MakeAndInitialize@VMkvMfStreamAudioAAC@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioAAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002d921  mov     ebx, eax
0x18002d923  test    eax, eax
0x18002d925  jns     loc_18002DCAE
0x18002d92b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d932  test    rcx, rcx
0x18002d935  jnz     short loc_18002D97E
0x18002d937  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d93e  nop     dword ptr [rax+rax+00h]
0x18002d943  mov     rcx, rax
0x18002d946  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d94d  test    rax, rax
0x18002d950  jz      short loc_18002D970
0x18002d952  mov     rax, [rax]
0x18002d955  mov     edx, 7F0h
0x18002d95a  mov     rax, [rax+8]
0x18002d95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d963  test    eax, eax
0x18002d965  jz      short loc_18002D970
0x18002d967  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d96e  jmp     short loc_18002D97E
0x18002d970  lea     rcx, qword_1800DBF70; this
0x18002d977  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d97e  cmp     [rcx+8], sil
0x18002d982  jz      loc_18002DD49
0x18002d988  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002d98d  cmp     [rax+7CCh], ebx
0x18002d993  jz      loc_18002DD49
0x18002d999  mov     r8d, 0CEh
0x18002d99f  jmp     loc_18002DD2C
0x18002d9a4  lea     rcx, [rbp+arg_10]
0x18002d9a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002d9ad  lea     r8, [rbp+arg_8]
0x18002d9b1  lea     rdx, [rbp+arg_0]
0x18002d9b5  lea     rcx, [rbp+arg_10]
0x18002d9b9  call    ??$MakeAndInitialize@VMkvMfStreamAudioFLAC@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioFLAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002d9be  mov     ebx, eax
0x18002d9c0  test    eax, eax
0x18002d9c2  jns     loc_18002DCAE
0x18002d9c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d9cf  test    rcx, rcx
0x18002d9d2  jnz     short loc_18002DA1B
0x18002d9d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002d9db  nop     dword ptr [rax+rax+00h]
0x18002d9e0  mov     rcx, rax
0x18002d9e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d9ea  test    rax, rax
0x18002d9ed  jz      short loc_18002DA0D
0x18002d9ef  mov     rax, [rax]
0x18002d9f2  mov     edx, 7F0h
0x18002d9f7  mov     rax, [rax+8]
0x18002d9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da00  test    eax, eax
0x18002da02  jz      short loc_18002DA0D
0x18002da04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da0b  jmp     short loc_18002DA1B
0x18002da0d  lea     rcx, qword_1800DBF70; this
0x18002da14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da1b  cmp     [rcx+8], sil
0x18002da1f  jz      loc_18002DD49
0x18002da25  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002da2a  cmp     [rax+7CCh], ebx
0x18002da30  jz      loc_18002DD49
0x18002da36  mov     r8d, 0D4h
0x18002da3c  jmp     loc_18002DD2C
0x18002da41  lea     rcx, [rbp+arg_10]
0x18002da45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002da4a  lea     r8, [rbp+arg_8]
0x18002da4e  lea     rdx, [rbp+arg_0]
0x18002da52  lea     rcx, [rbp+arg_10]
0x18002da56  call    ??$MakeAndInitialize@VMkvMfStreamAudioVorbis@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioVorbis,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002da5b  mov     ebx, eax
0x18002da5d  test    eax, eax
0x18002da5f  jns     loc_18002DCAE
0x18002da65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da6c  test    rcx, rcx
0x18002da6f  jnz     short loc_18002DAB8
0x18002da71  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002da78  nop     dword ptr [rax+rax+00h]
0x18002da7d  mov     rcx, rax
0x18002da80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002da87  test    rax, rax
0x18002da8a  jz      short loc_18002DAAA
0x18002da8c  mov     rax, [rax]
0x18002da8f  mov     edx, 7F0h
0x18002da94  mov     rax, [rax+8]
0x18002da98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da9d  test    eax, eax
0x18002da9f  jz      short loc_18002DAAA
0x18002daa1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002daa8  jmp     short loc_18002DAB8
0x18002daaa  lea     rcx, qword_1800DBF70; this
0x18002dab1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dab8  cmp     [rcx+8], sil
0x18002dabc  jz      loc_18002DD49
0x18002dac2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002dac7  cmp     [rax+7CCh], ebx
0x18002dacd  jz      loc_18002DD49
0x18002dad3  mov     r8d, 0D1h
0x18002dad9  jmp     loc_18002DD2C
0x18002dade  lea     rcx, [rbp+arg_10]
0x18002dae2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dae7  lea     r8, [rbp+arg_8]
0x18002daeb  lea     rdx, [rbp+arg_0]
0x18002daef  lea     rcx, [rbp+arg_10]
0x18002daf3  call    ??$MakeAndInitialize@VMkvMfStreamAudioStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002daf8  mov     ebx, eax
0x18002dafa  test    eax, eax
0x18002dafc  jns     loc_18002DCAE
0x18002db02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002db09  test    rcx, rcx
0x18002db0c  jnz     short loc_18002DB55
0x18002db0e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002db15  nop     dword ptr [rax+rax+00h]
0x18002db1a  mov     rcx, rax
0x18002db1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002db24  test    rax, rax
0x18002db27  jz      short loc_18002DB47
0x18002db29  mov     rax, [rax]
0x18002db2c  mov     edx, 7F0h
0x18002db31  mov     rax, [rax+8]
0x18002db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db3a  test    eax, eax
0x18002db3c  jz      short loc_18002DB47
0x18002db3e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002db45  jmp     short loc_18002DB55
0x18002db47  lea     rcx, qword_1800DBF70; this
0x18002db4e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002db55  cmp     [rcx+8], sil
0x18002db59  jz      loc_18002DD49
0x18002db5f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002db64  cmp     [rax+7CCh], ebx
0x18002db6a  jz      loc_18002DD49
0x18002db70  mov     r8d, 0DAh
0x18002db76  jmp     loc_18002DD2C
0x18002db7b  lea     rcx, [rbp+arg_10]
0x18002db7f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002db84  lea     r8, [rbp+arg_8]
0x18002db88  lea     rdx, [rbp+arg_0]
0x18002db8c  lea     rcx, [rbp+arg_10]
0x18002db90  call    ??$MakeAndInitialize@VMkvMfStreamAudioStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002db95  mov     ebx, eax
0x18002db97  test    eax, eax
0x18002db99  jns     loc_18002DCAE
0x18002db9f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dba6  test    rcx, rcx
0x18002dba9  jnz     short loc_18002DBF2
0x18002dbab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002dbb2  nop     dword ptr [rax+rax+00h]
0x18002dbb7  mov     rcx, rax
0x18002dbba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dbc1  test    rax, rax
0x18002dbc4  jz      short loc_18002DBE4
0x18002dbc6  mov     rax, [rax]
0x18002dbc9  mov     edx, 7F0h
0x18002dbce  mov     rax, [rax+8]
0x18002dbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbd7  test    eax, eax
0x18002dbd9  jz      short loc_18002DBE4
0x18002dbdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002dbe2  jmp     short loc_18002DBF2
0x18002dbe4  lea     rcx, qword_1800DBF70; this
0x18002dbeb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
