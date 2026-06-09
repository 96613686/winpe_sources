# CMFByteStreamMediaSource::CreateInstance(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,IMFMediaSource * *)

- ea: `0x1800a3d18`
- end: `0x1800a41cd`
- name: `?CreateInstance@CMFByteStreamMediaSource@@SAJPEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAPEAUIMFMediaSource@@@Z`
- size: `1205`
- prototype: `__int64 __fastcall(struct IMFByteStream *, struct IUnknown *, struct IPropertyStore *, unsigned int, struct IMFMediaSource **)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1801141d0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180018b90`
- `0x180073b14`
- `0x1800a3d18`
- `0x1800d7170`
- `0x1801095a8`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3d70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4052`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a40ef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3d70`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3e15`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3ebb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a3f98`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a4052`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a40ef`

## string_xrefs

- `0x1800a3d3f`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a3dd3`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a3e78`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a3f1e`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a3ffc`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a40b6`: `CMFByteStreamMediaSource::CreateInstance`
- `0x1800a4153`: `CMFByteStreamMediaSource::CreateInstance`

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
                  v28 = &qword_1801B07E0;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
                v24 = &qword_1801B07E0;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
              v31 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
            v18 = &qword_1801B07E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
          v15 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
        v11 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
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
0x1800a3d18  push    rbp
0x1800a3d1a  push    rbx
0x1800a3d1b  push    rsi
0x1800a3d1c  push    r12
0x1800a3d1e  push    r14
0x1800a3d20  push    r15
0x1800a3d22  mov     rbp, rsp
0x1800a3d25  sub     rsp, 48h
0x1800a3d29  mov     r12, r8
0x1800a3d2c  mov     [rbp+var_18], 0
0x1800a3d33  mov     rsi, rdx
0x1800a3d36  mov     r14, rcx
0x1800a3d39  mov     r8d, 128h; int
0x1800a3d3f  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a3d46  lea     rcx, [rbp+arg_0]; this
0x1800a3d4a  mov     r15d, r9d
0x1800a3d4d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a3d52  xor     ebx, ebx
0x1800a3d54  test    r14, r14
0x1800a3d57  jnz     loc_1800A3DF9
0x1800a3d5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3d64  mov     [rbp+var_18], 80004003h
0x1800a3d6b  test    rcx, rcx
0x1800a3d6e  jnz     short loc_1800A3DB1
0x1800a3d70  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3d76  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3d7d  mov     rcx, rax
0x1800a3d80  test    rax, rax
0x1800a3d83  jz      short loc_1800A3DA3
0x1800a3d85  mov     rax, [rax]
0x1800a3d88  mov     edx, 7F0h
0x1800a3d8d  mov     rax, [rax+8]
0x1800a3d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d96  test    eax, eax
0x1800a3d98  jz      short loc_1800A3DA3
0x1800a3d9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3da1  jmp     short loc_1800A3DB1
0x1800a3da3  lea     rcx, qword_1801B07E0; this
0x1800a3daa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3db1  cmp     [rcx+8], bl
0x1800a3db4  jz      short loc_1800A3DE2
0x1800a3db6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3dbb  mov     r9d, [rbp+var_18]; int
0x1800a3dbf  test    r9d, r9d
0x1800a3dc2  jns     short loc_1800A3DE2
0x1800a3dc4  cmp     [rax+7CCh], r9d
0x1800a3dcb  jz      short loc_1800A3DE2
0x1800a3dcd  mov     r8d, 12Ch; int
0x1800a3dd3  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a3dda  mov     rcx, rax; this
0x1800a3ddd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3de2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3de9  jb      loc_1800A4191
0x1800a3def  mov     edx, 10h
0x1800a3df4  jmp     loc_1800A4170
0x1800a3df9  test    rsi, rsi
0x1800a3dfc  jnz     loc_1800A3E9E
0x1800a3e02  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e09  mov     [rbp+var_18], 80004003h
0x1800a3e10  test    rcx, rcx
0x1800a3e13  jnz     short loc_1800A3E56
0x1800a3e15  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3e1b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e22  mov     rcx, rax
0x1800a3e25  test    rax, rax
0x1800a3e28  jz      short loc_1800A3E48
0x1800a3e2a  mov     rax, [rax]
0x1800a3e2d  mov     edx, 7F0h
0x1800a3e32  mov     rax, [rax+8]
0x1800a3e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e3b  test    eax, eax
0x1800a3e3d  jz      short loc_1800A3E48
0x1800a3e3f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e46  jmp     short loc_1800A3E56
0x1800a3e48  lea     rcx, qword_1801B07E0; this
0x1800a3e4f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3e56  cmp     [rcx+8], bl
0x1800a3e59  jz      short loc_1800A3E87
0x1800a3e5b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3e60  mov     r9d, [rbp+var_18]; int
0x1800a3e64  test    r9d, r9d
0x1800a3e67  jns     short loc_1800A3E87
0x1800a3e69  cmp     [rax+7CCh], r9d
0x1800a3e70  jz      short loc_1800A3E87
0x1800a3e72  mov     r8d, 12Dh; int
0x1800a3e78  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a3e7f  mov     rcx, rax; this
0x1800a3e82  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3e87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3e8e  jb      loc_1800A4191
0x1800a3e94  mov     edx, 11h
0x1800a3e99  jmp     loc_1800A4170
0x1800a3e9e  cmp     [rbp+arg_20], rbx
0x1800a3ea2  jnz     loc_1800A3F44
0x1800a3ea8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3eaf  mov     [rbp+var_18], 80004003h
0x1800a3eb6  test    rcx, rcx
0x1800a3eb9  jnz     short loc_1800A3EFC
0x1800a3ebb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3ec1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3ec8  mov     rcx, rax
0x1800a3ecb  test    rax, rax
0x1800a3ece  jz      short loc_1800A3EEE
0x1800a3ed0  mov     rax, [rax]
0x1800a3ed3  mov     edx, 7F0h
0x1800a3ed8  mov     rax, [rax+8]
0x1800a3edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ee1  test    eax, eax
0x1800a3ee3  jz      short loc_1800A3EEE
0x1800a3ee5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3eec  jmp     short loc_1800A3EFC
0x1800a3eee  lea     rcx, qword_1801B07E0; this
0x1800a3ef5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3efc  cmp     [rcx+8], bl
0x1800a3eff  jz      short loc_1800A3F2D
0x1800a3f01  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3f06  mov     r9d, [rbp+var_18]; int
0x1800a3f0a  test    r9d, r9d
0x1800a3f0d  jns     short loc_1800A3F2D
0x1800a3f0f  cmp     [rax+7CCh], r9d
0x1800a3f16  jz      short loc_1800A3F2D
0x1800a3f18  mov     r8d, 12Eh; int
0x1800a3f1e  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a3f25  mov     rcx, rax; this
0x1800a3f28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a3f2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a3f34  jb      loc_1800A4191
0x1800a3f3a  mov     edx, 12h
0x1800a3f3f  jmp     loc_1800A4170
0x1800a3f44  mov     ecx, 530h; Size
0x1800a3f49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a3f4e  test    rax, rax
0x1800a3f51  jz      loc_1800A40DC
0x1800a3f57  lea     rcx, [rbp+var_18]
0x1800a3f5b  mov     r9, r12; struct IPropertyStore *
0x1800a3f5e  mov     [rsp+48h+var_20], rcx; int *
0x1800a3f63  mov     r8, rsi; struct IUnknown *
0x1800a3f66  mov     rcx, rax; this
0x1800a3f69  mov     [rsp+48h+var_28], r15d; unsigned int
0x1800a3f6e  mov     rdx, r14; struct IMFByteStream *
0x1800a3f71  call    ??0CMFByteStreamMediaSource@@AEAA@PEAUIMFByteStream@@PEAUIUnknown@@PEAUIPropertyStore@@KPEAJ@Z; CMFByteStreamMediaSource::CMFByteStreamMediaSource(IMFByteStream *,IUnknown *,IPropertyStore *,ulong,long *)
0x1800a3f76  mov     rbx, rax
0x1800a3f79  test    rax, rax
0x1800a3f7c  jz      loc_1800A40DC
0x1800a3f82  cmp     [rbp+var_18], 0
0x1800a3f86  jge     loc_1800A4022
0x1800a3f8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3f93  test    rcx, rcx
0x1800a3f96  jnz     short loc_1800A3FD9
0x1800a3f98  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a3f9e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3fa5  mov     rcx, rax
0x1800a3fa8  test    rax, rax
0x1800a3fab  jz      short loc_1800A3FCB
0x1800a3fad  mov     rax, [rax]
0x1800a3fb0  mov     edx, 7F0h
0x1800a3fb5  mov     rax, [rax+8]
0x1800a3fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fbe  test    eax, eax
0x1800a3fc0  jz      short loc_1800A3FCB
0x1800a3fc2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3fc9  jmp     short loc_1800A3FD9
0x1800a3fcb  lea     rcx, qword_1801B07E0; this
0x1800a3fd2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a3fd9  cmp     byte ptr [rcx+8], 0
0x1800a3fdd  jz      short loc_1800A400B
0x1800a3fdf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a3fe4  mov     r9d, [rbp+var_18]; int
0x1800a3fe8  test    r9d, r9d
0x1800a3feb  jns     short loc_1800A400B
0x1800a3fed  cmp     [rax+7CCh], r9d
0x1800a3ff4  jz      short loc_1800A400B
0x1800a3ff6  mov     r8d, 136h; int
0x1800a3ffc  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a4003  mov     rcx, rax; this
0x1800a4006  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a400b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4012  jb      loc_1800A4191
0x1800a4018  mov     edx, 14h
0x1800a401d  jmp     loc_1800A4170
0x1800a4022  mov     rax, [rax]
0x1800a4025  lea     rdx, IID_IMFMediaSource
0x1800a402c  mov     r8, [rbp+arg_20]
0x1800a4030  mov     rcx, rbx
0x1800a4033  mov     rax, [rax]
0x1800a4036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a403b  mov     [rbp+var_18], eax
0x1800a403e  test    eax, eax
0x1800a4040  jns     loc_1800A4191
0x1800a4046  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a404d  test    rcx, rcx
0x1800a4050  jnz     short loc_1800A4093
0x1800a4052  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a4058  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a405f  mov     rcx, rax
0x1800a4062  test    rax, rax
0x1800a4065  jz      short loc_1800A4085
0x1800a4067  mov     rax, [rax]
0x1800a406a  mov     edx, 7F0h
0x1800a406f  mov     rax, [rax+8]
0x1800a4073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4078  test    eax, eax
0x1800a407a  jz      short loc_1800A4085
0x1800a407c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4083  jmp     short loc_1800A4093
0x1800a4085  lea     rcx, qword_1801B07E0; this
0x1800a408c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4093  cmp     byte ptr [rcx+8], 0
0x1800a4097  jz      short loc_1800A40C5
0x1800a4099  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a409e  mov     r9d, [rbp+var_18]; int
0x1800a40a2  test    r9d, r9d
0x1800a40a5  jns     short loc_1800A40C5
0x1800a40a7  cmp     [rax+7CCh], r9d
0x1800a40ae  jz      short loc_1800A40C5
0x1800a40b0  mov     r8d, 138h; int
0x1800a40b6  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a40bd  mov     rcx, rax; this
0x1800a40c0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a40c5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a40cc  jb      loc_1800A4191
0x1800a40d2  mov     edx, 15h
0x1800a40d7  jmp     loc_1800A4170
0x1800a40dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a40e3  mov     [rbp+var_18], 8007000Eh
0x1800a40ea  test    rcx, rcx
0x1800a40ed  jnz     short loc_1800A4130
0x1800a40ef  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a40f5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a40fc  mov     rcx, rax
0x1800a40ff  test    rax, rax
0x1800a4102  jz      short loc_1800A4122
0x1800a4104  mov     rax, [rax]
0x1800a4107  mov     edx, 7F0h
0x1800a410c  mov     rax, [rax+8]
0x1800a4110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4115  test    eax, eax
0x1800a4117  jz      short loc_1800A4122
0x1800a4119  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4120  jmp     short loc_1800A4130
0x1800a4122  lea     rcx, qword_1801B07E0; this
0x1800a4129  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a4130  cmp     byte ptr [rcx+8], 0
0x1800a4134  jz      short loc_1800A4162
0x1800a4136  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a413b  mov     r9d, [rbp+var_18]; int
0x1800a413f  test    r9d, r9d
0x1800a4142  jns     short loc_1800A4162
0x1800a4144  cmp     [rax+7CCh], r9d
0x1800a414b  jz      short loc_1800A4162
0x1800a414d  mov     r8d, 135h; int
0x1800a4153  lea     rdx, aCmfbytestreamm_54; "CMFByteStreamMediaSource::CreateInstanc"...
0x1800a415a  mov     rcx, rax; this
0x1800a415d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a4162  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a4169  jb      short loc_1800A4191
0x1800a416b  mov     edx, 13h
0x1800a4170  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4177  lea     r8, WPP_5e453b2cf4a23e6c31bab848ed53fc63_Traceguids
0x1800a417e  mov     eax, [rbp+var_18]
0x1800a4181  xor     r9d, r9d
0x1800a4184  mov     [rsp+48h+var_28], eax
0x1800a4188  mov     rcx, [rcx+10h]
0x1800a418c  call    WPP_SF_qD
0x1800a4191  cmp     [rbp+var_18], 0
0x1800a4195  jge     short loc_1800A41B1
0x1800a4197  test    rbx, rbx
0x1800a419a  jz      short loc_1800A41B1
0x1800a419c  lea     rcx, [rbx+58h]
0x1800a41a0  mov     edx, 1
0x1800a41a5  mov     rax, [rcx]
0x1800a41a8  mov     rax, [rax+18h]
0x1800a41ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a41b1  mov     ebx, [rbp+var_18]
0x1800a41b4  lea     rcx, [rbp+arg_0]; this
0x1800a41b8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a41bd  mov     eax, ebx
0x1800a41bf  add     rsp, 48h
0x1800a41c3  pop     r15
0x1800a41c5  pop     r14
0x1800a41c7  pop     r12
0x1800a41c9  pop     rsi
0x1800a41ca  pop     rbx
0x1800a41cb  pop     rbp
0x1800a41cc  retn
```
