# CMFPropHandlerBase::UpdateExistingValue(_tagpropertykey const &,tagPROPVARIANT const &,CMFProperty *)

- ea: `0x18003efe0`
- end: `0x18003f1a6`
- name: `?UpdateExistingValue@CMFPropHandlerBase@@IEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@PEAVCMFProperty@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *, struct CMFProperty *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18003db20`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003efe0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f03a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f0f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f03a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003f0f2`

## string_xrefs

- `0x18003eff2`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x18003f091`: `CMFPropHandlerBase::UpdateExistingValue`
- `0x18003f149`: `CMFPropHandlerBase::UpdateExistingValue`

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
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v18; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v18, "CMFPropHandlerBase::UpdateExistingValue", 624);
  v8 = (*(__int64 (__fastcall **)(struct CMFProperty *, const struct tagPROPVARIANT *))(*(_QWORD *)a4 + 288LL))(a4, a3);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct CMFProperty *, __int64 *, __int64))(*(_QWORD *)a4 + 168LL))(
           a4,
           MF_MD_MODIFIED,
           1);
    if ( v8 < 0 )
    {
      v14 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
        CallStackTracing::s_wpInstance = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v14 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::UpdateExistingValue", 629, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 53;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v9 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v9 = &qword_18006EB20;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
      if ( *((_DWORD *)v11 + 499) != v8 )
        CallStackContext::TraceFailure(v11, "CMFPropHandlerBase::UpdateExistingValue", 628, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 52;
LABEL_23:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids, this, v8);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003efe0  mov     [rsp+arg_0], rbx
0x18003efe5  mov     [rsp+arg_10], rsi
0x18003efea  push    rdi
0x18003efeb  sub     rsp, 30h
0x18003efef  mov     rbx, r8
0x18003eff2  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x18003eff9  mov     rsi, rcx
0x18003effc  mov     r8d, 270h; int
0x18003f002  lea     rcx, [rsp+38h+arg_8]; this
0x18003f007  mov     rdi, r9
0x18003f00a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003f00f  mov     rax, [rdi]
0x18003f012  mov     rdx, rbx
0x18003f015  mov     rcx, rdi
0x18003f018  mov     rax, [rax+120h]
0x18003f01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f024  mov     ebx, eax
0x18003f026  test    eax, eax
0x18003f028  jns     loc_18003F0BD
0x18003f02e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f035  test    rcx, rcx
0x18003f038  jnz     short loc_18003F07B
0x18003f03a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003f040  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f047  mov     rcx, rax
0x18003f04a  test    rax, rax
0x18003f04d  jz      short loc_18003F06D
0x18003f04f  mov     rax, [rax]
0x18003f052  mov     edx, 7F0h
0x18003f057  mov     rax, [rax+8]
0x18003f05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f060  test    eax, eax
0x18003f062  jz      short loc_18003F06D
0x18003f064  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f06b  jmp     short loc_18003F07B
0x18003f06d  lea     rcx, qword_18006EB20; this
0x18003f074  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f07b  cmp     byte ptr [rcx+8], 0
0x18003f07f  jz      short loc_18003F0A6
0x18003f081  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f086  cmp     [rax+7CCh], ebx
0x18003f08c  jz      short loc_18003F0A6
0x18003f08e  mov     r9d, ebx; int
0x18003f091  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x18003f098  mov     r8d, 274h; int
0x18003f09e  mov     rcx, rax; this
0x18003f0a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f0a6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f0ab  cmp     al, 1
0x18003f0ad  jb      loc_18003F18A
0x18003f0b3  mov     edx, 34h ; '4'
0x18003f0b8  jmp     loc_18003F16C
0x18003f0bd  mov     rax, [rdi]
0x18003f0c0  lea     rdx, MF_MD_MODIFIED
0x18003f0c7  mov     r8d, 1
0x18003f0cd  mov     rcx, rdi
0x18003f0d0  mov     rax, [rax+0A8h]
0x18003f0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f0dc  mov     ebx, eax
0x18003f0de  test    eax, eax
0x18003f0e0  jns     loc_18003F18A
0x18003f0e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f0ed  test    rcx, rcx
0x18003f0f0  jnz     short loc_18003F133
0x18003f0f2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003f0f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f0ff  mov     rcx, rax
0x18003f102  test    rax, rax
0x18003f105  jz      short loc_18003F125
0x18003f107  mov     rax, [rax]
0x18003f10a  mov     edx, 7F0h
0x18003f10f  mov     rax, [rax+8]
0x18003f113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f118  test    eax, eax
0x18003f11a  jz      short loc_18003F125
0x18003f11c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f123  jmp     short loc_18003F133
0x18003f125  lea     rcx, qword_18006EB20; this
0x18003f12c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003f133  cmp     byte ptr [rcx+8], 0
0x18003f137  jz      short loc_18003F15E
0x18003f139  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003f13e  cmp     [rax+7CCh], ebx
0x18003f144  jz      short loc_18003F15E
0x18003f146  mov     r9d, ebx; int
0x18003f149  lea     rdx, aCmfprophandler_0; "CMFPropHandlerBase::UpdateExistingValue"
0x18003f150  mov     r8d, 275h; int
0x18003f156  mov     rcx, rax; this
0x18003f159  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003f15e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f163  cmp     al, 1
0x18003f165  jb      short loc_18003F18A
0x18003f167  mov     edx, 35h ; '5'
0x18003f16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f173  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003f17a  mov     r9, rsi
0x18003f17d  mov     [rsp+38h+var_18], ebx
0x18003f181  mov     rcx, [rcx+10h]
0x18003f185  call    WPP_SF_qd
0x18003f18a  lea     rcx, [rsp+38h+arg_8]; this
0x18003f18f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003f194  mov     rsi, [rsp+38h+arg_10]
0x18003f199  mov     eax, ebx
0x18003f19b  mov     rbx, [rsp+38h+arg_0]
0x18003f1a0  add     rsp, 30h
0x18003f1a4  pop     rdi
0x18003f1a5  retn
```
