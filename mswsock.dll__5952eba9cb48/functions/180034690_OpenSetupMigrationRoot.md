# OpenSetupMigrationRoot

- ea: `0x180034690`
- end: `0x180034ae2`
- name: `OpenSetupMigrationRoot`
- size: `1106`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800328c0`

## callees

- `0x180031528`
- `0x1800327a8`
- `0x1800327f0`
- `0x180034690`
- `0x180034cbc`
- `0x18003592c`
- `0x180035acc`
- `0x180038104`
- `0x180038118`
- `0x18003a0d4`
- `0x18003aec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800349f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034a8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003471f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800347d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003488f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003471f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800347d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003488f`

## string_xrefs

- `0x180034736`: `Could not open Migration subkey`
- `0x1800347ef`: `Could not open providers subkey`
- `0x1800348a8`: `Could not open well known GUIDs subkey`
- `0x180034951`: `Failed to read setup version value`
- `0x18003495f`: `WARNING: Could not parse migration registry tree, so blowing away and creating a new one from scratch`
- `0x1800349c9`: `Failed to remove all installed providers`
- `0x180034a20`: `Failed to recursively delete migration subtree`
- `0x180034a46`: `Failed to create default setup migration tree`
- `0x180034aad`: `Successfully created default setup migration tree`

## pseudocode

```c
__int64 __fastcall OpenSetupMigrationRoot(HKEY hKey, HKEY *a2, HKEY *a3, HKEY *a4, __int64 a5)
{
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  const wchar_t *v11; // rdx
  __int64 v12; // rdx
  char v13; // al
  unsigned int v14; // eax
  __int64 v15; // rcx
  char v16; // al
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v21; // [rsp+30h] [rbp-58h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-50h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-48h] BYREF
  HKEY v24[8]; // [rsp+48h] [rbp-40h] BYREF

  v21 = 0;
  hKeya = 0;
  phkResult = 0;
  *(_OWORD *)a5 = 0;
  *(_OWORD *)(a5 + 16) = 0;
  *(_QWORD *)(a5 + 32) = 0;
  v24[0] = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_qS(
      1025,
      22,
      (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
      (_DWORD)hKey,
      (__int64)L"Setup Migration");
  v9 = RegOpenKeyExW(hKey, L"Setup Migration", 0, 0xF003Fu, &hKeya);
  v10 = v9;
  if ( v9 )
  {
    if ( v9 != 2 )
    {
      v11 = L"Could not open Migration subkey";
LABEL_49:
      v15 = v10;
      goto LABEL_50;
    }
    LogMsg(L"The migration subkey does not exist.");
    if ( (xmmword_180063D60 & 2) == 0 )
      goto LABEL_35;
    v12 = 24;
    goto LABEL_26;
  }
  v13 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_q(1025, 23, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, hKeya);
    v13 = xmmword_180063D60;
  }
  if ( (v13 & 2) != 0 )
    WPP_SF_qS(
      1025,
      25,
      (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
      (_DWORD)hKeya,
      (__int64)L"Providers");
  v14 = RegOpenKeyExW(hKeya, L"Providers", 0, 0xF003Fu, &phkResult);
  v10 = v14;
  if ( !v14 )
  {
    v16 = xmmword_180063D60;
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      WPP_SF_q(1025, 26, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, phkResult);
      v16 = xmmword_180063D60;
    }
    if ( (v16 & 2) != 0 )
      WPP_SF_qS(
        1025,
        28,
        (unsigned int)WPP_4593deb55ead3582b257adde53a3fabd_Traceguids,
        (_DWORD)hKeya,
        (__int64)L"Well Known Guids");
    v17 = RegOpenKeyExW(hKeya, L"Well Known Guids", 0, 0xF003Fu, v24);
    v10 = v17;
    if ( v17 )
    {
      v15 = v17;
      if ( v17 != 2 )
      {
        v11 = L"Could not open well known GUIDs subkey";
        goto LABEL_50;
      }
      LogError(2, L"The well known GUIDs migration subkey does not exist");
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v12 = 30;
        goto LABEL_26;
      }
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_q(1025, 29, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v24[0]);
      v18 = ReadDword(hKeya, L"Setup Version", &v21);
      v10 = v18;
      if ( v18 )
      {
        LogError(v18, L"Failed to read setup version value");
      }
      else
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_l(v19, 31, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v21);
        if ( v21 == 4105 )
          goto LABEL_58;
      }
    }
LABEL_35:
    LogMsg(L"WARNING: Could not parse migration registry tree, so blowing away and creating a new one from scratch");
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 32, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
    if ( hKeya )
    {
      RegCloseKey(hKeya);
      hKeya = 0;
    }
    if ( phkResult )
    {
      v10 = RemoveAllInstalledProviders(phkResult);
      if ( v10 )
      {
        v11 = L"Failed to remove all installed providers";
        goto LABEL_49;
      }
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    if ( v24[0] )
    {
      RegCloseKey(v24[0]);
      v24[0] = 0;
    }
    v10 = RecursivelyDeleteRegistryTree(hKey, L"Setup Migration");
    if ( v10 )
    {
      v11 = L"Failed to recursively delete migration subtree";
      goto LABEL_49;
    }
    v10 = CreateDefaultSetupMigrationTree(hKey, &hKeya, &phkResult, v24);
    if ( v10 )
    {
      v11 = L"Failed to create default setup migration tree";
      goto LABEL_49;
    }
    LogMsg(L"Successfully created default setup migration tree");
LABEL_58:
    *a2 = hKeya;
    *a3 = phkResult;
    *a4 = v24[0];
    return v10;
  }
  v15 = v14;
  if ( v14 == 2 )
  {
    LogError(2, L"The migration providers subkey does not exist");
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v12 = 27;
LABEL_26:
      WPP_SF_(1025, v12, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  v11 = L"Could not open providers subkey";
LABEL_50:
  LogError(v15, v11);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v24[0] )
    RegCloseKey(v24[0]);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  return v10;
}

```

## disassembly

```asm
0x180034690  mov     r11, rsp
0x180034693  push    rbx
0x180034694  push    rsi
0x180034695  push    rdi
0x180034696  push    r13
0x180034698  push    r14
0x18003469a  push    r15
0x18003469c  sub     rsp, 58h
0x1800346a0  mov     r13, [rsp+88h+arg_20]
0x1800346a8  xor     eax, eax
0x1800346aa  xorps   xmm0, xmm0
0x1800346ad  mov     [rsp+88h+var_58], 0
0x1800346b5  mov     rsi, r9
0x1800346b8  mov     [r11-50h], rax
0x1800346bc  mov     r14, r8
0x1800346bf  mov     [r11-48h], rax
0x1800346c3  movups  xmmword ptr [r13+0], xmm0
0x1800346c8  mov     r15, rdx
0x1800346cb  mov     rdi, rcx
0x1800346ce  movups  xmmword ptr [r13+10h], xmm0
0x1800346d3  mov     [r13+20h], rax
0x1800346d7  mov     [r11-40h], rax
0x1800346db  test    byte ptr cs:xmmword_180063D60, 2
0x1800346e2  lea     rbx, aSetupMigration; "Setup Migration"
0x1800346e9  jz      short loc_180034706
0x1800346eb  lea     edx, [rax+16h]
0x1800346ee  mov     [r11-68h], rbx
0x1800346f2  mov     ecx, 401h
0x1800346f7  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800346fe  mov     r9, rdi
0x180034701  call    WPP_SF_qS
0x180034706  lea     rax, [rsp+88h+hKey]
0x18003470b  mov     r9d, 0F003Fh; samDesired
0x180034711  xor     r8d, r8d; ulOptions
0x180034714  mov     [rsp+88h+phkResult], rax; phkResult
0x180034719  mov     rdx, rbx; lpSubKey
0x18003471c  mov     rcx, rdi; hKey
0x18003471f  call    cs:__imp_RegOpenKeyExW
0x180034726  nop     dword ptr [rax+rax+00h]
0x18003472b  mov     ebx, eax
0x18003472d  test    eax, eax
0x18003472f  jz      short loc_180034765
0x180034731  cmp     eax, 2
0x180034734  jz      short loc_180034742
0x180034736  lea     rdx, aCouldNotOpenMi; "Could not open Migration subkey"
0x18003473d  jmp     loc_180034A4D
0x180034742  lea     rcx, aTheMigrationSu; "The migration subkey does not exist."
0x180034749  call    LogMsg
0x18003474e  test    byte ptr cs:xmmword_180063D60, 2
0x180034755  jz      loc_18003495F
0x18003475b  mov     edx, 18h
0x180034760  jmp     loc_1800348D2
0x180034765  mov     al, byte ptr cs:xmmword_180063D60
0x18003476b  test    al, 2
0x18003476d  jz      short loc_180034790
0x18003476f  mov     r9, [rsp+88h+hKey]
0x180034774  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003477b  mov     edx, 17h
0x180034780  mov     ecx, 401h
0x180034785  call    WPP_SF_q
0x18003478a  mov     al, byte ptr cs:xmmword_180063D60
0x180034790  lea     rbx, aProviders; "Providers"
0x180034797  test    al, 2
0x180034799  jz      short loc_1800347BB
0x18003479b  mov     r9, [rsp+88h+hKey]
0x1800347a0  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800347a7  mov     edx, 19h
0x1800347ac  mov     [rsp+88h+phkResult], rbx
0x1800347b1  mov     ecx, 401h
0x1800347b6  call    WPP_SF_qS
0x1800347bb  mov     rcx, [rsp+88h+hKey]; hKey
0x1800347c0  lea     rax, [rsp+88h+var_48]
0x1800347c5  mov     r9d, 0F003Fh; samDesired
0x1800347cb  mov     [rsp+88h+phkResult], rax; phkResult
0x1800347d0  xor     r8d, r8d; ulOptions
0x1800347d3  mov     rdx, rbx; lpSubKey
0x1800347d6  call    cs:__imp_RegOpenKeyExW
0x1800347dd  nop     dword ptr [rax+rax+00h]
0x1800347e2  mov     ebx, eax
0x1800347e4  test    eax, eax
0x1800347e6  jz      short loc_18003481E
0x1800347e8  mov     ecx, eax
0x1800347ea  cmp     eax, 2
0x1800347ed  jz      short loc_1800347FB
0x1800347ef  lea     rdx, aCouldNotOpenPr; "Could not open providers subkey"
0x1800347f6  jmp     loc_180034A4F
0x1800347fb  lea     rdx, aTheMigrationPr; "The migration providers subkey does not"...
0x180034802  call    LogError
0x180034807  test    byte ptr cs:xmmword_180063D60, 2
0x18003480e  jz      loc_18003495F
0x180034814  mov     edx, 1Bh
0x180034819  jmp     loc_1800348D2
0x18003481e  mov     al, byte ptr cs:xmmword_180063D60
0x180034824  test    al, 2
0x180034826  jz      short loc_180034849
0x180034828  mov     r9, [rsp+88h+var_48]
0x18003482d  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034834  mov     edx, 1Ah
0x180034839  mov     ecx, 401h
0x18003483e  call    WPP_SF_q
0x180034843  mov     al, byte ptr cs:xmmword_180063D60
0x180034849  lea     rbx, aWellKnownGuids; "Well Known Guids"
0x180034850  test    al, 2
0x180034852  jz      short loc_180034874
0x180034854  mov     r9, [rsp+88h+hKey]
0x180034859  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034860  mov     edx, 1Ch
0x180034865  mov     [rsp+88h+phkResult], rbx
0x18003486a  mov     ecx, 401h
0x18003486f  call    WPP_SF_qS
0x180034874  mov     rcx, [rsp+88h+hKey]; hKey
0x180034879  lea     rax, [rsp+88h+var_40]
0x18003487e  mov     r9d, 0F003Fh; samDesired
0x180034884  mov     [rsp+88h+phkResult], rax; phkResult
0x180034889  xor     r8d, r8d; ulOptions
0x18003488c  mov     rdx, rbx; lpSubKey
0x18003488f  call    cs:__imp_RegOpenKeyExW
0x180034896  nop     dword ptr [rax+rax+00h]
0x18003489b  mov     ebx, eax
0x18003489d  test    eax, eax
0x18003489f  jz      short loc_1800348E5
0x1800348a1  mov     ecx, eax
0x1800348a3  cmp     eax, 2
0x1800348a6  jz      short loc_1800348B4
0x1800348a8  lea     rdx, aCouldNotOpenWe; "Could not open well known GUIDs subkey"
0x1800348af  jmp     loc_180034A4F
0x1800348b4  lea     rdx, aTheWellKnownGu; "The well known GUIDs migration subkey d"...
0x1800348bb  call    LogError
0x1800348c0  test    byte ptr cs:xmmword_180063D60, 2
0x1800348c7  jz      loc_18003495F
0x1800348cd  mov     edx, 1Eh
0x1800348d2  mov     ecx, 401h
0x1800348d7  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800348de  call    WPP_SF_
0x1800348e3  jmp     short loc_18003495F
0x1800348e5  test    byte ptr cs:xmmword_180063D60, 2
0x1800348ec  jz      short loc_180034909
0x1800348ee  mov     r9, [rsp+88h+var_40]
0x1800348f3  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800348fa  mov     edx, 1Dh
0x1800348ff  mov     ecx, 401h
0x180034904  call    WPP_SF_q
0x180034909  mov     rcx, [rsp+88h+hKey]
0x18003490e  lea     r8, [rsp+88h+var_58]
0x180034913  lea     rdx, aSetupVersion; "Setup Version"
0x18003491a  call    ReadDword
0x18003491f  mov     ebx, eax
0x180034921  test    eax, eax
0x180034923  jnz     short loc_180034951
0x180034925  test    byte ptr cs:xmmword_180063D60, 2
0x18003492c  jz      short loc_180034942
0x18003492e  mov     r9d, [rsp+88h+var_58]
0x180034933  lea     edx, [rax+1Fh]
0x180034936  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003493d  call    WPP_SF_l
0x180034942  cmp     [rsp+88h+var_58], 1009h
0x18003494a  jnz     short loc_18003495F
0x18003494c  jmp     loc_180034AB9
0x180034951  lea     rdx, aFailedToReadSe; "Failed to read setup version value"
0x180034958  mov     ecx, eax
0x18003495a  call    LogError
0x18003495f  lea     rcx, aWarningCouldNo; "WARNING: Could not parse migration regi"...
0x180034966  call    LogMsg
0x18003496b  test    byte ptr cs:xmmword_180063D60, 2
0x180034972  jz      short loc_18003498A
0x180034974  mov     edx, 20h ; ' '
0x180034979  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034980  mov     ecx, 401h
0x180034985  call    WPP_SF_
0x18003498a  mov     rcx, [rsp+88h+hKey]; hKey
0x18003498f  test    rcx, rcx
0x180034992  jz      short loc_1800349A9
0x180034994  call    cs:__imp_RegCloseKey
0x18003499b  nop     dword ptr [rax+rax+00h]
0x1800349a0  mov     [rsp+88h+hKey], 0
0x1800349a9  mov     rcx, [rsp+88h+var_48]; hKey
0x1800349ae  test    rcx, rcx
0x1800349b1  jz      short loc_1800349EC
0x1800349b3  mov     r8, [rsp+88h+arg_28]
0x1800349bb  mov     rdx, r13
0x1800349be  call    RemoveAllInstalledProviders
0x1800349c3  mov     ebx, eax
0x1800349c5  test    eax, eax
0x1800349c7  jz      short loc_1800349D2
0x1800349c9  lea     rdx, aFailedToRemove_1; "Failed to remove all installed provider"...
0x1800349d0  jmp     short loc_180034A4D
0x1800349d2  mov     rcx, [rsp+88h+var_48]; hKey
0x1800349d7  call    cs:__imp_RegCloseKey
0x1800349de  nop     dword ptr [rax+rax+00h]
0x1800349e3  mov     [rsp+88h+var_48], 0
0x1800349ec  mov     rcx, [rsp+88h+var_40]; hKey
0x1800349f1  test    rcx, rcx
0x1800349f4  jz      short loc_180034A0B
0x1800349f6  call    cs:__imp_RegCloseKey
0x1800349fd  nop     dword ptr [rax+rax+00h]
0x180034a02  mov     [rsp+88h+var_40], 0
0x180034a0b  lea     rdx, aSetupMigration; "Setup Migration"
0x180034a12  mov     rcx, rdi
0x180034a15  call    RecursivelyDeleteRegistryTree
0x180034a1a  mov     ebx, eax
0x180034a1c  test    eax, eax
0x180034a1e  jz      short loc_180034A29
0x180034a20  lea     rdx, aFailedToRecurs_0; "Failed to recursively delete migration "...
0x180034a27  jmp     short loc_180034A4D
0x180034a29  lea     r9, [rsp+88h+var_40]
0x180034a2e  mov     rcx, rdi
0x180034a31  lea     r8, [rsp+88h+var_48]
0x180034a36  lea     rdx, [rsp+88h+hKey]
0x180034a3b  call    CreateDefaultSetupMigrationTree
0x180034a40  mov     ebx, eax
0x180034a42  test    eax, eax
0x180034a44  jz      short loc_180034AAD
0x180034a46  lea     rdx, aFailedToCreate_1; "Failed to create default setup migratio"...
0x180034a4d  mov     ecx, ebx
0x180034a4f  call    LogError
0x180034a54  mov     rcx, [rsp+88h+hKey]; hKey
0x180034a59  test    rcx, rcx
0x180034a5c  jz      short loc_180034A6A
0x180034a5e  call    cs:__imp_RegCloseKey
0x180034a65  nop     dword ptr [rax+rax+00h]
0x180034a6a  mov     rcx, [rsp+88h+var_48]; hKey
0x180034a6f  test    rcx, rcx
0x180034a72  jz      short loc_180034A80
0x180034a74  call    cs:__imp_RegCloseKey
0x180034a7b  nop     dword ptr [rax+rax+00h]
0x180034a80  mov     rcx, [rsp+88h+var_40]; hKey
0x180034a85  test    rcx, rcx
0x180034a88  jz      short loc_180034A96
0x180034a8a  call    cs:__imp_RegCloseKey
0x180034a91  nop     dword ptr [rax+rax+00h]
0x180034a96  mov     qword ptr [r15], 0
0x180034a9d  mov     qword ptr [r14], 0
0x180034aa4  mov     qword ptr [rsi], 0
0x180034aab  jmp     short loc_180034AD1
0x180034aad  lea     rcx, aSuccessfullyCr; "Successfully created default setup migr"...
0x180034ab4  call    LogMsg
0x180034ab9  mov     rax, [rsp+88h+hKey]
0x180034abe  mov     [r15], rax
0x180034ac1  mov     rax, [rsp+88h+var_48]
0x180034ac6  mov     [r14], rax
0x180034ac9  mov     rax, [rsp+88h+var_40]
0x180034ace  mov     [rsi], rax
0x180034ad1  mov     eax, ebx
0x180034ad3  add     rsp, 58h
0x180034ad7  pop     r15
0x180034ad9  pop     r14
0x180034adb  pop     r13
0x180034add  pop     rdi
0x180034ade  pop     rsi
0x180034adf  pop     rbx
0x180034ae0  retn
```
