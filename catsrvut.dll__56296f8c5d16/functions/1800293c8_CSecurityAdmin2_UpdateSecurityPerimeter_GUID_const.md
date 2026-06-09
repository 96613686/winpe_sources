# CSecurityAdmin2::UpdateSecurityPerimeter(_GUID const &)

- ea: `0x1800293c8`
- end: `0x18002993e`
- name: `?UpdateSecurityPerimeter@CSecurityAdmin2@@QEAAJAEBU_GUID@@@Z`
- size: `1398`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180026b60`
- `0x1800286b0`

## callees

- `0x1800269a8`
- `0x180026af4`
- `0x1800293c8`
- `0x18002ae90`
- `0x18005582e`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800294ce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800294ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800296b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800296b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800297f3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800296e8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800296e8`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180029625`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180029625`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800295e2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800295e2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800296fb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029814`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800296fb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180029814`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029689`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180029689`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800296a5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800296a5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800296cc`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800296cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800298d5`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x180029761`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x180029761`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029715`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029726`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029715`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029726`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityAdmin2::UpdateSecurityPerimeter(
        struct ISimpleTableDispenser **this,
        const struct _GUID *a2)
{
  struct _ACL *v2; // rdi
  int Table; // ebx
  CSecurityAdmin2 *v4; // rcx
  const struct _GUID *v5; // r8
  DWORD v6; // esi
  int v7; // r14d
  int AclSize; // eax
  struct _ACL *v9; // rax
  CSecurityAdmin2 *v10; // rcx
  unsigned __int16 *v11; // rsi
  unsigned int v12; // r8d
  size_t v13; // rbx
  SIZE_T v14; // rdx
  char *v15; // rax
  signed int v16; // eax
  signed int LastError; // eax
  unsigned int nSubAuthority4; // [rsp+30h] [rbp-D0h]
  unsigned int nSubAuthority4a; // [rsp+30h] [rbp-D0h]
  ULONG pSizeNewSD; // [rsp+60h] [rbp-A0h] BYREF
  void *v22; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR pNewSD; // [rsp+78h] [rbp-88h] BYREF
  void *v25; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp-78h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  PACL pDacl; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v32[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v33; // [rsp+C0h] [rbp-40h]
  int v34; // [rsp+C4h] [rbp-3Ch]
  _QWORD v35[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+DCh] [rbp-24h]
  struct _TRUSTEE_W pGroup; // [rsp+E0h] [rbp-20h] BYREF
  struct _TRUSTEE_W pTrustee; // [rsp+100h] [rbp+0h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+120h] [rbp+20h] BYREF

  v32[0] = a2;
  v32[1] = 0;
  v33 = 72;
  v34 = 16;
  v35[0] = a2;
  v35[1] = 0;
  v36 = 72;
  v37 = 16;
  ppv = 0;
  v25 = 0;
  v22 = 0;
  v2 = 0;
  pDacl = 0;
  pSizeNewSD = 0;
  pSecurityDescriptor = 0;
  pNewSD = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  memset(&pGroup, 0, sizeof(pGroup));
  Table = CSecurityAdmin2::GetTable(
            (CSecurityAdmin2 *)this,
            this[2],
            (const struct _GUID *)0x48,
            &tidCOMSERVICES_ROLESDCACHE,
            v32,
            (void *)1,
            nSubAuthority4,
            0x20001u,
            &v25);
  if ( Table < 0 )
    goto LABEL_44;
  Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v25 + 24LL))(v25);
  if ( Table < 0 )
    goto LABEL_44;
  Table = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Table < 0 )
    goto LABEL_44;
  Table = CSecurityAdmin2::GetTable(v4, ppv, v5, &TID_APPLICATION, v35, (void *)1, nSubAuthority4a, 0x20000u, &v22);
  (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( Table < 0 )
    goto LABEL_44;
  Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v22 + 24LL))(v22);
  if ( Table < 0 )
    goto LABEL_44;
  v6 = 8;
  Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v22 + 48LL))(v22, 0);
  if ( Table < 0 )
    goto LABEL_44;
  while ( 2 )
  {
    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v25 + 32LL))(v25);
    if ( Table < 0 )
      goto LABEL_44;
    v7 = 0;
    while ( (*(int (__fastcall **)(void *))(*(_QWORD *)v25 + 40LL))(v25) >= 0 )
    {
      Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v25 + 64LL))(
                v25,
                2,
                0,
                0,
                &pSecurityDescriptor);
      if ( Table < 0 )
        goto LABEL_44;
      if ( !pSecurityDescriptor )
        goto LABEL_34;
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        goto LABEL_32;
      if ( bDaclPresent && pDacl )
      {
        AclSize = pDacl->AclSize;
        if ( v2 )
        {
          if ( !AddAce(v2, 2u, 0xFFFFFFFF, &pDacl[1], AclSize - 8) )
            goto LABEL_32;
        }
        else
        {
          v6 += AclSize - 8;
        }
      }
      ++v7;
    }
    if ( !v2 )
    {
      *(_DWORD *)pIdentifierAuthority.Value = 0;
      *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
      pSid = 0;
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        goto LABEL_32;
      if ( !pSid )
      {
LABEL_34:
        Table = -2147418113;
        goto LABEL_44;
      }
      v6 += GetLengthSid(pSid) + 8;
      v9 = (struct _ACL *)CoTaskMemAlloc(v6);
      v2 = v9;
      if ( v9 )
      {
        if ( InitializeAcl(v9, v6, 2u) && AddAccessAllowedAce(v2, 2u, 1u, pSid) )
        {
          FreeSid(pSid);
          if ( v7 )
            continue;
          break;
        }
        LastError = GetLastError();
        Table = LastError;
        if ( LastError > 0 )
          Table = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        Table = -2147024882;
      }
      FreeSid(pSid);
      goto LABEL_44;
    }
    break;
  }
  BuildTrusteeWithNameW(&pTrustee, (LPWSTR)L"CURRENT_USER");
  BuildTrusteeWithNameW(&pGroup, (LPWSTR)L"CURRENT_USER");
  pGroup.TrusteeType = TRUSTEE_IS_GROUP;
  if ( BuildSecurityDescriptorW(&pTrustee, &pGroup, 0, 0, 0, 0, 0, &pSizeNewSD, &pNewSD) )
  {
LABEL_32:
    v16 = GetLastError();
    Table = v16;
    if ( v16 > 0 )
      Table = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_44;
  }
  Src = 0;
  Table = CSecurityAdmin2::OptimizeAcl(v10, v2, (struct _ACL **)&Src);
  if ( Table >= 0 )
  {
    v11 = (unsigned __int16 *)Src;
    if ( Src )
    {
      CoTaskMemFree(v2);
      v2 = (struct _ACL *)v11;
      v13 = v11[1];
      v14 = (unsigned int)v13 + pSizeNewSD;
      if ( (unsigned int)v14 < pSizeNewSD )
      {
        Table = -2147024362;
      }
      else
      {
        v15 = (char *)SmartLocalReAlloc(pNewSD, v14, v12);
        if ( v15 )
        {
          pNewSD = v15;
          memcpy_0(&v15[pSizeNewSD], v11, v13);
          *((_DWORD *)pNewSD + 4) = pSizeNewSD;
          *((_WORD *)pNewSD + 1) &= ~0x10u;
          pSizeNewSD += v13;
          Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v22 + 128LL))(v22);
          if ( Table >= 0 )
          {
            Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v22 + 160LL))(
                      v22,
                      23,
                      pSizeNewSD,
                      pNewSD);
            if ( Table >= 0 )
            {
              Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v22 + 144LL))(v22);
              if ( Table >= 0 )
                Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v22 + 96LL))(v22);
            }
          }
        }
        else
        {
          Table = -2147024882;
        }
      }
    }
  }
LABEL_44:
  if ( pNewSD )
    LocalFree(pNewSD);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v25 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v22 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x1800293c8  mov     [rsp-8+arg_10], rbx
0x1800293cd  push    rbp
0x1800293ce  push    rsi
0x1800293cf  push    rdi
0x1800293d0  push    r12
0x1800293d2  push    r13
0x1800293d4  push    r14
0x1800293d6  push    r15
0x1800293d8  lea     rbp, [rsp-30h]
0x1800293dd  sub     rsp, 130h
0x1800293e4  mov     rax, cs:__security_cookie
0x1800293eb  xor     rax, rsp
0x1800293ee  mov     [rbp+60h+var_38], rax
0x1800293f2  mov     [rbp+60h+var_B0], rdx
0x1800293f6  xor     r15d, r15d
0x1800293f9  mov     [rbp+60h+var_A8], r15
0x1800293fd  lea     r8d, [r15+48h]; struct _GUID *
0x180029401  mov     [rbp+60h+var_A0], r8d
0x180029405  lea     eax, [r15+10h]
0x180029409  mov     [rbp+60h+var_9C], eax
0x18002940c  mov     [rbp+60h+var_98], rdx
0x180029410  mov     [rbp+60h+var_90], r15
0x180029414  mov     [rbp+60h+var_88], r8d
0x180029418  mov     [rbp+60h+var_84], eax
0x18002941b  mov     [rbp+60h+var_D0], r15
0x18002941f  mov     [rbp+60h+var_E0], r15
0x180029423  mov     [rsp+160h+var_F8], r15
0x180029428  mov     edi, r15d
0x18002942b  mov     [rbp+60h+pDacl], r15
0x18002942f  mov     [rsp+160h+pSizeNewSD], r15d
0x180029434  mov     [rbp+60h+pSecurityDescriptor], r15
0x180029438  mov     [rsp+160h+pNewSD], r15
0x18002943d  mov     [rbp+60h+bDaclPresent], r15d
0x180029441  mov     [rbp+60h+bDaclDefaulted], r15d
0x180029445  xorps   xmm0, xmm0
0x180029448  movups  xmmword ptr [rbp+60h+pTrustee.pMultipleTrustee], xmm0
0x18002944c  movups  xmmword ptr [rbp+60h+pTrustee.TrusteeType], xmm0
0x180029450  xorps   xmm1, xmm1
0x180029453  movups  xmmword ptr [rbp+60h+pGroup.pMultipleTrustee], xmm1
0x180029457  movups  xmmword ptr [rbp+60h+pGroup.TrusteeType], xmm1
0x18002945b  lea     rax, [rbp+60h+var_E0]
0x18002945f  mov     qword ptr [rsp+160h+nSubAuthority6], rax; void **
0x180029464  mov     [rsp+160h+nSubAuthority5], 20001h; unsigned int
0x18002946c  lea     r12d, [r15+1]
0x180029470  mov     qword ptr [rsp+160h+nSubAuthority3], r12; void *
0x180029475  lea     rax, [rbp+60h+var_B0]
0x180029479  mov     [rsp+160h+ppv], rax; void *
0x18002947e  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180029485  mov     rdx, [rcx+10h]; struct ISimpleTableDispenser *
0x180029489  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x18002948e  mov     ebx, eax
0x180029490  test    eax, eax
0x180029492  js      loc_1800298CB
0x180029498  mov     rcx, [rbp+60h+var_E0]
0x18002949c  mov     rax, [rcx]
0x18002949f  mov     rax, [rax+18h]
0x1800294a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294a8  mov     ebx, eax
0x1800294aa  test    eax, eax
0x1800294ac  js      loc_1800298CB
0x1800294b2  lea     rax, [rbp+60h+var_D0]
0x1800294b6  mov     [rsp+160h+ppv], rax; ppv
0x1800294bb  lea     r9, IID_ISimpleTableDispenser; riid
0x1800294c2  mov     r8d, r12d; dwClsContext
0x1800294c5  xor     edx, edx; pUnkOuter
0x1800294c7  lea     rcx, CLSID_STDispenser; rclsid
0x1800294ce  call    cs:__imp_CoCreateInstance
0x1800294d4  mov     ebx, eax
0x1800294d6  test    eax, eax
0x1800294d8  js      loc_1800298CB
0x1800294de  lea     rax, [rsp+160h+var_F8]
0x1800294e3  mov     qword ptr [rsp+160h+nSubAuthority6], rax; void **
0x1800294e8  mov     [rsp+160h+nSubAuthority5], 20000h; unsigned int
0x1800294f0  mov     qword ptr [rsp+160h+nSubAuthority3], r12; void *
0x1800294f5  lea     rax, [rbp+60h+var_98]
0x1800294f9  mov     [rsp+160h+ppv], rax; void *
0x1800294fe  lea     r9, TID_APPLICATION; struct _GUID *
0x180029505  mov     rdx, [rbp+60h+var_D0]; struct ISimpleTableDispenser *
0x180029509  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x18002950e  mov     ebx, eax
0x180029510  mov     rcx, [rbp+60h+var_D0]
0x180029514  mov     rax, [rcx]
0x180029517  mov     rax, [rax+10h]
0x18002951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029520  test    ebx, ebx
0x180029522  js      loc_1800298CB
0x180029528  mov     rcx, [rsp+160h+var_F8]
0x18002952d  mov     rax, [rcx]
0x180029530  mov     rax, [rax+18h]
0x180029534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029539  mov     ebx, eax
0x18002953b  test    eax, eax
0x18002953d  js      loc_1800298CB
0x180029543  lea     esi, [r15+8]
0x180029547  mov     rcx, [rsp+160h+var_F8]
0x18002954c  mov     rax, [rcx]
0x18002954f  xor     edx, edx
0x180029551  mov     rax, [rax+30h]
0x180029555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002955a  mov     ebx, eax
0x18002955c  test    eax, eax
0x18002955e  js      loc_1800298CB
0x180029564  lea     r13d, [r15+2]
0x180029568  mov     rcx, [rbp+60h+var_E0]
0x18002956c  mov     rax, [rcx]
0x18002956f  mov     rax, [rax+20h]
0x180029573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029578  mov     ebx, eax
0x18002957a  test    eax, eax
0x18002957c  js      loc_1800298CB
0x180029582  mov     r14d, r15d
0x180029585  mov     rcx, [rbp+60h+var_E0]
0x180029589  mov     rax, [rcx]
0x18002958c  mov     rax, [rax+28h]
0x180029590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029595  test    eax, eax
0x180029597  js      loc_18002963B
0x18002959d  mov     rcx, [rbp+60h+var_E0]
0x1800295a1  mov     rax, [rcx]
0x1800295a4  lea     rdx, [rbp+60h+pSecurityDescriptor]
0x1800295a8  mov     [rsp+160h+ppv], rdx
0x1800295ad  xor     r9d, r9d
0x1800295b0  xor     r8d, r8d
0x1800295b3  mov     edx, r13d
0x1800295b6  mov     rax, [rax+40h]
0x1800295ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295bf  mov     ebx, eax
0x1800295c1  test    eax, eax
0x1800295c3  js      loc_1800298CB
0x1800295c9  mov     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x1800295cd  test    rcx, rcx
0x1800295d0  jz      loc_1800297E9
0x1800295d6  lea     r9, [rbp+60h+bDaclDefaulted]; lpbDaclDefaulted
0x1800295da  lea     r8, [rbp+60h+pDacl]; pDacl
0x1800295de  lea     rdx, [rbp+60h+bDaclPresent]; lpbDaclPresent
0x1800295e2  call    cs:__imp_GetSecurityDescriptorDacl
0x1800295e8  test    eax, eax
0x1800295ea  jz      loc_1800297CB
0x1800295f0  cmp     [rbp+60h+bDaclPresent], r15d
0x1800295f4  jz      short loc_180029633
0x1800295f6  mov     r9, [rbp+60h+pDacl]
0x1800295fa  test    r9, r9
0x1800295fd  jz      short loc_180029633
0x1800295ff  movzx   eax, word ptr [r9+2]
0x180029604  test    rdi, rdi
0x180029607  jnz     short loc_180029610
0x180029609  add     eax, 0FFFFFFF8h
0x18002960c  add     esi, eax
0x18002960e  jmp     short loc_180029633
0x180029610  sub     eax, 8
0x180029613  add     r9, 8; pAceList
0x180029617  mov     dword ptr [rsp+160h+ppv], eax; nAceListLength
0x18002961b  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18002961f  mov     edx, r13d; dwAceRevision
0x180029622  mov     rcx, rdi; pAcl
0x180029625  call    cs:__imp_AddAce
0x18002962b  test    eax, eax
0x18002962d  jz      loc_1800297CB
0x180029633  add     r14d, r12d
0x180029636  jmp     loc_180029585
0x18002963b  test    rdi, rdi
0x18002963e  jnz     loc_18002970A
0x180029644  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], r15d
0x180029648  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 500h
0x18002964e  mov     [rsp+160h+var_F0], r15
0x180029653  lea     rax, [rsp+160h+var_F0]
0x180029658  mov     [rsp+160h+pSid], rax; pSid
0x18002965d  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x180029662  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x180029667  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x18002966c  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x180029671  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x180029676  mov     dword ptr [rsp+160h+ppv], r15d; nSubAuthority2
0x18002967b  xor     r9d, r9d; nSubAuthority1
0x18002967e  lea     r8d, [rdi+12h]; nSubAuthority0
0x180029682  mov     dl, r12b; nSubAuthorityCount
0x180029685  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x180029689  call    cs:__imp_AllocateAndInitializeSid
0x18002968f  test    eax, eax
0x180029691  jz      loc_1800297CB
0x180029697  mov     rcx, [rsp+160h+var_F0]; pSid
0x18002969c  test    rcx, rcx
0x18002969f  jz      loc_1800297E9
0x1800296a5  call    cs:__imp_GetLengthSid
0x1800296ab  add     eax, 8
0x1800296ae  add     esi, eax
0x1800296b0  mov     ecx, esi; cb
0x1800296b2  call    cs:__imp_CoTaskMemAlloc
0x1800296b8  mov     rdi, rax
0x1800296bb  test    rax, rax
0x1800296be  jz      loc_18002980A
0x1800296c4  mov     r8d, r13d; dwAclRevision
0x1800296c7  mov     edx, esi; nAclLength
0x1800296c9  mov     rcx, rax; pAcl
0x1800296cc  call    cs:__imp_InitializeAcl
0x1800296d2  test    eax, eax
0x1800296d4  jz      loc_1800297F3
0x1800296da  mov     r9, [rsp+160h+var_F0]; pSid
0x1800296df  mov     r8d, r12d; AccessMask
0x1800296e2  mov     edx, r13d; dwAceRevision
0x1800296e5  mov     rcx, rdi; pAcl
0x1800296e8  call    cs:__imp_AddAccessAllowedAce
0x1800296ee  test    eax, eax
0x1800296f0  jz      loc_1800297F3
0x1800296f6  mov     rcx, [rsp+160h+var_F0]; pSid
0x1800296fb  call    cs:__imp_FreeSid
0x180029701  test    r14d, r14d
0x180029704  jnz     loc_180029568
0x18002970a  lea     rdx, pName; "CURRENT_USER"
0x180029711  lea     rcx, [rbp+60h+pTrustee]; pTrustee
0x180029715  call    cs:__imp_BuildTrusteeWithNameW
0x18002971b  lea     rdx, pName; "CURRENT_USER"
0x180029722  lea     rcx, [rbp+60h+pGroup]; pTrustee
0x180029726  call    cs:__imp_BuildTrusteeWithNameW
0x18002972c  mov     [rbp+60h+pGroup.TrusteeType], r13d
0x180029730  lea     rax, [rsp+160h+pNewSD]
0x180029735  mov     qword ptr [rsp+160h+nSubAuthority6], rax; pNewSD
0x18002973a  lea     rax, [rsp+160h+pSizeNewSD]
0x18002973f  mov     qword ptr [rsp+160h+nSubAuthority5], rax; pSizeNewSD
0x180029744  mov     qword ptr [rsp+160h+nSubAuthority4], r15; pOldSD
0x180029749  mov     qword ptr [rsp+160h+nSubAuthority3], r15; pListOfAuditEntries
0x18002974e  mov     dword ptr [rsp+160h+ppv], r15d; cCountOfAuditEntries
0x180029753  xor     r9d, r9d; pListOfAccessEntries
0x180029756  xor     r8d, r8d; cCountOfAccessEntries
0x180029759  lea     rdx, [rbp+60h+pGroup]; pGroup
0x18002975d  lea     rcx, [rbp+60h+pTrustee]; pOwner
0x180029761  call    cs:__imp_BuildSecurityDescriptorW
0x180029767  test    eax, eax
0x180029769  jnz     short loc_1800297CB
0x18002976b  mov     [rbp+60h+Src], r15
0x18002976f  lea     r8, [rbp+60h+Src]; struct _ACL **
0x180029773  mov     rdx, rdi; struct _ACL *
0x180029776  call    ?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z; CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)
0x18002977b  mov     ebx, eax
0x18002977d  test    eax, eax
0x18002977f  js      loc_1800298CB
0x180029785  mov     rsi, [rbp+60h+Src]
0x180029789  test    rsi, rsi
0x18002978c  jz      loc_1800298CB
0x180029792  mov     rcx, rdi; pv
0x180029795  call    cs:__imp_CoTaskMemFree
0x18002979b  nop
0x18002979c  mov     rdi, rsi
0x18002979f  movzx   ebx, word ptr [rsi+2]
0x1800297a3  mov     eax, [rsp+160h+pSizeNewSD]
0x1800297a7  lea     edx, [rbx+rax]; uBytes
0x1800297aa  cmp     edx, eax
0x1800297ac  jb      loc_1800298C6
0x1800297b2  mov     rcx, [rsp+160h+pNewSD]; Src
0x1800297b7  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x1800297bc  test    rax, rax
0x1800297bf  jnz     short loc_18002981F
0x1800297c1  mov     ebx, 8007000Eh
0x1800297c6  jmp     loc_1800298CB
0x1800297cb  call    cs:__imp_GetLastError
0x1800297d1  mov     ebx, eax
0x1800297d3  test    eax, eax
0x1800297d5  jle     loc_1800298CB
0x1800297db  movzx   ebx, ax
0x1800297de  or      ebx, 80070000h
0x1800297e4  jmp     loc_1800298CB
0x1800297e9  mov     ebx, 8000FFFFh
0x1800297ee  jmp     loc_1800298CB
0x1800297f3  call    cs:__imp_GetLastError
0x1800297f9  mov     ebx, eax
0x1800297fb  test    eax, eax
0x1800297fd  jle     short loc_18002980F
0x1800297ff  movzx   ebx, ax
0x180029802  or      ebx, 80070000h
0x180029808  jmp     short loc_18002980F
0x18002980a  mov     ebx, 8007000Eh
0x18002980f  mov     rcx, [rsp+160h+var_F0]; pSid
0x180029814  call    cs:__imp_FreeSid
0x18002981a  jmp     loc_1800298CB
0x18002981f  mov     [rsp+160h+pNewSD], rax
0x180029824  mov     r8, rbx; Size
0x180029827  mov     ecx, [rsp+160h+pSizeNewSD]
0x18002982b  add     rcx, rax; void *
0x18002982e  mov     rdx, rsi; Src
0x180029831  call    memcpy_0
0x180029836  mov     ecx, [rsp+160h+pSizeNewSD]
0x18002983a  mov     rax, [rsp+160h+pNewSD]
0x18002983f  mov     [rax+10h], ecx
0x180029842  mov     rax, [rsp+160h+pNewSD]
0x180029847  mov     ecx, 0FFEFh
0x18002984c  and     [rax+2], cx
0x180029850  add     [rsp+160h+pSizeNewSD], ebx
0x180029854  mov     rcx, [rsp+160h+var_F8]
0x180029859  mov     rax, [rcx]
0x18002985c  mov     rax, [rax+80h]
0x180029863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029868  mov     ebx, eax
0x18002986a  test    eax, eax
0x18002986c  js      short loc_1800298CB
0x18002986e  mov     rcx, [rsp+160h+var_F8]
0x180029873  mov     rax, [rcx]
0x180029876  mov     r9, [rsp+160h+pNewSD]
0x18002987b  mov     r8d, [rsp+160h+pSizeNewSD]
0x180029880  mov     edx, 17h
0x180029885  mov     rax, [rax+0A0h]
  ... truncated ...
```
