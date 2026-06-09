# I_BCryptIsoInitUtilitiesOnce

- ea: `0x180028158`
- end: `0x180028316`
- name: `I_BCryptIsoInitUtilitiesOnce`
- size: `446`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800167fc`
- `0x18003f3b0`

## callees

- `0x18000af80`
- `0x18001b41c`
- `0x180028158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002818c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002822e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002818c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002822e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028273`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800281e6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800282cd`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800282cd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028216`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028216`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028297`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180028297`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002825b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002825b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180028174`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180028174`

## string_xrefs

- `0x1800281a0`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
__int64 I_BCryptIsoInitUtilitiesOnce()
{
  DWORD LastError; // eax
  __int64 v1; // r9
  int v2; // ebx
  HANDLE EventW; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax

  if ( !pwk )
  {
    pwk = CreateThreadpoolWork(I_BCryptIsoServicingCallback, 0, 0);
    if ( !pwk )
    {
      LastError = GetLastError();
      v1 = 82;
LABEL_4:
      v2 = LastError;
LABEL_5:
      DebugTraceError(
        LastError,
        "status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        v1);
      goto LABEL_21;
    }
  }
  v2 = 0;
  if ( !hKey )
  {
    LastError = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\KeyGuard",
                  0,
                  0x10u,
                  &hKey);
    v2 = LastError;
    if ( LastError )
    {
      v1 = 94;
      goto LABEL_5;
    }
  }
  EventW = hEvent;
  if ( !hEvent )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    hEvent = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v1 = 105;
      goto LABEL_4;
    }
  }
  if ( !pwa )
  {
    ThreadpoolWait = CreateThreadpoolWait(BCryptIsoDisableKeyguardProcessCallback, 0, 0);
    pwa = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      LastError = GetLastError();
      v1 = 116;
      goto LABEL_4;
    }
    SetThreadpoolWait(ThreadpoolWait, hEvent, 0);
    EventW = hEvent;
  }
  if ( !dword_18007A208 )
  {
    LastError = RegNotifyChangeKeyValue(hKey, 0, 0x10000004u, EventW, 1);
    v2 = LastError;
    if ( LastError )
    {
      v1 = 139;
      goto LABEL_5;
    }
    dword_18007A208 = 1;
  }
  BCryptIsoReadKeyguardRegistryData(&g_keyguardRegistryData);
LABEL_21:
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028158  push    rbx
0x18002815a  sub     rsp, 30h
0x18002815e  cmp     cs:pwk, 0
0x180028166  jnz     short loc_1800281BA
0x180028168  xor     r8d, r8d; pcbe
0x18002816b  lea     rcx, I_BCryptIsoServicingCallback; pfnwk
0x180028172  xor     edx, edx; pv
0x180028174  call    cs:__imp_CreateThreadpoolWork
0x18002817b  nop     dword ptr [rax+rax+00h]
0x180028180  mov     cs:pwk, rax
0x180028187  test    rax, rax
0x18002818a  jnz     short loc_1800281BA
0x18002818c  call    cs:__imp_GetLastError
0x180028193  nop     dword ptr [rax+rax+00h]
0x180028198  mov     r9d, 52h ; 'R'
0x18002819e  mov     ebx, eax
0x1800281a0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800281a7  mov     ecx, eax
0x1800281a9  lea     rdx, aStatus_0; "status"
0x1800281b0  call    DebugTraceError
0x1800281b5  jmp     loc_180028300
0x1800281ba  xor     ebx, ebx
0x1800281bc  cmp     cs:hKey, rbx
0x1800281c3  jnz     short loc_180028200
0x1800281c5  lea     rax, hKey
0x1800281cc  xor     r8d, r8d; ulOptions
0x1800281cf  lea     r9d, [rbx+10h]; samDesired
0x1800281d3  mov     [rsp+38h+phkResult], rax; phkResult
0x1800281d8  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x1800281df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800281e6  call    cs:__imp_RegOpenKeyExW
0x1800281ed  nop     dword ptr [rax+rax+00h]
0x1800281f2  mov     ebx, eax
0x1800281f4  test    eax, eax
0x1800281f6  jz      short loc_180028200
0x1800281f8  mov     r9d, 5Eh ; '^'
0x1800281fe  jmp     short loc_1800281A0
0x180028200  mov     rax, cs:hEvent
0x180028207  test    rax, rax
0x18002820a  jnz     short loc_180028245
0x18002820c  xor     r9d, r9d; lpName
0x18002820f  xor     r8d, r8d; bInitialState
0x180028212  xor     edx, edx; bManualReset
0x180028214  xor     ecx, ecx; lpEventAttributes
0x180028216  call    cs:__imp_CreateEventW
0x18002821d  nop     dword ptr [rax+rax+00h]
0x180028222  mov     cs:hEvent, rax
0x180028229  test    rax, rax
0x18002822c  jnz     short loc_180028245
0x18002822e  call    cs:__imp_GetLastError
0x180028235  nop     dword ptr [rax+rax+00h]
0x18002823a  mov     r9d, 69h ; 'i'
0x180028240  jmp     loc_18002819E
0x180028245  cmp     cs:pwa, 0
0x18002824d  jnz     short loc_1800282AA
0x18002824f  xor     r8d, r8d; pcbe
0x180028252  lea     rcx, BCryptIsoDisableKeyguardProcessCallback; pfnwa
0x180028259  xor     edx, edx; pv
0x18002825b  call    cs:__imp_CreateThreadpoolWait
0x180028262  nop     dword ptr [rax+rax+00h]
0x180028267  mov     cs:pwa, rax
0x18002826e  test    rax, rax
0x180028271  jnz     short loc_18002828A
0x180028273  call    cs:__imp_GetLastError
0x18002827a  nop     dword ptr [rax+rax+00h]
0x18002827f  mov     r9d, 74h ; 't'
0x180028285  jmp     loc_18002819E
0x18002828a  mov     rdx, cs:hEvent; h
0x180028291  xor     r8d, r8d; pftTimeout
0x180028294  mov     rcx, rax; pwa
0x180028297  call    cs:__imp_SetThreadpoolWait
0x18002829e  nop     dword ptr [rax+rax+00h]
0x1800282a3  mov     rax, cs:hEvent
0x1800282aa  cmp     cs:dword_18007A208, 0
0x1800282b1  jnz     short loc_1800282F4
0x1800282b3  mov     rcx, cs:hKey; hKey
0x1800282ba  mov     r9, rax; hEvent
0x1800282bd  xor     edx, edx; bWatchSubtree
0x1800282bf  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x1800282c7  mov     r8d, 10000004h; dwNotifyFilter
0x1800282cd  call    cs:__imp_RegNotifyChangeKeyValue
0x1800282d4  nop     dword ptr [rax+rax+00h]
0x1800282d9  mov     ebx, eax
0x1800282db  test    eax, eax
0x1800282dd  jz      short loc_1800282EA
0x1800282df  mov     r9d, 8Bh
0x1800282e5  jmp     loc_1800281A0
0x1800282ea  mov     cs:dword_18007A208, 1
0x1800282f4  lea     rcx, ?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x1800282fb  call    BCryptIsoReadKeyguardRegistryData
0x180028300  test    ebx, ebx
0x180028302  jle     short loc_18002830D
0x180028304  movzx   ebx, bx
0x180028307  or      ebx, 80070000h
0x18002830d  mov     eax, ebx
0x18002830f  add     rsp, 30h
0x180028313  pop     rbx
0x180028314  retn
```
