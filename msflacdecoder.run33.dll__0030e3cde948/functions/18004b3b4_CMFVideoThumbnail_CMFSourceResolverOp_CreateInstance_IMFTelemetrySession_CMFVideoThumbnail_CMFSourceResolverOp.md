# CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(IMFTelemetrySession *,CMFVideoThumbnail::CMFSourceResolverOp * *)

- ea: `0x18004b3b4`
- end: `0x18004b5f0`
- name: `?CreateInstance@CMFSourceResolverOp@CMFVideoThumbnail@@SAJPEAUIMFTelemetrySession@@PEAPEAV12@@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct IMFTelemetrySession *, struct CMFVideoThumbnail::CMFSourceResolverOp **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18004ab18`

## callees

- `0x1800018a4`
- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x180048a88`
- `0x18004b3b4`
- `0x180050334`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b4d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004b4d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b3fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b53c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b3fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b53c`

## string_xrefs

- `0x18004b3c9`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x18004b451`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x18004b593`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`

## pseudocode

```c
__int64 __fastcall CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(
        struct IMFTelemetrySession *a1,
        struct CMFVideoThumbnail::CMFSourceResolverOp **a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int v6; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  _DWORD *v10; // rax
  __int64 v11; // rdx
  _DWORD *v12; // rbx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v17; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v17,
    "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance",
    2067);
  if ( a2 )
  {
    v10 = operator new(0x60u);
    v12 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = &CBaseUnknown::`vftable';
      v10[2] = 1;
      *(_QWORD *)v10 = &CMFVideoThumbnail::CMFSourceResolverOp::`vftable';
      CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback::OnSourceResolutionAsyncCallback((CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback *)(v10 + 4));
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
      v12[10] = 0;
      *((_BYTE *)v12 + 44) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 12));
      *((_QWORD *)v12 + 11) = a1;
      if ( a1 )
        (*(void (__fastcall **)(struct IMFTelemetrySession *))(*(_QWORD *)a1 + 8LL))(a1);
      *a2 = (struct CMFVideoThumbnail::CMFSourceResolverOp *)v12;
      v6 = CMFVideoThumbnail::CMFSourceResolverOp::_Initialize((CMFVideoThumbnail::CMFSourceResolverOp *)v12);
      if ( v6 < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
        *a2 = 0;
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      v6 = -2147024882;
      *a2 = 0;
      if ( !v13 )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance",
            2070,
            -2147024882);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 208;
        goto LABEL_27;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    v6 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance", 2067, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 207;
LABEL_27:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids, 0, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004b3b4  mov     [rsp+arg_0], rbx
0x18004b3b9  mov     [rsp+arg_10], rsi
0x18004b3be  push    rdi
0x18004b3bf  sub     rsp, 30h
0x18004b3c3  mov     rdi, rdx
0x18004b3c6  mov     rsi, rcx
0x18004b3c9  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004b3d0  mov     r8d, 813h; int
0x18004b3d6  lea     rcx, [rsp+38h+arg_8]; this
0x18004b3db  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004b3e0  test    rdi, rdi
0x18004b3e3  jnz     loc_18004B47D
0x18004b3e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b3f0  mov     ebx, 80004003h
0x18004b3f5  test    rcx, rcx
0x18004b3f8  jnz     short loc_18004B43B
0x18004b3fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b400  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b407  mov     rcx, rax
0x18004b40a  test    rax, rax
0x18004b40d  jz      short loc_18004B42D
0x18004b40f  mov     rax, [rax]
0x18004b412  mov     edx, 7F0h
0x18004b417  mov     rax, [rax+8]
0x18004b41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b420  test    eax, eax
0x18004b422  jz      short loc_18004B42D
0x18004b424  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b42b  jmp     short loc_18004B43B
0x18004b42d  lea     rcx, qword_18006EB20; this
0x18004b434  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b43b  cmp     byte ptr [rcx+8], 0
0x18004b43f  jz      short loc_18004B466
0x18004b441  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b446  cmp     [rax+7CCh], ebx
0x18004b44c  jz      short loc_18004B466
0x18004b44e  mov     r9d, ebx; int
0x18004b451  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004b458  mov     r8d, 813h; int
0x18004b45e  mov     rcx, rax; this
0x18004b461  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b466  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b46b  cmp     al, 1
0x18004b46d  jb      loc_18004B5D4
0x18004b473  mov     edx, 0CFh
0x18004b478  jmp     loc_18004B5B6
0x18004b47d  mov     ecx, 60h ; '`'; Size
0x18004b482  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b487  mov     rbx, rax
0x18004b48a  test    rax, rax
0x18004b48d  jz      loc_18004B524
0x18004b493  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x18004b49a  mov     [rbx], rax
0x18004b49d  lea     rcx, [rbx+10h]; this
0x18004b4a1  lea     rax, ??_7CMFSourceResolverOp@CMFVideoThumbnail@@6B@; const CMFVideoThumbnail::CMFSourceResolverOp::`vftable'
0x18004b4a8  mov     dword ptr [rbx+8], 1
0x18004b4af  mov     [rbx], rax
0x18004b4b2  call    ??0OnSourceResolutionAsyncCallback@CMFSourceResolverOp@CMFVideoThumbnail@@QEAA@XZ; CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback::OnSourceResolutionAsyncCallback(void)
0x18004b4b7  mov     qword ptr [rbx+18h], 0
0x18004b4bf  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004b4c3  mov     qword ptr [rbx+20h], 0
0x18004b4cb  mov     dword ptr [rbx+28h], 0
0x18004b4d2  mov     byte ptr [rbx+2Ch], 0
0x18004b4d6  call    cs:__imp_InitializeCriticalSection
0x18004b4dc  mov     [rbx+58h], rsi
0x18004b4e0  test    rsi, rsi
0x18004b4e3  jz      short loc_18004B4F4
0x18004b4e5  mov     rax, [rsi]
0x18004b4e8  mov     rcx, rsi
0x18004b4eb  mov     rax, [rax+8]
0x18004b4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4f4  mov     rcx, rbx; this
0x18004b4f7  mov     [rdi], rbx
0x18004b4fa  call    ?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)
0x18004b4ff  mov     ebx, eax
0x18004b501  test    eax, eax
0x18004b503  jns     loc_18004B5D4
0x18004b509  mov     rcx, [rdi]
0x18004b50c  mov     rdx, [rcx]
0x18004b50f  mov     rax, [rdx+10h]
0x18004b513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b518  mov     qword ptr [rdi], 0
0x18004b51f  jmp     loc_18004B5D4
0x18004b524  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b52b  mov     ebx, 8007000Eh
0x18004b530  mov     qword ptr [rdi], 0
0x18004b537  test    rcx, rcx
0x18004b53a  jnz     short loc_18004B57D
0x18004b53c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b542  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b549  mov     rcx, rax
0x18004b54c  test    rax, rax
0x18004b54f  jz      short loc_18004B56F
0x18004b551  mov     rax, [rax]
0x18004b554  mov     edx, 7F0h
0x18004b559  mov     rax, [rax+8]
0x18004b55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b562  test    eax, eax
0x18004b564  jz      short loc_18004B56F
0x18004b566  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b56d  jmp     short loc_18004B57D
0x18004b56f  lea     rcx, qword_18006EB20; this
0x18004b576  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b57d  cmp     byte ptr [rcx+8], 0
0x18004b581  jz      short loc_18004B5A8
0x18004b583  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b588  cmp     [rax+7CCh], ebx
0x18004b58e  jz      short loc_18004B5A8
0x18004b590  mov     r9d, ebx; int
0x18004b593  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x18004b59a  mov     r8d, 816h; int
0x18004b5a0  mov     rcx, rax; this
0x18004b5a3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b5a8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004b5ad  cmp     al, 1
0x18004b5af  jb      short loc_18004B5D4
0x18004b5b1  mov     edx, 0D0h
0x18004b5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b5bd  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x18004b5c4  xor     r9d, r9d
0x18004b5c7  mov     [rsp+38h+var_18], ebx
0x18004b5cb  mov     rcx, [rcx+10h]
0x18004b5cf  call    WPP_SF_qd
0x18004b5d4  lea     rcx, [rsp+38h+arg_8]; this
0x18004b5d9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004b5de  mov     rsi, [rsp+38h+arg_10]
0x18004b5e3  mov     eax, ebx
0x18004b5e5  mov     rbx, [rsp+38h+arg_0]
0x18004b5ea  add     rsp, 30h
0x18004b5ee  pop     rdi
0x18004b5ef  retn
```
