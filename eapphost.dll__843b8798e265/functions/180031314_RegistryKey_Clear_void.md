# RegistryKey::Clear(void)

- ea: `0x180031314`
- end: `0x18003133f`
- name: `?Clear@RegistryKey@@QEAAXXZ`
- size: `43`
- prototype: `void __fastcall(RegistryKey *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012f60`
- `0x1800145f0`
- `0x180019c34`
- `0x18001a99c`
- `0x18001bc10`
- `0x18001c0a8`
- `0x18001c1e4`
- `0x1800277a8`
- `0x180031348`
- `0x180031424`

## callees

- `0x180031314`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031325`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031325`

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
0x180031314  push    rbx
0x180031316  sub     rsp, 20h
0x18003131a  mov     rbx, rcx
0x18003131d  mov     rcx, [rcx]; hKey
0x180031320  test    rcx, rcx
0x180031323  jz      short loc_180031338
0x180031325  call    cs:__imp_RegCloseKey
0x18003132c  nop     dword ptr [rax+rax+00h]
0x180031331  mov     qword ptr [rbx], 0
0x180031338  add     rsp, 20h
0x18003133c  pop     rbx
0x18003133d  retn
```
