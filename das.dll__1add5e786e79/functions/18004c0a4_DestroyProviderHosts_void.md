# DestroyProviderHosts(void)

- ea: `0x18004c0a4`
- end: `0x18004c1fe`
- name: `?DestroyProviderHosts@@YAXXZ`
- size: `346`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180049350`

## callees

- `0x1800153e0`
- `0x18001da90`
- `0x18004c0a4`
- `0x18004c7d8`
- `0x18007d850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c0e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c0e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c0d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c0d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c0f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c0f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c122`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c122`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c1ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c1d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c1d0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004c174`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004c174`

## pseudocode

```c
void DestroyProviderHosts(void)
{
  __int64 *v0; // rbx
  CHostContext *v1; // rcx
  int v2; // edx
  int v3; // r8d
  DWORD v4; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  Handles[0] = g_hHostsExitedEvent;
  Handles[1] = *(HANDLE *)g_providerManager;
  AcquireSRWLockExclusive(&g_srwDevnodeSubsystemStoping);
  g_bDevnodeSubsystemStoping = 1;
  ReleaseSRWLockExclusive(&g_srwDevnodeSubsystemStoping);
  EnterCriticalSection(&HostList);
  v0 = (__int64 *)qword_1800A4618;
  while ( v0 != &qword_1800A4618 )
  {
    v1 = (CHostContext *)(v0 - 3);
    v0 = (__int64 *)*v0;
    CHostContext::ShutdownProcess(v1);
  }
  LeaveCriticalSection(&HostList);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v2,
      v3,
      10,
      &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
      g_cHosts[0]);
  v4 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v4 )
  {
    if ( v4 == 1 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v7 = 12;
        goto LABEL_14;
      }
    }
    else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v7 = 13;
LABEL_14:
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v5,
        v6,
        v7,
        &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids);
    }
  }
  else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v7 = 11;
    goto LABEL_14;
  }
  CloseHandle(g_hHostsExitedEvent);
  g_hHostsExitedEvent = 0;
  pSetupUninitializeUtils();
  DeleteCriticalSection(&HostList);
}

```

## disassembly

```asm
0x18004c0a4  mov     [rsp+arg_0], rbx
0x18004c0a9  push    rdi
0x18004c0aa  sub     rsp, 40h
0x18004c0ae  mov     rax, cs:?g_hHostsExitedEvent@@3PEAXEA; void * g_hHostsExitedEvent
0x18004c0b5  mov     [rsp+48h+Handles], rax
0x18004c0ba  mov     rax, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18004c0c1  mov     rcx, [rax]
0x18004c0c4  mov     [rsp+48h+var_10], rcx
0x18004c0c9  lea     rcx, ?g_srwDevnodeSubsystemStoping@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004c0d0  call    cs:__imp_AcquireSRWLockExclusive
0x18004c0d6  lea     rcx, ?g_srwDevnodeSubsystemStoping@@3U_RTL_SRWLOCK@@A; SRWLock
0x18004c0dd  mov     cs:?g_bDevnodeSubsystemStoping@@3HA, 1; int g_bDevnodeSubsystemStoping
0x18004c0e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c0ed  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004c0f4  call    cs:__imp_EnterCriticalSection
0x18004c0fa  mov     rbx, cs:qword_1800A4618
0x18004c101  lea     rdi, qword_1800A4618
0x18004c108  jmp     short loc_18004C116
0x18004c10a  lea     rcx, [rbx-18h]; this
0x18004c10e  mov     rbx, [rbx]
0x18004c111  call    ?ShutdownProcess@CHostContext@@IEAAXXZ; CHostContext::ShutdownProcess(void)
0x18004c116  cmp     rbx, rdi
0x18004c119  jnz     short loc_18004C10A
0x18004c11b  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004c122  call    cs:__imp_LeaveCriticalSection
0x18004c128  lea     rbx, WPP_RECORDER_INITIALIZED
0x18004c12f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18004c136  lea     rdi, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x18004c13d  jz      short loc_18004C164
0x18004c13f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c146  mov     r9d, 0Ah; int
0x18004c14c  mov     eax, cs:?g_cHosts@@3KA; ulong g_cHosts
0x18004c152  mov     dword ptr [rsp+48h+var_20], eax; char
0x18004c156  mov     [rsp+48h+MessageGuid], rdi; MessageGuid
0x18004c15b  mov     rcx, [rcx+28h]; int
0x18004c15f  call    WPP_RECORDER_SF_d
0x18004c164  xor     r8d, r8d; bWaitAll
0x18004c167  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18004c16c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004c170  lea     ecx, [r8+2]; nCount
0x18004c174  call    cs:__imp_WaitForMultipleObjects
0x18004c17a  test    eax, eax
0x18004c17c  jz      short loc_18004C1A5
0x18004c17e  cmp     eax, 1
0x18004c181  jz      short loc_18004C194
0x18004c183  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18004c18a  jz      short loc_18004C1C9
0x18004c18c  mov     r9d, 0Dh
0x18004c192  jmp     short loc_18004C1B4
0x18004c194  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18004c19b  jz      short loc_18004C1C9
0x18004c19d  mov     r9d, 0Ch
0x18004c1a3  jmp     short loc_18004C1B4
0x18004c1a5  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18004c1ac  jz      short loc_18004C1C9
0x18004c1ae  mov     r9d, 0Bh; int
0x18004c1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1bb  mov     [rsp+48h+MessageGuid], rdi; MessageGuid
0x18004c1c0  mov     rcx, [rcx+28h]; int
0x18004c1c4  call    WPP_RECORDER_SF_
0x18004c1c9  mov     rcx, cs:?g_hHostsExitedEvent@@3PEAXEA; hObject
0x18004c1d0  call    cs:__imp_CloseHandle
0x18004c1d6  mov     cs:?g_hHostsExitedEvent@@3PEAXEA, 0; void * g_hHostsExitedEvent
0x18004c1e1  call    pSetupUninitializeUtils
0x18004c1e6  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x18004c1ed  call    cs:__imp_DeleteCriticalSection
0x18004c1f3  mov     rbx, [rsp+48h+arg_0]
0x18004c1f8  add     rsp, 40h
0x18004c1fc  pop     rdi
0x18004c1fd  retn
```
