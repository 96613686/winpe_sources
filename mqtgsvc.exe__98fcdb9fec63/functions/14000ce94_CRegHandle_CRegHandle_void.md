# CRegHandle::~CRegHandle(void)

- ea: `0x14000ce94`
- end: `0x14000ceac`
- name: `??1CRegHandle@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d00c`
- `0x14000f444`
- `0x14000f4e4`
- `0x14000f59c`
- `0x1400115c8`
- `0x140011d38`
- `0x1400120e8`
- `0x140016024`
- `0x14001e1d8`
- `0x14001e614`
- `0x14001e626`
- `0x14001e638`
- `0x14001e930`
- `0x14001ea4d`
- `0x14001f2a0`

## callees

- `0x14000ce94`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000cea0`
- `ADVAPI32!RegCloseKey` at `0x14000cea0`

## pseudocode

```c
void __fastcall CRegHandle::~CRegHandle(HKEY *this)
{
  HKEY v1; // rcx

  v1 = *this;
  if ( v1 )
    RegCloseKey(v1);
}

```

## disassembly

```asm
0x14000ce94  sub     rsp, 28h
0x14000ce98  mov     rcx, [rcx]; hKey
0x14000ce9b  test    rcx, rcx
0x14000ce9e  jz      short loc_14000CEA7
0x14000cea0  call    cs:__imp_RegCloseKey
0x14000cea6  nop
0x14000cea7  add     rsp, 28h
0x14000ceab  retn
```
