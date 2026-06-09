# DeleteConfigParam

- ea: `0x180022e54`
- end: `0x180022eb4`
- name: `DeleteConfigParam`
- size: `96`
- prototype: `LSTATUS __fastcall(LPCSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180003ff0`
- `0x18000b1c8`

## callees

- `0x180022e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180022e99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180022e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180022e87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180022e87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022ea6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022ea6`

## string_xrefs

- `0x180022e80`: `System\CurrentControlSet\Services\NTDS\Parameters`

## pseudocode

```c
LSTATUS __fastcall DeleteConfigParam(LPCSTR lpValueName)
{
  LSTATUS result; // eax
  LSTATUS v3; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  result = RegOpenKeyExA(
             HKEY_LOCAL_MACHINE,
             "System\\CurrentControlSet\\Services\\NTDS\\Parameters",
             0,
             0x2000000u,
             &hKey);
  if ( !result )
  {
    v3 = RegDeleteValueA(hKey, lpValueName);
    RegCloseKey(hKey);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180022e54  push    rbx
0x180022e56  sub     rsp, 30h
0x180022e5a  mov     rbx, rcx
0x180022e5d  mov     [rsp+38h+hKey], 0
0x180022e66  lea     rax, [rsp+38h+hKey]
0x180022e6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022e72  mov     r9d, 2000000h; samDesired
0x180022e78  mov     [rsp+38h+phkResult], rax; phkResult
0x180022e7d  xor     r8d, r8d; ulOptions
0x180022e80  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\NT"...
0x180022e87  call    cs:__imp_RegOpenKeyExA
0x180022e8d  test    eax, eax
0x180022e8f  jnz     short loc_180022EAE
0x180022e91  mov     rcx, [rsp+38h+hKey]; hKey
0x180022e96  mov     rdx, rbx; lpValueName
0x180022e99  call    cs:__imp_RegDeleteValueA
0x180022e9f  mov     rcx, [rsp+38h+hKey]; hKey
0x180022ea4  mov     ebx, eax
0x180022ea6  call    cs:__imp_RegCloseKey
0x180022eac  mov     eax, ebx
0x180022eae  add     rsp, 30h
0x180022eb2  pop     rbx
0x180022eb3  retn
```
