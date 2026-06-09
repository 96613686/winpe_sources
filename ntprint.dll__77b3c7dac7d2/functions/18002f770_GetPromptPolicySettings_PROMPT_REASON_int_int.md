# GetPromptPolicySettings(PROMPT_REASON,int *,int *)

- ea: `0x18002f770`
- end: `0x18002f94f`
- name: `?GetPromptPolicySettings@@YAJW4PROMPT_REASON@@PEAH1@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f9e0`

## callees

- `0x18002c3d0`
- `0x18002f770`
- `0x18002faa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f91e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f91e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f862`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f862`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f8ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f813`

## string_xrefs

- `0x18002f8e5`: `UpdatePromptSettings`
- `0x18002f8bb`: `NoWarningNoElevationOnInstall`

## pseudocode

```c
__int64 __fastcall GetPromptPolicySettings(int a1, _DWORD *a2, int *a3)
{
  __int64 result; // rax
  int v7; // edi
  LSTATUS v8; // eax
  signed int v9; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  int v14; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  Type = 0;
  if ( a2 && a3 )
  {
    v14 = 1;
    RunningAsLUA(&v14);
    if ( (unsigned int)RestrictDriverInstallationToAdministrators() && v14 )
    {
      *a2 = 1;
      result = 0;
      *a3 = 1;
      return result;
    }
    v7 = 1;
    v8 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\PointAndPrint",
           0,
           0x20019u,
           &hKey);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_28;
    cbData = 4;
    Type = 0;
    v10 = RegQueryValueExW(hKey, L"Restricted", 0, &Type, (LPBYTE)&Data, &cbData);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_28;
    }
    if ( Data != 1 )
      goto LABEL_28;
    cbData = 4;
    Type = 0;
    if ( a1 )
    {
      v12 = RegQueryValueExW(hKey, L"UpdatePromptSettings", 0, &Type, (LPBYTE)&Data, &cbData);
      v9 = v12;
      if ( v12 )
      {
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( v9 < 0 )
          goto LABEL_28;
      }
      if ( Data != 1 && Data != 2 )
        goto LABEL_28;
    }
    else
    {
      v11 = RegQueryValueExW(hKey, L"NoWarningNoElevationOnInstall", 0, &Type, (LPBYTE)&Data, &cbData);
      v9 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        if ( v9 < 0 )
          goto LABEL_28;
      }
      if ( !Data )
        goto LABEL_28;
    }
    v7 = 0;
LABEL_28:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v9 >= 0 )
    {
      *a2 = 1;
      *a3 = v7;
    }
    return (unsigned int)v9;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18002f770  mov     [rsp-28h+arg_0], rbx
0x18002f775  mov     [rsp-28h+arg_10], rsi
0x18002f77a  push    rbp
0x18002f77b  push    rdi
0x18002f77c  push    r13
0x18002f77e  push    r14
0x18002f780  push    r15
0x18002f782  mov     rbp, rsp
0x18002f785  sub     rsp, 40h
0x18002f789  mov     [rbp+hKey], 0
0x18002f791  mov     rsi, r8
0x18002f794  mov     [rbp+Data], 0
0x18002f79b  mov     r14, rdx
0x18002f79e  mov     [rbp+cbData], 0
0x18002f7a5  mov     r15d, ecx
0x18002f7a8  mov     [rbp+Type], 0
0x18002f7af  test    rdx, rdx
0x18002f7b2  jz      loc_18002F92F
0x18002f7b8  test    r8, r8
0x18002f7bb  jz      loc_18002F92F
0x18002f7c1  mov     r13d, 1
0x18002f7c7  lea     rcx, [rbp+var_C]; int *
0x18002f7cb  mov     [rbp+var_C], r13d
0x18002f7cf  call    ?RunningAsLUA@@YAJPEAH@Z; RunningAsLUA(int *)
0x18002f7d4  call    ?RestrictDriverInstallationToAdministrators@@YAHXZ; RestrictDriverInstallationToAdministrators(void)
0x18002f7d9  test    eax, eax
0x18002f7db  jz      short loc_18002F7F0
0x18002f7dd  cmp     [rbp+var_C], 0
0x18002f7e1  jz      short loc_18002F7F0
0x18002f7e3  mov     [r14], r13d
0x18002f7e6  xor     eax, eax
0x18002f7e8  mov     [rsi], r13d
0x18002f7eb  jmp     loc_18002F936
0x18002f7f0  lea     rax, [rbp+hKey]
0x18002f7f4  mov     r9d, 20019h; samDesired
0x18002f7fa  xor     r8d, r8d; ulOptions
0x18002f7fd  mov     [rsp+40h+phkResult], rax; phkResult
0x18002f802  lea     rdx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\Windows "...
0x18002f809  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f810  mov     edi, r13d
0x18002f813  call    cs:__imp_RegOpenKeyExW
0x18002f819  mov     ebx, eax
0x18002f81b  test    eax, eax
0x18002f81d  jle     short loc_18002F828
0x18002f81f  movzx   ebx, ax
0x18002f822  or      ebx, 80070000h
0x18002f828  test    ebx, ebx
0x18002f82a  js      loc_18002F915
0x18002f830  mov     rcx, [rbp+hKey]; hKey
0x18002f834  lea     rax, [rbp+cbData]
0x18002f838  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002f83d  lea     r9, [rbp+Type]; lpType
0x18002f841  lea     rax, [rbp+Data]
0x18002f845  mov     [rbp+cbData], 4
0x18002f84c  xor     r8d, r8d; lpReserved
0x18002f84f  mov     [rsp+40h+phkResult], rax; lpData
0x18002f854  lea     rdx, aRestricted; "Restricted"
0x18002f85b  mov     [rbp+Type], 0
0x18002f862  call    cs:__imp_RegQueryValueExW
0x18002f868  mov     ebx, eax
0x18002f86a  test    eax, eax
0x18002f86c  jz      short loc_18002F881
0x18002f86e  jle     short loc_18002F879
0x18002f870  movzx   ebx, ax
0x18002f873  or      ebx, 80070000h
0x18002f879  test    ebx, ebx
0x18002f87b  js      loc_18002F915
0x18002f881  cmp     [rbp+Data], r13d
0x18002f885  jnz     loc_18002F915
0x18002f88b  mov     rcx, [rbp+hKey]; hKey
0x18002f88f  lea     rax, [rbp+cbData]
0x18002f893  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002f898  lea     r9, [rbp+Type]; lpType
0x18002f89c  xor     r8d, r8d; lpReserved
0x18002f89f  mov     [rbp+cbData], 4
0x18002f8a6  mov     [rbp+Type], 0
0x18002f8ad  lea     rax, [rbp+Data]
0x18002f8b1  mov     [rsp+40h+phkResult], rax; lpData
0x18002f8b6  test    r15d, r15d
0x18002f8b9  jnz     short loc_18002F8E5
0x18002f8bb  lea     rdx, aNowarningnoele; "NoWarningNoElevationOnInstall"
0x18002f8c2  call    cs:__imp_RegQueryValueExW
0x18002f8c8  mov     ebx, eax
0x18002f8ca  test    eax, eax
0x18002f8cc  jz      short loc_18002F8DD
0x18002f8ce  jle     short loc_18002F8D9
0x18002f8d0  movzx   ebx, ax
0x18002f8d3  or      ebx, 80070000h
0x18002f8d9  test    ebx, ebx
0x18002f8db  js      short loc_18002F915
0x18002f8dd  cmp     [rbp+Data], 0
0x18002f8e1  jz      short loc_18002F915
0x18002f8e3  jmp     short loc_18002F913
0x18002f8e5  lea     rdx, aUpdatepromptse; "UpdatePromptSettings"
0x18002f8ec  call    cs:__imp_RegQueryValueExW
0x18002f8f2  mov     ebx, eax
0x18002f8f4  test    eax, eax
0x18002f8f6  jz      short loc_18002F907
0x18002f8f8  jle     short loc_18002F903
0x18002f8fa  movzx   ebx, ax
0x18002f8fd  or      ebx, 80070000h
0x18002f903  test    ebx, ebx
0x18002f905  js      short loc_18002F915
0x18002f907  cmp     [rbp+Data], r13d
0x18002f90b  jz      short loc_18002F913
0x18002f90d  cmp     [rbp+Data], 2
0x18002f911  jnz     short loc_18002F915
0x18002f913  xor     edi, edi
0x18002f915  mov     rcx, [rbp+hKey]; hKey
0x18002f919  test    rcx, rcx
0x18002f91c  jz      short loc_18002F924
0x18002f91e  call    cs:__imp_RegCloseKey
0x18002f924  test    ebx, ebx
0x18002f926  js      short loc_18002F934
0x18002f928  mov     [r14], r13d
0x18002f92b  mov     [rsi], edi
0x18002f92d  jmp     short loc_18002F934
0x18002f92f  mov     ebx, 80070057h
0x18002f934  mov     eax, ebx
0x18002f936  lea     r11, [rsp+40h+var_s0]
0x18002f93b  mov     rbx, [r11+30h]
0x18002f93f  mov     rsi, [r11+40h]
0x18002f943  mov     rsp, r11
0x18002f946  pop     r15
0x18002f948  pop     r14
0x18002f94a  pop     r13
0x18002f94c  pop     rdi
0x18002f94d  pop     rbp
0x18002f94e  retn
```
