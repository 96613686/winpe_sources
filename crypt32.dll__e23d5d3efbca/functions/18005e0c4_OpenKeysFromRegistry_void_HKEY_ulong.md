# OpenKeysFromRegistry(void *,HKEY__ *,ulong)

- ea: `0x18005e0c4`
- end: `0x18005e71a`
- name: `?OpenKeysFromRegistry@@YAHPEAXPEAUHKEY__@@K@Z`
- size: `1622`
- prototype: `int(void *, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008a464`

## callees

- `0x1800219ec`
- `0x180028d60`
- `0x1800334b8`
- `0x180033690`
- `0x1800336b8`
- `0x1800450c0`
- `0x180057c48`
- `0x18005d484`
- `0x18005e0c4`
- `0x18005f450`
- `0x1800600e0`
- `0x180060a00`
- `0x18009377c`
- `0x1800bec20`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e47d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e47d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e2d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e4f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e6d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e2d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e458`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e490`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e4f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e6d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005e18f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005e18f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005e143`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005e143`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e245`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e60c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e245`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005e60c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e69a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005e69a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e2d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e2d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e1ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005e1ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e488`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e488`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e272`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005e272`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e42c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e42c`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e589`
- `profapi!__imp_GetAppContainerRegistryHandle` at `0x18005e589`

## pseudocode

```c
__int64 __fastcall OpenKeysFromRegistry(struct _CERT_STORE *a1, HKEY a2, unsigned int a3)
{
  int v3; // r15d
  unsigned int v5; // r14d
  LSTATUS v6; // eax
  unsigned int v7; // r12d
  DWORD v8; // edx
  LSTATUS v9; // eax
  BYTE *v10; // rdi
  HKEY v11; // rcx
  LSTATUS v12; // ebx
  HKEY v13; // rbx
  LSTATUS Value; // eax
  DWORD v15; // ecx
  int v16; // ebx
  unsigned int v17; // esi
  HKEY v18; // r14
  DWORD LastError; // ebx
  struct _CERT_STORE *v20; // rax
  unsigned int v21; // eax
  const CERT_CONTEXT *v22; // rsi
  DWORD v23; // ebx
  DWORD v24; // eax
  DWORD v25; // r9d
  WCHAR *v26; // r8
  _BYTE *v27; // r10
  DWORD v28; // r11d
  __int16 v29; // ax
  unsigned int v30; // ecx
  unsigned int v31; // edx
  __int16 v32; // ax
  int CrlRegValueName; // eax
  DWORD v34; // ebx
  DWORD v35; // ebx
  DWORD v36; // ecx
  DWORD v37; // ebx
  DWORD v38; // ebx
  DWORD v39; // ebx
  LSTATUS AppContainerRegistryHandle; // eax
  int MultipleKeyBlobsFromRegistry; // eax
  __int64 v43; // rax
  HKEY v44; // rcx
  DWORD cbData[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v49; // [rsp+78h] [rbp-88h]
  DWORD v50; // [rsp+7Ch] [rbp-84h]
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-78h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+90h] [rbp-70h] BYREF
  struct _CERT_STORE *v54; // [rsp+98h] [rbp-68h]
  BYTE *v55; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v56; // [rsp+A8h] [rbp-58h]
  int v57; // [rsp+ACh] [rbp-54h]
  _BYTE pvData[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR String2[48]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[48]; // [rsp+130h] [rbp+30h] BYREF

  v3 = 0;
  v49 = a3;
  v5 = a3;
  v54 = a1;
  cSubKeys = 0;
  v6 = RegQueryInfoKeyW(a2, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v6 )
  {
    SetLastError(v6);
    return 0;
  }
  else
  {
    v7 = 1;
    v8 = 0;
    v50 = 0;
    if ( cSubKeys != -10 )
    {
      do
      {
        cchName = 42;
        v9 = RegEnumKeyExW(a2, v8, Name, &cchName, 0, 0, 0, 0);
        if ( v9 )
        {
          if ( v9 == 259 )
            return v7;
        }
        else if ( (v5 & 0x10) == 0 )
        {
          pcbData = 0;
          v10 = 0;
          pCertContext = 0;
          phkResult = 0;
          if ( (v5 & 0x800) == 0 )
          {
            hKey = 0;
            if ( a2 != HKEY_CURRENT_USER )
            {
              v11 = a2;
              goto LABEL_8;
            }
            if ( (unsigned int)I_CryptIsAppContainerToken(0) )
              AppContainerRegistryHandle = GetAppContainerRegistryHandle(131097, &hKey);
            else
              AppContainerRegistryHandle = RegOpenHKCUEx(&hKey);
            v12 = AppContainerRegistryHandle;
            if ( !AppContainerRegistryHandle )
            {
              v11 = hKey;
LABEL_8:
              v12 = RegOpenKeyExW(v11, Name, 0, 0x20019u, &phkResult);
              if ( hKey && hKey != HKEY_CURRENT_USER )
                RegCloseKey(hKey);
              goto LABEL_11;
            }
            goto LABEL_55;
          }
          LODWORD(hKey) = 0;
          *(_QWORD *)cbData = 0;
          if ( a2 == HKEY_CURRENT_USER )
          {
            v12 = RegOpenAppContainerHKCU((PHKEY)cbData);
            if ( v12 )
              goto LABEL_11;
            v44 = *(HKEY *)cbData;
          }
          else
          {
            v44 = a2;
          }
          v12 = RegCreateKeyExW(v44, Name, 0, 0, 4u, 0x20019u, 0, &phkResult, (LPDWORD)&hKey);
          if ( *(_QWORD *)cbData )
            RegCloseHKCU();
LABEL_11:
          if ( v12 )
          {
LABEL_55:
            SetLastError(v12);
          }
          else
          {
            v13 = phkResult;
            LODWORD(hKey) = 0;
            cbData[0] = 0;
            Value = RegQueryValueExW(phkResult, L"Blob", 0, (LPDWORD)&hKey, 0, cbData);
            if ( !Value || Value == 234 )
            {
              if ( (_DWORD)hKey != 3 || cbData[0] > 0xFFFFFF )
              {
                v15 = -2146885629;
                goto LABEL_17;
              }
              v10 = (BYTE *)LocalAlloc(0, cbData[0] + 3);
              if ( !v10 )
              {
                v15 = -2147024882;
                goto LABEL_17;
              }
              v43 = cbData[0];
              if ( cbData[0] )
              {
                Value = RegQueryValueExW(v13, L"Blob", 0, (LPDWORD)&hKey, v10, cbData);
                if ( Value )
                  goto LABEL_62;
                v43 = cbData[0];
              }
              v16 = 1;
              *(_WORD *)&v10[v43] = 0;
              v10[v43 + 2] = 0;
              v17 = cbData[0];
            }
            else
            {
LABEL_62:
              v15 = Value;
LABEL_17:
              SetLastError(v15);
              v16 = 0;
              PkiDefaultCryptFree(v10);
              v10 = 0;
              v17 = 0;
            }
            *(_QWORD *)cbData = v10;
            LODWORD(hKey) = v17;
            if ( v16 && v17 )
            {
LABEL_20:
              v3 = 1;
              goto LABEL_21;
            }
            PkiDefaultCryptFree(v10);
            MultipleKeyBlobsFromRegistry = ReadMultipleKeyBlobsFromRegistry(
                                             phkResult,
                                             v5,
                                             (unsigned __int8 **)cbData,
                                             (unsigned int *)&hKey);
            v10 = *(BYTE **)cbData;
            if ( MultipleKeyBlobsFromRegistry )
            {
              v17 = (unsigned int)hKey;
              goto LABEL_20;
            }
          }
          PkiDefaultCryptFree(v10);
          v10 = 0;
          v17 = 0;
LABEL_21:
          v18 = phkResult;
          if ( phkResult )
          {
            LastError = GetLastError();
            RegCloseKey(v18);
            SetLastError(LastError);
          }
          if ( !v3 )
          {
            v3 = 0;
LABEL_47:
            if ( v10 )
            {
              v39 = GetLastError();
              LocalFree(v10);
              SetLastError(v39);
            }
            v5 = v49;
            goto LABEL_50;
          }
          v55 = v10;
          v20 = v54;
          v56 = v17;
          if ( !v54 )
            v20 = (struct _CERT_STORE *)&dword_180157FC0;
          v57 = 0;
          v3 = 0;
          v21 = LoadStoreElement(
                  &v55,
                  ReadFromMemory,
                  (int (*)(void *, unsigned int))SkipInMemory,
                  v17,
                  v20,
                  4u,
                  0xFFFFFFFF,
                  &pcbData,
                  (const void **)&pCertContext,
                  0);
          if ( v21 != 1 )
          {
            if ( v21 == 2 )
              SetLastError(0x80092004);
            goto LABEL_47;
          }
          v22 = pCertContext;
          memset_0(String2, 0, 0x54u);
          v23 = pcbData;
          v24 = pcbData - 1;
          switch ( pcbData )
          {
            case 1u:
              pcbData = 20;
              if ( CertGetCertificateContextProperty(v22, v24 + 3, pvData, &pcbData) )
              {
                v25 = pcbData;
                v26 = String2;
                v27 = pvData;
                v28 = 0;
                if ( pcbData )
                {
                  do
                  {
                    v29 = 48;
                    v30 = (unsigned __int8)*v27 >> 4;
                    if ( v30 > 9 )
                      v29 = 55;
                    v31 = *v27 & 0xF;
                    *v26 = v30 + v29;
                    v32 = 48;
                    if ( v31 > 9 )
                      v32 = 55;
                    ++v27;
                    ++v28;
                    v26[1] = v31 + v32;
                    v26 += 2;
                  }
                  while ( v28 < v25 );
                  v22 = pCertContext;
                }
                *v26 = 0;
                CrlRegValueName = 1;
              }
              else
              {
                CrlRegValueName = 0;
              }
LABEL_37:
              if ( CrlRegValueName )
              {
                if ( CompareStringW(0x409u, 1u, Name, -1, String2, -1) == 2 )
                {
                  v34 = v23 - 1;
                  if ( !v34 || (v35 = v34 - 1) == 0 || v35 == 1 )
                    CertFreeCertificateContext(v22);
                  goto LABEL_47;
                }
                v36 = 161;
LABEL_43:
                SetLastError(v36);
              }
              v37 = v23 - 1;
              if ( !v37 || (v38 = v37 - 1) == 0 || v38 == 1 )
                CertDeleteCTLFromStore(v22);
              goto LABEL_47;
            case 2u:
              CrlRegValueName = GetCrlRegValueName((const struct _CRL_CONTEXT *)v22, String2);
              goto LABEL_37;
            case 3u:
              CrlRegValueName = GetCtlRegValueName((const struct _CTL_CONTEXT *)v22, String2);
              goto LABEL_37;
          }
          v36 = -2147418113;
          goto LABEL_43;
        }
LABEL_50:
        v8 = v50 + 1;
        v50 = v8;
      }
      while ( v8 < cSubKeys + 10 );
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18005e0c4  mov     [rsp-8+arg_10], rbx
0x18005e0c9  push    rbp
0x18005e0ca  push    rsi
0x18005e0cb  push    rdi
0x18005e0cc  push    r12
0x18005e0ce  push    r13
0x18005e0d0  push    r14
0x18005e0d2  push    r15
0x18005e0d4  lea     rbp, [rsp-0A0h]
0x18005e0dc  sub     rsp, 1A0h
0x18005e0e3  mov     rax, cs:__security_cookie
0x18005e0ea  xor     rax, rsp
0x18005e0ed  mov     [rbp+0D0h+var_40], rax
0x18005e0f4  xor     r15d, r15d
0x18005e0f7  mov     [rsp+1D0h+var_158], r8d
0x18005e0fc  mov     [rsp+1D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18005e101  lea     rax, [rsp+1D0h+cSubKeys]
0x18005e106  mov     [rsp+1D0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18005e10b  mov     r13, rdx
0x18005e10e  mov     [rsp+1D0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18005e113  mov     r14d, r8d
0x18005e116  mov     [rsp+1D0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18005e11b  xor     r9d, r9d; lpReserved
0x18005e11e  mov     [rsp+1D0h+lpcValues], r15; lpcValues
0x18005e123  xor     r8d, r8d; lpcchClass
0x18005e126  mov     [rsp+1D0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18005e12b  xor     edx, edx; lpClass
0x18005e12d  mov     [rbp+0D0h+var_138], rcx
0x18005e131  mov     rcx, r13; hKey
0x18005e134  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18005e139  mov     [rsp+1D0h+lpcSubKeys], rax; lpcSubKeys
0x18005e13e  mov     [rsp+1D0h+cSubKeys], r15d
0x18005e143  call    cs:__imp_RegQueryInfoKeyW
0x18005e149  test    eax, eax
0x18005e14b  jnz     loc_18005E6D5
0x18005e151  mov     eax, [rsp+1D0h+cSubKeys]
0x18005e155  lea     r12d, [r15+1]
0x18005e159  mov     edx, r15d; dwIndex
0x18005e15c  mov     [rsp+1D0h+var_154], edx
0x18005e160  add     eax, 0Ah
0x18005e163  jz      loc_18005E4B5
0x18005e169  mov     [rsp+1D0h+lpcValues], r15; lpftLastWriteTime
0x18005e16e  lea     r9, [rbp+0D0h+cchName]; lpcchName
0x18005e172  mov     [rsp+1D0h+lpcbMaxClassLen], r15; lpcchClass
0x18005e177  lea     r8, [rbp+0D0h+Name]; lpName
0x18005e17b  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r15; lpClass
0x18005e180  mov     rcx, r13; hKey
0x18005e183  mov     [rsp+1D0h+lpcSubKeys], r15; lpReserved
0x18005e188  mov     [rbp+0D0h+cchName], 2Ah ; '*'
0x18005e18f  call    cs:__imp_RegEnumKeyExW
0x18005e195  test    eax, eax
0x18005e197  jnz     loc_18005E4E2
0x18005e19d  test    r14b, 10h
0x18005e1a1  jnz     loc_18005E49B
0x18005e1a7  mov     [rsp+1D0h+pcbData], r15d
0x18005e1ac  mov     rdi, r15
0x18005e1af  mov     [rbp+0D0h+pCertContext], r15
0x18005e1b3  mov     [rbp+0D0h+phkResult], r15
0x18005e1b7  bt      r14d, 0Bh
0x18005e1bc  jb      loc_18005E652
0x18005e1c2  mov     [rsp+1D0h+hKey], r15
0x18005e1c7  cmp     r13, 0FFFFFFFF80000001h
0x18005e1ce  jz      loc_18005E50E
0x18005e1d4  mov     rcx, r13; hKey
0x18005e1d7  lea     rax, [rbp+0D0h+phkResult]
0x18005e1db  mov     r9d, 20019h; samDesired
0x18005e1e1  xor     r8d, r8d; ulOptions
0x18005e1e4  mov     [rsp+1D0h+lpcSubKeys], rax; phkResult
0x18005e1e9  lea     rdx, [rbp+0D0h+Name]; lpSubKey
0x18005e1ed  call    cs:__imp_RegOpenKeyExW
0x18005e1f3  mov     rcx, [rsp+1D0h+hKey]; hKey
0x18005e1f8  mov     ebx, eax
0x18005e1fa  test    rcx, rcx
0x18005e1fd  jz      short loc_18005E20E
0x18005e1ff  cmp     rcx, 0FFFFFFFF80000001h
0x18005e206  jz      short loc_18005E20E
0x18005e208  call    cs:__imp_RegCloseKey
0x18005e20e  test    ebx, ebx
0x18005e210  jnz     loc_18005E4F5
0x18005e216  mov     rbx, [rbp+0D0h+phkResult]
0x18005e21a  lea     rax, [rsp+1D0h+cbData]
0x18005e21f  mov     [rsp+1D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18005e224  lea     r9, [rsp+1D0h+hKey]; lpType
0x18005e229  mov     rcx, rbx; hKey
0x18005e22c  mov     [rsp+1D0h+lpcSubKeys], r15; lpData
0x18005e231  xor     r8d, r8d; lpReserved
0x18005e234  mov     dword ptr [rsp+1D0h+hKey], r15d
0x18005e239  lea     rdx, aBlob; "Blob"
0x18005e240  mov     [rsp+1D0h+cbData], r15d
0x18005e245  call    cs:__imp_RegQueryValueExW
0x18005e24b  test    eax, eax
0x18005e24d  jnz     loc_18005E535
0x18005e253  cmp     dword ptr [rsp+1D0h+hKey], 3
0x18005e258  jnz     loc_18005E4EB
0x18005e25e  mov     eax, [rsp+1D0h+cbData]
0x18005e262  cmp     eax, 0FFFFFFh
0x18005e267  ja      loc_18005E4EB
0x18005e26d  lea     edx, [rax+3]; uBytes
0x18005e270  xor     ecx, ecx; uFlags
0x18005e272  call    cs:__imp_LocalAlloc
0x18005e278  mov     rdi, rax
0x18005e27b  test    rax, rax
0x18005e27e  jnz     loc_18005E5E3
0x18005e284  mov     ecx, 8007000Eh; dwErrCode
0x18005e289  call    cs:__imp_SetLastError
0x18005e28f  mov     rcx, rdi; hMem
0x18005e292  mov     ebx, r15d
0x18005e295  call    PkiDefaultCryptFree
0x18005e29a  mov     rdi, r15
0x18005e29d  mov     esi, r15d
0x18005e2a0  mov     qword ptr [rsp+1D0h+cbData], rdi
0x18005e2a5  mov     dword ptr [rsp+1D0h+hKey], esi
0x18005e2a9  test    ebx, ebx
0x18005e2ab  jz      loc_18005E59E
0x18005e2b1  test    esi, esi
0x18005e2b3  jz      loc_18005E59E
0x18005e2b9  mov     r15d, r12d
0x18005e2bc  mov     r14, [rbp+0D0h+phkResult]
0x18005e2c0  test    r14, r14
0x18005e2c3  jz      short loc_18005E2DE
0x18005e2c5  call    cs:__imp_GetLastError
0x18005e2cb  mov     rcx, r14; hKey
0x18005e2ce  mov     ebx, eax
0x18005e2d0  call    cs:__imp_RegCloseKey
0x18005e2d6  mov     ecx, ebx; dwErrCode
0x18005e2d8  call    cs:__imp_SetLastError
0x18005e2de  test    r15d, r15d
0x18005e2e1  jz      loc_18005E64A
0x18005e2e7  mov     r15, [rbp+0D0h+var_138]
0x18005e2eb  lea     rcx, dword_180157FC0
0x18005e2f2  test    r15, r15
0x18005e2f5  mov     [rbp+0D0h+var_130], rdi
0x18005e2f9  mov     rax, r15
0x18005e2fc  mov     [rbp+0D0h+var_128], esi
0x18005e2ff  cmovz   rax, rcx
0x18005e303  mov     [rbp+0D0h+var_124], 0
0x18005e30a  lea     rcx, [rbp+0D0h+pCertContext]
0x18005e30e  xor     r15d, r15d
0x18005e311  mov     dword ptr [rsp+1D0h+lpcbMaxValueLen], r15d; int
0x18005e316  lea     r8, ?SkipInMemory@@YAHPEAXK@Z; int (*)(void *, unsigned int)
0x18005e31d  mov     [rsp+1D0h+lpcbMaxValueNameLen], rcx; void **
0x18005e322  lea     rdx, ?ReadFromMemory@@YAHPEAX0K@Z; int (*)(void *, void *, unsigned int)
0x18005e329  lea     rcx, [rsp+1D0h+pcbData]
0x18005e32e  mov     r9d, esi; unsigned int
0x18005e331  mov     [rsp+1D0h+lpcValues], rcx; unsigned int *
0x18005e336  lea     rcx, [rbp+0D0h+var_130]; void *
0x18005e33a  mov     dword ptr [rsp+1D0h+lpcbMaxClassLen], 0FFFFFFFFh; unsigned int
0x18005e342  mov     dword ptr [rsp+1D0h+lpcbMaxSubKeyLen], 4; unsigned int
0x18005e34a  mov     [rsp+1D0h+lpcSubKeys], rax; struct _CERT_STORE *
0x18005e34f  call    ?LoadStoreElement@@YAKPEAXP6AH00K@ZP6AH0K@ZKPEAU_CERT_STORE@@KKPEAKPEAPEBXH@Z; LoadStoreElement(void *,int (*)(void *,void *,ulong),int (*)(void *,ulong),ulong,_CERT_STORE *,ulong,ulong,ulong *,void const * *,int)
0x18005e354  cmp     eax, r12d
0x18005e357  jnz     loc_18005E547
0x18005e35d  mov     rsi, [rbp+0D0h+pCertContext]
0x18005e361  lea     r8d, [r15+54h]; Size
0x18005e365  xor     edx, edx; Val
0x18005e367  lea     rcx, [rbp+0D0h+String2]; void *
0x18005e36b  call    memset_0
0x18005e370  mov     ebx, [rsp+1D0h+pcbData]
0x18005e374  mov     eax, ebx
0x18005e376  sub     eax, r12d
0x18005e379  jnz     loc_18005E560
0x18005e37f  lea     r9, [rsp+1D0h+pcbData]; pcbData
0x18005e384  mov     [rsp+1D0h+pcbData], 14h
0x18005e38c  lea     r8, [rbp+0D0h+pvData]; pvData
0x18005e390  mov     rcx, rsi; pCertContext
0x18005e393  lea     edx, [rax+3]; dwPropId
0x18005e396  call    CertGetCertificateContextProperty
0x18005e39b  test    eax, eax
0x18005e39d  jz      loc_18005E6EF
0x18005e3a3  mov     r9d, [rsp+1D0h+pcbData]
0x18005e3a8  lea     r8, [rbp+0D0h+String2]
0x18005e3ac  lea     r10, [rbp+0D0h+pvData]
0x18005e3b0  mov     r11d, r15d
0x18005e3b3  test    r9d, r9d
0x18005e3b6  jz      short loc_18005E402
0x18005e3b8  lea     esi, [r15+37h]
0x18005e3bc  lea     r14d, [r15+30h]
0x18005e3c0  movzx   edx, byte ptr [r10]
0x18005e3c4  mov     eax, r14d
0x18005e3c7  mov     ecx, edx
0x18005e3c9  shr     ecx, 4
0x18005e3cc  cmp     ecx, 9
0x18005e3cf  cmova   ax, si
0x18005e3d3  and     edx, 0Fh
0x18005e3d6  add     ax, cx
0x18005e3d9  mov     [r8], ax
0x18005e3dd  cmp     edx, 9
0x18005e3e0  mov     eax, r14d
0x18005e3e3  cmova   ax, si
0x18005e3e7  add     r10, r12
0x18005e3ea  add     ax, dx
0x18005e3ed  add     r11d, r12d
0x18005e3f0  mov     [r8+2], ax
0x18005e3f5  add     r8, 4
0x18005e3f9  cmp     r11d, r9d
0x18005e3fc  jb      short loc_18005E3C0
0x18005e3fe  mov     rsi, [rbp+0D0h+pCertContext]
0x18005e402  mov     [r8], r15w
0x18005e406  mov     eax, r12d
0x18005e409  test    eax, eax
0x18005e40b  jz      short loc_18005E45E
0x18005e40d  or      ecx, 0FFFFFFFFh
0x18005e410  lea     rax, [rbp+0D0h+String2]
0x18005e414  mov     dword ptr [rsp+1D0h+lpcbMaxSubKeyLen], ecx; cchCount2
0x18005e418  lea     r8, [rbp+0D0h+Name]; lpString1
0x18005e41c  mov     r9d, ecx; cchCount1
0x18005e41f  mov     [rsp+1D0h+lpcSubKeys], rax; lpString2
0x18005e424  mov     ecx, 409h; Locale
0x18005e429  mov     edx, r12d; dwCmpFlags
0x18005e42c  call    cs:__imp_CompareStringW
0x18005e432  cmp     eax, 2
0x18005e435  jnz     short loc_18005E453
0x18005e437  sub     ebx, r12d
0x18005e43a  jz      loc_18005E591
0x18005e440  sub     ebx, r12d
0x18005e443  jnz     loc_18005E634
0x18005e449  mov     rcx, rsi; pCertContext
0x18005e44c  call    CertFreeCertificateContext
0x18005e451  jmp     short loc_18005E478
0x18005e453  mov     ecx, 0A1h; dwErrCode
0x18005e458  call    cs:__imp_SetLastError
0x18005e45e  sub     ebx, r12d
0x18005e461  jz      loc_18005E70D
0x18005e467  sub     ebx, r12d
0x18005e46a  jnz     loc_18005E6F7
0x18005e470  mov     rcx, rsi; pCertContext
0x18005e473  call    CertDeleteCTLFromStore
0x18005e478  test    rdi, rdi
0x18005e47b  jz      short loc_18005E496
0x18005e47d  call    cs:__imp_GetLastError
0x18005e483  mov     rcx, rdi; hMem
0x18005e486  mov     ebx, eax
0x18005e488  call    cs:__imp_LocalFree
0x18005e48e  mov     ecx, ebx; dwErrCode
0x18005e490  call    cs:__imp_SetLastError
0x18005e496  mov     r14d, [rsp+1D0h+var_158]
0x18005e49b  mov     edx, [rsp+1D0h+var_154]
0x18005e49f  mov     ecx, [rsp+1D0h+cSubKeys]
0x18005e4a3  add     edx, r12d
0x18005e4a6  add     ecx, 0Ah
0x18005e4a9  mov     [rsp+1D0h+var_154], edx
0x18005e4ad  cmp     edx, ecx
0x18005e4af  jb      loc_18005E169
0x18005e4b5  mov     eax, r12d
0x18005e4b8  mov     rcx, [rbp+0D0h+var_40]
0x18005e4bf  xor     rcx, rsp; StackCookie
0x18005e4c2  call    __security_check_cookie
0x18005e4c7  mov     rbx, [rsp+1D0h+arg_10]
0x18005e4cf  add     rsp, 1A0h
0x18005e4d6  pop     r15
0x18005e4d8  pop     r14
0x18005e4da  pop     r13
0x18005e4dc  pop     r12
0x18005e4de  pop     rdi
0x18005e4df  pop     rsi
0x18005e4e0  pop     rbp
0x18005e4e1  retn
0x18005e4e2  cmp     eax, 103h
0x18005e4e7  jz      short loc_18005E4B5
0x18005e4e9  jmp     short loc_18005E49B
0x18005e4eb  mov     ecx, 80092003h
0x18005e4f0  jmp     loc_18005E289
0x18005e4f5  mov     ecx, ebx; dwErrCode
0x18005e4f7  call    cs:__imp_SetLastError
0x18005e4fd  mov     rcx, rdi; hMem
0x18005e500  call    PkiDefaultCryptFree
0x18005e505  xor     edi, edi
0x18005e507  xor     esi, esi
0x18005e509  jmp     loc_18005E2BC
0x18005e50e  xor     ecx, ecx
0x18005e510  call    I_CryptIsAppContainerToken
0x18005e515  test    eax, eax
0x18005e517  jnz     short loc_18005E57F
0x18005e519  xor     edx, edx
0x18005e51b  lea     rcx, [rsp+1D0h+hKey]; phkResult
0x18005e520  call    RegOpenHKCUEx
0x18005e525  mov     ebx, eax
0x18005e527  test    eax, eax
0x18005e529  jnz     short loc_18005E4F5
0x18005e52b  mov     rcx, [rsp+1D0h+hKey]
0x18005e530  jmp     loc_18005E1D7
0x18005e535  cmp     eax, 0EAh
0x18005e53a  jz      loc_18005E253
0x18005e540  mov     ecx, eax
0x18005e542  jmp     loc_18005E289
0x18005e547  cmp     eax, 2
0x18005e54a  jnz     loc_18005E478
0x18005e550  mov     ecx, 80092004h; dwErrCode
0x18005e555  call    cs:__imp_SetLastError
0x18005e55b  jmp     loc_18005E478
0x18005e560  sub     eax, r12d
0x18005e563  jz      short loc_18005E5D2
0x18005e565  cmp     eax, r12d
0x18005e568  jnz     loc_18005E6E5
0x18005e56e  lea     rdx, [rbp+0D0h+String2]; unsigned __int16 *
0x18005e572  mov     rcx, rsi; struct _CTL_CONTEXT *
0x18005e575  call    ?GetCtlRegValueName@@YAHPEBU_CTL_CONTEXT@@QEAG@Z; GetCtlRegValueName(_CTL_CONTEXT const *,ushort * const)
0x18005e57a  jmp     loc_18005E409
0x18005e57f  lea     rdx, [rsp+1D0h+hKey]
0x18005e584  mov     ecx, 20019h
  ... truncated ...
```
