# CIISModuleFactory::Terminate(void)

- ea: `0x1800072b0`
- end: `0x1800073ac`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `252`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800052b4`
- `0x1800052dc`
- `0x180005314`
- `0x180005a4c`
- `0x1800063bc`
- `0x1800072b0`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000735c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18000735c`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  UL_RESPONSE_CACHE *v2; // rcx
  unsigned int v3; // edx
  unsigned int v4; // edx
  OUTPUT_CACHE *v5; // rbx
  void *v6; // rdx

  v2 = (UL_RESPONSE_CACHE *)g_pMonitorStoredContext;
  if ( g_pMonitorStoredContext )
  {
    operator delete(g_pMonitorStoredContext);
    g_pMonitorStoredContext = 0;
  }
  RESPONSE_ENTRY::sm_hHeap = 0;
  if ( g_pUlCache )
  {
    UL_RESPONSE_CACHE::Terminate(v2);
    v2 = (UL_RESPONSE_CACHE *)g_pUlCache;
    if ( g_pUlCache )
      OUTPUT_CACHE::`scalar deleting destructor'((OUTPUT_CACHE *)g_pUlCache, v3);
    g_pUlCache = 0;
  }
  if ( g_pVaryByCache )
  {
    VARY_BY_CACHE::Terminate(v2);
    if ( g_pVaryByCache )
      VARY_BY_CACHE::`scalar deleting destructor'((VARY_BY_CACHE *)g_pVaryByCache, v4);
    g_pVaryByCache = 0;
  }
  v5 = (OUTPUT_CACHE *)g_pOutputCache;
  if ( g_pOutputCache )
  {
    v6 = (void *)*((_QWORD *)g_pOutputCache + 9);
    *((_DWORD *)g_pOutputCache + 20) = 0;
    if ( v6 )
    {
      DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)v5 + 9) = 0;
      v5 = (OUTPUT_CACHE *)g_pOutputCache;
    }
    if ( v5 )
      OUTPUT_CACHE::`scalar deleting destructor'(v5, (unsigned int)v6);
    g_pOutputCache = 0;
  }
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x1800072b0  mov     [rsp+arg_0], rbx
0x1800072b5  push    rdi
0x1800072b6  sub     rsp, 20h
0x1800072ba  mov     rdi, rcx
0x1800072bd  mov     rcx, cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA; Block
0x1800072c4  test    rcx, rcx
0x1800072c7  jz      short loc_1800072D9
0x1800072c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800072ce  mov     cs:?g_pMonitorStoredContext@@3PEAVMonitorStoredContext@@EA, 0; MonitorStoredContext * g_pMonitorStoredContext
0x1800072d9  cmp     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, 0; UL_RESPONSE_CACHE * g_pUlCache
0x1800072e1  mov     cs:?sm_hHeap@RESPONSE_ENTRY@@0PEAXEA, 0; void * RESPONSE_ENTRY::sm_hHeap
0x1800072ec  jz      short loc_18000730F
0x1800072ee  call    ?Terminate@UL_RESPONSE_CACHE@@QEAAXXZ; UL_RESPONSE_CACHE::Terminate(void)
0x1800072f3  mov     rcx, cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA; this
0x1800072fa  test    rcx, rcx
0x1800072fd  jz      short loc_180007304
0x1800072ff  call    ??_GOUTPUT_CACHE@@QEAAPEAXI@Z; OUTPUT_CACHE::`scalar deleting destructor'(uint)
0x180007304  mov     cs:?g_pUlCache@@3PEAVUL_RESPONSE_CACHE@@EA, 0; UL_RESPONSE_CACHE * g_pUlCache
0x18000730f  cmp     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, 0; VARY_BY_CACHE * g_pVaryByCache
0x180007317  jz      short loc_18000733A
0x180007319  call    ?Terminate@VARY_BY_CACHE@@QEAAXXZ; VARY_BY_CACHE::Terminate(void)
0x18000731e  mov     rcx, cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA; this
0x180007325  test    rcx, rcx
0x180007328  jz      short loc_18000732F
0x18000732a  call    ??_GVARY_BY_CACHE@@QEAAPEAXI@Z; VARY_BY_CACHE::`scalar deleting destructor'(uint)
0x18000732f  mov     cs:?g_pVaryByCache@@3PEAVVARY_BY_CACHE@@EA, 0; VARY_BY_CACHE * g_pVaryByCache
0x18000733a  mov     rbx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180007341  test    rbx, rbx
0x180007344  jz      short loc_180007389
0x180007346  mov     rdx, [rbx+48h]; Timer
0x18000734a  mov     dword ptr [rbx+50h], 0
0x180007351  test    rdx, rdx
0x180007354  jz      short loc_180007371
0x180007356  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18000735a  xor     ecx, ecx; TimerQueue
0x18000735c  call    cs:__imp_DeleteTimerQueueTimer
0x180007362  mov     qword ptr [rbx+48h], 0
0x18000736a  mov     rbx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180007371  test    rbx, rbx
0x180007374  jz      short loc_18000737E
0x180007376  mov     rcx, rbx; this
0x180007379  call    ??_GOUTPUT_CACHE@@QEAAPEAXI@Z; OUTPUT_CACHE::`scalar deleting destructor'(uint)
0x18000737e  mov     cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA, 0; OUTPUT_CACHE * g_pOutputCache
0x180007389  test    rdi, rdi
0x18000738c  jz      short loc_1800073A1
0x18000738e  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180007395  mov     rcx, rdi; Block
0x180007398  mov     [rdi+8], rax
0x18000739c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073a1  mov     rbx, [rsp+28h+arg_0]
0x1800073a6  add     rsp, 20h
0x1800073aa  pop     rdi
0x1800073ab  retn
```
