# WxpDeObfuscateKey

- ea: `0x1803a6c08`
- end: `0x1803a7131`
- name: `WxpDeObfuscateKey`
- size: `1321`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180190d1c`

## callees

- `0x18001e090`
- `0x1803a6aec`
- `0x1803a6c08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6d9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6ebd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6fe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6d9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6ebd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1803a6fe0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6cc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6de6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6f09`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a702c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6cc9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6de6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a6f09`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1803a702c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6f15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a7038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a7108`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6cd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a6f15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a7038`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803a7108`

## pseudocode

```c
char __fastcall WxpDeObfuscateKey(__int64 a1, __int64 a2)
{
  HKEY v3; // rax
  HKEY v4; // r14
  __int128 *v5; // rsi
  char v6; // di
  LSTATUS v7; // ebx
  unsigned int i; // r9d
  CHAR v9; // dl
  char v10; // dl
  CHAR v11; // r8
  char v12; // r8
  LSTATUS v13; // ebx
  unsigned int j; // r9d
  CHAR v15; // dl
  char v16; // dl
  CHAR v17; // r8
  char v18; // r8
  LSTATUS v19; // ebx
  unsigned int k; // r9d
  CHAR v21; // dl
  char v22; // dl
  CHAR v23; // r8
  char v24; // r8
  LSTATUS v25; // ebx
  unsigned int m; // r9d
  CHAR v27; // dl
  char v28; // dl
  CHAR v29; // r8
  char v30; // r8
  __int64 n; // r9
  CHAR v32; // dl
  __int64 v33; // r8
  DWORD cchClass; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-21h] BYREF
  __int128 v37; // [rsp+78h] [rbp-11h] BYREF
  CHAR Class[16]; // [rsp+88h] [rbp-1h] BYREF

  v37 = 0;
  hKey[0] = 0;
  cchClass = 0;
  v3 = (HKEY)OpenLsaKey();
  v4 = v3;
  if ( v3 )
  {
    v5 = &v37;
    v6 = 1;
    if ( !RegOpenKeyExA(v3, "JD", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v7 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v7 )
      {
        for ( i = 0; i < 8; i += 2 )
        {
          v9 = Class[i];
          if ( (unsigned __int8)(v9 - 48) > 9u )
          {
            if ( (unsigned __int8)(v9 - 97) > 5u )
            {
              if ( (unsigned __int8)(v9 - 65) > 5u )
                v10 = -1;
              else
                v10 = v9 - 55;
            }
            else
            {
              v10 = v9 - 87;
            }
          }
          else
          {
            v10 = v9 - 48;
          }
          v11 = Class[i + 1];
          if ( (unsigned __int8)(v11 - 48) > 9u )
          {
            if ( (unsigned __int8)(v11 - 97) > 5u )
            {
              if ( (unsigned __int8)(v11 - 65) > 5u )
                v12 = -1;
              else
                v12 = v11 - 55;
            }
            else
            {
              v12 = v11 - 87;
            }
          }
          else
          {
            v12 = v11 - 48;
          }
          if ( (unsigned __int8)v10 > 0xFu || (unsigned __int8)v12 > 0xFu )
          {
LABEL_86:
            v6 = 0;
            goto LABEL_89;
          }
          *(_BYTE *)v5 = v12 + 16 * v10;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "Skew1", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v13 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v13 )
      {
        for ( j = 0; j < 8; j += 2 )
        {
          v15 = Class[j];
          if ( (unsigned __int8)(v15 - 48) > 9u )
          {
            if ( (unsigned __int8)(v15 - 97) > 5u )
            {
              if ( (unsigned __int8)(v15 - 65) > 5u )
                v16 = -1;
              else
                v16 = v15 - 55;
            }
            else
            {
              v16 = v15 - 87;
            }
          }
          else
          {
            v16 = v15 - 48;
          }
          v17 = Class[j + 1];
          if ( (unsigned __int8)(v17 - 48) > 9u )
          {
            if ( (unsigned __int8)(v17 - 97) > 5u )
            {
              if ( (unsigned __int8)(v17 - 65) > 5u )
                v18 = -1;
              else
                v18 = v17 - 55;
            }
            else
            {
              v18 = v17 - 87;
            }
          }
          else
          {
            v18 = v17 - 48;
          }
          if ( (unsigned __int8)v16 > 0xFu || (unsigned __int8)v18 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v18 + 16 * v16;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "GBG", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v19 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v19 )
      {
        for ( k = 0; k < 8; k += 2 )
        {
          v21 = Class[k];
          if ( (unsigned __int8)(v21 - 48) > 9u )
          {
            if ( (unsigned __int8)(v21 - 97) > 5u )
            {
              if ( (unsigned __int8)(v21 - 65) > 5u )
                v22 = -1;
              else
                v22 = v21 - 55;
            }
            else
            {
              v22 = v21 - 87;
            }
          }
          else
          {
            v22 = v21 - 48;
          }
          v23 = Class[k + 1];
          if ( (unsigned __int8)(v23 - 48) > 9u )
          {
            if ( (unsigned __int8)(v23 - 97) > 5u )
            {
              if ( (unsigned __int8)(v23 - 65) > 5u )
                v24 = -1;
              else
                v24 = v23 - 55;
            }
            else
            {
              v24 = v23 - 87;
            }
          }
          else
          {
            v24 = v23 - 48;
          }
          if ( (unsigned __int8)v22 > 0xFu || (unsigned __int8)v24 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v24 + 16 * v22;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    if ( !RegOpenKeyExA(v4, "Data", 0, 0x20019u, hKey) )
    {
      cchClass = 9;
      v25 = RegQueryInfoKeyA(hKey[0], Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
      RegCloseKey(hKey[0]);
      if ( !v25 )
      {
        for ( m = 0; m < 8; m += 2 )
        {
          v27 = Class[m];
          if ( (unsigned __int8)(v27 - 48) > 9u )
          {
            if ( (unsigned __int8)(v27 - 97) > 5u )
            {
              if ( (unsigned __int8)(v27 - 65) > 5u )
                v28 = -1;
              else
                v28 = v27 - 55;
            }
            else
            {
              v28 = v27 - 87;
            }
          }
          else
          {
            v28 = v27 - 48;
          }
          v29 = Class[m + 1];
          if ( (unsigned __int8)(v29 - 48) > 9u )
          {
            if ( (unsigned __int8)(v29 - 97) > 5u )
            {
              if ( (unsigned __int8)(v29 - 65) > 5u )
                v30 = -1;
              else
                v30 = v29 - 55;
            }
            else
            {
              v30 = v29 - 87;
            }
          }
          else
          {
            v30 = v29 - 48;
          }
          if ( (unsigned __int8)v28 > 0xFu || (unsigned __int8)v30 > 0xFu )
            goto LABEL_86;
          *(_BYTE *)v5 = v30 + 16 * v28;
          v5 = (__int128 *)((char *)v5 + 1);
        }
      }
    }
    for ( n = 0; n != 16; ++n )
    {
      v32 = Class[n - 16];
      v33 = *((unsigned __int8 *)qword_1804CA4A0 + n);
      *(_BYTE *)(v33 + a2) = v32;
    }
LABEL_89:
    RegCloseKey(v4);
    LOBYTE(v3) = v6;
  }
  return (char)v3;
}

```

## disassembly

```asm
0x1803a6c08  push    rbp
0x1803a6c0a  push    rbx
0x1803a6c0b  push    rsi
0x1803a6c0c  push    rdi
0x1803a6c0d  push    r12
0x1803a6c0f  push    r13
0x1803a6c11  push    r14
0x1803a6c13  push    r15
0x1803a6c15  lea     rbp, [rsp-1Fh]
0x1803a6c1a  sub     rsp, 0A8h
0x1803a6c21  mov     rax, cs:__security_cookie
0x1803a6c28  xor     rax, rsp
0x1803a6c2b  mov     [rbp+57h+var_48], rax
0x1803a6c2f  xorps   xmm0, xmm0
0x1803a6c32  xor     r12d, r12d
0x1803a6c35  movups  [rbp+57h+var_68], xmm0
0x1803a6c39  mov     [rbp+57h+hKey], r12
0x1803a6c3d  mov     r15, rdx
0x1803a6c40  mov     [rbp+57h+cchClass], r12d
0x1803a6c44  call    OpenLsaKey
0x1803a6c49  mov     r14, rax
0x1803a6c4c  test    rax, rax
0x1803a6c4f  jz      loc_1803A7111
0x1803a6c55  lea     rax, [rbp+57h+hKey]
0x1803a6c59  mov     r9d, 20019h; samDesired
0x1803a6c5f  xor     r8d, r8d; ulOptions
0x1803a6c62  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1803a6c67  lea     rdx, aJd; "JD"
0x1803a6c6e  mov     rcx, r14; hKey
0x1803a6c71  lea     rsi, [rbp+57h+var_68]
0x1803a6c75  call    cs:__imp_RegOpenKeyExA
0x1803a6c7b  mov     r13b, 5
0x1803a6c7e  mov     edi, 1
0x1803a6c83  test    eax, eax
0x1803a6c85  jnz     loc_1803A6D7E
0x1803a6c8b  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6c8f  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1803a6c93  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1803a6c98  lea     rdx, [rbp+57h+Class]; lpClass
0x1803a6c9c  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1803a6ca1  xor     r9d, r9d; lpReserved
0x1803a6ca4  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1803a6ca9  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1803a6cae  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1803a6cb3  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1803a6cb8  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1803a6cbd  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1803a6cc2  mov     [rbp+57h+cchClass], 9
0x1803a6cc9  call    cs:__imp_RegQueryInfoKeyA
0x1803a6ccf  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6cd3  mov     ebx, eax
0x1803a6cd5  call    cs:__imp_RegCloseKey
0x1803a6cdb  test    ebx, ebx
0x1803a6cdd  jnz     loc_1803A6D7E
0x1803a6ce3  mov     r9d, r12d
0x1803a6ce6  cmp     r9d, 8
0x1803a6cea  jnb     loc_1803A6D7E
0x1803a6cf0  mov     eax, r9d
0x1803a6cf3  mov     dl, [rbp+rax+57h+Class]
0x1803a6cf7  lea     eax, [rdx-30h]
0x1803a6cfa  cmp     al, 9
0x1803a6cfc  ja      short loc_1803A6D03
0x1803a6cfe  sub     dl, 30h ; '0'
0x1803a6d01  jmp     short loc_1803A6D1F
0x1803a6d03  lea     eax, [rdx-61h]
0x1803a6d06  cmp     al, r13b
0x1803a6d09  ja      short loc_1803A6D10
0x1803a6d0b  sub     dl, 57h ; 'W'
0x1803a6d0e  jmp     short loc_1803A6D1F
0x1803a6d10  lea     eax, [rdx-41h]
0x1803a6d13  cmp     al, r13b
0x1803a6d16  ja      short loc_1803A6D1D
0x1803a6d18  sub     dl, 37h ; '7'
0x1803a6d1b  jmp     short loc_1803A6D1F
0x1803a6d1d  mov     dl, 0FFh
0x1803a6d1f  lea     eax, [r9+1]
0x1803a6d23  mov     r8b, [rbp+rax+57h+Class]
0x1803a6d28  lea     eax, [r8-30h]
0x1803a6d2c  cmp     al, 9
0x1803a6d2e  ja      short loc_1803A6D36
0x1803a6d30  sub     r8b, 30h ; '0'
0x1803a6d34  jmp     short loc_1803A6D57
0x1803a6d36  lea     eax, [r8-61h]
0x1803a6d3a  cmp     al, r13b
0x1803a6d3d  ja      short loc_1803A6D45
0x1803a6d3f  sub     r8b, 57h ; 'W'
0x1803a6d43  jmp     short loc_1803A6D57
0x1803a6d45  lea     eax, [r8-41h]
0x1803a6d49  cmp     al, r13b
0x1803a6d4c  ja      short loc_1803A6D54
0x1803a6d4e  sub     r8b, 37h ; '7'
0x1803a6d52  jmp     short loc_1803A6D57
0x1803a6d54  mov     r8b, 0FFh
0x1803a6d57  cmp     dl, 0Fh
0x1803a6d5a  ja      loc_1803A70DF
0x1803a6d60  cmp     r8b, 0Fh
0x1803a6d64  ja      loc_1803A70DF
0x1803a6d6a  shl     dl, 4
0x1803a6d6d  add     dl, r8b
0x1803a6d70  mov     [rsi], dl
0x1803a6d72  add     rsi, rdi
0x1803a6d75  add     r9d, 2
0x1803a6d79  jmp     loc_1803A6CE6
0x1803a6d7e  lea     rax, [rbp+57h+hKey]
0x1803a6d82  mov     r9d, 20019h; samDesired
0x1803a6d88  xor     r8d, r8d; ulOptions
0x1803a6d8b  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1803a6d90  lea     rdx, aSkew1; "Skew1"
0x1803a6d97  mov     rcx, r14; hKey
0x1803a6d9a  call    cs:__imp_RegOpenKeyExA
0x1803a6da0  test    eax, eax
0x1803a6da2  jnz     loc_1803A6EA1
0x1803a6da8  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6dac  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1803a6db0  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1803a6db5  lea     rdx, [rbp+57h+Class]; lpClass
0x1803a6db9  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1803a6dbe  xor     r9d, r9d; lpReserved
0x1803a6dc1  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1803a6dc6  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1803a6dcb  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1803a6dd0  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1803a6dd5  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1803a6dda  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1803a6ddf  mov     [rbp+57h+cchClass], 9
0x1803a6de6  call    cs:__imp_RegQueryInfoKeyA
0x1803a6dec  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6df0  mov     ebx, eax
0x1803a6df2  call    cs:__imp_RegCloseKey
0x1803a6df8  test    ebx, ebx
0x1803a6dfa  jnz     loc_1803A6EA1
0x1803a6e00  mov     r9d, r12d
0x1803a6e03  mov     r10b, 30h ; '0'
0x1803a6e06  cmp     r9d, 8
0x1803a6e0a  jnb     loc_1803A6EA1
0x1803a6e10  mov     eax, r9d
0x1803a6e13  mov     dl, [rbp+rax+57h+Class]
0x1803a6e17  mov     al, dl
0x1803a6e19  sub     al, r10b
0x1803a6e1c  cmp     al, 9
0x1803a6e1e  ja      short loc_1803A6E25
0x1803a6e20  sub     dl, r10b
0x1803a6e23  jmp     short loc_1803A6E41
0x1803a6e25  lea     eax, [rdx-61h]
0x1803a6e28  cmp     al, r13b
0x1803a6e2b  ja      short loc_1803A6E32
0x1803a6e2d  sub     dl, 57h ; 'W'
0x1803a6e30  jmp     short loc_1803A6E41
0x1803a6e32  lea     eax, [rdx-41h]
0x1803a6e35  cmp     al, r13b
0x1803a6e38  ja      short loc_1803A6E3F
0x1803a6e3a  sub     dl, 37h ; '7'
0x1803a6e3d  jmp     short loc_1803A6E41
0x1803a6e3f  mov     dl, 0FFh
0x1803a6e41  lea     eax, [r9+1]
0x1803a6e45  mov     r8b, [rbp+rax+57h+Class]
0x1803a6e4a  mov     al, r8b
0x1803a6e4d  sub     al, r10b
0x1803a6e50  cmp     al, 9
0x1803a6e52  ja      short loc_1803A6E59
0x1803a6e54  sub     r8b, r10b
0x1803a6e57  jmp     short loc_1803A6E7A
0x1803a6e59  lea     eax, [r8-61h]
0x1803a6e5d  cmp     al, r13b
0x1803a6e60  ja      short loc_1803A6E68
0x1803a6e62  sub     r8b, 57h ; 'W'
0x1803a6e66  jmp     short loc_1803A6E7A
0x1803a6e68  lea     eax, [r8-41h]
0x1803a6e6c  cmp     al, r13b
0x1803a6e6f  ja      short loc_1803A6E77
0x1803a6e71  sub     r8b, 37h ; '7'
0x1803a6e75  jmp     short loc_1803A6E7A
0x1803a6e77  mov     r8b, 0FFh
0x1803a6e7a  cmp     dl, 0Fh
0x1803a6e7d  ja      loc_1803A70DF
0x1803a6e83  cmp     r8b, 0Fh
0x1803a6e87  ja      loc_1803A70DF
0x1803a6e8d  shl     dl, 4
0x1803a6e90  add     dl, r8b
0x1803a6e93  mov     [rsi], dl
0x1803a6e95  add     rsi, rdi
0x1803a6e98  add     r9d, 2
0x1803a6e9c  jmp     loc_1803A6E06
0x1803a6ea1  lea     rax, [rbp+57h+hKey]
0x1803a6ea5  mov     r9d, 20019h; samDesired
0x1803a6eab  xor     r8d, r8d; ulOptions
0x1803a6eae  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1803a6eb3  lea     rdx, aGbg; "GBG"
0x1803a6eba  mov     rcx, r14; hKey
0x1803a6ebd  call    cs:__imp_RegOpenKeyExA
0x1803a6ec3  test    eax, eax
0x1803a6ec5  jnz     loc_1803A6FC4
0x1803a6ecb  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6ecf  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1803a6ed3  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1803a6ed8  lea     rdx, [rbp+57h+Class]; lpClass
0x1803a6edc  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1803a6ee1  xor     r9d, r9d; lpReserved
0x1803a6ee4  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1803a6ee9  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1803a6eee  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1803a6ef3  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1803a6ef8  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1803a6efd  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1803a6f02  mov     [rbp+57h+cchClass], 9
0x1803a6f09  call    cs:__imp_RegQueryInfoKeyA
0x1803a6f0f  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6f13  mov     ebx, eax
0x1803a6f15  call    cs:__imp_RegCloseKey
0x1803a6f1b  test    ebx, ebx
0x1803a6f1d  jnz     loc_1803A6FC4
0x1803a6f23  mov     r9d, r12d
0x1803a6f26  mov     r10b, 30h ; '0'
0x1803a6f29  cmp     r9d, 8
0x1803a6f2d  jnb     loc_1803A6FC4
0x1803a6f33  mov     eax, r9d
0x1803a6f36  mov     dl, [rbp+rax+57h+Class]
0x1803a6f3a  mov     al, dl
0x1803a6f3c  sub     al, r10b
0x1803a6f3f  cmp     al, 9
0x1803a6f41  ja      short loc_1803A6F48
0x1803a6f43  sub     dl, r10b
0x1803a6f46  jmp     short loc_1803A6F64
0x1803a6f48  lea     eax, [rdx-61h]
0x1803a6f4b  cmp     al, r13b
0x1803a6f4e  ja      short loc_1803A6F55
0x1803a6f50  sub     dl, 57h ; 'W'
0x1803a6f53  jmp     short loc_1803A6F64
0x1803a6f55  lea     eax, [rdx-41h]
0x1803a6f58  cmp     al, r13b
0x1803a6f5b  ja      short loc_1803A6F62
0x1803a6f5d  sub     dl, 37h ; '7'
0x1803a6f60  jmp     short loc_1803A6F64
0x1803a6f62  mov     dl, 0FFh
0x1803a6f64  lea     eax, [r9+1]
0x1803a6f68  mov     r8b, [rbp+rax+57h+Class]
0x1803a6f6d  mov     al, r8b
0x1803a6f70  sub     al, r10b
0x1803a6f73  cmp     al, 9
0x1803a6f75  ja      short loc_1803A6F7C
0x1803a6f77  sub     r8b, r10b
0x1803a6f7a  jmp     short loc_1803A6F9D
0x1803a6f7c  lea     eax, [r8-61h]
0x1803a6f80  cmp     al, r13b
0x1803a6f83  ja      short loc_1803A6F8B
0x1803a6f85  sub     r8b, 57h ; 'W'
0x1803a6f89  jmp     short loc_1803A6F9D
0x1803a6f8b  lea     eax, [r8-41h]
0x1803a6f8f  cmp     al, r13b
0x1803a6f92  ja      short loc_1803A6F9A
0x1803a6f94  sub     r8b, 37h ; '7'
0x1803a6f98  jmp     short loc_1803A6F9D
0x1803a6f9a  mov     r8b, 0FFh
0x1803a6f9d  cmp     dl, 0Fh
0x1803a6fa0  ja      loc_1803A70DF
0x1803a6fa6  cmp     r8b, 0Fh
0x1803a6faa  ja      loc_1803A70DF
0x1803a6fb0  shl     dl, 4
0x1803a6fb3  add     dl, r8b
0x1803a6fb6  mov     [rsi], dl
0x1803a6fb8  add     rsi, rdi
0x1803a6fbb  add     r9d, 2
0x1803a6fbf  jmp     loc_1803A6F29
0x1803a6fc4  lea     rax, [rbp+57h+hKey]
0x1803a6fc8  mov     r9d, 20019h; samDesired
0x1803a6fce  xor     r8d, r8d; ulOptions
0x1803a6fd1  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1803a6fd6  lea     rdx, aData; "Data"
0x1803a6fdd  mov     rcx, r14; hKey
0x1803a6fe0  call    cs:__imp_RegOpenKeyExA
0x1803a6fe6  test    eax, eax
0x1803a6fe8  jnz     loc_1803A70E4
0x1803a6fee  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a6ff2  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1803a6ff6  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1803a6ffb  lea     rdx, [rbp+57h+Class]; lpClass
0x1803a6fff  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1803a7004  xor     r9d, r9d; lpReserved
0x1803a7007  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1803a700c  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1803a7011  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1803a7016  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1803a701b  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1803a7020  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1803a7025  mov     [rbp+57h+cchClass], 9
0x1803a702c  call    cs:__imp_RegQueryInfoKeyA
0x1803a7032  mov     rcx, [rbp+57h+hKey]; hKey
0x1803a7036  mov     ebx, eax
0x1803a7038  call    cs:__imp_RegCloseKey
0x1803a703e  test    ebx, ebx
0x1803a7040  jnz     loc_1803A70E4
0x1803a7046  mov     r9d, r12d
0x1803a7049  mov     r10b, 30h ; '0'
0x1803a704c  cmp     r9d, 8
0x1803a7050  jnb     loc_1803A70E4
0x1803a7056  mov     eax, r9d
0x1803a7059  mov     dl, [rbp+rax+57h+Class]
0x1803a705d  mov     al, dl
0x1803a705f  sub     al, r10b
0x1803a7062  cmp     al, 9
  ... truncated ...
```
