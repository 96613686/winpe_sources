# CRegistry::DeleteSubKey(wchar_t const *)

- ea: `0x180036144`
- end: `0x180036189`
- name: `?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z`
- size: `69`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180036190`

## callees

- `0x180036144`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036179`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036179`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036169`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180036169`

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
0x180036144  sub     rsp, 28h
0x180036148  mov     rcx, [rcx+0B0h]; hKey
0x18003614f  test    rcx, rcx
0x180036152  jnz     short loc_180036163
0x180036154  mov     ecx, 6; dwErrCode
0x180036159  call    cs:__imp_SetLastError
0x18003615f  xor     eax, eax
0x180036161  jmp     short loc_180036184
0x180036163  xor     r9d, r9d; Reserved
0x180036166  xor     r8d, r8d; samDesired
0x180036169  call    cs:__imp_RegDeleteKeyExW
0x18003616f  test    eax, eax
0x180036171  jz      short loc_180036177
0x180036173  mov     ecx, eax
0x180036175  jmp     short loc_180036159
0x180036177  xor     ecx, ecx; dwErrCode
0x180036179  call    cs:__imp_SetLastError
0x18003617f  mov     eax, 1
0x180036184  add     rsp, 28h
0x180036188  retn
```
