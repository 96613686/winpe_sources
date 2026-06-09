# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180039b68`
- end: `0x180039bb4`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800193d4`
- `0x180019988`
- `0x18001a008`
- `0x18001a598`
- `0x18001a984`
- `0x18003d1a0`

## callees

- `0x180039b68`
- `0x180039bbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039ba9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039ba9`

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
0x180039b68  sub     rsp, 38h
0x180039b6c  xor     r9d, r9d
0x180039b6f  test    r8, r8
0x180039b72  jnz     short loc_180039B7F
0x180039b74  mov     ecx, 80004005h; int
0x180039b79  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180039b7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039b83  inc     rax
0x180039b86  cmp     [r8+rax*2], r9w
0x180039b8b  jnz     short loc_180039B83
0x180039b8d  mov     rcx, [rcx]; hKey
0x180039b90  lea     eax, ds:2[rax*2]
0x180039b97  mov     [rsp+38h+cbData], eax; cbData
0x180039b9b  mov     r9d, 1; dwType
0x180039ba1  mov     [rsp+38h+lpData], r8; lpData
0x180039ba6  xor     r8d, r8d; Reserved
0x180039ba9  call    cs:__imp_RegSetValueExW
0x180039baf  add     rsp, 38h
0x180039bb3  retn
```
