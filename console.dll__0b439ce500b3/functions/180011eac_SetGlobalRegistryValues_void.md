# SetGlobalRegistryValues(void)

- ea: `0x180011eac`
- end: `0x180011f3c`
- name: `?SetGlobalRegistryValues@@YAXXZ`
- size: `144`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180007e0c`
- `0x180011f44`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180011ee7`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180011f2a`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180011ee7`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x180011f2a`

## pseudocode

```c
void SetGlobalRegistryValues(void)
{
  BOOL pvData; // [rsp+40h] [rbp+8h] BYREF
  UINT v1; // [rsp+48h] [rbp+10h] BYREF

  pvData = g_fForceV2;
  SHSetValueW(HKEY_CURRENT_USER, L"Console", L"ForceV2", 4u, &pvData, 4u);
  v1 = g_fEditKeys;
  SHSetValueW(HKEY_CURRENT_USER, L"Console", L"ExtendedEditKey", 4u, &v1, 4u);
}

```

## disassembly

```asm
0x180011eac  sub     rsp, 38h
0x180011eb0  mov     eax, cs:?g_fForceV2@@3HA; int g_fForceV2
0x180011eb6  lea     r8, pszValue; "ForceV2"
0x180011ebd  mov     [rsp+38h+arg_0], eax
0x180011ec1  lea     rdx, aConsole; "Console"
0x180011ec8  lea     rax, [rsp+38h+arg_0]
0x180011ecd  mov     [rsp+38h+cbData], 4; cbData
0x180011ed5  mov     r9d, 4; dwType
0x180011edb  mov     [rsp+38h+pvData], rax; pvData
0x180011ee0  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180011ee7  call    cs:__imp_SHSetValueW
0x180011eee  nop     dword ptr [rax+rax+00h]
0x180011ef3  mov     eax, cs:?g_fEditKeys@@3HA; int g_fEditKeys
0x180011ef9  lea     r8, aExtendededitke; "ExtendedEditKey"
0x180011f00  mov     [rsp+38h+arg_8], eax
0x180011f04  lea     rdx, aConsole; "Console"
0x180011f0b  lea     rax, [rsp+38h+arg_8]
0x180011f10  mov     [rsp+38h+cbData], 4; cbData
0x180011f18  mov     r9d, 4; dwType
0x180011f1e  mov     [rsp+38h+pvData], rax; pvData
0x180011f23  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180011f2a  call    cs:__imp_SHSetValueW
0x180011f31  nop     dword ptr [rax+rax+00h]
0x180011f36  add     rsp, 38h
0x180011f3a  retn
```
