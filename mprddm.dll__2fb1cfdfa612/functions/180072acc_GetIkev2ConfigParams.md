# GetIkev2ConfigParams

- ea: `0x180072acc`
- end: `0x180073393`
- name: `GetIkev2ConfigParams`
- size: `2247`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004950`

## callees

- `0x180072958`
- `0x1800729dc`
- `0x180072acc`
- `0x18007360c`
- `0x180073634`
- `0x1800737a0`
- `0x18008c5f2`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180072d36`
- `KERNEL32!GetProcessHeap` at `0x180072d76`
- `KERNEL32!GetProcessHeap` at `0x180072e12`
- `KERNEL32!GetProcessHeap` at `0x18007310a`
- `KERNEL32!GetProcessHeap` at `0x180073150`
- `KERNEL32!GetProcessHeap` at `0x18007320a`
- `KERNEL32!GetProcessHeap` at `0x18007332e`
- `KERNEL32!GetProcessHeap` at `0x18007334b`
- `KERNEL32!GetProcessHeap` at `0x180072d36`
- `KERNEL32!GetProcessHeap` at `0x180072d76`
- `KERNEL32!GetProcessHeap` at `0x180072e12`
- `KERNEL32!GetProcessHeap` at `0x18007310a`
- `KERNEL32!GetProcessHeap` at `0x180073150`
- `KERNEL32!GetProcessHeap` at `0x18007320a`
- `KERNEL32!GetProcessHeap` at `0x18007332e`
- `KERNEL32!GetProcessHeap` at `0x18007334b`
- `KERNEL32!HeapAlloc` at `0x180072d44`
- `KERNEL32!HeapAlloc` at `0x180072d84`
- `KERNEL32!HeapAlloc` at `0x180072e20`
- `KERNEL32!HeapAlloc` at `0x180073118`
- `KERNEL32!HeapAlloc` at `0x18007315e`
- `KERNEL32!HeapAlloc` at `0x180073218`
- `KERNEL32!HeapAlloc` at `0x180072d44`
- `KERNEL32!HeapAlloc` at `0x180072d84`
- `KERNEL32!HeapAlloc` at `0x180072e20`
- `KERNEL32!HeapAlloc` at `0x180073118`
- `KERNEL32!HeapAlloc` at `0x18007315e`
- `KERNEL32!HeapAlloc` at `0x180073218`
- `KERNEL32!GetLastError` at `0x180072d56`
- `KERNEL32!GetLastError` at `0x18007312a`
- `KERNEL32!GetLastError` at `0x180072d56`
- `KERNEL32!GetLastError` at `0x18007312a`
- `KERNEL32!HeapFree` at `0x18007333c`
- `KERNEL32!HeapFree` at `0x180073359`
- `KERNEL32!HeapFree` at `0x18007333c`
- `KERNEL32!HeapFree` at `0x180073359`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180072cfe`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800730c5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180072cfe`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800730c5`
- `ADVAPI32!RegOpenKeyExW` at `0x180072ca0`
- `ADVAPI32!RegOpenKeyExW` at `0x180072f00`
- `ADVAPI32!RegOpenKeyExW` at `0x180073053`
- `ADVAPI32!RegOpenKeyExW` at `0x180072ca0`
- `ADVAPI32!RegOpenKeyExW` at `0x180072f00`
- `ADVAPI32!RegOpenKeyExW` at `0x180073053`
- `ADVAPI32!RegQueryValueExW` at `0x180072c13`
- `ADVAPI32!RegQueryValueExW` at `0x180072c5d`
- `ADVAPI32!RegQueryValueExW` at `0x180072fba`
- `ADVAPI32!RegQueryValueExW` at `0x180072c13`
- `ADVAPI32!RegQueryValueExW` at `0x180072c5d`
- `ADVAPI32!RegQueryValueExW` at `0x180072fba`
- `ADVAPI32!RegCloseKey` at `0x180072f2a`
- `ADVAPI32!RegCloseKey` at `0x180073368`
- `ADVAPI32!RegCloseKey` at `0x180073377`
- `ADVAPI32!RegCloseKey` at `0x180072f2a`
- `ADVAPI32!RegCloseKey` at `0x180073368`
- `ADVAPI32!RegCloseKey` at `0x180073377`
- `ADVAPI32!RegEnumKeyW` at `0x180072db1`
- `ADVAPI32!RegEnumKeyW` at `0x1800731a2`
- `ADVAPI32!RegEnumKeyW` at `0x180072db1`
- `ADVAPI32!RegEnumKeyW` at `0x1800731a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072df5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072e5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800731e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073253`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800732a5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072df5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180072e5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800731e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073253`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800732a5`

## string_xrefs

- `0x180072b61`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall GetIkev2ConfigParams(HKEY hkey, char a2, __int64 a3, unsigned int a4)
{
  WCHAR *v4; // r14
  DWORD LastError; // ebx
  bool v9; // cf
  unsigned int i; // edi
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  DWORD v13; // edx
  unsigned int v14; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v16; // ebx
  HANDLE v17; // rax
  DWORD v18; // edi
  DWORD *v19; // rsi
  DWORD v20; // ebx
  HANDLE v21; // rax
  void *v22; // rax
  void *v23; // r14
  __int128 v24; // xmm1
  HKEY v25; // rcx
  LSTATUS v26; // eax
  void *v27; // rax
  DWORD Binary; // eax
  LSTATUS v29; // eax
  DWORD v30; // eax
  LSTATUS v31; // eax
  DWORD v32; // eax
  unsigned int v33; // edx
  unsigned int v34; // ebx
  HANDLE v35; // rax
  WCHAR *v36; // r15
  DWORD v37; // ebx
  HANDLE v38; // rax
  char *v39; // rax
  char *v40; // rsi
  DWORD v41; // edi
  DWORD *v42; // rsi
  unsigned int v43; // ebx
  HANDLE v44; // rax
  void *v45; // rax
  HANDLE v46; // rax
  void *v47; // rdi
  HANDLE v48; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD v53; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v54; // [rsp+70h] [rbp-90h] BYREF
  DWORD pdwType; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v56; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v60; // [rsp+98h] [rbp-68h]
  WCHAR *v61; // [rsp+A0h] [rbp-60h]
  LPVOID v62; // [rsp+A8h] [rbp-58h]
  LPVOID lpMem; // [rsp+B0h] [rbp-50h]
  __int128 v64; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v65; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpValueName; // [rsp+E0h] [rbp-20h]
  LPBYTE v67[17]; // [rsp+E8h] [rbp-18h]
  size_t Size; // [rsp+188h] [rbp+88h] BYREF

  v4 = 0;
  phkResult = 0;
  lpValueName = L"idleTimeout";
  hKey = 0;
  v67[0] = (LPBYTE)&v64;
  cSubKeys = 0;
  v67[1] = (LPBYTE)L"networkBlackoutTime";
  v54 = 0;
  v67[2] = (LPBYTE)&v64 + 4;
  v67[3] = (LPBYTE)L"saLifeTime";
  v67[4] = (LPBYTE)&v64 + 8;
  v67[5] = (LPBYTE)L"saDataSize";
  v67[6] = (LPBYTE)&v64 + 12;
  v67[7] = (LPBYTE)L"ConfigOptions";
  v67[8] = (LPBYTE)&v65;
  v61 = 0;
  lpMem = 0;
  v62 = 0;
  v60 = 0;
  cbData = 0;
  Type = 0;
  v64 = 0;
  v65 = 0;
  switch ( a2 )
  {
    case 1:
      v9 = a4 < 0x20;
LABEL_8:
      if ( v9 )
      {
LABEL_9:
        LastError = 87;
        goto LABEL_97;
      }
      for ( i = 0; i < 5; ++i )
      {
        cbData = 4;
        Type = 4;
        LastError = RegQueryValueExW(hkey, (LPCWSTR)v67[2 * i - 1], 0, &Type, v67[2 * i], &cbData);
        if ( LastError )
          goto LABEL_97;
      }
      if ( a2 >= 5 )
      {
        cbData = 4;
        Type = 4;
        v11 = RegQueryValueExW(hkey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 96), &cbData);
        LastError = v11;
        if ( v11 )
        {
          if ( v11 != 2 )
            goto LABEL_97;
          *(_DWORD *)(a3 + 96) = 28800;
        }
      }
      cbMaxSubKeyLen = 0;
      pdwType = 3;
      v12 = RegOpenKeyExW(hkey, L"AllowedTrustedRootCerts", 0, 0x20019u, &phkResult);
      LastError = v12;
      if ( v12 )
      {
        if ( v12 != 2 )
          goto LABEL_97;
        LastError = 0;
        goto LABEL_41;
      }
      LastError = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( LastError )
        goto LABEL_97;
      if ( cSubKeys )
      {
        v13 = -1;
        if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
          v13 = cbMaxSubKeyLen + 1;
        if ( 2 * (unsigned __int64)v13 > 0xFFFFFFFF )
          goto LABEL_44;
        v14 = 2 * v13;
        ProcessHeap = GetProcessHeap();
        v61 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v14);
        v4 = v61;
        if ( !v61 )
        {
LABEL_29:
          LastError = GetLastError();
          goto LABEL_96;
        }
        if ( 16 * (unsigned __int64)cSubKeys > 0xFFFFFFFF )
        {
LABEL_44:
          LastError = -2147024362;
          goto LABEL_97;
        }
        v16 = 16 * cSubKeys;
        v17 = GetProcessHeap();
        v62 = HeapAlloc(v17, 0, v16);
        if ( !v62 )
          goto LABEL_29;
        LastError = 0;
        v18 = 0;
        if ( cSubKeys )
        {
          do
          {
            LastError = RegEnumKeyW(phkResult, v18, v4, cbMaxSubKeyLen + 1);
            if ( LastError )
              goto LABEL_97;
            v19 = (DWORD *)((char *)v62 + 16 * v18);
            LastError = RegGetValueW(phkResult, v4, L"TrustedRootCert", 8u, &pdwType, 0, v19);
            if ( LastError )
              goto LABEL_97;
            if ( pdwType != 3 )
              goto LABEL_9;
            v20 = *v19;
            v21 = GetProcessHeap();
            v22 = HeapAlloc(v21, 0, v20);
            *((_QWORD *)v19 + 1) = v22;
            if ( !v22 )
              goto LABEL_29;
            LastError = RegGetValueW(phkResult, v4, L"TrustedRootCert", 8u, &pdwType, v22, v19);
            if ( LastError )
              goto LABEL_97;
            if ( pdwType != 3 )
              goto LABEL_9;
          }
          while ( ++v18 < cSubKeys );
        }
      }
      DWORD1(v65) = cSubKeys;
      *((_QWORD *)&v65 + 1) = v62;
LABEL_41:
      v23 = 0;
      v24 = v65;
      *(_OWORD *)a3 = v64;
      *(_OWORD *)(a3 + 16) = v24;
      if ( a2 >= 2 )
      {
        v23 = (void *)MprCommonAlloc(24);
        if ( !v23 )
        {
          v4 = v61;
          LastError = 8;
          goto LABEL_97;
        }
        v25 = 0;
        v56 = 0;
        if ( hkey )
        {
          v26 = RegOpenKeyExW(hkey, L"IKEv2CustomPolicy", 0, 0x20019u, &v56);
          v25 = v56;
          LastError = v26;
          if ( !v26 )
          {
            GetCustomPolicyRegParams(v56, v23);
            v25 = v56;
          }
        }
        else
        {
          LastError = 87;
        }
        if ( v25 )
          RegCloseKey(v25);
        if ( LastError )
        {
          if ( LastError != 2 )
            goto LABEL_94;
          v27 = 0;
        }
        else
        {
          v27 = v23;
          v23 = 0;
        }
        *(_QWORD *)(a3 + 56) = v27;
        Binary = RegGetBinary(hkey, L"MachineCertificateName", a3 + 32, a3 + 40);
        LastError = Binary;
        if ( Binary )
        {
          if ( Binary != 2 )
            goto LABEL_93;
          *(_DWORD *)(a3 + 32) = 0;
          *(_QWORD *)(a3 + 40) = 0;
        }
        cbData = 4;
        Type = 4;
        v29 = RegQueryValueExW(hkey, L"EncryptionType", 0, &Type, (LPBYTE)(a3 + 48), &cbData);
        LastError = v29;
        if ( v29 )
        {
          if ( v29 != 2 )
            goto LABEL_93;
          LastError = 0;
          *(_DWORD *)(a3 + 48) = 2;
        }
      }
      if ( a2 >= 3 )
      {
        LODWORD(v56) = 0;
        v53 = 1;
        LODWORD(Size) = 0;
        v30 = RegGetBinary(hkey, L"MachineCertificateHash", a3 + 80, a3 + 88);
        LastError = v30;
        if ( v30 )
        {
          if ( v30 != 2 )
            goto LABEL_93;
          *(_DWORD *)(a3 + 80) = 0;
          *(_QWORD *)(a3 + 88) = 0;
        }
        v31 = RegOpenKeyExW(hkey, L"AllowedCertEku", 0, 0x20019u, &hKey);
        LastError = v31;
        if ( v31 )
        {
          if ( v31 == 2 )
            LastError = 0;
          goto LABEL_93;
        }
        LastError = RegQueryInfoKeyW(hKey, 0, 0, 0, &v54, (LPDWORD)&v56, 0, 0, 0, 0, 0, 0);
        if ( LastError )
          goto LABEL_93;
        v32 = v54;
        if ( v54 )
        {
          v33 = -1;
          if ( (int)v56 + 1 >= (unsigned int)v56 )
            v33 = (_DWORD)v56 + 1;
          if ( 2 * (unsigned __int64)v33 > 0xFFFFFFFF )
          {
            LODWORD(Size) = -1;
            LastError = -2147024362;
            goto LABEL_93;
          }
          v34 = 2 * v33;
          LODWORD(Size) = 2 * v33;
          v35 = GetProcessHeap();
          lpMem = HeapAlloc(v35, 0, v34);
          v36 = (WCHAR *)lpMem;
          if ( !lpMem )
            goto LABEL_74;
          if ( 16 * (unsigned __int64)v54 > 0xFFFFFFFF )
          {
            LODWORD(Size) = -1;
            LastError = -2147024362;
            goto LABEL_93;
          }
          v37 = 16 * v54;
          LODWORD(Size) = 16 * v54;
          v38 = GetProcessHeap();
          v39 = (char *)HeapAlloc(v38, 0, v37);
          v60 = v39;
          v40 = v39;
          if ( !v39 )
          {
LABEL_74:
            LastError = GetLastError();
            goto LABEL_93;
          }
          memset_0(v39, 0, (unsigned int)Size);
          v32 = v54;
          v41 = 0;
          for ( LastError = 0; v41 < v54; v40 = (char *)v60 )
          {
            LastError = RegEnumKeyW(hKey, v41, v36, (_DWORD)v56 + 1);
            if ( LastError )
              goto LABEL_93;
            v42 = (DWORD *)&v40[16 * v41];
            LastError = RegGetValueW(hKey, v36, L"TrustedEku", 2u, &v53, 0, v42);
            if ( LastError )
              goto LABEL_93;
            if ( v53 != 1 )
              goto LABEL_88;
            LODWORD(Size) = *v42;
            v43 = Size;
            v44 = GetProcessHeap();
            v45 = HeapAlloc(v44, 0, v43);
            *((_QWORD *)v42 + 1) = v45;
            if ( !v45 )
              goto LABEL_74;
            LastError = RegGetValueW(hKey, v36, L"TrustedEku", 2u, &v53, v45, v42);
            if ( LastError )
              goto LABEL_93;
            if ( v53 != 1 )
              goto LABEL_88;
            LODWORD(Size) = 4;
            LastError = RegGetValueW(hKey, v36, L"IsEkuOID", 0x10u, &v53, v42 + 1, (LPDWORD)&Size);
            if ( LastError )
              goto LABEL_93;
            if ( v53 != 4 )
            {
LABEL_88:
              LastError = 87;
              goto LABEL_93;
            }
            v32 = v54;
            ++v41;
          }
        }
        else
        {
          v40 = (char *)v60;
        }
        *(_DWORD *)(a3 + 64) = v32;
        *(_QWORD *)(a3 + 72) = v40;
      }
LABEL_93:
      if ( !v23 )
      {
LABEL_95:
        v4 = v61;
LABEL_96:
        if ( !LastError )
          goto LABEL_98;
        goto LABEL_97;
      }
LABEL_94:
      MprCommonFree(v23);
      goto LABEL_95;
    case 2:
      v9 = a4 < 0x40;
      goto LABEL_8;
    case 3:
    case 4:
      v9 = a4 < 0x60;
      goto LABEL_8;
    case 5:
      v9 = a4 < 0x68;
      goto LABEL_8;
  }
  LastError = 50;
LABEL_97:
  FreeEkus(v62);
  FreeEkus(v60);
LABEL_98:
  if ( v4 )
  {
    v46 = GetProcessHeap();
    HeapFree(v46, 0, v4);
  }
  v47 = lpMem;
  if ( lpMem )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, v47);
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x180072acc  push    rbp
0x180072ace  push    rbx
0x180072acf  push    rsi
0x180072ad0  push    rdi
0x180072ad1  push    r12
0x180072ad3  push    r13
0x180072ad5  push    r14
0x180072ad7  push    r15
0x180072ad9  lea     rbp, [rsp-38h]
0x180072ade  sub     rsp, 138h
0x180072ae5  xor     r14d, r14d
0x180072ae8  movsx   r12d, dl
0x180072aec  lea     rax, aIdletimeout; "idleTimeout"
0x180072af3  mov     [rbp+70h+phkResult], 0
0x180072afb  mov     [rbp+70h+lpValueName], rax
0x180072aff  mov     r15, rcx
0x180072b02  lea     rax, [rbp+70h+var_B8]
0x180072b06  mov     [rbp+70h+hKey], 0
0x180072b0e  mov     [rbp+70h+var_88], rax
0x180072b12  xorps   xmm0, xmm0
0x180072b15  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x180072b1c  mov     [rsp+170h+cSubKeys], 0
0x180072b24  mov     [rbp+70h+var_80], rax
0x180072b28  mov     ecx, r12d
0x180072b2b  mov     [rsp+170h+var_100], 0
0x180072b33  lea     rax, [rbp+70h+var_B8+4]
0x180072b37  mov     [rbp+70h+var_78], rax
0x180072b3b  lea     rax, aSalifetime; "saLifeTime"
0x180072b42  mov     [rbp+70h+var_70], rax
0x180072b46  lea     rax, [rbp+70h+var_B8+8]
0x180072b4a  mov     [rbp+70h+var_68], rax
0x180072b4e  lea     rax, aSadatasize; "saDataSize"
0x180072b55  mov     [rbp+70h+var_60], rax
0x180072b59  lea     rax, [rbp+70h+var_B8+0Ch]
0x180072b5d  mov     [rbp+70h+var_58], rax
0x180072b61  lea     rax, aConfigoptions; "ConfigOptions"
0x180072b68  mov     [rbp+70h+var_50], rax
0x180072b6c  lea     rax, [rbp+70h+var_A8]
0x180072b70  mov     [rbp+70h+var_48], rax
0x180072b74  mov     r13, r8
0x180072b77  mov     [rbp+70h+var_D0], r14
0x180072b7b  mov     [rbp+70h+lpMem], r14
0x180072b7f  mov     [rbp+70h+var_C8], r14
0x180072b83  mov     [rbp+70h+var_D8], r14
0x180072b87  mov     [rsp+170h+cbData], r14d
0x180072b8c  mov     [rsp+170h+Type], r14d
0x180072b91  movups  [rbp+70h+var_B8], xmm0
0x180072b95  movups  [rbp+70h+var_A8], xmm0
0x180072b99  sub     ecx, 1
0x180072b9c  jz      short loc_180072BD7
0x180072b9e  sub     ecx, 1
0x180072ba1  jz      short loc_180072BD1
0x180072ba3  sub     ecx, 1
0x180072ba6  jz      short loc_180072BCB
0x180072ba8  sub     ecx, 1
0x180072bab  jz      short loc_180072BCB
0x180072bad  cmp     ecx, 1
0x180072bb0  jz      short loc_180072BBB
0x180072bb2  lea     ebx, [r14+32h]
0x180072bb6  jmp     loc_18007330F
0x180072bbb  cmp     r9d, 68h ; 'h'
0x180072bbf  jnb     short loc_180072BDD
0x180072bc1  mov     ebx, 57h ; 'W'
0x180072bc6  jmp     loc_18007330F
0x180072bcb  cmp     r9d, 60h ; '`'
0x180072bcf  jmp     short loc_180072BBF
0x180072bd1  cmp     r9d, 40h ; '@'
0x180072bd5  jmp     short loc_180072BBF
0x180072bd7  cmp     r9d, 20h ; ' '
0x180072bdb  jmp     short loc_180072BBF
0x180072bdd  xor     edi, edi
0x180072bdf  lea     esi, [rdi+4]
0x180072be2  lea     rax, [rsp+170h+cbData]
0x180072be7  mov     edx, edi
0x180072be9  add     rdx, rdx
0x180072bec  mov     [rsp+170h+lpcbData], rax; lpcbData
0x180072bf1  lea     r9, [rsp+170h+Type]; lpType
0x180072bf6  mov     [rsp+170h+cbData], esi
0x180072bfa  xor     r8d, r8d; lpReserved
0x180072bfd  mov     [rsp+170h+Type], esi
0x180072c01  mov     rcx, r15; hKey
0x180072c04  mov     rax, [rbp+rdx*8+70h+var_88]
0x180072c09  mov     rdx, [rbp+rdx*8+70h+lpValueName]; lpValueName
0x180072c0e  mov     [rsp+170h+lpData], rax; lpData
0x180072c13  call    cs:__imp_RegQueryValueExW
0x180072c19  mov     ebx, eax
0x180072c1b  test    eax, eax
0x180072c1d  jnz     loc_18007330F
0x180072c23  inc     edi
0x180072c25  cmp     edi, 5
0x180072c28  jb      short loc_180072BE2
0x180072c2a  cmp     r12b, 5
0x180072c2e  jl      short loc_180072C78
0x180072c30  lea     rax, [rsp+170h+cbData]
0x180072c35  mov     [rsp+170h+cbData], esi
0x180072c39  mov     [rsp+170h+lpcbData], rax; lpcbData
0x180072c3e  lea     rdi, [r13+60h]
0x180072c42  lea     r9, [rsp+170h+Type]; lpType
0x180072c47  mov     [rsp+170h+lpData], rdi; lpData
0x180072c4c  xor     r8d, r8d; lpReserved
0x180072c4f  mov     [rsp+170h+Type], esi
0x180072c53  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180072c5a  mov     rcx, r15; hKey
0x180072c5d  call    cs:__imp_RegQueryValueExW
0x180072c63  mov     ebx, eax
0x180072c65  test    eax, eax
0x180072c67  jz      short loc_180072C78
0x180072c69  cmp     eax, 2
0x180072c6c  jnz     loc_18007330F
0x180072c72  mov     dword ptr [rdi], 7080h
0x180072c78  lea     rax, [rbp+70h+phkResult]
0x180072c7c  mov     [rbp+70h+cbMaxSubKeyLen], r14d
0x180072c80  mov     r9d, 20019h; samDesired
0x180072c86  mov     [rsp+170h+lpData], rax; phkResult
0x180072c8b  xor     r8d, r8d; ulOptions
0x180072c8e  mov     [rsp+170h+pdwType], 3
0x180072c96  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x180072c9d  mov     rcx, r15; hKey
0x180072ca0  call    cs:__imp_RegOpenKeyExW
0x180072ca6  mov     ebx, eax
0x180072ca8  mov     edi, 0FFFFFFFFh
0x180072cad  test    eax, eax
0x180072caf  jz      short loc_180072CC1
0x180072cb1  cmp     eax, 2
0x180072cb4  jnz     loc_18007330F
0x180072cba  xor     ebx, ebx
0x180072cbc  jmp     loc_180072E91
0x180072cc1  mov     rcx, [rbp+70h+phkResult]; hKey
0x180072cc5  lea     rax, [rbp+70h+cbMaxSubKeyLen]
0x180072cc9  mov     [rsp+170h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180072cce  xor     r9d, r9d; lpReserved
0x180072cd1  mov     [rsp+170h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180072cd6  xor     r8d, r8d; lpcchClass
0x180072cd9  mov     [rsp+170h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180072cde  xor     edx, edx; lpClass
0x180072ce0  mov     [rsp+170h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180072ce5  mov     [rsp+170h+lpcValues], r14; lpcValues
0x180072cea  mov     [rsp+170h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180072cef  mov     [rsp+170h+lpcbData], rax; lpcbMaxSubKeyLen
0x180072cf4  lea     rax, [rsp+170h+cSubKeys]
0x180072cf9  mov     [rsp+170h+lpData], rax; lpcSubKeys
0x180072cfe  call    cs:__imp_RegQueryInfoKeyW
0x180072d04  mov     ebx, eax
0x180072d06  test    eax, eax
0x180072d08  jnz     loc_18007330F
0x180072d0e  cmp     [rsp+170h+cSubKeys], r14d
0x180072d13  jz      loc_180072E82
0x180072d19  mov     eax, [rbp+70h+cbMaxSubKeyLen]
0x180072d1c  mov     edx, edi
0x180072d1e  lea     ecx, [rax+1]
0x180072d21  cmp     ecx, eax
0x180072d23  cmovnb  edx, ecx
0x180072d26  mov     eax, edx
0x180072d28  add     rax, rax
0x180072d2b  cmp     rax, rdi
0x180072d2e  ja      loc_180072ECD
0x180072d34  mov     ebx, eax
0x180072d36  call    cs:__imp_GetProcessHeap
0x180072d3c  mov     r8d, ebx; dwBytes
0x180072d3f  xor     edx, edx; dwFlags
0x180072d41  mov     rcx, rax; hHeap
0x180072d44  call    cs:__imp_HeapAlloc
0x180072d4a  mov     [rbp+70h+var_D0], rax
0x180072d4e  mov     r14, rax
0x180072d51  test    rax, rax
0x180072d54  jnz     short loc_180072D63
0x180072d56  call    cs:__imp_GetLastError
0x180072d5c  mov     ebx, eax
0x180072d5e  jmp     loc_18007330B
0x180072d63  mov     eax, [rsp+170h+cSubKeys]
0x180072d67  shl     rax, 4
0x180072d6b  cmp     rax, rdi
0x180072d6e  ja      loc_180072ECD
0x180072d74  mov     ebx, eax
0x180072d76  call    cs:__imp_GetProcessHeap
0x180072d7c  mov     r8d, ebx; dwBytes
0x180072d7f  xor     edx, edx; dwFlags
0x180072d81  mov     rcx, rax; hHeap
0x180072d84  call    cs:__imp_HeapAlloc
0x180072d8a  mov     [rbp+70h+var_C8], rax
0x180072d8e  test    rax, rax
0x180072d91  jz      short loc_180072D56
0x180072d93  xor     ebx, ebx
0x180072d95  xor     edi, edi
0x180072d97  cmp     [rsp+170h+cSubKeys], ebx
0x180072d9b  jbe     loc_180072E82
0x180072da1  mov     r9d, [rbp+70h+cbMaxSubKeyLen]
0x180072da5  mov     r8, r14; lpName
0x180072da8  mov     rcx, [rbp+70h+phkResult]; hKey
0x180072dac  inc     r9d; cchName
0x180072daf  mov     edx, edi; dwIndex
0x180072db1  call    cs:__imp_RegEnumKeyW
0x180072db7  mov     ebx, eax
0x180072db9  test    eax, eax
0x180072dbb  jnz     loc_18007330F
0x180072dc1  mov     rcx, [rbp+70h+phkResult]; hkey
0x180072dc5  lea     rax, [rsp+170h+pdwType]
0x180072dca  mov     esi, edi
0x180072dcc  lea     r9d, [rbx+8]; dwFlags
0x180072dd0  shl     rsi, 4
0x180072dd4  lea     r8, Value; "TrustedRootCert"
0x180072ddb  add     rsi, [rbp+70h+var_C8]
0x180072ddf  mov     rdx, r14; lpSubKey
0x180072de2  mov     [rsp+170h+lpcbMaxClassLen], rsi; pcbData
0x180072de7  mov     [rsp+170h+lpcbData], 0; pvData
0x180072df0  mov     [rsp+170h+lpData], rax; pdwType
0x180072df5  call    cs:__imp_RegGetValueW
0x180072dfb  mov     ebx, eax
0x180072dfd  test    eax, eax
0x180072dff  jnz     loc_18007330F
0x180072e05  cmp     [rsp+170h+pdwType], 3
0x180072e0a  jnz     loc_180072BC1
0x180072e10  mov     ebx, [rsi]
0x180072e12  call    cs:__imp_GetProcessHeap
0x180072e18  mov     r8d, ebx; dwBytes
0x180072e1b  xor     edx, edx; dwFlags
0x180072e1d  mov     rcx, rax; hHeap
0x180072e20  call    cs:__imp_HeapAlloc
0x180072e26  mov     [rsi+8], rax
0x180072e2a  test    rax, rax
0x180072e2d  jz      loc_180072D56
0x180072e33  mov     rcx, [rbp+70h+phkResult]; hkey
0x180072e37  lea     r8, Value; "TrustedRootCert"
0x180072e3e  mov     [rsp+170h+lpcbMaxClassLen], rsi; pcbData
0x180072e43  mov     r9d, 8; dwFlags
0x180072e49  mov     [rsp+170h+lpcbData], rax; pvData
0x180072e4e  mov     rdx, r14; lpSubKey
0x180072e51  lea     rax, [rsp+170h+pdwType]
0x180072e56  mov     [rsp+170h+lpData], rax; pdwType
0x180072e5b  call    cs:__imp_RegGetValueW
0x180072e61  mov     ebx, eax
0x180072e63  test    eax, eax
0x180072e65  jnz     loc_18007330F
0x180072e6b  cmp     [rsp+170h+pdwType], 3
0x180072e70  jnz     loc_180072BC1
0x180072e76  inc     edi
0x180072e78  cmp     edi, [rsp+170h+cSubKeys]
0x180072e7c  jb      loc_180072DA1
0x180072e82  mov     eax, [rsp+170h+cSubKeys]
0x180072e86  mov     dword ptr [rbp+70h+var_A8+4], eax
0x180072e89  mov     rax, [rbp+70h+var_C8]
0x180072e8d  mov     qword ptr [rbp+70h+var_A8+8], rax
0x180072e91  movups  xmm0, [rbp+70h+var_B8]
0x180072e95  xor     r14d, r14d
0x180072e98  movups  xmm1, [rbp+70h+var_A8]
0x180072e9c  movups  xmmword ptr [r13+0], xmm0
0x180072ea1  movups  xmmword ptr [r13+10h], xmm1
0x180072ea6  cmp     r12b, 2
0x180072eaa  jl      loc_180072FD3
0x180072eb0  lea     ecx, [r14+18h]
0x180072eb4  call    MprCommonAlloc
0x180072eb9  mov     r14, rax
0x180072ebc  test    rax, rax
0x180072ebf  jnz     short loc_180072ED7
0x180072ec1  mov     r14, [rbp+70h+var_D0]
0x180072ec5  lea     ebx, [rax+8]
0x180072ec8  jmp     loc_18007330F
0x180072ecd  mov     ebx, 80070216h
0x180072ed2  jmp     loc_18007330F
0x180072ed7  xor     ecx, ecx; hKey
0x180072ed9  mov     [rsp+170h+var_F8], rcx
0x180072ede  test    r15, r15
0x180072ee1  jz      short loc_180072F20
0x180072ee3  lea     rax, [rsp+170h+var_F8]
0x180072ee8  mov     r9d, 20019h; samDesired
0x180072eee  xor     r8d, r8d; ulOptions
0x180072ef1  mov     [rsp+170h+lpData], rax; phkResult
0x180072ef6  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x180072efd  mov     rcx, r15; hKey
0x180072f00  call    cs:__imp_RegOpenKeyExW
0x180072f06  mov     rcx, [rsp+170h+var_F8]
0x180072f0b  mov     ebx, eax
0x180072f0d  test    eax, eax
0x180072f0f  jnz     short loc_180072F25
0x180072f11  mov     rdx, r14
0x180072f14  call    GetCustomPolicyRegParams
0x180072f19  mov     rcx, [rsp+170h+var_F8]
0x180072f1e  jmp     short loc_180072F25
0x180072f20  mov     ebx, 57h ; 'W'
0x180072f25  test    rcx, rcx
0x180072f28  jz      short loc_180072F30
0x180072f2a  call    cs:__imp_RegCloseKey
0x180072f30  test    ebx, ebx
0x180072f32  jz      short loc_180072F41
0x180072f34  cmp     ebx, 2
0x180072f37  jnz     loc_1800732FF
0x180072f3d  xor     eax, eax
0x180072f3f  jmp     short loc_180072F47
0x180072f41  mov     rax, r14
0x180072f44  xor     r14d, r14d
0x180072f47  lea     rdi, [r13+28h]
0x180072f4b  mov     [r13+38h], rax
0x180072f4f  lea     rsi, [r13+20h]
0x180072f53  mov     [rsp+170h+lpcbData], rdi; __int64
0x180072f58  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x180072f5f  mov     [rsp+170h+lpData], rsi; __int64
0x180072f64  mov     rcx, r15; hkey
0x180072f67  call    RegGetBinary
0x180072f6c  mov     ebx, eax
0x180072f6e  test    eax, eax
  ... truncated ...
```
