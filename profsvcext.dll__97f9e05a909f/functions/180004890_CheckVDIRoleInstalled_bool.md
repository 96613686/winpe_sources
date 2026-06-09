# CheckVDIRoleInstalled(bool &)

- ea: `0x180004890`
- end: `0x180004923`
- name: `?CheckVDIRoleInstalled@@YAJAEA_N@Z`
- size: `147`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015f30`

## callees

- `0x180004890`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004915`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004915`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004902`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004902`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800048c6`

## pseudocode

```c
__int64 __fastcall CheckVDIRoleInstalled(bool *a1)
{
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  *a1 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"RDVirtualizationPool", 0, 0, (LPBYTE)&Data, &cbData) != 2 )
      *a1 = 1;
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180004890  push    rbx
0x180004892  sub     rsp, 30h
0x180004896  mov     rbx, rcx
0x180004899  mov     byte ptr [rcx], 0
0x18000489c  lea     rax, [rsp+38h+hKey]
0x1800048a1  mov     [rsp+38h+hKey], 0
0x1800048aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048b1  mov     [rsp+38h+phkResult], rax; phkResult
0x1800048b6  mov     r9d, 20019h; samDesired
0x1800048bc  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800048c3  xor     r8d, r8d; ulOptions
0x1800048c6  call    cs:__imp_RegOpenKeyExW
0x1800048cc  test    eax, eax
0x1800048ce  jnz     short loc_18000491B
0x1800048d0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800048d5  lea     rdx, aRdvirtualizati; "RDVirtualizationPool"
0x1800048dc  mov     [rsp+38h+Data], eax
0x1800048e0  xor     r9d, r9d; lpType
0x1800048e3  lea     rax, [rsp+38h+cbData]
0x1800048e8  mov     [rsp+38h+cbData], 4
0x1800048f0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800048f5  xor     r8d, r8d; lpReserved
0x1800048f8  lea     rax, [rsp+38h+Data]
0x1800048fd  mov     [rsp+38h+phkResult], rax; lpData
0x180004902  call    cs:__imp_RegQueryValueExW
0x180004908  cmp     eax, 2
0x18000490b  jz      short loc_180004910
0x18000490d  mov     byte ptr [rbx], 1
0x180004910  mov     rcx, [rsp+38h+hKey]; hKey
0x180004915  call    cs:__imp_RegCloseKey
0x18000491b  xor     eax, eax
0x18000491d  add     rsp, 30h
0x180004921  pop     rbx
0x180004922  retn
```
