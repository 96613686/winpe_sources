# BCryptIsoDoStateChangeWork

- ea: `0x18003f3b0`
- end: `0x18003f472`
- name: `BCryptIsoDoStateChangeWork`
- size: `194`
- prototype: `void __fastcall(int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18000af80`
- `0x18001b154`
- `0x18001b4a0`
- `0x180023bc8`
- `0x180025ea8`
- `0x180028158`
- `0x18003f3b0`
- `0x1800406dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f3e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f3e4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f3ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f3ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f45a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f45a`

## string_xrefs

- `0x18003f43e`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
void __fastcall BCryptIsoDoStateChangeWork(int a1)
{
  int DwordFromRegistry; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int inited; // eax
  __int64 v8; // r9

  g_keyguardRegistryData = BCryptIsoIsDisabledInRegistry();
  DwordFromRegistry = I_BCryptIsoReadDwordFromRegistry(L"SYSTEM\\CurrentControlSet\\Control\\Lsa", L"LsaPid");
  if ( DwordFromRegistry && GetCurrentProcessId() == DwordFromRegistry && a1 )
  {
    AcquireSRWLockExclusive(&g_servicingLock);
    I_BCryptIsoUninitializeRpc(v4, v3, v5, v6);
    BCryptIsoRemoveAndInvalidateAllHandles();
    if ( !g_keyguardRegistryData )
    {
      inited = I_BCryptIsoInitUtilitiesOnce();
      if ( inited < 0 )
      {
        v8 = 1331;
LABEL_9:
        DebugTraceError(
          (unsigned int)inited,
          "secStatus",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
          v8);
        goto LABEL_10;
      }
      inited = I_BCryptIsoInitializeRpc();
      if ( inited < 0 )
      {
        v8 = 1338;
        goto LABEL_9;
      }
    }
LABEL_10:
    ReleaseSRWLockExclusive(&g_servicingLock);
  }
}

```

## disassembly

```asm
0x18003f3b0  mov     [rsp+arg_0], rbx
0x18003f3b5  push    rdi
0x18003f3b6  sub     rsp, 20h
0x18003f3ba  mov     edi, ecx
0x18003f3bc  call    ?BCryptIsoIsDisabledInRegistry@@YAHXZ; BCryptIsoIsDisabledInRegistry(void)
0x18003f3c1  lea     rdx, ValueName; "LsaPid"
0x18003f3c8  mov     cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A, eax; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18003f3ce  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x18003f3d5  call    I_BCryptIsoReadDwordFromRegistry
0x18003f3da  mov     ebx, eax
0x18003f3dc  test    eax, eax
0x18003f3de  jz      loc_18003F466
0x18003f3e4  call    cs:__imp_GetCurrentProcessId
0x18003f3eb  nop     dword ptr [rax+rax+00h]
0x18003f3f0  cmp     eax, ebx
0x18003f3f2  jnz     short loc_18003F466
0x18003f3f4  test    edi, edi
0x18003f3f6  jz      short loc_18003F466
0x18003f3f8  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003f3ff  call    cs:__imp_AcquireSRWLockExclusive
0x18003f406  nop     dword ptr [rax+rax+00h]
0x18003f40b  call    I_BCryptIsoUninitializeRpc
0x18003f410  call    ?BCryptIsoRemoveAndInvalidateAllHandles@@YAXXZ; BCryptIsoRemoveAndInvalidateAllHandles(void)
0x18003f415  cmp     cs:?g_keyguardRegistryData@@3U_KEYGUARD_REGISTRY_DATA@@A, 0; _KEYGUARD_REGISTRY_DATA g_keyguardRegistryData
0x18003f41c  jnz     short loc_18003F453
0x18003f41e  call    I_BCryptIsoInitUtilitiesOnce
0x18003f423  test    eax, eax
0x18003f425  jns     short loc_18003F42F
0x18003f427  mov     r9d, 533h
0x18003f42d  jmp     short loc_18003F43E
0x18003f42f  call    I_BCryptIsoInitializeRpc
0x18003f434  test    eax, eax
0x18003f436  jns     short loc_18003F453
0x18003f438  mov     r9d, 53Ah
0x18003f43e  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f445  mov     ecx, eax
0x18003f447  lea     rdx, aSecstatus; "secStatus"
0x18003f44e  call    DebugTraceError
0x18003f453  lea     rcx, ?g_servicingLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18003f45a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f461  nop     dword ptr [rax+rax+00h]
0x18003f466  mov     rbx, [rsp+28h+arg_0]
0x18003f46b  add     rsp, 20h
0x18003f46f  pop     rdi
0x18003f470  retn
```
