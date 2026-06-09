# CAVIMediaSourcePlugin::GetStreamParserByStreamId(ulong,CAVIStreamParser * *,int *)

- ea: `0x180067670`
- end: `0x180067ba1`
- name: `?GetStreamParserByStreamId@CAVIMediaSourcePlugin@@AEAAJKPEAPEAVCAVIStreamParser@@PEAH@Z`
- size: `1329`
- prototype: `__int64 __fastcall(CAVIMediaSourcePlugin *__hidden this, unsigned int, struct CAVIStreamParser **, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f8180`
- `0x18013f6b0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180047a00`
- `0x180067670`
- `0x180071a44`
- `0x180073b14`
- `0x180074814`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800677ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067882`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800679a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067ad8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800677ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067882`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800679a6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067a35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180067ad8`

## string_xrefs

- `0x18006768a`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180067703`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180067843`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x1800678d9`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x1800679fd`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180067a8c`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`
- `0x180067b2f`: `CAVIMediaSourcePlugin::GetStreamParserByStreamId`

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
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // r14d
  unsigned int NumberOfStreams; // r13d
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v29; // r14d
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  wchar_t *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  _QWORD v43[3]; // [rsp+30h] [rbp-18h] BYREF
  char v44; // [rsp+90h] [rbp+48h] BYREF
  int v45; // [rsp+98h] [rbp+50h]
  int v46; // [rsp+A0h] [rbp+58h] BYREF
  int v47; // [rsp+A8h] [rbp+60h] BYREF

  v45 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v44,
    "CAVIMediaSourcePlugin::GetStreamParserByStreamId",
    313);
  v43[0] = 0;
  v47 = 0;
  v46 = 0;
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
      v17 = 0;
      NumberOfStreams = CAVIIAVSStreamParser::GetNumberOfStreams(v13);
      v10 = 0;
      while ( v17 < NumberOfStreams )
      {
        ComSmartPtr<CMPEGFrame>::operator=(v43, 0);
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD *))(**((_QWORD **)this + 9) + 272LL))(
                *((_QWORD *)this + 9),
                v17,
                &v47,
                v43);
        if ( v10 < 0 )
        {
          v26 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
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
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v10 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CAVIMediaSourcePlugin::GetStreamParserByStreamId",
                355,
                v10);
          }
          if ( g_wppLevels )
          {
            v25 = 32;
            goto LABEL_31;
          }
          goto LABEL_83;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v43[0] + 264LL))(v43[0], &v46);
        if ( v10 < 0 )
        {
          v22 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
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
            v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v24 + 499) != v10 )
              CallStackContext::TraceFailure(v24, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 357, v10);
          }
          if ( g_wppLevels )
          {
            v25 = 33;
            goto LABEL_31;
          }
          goto LABEL_83;
        }
        if ( v46 == v45 )
        {
          *a3 = v13;
          goto LABEL_19;
        }
        ++v17;
      }
LABEL_71:
      if ( !*a3 )
      {
        v39 = (wchar_t *)CallStackTracing::s_wpInstance;
        v10 = -1072875819;
        if ( !CallStackTracing::s_wpInstance )
        {
          v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
          CallStackTracing::s_wpInstance = v40;
          if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
          {
            v39 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v39 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v39 + 8) )
        {
          v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
          if ( *((_DWORD *)v41 + 499) != -1072875819 )
            CallStackContext::TraceFailure(v41, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 401, -1072875819);
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
      v29 = 0;
      v10 = 0;
      while ( 1 )
      {
        if ( v29 >= v8 )
          goto LABEL_71;
        if ( v43[0] )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43[0] + 16LL))(v43[0]);
          v43[0] = 0;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, _QWORD *))(**((_QWORD **)this + 9) + 272LL))(
                *((_QWORD *)this + 9),
                v29,
                &v47,
                v43);
        if ( v10 < 0 )
          break;
        v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v43[0] + 264LL))(v43[0], &v46);
        if ( v10 < 0 )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14, v15, v16);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != v10 )
              CallStackContext::TraceFailure(v35, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 383, v10);
          }
          if ( g_wppLevels )
          {
            v25 = 35;
LABEL_31:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v25,
              &WPP_14119b90dfdd338c0d68c72da4c50d36_Traceguids,
              this,
              v10);
            goto LABEL_83;
          }
          goto LABEL_83;
        }
        if ( v46 == v45 )
        {
          v14 = v29;
          *a3 = *(struct CAVIStreamParser **)(*(_QWORD *)(*((_QWORD *)this + 10) + 104LL) + 8LL * v29);
LABEL_19:
          if ( a4 )
            *a4 = v47;
          goto LABEL_71;
        }
        ++v29;
      }
      v36 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
        if ( *((_DWORD *)v38 + 499) != v10 )
          CallStackContext::TraceFailure(v38, "CAVIMediaSourcePlugin::GetStreamParserByStreamId", 381, v10);
      }
      if ( g_wppLevels )
      {
        v25 = 34;
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
  if ( v43[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v43[0] + 16LL))(v43[0]);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180067670  mov     [rsp-40h+arg_8], edx
0x180067674  push    rbp
0x180067675  push    rbx
0x180067676  push    rsi
0x180067677  push    rdi
0x180067678  push    r12
0x18006767a  push    r13
0x18006767c  push    r14
0x18006767e  push    r15
0x180067680  mov     rbp, rsp
0x180067683  sub     rsp, 48h
0x180067687  mov     r12, r8
0x18006768a  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x180067691  mov     rsi, rcx
0x180067694  mov     r8d, 139h; int
0x18006769a  lea     rcx, [rbp+arg_0]; this
0x18006769e  mov     rdi, r9
0x1800676a1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800676a6  xor     r15d, r15d
0x1800676a9  mov     [rbp+var_18], r15
0x1800676ad  mov     [rbp+arg_18], r15d
0x1800676b1  mov     [rbp+arg_10], r15d
0x1800676b5  mov     [r12], r15
0x1800676b9  test    rdi, rdi
0x1800676bc  jz      short loc_1800676C1
0x1800676be  mov     [rdi], r15d
0x1800676c1  mov     rax, [rsi+50h]
0x1800676c5  mov     r13d, [rax+70h]
0x1800676c9  test    r13d, r13d
0x1800676cc  jnz     short loc_18006772F
0x1800676ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800676d5  mov     edi, 0C00D36D5h
0x1800676da  mov     ebx, edi
0x1800676dc  test    rcx, rcx
0x1800676df  jnz     short loc_1800676ED
0x1800676e1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800676e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800676ed  cmp     [rcx+8], r15b
0x1800676f1  jz      short loc_180067718
0x1800676f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800676f8  cmp     [rax+7CCh], edi
0x1800676fe  jz      short loc_180067718
0x180067700  mov     r9d, edi; int
0x180067703  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x18006770a  mov     r8d, 14Eh; int
0x180067710  mov     rcx, rax; this
0x180067713  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067718  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006771f  jb      loc_180067B70
0x180067725  mov     edx, 1Fh
0x18006772a  jmp     loc_180067B52
0x18006772f  mov     rax, [rax+68h]
0x180067733  mov     r15, [rax]
0x180067736  mov     rcx, r15
0x180067739  mov     rax, [r15]
0x18006773c  mov     rax, [rax+8]
0x180067740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067745  test    eax, eax
0x180067747  jz      loc_180067905
0x18006774d  mov     rcx, r15; this
0x180067750  call    ?GetNumberOfStreams@CAVIIAVSStreamParser@@QEAAKXZ; CAVIIAVSStreamParser::GetNumberOfStreams(void)
0x180067755  xor     r14d, r14d
0x180067758  mov     r13d, eax
0x18006775b  xor     ebx, ebx
0x18006775d  cmp     r14d, r13d
0x180067760  jnb     loc_180067AB8
0x180067766  xor     edx, edx
0x180067768  lea     rcx, [rbp+var_18]
0x18006776c  call    ??4?$ComSmartPtr@VCMPEGFrame@@@@QEAAPEAVCMPEGFrame@@PEAV1@@Z; ComSmartPtr<CMPEGFrame>::operator=(CMPEGFrame *)
0x180067771  mov     rcx, [rsi+48h]
0x180067775  lea     r9, [rbp+var_18]
0x180067779  lea     r8, [rbp+arg_18]
0x18006777d  mov     edx, r14d
0x180067780  mov     rax, [rcx]
0x180067783  mov     rax, [rax+110h]
0x18006778a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006778f  mov     ebx, eax
0x180067791  test    eax, eax
0x180067793  js      loc_180067873
0x180067799  mov     rcx, [rbp+var_18]
0x18006779d  lea     rdx, [rbp+arg_10]
0x1800677a1  mov     rax, [rcx]
0x1800677a4  mov     rax, [rax+108h]
0x1800677ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800677b0  mov     ebx, eax
0x1800677b2  test    eax, eax
0x1800677b4  js      short loc_1800677DD
0x1800677b6  mov     eax, [rbp+arg_8]
0x1800677b9  cmp     [rbp+arg_10], eax
0x1800677bc  jz      short loc_1800677C3
0x1800677be  inc     r14d
0x1800677c1  jmp     short loc_18006775D
0x1800677c3  mov     [r12], r15
0x1800677c7  xor     r15d, r15d
0x1800677ca  test    rdi, rdi
0x1800677cd  jz      loc_180067ABB
0x1800677d3  mov     eax, [rbp+arg_18]
0x1800677d6  mov     [rdi], eax
0x1800677d8  jmp     loc_180067ABB
0x1800677dd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800677e4  xor     r15d, r15d
0x1800677e7  test    rcx, rcx
0x1800677ea  jnz     short loc_18006782D
0x1800677ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800677f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800677f9  mov     rcx, rax
0x1800677fc  test    rax, rax
0x1800677ff  jz      short loc_18006781F
0x180067801  mov     rax, [rax]
0x180067804  mov     edx, 7F0h
0x180067809  mov     rax, [rax+8]
0x18006780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067812  test    eax, eax
0x180067814  jz      short loc_18006781F
0x180067816  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006781d  jmp     short loc_18006782D
0x18006781f  lea     rcx, qword_1801B07E0; this
0x180067826  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18006782d  cmp     [rcx+8], r15b
0x180067831  jz      short loc_180067858
0x180067833  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067838  cmp     [rax+7CCh], ebx
0x18006783e  jz      short loc_180067858
0x180067840  mov     r9d, ebx; int
0x180067843  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x18006784a  mov     r8d, 165h; int
0x180067850  mov     rcx, rax; this
0x180067853  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067858  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006785f  jb      loc_180067B70
0x180067865  mov     edx, 21h ; '!'
0x18006786a  mov     [rsp+48h+var_28], ebx
0x18006786e  jmp     loc_180067B56
0x180067873  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18006787a  xor     r15d, r15d
0x18006787d  test    rcx, rcx
0x180067880  jnz     short loc_1800678C3
0x180067882  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067888  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18006788f  mov     rcx, rax
0x180067892  test    rax, rax
0x180067895  jz      short loc_1800678B5
0x180067897  mov     rax, [rax]
0x18006789a  mov     edx, 7F0h
0x18006789f  mov     rax, [rax+8]
0x1800678a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678a8  test    eax, eax
0x1800678aa  jz      short loc_1800678B5
0x1800678ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800678b3  jmp     short loc_1800678C3
0x1800678b5  lea     rcx, qword_1801B07E0; this
0x1800678bc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800678c3  cmp     [rcx+8], r15b
0x1800678c7  jz      short loc_1800678EE
0x1800678c9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800678ce  cmp     [rax+7CCh], ebx
0x1800678d4  jz      short loc_1800678EE
0x1800678d6  mov     r9d, ebx; int
0x1800678d9  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x1800678e0  mov     r8d, 163h; int
0x1800678e6  mov     rcx, rax; this
0x1800678e9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800678ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800678f5  jb      loc_180067B70
0x1800678fb  mov     edx, 20h ; ' '
0x180067900  jmp     loc_18006786A
0x180067905  xor     r15d, r15d
0x180067908  mov     r14d, r15d
0x18006790b  mov     ebx, r15d
0x18006790e  cmp     r14d, r13d
0x180067911  jnb     loc_180067ABB
0x180067917  mov     rcx, [rbp+var_18]
0x18006791b  test    rcx, rcx
0x18006791e  jz      short loc_180067930
0x180067920  mov     rax, [rcx]
0x180067923  mov     rax, [rax+10h]
0x180067927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006792c  mov     [rbp+var_18], r15
0x180067930  mov     rcx, [rsi+48h]
0x180067934  lea     r9, [rbp+var_18]
0x180067938  lea     r8, [rbp+arg_18]
0x18006793c  mov     edx, r14d
0x18006793f  mov     rax, [rcx]
0x180067942  mov     rax, [rax+110h]
0x180067949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006794e  mov     ebx, eax
0x180067950  test    eax, eax
0x180067952  js      loc_180067A29
0x180067958  mov     rcx, [rbp+var_18]
0x18006795c  lea     rdx, [rbp+arg_10]
0x180067960  mov     rax, [rcx]
0x180067963  mov     rax, [rax+108h]
0x18006796a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006796f  mov     ebx, eax
0x180067971  test    eax, eax
0x180067973  js      short loc_18006799A
0x180067975  mov     eax, [rbp+arg_8]
0x180067978  cmp     [rbp+arg_10], eax
0x18006797b  jz      short loc_180067982
0x18006797d  inc     r14d
0x180067980  jmp     short loc_18006790E
0x180067982  mov     rax, [rsi+50h]
0x180067986  mov     edx, r14d
0x180067989  mov     rcx, [rax+68h]
0x18006798d  mov     rax, [rcx+rdx*8]
0x180067991  mov     [r12], rax
0x180067995  jmp     loc_1800677CA
0x18006799a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679a1  test    rcx, rcx
0x1800679a4  jnz     short loc_1800679E7
0x1800679a6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800679ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679b3  mov     rcx, rax
0x1800679b6  test    rax, rax
0x1800679b9  jz      short loc_1800679D9
0x1800679bb  mov     rax, [rax]
0x1800679be  mov     edx, 7F0h
0x1800679c3  mov     rax, [rax+8]
0x1800679c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679cc  test    eax, eax
0x1800679ce  jz      short loc_1800679D9
0x1800679d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679d7  jmp     short loc_1800679E7
0x1800679d9  lea     rcx, qword_1801B07E0; this
0x1800679e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800679e7  cmp     [rcx+8], r15b
0x1800679eb  jz      short loc_180067A12
0x1800679ed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800679f2  cmp     [rax+7CCh], ebx
0x1800679f8  jz      short loc_180067A12
0x1800679fa  mov     r9d, ebx; int
0x1800679fd  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x180067a04  mov     r8d, 17Fh; int
0x180067a0a  mov     rcx, rax; this
0x180067a0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067a12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067a19  jb      loc_180067B70
0x180067a1f  mov     edx, 23h ; '#'
0x180067a24  jmp     loc_18006786A
0x180067a29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a30  test    rcx, rcx
0x180067a33  jnz     short loc_180067A76
0x180067a35  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067a3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a42  mov     rcx, rax
0x180067a45  test    rax, rax
0x180067a48  jz      short loc_180067A68
0x180067a4a  mov     rax, [rax]
0x180067a4d  mov     edx, 7F0h
0x180067a52  mov     rax, [rax+8]
0x180067a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a5b  test    eax, eax
0x180067a5d  jz      short loc_180067A68
0x180067a5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a66  jmp     short loc_180067A76
0x180067a68  lea     rcx, qword_1801B07E0; this
0x180067a6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067a76  cmp     [rcx+8], r15b
0x180067a7a  jz      short loc_180067AA1
0x180067a7c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067a81  cmp     [rax+7CCh], ebx
0x180067a87  jz      short loc_180067AA1
0x180067a89  mov     r9d, ebx; int
0x180067a8c  lea     rdx, aCavimediasourc_29; "CAVIMediaSourcePlugin::GetStreamParserB"...
0x180067a93  mov     r8d, 17Dh; int
0x180067a99  mov     rcx, rax; this
0x180067a9c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180067aa1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180067aa8  jb      loc_180067B70
0x180067aae  mov     edx, 22h ; '"'
0x180067ab3  jmp     loc_18006786A
0x180067ab8  xor     r15d, r15d
0x180067abb  cmp     [r12], r15
0x180067abf  jnz     loc_180067B70
0x180067ac5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067acc  mov     edi, 0C00D36D5h
0x180067ad1  mov     ebx, edi
0x180067ad3  test    rcx, rcx
0x180067ad6  jnz     short loc_180067B19
0x180067ad8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180067ade  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180067ae5  mov     rcx, rax
0x180067ae8  test    rax, rax
0x180067aeb  jz      short loc_180067B0B
0x180067aed  mov     rax, [rax]
0x180067af0  mov     edx, 7F0h
0x180067af5  mov     rax, [rax+8]
0x180067af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067afe  test    eax, eax
0x180067b00  jz      short loc_180067B0B
0x180067b02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180067b09  jmp     short loc_180067B19
0x180067b0b  lea     rcx, qword_1801B07E0; this
0x180067b12  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180067b19  cmp     [rcx+8], r15b
0x180067b1d  jz      short loc_180067B44
0x180067b1f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180067b24  cmp     [rax+7CCh], edi
0x180067b2a  jz      short loc_180067B44
0x180067b2c  mov     r9d, edi; int
  ... truncated ...
```
