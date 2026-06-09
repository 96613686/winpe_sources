# ATL::CRegKey::~CRegKey(void)

- ea: `0x180002690`
- end: `0x1800026b4`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180010304`
- `0x180010316`
- `0x1800107df`
- `0x1800107f1`

## callees

- `0x180002690`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800026a1`
- `ADVAPI32!RegCloseKey` at `0x1800026a1`

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
0x180002690  push    rbx
0x180002692  sub     rsp, 20h
0x180002696  mov     rbx, rcx
0x180002699  mov     rcx, [rcx]; hKey
0x18000269c  test    rcx, rcx
0x18000269f  jz      short loc_1800026AE
0x1800026a1  call    cs:__imp_RegCloseKey
0x1800026a7  mov     qword ptr [rbx], 0
0x1800026ae  add     rsp, 20h
0x1800026b2  pop     rbx
0x1800026b3  retn
```
