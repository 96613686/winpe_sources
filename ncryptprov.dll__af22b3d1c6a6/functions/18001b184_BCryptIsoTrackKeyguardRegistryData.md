# BCryptIsoTrackKeyguardRegistryData

- ea: `0x18001b184`
- end: `0x18001b416`
- name: `BCryptIsoTrackKeyguardRegistryData`
- size: `658`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800222fc`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18001b184`
- `0x18001b41c`
- `0x18001b634`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b2d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b2d4`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001b27d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001b27d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b29a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b29a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b1ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b1ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b24d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001b24d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b224`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18001b224`

## string_xrefs

- `0x18001b330`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisoutils.cpp`
- `0x18001b3ae`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisoutils.cpp`
- `0x18001b3ee`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisoutils.cpp`

## pseudocode

```c
__int64 BCryptIsoTrackKeyguardRegistryData()
{
  HANDLE EventW; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  unsigned int LastError; // ebx
  unsigned int v3; // eax
  int v4; // edi
  LSTATUS v6; // eax
  int v7; // edx
  __int64 v8; // r9

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids);
  AcquireSRWLockExclusive(&SRWLock);
  BCryptIsoReadKeyguardRegistryData(&g_VbsRegistryData);
  if ( !phkResult )
  {
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard",
           0,
           0x10u,
           &phkResult);
    LastError = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v7,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp",
          (unsigned int)"lStatus",
          v6,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp",
          213);
      if ( (int)LastError > 0 )
      {
        LastError = (unsigned __int16)LastError;
LABEL_16:
        LastError |= 0xC0070000;
        goto LABEL_9;
      }
      goto LABEL_9;
    }
  }
  EventW = hObject;
  if ( !hObject )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    hObject = EventW;
    if ( !EventW )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      v8 = 225;
      goto LABEL_25;
    }
  }
  if ( qword_18007A218 )
    goto LABEL_8;
  ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)BCryptIsoRegNotifyCallback, &g_VbsRegistryData, 0);
  qword_18007A218 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    v8 = 236;
LABEL_25:
    DebugTraceError(LastError, "ntStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp", v8);
    goto LABEL_9;
  }
  SetThreadpoolWait(ThreadpoolWait, hObject, 0);
  EventW = hObject;
LABEL_8:
  LastError = 0;
  v3 = RegNotifyChangeKeyValue(phkResult, 1, 0x10000004u, EventW, 1);
  v4 = v3;
  if ( v3 )
  {
    DebugTraceError(v3, "lStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp", 257);
    if ( v4 <= 0 )
    {
      LastError = v4;
      goto LABEL_9;
    }
    LastError = (unsigned __int16)v4;
    goto LABEL_16;
  }
LABEL_9:
  ReleaseSRWLockExclusive(&SRWLock);
  return LastError;
}

```

## disassembly

```asm
0x18001b184  mov     [rsp+arg_0], rbx
0x18001b189  push    rdi
0x18001b18a  sub     rsp, 40h
0x18001b18e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b195  lea     rdi, WPP_GLOBAL_Control
0x18001b19c  mov     ebx, 10h
0x18001b1a1  cmp     rcx, rdi
0x18001b1a4  jnz     loc_18001B30B
0x18001b1aa  lea     rcx, SRWLock; SRWLock
0x18001b1b1  call    cs:__imp_AcquireSRWLockExclusive
0x18001b1b8  nop     dword ptr [rax+rax+00h]
0x18001b1bd  lea     rcx, g_VbsRegistryData
0x18001b1c4  call    BCryptIsoReadKeyguardRegistryData
0x18001b1c9  cmp     cs:phkResult, 0
0x18001b1d1  jz      loc_18001B2B4
0x18001b1d7  mov     rax, cs:hObject
0x18001b1de  test    rax, rax
0x18001b1e1  jnz     short loc_18001B209
0x18001b1e3  xor     r9d, r9d; lpName
0x18001b1e6  xor     r8d, r8d; bInitialState
0x18001b1e9  xor     edx, edx; bManualReset
0x18001b1eb  xor     ecx, ecx; lpEventAttributes
0x18001b1ed  call    cs:__imp_CreateEventW
0x18001b1f4  nop     dword ptr [rax+rax+00h]
0x18001b1f9  mov     cs:hObject, rax
0x18001b200  test    rax, rax
0x18001b203  jz      loc_18001B356
0x18001b209  cmp     cs:qword_18007A218, 0
0x18001b211  jnz     short loc_18001B260
0x18001b213  xor     r8d, r8d; pcbe
0x18001b216  lea     rdx, g_VbsRegistryData; pv
0x18001b21d  lea     rcx, BCryptIsoRegNotifyCallback; pfnwa
0x18001b224  call    cs:__imp_CreateThreadpoolWait
0x18001b22b  nop     dword ptr [rax+rax+00h]
0x18001b230  mov     cs:qword_18007A218, rax
0x18001b237  test    rax, rax
0x18001b23a  jz      loc_18001B3C8
0x18001b240  mov     rdx, cs:hObject; h
0x18001b247  xor     r8d, r8d; pftTimeout
0x18001b24a  mov     rcx, rax; pwa
0x18001b24d  call    cs:__imp_SetThreadpoolWait
0x18001b254  nop     dword ptr [rax+rax+00h]
0x18001b259  mov     rax, cs:hObject
0x18001b260  mov     rcx, cs:phkResult; hKey
0x18001b267  xor     ebx, ebx
0x18001b269  mov     r9, rax; hEvent
0x18001b26c  mov     [rsp+48h+fAsynchronous], 1; fAsynchronous
0x18001b274  mov     r8d, 10000004h; dwNotifyFilter
0x18001b27a  lea     edx, [rbx+1]; bWatchSubtree
0x18001b27d  call    cs:__imp_RegNotifyChangeKeyValue
0x18001b284  nop     dword ptr [rax+rax+00h]
0x18001b289  mov     edi, eax
0x18001b28b  test    eax, eax
0x18001b28d  jnz     loc_18001B3E8
0x18001b293  lea     rcx, SRWLock; SRWLock
0x18001b29a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b2a1  nop     dword ptr [rax+rax+00h]
0x18001b2a6  mov     eax, ebx
0x18001b2a8  mov     rbx, [rsp+48h+arg_0]
0x18001b2ad  add     rsp, 40h
0x18001b2b1  pop     rdi
0x18001b2b2  retn
0x18001b2b4  lea     rax, phkResult
0x18001b2bb  mov     r9d, ebx; samDesired
0x18001b2be  xor     r8d, r8d; ulOptions
0x18001b2c1  mov     qword ptr [rsp+48h+fAsynchronous], rax; phkResult
0x18001b2c6  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x18001b2cd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b2d4  call    cs:__imp_RegOpenKeyExW
0x18001b2db  nop     dword ptr [rax+rax+00h]
0x18001b2e0  mov     ebx, eax
0x18001b2e2  test    eax, eax
0x18001b2e4  jz      loc_18001B1D7
0x18001b2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2f1  cmp     rcx, rdi
0x18001b2f4  jz      short loc_18001B2FC
0x18001b2f6  test    byte ptr [rcx+1Ch], 1
0x18001b2fa  jnz     short loc_18001B32C
0x18001b2fc  test    ebx, ebx
0x18001b2fe  jle     short loc_18001B293
0x18001b300  movzx   ebx, bx
0x18001b303  or      ebx, 0C0070000h
0x18001b309  jmp     short loc_18001B293
0x18001b30b  test    byte ptr [rcx+1Ch], 8
0x18001b30f  jz      loc_18001B1AA
0x18001b315  mov     rcx, [rcx+10h]
0x18001b319  lea     r8, WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids
0x18001b320  mov     edx, ebx
0x18001b322  call    WPP_SF_
0x18001b327  jmp     loc_18001B1AA
0x18001b32c  mov     rcx, [rcx+10h]
0x18001b330  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b337  mov     [rsp+48h+var_18], 0D5h
0x18001b33f  lea     r9, aLstatus; "lStatus"
0x18001b346  mov     [rsp+48h+var_20], r8
0x18001b34b  mov     [rsp+48h+fAsynchronous], ebx
0x18001b34f  call    WPP_SF_sDsd
0x18001b354  jmp     short loc_18001B2FC
0x18001b356  call    cs:__imp_GetLastError
0x18001b35d  nop     dword ptr [rax+rax+00h]
0x18001b362  test    eax, eax
0x18001b364  jg      short loc_18001B376
0x18001b366  call    cs:__imp_GetLastError
0x18001b36d  nop     dword ptr [rax+rax+00h]
0x18001b372  mov     ebx, eax
0x18001b374  jmp     short loc_18001B38B
0x18001b376  call    cs:__imp_GetLastError
0x18001b37d  nop     dword ptr [rax+rax+00h]
0x18001b382  movzx   ebx, ax
0x18001b385  or      ebx, 0C0070000h
0x18001b38b  mov     r9d, 0E1h
0x18001b391  jmp     short loc_18001B3AE
0x18001b393  call    cs:__imp_GetLastError
0x18001b39a  nop     dword ptr [rax+rax+00h]
0x18001b39f  movzx   ebx, ax
0x18001b3a2  or      ebx, 0C0070000h
0x18001b3a8  mov     r9d, 0ECh
0x18001b3ae  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b3b5  mov     ecx, ebx
0x18001b3b7  lea     rdx, aNtstatus; "ntStatus"
0x18001b3be  call    DebugTraceError
0x18001b3c3  jmp     loc_18001B293
0x18001b3c8  call    cs:__imp_GetLastError
0x18001b3cf  nop     dword ptr [rax+rax+00h]
0x18001b3d4  test    eax, eax
0x18001b3d6  jg      short loc_18001B393
0x18001b3d8  call    cs:__imp_GetLastError
0x18001b3df  nop     dword ptr [rax+rax+00h]
0x18001b3e4  mov     ebx, eax
0x18001b3e6  jmp     short loc_18001B3A8
0x18001b3e8  mov     r9d, 101h
0x18001b3ee  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b3f5  lea     rdx, aLstatus; "lStatus"
0x18001b3fc  mov     ecx, edi
0x18001b3fe  call    DebugTraceError
0x18001b403  test    edi, edi
0x18001b405  jg      short loc_18001B40E
0x18001b407  mov     ebx, edi
0x18001b409  jmp     loc_18001B293
0x18001b40e  movzx   ebx, di
0x18001b411  jmp     loc_18001B303
```
