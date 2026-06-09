# ATL::CRegKey::SetBinaryValue(ushort const *,void const *,ulong)

- ea: `0x1800441e4`
- end: `0x180044209`
- name: `?SetBinaryValue@CRegKey@ATL@@QEAAJPEBGPEBXK@Z`
- size: `37`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const void *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001a008`
- `0x18001a598`
- `0x18001a984`
- `0x18003d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800441fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800441fe`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetBinaryValue(
        HKEY *this,
        const unsigned __int16 *a2,
        const BYTE *lpData,
        DWORD cbData)
{
  return RegSetValueExW(*this, a2, 0, 3u, lpData, cbData);
}

```

## disassembly

```asm
0x1800441e4  sub     rsp, 38h
0x1800441e8  mov     rcx, [rcx]; hKey
0x1800441eb  mov     [rsp+38h+cbData], r9d; cbData
0x1800441f0  mov     r9d, 3; dwType
0x1800441f6  mov     [rsp+38h+lpData], r8; lpData
0x1800441fb  xor     r8d, r8d; Reserved
0x1800441fe  call    cs:__imp_RegSetValueExW
0x180044204  add     rsp, 38h
0x180044208  retn
```
