# DnsReadPropertiesForServers

- ea: `0x180023aac`
- end: `0x180023f0d`
- name: `DnsReadPropertiesForServers`
- size: `1121`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, LPCWSTR lpSubKey@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180023380`

## callees

- `0x180008870`
- `0x18000b0a8`
- `0x18000b0e8`
- `0x18000b130`
- `0x180020e7c`
- `0x180023aac`
- `0x180046ec0`
- `0x180085fb8`
- `0x180086384`
- `0x180086b1c`
- `0x1800882f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180023ba7`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180023ba7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023edc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023e64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023edc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023bfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023dd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023bfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023dd9`

## pseudocode

```c
__int64 __fastcall DnsReadPropertiesForServers(
        HKEY hKey,
        HKEY a2,
        __int64 lpSubKey,
        unsigned int a4,
        unsigned int *a5,
        _QWORD *a6)
{
  _DWORD *v6; // rdi
  __int64 v7; // rax
  LPCWSTR v8; // rsi
  HKEY v9; // r14
  __int64 v11; // rbx
  wchar_t v12; // ax
  unsigned int v13; // ebx
  const WCHAR *v14; // rcx
  unsigned int v15; // r14d
  char v16; // al
  _WORD *v17; // rsi
  unsigned int v18; // eax
  unsigned int v20; // r14d
  __int64 j; // rsi
  __int64 v22; // rdx
  char v23; // al
  __int64 v24; // rdx
  unsigned int v25; // [rsp+50h] [rbp-49h] BYREF
  int i; // [rsp+54h] [rbp-45h]
  wchar_t v27; // [rsp+58h] [rbp-41h]
  unsigned int v28; // [rsp+5Ch] [rbp-3Dh]
  int v29; // [rsp+60h] [rbp-39h] BYREF
  int v30; // [rsp+64h] [rbp-35h] BYREF
  void *v31; // [rsp+68h] [rbp-31h]
  void *v32; // [rsp+70h] [rbp-29h]
  _WORD *v33; // [rsp+78h] [rbp-21h]
  HKEY v34; // [rsp+80h] [rbp-19h]
  HKEY hKeya; // [rsp+88h] [rbp-11h] BYREF

  v6 = 0;
  v7 = a4;
  v8 = (LPCWSTR)lpSubKey;
  v28 = a4;
  v9 = a2;
  hKeya = 0;
  v25 = 0;
  v31 = 0;
  v32 = 0;
  v30 = 0;
  v29 = 0;
  v34 = a2;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_qqSqqd((_DWORD)hKey, (_DWORD)a2, lpSubKey, (_DWORD)a2, (__int64)hKey, lpSubKey, (__int64)a6, (__int64)a5, a4);
    v7 = v28;
  }
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !a5 || !a6 || !v8 || !hKey && !v9 )
  {
    v13 = 87;
    goto LABEL_28;
  }
  v11 = 24 * v7;
  v6 = (_DWORD *)Dns_Allocate(24 * v7);
  if ( !v6 || hKey && (v31 = (void *)Dns_Allocate(v11)) == 0 || v9 && (v32 = (void *)Dns_Allocate(v11)) == 0 )
  {
    v13 = 14;
    goto LABEL_28;
  }
  v12 = *v8;
  v13 = 0;
  for ( i = 0; ; ++i )
  {
    if ( !v12 )
    {
      v18 = v25;
      *a6 = v6;
      v6 = 0;
      *a5 = v18;
      v25 = 0;
      goto LABEL_28;
    }
    v14 = &v8[wcscspn(v8, L" ,;")];
    v27 = *v14;
    *v14 = 0;
    v33 = v14;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_S(1035, 302, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v8);
    if ( v9 )
    {
      v15 = RegOpenKeyExW(v9, v8, 0, 0x20019u, &hKeya);
      if ( v15 != 2 )
      {
        v23 = BYTE1(xmmword_1800AB5A0);
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          WPP_SF_SD(1035, 303, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (_DWORD)v8, v15);
          v23 = BYTE1(xmmword_1800AB5A0);
        }
        v13 = v15;
        if ( v15 )
        {
          if ( (v23 & 8) == 0 )
            goto LABEL_28;
          v24 = 304;
          goto LABEL_56;
        }
        DnsAddPropertyToArray(
          2,
          (_DWORD)hKeya,
          (_DWORD)v8,
          i,
          (__int64)&v29,
          (__int64)v32,
          v28,
          (__int64)v6,
          (__int64)&v25);
        RegCloseKey(hKeya);
        hKeya = 0;
      }
    }
    if ( hKey )
    {
      v15 = RegOpenKeyExW(hKey, v8, 0, 0x20019u, &hKeya);
      if ( v15 != 2 )
        break;
    }
LABEL_26:
    v17 = v33;
    v12 = v27;
    v9 = v34;
    *v33 = v27;
    v8 = v17 + 1;
  }
  v16 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_SD(1035, 305, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (_DWORD)v8, v15);
    v16 = BYTE1(xmmword_1800AB5A0);
  }
  v13 = v15;
  if ( !v15 )
  {
    DnsAddPropertyToArray(1, (_DWORD)hKeya, (_DWORD)v8, i, (__int64)&v30, (__int64)v31, v28, (__int64)v6, (__int64)&v25);
    RegCloseKey(hKeya);
    hKeya = 0;
    goto LABEL_26;
  }
  if ( (v16 & 8) != 0 )
  {
    v24 = 306;
LABEL_56:
    WPP_SF_d(1035, v24, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v15);
  }
LABEL_28:
  MIDL_user_free(v31);
  MIDL_user_free(v32);
  if ( v6 )
  {
    v20 = v25;
    for ( j = 0; (unsigned int)j < v20; j = (unsigned int)(j + 1) )
    {
      v22 = 3 * j;
      if ( v6[6 * j + 2] == 1 )
      {
        DnsFreeServerPropertyDoh(&v6[2 * v22 + 4]);
      }
      else if ( v6[6 * j + 2] == 2 )
      {
        DnsFreeServerPropertyDot(&v6[2 * v22 + 4]);
      }
    }
  }
  MIDL_user_free(v6);
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 307, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180023aac  push    rbp
0x180023aae  push    rbx
0x180023aaf  push    rsi
0x180023ab0  push    rdi
0x180023ab1  push    r12
0x180023ab3  push    r13
0x180023ab5  push    r14
0x180023ab7  push    r15
0x180023ab9  lea     rbp, [rsp-0Fh]
0x180023abe  sub     rsp, 0A8h
0x180023ac5  mov     rax, cs:__security_cookie
0x180023acc  xor     rax, rsp
0x180023acf  mov     [rbp+47h+var_50], rax
0x180023ad3  mov     r15, [rbp+47h+arg_20]
0x180023ad7  xor     ebx, ebx
0x180023ad9  mov     r12, [rbp+47h+arg_28]
0x180023add  mov     edi, ebx
0x180023adf  mov     eax, r9d
0x180023ae2  mov     rsi, r8
0x180023ae5  mov     [rbp+47h+var_84], eax
0x180023ae8  mov     r14, rdx
0x180023aeb  mov     [rbp+47h+hKey], rbx
0x180023aef  mov     r13, rcx
0x180023af2  mov     [rbp+47h+var_90], ebx
0x180023af5  mov     [rbp+47h+var_78], rbx
0x180023af9  mov     [rbp+47h+var_70], rbx
0x180023afd  mov     [rbp+47h+var_7C], ebx
0x180023b00  mov     [rbp+47h+var_80], ebx
0x180023b03  mov     [rbp+47h+var_60], rdx
0x180023b07  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023b0e  jnz     loc_180023D6F
0x180023b14  test    r15, r15
0x180023b17  jz      short loc_180023B1C
0x180023b19  mov     [r15], ebx
0x180023b1c  test    r12, r12
0x180023b1f  jz      short loc_180023B25
0x180023b21  mov     [r12], rbx
0x180023b25  test    r15, r15
0x180023b28  jz      loc_180023CF7
0x180023b2e  test    r12, r12
0x180023b31  jz      loc_180023CF7
0x180023b37  test    rsi, rsi
0x180023b3a  jz      loc_180023CF7
0x180023b40  test    r13, r13
0x180023b43  jz      loc_180023D97
0x180023b49  lea     rbx, [rax+rax*2]
0x180023b4d  shl     rbx, 3
0x180023b51  mov     rcx, rbx
0x180023b54  call    Dns_Allocate
0x180023b59  xor     ecx, ecx
0x180023b5b  mov     rdi, rax
0x180023b5e  test    rax, rax
0x180023b61  jz      loc_180023CFE
0x180023b67  test    r13, r13
0x180023b6a  jz      short loc_180023B83
0x180023b6c  mov     rcx, rbx
0x180023b6f  call    Dns_Allocate
0x180023b74  xor     ecx, ecx
0x180023b76  mov     [rbp+47h+var_78], rax
0x180023b7a  test    rax, rax
0x180023b7d  jz      loc_180023CFE
0x180023b83  test    r14, r14
0x180023b86  jnz     loc_180023DA5
0x180023b8c  movzx   eax, word ptr [rsi]
0x180023b8f  mov     ebx, ecx
0x180023b91  mov     [rbp+47h+var_8C], ecx
0x180023b94  test    ax, ax
0x180023b97  jz      loc_180023C8C
0x180023b9d  lea     rdx, Control; " ,;"
0x180023ba4  mov     rcx, rsi; String
0x180023ba7  call    cs:__imp_wcscspn
0x180023bad  lea     rcx, [rsi+rax*2]
0x180023bb1  movzx   eax, word ptr [rcx]
0x180023bb4  mov     [rbp+47h+var_88], ax
0x180023bb8  xor     eax, eax
0x180023bba  mov     [rcx], ax
0x180023bbd  mov     [rbp+47h+var_68], rcx
0x180023bc1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023bc8  jnz     loc_180023D51
0x180023bce  xor     ecx, ecx
0x180023bd0  test    r14, r14
0x180023bd3  jnz     loc_180023DC1
0x180023bd9  test    r13, r13
0x180023bdc  jz      loc_180023C71
0x180023be2  lea     rax, [rbp+47h+hKey]
0x180023be6  mov     r9d, 20019h; samDesired
0x180023bec  xor     r8d, r8d; ulOptions
0x180023bef  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180023bf4  mov     rdx, rsi; lpSubKey
0x180023bf7  mov     rcx, r13; hKey
0x180023bfa  call    cs:__imp_RegOpenKeyExW
0x180023c00  mov     r14d, eax
0x180023c03  cmp     eax, 2
0x180023c06  jz      loc_180023D05
0x180023c0c  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180023c12  test    al, 8
0x180023c14  jnz     loc_180023E7C
0x180023c1a  mov     ebx, r14d
0x180023c1d  test    r14d, r14d
0x180023c20  jnz     loc_180023ED2
0x180023c26  mov     r9d, [rbp+47h+var_8C]
0x180023c2a  lea     rax, [rbp+47h+var_90]
0x180023c2e  mov     rdx, [rbp+47h+hKey]
0x180023c32  lea     ecx, [r14+1]
0x180023c36  mov     [rsp+0E0h+var_A0], rax
0x180023c3b  mov     r8, rsi
0x180023c3e  mov     eax, [rbp+47h+var_84]
0x180023c41  mov     [rsp+0E0h+var_A8], rdi
0x180023c46  mov     dword ptr [rsp+0E0h+var_B0], eax
0x180023c4a  mov     rax, [rbp+47h+var_78]
0x180023c4e  mov     [rsp+0E0h+var_B8], rax
0x180023c53  lea     rax, [rbp+47h+var_7C]
0x180023c57  mov     [rsp+0E0h+phkResult], rax
0x180023c5c  call    DnsAddPropertyToArray
0x180023c61  mov     rcx, [rbp+47h+hKey]; hKey
0x180023c65  call    cs:__imp_RegCloseKey
0x180023c6b  xor     ecx, ecx
0x180023c6d  mov     [rbp+47h+hKey], rcx
0x180023c71  mov     rsi, [rbp+47h+var_68]
0x180023c75  movzx   eax, [rbp+47h+var_88]
0x180023c79  mov     r14, [rbp+47h+var_60]
0x180023c7d  mov     [rsi], ax
0x180023c80  add     rsi, 2
0x180023c84  inc     [rbp+47h+var_8C]
0x180023c87  jmp     loc_180023B94
0x180023c8c  mov     eax, [rbp+47h+var_90]
0x180023c8f  mov     [r12], rdi
0x180023c93  mov     rdi, rcx
0x180023c96  mov     [r15], eax
0x180023c99  mov     [rbp+47h+var_90], ecx
0x180023c9c  mov     rcx, [rbp+47h+var_78]; void *
0x180023ca0  call    MIDL_user_free
0x180023ca5  mov     rcx, [rbp+47h+var_70]; void *
0x180023ca9  call    MIDL_user_free
0x180023cae  test    rdi, rdi
0x180023cb1  jnz     short loc_180023D0C
0x180023cb3  mov     rcx, rdi; void *
0x180023cb6  call    MIDL_user_free
0x180023cbb  mov     rcx, [rbp+47h+hKey]; hKey
0x180023cbf  test    rcx, rcx
0x180023cc2  jnz     loc_180023EDC
0x180023cc8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023ccf  jnz     loc_180023EEF
0x180023cd5  mov     eax, ebx
0x180023cd7  mov     rcx, [rbp+47h+var_50]
0x180023cdb  xor     rcx, rsp; StackCookie
0x180023cde  call    __security_check_cookie
0x180023ce3  add     rsp, 0A8h
0x180023cea  pop     r15
0x180023cec  pop     r14
0x180023cee  pop     r13
0x180023cf0  pop     r12
0x180023cf2  pop     rdi
0x180023cf3  pop     rsi
0x180023cf4  pop     rbx
0x180023cf5  pop     rbp
0x180023cf6  retn
0x180023cf7  mov     ebx, 57h ; 'W'
0x180023cfc  jmp     short loc_180023C9C
0x180023cfe  mov     ebx, 0Eh
0x180023d03  jmp     short loc_180023C9C
0x180023d05  xor     ecx, ecx
0x180023d07  jmp     loc_180023C71
0x180023d0c  mov     r14d, [rbp+47h+var_90]
0x180023d10  xor     esi, esi
0x180023d12  test    r14d, r14d
0x180023d15  jz      short loc_180023CB3
0x180023d17  lea     rdx, [rsi+rsi*2]
0x180023d1b  mov     ecx, [rdi+rdx*8+8]
0x180023d1f  sub     ecx, 1
0x180023d22  jnz     short loc_180023D3D
0x180023d24  add     rdx, 2
0x180023d28  lea     rcx, [rdi+rdx*8]
0x180023d2c  call    DnsFreeServerPropertyDoh
0x180023d31  inc     esi
0x180023d33  cmp     esi, r14d
0x180023d36  jb      short loc_180023D17
0x180023d38  jmp     loc_180023CB3
0x180023d3d  cmp     ecx, 1
0x180023d40  jnz     short loc_180023D31
0x180023d42  add     rdx, 2
0x180023d46  lea     rcx, [rdi+rdx*8]
0x180023d4a  call    DnsFreeServerPropertyDot
0x180023d4f  jmp     short loc_180023D31
0x180023d51  mov     edx, 12Eh
0x180023d56  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023d5d  mov     ecx, 40Bh
0x180023d62  mov     r9, rsi
0x180023d65  call    WPP_SF_S
0x180023d6a  jmp     loc_180023BCE
0x180023d6f  mov     dword ptr [rsp+0E0h+var_A0], eax
0x180023d73  mov     r9, r14
0x180023d76  mov     [rsp+0E0h+var_A8], r15
0x180023d7b  mov     [rsp+0E0h+var_B0], r12
0x180023d80  mov     [rsp+0E0h+var_B8], rsi
0x180023d85  mov     [rsp+0E0h+phkResult], r13
0x180023d8a  call    WPP_SF_qqSqqd
0x180023d8f  mov     eax, [rbp+47h+var_84]
0x180023d92  jmp     loc_180023B14
0x180023d97  test    r14, r14
0x180023d9a  jz      loc_180023CF7
0x180023da0  jmp     loc_180023B49
0x180023da5  mov     rcx, rbx
0x180023da8  call    Dns_Allocate
0x180023dad  xor     ecx, ecx
0x180023daf  mov     [rbp+47h+var_70], rax
0x180023db3  test    rax, rax
0x180023db6  jz      loc_180023CFE
0x180023dbc  jmp     loc_180023B8C
0x180023dc1  lea     rax, [rbp+47h+hKey]
0x180023dc5  mov     r9d, 20019h; samDesired
0x180023dcb  xor     r8d, r8d; ulOptions
0x180023dce  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180023dd3  mov     rdx, rsi; lpSubKey
0x180023dd6  mov     rcx, r14; hKey
0x180023dd9  call    cs:__imp_RegOpenKeyExW
0x180023ddf  mov     r14d, eax
0x180023de2  cmp     eax, 2
0x180023de5  jz      loc_180023E75
0x180023deb  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180023df1  test    al, 8
0x180023df3  jz      short loc_180023E19
0x180023df5  mov     edx, 12Fh
0x180023dfa  mov     dword ptr [rsp+0E0h+phkResult], r14d
0x180023dff  mov     ecx, 40Bh
0x180023e04  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023e0b  mov     r9, rsi
0x180023e0e  call    WPP_SF_SD
0x180023e13  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180023e19  mov     ebx, r14d
0x180023e1c  test    r14d, r14d
0x180023e1f  jnz     loc_180023EA5
0x180023e25  mov     r9d, [rbp+47h+var_8C]
0x180023e29  lea     rax, [rbp+47h+var_90]
0x180023e2d  mov     rdx, [rbp+47h+hKey]
0x180023e31  lea     ecx, [r14+2]
0x180023e35  mov     [rsp+0E0h+var_A0], rax
0x180023e3a  mov     r8, rsi
0x180023e3d  mov     eax, [rbp+47h+var_84]
0x180023e40  mov     [rsp+0E0h+var_A8], rdi
0x180023e45  mov     dword ptr [rsp+0E0h+var_B0], eax
0x180023e49  mov     rax, [rbp+47h+var_70]
0x180023e4d  mov     [rsp+0E0h+var_B8], rax
0x180023e52  lea     rax, [rbp+47h+var_80]
0x180023e56  mov     [rsp+0E0h+phkResult], rax
0x180023e5b  call    DnsAddPropertyToArray
0x180023e60  mov     rcx, [rbp+47h+hKey]; hKey
0x180023e64  call    cs:__imp_RegCloseKey
0x180023e6a  xor     ecx, ecx
0x180023e6c  mov     [rbp+47h+hKey], rcx
0x180023e70  jmp     loc_180023BD9
0x180023e75  xor     ecx, ecx
0x180023e77  jmp     loc_180023BD9
0x180023e7c  mov     edx, 131h
0x180023e81  mov     dword ptr [rsp+0E0h+phkResult], r14d
0x180023e86  mov     ecx, 40Bh
0x180023e8b  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023e92  mov     r9, rsi
0x180023e95  call    WPP_SF_SD
0x180023e9a  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180023ea0  jmp     loc_180023C1A
0x180023ea5  test    al, 8
0x180023ea7  jz      loc_180023C9C
0x180023ead  mov     edx, 130h
0x180023eb2  jmp     short loc_180023EB9
0x180023eb4  mov     edx, 132h
0x180023eb9  mov     ecx, 40Bh
0x180023ebe  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023ec5  mov     r9d, r14d
0x180023ec8  call    WPP_SF_d
0x180023ecd  jmp     loc_180023C9C
0x180023ed2  test    al, 8
0x180023ed4  jz      loc_180023C9C
0x180023eda  jmp     short loc_180023EB4
0x180023edc  call    cs:__imp_RegCloseKey
0x180023ee2  mov     [rbp+47h+hKey], 0
0x180023eea  jmp     loc_180023CC8
0x180023eef  mov     edx, 133h
0x180023ef4  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023efb  mov     ecx, 40Bh
0x180023f00  mov     r9d, ebx
0x180023f03  call    WPP_SF_d
0x180023f08  jmp     loc_180023CD5
```
