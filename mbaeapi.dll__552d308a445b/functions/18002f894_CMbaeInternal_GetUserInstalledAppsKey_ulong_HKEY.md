# CMbaeInternal::_GetUserInstalledAppsKey(ulong,HKEY__ * *)

- ea: `0x18002f894`
- end: `0x18002f93a`
- name: `?_GetUserInstalledAppsKey@CMbaeInternal@@AEAAJKPEAPEAUHKEY__@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(CMbaeInternal *this, REGSAM samDesired, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800305d0`
- `0x180030a74`

## callees

- `0x1800156cc`
- `0x18002f894`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f919`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f8ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f8ea`

## string_xrefs

- `0x18002f8dc`: `Software\Microsoft\Windows\CurrentVersion\MobileBroadbandAccounts\InstalledCompanionApps`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CMbaeInternal::_GetUserInstalledAppsKey(CMbaeInternal *this, REGSAM samDesired, HKEY *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  hKey = 0;
  v4 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\MobileBroadbandAccounts\\InstalledCompanionApps",
         0,
         0,
         0,
         samDesired,
         0,
         &hKey,
         0);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x36D,
           (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cmbaeinternal.cpp",
           (const char *)v4,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  else
  {
    *a3 = hKey;
    return 0;
  }
}

```

## disassembly

```asm
0x18002f894  mov     r11, rsp
0x18002f897  mov     [r11+8], rcx
0x18002f89b  push    rbx
0x18002f89c  sub     rsp, 50h
0x18002f8a0  mov     rbx, r8
0x18002f8a3  mov     qword ptr [r8], 0
0x18002f8aa  mov     qword ptr [r11+8], 0
0x18002f8b2  mov     qword ptr [r11-18h], 0
0x18002f8ba  lea     rax, [r11+8]
0x18002f8be  mov     [r11-20h], rax
0x18002f8c2  mov     qword ptr [r11-28h], 0
0x18002f8ca  mov     [rsp+58h+samDesired], edx; samDesired
0x18002f8ce  mov     [rsp+58h+dwOptions], 0; unsigned int
0x18002f8d6  xor     r9d, r9d; lpClass
0x18002f8d9  xor     r8d, r8d; Reserved
0x18002f8dc  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002f8e3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002f8ea  call    cs:__imp_RegCreateKeyExW
0x18002f8f0  test    eax, eax
0x18002f8f2  jz      short loc_18002F923
0x18002f8f4  mov     rcx, [rsp+58h]; this
0x18002f8f9  mov     r9d, eax; char *
0x18002f8fc  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18002f903  mov     edx, 36Dh; void *
0x18002f908  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f90d  mov     ebx, eax
0x18002f90f  mov     rcx, [rsp+58h+hKey]; hKey
0x18002f914  test    rcx, rcx
0x18002f917  jz      short loc_18002F91F
0x18002f919  call    cs:__imp_RegCloseKey
0x18002f91f  mov     eax, ebx
0x18002f921  jmp     short loc_18002F933
0x18002f923  mov     rax, [rsp+58h+hKey]
0x18002f928  mov     [rbx], rax
0x18002f92b  xor     eax, eax
0x18002f92d  jmp     short loc_18002F933
0x18002f92f  mov     eax, dword ptr [rsp+58h+hKey]
0x18002f933  add     rsp, 50h
0x18002f937  pop     rbx
0x18002f938  retn
```
