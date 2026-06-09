# LoadSkuAndRole

- ea: `0x180024954`
- end: `0x180024a47`
- name: `LoadSkuAndRole`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180020d30`
- `0x18002491c`

## callees

- `0x180024954`
- `0x18002739e`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a25`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800249a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800249a0`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800249d6`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800249d6`
- `DSROLE!DsRoleFreeMemory` at `0x180024a0b`
- `DSROLE!DsRoleFreeMemory` at `0x180024a0b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800249ee`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800249ee`

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
  dword_180031920 = v6;
  GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v4, v5, &pdwReturnedProductType);
  result = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  if ( !result )
  {
    dword_180031924 = *(_DWORD *)Buffer;
    DsRoleFreeMemory(Buffer);
    result = 0;
    dword_180031950 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180024954  push    rbp
0x180024956  lea     rbp, [rsp-70h]
0x18002495b  sub     rsp, 170h
0x180024962  mov     rax, cs:__security_cookie
0x180024969  xor     rax, rsp
0x18002496c  mov     [rbp+70h+var_10], rax
0x180024970  xor     edx, edx; Val
0x180024972  mov     [rsp+170h+Buffer], 0
0x18002497b  mov     r8d, 118h; Size
0x180024981  mov     [rsp+170h+var_140], 0
0x180024989  lea     rcx, [rsp+170h+VersionInformation.dwMajorVersion]; void *
0x18002498e  call    memset_0
0x180024993  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x180024998  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800249a0  call    cs:__imp_GetVersionExW
0x1800249a7  nop     dword ptr [rax+rax+00h]
0x1800249ac  test    eax, eax
0x1800249ae  jz      short loc_180024A25
0x1800249b0  movzx   eax, [rbp+70h+var_18]
0x1800249b4  movzx   r9d, [rbp+70h+var_1A]; dwSpMinorVersion
0x1800249b9  movzx   r8d, [rbp+70h+var_1C]; dwSpMajorVersion
0x1800249be  mov     edx, [rsp+170h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1800249c2  mov     ecx, [rsp+170h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1800249c6  mov     cs:dword_180031920, eax
0x1800249cc  lea     rax, [rsp+170h+var_140]
0x1800249d1  mov     [rsp+170h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1800249d6  call    cs:__imp_GetProductInfo
0x1800249dd  nop     dword ptr [rax+rax+00h]
0x1800249e2  lea     r8, [rsp+170h+Buffer]; Buffer
0x1800249e7  mov     edx, 1; InfoLevel
0x1800249ec  xor     ecx, ecx; lpServer
0x1800249ee  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800249f5  nop     dword ptr [rax+rax+00h]
0x1800249fa  test    eax, eax
0x1800249fc  jnz     short loc_180024A31
0x1800249fe  mov     rcx, [rsp+170h+Buffer]; Buffer
0x180024a03  mov     eax, [rcx]
0x180024a05  mov     cs:dword_180031924, eax
0x180024a0b  call    cs:__imp_DsRoleFreeMemory
0x180024a12  nop     dword ptr [rax+rax+00h]
0x180024a17  xor     eax, eax
0x180024a19  mov     cs:dword_180031950, 1
0x180024a23  jmp     short loc_180024A31
0x180024a25  call    cs:__imp_GetLastError
0x180024a2c  nop     dword ptr [rax+rax+00h]
0x180024a31  mov     rcx, [rbp+70h+var_10]
0x180024a35  xor     rcx, rsp; StackCookie
0x180024a38  call    __security_check_cookie
0x180024a3d  add     rsp, 170h
0x180024a44  pop     rbp
0x180024a45  retn
```
