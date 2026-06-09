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
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  unsigned int v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  struct IMFSampleVtbl *lpVtbl; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  wchar_t *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  unsigned int v49; // r14d
  struct IMFMediaType *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  char *v53; // r9
  wchar_t *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  wchar_t *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  int v64; // ebx
  char *v65; // r9
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  wchar_t *v69; // rcx
  CallStackTracing *v70; // rax
  struct CallStackContext *v71; // rax
  _BYTE v73[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int Size; // [rsp+34h] [rbp-44h] BYREF
  int Size_4; // [rsp+38h] [rbp-40h] BYREF
  __int64 v76; // [rsp+40h] [rbp-38h] BYREF
  struct IMFMediaType *v77; // [rsp+48h] [rbp-30h] BYREF
  void *Src; // [rsp+50h] [rbp-28h] BYREF
  GUID v79; // [rsp+58h] [rbp-20h] BYREF

  if ( !a2 || !a3 || (CurrentMediaType = 0, !a4) )
    CurrentMediaType = -2147467261;
  v76 = 0;
  Size_4 = 0;
  v77 = 0;
  v79 = GUID_00000000_0000_0000_0000_000000000000;
  v9 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v73, "CAVIStreamSink::GetSampleBytes", 774);
  if ( CurrentMediaType < 0 )
  {
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentMediaType )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CAVIStreamSink::GetSampleBytes", 774, CurrentMediaType);
    }
    if ( g_wppLevels )
    {
      v16 = 139;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
        this,
        CurrentMediaType);
      goto LABEL_111;
    }
    goto LABEL_111;
  }
  *a3 = 0;
  *a4 = 0;
  CurrentMediaType = CBaseStreamSink::GetCurrentMediaType((CAVIStreamSink *)((char *)this + 32), &v77);
  if ( CurrentMediaType >= 0 )
  {
    v23 = (unsigned int)v77;
    CurrentMediaType = ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *))v77->lpVtbl->GetMajorType)(v77, &v79);
    if ( CurrentMediaType < 0 )
    {
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25, v26);
        CallStackTracing::s_wpInstance = v28;
        if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v27 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
        if ( *((_DWORD *)v29 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v29, "CAVIStreamSink::GetSampleBytes", 780, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v16 = 141;
        goto LABEL_16;
      }
      goto LABEL_111;
    }
    CurrentMediaType = ((__int64 (__fastcall *)(struct IMFSample *, int *))a2->lpVtbl->GetBufferCount)(a2, &Size_4);
    if ( CurrentMediaType < 0 )
    {
      v33 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != CurrentMediaType )
          CallStackContext::TraceFailure(v35, "CAVIStreamSink::GetSampleBytes", 782, CurrentMediaType);
      }
      if ( g_wppLevels )
      {
        v16 = 142;
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
                           &v76);
      if ( CurrentMediaType < 0 )
      {
        v40 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v38, v39);
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
          if ( *((_DWORD *)v42 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v42, "CAVIStreamSink::GetSampleBytes", 788, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v16 = 143;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      CurrentMediaType = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, unsigned int *))(*(_QWORD *)v76 + 24LL))(
                           v76,
                           &Src,
                           0,
                           &Size);
      if ( CurrentMediaType < 0 )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
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
            CallStackContext::TraceFailure(v48, "CAVIStreamSink::GetSampleBytes", 789, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v16 = 144;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      v49 = Size + 8;
      v50 = (struct IMFMediaType *)operator new(Size + 8);
      v9 = v50;
      if ( !v50 )
      {
        v54 = (wchar_t *)CallStackTracing::s_wpInstance;
        CurrentMediaType = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52, v53);
          CallStackTracing::s_wpInstance = v55;
          if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
          {
            v54 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v54 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v54 + 8) )
        {
          v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
          if ( *((_DWORD *)v56 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v56, "CAVIStreamSink::GetSampleBytes", 794, -2147024882);
        }
        if ( !g_wppLevels )
          goto LABEL_110;
        v57 = 145;
        goto LABEL_84;
      }
      CurrentMediaType = AVIHelpers::GetChunkID((AVIHelpers *)*((unsigned int *)this + 56), v23, v50, v53);
      if ( CurrentMediaType < 0 )
      {
        v61 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59, v60);
          CallStackTracing::s_wpInstance = v62;
          if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
          {
            v61 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v61 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v61 + 8) )
        {
          v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
          if ( *((_DWORD *)v63 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v63, "CAVIStreamSink::GetSampleBytes", 797, CurrentMediaType);
        }
        if ( !g_wppLevels )
          goto LABEL_110;
        v57 = 146;
LABEL_84:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v57,
          &WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids,
          this,
          CurrentMediaType);
        goto LABEL_110;
      }
      v64 = 1;
      memcpy_0(&v9[1], Src, Size);
      HIDWORD(v9->lpVtbl) = Size;
    }
    else
    {
      v49 = 8;
      v9 = (struct IMFMediaType *)operator new(8u);
      CurrentMediaType = AVIHelpers::GetChunkID((AVIHelpers *)*((unsigned int *)this + 56), v23, v9, v65);
      if ( CurrentMediaType < 0 )
      {
        v69 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v70 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67, v68);
          CallStackTracing::s_wpInstance = v70;
          if ( v70 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v70 + 8LL))(v70, 2032) )
          {
            v69 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v69 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v69 + 8) )
        {
          v71 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v69);
          if ( *((_DWORD *)v71 + 499) != CurrentMediaType )
            CallStackContext::TraceFailure(v71, "CAVIStreamSink::GetSampleBytes", 808, CurrentMediaType);
        }
        if ( g_wppLevels )
        {
          v16 = 147;
          goto LABEL_16;
        }
        goto LABEL_111;
      }
      v64 = 0;
      HIDWORD(v9->lpVtbl) = 0;
    }
    *a3 = v9;
    v9 = 0;
    *a4 = v49;
    if ( !v64 )
      goto LABEL_111;
LABEL_110:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 32LL))(v76);
    goto LABEL_111;
  }
  v20 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18, v19);
    CallStackTracing::s_wpInstance = v21;
    if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
    {
      v20 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v20 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v20 + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
    if ( *((_DWORD *)v22 + 499) != CurrentMediaType )
      CallStackContext::TraceFailure(v22, "CAVIStreamSink::GetSampleBytes", 778, CurrentMediaType);
  }
  if ( g_wppLevels )
  {
    v16 = 140;
    goto LABEL_16;
  }
LABEL_111:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v73);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v77);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v76);
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
