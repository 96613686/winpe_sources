# RegistryKey::Clear(void)

- ea: `0x18002a7dc`
- end: `0x18002a800`
- name: `?Clear@RegistryKey@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180020508`
- `0x1800213a8`
- `0x1800247e0`
- `0x18002990c`
- `0x18002a808`
- `0x18002a8dc`
- `0x18002b8dc`
- `0x18002ca50`
- `0x18002cee8`
- `0x18002d040`

## callees

- `0x18002a7dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a7ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RegistryKey::Clear(HKEY *this)
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
0x18002a7dc  push    rbx
0x18002a7de  sub     rsp, 20h
0x18002a7e2  mov     rbx, rcx
0x18002a7e5  mov     rcx, [rcx]; hKey
0x18002a7e8  test    rcx, rcx
0x18002a7eb  jz      short loc_18002A7FA
0x18002a7ed  call    cs:__imp_RegCloseKey
0x18002a7f3  mov     qword ptr [rbx], 0
0x18002a7fa  add     rsp, 20h
0x18002a7fe  pop     rbx
0x18002a7ff  retn
```
