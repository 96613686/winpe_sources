# OnRegChange_CertInUse

- ea: `0x18001e970`
- end: `0x18001ea09`
- name: `OnRegChange_CertInUse`
- size: `153`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001652c`
- `0x18001e970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ea02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e97b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e97b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001e9b7`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001e9b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e9cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001e9f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001e9f1`

## pseudocode

```c
void __fastcall OnRegChange_CertInUse(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  AcquireSRWLockExclusive(&stru_18002AF98);
  ReadKey_CertInUse();
  if ( hKey && h && pwa )
  {
    if ( RegNotifyChangeKeyValue(hKey, 1, 0x10000004u, h, 1) )
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
    }
    else
    {
      SetThreadpoolWait(pwa, h, 0);
    }
  }
  ReleaseSRWLockExclusive(&stru_18002AF98);
}

```

## disassembly

```asm
0x18001e970  sub     rsp, 38h
0x18001e974  lea     rcx, stru_18002AF98; SRWLock
0x18001e97b  call    cs:__imp_AcquireSRWLockExclusive
0x18001e981  call    ReadKey_CertInUse
0x18001e986  mov     rcx, cs:hKey; hKey
0x18001e98d  test    rcx, rcx
0x18001e990  jz      short loc_18001E9F7
0x18001e992  mov     r9, cs:h; hEvent
0x18001e999  test    r9, r9
0x18001e99c  jz      short loc_18001E9F7
0x18001e99e  cmp     cs:pwa, 0
0x18001e9a6  jz      short loc_18001E9F7
0x18001e9a8  mov     edx, 1; bWatchSubtree
0x18001e9ad  mov     r8d, 10000004h; dwNotifyFilter
0x18001e9b3  mov     [rsp+38h+fAsynchronous], edx; fAsynchronous
0x18001e9b7  call    cs:__imp_RegNotifyChangeKeyValue
0x18001e9bd  test    eax, eax
0x18001e9bf  jz      short loc_18001E9E0
0x18001e9c1  mov     rcx, cs:hKey; hKey
0x18001e9c8  test    rcx, rcx
0x18001e9cb  jz      short loc_18001E9F7
0x18001e9cd  call    cs:__imp_RegCloseKey
0x18001e9d3  mov     cs:hKey, 0
0x18001e9de  jmp     short loc_18001E9F7
0x18001e9e0  mov     rdx, cs:h; h
0x18001e9e7  xor     r8d, r8d; pftTimeout
0x18001e9ea  mov     rcx, cs:pwa; pwa
0x18001e9f1  call    cs:__imp_SetThreadpoolWait
0x18001e9f7  lea     rcx, stru_18002AF98
0x18001e9fe  add     rsp, 38h
0x18001ea02  jmp     cs:__imp_ReleaseSRWLockExclusive
```
