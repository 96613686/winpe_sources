# CMFAC3PropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800a9700`
- end: `0x1800a9c51`
- name: `?FeedNextBufferToPlugin@CMFAC3PropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CMFAC3PropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008c9fc`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x1800a9700`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a977d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9824`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a98cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a994b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a99d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9bc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a977d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9824`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a98cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a994b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a99d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9b3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9bc2`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800a9761`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800a9761`

## string_xrefs

- `0x1800a971d`: `CMFAC3PropertyHandler::FeedNextBufferToPlugin`
- `0x1800a97e2`: `CMFAC3PropertyHandler::FeedNextBufferToPlugin`

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
                    v36 = &qword_1801B07E0;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                      v33 = &qword_1801B07E0;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v28 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v25 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v22 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v20 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v17 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v12 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800a9700  push    rbp
0x1800a9702  push    rbx
0x1800a9703  push    rsi
0x1800a9704  push    rdi
0x1800a9705  push    r12
0x1800a9707  push    r13
0x1800a9709  push    r14
0x1800a970b  push    r15
0x1800a970d  mov     rbp, rsp
0x1800a9710  sub     rsp, 78h
0x1800a9714  mov     r12, r8
0x1800a9717  mov     r14, rdx
0x1800a971a  mov     r15, rcx
0x1800a971d  lea     rdx, aCmfac3property; "CMFAC3PropertyHandler::FeedNextBufferTo"...
0x1800a9724  mov     r8d, 0CDh; int
0x1800a972a  lea     rcx, [rbp+arg_18]; this
0x1800a972e  mov     rdi, r9
0x1800a9731  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a9736  mov     rsi, [rdi]
0x1800a9739  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800a973d  xor     r13d, r13d
0x1800a9740  mov     ecx, 4000h; cbMaxLength
0x1800a9745  mov     [rbp+ppBuffer], r13
0x1800a9749  mov     [rbp+var_34], r13d
0x1800a974d  mov     [rbp+var_20], r13
0x1800a9751  mov     [rbp+var_2C], r13d
0x1800a9755  mov     [rbp+var_30], r13d
0x1800a9759  mov     [rbp+var_38], r13d
0x1800a975d  mov     [rbp+var_18], r13
0x1800a9761  call    cs:__imp_MFCreateMemoryBuffer
0x1800a9767  mov     ebx, eax
0x1800a9769  test    eax, eax
0x1800a976b  jns     loc_1800A97F6
0x1800a9771  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9778  test    rcx, rcx
0x1800a977b  jnz     short loc_1800A97BE
0x1800a977d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9783  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a978a  mov     rcx, rax
0x1800a978d  test    rax, rax
0x1800a9790  jz      short loc_1800A97B0
0x1800a9792  mov     rax, [rax]
0x1800a9795  mov     edx, 7F0h
0x1800a979a  mov     rax, [rax+8]
0x1800a979e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a97a3  test    eax, eax
0x1800a97a5  jz      short loc_1800A97B0
0x1800a97a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97ae  jmp     short loc_1800A97BE
0x1800a97b0  lea     rcx, qword_1801B07E0; this
0x1800a97b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97be  cmp     [rcx+8], r13b
0x1800a97c2  jz      loc_1800A9C2C
0x1800a97c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a97cd  cmp     [rax+7CCh], ebx
0x1800a97d3  jz      loc_1800A9C2C
0x1800a97d9  mov     r8d, 0DBh; int
0x1800a97df  mov     r9d, ebx; int
0x1800a97e2  lea     rdx, aCmfac3property; "CMFAC3PropertyHandler::FeedNextBufferTo"...
0x1800a97e9  mov     rcx, rax; this
0x1800a97ec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a97f1  jmp     loc_1800A9C2C
0x1800a97f6  mov     rcx, [rbp+ppBuffer]
0x1800a97fa  lea     r9, [rbp+var_2C]
0x1800a97fe  lea     r8, [rbp+var_30]
0x1800a9802  lea     rdx, [rbp+var_20]
0x1800a9806  mov     rax, [rcx]
0x1800a9809  mov     rax, [rax+18h]
0x1800a980d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9812  mov     ebx, eax
0x1800a9814  test    eax, eax
0x1800a9816  jns     short loc_1800A988B
0x1800a9818  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a981f  test    rcx, rcx
0x1800a9822  jnz     short loc_1800A9865
0x1800a9824  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a982a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9831  mov     rcx, rax
0x1800a9834  test    rax, rax
0x1800a9837  jz      short loc_1800A9857
0x1800a9839  mov     rax, [rax]
0x1800a983c  mov     edx, 7F0h
0x1800a9841  mov     rax, [rax+8]
0x1800a9845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a984a  test    eax, eax
0x1800a984c  jz      short loc_1800A9857
0x1800a984e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9855  jmp     short loc_1800A9865
0x1800a9857  lea     rcx, qword_1801B07E0; this
0x1800a985e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9865  cmp     [rcx+8], r13b
0x1800a9869  jz      loc_1800A9C2C
0x1800a986f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9874  cmp     [rax+7CCh], ebx
0x1800a987a  jz      loc_1800A9C2C
0x1800a9880  mov     r8d, 0DDh
0x1800a9886  jmp     loc_1800A97DF
0x1800a988b  mov     rcx, [r15+378h]
0x1800a9892  lea     r9, [rbp+var_38]
0x1800a9896  mov     r8d, [rbp+var_30]
0x1800a989a  mov     rdx, [rbp+var_20]
0x1800a989e  mov     rax, [rcx]
0x1800a98a1  mov     rax, [rax+18h]
0x1800a98a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98aa  mov     rcx, [rbp+ppBuffer]
0x1800a98ae  mov     ebx, eax
0x1800a98b0  mov     rax, [rcx]
0x1800a98b3  mov     rax, [rax+20h]
0x1800a98b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98bc  test    ebx, ebx
0x1800a98be  jns     short loc_1800A9933
0x1800a98c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a98c7  test    rcx, rcx
0x1800a98ca  jnz     short loc_1800A990D
0x1800a98cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a98d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a98d9  mov     rcx, rax
0x1800a98dc  test    rax, rax
0x1800a98df  jz      short loc_1800A98FF
0x1800a98e1  mov     rax, [rax]
0x1800a98e4  mov     edx, 7F0h
0x1800a98e9  mov     rax, [rax+8]
0x1800a98ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98f2  test    eax, eax
0x1800a98f4  jz      short loc_1800A98FF
0x1800a98f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a98fd  jmp     short loc_1800A990D
0x1800a98ff  lea     rcx, qword_1801B07E0; this
0x1800a9906  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a990d  cmp     [rcx+8], r13b
0x1800a9911  jz      loc_1800A9C2C
0x1800a9917  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a991c  cmp     [rax+7CCh], ebx
0x1800a9922  jz      loc_1800A9C2C
0x1800a9928  mov     r8d, 0E3h
0x1800a992e  jmp     loc_1800A97DF
0x1800a9933  mov     edx, [rbp+var_38]
0x1800a9936  test    edx, edx
0x1800a9938  jnz     short loc_1800A99B2
0x1800a993a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9941  mov     ebx, 8000FFFFh
0x1800a9946  test    rcx, rcx
0x1800a9949  jnz     short loc_1800A998C
0x1800a994b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9958  mov     rcx, rax
0x1800a995b  test    rax, rax
0x1800a995e  jz      short loc_1800A997E
0x1800a9960  mov     rax, [rax]
0x1800a9963  mov     edx, 7F0h
0x1800a9968  mov     rax, [rax+8]
0x1800a996c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9971  test    eax, eax
0x1800a9973  jz      short loc_1800A997E
0x1800a9975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a997c  jmp     short loc_1800A998C
0x1800a997e  lea     rcx, qword_1801B07E0; this
0x1800a9985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a998c  cmp     [rcx+8], r13b
0x1800a9990  jz      loc_1800A9C2C
0x1800a9996  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a999b  cmp     [rax+7CCh], ebx
0x1800a99a1  jz      loc_1800A9C2C
0x1800a99a7  mov     r8d, 0EBh
0x1800a99ad  jmp     loc_1800A97DF
0x1800a99b2  mov     rcx, [rbp+ppBuffer]
0x1800a99b6  mov     rax, [rcx]
0x1800a99b9  mov     rax, [rax+30h]
0x1800a99bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99c2  mov     ebx, eax
0x1800a99c4  test    eax, eax
0x1800a99c6  jns     short loc_1800A9A3B
0x1800a99c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a99cf  test    rcx, rcx
0x1800a99d2  jnz     short loc_1800A9A15
0x1800a99d4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a99da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a99e1  mov     rcx, rax
0x1800a99e4  test    rax, rax
0x1800a99e7  jz      short loc_1800A9A07
0x1800a99e9  mov     rax, [rax]
0x1800a99ec  mov     edx, 7F0h
0x1800a99f1  mov     rax, [rax+8]
0x1800a99f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99fa  test    eax, eax
0x1800a99fc  jz      short loc_1800A9A07
0x1800a99fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a05  jmp     short loc_1800A9A15
0x1800a9a07  lea     rcx, qword_1801B07E0; this
0x1800a9a0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a15  cmp     [rcx+8], r13b
0x1800a9a19  jz      loc_1800A9C2C
0x1800a9a1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9a24  cmp     [rax+7CCh], ebx
0x1800a9a2a  jz      loc_1800A9C2C
0x1800a9a30  mov     r8d, 0EEh
0x1800a9a36  jmp     loc_1800A97DF
0x1800a9a3b  mov     rax, [r14]
0x1800a9a3e  lea     rcx, [rbp+var_34]
0x1800a9a42  mov     r8, [rbp+ppBuffer]
0x1800a9a46  mov     r9, rsi
0x1800a9a49  mov     [rsp+78h+var_50], rcx
0x1800a9a4e  mov     rdx, r12
0x1800a9a51  mov     rcx, r14
0x1800a9a54  mov     [rsp+78h+var_58], rdi
0x1800a9a59  mov     rax, [rax+18h]
0x1800a9a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a62  mov     ebx, eax
0x1800a9a64  test    eax, eax
0x1800a9a66  jns     short loc_1800A9ADB
0x1800a9a68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a6f  test    rcx, rcx
0x1800a9a72  jnz     short loc_1800A9AB5
0x1800a9a74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9a7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a81  mov     rcx, rax
0x1800a9a84  test    rax, rax
0x1800a9a87  jz      short loc_1800A9AA7
0x1800a9a89  mov     rax, [rax]
0x1800a9a8c  mov     edx, 7F0h
0x1800a9a91  mov     rax, [rax+8]
0x1800a9a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a9a  test    eax, eax
0x1800a9a9c  jz      short loc_1800A9AA7
0x1800a9a9e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9aa5  jmp     short loc_1800A9AB5
0x1800a9aa7  lea     rcx, qword_1801B07E0; this
0x1800a9aae  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9ab5  cmp     [rcx+8], r13b
0x1800a9ab9  jz      loc_1800A9C2C
0x1800a9abf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9ac4  cmp     [rax+7CCh], ebx
0x1800a9aca  jz      loc_1800A9C2C
0x1800a9ad0  mov     r8d, 0F0h
0x1800a9ad6  jmp     loc_1800A97DF
0x1800a9adb  mov     ecx, [rbp+var_34]
0x1800a9ade  test    ecx, ecx
0x1800a9ae0  jz      loc_1800A9C21
0x1800a9ae6  mov     edx, [rbp+var_38]
0x1800a9ae9  add     rdx, rsi
0x1800a9aec  cmp     rdx, rsi
0x1800a9aef  jb      loc_1800A9BB1
0x1800a9af5  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800a9af9  mov     ebx, r13d
0x1800a9afc  jnz     short loc_1800A9B06
0x1800a9afe  mov     [rdi], rdx
0x1800a9b01  jmp     loc_1800A9BA8
0x1800a9b06  cmp     [rdi], rdx
0x1800a9b09  jz      loc_1800A9BA8
0x1800a9b0f  mov     rcx, [r15+378h]
0x1800a9b16  lea     r9, [rbp+var_18]
0x1800a9b1a  mov     rdx, [rdi]
0x1800a9b1d  xor     r8d, r8d
0x1800a9b20  mov     rax, [rcx]
0x1800a9b23  mov     rax, [rax+28h]
0x1800a9b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9b2c  mov     ebx, eax
0x1800a9b2e  test    eax, eax
0x1800a9b30  jns     short loc_1800A9BA5
0x1800a9b32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b39  test    rcx, rcx
0x1800a9b3c  jnz     short loc_1800A9B7F
0x1800a9b3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9b44  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b4b  mov     rcx, rax
0x1800a9b4e  test    rax, rax
0x1800a9b51  jz      short loc_1800A9B71
0x1800a9b53  mov     rax, [rax]
0x1800a9b56  mov     edx, 7F0h
0x1800a9b5b  mov     rax, [rax+8]
0x1800a9b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9b64  test    eax, eax
0x1800a9b66  jz      short loc_1800A9B71
0x1800a9b68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b6f  jmp     short loc_1800A9B7F
0x1800a9b71  lea     rcx, qword_1801B07E0; this
0x1800a9b78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9b7f  cmp     [rcx+8], r13b
0x1800a9b83  jz      loc_1800A9C2C
0x1800a9b89  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9b8e  cmp     [rax+7CCh], ebx
0x1800a9b94  jz      loc_1800A9C2C
0x1800a9b9a  mov     r8d, 101h
0x1800a9ba0  jmp     loc_1800A97DF
0x1800a9ba5  mov     ecx, [rbp+var_34]
0x1800a9ba8  test    ecx, ecx
0x1800a9baa  jz      short loc_1800A9C21
0x1800a9bac  mov     ecx, r13d
0x1800a9baf  jmp     short loc_1800A9C26
0x1800a9bb1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9bb8  mov     ebx, 80070216h
0x1800a9bbd  test    rcx, rcx
0x1800a9bc0  jnz     short loc_1800A9C03
0x1800a9bc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9bc8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9bcf  mov     rcx, rax
0x1800a9bd2  test    rax, rax
0x1800a9bd5  jz      short loc_1800A9BF5
0x1800a9bd7  mov     rax, [rax]
0x1800a9bda  mov     edx, 7F0h
  ... truncated ...
```
