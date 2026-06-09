# CAVIMediaSourcePlugin::GetStreamParserByStreamId(ulong,CAVIStreamParser * *,int *)

- ea: `0x180068574`
- end: `0x180068ac4`
- name: `?GetStreamParserByStreamId@CAVIMediaSourcePlugin@@AEAAJKPEAPEAVCAVIStreamParser@@PEAH@Z`
- size: `1360`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, unsigned int, struct CAVIStreamParser **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800feee0`
- `0x180147350`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004a8a8`
- `0x180068574`
- `0x180077708`
- `0x180079680`
- `0x18007a0e4`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800686f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006878c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800688b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006894b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800689f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800686f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006878c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800688b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18006894b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800689f4`

## string_xrefs

- `0x18006858e`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180068607`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x18006874d`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x1800687e9`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180068913`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x1800689a8`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180068a51`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`

## pseudocode

```c
__int64 __fastcall CAVIMediaSourcePlugin::GetStreamParserByStreamId(
        CAVIMediaSourcePlugin *this,
        int a2,
        struct CAVIStreamParser **a3,
        int *a4)
{
  __int64 v7; // rax
  unsigned int v8; // r13d
  CallStackTracing *v9; // rcx
  int v10; // ebx
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  CAVIIAVSStreamParser *v13; // r15
  __int64 v14; // rdx
  unsigned int v15; // r14d
  unsigned int NumberOfStreams; // r13d
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v25; // r14d
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _QWORD v37[3]; // [rsp+30h] [rbp-18h] BYREF
  char v38; // [rsp+90h] [rbp+48h] BYREF
  int v39; // [rsp+98h] [rbp+50h]
  int v40; // [rsp+A0h] [rbp+58h] BYREF
  int v41; // [rsp+A8h] [rbp+60h] BYREF

  v39 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v38,
    "CAVIMediaSourcePlugin::GetStreamParserByStreamId",
    313);
  v37[0] = 0;
  v41 = 0;
  v40 = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v7 = *((_QWORD *)this + 10);
  v8 = *(_DWORD *)(v7 + 112);
  if ( v8 )
  {
    v13 = **(CAVIIAVSStreamParser ***)(v7 + 104);
    if ( (*(unsigned int (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)v13 + 8LL))(v13) )
    {
      v15 = 0;
      NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v13);
      v10 = 0;
      while ( v15 < NumberOfStreams )
      {
        ComSmartPtr<CMPEGFrame>::operator=(v37, 0);
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD *))(**((_QWORD **)this + 9) + 272LL))(
                *((_QWORD *)this + 9),
                v15,
                &v41,
                v37);
        if ( v10 < 0 )
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17);
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
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CAVIMediaSourcePlugin::GetStreamParserByStreamId",
                355,
                v10);
          }
          if ( g_wppLevels )
          {
            v21 = 32;
            goto LABEL_31;
          }
          goto LABEL_83;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v37[0] + 264LL))(v37[0], &v40);
        if ( v10 < 0 )
        {
          v18 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
            if ( *((_DWORD *)v20 + 499) != v10 )
              CallStackContext::TraceFailure(v20, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 357, v10);
          }
          if ( g_wppLevels )
          {
            v21 = 33;
            goto LABEL_31;
          }
          goto LABEL_83;
        }
        if ( v40 == v39 )
        {
          *a3 = v13;
          goto LABEL_19;
        }
        ++v15;
      }
LABEL_71:
      if ( !*a3 )
      {
        v33 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -1072875819;
        if ( !CallStackTracing::s_wpInstance )
        {
          v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v34;
          if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
          v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
          if ( *((_DWORD *)v35 + 499) != -1072875819 )
            CallStackContext::TraceFailure(v35, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 401, -1072875819);
        }
        if ( g_wppLevels )
        {
          v12 = 36;
          goto LABEL_82;
        }
      }
    }
    else
    {
      v25 = 0;
      v10 = 0;
      while ( 1 )
      {
        if ( v25 >= v8 )
          goto LABEL_71;
        if ( v37[0] )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
          v37[0] = 0;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD *))(**((_QWORD **)this + 9) + 272LL))(
                *((_QWORD *)this + 9),
                v25,
                &v41,
                v37);
        if ( v10 < 0 )
          break;
        v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v37[0] + 264LL))(v37[0], &v40);
        if ( v10 < 0 )
        {
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
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
            if ( *((_DWORD *)v29 + 499) != v10 )
              CallStackContext::TraceFailure(v29, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 383, v10);
          }
          if ( g_wppLevels )
          {
            v21 = 35;
LABEL_31:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              this,
              v10);
            goto LABEL_83;
          }
          goto LABEL_83;
        }
        if ( v40 == v39 )
        {
          v14 = v25;
          *a3 = *(struct CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 10) + 104LL) + 8LL * v25);
LABEL_19:
          if ( a4 )
            *a4 = v41;
          goto LABEL_71;
        }
        ++v25;
      }
      v30 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v30 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
        if ( *((_DWORD *)v32 + 499) != v10 )
          CallStackContext::TraceFailure(v32, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 381, v10);
      }
      if ( g_wppLevels )
      {
        v21 = 34;
        goto LABEL_31;
      }
    }
  }
  else
  {
    v9 = CallStackTracing::s_wpInstance;
    v10 = -1072875819;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v9 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext(v9);
      if ( *((_DWORD *)v11 + 499) != -1072875819 )
        CallStackContext::TraceFailure(v11, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 334, -1072875819);
    }
    if ( g_wppLevels )
    {
      v12 = 31;
LABEL_82:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
        this,
        -1072875819);
    }
  }
LABEL_83:
  if ( v37[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v38);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180068574  mov     [rsp-40h+arg_8], edx
0x180068578  push    rbp
0x180068579  push    rbx
0x18006857a  push    rsi
0x18006857b  push    rdi
0x18006857c  push    r12
0x18006857e  push    r13
0x180068580  push    r14
0x180068582  push    r15
0x180068584  mov     rbp, rsp
0x180068587  sub     rsp, 48h
0x18006858b  mov     r12, r8
0x18006858e  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x180068595  mov     rsi, rcx
0x180068598  mov     r8d, 139h; int
0x18006859e  lea     rcx, [rbp+arg_0]; this
0x1800685a2  mov     rdi, r9
0x1800685a5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800685aa  xor     r15d, r15d
0x1800685ad  mov     [rbp+var_18], r15
0x1800685b1  mov     [rbp+arg_18], r15d
0x1800685b5  mov     [rbp+arg_10], r15d
0x1800685b9  mov     [r12], r15
0x1800685bd  test    rdi, rdi
0x1800685c0  jz      short loc_1800685C5
0x1800685c2  mov     [rdi], r15d
0x1800685c5  mov     rax, [rsi+50h]
0x1800685c9  mov     r13d, [rax+70h]
0x1800685cd  test    r13d, r13d
0x1800685d0  jnz     short loc_180068633
0x1800685d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800685d9  mov     edi, 0C00D36D5h
0x1800685de  mov     ebx, edi
0x1800685e0  test    rcx, rcx
0x1800685e3  jnz     short loc_1800685F1
0x1800685e5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800685ea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800685f1  cmp     [rcx+8], r15b
0x1800685f5  jz      short loc_18006861C
0x1800685f7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800685fc  cmp     [rax+7CCh], edi
0x180068602  jz      short loc_18006861C
0x180068604  mov     r9d, edi; int
0x180068607  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x18006860e  mov     r8d, 14Eh; int
0x180068614  mov     rcx, rax; this
0x180068617  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18006861c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068623  jb      loc_180068A92
0x180068629  mov     edx, 1Fh
0x18006862e  jmp     loc_180068A74
0x180068633  mov     rax, [rax+68h]
0x180068637  mov     r15, [rax]
0x18006863a  mov     rcx, r15
0x18006863d  mov     rax, [r15]
0x180068640  mov     rax, [rax+8]
0x180068644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068649  test    eax, eax
0x18006864b  jz      loc_180068815
0x180068651  mov     rcx, r15; this
0x180068654  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x180068659  xor     r14d, r14d
0x18006865c  mov     r13d, eax
0x18006865f  xor     ebx, ebx
0x180068661  cmp     r14d, r13d
0x180068664  jnb     loc_1800689D4
0x18006866a  xor     edx, edx
0x18006866c  lea     rcx, [rbp+var_18]
0x180068670  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@PEAV1@@Z; ComSmartPtr<CMPEGFrame>::operator=(CMPEGFrame *)
0x180068675  mov     rcx, [rsi+48h]
0x180068679  lea     r9, [rbp+var_18]
0x18006867d  lea     r8, [rbp+arg_18]
0x180068681  mov     edx, r14d
0x180068684  mov     rax, [rcx]
0x180068687  mov     rax, [rax+110h]
0x18006868e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068693  mov     ebx, eax
0x180068695  test    eax, eax
0x180068697  js      loc_18006877D
0x18006869d  mov     rcx, [rbp+var_18]
0x1800686a1  lea     rdx, [rbp+arg_10]
0x1800686a5  mov     rax, [rcx]
0x1800686a8  mov     rax, [rax+108h]
0x1800686af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800686b4  mov     ebx, eax
0x1800686b6  test    eax, eax
0x1800686b8  js      short loc_1800686E1
0x1800686ba  mov     eax, [rbp+arg_8]
0x1800686bd  cmp     [rbp+arg_10], eax
0x1800686c0  jz      short loc_1800686C7
0x1800686c2  inc     r14d
0x1800686c5  jmp     short loc_180068661
0x1800686c7  mov     [r12], r15
0x1800686cb  xor     r15d, r15d
0x1800686ce  test    rdi, rdi
0x1800686d1  jz      loc_1800689D7
0x1800686d7  mov     eax, [rbp+arg_18]
0x1800686da  mov     [rdi], eax
0x1800686dc  jmp     loc_1800689D7
0x1800686e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800686e8  xor     r15d, r15d
0x1800686eb  test    rcx, rcx
0x1800686ee  jnz     short loc_180068737
0x1800686f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800686f7  nop     dword ptr [rax+rax+00h]
0x1800686fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068703  mov     rcx, rax
0x180068706  test    rax, rax
0x180068709  jz      short loc_180068729
0x18006870b  mov     rax, [rax]
0x18006870e  mov     edx, 7F0h
0x180068713  mov     rax, [rax+8]
0x180068717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006871c  test    eax, eax
0x18006871e  jz      short loc_180068729
0x180068720  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068727  jmp     short loc_180068737
0x180068729  lea     rcx, qword_1801B97E0; this
0x180068730  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068737  cmp     [rcx+8], r15b
0x18006873b  jz      short loc_180068762
0x18006873d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068742  cmp     [rax+7CCh], ebx
0x180068748  jz      short loc_180068762
0x18006874a  mov     r9d, ebx; int
0x18006874d  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x180068754  mov     r8d, 165h; int
0x18006875a  mov     rcx, rax; this
0x18006875d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068762  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068769  jb      loc_180068A92
0x18006876f  mov     edx, 21h ; '!'
0x180068774  mov     [rsp+48h+var_28], ebx
0x180068778  jmp     loc_180068A78
0x18006877d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068784  xor     r15d, r15d
0x180068787  test    rcx, rcx
0x18006878a  jnz     short loc_1800687D3
0x18006878c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068793  nop     dword ptr [rax+rax+00h]
0x180068798  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006879f  mov     rcx, rax
0x1800687a2  test    rax, rax
0x1800687a5  jz      short loc_1800687C5
0x1800687a7  mov     rax, [rax]
0x1800687aa  mov     edx, 7F0h
0x1800687af  mov     rax, [rax+8]
0x1800687b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687b8  test    eax, eax
0x1800687ba  jz      short loc_1800687C5
0x1800687bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800687c3  jmp     short loc_1800687D3
0x1800687c5  lea     rcx, qword_1801B97E0; this
0x1800687cc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800687d3  cmp     [rcx+8], r15b
0x1800687d7  jz      short loc_1800687FE
0x1800687d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800687de  cmp     [rax+7CCh], ebx
0x1800687e4  jz      short loc_1800687FE
0x1800687e6  mov     r9d, ebx; int
0x1800687e9  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x1800687f0  mov     r8d, 163h; int
0x1800687f6  mov     rcx, rax; this
0x1800687f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800687fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068805  jb      loc_180068A92
0x18006880b  mov     edx, 20h ; ' '
0x180068810  jmp     loc_180068774
0x180068815  xor     r15d, r15d
0x180068818  mov     r14d, r15d
0x18006881b  mov     ebx, r15d
0x18006881e  cmp     r14d, r13d
0x180068821  jnb     loc_1800689D7
0x180068827  mov     rcx, [rbp+var_18]
0x18006882b  test    rcx, rcx
0x18006882e  jz      short loc_180068840
0x180068830  mov     rax, [rcx]
0x180068833  mov     rax, [rax+10h]
0x180068837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006883c  mov     [rbp+var_18], r15
0x180068840  mov     rcx, [rsi+48h]
0x180068844  lea     r9, [rbp+var_18]
0x180068848  lea     r8, [rbp+arg_18]
0x18006884c  mov     edx, r14d
0x18006884f  mov     rax, [rcx]
0x180068852  mov     rax, [rax+110h]
0x180068859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006885e  mov     ebx, eax
0x180068860  test    eax, eax
0x180068862  js      loc_18006893F
0x180068868  mov     rcx, [rbp+var_18]
0x18006886c  lea     rdx, [rbp+arg_10]
0x180068870  mov     rax, [rcx]
0x180068873  mov     rax, [rax+108h]
0x18006887a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006887f  mov     ebx, eax
0x180068881  test    eax, eax
0x180068883  js      short loc_1800688AA
0x180068885  mov     eax, [rbp+arg_8]
0x180068888  cmp     [rbp+arg_10], eax
0x18006888b  jz      short loc_180068892
0x18006888d  inc     r14d
0x180068890  jmp     short loc_18006881E
0x180068892  mov     rax, [rsi+50h]
0x180068896  mov     edx, r14d
0x180068899  mov     rcx, [rax+68h]
0x18006889d  mov     rax, [rcx+rdx*8]
0x1800688a1  mov     [r12], rax
0x1800688a5  jmp     loc_1800686CE
0x1800688aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800688b1  test    rcx, rcx
0x1800688b4  jnz     short loc_1800688FD
0x1800688b6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800688bd  nop     dword ptr [rax+rax+00h]
0x1800688c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800688c9  mov     rcx, rax
0x1800688cc  test    rax, rax
0x1800688cf  jz      short loc_1800688EF
0x1800688d1  mov     rax, [rax]
0x1800688d4  mov     edx, 7F0h
0x1800688d9  mov     rax, [rax+8]
0x1800688dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688e2  test    eax, eax
0x1800688e4  jz      short loc_1800688EF
0x1800688e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800688ed  jmp     short loc_1800688FD
0x1800688ef  lea     rcx, qword_1801B97E0; this
0x1800688f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800688fd  cmp     [rcx+8], r15b
0x180068901  jz      short loc_180068928
0x180068903  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180068908  cmp     [rax+7CCh], ebx
0x18006890e  jz      short loc_180068928
0x180068910  mov     r9d, ebx; int
0x180068913  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x18006891a  mov     r8d, 17Fh; int
0x180068920  mov     rcx, rax; this
0x180068923  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180068928  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006892f  jb      loc_180068A92
0x180068935  mov     edx, 23h ; '#'
0x18006893a  jmp     loc_180068774
0x18006893f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068946  test    rcx, rcx
0x180068949  jnz     short loc_180068992
0x18006894b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180068952  nop     dword ptr [rax+rax+00h]
0x180068957  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006895e  mov     rcx, rax
0x180068961  test    rax, rax
0x180068964  jz      short loc_180068984
0x180068966  mov     rax, [rax]
0x180068969  mov     edx, 7F0h
0x18006896e  mov     rax, [rax+8]
0x180068972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068977  test    eax, eax
0x180068979  jz      short loc_180068984
0x18006897b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068982  jmp     short loc_180068992
0x180068984  lea     rcx, qword_1801B97E0; this
0x18006898b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068992  cmp     [rcx+8], r15b
0x180068996  jz      short loc_1800689BD
0x180068998  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18006899d  cmp     [rax+7CCh], ebx
0x1800689a3  jz      short loc_1800689BD
0x1800689a5  mov     r9d, ebx; int
0x1800689a8  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x1800689af  mov     r8d, 17Dh; int
0x1800689b5  mov     rcx, rax; this
0x1800689b8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800689bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800689c4  jb      loc_180068A92
0x1800689ca  mov     edx, 22h ; '"'
0x1800689cf  jmp     loc_180068774
0x1800689d4  xor     r15d, r15d
0x1800689d7  cmp     [r12], r15
0x1800689db  jnz     loc_180068A92
0x1800689e1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800689e8  mov     edi, 0C00D36D5h
0x1800689ed  mov     ebx, edi
0x1800689ef  test    rcx, rcx
0x1800689f2  jnz     short loc_180068A3B
0x1800689f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800689fb  nop     dword ptr [rax+rax+00h]
0x180068a00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180068a07  mov     rcx, rax
0x180068a0a  test    rax, rax
0x180068a0d  jz      short loc_180068A2D
0x180068a0f  mov     rax, [rax]
0x180068a12  mov     edx, 7F0h
0x180068a17  mov     rax, [rax+8]
0x180068a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a20  test    eax, eax
0x180068a22  jz      short loc_180068A2D
0x180068a24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180068a2b  jmp     short loc_180068A3B
0x180068a2d  lea     rcx, qword_1801B97E0; this
0x180068a34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180068a3b  cmp     [rcx+8], r15b
  ... truncated ...
```
