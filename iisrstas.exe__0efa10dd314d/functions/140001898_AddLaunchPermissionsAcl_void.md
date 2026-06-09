# AddLaunchPermissionsAcl(void *)

- ea: `0x140001898`
- end: `0x1400019b1`
- name: `?AddLaunchPermissionsAcl@@YAJPEAX@Z`
- size: `281`
- prototype: `signed int __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140002a40`

## callees

- `0x140001008`
- `0x140001060`
- `0x140001898`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400018bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140001909`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1400018bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140001909`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001932`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140001932`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000196e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000196e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000199a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000199a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400018cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001913`

## pseudocode

```c
signed int __fastcall AddLaunchPermissionsAcl(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)
{
  signed int result; // eax
  BYTE *v3; // rax
  BYTE *v4; // rdi
  int LastError; // eax
  unsigned int v6; // ebx
  bool v7; // cc
  DWORD dwBufferLength; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  dwBufferLength = 0;
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength) )
    return -2147467259;
  result = GetLastError();
  if ( result != 122 )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v3 = (BYTE *)operator new[](dwBufferLength);
  v4 = v3;
  if ( !v3 )
    return -2147024882;
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v3, &dwBufferLength) )
  {
    LastError = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"AppID\\{E8FB8615-588F-11D2-9D61-00C04F79C5FE}", 0, 0x20006u, &hKey);
    v6 = LastError;
    v7 = LastError <= 0;
    if ( !LastError )
    {
      LastError = RegSetValueExW(hKey, L"LaunchPermission", 0, 3u, v4, dwBufferLength);
      if ( !LastError )
        goto LABEL_12;
      if ( LastError <= 0 )
      {
        v6 = LastError;
        goto LABEL_12;
      }
      goto LABEL_11;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = LastError <= 0;
  }
  if ( !v7 )
LABEL_11:
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  operator delete[](v4);
  return v6;
}

```

## disassembly

```asm
0x140001898  mov     rax, rsp
0x14000189b  mov     [rax+8], rbx
0x14000189f  push    rdi
0x1400018a0  sub     rsp, 30h
0x1400018a4  lea     r8, [rax+10h]; lpdwBufferLength
0x1400018a8  mov     qword ptr [rax+18h], 0
0x1400018b0  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x1400018b2  mov     dword ptr [rax+10h], 0
0x1400018b9  mov     rbx, rcx
0x1400018bc  call    cs:__imp_MakeSelfRelativeSD
0x1400018c2  test    eax, eax
0x1400018c4  jz      short loc_1400018CD
0x1400018c6  mov     eax, 80004005h
0x1400018cb  jmp     short loc_140001942
0x1400018cd  call    cs:__imp_GetLastError
0x1400018d3  cmp     eax, 7Ah ; 'z'
0x1400018d6  jz      short loc_1400018E6
0x1400018d8  test    eax, eax
0x1400018da  jle     short loc_140001942
0x1400018dc  movzx   eax, ax
0x1400018df  or      eax, 80070000h
0x1400018e4  jmp     short loc_140001942
0x1400018e6  mov     ecx, [rsp+38h+dwBufferLength]; unsigned __int64
0x1400018ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400018ef  mov     rdi, rax
0x1400018f2  test    rax, rax
0x1400018f5  jnz     short loc_1400018FE
0x1400018f7  mov     eax, 8007000Eh
0x1400018fc  jmp     short loc_140001942
0x1400018fe  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x140001903  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x140001906  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x140001909  call    cs:__imp_MakeSelfRelativeSD
0x14000190f  test    eax, eax
0x140001911  jnz     short loc_14000194D
0x140001913  call    cs:__imp_GetLastError
0x140001919  mov     ebx, eax
0x14000191b  test    eax, eax
0x14000191d  jle     short loc_140001928
0x14000191f  movzx   ebx, ax
0x140001922  or      ebx, 80070000h
0x140001928  mov     rcx, [rsp+38h+hKey]; hKey
0x14000192d  test    rcx, rcx
0x140001930  jz      short loc_140001938
0x140001932  call    cs:__imp_RegCloseKey
0x140001938  mov     rcx, rdi; void *
0x14000193b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x140001940  mov     eax, ebx
0x140001942  mov     rbx, [rsp+38h+arg_0]
0x140001947  add     rsp, 30h
0x14000194b  pop     rdi
0x14000194c  retn
0x14000194d  lea     rax, [rsp+38h+hKey]
0x140001952  mov     r9d, 20006h; samDesired
0x140001958  xor     r8d, r8d; ulOptions
0x14000195b  mov     [rsp+38h+phkResult], rax; phkResult
0x140001960  lea     rdx, SubKey; "AppID\\{E8FB8615-588F-11D2-9D61-00C04F7"...
0x140001967  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14000196e  call    cs:__imp_RegOpenKeyExW
0x140001974  mov     ebx, eax
0x140001976  test    eax, eax
0x140001978  jnz     short loc_14000191D
0x14000197a  mov     eax, [rsp+38h+dwBufferLength]
0x14000197e  lea     r9d, [rbx+3]; dwType
0x140001982  mov     rcx, [rsp+38h+hKey]; hKey
0x140001987  lea     rdx, ValueName; "LaunchPermission"
0x14000198e  mov     [rsp+38h+cbData], eax; cbData
0x140001992  xor     r8d, r8d; Reserved
0x140001995  mov     [rsp+38h+phkResult], rdi; lpData
0x14000199a  call    cs:__imp_RegSetValueExW
0x1400019a0  test    eax, eax
0x1400019a2  jz      short loc_140001928
0x1400019a4  jg      loc_14000191F
0x1400019aa  mov     ebx, eax
0x1400019ac  jmp     loc_140001928
```
