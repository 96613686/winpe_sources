# CSecurityAdmin2::BuildSecurityDescriptorForRoleSet(void *,void *,void * *,_GUID *,int)

- ea: `0x18003496c`
- end: `0x18003505a`
- name: `?BuildSecurityDescriptorForRoleSet@CSecurityAdmin2@@QEAAJPEAX0PEAPEAXPEAU_GUID@@H@Z`
- size: `1774`
- prototype: `__int64 __fastcall(struct ISimpleTableDispenser **this, void *, struct _GUID *, void **, struct _GUID *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003541c`

## callees

- `0x18000ae48`
- `0x18000b230`
- `0x180032d20`
- `0x180033d68`
- `0x180033eb4`
- `0x18003496c`
- `0x18003885c`
- `0x18005550e`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034f54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180034f54`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034f66`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180034f66`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003501b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003501b`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180034fcd`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180034fcd`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180034ca6`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180034ca6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180034c63`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180034ff9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180034c63`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180034ff9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180034cf2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180034e45`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180034cf2`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180034e45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034d3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034d3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e29`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180034ead`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180034ead`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180034e5e`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180034e6f`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180034e5e`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180034e6f`

## pseudocode

```c
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
0x18003496c  push    rbp
0x18003496e  push    rbx
0x18003496f  push    rsi
0x180034970  push    rdi
0x180034971  push    r12
0x180034973  push    r13
0x180034975  push    r14
0x180034977  push    r15
0x180034979  lea     rbp, [rsp-68h]
0x18003497e  sub     rsp, 168h
0x180034985  mov     rax, cs:__security_cookie
0x18003498c  xor     rax, rsp
0x18003498f  mov     [rbp+0A0h+var_48], rax
0x180034993  mov     r15, r9
0x180034996  mov     r12, rdx
0x180034999  mov     r13, rcx
0x18003499c  mov     [rsp+1A0h+hMem], r8
0x1800349a1  mov     rax, [rbp+0A0h+arg_20]
0x1800349a8  xor     r14d, r14d
0x1800349ab  mov     edi, r14d
0x1800349ae  mov     [rbp+0A0h+pDacl], r14
0x1800349b2  mov     [rsp+1A0h+var_130], r14d
0x1800349b7  mov     [rsp+1A0h+var_148], r14
0x1800349bc  mov     [rsp+1A0h+var_140], r14
0x1800349c1  xorps   xmm0, xmm0
0x1800349c4  movups  xmmword ptr [rbp+0A0h+pTrustee.pMultipleTrustee], xmm0
0x1800349c8  movups  xmmword ptr [rbp+0A0h+pTrustee.TrusteeType], xmm0
0x1800349cc  xorps   xmm1, xmm1
0x1800349cf  movups  xmmword ptr [rbp+0A0h+pGroup.pMultipleTrustee], xmm1
0x1800349d3  movups  xmmword ptr [rbp+0A0h+pGroup.TrusteeType], xmm1
0x1800349d7  mov     [rsp+1A0h+var_14C], r14d
0x1800349dc  mov     [rsp+1A0h+bDaclPresent], r14d
0x1800349e1  mov     [rsp+1A0h+bDaclDefaulted], r14d
0x1800349e6  movups  xmmword ptr [rbp+0A0h+GenericMapping.GenericRead], xmm0
0x1800349ea  mov     [rsp+1A0h+var_150], r14d
0x1800349ef  mov     [rbp+0A0h+var_C8], r14
0x1800349f3  mov     [rbp+0A0h+var_C0], r14d
0x1800349f7  mov     [rbp+0A0h+var_B8], r14
0x1800349fb  mov     [rbp+0A0h+hObject], r14
0x1800349ff  lea     edx, [r14+1]
0x180034a03  cmp     [rbp+0A0h+arg_28], r14d
0x180034a0a  jnz     short loc_180034A15
0x180034a0c  test    r8, r8
0x180034a0f  jnz     loc_180034F32
0x180034a15  mov     esi, 8
0x180034a1a  test    rax, rax
0x180034a1d  jz      loc_180034E26
0x180034a23  mov     [rbp+0A0h+var_B0], rax
0x180034a27  mov     [rbp+0A0h+var_A8], r14
0x180034a2b  lea     ecx, [rsi+40h]; this
0x180034a2e  mov     [rbp+0A0h+var_A0], ecx
0x180034a31  lea     eax, [rsi+8]
0x180034a34  mov     [rbp+0A0h+var_9C], eax
0x180034a37  mov     [rbp+0A0h+var_F8], r14
0x180034a3b  mov     [rbp+0A0h+var_F0], r14
0x180034a3f  mov     dword ptr [rbp+0A0h+var_E8], ecx
0x180034a42  mov     dword ptr [rbp+0A0h+var_E8+4], eax
0x180034a45  mov     [rbp+0A0h+var_E0], r14
0x180034a49  mov     [rbp+0A0h+var_D8], r14d
0x180034a4d  mov     [rbp+0A0h+var_D4], edx
0x180034a50  mov     [rbp+0A0h+var_D0], 82h
0x180034a58  mov     [rbp+0A0h+pSecurityDescriptor], r14
0x180034a5c  lea     rax, [rsp+1A0h+var_148]
0x180034a61  mov     [rsp+1A0h+pNewSD], rax; void **
0x180034a66  mov     dword ptr [rsp+1A0h+pSizeNewSD], 20000h; unsigned int
0x180034a6e  mov     [rsp+1A0h+pListOfAuditEntries], rdx; void *
0x180034a73  lea     rax, [rbp+0A0h+var_B0]
0x180034a77  mov     qword ptr [rsp+1A0h+nAceListLength], rax; void *
0x180034a7c  lea     r9, tidCOMSERVICES_ROLESET; struct _GUID *
0x180034a83  mov     rdx, [r13+20h]; struct ISimpleTableDispenser *
0x180034a87  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180034a8c  mov     ebx, eax
0x180034a8e  test    eax, eax
0x180034a90  js      loc_180034D1D
0x180034a96  mov     rcx, [rsp+1A0h+var_148]
0x180034a9b  mov     rax, [rcx]
0x180034a9e  mov     rax, [rax+18h]
0x180034aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034aa7  mov     ebx, eax
0x180034aa9  test    eax, eax
0x180034aab  js      loc_180034D1D
0x180034ab1  mov     rcx, [rsp+1A0h+var_148]
0x180034ab6  mov     rax, [rcx]
0x180034ab9  xor     edx, edx
0x180034abb  mov     rax, [rax+30h]
0x180034abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ac4  mov     rcx, [rsp+1A0h+var_148]
0x180034ac9  mov     rax, [rcx]
0x180034acc  mov     [rsp+1A0h+pNewSD], r14
0x180034ad1  lea     rdx, [rsp+1A0h+var_130]
0x180034ad6  mov     [rsp+1A0h+pSizeNewSD], rdx
0x180034adb  mov     [rsp+1A0h+pOldSD], r14; unsigned int
0x180034ae0  mov     [rsp+1A0h+pListOfAuditEntries], r14
0x180034ae5  mov     qword ptr [rsp+1A0h+nAceListLength], r14
0x180034aea  xor     r9d, r9d
0x180034aed  xor     r8d, r8d
0x180034af0  xor     edx, edx
0x180034af2  mov     rax, [rax+48h]
0x180034af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034afb  mov     ebx, eax
0x180034afd  test    eax, eax
0x180034aff  js      loc_180034D1D
0x180034b05  cmp     [rsp+1A0h+var_130], r14d
0x180034b0a  jz      loc_180034E26
0x180034b10  lea     r14d, [rsi-6]
0x180034b14  mov     rcx, [rsp+1A0h+var_148]
0x180034b19  mov     rax, [rcx]
0x180034b1c  lea     rdx, [rbp+0A0h+var_E0]
0x180034b20  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x180034b25  xor     r9d, r9d
0x180034b28  xor     r8d, r8d
0x180034b2b  lea     edx, [r9+1]
0x180034b2f  mov     rax, [rax+40h]
0x180034b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b38  mov     ebx, eax
0x180034b3a  test    eax, eax
0x180034b3c  js      loc_180034D1D
0x180034b42  mov     rcx, [rsp+1A0h+var_148]
0x180034b47  mov     rax, [rcx]
0x180034b4a  lea     rdx, [rbp+0A0h+var_F8]
0x180034b4e  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x180034b53  xor     r9d, r9d
0x180034b56  xor     r8d, r8d
0x180034b59  mov     edx, r14d
0x180034b5c  mov     rax, [rax+40h]
0x180034b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b65  mov     ebx, eax
0x180034b67  test    eax, eax
0x180034b69  js      loc_180034D1D
0x180034b6f  mov     rcx, [rbp+0A0h+var_E0]
0x180034b73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034b77  xor     ebx, ebx
0x180034b79  inc     rax
0x180034b7c  cmp     [rcx+rax*2], bx
0x180034b80  jnz     short loc_180034B79
0x180034b82  lea     eax, ds:2[rax*2]
0x180034b89  mov     dword ptr [rbp+0A0h+var_D0+4], eax
0x180034b8c  mov     rcx, [rsp+1A0h+var_140]
0x180034b91  test    rcx, rcx
0x180034b94  jz      short loc_180034BA7
0x180034b96  mov     rax, [rcx]
0x180034b99  mov     rax, [rax+10h]
0x180034b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ba2  mov     [rsp+1A0h+var_140], rbx
0x180034ba7  lea     rax, [rsp+1A0h+var_140]
0x180034bac  mov     [rsp+1A0h+pNewSD], rax; void **
0x180034bb1  mov     dword ptr [rsp+1A0h+pSizeNewSD], 20000h; unsigned int
0x180034bb9  mov     [rsp+1A0h+pListOfAuditEntries], r14; void *
0x180034bbe  lea     rax, [rbp+0A0h+var_F8]
0x180034bc2  mov     qword ptr [rsp+1A0h+nAceListLength], rax; void *
0x180034bc7  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180034bce  mov     rdx, [r13+18h]; struct ISimpleTableDispenser *
0x180034bd2  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180034bd7  mov     ebx, eax
0x180034bd9  test    eax, eax
0x180034bdb  js      loc_180034D1D
0x180034be1  mov     rcx, [rsp+1A0h+var_140]
0x180034be6  mov     rax, [rcx]
0x180034be9  mov     rax, [rax+18h]
0x180034bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bf2  mov     ebx, eax
0x180034bf4  test    eax, eax
0x180034bf6  js      loc_180034D1D
0x180034bfc  mov     rcx, [rsp+1A0h+var_140]
0x180034c01  mov     rax, [rcx]
0x180034c04  xor     edx, edx
0x180034c06  mov     rax, [rax+30h]
0x180034c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c0f  mov     ebx, eax
0x180034c11  test    eax, eax
0x180034c13  js      loc_180034D1D
0x180034c19  mov     rcx, [rsp+1A0h+var_140]
0x180034c1e  mov     rax, [rcx]
0x180034c21  lea     rdx, [rbp+0A0h+pSecurityDescriptor]
0x180034c25  mov     qword ptr [rsp+1A0h+nAceListLength], rdx
0x180034c2a  xor     r9d, r9d
0x180034c2d  xor     r8d, r8d
0x180034c30  mov     edx, r14d
0x180034c33  mov     rax, [rax+40h]
0x180034c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c3c  mov     ebx, eax
0x180034c3e  test    eax, eax
0x180034c40  js      loc_180034D1D
0x180034c46  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180034c4a  xor     ebx, ebx
0x180034c4c  test    rcx, rcx
0x180034c4f  jz      loc_180034E1C
0x180034c55  lea     r9, [rsp+1A0h+bDaclDefaulted]; lpbDaclDefaulted
0x180034c5a  lea     r8, [rbp+0A0h+pDacl]; pDacl
0x180034c5e  lea     rdx, [rsp+1A0h+bDaclPresent]; lpbDaclPresent
0x180034c63  call    cs:__imp_GetSecurityDescriptorDacl
0x180034c69  test    eax, eax
0x180034c6b  jz      loc_180034DB3
0x180034c71  cmp     [rsp+1A0h+bDaclPresent], ebx
0x180034c75  jz      short loc_180034CB4
0x180034c77  mov     r9, [rbp+0A0h+pDacl]
0x180034c7b  test    r9, r9
0x180034c7e  jz      short loc_180034CB4
0x180034c80  movzx   eax, word ptr [r9+2]
0x180034c85  test    rdi, rdi
0x180034c88  jnz     short loc_180034C91
0x180034c8a  add     eax, 0FFFFFFF8h
0x180034c8d  add     esi, eax
0x180034c8f  jmp     short loc_180034CB4
0x180034c91  sub     eax, 8
0x180034c94  add     r9, 8; pAceList
0x180034c98  mov     [rsp+1A0h+nAceListLength], eax; nAceListLength
0x180034c9c  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180034ca0  mov     edx, r14d; dwAceRevision
0x180034ca3  mov     rcx, rdi; pAcl
0x180034ca6  call    cs:__imp_AddAce
0x180034cac  test    eax, eax
0x180034cae  jz      loc_180034DB3
0x180034cb4  mov     rcx, [rsp+1A0h+var_148]
0x180034cb9  mov     rax, [rcx]
0x180034cbc  mov     rax, [rax+28h]
0x180034cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cc5  test    eax, eax
0x180034cc7  jns     loc_180034B14
0x180034ccd  test    rdi, rdi
0x180034cd0  jnz     loc_180034DDC
0x180034cd6  mov     ecx, esi; cb
0x180034cd8  call    cs:__imp_CoTaskMemAlloc
0x180034cde  mov     rdi, rax
0x180034ce1  test    rax, rax
0x180034ce4  jz      loc_180034DD2
0x180034cea  mov     r8d, r14d; dwAclRevision
0x180034ced  mov     edx, esi; nAclLength
0x180034cef  mov     rcx, rax; pAcl
0x180034cf2  call    cs:__imp_InitializeAcl
0x180034cf8  test    eax, eax
0x180034cfa  jz      loc_180034DB3
0x180034d00  mov     rcx, [rsp+1A0h+var_148]
0x180034d05  mov     rdx, [rcx]
0x180034d08  mov     rax, [rdx+30h]
0x180034d0c  xor     edx, edx
0x180034d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d13  mov     ebx, eax
0x180034d15  test    eax, eax
0x180034d17  jns     loc_180034B14
0x180034d1d  mov     r14d, [rsp+1A0h+var_150]
0x180034d22  mov     rcx, [rbp+0A0h+hObject]; hObject
0x180034d26  test    rcx, rcx
0x180034d29  jz      short loc_180034D31
0x180034d2b  call    cs:__imp_CloseHandle
0x180034d31  test    r14d, r14d
0x180034d34  jz      short loc_180034D41
0x180034d36  mov     rcx, [rsp+1A0h+hMem]; hMem
0x180034d3b  call    cs:__imp_LocalFree
0x180034d41  xor     r14d, r14d
0x180034d44  test    rdi, rdi
0x180034d47  jz      short loc_180034D52
0x180034d49  mov     rcx, rdi; pv
0x180034d4c  call    cs:__imp_CoTaskMemFree
0x180034d52  mov     rcx, [rsp+1A0h+var_148]
0x180034d57  test    rcx, rcx
0x180034d5a  jz      short loc_180034D6D
0x180034d5c  mov     rax, [rcx]
0x180034d5f  mov     rax, [rax+10h]
0x180034d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d68  mov     [rsp+1A0h+var_148], r14
0x180034d6d  mov     rcx, [rsp+1A0h+var_140]
0x180034d72  test    rcx, rcx
0x180034d75  jz      short loc_180034D88
0x180034d77  mov     rax, [rcx]
0x180034d7a  mov     rax, [rax+10h]
0x180034d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d83  mov     [rsp+1A0h+var_140], r14
0x180034d88  lea     rcx, [rbp+0A0h+var_C8]; this
0x180034d8c  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180034d91  mov     eax, ebx
0x180034d93  mov     rcx, [rbp+0A0h+var_48]
0x180034d97  xor     rcx, rsp; StackCookie
0x180034d9a  call    __security_check_cookie
0x180034d9f  add     rsp, 168h
0x180034da6  pop     r15
0x180034da8  pop     r14
0x180034daa  pop     r13
0x180034dac  pop     r12
0x180034dae  pop     rdi
0x180034daf  pop     rsi
0x180034db0  pop     rbx
0x180034db1  pop     rbp
0x180034db2  retn
0x180034db3  call    cs:__imp_GetLastError
0x180034db9  nop
0x180034dba  mov     ebx, eax
0x180034dbc  test    eax, eax
0x180034dbe  jle     loc_180034D1D
0x180034dc4  movzx   ebx, ax
0x180034dc7  or      ebx, 80070000h
0x180034dcd  jmp     loc_180034D1D
0x180034dd2  mov     ebx, 8007000Eh
0x180034dd7  jmp     loc_180034D1D
0x180034ddc  mov     [rbp+0A0h+Src], rbx
0x180034de0  lea     r8, [rbp+0A0h+Src]; struct _ACL **
0x180034de4  mov     rdx, rdi; struct _ACL *
0x180034de7  call    ?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z; CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)
0x180034dec  mov     ebx, eax
0x180034dee  xor     ecx, ecx
  ... truncated ...
```
