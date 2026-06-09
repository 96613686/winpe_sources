# CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingDWORD,ulong *)

- ea: `0x140036dc8`
- end: `0x140036ef6`
- name: `?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingDWORD@@PEAK@Z`
- size: `302`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000a858`
- `0x14001ffb8`
- `0x140020c24`
- `0x1400223c4`
- `0x140022c68`
- `0x14002981c`
- `0x14002ad4c`
- `0x14002ceb0`
- `0x14002cf20`
- `0x14002df5c`

## callees

- `0x140036dc8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140036eb8`
- `ADVAPI32!RegCloseKey` at `0x140036eb8`
- `ADVAPI32!RegOpenKeyExW` at `0x140036e58`
- `ADVAPI32!RegOpenKeyExW` at `0x140036e58`
- `ADVAPI32!RegQueryValueExW` at `0x140036e97`
- `ADVAPI32!RegQueryValueExW` at `0x140036e97`
- `KERNEL32!ReleaseMutex` at `0x140036ed4`
- `KERNEL32!ReleaseMutex` at `0x140036ed4`
- `KERNEL32!WaitForSingleObject` at `0x140036e1a`
- `KERNEL32!WaitForSingleObject` at `0x140036e1a`

## string_xrefs

- `0x140036e4a`: `Software\policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall CSettingsManager::GetGroupPolicySetting(HANDLE *a1, int a2, _DWORD *a3)
{
  __int64 v4; // rbx
  HANDLE v5; // rcx
  unsigned int v7; // ebx
  int v8; // edi
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  v4 = a2;
  v5 = *a1;
  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  if ( !v5 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v5, 0x64u) == 258 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services",
            0,
            1u,
            &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, (LPCWSTR)(&RA_GP_SETTINGS_DWORD)[v4], 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        v7 = 0;
        *a3 = Data;
        goto LABEL_9;
      }
    }
  }
  v7 = -2147467259;
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v8 == 1 )
    ReleaseMutex(*a1);
  return v7;
}

```

## disassembly

```asm
0x140036dc8  mov     [rsp-18h+arg_8], rbx
0x140036dcd  mov     [rsp-18h+arg_10], rsi
0x140036dd2  push    rbp
0x140036dd3  push    rdi
0x140036dd4  push    r14
0x140036dd6  mov     rbp, rsp
0x140036dd9  sub     rsp, 40h
0x140036ddd  mov     rsi, rcx
0x140036de0  movsxd  rbx, edx
0x140036de3  mov     rcx, [rcx]; hHandle
0x140036de6  mov     r14, r8
0x140036de9  mov     [rbp+hKey], 0
0x140036df1  mov     [rbp+cbData], 0
0x140036df8  mov     [rbp+Data], 0
0x140036dff  mov     [rbp+Type], 4
0x140036e06  test    rcx, rcx
0x140036e09  jnz     short loc_140036E15
0x140036e0b  mov     ebx, 8000FFFFh
0x140036e10  jmp     loc_140036EE0
0x140036e15  mov     edx, 64h ; 'd'; dwMilliseconds
0x140036e1a  call    cs:__imp_WaitForSingleObject
0x140036e21  nop     dword ptr [rax+rax+00h]
0x140036e26  cmp     eax, 102h
0x140036e2b  jnz     short loc_140036E36
0x140036e2d  xor     edi, edi
0x140036e2f  mov     ebx, 80004005h
0x140036e34  jmp     short loc_140036EAF
0x140036e36  lea     rax, [rbp+hKey]
0x140036e3a  mov     edi, 1
0x140036e3f  mov     r9d, edi; samDesired
0x140036e42  mov     [rsp+40h+phkResult], rax; phkResult
0x140036e47  xor     r8d, r8d; ulOptions
0x140036e4a  lea     rdx, aSoftwarePolici; "Software\\policies\\Microsoft\\Windows "...
0x140036e51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140036e58  call    cs:__imp_RegOpenKeyExW
0x140036e5f  nop     dword ptr [rax+rax+00h]
0x140036e64  test    eax, eax
0x140036e66  jnz     short loc_140036E2F
0x140036e68  lea     rax, [rbp+cbData]
0x140036e6c  mov     [rbp+cbData], 4
0x140036e73  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140036e78  lea     rcx, ?RA_GP_SETTINGS_DWORD@@3PAPEBGA; ushort const * near * RA_GP_SETTINGS_DWORD
0x140036e7f  mov     rdx, [rcx+rbx*8]; lpValueName
0x140036e83  lea     rax, [rbp+Data]
0x140036e87  mov     rcx, [rbp+hKey]; hKey
0x140036e8b  lea     r9, [rbp+Type]; lpType
0x140036e8f  xor     r8d, r8d; lpReserved
0x140036e92  mov     [rsp+40h+phkResult], rax; lpData
0x140036e97  call    cs:__imp_RegQueryValueExW
0x140036e9e  nop     dword ptr [rax+rax+00h]
0x140036ea3  test    eax, eax
0x140036ea5  jnz     short loc_140036E2F
0x140036ea7  mov     eax, [rbp+Data]
0x140036eaa  xor     ebx, ebx
0x140036eac  mov     [r14], eax
0x140036eaf  mov     rcx, [rbp+hKey]; hKey
0x140036eb3  test    rcx, rcx
0x140036eb6  jz      short loc_140036ECC
0x140036eb8  call    cs:__imp_RegCloseKey
0x140036ebf  nop     dword ptr [rax+rax+00h]
0x140036ec4  mov     [rbp+hKey], 0
0x140036ecc  cmp     edi, 1
0x140036ecf  jnz     short loc_140036EE0
0x140036ed1  mov     rcx, [rsi]; hMutex
0x140036ed4  call    cs:__imp_ReleaseMutex
0x140036edb  nop     dword ptr [rax+rax+00h]
0x140036ee0  mov     rsi, [rsp+40h+arg_10]
0x140036ee5  mov     eax, ebx
0x140036ee7  mov     rbx, [rsp+40h+arg_8]
0x140036eec  add     rsp, 40h
0x140036ef0  pop     r14
0x140036ef2  pop     rdi
0x140036ef3  pop     rbp
0x140036ef4  retn
```
