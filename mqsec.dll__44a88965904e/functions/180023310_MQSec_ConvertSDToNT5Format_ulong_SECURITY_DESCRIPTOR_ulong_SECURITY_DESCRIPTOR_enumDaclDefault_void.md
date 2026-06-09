# MQSec_ConvertSDToNT5Format(ulong,_SECURITY_DESCRIPTOR *,ulong *,_SECURITY_DESCRIPTOR * *,enumDaclDefault,void *)

- ea: `0x180023310`
- end: `0x180023e06`
- name: `?MQSec_ConvertSDToNT5Format@@YAJKPEAU_SECURITY_DESCRIPTOR@@PEAKPEAPEAU1@W4enumDaclDefault@@PEAX@Z`
- size: `2806`
- prototype: `__int64 __fastcall(unsigned int, _WORD *, DWORD *, _QWORD *, int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x180017430`
- `0x180023310`
- `0x1800247e4`
- `0x180024dbc`

## import_xrefs

- `msvcrt!free` at `0x180023741`
- `msvcrt!free` at `0x18002374a`
- `msvcrt!free` at `0x180023811`
- `msvcrt!free` at `0x18002381a`
- `msvcrt!free` at `0x18002389e`
- `msvcrt!free` at `0x1800238a7`
- `msvcrt!free` at `0x180023938`
- `msvcrt!free` at `0x180023941`
- `msvcrt!free` at `0x1800239b3`
- `msvcrt!free` at `0x1800239bc`
- `msvcrt!free` at `0x180023a30`
- `msvcrt!free` at `0x180023a39`
- `msvcrt!free` at `0x180023afa`
- `msvcrt!free` at `0x180023b05`
- `msvcrt!free` at `0x180023b85`
- `msvcrt!free` at `0x180023b8f`
- `msvcrt!free` at `0x180023c13`
- `msvcrt!free` at `0x180023c1d`
- `msvcrt!free` at `0x180023c8d`
- `msvcrt!free` at `0x180023c97`
- `msvcrt!free` at `0x180023d0b`
- `msvcrt!free` at `0x180023d15`
- `msvcrt!free` at `0x180023d98`
- `msvcrt!free` at `0x180023da2`
- `msvcrt!free` at `0x180023dac`
- `msvcrt!free` at `0x180023dc7`
- `msvcrt!free` at `0x180023dd1`
- `msvcrt!free` at `0x180023ddb`
- `msvcrt!free` at `0x180023741`
- `msvcrt!free` at `0x18002374a`
- `msvcrt!free` at `0x180023811`
- `msvcrt!free` at `0x18002381a`
- `msvcrt!free` at `0x18002389e`
- `msvcrt!free` at `0x1800238a7`
- `msvcrt!free` at `0x180023938`
- `msvcrt!free` at `0x180023941`
- `msvcrt!free` at `0x1800239b3`
- `msvcrt!free` at `0x1800239bc`
- `msvcrt!free` at `0x180023a30`
- `msvcrt!free` at `0x180023a39`
- `msvcrt!free` at `0x180023afa`
- `msvcrt!free` at `0x180023b05`
- `msvcrt!free` at `0x180023b85`
- `msvcrt!free` at `0x180023b8f`
- `msvcrt!free` at `0x180023c13`
- `msvcrt!free` at `0x180023c1d`
- `msvcrt!free` at `0x180023c8d`
- `msvcrt!free` at `0x180023c97`
- `msvcrt!free` at `0x180023d0b`
- `msvcrt!free` at `0x180023d15`
- `msvcrt!free` at `0x180023d98`
- `msvcrt!free` at `0x180023da2`
- `msvcrt!free` at `0x180023dac`
- `msvcrt!free` at `0x180023dc7`
- `msvcrt!free` at `0x180023dd1`
- `msvcrt!free` at `0x180023ddb`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800238dc`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x18002395a`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180023bb6`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180023c34`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x1800238dc`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x18002395a`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180023bb6`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180023c34`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023cb1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023d3b`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023cb1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180023d3b`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180023845`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180023845`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002367a`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18002367a`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180023629`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180023629`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800235d7`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x1800235d7`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180023586`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180023586`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002341f`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002341f`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800233c2`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800233c2`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800236e8`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800236e8`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002351c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002351c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180023b2c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180023b2c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800239d7`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800239d7`
- `KERNEL32!GetLastError` at `0x180023429`
- `KERNEL32!GetLastError` at `0x180023542`
- `KERNEL32!GetLastError` at `0x180023590`
- `KERNEL32!GetLastError` at `0x1800235e1`
- `KERNEL32!GetLastError` at `0x180023633`
- `KERNEL32!GetLastError` at `0x180023684`
- `KERNEL32!GetLastError` at `0x1800236f4`
- `KERNEL32!GetLastError` at `0x18002384f`
- `KERNEL32!GetLastError` at `0x1800238ea`
- `KERNEL32!GetLastError` at `0x180023964`
- `KERNEL32!GetLastError` at `0x1800239e1`
- `KERNEL32!GetLastError` at `0x180023b36`
- `KERNEL32!GetLastError` at `0x180023bc4`
- `KERNEL32!GetLastError` at `0x180023c3e`
- `KERNEL32!GetLastError` at `0x180023cb7`
- `KERNEL32!GetLastError` at `0x180023d45`
- `KERNEL32!GetLastError` at `0x180023429`
- `KERNEL32!GetLastError` at `0x180023542`
- `KERNEL32!GetLastError` at `0x180023590`
- `KERNEL32!GetLastError` at `0x1800235e1`
- `KERNEL32!GetLastError` at `0x180023633`
- `KERNEL32!GetLastError` at `0x180023684`
- `KERNEL32!GetLastError` at `0x1800236f4`
- `KERNEL32!GetLastError` at `0x18002384f`
- `KERNEL32!GetLastError` at `0x1800238ea`
- `KERNEL32!GetLastError` at `0x180023964`
- `KERNEL32!GetLastError` at `0x1800239e1`
- `KERNEL32!GetLastError` at `0x180023b36`
- `KERNEL32!GetLastError` at `0x180023bc4`
- `KERNEL32!GetLastError` at `0x180023c3e`
- `KERNEL32!GetLastError` at `0x180023cb7`
- `KERNEL32!GetLastError` at `0x180023d45`

## pseudocode

```c
__int64 __fastcall MQSec_ConvertSDToNT5Format(unsigned int a1, _WORD *a2, DWORD *a3, _QWORD *a4, int a5, __int64 a6)
{
  unsigned __int64 v8; // r12
  struct _ACL *v9; // rsi
  int LastError; // ebx
  unsigned int v11; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  WORD v15; // ax
  __int64 v16; // rcx
  DWORD v17; // eax
  PACL v18; // r15
  int v19; // r14d
  WINBOOL v20; // edx
  int v21; // esi
  unsigned int v22; // eax
  WINBOOL v23; // edx
  unsigned int v24; // eax
  void *v25; // rbx
  DWORD v26; // r14d
  int v27; // [rsp+60h] [rbp-69h] BYREF
  WINBOOL bSaclPresent; // [rsp+68h] [rbp-61h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+6Ch] [rbp-5Dh] BYREF
  DWORD dwBufferLength; // [rsp+70h] [rbp-59h] BYREF
  void *v31; // [rsp+78h] [rbp-51h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+80h] [rbp-49h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+84h] [rbp-45h] BYREF
  PACL pSacl; // [rsp+88h] [rbp-41h] BYREF
  DWORD dwRevision; // [rsp+90h] [rbp-39h] BYREF
  void *Block; // [rsp+98h] [rbp-31h] BYREF
  PACL pDacl; // [rsp+A0h] [rbp-29h] BYREF
  PSID pOwner; // [rsp+A8h] [rbp-21h] BYREF
  PSID pGroup; // [rsp+B0h] [rbp-19h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v41; // [rsp+D8h] [rbp+Fh]
  WORD pControl; // [rsp+128h] [rbp+5Fh] BYREF
  DWORD *v43; // [rsp+130h] [rbp+67h]

  v43 = a3;
  v8 = a1;
  v9 = 0;
  if ( !a2 )
  {
    LOWORD(v27) = 130;
    LastError = -1072821143;
    LODWORD(v31) = -1072821143;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v11 = mqwcslen(L"acssctrl/secd4to5");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v11 + 1),
        L"acssctrl/secd4to5",
        2,
        &v27,
        4,
        &v31,
        0,
        0);
    }
    return (unsigned int)LastError;
  }
  if ( !IsValidSecurityDescriptor(a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 37, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids);
    return 3222146051LL;
  }
  dwRevision = 0;
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v14 = 38;
LABEL_14:
      WPP_SF_d(v13[32], v14, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, (unsigned int)LastError);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v15 = pControl;
  if ( (pControl & 0x8000u) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 39, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids);
    return 3222146074LL;
  }
  if ( a5 == 1 )
  {
    pControl &= ~8u;
    a2[1] = v15 & 0xFFF7;
  }
  if ( (unsigned int)v8 > 0x36 )
    return 1074662402;
  v16 = 0x4000000000006ELL;
  if ( !_bittest64(&v16, v8) )
    return 1074662402;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v41 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v17 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 40, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, v17);
    }
    return 3222146050LL;
  }
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v14 = 41;
      goto LABEL_14;
    }
LABEL_15:
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  if ( pOwner && !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v14 = 42;
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  pGroup = 0;
  bGroupDefaulted = 0;
  if ( !GetSecurityDescriptorGroup(a2, &pGroup, &bGroupDefaulted) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v14 = 43;
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  if ( pGroup && !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bGroupDefaulted) )
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v14 = 44;
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  LODWORD(v31) = 0;
  pSacl = 0;
  v18 = 0;
  pDacl = 0;
  Block = 0;
  v19 = 0;
  v27 = 0;
  if ( !GetSecurityDescriptorSacl(a2, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        45,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    free(0);
    free(0);
    return (unsigned int)LastError;
  }
  v20 = bSaclPresent;
  if ( bSaclPresent )
  {
    if ( pSacl && pSacl->AceCount )
    {
      v21 = ConvertSaclToNT5Format(v8, pSacl, (DWORD *)&v31, (PACL *)&Block, &v27);
      if ( v21 < 0 )
      {
        LOWORD(v27) = 180;
        LODWORD(v31) = v21;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v22 = mqwcslen(L"acssctrl/secd4to5");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v22 + 1),
            L"acssctrl/secd4to5",
            2,
            &v27,
            4,
            &v31,
            0,
            0);
        }
        free(Block);
        free(0);
        return (unsigned int)v21;
      }
      v20 = bSaclPresent;
      v9 = (struct _ACL *)Block;
      v19 = v27;
    }
    else
    {
      v20 = 0;
      bSaclPresent = 0;
    }
  }
  if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, v20, v9, bSaclDefaulted) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        46,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_94:
    free(v9);
    free(0);
    return (unsigned int)LastError;
  }
  if ( v19 || (pControl & 0x2000) != 0 )
  {
    if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x2A00u, pControl & 0x2A00) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          47,
          WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
          (unsigned int)LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_94;
    }
  }
  else if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x2200u, 0x200u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        48,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_94;
  }
  if ( !GetSecurityDescriptorDacl(a2, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        49,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_94;
  }
  v27 = v19;
  v23 = bSaclPresent;
  if ( bSaclPresent )
  {
    LastError = ConvertDaclToNT5Format((unsigned int)v8, a6, pSacl, (DWORD *)&v31, &pDacl, &v27);
    if ( LastError < 0 )
    {
      LOWORD(v27) = 190;
      LODWORD(v31) = LastError;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v24 = mqwcslen(L"acssctrl/secd4to5");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v24 + 1),
          L"acssctrl/secd4to5",
          2,
          &v27,
          4,
          &v31,
          0,
          0);
      }
      free(v9);
      free(pDacl);
      return (unsigned int)LastError;
    }
    v23 = bSaclPresent;
    v18 = pDacl;
    v19 = v27;
  }
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v23, v18, bSaclDefaulted) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        50,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_129:
    free(v9);
    free(v18);
    return (unsigned int)LastError;
  }
  if ( v19 )
  {
    if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1500u, pControl & 0x1500) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          51,
          WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
          (unsigned int)LastError);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_129;
    }
  }
  else if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1100u, 0x100u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        52,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_129;
  }
  dwBufferLength = 0;
  MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        53,
        WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_129;
  }
  v25 = MmAllocate(dwBufferLength);
  v31 = v25;
  if ( MakeSelfRelativeSD(pSecurityDescriptor, v25, &dwBufferLength) )
  {
    *a4 = v25;
    *v43 = dwBufferLength;
    free(0);
    free(v9);
    free(v18);
    return 0;
  }
  else
  {
    v26 = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 54, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, v26);
    if ( (int)v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    free(v25);
    free(v9);
    free(v18);
    return v26;
  }
}

```

## disassembly

```asm
0x180023310  mov     [rsp-8+arg_0], rbx
0x180023315  mov     [rsp-8+arg_10], r8
0x18002331a  push    rbp
0x18002331b  push    rsi
0x18002331c  push    rdi
0x18002331d  push    r12
0x18002331f  push    r13
0x180023321  push    r14
0x180023323  push    r15
0x180023325  lea     rbp, [rsp-17h]
0x18002332a  sub     rsp, 0E0h
0x180023331  mov     r13, r9
0x180023334  mov     rbx, rdx
0x180023337  mov     r12d, ecx
0x18002333a  xor     esi, esi
0x18002333c  test    rdx, rdx
0x18002333f  jnz     short loc_1800233BF
0x180023341  mov     eax, 82h
0x180023346  mov     word ptr [rbp+47h+var_B0], ax
0x18002334a  mov     ebx, 0C00E0C69h
0x18002334f  mov     dword ptr [rbp+47h+var_98], ebx
0x180023352  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180023359  jz      short loc_1800233B8
0x18002335b  lea     r14, aAcssctrlSecd4t; "acssctrl/secd4to5"
0x180023362  mov     rcx, r14; wchar_t *
0x180023365  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002336a  lea     edi, [rsi+1]
0x18002336d  lea     r9d, [rdi+rax]
0x180023371  add     r9, r9
0x180023374  mov     [rsp+110h+var_C0], rsi
0x180023379  mov     [rsp+110h+var_C8], rsi
0x18002337e  lea     rax, [rbp+47h+var_98]
0x180023382  mov     [rsp+110h+var_D0], rax
0x180023387  mov     [rsp+110h+var_D8], 4
0x180023390  lea     rcx, [rbp+47h+var_B0]
0x180023394  mov     [rsp+110h+var_E0], rcx
0x180023399  mov     [rsp+110h+var_E8], 2
0x1800233a2  mov     [rsp+110h+var_F0], r14
0x1800233a7  mov     r8d, edi
0x1800233aa  mov     edx, edi
0x1800233ac  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800233b3  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800233b8  mov     eax, ebx
0x1800233ba  jmp     loc_180023DEB
0x1800233bf  mov     rcx, rbx; pSecurityDescriptor
0x1800233c2  call    cs:__imp_IsValidSecurityDescriptor
0x1800233c8  test    eax, eax
0x1800233ca  jnz     short loc_18002340D
0x1800233cc  lea     rax, WPP_GLOBAL_Control
0x1800233d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233da  cmp     rcx, rax
0x1800233dd  jz      short loc_180023403
0x1800233df  mov     edi, 1
0x1800233e4  test    [rcx+10Ch], dil
0x1800233eb  jz      short loc_180023403
0x1800233ed  lea     edx, [rdi+24h]
0x1800233f0  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x1800233f7  mov     rcx, [rcx+100h]
0x1800233fe  call    WPP_SF_
0x180023403  mov     eax, 0C00E0C03h
0x180023408  jmp     loc_180023DEB
0x18002340d  mov     [rbp+47h+dwRevision], esi
0x180023410  mov     [rbp+47h+pControl], si
0x180023414  lea     r8, [rbp+47h+dwRevision]; lpdwRevision
0x180023418  lea     rdx, [rbp+47h+pControl]; pControl
0x18002341c  mov     rcx, rbx; pSecurityDescriptor
0x18002341f  call    cs:__imp_GetSecurityDescriptorControl
0x180023425  test    eax, eax
0x180023427  jnz     short loc_180023481
0x180023429  call    cs:__imp_GetLastError
0x18002342f  mov     ebx, eax
0x180023431  lea     rax, WPP_GLOBAL_Control
0x180023438  mov     rcx, cs:WPP_GLOBAL_Control
0x18002343f  cmp     rcx, rax
0x180023442  jz      short loc_18002346B
0x180023444  mov     edi, 1
0x180023449  test    [rcx+10Ch], dil
0x180023450  jz      short loc_18002346B
0x180023452  lea     edx, [rdi+25h]
0x180023455  mov     r9d, ebx
0x180023458  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x18002345f  mov     rcx, [rcx+100h]
0x180023466  call    WPP_SF_d
0x18002346b  test    ebx, ebx
0x18002346d  jle     loc_1800233B8
0x180023473  movzx   ebx, bx
0x180023476  or      ebx, 80070000h
0x18002347c  jmp     loc_1800233B8
0x180023481  movzx   eax, [rbp+47h+pControl]
0x180023485  bt      ax, 0Fh
0x18002348a  jb      short loc_1800234CD
0x18002348c  lea     rax, WPP_GLOBAL_Control
0x180023493  mov     rcx, cs:WPP_GLOBAL_Control
0x18002349a  cmp     rcx, rax
0x18002349d  jz      short loc_1800234C3
0x18002349f  mov     edi, 1
0x1800234a4  test    [rcx+10Ch], dil
0x1800234ab  jz      short loc_1800234C3
0x1800234ad  lea     edx, [rdi+26h]
0x1800234b0  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x1800234b7  mov     rcx, [rcx+100h]
0x1800234be  call    WPP_SF_
0x1800234c3  mov     eax, 0C00E0C1Ah
0x1800234c8  jmp     loc_180023DEB
0x1800234cd  mov     edi, 1
0x1800234d2  cmp     [rbp+47h+arg_20], edi
0x1800234d5  jnz     short loc_1800234E7
0x1800234d7  mov     ecx, 0FFF7h
0x1800234dc  and     ax, cx
0x1800234df  mov     [rbp+47h+pControl], ax
0x1800234e3  mov     [rbx+2], ax
0x1800234e7  cmp     r12d, 36h ; '6'
0x1800234eb  ja      loc_180023DE6
0x1800234f1  mov     rcx, 4000000000006Eh
0x1800234fb  bt      rcx, r12
0x1800234ff  jnb     loc_180023DE6
0x180023505  xorps   xmm0, xmm0
0x180023508  xor     eax, eax
0x18002350a  movups  [rbp+47h+pSecurityDescriptor], xmm0
0x18002350e  movups  [rbp+47h+var_48], xmm0
0x180023512  mov     [rbp+47h+var_38], rax
0x180023516  mov     edx, edi; dwRevision
0x180023518  lea     rcx, [rbp+47h+pSecurityDescriptor]; pSecurityDescriptor
0x18002351c  call    cs:__imp_InitializeSecurityDescriptor
0x180023522  test    eax, eax
0x180023524  jnz     short loc_180023574
0x180023526  lea     rax, WPP_GLOBAL_Control
0x18002352d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023534  cmp     rcx, rax
0x180023537  jz      short loc_18002356A
0x180023539  test    [rcx+10Ch], dil
0x180023540  jz      short loc_18002356A
0x180023542  call    cs:__imp_GetLastError
0x180023548  mov     edx, 28h ; '('
0x18002354d  mov     r9d, eax
0x180023550  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180023557  mov     rcx, cs:WPP_GLOBAL_Control
0x18002355e  mov     rcx, [rcx+100h]
0x180023565  call    WPP_SF_d
0x18002356a  mov     eax, 0C00E0C02h
0x18002356f  jmp     loc_180023DEB
0x180023574  mov     [rbp+47h+pOwner], rsi
0x180023578  mov     [rbp+47h+bOwnerDefaulted], esi
0x18002357b  lea     r8, [rbp+47h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18002357f  lea     rdx, [rbp+47h+pOwner]; pOwner
0x180023583  mov     rcx, rbx; pSecurityDescriptor
0x180023586  call    cs:__imp_GetSecurityDescriptorOwner
0x18002358c  test    eax, eax
0x18002358e  jnz     short loc_1800235C6
0x180023590  call    cs:__imp_GetLastError
0x180023596  mov     ebx, eax
0x180023598  lea     rax, WPP_GLOBAL_Control
0x18002359f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235a6  cmp     rcx, rax
0x1800235a9  jz      loc_18002346B
0x1800235af  test    [rcx+10Ch], dil
0x1800235b6  jz      loc_18002346B
0x1800235bc  mov     edx, 29h ; ')'
0x1800235c1  jmp     loc_180023455
0x1800235c6  mov     rdx, [rbp+47h+pOwner]; pOwner
0x1800235ca  test    rdx, rdx
0x1800235cd  jz      short loc_180023617
0x1800235cf  mov     r8d, [rbp+47h+bOwnerDefaulted]; bOwnerDefaulted
0x1800235d3  lea     rcx, [rbp+47h+pSecurityDescriptor]; pSecurityDescriptor
0x1800235d7  call    cs:__imp_SetSecurityDescriptorOwner
0x1800235dd  test    eax, eax
0x1800235df  jnz     short loc_180023617
0x1800235e1  call    cs:__imp_GetLastError
0x1800235e7  mov     ebx, eax
0x1800235e9  lea     rax, WPP_GLOBAL_Control
0x1800235f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235f7  cmp     rcx, rax
0x1800235fa  jz      loc_18002346B
0x180023600  test    [rcx+10Ch], dil
0x180023607  jz      loc_18002346B
0x18002360d  mov     edx, 2Ah ; '*'
0x180023612  jmp     loc_180023455
0x180023617  mov     [rbp+47h+pGroup], rsi
0x18002361b  mov     [rbp+47h+bGroupDefaulted], esi
0x18002361e  lea     r8, [rbp+47h+bGroupDefaulted]; lpbGroupDefaulted
0x180023622  lea     rdx, [rbp+47h+pGroup]; pGroup
0x180023626  mov     rcx, rbx; pSecurityDescriptor
0x180023629  call    cs:__imp_GetSecurityDescriptorGroup
0x18002362f  test    eax, eax
0x180023631  jnz     short loc_180023669
0x180023633  call    cs:__imp_GetLastError
0x180023639  mov     ebx, eax
0x18002363b  lea     rax, WPP_GLOBAL_Control
0x180023642  mov     rcx, cs:WPP_GLOBAL_Control
0x180023649  cmp     rcx, rax
0x18002364c  jz      loc_18002346B
0x180023652  test    [rcx+10Ch], dil
0x180023659  jz      loc_18002346B
0x18002365f  mov     edx, 2Bh ; '+'
0x180023664  jmp     loc_180023455
0x180023669  mov     rdx, [rbp+47h+pGroup]; pGroup
0x18002366d  test    rdx, rdx
0x180023670  jz      short loc_1800236BA
0x180023672  mov     r8d, [rbp+47h+bGroupDefaulted]; bGroupDefaulted
0x180023676  lea     rcx, [rbp+47h+pSecurityDescriptor]; pSecurityDescriptor
0x18002367a  call    cs:__imp_SetSecurityDescriptorGroup
0x180023680  test    eax, eax
0x180023682  jnz     short loc_1800236BA
0x180023684  call    cs:__imp_GetLastError
0x18002368a  mov     ebx, eax
0x18002368c  lea     rax, WPP_GLOBAL_Control
0x180023693  mov     rcx, cs:WPP_GLOBAL_Control
0x18002369a  cmp     rcx, rax
0x18002369d  jz      loc_18002346B
0x1800236a3  test    [rcx+10Ch], dil
0x1800236aa  jz      loc_18002346B
0x1800236b0  mov     edx, 2Ch ; ','
0x1800236b5  jmp     loc_180023455
0x1800236ba  mov     [rbp+47h+bSaclPresent], esi
0x1800236bd  mov     [rbp+47h+bSaclDefaulted], esi
0x1800236c0  mov     dword ptr [rbp+47h+var_98], esi
0x1800236c3  mov     [rbp+47h+pSacl], rsi
0x1800236c7  mov     r15, rsi
0x1800236ca  mov     [rbp+47h+pDacl], rsi
0x1800236ce  mov     [rbp+47h+Block], rsi
0x1800236d2  xor     r14d, r14d
0x1800236d5  mov     [rbp+47h+var_B0], r14d
0x1800236d9  lea     r9, [rbp+47h+bSaclDefaulted]; lpbSaclDefaulted
0x1800236dd  lea     r8, [rbp+47h+pSacl]; pSacl
0x1800236e1  lea     rdx, [rbp+47h+bSaclPresent]; lpbSaclPresent
0x1800236e5  mov     rcx, rbx; pSecurityDescriptor
0x1800236e8  call    cs:__imp_GetSecurityDescriptorSacl
0x1800236ee  xor     ecx, ecx
0x1800236f0  test    eax, eax
0x1800236f2  jnz     short loc_180023756
0x1800236f4  call    cs:__imp_GetLastError
0x1800236fa  mov     ebx, eax
0x1800236fc  lea     rax, WPP_GLOBAL_Control
0x180023703  mov     rcx, cs:WPP_GLOBAL_Control
0x18002370a  cmp     rcx, rax
0x18002370d  jz      short loc_180023732
0x18002370f  test    [rcx+10Ch], dil
0x180023716  jz      short loc_180023732
0x180023718  lea     edx, [r14+2Dh]
0x18002371c  mov     r9d, ebx
0x18002371f  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x180023726  mov     rcx, [rcx+100h]
0x18002372d  call    WPP_SF_d
0x180023732  test    ebx, ebx
0x180023734  jle     short loc_18002373F
0x180023736  movzx   ebx, bx
0x180023739  or      ebx, 80070000h
0x18002373f  xor     ecx, ecx; Block
0x180023741  call    cs:__imp_free
0x180023747  nop
0x180023748  xor     ecx, ecx; Block
0x18002374a  call    cs:__imp_free
0x180023750  nop
0x180023751  jmp     loc_1800233B8
0x180023756  mov     edx, [rbp+47h+bSaclPresent]
0x180023759  test    edx, edx
0x18002375b  jz      loc_18002383A
0x180023761  mov     rdx, [rbp+47h+pSacl]
0x180023765  test    rdx, rdx
0x180023768  jz      loc_180023835
0x18002376e  cmp     [rdx+4], cx
0x180023772  jz      loc_180023835
0x180023778  lea     rax, [rbp+47h+var_B0]
0x18002377c  mov     [rsp+110h+var_F0], rax
0x180023781  lea     r9, [rbp+47h+Block]
0x180023785  lea     r8, [rbp+47h+var_98]
0x180023789  mov     ecx, r12d
0x18002378c  call    _ConvertSaclToNT5Format
0x180023791  mov     esi, eax
0x180023793  test    eax, eax
0x180023795  jns     loc_180023828
0x18002379b  mov     eax, 0B4h
0x1800237a0  mov     word ptr [rbp+47h+var_B0], ax
0x1800237a4  mov     dword ptr [rbp+47h+var_98], esi
0x1800237a7  xor     ebx, ebx
0x1800237a9  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800237b0  jz      short loc_18002380D
0x1800237b2  lea     r14, aAcssctrlSecd4t; "acssctrl/secd4to5"
0x1800237b9  mov     rcx, r14; wchar_t *
0x1800237bc  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800237c1  lea     r9d, [rdi+rax]
0x1800237c5  add     r9, r9
0x1800237c8  mov     [rsp+110h+var_C0], rbx
0x1800237cd  mov     [rsp+110h+var_C8], rbx
0x1800237d2  lea     rax, [rbp+47h+var_98]
0x1800237d6  mov     [rsp+110h+var_D0], rax
0x1800237db  mov     [rsp+110h+var_D8], 4
0x1800237e4  lea     rax, [rbp+47h+var_B0]
0x1800237e8  mov     [rsp+110h+var_E0], rax
0x1800237ed  mov     [rsp+110h+var_E8], 2
0x1800237f6  mov     [rsp+110h+var_F0], r14
0x1800237fb  mov     r8d, edi
0x1800237fe  mov     edx, edi
0x180023800  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180023807  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18002380c  nop
0x18002380d  mov     rcx, [rbp+47h+Block]; Block
0x180023811  call    cs:__imp_free
0x180023817  nop
0x180023818  xor     ecx, ecx; Block
  ... truncated ...
```
