# _CCorSvcMgr::TryProcessEmptyConfiguration_::_1_::catch$22

- ea: `0x180044593`
- end: `0x1800448ea`
- name: `_CCorSvcMgr::TryProcessEmptyConfiguration_::_1_::catch$22`
- size: `855`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005cec`
- `0x18000c8a8`
- `0x180025110`
- `0x18002dc24`
- `0x18002ff64`
- `0x180030d84`
- `0x180032654`
- `0x180033ab4`
- `0x180034de4`
- `0x180034fd4`
- `0x1800350c4`
- `0x18003549c`
- `0x180036524`
- `0x1800366a8`
- `0x18003f1db`
- `0x18003f280`
- `0x180044593`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800447f4`
- `KERNEL32!HeapFree` at `0x180044831`
- `KERNEL32!HeapFree` at `0x1800447f4`
- `KERNEL32!HeapFree` at `0x180044831`
- `KERNEL32!GetProcessHeap` at `0x1800447df`
- `KERNEL32!GetProcessHeap` at `0x18004481c`
- `KERNEL32!GetProcessHeap` at `0x1800447df`
- `KERNEL32!GetProcessHeap` at `0x18004481c`

## string_xrefs

- `0x180044724`: `Uninstalling assembly %s because of an error during compilation: %s.\n`

## pseudocode

```c
__int64 __fastcall CCorSvcMgr::TryProcessEmptyConfiguration_::_1_::catch_22(__int64 a1, __int64 a2, bool a3)
{
  Exception *v4; // rdi
  Exception *v5; // r14
  int v6; // esi
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 v9; // r13
  __int64 v10; // rax
  __int64 v11; // r14
  __int64 v12; // r8
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  void *v15; // rbx
  HANDLE v16; // rax
  Exception *v17; // rcx
  bool v18; // dl
  unsigned int CurrentExceptionCode; // eax
  int v20; // edx

  *(_QWORD *)(a2 + 72) = &Exception::`vftable';
  *(_QWORD *)(a2 + 80) = 0;
  *(_QWORD *)(a2 + 72) = &DelegatingException::`vftable';
  *(_QWORD *)(a2 + 88) = -1;
  v4 = *(Exception **)(a2 + 48);
  *(_QWORD *)(a2 + 56) = v4;
  *(_DWORD *)(a2 + 64) = 0;
  *(_DWORD *)(a2 + 64) = v4 != 0;
  Exception::HandlerState::SetupCatch((Exception::HandlerState *)(a2 + 40), 2272, a3);
  v5 = (Exception *)(a2 + 72);
  if ( v4 )
    v5 = v4;
  v6 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v5 + 16LL))(v5);
  v7 = *(_QWORD *)(a2 + 96);
  if ( (unsigned int)CCorSvcMgr::IsInterruptRequested((BSTR *)v7) )
    ThrowHR(-2146230784);
  if ( v6 == -2147023446 )
    ThrowHR(-2147023446);
  *(_DWORD *)(a2 + 128) = 0;
  *(_DWORD *)(a2 + 132) = 0;
  *(_DWORD *)(a2 + 136) = 0;
  *(_QWORD *)(a2 + 144) = 0;
  *(_QWORD *)(a2 + 144) = a2 + 152;
  *(_DWORD *)(a2 + 132) = 512;
  *(_DWORD *)(a2 + 128) = 2;
  **(_WORD **)(a2 + 144) = 0;
  (*(void (__fastcall **)(Exception *, __int64))(*(_QWORD *)v5 + 24LL))(v5, a2 + 128);
  *(_DWORD *)(a2 + 672) = 0;
  *(_DWORD *)(a2 + 676) = 0;
  *(_DWORD *)(a2 + 680) = 0;
  *(_QWORD *)(a2 + 688) = 0;
  *(_QWORD *)(a2 + 688) = a2 + 696;
  *(_DWORD *)(a2 + 676) = 512;
  *(_DWORD *)(a2 + 672) = 2;
  **(_WORD **)(a2 + 688) = 0;
  SString::ConvertToUnicode((SString *)(a2 + 128));
  v8 = *(_QWORD *)(a2 + 144);
  v9 = *(_QWORD *)(a2 + 104);
  v10 = *(_QWORD *)(v9 + 8);
  v11 = *(_QWORD *)(v10 + 24);
  if ( v11 )
  {
    SString::ConvertToUnicode(*(SString **)(v10 + 24));
    v12 = *(_QWORD *)(v11 + 16);
  }
  else
  {
    v12 = 0;
  }
  SString::Printf(
    (SString *)(a2 + 672),
    L"Uninstalling assembly %s because of an error during compilation: %s.\n",
    v12,
    v8);
  SString::ConvertToUnicode((SString *)(a2 + 672));
  Logger::Log(v7 + 208, *(_QWORD *)(a2 + 688), 1);
  Node::SetStatus(v9, 0);
  WorkQueue::AppendJobToSecondaryList((WorkQueue *)(v7 + 104), *(struct Root **)(v9 + 8));
  if ( *(int *)(v7 + 1264) >= 0 )
    *(_DWORD *)(v7 + 1264) = v6;
  if ( *(_DWORD *)(v7 + 1264) == -2147467260 )
    *(_DWORD *)(v7 + 1264) = v6;
  if ( v6 == -2147024784 )
    *(_DWORD *)(v7 + 1264) = -2147024784;
  if ( !*(_DWORD *)(v7 + 1268) )
    ThrowHR(v6, (const struct SString *)(a2 + 128));
  if ( *(int *)(v7 + 1284) >= 0 )
    *(_DWORD *)(v7 + 1284) = v6;
  if ( (*(_BYTE *)(a2 + 680) & 8) != 0 )
  {
    v13 = *(void **)(a2 + 688);
    if ( v13 )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v13);
    }
  }
  if ( (*(_BYTE *)(a2 + 136) & 8) != 0 )
  {
    v15 = *(void **)(a2 + 144);
    if ( v15 )
    {
      v16 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v16 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v16;
      }
      HeapFree(v16, 0, v15);
    }
  }
  v17 = (Exception *)(a2 + 72);
  if ( v4 )
    v17 = v4;
  if ( (unsigned int)Exception::IsTerminal(v17)
    || !CLRConfig::GetConfigValue(
          (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
          v18,
          (bool *)(a2 + 32))
    && (CurrentExceptionCode = GetCurrentExceptionCode(),
        (unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v20)) )
  {
    *(_DWORD *)(a2 + 64) = 0;
    throw;
  }
  if ( v4 )
  {
    if ( !(*(unsigned int (__fastcall **)(Exception *))(*(_QWORD *)v4 + 80LL))(v4) )
      (**(void (__fastcall ***)(Exception *, __int64))v4)(v4, 5);
    *(_DWORD *)(a2 + 64) = 0;
  }
  DelegatingException::~DelegatingException((DelegatingException *)(a2 + 72));
  return 0;
}

```

## disassembly

```asm
0x180044593  mov     [rsp+arg_8], rdx
0x180044598  push    rbx
0x180044599  push    rbp
0x18004459a  push    rsi
0x18004459b  push    rdi
0x18004459c  push    r12
0x18004459e  push    r13
0x1800445a0  push    r14
0x1800445a2  push    r15
0x1800445a4  sub     rsp, 28h
0x1800445a8  mov     rbp, rdx
0x1800445ab  lea     rax, ??_7Exception@@6B@; const Exception::`vftable'
0x1800445b2  mov     [rbp+48h], rax
0x1800445b6  and     qword ptr [rbp+50h], 0
0x1800445bb  lea     rax, ??_7DelegatingException@@6B@; const DelegatingException::`vftable'
0x1800445c2  mov     [rbp+48h], rax
0x1800445c6  or      qword ptr [rbp+58h], 0FFFFFFFFFFFFFFFFh
0x1800445cb  mov     rdi, [rbp+30h]
0x1800445cf  mov     [rbp+38h], rdi
0x1800445d3  xor     r15d, r15d
0x1800445d6  mov     [rbp+40h], r15d
0x1800445da  lea     eax, [r15+1]
0x1800445de  test    rdi, rdi
0x1800445e1  cmovnz  r15d, eax
0x1800445e5  mov     [rbp+40h], r15d
0x1800445e9  mov     edx, 8E0h; int
0x1800445ee  lea     rcx, [rbp+28h]; this
0x1800445f2  call    ?SetupCatch@HandlerState@Exception@@QEAAXH_N@Z; Exception::HandlerState::SetupCatch(int,bool)
0x1800445f7  lea     r14, [rbp+48h]
0x1800445fb  test    rdi, rdi
0x1800445fe  cmovnz  r14, rdi
0x180044602  mov     rax, [r14]
0x180044605  mov     rcx, r14
0x180044608  mov     rax, [rax+10h]
0x18004460c  call    cs:__guard_dispatch_icall_fptr
0x180044612  mov     esi, eax
0x180044614  mov     rbx, [rbp+60h]
0x180044618  mov     rcx, rbx; this
0x18004461b  call    ?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ; CCorSvcMgr::IsInterruptRequested(void)
0x180044620  test    eax, eax
0x180044622  jz      short loc_18004462F
0x180044624  mov     ecx, 80131E00h; int
0x180044629  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18004462f  cmp     esi, 800705AAh
0x180044635  jnz     short loc_18004463F
0x180044637  mov     ecx, esi; int
0x180044639  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18004463f  and     dword ptr [rbp+80h], 0
0x180044646  and     dword ptr [rbp+84h], 0
0x18004464d  and     dword ptr [rbp+88h], 0
0x180044654  and     qword ptr [rbp+90h], 0
0x18004465c  lea     rax, [rbp+98h]
0x180044663  mov     [rbp+90h], rax
0x18004466a  mov     dword ptr [rbp+84h], 200h
0x180044674  mov     dword ptr [rbp+80h], 2
0x18004467e  xor     ecx, ecx
0x180044680  mov     rax, [rbp+90h]
0x180044687  mov     [rax], cx
0x18004468a  mov     rax, [r14]
0x18004468d  lea     rdx, [rbp+80h]
0x180044694  mov     rcx, r14
0x180044697  mov     rax, [rax+18h]
0x18004469b  call    cs:__guard_dispatch_icall_fptr
0x1800446a1  and     dword ptr [rbp+2A0h], 0
0x1800446a8  and     dword ptr [rbp+2A4h], 0
0x1800446af  and     dword ptr [rbp+2A8h], 0
0x1800446b6  and     qword ptr [rbp+2B0h], 0
0x1800446be  lea     rax, [rbp+2B8h]
0x1800446c5  mov     [rbp+2B0h], rax
0x1800446cc  mov     dword ptr [rbp+2A4h], 200h
0x1800446d6  mov     dword ptr [rbp+2A0h], 2
0x1800446e0  xor     ecx, ecx
0x1800446e2  mov     rax, [rbp+2B0h]
0x1800446e9  mov     [rax], cx
0x1800446ec  lea     rcx, [rbp+80h]; this
0x1800446f3  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800446f8  mov     r12, [rbp+90h]
0x1800446ff  mov     r13, [rbp+68h]
0x180044703  mov     rax, [r13+8]
0x180044707  mov     r14, [rax+18h]
0x18004470b  test    r14, r14
0x18004470e  jnz     short loc_180044715
0x180044710  xor     r8d, r8d
0x180044713  jmp     short loc_180044721
0x180044715  mov     rcx, r14; this
0x180044718  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18004471d  mov     r8, [r14+10h]
0x180044721  mov     r9, r12
0x180044724  lea     rdx, aUninstallingAs_1; "Uninstalling assembly %s because of an "...
0x18004472b  lea     rcx, [rbp+2A0h]; this
0x180044732  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180044737  lea     rcx, [rbp+2A0h]; this
0x18004473e  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180044743  lea     rcx, [rbx+0D0h]
0x18004474a  mov     r8d, 1
0x180044750  mov     rdx, [rbp+2B0h]
0x180044757  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x18004475c  xor     edx, edx
0x18004475e  mov     rcx, r13
0x180044761  call    ?SetStatus@Node@@QEAAXW4EntryStatus@@@Z; Node::SetStatus(EntryStatus)
0x180044766  lea     rcx, [rbx+68h]; this
0x18004476a  mov     rdx, [r13+8]; struct Root *
0x18004476e  call    ?AppendJobToSecondaryList@WorkQueue@@QEAAXPEAVRoot@@@Z; WorkQueue::AppendJobToSecondaryList(Root *)
0x180044773  cmp     dword ptr [rbx+4F0h], 0
0x18004477a  jl      short loc_180044782
0x18004477c  mov     [rbx+4F0h], esi
0x180044782  cmp     dword ptr [rbx+4F0h], 80004004h
0x18004478c  jnz     short loc_180044794
0x18004478e  mov     [rbx+4F0h], esi
0x180044794  cmp     esi, 80070070h
0x18004479a  jnz     short loc_1800447A2
0x18004479c  mov     [rbx+4F0h], esi
0x1800447a2  cmp     dword ptr [rbx+4F4h], 0
0x1800447a9  jz      loc_1800448C9
0x1800447af  cmp     dword ptr [rbx+504h], 0
0x1800447b6  jl      short loc_1800447BE
0x1800447b8  mov     [rbx+504h], esi
0x1800447be  test    byte ptr [rbp+2A8h], 8
0x1800447c5  jz      short loc_1800447FB
0x1800447c7  mov     rbx, [rbp+2B0h]
0x1800447ce  test    rbx, rbx
0x1800447d1  jz      short loc_1800447FB
0x1800447d3  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800447da  test    rax, rax
0x1800447dd  jnz     short loc_1800447EC
0x1800447df  call    cs:__imp_GetProcessHeap
0x1800447e5  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800447ec  mov     r8, rbx; lpMem
0x1800447ef  xor     edx, edx; dwFlags
0x1800447f1  mov     rcx, rax; hHeap
0x1800447f4  call    cs:__imp_HeapFree
0x1800447fa  nop
0x1800447fb  test    byte ptr [rbp+88h], 8
0x180044802  jz      short loc_180044837
0x180044804  mov     rbx, [rbp+90h]
0x18004480b  test    rbx, rbx
0x18004480e  jz      short loc_180044837
0x180044810  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180044817  test    rax, rax
0x18004481a  jnz     short loc_180044829
0x18004481c  call    cs:__imp_GetProcessHeap
0x180044822  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180044829  mov     r8, rbx; lpMem
0x18004482c  xor     edx, edx; dwFlags
0x18004482e  mov     rcx, rax; hHeap
0x180044831  call    cs:__imp_HeapFree
0x180044837  lea     rcx, [rbp+48h]
0x18004483b  test    rdi, rdi
0x18004483e  cmovnz  rcx, rdi; this
0x180044842  call    ?IsTerminal@Exception@@QEAAHXZ; Exception::IsTerminal(void)
0x180044847  test    eax, eax
0x180044849  jnz     short loc_1800448BB
0x18004484b  lea     r8, [rbp+20h]; bool *
0x18004484f  lea     rcx, ?UNSUPPORTED_legacyCorruptedStateExceptionsPolicy@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180044856  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18004485b  test    eax, eax
0x18004485d  jnz     short loc_18004486F
0x18004485f  call    ?GetCurrentExceptionCode@@YAKXZ; GetCurrentExceptionCode(void)
0x180044864  mov     ecx, eax; unsigned int
0x180044866  call    ?IsProcessCorruptedStateException@@YAHKH@Z; IsProcessCorruptedStateException(ulong,int)
0x18004486b  test    eax, eax
0x18004486d  jnz     short loc_1800448BB
0x18004486f  test    r15d, r15d
0x180044872  jz      short loc_1800448A5
0x180044874  test    rdi, rdi
0x180044877  jz      short loc_1800448A1
0x180044879  mov     rax, [rdi]
0x18004487c  mov     rcx, rdi
0x18004487f  mov     rax, [rax+50h]
0x180044883  call    cs:__guard_dispatch_icall_fptr
0x180044889  test    eax, eax
0x18004488b  jnz     short loc_1800448A1
0x18004488d  mov     rax, [rdi]
0x180044890  mov     edx, 5
0x180044895  mov     rcx, rdi
0x180044898  mov     rax, [rax]
0x18004489b  call    cs:__guard_dispatch_icall_fptr
0x1800448a1  and     dword ptr [rbp+40h], 0
0x1800448a5  lea     rcx, [rbp+48h]; this
0x1800448a9  call    ??1DelegatingException@@UEAA@XZ; DelegatingException::~DelegatingException(void)
0x1800448ae  nop
0x1800448af  mov     rax, 0
0x1800448b9  jmp     short loc_1800448D8
0x1800448bb  and     dword ptr [rbp+40h], 0
0x1800448bf  xor     edx, edx; pThrowInfo
0x1800448c1  xor     ecx, ecx; pExceptionObject
0x1800448c3  call    _CxxThrowException_0
0x1800448c9  lea     rdx, [rbp+80h]; struct SString *
0x1800448d0  mov     ecx, esi; int
0x1800448d2  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
0x1800448d8  add     rsp, 28h
0x1800448dc  pop     r15
0x1800448de  pop     r14
0x1800448e0  pop     r13
0x1800448e2  pop     r12
0x1800448e4  pop     rdi
0x1800448e5  pop     rsi
0x1800448e6  pop     rbp
0x1800448e7  pop     rbx
0x1800448e8  retn
```
