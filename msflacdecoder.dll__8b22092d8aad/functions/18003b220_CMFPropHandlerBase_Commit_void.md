# CMFPropHandlerBase::Commit(void)

- ea: `0x18003b220`
- end: `0x18003b439`
- name: `?Commit@CMFPropHandlerBase@@UEAAJXZ`
- size: `537`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003b220`
- `0x18003f2f4`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b2bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b355`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b2bf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b355`

## string_xrefs

- `0x18003b238`: `CMFPropHandlerBase::Commit`
- `0x18003b316`: `CMFPropHandlerBase::Commit`
- `0x18003b3ac`: `CMFPropHandlerBase::Commit`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::Commit(CMFPropHandlerBase *this)
{
  __int64 v2; // rdx
  int v3; // ecx
  _DWORD *v4; // rdi
  __int64 v5; // rdx
  int v6; // ecx
  unsigned int v7; // esi
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  int v16; // [rsp+20h] [rbp-20h]
  int v17; // [rsp+20h] [rbp-20h]
  _BYTE v18[4]; // [rsp+30h] [rbp-10h] BYREF
  _DWORD v19[3]; // [rsp+34h] [rbp-Ch] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v18, "CMFPropHandlerBase::Commit", 472);
  v4 = (_DWORD *)((char *)this - 8);
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v16 = v4[220];
    v19[0] = 1096041805;
    McTemplateU0s4pq_EventWriteTransfer(
      v3,
      (unsigned int)Property_Handler_Commit_Begin,
      (unsigned int)v19,
      (_DWORD)this - 8,
      v16);
  }
  if ( *((_DWORD *)this + 225) )
  {
    v7 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v4 + 128LL))((char *)this - 8);
    if ( v7 == -2147418113 )
    {
      v8 = (__int64 *)CallStackTracing::s_wpInstance;
      v7 = -2147287035;
      if ( !CallStackTracing::s_wpInstance )
      {
        v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v9;
        if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
        {
          v8 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v8 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147287035 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::Commit", 491, -2147287035);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 39;
LABEL_25:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
          (char *)this - 8,
          -2147287035);
      }
    }
  }
  else
  {
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147287035;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != -2147287035 )
        CallStackContext::TraceFailure(v14, "CMFPropHandlerBase::Commit", 496, -2147287035);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 40;
      goto LABEL_25;
    }
  }
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v17 = *((_DWORD *)this + 218);
    v19[0] = 1096041805;
    McTemplateU0s4pq_EventWriteTransfer(
      v6,
      (unsigned int)Property_Handler_Commit_End,
      (unsigned int)v19,
      (_DWORD)this - 8,
      v17);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v18);
  return v7;
}

```

## disassembly

```asm
0x18003b220  mov     [rsp-18h+arg_8], rbx
0x18003b225  mov     [rsp-18h+arg_10], rsi
0x18003b22a  push    rbp
0x18003b22b  push    rdi
0x18003b22c  push    r14
0x18003b22e  mov     rbp, rsp
0x18003b231  sub     rsp, 40h
0x18003b235  mov     r14, rcx
0x18003b238  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x18003b23f  lea     rcx, [rbp+var_10]; this
0x18003b243  mov     r8d, 1D8h; int
0x18003b249  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b24e  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18003b255  lea     rdi, [r14-8]
0x18003b259  jz      short loc_18003B27F
0x18003b25b  mov     eax, [rdi+370h]
0x18003b261  lea     r8, [rbp+var_C]
0x18003b265  mov     r9, rdi
0x18003b268  mov     [rsp+40h+var_20], eax
0x18003b26c  lea     rdx, Property_Handler_Commit_Begin
0x18003b273  mov     [rbp+var_C], 4154454Dh
0x18003b27a  call    McTemplateU0s4pq_EventWriteTransfer
0x18003b27f  cmp     dword ptr [r14+384h], 0
0x18003b287  jz      loc_18003B342
0x18003b28d  mov     rax, [rdi]
0x18003b290  mov     rcx, rdi
0x18003b293  mov     rax, [rax+80h]
0x18003b29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b29f  mov     esi, eax
0x18003b2a1  cmp     eax, 8000FFFFh
0x18003b2a6  jnz     loc_18003B3ED
0x18003b2ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b2b3  mov     ebx, 80030005h
0x18003b2b8  mov     esi, ebx
0x18003b2ba  test    rcx, rcx
0x18003b2bd  jnz     short loc_18003B300
0x18003b2bf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b2c5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b2cc  mov     rcx, rax
0x18003b2cf  test    rax, rax
0x18003b2d2  jz      short loc_18003B2F2
0x18003b2d4  mov     rax, [rax]
0x18003b2d7  mov     edx, 7F0h
0x18003b2dc  mov     rax, [rax+8]
0x18003b2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2e5  test    eax, eax
0x18003b2e7  jz      short loc_18003B2F2
0x18003b2e9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b2f0  jmp     short loc_18003B300
0x18003b2f2  lea     rcx, qword_18006EB20; this
0x18003b2f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b300  cmp     byte ptr [rcx+8], 0
0x18003b304  jz      short loc_18003B32B
0x18003b306  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b30b  cmp     [rax+7CCh], ebx
0x18003b311  jz      short loc_18003B32B
0x18003b313  mov     r9d, ebx; int
0x18003b316  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x18003b31d  mov     r8d, 1EBh; int
0x18003b323  mov     rcx, rax; this
0x18003b326  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b32b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b330  cmp     al, 1
0x18003b332  jb      loc_18003B3ED
0x18003b338  mov     edx, 27h ; '''
0x18003b33d  jmp     loc_18003B3CF
0x18003b342  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b349  mov     ebx, 80030005h
0x18003b34e  mov     esi, ebx
0x18003b350  test    rcx, rcx
0x18003b353  jnz     short loc_18003B396
0x18003b355  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b35b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b362  mov     rcx, rax
0x18003b365  test    rax, rax
0x18003b368  jz      short loc_18003B388
0x18003b36a  mov     rax, [rax]
0x18003b36d  mov     edx, 7F0h
0x18003b372  mov     rax, [rax+8]
0x18003b376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b37b  test    eax, eax
0x18003b37d  jz      short loc_18003B388
0x18003b37f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b386  jmp     short loc_18003B396
0x18003b388  lea     rcx, qword_18006EB20; this
0x18003b38f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b396  cmp     byte ptr [rcx+8], 0
0x18003b39a  jz      short loc_18003B3C1
0x18003b39c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b3a1  cmp     [rax+7CCh], ebx
0x18003b3a7  jz      short loc_18003B3C1
0x18003b3a9  mov     r9d, ebx; int
0x18003b3ac  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x18003b3b3  mov     r8d, 1F0h; int
0x18003b3b9  mov     rcx, rax; this
0x18003b3bc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b3c1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b3c6  cmp     al, 1
0x18003b3c8  jb      short loc_18003B3ED
0x18003b3ca  mov     edx, 28h ; '('
0x18003b3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3d6  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003b3dd  mov     r9, rdi
0x18003b3e0  mov     [rsp+40h+var_20], ebx
0x18003b3e4  mov     rcx, [rcx+10h]
0x18003b3e8  call    WPP_SF_qd
0x18003b3ed  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x18003b3f4  jz      short loc_18003B41B
0x18003b3f6  mov     eax, [r14+368h]
0x18003b3fd  lea     r8, [rbp+var_C]
0x18003b401  mov     r9, rdi
0x18003b404  mov     [rsp+40h+var_20], eax
0x18003b408  lea     rdx, Property_Handler_Commit_End
0x18003b40f  mov     [rbp+var_C], 4154454Dh
0x18003b416  call    McTemplateU0s4pq_EventWriteTransfer
0x18003b41b  lea     rcx, [rbp+var_10]; this
0x18003b41f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b424  mov     rbx, [rsp+40h+arg_8]
0x18003b429  mov     eax, esi
0x18003b42b  mov     rsi, [rsp+40h+arg_10]
0x18003b430  add     rsp, 40h
0x18003b434  pop     r14
0x18003b436  pop     rdi
0x18003b437  pop     rbp
0x18003b438  retn
```
