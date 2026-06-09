# DhcpReadSavedConfigurations

- ea: `0x1800079e4`
- end: `0x180007cd1`
- name: `DhcpReadSavedConfigurations`
- size: `749`
- prototype: `__int64 __fastcall(HKEY hKey, _QWORD *, DWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008084`
- `0x1800227ac`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x1800079e4`
- `0x180007f08`
- `0x18001cef0`
- `0x18001d826`
- `0x180047e3c`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b3e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007b14`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007b14`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007a68`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007a68`

## pseudocode

```c
__int64 __fastcall DhcpReadSavedConfigurations(HKEY hKey, _QWORD *a2, DWORD *a3)
{
  __int64 v5; // rax
  unsigned int Configs; // ebx
  char *v9; // rdi
  DWORD i; // esi
  char *v11; // r15
  DWORD j; // r14d
  LPVOID *v13; // rcx
  SIZE_T v14; // rcx
  void *v15; // rax
  __int64 v16; // rdx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  char *v20; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[104]; // [rsp+80h] [rbp-80h] BYREF

  *a2 = 0;
  v5 = *a3;
  cSubKeys = 0;
  cchName = 0;
  phkResult = 0;
  if ( (_DWORD)v5 )
  {
    cSubKeys = v5;
    v20 = (char *)DhcpAlloc(24 * v5);
    v9 = v20;
    if ( v20 )
    {
      Configs = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= cSubKeys )
        {
          *a2 = v9;
          return Configs;
        }
        cchName = 100;
        memset_0(Name, 0, 0xC8u);
        Configs = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( Configs )
        {
          if ( (xmmword_1800616A0 & 0x10) != 0 )
            WPP_SF_d(1028, 81, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, i);
          goto LABEL_11;
        }
        Configs = RegOpenKeyExW(hKey, Name, 0, 0x2001Bu, &phkResult);
        if ( Configs )
          break;
        v11 = &v9[24 * i];
        Configs = ReadConfigs(phkResult);
        RegCloseKey(phkResult);
        if ( Configs )
        {
          if ( (xmmword_1800616A0 & 0x10) == 0 )
            goto LABEL_11;
          v16 = 83;
          goto LABEL_32;
        }
        v14 = 2 * cchName + 2LL;
        cchName *= 2;
        v15 = DhcpAlloc(v14);
        *(_QWORD *)v11 = v15;
        if ( !v15 )
        {
          Configs = 8;
          if ( (xmmword_1800616A0 & 0x10) == 0 )
            goto LABEL_11;
          v16 = 84;
          goto LABEL_32;
        }
        memcpy_0(v15, Name, cchName);
        *(_WORD *)(*(_QWORD *)v11 + 2 * ((unsigned __int64)cchName >> 1)) = 0;
      }
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v16 = 82;
LABEL_32:
        WPP_SF_(1028, v16, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      }
LABEL_11:
      for ( j = 0; j < i; ++j )
      {
        if ( v9 )
        {
          v13 = (LPVOID *)&v9[24 * j];
          if ( *v13 )
            DhcpPunycodeFree(v13);
        }
      }
    }
    else
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 80, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
      Configs = 8;
    }
    if ( v9 )
      DhcpPunycodeFree((LPVOID *)&v20);
  }
  else
  {
    Configs = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !Configs )
    {
      *a3 = cSubKeys;
      return 0;
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 79, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  }
  return Configs;
}

```

## disassembly

```asm
0x1800079e4  mov     [rsp-8+arg_18], rbx
0x1800079e9  push    rbp
0x1800079ea  push    rsi
0x1800079eb  push    rdi
0x1800079ec  push    r12
0x1800079ee  push    r13
0x1800079f0  push    r14
0x1800079f2  push    r15
0x1800079f4  lea     rbp, [rsp-60h]
0x1800079f9  sub     rsp, 160h
0x180007a00  mov     rax, cs:__security_cookie
0x180007a07  xor     rax, rsp
0x180007a0a  mov     [rbp+90h+var_40], rax
0x180007a0e  xor     r13d, r13d
0x180007a11  mov     rdi, r8
0x180007a14  mov     [rdx], r13
0x180007a17  mov     r12, rdx
0x180007a1a  mov     eax, [r8]
0x180007a1d  mov     r14, rcx
0x180007a20  mov     [rsp+190h+cSubKeys], r13d
0x180007a25  mov     [rsp+190h+cchName], r13d
0x180007a2a  mov     [rsp+190h+phkResult], r13
0x180007a2f  test    eax, eax
0x180007a31  jnz     short loc_180007AA7
0x180007a33  mov     [rsp+190h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180007a38  lea     rax, [rsp+190h+cSubKeys]
0x180007a3d  mov     [rsp+190h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180007a42  xor     r9d, r9d; lpReserved
0x180007a45  mov     [rsp+190h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180007a4a  xor     r8d, r8d; lpcchClass
0x180007a4d  mov     [rsp+190h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180007a52  xor     edx, edx; lpClass
0x180007a54  mov     [rsp+190h+lpcValues], r13; lpcValues
0x180007a59  mov     [rsp+190h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180007a5e  mov     [rsp+190h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180007a63  mov     [rsp+190h+lpcSubKeys], rax; lpcSubKeys
0x180007a68  call    cs:__imp_RegQueryInfoKeyW
0x180007a6e  mov     ebx, eax
0x180007a70  test    eax, eax
0x180007a72  jnz     loc_180007C62
0x180007a78  mov     eax, [rsp+190h+cSubKeys]
0x180007a7c  mov     [rdi], eax
0x180007a7e  xor     eax, eax
0x180007a80  mov     rcx, [rbp+90h+var_40]
0x180007a84  xor     rcx, rsp; StackCookie
0x180007a87  call    __security_check_cookie
0x180007a8c  mov     rbx, [rsp+190h+arg_18]
0x180007a94  add     rsp, 160h
0x180007a9b  pop     r15
0x180007a9d  pop     r14
0x180007a9f  pop     r13
0x180007aa1  pop     r12
0x180007aa3  pop     rdi
0x180007aa4  pop     rsi
0x180007aa5  pop     rbp
0x180007aa6  retn
0x180007aa7  lea     rcx, [rax+rax*2]
0x180007aab  mov     [rsp+190h+cSubKeys], eax
0x180007aaf  shl     rcx, 3
0x180007ab3  call    DhcpAlloc
0x180007ab8  mov     [rsp+190h+var_120], rax
0x180007abd  mov     rdi, rax
0x180007ac0  test    rax, rax
0x180007ac3  jz      loc_180007C28
0x180007ac9  mov     ebx, r13d
0x180007acc  mov     esi, r13d
0x180007acf  cmp     esi, [rsp+190h+cSubKeys]
0x180007ad3  jnb     loc_180007BBD
0x180007ad9  xor     edx, edx; Val
0x180007adb  mov     [rsp+190h+cchName], 64h ; 'd'
0x180007ae3  mov     r8d, 0C8h; Size
0x180007ae9  lea     rcx, [rbp+90h+Name]; void *
0x180007aed  call    memset_0
0x180007af2  mov     [rsp+190h+lpcValues], r13; lpftLastWriteTime
0x180007af7  lea     r9, [rsp+190h+cchName]; lpcchName
0x180007afc  mov     [rsp+190h+lpcbMaxClassLen], r13; lpcchClass
0x180007b01  lea     r8, [rbp+90h+Name]; lpName
0x180007b05  mov     [rsp+190h+lpcbMaxSubKeyLen], r13; lpClass
0x180007b0a  mov     edx, esi; dwIndex
0x180007b0c  mov     rcx, r14; hKey
0x180007b0f  mov     [rsp+190h+lpcSubKeys], r13; lpReserved
0x180007b14  call    cs:__imp_RegEnumKeyExW
0x180007b1a  mov     ebx, eax
0x180007b1c  test    eax, eax
0x180007b1e  jnz     loc_180007BFD
0x180007b24  lea     rax, [rsp+190h+phkResult]
0x180007b29  mov     r9d, 2001Bh; samDesired
0x180007b2f  xor     r8d, r8d; ulOptions
0x180007b32  mov     [rsp+190h+lpcSubKeys], rax; phkResult
0x180007b37  lea     rdx, [rbp+90h+Name]; lpSubKey
0x180007b3b  mov     rcx, r14; hKey
0x180007b3e  call    cs:__imp_RegOpenKeyExW
0x180007b44  mov     ebx, eax
0x180007b46  test    eax, eax
0x180007b48  jnz     loc_180007CBD
0x180007b4e  mov     eax, esi
0x180007b50  lea     rcx, [rax+rax*2]
0x180007b54  lea     r15, [rdi+rcx*8]
0x180007b58  mov     rcx, [rsp+190h+phkResult]; hKey
0x180007b5d  mov     rdx, r15
0x180007b60  call    ReadConfigs
0x180007b65  mov     rcx, [rsp+190h+phkResult]; hKey
0x180007b6a  mov     ebx, eax
0x180007b6c  call    cs:__imp_RegCloseKey
0x180007b72  test    ebx, ebx
0x180007b74  jz      short loc_180007BCC
0x180007b76  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007b7d  jnz     loc_180007CA2
0x180007b83  mov     r14d, r13d
0x180007b86  test    esi, esi
0x180007b88  jz      short loc_180007BAC
0x180007b8a  test    rdi, rdi
0x180007b8d  jz      short loc_180007BA4
0x180007b8f  mov     eax, r14d
0x180007b92  lea     rcx, [rax+rax*2]
0x180007b96  lea     rcx, [rdi+rcx*8]
0x180007b9a  cmp     [rcx], r13
0x180007b9d  jz      short loc_180007BA4
0x180007b9f  call    DhcpPunycodeFree
0x180007ba4  inc     r14d
0x180007ba7  cmp     r14d, esi
0x180007baa  jb      short loc_180007B8A
0x180007bac  test    rdi, rdi
0x180007baf  jz      short loc_180007BC5
0x180007bb1  lea     rcx, [rsp+190h+var_120]
0x180007bb6  call    DhcpPunycodeFree
0x180007bbb  jmp     short loc_180007BC5
0x180007bbd  mov     [r12], rdi
0x180007bc1  test    ebx, ebx
0x180007bc3  jnz     short loc_180007B83
0x180007bc5  mov     eax, ebx
0x180007bc7  jmp     loc_180007A80
0x180007bcc  mov     eax, [rsp+190h+cchName]
0x180007bd0  add     eax, eax
0x180007bd2  mov     ecx, eax
0x180007bd4  add     rcx, 2
0x180007bd8  mov     [rsp+190h+cchName], eax
0x180007bdc  call    DhcpAlloc
0x180007be1  mov     [r15], rax
0x180007be4  test    rax, rax
0x180007be7  jnz     short loc_180007C3B
0x180007be9  lea     ebx, [rax+8]
0x180007bec  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007bf3  jz      short loc_180007B83
0x180007bf5  lea     edx, [rax+54h]
0x180007bf8  jmp     loc_180007CA7
0x180007bfd  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007c04  jz      loc_180007B83
0x180007c0a  mov     edx, 51h ; 'Q'
0x180007c0f  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180007c16  mov     ecx, 404h
0x180007c1b  mov     r9d, esi
0x180007c1e  call    WPP_SF_d
0x180007c23  jmp     loc_180007B83
0x180007c28  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007c2f  jnz     short loc_180007C8A
0x180007c31  mov     ebx, 8
0x180007c36  jmp     loc_180007BAC
0x180007c3b  mov     r8d, [rsp+190h+cchName]; Size
0x180007c40  lea     rdx, [rbp+90h+Name]; Src
0x180007c44  mov     rcx, rax; void *
0x180007c47  call    memcpy_0
0x180007c4c  mov     edx, [rsp+190h+cchName]
0x180007c50  mov     rcx, [r15]
0x180007c53  shr     rdx, 1
0x180007c56  inc     esi
0x180007c58  mov     [rcx+rdx*2], r13w
0x180007c5d  jmp     loc_180007ACF
0x180007c62  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007c69  jz      loc_180007BC5
0x180007c6f  mov     edx, 4Fh ; 'O'
0x180007c74  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180007c7b  mov     ecx, 404h
0x180007c80  call    WPP_SF_
0x180007c85  jmp     loc_180007BC5
0x180007c8a  mov     edx, 50h ; 'P'
0x180007c8f  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180007c96  mov     ecx, 404h
0x180007c9b  call    WPP_SF_
0x180007ca0  jmp     short loc_180007C31
0x180007ca2  mov     edx, 53h ; 'S'
0x180007ca7  mov     ecx, 404h
0x180007cac  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180007cb3  call    WPP_SF_
0x180007cb8  jmp     loc_180007B83
0x180007cbd  test    byte ptr cs:xmmword_1800616A0, 10h
0x180007cc4  jz      loc_180007B83
0x180007cca  mov     edx, 52h ; 'R'
0x180007ccf  jmp     short loc_180007CA7
```
