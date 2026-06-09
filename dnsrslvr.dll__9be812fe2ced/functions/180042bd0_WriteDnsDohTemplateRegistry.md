# WriteDnsDohTemplateRegistry

- ea: `0x180042bd0`
- end: `0x180042e4d`
- name: `WriteDnsDohTemplateRegistry`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18004296c`

## callees

- `0x18004285c`
- `0x180042bd0`
- `0x180046ec0`
- `0x180047818`
- `0x18007d7fc`
- `0x180085fb8`
- `0x180086384`
- `0x1800868b8`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042def`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042def`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042e02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042d36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042d65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042d36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042d65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042c8f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042ccc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042ccc`

## string_xrefs

- `0x180042c81`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers`
- `0x180042d23`: `Template`

## pseudocode

```c
__int64 __fastcall WriteDnsDohTemplateRegistry(__int64 a1, __int64 *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  const BYTE *v7; // rcx
  __int64 v8; // rax
  const BYTE *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rdx
  HKEY v13; // [rsp+50h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-71h] BYREF
  WCHAR SubKey[72]; // [rsp+60h] [rbp-69h] BYREF

  hKey = 0;
  v13 = 0;
  memset_0(SubKey, 0, 0x82u);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_S(1035, 40, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, *a2);
  v4 = DnsConvertServerAddrToString(a1, SubKey);
  v5 = v4;
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_23;
    v11 = 41;
    goto LABEL_22;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_S(1035, 42, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, SubKey);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\DohWellKnownServers",
         0,
         0x3001Fu,
         &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_23;
    v11 = 43;
LABEL_22:
    WPP_SF_d(1035, v11, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v4);
    goto LABEL_23;
  }
  v6 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &v13, 0);
  v5 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 44, (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, (unsigned int)SubKey, v6);
  }
  else
  {
    v7 = (const BYTE *)*a2;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v7[2 * v8] );
    v5 = RegSetValueExW(v13, L"Template", 0, 1u, v7, 2 * v8 + 2);
    if ( v5 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_DS(1035, 45, (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5, *a2);
    }
    else
    {
      v9 = (const BYTE *)(a2 + 1);
      v5 = RegSetValueExW(v13, L"Flags", 0, 0xBu, v9, 8u);
      if ( v5 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_Di(v10, 46, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5, *(_QWORD *)v9);
    }
  }
LABEL_23:
  if ( v13 )
  {
    RegCloseKey(v13);
    v13 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 47, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180042bd0  mov     [rsp-8+arg_10], rbx
0x180042bd5  push    rbp
0x180042bd6  push    rsi
0x180042bd7  push    rdi
0x180042bd8  push    r12
0x180042bda  push    r15
0x180042bdc  lea     rbp, [rsp-37h]
0x180042be1  sub     rsp, 100h
0x180042be8  mov     rax, cs:__security_cookie
0x180042bef  xor     rax, rsp
0x180042bf2  mov     [rbp+57h+var_30], rax
0x180042bf6  xor     esi, esi
0x180042bf8  mov     rdi, rdx
0x180042bfb  mov     rbx, rcx
0x180042bfe  mov     [rbp+57h+hKey], rsi
0x180042c02  xor     edx, edx; Val
0x180042c04  mov     [rbp+57h+var_D0], rsi
0x180042c08  lea     rcx, [rbp+57h+SubKey]; void *
0x180042c0c  mov     r8d, 82h; Size
0x180042c12  call    memset_0
0x180042c17  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042c1e  lea     r15, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180042c25  mov     r12d, 40Bh
0x180042c2b  jz      short loc_180042C3E
0x180042c2d  mov     r9, [rdi]
0x180042c30  lea     edx, [rsi+28h]
0x180042c33  mov     ecx, r12d
0x180042c36  mov     r8, r15
0x180042c39  call    WPP_SF_S
0x180042c3e  lea     rdx, [rbp+57h+SubKey]
0x180042c42  mov     rcx, rbx
0x180042c45  call    DnsConvertServerAddrToString
0x180042c4a  mov     ebx, eax
0x180042c4c  test    eax, eax
0x180042c4e  jnz     loc_180042DCA
0x180042c54  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042c5b  jz      short loc_180042C6F
0x180042c5d  lea     edx, [rax+2Ah]
0x180042c60  mov     ecx, r12d
0x180042c63  lea     r9, [rbp+57h+SubKey]
0x180042c67  mov     r8, r15
0x180042c6a  call    WPP_SF_S
0x180042c6f  lea     rax, [rbp+57h+hKey]
0x180042c73  mov     r9d, 3001Fh; samDesired
0x180042c79  xor     r8d, r8d; ulOptions
0x180042c7c  mov     [rsp+120h+phkResult], rax; phkResult
0x180042c81  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180042c88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042c8f  call    cs:__imp_RegOpenKeyExW
0x180042c95  mov     ebx, eax
0x180042c97  test    eax, eax
0x180042c99  jnz     loc_180042DBA
0x180042c9f  mov     rcx, [rbp+57h+hKey]; hKey
0x180042ca3  lea     rax, [rbp+57h+var_D0]
0x180042ca7  mov     [rsp+120h+lpdwDisposition], rsi; lpdwDisposition
0x180042cac  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180042cb0  mov     [rsp+120h+var_E8], rax; phkResult
0x180042cb5  xor     r9d, r9d; lpClass
0x180042cb8  mov     [rsp+120h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180042cbd  xor     r8d, r8d; Reserved
0x180042cc0  mov     [rsp+120h+samDesired], 20006h; samDesired
0x180042cc8  mov     dword ptr [rsp+120h+phkResult], esi; dwOptions
0x180042ccc  call    cs:__imp_RegCreateKeyExW
0x180042cd2  mov     ebx, eax
0x180042cd4  test    eax, eax
0x180042cd6  jz      short loc_180042D02
0x180042cd8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042cdf  jz      loc_180042DE6
0x180042ce5  mov     edx, 2Ch ; ','
0x180042cea  mov     dword ptr [rsp+120h+phkResult], eax
0x180042cee  mov     ecx, r12d
0x180042cf1  lea     r9, [rbp+57h+SubKey]
0x180042cf5  mov     r8, r15
0x180042cf8  call    WPP_SF_SD
0x180042cfd  jmp     loc_180042DE6
0x180042d02  mov     rcx, [rdi]
0x180042d05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042d09  inc     rax
0x180042d0c  cmp     [rcx+rax*2], si
0x180042d10  jnz     short loc_180042D09
0x180042d12  lea     eax, ds:2[rax*2]
0x180042d19  mov     r9d, 1; dwType
0x180042d1f  mov     [rsp+120h+samDesired], eax; cbData
0x180042d23  lea     rdx, aTemplate; "Template"
0x180042d2a  mov     [rsp+120h+phkResult], rcx; lpData
0x180042d2f  xor     r8d, r8d; Reserved
0x180042d32  mov     rcx, [rbp+57h+var_D0]; hKey
0x180042d36  call    cs:__imp_RegSetValueExW
0x180042d3c  mov     ebx, eax
0x180042d3e  test    eax, eax
0x180042d40  jnz     short loc_180042D94
0x180042d42  mov     rcx, [rbp+57h+var_D0]; hKey
0x180042d46  lea     r9d, [rax+0Bh]; dwType
0x180042d4a  add     rdi, 8
0x180042d4e  mov     [rsp+120h+samDesired], 8; cbData
0x180042d56  xor     r8d, r8d; Reserved
0x180042d59  mov     [rsp+120h+phkResult], rdi; lpData
0x180042d5e  lea     rdx, aFlags; "Flags"
0x180042d65  call    cs:__imp_RegSetValueExW
0x180042d6b  mov     ebx, eax
0x180042d6d  test    eax, eax
0x180042d6f  jz      short loc_180042DE6
0x180042d71  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042d78  jz      short loc_180042DE6
0x180042d7a  mov     rax, [rdi]
0x180042d7d  mov     edx, 2Eh ; '.'
0x180042d82  mov     r9d, ebx
0x180042d85  mov     [rsp+120h+phkResult], rax
0x180042d8a  mov     r8, r15
0x180042d8d  call    WPP_SF_Di
0x180042d92  jmp     short loc_180042DE6
0x180042d94  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042d9b  jz      short loc_180042DE6
0x180042d9d  mov     rax, [rdi]
0x180042da0  mov     edx, 2Dh ; '-'
0x180042da5  mov     ecx, r12d
0x180042da8  mov     [rsp+120h+phkResult], rax
0x180042dad  mov     r9d, ebx
0x180042db0  mov     r8, r15
0x180042db3  call    WPP_SF_DS
0x180042db8  jmp     short loc_180042DE6
0x180042dba  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042dc1  jz      short loc_180042DE6
0x180042dc3  mov     edx, 2Bh ; '+'
0x180042dc8  jmp     short loc_180042DD8
0x180042dca  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042dd1  jz      short loc_180042DE6
0x180042dd3  mov     edx, 29h ; ')'
0x180042dd8  mov     r9d, eax
0x180042ddb  mov     r8, r15
0x180042dde  mov     ecx, r12d
0x180042de1  call    WPP_SF_d
0x180042de6  mov     rcx, [rbp+57h+var_D0]; hKey
0x180042dea  test    rcx, rcx
0x180042ded  jz      short loc_180042DF9
0x180042def  call    cs:__imp_RegCloseKey
0x180042df5  mov     [rbp+57h+var_D0], rsi
0x180042df9  mov     rcx, [rbp+57h+hKey]; hKey
0x180042dfd  test    rcx, rcx
0x180042e00  jz      short loc_180042E0C
0x180042e02  call    cs:__imp_RegCloseKey
0x180042e08  mov     [rbp+57h+hKey], rsi
0x180042e0c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180042e13  jz      short loc_180042E28
0x180042e15  mov     edx, 2Fh ; '/'
0x180042e1a  mov     ecx, r12d
0x180042e1d  mov     r9d, ebx
0x180042e20  mov     r8, r15
0x180042e23  call    WPP_SF_d
0x180042e28  mov     eax, ebx
0x180042e2a  mov     rcx, [rbp+57h+var_30]
0x180042e2e  xor     rcx, rsp; StackCookie
0x180042e31  call    __security_check_cookie
0x180042e36  mov     rbx, [rsp+120h+arg_10]
0x180042e3e  add     rsp, 100h
0x180042e45  pop     r15
0x180042e47  pop     r12
0x180042e49  pop     rdi
0x180042e4a  pop     rsi
0x180042e4b  pop     rbp
0x180042e4c  retn
```
