# CMFPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x18003b8f0`
- end: `0x18003ba08`
- name: `?CreateProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `280`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x1800018a4`
- `0x180020398`
- `0x180020484`
- `0x180029ddc`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x18003b8f0`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b95b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b95b`

## string_xrefs

- `0x18003b902`: `CMFPropHandlerBase::CreateProperty`
- `0x18003b9b2`: `CMFPropHandlerBase::CreateProperty`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::CreateProperty(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct CMFProperty **a3)
{
  CMFProperty *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  struct CMFProperty *v9; // rax
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v14; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v14, "CMFPropHandlerBase::CreateProperty", 637);
  v6 = (CMFProperty *)operator new(0x78u);
  if ( v6 )
  {
    v8 = 0;
    v9 = CMFProperty::CMFProperty(v6, a2);
    *a3 = v9;
    if ( v9 )
      goto LABEL_15;
  }
  else
  {
    *a3 = 0;
  }
  v10 = (__int64 *)CallStackTracing::s_wpInstance;
  v8 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7);
    CallStackTracing::s_wpInstance = v11;
    if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v10 = &qword_18006EB20;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
    }
  }
  if ( *((_BYTE *)v10 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::CreateProperty", 642, -2147024882);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
      this,
      -2147024882);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  return v8;
}

```

## disassembly

```asm
0x18003b8f0  push    rbx
0x18003b8f2  push    rbp
0x18003b8f3  push    rsi
0x18003b8f4  push    rdi
0x18003b8f5  sub     rsp, 38h
0x18003b8f9  mov     rdi, r8
0x18003b8fc  mov     rsi, rdx
0x18003b8ff  mov     rbp, rcx
0x18003b902  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x18003b909  mov     r8d, 27Dh; int
0x18003b90f  lea     rcx, [rsp+58h+arg_10]; this
0x18003b914  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b919  mov     ecx, 78h ; 'x'; Size
0x18003b91e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b923  test    rax, rax
0x18003b926  jz      short loc_18003B943
0x18003b928  mov     rdx, rsi; struct _tagpropertykey *
0x18003b92b  mov     rcx, rax; this
0x18003b92e  xor     ebx, ebx
0x18003b930  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x18003b935  mov     [rdi], rax
0x18003b938  test    rax, rax
0x18003b93b  jnz     loc_18003B9F3
0x18003b941  jmp     short loc_18003B94A
0x18003b943  mov     qword ptr [rdi], 0
0x18003b94a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b951  mov     ebx, 8007000Eh
0x18003b956  test    rcx, rcx
0x18003b959  jnz     short loc_18003B99C
0x18003b95b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b961  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b968  mov     rcx, rax
0x18003b96b  test    rax, rax
0x18003b96e  jz      short loc_18003B98E
0x18003b970  mov     rax, [rax]
0x18003b973  mov     edx, 7F0h
0x18003b978  mov     rax, [rax+8]
0x18003b97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b981  test    eax, eax
0x18003b983  jz      short loc_18003B98E
0x18003b985  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b98c  jmp     short loc_18003B99C
0x18003b98e  lea     rcx, qword_18006EB20; this
0x18003b995  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b99c  cmp     byte ptr [rcx+8], 0
0x18003b9a0  jz      short loc_18003B9C7
0x18003b9a2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b9a7  cmp     [rax+7CCh], ebx
0x18003b9ad  jz      short loc_18003B9C7
0x18003b9af  mov     r9d, ebx; int
0x18003b9b2  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x18003b9b9  mov     r8d, 282h; int
0x18003b9bf  mov     rcx, rax; this
0x18003b9c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b9c7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b9cc  cmp     al, 1
0x18003b9ce  jb      short loc_18003B9F3
0x18003b9d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9d7  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x18003b9de  mov     edx, 36h ; '6'
0x18003b9e3  mov     [rsp+58h+var_38], ebx
0x18003b9e7  mov     r9, rbp
0x18003b9ea  mov     rcx, [rcx+10h]
0x18003b9ee  call    WPP_SF_qd
0x18003b9f3  lea     rcx, [rsp+58h+arg_10]; this
0x18003b9f8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b9fd  mov     eax, ebx
0x18003b9ff  add     rsp, 38h
0x18003ba03  pop     rdi
0x18003ba04  pop     rsi
0x18003ba05  pop     rbp
0x18003ba06  pop     rbx
0x18003ba07  retn
```
