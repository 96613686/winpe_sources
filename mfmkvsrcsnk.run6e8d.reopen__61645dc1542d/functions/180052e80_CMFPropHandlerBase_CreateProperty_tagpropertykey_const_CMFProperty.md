# CMFPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x180052e80`
- end: `0x180052f98`
- name: `?CreateProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `280`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180001f90`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180051d54`
- `0x180052e80`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052eeb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180052eeb`

## string_xrefs

- `0x180052e92`: `CMFPropHandlerBase::CreateProperty`
- `0x180052f42`: `CMFPropHandlerBase::CreateProperty`

## pseudocode

```c
__int64 __fastcall CMFPropHandlerBase::CreateProperty(
        CMFPropHandlerBase *this,
        const struct _tagpropertykey *a2,
        struct CMFProperty **a3)
{
  CMFProperty *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  struct CMFProperty *v11; // rax
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v16; // [rsp+70h] [rbp+18h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v16, "CMFPropHandlerBase::CreateProperty", 637);
  v6 = (CMFProperty *)operator new(0x78u);
  if ( v6 )
  {
    v10 = 0;
    v11 = CMFProperty::CMFProperty(v6, a2);
    *a3 = v11;
    if ( v11 )
      goto LABEL_15;
  }
  else
  {
    *a3 = 0;
  }
  v12 = (__int64 *)CallStackTracing::s_wpInstance;
  v10 = -2147024882;
  if ( !CallStackTracing::s_wpInstance )
  {
    v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v7, v8, v9);
    CallStackTracing::s_wpInstance = v13;
    if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v12 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
    if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147024882 )
      CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropHandlerBase::CreateProperty", 642, -2147024882);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
      this,
      -2147024882);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return v10;
}

```

## disassembly

```asm
0x180052e80  push    rbx
0x180052e82  push    rbp
0x180052e83  push    rsi
0x180052e84  push    rdi
0x180052e85  sub     rsp, 38h
0x180052e89  mov     rdi, r8
0x180052e8c  mov     rsi, rdx
0x180052e8f  mov     rbp, rcx
0x180052e92  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x180052e99  mov     r8d, 27Dh; int
0x180052e9f  lea     rcx, [rsp+58h+arg_10]; this
0x180052ea4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180052ea9  mov     ecx, 78h ; 'x'; Size
0x180052eae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052eb3  test    rax, rax
0x180052eb6  jz      short loc_180052ED3
0x180052eb8  mov     rdx, rsi; struct _tagpropertykey *
0x180052ebb  mov     rcx, rax; this
0x180052ebe  xor     ebx, ebx
0x180052ec0  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x180052ec5  mov     [rdi], rax
0x180052ec8  test    rax, rax
0x180052ecb  jnz     loc_180052F83
0x180052ed1  jmp     short loc_180052EDA
0x180052ed3  mov     qword ptr [rdi], 0
0x180052eda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ee1  mov     ebx, 8007000Eh
0x180052ee6  test    rcx, rcx
0x180052ee9  jnz     short loc_180052F2C
0x180052eeb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180052ef1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180052ef8  mov     rcx, rax
0x180052efb  test    rax, rax
0x180052efe  jz      short loc_180052F1E
0x180052f00  mov     rax, [rax]
0x180052f03  mov     edx, 7F0h
0x180052f08  mov     rax, [rax+8]
0x180052f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f11  test    eax, eax
0x180052f13  jz      short loc_180052F1E
0x180052f15  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f1c  jmp     short loc_180052F2C
0x180052f1e  lea     rcx, qword_1800D6F70; this
0x180052f25  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180052f2c  cmp     byte ptr [rcx+8], 0
0x180052f30  jz      short loc_180052F57
0x180052f32  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180052f37  cmp     [rax+7CCh], ebx
0x180052f3d  jz      short loc_180052F57
0x180052f3f  mov     r9d, ebx; int
0x180052f42  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x180052f49  mov     r8d, 282h; int
0x180052f4f  mov     rcx, rax; this
0x180052f52  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180052f57  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180052f5e  jb      short loc_180052F83
0x180052f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180052f67  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x180052f6e  mov     edx, 36h ; '6'
0x180052f73  mov     [rsp+58h+var_38], ebx
0x180052f77  mov     r9, rbp
0x180052f7a  mov     rcx, [rcx+10h]
0x180052f7e  call    WPP_SF_qD
0x180052f83  lea     rcx, [rsp+58h+arg_10]; this
0x180052f88  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180052f8d  mov     eax, ebx
0x180052f8f  add     rsp, 38h
0x180052f93  pop     rdi
0x180052f94  pop     rsi
0x180052f95  pop     rbp
0x180052f96  pop     rbx
0x180052f97  retn
```
