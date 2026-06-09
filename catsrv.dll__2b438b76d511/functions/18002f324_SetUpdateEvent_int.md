# _SetUpdateEvent(int)

- ea: `0x18002f324`
- end: `0x18002f417`
- name: `?_SetUpdateEvent@@YAHH@Z`
- size: `243`
- prototype: `_BOOL8 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180027320`
- `0x18002ee0c`

## callees

- `0x18002f324`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f400`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f38c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f3f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f38c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f3f3`

## string_xrefs

- `0x18002f349`: `Software\Classes\CLSID`
- `0x18002f3b6`: `Software\Classes\CLSID`

## pseudocode

```c
_BOOL8 __fastcall _SetUpdateEvent(int a1)
{
  LSTATUS v1; // ebx
  LSTATUS v2; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &hKey) )
    return 0;
  v1 = RegSetValueExW(hKey, L"CLBVersion", 0, 4u, (const BYTE *)&Data, 4u);
  RegCloseKey(hKey);
  if ( v1 || RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20206u, &hKey) )
    return 0;
  v2 = RegSetValueExW(hKey, L"CLBVersion", 0, 4u, (const BYTE *)&Data, 4u);
  RegCloseKey(hKey);
  return v2 == 0;
}

```

## disassembly

```asm
0x18002f324  mov     [rsp+Data], ecx
0x18002f328  push    rbx
0x18002f329  sub     rsp, 30h
0x18002f32d  lea     rax, [rsp+38h+hKey]
0x18002f332  mov     [rsp+38h+hKey], 0
0x18002f33b  mov     r9d, 20006h; samDesired
0x18002f341  mov     [rsp+38h+phkResult], rax; phkResult
0x18002f346  xor     r8d, r8d; ulOptions
0x18002f349  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\CLSID"
0x18002f350  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f357  call    cs:__imp_RegOpenKeyExW
0x18002f35d  test    eax, eax
0x18002f35f  jnz     loc_18002F40F
0x18002f365  mov     rcx, [rsp+38h+hKey]; hKey
0x18002f36a  lea     rax, [rsp+38h+Data]
0x18002f36f  mov     [rsp+38h+cbData], 4; cbData
0x18002f377  lea     rdx, aClbversion; "CLBVersion"
0x18002f37e  mov     r9d, 4; dwType
0x18002f384  mov     [rsp+38h+phkResult], rax; lpData
0x18002f389  xor     r8d, r8d; Reserved
0x18002f38c  call    cs:__imp_RegSetValueExW
0x18002f392  mov     rcx, [rsp+38h+hKey]; hKey
0x18002f397  mov     ebx, eax
0x18002f399  call    cs:__imp_RegCloseKey
0x18002f39f  test    ebx, ebx
0x18002f3a1  jnz     short loc_18002F40F
0x18002f3a3  lea     rax, [rsp+38h+hKey]
0x18002f3a8  mov     r9d, 20206h; samDesired
0x18002f3ae  xor     r8d, r8d; ulOptions
0x18002f3b1  mov     [rsp+38h+phkResult], rax; phkResult
0x18002f3b6  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\CLSID"
0x18002f3bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f3c4  call    cs:__imp_RegOpenKeyExW
0x18002f3ca  test    eax, eax
0x18002f3cc  jnz     short loc_18002F40F
0x18002f3ce  mov     rcx, [rsp+38h+hKey]; hKey
0x18002f3d3  lea     rax, [rsp+38h+Data]
0x18002f3d8  mov     [rsp+38h+cbData], 4; cbData
0x18002f3e0  lea     r9d, [rbx+4]; dwType
0x18002f3e4  xor     r8d, r8d; Reserved
0x18002f3e7  mov     [rsp+38h+phkResult], rax; lpData
0x18002f3ec  lea     rdx, aClbversion; "CLBVersion"
0x18002f3f3  call    cs:__imp_RegSetValueExW
0x18002f3f9  mov     rcx, [rsp+38h+hKey]; hKey
0x18002f3fe  mov     ebx, eax
0x18002f400  call    cs:__imp_RegCloseKey
0x18002f406  xor     eax, eax
0x18002f408  test    ebx, ebx
0x18002f40a  setz    al
0x18002f40d  jmp     short loc_18002F411
0x18002f40f  xor     eax, eax
0x18002f411  add     rsp, 30h
0x18002f415  pop     rbx
0x18002f416  retn
```
