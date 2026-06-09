# V2IsDhcpSendUnicastMessagesEnabled(void)

- ea: `0x180041c40`
- end: `0x180041e15`
- name: `?V2IsDhcpSendUnicastMessagesEnabled@@YAHXZ`
- size: `469`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180002030`

## callees

- `0x18000c110`
- `0x180041c40`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041da7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041d58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041dbf`

## string_xrefs

- `0x180041c99`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

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
0x180041c40  mov     [rsp-8+arg_0], rbx
0x180041c45  mov     [rsp-8+arg_8], r14
0x180041c4a  push    rbp
0x180041c4b  lea     rbp, [rsp-10h]
0x180041c50  sub     rsp, 110h
0x180041c57  mov     rax, cs:__security_cookie
0x180041c5e  xor     rax, rsp
0x180041c61  mov     [rbp+10h+var_10], rax
0x180041c65  mov     rcx, cs:WPP_GLOBAL_Control
0x180041c6c  lea     r14, WPP_GLOBAL_Control
0x180041c73  cmp     rcx, r14
0x180041c76  jz      short loc_180041C99
0x180041c78  test    byte ptr [rcx+1Ch], 2
0x180041c7c  jz      short loc_180041C99
0x180041c7e  cmp     byte ptr [rcx+19h], 6
0x180041c82  jb      short loc_180041C99
0x180041c84  mov     rcx, [rcx+10h]
0x180041c88  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180041c8f  mov     edx, 5Ch ; '\'
0x180041c94  call    WPP_SF_
0x180041c99  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180041ca0  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x180041ca4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180041cab  mov     ebx, 1
0x180041cb0  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180041cb6  mov     r9d, ebx; samDesired
0x180041cb9  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x180041cbd  xor     r8d, r8d; ulOptions
0x180041cc0  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180041cc7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041cce  movaps  [rbp+10h+var_70], xmm0
0x180041cd2  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180041cd9  movaps  [rbp+10h+var_80], xmm1
0x180041cdd  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180041ce4  movaps  [rbp+10h+var_50], xmm0
0x180041ce8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180041cef  movaps  [rbp+10h+var_60], xmm1
0x180041cf3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180041cfa  movaps  [rbp+10h+var_30], xmm0
0x180041cfe  movups  xmm0, xmmword ptr cs:aDisablesenduni; "DisableSendUnicastDHCPMessages"
0x180041d05  mov     [rbp+10h+var_20], eax
0x180041d08  lea     rax, [rsp+110h+hKey]
0x180041d0d  movaps  [rbp+10h+var_40], xmm1
0x180041d11  movups  xmm1, xmmword ptr cs:aDisablesenduni+10h; "endUnicastDHCPMessages"
0x180041d18  mov     [rsp+110h+hKey], 0
0x180041d21  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x180041d26  mov     dword ptr [rsp+110h+Data], 0
0x180041d2e  movups  xmm0, xmmword ptr cs:aDisablesenduni+20h; "stDHCPMessages"
0x180041d35  mov     [rsp+110h+cbData], 4
0x180041d3d  movups  [rsp+110h+var_C0], xmm1
0x180041d42  mov     [rsp+110h+phkResult], rax; phkResult
0x180041d47  movups  xmm1, xmmword ptr cs:aDisablesenduni+2Eh; "essages"
0x180041d4e  movups  [rsp+110h+var_B0], xmm0
0x180041d53  movups  [rsp+110h+var_B0+0Eh], xmm1
0x180041d58  call    cs:__imp_RegOpenKeyExW
0x180041d5e  test    eax, eax
0x180041d60  jz      short loc_180041D83
0x180041d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d69  cmp     rcx, r14
0x180041d6c  jz      loc_180041DF2
0x180041d72  test    byte ptr [rcx+1Ch], 2
0x180041d76  jz      short loc_180041DF2
0x180041d78  cmp     byte ptr [rcx+19h], 6
0x180041d7c  jb      short loc_180041DF2
0x180041d7e  lea     edx, [rbx+5Ch]
0x180041d81  jmp     short loc_180041DE2
0x180041d83  mov     rcx, [rsp+110h+hKey]; hKey
0x180041d88  lea     rax, [rsp+110h+cbData]
0x180041d8d  mov     [rsp+110h+lpcbData], rax; lpcbData
0x180041d92  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x180041d97  lea     rax, [rsp+110h+Data]
0x180041d9c  xor     r9d, r9d; lpType
0x180041d9f  xor     r8d, r8d; lpReserved
0x180041da2  mov     [rsp+110h+phkResult], rax; lpData
0x180041da7  call    cs:__imp_RegQueryValueExW
0x180041dad  test    eax, eax
0x180041daf  jnz     short loc_180041DBA
0x180041db1  xor     ebx, ebx
0x180041db3  cmp     dword ptr [rsp+110h+Data], ebx
0x180041db7  setz    bl
0x180041dba  mov     rcx, [rsp+110h+hKey]; hKey
0x180041dbf  call    cs:__imp_RegCloseKey
0x180041dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041dcc  cmp     rcx, r14
0x180041dcf  jz      short loc_180041DF2
0x180041dd1  test    byte ptr [rcx+1Ch], 2
0x180041dd5  jz      short loc_180041DF2
0x180041dd7  cmp     byte ptr [rcx+19h], 6
0x180041ddb  jb      short loc_180041DF2
0x180041ddd  mov     edx, 5Eh ; '^'
0x180041de2  mov     rcx, [rcx+10h]
0x180041de6  lea     r8, WPP_fdaf6c9ffc3a3fb1f1bea20bf18fd4e0_Traceguids
0x180041ded  call    WPP_SF_
0x180041df2  mov     eax, ebx
0x180041df4  mov     rcx, [rbp+10h+var_10]
0x180041df8  xor     rcx, rsp; StackCookie
0x180041dfb  call    __security_check_cookie
0x180041e00  lea     r11, [rsp+110h+var_s0]
0x180041e08  mov     rbx, [r11+10h]
0x180041e0c  mov     r14, [r11+18h]
0x180041e10  mov     rsp, r11
0x180041e13  pop     rbp
0x180041e14  retn
```
