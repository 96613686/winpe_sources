# CAVIIAVSStreamParser::CreateAudioFormatChange(tWAVEFORMATEX *,IMFSample * *)

- ea: `0x18013da20`
- end: `0x18013ddfa`
- name: `?CreateAudioFormatChange@CAVIIAVSStreamParser@@AEAAJPEAUtWAVEFORMATEX@@PEAPEAUIMFSample@@@Z`
- size: `986`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *this, struct tWAVEFORMATEX *, struct IMFSample **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18013cf30`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180034d10`
- `0x180073b14`
- `0x18013da20`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013da80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013db2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dbca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dc89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dd3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013da80`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013db2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dbca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dc89`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18013dd3c`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013db10`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18013db10`
- `MFPlat!MFCreateSample` at `0x18013dbae`
- `MFPlat!MFCreateSample` at `0x18013dbae`
- `MFPlat!MFCreateMediaType` at `0x18013da64`
- `MFPlat!MFCreateMediaType` at `0x18013da64`

## string_xrefs

- `0x18013da36`: `CAVIIAVSStreamParser::CreateAudioFormatChange`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::CreateAudioFormatChange(
        CAVIIAVSStreamParser *this,
        struct tWAVEFORMATEX *a2,
        struct IMFSample **a3)
{
  __int64 v6; // rdx
  HRESULT v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  wchar_t *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  IMFSample *v26; // rdi
  HRESULT (__stdcall *SetSampleTime)(IMFSample *, LONGLONG); // rbx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  wchar_t *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  wchar_t *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v42; // [rsp+50h] [rbp+8h] BYREF
  IMFMediaType *ppMFType; // [rsp+68h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v42,
    "CAVIIAVSStreamParser::CreateAudioFormatChange",
    138);
  ppMFType = 0;
  v7 = MFCreateMediaType(&ppMFType);
  if ( v7 >= 0 )
  {
    v7 = MFInitMediaTypeFromWaveFormatEx(ppMFType, a2, a2->cbSize + 18);
    if ( v7 >= 0 )
    {
      v7 = MFCreateSample(a3);
      if ( v7 >= 0 )
      {
        v26 = *a3;
        SetSampleTime = (*a3)->lpVtbl->SetSampleTime;
        v28 = (*(__int64 (__fastcall **)(CAVIIAVSStreamParser *))(*(_QWORD *)this + 96LL))(this);
        v7 = ((__int64 (__fastcall *)(IMFSample *, __int64))SetSampleTime)(v26, v28);
        if ( v7 >= 0 )
        {
          v7 = ((__int64 (__fastcall *)(_QWORD, void *, IMFMediaType *))(*a3)->lpVtbl->SetUnknown)(
                 *a3,
                 &AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE,
                 ppMFType);
          if ( v7 < 0 )
          {
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
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CAVIIAVSStreamParser::CreateAudioFormatChange",
                  148,
                  v7);
            }
            if ( g_wppLevels )
            {
              v13 = 23;
              goto LABEL_56;
            }
          }
        }
        else
        {
          v32 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v7 )
              CallStackContext::TraceFailure(v34, "CAVIIAVSStreamParser::CreateAudioFormatChange", 147, v7);
          }
          if ( g_wppLevels )
          {
            v13 = 22;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v23 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v7 )
            CallStackContext::TraceFailure(v25, "CAVIIAVSStreamParser::CreateAudioFormatChange", 146, v7);
        }
        if ( g_wppLevels )
        {
          v13 = 21;
          goto LABEL_56;
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
        v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
        if ( *((_DWORD *)v19 + 499) != v7 )
          CallStackContext::TraceFailure(v19, "CAVIIAVSStreamParser::CreateAudioFormatChange", 143, v7);
      }
      if ( g_wppLevels )
      {
        v13 = 20;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6, v8, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v7 )
        CallStackContext::TraceFailure(v12, "CAVIIAVSStreamParser::CreateAudioFormatChange", 142, v7);
    }
    if ( g_wppLevels )
    {
      v13 = 19;
LABEL_56:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v7);
    }
  }
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppMFType);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v42);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18013da20  mov     [rsp+arg_8], rbx
0x18013da25  mov     [rsp+arg_10], rsi
0x18013da2a  push    rdi
0x18013da2b  push    r14
0x18013da2d  push    r15
0x18013da2f  sub     rsp, 30h
0x18013da33  mov     r14, r8
0x18013da36  lea     r15, aCaviiavsstream_3; "CAVIIAVSStreamParser::CreateAudioFormat"...
0x18013da3d  mov     rdi, rdx
0x18013da40  mov     rsi, rcx
0x18013da43  mov     rdx, r15; char *
0x18013da46  lea     rcx, [rsp+48h+arg_0]; this
0x18013da4b  mov     r8d, 8Ah; int
0x18013da51  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18013da56  lea     rcx, [rsp+48h+ppMFType]; ppMFType
0x18013da5b  mov     [rsp+48h+ppMFType], 0
0x18013da64  call    cs:__imp_MFCreateMediaType
0x18013da6a  mov     ebx, eax
0x18013da6c  test    eax, eax
0x18013da6e  jns     loc_18013DAFF
0x18013da74  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013da7b  test    rcx, rcx
0x18013da7e  jnz     short loc_18013DAC1
0x18013da80  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013da86  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013da8d  mov     rcx, rax
0x18013da90  test    rax, rax
0x18013da93  jz      short loc_18013DAB3
0x18013da95  mov     rax, [rax]
0x18013da98  mov     edx, 7F0h
0x18013da9d  mov     rax, [rax+8]
0x18013daa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013daa6  test    eax, eax
0x18013daa8  jz      short loc_18013DAB3
0x18013daaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dab1  jmp     short loc_18013DAC1
0x18013dab3  lea     rcx, qword_1801B07E0; this
0x18013daba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dac1  cmp     byte ptr [rcx+8], 0
0x18013dac5  jz      short loc_18013DAE8
0x18013dac7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013dacc  cmp     [rax+7CCh], ebx
0x18013dad2  jz      short loc_18013DAE8
0x18013dad4  mov     r9d, ebx; int
0x18013dad7  mov     r8d, 8Eh; int
0x18013dadd  mov     rdx, r15; char *
0x18013dae0  mov     rcx, rax; this
0x18013dae3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013dae8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013daef  jb      loc_18013DDD0
0x18013daf5  mov     edx, 13h
0x18013dafa  jmp     loc_18013DDB2
0x18013daff  movzx   r8d, word ptr [rdi+10h]
0x18013db04  mov     rdx, rdi; pWaveFormat
0x18013db07  mov     rcx, [rsp+48h+ppMFType]; pMFType
0x18013db0c  add     r8d, 12h; cbBufSize
0x18013db10  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x18013db16  mov     ebx, eax
0x18013db18  test    eax, eax
0x18013db1a  jns     loc_18013DBAB
0x18013db20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013db27  test    rcx, rcx
0x18013db2a  jnz     short loc_18013DB6D
0x18013db2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013db32  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013db39  mov     rcx, rax
0x18013db3c  test    rax, rax
0x18013db3f  jz      short loc_18013DB5F
0x18013db41  mov     rax, [rax]
0x18013db44  mov     edx, 7F0h
0x18013db49  mov     rax, [rax+8]
0x18013db4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013db52  test    eax, eax
0x18013db54  jz      short loc_18013DB5F
0x18013db56  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013db5d  jmp     short loc_18013DB6D
0x18013db5f  lea     rcx, qword_1801B07E0; this
0x18013db66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013db6d  cmp     byte ptr [rcx+8], 0
0x18013db71  jz      short loc_18013DB94
0x18013db73  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013db78  cmp     [rax+7CCh], ebx
0x18013db7e  jz      short loc_18013DB94
0x18013db80  mov     r9d, ebx; int
0x18013db83  mov     r8d, 8Fh; int
0x18013db89  mov     rdx, r15; char *
0x18013db8c  mov     rcx, rax; this
0x18013db8f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013db94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013db9b  jb      loc_18013DDD0
0x18013dba1  mov     edx, 14h
0x18013dba6  jmp     loc_18013DDB2
0x18013dbab  mov     rcx, r14; ppIMFSample
0x18013dbae  call    cs:__imp_MFCreateSample
0x18013dbb4  mov     ebx, eax
0x18013dbb6  test    eax, eax
0x18013dbb8  jns     loc_18013DC49
0x18013dbbe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dbc5  test    rcx, rcx
0x18013dbc8  jnz     short loc_18013DC0B
0x18013dbca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013dbd0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dbd7  mov     rcx, rax
0x18013dbda  test    rax, rax
0x18013dbdd  jz      short loc_18013DBFD
0x18013dbdf  mov     rax, [rax]
0x18013dbe2  mov     edx, 7F0h
0x18013dbe7  mov     rax, [rax+8]
0x18013dbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dbf0  test    eax, eax
0x18013dbf2  jz      short loc_18013DBFD
0x18013dbf4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dbfb  jmp     short loc_18013DC0B
0x18013dbfd  lea     rcx, qword_1801B07E0; this
0x18013dc04  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dc0b  cmp     byte ptr [rcx+8], 0
0x18013dc0f  jz      short loc_18013DC32
0x18013dc11  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013dc16  cmp     [rax+7CCh], ebx
0x18013dc1c  jz      short loc_18013DC32
0x18013dc1e  mov     r9d, ebx; int
0x18013dc21  mov     r8d, 92h; int
0x18013dc27  mov     rdx, r15; char *
0x18013dc2a  mov     rcx, rax; this
0x18013dc2d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013dc32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013dc39  jb      loc_18013DDD0
0x18013dc3f  mov     edx, 15h
0x18013dc44  jmp     loc_18013DDB2
0x18013dc49  mov     rdi, [r14]
0x18013dc4c  mov     rcx, rsi
0x18013dc4f  mov     rdx, [rsi]
0x18013dc52  mov     rax, [rdi]
0x18013dc55  mov     rbx, [rax+120h]
0x18013dc5c  mov     rax, [rdx+60h]
0x18013dc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dc65  mov     rdx, rax
0x18013dc68  mov     rcx, rdi
0x18013dc6b  mov     rax, rbx
0x18013dc6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dc73  mov     ebx, eax
0x18013dc75  test    eax, eax
0x18013dc77  jns     loc_18013DD08
0x18013dc7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dc84  test    rcx, rcx
0x18013dc87  jnz     short loc_18013DCCA
0x18013dc89  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013dc8f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dc96  mov     rcx, rax
0x18013dc99  test    rax, rax
0x18013dc9c  jz      short loc_18013DCBC
0x18013dc9e  mov     rax, [rax]
0x18013dca1  mov     edx, 7F0h
0x18013dca6  mov     rax, [rax+8]
0x18013dcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dcaf  test    eax, eax
0x18013dcb1  jz      short loc_18013DCBC
0x18013dcb3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dcba  jmp     short loc_18013DCCA
0x18013dcbc  lea     rcx, qword_1801B07E0; this
0x18013dcc3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dcca  cmp     byte ptr [rcx+8], 0
0x18013dcce  jz      short loc_18013DCF1
0x18013dcd0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013dcd5  cmp     [rax+7CCh], ebx
0x18013dcdb  jz      short loc_18013DCF1
0x18013dcdd  mov     r9d, ebx; int
0x18013dce0  mov     r8d, 93h; int
0x18013dce6  mov     rdx, r15; char *
0x18013dce9  mov     rcx, rax; this
0x18013dcec  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013dcf1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013dcf8  jb      loc_18013DDD0
0x18013dcfe  mov     edx, 16h
0x18013dd03  jmp     loc_18013DDB2
0x18013dd08  mov     rcx, [r14]
0x18013dd0b  lea     rdx, AVI_SAMPLE_ATTRIBUTE_FORMATCHANGE_MEDIATYPE
0x18013dd12  mov     r8, [rsp+48h+ppMFType]
0x18013dd17  mov     rax, [rcx]
0x18013dd1a  mov     rax, [rax+0D8h]
0x18013dd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dd26  mov     ebx, eax
0x18013dd28  test    eax, eax
0x18013dd2a  jns     loc_18013DDD0
0x18013dd30  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dd37  test    rcx, rcx
0x18013dd3a  jnz     short loc_18013DD7D
0x18013dd3c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18013dd42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dd49  mov     rcx, rax
0x18013dd4c  test    rax, rax
0x18013dd4f  jz      short loc_18013DD6F
0x18013dd51  mov     rax, [rax]
0x18013dd54  mov     edx, 7F0h
0x18013dd59  mov     rax, [rax+8]
0x18013dd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dd62  test    eax, eax
0x18013dd64  jz      short loc_18013DD6F
0x18013dd66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dd6d  jmp     short loc_18013DD7D
0x18013dd6f  lea     rcx, qword_1801B07E0; this
0x18013dd76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18013dd7d  cmp     byte ptr [rcx+8], 0
0x18013dd81  jz      short loc_18013DDA4
0x18013dd83  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18013dd88  cmp     [rax+7CCh], ebx
0x18013dd8e  jz      short loc_18013DDA4
0x18013dd90  mov     r9d, ebx; int
0x18013dd93  mov     r8d, 94h; int
0x18013dd99  mov     rdx, r15; char *
0x18013dd9c  mov     rcx, rax; this
0x18013dd9f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18013dda4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18013ddab  jb      short loc_18013DDD0
0x18013ddad  mov     edx, 17h
0x18013ddb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18013ddb9  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x18013ddc0  mov     r9, rsi
0x18013ddc3  mov     [rsp+48h+var_28], ebx
0x18013ddc7  mov     rcx, [rcx+10h]
0x18013ddcb  call    WPP_SF_qD
0x18013ddd0  lea     rcx, [rsp+48h+ppMFType]; void *
0x18013ddd5  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x18013ddda  lea     rcx, [rsp+48h+arg_0]; this
0x18013dddf  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18013dde4  mov     rsi, [rsp+48h+arg_10]
0x18013dde9  mov     eax, ebx
0x18013ddeb  mov     rbx, [rsp+48h+arg_8]
0x18013ddf0  add     rsp, 30h
0x18013ddf4  pop     r15
0x18013ddf6  pop     r14
0x18013ddf8  pop     rdi
0x18013ddf9  retn
```
