# GetProtectedRootInfo

- ea: `0x180059698`
- end: `0x1800599a2`
- name: `GetProtectedRootInfo`
- size: `778`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005a148`
- `0x1800b2730`

## callees

- `0x180028d60`
- `0x180059698`
- `0x1800599a8`
- `0x180059b78`
- `0x180059bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005990f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005990f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059965`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005995f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005995f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059997`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005972a`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005972a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005988b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005988b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059970`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059870`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059709`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180059709`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180059947`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180059947`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180059789`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800598d1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180059789`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800598d1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180059749`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180059749`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800597cf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800597f3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800598f3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800597cf`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800597f3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800598f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180059823`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180059823`

## pseudocode

```c
__int64 __fastcall GetProtectedRootInfo(__int64 a1, unsigned int a2, HKEY *a3, _QWORD *a4)
{
  HKEY v4; // r14
  HLOCAL v7; // r15
  LSTATUS KeySecurity; // eax
  DWORD LastError; // edi
  PACL v10; // rcx
  DWORD v11; // r12d
  DWORD v12; // ebx
  DWORD v13; // r13d
  DWORD i; // esi
  PACL v15; // rcx
  DWORD v16; // r12d
  DWORD j; // esi
  void *ProtectedRootInfo; // rsi
  HLOCAL v20; // rax
  DWORD v21; // ecx
  DWORD cbSecurityDescriptor; // [rsp+20h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+24h] [rbp-2Ch] BYREF
  WINBOOL bDaclPresent; // [rsp+28h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pAce[2]; // [rsp+40h] [rbp-10h] BYREF

  v4 = 0;
  pDacl = 0;
  pSacl = 0;
  v7 = 0;
  cbSecurityDescriptor = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( (unsigned int)GetPredefinedSids(a1)
    && (v4 = (HKEY)OpenProtectedRootSubKey(a1, a2)) != 0
    && (cbSecurityDescriptor = 1024, (v7 = LocalAlloc(0x40u, 0x400u)) != 0) )
  {
    while ( 1 )
    {
      KeySecurity = RegGetKeySecurity(v4, 0x14u, v7, &cbSecurityDescriptor);
      LastError = KeySecurity;
      if ( !KeySecurity )
        break;
      if ( KeySecurity != 122 )
      {
        v21 = KeySecurity;
        goto LABEL_50;
      }
      v20 = LocalReAlloc(v7, cbSecurityDescriptor, 0x40u);
      if ( !v20 )
        goto LABEL_44;
      v7 = v20;
    }
    if ( !GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      goto LABEL_51;
    v10 = pDacl;
    if ( !pDacl )
      goto LABEL_49;
    v11 = 0;
    v12 = LastError + 1;
    v13 = 0;
    for ( i = 0; i < v10->AceCount; i += v12 )
    {
      pAce[0] = 0;
      if ( !GetAce(v10, i, pAce) || *(_BYTE *)pAce[0] || *((_BYTE *)pAce[0] + 1) != 2 )
        goto LABEL_49;
      if ( *((_DWORD *)pAce[0] + 1) == 131097 )
      {
        if ( EqualSid(pSid, (char *)pAce[0] + 8) )
          v13 = LastError + 1;
      }
      else
      {
        if ( *((_DWORD *)pAce[0] + 1) != 983103 || !EqualSid(Sid, (char *)pAce[0] + 8) )
          goto LABEL_49;
        v11 = LastError + 1;
      }
      v10 = pDacl;
    }
    if ( v11 && v13 )
    {
      if ( !GetSecurityDescriptorSacl(v7, &bDaclPresent, &pSacl, &bDaclDefaulted) )
        goto LABEL_51;
      v15 = pSacl;
      if ( !pSacl )
        goto LABEL_56;
      v16 = 0;
      for ( j = 0; j < v15->AceCount; j += v12 )
      {
        pAce[0] = 0;
        if ( !GetAce(v15, j, pAce) )
          goto LABEL_56;
        if ( *(_BYTE *)pAce[0] == 17 )
        {
          if ( !EqualSid(qword_18015D618, (char *)pAce[0] + 8) )
            goto LABEL_56;
          v16 = LastError + 1;
        }
        v15 = pSacl;
      }
      if ( v16 )
      {
        ProtectedRootInfo = (void *)ReadProtectedRootInfo(v4);
        if ( ProtectedRootInfo )
          goto LABEL_27;
        v21 = 13;
      }
      else
      {
LABEL_56:
        v21 = 1299;
      }
    }
    else
    {
LABEL_49:
      v21 = 1336;
    }
LABEL_50:
    SetLastError(v21);
LABEL_51:
    LastError = GetLastError();
  }
  else
  {
    LastError = GetLastError();
    if ( !v4 )
      goto LABEL_43;
  }
  RegCloseKey(v4);
  v4 = 0;
LABEL_43:
  PkiDefaultCryptFree(0);
LABEL_44:
  ProtectedRootInfo = 0;
  v12 = 0;
LABEL_27:
  if ( v7 )
    LocalFree(v7);
  if ( a3 )
  {
    *a3 = v4;
  }
  else if ( v4 )
  {
    RegCloseKey(v4);
  }
  if ( a4 )
    *a4 = ProtectedRootInfo;
  else
    PkiDefaultCryptFree(ProtectedRootInfo);
  if ( !v12 )
    SetLastError(LastError);
  return v12;
}

```

## disassembly

```asm
0x180059698  mov     [rsp-38h+arg_0], rbx
0x18005969d  mov     [rsp-38h+arg_18], r9
0x1800596a2  mov     [rsp-38h+arg_10], r8
0x1800596a7  push    rbp
0x1800596a8  push    rsi
0x1800596a9  push    rdi
0x1800596aa  push    r12
0x1800596ac  push    r13
0x1800596ae  push    r14
0x1800596b0  push    r15
0x1800596b2  mov     rbp, rsp
0x1800596b5  sub     rsp, 50h
0x1800596b9  xor     r14d, r14d
0x1800596bc  mov     ebx, edx
0x1800596be  mov     [rbp+pDacl], r14
0x1800596c2  mov     rdi, rcx
0x1800596c5  mov     [rbp+pSacl], r14
0x1800596c9  xor     r15d, r15d
0x1800596cc  mov     [rbp+cbSecurityDescriptor], r14d
0x1800596d0  mov     [rbp+bDaclPresent], r14d
0x1800596d4  mov     [rbp+bDaclDefaulted], r14d
0x1800596d8  call    GetPredefinedSids
0x1800596dd  test    eax, eax
0x1800596df  jz      loc_18005990F
0x1800596e5  mov     edx, ebx
0x1800596e7  mov     rcx, rdi
0x1800596ea  call    OpenProtectedRootSubKey
0x1800596ef  mov     r14, rax
0x1800596f2  test    rax, rax
0x1800596f5  jz      loc_18005990F
0x1800596fb  mov     edx, 400h; uBytes
0x180059700  lea     ebx, [r15+40h]
0x180059704  mov     ecx, ebx; uFlags
0x180059706  mov     [rbp+cbSecurityDescriptor], edx
0x180059709  call    cs:__imp_LocalAlloc
0x18005970f  mov     r15, rax
0x180059712  test    rax, rax
0x180059715  jz      loc_18005990F
0x18005971b  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18005971f  mov     r8, r15; pSecurityDescriptor
0x180059722  mov     edx, 14h; SecurityInformation
0x180059727  mov     rcx, r14; hKey
0x18005972a  call    cs:__imp_RegGetKeySecurity
0x180059730  mov     edi, eax
0x180059732  test    eax, eax
0x180059734  jnz     loc_180059939
0x18005973a  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18005973e  mov     rcx, r15; pSecurityDescriptor
0x180059741  lea     r8, [rbp+pDacl]; pDacl
0x180059745  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180059749  call    cs:__imp_GetSecurityDescriptorDacl
0x18005974f  test    eax, eax
0x180059751  jz      loc_180059965
0x180059757  mov     rcx, [rbp+pDacl]; pAcl
0x18005975b  test    rcx, rcx
0x18005975e  jz      loc_18005995A
0x180059764  xor     r12d, r12d
0x180059767  lea     ebx, [rdi+1]
0x18005976a  xor     r13d, r13d
0x18005976d  xor     esi, esi
0x18005976f  movzx   eax, word ptr [rcx+4]
0x180059773  cmp     esi, eax
0x180059775  jnb     loc_180059802
0x18005977b  lea     r8, [rbp+pAce]; pAce
0x18005977f  mov     [rbp+pAce], 0
0x180059787  mov     edx, esi; dwAceIndex
0x180059789  call    cs:__imp_GetAce
0x18005978f  test    eax, eax
0x180059791  jz      loc_18005995A
0x180059797  mov     rdx, [rbp+pAce]
0x18005979b  cmp     byte ptr [rdx], 0
0x18005979e  jnz     loc_18005995A
0x1800597a4  cmp     byte ptr [rdx+1], 2
0x1800597a8  jnz     loc_18005995A
0x1800597ae  cmp     dword ptr [rdx+4], 20019h
0x1800597b5  jz      short loc_1800597E8
0x1800597b7  cmp     dword ptr [rdx+4], 0F003Fh
0x1800597be  jnz     loc_18005995A
0x1800597c4  mov     rcx, cs:Sid; pSid1
0x1800597cb  add     rdx, 8; pSid2
0x1800597cf  call    cs:__imp_EqualSid
0x1800597d5  test    eax, eax
0x1800597d7  jz      loc_18005995A
0x1800597dd  mov     r12d, ebx
0x1800597e0  mov     rcx, [rbp+pDacl]
0x1800597e4  add     esi, ebx
0x1800597e6  jmp     short loc_18005976F
0x1800597e8  mov     rcx, cs:pSid; pSid1
0x1800597ef  add     rdx, 8; pSid2
0x1800597f3  call    cs:__imp_EqualSid
0x1800597f9  test    eax, eax
0x1800597fb  jz      short loc_1800597E0
0x1800597fd  mov     r13d, ebx
0x180059800  jmp     short loc_1800597E0
0x180059802  test    r12d, r12d
0x180059805  jz      loc_18005995A
0x18005980b  test    r13d, r13d
0x18005980e  jz      loc_18005995A
0x180059814  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x180059818  mov     rcx, r15; pSecurityDescriptor
0x18005981b  lea     r8, [rbp+pSacl]; pSacl
0x18005981f  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180059823  call    cs:__imp_GetSecurityDescriptorSacl
0x180059829  test    eax, eax
0x18005982b  jz      loc_180059965
0x180059831  mov     rcx, [rbp+pSacl]; pAcl
0x180059835  test    rcx, rcx
0x180059838  jz      loc_18005998E
0x18005983e  xor     r12d, r12d
0x180059841  xor     esi, esi
0x180059843  movzx   eax, word ptr [rcx+4]
0x180059847  cmp     esi, eax
0x180059849  jb      short loc_1800598C3
0x18005984b  test    r12d, r12d
0x18005984e  jz      loc_18005998E
0x180059854  mov     rcx, r14
0x180059857  call    ReadProtectedRootInfo
0x18005985c  mov     rsi, rax
0x18005985f  test    rax, rax
0x180059862  jz      loc_180059987
0x180059868  test    r15, r15
0x18005986b  jz      short loc_180059876
0x18005986d  mov     rcx, r15; hMem
0x180059870  call    cs:__imp_LocalFree
0x180059876  mov     rax, [rbp+arg_10]
0x18005987a  test    rax, rax
0x18005987d  jnz     loc_18005997B
0x180059883  test    r14, r14
0x180059886  jz      short loc_180059891
0x180059888  mov     rcx, r14; hKey
0x18005988b  call    cs:__imp_RegCloseKey
0x180059891  mov     rax, [rbp+arg_18]
0x180059895  test    rax, rax
0x180059898  jz      loc_18005992C
0x18005989e  mov     [rax], rsi
0x1800598a1  test    ebx, ebx
0x1800598a3  jz      loc_180059995
0x1800598a9  mov     eax, ebx
0x1800598ab  mov     rbx, [rsp+50h+arg_0]
0x1800598b3  add     rsp, 50h
0x1800598b7  pop     r15
0x1800598b9  pop     r14
0x1800598bb  pop     r13
0x1800598bd  pop     r12
0x1800598bf  pop     rdi
0x1800598c0  pop     rsi
0x1800598c1  pop     rbp
0x1800598c2  retn
0x1800598c3  lea     r8, [rbp+pAce]; pAce
0x1800598c7  mov     [rbp+pAce], 0
0x1800598cf  mov     edx, esi; dwAceIndex
0x1800598d1  call    cs:__imp_GetAce
0x1800598d7  test    eax, eax
0x1800598d9  jz      loc_18005998E
0x1800598df  mov     rdx, [rbp+pAce]
0x1800598e3  cmp     byte ptr [rdx], 11h
0x1800598e6  jnz     short loc_180059904
0x1800598e8  mov     rcx, cs:qword_18015D618; pSid1
0x1800598ef  add     rdx, 8; pSid2
0x1800598f3  call    cs:__imp_EqualSid
0x1800598f9  test    eax, eax
0x1800598fb  jz      loc_18005998E
0x180059901  mov     r12d, ebx
0x180059904  mov     rcx, [rbp+pSacl]
0x180059908  add     esi, ebx
0x18005990a  jmp     loc_180059843
0x18005990f  call    cs:__imp_GetLastError
0x180059915  mov     edi, eax
0x180059917  test    r14, r14
0x18005991a  jnz     short loc_18005996D
0x18005991c  xor     ecx, ecx; hMem
0x18005991e  call    PkiDefaultCryptFree
0x180059923  xor     esi, esi
0x180059925  xor     ebx, ebx
0x180059927  jmp     loc_180059868
0x18005992c  mov     rcx, rsi; hMem
0x18005992f  call    PkiDefaultCryptFree
0x180059934  jmp     loc_1800598A1
0x180059939  cmp     eax, 7Ah ; 'z'
0x18005993c  jnz     short loc_180059983
0x18005993e  mov     edx, [rbp+cbSecurityDescriptor]; uBytes
0x180059941  mov     r8d, ebx; uFlags
0x180059944  mov     rcx, r15; hMem
0x180059947  call    cs:__imp_LocalReAlloc
0x18005994d  test    rax, rax
0x180059950  jz      short loc_180059923
0x180059952  mov     r15, rax
0x180059955  jmp     loc_18005971B
0x18005995a  mov     ecx, 538h; dwErrCode
0x18005995f  call    cs:__imp_SetLastError
0x180059965  call    cs:__imp_GetLastError
0x18005996b  mov     edi, eax
0x18005996d  mov     rcx, r14; hKey
0x180059970  call    cs:__imp_RegCloseKey
0x180059976  xor     r14d, r14d
0x180059979  jmp     short loc_18005991C
0x18005997b  mov     [rax], r14
0x18005997e  jmp     loc_180059891
0x180059983  mov     ecx, eax
0x180059985  jmp     short loc_18005995F
0x180059987  mov     ecx, 0Dh
0x18005998c  jmp     short loc_18005995F
0x18005998e  mov     ecx, 513h
0x180059993  jmp     short loc_18005995F
0x180059995  mov     ecx, edi; dwErrCode
0x180059997  call    cs:__imp_SetLastError
0x18005999d  jmp     loc_1800598A9
```
