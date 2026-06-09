# WxpDeObfuscateKey

- ea: `0x180136590`
- end: `0x180136b08`
- name: `WxpDeObfuscateKey`
- size: `1400`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180103a70`

## callees

- `0x1800b86d0`
- `0x1801362f8`
- `0x180136590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801368cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136a02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ad8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801368cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136a02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180136ad8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801365fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180136734`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180136869`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18013699e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1801365fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180136734`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180136869`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18013699e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180136657`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180136786`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1801368bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1801369f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180136657`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180136786`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1801368bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1801369f0`

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
      v33 = *((unsigned __int8 *)qword_180171BC0 + n);
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
0x180136590  push    rbp
0x180136592  push    rbx
0x180136593  push    rsi
0x180136594  push    rdi
0x180136595  push    r12
0x180136597  push    r13
0x180136599  push    r14
0x18013659b  push    r15
0x18013659d  lea     rbp, [rsp-1Fh]
0x1801365a2  sub     rsp, 0A8h
0x1801365a9  mov     rax, cs:__security_cookie
0x1801365b0  xor     rax, rsp
0x1801365b3  mov     [rbp+57h+var_48], rax
0x1801365b7  xorps   xmm0, xmm0
0x1801365ba  xor     r12d, r12d
0x1801365bd  movups  [rbp+57h+var_68], xmm0
0x1801365c1  mov     [rbp+57h+hKey], r12
0x1801365c5  mov     r15, rdx
0x1801365c8  mov     [rbp+57h+cchClass], r12d
0x1801365cc  call    OpenLsaKey
0x1801365d1  mov     r14, rax
0x1801365d4  test    rax, rax
0x1801365d7  jz      loc_180136AE7
0x1801365dd  lea     rax, [rbp+57h+hKey]
0x1801365e1  mov     r9d, 20019h; samDesired
0x1801365e7  xor     r8d, r8d; ulOptions
0x1801365ea  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1801365ef  lea     rdx, aJd; "JD"
0x1801365f6  mov     rcx, r14; hKey
0x1801365f9  lea     rsi, [rbp+57h+var_68]
0x1801365fd  call    cs:__imp_RegOpenKeyExA
0x180136604  nop     dword ptr [rax+rax+00h]
0x180136609  mov     r13b, 5
0x18013660c  mov     edi, 1
0x180136611  test    eax, eax
0x180136613  jnz     loc_180136718
0x180136619  mov     rcx, [rbp+57h+hKey]; hKey
0x18013661d  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180136621  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180136626  lea     rdx, [rbp+57h+Class]; lpClass
0x18013662a  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18013662f  xor     r9d, r9d; lpReserved
0x180136632  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180136637  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18013663c  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180136641  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180136646  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18013664b  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x180136650  mov     [rbp+57h+cchClass], 9
0x180136657  call    cs:__imp_RegQueryInfoKeyA
0x18013665e  nop     dword ptr [rax+rax+00h]
0x180136663  mov     rcx, [rbp+57h+hKey]; hKey
0x180136667  mov     ebx, eax
0x180136669  call    cs:__imp_RegCloseKey
0x180136670  nop     dword ptr [rax+rax+00h]
0x180136675  test    ebx, ebx
0x180136677  jnz     loc_180136718
0x18013667d  mov     r9d, r12d
0x180136680  cmp     r9d, 8
0x180136684  jnb     loc_180136718
0x18013668a  mov     eax, r9d
0x18013668d  mov     dl, [rbp+rax+57h+Class]
0x180136691  lea     eax, [rdx-30h]
0x180136694  cmp     al, 9
0x180136696  ja      short loc_18013669D
0x180136698  sub     dl, 30h ; '0'
0x18013669b  jmp     short loc_1801366B9
0x18013669d  lea     eax, [rdx-61h]
0x1801366a0  cmp     al, r13b
0x1801366a3  ja      short loc_1801366AA
0x1801366a5  sub     dl, 57h ; 'W'
0x1801366a8  jmp     short loc_1801366B9
0x1801366aa  lea     eax, [rdx-41h]
0x1801366ad  cmp     al, r13b
0x1801366b0  ja      short loc_1801366B7
0x1801366b2  sub     dl, 37h ; '7'
0x1801366b5  jmp     short loc_1801366B9
0x1801366b7  mov     dl, 0FFh
0x1801366b9  lea     eax, [r9+1]
0x1801366bd  mov     r8b, [rbp+rax+57h+Class]
0x1801366c2  lea     eax, [r8-30h]
0x1801366c6  cmp     al, 9
0x1801366c8  ja      short loc_1801366D0
0x1801366ca  sub     r8b, 30h ; '0'
0x1801366ce  jmp     short loc_1801366F1
0x1801366d0  lea     eax, [r8-61h]
0x1801366d4  cmp     al, r13b
0x1801366d7  ja      short loc_1801366DF
0x1801366d9  sub     r8b, 57h ; 'W'
0x1801366dd  jmp     short loc_1801366F1
0x1801366df  lea     eax, [r8-41h]
0x1801366e3  cmp     al, r13b
0x1801366e6  ja      short loc_1801366EE
0x1801366e8  sub     r8b, 37h ; '7'
0x1801366ec  jmp     short loc_1801366F1
0x1801366ee  mov     r8b, 0FFh
0x1801366f1  cmp     dl, 0Fh
0x1801366f4  ja      loc_180136AAF
0x1801366fa  cmp     r8b, 0Fh
0x1801366fe  ja      loc_180136AAF
0x180136704  shl     dl, 4
0x180136707  add     dl, r8b
0x18013670a  mov     [rsi], dl
0x18013670c  add     rsi, rdi
0x18013670f  add     r9d, 2
0x180136713  jmp     loc_180136680
0x180136718  lea     rax, [rbp+57h+hKey]
0x18013671c  mov     r9d, 20019h; samDesired
0x180136722  xor     r8d, r8d; ulOptions
0x180136725  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18013672a  lea     rdx, aSkew1; "Skew1"
0x180136731  mov     rcx, r14; hKey
0x180136734  call    cs:__imp_RegOpenKeyExA
0x18013673b  nop     dword ptr [rax+rax+00h]
0x180136740  test    eax, eax
0x180136742  jnz     loc_18013684D
0x180136748  mov     rcx, [rbp+57h+hKey]; hKey
0x18013674c  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180136750  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180136755  lea     rdx, [rbp+57h+Class]; lpClass
0x180136759  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18013675e  xor     r9d, r9d; lpReserved
0x180136761  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180136766  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18013676b  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180136770  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180136775  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18013677a  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x18013677f  mov     [rbp+57h+cchClass], 9
0x180136786  call    cs:__imp_RegQueryInfoKeyA
0x18013678d  nop     dword ptr [rax+rax+00h]
0x180136792  mov     rcx, [rbp+57h+hKey]; hKey
0x180136796  mov     ebx, eax
0x180136798  call    cs:__imp_RegCloseKey
0x18013679f  nop     dword ptr [rax+rax+00h]
0x1801367a4  test    ebx, ebx
0x1801367a6  jnz     loc_18013684D
0x1801367ac  mov     r9d, r12d
0x1801367af  mov     r10b, 30h ; '0'
0x1801367b2  cmp     r9d, 8
0x1801367b6  jnb     loc_18013684D
0x1801367bc  mov     eax, r9d
0x1801367bf  mov     dl, [rbp+rax+57h+Class]
0x1801367c3  mov     al, dl
0x1801367c5  sub     al, r10b
0x1801367c8  cmp     al, 9
0x1801367ca  ja      short loc_1801367D1
0x1801367cc  sub     dl, r10b
0x1801367cf  jmp     short loc_1801367ED
0x1801367d1  lea     eax, [rdx-61h]
0x1801367d4  cmp     al, r13b
0x1801367d7  ja      short loc_1801367DE
0x1801367d9  sub     dl, 57h ; 'W'
0x1801367dc  jmp     short loc_1801367ED
0x1801367de  lea     eax, [rdx-41h]
0x1801367e1  cmp     al, r13b
0x1801367e4  ja      short loc_1801367EB
0x1801367e6  sub     dl, 37h ; '7'
0x1801367e9  jmp     short loc_1801367ED
0x1801367eb  mov     dl, 0FFh
0x1801367ed  lea     eax, [r9+1]
0x1801367f1  mov     r8b, [rbp+rax+57h+Class]
0x1801367f6  mov     al, r8b
0x1801367f9  sub     al, r10b
0x1801367fc  cmp     al, 9
0x1801367fe  ja      short loc_180136805
0x180136800  sub     r8b, r10b
0x180136803  jmp     short loc_180136826
0x180136805  lea     eax, [r8-61h]
0x180136809  cmp     al, r13b
0x18013680c  ja      short loc_180136814
0x18013680e  sub     r8b, 57h ; 'W'
0x180136812  jmp     short loc_180136826
0x180136814  lea     eax, [r8-41h]
0x180136818  cmp     al, r13b
0x18013681b  ja      short loc_180136823
0x18013681d  sub     r8b, 37h ; '7'
0x180136821  jmp     short loc_180136826
0x180136823  mov     r8b, 0FFh
0x180136826  cmp     dl, 0Fh
0x180136829  ja      loc_180136AAF
0x18013682f  cmp     r8b, 0Fh
0x180136833  ja      loc_180136AAF
0x180136839  shl     dl, 4
0x18013683c  add     dl, r8b
0x18013683f  mov     [rsi], dl
0x180136841  add     rsi, rdi
0x180136844  add     r9d, 2
0x180136848  jmp     loc_1801367B2
0x18013684d  lea     rax, [rbp+57h+hKey]
0x180136851  mov     r9d, 20019h; samDesired
0x180136857  xor     r8d, r8d; ulOptions
0x18013685a  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18013685f  lea     rdx, aGbg; "GBG"
0x180136866  mov     rcx, r14; hKey
0x180136869  call    cs:__imp_RegOpenKeyExA
0x180136870  nop     dword ptr [rax+rax+00h]
0x180136875  test    eax, eax
0x180136877  jnz     loc_180136982
0x18013687d  mov     rcx, [rbp+57h+hKey]; hKey
0x180136881  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180136885  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18013688a  lea     rdx, [rbp+57h+Class]; lpClass
0x18013688e  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180136893  xor     r9d, r9d; lpReserved
0x180136896  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18013689b  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1801368a0  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1801368a5  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1801368aa  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1801368af  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1801368b4  mov     [rbp+57h+cchClass], 9
0x1801368bb  call    cs:__imp_RegQueryInfoKeyA
0x1801368c2  nop     dword ptr [rax+rax+00h]
0x1801368c7  mov     rcx, [rbp+57h+hKey]; hKey
0x1801368cb  mov     ebx, eax
0x1801368cd  call    cs:__imp_RegCloseKey
0x1801368d4  nop     dword ptr [rax+rax+00h]
0x1801368d9  test    ebx, ebx
0x1801368db  jnz     loc_180136982
0x1801368e1  mov     r9d, r12d
0x1801368e4  mov     r10b, 30h ; '0'
0x1801368e7  cmp     r9d, 8
0x1801368eb  jnb     loc_180136982
0x1801368f1  mov     eax, r9d
0x1801368f4  mov     dl, [rbp+rax+57h+Class]
0x1801368f8  mov     al, dl
0x1801368fa  sub     al, r10b
0x1801368fd  cmp     al, 9
0x1801368ff  ja      short loc_180136906
0x180136901  sub     dl, r10b
0x180136904  jmp     short loc_180136922
0x180136906  lea     eax, [rdx-61h]
0x180136909  cmp     al, r13b
0x18013690c  ja      short loc_180136913
0x18013690e  sub     dl, 57h ; 'W'
0x180136911  jmp     short loc_180136922
0x180136913  lea     eax, [rdx-41h]
0x180136916  cmp     al, r13b
0x180136919  ja      short loc_180136920
0x18013691b  sub     dl, 37h ; '7'
0x18013691e  jmp     short loc_180136922
0x180136920  mov     dl, 0FFh
0x180136922  lea     eax, [r9+1]
0x180136926  mov     r8b, [rbp+rax+57h+Class]
0x18013692b  mov     al, r8b
0x18013692e  sub     al, r10b
0x180136931  cmp     al, 9
0x180136933  ja      short loc_18013693A
0x180136935  sub     r8b, r10b
0x180136938  jmp     short loc_18013695B
0x18013693a  lea     eax, [r8-61h]
0x18013693e  cmp     al, r13b
0x180136941  ja      short loc_180136949
0x180136943  sub     r8b, 57h ; 'W'
0x180136947  jmp     short loc_18013695B
0x180136949  lea     eax, [r8-41h]
0x18013694d  cmp     al, r13b
0x180136950  ja      short loc_180136958
0x180136952  sub     r8b, 37h ; '7'
0x180136956  jmp     short loc_18013695B
0x180136958  mov     r8b, 0FFh
0x18013695b  cmp     dl, 0Fh
0x18013695e  ja      loc_180136AAF
0x180136964  cmp     r8b, 0Fh
0x180136968  ja      loc_180136AAF
0x18013696e  shl     dl, 4
0x180136971  add     dl, r8b
0x180136974  mov     [rsi], dl
0x180136976  add     rsi, rdi
0x180136979  add     r9d, 2
0x18013697d  jmp     loc_1801368E7
0x180136982  lea     rax, [rbp+57h+hKey]
0x180136986  mov     r9d, 20019h; samDesired
0x18013698c  xor     r8d, r8d; ulOptions
0x18013698f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180136994  lea     rdx, aData; "Data"
0x18013699b  mov     rcx, r14; hKey
0x18013699e  call    cs:__imp_RegOpenKeyExA
0x1801369a5  nop     dword ptr [rax+rax+00h]
0x1801369aa  test    eax, eax
0x1801369ac  jnz     loc_180136AB4
0x1801369b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1801369b6  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1801369ba  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1801369bf  lea     rdx, [rbp+57h+Class]; lpClass
0x1801369c3  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1801369c8  xor     r9d, r9d; lpReserved
0x1801369cb  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1801369d0  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1801369d5  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x1801369da  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1801369df  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1801369e4  mov     [rsp+0E0h+phkResult], r12; lpcSubKeys
0x1801369e9  mov     [rbp+57h+cchClass], 9
0x1801369f0  call    cs:__imp_RegQueryInfoKeyA
0x1801369f7  nop     dword ptr [rax+rax+00h]
0x1801369fc  mov     rcx, [rbp+57h+hKey]; hKey
0x180136a00  mov     ebx, eax
0x180136a02  call    cs:__imp_RegCloseKey
  ... truncated ...
```
