# AddSidToTokenAcl(void *,void *,ulong)

- ea: `0x180023030`
- end: `0x1800233fa`
- name: `?AddSidToTokenAcl@@YAJPEAX0K@Z`
- size: `970`
- prototype: `__int64 __fastcall(HANDLE Handle, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180023950`

## callees

- `0x180019230`
- `0x180019270`
- `0x180023030`
- `0x180023614`
- `0x180023814`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002337e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800232bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002337e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002336e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x18002336e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023351`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180023351`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800231b9`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800232ad`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800231b9`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1800232ad`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800230ad`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180023114`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800230ad`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180023114`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023333`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180023333`

## pseudocode

```c
__int64 __fastcall AddSidToTokenAcl(HANDLE Handle, void *a2)
{
  PSID v2; // r13
  void *v3; // r12
  PACL v5; // rsi
  signed int v6; // eax
  unsigned int v7; // ebx
  void *v8; // rax
  signed int LastError; // eax
  struct _ACL *v10; // rdi
  struct _ACL *pSacl; // r14
  void *pOwner; // r15
  unsigned int v13; // edx
  signed int v14; // eax
  void *pPrimaryGroup; // rax
  signed int v16; // eax
  int v17; // eax
  signed int v18; // eax
  DWORD dwOwnerSize; // [rsp+68h] [rbp-39h] BYREF
  DWORD dwSaclSize; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+70h] [rbp-31h] BYREF
  int v23; // [rsp+74h] [rbp-2Dh] BYREF
  PACL pAcl; // [rsp+78h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+80h] [rbp-21h]
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+88h] [rbp-19h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+7h]
  DWORD dwDaclSize; // [rsp+110h] [rbp+6Fh] BYREF
  int v30; // [rsp+114h] [rbp+73h]
  DWORD nLengthNeeded; // [rsp+118h] [rbp+77h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+120h] [rbp+7Fh] BYREF

  v30 = HIDWORD(a2);
  v2 = g_pSidWpg;
  v3 = 0;
  dwAbsoluteSecurityDescriptorSize = 0;
  v27 = 0;
  pAcl = 0;
  nLengthNeeded = 0;
  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  v5 = 0;
  v23 = 0;
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  GetKernelObjectSecurity(Handle, 4u, 0, 0, &nLengthNeeded);
  if ( nLengthNeeded )
  {
    v8 = operator new(nLengthNeeded);
    pSelfRelativeSecurityDescriptor = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    if ( !GetKernelObjectSecurity(Handle, 4u, v8, nLengthNeeded, &nLengthNeeded) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_42;
    }
    v10 = (struct _ACL *)operator new(nLengthNeeded);
    if ( !v10 )
    {
LABEL_10:
      v7 = -2147024882;
LABEL_42:
      operator delete(pSelfRelativeSecurityDescriptor);
      return v7;
    }
    pSacl = 0;
    pOwner = 0;
    dwAbsoluteSecurityDescriptorSize = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( !MakeAbsoluteSD(
            pSelfRelativeSecurityDescriptor,
            0,
            &dwAbsoluteSecurityDescriptorSize,
            0,
            &dwDaclSize,
            0,
            &dwSaclSize,
            0,
            &dwOwnerSize,
            0,
            &dwPrimaryGroupSize) )
    {
      dwDaclSize = nLengthNeeded;
      dwAbsoluteSecurityDescriptorSize = 40;
      v14 = GetLastError();
      v7 = v14;
      if ( v14 != 122 )
      {
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_40;
      }
      if ( dwDaclSize > nLengthNeeded )
      {
        operator delete(v10);
        v10 = (struct _ACL *)operator new(dwDaclSize);
        if ( !v10 )
          goto LABEL_10;
      }
      pSacl = (struct _ACL *)operator new(dwSaclSize);
      if ( !pSacl )
      {
        v7 = -2147024882;
LABEL_40:
        operator delete(v10);
        if ( v5 )
          operator delete(v5);
        goto LABEL_42;
      }
      pOwner = operator new(dwOwnerSize);
      if ( !pOwner || (pPrimaryGroup = operator new(dwPrimaryGroupSize), (v3 = pPrimaryGroup) == 0) )
      {
        v7 = -2147024882;
LABEL_35:
        operator delete(pSacl);
LABEL_36:
        if ( pOwner )
          operator delete(pOwner);
        if ( v3 )
          operator delete(v3);
        goto LABEL_40;
      }
      if ( !MakeAbsoluteSD(
              pSelfRelativeSecurityDescriptor,
              pAbsoluteSecurityDescriptor,
              &dwAbsoluteSecurityDescriptorSize,
              v10,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        v16 = GetLastError();
        v7 = v16;
        if ( v16 > 0 )
          v7 = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_35;
      }
    }
    v7 = AllowedAccessExists(v10, v13, v2, &v23);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( v23 )
      {
        v7 = 0;
      }
      else
      {
        v17 = ExpandAcl(v10, nLengthNeeded, &pAcl, v2);
        v5 = pAcl;
        v7 = v17;
        if ( v17 >= 0
          && (!AddAccessAllowedAce(pAcl, 2u, 0xF01FFu, v2)
           || !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v5, 0)
           || !SetKernelObjectSecurity(Handle, 4u, pAbsoluteSecurityDescriptor)) )
        {
          v18 = GetLastError();
          v7 = v18;
          if ( v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
        }
      }
    }
    if ( !pSacl )
      goto LABEL_36;
    goto LABEL_35;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180023030  mov     rax, rsp
0x180023033  mov     [rax+18h], r8d
0x180023037  mov     [rax+10h], rdx
0x18002303b  mov     [rax+8], rcx
0x18002303f  push    rbp
0x180023040  push    rbx
0x180023041  push    rsi
0x180023042  push    rdi
0x180023043  push    r12
0x180023045  push    r13
0x180023047  push    r14
0x180023049  push    r15
0x18002304b  lea     rbp, [rax-5Fh]
0x18002304f  sub     rsp, 0B8h
0x180023056  mov     r13, cs:?g_pSidWpg@@3PEAXEA; void * g_pSidWpg
0x18002305d  xor     r12d, r12d
0x180023060  xor     eax, eax
0x180023062  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r12d
0x180023066  xorps   xmm0, xmm0
0x180023069  mov     [rbp+57h+var_50], rax
0x18002306d  lea     rax, [rbp+57h+nLengthNeeded]
0x180023071  mov     [rbp+57h+pAcl], r12
0x180023075  lea     edi, [r12+4]
0x18002307a  mov     [rbp+57h+nLengthNeeded], r12d
0x18002307e  mov     edx, edi; RequestedInformation
0x180023080  mov     [rbp+57h+dwDaclSize], r12d
0x180023084  xor     r9d, r9d; nLength
0x180023087  mov     [rbp+57h+dwSaclSize], r12d
0x18002308b  xor     r8d, r8d; pSecurityDescriptor
0x18002308e  mov     [rbp+57h+dwOwnerSize], r12d
0x180023092  mov     rbx, rcx
0x180023095  mov     [rbp+57h+dwPrimaryGroupSize], r12d
0x180023099  mov     esi, r12d
0x18002309c  mov     [rbp+57h+var_84], r12d
0x1800230a0  movups  [rbp+57h+pAbsoluteSecurityDescriptor], xmm0
0x1800230a4  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800230a9  movups  [rbp+57h+var_60], xmm0
0x1800230ad  call    cs:__imp_GetKernelObjectSecurity
0x1800230b4  nop     dword ptr [rax+rax+00h]
0x1800230b9  mov     eax, [rbp+57h+nLengthNeeded]
0x1800230bc  test    eax, eax
0x1800230be  jnz     short loc_1800230E4
0x1800230c0  call    cs:__imp_GetLastError
0x1800230c7  nop     dword ptr [rax+rax+00h]
0x1800230cc  mov     ebx, eax
0x1800230ce  test    eax, eax
0x1800230d0  jle     loc_1800233E3
0x1800230d6  movzx   ebx, ax
0x1800230d9  or      ebx, 80070000h
0x1800230df  jmp     loc_1800233E3
0x1800230e4  mov     rcx, rax; Size
0x1800230e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800230ec  mov     [rbp+57h+pSelfRelativeSecurityDescriptor], rax
0x1800230f0  test    rax, rax
0x1800230f3  jnz     short loc_1800230FF
0x1800230f5  mov     ebx, 8007000Eh
0x1800230fa  jmp     loc_1800233E3
0x1800230ff  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180023103  lea     rcx, [rbp+57h+nLengthNeeded]
0x180023107  mov     [rsp+0F0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x18002310c  mov     r8, rax; pSecurityDescriptor
0x18002310f  mov     rcx, rbx; Handle
0x180023112  mov     edx, edi; RequestedInformation
0x180023114  call    cs:__imp_GetKernelObjectSecurity
0x18002311b  nop     dword ptr [rax+rax+00h]
0x180023120  test    eax, eax
0x180023122  jnz     short loc_180023148
0x180023124  call    cs:__imp_GetLastError
0x18002312b  nop     dword ptr [rax+rax+00h]
0x180023130  mov     ebx, eax
0x180023132  test    eax, eax
0x180023134  jle     loc_1800233DA
0x18002313a  movzx   ebx, ax
0x18002313d  or      ebx, 80070000h
0x180023143  jmp     loc_1800233DA
0x180023148  mov     ecx, [rbp+57h+nLengthNeeded]; Size
0x18002314b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023150  mov     rdi, rax
0x180023153  test    rax, rax
0x180023156  jnz     short loc_180023162
0x180023158  mov     ebx, 8007000Eh
0x18002315d  jmp     loc_1800233DA
0x180023162  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180023166  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18002316a  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18002316f  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180023173  xor     ebx, ebx
0x180023175  lea     rax, [rbp+57h+dwOwnerSize]
0x180023179  mov     [rsp+0F0h+pPrimaryGroup], rbx; pPrimaryGroup
0x18002317e  xor     r9d, r9d; pDacl
0x180023181  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180023186  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180023188  mov     [rsp+0F0h+pOwner], rbx; pOwner
0x18002318d  lea     rax, [rbp+57h+dwSaclSize]
0x180023191  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x180023196  mov     r14, r12
0x180023199  lea     rax, [rbp+57h+dwDaclSize]
0x18002319d  mov     [rsp+0F0h+pSacl], rbx; pSacl
0x1800231a2  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpdwDaclSize
0x1800231a7  mov     r15, r12
0x1800231aa  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ebx
0x1800231ad  mov     [rbp+57h+dwDaclSize], ebx
0x1800231b0  mov     [rbp+57h+dwSaclSize], ebx
0x1800231b3  mov     [rbp+57h+dwOwnerSize], ebx
0x1800231b6  mov     [rbp+57h+dwPrimaryGroupSize], ebx
0x1800231b9  call    cs:__imp_MakeAbsoluteSD
0x1800231c0  nop     dword ptr [rax+rax+00h]
0x1800231c5  test    eax, eax
0x1800231c7  jnz     loc_1800232E1
0x1800231cd  mov     eax, [rbp+57h+nLengthNeeded]
0x1800231d0  mov     [rbp+57h+dwDaclSize], eax
0x1800231d3  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x1800231da  call    cs:__imp_GetLastError
0x1800231e1  nop     dword ptr [rax+rax+00h]
0x1800231e6  mov     ebx, eax
0x1800231e8  cmp     eax, 7Ah ; 'z'
0x1800231eb  jz      short loc_180023203
0x1800231ed  test    eax, eax
0x1800231ef  jle     loc_1800233C5
0x1800231f5  movzx   ebx, ax
0x1800231f8  or      ebx, 80070000h
0x1800231fe  jmp     loc_1800233C5
0x180023203  mov     eax, [rbp+57h+nLengthNeeded]
0x180023206  cmp     [rbp+57h+dwDaclSize], eax
0x180023209  jbe     short loc_180023227
0x18002320b  mov     rcx, rdi; Block
0x18002320e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023213  mov     ecx, [rbp+57h+dwDaclSize]; Size
0x180023216  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002321b  mov     rdi, rax
0x18002321e  test    rax, rax
0x180023221  jz      loc_180023158
0x180023227  mov     ecx, [rbp+57h+dwSaclSize]; Size
0x18002322a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002322f  mov     r14, rax
0x180023232  test    rax, rax
0x180023235  jnz     short loc_180023241
0x180023237  mov     ebx, 8007000Eh
0x18002323c  jmp     loc_1800233C0
0x180023241  mov     ecx, [rbp+57h+dwOwnerSize]; Size
0x180023244  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023249  mov     r15, rax
0x18002324c  test    rax, rax
0x18002324f  jnz     short loc_18002325B
0x180023251  mov     ebx, 8007000Eh
0x180023256  jmp     loc_18002339E
0x18002325b  mov     ecx, [rbp+57h+dwPrimaryGroupSize]; Size
0x18002325e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023263  mov     r12, rax
0x180023266  test    rax, rax
0x180023269  jz      short loc_180023251
0x18002326b  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18002326f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180023273  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180023278  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18002327c  mov     [rsp+0F0h+pPrimaryGroup], r12; pPrimaryGroup
0x180023281  lea     rax, [rbp+57h+dwOwnerSize]
0x180023285  mov     [rsp+0F0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18002328a  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18002328e  mov     [rsp+0F0h+pOwner], r15; pOwner
0x180023293  lea     rax, [rbp+57h+dwSaclSize]
0x180023297  mov     [rsp+0F0h+lpdwSaclSize], rax; lpdwSaclSize
0x18002329c  mov     r9, rdi; pDacl
0x18002329f  lea     rax, [rbp+57h+dwDaclSize]
0x1800232a3  mov     [rsp+0F0h+pSacl], r14; pSacl
0x1800232a8  mov     [rsp+0F0h+lpnLengthNeeded], rax; lpdwDaclSize
0x1800232ad  call    cs:__imp_MakeAbsoluteSD
0x1800232b4  nop     dword ptr [rax+rax+00h]
0x1800232b9  test    eax, eax
0x1800232bb  jnz     short loc_1800232E1
0x1800232bd  call    cs:__imp_GetLastError
0x1800232c4  nop     dword ptr [rax+rax+00h]
0x1800232c9  mov     ebx, eax
0x1800232cb  test    eax, eax
0x1800232cd  jle     loc_18002339E
0x1800232d3  movzx   ebx, ax
0x1800232d6  or      ebx, 80070000h
0x1800232dc  jmp     loc_18002339E
0x1800232e1  lea     r9, [rbp+57h+var_84]; int *
0x1800232e5  mov     r8, r13; void *
0x1800232e8  mov     rcx, rdi; pAcl
0x1800232eb  call    ?AllowedAccessExists@@YAJPEAU_ACL@@KPEAXPEAH@Z; AllowedAccessExists(_ACL *,ulong,void *,int *)
0x1800232f0  mov     ebx, eax
0x1800232f2  test    eax, eax
0x1800232f4  js      loc_180023399
0x1800232fa  cmp     [rbp+57h+var_84], esi
0x1800232fd  jz      short loc_180023306
0x1800232ff  xor     ebx, ebx
0x180023301  jmp     loc_180023399
0x180023306  mov     edx, [rbp+57h+nLengthNeeded]; unsigned int
0x180023309  lea     r8, [rbp+57h+pAcl]; struct _ACL **
0x18002330d  mov     r9, r13; void *
0x180023310  mov     rcx, rdi; pAcl
0x180023313  call    ?ExpandAcl@@YAJPEAU_ACL@@KPEAPEAU1@PEAX@Z; ExpandAcl(_ACL *,ulong,_ACL * *,void *)
0x180023318  mov     rsi, [rbp+57h+pAcl]
0x18002331c  mov     ebx, eax
0x18002331e  test    eax, eax
0x180023320  js      short loc_180023399
0x180023322  mov     r9, r13; pSid
0x180023325  mov     edx, 2; dwAceRevision
0x18002332a  mov     r8d, 0F01FFh; AccessMask
0x180023330  mov     rcx, rsi; pAcl
0x180023333  call    cs:__imp_AddAccessAllowedAce
0x18002333a  nop     dword ptr [rax+rax+00h]
0x18002333f  test    eax, eax
0x180023341  jz      short loc_18002337E
0x180023343  xor     r9d, r9d; bDaclDefaulted
0x180023346  lea     rcx, [rbp+57h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x18002334a  mov     r8, rsi; pDacl
0x18002334d  lea     edx, [r9+1]; bDaclPresent
0x180023351  call    cs:__imp_SetSecurityDescriptorDacl
0x180023358  nop     dword ptr [rax+rax+00h]
0x18002335d  test    eax, eax
0x18002335f  jz      short loc_18002337E
0x180023361  mov     rcx, [rbp+57h+Handle]; Handle
0x180023365  lea     r8, [rbp+57h+pAbsoluteSecurityDescriptor]; SecurityDescriptor
0x180023369  mov     edx, 4; SecurityInformation
0x18002336e  call    cs:__imp_SetKernelObjectSecurity
0x180023375  nop     dword ptr [rax+rax+00h]
0x18002337a  test    eax, eax
0x18002337c  jnz     short loc_180023399
0x18002337e  call    cs:__imp_GetLastError
0x180023385  nop     dword ptr [rax+rax+00h]
0x18002338a  mov     ebx, eax
0x18002338c  test    eax, eax
0x18002338e  jle     short loc_180023399
0x180023390  movzx   ebx, ax
0x180023393  or      ebx, 80070000h
0x180023399  test    r14, r14
0x18002339c  jz      short loc_1800233A6
0x18002339e  mov     rcx, r14; Block
0x1800233a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233a6  test    r15, r15
0x1800233a9  jz      short loc_1800233B3
0x1800233ab  mov     rcx, r15; Block
0x1800233ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233b3  test    r12, r12
0x1800233b6  jz      short loc_1800233C0
0x1800233b8  mov     rcx, r12; Block
0x1800233bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233c0  test    rdi, rdi
0x1800233c3  jz      short loc_1800233CD
0x1800233c5  mov     rcx, rdi; Block
0x1800233c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233cd  test    rsi, rsi
0x1800233d0  jz      short loc_1800233DA
0x1800233d2  mov     rcx, rsi; Block
0x1800233d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233da  mov     rcx, [rbp+57h+pSelfRelativeSecurityDescriptor]; Block
0x1800233de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800233e3  mov     eax, ebx
0x1800233e5  add     rsp, 0B8h
0x1800233ec  pop     r15
0x1800233ee  pop     r14
0x1800233f0  pop     r13
0x1800233f2  pop     r12
0x1800233f4  pop     rdi
0x1800233f5  pop     rsi
0x1800233f6  pop     rbx
0x1800233f7  pop     rbp
0x1800233f8  retn
```
