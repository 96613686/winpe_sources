# V2SendArpForDADDisabled(void)

- ea: `0x18004219c`
- end: `0x180042367`
- name: `?V2SendArpForDADDisabled@@YAHXZ`
- size: `459`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002050`
- `0x180084440`

## callees

- `0x18000c110`
- `0x18004219c`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800422fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800422fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004229f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004229f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042311`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042311`

## string_xrefs

- `0x1800421f5`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

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
0x18004219c  mov     [rsp-8+arg_0], rbx
0x1800421a1  mov     [rsp-8+arg_8], r14
0x1800421a6  push    rbp
0x1800421a7  lea     rbp, [rsp-57h]
0x1800421ac  sub     rsp, 100h
0x1800421b3  mov     rax, cs:__security_cookie
0x1800421ba  xor     rax, rsp
0x1800421bd  mov     [rbp+57h+var_10], rax
0x1800421c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421c8  lea     r14, WPP_GLOBAL_Control
0x1800421cf  cmp     rcx, r14
0x1800421d2  jz      short loc_1800421F5
0x1800421d4  test    byte ptr [rcx+1Ch], 2
0x1800421d8  jz      short loc_1800421F5
0x1800421da  cmp     byte ptr [rcx+19h], 6
0x1800421de  jb      short loc_1800421F5
0x1800421e0  mov     rcx, [rcx+10h]
0x1800421e4  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x1800421eb  mov     edx, 59h ; 'Y'
0x1800421f0  call    WPP_SF_
0x1800421f5  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x1800421fc  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180042200  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180042207  mov     r9d, 1; samDesired
0x18004220d  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180042213  xor     r8d, r8d; ulOptions
0x180042216  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18004221a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042221  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180042228  movaps  [rbp+57h+var_70], xmm0
0x18004222c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180042233  movaps  [rbp+57h+var_50], xmm0
0x180042237  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18004223e  movaps  [rbp+57h+var_80], xmm1
0x180042242  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180042249  movaps  [rbp+57h+var_30], xmm0
0x18004224d  movups  xmm0, xmmword ptr cs:aDisablesendarp; "DisableSendArpForDAD"
0x180042254  mov     [rbp+57h+var_20], eax
0x180042257  lea     rax, [rbp+57h+hKey]
0x18004225b  movaps  [rbp+57h+var_60], xmm1
0x18004225f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180042266  movaps  [rbp+57h+var_40], xmm1
0x18004226a  movups  xmm1, xmmword ptr cs:aDisablesendarp+10h; "endArpForDAD"
0x180042271  mov     [rbp+57h+hKey], 0
0x180042279  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18004227d  mov     dword ptr [rbp+57h+Data], 0
0x180042284  movups  xmm0, xmmword ptr cs:aDisablesendarp+1Ah; "pForDAD"
0x18004228b  mov     [rbp+57h+cbData], 4
0x180042292  movups  [rbp+57h+var_B0], xmm1
0x180042296  mov     [rsp+100h+phkResult], rax; phkResult
0x18004229b  movups  [rbp+57h+var_B0+0Ah], xmm0
0x18004229f  call    cs:__imp_RegOpenKeyExW
0x1800422a5  test    eax, eax
0x1800422a7  jz      short loc_1800422DA
0x1800422a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800422b0  cmp     rcx, r14
0x1800422b3  jz      short loc_1800422D6
0x1800422b5  test    byte ptr [rcx+1Ch], 2
0x1800422b9  jz      short loc_1800422D6
0x1800422bb  cmp     byte ptr [rcx+19h], 6
0x1800422bf  jb      short loc_1800422D6
0x1800422c1  mov     rcx, [rcx+10h]
0x1800422c5  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x1800422cc  mov     edx, 5Ah ; 'Z'
0x1800422d1  call    WPP_SF_
0x1800422d6  xor     eax, eax
0x1800422d8  jmp     short loc_180042346
0x1800422da  mov     rcx, [rbp+57h+hKey]; hKey
0x1800422de  lea     rax, [rbp+57h+cbData]
0x1800422e2  mov     [rsp+100h+lpcbData], rax; lpcbData
0x1800422e7  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x1800422eb  lea     rax, [rbp+57h+Data]
0x1800422ef  xor     r9d, r9d; lpType
0x1800422f2  xor     r8d, r8d; lpReserved
0x1800422f5  mov     [rsp+100h+phkResult], rax; lpData
0x1800422fa  xor     ebx, ebx
0x1800422fc  call    cs:__imp_RegQueryValueExW
0x180042302  test    eax, eax
0x180042304  jnz     short loc_18004230D
0x180042306  cmp     dword ptr [rbp+57h+Data], 1
0x18004230a  setnz   bl
0x18004230d  mov     rcx, [rbp+57h+hKey]; hKey
0x180042311  call    cs:__imp_RegCloseKey
0x180042317  mov     rcx, cs:WPP_GLOBAL_Control
0x18004231e  cmp     rcx, r14
0x180042321  jz      short loc_180042344
0x180042323  test    byte ptr [rcx+1Ch], 2
0x180042327  jz      short loc_180042344
0x180042329  cmp     byte ptr [rcx+19h], 6
0x18004232d  jb      short loc_180042344
0x18004232f  mov     rcx, [rcx+10h]
0x180042333  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x18004233a  mov     edx, 5Bh ; '['
0x18004233f  call    WPP_SF_
0x180042344  mov     eax, ebx
0x180042346  mov     rcx, [rbp+57h+var_10]
0x18004234a  xor     rcx, rsp; StackCookie
0x18004234d  call    __security_check_cookie
0x180042352  lea     r11, [rsp+100h+var_s0]
0x18004235a  mov     rbx, [r11+10h]
0x18004235e  mov     r14, [r11+18h]
0x180042362  mov     rsp, r11
0x180042365  pop     rbp
0x180042366  retn
```
