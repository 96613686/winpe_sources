# GetIkev2ConfigParams

- ea: `0x180076510`
- end: `0x180076e9a`
- name: `GetIkev2ConfigParams`
- size: `2442`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b60`

## callees

- `0x180076380`
- `0x180076420`
- `0x180076510`
- `0x180077148`
- `0x18007717c`
- `0x18007731c`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800767a2`
- `KERNEL32!GetProcessHeap` at `0x1800767f6`
- `KERNEL32!GetProcessHeap` at `0x1800768bb`
- `KERNEL32!GetProcessHeap` at `0x1800769b9`
- `KERNEL32!GetProcessHeap` at `0x1800769e2`
- `KERNEL32!GetProcessHeap` at `0x180076c72`
- `KERNEL32!GetProcessHeap` at `0x180076cca`
- `KERNEL32!GetProcessHeap` at `0x180076d90`
- `KERNEL32!GetProcessHeap` at `0x1800767a2`
- `KERNEL32!GetProcessHeap` at `0x1800767f6`
- `KERNEL32!GetProcessHeap` at `0x1800768bb`
- `KERNEL32!GetProcessHeap` at `0x1800769b9`
- `KERNEL32!GetProcessHeap` at `0x1800769e2`
- `KERNEL32!GetProcessHeap` at `0x180076c72`
- `KERNEL32!GetProcessHeap` at `0x180076cca`
- `KERNEL32!GetProcessHeap` at `0x180076d90`
- `KERNEL32!HeapAlloc` at `0x1800767b6`
- `KERNEL32!HeapAlloc` at `0x18007680a`
- `KERNEL32!HeapAlloc` at `0x1800768cf`
- `KERNEL32!HeapAlloc` at `0x180076c86`
- `KERNEL32!HeapAlloc` at `0x180076cde`
- `KERNEL32!HeapAlloc` at `0x180076da4`
- `KERNEL32!HeapAlloc` at `0x1800767b6`
- `KERNEL32!HeapAlloc` at `0x18007680a`
- `KERNEL32!HeapAlloc` at `0x1800768cf`
- `KERNEL32!HeapAlloc` at `0x180076c86`
- `KERNEL32!HeapAlloc` at `0x180076cde`
- `KERNEL32!HeapAlloc` at `0x180076da4`
- `KERNEL32!GetLastError` at `0x1800767ce`
- `KERNEL32!GetLastError` at `0x18007681f`
- `KERNEL32!GetLastError` at `0x180076c9e`
- `KERNEL32!GetLastError` at `0x1800767ce`
- `KERNEL32!GetLastError` at `0x18007681f`
- `KERNEL32!GetLastError` at `0x180076c9e`
- `KERNEL32!HeapFree` at `0x1800769cd`
- `KERNEL32!HeapFree` at `0x1800769f6`
- `KERNEL32!HeapFree` at `0x1800769cd`
- `KERNEL32!HeapFree` at `0x1800769f6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076764`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076c2a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076764`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180076c2a`
- `ADVAPI32!RegOpenKeyExW` at `0x180076700`
- `ADVAPI32!RegOpenKeyExW` at `0x180076a7d`
- `ADVAPI32!RegOpenKeyExW` at `0x180076bc5`
- `ADVAPI32!RegOpenKeyExW` at `0x180076700`
- `ADVAPI32!RegOpenKeyExW` at `0x180076a7d`
- `ADVAPI32!RegOpenKeyExW` at `0x180076bc5`
- `ADVAPI32!RegQueryValueExW` at `0x180076661`
- `ADVAPI32!RegQueryValueExW` at `0x1800766b8`
- `ADVAPI32!RegQueryValueExW` at `0x180076b38`
- `ADVAPI32!RegQueryValueExW` at `0x180076661`
- `ADVAPI32!RegQueryValueExW` at `0x1800766b8`
- `ADVAPI32!RegQueryValueExW` at `0x180076b38`
- `ADVAPI32!RegCloseKey` at `0x180076a0b`
- `ADVAPI32!RegCloseKey` at `0x180076a20`
- `ADVAPI32!RegCloseKey` at `0x180076aab`
- `ADVAPI32!RegCloseKey` at `0x180076a0b`
- `ADVAPI32!RegCloseKey` at `0x180076a20`
- `ADVAPI32!RegCloseKey` at `0x180076aab`
- `ADVAPI32!RegEnumKeyW` at `0x180076852`
- `ADVAPI32!RegEnumKeyW` at `0x180076d20`
- `ADVAPI32!RegEnumKeyW` at `0x180076852`
- `ADVAPI32!RegEnumKeyW` at `0x180076d20`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076898`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076911`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076d68`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076de3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076e37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076898`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076911`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076d68`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076de3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180076e37`

## string_xrefs

- `0x1800765bc`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall GetIkev2ConfigParams(HKEY hkey, char a2, __int64 a3, unsigned int a4)
{
  WCHAR *v4; // rbx
  void *v6; // r12
  char v8; // r14
  DWORD LastError; // edi
  bool v10; // cf
  unsigned int v11; // esi
  const WCHAR **v12; // rbx
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  DWORD v16; // edx
  unsigned int v17; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v19; // ebx
  HANDLE v20; // rax
  DWORD v21; // esi
  DWORD *pcbData; // r14
  DWORD v23; // ebx
  HANDLE v24; // rax
  void *v25; // rax
  __int128 v26; // xmm1
  void *v27; // rbx
  HANDLE v28; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  HKEY v32; // rcx
  LSTATUS v33; // eax
  DWORD Binary; // eax
  LSTATUS v35; // eax
  DWORD v36; // eax
  LSTATUS v37; // eax
  DWORD v38; // eax
  unsigned int v39; // edx
  unsigned int v40; // ebx
  HANDLE v41; // rax
  WCHAR *v42; // r15
  DWORD v43; // ebx
  HANDLE v44; // rax
  void *v45; // rax
  DWORD v46; // esi
  DWORD *v47; // r14
  DWORD v48; // ebx
  HANDLE v49; // rax
  void *v50; // rax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  int Size; // [rsp+60h] [rbp-A0h] BYREF
  char Size_4; // [rsp+64h] [rbp-9Ch]
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbData; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD Type; // [rsp+70h] [rbp-90h] BYREF
  DWORD v57; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD v58; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR lpName; // [rsp+80h] [rbp-80h]
  DWORD pdwType; // [rsp+88h] [rbp-78h] BYREF
  HKEY pvData; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID v65; // [rsp+B0h] [rbp-50h]
  LPVOID v66; // [rsp+B8h] [rbp-48h]
  LPVOID lpMem; // [rsp+C0h] [rbp-40h]
  __int128 v68; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v69; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v70[10]; // [rsp+F0h] [rbp-10h] BYREF

  phkResult = 0;
  hKey = 0;
  v4 = 0;
  cSubKeys = 0;
  v58 = 0;
  lpMem = 0;
  v6 = 0;
  v65 = 0;
  v66 = 0;
  cbData = 0;
  Type = 0;
  v70[0] = L"idleTimeout";
  v70[1] = &v68;
  v70[2] = L"networkBlackoutTime";
  v70[3] = (char *)&v68 + 4;
  v70[4] = L"saLifeTime";
  v70[5] = (char *)&v68 + 8;
  v70[6] = L"saDataSize";
  v70[7] = (char *)&v68 + 12;
  v8 = a2;
  v70[8] = L"ConfigOptions";
  Size_4 = a2;
  v70[9] = &v69;
  lpName = 0;
  v68 = 0;
  v69 = 0;
  switch ( a2 )
  {
    case 1:
      v10 = a4 < 0x20;
      break;
    case 2:
      v10 = a4 < 0x40;
      break;
    case 3:
    case 4:
      v10 = a4 < 0x60;
      break;
    case 5:
      v10 = a4 < 0x68;
      break;
    default:
      LastError = 50;
LABEL_50:
      FreeEkus(v65);
      FreeEkus(v66);
      goto LABEL_51;
  }
  if ( v10 )
  {
LABEL_9:
    LastError = 87;
    goto LABEL_50;
  }
  v11 = 0;
  v12 = (const WCHAR **)v70;
  do
  {
    v13 = *v12;
    lpData = (BYTE *)v12[1];
    cbData = 4;
    Type = 4;
    LastError = RegQueryValueExW(hkey, v13, 0, &Type, lpData, &cbData);
    if ( LastError )
      goto LABEL_49;
    ++v11;
    v12 += 2;
  }
  while ( v11 < 5 );
  if ( v8 >= 5 )
  {
    cbData = 4;
    Type = 4;
    v14 = RegQueryValueExW(hkey, L"mmSaLifeTime", 0, &Type, (LPBYTE)(a3 + 96), &cbData);
    LastError = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
        goto LABEL_49;
      *(_DWORD *)(a3 + 96) = 28800;
    }
  }
  cbMaxSubKeyLen = 0;
  pdwType = 3;
  v15 = RegOpenKeyExW(hkey, L"AllowedTrustedRootCerts", 0, 0x20019u, &phkResult);
  LastError = v15;
  if ( !v15 )
  {
    LastError = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !LastError )
    {
      if ( cSubKeys )
      {
        v16 = -1;
        if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
          v16 = cbMaxSubKeyLen + 1;
        if ( 2 * (unsigned __int64)v16 > 0xFFFFFFFF )
        {
          LastError = -2147024362;
          goto LABEL_49;
        }
        v17 = 2 * v16;
        ProcessHeap = GetProcessHeap();
        lpName = (LPWSTR)HeapAlloc(ProcessHeap, 0, v17);
        v4 = lpName;
        if ( !lpName )
        {
          LastError = GetLastError();
          goto LABEL_106;
        }
        if ( 16 * (unsigned __int64)cSubKeys > 0xFFFFFFFF )
        {
          LastError = -2147024362;
          goto LABEL_50;
        }
        LastError = 0;
        v19 = 16 * cSubKeys;
        v20 = GetProcessHeap();
        v65 = HeapAlloc(v20, 0, v19);
        if ( !v65 )
        {
LABEL_32:
          LastError = GetLastError();
          goto LABEL_105;
        }
        v21 = 0;
        if ( cSubKeys )
        {
          v4 = lpName;
          while ( 1 )
          {
            LastError = RegEnumKeyW(phkResult, v21, v4, cbMaxSubKeyLen + 1);
            if ( LastError )
              goto LABEL_50;
            pcbData = (DWORD *)((char *)v65 + 16 * v21);
            LastError = RegGetValueW(phkResult, v4, L"TrustedRootCert", 8u, &pdwType, 0, pcbData);
            if ( LastError )
              goto LABEL_50;
            if ( pdwType != 3 )
              goto LABEL_9;
            v23 = *pcbData;
            v24 = GetProcessHeap();
            v25 = HeapAlloc(v24, 0, v23);
            *((_QWORD *)pcbData + 1) = v25;
            if ( !v25 )
              goto LABEL_32;
            v4 = lpName;
            LastError = RegGetValueW(phkResult, lpName, L"TrustedRootCert", 8u, &pdwType, v25, pcbData);
            if ( LastError )
              goto LABEL_50;
            if ( pdwType != 3 )
              goto LABEL_9;
            if ( ++v21 >= cSubKeys )
            {
              v8 = Size_4;
              break;
            }
          }
        }
      }
      DWORD1(v69) = cSubKeys;
      *((_QWORD *)&v69 + 1) = v65;
      goto LABEL_44;
    }
LABEL_49:
    v4 = 0;
    goto LABEL_50;
  }
  if ( v15 != 2 )
    goto LABEL_49;
  LastError = 0;
LABEL_44:
  v26 = v69;
  *(_OWORD *)a3 = v68;
  *(_OWORD *)(a3 + 16) = v26;
  if ( v8 >= 2 )
  {
    v6 = (void *)MprCommonAlloc(24);
    v27 = v6;
    if ( !v6 )
    {
      v4 = lpName;
      LastError = 8;
      goto LABEL_50;
    }
    v32 = 0;
    pvData = 0;
    if ( hkey )
    {
      v33 = RegOpenKeyExW(hkey, L"IKEv2CustomPolicy", 0, 0x20019u, &pvData);
      v32 = pvData;
      LastError = v33;
      if ( !v33 )
      {
        GetCustomPolicyRegParams(pvData, v6);
        v32 = pvData;
      }
    }
    else
    {
      LastError = 87;
    }
    if ( v32 )
      RegCloseKey(v32);
    if ( LastError )
    {
      if ( LastError != 2 )
      {
LABEL_104:
        MprCommonFree(v6);
        goto LABEL_105;
      }
      v27 = 0;
    }
    else
    {
      v6 = 0;
    }
    *(_QWORD *)(a3 + 56) = v27;
    Binary = RegGetBinary(hkey, L"MachineCertificateName", a3 + 32, a3 + 40);
    LastError = Binary;
    if ( Binary )
    {
      if ( Binary != 2 )
        goto LABEL_103;
      *(_DWORD *)(a3 + 32) = 0;
      *(_QWORD *)(a3 + 40) = 0;
    }
    cbData = 4;
    Type = 4;
    v35 = RegQueryValueExW(hkey, L"EncryptionType", 0, &Type, (LPBYTE)(a3 + 48), &cbData);
    LastError = v35;
    if ( v35 )
    {
      if ( v35 != 2 )
        goto LABEL_103;
      LastError = 0;
      *(_DWORD *)(a3 + 48) = 2;
    }
  }
  if ( v8 >= 3 )
  {
    LODWORD(pvData) = 0;
    Size = 0;
    v57 = 1;
    v36 = RegGetBinary(hkey, L"MachineCertificateHash", a3 + 80, a3 + 88);
    LastError = v36;
    if ( v36 )
    {
      if ( v36 != 2 )
        goto LABEL_103;
      *(_DWORD *)(a3 + 80) = 0;
      *(_QWORD *)(a3 + 88) = 0;
    }
    v37 = RegOpenKeyExW(hkey, L"AllowedCertEku", 0, 0x20019u, &hKey);
    LastError = v37;
    if ( v37 )
    {
      if ( v37 == 2 )
        LastError = 0;
      goto LABEL_103;
    }
    LastError = RegQueryInfoKeyW(hKey, 0, 0, 0, &v58, (LPDWORD)&pvData, 0, 0, 0, 0, 0, 0);
    if ( LastError )
      goto LABEL_103;
    v38 = v58;
    if ( !v58 )
      goto LABEL_102;
    v39 = -1;
    if ( (int)pvData + 1 >= (unsigned int)pvData )
      v39 = (_DWORD)pvData + 1;
    if ( 2 * (unsigned __int64)v39 > 0xFFFFFFFF )
      goto LABEL_109;
    v40 = 2 * v39;
    Size = 2 * v39;
    v41 = GetProcessHeap();
    lpMem = HeapAlloc(v41, 0, v40);
    v42 = (WCHAR *)lpMem;
    if ( !lpMem )
    {
LABEL_89:
      LastError = GetLastError();
      goto LABEL_103;
    }
    if ( 16 * (unsigned __int64)v58 > 0xFFFFFFFF )
    {
LABEL_109:
      Size = -1;
      LastError = -2147024362;
      goto LABEL_103;
    }
    v43 = 16 * v58;
    LastError = 0;
    Size = 16 * v58;
    v44 = GetProcessHeap();
    v45 = HeapAlloc(v44, 0, v43);
    v66 = v45;
    if ( !v45 )
      goto LABEL_89;
    memset_0(v45, 0, (unsigned int)Size);
    v38 = v58;
    v46 = 0;
    if ( !v58 )
    {
LABEL_102:
      *(_DWORD *)(a3 + 64) = v38;
      *(_QWORD *)(a3 + 72) = v66;
      goto LABEL_103;
    }
    while ( 1 )
    {
      LastError = RegEnumKeyW(hKey, v46, v42, (_DWORD)pvData + 1);
      if ( LastError )
        break;
      v47 = (DWORD *)((char *)v66 + 16 * v46);
      LastError = RegGetValueW(hKey, v42, L"TrustedEku", 2u, &v57, 0, v47);
      if ( LastError )
        break;
      if ( v57 != 1 )
        goto LABEL_108;
      Size = *v47;
      v48 = Size;
      v49 = GetProcessHeap();
      v50 = HeapAlloc(v49, 0, v48);
      *((_QWORD *)v47 + 1) = v50;
      if ( !v50 )
        goto LABEL_89;
      LastError = RegGetValueW(hKey, v42, L"TrustedEku", 2u, &v57, v50, v47);
      if ( LastError )
        break;
      if ( v57 != 1 )
        goto LABEL_108;
      Size = 4;
      LastError = RegGetValueW(hKey, v42, L"IsEkuOID", 0x10u, &v57, v47 + 1, (LPDWORD)&Size);
      if ( LastError )
        break;
      if ( v57 != 4 )
      {
LABEL_108:
        LastError = 87;
        break;
      }
      v38 = v58;
      if ( ++v46 >= v58 )
        goto LABEL_102;
    }
  }
LABEL_103:
  if ( v6 )
    goto LABEL_104;
LABEL_105:
  v4 = lpName;
LABEL_106:
  if ( LastError )
    goto LABEL_50;
LABEL_51:
  if ( v4 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v4);
  }
  v29 = lpMem;
  if ( lpMem )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
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
0x180076510  mov     [rsp-8+arg_8], rbx
0x180076515  push    rbp
0x180076516  push    rsi
0x180076517  push    rdi
0x180076518  push    r12
0x18007651a  push    r13
0x18007651c  push    r14
0x18007651e  push    r15
0x180076520  lea     rbp, [rsp-50h]
0x180076525  sub     rsp, 150h
0x18007652c  mov     rax, cs:__security_cookie
0x180076533  xor     rax, rsp
0x180076536  mov     [rbp+80h+var_40], rax
0x18007653a  and     [rbp+80h+phkResult], 0
0x18007653f  lea     rax, aIdletimeout; "idleTimeout"
0x180076546  and     [rbp+80h+hKey], 0
0x18007654b  xor     ebx, ebx
0x18007654d  and     [rsp+180h+cSubKeys], 0
0x180076552  mov     r15, rcx
0x180076555  and     [rsp+180h+var_108], 0
0x18007655a  xorps   xmm0, xmm0
0x18007655d  and     [rbp+80h+lpMem], rbx
0x180076561  xor     r12d, r12d
0x180076564  and     [rbp+80h+var_D0], rbx
0x180076568  mov     r13, r8
0x18007656b  and     [rbp+80h+var_C8], rbx
0x18007656f  and     [rsp+180h+cbData], ebx
0x180076573  and     [rsp+180h+Type], ebx
0x180076577  mov     [rbp+80h+var_90], rax
0x18007657b  lea     rax, [rbp+80h+var_B8]
0x18007657f  mov     [rbp+80h+var_88], rax
0x180076583  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x18007658a  mov     [rbp+80h+var_80], rax
0x18007658e  lea     rax, [rbp+80h+var_B8+4]
0x180076592  mov     [rbp+80h+var_78], rax
0x180076596  lea     rax, aSalifetime; "saLifeTime"
0x18007659d  mov     [rbp+80h+var_70], rax
0x1800765a1  lea     rax, [rbp+80h+var_B8+8]
0x1800765a5  mov     [rbp+80h+var_68], rax
0x1800765a9  lea     rax, aSadatasize; "saDataSize"
0x1800765b0  mov     [rbp+80h+var_60], rax
0x1800765b4  lea     rax, [rbp+80h+var_B8+0Ch]
0x1800765b8  mov     [rbp+80h+var_58], rax
0x1800765bc  lea     rax, aConfigoptions; "ConfigOptions"
0x1800765c3  movsx   r14d, dl
0x1800765c7  mov     [rbp+80h+var_50], rax
0x1800765cb  mov     ecx, r14d
0x1800765ce  mov     byte ptr [rsp+180h+Size+4], r14b
0x1800765d3  lea     rax, [rbp+80h+var_A8]
0x1800765d7  mov     [rbp+80h+var_48], rax
0x1800765db  mov     [rbp+80h+lpName], rbx
0x1800765df  movups  [rbp+80h+var_B8], xmm0
0x1800765e3  movups  [rbp+80h+var_A8], xmm0
0x1800765e7  sub     ecx, 1
0x1800765ea  jz      short loc_180076624
0x1800765ec  sub     ecx, 1
0x1800765ef  jz      short loc_18007661E
0x1800765f1  sub     ecx, 1
0x1800765f4  jz      short loc_180076618
0x1800765f6  sub     ecx, 1
0x1800765f9  jz      short loc_180076618
0x1800765fb  cmp     ecx, 1
0x1800765fe  jz      short loc_180076608
0x180076600  lea     edi, [rbx+32h]
0x180076603  jmp     loc_18007699A
0x180076608  cmp     r9d, 68h ; 'h'
0x18007660c  jnb     short loc_18007662A
0x18007660e  mov     edi, 57h ; 'W'
0x180076613  jmp     loc_18007699A
0x180076618  cmp     r9d, 60h ; '`'
0x18007661c  jmp     short loc_18007660C
0x18007661e  cmp     r9d, 40h ; '@'
0x180076622  jmp     short loc_18007660C
0x180076624  cmp     r9d, 20h ; ' '
0x180076628  jmp     short loc_18007660C
0x18007662a  xor     esi, esi
0x18007662c  lea     rbx, [rbp+80h+var_90]
0x180076630  mov     rdx, [rbx]; lpValueName
0x180076633  lea     rax, [rsp+180h+cbData]
0x180076638  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18007663d  lea     r9, [rsp+180h+Type]; lpType
0x180076642  mov     rax, [rbx+8]
0x180076646  xor     r8d, r8d; lpReserved
0x180076649  mov     rcx, r15; hKey
0x18007664c  mov     [rsp+180h+lpData], rax; lpData
0x180076651  mov     [rsp+180h+cbData], 4
0x180076659  mov     [rsp+180h+Type], 4
0x180076661  call    cs:__imp_RegQueryValueExW
0x180076668  nop     dword ptr [rax+rax+00h]
0x18007666d  mov     edi, eax
0x18007666f  test    eax, eax
0x180076671  jnz     loc_180076997
0x180076677  inc     esi
0x180076679  add     rbx, 10h
0x18007667d  cmp     esi, 5
0x180076680  jb      short loc_180076630
0x180076682  cmp     r14b, 5
0x180076686  jl      short loc_1800766D9
0x180076688  lea     eax, [rdi+4]
0x18007668b  xor     r8d, r8d; lpReserved
0x18007668e  mov     [rsp+180h+cbData], eax
0x180076692  lea     rbx, [r13+60h]
0x180076696  mov     [rsp+180h+Type], eax
0x18007669a  lea     r9, [rsp+180h+Type]; lpType
0x18007669f  lea     rax, [rsp+180h+cbData]
0x1800766a4  mov     rcx, r15; hKey
0x1800766a7  mov     [rsp+180h+lpcbData], rax; lpcbData
0x1800766ac  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x1800766b3  mov     [rsp+180h+lpData], rbx; lpData
0x1800766b8  call    cs:__imp_RegQueryValueExW
0x1800766bf  nop     dword ptr [rax+rax+00h]
0x1800766c4  mov     edi, eax
0x1800766c6  test    eax, eax
0x1800766c8  jz      short loc_1800766D9
0x1800766ca  cmp     eax, 2
0x1800766cd  jnz     loc_180076997
0x1800766d3  mov     dword ptr [rbx], 7080h
0x1800766d9  and     [rbp+80h+cbMaxSubKeyLen], r12d
0x1800766dd  lea     rax, [rbp+80h+phkResult]
0x1800766e1  mov     r9d, 20019h; samDesired
0x1800766e7  mov     [rsp+180h+lpData], rax; phkResult
0x1800766ec  xor     r8d, r8d; ulOptions
0x1800766ef  mov     [rbp+80h+pdwType], 3
0x1800766f6  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x1800766fd  mov     rcx, r15; hKey
0x180076700  call    cs:__imp_RegOpenKeyExW
0x180076707  nop     dword ptr [rax+rax+00h]
0x18007670c  mov     edi, eax
0x18007670e  mov     esi, 0FFFFFFFFh
0x180076713  test    eax, eax
0x180076715  jz      short loc_180076727
0x180076717  cmp     eax, 2
0x18007671a  jnz     loc_180076997
0x180076720  xor     edi, edi
0x180076722  jmp     loc_18007694D
0x180076727  and     [rsp+180h+var_128], r12
0x18007672c  lea     rax, [rbp+80h+cbMaxSubKeyLen]
0x180076730  and     [rsp+180h+var_130], r12
0x180076735  xor     r9d, r9d; lpReserved
0x180076738  and     [rsp+180h+var_138], r12
0x18007673d  xor     r8d, r8d; lpcchClass
0x180076740  and     [rsp+180h+var_140], r12
0x180076745  xor     edx, edx; lpClass
0x180076747  and     [rsp+180h+var_148], r12
0x18007674c  and     [rsp+180h+pcbData], r12
0x180076751  mov     rcx, [rbp+80h+phkResult]; hKey
0x180076755  mov     [rsp+180h+lpcbData], rax; pvData
0x18007675a  lea     rax, [rsp+180h+cSubKeys]
0x18007675f  mov     [rsp+180h+lpData], rax; lpcSubKeys
0x180076764  call    cs:__imp_RegQueryInfoKeyW
0x18007676b  nop     dword ptr [rax+rax+00h]
0x180076770  mov     edi, eax
0x180076772  test    eax, eax
0x180076774  jnz     loc_180076997
0x18007677a  cmp     [rsp+180h+cSubKeys], r12d
0x18007677f  jz      loc_18007693E
0x180076785  mov     eax, [rbp+80h+cbMaxSubKeyLen]
0x180076788  mov     edx, esi
0x18007678a  lea     ecx, [rax+1]
0x18007678d  cmp     ecx, eax
0x18007678f  cmovnb  edx, ecx
0x180076792  mov     eax, edx
0x180076794  add     rax, rax
0x180076797  cmp     rax, rsi
0x18007679a  ja      loc_180076992
0x1800767a0  mov     ebx, eax
0x1800767a2  call    cs:__imp_GetProcessHeap
0x1800767a9  nop     dword ptr [rax+rax+00h]
0x1800767ae  mov     r8d, ebx; dwBytes
0x1800767b1  xor     edx, edx; dwFlags
0x1800767b3  mov     rcx, rax; hHeap
0x1800767b6  call    cs:__imp_HeapAlloc
0x1800767bd  nop     dword ptr [rax+rax+00h]
0x1800767c2  mov     [rbp+80h+lpName], rax
0x1800767c6  mov     rbx, rax
0x1800767c9  test    rax, rax
0x1800767cc  jnz     short loc_1800767E1
0x1800767ce  call    cs:__imp_GetLastError
0x1800767d5  nop     dword ptr [rax+rax+00h]
0x1800767da  mov     edi, eax
0x1800767dc  jmp     loc_180076E7B
0x1800767e1  mov     eax, [rsp+180h+cSubKeys]
0x1800767e5  shl     rax, 4
0x1800767e9  cmp     rax, rsi
0x1800767ec  ja      loc_18007698B
0x1800767f2  xor     edi, edi
0x1800767f4  mov     ebx, eax
0x1800767f6  call    cs:__imp_GetProcessHeap
0x1800767fd  nop     dword ptr [rax+rax+00h]
0x180076802  mov     r8d, ebx; dwBytes
0x180076805  xor     edx, edx; dwFlags
0x180076807  mov     rcx, rax; hHeap
0x18007680a  call    cs:__imp_HeapAlloc
0x180076811  nop     dword ptr [rax+rax+00h]
0x180076816  mov     [rbp+80h+var_D0], rax
0x18007681a  test    rax, rax
0x18007681d  jnz     short loc_180076832
0x18007681f  call    cs:__imp_GetLastError
0x180076826  nop     dword ptr [rax+rax+00h]
0x18007682b  mov     edi, eax
0x18007682d  jmp     loc_180076E77
0x180076832  xor     esi, esi
0x180076834  cmp     [rsp+180h+cSubKeys], esi
0x180076838  jbe     loc_18007693E
0x18007683e  mov     rbx, [rbp+80h+lpName]
0x180076842  mov     r9d, [rbp+80h+cbMaxSubKeyLen]
0x180076846  mov     r8, rbx; lpName
0x180076849  mov     rcx, [rbp+80h+phkResult]; hKey
0x18007684d  inc     r9d; cchName
0x180076850  mov     edx, esi; dwIndex
0x180076852  call    cs:__imp_RegEnumKeyW
0x180076859  nop     dword ptr [rax+rax+00h]
0x18007685e  mov     edi, eax
0x180076860  test    eax, eax
0x180076862  jnz     loc_18007699A
0x180076868  mov     rcx, [rbp+80h+phkResult]; hkey
0x18007686c  lea     rax, [rbp+80h+pdwType]
0x180076870  mov     r14d, esi
0x180076873  lea     r9d, [rdi+8]; dwFlags
0x180076877  shl     r14, 4
0x18007687b  lea     r8, Value; "TrustedRootCert"
0x180076882  add     r14, [rbp+80h+var_D0]
0x180076886  mov     rdx, rbx; lpSubKey
0x180076889  mov     [rsp+180h+pcbData], r14; pcbData
0x18007688e  and     [rsp+180h+lpcbData], r12
0x180076893  mov     [rsp+180h+lpData], rax; pdwType
0x180076898  call    cs:__imp_RegGetValueW
0x18007689f  nop     dword ptr [rax+rax+00h]
0x1800768a4  mov     edi, eax
0x1800768a6  test    eax, eax
0x1800768a8  jnz     loc_18007699A
0x1800768ae  cmp     [rbp+80h+pdwType], 3
0x1800768b2  jnz     loc_18007660E
0x1800768b8  mov     ebx, [r14]
0x1800768bb  call    cs:__imp_GetProcessHeap
0x1800768c2  nop     dword ptr [rax+rax+00h]
0x1800768c7  mov     r8d, ebx; dwBytes
0x1800768ca  xor     edx, edx; dwFlags
0x1800768cc  mov     rcx, rax; hHeap
0x1800768cf  call    cs:__imp_HeapAlloc
0x1800768d6  nop     dword ptr [rax+rax+00h]
0x1800768db  mov     [r14+8], rax
0x1800768df  test    rax, rax
0x1800768e2  jz      loc_18007681F
0x1800768e8  mov     rbx, [rbp+80h+lpName]
0x1800768ec  lea     r9d, [rdi+8]; dwFlags
0x1800768f0  mov     rcx, [rbp+80h+phkResult]; hkey
0x1800768f4  lea     r8, Value; "TrustedRootCert"
0x1800768fb  mov     [rsp+180h+pcbData], r14; lpcbMaxClassLen
0x180076900  mov     rdx, rbx; lpSubKey
0x180076903  mov     [rsp+180h+lpcbData], rax; pvData
0x180076908  lea     rax, [rbp+80h+pdwType]
0x18007690c  mov     [rsp+180h+lpData], rax; pdwType
0x180076911  call    cs:__imp_RegGetValueW
0x180076918  nop     dword ptr [rax+rax+00h]
0x18007691d  mov     edi, eax
0x18007691f  test    eax, eax
0x180076921  jnz     short loc_18007699A
0x180076923  cmp     [rbp+80h+pdwType], 3
0x180076927  jnz     loc_18007660E
0x18007692d  inc     esi
0x18007692f  cmp     esi, [rsp+180h+cSubKeys]
0x180076933  jb      loc_180076842
0x180076939  mov     r14b, byte ptr [rsp+180h+Size+4]
0x18007693e  mov     eax, [rsp+180h+cSubKeys]
0x180076942  mov     dword ptr [rbp+80h+var_A8+4], eax
0x180076945  mov     rax, [rbp+80h+var_D0]
0x180076949  mov     qword ptr [rbp+80h+var_A8+8], rax
0x18007694d  movups  xmm0, [rbp+80h+var_B8]
0x180076951  movups  xmm1, [rbp+80h+var_A8]
0x180076955  movups  xmmword ptr [r13+0], xmm0
0x18007695a  movups  xmmword ptr [r13+10h], xmm1
0x18007695f  cmp     r14b, 2
0x180076963  jl      loc_180076B57
0x180076969  mov     ecx, 18h
0x18007696e  call    MprCommonAlloc
0x180076973  mov     r12, rax
0x180076976  mov     rbx, rax
0x180076979  test    rax, rax
0x18007697c  jnz     loc_180076A56
0x180076982  mov     rbx, [rbp+80h+lpName]
0x180076986  lea     edi, [rax+8]
0x180076989  jmp     short loc_18007699A
0x18007698b  mov     edi, 80070216h
0x180076990  jmp     short loc_18007699A
0x180076992  mov     edi, 80070216h
0x180076997  mov     rbx, r12
0x18007699a  mov     edx, [rsp+180h+cSubKeys]
0x18007699e  mov     rcx, [rbp+80h+var_D0]; lpMem
0x1800769a2  call    FreeEkus
0x1800769a7  mov     edx, [rsp+180h+var_108]
0x1800769ab  mov     rcx, [rbp+80h+var_C8]; lpMem
0x1800769af  call    FreeEkus
0x1800769b4  test    rbx, rbx
0x1800769b7  jz      short loc_1800769D9
0x1800769b9  call    cs:__imp_GetProcessHeap
0x1800769c0  nop     dword ptr [rax+rax+00h]
0x1800769c5  mov     r8, rbx; lpMem
0x1800769c8  xor     edx, edx; dwFlags
0x1800769ca  mov     rcx, rax; hHeap
  ... truncated ...
```
