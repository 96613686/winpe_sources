# RegReadPolicyKey(ushort const *)

- ea: `0x18001a6c0`
- end: `0x18001a7d7`
- name: `?RegReadPolicyKey@@YAHPEBG@Z`
- size: `279`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011fc0`

## callees

- `0x18001a6c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a74d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a7c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a74d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a7c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a733`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a7ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a733`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001a7ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a705`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a777`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a705`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a777`

## string_xrefs

- `0x18001a6f0`: `SOFTWARE\Policies\Microsoft\Windows\Task Scheduler5.0`
- `0x18001a769`: `SOFTWARE\Policies\Microsoft\Windows\Task Scheduler5.0`

## pseudocode

```c
_BOOL8 __fastcall RegReadPolicyKey(const unsigned __int16 *a1)
{
  BOOL v1; // ebx
  LSTATUS v2; // eax
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int v5; // [rsp+54h] [rbp+1Ch]
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v5 = HIDWORD(a1);
  v1 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\Task Scheduler5.0",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_6;
  }
  if ( !RegQueryValueExW(hKey, L"Allow Browse", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    LOBYTE(v1) = Data != 0;
  RegCloseKey(hKey);
  if ( !v1 )
  {
LABEL_6:
    v2 = RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\Task Scheduler5.0",
           0,
           0x20019u,
           &hKey);
    cbData = 4;
    if ( !v2 )
    {
      if ( !RegQueryValueExW(hKey, L"Allow Browse", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
        v1 = Data != 0;
      RegCloseKey(hKey);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001a6c0  mov     qword ptr [rsp-10h+Type], rcx
0x18001a6c5  push    rbp
0x18001a6c6  push    rbx
0x18001a6c7  mov     rbp, rsp
0x18001a6ca  sub     rsp, 38h
0x18001a6ce  xor     ebx, ebx
0x18001a6d0  mov     [rbp+hKey], 0
0x18001a6d8  lea     rax, [rbp+hKey]
0x18001a6dc  mov     [rbp+Type], ebx
0x18001a6df  mov     r9d, 20019h; samDesired
0x18001a6e5  mov     [rbp+Data], ebx
0x18001a6e8  xor     r8d, r8d; ulOptions
0x18001a6eb  mov     [rsp+38h+phkResult], rax; phkResult
0x18001a6f0  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001a6f7  mov     [rbp+cbData], 4
0x18001a6fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001a705  call    cs:__imp_RegOpenKeyExW
0x18001a70b  test    eax, eax
0x18001a70d  jnz     short loc_18001A757
0x18001a70f  mov     rcx, [rbp+hKey]; hKey
0x18001a713  lea     rax, [rbp+cbData]
0x18001a717  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001a71c  lea     r9, [rbp+Type]; lpType
0x18001a720  lea     rax, [rbp+Data]
0x18001a724  xor     r8d, r8d; lpReserved
0x18001a727  lea     rdx, aAllowBrowse; "Allow Browse"
0x18001a72e  mov     [rsp+38h+phkResult], rax; lpData
0x18001a733  call    cs:__imp_RegQueryValueExW
0x18001a739  test    eax, eax
0x18001a73b  jnz     short loc_18001A749
0x18001a73d  cmp     [rbp+Type], 4
0x18001a741  jnz     short loc_18001A749
0x18001a743  cmp     [rbp+Data], ebx
0x18001a746  setnbe  bl
0x18001a749  mov     rcx, [rbp+hKey]; hKey
0x18001a74d  call    cs:__imp_RegCloseKey
0x18001a753  test    ebx, ebx
0x18001a755  jnz     short loc_18001A7CE
0x18001a757  lea     rax, [rbp+hKey]
0x18001a75b  mov     r9d, 20019h; samDesired
0x18001a761  xor     r8d, r8d; ulOptions
0x18001a764  mov     [rsp+38h+phkResult], rax; phkResult
0x18001a769  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001a770  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a777  call    cs:__imp_RegOpenKeyExW
0x18001a77d  mov     [rbp+cbData], 4
0x18001a784  test    eax, eax
0x18001a786  jnz     short loc_18001A7CE
0x18001a788  mov     rcx, [rbp+hKey]; hKey
0x18001a78c  lea     rax, [rbp+cbData]
0x18001a790  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001a795  lea     r9, [rbp+Type]; lpType
0x18001a799  lea     rax, [rbp+Data]
0x18001a79d  xor     r8d, r8d; lpReserved
0x18001a7a0  lea     rdx, aAllowBrowse; "Allow Browse"
0x18001a7a7  mov     [rsp+38h+phkResult], rax; lpData
0x18001a7ac  call    cs:__imp_RegQueryValueExW
0x18001a7b2  test    eax, eax
0x18001a7b4  jnz     short loc_18001A7C4
0x18001a7b6  cmp     [rbp+Type], 4
0x18001a7ba  jnz     short loc_18001A7C4
0x18001a7bc  xor     ebx, ebx
0x18001a7be  cmp     [rbp+Data], ebx
0x18001a7c1  setnbe  bl
0x18001a7c4  mov     rcx, [rbp+hKey]; hKey
0x18001a7c8  call    cs:__imp_RegCloseKey
0x18001a7ce  mov     eax, ebx
0x18001a7d0  add     rsp, 38h
0x18001a7d4  pop     rbx
0x18001a7d5  pop     rbp
0x18001a7d6  retn
```
