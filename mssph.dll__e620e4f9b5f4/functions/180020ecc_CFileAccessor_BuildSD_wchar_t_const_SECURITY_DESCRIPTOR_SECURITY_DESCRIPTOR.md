# CFileAccessor::BuildSD(wchar_t const *,_SECURITY_DESCRIPTOR *,_SECURITY_DESCRIPTOR * *)

- ea: `0x180020ecc`
- end: `0x180021162`
- name: `?BuildSD@CFileAccessor@@AEAAJPEB_WPEAU_SECURITY_DESCRIPTOR@@PEAPEAU2@@Z`
- size: `662`
- prototype: `__int64 __fastcall(CFileAccessor *this, const wchar_t *, struct _SECURITY_DESCRIPTOR *, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x180005eb0`
- `0x1800101c0`
- `0x180010250`
- `0x180020ecc`
- `0x1800219a0`
- `0x180024c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210ad`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18002103f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18002103f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800210a3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800210f5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800210a3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800210f5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180021080`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180021080`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18002106a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18002106a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180021055`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180021055`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002102a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002102a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180021011`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180021011`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021119`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800210d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800210d5`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180020f87`
- `api-ms-win-security-trustee-l1-1-1!BuildExplicitAccessWithNameW` at `0x180020f87`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180020fc5`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180020fc5`

## pseudocode

```c
__int64 __fastcall CFileAccessor::BuildSD(
        CFileAccessor *this,
        const wchar_t *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        struct _SECURITY_DESCRIPTOR **a4)
{
  struct _SECURITY_DESCRIPTOR **v4; // rdi
  ULONG v5; // r15d
  struct _SECURITY_DESCRIPTOR *v6; // r13
  int CanAccessAndDecrypt; // eax
  ULONG v8; // r12d
  signed int Error; // esi
  struct _EXPLICIT_ACCESS_W *v10; // r14
  unsigned __int64 v11; // rax
  struct tagBLOB *v12; // r13
  struct _EXPLICIT_ACCESS_W *v13; // rbx
  __int64 v14; // rdi
  signed int v15; // eax
  signed int LastError; // eax
  struct _SECURITY_DESCRIPTOR *v17; // rax
  struct _SECURITY_DESCRIPTOR *v18; // rbx
  DWORD dwBufferLength; // [rsp+38h] [rbp-49h] BYREF
  ULONG cCountOfExplicitEntries; // [rsp+3Ch] [rbp-45h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp-41h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+44h] [rbp-3Dh] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-39h] BYREF
  struct tagBLOB *v25; // [rsp+50h] [rbp-31h] BYREF
  PSID pOwner; // [rsp+58h] [rbp-29h] BYREF
  PSID pGroup; // [rsp+60h] [rbp-21h] BYREF
  struct tagBLOB *v28; // [rsp+68h] [rbp-19h] BYREF
  ULONG v29; // [rsp+70h] [rbp-11h]
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v31; // [rsp+98h] [rbp+17h]

  v4 = a4;
  v5 = 0;
  v25 = 0;
  cCountOfExplicitEntries = 0;
  v6 = a3;
  CanAccessAndDecrypt = CFileAccessor::GetUsersWhoCanAccessAndDecrypt(this, a2, a3, &cCountOfExplicitEntries, &v25);
  v8 = cCountOfExplicitEntries;
  Error = CanAccessAndDecrypt;
  v10 = 0;
  if ( CanAccessAndDecrypt < 0 )
    goto LABEL_6;
  v11 = 48LL * cCountOfExplicitEntries;
  if ( !is_mul_ok(cCountOfExplicitEntries, 0x30u) )
    v11 = -1;
  v10 = (struct _EXPLICIT_ACCESS_W *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
LABEL_6:
    if ( Error >= 0 )
    {
      v12 = v25;
      while ( v5 < v8 )
      {
        v13 = &v10[v5];
        BuildExplicitAccessWithNameW(v13, 0, 0x120089u, GRANT_ACCESS, 0);
        v14 = v5;
        v13->Trustee.TrusteeForm = TRUSTEE_IS_SID;
        ++v5;
        v13->Trustee.ptstrName = (LPWCH)v12[v14].pBlobData;
      }
      v6 = a3;
      v4 = a4;
    }
    NewAcl = 0;
    if ( Error >= 0 )
    {
      v15 = SetEntriesInAclW(v8, v10, 0, &NewAcl);
      Error = v15;
      if ( v15 )
      {
        if ( v15 > 0 )
          Error = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
        Error = 0;
      }
    }
  }
  else
  {
    Error = -2147024882;
    NewAcl = 0;
  }
  pOwner = 0;
  bOwnerDefaulted = 0;
  pGroup = 0;
  bGroupDefaulted = 0;
  v31 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  if ( Error >= 0
    && (!InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
     || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0)
     || !GetSecurityDescriptorOwner(v6, &pOwner, &bOwnerDefaulted)
     || !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, bOwnerDefaulted)
     || !GetSecurityDescriptorGroup(v6, &pGroup, &bGroupDefaulted)
     || !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, bGroupDefaulted)) )
  {
    Error = ResultFromLastError();
  }
  dwBufferLength = 0;
  if ( Error >= 0 )
  {
    if ( MakeSelfRelativeSD(pSecurityDescriptor, 0, &dwBufferLength)
      || (LastError = GetLastError(), LastError == 122)
      || (LastError > 0 ? (Error = (unsigned __int16)LastError | 0x80070000) : (Error = LastError), Error >= 0) )
    {
      v17 = (struct _SECURITY_DESCRIPTOR *)LocalAlloc(0x40u, dwBufferLength);
      v18 = v17;
      if ( v17 )
      {
        if ( MakeSelfRelativeSD(pSecurityDescriptor, v17, &dwBufferLength)
          || (Error = ResultFromLastError(), Error >= 0) )
        {
          *v4 = v18;
        }
      }
      else
      {
        Error = -2147024882;
      }
    }
  }
  operator delete(v10);
  LocalFree(NewAcl);
  v28 = 0;
  v29 = 0;
  CSidContainer::FreeBlobs((CSidContainer *)&v28);
  v28 = v25;
  v29 = v8;
  CSidContainer::FreeBlobs((CSidContainer *)&v28);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180020ecc  mov     rax, rsp
0x180020ecf  mov     [rax+8], rbx
0x180020ed3  mov     [rax+20h], r9
0x180020ed7  mov     [rax+18h], r8
0x180020edb  push    rbp
0x180020edc  push    rsi
0x180020edd  push    rdi
0x180020ede  push    r12
0x180020ee0  push    r13
0x180020ee2  push    r14
0x180020ee4  push    r15
0x180020ee6  lea     rbp, [rax-5Fh]
0x180020eea  sub     rsp, 0A0h
0x180020ef1  mov     rdi, r9
0x180020ef4  lea     rax, [rbp+57h+var_88]
0x180020ef8  xor     r15d, r15d
0x180020efb  mov     [rsp+20h], rax; struct tagBLOB **
0x180020f00  lea     r9, [rbp+57h+cCountOfExplicitEntries]; unsigned int *
0x180020f04  mov     [rbp+57h+var_88], r15
0x180020f08  mov     [rbp+57h+cCountOfExplicitEntries], r15d
0x180020f0c  mov     r13, r8
0x180020f0f  call    ?GetUsersWhoCanAccessAndDecrypt@CFileAccessor@@AEAAJPEB_WPEAXPEAKPEAPEAUtagBLOB@@@Z; CFileAccessor::GetUsersWhoCanAccessAndDecrypt(wchar_t const *,void *,ulong *,tagBLOB * *)
0x180020f14  mov     r12d, [rbp+57h+cCountOfExplicitEntries]
0x180020f18  mov     esi, eax
0x180020f1a  mov     r14d, r15d
0x180020f1d  test    eax, eax
0x180020f1f  js      short loc_180020F55
0x180020f21  lea     rcx, [r15-1]
0x180020f25  lea     eax, [r15+30h]
0x180020f29  mul     r12
0x180020f2c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020f33  cmovb   rax, rcx
0x180020f37  mov     rcx, rax; unsigned __int64
0x180020f3a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020f3f  mov     r14, rax
0x180020f42  test    rax, rax
0x180020f45  jnz     short loc_180020F55
0x180020f47  mov     esi, 8007000Eh
0x180020f4c  mov     [rbp+57h+NewAcl], r15
0x180020f50  jmp     loc_180020FE1
0x180020f55  test    esi, esi
0x180020f57  js      short loc_180020FAD
0x180020f59  mov     r13, [rbp+57h+var_88]
0x180020f5d  cmp     r15d, r12d
0x180020f60  jnb     short loc_180020FA5
0x180020f62  xor     edx, edx; pTrusteeName
0x180020f64  mov     edi, r15d
0x180020f67  mov     r8d, 120089h; AccessPermissions
0x180020f6d  mov     dword ptr [rsp+20h], 0; Inheritance
0x180020f75  lea     rbx, [rdi+rdi*2]
0x180020f79  shl     rbx, 4
0x180020f7d  lea     r9d, [rdx+1]; AccessMode
0x180020f81  add     rbx, r14
0x180020f84  mov     rcx, rbx; pExplicitAccess
0x180020f87  call    cs:__imp_BuildExplicitAccessWithNameW
0x180020f8d  add     rdi, rdi
0x180020f90  mov     dword ptr [rbx+1Ch], 0
0x180020f97  inc     r15d
0x180020f9a  mov     rax, [r13+rdi*8+8]
0x180020f9f  mov     [rbx+28h], rax
0x180020fa3  jmp     short loc_180020F5D
0x180020fa5  mov     r13, [rbp+57h+arg_10]
0x180020fa9  mov     rdi, [rbp+57h+arg_18]
0x180020fad  xor     r15d, r15d
0x180020fb0  mov     [rbp+57h+NewAcl], r15
0x180020fb4  test    esi, esi
0x180020fb6  js      short loc_180020FE1
0x180020fb8  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180020fbc  xor     r8d, r8d; OldAcl
0x180020fbf  mov     rdx, r14; pListOfExplicitEntries
0x180020fc2  mov     ecx, r12d; cCountOfExplicitEntries
0x180020fc5  call    cs:__imp_SetEntriesInAclW
0x180020fcb  mov     esi, eax
0x180020fcd  test    eax, eax
0x180020fcf  jnz     short loc_180020FD6
0x180020fd1  mov     esi, r15d
0x180020fd4  jmp     short loc_180020FE1
0x180020fd6  jle     short loc_180020FE1
0x180020fd8  movzx   esi, ax
0x180020fdb  or      esi, 80070000h
0x180020fe1  xor     eax, eax
0x180020fe3  mov     [rbp+57h+pOwner], r15
0x180020fe7  mov     [rbp+57h+bOwnerDefaulted], r15d
0x180020feb  xorps   xmm0, xmm0
0x180020fee  mov     [rbp+57h+pGroup], r15
0x180020ff2  mov     [rbp+57h+bGroupDefaulted], r15d
0x180020ff6  mov     [rbp+57h+var_40], rax
0x180020ffa  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180020ffe  movups  [rbp+57h+var_50], xmm0
0x180021002  test    esi, esi
0x180021004  js      loc_180021091
0x18002100a  lea     edx, [rax+1]; dwRevision
0x18002100d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180021011  call    cs:__imp_InitializeSecurityDescriptor
0x180021017  test    eax, eax
0x180021019  jz      short loc_18002108A
0x18002101b  mov     r8, [rbp+57h+NewAcl]; pDacl
0x18002101f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180021023  xor     r9d, r9d; bDaclDefaulted
0x180021026  lea     edx, [r9+1]; bDaclPresent
0x18002102a  call    cs:__imp_SetSecurityDescriptorDacl
0x180021030  test    eax, eax
0x180021032  jz      short loc_18002108A
0x180021034  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180021038  mov     rcx, r13; pSecurityDescriptor
0x18002103b  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18002103f  call    cs:__imp_GetSecurityDescriptorOwner
0x180021045  test    eax, eax
0x180021047  jz      short loc_18002108A
0x180021049  mov     r8d, [rbp+57h+bOwnerDefaulted]; bOwnerDefaulted
0x18002104d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180021051  mov     rdx, [rbp+57h+pOwner]; pOwner
0x180021055  call    cs:__imp_SetSecurityDescriptorOwner
0x18002105b  test    eax, eax
0x18002105d  jz      short loc_18002108A
0x18002105f  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x180021063  mov     rcx, r13; pSecurityDescriptor
0x180021066  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18002106a  call    cs:__imp_GetSecurityDescriptorGroup
0x180021070  test    eax, eax
0x180021072  jz      short loc_18002108A
0x180021074  mov     r8d, [rbp+57h+bGroupDefaulted]; bGroupDefaulted
0x180021078  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002107c  mov     rdx, [rbp+57h+pGroup]; pGroup
0x180021080  call    cs:__imp_SetSecurityDescriptorGroup
0x180021086  test    eax, eax
0x180021088  jnz     short loc_180021091
0x18002108a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002108f  mov     esi, eax
0x180021091  mov     [rbp+57h+dwBufferLength], r15d
0x180021095  test    esi, esi
0x180021097  js      short loc_18002110D
0x180021099  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x18002109d  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18002109f  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800210a3  call    cs:__imp_MakeSelfRelativeSD
0x1800210a9  test    eax, eax
0x1800210ab  jnz     short loc_1800210CD
0x1800210ad  call    cs:__imp_GetLastError
0x1800210b3  cmp     eax, 7Ah ; 'z'
0x1800210b6  jz      short loc_1800210CD
0x1800210b8  test    eax, eax
0x1800210ba  jg      short loc_1800210C0
0x1800210bc  mov     esi, eax
0x1800210be  jmp     short loc_1800210C9
0x1800210c0  movzx   esi, ax
0x1800210c3  or      esi, 80070000h
0x1800210c9  test    esi, esi
0x1800210cb  js      short loc_18002110D
0x1800210cd  mov     edx, [rbp+57h+dwBufferLength]; uBytes
0x1800210d0  mov     ecx, 40h ; '@'; uFlags
0x1800210d5  call    cs:__imp_LocalAlloc
0x1800210db  mov     rbx, rax
0x1800210de  test    rax, rax
0x1800210e1  jnz     short loc_1800210EA
0x1800210e3  mov     esi, 8007000Eh
0x1800210e8  jmp     short loc_18002110D
0x1800210ea  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800210ee  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x1800210f1  lea     rcx, [rbp+57h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x1800210f5  call    cs:__imp_MakeSelfRelativeSD
0x1800210fb  test    eax, eax
0x1800210fd  jnz     short loc_18002110A
0x1800210ff  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180021104  mov     esi, eax
0x180021106  test    eax, eax
0x180021108  js      short loc_18002110D
0x18002110a  mov     [rdi], rbx
0x18002110d  mov     rcx, r14; Block
0x180021110  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021115  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180021119  call    cs:__imp_LocalFree
0x18002111f  lea     rcx, [rbp+57h+var_70]; this
0x180021123  mov     [rbp+57h+var_70], r15
0x180021127  mov     [rbp+57h+var_68], r15d
0x18002112b  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021130  mov     rax, [rbp+57h+var_88]
0x180021134  lea     rcx, [rbp+57h+var_70]; this
0x180021138  mov     [rbp+57h+var_70], rax
0x18002113c  mov     [rbp+57h+var_68], r12d
0x180021140  call    ?FreeBlobs@CSidContainer@@QEAAXXZ; CSidContainer::FreeBlobs(void)
0x180021145  mov     rbx, [rsp+0D0h+arg_0]
0x18002114d  mov     eax, esi
0x18002114f  add     rsp, 0A0h
0x180021156  pop     r15
0x180021158  pop     r14
0x18002115a  pop     r13
0x18002115c  pop     r12
0x18002115e  pop     rdi
0x18002115f  pop     rsi
0x180021160  pop     rbp
0x180021161  retn
```
