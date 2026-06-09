# RegistryKey::Clear(void)

- ea: `0x1800300fc`
- end: `0x180030120`
- name: `?Clear@RegistryKey@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(RegistryKey *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800127d0`
- `0x180013e00`
- `0x18001926c`
- `0x180019fbc`
- `0x18001b200`
- `0x18001b698`
- `0x18001b7cc`
- `0x180026a4c`
- `0x180030128`
- `0x1800301fc`

## callees

- `0x1800300fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003010d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003010d`

## pseudocode

```c
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
0x1800300fc  push    rbx
0x1800300fe  sub     rsp, 20h
0x180030102  mov     rbx, rcx
0x180030105  mov     rcx, [rcx]; hKey
0x180030108  test    rcx, rcx
0x18003010b  jz      short loc_18003011A
0x18003010d  call    cs:__imp_RegCloseKey
0x180030113  mov     qword ptr [rbx], 0
0x18003011a  add     rsp, 20h
0x18003011e  pop     rbx
0x18003011f  retn
```
