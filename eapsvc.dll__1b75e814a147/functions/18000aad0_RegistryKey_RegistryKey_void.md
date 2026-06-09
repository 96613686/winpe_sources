# RegistryKey::~RegistryKey(void)

- ea: `0x18000aad0`
- end: `0x18000aaf4`
- name: `??1RegistryKey@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015350`
- `0x1800155b0`
- `0x1800155f8`
- `0x180015dc1`

## callees

- `0x18000aad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aae1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aae1`

## pseudocode

```c
void __fastcall RegistryKey::~RegistryKey(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000aad0  push    rbx
0x18000aad2  sub     rsp, 20h
0x18000aad6  mov     rbx, rcx
0x18000aad9  mov     rcx, [rcx]; hKey
0x18000aadc  test    rcx, rcx
0x18000aadf  jz      short loc_18000AAEE
0x18000aae1  call    cs:__imp_RegCloseKey
0x18000aae7  mov     qword ptr [rbx], 0
0x18000aaee  add     rsp, 20h
0x18000aaf2  pop     rbx
0x18000aaf3  retn
```
