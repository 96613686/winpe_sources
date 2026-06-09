# CheckAclInheritance

- ea: `0x18017e8c0`
- end: `0x18017f6a5`
- name: `CheckAclInheritance`
- size: `3557`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, PSECURITY_DESCRIPTOR@<rdx>, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18039fb20`

## callees

- `0x18001e090`
- `0x18017e8c0`
- `0x18017f6ac`
- `0x18017fa2c`
- `0x180453340`
- `0x18047b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18017f64f`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x18017f64f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18017ea2c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18017ea2c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18017e99e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18017e99e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18017eaa8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18017eac5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18017eaa8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18017eac5`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18017eb50`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18017ebbd`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18017eb50`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18017ebbd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18017ea61`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18017ea61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017e9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ea36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ea6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017e9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ea36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ea6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017f67c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017edac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017efdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017efed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f0b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f0cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f14c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f172`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f190`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f2dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f56e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017edac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017efdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017efed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f0b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f0cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f14c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f172`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f190`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f2dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017f56e`

## string_xrefs

- `0x18017f5f0`: `*** Error: GetAce ==> 0x%x - analysis incomplete\n`
- `0x18017e9bc`: `*** Warning: GetSecurityDescriptorControl ==> 0x%x - analysis may be incomplete\n`
- `0x18017e9ed`: `*** Warning: Child has SE_DACL_PROTECTED set, therefore doesn't inherit - skipping test\n`
- `0x18017ea47`: `*** Warning: GetSecurityDescriptorOwner ==> 0x%x - analysis may be incomplete\n`
- `0x18017ea7c`: `*** Warning: GetSecurityDescriptorGroup ==> 0x%x - analysis may be incomplete\n`
- `0x18017f68c`: `*** Error: GetSecurityDescriptorDacl ==> 0x%x - analysis incomplete\n`
- `0x18017f66b`: `*** Error: DACL on parent and/or child is not present  - analysis incomplete\n`

## pseudocode

```c
__int64 __fastcall CheckAclInheritance(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PSECURITY_DESCRIPTOR a2,
        __int64 a3,
        unsigned int a4,
        void (*a5)(const char *, ...),
        int a6,
        int a7,
        DWORD *a8)
{
  DWORD v10; // r13d
  DWORD LastError; // eax
  void (*v12)(const char *, ...); // rbx
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD AceCount; // r12d
  DWORD v17; // edx
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  DWORD i; // esi
  DWORD v24; // ecx
  __int64 v25; // rsi
  _BYTE *v26; // r8
  __int64 *v27; // rax
  int v28; // r14d
  __int64 v29; // r9
  int v30; // r12d
  __int64 j; // rcx
  _QWORD *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  unsigned int v35; // esi
  unsigned int v36; // ecx
  _BYTE *v37; // rdx
  unsigned int v38; // r9d
  __int64 v39; // r8
  const char *v40; // rax
  char v41; // r14
  char v42; // r14
  unsigned int v43; // r12d
  unsigned int v44; // r13d
  __int64 v45; // r8
  __int64 v46; // r8
  const char *v47; // rax
  __int64 v48; // r8
  __int64 v49; // r8
  unsigned int n; // r10d
  const char *v51; // rax
  unsigned int v52; // r14d
  __int64 v53; // r8
  const char *v54; // rax
  const char *v55; // rcx
  unsigned int v56; // r10d
  __int64 v57; // r8
  const char *v58; // rax
  int v59; // r12d
  unsigned int v60; // esi
  unsigned int k; // r14d
  unsigned int v62; // r9d
  __int64 v63; // r8
  const char *v64; // rax
  int v65; // r12d
  unsigned int v66; // esi
  unsigned int m; // r14d
  unsigned int v68; // r9d
  __int64 v69; // r8
  const char *v70; // rax
  DWORD v71; // eax
  __int64 v72; // rsi
  unsigned int v73; // edx
  DWORD v74; // eax
  __int64 v75; // [rsp+20h] [rbp-50h]
  _DWORD v76[2]; // [rsp+70h] [rbp+0h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+8h] BYREF
  __int64 v78; // [rsp+80h] [rbp+10h] BYREF
  DWORD v79; // [rsp+88h] [rbp+18h]
  int v80; // [rsp+8Ch] [rbp+1Ch]
  int v81; // [rsp+90h] [rbp+20h]
  int v82; // [rsp+94h] [rbp+24h]
  LPVOID v83; // [rsp+98h] [rbp+28h] BYREF
  PACL pAcl; // [rsp+A0h] [rbp+30h] BYREF
  WORD pControl[2]; // [rsp+A8h] [rbp+38h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+ACh] [rbp+3Ch] BYREF
  __int64 v87; // [rsp+B0h] [rbp+40h] BYREF
  int v88; // [rsp+B8h] [rbp+48h]
  unsigned int v89; // [rsp+BCh] [rbp+4Ch]
  HLOCAL v90; // [rsp+C0h] [rbp+50h] BYREF
  HLOCAL v91; // [rsp+C8h] [rbp+58h] BYREF
  HLOCAL v92; // [rsp+D0h] [rbp+60h] BYREF
  PSID pGroup; // [rsp+D8h] [rbp+68h] BYREF
  PSID pOwner; // [rsp+E0h] [rbp+70h] BYREF
  WINBOOL bDaclPresent; // [rsp+E8h] [rbp+78h] BYREF
  unsigned int v96; // [rsp+ECh] [rbp+7Ch] BYREF
  unsigned int v97; // [rsp+F0h] [rbp+80h]
  PACL pDacl; // [rsp+F8h] [rbp+88h] BYREF
  DWORD dwRevision; // [rsp+100h] [rbp+90h] BYREF
  unsigned int v100; // [rsp+104h] [rbp+94h]
  DWORD v101; // [rsp+108h] [rbp+98h]
  __int128 v102; // [rsp+110h] [rbp+A0h]
  LPVOID pAce; // [rsp+120h] [rbp+B0h] BYREF
  __int64 v104; // [rsp+128h] [rbp+B8h]
  __int64 v105; // [rsp+130h] [rbp+C0h]
  _DWORD *v106; // [rsp+138h] [rbp+C8h]

  v100 = a4;
  v105 = a3;
  v10 = 0;
  pDacl = 0;
  pAcl = 0;
  v83 = 0;
  pAce = 0;
  bDaclPresent = 0;
  bOwnerDefaulted = 0;
  v102 = 0;
  v78 = 0;
  v87 = 0;
  v96 = 0;
  hMem = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  pOwner = 0;
  pGroup = 0;
  pControl[0] = 0;
  dwRevision = 0;
  if ( !pSecurityDescriptor || !a2 || !a3 || !a4 || !a8 )
    return 0;
  *a8 = 0;
  if ( GetSecurityDescriptorControl(a2, pControl, &dwRevision) )
  {
    v12 = a5;
  }
  else
  {
    LastError = GetLastError();
    v12 = a5;
    if ( a5 )
      a5("*** Warning: GetSecurityDescriptorControl ==> 0x%x - analysis may be incomplete\n", LastError);
  }
  if ( (pControl[0] & 0x1000) != 0 )
  {
    if ( v12 )
    {
      if ( a7 )
        v12("*** Warning: Child has SE_DACL_PROTECTED set, therefore doesn't inherit - skipping test\n");
    }
    return 0;
  }
  if ( !GetSecurityDescriptorOwner(a2, &pOwner, &bOwnerDefaulted) )
  {
    v14 = GetLastError();
    pOwner = 0;
    if ( v12 )
      v12("*** Warning: GetSecurityDescriptorOwner ==> 0x%x - analysis may be incomplete\n", v14);
  }
  if ( !GetSecurityDescriptorGroup(a2, &pGroup, &bOwnerDefaulted) )
  {
    v15 = GetLastError();
    pGroup = 0;
    if ( v12 )
      v12("*** Warning: GetSecurityDescriptorGroup ==> 0x%x - analysis may be incomplete\n", v15);
  }
  pAcl = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bOwnerDefaulted)
    || !GetSecurityDescriptorDacl(a2, &bDaclPresent, &pAcl, &bOwnerDefaulted) )
  {
    v74 = GetLastError();
    *a8 = v74;
    if ( v12 )
      v12("*** Error: GetSecurityDescriptorDacl ==> 0x%x - analysis incomplete\n", v74);
    return 1;
  }
  if ( !pDacl || !pAcl )
  {
    *a8 = 1338;
    if ( v12 )
      v12("*** Error: DACL on parent and/or child is not present  - analysis incomplete\n");
    return 1;
  }
  AceCount = pDacl->AceCount;
  v17 = pAcl->AceCount;
  v89 = v17;
  v18 = 4LL * v17;
  v19 = v18 + 15;
  if ( v18 + 15 < v18 )
    v19 = 0xFFFFFFFFFFFFFF0LL;
  v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
  v21 = alloca(v20);
  v22 = alloca(v20);
  v106 = v76;
  for ( i = 0; i < v17; ++i )
  {
    v76[i] = 0;
    if ( !GetAce(pAcl, i, &pAce) )
    {
LABEL_188:
      v71 = GetLastError();
      *a8 = v71;
      if ( v12 )
        v12("*** Error: GetAce ==> 0x%x - analysis incomplete\n", v71);
      return 2;
    }
    if ( (*((_BYTE *)pAce + 1) & 0x10) != 0 )
      v76[i] = MaskFromAce(pAce, 0);
    v17 = v89;
  }
  v24 = AceCount;
  v101 = AceCount;
  v25 = *((_QWORD *)&v102 + 1);
  v104 = *((_QWORD *)&v102 + 1);
LABEL_34:
  v79 = v10;
  if ( v10 < v24 )
  {
    if ( !GetAce(pDacl, v10, &v83) )
      goto LABEL_188;
    v26 = v83;
    if ( (*((_BYTE *)v83 + 1) & 1) != 0 && v12 )
    {
      v12("*** Warning: Parent ACE [%d] is OBJECT_INHERIT_ACE but DS objects should be CONTAINER_INHERIT_ACE\n", v10);
      v26 = v83;
    }
    LOBYTE(v76[0]) = v26[1] & 3;
    if ( !LOBYTE(v76[0]) )
      goto LABEL_184;
    if ( *v26 > 3u && (v26[8] & 2) != 0 )
    {
      v27 = (__int64 *)(v26 + 28);
      if ( (v26[8] & 1) == 0 )
        v27 = (__int64 *)(v26 + 12);
      v28 = 1;
      v25 = v27[1];
      v104 = v25;
      v29 = *v27;
      *(_QWORD *)&v102 = *v27;
    }
    else
    {
      v28 = 0;
      v29 = v102;
    }
    v81 = v28;
    v30 = 0;
    v82 = 0;
    if ( v28 )
    {
      for ( j = 0; (unsigned int)j < v100; j = (unsigned int)(j + 1) )
      {
        v32 = *(_QWORD **)(v105 + 8 * j);
        v33 = *v32 - v29;
        if ( *v32 == v29 )
          v33 = v32[1] - v25;
        if ( !v33 )
        {
          v30 = 1;
          v82 = 1;
          break;
        }
      }
    }
    v34 = MaskFromAce(v26, 0);
    v80 = v34;
    v35 = 1;
    v36 = 0;
    while ( 1 )
    {
      v97 = v36;
      if ( v36 >= 0x20 )
      {
        if ( (*((_BYTE *)v83 + 1) & 4) == 0 )
        {
          v59 = MaskFromAce(v83, 0);
          v60 = 1;
          for ( k = 0; k < 0x20; ++k )
          {
            if ( (v60 & v59 & 0xF0000000) != 0 )
            {
              FindAce(
                pAcl,
                0,
                v82,
                (__int64)&v78,
                (__int64)&hMem,
                (__int64)v12,
                LOBYTE(v76[0]) | 0x18,
                0,
                0,
                (__int64)&v78 + 4);
              v62 = v78;
              if ( (_DWORD)v78 )
              {
                v63 = 0;
                do
                {
                  v76[*((unsigned int *)hMem + v63)] &= ~v60;
                  v63 = (unsigned int)(v63 + 1);
                }
                while ( (unsigned int)v63 < v62 );
                if ( v12 && a7 )
                {
                  v64 = "(and others)";
                  if ( v62 <= 1 )
                    v64 = (const char *)&word_18049B11A;
                  v12(
                    "(Debug) Parent ACE [%d] generic Mask [0x%x] found in child ACE [%d] %s\n",
                    v10,
                    v60,
                    *(unsigned int *)hMem,
                    v64);
                }
                LocalFree(hMem);
              }
              else
              {
                if ( v12 )
                  v12("*** Error: Parent ACE [%d] generic Mask [0x%x] not found in child\n", v10, v60);
                if ( !a6 )
                  return 3;
              }
            }
            v60 *= 2;
          }
          v28 = v81;
        }
        if ( !v28 || v82 )
        {
          v65 = MaskFromAce(v83, 1);
          v66 = 1;
          for ( m = 0; m < 0x20; ++m )
          {
            if ( (v65 & v66) != 0 )
            {
              FindAce(
                pAcl,
                (__int64)pGroup,
                v82,
                (__int64)&v78,
                (__int64)&hMem,
                (__int64)v12,
                16,
                8,
                1,
                (__int64)&v78 + 4);
              v68 = v78;
              if ( (_DWORD)v78 )
              {
                v69 = 0;
                do
                {
                  v76[*((unsigned int *)hMem + v69)] &= ~v66;
                  v69 = (unsigned int)(v69 + 1);
                }
                while ( (unsigned int)v69 < v68 );
                if ( v12 && a7 )
                {
                  v70 = "(and others)";
                  if ( v68 <= 1 )
                    v70 = (const char *)&word_18049B11A;
                  v12(
                    "(Debug) Parent ACE [%d] implied Mask [0x%x] found in child ACE [%d] %s\n",
                    v10,
                    v66,
                    *(unsigned int *)hMem,
                    v70);
                }
                LocalFree(hMem);
              }
              else
              {
                if ( v12 )
                  v12("*** Error: Parent ACE [%d] implied Mask [0x%x] not found in child\n", v10, v66);
                if ( !a6 )
                  return 3;
              }
            }
            v66 *= 2;
          }
        }
        v25 = v104;
LABEL_184:
        ++v10;
        v24 = v101;
        goto LABEL_34;
      }
      if ( (v35 & v34 & 0xFFFFFFF) != 0 )
        break;
LABEL_146:
      v35 *= 2;
      v36 = v97 + 1;
      v30 = v82;
    }
    if ( !v28 || v30 )
    {
      v37 = v83;
      if ( (*((_BYTE *)v83 + 1) & 4) == 0 )
      {
        v41 = v76[0];
        FindAce(
          pAcl,
          0,
          v30,
          (__int64)&v78,
          (__int64)&hMem,
          (__int64)v12,
          LOBYTE(v76[0]) | 0x18,
          0,
          0,
          (__int64)&v78 + 4);
        FindAce(
          pAcl,
          (__int64)pGroup,
          v30,
          (__int64)&v87,
          (__int64)&v90,
          (__int64)v12,
          16,
          v41 | 8,
          0,
          (__int64)&v78 + 4);
        v42 = v41 | 0x10;
        FindAce(
          pAcl,
          (__int64)pGroup,
          v30,
          (__int64)&v87 + 4,
          (__int64)&v91,
          (__int64)v12,
          v42,
          8,
          0,
          (__int64)&v78 + 4);
        if ( !HIDWORD(v87) || (v88 = 1, !HIDWORD(v78)) )
          v88 = 0;
        FindAce(pAcl, 0, v30, (__int64)&v96, (__int64)&v92, (__int64)v12, v42, 8, 0, (__int64)&v78 + 4);
        v43 = v78;
        v44 = v87;
        if ( (_DWORD)v78 )
        {
          if ( (_DWORD)v87 )
          {
            v45 = 0;
            do
            {
              v76[*((unsigned int *)hMem + v45)] &= ~v35;
              v45 = (unsigned int)(v45 + 1);
            }
            while ( (unsigned int)v45 < v43 );
            v46 = 0;
            do
            {
              v76[*((unsigned int *)v90 + v46)] &= ~v35;
              v46 = (unsigned int)(v46 + 1);
            }
            while ( (unsigned int)v46 < v44 );
            if ( v12 && a7 )
            {
              if ( v43 > 1 || (v47 = (const char *)&word_18049B11A, v44 > 1) )
                v47 = "(and others)";
              LODWORD(v75) = *(_DWORD *)v90;
              v12(
                "(Debug) Parent ACE [%d] specific Mask [0x%x] split into child ACEs [%d] and [%d] %s\n",
                v79,
                v35,
                *(unsigned int *)hMem,
                v75,
                v47);
            }
            LocalFree(hMem);
            hMem = 0;
            LocalFree(v90);
            v90 = 0;
          }
          else if ( v88 )
          {
            v48 = 0;
            do
            {
              v76[*((unsigned int *)hMem + v48)] &= ~v35;
              v48 = (unsigned int)(v48 + 1);
            }
            while ( (unsigned int)v48 < v43 );
            v49 = 0;
            for ( n = HIDWORD(v87); (unsigned int)v49 < n; v49 = (unsigned int)(v49 + 1) )
              v76[*((unsigned int *)v91 + v49)] &= ~v35;
            if ( v12 && a7 )
            {
              if ( v43 > 1 || (v51 = (const char *)&word_18049B11A, n > 1) )
                v51 = "(and others)";
              LODWORD(v75) = *(_DWORD *)v91;
              v12(
                "(Debug) Parent ACE [%d] specific Mask [0x%x] split1 into child ACEs [%d] and [%d] %s\n",
                v79,
                v35,
                *(unsigned int *)hMem,
                v75,
                v51);
            }
            LocalFree(hMem);
            hMem = 0;
            LocalFree(v91);
            v91 = 0;
          }
        }
        v52 = v96;
        if ( v96 )
        {
          v53 = 0;
          do
          {
            v76[*((unsigned int *)v92 + v53)] &= ~v35;
            v53 = (unsigned int)(v53 + 1);
          }
          while ( (unsigned int)v53 < v52 );
          if ( v12 && a7 )
          {
            v54 = "(and others)";
            if ( v52 <= 1 )
              v54 = (const char *)&word_18049B11A;
            v12(
              "(Debug) Parent ACE [%d] specific Mask [0x%x] found in child ACE [%d] %s\n",
              v79,
              v35,
              *(unsigned int *)v92,
              v54);
          }
          LocalFree(v92);
          v92 = 0;
        }
        if ( hMem )
          LocalFree(hMem);
        if ( v90 )
          LocalFree(v90);
        if ( v91 )
          LocalFree(v91);
        if ( v92 )
          LocalFree(v92);
        if ( v43 && (v44 || v88) )
        {
          v10 = v79;
        }
        else
        {
          v10 = v79;
          if ( !v52 )
          {
            if ( v12 )
              v12("*** Error: Parent ACE [%d] specific Mask [0x%x] not found1 in child\n", v79, v35);
            if ( !a6 )
              return 3;
          }
        }
        v28 = v81;
        goto LABEL_145;
      }
    }
    else
    {
      v37 = v83;
    }
    if ( !v28 || v30 )
    {
      if ( (v37[1] & 4) == 0 )
      {
        if ( v12 )
          v12("*** Error: Algorithm failure - unexpected condition!\n");
        return 4;
      }
    }
    else if ( (v37[1] & 4) == 0 )
    {
      FindAce(pAcl, 0, 0, (__int64)&v78, (__int64)&hMem, (__int64)v12, LOBYTE(v76[0]) | 0x18, 0, 0, (__int64)&v78 + 4);
      v38 = v78;
      if ( (_DWORD)v78 )
      {
        v39 = 0;
        do
        {
          v76[*((unsigned int *)hMem + v39)] &= ~v35;
          v39 = (unsigned int)(v39 + 1);
        }
        while ( (unsigned int)v39 < v38 );
        if ( v12 && a7 )
        {
          v40 = "(and others)";
          if ( v38 <= 1 )
            v40 = (const char *)&word_18049B11A;
          v12(
            "(Debug) Parent ACE [%d] specific Mask [0x%x] found in child ACE [%d] %s\n",
            v10,
            v35,
            *(unsigned int *)hMem,
            v40);
        }
        LocalFree(hMem);
LABEL_145:
        v34 = v80;
        goto LABEL_146;
      }
      if ( v12 )
      {
        v55 = "*** Error: Parent ACE [%d] specific Mask [0x%x] not found2 in child\n";
LABEL_140:
        v12(v55, v10, v35);
        goto LABEL_141;
      }
      goto LABEL_141;
    }
    FindAce(
      pAcl,
      (__int64)pGroup,
      v30,
      (__int64)&v78,
      (__int64)&hMem,
      (__int64)v12,
      16,
      LOBYTE(v76[0]) | 8,
      0,
      (__int64)&v78 + 4);
    v56 = v78;
    if ( (_DWORD)v78 )
    {
      v57 = 0;
      do
      {
        v76[*((unsigned int *)hMem + v57)] &= ~v35;
        v57 = (unsigned int)(v57 + 1);
      }
      while ( (unsigned int)v57 < v56 );
      if ( v12 && a7 )
      {
        v58 = "(and others)";
        if ( v56 <= 1 )
          v58 = (const char *)&word_18049B11A;
        v12(
          "(Debug) Parent (NO_PROPAGATE_INHERIT) ACE [%d] specific Mask [0x%x] found in child ACE [%d] %s\n",
          v10,
          v35,
          *(unsigned int *)hMem,
          v58);
      }
      LocalFree(hMem);
      hMem = 0;
      goto LABEL_145;
    }
    if ( v12 )
    {
      v55 = "*** Error: Parent ACE [%d] specific Mask [0x%x] not found1 in child\n";
      goto LABEL_140;
    }
LABEL_141:
    if ( !a6 )
      return 3;
    goto LABEL_145;
  }
  v72 = 0;
  v73 = v89;
  while ( (unsigned int)v72 < v73 )
  {
    if ( v76[v72] )
    {
      if ( v12 )
      {
        v12(
          "*** Error: Child ACE [%d] Mask [0x%x] is INHERITED_ACE but there is no such inheritable ACE on parent\n",
          (unsigned int)v72);
        v73 = v89;
      }
      if ( !a6 )
        return 5;
    }
    v72 = (unsigned int)(v72 + 1);
  }
  return 0;
}

```

## disassembly

```asm
0x18017e8c0  push    rbp
0x18017e8c2  push    rbx
0x18017e8c3  push    rsi
0x18017e8c4  push    rdi
0x18017e8c5  push    r12
0x18017e8c7  push    r13
0x18017e8c9  push    r14
0x18017e8cb  push    r15
0x18017e8cd  sub     rsp, 158h
0x18017e8d4  lea     rbp, [rsp+70h]
0x18017e8d9  mov     rax, cs:__security_cookie
0x18017e8e0  xor     rax, rbp
0x18017e8e3  mov     [rbp+120h+var_50], rax
0x18017e8ea  mov     [rbp+120h+var_8C], r9d
0x18017e8f1  mov     [rbp+120h+var_60], r8
0x18017e8f8  mov     rdi, rdx
0x18017e8fb  mov     rsi, rcx
0x18017e8fe  xor     r13d, r13d
0x18017e901  mov     [rbp+120h+pDacl], r13
0x18017e908  mov     [rbp+120h+pAcl], r13
0x18017e90c  mov     [rbp+120h+var_F8], r13
0x18017e910  mov     [rbp+120h+pAce], r13
0x18017e917  mov     [rbp+120h+bDaclPresent], r13d
0x18017e91b  mov     [rbp+120h+bOwnerDefaulted], r13d
0x18017e91f  xorps   xmm0, xmm0
0x18017e922  movups  [rbp+120h+var_80], xmm0
0x18017e929  mov     dword ptr [rbp+120h+var_110], r13d
0x18017e92d  mov     dword ptr [rbp+120h+var_E0], r13d
0x18017e931  mov     dword ptr [rbp+120h+var_E0+4], r13d
0x18017e935  mov     dword ptr [rbp+120h+var_A4], r13d
0x18017e939  mov     [rbp+120h+hMem], r13
0x18017e93d  mov     [rbp+120h+var_D0], r13
0x18017e941  mov     [rbp+120h+var_C8], r13
0x18017e945  mov     [rbp+120h+var_C0], r13
0x18017e949  mov     [rbp+120h+pOwner], r13
0x18017e94d  mov     [rbp+120h+pGroup], r13
0x18017e951  mov     dword ptr [rbp+120h+var_110+4], r13d
0x18017e955  mov     [rbp+120h+pControl], r13w
0x18017e95a  mov     [rbp+120h+dwRevision], r13d
0x18017e961  test    rcx, rcx
0x18017e964  jz      loc_18017E9FC
0x18017e96a  test    rdx, rdx
0x18017e96d  jz      loc_18017E9FC
0x18017e973  test    r8, r8
0x18017e976  jz      loc_18017E9FC
0x18017e97c  test    r9d, r9d
0x18017e97f  jz      short loc_18017E9FC
0x18017e981  mov     r14, [rbp+120h+arg_38]
0x18017e988  test    r14, r14
0x18017e98b  jz      short loc_18017E9FC
0x18017e98d  mov     [r14], r13d
0x18017e990  lea     r8, [rbp+120h+dwRevision]; lpdwRevision
0x18017e997  lea     rdx, [rbp+120h+pControl]; pControl
0x18017e99b  mov     rcx, rdi; pSecurityDescriptor
0x18017e99e  call    cs:__imp_GetSecurityDescriptorControl
0x18017e9a4  test    eax, eax
0x18017e9a6  jnz     short loc_18017E9CD
0x18017e9a8  call    cs:__imp_GetLastError
0x18017e9ae  mov     rbx, [rbp+120h+arg_20]
0x18017e9b5  test    rbx, rbx
0x18017e9b8  jz      short loc_18017E9D4
0x18017e9ba  mov     edx, eax
0x18017e9bc  lea     rcx, aWarningGetsecu_1; "*** Warning: GetSecurityDescriptorContr"...
0x18017e9c3  mov     rax, rbx
0x18017e9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e9cb  jmp     short loc_18017E9D4
0x18017e9cd  mov     rbx, [rbp+120h+arg_20]
0x18017e9d4  mov     eax, 1000h
0x18017e9d9  test    [rbp+120h+pControl], ax
0x18017e9dd  jz      short loc_18017EA21
0x18017e9df  test    rbx, rbx
0x18017e9e2  jz      short loc_18017E9FC
0x18017e9e4  cmp     [rbp+120h+arg_30], r13d
0x18017e9eb  jz      short loc_18017E9FC
0x18017e9ed  lea     rcx, aWarningChildHa; "*** Warning: Child has SE_DACL_PROTECTE"...
0x18017e9f4  mov     rax, rbx
0x18017e9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017e9fc  xor     eax, eax
0x18017e9fe  mov     rcx, [rbp+120h+var_50]
0x18017ea05  xor     rcx, rbp; StackCookie
0x18017ea08  call    __security_check_cookie
0x18017ea0d  lea     rsp, [rbp+0E8h]
0x18017ea14  pop     r15
0x18017ea16  pop     r14
0x18017ea18  pop     r13
0x18017ea1a  pop     r12
0x18017ea1c  pop     rdi
0x18017ea1d  pop     rsi
0x18017ea1e  pop     rbx
0x18017ea1f  pop     rbp
0x18017ea20  retn
0x18017ea21  lea     r8, [rbp+120h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18017ea25  lea     rdx, [rbp+120h+pOwner]; pOwner
0x18017ea29  mov     rcx, rdi; pSecurityDescriptor
0x18017ea2c  call    cs:__imp_GetSecurityDescriptorOwner
0x18017ea32  test    eax, eax
0x18017ea34  jnz     short loc_18017EA56
0x18017ea36  call    cs:__imp_GetLastError
0x18017ea3c  mov     [rbp+120h+pOwner], r13
0x18017ea40  test    rbx, rbx
0x18017ea43  jz      short loc_18017EA56
0x18017ea45  mov     edx, eax
0x18017ea47  lea     rcx, aWarningGetsecu_0; "*** Warning: GetSecurityDescriptorOwner"...
0x18017ea4e  mov     rax, rbx
0x18017ea51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea56  lea     r8, [rbp+120h+bOwnerDefaulted]; lpbGroupDefaulted
0x18017ea5a  lea     rdx, [rbp+120h+pGroup]; pGroup
0x18017ea5e  mov     rcx, rdi; pSecurityDescriptor
0x18017ea61  call    cs:__imp_GetSecurityDescriptorGroup
0x18017ea67  test    eax, eax
0x18017ea69  jnz     short loc_18017EA8B
0x18017ea6b  call    cs:__imp_GetLastError
0x18017ea71  mov     [rbp+120h+pGroup], r13
0x18017ea75  test    rbx, rbx
0x18017ea78  jz      short loc_18017EA8B
0x18017ea7a  mov     edx, eax
0x18017ea7c  lea     rcx, aWarningGetsecu; "*** Warning: GetSecurityDescriptorGroup"...
0x18017ea83  mov     rax, rbx
0x18017ea86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ea8b  mov     [rbp+120h+pAcl], r13
0x18017ea8f  mov     [rbp+120h+pDacl], r13
0x18017ea96  lea     r9, [rbp+120h+bOwnerDefaulted]; lpbDaclDefaulted
0x18017ea9a  lea     r8, [rbp+120h+pDacl]; pDacl
0x18017eaa1  lea     rdx, [rbp+120h+bDaclPresent]; lpbDaclPresent
0x18017eaa5  mov     rcx, rsi; pSecurityDescriptor
0x18017eaa8  call    cs:__imp_GetSecurityDescriptorDacl
0x18017eaae  test    eax, eax
0x18017eab0  jz      loc_18017F67C
0x18017eab6  lea     r9, [rbp+120h+bOwnerDefaulted]; lpbDaclDefaulted
0x18017eaba  lea     r8, [rbp+120h+pAcl]; pDacl
0x18017eabe  lea     rdx, [rbp+120h+bDaclPresent]; lpbDaclPresent
0x18017eac2  mov     rcx, rdi; pSecurityDescriptor
0x18017eac5  call    cs:__imp_GetSecurityDescriptorDacl
0x18017eacb  test    eax, eax
0x18017eacd  jz      loc_18017F67C
0x18017ead3  mov     rax, [rbp+120h+pDacl]
0x18017eada  test    rax, rax
0x18017eadd  jz      loc_18017F65F
0x18017eae3  mov     rcx, [rbp+120h+pAcl]
0x18017eae7  test    rcx, rcx
0x18017eaea  jz      loc_18017F65F
0x18017eaf0  movzx   r12d, word ptr [rax+4]
0x18017eaf5  movzx   edx, word ptr [rcx+4]
0x18017eaf9  mov     [rbp+120h+var_D4], edx
0x18017eafc  mov     eax, edx
0x18017eafe  shl     rax, 2
0x18017eb02  lea     rcx, [rax+0Fh]
0x18017eb06  cmp     rcx, rax
0x18017eb09  ja      short loc_18017EB15
0x18017eb0b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18017eb15  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18017eb19  mov     rax, rcx
0x18017eb1c  call    _alloca_probe
0x18017eb21  sub     rsp, rcx
0x18017eb24  lea     r15, [rsp+190h+var_120]
0x18017eb29  mov     [rbp+120h+var_58], r15
0x18017eb30  mov     esi, r13d
0x18017eb33  mov     edi, 1
0x18017eb38  cmp     esi, edx
0x18017eb3a  jnb     short loc_18017EB7D
0x18017eb3c  mov     r14d, esi
0x18017eb3f  mov     [r15+r14*4], r13d
0x18017eb43  lea     r8, [rbp+120h+pAce]; pAce
0x18017eb4a  mov     edx, esi; dwAceIndex
0x18017eb4c  mov     rcx, [rbp+120h+pAcl]; pAcl
0x18017eb50  call    cs:__imp_GetAce
0x18017eb56  test    eax, eax
0x18017eb58  jz      loc_18017F5DA
0x18017eb5e  mov     rcx, [rbp+120h+pAce]
0x18017eb65  test    byte ptr [rcx+1], 10h
0x18017eb69  jz      short loc_18017EB76
0x18017eb6b  xor     edx, edx
0x18017eb6d  call    MaskFromAce
0x18017eb72  mov     [r15+r14*4], eax
0x18017eb76  add     esi, edi
0x18017eb78  mov     edx, [rbp+120h+var_D4]
0x18017eb7b  jmp     short loc_18017EB38
0x18017eb7d  mov     ecx, r12d
0x18017eb80  mov     [rbp+120h+var_88], ecx
0x18017eb86  mov     rsi, qword ptr [rbp+120h+var_80+8]
0x18017eb8d  mov     [rbp+120h+var_68], rsi
0x18017eb94  mov     rax, qword ptr [rbp+120h+var_80]
0x18017eb9b  mov     qword ptr [rbp+120h+var_80], rax
0x18017eba2  mov     [rbp+120h+var_108], r13d
0x18017eba6  cmp     r13d, ecx
0x18017eba9  jnb     loc_18017F609
0x18017ebaf  lea     r8, [rbp+120h+var_F8]; pAce
0x18017ebb3  mov     edx, r13d; dwAceIndex
0x18017ebb6  mov     rcx, [rbp+120h+pDacl]; pAcl
0x18017ebbd  call    cs:__imp_GetAce
0x18017ebc3  test    eax, eax
0x18017ebc5  jz      loc_18017F5DA
0x18017ebcb  mov     r8, [rbp+120h+var_F8]
0x18017ebcf  test    [r8+1], dil
0x18017ebd3  jz      short loc_18017EBF0
0x18017ebd5  test    rbx, rbx
0x18017ebd8  jz      short loc_18017EBF0
0x18017ebda  mov     edx, r13d
0x18017ebdd  lea     rcx, aWarningParentA; "*** Warning: Parent ACE [%d] is OBJECT_"...
0x18017ebe4  mov     rax, rbx
0x18017ebe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ebec  mov     r8, [rbp+120h+var_F8]
0x18017ebf0  mov     al, [r8+1]
0x18017ebf4  and     al, 3
0x18017ebf6  mov     [rbp+120h+var_120], al
0x18017ebf9  jz      loc_18017F5AE
0x18017ebff  cmp     byte ptr [r8], 3
0x18017ec03  jbe     short loc_18017EC36
0x18017ec05  test    byte ptr [r8+8], 2
0x18017ec0a  jz      short loc_18017EC36
0x18017ec0c  lea     rcx, [r8+0Ch]
0x18017ec10  test    [r8+8], dil
0x18017ec14  lea     rax, [rcx+10h]
0x18017ec18  cmovz   rax, rcx
0x18017ec1c  mov     r14d, edi
0x18017ec1f  mov     rsi, [rax+8]
0x18017ec23  mov     [rbp+120h+var_68], rsi
0x18017ec2a  mov     r9, [rax]
0x18017ec2d  mov     qword ptr [rbp+120h+var_80], r9
0x18017ec34  jmp     short loc_18017EC40
0x18017ec36  xor     r14d, r14d
0x18017ec39  mov     r9, qword ptr [rbp+120h+var_80]
0x18017ec40  mov     [rbp+120h+var_100], r14d
0x18017ec44  xor     r12d, r12d
0x18017ec47  mov     [rbp+120h+var_FC], r12d
0x18017ec4b  test    r14d, r14d
0x18017ec4e  jz      short loc_18017EC83
0x18017ec50  xor     ecx, ecx
0x18017ec52  cmp     ecx, [rbp+120h+var_8C]
0x18017ec58  jnb     short loc_18017EC83
0x18017ec5a  mov     rdx, [rbp+120h+var_60]
0x18017ec61  mov     rdx, [rdx+rcx*8]
0x18017ec65  mov     rax, [rdx]
0x18017ec68  sub     rax, r9
0x18017ec6b  jnz     short loc_18017EC74
0x18017ec6d  mov     rax, [rdx+8]
0x18017ec71  sub     rax, rsi
0x18017ec74  test    rax, rax
0x18017ec77  jz      short loc_18017EC7D
0x18017ec79  add     ecx, edi
0x18017ec7b  jmp     short loc_18017EC52
0x18017ec7d  mov     r12d, edi
0x18017ec80  mov     [rbp+120h+var_FC], edi
0x18017ec83  xor     edx, edx
0x18017ec85  mov     rcx, r8
0x18017ec88  call    MaskFromAce
0x18017ec8d  mov     [rbp+120h+var_104], eax
0x18017ec90  mov     esi, edi
0x18017ec92  xor     ecx, ecx
0x18017ec94  mov     dword ptr [rbp+120h+var_A4+4], ecx
0x18017ec9a  cmp     ecx, 20h ; ' '
0x18017ec9d  jnb     loc_18017F333
0x18017eca3  mov     ecx, eax
0x18017eca5  and     ecx, esi
0x18017eca7  test    ecx, 0FFFFFFFh
0x18017ecad  jz      loc_18017F320
0x18017ecb3  test    r14d, r14d
0x18017ecb6  jz      loc_18017EDB7
0x18017ecbc  test    r12d, r12d
0x18017ecbf  jnz     loc_18017EDB7
0x18017ecc5  mov     rdx, [rbp+120h+var_F8]
0x18017ecc9  test    r14d, r14d
0x18017eccc  jz      loc_18017F20B
0x18017ecd2  test    r12d, r12d
0x18017ecd5  jnz     loc_18017F20B
0x18017ecdb  test    byte ptr [rdx+1], 4
0x18017ecdf  jnz     loc_18017F215
0x18017ece5  mov     al, [rbp+120h+var_120]
0x18017ece8  or      al, 18h
0x18017ecea  lea     rcx, [rbp+120h+var_110+4]
0x18017ecee  mov     [rsp+190h+var_130], rcx; __int64
0x18017ecf3  mov     [rsp+190h+var_138], r12d; int
0x18017ecf8  mov     [rsp+190h+var_140], r12b; char
0x18017ecfd  mov     [rsp+190h+var_148], al; char
0x18017ed01  mov     [rsp+190h+var_150], rbx; __int64
0x18017ed06  lea     rax, [rbp+120h+hMem]
0x18017ed0a  mov     [rsp+190h+var_158], rax; __int64
0x18017ed0f  lea     rax, [rbp+120h+var_110]
0x18017ed13  mov     [rsp+190h+var_160], rax; __int64
0x18017ed18  mov     [rsp+190h+var_168], r12d; int
0x18017ed1d  mov     [rsp+190h+var_170], 0; __int64
0x18017ed26  xor     r9d, r9d
0x18017ed29  mov     r8d, esi
0x18017ed2c  mov     rcx, [rbp+120h+pAcl]; pAcl
0x18017ed30  call    FindAce
0x18017ed35  mov     r9d, dword ptr [rbp+120h+var_110]
0x18017ed39  test    r9d, r9d
0x18017ed3c  jz      loc_18017F1F6
0x18017ed42  xor     r8d, r8d
0x18017ed45  test    r9d, r9d
0x18017ed48  jz      short loc_18017ED64
0x18017ed4a  mov     r10d, esi
0x18017ed4d  not     r10d
0x18017ed50  mov     rax, [rbp+120h+hMem]
0x18017ed54  mov     edx, [rax+r8*4]
0x18017ed58  and     [r15+rdx*4], r10d
0x18017ed5c  add     r8d, edi
0x18017ed5f  cmp     r8d, r9d
0x18017ed62  jb      short loc_18017ED50
0x18017ed64  test    rbx, rbx
  ... truncated ...
```
