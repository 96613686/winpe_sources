# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x14001cb58`
- end: `0x14001cba4`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001cf70`
- `0x14001ddc4`
- `0x14001f060`
- `0x140020374`
- `0x140021068`

## callees

- `0x140005b50`
- `0x14001cb58`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14001cb99`
- `ADVAPI32!RegSetValueExW` at `0x14001cb99`

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
0x14001cb58  sub     rsp, 38h
0x14001cb5c  xor     r9d, r9d
0x14001cb5f  test    r8, r8
0x14001cb62  jnz     short loc_14001CB6F
0x14001cb64  mov     ecx, 80004005h; int
0x14001cb69  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001cb6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001cb73  inc     rax
0x14001cb76  cmp     [r8+rax*2], r9w
0x14001cb7b  jnz     short loc_14001CB73
0x14001cb7d  mov     rcx, [rcx]; hKey
0x14001cb80  lea     eax, ds:2[rax*2]
0x14001cb87  mov     [rsp+38h+cbData], eax; cbData
0x14001cb8b  mov     r9d, 1; dwType
0x14001cb91  mov     [rsp+38h+lpData], r8; lpData
0x14001cb96  xor     r8d, r8d; Reserved
0x14001cb99  call    cs:__imp_RegSetValueExW
0x14001cb9f  add     rsp, 38h
0x14001cba3  retn
```
