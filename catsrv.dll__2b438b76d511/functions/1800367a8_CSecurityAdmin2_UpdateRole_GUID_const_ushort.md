# CSecurityAdmin2::UpdateRole(_GUID const &,ushort *)

- ea: `0x1800367a8`
- end: `0x180036dbd`
- name: `?UpdateRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z`
- size: `1557`
- prototype: `int(CSecurityAdmin2 *__hidden this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180033f20`
- `0x1800360b0`

## callees

- `0x18001a6c8`
- `0x180033d68`
- `0x180033eb4`
- `0x1800367a8`
- `0x180037340`
- `0x18005550e`
- `0x180058010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180036bac`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180036bac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036d2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036a5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180036a5e`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180036aac`
- `api-ms-win-security-trustee-l1-1-0!BuildTrusteeWithSidW` at `0x180036aac`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180036b5a`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180036b5a`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180036b09`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180036b1a`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180036b09`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180036b1a`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::UpdateRole(CSecurityAdmin2 *this, const struct _GUID *a2, unsigned __int16 *a3)
{
  int v4; // eax
  __int64 v5; // r9
  int v6; // r11d
  __int64 v7; // r8
  int v8; // r10d
  const unsigned __int16 *v9; // rcx
  int v10; // eax
  struct ISimpleTableDispenser *v11; // rdx
  int v12; // r12d
  CSecurityAdmin2 *v13; // rcx
  const struct _GUID *v14; // r8
  __int64 result; // rax
  signed int Table; // ebx
  ULONG v17; // r15d
  struct _EXPLICIT_ACCESS_W *v18; // rdi
  SIZE_T v19; // rax
  CSecurityAdmin2 *v20; // rcx
  PSID v21; // rbx
  void *v22; // rax
  __int64 v23; // rcx
  CSecurityAdmin2 *v24; // rcx
  signed int v25; // esi
  const struct _GUID *v26; // r8
  bool v27; // cc
  unsigned int v28; // r8d
  SIZE_T v29; // rdx
  char *v30; // rax
  ULONG i; // r14d
  unsigned int pOldSD; // [rsp+30h] [rbp-D0h]
  unsigned int pOldSDa; // [rsp+30h] [rbp-D0h]
  struct ISimpleTableWrite *v34; // [rsp+50h] [rbp-B0h] BYREF
  void *v35; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  void *Src; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v43[2]; // [rsp+98h] [rbp-68h] BYREF
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  unsigned __int16 *v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+BCh] [rbp-44h]
  int v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C4h] [rbp-3Ch]
  _QWORD v51[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v52; // [rsp+D8h] [rbp-28h]
  int v53; // [rsp+DCh] [rbp-24h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  int v57; // [rsp+F0h] [rbp-10h]
  int v58; // [rsp+F4h] [rbp-Ch]
  struct _TRUSTEE_W pGroup; // [rsp+F8h] [rbp-8h] BYREF
  struct _TRUSTEE_W pTrustee; // [rsp+118h] [rbp+18h] BYREF
  ULONG pSizeNewSD; // [rsp+190h] [rbp+90h] BYREF
  SIZE_T cb; // [rsp+198h] [rbp+98h] BYREF
  struct _ACL pAcl; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned int v64; // [rsp+1A8h] [rbp+A8h] BYREF

  v43[0] = a2;
  v43[1] = 0;
  v46 = a3;
  v47 = 0;
  v44 = 72;
  v48 = 1;
  v49 = 130;
  v45 = 16;
  v4 = safe_lstrlenW(a3);
  v51[0] = v5;
  v51[1] = 0;
  v52 = 72;
  v53 = v6;
  v50 = 2 * v4 + 2;
  v54 = v7;
  v55 = 0;
  v56 = 1;
  v57 = v8;
  v10 = safe_lstrlenW(v9);
  v11 = (struct ISimpleTableDispenser *)*((_QWORD *)this + 2);
  v34 = 0;
  v35 = 0;
  *(_DWORD *)&pAcl.AclRevision = 0;
  v58 = 2 * v10 + 2;
  v12 = 0;
  v64 = 0;
  pSizeNewSD = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  hMem = 0;
  memset(&pGroup, 0, sizeof(pGroup));
  result = CSecurityAdmin2::GetTable(
             v13,
             v11,
             v14,
             &tidCOMSERVICES_ROLECONFIG,
             v43,
             (void *)2,
             pOldSD,
             0x20000u,
             (void **)&v34);
  if ( (int)result < 0 )
    return result;
  Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v34 + 24LL))(v34);
  if ( Table >= 0 )
  {
    (*(void (__fastcall **)(struct ISimpleTableWrite *, _QWORD))(*(_QWORD *)v34 + 48LL))(v34, 0);
    Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v34 + 72LL))(
              v34,
              0,
              0,
              0,
              0,
              0,
              0,
              &v64,
              0);
    if ( Table >= 0 )
    {
      v17 = 0;
      v18 = 0;
      if ( v64 )
      {
        v42 = 0;
        pv = 0;
        v19 = 48LL * v64;
        Src = 0;
        pSid = 0;
        if ( !is_mul_ok(v64, 0x30u) )
          v19 = -1;
        v37 = 0;
        v39 = 0;
        LODWORD(cb) = 0;
        v18 = (struct _EXPLICIT_ACCESS_W *)CoTaskMemAlloc(v19);
        if ( !v18 )
        {
          Table = -2147024882;
          goto LABEL_40;
        }
        while ( 1 )
        {
          Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, int *, __int64 *))(*(_QWORD *)v34 + 64LL))(
                    v34,
                    2,
                    &v37,
                    &v39,
                    &v42);
          if ( Table < 0 )
            break;
          Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, SIZE_T *, void **))(*(_QWORD *)v34 + 64LL))(
                    v34,
                    3,
                    &v37,
                    &cb,
                    &Src);
          if ( Table < 0 )
            break;
          Table = (*(__int64 (__fastcall **)(CSecurityAdmin2 *, __int64, LPVOID *, _QWORD))(*(_QWORD *)this + 88LL))(
                    this,
                    v42,
                    &pv,
                    0);
          if ( Table < 0 )
            break;
          if ( (unsigned int)CSecurityAdmin2::VerifyUserNameAndSid(
                               v20,
                               v34,
                               (unsigned __int16 *)pv,
                               Src,
                               cb,
                               (int *)&pAcl,
                               &pSid) )
          {
            v21 = pSid;
            if ( !pSid )
            {
              if ( !Src || (v22 = CoTaskMemAlloc((unsigned int)cb), pSid = v22, (v21 = v22) == 0) )
              {
                v12 = *(_DWORD *)&pAcl.AclRevision;
                Table = -2147418113;
                break;
              }
              memcpy_0(v22, Src, (unsigned int)cb);
            }
            v23 = v17;
            v18[v23].grfAccessPermissions = 1;
            v18[v23].grfAccessMode = GRANT_ACCESS;
            v18[v23].grfInheritance = 3;
            BuildTrusteeWithSidW(&v18[v23].Trustee, v21);
            v12 = *(_DWORD *)&pAcl.AclRevision;
            ++v17;
          }
          else
          {
            (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v34 + 136LL))(v34);
            v12 = 1;
            *(_DWORD *)&pAcl.AclRevision = 1;
          }
          CoTaskMemFree(pv);
          if ( (*(int (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v34 + 40LL))(v34) < 0 )
            goto LABEL_20;
        }
LABEL_37:
        for ( i = 0; i < v17; ++i )
          CoTaskMemFree(v18[i].Trustee.ptstrName);
        CoTaskMemFree(v18);
        goto LABEL_40;
      }
LABEL_20:
      BuildTrusteeWithNameW(&pTrustee, (LPWSTR)L"CURRENT_USER");
      BuildTrusteeWithNameW(&pGroup, (LPWSTR)L"CURRENT_USER");
      pGroup.TrusteeType = TRUSTEE_IS_GROUP;
      v25 = BuildSecurityDescriptorW(&pTrustee, &pGroup, v17, v18, 0, 0, 0, &pSizeNewSD, &hMem);
      if ( v12 )
      {
        Table = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v34 + 96LL))(v34);
        if ( Table < 0 )
        {
LABEL_36:
          if ( !v18 )
            goto LABEL_40;
          goto LABEL_37;
        }
      }
      if ( v64 )
      {
        v27 = v25 <= 0;
        if ( !v25 )
        {
LABEL_29:
          Table = CSecurityAdmin2::GetTable(
                    v24,
                    *((struct ISimpleTableDispenser **)this + 3),
                    v26,
                    &tidCOMSERVICES_ROLESDCACHE,
                    v51,
                    (void *)2,
                    pOldSDa,
                    0x20000u,
                    &v35);
          if ( Table >= 0 )
          {
            Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v35 + 24LL))(v35);
            if ( Table >= 0 )
            {
              Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v35 + 48LL))(v35, 0);
              if ( Table >= 0 )
              {
                Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v35 + 128LL))(v35);
                if ( Table >= 0 )
                {
                  Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v35 + 160LL))(
                            v35,
                            2,
                            pSizeNewSD,
                            hMem);
                  if ( Table >= 0 )
                  {
                    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v35 + 144LL))(v35);
                    if ( Table >= 0 )
                      Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v35 + 96LL))(v35);
                  }
                }
              }
            }
          }
          goto LABEL_36;
        }
      }
      else
      {
        v27 = v25 <= 0;
        if ( !v25 )
        {
          pAcl = 0;
          InitializeAcl(&pAcl, 8u, 4u);
          v29 = pSizeNewSD + 8;
          if ( (unsigned int)v29 < pSizeNewSD )
          {
            Table = -2147024362;
            goto LABEL_36;
          }
          v30 = (char *)SmartLocalReAlloc(hMem, v29, v28);
          if ( !v30 )
          {
            Table = -2147024882;
            goto LABEL_36;
          }
          hMem = v30;
          *(struct _ACL *)&v30[pSizeNewSD] = pAcl;
          v24 = (CSecurityAdmin2 *)pSizeNewSD;
          *((_DWORD *)hMem + 4) = pSizeNewSD;
          pSizeNewSD += 8;
          goto LABEL_29;
        }
      }
      if ( v27 )
        Table = v25;
      else
        Table = (unsigned __int16)v25 | 0x80070000;
      goto LABEL_36;
    }
  }
LABEL_40:
  if ( hMem )
    LocalFree(hMem);
  if ( v34 )
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v35 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
  if ( Table >= 0 )
    return v12 != 0;
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x1800367a8  push    rbp
0x1800367aa  push    rbx
0x1800367ab  push    rsi
0x1800367ac  push    rdi
0x1800367ad  push    r12
0x1800367af  push    r13
0x1800367b1  push    r14
0x1800367b3  push    r15
0x1800367b5  lea     rbp, [rsp-48h]
0x1800367ba  sub     rsp, 148h
0x1800367c1  xor     r13d, r13d
0x1800367c4  mov     [rbp+80h+var_E8], rdx
0x1800367c8  mov     r14, rcx
0x1800367cb  mov     [rbp+80h+var_E0], r13
0x1800367cf  mov     rcx, r8; unsigned __int16 *
0x1800367d2  mov     [rbp+80h+var_D0], r8
0x1800367d6  mov     r9, rdx
0x1800367d9  mov     [rbp+80h+var_C8], r13d
0x1800367dd  lea     ebx, [r13+48h]
0x1800367e1  lea     esi, [rbx-47h]
0x1800367e4  mov     [rbp+80h+var_D8], ebx
0x1800367e7  lea     r10d, [rbx+3Ah]
0x1800367eb  mov     [rbp+80h+var_C4], esi
0x1800367ee  lea     r11d, [r13+10h]
0x1800367f2  mov     [rbp+80h+var_C0], r10d
0x1800367f6  mov     [rbp+80h+var_D4], r11d
0x1800367fa  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800367ff  mov     [rbp+80h+var_B8], r9
0x180036803  mov     [rbp+80h+var_B0], r13
0x180036807  mov     [rbp+80h+var_A8], ebx
0x18003680a  lea     eax, ds:2[rax*2]
0x180036811  mov     [rbp+80h+var_A4], r11d
0x180036815  mov     [rbp+80h+var_BC], eax
0x180036818  mov     [rbp+80h+var_A0], r8
0x18003681c  mov     [rbp+80h+var_98], r13d
0x180036820  mov     [rbp+80h+var_94], esi
0x180036823  mov     [rbp+80h+var_90], r10d
0x180036827  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003682c  mov     rdx, [r14+10h]; struct ISimpleTableDispenser *
0x180036830  lea     r9, tidCOMSERVICES_ROLECONFIG; struct _GUID *
0x180036837  xorps   xmm0, xmm0
0x18003683a  mov     [rsp+180h+var_130], r13
0x18003683f  xorps   xmm1, xmm1
0x180036842  mov     [rsp+180h+var_128], r13
0x180036847  lea     eax, ds:2[rax*2]
0x18003684e  mov     dword ptr [rbp+80h+pAcl.AclRevision], r13d
0x180036855  mov     [rbp+80h+var_8C], eax
0x180036858  mov     r12d, r13d
0x18003685b  lea     rax, [rsp+180h+var_130]
0x180036860  mov     [rbp+80h+arg_18], r13d
0x180036867  mov     [rsp+180h+pNewSD], rax; void **
0x18003686c  lea     rax, [rbp+80h+var_E8]
0x180036870  mov     dword ptr [rsp+180h+pSizeNewSD], 20000h; unsigned int
0x180036878  mov     [rsp+180h+pListOfAuditEntries], 2; void *
0x180036881  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rax; void *
0x180036886  mov     [rbp+80h+arg_0], r13d
0x18003688d  movups  xmmword ptr [rbp+80h+pTrustee.pMultipleTrustee], xmm0
0x180036891  mov     [rsp+180h+hMem], r13
0x180036896  movups  xmmword ptr [rbp+80h+pTrustee.TrusteeType], xmm0
0x18003689a  movups  xmmword ptr [rbp+80h+pGroup.pMultipleTrustee], xmm1
0x18003689e  movups  xmmword ptr [rbp+80h+pGroup.TrusteeType], xmm1
0x1800368a2  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x1800368a7  test    eax, eax
0x1800368a9  js      loc_180036D80
0x1800368af  mov     rcx, [rsp+180h+var_130]
0x1800368b4  mov     rax, [rcx]
0x1800368b7  mov     rax, [rax+18h]
0x1800368bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368c0  mov     ebx, eax
0x1800368c2  test    eax, eax
0x1800368c4  js      loc_180036D35
0x1800368ca  mov     rcx, [rsp+180h+var_130]
0x1800368cf  xor     edx, edx
0x1800368d1  mov     rax, [rcx]
0x1800368d4  mov     rax, [rax+30h]
0x1800368d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368dd  mov     rcx, [rsp+180h+var_130]
0x1800368e2  lea     rdx, [rbp+80h+arg_18]
0x1800368e9  mov     [rsp+180h+pNewSD], r13
0x1800368ee  xor     r9d, r9d
0x1800368f1  mov     [rsp+180h+pSizeNewSD], rdx
0x1800368f6  xor     r8d, r8d
0x1800368f9  mov     [rsp+180h+pOldSD], r13
0x1800368fe  xor     edx, edx
0x180036900  mov     rax, [rcx]
0x180036903  mov     [rsp+180h+pListOfAuditEntries], r13
0x180036908  mov     qword ptr [rsp+180h+cCountOfAuditEntries], r13
0x18003690d  mov     rax, [rax+48h]
0x180036911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036916  mov     ebx, eax
0x180036918  test    eax, eax
0x18003691a  js      loc_180036D35
0x180036920  mov     eax, [rbp+80h+arg_18]
0x180036926  mov     r15d, r13d
0x180036929  mov     edi, r13d
0x18003692c  test    eax, eax
0x18003692e  jz      loc_180036AFE
0x180036934  mov     ecx, eax
0x180036936  mov     [rbp+80h+var_F0], r13
0x18003693a  lea     eax, [rsi+2Fh]
0x18003693d  mov     [rbp+80h+pv], r13
0x180036941  mul     rcx
0x180036944  lea     rcx, [r13-1]
0x180036948  mov     [rsp+180h+Src], r13
0x18003694d  mov     [rbp+80h+pSid], r13
0x180036951  cmovb   rax, rcx
0x180036955  mov     [rsp+180h+var_118], r13d
0x18003695a  mov     rcx, rax; cb
0x18003695d  mov     [rsp+180h+var_108], r13d
0x180036962  mov     dword ptr [rbp+80h+cb], r13d
0x180036969  call    cs:__imp_CoTaskMemAlloc
0x18003696f  mov     rdi, rax
0x180036972  test    rax, rax
0x180036975  jnz     short loc_180036981
0x180036977  mov     ebx, 8007000Eh
0x18003697c  jmp     loc_180036D35
0x180036981  mov     rcx, [rsp+180h+var_130]
0x180036986  lea     rdx, [rbp+80h+var_F0]
0x18003698a  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rdx
0x18003698f  lea     r9, [rsp+180h+var_108]
0x180036994  lea     r8, [rsp+180h+var_118]
0x180036999  mov     edx, 2
0x18003699e  mov     rax, [rcx]
0x1800369a1  mov     rax, [rax+40h]
0x1800369a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369aa  mov     ebx, eax
0x1800369ac  test    eax, eax
0x1800369ae  js      loc_180036D04
0x1800369b4  mov     rcx, [rsp+180h+var_130]
0x1800369b9  lea     rdx, [rsp+180h+Src]
0x1800369be  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rdx
0x1800369c3  lea     r9, [rbp+80h+cb]
0x1800369ca  lea     r8, [rsp+180h+var_118]
0x1800369cf  mov     edx, 3
0x1800369d4  mov     rax, [rcx]
0x1800369d7  mov     rax, [rax+40h]
0x1800369db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369e0  mov     ebx, eax
0x1800369e2  test    eax, eax
0x1800369e4  js      loc_180036D04
0x1800369ea  mov     rax, [r14]
0x1800369ed  lea     r8, [rbp+80h+pv]
0x1800369f1  mov     rdx, [rbp+80h+var_F0]
0x1800369f5  xor     r9d, r9d
0x1800369f8  mov     rcx, r14
0x1800369fb  mov     rax, [rax+58h]
0x1800369ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a04  mov     ebx, eax
0x180036a06  test    eax, eax
0x180036a08  js      loc_180036D04
0x180036a0e  mov     r9, [rsp+180h+Src]; void *
0x180036a13  lea     rax, [rbp+80h+pSid]
0x180036a17  mov     r8, [rbp+80h+pv]; unsigned __int16 *
0x180036a1b  mov     rdx, [rsp+180h+var_130]; struct ISimpleTableWrite *
0x180036a20  mov     [rsp+180h+pOldSD], rax; void **
0x180036a25  lea     rax, [rbp+80h+pAcl]
0x180036a2c  mov     [rsp+180h+pListOfAuditEntries], rax; int *
0x180036a31  mov     eax, dword ptr [rbp+80h+cb]
0x180036a37  mov     [rsp+180h+cCountOfAuditEntries], eax; unsigned int
0x180036a3b  call    ?VerifyUserNameAndSid@CSecurityAdmin2@@QEAAHPEAUISimpleTableWrite@@PEAGPEAXKPEAHPEAPEAX@Z; CSecurityAdmin2::VerifyUserNameAndSid(ISimpleTableWrite *,ushort *,void *,ulong,int *,void * *)
0x180036a40  test    eax, eax
0x180036a42  jz      short loc_180036ABE
0x180036a44  mov     rbx, [rbp+80h+pSid]
0x180036a48  test    rbx, rbx
0x180036a4b  jnz     short loc_180036A88
0x180036a4d  cmp     [rsp+180h+Src], r13
0x180036a52  jz      loc_180036BDF
0x180036a58  mov     ecx, dword ptr [rbp+80h+cb]; cb
0x180036a5e  call    cs:__imp_CoTaskMemAlloc
0x180036a64  mov     [rbp+80h+pSid], rax
0x180036a68  mov     rbx, rax
0x180036a6b  test    rax, rax
0x180036a6e  jz      loc_180036BDF
0x180036a74  mov     r8d, dword ptr [rbp+80h+cb]; Size
0x180036a7b  mov     rcx, rax; void *
0x180036a7e  mov     rdx, [rsp+180h+Src]; Src
0x180036a83  call    memcpy_0
0x180036a88  mov     eax, r15d
0x180036a8b  mov     rdx, rbx; pSid
0x180036a8e  lea     rcx, [rax+rax*2]
0x180036a92  shl     rcx, 4
0x180036a96  mov     [rcx+rdi], esi
0x180036a99  mov     [rcx+rdi+4], esi
0x180036a9d  mov     dword ptr [rcx+rdi+8], 3
0x180036aa5  add     rcx, 10h
0x180036aa9  add     rcx, rdi; pTrustee
0x180036aac  call    cs:__imp_BuildTrusteeWithSidW
0x180036ab2  mov     r12d, dword ptr [rbp+80h+pAcl.AclRevision]
0x180036ab9  add     r15d, esi
0x180036abc  jmp     short loc_180036ADB
0x180036abe  mov     rcx, [rsp+180h+var_130]
0x180036ac3  mov     rax, [rcx]
0x180036ac6  mov     rax, [rax+88h]
0x180036acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ad2  mov     r12d, esi
0x180036ad5  mov     dword ptr [rbp+80h+pAcl.AclRevision], esi
0x180036adb  mov     rcx, [rbp+80h+pv]; pv
0x180036adf  call    cs:__imp_CoTaskMemFree
0x180036ae5  mov     rcx, [rsp+180h+var_130]
0x180036aea  mov     rax, [rcx]
0x180036aed  mov     rax, [rax+28h]
0x180036af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036af6  test    eax, eax
0x180036af8  jns     loc_180036981
0x180036afe  lea     rdx, pName; "CURRENT_USER"
0x180036b05  lea     rcx, [rbp+80h+pTrustee]; pTrustee
0x180036b09  call    cs:__imp_BuildTrusteeWithNameW
0x180036b0f  lea     rdx, pName; "CURRENT_USER"
0x180036b16  lea     rcx, [rbp+80h+pGroup]; pTrustee
0x180036b1a  call    cs:__imp_BuildTrusteeWithNameW
0x180036b20  lea     rax, [rsp+180h+hMem]
0x180036b25  mov     [rbp+80h+pGroup.TrusteeType], 2
0x180036b2c  mov     [rsp+180h+pNewSD], rax; pNewSD
0x180036b31  lea     rdx, [rbp+80h+pGroup]; pGroup
0x180036b35  lea     rax, [rbp+80h+arg_0]
0x180036b3c  mov     r9, rdi; pListOfAccessEntries
0x180036b3f  mov     [rsp+180h+pSizeNewSD], rax; pSizeNewSD
0x180036b44  lea     rcx, [rbp+80h+pTrustee]; pOwner
0x180036b48  mov     [rsp+180h+pOldSD], r13; unsigned int
0x180036b4d  mov     r8d, r15d; cCountOfAccessEntries
0x180036b50  mov     [rsp+180h+pListOfAuditEntries], r13; pListOfAuditEntries
0x180036b55  mov     [rsp+180h+cCountOfAuditEntries], r13d; cCountOfAuditEntries
0x180036b5a  call    cs:__imp_BuildSecurityDescriptorW
0x180036b60  mov     esi, eax
0x180036b62  test    r12d, r12d
0x180036b65  jz      short loc_180036B82
0x180036b67  mov     rcx, [rsp+180h+var_130]
0x180036b6c  mov     rdx, [rcx]
0x180036b6f  mov     rax, [rdx+60h]
0x180036b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b78  mov     ebx, eax
0x180036b7a  test    eax, eax
0x180036b7c  js      loc_180036CFF
0x180036b82  cmp     [rbp+80h+arg_18], r13d
0x180036b89  jnz     loc_180036D9E
0x180036b8f  test    esi, esi
0x180036b91  jnz     loc_180036DA6
0x180036b97  lea     edx, [rsi+8]; nAclLength
0x180036b9a  mov     qword ptr [rbp+80h+pAcl.AclRevision], r13
0x180036ba1  lea     r8d, [rsi+4]; dwAclRevision
0x180036ba5  lea     rcx, [rbp+80h+pAcl]; pAcl
0x180036bac  call    cs:__imp_InitializeAcl
0x180036bb2  mov     eax, [rbp+80h+arg_0]
0x180036bb8  lea     edx, [rax+8]; uBytes
0x180036bbb  cmp     edx, eax
0x180036bbd  jb      loc_180036D94
0x180036bc3  mov     rcx, [rsp+180h+hMem]; Src
0x180036bc8  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x180036bcd  mov     rdx, rax
0x180036bd0  test    rax, rax
0x180036bd3  jnz     short loc_180036BF0
0x180036bd5  mov     ebx, 8007000Eh
0x180036bda  jmp     loc_180036CFF
0x180036bdf  mov     r12d, dword ptr [rbp+80h+pAcl.AclRevision]
0x180036be6  mov     ebx, 8000FFFFh
0x180036beb  jmp     loc_180036D04
0x180036bf0  mov     ecx, [rbp+80h+arg_0]
0x180036bf6  mov     rax, qword ptr [rbp+80h+pAcl.AclRevision]
0x180036bfd  mov     [rsp+180h+hMem], rdx
0x180036c02  mov     [rcx+rdx], rax
0x180036c06  mov     ecx, [rbp+80h+arg_0]; this
0x180036c0c  mov     rax, [rsp+180h+hMem]
0x180036c11  mov     [rax+10h], ecx
0x180036c14  add     [rbp+80h+arg_0], 8
0x180036c1b  mov     rdx, [r14+18h]; struct ISimpleTableDispenser *
0x180036c1f  lea     rax, [rsp+180h+var_128]
0x180036c24  mov     [rsp+180h+pNewSD], rax; void **
0x180036c29  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180036c30  mov     dword ptr [rsp+180h+pSizeNewSD], 20000h; unsigned int
0x180036c38  lea     rax, [rbp+80h+var_B8]
0x180036c3c  mov     [rsp+180h+pListOfAuditEntries], 2; void *
0x180036c45  mov     qword ptr [rsp+180h+cCountOfAuditEntries], rax; void *
0x180036c4a  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180036c4f  mov     ebx, eax
0x180036c51  test    eax, eax
0x180036c53  js      loc_180036CFF
0x180036c59  mov     rcx, [rsp+180h+var_128]
0x180036c5e  mov     rax, [rcx]
0x180036c61  mov     rax, [rax+18h]
0x180036c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c6a  mov     ebx, eax
0x180036c6c  test    eax, eax
0x180036c6e  js      loc_180036CFF
0x180036c74  mov     rcx, [rsp+180h+var_128]
0x180036c79  xor     edx, edx
0x180036c7b  mov     rax, [rcx]
0x180036c7e  mov     rax, [rax+30h]
0x180036c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c87  mov     ebx, eax
0x180036c89  test    eax, eax
0x180036c8b  js      short loc_180036CFF
0x180036c8d  mov     rcx, [rsp+180h+var_128]
0x180036c92  mov     rax, [rcx]
0x180036c95  mov     rax, [rax+80h]
0x180036c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ca1  mov     ebx, eax
0x180036ca3  test    eax, eax
0x180036ca5  js      short loc_180036CFF
0x180036ca7  mov     rcx, [rsp+180h+var_128]
0x180036cac  mov     edx, 2
  ... truncated ...
```
