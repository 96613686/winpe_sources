# CBaseMediaSink::AddStreamSink(ulong,IMFMediaType *,IMFStreamSink * *)

- ea: `0x1800ef7f0`
- end: `0x1800efe58`
- name: `?AddStreamSink@CBaseMediaSink@@UEAAJKPEAUIMFMediaType@@PEAPEAUIMFStreamSink@@@Z`
- size: `1640`
- prototype: `__int64 __fastcall(CBaseMediaSink *__hidden this, unsigned int, struct IMFMediaType *, struct IMFStreamSink **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180166510`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x1800820bc`
- `0x1800ef7f0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efe36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800efe36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ef820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ef820`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef86d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef92c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef9e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efab7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efb63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efc20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efcc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efd80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef86d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef92c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ef9e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efab7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efb63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efc20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efcc5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efd80`

## string_xrefs

- `0x1800ef82c`: `CBaseMediaSink::AddStreamSink`
- `0x1800ef8c4`: `CBaseMediaSink::AddStreamSink`
- `0x1800ef983`: `CBaseMediaSink::AddStreamSink`
- `0x1800efa3d`: `CBaseMediaSink::AddStreamSink`
- `0x1800efb0e`: `CBaseMediaSink::AddStreamSink`
- `0x1800efbba`: `CBaseMediaSink::AddStreamSink`
- `0x1800efc77`: `CBaseMediaSink::AddStreamSink`
- `0x1800efd1c`: `CBaseMediaSink::AddStreamSink`
- `0x1800efdd7`: `CBaseMediaSink::AddStreamSink`

## pseudocode

```c
__int64 __fastcall CBaseMediaSink::AddStreamSink(
        CBaseMediaSink *this,
        unsigned int a2,
        struct IMFMediaType *a3,
        struct IMFStreamSink **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r13
  __int64 v9; // rdx
  char *v10; // rsi
  wchar_t *v11; // rcx
  int v12; // ebx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v15; // rdx
  wchar_t *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  unsigned int v30; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rax
  __int64 v36; // rdx
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rdx
  wchar_t *v42; // rcx
  CallStackTracing *v43; // rax
  struct CallStackContext *v44; // rax
  __int64 v45; // rdx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  struct CBaseStreamSink *v50[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v51; // [rsp+70h] [rbp+30h] BYREF
  __int64 v52; // [rsp+88h] [rbp+48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 528);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v51, "CBaseMediaSink::AddStreamSink", 177);
  if ( a4 )
    *a4 = 0;
  v10 = (char *)this - 136;
  if ( *((_DWORD *)this + 124) == 8 )
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v12 = -1072873851;
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
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873851 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CBaseMediaSink::AddStreamSink", 193, -1072873851);
    }
    if ( g_wppLevels )
    {
      v15 = 20;
LABEL_14:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids, v10, v12);
      goto LABEL_97;
    }
    goto LABEL_97;
  }
  if ( (v10[656] & 1) == 0 )
  {
    v19 = *(_QWORD *)this;
    v52 = 0;
    if ( (*(int (__fastcall **)(CBaseMediaSink *, _QWORD, __int64 *))(v19 + 64))(this, a2, &v52) >= 0 )
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      v12 = -1072870852;
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
        if ( *((_DWORD *)v23 + 499) != -1072870852 )
          CallStackContext::TraceFailure(v23, "CBaseMediaSink::AddStreamSink", 210, -1072870852);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v24 = 22;
      goto LABEL_37;
    }
    v25 = *(_QWORD *)this;
    v51 = 0;
    v12 = (*(__int64 (__fastcall **)(CBaseMediaSink *, unsigned int *))(v25 + 48))(this, &v51);
    if ( v12 < 0 )
    {
      v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
        if ( *((_DWORD *)v29 + 499) != v12 )
          CallStackContext::TraceFailure(v29, "CBaseMediaSink::AddStreamSink", 218, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v24 = 23;
      goto LABEL_37;
    }
    v30 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v10 + 32LL))(v10);
    if ( v51 >= v30 )
    {
      v32 = (wchar_t *)CallStackTracing::s_wpInstance;
      v12 = -1072875853;
      if ( !CallStackTracing::s_wpInstance )
      {
        v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
        CallStackTracing::s_wpInstance = v33;
        if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        {
          v32 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v32 + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
        if ( *((_DWORD *)v34 + 499) != -1072875853 )
          CallStackContext::TraceFailure(v34, "CBaseMediaSink::AddStreamSink", 225, -1072875853);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v24 = 24;
LABEL_37:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids, v10, v12);
LABEL_96:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v52);
      goto LABEL_97;
    }
    v35 = *(_QWORD *)v10;
    v50[0] = 0;
    v12 = (*(__int64 (__fastcall **)(char *, _QWORD, struct IMFMediaType *, struct CBaseStreamSink **))(v35 + 40))(
            v10,
            a2,
            a3,
            v50);
    if ( v12 >= 0 )
    {
      v12 = CBaseMediaSink::AddStreamToSinkList((CBaseMediaSink *)v10, v50[0]);
      if ( v12 >= 0 )
      {
        if ( !a4 )
          goto LABEL_95;
        v12 = (**(__int64 (__fastcall ***)(struct CBaseStreamSink *, GUID *, struct IMFStreamSink **))v50[0])(
                v50[0],
                &IID_IMFStreamSink,
                a4);
        if ( v12 >= 0 )
          goto LABEL_95;
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
          if ( *((_DWORD *)v48 + 499) != v12 )
            CallStackContext::TraceFailure(v48, "CBaseMediaSink::AddStreamSink", 249, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v40 = 27;
      }
      else
      {
        v42 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41);
          CallStackTracing::s_wpInstance = v43;
          if ( v43 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
          {
            v42 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v42 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v44 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v42);
          if ( *((_DWORD *)v44 + 499) != v12 )
            CallStackContext::TraceFailure(v44, "CBaseMediaSink::AddStreamSink", 241, v12);
        }
        if ( !g_wppLevels )
          goto LABEL_95;
        v40 = 26;
      }
    }
    else
    {
      v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
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
        if ( *((_DWORD *)v39 + 499) != v12 )
          CallStackContext::TraceFailure(v39, "CBaseMediaSink::AddStreamSink", 235, v12);
      }
      if ( !g_wppLevels )
        goto LABEL_95;
      v40 = 25;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids, v10, v12);
LABEL_95:
    ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(v50);
    goto LABEL_96;
  }
  v16 = (wchar_t *)CallStackTracing::s_wpInstance;
  v12 = -1072870853;
  if ( !CallStackTracing::s_wpInstance )
  {
    v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
    if ( *((_DWORD *)v18 + 499) != -1072870853 )
      CallStackContext::TraceFailure(v18, "CBaseMediaSink::AddStreamSink", 200, -1072870853);
  }
  if ( g_wppLevels )
  {
    v15 = 21;
    goto LABEL_14;
  }
LABEL_97:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v51);
  LeaveCriticalSection(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800ef7f0  mov     [rsp-28h+arg_8], rbx
0x1800ef7f5  mov     [rsp-28h+arg_10], rsi
0x1800ef7fa  push    rbp
0x1800ef7fb  push    r12
0x1800ef7fd  push    r13
0x1800ef7ff  push    r14
0x1800ef801  push    r15
0x1800ef803  mov     rbp, rsp
0x1800ef806  sub     rsp, 40h
0x1800ef80a  lea     r13, [rcx+210h]
0x1800ef811  mov     rbx, rcx
0x1800ef814  mov     rcx, r13; lpCriticalSection
0x1800ef817  mov     r14, r9
0x1800ef81a  mov     r12, r8
0x1800ef81d  mov     r15d, edx
0x1800ef820  call    cs:__imp_EnterCriticalSection
0x1800ef826  mov     r8d, 0B1h; int
0x1800ef82c  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800ef833  lea     rcx, [rbp+arg_0]; this
0x1800ef837  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ef83c  test    r14, r14
0x1800ef83f  jz      short loc_1800EF848
0x1800ef841  mov     qword ptr [r14], 0
0x1800ef848  lea     rsi, [rbx-88h]
0x1800ef84f  cmp     dword ptr [rsi+278h], 8
0x1800ef856  jnz     loc_1800EF90E
0x1800ef85c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef863  mov     ebx, 0C00D3E85h
0x1800ef868  test    rcx, rcx
0x1800ef86b  jnz     short loc_1800EF8AE
0x1800ef86d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ef873  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef87a  mov     rcx, rax
0x1800ef87d  test    rax, rax
0x1800ef880  jz      short loc_1800EF8A0
0x1800ef882  mov     rax, [rax]
0x1800ef885  mov     edx, 7F0h
0x1800ef88a  mov     rax, [rax+8]
0x1800ef88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef893  test    eax, eax
0x1800ef895  jz      short loc_1800EF8A0
0x1800ef897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef89e  jmp     short loc_1800EF8AE
0x1800ef8a0  lea     rcx, qword_1801B07E0; this
0x1800ef8a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef8ae  cmp     byte ptr [rcx+8], 0
0x1800ef8b2  jz      short loc_1800EF8D9
0x1800ef8b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ef8b9  cmp     [rax+7CCh], ebx
0x1800ef8bf  jz      short loc_1800EF8D9
0x1800ef8c1  mov     r9d, ebx; int
0x1800ef8c4  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800ef8cb  mov     r8d, 0C1h; int
0x1800ef8d1  mov     rcx, rax; this
0x1800ef8d4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ef8d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ef8e0  jb      loc_1800EFE2A
0x1800ef8e6  mov     edx, 14h
0x1800ef8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef8f2  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800ef8f9  mov     r9, rsi
0x1800ef8fc  mov     [rsp+40h+var_20], ebx
0x1800ef900  mov     rcx, [rcx+10h]
0x1800ef904  call    WPP_SF_qD
0x1800ef909  jmp     loc_1800EFE2A
0x1800ef90e  test    byte ptr [rsi+290h], 1
0x1800ef915  jz      loc_1800EF9AF
0x1800ef91b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef922  mov     ebx, 0C00D4A3Bh
0x1800ef927  test    rcx, rcx
0x1800ef92a  jnz     short loc_1800EF96D
0x1800ef92c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ef932  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef939  mov     rcx, rax
0x1800ef93c  test    rax, rax
0x1800ef93f  jz      short loc_1800EF95F
0x1800ef941  mov     rax, [rax]
0x1800ef944  mov     edx, 7F0h
0x1800ef949  mov     rax, [rax+8]
0x1800ef94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef952  test    eax, eax
0x1800ef954  jz      short loc_1800EF95F
0x1800ef956  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef95d  jmp     short loc_1800EF96D
0x1800ef95f  lea     rcx, qword_1801B07E0; this
0x1800ef966  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef96d  cmp     byte ptr [rcx+8], 0
0x1800ef971  jz      short loc_1800EF998
0x1800ef973  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ef978  cmp     [rax+7CCh], ebx
0x1800ef97e  jz      short loc_1800EF998
0x1800ef980  mov     r9d, ebx; int
0x1800ef983  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800ef98a  mov     r8d, 0C8h; int
0x1800ef990  mov     rcx, rax; this
0x1800ef993  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ef998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ef99f  jb      loc_1800EFE2A
0x1800ef9a5  mov     edx, 15h
0x1800ef9aa  jmp     loc_1800EF8EB
0x1800ef9af  mov     rax, [rbx]
0x1800ef9b2  lea     r8, [rbp+arg_18]
0x1800ef9b6  mov     edx, r15d
0x1800ef9b9  mov     [rbp+arg_18], 0
0x1800ef9c1  mov     rcx, rbx
0x1800ef9c4  mov     rax, [rax+40h]
0x1800ef9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef9cd  test    eax, eax
0x1800ef9cf  js      loc_1800EFA87
0x1800ef9d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef9dc  mov     ebx, 0C00D4A3Ch
0x1800ef9e1  test    rcx, rcx
0x1800ef9e4  jnz     short loc_1800EFA27
0x1800ef9e6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ef9ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ef9f3  mov     rcx, rax
0x1800ef9f6  test    rax, rax
0x1800ef9f9  jz      short loc_1800EFA19
0x1800ef9fb  mov     rax, [rax]
0x1800ef9fe  mov     edx, 7F0h
0x1800efa03  mov     rax, [rax+8]
0x1800efa07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa0c  test    eax, eax
0x1800efa0e  jz      short loc_1800EFA19
0x1800efa10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efa17  jmp     short loc_1800EFA27
0x1800efa19  lea     rcx, qword_1801B07E0; this
0x1800efa20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efa27  cmp     byte ptr [rcx+8], 0
0x1800efa2b  jz      short loc_1800EFA52
0x1800efa2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800efa32  cmp     [rax+7CCh], ebx
0x1800efa38  jz      short loc_1800EFA52
0x1800efa3a  mov     r9d, ebx; int
0x1800efa3d  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800efa44  mov     r8d, 0D2h; int
0x1800efa4a  mov     rcx, rax; this
0x1800efa4d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800efa52  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800efa59  jb      loc_1800EFE21
0x1800efa5f  mov     edx, 16h
0x1800efa64  mov     rcx, cs:WPP_GLOBAL_Control
0x1800efa6b  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800efa72  mov     r9, rsi
0x1800efa75  mov     [rsp+40h+var_20], ebx
0x1800efa79  mov     rcx, [rcx+10h]
0x1800efa7d  call    WPP_SF_qD
0x1800efa82  jmp     loc_1800EFE21
0x1800efa87  mov     rax, [rbx]
0x1800efa8a  lea     rdx, [rbp+arg_0]
0x1800efa8e  mov     rcx, rbx
0x1800efa91  mov     [rbp+arg_0], 0
0x1800efa98  mov     rax, [rax+30h]
0x1800efa9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efaa1  mov     ebx, eax
0x1800efaa3  test    eax, eax
0x1800efaa5  jns     loc_1800EFB3A
0x1800efaab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efab2  test    rcx, rcx
0x1800efab5  jnz     short loc_1800EFAF8
0x1800efab7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800efabd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efac4  mov     rcx, rax
0x1800efac7  test    rax, rax
0x1800efaca  jz      short loc_1800EFAEA
0x1800efacc  mov     rax, [rax]
0x1800efacf  mov     edx, 7F0h
0x1800efad4  mov     rax, [rax+8]
0x1800efad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efadd  test    eax, eax
0x1800efadf  jz      short loc_1800EFAEA
0x1800efae1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efae8  jmp     short loc_1800EFAF8
0x1800efaea  lea     rcx, qword_1801B07E0; this
0x1800efaf1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efaf8  cmp     byte ptr [rcx+8], 0
0x1800efafc  jz      short loc_1800EFB23
0x1800efafe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800efb03  cmp     [rax+7CCh], ebx
0x1800efb09  jz      short loc_1800EFB23
0x1800efb0b  mov     r9d, ebx; int
0x1800efb0e  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800efb15  mov     r8d, 0DAh; int
0x1800efb1b  mov     rcx, rax; this
0x1800efb1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800efb23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800efb2a  jb      loc_1800EFE21
0x1800efb30  mov     edx, 17h
0x1800efb35  jmp     loc_1800EFA64
0x1800efb3a  mov     rax, [rsi]
0x1800efb3d  mov     rcx, rsi
0x1800efb40  mov     rax, [rax+20h]
0x1800efb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb49  cmp     [rbp+arg_0], eax
0x1800efb4c  jb      loc_1800EFBE6
0x1800efb52  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efb59  mov     ebx, 0C00D36B3h
0x1800efb5e  test    rcx, rcx
0x1800efb61  jnz     short loc_1800EFBA4
0x1800efb63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800efb69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efb70  mov     rcx, rax
0x1800efb73  test    rax, rax
0x1800efb76  jz      short loc_1800EFB96
0x1800efb78  mov     rax, [rax]
0x1800efb7b  mov     edx, 7F0h
0x1800efb80  mov     rax, [rax+8]
0x1800efb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb89  test    eax, eax
0x1800efb8b  jz      short loc_1800EFB96
0x1800efb8d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efb94  jmp     short loc_1800EFBA4
0x1800efb96  lea     rcx, qword_1801B07E0; this
0x1800efb9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efba4  cmp     byte ptr [rcx+8], 0
0x1800efba8  jz      short loc_1800EFBCF
0x1800efbaa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800efbaf  cmp     [rax+7CCh], ebx
0x1800efbb5  jz      short loc_1800EFBCF
0x1800efbb7  mov     r9d, ebx; int
0x1800efbba  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800efbc1  mov     r8d, 0E1h; int
0x1800efbc7  mov     rcx, rax; this
0x1800efbca  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800efbcf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800efbd6  jb      loc_1800EFE21
0x1800efbdc  mov     edx, 18h
0x1800efbe1  jmp     loc_1800EFA64
0x1800efbe6  mov     rax, [rsi]
0x1800efbe9  lea     r9, [rbp+var_10]
0x1800efbed  mov     r8, r12
0x1800efbf0  mov     [rbp+var_10], 0
0x1800efbf8  mov     edx, r15d
0x1800efbfb  mov     rcx, rsi
0x1800efbfe  mov     rax, [rax+28h]
0x1800efc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc07  xor     r15d, r15d
0x1800efc0a  mov     ebx, eax
0x1800efc0c  test    eax, eax
0x1800efc0e  jns     loc_1800EFCA3
0x1800efc14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efc1b  test    rcx, rcx
0x1800efc1e  jnz     short loc_1800EFC61
0x1800efc20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800efc26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efc2d  mov     rcx, rax
0x1800efc30  test    rax, rax
0x1800efc33  jz      short loc_1800EFC53
0x1800efc35  mov     rax, [rax]
0x1800efc38  mov     edx, 7F0h
0x1800efc3d  mov     rax, [rax+8]
0x1800efc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc46  test    eax, eax
0x1800efc48  jz      short loc_1800EFC53
0x1800efc4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efc51  jmp     short loc_1800EFC61
0x1800efc53  lea     rcx, qword_1801B07E0; this
0x1800efc5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efc61  cmp     [rcx+8], r15b
0x1800efc65  jz      short loc_1800EFC8C
0x1800efc67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800efc6c  cmp     [rax+7CCh], ebx
0x1800efc72  jz      short loc_1800EFC8C
0x1800efc74  mov     r9d, ebx; int
0x1800efc77  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800efc7e  mov     r8d, 0EBh; int
0x1800efc84  mov     rcx, rax; this
0x1800efc87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800efc8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800efc93  jb      loc_1800EFE18
0x1800efc99  mov     edx, 19h
0x1800efc9e  jmp     loc_1800EFDFA
0x1800efca3  mov     rdx, [rbp+var_10]; struct CBaseStreamSink *
0x1800efca7  mov     rcx, rsi; this
0x1800efcaa  call    ?AddStreamToSinkList@CBaseMediaSink@@IEAAJPEAVCBaseStreamSink@@@Z; CBaseMediaSink::AddStreamToSinkList(CBaseStreamSink *)
0x1800efcaf  mov     ebx, eax
0x1800efcb1  test    eax, eax
0x1800efcb3  jns     loc_1800EFD48
0x1800efcb9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efcc0  test    rcx, rcx
0x1800efcc3  jnz     short loc_1800EFD06
0x1800efcc5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800efccb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efcd2  mov     rcx, rax
0x1800efcd5  test    rax, rax
0x1800efcd8  jz      short loc_1800EFCF8
0x1800efcda  mov     rax, [rax]
0x1800efcdd  mov     edx, 7F0h
0x1800efce2  mov     rax, [rax+8]
0x1800efce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efceb  test    eax, eax
0x1800efced  jz      short loc_1800EFCF8
0x1800efcef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efcf6  jmp     short loc_1800EFD06
0x1800efcf8  lea     rcx, qword_1801B07E0; this
0x1800efcff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800efd06  cmp     [rcx+8], r15b
0x1800efd0a  jz      short loc_1800EFD31
0x1800efd0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800efd11  cmp     [rax+7CCh], ebx
  ... truncated ...
```
