# CreateDefaultSetupMigrationTree

- ea: `0x180031528`
- end: `0x1800317c2`
- name: `CreateDefaultSetupMigrationTree`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180034690`

## callees

- `0x180031528`
- `0x1800327a8`
- `0x18003639c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031596`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003167f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800316ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031596`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003167f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800316ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800315e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003176c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003176c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031796`

## string_xrefs

- `0x1800315a8`: `Failed to create setup migration key`
- `0x180031691`: `Failed to create providers subkey`
- `0x1800316e0`: `Failed to create well known GUIDs subkey`
- `0x18003173e`: `Failed to write GUID`

## pseudocode

```c
__int64 __fastcall CreateDefaultSetupMigrationTree(HKEY a1, HKEY *a2, HKEY *a3, HKEY *a4)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx
  const wchar_t *v9; // rdx
  unsigned int i; // edi
  DWORD dwDisposition; // [rsp+50h] [rbp-19h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  HKEY v15; // [rsp+68h] [rbp-1h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+7h] BYREF

  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  v15 = 0;
  v7 = RegCreateKeyExW(a1, L"Setup Migration", 0, (LPWSTR)&::Data, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to create setup migration key";
    goto LABEL_3;
  }
  *(_DWORD *)Data = 4105;
  v7 = RegSetValueExW(hKey, L"Setup Version", 0, 4u, Data, 4u);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to set default setup version value";
    goto LABEL_3;
  }
  v7 = WriteMultiSz(hKey);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to set default provider list value";
    goto LABEL_3;
  }
  v7 = WriteMultiSz(hKey);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to set known static provider list value";
    goto LABEL_3;
  }
  v7 = RegCreateKeyExW(hKey, L"Providers", 0, (LPWSTR)&::Data, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to create providers subkey";
    goto LABEL_3;
  }
  v7 = RegCreateKeyExW(hKey, L"Well Known Guids", 0, (LPWSTR)&::Data, 0, 0x2001Fu, 0, &v15, &dwDisposition);
  v8 = v7;
  if ( v7 )
  {
    v9 = L"Failed to create well known GUIDs subkey";
LABEL_3:
    LogError(v7, v9);
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v15 )
      RegCloseKey(v15);
    *a2 = 0;
    *a3 = 0;
    *a4 = 0;
    return v8;
  }
  for ( i = 0; i < 3; ++i )
  {
    v7 = RegSetValueExW(v15, (&DefaultWellKnownGuids)[3 * i], 0, 3u, (const BYTE *)&qword_180063418[3 * i], 0x10u);
    v8 = v7;
    if ( v7 )
    {
      v9 = L"Failed to write GUID";
      goto LABEL_3;
    }
  }
  *a2 = hKey;
  *a3 = phkResult;
  *a4 = v15;
  return v8;
}

```

## disassembly

```asm
0x180031528  push    rbp
0x18003152a  push    rbx
0x18003152b  push    rsi
0x18003152c  push    rdi
0x18003152d  push    r12
0x18003152f  push    r13
0x180031531  push    r14
0x180031533  push    r15
0x180031535  lea     rbp, [rsp-1Fh]
0x18003153a  sub     rsp, 88h
0x180031541  xor     r12d, r12d
0x180031544  lea     rax, [rbp+57h+dwDisposition]
0x180031548  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18003154d  lea     r13, Data
0x180031554  lea     rax, [rbp+57h+hKey]
0x180031558  mov     [rbp+57h+dwDisposition], r12d
0x18003155c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180031561  mov     rsi, r9
0x180031564  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180031569  mov     r14, r8
0x18003156c  mov     r15, rdx
0x18003156f  mov     [rbp+57h+hKey], r12
0x180031573  mov     edi, 2001Fh
0x180031578  mov     [rbp+57h+var_50], r12
0x18003157c  mov     [rsp+0C0h+samDesired], edi; samDesired
0x180031580  lea     rdx, aSetupMigration; "Setup Migration"
0x180031587  mov     r9, r13; lpClass
0x18003158a  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x18003158f  xor     r8d, r8d; Reserved
0x180031592  mov     [rbp+57h+var_58], r12
0x180031596  call    cs:__imp_RegCreateKeyExW
0x18003159d  nop     dword ptr [rax+rax+00h]
0x1800315a2  mov     ebx, eax
0x1800315a4  test    eax, eax
0x1800315a6  jz      short loc_1800315BB
0x1800315a8  lea     rdx, aFailedToCreate; "Failed to create setup migration key"
0x1800315af  mov     ecx, eax
0x1800315b1  call    LogError
0x1800315b6  jmp     loc_180031763
0x1800315bb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800315bf  lea     rax, [rbp+57h+Data]
0x1800315c3  mov     r9d, 4; dwType
0x1800315c9  mov     dword ptr [rbp+57h+Data], 1009h
0x1800315d0  mov     [rsp+0C0h+samDesired], r9d; cbData
0x1800315d5  lea     rdx, aSetupVersion; "Setup Version"
0x1800315dc  xor     r8d, r8d; Reserved
0x1800315df  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x1800315e4  call    cs:__imp_RegSetValueExW
0x1800315eb  nop     dword ptr [rax+rax+00h]
0x1800315f0  mov     ebx, eax
0x1800315f2  test    eax, eax
0x1800315f4  jz      short loc_1800315FF
0x1800315f6  lea     rdx, aFailedToSetDef; "Failed to set default setup version val"...
0x1800315fd  jmp     short loc_1800315AF
0x1800315ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180031603  lea     r8, DefaultProviderList
0x18003160a  lea     rdx, aProviderList; "Provider List"
0x180031611  call    WriteMultiSz
0x180031616  mov     ebx, eax
0x180031618  test    eax, eax
0x18003161a  jz      short loc_180031625
0x18003161c  lea     rdx, aFailedToSetDef_0; "Failed to set default provider list val"...
0x180031623  jmp     short loc_1800315AF
0x180031625  mov     rcx, [rbp+57h+hKey]; hKey
0x180031629  lea     r8, DefaultKnownStaticProviders; "Tcpip"
0x180031630  lea     rdx, aKnownStaticPro; "Known Static Providers"
0x180031637  call    WriteMultiSz
0x18003163c  mov     ebx, eax
0x18003163e  test    eax, eax
0x180031640  jz      short loc_18003164E
0x180031642  lea     rdx, aFailedToSetKno; "Failed to set known static provider lis"...
0x180031649  jmp     loc_1800315AF
0x18003164e  mov     rcx, [rbp+57h+hKey]; hKey
0x180031652  lea     rax, [rbp+57h+dwDisposition]
0x180031656  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x18003165b  lea     rdx, aProviders; "Providers"
0x180031662  lea     rax, [rbp+57h+var_50]
0x180031666  mov     r9, r13; lpClass
0x180031669  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18003166e  xor     r8d, r8d; Reserved
0x180031671  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180031676  mov     [rsp+0C0h+samDesired], edi; samDesired
0x18003167a  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x18003167f  call    cs:__imp_RegCreateKeyExW
0x180031686  nop     dword ptr [rax+rax+00h]
0x18003168b  mov     ebx, eax
0x18003168d  test    eax, eax
0x18003168f  jz      short loc_18003169D
0x180031691  lea     rdx, aFailedToCreate_0; "Failed to create providers subkey"
0x180031698  jmp     loc_1800315AF
0x18003169d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800316a1  lea     rax, [rbp+57h+dwDisposition]
0x1800316a5  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x1800316aa  lea     rdx, aWellKnownGuids; "Well Known Guids"
0x1800316b1  lea     rax, [rbp+57h+var_58]
0x1800316b5  mov     r9, r13; lpClass
0x1800316b8  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800316bd  xor     r8d, r8d; Reserved
0x1800316c0  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800316c5  mov     [rsp+0C0h+samDesired], edi; samDesired
0x1800316c9  mov     [rsp+0C0h+dwOptions], r12d; dwOptions
0x1800316ce  call    cs:__imp_RegCreateKeyExW
0x1800316d5  nop     dword ptr [rax+rax+00h]
0x1800316da  mov     ebx, eax
0x1800316dc  test    eax, eax
0x1800316de  jz      short loc_1800316EC
0x1800316e0  lea     rdx, aFailedToCreate_2; "Failed to create well known GUIDs subke"...
0x1800316e7  jmp     loc_1800315AF
0x1800316ec  mov     edi, r12d
0x1800316ef  lea     r13, DefaultWellKnownGuids
0x1800316f6  cmp     edi, 3
0x1800316f9  jnb     short loc_18003174A
0x1800316fb  mov     rcx, [rbp+57h+var_58]; hKey
0x1800316ff  mov     r9d, 3; dwType
0x180031705  mov     eax, edi
0x180031707  xor     r8d, r8d; Reserved
0x18003170a  mov     [rsp+0C0h+samDesired], 10h; cbData
0x180031712  lea     rdx, [rax+rax*2]
0x180031716  lea     rax, [r13+8]
0x18003171a  lea     rax, [rax+rdx*8]
0x18003171e  mov     rdx, [r13+rdx*8+0]; lpValueName
0x180031723  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180031728  call    cs:__imp_RegSetValueExW
0x18003172f  nop     dword ptr [rax+rax+00h]
0x180031734  mov     ebx, eax
0x180031736  test    eax, eax
0x180031738  jnz     short loc_18003173E
0x18003173a  inc     edi
0x18003173c  jmp     short loc_1800316F6
0x18003173e  lea     rdx, aFailedToWriteG; "Failed to write GUID"
0x180031745  jmp     loc_1800315AF
0x18003174a  mov     rax, [rbp+57h+hKey]
0x18003174e  mov     [r15], rax
0x180031751  mov     rax, [rbp+57h+var_50]
0x180031755  mov     [r14], rax
0x180031758  mov     rax, [rbp+57h+var_58]
0x18003175c  mov     [rsi], rax
0x18003175f  test    ebx, ebx
0x180031761  jz      short loc_1800317AB
0x180031763  mov     rcx, [rbp+57h+hKey]; hKey
0x180031767  test    rcx, rcx
0x18003176a  jz      short loc_180031778
0x18003176c  call    cs:__imp_RegCloseKey
0x180031773  nop     dword ptr [rax+rax+00h]
0x180031778  mov     rcx, [rbp+57h+var_50]; hKey
0x18003177c  test    rcx, rcx
0x18003177f  jz      short loc_18003178D
0x180031781  call    cs:__imp_RegCloseKey
0x180031788  nop     dword ptr [rax+rax+00h]
0x18003178d  mov     rcx, [rbp+57h+var_58]; hKey
0x180031791  test    rcx, rcx
0x180031794  jz      short loc_1800317A2
0x180031796  call    cs:__imp_RegCloseKey
0x18003179d  nop     dword ptr [rax+rax+00h]
0x1800317a2  mov     [r15], r12
0x1800317a5  mov     [r14], r12
0x1800317a8  mov     [rsi], r12
0x1800317ab  mov     eax, ebx
0x1800317ad  add     rsp, 88h
0x1800317b4  pop     r15
0x1800317b6  pop     r14
0x1800317b8  pop     r13
0x1800317ba  pop     r12
0x1800317bc  pop     rdi
0x1800317bd  pop     rsi
0x1800317be  pop     rbx
0x1800317bf  pop     rbp
0x1800317c0  retn
```
