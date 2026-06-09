# ReAclDNSRecords(_HCLUSTER *,cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0> &,CAutoMemPtr<ClusterADLdap> &,CAutoMemPtr<ClusterADObject> &)

- ea: `0x180075a58`
- end: `0x1800766b1`
- name: `?ReAclDNSRecords@@YAKPEAU_HCLUSTER@@AEAU?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@AEAV?$CAutoMemPtr@VClusterADLdap@@@@AEAV?$CAutoMemPtr@VClusterADObject@@@@@Z`
- size: `3161`
- prototype: `__int64 __fastcall(HCLUSTER hCluster)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800770a0`

## callees

- `0x180002f50`
- `0x180013ae4`
- `0x180019030`
- `0x180019c18`
- `0x18001cc08`
- `0x18001ecdc`
- `0x18001ed18`
- `0x180028f30`
- `0x180029578`
- `0x180029ce4`
- `0x18002a644`
- `0x18002fb04`
- `0x180039028`
- `0x18006f910`
- `0x180070c2c`
- `0x180070f3c`
- `0x1800738b0`
- `0x180073d78`
- `0x18007405c`
- `0x18007438c`
- `0x180075a58`
- `0x1800766b8`
- `0x1800a45f0`
- `0x1800a4944`
- `0x1800a5388`

## string_xrefs

- `0x180075ac7`: `ReAclDNSRecords`
- `0x180075c69`: `ReAclDNSRecords`
- `0x180075e78`: `ReAclDNSRecords`
- `0x180075ef5`: `ReAclDNSRecords`
- `0x180075f22`: `ReAclDNSRecords`
- `0x180075f51`: `ReAclDNSRecords`
- `0x180075ff1`: `ReAclDNSRecords`
- `0x180076099`: `ReAclDNSRecords`
- `0x1800762c6`: `ReAclDNSRecords`
- `0x1800762f9`: `ReAclDNSRecords`
- `0x18007631c`: `ReAclDNSRecords`
- `0x180076399`: `ReAclDNSRecords`
- `0x1800763c1`: `ReAclDNSRecords`
- `0x1800763ee`: `ReAclDNSRecords`
- `0x18007648f`: `ReAclDNSRecords`
- `0x18007654f`: `ReAclDNSRecords`
- `0x180075ca4`: `Getting SID for the CNO Account`
- `0x180075cf0`: `Failed to get the CNO's SID, error %d.`
- `0x180075e66`: `Attempting to grant CNO permissions`
- `0x18007630a`: `Attempting to grant CNO permissions`
- `0x180076175`: `Getting SID for the Network Name Account`
- `0x1800761af`: `Failed to get a Netname's SID, error %d. Moving on to next netname.`
- `0x1800762b4`: `Attempting to grant VCO permissions`
- `0x1800765d7`: `Complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ReAclDNSRecords(HCLUSTER hCluster, struct _HRESOURCE **a2, _QWORD *a3)
{
  _QWORD *v3; // r12
  int AdapterDnsSuffixesForCluster; // eax
  unsigned int SIDForResource; // ebx
  __int64 first_of; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  int DomainDN; // eax
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  const wchar_t *v18; // rax
  __int64 v19; // r9
  _QWORD *v20; // rbx
  unsigned int v21; // r15d
  __int64 v22; // rax
  unsigned int DnsADOObject; // eax
  unsigned int v24; // edi
  __int64 v25; // rdi
  int v26; // r12d
  __int64 v27; // rdi
  __int64 v28; // rax
  __int64 **v29; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rcx
  struct _HRESOURCE **k; // rsi
  __int64 v39; // rax
  int v40; // eax
  int DnsNameForResource; // eax
  _QWORD *v42; // rbx
  __int64 v43; // rax
  unsigned int v44; // eax
  __int64 v45; // rdi
  int v46; // r12d
  __int64 v47; // rdi
  __int64 v48; // rax
  __int64 **v49; // rcx
  __int64 m; // rax
  __int64 *n; // rcx
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // [rsp+28h] [rbp-D8h]
  __int64 v57; // [rsp+28h] [rbp-D8h]
  __int64 v58; // [rsp+28h] [rbp-D8h]
  __int64 v59; // [rsp+38h] [rbp-C8h]
  __int128 v60; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h]
  _QWORD v62[2]; // [rsp+68h] [rbp-98h] BYREF
  char v63[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v64; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+88h] [rbp-78h]
  _QWORD *v66; // [rsp+90h] [rbp-70h]
  _BYTE v67[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v68[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v69[32]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v70[32]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v71[32]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v72[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v73[32]; // [rsp+158h] [rbp+58h] BYREF

  v3 = a3;
  v66 = a3;
  v62[0] = CaseInsensitiveLessThan;
  std::set<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>>::set<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>>(
    v63,
    v62);
  std::wstring::wstring(v69);
  TraceMsg(4, 0, L"ReAclDNSRecords", 2199, L"Getting DNS suffixes for the cluster");
  AdapterDnsSuffixesForCluster = GetAdapterDnsSuffixesForCluster(hCluster, v63);
  SIDForResource = AdapterDnsSuffixesForCluster;
  if ( AdapterDnsSuffixesForCluster )
  {
    TraceMsg(
      2,
      0,
      L"ReAclDNSRecords",
      2207,
      L"failed getting the DNS Suffix list for the cluster, error %d.",
      AdapterDnsSuffixesForCluster);
LABEL_3:
    std::wstring::_Tidy_deallocate(v69);
    std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
      &v64,
      &v64);
    return SIDForResource;
  }
  TraceMsg(4, 0, L"ReAclDNSRecords", 2211, L"Found %d suffixes", v65);
  TraceMsg(4, 0, L"ReAclDNSRecords", 2215, L"Getting AD Domain name from our LDAP connection");
  ClusterADLdap::GetADDomainName(*v3, v67);
  std::wstring::wstring(v72);
  std::_Tree<std::_Tset_traits<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>,0>>::insert<0,0>(
    v63,
    v62,
    v67);
  first_of = std::wstring::find_first_of(v67);
  if ( first_of == -1 )
  {
    std::wstring::operator=(v72, v67);
  }
  else
  {
    v11 = std::wstring::substr(v67, v73, v10, first_of);
    std::wstring::operator=(v72, v11);
    std::wstring::_Tidy_deallocate(v73);
  }
  DomainDN = ClusterADLdap::GetDomainDN(*v3, v67, v72, v69);
  v13 = *v3;
  if ( (DomainDN & 0x1FFF0000) == 0x70000 )
    v14 = (unsigned __int16)ClusterADLdap::GetDomainDN(v13, v67, v72, v69);
  else
    v14 = ClusterADLdap::GetDomainDN(v13, v67, v72, v69);
  v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v67);
  v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v72);
  v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v69);
  TraceMsg(
    4,
    0,
    L"ReAclDNSRecords",
    2236,
    L"Got Domain DN '%ws' from DomainFlatName '%ws' or DomainNameDns '%ws'. Status %d.",
    v17,
    v16,
    v15,
    v14);
  LODWORD(v56) = v65;
  TraceMsg(4, 0, L"ReAclDNSRecords", 2238, L"Final DnsSuffixList contains %d suffixes", v56);
  TraceMsg(4, 0, L"ReAclDNSRecords", 2241, L"Getting SID for the CNO Account");
  std::wstring::wstring(v68);
  std::wstring::wstring(v71);
  SIDForResource = GetSIDForResource(v3, *a2, v68);
  if ( SIDForResource )
  {
    v18 = L"Failed to get the CNO's SID, error %d.";
    v19 = 2249;
LABEL_12:
    LODWORD(v57) = SIDForResource;
    TraceMsg(2, 0, L"ReAclDNSRecords", v19, v18, v57);
    std::wstring::_Tidy_deallocate(v71);
    std::wstring::_Tidy_deallocate(v68);
    std::wstring::_Tidy_deallocate(v72);
    std::wstring::_Tidy_deallocate(v67);
    goto LABEL_3;
  }
  TraceMsg(4, 0, L"ReAclDNSRecords", 2253, L"Getting DNSName for the CNO");
  SIDForResource = GetDnsNameForResource(*a2);
  if ( SIDForResource )
  {
    v18 = L"Failed to get the CNO's DNS Name, error %d.";
    v19 = 2259;
    goto LABEL_12;
  }
  TraceMsg(4, 0, L"ReAclDNSRecords", 2266, L"Getting list of all non-CNO netname resources");
  std::vector<_GUID>::vector<_GUID>(&v60);
  GetAllNonCoreNameResources(hCluster);
  TraceMsg(4, 0, L"ReAclDNSRecords", 2275, L"Checking/Fixing CNO permissions.");
  v20 = (_QWORD *)*v64;
  v21 = 4312;
  while ( v20 != v64 )
  {
    v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20 + 4);
    TraceMsg(4, 0, L"ReAclDNSRecords", 2279, L"CNO DNS - Looking for DNS record for suffix '%ws'.", v22);
    v62[0] = 0;
    DnsADOObject = GetDnsADOObject((_DWORD)v3, (unsigned int)v69, (int)v20 + 32, (unsigned int)v71, (__int64)v62);
    v24 = DnsADOObject;
    if ( DnsADOObject == 4312 || DnsADOObject == 2 )
    {
      TraceMsg(4, 0, L"ReAclDNSRecords", 2289, L"No record for for this suffix");
    }
    else
    {
      if ( DnsADOObject )
      {
        v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20 + 4);
        v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v71);
        LODWORD(v59) = v24;
        TraceMsg(
          2,
          0,
          L"ReAclDNSRecords",
          2295,
          L"Searching for DNS Permissions objects for Name '%ws' suffix '%ws', error %d.",
          v36,
          v35,
          v59);
        CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
        v37 = v60;
        if ( (_QWORD)v60 )
        {
LABEL_75:
          std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
            v37,
            *((_QWORD *)&v60 + 1));
          std::_Deallocate<16>(v60, 8 * ((v61 - (__int64)v60) >> 3));
          v61 = 0;
          v60 = 0;
        }
LABEL_76:
        v21 = v24;
        goto LABEL_80;
      }
      v25 = v62[0];
      if ( !v62[0] )
      {
        v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20 + 4);
        v33 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v71);
        TraceMsg(
          2,
          0,
          L"ReAclDNSRecords",
          2303,
          L"Searching for DNS Permissions objects for Name '%ws' suffix '%ws' returned success, but object was not populated",
          v33,
          v32);
        CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
        v34 = v60;
        if ( (_QWORD)v60 )
        {
LABEL_39:
          std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
            v34,
            *((_QWORD *)&v60 + 1));
          std::_Deallocate<16>(v60, 8 * ((v61 - (__int64)v60) >> 3));
          v60 = 0;
          v61 = 0;
        }
        goto LABEL_80;
      }
      TraceMsg(4, 0, L"ReAclDNSRecords", 2307, L"Attempting to grant CNO permissions");
      if ( (ClusterADObject::GiveFullControlForSid(v25, v68) & 0x1FFF0000) == 0x70000 )
        v26 = (unsigned __int16)ClusterADObject::GiveFullControlForSid(v25, v68);
      else
        v26 = ClusterADObject::GiveFullControlForSid(v25, v68);
      if ( v26 )
      {
        v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v20 + 4);
        v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v71);
        LODWORD(v59) = v26;
        TraceMsg(
          2,
          0,
          L"ReAclDNSRecords",
          2312,
          L"Found DNS Object for '%ws' suffix '%ws', but failed to give the CNO full control - error %d. Ignoring error and continuing.",
          v28,
          v27,
          v59);
      }
      else
      {
        TraceMsg(4, 0, L"ReAclDNSRecords", 2317, L"Successfully granted permissions");
      }
      v3 = v66;
    }
    CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
    v29 = (__int64 **)v20[2];
    if ( *((_BYTE *)v29 + 25) )
    {
      for ( i = v20[1]; !*(_BYTE *)(i + 25) && v20 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v20 = (_QWORD *)i;
      v20 = (_QWORD *)i;
    }
    else
    {
      v20 = (_QWORD *)v20[2];
      for ( j = *v29; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v20 = j;
    }
  }
  TraceMsg(4, 0, L"ReAclDNSRecords", 2323, L"Checking/Fixing VCO permissions.");
  for ( k = (struct _HRESOURCE **)v60; k != *((struct _HRESOURCE ***)&v60 + 1); k += 5 )
  {
    v39 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(k + 1);
    TraceMsg(4, 0, L"ReAclDNSRecords", 2328, L" Processing Network Name '%ws'.", v39);
    std::wstring::wstring(v73);
    std::wstring::wstring(v70);
    TraceMsg(4, 0, L"ReAclDNSRecords", 2331, L"Getting SID for the Network Name Account");
    v40 = GetSIDForResource(v3, *k, v73);
    if ( v40 )
    {
      LODWORD(v58) = v40;
      TraceMsg(
        2,
        0,
        L"ReAclDNSRecords",
        2336,
        L"Failed to get a Netname's SID, error %d. Moving on to next netname.",
        v58);
    }
    else
    {
      TraceMsg(4, 0, L"ReAclDNSRecords", 2341, L"Getting DnsName for the Network Name");
      DnsNameForResource = GetDnsNameForResource(*k);
      if ( DnsNameForResource )
      {
        LODWORD(v58) = DnsNameForResource;
        TraceMsg(
          2,
          0,
          L"ReAclDNSRecords",
          2346,
          L"Failed to get a Netname's DNS Name, error %d. Moving on to next netname.",
          v58);
      }
      else
      {
        v42 = (_QWORD *)*v64;
        while ( v42 != v64 )
        {
          v43 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42 + 4);
          TraceMsg(4, 0, L"ReAclDNSRecords", 2354, L"VCO DNS - Looking for DNS record for suffix '%ws'.", v43);
          v62[0] = 0;
          v44 = GetDnsADOObject((_DWORD)v3, (unsigned int)v69, (int)v42 + 32, (unsigned int)v70, (__int64)v62);
          v24 = v44;
          if ( v44 == 4312 || v44 == 2 )
          {
            TraceMsg(4, 0, L"ReAclDNSRecords", 2360, L"No record for for this suffix");
          }
          else
          {
            if ( v44 )
            {
              v54 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42 + 4);
              v55 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v70);
              LODWORD(v59) = v24;
              TraceMsg(
                2,
                0,
                L"ReAclDNSRecords",
                2366,
                L"Searching for DNS Permissions objects for Name '%ws' suffix '%ws', error %d.",
                v55,
                v54,
                v59);
              CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
              std::wstring::_Tidy_deallocate(v70);
              std::wstring::_Tidy_deallocate(v73);
              v37 = v60;
              if ( !(_QWORD)v60 )
                goto LABEL_76;
              goto LABEL_75;
            }
            v45 = v62[0];
            if ( !v62[0] )
            {
              v52 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42 + 4);
              v53 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v70);
              TraceMsg(
                2,
                0,
                L"ReAclDNSRecords",
                2374,
                L"Searching for DNS Permissions objects for Name '%ws' suffix '%ws' returned success, but object was not populated",
                v53,
                v52);
              CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
              std::wstring::_Tidy_deallocate(v70);
              std::wstring::_Tidy_deallocate(v73);
              v34 = v60;
              if ( !(_QWORD)v60 )
                goto LABEL_80;
              goto LABEL_39;
            }
            TraceMsg(4, 0, L"ReAclDNSRecords", 2378, L"Attempting to grant VCO permissions");
            ClusterADObject::GiveFullControlForSid(v45, v73);
            TraceMsg(4, 0, L"ReAclDNSRecords", 2388, L"Successfully granted permissions");
            TraceMsg(4, 0, L"ReAclDNSRecords", 2391, L"Attempting to grant CNO permissions");
            if ( (ClusterADObject::GiveFullControlForSid(v45, v68) & 0x1FFF0000) == 0x70000 )
              v46 = (unsigned __int16)ClusterADObject::GiveFullControlForSid(v45, v68);
            else
              v46 = ClusterADObject::GiveFullControlForSid(v45, v68);
            if ( v46 )
            {
              v47 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v42 + 4);
              v48 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v71);
              LODWORD(v59) = v46;
              TraceMsg(
                2,
                0,
                L"ReAclDNSRecords",
                2397,
                L"Found DNS Object for '%ws' suffix '%ws', but failed to give the CNO full control - error %d. Ignoring er"
                 "ror and continuing.",
                v48,
                v47,
                v59);
            }
            else
            {
              TraceMsg(4, 0, L"ReAclDNSRecords", 2402, L"Successfully granted permissions");
            }
            v3 = v66;
          }
          CTSmartObj<ClusterADObject *,CTSmartPtr_PolicyComplete<CTSmartPtr_PolicyNewMem>>::Release(v62);
          v49 = (__int64 **)v42[2];
          if ( *((_BYTE *)v49 + 25) )
          {
            for ( m = v42[1]; !*(_BYTE *)(m + 25) && v42 == *(_QWORD **)(m + 16); m = *(_QWORD *)(m + 8) )
              v42 = (_QWORD *)m;
            v42 = (_QWORD *)m;
          }
          else
          {
            v42 = (_QWORD *)v42[2];
            for ( n = *v49; !*((_BYTE *)n + 25); n = (__int64 *)*n )
              v42 = n;
          }
        }
      }
    }
    std::wstring::_Tidy_deallocate(v70);
    std::wstring::_Tidy_deallocate(v73);
  }
  TraceMsg(4, 0, L"ReAclDNSRecords", 2408, L"Complete");
  if ( (_QWORD)v60 )
  {
    std::_Destroy_range<std::allocator<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&int CloseClusterResource(_HRESOURCE *),0>,std::wstring>>>(
      v60,
      *((_QWORD *)&v60 + 1));
    std::_Deallocate<16>(v60, 8 * ((v61 - (__int64)v60) >> 3));
    v60 = 0;
    v61 = 0;
  }
  v21 = 0;
LABEL_80:
  std::wstring::_Tidy_deallocate(v71);
  std::wstring::_Tidy_deallocate(v68);
  std::wstring::_Tidy_deallocate(v72);
  std::wstring::_Tidy_deallocate(v67);
  std::wstring::_Tidy_deallocate(v69);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    &v64,
    &v64);
  return v21;
}

```

## disassembly

```asm
0x180075a58  mov     [rsp-8+arg_18], rbx
0x180075a5d  push    rbp
0x180075a5e  push    rsi
0x180075a5f  push    rdi
0x180075a60  push    r12
0x180075a62  push    r13
0x180075a64  push    r14
0x180075a66  push    r15
0x180075a68  lea     rbp, [rsp-80h]
0x180075a6d  sub     rsp, 180h
0x180075a74  mov     rax, cs:__security_cookie
0x180075a7b  xor     rax, rsp
0x180075a7e  mov     [rbp+0B0h+var_38], rax
0x180075a82  mov     r12, r8
0x180075a85  mov     [rbp+0B0h+var_120], r8
0x180075a89  mov     r14, rdx
0x180075a8c  mov     r15, rcx
0x180075a8f  lea     rax, ?CaseInsensitiveLessThan@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; CaseInsensitiveLessThan(std::wstring const &,std::wstring const &)
0x180075a96  mov     [rsp+1B0h+var_148], rax
0x180075a9b  lea     rdx, [rsp+1B0h+var_148]
0x180075aa0  lea     rcx, [rsp+1B0h+var_138]
0x180075aa5  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A_NAEBV12@0@ZV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@AEBQ6A_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@0@Z@Z; std::set<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>>::set<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>>(bool (*const &)(std::wstring const &,std::wstring const &))
0x180075aaa  nop
0x180075aab  lea     rcx, [rbp+0B0h+var_D8]
0x180075aaf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075ab4  nop
0x180075ab5  lea     rax, aGettingDnsSuff; "Getting DNS suffixes for the cluster"
0x180075abc  mov     [rsp+1B0h+var_190], rax
0x180075ac1  mov     r9d, 897h
0x180075ac7  lea     rdi, aReacldnsrecord; "ReAclDNSRecords"
0x180075ace  mov     r8, rdi
0x180075ad1  xor     edx, edx
0x180075ad3  lea     esi, [rdx+4]
0x180075ad6  mov     ecx, esi
0x180075ad8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075add  lea     rdx, [rsp+1B0h+var_138]
0x180075ae2  mov     rcx, r15
0x180075ae5  call    ?GetAdapterDnsSuffixesForCluster@@YAKPEAU_HCLUSTER@@AEAV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A_NAEBV12@0@ZV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; GetAdapterDnsSuffixesForCluster(_HCLUSTER *,std::set<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>> &)
0x180075aea  mov     ebx, eax
0x180075aec  xor     r13d, r13d
0x180075aef  mov     r8, rdi
0x180075af2  xor     edx, edx
0x180075af4  test    eax, eax
0x180075af6  jz      short loc_180075B35
0x180075af8  mov     dword ptr [rsp+1B0h+var_188], eax
0x180075afc  lea     rax, aFailedGettingT; "failed getting the DNS Suffix list for "...
0x180075b03  mov     [rsp+1B0h+var_190], rax
0x180075b08  mov     r9d, 89Fh
0x180075b0e  lea     ecx, [rsi-2]
0x180075b11  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075b16  nop
0x180075b17  lea     rcx, [rbp+0B0h+var_D8]
0x180075b1b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075b20  nop
0x180075b21  lea     rdx, [rbp+0B0h+var_130]
0x180075b25  lea     rcx, [rbp+0B0h+var_130]
0x180075b29  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x180075b2e  mov     eax, ebx
0x180075b30  jmp     loc_18007668A
0x180075b35  mov     eax, [rbp+0B0h+var_128]
0x180075b38  mov     dword ptr [rsp+1B0h+var_188], eax
0x180075b3c  lea     rax, aFoundDSuffixes; "Found %d suffixes"
0x180075b43  mov     [rsp+1B0h+var_190], rax
0x180075b48  mov     r9d, 8A3h
0x180075b4e  mov     ecx, esi
0x180075b50  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075b55  lea     rax, aGettingAdDomai; "Getting AD Domain name from our LDAP co"...
0x180075b5c  mov     [rsp+1B0h+var_190], rax
0x180075b61  mov     r9d, 8A7h
0x180075b67  mov     r8, rdi
0x180075b6a  xor     edx, edx
0x180075b6c  mov     ecx, esi
0x180075b6e  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075b73  lea     rdx, [rbp+0B0h+var_118]
0x180075b77  mov     rcx, [r12]
0x180075b7b  call    ?GetADDomainName@ClusterADLdap@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; ClusterADLdap::GetADDomainName(void)
0x180075b80  nop
0x180075b81  lea     rcx, [rbp+0B0h+var_78]
0x180075b85  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075b8a  nop
0x180075b8b  lea     r8, [rbp+0B0h+var_118]
0x180075b8f  lea     rdx, [rsp+1B0h+var_148]
0x180075b94  lea     rcx, [rsp+1B0h+var_138]
0x180075b99  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@P6A_NAEBV12@0@ZV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,bool (*)(std::wstring const &,std::wstring const &),std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x180075b9e  lea     rcx, [rbp+0B0h+var_118]
0x180075ba2  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_KQEB_W_K@Z; std::wstring::find_first_of(wchar_t const * const,unsigned __int64)
0x180075ba7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075bab  jz      short loc_180075BD4
0x180075bad  mov     r9, rax
0x180075bb0  lea     rdx, [rbp+0B0h+var_58]
0x180075bb4  lea     rcx, [rbp+0B0h+var_118]
0x180075bb8  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180075bbd  mov     rdx, rax
0x180075bc0  lea     rcx, [rbp+0B0h+var_78]
0x180075bc4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180075bc9  lea     rcx, [rbp+0B0h+var_58]
0x180075bcd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075bd2  jmp     short loc_180075BE1
0x180075bd4  lea     rdx, [rbp+0B0h+var_118]
0x180075bd8  lea     rcx, [rbp+0B0h+var_78]
0x180075bdc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180075be1  lea     r9, [rbp+0B0h+var_D8]
0x180075be5  lea     r8, [rbp+0B0h+var_78]
0x180075be9  lea     rdx, [rbp+0B0h+var_118]
0x180075bed  mov     rcx, [r12]
0x180075bf1  call    ?GetDomainDN@ClusterADLdap@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; ClusterADLdap::GetDomainDN(std::wstring const &,std::wstring const &,std::wstring &)
0x180075bf6  and     eax, 1FFF0000h
0x180075bfb  lea     r9, [rbp+0B0h+var_D8]
0x180075bff  lea     r8, [rbp+0B0h+var_78]
0x180075c03  lea     rdx, [rbp+0B0h+var_118]
0x180075c07  mov     rcx, [r12]
0x180075c0b  cmp     eax, 70000h
0x180075c10  jnz     short loc_180075C1C
0x180075c12  call    ?GetDomainDN@ClusterADLdap@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; ClusterADLdap::GetDomainDN(std::wstring const &,std::wstring const &,std::wstring &)
0x180075c17  movzx   esi, ax
0x180075c1a  jmp     short loc_180075C23
0x180075c1c  call    ?GetDomainDN@ClusterADLdap@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; ClusterADLdap::GetDomainDN(std::wstring const &,std::wstring const &,std::wstring &)
0x180075c21  mov     esi, eax
0x180075c23  lea     rcx, [rbp+0B0h+var_118]
0x180075c27  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075c2c  mov     rdi, rax
0x180075c2f  lea     rcx, [rbp+0B0h+var_78]
0x180075c33  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075c38  mov     rbx, rax
0x180075c3b  lea     rcx, [rbp+0B0h+var_D8]
0x180075c3f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075c44  mov     [rsp+1B0h+var_170], esi
0x180075c48  mov     [rsp+1B0h+var_178], rdi
0x180075c4d  mov     [rsp+1B0h+var_180], rbx
0x180075c52  mov     [rsp+1B0h+var_188], rax
0x180075c57  lea     rax, aGotDomainDnWsF; "Got Domain DN '%ws' from DomainFlatName"...
0x180075c5e  mov     [rsp+1B0h+var_190], rax
0x180075c63  mov     r9d, 8BCh
0x180075c69  lea     rdi, aReacldnsrecord; "ReAclDNSRecords"
0x180075c70  mov     r8, rdi
0x180075c73  xor     edx, edx
0x180075c75  lea     esi, [rdx+4]
0x180075c78  mov     ecx, esi
0x180075c7a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075c7f  mov     eax, [rbp+0B0h+var_128]
0x180075c82  mov     dword ptr [rsp+1B0h+var_188], eax
0x180075c86  lea     rax, aFinalDnssuffix; "Final DnsSuffixList contains %d suffixe"...
0x180075c8d  mov     [rsp+1B0h+var_190], rax
0x180075c92  mov     r9d, 8BEh
0x180075c98  mov     r8, rdi
0x180075c9b  xor     edx, edx
0x180075c9d  mov     ecx, esi
0x180075c9f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075ca4  lea     rax, aGettingSidForT_0; "Getting SID for the CNO Account"
0x180075cab  mov     [rsp+1B0h+var_190], rax
0x180075cb0  mov     r9d, 8C1h
0x180075cb6  mov     r8, rdi
0x180075cb9  xor     edx, edx
0x180075cbb  mov     ecx, esi
0x180075cbd  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075cc2  lea     rcx, [rbp+0B0h+var_F8]
0x180075cc6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075ccb  nop
0x180075ccc  lea     rcx, [rbp+0B0h+var_98]
0x180075cd0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180075cd5  nop
0x180075cd6  lea     r8, [rbp+0B0h+var_F8]
0x180075cda  mov     rdx, [r14]
0x180075cdd  mov     rcx, r12
0x180075ce0  call    ?GetSIDForResource@@YAKAEAV?$CAutoMemPtr@VClusterADLdap@@@@PEAU_HRESOURCE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetSIDForResource(CAutoMemPtr<ClusterADLdap> &,_HRESOURCE *,std::wstring &)
0x180075ce5  mov     ebx, eax
0x180075ce7  mov     r8, rdi
0x180075cea  xor     edx, edx
0x180075cec  test    eax, eax
0x180075cee  jz      short loc_180075D3D
0x180075cf0  lea     rax, aFailedToGetThe_1; "Failed to get the CNO's SID, error %d."
0x180075cf7  mov     r9d, 8C9h
0x180075cfd  mov     dword ptr [rsp+1B0h+var_188], ebx
0x180075d01  mov     [rsp+1B0h+var_190], rax
0x180075d06  mov     ecx, 2
0x180075d0b  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075d10  nop
0x180075d11  lea     rcx, [rbp+0B0h+var_98]
0x180075d15  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075d1a  nop
0x180075d1b  lea     rcx, [rbp+0B0h+var_F8]
0x180075d1f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075d24  nop
0x180075d25  lea     rcx, [rbp+0B0h+var_78]
0x180075d29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075d2e  nop
0x180075d2f  lea     rcx, [rbp+0B0h+var_118]
0x180075d33  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180075d38  jmp     loc_180075B17
0x180075d3d  lea     rax, aGettingDnsname; "Getting DNSName for the CNO"
0x180075d44  mov     [rsp+1B0h+var_190], rax
0x180075d49  mov     r9d, 8CDh
0x180075d4f  mov     ecx, esi
0x180075d51  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075d56  lea     rdx, [rbp+0B0h+var_98]
0x180075d5a  mov     rcx, [r14]; struct _HRESOURCE *
0x180075d5d  call    ?GetDnsNameForResource@@YAKPEAU_HRESOURCE@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetDnsNameForResource(_HRESOURCE *,std::wstring &)
0x180075d62  mov     ebx, eax
0x180075d64  mov     r8, rdi
0x180075d67  xor     edx, edx
0x180075d69  test    eax, eax
0x180075d6b  jz      short loc_180075D7C
0x180075d6d  lea     rax, aFailedToGetThe_0; "Failed to get the CNO's DNS Name, error"...
0x180075d74  mov     r9d, 8D3h
0x180075d7a  jmp     short loc_180075CFD
0x180075d7c  lea     rax, aGettingListOfA; "Getting list of all non-CNO netname res"...
0x180075d83  mov     [rsp+1B0h+var_190], rax
0x180075d88  mov     r9d, 8DAh
0x180075d8e  mov     ecx, esi
0x180075d90  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075d95  lea     rcx, [rsp+1B0h+var_160]
0x180075d9a  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180075d9f  nop
0x180075da0  lea     r8, [rsp+1B0h+var_160]
0x180075da5  xor     edx, edx
0x180075da7  mov     rcx, r15; hCluster
0x180075daa  call    ?GetAllNonCoreNameResources@@YAKPEAU_HCLUSTER@@HAEAV?$vector@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@U?$AutoHandle@PEAU_HRESOURCE@@H$1?CloseClusterResource@@YAHPEAU1@@Z$0A@@cxl@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@@Z; GetAllNonCoreNameResources(_HCLUSTER *,int,std::vector<std::pair<cxl::AutoHandle<_HRESOURCE *,int,&CloseClusterResource(_HRESOURCE *),0>,std::wstring>> &)
0x180075daf  lea     rax, aCheckingFixing_0; "Checking/Fixing CNO permissions."
0x180075db6  mov     [rsp+1B0h+var_190], rax
0x180075dbb  mov     r9d, 8E3h
0x180075dc1  mov     r8, rdi
0x180075dc4  xor     edx, edx
0x180075dc6  mov     ecx, esi
0x180075dc8  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075dcd  mov     rbx, [rbp+0B0h+var_130]
0x180075dd1  mov     rbx, [rbx]
0x180075dd4  mov     r14d, 2
0x180075dda  mov     r15d, 10D8h
0x180075de0  cmp     rbx, [rbp+0B0h+var_130]
0x180075de4  jz      loc_180076104
0x180075dea  lea     rsi, [rbx+20h]
0x180075dee  mov     rcx, rsi
0x180075df1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075df6  mov     [rsp+1B0h+var_188], rax
0x180075dfb  lea     rax, aCnoDnsLookingF; "CNO DNS - Looking for DNS record for su"...
0x180075e02  mov     [rsp+1B0h+var_190], rax
0x180075e07  mov     r9d, 8E7h
0x180075e0d  mov     r8, rdi
0x180075e10  xor     edx, edx
0x180075e12  lea     ecx, [rdx+4]
0x180075e15  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075e1a  mov     [rsp+1B0h+var_148], r13
0x180075e1f  lea     rax, [rsp+1B0h+var_148]
0x180075e24  mov     [rsp+1B0h+var_190], rax
0x180075e29  lea     r9, [rbp+0B0h+var_98]
0x180075e2d  mov     r8, rsi
0x180075e30  lea     rdx, [rbp+0B0h+var_D8]
0x180075e34  mov     rcx, r12
0x180075e37  call    ?GetDnsADOObject@@YAKAEAV?$CAutoMemPtr@VClusterADLdap@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@11AEAV?$CAutoMemPtr@VClusterADObject@@@@@Z; GetDnsADOObject(CAutoMemPtr<ClusterADLdap> &,std::wstring const &,std::wstring const &,std::wstring const &,CAutoMemPtr<ClusterADObject> &)
0x180075e3c  mov     edi, eax
0x180075e3e  cmp     eax, r15d
0x180075e41  jz      loc_180075F3F
0x180075e47  cmp     eax, r14d
0x180075e4a  jz      loc_180075F3F
0x180075e50  test    eax, eax
0x180075e52  jnz     loc_180076065
0x180075e58  mov     rdi, [rsp+1B0h+var_148]
0x180075e5d  test    rdi, rdi
0x180075e60  jz      loc_180075FC1
0x180075e66  lea     rax, aAttemptingToGr; "Attempting to grant CNO permissions"
0x180075e6d  mov     [rsp+1B0h+var_190], rax
0x180075e72  mov     r9d, 903h
0x180075e78  lea     r8, aReacldnsrecord; "ReAclDNSRecords"
0x180075e7f  xor     edx, edx
0x180075e81  lea     ecx, [rdx+4]
0x180075e84  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075e89  lea     rdx, [rbp+0B0h+var_F8]
0x180075e8d  mov     rcx, rdi
0x180075e90  call    ?GiveFullControlForSid@ClusterADObject@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusterADObject::GiveFullControlForSid(std::wstring const &)
0x180075e95  and     eax, 1FFF0000h
0x180075e9a  lea     rdx, [rbp+0B0h+var_F8]
0x180075e9e  mov     rcx, rdi
0x180075ea1  cmp     eax, 70000h
0x180075ea6  jnz     short loc_180075EB3
0x180075ea8  call    ?GiveFullControlForSid@ClusterADObject@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusterADObject::GiveFullControlForSid(std::wstring const &)
0x180075ead  movzx   r12d, ax
0x180075eb1  jmp     short loc_180075EBB
0x180075eb3  call    ?GiveFullControlForSid@ClusterADObject@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusterADObject::GiveFullControlForSid(std::wstring const &)
0x180075eb8  mov     r12d, eax
0x180075ebb  test    r12d, r12d
0x180075ebe  jz      short loc_180075F10
0x180075ec0  mov     rcx, rsi
0x180075ec3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075ec8  mov     rdi, rax
0x180075ecb  lea     rcx, [rbp+0B0h+var_98]
0x180075ecf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180075ed4  mov     dword ptr [rsp+1B0h+var_178], r12d
0x180075ed9  mov     [rsp+1B0h+var_180], rdi
0x180075ede  mov     [rsp+1B0h+var_188], rax
0x180075ee3  lea     rax, aFoundDnsObject; "Found DNS Object for '%ws' suffix '%ws'"...
0x180075eea  mov     [rsp+1B0h+var_190], rax
0x180075eef  mov     r9d, 908h
0x180075ef5  lea     rdi, aReacldnsrecord; "ReAclDNSRecords"
0x180075efc  mov     r8, rdi
0x180075eff  xor     edx, edx
0x180075f01  mov     ecx, r14d
0x180075f04  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180075f09  mov     esi, 4
0x180075f0e  jmp     short loc_180075F39
0x180075f10  lea     rax, aSuccessfullyGr; "Successfully granted permissions"
  ... truncated ...
```
