# SendArpForDADDisabled(void)

- ea: `0x18003b038`
- end: `0x18003b219`
- name: `?SendArpForDADDisabled@@YAHXZ`
- size: `481`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003aab0`
- `0x18003acd0`

## callees

- `0x18000ca20`
- `0x18003b038`
- `0x18004561c`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b19e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b19e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b13b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b13b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b1b9`

## string_xrefs

- `0x18003b091`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
__int64 SendArpForDADDisabled(void)
{
  unsigned int v1; // ebx
  __int64 v2; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-79h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-75h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  WCHAR ValueName[24]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR SubKey[64]; // [rsp+70h] [rbp-39h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids);
  }
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"DisableSenpForDAD");
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids);
    }
    return 0;
  }
  else
  {
    v1 = 0;
    if ( !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
      LOBYTE(v1) = *(_DWORD *)Data != 1;
    RegCloseKey(hKey);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      LOBYTE(v2) = v1;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids, v2);
    }
    return v1;
  }
}

```

## disassembly

```asm
0x18003b038  mov     [rsp-8+arg_0], rbx
0x18003b03d  mov     [rsp-8+arg_8], r14
0x18003b042  push    rbp
0x18003b043  lea     rbp, [rsp-57h]
0x18003b048  sub     rsp, 100h
0x18003b04f  mov     rax, cs:__security_cookie
0x18003b056  xor     rax, rsp
0x18003b059  mov     [rbp+57h+var_10], rax
0x18003b05d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b064  lea     r14, WPP_GLOBAL_Control
0x18003b06b  cmp     rcx, r14
0x18003b06e  jz      short loc_18003B091
0x18003b070  test    byte ptr [rcx+1Ch], 2
0x18003b074  jz      short loc_18003B091
0x18003b076  cmp     byte ptr [rcx+19h], 6
0x18003b07a  jb      short loc_18003B091
0x18003b07c  mov     rcx, [rcx+10h]
0x18003b080  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18003b087  mov     edx, 59h ; 'Y'
0x18003b08c  call    WPP_SF_
0x18003b091  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18003b098  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003b09c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18003b0a3  mov     r9d, 1; samDesired
0x18003b0a9  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18003b0af  xor     r8d, r8d; ulOptions
0x18003b0b2  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18003b0b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b0bd  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18003b0c4  movaps  [rbp+57h+var_70], xmm0
0x18003b0c8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18003b0cf  movaps  [rbp+57h+var_50], xmm0
0x18003b0d3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18003b0da  movaps  [rbp+57h+var_80], xmm1
0x18003b0de  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x18003b0e5  movaps  [rbp+57h+var_30], xmm0
0x18003b0e9  movups  xmm0, xmmword ptr cs:aDisablesendarp; "DisableSendArpForDAD"
0x18003b0f0  mov     [rbp+57h+var_20], eax
0x18003b0f3  lea     rax, [rbp+57h+hKey]
0x18003b0f7  movaps  [rbp+57h+var_60], xmm1
0x18003b0fb  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18003b102  movaps  [rbp+57h+var_40], xmm1
0x18003b106  movups  xmm1, xmmword ptr cs:aDisablesendarp+10h; "endArpForDAD"
0x18003b10d  mov     [rbp+57h+hKey], 0
0x18003b115  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18003b119  mov     dword ptr [rbp+57h+Data], 0
0x18003b120  movups  xmm0, xmmword ptr cs:aDisablesendarp+1Ah; "pForDAD"
0x18003b127  mov     [rbp+57h+cbData], 4
0x18003b12e  movups  [rbp+57h+var_B0], xmm1
0x18003b132  mov     [rsp+100h+phkResult], rax; phkResult
0x18003b137  movups  [rbp+57h+var_B0+0Ah], xmm0
0x18003b13b  call    cs:__imp_RegOpenKeyExW
0x18003b142  nop     dword ptr [rax+rax+00h]
0x18003b147  test    eax, eax
0x18003b149  jz      short loc_18003B17C
0x18003b14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b152  cmp     rcx, r14
0x18003b155  jz      short loc_18003B178
0x18003b157  test    byte ptr [rcx+1Ch], 2
0x18003b15b  jz      short loc_18003B178
0x18003b15d  cmp     byte ptr [rcx+19h], 6
0x18003b161  jb      short loc_18003B178
0x18003b163  mov     rcx, [rcx+10h]
0x18003b167  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18003b16e  mov     edx, 5Ah ; 'Z'
0x18003b173  call    WPP_SF_
0x18003b178  xor     eax, eax
0x18003b17a  jmp     short loc_18003B1F7
0x18003b17c  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b180  lea     rax, [rbp+57h+cbData]
0x18003b184  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18003b189  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18003b18d  lea     rax, [rbp+57h+Data]
0x18003b191  xor     r9d, r9d; lpType
0x18003b194  xor     r8d, r8d; lpReserved
0x18003b197  mov     [rsp+100h+phkResult], rax; lpData
0x18003b19c  xor     ebx, ebx
0x18003b19e  call    cs:__imp_RegQueryValueExW
0x18003b1a5  nop     dword ptr [rax+rax+00h]
0x18003b1aa  test    eax, eax
0x18003b1ac  jnz     short loc_18003B1B5
0x18003b1ae  cmp     dword ptr [rbp+57h+Data], 1
0x18003b1b2  setnz   bl
0x18003b1b5  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b1b9  call    cs:__imp_RegCloseKey
0x18003b1c0  nop     dword ptr [rax+rax+00h]
0x18003b1c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1cc  cmp     rcx, r14
0x18003b1cf  jz      short loc_18003B1F5
0x18003b1d1  test    byte ptr [rcx+1Ch], 2
0x18003b1d5  jz      short loc_18003B1F5
0x18003b1d7  cmp     byte ptr [rcx+19h], 6
0x18003b1db  jb      short loc_18003B1F5
0x18003b1dd  mov     rcx, [rcx+10h]
0x18003b1e1  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18003b1e8  mov     r9b, bl
0x18003b1eb  mov     edx, 5Bh ; '['
0x18003b1f0  call    WPP_SF_c
0x18003b1f5  mov     eax, ebx
0x18003b1f7  mov     rcx, [rbp+57h+var_10]
0x18003b1fb  xor     rcx, rsp; StackCookie
0x18003b1fe  call    __security_check_cookie
0x18003b203  lea     r11, [rsp+100h+var_s0]
0x18003b20b  mov     rbx, [r11+10h]
0x18003b20f  mov     r14, [r11+18h]
0x18003b213  mov     rsp, r11
0x18003b216  pop     rbp
0x18003b217  retn
```
