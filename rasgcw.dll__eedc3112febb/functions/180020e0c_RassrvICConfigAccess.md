# RassrvICConfigAccess

- ea: `0x180020e0c`
- end: `0x180020f62`
- name: `RassrvICConfigAccess`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001ffac`
- `0x180020c48`

## callees

- `0x180020e0c`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020f42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020f42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020ed0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020ed0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020efd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020efd`
- `KERNEL32!RegQueryValueExW` at `0x180020f32`
- `KERNEL32!RegQueryValueExW` at `0x180020f32`

## string_xrefs

- `0x180020e8f`: `IcConfigured`
- `0x180020e2b`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall RassrvICConfigAccess(int a1, BYTE *a2)
{
  unsigned int v5; // ebx
  HKEY v6; // rcx
  HKEY hKey; // [rsp+30h] [rbp-89h] BYREF
  DWORD v8; // [rsp+38h] [rbp-81h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-7Dh] BYREF
  WCHAR ValueName[16]; // [rsp+40h] [rbp-79h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-59h] BYREF

  wcscpy(SubKey, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"Icfigured");
  if ( !a2 )
    return 87;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Fu, &hKey);
  if ( !v5 )
  {
    v6 = hKey;
    if ( a1 )
    {
      v5 = RegSetValueExW(hKey, ValueName, 0, 4u, a2, 4u);
    }
    else
    {
      Type = 0;
      v8 = 4;
      *(_DWORD *)a2 = 0;
      RegQueryValueExW(v6, ValueName, 0, &Type, a2, &v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180020e0c  push    rbp
0x180020e0e  push    rbx
0x180020e0f  push    rsi
0x180020e10  push    rdi
0x180020e11  lea     rbp, [rsp-3Fh]
0x180020e16  sub     rsp, 0F8h
0x180020e1d  mov     rax, cs:__security_cookie
0x180020e24  xor     rax, rsp
0x180020e27  mov     [rbp+57h+var_30], rax
0x180020e2b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180020e32  mov     rdi, rdx
0x180020e35  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+10h; "urrentControlSet\\Services\\RemoteAcces"...
0x180020e3c  mov     esi, ecx
0x180020e3e  mov     eax, dword ptr cs:aSystemCurrentc_0+70h; "s"
0x180020e44  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180020e48  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+20h; "ntrolSet\\Services\\RemoteAccess\\Param"...
0x180020e4f  movaps  [rbp+57h+var_90], xmm0
0x180020e53  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+40h; "s\\RemoteAccess\\Parameters"
0x180020e5a  movaps  [rbp+57h+var_A0], xmm1
0x180020e5e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+30h; "\\Services\\RemoteAccess\\Parameters"
0x180020e65  movaps  [rbp+57h+var_70], xmm0
0x180020e69  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+60h; "arameters"
0x180020e70  movaps  [rbp+57h+var_80], xmm1
0x180020e74  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+50h; "Access\\Parameters"
0x180020e7b  movaps  [rbp+57h+var_50], xmm0
0x180020e7f  movaps  [rbp+57h+var_60], xmm1
0x180020e83  mov     [rbp+57h+var_40], eax
0x180020e86  mov     [rsp+110h+hKey], 0
0x180020e8f  movups  xmm0, xmmword ptr cs:aIcconfigured; "IcConfigured"
0x180020e96  movups  xmm1, xmmword ptr cs:aIcconfigured+0Ah; "figured"
0x180020e9d  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180020ea1  movups  xmmword ptr [rbp+57h+ValueName+0Ah], xmm1
0x180020ea5  test    rdx, rdx
0x180020ea8  jnz     short loc_180020EB2
0x180020eaa  lea     eax, [rdx+57h]
0x180020ead  jmp     loc_180020F4A
0x180020eb2  lea     rax, [rsp+110h+hKey]
0x180020eb7  mov     r9d, 2001Fh; samDesired
0x180020ebd  xor     r8d, r8d; ulOptions
0x180020ec0  mov     [rsp+110h+phkResult], rax; phkResult
0x180020ec5  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180020ec9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020ed0  call    cs:__imp_RegOpenKeyExW
0x180020ed6  mov     ebx, eax
0x180020ed8  test    eax, eax
0x180020eda  jnz     short loc_180020F38
0x180020edc  mov     rcx, [rsp+110h+hKey]; hKey
0x180020ee1  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180020ee5  test    esi, esi
0x180020ee7  jz      short loc_180020F07
0x180020ee9  mov     [rsp+110h+cbData], 4; cbData
0x180020ef1  lea     r9d, [rax+4]; dwType
0x180020ef5  xor     r8d, r8d; Reserved
0x180020ef8  mov     [rsp+110h+phkResult], rdi; lpData
0x180020efd  call    cs:__imp_RegSetValueExW
0x180020f03  mov     ebx, eax
0x180020f05  jmp     short loc_180020F38
0x180020f07  lea     rax, [rsp+110h+var_D8]
0x180020f0c  mov     [rbp+57h+Type], 0
0x180020f13  mov     qword ptr [rsp+110h+cbData], rax; lpcbData
0x180020f18  lea     r9, [rbp+57h+Type]; lpType
0x180020f1c  xor     r8d, r8d; lpReserved
0x180020f1f  mov     [rsp+110h+phkResult], rdi; lpData
0x180020f24  mov     [rsp+110h+var_D8], 4
0x180020f2c  mov     dword ptr [rdi], 0
0x180020f32  call    cs:__imp_RegQueryValueExW
0x180020f38  mov     rcx, [rsp+110h+hKey]; hKey
0x180020f3d  test    rcx, rcx
0x180020f40  jz      short loc_180020F48
0x180020f42  call    cs:__imp_RegCloseKey
0x180020f48  mov     eax, ebx
0x180020f4a  mov     rcx, [rbp+57h+var_30]
0x180020f4e  xor     rcx, rsp; StackCookie
0x180020f51  call    __security_check_cookie
0x180020f56  add     rsp, 0F8h
0x180020f5d  pop     rdi
0x180020f5e  pop     rsi
0x180020f5f  pop     rbx
0x180020f60  pop     rbp
0x180020f61  retn
```
