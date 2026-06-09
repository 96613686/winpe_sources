# CxCodeVideoProcMFT::GetService(_GUID const &,_GUID const &,void * *)

- ea: `0x180021130`
- end: `0x180021354`
- name: `?GetService@CxCodeVideoProcMFT@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `548`
- prototype: `int(CxCodeVideoProcMFT *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180021130`
- `0x18002135c`
- `0x18003639c`
- `0x180059a54`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002133f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002133f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002118a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002122f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002118a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002122f`

## string_xrefs

- `0x18002115d`: `CxCodeVideoProcMFT::GetService`
- `0x1800211e5`: `CxCodeVideoProcMFT::GetService`
- `0x180021286`: `CxCodeVideoProcMFT::GetService`
- `0x1800212f1`: `CxCodeVideoProcMFT::GetService`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFT::GetService(
        CxCodeVideoProcMFT *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r15
  char *v6; // rdi
  int v9; // eax
  __int64 *v10; // rcx
  int Service; // ebx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CxCodeVideoProcMFTDataHandler *v15; // rcx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  CallStackTracing *v19; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  char v22; // [rsp+70h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 56);
  v6 = (char *)this - 96;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 56));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v22, "CxCodeVideoProcMFT::GetService", 1031);
  if ( a4 )
  {
    v15 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)v6 + 4);
    if ( v15 )
    {
      Service = CxCodeVideoProcMFTDataHandler::GetService(v15, a2, a3, a4);
      if ( Service < 0 )
      {
        v19 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v19 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v19 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v19);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != Service )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcMFT::GetService", 1034, Service);
        }
        if ( g_wppLevels )
        {
          v14 = 89;
          goto LABEL_32;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      Service = -1072875845;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -1072875845 )
          CallStackContext::TraceFailure(v18, "CxCodeVideoProcMFT::GetService", 1033, -1072875845);
      }
      if ( g_wppLevels )
      {
        v14 = 88;
        goto LABEL_32;
      }
    }
  }
  else
  {
    v9 = XvpOriginateError<16>();
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    Service = v9;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( Service < 0 && *((_DWORD *)v13 + 499) != Service )
        CallStackContext::TraceFailure(v13, "CxCodeVideoProcMFT::GetService", 1031, Service);
    }
    if ( g_wppLevels )
    {
      v14 = 87;
LABEL_32:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, v6, Service);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v22);
  LeaveCriticalSection(v4);
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x180021130  push    rbx
0x180021132  push    rbp
0x180021133  push    rsi
0x180021134  push    rdi
0x180021135  push    r14
0x180021137  push    r15
0x180021139  sub     rsp, 38h
0x18002113d  lea     r15, [rcx-38h]
0x180021141  mov     rsi, r9
0x180021144  lea     rdi, [rcx-60h]
0x180021148  mov     rbp, r8
0x18002114b  mov     rcx, r15; lpCriticalSection
0x18002114e  mov     r14, rdx
0x180021151  call    cs:__imp_EnterCriticalSection
0x180021157  mov     r8d, 407h; int
0x18002115d  lea     rdx, aCxcodevideopro_9; "CxCodeVideoProcMFT::GetService"
0x180021164  lea     rcx, [rsp+68h+arg_0]; this
0x180021169  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002116e  test    rsi, rsi
0x180021171  jnz     loc_180021211
0x180021177  call    ??$XvpOriginateError@$0BA@@@YAJQEADJAEAY0BA@$$CBG@Z; XvpOriginateError<16>(char * const,long,ushort const (&)[16])
0x18002117c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021183  mov     ebx, eax
0x180021185  test    rcx, rcx
0x180021188  jnz     short loc_1800211CB
0x18002118a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021190  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180021197  mov     rcx, rax
0x18002119a  test    rax, rax
0x18002119d  jz      short loc_1800211BD
0x18002119f  mov     rdx, [rax]
0x1800211a2  mov     rax, [rdx+8]
0x1800211a6  mov     edx, 7F0h
0x1800211ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b0  test    eax, eax
0x1800211b2  jz      short loc_1800211BD
0x1800211b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800211bb  jmp     short loc_1800211CB
0x1800211bd  lea     rcx, qword_180153440; this
0x1800211c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800211cb  cmp     byte ptr [rcx+8], 0
0x1800211cf  jz      short loc_1800211FA
0x1800211d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800211d6  test    ebx, ebx
0x1800211d8  jns     short loc_1800211FA
0x1800211da  cmp     [rax+7CCh], ebx
0x1800211e0  jz      short loc_1800211FA
0x1800211e2  mov     r9d, ebx; int
0x1800211e5  lea     rdx, aCxcodevideopro_9; "CxCodeVideoProcMFT::GetService"
0x1800211ec  mov     r8d, 407h; int
0x1800211f2  mov     rcx, rax; this
0x1800211f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800211fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180021201  jb      loc_180021332
0x180021207  mov     edx, 57h ; 'W'
0x18002120c  jmp     loc_180021314
0x180021211  mov     rcx, [rdi+20h]; this
0x180021215  test    rcx, rcx
0x180021218  jnz     loc_1800212AF
0x18002121e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021225  mov     ebx, 0C00D36BBh
0x18002122a  test    rcx, rcx
0x18002122d  jnz     short loc_180021270
0x18002122f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180021235  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002123c  mov     rcx, rax
0x18002123f  test    rax, rax
0x180021242  jz      short loc_180021262
0x180021244  mov     rax, [rax]
0x180021247  mov     edx, 7F0h
0x18002124c  mov     rax, [rax+8]
0x180021250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021255  test    eax, eax
0x180021257  jz      short loc_180021262
0x180021259  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180021260  jmp     short loc_180021270
0x180021262  lea     rcx, qword_180153440; this
0x180021269  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180021270  cmp     byte ptr [rcx+8], 0
0x180021274  jz      short loc_18002129B
0x180021276  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002127b  cmp     [rax+7CCh], ebx
0x180021281  jz      short loc_18002129B
0x180021283  mov     r9d, ebx; int
0x180021286  lea     rdx, aCxcodevideopro_9; "CxCodeVideoProcMFT::GetService"
0x18002128d  mov     r8d, 409h; int
0x180021293  mov     rcx, rax; this
0x180021296  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002129b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800212a2  jb      loc_180021332
0x1800212a8  mov     edx, 58h ; 'X'
0x1800212ad  jmp     short loc_180021314
0x1800212af  mov     r9, rsi; void **
0x1800212b2  mov     r8, rbp; struct _GUID *
0x1800212b5  mov     rdx, r14; struct _GUID *
0x1800212b8  call    ?GetService@CxCodeVideoProcMFTDataHandler@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CxCodeVideoProcMFTDataHandler::GetService(_GUID const &,_GUID const &,void * *)
0x1800212bd  mov     ebx, eax
0x1800212bf  test    eax, eax
0x1800212c1  jns     short loc_180021332
0x1800212c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800212ca  test    rcx, rcx
0x1800212cd  jnz     short loc_1800212DB
0x1800212cf  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800212d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800212db  cmp     byte ptr [rcx+8], 0
0x1800212df  jz      short loc_180021306
0x1800212e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800212e6  cmp     [rax+7CCh], ebx
0x1800212ec  jz      short loc_180021306
0x1800212ee  mov     r9d, ebx; int
0x1800212f1  lea     rdx, aCxcodevideopro_9; "CxCodeVideoProcMFT::GetService"
0x1800212f8  mov     r8d, 40Ah; int
0x1800212fe  mov     rcx, rax; this
0x180021301  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180021306  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002130d  jb      short loc_180021332
0x18002130f  mov     edx, 59h ; 'Y'
0x180021314  mov     rcx, cs:WPP_GLOBAL_Control
0x18002131b  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x180021322  mov     r9, rdi
0x180021325  mov     [rsp+68h+var_48], ebx
0x180021329  mov     rcx, [rcx+10h]
0x18002132d  call    WPP_SF_qD
0x180021332  lea     rcx, [rsp+68h+arg_0]; this
0x180021337  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002133c  mov     rcx, r15; lpCriticalSection
0x18002133f  call    cs:__imp_LeaveCriticalSection
0x180021345  mov     eax, ebx
0x180021347  add     rsp, 38h
0x18002134b  pop     r15
0x18002134d  pop     r14
0x18002134f  pop     rdi
0x180021350  pop     rsi
0x180021351  pop     rbp
0x180021352  pop     rbx
0x180021353  retn
```
