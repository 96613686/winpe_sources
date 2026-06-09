# ATL::CRegKey::~CRegKey(void)

- ea: `0x180002d20`
- end: `0x180002d44`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ab0a`
- `0x18000ab40`
- `0x18000ab52`

## callees

- `0x180002d20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d31`

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
0x180002d20  push    rbx
0x180002d22  sub     rsp, 20h
0x180002d26  mov     rbx, rcx
0x180002d29  mov     rcx, [rcx]; hKey
0x180002d2c  test    rcx, rcx
0x180002d2f  jz      short loc_180002D3E
0x180002d31  call    cs:__imp_RegCloseKey
0x180002d37  mov     qword ptr [rbx], 0
0x180002d3e  add     rsp, 20h
0x180002d42  pop     rbx
0x180002d43  retn
```
