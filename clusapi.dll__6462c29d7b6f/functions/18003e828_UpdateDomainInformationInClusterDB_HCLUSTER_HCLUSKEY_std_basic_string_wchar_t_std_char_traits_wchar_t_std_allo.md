# UpdateDomainInformationInClusterDB(_HCLUSTER *,HCLUSKEY__ *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18003e828`
- end: `0x18003f0cf`
- name: `?UpdateDomainInformationInClusterDB@@YAKPEAU_HCLUSTER@@PEAUHCLUSKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W333@Z`
- size: `2215`
- prototype: `__int64 __usercall@<rax>(HCLUSTER hCluster@<rcx>, HKEY hKey@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003359c`
- `0x18003f0d8`

## callees

- `0x180002f50`
- `0x180014638`
- `0x18001cad0`
- `0x18001cc2c`
- `0x18001cc7c`
- `0x180028f30`
- `0x180029538`
- `0x180029578`
- `0x18003049c`
- `0x180032638`
- `0x1800331c0`
- `0x18003c320`
- `0x18003e828`
- `0x180064d10`
- `0x180064f20`
- `0x18006f910`
- `0x1800948dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003ead9`
- `ntdll!RtlNtStatusToDosError` at `0x18003eb53`
- `ntdll!RtlNtStatusToDosError` at `0x18003ead9`
- `ntdll!RtlNtStatusToDosError` at `0x18003eb53`
- `wkscli!NetUseAdd` at `0x18003e9c6`
- `wkscli!NetUseAdd` at `0x18003e9c6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003eb1f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18003eb1f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003eaa5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18003eaa5`

## string_xrefs

- `0x18003e8ba`: `UpdateDomainInformationInClusterDB`
- `0x18003e9f5`: `UpdateDomainInformationInClusterDB`
- `0x18003eac7`: `UpdateDomainInformationInClusterDB`
- `0x18003eb41`: `UpdateDomainInformationInClusterDB`
- `0x18003ebfd`: `UpdateDomainInformationInClusterDB`
- `0x18003ecb8`: `UpdateDomainInformationInClusterDB`
- `0x18003ed8c`: `UpdateDomainInformationInClusterDB`
- `0x18003eea1`: `UpdateDomainInformationInClusterDB`
- `0x18003ef9b`: `UpdateDomainInformationInClusterDB`
- `0x18003f02c`: `UpdateDomainInformationInClusterDB`
- `0x18003eab5`: `Error in LsaOpenPolicy %d`
- `0x18003f01a`: `DnsDomain already exists. Not overiding it`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall UpdateDomainInformationInClusterDB(
        HCLUSTER hCluster,
        HKEY hKey,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rbx
  __int64 v15; // rax
  DWORD v16; // ebx
  __int64 v17; // rax
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  ULONG v20; // ebx
  NTSTATUS v21; // eax
  NTSTATUS v22; // ebx
  ULONG v23; // ebx
  int v24; // ebx
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  int v30; // ebx
  int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // ebx
  int v34; // ebx
  int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // ebx
  LONG v38; // eax
  int v39; // ebx
  int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // ebx
  wchar_t *v43; // [rsp+28h] [rbp-1F0h]
  wchar_t *v44; // [rsp+28h] [rbp-1F0h]
  wchar_t *v45; // [rsp+28h] [rbp-1F0h]
  wchar_t *v46; // [rsp+28h] [rbp-1F0h]
  wchar_t *v47; // [rsp+28h] [rbp-1F0h]
  bool v48; // [rsp+40h] [rbp-1D8h] BYREF
  DWORD parm_err; // [rsp+44h] [rbp-1D4h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-1D0h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-1C8h] BYREF
  _QWORD v52[2]; // [rsp+58h] [rbp-1C0h] BYREF
  char v53; // [rsp+68h] [rbp-1B0h]
  DWORD dwValueType; // [rsp+70h] [rbp-1A8h] BYREF
  _LSA_UNICODE_STRING SystemName; // [rsp+78h] [rbp-1A0h] BYREF
  BYTE buf[8]; // [rsp+88h] [rbp-190h] BYREF
  __int64 v57; // [rsp+90h] [rbp-188h]
  __int64 v58; // [rsp+98h] [rbp-180h]
  int v59; // [rsp+A0h] [rbp-178h]
  int v60; // [rsp+A4h] [rbp-174h]
  __int64 v61; // [rsp+A8h] [rbp-170h]
  __int64 v62; // [rsp+B0h] [rbp-168h]
  __int64 v63; // [rsp+B8h] [rbp-160h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-148h] BYREF
  __int128 v65; // [rsp+100h] [rbp-118h] BYREF
  __int128 v66; // [rsp+110h] [rbp-108h]
  _BYTE v67[16]; // [rsp+120h] [rbp-F8h] BYREF
  int v68; // [rsp+130h] [rbp-E8h]
  _BYTE v69[16]; // [rsp+140h] [rbp-D8h] BYREF
  int v70; // [rsp+150h] [rbp-C8h]
  _BYTE v71[16]; // [rsp+160h] [rbp-B8h] BYREF
  int v72; // [rsp+170h] [rbp-A8h]
  _BYTE v73[16]; // [rsp+180h] [rbp-98h] BYREF
  int v74; // [rsp+190h] [rbp-88h]
  _BYTE v75[32]; // [rsp+1A0h] [rbp-78h] BYREF
  __int128 v76; // [rsp+1C0h] [rbp-58h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
    return 6;
  v48 = 0;
  v12 = IsPreferCNODomainPresent(hCluster, a4, &v48);
  v13 = v12;
  if ( v12 )
  {
    TraceMsg(2, 0, L"UpdateDomainInformationInClusterDB", 9323, L"IsPreferCNODomainPresent Failed with error %d.", v12);
    return v13;
  }
  if ( v48 )
  {
    v14 = (void *)std::wstring::wstring(v75, L"\\IPC$");
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
    v15 = std::wstring::_Insert<wchar_t>(v14);
    v65 = 0;
    v66 = 0;
    v65 = *(_OWORD *)v15;
    v66 = *(_OWORD *)(v15 + 16);
    *(_QWORD *)(v15 + 16) = 0;
    *(_QWORD *)(v15 + 24) = 7;
    *(_WORD *)v15 = 0;
    std::wstring::_Tidy_deallocate(v75);
    v59 = 0;
    v61 = 0;
    *(_QWORD *)buf = 0;
    v57 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v65);
    v60 = 3;
    v62 = a6;
    v63 = a5;
    v58 = a7;
    parm_err = 0;
    Buffer = 0;
    v16 = NetUseAdd(0, 2u, buf, &parm_err);
    if ( v16 )
    {
      v17 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
      TraceMsg(
        2,
        0,
        L"UpdateDomainInformationInClusterDB",
        9353,
        L"NetUseAdd to DC %ws failed with error %d.",
        v17,
        v16);
      std::wstring::_Tidy_deallocate(&v65);
      return v16;
    }
    v52[0] = &v65;
    v52[1] = &Buffer;
    v53 = 0;
    *(_DWORD *)(&SystemName.MaximumLength + 1) = 0;
    SystemName.Buffer = (PWSTR)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
    SystemName.Length = 2 * *(_WORD *)(a3 + 16);
    SystemName.MaximumLength = SystemName.Length + 2;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    PolicyHandle = 0;
    cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
    v18 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 1u, &PolicyHandle);
    v19 = v18;
    if ( v18 )
    {
      TraceMsg(2, 0, L"UpdateDomainInformationInClusterDB", 9384, L"Error in LsaOpenPolicy %d", v18);
      v20 = RtlNtStatusToDosError(v19);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v20;
    }
    v21 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    v22 = v21;
    if ( v21 )
    {
      TraceMsg(2, 0, L"UpdateDomainInformationInClusterDB", 9391, L"Error in LsaQueryInformationPolicy %d", v21);
      v23 = RtlNtStatusToDosError(v22);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v23;
    }
    std::wstring::wstring(v69, *((_QWORD *)Buffer + 1), (unsigned __int64)*(unsigned __int16 *)Buffer >> 1);
    v24 = 2 * v70 + 2;
    v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v69);
    v26 = ClusterRegSetValueEx((int)hKey, (int)L"DomainNameFlat", 1, v25, v24, 0);
    v27 = v26;
    if ( v26 )
    {
      LODWORD(v43) = v26;
      TraceMsg(
        2,
        0,
        L"UpdateDomainInformationInClusterDB",
        9404,
        L"Failed to set DomainNameFlat in clusdb, error %d.",
        v43);
      std::wstring::_Tidy_deallocate(v69);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v27;
    }
    std::wstring::wstring(v67, *((_QWORD *)Buffer + 3), (unsigned __int64)*((unsigned __int16 *)Buffer + 8) >> 1);
    v28 = ClusterRegSetValueEx((int)hKey, (int)L"DomainNameDns", 1, *((_QWORD *)Buffer + 3), 2 * v68 + 2, 0);
    v29 = v28;
    if ( v28 )
    {
      LODWORD(v44) = v28;
      TraceMsg(
        2,
        0,
        L"UpdateDomainInformationInClusterDB",
        9416,
        L"Failed to set DomainNameDns in clusdb, error %d.",
        v44);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v29;
    }
    std::wstring::wstring(v71, *((_QWORD *)Buffer + 5), (unsigned __int64)*((unsigned __int16 *)Buffer + 16) >> 1);
    v30 = 2 * v72 + 2;
    v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v71);
    v32 = ClusterRegSetValueEx((int)hKey, (int)L"DomainForestName", 1, v31, v30, 0);
    v33 = v32;
    if ( v32 )
    {
      LODWORD(v45) = v32;
      TraceMsg(
        2,
        0,
        L"UpdateDomainInformationInClusterDB",
        9428,
        L"Failed to set DomainForestName in clusdb, error %d.",
        v45);
      std::wstring::_Tidy_deallocate(v71);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v33;
    }
    v76 = *((_OWORD *)Buffer + 3);
    std::string::string(v75, "B");
    cxl::Guid::ToString((cxl::Guid *)&v76);
    std::string::_Tidy_deallocate(v75);
    v34 = 2 * v74 + 2;
    v35 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v73);
    v36 = ClusterRegSetValueEx((int)hKey, (int)L"DomainGuid", 1, v35, v34, 0);
    v37 = v36;
    if ( v36 )
    {
      LODWORD(v46) = v36;
      TraceMsg(2, 0, L"UpdateDomainInformationInClusterDB", 9440, L"Failed to set DomainGuid in clusdb, error %d.", v46);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::_Tidy_deallocate(v71);
      std::wstring::_Tidy_deallocate(v67);
      std::wstring::_Tidy_deallocate(v69);
      cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
      v53 = 1;
      lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
      std::wstring::_Tidy_deallocate(&v65);
      return v37;
    }
    dwValueType = 0;
    v38 = ClusterRegQueryValue(hKey, L"DnsDomain", &dwValueType, 0, 0);
    if ( v38 == 2 )
    {
      v39 = 2 * v68 + 2;
      v40 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v67);
      v41 = ClusterRegSetValueEx((int)hKey, (int)L"DnsDomain", 1, v40, v39, 0);
      v42 = v41;
      if ( v41 )
      {
        LODWORD(v47) = v41;
        TraceMsg(
          2,
          0,
          L"UpdateDomainInformationInClusterDB",
          9455,
          L"Failed to set dns domain in clusdb, error %d.",
          v47);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::_Tidy_deallocate(v71);
        std::wstring::_Tidy_deallocate(v67);
        std::wstring::_Tidy_deallocate(v69);
        cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
        v53 = 1;
        lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
        std::wstring::_Tidy_deallocate(&v65);
        return v42;
      }
    }
    else if ( v38 == 234 )
    {
      TraceMsg(4, 0, L"UpdateDomainInformationInClusterDB", 9462, L"DnsDomain already exists. Not overiding it");
    }
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::_Tidy_deallocate(v71);
    std::wstring::_Tidy_deallocate(v67);
    std::wstring::_Tidy_deallocate(v69);
    cxl::AutoHandle<void *,long,&long LsaClose(void *),0>::Close(&PolicyHandle);
    v53 = 1;
    lambda_da204913539f8ac3951b708370ebab48_::operator()(v52);
    std::wstring::_Tidy_deallocate(&v65);
  }
  return 0;
}

```

## disassembly

```asm
0x18003e828  push    rbx
0x18003e82a  push    rsi
0x18003e82b  push    rdi
0x18003e82c  push    r12
0x18003e82e  push    r13
0x18003e830  push    r14
0x18003e832  push    r15
0x18003e834  sub     rsp, 1E0h
0x18003e83b  mov     rax, cs:__security_cookie
0x18003e842  xor     rax, rsp
0x18003e845  mov     [rsp+218h+var_48], rax
0x18003e84d  mov     rdi, r9
0x18003e850  mov     r14, r8
0x18003e853  mov     rsi, rdx
0x18003e856  mov     rbx, rcx
0x18003e859  mov     r15, [rsp+218h+arg_20]
0x18003e861  mov     r12, [rsp+218h+arg_28]
0x18003e869  mov     r13, [rsp+218h+arg_30]
0x18003e871  mov     rdx, rcx
0x18003e874  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18003e879  test    al, al
0x18003e87b  jnz     short loc_18003E887
0x18003e87d  mov     eax, 6
0x18003e882  jmp     loc_18003F0A6
0x18003e887  mov     [rsp+218h+var_1D8], 0
0x18003e88c  lea     r8, [rsp+218h+var_1D8]; bool *
0x18003e891  mov     rdx, rdi; wchar_t *
0x18003e894  mov     rcx, rbx; hCluster
0x18003e897  call    ?IsPreferCNODomainPresent@@YAKPEAU_HCLUSTER@@PEB_WAEA_N@Z; IsPreferCNODomainPresent(_HCLUSTER *,wchar_t const *,bool &)
0x18003e89c  mov     ebx, eax
0x18003e89e  xor     edi, edi
0x18003e8a0  test    eax, eax
0x18003e8a2  jz      short loc_18003E8D2
0x18003e8a4  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003e8a8  lea     rax, aIsprefercnodom_1; "IsPreferCNODomainPresent Failed with er"...
0x18003e8af  mov     [rsp+218h+lpcbData], rax
0x18003e8b4  mov     r9d, 246Bh
0x18003e8ba  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003e8c1  xor     edx, edx
0x18003e8c3  lea     ecx, [rdi+2]
0x18003e8c6  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003e8cb  mov     eax, ebx
0x18003e8cd  jmp     loc_18003F0A6
0x18003e8d2  cmp     [rsp+218h+var_1D8], dil
0x18003e8d7  jz      loc_18003F09E
0x18003e8dd  lea     rdx, aIpc; "\\IPC$"
0x18003e8e4  lea     rcx, [rsp+218h+var_78]
0x18003e8ec  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003e8f1  mov     rbx, rax
0x18003e8f4  mov     rcx, r14
0x18003e8f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e8fc  mov     r9, [r14+10h]
0x18003e900  mov     r8, rax
0x18003e903  mov     rcx, rbx; Src
0x18003e906  call    ??$_Insert@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KQEB_W0@Z; std::wstring::_Insert<wchar_t>(unsigned __int64,wchar_t const * const,unsigned __int64)
0x18003e90b  xorps   xmm0, xmm0
0x18003e90e  movups  [rsp+218h+var_118], xmm0
0x18003e916  xorps   xmm1, xmm1
0x18003e919  movdqu  [rsp+218h+var_108], xmm1
0x18003e922  movups  xmm0, xmmword ptr [rax]
0x18003e925  movups  [rsp+218h+var_118], xmm0
0x18003e92d  movups  xmm1, xmmword ptr [rax+10h]
0x18003e931  movups  [rsp+218h+var_108], xmm1
0x18003e939  mov     [rax+10h], rdi
0x18003e93d  mov     qword ptr [rax+18h], 7
0x18003e945  mov     [rax], di
0x18003e948  lea     rcx, [rsp+218h+var_78]
0x18003e950  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003e955  mov     [rsp+218h+var_178], edi
0x18003e95c  mov     [rsp+218h+var_170], rdi
0x18003e964  mov     qword ptr [rsp+218h+buf], rdi
0x18003e96c  lea     rcx, [rsp+218h+var_118]
0x18003e974  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e979  mov     [rsp+218h+var_188], rax
0x18003e981  mov     [rsp+218h+var_174], 3
0x18003e98c  mov     [rsp+218h+var_168], r12
0x18003e994  mov     [rsp+218h+var_160], r15
0x18003e99c  mov     [rsp+218h+var_180], r13
0x18003e9a4  xor     r15d, r15d
0x18003e9a7  mov     [rsp+218h+parm_err], r15d
0x18003e9ac  mov     [rsp+218h+Buffer], r15
0x18003e9b1  lea     r9, [rsp+218h+parm_err]; parm_err
0x18003e9b6  lea     r8, [rsp+218h+buf]; buf
0x18003e9be  lea     edi, [r15+2]
0x18003e9c2  mov     edx, edi; LevelFlags
0x18003e9c4  xor     ecx, ecx; servername
0x18003e9c6  call    cs:__imp_NetUseAdd
0x18003e9cc  mov     ebx, eax
0x18003e9ce  test    eax, eax
0x18003e9d0  jz      short loc_18003EA1A
0x18003e9d2  mov     rcx, r14
0x18003e9d5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003e9da  mov     [rsp+218h+var_1E8], ebx
0x18003e9de  mov     [rsp+218h+var_1F0], rax
0x18003e9e3  lea     rax, aNetuseaddToDcW; "NetUseAdd to DC %ws failed with error %"...
0x18003e9ea  mov     [rsp+218h+lpcbData], rax
0x18003e9ef  mov     r9d, 2489h
0x18003e9f5  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003e9fc  xor     edx, edx
0x18003e9fe  mov     ecx, edi
0x18003ea00  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003ea05  nop
0x18003ea06  lea     rcx, [rsp+218h+var_118]
0x18003ea0e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ea13  mov     eax, ebx
0x18003ea15  jmp     loc_18003F0A6
0x18003ea1a  lea     rax, [rsp+218h+var_118]
0x18003ea22  mov     [rsp+218h+var_1C0], rax
0x18003ea27  lea     rax, [rsp+218h+Buffer]
0x18003ea2c  mov     [rsp+218h+var_1B8], rax
0x18003ea31  mov     [rsp+218h+var_1B0], r15b
0x18003ea36  mov     dword ptr [rsp+218h+SystemName+4], r15d
0x18003ea3b  mov     rcx, r14
0x18003ea3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ea43  mov     [rsp+218h+SystemName.Buffer], rax
0x18003ea4b  movzx   eax, word ptr [r14+10h]
0x18003ea50  add     ax, ax
0x18003ea53  mov     [rsp+218h+SystemName.Length], ax
0x18003ea58  add     ax, di
0x18003ea5b  mov     [rsp+218h+SystemName.MaximumLength], ax
0x18003ea60  xorps   xmm0, xmm0
0x18003ea63  movups  xmmword ptr [rsp+218h+ObjectAttributes.Length], xmm0
0x18003ea6b  movups  xmmword ptr [rsp+218h+ObjectAttributes.ObjectName], xmm0
0x18003ea73  movups  xmmword ptr [rsp+218h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003ea7b  mov     [rsp+218h+PolicyHandle], r15
0x18003ea80  lea     rcx, [rsp+218h+PolicyHandle]
0x18003ea85  call    ?Close@?$AutoHandle@PEAXJ$1?LsaClose@@YAJPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,long,&LsaClose(void *),0>::Close(void)
0x18003ea8a  lea     r9, [rsp+218h+PolicyHandle]; PolicyHandle
0x18003ea8f  mov     r14d, 1
0x18003ea95  mov     r8d, r14d; DesiredAccess
0x18003ea98  lea     rdx, [rsp+218h+ObjectAttributes]; ObjectAttributes
0x18003eaa0  lea     rcx, [rsp+218h+SystemName]; SystemName
0x18003eaa5  call    cs:__imp_LsaOpenPolicy
0x18003eaab  mov     ebx, eax
0x18003eaad  test    eax, eax
0x18003eaaf  jz      short loc_18003EB10
0x18003eab1  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003eab5  lea     rax, aErrorInLsaopen; "Error in LsaOpenPolicy %d"
0x18003eabc  mov     [rsp+218h+lpcbData], rax
0x18003eac1  mov     r9d, 24A8h
0x18003eac7  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003eace  xor     edx, edx
0x18003ead0  mov     ecx, edi
0x18003ead2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003ead7  mov     ecx, ebx; Status
0x18003ead9  call    cs:__imp_RtlNtStatusToDosError
0x18003eadf  mov     ebx, eax
0x18003eae1  lea     rcx, [rsp+218h+PolicyHandle]
0x18003eae6  call    ?Close@?$AutoHandle@PEAXJ$1?LsaClose@@YAJPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,long,&LsaClose(void *),0>::Close(void)
0x18003eaeb  nop
0x18003eaec  mov     [rsp+218h+var_1B0], r14b
0x18003eaf1  lea     rcx, [rsp+218h+var_1C0]
0x18003eaf6  call    _lambda_da204913539f8ac3951b708370ebab48___operator__
0x18003eafb  nop
0x18003eafc  lea     rcx, [rsp+218h+var_118]
0x18003eb04  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eb09  mov     eax, ebx
0x18003eb0b  jmp     loc_18003F0A6
0x18003eb10  lea     r8, [rsp+218h+Buffer]; Buffer
0x18003eb15  mov     edx, 0Ch; InformationClass
0x18003eb1a  mov     rcx, [rsp+218h+PolicyHandle]; PolicyHandle
0x18003eb1f  call    cs:__imp_LsaQueryInformationPolicy
0x18003eb25  mov     ebx, eax
0x18003eb27  test    eax, eax
0x18003eb29  jz      short loc_18003EB8A
0x18003eb2b  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003eb2f  lea     rax, aErrorInLsaquer; "Error in LsaQueryInformationPolicy %d"
0x18003eb36  mov     [rsp+218h+lpcbData], rax
0x18003eb3b  mov     r9d, 24AFh
0x18003eb41  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003eb48  xor     edx, edx
0x18003eb4a  mov     ecx, edi
0x18003eb4c  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003eb51  mov     ecx, ebx; Status
0x18003eb53  call    cs:__imp_RtlNtStatusToDosError
0x18003eb59  mov     ebx, eax
0x18003eb5b  lea     rcx, [rsp+218h+PolicyHandle]
0x18003eb60  call    ?Close@?$AutoHandle@PEAXJ$1?LsaClose@@YAJPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,long,&LsaClose(void *),0>::Close(void)
0x18003eb65  nop
0x18003eb66  mov     [rsp+218h+var_1B0], r14b
0x18003eb6b  lea     rcx, [rsp+218h+var_1C0]
0x18003eb70  call    _lambda_da204913539f8ac3951b708370ebab48___operator__
0x18003eb75  nop
0x18003eb76  lea     rcx, [rsp+218h+var_118]
0x18003eb7e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eb83  mov     eax, ebx
0x18003eb85  jmp     loc_18003F0A6
0x18003eb8a  mov     rdx, [rsp+218h+Buffer]
0x18003eb8f  movzx   r8d, word ptr [rdx]
0x18003eb93  shr     r8, 1
0x18003eb96  mov     rdx, [rdx+8]
0x18003eb9a  lea     rcx, [rsp+218h+var_D8]
0x18003eba2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x18003eba7  nop
0x18003eba8  mov     eax, [rsp+218h+var_C8]
0x18003ebaf  lea     ebx, ds:2[rax*2]
0x18003ebb6  lea     rcx, [rsp+218h+var_D8]
0x18003ebbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ebc3  mov     r9, rax; int
0x18003ebc6  mov     [rsp+218h+var_1F0], r15; wchar_t *
0x18003ebcb  mov     dword ptr [rsp+218h+lpcbData], ebx; int
0x18003ebcf  mov     r8d, r14d; int
0x18003ebd2  lea     rdx, aDomainnameflat; "DomainNameFlat"
0x18003ebd9  mov     rcx, rsi; int
0x18003ebdc  call    ClusterRegSetValueEx
0x18003ebe1  mov     ebx, eax
0x18003ebe3  test    eax, eax
0x18003ebe5  jz      short loc_18003EC4B
0x18003ebe7  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003ebeb  lea     rax, aFailedToSetDom_1; "Failed to set DomainNameFlat in clusdb,"...
0x18003ebf2  mov     [rsp+218h+lpcbData], rax
0x18003ebf7  mov     r9d, 24BCh
0x18003ebfd  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003ec04  xor     edx, edx
0x18003ec06  mov     ecx, edi
0x18003ec08  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003ec0d  nop
0x18003ec0e  lea     rcx, [rsp+218h+var_D8]
0x18003ec16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ec1b  nop
0x18003ec1c  lea     rcx, [rsp+218h+PolicyHandle]
0x18003ec21  call    ?Close@?$AutoHandle@PEAXJ$1?LsaClose@@YAJPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,long,&LsaClose(void *),0>::Close(void)
0x18003ec26  nop
0x18003ec27  mov     [rsp+218h+var_1B0], r14b
0x18003ec2c  lea     rcx, [rsp+218h+var_1C0]
0x18003ec31  call    _lambda_da204913539f8ac3951b708370ebab48___operator__
0x18003ec36  nop
0x18003ec37  lea     rcx, [rsp+218h+var_118]
0x18003ec3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ec44  mov     eax, ebx
0x18003ec46  jmp     loc_18003F0A6
0x18003ec4b  mov     rdx, [rsp+218h+Buffer]
0x18003ec50  movzx   r8d, word ptr [rdx+10h]
0x18003ec55  shr     r8, 1
0x18003ec58  mov     rdx, [rdx+18h]
0x18003ec5c  lea     rcx, [rsp+218h+var_F8]
0x18003ec64  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x18003ec69  nop
0x18003ec6a  mov     eax, [rsp+218h+var_E8]
0x18003ec71  lea     eax, ds:2[rax*2]
0x18003ec78  mov     [rsp+218h+var_1F0], r15; wchar_t *
0x18003ec7d  mov     dword ptr [rsp+218h+lpcbData], eax; int
0x18003ec81  mov     r9, [rsp+218h+Buffer]
0x18003ec86  mov     r9, [r9+18h]; int
0x18003ec8a  mov     r8d, r14d; int
0x18003ec8d  lea     rdx, aDomainnamedns; "DomainNameDns"
0x18003ec94  mov     rcx, rsi; int
0x18003ec97  call    ClusterRegSetValueEx
0x18003ec9c  mov     ebx, eax
0x18003ec9e  test    eax, eax
0x18003eca0  jz      short loc_18003ED14
0x18003eca2  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003eca6  lea     rax, aFailedToSetDom_0; "Failed to set DomainNameDns in clusdb, "...
0x18003ecad  mov     [rsp+218h+lpcbData], rax
0x18003ecb2  mov     r9d, 24C8h
0x18003ecb8  lea     r8, aUpdatedomainin; "UpdateDomainInformationInClusterDB"
0x18003ecbf  xor     edx, edx
0x18003ecc1  mov     ecx, edi
0x18003ecc3  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18003ecc8  nop
0x18003ecc9  lea     rcx, [rsp+218h+var_F8]
0x18003ecd1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ecd6  nop
0x18003ecd7  lea     rcx, [rsp+218h+var_D8]
0x18003ecdf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ece4  nop
0x18003ece5  lea     rcx, [rsp+218h+PolicyHandle]
0x18003ecea  call    ?Close@?$AutoHandle@PEAXJ$1?LsaClose@@YAJPEAX@Z$0A@@cxl@@QEAAXXZ; cxl::AutoHandle<void *,long,&LsaClose(void *),0>::Close(void)
0x18003ecef  nop
0x18003ecf0  mov     [rsp+218h+var_1B0], r14b
0x18003ecf5  lea     rcx, [rsp+218h+var_1C0]
0x18003ecfa  call    _lambda_da204913539f8ac3951b708370ebab48___operator__
0x18003ecff  nop
0x18003ed00  lea     rcx, [rsp+218h+var_118]
0x18003ed08  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ed0d  mov     eax, ebx
0x18003ed0f  jmp     loc_18003F0A6
0x18003ed14  mov     rdx, [rsp+218h+Buffer]
0x18003ed19  movzx   r8d, word ptr [rdx+20h]
0x18003ed1e  shr     r8, 1
0x18003ed21  mov     rdx, [rdx+28h]
0x18003ed25  lea     rcx, [rsp+218h+var_B8]
0x18003ed2d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x18003ed32  nop
0x18003ed33  mov     eax, [rsp+218h+var_A8]
0x18003ed3a  lea     ebx, ds:2[rax*2]
0x18003ed41  lea     rcx, [rsp+218h+var_B8]
0x18003ed49  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003ed4e  mov     r9, rax; int
0x18003ed51  mov     [rsp+218h+var_1F0], r15; wchar_t *
0x18003ed56  mov     dword ptr [rsp+218h+lpcbData], ebx; int
0x18003ed5a  mov     r8d, r14d; int
0x18003ed5d  lea     rdx, aDomainforestna; "DomainForestName"
0x18003ed64  mov     rcx, rsi; int
0x18003ed67  call    ClusterRegSetValueEx
0x18003ed6c  mov     ebx, eax
0x18003ed6e  test    eax, eax
0x18003ed70  jz      loc_18003EDF6
0x18003ed76  mov     dword ptr [rsp+218h+var_1F0], eax
0x18003ed7a  lea     rax, aFailedToSetDom; "Failed to set DomainForestName in clusd"...
  ... truncated ...
```
