# AEUIDisabled(HKEY__ *)

- ea: `0x180006abc`
- end: `0x180006b0a`
- name: `?AEUIDisabled@@YAHPEAUHKEY__@@@Z`
- size: `78`
- prototype: `_BOOL8 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x180006abc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ae5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006ae5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006afc`

## pseudocode

```c
_BOOL8 __fastcall AEUIDisabled(HKEY a1)
{
  BOOL v1; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v1 = RegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment\\AEDisable", 0, 0x20019u, &hKey) == 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180006abc  push    rbx
0x180006abe  sub     rsp, 30h
0x180006ac2  lea     rax, [rsp+38h+hKey]
0x180006ac7  mov     [rsp+38h+hKey], 0
0x180006ad0  mov     r9d, 20019h; samDesired
0x180006ad6  mov     [rsp+38h+phkResult], rax; phkResult
0x180006adb  xor     r8d, r8d; ulOptions
0x180006ade  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x180006ae5  call    cs:__imp_RegOpenKeyExW
0x180006aeb  mov     rcx, [rsp+38h+hKey]; hKey
0x180006af0  xor     ebx, ebx
0x180006af2  test    eax, eax
0x180006af4  setz    bl
0x180006af7  test    rcx, rcx
0x180006afa  jz      short loc_180006B02
0x180006afc  call    cs:__imp_RegCloseKey
0x180006b02  mov     eax, ebx
0x180006b04  add     rsp, 30h
0x180006b08  pop     rbx
0x180006b09  retn
```
