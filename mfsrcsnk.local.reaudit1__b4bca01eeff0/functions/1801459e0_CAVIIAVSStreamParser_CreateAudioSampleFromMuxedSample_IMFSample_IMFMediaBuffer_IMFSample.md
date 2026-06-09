# CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(IMFSample *,IMFMediaBuffer *,IMFSample * *)

- ea: `0x1801459e0`
- end: `0x180145e4b`
- name: `?CreateAudioSampleFromMuxedSample@CAVIIAVSStreamParser@@AEAAJPEAUIMFSample@@PEAUIMFMediaBuffer@@PEAPEAU2@@Z`
- size: `1131`
- prototype: `__int64 __fastcall(CAVIIAVSStreamParser *__hidden this, struct IMFSample *, struct IMFMediaBuffer *, struct IMFSample **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180144a80`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180036c30`
- `0x180079680`
- `0x1801459e0`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145c21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145cdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145d8d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145a63`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145b51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145c21`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145cdc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180145d8d`
- `MFPlat!MFCreateSample` at `0x180145a41`
- `MFPlat!MFCreateSample` at `0x180145a41`

## string_xrefs

- `0x180145a1a`: `CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample`

## pseudocode

```c
__int64 __fastcall CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample(
        CAVIIAVSStreamParser *this,
        struct IMFSample *a2,
        struct IMFMediaBuffer *a3,
        struct IMFSample **a4)
{
  __int64 v8; // rdx
  HRESULT v9; // ebx
  wchar_t *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFSample *ppIMFSample; // [rsp+30h] [rbp-20h] BYREF
  __int64 v32; // [rsp+38h] [rbp-18h] BYREF
  __int64 v33; // [rsp+40h] [rbp-10h] BYREF
  char v34; // [rsp+98h] [rbp+48h] BYREF

  ppIMFSample = 0;
  v32 = 0;
  v33 = 0;
  *a4 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v34,
    "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample",
    304);
  v9 = MFCreateSample(&ppIMFSample);
  if ( v9 >= 0 )
  {
    if ( ((int (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleTime)(a2, &v32) < 0
      || (v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, v32),
          v9 >= 0) )
    {
      if ( ((int (__fastcall *)(struct IMFSample *, __int64 *))a2->lpVtbl->GetSampleDuration)(a2, &v33) < 0
        || (v9 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(
                   ppIMFSample,
                   v33),
            v9 >= 0) )
      {
        v9 = ((__int64 (__fastcall *)(IMFSample *, const GUID *, __int64))ppIMFSample->lpVtbl->SetUINT32)(
               ppIMFSample,
               &MFSampleExtension_CleanPoint,
               1);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                 ppIMFSample,
                 a3);
          if ( v9 >= 0 )
          {
            *a4 = ppIMFSample;
            ppIMFSample = 0;
            goto LABEL_60;
          }
          v27 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v9 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample",
                318,
                v9);
          }
          if ( g_wppLevels )
          {
            v13 = 41;
            goto LABEL_12;
          }
        }
        else
        {
          v23 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v24;
            if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
            {
              v23 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v23 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v23 + 8) )
          {
            v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
            if ( *((_DWORD *)v25 + 499) != v9 )
              CallStackContext::TraceFailure(v25, "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample", 317, v9);
          }
          if ( g_wppLevels )
          {
            v13 = 40;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v19 = (wchar_t *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
          CallStackTracing::s_wpInstance = v20;
          if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
          {
            v19 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v19 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
          if ( *((_DWORD *)v21 + 499) != v9 )
            CallStackContext::TraceFailure(v21, "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample", 313, v9);
        }
        if ( g_wppLevels )
        {
          v13 = 39;
          goto LABEL_12;
        }
      }
    }
    else
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
        if ( *((_DWORD *)v17 + 499) != v9 )
          CallStackContext::TraceFailure(v17, "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample", 308, v9);
      }
      if ( g_wppLevels )
      {
        v13 = 38;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v10 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v9 )
        CallStackContext::TraceFailure(v12, "CAVIIAVSStreamParser::CreateAudioSampleFromMuxedSample", 304, v9);
    }
    if ( g_wppLevels )
    {
      v13 = 37;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids, this, v9);
    }
  }
LABEL_60:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(&ppIMFSample);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801459e0  mov     [rsp-28h+arg_0], rbx
0x1801459e5  mov     [rsp-28h+arg_8], rsi
0x1801459ea  push    rbp
0x1801459eb  push    rdi
0x1801459ec  push    r13
0x1801459ee  push    r14
0x1801459f0  push    r15
0x1801459f2  mov     rbp, rsp
0x1801459f5  sub     rsp, 50h
0x1801459f9  mov     r15, r8
0x1801459fc  mov     [rbp+ppIMFSample], 0
0x180145a04  mov     rdi, rdx
0x180145a07  mov     [rbp+var_18], 0
0x180145a0f  mov     rsi, rcx
0x180145a12  mov     [rbp+var_10], 0
0x180145a1a  lea     r13, aCaviiavsstream_1; "CAVIIAVSStreamParser::CreateAudioSample"...
0x180145a21  mov     qword ptr [r9], 0
0x180145a28  mov     rdx, r13; char *
0x180145a2b  lea     rcx, [rbp+arg_18]; this
0x180145a2f  mov     r8d, 130h; int
0x180145a35  mov     r14, r9
0x180145a38  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180145a3d  lea     rcx, [rbp+ppIMFSample]; ppIMFSample
0x180145a41  call    cs:__imp_MFCreateSample
0x180145a48  nop     dword ptr [rax+rax+00h]
0x180145a4d  mov     ebx, eax
0x180145a4f  test    eax, eax
0x180145a51  jns     loc_180145B06
0x180145a57  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145a5e  test    rcx, rcx
0x180145a61  jnz     short loc_180145AAA
0x180145a63  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145a6a  nop     dword ptr [rax+rax+00h]
0x180145a6f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145a76  mov     rcx, rax
0x180145a79  test    rax, rax
0x180145a7c  jz      short loc_180145A9C
0x180145a7e  mov     rax, [rax]
0x180145a81  mov     edx, 7F0h
0x180145a86  mov     rax, [rax+8]
0x180145a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145a8f  test    eax, eax
0x180145a91  jz      short loc_180145A9C
0x180145a93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145a9a  jmp     short loc_180145AAA
0x180145a9c  lea     rcx, qword_1801B97E0; this
0x180145aa3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145aaa  cmp     byte ptr [rcx+8], 0
0x180145aae  jz      short loc_180145AD1
0x180145ab0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145ab5  cmp     [rax+7CCh], ebx
0x180145abb  jz      short loc_180145AD1
0x180145abd  mov     r9d, ebx; int
0x180145ac0  mov     r8d, 130h; int
0x180145ac6  mov     rdx, r13; char *
0x180145ac9  mov     rcx, rax; this
0x180145acc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145ad1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145ad8  jb      loc_180145E1D
0x180145ade  mov     edx, 25h ; '%'
0x180145ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180145aea  lea     r8, WPP_0c6b2006a0443a18a2b9fa7547964932_Traceguids
0x180145af1  mov     r9, rsi
0x180145af4  mov     [rsp+50h+var_30], ebx
0x180145af8  mov     rcx, [rcx+10h]
0x180145afc  call    WPP_SF_qD
0x180145b01  jmp     loc_180145E1D
0x180145b06  mov     rax, [rdi]
0x180145b09  lea     rdx, [rbp+var_18]
0x180145b0d  mov     rcx, rdi
0x180145b10  mov     rax, [rax+118h]
0x180145b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145b1c  test    eax, eax
0x180145b1e  js      loc_180145BD6
0x180145b24  mov     rcx, [rbp+ppIMFSample]
0x180145b28  mov     rdx, [rbp+var_18]
0x180145b2c  mov     rax, [rcx]
0x180145b2f  mov     rax, [rax+120h]
0x180145b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145b3b  mov     ebx, eax
0x180145b3d  test    eax, eax
0x180145b3f  jns     loc_180145BD6
0x180145b45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145b4c  test    rcx, rcx
0x180145b4f  jnz     short loc_180145B98
0x180145b51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145b58  nop     dword ptr [rax+rax+00h]
0x180145b5d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145b64  mov     rcx, rax
0x180145b67  test    rax, rax
0x180145b6a  jz      short loc_180145B8A
0x180145b6c  mov     rax, [rax]
0x180145b6f  mov     edx, 7F0h
0x180145b74  mov     rax, [rax+8]
0x180145b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145b7d  test    eax, eax
0x180145b7f  jz      short loc_180145B8A
0x180145b81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145b88  jmp     short loc_180145B98
0x180145b8a  lea     rcx, qword_1801B97E0; this
0x180145b91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145b98  cmp     byte ptr [rcx+8], 0
0x180145b9c  jz      short loc_180145BBF
0x180145b9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145ba3  cmp     [rax+7CCh], ebx
0x180145ba9  jz      short loc_180145BBF
0x180145bab  mov     r9d, ebx; int
0x180145bae  mov     r8d, 134h; int
0x180145bb4  mov     rdx, r13; char *
0x180145bb7  mov     rcx, rax; this
0x180145bba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145bbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145bc6  jb      loc_180145E1D
0x180145bcc  mov     edx, 26h ; '&'
0x180145bd1  jmp     loc_180145AE3
0x180145bd6  mov     rax, [rdi]
0x180145bd9  lea     rdx, [rbp+var_10]
0x180145bdd  mov     rcx, rdi
0x180145be0  mov     rax, [rax+128h]
0x180145be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145bec  test    eax, eax
0x180145bee  js      loc_180145CA6
0x180145bf4  mov     rcx, [rbp+ppIMFSample]
0x180145bf8  mov     rdx, [rbp+var_10]
0x180145bfc  mov     rax, [rcx]
0x180145bff  mov     rax, [rax+130h]
0x180145c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145c0b  mov     ebx, eax
0x180145c0d  test    eax, eax
0x180145c0f  jns     loc_180145CA6
0x180145c15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145c1c  test    rcx, rcx
0x180145c1f  jnz     short loc_180145C68
0x180145c21  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145c28  nop     dword ptr [rax+rax+00h]
0x180145c2d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145c34  mov     rcx, rax
0x180145c37  test    rax, rax
0x180145c3a  jz      short loc_180145C5A
0x180145c3c  mov     rax, [rax]
0x180145c3f  mov     edx, 7F0h
0x180145c44  mov     rax, [rax+8]
0x180145c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145c4d  test    eax, eax
0x180145c4f  jz      short loc_180145C5A
0x180145c51  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145c58  jmp     short loc_180145C68
0x180145c5a  lea     rcx, qword_1801B97E0; this
0x180145c61  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145c68  cmp     byte ptr [rcx+8], 0
0x180145c6c  jz      short loc_180145C8F
0x180145c6e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145c73  cmp     [rax+7CCh], ebx
0x180145c79  jz      short loc_180145C8F
0x180145c7b  mov     r9d, ebx; int
0x180145c7e  mov     r8d, 139h; int
0x180145c84  mov     rdx, r13; char *
0x180145c87  mov     rcx, rax; this
0x180145c8a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145c8f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145c96  jb      loc_180145E1D
0x180145c9c  mov     edx, 27h ; '''
0x180145ca1  jmp     loc_180145AE3
0x180145ca6  mov     rcx, [rbp+ppIMFSample]
0x180145caa  lea     rdx, MFSampleExtension_CleanPoint
0x180145cb1  mov     r8d, 1
0x180145cb7  mov     rax, [rcx]
0x180145cba  mov     rax, [rax+0A8h]
0x180145cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145cc6  mov     ebx, eax
0x180145cc8  test    eax, eax
0x180145cca  jns     loc_180145D61
0x180145cd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145cd7  test    rcx, rcx
0x180145cda  jnz     short loc_180145D23
0x180145cdc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145ce3  nop     dword ptr [rax+rax+00h]
0x180145ce8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145cef  mov     rcx, rax
0x180145cf2  test    rax, rax
0x180145cf5  jz      short loc_180145D15
0x180145cf7  mov     rax, [rax]
0x180145cfa  mov     edx, 7F0h
0x180145cff  mov     rax, [rax+8]
0x180145d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145d08  test    eax, eax
0x180145d0a  jz      short loc_180145D15
0x180145d0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145d13  jmp     short loc_180145D23
0x180145d15  lea     rcx, qword_1801B97E0; this
0x180145d1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145d23  cmp     byte ptr [rcx+8], 0
0x180145d27  jz      short loc_180145D4A
0x180145d29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145d2e  cmp     [rax+7CCh], ebx
0x180145d34  jz      short loc_180145D4A
0x180145d36  mov     r9d, ebx; int
0x180145d39  mov     r8d, 13Dh; int
0x180145d3f  mov     rdx, r13; char *
0x180145d42  mov     rcx, rax; this
0x180145d45  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145d4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145d51  jb      loc_180145E1D
0x180145d57  mov     edx, 28h ; '('
0x180145d5c  jmp     loc_180145AE3
0x180145d61  mov     rcx, [rbp+ppIMFSample]
0x180145d65  mov     rdx, r15
0x180145d68  mov     rax, [rcx]
0x180145d6b  mov     rax, [rax+150h]
0x180145d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145d77  mov     ebx, eax
0x180145d79  test    eax, eax
0x180145d7b  jns     loc_180145E0E
0x180145d81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145d88  test    rcx, rcx
0x180145d8b  jnz     short loc_180145DD4
0x180145d8d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180145d94  nop     dword ptr [rax+rax+00h]
0x180145d99  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180145da0  mov     rcx, rax
0x180145da3  test    rax, rax
0x180145da6  jz      short loc_180145DC6
0x180145da8  mov     rax, [rax]
0x180145dab  mov     edx, 7F0h
0x180145db0  mov     rax, [rax+8]
0x180145db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180145db9  test    eax, eax
0x180145dbb  jz      short loc_180145DC6
0x180145dbd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180145dc4  jmp     short loc_180145DD4
0x180145dc6  lea     rcx, qword_1801B97E0; this
0x180145dcd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180145dd4  cmp     byte ptr [rcx+8], 0
0x180145dd8  jz      short loc_180145DFB
0x180145dda  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180145ddf  cmp     [rax+7CCh], ebx
0x180145de5  jz      short loc_180145DFB
0x180145de7  mov     r9d, ebx; int
0x180145dea  mov     r8d, 13Eh; int
0x180145df0  mov     rdx, r13; char *
0x180145df3  mov     rcx, rax; this
0x180145df6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180145dfb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180145e02  jb      short loc_180145E1D
0x180145e04  mov     edx, 29h ; ')'
0x180145e09  jmp     loc_180145AE3
0x180145e0e  mov     rax, [rbp+ppIMFSample]
0x180145e12  mov     [r14], rax
0x180145e15  mov     [rbp+ppIMFSample], 0
0x180145e1d  lea     rcx, [rbp+arg_18]; this
0x180145e21  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180145e26  lea     rcx, [rbp+ppIMFSample]; void *
0x180145e2a  call    ??1?$ComSmartPtr@UIMFMediaEvent@@@@QEAA@XZ; ComSmartPtr<IMFMediaEvent>::~ComSmartPtr<IMFMediaEvent>(void)
0x180145e2f  lea     r11, [rsp+50h+var_s0]
0x180145e34  mov     eax, ebx
0x180145e36  mov     rbx, [r11+30h]
0x180145e3a  mov     rsi, [r11+38h]
0x180145e3e  mov     rsp, r11
0x180145e41  pop     r15
0x180145e43  pop     r14
0x180145e45  pop     r13
0x180145e47  pop     rdi
0x180145e48  pop     rbp
0x180145e49  retn
```
