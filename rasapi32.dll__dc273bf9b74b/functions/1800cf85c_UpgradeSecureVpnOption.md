# UpgradeSecureVpnOption

- ea: `0x1800cf85c`
- end: `0x1800cfa1d`
- name: `UpgradeSecureVpnOption`
- size: `449`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800cf698`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800cf85c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cf9c4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cf9c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf914`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf9dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf9dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cf97e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800cf97e`

## string_xrefs

- `0x1800cf90a`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeSecureVpnOption(HKEY hKey, __int64 a2)
{
  char *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 864, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = (char *)WPP_GLOBAL_Control;
  }
  hKeya = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !a2 )
  {
    v5 = 87;
    if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 6u )
    {
      v6 = 865;
LABEL_31:
      WPP_SF_d(*((_QWORD *)v4 + 2), v6, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKeya);
  v5 = v7;
  if ( v7 )
  {
    v4 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 866;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v4 + 2), v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
LABEL_24:
      v4 = (char *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v7 = RegQueryValueExW(hKeya, L"SecureVPN", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v7;
    if ( !v7 )
    {
      if ( Data )
        *(_DWORD *)(a2 + 164) = 512;
      RegDeleteValueW(hKeya, L"SecureVPN");
      goto LABEL_24;
    }
    v4 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 867;
      goto LABEL_15;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v4 = (char *)WPP_GLOBAL_Control;
  }
  if ( v4 != (char *)&WPP_GLOBAL_Control && v4[28] < 0 && (unsigned __int8)v4[25] >= 6u )
  {
    v6 = 868;
    goto LABEL_31;
  }
  return v5;
}

```

## disassembly

```asm
0x1800cf85c  push    rbp
0x1800cf85e  push    rbx
0x1800cf85f  push    rdi
0x1800cf860  push    r12
0x1800cf862  push    r15
0x1800cf864  mov     rbp, rsp
0x1800cf867  sub     rsp, 40h
0x1800cf86b  mov     rdi, rdx
0x1800cf86e  mov     rbx, rcx
0x1800cf871  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf878  lea     r15, WPP_GLOBAL_Control
0x1800cf87f  lea     r12, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cf886  cmp     rcx, r15
0x1800cf889  jz      short loc_1800CF8AF
0x1800cf88b  test    byte ptr [rcx+1Ch], 80h
0x1800cf88f  jz      short loc_1800CF8AF
0x1800cf891  cmp     byte ptr [rcx+19h], 6
0x1800cf895  jb      short loc_1800CF8AF
0x1800cf897  mov     rcx, [rcx+10h]
0x1800cf89b  mov     edx, 360h
0x1800cf8a0  mov     r8, r12
0x1800cf8a3  call    WPP_SF_
0x1800cf8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf8af  mov     [rbp+hKey], 0
0x1800cf8b7  mov     eax, 4
0x1800cf8bc  mov     [rbp+Type], eax
0x1800cf8bf  mov     [rbp+cbData], eax
0x1800cf8c2  mov     [rbp+Data], 0
0x1800cf8c9  test    rdi, rdi
0x1800cf8cc  jnz     short loc_1800CF8F8
0x1800cf8ce  lea     ebx, [rax+53h]
0x1800cf8d1  cmp     rcx, r15
0x1800cf8d4  jz      loc_1800CFA0F
0x1800cf8da  test    byte ptr [rcx+1Ch], 80h
0x1800cf8de  jz      loc_1800CFA0F
0x1800cf8e4  cmp     byte ptr [rcx+19h], 6
0x1800cf8e8  jb      loc_1800CFA0F
0x1800cf8ee  mov     edx, 361h
0x1800cf8f3  jmp     loc_1800CFA00
0x1800cf8f8  lea     rax, [rbp+hKey]
0x1800cf8fc  mov     r9d, 20019h; samDesired
0x1800cf902  xor     r8d, r8d; ulOptions
0x1800cf905  mov     [rsp+40h+phkResult], rax; phkResult
0x1800cf90a  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x1800cf911  mov     rcx, rbx; hKey
0x1800cf914  call    cs:__imp_RegOpenKeyExW
0x1800cf91a  mov     ebx, eax
0x1800cf91c  test    eax, eax
0x1800cf91e  jz      short loc_1800CF95A
0x1800cf920  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf927  cmp     rcx, r15
0x1800cf92a  jz      loc_1800CF9D1
0x1800cf930  test    byte ptr [rcx+1Ch], 80h
0x1800cf934  jz      loc_1800CF9D1
0x1800cf93a  cmp     byte ptr [rcx+19h], 2
0x1800cf93e  jb      loc_1800CF9D1
0x1800cf944  mov     edx, 362h
0x1800cf949  mov     rcx, [rcx+10h]
0x1800cf94d  mov     r9d, eax
0x1800cf950  mov     r8, r12
0x1800cf953  call    WPP_SF_d
0x1800cf958  jmp     short loc_1800CF9CA
0x1800cf95a  mov     rcx, [rbp+hKey]; hKey
0x1800cf95e  lea     rax, [rbp+cbData]
0x1800cf962  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800cf967  lea     r9, [rbp+Type]; lpType
0x1800cf96b  lea     rax, [rbp+Data]
0x1800cf96f  xor     r8d, r8d; lpReserved
0x1800cf972  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x1800cf979  mov     [rsp+40h+phkResult], rax; lpData
0x1800cf97e  call    cs:__imp_RegQueryValueExW
0x1800cf984  mov     ebx, eax
0x1800cf986  test    eax, eax
0x1800cf988  jz      short loc_1800CF9A9
0x1800cf98a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf991  cmp     rcx, r15
0x1800cf994  jz      short loc_1800CF9D1
0x1800cf996  test    byte ptr [rcx+1Ch], 80h
0x1800cf99a  jz      short loc_1800CF9D1
0x1800cf99c  cmp     byte ptr [rcx+19h], 2
0x1800cf9a0  jb      short loc_1800CF9D1
0x1800cf9a2  mov     edx, 363h
0x1800cf9a7  jmp     short loc_1800CF949
0x1800cf9a9  cmp     [rbp+Data], 0
0x1800cf9ad  jz      short loc_1800CF9B9
0x1800cf9af  mov     dword ptr [rdi+0A4h], 200h
0x1800cf9b9  mov     rcx, [rbp+hKey]; hKey
0x1800cf9bd  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x1800cf9c4  call    cs:__imp_RegDeleteValueW
0x1800cf9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf9d1  mov     rax, [rbp+hKey]
0x1800cf9d5  test    rax, rax
0x1800cf9d8  jz      short loc_1800CF9EA
0x1800cf9da  mov     rcx, rax; hKey
0x1800cf9dd  call    cs:__imp_RegCloseKey
0x1800cf9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf9ea  cmp     rcx, r15
0x1800cf9ed  jz      short loc_1800CFA0F
0x1800cf9ef  test    byte ptr [rcx+1Ch], 80h
0x1800cf9f3  jz      short loc_1800CFA0F
0x1800cf9f5  cmp     byte ptr [rcx+19h], 6
0x1800cf9f9  jb      short loc_1800CFA0F
0x1800cf9fb  mov     edx, 364h
0x1800cfa00  mov     rcx, [rcx+10h]
0x1800cfa04  mov     r9d, ebx
0x1800cfa07  mov     r8, r12
0x1800cfa0a  call    WPP_SF_d
0x1800cfa0f  mov     eax, ebx
0x1800cfa11  add     rsp, 40h
0x1800cfa15  pop     r15
0x1800cfa17  pop     r12
0x1800cfa19  pop     rdi
0x1800cfa1a  pop     rbx
0x1800cfa1b  pop     rbp
0x1800cfa1c  retn
```
