# CRegistry::DeleteSubKey(wchar_t const *)

- ea: `0x18001d2a4`
- end: `0x18001d2e9`
- name: `?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z`
- size: `69`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d2f0`

## callees

- `0x18001d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d2b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d2d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d2b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d2d9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001d2c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001d2c9`

## pseudocode

```c
__int64 __fastcall CRegistry::DeleteSubKey(CRegistry *this, const wchar_t *a2)
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
  v5 = RegDeleteKeyExW(v2, a2, 0, 0);
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
0x18001d2a4  sub     rsp, 28h
0x18001d2a8  mov     rcx, [rcx+0B0h]; hKey
0x18001d2af  test    rcx, rcx
0x18001d2b2  jnz     short loc_18001D2C3
0x18001d2b4  mov     ecx, 6; dwErrCode
0x18001d2b9  call    cs:__imp_SetLastError
0x18001d2bf  xor     eax, eax
0x18001d2c1  jmp     short loc_18001D2E4
0x18001d2c3  xor     r9d, r9d; Reserved
0x18001d2c6  xor     r8d, r8d; samDesired
0x18001d2c9  call    cs:__imp_RegDeleteKeyExW
0x18001d2cf  test    eax, eax
0x18001d2d1  jz      short loc_18001D2D7
0x18001d2d3  mov     ecx, eax
0x18001d2d5  jmp     short loc_18001D2B9
0x18001d2d7  xor     ecx, ecx; dwErrCode
0x18001d2d9  call    cs:__imp_SetLastError
0x18001d2df  mov     eax, 1
0x18001d2e4  add     rsp, 28h
0x18001d2e8  retn
```
