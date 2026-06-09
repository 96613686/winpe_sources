# CMFPropHandlerBase::UpdateExistingValue(_tagpropertykey const &,tagPROPVARIANT const &,CMFProperty *)

- ea: `0x1800565b0`
- end: `0x180056776`
- name: `?UpdateExistingValue@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAVCMFProperty@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, struct CMFProperty *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180055220`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x1800565b0`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005660a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800566c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005660a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800566c2`

## string_xrefs

- `0x1800565c2`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x180056661`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x180056719`: `CMFPropHandlerBase::UpdateExistingValue`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::UpdateExistingValue(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3,
        struct CMFProperty *a4)
{
  __int64 v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CMFPropHandlerBase::UpdateExistingValue", 624);
  v8 = (*(__int64 (__fastcall **)(struct CMFProperty *, const struct tagPROPVARIANT *))(*(_QWORD *)a4 + 288LL))(a4, a3);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct CMFProperty *, __int64 *, __int64))(*(_QWORD *)a4 + 168LL))(
           a4,
           MF_MD_MODIFIED,
           1);
    if ( v8 < 0 )
    {
      v18 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15, v16, v17);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v18 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v18 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v18 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::UpdateExistingValue", 629, v8);
      }
      if ( g_wppLevels )
      {
        v14 = 53;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v13 + 499) != v8 )
        CallStackContext::TraceFailure(v13, "CMFPropHandlerBase::UpdateExistingValue", 628, v8);
    }
    if ( g_wppLevels )
    {
      v14 = 52;
LABEL_23:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800565b0  mov     [rsp+arg_0], rbx
0x1800565b5  mov     [rsp+arg_10], rsi
0x1800565ba  push    rdi
0x1800565bb  sub     rsp, 30h
0x1800565bf  mov     rbx, r8
0x1800565c2  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x1800565c9  mov     rsi, rcx
0x1800565cc  mov     r8d, 270h; int
0x1800565d2  lea     rcx, [rsp+38h+arg_8]; this
0x1800565d7  mov     rdi, r9
0x1800565da  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800565df  mov     rax, [rdi]
0x1800565e2  mov     rdx, rbx
0x1800565e5  mov     rcx, rdi
0x1800565e8  mov     rax, [rax+120h]
0x1800565ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565f4  mov     ebx, eax
0x1800565f6  test    eax, eax
0x1800565f8  jns     loc_18005668D
0x1800565fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180056605  test    rcx, rcx
0x180056608  jnz     short loc_18005664B
0x18005660a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180056610  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180056617  mov     rcx, rax
0x18005661a  test    rax, rax
0x18005661d  jz      short loc_18005663D
0x18005661f  mov     rax, [rax]
0x180056622  mov     edx, 7F0h
0x180056627  mov     rax, [rax+8]
0x18005662b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056630  test    eax, eax
0x180056632  jz      short loc_18005663D
0x180056634  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005663b  jmp     short loc_18005664B
0x18005663d  lea     rcx, qword_1800D6F70; this
0x180056644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005664b  cmp     byte ptr [rcx+8], 0
0x18005664f  jz      short loc_180056676
0x180056651  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180056656  cmp     [rax+7CCh], ebx
0x18005665c  jz      short loc_180056676
0x18005665e  mov     r9d, ebx; int
0x180056661  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x180056668  mov     r8d, 274h; int
0x18005666e  mov     rcx, rax; this
0x180056671  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180056676  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005667d  jb      loc_18005675A
0x180056683  mov     edx, 34h ; '4'
0x180056688  jmp     loc_18005673C
0x18005668d  mov     rax, [rdi]
0x180056690  lea     rdx, MF_MD_MODIFIED
0x180056697  mov     r8d, 1
0x18005669d  mov     rcx, rdi
0x1800566a0  mov     rax, [rax+0A8h]
0x1800566a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566ac  mov     ebx, eax
0x1800566ae  test    eax, eax
0x1800566b0  jns     loc_18005675A
0x1800566b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800566bd  test    rcx, rcx
0x1800566c0  jnz     short loc_180056703
0x1800566c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800566c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800566cf  mov     rcx, rax
0x1800566d2  test    rax, rax
0x1800566d5  jz      short loc_1800566F5
0x1800566d7  mov     rax, [rax]
0x1800566da  mov     edx, 7F0h
0x1800566df  mov     rax, [rax+8]
0x1800566e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566e8  test    eax, eax
0x1800566ea  jz      short loc_1800566F5
0x1800566ec  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800566f3  jmp     short loc_180056703
0x1800566f5  lea     rcx, qword_1800D6F70; this
0x1800566fc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180056703  cmp     byte ptr [rcx+8], 0
0x180056707  jz      short loc_18005672E
0x180056709  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18005670e  cmp     [rax+7CCh], ebx
0x180056714  jz      short loc_18005672E
0x180056716  mov     r9d, ebx; int
0x180056719  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x180056720  mov     r8d, 275h; int
0x180056726  mov     rcx, rax; this
0x180056729  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005672e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180056735  jb      short loc_18005675A
0x180056737  mov     edx, 35h ; '5'
0x18005673c  mov     rcx, cs:WPP_GLOBAL_Control
0x180056743  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18005674a  mov     r9, rsi
0x18005674d  mov     [rsp+38h+var_18], ebx
0x180056751  mov     rcx, [rcx+10h]
0x180056755  call    WPP_SF_qD
0x18005675a  lea     rcx, [rsp+38h+arg_8]; this
0x18005675f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180056764  mov     rsi, [rsp+38h+arg_10]
0x180056769  mov     eax, ebx
0x18005676b  mov     rbx, [rsp+38h+arg_0]
0x180056770  add     rsp, 30h
0x180056774  pop     rdi
0x180056775  retn
```
