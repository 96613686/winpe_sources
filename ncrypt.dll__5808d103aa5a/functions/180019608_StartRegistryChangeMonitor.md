# StartRegistryChangeMonitor

- ea: `0x180019608`
- end: `0x180019769`
- name: `StartRegistryChangeMonitor`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800169b0`

## callees

- `0x18001652c`
- `0x180019608`
- `0x180019770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800196e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800196e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019667`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019667`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019613`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019613`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001964f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001964f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196af`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001970f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001970f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019643`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019692`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180019729`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180019729`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001974c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001974c`

## string_xrefs

- `0x18001967a`: `Failed to initialize StartRegistryChangeMonitor`

## pseudocode

```c
void StartRegistryChangeMonitor()
{
  LSTATUS v0; // eax
  HANDLE EventA; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(&stru_18002AF98);
  phkResult = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Cryptography", 0, 0x10u, &phkResult);
  if ( v0 )
  {
    SetLastError(v0);
    hKey = 0;
  }
  else
  {
    hKey = phkResult;
    if ( phkResult )
    {
      EventA = CreateEventA(0, 0, 0, 0);
      h = EventA;
      if ( EventA )
      {
        if ( !RegNotifyChangeKeyValue(hKey, 1, 0x10000004u, EventA, 1) )
        {
          ThreadpoolWait = CreateThreadpoolWait(OnRegChange_CertInUse, 0, 0);
          pwa = ThreadpoolWait;
          if ( ThreadpoolWait )
          {
            SetThreadpoolWait(ThreadpoolWait, h, 0);
            ReadKey_CertInUse();
            ReleaseSRWLockExclusive(&stru_18002AF98);
            return;
          }
        }
      }
    }
  }
  ReleaseSRWLockExclusive(&stru_18002AF98);
  EtwErrorNCryptCertInUse(L"Failed to initialize StartRegistryChangeMonitor", (STRSAFE_PCNZWCH)&LocaleName);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( h )
  {
    CloseHandle(h);
    h = 0;
  }
}

```

## disassembly

```asm
0x180019608  sub     rsp, 38h
0x18001960c  lea     rcx, stru_18002AF98; SRWLock
0x180019613  call    cs:__imp_AcquireSRWLockExclusive
0x180019619  lea     rax, [rsp+38h+arg_0]
0x18001961e  mov     [rsp+38h+arg_0], 0
0x180019627  mov     r9d, 10h; samDesired
0x18001962d  mov     [rsp+38h+phkResult], rax; phkResult
0x180019632  xor     r8d, r8d; ulOptions
0x180019635  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18001963c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019643  call    cs:__imp_RegOpenKeyExW
0x180019649  test    eax, eax
0x18001964b  jz      short loc_1800196C5
0x18001964d  mov     ecx, eax; dwErrCode
0x18001964f  call    cs:__imp_SetLastError
0x180019655  mov     cs:hKey, 0
0x180019660  lea     rcx, stru_18002AF98; SRWLock
0x180019667  call    cs:__imp_ReleaseSRWLockExclusive
0x18001966d  mov     r8d, 80004005h
0x180019673  lea     rdx, LocaleName; STRSAFE_PCNZWCH
0x18001967a  lea     rcx, aFailedToInitia; "Failed to initialize StartRegistryChang"...
0x180019681  call    EtwErrorNCryptCertInUse
0x180019686  mov     rcx, cs:hKey; hKey
0x18001968d  test    rcx, rcx
0x180019690  jz      short loc_1800196A3
0x180019692  call    cs:__imp_RegCloseKey
0x180019698  mov     cs:hKey, 0
0x1800196a3  mov     rcx, cs:h; hObject
0x1800196aa  test    rcx, rcx
0x1800196ad  jz      short loc_1800196C0
0x1800196af  call    cs:__imp_CloseHandle
0x1800196b5  mov     cs:h, 0
0x1800196c0  add     rsp, 38h
0x1800196c4  retn
0x1800196c5  mov     rax, [rsp+38h+arg_0]
0x1800196ca  mov     cs:hKey, rax
0x1800196d1  test    rax, rax
0x1800196d4  jz      short loc_180019660
0x1800196d6  xor     r9d, r9d; lpName
0x1800196d9  xor     r8d, r8d; bInitialState
0x1800196dc  xor     edx, edx; bManualReset
0x1800196de  xor     ecx, ecx; lpEventAttributes
0x1800196e0  call    cs:__imp_CreateEventA
0x1800196e6  mov     cs:h, rax
0x1800196ed  test    rax, rax
0x1800196f0  jz      loc_180019660
0x1800196f6  mov     rcx, cs:hKey; hKey
0x1800196fd  mov     edx, 1; bWatchSubtree
0x180019702  mov     r9, rax; hEvent
0x180019705  mov     dword ptr [rsp+38h+phkResult], edx; fAsynchronous
0x180019709  mov     r8d, 10000004h; dwNotifyFilter
0x18001970f  call    cs:__imp_RegNotifyChangeKeyValue
0x180019715  test    eax, eax
0x180019717  jnz     loc_180019660
0x18001971d  xor     r8d, r8d; pcbe
0x180019720  lea     rcx, OnRegChange_CertInUse; pfnwa
0x180019727  xor     edx, edx; pv
0x180019729  call    cs:__imp_CreateThreadpoolWait
0x18001972f  mov     cs:pwa, rax
0x180019736  test    rax, rax
0x180019739  jz      loc_180019660
0x18001973f  mov     rdx, cs:h; h
0x180019746  xor     r8d, r8d; pftTimeout
0x180019749  mov     rcx, rax; pwa
0x18001974c  call    cs:__imp_SetThreadpoolWait
0x180019752  call    ReadKey_CertInUse
0x180019757  lea     rcx, stru_18002AF98
0x18001975e  add     rsp, 38h
0x180019762  jmp     cs:__imp_ReleaseSRWLockExclusive
```
