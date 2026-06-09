# CAVIStreamParser::ValidateStreamLength(void)

- ea: `0x18004ae78`
- end: `0x18004b6cc`
- name: `?ValidateStreamLength@CAVIStreamParser@@QEAAJXZ`
- size: `2132`
- prototype: `__int64 __fastcall(CAVIStreamParser *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18013de3c`

## callees

- `0x180005cf4`
- `0x180019d24`
- `0x18001a8f4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x18004ae78`
- `0x180077708`
- `0x180079680`
- `0x1800ee5b8`
- `0x18013fe10`
- `0x180140a7c`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004afa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b04c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b10c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b1c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b27e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b490`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b5ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004aef7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004afa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b04c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b10c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b1c4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b27e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b336`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b490`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b5ee`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18004b311`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18004b311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b693`

## pseudocode

```c
__int64 __fastcall CAVIStreamParser::ValidateStreamLength(CAVIStreamParser *this)
{
  unsigned int v2; // r14d
  __int64 v3; // rdx
  __int64 v4; // rcx
  wchar_t *v5; // rcx
  signed int StreamLength; // edi
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  int v19; // ebx
  CAVIidx1Index *v20; // r12
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  wchar_t *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  int v37; // r15d
  __int64 v38; // r13
  int v39; // ebx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rdx
  int StreamNumberFromDataChunkID; // ebx
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  int NextIndexEntry; // ebx
  __int64 v50; // rdx
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  WAVEFORMATEX *ppWF; // [rsp+30h] [rbp-18h] BYREF
  IMFMediaType *pMFType; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v57; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v58; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v59; // [rsp+A0h] [rbp+58h] BYREF

  pMFType = 0;
  v2 = 0;
  ppWF = 0;
  v59 = 0;
  v58 = 0;
  if ( *((_DWORD *)this + 144) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v57, "CAVIStreamParser::ValidateStreamLength", 193);
    v4 = *((_QWORD *)this + 71);
    if ( !v4 )
    {
      v5 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamLength = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v5 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v5 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v5 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CAVIStreamParser::ValidateStreamLength",
            193,
            -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_124;
      v9 = 18;
      goto LABEL_13;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4) != 1 )
    {
      v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamLength = -2147418113;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v13, "CAVIStreamParser::ValidateStreamLength", 197, -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_124;
      v9 = 19;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
        this,
        -2147418113);
      goto LABEL_124;
    }
    StreamLength = CODMLSuperIndex::GetStreamLength(*((CODMLSuperIndex **)this + 71), &v59);
    if ( StreamLength < 0 )
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
        CallStackTracing::s_wpInstance = v16;
        if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
        {
          v15 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = &qword_1801B97E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != StreamLength )
          CallStackContext::TraceFailure(v17, "CAVIStreamParser::ValidateStreamLength", 201, StreamLength);
      }
      if ( !g_wppLevels )
        goto LABEL_124;
      v18 = 20;
      goto LABEL_123;
    }
    v2 = v59;
  }
  else
  {
    v19 = *((_DWORD *)this + 2);
    v20 = *(CAVIidx1Index **)(*((_QWORD *)this + 9) + 16LL);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v57, "CAVIStreamParser::ValidateStreamLength", 208);
    if ( !v20 )
    {
      v22 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamLength = -1072875854;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21);
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
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v24, "CAVIStreamParser::ValidateStreamLength", 208, -1072875854);
      }
      if ( !g_wppLevels )
        goto LABEL_124;
      v18 = 21;
      goto LABEL_123;
    }
    if ( !(unsigned int)CAVIidx1Index::FindNextIndexEntry(v20, *((_DWORD *)this + 21), 0, &v58, 1) )
    {
      v26 = (wchar_t *)CallStackTracing::s_wpInstance;
      StreamLength = -1072875842;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v28, "CAVIStreamParser::ValidateStreamLength", 215, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_124;
      v18 = 22;
      goto LABEL_123;
    }
    if ( v19 == 1935963489 )
    {
      StreamLength = (*(__int64 (__fastcall **)(CAVIStreamParser *, IMFMediaType **))(*(_QWORD *)this + 48LL))(
                       this,
                       &pMFType);
      if ( StreamLength < 0 )
      {
        v30 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29);
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
          if ( *((_DWORD *)v32 + 499) != StreamLength )
            CallStackContext::TraceFailure(v32, "CAVIStreamParser::ValidateStreamLength", 220, StreamLength);
        }
        if ( !g_wppLevels )
          goto LABEL_124;
        v18 = 23;
        goto LABEL_123;
      }
      v59 = MFCreateWaveFormatExFromMFMediaType(pMFType, &ppWF, 0, 0);
      StreamLength = v59;
      if ( (v59 & 0x80000000) != 0 )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
          CallStackTracing::s_wpInstance = v35;
          if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
          {
            v34 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v34 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != StreamLength )
            CallStackContext::TraceFailure(v36, "CAVIStreamParser::ValidateStreamLength", 221, StreamLength);
        }
        if ( !g_wppLevels )
          goto LABEL_124;
        v18 = 24;
        goto LABEL_123;
      }
    }
    else
    {
      v59 = 0;
    }
    v37 = v19;
    do
    {
      v38 = v58;
      v39 = *(_DWORD *)(*(_QWORD *)v20 + 16LL * v58 + 12);
      if ( (*(unsigned int (__fastcall **)(CAVIStreamParser *, _QWORD))(*(_QWORD *)this + 120LL))(
             this,
             *(unsigned int *)(*(_QWORD *)v20 + 16LL * v58)) )
      {
        if ( v37 == 1935963489 && ppWF->nBlockAlign )
          v2 += (v39 + (unsigned int)ppWF->nBlockAlign - 1) / ppWF->nBlockAlign;
        else
          ++v2;
      }
      v40 = CallStackTracing::s_wpInstance;
      v57 = 0;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v40 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        v42 = *((unsigned int *)v41 + 497);
        if ( (unsigned int)v42 < *((_DWORD *)v41 + 498) )
        {
          v43 = 2 * v42;
          *((_QWORD *)v41 + v43) = "CAVIidx1Index::GetNextIndexEntry";
          *((_DWORD *)v41 + 2 * v43 + 2) = 490;
        }
        ++*((_DWORD *)v41 + 497);
      }
      StreamNumberFromDataChunkID = GetStreamNumberFromDataChunkID(*(_DWORD *)(*(_QWORD *)v20 + 16 * v38), &v57);
      if ( StreamNumberFromDataChunkID >= 0 )
      {
        LODWORD(v38) = v38 + 1;
      }
      else
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
          if ( *((_DWORD *)v48 + 499) != StreamNumberFromDataChunkID )
            CallStackContext::TraceFailure(v48, "CAVIidx1Index::GetNextIndexEntry", 490, StreamNumberFromDataChunkID);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            &WPP_deea3ab0e8a03b65a437603afa377d04_Traceguids,
            v20,
            StreamNumberFromDataChunkID);
      }
      NextIndexEntry = CAVIidx1Index::FindNextIndexEntry(v20, v57, v38, &v58, 1);
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
    }
    while ( NextIndexEntry );
    StreamLength = v59;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
  if ( v2 == *((_DWORD *)this + 10) )
    goto LABEL_125;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v57, "CAVIStreamParser::ValidateStreamLength", 249);
  if ( (unsigned __int8)byte_1801BA109 >= 8u )
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      25,
      &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
      this,
      *((_DWORD *)this + 10),
      v2);
  *((_DWORD *)this + 10) = v2;
  StreamLength = CAVIStreamParser::SetStreamStartTimeAndLength(this);
  if ( StreamLength < 0 )
  {
    v51 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50);
      CallStackTracing::s_wpInstance = v52;
      if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
      {
        v51 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v51 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v51 + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
      if ( *((_DWORD *)v53 + 499) != StreamLength )
        CallStackContext::TraceFailure(v53, "CAVIStreamParser::ValidateStreamLength", 251, StreamLength);
    }
    if ( g_wppLevels )
    {
      v18 = 26;
LABEL_123:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
        this,
        StreamLength);
    }
  }
LABEL_124:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
LABEL_125:
  CoTaskMemFree(ppWF);
  ppWF = 0;
  if ( pMFType )
    ((void (__fastcall *)(IMFMediaType *))pMFType->lpVtbl->Release)(pMFType);
  return (unsigned int)StreamLength;
}

```

## disassembly

```asm
0x18004ae78  push    rbp
0x18004ae7a  push    rbx
0x18004ae7b  push    rsi
0x18004ae7c  push    rdi
0x18004ae7d  push    r12
0x18004ae7f  push    r13
0x18004ae81  push    r14
0x18004ae83  push    r15
0x18004ae85  mov     rbp, rsp
0x18004ae88  sub     rsp, 48h
0x18004ae8c  xor     r13d, r13d
0x18004ae8f  lea     r15, aCavistreampars_13; "CAVIStreamParser::ValidateStreamLength"
0x18004ae96  mov     rsi, rcx
0x18004ae99  mov     [rbp+pMFType], r13
0x18004ae9d  mov     r14d, r13d
0x18004aea0  mov     [rbp+ppWF], r13
0x18004aea4  mov     r12d, 7F0h
0x18004aeaa  mov     [rbp+arg_10], r13d
0x18004aeae  mov     rdx, r15; char *
0x18004aeb1  mov     [rbp+arg_8], r13d
0x18004aeb5  cmp     [rcx+240h], r13d
0x18004aebc  jz      loc_18004B0D8
0x18004aec2  mov     r14d, 0C1h
0x18004aec8  lea     rcx, [rbp+arg_0]; this
0x18004aecc  mov     r8d, r14d; int
0x18004aecf  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004aed4  mov     rcx, [rsi+238h]
0x18004aedb  test    rcx, rcx
0x18004aede  jnz     loc_18004AF7B
0x18004aee4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004aeeb  mov     ebx, 8000FFFFh
0x18004aef0  mov     edi, ebx
0x18004aef2  test    rcx, rcx
0x18004aef5  jnz     short loc_18004AF3C
0x18004aef7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004aefe  nop     dword ptr [rax+rax+00h]
0x18004af03  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af0a  mov     rcx, rax
0x18004af0d  test    rax, rax
0x18004af10  jz      short loc_18004AF2E
0x18004af12  mov     rax, [rax]
0x18004af15  mov     edx, r12d
0x18004af18  mov     rax, [rax+8]
0x18004af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af21  test    eax, eax
0x18004af23  jz      short loc_18004AF2E
0x18004af25  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af2c  jmp     short loc_18004AF3C
0x18004af2e  lea     rcx, qword_1801B97E0; this
0x18004af35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af3c  cmp     [rcx+8], r13b
0x18004af40  jz      short loc_18004AF60
0x18004af42  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004af47  cmp     [rax+7CCh], ebx
0x18004af4d  jz      short loc_18004AF60
0x18004af4f  mov     r9d, ebx; int
0x18004af52  mov     r8d, r14d; int
0x18004af55  mov     rdx, r15; char *
0x18004af58  mov     rcx, rax; this
0x18004af5b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004af60  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004af67  jb      loc_18004B686
0x18004af6d  mov     edx, 12h
0x18004af72  mov     [rsp+48h+var_28], ebx
0x18004af76  jmp     loc_18004B66C
0x18004af7b  mov     rax, [rcx]
0x18004af7e  mov     rax, [rax+8]
0x18004af82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af87  cmp     eax, 1
0x18004af8a  jz      loc_18004B026
0x18004af90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af97  mov     ebx, 8000FFFFh
0x18004af9c  mov     edi, ebx
0x18004af9e  test    rcx, rcx
0x18004afa1  jnz     short loc_18004AFE8
0x18004afa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004afaa  nop     dword ptr [rax+rax+00h]
0x18004afaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afb6  mov     rcx, rax
0x18004afb9  test    rax, rax
0x18004afbc  jz      short loc_18004AFDA
0x18004afbe  mov     rax, [rax]
0x18004afc1  mov     edx, r12d
0x18004afc4  mov     rax, [rax+8]
0x18004afc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afcd  test    eax, eax
0x18004afcf  jz      short loc_18004AFDA
0x18004afd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afd8  jmp     short loc_18004AFE8
0x18004afda  lea     rcx, qword_1801B97E0; this
0x18004afe1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004afe8  cmp     [rcx+8], r13b
0x18004afec  jz      short loc_18004B00F
0x18004afee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004aff3  cmp     [rax+7CCh], ebx
0x18004aff9  jz      short loc_18004B00F
0x18004affb  mov     r9d, ebx; int
0x18004affe  mov     r8d, 0C5h; int
0x18004b004  mov     rdx, r15; char *
0x18004b007  mov     rcx, rax; this
0x18004b00a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b00f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b016  jb      loc_18004B686
0x18004b01c  mov     edx, 13h
0x18004b021  jmp     loc_18004AF72
0x18004b026  mov     rcx, [rsi+238h]; this
0x18004b02d  lea     rdx, [rbp+arg_10]; unsigned int *
0x18004b031  call    ?GetStreamLength@CODMLSuperIndex@@QEBAJPEAK@Z; CODMLSuperIndex::GetStreamLength(ulong *)
0x18004b036  mov     edi, eax
0x18004b038  test    eax, eax
0x18004b03a  jns     loc_18004B0CF
0x18004b040  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b047  test    rcx, rcx
0x18004b04a  jnz     short loc_18004B091
0x18004b04c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b053  nop     dword ptr [rax+rax+00h]
0x18004b058  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b05f  mov     rcx, rax
0x18004b062  test    rax, rax
0x18004b065  jz      short loc_18004B083
0x18004b067  mov     rax, [rax]
0x18004b06a  mov     edx, r12d
0x18004b06d  mov     rax, [rax+8]
0x18004b071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b076  test    eax, eax
0x18004b078  jz      short loc_18004B083
0x18004b07a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b081  jmp     short loc_18004B091
0x18004b083  lea     rcx, qword_1801B97E0; this
0x18004b08a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b091  cmp     [rcx+8], r13b
0x18004b095  jz      short loc_18004B0B8
0x18004b097  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b09c  cmp     [rax+7CCh], edi
0x18004b0a2  jz      short loc_18004B0B8
0x18004b0a4  mov     r9d, edi; int
0x18004b0a7  mov     r8d, 0C9h; int
0x18004b0ad  mov     rdx, r15; char *
0x18004b0b0  mov     rcx, rax; this
0x18004b0b3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b0b8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b0bf  jb      loc_18004B686
0x18004b0c5  mov     edx, 14h
0x18004b0ca  jmp     loc_18004B668
0x18004b0cf  mov     r14d, [rbp+arg_10]
0x18004b0d3  jmp     loc_18004B573
0x18004b0d8  mov     rax, [rcx+48h]
0x18004b0dc  mov     r8d, 0D0h; int
0x18004b0e2  mov     ebx, [rcx+8]
0x18004b0e5  lea     rcx, [rbp+arg_0]; this
0x18004b0e9  mov     r12, [rax+10h]
0x18004b0ed  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b0f2  test    r12, r12
0x18004b0f5  jnz     loc_18004B191
0x18004b0fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b102  mov     edi, 0C00D36B2h
0x18004b107  test    rcx, rcx
0x18004b10a  jnz     short loc_18004B153
0x18004b10c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b113  nop     dword ptr [rax+rax+00h]
0x18004b118  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b11f  mov     rcx, rax
0x18004b122  test    rax, rax
0x18004b125  jz      short loc_18004B145
0x18004b127  mov     rax, [rax]
0x18004b12a  mov     edx, 7F0h
0x18004b12f  mov     rax, [rax+8]
0x18004b133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b138  test    eax, eax
0x18004b13a  jz      short loc_18004B145
0x18004b13c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b143  jmp     short loc_18004B153
0x18004b145  lea     rcx, qword_1801B97E0; this
0x18004b14c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b153  cmp     [rcx+8], r13b
0x18004b157  jz      short loc_18004B17A
0x18004b159  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b15e  cmp     [rax+7CCh], edi
0x18004b164  jz      short loc_18004B17A
0x18004b166  mov     r9d, edi; int
0x18004b169  mov     r8d, 0D0h; int
0x18004b16f  mov     rdx, r15; char *
0x18004b172  mov     rcx, rax; this
0x18004b175  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b17a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b181  jb      loc_18004B686
0x18004b187  mov     edx, 15h
0x18004b18c  jmp     loc_18004B668
0x18004b191  mov     edx, [rsi+54h]; unsigned int
0x18004b194  lea     r9, [rbp+arg_8]; unsigned int *
0x18004b198  xor     r8d, r8d; unsigned int
0x18004b19b  mov     [rsp+48h+var_28], 1; int
0x18004b1a3  mov     rcx, r12; this
0x18004b1a6  call    ?FindNextIndexEntry@CAVIidx1Index@@AEBAHKKPEAKH@Z; CAVIidx1Index::FindNextIndexEntry(ulong,ulong,ulong *,int)
0x18004b1ab  test    eax, eax
0x18004b1ad  jnz     loc_18004B249
0x18004b1b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b1ba  mov     edi, 0C00D36BEh
0x18004b1bf  test    rcx, rcx
0x18004b1c2  jnz     short loc_18004B20B
0x18004b1c4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b1cb  nop     dword ptr [rax+rax+00h]
0x18004b1d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b1d7  mov     rcx, rax
0x18004b1da  test    rax, rax
0x18004b1dd  jz      short loc_18004B1FD
0x18004b1df  mov     rax, [rax]
0x18004b1e2  mov     edx, 7F0h
0x18004b1e7  mov     rax, [rax+8]
0x18004b1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1f0  test    eax, eax
0x18004b1f2  jz      short loc_18004B1FD
0x18004b1f4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b1fb  jmp     short loc_18004B20B
0x18004b1fd  lea     rcx, qword_1801B97E0; this
0x18004b204  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b20b  cmp     [rcx+8], r13b
0x18004b20f  jz      short loc_18004B232
0x18004b211  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b216  cmp     [rax+7CCh], edi
0x18004b21c  jz      short loc_18004B232
0x18004b21e  mov     r9d, edi; int
0x18004b221  mov     r8d, 0D7h; int
0x18004b227  mov     rdx, r15; char *
0x18004b22a  mov     rcx, rax; this
0x18004b22d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b232  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b239  jb      loc_18004B686
0x18004b23f  mov     edx, 16h
0x18004b244  jmp     loc_18004B668
0x18004b249  cmp     ebx, 73647561h
0x18004b24f  jnz     loc_18004B3BB
0x18004b255  mov     rax, [rsi]
0x18004b258  lea     rdx, [rbp+pMFType]
0x18004b25c  mov     rcx, rsi
0x18004b25f  mov     rax, [rax+30h]
0x18004b263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b268  mov     edi, eax
0x18004b26a  test    eax, eax
0x18004b26c  jns     loc_18004B303
0x18004b272  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b279  test    rcx, rcx
0x18004b27c  jnz     short loc_18004B2C5
0x18004b27e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b285  nop     dword ptr [rax+rax+00h]
0x18004b28a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b291  mov     rcx, rax
0x18004b294  test    rax, rax
0x18004b297  jz      short loc_18004B2B7
0x18004b299  mov     rax, [rax]
0x18004b29c  mov     edx, 7F0h
0x18004b2a1  mov     rax, [rax+8]
0x18004b2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2aa  test    eax, eax
0x18004b2ac  jz      short loc_18004B2B7
0x18004b2ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2b5  jmp     short loc_18004B2C5
0x18004b2b7  lea     rcx, qword_1801B97E0; this
0x18004b2be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2c5  cmp     [rcx+8], r13b
0x18004b2c9  jz      short loc_18004B2EC
0x18004b2cb  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b2d0  cmp     [rax+7CCh], edi
0x18004b2d6  jz      short loc_18004B2EC
0x18004b2d8  mov     r9d, edi; int
0x18004b2db  mov     r8d, 0DCh; int
0x18004b2e1  mov     rdx, r15; char *
0x18004b2e4  mov     rcx, rax; this
0x18004b2e7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b2ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b2f3  jb      loc_18004B686
0x18004b2f9  mov     edx, 17h
0x18004b2fe  jmp     loc_18004B668
0x18004b303  mov     rcx, [rbp+pMFType]; pMFType
0x18004b307  lea     rdx, [rbp+ppWF]; ppWF
0x18004b30b  xor     r9d, r9d; Flags
0x18004b30e  xor     r8d, r8d; pcbSize
0x18004b311  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18004b318  nop     dword ptr [rax+rax+00h]
0x18004b31d  mov     [rbp+arg_10], eax
0x18004b320  mov     edi, eax
0x18004b322  test    eax, eax
0x18004b324  jns     loc_18004B3BF
0x18004b32a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b331  test    rcx, rcx
0x18004b334  jnz     short loc_18004B37D
0x18004b336  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b33d  nop     dword ptr [rax+rax+00h]
0x18004b342  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b349  mov     rcx, rax
0x18004b34c  test    rax, rax
0x18004b34f  jz      short loc_18004B36F
0x18004b351  mov     rax, [rax]
0x18004b354  mov     edx, 7F0h
0x18004b359  mov     rax, [rax+8]
0x18004b35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b362  test    eax, eax
0x18004b364  jz      short loc_18004B36F
0x18004b366  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b36d  jmp     short loc_18004B37D
  ... truncated ...
```
