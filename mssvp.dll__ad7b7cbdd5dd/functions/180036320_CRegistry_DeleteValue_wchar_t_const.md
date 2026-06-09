# CRegistry::DeleteValue(wchar_t const *)

- ea: `0x180036320`
- end: `0x18003635f`
- name: `?DeleteValue@CRegistry@@UEAAHPEB_W@Z`
- size: `63`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180036320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036335`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003634f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036335`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003634f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003633f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003633f`

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
0x180036320  sub     rsp, 28h
0x180036324  mov     rcx, [rcx+0B0h]; hKey
0x18003632b  test    rcx, rcx
0x18003632e  jnz     short loc_18003633F
0x180036330  mov     ecx, 6; dwErrCode
0x180036335  call    cs:__imp_SetLastError
0x18003633b  xor     eax, eax
0x18003633d  jmp     short loc_18003635A
0x18003633f  call    cs:__imp_RegDeleteValueW
0x180036345  test    eax, eax
0x180036347  jz      short loc_18003634D
0x180036349  mov     ecx, eax
0x18003634b  jmp     short loc_180036335
0x18003634d  xor     ecx, ecx; dwErrCode
0x18003634f  call    cs:__imp_SetLastError
0x180036355  mov     eax, 1
0x18003635a  add     rsp, 28h
0x18003635e  retn
```
