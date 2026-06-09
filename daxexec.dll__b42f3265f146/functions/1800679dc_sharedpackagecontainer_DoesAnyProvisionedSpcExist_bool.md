# sharedpackagecontainer::DoesAnyProvisionedSpcExist(bool &)

- ea: `0x1800679dc`
- end: `0x180067a81`
- name: `?DoesAnyProvisionedSpcExist@sharedpackagecontainer@@YA_NAEA_N@Z`
- size: `165`
- prototype: `bool __fastcall(sharedpackagecontainer *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800688c0`

## callees

- `0x1800679dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067a1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067a6c`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180067a4e`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180067a4e`

## pseudocode

```c
bool __fastcall sharedpackagecontainer::DoesAnyProvisionedSpcExist(sharedpackagecontainer *this, bool *a2)
{
  LSTATUS v3; // eax
  HKEY v4; // rcx
  bool v6; // bl
  int v7; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  *(_BYTE *)this = 0;
  v7 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  v4 = hKey;
  if ( v3 )
  {
    *(_BYTE *)this = 1;
    if ( v4 )
      RegCloseKey(v4);
    return 0;
  }
  else
  {
    GetProvisionedSharedPackageContainersFromRegistryStore(hKey, 0, &v7);
    v6 = v7 != 0;
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
}

```

## disassembly

```asm
0x1800679dc  push    rbx
0x1800679de  sub     rsp, 30h
0x1800679e2  mov     rbx, rcx
0x1800679e5  mov     byte ptr [rcx], 0
0x1800679e8  lea     rax, [rsp+38h+hKey]
0x1800679ed  mov     [rsp+38h+arg_0], 0
0x1800679f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800679fc  mov     [rsp+38h+phkResult], rax; phkResult
0x180067a01  mov     r9d, 20019h; samDesired
0x180067a07  mov     [rsp+38h+hKey], 0
0x180067a10  xor     r8d, r8d; ulOptions
0x180067a13  lea     rdx, aSoftware_1; "Software"
0x180067a1a  call    cs:__imp_RegOpenKeyExW
0x180067a21  nop     dword ptr [rax+rax+00h]
0x180067a26  mov     rcx, [rsp+38h+hKey]; hKey
0x180067a2b  test    eax, eax
0x180067a2d  jz      short loc_180067A47
0x180067a2f  mov     byte ptr [rbx], 1
0x180067a32  test    rcx, rcx
0x180067a35  jz      short loc_180067A43
0x180067a37  call    cs:__imp_RegCloseKey
0x180067a3e  nop     dword ptr [rax+rax+00h]
0x180067a43  xor     al, al
0x180067a45  jmp     short loc_180067A7A
0x180067a47  lea     r8, [rsp+38h+arg_0]
0x180067a4c  xor     edx, edx
0x180067a4e  call    cs:__imp_GetProvisionedSharedPackageContainersFromRegistryStore
0x180067a55  nop     dword ptr [rax+rax+00h]
0x180067a5a  cmp     [rsp+38h+arg_0], 0
0x180067a5f  mov     rcx, [rsp+38h+hKey]; hKey
0x180067a64  setnbe  bl
0x180067a67  test    rcx, rcx
0x180067a6a  jz      short loc_180067A78
0x180067a6c  call    cs:__imp_RegCloseKey
0x180067a73  nop     dword ptr [rax+rax+00h]
0x180067a78  mov     al, bl
0x180067a7a  add     rsp, 30h
0x180067a7e  pop     rbx
0x180067a7f  retn
```
