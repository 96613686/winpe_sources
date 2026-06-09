# shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::InitializeDefaults(void)

- ea: `0x180084544`
- end: `0x180084d56`
- name: `?InitializeDefaults@GlobalSettingsBaseStorage@SharedGlobalSettingsBase@shared@@AEAAXXZ`
- size: `2066`
- prototype: `void __fastcall(shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e7c4`
- `0x1800fc970`

## callees

- `0x180030190`
- `0x180084544`
- `0x180084d5c`
- `0x180084ef8`
- `0x180084fd8`
- `0x18008539c`
- `0x180085410`
- `0x1800854e4`
- `0x18010b348`
- `0x18010b3ac`
- `0x1801993d4`
- `0x1801f6fb0`
- `0x1801fcb5a`
- `0x18021c1e0`
- `0x18022b850`

## import_xrefs

- `msvcp_win!_Thrd_hardware_concurrency` at `0x180084b0e`
- `msvcp_win!_Thrd_hardware_concurrency` at `0x180084b0e`

## string_xrefs

- `0x18008466f`: `https://assets.activity.windows.com/v1/assets`
- `0x180084c0d`: `https://assets.activity.windows.com/v1/assets`
- `0x18008463c`: `https://activity.windows.com`
- `0x1800847a4`: `romeccs.microsoft.com`
- `0x180084c5d`: `romeccs.microsoft.com`
- `0x1800846d5`: `https://assets.activity.windows.com`
- `0x180084c35`: `https://assets.activity.windows.com`
- `0x1800846a2`: `https://assets.activity.windows.com/v1/assets/$batch`
- `0x180084c21`: `https://assets.activity.windows.com/v1/assets/$batch`
- `0x180084708`: `https://assets.activity.microsoft.com`
- `0x180084c49`: `https://assets.activity.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::InitializeDefaults(
        shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage *this)
{
  __int64 *v2; // rcx
  __int64 *v3; // rdx
  unsigned int v4; // r8d
  __int64 v5; // r8
  _BYTE **v6; // rcx
  _BYTE *v7; // rbx
  __int64 v8; // r8
  _BYTE **v9; // rcx
  _BYTE *v10; // rbx
  __int64 v11; // r8
  _BYTE **v12; // rcx
  _BYTE *v13; // rbx
  __int64 v14; // r8
  _BYTE **v15; // rcx
  _BYTE *v16; // rbx
  __int64 v17; // r8
  char **v18; // rcx
  __int64 v19; // r8
  char *v20; // rbx
  _BYTE **v21; // rcx
  _BYTE *v22; // rbx
  __int64 v23; // r8
  void **v24; // rbx
  __int64 v25; // r8
  _BYTE *v26; // rbx
  __int64 v27; // r8
  void **v28; // rbx
  __int64 v29; // r8
  _BYTE *v30; // rbx
  unsigned int v31; // eax
  _BYTE v32[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+44h] [rbp-BCh] BYREF
  char v34; // [rsp+48h] [rbp-B8h]
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h]
  void *v39[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h]
  unsigned __int64 v41; // [rsp+98h] [rbp-68h]
  void *v42[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-30h]
  __int64 v47; // [rsp+D8h] [rbp-28h]
  __int128 v48; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  void *v51[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h]
  unsigned __int64 v53; // [rsp+118h] [rbp+18h]
  void *v54[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v55; // [rsp+130h] [rbp+30h]
  unsigned __int64 v56; // [rsp+138h] [rbp+38h]
  __int128 v57; // [rsp+140h] [rbp+40h] BYREF
  __int64 v58; // [rsp+150h] [rbp+50h]
  __int64 v59; // [rsp+158h] [rbp+58h]

  *((_DWORD *)this + 21) = 3000;
  *((_DWORD *)this + 22) = 300000;
  *((_DWORD *)this + 25) = 180;
  *((_DWORD *)this + 24) = 0x10000;
  *((_DWORD *)this + 29) = 3;
  *((_DWORD *)this + 30) = 1;
  *((_DWORD *)this + 31) = 10000;
  *((_DWORD *)this + 32) = 100;
  *((_WORD *)this + 66) = 257;
  v2 = (__int64 *)((char *)this + 136);
  v3 = &qword_180549CC0;
  if ( v2 != &qword_180549CC0 )
  {
    if ( (unsigned __int64)qword_180549CD8 > 0xF )
      v3 = (__int64 *)qword_180549CC0;
    std::string::_Assign<char>(v2, v3, qword_180549CD0);
  }
  *((_DWORD *)this + 42) = 0;
  v4 = *(_DWORD *)Feature_CDPAFSProdDomainUri__descriptor;
  if ( (*(_DWORD *)Feature_CDPAFSProdDomainUri__descriptor & 4) == 0 )
  {
    v35 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CDPAFSProdDomainUri>::GetCachedFeatureEnabledState(
                       v2,
                       &v35);
    v4 = v35;
  }
  v33 = 0;
  v34 = 3;
  wil::details::ReportUsageToService(&qword_18054A690, 7776321, (v4 >> 10) & 1, (v4 >> 11) & 1, &v33, 1, 3);
  std::string::assign((char *)this + 176, "https://activity.windows.com");
  *((_QWORD *)this + 26) = 0;
  v6 = (_BYTE **)((char *)this + 216);
  if ( *((_QWORD *)this + 30) < 0x2Du )
  {
    LOBYTE(v5) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v6,
      45,
      v5,
      "https://assets.activity.windows.com/v1/assets");
  }
  else
  {
    v7 = *v6;
    *((_QWORD *)this + 29) = 45;
    memmove_0(v7, "https://assets.activity.windows.com/v1/assets", 0x2Du);
    v7[45] = 0;
  }
  v9 = (_BYTE **)((char *)this + 248);
  if ( *((_QWORD *)this + 34) < 0x34u )
  {
    LOBYTE(v8) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v9,
      52,
      v8,
      "https://assets.activity.windows.com/v1/assets/$batch");
  }
  else
  {
    v10 = *v9;
    *((_QWORD *)this + 33) = 52;
    memmove_0(v10, "https://assets.activity.windows.com/v1/assets/$batch", 0x34u);
    v10[52] = 0;
  }
  v12 = (_BYTE **)((char *)this + 280);
  if ( *((_QWORD *)this + 38) < 0x23u )
  {
    LOBYTE(v11) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v12,
      35,
      v11,
      "https://assets.activity.windows.com");
  }
  else
  {
    v13 = *v12;
    *((_QWORD *)this + 37) = 35;
    memmove_0(v13, "https://assets.activity.windows.com", 0x23u);
    v13[35] = 0;
  }
  v15 = (_BYTE **)((char *)this + 312);
  if ( *((_QWORD *)this + 42) < 0x25u )
  {
    LOBYTE(v14) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v15,
      37,
      v14,
      "https://assets.activity.microsoft.com");
  }
  else
  {
    v16 = *v15;
    *((_QWORD *)this + 41) = 37;
    memmove_0(v16, "https://assets.activity.microsoft.com", 0x25u);
    v16[37] = 0;
  }
  *((_BYTE *)this + 344) = 1;
  *((_DWORD *)this + 87) = 1024000;
  *((_DWORD *)this + 88) = 5000;
  *((_DWORD *)this + 89) = 10;
  v18 = (char **)((char *)this + 360);
  if ( *((_QWORD *)this + 48) >= 7u )
  {
    if ( *((_QWORD *)this + 48) > 0xFu )
      v20 = *v18;
    else
      v20 = (char *)this + 360;
    *((_QWORD *)this + 47) = 7;
    memmove_0(v20, "/api/v1", 7u);
    v20[7] = 0;
  }
  else
  {
    LOBYTE(v17) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v18, 7, v17, "/api/v1");
  }
  v21 = (_BYTE **)((char *)this + 392);
  if ( *((_QWORD *)this + 52) < 0x15u )
  {
    LOBYTE(v19) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v21,
      21,
      v19,
      "romeccs.microsoft.com");
  }
  else
  {
    v22 = *v21;
    *((_QWORD *)this + 51) = 21;
    memmove_0(v22, "romeccs.microsoft.com", 0x15u);
    v22[21] = 0;
  }
  *((_DWORD *)this + 106) = 1;
  *((_BYTE *)this + 428) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_BYTE *)this + 440) = 0;
  *((_BYTE *)this + 729) = 0;
  *((_DWORD *)this + 23) = 3600;
  *(_WORD *)((char *)this + 731) = 257;
  v32[0] = 3;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 1;
  v32[0] = 1;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 1;
  v32[0] = 2;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 1;
  v32[0] = 4;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 0;
  v32[0] = 5;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 0;
  v32[0] = 6;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 696, v32) = 0;
  v32[0] = 3;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 1;
  v32[0] = 1;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 0;
  v32[0] = 2;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 0;
  v32[0] = 4;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 0;
  v32[0] = 5;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 0;
  v32[0] = 6;
  *(_BYTE *)std::map<enum shared::TransportSettingType,bool>::operator[]((char *)this + 712, v32) = 0;
  *((_BYTE *)this + 728) = 0;
  if ( *((_QWORD *)this + 96) != *((_QWORD *)this + 97) )
  {
    std::_Destroy_range<std::allocator<shared::POBoxInfo>>(*((shared::POBoxInfo **)this + 96));
    *((_QWORD *)this + 97) = *((_QWORD *)this + 96);
  }
  v48 = 0;
  v50 = 15;
  LOBYTE(v48) = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  v53 = 15;
  LOBYTE(v51[0]) = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  v56 = 15;
  LOBYTE(v54[0]) = 0;
  v57 = 0;
  v59 = 15;
  v58 = 6;
  strcpy((char *)&v57, "binary");
  v49 = 15;
  memmove_0(&v48, "cortana.xdevice", 0xFu);
  HIBYTE(v48) = 0;
  if ( v53 < 0xF )
  {
    LOBYTE(v23) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v51,
      15,
      v23,
      "cortana.xdevice");
  }
  else
  {
    v24 = v51;
    if ( v53 > 0xF )
      v24 = (void **)v51[0];
    v52 = 15;
    memmove_0(v24, "cortana.xdevice", 0xFu);
    *((_BYTE *)v24 + 15) = 0;
  }
  if ( v56 < 0x13 )
  {
    LOBYTE(v25) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v54,
      19,
      v25,
      "ShareFileBinaryHost");
  }
  else
  {
    v26 = v54[0];
    v55 = 19;
    memmove_0(v54[0], "ShareFileBinaryHost", 0x13u);
    v26[19] = 0;
  }
  v36 = 0;
  v38 = 15;
  LOBYTE(v36) = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 15;
  LOBYTE(v39[0]) = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 15;
  LOBYTE(v42[0]) = 0;
  v45 = 0;
  v47 = 15;
  v46 = 6;
  strcpy((char *)&v45, "binary");
  v37 = 15;
  memmove_0(&v36, "cortana.xdevice", 0xFu);
  HIBYTE(v36) = 0;
  if ( v41 < 0xF )
  {
    LOBYTE(v27) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v39,
      15,
      v27,
      "cortana.xdevice");
  }
  else
  {
    v28 = v39;
    if ( v41 > 0xF )
      v28 = (void **)v39[0];
    v40 = 15;
    memmove_0(v28, "cortana.xdevice", 0xFu);
    *((_BYTE *)v28 + 15) = 0;
  }
  if ( v44 < 0x1C )
  {
    LOBYTE(v29) = 0;
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      v42,
      28,
      v29,
      "NotificationActionBinaryHost");
  }
  else
  {
    v30 = v42[0];
    v43 = 28;
    memmove_0(v42[0], "NotificationActionBinaryHost", 0x1Cu);
    v30[28] = 0;
  }
  if ( *((_QWORD *)this + 97) == *((_QWORD *)this + 98) )
  {
    std::vector<shared::POBoxInfo>::_Emplace_reallocate<shared::POBoxInfo &>(
      (char *)this + 768,
      *((_QWORD *)this + 97),
      &v48);
  }
  else
  {
    shared::POBoxInfo::POBoxInfo(*((shared::POBoxInfo **)this + 97), (const struct shared::POBoxInfo *)&v48);
    *((_QWORD *)this + 97) += 128LL;
  }
  if ( *((_QWORD *)this + 97) == *((_QWORD *)this + 98) )
  {
    std::vector<shared::POBoxInfo>::_Emplace_reallocate<shared::POBoxInfo &>(
      (char *)this + 768,
      *((_QWORD *)this + 97),
      &v36);
  }
  else
  {
    shared::POBoxInfo::POBoxInfo(*((shared::POBoxInfo **)this + 97), (const struct shared::POBoxInfo *)&v36);
    *((_QWORD *)this + 97) += 128LL;
  }
  *((_DWORD *)this + 8) = 3;
  *((_DWORD *)this + 9) = 66;
  v31 = _Thrd_hardware_concurrency();
  if ( v31 >= 0x100 )
    LOBYTE(v31) = -1;
  *((_BYTE *)this + 960) = v31;
  if ( !(_BYTE)v31 )
    *((_BYTE *)this + 960) = 4;
  *((_BYTE *)this + 961) = 1;
  *((_DWORD *)this + 241) = 10000;
  *((_DWORD *)this + 242) = 86400000;
  *((_DWORD *)this + 243) = 32;
  *((_DWORD *)this + 244) = 5;
  *((_DWORD *)this + 245) = 100;
  *((_BYTE *)this + 984) = 0;
  *((_WORD *)this + 520) = 257;
  *((_BYTE *)this + 730) = 0;
  *((_WORD *)this + 367) = -75;
  shared::SharedGlobalSettingsBase::OverridePlatformDefaults(this);
  shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::EnsureVirtualDeviceId(this);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v45);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v42);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v39);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v36);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v57);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v54);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v51);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v48);
}

```

## disassembly

```asm
0x180084544  mov     [rsp-8+arg_8], rbx
0x180084549  mov     [rsp-8+arg_10], rsi
0x18008454e  push    rbp
0x18008454f  push    rdi
0x180084550  push    r12
0x180084552  push    r14
0x180084554  push    r15
0x180084556  lea     rbp, [rsp-70h]
0x18008455b  sub     rsp, 170h
0x180084562  mov     rax, cs:__security_cookie
0x180084569  xor     rax, rsp
0x18008456c  mov     [rbp+90h+var_30], rax
0x180084570  mov     rdi, rcx
0x180084573  mov     dword ptr [rcx+54h], 0BB8h
0x18008457a  mov     dword ptr [rcx+58h], 493E0h
0x180084581  mov     dword ptr [rcx+64h], 0B4h
0x180084588  mov     dword ptr [rcx+60h], 10000h
0x18008458f  mov     esi, 3
0x180084594  mov     [rcx+74h], esi
0x180084597  mov     dword ptr [rcx+78h], 1
0x18008459e  mov     dword ptr [rcx+7Ch], 2710h
0x1800845a5  mov     dword ptr [rcx+80h], 64h ; 'd'
0x1800845af  mov     word ptr [rcx+84h], 101h
0x1800845b8  add     rcx, 88h
0x1800845bf  lea     rdx, qword_180549CC0
0x1800845c6  lea     r12d, [rsi+0Ch]
0x1800845ca  cmp     rcx, rdx
0x1800845cd  jnz     loc_180084CDE
0x1800845d3  xor     r15d, r15d
0x1800845d6  mov     [rdi+0A8h], r15d
0x1800845dd  mov     rax, cs:Feature_CDPAFSProdDomainUri__descriptor
0x1800845e4  mov     r8d, [rax]
0x1800845e7  test    r8b, 4
0x1800845eb  jz      loc_180084CFE
0x1800845f1  mov     [rsp+190h+var_14C], r15d
0x1800845f6  mov     [rsp+190h+var_148], sil
0x1800845fb  mov     r9d, r8d
0x1800845fe  shr     r9d, 0Bh
0x180084602  and     r9d, 1
0x180084606  shr     r8d, 0Ah
0x18008460a  and     r8d, 1
0x18008460e  mov     [rsp+190h+var_160], esi
0x180084612  mov     [rsp+190h+var_168], 1
0x18008461a  lea     rax, [rsp+190h+var_14C]
0x18008461f  mov     [rsp+190h+var_170], rax
0x180084624  mov     edx, 76A841h
0x180084629  lea     rcx, qword_18054A690
0x180084630  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180084635  lea     rcx, [rdi+0B0h]
0x18008463c  lea     rdx, ?CDP_PROD_AFS_URL@shared@@3QBDB; "https://activity.windows.com"
0x180084643  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180084648  mov     [rdi+0D0h], r15
0x18008464f  lea     rcx, [rdi+0D8h]
0x180084656  mov     edx, 2Dh ; '-'
0x18008465b  cmp     [rcx+18h], rdx
0x18008465f  jb      loc_180084C0A
0x180084665  mov     rbx, [rcx]
0x180084668  mov     [rcx+10h], rdx
0x18008466c  mov     r8d, edx; Size
0x18008466f  lea     rdx, ?c_ActivityAssetUrlProd@shared@@3QBDB; "https://assets.activity.windows.com/v1/"...
0x180084676  mov     rcx, rbx; void *
0x180084679  call    memmove_0
0x18008467e  mov     [rbx+2Dh], r15b
0x180084682  lea     rcx, [rdi+0F8h]
0x180084689  mov     edx, 34h ; '4'
0x18008468e  cmp     [rcx+18h], rdx
0x180084692  jb      loc_180084C1E
0x180084698  mov     rbx, [rcx]
0x18008469b  mov     [rcx+10h], rdx
0x18008469f  mov     r8d, edx; Size
0x1800846a2  lea     rdx, ?c_ActivityAssetBatchUrlProd@shared@@3QBDB; "https://assets.activity.windows.com/v1/"...
0x1800846a9  mov     rcx, rbx; void *
0x1800846ac  call    memmove_0
0x1800846b1  mov     [rbx+34h], r15b
0x1800846b5  lea     rcx, [rdi+118h]
0x1800846bc  mov     edx, 23h ; '#'
0x1800846c1  cmp     [rcx+18h], rdx
0x1800846c5  jb      loc_180084C32
0x1800846cb  mov     rbx, [rcx]
0x1800846ce  mov     [rcx+10h], rdx
0x1800846d2  mov     r8d, edx; Size
0x1800846d5  lea     rdx, ?c_MsaAssetScopeEndpointNameProd@shared@@3QBDB; "https://assets.activity.windows.com"
0x1800846dc  mov     rcx, rbx; void *
0x1800846df  call    memmove_0
0x1800846e4  mov     [rbx+23h], r15b
0x1800846e8  lea     rcx, [rdi+138h]
0x1800846ef  mov     edx, 25h ; '%'
0x1800846f4  cmp     [rcx+18h], rdx
0x1800846f8  jb      loc_180084C46
0x1800846fe  mov     rbx, [rcx]
0x180084701  mov     [rcx+10h], rdx
0x180084705  mov     r8d, edx; Size
0x180084708  lea     rdx, ?c_AadAssetAudienceNameProd@shared@@3QBDB; "https://assets.activity.microsoft.com"
0x18008470f  mov     rcx, rbx; void *
0x180084712  call    memmove_0
0x180084717  mov     [rbx+25h], r15b
0x18008471b  mov     byte ptr [rdi+158h], 1
0x180084722  mov     dword ptr [rdi+15Ch], 0FA000h
0x18008472c  mov     dword ptr [rdi+160h], 1388h
0x180084736  mov     dword ptr [rdi+164h], 0Ah
0x180084740  lea     rcx, [rdi+168h]
0x180084747  mov     edx, 7
0x18008474c  cmp     [rcx+18h], rdx
0x180084750  jnb     loc_180084CCC
0x180084756  mov     r8b, r15b
0x180084759  lea     r9, ?CcsDefaultApiVersion@shared@@3QBDB; "/api/v1"
0x180084760  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180084765  jmp     short loc_180084784
0x180084767  mov     rbx, [rcx]
0x18008476a  mov     [rcx+10h], rdx
0x18008476e  mov     r8, rdx; Size
0x180084771  lea     rdx, ?CcsDefaultApiVersion@shared@@3QBDB; "/api/v1"
0x180084778  mov     rcx, rbx; void *
0x18008477b  call    memmove_0
0x180084780  mov     [rbx+7], r15b
0x180084784  lea     rcx, [rdi+188h]
0x18008478b  mov     edx, 15h
0x180084790  cmp     [rcx+18h], rdx
0x180084794  jb      loc_180084C5A
0x18008479a  mov     rbx, [rcx]
0x18008479d  mov     [rcx+10h], rdx
0x1800847a1  mov     r8d, edx; Size
0x1800847a4  lea     rdx, ?CcsDefaultServerName@shared@@3QBDB; "romeccs.microsoft.com"
0x1800847ab  mov     rcx, rbx; void *
0x1800847ae  call    memmove_0
0x1800847b3  mov     [rbx+15h], r15b
0x1800847b7  mov     dword ptr [rdi+1A8h], 1
0x1800847c1  mov     [rdi+1ACh], r15b
0x1800847c8  mov     [rdi+1B0h], r15
0x1800847cf  mov     [rdi+1B8h], r15b
0x1800847d6  mov     [rdi+2D9h], r15b
0x1800847dd  mov     dword ptr [rdi+5Ch], 0E10h
0x1800847e4  mov     word ptr [rdi+2DBh], 101h
0x1800847ed  mov     [rsp+190h+var_150], sil
0x1800847f2  lea     rbx, [rdi+2B8h]
0x1800847f9  lea     rdx, [rsp+190h+var_150]
0x1800847fe  mov     rcx, rbx
0x180084801  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x180084806  mov     byte ptr [rax], 1
0x180084809  mov     [rsp+190h+var_150], 1
0x18008480e  lea     rdx, [rsp+190h+var_150]
0x180084813  mov     rcx, rbx
0x180084816  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x18008481b  mov     byte ptr [rax], 1
0x18008481e  mov     [rsp+190h+var_150], 2
0x180084823  lea     rdx, [rsp+190h+var_150]
0x180084828  mov     rcx, rbx
0x18008482b  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x180084830  mov     byte ptr [rax], 1
0x180084833  mov     [rsp+190h+var_150], 4
0x180084838  lea     rdx, [rsp+190h+var_150]
0x18008483d  mov     rcx, rbx
0x180084840  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x180084845  mov     [rax], r15b
0x180084848  mov     [rsp+190h+var_150], 5
0x18008484d  lea     rdx, [rsp+190h+var_150]
0x180084852  mov     rcx, rbx
0x180084855  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x18008485a  mov     [rax], r15b
0x18008485d  mov     [rsp+190h+var_150], 6
0x180084862  lea     rdx, [rsp+190h+var_150]
0x180084867  mov     rcx, rbx
0x18008486a  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x18008486f  mov     [rax], r15b
0x180084872  mov     [rsp+190h+var_150], sil
0x180084877  lea     rbx, [rdi+2C8h]
0x18008487e  lea     rdx, [rsp+190h+var_150]
0x180084883  mov     rcx, rbx
0x180084886  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x18008488b  mov     byte ptr [rax], 1
0x18008488e  mov     [rsp+190h+var_150], 1
0x180084893  lea     rdx, [rsp+190h+var_150]
0x180084898  mov     rcx, rbx
0x18008489b  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x1800848a0  mov     [rax], r15b
0x1800848a3  mov     [rsp+190h+var_150], 2
0x1800848a8  lea     rdx, [rsp+190h+var_150]
0x1800848ad  mov     rcx, rbx
0x1800848b0  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x1800848b5  mov     [rax], r15b
0x1800848b8  mov     [rsp+190h+var_150], 4
0x1800848bd  lea     rdx, [rsp+190h+var_150]
0x1800848c2  mov     rcx, rbx
0x1800848c5  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x1800848ca  mov     [rax], r15b
0x1800848cd  mov     [rsp+190h+var_150], 5
0x1800848d2  lea     rdx, [rsp+190h+var_150]
0x1800848d7  mov     rcx, rbx
0x1800848da  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x1800848df  mov     [rax], r15b
0x1800848e2  mov     [rsp+190h+var_150], 6
0x1800848e7  lea     rdx, [rsp+190h+var_150]
0x1800848ec  mov     rcx, rbx
0x1800848ef  call    ??A?$map@W4TransportSettingType@shared@@_NU?$less@W4TransportSettingType@shared@@@std@@V?$allocator@U?$pair@$$CBW4TransportSettingType@shared@@_N@std@@@4@@std@@QEAAAEA_N$$QEAW4TransportSettingType@shared@@@Z; std::map<shared::TransportSettingType,bool>::operator[](shared::TransportSettingType &&)
0x1800848f4  mov     [rax], r15b
0x1800848f7  mov     [rdi+2D8h], r15b
0x1800848fe  lea     rsi, [rdi+300h]
0x180084905  mov     rdx, [rsi+8]
0x180084909  cmp     [rsi], rdx
0x18008490c  jnz     loc_180084D18
0x180084912  xorps   xmm0, xmm0
0x180084915  movups  [rbp+90h+var_B0], xmm0
0x180084919  mov     [rbp+90h+var_98], r12
0x18008491d  mov     byte ptr [rbp+90h+var_B0], r15b
0x180084921  movups  xmmword ptr [rbp+90h+var_90], xmm0
0x180084925  mov     [rbp+90h+var_80], r15
0x180084929  mov     [rbp+90h+var_78], r12
0x18008492d  mov     byte ptr [rbp+90h+var_90], r15b
0x180084931  movups  xmmword ptr [rbp+90h+var_70], xmm0
0x180084935  mov     [rbp+90h+var_60], r15
0x180084939  mov     [rbp+90h+var_58], r12
0x18008493d  mov     byte ptr [rbp+90h+var_70], r15b
0x180084941  movups  [rbp+90h+var_50], xmm0
0x180084945  mov     [rbp+90h+var_38], r12
0x180084949  mov     [rbp+90h+var_40], 6
0x180084951  mov     eax, dword ptr cs:aBinary; "binary"
0x180084957  mov     dword ptr [rbp+90h+var_50], eax
0x18008495a  movzx   eax, word ptr cs:aBinary+4; "ry"
0x180084961  mov     word ptr [rbp+90h+var_50+4], ax
0x180084965  mov     byte ptr [rbp+90h+var_50+6], r15b
0x180084969  lea     rbx, [rbp+90h+var_B0]
0x18008496d  mov     [rbp+90h+var_A0], r12
0x180084971  mov     r8, r12; Size
0x180084974  lea     r14, aCortanaXdevice; "cortana.xdevice"
0x18008497b  mov     rdx, r14; Src
0x18008497e  mov     rcx, rbx; void *
0x180084981  call    memmove_0
0x180084986  mov     [rbx+0Fh], r15b
0x18008498a  cmp     [rbp+90h+var_78], r12
0x18008498e  jb      loc_180084C6E
0x180084994  lea     rbx, [rbp+90h+var_90]
0x180084998  cmova   rbx, [rbp+90h+var_90]
0x18008499d  mov     [rbp+90h+var_80], r12
0x1800849a1  mov     r8, r12; Size
0x1800849a4  mov     rdx, r14; Src
0x1800849a7  mov     rcx, rbx; void *
0x1800849aa  call    memmove_0
0x1800849af  mov     [rbx+0Fh], r15b
0x1800849b3  mov     edx, 13h
0x1800849b8  cmp     [rbp+90h+var_58], rdx
0x1800849bc  jb      loc_180084C85
0x1800849c2  lea     rbx, [rbp+90h+var_70]
0x1800849c6  cmp     [rbp+90h+var_58], r12
0x1800849ca  cmova   rbx, [rbp+90h+var_70]
0x1800849cf  mov     [rbp+90h+var_60], rdx
0x1800849d3  mov     r8d, edx; Size
0x1800849d6  lea     rdx, aSharefilebinar; "ShareFileBinaryHost"
0x1800849dd  mov     rcx, rbx; void *
0x1800849e0  call    memmove_0
0x1800849e5  mov     [rbx+13h], r15b
0x1800849e9  xorps   xmm0, xmm0
0x1800849ec  movups  [rsp+190h+var_130], xmm0
0x1800849f1  mov     [rsp+190h+var_118], r12
0x1800849f6  mov     byte ptr [rsp+190h+var_130], r15b
0x1800849fb  movups  xmmword ptr [rbp+90h+var_110], xmm0
0x1800849ff  mov     [rbp+90h+var_100], r15
0x180084a03  mov     [rbp+90h+var_F8], r12
0x180084a07  mov     byte ptr [rbp+90h+var_110], r15b
0x180084a0b  movups  xmmword ptr [rbp+90h+var_F0], xmm0
0x180084a0f  mov     [rbp+90h+var_E0], r15
0x180084a13  mov     [rbp+90h+var_D8], r12
0x180084a17  mov     byte ptr [rbp+90h+var_F0], r15b
0x180084a1b  movups  [rbp+90h+var_D0], xmm0
0x180084a1f  mov     [rbp+90h+var_B8], r12
0x180084a23  mov     [rbp+90h+var_C0], 6
0x180084a2b  mov     eax, dword ptr cs:aBinary; "binary"
0x180084a31  mov     dword ptr [rbp+90h+var_D0], eax
0x180084a34  movzx   eax, word ptr cs:aBinary+4; "ry"
0x180084a3b  mov     word ptr [rbp+90h+var_D0+4], ax
0x180084a3f  mov     byte ptr [rbp+90h+var_D0+6], r15b
0x180084a43  lea     rbx, [rsp+190h+var_130]
0x180084a48  mov     [rsp+190h+var_120], r12
0x180084a4d  mov     r8, r12; Size
0x180084a50  mov     rdx, r14; Src
0x180084a53  mov     rcx, rbx; void *
0x180084a56  call    memmove_0
0x180084a5b  mov     [rbx+0Fh], r15b
0x180084a5f  cmp     [rbp+90h+var_F8], r12
0x180084a63  jb      loc_180084C9D
0x180084a69  lea     rbx, [rbp+90h+var_110]
0x180084a6d  cmova   rbx, [rbp+90h+var_110]
0x180084a72  mov     [rbp+90h+var_100], r12
0x180084a76  mov     r8, r12; Size
0x180084a79  mov     rdx, r14; Src
0x180084a7c  mov     rcx, rbx; void *
0x180084a7f  call    memmove_0
0x180084a84  mov     [rbx+0Fh], r15b
0x180084a88  mov     edx, 1Ch
0x180084a8d  cmp     [rbp+90h+var_D8], rdx
0x180084a91  jb      loc_180084CB4
0x180084a97  lea     rbx, [rbp+90h+var_F0]
0x180084a9b  cmp     [rbp+90h+var_D8], r12
0x180084a9f  cmova   rbx, [rbp+90h+var_F0]
0x180084aa4  mov     [rbp+90h+var_E0], rdx
0x180084aa8  mov     r8d, edx; Size
0x180084aab  lea     rdx, aNotificationac; "NotificationActionBinaryHost"
0x180084ab2  mov     rcx, rbx; void *
0x180084ab5  call    memmove_0
0x180084aba  mov     [rbx+1Ch], r15b
0x180084abe  mov     rax, [rsi+8]
  ... truncated ...
```
