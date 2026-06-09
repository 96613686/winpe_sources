# CMFADTSPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x18009c498`
- end: `0x18009c9e9`
- name: `?FeedNextBufferToPlugin@CMFADTSPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CMFADTSPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f914c`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18009c498`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c515`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c664`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c6e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c76c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c80c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c8d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c95a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c515`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c5bc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c664`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c6e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c76c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c80c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c8d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009c95a`
- `MFPlat!MFCreateMemoryBuffer` at `0x18009c4f9`
- `MFPlat!MFCreateMemoryBuffer` at `0x18009c4f9`

## string_xrefs

- `0x18009c4b5`: `CMFADTSPropertyHandler::FeedNextBufferToPlugin`
- `0x18009c57a`: `CMFADTSPropertyHandler::FeedNextBufferToPlugin`

## pseudocode

```c
__int64 __fastcall CMFADTSPropertyHandler::FeedNextBufferToPlugin(
        CMFADTSPropertyHandler *this,
        struct IMFSourceHeaderParserPlugin *a2,
        __int64 a3,
        unsigned __int64 *a4,
        int *a5)
{
  unsigned __int64 v9; // rsi
  __int64 v10; // rdx
  HRESULT v11; // ebx
  __int64 v12; // r8
  __int64 v13; // r9
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  wchar_t *v21; // rcx
  CallStackTracing *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  int v40; // ecx
  unsigned __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  wchar_t *v45; // rcx
  CallStackTracing *v46; // rax
  int v47; // ecx
  wchar_t *v48; // rcx
  CallStackTracing *v49; // rax
  unsigned int v51; // [rsp+40h] [rbp-38h] BYREF
  int v52; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-30h] BYREF
  int v54; // [rsp+4Ch] [rbp-2Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-28h] BYREF
  __int64 v56; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v57[3]; // [rsp+60h] [rbp-18h] BYREF
  char v58; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v58,
    "CMFADTSPropertyHandler::FeedNextBufferToPlugin",
    194);
  v9 = *a4;
  ppBuffer = 0;
  v52 = 0;
  v56 = 0;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v57[0] = 0;
  v11 = MFCreateMemoryBuffer(0x4000u, &ppBuffer);
  if ( v11 >= 0 )
  {
    v11 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v56,
            &v53,
            &v54);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**((_QWORD **)this + 111) + 24LL))(
              *((_QWORD *)this + 111),
              v56,
              v53,
              &v51);
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v11 >= 0 )
      {
        if ( v51 )
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
                    &v52);
            if ( v11 >= 0 )
            {
              v40 = v52;
              if ( !v52 )
                goto LABEL_81;
              v41 = v9 + v51;
              if ( v41 < v9 )
              {
                v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                v11 = -2147024362;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v41, v36, v37);
                  CallStackTracing::s_wpInstance = v49;
                  if ( v49
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
                  {
                    v48 = (wchar_t *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v48 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                  }
                }
                if ( *((_BYTE *)v48 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v48);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
                  {
                    v17 = 233;
                    goto LABEL_10;
                  }
                }
                goto LABEL_83;
              }
              v11 = 0;
              if ( *a4 == -1 )
              {
                *a4 = v41;
              }
              else if ( *a4 != v41 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 111) + 40LL))(
                        *((_QWORD *)this + 111),
                        *a4,
                        0,
                        v57);
                if ( v11 < 0 )
                {
                  v45 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v42, v43, v44);
                    CallStackTracing::s_wpInstance = v46;
                    if ( v46
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
                    {
                      v45 = (wchar_t *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v45 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
                    }
                  }
                  if ( *((_BYTE *)v45 + 8) )
                  {
                    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
                    {
                      v17 = 246;
                      goto LABEL_10;
                    }
                  }
                  goto LABEL_83;
                }
                v40 = v52;
              }
              if ( v40 )
                v47 = 0;
              else
LABEL_81:
                v47 = 1;
              *a5 = v47;
              goto LABEL_83;
            }
            v38 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
              {
                v17 = 229;
                goto LABEL_10;
              }
            }
          }
          else
          {
            v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
              CallStackTracing::s_wpInstance = v34;
              if ( v34
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
              {
                v17 = 227;
                goto LABEL_10;
              }
            }
          }
        }
        else
        {
          v28 = (wchar_t *)CallStackTracing::s_wpInstance;
          v11 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v24, v25);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            {
              v17 = 224;
              goto LABEL_10;
            }
          }
        }
      }
      else
      {
        v26 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24, v25);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
          {
            v17 = 216;
            goto LABEL_10;
          }
        }
      }
    }
    else
    {
      v21 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
        {
          v17 = 210;
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v14 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
      {
        v17 = 208;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFADTSPropertyHandler::FeedNextBufferToPlugin",
          v17,
          v11);
      }
    }
  }
LABEL_83:
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v58);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18009c498  push    rbp
0x18009c49a  push    rbx
0x18009c49b  push    rsi
0x18009c49c  push    rdi
0x18009c49d  push    r12
0x18009c49f  push    r13
0x18009c4a1  push    r14
0x18009c4a3  push    r15
0x18009c4a5  mov     rbp, rsp
0x18009c4a8  sub     rsp, 78h
0x18009c4ac  mov     r12, r8
0x18009c4af  mov     r14, rdx
0x18009c4b2  mov     r15, rcx
0x18009c4b5  lea     rdx, aCmfadtspropert_1; "CMFADTSPropertyHandler::FeedNextBufferT"...
0x18009c4bc  mov     r8d, 0C2h; int
0x18009c4c2  lea     rcx, [rbp+arg_18]; this
0x18009c4c6  mov     rdi, r9
0x18009c4c9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18009c4ce  mov     rsi, [rdi]
0x18009c4d1  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x18009c4d5  xor     r13d, r13d
0x18009c4d8  mov     ecx, 4000h; cbMaxLength
0x18009c4dd  mov     [rbp+ppBuffer], r13
0x18009c4e1  mov     [rbp+var_34], r13d
0x18009c4e5  mov     [rbp+var_20], r13
0x18009c4e9  mov     [rbp+var_2C], r13d
0x18009c4ed  mov     [rbp+var_30], r13d
0x18009c4f1  mov     [rbp+var_38], r13d
0x18009c4f5  mov     [rbp+var_18], r13
0x18009c4f9  call    cs:__imp_MFCreateMemoryBuffer
0x18009c4ff  mov     ebx, eax
0x18009c501  test    eax, eax
0x18009c503  jns     loc_18009C58E
0x18009c509  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c510  test    rcx, rcx
0x18009c513  jnz     short loc_18009C556
0x18009c515  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c51b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c522  mov     rcx, rax
0x18009c525  test    rax, rax
0x18009c528  jz      short loc_18009C548
0x18009c52a  mov     rax, [rax]
0x18009c52d  mov     edx, 7F0h
0x18009c532  mov     rax, [rax+8]
0x18009c536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c53b  test    eax, eax
0x18009c53d  jz      short loc_18009C548
0x18009c53f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c546  jmp     short loc_18009C556
0x18009c548  lea     rcx, qword_1801B07E0; this
0x18009c54f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c556  cmp     [rcx+8], r13b
0x18009c55a  jz      loc_18009C9C4
0x18009c560  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c565  cmp     [rax+7CCh], ebx
0x18009c56b  jz      loc_18009C9C4
0x18009c571  mov     r8d, 0D0h; int
0x18009c577  mov     r9d, ebx; int
0x18009c57a  lea     rdx, aCmfadtspropert_1; "CMFADTSPropertyHandler::FeedNextBufferT"...
0x18009c581  mov     rcx, rax; this
0x18009c584  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009c589  jmp     loc_18009C9C4
0x18009c58e  mov     rcx, [rbp+ppBuffer]
0x18009c592  lea     r9, [rbp+var_2C]
0x18009c596  lea     r8, [rbp+var_30]
0x18009c59a  lea     rdx, [rbp+var_20]
0x18009c59e  mov     rax, [rcx]
0x18009c5a1  mov     rax, [rax+18h]
0x18009c5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c5aa  mov     ebx, eax
0x18009c5ac  test    eax, eax
0x18009c5ae  jns     short loc_18009C623
0x18009c5b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c5b7  test    rcx, rcx
0x18009c5ba  jnz     short loc_18009C5FD
0x18009c5bc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c5c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c5c9  mov     rcx, rax
0x18009c5cc  test    rax, rax
0x18009c5cf  jz      short loc_18009C5EF
0x18009c5d1  mov     rax, [rax]
0x18009c5d4  mov     edx, 7F0h
0x18009c5d9  mov     rax, [rax+8]
0x18009c5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c5e2  test    eax, eax
0x18009c5e4  jz      short loc_18009C5EF
0x18009c5e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c5ed  jmp     short loc_18009C5FD
0x18009c5ef  lea     rcx, qword_1801B07E0; this
0x18009c5f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c5fd  cmp     [rcx+8], r13b
0x18009c601  jz      loc_18009C9C4
0x18009c607  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c60c  cmp     [rax+7CCh], ebx
0x18009c612  jz      loc_18009C9C4
0x18009c618  mov     r8d, 0D2h
0x18009c61e  jmp     loc_18009C577
0x18009c623  mov     rcx, [r15+378h]
0x18009c62a  lea     r9, [rbp+var_38]
0x18009c62e  mov     r8d, [rbp+var_30]
0x18009c632  mov     rdx, [rbp+var_20]
0x18009c636  mov     rax, [rcx]
0x18009c639  mov     rax, [rax+18h]
0x18009c63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c642  mov     rcx, [rbp+ppBuffer]
0x18009c646  mov     ebx, eax
0x18009c648  mov     rax, [rcx]
0x18009c64b  mov     rax, [rax+20h]
0x18009c64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c654  test    ebx, ebx
0x18009c656  jns     short loc_18009C6CB
0x18009c658  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c65f  test    rcx, rcx
0x18009c662  jnz     short loc_18009C6A5
0x18009c664  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c66a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c671  mov     rcx, rax
0x18009c674  test    rax, rax
0x18009c677  jz      short loc_18009C697
0x18009c679  mov     rax, [rax]
0x18009c67c  mov     edx, 7F0h
0x18009c681  mov     rax, [rax+8]
0x18009c685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c68a  test    eax, eax
0x18009c68c  jz      short loc_18009C697
0x18009c68e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c695  jmp     short loc_18009C6A5
0x18009c697  lea     rcx, qword_1801B07E0; this
0x18009c69e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c6a5  cmp     [rcx+8], r13b
0x18009c6a9  jz      loc_18009C9C4
0x18009c6af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c6b4  cmp     [rax+7CCh], ebx
0x18009c6ba  jz      loc_18009C9C4
0x18009c6c0  mov     r8d, 0D8h
0x18009c6c6  jmp     loc_18009C577
0x18009c6cb  mov     edx, [rbp+var_38]
0x18009c6ce  test    edx, edx
0x18009c6d0  jnz     short loc_18009C74A
0x18009c6d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c6d9  mov     ebx, 8000FFFFh
0x18009c6de  test    rcx, rcx
0x18009c6e1  jnz     short loc_18009C724
0x18009c6e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c6e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c6f0  mov     rcx, rax
0x18009c6f3  test    rax, rax
0x18009c6f6  jz      short loc_18009C716
0x18009c6f8  mov     rax, [rax]
0x18009c6fb  mov     edx, 7F0h
0x18009c700  mov     rax, [rax+8]
0x18009c704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c709  test    eax, eax
0x18009c70b  jz      short loc_18009C716
0x18009c70d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c714  jmp     short loc_18009C724
0x18009c716  lea     rcx, qword_1801B07E0; this
0x18009c71d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c724  cmp     [rcx+8], r13b
0x18009c728  jz      loc_18009C9C4
0x18009c72e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c733  cmp     [rax+7CCh], ebx
0x18009c739  jz      loc_18009C9C4
0x18009c73f  mov     r8d, 0E0h
0x18009c745  jmp     loc_18009C577
0x18009c74a  mov     rcx, [rbp+ppBuffer]
0x18009c74e  mov     rax, [rcx]
0x18009c751  mov     rax, [rax+30h]
0x18009c755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c75a  mov     ebx, eax
0x18009c75c  test    eax, eax
0x18009c75e  jns     short loc_18009C7D3
0x18009c760  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c767  test    rcx, rcx
0x18009c76a  jnz     short loc_18009C7AD
0x18009c76c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c772  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c779  mov     rcx, rax
0x18009c77c  test    rax, rax
0x18009c77f  jz      short loc_18009C79F
0x18009c781  mov     rax, [rax]
0x18009c784  mov     edx, 7F0h
0x18009c789  mov     rax, [rax+8]
0x18009c78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c792  test    eax, eax
0x18009c794  jz      short loc_18009C79F
0x18009c796  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c79d  jmp     short loc_18009C7AD
0x18009c79f  lea     rcx, qword_1801B07E0; this
0x18009c7a6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c7ad  cmp     [rcx+8], r13b
0x18009c7b1  jz      loc_18009C9C4
0x18009c7b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c7bc  cmp     [rax+7CCh], ebx
0x18009c7c2  jz      loc_18009C9C4
0x18009c7c8  mov     r8d, 0E3h
0x18009c7ce  jmp     loc_18009C577
0x18009c7d3  mov     rax, [r14]
0x18009c7d6  lea     rcx, [rbp+var_34]
0x18009c7da  mov     r8, [rbp+ppBuffer]
0x18009c7de  mov     r9, rsi
0x18009c7e1  mov     [rsp+78h+var_50], rcx
0x18009c7e6  mov     rdx, r12
0x18009c7e9  mov     rcx, r14
0x18009c7ec  mov     [rsp+78h+var_58], rdi
0x18009c7f1  mov     rax, [rax+18h]
0x18009c7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c7fa  mov     ebx, eax
0x18009c7fc  test    eax, eax
0x18009c7fe  jns     short loc_18009C873
0x18009c800  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c807  test    rcx, rcx
0x18009c80a  jnz     short loc_18009C84D
0x18009c80c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c812  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c819  mov     rcx, rax
0x18009c81c  test    rax, rax
0x18009c81f  jz      short loc_18009C83F
0x18009c821  mov     rax, [rax]
0x18009c824  mov     edx, 7F0h
0x18009c829  mov     rax, [rax+8]
0x18009c82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c832  test    eax, eax
0x18009c834  jz      short loc_18009C83F
0x18009c836  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c83d  jmp     short loc_18009C84D
0x18009c83f  lea     rcx, qword_1801B07E0; this
0x18009c846  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c84d  cmp     [rcx+8], r13b
0x18009c851  jz      loc_18009C9C4
0x18009c857  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c85c  cmp     [rax+7CCh], ebx
0x18009c862  jz      loc_18009C9C4
0x18009c868  mov     r8d, 0E5h
0x18009c86e  jmp     loc_18009C577
0x18009c873  mov     ecx, [rbp+var_34]
0x18009c876  test    ecx, ecx
0x18009c878  jz      loc_18009C9B9
0x18009c87e  mov     edx, [rbp+var_38]
0x18009c881  add     rdx, rsi
0x18009c884  cmp     rdx, rsi
0x18009c887  jb      loc_18009C949
0x18009c88d  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18009c891  mov     ebx, r13d
0x18009c894  jnz     short loc_18009C89E
0x18009c896  mov     [rdi], rdx
0x18009c899  jmp     loc_18009C940
0x18009c89e  cmp     [rdi], rdx
0x18009c8a1  jz      loc_18009C940
0x18009c8a7  mov     rcx, [r15+378h]
0x18009c8ae  lea     r9, [rbp+var_18]
0x18009c8b2  mov     rdx, [rdi]
0x18009c8b5  xor     r8d, r8d
0x18009c8b8  mov     rax, [rcx]
0x18009c8bb  mov     rax, [rax+28h]
0x18009c8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8c4  mov     ebx, eax
0x18009c8c6  test    eax, eax
0x18009c8c8  jns     short loc_18009C93D
0x18009c8ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c8d1  test    rcx, rcx
0x18009c8d4  jnz     short loc_18009C917
0x18009c8d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c8dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c8e3  mov     rcx, rax
0x18009c8e6  test    rax, rax
0x18009c8e9  jz      short loc_18009C909
0x18009c8eb  mov     rax, [rax]
0x18009c8ee  mov     edx, 7F0h
0x18009c8f3  mov     rax, [rax+8]
0x18009c8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8fc  test    eax, eax
0x18009c8fe  jz      short loc_18009C909
0x18009c900  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c907  jmp     short loc_18009C917
0x18009c909  lea     rcx, qword_1801B07E0; this
0x18009c910  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c917  cmp     [rcx+8], r13b
0x18009c91b  jz      loc_18009C9C4
0x18009c921  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18009c926  cmp     [rax+7CCh], ebx
0x18009c92c  jz      loc_18009C9C4
0x18009c932  mov     r8d, 0F6h
0x18009c938  jmp     loc_18009C577
0x18009c93d  mov     ecx, [rbp+var_34]
0x18009c940  test    ecx, ecx
0x18009c942  jz      short loc_18009C9B9
0x18009c944  mov     ecx, r13d
0x18009c947  jmp     short loc_18009C9BE
0x18009c949  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c950  mov     ebx, 80070216h
0x18009c955  test    rcx, rcx
0x18009c958  jnz     short loc_18009C99B
0x18009c95a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009c960  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009c967  mov     rcx, rax
0x18009c96a  test    rax, rax
0x18009c96d  jz      short loc_18009C98D
0x18009c96f  mov     rax, [rax]
0x18009c972  mov     edx, 7F0h
  ... truncated ...
```
