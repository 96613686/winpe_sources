# CMP3BytewiseMediaSource::OnID3v1FooterRead(IMFAsyncResult *)

- ea: `0x1800f99b8`
- end: `0x1800fa1fe`
- name: `?OnID3v1FooterRead@CMP3BytewiseMediaSource@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2118`
- prototype: `void __fastcall(CMP3BytewiseMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801564c0`

## callees

- `0x180005cf4`
- `0x18001afb8`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180020c04`
- `0x180024890`
- `0x180036c30`
- `0x18004e918`
- `0x18005189c`
- `0x180055970`
- `0x180079680`
- `0x18009e630`
- `0x1800f99b8`
- `0x180110ed0`
- `0x180121750`
- `0x1801729e0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fa1c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fa1c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f9a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f9a67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9abc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9ba9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9d10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9db7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9eac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9f8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fa04e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fa11c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9abc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9ba9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9d10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9db7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9eac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f9f8f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fa04e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fa11c`

## string_xrefs

- `0x1800f99e3`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9b1e`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9c07`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9d6d`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9e14`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9f09`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f9fec`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800fa0ab`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800fa179`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`

## pseudocode

```c
void __fastcall CMP3BytewiseMediaSource::OnID3v1FooterRead(CMP3BytewiseMediaSource *this, struct IMFAsyncResult *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  __int64 v7; // rdx
  CMP3Base *v8; // rdi
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r14d
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  CByteStreamCacheReaderEx **v15; // rbx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  int MP3Metadata; // edi
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  int NextFrame; // ebx
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  bool v43; // zf
  __int64 v44; // rdx
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  _BYTE v52[8]; // [rsp+30h] [rbp-30h] BYREF
  CMP3Base *v53; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v54[2]; // [rsp+40h] [rbp-20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v52,
    "CMP3BytewiseMediaSource::OnID3v1FooterRead",
    3176);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 139) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 139) + 280LL))(
                      *((_QWORD *)this + 139),
                      v54);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v7 = *((_QWORD *)this + 121);
  *((_DWORD *)this + 248) = 0;
  ComSmartPtr<CID3Footer>::ComSmartPtr<CID3Footer>(&v53, v7);
  v8 = v53;
  v9 = CMP3Base::EndDeSerialize(v53, a2);
  v11 = v9;
  if ( !*((_DWORD *)this + 49) )
  {
    v15 = (CByteStreamCacheReaderEx **)((char *)this + 1024);
    CByteStreamCacheReaderEx::PopPosition(*((CByteStreamCacheReaderEx **)this + 128), v9 >= 0);
    if ( v11 != -1072873850 )
    {
      if ( v11 >= 0 )
      {
        if ( v8 )
        {
          (*(void (__fastcall **)(CMP3Base *))(*(_QWORD *)v8 + 8LL))(v8);
          v21 = *((_QWORD *)this + 109);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          *((_QWORD *)this + 109) = v8;
        }
        else
        {
          v20 = *((_QWORD *)this + 109);
          if ( v20 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            *((_QWORD *)this + 109) = 0;
          }
          v8 = 0;
        }
        if ( !*((_DWORD *)this + 236) || *((_QWORD *)this + 108) != -1 )
          *((_QWORD *)this + 101) = *((_QWORD *)v8 + 3);
        if ( !*((_QWORD *)this + 116) )
          goto LABEL_63;
        v22 = *(_QWORD **)this;
        v54[0] = 0;
        if ( ((int (__fastcall *)(CMP3BytewiseMediaSource *, _QWORD *))v22[15])(this, v54) < 0
          || (MP3Metadata = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(**((_QWORD **)this + 30) + 176LL))(
                              *((_QWORD *)this + 30),
                              &MF_PD_DURATION,
                              v54[0]),
              MP3Metadata >= 0) )
        {
          MP3Metadata = CMP3BytewiseMediaSource::CreateMP3Metadata(this);
          if ( MP3Metadata >= 0 )
            goto LABEL_63;
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
            if ( *((_DWORD *)v32 + 499) != MP3Metadata )
              CallStackContext::TraceFailure(v32, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3240, MP3Metadata);
          }
          if ( !g_wppLevels )
            goto LABEL_63;
          v28 = 278;
        }
        else
        {
          v25 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != MP3Metadata )
              CallStackContext::TraceFailure(v27, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3232, MP3Metadata);
          }
          if ( !g_wppLevels )
            goto LABEL_63;
          v28 = 277;
        }
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v28,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          this,
          MP3Metadata);
      }
      else
      {
        v17 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)v19 + 499) != v11 )
            CallStackContext::TraceFailure(v19, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3203, v11);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            276,
            &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
            this,
            v11);
      }
    }
LABEL_63:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v53);
    goto LABEL_64;
  }
  v12 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)v14 + 499) != -1072873851 )
      CallStackContext::TraceFailure(v14, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3194, -1072873851);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      275,
      &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
      this,
      -1072873851);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v53);
  v15 = (CByteStreamCacheReaderEx **)((char *)this + 1024);
LABEL_64:
  if ( *((_DWORD *)this + 236) )
  {
    if ( *((_QWORD *)this + 108) == -1 )
    {
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 284, &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids, this);
      NextFrame = CMP3BytewiseMediaSource::ReadNextFrame(this);
      if ( NextFrame < 0 )
      {
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
          CallStackTracing::s_wpInstance = v50;
          if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
          {
            v49 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v49 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v49 + 8) )
        {
          v51 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
          if ( *((_DWORD *)v51 + 499) != NextFrame )
            CallStackContext::TraceFailure(v51, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3298, NextFrame);
        }
        if ( g_wppLevels )
        {
          v38 = 285;
          goto LABEL_117;
        }
      }
    }
    else
    {
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 281, &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids, this);
      NextFrame = CByteStreamCacheReaderEx::SetCurrentPosition(*v15, *((_QWORD *)this + 108));
      if ( NextFrame >= 0 )
      {
        v43 = *((_DWORD *)this + 50) == 1;
        *((_QWORD *)this + 108) = -1;
        if ( v43 )
        {
          NextFrame = CMP3BytewiseMediaSource::ReadNextFrame(this);
          if ( NextFrame < 0 )
          {
            v45 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
              CallStackTracing::s_wpInstance = v46;
              if ( v46
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
              {
                v45 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v45 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v45 + 8) )
            {
              v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
              if ( *((_DWORD *)v47 + 499) != NextFrame )
                CallStackContext::TraceFailure(v47, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3287, NextFrame);
            }
            if ( g_wppLevels )
            {
              v38 = 283;
              goto LABEL_117;
            }
          }
        }
      }
      else
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != NextFrame )
            CallStackContext::TraceFailure(v42, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3280, NextFrame);
        }
        if ( g_wppLevels )
        {
          v38 = 282;
          goto LABEL_117;
        }
      }
    }
  }
  else
  {
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 279, &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids, this);
    NextFrame = CMP3BytewiseMediaSource::ReadNextFrame(this);
    if ( NextFrame < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v37 + 499) != NextFrame )
          CallStackContext::TraceFailure(v37, "CMP3BytewiseMediaSource::OnID3v1FooterRead", 3268, NextFrame);
      }
      if ( g_wppLevels )
      {
        v38 = 280;
LABEL_117:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          this,
          NextFrame);
      }
    }
  }
  CMP3BytewiseMediaSource::HandleError(this, NextFrame);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v52);
}

```

## disassembly

```asm
0x1800f99b8  mov     [rsp-38h+arg_10], rbx
0x1800f99bd  push    rbp
0x1800f99be  push    rsi
0x1800f99bf  push    rdi
0x1800f99c0  push    r12
0x1800f99c2  push    r13
0x1800f99c4  push    r14
0x1800f99c6  push    r15
0x1800f99c8  mov     rbp, rsp
0x1800f99cb  sub     rsp, 60h
0x1800f99cf  mov     rax, cs:__security_cookie
0x1800f99d6  xor     rax, rsp
0x1800f99d9  mov     [rbp+var_10], rax
0x1800f99dd  mov     r14, rdx
0x1800f99e0  mov     rsi, rcx
0x1800f99e3  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f99ea  mov     r8d, 0C68h; int
0x1800f99f0  lea     rcx, [rbp+var_30]; this
0x1800f99f4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f99f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f9a00  xor     r12d, r12d
0x1800f9a03  cmp     [rcx+8], r12b
0x1800f9a07  jz      short loc_1800F9A63
0x1800f9a09  cmp     [rsi+458h], r12
0x1800f9a10  jz      short loc_1800F9A63
0x1800f9a12  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f9a17  mov     rdx, [rsi+458h]
0x1800f9a1e  mov     rdi, rax
0x1800f9a21  mov     rcx, [rdx]
0x1800f9a24  mov     rax, [rcx+128h]
0x1800f9a2b  mov     rcx, rdx
0x1800f9a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a33  mov     r8, [rsi+458h]
0x1800f9a3a  lea     rdx, [rbp+var_20]
0x1800f9a3e  mov     ebx, eax
0x1800f9a40  mov     rcx, [r8]
0x1800f9a43  mov     rax, [rcx+118h]
0x1800f9a4a  mov     rcx, r8
0x1800f9a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9a52  movups  xmm0, xmmword ptr [rax]
0x1800f9a55  mov     [rdi+7E0h], ebx
0x1800f9a5b  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800f9a63  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800f9a67  call    cs:__imp_EnterCriticalSection
0x1800f9a6e  nop     dword ptr [rax+rax+00h]
0x1800f9a73  mov     rdx, [rsi+3C8h]
0x1800f9a7a  lea     rcx, [rbp+var_28]
0x1800f9a7e  mov     [rsi+3E0h], r12d
0x1800f9a85  call    ??0?$ComSmartPtr@VCID3Footer@@@@QEAA@PEAVCID3Footer@@@Z; ComSmartPtr<CID3Footer>::ComSmartPtr<CID3Footer>(CID3Footer *)
0x1800f9a8a  mov     rdi, [rbp+var_28]
0x1800f9a8e  mov     rdx, r14; struct IMFAsyncResult *
0x1800f9a91  mov     rcx, rdi; this
0x1800f9a94  call    ?EndDeSerialize@CMP3Base@@QEAAJPEAUIMFAsyncResult@@@Z; CMP3Base::EndDeSerialize(IMFAsyncResult *)
0x1800f9a99  lea     r13, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800f9aa0  mov     r14d, eax
0x1800f9aa3  cmp     [rsi+0C4h], r12d
0x1800f9aaa  jz      loc_1800F9B70
0x1800f9ab0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9ab7  test    rcx, rcx
0x1800f9aba  jnz     short loc_1800F9B03
0x1800f9abc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f9ac3  nop     dword ptr [rax+rax+00h]
0x1800f9ac8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9acf  mov     rcx, rax
0x1800f9ad2  test    rax, rax
0x1800f9ad5  jz      short loc_1800F9AF5
0x1800f9ad7  mov     rax, [rax]
0x1800f9ada  mov     edx, 7F0h
0x1800f9adf  mov     rax, [rax+8]
0x1800f9ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ae8  test    eax, eax
0x1800f9aea  jz      short loc_1800F9AF5
0x1800f9aec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9af3  jmp     short loc_1800F9B03
0x1800f9af5  lea     rcx, qword_1801B97E0; this
0x1800f9afc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9b03  mov     ebx, 0C00D3E85h
0x1800f9b08  cmp     [rcx+8], r12b
0x1800f9b0c  jz      short loc_1800F9B33
0x1800f9b0e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f9b13  cmp     [rax+7CCh], ebx
0x1800f9b19  jz      short loc_1800F9B33
0x1800f9b1b  mov     r9d, ebx; int
0x1800f9b1e  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f9b25  mov     r8d, 0C7Ah; int
0x1800f9b2b  mov     rcx, rax; this
0x1800f9b2e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f9b33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f9b3a  jb      short loc_1800F9B5B
0x1800f9b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9b43  mov     edx, 113h
0x1800f9b48  mov     r9, rsi
0x1800f9b4b  mov     [rsp+60h+var_40], ebx
0x1800f9b4f  mov     r8, r13
0x1800f9b52  mov     rcx, [rcx+10h]
0x1800f9b56  call    WPP_SF_qD
0x1800f9b5b  lea     rcx, [rbp+var_28]; void *
0x1800f9b5f  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f9b64  lea     rbx, [rsi+400h]
0x1800f9b6b  jmp     loc_1800F9E5A
0x1800f9b70  mov     edx, r14d
0x1800f9b73  lea     rbx, [rsi+400h]
0x1800f9b7a  mov     rcx, [rbx]; this
0x1800f9b7d  not     edx
0x1800f9b7f  shr     edx, 1Fh; int
0x1800f9b82  call    ?PopPosition@CByteStreamCacheReaderEx@@QEAAJH@Z; CByteStreamCacheReaderEx::PopPosition(int)
0x1800f9b87  cmp     r14d, 0C00D3E86h
0x1800f9b8e  jz      loc_1800F9E51
0x1800f9b94  test    r14d, r14d
0x1800f9b97  jns     loc_1800F9C38
0x1800f9b9d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9ba4  test    rcx, rcx
0x1800f9ba7  jnz     short loc_1800F9BF0
0x1800f9ba9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f9bb0  nop     dword ptr [rax+rax+00h]
0x1800f9bb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9bbc  mov     rcx, rax
0x1800f9bbf  test    rax, rax
0x1800f9bc2  jz      short loc_1800F9BE2
0x1800f9bc4  mov     rax, [rax]
0x1800f9bc7  mov     edx, 7F0h
0x1800f9bcc  mov     rax, [rax+8]
0x1800f9bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9bd5  test    eax, eax
0x1800f9bd7  jz      short loc_1800F9BE2
0x1800f9bd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9be0  jmp     short loc_1800F9BF0
0x1800f9be2  lea     rcx, qword_1801B97E0; this
0x1800f9be9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9bf0  cmp     [rcx+8], r12b
0x1800f9bf4  jz      short loc_1800F9C1C
0x1800f9bf6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f9bfb  cmp     [rax+7CCh], r14d
0x1800f9c02  jz      short loc_1800F9C1C
0x1800f9c04  mov     r9d, r14d; int
0x1800f9c07  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f9c0e  mov     r8d, 0C83h; int
0x1800f9c14  mov     rcx, rax; this
0x1800f9c17  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f9c1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f9c23  jb      loc_1800F9E51
0x1800f9c29  mov     edx, 114h
0x1800f9c2e  mov     [rsp+60h+var_40], r14d
0x1800f9c33  jmp     loc_1800F9E3B
0x1800f9c38  test    rdi, rdi
0x1800f9c3b  jnz     short loc_1800F9C61
0x1800f9c3d  mov     rcx, [rsi+368h]
0x1800f9c44  test    rcx, rcx
0x1800f9c47  jz      short loc_1800F9C5C
0x1800f9c49  mov     rax, [rcx]
0x1800f9c4c  mov     rax, [rax+10h]
0x1800f9c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c55  mov     [rsi+368h], r12
0x1800f9c5c  mov     rdi, r12
0x1800f9c5f  jmp     short loc_1800F9C8F
0x1800f9c61  mov     rax, [rdi]
0x1800f9c64  mov     rcx, rdi
0x1800f9c67  mov     rax, [rax+8]
0x1800f9c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c70  mov     rcx, [rsi+368h]
0x1800f9c77  test    rcx, rcx
0x1800f9c7a  jz      short loc_1800F9C88
0x1800f9c7c  mov     rax, [rcx]
0x1800f9c7f  mov     rax, [rax+10h]
0x1800f9c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9c88  mov     [rsi+368h], rdi
0x1800f9c8f  cmp     [rsi+3B0h], r12d
0x1800f9c96  jz      short loc_1800F9CA2
0x1800f9c98  cmp     qword ptr [rsi+360h], 0FFFFFFFFFFFFFFFFh
0x1800f9ca0  jz      short loc_1800F9CAD
0x1800f9ca2  mov     rax, [rdi+18h]
0x1800f9ca6  mov     [rsi+328h], rax
0x1800f9cad  cmp     [rsi+3A0h], r12
0x1800f9cb4  jz      loc_1800F9E51
0x1800f9cba  mov     rax, [rsi]
0x1800f9cbd  lea     rdx, [rbp+var_20]
0x1800f9cc1  mov     rcx, rsi
0x1800f9cc4  mov     [rbp+var_20], r12
0x1800f9cc8  mov     rax, [rax+78h]
0x1800f9ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9cd1  test    eax, eax
0x1800f9cd3  js      loc_1800F9D99
0x1800f9cd9  mov     rcx, [rsi+0F0h]
0x1800f9ce0  lea     rdx, MF_PD_DURATION
0x1800f9ce7  mov     r8, [rbp+var_20]
0x1800f9ceb  mov     rax, [rcx]
0x1800f9cee  mov     rax, [rax+0B0h]
0x1800f9cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9cfa  mov     edi, eax
0x1800f9cfc  test    eax, eax
0x1800f9cfe  jns     loc_1800F9D99
0x1800f9d04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9d0b  test    rcx, rcx
0x1800f9d0e  jnz     short loc_1800F9D57
0x1800f9d10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f9d17  nop     dword ptr [rax+rax+00h]
0x1800f9d1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9d23  mov     rcx, rax
0x1800f9d26  test    rax, rax
0x1800f9d29  jz      short loc_1800F9D49
0x1800f9d2b  mov     rax, [rax]
0x1800f9d2e  mov     edx, 7F0h
0x1800f9d33  mov     rax, [rax+8]
0x1800f9d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9d3c  test    eax, eax
0x1800f9d3e  jz      short loc_1800F9D49
0x1800f9d40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9d47  jmp     short loc_1800F9D57
0x1800f9d49  lea     rcx, qword_1801B97E0; this
0x1800f9d50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9d57  cmp     [rcx+8], r12b
0x1800f9d5b  jz      short loc_1800F9D82
0x1800f9d5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f9d62  cmp     [rax+7CCh], edi
0x1800f9d68  jz      short loc_1800F9D82
0x1800f9d6a  mov     r9d, edi; int
0x1800f9d6d  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f9d74  mov     r8d, 0CA0h; int
0x1800f9d7a  mov     rcx, rax; this
0x1800f9d7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f9d82  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f9d89  jb      loc_1800F9E51
0x1800f9d8f  mov     edx, 115h
0x1800f9d94  jmp     loc_1800F9E37
0x1800f9d99  mov     rcx, rsi; this
0x1800f9d9c  call    ?CreateMP3Metadata@CMP3BytewiseMediaSource@@AEAAJXZ; CMP3BytewiseMediaSource::CreateMP3Metadata(void)
0x1800f9da1  mov     edi, eax
0x1800f9da3  test    eax, eax
0x1800f9da5  jns     loc_1800F9E51
0x1800f9dab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9db2  test    rcx, rcx
0x1800f9db5  jnz     short loc_1800F9DFE
0x1800f9db7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f9dbe  nop     dword ptr [rax+rax+00h]
0x1800f9dc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9dca  mov     rcx, rax
0x1800f9dcd  test    rax, rax
0x1800f9dd0  jz      short loc_1800F9DF0
0x1800f9dd2  mov     rax, [rax]
0x1800f9dd5  mov     edx, 7F0h
0x1800f9dda  mov     rax, [rax+8]
0x1800f9dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9de3  test    eax, eax
0x1800f9de5  jz      short loc_1800F9DF0
0x1800f9de7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9dee  jmp     short loc_1800F9DFE
0x1800f9df0  lea     rcx, qword_1801B97E0; this
0x1800f9df7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9dfe  cmp     [rcx+8], r12b
0x1800f9e02  jz      short loc_1800F9E29
0x1800f9e04  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f9e09  cmp     [rax+7CCh], edi
0x1800f9e0f  jz      short loc_1800F9E29
0x1800f9e11  mov     r9d, edi; int
0x1800f9e14  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f9e1b  mov     r8d, 0CA8h; int
0x1800f9e21  mov     rcx, rax; this
0x1800f9e24  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f9e29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f9e30  jb      short loc_1800F9E51
0x1800f9e32  mov     edx, 116h
0x1800f9e37  mov     [rsp+60h+var_40], edi
0x1800f9e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9e42  mov     r9, rsi
0x1800f9e45  mov     r8, r13
0x1800f9e48  mov     rcx, [rcx+10h]
0x1800f9e4c  call    WPP_SF_qD
0x1800f9e51  lea     rcx, [rbp+var_28]; void *
0x1800f9e55  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f9e5a  cmp     [rsi+3B0h], r12d
0x1800f9e61  jnz     loc_1800F9F35
0x1800f9e67  cmp     cs:byte_1801BA10B, 8
0x1800f9e6e  jb      short loc_1800F9E8E
0x1800f9e70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f9e77  mov     edx, 117h
0x1800f9e7c  mov     r9, rsi
0x1800f9e7f  mov     r8, r13
0x1800f9e82  mov     rcx, [rcx+88h]
0x1800f9e89  call    WPP_SF_q
0x1800f9e8e  mov     rcx, rsi; this
0x1800f9e91  call    ?ReadNextFrame@CMP3BytewiseMediaSource@@AEAAJXZ; CMP3BytewiseMediaSource::ReadNextFrame(void)
0x1800f9e96  mov     ebx, eax
0x1800f9e98  test    eax, eax
0x1800f9e9a  jns     loc_1800FA1B6
0x1800f9ea0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9ea7  test    rcx, rcx
0x1800f9eaa  jnz     short loc_1800F9EF3
0x1800f9eac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f9eb3  nop     dword ptr [rax+rax+00h]
0x1800f9eb8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f9ebf  mov     rcx, rax
0x1800f9ec2  test    rax, rax
0x1800f9ec5  jz      short loc_1800F9EE5
0x1800f9ec7  mov     rax, [rax]
0x1800f9eca  mov     edx, 7F0h
0x1800f9ecf  mov     rax, [rax+8]
0x1800f9ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f9ed8  test    eax, eax
0x1800f9eda  jz      short loc_1800F9EE5
0x1800f9edc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
