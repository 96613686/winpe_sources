# CMFPropHandlerBase::CreateProperty(_tagpropertykey const &,CMFProperty * *)

- ea: `0x180055200`
- end: `0x18005531f`
- name: `?CreateProperty@CMFPropHandlerBase@@MEAAJAEBU_tagpropertykey@@PEAPEAVCMFProperty@@@Z`
- size: `287`
- prototype: `int(CMFPropHandlerBase *__hidden this, const struct _tagpropertykey *, struct CMFProperty **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180001fb0`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800540bc`
- `0x180055200`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005526b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18005526b`

## string_xrefs

- `0x180055212`: `CMFPropHandlerBase::CreateProperty`
- `0x1800552c8`: `CMFPropHandlerBase::CreateProperty`

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
      v12 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      &WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids,
      this,
      -2147024882);
LABEL_15:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return v10;
}

```

## disassembly

```asm
0x180055200  push    rbx
0x180055202  push    rbp
0x180055203  push    rsi
0x180055204  push    rdi
0x180055205  sub     rsp, 38h
0x180055209  mov     rdi, r8
0x18005520c  mov     rsi, rdx
0x18005520f  mov     rbp, rcx
0x180055212  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x180055219  mov     r8d, 27Dh; int
0x18005521f  lea     rcx, [rsp+58h+arg_10]; this
0x180055224  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180055229  mov     ecx, 78h ; 'x'; Size
0x18005522e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055233  test    rax, rax
0x180055236  jz      short loc_180055253
0x180055238  mov     rdx, rsi; struct _tagpropertykey *
0x18005523b  mov     rcx, rax; this
0x18005523e  xor     ebx, ebx
0x180055240  call    ??0CMFProperty@@QEAA@AEBU_tagpropertykey@@@Z; CMFProperty::CMFProperty(_tagpropertykey const &)
0x180055245  mov     [rdi], rax
0x180055248  test    rax, rax
0x18005524b  jnz     loc_180055309
0x180055251  jmp     short loc_18005525A
0x180055253  mov     qword ptr [rdi], 0
0x18005525a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180055261  mov     ebx, 8007000Eh
0x180055266  test    rcx, rcx
0x180055269  jnz     short loc_1800552B2
0x18005526b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180055272  nop     dword ptr [rax+rax+00h]
0x180055277  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18005527e  mov     rcx, rax
0x180055281  test    rax, rax
0x180055284  jz      short loc_1800552A4
0x180055286  mov     rax, [rax]
0x180055289  mov     edx, 7F0h
0x18005528e  mov     rax, [rax+8]
0x180055292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055297  test    eax, eax
0x180055299  jz      short loc_1800552A4
0x18005529b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800552a2  jmp     short loc_1800552B2
0x1800552a4  lea     rcx, qword_1800DBF70; this
0x1800552ab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800552b2  cmp     byte ptr [rcx+8], 0
0x1800552b6  jz      short loc_1800552DD
0x1800552b8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800552bd  cmp     [rax+7CCh], ebx
0x1800552c3  jz      short loc_1800552DD
0x1800552c5  mov     r9d, ebx; int
0x1800552c8  lea     rdx, aCmfprophandler_13; "CMFPropHandlerBase::CreateProperty"
0x1800552cf  mov     r8d, 282h; int
0x1800552d5  mov     rcx, rax; this
0x1800552d8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800552dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800552e4  jb      short loc_180055309
0x1800552e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552ed  lea     r8, WPP_00a9ad44da4f333d3f7a341524dd7a80_Traceguids
0x1800552f4  mov     edx, 36h ; '6'
0x1800552f9  mov     [rsp+58h+var_38], ebx
0x1800552fd  mov     r9, rbp
0x180055300  mov     rcx, [rcx+10h]
0x180055304  call    WPP_SF_qD
0x180055309  lea     rcx, [rsp+58h+arg_10]; this
0x18005530e  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180055313  mov     eax, ebx
0x180055315  add     rsp, 38h
0x180055319  pop     rdi
0x18005531a  pop     rsi
0x18005531b  pop     rbp
0x18005531c  pop     rbx
0x18005531d  retn
```
