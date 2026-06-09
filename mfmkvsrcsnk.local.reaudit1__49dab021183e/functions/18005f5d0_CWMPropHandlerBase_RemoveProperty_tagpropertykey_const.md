# CWMPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x18005f5d0`
- end: `0x18005f711`
- name: `?RemoveProperty@CWMPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180058188`
- `0x180058440`
- `0x18005f5d0`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f626`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005f626`

## string_xrefs

- `0x18005f5e5`: `CWMPropHandlerBase::RemoveProperty`
- `0x18005f683`: `CWMPropHandlerBase::RemoveProperty`

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
        v8 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18005f5d0  mov     [rsp+arg_0], rbx
0x18005f5d5  mov     [rsp+arg_8], rsi
0x18005f5da  push    rdi
0x18005f5db  sub     rsp, 30h
0x18005f5df  mov     rsi, rdx
0x18005f5e2  mov     rdi, rcx
0x18005f5e5  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x18005f5ec  mov     r8d, 394h; int
0x18005f5f2  lea     rcx, [rsp+38h+arg_10]; this
0x18005f5f7  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18005f5fc  mov     rdx, rsi; struct _tagpropertykey *
0x18005f5ff  mov     [rsp+38h+arg_10], 0
0x18005f608  mov     rcx, rdi; this
0x18005f60b  call    ?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)
0x18005f610  mov     ebx, eax
0x18005f612  test    eax, eax
0x18005f614  jns     loc_18005F6C6
0x18005f61a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f621  test    rcx, rcx
0x18005f624  jnz     short loc_18005F66D
0x18005f626  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005f62d  nop     dword ptr [rax+rax+00h]
0x18005f632  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f639  mov     rcx, rax
0x18005f63c  test    rax, rax
0x18005f63f  jz      short loc_18005F65F
0x18005f641  mov     rax, [rax]
0x18005f644  mov     edx, 7F0h
0x18005f649  mov     rax, [rax+8]
0x18005f64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f652  test    eax, eax
0x18005f654  jz      short loc_18005F65F
0x18005f656  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f65d  jmp     short loc_18005F66D
0x18005f65f  lea     rcx, qword_1800DBF70; this
0x18005f666  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f66d  cmp     byte ptr [rcx+8], 0
0x18005f671  jz      short loc_18005F698
0x18005f673  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005f678  cmp     [rax+7CCh], ebx
0x18005f67e  jz      short loc_18005F698
0x18005f680  mov     r9d, ebx; int
0x18005f683  lea     rdx, aCwmprophandler_17; "CWMPropHandlerBase::RemoveProperty"
0x18005f68a  mov     r8d, 399h; int
0x18005f690  mov     rcx, rax; this
0x18005f693  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005f698  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005f69f  jb      short loc_18005F6F4
0x18005f6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6a8  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x18005f6af  mov     edx, 53h ; 'S'
0x18005f6b4  mov     [rsp+38h+var_18], ebx
0x18005f6b8  mov     r9, rdi
0x18005f6bb  mov     rcx, [rcx+10h]
0x18005f6bf  call    WPP_SF_qD
0x18005f6c4  jmp     short loc_18005F6F4
0x18005f6c6  lea     rcx, [rdi+518h]
0x18005f6cd  mov     rdx, rsi
0x18005f6d0  lea     r8, [rsp+38h+arg_10]
0x18005f6d5  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x18005f6da  test    eax, eax
0x18005f6dc  jz      short loc_18005F6F4
0x18005f6de  mov     rcx, [rsp+38h+arg_10]
0x18005f6e3  test    rcx, rcx
0x18005f6e6  jz      short loc_18005F6F4
0x18005f6e8  mov     rax, [rcx]
0x18005f6eb  mov     rax, [rax+10h]
0x18005f6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f6f4  lea     rcx, [rsp+38h+arg_10]; this
0x18005f6f9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18005f6fe  mov     rsi, [rsp+38h+arg_8]
0x18005f703  mov     eax, ebx
0x18005f705  mov     rbx, [rsp+38h+arg_0]
0x18005f70a  add     rsp, 30h
0x18005f70e  pop     rdi
0x18005f70f  retn
```
