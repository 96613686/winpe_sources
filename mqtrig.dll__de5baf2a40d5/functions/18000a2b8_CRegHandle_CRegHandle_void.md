# CRegHandle::~CRegHandle(void)

- ea: `0x18000a2b8`
- end: `0x18000a2d0`
- name: `??1CRegHandle@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b760`
- `0x180012770`
- `0x18001557c`
- `0x18001561c`
- `0x1800156d4`
- `0x180016944`
- `0x180016b50`
- `0x180017070`
- `0x1800173dc`
- `0x180019230`
- `0x1800199a0`
- `0x180019b4c`
- `0x180019dc0`
- `0x18001a358`
- `0x18001a718`
- `0x18001fbe7`
- `0x18001fbf9`
- `0x18002094b`
- `0x18002095d`
- `0x180020c20`
- `0x180020c32`
- `0x180020e98`
- `0x180020eaa`
- `0x18002140b`
- `0x18002141d`
- `0x180021528`
- `0x1800215b3`
- `0x180021b30`

## callees

- `0x18000a2b8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000a2c4`
- `ADVAPI32!RegCloseKey` at `0x18000a2c4`

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
0x18000a2b8  sub     rsp, 28h
0x18000a2bc  mov     rcx, [rcx]; hKey
0x18000a2bf  test    rcx, rcx
0x18000a2c2  jz      short loc_18000A2CB
0x18000a2c4  call    cs:__imp_RegCloseKey
0x18000a2ca  nop
0x18000a2cb  add     rsp, 28h
0x18000a2cf  retn
```
