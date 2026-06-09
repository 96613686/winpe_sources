# ConvertPrinterSDToRestrictedDeviceSD(void *,void * *)

- ea: `0x1800cb884`
- end: `0x1800cbd6f`
- name: `?ConvertPrinterSDToRestrictedDeviceSD@@YAJPEAXPEAPEAX@Z`
- size: `1259`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c4420`

## callees

- `0x180011e64`
- `0x180011e98`
- `0x180011ed0`
- `0x180015e28`
- `0x180046650`
- `0x180046aa0`
- `0x180047318`
- `0x180047330`
- `0x1800547e0`
- `0x1800cb884`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800cbbf2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800cbbf2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800cbac6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800cbac6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba32`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba5b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba6d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba32`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba5b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cba6d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800cbb90`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800cbbb6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800cbb90`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800cbbb6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800cbca7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800cbca7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800cb919`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800cb977`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800cb919`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800cb977`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800cbd1c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800cbd2b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800cbd1c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800cbd2b`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800cbb62`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800cbb62`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800cb9e5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800cb9e5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800cba24`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800cba24`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800cbb07`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800cbb07`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800cb984`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800cbcc5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800cb984`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800cbcc5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800cbc4c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800cbc4c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800cbc91`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800cbc91`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800cbc62`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800cbc62`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800cbc19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800cbc19`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cbcf0`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cbcf0`
- `SPOOLSS!DllFreeSplMem` at `0x1800cbd0d`
- `SPOOLSS!DllFreeSplMem` at `0x1800cbd0d`
- `SPOOLSS!DllAllocSplMem` at `0x1800cbcd0`
- `SPOOLSS!DllAllocSplMem` at `0x1800cbcd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConvertPrinterSDToRestrictedDeviceSD(void *Src, void **a2)
{
  void **v2; // r15
  struct _ACL *v4; // r14
  BOOL v5; // r12d
  NCoreLibrary *v6; // rcx
  unsigned __int64 SecurityDescriptorLength; // rsi
  void *v9; // rax
  PSECURITY_DESCRIPTOR v10; // rdi
  int LastErrorAsFailHRNoBreak; // ebx
  struct _ACL *v12; // rcx
  NCoreLibrary *v13; // rcx
  DWORD v14; // edi
  NCoreLibrary *v15; // rcx
  DWORD LengthSid; // eax
  void *v17; // rax
  struct _ACL *v18; // rsi
  NCoreLibrary *v19; // rcx
  DWORD v20; // edi
  DWORD v21; // esi
  NCoreLibrary *v22; // rcx
  unsigned __int16 *v23; // r9
  char v24; // al
  _DWORD *v25; // rcx
  NCoreLibrary *v26; // rcx
  NCoreLibrary *v27; // rcx
  NCoreLibrary *v28; // rcx
  NCoreLibrary *v29; // rcx
  NCoreLibrary *v30; // rcx
  NCoreLibrary *v31; // rcx
  void *v32; // rdi
  void *v33; // rax
  NCoreLibrary *v34; // rcx
  LPVOID pAce; // [rsp+60h] [rbp-69h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-61h] BYREF
  DWORD dwBufferLength; // [rsp+70h] [rbp-59h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-51h] BYREF
  PSID pSid; // [rsp+80h] [rbp-49h] BYREF
  PSID v40; // [rsp+88h] [rbp-41h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp-39h] BYREF
  WINBOOL bDaclPresent; // [rsp+94h] [rbp-35h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp-31h] BYREF
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C8h] [rbp-1h] BYREF
  _BYTE pAclInformation[12]; // [rsp+D0h] [rbp+7h] BYREF

  v2 = a2;
  pOwner = a2;
  v4 = 0;
  pSid = 0;
  v40 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v5 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) != 0;
  *v2 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || v5
    && !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x63u,
          0xCE5DBACu,
          0x76F17EC4u,
          0xE5F30EDB,
          0x8F58C130,
          0x9C65577D,
          0,
          0,
          &v40) )
  {
    return NCoreLibrary::GetLastErrorAsFailHRNoBreak(v6);
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
  v9 = operator new[](SecurityDescriptorLength);
  NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(&pSecurityDescriptor, v9);
  v10 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    LastErrorAsFailHRNoBreak = 0;
    memcpy_0(pSecurityDescriptor, Src, (unsigned int)SecurityDescriptorLength);
    Src = v10;
  }
  else
  {
    LastErrorAsFailHRNoBreak = -2147024882;
  }
  bDaclPresent = 0;
  v12 = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    if ( !GetSecurityDescriptorDacl(Src, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13);
    v12 = pDacl;
  }
  LODWORD(pAce) = 0;
  v14 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    *(_DWORD *)pAclInformation = 0;
    *(_QWORD *)&pAclInformation[4] = 8;
    if ( !v12 )
      goto LABEL_18;
    if ( GetAclInformation(v12, pAclInformation, 0xCu, AclSizeInformation) )
    {
      LengthSid = GetLengthSid(pSid);
      v14 = LengthSid + *(_DWORD *)&pAclInformation[4] + 8;
      LODWORD(pAce) = *(_DWORD *)pAclInformation;
      goto LABEL_19;
    }
    if ( !pDacl )
    {
LABEL_18:
      v14 = GetLengthSid(pSid) + 16;
LABEL_19:
      if ( v5 )
        v14 += GetLengthSid(v40) + 8;
      goto LABEL_21;
    }
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v15);
  }
LABEL_21:
  NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(pAclInformation, 0);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    v17 = operator new[](v14);
    NCoreLibrary::TAutoPtrArray<unsigned long>::operator=(pAclInformation, v17);
    v18 = *(struct _ACL **)pAclInformation;
    if ( *(_QWORD *)pAclInformation )
    {
      memset_0(*(void **)pAclInformation, 0, v14);
      if ( !InitializeAcl(v18, v14, 2u) )
        LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v19);
      v4 = v18;
      v20 = 0;
      if ( LastErrorAsFailHRNoBreak >= 0 )
      {
        v21 = (unsigned int)pAce;
        while ( v20 < v21 )
        {
          pAce = 0;
          if ( !GetAce(pDacl, v20, &pAce) )
            goto LABEL_39;
          v23 = (unsigned __int16 *)pAce;
          v24 = *(_BYTE *)pAce;
          if ( !*(_BYTE *)pAce || v24 == 1 || v24 == 5 || v24 == 6 )
          {
            v25 = (char *)pAce + 4;
            if ( pAce != (LPVOID)-4LL )
            {
              if ( (*v25 & 4) != 0 )
                *v25 = 983041;
              else
                *v25 = (*v25 & 8) != 0 ? 0x20001 : 0;
              v23 = (unsigned __int16 *)pAce;
            }
          }
          if ( !AddAce(v4, 2u, 0xFFFFFFFF, v23, v23[1]) )
LABEL_39:
            LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v22);
          ++v20;
          if ( LastErrorAsFailHRNoBreak < 0 )
            goto LABEL_48;
        }
        if ( AddAccessAllowedAce(v4, 2u, 0xF0001u, pSid)
          || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v26), LastErrorAsFailHRNoBreak >= 0) )
        {
          if ( v5 && !AddAccessAllowedAce(v4, 2u, 0xF0001u, v40) )
            LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v27);
        }
      }
    }
    else
    {
      LastErrorAsFailHRNoBreak = -2147024882;
    }
LABEL_48:
    v2 = (void **)pOwner;
  }
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  v45 = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    if ( InitializeSecurityDescriptor(pAbsoluteSecurityDescriptor, 1u)
      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v28), LastErrorAsFailHRNoBreak >= 0) )
    {
      if ( SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v4, 0)
        || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v29), LastErrorAsFailHRNoBreak >= 0) )
      {
        if ( (pOwner = 0, LODWORD(pAce) = 0, GetSecurityDescriptorOwner(Src, &pOwner, (LPBOOL)&pAce))
          && SetSecurityDescriptorOwner(pAbsoluteSecurityDescriptor, pOwner, (BOOL)pAce)
          || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v30), LastErrorAsFailHRNoBreak >= 0) )
        {
          pOwner = 0;
          LODWORD(pAce) = 0;
          if ( !GetSecurityDescriptorGroup(Src, &pOwner, (LPBOOL)&pAce)
            || !SetSecurityDescriptorGroup(pAbsoluteSecurityDescriptor, pOwner, (BOOL)pAce) )
          {
            LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v31);
          }
        }
      }
    }
  }
  v32 = 0;
  dwBufferLength = 0;
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    dwBufferLength = GetSecurityDescriptorLength(pAbsoluteSecurityDescriptor);
    v33 = (void *)DllAllocSplMem(dwBufferLength);
    v32 = v33;
    if ( v33 )
    {
      if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v33, &dwBufferLength)
        || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v34), LastErrorAsFailHRNoBreak >= 0) )
      {
        *v2 = v32;
        v32 = 0;
      }
    }
    else
    {
      LastErrorAsFailHRNoBreak = -2147024882;
    }
  }
  DllFreeSplMem(v32);
  if ( pSid )
    FreeSid(pSid);
  if ( v40 )
    FreeSid(v40);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(pAclInformation);
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&pSecurityDescriptor);
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x1800cb884  mov     [rsp-8+arg_10], rbx
0x1800cb889  push    rbp
0x1800cb88a  push    rsi
0x1800cb88b  push    rdi
0x1800cb88c  push    r12
0x1800cb88e  push    r13
0x1800cb890  push    r14
0x1800cb892  push    r15
0x1800cb894  lea     rbp, [rsp-27h]
0x1800cb899  sub     rsp, 0F0h
0x1800cb8a0  mov     rax, cs:__security_cookie
0x1800cb8a7  xor     rax, rsp
0x1800cb8aa  mov     [rbp+57h+var_40], rax
0x1800cb8ae  mov     r15, rdx
0x1800cb8b1  mov     [rbp+57h+pOwner], rdx
0x1800cb8b5  mov     r13, rcx
0x1800cb8b8  xor     r14d, r14d
0x1800cb8bb  mov     [rbp+57h+var_A0], r14
0x1800cb8bf  mov     [rbp+57h+var_98], r14
0x1800cb8c3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x1800cb8c7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800cb8cd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800cb8d4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800cb8d9  mov     r12d, r14d
0x1800cb8dc  test    al, al
0x1800cb8de  setnz   r12b
0x1800cb8e2  mov     [r15], r14
0x1800cb8e5  lea     rax, [rbp+57h+var_A0]
0x1800cb8e9  mov     [rsp+120h+pSid], rax; pSid
0x1800cb8ee  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x1800cb8f3  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x1800cb8f8  mov     [rsp+120h+nSubAuthority5], r14d; nSubAuthority5
0x1800cb8fd  mov     [rsp+120h+nSubAuthority4], r14d; nSubAuthority4
0x1800cb902  mov     [rsp+120h+nSubAuthority3], r14d; nSubAuthority3
0x1800cb907  mov     [rsp+120h+nSubAuthority2], r14d; nSubAuthority2
0x1800cb90c  xor     r9d, r9d; nSubAuthority1
0x1800cb90f  lea     r8d, [r14+12h]; nSubAuthority0
0x1800cb913  mov     dl, 1; nSubAuthorityCount
0x1800cb915  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800cb919  call    cs:__imp_AllocateAndInitializeSid
0x1800cb91f  test    eax, eax
0x1800cb921  jnz     short loc_1800CB92D
0x1800cb923  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cb928  jmp     loc_1800CBD48
0x1800cb92d  test    r12d, r12d
0x1800cb930  jz      short loc_1800CB981
0x1800cb932  lea     rax, [rbp+57h+var_98]
0x1800cb936  mov     [rsp+120h+pSid], rax; pSid
0x1800cb93b  mov     [rsp+120h+nSubAuthority7], r14d; nSubAuthority7
0x1800cb940  mov     [rsp+120h+nSubAuthority6], r14d; nSubAuthority6
0x1800cb945  mov     [rsp+120h+nSubAuthority5], 9C65577Dh; nSubAuthority5
0x1800cb94d  mov     [rsp+120h+nSubAuthority4], 8F58C130h; nSubAuthority4
0x1800cb955  mov     [rsp+120h+nSubAuthority3], 0E5F30EDBh; nSubAuthority3
0x1800cb95d  mov     [rsp+120h+nSubAuthority2], 76F17EC4h; nSubAuthority2
0x1800cb965  mov     r9d, 0CE5DBACh; nSubAuthority1
0x1800cb96b  mov     r8d, 63h ; 'c'; nSubAuthority0
0x1800cb971  mov     dl, 6; nSubAuthorityCount
0x1800cb973  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800cb977  call    cs:__imp_AllocateAndInitializeSid
0x1800cb97d  test    eax, eax
0x1800cb97f  jz      short loc_1800CB923
0x1800cb981  mov     rcx, r13; pSecurityDescriptor
0x1800cb984  call    cs:__imp_GetSecurityDescriptorLength
0x1800cb98a  mov     esi, eax
0x1800cb98c  mov     ecx, eax; unsigned __int64
0x1800cb98e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800cb993  mov     rdx, rax
0x1800cb996  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1800cb99a  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x1800cb99f  mov     rdi, [rbp+57h+pSecurityDescriptor]
0x1800cb9a3  test    rdi, rdi
0x1800cb9a6  jz      short loc_1800CB9BE
0x1800cb9a8  mov     ebx, r14d
0x1800cb9ab  mov     r8d, esi; Size
0x1800cb9ae  mov     rdx, r13; Src
0x1800cb9b1  mov     rcx, rdi; void *
0x1800cb9b4  call    memcpy_0
0x1800cb9b9  mov     r13, rdi
0x1800cb9bc  jmp     short loc_1800CB9C3
0x1800cb9be  mov     ebx, 8007000Eh
0x1800cb9c3  mov     [rbp+57h+bDaclPresent], r14d
0x1800cb9c7  mov     rcx, r14
0x1800cb9ca  mov     [rbp+57h+pDacl], rcx
0x1800cb9ce  mov     [rbp+57h+bDaclDefaulted], r14d
0x1800cb9d2  test    ebx, ebx
0x1800cb9d4  js      short loc_1800CB9FA
0x1800cb9d6  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x1800cb9da  lea     r8, [rbp+57h+pDacl]; pDacl
0x1800cb9de  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x1800cb9e2  mov     rcx, r13; pSecurityDescriptor
0x1800cb9e5  call    cs:__imp_GetSecurityDescriptorDacl
0x1800cb9eb  test    eax, eax
0x1800cb9ed  jnz     short loc_1800CB9F6
0x1800cb9ef  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cb9f4  mov     ebx, eax
0x1800cb9f6  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1800cb9fa  mov     dword ptr [rbp+57h+pAce], r14d
0x1800cb9fe  mov     edi, r14d
0x1800cba01  test    ebx, ebx
0x1800cba03  js      short loc_1800CBA78
0x1800cba05  xor     eax, eax
0x1800cba07  mov     [rbp+57h+pAclInformation], rax
0x1800cba0b  mov     [rbp+57h+pAclInformation+4], 8
0x1800cba13  test    rcx, rcx
0x1800cba16  jz      short loc_1800CBA57
0x1800cba18  lea     r9d, [rax+2]; dwAclInformationClass
0x1800cba1c  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1800cba20  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x1800cba24  call    cs:__imp_GetAclInformation
0x1800cba2a  test    eax, eax
0x1800cba2c  jz      short loc_1800CBA48
0x1800cba2e  mov     rcx, [rbp+57h+var_A0]; pSid
0x1800cba32  call    cs:__imp_GetLengthSid
0x1800cba38  mov     edi, dword ptr [rbp+57h+pAclInformation+4]
0x1800cba3b  add     edi, 8
0x1800cba3e  add     edi, eax
0x1800cba40  mov     eax, dword ptr [rbp+57h+pAclInformation]
0x1800cba43  mov     dword ptr [rbp+57h+pAce], eax
0x1800cba46  jmp     short loc_1800CBA64
0x1800cba48  cmp     [rbp+57h+pDacl], r14
0x1800cba4c  jz      short loc_1800CBA57
0x1800cba4e  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cba53  mov     ebx, eax
0x1800cba55  jmp     short loc_1800CBA78
0x1800cba57  mov     rcx, [rbp+57h+var_A0]; pSid
0x1800cba5b  call    cs:__imp_GetLengthSid
0x1800cba61  lea     edi, [rax+10h]
0x1800cba64  test    r12d, r12d
0x1800cba67  jz      short loc_1800CBA78
0x1800cba69  mov     rcx, [rbp+57h+var_98]; pSid
0x1800cba6d  call    cs:__imp_GetLengthSid
0x1800cba73  add     edi, 8
0x1800cba76  add     edi, eax
0x1800cba78  xor     edx, edx
0x1800cba7a  lea     rcx, [rbp+57h+pAclInformation]
0x1800cba7e  call    ??0?$TAutoPtrArray@UPrintNamedProperty@@@NCoreLibrary@@QEAA@PEAUPrintNamedProperty@@@Z; NCoreLibrary::TAutoPtrArray<PrintNamedProperty>::TAutoPtrArray<PrintNamedProperty>(PrintNamedProperty *)
0x1800cba83  test    ebx, ebx
0x1800cba85  js      loc_1800CBBD2
0x1800cba8b  mov     r15d, edi
0x1800cba8e  mov     ecx, edi; unsigned __int64
0x1800cba90  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800cba95  mov     rdx, rax
0x1800cba98  lea     rcx, [rbp+57h+pAclInformation]
0x1800cba9c  call    ??4?$TAutoPtrArray@K@NCoreLibrary@@QEAAPEAKPEAK@Z; NCoreLibrary::TAutoPtrArray<ulong>::operator=(ulong *)
0x1800cbaa1  mov     rsi, [rbp+57h+pAclInformation]
0x1800cbaa5  test    rsi, rsi
0x1800cbaa8  jz      loc_1800CBBC9
0x1800cbaae  mov     r8d, r15d; Size
0x1800cbab1  xor     edx, edx; Val
0x1800cbab3  mov     rcx, rsi; void *
0x1800cbab6  call    memset_0
0x1800cbabb  mov     r8d, 2; dwAclRevision
0x1800cbac1  mov     edx, edi; nAclLength
0x1800cbac3  mov     rcx, rsi; pAcl
0x1800cbac6  call    cs:__imp_InitializeAcl
0x1800cbacc  test    eax, eax
0x1800cbace  jnz     short loc_1800CBAD7
0x1800cbad0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbad5  mov     ebx, eax
0x1800cbad7  mov     r14, rsi
0x1800cbada  xor     edi, edi
0x1800cbadc  test    ebx, ebx
0x1800cbade  js      loc_1800CBBCE
0x1800cbae4  mov     r15d, 0F0001h
0x1800cbaea  mov     esi, dword ptr [rbp+57h+pAce]
0x1800cbaed  cmp     edi, esi
0x1800cbaef  jnb     loc_1800CBB7F
0x1800cbaf5  mov     [rbp+57h+pAce], 0
0x1800cbafd  lea     r8, [rbp+57h+pAce]; pAce
0x1800cbb01  mov     edx, edi; dwAceIndex
0x1800cbb03  mov     rcx, [rbp+57h+pDacl]; pAcl
0x1800cbb07  call    cs:__imp_GetAce
0x1800cbb0d  test    eax, eax
0x1800cbb0f  jz      short loc_1800CBB6C
0x1800cbb11  mov     r9, [rbp+57h+pAce]
0x1800cbb15  mov     al, [r9]
0x1800cbb18  test    al, al
0x1800cbb1a  jz      short loc_1800CBB28
0x1800cbb1c  cmp     al, 1
0x1800cbb1e  jz      short loc_1800CBB28
0x1800cbb20  cmp     al, 5
0x1800cbb22  jz      short loc_1800CBB28
0x1800cbb24  cmp     al, 6
0x1800cbb26  jnz     short loc_1800CBB4D
0x1800cbb28  lea     rcx, [r9+4]
0x1800cbb2c  test    rcx, rcx
0x1800cbb2f  jz      short loc_1800CBB4D
0x1800cbb31  mov     eax, [rcx]
0x1800cbb33  test    al, 4
0x1800cbb35  jz      short loc_1800CBB3C
0x1800cbb37  mov     [rcx], r15d
0x1800cbb3a  jmp     short loc_1800CBB49
0x1800cbb3c  and     al, 8
0x1800cbb3e  neg     al
0x1800cbb40  sbb     eax, eax
0x1800cbb42  and     eax, 20001h
0x1800cbb47  mov     [rcx], eax
0x1800cbb49  mov     r9, [rbp+57h+pAce]; pAceList
0x1800cbb4d  movzx   eax, word ptr [r9+2]
0x1800cbb52  mov     [rsp+120h+nSubAuthority2], eax; nAceListLength
0x1800cbb56  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800cbb5a  mov     edx, 2; dwAceRevision
0x1800cbb5f  mov     rcx, r14; pAcl
0x1800cbb62  call    cs:__imp_AddAce
0x1800cbb68  test    eax, eax
0x1800cbb6a  jnz     short loc_1800CBB73
0x1800cbb6c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbb71  mov     ebx, eax
0x1800cbb73  inc     edi
0x1800cbb75  test    ebx, ebx
0x1800cbb77  jns     loc_1800CBAED
0x1800cbb7d  jmp     short loc_1800CBBCE
0x1800cbb7f  mov     r9, [rbp+57h+var_A0]; pSid
0x1800cbb83  mov     r8d, r15d; AccessMask
0x1800cbb86  mov     edi, 2
0x1800cbb8b  mov     edx, edi; dwAceRevision
0x1800cbb8d  mov     rcx, r14; pAcl
0x1800cbb90  call    cs:__imp_AddAccessAllowedAce
0x1800cbb96  test    eax, eax
0x1800cbb98  jnz     short loc_1800CBBA5
0x1800cbb9a  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbb9f  mov     ebx, eax
0x1800cbba1  test    eax, eax
0x1800cbba3  js      short loc_1800CBBCE
0x1800cbba5  test    r12d, r12d
0x1800cbba8  jz      short loc_1800CBBCE
0x1800cbbaa  mov     r9, [rbp+57h+var_98]; pSid
0x1800cbbae  mov     r8d, r15d; AccessMask
0x1800cbbb1  mov     edx, edi; dwAceRevision
0x1800cbbb3  mov     rcx, r14; pAcl
0x1800cbbb6  call    cs:__imp_AddAccessAllowedAce
0x1800cbbbc  test    eax, eax
0x1800cbbbe  jnz     short loc_1800CBBCE
0x1800cbbc0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbbc5  mov     ebx, eax
0x1800cbbc7  jmp     short loc_1800CBBCE
0x1800cbbc9  mov     ebx, 8007000Eh
0x1800cbbce  mov     r15, [rbp+57h+pOwner]
0x1800cbbd2  xorps   xmm0, xmm0
0x1800cbbd5  xor     eax, eax
0x1800cbbd7  movups  [rbp+57h+pAbsoluteSecurityDescriptor], xmm0
0x1800cbbdb  movups  [rbp+57h+var_70], xmm0
0x1800cbbdf  mov     [rbp+57h+var_60], rax
0x1800cbbe3  test    ebx, ebx
0x1800cbbe5  js      loc_1800CBCB8
0x1800cbbeb  lea     edx, [rax+1]; dwRevision
0x1800cbbee  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x1800cbbf2  call    cs:__imp_InitializeSecurityDescriptor
0x1800cbbf8  test    eax, eax
0x1800cbbfa  jnz     short loc_1800CBC0B
0x1800cbbfc  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbc01  mov     ebx, eax
0x1800cbc03  test    eax, eax
0x1800cbc05  js      loc_1800CBCB8
0x1800cbc0b  xor     r9d, r9d; bDaclDefaulted
0x1800cbc0e  mov     r8, r14; pDacl
0x1800cbc11  lea     edx, [r9+1]; bDaclPresent
0x1800cbc15  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x1800cbc19  call    cs:__imp_SetSecurityDescriptorDacl
0x1800cbc1f  test    eax, eax
0x1800cbc21  jnz     short loc_1800CBC32
0x1800cbc23  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbc28  mov     ebx, eax
0x1800cbc2a  test    eax, eax
0x1800cbc2c  js      loc_1800CBCB8
0x1800cbc32  mov     [rbp+57h+pOwner], 0
0x1800cbc3a  mov     dword ptr [rbp+57h+pAce], 0
0x1800cbc41  lea     r8, [rbp+57h+pAce]; lpbOwnerDefaulted
0x1800cbc45  lea     rdx, [rbp+57h+pOwner]; pOwner
0x1800cbc49  mov     rcx, r13; pSecurityDescriptor
0x1800cbc4c  call    cs:__imp_GetSecurityDescriptorOwner
0x1800cbc52  test    eax, eax
0x1800cbc54  jz      short loc_1800CBC6C
0x1800cbc56  mov     r8d, dword ptr [rbp+57h+pAce]; bOwnerDefaulted
0x1800cbc5a  mov     rdx, [rbp+57h+pOwner]; pOwner
0x1800cbc5e  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x1800cbc62  call    cs:__imp_SetSecurityDescriptorOwner
0x1800cbc68  test    eax, eax
0x1800cbc6a  jnz     short loc_1800CBC77
0x1800cbc6c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbc71  mov     ebx, eax
0x1800cbc73  test    eax, eax
0x1800cbc75  js      short loc_1800CBCB8
0x1800cbc77  mov     [rbp+57h+pOwner], 0
0x1800cbc7f  mov     dword ptr [rbp+57h+pAce], 0
0x1800cbc86  lea     r8, [rbp+57h+pAce]; lpbGroupDefaulted
0x1800cbc8a  lea     rdx, [rbp+57h+pOwner]; pGroup
0x1800cbc8e  mov     rcx, r13; pSecurityDescriptor
0x1800cbc91  call    cs:__imp_GetSecurityDescriptorGroup
0x1800cbc97  test    eax, eax
0x1800cbc99  jz      short loc_1800CBCB1
0x1800cbc9b  mov     r8d, dword ptr [rbp+57h+pAce]; bGroupDefaulted
0x1800cbc9f  mov     rdx, [rbp+57h+pOwner]; pGroup
0x1800cbca3  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x1800cbca7  call    cs:__imp_SetSecurityDescriptorGroup
0x1800cbcad  test    eax, eax
0x1800cbcaf  jnz     short loc_1800CBCB8
0x1800cbcb1  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800cbcb6  mov     ebx, eax
0x1800cbcb8  xor     edi, edi
  ... truncated ...
```
