# V2IsDhcpSendUnicastMessagesEnabled(void)

- ea: `0x180045424`
- end: `0x180045614`
- name: `?V2IsDhcpSendUnicastMessagesEnabled@@YAHXZ`
- size: `496`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002050`

## callees

- `0x18000ca20`
- `0x180045424`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045599`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180045599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004553c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004553c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800455b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800455b7`

## string_xrefs

- `0x18004547d`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 V2IsDhcpSendUnicastMessagesEnabled(void)
{
  BOOL v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
  }
  v0 = 1;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"DisableSendUnicastDHCPessages");
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v2 = 93;
LABEL_16:
      WPP_SF_(v1[2], v2, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids);
    }
  }
  else
  {
    if ( !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
      v0 = *(_DWORD *)Data == 0;
    RegCloseKey(hKey);
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v2 = 94;
      goto LABEL_16;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180045424  mov     [rsp-8+arg_0], rbx
0x180045429  mov     [rsp-8+arg_8], r14
0x18004542e  push    rbp
0x18004542f  lea     rbp, [rsp-10h]
0x180045434  sub     rsp, 110h
0x18004543b  mov     rax, cs:__security_cookie
0x180045442  xor     rax, rsp
0x180045445  mov     [rbp+10h+var_10], rax
0x180045449  mov     rcx, cs:WPP_GLOBAL_Control
0x180045450  lea     r14, WPP_GLOBAL_Control
0x180045457  cmp     rcx, r14
0x18004545a  jz      short loc_18004547D
0x18004545c  test    byte ptr [rcx+1Ch], 2
0x180045460  jz      short loc_18004547D
0x180045462  cmp     byte ptr [rcx+19h], 6
0x180045466  jb      short loc_18004547D
0x180045468  mov     rcx, [rcx+10h]
0x18004546c  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180045473  mov     edx, 5Ch ; '\'
0x180045478  call    WPP_SF_
0x18004547d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180045484  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x180045488  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18004548f  mov     ebx, 1
0x180045494  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18004549a  mov     r9d, ebx; samDesired
0x18004549d  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x1800454a1  xor     r8d, r8d; ulOptions
0x1800454a4  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x1800454ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800454b2  movaps  [rbp+10h+var_70], xmm0
0x1800454b6  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x1800454bd  movaps  [rbp+10h+var_80], xmm1
0x1800454c1  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x1800454c8  movaps  [rbp+10h+var_50], xmm0
0x1800454cc  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x1800454d3  movaps  [rbp+10h+var_60], xmm1
0x1800454d7  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x1800454de  movaps  [rbp+10h+var_30], xmm0
0x1800454e2  movups  xmm0, xmmword ptr cs:aDisablesenduni; "DisableSendUnicastDHCPMessages"
0x1800454e9  mov     [rbp+10h+var_20], eax
0x1800454ec  lea     rax, [rsp+110h+hKey]
0x1800454f1  movaps  [rbp+10h+var_40], xmm1
0x1800454f5  movups  xmm1, xmmword ptr cs:aDisablesenduni+10h; "endUnicastDHCPMessages"
0x1800454fc  mov     [rsp+110h+hKey], 0
0x180045505  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x18004550a  mov     dword ptr [rsp+110h+Data], 0
0x180045512  movups  xmm0, xmmword ptr cs:aDisablesenduni+20h; "stDHCPMessages"
0x180045519  mov     [rsp+110h+cbData], 4
0x180045521  movups  [rsp+110h+var_C0], xmm1
0x180045526  mov     [rsp+110h+phkResult], rax; phkResult
0x18004552b  movups  xmm1, xmmword ptr cs:aDisablesenduni+2Eh; "essages"
0x180045532  movups  [rsp+110h+var_B0], xmm0
0x180045537  movups  [rsp+110h+var_B0+0Eh], xmm1
0x18004553c  call    cs:__imp_RegOpenKeyExW
0x180045543  nop     dword ptr [rax+rax+00h]
0x180045548  test    eax, eax
0x18004554a  jz      short loc_180045575
0x18004554c  mov     rcx, cs:WPP_GLOBAL_Control
0x180045553  cmp     rcx, r14
0x180045556  jz      loc_1800455F0
0x18004555c  test    byte ptr [rcx+1Ch], 2
0x180045560  jz      loc_1800455F0
0x180045566  cmp     byte ptr [rcx+19h], 6
0x18004556a  jb      loc_1800455F0
0x180045570  lea     edx, [rbx+5Ch]
0x180045573  jmp     short loc_1800455E0
0x180045575  mov     rcx, [rsp+110h+hKey]; hKey
0x18004557a  lea     rax, [rsp+110h+cbData]
0x18004557f  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180045584  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x180045589  lea     rax, [rsp+110h+Data]
0x18004558e  xor     r9d, r9d; lpType
0x180045591  xor     r8d, r8d; lpReserved
0x180045594  mov     [rsp+110h+phkResult], rax; lpData
0x180045599  call    cs:__imp_RegQueryValueExW
0x1800455a0  nop     dword ptr [rax+rax+00h]
0x1800455a5  test    eax, eax
0x1800455a7  jnz     short loc_1800455B2
0x1800455a9  xor     ebx, ebx
0x1800455ab  cmp     dword ptr [rsp+110h+Data], ebx
0x1800455af  setz    bl
0x1800455b2  mov     rcx, [rsp+110h+hKey]; hKey
0x1800455b7  call    cs:__imp_RegCloseKey
0x1800455be  nop     dword ptr [rax+rax+00h]
0x1800455c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800455ca  cmp     rcx, r14
0x1800455cd  jz      short loc_1800455F0
0x1800455cf  test    byte ptr [rcx+1Ch], 2
0x1800455d3  jz      short loc_1800455F0
0x1800455d5  cmp     byte ptr [rcx+19h], 6
0x1800455d9  jb      short loc_1800455F0
0x1800455db  mov     edx, 5Eh ; '^'
0x1800455e0  mov     rcx, [rcx+10h]
0x1800455e4  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x1800455eb  call    WPP_SF_
0x1800455f0  mov     eax, ebx
0x1800455f2  mov     rcx, [rbp+10h+var_10]
0x1800455f6  xor     rcx, rsp; StackCookie
0x1800455f9  call    __security_check_cookie
0x1800455fe  lea     r11, [rsp+110h+var_s0]
0x180045606  mov     rbx, [r11+10h]
0x18004560a  mov     r14, [r11+18h]
0x18004560e  mov     rsp, r11
0x180045611  pop     rbp
0x180045612  retn
```
