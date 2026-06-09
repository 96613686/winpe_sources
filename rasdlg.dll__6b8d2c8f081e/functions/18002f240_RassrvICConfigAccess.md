# RassrvICConfigAccess

- ea: `0x18002f240`
- end: `0x18002f396`
- name: `RassrvICConfigAccess`
- size: `342`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002df80`
- `0x18002ec90`
- `0x18002f0dc`

## callees

- `0x18002f240`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f304`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f376`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f331`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f331`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f366`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f366`

## string_xrefs

- `0x18002f25f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18002f2c3`: `IcConfigured`

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
0x18002f240  push    rbp
0x18002f242  push    rbx
0x18002f243  push    rsi
0x18002f244  push    rdi
0x18002f245  lea     rbp, [rsp-3Fh]
0x18002f24a  sub     rsp, 0F8h
0x18002f251  mov     rax, cs:__security_cookie
0x18002f258  xor     rax, rsp
0x18002f25b  mov     [rbp+57h+var_30], rax
0x18002f25f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18002f266  mov     rdi, rdx
0x18002f269  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+10h; "urrentControlSet\\Services\\RemoteAcces"...
0x18002f270  mov     esi, ecx
0x18002f272  mov     eax, dword ptr cs:aSystemCurrentc_0+70h; "s"
0x18002f278  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18002f27c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+20h; "ntrolSet\\Services\\RemoteAccess\\Param"...
0x18002f283  movaps  [rbp+57h+var_90], xmm0
0x18002f287  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+40h; "s\\RemoteAccess\\Parameters"
0x18002f28e  movaps  [rbp+57h+var_A0], xmm1
0x18002f292  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+30h; "\\Services\\RemoteAccess\\Parameters"
0x18002f299  movaps  [rbp+57h+var_70], xmm0
0x18002f29d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_0+60h; "arameters"
0x18002f2a4  movaps  [rbp+57h+var_80], xmm1
0x18002f2a8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_0+50h; "Access\\Parameters"
0x18002f2af  movaps  [rbp+57h+var_50], xmm0
0x18002f2b3  movaps  [rbp+57h+var_60], xmm1
0x18002f2b7  mov     [rbp+57h+var_40], eax
0x18002f2ba  mov     [rsp+110h+hKey], 0
0x18002f2c3  movups  xmm0, xmmword ptr cs:aIcconfigured; "IcConfigured"
0x18002f2ca  movups  xmm1, xmmword ptr cs:aIcconfigured+0Ah; "figured"
0x18002f2d1  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18002f2d5  movups  xmmword ptr [rbp+57h+ValueName+0Ah], xmm1
0x18002f2d9  test    rdx, rdx
0x18002f2dc  jnz     short loc_18002F2E6
0x18002f2de  lea     eax, [rdx+57h]
0x18002f2e1  jmp     loc_18002F37E
0x18002f2e6  lea     rax, [rsp+110h+hKey]
0x18002f2eb  mov     r9d, 2001Fh; samDesired
0x18002f2f1  xor     r8d, r8d; ulOptions
0x18002f2f4  mov     [rsp+110h+phkResult], rax; phkResult
0x18002f2f9  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18002f2fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f304  call    cs:__imp_RegOpenKeyExW
0x18002f30a  mov     ebx, eax
0x18002f30c  test    eax, eax
0x18002f30e  jnz     short loc_18002F36C
0x18002f310  mov     rcx, [rsp+110h+hKey]; hKey
0x18002f315  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18002f319  test    esi, esi
0x18002f31b  jz      short loc_18002F33B
0x18002f31d  mov     [rsp+110h+cbData], 4; cbData
0x18002f325  lea     r9d, [rax+4]; dwType
0x18002f329  xor     r8d, r8d; Reserved
0x18002f32c  mov     [rsp+110h+phkResult], rdi; lpData
0x18002f331  call    cs:__imp_RegSetValueExW
0x18002f337  mov     ebx, eax
0x18002f339  jmp     short loc_18002F36C
0x18002f33b  lea     rax, [rsp+110h+var_D8]
0x18002f340  mov     [rbp+57h+Type], 0
0x18002f347  mov     qword ptr [rsp+110h+cbData], rax; lpcbData
0x18002f34c  lea     r9, [rbp+57h+Type]; lpType
0x18002f350  xor     r8d, r8d; lpReserved
0x18002f353  mov     [rsp+110h+phkResult], rdi; lpData
0x18002f358  mov     [rsp+110h+var_D8], 4
0x18002f360  mov     dword ptr [rdi], 0
0x18002f366  call    cs:__imp_RegQueryValueExW
0x18002f36c  mov     rcx, [rsp+110h+hKey]; hKey
0x18002f371  test    rcx, rcx
0x18002f374  jz      short loc_18002F37C
0x18002f376  call    cs:__imp_RegCloseKey
0x18002f37c  mov     eax, ebx
0x18002f37e  mov     rcx, [rbp+57h+var_30]
0x18002f382  xor     rcx, rsp; StackCookie
0x18002f385  call    __security_check_cookie
0x18002f38a  add     rsp, 0F8h
0x18002f391  pop     rdi
0x18002f392  pop     rsi
0x18002f393  pop     rbx
0x18002f394  pop     rbp
0x18002f395  retn
```
