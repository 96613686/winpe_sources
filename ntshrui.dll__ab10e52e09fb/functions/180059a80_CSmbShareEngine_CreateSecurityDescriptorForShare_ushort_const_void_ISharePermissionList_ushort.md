# CSmbShareEngine::_CreateSecurityDescriptorForShare(ushort const *,void *,ISharePermissionList *,ushort * *)

- ea: `0x180059a80`
- end: `0x180059d6c`
- name: `?_CreateSecurityDescriptorForShare@CSmbShareEngine@@AEAAJPEBGPEAXPEAUISharePermissionList@@PEAPEAG@Z`
- size: `748`
- prototype: `__int64 __fastcall(CSmbShareEngine *__hidden this, const unsigned __int16 *, PSID pOwner, struct ISharePermissionList *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059d74`
- `0x18005c7ac`

## callees

- `0x1800098dc`
- `0x18000b660`
- `0x18000bdc0`
- `0x18000d1f0`
- `0x18000f840`
- `0x18000fdf0`
- `0x18001b6e8`
- `0x180023adc`
- `0x18002ad00`
- `0x180059470`
- `0x180059a80`
- `0x18005a488`
- `0x18005e070`
- `0x180072800`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180059cb8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180059cb8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180059ceb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180059ceb`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180059ccc`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180059ccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059c78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059c78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180059d13`

## pseudocode

```c
__int64 __fastcall CSmbShareEngine::_CreateSecurityDescriptorForShare(
        CSmbShareEngine *this,
        const unsigned __int16 *a2,
        PSID pOwner,
        struct ISharePermissionList *a4,
        unsigned __int16 **a5)
{
  int Initiator; // ebx
  int v10; // eax
  CAceList *v11; // rdi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  void *v14; // rdx
  int v15; // r9d
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 Ace; // rax
  HLOCAL hMem; // [rsp+30h] [rbp-40h] BYREF
  CAceList *v23; // [rsp+38h] [rbp-38h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v25; // [rsp+60h] [rbp-10h]

  v23 = 0;
  Initiator = CAceList::CreateInstance(&v23);
  if ( Initiator < 0 )
  {
LABEL_40:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_055da27402593bc4c79a5720b75a8198_Traceguids,
        (unsigned int)Initiator);
    return (unsigned int)Initiator;
  }
  hMem = 0;
  v10 = LocalAllocWellKnownSid(WinBuiltinAdministratorsSid, &hMem);
  v11 = v23;
  Initiator = v10;
  if ( v10 >= 0 )
  {
    Initiator = CAceList::SetExplicitAllowAce(v23, hMem, 0x1F01FFu, 3u);
    if ( Initiator < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_11;
      v13 = 68;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_11;
      v13 = 67;
    }
    WPP_SF_(v12[2], v13);
LABEL_11:
    LocalFree(hMem);
  }
  if ( (unsigned int)CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(a2) )
  {
    if ( Initiator < 0 )
      goto LABEL_37;
    hMem = 0;
    Initiator = LocalAllocWellKnownSid(WinWorldSid, &hMem);
    if ( Initiator < 0 )
      goto LABEL_37;
    Initiator = CAceList::SetExplicitAllowAce(v11, hMem, 0x1F01FFu, 3u);
    if ( Initiator < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 70;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v17 = 69;
LABEL_22:
        WPP_SF_(v16[2], v17);
      }
    }
  }
  else
  {
    Initiator = CSmbShareEngine::_ApplyPermissionsToAcl(this, a4, v11, v15);
    if ( Initiator < 0 )
      goto LABEL_37;
    hMem = 0;
    Initiator = CFolderAclEngine::_GetInitiator((CSmbShareEngine *)((char *)this + 8), &hMem);
    if ( Initiator < 0 )
      goto LABEL_37;
    LOBYTE(v19) = -1;
    Ace = CAceList::s_FindAce(v18, (char *)v11 + 16, hMem, v19, 0);
    if ( Ace && *(_DWORD *)(Ace + 4) == 2032127 )
      Initiator = 0;
    else
      Initiator = CAceList::SetExplicitAllowAce(v11, hMem, 0x1F01FFu, 3u);
  }
  LocalFree(hMem);
  if ( Initiator >= 0 )
  {
    hMem = 0;
    Initiator = CAceList::GetAclForExplicitEntries(v11, v14, (struct _ACL **)&hMem);
    if ( Initiator >= 0 )
    {
      memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
      v25 = 0;
      InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
      if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)hMem, 0)
        || (Initiator = ResultFromKnownLastError(), Initiator >= 0) )
      {
        if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
          || (Initiator = ResultFromKnownLastError(), Initiator >= 0) )
        {
          Initiator = ConvertSDToSDDL(pSecurityDescriptor, a5);
        }
      }
      LocalFree(hMem);
    }
  }
LABEL_37:
  if ( v11 )
    CAceList::`scalar deleting destructor'(v11, (unsigned int)v14);
  if ( Initiator < 0 )
    goto LABEL_40;
  return (unsigned int)Initiator;
}

```

## disassembly

```asm
0x180059a80  push    rbp
0x180059a82  push    rbx
0x180059a83  push    rsi
0x180059a84  push    rdi
0x180059a85  push    r12
0x180059a87  push    r14
0x180059a89  push    r15
0x180059a8b  mov     rbp, rsp
0x180059a8e  sub     rsp, 70h
0x180059a92  mov     rsi, rcx
0x180059a95  mov     [rbp+var_38], 0
0x180059a9d  lea     rcx, [rbp+var_38]; struct CAceList **
0x180059aa1  mov     r15, r9
0x180059aa4  mov     r12, r8
0x180059aa7  mov     r14, rdx
0x180059aaa  call    ?CreateInstance@CAceList@@SAJPEAPEAV1@@Z; CAceList::CreateInstance(CAceList * *)
0x180059aaf  mov     ebx, eax
0x180059ab1  lea     rax, WPP_GLOBAL_Control
0x180059ab8  test    ebx, ebx
0x180059aba  js      loc_180059D31
0x180059ac0  lea     rdx, [rbp+hMem]; void **
0x180059ac4  mov     [rbp+hMem], 0
0x180059acc  mov     ecx, 1Ah; WellKnownSidType
0x180059ad1  call    ?LocalAllocWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalAllocWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180059ad6  mov     rdi, [rbp+var_38]
0x180059ada  mov     ebx, eax
0x180059adc  test    eax, eax
0x180059ade  js      short loc_180059B4C
0x180059ae0  mov     rdx, [rbp+hMem]; void *
0x180059ae4  mov     r9b, 3; unsigned __int8
0x180059ae7  mov     r8d, 1F01FFh; unsigned int
0x180059aed  mov     rcx, rdi; this
0x180059af0  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180059af5  mov     ebx, eax
0x180059af7  test    eax, eax
0x180059af9  js      short loc_180059B1B
0x180059afb  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b02  lea     rax, WPP_GLOBAL_Control
0x180059b09  cmp     rcx, rax
0x180059b0c  jz      short loc_180059B42
0x180059b0e  test    byte ptr [rcx+1Ch], 8
0x180059b12  jz      short loc_180059B42
0x180059b14  mov     edx, 43h ; 'C'
0x180059b19  jmp     short loc_180059B39
0x180059b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b22  lea     rax, WPP_GLOBAL_Control
0x180059b29  cmp     rcx, rax
0x180059b2c  jz      short loc_180059B42
0x180059b2e  test    byte ptr [rcx+1Ch], 2
0x180059b32  jz      short loc_180059B42
0x180059b34  mov     edx, 44h ; 'D'
0x180059b39  mov     rcx, [rcx+10h]
0x180059b3d  call    WPP_SF_
0x180059b42  mov     rcx, [rbp+hMem]; hMem
0x180059b46  call    cs:__imp_LocalFree
0x180059b4c  mov     rcx, r14; unsigned __int16 *
0x180059b4f  call    ?s_DoesVolumeSupportFileSystemAcls@CFolderAclEngine@@SAHPEBG@Z; CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(ushort const *)
0x180059b54  mov     r14d, 1
0x180059b5a  test    eax, eax
0x180059b5c  jz      loc_180059BFB
0x180059b62  test    ebx, ebx
0x180059b64  js      loc_180059D19
0x180059b6a  lea     rdx, [rbp+hMem]; void **
0x180059b6e  mov     [rbp+hMem], 0
0x180059b76  mov     ecx, r14d; WellKnownSidType
0x180059b79  call    ?LocalAllocWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; LocalAllocWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180059b7e  mov     ebx, eax
0x180059b80  test    eax, eax
0x180059b82  js      loc_180059D19
0x180059b88  mov     rdx, [rbp+hMem]; void *
0x180059b8c  mov     r9b, 3; unsigned __int8
0x180059b8f  mov     r8d, 1F01FFh; unsigned int
0x180059b95  mov     rcx, rdi; this
0x180059b98  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180059b9d  mov     ebx, eax
0x180059b9f  test    eax, eax
0x180059ba1  js      short loc_180059BCA
0x180059ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180059baa  lea     rax, WPP_GLOBAL_Control
0x180059bb1  cmp     rcx, rax
0x180059bb4  jz      loc_180059C74
0x180059bba  test    byte ptr [rcx+1Ch], 8
0x180059bbe  jz      loc_180059C74
0x180059bc4  lea     edx, [r14+44h]
0x180059bc8  jmp     short loc_180059BF0
0x180059bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bd1  lea     rax, WPP_GLOBAL_Control
0x180059bd8  cmp     rcx, rax
0x180059bdb  jz      loc_180059C74
0x180059be1  test    byte ptr [rcx+1Ch], 2
0x180059be5  jz      loc_180059C74
0x180059beb  mov     edx, 46h ; 'F'
0x180059bf0  mov     rcx, [rcx+10h]
0x180059bf4  call    WPP_SF_
0x180059bf9  jmp     short loc_180059C74
0x180059bfb  mov     r8, rdi; struct CAceList *
0x180059bfe  mov     rdx, r15; struct ISharePermissionList *
0x180059c01  mov     rcx, rsi; this
0x180059c04  call    ?_ApplyPermissionsToAcl@CSmbShareEngine@@AEAAJPEAUISharePermissionList@@PEAVCAceList@@H@Z; CSmbShareEngine::_ApplyPermissionsToAcl(ISharePermissionList *,CAceList *,int)
0x180059c09  mov     ebx, eax
0x180059c0b  test    eax, eax
0x180059c0d  js      loc_180059D19
0x180059c13  lea     rcx, [rsi+8]; this
0x180059c17  mov     [rbp+hMem], 0
0x180059c1f  lea     rdx, [rbp+hMem]; void **
0x180059c23  call    ?_GetInitiator@CFolderAclEngine@@IEAAJPEAPEAX@Z; CFolderAclEngine::_GetInitiator(void * *)
0x180059c28  mov     ebx, eax
0x180059c2a  test    eax, eax
0x180059c2c  js      loc_180059D19
0x180059c32  mov     r8, [rbp+hMem]
0x180059c36  lea     rdx, [rdi+10h]
0x180059c3a  mov     r9b, 0FFh
0x180059c3d  mov     [rsp+70h+var_50], 0
0x180059c46  call    ?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z; CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)
0x180059c4b  test    rax, rax
0x180059c4e  jz      short loc_180059C5D
0x180059c50  cmp     dword ptr [rax+4], 1F01FFh
0x180059c57  jnz     short loc_180059C5D
0x180059c59  xor     ebx, ebx
0x180059c5b  jmp     short loc_180059C74
0x180059c5d  mov     rdx, [rbp+hMem]; void *
0x180059c61  mov     r9b, 3; unsigned __int8
0x180059c64  mov     r8d, 1F01FFh; unsigned int
0x180059c6a  mov     rcx, rdi; this
0x180059c6d  call    ?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z; CAceList::SetExplicitAllowAce(void *,ulong,uchar)
0x180059c72  mov     ebx, eax
0x180059c74  mov     rcx, [rbp+hMem]; hMem
0x180059c78  call    cs:__imp_LocalFree
0x180059c7e  test    ebx, ebx
0x180059c80  js      loc_180059D19
0x180059c86  lea     r8, [rbp+hMem]; struct _ACL **
0x180059c8a  mov     [rbp+hMem], 0
0x180059c92  mov     rcx, rdi; this
0x180059c95  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x180059c9a  mov     ebx, eax
0x180059c9c  test    eax, eax
0x180059c9e  js      short loc_180059D19
0x180059ca0  xorps   xmm0, xmm0
0x180059ca3  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180059ca7  xor     eax, eax
0x180059ca9  mov     edx, r14d; dwRevision
0x180059cac  movups  [rbp+pSecurityDescriptor], xmm0
0x180059cb0  mov     [rbp+var_10], rax
0x180059cb4  movups  [rbp+var_20], xmm0
0x180059cb8  call    cs:__imp_InitializeSecurityDescriptor
0x180059cbe  mov     r8, [rbp+hMem]; pDacl
0x180059cc2  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180059cc6  xor     r9d, r9d; bDaclDefaulted
0x180059cc9  mov     edx, r14d; bDaclPresent
0x180059ccc  call    cs:__imp_SetSecurityDescriptorDacl
0x180059cd2  test    eax, eax
0x180059cd4  jnz     short loc_180059CE1
0x180059cd6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180059cdb  mov     ebx, eax
0x180059cdd  test    eax, eax
0x180059cdf  js      short loc_180059D0F
0x180059ce1  xor     r8d, r8d; bOwnerDefaulted
0x180059ce4  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180059ce8  mov     rdx, r12; pOwner
0x180059ceb  call    cs:__imp_SetSecurityDescriptorOwner
0x180059cf1  test    eax, eax
0x180059cf3  jnz     short loc_180059D00
0x180059cf5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180059cfa  mov     ebx, eax
0x180059cfc  test    eax, eax
0x180059cfe  js      short loc_180059D0F
0x180059d00  mov     rdx, [rbp+arg_20]; unsigned __int16 **
0x180059d04  lea     rcx, [rbp+pSecurityDescriptor]; void *
0x180059d08  call    ?ConvertSDToSDDL@@YAJPEAXPEAPEAG@Z; ConvertSDToSDDL(void *,ushort * *)
0x180059d0d  mov     ebx, eax
0x180059d0f  mov     rcx, [rbp+hMem]; hMem
0x180059d13  call    cs:__imp_LocalFree
0x180059d19  test    rdi, rdi
0x180059d1c  jz      short loc_180059D26
0x180059d1e  mov     rcx, rdi; this
0x180059d21  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x180059d26  test    ebx, ebx
0x180059d28  jns     short loc_180059D5B
0x180059d2a  lea     rax, WPP_GLOBAL_Control
0x180059d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d38  cmp     rcx, rax
0x180059d3b  jz      short loc_180059D5B
0x180059d3d  test    byte ptr [rcx+1Ch], 2
0x180059d41  jz      short loc_180059D5B
0x180059d43  mov     rcx, [rcx+10h]
0x180059d47  lea     r8, WPP_055da27402593bc4c79a5720b75a8198_Traceguids
0x180059d4e  mov     edx, 47h ; 'G'
0x180059d53  mov     r9d, ebx
0x180059d56  call    WPP_SF_d
0x180059d5b  mov     eax, ebx
0x180059d5d  add     rsp, 70h
0x180059d61  pop     r15
0x180059d63  pop     r14
0x180059d65  pop     r12
0x180059d67  pop     rdi
0x180059d68  pop     rsi
0x180059d69  pop     rbx
0x180059d6a  pop     rbp
0x180059d6b  retn
```
