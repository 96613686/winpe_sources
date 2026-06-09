# RegistrySerialization::s_CreateKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)

- ea: `0x18001851c`
- end: `0x18001853e`
- name: `?s_CreateKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z`
- size: `34`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *const, HKEY *const)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011f44`
- `0x1800175e4`
- `0x180018580`

## callees

- `0x18001851c`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180018520`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180018520`

## pseudocode

```c
LSTATUS __fastcall RegistrySerialization::s_CreateKey(HKEY a1, const WCHAR *a2, HKEY *const a3)
{
  LSTATUS result; // eax

  result = RegCreateKeyW(a1, a2, a3);
  if ( result > 0 )
    return (unsigned __int16)result | 0xC0070000;
  return result;
}

```

## disassembly

```asm
0x18001851c  sub     rsp, 28h
0x180018520  call    cs:__imp_RegCreateKeyW
0x180018527  nop     dword ptr [rax+rax+00h]
0x18001852c  test    eax, eax
0x18001852e  jle     short loc_180018538
0x180018530  movzx   eax, ax
0x180018533  or      eax, 0C0070000h
0x180018538  add     rsp, 28h
0x18001853c  retn
```
