# CreateStatisticsMutex(ushort const *)

- ea: `0x18002b978`
- end: `0x18002be25`
- name: `?CreateStatisticsMutex@@YAPEAXPEBG@Z`
- size: `1197`
- prototype: `void *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024c00`

## callees

- `0x18000dc54`
- `0x180014710`
- `0x18001d31c`
- `0x18002b19c`
- `0x18002b22c`
- `0x18002b978`
- `0x18002df44`
- `0x18002e230`
- `0x18002e2f0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002ba47`
- `KERNEL32!GetLastError` at `0x18002bba1`
- `KERNEL32!GetLastError` at `0x18002bc6b`
- `KERNEL32!GetLastError` at `0x18002bcd0`
- `KERNEL32!GetLastError` at `0x18002bd7d`
- `KERNEL32!GetLastError` at `0x18002ba47`
- `KERNEL32!GetLastError` at `0x18002bba1`
- `KERNEL32!GetLastError` at `0x18002bc6b`
- `KERNEL32!GetLastError` at `0x18002bcd0`
- `KERNEL32!GetLastError` at `0x18002bd7d`
- `KERNEL32!CreateMutexW` at `0x18002bd3f`
- `KERNEL32!CreateMutexW` at `0x18002bd3f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bcc6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002bcc6`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002bc61`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002bc61`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bbfb`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc15`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc2f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc49`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bbfb`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc15`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc2f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18002bc49`
- `ADVAPI32!InitializeAcl` at `0x18002bb97`
- `ADVAPI32!InitializeAcl` at `0x18002bb97`
- `ADVAPI32!GetLengthSid` at `0x18002baba`
- `ADVAPI32!GetLengthSid` at `0x18002bac6`
- `ADVAPI32!GetLengthSid` at `0x18002bad2`
- `ADVAPI32!GetLengthSid` at `0x18002bade`
- `ADVAPI32!GetLengthSid` at `0x18002baba`
- `ADVAPI32!GetLengthSid` at `0x18002bac6`
- `ADVAPI32!GetLengthSid` at `0x18002bad2`
- `ADVAPI32!GetLengthSid` at `0x18002bade`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002ba3d`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18002ba3d`

## string_xrefs

- `0x18002ba80`: `ConvertStringSidToSid failed. Error %!winerr!`
- `0x18002bbd6`: `AddAccessAllowedAce failed. Error %x`
- `0x18002bda6`: `AddAccessAllowedAce failed. Error %x`
- `0x18002bca0`: `InitializeSecurityDescriptor failed. Error %x`
- `0x18002bd05`: `SetSecurityDescriptorDacl failed. Error %x`

## pseudocode

```c
HANDLE __fastcall CreateStatisticsMutex(const unsigned __int16 *a1)
{
  char LastError; // bl
  DWORD LengthSid; // esi
  DWORD v3; // esi
  DWORD v4; // esi
  PSID *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  void *v9; // rsp
  void *v10; // rsp
  _DWORD *v11; // rax
  char v12; // bl
  int v13; // edx
  HANDLE v14; // rbx
  __int64 v16; // [rsp+0h] [rbp-30h] BYREF
  PSID v17; // [rsp+30h] [rbp+0h] BYREF
  PSID v18; // [rsp+38h] [rbp+8h] BYREF
  PSID pSid; // [rsp+40h] [rbp+10h] BYREF
  PSID Sid; // [rsp+48h] [rbp+18h] BYREF
  PSID *v21; // [rsp+50h] [rbp+20h] BYREF
  PSID *p_Sid; // [rsp+58h] [rbp+28h] BYREF
  int v23; // [rsp+60h] [rbp+30h]
  PSID *p_pSid; // [rsp+68h] [rbp+38h] BYREF
  int v25; // [rsp+70h] [rbp+40h]
  PSID *v26; // [rsp+78h] [rbp+48h] BYREF
  int v27; // [rsp+80h] [rbp+50h]
  PSID *v28; // [rsp+88h] [rbp+58h] BYREF
  int v29; // [rsp+90h] [rbp+60h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+98h] [rbp+68h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+B0h] [rbp+80h] BYREF

  v17 = 0;
  v18 = 0;
  pSid = 0;
  Sid = 0;
  v28 = &v17;
  v29 = 1;
  v26 = &v18;
  v27 = 1;
  p_pSid = &pSid;
  v25 = 1;
  p_Sid = &Sid;
  v23 = 0;
  if ( AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v17)
    || AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v18)
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
      WppDbgPrint("ConvertStringSidToSid failed. Error %!winerr!");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        LastError);
    }
    goto LABEL_47;
  }
  LengthSid = GetLengthSid(Sid);
  v3 = GetLengthSid(pSid) + LengthSid;
  v4 = GetLengthSid(v18) + v3;
  v5 = 0;
  v6 = GetLengthSid(v17) + v4 + 40;
  if ( (_DWORD)v6
    && (unsigned int)v6 <= (unsigned __int64)g_ulMaxStackAllocSize
    && (unsigned __int64)(unsigned int)v6 + g_ulAdditionalProbeSize + 8 >= (unsigned int)v6
    && (unsigned int)VerifyStackAvailable() )
  {
    v7 = v6 + 23;
    if ( v6 + 23 <= (unsigned __int64)(v6 + 8) )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = v7 & 0xFFFFFFFFFFFFFFF0uLL;
    v9 = alloca(v8);
    v10 = alloca(v8);
    v5 = &v17;
    if ( &v16 != (__int64 *)-48LL )
    {
      LODWORD(v17) = 1801679955;
      v5 = &v18;
      if ( &v18 )
      {
LABEL_21:
        v21 = v5;
        if ( InitializeAcl((PACL)v5, v6, 2u) )
        {
          if ( AddAccessAllowedAce((PACL)v5, 2u, 0x1F0001u, v17)
            && AddAccessAllowedAce((PACL)v5, 2u, 0x1F0001u, v18)
            && AddAccessAllowedAce((PACL)v5, 2u, 0x1F0001u, pSid)
            && AddAccessAllowedAce((PACL)v5, 2u, 0x1F0001u, Sid) )
          {
            if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)v5, 0) )
              {
                *(_QWORD *)&MutexAttributes.nLength = 24;
                *(_QWORD *)&MutexAttributes.bInheritHandle = 1;
                MutexAttributes.lpSecurityDescriptor = pSecurityDescriptor;
                v14 = CreateMutexW(&MutexAttributes, 0, L"{A5B99A4D-2959-11D1-BAC8-00C04FC2E20D}");
                SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v21);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_Sid);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_pSid);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v26);
                SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v28);
                return v14;
              }
              v12 = GetLastError();
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_46;
              }
              WppDbgPrint("SetSecurityDescriptorDacl failed. Error %x");
              v13 = 25;
            }
            else
            {
              v12 = GetLastError();
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_46;
              }
              WppDbgPrint("InitializeSecurityDescriptor failed. Error %x");
              v13 = 24;
            }
          }
          else
          {
            v12 = GetLastError();
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_46;
            }
            WppDbgPrint("AddAccessAllowedAce failed. Error %x");
            v13 = 23;
          }
        }
        else
        {
          v12 = GetLastError();
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_46;
          }
          WppDbgPrint("AddAccessAllowedAce failed. Error %x");
          v13 = 22;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
          (unsigned int)"NAPBASE",
          v12);
LABEL_46:
        SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v21);
        goto LABEL_47;
      }
    }
  }
  if ( v6 + 8 >= (unsigned __int64)(unsigned int)v6 )
  {
    v11 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
    if ( !v11 )
      goto LABEL_47;
    *v11 = 1885431112;
    v5 = (PSID *)(v11 + 2);
  }
  if ( v5 )
    goto LABEL_21;
LABEL_47:
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_Sid);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&p_pSid);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v26);
  SIDCleanupScopeGuard::~SIDCleanupScopeGuard((SIDCleanupScopeGuard *)&v28);
  return 0;
}

```

## disassembly

```asm
0x18002b978  push    rbp
0x18002b97a  push    rbx
0x18002b97b  push    rsi
0x18002b97c  push    rdi
0x18002b97d  push    r15
0x18002b97f  sub     rsp, 0E0h
0x18002b986  lea     rbp, [rsp+30h]
0x18002b98b  mov     rax, cs:__security_cookie
0x18002b992  xor     rax, rbp
0x18002b995  mov     [rbp+0D0h+var_28], rax
0x18002b99c  mov     [rbp+0D0h+var_D0], 0
0x18002b9a4  mov     [rbp+0D0h+var_C8], 0
0x18002b9ac  mov     [rbp+0D0h+pSid], 0
0x18002b9b4  mov     [rbp+0D0h+Sid], 0
0x18002b9bc  lea     rax, [rbp+0D0h+var_D0]
0x18002b9c0  mov     [rbp+0D0h+var_78], rax
0x18002b9c4  mov     r15d, 1
0x18002b9ca  mov     [rbp+0D0h+var_70], r15d
0x18002b9ce  lea     rax, [rbp+0D0h+var_C8]
0x18002b9d2  mov     [rbp+0D0h+var_88], rax
0x18002b9d6  mov     [rbp+0D0h+var_80], r15d
0x18002b9da  lea     rax, [rbp+0D0h+pSid]
0x18002b9de  mov     [rbp+0D0h+var_98], rax
0x18002b9e2  mov     [rbp+0D0h+var_90], r15d
0x18002b9e6  lea     rax, [rbp+0D0h+Sid]
0x18002b9ea  mov     [rbp+0D0h+var_A8], rax
0x18002b9ee  mov     [rbp+0D0h+var_A0], 0
0x18002b9f5  lea     rdx, [rbp+0D0h+var_D0]; void **
0x18002b9f9  lea     ecx, [r15+19h]; WellKnownSidType
0x18002b9fd  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002ba02  test    eax, eax
0x18002ba04  jnz     loc_18002BDE2
0x18002ba0a  lea     rdx, [rbp+0D0h+var_C8]; void **
0x18002ba0e  lea     ecx, [rax+39h]; WellKnownSidType
0x18002ba11  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002ba16  test    eax, eax
0x18002ba18  jnz     loc_18002BDE2
0x18002ba1e  lea     rdx, [rbp+0D0h+pSid]; void **
0x18002ba22  lea     ecx, [rax+3Ah]; WellKnownSidType
0x18002ba25  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002ba2a  test    eax, eax
0x18002ba2c  jnz     loc_18002BDE2
0x18002ba32  lea     rdx, [rbp+0D0h+Sid]; Sid
0x18002ba36  lea     rcx, StringSid; "S-1-5-80-611605672-2879557022-220662426"...
0x18002ba3d  call    cs:__imp_ConvertStringSidToSidW
0x18002ba43  test    eax, eax
0x18002ba45  jnz     short loc_18002BAB6
0x18002ba47  call    cs:__imp_GetLastError
0x18002ba4d  mov     ebx, eax
0x18002ba4f  lea     rcx, WPP_GLOBAL_Control
0x18002ba56  mov     rdx, cs:WPP_GLOBAL_Control
0x18002ba5d  cmp     rdx, rcx
0x18002ba60  jz      loc_18002BDE2
0x18002ba66  lea     edi, [r15+1]
0x18002ba6a  cmp     [rdx+19h], dil
0x18002ba6e  jb      loc_18002BDE2
0x18002ba74  test    [rdx+1Ch], r15b
0x18002ba78  jz      loc_18002BDE2
0x18002ba7e  mov     edx, eax
0x18002ba80  lea     rcx, aConvertstrings; "ConvertStringSidToSid failed. Error %!w"...
0x18002ba87  call    WppDbgPrint
0x18002ba8c  lea     edx, [rdi+13h]
0x18002ba8f  mov     [rsp+100h+var_E0], ebx
0x18002ba93  lea     r9, aNapbase; "NAPBASE"
0x18002ba9a  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002baa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002baa8  mov     rcx, [rcx+10h]
0x18002baac  call    WPP_SF_sd
0x18002bab1  jmp     loc_18002BDE2
0x18002bab6  mov     rcx, [rbp+0D0h+Sid]; pSid
0x18002baba  call    cs:__imp_GetLengthSid
0x18002bac0  mov     esi, eax
0x18002bac2  mov     rcx, [rbp+0D0h+pSid]; pSid
0x18002bac6  call    cs:__imp_GetLengthSid
0x18002bacc  add     esi, eax
0x18002bace  mov     rcx, [rbp+0D0h+var_C8]; pSid
0x18002bad2  call    cs:__imp_GetLengthSid
0x18002bad8  add     esi, eax
0x18002bada  mov     rcx, [rbp+0D0h+var_D0]; pSid
0x18002bade  call    cs:__imp_GetLengthSid
0x18002bae4  add     esi, 28h ; '('
0x18002bae7  xor     ebx, ebx
0x18002bae9  add     esi, eax
0x18002baeb  jz      short loc_18002BB50
0x18002baed  mov     edi, esi
0x18002baef  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18002baf6  ja      short loc_18002BB50
0x18002baf8  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002baff  add     rcx, 8
0x18002bb03  add     rcx, rdi
0x18002bb06  cmp     rcx, rdi
0x18002bb09  jb      short loc_18002BB50
0x18002bb0b  call    VerifyStackAvailable
0x18002bb10  test    eax, eax
0x18002bb12  jz      short loc_18002BB50
0x18002bb14  lea     rax, [rsi+8]
0x18002bb18  lea     rcx, [rax+0Fh]
0x18002bb1c  cmp     rcx, rax
0x18002bb1f  ja      short loc_18002BB2B
0x18002bb21  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002bb2b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002bb2f  mov     rax, rcx
0x18002bb32  call    _alloca_probe
0x18002bb37  sub     rsp, rcx
0x18002bb3a  lea     rbx, [rsp+100h+var_D0]
0x18002bb3f  test    rbx, rbx
0x18002bb42  jz      short loc_18002BB50
0x18002bb44  mov     dword ptr [rbx], 6B637453h
0x18002bb4a  add     rbx, 8
0x18002bb4e  jnz     short loc_18002BB86
0x18002bb50  mov     eax, esi
0x18002bb52  lea     rcx, [rsi+8]
0x18002bb56  cmp     rcx, rax
0x18002bb59  jb      short loc_18002BB7D
0x18002bb5b  mov     rax, cs:g_pfnAllocate
0x18002bb62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb67  mov     rbx, rax
0x18002bb6a  test    rax, rax
0x18002bb6d  jz      loc_18002BDE2
0x18002bb73  mov     dword ptr [rax], 70616548h
0x18002bb79  add     rbx, 8
0x18002bb7d  test    rbx, rbx
0x18002bb80  jz      loc_18002BDE2
0x18002bb86  mov     [rbp+0D0h+var_B0], rbx
0x18002bb8a  mov     edi, 2
0x18002bb8f  mov     r8d, edi; dwAclRevision
0x18002bb92  mov     edx, esi; nAclLength
0x18002bb94  mov     rcx, rbx; pAcl
0x18002bb97  call    cs:__imp_InitializeAcl
0x18002bb9d  test    eax, eax
0x18002bb9f  jnz     short loc_18002BBEA
0x18002bba1  call    cs:__imp_GetLastError
0x18002bba7  mov     ebx, eax
0x18002bba9  lea     rcx, WPP_GLOBAL_Control
0x18002bbb0  mov     rdx, cs:WPP_GLOBAL_Control
0x18002bbb7  cmp     rdx, rcx
0x18002bbba  jz      loc_18002BDD9
0x18002bbc0  cmp     [rdx+19h], dil
0x18002bbc4  jb      loc_18002BDD9
0x18002bbca  test    [rdx+1Ch], r15b
0x18002bbce  jz      loc_18002BDD9
0x18002bbd4  mov     edx, eax
0x18002bbd6  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x18002bbdd  call    WppDbgPrint
0x18002bbe2  lea     edx, [rdi+14h]
0x18002bbe5  jmp     loc_18002BDB7
0x18002bbea  mov     r9, [rbp+0D0h+var_D0]; pSid
0x18002bbee  mov     esi, 1F0001h
0x18002bbf3  mov     r8d, esi; AccessMask
0x18002bbf6  mov     edx, edi; dwAceRevision
0x18002bbf8  mov     rcx, rbx; pAcl
0x18002bbfb  call    cs:__imp_AddAccessAllowedAce
0x18002bc01  test    eax, eax
0x18002bc03  jz      loc_18002BD7D
0x18002bc09  mov     r9, [rbp+0D0h+var_C8]; pSid
0x18002bc0d  mov     r8d, esi; AccessMask
0x18002bc10  mov     edx, edi; dwAceRevision
0x18002bc12  mov     rcx, rbx; pAcl
0x18002bc15  call    cs:__imp_AddAccessAllowedAce
0x18002bc1b  test    eax, eax
0x18002bc1d  jz      loc_18002BD7D
0x18002bc23  mov     r9, [rbp+0D0h+pSid]; pSid
0x18002bc27  mov     r8d, esi; AccessMask
0x18002bc2a  mov     edx, edi; dwAceRevision
0x18002bc2c  mov     rcx, rbx; pAcl
0x18002bc2f  call    cs:__imp_AddAccessAllowedAce
0x18002bc35  test    eax, eax
0x18002bc37  jz      loc_18002BD7D
0x18002bc3d  mov     r9, [rbp+0D0h+Sid]; pSid
0x18002bc41  mov     r8d, esi; AccessMask
0x18002bc44  mov     edx, edi; dwAceRevision
0x18002bc46  mov     rcx, rbx; pAcl
0x18002bc49  call    cs:__imp_AddAccessAllowedAce
0x18002bc4f  test    eax, eax
0x18002bc51  jz      loc_18002BD7D
0x18002bc57  mov     edx, r15d; dwRevision
0x18002bc5a  lea     rcx, [rbp+0D0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002bc61  call    cs:__imp_InitializeSecurityDescriptor
0x18002bc67  test    eax, eax
0x18002bc69  jnz     short loc_18002BCB6
0x18002bc6b  call    cs:__imp_GetLastError
0x18002bc71  mov     ebx, eax
0x18002bc73  lea     rcx, WPP_GLOBAL_Control
0x18002bc7a  mov     rdx, cs:WPP_GLOBAL_Control
0x18002bc81  cmp     rdx, rcx
0x18002bc84  jz      loc_18002BDD9
0x18002bc8a  cmp     [rdx+19h], dil
0x18002bc8e  jb      loc_18002BDD9
0x18002bc94  test    [rdx+1Ch], r15b
0x18002bc98  jz      loc_18002BDD9
0x18002bc9e  mov     edx, eax
0x18002bca0  lea     rcx, aInitializesecu; "InitializeSecurityDescriptor failed. Er"...
0x18002bca7  call    WppDbgPrint
0x18002bcac  mov     edx, 18h
0x18002bcb1  jmp     loc_18002BDB7
0x18002bcb6  xor     r9d, r9d; bDaclDefaulted
0x18002bcb9  mov     r8, rbx; pDacl
0x18002bcbc  mov     edx, r15d; bDaclPresent
0x18002bcbf  lea     rcx, [rbp+0D0h+pSecurityDescriptor]; pSecurityDescriptor
0x18002bcc6  call    cs:__imp_SetSecurityDescriptorDacl
0x18002bccc  test    eax, eax
0x18002bcce  jnz     short loc_18002BD1B
0x18002bcd0  call    cs:__imp_GetLastError
0x18002bcd6  mov     ebx, eax
0x18002bcd8  lea     rcx, WPP_GLOBAL_Control
0x18002bcdf  mov     rdx, cs:WPP_GLOBAL_Control
0x18002bce6  cmp     rdx, rcx
0x18002bce9  jz      loc_18002BDD9
0x18002bcef  cmp     [rdx+19h], dil
0x18002bcf3  jb      loc_18002BDD9
0x18002bcf9  test    [rdx+1Ch], r15b
0x18002bcfd  jz      loc_18002BDD9
0x18002bd03  mov     edx, eax
0x18002bd05  lea     rcx, aSetsecuritydes; "SetSecurityDescriptorDacl failed. Error"...
0x18002bd0c  call    WppDbgPrint
0x18002bd11  mov     edx, 19h
0x18002bd16  jmp     loc_18002BDB7
0x18002bd1b  mov     qword ptr [rbp+0D0h+MutexAttributes.nLength], 18h
0x18002bd23  mov     qword ptr [rbp+0D0h+MutexAttributes.bInheritHandle], r15
0x18002bd27  lea     rax, [rbp+0D0h+pSecurityDescriptor]
0x18002bd2e  mov     [rbp+0D0h+MutexAttributes.lpSecurityDescriptor], rax
0x18002bd32  lea     r8, aA5b99a4d295911; "{A5B99A4D-2959-11D1-BAC8-00C04FC2E20D}"
0x18002bd39  xor     edx, edx; bInitialOwner
0x18002bd3b  lea     rcx, [rbp+0D0h+MutexAttributes]; lpMutexAttributes
0x18002bd3f  call    cs:__imp_CreateMutexW
0x18002bd45  mov     rbx, rax
0x18002bd48  lea     rcx, [rbp+0D0h+var_B0]; this
0x18002bd4c  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18002bd51  lea     rcx, [rbp+0D0h+var_A8]; this
0x18002bd55  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bd5a  lea     rcx, [rbp+0D0h+var_98]; this
0x18002bd5e  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bd63  lea     rcx, [rbp+0D0h+var_88]; this
0x18002bd67  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bd6c  lea     rcx, [rbp+0D0h+var_78]; this
0x18002bd70  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bd75  mov     rax, rbx
0x18002bd78  jmp     loc_18002BE08
0x18002bd7d  call    cs:__imp_GetLastError
0x18002bd83  mov     ebx, eax
0x18002bd85  lea     rcx, WPP_GLOBAL_Control
0x18002bd8c  mov     rdx, cs:WPP_GLOBAL_Control
0x18002bd93  cmp     rdx, rcx
0x18002bd96  jz      short loc_18002BDD9
0x18002bd98  cmp     [rdx+19h], dil
0x18002bd9c  jb      short loc_18002BDD9
0x18002bd9e  test    [rdx+1Ch], r15b
0x18002bda2  jz      short loc_18002BDD9
0x18002bda4  mov     edx, eax
0x18002bda6  lea     rcx, aAddaccessallow; "AddAccessAllowedAce failed. Error %x"
0x18002bdad  call    WppDbgPrint
0x18002bdb2  mov     edx, 17h
0x18002bdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bdbe  mov     [rsp+100h+var_E0], ebx
0x18002bdc2  lea     r9, aNapbase; "NAPBASE"
0x18002bdc9  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002bdd0  mov     rcx, [rcx+10h]
0x18002bdd4  call    WPP_SF_sd
0x18002bdd9  lea     rcx, [rbp+0D0h+var_B0]; this
0x18002bddd  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18002bde2  lea     rcx, [rbp+0D0h+var_A8]; this
0x18002bde6  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bdeb  lea     rcx, [rbp+0D0h+var_98]; this
0x18002bdef  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bdf4  lea     rcx, [rbp+0D0h+var_88]; this
0x18002bdf8  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002bdfd  lea     rcx, [rbp+0D0h+var_78]; this
0x18002be01  call    ??1SIDCleanupScopeGuard@@QEAA@XZ; SIDCleanupScopeGuard::~SIDCleanupScopeGuard(void)
0x18002be06  xor     eax, eax
0x18002be08  mov     rcx, [rbp+0D0h+var_28]
0x18002be0f  xor     rcx, rbp; StackCookie
0x18002be12  call    __security_check_cookie
0x18002be17  lea     rsp, [rbp+0B0h]
0x18002be1e  pop     r15
0x18002be20  pop     rdi
0x18002be21  pop     rsi
0x18002be22  pop     rbx
0x18002be23  pop     rbp
0x18002be24  retn
```
