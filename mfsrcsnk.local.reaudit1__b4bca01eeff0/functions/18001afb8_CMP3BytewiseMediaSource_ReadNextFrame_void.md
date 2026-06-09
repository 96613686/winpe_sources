# CMP3BytewiseMediaSource::ReadNextFrame(void)

- ea: `0x18001afb8`
- end: `0x18001c25b`
- name: `?ReadNextFrame@CMP3BytewiseMediaSource@@AEAAJXZ`
- size: `4771`
- prototype: `__int64 __fastcall(CMP3BytewiseMediaSource *__hidden this)`
- caller_count: `6`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f990`
- `0x180040700`
- `0x18005e8f0`
- `0x1800cadd8`
- `0x1800f99b8`
- `0x180157364`

## callees

- `0x180005cf4`
- `0x180008890`
- `0x180018a3c`
- `0x180018a54`
- `0x18001a480`
- `0x18001afb8`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180036c30`
- `0x180042b1c`
- `0x180048588`
- `0x1800485a0`
- `0x18004a8a8`
- `0x18004f030`
- `0x180058af4`
- `0x180077708`
- `0x180079680`
- `0x180110a94`
- `0x180111960`
- `0x180124a8c`
- `0x18015cbec`
- `0x1801729e0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b15f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b15f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b5fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b963`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b0c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b5d6`
- `MFPlat!MFLockPlatform` at `0x18001b525`
- `MFPlat!MFLockPlatform` at `0x18001b525`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b798`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b89b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b8e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b97f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001baf1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b798`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b89b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b8e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b929`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b97f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b9f9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ba75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001bab3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001baf1`

## string_xrefs

- `0x18001afe2`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001b082`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bbb9`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bc43`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bc71`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bc9f`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bd2a`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001bd59`: `CMP3BytewiseMediaSource::ReadNextFrame`
- `0x18001b4aa`: `CMP3Base::BeginDeSerialize`
- `0x18001bccd`: `CMP3Base::BeginDeSerialize`
- `0x18001bcfc`: `CMP3Base::BeginDeSerialize`
- `0x18001b26a`: `CByteStreamCacheReaderEx::GetCurrentPosition`
- `0x18001b5b3`: `CByteStreamCacheReaderEx::GetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CMP3BytewiseMediaSource::ReadNextFrame(CMP3BytewiseMediaSource *this)
{
  CallStackTracing *v2; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  struct CallStackContext *v6; // rdi
  int v7; // ebx
  __int128 *v8; // rax
  __int128 v9; // xmm0
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  void **v15; // rbx
  char *v16; // rbx
  __int64 v17; // rdx
  int v18; // r9d
  wchar_t *v19; // rcx
  struct CallStackContext *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // rbx
  struct CallStackContext *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // r14
  __int64 v31; // rdi
  CallStackTracing *v32; // rcx
  struct CallStackContext *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rdx
  CallStackTracing *v39; // rcx
  struct CallStackContext *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rcx
  tagMFASYNCRESULT *v43; // rax
  __int64 v44; // rdx
  tagMFASYNCRESULT *v45; // rdi
  __int64 v46; // rcx
  CallStackTracing *v47; // rcx
  __int64 v48; // rdi
  struct CallStackContext *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rcx
  struct CallStackContext *v56; // rax
  int v57; // ecx
  int v58; // ecx
  wchar_t *v60; // rcx
  CallStackTracing *v61; // rax
  __int64 v62; // rdx
  int v63; // edx
  CallStackTracing *v64; // rax
  CallStackTracing *v65; // rax
  CallStackTracing *v66; // rax
  __int64 v67; // rdx
  wchar_t *v68; // rcx
  CallStackTracing *v69; // rax
  CallStackTracing *v70; // rax
  wchar_t *v71; // rcx
  CallStackTracing *v72; // rax
  wchar_t *v73; // rcx
  CallStackTracing *v74; // rax
  wchar_t *v75; // rcx
  CallStackTracing *v76; // rax
  wchar_t *v77; // rcx
  CallStackTracing *v78; // rax
  wchar_t *v79; // rcx
  CallStackTracing *v80; // rax
  struct CallStackContext *v81; // rax
  struct CallStackContext *v82; // rax
  struct CallStackContext *v83; // rax
  struct CallStackContext *v84; // rax
  struct CallStackContext *v85; // rax
  struct CallStackContext *v86; // rax
  struct CallStackContext *v87; // rax
  struct CallStackContext *v88; // rax
  struct CallStackContext *v89; // rax
  struct CallStackContext *v90; // rax
  struct CallStackContext *v91; // rax
  struct CallStackContext *v92; // rax
  struct CallStackContext *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  __int64 v96; // rdx
  __int64 v97; // rdx
  __int64 v98; // rdx
  __int64 v99; // rcx
  __int64 v100; // rdx
  char v101[8]; // [rsp+30h] [rbp-28h] BYREF
  char *v102; // [rsp+38h] [rbp-20h] BYREF
  char v103[24]; // [rsp+40h] [rbp-18h] BYREF

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v2);
    v4 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v4 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v5 = 2 * v4;
      *((_QWORD *)ThreadRelativeContext + v5) = "CMP3BytewiseMediaSource::ReadNextFrame";
      *((_DWORD *)ThreadRelativeContext + 2 * v5 + 2) = 2619;
    }
    v2 = CallStackTracing::s_wpInstance;
    ++*((_DWORD *)ThreadRelativeContext + 497);
    if ( *((_BYTE *)v2 + 8) && *((_QWORD *)this + 139) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext(v2);
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 139) + 296LL))(*((_QWORD *)this + 139));
      v8 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 139) + 280LL))(
                         *((_QWORD *)this + 139),
                         v103);
      v2 = CallStackTracing::s_wpInstance;
      v9 = *v8;
      *((_DWORD *)v6 + 504) = v7;
      *((_OWORD *)v6 + 125) = v9;
    }
  }
  if ( !*((_DWORD *)this + 210) )
  {
    if ( (unsigned __int8)byte_1801BA10B >= 8u )
      WPP_SF_qI(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        219,
        &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
        this,
        *((_QWORD *)this + 103));
    v24 = CByteStreamCacheReaderEx::SetCurrentPosition(
            *((CByteStreamCacheReaderEx **)this + 128),
            *((_QWORD *)this + 103));
    if ( v24 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v95, v94);
        CallStackTracing::s_wpInstance = v64;
        if ( !v64 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v81 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v81 + 499) != v24 )
          CallStackContext::TraceFailure(v81, "CMP3BytewiseMediaSource::ReadNextFrame", 2645, v24);
      }
      if ( !g_wppLevels )
        goto LABEL_86;
      v62 = 220;
LABEL_105:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v62, &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids, this, v24);
      goto LABEL_86;
    }
    *((_QWORD *)this + 123) = 0;
    ComSmartPtr<IMFMediaBuffer>::operator=((char *)this + 976, 0);
    ComSmartPtr<CMPEGFrame>::operator=((char *)this + 1000, 0);
    v2 = CallStackTracing::s_wpInstance;
    *((_DWORD *)this + 210) = 1;
  }
  if ( !*((_QWORD *)this + 127) )
  {
    v102 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      v13 = *((unsigned int *)v12 + 497);
      if ( (unsigned int)v13 < *((_DWORD *)v12 + 498) )
      {
        v14 = 2 * v13;
        *((_QWORD *)v12 + v14) = "CMediaSourceBase::GetActiveMediaStreamByIndex";
        *((_DWORD *)v12 + 2 * v14 + 2) = 1714;
      }
      ++*((_DWORD *)v12 + 497);
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    if ( *((_DWORD *)this + 174) )
    {
      v15 = (void **)*((_QWORD *)this + 85);
      if ( v15 )
      {
        v16 = (char *)*v15;
        v102 = v16;
        if ( v16 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          v21 = *((unsigned int *)v20 + 497);
          if ( (unsigned int)v21 < *((_DWORD *)v20 + 498) )
          {
            v22 = 2 * v21;
            *((_QWORD *)v20 + v22) = "CMediaSourceBase::IsSampleNeeded";
            *((_DWORD *)v20 + 2 * v22 + 2) = 1539;
          }
          v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          ++*((_DWORD *)v20 + 497);
        }
        if ( *((_DWORD *)this + 49) )
          goto LABEL_95;
        if ( v16 )
        {
          if ( *((_DWORD *)this + 50) == 2 )
          {
            if ( (unsigned __int8)byte_1801BA10B < 8u )
            {
LABEL_95:
              v24 = 1;
LABEL_35:
              CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
              if ( v24 >= 0 )
              {
                if ( v24 )
                {
                  v24 = 0;
LABEL_84:
                  if ( v16 )
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
                  goto LABEL_86;
                }
                if ( v16 )
                  (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16);
                v2 = CallStackTracing::s_wpInstance;
                goto LABEL_40;
              }
              v73 = (wchar_t *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v74 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
                CallStackTracing::s_wpInstance = v74;
                if ( v74
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v74 + 8LL))(v74, 2032) )
                {
                  v73 = (wchar_t *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v73 = &qword_1801B97E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                }
              }
              if ( *((_BYTE *)v73 + 8) )
              {
                v87 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v73);
                if ( *((_DWORD *)v87 + 499) != v24 )
                  CallStackContext::TraceFailure(v87, "CMP3BytewiseMediaSource::ReadNextFrame", 2670, v24);
              }
              if ( !g_wppLevels )
                goto LABEL_195;
              v97 = 222;
LABEL_194:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v97,
                &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
                this,
                v24);
              goto LABEL_195;
            }
            v63 = 147;
LABEL_203:
            WPP_SF_sq(
              *((_QWORD *)WPP_GLOBAL_Control + 17),
              v63,
              (unsigned int)&WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
              v18,
              (__int64)this);
            goto LABEL_95;
          }
          v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v16 + 112LL))(v16);
          if ( v24 >= 0 )
          {
            if ( !*((_DWORD *)this + 50) )
              goto LABEL_95;
            if ( (unsigned int)CBytewiseMediaStream::HasOutstandingRequests((CBytewiseMediaStream *)v16)
              || *((_DWORD *)v16 + 44) && *((_DWORD *)v16 + 38) && *((_DWORD *)v16 + 45) )
            {
              if ( (unsigned __int8)byte_1801BA10B >= 0x10u )
                WPP_SF_sq(
                  *((_QWORD *)WPP_GLOBAL_Control + 17),
                  150,
                  (unsigned int)&WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
                  v18,
                  (__int64)this);
              goto LABEL_35;
            }
            if ( (unsigned __int8)byte_1801BA10B < 0x10u )
              goto LABEL_95;
            v63 = 149;
            goto LABEL_203;
          }
          v71 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v72 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
            CallStackTracing::s_wpInstance = v72;
            if ( v72 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
            {
              v71 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v71 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v71 + 8) )
          {
            v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v71);
            if ( *((_DWORD *)v86 + 499) != v24 )
              CallStackContext::TraceFailure(v86, "CMediaSourceBase::IsSampleNeeded", 1572, v24);
          }
          if ( !g_wppLevels )
            goto LABEL_35;
          v98 = 148;
        }
        else
        {
          v24 = -2147467261;
          if ( !v19 )
          {
            v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
            CallStackTracing::s_wpInstance = v70;
            if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
            {
              v19 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v85 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v85 + 499) != -2147467261 )
              CallStackContext::TraceFailure(v85, "CMediaSourceBase::IsSampleNeeded", 1556, -2147467261);
          }
          if ( !g_wppLevels )
            goto LABEL_35;
          v98 = 146;
        }
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v98, &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids, this, v24);
        goto LABEL_35;
      }
      v24 = -1072875853;
      if ( !v11 )
      {
        v66 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v66;
        if ( v66 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v66 + 8LL))(v66, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v83 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v83 + 499) != -1072875853 )
          CallStackContext::TraceFailure(v83, "CMediaSourceBase::GetActiveMediaStreamByIndex", 1730, -1072875853);
      }
      if ( !g_wppLevels )
      {
LABEL_123:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
        v68 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v67);
          CallStackTracing::s_wpInstance = v69;
          if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
          {
            v68 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v68 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v68 + 8) )
        {
          v84 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
          if ( *((_DWORD *)v84 + 499) != -1072875853 )
            CallStackContext::TraceFailure(v84, "CMP3BytewiseMediaSource::ReadNextFrame", 2668, -1072875853);
        }
        if ( !g_wppLevels )
          goto LABEL_195;
        v97 = 221;
        goto LABEL_194;
      }
      v96 = 158;
    }
    else
    {
      v24 = -1072875853;
      if ( !v11 )
      {
        v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v65;
        if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v82 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v82 + 499) != -1072875853 )
          CallStackContext::TraceFailure(v82, "CMediaSourceBase::GetActiveMediaStreamByIndex", 1721, -1072875853);
      }
      if ( !g_wppLevels )
        goto LABEL_123;
      v96 = 157;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v96,
      &WPP_735b9883034235cea6dbd7724b1afea7_Traceguids,
      this,
      -1072875853);
    goto LABEL_123;
  }
LABEL_40:
  v26 = *((_QWORD *)this + 128);
  if ( !v2 )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v27 = CallStackTracing::GetThreadRelativeContext(v2);
    v28 = *((unsigned int *)v27 + 497);
    if ( (unsigned int)v28 < *((_DWORD *)v27 + 498) )
    {
      v29 = 2 * v28;
      *((_QWORD *)v27 + v29) = "CByteStreamCacheReaderEx::GetCurrentPosition";
      *((_DWORD *)v27 + 2 * v29 + 2) = 439;
    }
    ++*((_DWORD *)v27 + 497);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v26 + 568));
  v30 = *(_QWORD *)(v26 + 512);
  if ( v30 == -1 )
    v30 = *(_QWORD *)(v26 + 504);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 568));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
  if ( v30 == *((_QWORD *)this + 101) )
  {
    v24 = -1072873849;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v88 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v88 + 499) != -1072873849 )
        CallStackContext::TraceFailure(v88, "CMP3BytewiseMediaSource::ReadNextFrame", 2686, -1072873849);
    }
    if ( !g_wppLevels )
      goto LABEL_86;
    v62 = 224;
    goto LABEL_105;
  }
  v16 = (char *)operator new(0x160u);
  if ( v16 )
  {
    v31 = *((_QWORD *)this + 128);
    v32 = CallStackTracing::s_wpInstance;
    *(_QWORD *)v16 = &CMP3Base::`vftable';
    *((_QWORD *)v16 + 5) = 0;
    *((_QWORD *)v16 + 6) = 0;
    if ( !v32 )
    {
      CallStackTracing::InitInstance();
      v32 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v33 = CallStackTracing::GetThreadRelativeContext(v32);
      v34 = *((unsigned int *)v33 + 497);
      if ( (unsigned int)v34 < *((_DWORD *)v33 + 498) )
      {
        v35 = 2 * v34;
        *((_QWORD *)v33 + v35) = "CMP3Base::CMP3Base";
        *((_DWORD *)v33 + 2 * v35 + 2) = 31;
      }
      ++*((_DWORD *)v33 + 497);
    }
    *((_DWORD *)v16 + 8) = 0;
    *((_QWORD *)v16 + 1) = 0;
    *((_DWORD *)v16 + 4) = 0;
    *((_QWORD *)v16 + 3) = 0;
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      v36 = *((_QWORD *)v16 + 5);
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      *((_QWORD *)v16 + 5) = v31;
    }
    else
    {
      v99 = *((_QWORD *)v16 + 5);
      if ( v99 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
        *((_QWORD *)v16 + 5) = 0;
      }
    }
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
    *(_QWORD *)v16 = &CMPEGFrame::`vftable';
    *((_QWORD *)v16 + 16) = 0;
    CMPEGFrame::OnHeaderReadAsyncCallback::OnHeaderReadAsyncCallback((CMPEGFrame::OnHeaderReadAsyncCallback *)(v16 + 328));
    CMPEGFrame::OnFrameReadAsyncCallback::OnFrameReadAsyncCallback((CMPEGFrame::OnFrameReadAsyncCallback *)(v16 + 336));
    *((_DWORD *)v16 + 4) = 10;
    *((_QWORD *)v16 + 7) = 0;
    *((_QWORD *)v16 + 8) = 0;
    *((_QWORD *)v16 + 9) = 0;
    *((_QWORD *)v16 + 10) = 0;
    *((_QWORD *)v16 + 11) = 0;
    *((_QWORD *)v16 + 12) = 0;
    *((_QWORD *)v16 + 13) = 0;
    *((_QWORD *)v16 + 14) = 0;
    *((_DWORD *)v16 + 30) = 0;
    *((_QWORD *)v16 + 17) = 0;
    *((_QWORD *)v16 + 18) = 0;
    *((_QWORD *)v16 + 19) = 0;
    *((_QWORD *)v16 + 20) = 0;
    *((_QWORD *)v16 + 21) = 0;
    *((_DWORD *)v16 + 44) = 0;
    memset_0(v16 + 180, 0, 0x64u);
    *((_QWORD *)v16 + 35) = 0;
    *((_QWORD *)v16 + 36) = 0;
    *((_QWORD *)v16 + 43) = 0;
    *(_OWORD *)(v16 + 300) = 0;
    *(_QWORD *)(v16 + 316) = 0;
    *((_DWORD *)v16 + 74) = 0;
    v37 = *(_QWORD *)v16;
    v102 = v16;
    (*(void (__fastcall **)(char *))(v37 + 8))(v16);
    v24 = CByteStreamCacheReaderEx::PushPosition(*((CByteStreamCacheReaderEx **)this + 128));
    if ( v24 < 0 )
    {
      v75 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v76 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
        CallStackTracing::s_wpInstance = v76;
        if ( v76 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v76 + 8LL))(v76, 2032) )
        {
          v75 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v75 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v75 + 8) )
      {
        v89 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v75);
        if ( *((_DWORD *)v89 + 499) != v24 )
          CallStackContext::TraceFailure(v89, "CMP3BytewiseMediaSource::ReadNextFrame", 2696, v24);
      }
      if ( !g_wppLevels )
        goto LABEL_195;
      v100 = 226;
      goto LABEL_221;
    }
    if ( !*((_QWORD *)this + 125) && (!*((_DWORD *)this + 236) || *((_DWORD *)this + 237)) )
    {
      *((_QWORD *)this + 126) = v30;
      if ( (unsigned __int8)byte_1801BA10B >= 8u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          227,
          &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
          (unsigned int)v30);
    }
    v39 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v39 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v40 = CallStackTracing::GetThreadRelativeContext(v39);
      v41 = *((unsigned int *)v40 + 497);
      if ( (unsigned int)v41 < *((_DWORD *)v40 + 498) )
      {
        v42 = 2 * v41;
        *((_QWORD *)v40 + v42) = "CMP3Base::BeginDeSerialize";
        *((_DWORD *)v40 + 2 * v42 + 2) = 129;
      }
      ++*((_DWORD *)v40 + 497);
    }
    v43 = (tagMFASYNCRESULT *)operator new(0x68u);
    v45 = v43;
    if ( v43 )
    {
      tagMFASYNCRESULT::tagMFASYNCRESULT(v43);
      *(_QWORD *)(v46 + 64) = &CMFRefCounted::`vftable';
      *(_DWORD *)(v46 + 72) = 0;
      *(_QWORD *)v46 = &CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'};
      *(_QWORD *)(v46 + 64) = &CAsyncResult::`vftable'{for `CMFRefCounted'};
      *(_DWORD *)(v46 + 96) = 0;
      MFLockPlatform();
      HIDWORD(v45[1].overlapped.hEvent) = 0;
      v45->hrStatusResult = 0;
      v45->hEvent = 0;
      v45[1].overlapped.InternalHigh = 0;
      v45[1].overlapped.Pointer = 0;
      v45->pCallback = (IMFAsyncCallback *)((char *)this + 1064);
      if ( this != (CMP3BytewiseMediaSource *)-1064LL )
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 133) + 8LL))((char *)this + 1064);
      *(_OWORD *)&v45->overlapped.Internal = 0;
      *(_OWORD *)&v45->overlapped.Offset = 0;
      v45->dwBytesTransferred = 0;
      ((void (__fastcall *)(tagMFASYNCRESULT *))v45->AsyncResult.lpVtbl->AddRef)(v45);
      v47 = CallStackTracing::s_wpInstance;
      *((_QWORD *)v16 + 6) = v45;
      v48 = *((_QWORD *)v16 + 5);
      if ( !v47 )
      {
        CallStackTracing::InitInstance();
        v47 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v47 + 8) )
      {
        v49 = CallStackTracing::GetThreadRelativeContext(v47);
        v50 = *((unsigned int *)v49 + 497);
        if ( (unsigned int)v50 < *((_DWORD *)v49 + 498) )
        {
          v51 = 2 * v50;
          *((_QWORD *)v49 + v51) = "CByteStreamCacheReaderEx::GetCurrentPosition";
          *((_DWORD *)v49 + 2 * v51 + 2) = 439;
        }
        ++*((_DWORD *)v49 + 497);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v48 + 568));
      v52 = *(_QWORD *)(v48 + 512);
      if ( v52 == -1 )
        v52 = *(_QWORD *)(v48 + 504);
      *((_QWORD *)v16 + 3) = v52;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v48 + 568));
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
      v24 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v16 + 48LL))(v16);
      if ( v24 >= 0 )
      {
LABEL_80:
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v101);
        if ( v24 >= 0 )
        {
          (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 8LL))(v16);
          v55 = *((_QWORD *)this + 121);
          if ( v55 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
          *((_QWORD *)this + 121) = v16;
          *((_DWORD *)this + 248) = 1;
          goto LABEL_84;
        }
        v79 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v80 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
          CallStackTracing::s_wpInstance = v80;
          if ( v80 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v80 + 8LL))(v80, 2032) )
          {
            v79 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v79 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v79 + 8) )
        {
          v92 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v79);
          if ( *((_DWORD *)v92 + 499) != v24 )
            CallStackContext::TraceFailure(v92, "CMP3BytewiseMediaSource::ReadNextFrame", 2711, v24);
        }
        if ( g_wppLevels )
        {
          v100 = 228;
LABEL_221:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v100,
            &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
            this,
            v24);
        }
LABEL_195:
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v102);
        goto LABEL_86;
      }
      v77 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v78 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v53);
        CallStackTracing::s_wpInstance = v78;
        if ( v78 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v78 + 8LL))(v78, 2032) )
        {
          v77 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v77 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v77 + 8) )
      {
        v90 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v77);
        if ( *((_DWORD *)v90 + 499) != v24 )
          CallStackContext::TraceFailure(v90, "CMP3Base::BeginDeSerialize", 145, v24);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d18bbb785de430394c1967457ee8924f_Traceguids, v16, v24);
    }
    else
    {
      v60 = (wchar_t *)CallStackTracing::s_wpInstance;
      v24 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
        CallStackTracing::s_wpInstance = v61;
        if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
        {
          v60 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v60 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v60 + 8) )
      {
        v91 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
        if ( *((_DWORD *)v91 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v91, "CMP3Base::BeginDeSerialize", 137, -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_d18bbb785de430394c1967457ee8924f_Traceguids,
          v16,
          -2147024882);
    }
    ComSmartPtr<CBaseStreamSink>::operator=(v16 + 48);
    goto LABEL_80;
  }
  v24 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v93 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v93 + 499) != -2147024882 )
      CallStackContext::TraceFailure(v93, "CMP3BytewiseMediaSource::ReadNextFrame", 2693, -2147024882);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      225,
      &WPP_a1add6380c0f3817e43b5b33a615088f_Traceguids,
      this,
      -2147024882);
LABEL_86:
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v56 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v57 = *((_DWORD *)v56 + 497);
    if ( v57 )
    {
      v58 = v57 - 1;
      *((_DWORD *)v56 + 497) = v58;
      if ( !v58 )
        CallStackContext::ClearState(v56);
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18001afb8  push    rbp
0x18001afba  push    rbx
0x18001afbb  push    rsi
0x18001afbc  push    rdi
0x18001afbd  push    r12
0x18001afbf  push    r13
0x18001afc1  push    r14
0x18001afc3  push    r15
0x18001afc5  mov     rbp, rsp
0x18001afc8  sub     rsp, 58h
0x18001afcc  mov     rsi, rcx
0x18001afcf  xor     r13d, r13d
0x18001afd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001afd9  test    rcx, rcx
0x18001afdc  jz      loc_18001B6D4
0x18001afe2  lea     rbx, aCmp3bytewiseme_55; "CMP3BytewiseMediaSource::ReadNextFrame"
0x18001afe9  mov     r14d, 1
0x18001afef  cmp     [rcx+8], r13b
0x18001aff3  jz      loc_18001B091
0x18001aff9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001affe  mov     ecx, [rax+7C4h]
0x18001b004  cmp     ecx, [rax+7C8h]
0x18001b00a  jnb     short loc_18001B01B
0x18001b00c  add     rcx, rcx
0x18001b00f  mov     [rax+rcx*8], rbx
0x18001b013  mov     dword ptr [rax+rcx*8+8], 0A3Bh
0x18001b01b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b022  add     [rax+7C4h], r14d
0x18001b029  cmp     [rcx+8], r13b
0x18001b02d  jz      short loc_18001B091
0x18001b02f  cmp     [rsi+458h], r13
0x18001b036  jz      short loc_18001B091
0x18001b038  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b03d  mov     rcx, [rsi+458h]
0x18001b044  mov     rdi, rax
0x18001b047  mov     rdx, [rcx]
0x18001b04a  mov     rax, [rdx+128h]
0x18001b051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b056  mov     rcx, [rsi+458h]
0x18001b05d  mov     ebx, eax
0x18001b05f  mov     rdx, [rcx]
0x18001b062  mov     rax, [rdx+118h]
0x18001b069  lea     rdx, [rbp+var_18]
0x18001b06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b072  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b079  movups  xmm0, xmmword ptr [rax]
0x18001b07c  mov     [rdi+7E0h], ebx
0x18001b082  lea     rbx, aCmp3bytewiseme_55; "CMP3BytewiseMediaSource::ReadNextFrame"
0x18001b089  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001b091  cmp     [rsi+348h], r13d
0x18001b098  jz      loc_18001BD73
0x18001b09e  lea     r15, qword_1801B97E0
0x18001b0a5  mov     r12d, 7F0h
0x18001b0ab  cmp     [rsi+3F8h], r13
0x18001b0b2  jnz     loc_18001B25A
0x18001b0b8  lea     r14, [rsi+28h]
0x18001b0bc  mov     [rbp+var_20], r13
0x18001b0c0  mov     rcx, r14; lpCriticalSection
0x18001b0c3  call    cs:__imp_EnterCriticalSection
0x18001b0ca  nop     dword ptr [rax+rax+00h]
0x18001b0cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b0d6  test    rcx, rcx
0x18001b0d9  jz      loc_18001B729
0x18001b0df  lea     rbx, aCmediasourceba_16; "CMediaSourceBase::GetActiveMediaStreamB"...
0x18001b0e6  cmp     [rcx+8], r13b
0x18001b0ea  jz      short loc_18001B11B
0x18001b0ec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b0f1  mov     ecx, [rax+7C4h]
0x18001b0f7  cmp     ecx, [rax+7C8h]
0x18001b0fd  jnb     short loc_18001B10E
0x18001b0ff  add     rcx, rcx
0x18001b102  mov     [rax+rcx*8], rbx
0x18001b106  mov     dword ptr [rax+rcx*8+8], 6B2h
0x18001b10e  inc     dword ptr [rax+7C4h]
0x18001b114  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b11b  cmp     [rsi+2B8h], r13d
0x18001b122  jbe     loc_18001B8CD
0x18001b128  mov     rbx, [rsi+2A8h]
0x18001b12f  test    rbx, rbx
0x18001b132  jz      loc_18001B912
0x18001b138  mov     rbx, [rbx]
0x18001b13b  mov     [rbp+var_20], rbx
0x18001b13f  test    rbx, rbx
0x18001b142  jz      short loc_18001B153
0x18001b144  mov     rax, [rbx]
0x18001b147  mov     rcx, rbx
0x18001b14a  mov     rax, [rax+8]
0x18001b14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b153  lea     rcx, [rbp+var_28]; this
0x18001b157  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001b15c  mov     rcx, r14; lpCriticalSection
0x18001b15f  call    cs:__imp_LeaveCriticalSection
0x18001b166  nop     dword ptr [rax+rax+00h]
0x18001b16b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b172  test    rcx, rcx
0x18001b175  jz      loc_18001B73A
0x18001b17b  lea     rdi, aCmediasourceba_2; "CMediaSourceBase::IsSampleNeeded"
0x18001b182  cmp     [rcx+8], r13b
0x18001b186  jz      loc_18001B823
0x18001b18c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b191  mov     ecx, [rax+7C4h]
0x18001b197  cmp     ecx, [rax+7C8h]
0x18001b19d  jnb     short loc_18001B1AE
0x18001b19f  add     rcx, rcx
0x18001b1a2  mov     [rax+rcx*8], rdi
0x18001b1a6  mov     dword ptr [rax+rcx*8+8], 603h
0x18001b1ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001b1b5  mov     r14d, 1
0x18001b1bb  add     [rax+7C4h], r14d
0x18001b1c2  cmp     [rsi+0C4h], r13d
0x18001b1c9  jnz     loc_18001B777
0x18001b1cf  test    rbx, rbx
0x18001b1d2  jz      loc_18001B9AD
0x18001b1d8  cmp     dword ptr [rsi+0C8h], 2
0x18001b1df  jz      loc_18001B805
0x18001b1e5  mov     rax, [rbx]
0x18001b1e8  mov     rcx, rbx
0x18001b1eb  mov     rax, [rax+70h]
0x18001b1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1f4  mov     edi, eax
0x18001b1f6  test    eax, eax
0x18001b1f8  js      loc_18001B9E9
0x18001b1fe  cmp     [rsi+0C8h], r13d
0x18001b205  jz      loc_18001B777
0x18001b20b  mov     rcx, rbx; this
0x18001b20e  call    ?HasOutstandingRequests@CBytewiseMediaStream@@QEAAHXZ; CBytewiseMediaStream::HasOutstandingRequests(void)
0x18001b213  test    eax, eax
0x18001b215  jz      loc_18001B74B
0x18001b21b  cmp     cs:byte_1801BA10B, 10h
0x18001b222  jnb     loc_18001C007
0x18001b228  lea     rcx, [rbp+var_28]; this
0x18001b22c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001b231  test    edi, edi
0x18001b233  js      loc_18001BA27
0x18001b239  jnz     loc_18001B7C6
0x18001b23f  test    rbx, rbx
0x18001b242  jz      short loc_18001B253
0x18001b244  mov     rax, [rbx]
0x18001b247  mov     rcx, rbx
0x18001b24a  mov     rax, [rax+10h]
0x18001b24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b253  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b25a  mov     rbx, [rsi+400h]
0x18001b261  test    rcx, rcx
0x18001b264  jz      loc_18001B6E5
0x18001b26a  lea     rdi, aCbytestreamcac_21; "CByteStreamCacheReaderEx::GetCurrentPos"...
0x18001b271  cmp     [rcx+8], r13b
0x18001b275  jz      short loc_18001B2A0
0x18001b277  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b27c  mov     ecx, [rax+7C4h]
0x18001b282  cmp     ecx, [rax+7C8h]
0x18001b288  jnb     short loc_18001B299
0x18001b28a  add     rcx, rcx
0x18001b28d  mov     [rax+rcx*8], rdi
0x18001b291  mov     dword ptr [rax+rcx*8+8], 1B7h
0x18001b299  add     [rax+7C4h], r14d
0x18001b2a0  lea     rdi, [rbx+238h]
0x18001b2a7  mov     rcx, rdi; lpCriticalSection
0x18001b2aa  call    cs:__imp_EnterCriticalSection
0x18001b2b1  nop     dword ptr [rax+rax+00h]
0x18001b2b6  mov     r14, [rbx+200h]
0x18001b2bd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18001b2c1  jnz     short loc_18001B2CA
0x18001b2c3  mov     r14, [rbx+1F8h]
0x18001b2ca  mov     rcx, rdi; lpCriticalSection
0x18001b2cd  call    cs:__imp_LeaveCriticalSection
0x18001b2d4  nop     dword ptr [rax+rax+00h]
0x18001b2d9  lea     rcx, [rbp+var_28]; this
0x18001b2dd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001b2e2  cmp     r14, [rsi+328h]
0x18001b2e9  jz      loc_18001B7CE
0x18001b2ef  mov     ecx, 160h; Size
0x18001b2f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b2f9  mov     rbx, rax
0x18001b2fc  test    rax, rax
0x18001b2ff  jz      loc_18001B82E
0x18001b305  mov     rdi, [rsi+400h]
0x18001b30c  lea     rax, ??_7CMP3Base@@6B@; const CMP3Base::`vftable'
0x18001b313  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b31a  mov     [rbx], rax
0x18001b31d  mov     [rbx+28h], r13
0x18001b321  mov     [rbx+30h], r13
0x18001b325  test    rcx, rcx
0x18001b328  jz      loc_18001B6F6
0x18001b32e  cmp     [rcx+8], r13b
0x18001b332  jz      short loc_18001B363
0x18001b334  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b339  mov     ecx, [rax+7C4h]
0x18001b33f  cmp     ecx, [rax+7C8h]
0x18001b345  jnb     short loc_18001B35D
0x18001b347  add     rcx, rcx
0x18001b34a  lea     rdx, aCmp3baseCmp3ba; "CMP3Base::CMP3Base"
0x18001b351  mov     [rax+rcx*8], rdx
0x18001b355  mov     dword ptr [rax+rcx*8+8], 1Fh
0x18001b35d  inc     dword ptr [rax+7C4h]
0x18001b363  mov     [rbx+20h], r13d
0x18001b367  mov     [rbx+8], r13
0x18001b36b  mov     [rbx+10h], r13d
0x18001b36f  mov     [rbx+18h], r13
0x18001b373  test    rdi, rdi
0x18001b376  jz      loc_18001C06A
0x18001b37c  mov     rax, [rdi]
0x18001b37f  mov     rcx, rdi
0x18001b382  mov     rax, [rax+8]
0x18001b386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b38b  mov     rcx, [rbx+28h]
0x18001b38f  test    rcx, rcx
0x18001b392  jnz     loc_18001C08C
0x18001b398  mov     [rbx+28h], rdi
0x18001b39c  lea     rcx, [rbp+var_28]; this
0x18001b3a0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001b3a5  lea     rax, ??_7CMPEGFrame@@6B@; const CMPEGFrame::`vftable'
0x18001b3ac  mov     [rbx], rax
0x18001b3af  lea     rcx, [rbx+148h]; this
0x18001b3b6  mov     [rbx+80h], r13
0x18001b3bd  call    ??0OnHeaderReadAsyncCallback@CMPEGFrame@@QEAA@XZ; CMPEGFrame::OnHeaderReadAsyncCallback::OnHeaderReadAsyncCallback(void)
0x18001b3c2  lea     rcx, [rbx+150h]; this
0x18001b3c9  call    ??0OnFrameReadAsyncCallback@CMPEGFrame@@QEAA@XZ; CMPEGFrame::OnFrameReadAsyncCallback::OnFrameReadAsyncCallback(void)
0x18001b3ce  xor     edx, edx; Val
0x18001b3d0  mov     dword ptr [rbx+10h], 0Ah
0x18001b3d7  lea     rcx, [rbx+0B4h]; void *
0x18001b3de  mov     [rbx+38h], r13
0x18001b3e2  mov     [rbx+40h], r13
0x18001b3e6  mov     [rbx+48h], r13
0x18001b3ea  lea     r8d, [rdx+64h]; Size
0x18001b3ee  mov     [rbx+50h], r13
0x18001b3f2  mov     [rbx+58h], r13
0x18001b3f6  mov     [rbx+60h], r13
0x18001b3fa  mov     [rbx+68h], r13
0x18001b3fe  mov     [rbx+70h], r13
0x18001b402  mov     [rbx+78h], r13d
0x18001b406  mov     [rbx+88h], r13
0x18001b40d  mov     [rbx+90h], r13
0x18001b414  mov     [rbx+98h], r13
0x18001b41b  mov     [rbx+0A0h], r13
0x18001b422  mov     [rbx+0A8h], r13
0x18001b429  mov     [rbx+0B0h], r13d
0x18001b430  call    memset_0
0x18001b435  mov     [rbx+118h], r13
0x18001b43c  xor     eax, eax
0x18001b43e  mov     [rbx+120h], r13
0x18001b445  xorps   xmm0, xmm0
0x18001b448  mov     [rbx+158h], r13
0x18001b44f  mov     rcx, rbx
0x18001b452  movups  xmmword ptr [rbx+12Ch], xmm0
0x18001b459  mov     [rbx+13Ch], rax
0x18001b460  mov     [rbx+128h], r13d
0x18001b467  mov     rax, [rbx]
0x18001b46a  mov     [rbp+var_20], rbx
0x18001b46e  mov     rax, [rax+8]
0x18001b472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b477  mov     rcx, [rsi+400h]; this
0x18001b47e  call    ?PushPosition@CByteStreamCacheReaderEx@@QEAAJXZ; CByteStreamCacheReaderEx::PushPosition(void)
0x18001b483  mov     edi, eax
0x18001b485  test    eax, eax
0x18001b487  js      loc_18001BA65
0x18001b48d  cmp     [rsi+3E8h], r13
0x18001b494  jz      loc_18001C106
0x18001b49a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001b4a1  test    rcx, rcx
0x18001b4a4  jz      loc_18001B707
0x18001b4aa  lea     rdi, aCmp3baseBegind; "CMP3Base::BeginDeSerialize"
0x18001b4b1  cmp     [rcx+8], r13b
0x18001b4b5  jz      short loc_18001B4DF
0x18001b4b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001b4bc  mov     ecx, [rax+7C4h]
0x18001b4c2  cmp     ecx, [rax+7C8h]
0x18001b4c8  jnb     short loc_18001B4D9
0x18001b4ca  add     rcx, rcx
0x18001b4cd  mov     [rax+rcx*8], rdi
0x18001b4d1  mov     dword ptr [rax+rcx*8+8], 81h
0x18001b4d9  inc     dword ptr [rax+7C4h]
0x18001b4df  mov     ecx, 68h ; 'h'; Size
0x18001b4e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b4e9  mov     rdi, rax
0x18001b4ec  test    rax, rax
0x18001b4ef  jz      loc_18001B77F
0x18001b4f5  mov     rcx, rax; this
0x18001b4f8  call    ??0tagMFASYNCRESULT@@QEAA@XZ; tagMFASYNCRESULT::tagMFASYNCRESULT(void)
0x18001b4fd  lea     rax, ??_7CMFRefCounted@@6B@; const CMFRefCounted::`vftable'
0x18001b504  mov     [rcx+40h], rax
0x18001b508  lea     rax, ??_7CMP3ByteStreamPluginResult@@6BtagMFASYNCRESULT@@@; const CMP3ByteStreamPluginResult::`vftable'{for `tagMFASYNCRESULT'}
0x18001b50f  mov     [rcx+48h], r13d
0x18001b513  mov     [rcx], rax
0x18001b516  lea     rax, ??_7CAsyncResult@@6BCMFRefCounted@@@; const CAsyncResult::`vftable'{for `CMFRefCounted'}
0x18001b51d  mov     [rcx+40h], rax
0x18001b521  mov     [rcx+60h], r13d
0x18001b525  call    cs:__imp_MFLockPlatform
0x18001b52c  nop     dword ptr [rax+rax+00h]
0x18001b531  lea     rcx, [rsi+428h]
0x18001b538  mov     [rdi+64h], r13d
0x18001b53c  mov     [rdi+30h], r13d
0x18001b540  mov     [rdi+38h], r13
0x18001b544  mov     [rdi+50h], r13
0x18001b548  mov     [rdi+58h], r13
0x18001b54c  mov     [rdi+28h], rcx
0x18001b550  test    rcx, rcx
0x18001b553  jz      short loc_18001B561
0x18001b555  mov     rax, [rcx]
0x18001b558  mov     rax, [rax+8]
  ... truncated ...
```
