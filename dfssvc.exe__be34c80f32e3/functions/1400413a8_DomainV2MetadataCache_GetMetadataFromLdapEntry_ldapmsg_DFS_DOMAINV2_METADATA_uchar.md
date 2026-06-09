# DomainV2MetadataCache::GetMetadataFromLdapEntry(ldapmsg *,_DFS_DOMAINV2_METADATA * *,uchar *)

- ea: `0x1400413a8`
- end: `0x1400425b1`
- name: `?GetMetadataFromLdapEntry@DomainV2MetadataCache@@AEAAKPEAUldapmsg@@PEAPEAU_DFS_DOMAINV2_METADATA@@PEAE@Z`
- size: `4617`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, LDAPMessage *entry, struct _DFS_DOMAINV2_METADATA **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140042ebc`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x1400096ac`
- `0x14000fca8`
- `0x140015f64`
- `0x14001e548`
- `0x1400401ac`
- `0x140040bc8`
- `0x1400411ec`
- `0x1400413a8`
- `0x1400425b8`
- `0x1400482c0`
- `0x14005ce22`
- `0x14005ce3a`

## import_xrefs

- `msvcrt!wcstoul` at `0x140041b04`
- `msvcrt!wcstoul` at `0x140041d0a`
- `msvcrt!wcstoul` at `0x140041d73`
- `msvcrt!wcstoul` at `0x140041b04`
- `msvcrt!wcstoul` at `0x140041d0a`
- `msvcrt!wcstoul` at `0x140041d73`
- `msvcrt!_wcsicmp` at `0x1400414ab`
- `msvcrt!_wcsicmp` at `0x1400414c5`
- `msvcrt!_wcsicmp` at `0x1400417ff`
- `msvcrt!_wcsicmp` at `0x14004186a`
- `msvcrt!_wcsicmp` at `0x140041964`
- `msvcrt!_wcsicmp` at `0x1400419d0`
- `msvcrt!_wcsicmp` at `0x140041a3c`
- `msvcrt!_wcsicmp` at `0x140041aba`
- `msvcrt!_wcsicmp` at `0x140041b26`
- `msvcrt!_wcsicmp` at `0x140041b8d`
- `msvcrt!_wcsicmp` at `0x140041c0f`
- `msvcrt!_wcsicmp` at `0x140041cc0`
- `msvcrt!_wcsicmp` at `0x140041d29`
- `msvcrt!_wcsicmp` at `0x140041d92`
- `msvcrt!_wcsicmp` at `0x1400414ab`
- `msvcrt!_wcsicmp` at `0x1400414c5`
- `msvcrt!_wcsicmp` at `0x1400417ff`
- `msvcrt!_wcsicmp` at `0x14004186a`
- `msvcrt!_wcsicmp` at `0x140041964`
- `msvcrt!_wcsicmp` at `0x1400419d0`
- `msvcrt!_wcsicmp` at `0x140041a3c`
- `msvcrt!_wcsicmp` at `0x140041aba`
- `msvcrt!_wcsicmp` at `0x140041b26`
- `msvcrt!_wcsicmp` at `0x140041b8d`
- `msvcrt!_wcsicmp` at `0x140041c0f`
- `msvcrt!_wcsicmp` at `0x140041cc0`
- `msvcrt!_wcsicmp` at `0x140041d29`
- `msvcrt!_wcsicmp` at `0x140041d92`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004164b`
- `ntdll!RtlInitUnicodeStringEx` at `0x140041746`
- `ntdll!RtlInitUnicodeStringEx` at `0x14004164b`
- `ntdll!RtlInitUnicodeStringEx` at `0x140041746`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1400418f3`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1400418f3`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004141e`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041546`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041777`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041e5f`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041ece`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041faf`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004206d`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004212b`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004219a`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042209`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042278`
- `WLDAP32!__imp_LdapGetLastError` at `0x1400422e7`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042356`
- `WLDAP32!__imp_LdapGetLastError` at `0x1400423c5`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042434`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004141e`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041546`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041777`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041e5f`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041ece`
- `WLDAP32!__imp_LdapGetLastError` at `0x140041faf`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004206d`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004212b`
- `WLDAP32!__imp_LdapGetLastError` at `0x14004219a`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042209`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042278`
- `WLDAP32!__imp_LdapGetLastError` at `0x1400422e7`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042356`
- `WLDAP32!__imp_LdapGetLastError` at `0x1400423c5`
- `WLDAP32!__imp_LdapGetLastError` at `0x140042434`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004142c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041554`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041785`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041e6d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041edc`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041fbd`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004207b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042139`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400421a8`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042217`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042286`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400422f5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042364`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400423d3`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042442`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004142c`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041554`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041785`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041e6d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041edc`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140041fbd`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x14004207b`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042139`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400421a8`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042217`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042286`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400422f5`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042364`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x1400423d3`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x140042442`
- `WLDAP32!__imp_ldap_count_values_len` at `0x14004189a`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041990`
- `WLDAP32!__imp_ldap_count_values_len` at `0x1400419fc`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041a68`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041c3f`
- `WLDAP32!__imp_ldap_count_values_len` at `0x14004189a`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041990`
- `WLDAP32!__imp_ldap_count_values_len` at `0x1400419fc`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041a68`
- `WLDAP32!__imp_ldap_count_values_len` at `0x140041c3f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1400418dd`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140041a9f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140041c74`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140042524`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1400418dd`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140041a9f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140041c74`
- `WLDAP32!__imp_ldap_value_free_len` at `0x140042524`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x14004140e`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041534`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x14004182b`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041ae6`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041b52`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041bb9`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041cec`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041d55`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041dc2`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x14004140e`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041534`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x14004182b`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041ae6`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041b52`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041bb9`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041cec`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041d55`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x140041dc2`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x140041763`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x140041763`
- `WLDAP32!__imp_ldap_get_dnW` at `0x1400416d9`
- `WLDAP32!__imp_ldap_get_dnW` at `0x1400416d9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1400413fc`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041522`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041819`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041ad4`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041b40`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041ba7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041cda`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041d43`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041db0`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1400413fc`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041522`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041819`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041ad4`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041b40`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041ba7`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041cda`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041d43`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x140041db0`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041888`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x14004197e`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1400419ea`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041a56`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041c2d`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041888`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x14004197e`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1400419ea`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041a56`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x140041c2d`
- `WLDAP32!__imp_ldap_memfreeW` at `0x140041e34`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1400424f9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x140042551`
- `WLDAP32!__imp_ldap_memfreeW` at `0x140041e34`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1400424f9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x140042551`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x140041e4b`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x140041e4b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400414f9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x14004161e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x140041e23`
- `WLDAP32!__imp_ldap_value_freeW` at `0x140042510`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1400414f9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x14004161e`
- `WLDAP32!__imp_ldap_value_freeW` at `0x140041e23`
- `WLDAP32!__imp_ldap_value_freeW` at `0x140042510`
- `WLDAP32!__imp_ber_free` at `0x1400424e5`
- `WLDAP32!__imp_ber_free` at `0x1400424e5`

## string_xrefs

- `0x1400417f8`: `msDFS-LinkPathv2`
- `0x1400414a4`: `msDFS-DeletedLinkv2`
- `0x140041b86`: `msDFS-Commentv2`
- `0x1400419c9`: `msDFS-LinkIdentityGUIDv2`
- `0x140041863`: `msDFS-LinkSecurityDescriptorv2`

## pseudocode

```c
__int64 __fastcall DomainV2MetadataCache::GetMetadataFromLdapEntry(
        LDAP **this,
        LDAPMessage *entry,
        struct _DFS_DOMAINV2_METADATA **a3,
        unsigned __int8 *a4)
{
  char *v7; // r14
  struct berval **values_lenW; // rsi
  WCHAR *attributeW; // r12
  PWCHAR *valuesW; // rdi
  ULONG LastError; // eax
  ULONG v12; // eax
  ULONG NamedMetadata; // ebx
  unsigned int *v14; // rcx
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  const wchar_t **i; // r14
  char v18; // r14
  __int64 v19; // rbx
  ULONG v20; // eax
  ULONG v21; // eax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rdx
  const WCHAR *v24; // rbx
  struct _DFS_DOMAINV2_METADATA **v25; // r13
  char *v26; // rax
  ULONG v27; // eax
  __int64 v28; // rax
  void *v29; // rax
  __int64 bv_len; // r9
  __int64 v31; // rbx
  unsigned __int64 v32; // rbx
  unsigned __int16 *v33; // rax
  __int64 v34; // rbx
  ULONG v35; // eax
  ULONG v36; // eax
  ULONG v37; // eax
  ULONG v38; // eax
  unsigned int *v39; // rcx
  __int64 v40; // rdx
  unsigned int *v41; // rcx
  __int64 v42; // rdx
  ULONG v43; // eax
  ULONG v44; // eax
  ULONG v45; // eax
  ULONG v46; // eax
  ULONG v47; // eax
  ULONG v48; // eax
  ULONG v49; // eax
  ULONG v50; // eax
  ULONG v51; // eax
  ULONG v52; // eax
  ULONG v53; // eax
  ULONG v54; // eax
  ULONG v55; // eax
  ULONG v56; // eax
  ULONG v57; // eax
  ULONG v58; // eax
  ULONG v59; // eax
  ULONG v60; // eax
  ULONG v61; // eax
  ULONG v62; // eax
  unsigned __int16 *Block; // [rsp+20h] [rbp-30h]
  BerElement *ptr; // [rsp+30h] [rbp-20h] BYREF
  PWCHAR dnW; // [rsp+38h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v68; // [rsp+90h] [rbp+40h] BYREF
  struct _DFS_DOMAINV2_METADATA **v69; // [rsp+A0h] [rbp+50h]
  char v70; // [rsp+A8h] [rbp+58h]

  v69 = a3;
  ptr = 0;
  v7 = 0;
  v70 = 0;
  values_lenW = 0;
  Block = 0;
  attributeW = 0;
  dnW = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  valuesW = ldap_get_valuesW(this[8], entry, (const PWSTR)L"objectClass");
  if ( !ldap_count_valuesW(valuesW) )
  {
    LastError = LdapGetLastError();
    v12 = LdapMapErrorToWin32(LastError);
    NamedMetadata = v12;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v14 = pWppControl;
    if ( pWppControl )
    {
      if ( (((1 << (v12 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        v15 = 48;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    goto LABEL_194;
  }
  for ( i = (const wchar_t **)valuesW; ; ++i )
  {
    if ( !*i )
    {
      v18 = 0;
      goto LABEL_20;
    }
    if ( !_wcsicmp(*i, L"msDFS-DeletedLinkv2") )
      break;
    if ( !_wcsicmp(*i, L"msDFS-Namespacev2") )
    {
      v70 = 1;
      v18 = 0;
      goto LABEL_20;
    }
  }
  v18 = 1;
  if ( a4 )
    *a4 = 1;
LABEL_20:
  ldap_value_freeW(valuesW);
  v19 = -1;
  if ( v70 )
  {
    v24 = 0;
  }
  else
  {
    valuesW = ldap_get_valuesW(this[8], entry, (const PWSTR)L"name");
    if ( !ldap_count_valuesW(valuesW) )
    {
      v20 = LdapGetLastError();
      v21 = LdapMapErrorToWin32(v20);
      NamedMetadata = v21;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( !pWppControl )
        {
          v7 = 0;
LABEL_194:
          v16 = 0;
          goto LABEL_195;
        }
        if ( (((1 << (v21 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
          WPP_SF_D(*((_QWORD *)pWppControl + 2), 49, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, v21);
      }
      v7 = 0;
      goto LABEL_10;
    }
    do
      ++v19;
    while ( (*valuesW)[v19] );
    v22 = v19 + 1;
    v16 = (unsigned __int16 *)operator new(saturated_mul(v22, 2u));
    Block = v16;
    if ( !v16 )
    {
      v7 = 0;
LABEL_31:
      NamedMetadata = 8;
      goto LABEL_195;
    }
    v23 = v22;
    v24 = v16;
    StringCchCopyW(v16, v23, *valuesW);
    ldap_value_freeW(valuesW);
  }
  valuesW = 0;
  if ( v18 )
  {
    DestinationString = 0;
    RtlInitUnicodeStringEx(&DestinationString, v24);
    DestinationString.Buffer += 7;
    DestinationString.Length -= 14;
    DestinationString.MaximumLength -= 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_Z(*((_QWORD *)pWppControl + 2), 50, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, &DestinationString);
    }
    v25 = v69;
    NamedMetadata = DomainV2MetadataCache::GetNamedMetadata((DomainV2MetadataCache *)this, &DestinationString, v69);
    v7 = 0;
LABEL_41:
    v16 = Block;
    goto LABEL_196;
  }
  dnW = ldap_get_dnW(this[8], entry);
  if ( !dnW )
  {
    v7 = 0;
LABEL_44:
    NamedMetadata = 8;
LABEL_45:
    v16 = Block;
    goto LABEL_195;
  }
  v26 = (char *)operator new(0xE0u);
  v7 = v26;
  if ( !v26 )
    goto LABEL_44;
  memset_0(v26, 0, 0xE0u);
  *((_DWORD *)v7 + 6) = 1;
  *((_QWORD *)v7 + 1) = v7 + 80;
  *((_QWORD *)v7 + 2) = v7;
  *((_DWORD *)v7 + 14) = *((_DWORD *)this + 13);
  *((_QWORD *)v7 + 13) = v24;
  RtlInitUnicodeStringEx((PUNICODE_STRING)v7 + 5, v24);
  Block = 0;
  attributeW = ldap_first_attributeW(this[8], entry, &ptr);
  if ( !attributeW )
  {
    v27 = LdapGetLastError();
    NamedMetadata = LdapMapErrorToWin32(v27);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v14 = pWppControl;
    v16 = 0;
    if ( pWppControl )
    {
      if ( (((1 << (NamedMetadata != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        v15 = 51;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    goto LABEL_195;
  }
  valuesW = 0;
  while ( 1 )
  {
    if ( !attributeW )
    {
      *((_QWORD *)v7 + 9) = 0;
      if ( !*((_QWORD *)v7 + 13) )
        *((_DWORD *)v7 + 43) |= 0x80u;
      v25 = v69;
      NamedMetadata = 0;
      values_lenW = 0;
      *v69 = (struct _DFS_DOMAINV2_METADATA *)v7;
      goto LABEL_41;
    }
    if ( !_wcsicmp(L"msDFS-LinkPathv2", attributeW) )
    {
      valuesW = ldap_get_valuesW(this[8], entry, attributeW);
      values_lenW = 0;
      if ( !ldap_count_valuesW(valuesW) )
      {
        v35 = LdapGetLastError();
        v36 = LdapMapErrorToWin32(v35);
        NamedMetadata = v36;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v14 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v36 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v15 = 52;
              goto LABEL_9;
            }
          }
        }
        goto LABEL_10;
      }
      v28 = anonymous_namespace_::DfspSwitchSlashesInPath(*valuesW, 0);
      *((_QWORD *)v7 + 14) = v28;
      if ( !v28 )
        goto LABEL_58;
      goto LABEL_111;
    }
    if ( !_wcsicmp(L"msDFS-LinkSecurityDescriptorv2", attributeW) )
    {
      values_lenW = ldap_get_values_lenW(this[8], entry, attributeW);
      if ( !ldap_count_values_len(values_lenW) )
      {
        v37 = LdapGetLastError();
        v38 = LdapMapErrorToWin32(v37);
        NamedMetadata = v38;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v38 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v40 = 53;
              goto LABEL_123;
            }
          }
        }
        goto LABEL_68;
      }
      v29 = operator new((*values_lenW)->bv_len);
      *((_QWORD *)v7 + 24) = v29;
      if ( !v29 )
        goto LABEL_44;
      memcpy_0(v29, (*values_lenW)->bv_val, (*values_lenW)->bv_len);
      ldap_value_free_len(values_lenW);
      values_lenW = 0;
      if ( !IsValidSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)v7 + 24)) )
      {
        NamedMetadata = 1361;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0xA00) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)pWppControl + 2), 54, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids);
        }
        goto LABEL_68;
      }
      goto LABEL_112;
    }
    if ( !_wcsicmp(L"msDFS-NamespaceIdentityGUIDv2", attributeW) )
    {
      values_lenW = ldap_get_values_lenW(this[8], entry, attributeW);
      if ( !ldap_count_values_len(values_lenW) )
      {
        v43 = LdapGetLastError();
        v44 = LdapMapErrorToWin32(v43);
        NamedMetadata = v44;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v44 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v40 = 55;
              goto LABEL_123;
            }
          }
        }
        goto LABEL_68;
      }
      bv_len = (*values_lenW)->bv_len;
      if ( (_DWORD)bv_len == 16 )
      {
        *(_OWORD *)(v7 + 120) = *(_OWORD *)(*values_lenW)->bv_val;
LABEL_81:
        ldap_value_free_len(values_lenW);
        goto LABEL_112;
      }
      NamedMetadata = 1629;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_68;
      v41 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0xA00) == 0 || *((_BYTE *)pWppControl + 25) < 3u )
        goto LABEL_68;
      v42 = 56;
      goto LABEL_129;
    }
    if ( !_wcsicmp(L"msDFS-LinkIdentityGUIDv2", attributeW) )
    {
      values_lenW = ldap_get_values_lenW(this[8], entry, attributeW);
      if ( !ldap_count_values_len(values_lenW) )
      {
        v45 = LdapGetLastError();
        v46 = LdapMapErrorToWin32(v45);
        NamedMetadata = v46;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v46 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v40 = 57;
              goto LABEL_123;
            }
          }
        }
        goto LABEL_68;
      }
      bv_len = (*values_lenW)->bv_len;
      if ( (_DWORD)bv_len == 16 )
      {
        *(_OWORD *)(v7 + 136) = *(_OWORD *)(*values_lenW)->bv_val;
        goto LABEL_81;
      }
      NamedMetadata = 1629;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_68;
      v41 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0xA00) == 0 || *((_BYTE *)pWppControl + 25) < 3u )
        goto LABEL_68;
      v42 = 58;
LABEL_129:
      WPP_SF_D(*((_QWORD *)v41 + 2), v42, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, bv_len);
      goto LABEL_68;
    }
    if ( !_wcsicmp(L"msDFS-GenerationGUIDv2", attributeW) )
    {
      values_lenW = ldap_get_values_lenW(this[8], entry, attributeW);
      if ( !ldap_count_values_len(values_lenW) )
      {
        v47 = LdapGetLastError();
        v48 = LdapMapErrorToWin32(v47);
        NamedMetadata = v48;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v39 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v48 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v40 = 59;
              goto LABEL_123;
            }
          }
        }
        goto LABEL_68;
      }
      bv_len = (*values_lenW)->bv_len;
      if ( (_DWORD)bv_len == 16 )
      {
        *(_OWORD *)(v7 + 152) = *(_OWORD *)(*values_lenW)->bv_val;
        goto LABEL_81;
      }
      NamedMetadata = 1629;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_68;
      v41 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0xA00) == 0 || *((_BYTE *)pWppControl + 25) < 3u )
        goto LABEL_68;
      v42 = 60;
      goto LABEL_129;
    }
    if ( !_wcsicmp(L"msDFS-Ttlv2", attributeW) )
    {
      valuesW = ldap_get_valuesW(this[8], entry, attributeW);
      values_lenW = 0;
      if ( !ldap_count_valuesW(valuesW) )
      {
        v49 = LdapGetLastError();
        v50 = LdapMapErrorToWin32(v49);
        NamedMetadata = v50;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v14 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v50 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v15 = 61;
              goto LABEL_9;
            }
          }
        }
        goto LABEL_10;
      }
      *((_DWORD *)v7 + 46) = wcstoul(*valuesW, 0, 0);
      goto LABEL_111;
    }
    if ( !_wcsicmp(L"msDFS-Propertiesv2", attributeW) )
    {
      valuesW = ldap_get_valuesW(this[8], entry, attributeW);
      values_lenW = 0;
      if ( !ldap_count_valuesW(valuesW) )
      {
        v51 = LdapGetLastError();
        v52 = LdapMapErrorToWin32(v51);
        NamedMetadata = v52;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v14 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v52 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v15 = 62;
              goto LABEL_9;
            }
          }
        }
        goto LABEL_10;
      }
      *((_DWORD *)v7 + 43) = anonymous_namespace_::DfspConvertEntryPropertiesToStateAndType(valuesW, v7 + 168);
      goto LABEL_111;
    }
    if ( !_wcsicmp(L"msDFS-Commentv2", attributeW) )
    {
      valuesW = ldap_get_valuesW(this[8], entry, attributeW);
      values_lenW = 0;
      if ( !ldap_count_valuesW(valuesW) )
      {
        v53 = LdapGetLastError();
        v54 = LdapMapErrorToWin32(v53);
        NamedMetadata = v54;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v14 = pWppControl;
          if ( pWppControl )
          {
            if ( (((1 << (v54 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              v15 = 63;
              goto LABEL_9;
            }
          }
        }
        goto LABEL_10;
      }
      v31 = -1;
      do
        ++v31;
      while ( (*valuesW)[v31] );
      v32 = v31 + 1;
      v33 = (unsigned __int16 *)operator new(saturated_mul(v32, 2u));
      *((_QWORD *)v7 + 22) = v33;
LABEL_109:
      if ( !v33 )
      {
LABEL_58:
        v16 = 0;
        goto LABEL_31;
      }
      StringCchCopyW(v33, v32, *valuesW);
LABEL_111:
      ldap_value_freeW(valuesW);
      valuesW = 0;
      goto LABEL_112;
    }
    if ( _wcsicmp(L"msDFS-TargetListv2", attributeW) )
      break;
    values_lenW = ldap_get_values_lenW(this[8], entry, attributeW);
    if ( !ldap_count_values_len(values_lenW) )
    {
      v55 = LdapGetLastError();
      v56 = LdapMapErrorToWin32(v55);
      NamedMetadata = v56;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v39 = pWppControl;
        if ( pWppControl )
        {
          if ( (((1 << (v56 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            v40 = 64;
LABEL_123:
            WPP_SF_D(*((_QWORD *)v39 + 2), v40, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, NamedMetadata);
          }
        }
      }
LABEL_68:
      v16 = 0;
      goto LABEL_195;
    }
    NamedMetadata = DfsConvertEntryTargetXmlDocument(
                      (*values_lenW)->bv_val,
                      (*values_lenW)->bv_len,
                      (struct _DFS_DOMAINV2_TARGET **)v7 + 26,
                      (unsigned int *)v7 + 50);
    ldap_value_free_len(values_lenW);
    values_lenW = 0;
    if ( NamedMetadata )
    {
      if ( NamedMetadata == -1073727281 )
      {
        v68 = dnW;
        DfsLogDfsEvent(0xC00038CF, 1u, (const unsigned __int16 **const)&v68, 0);
      }
      goto LABEL_45;
    }
LABEL_112:
    ldap_memfreeW(attributeW);
    attributeW = ldap_next_attributeW(this[8], entry, ptr);
  }
  if ( !_wcsicmp(L"msDFS-SchemaMajorVersion", attributeW) )
  {
    valuesW = ldap_get_valuesW(this[8], entry, attributeW);
    values_lenW = 0;
    if ( !ldap_count_valuesW(valuesW) )
    {
      v57 = LdapGetLastError();
      v58 = LdapMapErrorToWin32(v57);
      NamedMetadata = v58;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v14 = pWppControl;
        if ( pWppControl )
        {
          if ( (((1 << (v58 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            v15 = 65;
            goto LABEL_9;
          }
        }
      }
      goto LABEL_10;
    }
    *((_DWORD *)v7 + 15) = wcstoul(*valuesW, 0, 0);
    goto LABEL_111;
  }
  if ( !_wcsicmp(L"msDFS-SchemaMinorVersion", attributeW) )
  {
    valuesW = ldap_get_valuesW(this[8], entry, attributeW);
    values_lenW = 0;
    if ( !ldap_count_valuesW(valuesW) )
    {
      v59 = LdapGetLastError();
      v60 = LdapMapErrorToWin32(v59);
      NamedMetadata = v60;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v14 = pWppControl;
        if ( pWppControl )
        {
          if ( (((1 << (v60 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            v15 = 66;
            goto LABEL_9;
          }
        }
      }
      goto LABEL_10;
    }
    *((_DWORD *)v7 + 16) = wcstoul(*valuesW, 0, 0);
    goto LABEL_111;
  }
  if ( _wcsicmp(L"msDFS-LastModifiedv2", attributeW) )
    goto LABEL_112;
  valuesW = ldap_get_valuesW(this[8], entry, attributeW);
  values_lenW = 0;
  if ( ldap_count_valuesW(valuesW) )
  {
    v34 = -1;
    do
      ++v34;
    while ( (*valuesW)[v34] );
    v32 = v34 + 1;
    v33 = (unsigned __int16 *)operator new(saturated_mul(v32, 2u));
    *((_QWORD *)v7 + 27) = v33;
    goto LABEL_109;
  }
  v61 = LdapGetLastError();
  v62 = LdapMapErrorToWin32(v61);
  NamedMetadata = v62;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v14 = pWppControl;
    if ( pWppControl )
    {
      if ( (((1 << (v62 != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        v15 = 67;
LABEL_9:
        WPP_SF_D(*((_QWORD *)v14 + 2), v15, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, NamedMetadata);
      }
    }
  }
LABEL_10:
  v16 = 0;
LABEL_195:
  v25 = v69;
LABEL_196:
  operator delete(v16);
  if ( ptr )
    ber_free(ptr, 0);
  if ( attributeW )
    ldap_memfreeW(attributeW);
  if ( valuesW )
    ldap_value_freeW(valuesW);
  if ( values_lenW )
    ldap_value_free_len(values_lenW);
  if ( NamedMetadata && v7 )
  {
    DfsDomainV2FreeMetadata((struct _DFS_DOMAINV2_METADATA *)v7);
    *v25 = 0;
  }
  if ( dnW )
    ldap_memfreeW(dnW);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 68, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids, NamedMetadata);
  }
  return NamedMetadata;
}

```

## disassembly

```asm
0x1400413a8  mov     [rsp-38h+arg_8], rbx
0x1400413ad  mov     [rsp-38h+arg_10], r8
0x1400413b2  push    rbp
0x1400413b3  push    rsi
0x1400413b4  push    rdi
0x1400413b5  push    r12
0x1400413b7  push    r13
0x1400413b9  push    r14
0x1400413bb  push    r15
0x1400413bd  mov     rbp, rsp
0x1400413c0  sub     rsp, 50h
0x1400413c4  mov     r15, rcx
0x1400413c7  mov     rbx, r9
0x1400413ca  xor     ecx, ecx
0x1400413cc  mov     r13, rdx
0x1400413cf  mov     [rbp+ptr], rcx
0x1400413d3  mov     r14d, ecx
0x1400413d6  mov     [rbp+arg_18], cl
0x1400413d9  mov     esi, ecx
0x1400413db  mov     [rbp+Block], rcx
0x1400413df  mov     r12d, ecx
0x1400413e2  mov     [rbp+var_18], rcx
0x1400413e6  mov     [r8], rcx
0x1400413e9  test    r9, r9
0x1400413ec  jz      short loc_1400413F1
0x1400413ee  mov     [r9], cl
0x1400413f1  mov     rcx, [r15+40h]; ld
0x1400413f5  lea     r8, attr; "objectClass"
0x1400413fc  call    cs:__imp_ldap_get_valuesW
0x140041403  nop     dword ptr [rax+rax+00h]
0x140041408  mov     rcx, rax; vals
0x14004140b  mov     rdi, rax
0x14004140e  call    cs:__imp_ldap_count_valuesW
0x140041415  nop     dword ptr [rax+rax+00h]
0x14004141a  test    eax, eax
0x14004141c  jnz     short loc_140041499
0x14004141e  call    cs:__imp_LdapGetLastError
0x140041425  nop     dword ptr [rax+rax+00h]
0x14004142a  mov     ecx, eax; LdapError
0x14004142c  call    cs:__imp_LdapMapErrorToWin32
0x140041433  nop     dword ptr [rax+rax+00h]
0x140041438  mov     ebx, eax
0x14004143a  lea     r15, WPP_GLOBAL_Control
0x140041441  cmp     cs:WPP_GLOBAL_Control, r15
0x140041448  jz      short loc_140041491
0x14004144a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140041451  xor     edx, edx
0x140041453  test    rcx, rcx
0x140041456  jz      loc_1400424CB
0x14004145c  neg     eax
0x14004145e  mov     eax, 200h
0x140041463  sbb     edx, edx
0x140041465  and     edx, 0FFFFFFECh
0x140041468  add     edx, 1Fh
0x14004146b  bts     eax, edx
0x14004146e  test    [rcx+1Ch], eax
0x140041471  jz      short loc_140041491
0x140041473  cmp     byte ptr [rcx+19h], 3
0x140041477  jb      short loc_140041491
0x140041479  mov     edx, 30h ; '0'
0x14004147e  mov     rcx, [rcx+10h]
0x140041482  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140041489  mov     r9d, ebx
0x14004148c  call    WPP_SF_D
0x140041491  mov     rax, rsi
0x140041494  jmp     loc_1400424CE
0x140041499  mov     r14, rdi
0x14004149c  mov     rcx, [r14]; String1
0x14004149f  test    rcx, rcx
0x1400414a2  jz      short loc_1400414F3
0x1400414a4  lea     rdx, aMsdfsDeletedli; "msDFS-DeletedLinkv2"
0x1400414ab  call    cs:__imp__wcsicmp
0x1400414b2  nop     dword ptr [rax+rax+00h]
0x1400414b7  test    eax, eax
0x1400414b9  jz      short loc_1400414E6
0x1400414bb  mov     rcx, [r14]; String1
0x1400414be  lea     rdx, aMsdfsNamespace_0; "msDFS-Namespacev2"
0x1400414c5  call    cs:__imp__wcsicmp
0x1400414cc  nop     dword ptr [rax+rax+00h]
0x1400414d1  xor     edx, edx
0x1400414d3  test    eax, eax
0x1400414d5  jz      short loc_1400414DD
0x1400414d7  add     r14, 8
0x1400414db  jmp     short loc_14004149C
0x1400414dd  mov     [rbp+arg_18], 1
0x1400414e1  mov     r14b, dl
0x1400414e4  jmp     short loc_1400414F6
0x1400414e6  mov     r14b, 1
0x1400414e9  test    rbx, rbx
0x1400414ec  jz      short loc_1400414F6
0x1400414ee  mov     [rbx], r14b
0x1400414f1  jmp     short loc_1400414F6
0x1400414f3  mov     r14b, sil
0x1400414f6  mov     rcx, rdi; vals
0x1400414f9  call    cs:__imp_ldap_value_freeW
0x140041500  nop     dword ptr [rax+rax+00h]
0x140041505  xor     eax, eax
0x140041507  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004150b  cmp     [rbp+arg_18], al
0x14004150e  jnz     loc_14004162E
0x140041514  mov     rcx, [r15+40h]; ld
0x140041518  lea     r8, aName; "name"
0x14004151f  mov     rdx, r13; entry
0x140041522  call    cs:__imp_ldap_get_valuesW
0x140041529  nop     dword ptr [rax+rax+00h]
0x14004152e  mov     rcx, rax; vals
0x140041531  mov     rdi, rax
0x140041534  call    cs:__imp_ldap_count_valuesW
0x14004153b  nop     dword ptr [rax+rax+00h]
0x140041540  xor     ecx, ecx
0x140041542  test    eax, eax
0x140041544  jnz     short loc_1400415C1
0x140041546  call    cs:__imp_LdapGetLastError
0x14004154d  nop     dword ptr [rax+rax+00h]
0x140041552  mov     ecx, eax; LdapError
0x140041554  call    cs:__imp_LdapMapErrorToWin32
0x14004155b  nop     dword ptr [rax+rax+00h]
0x140041560  mov     ebx, eax
0x140041562  lea     r15, WPP_GLOBAL_Control
0x140041569  cmp     cs:WPP_GLOBAL_Control, r15
0x140041570  jz      short loc_1400415B9
0x140041572  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140041579  xor     edx, edx
0x14004157b  test    rcx, rcx
0x14004157e  jz      loc_1400424C8
0x140041584  neg     eax
0x140041586  mov     eax, 200h
0x14004158b  sbb     edx, edx
0x14004158d  and     edx, 0FFFFFFECh
0x140041590  add     edx, 1Fh
0x140041593  bts     eax, edx
0x140041596  test    [rcx+1Ch], eax
0x140041599  jz      short loc_1400415B9
0x14004159b  cmp     byte ptr [rcx+19h], 3
0x14004159f  jb      short loc_1400415B9
0x1400415a1  mov     rcx, [rcx+10h]
0x1400415a5  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x1400415ac  mov     edx, 31h ; '1'
0x1400415b1  mov     r9d, ebx
0x1400415b4  call    WPP_SF_D
0x1400415b9  mov     r14, rsi
0x1400415bc  jmp     loc_140041491
0x1400415c1  mov     rax, [rdi]
0x1400415c4  inc     rbx
0x1400415c7  cmp     [rax+rbx*2], cx
0x1400415cb  jnz     short loc_1400415C4
0x1400415cd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400415d4  inc     rbx
0x1400415d7  mov     eax, 2
0x1400415dc  mul     rbx
0x1400415df  cmovo   rax, rcx
0x1400415e3  mov     rcx, rax; Size
0x1400415e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400415eb  xor     edx, edx
0x1400415ed  mov     [rbp+Block], rax
0x1400415f1  test    rax, rax
0x1400415f4  jnz     short loc_14004160A
0x1400415f6  mov     r14d, edx
0x1400415f9  mov     ebx, 8
0x1400415fe  lea     r15, WPP_GLOBAL_Control
0x140041605  jmp     loc_1400424CE
0x14004160a  mov     r8, [rdi]; unsigned __int16 *
0x14004160d  mov     rdx, rbx; unsigned __int64
0x140041610  mov     rcx, rax; unsigned __int16 *
0x140041613  mov     rbx, rax
0x140041616  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004161b  mov     rcx, rdi; vals
0x14004161e  call    cs:__imp_ldap_value_freeW
0x140041625  nop     dword ptr [rax+rax+00h]
0x14004162a  xor     eax, eax
0x14004162c  jmp     short loc_140041631
0x14004162e  mov     rbx, rax
0x140041631  mov     rdi, rax
0x140041634  test    r14b, r14b
0x140041637  jz      loc_1400416D2
0x14004163d  xorps   xmm0, xmm0
0x140041640  lea     rcx, [rbp+DestinationString]; DestinationString
0x140041644  mov     rdx, rbx; SourceString
0x140041647  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004164b  call    cs:__imp_RtlInitUnicodeStringEx
0x140041652  nop     dword ptr [rax+rax+00h]
0x140041657  add     [rbp+DestinationString.Buffer], 0Eh
0x14004165c  mov     eax, 0FFF2h
0x140041661  add     [rbp+DestinationString.Length], ax
0x140041665  add     [rbp+DestinationString.MaximumLength], ax
0x140041669  lea     rax, WPP_GLOBAL_Control
0x140041670  cmp     cs:WPP_GLOBAL_Control, rax
0x140041677  jz      short loc_1400416AA
0x140041679  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140041680  test    rcx, rcx
0x140041683  jz      short loc_1400416AA
0x140041685  test    byte ptr [rcx+1Ch], 20h
0x140041689  jz      short loc_1400416AA
0x14004168b  cmp     byte ptr [rcx+19h], 2
0x14004168f  jb      short loc_1400416AA
0x140041691  mov     rcx, [rcx+10h]
0x140041695  lea     r9, [rbp+DestinationString]
0x140041699  mov     edx, 32h ; '2'
0x14004169e  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x1400416a5  call    WPP_SF_Z
0x1400416aa  mov     r13, [rbp+arg_10]
0x1400416ae  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x1400416b2  mov     r8, r13; struct _DFS_DOMAINV2_METADATA **
0x1400416b5  mov     rcx, r15; this
0x1400416b8  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x1400416bd  mov     ebx, eax
0x1400416bf  mov     r14, rsi
0x1400416c2  mov     rax, [rbp+Block]
0x1400416c6  lea     r15, WPP_GLOBAL_Control
0x1400416cd  jmp     loc_1400424D2
0x1400416d2  mov     rcx, [r15+40h]; ld
0x1400416d6  mov     rdx, r13; entry
0x1400416d9  call    cs:__imp_ldap_get_dnW
0x1400416e0  nop     dword ptr [rax+rax+00h]
0x1400416e5  xor     edx, edx
0x1400416e7  mov     [rbp+var_18], rax
0x1400416eb  test    rax, rax
0x1400416ee  jnz     short loc_140041701
0x1400416f0  mov     r14d, edx
0x1400416f3  mov     ebx, 8
0x1400416f8  mov     rax, [rbp+Block]
0x1400416fc  jmp     loc_1400415FE
0x140041701  mov     ecx, 0E0h; Size
0x140041706  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004170b  mov     r14, rax
0x14004170e  test    rax, rax
0x140041711  jz      short loc_1400416F3
0x140041713  xor     edx, edx; Val
0x140041715  mov     r8d, 0E0h; Size
0x14004171b  mov     rcx, rax; void *
0x14004171e  call    memset_0
0x140041723  lea     rcx, [r14+50h]; DestinationString
0x140041727  mov     dword ptr [r14+18h], 1
0x14004172f  mov     [r14+8], rcx
0x140041733  mov     rdx, rbx; SourceString
0x140041736  mov     [r14+10h], r14
0x14004173a  mov     eax, [r15+34h]
0x14004173e  mov     [r14+38h], eax
0x140041742  mov     [r14+68h], rbx
0x140041746  call    cs:__imp_RtlInitUnicodeStringEx
0x14004174d  nop     dword ptr [rax+rax+00h]
0x140041752  mov     rcx, [r15+40h]; ld
0x140041756  lea     r8, [rbp+ptr]; ptr
0x14004175a  xor     ebx, ebx
0x14004175c  mov     rdx, r13; entry
0x14004175f  mov     [rbp+Block], rbx
0x140041763  call    cs:__imp_ldap_first_attributeW
0x14004176a  nop     dword ptr [rax+rax+00h]
0x14004176f  mov     r12, rax
0x140041772  test    rax, rax
0x140041775  jnz     short loc_1400417EA
0x140041777  call    cs:__imp_LdapGetLastError
0x14004177e  nop     dword ptr [rax+rax+00h]
0x140041783  mov     ecx, eax; LdapError
0x140041785  call    cs:__imp_LdapMapErrorToWin32
0x14004178c  nop     dword ptr [rax+rax+00h]
0x140041791  mov     ebx, eax
0x140041793  lea     r15, WPP_GLOBAL_Control
0x14004179a  cmp     cs:WPP_GLOBAL_Control, r15
0x1400417a1  jz      loc_140041491
0x1400417a7  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400417ae  xor     eax, eax
0x1400417b0  test    rcx, rcx
0x1400417b3  jz      loc_1400424CE
0x1400417b9  mov     eax, ebx
0x1400417bb  neg     eax
0x1400417bd  mov     eax, 200h
0x1400417c2  sbb     edx, edx
0x1400417c4  and     edx, 0FFFFFFECh
0x1400417c7  add     edx, 1Fh
0x1400417ca  bts     eax, edx
0x1400417cd  test    [rcx+1Ch], eax
0x1400417d0  jz      loc_140041491
0x1400417d6  cmp     byte ptr [rcx+19h], 3
0x1400417da  jb      loc_140041491
0x1400417e0  lea     edx, [r12+33h]
0x1400417e5  jmp     loc_14004147E
0x1400417ea  xor     edi, edi
0x1400417ec  test    r12, r12
0x1400417ef  jz      loc_1400424A3
0x1400417f5  mov     rdx, r12; String2
0x1400417f8  lea     rcx, aMsdfsLinkpathv_0; "msDFS-LinkPathv2"
0x1400417ff  call    cs:__imp__wcsicmp
0x140041806  nop     dword ptr [rax+rax+00h]
0x14004180b  test    eax, eax
0x14004180d  jnz     short loc_140041860
0x14004180f  mov     rcx, [r15+40h]; ld
0x140041813  mov     r8, r12; attr
0x140041816  mov     rdx, r13; entry
0x140041819  call    cs:__imp_ldap_get_valuesW
0x140041820  nop     dword ptr [rax+rax+00h]
0x140041825  mov     rcx, rax; vals
0x140041828  mov     rdi, rax
0x14004182b  call    cs:__imp_ldap_count_valuesW
0x140041832  nop     dword ptr [rax+rax+00h]
0x140041837  xor     esi, esi
0x140041839  test    eax, eax
0x14004183b  jz      loc_140041E5F
0x140041841  mov     rcx, [rdi]
0x140041844  xor     edx, edx
  ... truncated ...
```
