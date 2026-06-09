# InitializeProviderHosts(void)

- ea: `0x180033c70`
- end: `0x180033d00`
- name: `?InitializeProviderHosts@@YAJXZ`
- size: `144`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180042f44`

## callees

- `0x180033c70`
- `0x180033d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180033c90`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180033c90`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180033cac`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180033cac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033cd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180033cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ce5`

## pseudocode

```c
signed int InitializeProviderHosts(void)
{
  signed int result; // eax

  qword_1800A4620 = (__int64)&qword_1800A4618;
  qword_1800A4618 = (__int64)&qword_1800A4618;
  InitializeCriticalSection(&HostList);
  pSetupInitializeUtils();
  g_bDevnodeSubsystemStoping = 0;
  InitializeSRWLock(&g_srwDevnodeSubsystemStoping);
  *(_DWORD *)g_cHosts = 0;
  g_hHostsExitedEvent = 0;
  g_hHostsExitedEvent = CreateEventW(0, 1, 1, 0);
  if ( g_hHostsExitedEvent )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180033c70  sub     rsp, 28h
0x180033c74  lea     rax, qword_1800A4618
0x180033c7b  mov     cs:qword_1800A4620, rax
0x180033c82  mov     cs:qword_1800A4618, rax
0x180033c89  lea     rcx, ?HostList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180033c90  call    cs:__imp_InitializeCriticalSection
0x180033c96  call    pSetupInitializeUtils
0x180033c9b  mov     cs:?g_bDevnodeSubsystemStoping@@3HA, 0; int g_bDevnodeSubsystemStoping
0x180033ca5  lea     rcx, ?g_srwDevnodeSubsystemStoping@@3U_RTL_SRWLOCK@@A; SRWLock
0x180033cac  call    cs:__imp_InitializeSRWLock
0x180033cb2  mov     cs:?g_cHosts@@3KA, 0; ulong g_cHosts
0x180033cbc  mov     cs:?g_hHostsExitedEvent@@3PEAXEA, 0; void * g_hHostsExitedEvent
0x180033cc7  xor     r9d, r9d; lpName
0x180033cca  lea     edx, [r9+1]; bManualReset
0x180033cce  mov     r8d, edx; bInitialState
0x180033cd1  xor     ecx, ecx; lpEventAttributes
0x180033cd3  call    cs:__imp_CreateEventW
0x180033cd9  mov     cs:?g_hHostsExitedEvent@@3PEAXEA, rax; void * g_hHostsExitedEvent
0x180033ce0  test    rax, rax
0x180033ce3  jnz     short loc_180033CF9
0x180033ce5  call    cs:__imp_GetLastError
0x180033ceb  test    eax, eax
0x180033ced  jle     short loc_180033CFB
0x180033cef  movzx   eax, ax
0x180033cf2  or      eax, 80070000h
0x180033cf7  jmp     short loc_180033CFB
0x180033cf9  xor     eax, eax
0x180033cfb  add     rsp, 28h
0x180033cff  retn
```
