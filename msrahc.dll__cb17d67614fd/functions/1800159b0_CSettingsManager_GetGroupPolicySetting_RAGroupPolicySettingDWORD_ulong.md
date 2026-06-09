# CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingDWORD,ulong *)

- ea: `0x1800159b0`
- end: `0x180015aa9`
- name: `?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingDWORD@@PEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(HANDLE *, DWORD, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011170`

## callees

- `0x1800159b0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180015a65`
- `ADVAPI32!RegQueryValueExW` at `0x180015a65`
- `ADVAPI32!RegOpenKeyExW` at `0x180015a34`
- `ADVAPI32!RegOpenKeyExW` at `0x180015a34`
- `ADVAPI32!RegCloseKey` at `0x180015a80`
- `ADVAPI32!RegCloseKey` at `0x180015a80`
- `KERNEL32!ReleaseMutex` at `0x180015a96`
- `KERNEL32!ReleaseMutex` at `0x180015a96`
- `KERNEL32!WaitForSingleObject` at `0x1800159fc`
- `KERNEL32!WaitForSingleObject` at `0x1800159fc`

## string_xrefs

- `0x180015a26`: `Software\policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall CSettingsManager::GetGroupPolicySetting(HANDLE *a1, DWORD a2, _DWORD *a3)
{
  HANDLE v4; // rcx
  unsigned int v6; // ebx
  int v7; // edi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  cbData = a2;
  hKey = 0;
  v4 = *a1;
  cbData = 0;
  Data = 0;
  Type = 4;
  if ( !v4 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v4, 0x64u) == 258 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services",
            0,
            1u,
            &hKey) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(hKey, RA_GP_SETTINGS_DWORD, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        v6 = 0;
        *a3 = Data;
        goto LABEL_9;
      }
    }
  }
  v6 = -2147467259;
LABEL_9:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 == 1 )
    ReleaseMutex(*a1);
  return v6;
}

```

## disassembly

```asm
0x1800159b0  mov     [rsp-28h+cbData], edx
0x1800159b4  push    rbp
0x1800159b5  push    rbx
0x1800159b6  push    rsi
0x1800159b7  push    rdi
0x1800159b8  push    r14
0x1800159ba  mov     rbp, rsp
0x1800159bd  sub     rsp, 40h
0x1800159c1  mov     rsi, rcx
0x1800159c4  mov     [rbp+hKey], 0
0x1800159cc  mov     rcx, [rcx]; hHandle
0x1800159cf  mov     ebx, 4
0x1800159d4  mov     [rbp+cbData], 0
0x1800159db  mov     r14, r8
0x1800159de  mov     [rbp+Data], 0
0x1800159e5  mov     [rbp+Type], ebx
0x1800159e8  test    rcx, rcx
0x1800159eb  jnz     short loc_1800159F7
0x1800159ed  mov     ebx, 8000FFFFh
0x1800159f2  jmp     loc_180015A9C
0x1800159f7  mov     edx, 64h ; 'd'; dwMilliseconds
0x1800159fc  call    cs:__imp_WaitForSingleObject
0x180015a02  cmp     eax, 102h
0x180015a07  jnz     short loc_180015A12
0x180015a09  xor     edi, edi
0x180015a0b  mov     ebx, 80004005h
0x180015a10  jmp     short loc_180015A77
0x180015a12  lea     rax, [rbp+hKey]
0x180015a16  mov     edi, 1
0x180015a1b  mov     r9d, edi; samDesired
0x180015a1e  mov     [rsp+40h+phkResult], rax; phkResult
0x180015a23  xor     r8d, r8d; ulOptions
0x180015a26  lea     rdx, aSoftwarePolici; "Software\\policies\\Microsoft\\Windows "...
0x180015a2d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015a34  call    cs:__imp_RegOpenKeyExW
0x180015a3a  test    eax, eax
0x180015a3c  jnz     short loc_180015A0B
0x180015a3e  mov     rdx, cs:?RA_GP_SETTINGS_DWORD@@3PAPEBGA; lpValueName
0x180015a45  lea     rax, [rbp+cbData]
0x180015a49  mov     rcx, [rbp+hKey]; hKey
0x180015a4d  lea     r9, [rbp+Type]; lpType
0x180015a51  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180015a56  xor     r8d, r8d; lpReserved
0x180015a59  lea     rax, [rbp+Data]
0x180015a5d  mov     [rbp+cbData], ebx
0x180015a60  mov     [rsp+40h+phkResult], rax; lpData
0x180015a65  call    cs:__imp_RegQueryValueExW
0x180015a6b  test    eax, eax
0x180015a6d  jnz     short loc_180015A0B
0x180015a6f  mov     eax, [rbp+Data]
0x180015a72  xor     ebx, ebx
0x180015a74  mov     [r14], eax
0x180015a77  mov     rcx, [rbp+hKey]; hKey
0x180015a7b  test    rcx, rcx
0x180015a7e  jz      short loc_180015A8E
0x180015a80  call    cs:__imp_RegCloseKey
0x180015a86  mov     [rbp+hKey], 0
0x180015a8e  cmp     edi, 1
0x180015a91  jnz     short loc_180015A9C
0x180015a93  mov     rcx, [rsi]; hMutex
0x180015a96  call    cs:__imp_ReleaseMutex
0x180015a9c  mov     eax, ebx
0x180015a9e  add     rsp, 40h
0x180015aa2  pop     r14
0x180015aa4  pop     rdi
0x180015aa5  pop     rsi
0x180015aa6  pop     rbx
0x180015aa7  pop     rbp
0x180015aa8  retn
```
