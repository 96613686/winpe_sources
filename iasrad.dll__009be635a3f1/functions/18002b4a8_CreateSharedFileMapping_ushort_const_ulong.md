# CreateSharedFileMapping(ushort const *,ulong)

- ea: `0x18002b4a8`
- end: `0x18002b972`
- name: `?CreateSharedFileMapping@@YAPEAXPEBGK@Z`
- size: `1226`
- prototype: `void *(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002d598`

## callees

- `0x18000dc54`
- `0x180014710`
- `0x18001d31c`
- `0x18002b19c`
- `0x18002b22c`
- `0x18002b4a8`
- `0x18002df44`
- `0x18002e230`
- `0x18002e2f0`
- `0x180030010`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18002b88a`
- `KERNEL32!CreateFileMappingW` at `0x18002b88a`
- `KERNEL32!GetLastError` at `0x18002b57f`
- `KERNEL32!GetLastError` at `0x18002b6d7`
- `KERNEL32!GetLastError` at `0x18002b7a1`
- `KERNEL32!GetLastError` at `0x18002b806`
- `KERNEL32!GetLastError` at `0x18002b8c8`
- `KERNEL32!GetLastError` at `0x18002b57f`
- `KERNEL32!GetLastError` at `0x18002b6d7`
- `KERNEL32!GetLastError` at `0x18002b7a1`
- `KERNEL32!GetLastError` at `0x18002b806`
- `KERNEL32!GetLastError` at `0x18002b8c8`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002b7fc`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002b7fc`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002b797`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002b797`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b731`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b74b`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b765`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b77f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b731`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b74b`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b765`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002b77f`
- `ADVAPI32!InitializeAcl` at `0x18002b6cd`
- `ADVAPI32!InitializeAcl` at `0x18002b6cd`
- `ADVAPI32!GetLengthSid` at `0x18002b5f0`
- `ADVAPI32!GetLengthSid` at `0x18002b5fc`
- `ADVAPI32!GetLengthSid` at `0x18002b608`
- `ADVAPI32!GetLengthSid` at `0x18002b614`
- `ADVAPI32!GetLengthSid` at `0x18002b5f0`
- `ADVAPI32!GetLengthSid` at `0x18002b5fc`
- `ADVAPI32!GetLengthSid` at `0x18002b608`
- `ADVAPI32!GetLengthSid` at `0x18002b614`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002b575`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002b575`

## string_xrefs

- `0x18002b70c`: `AddAccessAllowedAce failed. Error %x`
- `0x18002b8f1`: `AddAccessAllowedAce failed. Error %x`
- `0x18002b7d6`: `InitializeSecurityDescriptor failed. Error %x`
- `0x18002b83b`: `SetSecurityDescriptorDacl failed. Error %x`
- `0x18002b5b7`: `ConvertStringSidToSid failed. Error %x`

## pseudocode

```c
HANDLE __fastcall CreateSharedFileMapping(const unsigned __int16 *a1, DWORD a2)
{
  char LastError; // bl
  DWORD LengthSid; // esi
  DWORD v5; // esi
  DWORD v6; // esi
  PSID *v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  _DWORD *v13; // rax
  char v14; // bl
  int v15; // edx
  HANDLE v16; // rbx
  __int64 v18; // [rsp+0h] [rbp-30h] BYREF
  PSID v19; // [rsp+30h] [rbp+0h] BYREF
  PSID v20; // [rsp+38h] [rbp+8h] BYREF
  PSID pSid; // [rsp+40h] [rbp+10h] BYREF
  PSID Sid; // [rsp+48h] [rbp+18h] BYREF
  PSID *v23; // [rsp+50h] [rbp+20h] BYREF
  PSID *p_Sid; // [rsp+58h] [rbp+28h] BYREF
  int v25; // [rsp+60h] [rbp+30h]
  PSID *p_pSid; // [rsp+68h] [rbp+38h] BYREF
  int v27; // [rsp+70h] [rbp+40h]
  PSID *v28; // [rsp+78h] [rbp+48h] BYREF
  int v29; // [rsp+80h] [rbp+50h]
  PSID *v30; // [rsp+88h] [rbp+58h] BYREF
  int v31; // [rsp+90h] [rbp+60h]
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+98h] [rbp+68h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+B0h] [rbp+80h] BYREF

  v19 = 0;
  v20 = 0;
  pSid = 0;
  Sid = 0;
  v30 = &v19;
  v31 = 1;
  v28 = &v20;
  v29 = 1;
  p_pSid = &pSid;
  v27 = 1;
  p_Sid = &Sid;
  v25 = 0;
  if ( AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v19)
    || AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v20)
    || AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &pSid) )
  {
    goto LABEL_47;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-611605672-2879557022-2206624263-4029342278-3129212340", &Sid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("ConvertStringSidToSid failed. Error %x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        LastError);
    }
    goto LABEL_47;
  }
  LengthSid = GetLengthSid(Sid);
  v5 = GetLengthSid(pSid) + LengthSid;
  v6 = GetLengthSid(v20) + v5;
  v7 = 0;
  v8 = GetLengthSid(v19) + v6 + 40;
  if ( (_DWORD)v8
    && (unsigned int)v8 <= (unsigned __int64)g_ulMaxStackAllocSize
    && (unsigned __int64)(unsigned int)v8 + g_ulAdditionalProbeSize + 8 >= (unsigned int)v8
    && (unsigned int)VerifyStackAvailable() )
  {
    v9 = v8 + 23;
    if ( v8 + 23 <= (unsigned __int64)(v8 + 8) )
      v9 = 0xFFFFFFFFFFFFFF0LL;
    v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
    v11 = alloca(v10);
    v12 = alloca(v10);
    v7 = &v19;
    if ( &v18 != (__int64 *)-48LL )
    {
      LODWORD(v19) = 1801679955;
      v7 = &v20;
      if ( &v20 )
      {
LABEL_21:
        v23 = v7;
        if ( InitializeAcl((PACL)v7, v8, 2u) )
        {
          if ( AddAccessAllowedAce((PACL)v7, 2u, 0xF001Fu, v19)
            && AddAccessAllowedAce((PACL)v7, 2u, 0xF001Fu, v20)
            && AddAccessAllowedAce((PACL)v7, 2u, 0xF001Fu, pSid)
            && AddAccessAllowedAce((PACL)v7, 2u, 0xF001Fu, Sid) )
          {
            if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)v7, 0) )
              {
                *(_QWORD *)&FileMappingAttributes.nLength = 24;
                *(_QWORD *)&FileMappingAttributes.bInheritHandle = 1;
                FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
                v16 = CreateFileMappingW(
                        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                        &FileMappingAttributes,
                        0x4000004u,
                        0,
                        a2,
                        L"{A5B99A4E-2959-11D1-BAC8-00C04FC2E20D}");
                SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v23);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_Sid);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_pSid);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v28);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v30);
                return v16;
              }
              v14 = GetLastError();
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_46;
              }
              WppDbgPrint("SetSecurityDescriptorDacl failed. Error %x");
              v15 = 30;
            }
            else
            {
              v14 = GetLastError();
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_46;
              }
              WppDbgPrint("InitializeSecurityDescriptor failed. Error %x");
              v15 = 29;
            }
          }
          else
          {
            v14 = GetLastError();
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_46;
            }
            WppDbgPrint("AddAccessAllowedAce failed. Error %x");
            v15 = 28;
          }
        }
        else
        {
          v14 = GetLastError();
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_46;
          }
          WppDbgPrint("AddAccessAllowedAce failed. Error %x");
          v15 = 27;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
          (unsigned int)"NAPBASE",
          v14);
LABEL_46:
        SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v23);
        goto LABEL_47;
      }
    }
  }
  if ( v8 + 8 >= (unsigned __int64)(unsigned int)v8 )
  {
    v13 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
    if ( !v13 )
      goto LABEL_47;
    *v13 = 1885431112;
    v7 = (PSID *)(v13 + 2);
  }
  if ( v7 )
    goto LABEL_21;
LABEL_47:
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_Sid);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_pSid);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v28);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v30);
  return 0;
}

```

## disassembly

```asm
0x18002b4a8  push    rbp
0x18002b4aa  push    rbx
0x18002b4ab  push    rsi
0x18002b4ac  push    rdi
0x18002b4ad  push    r12
0x18002b4af  push    r14
0x18002b4b1  sub     rsp, 0E8h
0x18002b4b8  lea     rbp, [rsp+30h]
0x18002b4bd  mov     rax, cs:__security_cookie
0x18002b4c4  xor     rax, rbp
0x18002b4c7  mov     [rbp+0E0h+var_38], rax
0x18002b4ce  mov     r14d, edx
0x18002b4d1  mov     [rbp+0E0h+var_E0], 0
0x18002b4d9  mov     [rbp+0E0h+var_D8], 0
0x18002b4e1  mov     [rbp+0E0h+pSid], 0
0x18002b4e9  mov     [rbp+0E0h+Sid], 0
0x18002b4f1  lea     rax, [rbp+0E0h+var_E0]
0x18002b4f5  mov     [rbp+0E0h+var_88], rax
0x18002b4f9  mov     r12d, 1
0x18002b4ff  mov     [rbp+0E0h+var_80], r12d
0x18002b503  lea     rax, [rbp+0E0h+var_D8]
0x18002b507  mov     [rbp+0E0h+var_98], rax
0x18002b50b  mov     [rbp+0E0h+var_90], r12d
0x18002b50f  lea     rax, [rbp+0E0h+pSid]
0x18002b513  mov     [rbp+0E0h+var_A8], rax
0x18002b517  mov     [rbp+0E0h+var_A0], r12d
0x18002b51b  lea     rax, [rbp+0E0h+Sid]
0x18002b51f  mov     [rbp+0E0h+var_B8], rax
0x18002b523  mov     [rbp+0E0h+var_B0], 0
0x18002b52a  lea     rdx, [rbp+0E0h+var_E0]; void **
0x18002b52e  lea     esi, [r12+19h]
0x18002b533  mov     ecx, esi; WellKnownSidType
0x18002b535  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002b53a  test    eax, eax
0x18002b53c  jnz     loc_18002B92D
0x18002b542  lea     rdx, [rbp+0E0h+var_D8]; void **
0x18002b546  lea     ecx, [rsi+1Fh]; WellKnownSidType
0x18002b549  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002b54e  test    eax, eax
0x18002b550  jnz     loc_18002B92D
0x18002b556  lea     rdx, [rbp+0E0h+pSid]; void **
0x18002b55a  lea     ecx, [rsi+20h]; WellKnownSidType
0x18002b55d  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002b562  test    eax, eax
0x18002b564  jnz     loc_18002B92D
0x18002b56a  lea     rdx, [rbp+0E0h+Sid]; Sid
0x18002b56e  lea     rcx, StringSid; "S-1-5-80-611605672-2879557022-220662426"...
0x18002b575  call    cs:__imp_ConvertStringSidToSidW
0x18002b57b  test    eax, eax
0x18002b57d  jnz     short loc_18002B5EC
0x18002b57f  call    cs:__imp_GetLastError
0x18002b585  mov     ebx, eax
0x18002b587  lea     rcx, WPP_GLOBAL_Control
0x18002b58e  mov     r8, cs:WPP_GLOBAL_Control
0x18002b595  cmp     r8, rcx
0x18002b598  jz      loc_18002B92D
0x18002b59e  lea     edi, [rsi-18h]
0x18002b5a1  cmp     [r8+19h], dil
0x18002b5a5  jb      loc_18002B92D
0x18002b5ab  test    [r8+1Ch], r12b
0x18002b5af  jz      loc_18002B92D
0x18002b5b5  mov     edx, eax
0x18002b5b7  lea     rcx, aConvertstrings_0; "ConvertStringSidToSid failed. Error %x"
0x18002b5be  call    WppDbgPrint
0x18002b5c3  mov     edx, esi
0x18002b5c5  mov     [rsp+110h+dwMaximumSizeLow], ebx
0x18002b5c9  lea     r9, aNapbase; "NAPBASE"
0x18002b5d0  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b5d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5de  mov     rcx, [rcx+10h]
0x18002b5e2  call    WPP_SF_sd
0x18002b5e7  jmp     loc_18002B92D
0x18002b5ec  mov     rcx, [rbp+0E0h+Sid]; pSid
0x18002b5f0  call    cs:__imp_GetLengthSid
0x18002b5f6  mov     esi, eax
0x18002b5f8  mov     rcx, [rbp+0E0h+pSid]; pSid
0x18002b5fc  call    cs:__imp_GetLengthSid
0x18002b602  add     esi, eax
0x18002b604  mov     rcx, [rbp+0E0h+var_D8]; pSid
0x18002b608  call    cs:__imp_GetLengthSid
0x18002b60e  add     esi, eax
0x18002b610  mov     rcx, [rbp+0E0h+var_E0]; pSid
0x18002b614  call    cs:__imp_GetLengthSid
0x18002b61a  add     esi, 28h ; '('
0x18002b61d  xor     ebx, ebx
0x18002b61f  add     esi, eax
0x18002b621  jz      short loc_18002B686
0x18002b623  mov     edi, esi
0x18002b625  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002b62c  ja      short loc_18002B686
0x18002b62e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b635  add     rcx, 8
0x18002b639  add     rcx, rdi
0x18002b63c  cmp     rcx, rdi
0x18002b63f  jb      short loc_18002B686
0x18002b641  call    VerifyStackAvailable
0x18002b646  test    eax, eax
0x18002b648  jz      short loc_18002B686
0x18002b64a  lea     rax, [rsi+8]
0x18002b64e  lea     rcx, [rax+0Fh]
0x18002b652  cmp     rcx, rax
0x18002b655  ja      short loc_18002B661
0x18002b657  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002b661  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b665  mov     rax, rcx
0x18002b668  call    _alloca_probe
0x18002b66d  sub     rsp, rcx
0x18002b670  lea     rbx, [rsp+110h+var_E0]
0x18002b675  test    rbx, rbx
0x18002b678  jz      short loc_18002B686
0x18002b67a  mov     dword ptr [rbx], 6B637453h
0x18002b680  add     rbx, 8
0x18002b684  jnz     short loc_18002B6BC
0x18002b686  mov     eax, esi
0x18002b688  lea     rcx, [rsi+8]
0x18002b68c  cmp     rcx, rax
0x18002b68f  jb      short loc_18002B6B3
0x18002b691  mov     rax, cs:g_pfnAllocate
0x18002b698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b69d  mov     rbx, rax
0x18002b6a0  test    rax, rax
0x18002b6a3  jz      loc_18002B92D
0x18002b6a9  mov     dword ptr [rax], 70616548h
0x18002b6af  add     rbx, 8
0x18002b6b3  test    rbx, rbx
0x18002b6b6  jz      loc_18002B92D
0x18002b6bc  mov     [rbp+0E0h+var_C0], rbx
0x18002b6c0  mov     edi, 2
0x18002b6c5  mov     r8d, edi; dwAclRevision
0x18002b6c8  mov     edx, esi; nAclLength
0x18002b6ca  mov     rcx, rbx; pAcl
0x18002b6cd  call    cs:__imp_InitializeAcl
0x18002b6d3  test    eax, eax
0x18002b6d5  jnz     short loc_18002B720
0x18002b6d7  call    cs:__imp_GetLastError
0x18002b6dd  mov     ebx, eax
0x18002b6df  lea     rcx, WPP_GLOBAL_Control
0x18002b6e6  mov     rdx, cs:WPP_GLOBAL_Control
0x18002b6ed  cmp     rdx, rcx
0x18002b6f0  jz      loc_18002B924
0x18002b6f6  cmp     [rdx+19h], dil
0x18002b6fa  jb      loc_18002B924
0x18002b700  test    [rdx+1Ch], r12b
0x18002b704  jz      loc_18002B924
0x18002b70a  mov     edx, eax
0x18002b70c  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x18002b713  call    WppDbgPrint
0x18002b718  lea     edx, [rdi+19h]
0x18002b71b  jmp     loc_18002B902
0x18002b720  mov     r9, [rbp+0E0h+var_E0]; pSid
0x18002b724  mov     esi, 0F001Fh
0x18002b729  mov     r8d, esi; AccessMask
0x18002b72c  mov     edx, edi; dwAceRevision
0x18002b72e  mov     rcx, rbx; pAcl
0x18002b731  call    cs:__imp_AddAccessAllowedAce
0x18002b737  test    eax, eax
0x18002b739  jz      loc_18002B8C8
0x18002b73f  mov     r9, [rbp+0E0h+var_D8]; pSid
0x18002b743  mov     r8d, esi; AccessMask
0x18002b746  mov     edx, edi; dwAceRevision
0x18002b748  mov     rcx, rbx; pAcl
0x18002b74b  call    cs:__imp_AddAccessAllowedAce
0x18002b751  test    eax, eax
0x18002b753  jz      loc_18002B8C8
0x18002b759  mov     r9, [rbp+0E0h+pSid]; pSid
0x18002b75d  mov     r8d, esi; AccessMask
0x18002b760  mov     edx, edi; dwAceRevision
0x18002b762  mov     rcx, rbx; pAcl
0x18002b765  call    cs:__imp_AddAccessAllowedAce
0x18002b76b  test    eax, eax
0x18002b76d  jz      loc_18002B8C8
0x18002b773  mov     r9, [rbp+0E0h+Sid]; pSid
0x18002b777  mov     r8d, esi; AccessMask
0x18002b77a  mov     edx, edi; dwAceRevision
0x18002b77c  mov     rcx, rbx; pAcl
0x18002b77f  call    cs:__imp_AddAccessAllowedAce
0x18002b785  test    eax, eax
0x18002b787  jz      loc_18002B8C8
0x18002b78d  mov     edx, r12d; dwRevision
0x18002b790  lea     rcx, [rbp+0E0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002b797  call    cs:__imp_InitializeSecurityDescriptor
0x18002b79d  test    eax, eax
0x18002b79f  jnz     short loc_18002B7EC
0x18002b7a1  call    cs:__imp_GetLastError
0x18002b7a7  mov     ebx, eax
0x18002b7a9  lea     rcx, WPP_GLOBAL_Control
0x18002b7b0  mov     rdx, cs:WPP_GLOBAL_Control
0x18002b7b7  cmp     rdx, rcx
0x18002b7ba  jz      loc_18002B924
0x18002b7c0  cmp     [rdx+19h], dil
0x18002b7c4  jb      loc_18002B924
0x18002b7ca  test    [rdx+1Ch], r12b
0x18002b7ce  jz      loc_18002B924
0x18002b7d4  mov     edx, eax
0x18002b7d6  lea     rcx, aInitializesecu; "InitializeSecurityDescriptor failed. Er"...
0x18002b7dd  call    WppDbgPrint
0x18002b7e2  mov     edx, 1Dh
0x18002b7e7  jmp     loc_18002B902
0x18002b7ec  xor     r9d, r9d; bDaclDefaulted
0x18002b7ef  mov     r8, rbx; pDacl
0x18002b7f2  mov     edx, r12d; bDaclPresent
0x18002b7f5  lea     rcx, [rbp+0E0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002b7fc  call    cs:__imp_SetSecurityDescriptorDacl
0x18002b802  test    eax, eax
0x18002b804  jnz     short loc_18002B851
0x18002b806  call    cs:__imp_GetLastError
0x18002b80c  mov     ebx, eax
0x18002b80e  lea     rcx, WPP_GLOBAL_Control
0x18002b815  mov     rdx, cs:WPP_GLOBAL_Control
0x18002b81c  cmp     rdx, rcx
0x18002b81f  jz      loc_18002B924
0x18002b825  cmp     [rdx+19h], dil
0x18002b829  jb      loc_18002B924
0x18002b82f  test    [rdx+1Ch], r12b
0x18002b833  jz      loc_18002B924
0x18002b839  mov     edx, eax
0x18002b83b  lea     rcx, aSetsecuritydes; "SetSecurityDescriptorDacl failed. Error"...
0x18002b842  call    WppDbgPrint
0x18002b847  mov     edx, 1Eh
0x18002b84c  jmp     loc_18002B902
0x18002b851  mov     qword ptr [rbp+0E0h+FileMappingAttributes.nLength], 18h
0x18002b859  mov     qword ptr [rbp+0E0h+FileMappingAttributes.bInheritHandle], r12
0x18002b85d  lea     rax, [rbp+0E0h+pSecurityDescriptor]
0x18002b864  mov     [rbp+0E0h+FileMappingAttributes.lpSecurityDescriptor], rax
0x18002b868  lea     rax, Name; "{A5B99A4E-2959-11D1-BAC8-00C04FC2E20D}"
0x18002b86f  mov     [rsp+110h+lpName], rax; lpName
0x18002b874  mov     [rsp+110h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x18002b879  xor     r9d, r9d; dwMaximumSizeHigh
0x18002b87c  mov     r8d, 4000004h; flProtect
0x18002b882  lea     rdx, [rbp+0E0h+FileMappingAttributes]; lpFileMappingAttributes
0x18002b886  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002b88a  call    cs:__imp_CreateFileMappingW
0x18002b890  mov     rbx, rax
0x18002b893  lea     rcx, [rbp+0E0h+var_C0]; this
0x18002b897  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18002b89c  lea     rcx, [rbp+0E0h+var_B8]; this
0x18002b8a0  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b8a5  lea     rcx, [rbp+0E0h+var_A8]; this
0x18002b8a9  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b8ae  lea     rcx, [rbp+0E0h+var_98]; this
0x18002b8b2  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b8b7  lea     rcx, [rbp+0E0h+var_88]; this
0x18002b8bb  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b8c0  mov     rax, rbx
0x18002b8c3  jmp     loc_18002B953
0x18002b8c8  call    cs:__imp_GetLastError
0x18002b8ce  mov     ebx, eax
0x18002b8d0  lea     rcx, WPP_GLOBAL_Control
0x18002b8d7  mov     rdx, cs:WPP_GLOBAL_Control
0x18002b8de  cmp     rdx, rcx
0x18002b8e1  jz      short loc_18002B924
0x18002b8e3  cmp     [rdx+19h], dil
0x18002b8e7  jb      short loc_18002B924
0x18002b8e9  test    [rdx+1Ch], r12b
0x18002b8ed  jz      short loc_18002B924
0x18002b8ef  mov     edx, eax
0x18002b8f1  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x18002b8f8  call    WppDbgPrint
0x18002b8fd  mov     edx, 1Ch
0x18002b902  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b909  mov     [rsp+110h+dwMaximumSizeLow], ebx
0x18002b90d  lea     r9, aNapbase; "NAPBASE"
0x18002b914  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b91b  mov     rcx, [rcx+10h]
0x18002b91f  call    WPP_SF_sd
0x18002b924  lea     rcx, [rbp+0E0h+var_C0]; this
0x18002b928  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18002b92d  lea     rcx, [rbp+0E0h+var_B8]; this
0x18002b931  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b936  lea     rcx, [rbp+0E0h+var_A8]; this
0x18002b93a  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b93f  lea     rcx, [rbp+0E0h+var_98]; this
0x18002b943  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b948  lea     rcx, [rbp+0E0h+var_88]; this
0x18002b94c  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002b951  xor     eax, eax
0x18002b953  mov     rcx, [rbp+0E0h+var_38]
0x18002b95a  xor     rcx, rbp; StackCookie
0x18002b95d  call    __security_check_cookie
0x18002b962  lea     rsp, [rbp+0B8h]
0x18002b969  pop     r14
0x18002b96b  pop     r12
0x18002b96d  pop     rdi
0x18002b96e  pop     rsi
0x18002b96f  pop     rbx
0x18002b970  pop     rbp
0x18002b971  retn
```
