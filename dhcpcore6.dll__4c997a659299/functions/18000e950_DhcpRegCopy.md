# DhcpRegCopy

- ea: `0x18000e950`
- end: `0x18000ebc1`
- name: `DhcpRegCopy`
- size: `625`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000e848`
- `0x180016440`

## callees

- `0x180007564`
- `0x18000e950`
- `0x18000ebc8`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb69`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ea00`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ea00`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eb1a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eb1a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000eadc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000eadc`

## pseudocode

```c
__int64 __fastcall DhcpRegCopy(HKEY hKey, HKEY a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  void *v6; // rsi
  DWORD v7; // edi
  __int64 v8; // rdx
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[104]; // [rsp+80h] [rbp-80h] BYREF

  cValues = 0;
  cchValueName = 0;
  cbMaxValueLen = 0;
  Type[0] = 0;
  cbData = 0;
  v4 = DhcpRegDeleteAll(a2);
  if ( v4 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      v5 = 91;
LABEL_24:
      WPP_SF_(1028, v5, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      return v4;
    }
    return v4;
  }
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  if ( !v4 )
  {
    if ( !cValues || !cbMaxValueLen )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v5 = 93;
        goto LABEL_24;
      }
      return v4;
    }
    cbMaxValueLen = 2 * cbMaxValueLen + 2;
    v6 = (void *)DhcpAlloc(cbMaxValueLen);
    if ( !v6 )
    {
      v4 = 8;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v5 = 94;
        goto LABEL_24;
      }
      return v4;
    }
    v7 = 0;
    if ( !cValues )
    {
LABEL_21:
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
      return v4;
    }
    while ( 1 )
    {
      cchValueName = 100;
      cbData = cbMaxValueLen;
      memset_0(v6, 0, cbMaxValueLen);
      memset_0(ValueName, 0, 2LL * cchValueName);
      v4 = RegEnumValueW(hKey, v7, ValueName, &cchValueName, 0, Type, (LPBYTE)v6, &cbData);
      if ( !v4 )
        break;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v8 = 95;
LABEL_19:
        WPP_SF_(1028, v8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      }
LABEL_20:
      if ( ++v7 >= cValues )
        goto LABEL_21;
    }
    v4 = RegSetValueExW(a2, ValueName, 0, Type[0], (const BYTE *)v6, cbData);
    if ( !v4 || (xmmword_1800423E0 & 0x10) == 0 )
      goto LABEL_20;
    v8 = 96;
    goto LABEL_19;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    v5 = 92;
    goto LABEL_24;
  }
  return v4;
}

```

## disassembly

```asm
0x18000e950  mov     [rsp-8+arg_10], rbx
0x18000e955  mov     [rsp-8+arg_18], rsi
0x18000e95a  push    rbp
0x18000e95b  push    rdi
0x18000e95c  push    r12
0x18000e95e  push    r14
0x18000e960  push    r15
0x18000e962  lea     rbp, [rsp-60h]
0x18000e967  sub     rsp, 160h
0x18000e96e  mov     rax, cs:__security_cookie
0x18000e975  xor     rax, rsp
0x18000e978  mov     [rbp+80h+var_30], rax
0x18000e97c  xor     r12d, r12d
0x18000e97f  mov     r15, rcx
0x18000e982  mov     rcx, rdx; hKey
0x18000e985  mov     [rsp+180h+cValues], r12d
0x18000e98a  mov     [rsp+180h+cchValueName], r12d
0x18000e98f  mov     r14, rdx
0x18000e992  mov     [rsp+180h+cbMaxValueLen], r12d
0x18000e997  mov     [rsp+180h+Type], r12d
0x18000e99c  mov     [rsp+180h+cbData], r12d
0x18000e9a1  call    DhcpRegDeleteAll
0x18000e9a6  mov     ebx, eax
0x18000e9a8  test    eax, eax
0x18000e9aa  jz      short loc_18000E9C3
0x18000e9ac  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e9b3  jz      loc_18000EB96
0x18000e9b9  lea     edx, [r12+5Bh]
0x18000e9be  jmp     loc_18000EB85
0x18000e9c3  mov     [rsp+180h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000e9c8  lea     rax, [rsp+180h+cbMaxValueLen]
0x18000e9cd  mov     [rsp+180h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000e9d2  xor     r9d, r9d; lpReserved
0x18000e9d5  mov     [rsp+180h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000e9da  xor     r8d, r8d; lpcchClass
0x18000e9dd  mov     [rsp+180h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18000e9e2  lea     rax, [rsp+180h+cValues]
0x18000e9e7  mov     [rsp+180h+lpcValues], rax; lpcValues
0x18000e9ec  xor     edx, edx; lpClass
0x18000e9ee  mov     [rsp+180h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000e9f3  mov     rcx, r15; hKey
0x18000e9f6  mov     [rsp+180h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000e9fb  mov     [rsp+180h+lpcSubKeys], r12; lpcSubKeys
0x18000ea00  call    cs:__imp_RegQueryInfoKeyW
0x18000ea07  nop     dword ptr [rax+rax+00h]
0x18000ea0c  mov     ebx, eax
0x18000ea0e  test    eax, eax
0x18000ea10  jz      short loc_18000EA29
0x18000ea12  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ea19  jz      loc_18000EB96
0x18000ea1f  mov     edx, 5Ch ; '\'
0x18000ea24  jmp     loc_18000EB85
0x18000ea29  cmp     [rsp+180h+cValues], r12d
0x18000ea2e  jz      loc_18000EB77
0x18000ea34  mov     eax, [rsp+180h+cbMaxValueLen]
0x18000ea38  test    eax, eax
0x18000ea3a  jz      loc_18000EB77
0x18000ea40  lea     eax, ds:2[rax*2]
0x18000ea47  mov     ecx, eax
0x18000ea49  mov     [rsp+180h+cbMaxValueLen], eax
0x18000ea4d  call    DhcpAlloc
0x18000ea52  mov     rsi, rax
0x18000ea55  test    rax, rax
0x18000ea58  jnz     short loc_18000EA72
0x18000ea5a  lea     ebx, [rax+8]
0x18000ea5d  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ea64  jz      loc_18000EB96
0x18000ea6a  lea     edx, [rax+5Eh]
0x18000ea6d  jmp     loc_18000EB85
0x18000ea72  mov     edi, r12d
0x18000ea75  cmp     [rsp+180h+cValues], r12d
0x18000ea7a  jbe     loc_18000EB57
0x18000ea80  mov     eax, [rsp+180h+cbMaxValueLen]
0x18000ea84  xor     edx, edx; Val
0x18000ea86  mov     r8d, eax; Size
0x18000ea89  mov     [rsp+180h+cchValueName], 64h ; 'd'
0x18000ea91  mov     rcx, rsi; void *
0x18000ea94  mov     [rsp+180h+cbData], eax
0x18000ea98  call    memset_0
0x18000ea9d  mov     r8d, [rsp+180h+cchValueName]
0x18000eaa2  lea     rcx, [rbp+80h+ValueName]; void *
0x18000eaa6  add     r8, r8; Size
0x18000eaa9  xor     edx, edx; Val
0x18000eaab  call    memset_0
0x18000eab0  lea     rax, [rsp+180h+cbData]
0x18000eab5  mov     edx, edi; dwIndex
0x18000eab7  mov     [rsp+180h+lpcValues], rax; lpcbData
0x18000eabc  lea     r9, [rsp+180h+cchValueName]; lpcchValueName
0x18000eac1  lea     rax, [rsp+180h+Type]
0x18000eac6  mov     [rsp+180h+lpcbMaxClassLen], rsi; lpData
0x18000eacb  mov     [rsp+180h+lpcbMaxSubKeyLen], rax; lpType
0x18000ead0  lea     r8, [rbp+80h+ValueName]; lpValueName
0x18000ead4  mov     rcx, r15; hKey
0x18000ead7  mov     [rsp+180h+lpcSubKeys], r12; lpReserved
0x18000eadc  call    cs:__imp_RegEnumValueW
0x18000eae3  nop     dword ptr [rax+rax+00h]
0x18000eae8  mov     ebx, eax
0x18000eaea  test    eax, eax
0x18000eaec  jz      short loc_18000EAFE
0x18000eaee  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000eaf5  jz      short loc_18000EB4B
0x18000eaf7  mov     edx, 5Fh ; '_'
0x18000eafc  jmp     short loc_18000EB3A
0x18000eafe  mov     eax, [rsp+180h+cbData]
0x18000eb02  lea     rdx, [rbp+80h+ValueName]; lpValueName
0x18000eb06  mov     r9d, [rsp+180h+Type]; dwType
0x18000eb0b  xor     r8d, r8d; Reserved
0x18000eb0e  mov     dword ptr [rsp+180h+lpcbMaxSubKeyLen], eax; cbData
0x18000eb12  mov     rcx, r14; hKey
0x18000eb15  mov     [rsp+180h+lpcSubKeys], rsi; lpData
0x18000eb1a  call    cs:__imp_RegSetValueExW
0x18000eb21  nop     dword ptr [rax+rax+00h]
0x18000eb26  mov     ebx, eax
0x18000eb28  test    eax, eax
0x18000eb2a  jz      short loc_18000EB4B
0x18000eb2c  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000eb33  jz      short loc_18000EB4B
0x18000eb35  mov     edx, 60h ; '`'
0x18000eb3a  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000eb41  mov     ecx, 404h
0x18000eb46  call    WPP_SF_
0x18000eb4b  inc     edi
0x18000eb4d  cmp     edi, [rsp+180h+cValues]
0x18000eb51  jb      loc_18000EA80
0x18000eb57  mov     rcx, gs:60h
0x18000eb60  mov     r8, rsi; lpMem
0x18000eb63  xor     edx, edx; dwFlags
0x18000eb65  mov     rcx, [rcx+30h]; hHeap
0x18000eb69  call    cs:__imp_HeapFree
0x18000eb70  nop     dword ptr [rax+rax+00h]
0x18000eb75  jmp     short loc_18000EB96
0x18000eb77  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000eb7e  jz      short loc_18000EB96
0x18000eb80  mov     edx, 5Dh ; ']'
0x18000eb85  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000eb8c  mov     ecx, 404h
0x18000eb91  call    WPP_SF_
0x18000eb96  mov     eax, ebx
0x18000eb98  mov     rcx, [rbp+80h+var_30]
0x18000eb9c  xor     rcx, rsp; StackCookie
0x18000eb9f  call    __security_check_cookie
0x18000eba4  lea     r11, [rsp+180h+var_20]
0x18000ebac  mov     rbx, [r11+40h]
0x18000ebb0  mov     rsi, [r11+48h]
0x18000ebb4  mov     rsp, r11
0x18000ebb7  pop     r15
0x18000ebb9  pop     r14
0x18000ebbb  pop     r12
0x18000ebbd  pop     rdi
0x18000ebbe  pop     rbp
0x18000ebbf  retn
```
