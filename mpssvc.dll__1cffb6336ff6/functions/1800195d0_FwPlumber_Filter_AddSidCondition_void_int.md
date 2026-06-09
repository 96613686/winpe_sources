# FwPlumber::Filter::AddSidCondition(void *,int)

- ea: `0x1800195d0`
- end: `0x18001a4db`
- name: `?AddSidCondition@Filter@FwPlumber@@QEAAXPEAXH@Z`
- size: `3851`
- prototype: `void __fastcall(FwPlumber::Filter *this, void *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000da60`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x1800195d0`
- `0x18001a4e4`
- `0x18001a780`
- `0x18001a8c0`
- `0x18006b670`
- `0x18006f520`
- `0x18006f614`
- `0x18006ffc8`
- `0x18007377c`
- `0x1800738b2`
- `0x1800738d6`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a13b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a13b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a30f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a35d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019736`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180019736`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001996a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001996a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001993a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001993a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180019903`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180019903`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800197e5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019b39`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019b99`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019bfb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019c58`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019cc4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800197e5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019b39`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019b99`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019bfb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019c58`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180019cc4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a12`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a42`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a52`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a62`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a12`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a42`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a52`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180019a62`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800198e8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800198e8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180019809`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180019809`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019828`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019852`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019872`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019892`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800198b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800198d2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019828`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019852`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019872`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180019892`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800198b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800198d2`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180019959`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180019959`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001991e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18001991e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001976b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019b4a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019baa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c69`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019cd5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001976b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019b4a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019baa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c0c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019c69`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180019cd5`
- `fwbase!FwAlloc` at `0x180019609`
- `fwbase!FwAlloc` at `0x18001964f`
- `fwbase!FwAlloc` at `0x180019695`
- `fwbase!FwAlloc` at `0x180019609`
- `fwbase!FwAlloc` at `0x18001964f`
- `fwbase!FwAlloc` at `0x180019695`
- `fwbase!FwFree` at `0x180019a6c`
- `fwbase!FwFree` at `0x180019a76`
- `fwbase!FwFree` at `0x180019a80`
- `fwbase!FwFree` at `0x180019a6c`
- `fwbase!FwFree` at `0x180019a76`
- `fwbase!FwFree` at `0x180019a80`

## pseudocode

```c
void __fastcall FwPlumber::Filter::AddSidCondition(FwPlumber::Filter *this, void *a2, int a3)
{
  struct _ACL *v5; // rbx
  void *v6; // rdi
  void *v7; // rsi
  __int64 v8; // rcx
  DWORD v9; // r12d
  __int64 v10; // r15
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r14
  DWORD *v14; // rax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // kr00_8
  void *v17; // rax
  int v18; // edx
  void *v19; // r12
  FwPlumber *v20; // rcx
  unsigned int v21; // eax
  int v22; // edx
  DWORD v23; // r12d
  unsigned int v24; // eax
  int v25; // edx
  DWORD v26; // r12d
  unsigned int v27; // eax
  int v28; // edx
  DWORD v29; // r12d
  unsigned int v30; // eax
  int v31; // edx
  DWORD v32; // r12d
  unsigned int v33; // eax
  int v34; // edx
  DWORD LastError; // eax
  signed int v36; // ebx
  DWORD v37; // eax
  signed int v38; // ebx
  DWORD v39; // eax
  signed int v40; // ebx
  DWORD v41; // eax
  signed int v42; // ebx
  DWORD v43; // eax
  signed int v44; // ebx
  DWORD v45; // eax
  signed int v46; // ebx
  DWORD v47; // eax
  signed int v48; // ebx
  DWORD v49; // eax
  signed int v50; // ebx
  DWORD v51; // eax
  signed int v52; // ebx
  DWORD v53; // eax
  signed int v54; // ebx
  DWORD v55; // eax
  signed int v56; // ebx
  DWORD v57; // eax
  signed int v58; // ebx
  DWORD v59; // eax
  signed int v60; // ebx
  _QWORD pExceptionObject[4]; // [rsp+60h] [rbp-49h] BYREF
  DWORD dwBufferLength; // [rsp+80h] [rbp-29h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v63; // [rsp+84h] [rbp-25h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+8Ch] [rbp-1Dh] BYREF
  PSID v65; // [rsp+98h] [rbp-11h] BYREF
  PSID v66; // [rsp+A0h] [rbp-9h] BYREF
  PSID v67; // [rsp+A8h] [rbp-1h] BYREF
  PSID v68; // [rsp+B0h] [rbp+7h] BYREF
  PSID pSid; // [rsp+B8h] [rbp+Fh] BYREF
  PSID pOwner; // [rsp+C0h] [rbp+17h] BYREF

  pExceptionObject[0] = this;
  v5 = (struct _ACL *)FwAlloc(4096);
  pExceptionObject[1] = v5;
  if ( !v5 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
    LODWORD(pExceptionObject[0]) = 14;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  v6 = (void *)FwAlloc(4096);
  pExceptionObject[2] = v6;
  if ( !v6 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
    LODWORD(pExceptionObject[0]) = 14;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  v7 = (void *)FwAlloc(4096);
  pExceptionObject[3] = v7;
  if ( !v7 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
    LODWORD(pExceptionObject[0]) = 14;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  pOwner = 0;
  pSid = 0;
  v68 = 0;
  v67 = 0;
  v66 = 0;
  v65 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v8 + 16), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 2147500035LL);
    LODWORD(pExceptionObject[0]) = -2147467261;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( !IsValidSid(a2) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_489b48d90f353cde71bd342750f78ef2_Traceguids,
        2147942487LL);
    LODWORD(pExceptionObject[0]) = -2147024809;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  v9 = GetLengthSid(a2) + 16;
  if ( v9 > 0x1000 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
    LODWORD(pExceptionObject[0]) = 14;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pOwner) )
  {
    LastError = GetLastError();
    v36 = LastError;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, LastError);
    if ( v36 > 0 )
      v36 = (unsigned __int16)v36 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v36;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( a3 == 1 )
  {
    *(_DWORD *)v63.Value = 0;
    *(_WORD *)&v63.Value[4] = 3840;
    v21 = AllocateAndInitializeSid(&v63, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid);
    FwPlumber::ThrowIf32Bool((FwPlumber *)v21, v22);
    v23 = GetLengthSid(pSid) + v9 + 8;
    if ( v23 > 0x1000 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
      LODWORD(pExceptionObject[0]) = 14;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    v24 = AllocateAndInitializeSid(&v63, 2u, 3u, 1u, 0, 0, 0, 0, 0, 0, &v68);
    FwPlumber::ThrowIf32Bool((FwPlumber *)v24, v25);
    v26 = GetLengthSid(v68) + v23 + 8;
    if ( v26 > 0x1000 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
      LODWORD(pExceptionObject[0]) = 14;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    v27 = AllocateAndInitializeSid(&v63, 2u, 3u, 2u, 0, 0, 0, 0, 0, 0, &v67);
    FwPlumber::ThrowIf32Bool((FwPlumber *)v27, v28);
    v29 = GetLengthSid(v67) + v26 + 8;
    if ( v29 > 0x1000 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
      LODWORD(pExceptionObject[0]) = 14;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    v30 = AllocateAndInitializeSid(&v63, 2u, 3u, 3u, 0, 0, 0, 0, 0, 0, &v66);
    FwPlumber::ThrowIf32Bool((FwPlumber *)v30, v31);
    v32 = GetLengthSid(v66) + v29 + 8;
    if ( v32 > 0x1000 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
      LODWORD(pExceptionObject[0]) = 14;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    v33 = AllocateAndInitializeSid(&v63, 5u, 3u, 0xFB3842CD, 0x4F839E2Au, 0x74BCC8Fu, 0xE99A1361, 0, 0, 0, &v65);
    FwPlumber::ThrowIf32Bool((FwPlumber *)v33, v34);
    v9 = GetLengthSid(v65) + v32 + 8;
    if ( v9 > 0x1000 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 14);
      LODWORD(pExceptionObject[0]) = 14;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
  }
  if ( !InitializeAcl(v5, v9, 2u) )
  {
    v37 = GetLastError();
    v38 = v37;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v37);
    if ( v38 > 0 )
      v38 = (unsigned __int16)v38 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v38;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, a2) )
  {
    v39 = GetLastError();
    v40 = v39;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v39);
    if ( v40 > 0 )
      v40 = (unsigned __int16)v40 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v40;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( a3 == 1 )
  {
    if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, pSid) )
    {
      v51 = GetLastError();
      v52 = v51;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v51);
      if ( v52 > 0 )
        v52 = (unsigned __int16)v52 | 0x80070000;
      LODWORD(pExceptionObject[0]) = v52;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, v68) )
    {
      v53 = GetLastError();
      v54 = v53;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v53);
      if ( v54 > 0 )
        v54 = (unsigned __int16)v54 | 0x80070000;
      LODWORD(pExceptionObject[0]) = v54;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, v67) )
    {
      v55 = GetLastError();
      v56 = v55;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v55);
      if ( v56 > 0 )
        v56 = (unsigned __int16)v56 | 0x80070000;
      LODWORD(pExceptionObject[0]) = v56;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, v66) )
    {
      v57 = GetLastError();
      v58 = v57;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v57);
      if ( v58 > 0 )
        v58 = (unsigned __int16)v58 | 0x80070000;
      LODWORD(pExceptionObject[0]) = v58;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
    if ( !AddAccessAllowedAce(v5, 2u, 0x20001u, v65) )
    {
      v59 = GetLastError();
      v60 = v59;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v59);
      if ( v60 > 0 )
        v60 = (unsigned __int16)v60 | 0x80070000;
      LODWORD(pExceptionObject[0]) = v60;
      throw (FwPlumber::Exception *)pExceptionObject;
    }
  }
  if ( !InitializeSecurityDescriptor(v6, 1u) )
  {
    v41 = GetLastError();
    v42 = v41;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v41);
    if ( v42 > 0 )
      v42 = (unsigned __int16)v42 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v42;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( !SetSecurityDescriptorOwner(v6, pOwner, 1) )
  {
    v43 = GetLastError();
    v44 = v43;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v43);
    if ( v44 > 0 )
      v44 = (unsigned __int16)v44 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v44;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( !SetSecurityDescriptorGroup(v6, pOwner, 1) )
  {
    v45 = GetLastError();
    v46 = v45;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v45);
    if ( v46 > 0 )
      v46 = (unsigned __int16)v46 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v46;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  if ( !SetSecurityDescriptorDacl(v6, 1, v5, 0) )
  {
    v47 = GetLastError();
    v48 = v47;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v47);
    if ( v48 > 0 )
      v48 = (unsigned __int16)v48 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v48;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  dwBufferLength = 4096;
  if ( !MakeSelfRelativeSD(v6, v7, &dwBufferLength) )
  {
    v49 = GetLastError();
    v50 = v49;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, v49);
    if ( v50 > 0 )
      v50 = (unsigned __int16)v50 | 0x80070000;
    LODWORD(pExceptionObject[0]) = v50;
    throw (FwPlumber::Exception *)pExceptionObject;
  }
  dwBufferLength = GetSecurityDescriptorLength(v7);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  v10 = pExceptionObject[0];
  v11 = *(_DWORD *)(pExceptionObject[0] + 200LL);
  if ( *(_DWORD *)(pExceptionObject[0] + 112LL) >= v11 )
  {
    v16 = 2 * v11;
    v15 = 40 * v16;
    if ( !is_mul_ok(v16, 0x28u) )
      v15 = -1;
    v17 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v17;
    if ( !v17 )
    {
      v20 = (FwPlumber *)WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
      FwPlumber::Throw(v20, v18);
    }
    memset_0(v17, 0, 40LL * (unsigned int)(2 * *(_DWORD *)(pExceptionObject[0] + 200LL)));
    *(_DWORD *)(pExceptionObject[0] + 200LL) *= 2;
    memcpy_0(v19, *(const void **)(v10 + 120), 40LL * *(unsigned int *)(v10 + 112));
    operator delete(*(void **)(v10 + 120));
    *(_QWORD *)(v10 + 120) = v19;
  }
  v12 = *(unsigned int *)(v10 + 112);
  v13 = *(_QWORD *)(v10 + 120) + 40 * v12;
  *(_DWORD *)(v10 + 112) = v12 + 1;
  *(GUID *)v13 = FWPM_CONDITION_ALE_USER_ID;
  *(_DWORD *)(v13 + 16) = 0;
  *(_DWORD *)(v13 + 24) = 14;
  v14 = (DWORD *)FwPlumber::Filter::Allocate<FWP_BYTE_BLOB_>(v10);
  *(_QWORD *)(v13 + 32) = v14;
  *v14 = dwBufferLength;
  *(_QWORD *)(*(_QWORD *)(v13 + 32) + 8LL) = FwPlumber::Filter::Allocate<unsigned char>(v10, dwBufferLength);
  memcpy_0(*(void **)(*(_QWORD *)(v13 + 32) + 8LL), v7, dwBufferLength);
  if ( v65 )
    FreeSid(v65);
  if ( v66 )
    FreeSid(v66);
  if ( v67 )
    FreeSid(v67);
  if ( v68 )
    FreeSid(v68);
  if ( pSid )
    FreeSid(pSid);
  if ( pOwner )
    FreeSid(pOwner);
  FwFree(v7);
  FwFree(v6);
  FwFree(v5);
}

```

## disassembly

```asm
0x1800195d0  mov     [rsp-8+arg_10], rbx
0x1800195d5  push    rbp
0x1800195d6  push    rsi
0x1800195d7  push    rdi
0x1800195d8  push    r12
0x1800195da  push    r13
0x1800195dc  push    r14
0x1800195de  push    r15
0x1800195e0  lea     rbp, [rsp-27h]
0x1800195e5  sub     rsp, 0D0h
0x1800195ec  mov     rax, cs:__security_cookie
0x1800195f3  xor     rax, rsp
0x1800195f6  mov     [rbp+57h+var_38], rax
0x1800195fa  mov     r13d, r8d
0x1800195fd  mov     r15, rdx
0x180019600  mov     [rbp+57h+pExceptionObject], rcx
0x180019604  mov     ecx, 1000h
0x180019609  call    cs:__imp_FwAlloc
0x18001960f  mov     rbx, rax
0x180019612  mov     [rbp+57h+var_98], rax
0x180019616  test    rax, rax
0x180019619  jnz     short loc_18001964A
0x18001961b  lea     r14, WPP_GLOBAL_Control
0x180019622  mov     rcx, cs:WPP_GLOBAL_Control
0x180019629  cmp     rcx, r14
0x18001962c  jnz     loc_180019E20
0x180019632  mov     dword ptr [rbp+57h+pExceptionObject], 0Eh
0x180019639  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180019640  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019644  call    _CxxThrowException_0
0x18001964a  mov     ecx, 1000h
0x18001964f  call    cs:__imp_FwAlloc
0x180019655  mov     rdi, rax
0x180019658  mov     [rbp+57h+var_90], rax
0x18001965c  test    rax, rax
0x18001965f  jnz     short loc_180019690
0x180019661  lea     r14, WPP_GLOBAL_Control
0x180019668  mov     rcx, cs:WPP_GLOBAL_Control
0x18001966f  cmp     rcx, r14
0x180019672  jnz     loc_180019E4A
0x180019678  mov     dword ptr [rbp+57h+pExceptionObject], 0Eh
0x18001967f  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180019686  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001968a  call    _CxxThrowException_0
0x180019690  mov     ecx, 1000h
0x180019695  call    cs:__imp_FwAlloc
0x18001969b  mov     rsi, rax
0x18001969e  mov     [rbp+57h+var_88], rax
0x1800196a2  test    rax, rax
0x1800196a5  jnz     short loc_1800196D6
0x1800196a7  lea     r14, WPP_GLOBAL_Control
0x1800196ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196b5  cmp     rcx, r14
0x1800196b8  jnz     loc_180019E74
0x1800196be  mov     dword ptr [rbp+57h+pExceptionObject], 0Eh
0x1800196c5  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x1800196cc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800196d0  call    _CxxThrowException_0
0x1800196d6  xor     eax, eax
0x1800196d8  mov     [rbp+57h+pOwner], rax
0x1800196dc  mov     [rbp+57h+var_48], rax
0x1800196e0  mov     [rbp+57h+var_50], rax
0x1800196e4  mov     [rbp+57h+var_58], rax
0x1800196e8  mov     [rbp+57h+var_60], rax
0x1800196ec  mov     [rbp+57h+var_68], rax
0x1800196f0  lea     r14, WPP_GLOBAL_Control
0x1800196f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196fe  cmp     rcx, r14
0x180019701  jz      short loc_18001970D
0x180019703  test    byte ptr [rcx+1Ch], 8
0x180019707  jnz     loc_180019D17
0x18001970d  test    r15, r15
0x180019710  jnz     short loc_180019733
0x180019712  cmp     rcx, r14
0x180019715  jnz     loc_180019DA2
0x18001971b  mov     dword ptr [rbp+57h+pExceptionObject], 80004003h
0x180019722  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180019729  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001972d  call    _CxxThrowException_0
0x180019733  mov     rcx, r15; pSid
0x180019736  call    cs:__imp_IsValidSid
0x18001973c  test    eax, eax
0x18001973e  jnz     short loc_180019768
0x180019740  mov     rcx, cs:WPP_GLOBAL_Control
0x180019747  cmp     rcx, r14
0x18001974a  jnz     loc_180019DCC
0x180019750  mov     dword ptr [rbp+57h+pExceptionObject], 80070057h
0x180019757  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001975e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180019762  call    _CxxThrowException_0
0x180019768  mov     rcx, r15; pSid
0x18001976b  call    cs:__imp_GetLengthSid
0x180019771  lea     r12d, [rax+10h]
0x180019775  cmp     r12d, 1000h
0x18001977c  jbe     short loc_1800197A6
0x18001977e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019785  cmp     rcx, r14
0x180019788  jnz     loc_180019DF6
0x18001978e  mov     dword ptr [rbp+57h+pExceptionObject], 0Eh
0x180019795  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001979c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800197a0  call    _CxxThrowException_0
0x1800197a6  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x1800197ad  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800197b3  lea     rax, [rbp+57h+pOwner]
0x1800197b7  mov     [rsp+100h+pSid], rax; pSid
0x1800197bc  xor     eax, eax
0x1800197be  mov     [rsp+100h+nSubAuthority7], eax; nSubAuthority7
0x1800197c2  mov     [rsp+100h+nSubAuthority6], eax; nSubAuthority6
0x1800197c6  mov     [rsp+100h+nSubAuthority5], eax; nSubAuthority5
0x1800197ca  mov     [rsp+100h+nSubAuthority4], eax; nSubAuthority4
0x1800197ce  mov     [rsp+100h+nSubAuthority3], eax; nSubAuthority3
0x1800197d2  mov     [rsp+100h+nSubAuthority2], eax; nSubAuthority2
0x1800197d6  xor     r9d, r9d; nSubAuthority1
0x1800197d9  mov     r8d, 12h; nSubAuthority0
0x1800197df  mov     dl, 1; nSubAuthorityCount
0x1800197e1  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800197e5  call    cs:__imp_AllocateAndInitializeSid
0x1800197eb  test    eax, eax
0x1800197ed  jz      loc_180019FB5
0x1800197f3  cmp     r13d, 1
0x1800197f7  jz      loc_180019AF5
0x1800197fd  mov     r8d, 2; dwAclRevision
0x180019803  mov     edx, r12d; nAclLength
0x180019806  mov     rcx, rbx; pAcl
0x180019809  call    cs:__imp_InitializeAcl
0x18001980f  test    eax, eax
0x180019811  jz      loc_18001A003
0x180019817  mov     r9, r15; pSid
0x18001981a  mov     edx, 2; dwAceRevision
0x18001981f  mov     r8d, 20001h; AccessMask
0x180019825  mov     rcx, rbx; pAcl
0x180019828  call    cs:__imp_AddAccessAllowedAce
0x18001982e  test    eax, eax
0x180019830  jz      loc_18001A051
0x180019836  cmp     r13d, 1
0x18001983a  jnz     loc_1800198E0
0x180019840  mov     r9, [rbp+57h+var_48]; pSid
0x180019844  mov     edx, 2; dwAceRevision
0x180019849  mov     r8d, 20001h; AccessMask
0x18001984f  mov     rcx, rbx; pAcl
0x180019852  call    cs:__imp_AddAccessAllowedAce
0x180019858  test    eax, eax
0x18001985a  jz      loc_18001A225
0x180019860  mov     r9, [rbp+57h+var_50]; pSid
0x180019864  mov     edx, 2; dwAceRevision
0x180019869  mov     r8d, 20001h; AccessMask
0x18001986f  mov     rcx, rbx; pAcl
0x180019872  call    cs:__imp_AddAccessAllowedAce
0x180019878  test    eax, eax
0x18001987a  jz      loc_18001A273
0x180019880  mov     r9, [rbp+57h+var_58]; pSid
0x180019884  mov     edx, 2; dwAceRevision
0x180019889  mov     r8d, 20001h; AccessMask
0x18001988f  mov     rcx, rbx; pAcl
0x180019892  call    cs:__imp_AddAccessAllowedAce
0x180019898  test    eax, eax
0x18001989a  jz      loc_18001A2C1
0x1800198a0  mov     r9, [rbp+57h+var_60]; pSid
0x1800198a4  mov     edx, 2; dwAceRevision
0x1800198a9  mov     r8d, 20001h; AccessMask
0x1800198af  mov     rcx, rbx; pAcl
0x1800198b2  call    cs:__imp_AddAccessAllowedAce
0x1800198b8  test    eax, eax
0x1800198ba  jz      loc_18001A30F
0x1800198c0  mov     r9, [rbp+57h+var_68]; pSid
0x1800198c4  mov     edx, 2; dwAceRevision
0x1800198c9  mov     r8d, 20001h; AccessMask
0x1800198cf  mov     rcx, rbx; pAcl
0x1800198d2  call    cs:__imp_AddAccessAllowedAce
0x1800198d8  test    eax, eax
0x1800198da  jz      loc_18001A35D
0x1800198e0  mov     edx, 1; dwRevision
0x1800198e5  mov     rcx, rdi; pSecurityDescriptor
0x1800198e8  call    cs:__imp_InitializeSecurityDescriptor
0x1800198ee  test    eax, eax
0x1800198f0  jz      loc_18001A09F
0x1800198f6  mov     r8d, 1; bOwnerDefaulted
0x1800198fc  mov     rdx, [rbp+57h+pOwner]; pOwner
0x180019900  mov     rcx, rdi; pSecurityDescriptor
0x180019903  call    cs:__imp_SetSecurityDescriptorOwner
0x180019909  test    eax, eax
0x18001990b  jz      loc_18001A0ED
0x180019911  mov     r8d, 1; bGroupDefaulted
0x180019917  mov     rdx, [rbp+57h+pOwner]; pGroup
0x18001991b  mov     rcx, rdi; pSecurityDescriptor
0x18001991e  call    cs:__imp_SetSecurityDescriptorGroup
0x180019924  test    eax, eax
0x180019926  jz      loc_18001A13B
0x18001992c  xor     r9d, r9d; bDaclDefaulted
0x18001992f  mov     r8, rbx; pDacl
0x180019932  mov     edx, 1; bDaclPresent
0x180019937  mov     rcx, rdi; pSecurityDescriptor
0x18001993a  call    cs:__imp_SetSecurityDescriptorDacl
0x180019940  test    eax, eax
0x180019942  jz      loc_18001A189
0x180019948  mov     [rbp+57h+dwBufferLength], 1000h
0x18001994f  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180019953  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x180019956  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180019959  call    cs:__imp_MakeSelfRelativeSD
0x18001995f  test    eax, eax
0x180019961  jz      loc_18001A1D7
0x180019967  mov     rcx, rsi; pSecurityDescriptor
0x18001996a  call    cs:__imp_GetSecurityDescriptorLength
0x180019970  mov     [rbp+57h+dwBufferLength], eax
0x180019973  mov     rcx, cs:WPP_GLOBAL_Control
0x18001997a  cmp     rcx, r14
0x18001997d  jz      short loc_180019989
0x18001997f  test    byte ptr [rcx+1Ch], 8
0x180019983  jnz     loc_180019D38
0x180019989  mov     r15, [rbp+57h+pExceptionObject]
0x18001998d  mov     eax, [r15+0C8h]
0x180019994  cmp     [r15+70h], eax
0x180019998  jnb     loc_180019AAE
0x18001999e  mov     edx, [r15+70h]
0x1800199a2  lea     rcx, [rdx+rdx*4]
0x1800199a6  mov     rax, [r15+78h]
0x1800199aa  lea     r14, [rax+rcx*8]
0x1800199ae  lea     eax, [rdx+1]
0x1800199b1  mov     [r15+70h], eax
0x1800199b5  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_ALE_USER_ID.Data1
0x1800199bc  movups  xmmword ptr [r14], xmm0
0x1800199c0  mov     dword ptr [r14+10h], 0
0x1800199c8  mov     dword ptr [r14+18h], 0Eh
0x1800199d0  mov     rcx, r15
0x1800199d3  call    ??$Allocate@UFWP_BYTE_BLOB_@@@Filter@FwPlumber@@IEAAPEAUFWP_BYTE_BLOB_@@I@Z; FwPlumber::Filter::Allocate<FWP_BYTE_BLOB_>(uint)
0x1800199d8  mov     [r14+20h], rax
0x1800199dc  mov     edx, [rbp+57h+dwBufferLength]
0x1800199df  mov     [rax], edx
0x1800199e1  mov     edx, [rbp+57h+dwBufferLength]
0x1800199e4  mov     rcx, r15
0x1800199e7  call    ??$Allocate@E@Filter@FwPlumber@@IEAAPEAEI@Z; FwPlumber::Filter::Allocate<uchar>(uint)
0x1800199ec  mov     rcx, [r14+20h]
0x1800199f0  mov     [rcx+8], rax
0x1800199f4  mov     r8d, [rbp+57h+dwBufferLength]; Size
0x1800199f8  mov     rcx, [r14+20h]
0x1800199fc  mov     rdx, rsi; Src
0x1800199ff  mov     rcx, [rcx+8]; void *
0x180019a03  call    memcpy_0
0x180019a08  nop
0x180019a09  mov     rcx, [rbp+57h+var_68]; pSid
0x180019a0d  test    rcx, rcx
0x180019a10  jz      short loc_180019A19
0x180019a12  call    cs:__imp_FreeSid
0x180019a18  nop
0x180019a19  mov     rcx, [rbp+57h+var_60]; pSid
0x180019a1d  test    rcx, rcx
0x180019a20  jz      short loc_180019A29
0x180019a22  call    cs:__imp_FreeSid
0x180019a28  nop
0x180019a29  mov     rcx, [rbp+57h+var_58]; pSid
0x180019a2d  test    rcx, rcx
0x180019a30  jz      short loc_180019A39
0x180019a32  call    cs:__imp_FreeSid
0x180019a38  nop
0x180019a39  mov     rcx, [rbp+57h+var_50]; pSid
0x180019a3d  test    rcx, rcx
0x180019a40  jz      short loc_180019A49
0x180019a42  call    cs:__imp_FreeSid
0x180019a48  nop
0x180019a49  mov     rcx, [rbp+57h+var_48]; pSid
0x180019a4d  test    rcx, rcx
0x180019a50  jz      short loc_180019A59
0x180019a52  call    cs:__imp_FreeSid
0x180019a58  nop
0x180019a59  mov     rcx, [rbp+57h+pOwner]; pSid
0x180019a5d  test    rcx, rcx
0x180019a60  jz      short loc_180019A69
0x180019a62  call    cs:__imp_FreeSid
0x180019a68  nop
0x180019a69  mov     rcx, rsi
0x180019a6c  call    cs:__imp_FwFree
0x180019a72  nop
0x180019a73  mov     rcx, rdi
0x180019a76  call    cs:__imp_FwFree
0x180019a7c  nop
0x180019a7d  mov     rcx, rbx
0x180019a80  call    cs:__imp_FwFree
0x180019a86  nop
0x180019a87  mov     rcx, [rbp+57h+var_38]
0x180019a8b  xor     rcx, rsp; StackCookie
0x180019a8e  call    __security_check_cookie
0x180019a93  mov     rbx, [rsp+100h+arg_10]
0x180019a9b  add     rsp, 0D0h
0x180019aa2  pop     r15
0x180019aa4  pop     r14
0x180019aa6  pop     r13
0x180019aa8  pop     r12
0x180019aaa  pop     rdi
0x180019aab  pop     rsi
0x180019aac  pop     rbp
0x180019aad  retn
0x180019aae  lea     ecx, [rax+rax]
0x180019ab1  mov     eax, 28h ; '('
0x180019ab6  mul     rcx
0x180019ab9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019ac0  cmovb   rax, rcx
0x180019ac4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019acb  mov     rcx, rax; unsigned __int64
  ... truncated ...
```
