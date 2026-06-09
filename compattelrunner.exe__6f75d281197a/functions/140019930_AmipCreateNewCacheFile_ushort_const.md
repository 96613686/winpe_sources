# AmipCreateNewCacheFile(ushort const *)

- ea: `0x140019930`
- end: `0x140019db5`
- name: `?AmipCreateNewCacheFile@@YAKPEBG@Z`
- size: `1157`
- prototype: `unsigned int __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001a914`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400151b0`
- `0x140018988`
- `0x140018c3c`
- `0x140019930`
- `0x14001ac30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140019a69`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140019a8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140019a69`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140019a8a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140019a2a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140019a2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140019c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140019c05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140019bec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140019bec`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140019b10`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140019b10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019d67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019d67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019acb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140019acb`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140019d3c`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140019d3c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140019d82`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140019d82`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019bb1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019c6b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019cc8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019d0d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019bb1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019c6b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019cc8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140019d0d`

## string_xrefs

- `0x1400199db`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1400199e8`: `AppCompatFlags`
- `0x1400199c1`: `AmipCreateNewCacheFile`
- `0x140019a44`: `AmipCreateNewCacheFile`
- `0x140019b6a`: `AmipCreateNewCacheFile`
- `0x140019bcc`: `AmipCreateNewCacheFile`
- `0x140019c2f`: `AmipCreateNewCacheFile`
- `0x140019c86`: `AmipCreateNewCacheFile`
- `0x140019af9`: `AmiUtilityGivePrivilegesToServices failed [%d]`
- `0x140019ad7`: `RegCreateKeyEx failed [%d]`
- `0x140019ba0`: `CreatingCommand`
- `0x140019b63`: `AmiCache creating command: %ls`
- `0x140019c1d`: `AmiCache creating module: %ls`
- `0x140019bbb`: `RegSetKeyValue failed [%d]`
- `0x140019c75`: `RegSetKeyValue failed [%d]`
- `0x140019cd4`: `RegSetKeyValue failed [%d]`
- `0x140019d19`: `RegSetKeyValue failed [%d]`
- `0x140019d78`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\{11517B7C-E79D-4e20-961B-75A811715ADD}`

## pseudocode

```c
__int64 __fastcall AmipCreateNewCacheFile(LPCWSTR lpFile)
{
  unsigned __int8 v2; // dl
  LSTATUS PersistedLocation; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rbx
  LPWSTR CommandLineW; // rax
  WCHAR *v11; // rdx
  __int64 v12; // r8
  WCHAR *v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rax
  LSTATUS v16; // eax
  const wchar_t *v17; // rbx
  LSTATUS v18; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v25[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Data[264]; // [rsp+490h] [rbp+390h] BYREF

  v21 = 0;
  memset_0(v25, 0, 0x20Au);
  memset_0(SubKey, 0, 0x20Au);
  hKey = 0;
  phModule = 0;
  PersistedLocation = AmiUtilitySetPrivilege(0x11u, v2);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "You must be logged on as Administrator/System [%d]";
    v6 = 56;
    v7 = 3;
LABEL_3:
    dwOptions[0] = PersistedLocation;
    AslLogCallPrintf(v7, "AmipCreateNewCacheFile", v6, v5, *(_QWORD *)dwOptions);
    goto LABEL_42;
  }
  PersistedLocation = AmiUtilityGetPersistedLocation(
                        (unsigned int)v25,
                        261,
                        (unsigned int)L"AppCompatFlags",
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                        1);
  if ( PersistedLocation < 0 )
  {
    v4 = 1287;
    v5 = "AmiUtilityGetPersistedLocation [%#x]";
    v6 = 67;
LABEL_6:
    v7 = 1;
    goto LABEL_3;
  }
  if ( (unsigned int)_o_wcscpy_s(SubKey, 261, v25) )
  {
    v8 = 74;
LABEL_9:
    v4 = 1287;
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", v8, "wcscpy_s failed");
    goto LABEL_42;
  }
  if ( (unsigned int)_o_wcscat_s(SubKey, 261, L"\\") )
  {
    v8 = 81;
    goto LABEL_9;
  }
  if ( (unsigned int)_o_wcscat_s(SubKey, 261, L"{11517B7C-E79D-4e20-961B-75A811715ADD}") )
  {
    v8 = 88;
    goto LABEL_9;
  }
  PersistedLocation = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegCreateKeyEx failed [%d]";
    v6 = 107;
    goto LABEL_6;
  }
  PersistedLocation = AmiUtilityGivePrivilegesToServices(hKey);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "AmiUtilityGivePrivilegesToServices failed [%d]";
    v6 = 118;
    goto LABEL_6;
  }
  v9 = 2147483646;
  CommandLineW = GetCommandLineW();
  v11 = Data;
  v12 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*CommandLineW )
      break;
    *v11++ = *CommandLineW++;
    --v9;
    --v12;
  }
  while ( v12 );
  v13 = v11 - 1;
  if ( v12 )
    v13 = v11;
  *v13 = 0;
  AslLogCallPrintf(3, "AmipCreateNewCacheFile", 138, "AmiCache creating command: %ls", Data);
  v14 = -1;
  v15 = -1;
  do
    ++v15;
  while ( Data[v15] );
  v16 = RegSetKeyValueW(hKey, 0, L"CreatingCommand", 1u, Data, 2 * v15 + 2);
  if ( v16 )
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", 147, "RegSetKeyValue failed [%d]", v16);
  if ( !GetModuleHandleExW(6u, (LPCWSTR)AmipCreateNewCacheFile, &phModule)
    || (v17 = Data, !GetModuleFileNameW(phModule, Data, 0x104u)) )
  {
    v17 = L"Unknown";
  }
  AslLogCallPrintf(3, "AmipCreateNewCacheFile", 162, "AmiCache creating module: %ls", v17);
  do
    ++v14;
  while ( v17[v14] );
  v18 = RegSetKeyValueW(hKey, 0, L"CreatingModule", 1u, v17, 2 * v14 + 2);
  if ( v18 )
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", 171, "RegSetKeyValue failed [%d]", v18);
  v21 = 1;
  PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v25, L"AmiHivePermissionsCorrect", 4u, &v21, 4u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSetKeyValue failed [%d]";
    v6 = 186;
    goto LABEL_6;
  }
  v21 = 1;
  PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v25, L"AmiHiveOwnerCorrect", 4u, &v21, 4u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSetKeyValue failed [%d]";
    v6 = 198;
    goto LABEL_6;
  }
  PersistedLocation = RegSaveKeyExW(hKey, lpFile, 0, 2u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSaveKeyEx failed [%d]";
    v6 = 208;
    goto LABEL_6;
  }
  v4 = 0;
LABEL_42:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
    RegDeleteKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\{11517B7C-E79D-4e20-961B-75A811715ADD}",
      0,
      0);
  }
  return v4;
}

```

## disassembly

```asm
0x140019930  mov     [rsp-8+arg_8], rbx
0x140019935  mov     [rsp-8+arg_10], rsi
0x14001993a  push    rbp
0x14001993b  push    rdi
0x14001993c  push    r13
0x14001993e  push    r14
0x140019940  push    r15
0x140019942  lea     rbp, [rsp-5B0h]
0x14001994a  sub     rsp, 6B0h
0x140019951  mov     rax, cs:__security_cookie
0x140019958  xor     rax, rsp
0x14001995b  mov     [rbp+5D0h+var_30], rax
0x140019962  mov     rsi, rcx
0x140019965  mov     ebx, 20Ah
0x14001996a  xor     r14d, r14d
0x14001996d  lea     rcx, [rbp+5D0h+var_450]; void *
0x140019974  mov     r8d, ebx; Size
0x140019977  mov     [rsp+6D0h+var_680], r14d
0x14001997c  xor     edx, edx; Val
0x14001997e  call    memset_0
0x140019983  mov     r8d, ebx; Size
0x140019986  lea     rcx, [rsp+6D0h+SubKey]; void *
0x14001998b  xor     edx, edx; Val
0x14001998d  call    memset_0
0x140019992  lea     ecx, [r14+11h]; unsigned int
0x140019996  mov     [rsp+6D0h+hKey], r14
0x14001999b  mov     [rsp+6D0h+phModule], r14
0x1400199a0  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x1400199a5  mov     ebx, eax
0x1400199a7  mov     r13, 0FFFFFFFF80000002h
0x1400199ae  test    eax, eax
0x1400199b0  jz      short loc_1400199D6
0x1400199b2  lea     r9, aYouMustBeLogge; "You must be logged on as Administrator/"...
0x1400199b9  lea     r8d, [r14+38h]
0x1400199bd  lea     ecx, [r14+3]
0x1400199c1  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x1400199c8  mov     [rsp+6D0h+dwOptions], eax
0x1400199cc  call    AslLogCallPrintf
0x1400199d1  jmp     loc_140019D5D
0x1400199d6  mov     ebx, 105h
0x1400199db  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400199e2  mov     r15d, 1
0x1400199e8  lea     r8, aAppcompatflags; "AppCompatFlags"
0x1400199ef  mov     edx, ebx
0x1400199f1  mov     [rsp+6D0h+dwOptions], r15d
0x1400199f6  lea     rcx, [rbp+5D0h+var_450]
0x1400199fd  call    AmiUtilityGetPersistedLocation
0x140019a02  test    eax, eax
0x140019a04  jns     short loc_140019A1B
0x140019a06  mov     ebx, 507h
0x140019a0b  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x140019a12  lea     r8d, [r15+42h]
0x140019a16  mov     ecx, r15d
0x140019a19  jmp     short loc_1400199C1
0x140019a1b  lea     r8, [rbp+5D0h+var_450]
0x140019a22  mov     rdx, rbx
0x140019a25  lea     rcx, [rsp+6D0h+SubKey]
0x140019a2a  call    cs:__imp__o_wcscpy_s
0x140019a30  test    eax, eax
0x140019a32  jz      short loc_140019A5A
0x140019a34  mov     r8d, 4Ah ; 'J'
0x140019a3a  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x140019a41  mov     ecx, r15d
0x140019a44  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x140019a4b  mov     ebx, 507h
0x140019a50  call    AslLogCallPrintf
0x140019a55  jmp     loc_140019D5D
0x140019a5a  lea     r8, Source; "\\"
0x140019a61  mov     rdx, rbx
0x140019a64  lea     rcx, [rsp+6D0h+SubKey]
0x140019a69  call    cs:__imp__o_wcscat_s
0x140019a6f  test    eax, eax
0x140019a71  jz      short loc_140019A7B
0x140019a73  mov     r8d, 51h ; 'Q'
0x140019a79  jmp     short loc_140019A3A
0x140019a7b  lea     r8, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x140019a82  mov     rdx, rbx
0x140019a85  lea     rcx, [rsp+6D0h+SubKey]
0x140019a8a  call    cs:__imp__o_wcscat_s
0x140019a90  test    eax, eax
0x140019a92  jz      short loc_140019A9C
0x140019a94  mov     r8d, 58h ; 'X'
0x140019a9a  jmp     short loc_140019A3A
0x140019a9c  mov     [rsp+6D0h+lpdwDisposition], r14; lpdwDisposition
0x140019aa1  lea     rax, [rsp+6D0h+hKey]
0x140019aa6  mov     [rsp+6D0h+phkResult], rax; phkResult
0x140019aab  lea     rdx, [rsp+6D0h+SubKey]; lpSubKey
0x140019ab0  mov     [rsp+6D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140019ab5  xor     r9d, r9d; lpClass
0x140019ab8  mov     [rsp+6D0h+samDesired], 0F003Fh; samDesired
0x140019ac0  xor     r8d, r8d; Reserved
0x140019ac3  mov     rcx, r13; hKey
0x140019ac6  mov     [rsp+6D0h+dwOptions], r14d; dwOptions
0x140019acb  call    cs:__imp_RegCreateKeyExW
0x140019ad1  mov     ebx, eax
0x140019ad3  test    eax, eax
0x140019ad5  jz      short loc_140019AE9
0x140019ad7  lea     r9, aRegcreatekeyex; "RegCreateKeyEx failed [%d]"
0x140019ade  mov     r8d, 6Bh ; 'k'
0x140019ae4  jmp     loc_140019A16
0x140019ae9  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140019aee  call    ?AmiUtilityGivePrivilegesToServices@@YAKPEAUHKEY__@@@Z; AmiUtilityGivePrivilegesToServices(HKEY__ *)
0x140019af3  mov     ebx, eax
0x140019af5  test    eax, eax
0x140019af7  jz      short loc_140019B0B
0x140019af9  lea     r9, aAmiutilitygive_0; "AmiUtilityGivePrivilegesToServices fail"...
0x140019b00  mov     r8d, 76h ; 'v'
0x140019b06  jmp     loc_140019A16
0x140019b0b  mov     ebx, 7FFFFFFEh
0x140019b10  call    cs:__imp_GetCommandLineW
0x140019b16  mov     r13d, 104h
0x140019b1c  lea     rdx, [rbp+5D0h+Data]
0x140019b23  mov     r8d, r13d
0x140019b26  test    rbx, rbx
0x140019b29  jz      short loc_140019B46
0x140019b2b  movzx   ecx, word ptr [rax]
0x140019b2e  test    cx, cx
0x140019b31  jz      short loc_140019B46
0x140019b33  mov     [rdx], cx
0x140019b36  add     rax, 2
0x140019b3a  add     rdx, 2
0x140019b3e  sub     rbx, r15
0x140019b41  sub     r8, r15
0x140019b44  jnz     short loc_140019B26
0x140019b46  test    r8, r8
0x140019b49  lea     rcx, [rdx-2]
0x140019b4d  lea     rbx, [rbp+5D0h+Data]
0x140019b54  mov     r8d, 8Ah
0x140019b5a  cmovnz  rcx, rdx
0x140019b5e  mov     qword ptr [rsp+6D0h+dwOptions], rbx
0x140019b63  lea     r9, aAmicacheCreati_0; "AmiCache creating command: %ls"
0x140019b6a  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x140019b71  mov     [rcx], r14w
0x140019b75  mov     ecx, 3
0x140019b7a  call    AslLogCallPrintf
0x140019b7f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140019b83  mov     rax, rdi
0x140019b86  inc     rax
0x140019b89  cmp     [rbx+rax*2], r14w
0x140019b8e  jnz     short loc_140019B86
0x140019b90  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140019b95  lea     eax, ds:2[rax*2]
0x140019b9c  mov     [rsp+6D0h+samDesired], eax; cbData
0x140019ba0  lea     r8, aCreatingcomman; "CreatingCommand"
0x140019ba7  mov     r9d, r15d; dwType
0x140019baa  mov     qword ptr [rsp+6D0h+dwOptions], rbx; lpData
0x140019baf  xor     edx, edx; lpSubKey
0x140019bb1  call    cs:__imp_RegSetKeyValueW
0x140019bb7  test    eax, eax
0x140019bb9  jz      short loc_140019BDB
0x140019bbb  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x140019bc2  mov     [rsp+6D0h+dwOptions], eax
0x140019bc6  mov     r8d, 93h
0x140019bcc  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x140019bd3  mov     ecx, r15d
0x140019bd6  call    AslLogCallPrintf
0x140019bdb  lea     r8, [rsp+6D0h+phModule]; phModule
0x140019be0  mov     ecx, 6; dwFlags
0x140019be5  lea     rdx, ?AmipCreateNewCacheFile@@YAKPEBG@Z; lpModuleName
0x140019bec  call    cs:__imp_GetModuleHandleExW
0x140019bf2  test    eax, eax
0x140019bf4  jz      short loc_140019C16
0x140019bf6  mov     rcx, [rsp+6D0h+phModule]; hModule
0x140019bfb  lea     rdx, [rbp+5D0h+Data]; lpFilename
0x140019c02  mov     r8d, r13d; nSize
0x140019c05  call    cs:__imp_GetModuleFileNameW
0x140019c0b  lea     rbx, [rbp+5D0h+Data]
0x140019c12  test    eax, eax
0x140019c14  jnz     short loc_140019C1D
0x140019c16  lea     rbx, aUnknown; "Unknown"
0x140019c1d  lea     r9, aAmicacheCreati; "AmiCache creating module: %ls"
0x140019c24  mov     qword ptr [rsp+6D0h+dwOptions], rbx
0x140019c29  mov     r8d, 0A2h
0x140019c2f  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x140019c36  mov     ecx, 3
0x140019c3b  call    AslLogCallPrintf
0x140019c40  inc     rdi
0x140019c43  cmp     [rbx+rdi*2], r14w
0x140019c48  jnz     short loc_140019C40
0x140019c4a  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140019c4f  lea     eax, ds:2[rdi*2]
0x140019c56  mov     [rsp+6D0h+samDesired], eax; cbData
0x140019c5a  lea     r8, aCreatingmodule; "CreatingModule"
0x140019c61  mov     r9d, r15d; dwType
0x140019c64  mov     qword ptr [rsp+6D0h+dwOptions], rbx; lpData
0x140019c69  xor     edx, edx; lpSubKey
0x140019c6b  call    cs:__imp_RegSetKeyValueW
0x140019c71  test    eax, eax
0x140019c73  jz      short loc_140019C95
0x140019c75  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x140019c7c  mov     [rsp+6D0h+dwOptions], eax
0x140019c80  mov     r8d, 0ABh
0x140019c86  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x140019c8d  mov     ecx, r15d
0x140019c90  call    AslLogCallPrintf
0x140019c95  mov     edi, 4
0x140019c9a  mov     [rsp+6D0h+var_680], r15d
0x140019c9f  lea     rax, [rsp+6D0h+var_680]
0x140019ca4  mov     [rsp+6D0h+samDesired], edi; cbData
0x140019ca8  mov     r13, 0FFFFFFFF80000002h
0x140019caf  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x140019cb4  mov     r9d, edi; dwType
0x140019cb7  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x140019cbe  mov     rcx, r13; hKey
0x140019cc1  lea     rdx, [rbp+5D0h+var_450]; lpSubKey
0x140019cc8  call    cs:__imp_RegSetKeyValueW
0x140019cce  mov     ebx, eax
0x140019cd0  test    eax, eax
0x140019cd2  jz      short loc_140019CE6
0x140019cd4  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x140019cdb  mov     r8d, 0BAh
0x140019ce1  jmp     loc_140019A16
0x140019ce6  lea     rax, [rsp+6D0h+var_680]
0x140019ceb  mov     [rsp+6D0h+samDesired], edi; cbData
0x140019cef  mov     r9d, edi; dwType
0x140019cf2  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x140019cf7  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x140019cfe  mov     [rsp+6D0h+var_680], r15d
0x140019d03  lea     rdx, [rbp+5D0h+var_450]; lpSubKey
0x140019d0a  mov     rcx, r13; hKey
0x140019d0d  call    cs:__imp_RegSetKeyValueW
0x140019d13  mov     ebx, eax
0x140019d15  test    eax, eax
0x140019d17  jz      short loc_140019D2B
0x140019d19  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x140019d20  mov     r8d, 0C6h
0x140019d26  jmp     loc_140019A16
0x140019d2b  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140019d30  mov     r9d, 2; Flags
0x140019d36  xor     r8d, r8d; lpSecurityAttributes
0x140019d39  mov     rdx, rsi; lpFile
0x140019d3c  call    cs:__imp_RegSaveKeyExW
0x140019d42  mov     ebx, eax
0x140019d44  test    eax, eax
0x140019d46  jz      short loc_140019D5A
0x140019d48  lea     r9, aRegsavekeyexFa; "RegSaveKeyEx failed [%d]"
0x140019d4f  mov     r8d, 0D0h
0x140019d55  jmp     loc_140019A16
0x140019d5a  mov     ebx, r14d
0x140019d5d  mov     rcx, [rsp+6D0h+hKey]; hKey
0x140019d62  test    rcx, rcx
0x140019d65  jz      short loc_140019D88
0x140019d67  call    cs:__imp_RegCloseKey
0x140019d6d  xor     r9d, r9d; Reserved
0x140019d70  mov     [rsp+6D0h+hKey], r14
0x140019d75  xor     r8d, r8d; samDesired
0x140019d78  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140019d7f  mov     rcx, r13; hKey
0x140019d82  call    cs:__imp_RegDeleteKeyExW
0x140019d88  mov     eax, ebx
0x140019d8a  mov     rcx, [rbp+5D0h+var_30]
0x140019d91  xor     rcx, rsp; StackCookie
0x140019d94  call    __security_check_cookie
0x140019d99  lea     r11, [rsp+6D0h+var_20]
0x140019da1  mov     rbx, [r11+38h]
0x140019da5  mov     rsi, [r11+40h]
0x140019da9  mov     rsp, r11
0x140019dac  pop     r15
0x140019dae  pop     r14
0x140019db0  pop     r13
0x140019db2  pop     rdi
0x140019db3  pop     rbp
0x140019db4  retn
```
