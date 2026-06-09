# IsIcsDnsEnabled(void)

- ea: `0x18000ea20`
- end: `0x18000ec22`
- name: `?IsIcsDnsEnabled@@YAHXZ`
- size: `514`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180028924`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000ea20`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ebcd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ebcd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eb23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eb23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb37`

## string_xrefs

- `0x18000ea67`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
_BOOL8 IsIcsDnsEnabled(void)
{
  BOOL v0; // ebx
  PVOID *v1; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C0h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-B8h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-98h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
  }
  v0 = 0;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  hKey = 0;
  wcscpy(ValueName, L"IcsDEnabled");
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids);
      v1 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x10) != 0 && *((_BYTE *)v1 + 25) >= 4u )
      WPP_SF_d(v1[2], 14, &WPP_9be8243bb99535625437fc4fc0071459_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x18000ea20  mov     [rsp+arg_0], rbx
0x18000ea25  mov     [rsp+arg_8], rsi
0x18000ea2a  push    rdi
0x18000ea2b  sub     rsp, 0F0h
0x18000ea32  mov     rax, cs:__security_cookie
0x18000ea39  xor     rax, rsp
0x18000ea3c  mov     [rsp+0F8h+var_18], rax
0x18000ea44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea4b  lea     rdi, WPP_GLOBAL_Control
0x18000ea52  cmp     rcx, rdi
0x18000ea55  jz      short loc_18000EA67
0x18000ea57  test    byte ptr [rcx+1Ch], 10h
0x18000ea5b  jz      short loc_18000EA67
0x18000ea5d  cmp     byte ptr [rcx+19h], 6
0x18000ea61  jnb     loc_18000EBE7
0x18000ea67  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18000ea6e  lea     rdx, [rsp+0F8h+SubKey]; lpSubKey
0x18000ea73  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18000ea7a  xor     ebx, ebx
0x18000ea7c  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18000ea82  mov     esi, 1
0x18000ea87  movaps  xmmword ptr [rsp+0F8h+SubKey], xmm0
0x18000ea8c  mov     r9d, esi; samDesired
0x18000ea8f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18000ea96  xor     r8d, r8d; ulOptions
0x18000ea99  movaps  [rsp+0F8h+var_78], xmm0
0x18000eaa1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eaa8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18000eaaf  movaps  [rsp+0F8h+var_88], xmm1
0x18000eab4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x18000eabb  movaps  [rsp+0F8h+var_58], xmm0
0x18000eac3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18000eaca  movaps  [rsp+0F8h+var_68], xmm1
0x18000ead2  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18000ead9  movaps  [rsp+0F8h+var_38], xmm0
0x18000eae1  movups  xmm0, xmmword ptr cs:aIcsdnsenabled; "IcsDnsEnabled"
0x18000eae8  mov     [rsp+0F8h+var_28], eax
0x18000eaef  lea     rax, [rsp+0F8h+hKey]
0x18000eaf4  movaps  [rsp+0F8h+var_48], xmm1
0x18000eafc  movups  xmm1, xmmword ptr cs:aIcsdnsenabled+0Ch; "Enabled"
0x18000eb03  mov     [rsp+0F8h+hKey], rbx
0x18000eb08  movups  xmmword ptr [rsp+0F8h+ValueName], xmm0
0x18000eb0d  mov     [rsp+0F8h+cbData], 4
0x18000eb15  movups  xmmword ptr [rsp+0F8h+ValueName+0Ch], xmm1
0x18000eb1a  mov     dword ptr [rsp+0F8h+Data], ebx
0x18000eb1e  mov     [rsp+0F8h+phkResult], rax; phkResult
0x18000eb23  call    cs:__imp_RegOpenKeyExW
0x18000eb29  test    eax, eax
0x18000eb2b  jz      short loc_18000EBA9
0x18000eb2d  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18000eb32  test    rcx, rcx
0x18000eb35  jz      short loc_18000EB3D
0x18000eb37  call    cs:__imp_RegCloseKey
0x18000eb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb44  cmp     rcx, rdi
0x18000eb47  jz      short loc_18000EB82
0x18000eb49  test    byte ptr [rcx+1Ch], 10h
0x18000eb4d  jz      short loc_18000EB59
0x18000eb4f  cmp     byte ptr [rcx+19h], 6
0x18000eb53  jnb     loc_18000EC01
0x18000eb59  cmp     rcx, rdi
0x18000eb5c  jz      short loc_18000EB82
0x18000eb5e  test    byte ptr [rcx+1Ch], 10h
0x18000eb62  jz      short loc_18000EB82
0x18000eb64  cmp     byte ptr [rcx+19h], 4
0x18000eb68  jb      short loc_18000EB82
0x18000eb6a  mov     rcx, [rcx+10h]
0x18000eb6e  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000eb75  mov     edx, 0Eh
0x18000eb7a  mov     r9d, ebx
0x18000eb7d  call    WPP_SF_d
0x18000eb82  mov     eax, ebx
0x18000eb84  mov     rcx, [rsp+0F8h+var_18]
0x18000eb8c  xor     rcx, rsp; StackCookie
0x18000eb8f  call    __security_check_cookie
0x18000eb94  lea     r11, [rsp+0F8h+var_8]
0x18000eb9c  mov     rbx, [r11+10h]
0x18000eba0  mov     rsi, [r11+18h]
0x18000eba4  mov     rsp, r11
0x18000eba7  pop     rdi
0x18000eba8  retn
0x18000eba9  mov     rcx, [rsp+0F8h+hKey]; hKey
0x18000ebae  lea     rax, [rsp+0F8h+cbData]
0x18000ebb3  mov     [rsp+0F8h+lpcbData], rax; lpcbData
0x18000ebb8  lea     rdx, [rsp+0F8h+ValueName]; lpValueName
0x18000ebbd  lea     rax, [rsp+0F8h+Data]
0x18000ebc2  xor     r9d, r9d; lpType
0x18000ebc5  xor     r8d, r8d; lpReserved
0x18000ebc8  mov     [rsp+0F8h+phkResult], rax; lpData
0x18000ebcd  call    cs:__imp_RegQueryValueExW
0x18000ebd3  test    eax, eax
0x18000ebd5  jnz     loc_18000EB2D
0x18000ebdb  cmp     dword ptr [rsp+0F8h+Data], ebx
0x18000ebdf  cmovnz  ebx, esi
0x18000ebe2  jmp     loc_18000EB2D
0x18000ebe7  mov     rcx, [rcx+10h]
0x18000ebeb  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000ebf2  mov     edx, 0Ch
0x18000ebf7  call    WPP_SF_
0x18000ebfc  jmp     loc_18000EA67
0x18000ec01  mov     rcx, [rcx+10h]
0x18000ec05  lea     r8, WPP_9be8243bb99535625437fc4fc0071459_Traceguids
0x18000ec0c  mov     edx, 0Dh
0x18000ec11  call    WPP_SF_
0x18000ec16  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1d  jmp     loc_18000EB59
```
