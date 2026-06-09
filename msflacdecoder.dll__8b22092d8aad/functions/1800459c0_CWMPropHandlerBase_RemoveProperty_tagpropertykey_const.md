# CWMPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x1800459c0`
- end: `0x180045afa`
- name: `?RemoveProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18002e1e0`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003e688`
- `0x18003e940`
- `0x1800459c0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045a16`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180045a16`

## string_xrefs

- `0x1800459d5`: `CWMPropHandlerBase::RemoveProperty`
- `0x180045a6d`: `CWMPropHandlerBase::RemoveProperty`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::RemoveProperty(CWMPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v10, "CWMPropHandlerBase::RemoveProperty", 916);
  v10 = 0;
  v5 = CMFPropHandlerBase::RemoveProperty(this, a2);
  if ( v5 >= 0 )
  {
    if ( (unsigned int)CTBucketHash<_tagpropertykey,CMFProperty *>::Remove((char *)this + 1304, a2, &v10) && v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::RemoveProperty", 921, v5);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v5);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800459c0  mov     [rsp+arg_0], rbx
0x1800459c5  mov     [rsp+arg_8], rsi
0x1800459ca  push    rdi
0x1800459cb  sub     rsp, 30h
0x1800459cf  mov     rsi, rdx
0x1800459d2  mov     rdi, rcx
0x1800459d5  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x1800459dc  mov     r8d, 394h; int
0x1800459e2  lea     rcx, [rsp+38h+arg_10]; this
0x1800459e7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800459ec  mov     rdx, rsi; struct _tagpropertykey *
0x1800459ef  mov     [rsp+38h+arg_10], 0
0x1800459f8  mov     rcx, rdi; this
0x1800459fb  call    ?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)
0x180045a00  mov     ebx, eax
0x180045a02  test    eax, eax
0x180045a04  jns     loc_180045AB0
0x180045a0a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a11  test    rcx, rcx
0x180045a14  jnz     short loc_180045A57
0x180045a16  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045a1c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a23  mov     rcx, rax
0x180045a26  test    rax, rax
0x180045a29  jz      short loc_180045A49
0x180045a2b  mov     rax, [rax]
0x180045a2e  mov     edx, 7F0h
0x180045a33  mov     rax, [rax+8]
0x180045a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a3c  test    eax, eax
0x180045a3e  jz      short loc_180045A49
0x180045a40  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a47  jmp     short loc_180045A57
0x180045a49  lea     rcx, qword_18006EB20; this
0x180045a50  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180045a57  cmp     byte ptr [rcx+8], 0
0x180045a5b  jz      short loc_180045A82
0x180045a5d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045a62  cmp     [rax+7CCh], ebx
0x180045a68  jz      short loc_180045A82
0x180045a6a  mov     r9d, ebx; int
0x180045a6d  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x180045a74  mov     r8d, 399h; int
0x180045a7a  mov     rcx, rax; this
0x180045a7d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045a82  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180045a87  cmp     al, 1
0x180045a89  jb      short loc_180045ADE
0x180045a8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a92  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180045a99  mov     edx, 53h ; 'S'
0x180045a9e  mov     [rsp+38h+var_18], ebx
0x180045aa2  mov     r9, rdi
0x180045aa5  mov     rcx, [rcx+10h]
0x180045aa9  call    WPP_SF_qd
0x180045aae  jmp     short loc_180045ADE
0x180045ab0  lea     rcx, [rdi+518h]
0x180045ab7  mov     rdx, rsi
0x180045aba  lea     r8, [rsp+38h+arg_10]
0x180045abf  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x180045ac4  test    eax, eax
0x180045ac6  jz      short loc_180045ADE
0x180045ac8  mov     rcx, [rsp+38h+arg_10]
0x180045acd  test    rcx, rcx
0x180045ad0  jz      short loc_180045ADE
0x180045ad2  mov     rax, [rcx]
0x180045ad5  mov     rax, [rax+10h]
0x180045ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ade  lea     rcx, [rsp+38h+arg_10]; this
0x180045ae3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045ae8  mov     rsi, [rsp+38h+arg_8]
0x180045aed  mov     eax, ebx
0x180045aef  mov     rbx, [rsp+38h+arg_0]
0x180045af4  add     rsp, 30h
0x180045af8  pop     rdi
0x180045af9  retn
```
