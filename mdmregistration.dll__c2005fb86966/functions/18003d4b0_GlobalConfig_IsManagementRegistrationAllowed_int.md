# GlobalConfig::IsManagementRegistrationAllowed(int *)

- ea: `0x18003d4b0`
- end: `0x18003d693`
- name: `?IsManagementRegistrationAllowed@GlobalConfig@@QEBAJPEAH@Z`
- size: `483`
- prototype: `__int64 __fastcall(GlobalConfig *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3e0`

## callees

- `0x18003cd7c`
- `0x18003d170`
- `0x18003d4b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d55d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d601`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d55d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003d601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d679`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d510`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d510`

## pseudocode

```c
__int64 __fastcall GlobalConfig::IsManagementRegistrationAllowed(GlobalConfig *this, int *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS ValueW; // eax
  BOOL v6; // r14d
  const WCHAR *EnrollmentsRootKey; // rax
  LSTATUS v8; // eax
  BOOL v9; // edi
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-8h] BYREF
  GlobalConfig *pvData; // [rsp+80h] [rbp+30h] BYREF
  int v14; // [rsp+88h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD v16; // [rsp+98h] [rbp+48h] BYREF

  pvData = this;
  if ( !a2 )
    return (unsigned int)-2147024809;
  *a2 = 1;
  LODWORD(pvData) = 0;
  pcbData = 4;
  hkey = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\MDM",
         0,
         0x20119u,
         &hkey);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"DisableRegistration", 0x18u, 0, &pvData, &pcbData);
    v3 = ValueW;
    if ( ValueW > 0 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v3 == -2147024894 || v3 == -2147023267 )
  {
    v6 = 0;
LABEL_13:
    v14 = 0;
    v16 = 4;
    hKey = 0;
    EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
    v3 = EEDBManager::OpenHKEY(EnrollmentsRootKey, 0x20019u, &hKey);
    if ( v3 >= 0 )
    {
      v8 = RegGetValueW(hKey, 0, L"ExternallyManaged", 0x18u, 0, &v14, &v16);
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
    }
    if ( v3 == -2147024894 || v3 == -2147023267 )
    {
      v9 = 0;
      v3 = 0;
    }
    else
    {
      v9 = 1;
      if ( v3 >= 0 )
        v9 = v14 != 0;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v3 >= 0 )
      *a2 = !v6 && !v9;
    goto LABEL_28;
  }
  if ( v3 >= 0 )
  {
    v6 = (_DWORD)pvData != 0;
    goto LABEL_13;
  }
LABEL_28:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003d4b0  mov     [rsp-28h+arg_0], rcx
0x18003d4b5  push    rbp
0x18003d4b6  push    rbx
0x18003d4b7  push    rsi
0x18003d4b8  push    rdi
0x18003d4b9  push    r14
0x18003d4bb  mov     rbp, rsp
0x18003d4be  sub     rsp, 50h
0x18003d4c2  mov     rsi, rdx
0x18003d4c5  test    rdx, rdx
0x18003d4c8  jnz     short loc_18003D4D4
0x18003d4ca  mov     ebx, 80070057h
0x18003d4cf  jmp     loc_18003D685
0x18003d4d4  mov     dword ptr [rdx], 1
0x18003d4da  lea     rax, [rbp+hkey]
0x18003d4de  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18003d4e5  mov     [rsp+50h+phkResult], rax; phkResult
0x18003d4ea  mov     r9d, 20119h; samDesired
0x18003d4f0  mov     dword ptr [rbp+arg_0], 0
0x18003d4f7  xor     r8d, r8d; ulOptions
0x18003d4fa  mov     [rbp+arg_10], 4
0x18003d501  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d508  mov     [rbp+hkey], 0
0x18003d510  call    cs:__imp_RegOpenKeyExW
0x18003d517  nop     dword ptr [rax+rax+00h]
0x18003d51c  mov     ebx, eax
0x18003d51e  test    eax, eax
0x18003d520  jle     short loc_18003D52B
0x18003d522  movzx   ebx, ax
0x18003d525  or      ebx, 80070000h
0x18003d52b  test    ebx, ebx
0x18003d52d  js      short loc_18003D578
0x18003d52f  mov     rcx, [rbp+hkey]; hkey
0x18003d533  lea     rax, [rbp+arg_10]
0x18003d537  mov     [rsp+50h+pcbData], rax; pcbData
0x18003d53c  lea     r8, aDisableregistr; "DisableRegistration"
0x18003d543  lea     rax, [rbp+arg_0]
0x18003d547  mov     r9d, 18h; dwFlags
0x18003d54d  mov     [rsp+50h+pvData], rax; pvData
0x18003d552  xor     edx, edx; lpSubKey
0x18003d554  mov     [rsp+50h+phkResult], 0; pdwType
0x18003d55d  call    cs:__imp_RegGetValueW
0x18003d564  nop     dword ptr [rax+rax+00h]
0x18003d569  mov     ebx, eax
0x18003d56b  test    eax, eax
0x18003d56d  jle     short loc_18003D578
0x18003d56f  movzx   ebx, ax
0x18003d572  or      ebx, 80070000h
0x18003d578  mov     edi, 8007065Dh
0x18003d57d  cmp     ebx, 80070002h
0x18003d583  jz      short loc_18003D59E
0x18003d585  cmp     ebx, edi
0x18003d587  jz      short loc_18003D59E
0x18003d589  test    ebx, ebx
0x18003d58b  js      loc_18003D670
0x18003d591  xor     r14d, r14d
0x18003d594  cmp     dword ptr [rbp+arg_0], r14d
0x18003d598  setnz   r14b
0x18003d59c  jmp     short loc_18003D5A1
0x18003d59e  xor     r14d, r14d
0x18003d5a1  mov     [rbp+arg_8], 0
0x18003d5a8  mov     [rbp+arg_18], 4
0x18003d5af  mov     [rbp+hKey], 0
0x18003d5b7  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003d5bc  mov     rcx, rax; lpSubKey
0x18003d5bf  lea     r8, [rbp+hKey]; HKEY *
0x18003d5c3  mov     edx, 20019h; unsigned int
0x18003d5c8  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18003d5cd  mov     ebx, eax
0x18003d5cf  test    eax, eax
0x18003d5d1  js      short loc_18003D61C
0x18003d5d3  mov     rcx, [rbp+hKey]; hkey
0x18003d5d7  lea     rax, [rbp+arg_18]
0x18003d5db  mov     [rsp+50h+pcbData], rax; pcbData
0x18003d5e0  lea     r8, aExternallymana; "ExternallyManaged"
0x18003d5e7  lea     rax, [rbp+arg_8]
0x18003d5eb  mov     r9d, 18h; dwFlags
0x18003d5f1  mov     [rsp+50h+pvData], rax; pvData
0x18003d5f6  xor     edx, edx; lpSubKey
0x18003d5f8  mov     [rsp+50h+phkResult], 0; pdwType
0x18003d601  call    cs:__imp_RegGetValueW
0x18003d608  nop     dword ptr [rax+rax+00h]
0x18003d60d  mov     ebx, eax
0x18003d60f  test    eax, eax
0x18003d611  jle     short loc_18003D61C
0x18003d613  movzx   ebx, ax
0x18003d616  or      ebx, 80070000h
0x18003d61c  cmp     ebx, 80070002h
0x18003d622  jz      short loc_18003D63C
0x18003d624  cmp     ebx, edi
0x18003d626  jz      short loc_18003D63C
0x18003d628  mov     edi, 1
0x18003d62d  test    ebx, ebx
0x18003d62f  js      short loc_18003D640
0x18003d631  xor     edi, edi
0x18003d633  cmp     [rbp+arg_8], edi
0x18003d636  setnz   dil
0x18003d63a  jmp     short loc_18003D640
0x18003d63c  xor     edi, edi
0x18003d63e  xor     ebx, ebx
0x18003d640  mov     rcx, [rbp+hKey]; hKey
0x18003d644  test    rcx, rcx
0x18003d647  jz      short loc_18003D655
0x18003d649  call    cs:__imp_RegCloseKey
0x18003d650  nop     dword ptr [rax+rax+00h]
0x18003d655  test    ebx, ebx
0x18003d657  js      short loc_18003D670
0x18003d659  test    r14d, r14d
0x18003d65c  jnz     short loc_18003D66A
0x18003d65e  test    edi, edi
0x18003d660  jnz     short loc_18003D66A
0x18003d662  mov     dword ptr [rsi], 1
0x18003d668  jmp     short loc_18003D670
0x18003d66a  mov     dword ptr [rsi], 0
0x18003d670  mov     rcx, [rbp+hkey]; hKey
0x18003d674  test    rcx, rcx
0x18003d677  jz      short loc_18003D685
0x18003d679  call    cs:__imp_RegCloseKey
0x18003d680  nop     dword ptr [rax+rax+00h]
0x18003d685  mov     eax, ebx
0x18003d687  add     rsp, 50h
0x18003d68b  pop     r14
0x18003d68d  pop     rdi
0x18003d68e  pop     rsi
0x18003d68f  pop     rbx
0x18003d690  pop     rbp
0x18003d691  retn
```
