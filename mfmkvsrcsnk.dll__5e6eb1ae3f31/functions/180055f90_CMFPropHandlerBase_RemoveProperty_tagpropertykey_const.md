# CMFPropHandlerBase::RemoveProperty(_tagpropertykey const &)

- ea: `0x180055f90`
- end: `0x1800560b7`
- name: `?RemoveProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18005ce30`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180055ce4`
- `0x180055dcc`
- `0x180055f90`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056008`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180056008`

## string_xrefs

- `0x180055fa0`: `CMFPropHandlerBase::RemoveProperty`
- `0x18005605f`: `CMFPropHandlerBase::RemoveProperty`

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
        v8 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180055f90  mov     [rsp+arg_8], rbx
0x180055f95  push    rdi
0x180055f96  sub     rsp, 30h
0x180055f9a  mov     rbx, rdx
0x180055f9d  mov     rdi, rcx
0x180055fa0  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x180055fa7  mov     r8d, 25Dh; int
0x180055fad  lea     rcx, [rsp+38h+arg_0]; this
0x180055fb2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055fb7  lea     rcx, [rdi+30h]
0x180055fbb  mov     [rsp+38h+arg_0], 0
0x180055fc4  lea     r8, [rsp+38h+arg_0]
0x180055fc9  mov     rdx, rbx
0x180055fcc  call    ?Remove@?$CTBucketHash@U_tagpropertykey@@PEAVCMFProperty@@@@QEAAHAEBU_tagpropertykey@@AEAPEAVCMFProperty@@@Z; CTBucketHash<_tagpropertykey,CMFProperty *>::Remove(_tagpropertykey const &,CMFProperty * &)
0x180055fd1  mov     rcx, [rsp+38h+arg_0]
0x180055fd6  test    rcx, rcx
0x180055fd9  jz      short loc_180055FE7
0x180055fdb  mov     rax, [rcx]
0x180055fde  mov     rax, [rax+10h]
0x180055fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fe7  mov     rdx, rbx; struct _tagpropertykey *
0x180055fea  mov     rcx, rdi; this
0x180055fed  call    ?RemoveKey@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@@Z; CMFPropHandlerBase::RemoveKey(_tagpropertykey const &)
0x180055ff2  mov     ebx, eax
0x180055ff4  test    eax, eax
0x180055ff6  jns     loc_1800560A0
0x180055ffc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056003  test    rcx, rcx
0x180056006  jnz     short loc_180056049
0x180056008  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18005600e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180056015  mov     rcx, rax
0x180056018  test    rax, rax
0x18005601b  jz      short loc_18005603B
0x18005601d  mov     rax, [rax]
0x180056020  mov     edx, 7F0h
0x180056025  mov     rax, [rax+8]
0x180056029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005602e  test    eax, eax
0x180056030  jz      short loc_18005603B
0x180056032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056039  jmp     short loc_180056049
0x18005603b  lea     rcx, qword_1800D6F70; this
0x180056042  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180056049  cmp     byte ptr [rcx+8], 0
0x18005604d  jz      short loc_180056074
0x18005604f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180056054  cmp     [rax+7CCh], ebx
0x18005605a  jz      short loc_180056074
0x18005605c  mov     r9d, ebx; int
0x18005605f  lea     rdx, aCmfprophandler_4; "CMFPropHandlerBase::RemoveProperty"
0x180056066  mov     r8d, 265h; int
0x18005606c  mov     rcx, rax; this
0x18005606f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180056074  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005607b  jb      short loc_1800560A0
0x18005607d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056084  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18005608b  mov     edx, 33h ; '3'
0x180056090  mov     [rsp+38h+var_18], ebx
0x180056094  mov     r9, rdi
0x180056097  mov     rcx, [rcx+10h]
0x18005609b  call    WPP_SF_qD
0x1800560a0  lea     rcx, [rsp+38h+arg_0]; this
0x1800560a5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800560aa  mov     eax, ebx
0x1800560ac  mov     rbx, [rsp+38h+arg_8]
0x1800560b1  add     rsp, 30h
0x1800560b5  pop     rdi
0x1800560b6  retn
```
