# IsDhcpSendUnicastMessagesEnabled(void)

- ea: `0x180043150`
- end: `0x180043340`
- name: `?IsDhcpSendUnicastMessagesEnabled@@YAHXZ`
- size: `496`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180002070`

## callees

- `0x18000c110`
- `0x18004215c`
- `0x180043150`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800432cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800432cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043268`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043268`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800432e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800432e7`

## string_xrefs

- `0x1800431a9`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsDhcpSendUnicastMessagesEnabled(void)
{
  BOOL v0; // ebx
  __int64 v1; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids);
  }
  v0 = 1;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"DisableSendUnicastDHCPessages");
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids);
    }
  }
  else
  {
    if ( !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
      v0 = *(_DWORD *)Data == 0;
    RegCloseKey(hKey);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      LOBYTE(v1) = v0;
      WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids, v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180043150  mov     [rsp-8+arg_0], rbx
0x180043155  mov     [rsp-8+arg_8], r14
0x18004315a  push    rbp
0x18004315b  lea     rbp, [rsp-10h]
0x180043160  sub     rsp, 110h
0x180043167  mov     rax, cs:__security_cookie
0x18004316e  xor     rax, rsp
0x180043171  mov     [rbp+10h+var_10], rax
0x180043175  mov     rcx, cs:WPP_GLOBAL_Control
0x18004317c  lea     r14, WPP_GLOBAL_Control
0x180043183  cmp     rcx, r14
0x180043186  jz      short loc_1800431A9
0x180043188  test    byte ptr [rcx+1Ch], 2
0x18004318c  jz      short loc_1800431A9
0x18004318e  cmp     byte ptr [rcx+19h], 6
0x180043192  jb      short loc_1800431A9
0x180043194  mov     rcx, [rcx+10h]
0x180043198  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x18004319f  mov     edx, 5Ch ; '\'
0x1800431a4  call    WPP_SF_
0x1800431a9  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x1800431b0  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x1800431b4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x1800431bb  mov     ebx, 1
0x1800431c0  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x1800431c6  mov     r9d, ebx; samDesired
0x1800431c9  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x1800431cd  xor     r8d, r8d; ulOptions
0x1800431d0  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x1800431d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800431de  movaps  [rbp+10h+var_70], xmm0
0x1800431e2  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x1800431e9  movaps  [rbp+10h+var_80], xmm1
0x1800431ed  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x1800431f4  movaps  [rbp+10h+var_50], xmm0
0x1800431f8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x1800431ff  movaps  [rbp+10h+var_60], xmm1
0x180043203  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18004320a  movaps  [rbp+10h+var_30], xmm0
0x18004320e  movups  xmm0, xmmword ptr cs:aDisablesenduni; "DisableSendUnicastDHCPMessages"
0x180043215  mov     [rbp+10h+var_20], eax
0x180043218  lea     rax, [rsp+110h+hKey]
0x18004321d  movaps  [rbp+10h+var_40], xmm1
0x180043221  movups  xmm1, xmmword ptr cs:aDisablesenduni+10h; "endUnicastDHCPMessages"
0x180043228  mov     [rsp+110h+hKey], 0
0x180043231  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x180043236  mov     dword ptr [rsp+110h+Data], 0
0x18004323e  movups  xmm0, xmmword ptr cs:aDisablesenduni+20h; "stDHCPMessages"
0x180043245  mov     [rsp+110h+cbData], 4
0x18004324d  movups  [rsp+110h+var_C0], xmm1
0x180043252  mov     [rsp+110h+phkResult], rax; phkResult
0x180043257  movups  xmm1, xmmword ptr cs:aDisablesenduni+2Eh; "essages"
0x18004325e  movups  [rsp+110h+var_B0], xmm0
0x180043263  movups  [rsp+110h+var_B0+0Eh], xmm1
0x180043268  call    cs:__imp_RegOpenKeyExW
0x18004326e  test    eax, eax
0x180043270  jz      short loc_1800432AB
0x180043272  mov     rcx, cs:WPP_GLOBAL_Control
0x180043279  cmp     rcx, r14
0x18004327c  jz      loc_18004331D
0x180043282  test    byte ptr [rcx+1Ch], 2
0x180043286  jz      loc_18004331D
0x18004328c  cmp     byte ptr [rcx+19h], 6
0x180043290  jb      loc_18004331D
0x180043296  mov     rcx, [rcx+10h]
0x18004329a  lea     edx, [rbx+5Ch]
0x18004329d  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x1800432a4  call    WPP_SF_
0x1800432a9  jmp     short loc_18004331D
0x1800432ab  mov     rcx, [rsp+110h+hKey]; hKey
0x1800432b0  lea     rax, [rsp+110h+cbData]
0x1800432b5  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800432ba  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x1800432bf  lea     rax, [rsp+110h+Data]
0x1800432c4  xor     r9d, r9d; lpType
0x1800432c7  xor     r8d, r8d; lpReserved
0x1800432ca  mov     [rsp+110h+phkResult], rax; lpData
0x1800432cf  call    cs:__imp_RegQueryValueExW
0x1800432d5  test    eax, eax
0x1800432d7  jnz     short loc_1800432E2
0x1800432d9  xor     ebx, ebx
0x1800432db  cmp     dword ptr [rsp+110h+Data], ebx
0x1800432df  setz    bl
0x1800432e2  mov     rcx, [rsp+110h+hKey]; hKey
0x1800432e7  call    cs:__imp_RegCloseKey
0x1800432ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432f4  cmp     rcx, r14
0x1800432f7  jz      short loc_18004331D
0x1800432f9  test    byte ptr [rcx+1Ch], 2
0x1800432fd  jz      short loc_18004331D
0x1800432ff  cmp     byte ptr [rcx+19h], 6
0x180043303  jb      short loc_18004331D
0x180043305  mov     rcx, [rcx+10h]
0x180043309  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x180043310  mov     r9b, bl
0x180043313  mov     edx, 5Eh ; '^'
0x180043318  call    WPP_SF_c
0x18004331d  mov     eax, ebx
0x18004331f  mov     rcx, [rbp+10h+var_10]
0x180043323  xor     rcx, rsp; StackCookie
0x180043326  call    __security_check_cookie
0x18004332b  lea     r11, [rsp+110h+var_s0]
0x180043333  mov     rbx, [r11+10h]
0x180043337  mov     r14, [r11+18h]
0x18004333b  mov     rsp, r11
0x18004333e  pop     rbp
0x18004333f  retn
```
