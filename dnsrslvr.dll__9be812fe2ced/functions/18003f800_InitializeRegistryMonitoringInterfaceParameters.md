# InitializeRegistryMonitoringInterfaceParameters

- ea: `0x18003f800`
- end: `0x18003f890`
- name: `InitializeRegistryMonitoringInterfaceParameters`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18003f724`

## callees

- `0x18002025c`
- `0x18003f800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f867`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003f885`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003f885`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f851`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f851`

## string_xrefs

- `0x18003f81f`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003f82f`: `Dnscache`

## pseudocode

```c
LSTATUS __fastcall InitializeRegistryMonitoringInterfaceParameters(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  LSTATUS result; // eax
  HANDLE EventW; // rax

  result = CreatePersistedRegistryKeyHelper(
             (__int64)L"Dnscache",
             (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
             (__int64)L"InterfaceSpecificParameters",
             a4,
             0x20019u,
             0,
             0,
             &g_hInterfaceSpecificKey);
  if ( !result )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    g_hInterfaceSpecificKeyChange = EventW;
    if ( EventW )
      return RegNotifyChangeKeyValue(g_hInterfaceSpecificKey, 1, 5u, EventW, 1);
    else
      return GetLastError();
  }
  return result;
}

```

## disassembly

```asm
0x18003f800  sub     rsp, 48h
0x18003f804  lea     rax, g_hInterfaceSpecificKey
0x18003f80b  mov     [rsp+48h+var_10], rax
0x18003f810  lea     r8, aInterfacespeci; "InterfaceSpecificParameters"
0x18003f817  mov     [rsp+48h+var_18], 0
0x18003f81f  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003f826  mov     [rsp+48h+var_20], 0
0x18003f82f  lea     rcx, aDnscache_0; "Dnscache"
0x18003f836  mov     [rsp+48h+fAsynchronous], 20019h
0x18003f83e  call    CreatePersistedRegistryKeyHelper
0x18003f843  test    eax, eax
0x18003f845  jnz     short loc_18003F88B
0x18003f847  xor     r9d, r9d; lpName
0x18003f84a  xor     r8d, r8d; bInitialState
0x18003f84d  xor     edx, edx; bManualReset
0x18003f84f  xor     ecx, ecx; lpEventAttributes
0x18003f851  call    cs:__imp_CreateEventW
0x18003f857  mov     cs:g_hInterfaceSpecificKeyChange, rax
0x18003f85e  test    rax, rax
0x18003f861  jnz     short loc_18003F86E
0x18003f863  add     rsp, 48h
0x18003f867  jmp     cs:__imp_GetLastError
0x18003f86e  mov     rcx, cs:g_hInterfaceSpecificKey; hKey
0x18003f875  mov     edx, 1; bWatchSubtree
0x18003f87a  mov     r9, rax; hEvent
0x18003f87d  mov     [rsp+48h+fAsynchronous], edx; fAsynchronous
0x18003f881  lea     r8d, [rdx+4]; dwNotifyFilter
0x18003f885  call    cs:__imp_RegNotifyChangeKeyValue
0x18003f88b  add     rsp, 48h
0x18003f88f  retn
```
