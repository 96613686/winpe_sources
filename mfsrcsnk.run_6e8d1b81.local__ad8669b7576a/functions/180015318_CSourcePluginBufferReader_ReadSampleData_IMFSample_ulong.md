# CSourcePluginBufferReader::ReadSampleData(IMFSample *,ulong)

- ea: `0x180015318`
- end: `0x180015a0b`
- name: `?ReadSampleData@CSourcePluginBufferReader@@QEAAJPEAUIMFSample@@K@Z`
- size: `1779`
- prototype: `__int64 __fastcall(CSourcePluginBufferReader *__hidden this, struct IMFSample *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006c2bc`
- `0x18006ca5c`
- `0x1800c2d10`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180015238`
- `0x180015318`
- `0x180015a14`
- `0x180017598`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x180147f70`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800153be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001555e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800155f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001576d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800157fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800158b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015948`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800153be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015499`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001555e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800155f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001576d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800157fc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800158b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015948`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180015712`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180015712`

## string_xrefs

- `0x180015337`: `CSourcePluginBufferReader::ReadSampleData`
- `0x1800157c4`: `CSourcePluginBufferReader::ReadSampleData`
- `0x180015853`: `CSourcePluginBufferReader::ReadSampleData`
- `0x18001590c`: `CSourcePluginBufferReader::ReadSampleData`
- `0x18001599f`: `CSourcePluginBufferReader::ReadSampleData`

## pseudocode

```c
__int64 __fastcall CSourcePluginBufferReader::ReadSampleData(
        CSourcePluginBufferReader *this,
        struct IMFSample *a2,
        unsigned int a3)
{
  __int64 v3; // r15
  unsigned __int64 *v5; // rsi
  __int64 v6; // rdx
  HRESULT v7; // ebx
  wchar_t *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  int v14; // esi
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  DWORD v25; // r13d
  unsigned __int64 v26; // r14
  __int64 v27; // rax
  __int64 v28; // rdx
  unsigned __int64 v29; // r12
  DWORD v30; // r8d
  DWORD v31; // edx
  __int64 v32; // rdx
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  __int64 v37; // rdx
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  int v48; // [rsp+20h] [rbp-40h]
  DWORD v49; // [rsp+30h] [rbp-30h]
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v51; // [rsp+40h] [rbp-20h]
  IMFMediaBuffer *pBuffer; // [rsp+48h] [rbp-18h]
  __int64 v53; // [rsp+50h] [rbp-10h]
  unsigned int v55; // [rsp+B8h] [rbp+58h] BYREF

  v3 = a3;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v55,
    "CSourcePluginBufferReader::ReadSampleData",
    282);
  v5 = (unsigned __int64 *)((char *)this + 472);
  if ( (unsigned __int8)byte_1801B1109 >= 0x20u )
    WPP_SF_qId(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids, this, *v5, v3);
  v55 = 0;
  v7 = CSourcePluginBufferReader::CheckReadHits(this, v3, (enum CSourcePluginBufferReader::ReadHits *)&v55);
  if ( v7 >= 0 )
  {
    if ( !v55 )
    {
      v25 = v3;
      v26 = *((_QWORD *)this + 57);
      v27 = *((_QWORD *)this + 54);
      v51 = *v5;
      v55 = 0;
      while ( 1 )
      {
        if ( !v25 || !v27 )
        {
          *v5 += v3;
          CSourcePluginBufferReader::RemoveStaleBuffers(this);
          *((_QWORD *)this + 60) = -1;
          goto LABEL_110;
        }
        v53 = *(_QWORD *)(v27 + 8);
        pBuffer = *(IMFMediaBuffer **)v27;
        v7 = ((__int64 (__fastcall *)(IMFMediaBuffer *, unsigned int *))pBuffer->lpVtbl->GetCurrentLength)(
               pBuffer,
               &v55);
        if ( v7 < 0 )
          break;
        v29 = v26 + v55;
        if ( v29 < v26 )
        {
          v41 = (wchar_t *)CallStackTracing::s_wpInstance;
          v7 = -2147024362;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CSourcePluginBufferReader::ReadSampleData",
                309,
                -2147024362);
          }
          if ( g_wppLevels )
          {
            v11 = 30;
            v48 = -2147024362;
            goto LABEL_14;
          }
          goto LABEL_110;
        }
        v7 = 0;
        if ( v51 < v29 )
        {
          ppBuffer = 0;
          v30 = v25;
          if ( v25 >= v29 - v51 )
            v30 = v29 - v51;
          v49 = v30;
          if ( *v5 > v26 )
            v31 = *(_DWORD *)v5 - v26;
          else
            v31 = 0;
          v7 = MFCreateMediaBufferWrapper(pBuffer, v31, v30, &ppBuffer);
          if ( v7 < 0 )
          {
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
              CallStackTracing::s_wpInstance = v39;
              if ( v39
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
              {
                v38 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v38 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v38 + 8) )
            {
              v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)v40 + 499) != v7 )
                CallStackContext::TraceFailure(v40, "CSourcePluginBufferReader::ReadSampleData", 317, v7);
            }
            if ( g_wppLevels )
            {
              v37 = 31;
LABEL_87:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v37,
                WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids,
                this,
                v7);
            }
LABEL_88:
            ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
            goto LABEL_110;
          }
          v7 = ((__int64 (__fastcall *)(struct IMFSample *, IMFMediaBuffer *))a2->lpVtbl->AddBuffer)(a2, ppBuffer);
          if ( v7 < 0 )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
              CallStackTracing::s_wpInstance = v35;
              if ( v35
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
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
              if ( *((_DWORD *)v36 + 499) != v7 )
                CallStackContext::TraceFailure(v36, "CSourcePluginBufferReader::ReadSampleData", 318, v7);
            }
            if ( g_wppLevels )
            {
              v37 = 32;
              goto LABEL_87;
            }
            goto LABEL_88;
          }
          v51 += v49;
          v25 -= v49;
          ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
        }
        v27 = v53;
        v26 = v29;
      }
      v44 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
        if ( *((_DWORD *)v46 + 499) != v7 )
          CallStackContext::TraceFailure(v46, "CSourcePluginBufferReader::ReadSampleData", 308, v7);
      }
      if ( g_wppLevels )
      {
        v11 = 29;
        v48 = v7;
        goto LABEL_14;
      }
      goto LABEL_110;
    }
    if ( v55 != 1 )
    {
      if ( v55 != 2 )
        goto LABEL_110;
      *((_QWORD *)this + 60) = *v5;
      CSourcePluginBufferReader::RemoveAllBuffers(this);
      v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      v14 = -1072863856;
      v7 = -1072863856;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
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
        v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v16 + 499) != -1072863856 )
          CallStackContext::TraceFailure(v16, "CSourcePluginBufferReader::ReadSampleData", 338, -1072863856);
      }
      if ( !g_wppLevels )
        goto LABEL_110;
      v11 = 33;
      goto LABEL_28;
    }
    if ( *((_DWORD *)this + 122) )
    {
      v17 = -1;
    }
    else
    {
      v18 = *((_QWORD *)this + 57);
      v17 = v18 + *((unsigned int *)this + 116);
      if ( v17 < v18 )
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        v14 = -2147024362;
        v7 = -2147024362;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
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
          if ( *((_DWORD *)v24 + 499) != -2147024362 )
            CallStackContext::TraceFailure(v24, "CSourcePluginBufferReader::ReadSampleData", 356, -2147024362);
        }
        if ( !g_wppLevels )
          goto LABEL_110;
        v11 = 34;
LABEL_28:
        v48 = v14;
        goto LABEL_14;
      }
    }
    *((_QWORD *)this + 60) = v17;
    v14 = -1072863856;
    v19 = (wchar_t *)CallStackTracing::s_wpInstance;
    v7 = -1072863856;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != -1072863856 )
        CallStackContext::TraceFailure(v21, "CSourcePluginBufferReader::ReadSampleData", 360, -1072863856);
    }
    if ( !g_wppLevels )
      goto LABEL_110;
    v11 = 35;
    goto LABEL_28;
  }
  v8 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
    CallStackTracing::s_wpInstance = v9;
    if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
    {
      v8 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v8 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v8 + 8) )
  {
    v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
    if ( *((_DWORD *)v10 + 499) != v7 )
      CallStackContext::TraceFailure(v10, "CSourcePluginBufferReader::ReadSampleData", 287, v7);
  }
  if ( g_wppLevels )
  {
    v11 = 28;
    v48 = v7;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids, this, v48);
  }
LABEL_110:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v55);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015318  mov     [rsp-38h+arg_0], rbx
0x18001531d  mov     [rsp-38h+arg_8], rdx
0x180015322  push    rbp
0x180015323  push    rsi
0x180015324  push    rdi
0x180015325  push    r12
0x180015327  push    r13
0x180015329  push    r14
0x18001532b  push    r15
0x18001532d  mov     rbp, rsp
0x180015330  sub     rsp, 60h
0x180015334  mov     r15d, r8d
0x180015337  lea     r14, aCsourcepluginb_7; "CSourcePluginBufferReader::ReadSampleDa"...
0x18001533e  mov     rdi, rcx
0x180015341  mov     rdx, r14; char *
0x180015344  mov     r8d, 11Ah; int
0x18001534a  lea     rcx, [rbp+arg_18]; this
0x18001534e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180015353  cmp     cs:byte_1801B1109, 20h ; ' '
0x18001535a  lea     rsi, [rdi+1D8h]
0x180015361  lea     r13, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x180015368  jb      short loc_180015392
0x18001536a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015371  mov     edx, 1Bh
0x180015376  mov     rax, [rsi]
0x180015379  mov     r9, rdi
0x18001537c  mov     [rsp+60h+var_38], r15d
0x180015381  mov     r8, r13
0x180015384  mov     [rsp+60h+var_40], rax
0x180015389  mov     rcx, [rcx+38h]
0x18001538d  call    WPP_SF_qId
0x180015392  xor     r12d, r12d
0x180015395  lea     r8, [rbp+arg_18]; enum CSourcePluginBufferReader::ReadHits *
0x180015399  mov     edx, r15d; unsigned int
0x18001539c  mov     [rbp+arg_18], r12d
0x1800153a0  mov     rcx, rdi; this
0x1800153a3  call    ?CheckReadHits@CSourcePluginBufferReader@@IEAAJKPEAW4ReadHits@1@@Z; CSourcePluginBufferReader::CheckReadHits(ulong,CSourcePluginBufferReader::ReadHits *)
0x1800153a8  mov     ebx, eax
0x1800153aa  test    eax, eax
0x1800153ac  jns     loc_180015457
0x1800153b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153b9  test    rcx, rcx
0x1800153bc  jnz     short loc_1800153FF
0x1800153be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800153c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153cb  mov     rcx, rax
0x1800153ce  test    rax, rax
0x1800153d1  jz      short loc_1800153F1
0x1800153d3  mov     rax, [rax]
0x1800153d6  mov     edx, 7F0h
0x1800153db  mov     rax, [rax+8]
0x1800153df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e4  test    eax, eax
0x1800153e6  jz      short loc_1800153F1
0x1800153e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153ef  jmp     short loc_1800153FF
0x1800153f1  lea     rcx, qword_1801B07E0; this
0x1800153f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800153ff  cmp     [rcx+8], r12b
0x180015403  jz      short loc_180015426
0x180015405  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001540a  cmp     [rax+7CCh], ebx
0x180015410  jz      short loc_180015426
0x180015412  mov     r9d, ebx; int
0x180015415  mov     r8d, 11Fh; int
0x18001541b  mov     rdx, r14; char *
0x18001541e  mov     rcx, rax; this
0x180015421  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015426  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001542d  jb      loc_1800159E8
0x180015433  mov     edx, 1Ch
0x180015438  mov     dword ptr [rsp+60h+var_40], ebx
0x18001543c  mov     r8, r13
0x18001543f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015446  mov     r9, rdi
0x180015449  mov     rcx, [rcx+10h]
0x18001544d  call    WPP_SF_qD
0x180015452  jmp     loc_1800159E8
0x180015457  mov     ecx, [rbp+arg_18]
0x18001545a  test    ecx, ecx
0x18001545c  jz      loc_18001566F
0x180015462  sub     ecx, 1
0x180015465  jz      loc_18001551C
0x18001546b  cmp     ecx, 1
0x18001546e  jnz     loc_1800159E8
0x180015474  mov     rax, [rsi]
0x180015477  mov     rcx, rdi; this
0x18001547a  mov     [rdi+1E0h], rax
0x180015481  call    ?RemoveAllBuffers@CSourcePluginBufferReader@@QEAAXXZ; CSourcePluginBufferReader::RemoveAllBuffers(void)
0x180015486  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001548d  mov     esi, 0C00D6590h
0x180015492  mov     ebx, esi
0x180015494  test    rcx, rcx
0x180015497  jnz     short loc_1800154DA
0x180015499  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001549f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800154a6  mov     rcx, rax
0x1800154a9  test    rax, rax
0x1800154ac  jz      short loc_1800154CC
0x1800154ae  mov     rax, [rax]
0x1800154b1  mov     edx, 7F0h
0x1800154b6  mov     rax, [rax+8]
0x1800154ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154bf  test    eax, eax
0x1800154c1  jz      short loc_1800154CC
0x1800154c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800154ca  jmp     short loc_1800154DA
0x1800154cc  lea     rcx, qword_1801B07E0; this
0x1800154d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800154da  cmp     [rcx+8], r12b
0x1800154de  jz      short loc_180015501
0x1800154e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800154e5  cmp     [rax+7CCh], esi
0x1800154eb  jz      short loc_180015501
0x1800154ed  mov     r9d, esi; int
0x1800154f0  mov     r8d, 152h; int
0x1800154f6  mov     rdx, r14; char *
0x1800154f9  mov     rcx, rax; this
0x1800154fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015501  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180015508  jb      loc_1800159E8
0x18001550e  mov     edx, 21h ; '!'
0x180015513  mov     dword ptr [rsp+60h+var_40], esi
0x180015517  jmp     loc_18001543C
0x18001551c  cmp     [rdi+1E8h], r12d
0x180015523  jz      short loc_18001552B
0x180015525  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015529  jmp     short loc_180015544
0x18001552b  mov     rcx, [rdi+1C8h]
0x180015532  mov     eax, [rdi+1D0h]
0x180015538  add     rax, rcx
0x18001553b  cmp     rax, rcx
0x18001553e  jb      loc_1800155DD
0x180015544  mov     [rdi+1E0h], rax
0x18001554b  mov     esi, 0C00D6590h
0x180015550  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015557  mov     ebx, esi
0x180015559  test    rcx, rcx
0x18001555c  jnz     short loc_18001559F
0x18001555e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015564  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001556b  mov     rcx, rax
0x18001556e  test    rax, rax
0x180015571  jz      short loc_180015591
0x180015573  mov     rax, [rax]
0x180015576  mov     edx, 7F0h
0x18001557b  mov     rax, [rax+8]
0x18001557f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015584  test    eax, eax
0x180015586  jz      short loc_180015591
0x180015588  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001558f  jmp     short loc_18001559F
0x180015591  lea     rcx, qword_1801B07E0; this
0x180015598  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001559f  cmp     [rcx+8], r12b
0x1800155a3  jz      short loc_1800155C6
0x1800155a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800155aa  cmp     [rax+7CCh], esi
0x1800155b0  jz      short loc_1800155C6
0x1800155b2  mov     r9d, esi; int
0x1800155b5  mov     r8d, 168h; int
0x1800155bb  mov     rdx, r14; char *
0x1800155be  mov     rcx, rax; this
0x1800155c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800155c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800155cd  jb      loc_1800159E8
0x1800155d3  mov     edx, 23h ; '#'
0x1800155d8  jmp     loc_180015513
0x1800155dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800155e4  mov     esi, 80070216h
0x1800155e9  mov     ebx, esi
0x1800155eb  test    rcx, rcx
0x1800155ee  jnz     short loc_180015631
0x1800155f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800155f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800155fd  mov     rcx, rax
0x180015600  test    rax, rax
0x180015603  jz      short loc_180015623
0x180015605  mov     rax, [rax]
0x180015608  mov     edx, 7F0h
0x18001560d  mov     rax, [rax+8]
0x180015611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015616  test    eax, eax
0x180015618  jz      short loc_180015623
0x18001561a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015621  jmp     short loc_180015631
0x180015623  lea     rcx, qword_1801B07E0; this
0x18001562a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015631  cmp     [rcx+8], r12b
0x180015635  jz      short loc_180015658
0x180015637  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001563c  cmp     [rax+7CCh], esi
0x180015642  jz      short loc_180015658
0x180015644  mov     r9d, esi; int
0x180015647  mov     r8d, 164h; int
0x18001564d  mov     rdx, r14; char *
0x180015650  mov     rcx, rax; this
0x180015653  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180015658  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001565f  jb      loc_1800159E8
0x180015665  mov     edx, 22h ; '"'
0x18001566a  jmp     loc_180015513
0x18001566f  mov     rdx, [rsi]
0x180015672  mov     r13d, r15d
0x180015675  mov     r14, [rdi+1C8h]
0x18001567c  mov     rax, [rdi+1B0h]
0x180015683  mov     [rbp+var_20], rdx
0x180015687  mov     [rbp+arg_18], r12d
0x18001568b  test    r13d, r13d
0x18001568e  jz      loc_1800159D2
0x180015694  test    rax, rax
0x180015697  jz      loc_1800159D2
0x18001569d  mov     rcx, [rax+8]
0x1800156a1  lea     rdx, [rbp+arg_18]
0x1800156a5  mov     [rbp+var_10], rcx
0x1800156a9  mov     rcx, [rax]
0x1800156ac  mov     [rbp+pBuffer], rcx
0x1800156b0  mov     rax, [rcx]
0x1800156b3  mov     rax, [rax+28h]
0x1800156b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156bc  mov     ebx, eax
0x1800156be  test    eax, eax
0x1800156c0  js      loc_18001593C
0x1800156c6  mov     r12d, [rbp+arg_18]
0x1800156ca  add     r12, r14
0x1800156cd  cmp     r12, r14
0x1800156d0  jb      loc_1800158A2
0x1800156d6  mov     rdx, [rbp+var_20]
0x1800156da  xor     ebx, ebx
0x1800156dc  cmp     rdx, r12
0x1800156df  jnb     short loc_180015752
0x1800156e1  mov     rcx, r12
0x1800156e4  mov     eax, r13d
0x1800156e7  sub     rcx, rdx
0x1800156ea  mov     [rbp+ppBuffer], rbx
0x1800156ee  cmp     rax, rcx
0x1800156f1  mov     r8d, r13d
0x1800156f4  cmovnb  r8d, ecx; dwLength
0x1800156f8  mov     [rbp+var_30], r8d
0x1800156fc  cmp     [rsi], r14
0x1800156ff  ja      short loc_180015705
0x180015701  xor     edx, edx
0x180015703  jmp     short loc_18001570A
0x180015705  mov     edx, [rsi]
0x180015707  sub     edx, r14d; cbOffset
0x18001570a  mov     rcx, [rbp+pBuffer]; pBuffer
0x18001570e  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180015712  call    cs:__imp_MFCreateMediaBufferWrapper
0x180015718  mov     ebx, eax
0x18001571a  test    eax, eax
0x18001571c  js      loc_1800157F0
0x180015722  mov     rcx, [rbp+arg_8]
0x180015726  mov     rdx, [rbp+ppBuffer]
0x18001572a  mov     rax, [rcx]
0x18001572d  mov     rax, [rax+150h]
0x180015734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015739  mov     ebx, eax
0x18001573b  test    eax, eax
0x18001573d  js      short loc_180015761
0x18001573f  mov     eax, [rbp+var_30]
0x180015742  lea     rcx, [rbp+ppBuffer]; void *
0x180015746  add     [rbp+var_20], rax
0x18001574a  sub     r13d, eax
0x18001574d  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180015752  mov     rax, [rbp+var_10]
0x180015756  mov     r14, r12
0x180015759  xor     r12d, r12d
0x18001575c  jmp     loc_18001568B
0x180015761  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015768  test    rcx, rcx
0x18001576b  jnz     short loc_1800157AE
0x18001576d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015773  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001577a  mov     rcx, rax
0x18001577d  test    rax, rax
0x180015780  jz      short loc_1800157A0
0x180015782  mov     rax, [rax]
0x180015785  mov     edx, 7F0h
0x18001578a  mov     rax, [rax+8]
0x18001578e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015793  test    eax, eax
0x180015795  jz      short loc_1800157A0
0x180015797  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001579e  jmp     short loc_1800157AE
0x1800157a0  lea     rcx, qword_1801B07E0; this
0x1800157a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800157ae  cmp     byte ptr [rcx+8], 0
0x1800157b2  jz      short loc_1800157D9
0x1800157b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800157b9  cmp     [rax+7CCh], ebx
0x1800157bf  jz      short loc_1800157D9
0x1800157c1  mov     r9d, ebx; int
0x1800157c4  lea     rdx, aCsourcepluginb_7; "CSourcePluginBufferReader::ReadSampleDa"...
0x1800157cb  mov     r8d, 13Eh; int
0x1800157d1  mov     rcx, rax; this
0x1800157d4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800157d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800157e0  jb      loc_180015894
0x1800157e6  mov     edx, 20h ; ' '
0x1800157eb  jmp     loc_180015876
  ... truncated ...
```
