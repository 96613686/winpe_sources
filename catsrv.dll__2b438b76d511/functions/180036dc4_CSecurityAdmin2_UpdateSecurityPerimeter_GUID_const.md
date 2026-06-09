# CSecurityAdmin2::UpdateSecurityPerimeter(_GUID const &)

- ea: `0x180036dc4`
- end: `0x180037338`
- name: `?UpdateSecurityPerimeter@CSecurityAdmin2@@QEAAJAEBU_GUID@@@Z`
- size: `1396`
- prototype: `__int64 __fastcall(CSecurityAdmin2 *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180033f20`
- `0x1800360b0`

## callees

- `0x180033d68`
- `0x180033eb4`
- `0x180036dc4`
- `0x18003885c`
- `0x18005550e`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371ee`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800370f7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003720f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800370f7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003720f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037085`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037085`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180037021`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180037021`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036fde`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180036fde`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800370a1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800370a1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800370c8`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800370c8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800370e4`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800370e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800372d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800372d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037191`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800370ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800370ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036eca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180036eca`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x18003715d`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x18003715d`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180037111`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180037122`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180037111`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180037122`

## pseudocode

```c
__int64 __fastcall CSecurityAdmin2::UpdateSecurityPerimeter(CSecurityAdmin2 *this, const struct _GUID *a2)
{
  struct ISimpleTableDispenser *v2; // rdx
  struct _ACL *v3; // rdi
  int Table; // ebx
  CSecurityAdmin2 *v5; // rcx
  const struct _GUID *v6; // r8
  DWORD v7; // esi
  int v8; // r14d
  int AclSize; // eax
  struct _ACL *v10; // rax
  CSecurityAdmin2 *v11; // rcx
  unsigned __int16 *v12; // rsi
  unsigned int v13; // r8d
  size_t v14; // rbx
  SIZE_T v15; // rdx
  char *v16; // rax
  signed int v17; // eax
  signed int LastError; // eax
  unsigned int nSubAuthority4; // [rsp+30h] [rbp-D0h]
  unsigned int nSubAuthority4a; // [rsp+30h] [rbp-D0h]
  ULONG pSizeNewSD; // [rsp+60h] [rbp-A0h] BYREF
  void *v23; // [rsp+68h] [rbp-98h] BYREF
  PSID pSid; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_DESCRIPTOR pNewSD; // [rsp+78h] [rbp-88h] BYREF
  void *v26; // [rsp+80h] [rbp-80h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp-78h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISimpleTableDispenser *ppv; // [rsp+90h] [rbp-70h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+98h] [rbp-68h] BYREF
  PACL pDacl; // [rsp+A0h] [rbp-60h] BYREF
  void *Src; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+C4h] [rbp-3Ch]
  _QWORD v36[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v37; // [rsp+D8h] [rbp-28h]
  int v38; // [rsp+DCh] [rbp-24h]
  struct _TRUSTEE_W pGroup; // [rsp+E0h] [rbp-20h] BYREF
  struct _TRUSTEE_W pTrustee; // [rsp+100h] [rbp+0h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+120h] [rbp+20h] BYREF

  v33[0] = a2;
  v36[0] = a2;
  v2 = (struct ISimpleTableDispenser *)*((_QWORD *)this + 2);
  v33[1] = 0;
  v36[1] = 0;
  v35 = 16;
  v38 = 16;
  v34 = 72;
  v3 = 0;
  v37 = 72;
  ppv = 0;
  v26 = 0;
  v23 = 0;
  pDacl = 0;
  pSizeNewSD = 0;
  pSecurityDescriptor = 0;
  pNewSD = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  memset(&pGroup, 0, sizeof(pGroup));
  Table = CSecurityAdmin2::GetTable(
            this,
            v2,
            (const struct _GUID *)0x48,
            &tidCOMSERVICES_ROLESDCACHE,
            v33,
            (void *)1,
            nSubAuthority4,
            0x20001u,
            &v26);
  if ( Table < 0 )
    goto LABEL_44;
  Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v26 + 24LL))(v26);
  if ( Table < 0 )
    goto LABEL_44;
  Table = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Table < 0 )
    goto LABEL_44;
  Table = CSecurityAdmin2::GetTable(v5, ppv, v6, &TID_APPLICATION, v36, (void *)1, nSubAuthority4a, 0x20000u, &v23);
  (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( Table < 0 )
    goto LABEL_44;
  Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 24LL))(v23);
  if ( Table < 0 )
    goto LABEL_44;
  v7 = 8;
  Table = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v23 + 48LL))(v23, 0);
  if ( Table < 0 )
    goto LABEL_44;
  while ( 2 )
  {
    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v26 + 32LL))(v26);
    if ( Table < 0 )
      goto LABEL_44;
    v8 = 0;
    while ( (*(int (__fastcall **)(void *))(*(_QWORD *)v26 + 40LL))(v26) >= 0 )
    {
      Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, _QWORD, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v26 + 64LL))(
                v26,
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
        if ( v3 )
        {
          if ( !AddAce(v3, 2u, 0xFFFFFFFF, &pDacl[1], AclSize - 8) )
            goto LABEL_32;
        }
        else
        {
          v7 += AclSize - 8;
        }
      }
      ++v8;
    }
    if ( !v3 )
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
      v7 += GetLengthSid(pSid) + 8;
      v10 = (struct _ACL *)CoTaskMemAlloc(v7);
      v3 = v10;
      if ( v10 )
      {
        if ( InitializeAcl(v10, v7, 2u) && AddAccessAllowedAce(v3, 2u, 1u, pSid) )
        {
          FreeSid(pSid);
          if ( v8 )
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
    v17 = GetLastError();
    Table = v17;
    if ( v17 > 0 )
      Table = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_44;
  }
  Src = 0;
  Table = CSecurityAdmin2::OptimizeAcl(v11, v3, (struct _ACL **)&Src);
  if ( Table >= 0 )
  {
    v12 = (unsigned __int16 *)Src;
    if ( Src )
    {
      CoTaskMemFree(v3);
      v3 = (struct _ACL *)v12;
      v14 = v12[1];
      v15 = (unsigned int)v14 + pSizeNewSD;
      if ( (unsigned int)v15 < pSizeNewSD )
      {
        Table = -2147024362;
      }
      else
      {
        v16 = (char *)SmartLocalReAlloc(pNewSD, v15, v13);
        if ( v16 )
        {
          pNewSD = v16;
          memcpy_0(&v16[pSizeNewSD], v12, v14);
          *((_DWORD *)pNewSD + 4) = pSizeNewSD;
          *((_WORD *)pNewSD + 1) &= ~0x10u;
          pSizeNewSD += v14;
          Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 128LL))(v23);
          if ( Table >= 0 )
          {
            Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v23 + 160LL))(
                      v23,
                      23,
                      pSizeNewSD,
                      pNewSD);
            if ( Table >= 0 )
            {
              Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 144LL))(v23);
              if ( Table >= 0 )
                Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v23 + 96LL))(v23);
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
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v26 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v23 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  return (unsigned int)Table;
}

```

## disassembly

```asm
0x180036dc4  mov     [rsp-8+arg_10], rbx
0x180036dc9  push    rbp
0x180036dca  push    rsi
0x180036dcb  push    rdi
0x180036dcc  push    r12
0x180036dce  push    r13
0x180036dd0  push    r14
0x180036dd2  push    r15
0x180036dd4  lea     rbp, [rsp-30h]
0x180036dd9  sub     rsp, 130h
0x180036de0  mov     rax, cs:__security_cookie
0x180036de7  xor     rax, rsp
0x180036dea  mov     [rbp+60h+var_38], rax
0x180036dee  xor     r15d, r15d
0x180036df1  mov     [rbp+60h+var_B0], rdx
0x180036df5  xorps   xmm0, xmm0
0x180036df8  mov     [rbp+60h+var_98], rdx
0x180036dfc  mov     rdx, [rcx+10h]; struct ISimpleTableDispenser *
0x180036e00  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180036e07  xorps   xmm1, xmm1
0x180036e0a  mov     [rbp+60h+var_A8], r15
0x180036e0e  lea     eax, [r15+10h]
0x180036e12  mov     [rbp+60h+var_90], r15
0x180036e16  mov     [rbp+60h+var_9C], eax
0x180036e19  lea     r8d, [r15+48h]; struct _GUID *
0x180036e1d  mov     [rbp+60h+var_84], eax
0x180036e20  lea     r12d, [r15+1]
0x180036e24  lea     rax, [rbp+60h+var_E0]
0x180036e28  mov     [rbp+60h+var_A0], r8d
0x180036e2c  mov     qword ptr [rsp+160h+nSubAuthority6], rax; void **
0x180036e31  mov     edi, r15d
0x180036e34  mov     [rsp+160h+nSubAuthority5], 20001h; unsigned int
0x180036e3c  lea     rax, [rbp+60h+var_B0]
0x180036e40  mov     qword ptr [rsp+160h+nSubAuthority3], r12; void *
0x180036e45  mov     [rsp+160h+ppv], rax; void *
0x180036e4a  mov     [rbp+60h+var_88], r8d
0x180036e4e  mov     [rbp+60h+var_D0], r15
0x180036e52  mov     [rbp+60h+var_E0], r15
0x180036e56  mov     [rsp+160h+var_F8], r15
0x180036e5b  mov     [rbp+60h+pDacl], r15
0x180036e5f  mov     [rsp+160h+pSizeNewSD], r15d
0x180036e64  mov     [rbp+60h+pSecurityDescriptor], r15
0x180036e68  mov     [rsp+160h+pNewSD], r15
0x180036e6d  mov     [rbp+60h+bDaclPresent], r15d
0x180036e71  mov     [rbp+60h+bDaclDefaulted], r15d
0x180036e75  movups  xmmword ptr [rbp+60h+pTrustee.pMultipleTrustee], xmm0
0x180036e79  movups  xmmword ptr [rbp+60h+pTrustee.TrusteeType], xmm0
0x180036e7d  movups  xmmword ptr [rbp+60h+pGroup.pMultipleTrustee], xmm1
0x180036e81  movups  xmmword ptr [rbp+60h+pGroup.TrusteeType], xmm1
0x180036e85  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180036e8a  mov     ebx, eax
0x180036e8c  test    eax, eax
0x180036e8e  js      loc_1800372C6
0x180036e94  mov     rcx, [rbp+60h+var_E0]
0x180036e98  mov     rax, [rcx]
0x180036e9b  mov     rax, [rax+18h]
0x180036e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ea4  mov     ebx, eax
0x180036ea6  test    eax, eax
0x180036ea8  js      loc_1800372C6
0x180036eae  lea     rax, [rbp+60h+var_D0]
0x180036eb2  mov     r8d, r12d; dwClsContext
0x180036eb5  lea     r9, IID_ISimpleTableDispenser; riid
0x180036ebc  mov     [rsp+160h+ppv], rax; ppv
0x180036ec1  xor     edx, edx; pUnkOuter
0x180036ec3  lea     rcx, CLSID_STDispenser; rclsid
0x180036eca  call    cs:__imp_CoCreateInstance
0x180036ed0  mov     ebx, eax
0x180036ed2  test    eax, eax
0x180036ed4  js      loc_1800372C6
0x180036eda  mov     rdx, [rbp+60h+var_D0]; struct ISimpleTableDispenser *
0x180036ede  lea     rax, [rsp+160h+var_F8]
0x180036ee3  mov     qword ptr [rsp+160h+nSubAuthority6], rax; void **
0x180036ee8  lea     r9, TID_APPLICATION; struct _GUID *
0x180036eef  mov     [rsp+160h+nSubAuthority5], 20000h; unsigned int
0x180036ef7  lea     rax, [rbp+60h+var_98]
0x180036efb  mov     qword ptr [rsp+160h+nSubAuthority3], r12; void *
0x180036f00  mov     [rsp+160h+ppv], rax; void *
0x180036f05  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180036f0a  mov     rcx, [rbp+60h+var_D0]
0x180036f0e  mov     ebx, eax
0x180036f10  mov     rax, [rcx]
0x180036f13  mov     rax, [rax+10h]
0x180036f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f1c  test    ebx, ebx
0x180036f1e  js      loc_1800372C6
0x180036f24  mov     rcx, [rsp+160h+var_F8]
0x180036f29  mov     rax, [rcx]
0x180036f2c  mov     rax, [rax+18h]
0x180036f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f35  mov     ebx, eax
0x180036f37  test    eax, eax
0x180036f39  js      loc_1800372C6
0x180036f3f  mov     rcx, [rsp+160h+var_F8]
0x180036f44  lea     esi, [r15+8]
0x180036f48  xor     edx, edx
0x180036f4a  mov     rax, [rcx]
0x180036f4d  mov     rax, [rax+30h]
0x180036f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f56  mov     ebx, eax
0x180036f58  test    eax, eax
0x180036f5a  js      loc_1800372C6
0x180036f60  lea     r13d, [r15+2]
0x180036f64  mov     rcx, [rbp+60h+var_E0]
0x180036f68  mov     rax, [rcx]
0x180036f6b  mov     rax, [rax+20h]
0x180036f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f74  mov     ebx, eax
0x180036f76  test    eax, eax
0x180036f78  js      loc_1800372C6
0x180036f7e  mov     r14d, r15d
0x180036f81  mov     rcx, [rbp+60h+var_E0]
0x180036f85  mov     rax, [rcx]
0x180036f88  mov     rax, [rax+28h]
0x180036f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f91  test    eax, eax
0x180036f93  js      loc_180037037
0x180036f99  mov     rcx, [rbp+60h+var_E0]
0x180036f9d  lea     rdx, [rbp+60h+pSecurityDescriptor]
0x180036fa1  mov     [rsp+160h+ppv], rdx
0x180036fa6  xor     r9d, r9d
0x180036fa9  xor     r8d, r8d
0x180036fac  mov     edx, r13d
0x180036faf  mov     rax, [rcx]
0x180036fb2  mov     rax, [rax+40h]
0x180036fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fbb  mov     ebx, eax
0x180036fbd  test    eax, eax
0x180036fbf  js      loc_1800372C6
0x180036fc5  mov     rcx, [rbp+60h+pSecurityDescriptor]; pSecurityDescriptor
0x180036fc9  test    rcx, rcx
0x180036fcc  jz      loc_1800371E4
0x180036fd2  lea     r9, [rbp+60h+bDaclDefaulted]; lpbDaclDefaulted
0x180036fd6  lea     r8, [rbp+60h+pDacl]; pDacl
0x180036fda  lea     rdx, [rbp+60h+bDaclPresent]; lpbDaclPresent
0x180036fde  call    cs:__imp_GetSecurityDescriptorDacl
0x180036fe4  test    eax, eax
0x180036fe6  jz      loc_1800371C6
0x180036fec  cmp     [rbp+60h+bDaclPresent], r15d
0x180036ff0  jz      short loc_18003702F
0x180036ff2  mov     r9, [rbp+60h+pDacl]
0x180036ff6  test    r9, r9
0x180036ff9  jz      short loc_18003702F
0x180036ffb  movzx   eax, word ptr [r9+2]
0x180037000  test    rdi, rdi
0x180037003  jnz     short loc_18003700C
0x180037005  add     eax, 0FFFFFFF8h
0x180037008  add     esi, eax
0x18003700a  jmp     short loc_18003702F
0x18003700c  sub     eax, 8
0x18003700f  add     r9, 8; pAceList
0x180037013  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180037017  mov     dword ptr [rsp+160h+ppv], eax; nAceListLength
0x18003701b  mov     edx, r13d; dwAceRevision
0x18003701e  mov     rcx, rdi; pAcl
0x180037021  call    cs:__imp_AddAce
0x180037027  test    eax, eax
0x180037029  jz      loc_1800371C6
0x18003702f  add     r14d, r12d
0x180037032  jmp     loc_180036F81
0x180037037  test    rdi, rdi
0x18003703a  jnz     loc_180037106
0x180037040  lea     rax, [rsp+160h+var_F0]
0x180037045  mov     dword ptr [rbp+60h+pIdentifierAuthority.Value], r15d
0x180037049  mov     [rsp+160h+pSid], rax; pSid
0x18003704e  lea     r8d, [rdi+12h]; nSubAuthority0
0x180037052  mov     [rsp+160h+nSubAuthority7], r15d; nSubAuthority7
0x180037057  lea     rcx, [rbp+60h+pIdentifierAuthority]; pIdentifierAuthority
0x18003705b  mov     [rsp+160h+nSubAuthority6], r15d; nSubAuthority6
0x180037060  xor     r9d, r9d; nSubAuthority1
0x180037063  mov     [rsp+160h+nSubAuthority5], r15d; nSubAuthority5
0x180037068  mov     dl, r12b; nSubAuthorityCount
0x18003706b  mov     [rsp+160h+nSubAuthority4], r15d; nSubAuthority4
0x180037070  mov     [rsp+160h+nSubAuthority3], r15d; nSubAuthority3
0x180037075  mov     dword ptr [rsp+160h+ppv], r15d; nSubAuthority2
0x18003707a  mov     word ptr [rbp+60h+pIdentifierAuthority.Value+4], 500h
0x180037080  mov     [rsp+160h+var_F0], r15
0x180037085  call    cs:__imp_AllocateAndInitializeSid
0x18003708b  test    eax, eax
0x18003708d  jz      loc_1800371C6
0x180037093  mov     rcx, [rsp+160h+var_F0]; pSid
0x180037098  test    rcx, rcx
0x18003709b  jz      loc_1800371E4
0x1800370a1  call    cs:__imp_GetLengthSid
0x1800370a7  add     eax, 8
0x1800370aa  add     esi, eax
0x1800370ac  mov     ecx, esi; cb
0x1800370ae  call    cs:__imp_CoTaskMemAlloc
0x1800370b4  mov     rdi, rax
0x1800370b7  test    rax, rax
0x1800370ba  jz      loc_180037205
0x1800370c0  mov     r8d, r13d; dwAclRevision
0x1800370c3  mov     edx, esi; nAclLength
0x1800370c5  mov     rcx, rax; pAcl
0x1800370c8  call    cs:__imp_InitializeAcl
0x1800370ce  test    eax, eax
0x1800370d0  jz      loc_1800371EE
0x1800370d6  mov     r9, [rsp+160h+var_F0]; pSid
0x1800370db  mov     r8d, r12d; AccessMask
0x1800370de  mov     edx, r13d; dwAceRevision
0x1800370e1  mov     rcx, rdi; pAcl
0x1800370e4  call    cs:__imp_AddAccessAllowedAce
0x1800370ea  test    eax, eax
0x1800370ec  jz      loc_1800371EE
0x1800370f2  mov     rcx, [rsp+160h+var_F0]; pSid
0x1800370f7  call    cs:__imp_FreeSid
0x1800370fd  test    r14d, r14d
0x180037100  jnz     loc_180036F64
0x180037106  lea     rdx, pName; "CURRENT_USER"
0x18003710d  lea     rcx, [rbp+60h+pTrustee]; pTrustee
0x180037111  call    cs:__imp_BuildTrusteeWithNameW
0x180037117  lea     rdx, pName; "CURRENT_USER"
0x18003711e  lea     rcx, [rbp+60h+pGroup]; pTrustee
0x180037122  call    cs:__imp_BuildTrusteeWithNameW
0x180037128  lea     rax, [rsp+160h+pNewSD]
0x18003712d  mov     [rbp+60h+pGroup.TrusteeType], r13d
0x180037131  mov     qword ptr [rsp+160h+nSubAuthority6], rax; pNewSD
0x180037136  lea     rdx, [rbp+60h+pGroup]; pGroup
0x18003713a  lea     rax, [rsp+160h+pSizeNewSD]
0x18003713f  xor     r9d, r9d; pListOfAccessEntries
0x180037142  mov     qword ptr [rsp+160h+nSubAuthority5], rax; pSizeNewSD
0x180037147  lea     rcx, [rbp+60h+pTrustee]; pOwner
0x18003714b  mov     qword ptr [rsp+160h+nSubAuthority4], r15; pOldSD
0x180037150  xor     r8d, r8d; cCountOfAccessEntries
0x180037153  mov     qword ptr [rsp+160h+nSubAuthority3], r15; pListOfAuditEntries
0x180037158  mov     dword ptr [rsp+160h+ppv], r15d; cCountOfAuditEntries
0x18003715d  call    cs:__imp_BuildSecurityDescriptorW
0x180037163  test    eax, eax
0x180037165  jnz     short loc_1800371C6
0x180037167  lea     r8, [rbp+60h+Src]; struct _ACL **
0x18003716b  mov     [rbp+60h+Src], r15
0x18003716f  mov     rdx, rdi; struct _ACL *
0x180037172  call    ?OptimizeAcl@CSecurityAdmin2@@QEAAJPEAU_ACL@@PEAPEAU2@@Z; CSecurityAdmin2::OptimizeAcl(_ACL *,_ACL * *)
0x180037177  mov     ebx, eax
0x180037179  test    eax, eax
0x18003717b  js      loc_1800372C6
0x180037181  mov     rsi, [rbp+60h+Src]
0x180037185  test    rsi, rsi
0x180037188  jz      loc_1800372C6
0x18003718e  mov     rcx, rdi; pv
0x180037191  call    cs:__imp_CoTaskMemFree
0x180037197  mov     eax, [rsp+160h+pSizeNewSD]
0x18003719b  mov     rdi, rsi
0x18003719e  movzx   ebx, word ptr [rsi+2]
0x1800371a2  lea     edx, [rbx+rax]; uBytes
0x1800371a5  cmp     edx, eax
0x1800371a7  jb      loc_1800372C1
0x1800371ad  mov     rcx, [rsp+160h+pNewSD]; Src
0x1800371b2  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x1800371b7  test    rax, rax
0x1800371ba  jnz     short loc_18003721A
0x1800371bc  mov     ebx, 8007000Eh
0x1800371c1  jmp     loc_1800372C6
0x1800371c6  call    cs:__imp_GetLastError
0x1800371cc  mov     ebx, eax
0x1800371ce  test    eax, eax
0x1800371d0  jle     loc_1800372C6
0x1800371d6  movzx   ebx, ax
0x1800371d9  or      ebx, 80070000h
0x1800371df  jmp     loc_1800372C6
0x1800371e4  mov     ebx, 8000FFFFh
0x1800371e9  jmp     loc_1800372C6
0x1800371ee  call    cs:__imp_GetLastError
0x1800371f4  mov     ebx, eax
0x1800371f6  test    eax, eax
0x1800371f8  jle     short loc_18003720A
0x1800371fa  movzx   ebx, ax
0x1800371fd  or      ebx, 80070000h
0x180037203  jmp     short loc_18003720A
0x180037205  mov     ebx, 8007000Eh
0x18003720a  mov     rcx, [rsp+160h+var_F0]; pSid
0x18003720f  call    cs:__imp_FreeSid
0x180037215  jmp     loc_1800372C6
0x18003721a  mov     ecx, [rsp+160h+pSizeNewSD]
0x18003721e  mov     r8, rbx; Size
0x180037221  add     rcx, rax; void *
0x180037224  mov     [rsp+160h+pNewSD], rax
0x180037229  mov     rdx, rsi; Src
0x18003722c  call    memcpy_0
0x180037231  mov     ecx, [rsp+160h+pSizeNewSD]
0x180037235  mov     rax, [rsp+160h+pNewSD]
0x18003723a  mov     [rax+10h], ecx
0x18003723d  mov     ecx, 0FFEFh
0x180037242  mov     rax, [rsp+160h+pNewSD]
0x180037247  and     [rax+2], cx
0x18003724b  mov     rcx, [rsp+160h+var_F8]
0x180037250  add     [rsp+160h+pSizeNewSD], ebx
0x180037254  mov     rax, [rcx]
0x180037257  mov     rax, [rax+80h]
0x18003725e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037263  mov     ebx, eax
0x180037265  test    eax, eax
0x180037267  js      short loc_1800372C6
0x180037269  mov     rcx, [rsp+160h+var_F8]
0x18003726e  mov     edx, 17h
0x180037273  mov     r9, [rsp+160h+pNewSD]
0x180037278  mov     r8d, [rsp+160h+pSizeNewSD]
0x18003727d  mov     rax, [rcx]
0x180037280  mov     rax, [rax+0A0h]
0x180037287  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
