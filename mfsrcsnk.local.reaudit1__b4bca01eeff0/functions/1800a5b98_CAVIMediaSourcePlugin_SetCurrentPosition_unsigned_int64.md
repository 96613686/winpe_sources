# CAVIMediaSourcePlugin::SetCurrentPosition(unsigned __int64)

- ea: `0x1800a5b98`
- end: `0x1800a606a`
- name: `?SetCurrentPosition@CAVIMediaSourcePlugin@@AEAAJ_K@Z`
- size: `1234`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801477a0`
- `0x180148050`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x18007a0e4`
- `0x1800a5b98`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5cae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5e7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5f11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5fab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5cae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5d43`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5e7c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5f11`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a5fab`

## string_xrefs

- `0x1800a5bb5`: `CAVIMediaSourcePlugin::SetCurrentPosition`
- `0x1800a5d0b`: `CAVIMediaSourcePlugin::SetCurrentPosition`
- `0x1800a5da0`: `CAVIMediaSourcePlugin::SetCurrentPosition`
- `0x1800a5ed9`: `CAVIMediaSourcePlugin::SetCurrentPosition`
- `0x1800a5f6e`: `CAVIMediaSourcePlugin::SetCurrentPosition`
- `0x1800a6008`: `CAVIMediaSourcePlugin::SetCurrentPosition`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::SetCurrentPosition(CAVIMediaSourcePlugin *this, __int64 a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rsi
  CAVIIAVSStreamParser *v8; // r14
  unsigned int NumberOfStreams; // r12d
  unsigned int i; // esi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  wchar_t *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  unsigned int v21; // r12d
  __int64 v22; // rax
  __int64 v23; // r14
  __int64 v24; // rdx
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  int v36; // [rsp+70h] [rbp+40h] BYREF
  __int64 v37; // [rsp+80h] [rbp+50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v36,
    "CAVIMediaSourcePlugin::SetCurrentPosition",
    2022);
  if ( *((_QWORD *)this + 9) )
  {
    v5 = 0;
    if ( a2 != *((_QWORD *)this + 73) )
      *((_DWORD *)this + 152) = -1;
    v6 = *((_QWORD *)this + 10);
    v7 = *((unsigned int *)this + 152);
    *((_QWORD *)this + 74) = -1;
    *((_QWORD *)this + 73) = a2;
    if ( (_DWORD)v7 == -1 )
      v7 = 0;
    v8 = **(CAVIIAVSStreamParser ***)(v6 + 104);
    if ( !(*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v8 + 8LL))(v8) )
    {
      v21 = *(_DWORD *)(*((_QWORD *)this + 10) + 112LL);
      while ( 1 )
      {
        if ( (unsigned int)v7 >= v21 )
          goto LABEL_73;
        v22 = *((_QWORD *)this + 10);
        v37 = 0;
        v36 = 0;
        v23 = *(_QWORD *)(*(_QWORD *)(v22 + 104) + 8 * v7);
        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, __int64 *))(**((_QWORD **)this + 9) + 272LL))(
               *((_QWORD *)this + 9),
               (unsigned int)v7,
               &v36,
               &v37);
        if ( v5 < 0 )
          break;
        if ( v36 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 104LL))(v23, a2);
          if ( v5 < 0 )
          {
            v26 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
              CallStackTracing::s_wpInstance = v27;
              if ( v27
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
              {
                v26 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v26 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v26 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAVIMediaSourcePlugin::SetCurrentPosition",
                  2089,
                  v5);
            }
            if ( g_wppLevels )
            {
              v17 = 203;
              goto LABEL_33;
            }
            goto LABEL_34;
          }
          v7 = (unsigned int)(v7 + 1);
          *((_DWORD *)this + 152) = v7;
        }
        else
        {
          v7 = (unsigned int)(v7 + 1);
        }
        ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v37);
      }
      v29 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
        if ( *((_DWORD *)v31 + 499) != v5 )
          CallStackContext::TraceFailure(v31, "CAVIMediaSourcePlugin::SetCurrentPosition", 2082, v5);
      }
      if ( g_wppLevels )
      {
        v17 = 202;
LABEL_33:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids, this, v5);
      }
LABEL_34:
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v37);
      goto LABEL_73;
    }
    NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v8);
    for ( i = 0; i < NumberOfStreams; ++i )
    {
      v11 = *((_QWORD *)this + 9);
      v37 = 0;
      v36 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v11 + 272LL))(v11, i, &v36, &v37);
      if ( v5 < 0 )
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != v5 )
            CallStackContext::TraceFailure(v20, "CAVIMediaSourcePlugin::SetCurrentPosition", 2061, v5);
        }
        if ( g_wppLevels )
        {
          v17 = 200;
          goto LABEL_33;
        }
        goto LABEL_34;
      }
      if ( v36 )
      {
        v5 = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *, __int64))(*(_QWORD *)v8 + 104LL))(v8, a2);
        if ( v5 < 0 )
        {
          v14 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
            CallStackTracing::s_wpInstance = v15;
            if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
            {
              v14 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v14 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v14 + 8) )
          {
            v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
            if ( *((_DWORD *)v16 + 499) != v5 )
              CallStackContext::TraceFailure(v16, "CAVIMediaSourcePlugin::SetCurrentPosition", 2068, v5);
          }
          if ( g_wppLevels )
          {
            v17 = 201;
            goto LABEL_33;
          }
        }
        goto LABEL_34;
      }
      ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&v37);
    }
  }
  else
  {
    v32 = (wchar_t *)CallStackTracing::s_wpInstance;
    v5 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
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
      if ( *((_DWORD *)v34 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v34, "CAVIMediaSourcePlugin::SetCurrentPosition", 2026, -1072875854);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        199,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        this,
        -1072875854);
  }
LABEL_73:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a5b98  mov     [rsp-38h+arg_8], rbx
0x1800a5b9d  push    rbp
0x1800a5b9e  push    rsi
0x1800a5b9f  push    rdi
0x1800a5ba0  push    r12
0x1800a5ba2  push    r13
0x1800a5ba4  push    r14
0x1800a5ba6  push    r15
0x1800a5ba8  mov     rbp, rsp
0x1800a5bab  sub     rsp, 30h
0x1800a5baf  mov     r15, rdx
0x1800a5bb2  mov     rdi, rcx
0x1800a5bb5  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a5bbc  mov     r8d, 7E6h; int
0x1800a5bc2  lea     rcx, [rbp+arg_0]; this
0x1800a5bc6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a5bcb  xor     r13d, r13d
0x1800a5bce  cmp     [rdi+48h], r13
0x1800a5bd2  jz      loc_1800A5F9A
0x1800a5bd8  or      ecx, 0FFFFFFFFh
0x1800a5bdb  mov     ebx, r13d
0x1800a5bde  cmp     r15, [rdi+248h]
0x1800a5be5  jz      short loc_1800A5BED
0x1800a5be7  mov     [rdi+260h], ecx
0x1800a5bed  mov     rax, [rdi+50h]
0x1800a5bf1  mov     esi, [rdi+260h]
0x1800a5bf7  cmp     esi, ecx
0x1800a5bf9  mov     qword ptr [rdi+250h], 0FFFFFFFFFFFFFFFFh
0x1800a5c04  mov     [rdi+248h], r15
0x1800a5c0b  cmovz   esi, r13d
0x1800a5c0f  mov     rcx, [rax+68h]
0x1800a5c13  mov     r14, [rcx]
0x1800a5c16  mov     rcx, r14
0x1800a5c19  mov     rax, [r14]
0x1800a5c1c  mov     rax, [rax+8]
0x1800a5c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c25  test    eax, eax
0x1800a5c27  jz      loc_1800A5DEF
0x1800a5c2d  mov     rcx, r14; this
0x1800a5c30  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x1800a5c35  mov     r12d, eax
0x1800a5c38  mov     esi, r13d
0x1800a5c3b  cmp     esi, r12d
0x1800a5c3e  jnb     loc_1800A6049
0x1800a5c44  mov     rcx, [rdi+48h]
0x1800a5c48  lea     r9, [rbp+arg_10]
0x1800a5c4c  mov     [rbp+arg_10], r13
0x1800a5c50  lea     r8, [rbp+arg_0]
0x1800a5c54  mov     [rbp+arg_0], r13d
0x1800a5c58  mov     edx, esi
0x1800a5c5a  mov     rax, [rcx]
0x1800a5c5d  mov     rax, [rax+110h]
0x1800a5c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c69  mov     ebx, eax
0x1800a5c6b  test    eax, eax
0x1800a5c6d  js      loc_1800A5D37
0x1800a5c73  cmp     [rbp+arg_0], r13d
0x1800a5c77  jnz     short loc_1800A5C86
0x1800a5c79  lea     rcx, [rbp+arg_10]; void *
0x1800a5c7d  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800a5c82  inc     esi
0x1800a5c84  jmp     short loc_1800A5C3B
0x1800a5c86  mov     rax, [r14]
0x1800a5c89  mov     rdx, r15
0x1800a5c8c  mov     rcx, r14
0x1800a5c8f  mov     rax, [rax+68h]
0x1800a5c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c98  mov     ebx, eax
0x1800a5c9a  test    eax, eax
0x1800a5c9c  jns     loc_1800A5DE1
0x1800a5ca2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ca9  test    rcx, rcx
0x1800a5cac  jnz     short loc_1800A5CF5
0x1800a5cae  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5cb5  nop     dword ptr [rax+rax+00h]
0x1800a5cba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5cc1  mov     rcx, rax
0x1800a5cc4  test    rax, rax
0x1800a5cc7  jz      short loc_1800A5CE7
0x1800a5cc9  mov     rax, [rax]
0x1800a5ccc  mov     edx, 7F0h
0x1800a5cd1  mov     rax, [rax+8]
0x1800a5cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5cda  test    eax, eax
0x1800a5cdc  jz      short loc_1800A5CE7
0x1800a5cde  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ce5  jmp     short loc_1800A5CF5
0x1800a5ce7  lea     rcx, qword_1801B97E0; this
0x1800a5cee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5cf5  cmp     [rcx+8], r13b
0x1800a5cf9  jz      short loc_1800A5D20
0x1800a5cfb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5d00  cmp     [rax+7CCh], ebx
0x1800a5d06  jz      short loc_1800A5D20
0x1800a5d08  mov     r9d, ebx; int
0x1800a5d0b  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a5d12  mov     r8d, 814h; int
0x1800a5d18  mov     rcx, rax; this
0x1800a5d1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5d20  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5d27  jb      loc_1800A5DE1
0x1800a5d2d  mov     edx, 0C9h
0x1800a5d32  jmp     loc_1800A5DC3
0x1800a5d37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d3e  test    rcx, rcx
0x1800a5d41  jnz     short loc_1800A5D8A
0x1800a5d43  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5d4a  nop     dword ptr [rax+rax+00h]
0x1800a5d4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d56  mov     rcx, rax
0x1800a5d59  test    rax, rax
0x1800a5d5c  jz      short loc_1800A5D7C
0x1800a5d5e  mov     rax, [rax]
0x1800a5d61  mov     edx, 7F0h
0x1800a5d66  mov     rax, [rax+8]
0x1800a5d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5d6f  test    eax, eax
0x1800a5d71  jz      short loc_1800A5D7C
0x1800a5d73  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d7a  jmp     short loc_1800A5D8A
0x1800a5d7c  lea     rcx, qword_1801B97E0; this
0x1800a5d83  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5d8a  cmp     [rcx+8], r13b
0x1800a5d8e  jz      short loc_1800A5DB5
0x1800a5d90  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5d95  cmp     [rax+7CCh], ebx
0x1800a5d9b  jz      short loc_1800A5DB5
0x1800a5d9d  mov     r9d, ebx; int
0x1800a5da0  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a5da7  mov     r8d, 80Dh; int
0x1800a5dad  mov     rcx, rax; this
0x1800a5db0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5db5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5dbc  jb      short loc_1800A5DE1
0x1800a5dbe  mov     edx, 0C8h
0x1800a5dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5dca  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800a5dd1  mov     r9, rdi
0x1800a5dd4  mov     [rsp+30h+var_10], ebx
0x1800a5dd8  mov     rcx, [rcx+10h]
0x1800a5ddc  call    WPP_SF_qD
0x1800a5de1  lea     rcx, [rbp+arg_10]; void *
0x1800a5de5  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800a5dea  jmp     loc_1800A6049
0x1800a5def  mov     rax, [rdi+50h]
0x1800a5df3  mov     r12d, [rax+70h]
0x1800a5df7  cmp     esi, r12d
0x1800a5dfa  jnb     loc_1800A6049
0x1800a5e00  mov     rax, [rdi+50h]
0x1800a5e04  lea     r9, [rbp+arg_10]
0x1800a5e08  mov     [rbp+arg_10], r13
0x1800a5e0c  lea     r8, [rbp+arg_0]
0x1800a5e10  mov     [rbp+arg_0], r13d
0x1800a5e14  mov     edx, esi
0x1800a5e16  mov     rcx, [rax+68h]
0x1800a5e1a  mov     r14, [rcx+rsi*8]
0x1800a5e1e  mov     rcx, [rdi+48h]
0x1800a5e22  mov     rax, [rcx]
0x1800a5e25  mov     rax, [rax+110h]
0x1800a5e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e31  mov     ebx, eax
0x1800a5e33  test    eax, eax
0x1800a5e35  js      loc_1800A5F05
0x1800a5e3b  cmp     [rbp+arg_0], r13d
0x1800a5e3f  jnz     short loc_1800A5E45
0x1800a5e41  inc     esi
0x1800a5e43  jmp     short loc_1800A5E65
0x1800a5e45  mov     rax, [r14]
0x1800a5e48  mov     rdx, r15
0x1800a5e4b  mov     rcx, r14
0x1800a5e4e  mov     rax, [rax+68h]
0x1800a5e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5e57  mov     ebx, eax
0x1800a5e59  test    eax, eax
0x1800a5e5b  js      short loc_1800A5E70
0x1800a5e5d  inc     esi
0x1800a5e5f  mov     [rdi+260h], esi
0x1800a5e65  lea     rcx, [rbp+arg_10]; void *
0x1800a5e69  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x1800a5e6e  jmp     short loc_1800A5DF7
0x1800a5e70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5e77  test    rcx, rcx
0x1800a5e7a  jnz     short loc_1800A5EC3
0x1800a5e7c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5e83  nop     dword ptr [rax+rax+00h]
0x1800a5e88  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5e8f  mov     rcx, rax
0x1800a5e92  test    rax, rax
0x1800a5e95  jz      short loc_1800A5EB5
0x1800a5e97  mov     rax, [rax]
0x1800a5e9a  mov     edx, 7F0h
0x1800a5e9f  mov     rax, [rax+8]
0x1800a5ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5ea8  test    eax, eax
0x1800a5eaa  jz      short loc_1800A5EB5
0x1800a5eac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5eb3  jmp     short loc_1800A5EC3
0x1800a5eb5  lea     rcx, qword_1801B97E0; this
0x1800a5ebc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ec3  cmp     [rcx+8], r13b
0x1800a5ec7  jz      short loc_1800A5EEE
0x1800a5ec9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5ece  cmp     [rax+7CCh], ebx
0x1800a5ed4  jz      short loc_1800A5EEE
0x1800a5ed6  mov     r9d, ebx; int
0x1800a5ed9  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a5ee0  mov     r8d, 829h; int
0x1800a5ee6  mov     rcx, rax; this
0x1800a5ee9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5eee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5ef5  jb      loc_1800A5DE1
0x1800a5efb  mov     edx, 0CBh
0x1800a5f00  jmp     loc_1800A5DC3
0x1800a5f05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5f0c  test    rcx, rcx
0x1800a5f0f  jnz     short loc_1800A5F58
0x1800a5f11  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5f18  nop     dword ptr [rax+rax+00h]
0x1800a5f1d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5f24  mov     rcx, rax
0x1800a5f27  test    rax, rax
0x1800a5f2a  jz      short loc_1800A5F4A
0x1800a5f2c  mov     rax, [rax]
0x1800a5f2f  mov     edx, 7F0h
0x1800a5f34  mov     rax, [rax+8]
0x1800a5f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5f3d  test    eax, eax
0x1800a5f3f  jz      short loc_1800A5F4A
0x1800a5f41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5f48  jmp     short loc_1800A5F58
0x1800a5f4a  lea     rcx, qword_1801B97E0; this
0x1800a5f51  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5f58  cmp     [rcx+8], r13b
0x1800a5f5c  jz      short loc_1800A5F83
0x1800a5f5e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5f63  cmp     [rax+7CCh], ebx
0x1800a5f69  jz      short loc_1800A5F83
0x1800a5f6b  mov     r9d, ebx; int
0x1800a5f6e  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a5f75  mov     r8d, 822h; int
0x1800a5f7b  mov     rcx, rax; this
0x1800a5f7e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a5f83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a5f8a  jb      loc_1800A5DE1
0x1800a5f90  mov     edx, 0CAh
0x1800a5f95  jmp     loc_1800A5DC3
0x1800a5f9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5fa1  mov     ebx, 0C00D36B2h
0x1800a5fa6  test    rcx, rcx
0x1800a5fa9  jnz     short loc_1800A5FF2
0x1800a5fab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a5fb2  nop     dword ptr [rax+rax+00h]
0x1800a5fb7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5fbe  mov     rcx, rax
0x1800a5fc1  test    rax, rax
0x1800a5fc4  jz      short loc_1800A5FE4
0x1800a5fc6  mov     rax, [rax]
0x1800a5fc9  mov     edx, 7F0h
0x1800a5fce  mov     rax, [rax+8]
0x1800a5fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fd7  test    eax, eax
0x1800a5fd9  jz      short loc_1800A5FE4
0x1800a5fdb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5fe2  jmp     short loc_1800A5FF2
0x1800a5fe4  lea     rcx, qword_1801B97E0; this
0x1800a5feb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a5ff2  cmp     [rcx+8], r13b
0x1800a5ff6  jz      short loc_1800A601D
0x1800a5ff8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a5ffd  cmp     [rax+7CCh], ebx
0x1800a6003  jz      short loc_1800A601D
0x1800a6005  mov     r9d, ebx; int
0x1800a6008  lea     rdx, aCavimediasourc_3; "CAVIMediaSourcePlugin::SetCurrentPositi"...
0x1800a600f  mov     r8d, 7EAh; int
0x1800a6015  mov     rcx, rax; this
0x1800a6018  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a601d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a6024  jb      short loc_1800A6049
0x1800a6026  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a602d  lea     r8, WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids
0x1800a6034  mov     edx, 0C7h
0x1800a6039  mov     [rsp+30h+var_10], ebx
0x1800a603d  mov     r9, rdi
0x1800a6040  mov     rcx, [rcx+10h]
0x1800a6044  call    WPP_SF_qD
0x1800a6049  lea     rcx, [rbp+arg_0]; this
0x1800a604d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a6052  mov     eax, ebx
0x1800a6054  mov     rbx, [rsp+30h+arg_8]
0x1800a6059  add     rsp, 30h
0x1800a605d  pop     r15
0x1800a605f  pop     r14
0x1800a6061  pop     r13
0x1800a6063  pop     r12
0x1800a6065  pop     rdi
0x1800a6066  pop     rsi
0x1800a6067  pop     rbp
0x1800a6068  retn
```
