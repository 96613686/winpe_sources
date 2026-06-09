# ATL::CRegKey::Close(void)

- ea: `0x180009a94`
- end: `0x180009aba`
- name: `?Close@CRegKey@ATL@@QEAAJXZ`
- size: `38`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008d28`
- `0x18000a6d0`
- `0x18000a9f8`
- `0x18000ae30`

## callees

- `0x180009a94`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180009aa7`
- `ADVAPI32!RegCloseKey` at `0x180009aa7`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::Close(HKEY *this)
{
  LSTATUS result; // eax
  HKEY v3; // rcx

  result = 0;
  v3 = *this;
  if ( v3 )
  {
    result = RegCloseKey(v3);
    *this = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009a94  push    rbx
0x180009a96  sub     rsp, 20h
0x180009a9a  mov     rbx, rcx
0x180009a9d  xor     eax, eax
0x180009a9f  mov     rcx, [rcx]; hKey
0x180009aa2  test    rcx, rcx
0x180009aa5  jz      short loc_180009AB4
0x180009aa7  call    cs:__imp_RegCloseKey
0x180009aad  mov     qword ptr [rbx], 0
0x180009ab4  add     rsp, 20h
0x180009ab8  pop     rbx
0x180009ab9  retn
```
