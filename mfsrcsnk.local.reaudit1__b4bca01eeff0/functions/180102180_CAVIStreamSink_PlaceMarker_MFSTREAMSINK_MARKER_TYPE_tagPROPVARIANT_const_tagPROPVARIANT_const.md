# CAVIStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180102180`
- end: `0x18010291b`
- name: `?PlaceMarker@CAVIStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z`
- size: `1947`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, enum _MFSTREAMSINK_MARKER_TYPE, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x1800790a8`
- `0x180079680`
- `0x1800a3590`
- `0x180102180`
- `0x180110a94`
- `0x18012cf20`
- `0x18012f630`
- `0x18012f824`
- `0x1801304c8`
- `0x1801323d4`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180102297`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010277e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801028e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180102297`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010277e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801028e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801021c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180102435`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010271b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801021c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180102435`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010271b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801021f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801022ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801023a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102539`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801027a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102848`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801021f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801022ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801023a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102539`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102688`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801027a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180102848`

## string_xrefs

- `0x18010219d`: `CAVIStreamSink::PlaceMarker`
- `0x180102254`: `CAVIStreamSink::PlaceMarker`
- `0x180102327`: `CAVIStreamSink::PlaceMarker`
- `0x1801023ff`: `CAVIStreamSink::PlaceMarker`
- `0x1801024d5`: `CAVIStreamSink::PlaceMarker`
- `0x180102596`: `CAVIStreamSink::PlaceMarker`
- `0x1801026e5`: `CAVIStreamSink::PlaceMarker`
- `0x180102806`: `CAVIStreamSink::PlaceMarker`
- `0x1801028a5`: `CAVIStreamSink::PlaceMarker`

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
  HANDLE *p_LockSemaphore; // r15
  wchar_t *v11; // rcx
  int SamplesPerSecond; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  HANDLE v32; // r8
  unsigned __int64 v33; // rdx
  __int64 v34; // rdx
  double v35; // xmm0_8
  CAVIStreamSink::StreamSampleQueueEntry *v36; // rax
  __int64 v37; // rdx
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  CAVIStreamSink::StreamSampleQueueEntry *v44; // rax
  __int64 v45; // rdx
  _QWORD *v46; // rax
  _QWORD *SpinCount; // rdx
  __int64 v48; // rdx
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  unsigned __int64 v56; // [rsp+30h] [rbp-38h] BYREF
  double v57; // [rsp+38h] [rbp-30h] BYREF
  struct tagPROPVARIANT v58; // [rsp+40h] [rbp-28h] BYREF
  CAVIMediaSink *v59; // [rsp+B0h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v59, "CAVIStreamSink::PlaceMarker", 631);
  v8 = this + 14;
  v59 = 0;
  EnterCriticalSection(this + 14);
  p_LockSemaphore = &this[-1].LockSemaphore;
  if ( !this[9].DebugInfo )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -1072870856;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
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
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072870856 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::PlaceMarker", 636, -1072870856);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v15 = 121;
    goto LABEL_12;
  }
  Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(&v59, &this[9]);
  LeaveCriticalSection(this + 14);
  SamplesPerSecond = CBaseStreamSink::PlaceMarker((CBaseStreamSink *)this, a2, a3, a4);
  if ( SamplesPerSecond < 0 )
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
      if ( *((_DWORD *)v19 + 499) != SamplesPerSecond )
        CallStackContext::TraceFailure(v19, "CAVIStreamSink::PlaceMarker", 641, SamplesPerSecond);
    }
    if ( g_wppLevels )
    {
      v20 = 122;
LABEL_24:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
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
    v44 = (CAVIStreamSink::StreamSampleQueueEntry *)operator new(0x70u);
    if ( v44 )
    {
      v46 = (_QWORD *)CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(v44, a2, a3, a4, 0);
      if ( v46 )
      {
        SpinCount = (_QWORD *)this[12].SpinCount;
        *v46 = (char *)this + 504;
        v46[1] = SpinCount;
        *SpinCount = v46;
        this[12].SpinCount = (ULONG_PTR)v46;
        goto LABEL_85;
      }
    }
    v52 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
      CallStackTracing::s_wpInstance = v53;
      if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v52 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v52 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
      if ( *((_DWORD *)v54 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v54, "CAVIStreamSink::PlaceMarker", 689, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v43 = 127;
LABEL_106:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v43,
      &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
      p_LockSemaphore,
      -2147024882);
    goto LABEL_107;
  }
  if ( !a3 || a3->vt == 20 )
  {
    v8 = this + 13;
    EnterCriticalSection(this + 13);
    v57 = 0.0;
    memset(&v58, 0, sizeof(v58));
    SamplesPerSecond = CAVIStreamSink::GetSamplesPerSecond((CAVIStreamSink *)&this[-1].LockSemaphore, &v57);
    if ( SamplesPerSecond < 0 )
    {
      v25 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
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
        if ( *((_DWORD *)v27 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v27, "CAVIStreamSink::PlaceMarker", 651, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v15 = 123;
      goto LABEL_12;
    }
    v58.vt = 19;
    if ( !a3 )
      goto LABEL_68;
    v56 = 0;
    SamplesPerSecond = CAVIStreamSink::GetFrameDuration((CAVIStreamSink *)&this[-1].LockSemaphore, &v56);
    if ( SamplesPerSecond < 0 )
    {
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != SamplesPerSecond )
          CallStackContext::TraceFailure(v31, "CAVIStreamSink::PlaceMarker", 661, SamplesPerSecond);
      }
      if ( !g_wppLevels )
        goto LABEL_107;
      v15 = 124;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        p_LockSemaphore,
        SamplesPerSecond);
LABEL_107:
      LeaveCriticalSection(v8);
      goto LABEL_108;
    }
    v32 = 0;
    if ( (__int64)p_LockSemaphore[61] > 0 )
      v32 = p_LockSemaphore[61];
    v33 = v56 + a3->hVal.QuadPart;
    if ( v33 > (unsigned __int64)v32 )
    {
      v34 = v33 - (_QWORD)v32;
      if ( v34 < 0 )
        v35 = (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1))
            + (double)(int)(v34 & 1 | ((unsigned __int64)v34 >> 1));
      else
        v35 = (double)(int)v34;
      v58.lVal = (int)(v35 * v57 / 10000000.0 + 0.9);
    }
    else
    {
LABEL_68:
      v58.lVal = 1;
    }
    v36 = (CAVIStreamSink::StreamSampleQueueEntry *)operator new(0x70u);
    if ( v36 )
    {
      v38 = (_QWORD *)CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(
                        v36,
                        MFSTREAMSINK_MARKER_TICK,
                        &v58,
                        a4,
                        1);
      if ( v38 )
      {
        v39 = (_QWORD *)this[12].SpinCount;
        *v38 = (char *)this + 504;
        v38[1] = v39;
        *v39 = v38;
        this[12].SpinCount = (ULONG_PTR)v38;
LABEL_85:
        ++LODWORD(this[12].OwningThread);
        LeaveCriticalSection(v8);
        SamplesPerSecond = CAVIMediaSink::NotifySampleReceived(v59);
        if ( SamplesPerSecond < 0 )
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
            if ( *((_DWORD *)v51 + 499) != SamplesPerSecond )
              CallStackContext::TraceFailure(v51, "CAVIStreamSink::PlaceMarker", 693, SamplesPerSecond);
          }
          if ( g_wppLevels )
          {
            v20 = 128;
            goto LABEL_24;
          }
        }
        goto LABEL_108;
      }
    }
    v40 = (wchar_t *)CallStackTracing::s_wpInstance;
    SamplesPerSecond = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
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
      if ( *((_DWORD *)v42 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v42, "CAVIStreamSink::PlaceMarker", 677, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_107;
    v43 = 125;
    goto LABEL_106;
  }
  v21 = (wchar_t *)CallStackTracing::s_wpInstance;
  SamplesPerSecond = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
    CallStackTracing::s_wpInstance = v22;
    if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v21 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v21 + 8) )
  {
    v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
    if ( *((_DWORD *)v23 + 499) != -2147024809 )
      CallStackContext::TraceFailure(v23, "CAVIStreamSink::PlaceMarker", 682, -2147024809);
  }
  if ( g_wppLevels )
  {
    v20 = 126;
    goto LABEL_24;
  }
LABEL_108:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v59);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v59);
  return (unsigned int)SamplesPerSecond;
}

```

## disassembly

```asm
0x180102180  push    rbp
0x180102182  push    rbx
0x180102183  push    rsi
0x180102184  push    rdi
0x180102185  push    r12
0x180102187  push    r13
0x180102189  push    r14
0x18010218b  push    r15
0x18010218d  mov     rbp, rsp
0x180102190  sub     rsp, 68h
0x180102194  mov     rsi, r8
0x180102197  mov     r12d, edx
0x18010219a  mov     rdi, rcx
0x18010219d  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1801021a4  mov     r8d, 277h; int
0x1801021aa  lea     rcx, [rbp+arg_0]; this
0x1801021ae  mov     r13, r9
0x1801021b1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801021b6  lea     r14, [rdi+230h]
0x1801021bd  mov     [rbp+arg_0], 0
0x1801021c5  mov     rcx, r14; lpCriticalSection
0x1801021c8  call    cs:__imp_EnterCriticalSection
0x1801021cf  nop     dword ptr [rax+rax+00h]
0x1801021d4  lea     r15, [rdi-10h]
0x1801021d8  cmp     qword ptr [r15+178h], 0
0x1801021e0  jnz     loc_180102284
0x1801021e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801021ed  mov     ebx, 0C00D4A38h
0x1801021f2  test    rcx, rcx
0x1801021f5  jnz     short loc_18010223E
0x1801021f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801021fe  nop     dword ptr [rax+rax+00h]
0x180102203  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010220a  mov     rcx, rax
0x18010220d  test    rax, rax
0x180102210  jz      short loc_180102230
0x180102212  mov     rax, [rax]
0x180102215  mov     edx, 7F0h
0x18010221a  mov     rax, [rax+8]
0x18010221e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102223  test    eax, eax
0x180102225  jz      short loc_180102230
0x180102227  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010222e  jmp     short loc_18010223E
0x180102230  lea     rcx, qword_1801B97E0; this
0x180102237  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18010223e  cmp     byte ptr [rcx+8], 0
0x180102242  jz      short loc_180102269
0x180102244  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180102249  cmp     [rax+7CCh], ebx
0x18010224f  jz      short loc_180102269
0x180102251  mov     r9d, ebx; int
0x180102254  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x18010225b  mov     r8d, 27Ch; int
0x180102261  mov     rcx, rax; this
0x180102264  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180102269  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180102270  jb      loc_1801028E6
0x180102276  mov     edx, 79h ; 'y'
0x18010227b  mov     dword ptr [rsp+68h+var_48], ebx
0x18010227f  jmp     loc_1801028CC
0x180102284  lea     rdx, [rdi+168h]
0x18010228b  lea     rcx, [rbp+arg_0]
0x18010228f  call    ??4?$ComPtr@VCAVIMediaSink@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CAVIMediaSink>::operator=(Microsoft::WRL::ComPtr<CAVIMediaSink> const &)
0x180102294  mov     rcx, r14; lpCriticalSection
0x180102297  call    cs:__imp_LeaveCriticalSection
0x18010229e  nop     dword ptr [rax+rax+00h]
0x1801022a3  mov     r9, r13; struct tagPROPVARIANT *
0x1801022a6  mov     r8, rsi; struct tagPROPVARIANT *
0x1801022a9  mov     edx, r12d; enum _MFSTREAMSINK_MARKER_TYPE
0x1801022ac  mov     rcx, rdi; this
0x1801022af  call    ?PlaceMarker@CBaseStreamSink@@UEAAJW4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1@Z; CBaseStreamSink::PlaceMarker(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x1801022b4  mov     ebx, eax
0x1801022b6  test    eax, eax
0x1801022b8  jns     loc_180102371
0x1801022be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801022c5  test    rcx, rcx
0x1801022c8  jnz     short loc_180102311
0x1801022ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801022d1  nop     dword ptr [rax+rax+00h]
0x1801022d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801022dd  mov     rcx, rax
0x1801022e0  test    rax, rax
0x1801022e3  jz      short loc_180102303
0x1801022e5  mov     rax, [rax]
0x1801022e8  mov     edx, 7F0h
0x1801022ed  mov     rax, [rax+8]
0x1801022f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801022f6  test    eax, eax
0x1801022f8  jz      short loc_180102303
0x1801022fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180102301  jmp     short loc_180102311
0x180102303  lea     rcx, qword_1801B97E0; this
0x18010230a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180102311  cmp     byte ptr [rcx+8], 0
0x180102315  jz      short loc_18010233C
0x180102317  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010231c  cmp     [rax+7CCh], ebx
0x180102322  jz      short loc_18010233C
0x180102324  mov     r9d, ebx; int
0x180102327  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x18010232e  mov     r8d, 281h; int
0x180102334  mov     rcx, rax; this
0x180102337  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18010233c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180102343  jb      loc_1801028F5
0x180102349  mov     edx, 7Ah ; 'z'
0x18010234e  mov     rcx, cs:WPP_GLOBAL_Control
0x180102355  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x18010235c  mov     r9, r15
0x18010235f  mov     dword ptr [rsp+68h+var_48], ebx
0x180102363  mov     rcx, [rcx+10h]
0x180102367  call    WPP_SF_qD
0x18010236c  jmp     loc_1801028F5
0x180102371  cmp     r12d, 2
0x180102375  jnz     loc_180102711
0x18010237b  xor     r12d, r12d
0x18010237e  test    rsi, rsi
0x180102381  jz      loc_18010242B
0x180102387  cmp     word ptr [rsi], 14h
0x18010238b  jz      loc_18010242B
0x180102391  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180102398  mov     ebx, 80070057h
0x18010239d  test    rcx, rcx
0x1801023a0  jnz     short loc_1801023E9
0x1801023a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801023a9  nop     dword ptr [rax+rax+00h]
0x1801023ae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801023b5  mov     rcx, rax
0x1801023b8  test    rax, rax
0x1801023bb  jz      short loc_1801023DB
0x1801023bd  mov     rax, [rax]
0x1801023c0  mov     edx, 7F0h
0x1801023c5  mov     rax, [rax+8]
0x1801023c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801023ce  test    eax, eax
0x1801023d0  jz      short loc_1801023DB
0x1801023d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801023d9  jmp     short loc_1801023E9
0x1801023db  lea     rcx, qword_1801B97E0; this
0x1801023e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801023e9  cmp     [rcx+8], r12b
0x1801023ed  jz      short loc_180102414
0x1801023ef  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801023f4  cmp     [rax+7CCh], ebx
0x1801023fa  jz      short loc_180102414
0x1801023fc  mov     r9d, ebx; int
0x1801023ff  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x180102406  mov     r8d, 2AAh; int
0x18010240c  mov     rcx, rax; this
0x18010240f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180102414  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18010241b  jb      loc_1801028F5
0x180102421  mov     edx, 7Eh ; '~'
0x180102426  jmp     loc_18010234E
0x18010242b  lea     r14, [rdi+208h]
0x180102432  mov     rcx, r14; lpCriticalSection
0x180102435  call    cs:__imp_EnterCriticalSection
0x18010243c  nop     dword ptr [rax+rax+00h]
0x180102441  xorps   xmm0, xmm0
0x180102444  lea     rdx, [rbp+var_30]; double *
0x180102448  xorps   xmm1, xmm1
0x18010244b  movsd   [rbp+var_30], xmm0
0x180102450  xor     eax, eax
0x180102452  mov     rcx, r15; this
0x180102455  movups  xmmword ptr [rbp+var_28], xmm1
0x180102459  mov     qword ptr [rbp+var_28+10h], rax
0x18010245d  call    ?GetSamplesPerSecond@CAVIStreamSink@@AEAAJPEAN@Z; CAVIStreamSink::GetSamplesPerSecond(double *)
0x180102462  mov     ebx, eax
0x180102464  test    eax, eax
0x180102466  jns     loc_180102501
0x18010246c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180102473  test    rcx, rcx
0x180102476  jnz     short loc_1801024BF
0x180102478  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010247f  nop     dword ptr [rax+rax+00h]
0x180102484  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010248b  mov     rcx, rax
0x18010248e  test    rax, rax
0x180102491  jz      short loc_1801024B1
0x180102493  mov     rax, [rax]
0x180102496  mov     edx, 7F0h
0x18010249b  mov     rax, [rax+8]
0x18010249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801024a4  test    eax, eax
0x1801024a6  jz      short loc_1801024B1
0x1801024a8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801024af  jmp     short loc_1801024BF
0x1801024b1  lea     rcx, qword_1801B97E0; this
0x1801024b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801024bf  cmp     [rcx+8], r12b
0x1801024c3  jz      short loc_1801024EA
0x1801024c5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801024ca  cmp     [rax+7CCh], ebx
0x1801024d0  jz      short loc_1801024EA
0x1801024d2  mov     r9d, ebx; int
0x1801024d5  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x1801024dc  mov     r8d, 28Bh; int
0x1801024e2  mov     rcx, rax; this
0x1801024e5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801024ea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801024f1  jb      loc_1801028E6
0x1801024f7  mov     edx, 7Bh ; '{'
0x1801024fc  jmp     loc_18010227B
0x180102501  mov     eax, 13h
0x180102506  mov     word ptr [rbp+var_28], ax
0x18010250a  test    rsi, rsi
0x18010250d  jz      loc_180102623
0x180102513  lea     rdx, [rbp+var_38]; unsigned __int64 *
0x180102517  mov     [rbp+var_38], r12
0x18010251b  mov     rcx, r15; this
0x18010251e  call    ?GetFrameDuration@CAVIStreamSink@@AEAAJPEA_K@Z; CAVIStreamSink::GetFrameDuration(unsigned __int64 *)
0x180102523  mov     ebx, eax
0x180102525  test    eax, eax
0x180102527  jns     loc_1801025C2
0x18010252d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180102534  test    rcx, rcx
0x180102537  jnz     short loc_180102580
0x180102539  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180102540  nop     dword ptr [rax+rax+00h]
0x180102545  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18010254c  mov     rcx, rax
0x18010254f  test    rax, rax
0x180102552  jz      short loc_180102572
0x180102554  mov     rax, [rax]
0x180102557  mov     edx, 7F0h
0x18010255c  mov     rax, [rax+8]
0x180102560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102565  test    eax, eax
0x180102567  jz      short loc_180102572
0x180102569  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180102570  jmp     short loc_180102580
0x180102572  lea     rcx, qword_1801B97E0; this
0x180102579  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180102580  cmp     [rcx+8], r12b
0x180102584  jz      short loc_1801025AB
0x180102586  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18010258b  cmp     [rax+7CCh], ebx
0x180102591  jz      short loc_1801025AB
0x180102593  mov     r9d, ebx; int
0x180102596  lea     rdx, aCavistreamsink_20; "CAVIStreamSink::PlaceMarker"
0x18010259d  mov     r8d, 295h; int
0x1801025a3  mov     rcx, rax; this
0x1801025a6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801025ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801025b2  jb      loc_1801028E6
0x1801025b8  mov     edx, 7Ch ; '|'
0x1801025bd  jmp     loc_18010227B
0x1801025c2  mov     rax, [r15+1E8h]
0x1801025c9  mov     r8, r12
0x1801025cc  mov     rdx, [rsi+8]
0x1801025d0  test    rax, rax
0x1801025d3  cmovg   r8, rax
0x1801025d7  add     rdx, [rbp+var_38]
0x1801025db  cmp     rdx, r8
0x1801025de  jbe     short loc_180102623
0x1801025e0  sub     rdx, r8
0x1801025e3  xorps   xmm0, xmm0
0x1801025e6  js      short loc_1801025EF
0x1801025e8  cvtsi2sd xmm0, rdx
0x1801025ed  jmp     short loc_180102604
0x1801025ef  mov     rax, rdx
0x1801025f2  and     edx, 1
0x1801025f5  shr     rax, 1
0x1801025f8  or      rax, rdx
0x1801025fb  cvtsi2sd xmm0, rax
0x180102600  addsd   xmm0, xmm0
0x180102604  mulsd   xmm0, [rbp+var_30]
0x180102609  divsd   xmm0, cs:__real@416312d000000000
0x180102611  addsd   xmm0, cs:__real@3feccccccccccccd
0x180102619  cvttsd2si rax, xmm0
0x18010261e  mov     dword ptr [rbp+var_28+8], eax
0x180102621  jmp     short loc_18010262A
0x180102623  mov     dword ptr [rbp+var_28+8], 1
0x18010262a  mov     ecx, 70h ; 'p'; Size
0x18010262f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102634  test    rax, rax
0x180102637  jz      short loc_180102675
0x180102639  mov     r9, r13; struct tagPROPVARIANT *
0x18010263c  mov     [rsp+68h+var_48], 1; bool
0x180102641  lea     r8, [rbp+var_28]; struct tagPROPVARIANT *
0x180102645  mov     edx, 2; enum _MFSTREAMSINK_MARKER_TYPE
0x18010264a  mov     rcx, rax; this
0x18010264d  call    ??0StreamSampleQueueEntry@CAVIStreamSink@@QEAA@W4_MFSTREAMSINK_MARKER_TYPE@@PEBUtagPROPVARIANT@@1_N@Z; CAVIStreamSink::StreamSampleQueueEntry::StreamSampleQueueEntry(_MFSTREAMSINK_MARKER_TYPE,tagPROPVARIANT const *,tagPROPVARIANT const *,bool)
0x180102652  test    rax, rax
0x180102655  jz      short loc_180102675
0x180102657  lea     rdx, [rdi+1F8h]
0x18010265e  mov     rcx, [rdx+8]
0x180102662  mov     [rax], rdx
0x180102665  mov     [rax+8], rcx
0x180102669  mov     [rcx], rax
0x18010266c  mov     [rdx+8], rax
0x180102670  jmp     loc_180102775
0x180102675  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18010267c  mov     edi, 8007000Eh
0x180102681  mov     ebx, edi
0x180102683  test    rcx, rcx
0x180102686  jnz     short loc_1801026CF
0x180102688  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18010268f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
