# CertInUseCleanup

- ea: `0x180019a98`
- end: `0x180019b7e`
- name: `CertInUseCleanup`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013d38`

## callees

- `0x18000148c`
- `0x180018e48`
- `0x180019a98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019aa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019aa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019af6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180019aba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180019aba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180019ad9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180019ad9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180019acc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180019acc`

## pseudocode

```c
__int64 CertInUseCleanup()
{
  AcquireSRWLockExclusive(&stru_18002AF98);
  if ( pwa )
  {
    SetThreadpoolWait(pwa, 0, 0);
    WaitForThreadpoolWaitCallbacks(pwa, 1);
    CloseThreadpoolWait(pwa);
    pwa = 0;
  }
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
  ReleaseSRWLockExclusive(&stru_18002AF98);
  if ( g_pCertInUseProcessInfo )
  {
    ((void (*)(void))CertInUseFree)();
    CertInUseFree(g_pCertInUseProcessInfo + 8);
    CertInUseFree(g_pCertInUseProcessInfo + 16);
    CertInUseFree(&g_pCertInUseProcessInfo);
  }
  return TraceLoggingUnregister_EventUnregister(&qword_18002A108);
}

```

## disassembly

```asm
0x180019a98  sub     rsp, 28h
0x180019a9c  lea     rcx, stru_18002AF98; SRWLock
0x180019aa3  call    cs:__imp_AcquireSRWLockExclusive
0x180019aa9  mov     rcx, cs:pwa; pwa
0x180019ab0  test    rcx, rcx
0x180019ab3  jz      short loc_180019AEA
0x180019ab5  xor     r8d, r8d; pftTimeout
0x180019ab8  xor     edx, edx; h
0x180019aba  call    cs:__imp_SetThreadpoolWait
0x180019ac0  mov     rcx, cs:pwa; pwa
0x180019ac7  mov     edx, 1; fCancelPendingCallbacks
0x180019acc  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180019ad2  mov     rcx, cs:pwa; pwa
0x180019ad9  call    cs:__imp_CloseThreadpoolWait
0x180019adf  mov     cs:pwa, 0
0x180019aea  mov     rcx, cs:hKey; hKey
0x180019af1  test    rcx, rcx
0x180019af4  jz      short loc_180019B07
0x180019af6  call    cs:__imp_RegCloseKey
0x180019afc  mov     cs:hKey, 0
0x180019b07  mov     rcx, cs:h; hObject
0x180019b0e  test    rcx, rcx
0x180019b11  jz      short loc_180019B24
0x180019b13  call    cs:__imp_CloseHandle
0x180019b19  mov     cs:h, 0
0x180019b24  lea     rcx, stru_18002AF98; SRWLock
0x180019b2b  call    cs:__imp_ReleaseSRWLockExclusive
0x180019b31  mov     rcx, cs:g_pCertInUseProcessInfo
0x180019b38  test    rcx, rcx
0x180019b3b  jz      short loc_180019B6E
0x180019b3d  call    CertInUseFree
0x180019b42  mov     rcx, cs:g_pCertInUseProcessInfo
0x180019b49  add     rcx, 8
0x180019b4d  call    CertInUseFree
0x180019b52  mov     rcx, cs:g_pCertInUseProcessInfo
0x180019b59  add     rcx, 10h
0x180019b5d  call    CertInUseFree
0x180019b62  lea     rcx, g_pCertInUseProcessInfo
0x180019b69  call    CertInUseFree
0x180019b6e  lea     rcx, qword_18002A108
0x180019b75  add     rsp, 28h
0x180019b79  jmp     TraceLoggingUnregister_EventUnregister
```
