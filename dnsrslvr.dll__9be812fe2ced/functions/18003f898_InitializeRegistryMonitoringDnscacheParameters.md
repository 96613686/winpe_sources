# InitializeRegistryMonitoringDnscacheParameters

- ea: `0x18003f898`
- end: `0x18003f954`
- name: `InitializeRegistryMonitoringDnscacheParameters`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18003f724`

## callees

- `0x18002025c`
- `0x18003f898`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f8ff`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003f91e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003f91e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f8ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003f8ed`

## string_xrefs

- `0x18003f8b9`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18003f8c9`: `Dnscache`

## pseudocode

```c
__int64 __fastcall InitializeRegistryMonitoringDnscacheParameters(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int PersistedRegistryKeyHelper; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax

  PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                 (__int64)L"Dnscache",
                                 (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                 (__int64)L"Parameters",
                                 a4,
                                 0x20019u,
                                 0,
                                 0,
                                 &g_hCacheKey);
  if ( PersistedRegistryKeyHelper
    || ((EventW = CreateEventW(0, 0, 0, 0), (g_hRegistryChange = EventW) != 0)
      ? (LastError = RegNotifyChangeKeyValue(g_hCacheKey, 1, 5u, EventW, 1))
      : (LastError = GetLastError()),
        (PersistedRegistryKeyHelper = LastError) != 0) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 19, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids, PersistedRegistryKeyHelper);
  }
  return PersistedRegistryKeyHelper;
}

```

## disassembly

```asm
0x18003f898  push    rbx
0x18003f89a  sub     rsp, 40h
0x18003f89e  lea     rax, g_hCacheKey
0x18003f8a5  mov     [rsp+48h+var_10], rax
0x18003f8aa  lea     r8, aParameters; "Parameters"
0x18003f8b1  mov     [rsp+48h+var_18], 0
0x18003f8b9  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18003f8c0  mov     [rsp+48h+var_20], 0
0x18003f8c9  lea     rcx, aDnscache_0; "Dnscache"
0x18003f8d0  mov     [rsp+48h+fAsynchronous], 20019h
0x18003f8d8  call    CreatePersistedRegistryKeyHelper
0x18003f8dd  mov     ebx, eax
0x18003f8df  test    eax, eax
0x18003f8e1  jnz     short loc_18003F92A
0x18003f8e3  xor     r9d, r9d; lpName
0x18003f8e6  xor     r8d, r8d; bInitialState
0x18003f8e9  xor     edx, edx; bManualReset
0x18003f8eb  xor     ecx, ecx; lpEventAttributes
0x18003f8ed  call    cs:__imp_CreateEventW
0x18003f8f3  mov     cs:g_hRegistryChange, rax
0x18003f8fa  test    rax, rax
0x18003f8fd  jnz     short loc_18003F907
0x18003f8ff  call    cs:__imp_GetLastError
0x18003f905  jmp     short loc_18003F924
0x18003f907  mov     rcx, cs:g_hCacheKey; hKey
0x18003f90e  mov     edx, 1; bWatchSubtree
0x18003f913  mov     r9, rax; hEvent
0x18003f916  mov     [rsp+48h+fAsynchronous], edx; fAsynchronous
0x18003f91a  lea     r8d, [rdx+4]; dwNotifyFilter
0x18003f91e  call    cs:__imp_RegNotifyChangeKeyValue
0x18003f924  mov     ebx, eax
0x18003f926  test    eax, eax
0x18003f928  jz      short loc_18003F94C
0x18003f92a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003f931  jz      short loc_18003F94C
0x18003f933  mov     edx, 13h
0x18003f938  lea     r8, WPP_f740467901d037f9bb0724a7406bee3b_Traceguids
0x18003f93f  mov     ecx, 40Bh
0x18003f944  mov     r9d, ebx
0x18003f947  call    WPP_SF_d
0x18003f94c  mov     eax, ebx
0x18003f94e  add     rsp, 40h
0x18003f952  pop     rbx
0x18003f953  retn
```
