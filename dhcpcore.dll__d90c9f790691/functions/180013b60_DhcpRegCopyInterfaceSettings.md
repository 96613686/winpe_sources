# DhcpRegCopyInterfaceSettings

- ea: `0x180013b60`
- end: `0x180013e67`
- name: `DhcpRegCopyInterfaceSettings`
- size: `775`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180013398`
- `0x1800368d0`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x180013b60`
- `0x180013e70`
- `0x18001cef0`
- `0x18001d826`
- `0x18003611c`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d310`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013dc2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013dc2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013d18`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013d18`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013c59`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013c59`

## pseudocode

```c
__int64 __fastcall DhcpRegCopyInterfaceSettings(HKEY hKey, HKEY a2)
{
  void *v4; // rdi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  DWORD i; // esi
  LSTATUS v9; // eax
  int v10; // edx
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v17; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[104]; // [rsp+80h] [rbp-80h] BYREF

  cValues = 0;
  memset_0(ValueName, 0, 0xC8u);
  cchValueName = 0;
  v4 = 0;
  v17 = 0;
  cbMaxValueLen = 0;
  cbData = 0;
  Type = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 69, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  v5 = DhcpRegDeleteInterfaceSettings(a2);
  v6 = v5;
  if ( v5 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_36;
    v7 = 70;
    goto LABEL_6;
  }
  v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, &cbMaxValueLen, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      v7 = 71;
LABEL_6:
      WPP_SF_D(1025, v7, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v5);
    }
  }
  else
  {
    if ( cValues && cbMaxValueLen )
    {
      v17 = DhcpAlloc(cbMaxValueLen);
      v4 = v17;
      if ( v17 )
      {
        for ( i = 0; ; ++i )
        {
          v6 = 0;
          if ( i >= cValues )
            goto LABEL_34;
          cchValueName = 100;
          memset_0(ValueName, 0, 0xC8u);
          cbData = cbMaxValueLen;
          memset_0(v4, 0, cbMaxValueLen);
          while ( 1 )
          {
            v9 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, (LPBYTE)v4, &cbData);
            if ( v9 != 234 )
              break;
            if ( v6 >= 2 )
              goto LABEL_24;
            if ( (xmmword_1800616A0 & 0x10) != 0 )
              WPP_SF_Dd(1028, 73, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, cbMaxValueLen, cbData);
            cbMaxValueLen = cbData;
            DhcpPunycodeFree(&v17);
            v17 = DhcpAlloc(cbMaxValueLen);
            v4 = v17;
            if ( !v17 )
              goto LABEL_13;
            ++v6;
          }
          if ( v9 )
            break;
          if ( !(unsigned int)DhcpIgnoreInterfaceRegSetting((char *)ValueName) )
          {
            v9 = RegSetValueExW(a2, ValueName, 0, Type, (const BYTE *)v4, cbData);
            if ( v9 )
            {
              if ( (xmmword_1800616A0 & 2) != 0 )
              {
                v10 = 75;
LABEL_30:
                WPP_SF_SD(
                  1025,
                  v10,
                  (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids,
                  (unsigned int)ValueName,
                  v9);
                continue;
              }
            }
          }
LABEL_31:
          ;
        }
LABEL_24:
        if ( (xmmword_1800616A0 & 2) == 0 )
          goto LABEL_31;
        v10 = 74;
        goto LABEL_30;
      }
LABEL_13:
      v6 = 8;
    }
    else
    {
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        return v6;
      WPP_SF_(1028, 72, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    }
LABEL_34:
    if ( v4 )
      DhcpPunycodeFree(&v17);
  }
LABEL_36:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 76, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180013b60  mov     [rsp-8+arg_10], rbx
0x180013b65  push    rbp
0x180013b66  push    rsi
0x180013b67  push    rdi
0x180013b68  push    r12
0x180013b6a  push    r13
0x180013b6c  push    r14
0x180013b6e  push    r15
0x180013b70  lea     rbp, [rsp-60h]
0x180013b75  sub     rsp, 160h
0x180013b7c  mov     rax, cs:__security_cookie
0x180013b83  xor     rax, rsp
0x180013b86  mov     [rbp+90h+var_40], rax
0x180013b8a  mov     r15, rdx
0x180013b8d  mov     r14, rcx
0x180013b90  xor     r12d, r12d
0x180013b93  lea     rcx, [rbp+90h+ValueName]; void *
0x180013b97  xor     edx, edx; Val
0x180013b99  mov     [rsp+190h+cValues], r12d
0x180013b9e  mov     r8d, 0C8h; Size
0x180013ba4  call    memset_0
0x180013ba9  mov     [rsp+190h+cchValueName], r12d
0x180013bae  mov     edi, r12d
0x180013bb1  mov     [rsp+190h+var_118], r12
0x180013bb6  mov     [rsp+190h+cbMaxValueLen], r12d
0x180013bbb  mov     [rsp+190h+cbData], r12d
0x180013bc0  mov     [rsp+190h+Type], r12d
0x180013bc5  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013bcc  lea     r13, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013bd3  jz      short loc_180013BE7
0x180013bd5  lea     edx, [r12+45h]
0x180013bda  mov     ecx, 404h
0x180013bdf  mov     r8, r13
0x180013be2  call    WPP_SF_
0x180013be7  mov     rcx, r15; hKey
0x180013bea  call    DhcpRegDeleteInterfaceSettings
0x180013bef  mov     ebx, eax
0x180013bf1  test    eax, eax
0x180013bf3  jz      short loc_180013C1C
0x180013bf5  test    byte ptr cs:xmmword_1800616A0, 2
0x180013bfc  jz      loc_180013E20
0x180013c02  mov     edx, 46h ; 'F'
0x180013c07  mov     ecx, 401h
0x180013c0c  mov     r9d, eax
0x180013c0f  mov     r8, r13
0x180013c12  call    WPP_SF_D
0x180013c17  jmp     loc_180013E20
0x180013c1c  mov     [rsp+190h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180013c21  lea     rax, [rsp+190h+cbMaxValueLen]
0x180013c26  mov     [rsp+190h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180013c2b  xor     r9d, r9d; lpReserved
0x180013c2e  mov     [rsp+190h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180013c33  xor     r8d, r8d; lpcchClass
0x180013c36  mov     [rsp+190h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180013c3b  lea     rax, [rsp+190h+cValues]
0x180013c40  mov     [rsp+190h+lpcValues], rax; lpcValues
0x180013c45  xor     edx, edx; lpClass
0x180013c47  mov     [rsp+190h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180013c4c  mov     rcx, r14; hKey
0x180013c4f  mov     [rsp+190h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180013c54  mov     [rsp+190h+lpcSubKeys], r12; lpcSubKeys
0x180013c59  call    cs:__imp_RegQueryInfoKeyW
0x180013c5f  mov     ebx, eax
0x180013c61  test    eax, eax
0x180013c63  jz      short loc_180013C79
0x180013c65  test    byte ptr cs:xmmword_1800616A0, 2
0x180013c6c  jz      loc_180013E20
0x180013c72  mov     edx, 47h ; 'G'
0x180013c77  jmp     short loc_180013C07
0x180013c79  cmp     [rsp+190h+cValues], r12d
0x180013c7e  jz      loc_180013DF6
0x180013c84  mov     eax, [rsp+190h+cbMaxValueLen]
0x180013c88  test    eax, eax
0x180013c8a  jz      loc_180013DF6
0x180013c90  mov     ecx, eax
0x180013c92  call    DhcpAlloc
0x180013c97  mov     [rsp+190h+var_118], rax
0x180013c9c  mov     rdi, rax
0x180013c9f  test    rax, rax
0x180013ca2  jnz     short loc_180013CAE
0x180013ca4  mov     ebx, 8
0x180013ca9  jmp     loc_180013E11
0x180013cae  mov     esi, r12d
0x180013cb1  mov     ebx, r12d
0x180013cb4  cmp     esi, [rsp+190h+cValues]
0x180013cb8  jnb     loc_180013E11
0x180013cbe  xor     edx, edx; Val
0x180013cc0  mov     [rsp+190h+cchValueName], 64h ; 'd'
0x180013cc8  mov     r8d, 0C8h; Size
0x180013cce  lea     rcx, [rbp+90h+ValueName]; void *
0x180013cd2  call    memset_0
0x180013cd7  mov     eax, [rsp+190h+cbMaxValueLen]
0x180013cdb  xor     edx, edx; Val
0x180013cdd  mov     r8d, eax; Size
0x180013ce0  mov     [rsp+190h+cbData], eax
0x180013ce4  mov     rcx, rdi; void *
0x180013ce7  call    memset_0
0x180013cec  lea     rax, [rsp+190h+cbData]
0x180013cf1  mov     edx, esi; dwIndex
0x180013cf3  mov     [rsp+190h+lpcValues], rax; lpcbData
0x180013cf8  lea     r9, [rsp+190h+cchValueName]; lpcchValueName
0x180013cfd  lea     rax, [rsp+190h+Type]
0x180013d02  mov     [rsp+190h+lpcbMaxClassLen], rdi; lpData
0x180013d07  mov     [rsp+190h+lpcbMaxSubKeyLen], rax; lpType
0x180013d0c  lea     r8, [rbp+90h+ValueName]; lpValueName
0x180013d10  mov     rcx, r14; hKey
0x180013d13  mov     [rsp+190h+lpcSubKeys], r12; lpReserved
0x180013d18  call    cs:__imp_RegEnumValueW
0x180013d1e  cmp     eax, 0EAh
0x180013d23  jnz     short loc_180013D85
0x180013d25  cmp     ebx, 2
0x180013d28  jnb     short loc_180013D89
0x180013d2a  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013d31  jz      short loc_180013D52
0x180013d33  mov     eax, [rsp+190h+cbData]
0x180013d37  mov     edx, 49h ; 'I'
0x180013d3c  mov     r9d, [rsp+190h+cbMaxValueLen]
0x180013d41  mov     ecx, 404h
0x180013d46  mov     r8, r13
0x180013d49  mov     dword ptr [rsp+190h+lpcSubKeys], eax
0x180013d4d  call    WPP_SF_Dd
0x180013d52  mov     eax, [rsp+190h+cbData]
0x180013d56  lea     rcx, [rsp+190h+var_118]
0x180013d5b  mov     [rsp+190h+cbMaxValueLen], eax
0x180013d5f  call    DhcpPunycodeFree
0x180013d64  mov     ecx, [rsp+190h+cbMaxValueLen]
0x180013d68  call    DhcpAlloc
0x180013d6d  mov     [rsp+190h+var_118], rax
0x180013d72  mov     rdi, rax
0x180013d75  test    rax, rax
0x180013d78  jz      loc_180013CA4
0x180013d7e  inc     ebx
0x180013d80  jmp     loc_180013CEC
0x180013d85  test    eax, eax
0x180013d87  jz      short loc_180013D99
0x180013d89  test    byte ptr cs:xmmword_1800616A0, 2
0x180013d90  jz      short loc_180013DEF
0x180013d92  mov     edx, 4Ah ; 'J'
0x180013d97  jmp     short loc_180013DDA
0x180013d99  lea     rcx, [rbp+90h+ValueName]
0x180013d9d  call    DhcpIgnoreInterfaceRegSetting
0x180013da2  test    eax, eax
0x180013da4  jnz     short loc_180013DEF
0x180013da6  mov     eax, [rsp+190h+cbData]
0x180013daa  lea     rdx, [rbp+90h+ValueName]; lpValueName
0x180013dae  mov     r9d, [rsp+190h+Type]; dwType
0x180013db3  xor     r8d, r8d; Reserved
0x180013db6  mov     dword ptr [rsp+190h+lpcbMaxSubKeyLen], eax; cbData
0x180013dba  mov     rcx, r15; hKey
0x180013dbd  mov     [rsp+190h+lpcSubKeys], rdi; lpData
0x180013dc2  call    cs:__imp_RegSetValueExW
0x180013dc8  test    eax, eax
0x180013dca  jz      short loc_180013DEF
0x180013dcc  test    byte ptr cs:xmmword_1800616A0, 2
0x180013dd3  jz      short loc_180013DEF
0x180013dd5  mov     edx, 4Bh ; 'K'
0x180013dda  lea     r9, [rbp+90h+ValueName]
0x180013dde  mov     dword ptr [rsp+190h+lpcSubKeys], eax
0x180013de2  mov     r8, r13
0x180013de5  mov     ecx, 401h
0x180013dea  call    WPP_SF_SD
0x180013def  inc     esi
0x180013df1  jmp     loc_180013CB1
0x180013df6  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013dfd  jz      short loc_180013E3E
0x180013dff  mov     edx, 48h ; 'H'
0x180013e04  mov     ecx, 404h
0x180013e09  mov     r8, r13
0x180013e0c  call    WPP_SF_
0x180013e11  test    rdi, rdi
0x180013e14  jz      short loc_180013E20
0x180013e16  lea     rcx, [rsp+190h+var_118]
0x180013e1b  call    DhcpPunycodeFree
0x180013e20  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013e27  jz      short loc_180013E3E
0x180013e29  mov     edx, 4Ch ; 'L'
0x180013e2e  mov     ecx, 404h
0x180013e33  mov     r9d, ebx
0x180013e36  mov     r8, r13
0x180013e39  call    WPP_SF_D
0x180013e3e  mov     eax, ebx
0x180013e40  mov     rcx, [rbp+90h+var_40]
0x180013e44  xor     rcx, rsp; StackCookie
0x180013e47  call    __security_check_cookie
0x180013e4c  mov     rbx, [rsp+190h+arg_10]
0x180013e54  add     rsp, 160h
0x180013e5b  pop     r15
0x180013e5d  pop     r14
0x180013e5f  pop     r13
0x180013e61  pop     r12
0x180013e63  pop     rdi
0x180013e64  pop     rsi
0x180013e65  pop     rbp
0x180013e66  retn
```
