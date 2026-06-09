# BCryptIsoUninitialize

- ea: `0x180024af4`
- end: `0x180024c12`
- name: `BCryptIsoUninitialize`
- size: `286`
- prototype: `void()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002247c`

## callees

- `0x18000af80`
- `0x180024af4`
- `0x180040040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024b92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024bb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180024b5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180024b5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180024b09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180024b09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180024b44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180024b44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180024b1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180024b1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024b6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180024b6f`

## string_xrefs

- `0x180024bd7`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
void BCryptIsoUninitialize()
{
  DWORD LastError; // eax

  if ( pwk )
  {
    WaitForThreadpoolWorkCallbacks(pwk, 1);
    CloseThreadpoolWork(pwk);
    pwk = 0;
  }
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
  if ( hEvent )
  {
    if ( !CloseHandle(hEvent) )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "GetLastError()",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        203);
    }
    hEvent = 0;
  }
  if ( dword_18007A77C )
    KGT_Uninitialize((PRTL_CRITICAL_SECTION)qword_18007A780);
}

```

## disassembly

```asm
0x180024af4  sub     rsp, 28h
0x180024af8  mov     rcx, cs:pwk; pwk
0x180024aff  test    rcx, rcx
0x180024b02  jz      short loc_180024B33
0x180024b04  mov     edx, 1; fCancelPendingCallbacks
0x180024b09  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180024b10  nop     dword ptr [rax+rax+00h]
0x180024b15  mov     rcx, cs:pwk; pwk
0x180024b1c  call    cs:__imp_CloseThreadpoolWork
0x180024b23  nop     dword ptr [rax+rax+00h]
0x180024b28  mov     cs:pwk, 0
0x180024b33  mov     rcx, cs:pwa; pwa
0x180024b3a  test    rcx, rcx
0x180024b3d  jz      short loc_180024B86
0x180024b3f  xor     r8d, r8d; pftTimeout
0x180024b42  xor     edx, edx; h
0x180024b44  call    cs:__imp_SetThreadpoolWait
0x180024b4b  nop     dword ptr [rax+rax+00h]
0x180024b50  mov     rcx, cs:pwa; pwa
0x180024b57  mov     edx, 1; fCancelPendingCallbacks
0x180024b5c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180024b63  nop     dword ptr [rax+rax+00h]
0x180024b68  mov     rcx, cs:pwa; pwa
0x180024b6f  call    cs:__imp_CloseThreadpoolWait
0x180024b76  nop     dword ptr [rax+rax+00h]
0x180024b7b  mov     cs:pwa, 0
0x180024b86  mov     rcx, cs:hKey; hKey
0x180024b8d  test    rcx, rcx
0x180024b90  jz      short loc_180024BA9
0x180024b92  call    cs:__imp_RegCloseKey
0x180024b99  nop     dword ptr [rax+rax+00h]
0x180024b9e  mov     cs:hKey, 0
0x180024ba9  mov     rcx, cs:hEvent; hObject
0x180024bb0  test    rcx, rcx
0x180024bb3  jz      short loc_180024BF7
0x180024bb5  call    cs:__imp_CloseHandle
0x180024bbc  nop     dword ptr [rax+rax+00h]
0x180024bc1  test    eax, eax
0x180024bc3  jnz     short loc_180024BEC
0x180024bc5  call    cs:__imp_GetLastError
0x180024bcc  nop     dword ptr [rax+rax+00h]
0x180024bd1  mov     r9d, 0CBh
0x180024bd7  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180024bde  mov     ecx, eax
0x180024be0  lea     rdx, aGetlasterror; "GetLastError()"
0x180024be7  call    DebugTraceError
0x180024bec  mov     cs:hEvent, 0
0x180024bf7  cmp     cs:dword_18007A77C, 0
0x180024bfe  jz      short loc_180024C0C
0x180024c00  lea     rcx, qword_18007A780; CriticalSection
0x180024c07  call    ?KGT_Uninitialize@@YAXPEAUKEYGUARD_TELEMETRY_GLOBAL@@@Z; KGT_Uninitialize(KEYGUARD_TELEMETRY_GLOBAL *)
0x180024c0c  add     rsp, 28h
0x180024c10  retn
```
