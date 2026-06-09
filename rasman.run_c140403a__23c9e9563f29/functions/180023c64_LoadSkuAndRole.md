# LoadSkuAndRole

- ea: `0x180023c64`
- end: `0x180023d38`
- name: `LoadSkuAndRole`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800202a0`
- `0x180023c30`

## callees

- `0x180023c64`
- `0x1800263ce`
- `0x180026400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180023cb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180023cb0`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180023ce0`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180023ce0`
- `DSROLE!DsRoleFreeMemory` at `0x180023d09`
- `DSROLE!DsRoleFreeMemory` at `0x180023d09`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180023cf2`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180023cf2`

## pseudocode

```c
DWORD LoadSkuAndRole()
{
  DWORD result; // eax
  DWORD pdwReturnedProductType; // [rsp+30h] [rbp-D0h] BYREF
  PBYTE Buffer; // [rsp+38h] [rbp-C8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v4; // [rsp+154h] [rbp+54h]
  unsigned __int16 v5; // [rsp+156h] [rbp+56h]
  unsigned __int16 v6; // [rsp+158h] [rbp+58h]

  Buffer = 0;
  pdwReturnedProductType = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    return GetLastError();
  dword_180030920 = v6;
  GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v4, v5, &pdwReturnedProductType);
  result = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  if ( !result )
  {
    dword_180030924 = *(_DWORD *)Buffer;
    DsRoleFreeMemory(Buffer);
    result = 0;
    dword_180030950 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180023c64  push    rbp
0x180023c66  lea     rbp, [rsp-70h]
0x180023c6b  sub     rsp, 170h
0x180023c72  mov     rax, cs:__security_cookie
0x180023c79  xor     rax, rsp
0x180023c7c  mov     [rbp+70h+var_10], rax
0x180023c80  xor     edx, edx; Val
0x180023c82  mov     [rsp+170h+Buffer], 0
0x180023c8b  mov     r8d, 118h; Size
0x180023c91  mov     [rsp+170h+var_140], 0
0x180023c99  lea     rcx, [rsp+170h+VersionInformation.dwMajorVersion]; void *
0x180023c9e  call    memset_0
0x180023ca3  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x180023ca8  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180023cb0  call    cs:__imp_GetVersionExW
0x180023cb6  test    eax, eax
0x180023cb8  jz      short loc_180023D1D
0x180023cba  movzx   eax, [rbp+70h+var_18]
0x180023cbe  movzx   r9d, [rbp+70h+var_1A]; dwSpMinorVersion
0x180023cc3  movzx   r8d, [rbp+70h+var_1C]; dwSpMajorVersion
0x180023cc8  mov     edx, [rsp+170h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180023ccc  mov     ecx, [rsp+170h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180023cd0  mov     cs:dword_180030920, eax
0x180023cd6  lea     rax, [rsp+170h+var_140]
0x180023cdb  mov     [rsp+170h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180023ce0  call    cs:__imp_GetProductInfo
0x180023ce6  lea     r8, [rsp+170h+Buffer]; Buffer
0x180023ceb  mov     edx, 1; InfoLevel
0x180023cf0  xor     ecx, ecx; lpServer
0x180023cf2  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180023cf8  test    eax, eax
0x180023cfa  jnz     short loc_180023D23
0x180023cfc  mov     rcx, [rsp+170h+Buffer]; Buffer
0x180023d01  mov     eax, [rcx]
0x180023d03  mov     cs:dword_180030924, eax
0x180023d09  call    cs:__imp_DsRoleFreeMemory
0x180023d0f  xor     eax, eax
0x180023d11  mov     cs:dword_180030950, 1
0x180023d1b  jmp     short loc_180023D23
0x180023d1d  call    cs:__imp_GetLastError
0x180023d23  mov     rcx, [rbp+70h+var_10]
0x180023d27  xor     rcx, rsp; StackCookie
0x180023d2a  call    __security_check_cookie
0x180023d2f  add     rsp, 170h
0x180023d36  pop     rbp
0x180023d37  retn
```
