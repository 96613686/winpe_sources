# CRegistry::CreateSubKey(wchar_t const *)

- ea: `0x18001d200`
- end: `0x18001d29c`
- name: `?CreateSubKey@CRegistry@@UEAAHPEB_W@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001c960`

## callees

- `0x18001d200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d226`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d28c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d226`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d28c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d263`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d276`

## pseudocode

```c
__int64 __fastcall CRegistry::CreateSubKey(CRegistry *this, const wchar_t *a2)
{
  HKEY v2; // rcx
  DWORD v3; // ecx
  LSTATUS v5; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 22);
  hKey = 0;
  dwDisposition = 0;
  if ( !v2 )
  {
    v3 = 6;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = RegCreateKeyExW(v2, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v5 )
  {
    v3 = v5;
    goto LABEL_3;
  }
  RegCloseKey(hKey);
  if ( dwDisposition == 2 )
  {
    v3 = 183;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x18001d200  sub     rsp, 58h
0x18001d204  mov     rcx, [rcx+0B0h]; hKey
0x18001d20b  mov     [rsp+58h+hKey], 0
0x18001d214  mov     [rsp+58h+dwDisposition], 0
0x18001d21c  test    rcx, rcx
0x18001d21f  jnz     short loc_18001D230
0x18001d221  mov     ecx, 6; dwErrCode
0x18001d226  call    cs:__imp_SetLastError
0x18001d22c  xor     eax, eax
0x18001d22e  jmp     short loc_18001D297
0x18001d230  lea     rax, [rsp+58h+dwDisposition]
0x18001d235  xor     r9d, r9d; lpClass
0x18001d238  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18001d23d  xor     r8d, r8d; Reserved
0x18001d240  lea     rax, [rsp+58h+hKey]
0x18001d245  mov     [rsp+58h+phkResult], rax; phkResult
0x18001d24a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d253  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18001d25b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18001d263  call    cs:__imp_RegCreateKeyExW
0x18001d269  test    eax, eax
0x18001d26b  jz      short loc_18001D271
0x18001d26d  mov     ecx, eax
0x18001d26f  jmp     short loc_18001D226
0x18001d271  mov     rcx, [rsp+58h+hKey]; hKey
0x18001d276  call    cs:__imp_RegCloseKey
0x18001d27c  cmp     [rsp+58h+dwDisposition], 2
0x18001d281  jnz     short loc_18001D28A
0x18001d283  mov     ecx, 0B7h
0x18001d288  jmp     short loc_18001D226
0x18001d28a  xor     ecx, ecx; dwErrCode
0x18001d28c  call    cs:__imp_SetLastError
0x18001d292  mov     eax, 1
0x18001d297  add     rsp, 58h
0x18001d29b  retn
```
