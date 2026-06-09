# CMFPropHandlerBase::UpdateExistingValue(_tagpropertykey const &,tagPROPVARIANT const &,CMFProperty *)

- ea: `0x180058a7c`
- end: `0x180058c4f`
- name: `?UpdateExistingValue@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAVCMFProperty@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, struct CMFProperty *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180057680`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x180058a7c`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ad6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058b94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058ad6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180058b94`

## string_xrefs

- `0x180058a8e`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x180058b33`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x180058bf1`: `CMFPropHandlerBase::UpdateExistingValue`

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
          v18 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180058a7c  mov     [rsp+arg_0], rbx
0x180058a81  mov     [rsp+arg_10], rsi
0x180058a86  push    rdi
0x180058a87  sub     rsp, 30h
0x180058a8b  mov     rbx, r8
0x180058a8e  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x180058a95  mov     rsi, rcx
0x180058a98  mov     r8d, 270h; int
0x180058a9e  lea     rcx, [rsp+38h+arg_8]; this
0x180058aa3  mov     rdi, r9
0x180058aa6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180058aab  mov     rax, [rdi]
0x180058aae  mov     rdx, rbx
0x180058ab1  mov     rcx, rdi
0x180058ab4  mov     rax, [rax+120h]
0x180058abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ac0  mov     ebx, eax
0x180058ac2  test    eax, eax
0x180058ac4  jns     loc_180058B5F
0x180058aca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058ad1  test    rcx, rcx
0x180058ad4  jnz     short loc_180058B1D
0x180058ad6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058add  nop     dword ptr [rax+rax+00h]
0x180058ae2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058ae9  mov     rcx, rax
0x180058aec  test    rax, rax
0x180058aef  jz      short loc_180058B0F
0x180058af1  mov     rax, [rax]
0x180058af4  mov     edx, 7F0h
0x180058af9  mov     rax, [rax+8]
0x180058afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b02  test    eax, eax
0x180058b04  jz      short loc_180058B0F
0x180058b06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058b0d  jmp     short loc_180058B1D
0x180058b0f  lea     rcx, qword_1800DBF70; this
0x180058b16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058b1d  cmp     byte ptr [rcx+8], 0
0x180058b21  jz      short loc_180058B48
0x180058b23  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058b28  cmp     [rax+7CCh], ebx
0x180058b2e  jz      short loc_180058B48
0x180058b30  mov     r9d, ebx; int
0x180058b33  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x180058b3a  mov     r8d, 274h; int
0x180058b40  mov     rcx, rax; this
0x180058b43  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058b48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058b4f  jb      loc_180058C32
0x180058b55  mov     edx, 34h ; '4'
0x180058b5a  jmp     loc_180058C14
0x180058b5f  mov     rax, [rdi]
0x180058b62  lea     rdx, MF_MD_MODIFIED
0x180058b69  mov     r8d, 1
0x180058b6f  mov     rcx, rdi
0x180058b72  mov     rax, [rax+0A8h]
0x180058b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b7e  mov     ebx, eax
0x180058b80  test    eax, eax
0x180058b82  jns     loc_180058C32
0x180058b88  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058b8f  test    rcx, rcx
0x180058b92  jnz     short loc_180058BDB
0x180058b94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180058b9b  nop     dword ptr [rax+rax+00h]
0x180058ba0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180058ba7  mov     rcx, rax
0x180058baa  test    rax, rax
0x180058bad  jz      short loc_180058BCD
0x180058baf  mov     rax, [rax]
0x180058bb2  mov     edx, 7F0h
0x180058bb7  mov     rax, [rax+8]
0x180058bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bc0  test    eax, eax
0x180058bc2  jz      short loc_180058BCD
0x180058bc4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180058bcb  jmp     short loc_180058BDB
0x180058bcd  lea     rcx, qword_1800DBF70; this
0x180058bd4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180058bdb  cmp     byte ptr [rcx+8], 0
0x180058bdf  jz      short loc_180058C06
0x180058be1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180058be6  cmp     [rax+7CCh], ebx
0x180058bec  jz      short loc_180058C06
0x180058bee  mov     r9d, ebx; int
0x180058bf1  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x180058bf8  mov     r8d, 275h; int
0x180058bfe  mov     rcx, rax; this
0x180058c01  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180058c06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180058c0d  jb      short loc_180058C32
0x180058c0f  mov     edx, 35h ; '5'
0x180058c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180058c1b  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180058c22  mov     r9, rsi
0x180058c25  mov     [rsp+38h+var_18], ebx
0x180058c29  mov     rcx, [rcx+10h]
0x180058c2d  call    WPP_SF_qD
0x180058c32  lea     rcx, [rsp+38h+arg_8]; this
0x180058c37  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180058c3c  mov     rsi, [rsp+38h+arg_10]
0x180058c41  mov     eax, ebx
0x180058c43  mov     rbx, [rsp+38h+arg_0]
0x180058c48  add     rsp, 30h
0x180058c4c  pop     rdi
0x180058c4d  retn
```
