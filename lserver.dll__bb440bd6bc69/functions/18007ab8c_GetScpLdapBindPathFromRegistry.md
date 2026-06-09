# GetScpLdapBindPathFromRegistry

- ea: `0x18007ab8c`
- end: `0x18007add0`
- name: `GetScpLdapBindPathFromRegistry`
- size: `580`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18007a960`
- `0x18007c4cc`

## callees

- `0x180005665`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18007aaf8`
- `0x18007ab8c`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18007ac65`
- `ADVAPI32!RegQueryValueExW` at `0x18007ad3b`
- `ADVAPI32!RegQueryValueExW` at `0x18007ac65`
- `ADVAPI32!RegQueryValueExW` at `0x18007ad3b`
- `ADVAPI32!RegOpenKeyExW` at `0x18007abf2`
- `ADVAPI32!RegOpenKeyExW` at `0x18007abf2`
- `ADVAPI32!RegCloseKey` at `0x18007ad9d`
- `ADVAPI32!RegCloseKey` at `0x18007ad9d`
- `KERNEL32!LocalAlloc` at `0x18007acb5`
- `KERNEL32!LocalAlloc` at `0x18007acb5`

## string_xrefs

- `0x18007ac37`: `"RegOpenKeyEx"`

## pseudocode

```c
__int64 __fastcall GetScpLdapBindPathFromRegistry(__int64 a1, LPBYTE *a2)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  const wchar_t *v7; // r9
  LSTATUS v8; // eax
  BYTE *v9; // rax
  LSTATUS v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[1024]; // [rsp+40h] [rbp-C0h] BYREF

  *a2 = 0;
  hKey = 0;
  cbData = 0;
  GetScpGUIDRegistryKeyPath(a1, SubKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 84;
      v7 = L"\"RegOpenKeyEx\"";
LABEL_25:
      WPP_SF_SD(v5[2], v6, (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (_DWORD)v7, v4);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v8 = RegQueryValueExW(hKey, L"GUIDBindingString", 0, 0, 0, &cbData);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_26;
    v6 = 85;
LABEL_24:
    v7 = L"\"RegQueryValueEx\"";
    goto LABEL_25;
  }
  v9 = (BYTE *)LocalAlloc(0, cbData);
  *a2 = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        L"_T(\"LocalAlloc\")");
    v4 = -2147024882;
    goto LABEL_26;
  }
  memset_0(v9, 0, cbData);
  v10 = RegQueryValueExW(hKey, L"GUIDBindingString", 0, 0, *a2, &cbData);
  v4 = v10;
  if ( v10 > 0 )
    v4 = (unsigned __int16)v10 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 87;
      goto LABEL_24;
    }
  }
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007ab8c  mov     [rsp-8+arg_10], rbx
0x18007ab91  mov     [rsp-8+arg_18], rdi
0x18007ab96  push    rbp
0x18007ab97  lea     rbp, [rsp-750h]
0x18007ab9f  sub     rsp, 850h
0x18007aba6  mov     rax, cs:__security_cookie
0x18007abad  xor     rax, rsp
0x18007abb0  mov     [rbp+750h+var_10], rax
0x18007abb7  and     qword ptr [rdx], 0
0x18007abbb  mov     rdi, rdx
0x18007abbe  and     [rsp+850h+hKey], 0
0x18007abc4  lea     rdx, [rsp+850h+SubKey]
0x18007abc9  and     [rsp+850h+cbData], 0
0x18007abce  call    GetScpGUIDRegistryKeyPath
0x18007abd3  lea     rax, [rsp+850h+hKey]
0x18007abd8  mov     r9d, 20019h; samDesired
0x18007abde  xor     r8d, r8d; ulOptions
0x18007abe1  mov     [rsp+850h+phkResult], rax; lpData
0x18007abe6  lea     rdx, [rsp+850h+SubKey]; lpSubKey
0x18007abeb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007abf2  call    cs:__imp_RegOpenKeyExW
0x18007abf9  nop     dword ptr [rax+rax+00h]
0x18007abfe  mov     ebx, eax
0x18007ac00  test    eax, eax
0x18007ac02  jle     short loc_18007AC0D
0x18007ac04  movzx   ebx, ax
0x18007ac07  or      ebx, 80070000h
0x18007ac0d  test    ebx, ebx
0x18007ac0f  jns     short loc_18007AC43
0x18007ac11  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac18  lea     rax, WPP_GLOBAL_Control
0x18007ac1f  cmp     rcx, rax
0x18007ac22  jz      loc_18007AD93
0x18007ac28  cmp     byte ptr [rcx+19h], 2
0x18007ac2c  jb      loc_18007AD93
0x18007ac32  mov     edx, 54h ; 'T'
0x18007ac37  lea     r9, aRegopenkeyex; "\"RegOpenKeyEx\""
0x18007ac3e  jmp     loc_18007AD7F
0x18007ac43  mov     rcx, [rsp+850h+hKey]; hKey
0x18007ac48  lea     rax, [rsp+850h+cbData]
0x18007ac4d  mov     [rsp+850h+lpcbData], rax; lpcbData
0x18007ac52  lea     rdx, aGuidbindingstr; "GUIDBindingString"
0x18007ac59  and     [rsp+850h+phkResult], 0
0x18007ac5f  xor     r9d, r9d; lpType
0x18007ac62  xor     r8d, r8d; lpReserved
0x18007ac65  call    cs:__imp_RegQueryValueExW
0x18007ac6c  nop     dword ptr [rax+rax+00h]
0x18007ac71  mov     ebx, eax
0x18007ac73  test    eax, eax
0x18007ac75  jle     short loc_18007AC80
0x18007ac77  movzx   ebx, ax
0x18007ac7a  or      ebx, 80070000h
0x18007ac80  test    ebx, ebx
0x18007ac82  jns     short loc_18007ACAF
0x18007ac84  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac8b  lea     rax, WPP_GLOBAL_Control
0x18007ac92  cmp     rcx, rax
0x18007ac95  jz      loc_18007AD93
0x18007ac9b  cmp     byte ptr [rcx+19h], 2
0x18007ac9f  jb      loc_18007AD93
0x18007aca5  mov     edx, 55h ; 'U'
0x18007acaa  jmp     loc_18007AD78
0x18007acaf  mov     edx, [rsp+850h+cbData]; uBytes
0x18007acb3  xor     ecx, ecx; uFlags
0x18007acb5  call    cs:__imp_LocalAlloc
0x18007acbc  nop     dword ptr [rax+rax+00h]
0x18007acc1  mov     [rdi], rax
0x18007acc4  test    rax, rax
0x18007acc7  jnz     short loc_18007AD08
0x18007acc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007acd0  lea     rax, WPP_GLOBAL_Control
0x18007acd7  cmp     rcx, rax
0x18007acda  jz      short loc_18007ACFE
0x18007acdc  cmp     byte ptr [rcx+19h], 2
0x18007ace0  jb      short loc_18007ACFE
0x18007ace2  mov     rcx, [rcx+10h]
0x18007ace6  lea     r9, aTLocalalloc; "_T(\"LocalAlloc\")"
0x18007aced  mov     edx, 56h ; 'V'
0x18007acf2  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007acf9  call    WPP_SF_S
0x18007acfe  mov     ebx, 8007000Eh
0x18007ad03  jmp     loc_18007AD93
0x18007ad08  mov     r8d, [rsp+850h+cbData]; Size
0x18007ad0d  xor     edx, edx; Val
0x18007ad0f  mov     rcx, rax; void *
0x18007ad12  call    memset_0
0x18007ad17  mov     rcx, [rsp+850h+hKey]; hKey
0x18007ad1c  lea     rax, [rsp+850h+cbData]
0x18007ad21  mov     [rsp+850h+lpcbData], rax; lpcbData
0x18007ad26  lea     rdx, aGuidbindingstr; "GUIDBindingString"
0x18007ad2d  mov     rax, [rdi]
0x18007ad30  xor     r9d, r9d; lpType
0x18007ad33  xor     r8d, r8d; lpReserved
0x18007ad36  mov     [rsp+850h+phkResult], rax; lpData
0x18007ad3b  call    cs:__imp_RegQueryValueExW
0x18007ad42  nop     dword ptr [rax+rax+00h]
0x18007ad47  mov     ebx, eax
0x18007ad49  test    eax, eax
0x18007ad4b  jle     short loc_18007AD56
0x18007ad4d  movzx   ebx, ax
0x18007ad50  or      ebx, 80070000h
0x18007ad56  test    ebx, ebx
0x18007ad58  jns     short loc_18007AD93
0x18007ad5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad61  lea     rax, WPP_GLOBAL_Control
0x18007ad68  cmp     rcx, rax
0x18007ad6b  jz      short loc_18007AD93
0x18007ad6d  cmp     byte ptr [rcx+19h], 2
0x18007ad71  jb      short loc_18007AD93
0x18007ad73  mov     edx, 57h ; 'W'
0x18007ad78  lea     r9, aRegqueryvaluee_0; "\"RegQueryValueEx\""
0x18007ad7f  mov     rcx, [rcx+10h]
0x18007ad83  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007ad8a  mov     dword ptr [rsp+850h+phkResult], ebx
0x18007ad8e  call    WPP_SF_SD
0x18007ad93  mov     rcx, [rsp+850h+hKey]; hKey
0x18007ad98  test    rcx, rcx
0x18007ad9b  jz      short loc_18007ADA9
0x18007ad9d  call    cs:__imp_RegCloseKey
0x18007ada4  nop     dword ptr [rax+rax+00h]
0x18007ada9  mov     eax, ebx
0x18007adab  mov     rcx, [rbp+750h+var_10]
0x18007adb2  xor     rcx, rsp; StackCookie
0x18007adb5  call    __security_check_cookie
0x18007adba  lea     r11, [rsp+850h+var_s0]
0x18007adc2  mov     rbx, [r11+20h]
0x18007adc6  mov     rdi, [r11+28h]
0x18007adca  mov     rsp, r11
0x18007adcd  pop     rbp
0x18007adce  retn
```
