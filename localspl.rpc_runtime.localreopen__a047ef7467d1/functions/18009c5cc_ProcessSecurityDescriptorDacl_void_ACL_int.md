# ProcessSecurityDescriptorDacl(void *,_ACL * *,int *)

- ea: `0x18009c5cc`
- end: `0x18009c902`
- name: `?ProcessSecurityDescriptorDacl@@YAHPEAXPEAPEAU_ACL@@PEAH@Z`
- size: `822`
- prototype: `int(void *, struct _ACL **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009c908`

## callees

- `0x180046650`
- `0x18009c5cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18009c842`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18009c842`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009c800`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18009c800`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18009c749`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18009c749`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009c77d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009c7cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009c77d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009c7cf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009c836`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18009c836`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18009c622`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18009c622`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009c665`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18009c665`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009c718`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009c859`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009c718`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009c859`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009c7aa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009c7aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c88b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c88b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c8dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c685`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c697`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c6a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c6b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c78d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c7e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c685`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c697`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c6a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c6b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c78d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c7e7`

## pseudocode

```c
__int64 __fastcall ProcessSecurityDescriptorDacl(void *a1, struct _ACL **a2, int *a3)
{
  DWORD v3; // ebx
  SIZE_T v5; // rdx
  _QWORD *v6; // r15
  HLOCAL v7; // r12
  _BYTE *v8; // r13
  HLOCAL v9; // rax
  struct _ACL *v10; // rsi
  __int64 v11; // rdi
  DWORD v12; // r12d
  DWORD v13; // ebx
  HLOCAL v14; // rax
  DWORD LengthSid; // eax
  struct _ACL *v16; // rax
  __int64 v17; // r12
  _BYTE *v18; // rbx
  void *v19; // r9
  DWORD v20; // r8d
  __int64 i; // r12
  DWORD AccessMask; // [rsp+20h] [rbp-49h] BYREF
  WINBOOL bDaclPresent; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pAce; // [rsp+30h] [rbp-39h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-31h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-29h]
  HLOCAL v27; // [rsp+48h] [rbp-21h]
  DWORD nDestinationSidLength; // [rsp+50h] [rbp-19h]
  LPVOID v29; // [rsp+58h] [rbp-11h] BYREF
  PSID pSourceSid; // [rsp+60h] [rbp-9h]
  HLOCAL v31; // [rsp+68h] [rbp-1h]
  struct _ACL **v32; // [rsp+70h] [rbp+7h]
  __int64 pAclInformation; // [rsp+78h] [rbp+Fh] BYREF
  int v34; // [rsp+80h] [rbp+17h]

  v32 = a2;
  bDaclPresent = 0;
  pDacl = 0;
  pAce = 0;
  v29 = 0;
  *a2 = 0;
  pAclInformation = 0;
  v34 = 0;
  AccessMask = GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, a3);
  v3 = AccessMask;
  if ( AccessMask )
  {
    if ( !pDacl )
      return 1;
    v3 = bDaclPresent;
    AccessMask = bDaclPresent;
  }
  if ( v3 )
  {
    GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation);
    v5 = 8LL * (unsigned int)pAclInformation;
    if ( v5 > 0xFFFFFFFF )
      return 0;
    v6 = LocalAlloc(0x40u, v5);
    v7 = LocalAlloc(0x40u, 4LL * (unsigned int)pAclInformation);
    hMem = v7;
    v8 = LocalAlloc(0x40u, (unsigned int)pAclInformation);
    v9 = LocalAlloc(0x40u, (unsigned int)pAclInformation);
    v27 = v9;
    v3 = v6 && v7 && v8 && v9;
    AccessMask = v3;
  }
  else
  {
    v6 = 0;
    v8 = 0;
    v27 = 0;
    hMem = 0;
  }
  v10 = 0;
  v11 = 0;
  if ( v3 )
  {
    v12 = 0;
    v13 = 8;
    while ( v12 < (unsigned int)pAclInformation )
    {
      GetAce(pDacl, v12, &pAce);
      if ( (*((_BYTE *)pAce + 1) & 8) == 0 )
      {
        *((_BYTE *)v27 + v11) = *(_BYTE *)pAce;
        AccessMask = *((_DWORD *)pAce + 1);
        MapGenericMask(&AccessMask, &stru_18013DDE8);
        *((_DWORD *)hMem + v11) = (AccessMask & 0xC) != 0 ? 0x10000000 : 0;
        v8[v11] = *((_BYTE *)pAce + 1);
        pSourceSid = (char *)pAce + 8;
        nDestinationSidLength = GetLengthSid((char *)pAce + 8);
        v14 = LocalAlloc(0x40u, nDestinationSidLength);
        v31 = v14;
        if ( !v14 )
          goto LABEL_32;
        CopySid(nDestinationSidLength, v14, pSourceSid);
        v6[v11] = v31;
        v11 = (unsigned int)(v11 + 1);
      }
      ++v12;
    }
    if ( (_DWORD)v11 )
    {
      do
      {
        LengthSid = GetLengthSid((PSID)v6[(unsigned int)v10]);
        LODWORD(v10) = (_DWORD)v10 + 1;
        v13 += LengthSid + 8;
      }
      while ( (unsigned int)v10 < (unsigned int)v11 );
    }
    v16 = (struct _ACL *)LocalAlloc(0x40u, v13);
    v10 = v16;
    if ( v16 )
    {
      v3 = InitializeAcl(v16, v13, 2u);
      AccessMask = v3;
      goto LABEL_27;
    }
LABEL_32:
    v3 = 0;
  }
  else
  {
LABEL_27:
    v17 = 0;
    if ( v3 )
    {
      v18 = v27;
      while ( (unsigned int)v17 < (unsigned int)v11 )
      {
        v19 = (void *)v6[v17];
        v20 = *((_DWORD *)hMem + v17);
        if ( v18[v17] )
          AddAccessDeniedAce(v10, 2u, v20, v19);
        else
          AddAccessAllowedAce(v10, 2u, v20, v19);
        if ( v8[v17] )
        {
          GetAce(v10, v17, &v29);
          *((_BYTE *)v29 + 1) = v8[v17];
        }
        v17 = (unsigned int)(v17 + 1);
      }
      v3 = AccessMask;
      *v32 = v10;
      v10 = 0;
    }
  }
  if ( v6 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)v11; i = (unsigned int)(i + 1) )
      LocalFree((HLOCAL)v6[i]);
    LocalFree(v6);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    LocalFree(v8);
  if ( v27 )
    LocalFree(v27);
  if ( v10 )
    LocalFree(v10);
  return v3;
}

```

## disassembly

```asm
0x18009c5cc  push    rbp
0x18009c5ce  push    rbx
0x18009c5cf  push    rsi
0x18009c5d0  push    rdi
0x18009c5d1  push    r12
0x18009c5d3  push    r13
0x18009c5d5  push    r15
0x18009c5d7  lea     rbp, [rsp-27h]
0x18009c5dc  sub     rsp, 90h
0x18009c5e3  mov     rax, cs:__security_cookie
0x18009c5ea  xor     rax, rsp
0x18009c5ed  mov     [rbp+57h+var_38], rax
0x18009c5f1  xor     r9d, r9d
0x18009c5f4  mov     [rbp+57h+var_50], rdx
0x18009c5f8  mov     rax, rdx
0x18009c5fb  mov     [rbp+57h+bDaclPresent], r9d
0x18009c5ff  xor     edx, edx
0x18009c601  mov     [rbp+57h+pDacl], r9
0x18009c605  mov     [rbp+57h+pAce], r9
0x18009c609  mov     [rbp+57h+var_68], r9
0x18009c60d  mov     [rax], r9
0x18009c610  mov     r9, r8; lpbDaclDefaulted
0x18009c613  mov     [rbp+57h+pAclInformation], rdx
0x18009c617  lea     r8, [rbp+57h+pDacl]; pDacl
0x18009c61b  mov     [rbp+57h+var_40], edx
0x18009c61e  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18009c622  call    cs:__imp_GetSecurityDescriptorDacl
0x18009c628  mov     [rbp+57h+AccessMask], eax
0x18009c62b  mov     ebx, eax
0x18009c62d  test    eax, eax
0x18009c62f  jz      short loc_18009C648
0x18009c631  cmp     [rbp+57h+pDacl], 0
0x18009c636  jnz     short loc_18009C642
0x18009c638  mov     eax, 1
0x18009c63d  jmp     loc_18009C8E4
0x18009c642  mov     ebx, [rbp+57h+bDaclPresent]
0x18009c645  mov     [rbp+57h+AccessMask], ebx
0x18009c648  mov     edi, 40h ; '@'
0x18009c64d  test    ebx, ebx
0x18009c64f  jz      loc_18009C6E3
0x18009c655  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18009c659  lea     r9d, [rdi-3Eh]; dwAclInformationClass
0x18009c65d  lea     r8d, [rdi-34h]; nAclInformationLength
0x18009c661  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x18009c665  call    cs:__imp_GetAclInformation
0x18009c66b  mov     edx, dword ptr [rbp+57h+pAclInformation]
0x18009c66e  mov     eax, 0FFFFFFFFh
0x18009c673  shl     rdx, 3; uBytes
0x18009c677  cmp     rdx, rax
0x18009c67a  jbe     short loc_18009C683
0x18009c67c  xor     eax, eax
0x18009c67e  jmp     loc_18009C8E4
0x18009c683  mov     ecx, edi; uFlags
0x18009c685  call    cs:__imp_LocalAlloc
0x18009c68b  mov     edx, dword ptr [rbp+57h+pAclInformation]
0x18009c68e  mov     ecx, edi; uFlags
0x18009c690  shl     rdx, 2; uBytes
0x18009c694  mov     r15, rax
0x18009c697  call    cs:__imp_LocalAlloc
0x18009c69d  mov     edx, dword ptr [rbp+57h+pAclInformation]; uBytes
0x18009c6a0  mov     ecx, edi; uFlags
0x18009c6a2  mov     r12, rax
0x18009c6a5  mov     [rbp+57h+hMem], rax
0x18009c6a9  call    cs:__imp_LocalAlloc
0x18009c6af  mov     edx, dword ptr [rbp+57h+pAclInformation]; uBytes
0x18009c6b2  mov     ecx, edi; uFlags
0x18009c6b4  mov     r13, rax
0x18009c6b7  call    cs:__imp_LocalAlloc
0x18009c6bd  mov     [rbp+57h+var_78], rax
0x18009c6c1  test    r15, r15
0x18009c6c4  jz      short loc_18009C6DF
0x18009c6c6  test    r12, r12
0x18009c6c9  jz      short loc_18009C6DF
0x18009c6cb  test    r13, r13
0x18009c6ce  jz      short loc_18009C6DF
0x18009c6d0  test    rax, rax
0x18009c6d3  jz      short loc_18009C6DF
0x18009c6d5  mov     ebx, 1
0x18009c6da  mov     [rbp+57h+AccessMask], ebx
0x18009c6dd  jmp     short loc_18009C6F1
0x18009c6df  xor     ebx, ebx
0x18009c6e1  jmp     short loc_18009C6DA
0x18009c6e3  xor     r15d, r15d
0x18009c6e6  xor     r13d, r13d
0x18009c6e9  mov     [rbp+57h+var_78], r13
0x18009c6ed  mov     [rbp+57h+hMem], r13
0x18009c6f1  xor     esi, esi
0x18009c6f3  xor     edi, edi
0x18009c6f5  test    ebx, ebx
0x18009c6f7  jz      loc_18009C80B
0x18009c6fd  xor     r12d, r12d
0x18009c700  lea     ebx, [rsi+8]
0x18009c703  cmp     r12d, dword ptr [rbp+57h+pAclInformation]
0x18009c707  jnb     loc_18009C7C2
0x18009c70d  mov     rcx, [rbp+57h+pDacl]; pAcl
0x18009c711  lea     r8, [rbp+57h+pAce]; pAce
0x18009c715  mov     edx, r12d; dwAceIndex
0x18009c718  call    cs:__imp_GetAce
0x18009c71e  mov     rax, [rbp+57h+pAce]
0x18009c722  test    [rax+1], bl
0x18009c725  jnz     loc_18009C7BA
0x18009c72b  mov     rcx, [rbp+57h+var_78]
0x18009c72f  lea     rdx, stru_18013DDE8; GenericMapping
0x18009c736  mov     al, [rax]
0x18009c738  mov     [rdi+rcx], al
0x18009c73b  mov     rax, [rbp+57h+pAce]
0x18009c73f  mov     ecx, [rax+4]
0x18009c742  mov     [rbp+57h+AccessMask], ecx
0x18009c745  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18009c749  call    cs:__imp_MapGenericMask
0x18009c74f  mov     eax, [rbp+57h+AccessMask]
0x18009c752  mov     rcx, [rbp+57h+hMem]
0x18009c756  and     al, 0Ch
0x18009c758  neg     al
0x18009c75a  sbb     eax, eax
0x18009c75c  and     eax, 10000000h
0x18009c761  mov     [rcx+rdi*4], eax
0x18009c764  mov     rax, [rbp+57h+pAce]
0x18009c768  mov     cl, [rax+1]
0x18009c76b  mov     [rdi+r13], cl
0x18009c76f  mov     rax, [rbp+57h+pAce]
0x18009c773  add     rax, rbx
0x18009c776  mov     rcx, rax; pSid
0x18009c779  mov     [rbp+57h+pSourceSid], rax
0x18009c77d  call    cs:__imp_GetLengthSid
0x18009c783  mov     edx, eax; uBytes
0x18009c785  mov     ecx, 40h ; '@'; uFlags
0x18009c78a  mov     [rbp+57h+nDestinationSidLength], eax
0x18009c78d  call    cs:__imp_LocalAlloc
0x18009c793  mov     [rbp+57h+var_58], rax
0x18009c797  test    rax, rax
0x18009c79a  jz      loc_18009C83E
0x18009c7a0  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x18009c7a4  mov     rdx, rax; pDestinationSid
0x18009c7a7  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x18009c7aa  call    cs:__imp_CopySid
0x18009c7b0  mov     rax, [rbp+57h+var_58]
0x18009c7b4  mov     [r15+rdi*8], rax
0x18009c7b8  inc     edi
0x18009c7ba  inc     r12d
0x18009c7bd  jmp     loc_18009C703
0x18009c7c2  xor     r9d, r9d
0x18009c7c5  test    edi, edi
0x18009c7c7  jz      short loc_18009C7E0
0x18009c7c9  mov     ecx, esi
0x18009c7cb  mov     rcx, [r15+rcx*8]; pSid
0x18009c7cf  call    cs:__imp_GetLengthSid
0x18009c7d5  add     ebx, 8
0x18009c7d8  inc     esi
0x18009c7da  add     ebx, eax
0x18009c7dc  cmp     esi, edi
0x18009c7de  jb      short loc_18009C7C9
0x18009c7e0  mov     edx, ebx; uBytes
0x18009c7e2  mov     ecx, 40h ; '@'; uFlags
0x18009c7e7  call    cs:__imp_LocalAlloc
0x18009c7ed  mov     rsi, rax
0x18009c7f0  test    rax, rax
0x18009c7f3  jz      short loc_18009C83E
0x18009c7f5  mov     r8d, 2; dwAclRevision
0x18009c7fb  mov     edx, ebx; nAclLength
0x18009c7fd  mov     rcx, rax; pAcl
0x18009c800  call    cs:__imp_InitializeAcl
0x18009c806  mov     ebx, eax
0x18009c808  mov     [rbp+57h+AccessMask], eax
0x18009c80b  xor     r12d, r12d
0x18009c80e  test    ebx, ebx
0x18009c810  jz      short loc_18009C87B
0x18009c812  mov     rbx, [rbp+57h+var_78]
0x18009c816  cmp     r12d, edi
0x18009c819  jnb     short loc_18009C86F
0x18009c81b  cmp     byte ptr [r12+rbx], 0
0x18009c820  mov     edx, 2; dwAceRevision
0x18009c825  mov     rcx, [rbp+57h+hMem]
0x18009c829  mov     r9, [r15+r12*8]; pSid
0x18009c82d  mov     r8d, [rcx+r12*4]; AccessMask
0x18009c831  mov     rcx, rsi; pAcl
0x18009c834  jnz     short loc_18009C842
0x18009c836  call    cs:__imp_AddAccessAllowedAce
0x18009c83c  jmp     short loc_18009C848
0x18009c83e  xor     ebx, ebx
0x18009c840  jmp     short loc_18009C87B
0x18009c842  call    cs:__imp_AddAccessDeniedAce
0x18009c848  cmp     byte ptr [r12+r13], 0
0x18009c84d  jz      short loc_18009C86A
0x18009c84f  lea     r8, [rbp+57h+var_68]; pAce
0x18009c853  mov     edx, r12d; dwAceIndex
0x18009c856  mov     rcx, rsi; pAcl
0x18009c859  call    cs:__imp_GetAce
0x18009c85f  mov     rax, [rbp+57h+var_68]
0x18009c863  mov     cl, [r12+r13]
0x18009c867  mov     [rax+1], cl
0x18009c86a  inc     r12d
0x18009c86d  jmp     short loc_18009C816
0x18009c86f  mov     rax, [rbp+57h+var_50]
0x18009c873  mov     ebx, [rbp+57h+AccessMask]
0x18009c876  mov     [rax], rsi
0x18009c879  xor     esi, esi
0x18009c87b  test    r15, r15
0x18009c87e  jz      short loc_18009C8A2
0x18009c880  xor     r12d, r12d
0x18009c883  test    edi, edi
0x18009c885  jz      short loc_18009C899
0x18009c887  mov     rcx, [r15+r12*8]; hMem
0x18009c88b  call    cs:__imp_LocalFree
0x18009c891  inc     r12d
0x18009c894  cmp     r12d, edi
0x18009c897  jb      short loc_18009C887
0x18009c899  mov     rcx, r15; hMem
0x18009c89c  call    cs:__imp_LocalFree
0x18009c8a2  mov     rax, [rbp+57h+hMem]
0x18009c8a6  test    rax, rax
0x18009c8a9  jz      short loc_18009C8B4
0x18009c8ab  mov     rcx, rax; hMem
0x18009c8ae  call    cs:__imp_LocalFree
0x18009c8b4  test    r13, r13
0x18009c8b7  jz      short loc_18009C8C2
0x18009c8b9  mov     rcx, r13; hMem
0x18009c8bc  call    cs:__imp_LocalFree
0x18009c8c2  mov     rax, [rbp+57h+var_78]
0x18009c8c6  test    rax, rax
0x18009c8c9  jz      short loc_18009C8D4
0x18009c8cb  mov     rcx, rax; hMem
0x18009c8ce  call    cs:__imp_LocalFree
0x18009c8d4  test    rsi, rsi
0x18009c8d7  jz      short loc_18009C8E2
0x18009c8d9  mov     rcx, rsi; hMem
0x18009c8dc  call    cs:__imp_LocalFree
0x18009c8e2  mov     eax, ebx
0x18009c8e4  mov     rcx, [rbp+57h+var_38]
0x18009c8e8  xor     rcx, rsp; StackCookie
0x18009c8eb  call    __security_check_cookie
0x18009c8f0  add     rsp, 90h
0x18009c8f7  pop     r15
0x18009c8f9  pop     r13
0x18009c8fb  pop     r12
0x18009c8fd  pop     rdi
0x18009c8fe  pop     rsi
0x18009c8ff  pop     rbx
0x18009c900  pop     rbp
0x18009c901  retn
```
