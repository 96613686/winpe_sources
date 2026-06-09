# DotDeleteServerRegistry

- ea: `0x180052b30`
- end: `0x180052d13`
- name: `DotDeleteServerRegistry`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800537e4`

## callees

- `0x18004285c`
- `0x180046ec0`
- `0x180047818`
- `0x180052b30`
- `0x1800868b8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052cf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052cf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052be9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052c20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052c57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052be9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052c20`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052c57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052ba8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052bd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052ba8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052bd0`

## string_xrefs

- `0x180052b9a`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers`

## pseudocode

```c
unsigned int __fastcall DotDeleteServerRegistry(__int64 a1)
{
  unsigned int result; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  WCHAR SubKey[72]; // [rsp+40h] [rbp-49h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(SubKey, 0, 0x82u);
  result = DnsConvertServerAddrToString(a1, SubKey);
  if ( result )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_20;
    v5 = 60;
    goto LABEL_19;
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
      goto LABEL_20;
    v5 = 61;
    goto LABEL_19;
  }
  result = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
  if ( result )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      result = WPP_SF_DS(
                 1035,
                 62,
                 (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids,
                 result,
                 (__int64)SubKey);
  }
  else
  {
    v3 = RegDeleteValueW(phkResult, L"DotFlags");
    if ( v3 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 63, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v3);
    v4 = RegDeleteValueW(phkResult, L"DotPort");
    if ( v4 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 64, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v4);
    result = RegDeleteValueW(phkResult, L"DotHost");
    if ( result && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v5 = 65;
LABEL_19:
      result = WPP_SF_d(1035, v5, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, result);
    }
  }
LABEL_20:
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
0x180052b30  mov     [rsp-8+arg_8], rbx
0x180052b35  push    rbp
0x180052b36  lea     rbp, [rsp-57h]
0x180052b3b  sub     rsp, 0E0h
0x180052b42  mov     rax, cs:__security_cookie
0x180052b49  xor     rax, rsp
0x180052b4c  mov     [rbp+57h+var_10], rax
0x180052b50  mov     rbx, rcx
0x180052b53  mov     [rbp+57h+hKey], 0
0x180052b5b  lea     rcx, [rbp+57h+SubKey]; void *
0x180052b5f  mov     [rbp+57h+var_B0], 0
0x180052b67  xor     edx, edx; Val
0x180052b69  mov     r8d, 82h; Size
0x180052b6f  call    memset_0
0x180052b74  lea     rdx, [rbp+57h+SubKey]
0x180052b78  mov     rcx, rbx
0x180052b7b  call    DnsConvertServerAddrToString
0x180052b80  test    eax, eax
0x180052b82  jnz     loc_180052CAE
0x180052b88  lea     rax, [rbp+57h+hKey]
0x180052b8c  mov     r9d, 3001Fh; samDesired
0x180052b92  xor     r8d, r8d; ulOptions
0x180052b95  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180052b9a  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180052ba1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052ba8  call    cs:__imp_RegOpenKeyExW
0x180052bae  test    eax, eax
0x180052bb0  jnz     loc_180052C9E
0x180052bb6  mov     rcx, [rbp+57h+hKey]; hKey
0x180052bba  lea     rax, [rbp+57h+var_B0]
0x180052bbe  mov     r9d, 20006h; samDesired
0x180052bc4  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180052bc9  xor     r8d, r8d; ulOptions
0x180052bcc  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180052bd0  call    cs:__imp_RegOpenKeyExW
0x180052bd6  test    eax, eax
0x180052bd8  jnz     loc_180052C71
0x180052bde  mov     rcx, [rbp+57h+var_B0]; hKey
0x180052be2  lea     rdx, aDotflags; "DotFlags"
0x180052be9  call    cs:__imp_RegDeleteValueW
0x180052bef  test    eax, eax
0x180052bf1  jz      short loc_180052C15
0x180052bf3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052bfa  jz      short loc_180052C15
0x180052bfc  mov     edx, 3Fh ; '?'
0x180052c01  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052c08  mov     ecx, 40Bh
0x180052c0d  mov     r9d, eax
0x180052c10  call    WPP_SF_d
0x180052c15  mov     rcx, [rbp+57h+var_B0]; hKey
0x180052c19  lea     rdx, aDotport; "DotPort"
0x180052c20  call    cs:__imp_RegDeleteValueW
0x180052c26  test    eax, eax
0x180052c28  jz      short loc_180052C4C
0x180052c2a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052c31  jz      short loc_180052C4C
0x180052c33  mov     edx, 40h ; '@'
0x180052c38  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052c3f  mov     ecx, 40Bh
0x180052c44  mov     r9d, eax
0x180052c47  call    WPP_SF_d
0x180052c4c  mov     rcx, [rbp+57h+var_B0]; hKey
0x180052c50  lea     rdx, aDothost; "DotHost"
0x180052c57  call    cs:__imp_RegDeleteValueW
0x180052c5d  test    eax, eax
0x180052c5f  jz      short loc_180052CD0
0x180052c61  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052c68  jz      short loc_180052CD0
0x180052c6a  mov     edx, 41h ; 'A'
0x180052c6f  jmp     short loc_180052CBC
0x180052c71  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052c78  jz      short loc_180052CD0
0x180052c7a  lea     r8, [rbp+57h+SubKey]
0x180052c7e  mov     edx, 3Eh ; '>'
0x180052c83  mov     [rsp+0E0h+phkResult], r8
0x180052c88  mov     ecx, 40Bh
0x180052c8d  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052c94  mov     r9d, eax
0x180052c97  call    WPP_SF_DS
0x180052c9c  jmp     short loc_180052CD0
0x180052c9e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052ca5  jz      short loc_180052CD0
0x180052ca7  mov     edx, 3Dh ; '='
0x180052cac  jmp     short loc_180052CBC
0x180052cae  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052cb5  jz      short loc_180052CD0
0x180052cb7  mov     edx, 3Ch ; '<'
0x180052cbc  mov     r9d, eax
0x180052cbf  lea     r8, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052cc6  mov     ecx, 40Bh
0x180052ccb  call    WPP_SF_d
0x180052cd0  mov     rcx, [rbp+57h+hKey]; hKey
0x180052cd4  test    rcx, rcx
0x180052cd7  jz      short loc_180052CE7
0x180052cd9  call    cs:__imp_RegCloseKey
0x180052cdf  mov     [rbp+57h+hKey], 0
0x180052ce7  mov     rcx, [rbp+57h+var_B0]; hKey
0x180052ceb  test    rcx, rcx
0x180052cee  jz      short loc_180052CF6
0x180052cf0  call    cs:__imp_RegCloseKey
0x180052cf6  mov     rcx, [rbp+57h+var_10]
0x180052cfa  xor     rcx, rsp; StackCookie
0x180052cfd  call    __security_check_cookie
0x180052d02  mov     rbx, [rsp+0E0h+arg_8]
0x180052d0a  add     rsp, 0E0h
0x180052d11  pop     rbp
0x180052d12  retn
```
