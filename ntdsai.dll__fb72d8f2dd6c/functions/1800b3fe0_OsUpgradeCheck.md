# OsUpgradeCheck

- ea: `0x1800b3fe0`
- end: `0x1800b48a9`
- name: `OsUpgradeCheck`
- size: `2249`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800a504c`

## callees

- `0x180006360`
- `0x18000bb80`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180022da4`
- `0x1800b32ec`
- `0x1800b3c48`
- `0x1800b3ca0`
- `0x1800b3fe0`
- `0x18016ffe8`
- `0x1801705ec`
- `0x180170da4`
- `0x180172a88`
- `0x180180c50`
- `0x180181460`
- `0x18042abe4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800b477e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x1800b477e`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800b4751`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800b4767`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800b4751`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800b4767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b43b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b43b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b446a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4216`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b446a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b426a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b44e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b45ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b426a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b44e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b45ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b45f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b45f2`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b417c`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b41e0`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b417c`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b41e0`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4850`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4865`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4850`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b4865`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b425d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b44a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4521`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b425d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b44a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b4521`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b43a8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b46ea`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b43a8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b46ea`
- `ntdll!RtlAdjustPrivilege` at `0x1800b411b`
- `ntdll!RtlAdjustPrivilege` at `0x1800b4880`
- `ntdll!RtlAdjustPrivilege` at `0x1800b411b`
- `ntdll!RtlAdjustPrivilege` at `0x1800b4880`
- `CRYPTBASE!SystemFunction036` at `0x1800b433b`
- `CRYPTBASE!SystemFunction036` at `0x1800b433b`

## string_xrefs

- `0x1800b40d7`: `SYSTEM\CurrentControlSet\Services\NetLogon\Parameters`
- `0x1800b4677`: `SYSTEM\CurrentControlSet\Services\NetLogon\Parameters`
- `0x1800b4133`: `Windows.old`
- `0x1800b419a`: `Windows.old`
- `0x1800b413a`: `%c:\%ws\Windows\System32\config\SOFTWARE`
- `0x1800b41a1`: `%c:\%ws\Windows\SYSTEM32\CONFIG\SYSTEM`
- `0x1800b4286`: `OLD_SYSTEM\ControlSet%03d\Services\NetLogon\Parameters`
- `0x1800b4400`: `TempSysvolPath`
- `0x1800b46b4`: `TempSysvolPath`
- `0x1800b46cd`: `TempSysvolPath`
- `0x1800b44a1`: `PendingFileRenameOperations`
- `0x1800b451a`: `PendingFileRenameOperations`
- `0x1800b45c4`: `PendingFileRenameOperations`

## pseudocode

```c
NTSTATUS OsUpgradeCheck()
{
  NTSTATUS result; // eax
  int v1; // esi
  unsigned int v2; // ebx
  int v3; // r12d
  BYTE *v4; // r14
  int v5; // r13d
  unsigned int v6; // edi
  int v7; // esi
  bool v8; // zf
  int v9; // esi
  unsigned int i; // edi
  __int64 v11; // rdi
  __int64 v12; // rsi
  int v13; // r15d
  LSTATUS v14; // ebx
  DWORD v15; // ecx
  DWORD v16; // ebx
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  DWORD v19; // ebx
  __int64 v20; // rcx
  int v21; // ebx
  __int64 v22; // rcx
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned __int8 OldValue[4]; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v25; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v26[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  _DWORD RandomBuffer[3]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+88h] [rbp-78h]
  DWORD Offset; // [rsp+8Ch] [rbp-74h]
  __int64 v35; // [rsp+90h] [rbp-70h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A4h] [rbp-5Ch]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C0h] [rbp-40h]
  int v43; // [rsp+C8h] [rbp-38h]
  __int64 v44; // [rsp+CCh] [rbp-34h]
  int v45; // [rsp+D4h] [rbp-2Ch]
  char *v46; // [rsp+D8h] [rbp-28h]
  __int64 v47[4]; // [rsp+E0h] [rbp-20h] BYREF
  char v48; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v49[24]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v50[24]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v51[32]; // [rsp+350h] [rbp+250h] BYREF
  wchar_t pszDest[264]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR v53[264]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR NewFileName[264]; // [rsp+790h] [rbp+690h] BYREF
  wchar_t Src[264]; // [rsp+9A0h] [rbp+8A0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+BB0h] [rbp+AB0h] BYREF

  memset_0(v53, 0, 0x20Au);
  *(_DWORD *)Data = 0;
  hKey = 0;
  *(_DWORD *)v26 = 0;
  Type = 0;
  cbData = 4;
  v25 = 0;
  OldValue[0] = 0;
  if ( !(unsigned int)IsSetupRunning() )
  {
    result = GetConfigParamLocalWEx(L"UpgradeCheck", v26, 4u, 0);
    if ( result || !*(_DWORD *)v26 )
      return result;
    DeleteConfigParamW(L"UpgradeCheck");
    v9 = 0;
    v3 = 0;
    v4 = 0;
    v5 = 0;
    goto LABEL_75;
  }
  result = IsSystemUpgradeInProgress();
  if ( result )
  {
    if ( (unsigned int)GetConfigParamLocalWEx(L"UpgradeCheck", v26, 4u, 0) || (v1 = 2, !*(_DWORD *)v26) )
      v1 = 1;
    *(_DWORD *)v26 = v1;
    result = SetConfigParamW((__int64)L"UpgradeCheck", 4, (__int64)v26, 4);
    v2 = result;
  }
  else
  {
    v1 = 0;
    v2 = 0;
  }
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = v1 - 1;
  if ( v7 )
  {
    v8 = v7 == 2;
    v9 = 0;
    if ( !v8 )
      goto LABEL_83;
LABEL_75:
    result = GetSysvolPath(L"SYSTEM\\CurrentControlSet\\Services\\NetLogon\\Parameters", (LPBYTE)v53);
    v2 = result;
    if ( result )
    {
      v6 = 50340978;
    }
    else
    {
      result = IsDirectoryExist(v53);
      if ( result )
        return result;
      result = GetConfigParamLocalWEx(L"TempSysvolPath", (LPBYTE)ExistingFileName, 0x20Au, 0);
      v2 = result;
      if ( !result )
      {
        DeleteConfigParamW(L"TempSysvolPath");
        result = MoveFileExW(ExistingFileName, v53, 0);
        if ( result )
          return result;
        result = GetLastError();
        v6 = 50341005;
LABEL_82:
        v2 = result;
LABEL_83:
        if ( !v2 )
          goto LABEL_87;
        goto LABEL_84;
      }
      v6 = 50340994;
    }
LABEL_84:
    if ( gpDsEventConfig )
    {
      v47[0] = (__int64)v51;
      v47[1] = (__int64)v50;
      v47[2] = (__int64)v49;
      _o__itow_s(v2, v50, 12);
      _o__itow_s(v2, v51, 12);
      _o__ultow_s(v6, v49, 9, 16);
      DoLogEventW(768, gpDsEventConfig[4].Offset, 0, -1073740656, 1, 3u, (__int64)v47, 0, 0);
      result = (int)gpDsEventConfig;
      if ( gpDsEventConfig )
      {
        Offset = gpDsEventConfig[7].Offset;
        v35 = 0;
        v41 = 0;
        v44 = 0;
        v45 = 0;
        v46 = &v48;
        v32 = 0;
        v33 = -1073740656;
        v36 = 0;
        v40 = 0;
        v39 = 768;
        v37 = 1;
        v38 = 1;
        v42 = 0;
        v43 = 0;
        result = DoLogEventAndTrace(&v32);
      }
    }
LABEL_87:
    if ( !v4 )
      goto LABEL_89;
    goto LABEL_88;
  }
  result = GetSysvolPath(L"SYSTEM\\CurrentControlSet\\Services\\NetLogon\\Parameters", (LPBYTE)v53);
  v2 = result;
  if ( result )
  {
    v6 = 50340672;
LABEL_13:
    v9 = 0;
    goto LABEL_84;
  }
  result = IsDirectoryExist(v53);
  if ( result )
    return result;
  v9 = 1;
  result = RtlAdjustPrivilege(0x12u, 1u, 0, OldValue);
  v2 = result;
  if ( result < 0 )
  {
    v6 = 50340698;
    goto LABEL_13;
  }
  v5 = 1;
  result = StringCchPrintfW(pszDest, 0x105u, L"%c:\\%ws\\Windows\\System32\\config\\SOFTWARE", v53[0], L"Windows.old");
  v2 = result;
  if ( result )
  {
    v6 = 50340718;
    goto LABEL_13;
  }
  result = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"OLD_SOFTWARE", pszDest);
  v2 = result;
  if ( result )
  {
    v6 = 50340723;
    goto LABEL_13;
  }
  result = StringCchPrintfW(pszDest, 0x105u, L"%c:\\%ws\\Windows\\SYSTEM32\\CONFIG\\SYSTEM", v53[0], L"Windows.old");
  v2 = result;
  if ( result )
    goto LABEL_84;
  result = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"OLD_SYSTEM", pszDest);
  v2 = result;
  if ( result )
  {
    v6 = 50340744;
    goto LABEL_84;
  }
  v3 = 1;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"OLD_SYSTEM\\Select", 0, 0x20019u, &hKey);
  v2 = result;
  if ( result )
  {
    v6 = 50340761;
    goto LABEL_84;
  }
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"Current", 0, &Type, Data, &cbData);
  result = RegCloseKey(hKey);
  if ( v2 )
  {
    v6 = 50340778;
LABEL_27:
    v9 = 1;
    goto LABEL_84;
  }
  result = StringCchPrintfW(
             pszDest,
             0x105u,
             L"OLD_SYSTEM\\ControlSet%03d\\Services\\NetLogon\\Parameters",
             *(unsigned int *)Data);
  v2 = result;
  if ( result )
  {
    v6 = 50340792;
    goto LABEL_27;
  }
  result = GetSysvolPath(pszDest, (LPBYTE)Src);
  v2 = result;
  if ( result )
  {
    v6 = 50340799;
    goto LABEL_27;
  }
  if ( !(unsigned int)MapDirNameToTempDirName(Src, ExistingFileName)
    || !(unsigned int)IsDirectoryExist(ExistingFileName) )
  {
    goto LABEL_90;
  }
  for ( i = 0; ; ++i )
  {
    if ( i )
    {
      RandomBuffer[0] = 0;
      SystemFunction036(RandomBuffer, 4u);
      LODWORD(lpcbData) = RandomBuffer[0];
      result = StringCchPrintfW(NewFileName, 0x105u, L"%c:\\%ws%d", Src[0], L"$SYSVOL.~SAVE", lpcbData);
    }
    else
    {
      result = StringCchPrintfW(NewFileName, 0x105u, L"%c:\\%ws", Src[0], L"$SYSVOL.~SAVE");
    }
    v4 = 0;
    v2 = result;
    if ( result )
    {
      v6 = 50340847;
      goto LABEL_27;
    }
    if ( !(unsigned int)IsDirectoryExist(NewFileName) || i >= 0x64 )
      break;
  }
  if ( !MoveFileExW(ExistingFileName, NewFileName, 0) )
  {
    result = GetLastError();
    v6 = 50340858;
    v9 = 1;
    goto LABEL_82;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( NewFileName[v12] );
  do
    ++v11;
  while ( Src[v11] );
  v13 = 2 * v12;
  result = SetConfigParamW((__int64)L"TempSysvolPath", 1, (__int64)NewFileName, 2 * (unsigned __int8)v12 + 2);
  v2 = result;
  if ( result )
  {
    v6 = 50340871;
LABEL_59:
    v9 = 1;
    goto LABEL_84;
  }
  result = StringCchPrintfW(
             pszDest,
             0x105u,
             L"OLD_SYSTEM\\ControlSet%03d\\Control\\Session Manager",
             *(unsigned int *)Data);
  v2 = result;
  if ( result )
  {
    v6 = 50340886;
    goto LABEL_59;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2000000u, &hKey);
  v2 = result;
  if ( result )
  {
    v6 = 50340892;
    goto LABEL_59;
  }
  v25 = 0;
  v14 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, 0, &v25);
  if ( v14 )
  {
    v15 = 0;
    v25 = 0;
  }
  else
  {
    v15 = v25;
  }
  v4 = (BYTE *)DSAllocAux(v15 + 2 * ((_DWORD)v12 + (_DWORD)v11) + 20, 50340904);
  if ( !v4 )
  {
    v2 = 14;
    v6 = 50340908;
LABEL_58:
    result = RegCloseKey(hKey);
    goto LABEL_59;
  }
  if ( v14 )
  {
    v16 = v25;
  }
  else
  {
    v2 = RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, &Type, v4, &v25);
    if ( v2 )
    {
      v6 = 50340917;
      goto LABEL_58;
    }
    v16 = v25;
    if ( v25 >= 4 )
    {
      v17 = (unsigned __int64)v25 >> 1;
      if ( !*(_WORD *)&v4[2 * v17 - 4] && !*(_WORD *)&v4[2 * v17 - 2] )
      {
        v16 = v25 - 2;
        v25 -= 2;
      }
    }
  }
  v18 = v16;
  v19 = v16 + 8;
  *(_QWORD *)&v4[v18] = 0x5C003F003F005CLL;
  memcpy_0(&v4[v19], NewFileName, 2LL * (unsigned int)(v12 + 1));
  v20 = v13 + v19 + 2;
  *(_QWORD *)&v4[v20] = 0x5C003F003F005CLL;
  v21 = v20 + 8;
  memcpy_0(&v4[(unsigned int)(v20 + 8)], Src, 2LL * (unsigned int)(v11 + 1));
  v22 = (unsigned int)(v13 + v21 + 2);
  v4[v22] = 0;
  LODWORD(v22) = v22 + 1;
  v4[(unsigned int)v22] = 0;
  Type = 7;
  v2 = RegSetValueExW(hKey, L"PendingFileRenameOperations", 0, 7u, v4, v22 + 1);
  result = RegCloseKey(hKey);
  v9 = 1;
  if ( v2 )
  {
    v6 = 50340956;
    goto LABEL_84;
  }
LABEL_88:
  result = DSFreeAux(v4, 50341026);
LABEL_89:
  if ( v9 )
LABEL_90:
    result = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"OLD_SOFTWARE");
  if ( v3 )
    result = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"OLD_SYSTEM");
  if ( v5 )
    return RtlAdjustPrivilege(0x12u, OldValue[0], 0, OldValue);
  return result;
}

```

## disassembly

```asm
0x1800b3fe0  push    rbp
0x1800b3fe2  push    rbx
0x1800b3fe3  push    rsi
0x1800b3fe4  push    rdi
0x1800b3fe5  push    r12
0x1800b3fe7  push    r13
0x1800b3fe9  push    r14
0x1800b3feb  push    r15
0x1800b3fed  lea     rbp, [rsp-0CD8h]
0x1800b3ff5  sub     rsp, 0DD8h
0x1800b3ffc  mov     rax, cs:__security_cookie
0x1800b4003  xor     rax, rsp
0x1800b4006  mov     [rbp+0D10h+var_50], rax
0x1800b400d  xor     edx, edx; Val
0x1800b400f  lea     rcx, [rbp+0D10h+var_890]; void *
0x1800b4016  mov     r8d, 20Ah; Size
0x1800b401c  call    memset_0
0x1800b4021  xor     r15d, r15d
0x1800b4024  mov     dword ptr [rsp+0E10h+Data], r15d
0x1800b4029  mov     [rsp+0E10h+hKey], r15
0x1800b402e  mov     dword ptr [rsp+0E10h+var_DB4], r15d
0x1800b4033  lea     ebx, [r15+4]
0x1800b4037  mov     [rsp+0E10h+Type], r15d
0x1800b403c  mov     [rsp+0E10h+cbData], ebx
0x1800b4040  mov     [rsp+0E10h+var_DB8], r15d
0x1800b4045  mov     [rsp+0E10h+OldValue], r15b
0x1800b404a  call    IsSetupRunning
0x1800b404f  test    eax, eax
0x1800b4051  jz      loc_1800B462E
0x1800b4057  call    IsSystemUpgradeInProgress
0x1800b405c  test    eax, eax
0x1800b405e  jz      short loc_1800B40A8
0x1800b4060  xor     r9d, r9d
0x1800b4063  lea     rdx, [rsp+0E10h+var_DB4]; lpData
0x1800b4068  mov     r8d, ebx
0x1800b406b  lea     rcx, aUpgradecheck; "UpgradeCheck"
0x1800b4072  call    GetConfigParamLocalWEx
0x1800b4077  test    eax, eax
0x1800b4079  jnz     short loc_1800B4085
0x1800b407b  lea     esi, [rbx-2]
0x1800b407e  cmp     dword ptr [rsp+0E10h+var_DB4], r15d
0x1800b4083  jnz     short loc_1800B408A
0x1800b4085  mov     esi, 1
0x1800b408a  mov     r9d, ebx; char
0x1800b408d  mov     dword ptr [rsp+0E10h+var_DB4], esi
0x1800b4091  lea     r8, [rsp+0E10h+var_DB4]; __int64
0x1800b4096  mov     edx, ebx; char
0x1800b4098  lea     rcx, aUpgradecheck; "UpgradeCheck"
0x1800b409f  call    SetConfigParamW
0x1800b40a4  mov     ebx, eax
0x1800b40a6  jmp     short loc_1800B40AE
0x1800b40a8  mov     esi, r15d
0x1800b40ab  mov     ebx, r15d
0x1800b40ae  mov     r12d, r15d
0x1800b40b1  mov     r14, r15
0x1800b40b4  mov     r13d, r15d
0x1800b40b7  mov     edi, r15d
0x1800b40ba  sub     esi, 1
0x1800b40bd  jz      short loc_1800B40D0
0x1800b40bf  cmp     esi, 2
0x1800b40c2  mov     esi, r15d
0x1800b40c5  jz      loc_1800B4670
0x1800b40cb  jmp     loc_1800B4705
0x1800b40d0  lea     rdx, [rbp+0D10h+var_890]; lpData
0x1800b40d7  lea     rcx, aSystemCurrentc_9; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800b40de  call    GetSysvolPath
0x1800b40e3  mov     ebx, eax
0x1800b40e5  test    eax, eax
0x1800b40e7  jz      short loc_1800B40F6
0x1800b40e9  mov     edi, 3002340h
0x1800b40ee  mov     esi, r15d
0x1800b40f1  jmp     loc_1800B470D
0x1800b40f6  lea     rcx, [rbp+0D10h+var_890]
0x1800b40fd  call    IsDirectoryExist
0x1800b4102  test    eax, eax
0x1800b4104  jnz     loc_1800B4886
0x1800b410a  lea     esi, [rax+1]
0x1800b410d  xor     r8d, r8d; ForThread
0x1800b4110  mov     dl, sil; NewValue
0x1800b4113  lea     r9, [rsp+0E10h+OldValue]; OldValue
0x1800b4118  lea     ecx, [rax+12h]; Privilege
0x1800b411b  call    cs:__imp_RtlAdjustPrivilege
0x1800b4121  mov     ebx, eax
0x1800b4123  test    eax, eax
0x1800b4125  js      loc_1800B4624
0x1800b412b  movzx   r9d, [rbp+0D10h+var_890]
0x1800b4133  lea     rax, aWindowsOld; "Windows.old"
0x1800b413a  lea     r8, aCWsWindowsSyst; "%c:\\%ws\\Windows\\System32\\config\\SO"...
0x1800b4141  mov     [rsp+0E10h+phkResult], rax
0x1800b4146  mov     edx, 105h; cchDest
0x1800b414b  lea     rcx, [rbp+0D10h+pszDest]; pszDest
0x1800b4152  mov     r13d, esi
0x1800b4155  call    StringCchPrintfW
0x1800b415a  mov     ebx, eax
0x1800b415c  test    eax, eax
0x1800b415e  jz      short loc_1800B4167
0x1800b4160  mov     edi, 300236Eh
0x1800b4165  jmp     short loc_1800B40EE
0x1800b4167  lea     r8, [rbp+0D10h+pszDest]; lpFile
0x1800b416e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4175  lea     rdx, aOldSoftware; "OLD_SOFTWARE"
0x1800b417c  call    cs:__imp_RegLoadKeyW
0x1800b4182  mov     ebx, eax
0x1800b4184  test    eax, eax
0x1800b4186  jz      short loc_1800B4192
0x1800b4188  mov     edi, 3002373h
0x1800b418d  jmp     loc_1800B40EE
0x1800b4192  movzx   r9d, [rbp+0D10h+var_890]
0x1800b419a  lea     rax, aWindowsOld; "Windows.old"
0x1800b41a1  lea     r8, aCWsWindowsSyst_0; "%c:\\%ws\\Windows\\SYSTEM32\\CONFIG\\SY"...
0x1800b41a8  mov     [rsp+0E10h+phkResult], rax
0x1800b41ad  mov     edx, 105h; cchDest
0x1800b41b2  lea     rcx, [rbp+0D10h+pszDest]; pszDest
0x1800b41b9  call    StringCchPrintfW
0x1800b41be  mov     ebx, eax
0x1800b41c0  test    eax, eax
0x1800b41c2  jnz     loc_1800B470D
0x1800b41c8  mov     rdi, 0FFFFFFFF80000002h
0x1800b41cf  lea     r8, [rbp+0D10h+pszDest]; lpFile
0x1800b41d6  mov     rcx, rdi; hKey
0x1800b41d9  lea     rdx, aOldSystem; "OLD_SYSTEM"
0x1800b41e0  call    cs:__imp_RegLoadKeyW
0x1800b41e6  mov     ebx, eax
0x1800b41e8  test    eax, eax
0x1800b41ea  jz      short loc_1800B41F6
0x1800b41ec  mov     edi, 3002388h
0x1800b41f1  jmp     loc_1800B470D
0x1800b41f6  lea     rax, [rsp+0E10h+hKey]
0x1800b41fb  mov     r9d, 20019h; samDesired
0x1800b4201  xor     r8d, r8d; ulOptions
0x1800b4204  mov     [rsp+0E10h+phkResult], rax; phkResult
0x1800b4209  lea     rdx, aOldSystemSelec; "OLD_SYSTEM\\Select"
0x1800b4210  mov     rcx, rdi; hKey
0x1800b4213  mov     r12d, esi
0x1800b4216  call    cs:__imp_RegOpenKeyExW
0x1800b421c  mov     ebx, eax
0x1800b421e  test    eax, eax
0x1800b4220  jz      short loc_1800B422C
0x1800b4222  mov     edi, 3002399h
0x1800b4227  jmp     loc_1800B470D
0x1800b422c  mov     rcx, [rsp+0E10h+hKey]; hKey
0x1800b4231  lea     rax, [rsp+0E10h+cbData]
0x1800b4236  mov     [rsp+0E10h+lpcbData], rax; lpcbData
0x1800b423b  lea     r9, [rsp+0E10h+Type]; lpType
0x1800b4240  lea     rax, [rsp+0E10h+Data]
0x1800b4245  mov     esi, 4
0x1800b424a  xor     r8d, r8d; lpReserved
0x1800b424d  mov     [rsp+0E10h+phkResult], rax; lpData
0x1800b4252  lea     rdx, aCurrent; "Current"
0x1800b4259  mov     [rsp+0E10h+cbData], esi
0x1800b425d  call    cs:__imp_RegQueryValueExW
0x1800b4263  mov     rcx, [rsp+0E10h+hKey]; hKey
0x1800b4268  mov     ebx, eax
0x1800b426a  call    cs:__imp_RegCloseKey
0x1800b4270  test    ebx, ebx
0x1800b4272  jz      short loc_1800B4281
0x1800b4274  mov     edi, 30023AAh
0x1800b4279  mov     esi, r12d
0x1800b427c  jmp     loc_1800B470D
0x1800b4281  mov     r9d, dword ptr [rsp+0E10h+Data]
0x1800b4286  lea     r8, aOldSystemContr_0; "OLD_SYSTEM\\ControlSet%03d\\Services\\N"...
0x1800b428d  mov     edx, 105h; cchDest
0x1800b4292  lea     rcx, [rbp+0D10h+pszDest]; pszDest
0x1800b4299  call    StringCchPrintfW
0x1800b429e  mov     ebx, eax
0x1800b42a0  test    eax, eax
0x1800b42a2  jz      short loc_1800B42AB
0x1800b42a4  mov     edi, 30023B8h
0x1800b42a9  jmp     short loc_1800B4279
0x1800b42ab  lea     rdx, [rbp+0D10h+Src]; lpData
0x1800b42b2  lea     rcx, [rbp+0D10h+pszDest]; lpSubKey
0x1800b42b9  call    GetSysvolPath
0x1800b42be  mov     ebx, eax
0x1800b42c0  test    eax, eax
0x1800b42c2  jz      short loc_1800B42CB
0x1800b42c4  mov     edi, 30023BFh
0x1800b42c9  jmp     short loc_1800B4279
0x1800b42cb  lea     rdx, [rbp+0D10h+ExistingFileName]; pszDest
0x1800b42d2  lea     rcx, [rbp+0D10h+Src]; Str
0x1800b42d9  call    MapDirNameToTempDirName
0x1800b42de  test    eax, eax
0x1800b42e0  jz      loc_1800B4846
0x1800b42e6  lea     rcx, [rbp+0D10h+ExistingFileName]
0x1800b42ed  call    IsDirectoryExist
0x1800b42f2  test    eax, eax
0x1800b42f4  jz      loc_1800B4846
0x1800b42fa  mov     edi, r15d
0x1800b42fd  lea     rbx, aSysvolSave; "$SYSVOL.~SAVE"
0x1800b4304  test    edi, edi
0x1800b4306  jnz     short loc_1800B432F
0x1800b4308  movzx   r9d, [rbp+0D10h+Src]
0x1800b4310  lea     r8, aCWs; "%c:\\%ws"
0x1800b4317  mov     edx, 105h; cchDest
0x1800b431c  mov     [rsp+0E10h+phkResult], rbx
0x1800b4321  lea     rcx, [rbp+0D10h+NewFileName]; pszDest
0x1800b4328  call    StringCchPrintfW
0x1800b432d  jmp     short loc_1800B436E
0x1800b432f  mov     edx, esi; RandomBufferLength
0x1800b4331  mov     [rsp+0E10h+RandomBuffer], r15d
0x1800b4336  lea     rcx, [rsp+0E10h+RandomBuffer]; RandomBuffer
0x1800b433b  call    cs:__imp_SystemFunction036
0x1800b4341  mov     eax, [rsp+0E10h+RandomBuffer]
0x1800b4345  lea     r8, aCWsD; "%c:\\%ws%d"
0x1800b434c  movzx   r9d, [rbp+0D10h+Src]
0x1800b4354  lea     rcx, [rbp+0D10h+NewFileName]; pszDest
0x1800b435b  mov     dword ptr [rsp+0E10h+lpcbData], eax
0x1800b435f  mov     edx, 105h; cchDest
0x1800b4364  mov     [rsp+0E10h+phkResult], rbx
0x1800b4369  call    StringCchPrintfW
0x1800b436e  mov     r14, r15
0x1800b4371  mov     ebx, eax
0x1800b4373  test    eax, eax
0x1800b4375  jnz     loc_1800B461A
0x1800b437b  lea     rcx, [rbp+0D10h+NewFileName]
0x1800b4382  call    IsDirectoryExist
0x1800b4387  test    eax, eax
0x1800b4389  jz      short loc_1800B4397
0x1800b438b  cmp     edi, 64h ; 'd'
0x1800b438e  jnb     short loc_1800B4397
0x1800b4390  inc     edi
0x1800b4392  jmp     loc_1800B42FD
0x1800b4397  xor     r8d, r8d; dwFlags
0x1800b439a  lea     rdx, [rbp+0D10h+NewFileName]; lpNewFileName
0x1800b43a1  lea     rcx, [rbp+0D10h+ExistingFileName]; lpExistingFileName
0x1800b43a8  call    cs:__imp_MoveFileExW
0x1800b43ae  test    eax, eax
0x1800b43b0  jnz     short loc_1800B43C5
0x1800b43b2  call    cs:__imp_GetLastError
0x1800b43b8  mov     edi, 30023FAh
0x1800b43bd  mov     esi, r12d
0x1800b43c0  jmp     loc_1800B4703
0x1800b43c5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b43c9  lea     rax, [rbp+0D10h+NewFileName]
0x1800b43d0  mov     rsi, rdi
0x1800b43d3  inc     rsi
0x1800b43d6  cmp     [rax+rsi*2], r15w
0x1800b43db  jnz     short loc_1800B43D3
0x1800b43dd  lea     rax, [rbp+0D10h+Src]
0x1800b43e4  inc     rdi
0x1800b43e7  cmp     [rax+rdi*2], r15w
0x1800b43ec  jnz     short loc_1800B43E4
0x1800b43ee  lea     r15d, [rsi+rsi]
0x1800b43f2  mov     edx, r12d; char
0x1800b43f5  lea     r9d, [r15+2]; char
0x1800b43f9  lea     r8, [rbp+0D10h+NewFileName]; __int64
0x1800b4400  lea     rcx, aTempsysvolpath; "TempSysvolPath"
0x1800b4407  call    SetConfigParamW
0x1800b440c  mov     ebx, eax
0x1800b440e  test    eax, eax
0x1800b4410  jz      short loc_1800B441C
0x1800b4412  mov     edi, 3002407h
0x1800b4417  jmp     loc_1800B44EF
0x1800b441c  mov     r9d, dword ptr [rsp+0E10h+Data]
0x1800b4421  lea     r8, aOldSystemContr; "OLD_SYSTEM\\ControlSet%03d\\Control\\Se"...
0x1800b4428  mov     edx, 105h; cchDest
0x1800b442d  lea     rcx, [rbp+0D10h+pszDest]; pszDest
0x1800b4434  call    StringCchPrintfW
0x1800b4439  mov     ebx, eax
0x1800b443b  test    eax, eax
0x1800b443d  jz      short loc_1800B4449
0x1800b443f  mov     edi, 3002416h
0x1800b4444  jmp     loc_1800B44EF
0x1800b4449  lea     rax, [rsp+0E10h+hKey]
0x1800b444e  mov     r9d, 2000000h; samDesired
0x1800b4454  xor     r8d, r8d; ulOptions
0x1800b4457  mov     [rsp+0E10h+phkResult], rax; phkResult
0x1800b445c  lea     rdx, [rbp+0D10h+pszDest]; lpSubKey
0x1800b4463  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b446a  call    cs:__imp_RegOpenKeyExW
0x1800b4470  mov     ebx, eax
0x1800b4472  test    eax, eax
0x1800b4474  jz      short loc_1800B447D
0x1800b4476  mov     edi, 300241Ch
0x1800b447b  jmp     short loc_1800B44EF
0x1800b447d  mov     rcx, [rsp+0E10h+hKey]; hKey
0x1800b4482  lea     rax, [rsp+0E10h+var_DB8]
0x1800b4487  xor     r14d, r14d
0x1800b448a  mov     [rsp+0E10h+lpcbData], rax; lpcbData
0x1800b448f  lea     r9, [rsp+0E10h+Type]; lpType
0x1800b4494  mov     [rsp+0E10h+phkResult], r14; lpData
0x1800b4499  xor     r8d, r8d; lpReserved
0x1800b449c  mov     [rsp+0E10h+var_DB8], r14d
0x1800b44a1  lea     rdx, aPendingfileren; "PendingFileRenameOperations"
0x1800b44a8  call    cs:__imp_RegQueryValueExW
0x1800b44ae  mov     ebx, eax
0x1800b44b0  test    eax, eax
0x1800b44b2  jz      short loc_1800B44BD
0x1800b44b4  mov     ecx, r14d
0x1800b44b7  mov     [rsp+0E10h+var_DB8], ecx
0x1800b44bb  jmp     short loc_1800B44C1
0x1800b44bd  mov     ecx, [rsp+0E10h+var_DB8]
0x1800b44c1  lea     eax, [rsi+rdi]
0x1800b44c4  mov     edx, 3002428h
0x1800b44c9  lea     ecx, [rcx+rax*2]
0x1800b44cc  add     ecx, 14h
0x1800b44cf  call    DSAllocAux
0x1800b44d4  mov     r14, rax
0x1800b44d7  test    rax, rax
0x1800b44da  jnz     short loc_1800B44FA
0x1800b44dc  lea     ebx, [rax+0Eh]
  ... truncated ...
```
