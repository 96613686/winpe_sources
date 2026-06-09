# GetIkev2ConfigParams

- ea: `0x180032e84`
- end: `0x180033648`
- name: `GetIkev2ConfigParams`
- size: `1988`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039b4c`

## callees

- `0x180032c70`
- `0x180032cf4`
- `0x180032e84`
- `0x180033650`
- `0x180033e30`
- `0x180033f64`
- `0x180046e2a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003340a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003340a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033096`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800330d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033169`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800333fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003343b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800334ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033096`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800330d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033169`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800333fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003343b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800334ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800335ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800335ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033607`
- `KERNEL32!GetProcessHeap` at `0x180033088`
- `KERNEL32!GetProcessHeap` at `0x1800330c8`
- `KERNEL32!GetProcessHeap` at `0x18003315b`
- `KERNEL32!GetProcessHeap` at `0x1800333ee`
- `KERNEL32!GetProcessHeap` at `0x18003342d`
- `KERNEL32!GetProcessHeap` at `0x1800334df`
- `KERNEL32!GetProcessHeap` at `0x1800335e0`
- `KERNEL32!GetProcessHeap` at `0x1800335f9`
- `KERNEL32!GetProcessHeap` at `0x180033088`
- `KERNEL32!GetProcessHeap` at `0x1800330c8`
- `KERNEL32!GetProcessHeap` at `0x18003315b`
- `KERNEL32!GetProcessHeap` at `0x1800333ee`
- `KERNEL32!GetProcessHeap` at `0x18003342d`
- `KERNEL32!GetProcessHeap` at `0x1800334df`
- `KERNEL32!GetProcessHeap` at `0x1800335e0`
- `KERNEL32!GetProcessHeap` at `0x1800335f9`
- `KERNEL32!RegGetValueW` at `0x180033142`
- `KERNEL32!RegGetValueW` at `0x1800331a4`
- `KERNEL32!RegGetValueW` at `0x1800334be`
- `KERNEL32!RegGetValueW` at `0x180033527`
- `KERNEL32!RegGetValueW` at `0x18003356d`
- `KERNEL32!RegGetValueW` at `0x180033142`
- `KERNEL32!RegGetValueW` at `0x1800331a4`
- `KERNEL32!RegGetValueW` at `0x1800334be`
- `KERNEL32!RegGetValueW` at `0x180033527`
- `KERNEL32!RegGetValueW` at `0x18003356d`
- `ADVAPI32!RegOpenKeyExW` at `0x180032ff2`
- `ADVAPI32!RegOpenKeyExW` at `0x180033352`
- `ADVAPI32!RegOpenKeyExW` at `0x180032ff2`
- `ADVAPI32!RegOpenKeyExW` at `0x180033352`
- `ADVAPI32!RegCloseKey` at `0x180033616`
- `ADVAPI32!RegCloseKey` at `0x180033625`
- `ADVAPI32!RegCloseKey` at `0x180033616`
- `ADVAPI32!RegCloseKey` at `0x180033625`
- `ADVAPI32!RegQueryValueExW` at `0x180032f8a`
- `ADVAPI32!RegQueryValueExW` at `0x180032fae`
- `ADVAPI32!RegQueryValueExW` at `0x1800332cb`
- `ADVAPI32!RegQueryValueExW` at `0x180032f8a`
- `ADVAPI32!RegQueryValueExW` at `0x180032fae`
- `ADVAPI32!RegQueryValueExW` at `0x1800332cb`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003304f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800333ac`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003304f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800333ac`
- `ADVAPI32!RegEnumKeyW` at `0x180033102`
- `ADVAPI32!RegEnumKeyW` at `0x18003347c`
- `ADVAPI32!RegEnumKeyW` at `0x180033102`
- `ADVAPI32!RegEnumKeyW` at `0x18003347c`

## string_xrefs

- `0x180032f31`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall GetIkev2ConfigParams(HKEY hkey, char a2, __int64 a3, DWORD a4)
{
  WCHAR *v4; // r12
  WCHAR *v5; // r14
  unsigned int v8; // edi
  DWORD LastError; // ebx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD v12; // edx
  unsigned int v13; // ebx
  HANDLE v14; // rax
  DWORD v15; // ebx
  HANDLE v16; // rax
  DWORD i; // edi
  DWORD *v18; // rsi
  DWORD v19; // ebx
  HANDLE v20; // rax
  void *v21; // rax
  __int128 v22; // xmm1
  __int64 v23; // r14
  DWORD Ikev2CustomPolicy; // eax
  __int64 v25; // rax
  DWORD Binary; // eax
  LSTATUS v27; // eax
  DWORD v28; // eax
  LSTATUS v29; // eax
  DWORD v30; // eax
  DWORD v31; // edx
  unsigned int v32; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v34; // ebx
  HANDLE v35; // rax
  char *v36; // rax
  char *v37; // r15
  DWORD v38; // edi
  DWORD *v39; // rsi
  unsigned int v40; // ebx
  HANDLE v41; // rax
  void *v42; // rax
  HANDLE v43; // rax
  HANDLE v44; // rax
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  DWORD v47; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD pdwType; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-94h] BYREF
  DWORD Type; // [rsp+78h] [rbp-90h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD v52; // [rsp+80h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-78h] BYREF
  WCHAR *v55; // [rsp+98h] [rbp-70h]
  LPVOID lpMem; // [rsp+A0h] [rbp-68h]
  LPVOID v57; // [rsp+A8h] [rbp-60h]
  __int128 v58; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v59; // [rsp+C0h] [rbp-48h] BYREF
  LPCWSTR lpValueName; // [rsp+D8h] [rbp-30h]
  LPBYTE v61[15]; // [rsp+E0h] [rbp-28h]
  size_t Size; // [rsp+170h] [rbp+68h] BYREF
  DWORD v63; // [rsp+180h] [rbp+78h] BYREF

  v63 = a4;
  LOBYTE(Size) = a2;
  v4 = 0;
  phkResult = 0;
  hKey = 0;
  lpValueName = L"idleTimeout";
  v5 = 0;
  cSubKeys = 0;
  v61[0] = (LPBYTE)&v58;
  v47 = 0;
  v61[1] = (LPBYTE)L"networkBlackoutTime";
  v55 = 0;
  v61[2] = (LPBYTE)&v58 + 4;
  lpMem = 0;
  v61[3] = (LPBYTE)L"saLifeTime";
  v8 = 0;
  v57 = 0;
  v61[4] = (LPBYTE)&v58 + 8;
  v61[5] = (LPBYTE)L"saDataSize";
  v61[6] = (LPBYTE)&v58 + 12;
  v61[7] = (LPBYTE)L"ConfigOptions";
  v61[8] = (LPBYTE)&v59;
  v58 = 0;
  v59 = 0;
  while ( 1 )
  {
    cbData = 4;
    Type = 4;
    if ( v8 >= 5 )
      break;
    LastError = RegQueryValueExW(hkey, (LPCWSTR)v61[2 * v8 - 1], 0, &Type, v61[2 * v8], &cbData);
    if ( LastError )
      goto LABEL_80;
    ++v8;
  }
  v10 = RegQueryValueExW(hkey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 96), &cbData);
  LastError = v10;
  if ( v10 )
  {
    if ( v10 != 2 )
      goto LABEL_80;
    *(_DWORD *)(a3 + 96) = 28800;
  }
  cbMaxSubKeyLen = 0;
  pdwType = 3;
  v11 = RegOpenKeyExW(hkey, L"AllowedTrustedRootCerts", 0, 0x20019u, &phkResult);
  LastError = v11;
  if ( v11 )
  {
    if ( v11 == 2 )
    {
LABEL_33:
      v22 = v59;
      *(_OWORD *)a3 = v58;
      *(_OWORD *)(a3 + 16) = v22;
      v23 = MprCommonAlloc(24);
      if ( !v23 )
      {
        v5 = v55;
        LastError = 8;
        goto LABEL_80;
      }
      Ikev2CustomPolicy = GetIkev2CustomPolicy(hkey);
      LastError = Ikev2CustomPolicy;
      if ( Ikev2CustomPolicy )
      {
        if ( Ikev2CustomPolicy != 2 )
          goto LABEL_77;
        v25 = 0;
      }
      else
      {
        v25 = v23;
        v23 = 0;
      }
      *(_QWORD *)(a3 + 56) = v25;
      Binary = RegGetBinary(hkey, L"MachineCertificateName", a3 + 32, a3 + 40);
      LastError = Binary;
      if ( Binary )
      {
        if ( Binary != 2 )
          goto LABEL_76;
        *(_DWORD *)(a3 + 32) = 0;
        *(_QWORD *)(a3 + 40) = 0;
      }
      cbData = 4;
      Type = 4;
      v27 = RegQueryValueExW(hkey, L"EncryptionType", 0, &Type, (LPBYTE)(a3 + 48), &cbData);
      LastError = v27;
      if ( v27 )
      {
        if ( v27 != 2 )
          goto LABEL_76;
        *(_DWORD *)(a3 + 48) = 2;
      }
      v52 = 0;
      v63 = 1;
      LODWORD(Size) = 0;
      v28 = RegGetBinary(hkey, L"MachineCertificateHash", a3 + 80, a3 + 88);
      LastError = v28;
      if ( v28 )
      {
        if ( v28 != 2 )
          goto LABEL_76;
        *(_DWORD *)(a3 + 80) = 0;
        *(_QWORD *)(a3 + 88) = 0;
      }
      v29 = RegOpenKeyExW(hkey, L"AllowedCertEku", 0, 0x20019u, &hKey);
      LastError = v29;
      if ( v29 )
      {
        if ( v29 == 2 )
          LastError = 0;
      }
      else
      {
        LastError = RegQueryInfoKeyW(hKey, 0, 0, 0, &v47, &v52, 0, 0, 0, 0, 0, 0);
        if ( LastError )
          goto LABEL_76;
        v30 = v47;
        if ( v47 )
        {
          v31 = -1;
          if ( v52 + 1 >= v52 )
            v31 = v52 + 1;
          if ( 2 * (unsigned __int64)v31 > 0xFFFFFFFF )
          {
            LODWORD(Size) = -1;
            LastError = -2147024362;
            goto LABEL_76;
          }
          v32 = 2 * v31;
          LODWORD(Size) = 2 * v31;
          ProcessHeap = GetProcessHeap();
          v4 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v32);
          if ( !v4 )
            goto LABEL_57;
          if ( 16 * (unsigned __int64)v47 > 0xFFFFFFFF )
          {
            LODWORD(Size) = -1;
            LastError = -2147024362;
            goto LABEL_76;
          }
          v34 = 16 * v47;
          LODWORD(Size) = 16 * v47;
          v35 = GetProcessHeap();
          v36 = (char *)HeapAlloc(v35, 0, v34);
          v57 = v36;
          v37 = v36;
          if ( !v36 )
          {
LABEL_57:
            LastError = GetLastError();
            goto LABEL_76;
          }
          memset_0(v36, 0, (unsigned int)Size);
          v38 = 0;
          LastError = 0;
          while ( 1 )
          {
            v30 = v47;
            if ( v38 >= v47 )
              break;
            LastError = RegEnumKeyW(hKey, v38, v4, v52 + 1);
            if ( LastError )
              goto LABEL_76;
            v39 = (DWORD *)&v37[16 * v38];
            LastError = RegGetValueW(hKey, v4, L"TrustedEku", 2u, &v63, 0, v39);
            if ( LastError )
              goto LABEL_76;
            if ( v63 != 1 )
              goto LABEL_71;
            LODWORD(Size) = *v39;
            v40 = Size;
            v41 = GetProcessHeap();
            v42 = HeapAlloc(v41, 0, v40);
            *((_QWORD *)v39 + 1) = v42;
            if ( !v42 )
              goto LABEL_57;
            LastError = RegGetValueW(hKey, v4, L"TrustedEku", 2u, &v63, v42, v39);
            if ( LastError )
              goto LABEL_76;
            if ( v63 != 1 )
              goto LABEL_71;
            LODWORD(Size) = 4;
            LastError = RegGetValueW(hKey, v4, L"IsEkuOID", 0x10u, &v63, v39 + 1, (LPDWORD)&Size);
            if ( LastError )
              goto LABEL_76;
            if ( v63 != 4 )
            {
LABEL_71:
              LastError = 87;
              goto LABEL_76;
            }
            ++v38;
          }
        }
        else
        {
          v37 = 0;
        }
        *(_DWORD *)(a3 + 64) = v30;
        *(_QWORD *)(a3 + 72) = v37;
      }
LABEL_76:
      if ( !v23 )
      {
LABEL_78:
        v5 = v55;
LABEL_79:
        if ( !LastError )
          goto LABEL_81;
        goto LABEL_80;
      }
LABEL_77:
      FreeCustomPolicy(v23);
      goto LABEL_78;
    }
  }
  else
  {
    LastError = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !LastError )
    {
      if ( cSubKeys )
      {
        v12 = -1;
        if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
          v12 = cbMaxSubKeyLen + 1;
        if ( 2 * (unsigned __int64)v12 > 0xFFFFFFFF )
        {
          LastError = -2147024362;
          goto LABEL_80;
        }
        v13 = 2 * v12;
        v14 = GetProcessHeap();
        v55 = (WCHAR *)HeapAlloc(v14, 0, v13);
        v5 = v55;
        if ( !v55 )
          goto LABEL_17;
        if ( 16 * (unsigned __int64)cSubKeys > 0xFFFFFFFF )
        {
          LastError = -2147024362;
          goto LABEL_80;
        }
        v15 = 16 * cSubKeys;
        v16 = GetProcessHeap();
        lpMem = HeapAlloc(v16, 0, v15);
        if ( !lpMem )
        {
LABEL_17:
          LastError = GetLastError();
          goto LABEL_79;
        }
        for ( i = 0; i < cSubKeys; ++i )
        {
          LastError = RegEnumKeyW(phkResult, i, v5, cbMaxSubKeyLen + 1);
          if ( LastError )
            goto LABEL_80;
          v18 = (DWORD *)((char *)lpMem + 16 * i);
          LastError = RegGetValueW(phkResult, v5, L"TrustedRootCert", 8u, &pdwType, 0, v18);
          if ( LastError )
            goto LABEL_80;
          if ( pdwType != 3 )
            goto LABEL_29;
          v19 = *v18;
          v20 = GetProcessHeap();
          v21 = HeapAlloc(v20, 0, v19);
          *((_QWORD *)v18 + 1) = v21;
          if ( !v21 )
            goto LABEL_17;
          LastError = RegGetValueW(phkResult, v5, L"TrustedRootCert", 8u, &pdwType, v21, v18);
          if ( LastError )
            goto LABEL_80;
          if ( pdwType != 3 )
          {
LABEL_29:
            LastError = 87;
            goto LABEL_80;
          }
        }
      }
      DWORD1(v59) = cSubKeys;
      *((_QWORD *)&v59 + 1) = lpMem;
      goto LABEL_33;
    }
  }
LABEL_80:
  FreeEkus(lpMem);
  FreeEkus(v57);
LABEL_81:
  if ( v5 )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v5);
  }
  if ( v4 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v4);
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
0x180032e84  mov     rax, rsp
0x180032e87  mov     [rax+8], rbx
0x180032e8b  mov     [rax+20h], r9d
0x180032e8f  mov     [rax+10h], dl
0x180032e92  push    rbp
0x180032e93  push    rsi
0x180032e94  push    rdi
0x180032e95  push    r12
0x180032e97  push    r13
0x180032e99  push    r14
0x180032e9b  push    r15
0x180032e9d  lea     rbp, [rax-58h]
0x180032ea1  sub     rsp, 120h
0x180032ea8  xor     r12d, r12d
0x180032eab  mov     [rbp+50h+phkResult], 0
0x180032eb3  lea     rax, aIdletimeout; "idleTimeout"
0x180032eba  mov     [rbp+50h+hKey], 0
0x180032ec2  mov     [rbp+50h+lpValueName], rax
0x180032ec6  xor     r14d, r14d
0x180032ec9  lea     rax, [rbp+50h+var_A8]
0x180032ecd  mov     [rsp+150h+cSubKeys], 0
0x180032ed5  mov     [rbp+50h+var_78], rax
0x180032ed9  xorps   xmm0, xmm0
0x180032edc  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x180032ee3  mov     [rsp+150h+var_EC], 0
0x180032eeb  mov     [rbp+50h+var_70], rax
0x180032eef  mov     r13, r8
0x180032ef2  lea     rax, [rbp+50h+var_A8+4]
0x180032ef6  mov     [rbp+50h+var_C0], r14
0x180032efa  mov     [rbp+50h+var_68], rax
0x180032efe  mov     r15, rcx
0x180032f01  lea     rax, aSalifetime; "saLifeTime"
0x180032f08  mov     [rbp+50h+lpMem], r12
0x180032f0c  mov     [rbp+50h+var_60], rax
0x180032f10  xor     edi, edi
0x180032f12  lea     rax, [rbp+50h+var_A8+8]
0x180032f16  mov     [rbp+50h+var_B0], r12
0x180032f1a  mov     [rbp+50h+var_58], rax
0x180032f1e  lea     rax, aSadatasize; "saDataSize"
0x180032f25  mov     [rbp+50h+var_50], rax
0x180032f29  lea     rax, [rbp+50h+var_A8+0Ch]
0x180032f2d  mov     [rbp+50h+var_48], rax
0x180032f31  lea     rax, aConfigoptions; "ConfigOptions"
0x180032f38  mov     [rbp+50h+var_40], rax
0x180032f3c  lea     rax, [rbp+50h+var_98]
0x180032f40  mov     [rbp+50h+var_38], rax
0x180032f44  movups  [rbp+50h+var_A8], xmm0
0x180032f48  movups  [rbp+50h+var_98], xmm0
0x180032f4c  xor     r8d, r8d; lpReserved
0x180032f4f  mov     [rsp+150h+cbData], 4
0x180032f57  mov     [rsp+150h+Type], 4
0x180032f5f  lea     rax, [rsp+150h+cbData]
0x180032f64  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180032f69  lea     r9, [rsp+150h+Type]; lpType
0x180032f6e  mov     rcx, r15; hKey
0x180032f71  cmp     edi, 5
0x180032f74  jnb     short loc_180032F9E
0x180032f76  mov     edx, edi
0x180032f78  add     rdx, rdx
0x180032f7b  mov     rax, [rbp+rdx*8+50h+var_78]
0x180032f80  mov     rdx, [rbp+rdx*8+50h+lpValueName]; lpValueName
0x180032f85  mov     [rsp+150h+lpData], rax; lpData
0x180032f8a  call    cs:__imp_RegQueryValueExW
0x180032f90  mov     ebx, eax
0x180032f92  test    eax, eax
0x180032f94  jnz     loc_1800335C1
0x180032f9a  inc     edi
0x180032f9c  jmp     short loc_180032F4C
0x180032f9e  lea     rdi, [r13+60h]
0x180032fa2  lea     rdx, aMmsalifetime_0; "mmSaLifeTime"
0x180032fa9  mov     [rsp+150h+lpData], rdi; lpData
0x180032fae  call    cs:__imp_RegQueryValueExW
0x180032fb4  mov     ebx, eax
0x180032fb6  test    eax, eax
0x180032fb8  jz      short loc_180032FC9
0x180032fba  cmp     eax, 2
0x180032fbd  jnz     loc_1800335C1
0x180032fc3  mov     dword ptr [rdi], 7080h
0x180032fc9  lea     rax, [rbp+50h+phkResult]
0x180032fcd  mov     [rsp+150h+cbMaxSubKeyLen], r12d
0x180032fd2  mov     r9d, 20019h; samDesired
0x180032fd8  mov     [rsp+150h+lpData], rax; phkResult
0x180032fdd  xor     r8d, r8d; ulOptions
0x180032fe0  mov     [rsp+150h+pdwType], 3
0x180032fe8  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x180032fef  mov     rcx, r15; hKey
0x180032ff2  call    cs:__imp_RegOpenKeyExW
0x180032ff8  mov     ebx, eax
0x180032ffa  mov     edi, 0FFFFFFFFh
0x180032fff  test    eax, eax
0x180033001  jz      short loc_180033011
0x180033003  cmp     eax, 2
0x180033006  jnz     loc_1800335C1
0x18003300c  jmp     loc_1800331EF
0x180033011  mov     rcx, [rbp+50h+phkResult]; hKey
0x180033015  lea     rax, [rsp+150h+cbMaxSubKeyLen]
0x18003301a  mov     [rsp+150h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003301f  xor     r9d, r9d; lpReserved
0x180033022  mov     [rsp+150h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180033027  xor     r8d, r8d; lpcchClass
0x18003302a  mov     [rsp+150h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18003302f  xor     edx, edx; lpClass
0x180033031  mov     [rsp+150h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180033036  mov     [rsp+150h+lpcValues], r12; lpcValues
0x18003303b  mov     [rsp+150h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180033040  mov     [rsp+150h+lpcbData], rax; lpcbMaxSubKeyLen
0x180033045  lea     rax, [rsp+150h+cSubKeys]
0x18003304a  mov     [rsp+150h+lpData], rax; lpcSubKeys
0x18003304f  call    cs:__imp_RegQueryInfoKeyW
0x180033055  mov     ebx, eax
0x180033057  test    eax, eax
0x180033059  jnz     loc_1800335C1
0x18003305f  cmp     [rsp+150h+cSubKeys], r12d
0x180033064  jz      loc_1800331E0
0x18003306a  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x18003306e  mov     edx, edi
0x180033070  lea     ecx, [rax+1]
0x180033073  cmp     ecx, eax
0x180033075  cmovnb  edx, ecx
0x180033078  mov     eax, edx
0x18003307a  add     rax, rax
0x18003307d  cmp     rax, rdi
0x180033080  ja      loc_1800331D6
0x180033086  mov     ebx, eax
0x180033088  call    cs:__imp_GetProcessHeap
0x18003308e  mov     r8d, ebx; dwBytes
0x180033091  xor     edx, edx; dwFlags
0x180033093  mov     rcx, rax; hHeap
0x180033096  call    cs:__imp_HeapAlloc
0x18003309c  mov     [rbp+50h+var_C0], rax
0x1800330a0  mov     r14, rax
0x1800330a3  test    rax, rax
0x1800330a6  jnz     short loc_1800330B5
0x1800330a8  call    cs:__imp_GetLastError
0x1800330ae  mov     ebx, eax
0x1800330b0  jmp     loc_1800335BD
0x1800330b5  mov     eax, [rsp+150h+cSubKeys]
0x1800330b9  shl     rax, 4
0x1800330bd  cmp     rax, rdi
0x1800330c0  ja      loc_1800331CC
0x1800330c6  mov     ebx, eax
0x1800330c8  call    cs:__imp_GetProcessHeap
0x1800330ce  mov     r8d, ebx; dwBytes
0x1800330d1  xor     edx, edx; dwFlags
0x1800330d3  mov     rcx, rax; hHeap
0x1800330d6  call    cs:__imp_HeapAlloc
0x1800330dc  mov     [rbp+50h+lpMem], rax
0x1800330e0  test    rax, rax
0x1800330e3  jz      short loc_1800330A8
0x1800330e5  xor     edi, edi
0x1800330e7  cmp     edi, [rsp+150h+cSubKeys]
0x1800330eb  jnb     loc_1800331E0
0x1800330f1  mov     r9d, [rsp+150h+cbMaxSubKeyLen]
0x1800330f6  mov     r8, r14; lpName
0x1800330f9  mov     rcx, [rbp+50h+phkResult]; hKey
0x1800330fd  inc     r9d; cchName
0x180033100  mov     edx, edi; dwIndex
0x180033102  call    cs:__imp_RegEnumKeyW
0x180033108  mov     ebx, eax
0x18003310a  test    eax, eax
0x18003310c  jnz     loc_1800335C1
0x180033112  mov     rcx, [rbp+50h+phkResult]; hkey
0x180033116  lea     rax, [rsp+150h+pdwType]
0x18003311b  mov     esi, edi
0x18003311d  lea     r9d, [rbx+8]; dwFlags
0x180033121  shl     rsi, 4
0x180033125  lea     r8, Value; "TrustedRootCert"
0x18003312c  add     rsi, [rbp+50h+lpMem]
0x180033130  mov     rdx, r14; lpSubKey
0x180033133  mov     [rsp+150h+lpcbMaxClassLen], rsi; pcbData
0x180033138  mov     [rsp+150h+lpcbData], r12; pvData
0x18003313d  mov     [rsp+150h+lpData], rax; pdwType
0x180033142  call    cs:__imp_RegGetValueW
0x180033148  mov     ebx, eax
0x18003314a  test    eax, eax
0x18003314c  jnz     loc_1800335C1
0x180033152  cmp     [rsp+150h+pdwType], 3
0x180033157  jnz     short loc_1800331C2
0x180033159  mov     ebx, [rsi]
0x18003315b  call    cs:__imp_GetProcessHeap
0x180033161  mov     r8d, ebx; dwBytes
0x180033164  xor     edx, edx; dwFlags
0x180033166  mov     rcx, rax; hHeap
0x180033169  call    cs:__imp_HeapAlloc
0x18003316f  mov     [rsi+8], rax
0x180033173  test    rax, rax
0x180033176  jz      loc_1800330A8
0x18003317c  mov     rcx, [rbp+50h+phkResult]; hkey
0x180033180  lea     r8, Value; "TrustedRootCert"
0x180033187  mov     [rsp+150h+lpcbMaxClassLen], rsi; pcbData
0x18003318c  mov     r9d, 8; dwFlags
0x180033192  mov     [rsp+150h+lpcbData], rax; pvData
0x180033197  mov     rdx, r14; lpSubKey
0x18003319a  lea     rax, [rsp+150h+pdwType]
0x18003319f  mov     [rsp+150h+lpData], rax; pdwType
0x1800331a4  call    cs:__imp_RegGetValueW
0x1800331aa  mov     ebx, eax
0x1800331ac  test    eax, eax
0x1800331ae  jnz     loc_1800335C1
0x1800331b4  cmp     [rsp+150h+pdwType], 3
0x1800331b9  jnz     short loc_1800331C2
0x1800331bb  inc     edi
0x1800331bd  jmp     loc_1800330E7
0x1800331c2  mov     ebx, 57h ; 'W'
0x1800331c7  jmp     loc_1800335C1
0x1800331cc  mov     ebx, 80070216h
0x1800331d1  jmp     loc_1800335C1
0x1800331d6  mov     ebx, 80070216h
0x1800331db  jmp     loc_1800335C1
0x1800331e0  mov     eax, [rsp+150h+cSubKeys]
0x1800331e4  mov     dword ptr [rbp+50h+var_98+4], eax
0x1800331e7  mov     rax, [rbp+50h+lpMem]
0x1800331eb  mov     qword ptr [rbp+50h+var_98+8], rax
0x1800331ef  movups  xmm0, [rbp+50h+var_A8]
0x1800331f3  mov     ecx, 18h
0x1800331f8  movups  xmm1, [rbp+50h+var_98]
0x1800331fc  movups  xmmword ptr [r13+0], xmm0
0x180033201  movups  xmmword ptr [r13+10h], xmm1
0x180033206  call    MprCommonAlloc
0x18003320b  mov     r14, rax
0x18003320e  test    rax, rax
0x180033211  jnz     short loc_18003321F
0x180033213  mov     r14, [rbp+50h+var_C0]
0x180033217  lea     ebx, [rax+8]
0x18003321a  jmp     loc_1800335C1
0x18003321f  mov     r9, r14
0x180033222  lea     r8, MprCommonFree
0x180033229  lea     rdx, MprCommonAlloc
0x180033230  mov     rcx, r15; hKey
0x180033233  call    GetIkev2CustomPolicy
0x180033238  mov     ebx, eax
0x18003323a  test    eax, eax
0x18003323c  jz      short loc_18003324B
0x18003323e  cmp     eax, 2
0x180033241  jnz     loc_1800335B1
0x180033247  xor     eax, eax
0x180033249  jmp     short loc_180033251
0x18003324b  mov     rax, r14
0x18003324e  xor     r14d, r14d
0x180033251  lea     rdi, [r13+28h]
0x180033255  mov     [r13+38h], rax
0x180033259  lea     rsi, [r13+20h]
0x18003325d  mov     [rsp+150h+lpcbData], rdi; __int64
0x180033262  lea     r9, MprCommonFree
0x180033269  mov     [rsp+150h+lpData], rsi; __int64
0x18003326e  lea     r8, MprCommonAlloc
0x180033275  mov     rcx, r15; hkey
0x180033278  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x18003327f  call    RegGetBinary
0x180033284  mov     ebx, eax
0x180033286  test    eax, eax
0x180033288  jz      short loc_180033299
0x18003328a  cmp     eax, 2
0x18003328d  jnz     loc_1800335AC
0x180033293  mov     [rsi], r12d
0x180033296  mov     [rdi], r12
0x180033299  mov     eax, 4
0x18003329e  lea     rdi, [r13+30h]
0x1800332a2  mov     [rsp+150h+cbData], eax
0x1800332a6  lea     r9, [rsp+150h+Type]; lpType
0x1800332ab  mov     [rsp+150h+Type], eax
0x1800332af  lea     rdx, aEncryptiontype; "EncryptionType"
0x1800332b6  lea     rax, [rsp+150h+cbData]
0x1800332bb  xor     r8d, r8d; lpReserved
0x1800332be  mov     [rsp+150h+lpcbData], rax; lpcbData
0x1800332c3  mov     rcx, r15; hKey
0x1800332c6  mov     [rsp+150h+lpData], rdi; lpData
0x1800332cb  call    cs:__imp_RegQueryValueExW
0x1800332d1  mov     ebx, eax
0x1800332d3  test    eax, eax
0x1800332d5  jz      short loc_1800332E2
0x1800332d7  cmp     eax, 2
0x1800332da  jnz     loc_1800335AC
0x1800332e0  mov     [rdi], eax
0x1800332e2  lea     rdi, [r13+58h]
0x1800332e6  mov     [rsp+150h+var_D8], r12d
0x1800332eb  lea     rsi, [r13+50h]
0x1800332ef  mov     [rsp+150h+lpcbData], rdi; __int64
0x1800332f4  lea     r9, MprCommonFree
0x1800332fb  mov     [rsp+150h+lpData], rsi; __int64
0x180033300  lea     r8, MprCommonAlloc
0x180033307  mov     [rbp+50h+arg_18], 1
0x18003330e  lea     rdx, aMachinecertifi; "MachineCertificateHash"
0x180033315  mov     dword ptr [rbp+50h+Size], r12d
0x180033319  mov     rcx, r15; hkey
0x18003331c  call    RegGetBinary
0x180033321  mov     ebx, eax
0x180033323  test    eax, eax
0x180033325  jz      short loc_180033336
0x180033327  cmp     eax, 2
0x18003332a  jnz     loc_1800335AC
0x180033330  mov     [rsi], r12d
0x180033333  mov     [rdi], r12
0x180033336  lea     rax, [rbp+50h+hKey]
0x18003333a  mov     r9d, 20019h; samDesired
0x180033340  xor     r8d, r8d; ulOptions
0x180033343  mov     [rsp+150h+lpData], rax; phkResult
0x180033348  lea     rdx, aAllowedcerteku; "AllowedCertEku"
0x18003334f  mov     rcx, r15; hKey
0x180033352  call    cs:__imp_RegOpenKeyExW
  ... truncated ...
```
