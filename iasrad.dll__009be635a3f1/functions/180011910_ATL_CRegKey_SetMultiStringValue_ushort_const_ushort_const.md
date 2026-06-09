# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x180011910`
- end: `0x180011973`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ea4c`

## callees

- `0x18000afe0`
- `0x180011910`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001195c`
- `ADVAPI32!RegSetValueExW` at `0x18001195c`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetMultiStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  DWORD cbData; // r9d
  const BYTE *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  cbData = 0;
  v6 = lpData;
  do
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
    v8 = (unsigned int)(v7 + 1);
    v6 += 2 * v8;
    cbData += 2 * v8;
  }
  while ( (_DWORD)v8 != 1 );
  return RegSetValueExW(*this, a2, 0, 7u, lpData, cbData);
}

```

## disassembly

```asm
0x180011910  push    rbx
0x180011912  sub     rsp, 30h
0x180011916  xor     ebx, ebx
0x180011918  mov     r10, rdx
0x18001191b  mov     r11, rcx
0x18001191e  test    r8, r8
0x180011921  jz      short loc_180011968
0x180011923  mov     r9d, ebx
0x180011926  mov     rdx, r8
0x180011929  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001192d  inc     rcx
0x180011930  cmp     [rdx+rcx*2], bx
0x180011934  jnz     short loc_18001192D
0x180011936  inc     ecx
0x180011938  lea     rdx, [rdx+rcx*2]
0x18001193c  lea     r9d, [r9+rcx*2]
0x180011940  cmp     ecx, 1
0x180011943  jnz     short loc_180011929
0x180011945  mov     [rsp+38h+cbData], r9d; cbData
0x18001194a  mov     rdx, r10; lpValueName
0x18001194d  mov     [rsp+38h+lpData], r8; lpData
0x180011952  lea     r9d, [rcx+6]; dwType
0x180011956  mov     rcx, [r11]; hKey
0x180011959  xor     r8d, r8d; Reserved
0x18001195c  call    cs:__imp_RegSetValueExW
0x180011962  add     rsp, 30h
0x180011966  pop     rbx
0x180011967  retn
0x180011968  mov     ecx, 80004005h; int
0x18001196d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
