# BCryptIsoUntrackKeyguardRegistryData

- ea: `0x180028a98`
- end: `0x180028be5`
- name: `BCryptIsoUntrackKeyguardRegistryData`
- size: `333`
- prototype: `void()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002247c`

## callees

- `0x18000af80`
- `0x18001b634`
- `0x180028a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028b68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028ad3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028ad3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028b15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028b15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028bd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b8b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180028b2e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180028b2e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028af0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028af0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180028b3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180028b3d`

## string_xrefs

- `0x180028bad`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisoutils.cpp`

## pseudocode

```c
void BCryptIsoUntrackKeyguardRegistryData()
{
  struct _TP_WAIT *v0; // rbx
  DWORD LastError; // eax

  v0 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids);
  AcquireSRWLockExclusive(&SRWLock);
  if ( qword_18007A218 )
  {
    SetThreadpoolWait(qword_18007A218, 0, 0);
    v0 = qword_18007A218;
    qword_18007A218 = 0;
  }
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v0 )
  {
    WaitForThreadpoolWaitCallbacks(v0, 1);
    CloseThreadpoolWait(v0);
  }
  AcquireSRWLockExclusive(&SRWLock);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hObject )
  {
    if ( !CloseHandle(hObject) )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp",
        315);
    }
    hObject = 0;
  }
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180028a98  push    rbx
0x180028a9a  sub     rsp, 20h
0x180028a9e  xor     ebx, ebx
0x180028aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028aa7  lea     rax, WPP_GLOBAL_Control
0x180028aae  cmp     rcx, rax
0x180028ab1  jz      short loc_180028ACC
0x180028ab3  test    byte ptr [rcx+1Ch], 8
0x180028ab7  jz      short loc_180028ACC
0x180028ab9  mov     rcx, [rcx+10h]
0x180028abd  lea     edx, [rbx+11h]
0x180028ac0  lea     r8, WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids
0x180028ac7  call    WPP_SF_
0x180028acc  lea     rcx, SRWLock; SRWLock
0x180028ad3  call    cs:__imp_AcquireSRWLockExclusive
0x180028ada  nop     dword ptr [rax+rax+00h]
0x180028adf  mov     rcx, cs:qword_18007A218; pwa
0x180028ae6  test    rcx, rcx
0x180028ae9  jz      short loc_180028B0E
0x180028aeb  xor     r8d, r8d; pftTimeout
0x180028aee  xor     edx, edx; h
0x180028af0  call    cs:__imp_SetThreadpoolWait
0x180028af7  nop     dword ptr [rax+rax+00h]
0x180028afc  mov     rbx, cs:qword_18007A218
0x180028b03  mov     cs:qword_18007A218, 0
0x180028b0e  lea     rcx, SRWLock; SRWLock
0x180028b15  call    cs:__imp_ReleaseSRWLockExclusive
0x180028b1c  nop     dword ptr [rax+rax+00h]
0x180028b21  test    rbx, rbx
0x180028b24  jz      short loc_180028B49
0x180028b26  mov     edx, 1; fCancelPendingCallbacks
0x180028b2b  mov     rcx, rbx; pwa
0x180028b2e  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180028b35  nop     dword ptr [rax+rax+00h]
0x180028b3a  mov     rcx, rbx; pwa
0x180028b3d  call    cs:__imp_CloseThreadpoolWait
0x180028b44  nop     dword ptr [rax+rax+00h]
0x180028b49  lea     rcx, SRWLock; SRWLock
0x180028b50  call    cs:__imp_AcquireSRWLockExclusive
0x180028b57  nop     dword ptr [rax+rax+00h]
0x180028b5c  mov     rcx, cs:phkResult; hKey
0x180028b63  test    rcx, rcx
0x180028b66  jz      short loc_180028B7F
0x180028b68  call    cs:__imp_RegCloseKey
0x180028b6f  nop     dword ptr [rax+rax+00h]
0x180028b74  mov     cs:phkResult, 0
0x180028b7f  mov     rcx, cs:hObject; hObject
0x180028b86  test    rcx, rcx
0x180028b89  jz      short loc_180028BCD
0x180028b8b  call    cs:__imp_CloseHandle
0x180028b92  nop     dword ptr [rax+rax+00h]
0x180028b97  test    eax, eax
0x180028b99  jnz     short loc_180028BC2
0x180028b9b  call    cs:__imp_GetLastError
0x180028ba2  nop     dword ptr [rax+rax+00h]
0x180028ba7  mov     r9d, 13Bh
0x180028bad  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180028bb4  mov     ecx, eax
0x180028bb6  lea     rdx, aGetlasterror; "GetLastError()"
0x180028bbd  call    DebugTraceError
0x180028bc2  mov     cs:hObject, 0
0x180028bcd  lea     rcx, SRWLock
0x180028bd4  add     rsp, 20h
0x180028bd8  pop     rbx
0x180028bd9  jmp     cs:__imp_ReleaseSRWLockExclusive
```
