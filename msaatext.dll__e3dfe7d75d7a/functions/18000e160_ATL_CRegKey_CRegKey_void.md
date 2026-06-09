# ATL::CRegKey::~CRegKey(void)

- ea: `0x18000e160`
- end: `0x18000e184`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013a0b`
- `0x180013a41`
- `0x180013a53`

## callees

- `0x18000e160`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000e171`
- `ADVAPI32!RegCloseKey` at `0x18000e171`

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
0x18000e160  push    rbx
0x18000e162  sub     rsp, 20h
0x18000e166  mov     rbx, rcx
0x18000e169  mov     rcx, [rcx]; hKey
0x18000e16c  test    rcx, rcx
0x18000e16f  jz      short loc_18000E17E
0x18000e171  call    cs:__imp_RegCloseKey
0x18000e177  mov     qword ptr [rbx], 0
0x18000e17e  add     rsp, 20h
0x18000e182  pop     rbx
0x18000e183  retn
```
