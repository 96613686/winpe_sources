# CRegistry::CreateSubKey(wchar_t const *)

- ea: `0x1800360a0`
- end: `0x18003613c`
- name: `?CreateSubKey@CRegistry@@UEAAHPEB_W@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800360a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800360c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003612c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800360c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003612c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036116`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036103`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036103`

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
0x1800360a0  sub     rsp, 58h
0x1800360a4  mov     rcx, [rcx+0B0h]; hKey
0x1800360ab  mov     [rsp+58h+hKey], 0
0x1800360b4  mov     [rsp+58h+dwDisposition], 0
0x1800360bc  test    rcx, rcx
0x1800360bf  jnz     short loc_1800360D0
0x1800360c1  mov     ecx, 6; dwErrCode
0x1800360c6  call    cs:__imp_SetLastError
0x1800360cc  xor     eax, eax
0x1800360ce  jmp     short loc_180036137
0x1800360d0  lea     rax, [rsp+58h+dwDisposition]
0x1800360d5  xor     r9d, r9d; lpClass
0x1800360d8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1800360dd  xor     r8d, r8d; Reserved
0x1800360e0  lea     rax, [rsp+58h+hKey]
0x1800360e5  mov     [rsp+58h+phkResult], rax; phkResult
0x1800360ea  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800360f3  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800360fb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180036103  call    cs:__imp_RegCreateKeyExW
0x180036109  test    eax, eax
0x18003610b  jz      short loc_180036111
0x18003610d  mov     ecx, eax
0x18003610f  jmp     short loc_1800360C6
0x180036111  mov     rcx, [rsp+58h+hKey]; hKey
0x180036116  call    cs:__imp_RegCloseKey
0x18003611c  cmp     [rsp+58h+dwDisposition], 2
0x180036121  jnz     short loc_18003612A
0x180036123  mov     ecx, 0B7h
0x180036128  jmp     short loc_1800360C6
0x18003612a  xor     ecx, ecx; dwErrCode
0x18003612c  call    cs:__imp_SetLastError
0x180036132  mov     eax, 1
0x180036137  add     rsp, 58h
0x18003613b  retn
```
