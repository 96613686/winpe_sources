# SetSecurityAttributes(_SECURITY_ATTRIBUTES *,_EXPLICIT_ACCESS_W * const,void *,void *,void *,_ACL * *,void * *)

- ea: `0x14000b3c0`
- end: `0x14000b64e`
- name: `?SetSecurityAttributes@@YAJPEAU_SECURITY_ATTRIBUTES@@QEAU_EXPLICIT_ACCESS_W@@PEAX22PEAPEAU_ACL@@PEAPEAX@Z`
- size: `654`
- prototype: `int(struct _SECURITY_ATTRIBUTES *, struct _EXPLICIT_ACCESS_W *const, void *, void *, void *, struct _ACL **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000a798`

## callees

- `0x140001af3`
- `0x14000b3c0`
- `0x14000d2a8`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000b58d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000b58d`
- `ADVAPI32!CopySid` at `0x14000b4c0`
- `ADVAPI32!CopySid` at `0x14000b4c0`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b435`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b484`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b512`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b435`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b484`
- `ADVAPI32!CreateWellKnownSid` at `0x14000b512`
- `ADVAPI32!SetEntriesInAclW` at `0x14000b559`
- `ADVAPI32!SetEntriesInAclW` at `0x14000b559`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000b5a8`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000b5a8`
- `KERNEL32!LocalAlloc` at `0x14000b56f`
- `KERNEL32!LocalAlloc` at `0x14000b56f`
- `KERNEL32!LocalFree` at `0x14000b5fc`
- `KERNEL32!LocalFree` at `0x14000b617`
- `KERNEL32!LocalFree` at `0x14000b62e`
- `KERNEL32!LocalFree` at `0x14000b5fc`
- `KERNEL32!LocalFree` at `0x14000b617`
- `KERNEL32!LocalFree` at `0x14000b62e`
- `KERNEL32!GetLastError` at `0x14000b5d9`
- `KERNEL32!GetLastError` at `0x14000b5d9`
- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x14000b4a0`
- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x14000b4a0`

## pseudocode

```c
__int64 __fastcall SetSecurityAttributes(
        struct _SECURITY_ATTRIBUTES *a1,
        struct _EXPLICIT_ACCESS_W *const a2,
        void *a3,
        void *a4,
        WCHAR *pSid,
        struct _ACL **NewAcl,
        void **a7)
{
  unsigned int InstallScopeFromIntegrityLevel; // ebx
  bool v12; // zf
  BOOL v13; // eax
  signed int LastError; // eax
  bool v15; // cc
  HLOCAL v16; // rax
  __int64 result; // rax
  DWORD cbSid; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-14h] BYREF
  PSID pSourceSid; // [rsp+28h] [rbp-10h] BYREF

  cbSid = 68;
  v19 = 0;
  pSourceSid = 0;
  InstallScopeFromIntegrityLevel = GetInstallScopeFromIntegrityLevel(&v19);
  if ( !InstallScopeFromIntegrityLevel )
  {
    *NewAcl = 0;
    *a7 = 0;
    memset_0(a2, 0, 0x90u);
    if ( !CreateWellKnownSid(WinAuthenticatedUserSid, 0, a3, &cbSid) )
    {
LABEL_16:
      LastError = GetLastError();
      InstallScopeFromIntegrityLevel = LastError;
      v15 = LastError <= 0;
LABEL_17:
      if ( !v15 )
        InstallScopeFromIntegrityLevel = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_19;
    }
    v12 = v19 == 1;
    a2->grfAccessPermissions = -1610612736;
    a2->grfAccessMode = SET_ACCESS;
    a2->grfInheritance = 3;
    a2->Trustee.TrusteeForm = TRUSTEE_IS_SID;
    a2->Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    a2->Trustee.ptstrName = (LPWCH)a3;
    cbSid = 68;
    if ( v12 )
    {
      v13 = CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, a4, &cbSid);
LABEL_8:
      if ( v13 )
      {
        a2[1].grfAccessPermissions = 270467072;
        a2[1].grfInheritance = 3;
        a2[1].grfAccessMode = SET_ACCESS;
        a2[1].Trustee.TrusteeForm = TRUSTEE_IS_SID;
        a2[1].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
        a2[1].Trustee.ptstrName = (LPWCH)a4;
        cbSid = 68;
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
        {
          a2[2].grfAccessPermissions = 270467072;
          a2[2].grfAccessMode = SET_ACCESS;
          a2[2].grfInheritance = 3;
          a2[2].Trustee.TrusteeForm = TRUSTEE_IS_SID;
          a2[2].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
          a2[2].Trustee.ptstrName = pSid;
          if ( !SetEntriesInAclW(3u, a2, 0, NewAcl) )
          {
            v16 = LocalAlloc(0x40u, 0x28u);
            *a7 = v16;
            if ( v16 )
            {
              if ( InitializeSecurityDescriptor(v16, 1u) && SetSecurityDescriptorDacl(*a7, 1, *NewAcl, 0) )
              {
                a1->lpSecurityDescriptor = *a7;
                result = 0;
                a1->nLength = 24;
                a1->bInheritHandle = 0;
                return result;
              }
            }
          }
        }
      }
      goto LABEL_16;
    }
    if ( v19 == 2 )
    {
      LastError = GetCurrentUserSid(&pSourceSid);
      InstallScopeFromIntegrityLevel = LastError;
      v15 = LastError <= 0;
      if ( LastError )
        goto LABEL_17;
      v13 = CopySid(cbSid, a4, pSourceSid);
      goto LABEL_8;
    }
    InstallScopeFromIntegrityLevel = -2147467263;
  }
LABEL_19:
  if ( *NewAcl )
  {
    LocalFree(*NewAcl);
    *NewAcl = 0;
  }
  if ( *a7 )
  {
    LocalFree(*a7);
    *a7 = 0;
  }
  LocalFree(pSourceSid);
  return InstallScopeFromIntegrityLevel;
}

```

## disassembly

```asm
0x14000b3c0  push    rbp
0x14000b3c2  push    rbx
0x14000b3c3  push    rsi
0x14000b3c4  push    rdi
0x14000b3c5  push    r12
0x14000b3c7  push    r13
0x14000b3c9  push    r14
0x14000b3cb  push    r15
0x14000b3cd  mov     rbp, rsp
0x14000b3d0  sub     rsp, 38h
0x14000b3d4  mov     r15, rcx
0x14000b3d7  mov     [rbp+cbSid], 44h ; 'D'
0x14000b3de  lea     rcx, [rbp+var_14]; unsigned int *
0x14000b3e2  mov     [rbp+var_14], 0
0x14000b3e9  mov     r13, r9
0x14000b3ec  mov     [rbp+pSourceSid], 0
0x14000b3f4  mov     r12, r8
0x14000b3f7  mov     rdi, rdx
0x14000b3fa  call    ?GetInstallScopeFromIntegrityLevel@@YAJPEAK@Z; GetInstallScopeFromIntegrityLevel(ulong *)
0x14000b3ff  mov     rsi, [rbp+arg_30]
0x14000b403  mov     ebx, eax
0x14000b405  mov     r14, [rbp+NewAcl]
0x14000b409  test    eax, eax
0x14000b40b  jnz     loc_14000B5F4
0x14000b411  xor     ebx, ebx
0x14000b413  xor     edx, edx; Val
0x14000b415  mov     r8d, 90h; Size
0x14000b41b  mov     [r14], rbx
0x14000b41e  mov     rcx, rdi; void *
0x14000b421  mov     [rsi], rbx
0x14000b424  call    memset_0
0x14000b429  lea     r9, [rbp+cbSid]; cbSid
0x14000b42d  mov     r8, r12; pSid
0x14000b430  xor     edx, edx; DomainSid
0x14000b432  lea     ecx, [rbx+11h]; WellKnownSidType
0x14000b435  call    cs:__imp_CreateWellKnownSid
0x14000b43c  nop     dword ptr [rax+rax+00h]
0x14000b441  test    eax, eax
0x14000b443  jz      loc_14000B5D9
0x14000b449  cmp     [rbp+var_14], 1
0x14000b44d  mov     dword ptr [rdi], 0A0000000h
0x14000b453  mov     dword ptr [rdi+4], 2
0x14000b45a  mov     dword ptr [rdi+8], 3
0x14000b461  mov     [rdi+1Ch], ebx
0x14000b464  mov     dword ptr [rdi+20h], 5
0x14000b46b  mov     [rdi+28h], r12
0x14000b46f  mov     [rbp+cbSid], 44h ; 'D'
0x14000b476  jnz     short loc_14000B492
0x14000b478  lea     r9, [rbp+cbSid]; cbSid
0x14000b47c  mov     r8, r13; pSid
0x14000b47f  xor     edx, edx; DomainSid
0x14000b481  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x14000b484  call    cs:__imp_CreateWellKnownSid
0x14000b48b  nop     dword ptr [rax+rax+00h]
0x14000b490  jmp     short loc_14000B4CC
0x14000b492  cmp     [rbp+var_14], 2
0x14000b496  jnz     loc_14000B5D2
0x14000b49c  lea     rcx, [rbp+pSourceSid]
0x14000b4a0  call    cs:__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z; GetCurrentUserSid(void * *)
0x14000b4a7  nop     dword ptr [rax+rax+00h]
0x14000b4ac  mov     ebx, eax
0x14000b4ae  test    eax, eax
0x14000b4b0  jnz     loc_14000B5E9
0x14000b4b6  mov     r8, [rbp+pSourceSid]; pSourceSid
0x14000b4ba  mov     rdx, r13; pDestinationSid
0x14000b4bd  mov     ecx, [rbp+cbSid]; nDestinationSidLength
0x14000b4c0  call    cs:__imp_CopySid
0x14000b4c7  nop     dword ptr [rax+rax+00h]
0x14000b4cc  test    eax, eax
0x14000b4ce  jz      loc_14000B5D9
0x14000b4d4  mov     rbx, [rbp+pSid]
0x14000b4d8  lea     r9, [rbp+cbSid]; cbSid
0x14000b4dc  xor     edx, edx; DomainSid
0x14000b4de  mov     dword ptr [rdi+30h], 101F0000h
0x14000b4e5  mov     r12d, 2
0x14000b4eb  mov     dword ptr [rdi+38h], 3
0x14000b4f2  mov     r8, rbx; pSid
0x14000b4f5  mov     [rdi+34h], r12d
0x14000b4f9  mov     dword ptr [rdi+4Ch], 0
0x14000b500  lea     ecx, [rdx+16h]; WellKnownSidType
0x14000b503  mov     [rdi+50h], r12d
0x14000b507  mov     [rdi+58h], r13
0x14000b50b  mov     [rbp+cbSid], 44h ; 'D'
0x14000b512  call    cs:__imp_CreateWellKnownSid
0x14000b519  nop     dword ptr [rax+rax+00h]
0x14000b51e  test    eax, eax
0x14000b520  jz      loc_14000B5D9
0x14000b526  lea     eax, [r12+1]
0x14000b52b  mov     dword ptr [rdi+60h], 101F0000h
0x14000b532  mov     ecx, eax; cCountOfExplicitEntries
0x14000b534  mov     [rdi+64h], r12d
0x14000b538  mov     r9, r14; NewAcl
0x14000b53b  mov     [rdi+68h], eax
0x14000b53e  xor     r8d, r8d; OldAcl
0x14000b541  mov     dword ptr [rdi+7Ch], 0
0x14000b548  mov     rdx, rdi; pListOfExplicitEntries
0x14000b54b  mov     [rdi+80h], r12d
0x14000b552  mov     [rdi+88h], rbx
0x14000b559  call    cs:__imp_SetEntriesInAclW
0x14000b560  nop     dword ptr [rax+rax+00h]
0x14000b565  test    eax, eax
0x14000b567  jnz     short loc_14000B5D9
0x14000b569  lea     edx, [rax+28h]; uBytes
0x14000b56c  lea     ecx, [rax+40h]; uFlags
0x14000b56f  call    cs:__imp_LocalAlloc
0x14000b576  nop     dword ptr [rax+rax+00h]
0x14000b57b  mov     [rsi], rax
0x14000b57e  test    rax, rax
0x14000b581  jz      short loc_14000B5D9
0x14000b583  lea     ebx, [r12-1]
0x14000b588  mov     rcx, rax; pSecurityDescriptor
0x14000b58b  mov     edx, ebx; dwRevision
0x14000b58d  call    cs:__imp_InitializeSecurityDescriptor
0x14000b594  nop     dword ptr [rax+rax+00h]
0x14000b599  test    eax, eax
0x14000b59b  jz      short loc_14000B5D9
0x14000b59d  mov     r8, [r14]; pDacl
0x14000b5a0  xor     r9d, r9d; bDaclDefaulted
0x14000b5a3  mov     rcx, [rsi]; pSecurityDescriptor
0x14000b5a6  mov     edx, ebx; bDaclPresent
0x14000b5a8  call    cs:__imp_SetSecurityDescriptorDacl
0x14000b5af  nop     dword ptr [rax+rax+00h]
0x14000b5b4  test    eax, eax
0x14000b5b6  jz      short loc_14000B5D9
0x14000b5b8  mov     rax, [rsi]
0x14000b5bb  mov     [r15+8], rax
0x14000b5bf  xor     eax, eax
0x14000b5c1  mov     dword ptr [r15], 18h
0x14000b5c8  mov     dword ptr [r15+10h], 0
0x14000b5d0  jmp     short loc_14000B63C
0x14000b5d2  mov     ebx, 80004001h
0x14000b5d7  jmp     short loc_14000B5F4
0x14000b5d9  call    cs:__imp_GetLastError
0x14000b5e0  nop     dword ptr [rax+rax+00h]
0x14000b5e5  mov     ebx, eax
0x14000b5e7  test    eax, eax
0x14000b5e9  jle     short loc_14000B5F4
0x14000b5eb  movzx   ebx, ax
0x14000b5ee  or      ebx, 80070000h
0x14000b5f4  mov     rcx, [r14]; hMem
0x14000b5f7  test    rcx, rcx
0x14000b5fa  jz      short loc_14000B60F
0x14000b5fc  call    cs:__imp_LocalFree
0x14000b603  nop     dword ptr [rax+rax+00h]
0x14000b608  mov     qword ptr [r14], 0
0x14000b60f  mov     rcx, [rsi]; hMem
0x14000b612  test    rcx, rcx
0x14000b615  jz      short loc_14000B62A
0x14000b617  call    cs:__imp_LocalFree
0x14000b61e  nop     dword ptr [rax+rax+00h]
0x14000b623  mov     qword ptr [rsi], 0
0x14000b62a  mov     rcx, [rbp+pSourceSid]; hMem
0x14000b62e  call    cs:__imp_LocalFree
0x14000b635  nop     dword ptr [rax+rax+00h]
0x14000b63a  mov     eax, ebx
0x14000b63c  add     rsp, 38h
0x14000b640  pop     r15
0x14000b642  pop     r14
0x14000b644  pop     r13
0x14000b646  pop     r12
0x14000b648  pop     rdi
0x14000b649  pop     rsi
0x14000b64a  pop     rbx
0x14000b64b  pop     rbp
0x14000b64c  retn
```
