# CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck(IMFAsyncResult *)

- ea: `0x18003eb70`
- end: `0x18003f856`
- name: `?OnDataReadForNonMP3FileTypesCheck@CMP3BytewiseMediaSource@@AEAAXPEAUIMFAsyncResult@@@Z`
- size: `3302`
- prototype: `void __fastcall(CMP3BytewiseMediaSource *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18003eb50`

## callees

- `0x18000e0c0`
- `0x18000e9ec`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x18003e610`
- `0x18003eb70`
- `0x18003f85c`
- `0x18003fb20`
- `0x18003fe50`
- `0x180071a44`
- `0x180073b14`
- `0x180089e0c`
- `0x18008a908`
- `0x18008e6e8`
- `0x180091804`
- `0x1800bb2ec`
- `0x1800c8e00`
- `0x1800c8f8c`
- `0x1800d832c`
- `0x1800f70c8`
- `0x1800fe900`
- `0x1801081d0`
- `0x18014f8bc`
- `0x1801699d8`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f7cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f7cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f817`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f817`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f806`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003f806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ec1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ec1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f7fc`
- `MFPlat!MFPutWorkItemEx2` at `0x18003f7b3`
- `MFPlat!MFPutWorkItemEx2` at `0x18003f7b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ecbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ed8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eee8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ef8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f034`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f0da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f226`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f4be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f564`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f620`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f6c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ecbd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ed8b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ee33`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003eee8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003ef8e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f034`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f0da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f226`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f2cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f372`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f4be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f564`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f620`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f6c5`

## string_xrefs

- `0x18003eb92`: `CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck`

## pseudocode

```c
// bad sp value at call has been detected, the output may be wrong!
void __fastcall CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck(
        CMP3BytewiseMediaSource *this,
        struct IMFAsyncResult *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 v6; // xmm0
  struct _RTL_CRITICAL_SECTION *v7; // r12
  CByteStreamCacheReaderEx *v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  CCacheReaderBufferList *v11; // rbx
  int LockedBufferPointer; // edi
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
  DWORD v15; // r14d
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CByteStreamCacheReaderEx *v20; // rcx
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int128 v29; // xmm6
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  __int64 v47; // rdx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  struct CallStackContext *v50; // rax
  __int64 v51; // rdx
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  wchar_t *v56; // rcx
  CallStackTracing *v57; // rax
  struct CallStackContext *v58; // rax
  __int64 v59; // rdx
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  __int64 v63; // rdx
  wchar_t *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 v67; // rdx
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  __int64 v71; // rdx
  wchar_t *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  __int64 v75; // rdx
  wchar_t *v76; // rcx
  CallStackTracing *v77; // rax
  struct CallStackContext *v78; // rax
  __int64 v79; // rdx
  wchar_t *v80; // rcx
  CallStackTracing *v81; // rax
  struct CallStackContext *v82; // rax
  char *v83; // r15
  __int64 v84; // rsi
  __int64 v85; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  bool v88; // sf
  CCacheReaderBufferList *v89[2]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v90[4]; // [rsp+40h] [rbp-20h] BYREF
  int v91[3]; // [rsp+44h] [rbp-1Ch] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v90,
    "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
    562);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 139) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
    v6 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, CCacheReaderBufferList **))(**((_QWORD **)this + 139) + 280LL))(
                      *((_QWORD *)this + 139),
                      v89);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v6;
  }
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  v89[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v8 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 128);
  *((_DWORD *)this + 248) = 0;
  v9 = CByteStreamCacheReaderEx::EndRead(v8, a2, v89);
  v11 = v89[0];
  LockedBufferPointer = v9;
  if ( v9 < 0 )
  {
    v13 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v13 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)v14 + 499) != LockedBufferPointer )
        CallStackContext::TraceFailure(
          v14,
          "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
          577,
          LockedBufferPointer);
    }
    v15 = 1;
    if ( g_wppLevels )
    {
      v16 = 53;
LABEL_23:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
        this,
        LockedBufferPointer);
      goto LABEL_194;
    }
    goto LABEL_194;
  }
  if ( !*((_DWORD *)this + 49) )
  {
    v20 = (CByteStreamCacheReaderEx *)*((_QWORD *)this + 128);
    v89[0] = 0;
    v89[1] = 0;
    LockedBufferPointer = CByteStreamCacheReaderEx::SetCurrentPosition(v20, 0);
    if ( LockedBufferPointer < 0 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != LockedBufferPointer )
          CallStackContext::TraceFailure(
            v24,
            "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
            594,
            LockedBufferPointer);
      }
      v15 = 1;
      if ( g_wppLevels )
      {
        v16 = 55;
        goto LABEL_23;
      }
      goto LABEL_194;
    }
    LockedBufferPointer = CCacheReaderBufferList::GetLockedBufferPointer(v11, 0, (struct MFBUFFER::CBuffer *)v89);
    if ( LockedBufferPointer < 0 )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != LockedBufferPointer )
          CallStackContext::TraceFailure(
            v28,
            "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
            600,
            LockedBufferPointer);
      }
      v15 = 1;
      if ( g_wppLevels )
      {
        v16 = 56;
        goto LABEL_23;
      }
      goto LABEL_194;
    }
    v29 = *(_OWORD *)v89;
    LockedBufferPointer = CMP3BytewiseMediaSource::CheckForFullMPEG(this, (const struct MFBUFFER::CBufferRO *)v89);
    v15 = 1;
    if ( LockedBufferPointer >= 0 )
    {
      *(_OWORD *)v89 = v29;
      LockedBufferPointer = CMP3BytewiseMediaSource::CheckForRIFF(this, (const struct MFBUFFER::CBufferRO *)v89);
      if ( LockedBufferPointer >= 0 )
      {
        *(_OWORD *)v89 = v29;
        LockedBufferPointer = CMP3BytewiseMediaSource::CheckForFlash(this, (const struct MFBUFFER::CBufferRO *)v89);
        if ( LockedBufferPointer >= 0 )
        {
          *(_OWORD *)v89 = v29;
          LockedBufferPointer = CMP3BytewiseMediaSource::CheckForGIF(this, (const struct MFBUFFER::CBufferRO *)v89);
          if ( LockedBufferPointer >= 0 )
          {
            *(_OWORD *)v89 = v29;
            LockedBufferPointer = CMP3BytewiseMediaSource::CheckForMP4(this, (const struct MFBUFFER::CBufferRO *)v89);
            if ( LockedBufferPointer >= 0 )
            {
              *(_OWORD *)v89 = v29;
              LockedBufferPointer = CMP3BytewiseMediaSource::CheckForMKV(this, (const struct MFBUFFER::CBufferRO *)v89);
              if ( LockedBufferPointer >= 0 )
              {
                *(_OWORD *)v89 = v29;
                LockedBufferPointer = CMP3BytewiseMediaSource::CheckForOgg(
                                        this,
                                        (const struct MFBUFFER::CBufferRO *)v89);
                if ( LockedBufferPointer >= 0 )
                {
                  *(_OWORD *)v89 = v29;
                  LockedBufferPointer = CMP3BytewiseMediaSource::CheckForFLAC(
                                          this,
                                          (const struct MFBUFFER::CBufferRO *)v89);
                  if ( LockedBufferPointer >= 0 )
                  {
                    *(_OWORD *)v89 = v29;
                    LockedBufferPointer = CMP3BytewiseMediaSource::CheckForASF(
                                            this,
                                            (const struct MFBUFFER::CBufferRO *)v89);
                    if ( LockedBufferPointer >= 0 )
                    {
                      *(_OWORD *)v89 = v29;
                      LockedBufferPointer = CMP3BytewiseMediaSource::CheckForPNG(
                                              this,
                                              (const struct MFBUFFER::CBufferRO *)v89);
                      if ( LockedBufferPointer >= 0 )
                      {
                        *(_OWORD *)v89 = v29;
                        LockedBufferPointer = CMP3BytewiseMediaSource::CheckForJPEG(
                                                this,
                                                (const struct MFBUFFER::CBufferRO *)v89);
                        if ( LockedBufferPointer >= 0 )
                        {
                          if ( *((_DWORD *)this + 54) && (*((_DWORD *)this + 177) & 0x200) == 0 )
                          {
                            LockedBufferPointer = CMP3BytewiseMediaSource::SeekAndReadFooter(this, 0);
                            if ( LockedBufferPointer < 0 )
                            {
                              v76 = (wchar_t *)CallStackTracing::s_wpInstance;
                              if ( !CallStackTracing::s_wpInstance )
                              {
                                v77 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v75);
                                CallStackTracing::s_wpInstance = v77;
                                if ( v77
                                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v77 + 8LL))(
                                       v77,
                                       2032) )
                                {
                                  v76 = (wchar_t *)CallStackTracing::s_wpInstance;
                                }
                                else
                                {
                                  v76 = &qword_1801B07E0;
                                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                                }
                              }
                              if ( *((_BYTE *)v76 + 8) )
                              {
                                v78 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v76);
                                if ( *((_DWORD *)v78 + 499) != LockedBufferPointer )
                                  CallStackContext::TraceFailure(
                                    v78,
                                    "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                                    625,
                                    LockedBufferPointer);
                              }
                              if ( g_wppLevels )
                              {
                                v34 = 68;
                                goto LABEL_192;
                              }
                              goto LABEL_193;
                            }
                            if ( !LockedBufferPointer )
                              goto LABEL_193;
                          }
                          LockedBufferPointer = CMP3BytewiseMediaSource::ReadNextFrame(this);
                          if ( LockedBufferPointer < 0 )
                          {
                            v80 = (wchar_t *)CallStackTracing::s_wpInstance;
                            if ( !CallStackTracing::s_wpInstance )
                            {
                              v81 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v79);
                              CallStackTracing::s_wpInstance = v81;
                              if ( v81
                                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v81 + 8LL))(
                                     v81,
                                     2032) )
                              {
                                v80 = (wchar_t *)CallStackTracing::s_wpInstance;
                              }
                              else
                              {
                                v80 = &qword_1801B07E0;
                                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                              }
                            }
                            if ( *((_BYTE *)v80 + 8) )
                            {
                              v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v80);
                              if ( *((_DWORD *)v82 + 499) != LockedBufferPointer )
                                CallStackContext::TraceFailure(
                                  v82,
                                  "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                                  637,
                                  LockedBufferPointer);
                            }
                            if ( g_wppLevels )
                            {
                              v34 = 69;
                              goto LABEL_192;
                            }
                          }
                          goto LABEL_193;
                        }
                        v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v71);
                          CallStackTracing::s_wpInstance = v73;
                          if ( v73
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(
                                 v73,
                                 2032) )
                          {
                            v72 = (wchar_t *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v72 = &qword_1801B07E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                          }
                        }
                        if ( *((_BYTE *)v72 + 8) )
                        {
                          v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
                          if ( *((_DWORD *)v74 + 499) != LockedBufferPointer )
                            CallStackContext::TraceFailure(
                              v74,
                              "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                              616,
                              LockedBufferPointer);
                        }
                        if ( g_wppLevels )
                        {
                          v34 = 67;
                          goto LABEL_192;
                        }
                      }
                      else
                      {
                        v68 = (wchar_t *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67);
                          CallStackTracing::s_wpInstance = v69;
                          if ( v69
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(
                                 v69,
                                 2032) )
                          {
                            v68 = (wchar_t *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v68 = &qword_1801B07E0;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                          }
                        }
                        if ( *((_BYTE *)v68 + 8) )
                        {
                          v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
                          if ( *((_DWORD *)v70 + 499) != LockedBufferPointer )
                            CallStackContext::TraceFailure(
                              v70,
                              "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                              615,
                              LockedBufferPointer);
                        }
                        if ( g_wppLevels )
                        {
                          v34 = 66;
                          goto LABEL_192;
                        }
                      }
                    }
                    else
                    {
                      v64 = (wchar_t *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v63);
                        CallStackTracing::s_wpInstance = v65;
                        if ( v65
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(
                               v65,
                               2032) )
                        {
                          v64 = (wchar_t *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v64 = &qword_1801B07E0;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                        }
                      }
                      if ( *((_BYTE *)v64 + 8) )
                      {
                        v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
                        if ( *((_DWORD *)v66 + 499) != LockedBufferPointer )
                          CallStackContext::TraceFailure(
                            v66,
                            "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                            614,
                            LockedBufferPointer);
                      }
                      if ( g_wppLevels )
                      {
                        v34 = 65;
                        goto LABEL_192;
                      }
                    }
                  }
                  else
                  {
                    v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v59);
                      CallStackTracing::s_wpInstance = v61;
                      if ( v61
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(
                             v61,
                             2032) )
                      {
                        v60 = (wchar_t *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v60 = &qword_1801B07E0;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                      }
                    }
                    if ( *((_BYTE *)v60 + 8) )
                    {
                      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
                      if ( *((_DWORD *)v62 + 499) != LockedBufferPointer )
                        CallStackContext::TraceFailure(
                          v62,
                          "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                          613,
                          LockedBufferPointer);
                    }
                    if ( g_wppLevels )
                    {
                      v34 = 64;
                      goto LABEL_192;
                    }
                  }
                }
                else
                {
                  v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v57 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55);
                    CallStackTracing::s_wpInstance = v57;
                    if ( v57
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v57 + 8LL))(v57, 2032) )
                    {
                      v56 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v56 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v56 + 8) )
                  {
                    v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v56);
                    if ( *((_DWORD *)v58 + 499) != LockedBufferPointer )
                      CallStackContext::TraceFailure(
                        v58,
                        "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                        612,
                        LockedBufferPointer);
                  }
                  if ( g_wppLevels )
                  {
                    v34 = 63;
                    goto LABEL_192;
                  }
                }
              }
              else
              {
                v52 = (wchar_t *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
                  CallStackTracing::s_wpInstance = v53;
                  if ( v53
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
                  {
                    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v52 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v52 + 8) )
                {
                  v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
                  if ( *((_DWORD *)v54 + 499) != LockedBufferPointer )
                    CallStackContext::TraceFailure(
                      v54,
                      "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                      611,
                      LockedBufferPointer);
                }
                if ( g_wppLevels )
                {
                  v34 = 62;
                  goto LABEL_192;
                }
              }
            }
            else
            {
              v48 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47);
                CallStackTracing::s_wpInstance = v49;
                if ( v49
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                {
                  v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v48 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                }
              }
              if ( *((_BYTE *)v48 + 8) )
              {
                v50 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                if ( *((_DWORD *)v50 + 499) != LockedBufferPointer )
                  CallStackContext::TraceFailure(
                    v50,
                    "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                    610,
                    LockedBufferPointer);
              }
              if ( g_wppLevels )
              {
                v34 = 61;
                goto LABEL_192;
              }
            }
          }
          else
          {
            v44 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43);
              CallStackTracing::s_wpInstance = v45;
              if ( v45
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
              {
                v44 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v44 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v44 + 8) )
            {
              v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
              if ( *((_DWORD *)v46 + 499) != LockedBufferPointer )
                CallStackContext::TraceFailure(
                  v46,
                  "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                  609,
                  LockedBufferPointer);
            }
            if ( g_wppLevels )
            {
              v34 = 60;
              goto LABEL_192;
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
            if ( *((_DWORD *)v42 + 499) != LockedBufferPointer )
              CallStackContext::TraceFailure(
                v42,
                "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
                608,
                LockedBufferPointer);
          }
          if ( g_wppLevels )
          {
            v34 = 59;
            goto LABEL_192;
          }
        }
      }
      else
      {
        v36 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v36 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
          if ( *((_DWORD *)v38 + 499) != LockedBufferPointer )
            CallStackContext::TraceFailure(
              v38,
              "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
              607,
              LockedBufferPointer);
        }
        if ( g_wppLevels )
        {
          v34 = 58;
          goto LABEL_192;
        }
      }
    }
    else
    {
      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
        CallStackTracing::s_wpInstance = v32;
        if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
        if ( *((_DWORD *)v33 + 499) != LockedBufferPointer )
          CallStackContext::TraceFailure(
            v33,
            "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
            606,
            LockedBufferPointer);
      }
      if ( g_wppLevels )
      {
        v34 = 57;
LABEL_192:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v34,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          this,
          LockedBufferPointer);
      }
    }
LABEL_193:
    CCacheReaderBufferList::UnlockBuffer(v11, 0);
    if ( LockedBufferPointer >= 0 )
      goto LABEL_209;
    goto LABEL_194;
  }
  v17 = (wchar_t *)CallStackTracing::s_wpInstance;
  LockedBufferPointer = -1072873851;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
    if ( *((_DWORD *)v19 + 499) != -1072873851 )
      CallStackContext::TraceFailure(
        v19,
        "CMP3BytewiseMediaSource::OnDataReadForNonMP3FileTypesCheck",
        584,
        -1072873851);
  }
  v15 = 1;
  if ( g_wppLevels )
  {
    v16 = 54;
    goto LABEL_23;
  }
LABEL_194:
  v83 = (char *)this + 1016;
  v84 = *((_QWORD *)this + 127);
  v85 = *(_QWORD *)(v84 + 40);
  *(_DWORD *)(v84 + 48) = LockedBufferPointer;
  if ( v85 )
  {
    LODWORD(v89[0]) = 0;
    v91[0] = 0;
    if ( (*(int (__fastcall **)(__int64, CCacheReaderBufferList **, int *))(*(_QWORD *)v85 + 24LL))(v85, v89, v91) >= 0 )
      v15 = v91[0];
    else
      v91[0] = 1;
    MFPutWorkItemEx2(v15, 0, (IMFAsyncResult *)v84);
  }
  else
  {
    if ( !*(_QWORD *)(v84 + 56) )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v84 + 56), (signed __int64)EventW, 0) )
          CloseHandle(EventW);
      }
      else
      {
        LastError = GetLastError();
        v88 = LastError < 0;
        if ( LastError > 0 )
          v88 = 1;
        if ( v88 )
          goto LABEL_208;
      }
    }
    SetEvent(*(HANDLE *)(v84 + 56));
  }
LABEL_208:
  ComSmartPtr<IUnknown>::Release(v83);
LABEL_209:
  LeaveCriticalSection(v7);
  if ( v11 )
    (*(void (__fastcall **)(CCacheReaderBufferList *))(*(_QWORD *)v11 + 16LL))(v11);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v90);
}

```

## disassembly

```asm
0x18003eb70  mov     [rsp-38h+arg_10], rbx
0x18003eb75  push    rbp
0x18003eb76  push    rsi
0x18003eb77  push    rdi
0x18003eb78  push    r12
0x18003eb7a  push    r13
0x18003eb7c  push    r14
0x18003eb7e  push    r15
0x18003eb80  mov     rbp, rsp
0x18003eb83  sub     rsp, 60h
0x18003eb87  mov     r14, rdx
0x18003eb8a  movaps  [rsp+60h+var_10], xmm6
0x18003eb8f  mov     rsi, rcx
0x18003eb92  lea     r15, aCmp3bytewiseme_41; "CMP3BytewiseMediaSource::OnDataReadForN"...
0x18003eb99  mov     rdx, r15; char *
0x18003eb9c  lea     rcx, [rbp+var_20]; this
0x18003eba0  mov     r8d, 232h; int
0x18003eba6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003ebab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003ebb2  xor     r13d, r13d
0x18003ebb5  cmp     [rcx+8], r13b
0x18003ebb9  jz      short loc_18003EC0F
0x18003ebbb  cmp     [rsi+458h], r13
0x18003ebc2  jz      short loc_18003EC0F
0x18003ebc4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ebc9  mov     rcx, [rsi+458h]
0x18003ebd0  mov     rdi, rax
0x18003ebd3  mov     rdx, [rcx]
0x18003ebd6  mov     rax, [rdx+128h]
0x18003ebdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebe2  mov     rcx, [rsi+458h]
0x18003ebe9  mov     ebx, eax
0x18003ebeb  mov     rdx, [rcx]
0x18003ebee  mov     rax, [rdx+118h]
0x18003ebf5  lea     rdx, [rbp+var_30]
0x18003ebf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebfe  movups  xmm0, xmmword ptr [rax]
0x18003ec01  mov     [rdi+7E0h], ebx
0x18003ec07  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18003ec0f  lea     r12, [rsi+28h]
0x18003ec13  mov     [rbp+var_30], r13
0x18003ec17  mov     rcx, r12; lpCriticalSection
0x18003ec1a  call    cs:__imp_EnterCriticalSection
0x18003ec20  mov     rcx, [rsi+400h]; this
0x18003ec27  lea     r8, [rbp+var_30]; struct CCacheReaderBufferList **
0x18003ec2b  mov     rdx, r14; struct IMFAsyncResult *
0x18003ec2e  mov     [rsi+3E0h], r13d
0x18003ec35  call    ?EndRead@CByteStreamCacheReaderEx@@QEAAJPEAUIMFAsyncResult@@PEAPEAVCCacheReaderBufferList@@@Z; CByteStreamCacheReaderEx::EndRead(IMFAsyncResult *,CCacheReaderBufferList * *)
0x18003ec3a  mov     rbx, [rbp+var_30]
0x18003ec3e  mov     edi, eax
0x18003ec40  test    eax, eax
0x18003ec42  jns     short loc_18003EC9F
0x18003ec44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ec4b  test    rcx, rcx
0x18003ec4e  jnz     short loc_18003EC5C
0x18003ec50  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003ec55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18003ec5c  cmp     [rcx+8], r13b
0x18003ec60  jz      short loc_18003EC83
0x18003ec62  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ec67  cmp     [rax+7CCh], edi
0x18003ec6d  jz      short loc_18003EC83
0x18003ec6f  mov     r9d, edi; int
0x18003ec72  mov     r8d, 241h; int
0x18003ec78  mov     rdx, r15; char *
0x18003ec7b  mov     rcx, rax; this
0x18003ec7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ec83  mov     r14d, 1
0x18003ec89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003ec90  jb      loc_18003F76B
0x18003ec96  lea     edx, [r14+34h]
0x18003ec9a  jmp     loc_18003ED3C
0x18003ec9f  cmp     [rsi+0C4h], r13d
0x18003eca6  jz      loc_18003ED5F
0x18003ecac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecb3  mov     edi, 0C00D3E85h
0x18003ecb8  test    rcx, rcx
0x18003ecbb  jnz     short loc_18003ECFE
0x18003ecbd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ecc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecca  mov     rcx, rax
0x18003eccd  test    rax, rax
0x18003ecd0  jz      short loc_18003ECF0
0x18003ecd2  mov     rax, [rax]
0x18003ecd5  mov     edx, 7F0h
0x18003ecda  mov     rax, [rax+8]
0x18003ecde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ece3  test    eax, eax
0x18003ece5  jz      short loc_18003ECF0
0x18003ece7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecee  jmp     short loc_18003ECFE
0x18003ecf0  lea     rcx, qword_1801B07E0; this
0x18003ecf7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ecfe  cmp     [rcx+8], r13b
0x18003ed02  jz      short loc_18003ED25
0x18003ed04  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ed09  cmp     [rax+7CCh], edi
0x18003ed0f  jz      short loc_18003ED25
0x18003ed11  mov     r9d, edi; int
0x18003ed14  mov     r8d, 248h; int
0x18003ed1a  mov     rdx, r15; char *
0x18003ed1d  mov     rcx, rax; this
0x18003ed20  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ed25  mov     r14d, 1
0x18003ed2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003ed32  jb      loc_18003F76B
0x18003ed38  lea     edx, [r14+35h]
0x18003ed3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed43  lea     r8, WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids
0x18003ed4a  mov     r9, rsi
0x18003ed4d  mov     [rsp+60h+var_40], edi
0x18003ed51  mov     rcx, [rcx+10h]
0x18003ed55  call    WPP_SF_qD
0x18003ed5a  jmp     loc_18003F76B
0x18003ed5f  mov     rcx, [rsi+400h]; this
0x18003ed66  xor     edx, edx; unsigned __int64
0x18003ed68  mov     [rbp+var_30], r13
0x18003ed6c  mov     [rbp+var_30+8], r13
0x18003ed70  call    ?SetCurrentPosition@CByteStreamCacheReaderEx@@QEAAJ_K@Z; CByteStreamCacheReaderEx::SetCurrentPosition(unsigned __int64)
0x18003ed75  mov     edi, eax
0x18003ed77  test    eax, eax
0x18003ed79  jns     loc_18003EE0F
0x18003ed7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed86  test    rcx, rcx
0x18003ed89  jnz     short loc_18003EDCC
0x18003ed8b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ed91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ed98  mov     rcx, rax
0x18003ed9b  test    rax, rax
0x18003ed9e  jz      short loc_18003EDBE
0x18003eda0  mov     rax, [rax]
0x18003eda3  mov     edx, 7F0h
0x18003eda8  mov     rax, [rax+8]
0x18003edac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edb1  test    eax, eax
0x18003edb3  jz      short loc_18003EDBE
0x18003edb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edbc  jmp     short loc_18003EDCC
0x18003edbe  lea     rcx, qword_1801B07E0; this
0x18003edc5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003edcc  cmp     [rcx+8], r13b
0x18003edd0  jz      short loc_18003EDF3
0x18003edd2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003edd7  cmp     [rax+7CCh], edi
0x18003eddd  jz      short loc_18003EDF3
0x18003eddf  mov     r9d, edi; int
0x18003ede2  mov     r8d, 252h; int
0x18003ede8  mov     rdx, r15; char *
0x18003edeb  mov     rcx, rax; this
0x18003edee  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003edf3  mov     r14d, 1
0x18003edf9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003ee00  jb      loc_18003F76B
0x18003ee06  lea     edx, [r14+36h]
0x18003ee0a  jmp     loc_18003ED3C
0x18003ee0f  lea     r8, [rbp+var_30]; struct MFBUFFER::CBuffer *
0x18003ee13  xor     edx, edx; unsigned int
0x18003ee15  mov     rcx, rbx; this
0x18003ee18  call    ?GetLockedBufferPointer@CCacheReaderBufferList@@QEAAJKAEAVCBuffer@MFBUFFER@@@Z; CCacheReaderBufferList::GetLockedBufferPointer(ulong,MFBUFFER::CBuffer &)
0x18003ee1d  mov     edi, eax
0x18003ee1f  test    eax, eax
0x18003ee21  jns     loc_18003EEB7
0x18003ee27  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee2e  test    rcx, rcx
0x18003ee31  jnz     short loc_18003EE74
0x18003ee33  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ee39  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee40  mov     rcx, rax
0x18003ee43  test    rax, rax
0x18003ee46  jz      short loc_18003EE66
0x18003ee48  mov     rax, [rax]
0x18003ee4b  mov     edx, 7F0h
0x18003ee50  mov     rax, [rax+8]
0x18003ee54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee59  test    eax, eax
0x18003ee5b  jz      short loc_18003EE66
0x18003ee5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee64  jmp     short loc_18003EE74
0x18003ee66  lea     rcx, qword_1801B07E0; this
0x18003ee6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ee74  cmp     [rcx+8], r13b
0x18003ee78  jz      short loc_18003EE9B
0x18003ee7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ee7f  cmp     [rax+7CCh], edi
0x18003ee85  jz      short loc_18003EE9B
0x18003ee87  mov     r9d, edi; int
0x18003ee8a  mov     r8d, 258h; int
0x18003ee90  mov     rdx, r15; char *
0x18003ee93  mov     rcx, rax; this
0x18003ee96  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ee9b  mov     r14d, 1
0x18003eea1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003eea8  jb      loc_18003F76B
0x18003eeae  lea     edx, [r14+37h]
0x18003eeb2  jmp     loc_18003ED3C
0x18003eeb7  movaps  xmm6, xmmword ptr [rbp+var_30]
0x18003eebb  lea     rdx, [rbp+var_30]; struct MFBUFFER::CBufferRO *
0x18003eebf  mov     rcx, rsi; this
0x18003eec2  movdqa  xmmword ptr [rbp+var_30], xmm6
0x18003eec7  call    ?CheckForFullMPEG@CMP3BytewiseMediaSource@@AEAAJAEBVCBufferRO@MFBUFFER@@@Z; CMP3BytewiseMediaSource::CheckForFullMPEG(MFBUFFER::CBufferRO const &)
0x18003eecc  mov     edi, eax
0x18003eece  mov     r14d, 1
0x18003eed4  test    eax, eax
0x18003eed6  jns     loc_18003EF67
0x18003eedc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eee3  test    rcx, rcx
0x18003eee6  jnz     short loc_18003EF29
0x18003eee8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003eeee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003eef5  mov     rcx, rax
0x18003eef8  test    rax, rax
0x18003eefb  jz      short loc_18003EF1B
0x18003eefd  mov     rax, [rax]
0x18003ef00  mov     edx, 7F0h
0x18003ef05  mov     rax, [rax+8]
0x18003ef09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef0e  test    eax, eax
0x18003ef10  jz      short loc_18003EF1B
0x18003ef12  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef19  jmp     short loc_18003EF29
0x18003ef1b  lea     rcx, qword_1801B07E0; this
0x18003ef22  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef29  cmp     [rcx+8], r13b
0x18003ef2d  jz      short loc_18003EF50
0x18003ef2f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ef34  cmp     [rax+7CCh], edi
0x18003ef3a  jz      short loc_18003EF50
0x18003ef3c  mov     r9d, edi; int
0x18003ef3f  mov     r8d, 25Eh; int
0x18003ef45  mov     rdx, r15; char *
0x18003ef48  mov     rcx, rax; this
0x18003ef4b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ef50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003ef57  jb      loc_18003F759
0x18003ef5d  mov     edx, 39h ; '9'
0x18003ef62  jmp     loc_18003F73B
0x18003ef67  lea     rdx, [rbp+var_30]; struct MFBUFFER::CBufferRO *
0x18003ef6b  movdqa  xmmword ptr [rbp+var_30], xmm6
0x18003ef70  mov     rcx, rsi; this
0x18003ef73  call    ?CheckForRIFF@CMP3BytewiseMediaSource@@AEAAJAEBVCBufferRO@MFBUFFER@@@Z; CMP3BytewiseMediaSource::CheckForRIFF(MFBUFFER::CBufferRO const &)
0x18003ef78  mov     edi, eax
0x18003ef7a  test    eax, eax
0x18003ef7c  jns     loc_18003F00D
0x18003ef82  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef89  test    rcx, rcx
0x18003ef8c  jnz     short loc_18003EFCF
0x18003ef8e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003ef94  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003ef9b  mov     rcx, rax
0x18003ef9e  test    rax, rax
0x18003efa1  jz      short loc_18003EFC1
0x18003efa3  mov     rax, [rax]
0x18003efa6  mov     edx, 7F0h
0x18003efab  mov     rax, [rax+8]
0x18003efaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efb4  test    eax, eax
0x18003efb6  jz      short loc_18003EFC1
0x18003efb8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003efbf  jmp     short loc_18003EFCF
0x18003efc1  lea     rcx, qword_1801B07E0; this
0x18003efc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003efcf  cmp     [rcx+8], r13b
0x18003efd3  jz      short loc_18003EFF6
0x18003efd5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003efda  cmp     [rax+7CCh], edi
0x18003efe0  jz      short loc_18003EFF6
0x18003efe2  mov     r9d, edi; int
0x18003efe5  mov     r8d, 25Fh; int
0x18003efeb  mov     rdx, r15; char *
0x18003efee  mov     rcx, rax; this
0x18003eff1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003eff6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003effd  jb      loc_18003F759
0x18003f003  mov     edx, 3Ah ; ':'
0x18003f008  jmp     loc_18003F73B
0x18003f00d  lea     rdx, [rbp+var_30]; struct MFBUFFER::CBufferRO *
0x18003f011  movdqa  xmmword ptr [rbp+var_30], xmm6
0x18003f016  mov     rcx, rsi; this
0x18003f019  call    ?CheckForFlash@CMP3BytewiseMediaSource@@AEAAJAEBVCBufferRO@MFBUFFER@@@Z; CMP3BytewiseMediaSource::CheckForFlash(MFBUFFER::CBufferRO const &)
0x18003f01e  mov     edi, eax
0x18003f020  test    eax, eax
0x18003f022  jns     loc_18003F0B3
0x18003f028  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f02f  test    rcx, rcx
0x18003f032  jnz     short loc_18003F075
0x18003f034  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003f03a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f041  mov     rcx, rax
0x18003f044  test    rax, rax
0x18003f047  jz      short loc_18003F067
0x18003f049  mov     rax, [rax]
0x18003f04c  mov     edx, 7F0h
0x18003f051  mov     rax, [rax+8]
0x18003f055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f05a  test    eax, eax
0x18003f05c  jz      short loc_18003F067
0x18003f05e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f065  jmp     short loc_18003F075
0x18003f067  lea     rcx, qword_1801B07E0; this
0x18003f06e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
