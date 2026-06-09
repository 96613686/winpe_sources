# CCorSvcMgr::CCorSvcMgr(void)

- ea: `0x18001d274`
- end: `0x18001d596`
- name: `??0CCorSvcMgr@@QEAA@XZ`
- size: `802`
- prototype: `CCorSvcMgr *__fastcall(CCorSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180008680`

## callees

- `0x18001d274`
- `0x18002d9f0`
- `0x1800304ec`
- `0x1800351e8`
- `0x1800366a8`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x18001d575`
- `KERNEL32!SetErrorMode` at `0x18001d575`
- `KERNEL32!InitializeCriticalSection` at `0x18001d479`
- `KERNEL32!InitializeCriticalSection` at `0x18001d479`
- `KERNEL32!CloseHandle` at `0x18001d4ba`
- `KERNEL32!CloseHandle` at `0x18001d4ba`
- `KERNEL32!CreateEventW` at `0x18001d428`
- `KERNEL32!CreateEventW` at `0x18001d428`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d4d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d4d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
CCorSvcMgr *__fastcall CCorSvcMgr::CCorSvcMgr(CCorSvcMgr *this)
{
  char *v2; // rdi
  char *v3; // rax
  char *v4; // rax
  BSTR *v5; // rsi
  char *v6; // rax
  __int64 v7; // rcx
  HANDLE EventW; // rax
  HANDLE *v9; // rdi
  bool v10; // dl
  bool v11; // dl
  bool v12; // dl
  unsigned int ConfigValue; // eax
  int v14; // eax
  char *v16; // [rsp+78h] [rbp+38h] BYREF
  char *v17; // [rsp+80h] [rbp+40h] BYREF
  char *v18; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)this = &CCorSvcMgr::`vftable'{for `ICorSvcInstaller'};
  *((_QWORD *)this + 1) = &CCorSvcMgr::`vftable'{for `ICorSvcAdvancedInstaller'};
  *((_QWORD *)this + 2) = &CCorSvcMgr::`vftable'{for `ICorSvcOptimizer3'};
  *((_QWORD *)this + 3) = &CCorSvcMgr::`vftable'{for `ICorSvcLogger'};
  *((_QWORD *)this + 4) = &CCorSvcMgr::`vftable'{for `ICorSvcRepository'};
  *((_QWORD *)this + 5) = &CCorSvcMgr::`vftable'{for `ICorSvcSetPrivateAttributes'};
  *((_QWORD *)this + 6) = &CCorSvcMgr::`vftable'{for `ICorSvcManager'};
  *((_QWORD *)this + 7) = &CCorSvcMgr::`vftable'{for `ICorSvcManager2'};
  *((_QWORD *)this + 8) = &CCorSvcMgr::`vftable'{for `ICorSvcSetLegacyServiceBehavior'};
  *((_QWORD *)this + 9) = &CCorSvcMgr::`vftable'{for `ICorSvcSetTaskBootTriggerState'};
  *((_QWORD *)this + 10) = &CCorSvcMgr::`vftable'{for `ICorSvcSetTaskDelayStartTriggerState'};
  v2 = (char *)this + 104;
  v16 = (char *)this + 104;
  v17 = (char *)this + 104;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 15) = 0;
  v3 = (char *)operator new(0x18u);
  v18 = v3;
  if ( v3 )
  {
    *(_QWORD *)v3 = 0;
    *((_DWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 2) = 0;
  }
  else
  {
    v3 = 0;
  }
  *((_QWORD *)v2 + 3) = v3;
  v4 = (char *)operator new(0x18u);
  v17 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = 0;
    *((_DWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 2) = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)v2 + 4) = v4;
  *((_DWORD *)v2 + 10) = 0;
  *((_QWORD *)this + 26) = 0;
  v16 = (char *)this + 224;
  v17 = (char *)this + 224;
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 30) = 0;
  v5 = (BSTR *)((char *)this + 248);
  v18 = (char *)this + 248;
  *((_QWORD *)this + 31) = 0;
  *((_DWORD *)this + 64) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  v6 = (char *)this + 360;
  v7 = 16;
  do
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 5) = 0;
    *((_DWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 3) = 0;
    v6 += 56;
    --v7;
  }
  while ( v7 );
  *((_DWORD *)this + 88) = ThreadPool::ComputeNumWorkers();
  *((_DWORD *)this + 89) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 157) = EventW;
  if ( !EventW )
    ThrowLastError();
  v9 = (HANDLE *)((char *)this + 1296);
  v16 = (char *)this + 1296;
  *((_QWORD *)this + 162) = -1;
  *((_DWORD *)this + 326) = 0;
  v17 = (char *)this + 1320;
  v18 = (char *)this + 1320;
  *((_QWORD *)this + 165) = 0;
  *((_DWORD *)this + 332) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_DWORD *)this + 22) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 158) = 0;
  *(_QWORD *)((char *)this + 1284) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 72) = 32;
  *((_DWORD *)this + 323) = 0;
  if ( *((_DWORD *)this + 326) )
  {
    if ( *v9 )
      CloseHandle(*v9);
    *((_DWORD *)this + 326) = 0;
  }
  *v9 = (HANDLE)-1LL;
  if ( *((_DWORD *)this + 64) )
  {
    SysFreeString(*v5);
    *((_DWORD *)this + 64) = 0;
  }
  *v5 = 0;
  *((_DWORD *)this + 66) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_DWORD *)this + 319) = CLRConfig::GetConfigValue(
                              (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_EnableMultiproc,
                              v10,
                              (bool *)&v16) != 0;
  *((_DWORD *)this + 320) = CLRConfig::GetConfigValue(
                              (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_SvcRetryNgenFailures,
                              v11,
                              (bool *)&v17) == 1;
  ConfigValue = CLRConfig::GetConfigValue(
                  (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGenLocalWorker,
                  v12,
                  (bool *)&v18);
  *((_DWORD *)this + 318) = ConfigValue != 0;
  if ( ConfigValue || (v14 = 1, !*((_DWORD *)this + 319)) )
    v14 = 0;
  *((_DWORD *)this + 319) = v14;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 328) = 3;
  SetErrorMode(1u);
  _InterlockedIncrement(&CCorSvcMgr::corSvcMgrCount);
  return this;
}

```

## disassembly

```asm
0x18001d274  mov     [rsp-28h+arg_0], rcx
0x18001d279  push    rbp
0x18001d27a  push    rbx
0x18001d27b  push    rsi
0x18001d27c  push    rdi
0x18001d27d  push    r14
0x18001d27f  mov     rbp, rsp
0x18001d282  sub     rsp, 40h
0x18001d286  mov     rbx, rcx
0x18001d289  lea     rax, ??_7CCorSvcMgr@@6BICorSvcInstaller@@@; const CCorSvcMgr::`vftable'{for `ICorSvcInstaller'}
0x18001d290  mov     [rcx], rax
0x18001d293  lea     rax, ??_7CCorSvcMgr@@6BICorSvcAdvancedInstaller@@@; const CCorSvcMgr::`vftable'{for `ICorSvcAdvancedInstaller'}
0x18001d29a  mov     [rcx+8], rax
0x18001d29e  lea     rax, ??_7CCorSvcMgr@@6BICorSvcOptimizer3@@@; const CCorSvcMgr::`vftable'{for `ICorSvcOptimizer3'}
0x18001d2a5  mov     [rcx+10h], rax
0x18001d2a9  lea     rax, ??_7CCorSvcMgr@@6BICorSvcLogger@@@; const CCorSvcMgr::`vftable'{for `ICorSvcLogger'}
0x18001d2b0  mov     [rcx+18h], rax
0x18001d2b4  lea     rax, ??_7CCorSvcMgr@@6BICorSvcRepository@@@; const CCorSvcMgr::`vftable'{for `ICorSvcRepository'}
0x18001d2bb  mov     [rcx+20h], rax
0x18001d2bf  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetPrivateAttributes@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetPrivateAttributes'}
0x18001d2c6  mov     [rcx+28h], rax
0x18001d2ca  lea     rax, ??_7CCorSvcMgr@@6BICorSvcManager@@@; const CCorSvcMgr::`vftable'{for `ICorSvcManager'}
0x18001d2d1  mov     [rcx+30h], rax
0x18001d2d5  lea     rax, ??_7CCorSvcMgr@@6BICorSvcManager2@@@; const CCorSvcMgr::`vftable'{for `ICorSvcManager2'}
0x18001d2dc  mov     [rcx+38h], rax
0x18001d2e0  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetLegacyServiceBehavior@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetLegacyServiceBehavior'}
0x18001d2e7  mov     [rcx+40h], rax
0x18001d2eb  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetTaskBootTriggerState@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetTaskBootTriggerState'}
0x18001d2f2  mov     [rcx+48h], rax
0x18001d2f6  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetTaskDelayStartTriggerState@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetTaskDelayStartTriggerState'}
0x18001d2fd  mov     [rcx+50h], rax
0x18001d301  lea     rdi, [rcx+68h]
0x18001d305  mov     [rbp+arg_8], rdi
0x18001d309  mov     [rbp+arg_10], rdi
0x18001d30d  xor     r14d, r14d
0x18001d310  mov     [rdi], r14
0x18001d313  mov     [rdi+8], r14d
0x18001d317  mov     [rdi+10h], r14
0x18001d31b  lea     esi, [r14+18h]
0x18001d31f  mov     ecx, esi; dwBytes
0x18001d321  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d326  mov     [rbp+arg_18], rax
0x18001d32a  test    rax, rax
0x18001d32d  jz      short loc_18001D33C
0x18001d32f  mov     [rax], r14
0x18001d332  mov     [rax+8], r14d
0x18001d336  mov     [rax+10h], r14
0x18001d33a  jmp     short loc_18001D33F
0x18001d33c  mov     rax, r14
0x18001d33f  mov     [rdi+18h], rax
0x18001d343  mov     rcx, rsi; dwBytes
0x18001d346  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d34b  mov     [rbp+arg_10], rax
0x18001d34f  test    rax, rax
0x18001d352  jz      short loc_18001D361
0x18001d354  mov     [rax], r14
0x18001d357  mov     [rax+8], r14d
0x18001d35b  mov     [rax+10h], r14
0x18001d35f  jmp     short loc_18001D364
0x18001d361  mov     rax, r14
0x18001d364  mov     [rdi+20h], rax
0x18001d368  mov     [rdi+28h], r14d
0x18001d36c  mov     [rbx+0D0h], r14
0x18001d373  lea     rax, [rbx+0E0h]
0x18001d37a  mov     [rbp+arg_8], rax
0x18001d37e  mov     [rbp+arg_10], rax
0x18001d382  mov     [rax], r14
0x18001d385  mov     [rax+8], r14d
0x18001d389  mov     [rax+10h], r14
0x18001d38d  lea     rsi, [rbx+0F8h]
0x18001d394  mov     [rbp+arg_18], rsi
0x18001d398  mov     [rsi], r14
0x18001d39b  mov     [rsi+8], r14d
0x18001d39f  mov     [rbx+110h], r14
0x18001d3a6  mov     [rbx+118h], r14
0x18001d3ad  lea     rax, [rbx+128h]
0x18001d3b4  mov     [rbp+var_20], rax
0x18001d3b8  mov     [rax], r14
0x18001d3bb  mov     [rax+8], r14d
0x18001d3bf  lea     rax, [rbx+138h]
0x18001d3c6  mov     [rbp+var_18], rax
0x18001d3ca  mov     [rax], r14
0x18001d3cd  mov     [rax+8], r14d
0x18001d3d1  lea     rax, [rbx+148h]
0x18001d3d8  mov     [rbp+var_10], rax
0x18001d3dc  mov     [rax], r14
0x18001d3df  mov     [rax+8], r14d
0x18001d3e3  lea     rax, [rbx+168h]
0x18001d3ea  mov     ecx, 10h
0x18001d3ef  mov     [rax], r14
0x18001d3f2  mov     [rax+8], r14
0x18001d3f6  mov     [rax+28h], r14
0x18001d3fa  mov     [rax+10h], r14d
0x18001d3fe  mov     [rax+18h], r14
0x18001d402  lea     rax, [rax+38h]
0x18001d406  sub     rcx, 1
0x18001d40a  jnz     short loc_18001D3EF
0x18001d40c  call    ?ComputeNumWorkers@ThreadPool@@CAKXZ; ThreadPool::ComputeNumWorkers(void)
0x18001d411  mov     [rbx+160h], eax
0x18001d417  mov     [rbx+164h], r14d
0x18001d41e  xor     r9d, r9d; lpName
0x18001d421  xor     r8d, r8d; bInitialState
0x18001d424  xor     edx, edx; bManualReset
0x18001d426  xor     ecx, ecx; lpEventAttributes
0x18001d428  call    cs:__imp_CreateEventW
0x18001d42e  mov     [rbx+4E8h], rax
0x18001d435  test    rax, rax
0x18001d438  jz      loc_18001D590
0x18001d43e  lea     rdi, [rbx+510h]
0x18001d445  mov     [rbp+arg_8], rdi
0x18001d449  or      qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001d44d  mov     [rdi+8], r14d
0x18001d451  lea     rax, [rbx+528h]
0x18001d458  mov     [rbp+arg_10], rax
0x18001d45c  mov     [rbp+arg_18], rax
0x18001d460  mov     [rax], r14
0x18001d463  mov     [rax+8], r14d
0x18001d467  mov     [rax+10h], r14
0x18001d46b  mov     dword ptr [rbx+58h], 1
0x18001d472  lea     rcx, [rbx+98h]; lpCriticalSection
0x18001d479  call    cs:__imp_InitializeCriticalSection
0x18001d47f  mov     [rbx+0C0h], r14
0x18001d486  mov     [rbx+4F0h], r14
0x18001d48d  mov     [rbx+504h], r14
0x18001d494  mov     [rbx+0C8h], r14
0x18001d49b  mov     dword ptr [rbx+120h], 20h ; ' '
0x18001d4a5  mov     [rbx+50Ch], r14d
0x18001d4ac  cmp     [rdi+8], r14d
0x18001d4b0  jz      short loc_18001D4C4
0x18001d4b2  mov     rcx, [rdi]; hObject
0x18001d4b5  test    rcx, rcx
0x18001d4b8  jz      short loc_18001D4C0
0x18001d4ba  call    cs:__imp_CloseHandle
0x18001d4c0  mov     [rdi+8], r14d
0x18001d4c4  or      qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001d4c8  cmp     [rsi+8], r14d
0x18001d4cc  jz      short loc_18001D4DB
0x18001d4ce  mov     rcx, [rsi]; bstrString
0x18001d4d1  call    cs:__imp_SysFreeString
0x18001d4d7  mov     [rsi+8], r14d
0x18001d4db  mov     [rsi], r14
0x18001d4de  mov     [rbx+108h], r14d
0x18001d4e5  mov     [rbx+158h], r14b
0x18001d4ec  lea     r8, [rbp+arg_8]; bool *
0x18001d4f0  lea     rcx, ?EXTERNAL_EnableMultiproc@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001d4f7  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001d4fc  mov     ecx, r14d
0x18001d4ff  test    eax, eax
0x18001d501  setnz   cl
0x18001d504  mov     [rbx+4FCh], ecx
0x18001d50a  lea     r8, [rbp+arg_10]; bool *
0x18001d50e  lea     rcx, ?EXTERNAL_SvcRetryNgenFailures@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001d515  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001d51a  mov     ecx, r14d
0x18001d51d  cmp     eax, 1
0x18001d520  setz    cl
0x18001d523  mov     [rbx+500h], ecx
0x18001d529  lea     r8, [rbp+arg_18]; bool *
0x18001d52d  lea     rcx, ?EXTERNAL_NGenLocalWorker@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x18001d534  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x18001d539  mov     ecx, r14d
0x18001d53c  test    eax, eax
0x18001d53e  setnz   cl
0x18001d541  mov     [rbx+4F8h], ecx
0x18001d547  test    eax, eax
0x18001d549  jnz     short loc_18001D559
0x18001d54b  cmp     [rbx+4FCh], r14d
0x18001d552  mov     eax, 1
0x18001d557  jnz     short loc_18001D55C
0x18001d559  mov     eax, r14d
0x18001d55c  mov     [rbx+4FCh], eax
0x18001d562  mov     [rbx+60h], r14
0x18001d566  mov     dword ptr [rbx+520h], 3
0x18001d570  mov     ecx, 1; uMode
0x18001d575  call    cs:__imp_SetErrorMode
0x18001d57b  lock inc cs:?corSvcMgrCount@CCorSvcMgr@@0JA; long CCorSvcMgr::corSvcMgrCount
0x18001d582  mov     rax, rbx
0x18001d585  add     rsp, 40h
0x18001d589  pop     r14
0x18001d58b  pop     rdi
0x18001d58c  pop     rsi
0x18001d58d  pop     rbx
0x18001d58e  pop     rbp
0x18001d58f  retn
0x18001d590  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
```
