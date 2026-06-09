# GetDnsThreadpoolThreadCount(void)

- ea: `0x180034cc8`
- end: `0x180034f08`
- name: `?GetDnsThreadpoolThreadCount@@YAKXZ`
- size: `576`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180034b54`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180034cc8`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034eb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034eb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034dc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034dc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e4b`

## string_xrefs

- `0x180034d0e`: `System\CurrentControlSet\Services\SharedAccess\Parameters`
- `0x180034d5f`: `DnsThreadpoolThreadCount`

## pseudocode

```c
__int64 GetDnsThreadpoolThreadCount(void)
{
  unsigned int v0; // ebx
  PVOID *v1; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
  v0 = 128;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  wcscpy(ValueName, L"DnsThreadpoolThreadCount");
  hKey = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData)
    && (unsigned int)(*(_DWORD *)Data - 1) <= 0x3FF )
  {
    v0 = *(_DWORD *)Data;
  }
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v0);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x10) != 0 && *((_BYTE *)v1 + 25) >= 6u )
    WPP_SF_(v1[2], 39, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  return v0;
}

```

## disassembly

```asm
0x180034cc8  mov     [rsp-8+arg_0], rbx
0x180034ccd  mov     [rsp-8+arg_8], rsi
0x180034cd2  push    rbp
0x180034cd3  lea     rbp, [rsp-10h]
0x180034cd8  sub     rsp, 110h
0x180034cdf  mov     rax, cs:__security_cookie
0x180034ce6  xor     rax, rsp
0x180034ce9  mov     [rbp+10h+var_10], rax
0x180034ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180034cf4  lea     rsi, WPP_GLOBAL_Control
0x180034cfb  cmp     rcx, rsi
0x180034cfe  jnz     loc_180034E60
0x180034d04  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180034d0a  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x180034d0e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180034d15  mov     ebx, 80h
0x180034d1a  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180034d21  xor     r8d, r8d; ulOptions
0x180034d24  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x180034d28  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034d2f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180034d36  movaps  [rbp+10h+var_70], xmm0
0x180034d3a  lea     r9d, [rbx-7Fh]; samDesired
0x180034d3e  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180034d45  movaps  [rbp+10h+var_50], xmm0
0x180034d49  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180034d50  movaps  [rbp+10h+var_80], xmm1
0x180034d54  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180034d5b  movaps  [rbp+10h+var_30], xmm0
0x180034d5f  movups  xmm0, xmmword ptr cs:aDnsthreadpoolt; "DnsThreadpoolThreadCount"
0x180034d66  mov     [rbp+10h+var_20], eax
0x180034d69  movzx   eax, word ptr cs:aDnsthreadpoolt+30h; ""
0x180034d70  movaps  [rbp+10h+var_60], xmm1
0x180034d74  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180034d7b  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x180034d80  mov     [rsp+110h+var_A0], ax
0x180034d85  lea     rax, [rsp+110h+hKey]
0x180034d8a  movups  xmm0, xmmword ptr cs:aDnsthreadpoolt+20h; "eadCount"
0x180034d91  mov     [rsp+110h+hKey], 0
0x180034d9a  movaps  [rbp+10h+var_40], xmm1
0x180034d9e  movups  xmm1, xmmword ptr cs:aDnsthreadpoolt+10h; "dpoolThreadCount"
0x180034da5  mov     [rsp+110h+cbData], 4
0x180034dad  movups  [rsp+110h+var_B0], xmm0
0x180034db2  mov     dword ptr [rsp+110h+Data], 0
0x180034dba  movups  [rsp+110h+var_C0], xmm1
0x180034dbf  mov     [rsp+110h+phkResult], rax; phkResult
0x180034dc4  call    cs:__imp_RegOpenKeyExW
0x180034dcb  nop     dword ptr [rax+rax+00h]
0x180034dd0  test    eax, eax
0x180034dd2  jz      loc_180034E8E
0x180034dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ddf  cmp     rcx, rsi
0x180034de2  jz      short loc_180034DEA
0x180034de4  test    byte ptr [rcx+1Ch], 10h
0x180034de8  jnz     short loc_180034E21
0x180034dea  mov     rax, [rsp+110h+hKey]
0x180034def  test    rax, rax
0x180034df2  jnz     short loc_180034E48
0x180034df4  cmp     rcx, rsi
0x180034df7  jnz     loc_180034EDA
0x180034dfd  mov     eax, ebx
0x180034dff  mov     rcx, [rbp+10h+var_10]
0x180034e03  xor     rcx, rsp; StackCookie
0x180034e06  call    __security_check_cookie
0x180034e0b  lea     r11, [rsp+110h+var_s0]
0x180034e13  mov     rbx, [r11+10h]
0x180034e17  mov     rsi, [r11+18h]
0x180034e1b  mov     rsp, r11
0x180034e1e  pop     rbp
0x180034e1f  retn
0x180034e21  cmp     byte ptr [rcx+19h], 4
0x180034e25  jb      short loc_180034DEA
0x180034e27  mov     rcx, [rcx+10h]
0x180034e2b  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180034e32  mov     edx, 26h ; '&'
0x180034e37  mov     r9d, ebx
0x180034e3a  call    WPP_SF_d
0x180034e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e46  jmp     short loc_180034DEA
0x180034e48  mov     rcx, rax; hKey
0x180034e4b  call    cs:__imp_RegCloseKey
0x180034e52  nop     dword ptr [rax+rax+00h]
0x180034e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e5e  jmp     short loc_180034DF4
0x180034e60  test    byte ptr [rcx+1Ch], 10h
0x180034e64  jz      loc_180034D04
0x180034e6a  cmp     byte ptr [rcx+19h], 6
0x180034e6e  jb      loc_180034D04
0x180034e74  mov     rcx, [rcx+10h]
0x180034e78  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180034e7f  mov     edx, 25h ; '%'
0x180034e84  call    WPP_SF_
0x180034e89  jmp     loc_180034D04
0x180034e8e  mov     rcx, [rsp+110h+hKey]; hKey
0x180034e93  lea     rax, [rsp+110h+cbData]
0x180034e98  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180034e9d  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x180034ea2  lea     rax, [rsp+110h+Data]
0x180034ea7  xor     r9d, r9d; lpType
0x180034eaa  xor     r8d, r8d; lpReserved
0x180034ead  mov     [rsp+110h+phkResult], rax; lpData
0x180034eb2  call    cs:__imp_RegQueryValueExW
0x180034eb9  nop     dword ptr [rax+rax+00h]
0x180034ebe  test    eax, eax
0x180034ec0  jnz     loc_180034DD8
0x180034ec6  mov     ecx, dword ptr [rsp+110h+Data]
0x180034eca  lea     eax, [rcx-1]
0x180034ecd  cmp     eax, 3FFh
0x180034ed2  cmovbe  ebx, ecx
0x180034ed5  jmp     loc_180034DD8
0x180034eda  test    byte ptr [rcx+1Ch], 10h
0x180034ede  jz      loc_180034DFD
0x180034ee4  cmp     byte ptr [rcx+19h], 6
0x180034ee8  jb      loc_180034DFD
0x180034eee  mov     rcx, [rcx+10h]
0x180034ef2  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180034ef9  mov     edx, 27h ; '''
0x180034efe  call    WPP_SF_
0x180034f03  jmp     loc_180034DFD
```
