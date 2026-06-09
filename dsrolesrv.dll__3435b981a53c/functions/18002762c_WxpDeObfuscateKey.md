# WxpDeObfuscateKey

- ea: `0x18002762c`
- end: `0x180027c2a`
- name: `WxpDeObfuscateKey`
- size: `1534`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800275a8`

## callees

- `0x18002748c`
- `0x18002762c`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800276da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800276a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800276a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002774b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180027892`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800279b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180027ad4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18002774b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180027892`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800279b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180027ad4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002786a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027a0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027bfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800276e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800277a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002786a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800278ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027a0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027b2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027bfa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18002779d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800278de`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800279ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180027b20`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x18002779d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800278de`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800279ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180027b20`

## pseudocode

```c
char __fastcall WxpDeObfuscateKey(HKEY hKey, __int64 a2)
{
  char v4; // si
  LSTATUS v5; // ebx
  const WCHAR *v6; // rdx
  HKEY v7; // rax
  __int128 *v8; // rdi
  LSTATUS v9; // ebx
  unsigned int i; // r9d
  CHAR v11; // dl
  char v12; // dl
  CHAR v14; // r8
  char v15; // r8
  LSTATUS v16; // ebx
  unsigned int j; // r9d
  CHAR v18; // dl
  char v19; // dl
  CHAR v20; // r8
  char v21; // r8
  LSTATUS v22; // ebx
  unsigned int k; // r9d
  CHAR v24; // dl
  char v25; // dl
  CHAR v26; // r8
  char v27; // r8
  LSTATUS v28; // ebx
  unsigned int m; // r9d
  CHAR v30; // dl
  char v31; // dl
  CHAR v32; // r8
  char v33; // r8
  __int64 n; // r8
  CHAR v35; // cl
  __int64 v36; // rdx
  DWORD cchClass; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  BYTE Data[4]; // [rsp+78h] [rbp-11h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-Dh] BYREF
  DWORD Type; // [rsp+80h] [rbp-9h] BYREF
  __int128 v43; // [rsp+88h] [rbp-1h] BYREF
  CHAR Class[16]; // [rsp+98h] [rbp+Fh] BYREF

  phkResult = 0;
  cchClass = 0;
  hKeya = 0;
  v4 = 1;
  v43 = 0;
  if ( hKey )
  {
    *(_DWORD *)Data = 0;
    Type = 4;
    cbData = 4;
    if ( !RegOpenKeyExW(hKey, L"Select", 0, 0x2001Fu, &hKeya) )
    {
      v5 = RegQueryValueExW(hKeya, L"Default", 0, &Type, Data, &cbData);
      RegCloseKey(hKeya);
      if ( !v5 )
      {
        v6 = L"ControlSet001\\Control\\Lsa";
        if ( *(_DWORD *)Data != 1 )
          v6 = L"ControlSet002\\Control\\Lsa";
        if ( !RegOpenKeyExW(hKey, v6, 0, 0x2001Fu, &hKeya) )
        {
          v7 = hKeya;
          goto LABEL_8;
        }
      }
    }
    return 0;
  }
  v7 = (HKEY)OpenLsaKey();
  hKeya = v7;
  if ( !v7 )
    return 0;
LABEL_8:
  v8 = &v43;
  if ( !RegOpenKeyExA(v7, "JD", 0, 0x20019u, &phkResult) )
  {
    cchClass = 9;
    v9 = RegQueryInfoKeyA(phkResult, Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    RegCloseKey(phkResult);
    if ( !v9 )
    {
      for ( i = 0; i < 8; i += 2 )
      {
        v11 = Class[i];
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
        v14 = Class[i + 1];
        if ( (unsigned __int8)(v14 - 48) > 9u )
        {
          if ( (unsigned __int8)(v14 - 97) > 5u )
          {
            if ( (unsigned __int8)(v14 - 65) > 5u )
              v15 = -1;
            else
              v15 = v14 - 55;
          }
          else
          {
            v15 = v14 - 87;
          }
        }
        else
        {
          v15 = v14 - 48;
        }
        if ( (unsigned __int8)v12 > 0xFu || (unsigned __int8)v15 > 0xFu )
        {
LABEL_31:
          RegCloseKey(hKeya);
          return 0;
        }
        *(_BYTE *)v8 = v15 + 16 * v12;
        v8 = (__int128 *)((char *)v8 + 1);
      }
    }
  }
  if ( !RegOpenKeyExA(hKeya, "Skew1", 0, 0x20019u, &phkResult) )
  {
    cchClass = 9;
    v16 = RegQueryInfoKeyA(phkResult, Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    RegCloseKey(phkResult);
    if ( !v16 )
    {
      for ( j = 0; j < 8; j += 2 )
      {
        v18 = Class[j];
        if ( (unsigned __int8)(v18 - 48) > 9u )
        {
          if ( (unsigned __int8)(v18 - 97) > 5u )
          {
            if ( (unsigned __int8)(v18 - 65) > 5u )
              v19 = -1;
            else
              v19 = v18 - 55;
          }
          else
          {
            v19 = v18 - 87;
          }
        }
        else
        {
          v19 = v18 - 48;
        }
        v20 = Class[j + 1];
        if ( (unsigned __int8)(v20 - 48) > 9u )
        {
          if ( (unsigned __int8)(v20 - 97) > 5u )
          {
            if ( (unsigned __int8)(v20 - 65) > 5u )
              v21 = -1;
            else
              v21 = v20 - 55;
          }
          else
          {
            v21 = v20 - 87;
          }
        }
        else
        {
          v21 = v20 - 48;
        }
        if ( (unsigned __int8)v19 > 0xFu || (unsigned __int8)v21 > 0xFu )
          goto LABEL_31;
        *(_BYTE *)v8 = v21 + 16 * v19;
        v8 = (__int128 *)((char *)v8 + 1);
      }
    }
  }
  if ( !RegOpenKeyExA(hKeya, "GBG", 0, 0x20019u, &phkResult) )
  {
    cchClass = 9;
    v22 = RegQueryInfoKeyA(phkResult, Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    RegCloseKey(phkResult);
    if ( !v22 )
    {
      for ( k = 0; k < 8; k += 2 )
      {
        v24 = Class[k];
        if ( (unsigned __int8)(v24 - 48) > 9u )
        {
          if ( (unsigned __int8)(v24 - 97) > 5u )
          {
            if ( (unsigned __int8)(v24 - 65) > 5u )
              v25 = -1;
            else
              v25 = v24 - 55;
          }
          else
          {
            v25 = v24 - 87;
          }
        }
        else
        {
          v25 = v24 - 48;
        }
        v26 = Class[k + 1];
        if ( (unsigned __int8)(v26 - 48) > 9u )
        {
          if ( (unsigned __int8)(v26 - 97) > 5u )
          {
            if ( (unsigned __int8)(v26 - 65) > 5u )
              v27 = -1;
            else
              v27 = v26 - 55;
          }
          else
          {
            v27 = v26 - 87;
          }
        }
        else
        {
          v27 = v26 - 48;
        }
        if ( (unsigned __int8)v25 > 0xFu || (unsigned __int8)v27 > 0xFu )
          goto LABEL_31;
        *(_BYTE *)v8 = v27 + 16 * v25;
        v8 = (__int128 *)((char *)v8 + 1);
      }
    }
  }
  if ( !RegOpenKeyExA(hKeya, "Data", 0, 0x20019u, &phkResult) )
  {
    cchClass = 9;
    v28 = RegQueryInfoKeyA(phkResult, Class, &cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
    RegCloseKey(phkResult);
    if ( !v28 )
    {
      for ( m = 0; m < 8; m += 2 )
      {
        v30 = Class[m];
        if ( (unsigned __int8)(v30 - 48) > 9u )
        {
          if ( (unsigned __int8)(v30 - 97) > 5u )
          {
            if ( (unsigned __int8)(v30 - 65) > 5u )
              v31 = -1;
            else
              v31 = v30 - 55;
          }
          else
          {
            v31 = v30 - 87;
          }
        }
        else
        {
          v31 = v30 - 48;
        }
        v32 = Class[m + 1];
        if ( (unsigned __int8)(v32 - 48) > 9u )
        {
          if ( (unsigned __int8)(v32 - 97) > 5u )
          {
            if ( (unsigned __int8)(v32 - 65) > 5u )
              v33 = -1;
            else
              v33 = v32 - 55;
          }
          else
          {
            v33 = v32 - 87;
          }
        }
        else
        {
          v33 = v32 - 48;
        }
        if ( (unsigned __int8)v31 > 0xFu || (unsigned __int8)v33 > 0xFu )
        {
          v4 = 0;
          goto LABEL_98;
        }
        *(_BYTE *)v8 = v33 + 16 * v31;
        v8 = (__int128 *)((char *)v8 + 1);
      }
    }
  }
  for ( n = 0; n != 16; ++n )
  {
    v35 = Class[n - 16];
    v36 = *((unsigned __int8 *)qword_180043580 + n);
    *(_BYTE *)(v36 + a2) = v35;
  }
LABEL_98:
  RegCloseKey(hKeya);
  return v4;
}

```

## disassembly

```asm
0x18002762c  mov     [rsp-8+arg_10], rbx
0x180027631  push    rbp
0x180027632  push    rsi
0x180027633  push    rdi
0x180027634  push    r12
0x180027636  push    r13
0x180027638  push    r14
0x18002763a  push    r15
0x18002763c  lea     rbp, [rsp-27h]
0x180027641  sub     rsp, 0B0h
0x180027648  mov     rax, cs:__security_cookie
0x18002764f  xor     rax, rsp
0x180027652  mov     [rbp+57h+var_38], rax
0x180027656  xor     r15d, r15d
0x180027659  xorps   xmm0, xmm0
0x18002765c  mov     [rbp+57h+var_70], r15
0x180027660  mov     r14, rdx
0x180027663  mov     [rbp+57h+cchClass], r15d
0x180027667  mov     rdi, rcx
0x18002766a  mov     [rbp+57h+hKey], r15
0x18002766e  lea     esi, [r15+1]
0x180027672  movups  [rbp+57h+var_58], xmm0
0x180027676  test    rcx, rcx
0x180027679  jz      loc_1800277D9
0x18002767f  lea     eax, [rsi+3]
0x180027682  mov     dword ptr [rbp+57h+Data], r15d
0x180027686  mov     [rbp+57h+Type], eax
0x180027689  lea     rdx, aSelect; "Select"
0x180027690  mov     [rbp+57h+cbData], eax
0x180027693  mov     r12d, 2001Fh
0x180027699  lea     rax, [rbp+57h+hKey]
0x18002769d  mov     r9d, r12d; samDesired
0x1800276a0  xor     r8d, r8d; ulOptions
0x1800276a3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800276a8  call    cs:__imp_RegOpenKeyExW
0x1800276ae  test    eax, eax
0x1800276b0  jnz     loc_1800277EB
0x1800276b6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800276ba  lea     rax, [rbp+57h+cbData]
0x1800276be  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800276c3  lea     r9, [rbp+57h+Type]; lpType
0x1800276c7  lea     rax, [rbp+57h+Data]
0x1800276cb  xor     r8d, r8d; lpReserved
0x1800276ce  lea     rdx, aDefault; "Default"
0x1800276d5  mov     [rsp+0E0h+phkResult], rax; lpData
0x1800276da  call    cs:__imp_RegQueryValueExW
0x1800276e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800276e4  mov     ebx, eax
0x1800276e6  call    cs:__imp_RegCloseKey
0x1800276ec  test    ebx, ebx
0x1800276ee  jnz     loc_1800277EB
0x1800276f4  xor     r8d, r8d; ulOptions
0x1800276f7  lea     rax, [rbp+57h+hKey]
0x1800276fb  lea     rdx, aControlset001C; "ControlSet001\\Control\\Lsa"
0x180027702  mov     r9d, r12d; samDesired
0x180027705  mov     rcx, rdi; hKey
0x180027708  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18002770d  cmp     dword ptr [rbp+57h+Data], esi
0x180027710  jz      short loc_180027719
0x180027712  lea     rdx, aControlset002C; "ControlSet002\\Control\\Lsa"
0x180027719  call    cs:__imp_RegOpenKeyExW
0x18002771f  test    eax, eax
0x180027721  jnz     loc_1800277EB
0x180027727  mov     rax, [rbp+57h+hKey]
0x18002772b  lea     rcx, [rbp+57h+var_70]
0x18002772f  mov     r9d, 20019h; samDesired
0x180027735  mov     [rsp+0E0h+phkResult], rcx; phkResult
0x18002773a  lea     rdx, aJd; "JD"
0x180027741  mov     rcx, rax; hKey
0x180027744  lea     rdi, [rbp+57h+var_58]
0x180027748  xor     r8d, r8d; ulOptions
0x18002774b  call    cs:__imp_RegOpenKeyExA
0x180027751  mov     r13b, 30h ; '0'
0x180027754  mov     r12b, 5
0x180027757  test    eax, eax
0x180027759  jnz     loc_180027875
0x18002775f  mov     rcx, [rbp+57h+var_70]; hKey
0x180027763  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180027767  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002776c  lea     rdx, [rbp+57h+Class]; lpClass
0x180027770  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180027775  xor     r9d, r9d; lpReserved
0x180027778  mov     [rsp+0E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002777d  mov     [rsp+0E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180027782  mov     [rsp+0E0h+lpcValues], r15; lpcValues
0x180027787  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18002778c  mov     [rsp+0E0h+lpcbData], r15; lpcbMaxSubKeyLen
0x180027791  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x180027796  mov     [rbp+57h+cchClass], 9
0x18002779d  call    cs:__imp_RegQueryInfoKeyA
0x1800277a3  mov     rcx, [rbp+57h+var_70]; hKey
0x1800277a7  mov     ebx, eax
0x1800277a9  call    cs:__imp_RegCloseKey
0x1800277af  test    ebx, ebx
0x1800277b1  jnz     loc_180027875
0x1800277b7  mov     r9d, r15d
0x1800277ba  cmp     r9d, 8
0x1800277be  jnb     loc_180027875
0x1800277c4  mov     eax, r9d
0x1800277c7  mov     dl, [rbp+rax+57h+Class]
0x1800277cb  mov     al, dl
0x1800277cd  sub     al, r13b
0x1800277d0  cmp     al, 9
0x1800277d2  ja      short loc_1800277F2
0x1800277d4  sub     dl, r13b
0x1800277d7  jmp     short loc_18002780E
0x1800277d9  call    OpenLsaKey
0x1800277de  mov     [rbp+57h+hKey], rax
0x1800277e2  test    rax, rax
0x1800277e5  jnz     loc_18002772B
0x1800277eb  xor     al, al
0x1800277ed  jmp     loc_180027C03
0x1800277f2  lea     eax, [rdx-61h]
0x1800277f5  cmp     al, r12b
0x1800277f8  ja      short loc_1800277FF
0x1800277fa  sub     dl, 57h ; 'W'
0x1800277fd  jmp     short loc_18002780E
0x1800277ff  lea     eax, [rdx-41h]
0x180027802  cmp     al, r12b
0x180027805  ja      short loc_18002780C
0x180027807  sub     dl, 37h ; '7'
0x18002780a  jmp     short loc_18002780E
0x18002780c  mov     dl, 0FFh
0x18002780e  lea     eax, [r9+1]
0x180027812  mov     r8b, [rbp+rax+57h+Class]
0x180027817  mov     al, r8b
0x18002781a  sub     al, r13b
0x18002781d  cmp     al, 9
0x18002781f  ja      short loc_180027826
0x180027821  sub     r8b, r13b
0x180027824  jmp     short loc_180027847
0x180027826  lea     eax, [r8-61h]
0x18002782a  cmp     al, r12b
0x18002782d  ja      short loc_180027835
0x18002782f  sub     r8b, 57h ; 'W'
0x180027833  jmp     short loc_180027847
0x180027835  lea     eax, [r8-41h]
0x180027839  cmp     al, r12b
0x18002783c  ja      short loc_180027844
0x18002783e  sub     r8b, 37h ; '7'
0x180027842  jmp     short loc_180027847
0x180027844  mov     r8b, 0FFh
0x180027847  cmp     dl, 0Fh
0x18002784a  ja      short loc_180027866
0x18002784c  cmp     r8b, 0Fh
0x180027850  ja      short loc_180027866
0x180027852  shl     dl, 4
0x180027855  add     dl, r8b
0x180027858  mov     [rdi], dl
0x18002785a  add     rdi, rsi
0x18002785d  add     r9d, 2
0x180027861  jmp     loc_1800277BA
0x180027866  mov     rcx, [rbp+57h+hKey]; hKey
0x18002786a  call    cs:__imp_RegCloseKey
0x180027870  jmp     loc_1800277EB
0x180027875  mov     rcx, [rbp+57h+hKey]; hKey
0x180027879  lea     rax, [rbp+57h+var_70]
0x18002787d  mov     r9d, 20019h; samDesired
0x180027883  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180027888  xor     r8d, r8d; ulOptions
0x18002788b  lea     rdx, aSkew1; "Skew1"
0x180027892  call    cs:__imp_RegOpenKeyExA
0x180027898  test    eax, eax
0x18002789a  jnz     loc_180027996
0x1800278a0  mov     rcx, [rbp+57h+var_70]; hKey
0x1800278a4  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800278a8  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800278ad  lea     rdx, [rbp+57h+Class]; lpClass
0x1800278b1  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800278b6  xor     r9d, r9d; lpReserved
0x1800278b9  mov     [rsp+0E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800278be  mov     [rsp+0E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800278c3  mov     [rsp+0E0h+lpcValues], r15; lpcValues
0x1800278c8  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800278cd  mov     [rsp+0E0h+lpcbData], r15; lpcbMaxSubKeyLen
0x1800278d2  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x1800278d7  mov     [rbp+57h+cchClass], 9
0x1800278de  call    cs:__imp_RegQueryInfoKeyA
0x1800278e4  mov     rcx, [rbp+57h+var_70]; hKey
0x1800278e8  mov     ebx, eax
0x1800278ea  call    cs:__imp_RegCloseKey
0x1800278f0  test    ebx, ebx
0x1800278f2  jnz     loc_180027996
0x1800278f8  mov     r9d, r15d
0x1800278fb  cmp     r9d, 8
0x1800278ff  jnb     loc_180027996
0x180027905  mov     eax, r9d
0x180027908  mov     dl, [rbp+rax+57h+Class]
0x18002790c  mov     al, dl
0x18002790e  sub     al, r13b
0x180027911  cmp     al, 9
0x180027913  ja      short loc_18002791A
0x180027915  sub     dl, r13b
0x180027918  jmp     short loc_180027936
0x18002791a  lea     eax, [rdx-61h]
0x18002791d  cmp     al, r12b
0x180027920  ja      short loc_180027927
0x180027922  sub     dl, 57h ; 'W'
0x180027925  jmp     short loc_180027936
0x180027927  lea     eax, [rdx-41h]
0x18002792a  cmp     al, r12b
0x18002792d  ja      short loc_180027934
0x18002792f  sub     dl, 37h ; '7'
0x180027932  jmp     short loc_180027936
0x180027934  mov     dl, 0FFh
0x180027936  lea     eax, [r9+1]
0x18002793a  mov     r8b, [rbp+rax+57h+Class]
0x18002793f  mov     al, r8b
0x180027942  sub     al, r13b
0x180027945  cmp     al, 9
0x180027947  ja      short loc_18002794E
0x180027949  sub     r8b, r13b
0x18002794c  jmp     short loc_18002796F
0x18002794e  lea     eax, [r8-61h]
0x180027952  cmp     al, r12b
0x180027955  ja      short loc_18002795D
0x180027957  sub     r8b, 57h ; 'W'
0x18002795b  jmp     short loc_18002796F
0x18002795d  lea     eax, [r8-41h]
0x180027961  cmp     al, r12b
0x180027964  ja      short loc_18002796C
0x180027966  sub     r8b, 37h ; '7'
0x18002796a  jmp     short loc_18002796F
0x18002796c  mov     r8b, 0FFh
0x18002796f  cmp     dl, 0Fh
0x180027972  ja      loc_180027866
0x180027978  cmp     r8b, 0Fh
0x18002797c  ja      loc_180027866
0x180027982  shl     dl, 4
0x180027985  add     dl, r8b
0x180027988  mov     [rdi], dl
0x18002798a  add     rdi, rsi
0x18002798d  add     r9d, 2
0x180027991  jmp     loc_1800278FB
0x180027996  mov     rcx, [rbp+57h+hKey]; hKey
0x18002799a  lea     rax, [rbp+57h+var_70]
0x18002799e  mov     r9d, 20019h; samDesired
0x1800279a4  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800279a9  xor     r8d, r8d; ulOptions
0x1800279ac  lea     rdx, aGbg; "GBG"
0x1800279b3  call    cs:__imp_RegOpenKeyExA
0x1800279b9  test    eax, eax
0x1800279bb  jnz     loc_180027AB7
0x1800279c1  mov     rcx, [rbp+57h+var_70]; hKey
0x1800279c5  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x1800279c9  mov     [rsp+0E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800279ce  lea     rdx, [rbp+57h+Class]; lpClass
0x1800279d2  mov     [rsp+0E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800279d7  xor     r9d, r9d; lpReserved
0x1800279da  mov     [rsp+0E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800279df  mov     [rsp+0E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800279e4  mov     [rsp+0E0h+lpcValues], r15; lpcValues
0x1800279e9  mov     [rsp+0E0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800279ee  mov     [rsp+0E0h+lpcbData], r15; lpcbMaxSubKeyLen
0x1800279f3  mov     [rsp+0E0h+phkResult], r15; lpcSubKeys
0x1800279f8  mov     [rbp+57h+cchClass], 9
0x1800279ff  call    cs:__imp_RegQueryInfoKeyA
0x180027a05  mov     rcx, [rbp+57h+var_70]; hKey
0x180027a09  mov     ebx, eax
0x180027a0b  call    cs:__imp_RegCloseKey
0x180027a11  test    ebx, ebx
0x180027a13  jnz     loc_180027AB7
0x180027a19  mov     r9d, r15d
0x180027a1c  cmp     r9d, 8
0x180027a20  jnb     loc_180027AB7
0x180027a26  mov     eax, r9d
0x180027a29  mov     dl, [rbp+rax+57h+Class]
0x180027a2d  mov     al, dl
0x180027a2f  sub     al, r13b
0x180027a32  cmp     al, 9
0x180027a34  ja      short loc_180027A3B
0x180027a36  sub     dl, r13b
0x180027a39  jmp     short loc_180027A57
0x180027a3b  lea     eax, [rdx-61h]
0x180027a3e  cmp     al, r12b
0x180027a41  ja      short loc_180027A48
0x180027a43  sub     dl, 57h ; 'W'
0x180027a46  jmp     short loc_180027A57
0x180027a48  lea     eax, [rdx-41h]
0x180027a4b  cmp     al, r12b
0x180027a4e  ja      short loc_180027A55
0x180027a50  sub     dl, 37h ; '7'
0x180027a53  jmp     short loc_180027A57
0x180027a55  mov     dl, 0FFh
0x180027a57  lea     eax, [r9+1]
0x180027a5b  mov     r8b, [rbp+rax+57h+Class]
0x180027a60  mov     al, r8b
0x180027a63  sub     al, r13b
0x180027a66  cmp     al, 9
0x180027a68  ja      short loc_180027A6F
0x180027a6a  sub     r8b, r13b
0x180027a6d  jmp     short loc_180027A90
0x180027a6f  lea     eax, [r8-61h]
0x180027a73  cmp     al, r12b
0x180027a76  ja      short loc_180027A7E
0x180027a78  sub     r8b, 57h ; 'W'
0x180027a7c  jmp     short loc_180027A90
0x180027a7e  lea     eax, [r8-41h]
0x180027a82  cmp     al, r12b
0x180027a85  ja      short loc_180027A8D
  ... truncated ...
```
