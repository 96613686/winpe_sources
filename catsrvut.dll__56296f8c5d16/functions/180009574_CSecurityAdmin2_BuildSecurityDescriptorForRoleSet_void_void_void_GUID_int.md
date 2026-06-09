# CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(void *,void *,void * *,_GUID *,int)

- ea: `0x180009574`
- end: `0x180009c64`
- name: `?BuildSecurityDescriptorForRoleSet@CSecurityAdmin2@@QEAAJPEAX0PEAPEAXPEAU_GUID@@H@Z`
- size: `1776`
- prototype: `__int64 __fastcall(struct ISimpleTableDispenser **this, void *, struct _GUID *, void **, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027a1c`

## callees

- `0x1800074d8`
- `0x180007a4c`
- `0x180009574`
- `0x180009c6c`
- `0x1800269a8`
- `0x180026af4`
- `0x18002ae90`
- `0x18005582e`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009954`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800098e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800098e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009933`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009b5e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009b70`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180009b70`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800098ae`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1800098ae`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180009c25`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180009c25`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180009bd7`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180009bd7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000986b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009c03`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000986b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180009c03`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800098fa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180009a4f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800098fa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180009a4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009943`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x180009ab7`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x180009ab7`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180009a68`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180009a79`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180009a68`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180009a79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(
        struct ISimpleTableDispenser **this,
        void *a2,
        struct _GUID *a3,
        void **a4,
        struct _GUID *a5,
        int a6)
{
  struct _ACL *v9; // rdi
  DWORD v10; // esi
  signed int Table; // ebx
  const struct _GUID *v12; // r8
  __int64 v13; // rax
  CSecurityAdmin2 *v14; // rcx
  int AclSize; // eax
  CSecurityAdmin2 *v16; // rcx
  struct _ACL *v17; // rax
  int v18; // r14d
  signed int LastError; // eax
  struct _ACL *v21; // rbx
  struct _ACL *v22; // rax
  signed int v23; // eax
  unsigned int v24; // r8d
  bool v25; // cc
  SIZE_T v26; // rdx
  char *v27; // rax
  HANDLE CurrentProcess; // rax
  BOOL v29; // esi
  signed int v30; // eax
  int v31; // ecx
  PACL v32; // rdx
  __int64 v33; // rax
  unsigned int pOldSD; // [rsp+30h] [rbp-D0h]
  unsigned int pOldSDa; // [rsp+30h] [rbp-D0h]
  ULONG pSizeNewSD; // [rsp+54h] [rbp-ACh] BYREF
  void *v37; // [rsp+58h] [rbp-A8h] BYREF
  void *v38; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  WINBOOL bDaclPresent; // [rsp+74h] [rbp-8Ch] BYREF
  WINBOOL v42; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  PACL pDacl; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  PACL v48; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v49[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h]
  int v51; // [rsp+C8h] [rbp-38h]
  int v52; // [rsp+CCh] [rbp-34h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+D8h] [rbp-28h] BYREF
  int v55; // [rsp+E0h] [rbp-20h]
  __int64 v56; // [rsp+E8h] [rbp-18h]
  _QWORD v57[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v58; // [rsp+100h] [rbp+0h]
  int v59; // [rsp+104h] [rbp+4h]
  struct _TRUSTEE_W pGroup; // [rsp+108h] [rbp+8h] BYREF
  _TRUSTEE_W pTrustee; // [rsp+128h] [rbp+28h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+148h] [rbp+48h] BYREF

  hMem = a3;
  v9 = 0;
  pDacl = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  memset(&pGroup, 0, sizeof(pGroup));
  pSizeNewSD = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  GenericMapping = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  hObject = 0;
  if ( !a6 && a3 )
  {
    v18 = 0;
    goto LABEL_62;
  }
  v10 = 8;
  if ( a5 )
  {
    v57[0] = a5;
    v57[1] = 0;
    v58 = 72;
    v59 = 16;
    v49[0] = 0;
    v49[1] = 0;
    v49[2] = 0x1000000048LL;
    v50 = 0;
    v51 = 0;
    v52 = 1;
    v53 = 130;
    pSecurityDescriptor = 0;
    Table = CSecurityAdmin2::GetTable(
              (CSecurityAdmin2 *)0x48,
              this[4],
              a3,
              &tidCOMSERVICES_ROLESET,
              v57,
              (void *)1,
              pOldSD,
              0x20000u,
              &v37);
    if ( Table < 0 )
      goto LABEL_30;
    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v37 + 24LL))(v37);
    if ( Table < 0 )
      goto LABEL_30;
    (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v37 + 48LL))(v37, 0);
    pOldSDa = 0;
    Table = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v37 + 72LL))(
              v37,
              0,
              0,
              0,
              0,
              0);
    if ( Table < 0 )
      goto LABEL_30;
    if ( v40 )
    {
      while ( 1 )
      {
        do
        {
          Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)v37 + 64LL))(v37, 1, 0);
          if ( Table < 0 )
            goto LABEL_30;
          Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v37 + 64LL))(
                    v37,
                    2,
                    0,
                    0,
                    v49);
          if ( Table < 0 )
            goto LABEL_30;
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(v50 + 2 * v13) );
          HIDWORD(v53) = 2 * v13 + 2;
          v14 = (CSecurityAdmin2 *)v38;
          if ( v38 )
          {
            (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
            v38 = 0;
          }
          Table = CSecurityAdmin2::GetTable(
                    v14,
                    this[3],
                    v12,
                    &tidCOMSERVICES_ROLESDCACHE,
                    v49,
                    (void *)2,
                    pOldSDa,
                    0x20000u,
                    &v38);
          if ( Table < 0 )
            goto LABEL_30;
          Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v38 + 24LL))(v38);
          if ( Table < 0 )
            goto LABEL_30;
          Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v38 + 48LL))(v38, 0);
          if ( Table < 0 )
            goto LABEL_30;
          Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v38 + 64LL))(
                    v38,
                    2,
                    0,
                    0,
                    &pSecurityDescriptor);
          if ( Table < 0 )
            goto LABEL_30;
          if ( !pSecurityDescriptor )
          {
            Table = -2147418113;
            goto LABEL_30;
          }
          if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
            goto LABEL_42;
          if ( bDaclPresent && pDacl )
          {
            AclSize = pDacl->AclSize;
            if ( v9 )
            {
              if ( !AddAce(v9, 2u, 0xFFFFFFFF, &pDacl[1], AclSize - 8) )
                goto LABEL_42;
            }
            else
            {
              v10 += AclSize - 8;
            }
          }
        }
        while ( (*(int (__fastcall **)(void *))(*(_QWORD *)v37 + 40LL))(v37) >= 0 );
        if ( v9 )
          break;
        v17 = (struct _ACL *)CoTaskMemAlloc(v10);
        v9 = v17;
        if ( !v17 )
          goto LABEL_44;
        if ( !InitializeAcl(v17, v10, 2u) )
          goto LABEL_42;
        Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v37 + 48LL))(v37, 0);
        if ( Table < 0 )
          goto LABEL_30;
      }
      Src = 0;
      Table = CSecurityAdmin2::OptimizeAcl(v16, v9, (struct _ACL **)&Src);
      if ( Table < 0 )
      {
LABEL_48:
        v18 = 0;
        goto LABEL_31;
      }
      v21 = (struct _ACL *)Src;
      if ( !Src )
      {
        Table = -2147418113;
        goto LABEL_48;
      }
      CoTaskMemFree(v9);
      v9 = v21;
      v10 = v21->AclSize;
      goto LABEL_53;
    }
  }
  v22 = (struct _ACL *)CoTaskMemAlloc(8u);
  v9 = v22;
  if ( !v22 )
  {
LABEL_44:
    Table = -2147024882;
LABEL_30:
    v18 = 0;
    goto LABEL_31;
  }
  if ( !InitializeAcl(v22, 8u, 2u) )
  {
LABEL_42:
    LastError = GetLastError();
    Table = LastError;
    if ( LastError > 0 )
      Table = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_30;
  }
LABEL_53:
  BuildTrusteeWithNameW(&pTrustee, (LPWSTR)L"CURRENT_USER");
  BuildTrusteeWithNameW(&pGroup, (LPWSTR)L"CURRENT_USER");
  pGroup.TrusteeType = TRUSTEE_IS_GROUP;
  v18 = 0;
  v23 = BuildSecurityDescriptorW(&pTrustee, &pGroup, 0, 0, 0, 0, 0, &pSizeNewSD, &hMem);
  Table = v23;
  v25 = v23 <= 0;
  if ( v23 )
  {
LABEL_54:
    if ( v25 )
      goto LABEL_31;
    Table = (unsigned __int16)v23;
    goto LABEL_56;
  }
  v18 = 1;
  v26 = pSizeNewSD + v10;
  if ( (unsigned int)v26 < pSizeNewSD )
  {
    Table = -2147024362;
    goto LABEL_31;
  }
  v27 = (char *)SmartLocalReAlloc(hMem, v26, v24);
  if ( !v27 )
  {
    Table = -2147024882;
    goto LABEL_31;
  }
  hMem = v27;
  memcpy_0(&v27[pSizeNewSD], v9, v10);
  *((_DWORD *)hMem + 4) = pSizeNewSD;
  *((_WORD *)hMem + 1) &= ~0x10u;
  pSizeNewSD += v10;
LABEL_62:
  v42 = 0;
  v48 = 0;
  Table = 0;
  if ( (int)CImpersonate::SuspendImpersonation((CImpersonate *)&v54) >= 0 )
  {
    CurrentProcess = GetCurrentProcess();
    v29 = OpenProcessToken(CurrentProcess, 8u, &hObject);
    if ( !v29 )
      Table = GetLastError();
    if ( (v55 & 1) != 0 )
      CImpersonate::ResumeImpersonation((CImpersonate *)&v54);
    if ( v29 )
    {
      Table = 0;
      if ( !CreatePrivateObjectSecurityEx(a2, hMem, a4, 0, 1, 0x11u, hObject, &GenericMapping) )
      {
        v23 = GetLastError();
        Table = v23;
        v25 = v23 <= 0;
        goto LABEL_54;
      }
      if ( GetSecurityDescriptorDacl(*a4, &v42, &v48, &v42) )
      {
        v31 = v48->AclSize - 8;
        v32 = v48 + 1;
        if ( v48->AclSize != 8 )
        {
          do
          {
            v32->Sbz1 &= ~8u;
            v33 = v32->AclSize;
            v32 = (PACL)((char *)v32 + v33);
            v31 -= v33;
          }
          while ( v31 );
        }
      }
      else
      {
        v30 = GetLastError();
        Table = v30;
        if ( v30 > 0 )
          Table = (unsigned __int16)v30 | 0x80070000;
        DestroyPrivateObjectSecurity(a4);
      }
    }
    else if ( Table > 0 )
    {
      Table = (unsigned __int16)Table;
LABEL_56:
      Table |= 0x80070000;
    }
  }
LABEL_31:
  if ( hObject )
    CloseHandle(hObject);
  if ( v18 )
    LocalFree(hMem);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( v37 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  CImpersonate::~CImpersonate((CImpersonate *)&v54);
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x180009574  push    rbp
0x180009576  push    rbx
0x180009577  push    rsi
0x180009578  push    rdi
0x180009579  push    r12
0x18000957b  push    r13
0x18000957d  push    r14
0x18000957f  push    r15
0x180009581  lea     rbp, [rsp-68h]
0x180009586  sub     rsp, 168h
0x18000958d  mov     rax, cs:__security_cookie
0x180009594  xor     rax, rsp
0x180009597  mov     [rbp+0A0h+var_48], rax
0x18000959b  mov     r15, r9
0x18000959e  mov     r12, rdx
0x1800095a1  mov     r13, rcx
0x1800095a4  mov     [rsp+1A0h+hMem], r8
0x1800095a9  mov     rax, [rbp+0A0h+arg_20]
0x1800095b0  xor     r14d, r14d
0x1800095b3  mov     edi, r14d
0x1800095b6  mov     [rbp+0A0h+pDacl], r14
0x1800095ba  mov     [rsp+1A0h+var_130], r14d
0x1800095bf  mov     [rsp+1A0h+var_148], r14
0x1800095c4  mov     [rsp+1A0h+var_140], r14
0x1800095c9  xorps   xmm0, xmm0
0x1800095cc  movups  xmmword ptr [rbp+0A0h+pTrustee.pMultipleTrustee], xmm0
0x1800095d0  movups  xmmword ptr [rbp+0A0h+pTrustee.TrusteeType], xmm0
0x1800095d4  xorps   xmm1, xmm1
0x1800095d7  movups  xmmword ptr [rbp+0A0h+pGroup.pMultipleTrustee], xmm1
0x1800095db  movups  xmmword ptr [rbp+0A0h+pGroup.TrusteeType], xmm1
0x1800095df  mov     [rsp+1A0h+var_14C], r14d
0x1800095e4  mov     [rsp+1A0h+bDaclPresent], r14d
0x1800095e9  mov     [rsp+1A0h+bDaclDefaulted], r14d
0x1800095ee  movups  xmmword ptr [rbp+0A0h+GenericMapping.GenericRead], xmm0
0x1800095f2  mov     [rsp+1A0h+var_150], r14d
0x1800095f7  mov     [rbp+0A0h+var_C8], r14
0x1800095fb  mov     [rbp+0A0h+var_C0], r14d
0x1800095ff  mov     [rbp+0A0h+var_B8], r14
0x180009603  mov     [rbp+0A0h+hObject], r14
0x180009607  lea     edx, [r14+1]
0x18000960b  cmp     [rbp+0A0h+arg_28], r14d
0x180009612  jnz     short loc_18000961D
0x180009614  test    r8, r8
0x180009617  jnz     loc_180009B3C
0x18000961d  mov     esi, 8
0x180009622  test    rax, rax
0x180009625  jz      loc_180009A30
0x18000962b  mov     [rbp+0A0h+var_B0], rax
0x18000962f  mov     [rbp+0A0h+var_A8], r14
0x180009633  lea     ecx, [rsi+40h]; this
0x180009636  mov     [rbp+0A0h+var_A0], ecx
0x180009639  lea     eax, [rsi+8]
0x18000963c  mov     [rbp+0A0h+var_9C], eax
0x18000963f  mov     [rbp+0A0h+var_F8], r14
0x180009643  mov     [rbp+0A0h+var_F0], r14
0x180009647  mov     dword ptr [rbp+0A0h+var_E8], ecx
0x18000964a  mov     dword ptr [rbp+0A0h+var_E8+4], eax
0x18000964d  mov     [rbp+0A0h+var_E0], r14
0x180009651  mov     [rbp+0A0h+var_D8], r14d
0x180009655  mov     [rbp+0A0h+var_D4], edx
0x180009658  mov     [rbp+0A0h+var_D0], 82h
0x180009660  mov     [rbp+0A0h+pSecurityDescriptor], r14
0x180009664  lea     rax, [rsp+1A0h+var_148]
0x180009669  mov     [rsp+1A0h+pNewSD], rax; void **
0x18000966e  mov     dword ptr [rsp+1A0h+pSizeNewSD], 20000h; unsigned int
0x180009676  mov     [rsp+1A0h+pListOfAuditEntries], rdx; void *
0x18000967b  lea     rax, [rbp+0A0h+var_B0]
0x18000967f  mov     qword ptr [rsp+1A0h+nAceListLength], rax; void *
0x180009684  lea     r9, tidCOMSERVICES_ROLESET; struct _GUID *
0x18000968b  mov     rdx, [r13+20h]; struct ISimpleTableDispenser *
0x18000968f  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180009694  mov     ebx, eax
0x180009696  test    eax, eax
0x180009698  js      loc_180009925
0x18000969e  mov     rcx, [rsp+1A0h+var_148]
0x1800096a3  mov     rax, [rcx]
0x1800096a6  mov     rax, [rax+18h]
0x1800096aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096af  mov     ebx, eax
0x1800096b1  test    eax, eax
0x1800096b3  js      loc_180009925
0x1800096b9  mov     rcx, [rsp+1A0h+var_148]
0x1800096be  mov     rax, [rcx]
0x1800096c1  xor     edx, edx
0x1800096c3  mov     rax, [rax+30h]
0x1800096c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096cc  mov     rcx, [rsp+1A0h+var_148]
0x1800096d1  mov     rax, [rcx]
0x1800096d4  mov     [rsp+1A0h+pNewSD], r14
0x1800096d9  lea     rdx, [rsp+1A0h+var_130]
0x1800096de  mov     [rsp+1A0h+pSizeNewSD], rdx
0x1800096e3  mov     [rsp+1A0h+pOldSD], r14; unsigned int
0x1800096e8  mov     [rsp+1A0h+pListOfAuditEntries], r14
0x1800096ed  mov     qword ptr [rsp+1A0h+nAceListLength], r14
0x1800096f2  xor     r9d, r9d
0x1800096f5  xor     r8d, r8d
0x1800096f8  xor     edx, edx
0x1800096fa  mov     rax, [rax+48h]
0x1800096fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009703  mov     ebx, eax
0x180009705  test    eax, eax
0x180009707  js      loc_180009925
0x18000970d  cmp     [rsp+1A0h+var_130], r14d
0x180009712  jz      loc_180009A30
0x180009718  lea     r14d, [rsi-6]
0x18000971c  mov     rcx, [rsp+1A0h+var_148]
0x180009721  mov     rax, [rcx]
0x180009724  lea     rdx, [rbp+0A0h+var_E0]
0x180009728  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x18000972d  xor     r9d, r9d
0x180009730  xor     r8d, r8d
0x180009733  lea     edx, [r9+1]
0x180009737  mov     rax, [rax+40h]
0x18000973b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009740  mov     ebx, eax
0x180009742  test    eax, eax
0x180009744  js      loc_180009925
0x18000974a  mov     rcx, [rsp+1A0h+var_148]
0x18000974f  mov     rax, [rcx]
0x180009752  lea     rdx, [rbp+0A0h+var_F8]
0x180009756  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x18000975b  xor     r9d, r9d
0x18000975e  xor     r8d, r8d
0x180009761  mov     edx, r14d
0x180009764  mov     rax, [rax+40h]
0x180009768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000976d  mov     ebx, eax
0x18000976f  test    eax, eax
0x180009771  js      loc_180009925
0x180009777  mov     rcx, [rbp+0A0h+var_E0]
0x18000977b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000977f  xor     ebx, ebx
0x180009781  inc     rax
0x180009784  cmp     [rcx+rax*2], bx
0x180009788  jnz     short loc_180009781
0x18000978a  lea     eax, ds:2[rax*2]
0x180009791  mov     dword ptr [rbp+0A0h+var_D0+4], eax
0x180009794  mov     rcx, [rsp+1A0h+var_140]
0x180009799  test    rcx, rcx
0x18000979c  jz      short loc_1800097AF
0x18000979e  mov     rax, [rcx]
0x1800097a1  mov     rax, [rax+10h]
0x1800097a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097aa  mov     [rsp+1A0h+var_140], rbx
0x1800097af  lea     rax, [rsp+1A0h+var_140]
0x1800097b4  mov     [rsp+1A0h+pNewSD], rax; void **
0x1800097b9  mov     dword ptr [rsp+1A0h+pSizeNewSD], 20000h; unsigned int
0x1800097c1  mov     [rsp+1A0h+pListOfAuditEntries], r14; void *
0x1800097c6  lea     rax, [rbp+0A0h+var_F8]
0x1800097ca  mov     qword ptr [rsp+1A0h+nAceListLength], rax; void *
0x1800097cf  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x1800097d6  mov     rdx, [r13+18h]; struct ISimpleTableDispenser *
0x1800097da  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x1800097df  mov     ebx, eax
0x1800097e1  test    eax, eax
0x1800097e3  js      loc_180009925
0x1800097e9  mov     rcx, [rsp+1A0h+var_140]
0x1800097ee  mov     rax, [rcx]
0x1800097f1  mov     rax, [rax+18h]
0x1800097f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fa  mov     ebx, eax
0x1800097fc  test    eax, eax
0x1800097fe  js      loc_180009925
0x180009804  mov     rcx, [rsp+1A0h+var_140]
0x180009809  mov     rax, [rcx]
0x18000980c  xor     edx, edx
0x18000980e  mov     rax, [rax+30h]
0x180009812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009817  mov     ebx, eax
0x180009819  test    eax, eax
0x18000981b  js      loc_180009925
0x180009821  mov     rcx, [rsp+1A0h+var_140]
0x180009826  mov     rax, [rcx]
0x180009829  lea     rdx, [rbp+0A0h+pSecurityDescriptor]
0x18000982d  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x180009832  xor     r9d, r9d
0x180009835  xor     r8d, r8d
0x180009838  mov     edx, r14d
0x18000983b  mov     rax, [rax+40h]
0x18000983f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009844  mov     ebx, eax
0x180009846  test    eax, eax
0x180009848  js      loc_180009925
0x18000984e  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180009852  xor     ebx, ebx
0x180009854  test    rcx, rcx
0x180009857  jz      loc_180009A26
0x18000985d  lea     r9, [rsp+1A0h+bDaclDefaulted]; lpbDaclDefaulted
0x180009862  lea     r8, [rbp+0A0h+pDacl]; pDacl
0x180009866  lea     rdx, [rsp+1A0h+bDaclPresent]; lpbDaclPresent
0x18000986b  call    cs:__imp_GetSecurityDescriptorDacl
0x180009871  test    eax, eax
0x180009873  jz      loc_1800099BC
0x180009879  cmp     [rsp+1A0h+bDaclPresent], ebx
0x18000987d  jz      short loc_1800098BC
0x18000987f  mov     r9, [rbp+0A0h+pDacl]
0x180009883  test    r9, r9
0x180009886  jz      short loc_1800098BC
0x180009888  movzx   eax, word ptr [r9+2]
0x18000988d  test    rdi, rdi
0x180009890  jnz     short loc_180009899
0x180009892  add     eax, 0FFFFFFF8h
0x180009895  add     esi, eax
0x180009897  jmp     short loc_1800098BC
0x180009899  sub     eax, 8
0x18000989c  add     r9, 8; pAceList
0x1800098a0  mov     [rsp+1A0h+nAceListLength], eax; nAceListLength
0x1800098a4  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1800098a8  mov     edx, r14d; dwAceRevision
0x1800098ab  mov     rcx, rdi; pAcl
0x1800098ae  call    cs:__imp_AddAce
0x1800098b4  test    eax, eax
0x1800098b6  jz      loc_1800099BC
0x1800098bc  mov     rcx, [rsp+1A0h+var_148]
0x1800098c1  mov     rax, [rcx]
0x1800098c4  mov     rax, [rax+28h]
0x1800098c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cd  test    eax, eax
0x1800098cf  jns     loc_18000971C
0x1800098d5  test    rdi, rdi
0x1800098d8  jnz     loc_1800099E5
0x1800098de  mov     ecx, esi; cb
0x1800098e0  call    cs:__imp_CoTaskMemAlloc
0x1800098e6  mov     rdi, rax
0x1800098e9  test    rax, rax
0x1800098ec  jz      loc_1800099DB
0x1800098f2  mov     r8d, r14d; dwAclRevision
0x1800098f5  mov     edx, esi; nAclLength
0x1800098f7  mov     rcx, rax; pAcl
0x1800098fa  call    cs:__imp_InitializeAcl
0x180009900  test    eax, eax
0x180009902  jz      loc_1800099BC
0x180009908  mov     rcx, [rsp+1A0h+var_148]
0x18000990d  mov     rdx, [rcx]
0x180009910  mov     rax, [rdx+30h]
0x180009914  xor     edx, edx
0x180009916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000991b  mov     ebx, eax
0x18000991d  test    eax, eax
0x18000991f  jns     loc_18000971C
0x180009925  mov     r14d, [rsp+1A0h+var_150]
0x18000992a  mov     rcx, [rbp+0A0h+hObject]; hObject
0x18000992e  test    rcx, rcx
0x180009931  jz      short loc_180009939
0x180009933  call    cs:__imp_CloseHandle
0x180009939  test    r14d, r14d
0x18000993c  jz      short loc_180009949
0x18000993e  mov     rcx, [rsp+1A0h+hMem]; hMem
0x180009943  call    cs:__imp_LocalFree
0x180009949  xor     r14d, r14d
0x18000994c  test    rdi, rdi
0x18000994f  jz      short loc_18000995B
0x180009951  mov     rcx, rdi; pv
0x180009954  call    cs:__imp_CoTaskMemFree
0x18000995a  nop
0x18000995b  mov     rcx, [rsp+1A0h+var_148]
0x180009960  test    rcx, rcx
0x180009963  jz      short loc_180009976
0x180009965  mov     rax, [rcx]
0x180009968  mov     rax, [rax+10h]
0x18000996c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009971  mov     [rsp+1A0h+var_148], r14
0x180009976  mov     rcx, [rsp+1A0h+var_140]
0x18000997b  test    rcx, rcx
0x18000997e  jz      short loc_180009991
0x180009980  mov     rax, [rcx]
0x180009983  mov     rax, [rax+10h]
0x180009987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998c  mov     [rsp+1A0h+var_140], r14
0x180009991  lea     rcx, [rbp+0A0h+var_C8]; this
0x180009995  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18000999a  mov     eax, ebx
0x18000999c  mov     rcx, [rbp+0A0h+var_48]
0x1800099a0  xor     rcx, rsp; StackCookie
0x1800099a3  call    __security_check_cookie
0x1800099a8  add     rsp, 168h
0x1800099af  pop     r15
0x1800099b1  pop     r14
0x1800099b3  pop     r13
0x1800099b5  pop     r12
0x1800099b7  pop     rdi
0x1800099b8  pop     rsi
0x1800099b9  pop     rbx
0x1800099ba  pop     rbp
0x1800099bb  retn
0x1800099bc  call    cs:__imp_GetLastError
0x1800099c2  nop
0x1800099c3  mov     ebx, eax
0x1800099c5  test    eax, eax
0x1800099c7  jle     loc_180009925
0x1800099cd  movzx   ebx, ax
0x1800099d0  or      ebx, 80070000h
0x1800099d6  jmp     loc_180009925
0x1800099db  mov     ebx, 8007000Eh
0x1800099e0  jmp     loc_180009925
0x1800099e5  mov     [rbp+0A0h+Src], rbx
0x1800099e9  lea     r8, [rbp+0A0h+Src]; struct _ACL **
0x1800099ed  mov     rdx, rdi; struct _ACL *
0x1800099f0  call    ?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z; CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)
0x1800099f5  mov     ebx, eax
  ... truncated ...
```
