# V2SendArpForDADDisabled(void)

- ea: `0x1800459d8`
- end: `0x180045bb6`
- name: `?V2SendArpForDADDisabled@@YAHXZ`
- size: `478`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002070`
- `0x18008ad10`

## callees

- `0x18000ca20`
- `0x1800459d8`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045b3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045adb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045adb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045b59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045b59`

## string_xrefs

- `0x180045a31`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
__int64 V2SendArpForDADDisabled(void)
{
  unsigned int v1; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-79h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-75h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  WCHAR ValueName[24]; // [rsp+40h] [rbp-69h] BYREF
  WCHAR SubKey[64]; // [rsp+70h] [rbp-39h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
    }
    return v1;
  }
}

```

## disassembly

```asm
0x1800459d8  mov     [rsp-8+arg_0], rbx
0x1800459dd  mov     [rsp-8+arg_8], r14
0x1800459e2  push    rbp
0x1800459e3  lea     rbp, [rsp-57h]
0x1800459e8  sub     rsp, 100h
0x1800459ef  mov     rax, cs:__security_cookie
0x1800459f6  xor     rax, rsp
0x1800459f9  mov     [rbp+57h+var_10], rax
0x1800459fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180045a04  lea     r14, WPP_GLOBAL_Control
0x180045a0b  cmp     rcx, r14
0x180045a0e  jz      short loc_180045A31
0x180045a10  test    byte ptr [rcx+1Ch], 2
0x180045a14  jz      short loc_180045A31
0x180045a16  cmp     byte ptr [rcx+19h], 6
0x180045a1a  jb      short loc_180045A31
0x180045a1c  mov     rcx, [rcx+10h]
0x180045a20  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180045a27  mov     edx, 59h ; 'Y'
0x180045a2c  call    WPP_SF_
0x180045a31  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180045a38  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180045a3c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180045a43  mov     r9d, 1; samDesired
0x180045a49  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180045a4f  xor     r8d, r8d; ulOptions
0x180045a52  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180045a56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045a5d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180045a64  movaps  [rbp+57h+var_70], xmm0
0x180045a68  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180045a6f  movaps  [rbp+57h+var_50], xmm0
0x180045a73  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180045a7a  movaps  [rbp+57h+var_80], xmm1
0x180045a7e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180045a85  movaps  [rbp+57h+var_30], xmm0
0x180045a89  movups  xmm0, xmmword ptr cs:aDisablesendarp; "DisableSendArpForDAD"
0x180045a90  mov     [rbp+57h+var_20], eax
0x180045a93  lea     rax, [rbp+57h+hKey]
0x180045a97  movaps  [rbp+57h+var_60], xmm1
0x180045a9b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180045aa2  movaps  [rbp+57h+var_40], xmm1
0x180045aa6  movups  xmm1, xmmword ptr cs:aDisablesendarp+10h; "endArpForDAD"
0x180045aad  mov     [rbp+57h+hKey], 0
0x180045ab5  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180045ab9  mov     dword ptr [rbp+57h+Data], 0
0x180045ac0  movups  xmm0, xmmword ptr cs:aDisablesendarp+1Ah; "pForDAD"
0x180045ac7  mov     [rbp+57h+cbData], 4
0x180045ace  movups  [rbp+57h+var_B0], xmm1
0x180045ad2  mov     [rsp+100h+phkResult], rax; phkResult
0x180045ad7  movups  [rbp+57h+var_B0+0Ah], xmm0
0x180045adb  call    cs:__imp_RegOpenKeyExW
0x180045ae2  nop     dword ptr [rax+rax+00h]
0x180045ae7  test    eax, eax
0x180045ae9  jz      short loc_180045B1C
0x180045aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045af2  cmp     rcx, r14
0x180045af5  jz      short loc_180045B18
0x180045af7  test    byte ptr [rcx+1Ch], 2
0x180045afb  jz      short loc_180045B18
0x180045afd  cmp     byte ptr [rcx+19h], 6
0x180045b01  jb      short loc_180045B18
0x180045b03  mov     rcx, [rcx+10h]
0x180045b07  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180045b0e  mov     edx, 5Ah ; 'Z'
0x180045b13  call    WPP_SF_
0x180045b18  xor     eax, eax
0x180045b1a  jmp     short loc_180045B94
0x180045b1c  mov     rcx, [rbp+57h+hKey]; hKey
0x180045b20  lea     rax, [rbp+57h+cbData]
0x180045b24  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180045b29  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180045b2d  lea     rax, [rbp+57h+Data]
0x180045b31  xor     r9d, r9d; lpType
0x180045b34  xor     r8d, r8d; lpReserved
0x180045b37  mov     [rsp+100h+phkResult], rax; lpData
0x180045b3c  xor     ebx, ebx
0x180045b3e  call    cs:__imp_RegQueryValueExW
0x180045b45  nop     dword ptr [rax+rax+00h]
0x180045b4a  test    eax, eax
0x180045b4c  jnz     short loc_180045B55
0x180045b4e  cmp     dword ptr [rbp+57h+Data], 1
0x180045b52  setnz   bl
0x180045b55  mov     rcx, [rbp+57h+hKey]; hKey
0x180045b59  call    cs:__imp_RegCloseKey
0x180045b60  nop     dword ptr [rax+rax+00h]
0x180045b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180045b6c  cmp     rcx, r14
0x180045b6f  jz      short loc_180045B92
0x180045b71  test    byte ptr [rcx+1Ch], 2
0x180045b75  jz      short loc_180045B92
0x180045b77  cmp     byte ptr [rcx+19h], 6
0x180045b7b  jb      short loc_180045B92
0x180045b7d  mov     rcx, [rcx+10h]
0x180045b81  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180045b88  mov     edx, 5Bh ; '['
0x180045b8d  call    WPP_SF_
0x180045b92  mov     eax, ebx
0x180045b94  mov     rcx, [rbp+57h+var_10]
0x180045b98  xor     rcx, rsp; StackCookie
0x180045b9b  call    __security_check_cookie
0x180045ba0  lea     r11, [rsp+100h+var_s0]
0x180045ba8  mov     rbx, [r11+10h]
0x180045bac  mov     r14, [r11+18h]
0x180045bb0  mov     rsp, r11
0x180045bb3  pop     rbp
0x180045bb4  retn
```
