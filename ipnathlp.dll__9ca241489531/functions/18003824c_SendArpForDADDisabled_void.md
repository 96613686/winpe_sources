# SendArpForDADDisabled(void)

- ea: `0x18003824c`
- end: `0x18003841a`
- name: `?SendArpForDADDisabled@@YAHXZ`
- size: `462`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180037d60`
- `0x180037f50`

## callees

- `0x18000c110`
- `0x18003824c`
- `0x18004215c`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800383ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003834f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003834f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383c1`

## string_xrefs

- `0x1800382a5`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

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
0x18003824c  mov     [rsp-8+arg_0], rbx
0x180038251  mov     [rsp-8+arg_8], r14
0x180038256  push    rbp
0x180038257  lea     rbp, [rsp-57h]
0x18003825c  sub     rsp, 100h
0x180038263  mov     rax, cs:__security_cookie
0x18003826a  xor     rax, rsp
0x18003826d  mov     [rbp+57h+var_10], rax
0x180038271  mov     rcx, cs:WPP_GLOBAL_Control
0x180038278  lea     r14, WPP_GLOBAL_Control
0x18003827f  cmp     rcx, r14
0x180038282  jz      short loc_1800382A5
0x180038284  test    byte ptr [rcx+1Ch], 2
0x180038288  jz      short loc_1800382A5
0x18003828a  cmp     byte ptr [rcx+19h], 6
0x18003828e  jb      short loc_1800382A5
0x180038290  mov     rcx, [rcx+10h]
0x180038294  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18003829b  mov     edx, 59h ; 'Y'
0x1800382a0  call    WPP_SF_
0x1800382a5  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x1800382ac  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800382b0  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x1800382b7  mov     r9d, 1; samDesired
0x1800382bd  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x1800382c3  xor     r8d, r8d; ulOptions
0x1800382c6  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x1800382ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800382d1  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x1800382d8  movaps  [rbp+57h+var_70], xmm0
0x1800382dc  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x1800382e3  movaps  [rbp+57h+var_50], xmm0
0x1800382e7  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x1800382ee  movaps  [rbp+57h+var_80], xmm1
0x1800382f2  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x1800382f9  movaps  [rbp+57h+var_30], xmm0
0x1800382fd  movups  xmm0, xmmword ptr cs:aDisablesendarp; "DisableSendArpForDAD"
0x180038304  mov     [rbp+57h+var_20], eax
0x180038307  lea     rax, [rbp+57h+hKey]
0x18003830b  movaps  [rbp+57h+var_60], xmm1
0x18003830f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180038316  movaps  [rbp+57h+var_40], xmm1
0x18003831a  movups  xmm1, xmmword ptr cs:aDisablesendarp+10h; "endArpForDAD"
0x180038321  mov     [rbp+57h+hKey], 0
0x180038329  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x18003832d  mov     dword ptr [rbp+57h+Data], 0
0x180038334  movups  xmm0, xmmword ptr cs:aDisablesendarp+1Ah; "pForDAD"
0x18003833b  mov     [rbp+57h+cbData], 4
0x180038342  movups  [rbp+57h+var_B0], xmm1
0x180038346  mov     [rsp+100h+phkResult], rax; phkResult
0x18003834b  movups  [rbp+57h+var_B0+0Ah], xmm0
0x18003834f  call    cs:__imp_RegOpenKeyExW
0x180038355  test    eax, eax
0x180038357  jz      short loc_18003838A
0x180038359  mov     rcx, cs:WPP_GLOBAL_Control
0x180038360  cmp     rcx, r14
0x180038363  jz      short loc_180038386
0x180038365  test    byte ptr [rcx+1Ch], 2
0x180038369  jz      short loc_180038386
0x18003836b  cmp     byte ptr [rcx+19h], 6
0x18003836f  jb      short loc_180038386
0x180038371  mov     rcx, [rcx+10h]
0x180038375  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18003837c  mov     edx, 5Ah ; 'Z'
0x180038381  call    WPP_SF_
0x180038386  xor     eax, eax
0x180038388  jmp     short loc_1800383F9
0x18003838a  mov     rcx, [rbp+57h+hKey]; hKey
0x18003838e  lea     rax, [rbp+57h+cbData]
0x180038392  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180038397  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18003839b  lea     rax, [rbp+57h+Data]
0x18003839f  xor     r9d, r9d; lpType
0x1800383a2  xor     r8d, r8d; lpReserved
0x1800383a5  mov     [rsp+100h+phkResult], rax; lpData
0x1800383aa  xor     ebx, ebx
0x1800383ac  call    cs:__imp_RegQueryValueExW
0x1800383b2  test    eax, eax
0x1800383b4  jnz     short loc_1800383BD
0x1800383b6  cmp     dword ptr [rbp+57h+Data], 1
0x1800383ba  setnz   bl
0x1800383bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800383c1  call    cs:__imp_RegCloseKey
0x1800383c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383ce  cmp     rcx, r14
0x1800383d1  jz      short loc_1800383F7
0x1800383d3  test    byte ptr [rcx+1Ch], 2
0x1800383d7  jz      short loc_1800383F7
0x1800383d9  cmp     byte ptr [rcx+19h], 6
0x1800383dd  jb      short loc_1800383F7
0x1800383df  mov     rcx, [rcx+10h]
0x1800383e3  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x1800383ea  mov     r9b, bl
0x1800383ed  mov     edx, 5Bh ; '['
0x1800383f2  call    WPP_SF_c
0x1800383f7  mov     eax, ebx
0x1800383f9  mov     rcx, [rbp+57h+var_10]
0x1800383fd  xor     rcx, rsp; StackCookie
0x180038400  call    __security_check_cookie
0x180038405  lea     r11, [rsp+100h+var_s0]
0x18003840d  mov     rbx, [r11+10h]
0x180038411  mov     r14, [r11+18h]
0x180038415  mov     rsp, r11
0x180038418  pop     rbp
0x180038419  retn
```
