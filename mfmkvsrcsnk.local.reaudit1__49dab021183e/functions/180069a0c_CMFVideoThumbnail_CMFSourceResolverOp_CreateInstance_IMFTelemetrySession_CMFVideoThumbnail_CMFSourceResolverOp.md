# CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(IMFTelemetrySession *,CMFVideoThumbnail::CMFSourceResolverOp * *)

- ea: `0x180069a0c`
- end: `0x180069bf3`
- name: `?CreateInstance@CMFSourceResolverOp@CMFVideoThumbnail@@SAJPEAUIMFTelemetrySession@@PEAPEAV12@@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct IMFTelemetrySession *, struct CMFVideoThumbnail::CMFSourceResolverOp **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180069134`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180066d04`
- `0x180069a0c`
- `0x18006eb18`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069b3d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180069b3d`

## string_xrefs

- `0x180069a1c`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x180069aaa`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x180069b9a`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(
        struct IMFTelemetrySession *a1,
        struct CMFVideoThumbnail::CMFSourceResolverOp **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 *v7; // rcx
  int v8; // ebx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CMFVideoThumbnail::CMFSourceResolverOp *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  struct CMFVideoThumbnail::CMFSourceResolverOp *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v21; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v21,
    "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance",
    2067);
  if ( a2 )
  {
    v12 = (CMFVideoThumbnail::CMFSourceResolverOp *)operator new(0x60u);
    if ( v12 )
    {
      v16 = (struct CMFVideoThumbnail::CMFSourceResolverOp *)CMFVideoThumbnail::CMFSourceResolverOp::CMFSourceResolverOp(
                                                               v12,
                                                               a1);
      *a2 = v16;
      if ( v16 )
      {
        v8 = CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(v16);
        if ( v8 < 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
          *a2 = 0;
        }
        goto LABEL_28;
      }
    }
    else
    {
      *a2 = 0;
    }
    v17 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v17 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v17 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance",
          2070,
          -2147024882);
    }
    if ( g_wppLevels )
    {
      v11 = 208;
      goto LABEL_27;
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    v8 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v10, "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance", 2067, -2147467261);
    }
    if ( g_wppLevels )
    {
      v11 = 207;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, 0, v8);
    }
  }
LABEL_28:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180069a0c  mov     [rsp+arg_0], rbx
0x180069a11  push    rdi
0x180069a12  sub     rsp, 30h
0x180069a16  mov     rdi, rdx
0x180069a19  mov     rbx, rcx
0x180069a1c  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180069a23  mov     r8d, 813h; int
0x180069a29  lea     rcx, [rsp+38h+arg_8]; this
0x180069a2e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180069a33  test    rdi, rdi
0x180069a36  jnz     loc_180069AD6
0x180069a3c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a43  mov     ebx, 80004003h
0x180069a48  test    rcx, rcx
0x180069a4b  jnz     short loc_180069A94
0x180069a4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069a54  nop     dword ptr [rax+rax+00h]
0x180069a59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a60  mov     rcx, rax
0x180069a63  test    rax, rax
0x180069a66  jz      short loc_180069A86
0x180069a68  mov     rax, [rax]
0x180069a6b  mov     edx, 7F0h
0x180069a70  mov     rax, [rax+8]
0x180069a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a79  test    eax, eax
0x180069a7b  jz      short loc_180069A86
0x180069a7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a84  jmp     short loc_180069A94
0x180069a86  lea     rcx, qword_1800DBF70; this
0x180069a8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069a94  cmp     byte ptr [rcx+8], 0
0x180069a98  jz      short loc_180069ABF
0x180069a9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069a9f  cmp     [rax+7CCh], ebx
0x180069aa5  jz      short loc_180069ABF
0x180069aa7  mov     r9d, ebx; int
0x180069aaa  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180069ab1  mov     r8d, 813h; int
0x180069ab7  mov     rcx, rax; this
0x180069aba  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069abf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069ac6  jb      loc_180069BDB
0x180069acc  mov     edx, 0CFh
0x180069ad1  jmp     loc_180069BBD
0x180069ad6  mov     ecx, 60h ; '`'; Size
0x180069adb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180069ae0  test    rax, rax
0x180069ae3  jz      short loc_180069B25
0x180069ae5  mov     rdx, rbx; struct IMFTelemetrySession *
0x180069ae8  mov     rcx, rax; this
0x180069aeb  call    ??0CMFSourceResolverOp@CMFVideoThumbnail@@QEAA@PEAUIMFTelemetrySession@@@Z; CMFVideoThumbnail::CMFSourceResolverOp::CMFSourceResolverOp(IMFTelemetrySession *)
0x180069af0  mov     [rdi], rax
0x180069af3  test    rax, rax
0x180069af6  jz      short loc_180069B2C
0x180069af8  mov     rcx, rax; this
0x180069afb  call    ?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)
0x180069b00  mov     ebx, eax
0x180069b02  test    eax, eax
0x180069b04  jns     loc_180069BDB
0x180069b0a  mov     rcx, [rdi]
0x180069b0d  mov     rdx, [rcx]
0x180069b10  mov     rax, [rdx+10h]
0x180069b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b19  mov     qword ptr [rdi], 0
0x180069b20  jmp     loc_180069BDB
0x180069b25  mov     qword ptr [rdi], 0
0x180069b2c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b33  mov     ebx, 8007000Eh
0x180069b38  test    rcx, rcx
0x180069b3b  jnz     short loc_180069B84
0x180069b3d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180069b44  nop     dword ptr [rax+rax+00h]
0x180069b49  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b50  mov     rcx, rax
0x180069b53  test    rax, rax
0x180069b56  jz      short loc_180069B76
0x180069b58  mov     rax, [rax]
0x180069b5b  mov     edx, 7F0h
0x180069b60  mov     rax, [rax+8]
0x180069b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b69  test    eax, eax
0x180069b6b  jz      short loc_180069B76
0x180069b6d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b74  jmp     short loc_180069B84
0x180069b76  lea     rcx, qword_1800DBF70; this
0x180069b7d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180069b84  cmp     byte ptr [rcx+8], 0
0x180069b88  jz      short loc_180069BAF
0x180069b8a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180069b8f  cmp     [rax+7CCh], ebx
0x180069b95  jz      short loc_180069BAF
0x180069b97  mov     r9d, ebx; int
0x180069b9a  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180069ba1  mov     r8d, 816h; int
0x180069ba7  mov     rcx, rax; this
0x180069baa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180069baf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180069bb6  jb      short loc_180069BDB
0x180069bb8  mov     edx, 0D0h
0x180069bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180069bc4  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180069bcb  xor     r9d, r9d
0x180069bce  mov     [rsp+38h+var_18], ebx
0x180069bd2  mov     rcx, [rcx+10h]
0x180069bd6  call    WPP_SF_qD
0x180069bdb  lea     rcx, [rsp+38h+arg_8]; this
0x180069be0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180069be5  mov     eax, ebx
0x180069be7  mov     rbx, [rsp+38h+arg_0]
0x180069bec  add     rsp, 30h
0x180069bf0  pop     rdi
0x180069bf1  retn
```
