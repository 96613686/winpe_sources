# ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)

- ea: `0x180016c04`
- end: `0x180016c67`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001399c`

## callees

- `0x180014178`
- `0x180016c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c50`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c50`

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
0x180016c04  push    rbx
0x180016c06  sub     rsp, 30h
0x180016c0a  xor     ebx, ebx
0x180016c0c  mov     r10, rdx
0x180016c0f  mov     r11, rcx
0x180016c12  test    r8, r8
0x180016c15  jz      short loc_180016C5C
0x180016c17  mov     r9d, ebx
0x180016c1a  mov     rdx, r8
0x180016c1d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016c21  inc     rcx
0x180016c24  cmp     [rdx+rcx*2], bx
0x180016c28  jnz     short loc_180016C21
0x180016c2a  inc     ecx
0x180016c2c  lea     rdx, [rdx+rcx*2]
0x180016c30  lea     r9d, [r9+rcx*2]
0x180016c34  cmp     ecx, 1
0x180016c37  jnz     short loc_180016C1D
0x180016c39  mov     [rsp+38h+cbData], r9d; cbData
0x180016c3e  mov     rdx, r10; lpValueName
0x180016c41  mov     [rsp+38h+lpData], r8; lpData
0x180016c46  lea     r9d, [rcx+6]; dwType
0x180016c4a  mov     rcx, [r11]; hKey
0x180016c4d  xor     r8d, r8d; Reserved
0x180016c50  call    cs:__imp_RegSetValueExW
0x180016c56  add     rsp, 30h
0x180016c5a  pop     rbx
0x180016c5b  retn
0x180016c5c  mov     ecx, 80004005h; int
0x180016c61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
