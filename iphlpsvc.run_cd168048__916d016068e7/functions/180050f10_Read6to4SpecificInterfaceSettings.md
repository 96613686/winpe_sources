# Read6to4SpecificInterfaceSettings

- ea: `0x180050f10`
- end: `0x18005108a`
- name: `Read6to4SpecificInterfaceSettings`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004fb60`

## callees

- `0x18002b46c`
- `0x18004b630`
- `0x180050f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180051037`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180051037`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051052`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050fec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051052`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050fb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050f6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180050fb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051060`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180051060`

## string_xrefs

- `0x180050f66`: `System\CurrentControlSet\Services\iphlpsvc\Interfaces`

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
0x180050f10  push    rbp
0x180050f12  push    rbx
0x180050f13  push    rsi
0x180050f14  push    rdi
0x180050f15  lea     rbp, [rsp-78h]
0x180050f1a  sub     rsp, 178h
0x180050f21  mov     rax, cs:__security_cookie
0x180050f28  xor     rax, rsp
0x180050f2b  mov     [rbp+90h+var_30], rax
0x180050f2f  mov     rsi, rcx
0x180050f32  mov     [rsp+190h+cchName], 0
0x180050f3a  lea     rax, [rsp+190h+hKey]
0x180050f3f  mov     [rsp+190h+hKey], 0FFFFFFFFFFFFFFFFh
0x180050f48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050f4f  mov     [rsp+190h+phkResult], rax; phkResult
0x180050f54  mov     r9d, 8; samDesired
0x180050f5a  mov     [rsp+190h+var_140], 0FFFFFFFFFFFFFFFFh
0x180050f63  xor     r8d, r8d; ulOptions
0x180050f66  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\ip"...
0x180050f6d  call    cs:__imp_RegOpenKeyExW
0x180050f74  nop     dword ptr [rax+rax+00h]
0x180050f79  mov     ebx, eax
0x180050f7b  test    eax, eax
0x180050f7d  jnz     loc_18005105E
0x180050f83  xor     edi, edi
0x180050f85  mov     [rsp+190h+lpftLastWriteTime], rdi
0x180050f8a  xor     edx, edx
0x180050f8c  mov     [rsp+190h+lpcchClass], rdi
0x180050f91  mov     [rsp+190h+lpClass], rdi
0x180050f96  mov     [rsp+190h+phkResult], rdi
0x180050f9b  jmp     loc_180051020
0x180050fa0  lea     rax, [rsp+190h+var_140]
0x180050fa5  mov     r9d, 1; samDesired
0x180050fab  xor     r8d, r8d; ulOptions
0x180050fae  mov     [rsp+190h+phkResult], rax; phkResult
0x180050fb3  lea     rdx, [rsp+190h+SubKey]; lpSubKey
0x180050fb8  call    cs:__imp_RegOpenKeyExW
0x180050fbf  nop     dword ptr [rax+rax+00h]
0x180050fc4  mov     rcx, [rsp+190h+var_140]
0x180050fc9  lea     rdx, aEnablerouting; "EnableRouting"
0x180050fd0  mov     r8d, 1
0x180050fd6  call    GetInteger
0x180050fdb  mov     rcx, [rsp+190h+var_140]; hKey
0x180050fe0  mov     [rsi+978h], eax
0x180050fe6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180050fea  jz      short loc_180050FF8
0x180050fec  call    cs:__imp_RegCloseKey
0x180050ff3  nop     dword ptr [rax+rax+00h]
0x180050ff8  mov     [rsp+190h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180051001  inc     edi
0x180051003  mov     [rsp+190h+lpcchClass], 0; lpcchClass
0x18005100c  mov     edx, edi; dwIndex
0x18005100e  mov     [rsp+190h+lpClass], 0; lpClass
0x180051017  mov     [rsp+190h+phkResult], 0; lpReserved
0x180051020  mov     rcx, [rsp+190h+hKey]; hKey
0x180051025  lea     r9, [rsp+190h+cchName]; lpcchName
0x18005102a  lea     r8, [rsp+190h+SubKey]; lpName
0x18005102f  mov     [rsp+190h+cchName], 80h
0x180051037  call    cs:__imp_RegEnumKeyExW
0x18005103e  nop     dword ptr [rax+rax+00h]
0x180051043  mov     rcx, [rsp+190h+hKey]; hKey
0x180051048  mov     ebx, eax
0x18005104a  test    eax, eax
0x18005104c  jz      loc_180050FA0
0x180051052  call    cs:__imp_RegCloseKey
0x180051059  nop     dword ptr [rax+rax+00h]
0x18005105e  mov     ecx, ebx; dwErrCode
0x180051060  call    cs:__imp_SetLastError
0x180051067  nop     dword ptr [rax+rax+00h]
0x18005106c  mov     eax, 1
0x180051071  mov     rcx, [rbp+90h+var_30]
0x180051075  xor     rcx, rsp; StackCookie
0x180051078  call    __security_check_cookie
0x18005107d  add     rsp, 178h
0x180051084  pop     rdi
0x180051085  pop     rsi
0x180051086  pop     rbx
0x180051087  pop     rbp
0x180051088  retn
```
