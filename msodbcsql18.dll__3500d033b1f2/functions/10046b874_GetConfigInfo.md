# GetConfigInfo

- ea: `0x10046b874`
- end: `0x10046b940`
- name: `GetConfigInfo`
- size: `204`
- prototype: `__int64 __fastcall(LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10046b5f4`

## callees

- `0x10046b874`
- `0x100545d74`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x10046b8f5`
- `ADVAPI32!RegQueryValueExW` at `0x10046b924`
- `ADVAPI32!RegQueryValueExW` at `0x10046b8f5`
- `ADVAPI32!RegQueryValueExW` at `0x10046b924`
- `ADVAPI32!RegOpenKeyExW` at `0x10046b8c2`
- `ADVAPI32!RegOpenKeyExW` at `0x10046b8c2`
- `ADVAPI32!RegCloseKey` at `0x10046b92f`
- `ADVAPI32!RegCloseKey` at `0x10046b92f`

## string_xrefs

- `0x10046b8b4`: `SOFTWARE\Microsoft\DataAccess\MSODBCSQL18`

## pseudocode

```c
LSTATUS __fastcall GetConfigInfo(LPBYTE lpData, LPBYTE a2)
{
  LSTATUS result; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)lpData = 1;
  *(_DWORD *)a2 = g_SystemInfo.dwNumberOfProcessors + 1;
  result = IsEmbeddedSNAC();
  if ( !result )
  {
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\DataAccess\\MSODBCSQL18", 0, 0x20019u, &hKey);
    if ( !result )
    {
      cbData = 4;
      RegQueryValueExW(hKey, L"UseMPHeap", 0, 0, lpData, &cbData);
      cbData = 4;
      RegQueryValueExW(hKey, L"NumberOfCsPools", 0, 0, a2, &cbData);
      return RegCloseKey(hKey);
    }
  }
  return result;
}

```

## disassembly

```asm
0x10046b874  mov     [rsp+arg_10], rbx
0x10046b879  push    rdi
0x10046b87a  sub     rsp, 30h
0x10046b87e  mov     dword ptr [rcx], 1
0x10046b884  mov     rbx, rdx
0x10046b887  mov     eax, cs:?g_SystemInfo@@3U_SYSTEM_INFO@@A.dwNumberOfProcessors; _SYSTEM_INFO g_SystemInfo ...
0x10046b88d  mov     rdi, rcx
0x10046b890  inc     eax
0x10046b892  mov     [rdx], eax
0x10046b894  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x10046b899  test    eax, eax
0x10046b89b  jnz     loc_10046B935
0x10046b8a1  lea     rax, [rsp+38h+hKey]
0x10046b8a6  mov     r9d, 20019h; samDesired
0x10046b8ac  xor     r8d, r8d; ulOptions
0x10046b8af  mov     [rsp+38h+phkResult], rax; phkResult
0x10046b8b4  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\DataAccess\\MSODBC"...
0x10046b8bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10046b8c2  call    cs:__imp_RegOpenKeyExW
0x10046b8c8  test    eax, eax
0x10046b8ca  jnz     short loc_10046B935
0x10046b8cc  mov     rcx, [rsp+38h+hKey]; hKey
0x10046b8d1  lea     rax, [rsp+38h+cbData]
0x10046b8d6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x10046b8db  lea     rdx, aUsempheap; "UseMPHeap"
0x10046b8e2  xor     r9d, r9d; lpType
0x10046b8e5  mov     [rsp+38h+phkResult], rdi; lpData
0x10046b8ea  xor     r8d, r8d; lpReserved
0x10046b8ed  mov     [rsp+38h+cbData], 4
0x10046b8f5  call    cs:__imp_RegQueryValueExW
0x10046b8fb  mov     rcx, [rsp+38h+hKey]; hKey
0x10046b900  lea     rax, [rsp+38h+cbData]
0x10046b905  mov     [rsp+38h+lpcbData], rax; lpcbData
0x10046b90a  lea     rdx, aNumberofcspool; "NumberOfCsPools"
0x10046b911  xor     r9d, r9d; lpType
0x10046b914  mov     [rsp+38h+phkResult], rbx; lpData
0x10046b919  xor     r8d, r8d; lpReserved
0x10046b91c  mov     [rsp+38h+cbData], 4
0x10046b924  call    cs:__imp_RegQueryValueExW
0x10046b92a  mov     rcx, [rsp+38h+hKey]; hKey
0x10046b92f  call    cs:__imp_RegCloseKey
0x10046b935  mov     rbx, [rsp+38h+arg_10]
0x10046b93a  add     rsp, 30h
0x10046b93e  pop     rdi
0x10046b93f  retn
```
