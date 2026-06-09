# CSourcePluginBufferReader::ReadSampleData(IMFSample *,ulong)

- ea: `0x180035c44`
- end: `0x18003636e`
- name: `?ReadSampleData@CSourcePluginBufferReader@@QEAAJPEAUIMFSample@@K@Z`
- size: `1834`
- prototype: `__int64 __fastcall(CSourcePluginBufferReader *__hidden this, struct IMFSample *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006d5c0`
- `0x18006e2bc`
- `0x1800c8bd0`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180035bb0`
- `0x180035c44`
- `0x180036374`
- `0x18003675c`
- `0x180036c30`
- `0x180079680`
- `0x1801500fc`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035cea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035dcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800360b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003614c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003620b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035cea`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035dcb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035f2e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800360b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003614c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003620b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800362a4`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180036056`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x180036056`

## string_xrefs

- `0x180035c63`: `CSourcePluginBufferReader::ReadSampleData`
- `0x180036114`: `CSourcePluginBufferReader::ReadSampleData`
- `0x1800361a9`: `CSourcePluginBufferReader::ReadSampleData`
- `0x180036268`: `CSourcePluginBufferReader::ReadSampleData`
- `0x180036301`: `CSourcePluginBufferReader::ReadSampleData`

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
  if ( (unsigned __int8)byte_1801BA109 >= 0x20u )
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
              v41 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v38 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
                v34 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v44 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
          v13 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
            v22 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
        v19 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
      v8 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
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
0x180035c44  mov     [rsp-38h+arg_0], rbx
0x180035c49  mov     [rsp-38h+arg_8], rdx
0x180035c4e  push    rbp
0x180035c4f  push    rsi
0x180035c50  push    rdi
0x180035c51  push    r12
0x180035c53  push    r13
0x180035c55  push    r14
0x180035c57  push    r15
0x180035c59  mov     rbp, rsp
0x180035c5c  sub     rsp, 60h
0x180035c60  mov     r15d, r8d
0x180035c63  lea     r14, aCsourcepluginb_7; "CSourcePluginBufferReader::ReadSampleDa"...
0x180035c6a  mov     rdi, rcx
0x180035c6d  mov     rdx, r14; char *
0x180035c70  mov     r8d, 11Ah; int
0x180035c76  lea     rcx, [rbp+arg_18]; this
0x180035c7a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180035c7f  cmp     cs:byte_1801BA109, 20h ; ' '
0x180035c86  lea     rsi, [rdi+1D8h]
0x180035c8d  lea     r13, WPP_14cf1409a17f339b8cdc44feff496b0f_Traceguids
0x180035c94  jb      short loc_180035CBE
0x180035c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c9d  mov     edx, 1Bh
0x180035ca2  mov     rax, [rsi]
0x180035ca5  mov     r9, rdi
0x180035ca8  mov     [rsp+60h+var_38], r15d
0x180035cad  mov     r8, r13
0x180035cb0  mov     [rsp+60h+var_40], rax
0x180035cb5  mov     rcx, [rcx+38h]
0x180035cb9  call    WPP_SF_qId
0x180035cbe  xor     r12d, r12d
0x180035cc1  lea     r8, [rbp+arg_18]; enum CSourcePluginBufferReader::ReadHits *
0x180035cc5  mov     edx, r15d; unsigned int
0x180035cc8  mov     [rbp+arg_18], r12d
0x180035ccc  mov     rcx, rdi; this
0x180035ccf  call    ?CheckReadHits@CSourcePluginBufferReader@@IEAAJKPEAW4ReadHits@1@@Z; CSourcePluginBufferReader::CheckReadHits(ulong,CSourcePluginBufferReader::ReadHits *)
0x180035cd4  mov     ebx, eax
0x180035cd6  test    eax, eax
0x180035cd8  jns     loc_180035D89
0x180035cde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ce5  test    rcx, rcx
0x180035ce8  jnz     short loc_180035D31
0x180035cea  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035cf1  nop     dword ptr [rax+rax+00h]
0x180035cf6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035cfd  mov     rcx, rax
0x180035d00  test    rax, rax
0x180035d03  jz      short loc_180035D23
0x180035d05  mov     rax, [rax]
0x180035d08  mov     edx, 7F0h
0x180035d0d  mov     rax, [rax+8]
0x180035d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d16  test    eax, eax
0x180035d18  jz      short loc_180035D23
0x180035d1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035d21  jmp     short loc_180035D31
0x180035d23  lea     rcx, qword_1801B97E0; this
0x180035d2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035d31  cmp     [rcx+8], r12b
0x180035d35  jz      short loc_180035D58
0x180035d37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035d3c  cmp     [rax+7CCh], ebx
0x180035d42  jz      short loc_180035D58
0x180035d44  mov     r9d, ebx; int
0x180035d47  mov     r8d, 11Fh; int
0x180035d4d  mov     rdx, r14; char *
0x180035d50  mov     rcx, rax; this
0x180035d53  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035d58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035d5f  jb      loc_18003634A
0x180035d65  mov     edx, 1Ch
0x180035d6a  mov     dword ptr [rsp+60h+var_40], ebx
0x180035d6e  mov     r8, r13
0x180035d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d78  mov     r9, rdi
0x180035d7b  mov     rcx, [rcx+10h]
0x180035d7f  call    WPP_SF_qD
0x180035d84  jmp     loc_18003634A
0x180035d89  mov     ecx, [rbp+arg_18]
0x180035d8c  test    ecx, ecx
0x180035d8e  jz      loc_180035FB3
0x180035d94  sub     ecx, 1
0x180035d97  jz      loc_180035E54
0x180035d9d  cmp     ecx, 1
0x180035da0  jnz     loc_18003634A
0x180035da6  mov     rax, [rsi]
0x180035da9  mov     rcx, rdi; this
0x180035dac  mov     [rdi+1E0h], rax
0x180035db3  call    ?RemoveAllBuffers@CSourcePluginBufferReader@@QEAAXXZ; CSourcePluginBufferReader::RemoveAllBuffers(void)
0x180035db8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035dbf  mov     esi, 0C00D6590h
0x180035dc4  mov     ebx, esi
0x180035dc6  test    rcx, rcx
0x180035dc9  jnz     short loc_180035E12
0x180035dcb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035dd2  nop     dword ptr [rax+rax+00h]
0x180035dd7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035dde  mov     rcx, rax
0x180035de1  test    rax, rax
0x180035de4  jz      short loc_180035E04
0x180035de6  mov     rax, [rax]
0x180035de9  mov     edx, 7F0h
0x180035dee  mov     rax, [rax+8]
0x180035df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035df7  test    eax, eax
0x180035df9  jz      short loc_180035E04
0x180035dfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e02  jmp     short loc_180035E12
0x180035e04  lea     rcx, qword_1801B97E0; this
0x180035e0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e12  cmp     [rcx+8], r12b
0x180035e16  jz      short loc_180035E39
0x180035e18  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035e1d  cmp     [rax+7CCh], esi
0x180035e23  jz      short loc_180035E39
0x180035e25  mov     r9d, esi; int
0x180035e28  mov     r8d, 152h; int
0x180035e2e  mov     rdx, r14; char *
0x180035e31  mov     rcx, rax; this
0x180035e34  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035e39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035e40  jb      loc_18003634A
0x180035e46  mov     edx, 21h ; '!'
0x180035e4b  mov     dword ptr [rsp+60h+var_40], esi
0x180035e4f  jmp     loc_180035D6E
0x180035e54  cmp     [rdi+1E8h], r12d
0x180035e5b  jz      short loc_180035E63
0x180035e5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035e61  jmp     short loc_180035E7C
0x180035e63  mov     rcx, [rdi+1C8h]
0x180035e6a  mov     eax, [rdi+1D0h]
0x180035e70  add     rax, rcx
0x180035e73  cmp     rax, rcx
0x180035e76  jb      loc_180035F1B
0x180035e7c  mov     [rdi+1E0h], rax
0x180035e83  mov     esi, 0C00D6590h
0x180035e88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e8f  mov     ebx, esi
0x180035e91  test    rcx, rcx
0x180035e94  jnz     short loc_180035EDD
0x180035e96  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035e9d  nop     dword ptr [rax+rax+00h]
0x180035ea2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ea9  mov     rcx, rax
0x180035eac  test    rax, rax
0x180035eaf  jz      short loc_180035ECF
0x180035eb1  mov     rax, [rax]
0x180035eb4  mov     edx, 7F0h
0x180035eb9  mov     rax, [rax+8]
0x180035ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ec2  test    eax, eax
0x180035ec4  jz      short loc_180035ECF
0x180035ec6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ecd  jmp     short loc_180035EDD
0x180035ecf  lea     rcx, qword_1801B97E0; this
0x180035ed6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035edd  cmp     [rcx+8], r12b
0x180035ee1  jz      short loc_180035F04
0x180035ee3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035ee8  cmp     [rax+7CCh], esi
0x180035eee  jz      short loc_180035F04
0x180035ef0  mov     r9d, esi; int
0x180035ef3  mov     r8d, 168h; int
0x180035ef9  mov     rdx, r14; char *
0x180035efc  mov     rcx, rax; this
0x180035eff  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035f04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035f0b  jb      loc_18003634A
0x180035f11  mov     edx, 23h ; '#'
0x180035f16  jmp     loc_180035E4B
0x180035f1b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f22  mov     esi, 80070216h
0x180035f27  mov     ebx, esi
0x180035f29  test    rcx, rcx
0x180035f2c  jnz     short loc_180035F75
0x180035f2e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035f35  nop     dword ptr [rax+rax+00h]
0x180035f3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f41  mov     rcx, rax
0x180035f44  test    rax, rax
0x180035f47  jz      short loc_180035F67
0x180035f49  mov     rax, [rax]
0x180035f4c  mov     edx, 7F0h
0x180035f51  mov     rax, [rax+8]
0x180035f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f5a  test    eax, eax
0x180035f5c  jz      short loc_180035F67
0x180035f5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f65  jmp     short loc_180035F75
0x180035f67  lea     rcx, qword_1801B97E0; this
0x180035f6e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f75  cmp     [rcx+8], r12b
0x180035f79  jz      short loc_180035F9C
0x180035f7b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035f80  cmp     [rax+7CCh], esi
0x180035f86  jz      short loc_180035F9C
0x180035f88  mov     r9d, esi; int
0x180035f8b  mov     r8d, 164h; int
0x180035f91  mov     rdx, r14; char *
0x180035f94  mov     rcx, rax; this
0x180035f97  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035f9c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180035fa3  jb      loc_18003634A
0x180035fa9  mov     edx, 22h ; '"'
0x180035fae  jmp     loc_180035E4B
0x180035fb3  mov     rdx, [rsi]
0x180035fb6  mov     r13d, r15d
0x180035fb9  mov     r14, [rdi+1C8h]
0x180035fc0  mov     rax, [rdi+1B0h]
0x180035fc7  mov     [rbp+var_20], rdx
0x180035fcb  mov     [rbp+arg_18], r12d
0x180035fcf  test    r13d, r13d
0x180035fd2  jz      loc_180036334
0x180035fd8  test    rax, rax
0x180035fdb  jz      loc_180036334
0x180035fe1  mov     rcx, [rax+8]
0x180035fe5  lea     rdx, [rbp+arg_18]
0x180035fe9  mov     [rbp+var_10], rcx
0x180035fed  mov     rcx, [rax]
0x180035ff0  mov     [rbp+pBuffer], rcx
0x180035ff4  mov     rax, [rcx]
0x180035ff7  mov     rax, [rax+28h]
0x180035ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036000  mov     ebx, eax
0x180036002  test    eax, eax
0x180036004  js      loc_180036298
0x18003600a  mov     r12d, [rbp+arg_18]
0x18003600e  add     r12, r14
0x180036011  cmp     r12, r14
0x180036014  jb      loc_1800361F8
0x18003601a  mov     rdx, [rbp+var_20]
0x18003601e  xor     ebx, ebx
0x180036020  cmp     rdx, r12
0x180036023  jnb     short loc_18003609C
0x180036025  mov     rcx, r12
0x180036028  mov     eax, r13d
0x18003602b  sub     rcx, rdx
0x18003602e  mov     [rbp+ppBuffer], rbx
0x180036032  cmp     rax, rcx
0x180036035  mov     r8d, r13d
0x180036038  cmovnb  r8d, ecx; dwLength
0x18003603c  mov     [rbp+var_30], r8d
0x180036040  cmp     [rsi], r14
0x180036043  ja      short loc_180036049
0x180036045  xor     edx, edx
0x180036047  jmp     short loc_18003604E
0x180036049  mov     edx, [rsi]
0x18003604b  sub     edx, r14d; cbOffset
0x18003604e  mov     rcx, [rbp+pBuffer]; pBuffer
0x180036052  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180036056  call    cs:__imp_MFCreateMediaBufferWrapper
0x18003605d  nop     dword ptr [rax+rax+00h]
0x180036062  mov     ebx, eax
0x180036064  test    eax, eax
0x180036066  js      loc_180036140
0x18003606c  mov     rcx, [rbp+arg_8]
0x180036070  mov     rdx, [rbp+ppBuffer]
0x180036074  mov     rax, [rcx]
0x180036077  mov     rax, [rax+150h]
0x18003607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036083  mov     ebx, eax
0x180036085  test    eax, eax
0x180036087  js      short loc_1800360AB
0x180036089  mov     eax, [rbp+var_30]
0x18003608c  lea     rcx, [rbp+ppBuffer]; void *
0x180036090  add     [rbp+var_20], rax
0x180036094  sub     r13d, eax
0x180036097  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18003609c  mov     rax, [rbp+var_10]
0x1800360a0  mov     r14, r12
0x1800360a3  xor     r12d, r12d
0x1800360a6  jmp     loc_180035FCF
0x1800360ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360b2  test    rcx, rcx
0x1800360b5  jnz     short loc_1800360FE
0x1800360b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800360be  nop     dword ptr [rax+rax+00h]
0x1800360c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360ca  mov     rcx, rax
0x1800360cd  test    rax, rax
0x1800360d0  jz      short loc_1800360F0
0x1800360d2  mov     rax, [rax]
0x1800360d5  mov     edx, 7F0h
0x1800360da  mov     rax, [rax+8]
0x1800360de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360e3  test    eax, eax
0x1800360e5  jz      short loc_1800360F0
0x1800360e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360ee  jmp     short loc_1800360FE
0x1800360f0  lea     rcx, qword_1801B97E0; this
0x1800360f7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800360fe  cmp     byte ptr [rcx+8], 0
0x180036102  jz      short loc_180036129
0x180036104  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180036109  cmp     [rax+7CCh], ebx
0x18003610f  jz      short loc_180036129
0x180036111  mov     r9d, ebx; int
0x180036114  lea     rdx, aCsourcepluginb_7; "CSourcePluginBufferReader::ReadSampleDa"...
0x18003611b  mov     r8d, 13Eh; int
  ... truncated ...
```
