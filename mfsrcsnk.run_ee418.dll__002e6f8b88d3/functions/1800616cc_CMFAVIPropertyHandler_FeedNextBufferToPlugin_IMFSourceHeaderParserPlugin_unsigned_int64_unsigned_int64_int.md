# CMFAVIPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x1800616cc`
- end: `0x180061bf0`
- name: `?FeedNextBufferToPlugin@CMFAVIPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1316`
- prototype: `__int64 __fastcall(CMFAVIPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800ebfd8`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x1800616cc`
- `0x180071a44`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800617b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006185f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061967`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061ad1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061b55`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800617b7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006185f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800618de`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061967`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061a07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061ad1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180061b55`
- `MFPlat!MFCreateMemoryBuffer` at `0x18006172d`
- `MFPlat!MFCreateMemoryBuffer` at `0x18006172d`

## string_xrefs

- `0x1800616e9`: `CMFAVIPropertyHandler::FeedNextBufferToPlugin`
- `0x180061775`: `CMFAVIPropertyHandler::FeedNextBufferToPlugin`

## pseudocode

```c
__int64 __fastcall CMFAVIPropertyHandler::FeedNextBufferToPlugin(
        CMFAVIPropertyHandler *this,
        struct IMFSourceHeaderParserPlugin *a2,
        __int64 a3,
        unsigned __int64 *a4,
        int *a5)
{
  unsigned __int64 v9; // rsi
  HRESULT v10; // ebx
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  int v36; // ecx
  unsigned __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  wchar_t *v41; // rcx
  CallStackTracing *v42; // rax
  int v43; // ecx
  wchar_t *v44; // rcx
  CallStackTracing *v45; // rax
  unsigned int v47; // [rsp+40h] [rbp-38h] BYREF
  int v48; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-30h] BYREF
  int v50; // [rsp+4Ch] [rbp-2Ch] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+50h] [rbp-28h] BYREF
  __int64 v52; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v53[3]; // [rsp+60h] [rbp-18h] BYREF
  char v54; // [rsp+D8h] [rbp+60h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v54,
    "CMFAVIPropertyHandler::FeedNextBufferToPlugin",
    248);
  v9 = *a4;
  ppBuffer = 0;
  v48 = 0;
  v52 = 0;
  v50 = 0;
  v49 = 0;
  v47 = 0;
  v53[0] = 0;
  v10 = MFCreateMemoryBuffer(0x4000u, &ppBuffer);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, unsigned int *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v52,
            &v49,
            &v50);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**((_QWORD **)this + 111) + 24LL))(
              *((_QWORD *)this + 111),
              v52,
              v49,
              &v47);
      ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
      if ( v10 >= 0 )
      {
        if ( v47 )
        {
          v10 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(struct IMFSourceHeaderParserPlugin *, __int64, IMFMediaBuffer *, unsigned __int64, unsigned __int64 *, int *))(*(_QWORD *)a2 + 24LL))(
                    a2,
                    a3,
                    ppBuffer,
                    v9,
                    a4,
                    &v48);
            if ( v10 >= 0 )
            {
              v36 = v48;
              if ( !v48 )
                goto LABEL_78;
              v37 = v9 + v47;
              if ( v37 < v9 )
              {
                v44 = (wchar_t *)CallStackTracing::s_wpInstance;
                v10 = -2147024362;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v37, v32, v33);
                  CallStackTracing::s_wpInstance = v45;
                  if ( v45
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
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
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024362 )
                  {
                    v13 = 287;
                    goto LABEL_7;
                  }
                }
                goto LABEL_80;
              }
              v10 = 0;
              if ( *a4 == -1 )
              {
                *a4 = v37;
              }
              else if ( *a4 != v37 )
              {
                v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 111) + 40LL))(
                        *((_QWORD *)this + 111),
                        *a4,
                        0,
                        v53);
                if ( v10 < 0 )
                {
                  v41 = (wchar_t *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39, v40);
                    CallStackTracing::s_wpInstance = v42;
                    if ( v42
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
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
                    if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
                    {
                      v13 = 300;
                      goto LABEL_7;
                    }
                  }
                  goto LABEL_80;
                }
                v36 = v48;
              }
              if ( v36 )
                v43 = 0;
              else
LABEL_78:
                v43 = 1;
              *a5 = v43;
              goto LABEL_80;
            }
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32, v33);
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
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              {
                v13 = 283;
                goto LABEL_7;
              }
            }
          }
          else
          {
            v29 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
              CallStackTracing::s_wpInstance = v30;
              if ( v30
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
              {
                v29 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v29 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
              }
            }
            if ( *((_BYTE *)v29 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              {
                v13 = 281;
                goto LABEL_7;
              }
            }
          }
        }
        else
        {
          v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          v10 = -2147418113;
          if ( !CallStackTracing::s_wpInstance )
          {
            v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v47, v20, v21);
            CallStackTracing::s_wpInstance = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v24 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
            {
              v13 = 278;
              goto LABEL_7;
            }
          }
        }
      }
      else
      {
        v22 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
          {
            v13 = 270;
            goto LABEL_7;
          }
        }
      }
    }
    else
    {
      v17 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
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
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
        {
          v13 = 264;
          goto LABEL_7;
        }
      }
    }
  }
  else
  {
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
      {
        v13 = 262;
LABEL_7:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFAVIPropertyHandler::FeedNextBufferToPlugin", v13, v10);
      }
    }
  }
LABEL_80:
  if ( ppBuffer )
    ((void (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Release)(ppBuffer);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v54);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800616cc  push    rbp
0x1800616ce  push    rbx
0x1800616cf  push    rsi
0x1800616d0  push    rdi
0x1800616d1  push    r12
0x1800616d3  push    r13
0x1800616d5  push    r14
0x1800616d7  push    r15
0x1800616d9  mov     rbp, rsp
0x1800616dc  sub     rsp, 78h
0x1800616e0  mov     r12, r8
0x1800616e3  mov     r14, rdx
0x1800616e6  mov     r15, rcx
0x1800616e9  lea     rdx, aCmfaviproperty_1; "CMFAVIPropertyHandler::FeedNextBufferTo"...
0x1800616f0  mov     r8d, 0F8h; int
0x1800616f6  lea     rcx, [rbp+arg_18]; this
0x1800616fa  mov     rdi, r9
0x1800616fd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180061702  mov     rsi, [rdi]
0x180061705  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180061709  xor     r13d, r13d
0x18006170c  mov     ecx, 4000h; cbMaxLength
0x180061711  mov     [rbp+ppBuffer], r13
0x180061715  mov     [rbp+var_34], r13d
0x180061719  mov     [rbp+var_20], r13
0x18006171d  mov     [rbp+var_2C], r13d
0x180061721  mov     [rbp+var_30], r13d
0x180061725  mov     [rbp+var_38], r13d
0x180061729  mov     [rbp+var_18], r13
0x18006172d  call    cs:__imp_MFCreateMemoryBuffer
0x180061733  mov     ebx, eax
0x180061735  test    eax, eax
0x180061737  jns     short loc_180061789
0x180061739  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061740  test    rcx, rcx
0x180061743  jnz     short loc_180061751
0x180061745  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18006174a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180061751  cmp     [rcx+8], r13b
0x180061755  jz      loc_180061BBF
0x18006175b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061760  cmp     [rax+7CCh], ebx
0x180061766  jz      loc_180061BBF
0x18006176c  mov     r8d, 106h; int
0x180061772  mov     r9d, ebx; int
0x180061775  lea     rdx, aCmfaviproperty_1; "CMFAVIPropertyHandler::FeedNextBufferTo"...
0x18006177c  mov     rcx, rax; this
0x18006177f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180061784  jmp     loc_180061BBF
0x180061789  mov     rcx, [rbp+ppBuffer]
0x18006178d  lea     r9, [rbp+var_2C]
0x180061791  lea     r8, [rbp+var_30]
0x180061795  lea     rdx, [rbp+var_20]
0x180061799  mov     rax, [rcx]
0x18006179c  mov     rax, [rax+18h]
0x1800617a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617a5  mov     ebx, eax
0x1800617a7  test    eax, eax
0x1800617a9  jns     short loc_18006181E
0x1800617ab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617b2  test    rcx, rcx
0x1800617b5  jnz     short loc_1800617F8
0x1800617b7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800617bd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617c4  mov     rcx, rax
0x1800617c7  test    rax, rax
0x1800617ca  jz      short loc_1800617EA
0x1800617cc  mov     rax, [rax]
0x1800617cf  mov     edx, 7F0h
0x1800617d4  mov     rax, [rax+8]
0x1800617d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617dd  test    eax, eax
0x1800617df  jz      short loc_1800617EA
0x1800617e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617e8  jmp     short loc_1800617F8
0x1800617ea  lea     rcx, qword_1801B07E0; this
0x1800617f1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800617f8  cmp     [rcx+8], r13b
0x1800617fc  jz      loc_180061BBF
0x180061802  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061807  cmp     [rax+7CCh], ebx
0x18006180d  jz      loc_180061BBF
0x180061813  mov     r8d, 108h
0x180061819  jmp     loc_180061772
0x18006181e  mov     rcx, [r15+378h]
0x180061825  lea     r9, [rbp+var_38]
0x180061829  mov     r8d, [rbp+var_30]
0x18006182d  mov     rdx, [rbp+var_20]
0x180061831  mov     rax, [rcx]
0x180061834  mov     rax, [rax+18h]
0x180061838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006183d  mov     rcx, [rbp+ppBuffer]
0x180061841  mov     ebx, eax
0x180061843  mov     rax, [rcx]
0x180061846  mov     rax, [rax+20h]
0x18006184a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006184f  test    ebx, ebx
0x180061851  jns     short loc_1800618C6
0x180061853  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006185a  test    rcx, rcx
0x18006185d  jnz     short loc_1800618A0
0x18006185f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061865  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006186c  mov     rcx, rax
0x18006186f  test    rax, rax
0x180061872  jz      short loc_180061892
0x180061874  mov     rax, [rax]
0x180061877  mov     edx, 7F0h
0x18006187c  mov     rax, [rax+8]
0x180061880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061885  test    eax, eax
0x180061887  jz      short loc_180061892
0x180061889  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061890  jmp     short loc_1800618A0
0x180061892  lea     rcx, qword_1801B07E0; this
0x180061899  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618a0  cmp     [rcx+8], r13b
0x1800618a4  jz      loc_180061BBF
0x1800618aa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800618af  cmp     [rax+7CCh], ebx
0x1800618b5  jz      loc_180061BBF
0x1800618bb  mov     r8d, 10Eh
0x1800618c1  jmp     loc_180061772
0x1800618c6  mov     edx, [rbp+var_38]
0x1800618c9  test    edx, edx
0x1800618cb  jnz     short loc_180061945
0x1800618cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618d4  mov     ebx, 8000FFFFh
0x1800618d9  test    rcx, rcx
0x1800618dc  jnz     short loc_18006191F
0x1800618de  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800618e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800618eb  mov     rcx, rax
0x1800618ee  test    rax, rax
0x1800618f1  jz      short loc_180061911
0x1800618f3  mov     rax, [rax]
0x1800618f6  mov     edx, 7F0h
0x1800618fb  mov     rax, [rax+8]
0x1800618ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061904  test    eax, eax
0x180061906  jz      short loc_180061911
0x180061908  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006190f  jmp     short loc_18006191F
0x180061911  lea     rcx, qword_1801B07E0; this
0x180061918  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006191f  cmp     [rcx+8], r13b
0x180061923  jz      loc_180061BBF
0x180061929  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006192e  cmp     [rax+7CCh], ebx
0x180061934  jz      loc_180061BBF
0x18006193a  mov     r8d, 116h
0x180061940  jmp     loc_180061772
0x180061945  mov     rcx, [rbp+ppBuffer]
0x180061949  mov     rax, [rcx]
0x18006194c  mov     rax, [rax+30h]
0x180061950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061955  mov     ebx, eax
0x180061957  test    eax, eax
0x180061959  jns     short loc_1800619CE
0x18006195b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061962  test    rcx, rcx
0x180061965  jnz     short loc_1800619A8
0x180061967  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18006196d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061974  mov     rcx, rax
0x180061977  test    rax, rax
0x18006197a  jz      short loc_18006199A
0x18006197c  mov     rax, [rax]
0x18006197f  mov     edx, 7F0h
0x180061984  mov     rax, [rax+8]
0x180061988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006198d  test    eax, eax
0x18006198f  jz      short loc_18006199A
0x180061991  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061998  jmp     short loc_1800619A8
0x18006199a  lea     rcx, qword_1801B07E0; this
0x1800619a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800619a8  cmp     [rcx+8], r13b
0x1800619ac  jz      loc_180061BBF
0x1800619b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800619b7  cmp     [rax+7CCh], ebx
0x1800619bd  jz      loc_180061BBF
0x1800619c3  mov     r8d, 119h
0x1800619c9  jmp     loc_180061772
0x1800619ce  mov     rax, [r14]
0x1800619d1  lea     rcx, [rbp+var_34]
0x1800619d5  mov     r8, [rbp+ppBuffer]
0x1800619d9  mov     r9, rsi
0x1800619dc  mov     [rsp+78h+var_50], rcx
0x1800619e1  mov     rdx, r12
0x1800619e4  mov     rcx, r14
0x1800619e7  mov     [rsp+78h+var_58], rdi
0x1800619ec  mov     rax, [rax+18h]
0x1800619f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800619f5  mov     ebx, eax
0x1800619f7  test    eax, eax
0x1800619f9  jns     short loc_180061A6E
0x1800619fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a02  test    rcx, rcx
0x180061a05  jnz     short loc_180061A48
0x180061a07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061a0d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a14  mov     rcx, rax
0x180061a17  test    rax, rax
0x180061a1a  jz      short loc_180061A3A
0x180061a1c  mov     rax, [rax]
0x180061a1f  mov     edx, 7F0h
0x180061a24  mov     rax, [rax+8]
0x180061a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a2d  test    eax, eax
0x180061a2f  jz      short loc_180061A3A
0x180061a31  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a38  jmp     short loc_180061A48
0x180061a3a  lea     rcx, qword_1801B07E0; this
0x180061a41  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061a48  cmp     [rcx+8], r13b
0x180061a4c  jz      loc_180061BBF
0x180061a52  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061a57  cmp     [rax+7CCh], ebx
0x180061a5d  jz      loc_180061BBF
0x180061a63  mov     r8d, 11Bh
0x180061a69  jmp     loc_180061772
0x180061a6e  mov     ecx, [rbp+var_34]
0x180061a71  test    ecx, ecx
0x180061a73  jz      loc_180061BB4
0x180061a79  mov     edx, [rbp+var_38]
0x180061a7c  add     rdx, rsi
0x180061a7f  cmp     rdx, rsi
0x180061a82  jb      loc_180061B44
0x180061a88  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180061a8c  mov     ebx, r13d
0x180061a8f  jnz     short loc_180061A99
0x180061a91  mov     [rdi], rdx
0x180061a94  jmp     loc_180061B3B
0x180061a99  cmp     [rdi], rdx
0x180061a9c  jz      loc_180061B3B
0x180061aa2  mov     rcx, [r15+378h]
0x180061aa9  lea     r9, [rbp+var_18]
0x180061aad  mov     rdx, [rdi]
0x180061ab0  xor     r8d, r8d
0x180061ab3  mov     rax, [rcx]
0x180061ab6  mov     rax, [rax+28h]
0x180061aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061abf  mov     ebx, eax
0x180061ac1  test    eax, eax
0x180061ac3  jns     short loc_180061B38
0x180061ac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061acc  test    rcx, rcx
0x180061acf  jnz     short loc_180061B12
0x180061ad1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061ad7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061ade  mov     rcx, rax
0x180061ae1  test    rax, rax
0x180061ae4  jz      short loc_180061B04
0x180061ae6  mov     rax, [rax]
0x180061ae9  mov     edx, 7F0h
0x180061aee  mov     rax, [rax+8]
0x180061af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061af7  test    eax, eax
0x180061af9  jz      short loc_180061B04
0x180061afb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b02  jmp     short loc_180061B12
0x180061b04  lea     rcx, qword_1801B07E0; this
0x180061b0b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b12  cmp     [rcx+8], r13b
0x180061b16  jz      loc_180061BBF
0x180061b1c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061b21  cmp     [rax+7CCh], ebx
0x180061b27  jz      loc_180061BBF
0x180061b2d  mov     r8d, 12Ch
0x180061b33  jmp     loc_180061772
0x180061b38  mov     ecx, [rbp+var_34]
0x180061b3b  test    ecx, ecx
0x180061b3d  jz      short loc_180061BB4
0x180061b3f  mov     ecx, r13d
0x180061b42  jmp     short loc_180061BB9
0x180061b44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b4b  mov     ebx, 80070216h
0x180061b50  test    rcx, rcx
0x180061b53  jnz     short loc_180061B96
0x180061b55  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180061b5b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b62  mov     rcx, rax
0x180061b65  test    rax, rax
0x180061b68  jz      short loc_180061B88
0x180061b6a  mov     rax, [rax]
0x180061b6d  mov     edx, 7F0h
0x180061b72  mov     rax, [rax+8]
0x180061b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b7b  test    eax, eax
0x180061b7d  jz      short loc_180061B88
0x180061b7f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b86  jmp     short loc_180061B96
0x180061b88  lea     rcx, qword_1801B07E0; this
0x180061b8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180061b96  cmp     [rcx+8], r13b
0x180061b9a  jz      short loc_180061BBF
0x180061b9c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180061ba1  cmp     [rax+7CCh], ebx
0x180061ba7  jz      short loc_180061BBF
  ... truncated ...
```
