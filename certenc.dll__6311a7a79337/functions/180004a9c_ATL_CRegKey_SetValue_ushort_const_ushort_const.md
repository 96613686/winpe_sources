# ATL::CRegKey::SetValue(ushort const *,ushort const *)

- ea: `0x180004a9c`
- end: `0x180004adb`
- name: `?SetValue@CRegKey@ATL@@QEAAJPEBG0@Z`
- size: `63`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004170`
- `0x180004788`
- `0x180004a1c`

## callees

- `0x180004a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004ad0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004ad0`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetValue(HKEY *this, const BYTE *lpData, const unsigned __int16 *a3)
{
  __int64 v3; // rax

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a3, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x180004a9c  sub     rsp, 38h
0x180004aa0  mov     r10, r8
0x180004aa3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004aa7  inc     rax
0x180004aaa  cmp     word ptr [rdx+rax*2], 0
0x180004aaf  jnz     short loc_180004AA7
0x180004ab1  mov     rcx, [rcx]; hKey
0x180004ab4  lea     eax, ds:2[rax*2]
0x180004abb  mov     [rsp+38h+cbData], eax; cbData
0x180004abf  mov     r9d, 1; dwType
0x180004ac5  mov     [rsp+38h+lpData], rdx; lpData
0x180004aca  xor     r8d, r8d; Reserved
0x180004acd  mov     rdx, r10; lpValueName
0x180004ad0  call    cs:__imp_RegSetValueExW
0x180004ad6  add     rsp, 38h
0x180004ada  retn
```
