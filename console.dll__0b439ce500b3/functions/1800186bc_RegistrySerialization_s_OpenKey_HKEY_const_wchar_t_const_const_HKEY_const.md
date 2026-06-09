# RegistrySerialization::s_OpenKey(HKEY__ * const,wchar_t const * const,HKEY__ * * const)

- ea: `0x1800186bc`
- end: `0x1800186de`
- name: `?s_OpenKey@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WQEAPEAU2@@Z`
- size: `34`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *const, HKEY *const)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800114d4`
- `0x180017368`
- `0x180018580`
- `0x1800188c0`

## callees

- `0x1800186bc`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800186c0`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800186c0`

## pseudocode

```c
LSTATUS __fastcall RegistrySerialization::s_OpenKey(HKEY a1, const WCHAR *a2, HKEY *const a3)
{
  LSTATUS result; // eax

  result = RegOpenKeyW(a1, a2, a3);
  if ( result > 0 )
    return (unsigned __int16)result | 0xC0070000;
  return result;
}

```

## disassembly

```asm
0x1800186bc  sub     rsp, 28h
0x1800186c0  call    cs:__imp_RegOpenKeyW
0x1800186c7  nop     dword ptr [rax+rax+00h]
0x1800186cc  test    eax, eax
0x1800186ce  jle     short loc_1800186D8
0x1800186d0  movzx   eax, ax
0x1800186d3  or      eax, 0C0070000h
0x1800186d8  add     rsp, 28h
0x1800186dc  retn
```
