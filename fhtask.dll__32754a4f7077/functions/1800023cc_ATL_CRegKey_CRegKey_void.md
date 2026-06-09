# ATL::CRegKey::~CRegKey(void)

- ea: `0x1800023cc`
- end: `0x1800023f0`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f74`
- `0x180009f86`

## callees

- `0x1800023cc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800023dd`
- `ADVAPI32!RegCloseKey` at `0x1800023dd`

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
0x1800023cc  push    rbx
0x1800023ce  sub     rsp, 20h
0x1800023d2  mov     rbx, rcx
0x1800023d5  mov     rcx, [rcx]; hKey
0x1800023d8  test    rcx, rcx
0x1800023db  jz      short loc_1800023EA
0x1800023dd  call    cs:__imp_RegCloseKey
0x1800023e3  mov     qword ptr [rbx], 0
0x1800023ea  add     rsp, 20h
0x1800023ee  pop     rbx
0x1800023ef  retn
```
