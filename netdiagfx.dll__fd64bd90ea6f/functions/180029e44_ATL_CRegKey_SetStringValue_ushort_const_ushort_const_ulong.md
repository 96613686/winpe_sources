# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180029e44`
- end: `0x180029e90`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028cdc`

## callees

- `0x180005c18`
- `0x180029e44`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180029e85`
- `ADVAPI32!RegSetValueExW` at `0x180029e85`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x180029e44  sub     rsp, 38h
0x180029e48  xor     r9d, r9d
0x180029e4b  test    r8, r8
0x180029e4e  jnz     short loc_180029E5B
0x180029e50  mov     ecx, 80004005h; int
0x180029e55  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180029e5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029e5f  inc     rax
0x180029e62  cmp     [r8+rax*2], r9w
0x180029e67  jnz     short loc_180029E5F
0x180029e69  mov     rcx, [rcx]; hKey
0x180029e6c  lea     eax, ds:2[rax*2]
0x180029e73  mov     [rsp+38h+cbData], eax; cbData
0x180029e77  mov     r9d, 1; dwType
0x180029e7d  mov     [rsp+38h+lpData], r8; lpData
0x180029e82  xor     r8d, r8d; Reserved
0x180029e85  call    cs:__imp_RegSetValueExW
0x180029e8b  add     rsp, 38h
0x180029e8f  retn
```
