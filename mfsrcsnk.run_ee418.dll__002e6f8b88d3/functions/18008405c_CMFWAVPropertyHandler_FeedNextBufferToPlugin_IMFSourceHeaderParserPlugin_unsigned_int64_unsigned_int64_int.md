# CMFWAVPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x18008405c`
- end: `0x1800845ad`
- name: `?FeedNextBufferToPlugin@CMFWAVPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1361`
- prototype: `__int64 __fastcall(CMFWAVPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ab8d0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x18008405c`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800840d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800842a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084330`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800843d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008449a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008451e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800840d9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084180`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084228`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800842a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180084330`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800843d0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008449a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008451e`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800840bd`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800840bd`

## string_xrefs

- `0x180084079`: `CMFWAVPropertyHandler::FeedNextBufferToPlugin`
- `0x18008413e`: `CMFWAVPropertyHandler::FeedNextBufferToPlugin`

## pseudocode

```c
__int64 __fastcall CMFWAVPropertyHandler::FeedNextBufferToPlugin(
        CMFWAVPropertyHandler *this,
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
    "CMFWAVPropertyHandler::FeedNextBufferToPlugin",
    181);
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
                    v17 = 220;
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
                      v17 = 233;
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
                v17 = 216;
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
                v17 = 214;
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
              v17 = 211;
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
            v17 = 203;
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
          v17 = 197;
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
        v17 = 195;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFWAVPropertyHandler::FeedNextBufferToPlugin", v17, v11);
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
0x18008405c  push    rbp
0x18008405e  push    rbx
0x18008405f  push    rsi
0x180084060  push    rdi
0x180084061  push    r12
0x180084063  push    r13
0x180084065  push    r14
0x180084067  push    r15
0x180084069  mov     rbp, rsp
0x18008406c  sub     rsp, 78h
0x180084070  mov     r12, r8
0x180084073  mov     r14, rdx
0x180084076  mov     r15, rcx
0x180084079  lea     rdx, aCmfwavproperty_2; "CMFWAVPropertyHandler::FeedNextBufferTo"...
0x180084080  mov     r8d, 0B5h; int
0x180084086  lea     rcx, [rbp+arg_18]; this
0x18008408a  mov     rdi, r9
0x18008408d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180084092  mov     rsi, [rdi]
0x180084095  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180084099  xor     r13d, r13d
0x18008409c  mov     ecx, 4000h; cbMaxLength
0x1800840a1  mov     [rbp+ppBuffer], r13
0x1800840a5  mov     [rbp+var_34], r13d
0x1800840a9  mov     [rbp+var_20], r13
0x1800840ad  mov     [rbp+var_2C], r13d
0x1800840b1  mov     [rbp+var_30], r13d
0x1800840b5  mov     [rbp+var_38], r13d
0x1800840b9  mov     [rbp+var_18], r13
0x1800840bd  call    cs:__imp_MFCreateMemoryBuffer
0x1800840c3  mov     ebx, eax
0x1800840c5  test    eax, eax
0x1800840c7  jns     loc_180084152
0x1800840cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800840d4  test    rcx, rcx
0x1800840d7  jnz     short loc_18008411A
0x1800840d9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800840df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800840e6  mov     rcx, rax
0x1800840e9  test    rax, rax
0x1800840ec  jz      short loc_18008410C
0x1800840ee  mov     rax, [rax]
0x1800840f1  mov     edx, 7F0h
0x1800840f6  mov     rax, [rax+8]
0x1800840fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800840ff  test    eax, eax
0x180084101  jz      short loc_18008410C
0x180084103  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008410a  jmp     short loc_18008411A
0x18008410c  lea     rcx, qword_1801B07E0; this
0x180084113  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008411a  cmp     [rcx+8], r13b
0x18008411e  jz      loc_180084588
0x180084124  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084129  cmp     [rax+7CCh], ebx
0x18008412f  jz      loc_180084588
0x180084135  mov     r8d, 0C3h; int
0x18008413b  mov     r9d, ebx; int
0x18008413e  lea     rdx, aCmfwavproperty_2; "CMFWAVPropertyHandler::FeedNextBufferTo"...
0x180084145  mov     rcx, rax; this
0x180084148  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008414d  jmp     loc_180084588
0x180084152  mov     rcx, [rbp+ppBuffer]
0x180084156  lea     r9, [rbp+var_2C]
0x18008415a  lea     r8, [rbp+var_30]
0x18008415e  lea     rdx, [rbp+var_20]
0x180084162  mov     rax, [rcx]
0x180084165  mov     rax, [rax+18h]
0x180084169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008416e  mov     ebx, eax
0x180084170  test    eax, eax
0x180084172  jns     short loc_1800841E7
0x180084174  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008417b  test    rcx, rcx
0x18008417e  jnz     short loc_1800841C1
0x180084180  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084186  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008418d  mov     rcx, rax
0x180084190  test    rax, rax
0x180084193  jz      short loc_1800841B3
0x180084195  mov     rax, [rax]
0x180084198  mov     edx, 7F0h
0x18008419d  mov     rax, [rax+8]
0x1800841a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800841a6  test    eax, eax
0x1800841a8  jz      short loc_1800841B3
0x1800841aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800841b1  jmp     short loc_1800841C1
0x1800841b3  lea     rcx, qword_1801B07E0; this
0x1800841ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800841c1  cmp     [rcx+8], r13b
0x1800841c5  jz      loc_180084588
0x1800841cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800841d0  cmp     [rax+7CCh], ebx
0x1800841d6  jz      loc_180084588
0x1800841dc  mov     r8d, 0C5h
0x1800841e2  jmp     loc_18008413B
0x1800841e7  mov     rcx, [r15+378h]
0x1800841ee  lea     r9, [rbp+var_38]
0x1800841f2  mov     r8d, [rbp+var_30]
0x1800841f6  mov     rdx, [rbp+var_20]
0x1800841fa  mov     rax, [rcx]
0x1800841fd  mov     rax, [rax+18h]
0x180084201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084206  mov     rcx, [rbp+ppBuffer]
0x18008420a  mov     ebx, eax
0x18008420c  mov     rax, [rcx]
0x18008420f  mov     rax, [rax+20h]
0x180084213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084218  test    ebx, ebx
0x18008421a  jns     short loc_18008428F
0x18008421c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084223  test    rcx, rcx
0x180084226  jnz     short loc_180084269
0x180084228  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008422e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180084235  mov     rcx, rax
0x180084238  test    rax, rax
0x18008423b  jz      short loc_18008425B
0x18008423d  mov     rax, [rax]
0x180084240  mov     edx, 7F0h
0x180084245  mov     rax, [rax+8]
0x180084249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008424e  test    eax, eax
0x180084250  jz      short loc_18008425B
0x180084252  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084259  jmp     short loc_180084269
0x18008425b  lea     rcx, qword_1801B07E0; this
0x180084262  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084269  cmp     [rcx+8], r13b
0x18008426d  jz      loc_180084588
0x180084273  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084278  cmp     [rax+7CCh], ebx
0x18008427e  jz      loc_180084588
0x180084284  mov     r8d, 0CBh
0x18008428a  jmp     loc_18008413B
0x18008428f  mov     edx, [rbp+var_38]
0x180084292  test    edx, edx
0x180084294  jnz     short loc_18008430E
0x180084296  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008429d  mov     ebx, 8000FFFFh
0x1800842a2  test    rcx, rcx
0x1800842a5  jnz     short loc_1800842E8
0x1800842a7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800842ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800842b4  mov     rcx, rax
0x1800842b7  test    rax, rax
0x1800842ba  jz      short loc_1800842DA
0x1800842bc  mov     rax, [rax]
0x1800842bf  mov     edx, 7F0h
0x1800842c4  mov     rax, [rax+8]
0x1800842c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800842cd  test    eax, eax
0x1800842cf  jz      short loc_1800842DA
0x1800842d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800842d8  jmp     short loc_1800842E8
0x1800842da  lea     rcx, qword_1801B07E0; this
0x1800842e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800842e8  cmp     [rcx+8], r13b
0x1800842ec  jz      loc_180084588
0x1800842f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800842f7  cmp     [rax+7CCh], ebx
0x1800842fd  jz      loc_180084588
0x180084303  mov     r8d, 0D3h
0x180084309  jmp     loc_18008413B
0x18008430e  mov     rcx, [rbp+ppBuffer]
0x180084312  mov     rax, [rcx]
0x180084315  mov     rax, [rax+30h]
0x180084319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008431e  mov     ebx, eax
0x180084320  test    eax, eax
0x180084322  jns     short loc_180084397
0x180084324  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008432b  test    rcx, rcx
0x18008432e  jnz     short loc_180084371
0x180084330  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084336  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008433d  mov     rcx, rax
0x180084340  test    rax, rax
0x180084343  jz      short loc_180084363
0x180084345  mov     rax, [rax]
0x180084348  mov     edx, 7F0h
0x18008434d  mov     rax, [rax+8]
0x180084351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084356  test    eax, eax
0x180084358  jz      short loc_180084363
0x18008435a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084361  jmp     short loc_180084371
0x180084363  lea     rcx, qword_1801B07E0; this
0x18008436a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084371  cmp     [rcx+8], r13b
0x180084375  jz      loc_180084588
0x18008437b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084380  cmp     [rax+7CCh], ebx
0x180084386  jz      loc_180084588
0x18008438c  mov     r8d, 0D6h
0x180084392  jmp     loc_18008413B
0x180084397  mov     rax, [r14]
0x18008439a  lea     rcx, [rbp+var_34]
0x18008439e  mov     r8, [rbp+ppBuffer]
0x1800843a2  mov     r9, rsi
0x1800843a5  mov     [rsp+78h+var_50], rcx
0x1800843aa  mov     rdx, r12
0x1800843ad  mov     rcx, r14
0x1800843b0  mov     [rsp+78h+var_58], rdi
0x1800843b5  mov     rax, [rax+18h]
0x1800843b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800843be  mov     ebx, eax
0x1800843c0  test    eax, eax
0x1800843c2  jns     short loc_180084437
0x1800843c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800843cb  test    rcx, rcx
0x1800843ce  jnz     short loc_180084411
0x1800843d0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800843d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800843dd  mov     rcx, rax
0x1800843e0  test    rax, rax
0x1800843e3  jz      short loc_180084403
0x1800843e5  mov     rax, [rax]
0x1800843e8  mov     edx, 7F0h
0x1800843ed  mov     rax, [rax+8]
0x1800843f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800843f6  test    eax, eax
0x1800843f8  jz      short loc_180084403
0x1800843fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084401  jmp     short loc_180084411
0x180084403  lea     rcx, qword_1801B07E0; this
0x18008440a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180084411  cmp     [rcx+8], r13b
0x180084415  jz      loc_180084588
0x18008441b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180084420  cmp     [rax+7CCh], ebx
0x180084426  jz      loc_180084588
0x18008442c  mov     r8d, 0D8h
0x180084432  jmp     loc_18008413B
0x180084437  mov     ecx, [rbp+var_34]
0x18008443a  test    ecx, ecx
0x18008443c  jz      loc_18008457D
0x180084442  mov     edx, [rbp+var_38]
0x180084445  add     rdx, rsi
0x180084448  cmp     rdx, rsi
0x18008444b  jb      loc_18008450D
0x180084451  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180084455  mov     ebx, r13d
0x180084458  jnz     short loc_180084462
0x18008445a  mov     [rdi], rdx
0x18008445d  jmp     loc_180084504
0x180084462  cmp     [rdi], rdx
0x180084465  jz      loc_180084504
0x18008446b  mov     rcx, [r15+378h]
0x180084472  lea     r9, [rbp+var_18]
0x180084476  mov     rdx, [rdi]
0x180084479  xor     r8d, r8d
0x18008447c  mov     rax, [rcx]
0x18008447f  mov     rax, [rax+28h]
0x180084483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084488  mov     ebx, eax
0x18008448a  test    eax, eax
0x18008448c  jns     short loc_180084501
0x18008448e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084495  test    rcx, rcx
0x180084498  jnz     short loc_1800844DB
0x18008449a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800844a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800844a7  mov     rcx, rax
0x1800844aa  test    rax, rax
0x1800844ad  jz      short loc_1800844CD
0x1800844af  mov     rax, [rax]
0x1800844b2  mov     edx, 7F0h
0x1800844b7  mov     rax, [rax+8]
0x1800844bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844c0  test    eax, eax
0x1800844c2  jz      short loc_1800844CD
0x1800844c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800844cb  jmp     short loc_1800844DB
0x1800844cd  lea     rcx, qword_1801B07E0; this
0x1800844d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800844db  cmp     [rcx+8], r13b
0x1800844df  jz      loc_180084588
0x1800844e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800844ea  cmp     [rax+7CCh], ebx
0x1800844f0  jz      loc_180084588
0x1800844f6  mov     r8d, 0E9h
0x1800844fc  jmp     loc_18008413B
0x180084501  mov     ecx, [rbp+var_34]
0x180084504  test    ecx, ecx
0x180084506  jz      short loc_18008457D
0x180084508  mov     ecx, r13d
0x18008450b  jmp     short loc_180084582
0x18008450d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180084514  mov     ebx, 80070216h
0x180084519  test    rcx, rcx
0x18008451c  jnz     short loc_18008455F
0x18008451e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180084524  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008452b  mov     rcx, rax
0x18008452e  test    rax, rax
0x180084531  jz      short loc_180084551
0x180084533  mov     rax, [rax]
0x180084536  mov     edx, 7F0h
  ... truncated ...
```
