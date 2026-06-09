# CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance(IMFTelemetrySession *,CMFVideoThumbnail::CMFSourceResolverOp * *)

- ea: `0x180066d9c`
- end: `0x180066fd8`
- name: `?CreateInstance@CMFSourceResolverOp@CMFVideoThumbnail@@SAJPEAUIMFTelemetrySession@@PEAPEAV12@@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct IMFTelemetrySession *, struct CMFVideoThumbnail::CMFSourceResolverOp **)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180066500`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800643ac`
- `0x180066d9c`
- `0x18006bd44`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066ebe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180066ebe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066f24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066de2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180066f24`

## string_xrefs

- `0x180066db1`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x180066e39`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`
- `0x180066f7b`: `CMFVideoThumbnail::CMFSourceResolverOp::CreateInstance`

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
  _DWORD *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  _DWORD *v16; // rbx
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
    v12 = operator new(0x60u);
    v16 = v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = &CBaseUnknown::`vftable';
      v12[2] = 1;
      *(_QWORD *)v12 = &CMFVideoThumbnail::CMFSourceResolverOp::`vftable';
      CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback::OnSourceResolutionAsyncCallback((CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback *)(v12 + 4));
      *((_QWORD *)v16 + 3) = 0;
      *((_QWORD *)v16 + 4) = 0;
      v16[10] = 0;
      *((_BYTE *)v16 + 44) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v16 + 12));
      *((_QWORD *)v16 + 11) = a1;
      if ( a1 )
        (*(void (__fastcall **)(struct IMFTelemetrySession *))(*(_QWORD *)a1 + 8LL))(a1);
      *a2 = (struct CMFVideoThumbnail::CMFSourceResolverOp *)v16;
      v8 = CMFVideoThumbnail::CMFSourceResolverOp::_Initialize((CMFVideoThumbnail::CMFSourceResolverOp *)v16);
      if ( v8 < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
        *a2 = 0;
      }
    }
    else
    {
      v17 = (__int64 *)CallStackTracing::s_wpInstance;
      v8 = -2147024882;
      *a2 = 0;
      if ( !v17 )
      {
        v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14, v15);
        CallStackTracing::s_wpInstance = v18;
        if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v7 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180066d9c  mov     [rsp+arg_0], rbx
0x180066da1  mov     [rsp+arg_10], rsi
0x180066da6  push    rdi
0x180066da7  sub     rsp, 30h
0x180066dab  mov     rdi, rdx
0x180066dae  mov     rsi, rcx
0x180066db1  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180066db8  mov     r8d, 813h; int
0x180066dbe  lea     rcx, [rsp+38h+arg_8]; this
0x180066dc3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180066dc8  test    rdi, rdi
0x180066dcb  jnz     loc_180066E65
0x180066dd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066dd8  mov     ebx, 80004003h
0x180066ddd  test    rcx, rcx
0x180066de0  jnz     short loc_180066E23
0x180066de2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066de8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066def  mov     rcx, rax
0x180066df2  test    rax, rax
0x180066df5  jz      short loc_180066E15
0x180066df7  mov     rax, [rax]
0x180066dfa  mov     edx, 7F0h
0x180066dff  mov     rax, [rax+8]
0x180066e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e08  test    eax, eax
0x180066e0a  jz      short loc_180066E15
0x180066e0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066e13  jmp     short loc_180066E23
0x180066e15  lea     rcx, qword_1800D6F70; this
0x180066e1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180066e23  cmp     byte ptr [rcx+8], 0
0x180066e27  jz      short loc_180066E4E
0x180066e29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066e2e  cmp     [rax+7CCh], ebx
0x180066e34  jz      short loc_180066E4E
0x180066e36  mov     r9d, ebx; int
0x180066e39  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180066e40  mov     r8d, 813h; int
0x180066e46  mov     rcx, rax; this
0x180066e49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066e4e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066e55  jb      loc_180066FBC
0x180066e5b  mov     edx, 0CFh
0x180066e60  jmp     loc_180066F9E
0x180066e65  mov     ecx, 60h ; '`'; Size
0x180066e6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066e6f  mov     rbx, rax
0x180066e72  test    rax, rax
0x180066e75  jz      loc_180066F0C
0x180066e7b  lea     rax, ??_7CBaseUnknown@@6B@; const CBaseUnknown::`vftable'
0x180066e82  mov     [rbx], rax
0x180066e85  lea     rcx, [rbx+10h]; this
0x180066e89  lea     rax, ??_7CMFSourceResolverOp@CMFVideoThumbnail@@6B@; const CMFVideoThumbnail::CMFSourceResolverOp::`vftable'
0x180066e90  mov     dword ptr [rbx+8], 1
0x180066e97  mov     [rbx], rax
0x180066e9a  call    ??0OnSourceResolutionAsyncCallback@CMFSourceResolverOp@CMFVideoThumbnail@@QEAA@XZ; CMFVideoThumbnail::CMFSourceResolverOp::OnSourceResolutionAsyncCallback::OnSourceResolutionAsyncCallback(void)
0x180066e9f  mov     qword ptr [rbx+18h], 0
0x180066ea7  lea     rcx, [rbx+30h]; lpCriticalSection
0x180066eab  mov     qword ptr [rbx+20h], 0
0x180066eb3  mov     dword ptr [rbx+28h], 0
0x180066eba  mov     byte ptr [rbx+2Ch], 0
0x180066ebe  call    cs:__imp_InitializeCriticalSection
0x180066ec4  mov     [rbx+58h], rsi
0x180066ec8  test    rsi, rsi
0x180066ecb  jz      short loc_180066EDC
0x180066ecd  mov     rax, [rsi]
0x180066ed0  mov     rcx, rsi
0x180066ed3  mov     rax, [rax+8]
0x180066ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066edc  mov     rcx, rbx; this
0x180066edf  mov     [rdi], rbx
0x180066ee2  call    ?_Initialize@CMFSourceResolverOp@CMFVideoThumbnail@@AEAAJXZ; CMFVideoThumbnail::CMFSourceResolverOp::_Initialize(void)
0x180066ee7  mov     ebx, eax
0x180066ee9  test    eax, eax
0x180066eeb  jns     loc_180066FBC
0x180066ef1  mov     rcx, [rdi]
0x180066ef4  mov     rdx, [rcx]
0x180066ef7  mov     rax, [rdx+10h]
0x180066efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f00  mov     qword ptr [rdi], 0
0x180066f07  jmp     loc_180066FBC
0x180066f0c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066f13  mov     ebx, 8007000Eh
0x180066f18  mov     qword ptr [rdi], 0
0x180066f1f  test    rcx, rcx
0x180066f22  jnz     short loc_180066F65
0x180066f24  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180066f2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180066f31  mov     rcx, rax
0x180066f34  test    rax, rax
0x180066f37  jz      short loc_180066F57
0x180066f39  mov     rax, [rax]
0x180066f3c  mov     edx, 7F0h
0x180066f41  mov     rax, [rax+8]
0x180066f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f4a  test    eax, eax
0x180066f4c  jz      short loc_180066F57
0x180066f4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180066f55  jmp     short loc_180066F65
0x180066f57  lea     rcx, qword_1800D6F70; this
0x180066f5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180066f65  cmp     byte ptr [rcx+8], 0
0x180066f69  jz      short loc_180066F90
0x180066f6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180066f70  cmp     [rax+7CCh], ebx
0x180066f76  jz      short loc_180066F90
0x180066f78  mov     r9d, ebx; int
0x180066f7b  lea     rdx, aCmfvideothumbn_14; "CMFVideoThumbnail::CMFSourceResolverOp:"...
0x180066f82  mov     r8d, 816h; int
0x180066f88  mov     rcx, rax; this
0x180066f8b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180066f90  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066f97  jb      short loc_180066FBC
0x180066f99  mov     edx, 0D0h
0x180066f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fa5  lea     r8, WPP_6245028be7c734f6f2ef00cca7760f57_Traceguids
0x180066fac  xor     r9d, r9d
0x180066faf  mov     [rsp+38h+var_18], ebx
0x180066fb3  mov     rcx, [rcx+10h]
0x180066fb7  call    WPP_SF_qD
0x180066fbc  lea     rcx, [rsp+38h+arg_8]; this
0x180066fc1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180066fc6  mov     rsi, [rsp+38h+arg_10]
0x180066fcb  mov     eax, ebx
0x180066fcd  mov     rbx, [rsp+38h+arg_0]
0x180066fd2  add     rsp, 30h
0x180066fd6  pop     rdi
0x180066fd7  retn
```
