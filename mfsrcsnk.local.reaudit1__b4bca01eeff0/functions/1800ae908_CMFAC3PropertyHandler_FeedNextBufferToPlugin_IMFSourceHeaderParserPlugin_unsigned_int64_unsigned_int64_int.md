# CMFAC3PropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800ae908`
- end: `0x1800aee90`
- name: `?FeedNextBufferToPlugin@CMFAC3PropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CMFAC3PropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800919f8`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800ae908`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae98b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aea38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeae6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeb6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aebfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aed70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aedfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae98b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aea38`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeae6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeb6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aebfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aeca0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aed70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aedfa`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ae969`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800ae969`

## string_xrefs

- `0x1800ae925`: `CMFAC3PropertyHandler::FeedNextBufferToPlugin`
- `0x1800ae9f6`: `CMFAC3PropertyHandler::FeedNextBufferToPlugin`

## pseudocode

```c
__int64 __fastcall CMFAC3PropertyHandler::FeedNextBufferToPlugin(
        CMFAC3PropertyHandler *this,
        struct IMFSourceHeaderParserPlugin *a2,
        __int64 a3,
        unsigned __int64 *a4,
        int *a5)
{
  unsigned __int64 v9; // rsi
  __int64 v10; // rdx
  HRESULT v11; // ebx
  wchar_t *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v15; // r8d
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  CallStackTracing *v21; // rax
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  wchar_t *v25; // rcx
  CallStackTracing *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  int v30; // ecx
  unsigned __int64 v31; // rdx
  __int64 v32; // rdx
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  int v35; // ecx
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  unsigned int v39; // [rsp+40h] [rbp-38h] BYREF
  int v40; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-30h] BYREF
  int v42; // [rsp+4Ch] [rbp-2Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-28h] BYREF
  __int64 v44; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v45[3]; // [rsp+60h] [rbp-18h] BYREF
  char v46; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v46,
    "CMFAC3PropertyHandler::FeedNextBufferToPlugin",
    205);
  v9 = *a4;
  ppBuffer = 0;
  v40 = 0;
  v44 = 0;
  v42 = 0;
  v41 = 0;
  v39 = 0;
  v45[0] = 0;
  v11 = MFCreateMemoryBuffer(0x4000u, &ppBuffer);
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v44,
            &v41,
            &v42);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**((_QWORD **)this + 111) + 24LL))(
              *((_QWORD *)this + 111),
              v44,
              v41,
              &v39);
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v11 >= 0 )
      {
        if ( v39 )
        {
          v11 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(struct IMFSourceHeaderParserPlugin *, __int64, IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    a3,
                    ppBuffer,
                    v9,
                    a4,
                    &v40);
            if ( v11 >= 0 )
            {
              v30 = v40;
              if ( !v40 )
                goto LABEL_81;
              v31 = v9 + v39;
              if ( v31 < v9 )
              {
                v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                v11 = -2147024362;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
                  CallStackTracing::s_wpInstance = v37;
                  if ( v37
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                  {
                    v36 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v36 = &qword_1801B97E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
                  }
                }
                if ( *((_BYTE *)v36 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
                  {
                    v15 = 244;
                    goto LABEL_10;
                  }
                }
                goto LABEL_83;
              }
              v11 = 0;
              if ( *a4 == -1 )
              {
                *a4 = v31;
              }
              else if ( *a4 != v31 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 111) + 40LL))(
                        *((_QWORD *)this + 111),
                        *a4,
                        0,
                        v45);
                if ( v11 < 0 )
                {
                  v33 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
                    CallStackTracing::s_wpInstance = v34;
                    if ( v34
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
                    {
                      v15 = 257;
                      goto LABEL_10;
                    }
                  }
                  goto LABEL_83;
                }
                v30 = v40;
              }
              if ( v30 )
                v35 = 0;
              else
LABEL_81:
                v35 = 1;
              *a5 = v35;
              goto LABEL_83;
            }
            v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
              CallStackTracing::s_wpInstance = v29;
              if ( v29
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
              {
                v28 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v28 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v28 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
              {
                v15 = 240;
                goto LABEL_10;
              }
            }
          }
          else
          {
            v25 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
              {
                v15 = 238;
                goto LABEL_10;
              }
            }
          }
        }
        else
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          v11 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            {
              v15 = 235;
              goto LABEL_10;
            }
          }
        }
      }
      else
      {
        v20 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
          CallStackTracing::s_wpInstance = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v20 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
          {
            v15 = 227;
            goto LABEL_10;
          }
        }
      }
    }
    else
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        {
          v15 = 221;
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v12 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
      {
        v15 = 219;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFAC3PropertyHandler::FeedNextBufferToPlugin", v15, v11);
      }
    }
  }
LABEL_83:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v46);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800ae908  push    rbp
0x1800ae90a  push    rbx
0x1800ae90b  push    rsi
0x1800ae90c  push    rdi
0x1800ae90d  push    r12
0x1800ae90f  push    r13
0x1800ae911  push    r14
0x1800ae913  push    r15
0x1800ae915  mov     rbp, rsp
0x1800ae918  sub     rsp, 78h
0x1800ae91c  mov     r12, r8
0x1800ae91f  mov     r14, rdx
0x1800ae922  mov     r15, rcx
0x1800ae925  lea     rdx, aCmfac3property; "CMFAC3PropertyHandler::FeedNextBufferTo"...
0x1800ae92c  mov     r8d, 0CDh; int
0x1800ae932  lea     rcx, [rbp+arg_18]; this
0x1800ae936  mov     rdi, r9
0x1800ae939  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ae93e  mov     rsi, [rdi]
0x1800ae941  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800ae945  xor     r13d, r13d
0x1800ae948  mov     ecx, 4000h; cbMaxLength
0x1800ae94d  mov     [rbp+ppBuffer], r13
0x1800ae951  mov     [rbp+var_34], r13d
0x1800ae955  mov     [rbp+var_20], r13
0x1800ae959  mov     [rbp+var_2C], r13d
0x1800ae95d  mov     [rbp+var_30], r13d
0x1800ae961  mov     [rbp+var_38], r13d
0x1800ae965  mov     [rbp+var_18], r13
0x1800ae969  call    cs:__imp_MFCreateMemoryBuffer
0x1800ae970  nop     dword ptr [rax+rax+00h]
0x1800ae975  mov     ebx, eax
0x1800ae977  test    eax, eax
0x1800ae979  jns     loc_1800AEA0A
0x1800ae97f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae986  test    rcx, rcx
0x1800ae989  jnz     short loc_1800AE9D2
0x1800ae98b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae992  nop     dword ptr [rax+rax+00h]
0x1800ae997  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae99e  mov     rcx, rax
0x1800ae9a1  test    rax, rax
0x1800ae9a4  jz      short loc_1800AE9C4
0x1800ae9a6  mov     rax, [rax]
0x1800ae9a9  mov     edx, 7F0h
0x1800ae9ae  mov     rax, [rax+8]
0x1800ae9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9b7  test    eax, eax
0x1800ae9b9  jz      short loc_1800AE9C4
0x1800ae9bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae9c2  jmp     short loc_1800AE9D2
0x1800ae9c4  lea     rcx, qword_1801B97E0; this
0x1800ae9cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae9d2  cmp     [rcx+8], r13b
0x1800ae9d6  jz      loc_1800AEE6A
0x1800ae9dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae9e1  cmp     [rax+7CCh], ebx
0x1800ae9e7  jz      loc_1800AEE6A
0x1800ae9ed  mov     r8d, 0DBh; int
0x1800ae9f3  mov     r9d, ebx; int
0x1800ae9f6  lea     rdx, aCmfac3property; "CMFAC3PropertyHandler::FeedNextBufferTo"...
0x1800ae9fd  mov     rcx, rax; this
0x1800aea00  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800aea05  jmp     loc_1800AEE6A
0x1800aea0a  mov     rcx, [rbp+ppBuffer]
0x1800aea0e  lea     r9, [rbp+var_2C]
0x1800aea12  lea     r8, [rbp+var_30]
0x1800aea16  lea     rdx, [rbp+var_20]
0x1800aea1a  mov     rax, [rcx]
0x1800aea1d  mov     rax, [rax+18h]
0x1800aea21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea26  mov     ebx, eax
0x1800aea28  test    eax, eax
0x1800aea2a  jns     short loc_1800AEAA5
0x1800aea2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea33  test    rcx, rcx
0x1800aea36  jnz     short loc_1800AEA7F
0x1800aea38  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aea3f  nop     dword ptr [rax+rax+00h]
0x1800aea44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea4b  mov     rcx, rax
0x1800aea4e  test    rax, rax
0x1800aea51  jz      short loc_1800AEA71
0x1800aea53  mov     rax, [rax]
0x1800aea56  mov     edx, 7F0h
0x1800aea5b  mov     rax, [rax+8]
0x1800aea5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aea64  test    eax, eax
0x1800aea66  jz      short loc_1800AEA71
0x1800aea68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea6f  jmp     short loc_1800AEA7F
0x1800aea71  lea     rcx, qword_1801B97E0; this
0x1800aea78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aea7f  cmp     [rcx+8], r13b
0x1800aea83  jz      loc_1800AEE6A
0x1800aea89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aea8e  cmp     [rax+7CCh], ebx
0x1800aea94  jz      loc_1800AEE6A
0x1800aea9a  mov     r8d, 0DDh
0x1800aeaa0  jmp     loc_1800AE9F3
0x1800aeaa5  mov     rcx, [r15+378h]
0x1800aeaac  lea     r9, [rbp+var_38]
0x1800aeab0  mov     r8d, [rbp+var_30]
0x1800aeab4  mov     rdx, [rbp+var_20]
0x1800aeab8  mov     rax, [rcx]
0x1800aeabb  mov     rax, [rax+18h]
0x1800aeabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeac4  mov     rcx, [rbp+ppBuffer]
0x1800aeac8  mov     ebx, eax
0x1800aeaca  mov     rax, [rcx]
0x1800aeacd  mov     rax, [rax+20h]
0x1800aead1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aead6  test    ebx, ebx
0x1800aead8  jns     short loc_1800AEB53
0x1800aeada  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeae1  test    rcx, rcx
0x1800aeae4  jnz     short loc_1800AEB2D
0x1800aeae6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aeaed  nop     dword ptr [rax+rax+00h]
0x1800aeaf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeaf9  mov     rcx, rax
0x1800aeafc  test    rax, rax
0x1800aeaff  jz      short loc_1800AEB1F
0x1800aeb01  mov     rax, [rax]
0x1800aeb04  mov     edx, 7F0h
0x1800aeb09  mov     rax, [rax+8]
0x1800aeb0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb12  test    eax, eax
0x1800aeb14  jz      short loc_1800AEB1F
0x1800aeb16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb1d  jmp     short loc_1800AEB2D
0x1800aeb1f  lea     rcx, qword_1801B97E0; this
0x1800aeb26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb2d  cmp     [rcx+8], r13b
0x1800aeb31  jz      loc_1800AEE6A
0x1800aeb37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aeb3c  cmp     [rax+7CCh], ebx
0x1800aeb42  jz      loc_1800AEE6A
0x1800aeb48  mov     r8d, 0E3h
0x1800aeb4e  jmp     loc_1800AE9F3
0x1800aeb53  mov     edx, [rbp+var_38]
0x1800aeb56  test    edx, edx
0x1800aeb58  jnz     short loc_1800AEBD8
0x1800aeb5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb61  mov     ebx, 8000FFFFh
0x1800aeb66  test    rcx, rcx
0x1800aeb69  jnz     short loc_1800AEBB2
0x1800aeb6b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aeb72  nop     dword ptr [rax+rax+00h]
0x1800aeb77  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeb7e  mov     rcx, rax
0x1800aeb81  test    rax, rax
0x1800aeb84  jz      short loc_1800AEBA4
0x1800aeb86  mov     rax, [rax]
0x1800aeb89  mov     edx, 7F0h
0x1800aeb8e  mov     rax, [rax+8]
0x1800aeb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb97  test    eax, eax
0x1800aeb99  jz      short loc_1800AEBA4
0x1800aeb9b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeba2  jmp     short loc_1800AEBB2
0x1800aeba4  lea     rcx, qword_1801B97E0; this
0x1800aebab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aebb2  cmp     [rcx+8], r13b
0x1800aebb6  jz      loc_1800AEE6A
0x1800aebbc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aebc1  cmp     [rax+7CCh], ebx
0x1800aebc7  jz      loc_1800AEE6A
0x1800aebcd  mov     r8d, 0EBh
0x1800aebd3  jmp     loc_1800AE9F3
0x1800aebd8  mov     rcx, [rbp+ppBuffer]
0x1800aebdc  mov     rax, [rcx]
0x1800aebdf  mov     rax, [rax+30h]
0x1800aebe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aebe8  mov     ebx, eax
0x1800aebea  test    eax, eax
0x1800aebec  jns     short loc_1800AEC67
0x1800aebee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aebf5  test    rcx, rcx
0x1800aebf8  jnz     short loc_1800AEC41
0x1800aebfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aec01  nop     dword ptr [rax+rax+00h]
0x1800aec06  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec0d  mov     rcx, rax
0x1800aec10  test    rax, rax
0x1800aec13  jz      short loc_1800AEC33
0x1800aec15  mov     rax, [rax]
0x1800aec18  mov     edx, 7F0h
0x1800aec1d  mov     rax, [rax+8]
0x1800aec21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec26  test    eax, eax
0x1800aec28  jz      short loc_1800AEC33
0x1800aec2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec31  jmp     short loc_1800AEC41
0x1800aec33  lea     rcx, qword_1801B97E0; this
0x1800aec3a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec41  cmp     [rcx+8], r13b
0x1800aec45  jz      loc_1800AEE6A
0x1800aec4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aec50  cmp     [rax+7CCh], ebx
0x1800aec56  jz      loc_1800AEE6A
0x1800aec5c  mov     r8d, 0EEh
0x1800aec62  jmp     loc_1800AE9F3
0x1800aec67  mov     rax, [r14]
0x1800aec6a  lea     rcx, [rbp+var_34]
0x1800aec6e  mov     r8, [rbp+ppBuffer]
0x1800aec72  mov     r9, rsi
0x1800aec75  mov     [rsp+78h+var_50], rcx
0x1800aec7a  mov     rdx, r12
0x1800aec7d  mov     rcx, r14
0x1800aec80  mov     [rsp+78h+var_58], rdi
0x1800aec85  mov     rax, [rax+18h]
0x1800aec89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec8e  mov     ebx, eax
0x1800aec90  test    eax, eax
0x1800aec92  jns     short loc_1800AED0D
0x1800aec94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aec9b  test    rcx, rcx
0x1800aec9e  jnz     short loc_1800AECE7
0x1800aeca0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aeca7  nop     dword ptr [rax+rax+00h]
0x1800aecac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aecb3  mov     rcx, rax
0x1800aecb6  test    rax, rax
0x1800aecb9  jz      short loc_1800AECD9
0x1800aecbb  mov     rax, [rax]
0x1800aecbe  mov     edx, 7F0h
0x1800aecc3  mov     rax, [rax+8]
0x1800aecc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeccc  test    eax, eax
0x1800aecce  jz      short loc_1800AECD9
0x1800aecd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aecd7  jmp     short loc_1800AECE7
0x1800aecd9  lea     rcx, qword_1801B97E0; this
0x1800aece0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aece7  cmp     [rcx+8], r13b
0x1800aeceb  jz      loc_1800AEE6A
0x1800aecf1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aecf6  cmp     [rax+7CCh], ebx
0x1800aecfc  jz      loc_1800AEE6A
0x1800aed02  mov     r8d, 0F0h
0x1800aed08  jmp     loc_1800AE9F3
0x1800aed0d  mov     ecx, [rbp+var_34]
0x1800aed10  test    ecx, ecx
0x1800aed12  jz      loc_1800AEE5F
0x1800aed18  mov     edx, [rbp+var_38]
0x1800aed1b  add     rdx, rsi
0x1800aed1e  cmp     rdx, rsi
0x1800aed21  jb      loc_1800AEDE9
0x1800aed27  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800aed2b  mov     ebx, r13d
0x1800aed2e  jnz     short loc_1800AED38
0x1800aed30  mov     [rdi], rdx
0x1800aed33  jmp     loc_1800AEDE0
0x1800aed38  cmp     [rdi], rdx
0x1800aed3b  jz      loc_1800AEDE0
0x1800aed41  mov     rcx, [r15+378h]
0x1800aed48  lea     r9, [rbp+var_18]
0x1800aed4c  mov     rdx, [rdi]
0x1800aed4f  xor     r8d, r8d
0x1800aed52  mov     rax, [rcx]
0x1800aed55  mov     rax, [rax+28h]
0x1800aed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed5e  mov     ebx, eax
0x1800aed60  test    eax, eax
0x1800aed62  jns     short loc_1800AEDDD
0x1800aed64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed6b  test    rcx, rcx
0x1800aed6e  jnz     short loc_1800AEDB7
0x1800aed70  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800aed77  nop     dword ptr [rax+rax+00h]
0x1800aed7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aed83  mov     rcx, rax
0x1800aed86  test    rax, rax
0x1800aed89  jz      short loc_1800AEDA9
0x1800aed8b  mov     rax, [rax]
0x1800aed8e  mov     edx, 7F0h
0x1800aed93  mov     rax, [rax+8]
0x1800aed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aed9c  test    eax, eax
0x1800aed9e  jz      short loc_1800AEDA9
0x1800aeda0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aeda7  jmp     short loc_1800AEDB7
0x1800aeda9  lea     rcx, qword_1801B97E0; this
0x1800aedb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aedb7  cmp     [rcx+8], r13b
0x1800aedbb  jz      loc_1800AEE6A
0x1800aedc1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800aedc6  cmp     [rax+7CCh], ebx
0x1800aedcc  jz      loc_1800AEE6A
0x1800aedd2  mov     r8d, 101h
0x1800aedd8  jmp     loc_1800AE9F3
0x1800aeddd  mov     ecx, [rbp+var_34]
0x1800aede0  test    ecx, ecx
0x1800aede2  jz      short loc_1800AEE5F
0x1800aede4  mov     ecx, r13d
0x1800aede7  jmp     short loc_1800AEE64
0x1800aede9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800aedf0  mov     ebx, 80070216h
0x1800aedf5  test    rcx, rcx
  ... truncated ...
```
