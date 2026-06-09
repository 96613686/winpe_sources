# ValidateLdapResponse(IASTL::IASRequest &,ldapmsg *,int)

- ea: `0x18000d794`
- end: `0x18000dbb7`
- name: `?ValidateLdapResponse@@YAKAEAVIASRequest@IASTL@@PEAUldapmsg@@H@Z`
- size: `1059`
- prototype: `unsigned int __fastcall(struct IASTL::IASRequest *, LDAPMessage *res, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e538`

## callees

- `0x18000acf4`
- `0x18000b484`
- `0x18000b82c`
- `0x18000ba5c`
- `0x18000c28c`
- `0x18000d55c`
- `0x18000d59c`
- `0x18000d794`
- `0x18000df3c`
- `0x18000ea60`
- `0x180016938`
- `0x180025264`
- `0x180027e8c`
- `0x180029b00`
- `0x18002b4a0`
- `0x18002b560`
- `0x18002e010`

## import_xrefs

- `msvcrt!_wtoi64` at `0x18000d864`
- `msvcrt!_wtoi64` at `0x18000d8e7`
- `msvcrt!_wtoi64` at `0x18000d864`
- `msvcrt!_wtoi64` at `0x18000d8e7`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000d7d9`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000d7d9`
- `WLDAP32!__imp_ldap_count_values_len` at `0x18000d9c9`
- `WLDAP32!__imp_ldap_count_values_len` at `0x18000d9c9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000d853`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000d8d6`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000d853`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000d8d6`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d7ef`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d915`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d993`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d7ef`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d915`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x18000d993`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000d870`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000d8f3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000d870`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000d8f3`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x18000d7ca`
- `WLDAP32!__imp_ldap_conn_from_msg` at `0x18000d7ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dae2`

## string_xrefs

- `0x18000d986`: `tokenGroups`
- `0x18000d7e2`: `objectSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ValidateLdapResponse(struct IAttributesRaw **a1, LDAPMessage *res, int a3)
{
  LDAP *v6; // r14
  LDAPMessage *entry; // r15
  struct berval **values_lenW; // rbx
  BOOL v9; // edi
  int v10; // eax
  unsigned int v11; // edi
  bool v12; // r12
  const wchar_t **valuesW; // rax
  PWCHAR *v14; // rdi
  __int16 v15; // si
  const wchar_t **v16; // rax
  PWCHAR *v17; // rdi
  void *v18; // rsi
  struct berval **v19; // rax
  struct berval *v20; // rcx
  struct berval **v21; // r13
  ULONG v22; // eax
  __int64 v23; // r15
  unsigned __int64 v24; // r14
  LPVOID *p_pv; // rsi
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  void *v28; // rsp
  void *v29; // rsp
  _DWORD *v30; // rax
  unsigned int v31; // r9d
  __int64 v32; // r8
  __int64 v33; // rdx
  bool v34; // dl
  _DWORD *v35; // rbx
  __int64 v37; // [rsp+0h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+30h] [rbp+0h] BYREF
  struct berval **v39; // [rsp+38h] [rbp+8h] BYREF
  LPVOID v40; // [rsp+40h] [rbp+10h] BYREF
  union _LARGE_INTEGER v41; // [rsp+48h] [rbp+18h] BYREF
  __int128 v42; // [rsp+50h] [rbp+20h] BYREF
  struct IAttributesRaw **v43; // [rsp+60h] [rbp+30h]
  struct berval **v44; // [rsp+68h] [rbp+38h] BYREF

  v43 = a1;
  v6 = ldap_conn_from_msg(0, res);
  entry = ldap_first_entry(v6, res);
  values_lenW = ldap_get_values_lenW(v6, entry, (const PWSTR)L"objectSid");
  v44 = values_lenW;
  if ( values_lenW )
  {
    v9 = a3 != 0;
    if ( !IASPeekAttribute(a1[1], (unsigned int)(v9 + 8161), 6) )
    {
      v10 = IASStoreAccountSID(a1[1], v9 + 8161, (*values_lenW)->bv_val);
      if ( v10 < 0 )
      {
        v11 = (unsigned __int16)v10;
        goto LABEL_48;
      }
    }
  }
  v12 = 1;
  valuesW = (const wchar_t **)ldap_get_valuesW(v6, entry, (const PWSTR)L"userAccountControl");
  v14 = (PWCHAR *)valuesW;
  if ( valuesW )
  {
    v15 = _wtoi64(*valuesW);
    ldap_value_freeW(v14);
    v12 = (v15 & 0x200) != 0;
    if ( (v15 & 2) != 0 )
    {
      v11 = 1331;
      goto LABEL_48;
    }
    if ( (v15 & 0x10) != 0 )
    {
      v11 = 1909;
      goto LABEL_48;
    }
  }
  pv = 0;
  if ( !v12 && IASTL::IASAttribute::load((IASTL::IASAttribute *)&pv, a1[1], 0x1FB6u) )
    goto LABEL_42;
  v16 = (const wchar_t **)ldap_get_valuesW(v6, entry, (const PWSTR)L"accountExpires");
  v17 = (PWCHAR *)v16;
  if ( v16 )
  {
    v18 = (void *)_wtoi64(*v16);
    ldap_value_freeW(v17);
  }
  else
  {
    v18 = 0;
  }
  v40 = v18;
  v42 = 0;
  v19 = ldap_get_values_lenW(v6, entry, (const PWSTR)L"logonHours");
  v39 = v19;
  if ( v19 )
  {
    v20 = *v19;
    LOWORD(v42) = 8 * LOWORD((*v19)->bv_len);
    *((_QWORD *)&v42 + 1) = v20->bv_val;
  }
  v41.QuadPart = 0;
  v11 = IASCheckAccountRestrictions(&v40, &v42, &v41);
  if ( !(unsigned __int8)IASTL::IASAttribute::load(&pv, a1[1], 8119, 6) )
    InsertInternalTimeout((struct IASTL::IASRequest *)a1, &v41);
  if ( !v11 )
  {
    v21 = ldap_get_values_lenW(v6, entry, (const PWSTR)L"tokenGroups");
    XPBerValue::free((XPBerValue *)&v39);
    v39 = v21;
    *(_QWORD *)&v42 = 0;
    v41.LowPart = 0;
    if ( v21 && values_lenW )
    {
      v22 = ldap_count_values_len(v21);
      v23 = v22;
      if ( v22 > 0xFFFFFFF )
      {
        XPBerValue::free((XPBerValue *)&v39);
        if ( pv )
          IASAttributeRelease(pv);
        v11 = 534;
        goto LABEL_48;
      }
      v24 = 16LL * v22 + 8;
      p_pv = 0;
      v11 = 8;
      if ( v24 > g_ulMaxStackAllocSize
        || v24 + g_ulAdditionalProbeSize + 8 < v24
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_51;
      }
      v26 = 16 * v23 + 31;
      if ( v26 <= 16 * v23 + 16 )
        v26 = 0xFFFFFFFFFFFFFF0LL;
      v27 = v26 & 0xFFFFFFFFFFFFFFF0uLL;
      v28 = alloca(v27);
      v29 = alloca(v27);
      p_pv = &pv;
      if ( &v37 == (__int64 *)-48LL || (LODWORD(pv) = 1801679955, (p_pv = (LPVOID *)&v39) == 0) )
      {
LABEL_51:
        if ( 16 * v23 + 16 >= (unsigned __int64)(16 * v23 + 8) )
        {
          v30 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
          p_pv = (LPVOID *)v30;
          if ( v30 )
          {
            *v30 = 1885431112;
            p_pv = (LPVOID *)(v30 + 2);
          }
        }
      }
      if ( p_pv )
      {
        v40 = p_pv;
        *(_DWORD *)p_pv = v23;
        v31 = 0;
        if ( (_DWORD)v23 )
        {
          v32 = 0;
          do
          {
            v33 = 2 * v32;
            p_pv[v33 + 1] = v21[v32]->bv_val;
            LODWORD(p_pv[v33 + 2]) = 4;
            ++v31;
            ++v32;
          }
          while ( v31 < (unsigned int)v23 );
        }
        v11 = IASGetAliasMembership(
                (__int64)(*values_lenW)->bv_val,
                (__int64)p_pv,
                (__int64 (__fastcall *)(_QWORD))CoTaskMemAlloc,
                (__int64 *)&v42,
                (ULONG *)&v41);
        SafeAllocaScopeGuard::~SafeAllocaScopeGuard((SafeAllocaScopeGuard *)&v40);
        if ( !v11 )
        {
          IASTL::IASAttribute::IASAttribute((IASTL::IASAttribute *)&v40, v34);
          v35 = v40;
          *((_DWORD *)v40 + 2) = v12 + 8118;
          v35[4] = 6;
          v35[1] |= 0x30000u;
          *((_QWORD *)v35 + 4) = v42;
          v35[6] = v41.LowPart;
          IASTL::IASAttribute::store((IASTL::IASAttribute *)&v40, v43[1]);
          IASAttributeRelease(v35);
          XPBerValue::free((XPBerValue *)&v39);
LABEL_42:
          if ( pv )
            IASAttributeRelease(pv);
          v11 = 0;
          goto LABEL_48;
        }
      }
    }
    else
    {
      v11 = 5;
    }
  }
  XPBerValue::free((XPBerValue *)&v39);
  if ( pv )
    IASAttributeRelease(pv);
LABEL_48:
  XPBerValue::free((XPBerValue *)&v44);
  return v11;
}

```

## disassembly

```asm
0x18000d794  push    rbp
0x18000d796  push    rbx
0x18000d797  push    rsi
0x18000d798  push    rdi
0x18000d799  push    r12
0x18000d79b  push    r13
0x18000d79d  push    r14
0x18000d79f  push    r15
0x18000d7a1  sub     rsp, 88h
0x18000d7a8  lea     rbp, [rsp+30h]
0x18000d7ad  mov     rax, cs:__security_cookie
0x18000d7b4  xor     rax, rbp
0x18000d7b7  mov     [rbp+90h+var_50], rax
0x18000d7bb  mov     edi, r8d
0x18000d7be  mov     rbx, rdx
0x18000d7c1  mov     r13, rcx
0x18000d7c4  mov     [rbp+90h+var_60], rcx
0x18000d7c8  xor     ecx, ecx; PrimaryConn
0x18000d7ca  call    cs:__imp_ldap_conn_from_msg
0x18000d7d0  mov     r14, rax
0x18000d7d3  mov     rdx, rbx; res
0x18000d7d6  mov     rcx, rax; ld
0x18000d7d9  call    cs:__imp_ldap_first_entry
0x18000d7df  mov     r15, rax
0x18000d7e2  lea     r8, attr; "objectSid"
0x18000d7e9  mov     rdx, rax; Message
0x18000d7ec  mov     rcx, r14; ExternalHandle
0x18000d7ef  call    cs:__imp_ldap_get_values_lenW
0x18000d7f5  mov     rbx, rax
0x18000d7f8  mov     [rbp+90h+var_58], rax
0x18000d7fc  test    rax, rax
0x18000d7ff  jz      short loc_18000D843
0x18000d801  neg     edi
0x18000d803  sbb     edi, edi
0x18000d805  neg     edi
0x18000d807  mov     r8d, 6
0x18000d80d  lea     edx, [rdi+1FE1h]
0x18000d813  mov     rcx, [r13+8]
0x18000d817  call    ?IASPeekAttribute@@YAPEAU_IASATTRIBUTE@@PEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASPeekAttribute(IAttributesRaw *,ulong,IASTYPEENUM)
0x18000d81c  test    rax, rax
0x18000d81f  jnz     short loc_18000D843
0x18000d821  mov     r8, [rbx]
0x18000d824  mov     r8, [r8+8]; void *
0x18000d828  lea     edx, [rdi+1FE1h]; unsigned int
0x18000d82e  mov     rcx, [r13+8]; struct IAttributesRaw *
0x18000d832  call    ?IASStoreAccountSID@@YAJPEAUIAttributesRaw@@KPEAX@Z; IASStoreAccountSID(IAttributesRaw *,ulong,void *)
0x18000d837  test    eax, eax
0x18000d839  jns     short loc_18000D843
0x18000d83b  movzx   edi, ax
0x18000d83e  jmp     loc_18000DB8F
0x18000d843  mov     r12b, 1
0x18000d846  lea     r8, aUseraccountcon; "userAccountControl"
0x18000d84d  mov     rdx, r15; entry
0x18000d850  mov     rcx, r14; ld
0x18000d853  call    cs:__imp_ldap_get_valuesW
0x18000d859  mov     rdi, rax
0x18000d85c  test    rax, rax
0x18000d85f  jz      short loc_18000D8A1
0x18000d861  mov     rcx, [rax]; String
0x18000d864  call    cs:__imp__wtoi64
0x18000d86a  mov     rsi, rax
0x18000d86d  mov     rcx, rdi; vals
0x18000d870  call    cs:__imp_ldap_value_freeW
0x18000d876  mov     r12d, esi
0x18000d879  shr     r12d, 9
0x18000d87d  and     r12b, 1
0x18000d881  test    sil, 2
0x18000d885  jz      short loc_18000D891
0x18000d887  mov     edi, 533h
0x18000d88c  jmp     loc_18000DB8F
0x18000d891  test    sil, 10h
0x18000d895  jz      short loc_18000D8A1
0x18000d897  mov     edi, 775h
0x18000d89c  jmp     loc_18000DB8F
0x18000d8a1  mov     [rbp+90h+pv], 0
0x18000d8a9  test    r12b, r12b
0x18000d8ac  jnz     short loc_18000D8C9
0x18000d8ae  mov     r8d, 1FB6h; unsigned int
0x18000d8b4  mov     rdx, [r13+8]; struct IAttributesRaw *
0x18000d8b8  lea     rcx, [rbp+90h+pv]; this
0x18000d8bc  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@K@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong)
0x18000d8c1  test    al, al
0x18000d8c3  jnz     loc_18000DB5F
0x18000d8c9  lea     r8, aAccountexpires; "accountExpires"
0x18000d8d0  mov     rdx, r15; entry
0x18000d8d3  mov     rcx, r14; ld
0x18000d8d6  call    cs:__imp_ldap_get_valuesW
0x18000d8dc  mov     rdi, rax
0x18000d8df  test    rax, rax
0x18000d8e2  jz      short loc_18000D8FB
0x18000d8e4  mov     rcx, [rax]; String
0x18000d8e7  call    cs:__imp__wtoi64
0x18000d8ed  mov     rsi, rax
0x18000d8f0  mov     rcx, rdi; vals
0x18000d8f3  call    cs:__imp_ldap_value_freeW
0x18000d8f9  jmp     short loc_18000D8FD
0x18000d8fb  xor     esi, esi
0x18000d8fd  mov     [rbp+90h+var_80], rsi
0x18000d901  xorps   xmm0, xmm0
0x18000d904  movups  [rbp+90h+var_70], xmm0
0x18000d908  lea     r8, aLogonhours; "logonHours"
0x18000d90f  mov     rdx, r15; Message
0x18000d912  mov     rcx, r14; ExternalHandle
0x18000d915  call    cs:__imp_ldap_get_values_lenW
0x18000d91b  mov     [rbp+90h+var_88], rax
0x18000d91f  test    rax, rax
0x18000d922  jz      short loc_18000D93A
0x18000d924  mov     rcx, [rax]
0x18000d927  movzx   eax, word ptr [rcx]
0x18000d92a  shl     ax, 3
0x18000d92e  mov     word ptr [rbp+90h+var_70], ax
0x18000d932  mov     rax, [rcx+8]
0x18000d936  mov     qword ptr [rbp+90h+var_70+8], rax
0x18000d93a  mov     qword ptr [rbp+90h+var_78], 0
0x18000d942  lea     r8, [rbp+90h+var_78]
0x18000d946  lea     rdx, [rbp+90h+var_70]
0x18000d94a  lea     rcx, [rbp+90h+var_80]
0x18000d94e  call    IASCheckAccountRestrictions
0x18000d953  mov     edi, eax
0x18000d955  mov     r9d, 6
0x18000d95b  mov     r8d, 1FB7h
0x18000d961  mov     rdx, [r13+8]
0x18000d965  lea     rcx, [rbp+90h+pv]
0x18000d969  call    ?load@IASAttribute@IASTL@@QEAA_NPEAUIAttributesRaw@@KW4IASTYPEENUM@@@Z; IASTL::IASAttribute::load(IAttributesRaw *,ulong,IASTYPEENUM)
0x18000d96e  test    al, al
0x18000d970  jnz     short loc_18000D97E
0x18000d972  lea     rdx, [rbp+90h+var_78]; union _LARGE_INTEGER *
0x18000d976  mov     rcx, r13; struct IASTL::IASRequest *
0x18000d979  call    ?InsertInternalTimeout@@YAXAEAVIASRequest@IASTL@@AEBT_LARGE_INTEGER@@@Z; InsertInternalTimeout(IASTL::IASRequest &,_LARGE_INTEGER const &)
0x18000d97e  test    edi, edi
0x18000d980  jnz     loc_18000DB76
0x18000d986  lea     r8, aTokengroups; "tokenGroups"
0x18000d98d  mov     rdx, r15; Message
0x18000d990  mov     rcx, r14; ExternalHandle
0x18000d993  call    cs:__imp_ldap_get_values_lenW
0x18000d999  mov     r13, rax
0x18000d99c  lea     rcx, [rbp+90h+var_88]; this
0x18000d9a0  call    ?free@XPBerValue@@AEAAXXZ; XPBerValue::free(void)
0x18000d9a5  mov     [rbp+90h+var_88], r13
0x18000d9a9  mov     qword ptr [rbp+90h+var_70], 0
0x18000d9b1  mov     dword ptr [rbp+90h+var_78], edi
0x18000d9b4  test    r13, r13
0x18000d9b7  jz      loc_18000DB71
0x18000d9bd  test    rbx, rbx
0x18000d9c0  jz      loc_18000DB71
0x18000d9c6  mov     rcx, r13; vals
0x18000d9c9  call    cs:__imp_ldap_count_values_len
0x18000d9cf  mov     r15d, eax
0x18000d9d2  cmp     eax, 0FFFFFFFh
0x18000d9d7  jbe     short loc_18000D9FB
0x18000d9d9  lea     rcx, [rbp+90h+var_88]; this
0x18000d9dd  call    ?free@XPBerValue@@AEAAXXZ; XPBerValue::free(void)
0x18000d9e2  nop
0x18000d9e3  mov     rcx, [rbp+90h+pv]; pv
0x18000d9e7  test    rcx, rcx
0x18000d9ea  jz      short loc_18000D9F1
0x18000d9ec  call    IASAttributeRelease
0x18000d9f1  mov     edi, 216h
0x18000d9f6  jmp     loc_18000DB8F
0x18000d9fb  mov     r14, r15
0x18000d9fe  shl     r14, 4
0x18000da02  add     r14, 8
0x18000da06  xor     esi, esi
0x18000da08  lea     edi, [rsi+8]
0x18000da0b  cmp     r14, cs:g_ulMaxStackAllocSize
0x18000da12  ja      short loc_18000DA6A
0x18000da14  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000da1b  add     rcx, rdi
0x18000da1e  add     rcx, r14
0x18000da21  cmp     rcx, r14
0x18000da24  jb      short loc_18000DA6A
0x18000da26  call    VerifyStackAvailable
0x18000da2b  test    eax, eax
0x18000da2d  jz      short loc_18000DA6A
0x18000da2f  lea     rax, [r14+8]
0x18000da33  lea     rcx, [rax+0Fh]
0x18000da37  cmp     rcx, rax
0x18000da3a  ja      short loc_18000DA46
0x18000da3c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000da46  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000da4a  mov     rax, rcx
0x18000da4d  call    _alloca_probe
0x18000da52  sub     rsp, rcx
0x18000da55  lea     rsi, [rsp+0C0h+pv]
0x18000da5a  test    rsi, rsi
0x18000da5d  jz      short loc_18000DA6A
0x18000da5f  mov     dword ptr [rsi], 6B637453h
0x18000da65  add     rsi, rdi
0x18000da68  jnz     short loc_18000DA90
0x18000da6a  lea     rcx, [r14+8]
0x18000da6e  cmp     rcx, r14
0x18000da71  jb      short loc_18000DA90
0x18000da73  mov     rax, cs:g_pfnAllocate
0x18000da7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7f  mov     rsi, rax
0x18000da82  test    rax, rax
0x18000da85  jz      short loc_18000DA90
0x18000da87  mov     dword ptr [rax], 70616548h
0x18000da8d  add     rsi, rdi
0x18000da90  test    rsi, rsi
0x18000da93  jz      loc_18000DB76
0x18000da99  mov     [rbp+90h+var_80], rsi
0x18000da9d  mov     [rsi], r15d
0x18000daa0  xor     r9d, r9d
0x18000daa3  test    r15d, r15d
0x18000daa6  jz      short loc_18000DAD2
0x18000daa8  xor     r8d, r8d
0x18000daab  mov     rdx, r8
0x18000daae  add     rdx, rdx
0x18000dab1  mov     rax, [r13+r8*8+0]
0x18000dab6  mov     rcx, [rax+8]
0x18000daba  mov     [rsi+rdx*8+8], rcx
0x18000dabf  mov     dword ptr [rsi+rdx*8+10h], 4
0x18000dac7  inc     r9d
0x18000daca  inc     r8
0x18000dacd  cmp     r9d, r15d
0x18000dad0  jb      short loc_18000DAAB
0x18000dad2  mov     rcx, [rbx]
0x18000dad5  lea     rax, [rbp+90h+var_78]
0x18000dad9  mov     [rsp+0C0h+var_A0], rax
0x18000dade  lea     r9, [rbp+90h+var_70]
0x18000dae2  mov     r8, cs:__imp_CoTaskMemAlloc
0x18000dae9  mov     rdx, rsi
0x18000daec  mov     rcx, [rcx+8]
0x18000daf0  call    IASGetAliasMembership
0x18000daf5  mov     edi, eax
0x18000daf7  lea     rcx, [rbp+90h+var_80]; this
0x18000dafb  call    ??1SafeAllocaScopeGuard@@QEAA@XZ; SafeAllocaScopeGuard::~SafeAllocaScopeGuard(void)
0x18000db00  test    edi, edi
0x18000db02  jnz     short loc_18000DB76
0x18000db04  lea     rcx, [rbp+90h+var_80]; this
0x18000db08  call    ??0IASAttribute@IASTL@@QEAA@_N@Z; IASTL::IASAttribute::IASAttribute(bool)
0x18000db0d  nop
0x18000db0e  movzx   eax, r12b
0x18000db12  add     eax, 1FB6h
0x18000db17  mov     rbx, [rbp+90h+var_80]
0x18000db1b  mov     [rbx+8], eax
0x18000db1e  mov     dword ptr [rbx+10h], 6
0x18000db25  or      dword ptr [rbx+4], 30000h
0x18000db2c  mov     rax, qword ptr [rbp+90h+var_70]
0x18000db30  mov     [rbx+20h], rax
0x18000db34  mov     eax, dword ptr [rbp+90h+var_78]
0x18000db37  mov     [rbx+18h], eax
0x18000db3a  mov     rdx, [rbp+90h+var_60]
0x18000db3e  mov     rdx, [rdx+8]; struct IAttributesRaw *
0x18000db42  lea     rcx, [rbp+90h+var_80]; this
0x18000db46  call    ?store@IASAttribute@IASTL@@QEBAXPEAUIAttributesRaw@@@Z; IASTL::IASAttribute::store(IAttributesRaw *)
0x18000db4b  nop
0x18000db4c  mov     rcx, rbx; pv
0x18000db4f  call    IASAttributeRelease
0x18000db54  nop
0x18000db55  lea     rcx, [rbp+90h+var_88]; this
0x18000db59  call    ?free@XPBerValue@@AEAAXXZ; XPBerValue::free(void)
0x18000db5e  nop
0x18000db5f  mov     rcx, [rbp+90h+pv]; pv
0x18000db63  test    rcx, rcx
0x18000db66  jz      short loc_18000DB6D
0x18000db68  call    IASAttributeRelease
0x18000db6d  xor     edi, edi
0x18000db6f  jmp     short loc_18000DB8F
0x18000db71  mov     edi, 5
0x18000db76  lea     rcx, [rbp+90h+var_88]; this
0x18000db7a  call    ?free@XPBerValue@@AEAAXXZ; XPBerValue::free(void)
0x18000db7f  nop
0x18000db80  mov     rcx, [rbp+90h+pv]; pv
0x18000db84  test    rcx, rcx
0x18000db87  jz      short loc_18000DB8F
0x18000db89  call    IASAttributeRelease
0x18000db8e  nop
0x18000db8f  lea     rcx, [rbp+90h+var_58]; this
0x18000db93  call    ?free@XPBerValue@@AEAAXXZ; XPBerValue::free(void)
0x18000db98  mov     eax, edi
0x18000db9a  mov     rcx, [rbp+90h+var_50]
0x18000db9e  xor     rcx, rbp; StackCookie
0x18000dba1  call    __security_check_cookie
0x18000dba6  lea     rsp, [rbp+58h]
0x18000dbaa  pop     r15
0x18000dbac  pop     r14
0x18000dbae  pop     r13
0x18000dbb0  pop     r12
0x18000dbb2  pop     rdi
0x18000dbb3  pop     rsi
0x18000dbb4  pop     rbx
0x18000dbb5  pop     rbp
0x18000dbb6  retn
```
