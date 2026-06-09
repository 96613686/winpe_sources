# Read6to4SpecificInterfaceSettings

- ea: `0x180050ed0`
- end: `0x18005104a`
- name: `Read6to4SpecificInterfaceSettings`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004fb20`

## callees

- `0x18002b47c`
- `0x18004b5f0`
- `0x180050ed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180050ff7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180050ff7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051012`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051020`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051020`

## string_xrefs

- `0x180050f26`: `System\CurrentControlSet\Services\iphlpsvc\Interfaces`

## pseudocode

```c
__int64 __fastcall Read6to4SpecificInterfaceSettings(__int64 a1)
{
  LSTATUS v2; // ebx
  DWORD v3; // edi
  DWORD i; // edx
  int Integer; // eax
  HKEY v6; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[128]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Interfaces", 0, 8u, &hKey);
  if ( !v2 )
  {
    v3 = 0;
    for ( i = 0; ; i = v3 )
    {
      cchName = 128;
      v2 = RegEnumKeyExW(hKey, i, SubKey, &cchName, 0, 0, 0, 0);
      if ( v2 )
        break;
      RegOpenKeyExW(hKey, SubKey, 0, 1u, &phkResult);
      Integer = GetInteger(phkResult, L"EnableRouting", 1);
      v6 = phkResult;
      *(_DWORD *)(a1 + 2424) = Integer;
      if ( v6 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(v6);
      ++v3;
    }
    RegCloseKey(hKey);
  }
  SetLastError(v2);
  return 1;
}

```

## disassembly

```asm
0x180050ed0  push    rbp
0x180050ed2  push    rbx
0x180050ed3  push    rsi
0x180050ed4  push    rdi
0x180050ed5  lea     rbp, [rsp-78h]
0x180050eda  sub     rsp, 178h
0x180050ee1  mov     rax, cs:__security_cookie
0x180050ee8  xor     rax, rsp
0x180050eeb  mov     [rbp+90h+var_30], rax
0x180050eef  mov     rsi, rcx
0x180050ef2  mov     [rsp+190h+cchName], 0
0x180050efa  lea     rax, [rsp+190h+hKey]
0x180050eff  mov     [rsp+190h+hKey], 0FFFFFFFFFFFFFFFFh
0x180050f08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050f0f  mov     [rsp+190h+phkResult], rax; phkResult
0x180050f14  mov     r9d, 8; samDesired
0x180050f1a  mov     [rsp+190h+var_140], 0FFFFFFFFFFFFFFFFh
0x180050f23  xor     r8d, r8d; ulOptions
0x180050f26  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\ip"...
0x180050f2d  call    cs:__imp_RegOpenKeyExW
0x180050f34  nop     dword ptr [rax+rax+00h]
0x180050f39  mov     ebx, eax
0x180050f3b  test    eax, eax
0x180050f3d  jnz     loc_18005101E
0x180050f43  xor     edi, edi
0x180050f45  mov     [rsp+190h+lpftLastWriteTime], rdi
0x180050f4a  xor     edx, edx
0x180050f4c  mov     [rsp+190h+lpcchClass], rdi
0x180050f51  mov     [rsp+190h+lpClass], rdi
0x180050f56  mov     [rsp+190h+phkResult], rdi
0x180050f5b  jmp     loc_180050FE0
0x180050f60  lea     rax, [rsp+190h+var_140]
0x180050f65  mov     r9d, 1; samDesired
0x180050f6b  xor     r8d, r8d; ulOptions
0x180050f6e  mov     [rsp+190h+phkResult], rax; phkResult
0x180050f73  lea     rdx, [rsp+190h+SubKey]; lpSubKey
0x180050f78  call    cs:__imp_RegOpenKeyExW
0x180050f7f  nop     dword ptr [rax+rax+00h]
0x180050f84  mov     rcx, [rsp+190h+var_140]
0x180050f89  lea     rdx, aEnablerouting; "EnableRouting"
0x180050f90  mov     r8d, 1
0x180050f96  call    GetInteger
0x180050f9b  mov     rcx, [rsp+190h+var_140]; hKey
0x180050fa0  mov     [rsi+978h], eax
0x180050fa6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180050faa  jz      short loc_180050FB8
0x180050fac  call    cs:__imp_RegCloseKey
0x180050fb3  nop     dword ptr [rax+rax+00h]
0x180050fb8  mov     [rsp+190h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180050fc1  inc     edi
0x180050fc3  mov     [rsp+190h+lpcchClass], 0; lpcchClass
0x180050fcc  mov     edx, edi; dwIndex
0x180050fce  mov     [rsp+190h+lpClass], 0; lpClass
0x180050fd7  mov     [rsp+190h+phkResult], 0; lpReserved
0x180050fe0  mov     rcx, [rsp+190h+hKey]; hKey
0x180050fe5  lea     r9, [rsp+190h+cchName]; lpcchName
0x180050fea  lea     r8, [rsp+190h+SubKey]; lpName
0x180050fef  mov     [rsp+190h+cchName], 80h
0x180050ff7  call    cs:__imp_RegEnumKeyExW
0x180050ffe  nop     dword ptr [rax+rax+00h]
0x180051003  mov     rcx, [rsp+190h+hKey]; hKey
0x180051008  mov     ebx, eax
0x18005100a  test    eax, eax
0x18005100c  jz      loc_180050F60
0x180051012  call    cs:__imp_RegCloseKey
0x180051019  nop     dword ptr [rax+rax+00h]
0x18005101e  mov     ecx, ebx; dwErrCode
0x180051020  call    cs:__imp_SetLastError
0x180051027  nop     dword ptr [rax+rax+00h]
0x18005102c  mov     eax, 1
0x180051031  mov     rcx, [rbp+90h+var_30]
0x180051035  xor     rcx, rsp; StackCookie
0x180051038  call    __security_check_cookie
0x18005103d  add     rsp, 178h
0x180051044  pop     rdi
0x180051045  pop     rsi
0x180051046  pop     rbx
0x180051047  pop     rbp
0x180051048  retn
```
