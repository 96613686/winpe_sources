# SetConfigParam

- ea: `0x1800235f0`
- end: `0x18002369b`
- name: `SetConfigParam`
- size: `171`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180003ff0`
- `0x18000b1c8`

## callees

- `0x1800235f0`
- `0x180023814`
- `0x1800238b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023658`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180023658`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002367b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002367b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023688`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023688`

## string_xrefs

- `0x18002364a`: `System\CurrentControlSet\Services\NTDS\Parameters`

## pseudocode

```c
LSTATUS __fastcall SetConfigParam(LPCSTR lpValueName, __int64 a2, const BYTE *a3)
{
  int v5; // eax
  _DWORD *v6; // r8
  int v7; // r9d
  LSTATUS result; // eax
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider() )
  {
    v5 = CheckWPPLevelFlagsEnabledForProvider();
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), *v6, (_DWORD)v6, v7, v5);
  }
  result = RegOpenKeyExA(
             HKEY_LOCAL_MACHINE,
             "System\\CurrentControlSet\\Services\\NTDS\\Parameters",
             0,
             0x2000000u,
             &hKey);
  if ( !result )
  {
    v9 = RegSetValueExA(hKey, lpValueName, 0, 4u, a3, 4u);
    RegCloseKey(hKey);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800235f0  mov     [rsp+arg_0], rbx
0x1800235f5  push    rdi
0x1800235f6  sub     rsp, 60h
0x1800235fa  mov     rbx, r8
0x1800235fd  mov     [rsp+68h+hKey], 0
0x180023606  mov     rdi, rcx
0x180023609  call    CheckWPPLevelFlagsEnabledForProvider
0x18002360e  test    eax, eax
0x180023610  jz      short loc_180023637
0x180023612  call    CheckWPPLevelFlagsEnabledForProvider
0x180023617  mov     rcx, cs:WPP_GLOBAL_Control
0x18002361e  mov     edx, [r8]
0x180023621  mov     [rsp+68h+var_20], edx
0x180023625  mov     [rsp+68h+var_28], rdi
0x18002362a  mov     rcx, [rcx+10h]
0x18002362e  mov     dword ptr [rsp+68h+phkResult], eax
0x180023632  call    WPP_SF_sd
0x180023637  lea     rax, [rsp+68h+hKey]
0x18002363c  mov     r9d, 2000000h; samDesired
0x180023642  xor     r8d, r8d; ulOptions
0x180023645  mov     [rsp+68h+phkResult], rax; phkResult
0x18002364a  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\NT"...
0x180023651  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023658  call    cs:__imp_RegOpenKeyExA
0x18002365e  test    eax, eax
0x180023660  jnz     short loc_180023690
0x180023662  mov     rcx, [rsp+68h+hKey]; hKey
0x180023667  lea     r9d, [rax+4]; dwType
0x18002366b  mov     [rsp+68h+cbData], r9d; cbData
0x180023670  xor     r8d, r8d; Reserved
0x180023673  mov     rdx, rdi; lpValueName
0x180023676  mov     [rsp+68h+phkResult], rbx; lpData
0x18002367b  call    cs:__imp_RegSetValueExA
0x180023681  mov     rcx, [rsp+68h+hKey]; hKey
0x180023686  mov     ebx, eax
0x180023688  call    cs:__imp_RegCloseKey
0x18002368e  mov     eax, ebx
0x180023690  mov     rbx, [rsp+68h+arg_0]
0x180023695  add     rsp, 60h
0x180023699  pop     rdi
0x18002369a  retn
```
