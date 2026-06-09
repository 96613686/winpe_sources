# ATL::CRegKey::~CRegKey(void)

- ea: `0x1800030e0`
- end: `0x180003104`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008e2c`
- `0x18000a3b4`
- `0x18000aed4`
- `0x18000af5c`
- `0x180010a00`
- `0x180011270`
- `0x180011c38`
- `0x1800125f4`
- `0x180012606`
- `0x1800127fd`

## callees

- `0x1800030e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800030f1`

## pseudocode

```c
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
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
0x1800030e0  push    rbx
0x1800030e2  sub     rsp, 20h
0x1800030e6  mov     rbx, rcx
0x1800030e9  mov     rcx, [rcx]; hKey
0x1800030ec  test    rcx, rcx
0x1800030ef  jz      short loc_1800030FE
0x1800030f1  call    cs:__imp_RegCloseKey
0x1800030f7  mov     qword ptr [rbx], 0
0x1800030fe  add     rsp, 20h
0x180003102  pop     rbx
0x180003103  retn
```
