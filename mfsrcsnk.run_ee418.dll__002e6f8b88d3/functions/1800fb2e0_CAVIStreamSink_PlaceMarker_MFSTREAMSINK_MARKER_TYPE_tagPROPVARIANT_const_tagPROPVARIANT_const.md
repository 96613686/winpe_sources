# CAVIStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800fb2e0`
- end: `0x1800fba26`
- name: `?PlaceMarker@CAVIStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z`
- size: `1862`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, enum _MFSTREAMSINK_MARKER_TYPE, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800734a8`
- `0x180073b14`
- `0x18009e1a0`
- `0x1800fb2e0`
- `0x1801095a8`
- `0x180125f30`
- `0x1801284a8`
- `0x180128690`
- `0x1801292b8`
- `0x18012b0dc`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb3eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb8a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb9fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb3eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb8a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb9fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb577`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb845`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb577`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb845`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb351`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb4ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb5b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb66f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb7b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb8c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb960`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb351`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb418`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb4ea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb5b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb66f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb7b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb8c7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800fb960`

## string_xrefs

- `0x1800fb2fd`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb3a8`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb46f`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb541`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb60b`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb6c6`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb80f`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb91e`: `CAVIStreamSink::PlaceMarker`
- `0x1800fb9b7`: `CAVIStreamSink::PlaceMarker`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::PlaceMarker(
        struct _RTL_CRITICAL_SECTION *this,
        enum _MFSTREAMSINK_MARKER_TYPE a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  HANDLE *p_LockSemaphore; // r15
  wchar_t *v13; // rcx
  int SamplesPerSecond; // ebx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  HANDLE v40; // r8
  unsigned __int64 v41; // rdx
  __int64 v42; // rdx
  double v43; // xmm0_8
  CAVIStreamSink::StreamSampleQueueEntry *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  _QWORD *v48; // rax
  _QWORD *v49; // rcx
  wchar_t *v50; // rcx
  CallStackTracing *v51; // rax
  struct CallStackContext *v52; // rax
  __int64 v53; // rdx
  CAVIStreamSink::StreamSampleQueueEntry *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  _QWORD *v58; // rax
  _QWORD *SpinCount; // rdx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  wchar_t *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  wchar_t *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  unsigned __int64 v70; // [rsp+30h] [rbp-38h] BYREF
  double v71; // [rsp+38h] [rbp-30h] BYREF
  struct tagPROPVARIANT v72; // [rsp+40h] [rbp-28h] BYREF
  CAVIMediaSink *v73; // [rsp+B0h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v73, "CAVIStreamSink::PlaceMarker", 631);
  v8 = this + 14;
  v73 = 0;
  EnterCriticalSection(this + 14);
  p_LockSemaphore = &this[-1].LockSemaphore;
  if ( !this[9].DebugInfo )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -1072870856;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10, v11);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072870856 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::PlaceMarker", 636, -1072870856);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v17 = 121;
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(&v73, &this[9]);
  LeaveCriticalSection(this + 14);
  SamplesPerSecond = CBaseStreamSink::PlaceMarker((CBaseStreamSink *)this, a2, a3, a4);
  if ( SamplesPerSecond < 0 )
  {
    v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v22;
      if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
      {
        v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v21 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v21 + 8) )
    {
      v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
      if ( *((_DWORD *)v23 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v23, "CAVIStreamSink::PlaceMarker", 641, SamplesPerSecond);
    }
    if ( g_wppLevels )
    {
      v24 = 122;
LABEL_24:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        &this[-1].LockSemaphore,
        SamplesPerSecond);
      goto LABEL_108;
    }
    goto LABEL_108;
  }
  if ( a2 != MFSTREAMSINK_MARKER_TICK )
  {
    v8 = this + 13;
    EnterCriticalSection(this + 13);
    v54 = (CAVIStreamSink::StreamSampleQueueEntry *)operator new(0x70u);
    if ( v54 )
    {
      v58 = (_QWORD *)CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(v54, a2, a3, a4, 0);
      if ( v58 )
      {
        SpinCount = (_QWORD *)this[12].SpinCount;
        *v58 = (char *)this + 504;
        v58[1] = SpinCount;
        *SpinCount = v58;
        this[12].SpinCount = (ULONG_PTR)v58;
        goto LABEL_85;
      }
    }
    v66 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56, v57);
      CallStackTracing::s_wpInstance = v67;
      if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
      {
        v66 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v66 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v66 + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
      if ( *((_DWORD *)v68 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v68, "CAVIStreamSink::PlaceMarker", 689, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v53 = 127;
LABEL_106:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v53,
      &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
      p_LockSemaphore,
      -2147024882);
    goto LABEL_107;
  }
  if ( !a3 || a3->vt == 20 )
  {
    v8 = this + 13;
    EnterCriticalSection(this + 13);
    v71 = 0.0;
    memset(&v72, 0, sizeof(v72));
    SamplesPerSecond = CAVIStreamSink::GetSamplesPerSecond((CAVIStreamSink *)&this[-1].LockSemaphore, &v71);
    if ( SamplesPerSecond < 0 )
    {
      v31 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29, v30);
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
        if ( *((_DWORD *)v33 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v33, "CAVIStreamSink::PlaceMarker", 651, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v17 = 123;
      goto LABEL_12;
    }
    v72.vt = 19;
    if ( !a3 )
      goto LABEL_68;
    v70 = 0;
    SamplesPerSecond = CAVIStreamSink::GetFrameDuration((CAVIStreamSink *)&this[-1].LockSemaphore, &v70);
    if ( SamplesPerSecond < 0 )
    {
      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v37 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v37 + 8) )
      {
        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
        if ( *((_DWORD *)v39 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v39, "CAVIStreamSink::PlaceMarker", 661, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v17 = 124;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        p_LockSemaphore,
        SamplesPerSecond);
LABEL_107:
      LeaveCriticalSection(v8);
      goto LABEL_108;
    }
    v40 = 0;
    if ( (__int64)p_LockSemaphore[61] > 0 )
      v40 = p_LockSemaphore[61];
    v41 = v70 + a3->hVal.QuadPart;
    if ( v41 > (unsigned __int64)v40 )
    {
      v42 = v41 - (_QWORD)v40;
      if ( v42 < 0 )
        v43 = (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1))
            + (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1));
      else
        v43 = (double)(int)v42;
      v72.lVal = (int)(v43 * v71 / 10000000.0 + 0.9);
    }
    else
    {
LABEL_68:
      v72.lVal = 1;
    }
    v44 = (CAVIStreamSink::StreamSampleQueueEntry *)operator new(0x70u);
    if ( v44 )
    {
      v48 = (_QWORD *)CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(
                        v44,
                        MFSTREAMSINK_MARKER_TICK,
                        &v72,
                        a4,
                        1);
      if ( v48 )
      {
        v49 = (_QWORD *)this[12].SpinCount;
        *v48 = (char *)this + 504;
        v48[1] = v49;
        *v49 = v48;
        this[12].SpinCount = (ULONG_PTR)v48;
LABEL_85:
        ++LODWORD(this[12].OwningThread);
        LeaveCriticalSection(v8);
        SamplesPerSecond = CAVIMediaSink::NotifySampleReceived(v73);
        if ( SamplesPerSecond < 0 )
        {
          v63 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v60, v61, v62);
            CallStackTracing::s_wpInstance = v64;
            if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
            {
              v63 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v63 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v63 + 8) )
          {
            v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
            if ( *((_DWORD *)v65 + 499) != SamplesPerSecond )
              CallStackContext::TraceFailure(v65, "CAVIStreamSink::PlaceMarker", 693, SamplesPerSecond);
          }
          if ( g_wppLevels )
          {
            v24 = 128;
            goto LABEL_24;
          }
        }
        goto LABEL_108;
      }
    }
    v50 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45, v46, v47);
      CallStackTracing::s_wpInstance = v51;
      if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
      {
        v50 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v50 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v50 + 8) )
    {
      v52 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v50);
      if ( *((_DWORD *)v52 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v52, "CAVIStreamSink::PlaceMarker", 677, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v53 = 125;
    goto LABEL_106;
  }
  v25 = (wchar_t *)CallStackTracing::s_wpInstance;
  SamplesPerSecond = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
    if ( *((_DWORD *)v27 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v27, "CAVIStreamSink::PlaceMarker", 682, -2147024809);
  }
  if ( g_wppLevels )
  {
    v24 = 126;
    goto LABEL_24;
  }
LABEL_108:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v73);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v73);
  return (unsigned int)SamplesPerSecond;
}

```

## disassembly

```asm
0x1800fb2e0  push    rbp
0x1800fb2e2  push    rbx
0x1800fb2e3  push    rsi
0x1800fb2e4  push    rdi
0x1800fb2e5  push    r12
0x1800fb2e7  push    r13
0x1800fb2e9  push    r14
0x1800fb2eb  push    r15
0x1800fb2ed  mov     rbp, rsp
0x1800fb2f0  sub     rsp, 68h
0x1800fb2f4  mov     rsi, r8
0x1800fb2f7  mov     r12d, edx
0x1800fb2fa  mov     rdi, rcx
0x1800fb2fd  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb304  mov     r8d, 277h; int
0x1800fb30a  lea     rcx, [rbp+arg_0]; this
0x1800fb30e  mov     r13, r9
0x1800fb311  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800fb316  lea     r14, [rdi+230h]
0x1800fb31d  mov     [rbp+arg_0], 0
0x1800fb325  mov     rcx, r14; lpCriticalSection
0x1800fb328  call    cs:__imp_EnterCriticalSection
0x1800fb32e  lea     r15, [rdi-10h]
0x1800fb332  cmp     qword ptr [r15+178h], 0
0x1800fb33a  jnz     loc_1800FB3D8
0x1800fb340  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb347  mov     ebx, 0C00D4A38h
0x1800fb34c  test    rcx, rcx
0x1800fb34f  jnz     short loc_1800FB392
0x1800fb351  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb357  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb35e  mov     rcx, rax
0x1800fb361  test    rax, rax
0x1800fb364  jz      short loc_1800FB384
0x1800fb366  mov     rax, [rax]
0x1800fb369  mov     edx, 7F0h
0x1800fb36e  mov     rax, [rax+8]
0x1800fb372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb377  test    eax, eax
0x1800fb379  jz      short loc_1800FB384
0x1800fb37b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb382  jmp     short loc_1800FB392
0x1800fb384  lea     rcx, qword_1801B07E0; this
0x1800fb38b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb392  cmp     byte ptr [rcx+8], 0
0x1800fb396  jz      short loc_1800FB3BD
0x1800fb398  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fb39d  cmp     [rax+7CCh], ebx
0x1800fb3a3  jz      short loc_1800FB3BD
0x1800fb3a5  mov     r9d, ebx; int
0x1800fb3a8  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb3af  mov     r8d, 27Ch; int
0x1800fb3b5  mov     rcx, rax; this
0x1800fb3b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fb3bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fb3c4  jb      loc_1800FB9F8
0x1800fb3ca  mov     edx, 79h ; 'y'
0x1800fb3cf  mov     dword ptr [rsp+68h+var_48], ebx
0x1800fb3d3  jmp     loc_1800FB9DE
0x1800fb3d8  lea     rdx, [rdi+168h]
0x1800fb3df  lea     rcx, [rbp+arg_0]
0x1800fb3e3  call    ??4?$ComPtr@VCAVIMediaSink@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(Microsoft::WRL::ComPtr<CAVIMediaSink> const &)
0x1800fb3e8  mov     rcx, r14; lpCriticalSection
0x1800fb3eb  call    cs:__imp_LeaveCriticalSection
0x1800fb3f1  mov     r9, r13; struct tagPROPVARIANT *
0x1800fb3f4  mov     r8, rsi; struct tagPROPVARIANT *
0x1800fb3f7  mov     edx, r12d; enum _MFSTREAMSINK_MARKER_TYPE
0x1800fb3fa  mov     rcx, rdi; this
0x1800fb3fd  call    ?PlaceMarker@CBaseStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z; CBaseStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1800fb402  mov     ebx, eax
0x1800fb404  test    eax, eax
0x1800fb406  jns     loc_1800FB4B9
0x1800fb40c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb413  test    rcx, rcx
0x1800fb416  jnz     short loc_1800FB459
0x1800fb418  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb41e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb425  mov     rcx, rax
0x1800fb428  test    rax, rax
0x1800fb42b  jz      short loc_1800FB44B
0x1800fb42d  mov     rax, [rax]
0x1800fb430  mov     edx, 7F0h
0x1800fb435  mov     rax, [rax+8]
0x1800fb439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb43e  test    eax, eax
0x1800fb440  jz      short loc_1800FB44B
0x1800fb442  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb449  jmp     short loc_1800FB459
0x1800fb44b  lea     rcx, qword_1801B07E0; this
0x1800fb452  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb459  cmp     byte ptr [rcx+8], 0
0x1800fb45d  jz      short loc_1800FB484
0x1800fb45f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fb464  cmp     [rax+7CCh], ebx
0x1800fb46a  jz      short loc_1800FB484
0x1800fb46c  mov     r9d, ebx; int
0x1800fb46f  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb476  mov     r8d, 281h; int
0x1800fb47c  mov     rcx, rax; this
0x1800fb47f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fb484  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fb48b  jb      loc_1800FBA01
0x1800fb491  mov     edx, 7Ah ; 'z'
0x1800fb496  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb49d  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800fb4a4  mov     r9, r15
0x1800fb4a7  mov     dword ptr [rsp+68h+var_48], ebx
0x1800fb4ab  mov     rcx, [rcx+10h]
0x1800fb4af  call    WPP_SF_qD
0x1800fb4b4  jmp     loc_1800FBA01
0x1800fb4b9  cmp     r12d, 2
0x1800fb4bd  jnz     loc_1800FB83B
0x1800fb4c3  xor     r12d, r12d
0x1800fb4c6  test    rsi, rsi
0x1800fb4c9  jz      loc_1800FB56D
0x1800fb4cf  cmp     word ptr [rsi], 14h
0x1800fb4d3  jz      loc_1800FB56D
0x1800fb4d9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb4e0  mov     ebx, 80070057h
0x1800fb4e5  test    rcx, rcx
0x1800fb4e8  jnz     short loc_1800FB52B
0x1800fb4ea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb4f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb4f7  mov     rcx, rax
0x1800fb4fa  test    rax, rax
0x1800fb4fd  jz      short loc_1800FB51D
0x1800fb4ff  mov     rax, [rax]
0x1800fb502  mov     edx, 7F0h
0x1800fb507  mov     rax, [rax+8]
0x1800fb50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb510  test    eax, eax
0x1800fb512  jz      short loc_1800FB51D
0x1800fb514  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb51b  jmp     short loc_1800FB52B
0x1800fb51d  lea     rcx, qword_1801B07E0; this
0x1800fb524  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb52b  cmp     [rcx+8], r12b
0x1800fb52f  jz      short loc_1800FB556
0x1800fb531  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fb536  cmp     [rax+7CCh], ebx
0x1800fb53c  jz      short loc_1800FB556
0x1800fb53e  mov     r9d, ebx; int
0x1800fb541  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb548  mov     r8d, 2AAh; int
0x1800fb54e  mov     rcx, rax; this
0x1800fb551  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fb556  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fb55d  jb      loc_1800FBA01
0x1800fb563  mov     edx, 7Eh ; '~'
0x1800fb568  jmp     loc_1800FB496
0x1800fb56d  lea     r14, [rdi+208h]
0x1800fb574  mov     rcx, r14; lpCriticalSection
0x1800fb577  call    cs:__imp_EnterCriticalSection
0x1800fb57d  xorps   xmm0, xmm0
0x1800fb580  lea     rdx, [rbp+var_30]; double *
0x1800fb584  xorps   xmm1, xmm1
0x1800fb587  movsd   [rbp+var_30], xmm0
0x1800fb58c  xor     eax, eax
0x1800fb58e  mov     rcx, r15; this
0x1800fb591  movups  xmmword ptr [rbp+var_28], xmm1
0x1800fb595  mov     qword ptr [rbp+var_28+10h], rax
0x1800fb599  call    ?GetSamplesPerSecond@CAVIStreamSink@@AEAAJPEAN@Z; CAVIStreamSink::GetSamplesPerSecond(double *)
0x1800fb59e  mov     ebx, eax
0x1800fb5a0  test    eax, eax
0x1800fb5a2  jns     loc_1800FB637
0x1800fb5a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb5af  test    rcx, rcx
0x1800fb5b2  jnz     short loc_1800FB5F5
0x1800fb5b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb5ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb5c1  mov     rcx, rax
0x1800fb5c4  test    rax, rax
0x1800fb5c7  jz      short loc_1800FB5E7
0x1800fb5c9  mov     rax, [rax]
0x1800fb5cc  mov     edx, 7F0h
0x1800fb5d1  mov     rax, [rax+8]
0x1800fb5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb5da  test    eax, eax
0x1800fb5dc  jz      short loc_1800FB5E7
0x1800fb5de  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb5e5  jmp     short loc_1800FB5F5
0x1800fb5e7  lea     rcx, qword_1801B07E0; this
0x1800fb5ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb5f5  cmp     [rcx+8], r12b
0x1800fb5f9  jz      short loc_1800FB620
0x1800fb5fb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fb600  cmp     [rax+7CCh], ebx
0x1800fb606  jz      short loc_1800FB620
0x1800fb608  mov     r9d, ebx; int
0x1800fb60b  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb612  mov     r8d, 28Bh; int
0x1800fb618  mov     rcx, rax; this
0x1800fb61b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fb620  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fb627  jb      loc_1800FB9F8
0x1800fb62d  mov     edx, 7Bh ; '{'
0x1800fb632  jmp     loc_1800FB3CF
0x1800fb637  mov     eax, 13h
0x1800fb63c  mov     word ptr [rbp+var_28], ax
0x1800fb640  test    rsi, rsi
0x1800fb643  jz      loc_1800FB753
0x1800fb649  lea     rdx, [rbp+var_38]; unsigned __int64 *
0x1800fb64d  mov     [rbp+var_38], r12
0x1800fb651  mov     rcx, r15; this
0x1800fb654  call    ?GetFrameDuration@CAVIStreamSink@@AEAAJPEA_K@Z; CAVIStreamSink::GetFrameDuration(unsigned __int64 *)
0x1800fb659  mov     ebx, eax
0x1800fb65b  test    eax, eax
0x1800fb65d  jns     loc_1800FB6F2
0x1800fb663  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb66a  test    rcx, rcx
0x1800fb66d  jnz     short loc_1800FB6B0
0x1800fb66f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb675  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb67c  mov     rcx, rax
0x1800fb67f  test    rax, rax
0x1800fb682  jz      short loc_1800FB6A2
0x1800fb684  mov     rax, [rax]
0x1800fb687  mov     edx, 7F0h
0x1800fb68c  mov     rax, [rax+8]
0x1800fb690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb695  test    eax, eax
0x1800fb697  jz      short loc_1800FB6A2
0x1800fb699  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb6a0  jmp     short loc_1800FB6B0
0x1800fb6a2  lea     rcx, qword_1801B07E0; this
0x1800fb6a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb6b0  cmp     [rcx+8], r12b
0x1800fb6b4  jz      short loc_1800FB6DB
0x1800fb6b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800fb6bb  cmp     [rax+7CCh], ebx
0x1800fb6c1  jz      short loc_1800FB6DB
0x1800fb6c3  mov     r9d, ebx; int
0x1800fb6c6  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1800fb6cd  mov     r8d, 295h; int
0x1800fb6d3  mov     rcx, rax; this
0x1800fb6d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800fb6db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800fb6e2  jb      loc_1800FB9F8
0x1800fb6e8  mov     edx, 7Ch ; '|'
0x1800fb6ed  jmp     loc_1800FB3CF
0x1800fb6f2  mov     rax, [r15+1E8h]
0x1800fb6f9  mov     r8, r12
0x1800fb6fc  mov     rdx, [rsi+8]
0x1800fb700  test    rax, rax
0x1800fb703  cmovg   r8, rax
0x1800fb707  add     rdx, [rbp+var_38]
0x1800fb70b  cmp     rdx, r8
0x1800fb70e  jbe     short loc_1800FB753
0x1800fb710  sub     rdx, r8
0x1800fb713  xorps   xmm0, xmm0
0x1800fb716  js      short loc_1800FB71F
0x1800fb718  cvtsi2sd xmm0, rdx
0x1800fb71d  jmp     short loc_1800FB734
0x1800fb71f  mov     rax, rdx
0x1800fb722  and     edx, 1
0x1800fb725  shr     rax, 1
0x1800fb728  or      rax, rdx
0x1800fb72b  cvtsi2sd xmm0, rax
0x1800fb730  addsd   xmm0, xmm0
0x1800fb734  mulsd   xmm0, [rbp+var_30]
0x1800fb739  divsd   xmm0, cs:__real@416312d000000000
0x1800fb741  addsd   xmm0, cs:__real@3feccccccccccccd
0x1800fb749  cvttsd2si rax, xmm0
0x1800fb74e  mov     dword ptr [rbp+var_28+8], eax
0x1800fb751  jmp     short loc_1800FB75A
0x1800fb753  mov     dword ptr [rbp+var_28+8], 1
0x1800fb75a  mov     ecx, 70h ; 'p'; Size
0x1800fb75f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fb764  test    rax, rax
0x1800fb767  jz      short loc_1800FB7A5
0x1800fb769  mov     r9, r13; struct tagPROPVARIANT *
0x1800fb76c  mov     [rsp+68h+var_48], 1; bool
0x1800fb771  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x1800fb775  mov     edx, 2; enum _MFSTREAMSINK_MARKER_TYPE
0x1800fb77a  mov     rcx, rax; this
0x1800fb77d  call    ??0StreamSampleQueueEntry@CAVIStreamSink@@QEAA@W4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1_N@Z; CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *,bool)
0x1800fb782  test    rax, rax
0x1800fb785  jz      short loc_1800FB7A5
0x1800fb787  lea     rdx, [rdi+1F8h]
0x1800fb78e  mov     rcx, [rdx+8]
0x1800fb792  mov     [rax], rdx
0x1800fb795  mov     [rax+8], rcx
0x1800fb799  mov     [rcx], rax
0x1800fb79c  mov     [rdx+8], rax
0x1800fb7a0  jmp     loc_1800FB899
0x1800fb7a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb7ac  mov     edi, 8007000Eh
0x1800fb7b1  mov     ebx, edi
0x1800fb7b3  test    rcx, rcx
0x1800fb7b6  jnz     short loc_1800FB7F9
0x1800fb7b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800fb7be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800fb7c5  mov     rcx, rax
0x1800fb7c8  test    rax, rax
0x1800fb7cb  jz      short loc_1800FB7EB
0x1800fb7cd  mov     rax, [rax]
0x1800fb7d0  mov     edx, 7F0h
0x1800fb7d5  mov     rax, [rax+8]
0x1800fb7d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb7de  test    eax, eax
  ... truncated ...
```
