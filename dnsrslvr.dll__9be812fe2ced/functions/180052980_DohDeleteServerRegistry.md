# DohDeleteServerRegistry

- ea: `0x180052980`
- end: `0x180052b28`
- name: `DohDeleteServerRegistry`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18004296c`
- `0x1800537e4`

## callees

- `0x18004285c`
- `0x180046ec0`
- `0x180047818`
- `0x180052980`
- `0x1800868b8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052b05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052a35`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052a6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052a35`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052a6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800529f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800529f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052a20`

## string_xrefs

- `0x1800529ea`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers`
- `0x180052a65`: `Template`

## pseudocode

```c
unsigned int __fastcall DohDeleteServerRegistry(__int64 a1)
{
  unsigned int result; // eax
  unsigned int v3; // eax
  __int64 v4; // rdx
  HKEY hKey; // [rsp+30h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-51h] BYREF
  WCHAR SubKey[72]; // [rsp+40h] [rbp-49h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(SubKey, 0, 0x82u);
  result = DnsConvertServerAddrToString(a1, SubKey);
  if ( result )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_17;
    v4 = 66;
    goto LABEL_16;
  }
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\DohWellKnownServers",
             0,
             0x3001Fu,
             &hKey);
  if ( result )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_17;
    v4 = 67;
    goto LABEL_16;
  }
  result = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
  if ( result )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      result = WPP_SF_DS(
                 1035,
                 68,
                 (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids,
                 result,
                 (__int64)SubKey);
  }
  else
  {
    v3 = RegDeleteValueW(phkResult, L"Flags");
    if ( v3 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 69, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v3);
    result = RegDeleteValueW(phkResult, L"Template");
    if ( result && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v4 = 70;
LABEL_16:
      result = WPP_SF_d(1035, v4, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, result);
    }
  }
LABEL_17:
  if ( hKey )
  {
    result = RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    return RegCloseKey(phkResult);
  return result;
}

```

## disassembly

```asm
0x180052980  mov     [rsp-8+arg_8], rbx
0x180052985  push    rbp
0x180052986  lea     rbp, [rsp-57h]
0x18005298b  sub     rsp, 0E0h
0x180052992  mov     rax, cs:__security_cookie
0x180052999  xor     rax, rsp
0x18005299c  mov     [rbp+57h+var_10], rax
0x1800529a0  mov     rbx, rcx
0x1800529a3  mov     [rbp+57h+hKey], 0
0x1800529ab  lea     rcx, [rbp+57h+SubKey]; void *
0x1800529af  mov     [rbp+57h+var_A8], 0
0x1800529b7  xor     edx, edx; Val
0x1800529b9  mov     r8d, 82h; Size
0x1800529bf  call    memset_0
0x1800529c4  lea     rdx, [rbp+57h+SubKey]
0x1800529c8  mov     rcx, rbx
0x1800529cb  call    DnsConvertServerAddrToString
0x1800529d0  test    eax, eax
0x1800529d2  jnz     loc_180052AC3
0x1800529d8  lea     rax, [rbp+57h+hKey]
0x1800529dc  mov     r9d, 3001Fh; samDesired
0x1800529e2  xor     r8d, r8d; ulOptions
0x1800529e5  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800529ea  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800529f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800529f8  call    cs:__imp_RegOpenKeyExW
0x1800529fe  test    eax, eax
0x180052a00  jnz     loc_180052AB3
0x180052a06  mov     rcx, [rbp+57h+hKey]; hKey
0x180052a0a  lea     rax, [rbp+57h+var_A8]
0x180052a0e  mov     r9d, 20006h; samDesired
0x180052a14  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180052a19  xor     r8d, r8d; ulOptions
0x180052a1c  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180052a20  call    cs:__imp_RegOpenKeyExW
0x180052a26  test    eax, eax
0x180052a28  jnz     short loc_180052A86
0x180052a2a  mov     rcx, [rbp+57h+var_A8]; hKey
0x180052a2e  lea     rdx, aFlags; "Flags"
0x180052a35  call    cs:__imp_RegDeleteValueW
0x180052a3b  test    eax, eax
0x180052a3d  jz      short loc_180052A61
0x180052a3f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052a46  jz      short loc_180052A61
0x180052a48  mov     edx, 45h ; 'E'
0x180052a4d  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052a54  mov     ecx, 40Bh
0x180052a59  mov     r9d, eax
0x180052a5c  call    WPP_SF_d
0x180052a61  mov     rcx, [rbp+57h+var_A8]; hKey
0x180052a65  lea     rdx, aTemplate; "Template"
0x180052a6c  call    cs:__imp_RegDeleteValueW
0x180052a72  test    eax, eax
0x180052a74  jz      short loc_180052AE5
0x180052a76  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052a7d  jz      short loc_180052AE5
0x180052a7f  mov     edx, 46h ; 'F'
0x180052a84  jmp     short loc_180052AD1
0x180052a86  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052a8d  jz      short loc_180052AE5
0x180052a8f  lea     r8, [rbp+57h+SubKey]
0x180052a93  mov     edx, 44h ; 'D'
0x180052a98  mov     [rsp+0E0h+phkResult], r8
0x180052a9d  mov     ecx, 40Bh
0x180052aa2  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052aa9  mov     r9d, eax
0x180052aac  call    WPP_SF_DS
0x180052ab1  jmp     short loc_180052AE5
0x180052ab3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052aba  jz      short loc_180052AE5
0x180052abc  mov     edx, 43h ; 'C'
0x180052ac1  jmp     short loc_180052AD1
0x180052ac3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052aca  jz      short loc_180052AE5
0x180052acc  mov     edx, 42h ; 'B'
0x180052ad1  mov     r9d, eax
0x180052ad4  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052adb  mov     ecx, 40Bh
0x180052ae0  call    WPP_SF_d
0x180052ae5  mov     rcx, [rbp+57h+hKey]; hKey
0x180052ae9  test    rcx, rcx
0x180052aec  jz      short loc_180052AFC
0x180052aee  call    cs:__imp_RegCloseKey
0x180052af4  mov     [rbp+57h+hKey], 0
0x180052afc  mov     rcx, [rbp+57h+var_A8]; hKey
0x180052b00  test    rcx, rcx
0x180052b03  jz      short loc_180052B0B
0x180052b05  call    cs:__imp_RegCloseKey
0x180052b0b  mov     rcx, [rbp+57h+var_10]
0x180052b0f  xor     rcx, rsp; StackCookie
0x180052b12  call    __security_check_cookie
0x180052b17  mov     rbx, [rsp+0E0h+arg_8]
0x180052b1f  add     rsp, 0E0h
0x180052b26  pop     rbp
0x180052b27  retn
```
