# CMFPropHandlerBase::Commit(void)

- ea: `0x1800527b0`
- end: `0x1800529c9`
- name: `?Commit@CMFPropHandlerBase@@UEAAJXZ`
- size: `537`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800527b0`
- `0x180056854`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005284f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800528e5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005284f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800528e5`

## string_xrefs

- `0x1800527c8`: `CMFPropHandlerBase::Commit`
- `0x1800528a6`: `CMFPropHandlerBase::Commit`
- `0x18005293c`: `CMFPropHandlerBase::Commit`

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
      (unsigned int)Property_Handler_Commit_Begin,
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
          v8 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      (unsigned int)Property_Handler_Commit_End,
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
0x1800527b0  mov     [rsp-18h+arg_8], rbx
0x1800527b5  mov     [rsp-18h+arg_10], rsi
0x1800527ba  push    rbp
0x1800527bb  push    rdi
0x1800527bc  push    r14
0x1800527be  mov     rbp, rsp
0x1800527c1  sub     rsp, 30h
0x1800527c5  mov     r14, rcx
0x1800527c8  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x1800527cf  lea     rcx, [rbp+arg_0]; this
0x1800527d3  mov     r8d, 1D8h; int
0x1800527d9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800527de  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x1800527e5  lea     rdi, [r14-8]
0x1800527e9  jz      short loc_18005280F
0x1800527eb  mov     eax, [rdi+370h]
0x1800527f1  lea     r8, [rbp+arg_0]
0x1800527f5  mov     r9, rdi
0x1800527f8  mov     [rsp+30h+var_10], eax
0x1800527fc  lea     rdx, Property_Handler_Commit_Begin
0x180052803  mov     [rbp+arg_0], 4154454Dh
0x18005280a  call    McTemplateU0s4pq_EventWriteTransfer
0x18005280f  cmp     dword ptr [r14+384h], 0
0x180052817  jz      loc_1800528D2
0x18005281d  mov     rax, [rdi]
0x180052820  mov     rcx, rdi
0x180052823  mov     rax, [rax+80h]
0x18005282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005282f  mov     esi, eax
0x180052831  cmp     eax, 8000FFFFh
0x180052836  jnz     loc_18005297D
0x18005283c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052843  mov     ebx, 80030005h
0x180052848  mov     esi, ebx
0x18005284a  test    rcx, rcx
0x18005284d  jnz     short loc_180052890
0x18005284f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052855  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005285c  mov     rcx, rax
0x18005285f  test    rax, rax
0x180052862  jz      short loc_180052882
0x180052864  mov     rax, [rax]
0x180052867  mov     edx, 7F0h
0x18005286c  mov     rax, [rax+8]
0x180052870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052875  test    eax, eax
0x180052877  jz      short loc_180052882
0x180052879  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052880  jmp     short loc_180052890
0x180052882  lea     rcx, qword_1800D6F70; this
0x180052889  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052890  cmp     byte ptr [rcx+8], 0
0x180052894  jz      short loc_1800528BB
0x180052896  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005289b  cmp     [rax+7CCh], ebx
0x1800528a1  jz      short loc_1800528BB
0x1800528a3  mov     r9d, ebx; int
0x1800528a6  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x1800528ad  mov     r8d, 1EBh; int
0x1800528b3  mov     rcx, rax; this
0x1800528b6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800528bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800528c2  jb      loc_18005297D
0x1800528c8  mov     edx, 27h ; '''
0x1800528cd  jmp     loc_18005295F
0x1800528d2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528d9  mov     ebx, 80030005h
0x1800528de  mov     esi, ebx
0x1800528e0  test    rcx, rcx
0x1800528e3  jnz     short loc_180052926
0x1800528e5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800528eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800528f2  mov     rcx, rax
0x1800528f5  test    rax, rax
0x1800528f8  jz      short loc_180052918
0x1800528fa  mov     rax, [rax]
0x1800528fd  mov     edx, 7F0h
0x180052902  mov     rax, [rax+8]
0x180052906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005290b  test    eax, eax
0x18005290d  jz      short loc_180052918
0x18005290f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052916  jmp     short loc_180052926
0x180052918  lea     rcx, qword_1800D6F70; this
0x18005291f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052926  cmp     byte ptr [rcx+8], 0
0x18005292a  jz      short loc_180052951
0x18005292c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052931  cmp     [rax+7CCh], ebx
0x180052937  jz      short loc_180052951
0x180052939  mov     r9d, ebx; int
0x18005293c  lea     rdx, aCmfprophandler; "CMFPropHandlerBase::Commit"
0x180052943  mov     r8d, 1F0h; int
0x180052949  mov     rcx, rax; this
0x18005294c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052951  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052958  jb      short loc_18005297D
0x18005295a  mov     edx, 28h ; '('
0x18005295f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052966  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18005296d  mov     r9, rdi
0x180052970  mov     [rsp+30h+var_10], ebx
0x180052974  mov     rcx, [rcx+10h]
0x180052978  call    WPP_SF_qD
0x18005297d  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180052984  jz      short loc_1800529AB
0x180052986  mov     eax, [r14+368h]
0x18005298d  lea     r8, [rbp+arg_0]
0x180052991  mov     r9, rdi
0x180052994  mov     [rsp+30h+var_10], eax
0x180052998  lea     rdx, Property_Handler_Commit_End
0x18005299f  mov     [rbp+arg_0], 4154454Dh
0x1800529a6  call    McTemplateU0s4pq_EventWriteTransfer
0x1800529ab  lea     rcx, [rbp+arg_0]; this
0x1800529af  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800529b4  mov     rbx, [rsp+30h+arg_8]
0x1800529b9  mov     eax, esi
0x1800529bb  mov     rsi, [rsp+30h+arg_10]
0x1800529c0  add     rsp, 30h
0x1800529c4  pop     r14
0x1800529c6  pop     rdi
0x1800529c7  pop     rbp
0x1800529c8  retn
```
