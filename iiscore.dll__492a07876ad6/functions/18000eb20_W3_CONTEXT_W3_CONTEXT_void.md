# W3_CONTEXT::~W3_CONTEXT(void)

- ea: `0x18000eb20`
- end: `0x18000ef6a`
- name: `??1W3_CONTEXT@@QEAA@XZ`
- size: `1098`
- prototype: `void __fastcall(W3_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18000ea5c`
- `0x1800214b0`

## callees

- `0x18000eb20`
- `0x18000ef70`
- `0x18000f0d4`
- `0x18000f2cc`
- `0x180016ad0`
- `0x180016b74`
- `0x18001ab70`
- `0x1800212f8`
- `0x1800306ac`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ee2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef3d`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000ed1e`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000ed1e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ed89`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ed9c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ee4f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000eed4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ed89`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ed9c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000ee4f`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000eed4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed44`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed57`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000edaf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed31`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed44`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000ed57`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000edaf`
- `iisutil!WriteRefTraceLog` at `0x18000ef59`
- `iisutil!WriteRefTraceLog` at `0x18000ef59`

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
                                                            + (unsigned int)dword_18004DD08
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
0x18000eb20  push    rbx
0x18000eb22  push    rbp
0x18000eb23  push    rsi
0x18000eb24  push    rdi
0x18000eb25  sub     rsp, 28h
0x18000eb29  lea     rax, ??_7W3_CONTEXT@@6BIHttpContext4@@@; const W3_CONTEXT::`vftable'{for `IHttpContext4'}
0x18000eb30  xor     ebp, ebp
0x18000eb32  mov     rbx, rcx
0x18000eb35  mov     [rcx], rax
0x18000eb38  lea     rax, ??_7W3_CONTEXT@@6BIHttpTraceContext@@@; const W3_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x18000eb3f  mov     [rcx+8], rax
0x18000eb43  lea     rax, ??_7W3_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x18000eb4a  mov     [rcx+10h], rax
0x18000eb4e  lea     rax, ??_7W3_CONTEXT@@6BIModuleAllocator@@@; const W3_CONTEXT::`vftable'{for `IModuleAllocator'}
0x18000eb55  mov     [rcx+18h], rax
0x18000eb59  lea     rax, ??_7W3_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x18000eb60  mov     [rcx+20h], rax
0x18000eb64  cmp     [rcx+1F88h], rbp
0x18000eb6b  jz      short loc_18000EBD7
0x18000eb6d  mov     rcx, [rcx+178h]
0x18000eb74  test    rcx, rcx
0x18000eb77  jz      short loc_18000EBD7
0x18000eb79  cmp     [rbx+190h], rbp
0x18000eb80  jnz     short loc_18000EBD7
0x18000eb82  mov     rax, [rcx]
0x18000eb85  mov     rax, [rax+10h]
0x18000eb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb8e  test    rax, rax
0x18000eb91  jz      short loc_18000EB9C
0x18000eb93  cmp     [rax], bp
0x18000eb96  jnz     loc_18000EE6F
0x18000eb9c  mov     rax, [rbx+1F88h]
0x18000eba3  mov     rdi, [rax+298h]
0x18000ebaa  test    rdi, rdi
0x18000ebad  jz      short loc_18000EBD7
0x18000ebaf  lea     rsi, [rbx+2478h]
0x18000ebb6  test    rsi, rsi
0x18000ebb9  jnz     loc_18000EE1D
0x18000ebbf  mov     edx, ebp
0x18000ebc1  mov     eax, cs:dword_18004DD08
0x18000ebc7  mov     ecx, edx
0x18000ebc9  imul    rcx, [rdi+8]
0x18000ebce  add     rcx, rax
0x18000ebd1  add     rcx, [rdi]
0x18000ebd4  lock dec dword ptr [rcx]
0x18000ebd7  lea     rsi, [rbx+22E0h]
0x18000ebde  mov     rcx, rsi; this
0x18000ebe1  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000ebe6  cmp     [rbx+1FA0h], bpl
0x18000ebed  jnz     loc_18000EE93
0x18000ebf3  mov     [rbx+1F98h], rbp
0x18000ebfa  cmp     [rbx+1FA7h], bpl
0x18000ec01  jnz     loc_18000EEA4
0x18000ec07  mov     rdi, [rbx+1F88h]
0x18000ec0e  mov     [rbx+22D0h], rbp
0x18000ec15  test    rdi, rdi
0x18000ec18  jz      short loc_18000EC34
0x18000ec1a  mov     eax, 0FFFFFFFFh
0x18000ec1f  lock xadd [rdi+0Ch], eax
0x18000ec24  cmp     eax, 1
0x18000ec27  jz      loc_18000EEBC
0x18000ec2d  mov     [rbx+1F88h], rbp
0x18000ec34  mov     rcx, [rbx+22D8h]
0x18000ec3b  test    rcx, rcx
0x18000ec3e  jz      short loc_18000EC58
0x18000ec40  mov     rax, [rcx+8]
0x18000ec44  add     rcx, 8
0x18000ec48  mov     rax, [rax+10h]
0x18000ec4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec51  mov     [rbx+22D8h], rbp
0x18000ec58  mov     rcx, [rbx+2358h]
0x18000ec5f  test    rcx, rcx
0x18000ec62  jz      short loc_18000EC77
0x18000ec64  mov     rax, [rcx]
0x18000ec67  mov     rax, [rax+10h]
0x18000ec6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec70  mov     [rbx+2358h], rbp
0x18000ec77  mov     rdi, [rbx+2360h]
0x18000ec7e  test    rdi, rdi
0x18000ec81  jnz     loc_18000EED1
0x18000ec87  mov     rdi, [rbx+2368h]
0x18000ec8e  test    rdi, rdi
0x18000ec91  jnz     loc_18000EE4C
0x18000ec97  mov     rcx, [rbx+178h]
0x18000ec9e  test    rcx, rcx
0x18000eca1  jz      short loc_18000ECB6
0x18000eca3  mov     rax, [rcx]
0x18000eca6  mov     rax, [rax+38h]
0x18000ecaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecaf  mov     [rbx+178h], rbp
0x18000ecb6  mov     rcx, [rbx+180h]
0x18000ecbd  test    rcx, rcx
0x18000ecc0  jnz     loc_18000EEF4
0x18000ecc6  mov     rcx, [rbx+2398h]; this
0x18000eccd  test    rcx, rcx
0x18000ecd0  jnz     loc_18000EF0C
0x18000ecd6  mov     rcx, [rbx+2390h]; this
0x18000ecdd  test    rcx, rcx
0x18000ece0  jnz     loc_18000EF1D
0x18000ece6  lea     rcx, [rbx+23A0h]; this
0x18000eced  call    ??1W3_TRACE_EVENT_MANAGER@@QEAA@XZ; W3_TRACE_EVENT_MANAGER::~W3_TRACE_EVENT_MANAGER(void)
0x18000ecf2  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000ecf9  mov     rcx, rsi; this
0x18000ecfc  mov     [rsi], rax
0x18000ecff  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000ed06  mov     [rsi+8], rax
0x18000ed0a  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000ed11  mov     [rsi+10h], rax
0x18000ed15  call    ?Cleanup@CONTEXT_CONTAINER@@QEAAXXZ; CONTEXT_CONTAINER::Cleanup(void)
0x18000ed1a  lea     rcx, [rsi+18h]
0x18000ed1e  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000ed25  nop     dword ptr [rax+rax+00h]
0x18000ed2a  lea     rcx, [rbx+2218h]
0x18000ed31  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ed38  nop     dword ptr [rax+rax+00h]
0x18000ed3d  lea     rcx, [rbx+20E0h]
0x18000ed44  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ed4b  nop     dword ptr [rax+rax+00h]
0x18000ed50  lea     rcx, [rbx+1FA8h]
0x18000ed57  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000ed5e  nop     dword ptr [rax+rax+00h]
0x18000ed63  mov     rax, [rbx+7D8h]
0x18000ed6a  mov     rdi, [rax]
0x18000ed6d  test    rdi, rdi
0x18000ed70  jnz     loc_18000EF2E
0x18000ed76  lea     rcx, [rbx+198h]; this
0x18000ed7d  call    ??1W3_RESPONSE@@UEAA@XZ; W3_RESPONSE::~W3_RESPONSE(void)
0x18000ed82  lea     rcx, [rbx+108h]
0x18000ed89  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ed90  nop     dword ptr [rax+rax+00h]
0x18000ed95  lea     rcx, [rbx+0D8h]
0x18000ed9c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000eda3  nop     dword ptr [rax+rax+00h]
0x18000eda8  lea     rcx, [rbx+98h]
0x18000edaf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000edb6  nop     dword ptr [rax+rax+00h]
0x18000edbb  mov     rcx, cs:?sm_pTraceLog@W3_CONTEXT_BASE@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * W3_CONTEXT_BASE::sm_pTraceLog
0x18000edc2  lea     rax, ??_7IISCORE_ASYNC_CONTEXT@@6B@; const IISCORE_ASYNC_CONTEXT::`vftable'
0x18000edc9  mov     [rbx+60h], rax
0x18000edcd  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpContext4@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpContext4'}
0x18000edd4  mov     [rbx], rax
0x18000edd7  lea     rax, ??_7W3_CONTEXT_BASE@@6BIHttpTraceContext@@@; const W3_CONTEXT_BASE::`vftable'{for `IHttpTraceContext'}
0x18000edde  mov     [rbx+8], rax
0x18000ede2  lea     rax, ??_7W3_CONTEXT_BASE@@6BIMapHandlerProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IMapHandlerProvider'}
0x18000ede9  mov     [rbx+10h], rax
0x18000eded  lea     rax, ??_7W3_CONTEXT_BASE@@6BIModuleAllocator@@@; const W3_CONTEXT_BASE::`vftable'{for `IModuleAllocator'}
0x18000edf4  mov     [rbx+18h], rax
0x18000edf8  lea     rax, ??_7W3_CONTEXT_BASE@@6BIAuthenticationProvider@@@; const W3_CONTEXT_BASE::`vftable'{for `IAuthenticationProvider'}
0x18000edff  mov     [rbx+20h], rax
0x18000ee03  test    rcx, rcx
0x18000ee06  jnz     loc_18000EF53
0x18000ee0c  mov     dword ptr [rbx+48h], 78633377h
0x18000ee13  add     rsp, 28h
0x18000ee17  pop     rdi
0x18000ee18  pop     rsi
0x18000ee19  pop     rbp
0x18000ee1a  pop     rbx
0x18000ee1b  retn
0x18000ee1d  mov     rdx, [rsi]
0x18000ee20  mov     eax, 0FFFFFFFFh
0x18000ee25  cmp     rdx, rax
0x18000ee28  jnz     loc_18000EBC1
0x18000ee2e  call    cs:__imp_GetCurrentThreadId
0x18000ee35  nop     dword ptr [rax+rax+00h]
0x18000ee3a  mov     eax, eax
0x18000ee3c  xor     edx, edx
0x18000ee3e  div     qword ptr [rdi+10h]
0x18000ee42  mov     eax, edx
0x18000ee44  mov     [rsi], rax
0x18000ee47  jmp     loc_18000EBC1
0x18000ee4c  mov     rcx, rdi
0x18000ee4f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000ee56  nop     dword ptr [rax+rax+00h]
0x18000ee5b  mov     rcx, rdi; Block
0x18000ee5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ee63  mov     [rbx+2368h], rbp
0x18000ee6a  jmp     loc_18000EC97
0x18000ee6f  mov     rcx, [rbx+1F88h]
0x18000ee76  lea     r8, [rbx+2478h]; unsigned __int64 *
0x18000ee7d  add     rcx, 290h; this
0x18000ee84  mov     edx, 4; unsigned int
0x18000ee89  call    ?DecrementCounter@SITE_PERF_COUNTERS@@QEAAXKPEA_KK@Z; SITE_PERF_COUNTERS::DecrementCounter(ulong,unsigned __int64 *,ulong)
0x18000ee8e  jmp     loc_18000EBD7
0x18000ee93  mov     rcx, [rbx+1F98h]; this
0x18000ee9a  call    ?DereferenceApplication@W3_APPLICATION@@QEAAXXZ; W3_APPLICATION::DereferenceApplication(void)
0x18000ee9f  jmp     loc_18000EBF3
0x18000eea4  mov     rcx, [rbx+22D0h]
0x18000eeab  mov     rax, [rcx]
0x18000eeae  mov     rax, [rax+28h]
0x18000eeb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeb7  jmp     loc_18000EC07
0x18000eebc  mov     rcx, rdi; this
0x18000eebf  call    ??1W3_SITE@@AEAA@XZ; W3_SITE::~W3_SITE(void)
0x18000eec4  mov     rcx, rdi; Block
0x18000eec7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eecc  jmp     loc_18000EC2D
0x18000eed1  mov     rcx, rdi
0x18000eed4  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000eedb  nop     dword ptr [rax+rax+00h]
0x18000eee0  mov     rcx, rdi; Block
0x18000eee3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eee8  mov     [rbx+2360h], rbp
0x18000eeef  jmp     loc_18000EC87
0x18000eef4  mov     rax, [rcx]
0x18000eef7  mov     rax, [rax+38h]
0x18000eefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef00  mov     [rbx+180h], rbp
0x18000ef07  jmp     loc_18000ECC6
0x18000ef0c  call    ?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ; W3_CONTEXT_BASE::DereferenceW3Context(void)
0x18000ef11  mov     [rbx+2398h], rbp
0x18000ef18  jmp     loc_18000ECD6
0x18000ef1d  call    ?DereferenceW3Context@W3_CONTEXT_BASE@@QEAAXXZ; W3_CONTEXT_BASE::DereferenceW3Context(void)
0x18000ef22  mov     [rbx+2390h], rbp
0x18000ef29  jmp     loc_18000ECE6
0x18000ef2e  mov     rcx, cs:?sm_hHeap@CONTEXT_ALLOC_BASE@@0PEAXEA; hHeap
0x18000ef35  mov     r8, rdi; lpMem
0x18000ef38  mov     rdi, [rdi]
0x18000ef3b  xor     edx, edx; dwFlags
0x18000ef3d  call    cs:__imp_HeapFree
0x18000ef44  nop     dword ptr [rax+rax+00h]
0x18000ef49  test    rdi, rdi
0x18000ef4c  jnz     short loc_18000EF2E
0x18000ef4e  jmp     loc_18000ED76
0x18000ef53  mov     edx, [rbx+4Ch]
0x18000ef56  mov     r8, rbx
0x18000ef59  call    cs:__imp_WriteRefTraceLog
0x18000ef60  nop     dword ptr [rax+rax+00h]
0x18000ef65  jmp     loc_18000EE0C
```
