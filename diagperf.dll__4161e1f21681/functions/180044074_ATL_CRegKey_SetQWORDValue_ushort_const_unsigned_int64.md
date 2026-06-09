# ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)

- ea: `0x180044074`
- end: `0x1800440a6`
- name: `?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z`
- size: `50`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001a008`
- `0x18001a598`
- `0x18001a984`
- `0x18003d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004409b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004409b`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetQWORDValue(HKEY *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  return RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
}

```

## disassembly

```asm
0x180044074  mov     [rsp+Data], r8
0x180044079  sub     rsp, 38h
0x18004407d  mov     rcx, [rcx]; hKey
0x180044080  lea     rax, [rsp+38h+Data]
0x180044085  mov     [rsp+38h+cbData], 8; cbData
0x18004408d  mov     r9d, 0Bh; dwType
0x180044093  xor     r8d, r8d; Reserved
0x180044096  mov     [rsp+38h+lpData], rax; lpData
0x18004409b  call    cs:__imp_RegSetValueExW
0x1800440a1  add     rsp, 38h
0x1800440a5  retn
```
