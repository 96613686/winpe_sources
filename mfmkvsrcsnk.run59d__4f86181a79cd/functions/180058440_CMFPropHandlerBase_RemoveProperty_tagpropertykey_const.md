# CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x180058440`
- end: `0x18005856e`
- name: `?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18005f5d0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180058188`
- `0x180058270`
- `0x180058440`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800584b8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800584b8`

## string_xrefs

- `0x180058450`: `CMFPropHandlerBase::RemoveProperty`
- `0x180058515`: `CMFPropHandlerBase::RemoveProperty`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::RemoveProperty(CMFPropHandlerBase *this, const struct _tagpropertykey *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "CMFPropHandlerBase::RemoveProperty", 605);
  v12 = 0;
  CTBucketHash<_tagpropertykey,CMFProperty *>::Remove((char *)this + 48, a2, &v12);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v5 = CMFPropHandlerBase::RemoveKey(this, a2);
  if ( v5 < 0 )
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
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::RemoveProperty", 613, v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v5);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058440  mov     [rsp+arg_8], rbx
0x180058445  push    rdi
0x180058446  sub     rsp, 30h
0x18005844a  mov     rbx, rdx
0x18005844d  mov     rdi, rcx
0x180058450  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x180058457  mov     r8d, 25Dh; int
0x18005845d  lea     rcx, [rsp+38h+arg_0]; this
0x180058462  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180058467  lea     rcx, [rdi+30h]
0x18005846b  mov     [rsp+38h+arg_0], 0
0x180058474  lea     r8, [rsp+38h+arg_0]
0x180058479  mov     rdx, rbx
0x18005847c  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x180058481  mov     rcx, [rsp+38h+arg_0]
0x180058486  test    rcx, rcx
0x180058489  jz      short loc_180058497
0x18005848b  mov     rax, [rcx]
0x18005848e  mov     rax, [rax+10h]
0x180058492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058497  mov     rdx, rbx; struct _tagpropertykey *
0x18005849a  mov     rcx, rdi; this
0x18005849d  call    ?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)
0x1800584a2  mov     ebx, eax
0x1800584a4  test    eax, eax
0x1800584a6  jns     loc_180058556
0x1800584ac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584b3  test    rcx, rcx
0x1800584b6  jnz     short loc_1800584FF
0x1800584b8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800584bf  nop     dword ptr [rax+rax+00h]
0x1800584c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584cb  mov     rcx, rax
0x1800584ce  test    rax, rax
0x1800584d1  jz      short loc_1800584F1
0x1800584d3  mov     rax, [rax]
0x1800584d6  mov     edx, 7F0h
0x1800584db  mov     rax, [rax+8]
0x1800584df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800584e4  test    eax, eax
0x1800584e6  jz      short loc_1800584F1
0x1800584e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584ef  jmp     short loc_1800584FF
0x1800584f1  lea     rcx, qword_1800DBF70; this
0x1800584f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800584ff  cmp     byte ptr [rcx+8], 0
0x180058503  jz      short loc_18005852A
0x180058505  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005850a  cmp     [rax+7CCh], ebx
0x180058510  jz      short loc_18005852A
0x180058512  mov     r9d, ebx; int
0x180058515  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x18005851c  mov     r8d, 265h; int
0x180058522  mov     rcx, rax; this
0x180058525  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005852a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058531  jb      short loc_180058556
0x180058533  mov     rcx, cs:WPP_GLOBAL_Control
0x18005853a  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180058541  mov     edx, 33h ; '3'
0x180058546  mov     [rsp+38h+var_18], ebx
0x18005854a  mov     r9, rdi
0x18005854d  mov     rcx, [rcx+10h]
0x180058551  call    WPP_SF_qD
0x180058556  lea     rcx, [rsp+38h+arg_0]; this
0x18005855b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180058560  mov     eax, ebx
0x180058562  mov     rbx, [rsp+38h+arg_8]
0x180058567  add     rsp, 30h
0x18005856b  pop     rdi
0x18005856c  retn
```
