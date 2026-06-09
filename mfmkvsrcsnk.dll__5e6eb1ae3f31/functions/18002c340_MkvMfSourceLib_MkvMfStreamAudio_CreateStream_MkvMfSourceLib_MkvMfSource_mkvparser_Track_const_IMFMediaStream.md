# MkvMfSourceLib::MkvMfStreamAudio::CreateStream(MkvMfSourceLib::MkvMfSource *,mkvparser::Track const *,IMFMediaStream * *)

- ea: `0x18002c340`
- end: `0x18002c99d`
- name: `?CreateStream@MkvMfStreamAudio@MkvMfSourceLib@@SAJPEAVMkvMfSource@2@PEBVTrack@mkvparser@@PEAPEAUIMFMediaStream@@@Z`
- size: `1629`
- prototype: `__int64 __fastcall(struct MkvMfSourceLib::MkvMfSource *, const struct mkvparser::Track *, struct IMFMediaStream **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010940`

## callees

- `0x180005ab8`
- `0x1800097f0`
- `0x18002bcfc`
- `0x18002bdd4`
- `0x18002bed0`
- `0x18002bfcc`
- `0x18002c0c8`
- `0x18002c1c4`
- `0x18002c340`
- `0x18004acfc`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c373`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c477`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c50a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c5a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c6cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c766`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c7fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c890`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c909`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c373`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c477`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c50a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c5a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c6cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c766`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c7fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c890`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002c909`

## string_xrefs

- `0x18002c3dd`: `MkvMfSourceLib::MkvMfStreamAudio::CreateStream`
- `0x18002c96b`: `MkvMfSourceLib::MkvMfStreamAudio::CreateStream`

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
              v29 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v27 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v25 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v23 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v21 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v19 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v17 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v13 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v32 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      v5 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x18002c340  mov     [rsp-18h+arg_18], rbx
0x18002c345  mov     [rsp-18h+arg_8], rdx
0x18002c34a  mov     [rsp-18h+arg_0], rcx
0x18002c34f  push    rbp
0x18002c350  push    rsi
0x18002c351  push    rdi
0x18002c352  mov     rbp, rsp
0x18002c355  sub     rsp, 40h
0x18002c359  mov     rdi, r8
0x18002c35c  xor     esi, esi
0x18002c35e  test    r8, r8
0x18002c361  jnz     loc_18002C3F1
0x18002c367  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c36e  test    rcx, rcx
0x18002c371  jnz     short loc_18002C3B4
0x18002c373  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c379  mov     rcx, rax
0x18002c37c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c383  test    rax, rax
0x18002c386  jz      short loc_18002C3A6
0x18002c388  mov     rax, [rax]
0x18002c38b  mov     edx, 7F0h
0x18002c390  mov     rax, [rax+8]
0x18002c394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c399  test    eax, eax
0x18002c39b  jz      short loc_18002C3A6
0x18002c39d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c3a4  jmp     short loc_18002C3B4
0x18002c3a6  lea     rcx, qword_1800D6F70; this
0x18002c3ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c3b4  mov     ebx, 80004003h
0x18002c3b9  cmp     [rcx+8], sil
0x18002c3bd  jz      loc_18002C98E
0x18002c3c3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c3c8  cmp     [rax+7CCh], ebx
0x18002c3ce  jz      loc_18002C98E
0x18002c3d4  mov     r9d, ebx; int
0x18002c3d7  mov     r8d, 0C1h; int
0x18002c3dd  lea     rdx, aMkvmfsourcelib_67; "MkvMfSourceLib::MkvMfStreamAudio::Creat"...
0x18002c3e4  mov     rcx, rax; this
0x18002c3e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002c3ec  jmp     loc_18002C98E
0x18002c3f1  mov     [r8], rsi
0x18002c3f4  mov     rdx, [rdx+58h]
0x18002c3f8  mov     [rbp+arg_10], rsi
0x18002c3fc  lea     rcx, [rbp+var_20]
0x18002c400  call    ?CodecFromIdString@MkvMfSourceLib@@YA?AVMkvCodec@1@PEBD@Z; MkvMfSourceLib::CodecFromIdString(char const *)
0x18002c405  mov     ecx, [rbp+var_20]
0x18002c408  sub     ecx, 1
0x18002c40b  jz      loc_18002C864
0x18002c411  sub     ecx, 15h
0x18002c414  jz      loc_18002C7CD
0x18002c41a  sub     ecx, 4
0x18002c41d  jz      loc_18002C736
0x18002c423  sub     ecx, 7
0x18002c426  jz      loc_18002C69F
0x18002c42c  sub     ecx, 1
0x18002c42f  jz      loc_18002C608
0x18002c435  sub     ecx, 2
0x18002c438  jz      loc_18002C571
0x18002c43e  cmp     ecx, 2
0x18002c441  lea     rcx, [rbp+arg_10]
0x18002c445  jz      loc_18002C4DE
0x18002c44b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c450  lea     r8, [rbp+arg_8]
0x18002c454  lea     rdx, [rbp+arg_0]
0x18002c458  lea     rcx, [rbp+arg_10]
0x18002c45c  call    ??$MakeAndInitialize@VMkvMfStreamAudio@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudio,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c461  mov     ebx, eax
0x18002c463  test    eax, eax
0x18002c465  jns     loc_18002C8F4
0x18002c46b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c472  test    rcx, rcx
0x18002c475  jnz     short loc_18002C4B8
0x18002c477  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c47d  mov     rcx, rax
0x18002c480  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c487  test    rax, rax
0x18002c48a  jz      short loc_18002C4AA
0x18002c48c  mov     rax, [rax]
0x18002c48f  mov     edx, 7F0h
0x18002c494  mov     rax, [rax+8]
0x18002c498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c49d  test    eax, eax
0x18002c49f  jz      short loc_18002C4AA
0x18002c4a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c4a8  jmp     short loc_18002C4B8
0x18002c4aa  lea     rcx, qword_1800D6F70; this
0x18002c4b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c4b8  cmp     [rcx+8], sil
0x18002c4bc  jz      loc_18002C985
0x18002c4c2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c4c7  cmp     [rax+7CCh], ebx
0x18002c4cd  jz      loc_18002C985
0x18002c4d3  mov     r8d, 0E3h
0x18002c4d9  jmp     loc_18002C968
0x18002c4de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c4e3  lea     r8, [rbp+arg_8]
0x18002c4e7  lea     rdx, [rbp+arg_0]
0x18002c4eb  lea     rcx, [rbp+arg_10]
0x18002c4ef  call    ??$MakeAndInitialize@VMkvMfStreamAudioMSACM@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioMSACM,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c4f4  mov     ebx, eax
0x18002c4f6  test    eax, eax
0x18002c4f8  jns     loc_18002C8F4
0x18002c4fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c505  test    rcx, rcx
0x18002c508  jnz     short loc_18002C54B
0x18002c50a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c510  mov     rcx, rax
0x18002c513  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c51a  test    rax, rax
0x18002c51d  jz      short loc_18002C53D
0x18002c51f  mov     rax, [rax]
0x18002c522  mov     edx, 7F0h
0x18002c527  mov     rax, [rax+8]
0x18002c52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c530  test    eax, eax
0x18002c532  jz      short loc_18002C53D
0x18002c534  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c53b  jmp     short loc_18002C54B
0x18002c53d  lea     rcx, qword_1800D6F70; this
0x18002c544  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c54b  cmp     [rcx+8], sil
0x18002c54f  jz      loc_18002C985
0x18002c555  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c55a  cmp     [rax+7CCh], ebx
0x18002c560  jz      loc_18002C985
0x18002c566  mov     r8d, 0DDh
0x18002c56c  jmp     loc_18002C968
0x18002c571  lea     rcx, [rbp+arg_10]
0x18002c575  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c57a  lea     r8, [rbp+arg_8]
0x18002c57e  lea     rdx, [rbp+arg_0]
0x18002c582  lea     rcx, [rbp+arg_10]
0x18002c586  call    ??$MakeAndInitialize@VMkvMfStreamAudioAAC@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioAAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c58b  mov     ebx, eax
0x18002c58d  test    eax, eax
0x18002c58f  jns     loc_18002C8F4
0x18002c595  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c59c  test    rcx, rcx
0x18002c59f  jnz     short loc_18002C5E2
0x18002c5a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c5a7  mov     rcx, rax
0x18002c5aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5b1  test    rax, rax
0x18002c5b4  jz      short loc_18002C5D4
0x18002c5b6  mov     rax, [rax]
0x18002c5b9  mov     edx, 7F0h
0x18002c5be  mov     rax, [rax+8]
0x18002c5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c5c7  test    eax, eax
0x18002c5c9  jz      short loc_18002C5D4
0x18002c5cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5d2  jmp     short loc_18002C5E2
0x18002c5d4  lea     rcx, qword_1800D6F70; this
0x18002c5db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c5e2  cmp     [rcx+8], sil
0x18002c5e6  jz      loc_18002C985
0x18002c5ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c5f1  cmp     [rax+7CCh], ebx
0x18002c5f7  jz      loc_18002C985
0x18002c5fd  mov     r8d, 0CEh
0x18002c603  jmp     loc_18002C968
0x18002c608  lea     rcx, [rbp+arg_10]
0x18002c60c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c611  lea     r8, [rbp+arg_8]
0x18002c615  lea     rdx, [rbp+arg_0]
0x18002c619  lea     rcx, [rbp+arg_10]
0x18002c61d  call    ??$MakeAndInitialize@VMkvMfStreamAudioFLAC@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioFLAC,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c622  mov     ebx, eax
0x18002c624  test    eax, eax
0x18002c626  jns     loc_18002C8F4
0x18002c62c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c633  test    rcx, rcx
0x18002c636  jnz     short loc_18002C679
0x18002c638  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c63e  mov     rcx, rax
0x18002c641  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c648  test    rax, rax
0x18002c64b  jz      short loc_18002C66B
0x18002c64d  mov     rax, [rax]
0x18002c650  mov     edx, 7F0h
0x18002c655  mov     rax, [rax+8]
0x18002c659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c65e  test    eax, eax
0x18002c660  jz      short loc_18002C66B
0x18002c662  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c669  jmp     short loc_18002C679
0x18002c66b  lea     rcx, qword_1800D6F70; this
0x18002c672  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c679  cmp     [rcx+8], sil
0x18002c67d  jz      loc_18002C985
0x18002c683  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c688  cmp     [rax+7CCh], ebx
0x18002c68e  jz      loc_18002C985
0x18002c694  mov     r8d, 0D4h
0x18002c69a  jmp     loc_18002C968
0x18002c69f  lea     rcx, [rbp+arg_10]
0x18002c6a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c6a8  lea     r8, [rbp+arg_8]
0x18002c6ac  lea     rdx, [rbp+arg_0]
0x18002c6b0  lea     rcx, [rbp+arg_10]
0x18002c6b4  call    ??$MakeAndInitialize@VMkvMfStreamAudioVorbis@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioVorbis,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c6b9  mov     ebx, eax
0x18002c6bb  test    eax, eax
0x18002c6bd  jns     loc_18002C8F4
0x18002c6c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c6ca  test    rcx, rcx
0x18002c6cd  jnz     short loc_18002C710
0x18002c6cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c6d5  mov     rcx, rax
0x18002c6d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c6df  test    rax, rax
0x18002c6e2  jz      short loc_18002C702
0x18002c6e4  mov     rax, [rax]
0x18002c6e7  mov     edx, 7F0h
0x18002c6ec  mov     rax, [rax+8]
0x18002c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6f5  test    eax, eax
0x18002c6f7  jz      short loc_18002C702
0x18002c6f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c700  jmp     short loc_18002C710
0x18002c702  lea     rcx, qword_1800D6F70; this
0x18002c709  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c710  cmp     [rcx+8], sil
0x18002c714  jz      loc_18002C985
0x18002c71a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c71f  cmp     [rax+7CCh], ebx
0x18002c725  jz      loc_18002C985
0x18002c72b  mov     r8d, 0D1h
0x18002c731  jmp     loc_18002C968
0x18002c736  lea     rcx, [rbp+arg_10]
0x18002c73a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c73f  lea     r8, [rbp+arg_8]
0x18002c743  lea     rdx, [rbp+arg_0]
0x18002c747  lea     rcx, [rbp+arg_10]
0x18002c74b  call    ??$MakeAndInitialize@VMkvMfStreamAudioStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c750  mov     ebx, eax
0x18002c752  test    eax, eax
0x18002c754  jns     loc_18002C8F4
0x18002c75a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c761  test    rcx, rcx
0x18002c764  jnz     short loc_18002C7A7
0x18002c766  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c76c  mov     rcx, rax
0x18002c76f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c776  test    rax, rax
0x18002c779  jz      short loc_18002C799
0x18002c77b  mov     rax, [rax]
0x18002c77e  mov     edx, 7F0h
0x18002c783  mov     rax, [rax+8]
0x18002c787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c78c  test    eax, eax
0x18002c78e  jz      short loc_18002C799
0x18002c790  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c797  jmp     short loc_18002C7A7
0x18002c799  lea     rcx, qword_1800D6F70; this
0x18002c7a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c7a7  cmp     [rcx+8], sil
0x18002c7ab  jz      loc_18002C985
0x18002c7b1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c7b6  cmp     [rax+7CCh], ebx
0x18002c7bc  jz      loc_18002C985
0x18002c7c2  mov     r8d, 0DAh
0x18002c7c8  jmp     loc_18002C968
0x18002c7cd  lea     rcx, [rbp+arg_10]
0x18002c7d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c7d6  lea     r8, [rbp+arg_8]
0x18002c7da  lea     rdx, [rbp+arg_0]
0x18002c7de  lea     rcx, [rbp+arg_10]
0x18002c7e2  call    ??$MakeAndInitialize@VMkvMfStreamAudioStoreCodec@MkvMfSourceLib@@UIMFMediaStream@@AEAPEAVMkvMfSource@2@AEAPEBVTrack@mkvparser@@@Details@WRL@Microsoft@@YAJPEAPEAUIMFMediaStream@@AEAPEAVMkvMfSource@MkvMfSourceLib@@AEAPEBVTrack@mkvparser@@@Z; Microsoft::WRL::Details::MakeAndInitialize<MkvMfSourceLib::MkvMfStreamAudioStoreCodec,IMFMediaStream,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &>(IMFMediaStream * *,MkvMfSourceLib::MkvMfSource * &,mkvparser::Track const * &)
0x18002c7e7  mov     ebx, eax
0x18002c7e9  test    eax, eax
0x18002c7eb  jns     loc_18002C8F4
0x18002c7f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c7f8  test    rcx, rcx
0x18002c7fb  jnz     short loc_18002C83E
0x18002c7fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002c803  mov     rcx, rax
0x18002c806  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c80d  test    rax, rax
0x18002c810  jz      short loc_18002C830
0x18002c812  mov     rax, [rax]
0x18002c815  mov     edx, 7F0h
0x18002c81a  mov     rax, [rax+8]
0x18002c81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c823  test    eax, eax
0x18002c825  jz      short loc_18002C830
0x18002c827  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c82e  jmp     short loc_18002C83E
0x18002c830  lea     rcx, qword_1800D6F70; this
0x18002c837  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002c83e  cmp     [rcx+8], sil
0x18002c842  jz      loc_18002C985
0x18002c848  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002c84d  cmp     [rax+7CCh], ebx
0x18002c853  jz      loc_18002C985
0x18002c859  mov     r8d, 0D7h
0x18002c85f  jmp     loc_18002C968
0x18002c864  lea     rcx, [rbp+arg_10]
  ... truncated ...
```
