# W3_CONTEXT::~W3_CONTEXT(void)

- ea: `0x18000df90`
- end: `0x18000e391`
- name: `??1W3_CONTEXT@@QEAA@XZ`
- size: `1025`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ded4`
- `0x18001f8b0`

## callees

- `0x18000df90`
- `0x18000e3a0`
- `0x18000e4e4`
- `0x18000e690`
- `0x180015900`
- `0x180015960`
- `0x180019598`
- `0x18001f710`
- `0x18002dc30`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e273`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e273`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e370`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000e18e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000e18e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e1e1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e1ee`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e28e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e30d`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e1e1`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e1ee`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e28e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000e30d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e19b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1a8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1fb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e19b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1a8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000e1fb`
- `iisutil!WriteRefTraceLog` at `0x18000e386`
- `iisutil!WriteRefTraceLog` at `0x18000e386`

## pseudocode

```c
void __fastcall W3_CONTEXT::~W3_CONTEXT(W3_CONTEXT *this)
{
  __int64 v2; // rcx
  _WORD *v3; // rax
  unsigned int v4; // r9d
  _QWORD *v5; // rdi
  unsigned __int64 *v6; // rsi
  unsigned __int64 v7; // rdx
  volatile signed __int32 *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  void *v11; // rdi
  void *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  W3_CONTEXT_BASE *v15; // rcx
  W3_CONTEXT_BASE *v16; // rcx
  _QWORD *v17; // rdi
  struct _TRACE_LOG *v18; // rcx
  void *v19; // r8

  *(_QWORD *)this = &W3_CONTEXT::`vftable'{for `IHttpContext4'};
  *((_QWORD *)this + 1) = &W3_CONTEXT::`vftable'{for `IHttpTraceContext'};
  *((_QWORD *)this + 2) = &W3_CONTEXT::`vftable'{for `IMapHandlerProvider'};
  *((_QWORD *)this + 3) = &W3_CONTEXT::`vftable'{for `IModuleAllocator'};
  *((_QWORD *)this + 4) = &W3_CONTEXT::`vftable'{for `IAuthenticationProvider'};
  if ( *((_QWORD *)this + 1009) )
  {
    v2 = *((_QWORD *)this + 47);
    if ( v2 )
    {
      if ( !*((_QWORD *)this + 50) )
      {
        v3 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
        if ( v3 && *v3 )
        {
          SITE_PERF_COUNTERS::DecrementCounter(
            (SITE_PERF_COUNTERS *)(*((_QWORD *)this + 1009) + 656LL),
            4u,
            (unsigned __int64 *)this + 1167,
            v4);
        }
        else
        {
          v5 = *(_QWORD **)(*((_QWORD *)this + 1009) + 664LL);
          if ( v5 )
          {
            v6 = (unsigned __int64 *)((char *)this + 9336);
            if ( this == (W3_CONTEXT *)-9336LL )
            {
              LODWORD(v7) = 0;
            }
            else
            {
              v7 = *v6;
              if ( *v6 == 0xFFFFFFFF )
              {
                v7 = (unsigned __int64)GetCurrentThreadId() % v5[2];
                *v6 = (unsigned int)v7;
              }
            }
            _InterlockedDecrement((volatile signed __int32 *)(*v5
                                                            + (unsigned int)dword_18004AD08
                                                            + v5[1] * (unsigned int)v7));
          }
        }
      }
    }
  }
  CONTEXT_CONTAINER::Cleanup((W3_CONTEXT *)((char *)this + 8928));
  if ( *((_BYTE *)this + 8096) )
    W3_APPLICATION::DereferenceApplication(*((W3_APPLICATION **)this + 1011));
  *((_QWORD *)this + 1011) = 0;
  if ( *((_BYTE *)this + 8103) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1114) + 40LL))(*((_QWORD *)this + 1114));
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 1009);
  *((_QWORD *)this + 1114) = 0;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
    {
      W3_SITE::~W3_SITE((W3_SITE *)v8);
      operator delete((void *)v8);
    }
    *((_QWORD *)this + 1009) = 0;
  }
  v9 = *((_QWORD *)this + 1115);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 8) + 16LL))(v9 + 8);
    *((_QWORD *)this + 1115) = 0;
  }
  v10 = *((_QWORD *)this + 1131);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 1131) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 1132);
  if ( v11 )
  {
    BUFFER::~BUFFER(*((BUFFER **)this + 1132));
    operator delete(v11);
    *((_QWORD *)this + 1132) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 1133);
  if ( v12 )
  {
    BUFFER::~BUFFER(*((BUFFER **)this + 1133));
    operator delete(v12);
    *((_QWORD *)this + 1133) = 0;
  }
  v13 = *((_QWORD *)this + 47);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 56LL))(v13);
    *((_QWORD *)this + 47) = 0;
  }
  v14 = *((_QWORD *)this + 48);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
    *((_QWORD *)this + 48) = 0;
  }
  v15 = (W3_CONTEXT_BASE *)*((_QWORD *)this + 1139);
  if ( v15 )
  {
    W3_CONTEXT_BASE::DereferenceW3Context(v15);
    *((_QWORD *)this + 1139) = 0;
  }
  v16 = (W3_CONTEXT_BASE *)*((_QWORD *)this + 1138);
  if ( v16 )
  {
    W3_CONTEXT_BASE::DereferenceW3Context(v16);
    *((_QWORD *)this + 1138) = 0;
  }
  W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER((W3_CONTEXT *)((char *)this + 9120));
  *((_QWORD *)this + 1116) = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
  *((_QWORD *)this + 1117) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
  *((_QWORD *)this + 1118) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
  CONTEXT_CONTAINER::Cleanup((W3_CONTEXT *)((char *)this + 8928));
  CReaderWriterLock3::~CReaderWriterLock3((W3_CONTEXT *)((char *)this + 8952));
  STRU::~STRU((W3_CONTEXT *)((char *)this + 8728));
  STRU::~STRU((W3_CONTEXT *)((char *)this + 8416));
  STRU::~STRU((W3_CONTEXT *)((char *)this + 8104));
  v17 = (_QWORD *)**((_QWORD **)this + 251);
  while ( v17 )
  {
    v19 = v17;
    v17 = (_QWORD *)*v17;
    HeapFree(CONTEXT_ALLOC_BASE::sm_hHeap, 0, v19);
  }
  W3_RESPONSE::~W3_RESPONSE((W3_CONTEXT *)((char *)this + 408));
  BUFFER::~BUFFER((W3_CONTEXT *)((char *)this + 264));
  BUFFER::~BUFFER((W3_CONTEXT *)((char *)this + 216));
  STRU::~STRU((W3_CONTEXT *)((char *)this + 152));
  v18 = W3_CONTEXT_BASE::sm_pTraceLog;
  *((_QWORD *)this + 12) = &IISCORE_ASYNC_CONTEXT::`vftable';
  *(_QWORD *)this = &W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'};
  *((_QWORD *)this + 1) = &W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'};
  *((_QWORD *)this + 2) = &W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'};
  *((_QWORD *)this + 3) = &W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'};
  *((_QWORD *)this + 4) = &W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'};
  if ( v18 )
    WriteRefTraceLog(v18, *((unsigned int *)this + 19), this);
  *((_DWORD *)this + 18) = 2019767159;
}

```

## disassembly

```asm
0x18000df90  push    rbx
0x18000df92  push    rbp
0x18000df93  push    rsi
0x18000df94  push    rdi
0x18000df95  sub     rsp, 28h
0x18000df99  lea     rax, ??_7W3_CONTEXT@@6BIHttpContext4@@@; const W3_CONTEXT::`vftable'{for `IHttpContext4'}
0x18000dfa0  xor     ebp, ebp
0x18000dfa2  mov     rbx, rcx
0x18000dfa5  mov     [rcx], rax
0x18000dfa8  lea     rax, ??_7W3_CONTEXT@@6BIHttpTraceContext@@@; const W3_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x18000dfaf  mov     [rcx+8], rax
0x18000dfb3  lea     rax, ??_7W3_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x18000dfba  mov     [rcx+10h], rax
0x18000dfbe  lea     rax, ??_7W3_CONTEXT@@6BIModuleAllocator@@@; const W3_CONTEXT::`vftable'{for `IModuleAllocator'}
0x18000dfc5  mov     [rcx+18h], rax
0x18000dfc9  lea     rax, ??_7W3_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x18000dfd0  mov     [rcx+20h], rax
0x18000dfd4  cmp     [rcx+1F88h], rbp
0x18000dfdb  jz      short loc_18000E047
0x18000dfdd  mov     rcx, [rcx+178h]
0x18000dfe4  test    rcx, rcx
0x18000dfe7  jz      short loc_18000E047
0x18000dfe9  cmp     [rbx+190h], rbp
0x18000dff0  jnz     short loc_18000E047
0x18000dff2  mov     rax, [rcx]
0x18000dff5  mov     rax, [rax+10h]
0x18000dff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dffe  test    rax, rax
0x18000e001  jz      short loc_18000E00C
0x18000e003  cmp     [rax], bp
0x18000e006  jnz     loc_18000E2A8
0x18000e00c  mov     rax, [rbx+1F88h]
0x18000e013  mov     rdi, [rax+298h]
0x18000e01a  test    rdi, rdi
0x18000e01d  jz      short loc_18000E047
0x18000e01f  lea     rsi, [rbx+2478h]
0x18000e026  test    rsi, rsi
0x18000e029  jnz     loc_18000E262
0x18000e02f  mov     edx, ebp
0x18000e031  mov     eax, cs:dword_18004AD08
0x18000e037  mov     ecx, edx
0x18000e039  imul    rcx, [rdi+8]
0x18000e03e  add     rcx, rax
0x18000e041  add     rcx, [rdi]
0x18000e044  lock dec dword ptr [rcx]
0x18000e047  lea     rsi, [rbx+22E0h]
0x18000e04e  mov     rcx, rsi; this
0x18000e051  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000e056  cmp     [rbx+1FA0h], bpl
0x18000e05d  jnz     loc_18000E2CC
0x18000e063  mov     [rbx+1F98h], rbp
0x18000e06a  cmp     [rbx+1FA7h], bpl
0x18000e071  jnz     loc_18000E2DD
0x18000e077  mov     rdi, [rbx+1F88h]
0x18000e07e  mov     [rbx+22D0h], rbp
0x18000e085  test    rdi, rdi
0x18000e088  jz      short loc_18000E0A4
0x18000e08a  mov     eax, 0FFFFFFFFh
0x18000e08f  lock xadd [rdi+0Ch], eax
0x18000e094  cmp     eax, 1
0x18000e097  jz      loc_18000E2F5
0x18000e09d  mov     [rbx+1F88h], rbp
0x18000e0a4  mov     rcx, [rbx+22D8h]
0x18000e0ab  test    rcx, rcx
0x18000e0ae  jz      short loc_18000E0C8
0x18000e0b0  mov     rax, [rcx+8]
0x18000e0b4  add     rcx, 8
0x18000e0b8  mov     rax, [rax+10h]
0x18000e0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0c1  mov     [rbx+22D8h], rbp
0x18000e0c8  mov     rcx, [rbx+2358h]
0x18000e0cf  test    rcx, rcx
0x18000e0d2  jz      short loc_18000E0E7
0x18000e0d4  mov     rax, [rcx]
0x18000e0d7  mov     rax, [rax+10h]
0x18000e0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e0  mov     [rbx+2358h], rbp
0x18000e0e7  mov     rdi, [rbx+2360h]
0x18000e0ee  test    rdi, rdi
0x18000e0f1  jnz     loc_18000E30A
0x18000e0f7  mov     rdi, [rbx+2368h]
0x18000e0fe  test    rdi, rdi
0x18000e101  jnz     loc_18000E28B
0x18000e107  mov     rcx, [rbx+178h]
0x18000e10e  test    rcx, rcx
0x18000e111  jz      short loc_18000E126
0x18000e113  mov     rax, [rcx]
0x18000e116  mov     rax, [rax+38h]
0x18000e11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e11f  mov     [rbx+178h], rbp
0x18000e126  mov     rcx, [rbx+180h]
0x18000e12d  test    rcx, rcx
0x18000e130  jnz     loc_18000E327
0x18000e136  mov     rcx, [rbx+2398h]; this
0x18000e13d  test    rcx, rcx
0x18000e140  jnz     loc_18000E33F
0x18000e146  mov     rcx, [rbx+2390h]; this
0x18000e14d  test    rcx, rcx
0x18000e150  jnz     loc_18000E350
0x18000e156  lea     rcx, [rbx+23A0h]; this
0x18000e15d  call    ??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ; W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)
0x18000e162  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000e169  mov     rcx, rsi; this
0x18000e16c  mov     [rsi], rax
0x18000e16f  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000e176  mov     [rsi+8], rax
0x18000e17a  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000e181  mov     [rsi+10h], rax
0x18000e185  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000e18a  lea     rcx, [rsi+18h]
0x18000e18e  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000e194  lea     rcx, [rbx+2218h]
0x18000e19b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e1a1  lea     rcx, [rbx+20E0h]
0x18000e1a8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e1ae  lea     rcx, [rbx+1FA8h]
0x18000e1b5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e1bb  mov     rax, [rbx+7D8h]
0x18000e1c2  mov     rdi, [rax]
0x18000e1c5  test    rdi, rdi
0x18000e1c8  jnz     loc_18000E361
0x18000e1ce  lea     rcx, [rbx+198h]; this
0x18000e1d5  call    ??1W3_RESPONSE@@UEAA@XZ; W3_RESPONSE::~W3_RESPONSE(void)
0x18000e1da  lea     rcx, [rbx+108h]
0x18000e1e1  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e1e7  lea     rcx, [rbx+0D8h]
0x18000e1ee  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e1f4  lea     rcx, [rbx+98h]
0x18000e1fb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000e201  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18000e208  lea     rax, ??_7IISCORE_ASYNC_CONTEXT@@6B@; const IISCORE_ASYNC_CONTEXT::`vftable'
0x18000e20f  mov     [rbx+60h], rax
0x18000e213  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpContext4@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'}
0x18000e21a  mov     [rbx], rax
0x18000e21d  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpTraceContext@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'}
0x18000e224  mov     [rbx+8], rax
0x18000e228  lea     rax, ??_7W3_CONTEXT_BASE@@6BIMapHandlerProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'}
0x18000e22f  mov     [rbx+10h], rax
0x18000e233  lea     rax, ??_7W3_CONTEXT_BASE@@6BIModuleAllocator@@@; const W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'}
0x18000e23a  mov     [rbx+18h], rax
0x18000e23e  lea     rax, ??_7W3_CONTEXT_BASE@@6BIAuthenticationProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'}
0x18000e245  mov     [rbx+20h], rax
0x18000e249  test    rcx, rcx
0x18000e24c  jnz     loc_18000E380
0x18000e252  mov     dword ptr [rbx+48h], 78633377h
0x18000e259  add     rsp, 28h
0x18000e25d  pop     rdi
0x18000e25e  pop     rsi
0x18000e25f  pop     rbp
0x18000e260  pop     rbx
0x18000e261  retn
0x18000e262  mov     rdx, [rsi]
0x18000e265  mov     eax, 0FFFFFFFFh
0x18000e26a  cmp     rdx, rax
0x18000e26d  jnz     loc_18000E031
0x18000e273  call    cs:__imp_GetCurrentThreadId
0x18000e279  mov     eax, eax
0x18000e27b  xor     edx, edx
0x18000e27d  div     qword ptr [rdi+10h]
0x18000e281  mov     eax, edx
0x18000e283  mov     [rsi], rax
0x18000e286  jmp     loc_18000E031
0x18000e28b  mov     rcx, rdi
0x18000e28e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e294  mov     rcx, rdi; Block
0x18000e297  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e29c  mov     [rbx+2368h], rbp
0x18000e2a3  jmp     loc_18000E107
0x18000e2a8  mov     rcx, [rbx+1F88h]
0x18000e2af  lea     r8, [rbx+2478h]; unsigned __int64 *
0x18000e2b6  add     rcx, 290h; this
0x18000e2bd  mov     edx, 4; unsigned int
0x18000e2c2  call    ?DecrementCounter@SITE_PERF_COUNTERS@@QEAAXKPEA_KK@Z; SITE_PERF_COUNTERS::DecrementCounter(ulong,unsigned __int64 *,ulong)
0x18000e2c7  jmp     loc_18000E047
0x18000e2cc  mov     rcx, [rbx+1F98h]; this
0x18000e2d3  call    ?DereferenceApplication@W3_APPLICATION@@QEAAXXZ; W3_APPLICATION::DereferenceApplication(void)
0x18000e2d8  jmp     loc_18000E063
0x18000e2dd  mov     rcx, [rbx+22D0h]
0x18000e2e4  mov     rax, [rcx]
0x18000e2e7  mov     rax, [rax+28h]
0x18000e2eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2f0  jmp     loc_18000E077
0x18000e2f5  mov     rcx, rdi; this
0x18000e2f8  call    ??1W3_SITE@@AEAA@XZ; W3_SITE::~W3_SITE(void)
0x18000e2fd  mov     rcx, rdi; Block
0x18000e300  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e305  jmp     loc_18000E09D
0x18000e30a  mov     rcx, rdi
0x18000e30d  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000e313  mov     rcx, rdi; Block
0x18000e316  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e31b  mov     [rbx+2360h], rbp
0x18000e322  jmp     loc_18000E0F7
0x18000e327  mov     rax, [rcx]
0x18000e32a  mov     rax, [rax+38h]
0x18000e32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e333  mov     [rbx+180h], rbp
0x18000e33a  jmp     loc_18000E136
0x18000e33f  call    ?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ; W3_CONTEXT_BASE::DereferenceW3Context(void)
0x18000e344  mov     [rbx+2398h], rbp
0x18000e34b  jmp     loc_18000E146
0x18000e350  call    ?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ; W3_CONTEXT_BASE::DereferenceW3Context(void)
0x18000e355  mov     [rbx+2390h], rbp
0x18000e35c  jmp     loc_18000E156
0x18000e361  mov     rcx, cs:?sm_hHeap@CONTEXT_ALLOC_BASE@@0PEAXEA; hHeap
0x18000e368  mov     r8, rdi; lpMem
0x18000e36b  mov     rdi, [rdi]
0x18000e36e  xor     edx, edx; dwFlags
0x18000e370  call    cs:__imp_HeapFree
0x18000e376  test    rdi, rdi
0x18000e379  jnz     short loc_18000E361
0x18000e37b  jmp     loc_18000E1CE
0x18000e380  mov     edx, [rbx+4Ch]
0x18000e383  mov     r8, rbx
0x18000e386  call    cs:__imp_WriteRefTraceLog
0x18000e38c  jmp     loc_18000E252
```
