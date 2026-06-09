# CreateSharedFileMapping(ushort const *,ulong)

- ea: `0x180013b2c`
- end: `0x180014121`
- name: `?CreateSharedFileMapping@@YAPEAXPEBGK@Z`
- size: `1525`
- prototype: `HANDLE __fastcall(const unsigned __int16 *, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800157b8`

## callees

- `0x18000d1c8`
- `0x1800138d0`
- `0x180013b2c`
- `0x180017754`
- `0x180017a84`
- `0x1800181e0`
- `0x1800182a0`
- `0x180019010`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180013f1f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180013f1f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180013e81`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180013e81`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e1b`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e35`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e4f`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e6a`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e1b`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e35`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e4f`
- `ADVAPI32!AddAccessAllowedAce` at `0x180013e6a`
- `ADVAPI32!InitializeAcl` at `0x180013d7a`
- `ADVAPI32!InitializeAcl` at `0x180013d7a`
- `ADVAPI32!GetLengthSid` at `0x180013c8d`
- `ADVAPI32!GetLengthSid` at `0x180013c9d`
- `ADVAPI32!GetLengthSid` at `0x180013cad`
- `ADVAPI32!GetLengthSid` at `0x180013cbd`
- `ADVAPI32!GetLengthSid` at `0x180013c8d`
- `ADVAPI32!GetLengthSid` at `0x180013c9d`
- `ADVAPI32!GetLengthSid` at `0x180013cad`
- `ADVAPI32!GetLengthSid` at `0x180013cbd`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180013c1a`
- `ADVAPI32!ConvertStringSidToSidW` at `0x180013c1a`
- `KERNEL32!GlobalFree` at `0x180013bd5`
- `KERNEL32!GlobalFree` at `0x180013c07`
- `KERNEL32!GlobalFree` at `0x180014022`
- `KERNEL32!GlobalFree` at `0x180014030`
- `KERNEL32!GlobalFree` at `0x18001403e`
- `KERNEL32!GlobalFree` at `0x1800140e0`
- `KERNEL32!GlobalFree` at `0x1800140ee`
- `KERNEL32!GlobalFree` at `0x1800140fc`
- `KERNEL32!GlobalFree` at `0x180013bd5`
- `KERNEL32!GlobalFree` at `0x180013c07`
- `KERNEL32!GlobalFree` at `0x180014022`
- `KERNEL32!GlobalFree` at `0x180014030`
- `KERNEL32!GlobalFree` at `0x18001403e`
- `KERNEL32!GlobalFree` at `0x1800140e0`
- `KERNEL32!GlobalFree` at `0x1800140ee`
- `KERNEL32!GlobalFree` at `0x1800140fc`
- `KERNEL32!CreateFileMappingW` at `0x180013fe9`
- `KERNEL32!CreateFileMappingW` at `0x180013fe9`
- `KERNEL32!GetLastError` at `0x180013c24`
- `KERNEL32!GetLastError` at `0x180013d88`
- `KERNEL32!GetLastError` at `0x180013e8f`
- `KERNEL32!GetLastError` at `0x180013f2d`
- `KERNEL32!GetLastError` at `0x18001404c`
- `KERNEL32!GetLastError` at `0x180013c24`
- `KERNEL32!GetLastError` at `0x180013d88`
- `KERNEL32!GetLastError` at `0x180013e8f`
- `KERNEL32!GetLastError` at `0x180013f2d`
- `KERNEL32!GetLastError` at `0x18001404c`
- `KERNEL32!LocalFree` at `0x180013b93`
- `KERNEL32!LocalFree` at `0x180013bc6`
- `KERNEL32!LocalFree` at `0x180013bf8`
- `KERNEL32!LocalFree` at `0x180014014`
- `KERNEL32!LocalFree` at `0x1800140d2`
- `KERNEL32!LocalFree` at `0x180013b93`
- `KERNEL32!LocalFree` at `0x180013bc6`
- `KERNEL32!LocalFree` at `0x180013bf8`
- `KERNEL32!LocalFree` at `0x180014014`
- `KERNEL32!LocalFree` at `0x1800140d2`

## string_xrefs

- `0x180013db2`: `AddAccessAllowedAce failed. Error %x`
- `0x180014076`: `AddAccessAllowedAce failed. Error %x`
- `0x180013eb9`: `InitializeSecurityDescriptor failed. Error %x`
- `0x180013f57`: `SetSecurityDescriptorDacl failed. Error %x`
- `0x180013c54`: `ConvertStringSidToSid failed. Error %x`

## pseudocode

```c
HANDLE __fastcall CreateSharedFileMapping(const unsigned __int16 *a1, DWORD a2)
{
  PSID v3; // rcx
  char LastError; // bl
  DWORD LengthSid; // r12d
  HGLOBAL v6; // r14
  DWORD v7; // r12d
  HGLOBAL v8; // rsi
  DWORD v9; // r12d
  PSID v10; // rdi
  HLOCAL *p_hMem; // rbx
  __int64 v12; // r12
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  void *v15; // rsp
  void *v16; // rsp
  _DWORD *v17; // rax
  char v18; // r12
  char v19; // r12
  char v20; // r12
  HANDLE v21; // r15
  char v23; // r12
  __int64 v24; // [rsp+0h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp+0h] BYREF
  PSID v26; // [rsp+38h] [rbp+8h] BYREF
  HGLOBAL v27; // [rsp+40h] [rbp+10h] BYREF
  HGLOBAL pSid; // [rsp+48h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+50h] [rbp+20h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+68h] [rbp+38h] BYREF

  v26 = 0;
  v27 = 0;
  pSid = 0;
  hMem = 0;
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v26) )
  {
LABEL_4:
    v3 = v26;
    if ( !v26 )
      return 0;
LABEL_90:
    GlobalFree(v3);
    return 0;
  }
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v27) )
  {
LABEL_9:
    if ( v27 )
      GlobalFree(v27);
    goto LABEL_4;
  }
  if ( (unsigned int)AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &pSid) )
  {
LABEL_12:
    if ( hMem )
      LocalFree(hMem);
    if ( pSid )
      GlobalFree(pSid);
    goto LABEL_9;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-611605672-2879557022-2206624263-4029342278-3129212340", &hMem) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("ConvertStringSidToSid failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        LastError);
    }
    goto LABEL_12;
  }
  LengthSid = GetLengthSid(hMem);
  v6 = pSid;
  v7 = GetLengthSid(pSid) + LengthSid;
  v8 = v27;
  v9 = GetLengthSid(v27) + v7;
  v10 = v26;
  p_hMem = 0;
  v12 = GetLengthSid(v26) + v9 + 40;
  if ( !(_DWORD)v12
    || (unsigned int)v12 > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)(unsigned int)v12 + g_ulAdditionalProbeSize + 8 < (unsigned int)v12
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_29;
  }
  v13 = v12 + 23;
  if ( v12 + 23 <= (unsigned __int64)(v12 + 8) )
    v13 = 0xFFFFFFFFFFFFFF0LL;
  v14 = v13 & 0xFFFFFFFFFFFFFFF0uLL;
  v15 = alloca(v14);
  v16 = alloca(v14);
  p_hMem = &hMem;
  if ( &v24 == (__int64 *)-48LL || (LODWORD(hMem) = 1801679955, (p_hMem = &v26) == 0) )
  {
LABEL_29:
    if ( v12 + 8 >= (unsigned __int64)(unsigned int)v12 )
    {
      v17 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v17 )
        goto LABEL_82;
      *v17 = 1885431112;
      p_hMem = (HLOCAL *)(v17 + 2);
    }
    if ( p_hMem )
      goto LABEL_33;
LABEL_82:
    if ( hMem )
      LocalFree(hMem);
    if ( v6 )
      GlobalFree(v6);
    if ( v8 )
      GlobalFree(v8);
    if ( !v10 )
      return 0;
    v3 = v10;
    goto LABEL_90;
  }
LABEL_33:
  if ( !InitializeAcl((PACL)p_hMem, v12, 2u) )
  {
    v18 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("AddAccessAllowedAce failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v18);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !AddAccessAllowedAce((PACL)p_hMem, 2u, 0xF001Fu, v10)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0xF001Fu, v8)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0xF001Fu, v6)
    || !AddAccessAllowedAce((PACL)p_hMem, 2u, 0xF001Fu, hMem) )
  {
    v23 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("AddAccessAllowedAce failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v23);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v19 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("InitializeSecurityDescriptor failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v19);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)p_hMem, 0) )
  {
    v20 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("SetSecurityDescriptorDacl failed. Error %x");
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        v20);
    }
    if ( p_hMem && *((_DWORD *)p_hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_82;
  }
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 1;
  FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  v21 = CreateFileMappingW(
          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
          &FileMappingAttributes,
          0x4000004u,
          0,
          a2,
          L"{A5B99A4C-2959-11D1-BAC8-00C04FC2E20D}");
  if ( *((_DWORD *)p_hMem - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    GlobalFree(v6);
  if ( v8 )
    GlobalFree(v8);
  if ( v10 )
    GlobalFree(v10);
  return v21;
}

```

## disassembly

```asm
0x180013b2c  push    rbp
0x180013b2e  push    rbx
0x180013b2f  push    rsi
0x180013b30  push    rdi
0x180013b31  push    r12
0x180013b33  push    r13
0x180013b35  push    r14
0x180013b37  push    r15
0x180013b39  sub     rsp, 0A8h
0x180013b40  lea     rbp, [rsp+30h]
0x180013b45  mov     rax, cs:__security_cookie
0x180013b4c  xor     rax, rbp
0x180013b4f  mov     [rbp+0B0h+var_50], rax
0x180013b53  mov     r13d, edx
0x180013b56  mov     [rbp+0B0h+var_A8], 0
0x180013b5e  mov     [rbp+0B0h+var_A0], 0
0x180013b66  mov     [rbp+0B0h+pSid], 0
0x180013b6e  mov     [rbp+0B0h+hMem], 0
0x180013b76  lea     rdx, [rbp+0B0h+var_A8]; void **
0x180013b7a  mov     edi, 1Ah
0x180013b7f  mov     ecx, edi; WellKnownSidType
0x180013b81  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180013b86  test    eax, eax
0x180013b88  jz      short loc_180013BAB
0x180013b8a  mov     rcx, [rbp+0B0h+hMem]; hMem
0x180013b8e  test    rcx, rcx
0x180013b91  jz      short loc_180013B99
0x180013b93  call    cs:__imp_LocalFree
0x180013b99  mov     rcx, [rbp+0B0h+var_A8]
0x180013b9d  test    rcx, rcx
0x180013ba0  jz      loc_180014102
0x180013ba6  jmp     loc_1800140FC
0x180013bab  lea     rdx, [rbp+0B0h+var_A0]; void **
0x180013baf  mov     ecx, 39h ; '9'; WellKnownSidType
0x180013bb4  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180013bb9  test    eax, eax
0x180013bbb  jz      short loc_180013BDD
0x180013bbd  mov     rcx, [rbp+0B0h+hMem]; hMem
0x180013bc1  test    rcx, rcx
0x180013bc4  jz      short loc_180013BCC
0x180013bc6  call    cs:__imp_LocalFree
0x180013bcc  mov     rcx, [rbp+0B0h+var_A0]; hMem
0x180013bd0  test    rcx, rcx
0x180013bd3  jz      short loc_180013B99
0x180013bd5  call    cs:__imp_GlobalFree
0x180013bdb  jmp     short loc_180013B99
0x180013bdd  lea     rdx, [rbp+0B0h+pSid]; void **
0x180013be1  mov     ecx, 3Ah ; ':'; WellKnownSidType
0x180013be6  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180013beb  test    eax, eax
0x180013bed  jz      short loc_180013C0F
0x180013bef  mov     rcx, [rbp+0B0h+hMem]; hMem
0x180013bf3  test    rcx, rcx
0x180013bf6  jz      short loc_180013BFE
0x180013bf8  call    cs:__imp_LocalFree
0x180013bfe  mov     rcx, [rbp+0B0h+pSid]; hMem
0x180013c02  test    rcx, rcx
0x180013c05  jz      short loc_180013BCC
0x180013c07  call    cs:__imp_GlobalFree
0x180013c0d  jmp     short loc_180013BCC
0x180013c0f  lea     rdx, [rbp+0B0h+hMem]; Sid
0x180013c13  lea     rcx, StringSid; "S-1-5-80-611605672-2879557022-220662426"...
0x180013c1a  call    cs:__imp_ConvertStringSidToSidW
0x180013c20  test    eax, eax
0x180013c22  jnz     short loc_180013C89
0x180013c24  call    cs:__imp_GetLastError
0x180013c2a  mov     ebx, eax
0x180013c2c  lea     rcx, WPP_GLOBAL_Control
0x180013c33  mov     r8, cs:WPP_GLOBAL_Control
0x180013c3a  cmp     r8, rcx
0x180013c3d  jz      short loc_180013BEF
0x180013c3f  mov     r15d, 2
0x180013c45  cmp     [r8+19h], r15b
0x180013c49  jb      short loc_180013BEF
0x180013c4b  test    byte ptr [r8+1Ch], 1
0x180013c50  jz      short loc_180013BEF
0x180013c52  mov     edx, eax
0x180013c54  lea     rcx, aConvertstrings_0; "ConvertStringSidToSid failed. Error %x"
0x180013c5b  call    WppDbgPrint
0x180013c60  mov     edx, edi
0x180013c62  mov     [rsp+0E0h+dwMaximumSizeLow], ebx
0x180013c66  lea     r9, aNapbase; "NAPBASE"
0x180013c6d  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180013c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c7b  mov     rcx, [rcx+10h]
0x180013c7f  call    WPP_SF_sD
0x180013c84  jmp     loc_180013BEF
0x180013c89  mov     rcx, [rbp+0B0h+hMem]; pSid
0x180013c8d  call    cs:__imp_GetLengthSid
0x180013c93  mov     r12d, eax
0x180013c96  mov     r14, [rbp+0B0h+pSid]
0x180013c9a  mov     rcx, r14; pSid
0x180013c9d  call    cs:__imp_GetLengthSid
0x180013ca3  add     r12d, eax
0x180013ca6  mov     rsi, [rbp+0B0h+var_A0]
0x180013caa  mov     rcx, rsi; pSid
0x180013cad  call    cs:__imp_GetLengthSid
0x180013cb3  add     r12d, eax
0x180013cb6  mov     rdi, [rbp+0B0h+var_A8]
0x180013cba  mov     rcx, rdi; pSid
0x180013cbd  call    cs:__imp_GetLengthSid
0x180013cc3  add     r12d, 28h ; '('
0x180013cc7  xor     ebx, ebx
0x180013cc9  add     r12d, eax
0x180013ccc  jz      short loc_180013D33
0x180013cce  mov     r15d, r12d
0x180013cd1  cmp     r15, cs:g_ulMaxStackAllocSize
0x180013cd8  ja      short loc_180013D33
0x180013cda  mov     rcx, cs:g_ulAdditionalProbeSize
0x180013ce1  add     rcx, 8
0x180013ce5  add     rcx, r15
0x180013ce8  cmp     rcx, r15
0x180013ceb  jb      short loc_180013D33
0x180013ced  call    VerifyStackAvailable
0x180013cf2  test    eax, eax
0x180013cf4  jz      short loc_180013D33
0x180013cf6  lea     rax, [r12+8]
0x180013cfb  lea     rcx, [rax+0Fh]
0x180013cff  cmp     rcx, rax
0x180013d02  ja      short loc_180013D0E
0x180013d04  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180013d0e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180013d12  mov     rax, rcx
0x180013d15  call    _alloca_probe
0x180013d1a  sub     rsp, rcx
0x180013d1d  lea     rbx, [rsp+0E0h+hMem]
0x180013d22  test    rbx, rbx
0x180013d25  jz      short loc_180013D33
0x180013d27  mov     dword ptr [rbx], 6B637453h
0x180013d2d  add     rbx, 8
0x180013d31  jnz     short loc_180013D6B
0x180013d33  mov     eax, r12d
0x180013d36  lea     rcx, [r12+8]
0x180013d3b  cmp     rcx, rax
0x180013d3e  jb      short loc_180013D62
0x180013d40  mov     rax, cs:g_pfnAllocate
0x180013d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d4c  mov     rbx, rax
0x180013d4f  test    rax, rax
0x180013d52  jz      loc_1800140C9
0x180013d58  mov     dword ptr [rax], 70616548h
0x180013d5e  add     rbx, 8
0x180013d62  test    rbx, rbx
0x180013d65  jz      loc_1800140C9
0x180013d6b  mov     r15d, 2
0x180013d71  mov     r8d, r15d; dwAclRevision
0x180013d74  mov     edx, r12d; nAclLength
0x180013d77  mov     rcx, rbx; pAcl
0x180013d7a  call    cs:__imp_InitializeAcl
0x180013d80  test    eax, eax
0x180013d82  jnz     loc_180013E09
0x180013d88  call    cs:__imp_GetLastError
0x180013d8e  mov     r12d, eax
0x180013d91  lea     rcx, WPP_GLOBAL_Control
0x180013d98  mov     rdx, cs:WPP_GLOBAL_Control
0x180013d9f  cmp     rdx, rcx
0x180013da2  jz      short loc_180013DE6
0x180013da4  cmp     [rdx+19h], r15b
0x180013da8  jb      short loc_180013DE6
0x180013daa  test    byte ptr [rdx+1Ch], 1
0x180013dae  jz      short loc_180013DE6
0x180013db0  mov     edx, eax
0x180013db2  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x180013db9  call    WppDbgPrint
0x180013dbe  lea     edx, [r15+19h]
0x180013dc2  mov     [rsp+0E0h+dwMaximumSizeLow], r12d
0x180013dc7  lea     r9, aNapbase; "NAPBASE"
0x180013dce  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180013dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ddc  mov     rcx, [rcx+10h]
0x180013de0  call    WPP_SF_sD
0x180013de5  nop
0x180013de6  test    rbx, rbx
0x180013de9  jz      short loc_180013E04
0x180013deb  lea     rcx, [rbx-8]
0x180013def  cmp     dword ptr [rcx], 70616548h
0x180013df5  jnz     short loc_180013E04
0x180013df7  mov     rax, cs:g_pfnFree
0x180013dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e03  nop
0x180013e04  jmp     loc_1800140C9
0x180013e09  mov     r9, rdi; pSid
0x180013e0c  mov     r12d, 0F001Fh
0x180013e12  mov     r8d, r12d; AccessMask
0x180013e15  mov     edx, r15d; dwAceRevision
0x180013e18  mov     rcx, rbx; pAcl
0x180013e1b  call    cs:__imp_AddAccessAllowedAce
0x180013e21  test    eax, eax
0x180013e23  jz      loc_18001404C
0x180013e29  mov     r9, rsi; pSid
0x180013e2c  mov     r8d, r12d; AccessMask
0x180013e2f  mov     edx, r15d; dwAceRevision
0x180013e32  mov     rcx, rbx; pAcl
0x180013e35  call    cs:__imp_AddAccessAllowedAce
0x180013e3b  test    eax, eax
0x180013e3d  jz      loc_18001404C
0x180013e43  mov     r9, r14; pSid
0x180013e46  mov     r8d, r12d; AccessMask
0x180013e49  mov     edx, r15d; dwAceRevision
0x180013e4c  mov     rcx, rbx; pAcl
0x180013e4f  call    cs:__imp_AddAccessAllowedAce
0x180013e55  test    eax, eax
0x180013e57  jz      loc_18001404C
0x180013e5d  mov     r9, [rbp+0B0h+hMem]; pSid
0x180013e61  mov     r8d, r12d; AccessMask
0x180013e64  mov     edx, r15d; dwAceRevision
0x180013e67  mov     rcx, rbx; pAcl
0x180013e6a  call    cs:__imp_AddAccessAllowedAce
0x180013e70  test    eax, eax
0x180013e72  jz      loc_18001404C
0x180013e78  mov     edx, 1; dwRevision
0x180013e7d  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180013e81  call    cs:__imp_InitializeSecurityDescriptor
0x180013e87  test    eax, eax
0x180013e89  jnz     loc_180013F11
0x180013e8f  call    cs:__imp_GetLastError
0x180013e95  mov     r12d, eax
0x180013e98  lea     rcx, WPP_GLOBAL_Control
0x180013e9f  mov     rdx, cs:WPP_GLOBAL_Control
0x180013ea6  cmp     rdx, rcx
0x180013ea9  jz      short loc_180013EEE
0x180013eab  cmp     [rdx+19h], r15b
0x180013eaf  jb      short loc_180013EEE
0x180013eb1  test    byte ptr [rdx+1Ch], 1
0x180013eb5  jz      short loc_180013EEE
0x180013eb7  mov     edx, eax
0x180013eb9  lea     rcx, aInitializesecu; "InitializeSecurityDescriptor failed. Er"...
0x180013ec0  call    WppDbgPrint
0x180013ec5  mov     edx, 1Dh
0x180013eca  mov     [rsp+0E0h+dwMaximumSizeLow], r12d
0x180013ecf  lea     r9, aNapbase; "NAPBASE"
0x180013ed6  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180013edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ee4  mov     rcx, [rcx+10h]
0x180013ee8  call    WPP_SF_sD
0x180013eed  nop
0x180013eee  test    rbx, rbx
0x180013ef1  jz      short loc_180013F0C
0x180013ef3  lea     rcx, [rbx-8]
0x180013ef7  cmp     dword ptr [rcx], 70616548h
0x180013efd  jnz     short loc_180013F0C
0x180013eff  mov     rax, cs:g_pfnFree
0x180013f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f0b  nop
0x180013f0c  jmp     loc_1800140C9
0x180013f11  xor     r9d, r9d; bDaclDefaulted
0x180013f14  mov     r8, rbx; pDacl
0x180013f17  lea     edx, [r9+1]; bDaclPresent
0x180013f1b  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x180013f1f  call    cs:__imp_SetSecurityDescriptorDacl
0x180013f25  test    eax, eax
0x180013f27  jnz     loc_180013FAF
0x180013f2d  call    cs:__imp_GetLastError
0x180013f33  mov     r12d, eax
0x180013f36  lea     rcx, WPP_GLOBAL_Control
0x180013f3d  mov     rdx, cs:WPP_GLOBAL_Control
0x180013f44  cmp     rdx, rcx
0x180013f47  jz      short loc_180013F8C
0x180013f49  cmp     [rdx+19h], r15b
0x180013f4d  jb      short loc_180013F8C
0x180013f4f  test    byte ptr [rdx+1Ch], 1
0x180013f53  jz      short loc_180013F8C
0x180013f55  mov     edx, eax
0x180013f57  lea     rcx, aSetsecuritydes; "SetSecurityDescriptorDacl failed. Error"...
0x180013f5e  call    WppDbgPrint
0x180013f63  mov     edx, 1Eh
0x180013f68  mov     [rsp+0E0h+dwMaximumSizeLow], r12d
0x180013f6d  lea     r9, aNapbase; "NAPBASE"
0x180013f74  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x180013f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f82  mov     rcx, [rcx+10h]
0x180013f86  call    WPP_SF_sD
0x180013f8b  nop
0x180013f8c  test    rbx, rbx
0x180013f8f  jz      short loc_180013FAA
0x180013f91  lea     rcx, [rbx-8]
0x180013f95  cmp     dword ptr [rcx], 70616548h
0x180013f9b  jnz     short loc_180013FAA
0x180013f9d  mov     rax, cs:g_pfnFree
0x180013fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fa9  nop
0x180013faa  jmp     loc_1800140C9
0x180013faf  mov     qword ptr [rbp+0B0h+FileMappingAttributes.nLength], 18h
0x180013fb7  mov     qword ptr [rbp+0B0h+FileMappingAttributes.bInheritHandle], 1
0x180013fbf  lea     rax, [rbp+0B0h+pSecurityDescriptor]
0x180013fc3  mov     [rbp+0B0h+FileMappingAttributes.lpSecurityDescriptor], rax
0x180013fc7  lea     rax, Name; "{A5B99A4C-2959-11D1-BAC8-00C04FC2E20D}"
0x180013fce  mov     [rsp+0E0h+lpName], rax; lpName
0x180013fd3  mov     [rsp+0E0h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x180013fd8  xor     r9d, r9d; dwMaximumSizeHigh
0x180013fdb  mov     r8d, 4000004h; flProtect
0x180013fe1  lea     rdx, [rbp+0B0h+FileMappingAttributes]; lpFileMappingAttributes
0x180013fe5  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180013fe9  call    cs:__imp_CreateFileMappingW
0x180013fef  mov     r15, rax
0x180013ff2  lea     rcx, [rbx-8]
0x180013ff6  cmp     dword ptr [rcx], 70616548h
0x180013ffc  jnz     short loc_18001400B
0x180013ffe  mov     rax, cs:g_pfnFree
0x180014005  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
