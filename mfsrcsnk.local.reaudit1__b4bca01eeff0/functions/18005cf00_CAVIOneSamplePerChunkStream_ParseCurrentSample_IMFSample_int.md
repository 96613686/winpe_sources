# CAVIOneSamplePerChunkStream::ParseCurrentSample(IMFSample * *,int *)

- ea: `0x18005cf00`
- end: `0x18005d68a`
- name: `?ParseCurrentSample@CAVIOneSamplePerChunkStream@@UEAAJPEAPEAUIMFSample@@PEAH@Z`
- size: `1930`
- prototype: `__int64 __fastcall(CAVIOneSamplePerChunkStream *__hidden this, struct IMFSample **, int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x18005cf00`
- `0x18005e2e4`
- `0x18005e660`
- `0x180077708`
- `0x180079194`
- `0x180079680`
- `0x1801467f8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d09b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d155`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d20d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d2c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d389`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d450`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d5d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d09b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d155`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d20d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d2c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d389`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d450`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005d5d7`
- `MFPlat!MFCreateSample` at `0x18005d076`
- `MFPlat!MFCreateSample` at `0x18005d076`

## pseudocode

```c
__int64 __fastcall CAVIOneSamplePerChunkStream::ParseCurrentSample(
        CAVIOneSamplePerChunkStream *this,
        struct IMFSample **a2,
        int *a3)
{
  HRESULT CurrentIndexEntry; // ebx
  __int64 v7; // rdx
  int v8; // eax
  BOOL v9; // esi
  BOOL v10; // r14d
  __int64 v11; // r15
  unsigned __int64 v12; // r13
  CallStackTracing *v13; // rcx
  struct CallStackContext *v14; // rax
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
  __int64 v29; // r8
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  struct CAVIIndex *v41; // rsi
  wchar_t *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned __int64 v46; // [rsp+50h] [rbp-10h] BYREF
  struct CAVIIndex *v47; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v48; // [rsp+B0h] [rbp+50h] BYREF
  IMFSample *ppIMFSample; // [rsp+B8h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v47,
    "CAVIOneSamplePerChunkStream::ParseCurrentSample",
    46);
  v48 = 0;
  v46 = 0;
  ppIMFSample = 0;
  *a3 = 0;
  CurrentIndexEntry = CAVIStreamParser::GetCurrentIndexEntry(this, &v46, &v48);
  if ( CurrentIndexEntry == 1 )
    goto LABEL_87;
  if ( !v48 )
  {
    *a3 = 1;
    CurrentIndexEntry = 0;
    *((_QWORD *)this + 77) += *(_DWORD *)(*((_QWORD *)this + 9) + 160LL) != 0 ? 1LL : -1LL;
    goto LABEL_87;
  }
  v47 = 0;
  CurrentIndexEntry = CAVIStreamParser::GetStreamIndex(this, &v47);
  if ( CurrentIndexEntry < 0 )
  {
    v43 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v44;
      if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
      {
        v43 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v43 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v43 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != CurrentIndexEntry )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CAVIOneSamplePerChunkStream::ParseCurrentSample",
          64,
          CurrentIndexEntry);
    }
    if ( g_wppLevels )
    {
      v15 = 11;
      goto LABEL_12;
    }
    goto LABEL_88;
  }
  v8 = (*(__int64 (__fastcall **)(struct CAVIIndex *))(*(_QWORD *)v47 + 56LL))(v47);
  v9 = v8 == 0;
  v10 = v8 != 0;
  v11 = (*(__int64 (__fastcall **)(CAVIOneSamplePerChunkStream *))(*(_QWORD *)this + 96LL))(this);
  v12 = 10000000 * (unsigned __int64)*((unsigned int *)this + 7) / *((unsigned int *)this + 8);
  if ( *((_QWORD *)this + 69) + *((_QWORD *)this + 70) < v11 + v12 )
  {
    v13 = CallStackTracing::s_wpInstance;
    *((_DWORD *)this + 20) = 1;
    CurrentIndexEntry = -1072875840;
    if ( !v13 )
    {
      CallStackTracing::InitInstance();
      v13 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext(v13);
      if ( *((_DWORD *)v14 + 499) != -1072875840 )
        CallStackContext::TraceFailure(v14, "CAVIOneSamplePerChunkStream::ParseCurrentSample", 77, -1072875840);
    }
    if ( g_wppLevels )
    {
      v15 = 12;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        &WPP_e0b2c5208bdf37832b2719142e4dc924_Traceguids,
        this,
        CurrentIndexEntry);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  CurrentIndexEntry = MFCreateSample(&ppIMFSample);
  if ( CurrentIndexEntry >= 0 )
  {
    CurrentIndexEntry = CAVIStreamParser::ReadSampleData(this, ppIMFSample, v48, v46 + 8);
    if ( CurrentIndexEntry < 0 )
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
        if ( *((_DWORD *)v23 + 499) != CurrentIndexEntry )
          CallStackContext::TraceFailure(v23, "CAVIOneSamplePerChunkStream::ParseCurrentSample", 89, CurrentIndexEntry);
      }
      if ( g_wppLevels )
      {
        v15 = 14;
        goto LABEL_12;
      }
      goto LABEL_88;
    }
    CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(
                          ppIMFSample,
                          v11);
    if ( CurrentIndexEntry < 0 )
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
        if ( *((_DWORD *)v27 + 499) != CurrentIndexEntry )
          CallStackContext::TraceFailure(v27, "CAVIOneSamplePerChunkStream::ParseCurrentSample", 91, CurrentIndexEntry);
      }
      if ( g_wppLevels )
      {
        v15 = 15;
        goto LABEL_12;
      }
      goto LABEL_88;
    }
    CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, unsigned __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
                          ppIMFSample,
                          v12);
    if ( CurrentIndexEntry < 0 )
    {
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
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
        if ( *((_DWORD *)v32 + 499) != CurrentIndexEntry )
          CallStackContext::TraceFailure(v32, "CAVIOneSamplePerChunkStream::ParseCurrentSample", 93, CurrentIndexEntry);
      }
      if ( g_wppLevels )
      {
        v15 = 16;
        goto LABEL_12;
      }
      goto LABEL_88;
    }
    if ( !v9 )
    {
      CurrentIndexEntry = ((__int64 (__fastcall *)(IMFSample *, const GUID *, BOOL))ppIMFSample->lpVtbl->SetUINT32)(
                            ppIMFSample,
                            &MFSampleExtension_CleanPoint,
                            v10);
      if ( CurrentIndexEntry < 0 )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v33 + 8) )
        {
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v35,
              "CAVIOneSamplePerChunkStream::ParseCurrentSample",
              97,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
        {
          v15 = 17;
          goto LABEL_12;
        }
        goto LABEL_88;
      }
    }
    if ( !*((_QWORD *)this + 77) )
    {
      v36 = *(_QWORD *)this;
      v47 = 0;
      CurrentIndexEntry = (*(__int64 (__fastcall **)(CAVIOneSamplePerChunkStream *, IMFSample *, struct CAVIIndex **))(v36 + 80))(
                            this,
                            ppIMFSample,
                            &v47);
      if ( CurrentIndexEntry < 0 )
      {
        v38 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != CurrentIndexEntry )
            CallStackContext::TraceFailure(
              v40,
              "CAVIOneSamplePerChunkStream::ParseCurrentSample",
              103,
              CurrentIndexEntry);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_e0b2c5208bdf37832b2719142e4dc924_Traceguids,
            this,
            CurrentIndexEntry);
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v47);
        goto LABEL_88;
      }
      v41 = v47;
      v47 = 0;
      if ( ppIMFSample )
        ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
      ppIMFSample = (IMFSample *)v41;
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v47);
    }
    *((_QWORD *)this + 77) += *(_DWORD *)(*((_QWORD *)this + 9) + 160LL) != 0 ? 1LL : -1LL;
    if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
      WPP_SF_qdiddi(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        v28,
        v29,
        this,
        *((_DWORD *)this + 21),
        v11,
        v48,
        v10,
        *((_QWORD *)this + 77));
LABEL_87:
    *a2 = ppIMFSample;
    ppIMFSample = 0;
    goto LABEL_88;
  }
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
    if ( *((_DWORD *)v19 + 499) != CurrentIndexEntry )
      CallStackContext::TraceFailure(v19, "CAVIOneSamplePerChunkStream::ParseCurrentSample", 84, CurrentIndexEntry);
  }
  if ( g_wppLevels )
  {
    v15 = 13;
    goto LABEL_12;
  }
LABEL_88:
  if ( ppIMFSample )
    ((void (__fastcall *)(IMFSample *))ppIMFSample->lpVtbl->Release)(ppIMFSample);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v47);
  return (unsigned int)CurrentIndexEntry;
}

```

## disassembly

```asm
0x18005cf00  mov     [rsp-38h+arg_8], rbx
0x18005cf05  push    rbp
0x18005cf06  push    rsi
0x18005cf07  push    rdi
0x18005cf08  push    r12
0x18005cf0a  push    r13
0x18005cf0c  push    r14
0x18005cf0e  push    r15
0x18005cf10  mov     rbp, rsp
0x18005cf13  sub     rsp, 60h
0x18005cf17  mov     rsi, r8
0x18005cf1a  mov     r12, rdx
0x18005cf1d  mov     rdi, rcx
0x18005cf20  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005cf27  mov     r8d, 2Eh ; '.'; int
0x18005cf2d  lea     rcx, [rbp+arg_0]; this
0x18005cf31  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005cf36  xor     r13d, r13d
0x18005cf39  lea     r8, [rbp+arg_10]; unsigned int *
0x18005cf3d  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x18005cf41  mov     [rbp+arg_10], r13d
0x18005cf45  mov     rcx, rdi; this
0x18005cf48  mov     [rbp+var_10], r13
0x18005cf4c  mov     [rbp+ppIMFSample], r13
0x18005cf50  mov     [rsi], r13d
0x18005cf53  call    ?GetCurrentIndexEntry@CAVIStreamParser@@QEAAJPEA_KPEAK@Z; CAVIStreamParser::GetCurrentIndexEntry(unsigned __int64 *,ulong *)
0x18005cf58  mov     ebx, eax
0x18005cf5a  cmp     eax, 1
0x18005cf5d  jz      loc_18005D582
0x18005cf63  cmp     [rbp+arg_10], r13d
0x18005cf67  jbe     loc_18005D660
0x18005cf6d  lea     rdx, [rbp+arg_0]; struct CAVIIndex **
0x18005cf71  mov     [rbp+arg_0], r13
0x18005cf75  mov     rcx, rdi; this
0x18005cf78  call    ?GetStreamIndex@CAVIStreamParser@@QEAAJPEAPEAVCAVIIndex@@@Z; CAVIStreamParser::GetStreamIndex(CAVIIndex * *)
0x18005cf7d  mov     ebx, eax
0x18005cf7f  test    eax, eax
0x18005cf81  js      loc_18005D5CB
0x18005cf87  mov     rcx, [rbp+arg_0]
0x18005cf8b  mov     rax, [rcx]
0x18005cf8e  mov     rax, [rax+38h]
0x18005cf92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf97  test    eax, eax
0x18005cf99  mov     esi, r13d
0x18005cf9c  mov     rax, [rdi]
0x18005cf9f  mov     r14d, r13d
0x18005cfa2  setz    sil
0x18005cfa6  mov     rcx, rdi
0x18005cfa9  test    esi, esi
0x18005cfab  mov     rax, [rax+60h]
0x18005cfaf  setz    r14b
0x18005cfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfb8  mov     ecx, [rdi+1Ch]
0x18005cfbb  xor     edx, edx
0x18005cfbd  mov     r15, rax
0x18005cfc0  imul    rax, rcx, 989680h
0x18005cfc7  mov     ecx, [rdi+20h]
0x18005cfca  div     rcx
0x18005cfcd  mov     rdx, [rdi+230h]
0x18005cfd4  add     rdx, [rdi+228h]
0x18005cfdb  mov     r13, rax
0x18005cfde  lea     rcx, [r15+rax]
0x18005cfe2  cmp     rdx, rcx
0x18005cfe5  jnb     loc_18005D072
0x18005cfeb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005cff2  xor     r13d, r13d
0x18005cff5  mov     dword ptr [rdi+50h], 1
0x18005cffc  mov     ebx, 0C00D36C0h
0x18005d001  test    rcx, rcx
0x18005d004  jnz     short loc_18005D012
0x18005d006  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18005d00b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18005d012  cmp     [rcx+8], r13b
0x18005d016  jz      short loc_18005D03D
0x18005d018  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d01d  cmp     [rax+7CCh], ebx
0x18005d023  jz      short loc_18005D03D
0x18005d025  mov     r9d, ebx; int
0x18005d028  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d02f  mov     r8d, 4Dh ; 'M'; int
0x18005d035  mov     rcx, rax; this
0x18005d038  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d03d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005d044  jb      loc_18005D592
0x18005d04a  mov     edx, 0Ch
0x18005d04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d056  lea     r8, WPP_e0b2c5208bdf37832b2719142e4dc924_Traceguids
0x18005d05d  mov     r9, rdi
0x18005d060  mov     [rsp+60h+var_40], ebx
0x18005d064  mov     rcx, [rcx+10h]
0x18005d068  call    WPP_SF_qD
0x18005d06d  jmp     loc_18005D592
0x18005d072  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x18005d076  call    cs:__imp_MFCreateSample
0x18005d07d  nop     dword ptr [rax+rax+00h]
0x18005d082  mov     ebx, eax
0x18005d084  test    eax, eax
0x18005d086  jns     loc_18005D124
0x18005d08c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d093  xor     r13d, r13d
0x18005d096  test    rcx, rcx
0x18005d099  jnz     short loc_18005D0E2
0x18005d09b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d0a2  nop     dword ptr [rax+rax+00h]
0x18005d0a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d0ae  mov     rcx, rax
0x18005d0b1  test    rax, rax
0x18005d0b4  jz      short loc_18005D0D4
0x18005d0b6  mov     rax, [rax]
0x18005d0b9  mov     edx, 7F0h
0x18005d0be  mov     rax, [rax+8]
0x18005d0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d0c7  test    eax, eax
0x18005d0c9  jz      short loc_18005D0D4
0x18005d0cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d0d2  jmp     short loc_18005D0E2
0x18005d0d4  lea     rcx, qword_1801B97E0; this
0x18005d0db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d0e2  cmp     [rcx+8], r13b
0x18005d0e6  jz      short loc_18005D10D
0x18005d0e8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d0ed  cmp     [rax+7CCh], ebx
0x18005d0f3  jz      short loc_18005D10D
0x18005d0f5  mov     r9d, ebx; int
0x18005d0f8  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d0ff  mov     r8d, 54h ; 'T'; int
0x18005d105  mov     rcx, rax; this
0x18005d108  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d10d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005d114  jb      loc_18005D592
0x18005d11a  mov     edx, 0Dh
0x18005d11f  jmp     loc_18005D04F
0x18005d124  mov     r9, [rbp+var_10]
0x18005d128  mov     rcx, rdi; this
0x18005d12b  mov     r8d, [rbp+arg_10]; unsigned int
0x18005d12f  add     r9, 8; unsigned __int64
0x18005d133  mov     rdx, [rbp+ppIMFSample]; struct IMFSample *
0x18005d137  call    ?ReadSampleData@CAVIStreamParser@@IEAAJPEAUIMFSample@@K_K@Z; CAVIStreamParser::ReadSampleData(IMFSample *,ulong,unsigned __int64)
0x18005d13c  mov     ebx, eax
0x18005d13e  test    eax, eax
0x18005d140  jns     loc_18005D1DE
0x18005d146  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d14d  xor     r13d, r13d
0x18005d150  test    rcx, rcx
0x18005d153  jnz     short loc_18005D19C
0x18005d155  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d15c  nop     dword ptr [rax+rax+00h]
0x18005d161  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d168  mov     rcx, rax
0x18005d16b  test    rax, rax
0x18005d16e  jz      short loc_18005D18E
0x18005d170  mov     rax, [rax]
0x18005d173  mov     edx, 7F0h
0x18005d178  mov     rax, [rax+8]
0x18005d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d181  test    eax, eax
0x18005d183  jz      short loc_18005D18E
0x18005d185  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d18c  jmp     short loc_18005D19C
0x18005d18e  lea     rcx, qword_1801B97E0; this
0x18005d195  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d19c  cmp     [rcx+8], r13b
0x18005d1a0  jz      short loc_18005D1C7
0x18005d1a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d1a7  cmp     [rax+7CCh], ebx
0x18005d1ad  jz      short loc_18005D1C7
0x18005d1af  mov     r9d, ebx; int
0x18005d1b2  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d1b9  mov     r8d, 59h ; 'Y'; int
0x18005d1bf  mov     rcx, rax; this
0x18005d1c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d1c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005d1ce  jb      loc_18005D592
0x18005d1d4  mov     edx, 0Eh
0x18005d1d9  jmp     loc_18005D04F
0x18005d1de  mov     rcx, [rbp+ppIMFSample]
0x18005d1e2  mov     rdx, r15
0x18005d1e5  mov     rax, [rcx]
0x18005d1e8  mov     rax, [rax+120h]
0x18005d1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d1f4  mov     ebx, eax
0x18005d1f6  test    eax, eax
0x18005d1f8  jns     loc_18005D296
0x18005d1fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d205  xor     r13d, r13d
0x18005d208  test    rcx, rcx
0x18005d20b  jnz     short loc_18005D254
0x18005d20d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d214  nop     dword ptr [rax+rax+00h]
0x18005d219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d220  mov     rcx, rax
0x18005d223  test    rax, rax
0x18005d226  jz      short loc_18005D246
0x18005d228  mov     rax, [rax]
0x18005d22b  mov     edx, 7F0h
0x18005d230  mov     rax, [rax+8]
0x18005d234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d239  test    eax, eax
0x18005d23b  jz      short loc_18005D246
0x18005d23d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d244  jmp     short loc_18005D254
0x18005d246  lea     rcx, qword_1801B97E0; this
0x18005d24d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d254  cmp     [rcx+8], r13b
0x18005d258  jz      short loc_18005D27F
0x18005d25a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d25f  cmp     [rax+7CCh], ebx
0x18005d265  jz      short loc_18005D27F
0x18005d267  mov     r9d, ebx; int
0x18005d26a  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d271  mov     r8d, 5Bh ; '['; int
0x18005d277  mov     rcx, rax; this
0x18005d27a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d27f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005d286  jb      loc_18005D592
0x18005d28c  mov     edx, 0Fh
0x18005d291  jmp     loc_18005D04F
0x18005d296  mov     rcx, [rbp+ppIMFSample]
0x18005d29a  mov     rdx, r13
0x18005d29d  mov     rax, [rcx]
0x18005d2a0  mov     rax, [rax+130h]
0x18005d2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2ac  xor     r13d, r13d
0x18005d2af  mov     ebx, eax
0x18005d2b1  test    eax, eax
0x18005d2b3  jns     loc_18005D34E
0x18005d2b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d2c0  test    rcx, rcx
0x18005d2c3  jnz     short loc_18005D30C
0x18005d2c5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d2cc  nop     dword ptr [rax+rax+00h]
0x18005d2d1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d2d8  mov     rcx, rax
0x18005d2db  test    rax, rax
0x18005d2de  jz      short loc_18005D2FE
0x18005d2e0  mov     rax, [rax]
0x18005d2e3  mov     edx, 7F0h
0x18005d2e8  mov     rax, [rax+8]
0x18005d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2f1  test    eax, eax
0x18005d2f3  jz      short loc_18005D2FE
0x18005d2f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d2fc  jmp     short loc_18005D30C
0x18005d2fe  lea     rcx, qword_1801B97E0; this
0x18005d305  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d30c  cmp     [rcx+8], r13b
0x18005d310  jz      short loc_18005D337
0x18005d312  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d317  cmp     [rax+7CCh], ebx
0x18005d31d  jz      short loc_18005D337
0x18005d31f  mov     r9d, ebx; int
0x18005d322  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d329  mov     r8d, 5Dh ; ']'; int
0x18005d32f  mov     rcx, rax; this
0x18005d332  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d337  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005d33e  jb      loc_18005D592
0x18005d344  mov     edx, 10h
0x18005d349  jmp     loc_18005D04F
0x18005d34e  test    esi, esi
0x18005d350  jnz     loc_18005D412
0x18005d356  mov     rcx, [rbp+ppIMFSample]
0x18005d35a  lea     rdx, MFSampleExtension_CleanPoint
0x18005d361  mov     r8d, r14d
0x18005d364  mov     rax, [rcx]
0x18005d367  mov     rax, [rax+0A8h]
0x18005d36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d373  mov     ebx, eax
0x18005d375  test    eax, eax
0x18005d377  jns     loc_18005D412
0x18005d37d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d384  test    rcx, rcx
0x18005d387  jnz     short loc_18005D3D0
0x18005d389  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005d390  nop     dword ptr [rax+rax+00h]
0x18005d395  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d39c  mov     rcx, rax
0x18005d39f  test    rax, rax
0x18005d3a2  jz      short loc_18005D3C2
0x18005d3a4  mov     rax, [rax]
0x18005d3a7  mov     edx, 7F0h
0x18005d3ac  mov     rax, [rax+8]
0x18005d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3b5  test    eax, eax
0x18005d3b7  jz      short loc_18005D3C2
0x18005d3b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d3c0  jmp     short loc_18005D3D0
0x18005d3c2  lea     rcx, qword_1801B97E0; this
0x18005d3c9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005d3d0  cmp     [rcx+8], r13b
0x18005d3d4  jz      short loc_18005D3FB
0x18005d3d6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005d3db  cmp     [rax+7CCh], ebx
0x18005d3e1  jz      short loc_18005D3FB
0x18005d3e3  mov     r9d, ebx; int
0x18005d3e6  lea     rdx, aCavionesamplep_0; "CAVIOneSamplePerChunkStream::ParseCurre"...
0x18005d3ed  mov     r8d, 61h ; 'a'; int
0x18005d3f3  mov     rcx, rax; this
0x18005d3f6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005d3fb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
