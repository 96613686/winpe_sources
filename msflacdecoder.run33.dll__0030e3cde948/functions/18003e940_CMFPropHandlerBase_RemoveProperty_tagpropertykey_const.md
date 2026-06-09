# CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x18003e940`
- end: `0x18003ea67`
- name: `?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x1800459c0`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003e688`
- `0x18003e770`
- `0x18003e940`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e9b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e9b8`

## string_xrefs

- `0x18003e950`: `CMFPropHandlerBase::RemoveProperty`
- `0x18003ea0f`: `CMFPropHandlerBase::RemoveProperty`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::RemoveProperty(CMFPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CMFPropHandlerBase::RemoveProperty", 605);
  v10 = 0;
  CTBucketHash<_tagpropertykey,CMFProperty *>::Remove((char *)this + 48, a2, &v10);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v5 = CMFPropHandlerBase::RemoveKey(this, a2);
  if ( v5 < 0 )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::RemoveProperty", 613, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v5);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e940  mov     [rsp+arg_8], rbx
0x18003e945  push    rdi
0x18003e946  sub     rsp, 30h
0x18003e94a  mov     rbx, rdx
0x18003e94d  mov     rdi, rcx
0x18003e950  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x18003e957  mov     r8d, 25Dh; int
0x18003e95d  lea     rcx, [rsp+38h+arg_0]; this
0x18003e962  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003e967  lea     rcx, [rdi+30h]
0x18003e96b  mov     [rsp+38h+arg_0], 0
0x18003e974  lea     r8, [rsp+38h+arg_0]
0x18003e979  mov     rdx, rbx
0x18003e97c  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x18003e981  mov     rcx, [rsp+38h+arg_0]
0x18003e986  test    rcx, rcx
0x18003e989  jz      short loc_18003E997
0x18003e98b  mov     rax, [rcx]
0x18003e98e  mov     rax, [rax+10h]
0x18003e992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e997  mov     rdx, rbx; struct _tagpropertykey *
0x18003e99a  mov     rcx, rdi; this
0x18003e99d  call    ?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)
0x18003e9a2  mov     ebx, eax
0x18003e9a4  test    eax, eax
0x18003e9a6  jns     loc_18003EA50
0x18003e9ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9b3  test    rcx, rcx
0x18003e9b6  jnz     short loc_18003E9F9
0x18003e9b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e9be  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9c5  mov     rcx, rax
0x18003e9c8  test    rax, rax
0x18003e9cb  jz      short loc_18003E9EB
0x18003e9cd  mov     rax, [rax]
0x18003e9d0  mov     edx, 7F0h
0x18003e9d5  mov     rax, [rax+8]
0x18003e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9de  test    eax, eax
0x18003e9e0  jz      short loc_18003E9EB
0x18003e9e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9e9  jmp     short loc_18003E9F9
0x18003e9eb  lea     rcx, qword_18006EB20; this
0x18003e9f2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9f9  cmp     byte ptr [rcx+8], 0
0x18003e9fd  jz      short loc_18003EA24
0x18003e9ff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003ea04  cmp     [rax+7CCh], ebx
0x18003ea0a  jz      short loc_18003EA24
0x18003ea0c  mov     r9d, ebx; int
0x18003ea0f  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x18003ea16  mov     r8d, 265h; int
0x18003ea1c  mov     rcx, rax; this
0x18003ea1f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003ea24  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003ea29  cmp     al, 1
0x18003ea2b  jb      short loc_18003EA50
0x18003ea2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea34  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003ea3b  mov     edx, 33h ; '3'
0x18003ea40  mov     [rsp+38h+var_18], ebx
0x18003ea44  mov     r9, rdi
0x18003ea47  mov     rcx, [rcx+10h]
0x18003ea4b  call    WPP_SF_qd
0x18003ea50  lea     rcx, [rsp+38h+arg_0]; this
0x18003ea55  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003ea5a  mov     eax, ebx
0x18003ea5c  mov     rbx, [rsp+38h+arg_8]
0x18003ea61  add     rsp, 30h
0x18003ea65  pop     rdi
0x18003ea66  retn
```
