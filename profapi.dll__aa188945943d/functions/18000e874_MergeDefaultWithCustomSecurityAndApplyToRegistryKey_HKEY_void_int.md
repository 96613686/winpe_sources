# MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)

- ea: `0x18000e874`
- end: `0x18000ebda`
- name: `?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z`
- size: `870`
- prototype: `__int64 __fastcall(HKEY, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e640`

## callees

- `0x1800063e0`
- `0x180007c60`
- `0x18000a750`
- `0x18000e874`
- `0x180012080`
- `0x18001214c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb65`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000e8e0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000e927`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000e8e0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000e927`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18000eb90`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18000eb90`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e9ae`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000eb1a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000e9ae`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000eb1a`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18000eb57`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18000eb57`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000e964`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000e964`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000ea3e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000eae0`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000ea3e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000eae0`

## pseudocode

```c
__int64 __fastcall MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY a1, void *a2, int a3)
{
  PSECURITY_DESCRIPTOR v4; // r14
  PACL v5; // rsi
  int v7; // eax
  PSECURITY_DESCRIPTOR v8; // r15
  int KeySecurity; // eax
  LSTATUS v10; // eax
  bool v11; // sf
  BOOL SecurityDescriptorDacl; // eax
  struct _ACL *v13; // rcx
  unsigned __int16 v14; // di
  DWORD v15; // ebx
  DWORD AceCount; // r12d
  BOOL Ace; // eax
  DWORD v18; // ebx
  signed int LastError; // eax
  bool v20; // sf
  int v21; // eax
  signed int v22; // eax
  bool v23; // sf
  BOOL v24; // eax
  signed int v25; // eax
  bool v26; // sf
  LSTATUS v27; // eax
  unsigned int v28; // ebx
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+60h] [rbp-19h] BYREF
  LPVOID pAce; // [rsp+68h] [rbp-11h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp-9h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+74h] [rbp-5h] BYREF
  DWORD dwOwnerSize; // [rsp+78h] [rbp-1h] BYREF
  DWORD dwSaclSize; // [rsp+7Ch] [rbp+3h] BYREF
  PACL pDacl; // [rsp+80h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+88h] [rbp+Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp+17h] BYREF
  PACL pAcl; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD cbSecurityDescriptor; // [rsp+E8h] [rbp+6Fh] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+F8h] [rbp+7Fh] BYREF

  pSecurityDescriptor = 0;
  pAbsoluteSecurityDescriptor = 0;
  v4 = 0;
  pAcl = 0;
  v5 = 0;
  cbSecurityDescriptor = 512;
  v7 = ResultFromHeapAlloc(0x200u, &pSecurityDescriptor);
  v8 = pSecurityDescriptor;
  if ( v7 < 0 )
    goto LABEL_43;
  KeySecurity = RegGetKeySecurity(a1, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
  if ( KeySecurity > 0 )
    KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
  if ( KeySecurity == -2147024774 )
  {
    pSecurityDescriptor = 0;
    if ( (int)ResultFromHeapReAlloc(v8, cbSecurityDescriptor, &pSecurityDescriptor) < 0 )
      goto LABEL_43;
    v8 = pSecurityDescriptor;
    v10 = RegGetKeySecurity(a1, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
    v11 = v10 < 0;
    if ( v10 <= 0 )
      goto LABEL_9;
    KeySecurity = (unsigned __int16)v10 | 0x80070000;
  }
  v11 = KeySecurity < 0;
LABEL_9:
  if ( !v11 )
  {
    if ( a3 )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      SecurityDescriptorDacl = GetSecurityDescriptorDacl(v8, &bDaclPresent, &pDacl, &bDaclDefaulted);
      if ( (int)ResultFromWin32Bool(SecurityDescriptorDacl) >= 0 )
      {
        if ( bDaclPresent )
        {
          v13 = pDacl;
          if ( pDacl )
          {
            pAce = 0;
            v14 = 0;
            v15 = 0;
            AceCount = pDacl->AceCount;
            if ( pDacl->AceCount )
            {
              while ( 1 )
              {
                Ace = GetAce(v13, v15, &pAce);
                if ( (int)ResultFromWin32Bool(Ace) < 0 )
                  break;
                if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
                  v14 += *((_WORD *)pAce + 1);
                if ( ++v15 >= AceCount )
                {
                  v18 = 0;
                  if ( v14 )
                  {
                    dwAbsoluteSecurityDescriptorSize = 0;
                    LODWORD(pSecurityDescriptor) = 0;
                    dwSaclSize = 0;
                    dwOwnerSize = 0;
                    dwPrimaryGroupSize = 0;
                    if ( MakeAbsoluteSD(
                           a2,
                           0,
                           &dwAbsoluteSecurityDescriptorSize,
                           0,
                           (LPDWORD)&pSecurityDescriptor,
                           0,
                           &dwSaclSize,
                           0,
                           &dwOwnerSize,
                           0,
                           &dwPrimaryGroupSize)
                      || GetLastError() == 122 )
                    {
                      goto LABEL_26;
                    }
                    LastError = GetLastError();
                    v20 = LastError < 0;
                    if ( LastError > 0 )
                      v20 = 1;
                    if ( !v20 )
                    {
LABEL_26:
                      if ( (int)ResultFromHeapAlloc(dwAbsoluteSecurityDescriptorSize, &pAbsoluteSecurityDescriptor) < 0 )
                      {
                        v4 = pAbsoluteSecurityDescriptor;
                      }
                      else
                      {
                        v21 = ResultFromHeapAlloc((unsigned int)pSecurityDescriptor + v14, (void **)&pAcl);
                        v5 = pAcl;
                        v4 = pAbsoluteSecurityDescriptor;
                        if ( v21 >= 0 )
                        {
                          if ( MakeAbsoluteSD(
                                 a2,
                                 pAbsoluteSecurityDescriptor,
                                 &dwAbsoluteSecurityDescriptorSize,
                                 pAcl,
                                 (LPDWORD)&pSecurityDescriptor,
                                 0,
                                 &dwSaclSize,
                                 0,
                                 &dwOwnerSize,
                                 0,
                                 &dwPrimaryGroupSize) )
                          {
                            goto LABEL_32;
                          }
                          v22 = GetLastError();
                          v23 = v22 < 0;
                          if ( v22 > 0 )
                            v23 = 1;
                          if ( !v23 )
                          {
LABEL_32:
                            v5->AclRevision = 2;
                            v5->AclSize += v14;
                            while ( 1 )
                            {
                              if ( v18 >= AceCount )
                                goto LABEL_41;
                              v24 = GetAce(pDacl, v18, &pAce);
                              if ( (int)ResultFromWin32Bool(v24) < 0 )
                                goto LABEL_43;
                              if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
                              {
                                *((_BYTE *)pAce + 1) &= ~0x10u;
                                if ( !AddAce(v5, 2u, 0, pAce, *((unsigned __int16 *)pAce + 1)) )
                                  break;
                              }
                              ++v18;
                            }
                            v25 = GetLastError();
                            v26 = v25 < 0;
                            if ( v25 > 0 )
                              v26 = 1;
                            if ( !v26 )
                            {
LABEL_41:
                              a2 = v4;
                              break;
                            }
                          }
                        }
                      }
                    }
                  }
                  break;
                }
                v13 = pDacl;
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  v27 = RegSetKeySecurity(a1, 4u, a2);
  v28 = v27;
  if ( v27 > 0 )
    v28 = (unsigned __int16)v27 | 0x80070000;
  ResultFromHeapFree(v4);
  ResultFromHeapFree(v8);
  ResultFromHeapFree(v5);
  return v28;
}

```

## disassembly

```asm
0x18000e874  mov     [rsp-8+arg_10], rbx
0x18000e879  mov     [rsp-8+hKey], rcx
0x18000e87e  push    rbp
0x18000e87f  push    rsi
0x18000e880  push    rdi
0x18000e881  push    r12
0x18000e883  push    r13
0x18000e885  push    r14
0x18000e887  push    r15
0x18000e889  lea     rbp, [rsp-27h]
0x18000e88e  sub     rsp, 0A0h
0x18000e895  xor     r12d, r12d
0x18000e898  mov     r13, rdx
0x18000e89b  mov     ecx, 200h; dwBytes
0x18000e8a0  mov     [rbp+57h+pSecurityDescriptor], r12
0x18000e8a4  lea     rdx, [rbp+57h+pSecurityDescriptor]; void **
0x18000e8a8  mov     [rbp+57h+pAbsoluteSecurityDescriptor], r12
0x18000e8ac  mov     r14d, r12d
0x18000e8af  mov     [rbp+57h+pAcl], r12
0x18000e8b3  mov     esi, r12d
0x18000e8b6  mov     [rbp+57h+cbSecurityDescriptor], ecx
0x18000e8b9  mov     ebx, r8d
0x18000e8bc  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000e8c1  mov     r15, [rbp+57h+pSecurityDescriptor]
0x18000e8c5  test    eax, eax
0x18000e8c7  js      loc_18000EB84
0x18000e8cd  mov     rdi, [rbp+57h+hKey]
0x18000e8d1  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000e8d5  mov     rcx, rdi; hKey
0x18000e8d8  lea     edx, [r12+4]; SecurityInformation
0x18000e8dd  mov     r8, r15; pSecurityDescriptor
0x18000e8e0  call    cs:__imp_RegGetKeySecurity
0x18000e8e6  test    eax, eax
0x18000e8e8  jle     short loc_18000E8F2
0x18000e8ea  movzx   eax, ax
0x18000e8ed  or      eax, 80070000h
0x18000e8f2  cmp     eax, 8007007Ah
0x18000e8f7  jnz     short loc_18000E939
0x18000e8f9  mov     edx, [rbp+57h+cbSecurityDescriptor]; dwBytes
0x18000e8fc  lea     r8, [rbp+57h+pSecurityDescriptor]; void **
0x18000e900  mov     rcx, r15; lpMem
0x18000e903  mov     [rbp+57h+pSecurityDescriptor], r12
0x18000e907  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x18000e90c  test    eax, eax
0x18000e90e  js      loc_18000EB84
0x18000e914  mov     r15, [rbp+57h+pSecurityDescriptor]
0x18000e918  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000e91c  mov     r8, r15; pSecurityDescriptor
0x18000e91f  mov     edx, 4; SecurityInformation
0x18000e924  mov     rcx, rdi; hKey
0x18000e927  call    cs:__imp_RegGetKeySecurity
0x18000e92d  test    eax, eax
0x18000e92f  jle     short loc_18000E93B
0x18000e931  movzx   eax, ax
0x18000e934  or      eax, 80070000h
0x18000e939  test    eax, eax
0x18000e93b  js      loc_18000EB84
0x18000e941  test    ebx, ebx
0x18000e943  jz      loc_18000EB84
0x18000e949  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18000e94d  mov     [rbp+57h+pDacl], r12
0x18000e951  lea     r8, [rbp+57h+pDacl]; pDacl
0x18000e955  mov     [rbp+57h+bDaclPresent], r12d
0x18000e959  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18000e95d  mov     [rbp+57h+bDaclDefaulted], r12d
0x18000e961  mov     rcx, r15; pSecurityDescriptor
0x18000e964  call    cs:__imp_GetSecurityDescriptorDacl
0x18000e96a  mov     ecx, eax; int
0x18000e96c  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000e971  test    eax, eax
0x18000e973  js      loc_18000EB84
0x18000e979  cmp     [rbp+57h+bDaclPresent], r12d
0x18000e97d  jz      loc_18000EB84
0x18000e983  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18000e987  test    rcx, rcx
0x18000e98a  jz      loc_18000EB84
0x18000e990  mov     [rbp+57h+pAce], r12
0x18000e994  mov     edi, r12d
0x18000e997  mov     ebx, r12d
0x18000e99a  movzx   r12d, word ptr [rcx+4]
0x18000e99f  test    r12d, r12d
0x18000e9a2  jz      loc_18000EB84
0x18000e9a8  lea     r8, [rbp+57h+pAce]; pAce
0x18000e9ac  mov     edx, ebx; dwAceIndex
0x18000e9ae  call    cs:__imp_GetAce
0x18000e9b4  mov     ecx, eax; int
0x18000e9b6  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000e9bb  test    eax, eax
0x18000e9bd  js      loc_18000EB84
0x18000e9c3  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x18000e9c7  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x18000e9cc  test    eax, eax
0x18000e9ce  jz      short loc_18000E9D8
0x18000e9d0  mov     rax, [rbp+57h+pAce]
0x18000e9d4  add     di, [rax+2]
0x18000e9d8  inc     ebx
0x18000e9da  cmp     ebx, r12d
0x18000e9dd  jnb     short loc_18000E9E5
0x18000e9df  mov     rcx, [rbp+57h+pDacl]
0x18000e9e3  jmp     short loc_18000E9A8
0x18000e9e5  xor     ebx, ebx
0x18000e9e7  test    di, di
0x18000e9ea  jz      loc_18000EB84
0x18000e9f0  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000e9f4  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x18000e9f7  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18000e9fc  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000ea00  mov     [rsp+0D0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18000ea05  lea     rax, [rbp+57h+dwOwnerSize]
0x18000ea09  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000ea0e  xor     r9d, r9d; pDacl
0x18000ea11  mov     [rsp+0D0h+pOwner], rbx; pOwner
0x18000ea16  lea     rax, [rbp+57h+dwSaclSize]
0x18000ea1a  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000ea1f  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18000ea21  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000ea25  mov     [rsp+0D0h+pSacl], rbx; pSacl
0x18000ea2a  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18000ea2d  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000ea32  mov     dword ptr [rbp+57h+pSecurityDescriptor], ebx
0x18000ea35  mov     [rbp+57h+dwSaclSize], ebx
0x18000ea38  mov     [rbp+57h+dwOwnerSize], ebx
0x18000ea3b  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x18000ea3e  call    cs:__imp_MakeAbsoluteSD
0x18000ea44  test    eax, eax
0x18000ea46  jnz     short loc_18000EA6D
0x18000ea48  call    cs:__imp_GetLastError
0x18000ea4e  cmp     eax, 7Ah ; 'z'
0x18000ea51  jz      short loc_18000EA6D
0x18000ea53  call    cs:__imp_GetLastError
0x18000ea59  test    eax, eax
0x18000ea5b  jle     short loc_18000EA67
0x18000ea5d  movzx   eax, ax
0x18000ea60  or      eax, 80070000h
0x18000ea65  test    eax, eax
0x18000ea67  js      loc_18000EB84
0x18000ea6d  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; dwBytes
0x18000ea70  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; void **
0x18000ea74  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000ea79  test    eax, eax
0x18000ea7b  js      loc_18000EB80
0x18000ea81  movzx   ecx, di
0x18000ea84  lea     rdx, [rbp+57h+pAcl]; void **
0x18000ea88  add     ecx, dword ptr [rbp+57h+pSecurityDescriptor]; dwBytes
0x18000ea8b  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18000ea90  mov     rsi, [rbp+57h+pAcl]
0x18000ea94  mov     r14, [rbp+57h+pAbsoluteSecurityDescriptor]
0x18000ea98  test    eax, eax
0x18000ea9a  js      loc_18000EB84
0x18000eaa0  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000eaa4  mov     r9, rsi; pDacl
0x18000eaa7  mov     [rsp+0D0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x18000eaac  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000eab0  mov     [rsp+0D0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18000eab5  lea     rax, [rbp+57h+dwOwnerSize]
0x18000eab9  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000eabe  mov     rdx, r14; pAbsoluteSecurityDescriptor
0x18000eac1  mov     [rsp+0D0h+pOwner], rbx; pOwner
0x18000eac6  lea     rax, [rbp+57h+dwSaclSize]
0x18000eaca  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000eacf  mov     rcx, r13; pSelfRelativeSecurityDescriptor
0x18000ead2  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000ead6  mov     [rsp+0D0h+pSacl], rbx; pSacl
0x18000eadb  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000eae0  call    cs:__imp_MakeAbsoluteSD
0x18000eae6  test    eax, eax
0x18000eae8  jnz     short loc_18000EB04
0x18000eaea  call    cs:__imp_GetLastError
0x18000eaf0  test    eax, eax
0x18000eaf2  jle     short loc_18000EAFE
0x18000eaf4  movzx   eax, ax
0x18000eaf7  or      eax, 80070000h
0x18000eafc  test    eax, eax
0x18000eafe  js      loc_18000EB84
0x18000eb04  mov     byte ptr [rsi], 2
0x18000eb07  add     [rsi+2], di
0x18000eb0b  cmp     ebx, r12d
0x18000eb0e  jnb     short loc_18000EB7B
0x18000eb10  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18000eb14  lea     r8, [rbp+57h+pAce]; pAce
0x18000eb18  mov     edx, ebx; dwAceIndex
0x18000eb1a  call    cs:__imp_GetAce
0x18000eb20  mov     ecx, eax; int
0x18000eb22  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18000eb27  test    eax, eax
0x18000eb29  js      short loc_18000EB84
0x18000eb2b  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x18000eb2f  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x18000eb34  test    eax, eax
0x18000eb36  jz      short loc_18000EB61
0x18000eb38  mov     rax, [rbp+57h+pAce]
0x18000eb3c  xor     r8d, r8d; dwStartingAceIndex
0x18000eb3f  mov     rcx, rsi; pAcl
0x18000eb42  and     byte ptr [rax+1], 0EFh
0x18000eb46  lea     edx, [r8+2]; dwAceRevision
0x18000eb4a  mov     r9, [rbp+57h+pAce]; pAceList
0x18000eb4e  movzx   eax, word ptr [r9+2]
0x18000eb53  mov     dword ptr [rsp+0D0h+lpdwDaclSize], eax; nAceListLength
0x18000eb57  call    cs:__imp_AddAce
0x18000eb5d  test    eax, eax
0x18000eb5f  jz      short loc_18000EB65
0x18000eb61  inc     ebx
0x18000eb63  jmp     short loc_18000EB0B
0x18000eb65  call    cs:__imp_GetLastError
0x18000eb6b  test    eax, eax
0x18000eb6d  jle     short loc_18000EB79
0x18000eb6f  movzx   eax, ax
0x18000eb72  or      eax, 80070000h
0x18000eb77  test    eax, eax
0x18000eb79  js      short loc_18000EB84
0x18000eb7b  mov     r13, r14
0x18000eb7e  jmp     short loc_18000EB84
0x18000eb80  mov     r14, [rbp+57h+pAbsoluteSecurityDescriptor]
0x18000eb84  mov     rcx, [rbp+57h+hKey]; hKey
0x18000eb88  mov     r8, r13; pSecurityDescriptor
0x18000eb8b  mov     edx, 4; SecurityInformation
0x18000eb90  call    cs:__imp_RegSetKeySecurity
0x18000eb96  mov     ebx, eax
0x18000eb98  test    eax, eax
0x18000eb9a  jle     short loc_18000EBA5
0x18000eb9c  movzx   ebx, ax
0x18000eb9f  or      ebx, 80070000h
0x18000eba5  mov     rcx, r14; lpMem
0x18000eba8  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000ebad  mov     rcx, r15; lpMem
0x18000ebb0  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000ebb5  mov     rcx, rsi; lpMem
0x18000ebb8  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000ebbd  mov     eax, ebx
0x18000ebbf  mov     rbx, [rsp+0D0h+arg_10]
0x18000ebc7  add     rsp, 0A0h
0x18000ebce  pop     r15
0x18000ebd0  pop     r14
0x18000ebd2  pop     r13
0x18000ebd4  pop     r12
0x18000ebd6  pop     rdi
0x18000ebd7  pop     rsi
0x18000ebd8  pop     rbp
0x18000ebd9  retn
```
