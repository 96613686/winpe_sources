# IsDhcpSendUnicastMessagesEnabled(void)

- ea: `0x180046a84`
- end: `0x180046c87`
- name: `?IsDhcpSendUnicastMessagesEnabled@@YAHXZ`
- size: `515`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180002090`

## callees

- `0x18000ca20`
- `0x18004561c`
- `0x180046a84`
- `0x180051f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046c09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046c09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046b9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046b9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046c27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046c27`

## string_xrefs

- `0x180046add`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

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
0x180046a84  mov     [rsp-8+arg_0], rbx
0x180046a89  mov     [rsp-8+arg_8], r14
0x180046a8e  push    rbp
0x180046a8f  lea     rbp, [rsp-10h]
0x180046a94  sub     rsp, 110h
0x180046a9b  mov     rax, cs:__security_cookie
0x180046aa2  xor     rax, rsp
0x180046aa5  mov     [rbp+10h+var_10], rax
0x180046aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ab0  lea     r14, WPP_GLOBAL_Control
0x180046ab7  cmp     rcx, r14
0x180046aba  jz      short loc_180046ADD
0x180046abc  test    byte ptr [rcx+1Ch], 2
0x180046ac0  jz      short loc_180046ADD
0x180046ac2  cmp     byte ptr [rcx+19h], 6
0x180046ac6  jb      short loc_180046ADD
0x180046ac8  mov     rcx, [rcx+10h]
0x180046acc  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x180046ad3  mov     edx, 5Ch ; '\'
0x180046ad8  call    WPP_SF_
0x180046add  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180046ae4  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x180046ae8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180046aef  mov     ebx, 1
0x180046af4  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180046afa  mov     r9d, ebx; samDesired
0x180046afd  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x180046b01  xor     r8d, r8d; ulOptions
0x180046b04  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180046b0b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180046b12  movaps  [rbp+10h+var_70], xmm0
0x180046b16  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180046b1d  movaps  [rbp+10h+var_80], xmm1
0x180046b21  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180046b28  movaps  [rbp+10h+var_50], xmm0
0x180046b2c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180046b33  movaps  [rbp+10h+var_60], xmm1
0x180046b37  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180046b3e  movaps  [rbp+10h+var_30], xmm0
0x180046b42  movups  xmm0, xmmword ptr cs:aDisablesenduni; "DisableSendUnicastDHCPMessages"
0x180046b49  mov     [rbp+10h+var_20], eax
0x180046b4c  lea     rax, [rsp+110h+hKey]
0x180046b51  movaps  [rbp+10h+var_40], xmm1
0x180046b55  movups  xmm1, xmmword ptr cs:aDisablesenduni+10h; "endUnicastDHCPMessages"
0x180046b5c  mov     [rsp+110h+hKey], 0
0x180046b65  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x180046b6a  mov     dword ptr [rsp+110h+Data], 0
0x180046b72  movups  xmm0, xmmword ptr cs:aDisablesenduni+20h; "stDHCPMessages"
0x180046b79  mov     [rsp+110h+cbData], 4
0x180046b81  movups  [rsp+110h+var_C0], xmm1
0x180046b86  mov     [rsp+110h+phkResult], rax; phkResult
0x180046b8b  movups  xmm1, xmmword ptr cs:aDisablesenduni+2Eh; "essages"
0x180046b92  movups  [rsp+110h+var_B0], xmm0
0x180046b97  movups  [rsp+110h+var_B0+0Eh], xmm1
0x180046b9c  call    cs:__imp_RegOpenKeyExW
0x180046ba3  nop     dword ptr [rax+rax+00h]
0x180046ba8  test    eax, eax
0x180046baa  jz      short loc_180046BE5
0x180046bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bb3  cmp     rcx, r14
0x180046bb6  jz      loc_180046C63
0x180046bbc  test    byte ptr [rcx+1Ch], 2
0x180046bc0  jz      loc_180046C63
0x180046bc6  cmp     byte ptr [rcx+19h], 6
0x180046bca  jb      loc_180046C63
0x180046bd0  mov     rcx, [rcx+10h]
0x180046bd4  lea     edx, [rbx+5Ch]
0x180046bd7  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x180046bde  call    WPP_SF_
0x180046be3  jmp     short loc_180046C63
0x180046be5  mov     rcx, [rsp+110h+hKey]; hKey
0x180046bea  lea     rax, [rsp+110h+cbData]
0x180046bef  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180046bf4  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x180046bf9  lea     rax, [rsp+110h+Data]
0x180046bfe  xor     r9d, r9d; lpType
0x180046c01  xor     r8d, r8d; lpReserved
0x180046c04  mov     [rsp+110h+phkResult], rax; lpData
0x180046c09  call    cs:__imp_RegQueryValueExW
0x180046c10  nop     dword ptr [rax+rax+00h]
0x180046c15  test    eax, eax
0x180046c17  jnz     short loc_180046C22
0x180046c19  xor     ebx, ebx
0x180046c1b  cmp     dword ptr [rsp+110h+Data], ebx
0x180046c1f  setz    bl
0x180046c22  mov     rcx, [rsp+110h+hKey]; hKey
0x180046c27  call    cs:__imp_RegCloseKey
0x180046c2e  nop     dword ptr [rax+rax+00h]
0x180046c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c3a  cmp     rcx, r14
0x180046c3d  jz      short loc_180046C63
0x180046c3f  test    byte ptr [rcx+1Ch], 2
0x180046c43  jz      short loc_180046C63
0x180046c45  cmp     byte ptr [rcx+19h], 6
0x180046c49  jb      short loc_180046C63
0x180046c4b  mov     rcx, [rcx+10h]
0x180046c4f  lea     r8, WPP_69f8adf245c63c1559ac8fe12caa5d77_Traceguids
0x180046c56  mov     r9b, bl
0x180046c59  mov     edx, 5Eh ; '^'
0x180046c5e  call    WPP_SF_c
0x180046c63  mov     eax, ebx
0x180046c65  mov     rcx, [rbp+10h+var_10]
0x180046c69  xor     rcx, rsp; StackCookie
0x180046c6c  call    __security_check_cookie
0x180046c71  lea     r11, [rsp+110h+var_s0]
0x180046c79  mov     rbx, [r11+10h]
0x180046c7d  mov     r14, [r11+18h]
0x180046c81  mov     rsp, r11
0x180046c84  pop     rbp
0x180046c85  retn
```
