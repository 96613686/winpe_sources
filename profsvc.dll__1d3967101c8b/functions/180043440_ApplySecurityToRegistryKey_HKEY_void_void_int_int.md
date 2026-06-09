# ApplySecurityToRegistryKey_(HKEY__ *,void *,void *,int,int)

- ea: `0x180043440`
- end: `0x1800436a3`
- name: `?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z`
- size: `611`
- prototype: `__int64 __fastcall(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004170`
- `0x180006580`
- `0x1800220f0`
- `0x18003e8fc`
- `0x180043440`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004348c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800434dc`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18004348c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800434dc`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800435a5`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800435a5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004353a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004353a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180043577`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180043577`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043511`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800435f8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180043511`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800435f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043675`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800435cf`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800435cf`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004365f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18004365f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180043629`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180043629`

## pseudocode

```c
__int64 __fastcall ApplySecurityToRegistryKey_(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a3)
{
  int v5; // eax
  PSECURITY_DESCRIPTOR v6; // rdi
  signed int v7; // ebx
  LSTATUS KeySecurity; // eax
  LSTATUS v9; // eax
  BOOL SecurityDescriptorDacl; // eax
  DWORD v11; // esi
  DWORD v12; // edx
  struct _ACL *v13; // rsi
  BOOL v14; // eax
  BOOL v15; // eax
  signed int ExplicitEntriesFromAclW; // eax
  BOOL v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+44h] [rbp-2Ch] BYREF
  WINBOOL bDaclDefaulted; // [rsp+48h] [rbp-28h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+4Ch] [rbp-24h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-20h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptora; // [rsp+60h] [rbp-10h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+68h] [rbp-8h] BYREF

  cbSecurityDescriptor = 512;
  pSecurityDescriptora = 0;
  v5 = ResultFromHeapAlloc(0x200u, &pSecurityDescriptora);
  v6 = pSecurityDescriptora;
  v7 = v5;
  if ( v5 >= 0 )
  {
    KeySecurity = RegGetKeySecurity(handle, 4u, pSecurityDescriptora, &cbSecurityDescriptor);
    v7 = KeySecurity;
    if ( KeySecurity > 0 )
      v7 = (unsigned __int16)KeySecurity | 0x80070000;
    if ( v7 == -2147024774 )
    {
      pSecurityDescriptora = 0;
      v7 = ResultFromHeapReAlloc(v6, cbSecurityDescriptor, &pSecurityDescriptora);
      if ( v7 < 0 )
        goto LABEL_26;
      v6 = pSecurityDescriptora;
      v9 = RegGetKeySecurity(handle, 4u, pSecurityDescriptora, &cbSecurityDescriptor);
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v7 >= 0 )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      SecurityDescriptorDacl = GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted);
      v7 = ResultFromWin32Bool(SecurityDescriptorDacl);
      if ( v7 >= 0 )
      {
        pAce = 0;
        GetAce(pDacl, pDacl->AceCount - 1, &pAce);
        pSecurityDescriptora = 0;
        v11 = (unsigned __int16)(*((_WORD *)pAce + 1) + 8);
        v7 = ResultFromHeapAlloc((unsigned __int16)(*((_WORD *)pAce + 1) + 8), &pSecurityDescriptora);
        if ( v7 >= 0 )
        {
          v12 = v11;
          v13 = (struct _ACL *)pSecurityDescriptora;
          v14 = InitializeAcl((PACL)pSecurityDescriptora, v12, 2u);
          v7 = ResultFromWin32Bool(v14);
          if ( v7 >= 0 )
          {
            v15 = AddAce(v13, 2u, 0, pAce, *((unsigned __int16 *)pAce + 1));
            v7 = ResultFromWin32Bool(v15);
            if ( v7 >= 0 )
            {
              pcCountOfExplicitEntries = 0;
              pListOfExplicitEntries = 0;
              ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(
                                          v13,
                                          &pcCountOfExplicitEntries,
                                          &pListOfExplicitEntries);
              v7 = ExplicitEntriesFromAclW;
              if ( ExplicitEntriesFromAclW > 0 )
                v7 = (unsigned __int16)ExplicitEntriesFromAclW | 0x80070000;
              if ( v7 >= 0 )
              {
                v17 = GetSecurityDescriptorDacl(v6, &bDaclPresent, &pDacl, &bDaclDefaulted);
                v7 = ResultFromWin32Bool(v17);
                if ( v7 >= 0 && bDaclPresent && pDacl )
                {
                  pSecurityDescriptora = 0;
                  v18 = SetEntriesInAclW(
                          pcCountOfExplicitEntries,
                          pListOfExplicitEntries,
                          pDacl,
                          (PACL *)&pSecurityDescriptora);
                  v7 = v18;
                  if ( v18 > 0 )
                    v7 = (unsigned __int16)v18 | 0x80070000;
                  if ( v7 >= 0 )
                  {
                    v19 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, (PACL)pSecurityDescriptora, 0);
                    v7 = v19;
                    if ( v19 > 0 )
                      v7 = (unsigned __int16)v19 | 0x80070000;
                    LocalFree(pSecurityDescriptora);
                  }
                }
              }
            }
          }
          ResultFromHeapFree(v13);
        }
      }
    }
  }
LABEL_26:
  ResultFromHeapFree(v6);
  ResultFromHeapFree(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180043440  push    rbp
0x180043442  push    rbx
0x180043443  push    rsi
0x180043444  push    rdi
0x180043445  push    r12
0x180043447  push    r14
0x180043449  push    r15
0x18004344b  mov     rbp, rsp
0x18004344e  sub     rsp, 70h
0x180043452  mov     r14, rcx
0x180043455  mov     rsi, rdx
0x180043458  mov     ecx, 200h; dwBytes
0x18004345d  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x180043461  xor     r15d, r15d
0x180043464  mov     [rbp+cbSecurityDescriptor], ecx
0x180043467  mov     [rbp+pSecurityDescriptor], r15
0x18004346b  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180043470  mov     rdi, [rbp+pSecurityDescriptor]
0x180043474  mov     ebx, eax
0x180043476  test    eax, eax
0x180043478  js      loc_180043683
0x18004347e  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180043482  mov     r8, rdi; pSecurityDescriptor
0x180043485  lea     edx, [r15+4]; SecurityInformation
0x180043489  mov     rcx, r14; hKey
0x18004348c  call    cs:__imp_RegGetKeySecurity
0x180043492  mov     ebx, eax
0x180043494  mov     r12d, 80070000h
0x18004349a  test    eax, eax
0x18004349c  jle     short loc_1800434A4
0x18004349e  movzx   ebx, ax
0x1800434a1  or      ebx, r12d
0x1800434a4  cmp     ebx, 8007007Ah
0x1800434aa  jnz     short loc_1800434EE
0x1800434ac  mov     edx, [rbp+cbSecurityDescriptor]; dwBytes
0x1800434af  lea     r8, [rbp+pSecurityDescriptor]; void **
0x1800434b3  mov     rcx, rdi; lpMem
0x1800434b6  mov     [rbp+pSecurityDescriptor], r15
0x1800434ba  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800434bf  mov     ebx, eax
0x1800434c1  test    eax, eax
0x1800434c3  js      loc_180043683
0x1800434c9  mov     rdi, [rbp+pSecurityDescriptor]
0x1800434cd  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800434d1  mov     r8, rdi; pSecurityDescriptor
0x1800434d4  mov     edx, 4; SecurityInformation
0x1800434d9  mov     rcx, r14; hKey
0x1800434dc  call    cs:__imp_RegGetKeySecurity
0x1800434e2  mov     ebx, eax
0x1800434e4  test    eax, eax
0x1800434e6  jle     short loc_1800434EE
0x1800434e8  movzx   ebx, ax
0x1800434eb  or      ebx, r12d
0x1800434ee  test    ebx, ebx
0x1800434f0  js      loc_180043683
0x1800434f6  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800434fa  mov     [rbp+pDacl], r15
0x1800434fe  lea     r8, [rbp+pDacl]; pDacl
0x180043502  mov     [rbp+bDaclPresent], r15d
0x180043506  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004350a  mov     [rbp+bDaclDefaulted], r15d
0x18004350e  mov     rcx, rsi; pSecurityDescriptor
0x180043511  call    cs:__imp_GetSecurityDescriptorDacl
0x180043517  mov     ecx, eax; int
0x180043519  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18004351e  mov     ebx, eax
0x180043520  test    eax, eax
0x180043522  js      loc_180043683
0x180043528  mov     rcx, [rbp+pDacl]; pAcl
0x18004352c  lea     r8, [rbp+pAce]; pAce
0x180043530  mov     [rbp+pAce], r15
0x180043534  movzx   edx, word ptr [rcx+4]
0x180043538  dec     edx; dwAceIndex
0x18004353a  call    cs:__imp_GetAce
0x180043540  mov     rax, [rbp+pAce]
0x180043544  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x180043548  mov     [rbp+pSecurityDescriptor], r15
0x18004354c  movzx   ecx, word ptr [rax+2]
0x180043550  add     cx, 8
0x180043554  movzx   esi, cx
0x180043557  mov     ecx, esi; dwBytes
0x180043559  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x18004355e  mov     ebx, eax
0x180043560  test    eax, eax
0x180043562  js      loc_180043683
0x180043568  mov     edx, esi; nAclLength
0x18004356a  mov     r8d, 2; dwAclRevision
0x180043570  mov     rsi, [rbp+pSecurityDescriptor]
0x180043574  mov     rcx, rsi; pAcl
0x180043577  call    cs:__imp_InitializeAcl
0x18004357d  mov     ecx, eax; int
0x18004357f  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180043584  mov     ebx, eax
0x180043586  test    eax, eax
0x180043588  js      loc_18004367B
0x18004358e  mov     r9, [rbp+pAce]; pAceList
0x180043592  xor     r8d, r8d; dwStartingAceIndex
0x180043595  mov     rcx, rsi; pAcl
0x180043598  movzx   eax, word ptr [r9+2]
0x18004359d  lea     edx, [r8+2]; dwAceRevision
0x1800435a1  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1800435a5  call    cs:__imp_AddAce
0x1800435ab  mov     ecx, eax; int
0x1800435ad  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800435b2  mov     ebx, eax
0x1800435b4  test    eax, eax
0x1800435b6  js      loc_18004367B
0x1800435bc  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800435c0  mov     [rbp+pcCountOfExplicitEntries], r15d
0x1800435c4  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x1800435c8  mov     [rbp+pListOfExplicitEntries], r15
0x1800435cc  mov     rcx, rsi; pacl
0x1800435cf  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800435d5  mov     ebx, eax
0x1800435d7  test    eax, eax
0x1800435d9  jle     short loc_1800435E1
0x1800435db  movzx   ebx, ax
0x1800435de  or      ebx, r12d
0x1800435e1  test    ebx, ebx
0x1800435e3  js      loc_18004367B
0x1800435e9  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800435ed  mov     rcx, rdi; pSecurityDescriptor
0x1800435f0  lea     r8, [rbp+pDacl]; pDacl
0x1800435f4  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800435f8  call    cs:__imp_GetSecurityDescriptorDacl
0x1800435fe  mov     ecx, eax; int
0x180043600  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180043605  mov     ebx, eax
0x180043607  test    eax, eax
0x180043609  js      short loc_18004367B
0x18004360b  cmp     [rbp+bDaclPresent], r15d
0x18004360f  jz      short loc_18004367B
0x180043611  mov     r8, [rbp+pDacl]; OldAcl
0x180043615  test    r8, r8
0x180043618  jz      short loc_18004367B
0x18004361a  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004361e  lea     r9, [rbp+pSecurityDescriptor]; NewAcl
0x180043622  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x180043625  mov     [rbp+pSecurityDescriptor], r15
0x180043629  call    cs:__imp_SetEntriesInAclW
0x18004362f  mov     ebx, eax
0x180043631  test    eax, eax
0x180043633  jle     short loc_18004363B
0x180043635  movzx   ebx, ax
0x180043638  or      ebx, r12d
0x18004363b  test    ebx, ebx
0x18004363d  js      short loc_18004367B
0x18004363f  mov     rax, [rbp+pSecurityDescriptor]
0x180043643  xor     r9d, r9d; psidOwner
0x180043646  mov     [rsp+70h+pSacl], r15; pSacl
0x18004364b  mov     rcx, r14; handle
0x18004364e  mov     [rsp+70h+var_48], rax; pDacl
0x180043653  mov     qword ptr [rsp+70h+nAceListLength], r15; psidGroup
0x180043658  lea     edx, [r9+4]; ObjectType
0x18004365c  mov     r8d, edx; SecurityInfo
0x18004365f  call    cs:__imp_SetSecurityInfo
0x180043665  mov     ebx, eax
0x180043667  test    eax, eax
0x180043669  jle     short loc_180043671
0x18004366b  movzx   ebx, ax
0x18004366e  or      ebx, r12d
0x180043671  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x180043675  call    cs:__imp_LocalFree
0x18004367b  mov     rcx, rsi; lpMem
0x18004367e  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180043683  mov     rcx, rdi; lpMem
0x180043686  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18004368b  xor     ecx, ecx; lpMem
0x18004368d  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180043692  mov     eax, ebx
0x180043694  add     rsp, 70h
0x180043698  pop     r15
0x18004369a  pop     r14
0x18004369c  pop     r12
0x18004369e  pop     rdi
0x18004369f  pop     rsi
0x1800436a0  pop     rbx
0x1800436a1  pop     rbp
0x1800436a2  retn
```
