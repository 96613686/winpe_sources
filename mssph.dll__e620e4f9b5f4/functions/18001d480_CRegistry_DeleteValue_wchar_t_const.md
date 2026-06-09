# CRegistry::DeleteValue(wchar_t const *)

- ea: `0x18001d480`
- end: `0x18001d4bf`
- name: `?DeleteValue@CRegistry@@UEAAHPEB_W@Z`
- size: `63`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001cab0`

## callees

- `0x18001d480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d495`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d4af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001d49f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001d49f`

## pseudocode

```c
__int64 __fastcall CRegistry::DeleteValue(CRegistry *this, const wchar_t *a2)
{
  HKEY v2; // rcx
  DWORD v3; // ecx
  LSTATUS v5; // eax

  v2 = (HKEY)*((_QWORD *)this + 22);
  if ( !v2 )
  {
    v3 = 6;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = RegDeleteValueW(v2, a2);
  if ( v5 )
  {
    v3 = v5;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x18001d480  sub     rsp, 28h
0x18001d484  mov     rcx, [rcx+0B0h]; hKey
0x18001d48b  test    rcx, rcx
0x18001d48e  jnz     short loc_18001D49F
0x18001d490  mov     ecx, 6; dwErrCode
0x18001d495  call    cs:__imp_SetLastError
0x18001d49b  xor     eax, eax
0x18001d49d  jmp     short loc_18001D4BA
0x18001d49f  call    cs:__imp_RegDeleteValueW
0x18001d4a5  test    eax, eax
0x18001d4a7  jz      short loc_18001D4AD
0x18001d4a9  mov     ecx, eax
0x18001d4ab  jmp     short loc_18001D495
0x18001d4ad  xor     ecx, ecx; dwErrCode
0x18001d4af  call    cs:__imp_SetLastError
0x18001d4b5  mov     eax, 1
0x18001d4ba  add     rsp, 28h
0x18001d4be  retn
```
