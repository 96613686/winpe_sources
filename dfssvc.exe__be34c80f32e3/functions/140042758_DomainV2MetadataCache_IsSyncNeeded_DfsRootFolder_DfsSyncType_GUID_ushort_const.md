# DomainV2MetadataCache::IsSyncNeeded(DfsRootFolder::DfsSyncType *,_GUID *,ushort const * *)

- ea: `0x140042758`
- end: `0x140042a03`
- name: `?IsSyncNeeded@DomainV2MetadataCache@@AEAAEPEAW4DfsSyncType@DfsRootFolder@@PEAU_GUID@@PEAPEBG@Z`
- size: `683`
- prototype: `unsigned __int8 __fastcall(DomainV2MetadataCache *__hidden this, enum DfsRootFolder::DfsSyncType *, struct _GUID *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003f344`

## callees

- `0x140006bf0`
- `0x140009770`
- `0x140041314`
- `0x140042758`
- `0x140044268`
- `0x1400442c4`
- `0x140049ba4`
- `0x14005ce70`

## import_xrefs

- `WLDAP32!__imp_ldap_count_entries` at `0x14004298e`
- `WLDAP32!__imp_ldap_count_entries` at `0x14004298e`
- `WLDAP32!__imp_ldap_msgfree` at `0x1400428a3`
- `WLDAP32!__imp_ldap_msgfree` at `0x1400428a3`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140042969`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x140042969`

## string_xrefs

- `0x140042914`: `(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))`
- `0x140042838`: `highestCommittedUSN`

## pseudocode

```c
bool __fastcall DomainV2MetadataCache::IsSyncNeeded(
        LDAP **this,
        enum DfsRootFolder::DfsSyncType *a2,
        struct _GUID *a3,
        const unsigned __int16 **a4)
{
  int v7; // edx
  unsigned int *v8; // rcx
  int v9; // r8d
  const unsigned __int16 *v10; // r9
  bool v11; // bl
  _QWORD *v12; // rdi
  const unsigned __int16 *AttributeValue; // rax
  const unsigned __int16 **v14; // rdi
  __int64 v16; // rax
  struct CConfigurationSettings *Instance; // rax
  WCHAR *v18; // rdx
  WCHAR *v19; // r9
  LONG v20; // ecx
  WCHAR *v21; // rax
  ULONG v22; // eax
  ULONG v23; // eax
  LDAPMessage *res; // [rsp+60h] [rbp-19h] BYREF
  struct l_timeval timeout; // [rsp+68h] [rbp-11h] BYREF
  const unsigned __int16 **v26; // [rsp+70h] [rbp-9h]
  PWSTR attrs[2]; // [rsp+78h] [rbp-1h] BYREF
  struct _GUID v28; // [rsp+88h] [rbp+Fh] BYREF

  v26 = a4;
  res = 0;
  timeout = 0;
  *(_OWORD *)attrs = 0;
  v28 = 0;
  if ( DomainV2MetadataCache::GetDcInvocationId((DomainV2MetadataCache *)this, &v28) )
  {
    v11 = 1;
    if ( *(_DWORD *)a2 == 1 )
      *(_DWORD *)a2 = 2;
    v12 = this + 144;
    goto LABEL_9;
  }
  v12 = this + 144;
  if ( this == (LDAP **)-1152LL )
    goto LABEL_6;
  if ( *(_DWORD *)a2 == 3 )
  {
    v11 = 1;
    goto LABEL_9;
  }
  v16 = *(_QWORD *)&v28.Data1 - *v12;
  if ( *(_QWORD *)&v28.Data1 == *v12 )
    v16 = *(_QWORD *)v28.Data4 - (_QWORD)this[145];
  if ( v16 )
  {
LABEL_6:
    v11 = 1;
LABEL_7:
    if ( *(_DWORD *)a2 == 1 )
      *(_DWORD *)a2 = 2;
    goto LABEL_9;
  }
  attrs[1] = 0;
  attrs[0] = (PWSTR)L"objectClass";
  Instance = CConfigurationSettings::_GetInstance(v8);
  v18 = (WCHAR *)this[143];
  v19 = L"(|(objectClass=msDFS-Namespacev2)(objectClass=msDFS-Linkv2)(objectClass=msDFS-DeletedLinkv2))";
  v11 = 1;
  v20 = *((_DWORD *)Instance + 7);
  v21 = (WCHAR *)this[146];
  timeout.tv_sec = v20;
  if ( v21 )
    v19 = v21;
  v22 = ldap_search_ext_sW(this[8], v18, 2u, v19, attrs, 1u, 0, 0, &timeout, 1u, &res);
  if ( v22 == 4 )
    goto LABEL_9;
  if ( v22 )
    goto LABEL_7;
  v23 = ldap_count_entries(this[8], res);
  v11 = v23 != 0;
  if ( v23 )
  {
LABEL_9:
    *a3 = v28;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x200) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_q_guid__guid_(*((_QWORD *)pWppControl + 2), v7, v9, (_DWORD)this, (__int64)a3, (__int64)v12);
    }
    AttributeValue = CLdap::GetAttributeValue((CLdap *)(this + 8), 0, L"highestCommittedUSN", v10);
    v14 = v26;
    *v26 = AttributeValue;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x200) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_qS(
        *((_QWORD *)pWppControl + 2),
        83,
        (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
        (_DWORD)this,
        (__int64)AttributeValue);
    }
    if ( !*v14 )
      *a3 = 0;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x200) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_q_guid_(*((_QWORD *)pWppControl + 2), 84, v9, (_DWORD)this, (__int64)&v28);
  }
LABEL_21:
  if ( res )
    ldap_msgfree(res);
  return v11;
}

```

## disassembly

```asm
0x140042758  push    rbp
0x14004275a  push    rbx
0x14004275b  push    rsi
0x14004275c  push    rdi
0x14004275d  push    r12
0x14004275f  push    r13
0x140042761  push    r14
0x140042763  lea     rbp, [rsp-27h]
0x140042768  sub     rsp, 0A0h
0x14004276f  mov     rax, cs:__security_cookie
0x140042776  xor     rax, rsp
0x140042779  mov     [rbp+57h+var_38], rax
0x14004277d  mov     rsi, rdx
0x140042780  mov     [rbp+57h+var_60], r9
0x140042784  xor     r12d, r12d
0x140042787  lea     rdx, [rbp+57h+var_48]; struct _GUID *
0x14004278b  xorps   xmm0, xmm0
0x14004278e  mov     [rbp+57h+res], r12
0x140042792  xorps   xmm1, xmm1
0x140042795  mov     qword ptr [rbp+57h+var_68.tv_sec], r12
0x140042799  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x14004279d  mov     r13, r8
0x1400427a0  mov     r14, rcx
0x1400427a3  movups  xmmword ptr [rbp+57h+var_48.Data1], xmm1
0x1400427a7  call    ?GetDcInvocationId@DomainV2MetadataCache@@AEAAKPEAU_GUID@@@Z; DomainV2MetadataCache::GetDcInvocationId(_GUID *)
0x1400427ac  test    eax, eax
0x1400427ae  jz      short loc_1400427C8
0x1400427b0  lea     ebx, [r12+1]
0x1400427b5  cmp     [rsi], ebx
0x1400427b7  jnz     short loc_1400427BF
0x1400427b9  mov     dword ptr [rsi], 2
0x1400427bf  lea     rdi, [r14+480h]
0x1400427c6  jmp     short loc_1400427E7
0x1400427c8  lea     rdi, [r14+480h]
0x1400427cf  test    rdi, rdi
0x1400427d2  jnz     loc_1400428D0
0x1400427d8  mov     ebx, 1
0x1400427dd  cmp     [rsi], ebx
0x1400427df  jnz     short loc_1400427E7
0x1400427e1  mov     dword ptr [rsi], 2
0x1400427e7  movups  xmm0, xmmword ptr [rbp+57h+var_48.Data1]
0x1400427eb  movdqu  xmmword ptr [r13+0], xmm0
0x1400427f1  lea     r12, WPP_GLOBAL_Control
0x1400427f8  cmp     cs:WPP_GLOBAL_Control, r12
0x1400427ff  jz      short loc_140042832
0x140042801  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042808  test    rcx, rcx
0x14004280b  jz      short loc_140042832
0x14004280d  test    dword ptr [rcx+1Ch], 200h
0x140042814  jz      short loc_140042832
0x140042816  cmp     byte ptr [rcx+19h], 3
0x14004281a  jb      short loc_140042832
0x14004281c  mov     rcx, [rcx+10h]
0x140042820  mov     r9, r14
0x140042823  mov     qword ptr [rsp+0D0h+attrsonly], rdi
0x140042828  mov     [rsp+0D0h+attrs], r13
0x14004282d  call    WPP_SF_q_guid__guid_
0x140042832  lea     rcx, [r14+40h]; this
0x140042836  xor     edx, edx; unsigned __int16 *
0x140042838  lea     r8, aHighestcommitt; "highestCommittedUSN"
0x14004283f  call    ?GetAttributeValue@CLdap@@QEAAPEBGPEBG00@Z; CLdap::GetAttributeValue(ushort const *,ushort const *,ushort const *)
0x140042844  mov     rdi, [rbp+57h+var_60]
0x140042848  mov     [rdi], rax
0x14004284b  cmp     cs:WPP_GLOBAL_Control, r12
0x140042852  jz      short loc_14004288C
0x140042854  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004285b  test    rcx, rcx
0x14004285e  jz      short loc_14004288C
0x140042860  test    dword ptr [rcx+1Ch], 200h
0x140042867  jz      short loc_14004288C
0x140042869  cmp     byte ptr [rcx+19h], 3
0x14004286d  jb      short loc_14004288C
0x14004286f  mov     rcx, [rcx+10h]
0x140042873  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14004287a  mov     edx, 53h ; 'S'
0x14004287f  mov     [rsp+0D0h+attrs], rax
0x140042884  mov     r9, r14
0x140042887  call    WPP_SF_qS
0x14004288c  cmp     qword ptr [rdi], 0
0x140042890  jnz     short loc_14004289A
0x140042892  xorps   xmm0, xmm0
0x140042895  movups  xmmword ptr [r13+0], xmm0
0x14004289a  mov     rcx, [rbp+57h+res]; res
0x14004289e  test    rcx, rcx
0x1400428a1  jz      short loc_1400428AF
0x1400428a3  call    cs:__imp_ldap_msgfree
0x1400428aa  nop     dword ptr [rax+rax+00h]
0x1400428af  mov     al, bl
0x1400428b1  mov     rcx, [rbp+57h+var_38]
0x1400428b5  xor     rcx, rsp; StackCookie
0x1400428b8  call    __security_check_cookie
0x1400428bd  add     rsp, 0A0h
0x1400428c4  pop     r14
0x1400428c6  pop     r13
0x1400428c8  pop     r12
0x1400428ca  pop     rdi
0x1400428cb  pop     rsi
0x1400428cc  pop     rbx
0x1400428cd  pop     rbp
0x1400428ce  retn
0x1400428d0  cmp     dword ptr [rsi], 3
0x1400428d3  jnz     short loc_1400428DF
0x1400428d5  mov     ebx, 1
0x1400428da  jmp     loc_1400427E7
0x1400428df  mov     rax, qword ptr [rbp+57h+var_48.Data1]
0x1400428e3  sub     rax, [rdi]
0x1400428e6  jnz     short loc_1400428F0
0x1400428e8  mov     rax, qword ptr [rbp+57h+var_48.Data4]
0x1400428ec  sub     rax, [rdi+8]
0x1400428f0  test    rax, rax
0x1400428f3  jnz     loc_1400427D8
0x1400428f9  lea     rax, attr; "objectClass"
0x140042900  mov     [rbp+57h+var_58+8], r12
0x140042904  mov     [rbp+57h+var_58], rax
0x140042908  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14004290d  mov     rdx, [r14+478h]; base
0x140042914  lea     r9, aObjectclassMsd_1; "(|(objectClass=msDFS-Namespacev2)(objec"...
0x14004291b  mov     ebx, 1
0x140042920  mov     ecx, [rax+1Ch]
0x140042923  mov     rax, [r14+490h]
0x14004292a  test    rax, rax
0x14004292d  mov     [rbp+57h+var_68.tv_sec], ecx
0x140042930  mov     rcx, [r14+40h]; ld
0x140042934  lea     r8d, [rbx+1]; scope
0x140042938  cmovnz  r9, rax; filter
0x14004293c  lea     rax, [rbp+57h+res]
0x140042940  mov     [rsp+0D0h+var_80], rax; res
0x140042945  lea     rax, [rbp+57h+var_68]
0x140042949  mov     [rsp+0D0h+SizeLimit], ebx; SizeLimit
0x14004294d  mov     [rsp+0D0h+timeout], rax; timeout
0x140042952  lea     rax, [rbp+57h+var_58]
0x140042956  mov     [rsp+0D0h+ClientControls], r12; ClientControls
0x14004295b  mov     [rsp+0D0h+ServerControls], r12; ServerControls
0x140042960  mov     [rsp+0D0h+attrsonly], ebx; attrsonly
0x140042964  mov     [rsp+0D0h+attrs], rax; attrs
0x140042969  call    cs:__imp_ldap_search_ext_sW
0x140042970  nop     dword ptr [rax+rax+00h]
0x140042975  cmp     eax, 4
0x140042978  jz      loc_1400427E7
0x14004297e  test    eax, eax
0x140042980  jnz     loc_1400427DD
0x140042986  mov     rdx, [rbp+57h+res]; res
0x14004298a  mov     rcx, [r14+40h]; ld
0x14004298e  call    cs:__imp_ldap_count_entries
0x140042995  nop     dword ptr [rax+rax+00h]
0x14004299a  test    eax, eax
0x14004299c  setnz   sil
0x1400429a0  mov     bl, sil
0x1400429a3  test    eax, eax
0x1400429a5  jnz     loc_1400427E7
0x1400429ab  lea     r12, WPP_GLOBAL_Control
0x1400429b2  cmp     cs:WPP_GLOBAL_Control, r12
0x1400429b9  jz      loc_14004289A
0x1400429bf  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400429c6  test    rcx, rcx
0x1400429c9  jz      loc_14004289A
0x1400429cf  test    dword ptr [rcx+1Ch], 200h
0x1400429d6  jz      loc_14004289A
0x1400429dc  cmp     byte ptr [rcx+19h], 3
0x1400429e0  jb      loc_14004289A
0x1400429e6  mov     rcx, [rcx+10h]
0x1400429ea  lea     edx, [rax+54h]
0x1400429ed  lea     rax, [rbp+57h+var_48]
0x1400429f1  mov     r9, r14
0x1400429f4  mov     [rsp+0D0h+attrs], rax
0x1400429f9  call    WPP_SF_q_guid_
0x1400429fe  jmp     loc_14004289A
```
