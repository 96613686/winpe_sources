# CAVIStreamParser::ValidateStreamLength(void)

- ea: `0x180050fb0`
- end: `0x180051681`
- name: `?ValidateStreamLength@CAVIStreamParser@@QEAAJXZ`
- size: `1745`
- prototype: `__int64 __fastcall(CAVIStreamParser *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801365f8`

## callees

- `0x18000e0c0`
- `0x18000e1a4`
- `0x180010190`
- `0x180010258`
- `0x18001303c`
- `0x180018b90`
- `0x180050fb0`
- `0x180073b14`
- `0x1800e7af8`
- `0x180138540`
- `0x180139144`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051029`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800510d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051176`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051232`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800512e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800515ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051029`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800510d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051176`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051232`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800512e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051399`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180051442`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800515ae`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180051426`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180051426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005164f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005164f`

## pseudocode

```c
__int64 __fastcall CAVIStreamParser::ValidateStreamLength(CAVIStreamParser *this)
{
  unsigned int v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  wchar_t *v5; // rcx
  HRESULT StreamLength; // ebx
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
  int v19; // r12d
  CAVIidx1Index *v20; // r15
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
  int v37; // r13d
  __int64 v38; // rdx
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  IMFMediaType *pMFType; // [rsp+30h] [rbp-18h] BYREF
  char v44; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v45; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v46; // [rsp+A0h] [rbp+58h] BYREF
  WAVEFORMATEX *ppWF; // [rsp+A8h] [rbp+60h] BYREF

  pMFType = 0;
  v2 = 0;
  ppWF = 0;
  v46 = 0;
  v45 = 0;
  if ( *((_DWORD *)this + 144) )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CAVIStreamParser::ValidateStreamLength", 193);
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
          v5 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        goto LABEL_104;
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
          v11 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != -2147418113 )
          CallStackContext::TraceFailure(v13, "CAVIStreamParser::ValidateStreamLength", 197, -2147418113);
      }
      if ( !g_wppLevels )
        goto LABEL_104;
      v9 = 19;
LABEL_13:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
        this,
        -2147418113);
      goto LABEL_104;
    }
    StreamLength = CODMLSuperIndex::GetStreamLength(*((CODMLSuperIndex **)this + 71), &v46);
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
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v15 + 8) )
      {
        v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
        if ( *((_DWORD *)v17 + 499) != StreamLength )
          CallStackContext::TraceFailure(v17, "CAVIStreamParser::ValidateStreamLength", 201, StreamLength);
      }
      if ( !g_wppLevels )
        goto LABEL_104;
      v18 = 20;
      goto LABEL_103;
    }
    v2 = v46;
  }
  else
  {
    v19 = *((_DWORD *)this + 2);
    v20 = *(CAVIidx1Index **)(*((_QWORD *)this + 9) + 16LL);
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CAVIStreamParser::ValidateStreamLength", 208);
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
          v22 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v22 + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
        if ( *((_DWORD *)v24 + 499) != -1072875854 )
          CallStackContext::TraceFailure(v24, "CAVIStreamParser::ValidateStreamLength", 208, -1072875854);
      }
      if ( !g_wppLevels )
        goto LABEL_104;
      v18 = 21;
      goto LABEL_103;
    }
    if ( !(unsigned int)CAVIidx1Index::FindNextIndexEntry(v20, *((_DWORD *)this + 21), 0, &v45, 1) )
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
          v26 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v28 + 499) != -1072875842 )
          CallStackContext::TraceFailure(v28, "CAVIStreamParser::ValidateStreamLength", 215, -1072875842);
      }
      if ( !g_wppLevels )
        goto LABEL_104;
      v18 = 22;
      goto LABEL_103;
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
            v30 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != StreamLength )
            CallStackContext::TraceFailure(v32, "CAVIStreamParser::ValidateStreamLength", 220, StreamLength);
        }
        if ( !g_wppLevels )
          goto LABEL_104;
        v18 = 23;
        goto LABEL_103;
      }
      StreamLength = MFCreateWaveFormatExFromMFMediaType(pMFType, &ppWF, 0, 0);
      if ( StreamLength < 0 )
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
            v34 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
          if ( *((_DWORD *)v36 + 499) != StreamLength )
            CallStackContext::TraceFailure(v36, "CAVIStreamParser::ValidateStreamLength", 221, StreamLength);
        }
        if ( !g_wppLevels )
          goto LABEL_104;
        v18 = 24;
        goto LABEL_103;
      }
    }
    else
    {
      StreamLength = 0;
    }
    do
    {
      v37 = *(_DWORD *)(*(_QWORD *)v20 + 16LL * v45 + 12);
      if ( (*(unsigned int (__fastcall **)(CAVIStreamParser *, _QWORD))(*(_QWORD *)this + 120LL))(
             this,
             *(unsigned int *)(*(_QWORD *)v20 + 16LL * v45)) )
      {
        if ( v19 == 1935963489 && ppWF->nBlockAlign )
          v2 += (v37 + (unsigned int)ppWF->nBlockAlign - 1) / ppWF->nBlockAlign;
        else
          ++v2;
      }
    }
    while ( (unsigned int)CAVIidx1Index::GetNextIndexEntry(v20, v45, &v45, 1) );
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  if ( v2 == *((_DWORD *)this + 10) )
    goto LABEL_105;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CAVIStreamParser::ValidateStreamLength", 249);
  if ( (unsigned __int8)byte_1801B1109 >= 8u )
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
    v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
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
      if ( *((_DWORD *)v41 + 499) != StreamLength )
        CallStackContext::TraceFailure(v41, "CAVIStreamParser::ValidateStreamLength", 251, StreamLength);
    }
    if ( g_wppLevels )
    {
      v18 = 26;
LABEL_103:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        &WPP_84f618ec34f9330309cc271626c14d28_Traceguids,
        this,
        StreamLength);
    }
  }
LABEL_104:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
LABEL_105:
  CoTaskMemFree(ppWF);
  ppWF = 0;
  if ( pMFType )
    ((void (__fastcall *)(IMFMediaType *))pMFType->lpVtbl->Release)(pMFType);
  return (unsigned int)StreamLength;
}

```

## disassembly

```asm
0x180050fb0  push    rbp
0x180050fb2  push    rbx
0x180050fb3  push    rsi
0x180050fb4  push    rdi
0x180050fb5  push    r12
0x180050fb7  push    r13
0x180050fb9  push    r14
0x180050fbb  push    r15
0x180050fbd  mov     rbp, rsp
0x180050fc0  sub     rsp, 48h
0x180050fc4  xor     r13d, r13d
0x180050fc7  lea     r14, aCavistreampars_13; "CAVIStreamParser::ValidateStreamLength"
0x180050fce  mov     rdi, rcx
0x180050fd1  mov     [rbp+pMFType], r13
0x180050fd5  mov     esi, r13d
0x180050fd8  mov     [rbp+ppWF], r13
0x180050fdc  mov     rdx, r14; char *
0x180050fdf  mov     [rbp+arg_10], r13d
0x180050fe3  mov     [rbp+arg_8], r13d
0x180050fe7  cmp     [rcx+240h], r13d
0x180050fee  jz      loc_1800511FD
0x180050ff4  mov     r15d, 0C1h
0x180050ffa  lea     rcx, [rbp+arg_0]; this
0x180050ffe  mov     r8d, r15d; int
0x180051001  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180051006  mov     rcx, [rdi+238h]
0x18005100d  test    rcx, rcx
0x180051010  jnz     loc_1800510A9
0x180051016  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005101d  mov     esi, 8000FFFFh
0x180051022  mov     ebx, esi
0x180051024  test    rcx, rcx
0x180051027  jnz     short loc_18005106A
0x180051029  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005102f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051036  mov     rcx, rax
0x180051039  test    rax, rax
0x18005103c  jz      short loc_18005105C
0x18005103e  mov     rax, [rax]
0x180051041  mov     edx, 7F0h
0x180051046  mov     rax, [rax+8]
0x18005104a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005104f  test    eax, eax
0x180051051  jz      short loc_18005105C
0x180051053  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005105a  jmp     short loc_18005106A
0x18005105c  lea     rcx, qword_1801B07E0; this
0x180051063  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005106a  cmp     [rcx+8], r13b
0x18005106e  jz      short loc_18005108E
0x180051070  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051075  cmp     [rax+7CCh], esi
0x18005107b  jz      short loc_18005108E
0x18005107d  mov     r9d, esi; int
0x180051080  mov     r8d, r15d; int
0x180051083  mov     rdx, r14; char *
0x180051086  mov     rcx, rax; this
0x180051089  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005108e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051095  jb      loc_180051642
0x18005109b  mov     edx, 12h
0x1800510a0  mov     [rsp+48h+var_28], esi
0x1800510a4  jmp     loc_180051628
0x1800510a9  mov     rax, [rcx]
0x1800510ac  mov     rax, [rax+8]
0x1800510b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510b5  cmp     eax, 1
0x1800510b8  jz      loc_180051150
0x1800510be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800510c5  mov     esi, 8000FFFFh
0x1800510ca  mov     ebx, esi
0x1800510cc  test    rcx, rcx
0x1800510cf  jnz     short loc_180051112
0x1800510d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800510d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800510de  mov     rcx, rax
0x1800510e1  test    rax, rax
0x1800510e4  jz      short loc_180051104
0x1800510e6  mov     rax, [rax]
0x1800510e9  mov     edx, 7F0h
0x1800510ee  mov     rax, [rax+8]
0x1800510f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510f7  test    eax, eax
0x1800510f9  jz      short loc_180051104
0x1800510fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051102  jmp     short loc_180051112
0x180051104  lea     rcx, qword_1801B07E0; this
0x18005110b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051112  cmp     [rcx+8], r13b
0x180051116  jz      short loc_180051139
0x180051118  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005111d  cmp     [rax+7CCh], esi
0x180051123  jz      short loc_180051139
0x180051125  mov     r9d, esi; int
0x180051128  mov     r8d, 0C5h; int
0x18005112e  mov     rdx, r14; char *
0x180051131  mov     rcx, rax; this
0x180051134  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051139  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051140  jb      loc_180051642
0x180051146  mov     edx, 13h
0x18005114b  jmp     loc_1800510A0
0x180051150  mov     rcx, [rdi+238h]; this
0x180051157  lea     rdx, [rbp+arg_10]; unsigned int *
0x18005115b  call    ?GetStreamLength@CODMLSuperIndex@@QEBAJPEAK@Z; CODMLSuperIndex::GetStreamLength(ulong *)
0x180051160  mov     ebx, eax
0x180051162  test    eax, eax
0x180051164  jns     loc_1800511F5
0x18005116a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051171  test    rcx, rcx
0x180051174  jnz     short loc_1800511B7
0x180051176  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005117c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180051183  mov     rcx, rax
0x180051186  test    rax, rax
0x180051189  jz      short loc_1800511A9
0x18005118b  mov     rax, [rax]
0x18005118e  mov     edx, 7F0h
0x180051193  mov     rax, [rax+8]
0x180051197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005119c  test    eax, eax
0x18005119e  jz      short loc_1800511A9
0x1800511a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800511a7  jmp     short loc_1800511B7
0x1800511a9  lea     rcx, qword_1801B07E0; this
0x1800511b0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800511b7  cmp     [rcx+8], r13b
0x1800511bb  jz      short loc_1800511DE
0x1800511bd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800511c2  cmp     [rax+7CCh], ebx
0x1800511c8  jz      short loc_1800511DE
0x1800511ca  mov     r9d, ebx; int
0x1800511cd  mov     r8d, 0C9h; int
0x1800511d3  mov     rdx, r14; char *
0x1800511d6  mov     rcx, rax; this
0x1800511d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800511de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800511e5  jb      loc_180051642
0x1800511eb  mov     edx, 14h
0x1800511f0  jmp     loc_180051624
0x1800511f5  mov     esi, [rbp+arg_10]
0x1800511f8  jmp     loc_180051536
0x1800511fd  mov     rax, [rcx+48h]
0x180051201  mov     r8d, 0D0h; int
0x180051207  mov     r12d, [rcx+8]
0x18005120b  lea     rcx, [rbp+arg_0]; this
0x18005120f  mov     r15, [rax+10h]
0x180051213  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180051218  test    r15, r15
0x18005121b  jnz     loc_1800512B1
0x180051221  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051228  mov     ebx, 0C00D36B2h
0x18005122d  test    rcx, rcx
0x180051230  jnz     short loc_180051273
0x180051232  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051238  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005123f  mov     rcx, rax
0x180051242  test    rax, rax
0x180051245  jz      short loc_180051265
0x180051247  mov     rax, [rax]
0x18005124a  mov     edx, 7F0h
0x18005124f  mov     rax, [rax+8]
0x180051253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051258  test    eax, eax
0x18005125a  jz      short loc_180051265
0x18005125c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051263  jmp     short loc_180051273
0x180051265  lea     rcx, qword_1801B07E0; this
0x18005126c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051273  cmp     [rcx+8], r13b
0x180051277  jz      short loc_18005129A
0x180051279  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005127e  cmp     [rax+7CCh], ebx
0x180051284  jz      short loc_18005129A
0x180051286  mov     r9d, ebx; int
0x180051289  mov     r8d, 0D0h; int
0x18005128f  mov     rdx, r14; char *
0x180051292  mov     rcx, rax; this
0x180051295  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005129a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800512a1  jb      loc_180051642
0x1800512a7  mov     edx, 15h
0x1800512ac  jmp     loc_180051624
0x1800512b1  mov     edx, [rdi+54h]; unsigned int
0x1800512b4  lea     r9, [rbp+arg_8]; unsigned int *
0x1800512b8  xor     r8d, r8d; unsigned int
0x1800512bb  mov     [rsp+48h+var_28], 1; int
0x1800512c3  mov     rcx, r15; this
0x1800512c6  call    ?FindNextIndexEntry@CAVIidx1Index@@AEBAHKKPEAKH@Z; CAVIidx1Index::FindNextIndexEntry(ulong,ulong,ulong *,int)
0x1800512cb  test    eax, eax
0x1800512cd  jnz     loc_180051363
0x1800512d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800512da  mov     ebx, 0C00D36BEh
0x1800512df  test    rcx, rcx
0x1800512e2  jnz     short loc_180051325
0x1800512e4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800512ea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800512f1  mov     rcx, rax
0x1800512f4  test    rax, rax
0x1800512f7  jz      short loc_180051317
0x1800512f9  mov     rax, [rax]
0x1800512fc  mov     edx, 7F0h
0x180051301  mov     rax, [rax+8]
0x180051305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005130a  test    eax, eax
0x18005130c  jz      short loc_180051317
0x18005130e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051315  jmp     short loc_180051325
0x180051317  lea     rcx, qword_1801B07E0; this
0x18005131e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051325  cmp     [rcx+8], r13b
0x180051329  jz      short loc_18005134C
0x18005132b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180051330  cmp     [rax+7CCh], ebx
0x180051336  jz      short loc_18005134C
0x180051338  mov     r9d, ebx; int
0x18005133b  mov     r8d, 0D7h; int
0x180051341  mov     rdx, r14; char *
0x180051344  mov     rcx, rax; this
0x180051347  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005134c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051353  jb      loc_180051642
0x180051359  mov     edx, 16h
0x18005135e  jmp     loc_180051624
0x180051363  cmp     r12d, 73647561h
0x18005136a  jnz     loc_1800514C1
0x180051370  mov     rax, [rdi]
0x180051373  lea     rdx, [rbp+pMFType]
0x180051377  mov     rcx, rdi
0x18005137a  mov     rax, [rax+30h]
0x18005137e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051383  mov     ebx, eax
0x180051385  test    eax, eax
0x180051387  jns     loc_180051418
0x18005138d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051394  test    rcx, rcx
0x180051397  jnz     short loc_1800513DA
0x180051399  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005139f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800513a6  mov     rcx, rax
0x1800513a9  test    rax, rax
0x1800513ac  jz      short loc_1800513CC
0x1800513ae  mov     rax, [rax]
0x1800513b1  mov     edx, 7F0h
0x1800513b6  mov     rax, [rax+8]
0x1800513ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800513bf  test    eax, eax
0x1800513c1  jz      short loc_1800513CC
0x1800513c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800513ca  jmp     short loc_1800513DA
0x1800513cc  lea     rcx, qword_1801B07E0; this
0x1800513d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800513da  cmp     [rcx+8], r13b
0x1800513de  jz      short loc_180051401
0x1800513e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800513e5  cmp     [rax+7CCh], ebx
0x1800513eb  jz      short loc_180051401
0x1800513ed  mov     r9d, ebx; int
0x1800513f0  mov     r8d, 0DCh; int
0x1800513f6  mov     rdx, r14; char *
0x1800513f9  mov     rcx, rax; this
0x1800513fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180051401  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180051408  jb      loc_180051642
0x18005140e  mov     edx, 17h
0x180051413  jmp     loc_180051624
0x180051418  mov     rcx, [rbp+pMFType]; pMFType
0x18005141c  lea     rdx, [rbp+ppWF]; ppWF
0x180051420  xor     r9d, r9d; Flags
0x180051423  xor     r8d, r8d; pcbSize
0x180051426  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18005142c  mov     ebx, eax
0x18005142e  test    eax, eax
0x180051430  jns     loc_1800514C4
0x180051436  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005143d  test    rcx, rcx
0x180051440  jnz     short loc_180051483
0x180051442  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180051448  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005144f  mov     rcx, rax
0x180051452  test    rax, rax
0x180051455  jz      short loc_180051475
0x180051457  mov     rax, [rax]
0x18005145a  mov     edx, 7F0h
0x18005145f  mov     rax, [rax+8]
0x180051463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051468  test    eax, eax
0x18005146a  jz      short loc_180051475
0x18005146c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180051473  jmp     short loc_180051483
0x180051475  lea     rcx, qword_1801B07E0; this
0x18005147c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180051483  cmp     [rcx+8], r13b
0x180051487  jz      short loc_1800514AA
0x180051489  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005148e  cmp     [rax+7CCh], ebx
0x180051494  jz      short loc_1800514AA
0x180051496  mov     r9d, ebx; int
0x180051499  mov     r8d, 0DDh; int
0x18005149f  mov     rdx, r14; char *
  ... truncated ...
```
