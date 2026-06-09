# CSecurityAdmin2::UpdateRole(_GUID const &,ushort *)

- ea: `0x180028da8`
- end: `0x1800293bf`
- name: `?UpdateRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z`
- size: `1559`
- prototype: `int(CSecurityAdmin2 *__hidden this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180026b60`
- `0x1800286b0`

## callees

- `0x180015594`
- `0x1800269a8`
- `0x180026af4`
- `0x180028da8`
- `0x180029944`
- `0x18005582e`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002931e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800290df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002931e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002905e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002905e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800291ac`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800291ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029341`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029341`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x18002915a`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x18002915a`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029109`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x18002911a`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180029109`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x18002911a`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800290ac`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x1800290ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSecurityAdmin2::UpdateRole(
        struct ISimpleTableDispenser **this,
        const struct _GUID *a2,
        unsigned __int16 *a3)
{
  __int64 v4; // r9
  int v5; // r11d
  __int64 v6; // r8
  int v7; // r10d
  const unsigned __int16 *v8; // rcx
  int v9; // r12d
  CSecurityAdmin2 *v10; // rcx
  const struct _GUID *v11; // r8
  __int64 result; // rax
  signed int Table; // ebx
  ULONG v14; // r15d
  struct _EXPLICIT_ACCESS_W *v15; // rdi
  CSecurityAdmin2 *v16; // rcx
  PSID v17; // rbx
  void *v18; // rax
  __int64 v19; // rcx
  CSecurityAdmin2 *v20; // rcx
  signed int v21; // esi
  const struct _GUID *v22; // r8
  bool v23; // cc
  unsigned int v24; // r8d
  SIZE_T v25; // rdx
  char *v26; // rax
  ULONG i; // r14d
  unsigned int pOldSD; // [rsp+30h] [rbp-D0h]
  unsigned int pOldSDa; // [rsp+30h] [rbp-D0h]
  struct ISimpleTableWrite *v30; // [rsp+50h] [rbp-B0h] BYREF
  void *v31; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v39[2]; // [rsp+98h] [rbp-68h] BYREF
  int v40; // [rsp+A8h] [rbp-58h]
  int v41; // [rsp+ACh] [rbp-54h]
  unsigned __int16 *v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+BCh] [rbp-44h]
  int v45; // [rsp+C0h] [rbp-40h]
  int v46; // [rsp+C4h] [rbp-3Ch]
  _QWORD v47[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v48; // [rsp+D8h] [rbp-28h]
  int v49; // [rsp+DCh] [rbp-24h]
  __int64 v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E8h] [rbp-18h]
  int v52; // [rsp+ECh] [rbp-14h]
  int v53; // [rsp+F0h] [rbp-10h]
  int v54; // [rsp+F4h] [rbp-Ch]
  struct _TRUSTEE_W pGroup; // [rsp+F8h] [rbp-8h] BYREF
  struct _TRUSTEE_W pTrustee; // [rsp+118h] [rbp+18h] BYREF
  ULONG pSizeNewSD; // [rsp+190h] [rbp+90h] BYREF
  SIZE_T cb; // [rsp+198h] [rbp+98h] BYREF
  struct _ACL pAcl; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v60; // [rsp+1A8h] [rbp+A8h] BYREF

  v39[0] = a2;
  v39[1] = 0;
  v40 = 72;
  v41 = 16;
  v42 = a3;
  v43 = 0;
  v44 = 1;
  v45 = 130;
  v46 = 2 * safe_lstrlenW(a3) + 2;
  v47[0] = v4;
  v47[1] = 0;
  v48 = 72;
  v49 = v5;
  v50 = v6;
  v51 = 0;
  v52 = 1;
  v53 = v7;
  v54 = 2 * safe_lstrlenW(v8) + 2;
  v30 = 0;
  v31 = 0;
  v9 = 0;
  *(_DWORD *)&pAcl.AclRevision = 0;
  v60 = 0;
  pSizeNewSD = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  memset(&pGroup, 0, sizeof(pGroup));
  hMem = 0;
  result = CSecurityAdmin2::GetTable(
             v10,
             this[2],
             v11,
             &tidCOMSERVICES_ROLECONFIG,
             v39,
             (void *)2,
             pOldSD,
             0x20000u,
             (void **)&v30);
  if ( (int)result < 0 )
    return result;
  Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 24LL))(v30);
  if ( Table >= 0 )
  {
    (*(void (__fastcall **)(struct ISimpleTableWrite *, _QWORD))(*(_QWORD *)v30 + 48LL))(v30, 0);
    Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v30 + 72LL))(
              v30,
              0,
              0,
              0,
              0,
              0,
              0,
              &v60,
              0);
    if ( Table >= 0 )
    {
      v14 = 0;
      v15 = 0;
      if ( v60 )
      {
        v38 = 0;
        pv = 0;
        Src = 0;
        pSid = 0;
        v33 = 0;
        v35 = 0;
        LODWORD(cb) = 0;
        v15 = (struct _EXPLICIT_ACCESS_W *)CoTaskMemAlloc(saturated_mul(v60, 0x30u));
        if ( !v15 )
        {
          Table = -2147024882;
          goto LABEL_38;
        }
        while ( 1 )
        {
          Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, int *, __int64 *))(*(_QWORD *)v30 + 64LL))(
                    v30,
                    2,
                    &v33,
                    &v35,
                    &v38);
          if ( Table < 0 )
            break;
          Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, SIZE_T *, void **))(*(_QWORD *)v30 + 64LL))(
                    v30,
                    3,
                    &v33,
                    &cb,
                    &Src);
          if ( Table < 0 )
            break;
          Table = (*((__int64 (__fastcall **)(struct ISimpleTableDispenser **, __int64, LPVOID *, _QWORD))*this + 11))(
                    this,
                    v38,
                    &pv,
                    0);
          if ( Table < 0 )
            break;
          if ( (unsigned int)CSecurityAdmin2::VerifyUserNameAndSid(
                               v16,
                               v30,
                               (unsigned __int16 *)pv,
                               Src,
                               cb,
                               (int *)&pAcl,
                               &pSid) )
          {
            v17 = pSid;
            if ( !pSid )
            {
              if ( !Src || (v18 = CoTaskMemAlloc((unsigned int)cb), v17 = v18, (pSid = v18) == 0) )
              {
                Table = -2147418113;
                v9 = *(_DWORD *)&pAcl.AclRevision;
                break;
              }
              memcpy_0(v18, Src, (unsigned int)cb);
            }
            v19 = v14;
            v15[v19].grfAccessPermissions = 1;
            v15[v19].grfAccessMode = GRANT_ACCESS;
            v15[v19].grfInheritance = 3;
            BuildTrusteeWithSidW(&v15[v19].Trustee, v17);
            ++v14;
            v9 = *(_DWORD *)&pAcl.AclRevision;
          }
          else
          {
            (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 136LL))(v30);
            v9 = 1;
            *(_DWORD *)&pAcl.AclRevision = 1;
          }
          CoTaskMemFree(pv);
          if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 40LL))(v30) < 0 )
            goto LABEL_18;
        }
LABEL_35:
        for ( i = 0; i < v14; ++i )
          CoTaskMemFree(v15[i].Trustee.ptstrName);
        CoTaskMemFree(v15);
        goto LABEL_38;
      }
LABEL_18:
      BuildTrusteeWithNameW(&pTrustee, (LPWSTR)L"CURRENT_USER");
      BuildTrusteeWithNameW(&pGroup, (LPWSTR)L"CURRENT_USER");
      pGroup.TrusteeType = TRUSTEE_IS_GROUP;
      v21 = BuildSecurityDescriptorW(&pTrustee, &pGroup, v14, v15, 0, 0, 0, &pSizeNewSD, &hMem);
      if ( v9 )
      {
        Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 96LL))(v30);
        if ( Table < 0 )
        {
LABEL_34:
          if ( !v15 )
            goto LABEL_38;
          goto LABEL_35;
        }
      }
      if ( v60 )
      {
        v23 = v21 <= 0;
        if ( !v21 )
        {
LABEL_27:
          Table = CSecurityAdmin2::GetTable(
                    v20,
                    this[3],
                    v22,
                    &tidCOMSERVICES_ROLESDCACHE,
                    v47,
                    (void *)2,
                    pOldSDa,
                    0x20000u,
                    &v31);
          if ( Table >= 0 )
          {
            Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 24LL))(v31);
            if ( Table >= 0 )
            {
              Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v31 + 48LL))(v31, 0);
              if ( Table >= 0 )
              {
                Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 128LL))(v31);
                if ( Table >= 0 )
                {
                  Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v31 + 160LL))(
                            v31,
                            2,
                            pSizeNewSD,
                            hMem);
                  if ( Table >= 0 )
                  {
                    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 144LL))(v31);
                    if ( Table >= 0 )
                      Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 96LL))(v31);
                  }
                }
              }
            }
          }
          goto LABEL_34;
        }
      }
      else
      {
        v23 = v21 <= 0;
        if ( !v21 )
        {
          pAcl = 0;
          InitializeAcl(&pAcl, 8u, 4u);
          v25 = pSizeNewSD + 8;
          if ( (unsigned int)v25 < pSizeNewSD )
          {
            Table = -2147024362;
            goto LABEL_34;
          }
          v26 = (char *)SmartLocalReAlloc(hMem, v25, v24);
          if ( !v26 )
          {
            Table = -2147024882;
            goto LABEL_34;
          }
          hMem = v26;
          *(struct _ACL *)&v26[pSizeNewSD] = pAcl;
          v20 = (CSecurityAdmin2 *)pSizeNewSD;
          *((_DWORD *)hMem + 4) = pSizeNewSD;
          pSizeNewSD += 8;
          goto LABEL_27;
        }
      }
      if ( v23 )
        Table = v21;
      else
        Table = (unsigned __int16)v21 | 0x80070000;
      goto LABEL_34;
    }
  }
LABEL_38:
  if ( hMem )
    LocalFree(hMem);
  if ( v30 )
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
  if ( Table >= 0 )
    return v9 != 0;
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x180028da8  push    rbp
0x180028daa  push    rbx
0x180028dab  push    rsi
0x180028dac  push    rdi
0x180028dad  push    r12
0x180028daf  push    r13
0x180028db1  push    r14
0x180028db3  push    r15
0x180028db5  lea     rbp, [rsp-48h]
0x180028dba  sub     rsp, 148h
0x180028dc1  mov     r9, rdx
0x180028dc4  mov     r14, rcx
0x180028dc7  mov     [rbp+80h+var_E8], rdx
0x180028dcb  xor     r13d, r13d
0x180028dce  mov     [rbp+80h+var_E0], r13
0x180028dd2  lea     ebx, [r13+48h]
0x180028dd6  mov     [rbp+80h+var_D8], ebx
0x180028dd9  lea     r11d, [r13+10h]
0x180028ddd  mov     [rbp+80h+var_D4], r11d
0x180028de1  mov     [rbp+80h+var_D0], r8
0x180028de5  mov     [rbp+80h+var_C8], r13d
0x180028de9  lea     esi, [rbx-47h]
0x180028dec  mov     [rbp+80h+var_C4], esi
0x180028def  lea     r10d, [rbx+3Ah]
0x180028df3  mov     [rbp+80h+var_C0], r10d
0x180028df7  mov     rcx, r8; unsigned __int16 *
0x180028dfa  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180028dff  lea     eax, ds:2[rax*2]
0x180028e06  mov     [rbp+80h+var_BC], eax
0x180028e09  mov     [rbp+80h+var_B8], r9
0x180028e0d  mov     [rbp+80h+var_B0], r13
0x180028e11  mov     [rbp+80h+var_A8], ebx
0x180028e14  mov     [rbp+80h+var_A4], r11d
0x180028e18  mov     [rbp+80h+var_A0], r8
0x180028e1c  mov     [rbp+80h+var_98], r13d
0x180028e20  mov     [rbp+80h+var_94], esi
0x180028e23  mov     [rbp+80h+var_90], r10d
0x180028e27  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180028e2c  lea     eax, ds:2[rax*2]
0x180028e33  mov     [rbp+80h+var_8C], eax
0x180028e36  mov     [rsp+180h+var_130], r13
0x180028e3b  mov     [rsp+180h+var_128], r13
0x180028e40  mov     r12d, r13d
0x180028e43  mov     dword ptr [rbp+80h+pAcl.AclRevision], r13d
0x180028e4a  mov     [rbp+80h+arg_18], r13d
0x180028e51  mov     [rbp+80h+arg_0], r13d
0x180028e58  xorps   xmm0, xmm0
0x180028e5b  movups  xmmword ptr [rbp+80h+pTrustee.pMultipleTrustee], xmm0
0x180028e5f  movups  xmmword ptr [rbp+80h+pTrustee.TrusteeType], xmm0
0x180028e63  xorps   xmm1, xmm1
0x180028e66  movups  xmmword ptr [rbp+80h+pGroup.pMultipleTrustee], xmm1
0x180028e6a  movups  xmmword ptr [rbp+80h+pGroup.TrusteeType], xmm1
0x180028e6e  mov     [rsp+180h+hMem], r13
0x180028e73  lea     rax, [rsp+180h+var_130]
0x180028e78  mov     [rsp+180h+pNewSD], rax; void **
0x180028e7d  mov     dword ptr [rsp+180h+pSizeNewSD], 20000h; unsigned int
0x180028e85  mov     [rsp+180h+pListOfAuditEntries], 2; void *
0x180028e8e  lea     rax, [rbp+80h+var_E8]
0x180028e92  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rax; void *
0x180028e97  lea     r9, tidCOMSERVICES_ROLECONFIG; struct _GUID *
0x180028e9e  mov     rdx, [r14+10h]; struct ISimpleTableDispenser *
0x180028ea2  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180028ea7  test    eax, eax
0x180028ea9  js      loc_180029382
0x180028eaf  mov     rcx, [rsp+180h+var_130]
0x180028eb4  mov     rax, [rcx]
0x180028eb7  mov     rax, [rax+18h]
0x180028ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ec0  mov     ebx, eax
0x180028ec2  test    eax, eax
0x180028ec4  js      loc_180029337
0x180028eca  mov     rcx, [rsp+180h+var_130]
0x180028ecf  mov     rax, [rcx]
0x180028ed2  xor     edx, edx
0x180028ed4  mov     rax, [rax+30h]
0x180028ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028edd  mov     rcx, [rsp+180h+var_130]
0x180028ee2  mov     rax, [rcx]
0x180028ee5  mov     [rsp+180h+pNewSD], r13
0x180028eea  lea     rdx, [rbp+80h+arg_18]
0x180028ef1  mov     [rsp+180h+pSizeNewSD], rdx
0x180028ef6  mov     [rsp+180h+pOldSD], r13
0x180028efb  mov     [rsp+180h+pListOfAuditEntries], r13
0x180028f00  mov     qword ptr [rsp+180h+cCountOfAuditEntries], r13
0x180028f05  xor     r9d, r9d
0x180028f08  xor     r8d, r8d
0x180028f0b  xor     edx, edx
0x180028f0d  mov     rax, [rax+48h]
0x180028f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f16  mov     ebx, eax
0x180028f18  test    eax, eax
0x180028f1a  js      loc_180029337
0x180028f20  mov     r15d, r13d
0x180028f23  mov     edi, r13d
0x180028f26  mov     eax, [rbp+80h+arg_18]
0x180028f2c  test    eax, eax
0x180028f2e  jz      loc_1800290FE
0x180028f34  mov     [rbp+80h+var_F0], r13
0x180028f38  mov     [rbp+80h+pv], r13
0x180028f3c  mov     [rsp+180h+Src], r13
0x180028f41  mov     [rbp+80h+pSid], r13
0x180028f45  mov     [rsp+180h+var_118], r13d
0x180028f4a  mov     [rsp+180h+var_108], r13d
0x180028f4f  mov     dword ptr [rbp+80h+cb], r13d
0x180028f56  mov     ecx, eax
0x180028f58  lea     eax, [rsi+2Fh]
0x180028f5b  mul     rcx
0x180028f5e  lea     rcx, [r13-1]
0x180028f62  cmovb   rax, rcx
0x180028f66  mov     rcx, rax; cb
0x180028f69  call    cs:__imp_CoTaskMemAlloc
0x180028f6f  mov     rdi, rax
0x180028f72  test    rax, rax
0x180028f75  jnz     short loc_180028F81
0x180028f77  mov     ebx, 8007000Eh
0x180028f7c  jmp     loc_180029337
0x180028f81  mov     rcx, [rsp+180h+var_130]
0x180028f86  mov     rax, [rcx]
0x180028f89  lea     rdx, [rbp+80h+var_F0]
0x180028f8d  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rdx
0x180028f92  lea     r9, [rsp+180h+var_108]
0x180028f97  lea     r8, [rsp+180h+var_118]
0x180028f9c  mov     edx, 2
0x180028fa1  mov     rax, [rax+40h]
0x180028fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028faa  mov     ebx, eax
0x180028fac  test    eax, eax
0x180028fae  js      loc_180029304
0x180028fb4  mov     rcx, [rsp+180h+var_130]
0x180028fb9  mov     rax, [rcx]
0x180028fbc  lea     rdx, [rsp+180h+Src]
0x180028fc1  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rdx
0x180028fc6  lea     r9, [rbp+80h+cb]
0x180028fcd  lea     r8, [rsp+180h+var_118]
0x180028fd2  mov     edx, 3
0x180028fd7  mov     rax, [rax+40h]
0x180028fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fe0  mov     ebx, eax
0x180028fe2  test    eax, eax
0x180028fe4  js      loc_180029304
0x180028fea  mov     rax, [r14]
0x180028fed  xor     r9d, r9d
0x180028ff0  lea     r8, [rbp+80h+pv]
0x180028ff4  mov     rdx, [rbp+80h+var_F0]
0x180028ff8  mov     rcx, r14
0x180028ffb  mov     rax, [rax+58h]
0x180028fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029004  mov     ebx, eax
0x180029006  test    eax, eax
0x180029008  js      loc_180029304
0x18002900e  lea     rax, [rbp+80h+pSid]
0x180029012  mov     [rsp+180h+pOldSD], rax; void **
0x180029017  lea     rax, [rbp+80h+pAcl]
0x18002901e  mov     [rsp+180h+pListOfAuditEntries], rax; int *
0x180029023  mov     eax, dword ptr [rbp+80h+cb]
0x180029029  mov     [rsp+180h+cCountOfAuditEntries], eax; unsigned int
0x18002902d  mov     r9, [rsp+180h+Src]; void *
0x180029032  mov     r8, [rbp+80h+pv]; unsigned __int16 *
0x180029036  mov     rdx, [rsp+180h+var_130]; struct ISimpleTableWrite *
0x18002903b  call    ?VerifyUserNameAndSid@CSecurityAdmin2@@QEAAHPEAUISimpleTableWrite@@PEAGPEAXKPEAHPEAPEAX@Z; CSecurityAdmin2::VerifyUserNameAndSid(ISimpleTableWrite *,ushort *,void *,ulong,int *,void * *)
0x180029040  test    eax, eax
0x180029042  jz      short loc_1800290BE
0x180029044  mov     rbx, [rbp+80h+pSid]
0x180029048  test    rbx, rbx
0x18002904b  jnz     short loc_180029088
0x18002904d  cmp     [rsp+180h+Src], r13
0x180029052  jz      loc_1800291DF
0x180029058  mov     ecx, dword ptr [rbp+80h+cb]; cb
0x18002905e  call    cs:__imp_CoTaskMemAlloc
0x180029064  mov     rbx, rax
0x180029067  mov     [rbp+80h+pSid], rax
0x18002906b  test    rax, rax
0x18002906e  jz      loc_1800291DF
0x180029074  mov     r8d, dword ptr [rbp+80h+cb]; Size
0x18002907b  mov     rdx, [rsp+180h+Src]; Src
0x180029080  mov     rcx, rax; void *
0x180029083  call    memcpy_0
0x180029088  mov     eax, r15d
0x18002908b  lea     rcx, [rax+rax*2]
0x18002908f  shl     rcx, 4
0x180029093  mov     [rcx+rdi], esi
0x180029096  mov     [rcx+rdi+4], esi
0x18002909a  mov     dword ptr [rcx+rdi+8], 3
0x1800290a2  add     rcx, 10h
0x1800290a6  add     rcx, rdi; pTrustee
0x1800290a9  mov     rdx, rbx; pSid
0x1800290ac  call    cs:__imp_BuildTrusteeWithSidW
0x1800290b2  add     r15d, esi
0x1800290b5  mov     r12d, dword ptr [rbp+80h+pAcl.AclRevision]
0x1800290bc  jmp     short loc_1800290DB
0x1800290be  mov     rcx, [rsp+180h+var_130]
0x1800290c3  mov     rax, [rcx]
0x1800290c6  mov     rax, [rax+88h]
0x1800290cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290d2  mov     r12d, esi
0x1800290d5  mov     dword ptr [rbp+80h+pAcl.AclRevision], esi
0x1800290db  mov     rcx, [rbp+80h+pv]; pv
0x1800290df  call    cs:__imp_CoTaskMemFree
0x1800290e5  mov     rcx, [rsp+180h+var_130]
0x1800290ea  mov     rax, [rcx]
0x1800290ed  mov     rax, [rax+28h]
0x1800290f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f6  test    eax, eax
0x1800290f8  jns     loc_180028F81
0x1800290fe  lea     rdx, pName; "CURRENT_USER"
0x180029105  lea     rcx, [rbp+80h+pTrustee]; pTrustee
0x180029109  call    cs:__imp_BuildTrusteeWithNameW
0x18002910f  lea     rdx, pName; "CURRENT_USER"
0x180029116  lea     rcx, [rbp+80h+pGroup]; pTrustee
0x18002911a  call    cs:__imp_BuildTrusteeWithNameW
0x180029120  mov     [rbp+80h+pGroup.TrusteeType], 2
0x180029127  lea     rax, [rsp+180h+hMem]
0x18002912c  mov     [rsp+180h+pNewSD], rax; pNewSD
0x180029131  lea     rax, [rbp+80h+arg_0]
0x180029138  mov     [rsp+180h+pSizeNewSD], rax; pSizeNewSD
0x18002913d  mov     [rsp+180h+pOldSD], r13; unsigned int
0x180029142  mov     [rsp+180h+pListOfAuditEntries], r13; pListOfAuditEntries
0x180029147  mov     [rsp+180h+cCountOfAuditEntries], r13d; cCountOfAuditEntries
0x18002914c  mov     r9, rdi; pListOfAccessEntries
0x18002914f  mov     r8d, r15d; cCountOfAccessEntries
0x180029152  lea     rdx, [rbp+80h+pGroup]; pGroup
0x180029156  lea     rcx, [rbp+80h+pTrustee]; pOwner
0x18002915a  call    cs:__imp_BuildSecurityDescriptorW
0x180029160  mov     esi, eax
0x180029162  test    r12d, r12d
0x180029165  jz      short loc_180029182
0x180029167  mov     rcx, [rsp+180h+var_130]
0x18002916c  mov     rdx, [rcx]
0x18002916f  mov     rax, [rdx+60h]
0x180029173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029178  mov     ebx, eax
0x18002917a  test    eax, eax
0x18002917c  js      loc_1800292FF
0x180029182  cmp     [rbp+80h+arg_18], r13d
0x180029189  jnz     loc_1800293A0
0x18002918f  test    esi, esi
0x180029191  jnz     loc_1800293A8
0x180029197  mov     qword ptr [rbp+80h+pAcl.AclRevision], r13
0x18002919e  lea     edx, [rsi+8]; nAclLength
0x1800291a1  lea     r8d, [rsi+4]; dwAclRevision
0x1800291a5  lea     rcx, [rbp+80h+pAcl]; pAcl
0x1800291ac  call    cs:__imp_InitializeAcl
0x1800291b2  mov     eax, [rbp+80h+arg_0]
0x1800291b8  lea     edx, [rax+8]; uBytes
0x1800291bb  cmp     edx, eax
0x1800291bd  jb      loc_180029396
0x1800291c3  mov     rcx, [rsp+180h+hMem]; Src
0x1800291c8  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x1800291cd  mov     rdx, rax
0x1800291d0  test    rax, rax
0x1800291d3  jnz     short loc_1800291F0
0x1800291d5  mov     ebx, 8007000Eh
0x1800291da  jmp     loc_1800292FF
0x1800291df  mov     ebx, 8000FFFFh
0x1800291e4  mov     r12d, dword ptr [rbp+80h+pAcl.AclRevision]
0x1800291eb  jmp     loc_180029304
0x1800291f0  mov     [rsp+180h+hMem], rdx
0x1800291f5  mov     ecx, [rbp+80h+arg_0]
0x1800291fb  mov     rax, qword ptr [rbp+80h+pAcl.AclRevision]
0x180029202  mov     [rcx+rdx], rax
0x180029206  mov     ecx, [rbp+80h+arg_0]; this
0x18002920c  mov     rax, [rsp+180h+hMem]
0x180029211  mov     [rax+10h], ecx
0x180029214  add     [rbp+80h+arg_0], 8
0x18002921b  lea     rax, [rsp+180h+var_128]
0x180029220  mov     [rsp+180h+pNewSD], rax; void **
0x180029225  mov     dword ptr [rsp+180h+pSizeNewSD], 20000h; unsigned int
0x18002922d  mov     [rsp+180h+pListOfAuditEntries], 2; void *
0x180029236  lea     rax, [rbp+80h+var_B8]
0x18002923a  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rax; void *
0x18002923f  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180029246  mov     rdx, [r14+18h]; struct ISimpleTableDispenser *
0x18002924a  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x18002924f  mov     ebx, eax
0x180029251  test    eax, eax
0x180029253  js      loc_1800292FF
0x180029259  mov     rcx, [rsp+180h+var_128]
0x18002925e  mov     rax, [rcx]
0x180029261  mov     rax, [rax+18h]
0x180029265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002926a  mov     ebx, eax
0x18002926c  test    eax, eax
0x18002926e  js      loc_1800292FF
0x180029274  mov     rcx, [rsp+180h+var_128]
0x180029279  mov     rax, [rcx]
0x18002927c  xor     edx, edx
0x18002927e  mov     rax, [rax+30h]
0x180029282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029287  mov     ebx, eax
0x180029289  test    eax, eax
0x18002928b  js      short loc_1800292FF
0x18002928d  mov     rcx, [rsp+180h+var_128]
0x180029292  mov     rax, [rcx]
0x180029295  mov     rax, [rax+80h]
0x18002929c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292a1  mov     ebx, eax
0x1800292a3  test    eax, eax
0x1800292a5  js      short loc_1800292FF
0x1800292a7  mov     rcx, [rsp+180h+var_128]
0x1800292ac  mov     rax, [rcx]
  ... truncated ...
```
