# CscService_Finalize(void)

- ea: `0x180055100`
- end: `0x180055242`
- name: `?CscService_Finalize@@YAXXZ`
- size: `322`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180054e64`
- `0x180055a8c`

## callees

- `0x180033c5c`
- `0x180035790`
- `0x180035810`
- `0x18003c460`
- `0x180055100`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800551a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055149`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055170`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005518b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800551e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055204`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055149`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055170`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005518b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800551e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180055204`

## pseudocode

```c
void CscService_Finalize(void)
{
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
  if ( dword_1800B7680 )
  {
    DeleteCriticalSection(&stru_1800B7658);
    dword_1800B7680 = 0;
  }
  CInvSemaphore::_Destroy((CInvSemaphore *)&qword_1800B7410);
  if ( g_bAgentCritSecInitialized )
  {
    DeleteCriticalSection(&g_AgentCritSec);
    g_bAgentCritSecInitialized = 0;
  }
  if ( g_bChgMonCritSectInitialized )
  {
    DeleteCriticalSection(&g_csChgMonCritSect);
    g_bChgMonCritSectInitialized = 0;
  }
  if ( g_hevtStopChgMonitor )
  {
    CloseHandle(g_hevtStopChgMonitor);
    g_hevtStopChgMonitor = 0;
  }
  CPreferenceChgMonitor::_Finalize((CPreferenceChgMonitor *)&g_PreferenceChgMonitor);
  CPolicyChgMonitor::_Finalize((struct _RTL_CRITICAL_SECTION *)&g_PolicyChgMonitor);
  g_bChgMonDirty = 0;
  CInvSemaphore::_Destroy((CInvSemaphore *)&g_invsemThreadControlBlocks);
  if ( g_bEventDispatcherCritSecInitialized )
  {
    DeleteCriticalSection(&g_csEventDispatcherLock);
    g_bEventDispatcherCritSecInitialized = 0;
  }
  if ( dword_1800B6B78 )
  {
    DeleteCriticalSection(&stru_1800B6B50);
    dword_1800B6B78 = 0;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
}

```

## disassembly

```asm
0x180055100  mov     [rsp+arg_0], rbx
0x180055105  push    rdi
0x180055106  sub     rsp, 20h
0x18005510a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055111  lea     rdi, WPP_GLOBAL_Control
0x180055118  cmp     rcx, rdi
0x18005511b  jz      short loc_180055138
0x18005511d  test    byte ptr [rcx+1Ch], 8
0x180055121  jz      short loc_180055138
0x180055123  mov     rcx, [rcx+10h]
0x180055127  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18005512e  mov     edx, 42h ; 'B'
0x180055133  call    WPP_SF_
0x180055138  xor     ebx, ebx
0x18005513a  cmp     cs:dword_1800B7680, ebx
0x180055140  jz      short loc_180055155
0x180055142  lea     rcx, stru_1800B7658; lpCriticalSection
0x180055149  call    cs:__imp_DeleteCriticalSection
0x18005514f  mov     cs:dword_1800B7680, ebx
0x180055155  lea     rcx, qword_1800B7410; this
0x18005515c  call    ?_Destroy@CInvSemaphore@@AEAAXXZ; CInvSemaphore::_Destroy(void)
0x180055161  cmp     cs:?g_bAgentCritSecInitialized@@3HA, ebx; int g_bAgentCritSecInitialized
0x180055167  jz      short loc_18005517C
0x180055169  lea     rcx, ?g_AgentCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180055170  call    cs:__imp_DeleteCriticalSection
0x180055176  mov     cs:?g_bAgentCritSecInitialized@@3HA, ebx; int g_bAgentCritSecInitialized
0x18005517c  cmp     cs:?g_bChgMonCritSectInitialized@@3HA, ebx; int g_bChgMonCritSectInitialized
0x180055182  jz      short loc_180055197
0x180055184  lea     rcx, ?g_csChgMonCritSect@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005518b  call    cs:__imp_DeleteCriticalSection
0x180055191  mov     cs:?g_bChgMonCritSectInitialized@@3HA, ebx; int g_bChgMonCritSectInitialized
0x180055197  mov     rcx, cs:?g_hevtStopChgMonitor@@3PEAXEA; hObject
0x18005519e  test    rcx, rcx
0x1800551a1  jz      short loc_1800551B0
0x1800551a3  call    cs:__imp_CloseHandle
0x1800551a9  mov     cs:?g_hevtStopChgMonitor@@3PEAXEA, rbx; void * g_hevtStopChgMonitor
0x1800551b0  lea     rcx, ?g_PreferenceChgMonitor@@3VCPreferenceChgMonitor@@A; this
0x1800551b7  call    ?_Finalize@CPreferenceChgMonitor@@AEAAXXZ; CPreferenceChgMonitor::_Finalize(void)
0x1800551bc  lea     rcx, ?g_PolicyChgMonitor@@3VCPolicyChgMonitor@@A; this
0x1800551c3  call    ?_Finalize@CPolicyChgMonitor@@AEAAXXZ; CPolicyChgMonitor::_Finalize(void)
0x1800551c8  lea     rcx, ?g_invsemThreadControlBlocks@@3VCInvSemaphore@@A; this
0x1800551cf  mov     cs:?g_bChgMonDirty@@3HA, ebx; int g_bChgMonDirty
0x1800551d5  call    ?_Destroy@CInvSemaphore@@AEAAXXZ; CInvSemaphore::_Destroy(void)
0x1800551da  cmp     cs:?g_bEventDispatcherCritSecInitialized@@3HA, ebx; int g_bEventDispatcherCritSecInitialized
0x1800551e0  jz      short loc_1800551F5
0x1800551e2  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800551e9  call    cs:__imp_DeleteCriticalSection
0x1800551ef  mov     cs:?g_bEventDispatcherCritSecInitialized@@3HA, ebx; int g_bEventDispatcherCritSecInitialized
0x1800551f5  cmp     cs:dword_1800B6B78, ebx
0x1800551fb  jz      short loc_180055210
0x1800551fd  lea     rcx, stru_1800B6B50; lpCriticalSection
0x180055204  call    cs:__imp_DeleteCriticalSection
0x18005520a  mov     cs:dword_1800B6B78, ebx
0x180055210  mov     rcx, cs:WPP_GLOBAL_Control
0x180055217  cmp     rcx, rdi
0x18005521a  jz      short loc_180055237
0x18005521c  test    byte ptr [rcx+1Ch], 8
0x180055220  jz      short loc_180055237
0x180055222  mov     rcx, [rcx+10h]
0x180055226  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18005522d  mov     edx, 43h ; 'C'
0x180055232  call    WPP_SF_
0x180055237  mov     rbx, [rsp+28h+arg_0]
0x18005523c  add     rsp, 20h
0x180055240  pop     rdi
0x180055241  retn
```
