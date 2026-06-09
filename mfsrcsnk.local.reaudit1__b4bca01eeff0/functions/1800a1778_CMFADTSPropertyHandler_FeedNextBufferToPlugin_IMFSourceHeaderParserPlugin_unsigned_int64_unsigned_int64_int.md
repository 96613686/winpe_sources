# CMFADTSPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800a1778`
- end: `0x1800a1d00`
- name: `?FeedNextBufferToPlugin@CMFADTSPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CMFADTSPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800fff40`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x1800a1778`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a17fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a18a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1956`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a19db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1a6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1b10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1be0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1c6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a17fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a18a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1956`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a19db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1a6a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1b10`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1be0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a1c6a`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800a17d9`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800a17d9`

## string_xrefs

- `0x1800a1795`: `CMFADTSPropertyHandler::FeedNextBufferToPlugin`
- `0x1800a1866`: `CMFADTSPropertyHandler::FeedNextBufferToPlugin`

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
    "CMFADTSPropertyHandler::FeedNextBufferToPlugin",
    194);
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
                    v15 = 233;
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
                      v15 = 246;
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
                v15 = 229;
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
                v15 = 227;
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
              v15 = 224;
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
            v15 = 216;
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
          v15 = 210;
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
        v15 = 208;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFADTSPropertyHandler::FeedNextBufferToPlugin",
          v15,
          v11);
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
0x1800a1778  push    rbp
0x1800a177a  push    rbx
0x1800a177b  push    rsi
0x1800a177c  push    rdi
0x1800a177d  push    r12
0x1800a177f  push    r13
0x1800a1781  push    r14
0x1800a1783  push    r15
0x1800a1785  mov     rbp, rsp
0x1800a1788  sub     rsp, 78h
0x1800a178c  mov     r12, r8
0x1800a178f  mov     r14, rdx
0x1800a1792  mov     r15, rcx
0x1800a1795  lea     rdx, aCmfadtspropert_1; "CMFADTSPropertyHandler::FeedNextBufferT"...
0x1800a179c  mov     r8d, 0C2h; int
0x1800a17a2  lea     rcx, [rbp+arg_18]; this
0x1800a17a6  mov     rdi, r9
0x1800a17a9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a17ae  mov     rsi, [rdi]
0x1800a17b1  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800a17b5  xor     r13d, r13d
0x1800a17b8  mov     ecx, 4000h; cbMaxLength
0x1800a17bd  mov     [rbp+ppBuffer], r13
0x1800a17c1  mov     [rbp+var_34], r13d
0x1800a17c5  mov     [rbp+var_20], r13
0x1800a17c9  mov     [rbp+var_2C], r13d
0x1800a17cd  mov     [rbp+var_30], r13d
0x1800a17d1  mov     [rbp+var_38], r13d
0x1800a17d5  mov     [rbp+var_18], r13
0x1800a17d9  call    cs:__imp_MFCreateMemoryBuffer
0x1800a17e0  nop     dword ptr [rax+rax+00h]
0x1800a17e5  mov     ebx, eax
0x1800a17e7  test    eax, eax
0x1800a17e9  jns     loc_1800A187A
0x1800a17ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a17f6  test    rcx, rcx
0x1800a17f9  jnz     short loc_1800A1842
0x1800a17fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1802  nop     dword ptr [rax+rax+00h]
0x1800a1807  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a180e  mov     rcx, rax
0x1800a1811  test    rax, rax
0x1800a1814  jz      short loc_1800A1834
0x1800a1816  mov     rax, [rax]
0x1800a1819  mov     edx, 7F0h
0x1800a181e  mov     rax, [rax+8]
0x1800a1822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1827  test    eax, eax
0x1800a1829  jz      short loc_1800A1834
0x1800a182b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1832  jmp     short loc_1800A1842
0x1800a1834  lea     rcx, qword_1801B97E0; this
0x1800a183b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1842  cmp     [rcx+8], r13b
0x1800a1846  jz      loc_1800A1CDA
0x1800a184c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1851  cmp     [rax+7CCh], ebx
0x1800a1857  jz      loc_1800A1CDA
0x1800a185d  mov     r8d, 0D0h; int
0x1800a1863  mov     r9d, ebx; int
0x1800a1866  lea     rdx, aCmfadtspropert_1; "CMFADTSPropertyHandler::FeedNextBufferT"...
0x1800a186d  mov     rcx, rax; this
0x1800a1870  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a1875  jmp     loc_1800A1CDA
0x1800a187a  mov     rcx, [rbp+ppBuffer]
0x1800a187e  lea     r9, [rbp+var_2C]
0x1800a1882  lea     r8, [rbp+var_30]
0x1800a1886  lea     rdx, [rbp+var_20]
0x1800a188a  mov     rax, [rcx]
0x1800a188d  mov     rax, [rax+18h]
0x1800a1891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1896  mov     ebx, eax
0x1800a1898  test    eax, eax
0x1800a189a  jns     short loc_1800A1915
0x1800a189c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18a3  test    rcx, rcx
0x1800a18a6  jnz     short loc_1800A18EF
0x1800a18a8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a18af  nop     dword ptr [rax+rax+00h]
0x1800a18b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18bb  mov     rcx, rax
0x1800a18be  test    rax, rax
0x1800a18c1  jz      short loc_1800A18E1
0x1800a18c3  mov     rax, [rax]
0x1800a18c6  mov     edx, 7F0h
0x1800a18cb  mov     rax, [rax+8]
0x1800a18cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18d4  test    eax, eax
0x1800a18d6  jz      short loc_1800A18E1
0x1800a18d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18df  jmp     short loc_1800A18EF
0x1800a18e1  lea     rcx, qword_1801B97E0; this
0x1800a18e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a18ef  cmp     [rcx+8], r13b
0x1800a18f3  jz      loc_1800A1CDA
0x1800a18f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a18fe  cmp     [rax+7CCh], ebx
0x1800a1904  jz      loc_1800A1CDA
0x1800a190a  mov     r8d, 0D2h
0x1800a1910  jmp     loc_1800A1863
0x1800a1915  mov     rcx, [r15+378h]
0x1800a191c  lea     r9, [rbp+var_38]
0x1800a1920  mov     r8d, [rbp+var_30]
0x1800a1924  mov     rdx, [rbp+var_20]
0x1800a1928  mov     rax, [rcx]
0x1800a192b  mov     rax, [rax+18h]
0x1800a192f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1934  mov     rcx, [rbp+ppBuffer]
0x1800a1938  mov     ebx, eax
0x1800a193a  mov     rax, [rcx]
0x1800a193d  mov     rax, [rax+20h]
0x1800a1941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1946  test    ebx, ebx
0x1800a1948  jns     short loc_1800A19C3
0x1800a194a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1951  test    rcx, rcx
0x1800a1954  jnz     short loc_1800A199D
0x1800a1956  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a195d  nop     dword ptr [rax+rax+00h]
0x1800a1962  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1969  mov     rcx, rax
0x1800a196c  test    rax, rax
0x1800a196f  jz      short loc_1800A198F
0x1800a1971  mov     rax, [rax]
0x1800a1974  mov     edx, 7F0h
0x1800a1979  mov     rax, [rax+8]
0x1800a197d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1982  test    eax, eax
0x1800a1984  jz      short loc_1800A198F
0x1800a1986  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a198d  jmp     short loc_1800A199D
0x1800a198f  lea     rcx, qword_1801B97E0; this
0x1800a1996  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a199d  cmp     [rcx+8], r13b
0x1800a19a1  jz      loc_1800A1CDA
0x1800a19a7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a19ac  cmp     [rax+7CCh], ebx
0x1800a19b2  jz      loc_1800A1CDA
0x1800a19b8  mov     r8d, 0D8h
0x1800a19be  jmp     loc_1800A1863
0x1800a19c3  mov     edx, [rbp+var_38]
0x1800a19c6  test    edx, edx
0x1800a19c8  jnz     short loc_1800A1A48
0x1800a19ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a19d1  mov     ebx, 8000FFFFh
0x1800a19d6  test    rcx, rcx
0x1800a19d9  jnz     short loc_1800A1A22
0x1800a19db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a19e2  nop     dword ptr [rax+rax+00h]
0x1800a19e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a19ee  mov     rcx, rax
0x1800a19f1  test    rax, rax
0x1800a19f4  jz      short loc_1800A1A14
0x1800a19f6  mov     rax, [rax]
0x1800a19f9  mov     edx, 7F0h
0x1800a19fe  mov     rax, [rax+8]
0x1800a1a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a07  test    eax, eax
0x1800a1a09  jz      short loc_1800A1A14
0x1800a1a0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a12  jmp     short loc_1800A1A22
0x1800a1a14  lea     rcx, qword_1801B97E0; this
0x1800a1a1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a22  cmp     [rcx+8], r13b
0x1800a1a26  jz      loc_1800A1CDA
0x1800a1a2c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1a31  cmp     [rax+7CCh], ebx
0x1800a1a37  jz      loc_1800A1CDA
0x1800a1a3d  mov     r8d, 0E0h
0x1800a1a43  jmp     loc_1800A1863
0x1800a1a48  mov     rcx, [rbp+ppBuffer]
0x1800a1a4c  mov     rax, [rcx]
0x1800a1a4f  mov     rax, [rax+30h]
0x1800a1a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a58  mov     ebx, eax
0x1800a1a5a  test    eax, eax
0x1800a1a5c  jns     short loc_1800A1AD7
0x1800a1a5e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a65  test    rcx, rcx
0x1800a1a68  jnz     short loc_1800A1AB1
0x1800a1a6a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1a71  nop     dword ptr [rax+rax+00h]
0x1800a1a76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1a7d  mov     rcx, rax
0x1800a1a80  test    rax, rax
0x1800a1a83  jz      short loc_1800A1AA3
0x1800a1a85  mov     rax, [rax]
0x1800a1a88  mov     edx, 7F0h
0x1800a1a8d  mov     rax, [rax+8]
0x1800a1a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1a96  test    eax, eax
0x1800a1a98  jz      short loc_1800A1AA3
0x1800a1a9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1aa1  jmp     short loc_1800A1AB1
0x1800a1aa3  lea     rcx, qword_1801B97E0; this
0x1800a1aaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1ab1  cmp     [rcx+8], r13b
0x1800a1ab5  jz      loc_1800A1CDA
0x1800a1abb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1ac0  cmp     [rax+7CCh], ebx
0x1800a1ac6  jz      loc_1800A1CDA
0x1800a1acc  mov     r8d, 0E3h
0x1800a1ad2  jmp     loc_1800A1863
0x1800a1ad7  mov     rax, [r14]
0x1800a1ada  lea     rcx, [rbp+var_34]
0x1800a1ade  mov     r8, [rbp+ppBuffer]
0x1800a1ae2  mov     r9, rsi
0x1800a1ae5  mov     [rsp+78h+var_50], rcx
0x1800a1aea  mov     rdx, r12
0x1800a1aed  mov     rcx, r14
0x1800a1af0  mov     [rsp+78h+var_58], rdi
0x1800a1af5  mov     rax, [rax+18h]
0x1800a1af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1afe  mov     ebx, eax
0x1800a1b00  test    eax, eax
0x1800a1b02  jns     short loc_1800A1B7D
0x1800a1b04  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b0b  test    rcx, rcx
0x1800a1b0e  jnz     short loc_1800A1B57
0x1800a1b10  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1b17  nop     dword ptr [rax+rax+00h]
0x1800a1b1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b23  mov     rcx, rax
0x1800a1b26  test    rax, rax
0x1800a1b29  jz      short loc_1800A1B49
0x1800a1b2b  mov     rax, [rax]
0x1800a1b2e  mov     edx, 7F0h
0x1800a1b33  mov     rax, [rax+8]
0x1800a1b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b3c  test    eax, eax
0x1800a1b3e  jz      short loc_1800A1B49
0x1800a1b40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b47  jmp     short loc_1800A1B57
0x1800a1b49  lea     rcx, qword_1801B97E0; this
0x1800a1b50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1b57  cmp     [rcx+8], r13b
0x1800a1b5b  jz      loc_1800A1CDA
0x1800a1b61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1b66  cmp     [rax+7CCh], ebx
0x1800a1b6c  jz      loc_1800A1CDA
0x1800a1b72  mov     r8d, 0E5h
0x1800a1b78  jmp     loc_1800A1863
0x1800a1b7d  mov     ecx, [rbp+var_34]
0x1800a1b80  test    ecx, ecx
0x1800a1b82  jz      loc_1800A1CCF
0x1800a1b88  mov     edx, [rbp+var_38]
0x1800a1b8b  add     rdx, rsi
0x1800a1b8e  cmp     rdx, rsi
0x1800a1b91  jb      loc_1800A1C59
0x1800a1b97  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800a1b9b  mov     ebx, r13d
0x1800a1b9e  jnz     short loc_1800A1BA8
0x1800a1ba0  mov     [rdi], rdx
0x1800a1ba3  jmp     loc_1800A1C50
0x1800a1ba8  cmp     [rdi], rdx
0x1800a1bab  jz      loc_1800A1C50
0x1800a1bb1  mov     rcx, [r15+378h]
0x1800a1bb8  lea     r9, [rbp+var_18]
0x1800a1bbc  mov     rdx, [rdi]
0x1800a1bbf  xor     r8d, r8d
0x1800a1bc2  mov     rax, [rcx]
0x1800a1bc5  mov     rax, [rax+28h]
0x1800a1bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bce  mov     ebx, eax
0x1800a1bd0  test    eax, eax
0x1800a1bd2  jns     short loc_1800A1C4D
0x1800a1bd4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1bdb  test    rcx, rcx
0x1800a1bde  jnz     short loc_1800A1C27
0x1800a1be0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a1be7  nop     dword ptr [rax+rax+00h]
0x1800a1bec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1bf3  mov     rcx, rax
0x1800a1bf6  test    rax, rax
0x1800a1bf9  jz      short loc_1800A1C19
0x1800a1bfb  mov     rax, [rax]
0x1800a1bfe  mov     edx, 7F0h
0x1800a1c03  mov     rax, [rax+8]
0x1800a1c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c0c  test    eax, eax
0x1800a1c0e  jz      short loc_1800A1C19
0x1800a1c10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1c17  jmp     short loc_1800A1C27
0x1800a1c19  lea     rcx, qword_1801B97E0; this
0x1800a1c20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1c27  cmp     [rcx+8], r13b
0x1800a1c2b  jz      loc_1800A1CDA
0x1800a1c31  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a1c36  cmp     [rax+7CCh], ebx
0x1800a1c3c  jz      loc_1800A1CDA
0x1800a1c42  mov     r8d, 0F6h
0x1800a1c48  jmp     loc_1800A1863
0x1800a1c4d  mov     ecx, [rbp+var_34]
0x1800a1c50  test    ecx, ecx
0x1800a1c52  jz      short loc_1800A1CCF
0x1800a1c54  mov     ecx, r13d
0x1800a1c57  jmp     short loc_1800A1CD4
0x1800a1c59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a1c60  mov     ebx, 80070216h
0x1800a1c65  test    rcx, rcx
  ... truncated ...
```
