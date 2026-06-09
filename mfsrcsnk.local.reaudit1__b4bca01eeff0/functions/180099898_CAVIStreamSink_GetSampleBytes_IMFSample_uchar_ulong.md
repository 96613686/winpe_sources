# CAVIStreamSink::GetSampleBytes(IMFSample *,uchar * *,ulong *)

- ea: `0x180099898`
- end: `0x18009a057`
- name: `?GetSampleBytes@CAVIStreamSink@@QEAAJPEAUIMFSample@@PEAPEAEPEAK@Z`
- size: `1983`
- prototype: `__int64 __fastcall(CAVIStreamSink *__hidden this, struct IMFSample *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18012e7e4`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180099898`
- `0x1800d70d0`
- `0x180110a7c`
- `0x180110a94`
- `0x180110ed0`
- `0x180136158`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099922`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800999f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099ab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099b6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099c36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099cf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099dae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099f67`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099922`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800999f6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099ab2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099b6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099c36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099cf4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099dae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099e80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180099f67`

## string_xrefs

- `0x1800998ef`: `CAVIStreamSink::GetSampleBytes`
- `0x18009997e`: `CAVIStreamSink::GetSampleBytes`
- `0x180099a52`: `CAVIStreamSink::GetSampleBytes`
- `0x180099b0f`: `CAVIStreamSink::GetSampleBytes`
- `0x180099bc8`: `CAVIStreamSink::GetSampleBytes`
- `0x180099c93`: `CAVIStreamSink::GetSampleBytes`
- `0x180099d51`: `CAVIStreamSink::GetSampleBytes`
- `0x180099e0b`: `CAVIStreamSink::GetSampleBytes`
- `0x180099edd`: `CAVIStreamSink::GetSampleBytes`
- `0x180099fc4`: `CAVIStreamSink::GetSampleBytes`

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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v25 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v30 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v41 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v46 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v52 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v16 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180099898  push    rbp
0x18009989a  push    rbx
0x18009989b  push    rsi
0x18009989c  push    rdi
0x18009989d  push    r12
0x18009989f  push    r13
0x1800998a1  push    r14
0x1800998a3  push    r15
0x1800998a5  mov     rbp, rsp
0x1800998a8  sub     rsp, 78h
0x1800998ac  mov     rax, cs:__security_cookie
0x1800998b3  xor     rax, rsp
0x1800998b6  mov     [rbp+var_10], rax
0x1800998ba  xor     ebx, ebx
0x1800998bc  mov     r12, r9
0x1800998bf  mov     r15, r8
0x1800998c2  mov     r14, rdx
0x1800998c5  mov     rsi, rcx
0x1800998c8  test    rdx, rdx
0x1800998cb  jz      short loc_1800998D9
0x1800998cd  test    r8, r8
0x1800998d0  jz      short loc_1800998D9
0x1800998d2  mov     edi, ebx
0x1800998d4  test    r9, r9
0x1800998d7  jnz     short loc_1800998DE
0x1800998d9  mov     edi, 80004003h
0x1800998de  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800998e5  mov     r8d, 306h; int
0x1800998eb  mov     [rbp+var_38], rbx
0x1800998ef  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x1800998f6  mov     dword ptr [rbp+Size+4], ebx
0x1800998f9  lea     rcx, [rbp+var_48]; this
0x1800998fd  mov     [rbp+var_30], rbx
0x180099901  movdqu  [rbp+var_20], xmm0
0x180099906  mov     r13, rbx
0x180099909  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009990e  test    edi, edi
0x180099910  jns     loc_1800999CC
0x180099916  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009991d  test    rcx, rcx
0x180099920  jnz     short loc_180099969
0x180099922  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180099929  nop     dword ptr [rax+rax+00h]
0x18009992e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099935  mov     rcx, rax
0x180099938  test    rax, rax
0x18009993b  jz      short loc_18009995B
0x18009993d  mov     rax, [rax]
0x180099940  mov     edx, 7F0h
0x180099945  mov     rax, [rax+8]
0x180099949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009994e  test    eax, eax
0x180099950  jz      short loc_18009995B
0x180099952  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099959  jmp     short loc_180099969
0x18009995b  lea     rcx, qword_1801B97E0; this
0x180099962  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099969  cmp     [rcx+8], bl
0x18009996c  jz      short loc_180099993
0x18009996e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099973  cmp     [rax+7CCh], edi
0x180099979  jz      short loc_180099993
0x18009997b  mov     r9d, edi; int
0x18009997e  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099985  mov     r8d, 306h; int
0x18009998b  mov     rcx, rax; this
0x18009998e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099993  mov     ebx, 1
0x180099998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x18009999e  jb      loc_18009A014
0x1800999a4  mov     edx, 8Bh
0x1800999a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800999b0  lea     r8, WPP_b31b1fb0752039c14fe2c8916f4ad2cd_Traceguids
0x1800999b7  mov     r9, rsi
0x1800999ba  mov     [rsp+78h+var_58], edi
0x1800999be  mov     rcx, [rcx+10h]
0x1800999c2  call    WPP_SF_qD
0x1800999c7  jmp     loc_18009A014
0x1800999cc  mov     [r15], rbx
0x1800999cf  lea     rcx, [rsi+20h]; this
0x1800999d3  lea     rdx, [rbp+var_30]; struct IMFMediaType **
0x1800999d7  mov     [r12], ebx
0x1800999db  call    ?GetCurrentMediaType@CBaseStreamSink@@UEAAJPEAPEAUIMFMediaType@@@Z; CBaseStreamSink::GetCurrentMediaType(IMFMediaType * *)
0x1800999e0  mov     edi, eax
0x1800999e2  test    eax, eax
0x1800999e4  jns     loc_180099A82
0x1800999ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800999f1  test    rcx, rcx
0x1800999f4  jnz     short loc_180099A3D
0x1800999f6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800999fd  nop     dword ptr [rax+rax+00h]
0x180099a02  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099a09  mov     rcx, rax
0x180099a0c  test    rax, rax
0x180099a0f  jz      short loc_180099A2F
0x180099a11  mov     rax, [rax]
0x180099a14  mov     edx, 7F0h
0x180099a19  mov     rax, [rax+8]
0x180099a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a22  test    eax, eax
0x180099a24  jz      short loc_180099A2F
0x180099a26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099a2d  jmp     short loc_180099A3D
0x180099a2f  lea     rcx, qword_1801B97E0; this
0x180099a36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099a3d  cmp     [rcx+8], bl
0x180099a40  jz      short loc_180099A67
0x180099a42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099a47  cmp     [rax+7CCh], edi
0x180099a4d  jz      short loc_180099A67
0x180099a4f  mov     r9d, edi; int
0x180099a52  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099a59  mov     r8d, 30Ah; int
0x180099a5f  mov     rcx, rax; this
0x180099a62  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099a67  mov     ebx, 1
0x180099a6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180099a72  jb      loc_18009A014
0x180099a78  mov     edx, 8Ch
0x180099a7d  jmp     loc_1800999A9
0x180099a82  mov     rbx, [rbp+var_30]
0x180099a86  lea     rdx, [rbp+var_20]
0x180099a8a  mov     rcx, rbx
0x180099a8d  mov     rax, [rbx]
0x180099a90  mov     rax, [rax+108h]
0x180099a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a9c  mov     edi, eax
0x180099a9e  test    eax, eax
0x180099aa0  jns     loc_180099B3F
0x180099aa6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099aad  test    rcx, rcx
0x180099ab0  jnz     short loc_180099AF9
0x180099ab2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180099ab9  nop     dword ptr [rax+rax+00h]
0x180099abe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099ac5  mov     rcx, rax
0x180099ac8  test    rax, rax
0x180099acb  jz      short loc_180099AEB
0x180099acd  mov     rax, [rax]
0x180099ad0  mov     edx, 7F0h
0x180099ad5  mov     rax, [rax+8]
0x180099ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ade  test    eax, eax
0x180099ae0  jz      short loc_180099AEB
0x180099ae2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099ae9  jmp     short loc_180099AF9
0x180099aeb  lea     rcx, qword_1801B97E0; this
0x180099af2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099af9  cmp     [rcx+8], r13b
0x180099afd  jz      short loc_180099B24
0x180099aff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099b04  cmp     [rax+7CCh], edi
0x180099b0a  jz      short loc_180099B24
0x180099b0c  mov     r9d, edi; int
0x180099b0f  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099b16  mov     r8d, 30Ch; int
0x180099b1c  mov     rcx, rax; this
0x180099b1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099b24  mov     ebx, 1
0x180099b29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180099b2f  jb      loc_18009A014
0x180099b35  mov     edx, 8Dh
0x180099b3a  jmp     loc_1800999A9
0x180099b3f  mov     rax, [r14]
0x180099b42  lea     rdx, [rbp+Size+4]
0x180099b46  mov     rcx, r14
0x180099b49  mov     rax, [rax+138h]
0x180099b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b55  mov     edi, eax
0x180099b57  test    eax, eax
0x180099b59  jns     loc_180099BF8
0x180099b5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099b66  test    rcx, rcx
0x180099b69  jnz     short loc_180099BB2
0x180099b6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180099b72  nop     dword ptr [rax+rax+00h]
0x180099b77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099b7e  mov     rcx, rax
0x180099b81  test    rax, rax
0x180099b84  jz      short loc_180099BA4
0x180099b86  mov     rax, [rax]
0x180099b89  mov     edx, 7F0h
0x180099b8e  mov     rax, [rax+8]
0x180099b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099b97  test    eax, eax
0x180099b99  jz      short loc_180099BA4
0x180099b9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099ba2  jmp     short loc_180099BB2
0x180099ba4  lea     rcx, qword_1801B97E0; this
0x180099bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099bb2  cmp     [rcx+8], r13b
0x180099bb6  jz      short loc_180099BDD
0x180099bb8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099bbd  cmp     [rax+7CCh], edi
0x180099bc3  jz      short loc_180099BDD
0x180099bc5  mov     r9d, edi; int
0x180099bc8  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099bcf  mov     r8d, 30Eh; int
0x180099bd5  mov     rcx, rax; this
0x180099bd8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099bdd  mov     ebx, 1
0x180099be2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180099be8  jb      loc_18009A014
0x180099bee  mov     edx, 8Eh
0x180099bf3  jmp     loc_1800999A9
0x180099bf8  cmp     dword ptr [rbp+Size+4], r13d
0x180099bfc  jbe     loc_180099F2F
0x180099c02  mov     rax, [r14]
0x180099c05  lea     rdx, [rbp+var_38]
0x180099c09  mov     rcx, r14
0x180099c0c  mov     [rbp+Src], r13
0x180099c10  mov     dword ptr [rbp+Size], r13d
0x180099c14  mov     rax, [rax+148h]
0x180099c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c20  mov     edi, eax
0x180099c22  test    eax, eax
0x180099c24  jns     loc_180099CC3
0x180099c2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099c31  test    rcx, rcx
0x180099c34  jnz     short loc_180099C7D
0x180099c36  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180099c3d  nop     dword ptr [rax+rax+00h]
0x180099c42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099c49  mov     rcx, rax
0x180099c4c  test    rax, rax
0x180099c4f  jz      short loc_180099C6F
0x180099c51  mov     rax, [rax]
0x180099c54  mov     edx, 7F0h
0x180099c59  mov     rax, [rax+8]
0x180099c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099c62  test    eax, eax
0x180099c64  jz      short loc_180099C6F
0x180099c66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099c6d  jmp     short loc_180099C7D
0x180099c6f  lea     rcx, qword_1801B97E0; this
0x180099c76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099c7d  cmp     [rcx+8], r13b
0x180099c81  jz      short loc_180099CA8
0x180099c83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099c88  cmp     [rax+7CCh], edi
0x180099c8e  jz      short loc_180099CA8
0x180099c90  mov     r9d, edi; int
0x180099c93  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099c9a  mov     r8d, 314h; int
0x180099ca0  mov     rcx, rax; this
0x180099ca3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099ca8  mov     ebx, 1
0x180099cad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180099cb3  jb      loc_18009A014
0x180099cb9  mov     edx, 8Fh
0x180099cbe  jmp     loc_1800999A9
0x180099cc3  mov     rcx, [rbp+var_38]
0x180099cc7  lea     r9, [rbp+Size]
0x180099ccb  xor     r8d, r8d
0x180099cce  lea     rdx, [rbp+Src]
0x180099cd2  mov     rax, [rcx]
0x180099cd5  mov     rax, [rax+18h]
0x180099cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099cde  mov     edi, eax
0x180099ce0  test    eax, eax
0x180099ce2  jns     loc_180099D81
0x180099ce8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099cef  test    rcx, rcx
0x180099cf2  jnz     short loc_180099D3B
0x180099cf4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180099cfb  nop     dword ptr [rax+rax+00h]
0x180099d00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180099d07  mov     rcx, rax
0x180099d0a  test    rax, rax
0x180099d0d  jz      short loc_180099D2D
0x180099d0f  mov     rax, [rax]
0x180099d12  mov     edx, 7F0h
0x180099d17  mov     rax, [rax+8]
0x180099d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099d20  test    eax, eax
0x180099d22  jz      short loc_180099D2D
0x180099d24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180099d2b  jmp     short loc_180099D3B
0x180099d2d  lea     rcx, qword_1801B97E0; this
0x180099d34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180099d3b  cmp     [rcx+8], r13b
0x180099d3f  jz      short loc_180099D66
0x180099d41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180099d46  cmp     [rax+7CCh], edi
0x180099d4c  jz      short loc_180099D66
0x180099d4e  mov     r9d, edi; int
0x180099d51  lea     rdx, aCavistreamsink_19; "CAVIStreamSink::GetSampleBytes"
0x180099d58  mov     r8d, 315h; int
0x180099d5e  mov     rcx, rax; this
0x180099d61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180099d66  mov     ebx, 1
0x180099d6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, bl; MFWppLevels g_wppLevels
0x180099d71  jb      loc_18009A014
0x180099d77  mov     edx, 90h
0x180099d7c  jmp     loc_1800999A9
0x180099d81  mov     r14d, dword ptr [rbp+Size]
0x180099d85  add     r14d, 8
0x180099d89  mov     ecx, r14d; Size
0x180099d8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180099d91  mov     r13, rax
  ... truncated ...
```
