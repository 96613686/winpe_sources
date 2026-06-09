# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x1800086a8`
- end: `0x18000870b`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003dbc`

## callees

- `0x180004d04`
- `0x1800086a8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800086f4`
- `ADVAPI32!RegSetValueExW` at `0x1800086f4`

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
0x1800086a8  push    rbx
0x1800086aa  sub     rsp, 30h
0x1800086ae  xor     ebx, ebx
0x1800086b0  mov     r10, rdx
0x1800086b3  mov     r11, rcx
0x1800086b6  test    r8, r8
0x1800086b9  jz      short loc_180008700
0x1800086bb  mov     r9d, ebx
0x1800086be  mov     rdx, r8
0x1800086c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800086c5  inc     rcx
0x1800086c8  cmp     [rdx+rcx*2], bx
0x1800086cc  jnz     short loc_1800086C5
0x1800086ce  inc     ecx
0x1800086d0  lea     rdx, [rdx+rcx*2]
0x1800086d4  lea     r9d, [r9+rcx*2]
0x1800086d8  cmp     ecx, 1
0x1800086db  jnz     short loc_1800086C1
0x1800086dd  mov     [rsp+38h+cbData], r9d; cbData
0x1800086e2  mov     rdx, r10; lpValueName
0x1800086e5  mov     [rsp+38h+lpData], r8; lpData
0x1800086ea  lea     r9d, [rcx+6]; dwType
0x1800086ee  mov     rcx, [r11]; hKey
0x1800086f1  xor     r8d, r8d; Reserved
0x1800086f4  call    cs:__imp_RegSetValueExW
0x1800086fa  add     rsp, 30h
0x1800086fe  pop     rbx
0x1800086ff  retn
0x180008700  mov     ecx, 80004005h; int
0x180008705  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
