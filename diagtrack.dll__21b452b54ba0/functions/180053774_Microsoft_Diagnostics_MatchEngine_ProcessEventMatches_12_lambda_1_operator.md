# _Microsoft::Diagnostics::MatchEngine::ProcessEventMatches_::_12_::_lambda_1_::operator()

- ea: `0x180053774`
- end: `0x180053d27`
- name: `_Microsoft::Diagnostics::MatchEngine::ProcessEventMatches_::_12_::_lambda_1_::operator()`
- size: `1459`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052d2c`
- `0x180053754`

## callees

- `0x180053774`
- `0x180054a74`
- `0x180055730`
- `0x18006bc74`
- `0x1800b0d1c`
- `0x1800b6104`
- `0x1800b6194`
- `0x1800b6204`
- `0x1800f71e4`
- `0x1801a38f4`
- `0x1801bbc78`
- `0x18020aac0`
- `0x18020ba94`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18005383f`
- `msvcp_win!_Mtx_lock` at `0x1800538b3`
- `msvcp_win!_Mtx_lock` at `0x18005383f`
- `msvcp_win!_Mtx_lock` at `0x1800538b3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180053cfe`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180053d20`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180053cfe`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180053d20`
- `msvcp_win!_Mtx_unlock` at `0x18005386f`
- `msvcp_win!_Mtx_unlock` at `0x180053b1f`
- `msvcp_win!_Mtx_unlock` at `0x180053c38`
- `msvcp_win!_Mtx_unlock` at `0x180053cdd`
- `msvcp_win!_Mtx_unlock` at `0x18005386f`
- `msvcp_win!_Mtx_unlock` at `0x180053b1f`
- `msvcp_win!_Mtx_unlock` at `0x180053c38`
- `msvcp_win!_Mtx_unlock` at `0x180053cdd`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180053d14`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180053d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800537cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800537cc`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800537e1`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x1800537e1`

## string_xrefs

- `0x180053bbb`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Microsoft::Diagnostics::MatchEngine::ProcessEventMatches_::_12_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // r14
  HANDLE CurrentThread; // rax
  unsigned __int64 *v7; // rdx
  unsigned __int64 v8; // r12
  __int64 *v9; // rax
  __int64 v10; // r15
  __int64 inserted; // rsi
  _QWORD *v12; // rdi
  void *v13; // r13
  __int64 v14; // rbx
  char v15; // al
  __int64 v16; // r13
  __int64 v17; // rdi
  _QWORD *v18; // rax
  __int64 v19; // rdi
  __int16 v20; // r10
  unsigned __int64 v21; // r9
  char v22; // r8
  __int64 v23; // rax
  int *v24; // rcx
  unsigned int v25; // eax
  int v26; // edx
  float v27; // xmm1_4
  __int64 v28; // rsi
  __int64 v29; // rdi
  _QWORD *v30; // rax
  __int64 v31; // rdi
  __int64 v32; // r15
  __int64 v33; // r8
  int result; // eax
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // rax
  __int64 v44; // r11
  __int64 v45; // r10
  void *Buf2; // [rsp+30h] [rbp-59h]
  unsigned __int64 CycleTime; // [rsp+38h] [rbp-51h] BYREF
  __int128 v48; // [rsp+40h] [rbp-49h]
  __int64 v49; // [rsp+58h] [rbp-31h]
  __int64 v50; // [rsp+60h] [rbp-29h] BYREF
  void *v51; // [rsp+68h] [rbp-21h]
  __int128 v52; // [rsp+70h] [rbp-19h] BYREF
  __int128 v53; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v54[2]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631F0 + 1, 0, 0) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
      a4);
  v5 = (__int64)*(&xmmword_1804631F0 + 1);
  v49 = **(_QWORD **)(a1 + 40);
  CurrentThread = GetCurrentThread();
  CycleTime = 0;
  QueryThreadCycleTime(CurrentThread, &CycleTime);
  v7 = *(unsigned __int64 **)(a1 + 32);
  if ( *v7 && CycleTime )
    v8 = (CycleTime - *v7) & -(__int64)(*v7 < CycleTime);
  else
    v8 = 0;
  *v7 = CycleTime;
  v9 = *(__int64 **)(a1 + 24);
  v10 = v9[1];
  inserted = *v9;
  CycleTime = **(_QWORD **)(a1 + 16);
  v12 = *(_QWORD **)(a1 + 8);
  v13 = *(void **)a1;
  Buf2 = *(void **)a1;
  v14 = v5 + 1256;
  if ( _Mtx_lock((_Mtx_t)(v5 + 1256)) )
    goto LABEL_65;
  if ( *(_DWORD *)(v5 + 1332) == 0x7FFFFFFF )
  {
LABEL_62:
    *(_DWORD *)(v14 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
LABEL_63:
    v26 = -1;
    goto LABEL_27;
  }
  *(_QWORD *)(v5 + 1464) += v8;
  *(_QWORD *)(v5 + 1456) += v49;
  _Mtx_unlock((_Mtx_t)(v5 + 1256));
  if ( *v12 )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v12 + 168LL))(*v12, 0);
  }
  else if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_180463150, 0, 0) )
  {
    ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v15 = *(_BYTE *)(Microsoft::Diagnostics::ScenarioManager::GetScenarioStateMapEntry(ScenarioManager, v54, v13) + 4)
        & 1;
  }
  else
  {
    v15 = 0;
  }
  v10 = (v10 - inserted) >> 4;
  *(_QWORD *)v54 = v10;
  if ( v15 )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)(v5 + 328));
    v38 = *(_QWORD *)(v5 + 536);
    v39 = v38 + v8;
    v40 = -1;
    if ( v38 + v8 < v38 )
      v39 = -1;
    *(_QWORD *)(v5 + 536) = v39;
    v41 = *(_QWORD *)(v5 + 408);
    v42 = v41 + v8;
    if ( v41 + v8 < v41 )
      v42 = -1;
    v43 = *(_QWORD *)(v5 + 528);
    v44 = v49;
    v45 = v43 + v49;
    if ( v43 + v49 < v43 )
      v45 = -1;
    *(_QWORD *)(v5 + 528) = v45;
    if ( v42 + v44 >= v42 )
      v40 = v42 + v44;
    *(_QWORD *)(v5 + 408) = v40;
    Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters::ReportCandidateTrigger(
      (Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters *)(v5 + 408),
      (const struct Microsoft::Diagnostics::ITriggerInst *)CycleTime,
      v10);
    _Mtx_unlock((_Mtx_t)(v5 + 328));
  }
  v14 = v5 + 200;
  *(_QWORD *)&v53 = v5 + 200;
  if ( _Mtx_lock((_Mtx_t)(v5 + 200)) )
  {
LABEL_65:
    std::_Throw_Cpp_error(5);
    JUMPOUT(0x180053D26LL);
  }
  if ( *(_DWORD *)(v5 + 276) == 0x7FFFFFFF )
    goto LABEL_62;
  v10 = v5 + 312;
  v16 = *(_QWORD *)(v5 + 312);
  v17 = *(_QWORD *)(v16 + 8);
  v48 = (unsigned __int64)v17;
  inserted = v16;
  if ( !*(_BYTE *)(v17 + 25) )
  {
    do
    {
      *(_QWORD *)&v48 = v17;
      if ( memcmp_0((const void *)(v17 + 32), Buf2, 0x10u) >= 0 )
      {
        DWORD2(v48) = 1;
        inserted = v17;
      }
      else
      {
        DWORD2(v48) = 0;
        v17 += 16;
      }
      v17 = *(_QWORD *)v17;
    }
    while ( !*(_BYTE *)(v17 + 25) );
    v14 = v5 + 200;
  }
  if ( *(_BYTE *)(inserted + 25) || memcmp_0(Buf2, (const void *)(inserted + 32), 0x10u) < 0 )
  {
    if ( *(_QWORD *)(v5 + 320) == 0x1FFFFFFFFFFFFFFLL )
      goto LABEL_64;
    *(_QWORD *)&v52 = Buf2;
    v18 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>(
            &v50,
            v5 + 312,
            v16);
    v19 = v18[1];
    v18[1] = 0;
    if ( v51 )
      std::_Deallocate<16>(v51, (struct std::nothrow_t *)0x80);
    v52 = v48;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>>>::_Insert_node(
                 v5 + 312,
                 &v52,
                 v19);
  }
  LODWORD(v13) = v54[0];
  v20 = 1;
  v21 = CycleTime;
  if ( v54[0] <= 1 || (*(_BYTE *)(CycleTime + 697) & 0x10) != 0 )
  {
    v22 = 0;
    v23 = 68;
  }
  else
  {
    v22 = 1;
    v23 = 72;
  }
  v24 = (int *)(v23 + inserted);
  v25 = *(_DWORD *)(v23 + inserted);
  v26 = v25 + 1;
  if ( v25 + 1 < v25 )
    goto LABEL_63;
LABEL_27:
  *v24 = v26;
  v27 = FLOAT_1_0;
  if ( v22 )
    v27 = 1.0 / (float)(int)v13;
  *(float *)(inserted + 76) = v27 + *(float *)(inserted + 76);
  if ( (*(_BYTE *)(v21 + 696) & 8) != 0 )
    *(_WORD *)(inserted + 88) += v20;
  v28 = *(_QWORD *)v10;
  v29 = *(_QWORD *)(*(_QWORD *)v10 + 8LL);
  v48 = (unsigned __int64)v29;
  if ( !*(_BYTE *)(v29 + 25) )
  {
    do
    {
      *(_QWORD *)&v48 = v29;
      if ( memcmp_0((const void *)(v29 + 32), Buf2, 0x10u) >= 0 )
      {
        DWORD2(v48) = 1;
        v28 = v29;
      }
      else
      {
        DWORD2(v48) = 0;
        v29 += 16;
      }
      v29 = *(_QWORD *)v29;
    }
    while ( !*(_BYTE *)(v29 + 25) );
    v14 = v5 + 200;
    v10 = v5 + 312;
  }
  if ( *(_BYTE *)(v28 + 25) || memcmp_0(Buf2, (const void *)(v28 + 32), 0x10u) < 0 )
  {
    if ( *(_QWORD *)(v10 + 8) != 0x1FFFFFFFFFFFFFFLL )
    {
      *(_QWORD *)v54 = Buf2;
      v30 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>(
              &v50,
              v10,
              *(_QWORD *)v10);
      v31 = v30[1];
      v30[1] = 0;
      if ( v51 )
        std::_Deallocate<16>(v51, (struct std::nothrow_t *)0x80);
      v53 = v48;
      v28 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>>>::_Insert_node(
              v10,
              &v53,
              v31);
      goto LABEL_42;
    }
LABEL_64:
    std::_Xlength_error("map/set too long");
  }
LABEL_42:
  v32 = v49;
  *(_QWORD *)(v28 + 48) += v49 + v8;
  _Mtx_unlock((_Mtx_t)v14);
  result = std::_Atomic_storage<bool,1>::load(v5 + 576, 5, v33);
  if ( (_BYTE)result )
  {
    *(_QWORD *)&v53 = v5 + 848;
    std::_Mutex_base::lock((std::_Mutex_base *)(v5 + 848));
    v36 = std::map<_GUID,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters>>>::_Try_emplace<_GUID const &,>(
            v5 + 952,
            &v50,
            Buf2);
    Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters::ReportCandidateTrigger(
      (Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters *)(*(_QWORD *)v36 + 48LL),
      (const struct Microsoft::Diagnostics::ITriggerInst *)CycleTime,
      (unsigned int)v13);
    v37 = std::map<_GUID,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters>>>::_Try_emplace<_GUID const &,>(
            v5 + 952,
            &v50,
            Buf2);
    *(_QWORD *)(*(_QWORD *)v37 + 48LL) += v32 + v8;
    return _Mtx_unlock((_Mtx_t)(v5 + 848));
  }
  return result;
}

```

## disassembly

```asm
0x180053774  push    rbp
0x180053776  push    rbx
0x180053777  push    rsi
0x180053778  push    rdi
0x180053779  push    r12
0x18005377b  push    r13
0x18005377d  push    r14
0x18005377f  push    r15
0x180053781  lea     rbp, [rsp-1Fh]
0x180053786  sub     rsp, 0A8h
0x18005378d  mov     rax, cs:__security_cookie
0x180053794  xor     rax, rsp
0x180053797  mov     [rbp+57h+var_48], rax
0x18005379b  mov     rbx, rcx
0x18005379e  xor     edx, edx
0x1800537a0  xor     eax, eax
0x1800537a2  lock cmpxchg qword ptr cs:xmmword_1804631F0+8, rdx
0x1800537ab  setz    al
0x1800537ae  mov     rcx, [rbp+5Fh]; this
0x1800537b2  test    al, al
0x1800537b4  jnz     loc_180053BBB
0x1800537ba  mov     r14, qword ptr cs:xmmword_1804631F0+8
0x1800537c1  mov     rax, [rbx+28h]
0x1800537c5  mov     rax, [rax]
0x1800537c8  mov     [rbp+57h+var_88], rax
0x1800537cc  call    cs:__imp_GetCurrentThread
0x1800537d2  mov     [rbp+57h+CycleTime], 0
0x1800537da  lea     rdx, [rbp+57h+CycleTime]; CycleTime
0x1800537de  mov     rcx, rax; ThreadHandle
0x1800537e1  call    cs:__imp_QueryThreadCycleTime
0x1800537e7  mov     rcx, [rbp+57h+CycleTime]
0x1800537eb  mov     rdx, [rbx+20h]
0x1800537ef  cmp     qword ptr [rdx], 0
0x1800537f3  jz      loc_180053BCD
0x1800537f9  test    rcx, rcx
0x1800537fc  jz      loc_180053BCD
0x180053802  mov     rax, rcx
0x180053805  sub     rax, [rdx]
0x180053808  cmp     [rdx], rcx
0x18005380b  sbb     r12, r12
0x18005380e  and     r12, rax
0x180053811  mov     [rdx], rcx
0x180053814  mov     rax, [rbx+18h]
0x180053818  mov     r15, [rax+8]
0x18005381c  mov     rsi, [rax]
0x18005381f  mov     rax, [rbx+10h]
0x180053823  mov     rax, [rax]
0x180053826  mov     [rbp+57h+CycleTime], rax
0x18005382a  mov     rdi, [rbx+8]
0x18005382e  mov     r13, [rbx]
0x180053831  mov     [rbp+57h+Buf2], r13
0x180053835  lea     rbx, [r14+4E8h]
0x18005383c  mov     rcx, rbx; _Mtx_t
0x18005383f  call    cs:__imp__Mtx_lock
0x180053845  test    eax, eax
0x180053847  jnz     loc_180053D1B
0x18005384d  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180053854  jz      loc_180053CF2
0x18005385a  add     [r14+5B8h], r12
0x180053861  mov     rax, [rbp+57h+var_88]
0x180053865  add     [r14+5B0h], rax
0x18005386c  mov     rcx, rbx; _Mtx_t
0x18005386f  call    cs:__imp__Mtx_unlock
0x180053875  mov     rcx, [rdi]
0x180053878  test    rcx, rcx
0x18005387b  jz      loc_180053B89
0x180053881  xor     edx, edx
0x180053883  mov     rax, [rcx]
0x180053886  mov     rax, [rax+0A8h]
0x18005388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053892  sub     r15, rsi
0x180053895  sar     r15, 4
0x180053899  mov     qword ptr [rbp+57h+var_50], r15
0x18005389d  test    al, al
0x18005389f  jnz     loc_180053C61
0x1800538a5  lea     rbx, [r14+0C8h]
0x1800538ac  mov     qword ptr [rbp+57h+var_60], rbx
0x1800538b0  mov     rcx, rbx; _Mtx_t
0x1800538b3  call    cs:__imp__Mtx_lock
0x1800538b9  test    eax, eax
0x1800538bb  jnz     loc_180053D1B
0x1800538c1  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800538c8  jz      loc_180053CF2
0x1800538ce  lea     r15, [r14+138h]
0x1800538d5  mov     r13, [r15]
0x1800538d8  mov     rdi, [r13+8]
0x1800538dc  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800538e0  mov     qword ptr [rbp+57h+var_A0+8], 0
0x1800538e8  mov     rsi, r13
0x1800538eb  cmp     [rdi+19h], al
0x1800538ee  jnz     short loc_18005392D
0x1800538f0  mov     rbx, [rbp+57h+Buf2]
0x1800538f4  mov     qword ptr [rbp+57h+var_A0], rdi
0x1800538f8  lea     rcx, [rdi+20h]; Buf1
0x1800538fc  mov     r8d, 10h; Size
0x180053902  mov     rdx, rbx; Buf2
0x180053905  call    memcmp_0
0x18005390a  test    eax, eax
0x18005390c  jns     loc_180053B5E
0x180053912  mov     dword ptr [rbp+57h+var_A0+8], 0
0x180053919  add     rdi, 10h
0x18005391d  mov     rdi, [rdi]
0x180053920  cmp     byte ptr [rdi+19h], 0
0x180053924  jz      short loc_1800538F4
0x180053926  lea     rbx, [r14+0C8h]
0x18005392d  mov     rax, 1FFFFFFFFFFFFFFh
0x180053937  mov     rdi, [rbp+57h+Buf2]
0x18005393b  cmp     byte ptr [rsi+19h], 0
0x18005393f  jnz     short loc_180053961
0x180053941  lea     rdx, [rsi+20h]; Buf2
0x180053945  mov     r8d, 10h; Size
0x18005394b  mov     rcx, rdi; Buf1
0x18005394e  call    memcmp_0
0x180053953  test    eax, eax
0x180053955  jns     short loc_1800539BB
0x180053957  mov     rax, 1FFFFFFFFFFFFFFh
0x180053961  cmp     [r15+8], rax
0x180053965  jz      loc_180053D0D
0x18005396b  mov     qword ptr [rbp+57h+var_70], rdi
0x18005396f  lea     rax, [rbp+57h+var_70]
0x180053973  mov     [rsp+0E0h+var_C0], rax
0x180053978  mov     r8, r13
0x18005397b  mov     rdx, r15
0x18005397e  lea     rcx, [rbp+57h+var_80]
0x180053982  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBU_GUID@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBU_GUID@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>> &,std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *> *,std::piecewise_construct_t const &,std::tuple<_GUID const &> &&,std::tuple<> &&)
0x180053987  mov     rdi, [rax+8]
0x18005398b  mov     qword ptr [rax+8], 0
0x180053993  mov     rcx, [rbp+57h+var_78]
0x180053997  test    rcx, rcx
0x18005399a  jnz     loc_180053C43
0x1800539a0  movups  xmm0, [rbp+57h+var_A0]
0x1800539a4  movdqu  [rbp+57h+var_70], xmm0
0x1800539a9  mov     r8, rdi
0x1800539ac  lea     rdx, [rbp+57h+var_70]
0x1800539b0  mov     rcx, r15
0x1800539b3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>,void *> * const)
0x1800539b8  mov     rsi, rax
0x1800539bb  mov     r13, qword ptr [rbp+57h+var_50]
0x1800539bf  mov     r10d, 1
0x1800539c5  mov     r9, [rbp+57h+CycleTime]
0x1800539c9  cmp     r13d, r10d
0x1800539cc  jbe     loc_180053B7C
0x1800539d2  test    byte ptr [r9+2B9h], 10h
0x1800539da  jnz     loc_180053B7C
0x1800539e0  mov     r8b, r10b
0x1800539e3  lea     eax, [r10+47h]
0x1800539e7  lea     rcx, [rax+rsi]
0x1800539eb  mov     eax, [rcx]
0x1800539ed  lea     edx, [rax+1]
0x1800539f0  cmp     edx, eax
0x1800539f2  jb      loc_180053D05
0x1800539f8  mov     [rcx], edx
0x1800539fa  movss   xmm1, cs:__real@3f800000
0x180053a02  test    r8b, r8b
0x180053a05  jz      short loc_180053A16
0x180053a07  mov     eax, r13d
0x180053a0a  xorps   xmm0, xmm0
0x180053a0d  cvtsi2ss xmm0, rax
0x180053a12  divss   xmm1, xmm0
0x180053a16  addss   xmm1, dword ptr [rsi+4Ch]
0x180053a1b  movss   dword ptr [rsi+4Ch], xmm1
0x180053a20  test    byte ptr [r9+2B8h], 8
0x180053a28  jz      short loc_180053A2F
0x180053a2a  add     [rsi+58h], r10w
0x180053a2f  mov     rsi, [r15]
0x180053a32  mov     rdi, [rsi+8]
0x180053a36  mov     qword ptr [rbp+57h+var_A0], rdi
0x180053a3a  mov     qword ptr [rbp+57h+var_A0+8], 0
0x180053a42  cmp     byte ptr [rdi+19h], 0
0x180053a46  jnz     short loc_180053A8C
0x180053a48  mov     rbx, [rbp+57h+Buf2]
0x180053a4c  mov     qword ptr [rbp+57h+var_A0], rdi
0x180053a50  lea     rcx, [rdi+20h]; Buf1
0x180053a54  mov     r8d, 10h; Size
0x180053a5a  mov     rdx, rbx; Buf2
0x180053a5d  call    memcmp_0
0x180053a62  test    eax, eax
0x180053a64  jns     loc_180053B6D
0x180053a6a  mov     dword ptr [rbp+57h+var_A0+8], 0
0x180053a71  add     rdi, 10h
0x180053a75  mov     rdi, [rdi]
0x180053a78  cmp     byte ptr [rdi+19h], 0
0x180053a7c  jz      short loc_180053A4C
0x180053a7e  lea     rbx, [r14+0C8h]
0x180053a85  lea     r15, [r14+138h]
0x180053a8c  mov     rdi, [rbp+57h+Buf2]
0x180053a90  cmp     byte ptr [rsi+19h], 0
0x180053a94  jnz     short loc_180053AAC
0x180053a96  lea     rdx, [rsi+20h]; Buf2
0x180053a9a  mov     r8d, 10h; Size
0x180053aa0  mov     rcx, rdi; Buf1
0x180053aa3  call    memcmp_0
0x180053aa8  test    eax, eax
0x180053aaa  jns     short loc_180053B10
0x180053aac  mov     rax, 1FFFFFFFFFFFFFFh
0x180053ab6  cmp     [r15+8], rax
0x180053aba  jz      loc_180053D0D
0x180053ac0  mov     qword ptr [rbp+57h+var_50], rdi
0x180053ac4  lea     rax, [rbp+57h+var_50]
0x180053ac8  mov     [rsp+0E0h+var_C0], rax
0x180053acd  mov     r8, [r15]
0x180053ad0  mov     rdx, r15
0x180053ad3  lea     rcx, [rbp+57h+var_80]
0x180053ad7  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBU_GUID@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBU_GUID@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *>> &,std::_Tree_node<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters>,void *> *,std::piecewise_construct_t const &,std::tuple<_GUID const &> &&,std::tuple<> &&)
0x180053adc  mov     rdi, [rax+8]
0x180053ae0  mov     qword ptr [rax+8], 0
0x180053ae8  mov     rcx, [rbp+57h+var_78]
0x180053aec  test    rcx, rcx
0x180053aef  jnz     loc_180053C52
0x180053af5  movups  xmm0, [rbp+57h+var_A0]
0x180053af9  movdqu  [rbp+57h+var_60], xmm0
0x180053afe  mov     r8, rdi
0x180053b01  lea     rdx, [rbp+57h+var_60]
0x180053b05  mov     rcx, r15
0x180053b08  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$array@V?$array@UUserIdentityCacheEntry@Diagnostics@Microsoft@@$03@std@@$02@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>,void *> *>,std::_Tree_node<std::pair<std::wstring const,std::array<std::array<Microsoft::Diagnostics::UserIdentityCacheEntry,4>,3>>,void *> * const)
0x180053b0d  mov     rsi, rax
0x180053b10  mov     r15, [rbp+57h+var_88]
0x180053b14  lea     rcx, [r15+r12]
0x180053b18  add     [rsi+30h], rcx
0x180053b1c  mov     rcx, rbx; _Mtx_t
0x180053b1f  call    cs:__imp__Mtx_unlock
0x180053b25  lea     rcx, [r14+240h]
0x180053b2c  mov     edx, 5
0x180053b31  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180053b36  test    al, al
0x180053b38  jnz     loc_180053BDC
0x180053b3e  mov     rcx, [rbp+57h+var_48]
0x180053b42  xor     rcx, rsp; StackCookie
0x180053b45  call    __security_check_cookie
0x180053b4a  add     rsp, 0A8h
0x180053b51  pop     r15
0x180053b53  pop     r14
0x180053b55  pop     r13
0x180053b57  pop     r12
0x180053b59  pop     rdi
0x180053b5a  pop     rsi
0x180053b5b  pop     rbx
0x180053b5c  pop     rbp
0x180053b5d  retn
0x180053b5e  mov     dword ptr [rbp+57h+var_A0+8], 1
0x180053b65  mov     rsi, rdi
0x180053b68  jmp     loc_18005391D
0x180053b6d  mov     dword ptr [rbp+57h+var_A0+8], 1
0x180053b74  mov     rsi, rdi
0x180053b77  jmp     loc_180053A75
0x180053b7c  xor     r8b, r8b
0x180053b7f  mov     eax, 44h ; 'D'
0x180053b84  jmp     loc_1800539E7
0x180053b89  xor     eax, eax
0x180053b8b  lock cmpxchg qword ptr cs:xmmword_180463150, rcx
0x180053b94  jz      short loc_180053BD5
0x180053b96  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180053b9d  call    ?GetScenarioManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVScenarioManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetScenarioManager(void)
0x180053ba2  mov     r8, r13
0x180053ba5  lea     rdx, [rbp+57h+var_50]
0x180053ba9  mov     rcx, rax
0x180053bac  call    ?GetScenarioStateMapEntry@ScenarioManager@Diagnostics@Microsoft@@QEBA?AUScenarioStateMapEntry@23@AEBU_GUID@@@Z; Microsoft::Diagnostics::ScenarioManager::GetScenarioStateMapEntry(_GUID const &)
0x180053bb1  mov     al, [rax+4]
0x180053bb4  and     al, 1
0x180053bb6  jmp     loc_180053892
0x180053bbb  lea     r8, aOnecoreBaseTel_20; "onecore\\base\\telemetry\\utc\\service"...
0x180053bc2  mov     edx, 6Eh ; 'n'; void *
0x180053bc7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180053bcd  xor     r12d, r12d
0x180053bd0  jmp     loc_180053811
0x180053bd5  xor     al, al
0x180053bd7  jmp     loc_180053892
0x180053bdc  lea     rdi, [r14+350h]
0x180053be3  mov     qword ptr [rbp+57h+var_60], rdi
0x180053be7  mov     rcx, rdi; this
0x180053bea  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180053bef  nop
0x180053bf0  lea     rbx, [r14+3B8h]
0x180053bf7  mov     r8, [rbp+57h+Buf2]
0x180053bfb  lea     rdx, [rbp+57h+var_80]
0x180053bff  mov     rcx, rbx
0x180053c02  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180053c07  mov     rcx, [rax]
0x180053c0a  add     rcx, 30h ; '0'; this
0x180053c0e  mov     r8d, r13d; unsigned int
0x180053c11  mov     rdx, [rbp+57h+CycleTime]; struct Microsoft::Diagnostics::ITriggerInst *
0x180053c15  call    ?ReportCandidateTrigger@StateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@QEAAXAEBVITriggerInst@34@K@Z; Microsoft::Diagnostics::UsageAnalyzer::StateModelCounters::ReportCandidateTrigger(Microsoft::Diagnostics::ITriggerInst const &,ulong)
0x180053c1a  mov     r8, [rbp+57h+Buf2]
0x180053c1e  lea     rdx, [rbp+57h+var_80]
0x180053c22  mov     rcx, rbx
0x180053c25  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@ULessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UReportStateModelCounters@UsageAnalyzer@Diagnostics@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters,LessGuid,std::allocator<std::pair<_GUID const,Microsoft::Diagnostics::UsageAnalyzer::ReportStateModelCounters>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180053c2a  mov     rdx, [rax]
0x180053c2d  lea     rax, [r15+r12]
0x180053c31  add     [rdx+30h], rax
0x180053c35  mov     rcx, rdi; _Mtx_t
0x180053c38  call    cs:__imp__Mtx_unlock
0x180053c3e  jmp     loc_180053B3E
0x180053c43  mov     edx, 80h
0x180053c48  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180053c4d  jmp     loc_1800539A0
0x180053c52  mov     edx, 80h
0x180053c57  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180053c5c  jmp     loc_180053AF5
0x180053c61  lea     rbx, [r14+148h]
0x180053c68  mov     rcx, rbx; this
  ... truncated ...
```
