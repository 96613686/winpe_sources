# lrGetEapKeyFromToken

- ea: `0x1800245e4`
- end: `0x1800246b2`
- name: `lrGetEapKeyFromToken`
- size: `206`
- prototype: `__int64 __fastcall(void *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023d40`

## callees

- `0x1800245e4`
- `0x1800246f4`
- `0x180024990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002469b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002469b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002463d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002463d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024681`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024681`

## pseudocode

```c
__int64 __fastcall lrGetEapKeyFromToken(void *a1, HKEY *a2)
{
  unsigned int SidFromToken; // ebx
  HKEY v5; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  lpSubKey = 0;
  hKey = 0;
  v5 = 0;
  dwDisposition = 0;
  SidFromToken = GetSidFromToken(a1, (HGLOBAL *)&lpSubKey);
  if ( !SidFromToken )
  {
    SidFromToken = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0xF003Fu, &hKey);
    if ( !SidFromToken )
      SidFromToken = RegCreateKeyExW(
                       hKey,
                       L"Software\\Microsoft\\RAS EAP\\UserEapInfo",
                       0,
                       0,
                       0,
                       0xF003Fu,
                       0,
                       &v5,
                       &dwDisposition);
  }
  Free0((void *)lpSubKey);
  if ( hKey )
    RegCloseKey(hKey);
  *a2 = v5;
  return SidFromToken;
}

```

## disassembly

```asm
0x1800245e4  push    rbp
0x1800245e6  push    rbx
0x1800245e7  push    rdi
0x1800245e8  mov     rbp, rsp
0x1800245eb  sub     rsp, 60h
0x1800245ef  mov     rdi, rdx
0x1800245f2  mov     [rbp+lpSubKey], 0
0x1800245fa  lea     rdx, [rbp+lpSubKey]
0x1800245fe  mov     [rbp+hKey], 0
0x180024606  mov     [rbp+var_10], 0
0x18002460e  mov     [rbp+dwDisposition], 0
0x180024615  call    GetSidFromToken
0x18002461a  mov     ebx, eax
0x18002461c  test    eax, eax
0x18002461e  jnz     short loc_180024689
0x180024620  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180024624  lea     rax, [rbp+hKey]
0x180024628  mov     r9d, 0F003Fh; samDesired
0x18002462e  mov     [rsp+60h+phkResult], rax; phkResult
0x180024633  xor     r8d, r8d; ulOptions
0x180024636  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002463d  call    cs:__imp_RegOpenKeyExW
0x180024643  mov     ebx, eax
0x180024645  test    eax, eax
0x180024647  jnz     short loc_180024689
0x180024649  mov     rcx, [rbp+hKey]; hKey
0x18002464d  lea     rax, [rbp+dwDisposition]
0x180024651  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180024656  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x18002465d  lea     rax, [rbp+var_10]
0x180024661  xor     r9d, r9d; lpClass
0x180024664  mov     [rsp+60h+var_28], rax; phkResult
0x180024669  xor     r8d, r8d; Reserved
0x18002466c  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180024675  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18002467d  mov     dword ptr [rsp+60h+phkResult], ebx; dwOptions
0x180024681  call    cs:__imp_RegCreateKeyExW
0x180024687  mov     ebx, eax
0x180024689  mov     rcx, [rbp+lpSubKey]
0x18002468d  call    Free0
0x180024692  mov     rcx, [rbp+hKey]; hKey
0x180024696  test    rcx, rcx
0x180024699  jz      short loc_1800246A1
0x18002469b  call    cs:__imp_RegCloseKey
0x1800246a1  mov     rax, [rbp+var_10]
0x1800246a5  mov     [rdi], rax
0x1800246a8  mov     eax, ebx
0x1800246aa  add     rsp, 60h
0x1800246ae  pop     rdi
0x1800246af  pop     rbx
0x1800246b0  pop     rbp
0x1800246b1  retn
```
