# MachineCertExpirationEnabled(void)

- ea: `0x180007178`
- end: `0x180007212`
- name: `?MachineCertExpirationEnabled@@YAHXZ`
- size: `154`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006974`

## callees

- `0x180007178`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800071e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007202`

## pseudocode

```c
_BOOL8 MachineCertExpirationEnabled(void)
{
  BOOL v0; // ebx
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"EnableMachineCertExpirationNotification", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4 )
    {
      v0 = Data != 0;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180007178  push    rbp
0x18000717a  push    rbx
0x18000717b  push    rsi
0x18000717c  mov     rbp, rsp
0x18000717f  sub     rsp, 30h
0x180007183  xor     ebx, ebx
0x180007185  mov     [rbp+hKey], 0
0x18000718d  lea     rax, [rbp+hKey]
0x180007191  mov     [rbp+Data], ebx
0x180007194  xor     r8d, r8d; ulOptions
0x180007197  mov     [rbp+Type], ebx
0x18000719a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x1800071a1  mov     [rbp+cbData], 4
0x1800071a8  lea     esi, [rbx+1]
0x1800071ab  mov     [rsp+30h+phkResult], rax; phkResult
0x1800071b0  mov     r9d, esi; samDesired
0x1800071b3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800071ba  call    cs:__imp_RegOpenKeyExW
0x1800071c0  test    eax, eax
0x1800071c2  jnz     short loc_180007208
0x1800071c4  mov     rcx, [rbp+hKey]; hKey
0x1800071c8  lea     rax, [rbp+cbData]
0x1800071cc  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800071d1  lea     r9, [rbp+Type]; lpType
0x1800071d5  lea     rax, [rbp+Data]
0x1800071d9  xor     r8d, r8d; lpReserved
0x1800071dc  lea     rdx, aEnablemachinec; "EnableMachineCertExpirationNotification"
0x1800071e3  mov     [rsp+30h+phkResult], rax; lpData
0x1800071e8  call    cs:__imp_RegQueryValueExW
0x1800071ee  test    eax, eax
0x1800071f0  jnz     short loc_1800071FE
0x1800071f2  cmp     [rbp+Type], 4
0x1800071f6  jnz     short loc_1800071FE
0x1800071f8  cmp     [rbp+Data], ebx
0x1800071fb  cmovnz  ebx, esi
0x1800071fe  mov     rcx, [rbp+hKey]; hKey
0x180007202  call    cs:__imp_RegCloseKey
0x180007208  mov     eax, ebx
0x18000720a  add     rsp, 30h
0x18000720e  pop     rsi
0x18000720f  pop     rbx
0x180007210  pop     rbp
0x180007211  retn
```
