# CBaseMediaSink::AddStreamSink(ulong,IMFMediaType *,IMFStreamSink * *)

- ea: `0x1800f66a0`
- end: `0x1800f6d45`
- name: `?AddStreamSink@CBaseMediaSink@@UEAAJKPEAUIMFMediaType@@PEAPEAUIMFStreamSink@@@Z`
- size: `1701`
- prototype: `__int64 __fastcall(CBaseMediaSink *__hidden this, unsigned int, struct IMFMediaType *, struct IMFStreamSink **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016f500`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x180086b54`
- `0x1800f66a0`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6d1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f66d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f66d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f67e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f68a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f697f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6a31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6af4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6c60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6723`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f67e8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f68a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f697f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6a31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6af4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f6c60`

## string_xrefs

- `0x1800f66e2`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6780`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6845`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6905`: `CBaseMediaSink::AddStreamSink`
- `0x1800f69dc`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6a8e`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6b51`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6bfc`: `CBaseMediaSink::AddStreamSink`
- `0x1800f6cbd`: `CBaseMediaSink::AddStreamSink`

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
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v21 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v27 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v32 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v46 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v42 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v37 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v16 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x1800f66a0  mov     [rsp-28h+arg_8], rbx
0x1800f66a5  mov     [rsp-28h+arg_10], rsi
0x1800f66aa  push    rbp
0x1800f66ab  push    r12
0x1800f66ad  push    r13
0x1800f66af  push    r14
0x1800f66b1  push    r15
0x1800f66b3  mov     rbp, rsp
0x1800f66b6  sub     rsp, 40h
0x1800f66ba  lea     r13, [rcx+210h]
0x1800f66c1  mov     rbx, rcx
0x1800f66c4  mov     rcx, r13; lpCriticalSection
0x1800f66c7  mov     r14, r9
0x1800f66ca  mov     r12, r8
0x1800f66cd  mov     r15d, edx
0x1800f66d0  call    cs:__imp_EnterCriticalSection
0x1800f66d7  nop     dword ptr [rax+rax+00h]
0x1800f66dc  mov     r8d, 0B1h; int
0x1800f66e2  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f66e9  lea     rcx, [rbp+arg_0]; this
0x1800f66ed  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800f66f2  test    r14, r14
0x1800f66f5  jz      short loc_1800F66FE
0x1800f66f7  mov     qword ptr [r14], 0
0x1800f66fe  lea     rsi, [rbx-88h]
0x1800f6705  cmp     dword ptr [rsi+278h], 8
0x1800f670c  jnz     loc_1800F67CA
0x1800f6712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6719  mov     ebx, 0C00D3E85h
0x1800f671e  test    rcx, rcx
0x1800f6721  jnz     short loc_1800F676A
0x1800f6723  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f672a  nop     dword ptr [rax+rax+00h]
0x1800f672f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6736  mov     rcx, rax
0x1800f6739  test    rax, rax
0x1800f673c  jz      short loc_1800F675C
0x1800f673e  mov     rax, [rax]
0x1800f6741  mov     edx, 7F0h
0x1800f6746  mov     rax, [rax+8]
0x1800f674a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f674f  test    eax, eax
0x1800f6751  jz      short loc_1800F675C
0x1800f6753  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f675a  jmp     short loc_1800F676A
0x1800f675c  lea     rcx, qword_1801B97E0; this
0x1800f6763  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f676a  cmp     byte ptr [rcx+8], 0
0x1800f676e  jz      short loc_1800F6795
0x1800f6770  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f6775  cmp     [rax+7CCh], ebx
0x1800f677b  jz      short loc_1800F6795
0x1800f677d  mov     r9d, ebx; int
0x1800f6780  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f6787  mov     r8d, 0C1h; int
0x1800f678d  mov     rcx, rax; this
0x1800f6790  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f6795  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f679c  jb      loc_1800F6D10
0x1800f67a2  mov     edx, 14h
0x1800f67a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f67ae  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800f67b5  mov     r9, rsi
0x1800f67b8  mov     [rsp+40h+var_20], ebx
0x1800f67bc  mov     rcx, [rcx+10h]
0x1800f67c0  call    WPP_SF_qD
0x1800f67c5  jmp     loc_1800F6D10
0x1800f67ca  test    byte ptr [rsi+290h], 1
0x1800f67d1  jz      loc_1800F6871
0x1800f67d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f67de  mov     ebx, 0C00D4A3Bh
0x1800f67e3  test    rcx, rcx
0x1800f67e6  jnz     short loc_1800F682F
0x1800f67e8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f67ef  nop     dword ptr [rax+rax+00h]
0x1800f67f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f67fb  mov     rcx, rax
0x1800f67fe  test    rax, rax
0x1800f6801  jz      short loc_1800F6821
0x1800f6803  mov     rax, [rax]
0x1800f6806  mov     edx, 7F0h
0x1800f680b  mov     rax, [rax+8]
0x1800f680f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6814  test    eax, eax
0x1800f6816  jz      short loc_1800F6821
0x1800f6818  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f681f  jmp     short loc_1800F682F
0x1800f6821  lea     rcx, qword_1801B97E0; this
0x1800f6828  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f682f  cmp     byte ptr [rcx+8], 0
0x1800f6833  jz      short loc_1800F685A
0x1800f6835  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f683a  cmp     [rax+7CCh], ebx
0x1800f6840  jz      short loc_1800F685A
0x1800f6842  mov     r9d, ebx; int
0x1800f6845  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f684c  mov     r8d, 0C8h; int
0x1800f6852  mov     rcx, rax; this
0x1800f6855  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f685a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f6861  jb      loc_1800F6D10
0x1800f6867  mov     edx, 15h
0x1800f686c  jmp     loc_1800F67A7
0x1800f6871  mov     rax, [rbx]
0x1800f6874  lea     r8, [rbp+arg_18]
0x1800f6878  mov     edx, r15d
0x1800f687b  mov     [rbp+arg_18], 0
0x1800f6883  mov     rcx, rbx
0x1800f6886  mov     rax, [rax+40h]
0x1800f688a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f688f  test    eax, eax
0x1800f6891  js      loc_1800F694F
0x1800f6897  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f689e  mov     ebx, 0C00D4A3Ch
0x1800f68a3  test    rcx, rcx
0x1800f68a6  jnz     short loc_1800F68EF
0x1800f68a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f68af  nop     dword ptr [rax+rax+00h]
0x1800f68b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f68bb  mov     rcx, rax
0x1800f68be  test    rax, rax
0x1800f68c1  jz      short loc_1800F68E1
0x1800f68c3  mov     rax, [rax]
0x1800f68c6  mov     edx, 7F0h
0x1800f68cb  mov     rax, [rax+8]
0x1800f68cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f68d4  test    eax, eax
0x1800f68d6  jz      short loc_1800F68E1
0x1800f68d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f68df  jmp     short loc_1800F68EF
0x1800f68e1  lea     rcx, qword_1801B97E0; this
0x1800f68e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f68ef  cmp     byte ptr [rcx+8], 0
0x1800f68f3  jz      short loc_1800F691A
0x1800f68f5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f68fa  cmp     [rax+7CCh], ebx
0x1800f6900  jz      short loc_1800F691A
0x1800f6902  mov     r9d, ebx; int
0x1800f6905  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f690c  mov     r8d, 0D2h; int
0x1800f6912  mov     rcx, rax; this
0x1800f6915  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f691a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f6921  jb      loc_1800F6D07
0x1800f6927  mov     edx, 16h
0x1800f692c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f6933  lea     r8, WPP_064ac3d23a4d328c92d991778bc5e966_Traceguids
0x1800f693a  mov     r9, rsi
0x1800f693d  mov     [rsp+40h+var_20], ebx
0x1800f6941  mov     rcx, [rcx+10h]
0x1800f6945  call    WPP_SF_qD
0x1800f694a  jmp     loc_1800F6D07
0x1800f694f  mov     rax, [rbx]
0x1800f6952  lea     rdx, [rbp+arg_0]
0x1800f6956  mov     rcx, rbx
0x1800f6959  mov     [rbp+arg_0], 0
0x1800f6960  mov     rax, [rax+30h]
0x1800f6964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6969  mov     ebx, eax
0x1800f696b  test    eax, eax
0x1800f696d  jns     loc_1800F6A08
0x1800f6973  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f697a  test    rcx, rcx
0x1800f697d  jnz     short loc_1800F69C6
0x1800f697f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f6986  nop     dword ptr [rax+rax+00h]
0x1800f698b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6992  mov     rcx, rax
0x1800f6995  test    rax, rax
0x1800f6998  jz      short loc_1800F69B8
0x1800f699a  mov     rax, [rax]
0x1800f699d  mov     edx, 7F0h
0x1800f69a2  mov     rax, [rax+8]
0x1800f69a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f69ab  test    eax, eax
0x1800f69ad  jz      short loc_1800F69B8
0x1800f69af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f69b6  jmp     short loc_1800F69C6
0x1800f69b8  lea     rcx, qword_1801B97E0; this
0x1800f69bf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f69c6  cmp     byte ptr [rcx+8], 0
0x1800f69ca  jz      short loc_1800F69F1
0x1800f69cc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f69d1  cmp     [rax+7CCh], ebx
0x1800f69d7  jz      short loc_1800F69F1
0x1800f69d9  mov     r9d, ebx; int
0x1800f69dc  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f69e3  mov     r8d, 0DAh; int
0x1800f69e9  mov     rcx, rax; this
0x1800f69ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f69f1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f69f8  jb      loc_1800F6D07
0x1800f69fe  mov     edx, 17h
0x1800f6a03  jmp     loc_1800F692C
0x1800f6a08  mov     rax, [rsi]
0x1800f6a0b  mov     rcx, rsi
0x1800f6a0e  mov     rax, [rax+20h]
0x1800f6a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6a17  cmp     [rbp+arg_0], eax
0x1800f6a1a  jb      loc_1800F6ABA
0x1800f6a20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6a27  mov     ebx, 0C00D36B3h
0x1800f6a2c  test    rcx, rcx
0x1800f6a2f  jnz     short loc_1800F6A78
0x1800f6a31  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f6a38  nop     dword ptr [rax+rax+00h]
0x1800f6a3d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6a44  mov     rcx, rax
0x1800f6a47  test    rax, rax
0x1800f6a4a  jz      short loc_1800F6A6A
0x1800f6a4c  mov     rax, [rax]
0x1800f6a4f  mov     edx, 7F0h
0x1800f6a54  mov     rax, [rax+8]
0x1800f6a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6a5d  test    eax, eax
0x1800f6a5f  jz      short loc_1800F6A6A
0x1800f6a61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6a68  jmp     short loc_1800F6A78
0x1800f6a6a  lea     rcx, qword_1801B97E0; this
0x1800f6a71  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6a78  cmp     byte ptr [rcx+8], 0
0x1800f6a7c  jz      short loc_1800F6AA3
0x1800f6a7e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f6a83  cmp     [rax+7CCh], ebx
0x1800f6a89  jz      short loc_1800F6AA3
0x1800f6a8b  mov     r9d, ebx; int
0x1800f6a8e  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f6a95  mov     r8d, 0E1h; int
0x1800f6a9b  mov     rcx, rax; this
0x1800f6a9e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f6aa3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f6aaa  jb      loc_1800F6D07
0x1800f6ab0  mov     edx, 18h
0x1800f6ab5  jmp     loc_1800F692C
0x1800f6aba  mov     rax, [rsi]
0x1800f6abd  lea     r9, [rbp+var_10]
0x1800f6ac1  mov     r8, r12
0x1800f6ac4  mov     [rbp+var_10], 0
0x1800f6acc  mov     edx, r15d
0x1800f6acf  mov     rcx, rsi
0x1800f6ad2  mov     rax, [rax+28h]
0x1800f6ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6adb  xor     r15d, r15d
0x1800f6ade  mov     ebx, eax
0x1800f6ae0  test    eax, eax
0x1800f6ae2  jns     loc_1800F6B7D
0x1800f6ae8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6aef  test    rcx, rcx
0x1800f6af2  jnz     short loc_1800F6B3B
0x1800f6af4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f6afb  nop     dword ptr [rax+rax+00h]
0x1800f6b00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6b07  mov     rcx, rax
0x1800f6b0a  test    rax, rax
0x1800f6b0d  jz      short loc_1800F6B2D
0x1800f6b0f  mov     rax, [rax]
0x1800f6b12  mov     edx, 7F0h
0x1800f6b17  mov     rax, [rax+8]
0x1800f6b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6b20  test    eax, eax
0x1800f6b22  jz      short loc_1800F6B2D
0x1800f6b24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6b2b  jmp     short loc_1800F6B3B
0x1800f6b2d  lea     rcx, qword_1801B97E0; this
0x1800f6b34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6b3b  cmp     [rcx+8], r15b
0x1800f6b3f  jz      short loc_1800F6B66
0x1800f6b41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800f6b46  cmp     [rax+7CCh], ebx
0x1800f6b4c  jz      short loc_1800F6B66
0x1800f6b4e  mov     r9d, ebx; int
0x1800f6b51  lea     rdx, aCbasemediasink_11; "CBaseMediaSink::AddStreamSink"
0x1800f6b58  mov     r8d, 0EBh; int
0x1800f6b5e  mov     rcx, rax; this
0x1800f6b61  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800f6b66  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800f6b6d  jb      loc_1800F6CFE
0x1800f6b73  mov     edx, 19h
0x1800f6b78  jmp     loc_1800F6CE0
0x1800f6b7d  mov     rdx, [rbp+var_10]; struct CBaseStreamSink *
0x1800f6b81  mov     rcx, rsi; this
0x1800f6b84  call    ?AddStreamToSinkList@CBaseMediaSink@@IEAAJPEAVCBaseStreamSink@@@Z; CBaseMediaSink::AddStreamToSinkList(CBaseStreamSink *)
0x1800f6b89  mov     ebx, eax
0x1800f6b8b  test    eax, eax
0x1800f6b8d  jns     loc_1800F6C28
0x1800f6b93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6b9a  test    rcx, rcx
0x1800f6b9d  jnz     short loc_1800F6BE6
0x1800f6b9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800f6ba6  nop     dword ptr [rax+rax+00h]
0x1800f6bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800f6bb2  mov     rcx, rax
0x1800f6bb5  test    rax, rax
0x1800f6bb8  jz      short loc_1800F6BD8
0x1800f6bba  mov     rax, [rax]
0x1800f6bbd  mov     edx, 7F0h
0x1800f6bc2  mov     rax, [rax+8]
0x1800f6bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f6bcb  test    eax, eax
0x1800f6bcd  jz      short loc_1800F6BD8
  ... truncated ...
```
