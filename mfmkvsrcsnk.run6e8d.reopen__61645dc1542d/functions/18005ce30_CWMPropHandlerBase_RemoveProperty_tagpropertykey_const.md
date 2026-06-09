# CWMPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x18005ce30`
- end: `0x18005cf6a`
- name: `?RemoveProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180055ce4`
- `0x180055f90`
- `0x18005ce30`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce86`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005ce86`

## string_xrefs

- `0x18005ce45`: `CWMPropHandlerBase::RemoveProperty`
- `0x18005cedd`: `CWMPropHandlerBase::RemoveProperty`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::RemoveProperty(CWMPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CWMPropHandlerBase::RemoveProperty", 916);
  v12 = 0;
  v5 = CMFPropHandlerBase::RemoveProperty(this, a2);
  if ( v5 >= 0 )
  {
    if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Remove((char *)this + 1304, a2, &v12) && v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v6, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::RemoveProperty", 921, v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v5);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005ce30  mov     [rsp+arg_0], rbx
0x18005ce35  mov     [rsp+arg_8], rsi
0x18005ce3a  push    rdi
0x18005ce3b  sub     rsp, 30h
0x18005ce3f  mov     rsi, rdx
0x18005ce42  mov     rdi, rcx
0x18005ce45  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x18005ce4c  mov     r8d, 394h; int
0x18005ce52  lea     rcx, [rsp+38h+arg_10]; this
0x18005ce57  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005ce5c  mov     rdx, rsi; struct _tagpropertykey *
0x18005ce5f  mov     [rsp+38h+arg_10], 0
0x18005ce68  mov     rcx, rdi; this
0x18005ce6b  call    ?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)
0x18005ce70  mov     ebx, eax
0x18005ce72  test    eax, eax
0x18005ce74  jns     loc_18005CF20
0x18005ce7a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ce81  test    rcx, rcx
0x18005ce84  jnz     short loc_18005CEC7
0x18005ce86  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005ce8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ce93  mov     rcx, rax
0x18005ce96  test    rax, rax
0x18005ce99  jz      short loc_18005CEB9
0x18005ce9b  mov     rax, [rax]
0x18005ce9e  mov     edx, 7F0h
0x18005cea3  mov     rax, [rax+8]
0x18005cea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceac  test    eax, eax
0x18005ceae  jz      short loc_18005CEB9
0x18005ceb0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005ceb7  jmp     short loc_18005CEC7
0x18005ceb9  lea     rcx, qword_1800D6F70; this
0x18005cec0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005cec7  cmp     byte ptr [rcx+8], 0
0x18005cecb  jz      short loc_18005CEF2
0x18005cecd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005ced2  cmp     [rax+7CCh], ebx
0x18005ced8  jz      short loc_18005CEF2
0x18005ceda  mov     r9d, ebx; int
0x18005cedd  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x18005cee4  mov     r8d, 399h; int
0x18005ceea  mov     rcx, rax; this
0x18005ceed  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005cef2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005cef9  jb      short loc_18005CF4E
0x18005cefb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf02  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005cf09  mov     edx, 53h ; 'S'
0x18005cf0e  mov     [rsp+38h+var_18], ebx
0x18005cf12  mov     r9, rdi
0x18005cf15  mov     rcx, [rcx+10h]
0x18005cf19  call    WPP_SF_qD
0x18005cf1e  jmp     short loc_18005CF4E
0x18005cf20  lea     rcx, [rdi+518h]
0x18005cf27  mov     rdx, rsi
0x18005cf2a  lea     r8, [rsp+38h+arg_10]
0x18005cf2f  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x18005cf34  test    eax, eax
0x18005cf36  jz      short loc_18005CF4E
0x18005cf38  mov     rcx, [rsp+38h+arg_10]
0x18005cf3d  test    rcx, rcx
0x18005cf40  jz      short loc_18005CF4E
0x18005cf42  mov     rax, [rcx]
0x18005cf45  mov     rax, [rax+10h]
0x18005cf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf4e  lea     rcx, [rsp+38h+arg_10]; this
0x18005cf53  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005cf58  mov     rsi, [rsp+38h+arg_8]
0x18005cf5d  mov     eax, ebx
0x18005cf5f  mov     rbx, [rsp+38h+arg_0]
0x18005cf64  add     rsp, 30h
0x18005cf68  pop     rdi
0x18005cf69  retn
```
