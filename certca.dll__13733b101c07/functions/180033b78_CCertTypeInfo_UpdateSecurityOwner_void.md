# CCertTypeInfo::_UpdateSecurityOwner(void)

- ea: `0x180033b78`
- end: `0x180033f69`
- name: `?_UpdateSecurityOwner@CCertTypeInfo@@IEAAJXZ`
- size: `1009`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180030224`

## callees

- `0x180008400`
- `0x180012450`
- `0x18002ffbc`
- `0x180031990`
- `0x180033b78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033ccb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033cf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033e6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033ccb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033cf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033d6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ef5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e46`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180033e18`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180033e18`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180033c21`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180033c21`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180033bba`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180033eb1`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180033bba`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180033eb1`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180033e3c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180033e93`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180033e3c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180033e93`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180033c9d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180033dce`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180033c9d`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180033dce`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180033df3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180033df3`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_UpdateSecurityOwner(CCertTypeInfo *this)
{
  void *v2; // rcx
  unsigned int v3; // ebx
  HLOCAL v4; // rdi
  struct _ACL *pSacl; // r13
  HLOCAL pOwner; // r12
  void *v7; // r15
  void *v8; // rsi
  int RootDomEntitySid; // eax
  unsigned int v10; // ecx
  int v11; // edx
  struct _ACL *v12; // rbx
  HLOCAL pPrimaryGroup; // rax
  HLOCAL v14; // rax
  DWORD dwDaclSize; // [rsp+60h] [rbp-9h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+64h] [rbp-5h] BYREF
  DWORD dwBufferLength; // [rsp+68h] [rbp-1h] BYREF
  DWORD dwRevision; // [rsp+6Ch] [rbp+3h] BYREF
  PSID pGroup; // [rsp+70h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+Fh]
  WORD pControl; // [rsp+D0h] [rbp+67h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD dwOwnerSize; // [rsp+E0h] [rbp+77h] BYREF
  DWORD dwSaclSize; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = (void *)*((_QWORD *)this + 17);
  pControl = 0;
  dwRevision = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwBufferLength = 0;
  pGroup = 0;
  if ( !IsValidSecurityDescriptor(v2) )
  {
    v3 = -2147023558;
    CSPrintErrorLineFile(0x1D6C0328u, -2147023558);
    return v3;
  }
  hMem = 0;
  v4 = 0;
  pSacl = 0;
  pOwner = 0;
  v7 = 0;
  v8 = 0;
  RootDomEntitySid = GetRootDomEntitySid(&pGroup, 519);
  v3 = RootDomEntitySid;
  if ( RootDomEntitySid )
  {
    v10 = 493945640;
  }
  else if ( GetSecurityDescriptorControl(*((PSECURITY_DESCRIPTOR *)this + 17), &pControl, &dwRevision) )
  {
    if ( (pControl & 0x8000) == 0 )
    {
      v11 = -2147023558;
      v10 = 494732072;
      v3 = -2147023558;
      goto LABEL_6;
    }
    if ( MakeAbsoluteSD(
           *((PSECURITY_DESCRIPTOR *)this + 17),
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize)
      || GetLastError() == 122 )
    {
      v4 = LocalAlloc(0x40u, dwAbsoluteSecurityDescriptorSize);
      if ( !v4 )
      {
        v11 = -2147024882;
        v10 = 495911720;
        v3 = -2147024882;
        goto LABEL_6;
      }
      hMem = LocalAlloc(0x40u, dwDaclSize);
      v12 = (struct _ACL *)hMem;
      if ( !hMem )
      {
        v11 = -2147024882;
        v10 = 496370472;
        v3 = -2147024882;
        goto LABEL_6;
      }
      pSacl = (struct _ACL *)LocalAlloc(0x40u, dwSaclSize);
      if ( !pSacl )
      {
        v11 = -2147024882;
        v10 = 496829224;
        v3 = -2147024882;
        goto LABEL_6;
      }
      pOwner = LocalAlloc(0x40u, dwOwnerSize);
      if ( !pOwner )
      {
        v11 = -2147024882;
        v10 = 497287976;
        v3 = -2147024882;
        goto LABEL_6;
      }
      pPrimaryGroup = LocalAlloc(0x40u, dwPrimaryGroupSize);
      v7 = pPrimaryGroup;
      if ( !pPrimaryGroup )
      {
        v11 = -2147024882;
        v10 = 497746728;
        v3 = -2147024882;
        goto LABEL_6;
      }
      if ( MakeAbsoluteSD(
             *((PSECURITY_DESCRIPTOR *)this + 17),
             v4,
             &dwAbsoluteSecurityDescriptorSize,
             v12,
             &dwDaclSize,
             pSacl,
             &dwSaclSize,
             pOwner,
             &dwOwnerSize,
             pPrimaryGroup,
             &dwPrimaryGroupSize) )
      {
        if ( SetSecurityDescriptorOwner(v4, pGroup, 0) )
        {
          if ( SetSecurityDescriptorGroup(v4, pGroup, 0) )
          {
            if ( MakeSelfRelativeSD(v4, 0, &dwBufferLength) || GetLastError() == 122 )
            {
              v14 = LocalAlloc(0x40u, dwBufferLength);
              v8 = v14;
              if ( !v14 )
              {
                v11 = -2147024882;
                v10 = 500302632;
                v3 = -2147024882;
                goto LABEL_6;
              }
              if ( MakeSelfRelativeSD(v4, v14, &dwBufferLength) )
              {
                if ( !IsValidSecurityDescriptor(v8) )
                {
                  v11 = -2147023558;
                  v10 = 501154600;
                  v3 = -2147023558;
                  goto LABEL_6;
                }
                RootDomEntitySid = CCertTypeInfo::SetSecurity(this, v8);
                v3 = RootDomEntitySid;
                if ( !RootDomEntitySid )
                {
                  v3 = 0;
                  goto LABEL_42;
                }
                v10 = 501547816;
              }
              else
              {
                RootDomEntitySid = myHLastError();
                v3 = RootDomEntitySid;
                v10 = 500761384;
              }
            }
            else
            {
              RootDomEntitySid = myHLastError();
              v3 = RootDomEntitySid;
              v10 = 499712808;
            }
          }
          else
          {
            RootDomEntitySid = myHLastError();
            v3 = RootDomEntitySid;
            v10 = 499057448;
          }
        }
        else
        {
          RootDomEntitySid = myHLastError();
          v3 = RootDomEntitySid;
          v10 = 498664232;
        }
      }
      else
      {
        RootDomEntitySid = myHLastError();
        v3 = RootDomEntitySid;
        v10 = 498205480;
      }
    }
    else
    {
      RootDomEntitySid = myHLastError();
      v3 = RootDomEntitySid;
      v10 = 495321896;
    }
  }
  else
  {
    RootDomEntitySid = myHLastError();
    v3 = RootDomEntitySid;
    v10 = 494338856;
  }
  v11 = RootDomEntitySid;
LABEL_6:
  CSPrintErrorLineFile(v10, v11);
LABEL_42:
  if ( pGroup )
    LocalFree(pGroup);
  if ( v8 )
    LocalFree(v8);
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
    LocalFree(hMem);
  if ( pSacl )
    LocalFree(pSacl);
  if ( pOwner )
    LocalFree(pOwner);
  if ( v7 )
    LocalFree(v7);
  return v3;
}

```

## disassembly

```asm
0x180033b78  push    rbp
0x180033b7a  push    rbx
0x180033b7b  push    rsi
0x180033b7c  push    rdi
0x180033b7d  push    r12
0x180033b7f  push    r13
0x180033b81  push    r14
0x180033b83  push    r15
0x180033b85  lea     rbp, [rsp-1Fh]
0x180033b8a  sub     rsp, 88h
0x180033b91  xor     ebx, ebx
0x180033b93  mov     r14, rcx
0x180033b96  mov     rcx, [rcx+88h]; pSecurityDescriptor
0x180033b9d  mov     [rbp+57h+pControl], bx
0x180033ba1  mov     [rbp+57h+dwRevision], ebx
0x180033ba4  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x180033ba7  mov     [rbp+57h+dwDaclSize], ebx
0x180033baa  mov     [rbp+57h+dwSaclSize], ebx
0x180033bad  mov     [rbp+57h+dwOwnerSize], ebx
0x180033bb0  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x180033bb3  mov     [rbp+57h+dwBufferLength], ebx
0x180033bb6  mov     [rbp+57h+pGroup], rbx
0x180033bba  call    cs:__imp_IsValidSecurityDescriptor
0x180033bc0  test    eax, eax
0x180033bc2  jnz     short loc_180033BDA
0x180033bc4  mov     edx, 8007053Ah; int
0x180033bc9  mov     ecx, 1D6C0328h; unsigned int
0x180033bce  mov     ebx, edx
0x180033bd0  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180033bd5  jmp     loc_180033F53
0x180033bda  mov     edx, 207h
0x180033bdf  mov     [rbp+57h+hMem], rbx
0x180033be3  lea     rcx, [rbp+57h+pGroup]
0x180033be7  mov     rdi, rbx
0x180033bea  mov     r13, rbx
0x180033bed  mov     r12, rbx
0x180033bf0  mov     r15, rbx
0x180033bf3  mov     rsi, rbx
0x180033bf6  call    GetRootDomEntitySid
0x180033bfb  mov     ebx, eax
0x180033bfd  test    eax, eax
0x180033bff  jz      short loc_180033C12
0x180033c01  mov     ecx, 1D710328h; unsigned int
0x180033c06  mov     edx, eax; int
0x180033c08  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180033c0d  jmp     loc_180033EE9
0x180033c12  mov     rcx, [r14+88h]; pSecurityDescriptor
0x180033c19  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x180033c1d  lea     rdx, [rbp+57h+pControl]; pControl
0x180033c21  call    cs:__imp_GetSecurityDescriptorControl
0x180033c27  xor     ebx, ebx
0x180033c29  test    eax, eax
0x180033c2b  jnz     short loc_180033C3B
0x180033c2d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033c32  mov     ebx, eax
0x180033c34  mov     ecx, 1D770328h
0x180033c39  jmp     short loc_180033C06
0x180033c3b  movzx   ecx, [rbp+57h+pControl]
0x180033c3f  mov     eax, 8000h
0x180033c44  and     cx, ax
0x180033c47  cmp     bx, cx
0x180033c4a  jnz     short loc_180033C5A
0x180033c4c  mov     edx, 8007053Ah
0x180033c51  mov     ecx, 1D7D0328h
0x180033c56  mov     ebx, edx
0x180033c58  jmp     short loc_180033C08
0x180033c5a  mov     rcx, [r14+88h]; pSelfRelativeSecurityDescriptor
0x180033c61  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180033c65  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180033c6a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180033c6e  mov     [rsp+0C0h+pPrimaryGroup], rbx; pPrimaryGroup
0x180033c73  lea     rax, [rbp+57h+dwOwnerSize]
0x180033c77  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180033c7c  xor     r9d, r9d; pDacl
0x180033c7f  mov     [rsp+0C0h+pOwner], rbx; pOwner
0x180033c84  lea     rax, [rbp+57h+dwSaclSize]
0x180033c88  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x180033c8d  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180033c8f  lea     rax, [rbp+57h+dwDaclSize]
0x180033c93  mov     [rsp+0C0h+pSacl], rbx; pSacl
0x180033c98  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x180033c9d  call    cs:__imp_MakeAbsoluteSD
0x180033ca3  test    eax, eax
0x180033ca5  jnz     short loc_180033CC3
0x180033ca7  call    cs:__imp_GetLastError
0x180033cad  cmp     eax, 7Ah ; 'z'
0x180033cb0  jz      short loc_180033CC3
0x180033cb2  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033cb7  mov     ebx, eax
0x180033cb9  mov     ecx, 1D860328h
0x180033cbe  jmp     loc_180033C06
0x180033cc3  mov     edx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; uBytes
0x180033cc6  mov     ecx, 40h ; '@'; uFlags
0x180033ccb  call    cs:__imp_LocalAlloc
0x180033cd1  mov     rdi, rax
0x180033cd4  test    rax, rax
0x180033cd7  jnz     short loc_180033CEA
0x180033cd9  mov     edx, 8007000Eh
0x180033cde  mov     ecx, 1D8F0328h
0x180033ce3  mov     ebx, edx
0x180033ce5  jmp     loc_180033C08
0x180033cea  mov     edx, [rbp+57h+dwDaclSize]; uBytes
0x180033ced  mov     ecx, 40h ; '@'; uFlags
0x180033cf2  call    cs:__imp_LocalAlloc
0x180033cf8  mov     [rbp+57h+hMem], rax
0x180033cfc  mov     rbx, rax
0x180033cff  test    rax, rax
0x180033d02  jnz     short loc_180033D15
0x180033d04  mov     edx, 8007000Eh
0x180033d09  mov     ecx, 1D960328h
0x180033d0e  mov     ebx, edx
0x180033d10  jmp     loc_180033C08
0x180033d15  mov     edx, [rbp+57h+dwSaclSize]; uBytes
0x180033d18  mov     ecx, 40h ; '@'; uFlags
0x180033d1d  call    cs:__imp_LocalAlloc
0x180033d23  mov     r13, rax
0x180033d26  test    rax, rax
0x180033d29  jnz     short loc_180033D3C
0x180033d2b  mov     edx, 8007000Eh
0x180033d30  mov     ecx, 1D9D0328h
0x180033d35  mov     ebx, edx
0x180033d37  jmp     loc_180033C08
0x180033d3c  mov     edx, [rbp+57h+dwOwnerSize]; uBytes
0x180033d3f  mov     ecx, 40h ; '@'; uFlags
0x180033d44  call    cs:__imp_LocalAlloc
0x180033d4a  mov     r12, rax
0x180033d4d  test    rax, rax
0x180033d50  jnz     short loc_180033D63
0x180033d52  mov     edx, 8007000Eh
0x180033d57  mov     ecx, 1DA40328h
0x180033d5c  mov     ebx, edx
0x180033d5e  jmp     loc_180033C08
0x180033d63  mov     edx, [rbp+57h+dwPrimaryGroupSize]; uBytes
0x180033d66  mov     ecx, 40h ; '@'; uFlags
0x180033d6b  call    cs:__imp_LocalAlloc
0x180033d71  mov     r15, rax
0x180033d74  test    rax, rax
0x180033d77  jnz     short loc_180033D8A
0x180033d79  mov     edx, 8007000Eh
0x180033d7e  mov     ecx, 1DAB0328h
0x180033d83  mov     ebx, edx
0x180033d85  jmp     loc_180033C08
0x180033d8a  mov     rcx, [r14+88h]; pSelfRelativeSecurityDescriptor
0x180033d91  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180033d95  mov     [rsp+0C0h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x180033d9a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180033d9e  mov     [rsp+0C0h+pPrimaryGroup], r15; pPrimaryGroup
0x180033da3  lea     rax, [rbp+57h+dwOwnerSize]
0x180033da7  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180033dac  mov     r9, rbx; pDacl
0x180033daf  mov     [rsp+0C0h+pOwner], r12; pOwner
0x180033db4  lea     rax, [rbp+57h+dwSaclSize]
0x180033db8  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x180033dbd  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x180033dc0  lea     rax, [rbp+57h+dwDaclSize]
0x180033dc4  mov     [rsp+0C0h+pSacl], r13; pSacl
0x180033dc9  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x180033dce  call    cs:__imp_MakeAbsoluteSD
0x180033dd4  test    eax, eax
0x180033dd6  jnz     short loc_180033DE9
0x180033dd8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033ddd  mov     ebx, eax
0x180033ddf  mov     ecx, 1DB20328h
0x180033de4  jmp     loc_180033C06
0x180033de9  mov     rdx, [rbp+57h+pGroup]; pOwner
0x180033ded  xor     r8d, r8d; bOwnerDefaulted
0x180033df0  mov     rcx, rdi; pSecurityDescriptor
0x180033df3  call    cs:__imp_SetSecurityDescriptorOwner
0x180033df9  test    eax, eax
0x180033dfb  jnz     short loc_180033E0E
0x180033dfd  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033e02  mov     ebx, eax
0x180033e04  mov     ecx, 1DB90328h
0x180033e09  jmp     loc_180033C06
0x180033e0e  mov     rdx, [rbp+57h+pGroup]; pGroup
0x180033e12  xor     r8d, r8d; bGroupDefaulted
0x180033e15  mov     rcx, rdi; pSecurityDescriptor
0x180033e18  call    cs:__imp_SetSecurityDescriptorGroup
0x180033e1e  test    eax, eax
0x180033e20  jnz     short loc_180033E33
0x180033e22  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033e27  mov     ebx, eax
0x180033e29  mov     ecx, 1DBF0328h
0x180033e2e  jmp     loc_180033C06
0x180033e33  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180033e37  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180033e39  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180033e3c  call    cs:__imp_MakeSelfRelativeSD
0x180033e42  test    eax, eax
0x180033e44  jnz     short loc_180033E62
0x180033e46  call    cs:__imp_GetLastError
0x180033e4c  cmp     eax, 7Ah ; 'z'
0x180033e4f  jz      short loc_180033E62
0x180033e51  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033e56  mov     ebx, eax
0x180033e58  mov     ecx, 1DC90328h
0x180033e5d  jmp     loc_180033C06
0x180033e62  mov     edx, [rbp+57h+dwBufferLength]; uBytes
0x180033e65  mov     ecx, 40h ; '@'; uFlags
0x180033e6a  call    cs:__imp_LocalAlloc
0x180033e70  mov     rsi, rax
0x180033e73  test    rax, rax
0x180033e76  jnz     short loc_180033E89
0x180033e78  mov     edx, 8007000Eh
0x180033e7d  mov     ecx, 1DD20328h
0x180033e82  mov     ebx, edx
0x180033e84  jmp     loc_180033C08
0x180033e89  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180033e8d  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x180033e90  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180033e93  call    cs:__imp_MakeSelfRelativeSD
0x180033e99  test    eax, eax
0x180033e9b  jnz     short loc_180033EAE
0x180033e9d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180033ea2  mov     ebx, eax
0x180033ea4  mov     ecx, 1DD90328h
0x180033ea9  jmp     loc_180033C06
0x180033eae  mov     rcx, rsi; pSecurityDescriptor
0x180033eb1  call    cs:__imp_IsValidSecurityDescriptor
0x180033eb7  test    eax, eax
0x180033eb9  jnz     short loc_180033ECC
0x180033ebb  mov     edx, 8007053Ah
0x180033ec0  mov     ecx, 1DDF0328h
0x180033ec5  mov     ebx, edx
0x180033ec7  jmp     loc_180033C08
0x180033ecc  mov     rdx, rsi; void *
0x180033ecf  mov     rcx, r14; this
0x180033ed2  call    ?SetSecurity@CCertTypeInfo@@QEAAJPEAX@Z; CCertTypeInfo::SetSecurity(void *)
0x180033ed7  mov     ebx, eax
0x180033ed9  test    eax, eax
0x180033edb  jz      short loc_180033EE7
0x180033edd  mov     ecx, 1DE50328h
0x180033ee2  jmp     loc_180033C06
0x180033ee7  xor     ebx, ebx
0x180033ee9  mov     rax, [rbp+57h+pGroup]
0x180033eed  test    rax, rax
0x180033ef0  jz      short loc_180033EFB
0x180033ef2  mov     rcx, rax; hMem
0x180033ef5  call    cs:__imp_LocalFree
0x180033efb  test    rsi, rsi
0x180033efe  jz      short loc_180033F09
0x180033f00  mov     rcx, rsi; hMem
0x180033f03  call    cs:__imp_LocalFree
0x180033f09  test    rdi, rdi
0x180033f0c  jz      short loc_180033F17
0x180033f0e  mov     rcx, rdi; hMem
0x180033f11  call    cs:__imp_LocalFree
0x180033f17  mov     rax, [rbp+57h+hMem]
0x180033f1b  test    rax, rax
0x180033f1e  jz      short loc_180033F29
0x180033f20  mov     rcx, rax; hMem
0x180033f23  call    cs:__imp_LocalFree
0x180033f29  test    r13, r13
0x180033f2c  jz      short loc_180033F37
0x180033f2e  mov     rcx, r13; hMem
0x180033f31  call    cs:__imp_LocalFree
0x180033f37  test    r12, r12
0x180033f3a  jz      short loc_180033F45
0x180033f3c  mov     rcx, r12; hMem
0x180033f3f  call    cs:__imp_LocalFree
0x180033f45  test    r15, r15
0x180033f48  jz      short loc_180033F53
0x180033f4a  mov     rcx, r15; hMem
0x180033f4d  call    cs:__imp_LocalFree
0x180033f53  mov     eax, ebx
0x180033f55  add     rsp, 88h
0x180033f5c  pop     r15
0x180033f5e  pop     r14
0x180033f60  pop     r13
0x180033f62  pop     r12
0x180033f64  pop     rdi
0x180033f65  pop     rsi
0x180033f66  pop     rbx
0x180033f67  pop     rbp
0x180033f68  retn
```
