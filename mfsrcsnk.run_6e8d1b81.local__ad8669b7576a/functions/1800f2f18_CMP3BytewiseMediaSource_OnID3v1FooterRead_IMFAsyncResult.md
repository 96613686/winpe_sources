# CMP3BytewiseMediaSource::OnID3v1FooterRead(IMFAsyncResult *)

- ea: `0x1800f2f18`
- end: `0x1800f3721`
- name: `?OnID3v1FooterRead@CMP3BytewiseMediaSource@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `2057`
- prototype: `void __fastcall(CMP3BytewiseMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18014e010`

## callees

- `0x18000b9ac`
- `0x18000e0c0`
- `0x18000e9ec`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18004b0cc`
- `0x18004e044`
- `0x180051688`
- `0x180073b14`
- `0x180099058`
- `0x1800f2f18`
- `0x1801099f0`
- `0x18011b1e4`
- `0x1801699d8`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f36ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f36ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f2fc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f2fc7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3016`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f30fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f325e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f32ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f33ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f34cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3584`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f364c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3016`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f30fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f325e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f32ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f33ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f34cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f3584`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f364c`

## string_xrefs

- `0x1800f2f43`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f3072`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f3155`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f32b5`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f3356`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f3445`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f3522`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f35db`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`
- `0x1800f36a3`: `CMP3BytewiseMediaSource::OnID3v1FooterRead`

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
              v30 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v25 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v17 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      v12 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B >= 8u )
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
            v49 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
      if ( (unsigned __int8)byte_1801B110B >= 8u )
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
                v45 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v40 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
    if ( (unsigned __int8)byte_1801B110B >= 8u )
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
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800f2f18  mov     [rsp-38h+arg_10], rbx
0x1800f2f1d  push    rbp
0x1800f2f1e  push    rsi
0x1800f2f1f  push    rdi
0x1800f2f20  push    r12
0x1800f2f22  push    r13
0x1800f2f24  push    r14
0x1800f2f26  push    r15
0x1800f2f28  mov     rbp, rsp
0x1800f2f2b  sub     rsp, 60h
0x1800f2f2f  mov     rax, cs:__security_cookie
0x1800f2f36  xor     rax, rsp
0x1800f2f39  mov     [rbp+var_10], rax
0x1800f2f3d  mov     r14, rdx
0x1800f2f40  mov     rsi, rcx
0x1800f2f43  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f2f4a  mov     r8d, 0C68h; int
0x1800f2f50  lea     rcx, [rbp+var_30]; this
0x1800f2f54  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f2f59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800f2f60  xor     r12d, r12d
0x1800f2f63  cmp     [rcx+8], r12b
0x1800f2f67  jz      short loc_1800F2FC3
0x1800f2f69  cmp     [rsi+458h], r12
0x1800f2f70  jz      short loc_1800F2FC3
0x1800f2f72  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f2f77  mov     rdx, [rsi+458h]
0x1800f2f7e  mov     rdi, rax
0x1800f2f81  mov     rcx, [rdx]
0x1800f2f84  mov     rax, [rcx+128h]
0x1800f2f8b  mov     rcx, rdx
0x1800f2f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2f93  mov     r8, [rsi+458h]
0x1800f2f9a  lea     rdx, [rbp+var_20]
0x1800f2f9e  mov     ebx, eax
0x1800f2fa0  mov     rcx, [r8]
0x1800f2fa3  mov     rax, [rcx+118h]
0x1800f2faa  mov     rcx, r8
0x1800f2fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2fb2  movups  xmm0, xmmword ptr [rax]
0x1800f2fb5  mov     [rdi+7E0h], ebx
0x1800f2fbb  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800f2fc3  lea     rcx, [rsi+28h]; lpCriticalSection
0x1800f2fc7  call    cs:__imp_EnterCriticalSection
0x1800f2fcd  mov     rdx, [rsi+3C8h]
0x1800f2fd4  lea     rcx, [rbp+var_28]
0x1800f2fd8  mov     [rsi+3E0h], r12d
0x1800f2fdf  call    ??0?$ComSmartPtr@VCID3Footer@@@@QEAA@PEAVCID3Footer@@@Z; ComSmartPtr<CID3Footer>::ComSmartPtr<CID3Footer>(CID3Footer *)
0x1800f2fe4  mov     rdi, [rbp+var_28]
0x1800f2fe8  mov     rdx, r14; struct IMFAsyncResult *
0x1800f2feb  mov     rcx, rdi; this
0x1800f2fee  call    ?EndDeSerialize@CMP3Base@@QEAAJPEAUIMFAsyncResult@@@Z; CMP3Base::EndDeSerialize(IMFAsyncResult *)
0x1800f2ff3  lea     r13, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x1800f2ffa  mov     r14d, eax
0x1800f2ffd  cmp     [rsi+0C4h], r12d
0x1800f3004  jz      loc_1800F30C4
0x1800f300a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3011  test    rcx, rcx
0x1800f3014  jnz     short loc_1800F3057
0x1800f3016  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f301c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3023  mov     rcx, rax
0x1800f3026  test    rax, rax
0x1800f3029  jz      short loc_1800F3049
0x1800f302b  mov     rax, [rax]
0x1800f302e  mov     edx, 7F0h
0x1800f3033  mov     rax, [rax+8]
0x1800f3037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f303c  test    eax, eax
0x1800f303e  jz      short loc_1800F3049
0x1800f3040  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3047  jmp     short loc_1800F3057
0x1800f3049  lea     rcx, qword_1801B07E0; this
0x1800f3050  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3057  mov     ebx, 0C00D3E85h
0x1800f305c  cmp     [rcx+8], r12b
0x1800f3060  jz      short loc_1800F3087
0x1800f3062  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f3067  cmp     [rax+7CCh], ebx
0x1800f306d  jz      short loc_1800F3087
0x1800f306f  mov     r9d, ebx; int
0x1800f3072  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f3079  mov     r8d, 0C7Ah; int
0x1800f307f  mov     rcx, rax; this
0x1800f3082  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f3087  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f308e  jb      short loc_1800F30AF
0x1800f3090  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3097  mov     edx, 113h
0x1800f309c  mov     r9, rsi
0x1800f309f  mov     [rsp+60h+var_40], ebx
0x1800f30a3  mov     r8, r13
0x1800f30a6  mov     rcx, [rcx+10h]
0x1800f30aa  call    WPP_SF_qD
0x1800f30af  lea     rcx, [rbp+var_28]; void *
0x1800f30b3  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f30b8  lea     rbx, [rsi+400h]
0x1800f30bf  jmp     loc_1800F339C
0x1800f30c4  mov     edx, r14d
0x1800f30c7  lea     rbx, [rsi+400h]
0x1800f30ce  mov     rcx, [rbx]; this
0x1800f30d1  not     edx
0x1800f30d3  shr     edx, 1Fh; int
0x1800f30d6  call    ?PopPosition@CByteStreamCacheReaderEx@@QEAAJH@Z; CByteStreamCacheReaderEx::PopPosition(int)
0x1800f30db  cmp     r14d, 0C00D3E86h
0x1800f30e2  jz      loc_1800F3393
0x1800f30e8  test    r14d, r14d
0x1800f30eb  jns     loc_1800F3186
0x1800f30f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f30f8  test    rcx, rcx
0x1800f30fb  jnz     short loc_1800F313E
0x1800f30fd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3103  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f310a  mov     rcx, rax
0x1800f310d  test    rax, rax
0x1800f3110  jz      short loc_1800F3130
0x1800f3112  mov     rax, [rax]
0x1800f3115  mov     edx, 7F0h
0x1800f311a  mov     rax, [rax+8]
0x1800f311e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3123  test    eax, eax
0x1800f3125  jz      short loc_1800F3130
0x1800f3127  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f312e  jmp     short loc_1800F313E
0x1800f3130  lea     rcx, qword_1801B07E0; this
0x1800f3137  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f313e  cmp     [rcx+8], r12b
0x1800f3142  jz      short loc_1800F316A
0x1800f3144  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f3149  cmp     [rax+7CCh], r14d
0x1800f3150  jz      short loc_1800F316A
0x1800f3152  mov     r9d, r14d; int
0x1800f3155  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f315c  mov     r8d, 0C83h; int
0x1800f3162  mov     rcx, rax; this
0x1800f3165  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f316a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f3171  jb      loc_1800F3393
0x1800f3177  mov     edx, 114h
0x1800f317c  mov     [rsp+60h+var_40], r14d
0x1800f3181  jmp     loc_1800F337D
0x1800f3186  test    rdi, rdi
0x1800f3189  jnz     short loc_1800F31AF
0x1800f318b  mov     rcx, [rsi+368h]
0x1800f3192  test    rcx, rcx
0x1800f3195  jz      short loc_1800F31AA
0x1800f3197  mov     rax, [rcx]
0x1800f319a  mov     rax, [rax+10h]
0x1800f319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31a3  mov     [rsi+368h], r12
0x1800f31aa  mov     rdi, r12
0x1800f31ad  jmp     short loc_1800F31DD
0x1800f31af  mov     rax, [rdi]
0x1800f31b2  mov     rcx, rdi
0x1800f31b5  mov     rax, [rax+8]
0x1800f31b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31be  mov     rcx, [rsi+368h]
0x1800f31c5  test    rcx, rcx
0x1800f31c8  jz      short loc_1800F31D6
0x1800f31ca  mov     rax, [rcx]
0x1800f31cd  mov     rax, [rax+10h]
0x1800f31d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31d6  mov     [rsi+368h], rdi
0x1800f31dd  cmp     [rsi+3B0h], r12d
0x1800f31e4  jz      short loc_1800F31F0
0x1800f31e6  cmp     qword ptr [rsi+360h], 0FFFFFFFFFFFFFFFFh
0x1800f31ee  jz      short loc_1800F31FB
0x1800f31f0  mov     rax, [rdi+18h]
0x1800f31f4  mov     [rsi+328h], rax
0x1800f31fb  cmp     [rsi+3A0h], r12
0x1800f3202  jz      loc_1800F3393
0x1800f3208  mov     rax, [rsi]
0x1800f320b  lea     rdx, [rbp+var_20]
0x1800f320f  mov     rcx, rsi
0x1800f3212  mov     [rbp+var_20], r12
0x1800f3216  mov     rax, [rax+78h]
0x1800f321a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f321f  test    eax, eax
0x1800f3221  js      loc_1800F32E1
0x1800f3227  mov     rcx, [rsi+0F0h]
0x1800f322e  lea     rdx, MF_PD_DURATION
0x1800f3235  mov     r8, [rbp+var_20]
0x1800f3239  mov     rax, [rcx]
0x1800f323c  mov     rax, [rax+0B0h]
0x1800f3243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3248  mov     edi, eax
0x1800f324a  test    eax, eax
0x1800f324c  jns     loc_1800F32E1
0x1800f3252  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3259  test    rcx, rcx
0x1800f325c  jnz     short loc_1800F329F
0x1800f325e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3264  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f326b  mov     rcx, rax
0x1800f326e  test    rax, rax
0x1800f3271  jz      short loc_1800F3291
0x1800f3273  mov     rax, [rax]
0x1800f3276  mov     edx, 7F0h
0x1800f327b  mov     rax, [rax+8]
0x1800f327f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3284  test    eax, eax
0x1800f3286  jz      short loc_1800F3291
0x1800f3288  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f328f  jmp     short loc_1800F329F
0x1800f3291  lea     rcx, qword_1801B07E0; this
0x1800f3298  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f329f  cmp     [rcx+8], r12b
0x1800f32a3  jz      short loc_1800F32CA
0x1800f32a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f32aa  cmp     [rax+7CCh], edi
0x1800f32b0  jz      short loc_1800F32CA
0x1800f32b2  mov     r9d, edi; int
0x1800f32b5  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f32bc  mov     r8d, 0CA0h; int
0x1800f32c2  mov     rcx, rax; this
0x1800f32c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f32ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f32d1  jb      loc_1800F3393
0x1800f32d7  mov     edx, 115h
0x1800f32dc  jmp     loc_1800F3379
0x1800f32e1  mov     rcx, rsi; this
0x1800f32e4  call    ?CreateMP3Metadata@CMP3BytewiseMediaSource@@AEAAJXZ; CMP3BytewiseMediaSource::CreateMP3Metadata(void)
0x1800f32e9  mov     edi, eax
0x1800f32eb  test    eax, eax
0x1800f32ed  jns     loc_1800F3393
0x1800f32f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f32fa  test    rcx, rcx
0x1800f32fd  jnz     short loc_1800F3340
0x1800f32ff  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f3305  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f330c  mov     rcx, rax
0x1800f330f  test    rax, rax
0x1800f3312  jz      short loc_1800F3332
0x1800f3314  mov     rax, [rax]
0x1800f3317  mov     edx, 7F0h
0x1800f331c  mov     rax, [rax+8]
0x1800f3320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3325  test    eax, eax
0x1800f3327  jz      short loc_1800F3332
0x1800f3329  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3330  jmp     short loc_1800F3340
0x1800f3332  lea     rcx, qword_1801B07E0; this
0x1800f3339  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f3340  cmp     [rcx+8], r12b
0x1800f3344  jz      short loc_1800F336B
0x1800f3346  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f334b  cmp     [rax+7CCh], edi
0x1800f3351  jz      short loc_1800F336B
0x1800f3353  mov     r9d, edi; int
0x1800f3356  lea     rdx, aCmp3bytewiseme_36; "CMP3BytewiseMediaSource::OnID3v1FooterR"...
0x1800f335d  mov     r8d, 0CA8h; int
0x1800f3363  mov     rcx, rax; this
0x1800f3366  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f336b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f3372  jb      short loc_1800F3393
0x1800f3374  mov     edx, 116h
0x1800f3379  mov     [rsp+60h+var_40], edi
0x1800f337d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3384  mov     r9, rsi
0x1800f3387  mov     r8, r13
0x1800f338a  mov     rcx, [rcx+10h]
0x1800f338e  call    WPP_SF_qD
0x1800f3393  lea     rcx, [rbp+var_28]; void *
0x1800f3397  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800f339c  cmp     [rsi+3B0h], r12d
0x1800f33a3  jnz     loc_1800F3471
0x1800f33a9  cmp     cs:byte_1801B110B, 8
0x1800f33b0  jb      short loc_1800F33D0
0x1800f33b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f33b9  mov     edx, 117h
0x1800f33be  mov     r9, rsi
0x1800f33c1  mov     r8, r13
0x1800f33c4  mov     rcx, [rcx+88h]
0x1800f33cb  call    WPP_SF_q
0x1800f33d0  mov     rcx, rsi; this
0x1800f33d3  call    ?ReadNextFrame@CMP3BytewiseMediaSource@@AEAAJXZ; CMP3BytewiseMediaSource::ReadNextFrame(void)
0x1800f33d8  mov     ebx, eax
0x1800f33da  test    eax, eax
0x1800f33dc  jns     loc_1800F36E0
0x1800f33e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f33e9  test    rcx, rcx
0x1800f33ec  jnz     short loc_1800F342F
0x1800f33ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f33f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f33fb  mov     rcx, rax
0x1800f33fe  test    rax, rax
0x1800f3401  jz      short loc_1800F3421
0x1800f3403  mov     rax, [rax]
0x1800f3406  mov     edx, 7F0h
0x1800f340b  mov     rax, [rax+8]
0x1800f340f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3414  test    eax, eax
0x1800f3416  jz      short loc_1800F3421
0x1800f3418  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f341f  jmp     short loc_1800F342F
0x1800f3421  lea     rcx, qword_1801B07E0; this
0x1800f3428  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f342f  cmp     [rcx+8], r12b
0x1800f3433  jz      short loc_1800F345A
0x1800f3435  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
  ... truncated ...
```
