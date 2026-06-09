# CWMPropHandlerBase::GetStreamMajorType(IMFStreamDescriptor *,_GUID *)

- ea: `0x1800453c8`
- end: `0x180045598`
- name: `?GetStreamMajorType@CWMPropHandlerBase@@IEAAJPEAUIMFStreamDescriptor@@PEAU_GUID@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CWMPropHandlerBase *__hidden this, struct IMFStreamDescriptor *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180045b00`

## callees

- `0x180020398`
- `0x180020484`
- `0x18002a100`
- `0x18002fce8`
- `0x18002fff0`
- `0x180031bdc`
- `0x180039e60`
- `0x1800453c8`
- `0x180056010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004542d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800454da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004542d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800454da`

## pseudocode

```c
__int64 __fastcall CWMPropHandlerBase::GetStreamMajorType(
        CWMPropHandlerBase *this,
        struct IMFStreamDescriptor *a2,
        struct _GUID *a3)
{
  struct IMFStreamDescriptorVtbl *lpVtbl; // rax
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
  __int64 v19; // [rsp+58h] [rbp+20h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v18, "CWMPropHandlerBase::GetStreamMajorType", 1119);
  lpVtbl = a2->lpVtbl;
  v19 = 0;
  v8 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))lpVtbl->GetMediaTypeHandler)(a2, &v19);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v19 + 64LL))(v19, a3);
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
          CallStackContext::TraceFailure(ThreadRelativeContext, "CWMPropHandlerBase::GetStreamMajorType", 1126, v8);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v12 = 94;
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
        CallStackContext::TraceFailure(v11, "CWMPropHandlerBase::GetStreamMajorType", 1124, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v12 = 93;
LABEL_23:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, WPP_d497573e8d0434bb74893564de0342d6_Traceguids, this, v8);
    }
  }
  ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(&v19);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800453c8  mov     [rsp+arg_0], rbx
0x1800453cd  mov     [rsp+arg_10], rsi
0x1800453d2  push    rdi
0x1800453d3  sub     rsp, 30h
0x1800453d7  mov     rsi, r8
0x1800453da  mov     rbx, rdx
0x1800453dd  mov     rdi, rcx
0x1800453e0  lea     rdx, aCwmprophandler_14; "CWMPropHandlerBase::GetStreamMajorType"
0x1800453e7  mov     r8d, 45Fh; int
0x1800453ed  lea     rcx, [rsp+38h+arg_8]; this
0x1800453f2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800453f7  mov     rax, [rbx]
0x1800453fa  lea     rdx, [rsp+38h+arg_18]
0x1800453ff  mov     rcx, rbx
0x180045402  mov     [rsp+38h+arg_18], 0
0x18004540b  mov     rax, [rax+110h]
0x180045412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045417  mov     ebx, eax
0x180045419  test    eax, eax
0x18004541b  jns     loc_1800454B0
0x180045421  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180045428  test    rcx, rcx
0x18004542b  jnz     short loc_18004546E
0x18004542d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180045433  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004543a  mov     rcx, rax
0x18004543d  test    rax, rax
0x180045440  jz      short loc_180045460
0x180045442  mov     rax, [rax]
0x180045445  mov     edx, 7F0h
0x18004544a  mov     rax, [rax+8]
0x18004544e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045453  test    eax, eax
0x180045455  jz      short loc_180045460
0x180045457  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004545e  jmp     short loc_18004546E
0x180045460  lea     rcx, qword_18006EB20; this
0x180045467  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004546e  cmp     byte ptr [rcx+8], 0
0x180045472  jz      short loc_180045499
0x180045474  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045479  cmp     [rax+7CCh], ebx
0x18004547f  jz      short loc_180045499
0x180045481  mov     r9d, ebx; int
0x180045484  lea     rdx, aCwmprophandler_14; "CWMPropHandlerBase::GetStreamMajorType"
0x18004548b  mov     r8d, 464h; int
0x180045491  mov     rcx, rax; this
0x180045494  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045499  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004549e  cmp     al, 1
0x1800454a0  jb      loc_180045572
0x1800454a6  mov     edx, 5Dh ; ']'
0x1800454ab  jmp     loc_180045554
0x1800454b0  mov     rcx, [rsp+38h+arg_18]
0x1800454b5  mov     rdx, rsi
0x1800454b8  mov     rax, [rcx]
0x1800454bb  mov     rax, [rax+40h]
0x1800454bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454c4  mov     ebx, eax
0x1800454c6  test    eax, eax
0x1800454c8  jns     loc_180045572
0x1800454ce  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454d5  test    rcx, rcx
0x1800454d8  jnz     short loc_18004551B
0x1800454da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800454e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800454e7  mov     rcx, rax
0x1800454ea  test    rax, rax
0x1800454ed  jz      short loc_18004550D
0x1800454ef  mov     rax, [rax]
0x1800454f2  mov     edx, 7F0h
0x1800454f7  mov     rax, [rax+8]
0x1800454fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045500  test    eax, eax
0x180045502  jz      short loc_18004550D
0x180045504  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004550b  jmp     short loc_18004551B
0x18004550d  lea     rcx, qword_18006EB20; this
0x180045514  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004551b  cmp     byte ptr [rcx+8], 0
0x18004551f  jz      short loc_180045546
0x180045521  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180045526  cmp     [rax+7CCh], ebx
0x18004552c  jz      short loc_180045546
0x18004552e  mov     r9d, ebx; int
0x180045531  lea     rdx, aCwmprophandler_14; "CWMPropHandlerBase::GetStreamMajorType"
0x180045538  mov     r8d, 466h; int
0x18004553e  mov     rcx, rax; this
0x180045541  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180045546  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004554b  cmp     al, 1
0x18004554d  jb      short loc_180045572
0x18004554f  mov     edx, 5Eh ; '^'
0x180045554  mov     rcx, cs:WPP_GLOBAL_Control
0x18004555b  lea     r8, WPP_d497573e8d0434bb74893564de0342d6_Traceguids
0x180045562  mov     r9, rdi
0x180045565  mov     [rsp+38h+var_18], ebx
0x180045569  mov     rcx, [rcx+10h]
0x18004556d  call    WPP_SF_qd
0x180045572  lea     rcx, [rsp+38h+arg_18]
0x180045577  call    ??1?$CComPtrBase@UIMFMediaTypeHandler@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFMediaTypeHandler>::~CComPtrBase<IMFMediaTypeHandler>(void)
0x18004557c  lea     rcx, [rsp+38h+arg_8]; this
0x180045581  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180045586  mov     rsi, [rsp+38h+arg_10]
0x18004558b  mov     eax, ebx
0x18004558d  mov     rbx, [rsp+38h+arg_0]
0x180045592  add     rsp, 30h
0x180045596  pop     rdi
0x180045597  retn
```
