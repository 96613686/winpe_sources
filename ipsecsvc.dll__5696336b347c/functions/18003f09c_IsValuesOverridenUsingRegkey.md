# IsValuesOverridenUsingRegkey

- ea: `0x18003f09c`
- end: `0x18003f160`
- name: `IsValuesOverridenUsingRegkey`
- size: `196`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f168`

## callees

- `0x18003f09c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f127`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f127`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f0de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f0de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f146`

## string_xrefs

- `0x18003f0cb`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Group Policy\Cache`

## pseudocode

```c
bool __fastcall IsValuesOverridenUsingRegkey(__int64 a1)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  LSTATUS v3; // eax
  bool result; // al
  int Data; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  v6 = HIDWORD(a1);
  hKey = 0;
  Data = 0;
  Type = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Cache",
         0,
         0x20019u,
         &hKey);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"ForceKerberosOverride", 0, &Type, (LPBYTE)&Data, &cbData);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  result = 0;
  if ( v2 >= 0 )
    return Data == 1;
  return result;
}

```

## disassembly

```asm
0x18003f09c  mov     rax, rsp
0x18003f09f  mov     [rax+8], rcx
0x18003f0a3  push    rbx
0x18003f0a4  sub     rsp, 30h
0x18003f0a8  mov     qword ptr [rax+20h], 0
0x18003f0b0  mov     r9d, 20019h; samDesired
0x18003f0b6  mov     dword ptr [rax+8], 0
0x18003f0bd  xor     r8d, r8d; ulOptions
0x18003f0c0  mov     dword ptr [rax+18h], 0
0x18003f0c7  lea     rax, [rax+20h]
0x18003f0cb  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003f0d2  mov     [rsp+38h+phkResult], rax; phkResult
0x18003f0d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f0de  call    cs:__imp_RegOpenKeyExW
0x18003f0e4  mov     ebx, eax
0x18003f0e6  test    eax, eax
0x18003f0e8  jle     short loc_18003F0F3
0x18003f0ea  movzx   ebx, ax
0x18003f0ed  or      ebx, 80070000h
0x18003f0f3  test    ebx, ebx
0x18003f0f5  js      short loc_18003F13C
0x18003f0f7  mov     rcx, [rsp+38h+hKey]; hKey
0x18003f0fc  lea     rax, [rsp+38h+cbData]
0x18003f101  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003f106  lea     r9, [rsp+38h+Type]; lpType
0x18003f10b  lea     rax, [rsp+38h+Data]
0x18003f110  mov     [rsp+38h+cbData], 4
0x18003f118  xor     r8d, r8d; lpReserved
0x18003f11b  mov     [rsp+38h+phkResult], rax; lpData
0x18003f120  lea     rdx, aForcekerberoso; "ForceKerberosOverride"
0x18003f127  call    cs:__imp_RegQueryValueExW
0x18003f12d  mov     ebx, eax
0x18003f12f  test    eax, eax
0x18003f131  jle     short loc_18003F13C
0x18003f133  movzx   ebx, ax
0x18003f136  or      ebx, 80070000h
0x18003f13c  mov     rcx, [rsp+38h+hKey]; hKey
0x18003f141  test    rcx, rcx
0x18003f144  jz      short loc_18003F14C
0x18003f146  call    cs:__imp_RegCloseKey
0x18003f14c  xor     eax, eax
0x18003f14e  test    ebx, ebx
0x18003f150  js      short loc_18003F15A
0x18003f152  cmp     [rsp+38h+Data], 1
0x18003f157  setz    al
0x18003f15a  add     rsp, 30h
0x18003f15e  pop     rbx
0x18003f15f  retn
```
