# CMFPropHandlerBase::Commit(void)

- ea: `0x180054b00`
- end: `0x180054d26`
- name: `?Commit@CMFPropHandlerBase@@UEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180054b00`
- `0x180058d38`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c3b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180054c3b`

## string_xrefs

- `0x180054b18`: `CMFPropHandlerBase::Commit`
- `0x180054bfc`: `CMFPropHandlerBase::Commit`
- `0x180054c98`: `CMFPropHandlerBase::Commit`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::Commit(CMFPropHandlerBase *this)
{
  __int64 v2; // rdx
  int v3; // ecx
  __int64 v4; // r8
  __int64 v5; // r9
  _DWORD *v6; // rdi
  __int64 v7; // rdx
  __int64 *v8; // rcx
  unsigned int v9; // esi
  __int64 v10; // r8
  __int64 v11; // r9
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  int v18; // [rsp+20h] [rbp-10h]
  int v19; // [rsp+20h] [rbp-10h]
  int v20; // [rsp+50h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v20, "CMFPropHandlerBase::Commit", 472);
  v6 = (_DWORD *)((char *)this - 8);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v18 = v6[220];
    v20 = 1096041805;
    McTemplateU0s4pq_EventWriteTransfer(
      v3,
      (unsigned int)&Property_Handler_Commit_Begin,
      (unsigned int)&v20,
      (_DWORD)this - 8,
      v18);
  }
  if ( *((_DWORD *)this + 225) )
  {
    v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 128LL))((char *)this - 8);
    if ( v9 == -2147418113 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      v9 = -2147287035;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v10, v11);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147287035 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::Commit", 491, -2147287035);
      }
      if ( g_wppLevels )
      {
        v14 = 39;
LABEL_25:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
          (char *)this - 8,
          -2147287035);
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    v9 = -2147287035;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v16 + 499) != -2147287035 )
        CallStackContext::TraceFailure(v16, "CMFPropHandlerBase::Commit", 496, -2147287035);
    }
    if ( g_wppLevels )
    {
      v14 = 40;
      goto LABEL_25;
    }
  }
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v19 = *((_DWORD *)this + 218);
    v20 = 1096041805;
    McTemplateU0s4pq_EventWriteTransfer(
      (_DWORD)v8,
      (unsigned int)&Property_Handler_Commit_End,
      (unsigned int)&v20,
      (_DWORD)this - 8,
      v19);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v20);
  return v9;
}

```

## disassembly

```asm
0x180054b00  mov     [rsp-18h+arg_8], rbx
0x180054b05  mov     [rsp-18h+arg_10], rsi
0x180054b0a  push    rbp
0x180054b0b  push    rdi
0x180054b0c  push    r14
0x180054b0e  mov     rbp, rsp
0x180054b11  sub     rsp, 30h
0x180054b15  mov     r14, rcx
0x180054b18  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x180054b1f  lea     rcx, [rbp+arg_0]; this
0x180054b23  mov     r8d, 1D8h; int
0x180054b29  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180054b2e  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180054b35  lea     rdi, [r14-8]
0x180054b39  jz      short loc_180054B5F
0x180054b3b  mov     eax, [rdi+370h]
0x180054b41  lea     r8, [rbp+arg_0]
0x180054b45  mov     r9, rdi
0x180054b48  mov     [rsp+30h+var_10], eax
0x180054b4c  lea     rdx, Property_Handler_Commit_Begin
0x180054b53  mov     [rbp+arg_0], 4154454Dh
0x180054b5a  call    McTemplateU0s4pq_EventWriteTransfer
0x180054b5f  cmp     dword ptr [r14+384h], 0
0x180054b67  jz      loc_180054C28
0x180054b6d  mov     rax, [rdi]
0x180054b70  mov     rcx, rdi
0x180054b73  mov     rax, [rax+80h]
0x180054b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b7f  mov     esi, eax
0x180054b81  cmp     eax, 8000FFFFh
0x180054b86  jnz     loc_180054CD9
0x180054b8c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054b93  mov     ebx, 80030005h
0x180054b98  mov     esi, ebx
0x180054b9a  test    rcx, rcx
0x180054b9d  jnz     short loc_180054BE6
0x180054b9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054ba6  nop     dword ptr [rax+rax+00h]
0x180054bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054bb2  mov     rcx, rax
0x180054bb5  test    rax, rax
0x180054bb8  jz      short loc_180054BD8
0x180054bba  mov     rax, [rax]
0x180054bbd  mov     edx, 7F0h
0x180054bc2  mov     rax, [rax+8]
0x180054bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bcb  test    eax, eax
0x180054bcd  jz      short loc_180054BD8
0x180054bcf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054bd6  jmp     short loc_180054BE6
0x180054bd8  lea     rcx, qword_1800DBF70; this
0x180054bdf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054be6  cmp     byte ptr [rcx+8], 0
0x180054bea  jz      short loc_180054C11
0x180054bec  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054bf1  cmp     [rax+7CCh], ebx
0x180054bf7  jz      short loc_180054C11
0x180054bf9  mov     r9d, ebx; int
0x180054bfc  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x180054c03  mov     r8d, 1EBh; int
0x180054c09  mov     rcx, rax; this
0x180054c0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054c11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054c18  jb      loc_180054CD9
0x180054c1e  mov     edx, 27h ; '''
0x180054c23  jmp     loc_180054CBB
0x180054c28  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c2f  mov     ebx, 80030005h
0x180054c34  mov     esi, ebx
0x180054c36  test    rcx, rcx
0x180054c39  jnz     short loc_180054C82
0x180054c3b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180054c42  nop     dword ptr [rax+rax+00h]
0x180054c47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c4e  mov     rcx, rax
0x180054c51  test    rax, rax
0x180054c54  jz      short loc_180054C74
0x180054c56  mov     rax, [rax]
0x180054c59  mov     edx, 7F0h
0x180054c5e  mov     rax, [rax+8]
0x180054c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c67  test    eax, eax
0x180054c69  jz      short loc_180054C74
0x180054c6b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c72  jmp     short loc_180054C82
0x180054c74  lea     rcx, qword_1800DBF70; this
0x180054c7b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180054c82  cmp     byte ptr [rcx+8], 0
0x180054c86  jz      short loc_180054CAD
0x180054c88  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180054c8d  cmp     [rax+7CCh], ebx
0x180054c93  jz      short loc_180054CAD
0x180054c95  mov     r9d, ebx; int
0x180054c98  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x180054c9f  mov     r8d, 1F0h; int
0x180054ca5  mov     rcx, rax; this
0x180054ca8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180054cad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054cb4  jb      short loc_180054CD9
0x180054cb6  mov     edx, 28h ; '('
0x180054cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180054cc2  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180054cc9  mov     r9, rdi
0x180054ccc  mov     [rsp+30h+var_10], ebx
0x180054cd0  mov     rcx, [rcx+10h]
0x180054cd4  call    WPP_SF_qD
0x180054cd9  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180054ce0  jz      short loc_180054D07
0x180054ce2  mov     eax, [r14+368h]
0x180054ce9  lea     r8, [rbp+arg_0]
0x180054ced  mov     r9, rdi
0x180054cf0  mov     [rsp+30h+var_10], eax
0x180054cf4  lea     rdx, Property_Handler_Commit_End
0x180054cfb  mov     [rbp+arg_0], 4154454Dh
0x180054d02  call    McTemplateU0s4pq_EventWriteTransfer
0x180054d07  lea     rcx, [rbp+arg_0]; this
0x180054d0b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180054d10  mov     rbx, [rsp+30h+arg_8]
0x180054d15  mov     eax, esi
0x180054d17  mov     rsi, [rsp+30h+arg_10]
0x180054d1c  add     rsp, 30h
0x180054d20  pop     r14
0x180054d22  pop     rdi
0x180054d23  pop     rbp
0x180054d24  retn
```
