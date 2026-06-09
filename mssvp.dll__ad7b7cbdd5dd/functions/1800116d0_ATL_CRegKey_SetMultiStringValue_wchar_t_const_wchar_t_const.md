# ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)

- ea: `0x1800116d0`
- end: `0x180011733`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b6ac`
- `0x18002dd8c`

## callees

- `0x18000419c`
- `0x1800116d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011727`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011727`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetMultiStringValue(HKEY *this, const wchar_t *a2, const BYTE *lpData)
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
0x1800116d0  push    rbx
0x1800116d2  sub     rsp, 30h
0x1800116d6  xor     ebx, ebx
0x1800116d8  mov     r10, rdx
0x1800116db  mov     r11, rcx
0x1800116de  test    r8, r8
0x1800116e1  jnz     short loc_1800116EE
0x1800116e3  mov     ecx, 80004005h; int
0x1800116e8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800116ee  mov     r9d, ebx
0x1800116f1  mov     rdx, r8
0x1800116f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800116f8  inc     rcx
0x1800116fb  cmp     [rdx+rcx*2], bx
0x1800116ff  jnz     short loc_1800116F8
0x180011701  inc     ecx
0x180011703  lea     rdx, [rdx+rcx*2]
0x180011707  lea     r9d, [r9+rcx*2]
0x18001170b  cmp     ecx, 1
0x18001170e  jnz     short loc_1800116F4
0x180011710  mov     [rsp+38h+cbData], r9d; cbData
0x180011715  mov     rdx, r10; lpValueName
0x180011718  mov     [rsp+38h+lpData], r8; lpData
0x18001171d  lea     r9d, [rcx+6]; dwType
0x180011721  mov     rcx, [r11]; hKey
0x180011724  xor     r8d, r8d; Reserved
0x180011727  call    cs:__imp_RegSetValueExW
0x18001172d  add     rsp, 30h
0x180011731  pop     rbx
0x180011732  retn
```
