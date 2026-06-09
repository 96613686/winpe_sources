# CMFByteStreamMediaSource::CreateInstance(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x1800a8c70`
- end: `0x1800a914a`
- name: `?CreateInstance@CMFByteStreamMediaSource@@SAJPEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1242`
- prototype: `__int64 __fastcall(struct IMFByteStream *, struct IUnknown *, struct IPropertyStore *, unsigned int, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18011bd40`

## callees

- `0x180005cf4`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180079680`
- `0x1800a8c70`
- `0x1800dd428`
- `0x180110a94`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8cc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8d73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8e1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8f02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8fc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9065`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8cc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8d73`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8e1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8f02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a8fc2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9065`

## string_xrefs

- `0x1800a8c97`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a8d31`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a8ddc`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a8e88`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a8f6c`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a902c`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a90cf`: `CMFByteStreamMediaSource::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFByteStreamMediaSource::CreateInstance(
        struct IMFByteStream *a1,
        struct IUnknown *a2,
        struct IPropertyStore *a3,
        unsigned int a4,
        struct IMFMediaSource **a5)
{
  __int64 v9; // rdx
  CMFByteStreamMediaSource *v10; // rbx
  wchar_t *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  wchar_t *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  CMFByteStreamMediaSource *v21; // rax
  __int64 v22; // rdx
  CMFByteStreamMediaSource *v23; // rax
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  wchar_t *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  unsigned int v34; // ebx
  int v36[6]; // [rsp+30h] [rbp-18h] BYREF
  char v37; // [rsp+80h] [rbp+38h] BYREF

  v36[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v37, "CMFByteStreamMediaSource::CreateInstance", 296);
  v10 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a5 )
      {
        v21 = (CMFByteStreamMediaSource *)operator new(0x530u);
        if ( v21
          && (v23 = CMFByteStreamMediaSource::CMFByteStreamMediaSource(v21, a1, a2, a3, a4, v36), (v10 = v23) != 0) )
        {
          if ( v36[0] >= 0 )
          {
            v36[0] = (**(__int64 (__fastcall ***)(CMFByteStreamMediaSource *, GUID *, struct IMFMediaSource **))v23)(
                       v23,
                       &IID_IMFMediaSource,
                       a5);
            if ( v36[0] < 0 )
            {
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
                if ( v36[0] < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v36[0] )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CMFByteStreamMediaSource::CreateInstance",
                    312,
                    v36[0]);
              }
              if ( g_wppLevels )
              {
                v14 = 21;
                goto LABEL_74;
              }
            }
          }
          else
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
              {
                v24 = (wchar_t *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v24 = &qword_1801B97E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
              }
            }
            if ( *((_BYTE *)v24 + 8) )
            {
              v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
              if ( v36[0] < 0 && *((_DWORD *)v26 + 499) != v36[0] )
                CallStackContext::TraceFailure(v26, "CMFByteStreamMediaSource::CreateInstance", 310, v36[0]);
            }
            if ( g_wppLevels )
            {
              v14 = 20;
              goto LABEL_74;
            }
          }
        }
        else
        {
          v31 = (wchar_t *)CallStackTracing::s_wpInstance;
          v36[0] = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = &qword_1801B97E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
            if ( v36[0] < 0 && *((_DWORD *)v33 + 499) != v36[0] )
              CallStackContext::TraceFailure(v33, "CMFByteStreamMediaSource::CreateInstance", 309, v36[0]);
          }
          if ( g_wppLevels )
          {
            v14 = 19;
            goto LABEL_74;
          }
        }
      }
      else
      {
        v18 = (wchar_t *)CallStackTracing::s_wpInstance;
        v36[0] = -2147467261;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
          if ( *((_DWORD *)v20 + 499) != v36[0] )
            CallStackContext::TraceFailure(v20, "CMFByteStreamMediaSource::CreateInstance", 302, v36[0]);
        }
        if ( g_wppLevels )
        {
          v14 = 18;
          goto LABEL_74;
        }
      }
    }
    else
    {
      v15 = (wchar_t *)CallStackTracing::s_wpInstance;
      v36[0] = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
        if ( *((_DWORD *)v17 + 499) != v36[0] )
          CallStackContext::TraceFailure(v17, "CMFByteStreamMediaSource::CreateInstance", 301, v36[0]);
      }
      if ( g_wppLevels )
      {
        v14 = 17;
        goto LABEL_74;
      }
    }
  }
  else
  {
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
    v36[0] = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
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
      if ( *((_DWORD *)v13 + 499) != v36[0] )
        CallStackContext::TraceFailure(v13, "CMFByteStreamMediaSource::CreateInstance", 300, v36[0]);
    }
    if ( g_wppLevels )
    {
      v14 = 16;
LABEL_74:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids, 0, v36[0]);
    }
  }
  if ( v36[0] < 0 && v10 )
    (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v10 + 11) + 24LL))((__int64)v10 + 88, 1);
  v34 = v36[0];
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v37);
  return v34;
}

```

## disassembly

```asm
0x1800a8c70  push    rbp
0x1800a8c72  push    rbx
0x1800a8c73  push    rsi
0x1800a8c74  push    r12
0x1800a8c76  push    r14
0x1800a8c78  push    r15
0x1800a8c7a  mov     rbp, rsp
0x1800a8c7d  sub     rsp, 48h
0x1800a8c81  mov     r12, r8
0x1800a8c84  mov     [rbp+var_18], 0
0x1800a8c8b  mov     rsi, rdx
0x1800a8c8e  mov     r14, rcx
0x1800a8c91  mov     r8d, 128h; int
0x1800a8c97  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a8c9e  lea     rcx, [rbp+arg_0]; this
0x1800a8ca2  mov     r15d, r9d
0x1800a8ca5  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a8caa  xor     ebx, ebx
0x1800a8cac  test    r14, r14
0x1800a8caf  jnz     loc_1800A8D57
0x1800a8cb5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8cbc  mov     [rbp+var_18], 80004003h
0x1800a8cc3  test    rcx, rcx
0x1800a8cc6  jnz     short loc_1800A8D0F
0x1800a8cc8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8ccf  nop     dword ptr [rax+rax+00h]
0x1800a8cd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8cdb  mov     rcx, rax
0x1800a8cde  test    rax, rax
0x1800a8ce1  jz      short loc_1800A8D01
0x1800a8ce3  mov     rax, [rax]
0x1800a8ce6  mov     edx, 7F0h
0x1800a8ceb  mov     rax, [rax+8]
0x1800a8cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8cf4  test    eax, eax
0x1800a8cf6  jz      short loc_1800A8D01
0x1800a8cf8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8cff  jmp     short loc_1800A8D0F
0x1800a8d01  lea     rcx, qword_1801B97E0; this
0x1800a8d08  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8d0f  cmp     [rcx+8], bl
0x1800a8d12  jz      short loc_1800A8D40
0x1800a8d14  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8d19  mov     r9d, [rbp+var_18]; int
0x1800a8d1d  test    r9d, r9d
0x1800a8d20  jns     short loc_1800A8D40
0x1800a8d22  cmp     [rax+7CCh], r9d
0x1800a8d29  jz      short loc_1800A8D40
0x1800a8d2b  mov     r8d, 12Ch; int
0x1800a8d31  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a8d38  mov     rcx, rax; this
0x1800a8d3b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8d40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8d47  jb      loc_1800A910D
0x1800a8d4d  mov     edx, 10h
0x1800a8d52  jmp     loc_1800A90EC
0x1800a8d57  test    rsi, rsi
0x1800a8d5a  jnz     loc_1800A8E02
0x1800a8d60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8d67  mov     [rbp+var_18], 80004003h
0x1800a8d6e  test    rcx, rcx
0x1800a8d71  jnz     short loc_1800A8DBA
0x1800a8d73  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8d7a  nop     dword ptr [rax+rax+00h]
0x1800a8d7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8d86  mov     rcx, rax
0x1800a8d89  test    rax, rax
0x1800a8d8c  jz      short loc_1800A8DAC
0x1800a8d8e  mov     rax, [rax]
0x1800a8d91  mov     edx, 7F0h
0x1800a8d96  mov     rax, [rax+8]
0x1800a8d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8d9f  test    eax, eax
0x1800a8da1  jz      short loc_1800A8DAC
0x1800a8da3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8daa  jmp     short loc_1800A8DBA
0x1800a8dac  lea     rcx, qword_1801B97E0; this
0x1800a8db3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8dba  cmp     [rcx+8], bl
0x1800a8dbd  jz      short loc_1800A8DEB
0x1800a8dbf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8dc4  mov     r9d, [rbp+var_18]; int
0x1800a8dc8  test    r9d, r9d
0x1800a8dcb  jns     short loc_1800A8DEB
0x1800a8dcd  cmp     [rax+7CCh], r9d
0x1800a8dd4  jz      short loc_1800A8DEB
0x1800a8dd6  mov     r8d, 12Dh; int
0x1800a8ddc  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a8de3  mov     rcx, rax; this
0x1800a8de6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8deb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8df2  jb      loc_1800A910D
0x1800a8df8  mov     edx, 11h
0x1800a8dfd  jmp     loc_1800A90EC
0x1800a8e02  cmp     [rbp+arg_20], rbx
0x1800a8e06  jnz     loc_1800A8EAE
0x1800a8e0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e13  mov     [rbp+var_18], 80004003h
0x1800a8e1a  test    rcx, rcx
0x1800a8e1d  jnz     short loc_1800A8E66
0x1800a8e1f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8e26  nop     dword ptr [rax+rax+00h]
0x1800a8e2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e32  mov     rcx, rax
0x1800a8e35  test    rax, rax
0x1800a8e38  jz      short loc_1800A8E58
0x1800a8e3a  mov     rax, [rax]
0x1800a8e3d  mov     edx, 7F0h
0x1800a8e42  mov     rax, [rax+8]
0x1800a8e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8e4b  test    eax, eax
0x1800a8e4d  jz      short loc_1800A8E58
0x1800a8e4f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e56  jmp     short loc_1800A8E66
0x1800a8e58  lea     rcx, qword_1801B97E0; this
0x1800a8e5f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8e66  cmp     [rcx+8], bl
0x1800a8e69  jz      short loc_1800A8E97
0x1800a8e6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8e70  mov     r9d, [rbp+var_18]; int
0x1800a8e74  test    r9d, r9d
0x1800a8e77  jns     short loc_1800A8E97
0x1800a8e79  cmp     [rax+7CCh], r9d
0x1800a8e80  jz      short loc_1800A8E97
0x1800a8e82  mov     r8d, 12Eh; int
0x1800a8e88  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a8e8f  mov     rcx, rax; this
0x1800a8e92  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8e97  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8e9e  jb      loc_1800A910D
0x1800a8ea4  mov     edx, 12h
0x1800a8ea9  jmp     loc_1800A90EC
0x1800a8eae  mov     ecx, 530h; Size
0x1800a8eb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a8eb8  test    rax, rax
0x1800a8ebb  jz      loc_1800A9052
0x1800a8ec1  lea     rcx, [rbp+var_18]
0x1800a8ec5  mov     r9, r12; struct IPropertyStore *
0x1800a8ec8  mov     [rsp+48h+var_20], rcx; int *
0x1800a8ecd  mov     r8, rsi; struct IUnknown *
0x1800a8ed0  mov     rcx, rax; this
0x1800a8ed3  mov     [rsp+48h+var_28], r15d; unsigned int
0x1800a8ed8  mov     rdx, r14; struct IMFByteStream *
0x1800a8edb  call    ??0CMFByteStreamMediaSource@@AEAA@PEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAJ@Z; CMFByteStreamMediaSource::CMFByteStreamMediaSource(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,long *)
0x1800a8ee0  mov     rbx, rax
0x1800a8ee3  test    rax, rax
0x1800a8ee6  jz      loc_1800A9052
0x1800a8eec  cmp     [rbp+var_18], 0
0x1800a8ef0  jge     loc_1800A8F92
0x1800a8ef6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8efd  test    rcx, rcx
0x1800a8f00  jnz     short loc_1800A8F49
0x1800a8f02  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8f09  nop     dword ptr [rax+rax+00h]
0x1800a8f0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f15  mov     rcx, rax
0x1800a8f18  test    rax, rax
0x1800a8f1b  jz      short loc_1800A8F3B
0x1800a8f1d  mov     rax, [rax]
0x1800a8f20  mov     edx, 7F0h
0x1800a8f25  mov     rax, [rax+8]
0x1800a8f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8f2e  test    eax, eax
0x1800a8f30  jz      short loc_1800A8F3B
0x1800a8f32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f39  jmp     short loc_1800A8F49
0x1800a8f3b  lea     rcx, qword_1801B97E0; this
0x1800a8f42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8f49  cmp     byte ptr [rcx+8], 0
0x1800a8f4d  jz      short loc_1800A8F7B
0x1800a8f4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a8f54  mov     r9d, [rbp+var_18]; int
0x1800a8f58  test    r9d, r9d
0x1800a8f5b  jns     short loc_1800A8F7B
0x1800a8f5d  cmp     [rax+7CCh], r9d
0x1800a8f64  jz      short loc_1800A8F7B
0x1800a8f66  mov     r8d, 136h; int
0x1800a8f6c  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a8f73  mov     rcx, rax; this
0x1800a8f76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a8f7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8f82  jb      loc_1800A910D
0x1800a8f88  mov     edx, 14h
0x1800a8f8d  jmp     loc_1800A90EC
0x1800a8f92  mov     rax, [rax]
0x1800a8f95  lea     rdx, IID_IMFMediaSource
0x1800a8f9c  mov     r8, [rbp+arg_20]
0x1800a8fa0  mov     rcx, rbx
0x1800a8fa3  mov     rax, [rax]
0x1800a8fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8fab  mov     [rbp+var_18], eax
0x1800a8fae  test    eax, eax
0x1800a8fb0  jns     loc_1800A910D
0x1800a8fb6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8fbd  test    rcx, rcx
0x1800a8fc0  jnz     short loc_1800A9009
0x1800a8fc2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a8fc9  nop     dword ptr [rax+rax+00h]
0x1800a8fce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8fd5  mov     rcx, rax
0x1800a8fd8  test    rax, rax
0x1800a8fdb  jz      short loc_1800A8FFB
0x1800a8fdd  mov     rax, [rax]
0x1800a8fe0  mov     edx, 7F0h
0x1800a8fe5  mov     rax, [rax+8]
0x1800a8fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8fee  test    eax, eax
0x1800a8ff0  jz      short loc_1800A8FFB
0x1800a8ff2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a8ff9  jmp     short loc_1800A9009
0x1800a8ffb  lea     rcx, qword_1801B97E0; this
0x1800a9002  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9009  cmp     byte ptr [rcx+8], 0
0x1800a900d  jz      short loc_1800A903B
0x1800a900f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9014  mov     r9d, [rbp+var_18]; int
0x1800a9018  test    r9d, r9d
0x1800a901b  jns     short loc_1800A903B
0x1800a901d  cmp     [rax+7CCh], r9d
0x1800a9024  jz      short loc_1800A903B
0x1800a9026  mov     r8d, 138h; int
0x1800a902c  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a9033  mov     rcx, rax; this
0x1800a9036  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a903b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9042  jb      loc_1800A910D
0x1800a9048  mov     edx, 15h
0x1800a904d  jmp     loc_1800A90EC
0x1800a9052  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9059  mov     [rbp+var_18], 8007000Eh
0x1800a9060  test    rcx, rcx
0x1800a9063  jnz     short loc_1800A90AC
0x1800a9065  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a906c  nop     dword ptr [rax+rax+00h]
0x1800a9071  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9078  mov     rcx, rax
0x1800a907b  test    rax, rax
0x1800a907e  jz      short loc_1800A909E
0x1800a9080  mov     rax, [rax]
0x1800a9083  mov     edx, 7F0h
0x1800a9088  mov     rax, [rax+8]
0x1800a908c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9091  test    eax, eax
0x1800a9093  jz      short loc_1800A909E
0x1800a9095  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a909c  jmp     short loc_1800A90AC
0x1800a909e  lea     rcx, qword_1801B97E0; this
0x1800a90a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a90ac  cmp     byte ptr [rcx+8], 0
0x1800a90b0  jz      short loc_1800A90DE
0x1800a90b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a90b7  mov     r9d, [rbp+var_18]; int
0x1800a90bb  test    r9d, r9d
0x1800a90be  jns     short loc_1800A90DE
0x1800a90c0  cmp     [rax+7CCh], r9d
0x1800a90c7  jz      short loc_1800A90DE
0x1800a90c9  mov     r8d, 135h; int
0x1800a90cf  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a90d6  mov     rcx, rax; this
0x1800a90d9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a90de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a90e5  jb      short loc_1800A910D
0x1800a90e7  mov     edx, 13h
0x1800a90ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a90f3  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800a90fa  mov     eax, [rbp+var_18]
0x1800a90fd  xor     r9d, r9d
0x1800a9100  mov     [rsp+48h+var_28], eax
0x1800a9104  mov     rcx, [rcx+10h]
0x1800a9108  call    WPP_SF_qD
0x1800a910d  cmp     [rbp+var_18], 0
0x1800a9111  jge     short loc_1800A912D
0x1800a9113  test    rbx, rbx
0x1800a9116  jz      short loc_1800A912D
0x1800a9118  lea     rcx, [rbx+58h]
0x1800a911c  mov     edx, 1
0x1800a9121  mov     rax, [rcx]
0x1800a9124  mov     rax, [rax+18h]
0x1800a9128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a912d  mov     ebx, [rbp+var_18]
0x1800a9130  lea     rcx, [rbp+arg_0]; this
0x1800a9134  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a9139  mov     eax, ebx
0x1800a913b  add     rsp, 48h
0x1800a913f  pop     r15
0x1800a9141  pop     r14
0x1800a9143  pop     r12
0x1800a9145  pop     rsi
0x1800a9146  pop     rbx
0x1800a9147  pop     rbp
0x1800a9148  retn
```
