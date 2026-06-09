# MQSec_ConvertSDToNT4Format(ulong,_SECURITY_DESCRIPTOR *,ulong *,_SECURITY_DESCRIPTOR * *,ulong)

- ea: `0x180021d10`
- end: `0x18002269c`
- name: `?MQSec_ConvertSDToNT4Format@@YAJKPEAU_SECURITY_DESCRIPTOR@@PEAKPEAPEAU1@K@Z`
- size: `2444`
- prototype: `__int64 __fastcall(unsigned int, struct _SECURITY_DESCRIPTOR *, unsigned int *, struct _SECURITY_DESCRIPTOR **, char)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x180017430`
- `0x180021d10`
- `0x1800226a4`
- `0x1800227e4`
- `0x180022d08`

## import_xrefs

- `msvcrt!free` at `0x180022145`
- `msvcrt!free` at `0x180022209`
- `msvcrt!free` at `0x18002229a`
- `msvcrt!free` at `0x180022329`
- `msvcrt!free` at `0x180022333`
- `msvcrt!free` at `0x1800223f7`
- `msvcrt!free` at `0x180022401`
- `msvcrt!free` at `0x180022482`
- `msvcrt!free` at `0x18002248c`
- `msvcrt!free` at `0x180022509`
- `msvcrt!free` at `0x180022513`
- `msvcrt!free` at `0x18002259d`
- `msvcrt!free` at `0x1800225a7`
- `msvcrt!free` at `0x1800225b1`
- `msvcrt!free` at `0x1800225db`
- `msvcrt!free` at `0x1800225e5`
- `msvcrt!free` at `0x1800225ef`
- `msvcrt!free` at `0x180022145`
- `msvcrt!free` at `0x180022209`
- `msvcrt!free` at `0x18002229a`
- `msvcrt!free` at `0x180022329`
- `msvcrt!free` at `0x180022333`
- `msvcrt!free` at `0x1800223f7`
- `msvcrt!free` at `0x180022401`
- `msvcrt!free` at `0x180022482`
- `msvcrt!free` at `0x18002248c`
- `msvcrt!free` at `0x180022509`
- `msvcrt!free` at `0x180022513`
- `msvcrt!free` at `0x18002259d`
- `msvcrt!free` at `0x1800225a7`
- `msvcrt!free` at `0x1800225b1`
- `msvcrt!free` at `0x1800225db`
- `msvcrt!free` at `0x1800225e5`
- `msvcrt!free` at `0x1800225ef`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800224af`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180022540`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800224af`
- `ADVAPI32!MakeSelfRelativeSD` at `0x180022540`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180022241`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180022241`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180022068`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x180022068`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180022013`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180022013`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180021fa8`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180021fa8`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180021f53`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180021f53`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180021dc3`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180021dc3`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180021d4c`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180021d4c`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800220ed`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800220ed`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180021ed2`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180021ed2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022429`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180022429`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800222d1`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800222d1`
- `KERNEL32!GetLastError` at `0x180021d56`
- `KERNEL32!GetLastError` at `0x180021dcd`
- `KERNEL32!GetLastError` at `0x180021ef8`
- `KERNEL32!GetLastError` at `0x180021f5d`
- `KERNEL32!GetLastError` at `0x180021fb2`
- `KERNEL32!GetLastError` at `0x18002201d`
- `KERNEL32!GetLastError` at `0x180022072`
- `KERNEL32!GetLastError` at `0x1800220f7`
- `KERNEL32!GetLastError` at `0x18002224b`
- `KERNEL32!GetLastError` at `0x1800222db`
- `KERNEL32!GetLastError` at `0x180022433`
- `KERNEL32!GetLastError` at `0x1800224b5`
- `KERNEL32!GetLastError` at `0x18002254a`
- `KERNEL32!GetLastError` at `0x180021d56`
- `KERNEL32!GetLastError` at `0x180021dcd`
- `KERNEL32!GetLastError` at `0x180021ef8`
- `KERNEL32!GetLastError` at `0x180021f5d`
- `KERNEL32!GetLastError` at `0x180021fb2`
- `KERNEL32!GetLastError` at `0x18002201d`
- `KERNEL32!GetLastError` at `0x180022072`
- `KERNEL32!GetLastError` at `0x1800220f7`
- `KERNEL32!GetLastError` at `0x18002224b`
- `KERNEL32!GetLastError` at `0x1800222db`
- `KERNEL32!GetLastError` at `0x180022433`
- `KERNEL32!GetLastError` at `0x1800224b5`
- `KERNEL32!GetLastError` at `0x18002254a`

## pseudocode

```c
__int64 __fastcall MQSec_ConvertSDToNT4Format(
        unsigned int a1,
        struct _SECURITY_DESCRIPTOR *a2,
        unsigned int *a3,
        struct _SECURITY_DESCRIPTOR **a4,
        char a5)
{
  struct _ACL *v7; // r15
  DWORD LastError; // eax
  signed int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax
  struct _ACL *v14; // rsi
  DWORD v15; // eax
  WINBOOL v16; // edx
  int v17; // esi
  unsigned int v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  WINBOOL v21; // edx
  unsigned int v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  struct _SECURITY_DESCRIPTOR *v25; // rbx
  DWORD v26; // eax
  signed int v27; // r14d
  unsigned int v28; // eax
  WINBOOL bOwnerDefaulted; // [rsp+60h] [rbp-A8h] BYREF
  WINBOOL bSaclPresent; // [rsp+68h] [rbp-A0h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD dwBufferLength; // [rsp+70h] [rbp-98h] BYREF
  struct _SECURITY_DESCRIPTOR *v33; // [rsp+78h] [rbp-90h] BYREF
  PACL pSacl; // [rsp+80h] [rbp-88h] BYREF
  DWORD dwRevision; // [rsp+88h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-78h] BYREF
  void *v37; // [rsp+98h] [rbp-70h] BYREF
  PSID pOwner; // [rsp+A0h] [rbp-68h] BYREF
  PSID pGroup; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-30h]
  WORD pControl; // [rsp+118h] [rbp+10h] BYREF
  unsigned int *v43; // [rsp+120h] [rbp+18h]
  struct _SECURITY_DESCRIPTOR **v44; // [rsp+128h] [rbp+20h]

  v44 = a4;
  v43 = a3;
  v7 = 0;
  if ( !a2 || !a4 )
  {
    LOWORD(bOwnerDefaulted) = 80;
    v10 = -1072821143;
    LODWORD(v33) = -1072821143;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v28 = mqwcslen(L"acssctrl/secd5to4");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v28 + 1),
        L"acssctrl/secd5to4",
        2,
        &bOwnerDefaulted,
        4,
        &v33,
        0,
        0);
    }
    return (unsigned int)v10;
  }
  *a4 = 0;
  if ( !IsValidSecurityDescriptor(a2) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 25, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, LastError);
    return 3222146051LL;
  }
  dwRevision = 0;
  pControl = 0;
  if ( !GetSecurityDescriptorControl(a2, &pControl, &dwRevision) )
  {
    v10 = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v12 = 26;
LABEL_12:
      WPP_SF_d(v11[32], v12, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, (unsigned int)v10);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  if ( (pControl & 0x8000u) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 27, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids);
    return 3222146074LL;
  }
  if ( (unsigned int)AlreadyNT4Format(a2) )
    return 1074662402;
  if ( a1 == 4 || !a1 || a1 >= 7 )
    return 1074662402;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v41 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v13);
    }
    return 3222146050LL;
  }
  pOwner = 0;
  if ( (a5 & 1) != 0 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted) )
    {
      v10 = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v12 = 30;
        goto LABEL_12;
      }
LABEL_13:
      if ( v10 > 0 )
        return (unsigned __int16)v10 | 0x80070000;
      return (unsigned int)v10;
    }
    if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted) )
    {
      v10 = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v12 = 31;
        goto LABEL_12;
      }
      goto LABEL_13;
    }
  }
  pGroup = 0;
  if ( (a5 & 2) != 0 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorGroup(a2, &pGroup, &bOwnerDefaulted) )
    {
      v10 = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v12 = 32;
        goto LABEL_12;
      }
      goto LABEL_13;
    }
    if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bOwnerDefaulted) )
    {
      v10 = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v12 = 33;
        goto LABEL_12;
      }
      goto LABEL_13;
    }
  }
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pSacl = 0;
  bOwnerDefaulted = 0;
  v14 = 0;
  Block = 0;
  if ( (a5 & 8) != 0 )
  {
    if ( !GetSecurityDescriptorSacl(a2, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      v15 = GetLastError();
      v10 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 34, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v15);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      free(0);
      return (unsigned int)v10;
    }
    v16 = bSaclPresent;
    if ( bSaclPresent )
    {
      if ( !pSacl )
        goto LABEL_64;
      v17 = ConvertSaclToNT4Format(a1, pSacl, &bOwnerDefaulted, &Block);
      if ( v17 < 0 )
      {
        LOWORD(bOwnerDefaulted) = 140;
        LODWORD(v33) = v17;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v18 = mqwcslen(L"acssctrl/secd5to4");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v18 + 1),
            L"acssctrl/secd5to4",
            2,
            &bOwnerDefaulted,
            4,
            &v33,
            0,
            0);
        }
        free(Block);
        return (unsigned int)v17;
      }
      v14 = (struct _ACL *)Block;
      if ( Block )
      {
        v16 = bSaclPresent;
      }
      else
      {
LABEL_64:
        v16 = 0;
        bSaclPresent = 0;
      }
    }
    if ( !SetSecurityDescriptorSacl(pSecurityDescriptor, v16, v14, bSaclDefaulted) )
    {
      v19 = GetLastError();
      v10 = v19;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 35, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v19);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      free(v14);
      return (unsigned int)v10;
    }
  }
  v37 = 0;
  if ( (a5 & 4) != 0 )
  {
    if ( !GetSecurityDescriptorDacl(a2, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      v20 = GetLastError();
      v10 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 36, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v20);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      free(0);
      free(v14);
      return (unsigned int)v10;
    }
    v21 = bSaclPresent;
    if ( bSaclPresent )
    {
      v10 = ConvertDaclToNT4Format(a1, pSacl, &bOwnerDefaulted, &v37);
      if ( v10 < 0 )
      {
        LOWORD(bOwnerDefaulted) = 150;
        LODWORD(v33) = v10;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v22 = mqwcslen(L"acssctrl/secd5to4");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v22 + 1),
            L"acssctrl/secd5to4",
            2,
            &bOwnerDefaulted,
            4,
            &v33,
            0,
            0);
        }
        free(v37);
        free(v14);
        return (unsigned int)v10;
      }
      v21 = bSaclPresent;
      v7 = (struct _ACL *)v37;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v21, v7, bSaclDefaulted) )
    {
      v23 = GetLastError();
      v10 = v23;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 37, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v23);
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
LABEL_92:
      free(v7);
      free(v14);
      return (unsigned int)v10;
    }
  }
  dwBufferLength = 0;
  MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength);
  v24 = GetLastError();
  v10 = v24;
  if ( v24 != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v24);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_92;
  }
  v25 = (struct _SECURITY_DESCRIPTOR *)MmAllocate(dwBufferLength);
  v33 = v25;
  if ( MakeSelfRelativeSD(pSecurityDescriptor, v25, &dwBufferLength) )
  {
    *v43 = dwBufferLength;
    *v44 = v25;
    free(0);
    free(v7);
    free(v14);
    return 0;
  }
  else
  {
    v26 = GetLastError();
    v27 = v26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 39, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids, v26);
    if ( v27 > 0 )
      v27 = (unsigned __int16)v27 | 0x80070000;
    free(v25);
    free(v7);
    free(v14);
    return (unsigned int)v27;
  }
}

```

## disassembly

```asm
0x180021d10  mov     [rsp+arg_18], r9
0x180021d15  mov     [rsp+arg_10], r8
0x180021d1a  push    rbx
0x180021d1b  push    rsi
0x180021d1c  push    rdi
0x180021d1d  push    r14
0x180021d1f  push    r15
0x180021d21  sub     rsp, 0E0h
0x180021d28  mov     rax, r9
0x180021d2b  mov     rbx, rdx
0x180021d2e  mov     r14d, ecx
0x180021d31  xor     r15d, r15d
0x180021d34  test    rdx, rdx
0x180021d37  jz      loc_18002260D
0x180021d3d  test    rax, rax
0x180021d40  jz      loc_18002260D
0x180021d46  mov     [r9], r15
0x180021d49  mov     rcx, rdx; pSecurityDescriptor
0x180021d4c  call    cs:__imp_IsValidSecurityDescriptor
0x180021d52  test    eax, eax
0x180021d54  jnz     short loc_180021D9F
0x180021d56  call    cs:__imp_GetLastError
0x180021d5c  lea     rdx, WPP_GLOBAL_Control
0x180021d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d6a  cmp     rcx, rdx
0x180021d6d  jz      short loc_180021D95
0x180021d6f  lea     edi, [r15+1]
0x180021d73  test    [rcx+10Ch], dil
0x180021d7a  jz      short loc_180021D95
0x180021d7c  lea     edx, [rdi+18h]
0x180021d7f  mov     r9d, eax
0x180021d82  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180021d89  mov     rcx, [rcx+100h]
0x180021d90  call    WPP_SF_d
0x180021d95  mov     eax, 0C00E0C03h
0x180021d9a  jmp     loc_18002268C
0x180021d9f  mov     [rsp+108h+dwRevision], r15d
0x180021da7  mov     [rsp+108h+pControl], r15w
0x180021db0  lea     r8, [rsp+108h+dwRevision]; lpdwRevision
0x180021db8  lea     rdx, [rsp+108h+pControl]; pControl
0x180021dc0  mov     rcx, rbx; pSecurityDescriptor
0x180021dc3  call    cs:__imp_GetSecurityDescriptorControl
0x180021dc9  test    eax, eax
0x180021dcb  jnz     short loc_180021E25
0x180021dcd  call    cs:__imp_GetLastError
0x180021dd3  mov     ebx, eax
0x180021dd5  lea     rdx, WPP_GLOBAL_Control
0x180021ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021de3  cmp     rcx, rdx
0x180021de6  jz      short loc_180021E0F
0x180021de8  mov     edi, 1
0x180021ded  test    [rcx+10Ch], dil
0x180021df4  jz      short loc_180021E0F
0x180021df6  lea     edx, [rdi+19h]
0x180021df9  mov     r9d, ebx
0x180021dfc  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180021e03  mov     rcx, [rcx+100h]
0x180021e0a  call    WPP_SF_d
0x180021e0f  test    ebx, ebx
0x180021e11  jle     loc_18002268A
0x180021e17  movzx   ebx, bx
0x180021e1a  or      ebx, 80070000h
0x180021e20  jmp     loc_18002268A
0x180021e25  mov     eax, 8000h
0x180021e2a  test    [rsp+108h+pControl], ax
0x180021e32  jnz     short loc_180021E75
0x180021e34  lea     rdx, WPP_GLOBAL_Control
0x180021e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e42  cmp     rcx, rdx
0x180021e45  jz      short loc_180021E6B
0x180021e47  mov     edi, 1
0x180021e4c  test    [rcx+10Ch], dil
0x180021e53  jz      short loc_180021E6B
0x180021e55  lea     edx, [rdi+1Ah]
0x180021e58  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180021e5f  mov     rcx, [rcx+100h]
0x180021e66  call    WPP_SF_
0x180021e6b  mov     eax, 0C00E0C1Ah
0x180021e70  jmp     loc_18002268C
0x180021e75  mov     rcx, rbx; pSecurityDescriptor
0x180021e78  call    _AlreadyNT4Format
0x180021e7d  test    eax, eax
0x180021e7f  jz      short loc_180021E8B
0x180021e81  mov     eax, 400E0C02h
0x180021e86  jmp     loc_18002268C
0x180021e8b  cmp     r14d, 4
0x180021e8f  jz      loc_1800225FD
0x180021e95  test    r14d, r14d
0x180021e98  jz      loc_1800225FD
0x180021e9e  cmp     r14d, 7
0x180021ea2  jnb     loc_1800225FD
0x180021ea8  xorps   xmm0, xmm0
0x180021eab  xor     eax, eax
0x180021ead  movups  [rsp+108h+pSecurityDescriptor], xmm0
0x180021eb5  movups  [rsp+108h+var_40], xmm0
0x180021ebd  mov     [rsp+108h+var_30], rax
0x180021ec5  lea     edi, [rax+1]
0x180021ec8  mov     edx, edi; dwRevision
0x180021eca  lea     rcx, [rsp+108h+pSecurityDescriptor]; pSecurityDescriptor
0x180021ed2  call    cs:__imp_InitializeSecurityDescriptor
0x180021ed8  test    eax, eax
0x180021eda  jnz     short loc_180021F28
0x180021edc  lea     rdx, WPP_GLOBAL_Control
0x180021ee3  mov     rax, cs:WPP_GLOBAL_Control
0x180021eea  cmp     rax, rdx
0x180021eed  jz      short loc_180021F1E
0x180021eef  test    [rax+10Ch], dil
0x180021ef6  jz      short loc_180021F1E
0x180021ef8  call    cs:__imp_GetLastError
0x180021efe  lea     edx, [rdi+1Ch]
0x180021f01  mov     r9d, eax
0x180021f04  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x180021f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f12  mov     rcx, [rcx+100h]
0x180021f19  call    WPP_SF_d
0x180021f1e  mov     eax, 0C00E0C02h
0x180021f23  jmp     loc_18002268C
0x180021f28  mov     [rsp+108h+pOwner], r15
0x180021f30  test    byte ptr [rsp+108h+arg_20], dil
0x180021f38  jz      loc_180021FE8
0x180021f3e  mov     [rsp+108h+bOwnerDefaulted], r15d
0x180021f43  lea     r8, [rsp+108h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180021f48  lea     rdx, [rsp+108h+pOwner]; pOwner
0x180021f50  mov     rcx, rbx; pSecurityDescriptor
0x180021f53  call    cs:__imp_GetSecurityDescriptorOwner
0x180021f59  test    eax, eax
0x180021f5b  jnz     short loc_180021F93
0x180021f5d  call    cs:__imp_GetLastError
0x180021f63  mov     ebx, eax
0x180021f65  lea     rdx, WPP_GLOBAL_Control
0x180021f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f73  cmp     rcx, rdx
0x180021f76  jz      loc_180021E0F
0x180021f7c  test    [rcx+10Ch], dil
0x180021f83  jz      loc_180021E0F
0x180021f89  mov     edx, 1Eh
0x180021f8e  jmp     loc_180021DF9
0x180021f93  mov     r8d, [rsp+108h+bOwnerDefaulted]; bOwnerDefaulted
0x180021f98  mov     rdx, [rsp+108h+pOwner]; pOwner
0x180021fa0  lea     rcx, [rsp+108h+pSecurityDescriptor]; pSecurityDescriptor
0x180021fa8  call    cs:__imp_SetSecurityDescriptorOwner
0x180021fae  test    eax, eax
0x180021fb0  jnz     short loc_180021FE8
0x180021fb2  call    cs:__imp_GetLastError
0x180021fb8  mov     ebx, eax
0x180021fba  lea     rdx, WPP_GLOBAL_Control
0x180021fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fc8  cmp     rcx, rdx
0x180021fcb  jz      loc_180021E0F
0x180021fd1  test    [rcx+10Ch], dil
0x180021fd8  jz      loc_180021E0F
0x180021fde  mov     edx, 1Fh
0x180021fe3  jmp     loc_180021DF9
0x180021fe8  mov     [rsp+108h+pGroup], r15
0x180021ff0  test    byte ptr [rsp+108h+arg_20], 2
0x180021ff8  jz      loc_1800220A8
0x180021ffe  mov     [rsp+108h+bOwnerDefaulted], r15d
0x180022003  lea     r8, [rsp+108h+bOwnerDefaulted]; lpbGroupDefaulted
0x180022008  lea     rdx, [rsp+108h+pGroup]; pGroup
0x180022010  mov     rcx, rbx; pSecurityDescriptor
0x180022013  call    cs:__imp_GetSecurityDescriptorGroup
0x180022019  test    eax, eax
0x18002201b  jnz     short loc_180022053
0x18002201d  call    cs:__imp_GetLastError
0x180022023  mov     ebx, eax
0x180022025  lea     rdx, WPP_GLOBAL_Control
0x18002202c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022033  cmp     rcx, rdx
0x180022036  jz      loc_180021E0F
0x18002203c  test    [rcx+10Ch], dil
0x180022043  jz      loc_180021E0F
0x180022049  mov     edx, 20h ; ' '
0x18002204e  jmp     loc_180021DF9
0x180022053  mov     r8d, [rsp+108h+bOwnerDefaulted]; bGroupDefaulted
0x180022058  mov     rdx, [rsp+108h+pGroup]; pGroup
0x180022060  lea     rcx, [rsp+108h+pSecurityDescriptor]; pSecurityDescriptor
0x180022068  call    cs:__imp_SetSecurityDescriptorGroup
0x18002206e  test    eax, eax
0x180022070  jnz     short loc_1800220A8
0x180022072  call    cs:__imp_GetLastError
0x180022078  mov     ebx, eax
0x18002207a  lea     rdx, WPP_GLOBAL_Control
0x180022081  mov     rcx, cs:WPP_GLOBAL_Control
0x180022088  cmp     rcx, rdx
0x18002208b  jz      loc_180021E0F
0x180022091  test    [rcx+10Ch], dil
0x180022098  jz      loc_180021E0F
0x18002209e  mov     edx, 21h ; '!'
0x1800220a3  jmp     loc_180021DF9
0x1800220a8  mov     [rsp+108h+bSaclPresent], r15d
0x1800220ad  mov     [rsp+108h+bSaclDefaulted], r15d
0x1800220b2  mov     [rsp+108h+pSacl], r15
0x1800220ba  mov     [rsp+108h+bOwnerDefaulted], r15d
0x1800220bf  mov     rsi, r15
0x1800220c2  mov     [rsp+108h+Block], r15
0x1800220ca  test    byte ptr [rsp+108h+arg_20], 8
0x1800220d2  jz      loc_1800222A6
0x1800220d8  lea     r9, [rsp+108h+bSaclDefaulted]; lpbSaclDefaulted
0x1800220dd  lea     r8, [rsp+108h+pSacl]; pSacl
0x1800220e5  lea     rdx, [rsp+108h+bSaclPresent]; lpbSaclPresent
0x1800220ea  mov     rcx, rbx; pSecurityDescriptor
0x1800220ed  call    cs:__imp_GetSecurityDescriptorSacl
0x1800220f3  test    eax, eax
0x1800220f5  jnz     short loc_180022151
0x1800220f7  call    cs:__imp_GetLastError
0x1800220fd  mov     ebx, eax
0x1800220ff  lea     rdx, WPP_GLOBAL_Control
0x180022106  mov     rcx, cs:WPP_GLOBAL_Control
0x18002210d  cmp     rcx, rdx
0x180022110  jz      short loc_180022136
0x180022112  test    [rcx+10Ch], dil
0x180022119  jz      short loc_180022136
0x18002211b  mov     edx, 22h ; '"'
0x180022120  mov     r9d, eax
0x180022123  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x18002212a  mov     rcx, [rcx+100h]
0x180022131  call    WPP_SF_d
0x180022136  test    ebx, ebx
0x180022138  jle     short loc_180022143
0x18002213a  movzx   ebx, bx
0x18002213d  or      ebx, 80070000h
0x180022143  xor     ecx, ecx; Block
0x180022145  call    cs:__imp_free
0x18002214b  nop
0x18002214c  jmp     loc_18002268A
0x180022151  mov     edx, [rsp+108h+bSaclPresent]
0x180022155  test    edx, edx
0x180022157  jz      loc_180022231
0x18002215d  mov     rdx, [rsp+108h+pSacl]
0x180022165  test    rdx, rdx
0x180022168  jz      loc_18002222A
0x18002216e  lea     r9, [rsp+108h+Block]
0x180022176  lea     r8, [rsp+108h+bOwnerDefaulted]
0x18002217b  mov     ecx, r14d
0x18002217e  call    _ConvertSaclToNT4Format
0x180022183  mov     esi, eax
0x180022185  test    eax, eax
0x180022187  jns     loc_180022217
0x18002218d  mov     eax, 8Ch
0x180022192  mov     word ptr [rsp+108h+bOwnerDefaulted], ax
0x180022197  mov     dword ptr [rsp+108h+var_90], esi
0x18002219b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r15; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800221a2  jz      short loc_180022201
0x1800221a4  lea     r14, aAcssctrlSecd5t; "acssctrl/secd5to4"
0x1800221ab  mov     rcx, r14; wchar_t *
0x1800221ae  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800221b3  lea     r9d, [rdi+rax]
0x1800221b7  add     r9, r9
0x1800221ba  mov     [rsp+108h+var_B8], r15
0x1800221bf  mov     [rsp+108h+var_C0], r15
0x1800221c4  lea     rax, [rsp+108h+var_90]
0x1800221c9  mov     [rsp+108h+var_C8], rax
0x1800221ce  mov     [rsp+108h+var_D0], 4
0x1800221d7  lea     rax, [rsp+108h+bOwnerDefaulted]
0x1800221dc  mov     [rsp+108h+var_D8], rax
0x1800221e1  mov     [rsp+108h+var_E0], 2
0x1800221ea  mov     [rsp+108h+var_E8], r14
0x1800221ef  mov     r8d, edi
0x1800221f2  mov     edx, edi
0x1800221f4  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800221fb  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180022200  nop
0x180022201  mov     rcx, [rsp+108h+Block]; Block
0x180022209  call    cs:__imp_free
0x18002220f  nop
0x180022210  mov     eax, esi
0x180022212  jmp     loc_18002268C
0x180022217  mov     rsi, [rsp+108h+Block]
0x18002221f  test    rsi, rsi
0x180022222  jz      short loc_18002222A
0x180022224  mov     edx, [rsp+108h+bSaclPresent]
0x180022228  jmp     short loc_180022231
0x18002222a  mov     edx, r15d; bSaclPresent
0x18002222d  mov     [rsp+108h+bSaclPresent], edx
0x180022231  mov     r9d, [rsp+108h+bSaclDefaulted]; bSaclDefaulted
0x180022236  mov     r8, rsi; pSacl
0x180022239  lea     rcx, [rsp+108h+pSecurityDescriptor]; pSecurityDescriptor
0x180022241  call    cs:__imp_SetSecurityDescriptorSacl
0x180022247  test    eax, eax
0x180022249  jnz     short loc_1800222A6
0x18002224b  call    cs:__imp_GetLastError
0x180022251  mov     ebx, eax
0x180022253  lea     rdx, WPP_GLOBAL_Control
0x18002225a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022261  cmp     rcx, rdx
0x180022264  jz      short loc_18002228A
0x180022266  test    [rcx+10Ch], dil
0x18002226d  jz      short loc_18002228A
0x18002226f  mov     edx, 23h ; '#'
0x180022274  mov     r9d, eax
0x180022277  lea     r8, WPP_2615a18b32b639d9ff8ae96fe12c9701_Traceguids
0x18002227e  mov     rcx, [rcx+100h]
0x180022285  call    WPP_SF_d
0x18002228a  test    ebx, ebx
0x18002228c  jle     short loc_180022297
0x18002228e  movzx   ebx, bx
0x180022291  or      ebx, 80070000h
0x180022297  mov     rcx, rsi; Block
0x18002229a  call    cs:__imp_free
0x1800222a0  nop
  ... truncated ...
```
