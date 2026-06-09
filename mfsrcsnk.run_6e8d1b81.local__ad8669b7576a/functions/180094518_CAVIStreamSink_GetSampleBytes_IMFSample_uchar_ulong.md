# CAVIStreamSink::GetSampleBytes(IMFSample *,uchar * *,ulong *)

- ea: `0x180094518`
- end: `0x180094ca0`
- name: `?GetSampleBytes@CAVIStreamSink@@QEAAJPEAUIMFSample@@PEAPEAEPEAK@Z`
- size: `1928`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180127704`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180094518`
- `0x1800d1150`
- `0x180109590`
- `0x1801095a8`
- `0x1801099f0`
- `0x18012ec80`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800945a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094670`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094726`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800947d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009489e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094956`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094a0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094ad6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094bb7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800945a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094670`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094726`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800947d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009489e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094956`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094a0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094ad6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180094bb7`

## string_xrefs

- `0x18009456f`: `CAVIStreamSink::GetSampleBytes`
- `0x1800945f8`: `CAVIStreamSink::GetSampleBytes`
- `0x1800946c6`: `CAVIStreamSink::GetSampleBytes`
- `0x18009477d`: `CAVIStreamSink::GetSampleBytes`
- `0x180094830`: `CAVIStreamSink::GetSampleBytes`
- `0x1800948f5`: `CAVIStreamSink::GetSampleBytes`
- `0x1800949ad`: `CAVIStreamSink::GetSampleBytes`
- `0x180094a61`: `CAVIStreamSink::GetSampleBytes`
- `0x180094b2d`: `CAVIStreamSink::GetSampleBytes`
- `0x180094c0e`: `CAVIStreamSink::GetSampleBytes`

## pseudocode

```c
__int64 __fastcall CAVIStreamSink::GetSampleBytes(
        CAVIStreamSink *this,
        struct IMFSample *a2,
        struct IMFMediaType **a3,
        unsigned int *a4)
{
  int CurrentMediaType; // edi
  struct IMFMediaType *v9; // r13
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  unsigned int v37; // r14d
  struct IMFMediaType *v38; // rax
  __int64 v39; // rdx
  char *v40; // r9
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  int v49; // ebx
  char *v50; // r9
  __int64 v51; // rdx
  wchar_t *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  _BYTE v56[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int Size; // [rsp+34h] [rbp-44h] BYREF
  int Size_4; // [rsp+38h] [rbp-40h] BYREF
  __int64 v59; // [rsp+40h] [rbp-38h] BYREF
  struct IMFMediaType *v60; // [rsp+48h] [rbp-30h] BYREF
  void *Src; // [rsp+50h] [rbp-28h] BYREF
  GUID v62; // [rsp+58h] [rbp-20h] BYREF

  if ( !a2 || !a3 || (CurrentMediaType = 0, !a4) )
    CurrentMediaType = -2147467261;
  v59 = 0;
  Size_4 = 0;
  v60 = 0;
  v62 = GUID_00000000_0000_0000_0000_000000000000;
  v9 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v56, "CAVIStreamSink::GetSampleBytes", 774);
  if ( CurrentMediaType < 0 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentMediaType )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::GetSampleBytes", 774, CurrentMediaType);
    }
    if ( g_wppLevels )
    {
      v14 = 139;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        this,
        CurrentMediaType);
      goto LABEL_111;
    }
    goto LABEL_111;
  }
  *a3 = 0;
  *a4 = 0;
  CurrentMediaType = CBaseStreamSink::GetCurrentMediaType((CAVIStreamSink *)((char *)this + 32), &v60);
  if ( CurrentMediaType >= 0 )
  {
    v19 = (unsigned int)v60;
    CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *))v60->lpVtbl->GetMajorType)(v60, &v62);
    if ( CurrentMediaType < 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20);
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
        if ( *((_DWORD *)v23 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v23, "CAVIStreamSink::GetSampleBytes", 780, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v14 = 141;
        goto LABEL_16;
      }
      goto LABEL_111;
    }
    CurrentMediaType = ((__int64 (__fastcall *)(struct IMFSample *, int *))a2->lpVtbl->GetBufferCount)(a2, &Size_4);
    if ( CurrentMediaType < 0 )
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
          v25 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v25 + 8) )
      {
        v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
        if ( *((_DWORD *)v27 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v27, "CAVIStreamSink::GetSampleBytes", 782, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v14 = 142;
        goto LABEL_16;
      }
      goto LABEL_111;
    }
    if ( Size_4 )
    {
      lpVtbl = a2->lpVtbl;
      Src = 0;
      Size = 0;
      CurrentMediaType = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))lpVtbl->ConvertToContiguousBuffer)(
                           a2,
                           &v59);
      if ( CurrentMediaType < 0 )
      {
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
          if ( *((_DWORD *)v32 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v32, "CAVIStreamSink::GetSampleBytes", 788, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v14 = 143;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      CurrentMediaType = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, unsigned int *))(*(_QWORD *)v59 + 24LL))(
                           v59,
                           &Src,
                           0,
                           &Size);
      if ( CurrentMediaType < 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v36, "CAVIStreamSink::GetSampleBytes", 789, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v14 = 144;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      v37 = Size + 8;
      v38 = (struct IMFMediaType *)operator new(Size + 8);
      v9 = v38;
      if ( !v38 )
      {
        v41 = (wchar_t *)CallStackTracing::s_wpInstance;
        CurrentMediaType = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
          CallStackTracing::s_wpInstance = v42;
          if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
          {
            v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v41 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v41 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
          if ( *((_DWORD *)v43 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v43, "CAVIStreamSink::GetSampleBytes", 794, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_110;
        v44 = 145;
        goto LABEL_84;
      }
      CurrentMediaType = AVIHelpers::GetChunkID((AVIHelpers *)*((unsigned int *)this + 56), v19, v38, v40);
      if ( CurrentMediaType < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v48, "CAVIStreamSink::GetSampleBytes", 797, CurrentMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_110;
        v44 = 146;
LABEL_84:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v44,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          this,
          CurrentMediaType);
        goto LABEL_110;
      }
      v49 = 1;
      memcpy_0(&v9[1], Src, Size);
      HIDWORD(v9->lpVtbl) = Size;
    }
    else
    {
      v37 = 8;
      v9 = (struct IMFMediaType *)operator new(8u);
      CurrentMediaType = AVIHelpers::GetChunkID((AVIHelpers *)*((unsigned int *)this + 56), v19, v9, v50);
      if ( CurrentMediaType < 0 )
      {
        v52 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51);
          CallStackTracing::s_wpInstance = v53;
          if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
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
          if ( *((_DWORD *)v54 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v54, "CAVIStreamSink::GetSampleBytes", 808, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v14 = 147;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      v49 = 0;
      HIDWORD(v9->lpVtbl) = 0;
    }
    *a3 = v9;
    v9 = 0;
    *a4 = v37;
    if ( !v49 )
      goto LABEL_111;
LABEL_110:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 32LL))(v59);
    goto LABEL_111;
  }
  v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
    CallStackTracing::s_wpInstance = v17;
    if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
    {
      v16 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v16 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v16 + 8) )
  {
    v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
    if ( *((_DWORD *)v18 + 499) != CurrentMediaType )
      CallStackContext::TraceFailure(v18, "CAVIStreamSink::GetSampleBytes", 778, CurrentMediaType);
  }
  if ( g_wppLevels )
  {
    v14 = 140;
    goto LABEL_16;
  }
LABEL_111:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v60);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v59);
  return (unsigned int)CurrentMediaType;
}

```

## disassembly

```asm
0x180094518  push    rbp
0x18009451a  push    rbx
0x18009451b  push    rsi
0x18009451c  push    rdi
0x18009451d  push    r12
0x18009451f  push    r13
0x180094521  push    r14
0x180094523  push    r15
0x180094525  mov     rbp, rsp
0x180094528  sub     rsp, 78h
0x18009452c  mov     rax, cs:__security_cookie
0x180094533  xor     rax, rsp
0x180094536  mov     [rbp+var_10], rax
0x18009453a  xor     ebx, ebx
0x18009453c  mov     r12, r9
0x18009453f  mov     r15, r8
0x180094542  mov     r14, rdx
0x180094545  mov     rsi, rcx
0x180094548  test    rdx, rdx
0x18009454b  jz      short loc_180094559
0x18009454d  test    r8, r8
0x180094550  jz      short loc_180094559
0x180094552  mov     edi, ebx
0x180094554  test    r9, r9
0x180094557  jnz     short loc_18009455E
0x180094559  mov     edi, 80004003h
0x18009455e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180094565  mov     r8d, 306h; int
0x18009456b  mov     [rbp+var_38], rbx
0x18009456f  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180094576  mov     dword ptr [rbp+Size+4], ebx
0x180094579  lea     rcx, [rbp+var_48]; this
0x18009457d  mov     [rbp+var_30], rbx
0x180094581  movdqu  [rbp+var_20], xmm0
0x180094586  mov     r13, rbx
0x180094589  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009458e  test    edi, edi
0x180094590  jns     loc_180094646
0x180094596  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009459d  test    rcx, rcx
0x1800945a0  jnz     short loc_1800945E3
0x1800945a2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800945a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945af  mov     rcx, rax
0x1800945b2  test    rax, rax
0x1800945b5  jz      short loc_1800945D5
0x1800945b7  mov     rax, [rax]
0x1800945ba  mov     edx, 7F0h
0x1800945bf  mov     rax, [rax+8]
0x1800945c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800945c8  test    eax, eax
0x1800945ca  jz      short loc_1800945D5
0x1800945cc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945d3  jmp     short loc_1800945E3
0x1800945d5  lea     rcx, qword_1801B07E0; this
0x1800945dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800945e3  cmp     [rcx+8], bl
0x1800945e6  jz      short loc_18009460D
0x1800945e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800945ed  cmp     [rax+7CCh], edi
0x1800945f3  jz      short loc_18009460D
0x1800945f5  mov     r9d, edi; int
0x1800945f8  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x1800945ff  mov     r8d, 306h; int
0x180094605  mov     rcx, rax; this
0x180094608  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009460d  mov     ebx, 1
0x180094612  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180094618  jb      loc_180094C5E
0x18009461e  mov     edx, 8Bh
0x180094623  mov     rcx, cs:WPP_GLOBAL_Control
0x18009462a  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x180094631  mov     r9, rsi
0x180094634  mov     [rsp+78h+var_58], edi
0x180094638  mov     rcx, [rcx+10h]
0x18009463c  call    WPP_SF_qD
0x180094641  jmp     loc_180094C5E
0x180094646  mov     [r15], rbx
0x180094649  lea     rcx, [rsi+20h]; this
0x18009464d  lea     rdx, [rbp+var_30]; struct IMFMediaType **
0x180094651  mov     [r12], ebx
0x180094655  call    ?GetCurrentMediaType@CBaseStreamSink@@UEAAJPEAPEAUIMFMediaType@@@Z; CBaseStreamSink::GetCurrentMediaType(IMFMediaType * *)
0x18009465a  mov     edi, eax
0x18009465c  test    eax, eax
0x18009465e  jns     loc_1800946F6
0x180094664  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009466b  test    rcx, rcx
0x18009466e  jnz     short loc_1800946B1
0x180094670  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180094676  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009467d  mov     rcx, rax
0x180094680  test    rax, rax
0x180094683  jz      short loc_1800946A3
0x180094685  mov     rax, [rax]
0x180094688  mov     edx, 7F0h
0x18009468d  mov     rax, [rax+8]
0x180094691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094696  test    eax, eax
0x180094698  jz      short loc_1800946A3
0x18009469a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800946a1  jmp     short loc_1800946B1
0x1800946a3  lea     rcx, qword_1801B07E0; this
0x1800946aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800946b1  cmp     [rcx+8], bl
0x1800946b4  jz      short loc_1800946DB
0x1800946b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800946bb  cmp     [rax+7CCh], edi
0x1800946c1  jz      short loc_1800946DB
0x1800946c3  mov     r9d, edi; int
0x1800946c6  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x1800946cd  mov     r8d, 30Ah; int
0x1800946d3  mov     rcx, rax; this
0x1800946d6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800946db  mov     ebx, 1
0x1800946e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800946e6  jb      loc_180094C5E
0x1800946ec  mov     edx, 8Ch
0x1800946f1  jmp     loc_180094623
0x1800946f6  mov     rbx, [rbp+var_30]
0x1800946fa  lea     rdx, [rbp+var_20]
0x1800946fe  mov     rcx, rbx
0x180094701  mov     rax, [rbx]
0x180094704  mov     rax, [rax+108h]
0x18009470b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094710  mov     edi, eax
0x180094712  test    eax, eax
0x180094714  jns     loc_1800947AD
0x18009471a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094721  test    rcx, rcx
0x180094724  jnz     short loc_180094767
0x180094726  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009472c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180094733  mov     rcx, rax
0x180094736  test    rax, rax
0x180094739  jz      short loc_180094759
0x18009473b  mov     rax, [rax]
0x18009473e  mov     edx, 7F0h
0x180094743  mov     rax, [rax+8]
0x180094747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009474c  test    eax, eax
0x18009474e  jz      short loc_180094759
0x180094750  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094757  jmp     short loc_180094767
0x180094759  lea     rcx, qword_1801B07E0; this
0x180094760  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094767  cmp     [rcx+8], r13b
0x18009476b  jz      short loc_180094792
0x18009476d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094772  cmp     [rax+7CCh], edi
0x180094778  jz      short loc_180094792
0x18009477a  mov     r9d, edi; int
0x18009477d  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180094784  mov     r8d, 30Ch; int
0x18009478a  mov     rcx, rax; this
0x18009478d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094792  mov     ebx, 1
0x180094797  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x18009479d  jb      loc_180094C5E
0x1800947a3  mov     edx, 8Dh
0x1800947a8  jmp     loc_180094623
0x1800947ad  mov     rax, [r14]
0x1800947b0  lea     rdx, [rbp+Size+4]
0x1800947b4  mov     rcx, r14
0x1800947b7  mov     rax, [rax+138h]
0x1800947be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947c3  mov     edi, eax
0x1800947c5  test    eax, eax
0x1800947c7  jns     loc_180094860
0x1800947cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800947d4  test    rcx, rcx
0x1800947d7  jnz     short loc_18009481A
0x1800947d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800947df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800947e6  mov     rcx, rax
0x1800947e9  test    rax, rax
0x1800947ec  jz      short loc_18009480C
0x1800947ee  mov     rax, [rax]
0x1800947f1  mov     edx, 7F0h
0x1800947f6  mov     rax, [rax+8]
0x1800947fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800947ff  test    eax, eax
0x180094801  jz      short loc_18009480C
0x180094803  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009480a  jmp     short loc_18009481A
0x18009480c  lea     rcx, qword_1801B07E0; this
0x180094813  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009481a  cmp     [rcx+8], r13b
0x18009481e  jz      short loc_180094845
0x180094820  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180094825  cmp     [rax+7CCh], edi
0x18009482b  jz      short loc_180094845
0x18009482d  mov     r9d, edi; int
0x180094830  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180094837  mov     r8d, 30Eh; int
0x18009483d  mov     rcx, rax; this
0x180094840  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180094845  mov     ebx, 1
0x18009484a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180094850  jb      loc_180094C5E
0x180094856  mov     edx, 8Eh
0x18009485b  jmp     loc_180094623
0x180094860  cmp     dword ptr [rbp+Size+4], r13d
0x180094864  jbe     loc_180094B7F
0x18009486a  mov     rax, [r14]
0x18009486d  lea     rdx, [rbp+var_38]
0x180094871  mov     rcx, r14
0x180094874  mov     [rbp+Src], r13
0x180094878  mov     dword ptr [rbp+Size], r13d
0x18009487c  mov     rax, [rax+148h]
0x180094883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094888  mov     edi, eax
0x18009488a  test    eax, eax
0x18009488c  jns     loc_180094925
0x180094892  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094899  test    rcx, rcx
0x18009489c  jnz     short loc_1800948DF
0x18009489e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800948a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800948ab  mov     rcx, rax
0x1800948ae  test    rax, rax
0x1800948b1  jz      short loc_1800948D1
0x1800948b3  mov     rax, [rax]
0x1800948b6  mov     edx, 7F0h
0x1800948bb  mov     rax, [rax+8]
0x1800948bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948c4  test    eax, eax
0x1800948c6  jz      short loc_1800948D1
0x1800948c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800948cf  jmp     short loc_1800948DF
0x1800948d1  lea     rcx, qword_1801B07E0; this
0x1800948d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800948df  cmp     [rcx+8], r13b
0x1800948e3  jz      short loc_18009490A
0x1800948e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800948ea  cmp     [rax+7CCh], edi
0x1800948f0  jz      short loc_18009490A
0x1800948f2  mov     r9d, edi; int
0x1800948f5  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x1800948fc  mov     r8d, 314h; int
0x180094902  mov     rcx, rax; this
0x180094905  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009490a  mov     ebx, 1
0x18009490f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180094915  jb      loc_180094C5E
0x18009491b  mov     edx, 8Fh
0x180094920  jmp     loc_180094623
0x180094925  mov     rcx, [rbp+var_38]
0x180094929  lea     r9, [rbp+Size]
0x18009492d  xor     r8d, r8d
0x180094930  lea     rdx, [rbp+Src]
0x180094934  mov     rax, [rcx]
0x180094937  mov     rax, [rax+18h]
0x18009493b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094940  mov     edi, eax
0x180094942  test    eax, eax
0x180094944  jns     loc_1800949DD
0x18009494a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094951  test    rcx, rcx
0x180094954  jnz     short loc_180094997
0x180094956  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009495c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180094963  mov     rcx, rax
0x180094966  test    rax, rax
0x180094969  jz      short loc_180094989
0x18009496b  mov     rax, [rax]
0x18009496e  mov     edx, 7F0h
0x180094973  mov     rax, [rax+8]
0x180094977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009497c  test    eax, eax
0x18009497e  jz      short loc_180094989
0x180094980  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094987  jmp     short loc_180094997
0x180094989  lea     rcx, qword_1801B07E0; this
0x180094990  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180094997  cmp     [rcx+8], r13b
0x18009499b  jz      short loc_1800949C2
0x18009499d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800949a2  cmp     [rax+7CCh], edi
0x1800949a8  jz      short loc_1800949C2
0x1800949aa  mov     r9d, edi; int
0x1800949ad  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x1800949b4  mov     r8d, 315h; int
0x1800949ba  mov     rcx, rax; this
0x1800949bd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800949c2  mov     ebx, 1
0x1800949c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x1800949cd  jb      loc_180094C5E
0x1800949d3  mov     edx, 90h
0x1800949d8  jmp     loc_180094623
0x1800949dd  mov     r14d, dword ptr [rbp+Size]
0x1800949e1  add     r14d, 8
0x1800949e5  mov     ecx, r14d; Size
0x1800949e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800949ed  mov     r13, rax
0x1800949f0  test    rax, rax
0x1800949f3  jnz     loc_180094AAF
0x1800949f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180094a00  mov     edi, 8007000Eh
0x180094a05  test    rcx, rcx
0x180094a08  jnz     short loc_180094A4B
  ... truncated ...
```
