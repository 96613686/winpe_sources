# CMFWAVPropertyHandler::FeedNextBufferToPlugin(IMFSourceHeaderParserPlugin *,unsigned __int64,unsigned __int64 *,int *)

- ea: `0x180088bd8`
- end: `0x180089160`
- name: `?FeedNextBufferToPlugin@CMFWAVPropertyHandler@@AEAAJPEAUIMFSourceHeaderParserPlugin@@_KPEA_KPEAH@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CMFWAVPropertyHandler *__hidden this, struct IMFSourceHeaderParserPlugin *, unsigned __int64, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b0bec`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180088bd8`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088db6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088eca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088f70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089040`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800890ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088c5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088d08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088db6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088e3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088eca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180088f70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180089040`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800890ca`
- `MFPlat!MFCreateMemoryBuffer` at `0x180088c39`
- `MFPlat!MFCreateMemoryBuffer` at `0x180088c39`

## string_xrefs

- `0x180088bf5`: `CMFWAVPropertyHandler::FeedNextBufferToPlugin`
- `0x180088cc6`: `CMFWAVPropertyHandler::FeedNextBufferToPlugin`

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
    "CMFWAVPropertyHandler::FeedNextBufferToPlugin",
    181);
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
                    v15 = 220;
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
                      v15 = 233;
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
                v15 = 216;
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
                v15 = 214;
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
              v15 = 211;
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
            v15 = 203;
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
          v15 = 197;
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
        v15 = 195;
LABEL_10:
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFWAVPropertyHandler::FeedNextBufferToPlugin", v15, v11);
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
0x180088bd8  push    rbp
0x180088bda  push    rbx
0x180088bdb  push    rsi
0x180088bdc  push    rdi
0x180088bdd  push    r12
0x180088bdf  push    r13
0x180088be1  push    r14
0x180088be3  push    r15
0x180088be5  mov     rbp, rsp
0x180088be8  sub     rsp, 78h
0x180088bec  mov     r12, r8
0x180088bef  mov     r14, rdx
0x180088bf2  mov     r15, rcx
0x180088bf5  lea     rdx, aCmfwavproperty_2; "CMFWAVPropertyHandler::FeedNextBufferTo"...
0x180088bfc  mov     r8d, 0B5h; int
0x180088c02  lea     rcx, [rbp+arg_18]; this
0x180088c06  mov     rdi, r9
0x180088c09  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180088c0e  mov     rsi, [rdi]
0x180088c11  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x180088c15  xor     r13d, r13d
0x180088c18  mov     ecx, 4000h; cbMaxLength
0x180088c1d  mov     [rbp+ppBuffer], r13
0x180088c21  mov     [rbp+var_34], r13d
0x180088c25  mov     [rbp+var_20], r13
0x180088c29  mov     [rbp+var_2C], r13d
0x180088c2d  mov     [rbp+var_30], r13d
0x180088c31  mov     [rbp+var_38], r13d
0x180088c35  mov     [rbp+var_18], r13
0x180088c39  call    cs:__imp_MFCreateMemoryBuffer
0x180088c40  nop     dword ptr [rax+rax+00h]
0x180088c45  mov     ebx, eax
0x180088c47  test    eax, eax
0x180088c49  jns     loc_180088CDA
0x180088c4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088c56  test    rcx, rcx
0x180088c59  jnz     short loc_180088CA2
0x180088c5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088c62  nop     dword ptr [rax+rax+00h]
0x180088c67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088c6e  mov     rcx, rax
0x180088c71  test    rax, rax
0x180088c74  jz      short loc_180088C94
0x180088c76  mov     rax, [rax]
0x180088c79  mov     edx, 7F0h
0x180088c7e  mov     rax, [rax+8]
0x180088c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088c87  test    eax, eax
0x180088c89  jz      short loc_180088C94
0x180088c8b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088c92  jmp     short loc_180088CA2
0x180088c94  lea     rcx, qword_1801B97E0; this
0x180088c9b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088ca2  cmp     [rcx+8], r13b
0x180088ca6  jz      loc_18008913A
0x180088cac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088cb1  cmp     [rax+7CCh], ebx
0x180088cb7  jz      loc_18008913A
0x180088cbd  mov     r8d, 0C3h; int
0x180088cc3  mov     r9d, ebx; int
0x180088cc6  lea     rdx, aCmfwavproperty_2; "CMFWAVPropertyHandler::FeedNextBufferTo"...
0x180088ccd  mov     rcx, rax; this
0x180088cd0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180088cd5  jmp     loc_18008913A
0x180088cda  mov     rcx, [rbp+ppBuffer]
0x180088cde  lea     r9, [rbp+var_2C]
0x180088ce2  lea     r8, [rbp+var_30]
0x180088ce6  lea     rdx, [rbp+var_20]
0x180088cea  mov     rax, [rcx]
0x180088ced  mov     rax, [rax+18h]
0x180088cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088cf6  mov     ebx, eax
0x180088cf8  test    eax, eax
0x180088cfa  jns     short loc_180088D75
0x180088cfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d03  test    rcx, rcx
0x180088d06  jnz     short loc_180088D4F
0x180088d08  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088d0f  nop     dword ptr [rax+rax+00h]
0x180088d14  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d1b  mov     rcx, rax
0x180088d1e  test    rax, rax
0x180088d21  jz      short loc_180088D41
0x180088d23  mov     rax, [rax]
0x180088d26  mov     edx, 7F0h
0x180088d2b  mov     rax, [rax+8]
0x180088d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d34  test    eax, eax
0x180088d36  jz      short loc_180088D41
0x180088d38  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d3f  jmp     short loc_180088D4F
0x180088d41  lea     rcx, qword_1801B97E0; this
0x180088d48  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088d4f  cmp     [rcx+8], r13b
0x180088d53  jz      loc_18008913A
0x180088d59  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088d5e  cmp     [rax+7CCh], ebx
0x180088d64  jz      loc_18008913A
0x180088d6a  mov     r8d, 0C5h
0x180088d70  jmp     loc_180088CC3
0x180088d75  mov     rcx, [r15+378h]
0x180088d7c  lea     r9, [rbp+var_38]
0x180088d80  mov     r8d, [rbp+var_30]
0x180088d84  mov     rdx, [rbp+var_20]
0x180088d88  mov     rax, [rcx]
0x180088d8b  mov     rax, [rax+18h]
0x180088d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088d94  mov     rcx, [rbp+ppBuffer]
0x180088d98  mov     ebx, eax
0x180088d9a  mov     rax, [rcx]
0x180088d9d  mov     rax, [rax+20h]
0x180088da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088da6  test    ebx, ebx
0x180088da8  jns     short loc_180088E23
0x180088daa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088db1  test    rcx, rcx
0x180088db4  jnz     short loc_180088DFD
0x180088db6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088dbd  nop     dword ptr [rax+rax+00h]
0x180088dc2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088dc9  mov     rcx, rax
0x180088dcc  test    rax, rax
0x180088dcf  jz      short loc_180088DEF
0x180088dd1  mov     rax, [rax]
0x180088dd4  mov     edx, 7F0h
0x180088dd9  mov     rax, [rax+8]
0x180088ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088de2  test    eax, eax
0x180088de4  jz      short loc_180088DEF
0x180088de6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088ded  jmp     short loc_180088DFD
0x180088def  lea     rcx, qword_1801B97E0; this
0x180088df6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088dfd  cmp     [rcx+8], r13b
0x180088e01  jz      loc_18008913A
0x180088e07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088e0c  cmp     [rax+7CCh], ebx
0x180088e12  jz      loc_18008913A
0x180088e18  mov     r8d, 0CBh
0x180088e1e  jmp     loc_180088CC3
0x180088e23  mov     edx, [rbp+var_38]
0x180088e26  test    edx, edx
0x180088e28  jnz     short loc_180088EA8
0x180088e2a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e31  mov     ebx, 8000FFFFh
0x180088e36  test    rcx, rcx
0x180088e39  jnz     short loc_180088E82
0x180088e3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088e42  nop     dword ptr [rax+rax+00h]
0x180088e47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e4e  mov     rcx, rax
0x180088e51  test    rax, rax
0x180088e54  jz      short loc_180088E74
0x180088e56  mov     rax, [rax]
0x180088e59  mov     edx, 7F0h
0x180088e5e  mov     rax, [rax+8]
0x180088e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e67  test    eax, eax
0x180088e69  jz      short loc_180088E74
0x180088e6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e72  jmp     short loc_180088E82
0x180088e74  lea     rcx, qword_1801B97E0; this
0x180088e7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088e82  cmp     [rcx+8], r13b
0x180088e86  jz      loc_18008913A
0x180088e8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088e91  cmp     [rax+7CCh], ebx
0x180088e97  jz      loc_18008913A
0x180088e9d  mov     r8d, 0D3h
0x180088ea3  jmp     loc_180088CC3
0x180088ea8  mov     rcx, [rbp+ppBuffer]
0x180088eac  mov     rax, [rcx]
0x180088eaf  mov     rax, [rax+30h]
0x180088eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088eb8  mov     ebx, eax
0x180088eba  test    eax, eax
0x180088ebc  jns     short loc_180088F37
0x180088ebe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088ec5  test    rcx, rcx
0x180088ec8  jnz     short loc_180088F11
0x180088eca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088ed1  nop     dword ptr [rax+rax+00h]
0x180088ed6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088edd  mov     rcx, rax
0x180088ee0  test    rax, rax
0x180088ee3  jz      short loc_180088F03
0x180088ee5  mov     rax, [rax]
0x180088ee8  mov     edx, 7F0h
0x180088eed  mov     rax, [rax+8]
0x180088ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ef6  test    eax, eax
0x180088ef8  jz      short loc_180088F03
0x180088efa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f01  jmp     short loc_180088F11
0x180088f03  lea     rcx, qword_1801B97E0; this
0x180088f0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f11  cmp     [rcx+8], r13b
0x180088f15  jz      loc_18008913A
0x180088f1b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088f20  cmp     [rax+7CCh], ebx
0x180088f26  jz      loc_18008913A
0x180088f2c  mov     r8d, 0D6h
0x180088f32  jmp     loc_180088CC3
0x180088f37  mov     rax, [r14]
0x180088f3a  lea     rcx, [rbp+var_34]
0x180088f3e  mov     r8, [rbp+ppBuffer]
0x180088f42  mov     r9, rsi
0x180088f45  mov     [rsp+78h+var_50], rcx
0x180088f4a  mov     rdx, r12
0x180088f4d  mov     rcx, r14
0x180088f50  mov     [rsp+78h+var_58], rdi
0x180088f55  mov     rax, [rax+18h]
0x180088f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f5e  mov     ebx, eax
0x180088f60  test    eax, eax
0x180088f62  jns     short loc_180088FDD
0x180088f64  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f6b  test    rcx, rcx
0x180088f6e  jnz     short loc_180088FB7
0x180088f70  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180088f77  nop     dword ptr [rax+rax+00h]
0x180088f7c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180088f83  mov     rcx, rax
0x180088f86  test    rax, rax
0x180088f89  jz      short loc_180088FA9
0x180088f8b  mov     rax, [rax]
0x180088f8e  mov     edx, 7F0h
0x180088f93  mov     rax, [rax+8]
0x180088f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088f9c  test    eax, eax
0x180088f9e  jz      short loc_180088FA9
0x180088fa0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fa7  jmp     short loc_180088FB7
0x180088fa9  lea     rcx, qword_1801B97E0; this
0x180088fb0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180088fb7  cmp     [rcx+8], r13b
0x180088fbb  jz      loc_18008913A
0x180088fc1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180088fc6  cmp     [rax+7CCh], ebx
0x180088fcc  jz      loc_18008913A
0x180088fd2  mov     r8d, 0D8h
0x180088fd8  jmp     loc_180088CC3
0x180088fdd  mov     ecx, [rbp+var_34]
0x180088fe0  test    ecx, ecx
0x180088fe2  jz      loc_18008912F
0x180088fe8  mov     edx, [rbp+var_38]
0x180088feb  add     rdx, rsi
0x180088fee  cmp     rdx, rsi
0x180088ff1  jb      loc_1800890B9
0x180088ff7  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180088ffb  mov     ebx, r13d
0x180088ffe  jnz     short loc_180089008
0x180089000  mov     [rdi], rdx
0x180089003  jmp     loc_1800890B0
0x180089008  cmp     [rdi], rdx
0x18008900b  jz      loc_1800890B0
0x180089011  mov     rcx, [r15+378h]
0x180089018  lea     r9, [rbp+var_18]
0x18008901c  mov     rdx, [rdi]
0x18008901f  xor     r8d, r8d
0x180089022  mov     rax, [rcx]
0x180089025  mov     rax, [rax+28h]
0x180089029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008902e  mov     ebx, eax
0x180089030  test    eax, eax
0x180089032  jns     short loc_1800890AD
0x180089034  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008903b  test    rcx, rcx
0x18008903e  jnz     short loc_180089087
0x180089040  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180089047  nop     dword ptr [rax+rax+00h]
0x18008904c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180089053  mov     rcx, rax
0x180089056  test    rax, rax
0x180089059  jz      short loc_180089079
0x18008905b  mov     rax, [rax]
0x18008905e  mov     edx, 7F0h
0x180089063  mov     rax, [rax+8]
0x180089067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008906c  test    eax, eax
0x18008906e  jz      short loc_180089079
0x180089070  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180089077  jmp     short loc_180089087
0x180089079  lea     rcx, qword_1801B97E0; this
0x180089080  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180089087  cmp     [rcx+8], r13b
0x18008908b  jz      loc_18008913A
0x180089091  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180089096  cmp     [rax+7CCh], ebx
0x18008909c  jz      loc_18008913A
0x1800890a2  mov     r8d, 0E9h
0x1800890a8  jmp     loc_180088CC3
0x1800890ad  mov     ecx, [rbp+var_34]
0x1800890b0  test    ecx, ecx
0x1800890b2  jz      short loc_18008912F
0x1800890b4  mov     ecx, r13d
0x1800890b7  jmp     short loc_180089134
0x1800890b9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800890c0  mov     ebx, 80070216h
0x1800890c5  test    rcx, rcx
  ... truncated ...
```
