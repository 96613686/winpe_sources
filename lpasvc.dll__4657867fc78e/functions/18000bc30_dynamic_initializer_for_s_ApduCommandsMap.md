# _dynamic_initializer_for__s_ApduCommandsMap__

- ea: `0x18000bc30`
- end: `0x18000c782`
- name: `_dynamic_initializer_for__s_ApduCommandsMap__`
- size: `2898`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000bc30`
- `0x18000df90`
- `0x18000dfb4`
- `0x18000e410`
- `0x18005dba0`
- `0x18005f440`
- `0x18005f848`
- `0x180060854`
- `0x180063668`
- `0x180070584`
- `0x180071650`

## string_xrefs

- `0x18000bcc7`: `UpdateMetadataRequest`
- `0x18000bd5a`: `ReplaceSessionKeysRequest`
- `0x18000bdbc`: `EuiccConfiguredDataRequest`
- `0x18000c092`: `VerifyCommandCodeRequest`
- `0x18000c156`: `DeleteProfileRequest`
- `0x18000c2a1`: `ExecuteCommandCodeRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=114
int dynamic_initializer_for__s_ApduCommandsMap__()
{
  __int64 v0; // rax
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rdi
  __int64 *v41; // rbx
  __int16 v43; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v44; // [rsp+22h] [rbp-DEh] BYREF
  __int16 v45; // [rsp+24h] [rbp-DCh] BYREF
  __int16 v46; // [rsp+26h] [rbp-DAh] BYREF
  __int16 v47; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v48; // [rsp+2Ah] [rbp-D6h] BYREF
  __int16 v49; // [rsp+2Ch] [rbp-D4h] BYREF
  __int16 v50; // [rsp+2Eh] [rbp-D2h] BYREF
  __int16 v51; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v52; // [rsp+32h] [rbp-CEh] BYREF
  __int16 v53; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v54; // [rsp+36h] [rbp-CAh] BYREF
  __int16 v55; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v56; // [rsp+3Ah] [rbp-C6h] BYREF
  __int16 v57; // [rsp+3Ch] [rbp-C4h] BYREF
  __int16 v58; // [rsp+3Eh] [rbp-C2h] BYREF
  __int16 v59; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v60; // [rsp+42h] [rbp-BEh] BYREF
  __int16 v61; // [rsp+44h] [rbp-BCh] BYREF
  __int16 v62; // [rsp+46h] [rbp-BAh] BYREF
  __int16 v63; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v64; // [rsp+4Ah] [rbp-B6h] BYREF
  __int16 v65; // [rsp+4Ch] [rbp-B4h] BYREF
  __int16 v66; // [rsp+4Eh] [rbp-B2h] BYREF
  __int16 v67; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v68; // [rsp+52h] [rbp-AEh] BYREF
  __int16 v69; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v70; // [rsp+56h] [rbp-AAh] BYREF
  __int16 v71; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v72; // [rsp+5Ah] [rbp-A6h] BYREF
  __int16 v73; // [rsp+5Ch] [rbp-A4h] BYREF
  __int16 v74; // [rsp+5Eh] [rbp-A2h] BYREF
  __int16 v75; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v76; // [rsp+62h] [rbp-9Eh] BYREF
  __int16 v77; // [rsp+64h] [rbp-9Ch] BYREF
  __int16 v78; // [rsp+66h] [rbp-9Ah] BYREF
  __int16 v79; // [rsp+68h] [rbp-98h] BYREF
  __int16 v80; // [rsp+6Ah] [rbp-96h] BYREF
  _BYTE v81[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v82[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v83[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v84[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v85[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v86[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v87[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v88[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v89[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v90[32]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v91[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v92[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v93[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v94[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v95[32]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v96[32]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v97[32]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v98[32]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v99[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v100[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v101[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v102[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v103[32]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v104[32]; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v105[32]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v106[32]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v107[32]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v108[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v109[32]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v110[32]; // [rsp+410h] [rbp+310h] BYREF
  _BYTE v111[32]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v112[32]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v113[32]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v114[32]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v115[32]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v116[32]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v117[32]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v118[32]; // [rsp+510h] [rbp+410h] BYREF
  _BYTE v119[40]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v120[40]; // [rsp+558h] [rbp+458h] BYREF
  _BYTE v121[40]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v122[40]; // [rsp+5A8h] [rbp+4A8h] BYREF
  _BYTE v123[40]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v124[40]; // [rsp+5F8h] [rbp+4F8h] BYREF
  _BYTE v125[40]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v126[40]; // [rsp+648h] [rbp+548h] BYREF
  _BYTE v127[40]; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v128[40]; // [rsp+698h] [rbp+598h] BYREF
  _BYTE v129[40]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v130[40]; // [rsp+6E8h] [rbp+5E8h] BYREF
  _BYTE v131[40]; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v132[40]; // [rsp+738h] [rbp+638h] BYREF
  _BYTE v133[40]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v134[40]; // [rsp+788h] [rbp+688h] BYREF
  _BYTE v135[40]; // [rsp+7B0h] [rbp+6B0h] BYREF
  _BYTE v136[40]; // [rsp+7D8h] [rbp+6D8h] BYREF
  _BYTE v137[40]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v138[40]; // [rsp+828h] [rbp+728h] BYREF
  _BYTE v139[40]; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v140[40]; // [rsp+878h] [rbp+778h] BYREF
  _BYTE v141[40]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v142[40]; // [rsp+8C8h] [rbp+7C8h] BYREF
  _BYTE v143[40]; // [rsp+8F0h] [rbp+7F0h] BYREF
  _BYTE v144[40]; // [rsp+918h] [rbp+818h] BYREF
  _BYTE v145[40]; // [rsp+940h] [rbp+840h] BYREF
  _BYTE v146[40]; // [rsp+968h] [rbp+868h] BYREF
  _BYTE v147[40]; // [rsp+990h] [rbp+890h] BYREF
  _BYTE v148[40]; // [rsp+9B8h] [rbp+8B8h] BYREF
  _BYTE v149[40]; // [rsp+9E0h] [rbp+8E0h] BYREF
  _BYTE v150[40]; // [rsp+A08h] [rbp+908h] BYREF
  _BYTE v151[40]; // [rsp+A30h] [rbp+930h] BYREF
  _BYTE v152[40]; // [rsp+A58h] [rbp+958h] BYREF
  _BYTE v153[40]; // [rsp+A80h] [rbp+980h] BYREF
  _BYTE v154[40]; // [rsp+AA8h] [rbp+9A8h] BYREF
  _BYTE v155[40]; // [rsp+AD0h] [rbp+9D0h] BYREF
  _BYTE v156[40]; // [rsp+AF8h] [rbp+9F8h] BYREF
  __int64 v157; // [rsp+B20h] [rbp+A20h] BYREF

  v43 = -16608;
  v0 = std::wstring::wstring(v118, L"EUICCInfo1");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v119, &v43, v0);
  v44 = -16606;
  v1 = std::wstring::wstring(v117, L"EUICCInfo2");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v120, &v44, v1);
  v45 = -16598;
  v2 = std::wstring::wstring(v116, L"UpdateMetadataRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v121, &v45, v2);
  v46 = -16605;
  v3 = std::wstring::wstring(v115, L"InitialiseSecureChannelRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v122, &v46, v3);
  v47 = -16603;
  v4 = std::wstring::wstring(v114, L"StoreMetadataRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v123, &v47, v4);
  v48 = -16602;
  v5 = std::wstring::wstring(v113, L"ReplaceSessionKeysRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v124, &v48, v5);
  v49 = -16574;
  v6 = std::wstring::wstring(v112, L"LpaeActivationRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v125, &v49, v6);
  v50 = -16580;
  v7 = std::wstring::wstring(v111, L"EuiccConfiguredDataRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v126, &v50, v7);
  v51 = -16577;
  v8 = std::wstring::wstring(v110, L"SetDefaultDpAddressRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v127, &v51, v8);
  v52 = -16571;
  v9 = std::wstring::wstring(v109, L"VerifyEventListRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v128, &v52, v9);
  v53 = -16607;
  v10 = std::wstring::wstring(v108, L"PrepareDownloadRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v129, &v53, v10);
  v54 = -16594;
  v11 = std::wstring::wstring(v107, L"GetEuiccChallengeRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v130, &v54, v11);
  v55 = -16608;
  v12 = std::wstring::wstring(v106, L"GetEuiccInfo1Request");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v131, &v55, v12);
  v56 = -16606;
  v13 = std::wstring::wstring(v105, L"GetEuiccInfo2Request");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v132, &v56, v13);
  v57 = -16606;
  v14 = std::wstring::wstring(v104, L"GetEuiccInfo2Request");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v133, &v57, v14);
  v58 = -16600;
  v15 = std::wstring::wstring(v103, L"ListNotificationRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v134, &v58, v15);
  v59 = -16593;
  v16 = std::wstring::wstring(v102, L"NotificationMetadata");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v135, &v59, v16);
  v60 = -16597;
  v17 = std::wstring::wstring(v101, L"RetrieveNotificationsListRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v136, &v60, v17);
  v61 = -16592;
  v18 = std::wstring::wstring(v100, L"NotificationSentRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v137, &v61, v18);
  v62 = -16584;
  v19 = std::wstring::wstring(v99, L"AuthenticateServerRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v138, &v62, v19);
  v63 = -16575;
  v20 = std::wstring::wstring(v98, L"CancelSessionRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v139, &v63, v20);
  v64 = -16570;
  v21 = std::wstring::wstring(v97, L"LoadRpmPackageRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v140, &v64, v21);
  v65 = -16567;
  v22 = std::wstring::wstring(v96, L"VerifyCommandCodeRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v141, &v65, v22);
  v66 = -16595;
  v23 = std::wstring::wstring(v95, L"ProfileInfoListRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v142, &v66, v23);
  v67 = -16591;
  v24 = std::wstring::wstring(v94, L"EnableProfileRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v143, &v67, v24);
  v68 = -16590;
  v25 = std::wstring::wstring(v93, L"DisableProfileRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v144, &v68, v25);
  v69 = -16589;
  v26 = std::wstring::wstring(v92, L"DeleteProfileRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v145, &v69, v26);
  v70 = -16588;
  v27 = std::wstring::wstring(v91, L"EuiccMemoryResetRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v146, &v70, v27);
  v71 = -16578;
  v28 = std::wstring::wstring(v90, L"GetEuiccDataRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v147, &v71, v28);
  v72 = -16599;
  v29 = std::wstring::wstring(v89, L"SetNicknameRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v148, &v72, v29);
  v73 = -16573;
  v30 = std::wstring::wstring(v88, L"GetRatRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v149, &v73, v30);
  v74 = -16566;
  v31 = std::wstring::wstring(v87, L"AlertData");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v150, &v74, v31);
  v75 = -16569;
  v32 = std::wstring::wstring(v86, L"InitiateLpaApiRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v151, &v75, v32);
  v76 = -16568;
  v33 = std::wstring::wstring(v85, L"ExecuteCommandCodeRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v152, &v76, v33);
  v77 = -16583;
  v34 = std::wstring::wstring(v84, L"InitiateAuthenticationRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v153, &v77, v34);
  v78 = -16581;
  v35 = std::wstring::wstring(v83, L"AuthenticateClientRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v154, &v78, v35);
  v79 = -16582;
  v36 = std::wstring::wstring(v82, L"GetBoundProfilePackageRequest");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v155, &v79, v36);
  v80 = -16579;
  v37 = std::wstring::wstring(v81, L"HandleNotification");
  std::pair<unsigned short const,std::wstring>::pair<unsigned short const,std::wstring>(v156, &v80, v37);
  std::_Compressed_pair<std::less<unsigned short>,std::_Compressed_pair<std::allocator<std::_Tree_node<std::pair<unsigned short const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,std::wstring>>>,1>,1>::_Compressed_pair<std::less<unsigned short>,std::_Compressed_pair<std::allocator<std::_Tree_node<std::pair<unsigned short const,std::wstring>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,std::wstring>>>,1>,1>();
  std::_Tree<std::_Tmap_traits<unsigned short,std::wstring,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(v38);
  v40 = xmmword_180173BB8;
  v41 = (__int64 *)v119;
  do
  {
    std::_Tree<std::_Tmap_traits<unsigned short,std::wstring,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,std::wstring>>,0>>::_Emplace_hint<std::pair<unsigned short const,std::wstring> const &>(
      v39,
      v40,
      v41);
    v41 += 5;
  }
  while ( v41 != &v157 );
  `eh vector destructor iterator'(
    v119,
    0x28u,
    0x26u,
    std::pair<unsigned short const,std::wstring>::~pair<unsigned short const,std::wstring>);
  std::wstring::_Tidy_deallocate(v81);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v81);
  std::wstring::_Tidy_deallocate(v82);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v82);
  std::wstring::_Tidy_deallocate(v83);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v83);
  std::wstring::_Tidy_deallocate(v84);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v84);
  std::wstring::_Tidy_deallocate(v85);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v85);
  std::wstring::_Tidy_deallocate(v86);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v86);
  std::wstring::_Tidy_deallocate(v87);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v87);
  std::wstring::_Tidy_deallocate(v88);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v88);
  std::wstring::_Tidy_deallocate(v89);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v89);
  std::wstring::_Tidy_deallocate(v90);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v90);
  std::wstring::_Tidy_deallocate(v91);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v91);
  std::wstring::_Tidy_deallocate(v92);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v92);
  std::wstring::_Tidy_deallocate(v93);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v93);
  std::wstring::_Tidy_deallocate(v94);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v94);
  std::wstring::_Tidy_deallocate(v95);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v95);
  std::wstring::_Tidy_deallocate(v96);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v96);
  std::wstring::_Tidy_deallocate(v97);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v97);
  std::wstring::_Tidy_deallocate(v98);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v98);
  std::wstring::_Tidy_deallocate(v99);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v99);
  std::wstring::_Tidy_deallocate(v100);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v100);
  std::wstring::_Tidy_deallocate(v101);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v101);
  std::wstring::_Tidy_deallocate(v102);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v102);
  std::wstring::_Tidy_deallocate(v103);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v103);
  std::wstring::_Tidy_deallocate(v104);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v104);
  std::wstring::_Tidy_deallocate(v105);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v105);
  std::wstring::_Tidy_deallocate(v106);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v106);
  std::wstring::_Tidy_deallocate(v107);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v107);
  std::wstring::_Tidy_deallocate(v108);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v108);
  std::wstring::_Tidy_deallocate(v109);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v109);
  std::wstring::_Tidy_deallocate(v110);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v110);
  std::wstring::_Tidy_deallocate(v111);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v111);
  std::wstring::_Tidy_deallocate(v112);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v112);
  std::wstring::_Tidy_deallocate(v113);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v113);
  std::wstring::_Tidy_deallocate(v114);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v114);
  std::wstring::_Tidy_deallocate(v115);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v115);
  std::wstring::_Tidy_deallocate(v116);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v116);
  std::wstring::_Tidy_deallocate(v117);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v117);
  std::wstring::_Tidy_deallocate(v118);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::set_buffer_size(v118);
  return atexit(dynamic_atexit_destructor_for__s_ApduCommandsMap__);
}

```

## disassembly

```asm
0x18000bc30  mov     [rsp-8+arg_0], rbx
0x18000bc35  mov     [rsp-8+arg_8], rdi
0x18000bc3a  push    rbp
0x18000bc3b  lea     rbp, [rsp-0A30h]
0x18000bc43  sub     rsp, 0B30h
0x18000bc4a  mov     rax, cs:__security_cookie
0x18000bc51  xor     rax, rsp
0x18000bc54  mov     [rbp+0A30h+var_10], rax
0x18000bc5b  mov     ebx, 0BF20h
0x18000bc60  mov     [rsp+0B30h+var_B10], bx
0x18000bc65  lea     rdx, aEuiccinfo1_0; "EUICCInfo1"
0x18000bc6c  lea     rcx, [rbp+0A30h+var_620]
0x18000bc73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bc78  nop
0x18000bc79  mov     r8, rax
0x18000bc7c  lea     rdx, [rsp+0B30h+var_B10]
0x18000bc81  lea     rcx, [rbp+0A30h+var_600]
0x18000bc88  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bc8d  nop
0x18000bc8e  lea     edi, [rbx+2]
0x18000bc91  mov     [rsp+0B30h+var_B0E], di
0x18000bc96  lea     rdx, aEuiccinfo2_1; "EUICCInfo2"
0x18000bc9d  lea     rcx, [rbp+0A30h+var_640]
0x18000bca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bca9  nop
0x18000bcaa  mov     r8, rax
0x18000bcad  lea     rdx, [rsp+0B30h+var_B0E]
0x18000bcb2  lea     rcx, [rbp+0A30h+var_5D8]
0x18000bcb9  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bcbe  nop
0x18000bcbf  lea     eax, [rbx+0Ah]
0x18000bcc2  mov     [rsp+0B30h+var_B0C], ax
0x18000bcc7  lea     rdx, aUpdatemetadata_1; "UpdateMetadataRequest"
0x18000bcce  lea     rcx, [rbp+0A30h+var_660]
0x18000bcd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bcda  nop
0x18000bcdb  mov     r8, rax
0x18000bcde  lea     rdx, [rsp+0B30h+var_B0C]
0x18000bce3  lea     rcx, [rbp+0A30h+var_5B0]
0x18000bcea  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bcef  nop
0x18000bcf0  lea     eax, [rbx+3]
0x18000bcf3  mov     [rsp+0B30h+var_B0A], ax
0x18000bcf8  lea     rdx, aInitialisesecu_1; "InitialiseSecureChannelRequest"
0x18000bcff  lea     rcx, [rbp+0A30h+var_680]
0x18000bd06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bd0b  nop
0x18000bd0c  mov     r8, rax
0x18000bd0f  lea     rdx, [rsp+0B30h+var_B0A]
0x18000bd14  lea     rcx, [rbp+0A30h+var_588]
0x18000bd1b  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bd20  nop
0x18000bd21  lea     eax, [rbx+5]
0x18000bd24  mov     [rsp+0B30h+var_B08], ax
0x18000bd29  lea     rdx, aStoremetadatar_0; "StoreMetadataRequest"
0x18000bd30  lea     rcx, [rbp+0A30h+var_6A0]
0x18000bd37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bd3c  nop
0x18000bd3d  mov     r8, rax
0x18000bd40  lea     rdx, [rsp+0B30h+var_B08]
0x18000bd45  lea     rcx, [rbp+0A30h+var_560]
0x18000bd4c  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bd51  nop
0x18000bd52  lea     eax, [rbx+6]
0x18000bd55  mov     [rsp+0B30h+var_B06], ax
0x18000bd5a  lea     rdx, aReplacesession; "ReplaceSessionKeysRequest"
0x18000bd61  lea     rcx, [rbp+0A30h+var_6C0]
0x18000bd68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bd6d  nop
0x18000bd6e  mov     r8, rax
0x18000bd71  lea     rdx, [rsp+0B30h+var_B06]
0x18000bd76  lea     rcx, [rbp+0A30h+var_538]
0x18000bd7d  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bd82  nop
0x18000bd83  lea     eax, [rbx+22h]
0x18000bd86  mov     [rsp+0B30h+var_B04], ax
0x18000bd8b  lea     rdx, aLpaeactivation; "LpaeActivationRequest"
0x18000bd92  lea     rcx, [rbp+0A30h+var_6E0]
0x18000bd99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bd9e  nop
0x18000bd9f  mov     r8, rax
0x18000bda2  lea     rdx, [rsp+0B30h+var_B04]
0x18000bda7  lea     rcx, [rbp+0A30h+var_510]
0x18000bdae  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bdb3  nop
0x18000bdb4  lea     eax, [rbx+1Ch]
0x18000bdb7  mov     [rsp+0B30h+var_B02], ax
0x18000bdbc  lea     rdx, aEuiccconfigure_0; "EuiccConfiguredDataRequest"
0x18000bdc3  lea     rcx, [rbp+0A30h+var_700]
0x18000bdca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bdcf  nop
0x18000bdd0  mov     r8, rax
0x18000bdd3  lea     rdx, [rsp+0B30h+var_B02]
0x18000bdd8  lea     rcx, [rbp+0A30h+var_4E8]
0x18000bddf  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bde4  nop
0x18000bde5  lea     eax, [rbx+1Fh]
0x18000bde8  mov     [rsp+0B30h+var_B00], ax
0x18000bded  lea     rdx, aSetdefaultdpad_1; "SetDefaultDpAddressRequest"
0x18000bdf4  lea     rcx, [rbp+0A30h+var_720]
0x18000bdfb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000be00  nop
0x18000be01  mov     r8, rax
0x18000be04  lea     rdx, [rsp+0B30h+var_B00]
0x18000be09  lea     rcx, [rbp+0A30h+var_4C0]
0x18000be10  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000be15  nop
0x18000be16  lea     eax, [rbx+25h]
0x18000be19  mov     [rsp+0B30h+var_AFE], ax
0x18000be1e  lea     rdx, aVerifyeventlis; "VerifyEventListRequest"
0x18000be25  lea     rcx, [rbp+0A30h+var_740]
0x18000be2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000be31  nop
0x18000be32  mov     r8, rax
0x18000be35  lea     rdx, [rsp+0B30h+var_AFE]
0x18000be3a  lea     rcx, [rbp+0A30h+var_498]
0x18000be41  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000be46  nop
0x18000be47  lea     eax, [rbx+1]
0x18000be4a  mov     [rsp+0B30h+var_AFC], ax
0x18000be4f  lea     rdx, aPreparedownloa_1; "PrepareDownloadRequest"
0x18000be56  lea     rcx, [rbp+0A30h+var_760]
0x18000be5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000be62  nop
0x18000be63  mov     r8, rax
0x18000be66  lea     rdx, [rsp+0B30h+var_AFC]
0x18000be6b  lea     rcx, [rbp+0A30h+var_470]
0x18000be72  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000be77  nop
0x18000be78  lea     eax, [rbx+0Eh]
0x18000be7b  mov     [rsp+0B30h+var_AFA], ax
0x18000be80  lea     rdx, aGeteuiccchalle_0; "GetEuiccChallengeRequest"
0x18000be87  lea     rcx, [rbp+0A30h+var_780]
0x18000be8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000be93  nop
0x18000be94  mov     r8, rax
0x18000be97  lea     rdx, [rsp+0B30h+var_AFA]
0x18000be9c  lea     rcx, [rbp+0A30h+var_448]
0x18000bea3  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bea8  nop
0x18000bea9  mov     [rsp+0B30h+var_AF8], bx
0x18000beae  lea     rdx, aGeteuiccinfo1r; "GetEuiccInfo1Request"
0x18000beb5  lea     rcx, [rbp+0A30h+var_7A0]
0x18000bebc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bec1  nop
0x18000bec2  mov     r8, rax
0x18000bec5  lea     rdx, [rsp+0B30h+var_AF8]
0x18000beca  lea     rcx, [rbp+0A30h+var_420]
0x18000bed1  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bed6  nop
0x18000bed7  mov     [rsp+0B30h+var_AF6], di
0x18000bedc  lea     rdx, aGeteuiccinfo2r_0; "GetEuiccInfo2Request"
0x18000bee3  lea     rcx, [rbp+0A30h+var_7C0]
0x18000beea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000beef  nop
0x18000bef0  mov     r8, rax
0x18000bef3  lea     rdx, [rsp+0B30h+var_AF6]
0x18000bef8  lea     rcx, [rbp+0A30h+var_3F8]
0x18000beff  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bf04  nop
0x18000bf05  mov     [rsp+0B30h+var_AF4], di
0x18000bf0a  lea     rdx, aGeteuiccinfo2r_0; "GetEuiccInfo2Request"
0x18000bf11  lea     rcx, [rbp+0A30h+var_7E0]
0x18000bf18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bf1d  nop
0x18000bf1e  mov     r8, rax
0x18000bf21  lea     rdx, [rsp+0B30h+var_AF4]
0x18000bf26  lea     rcx, [rbp+0A30h+var_3D0]
0x18000bf2d  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bf32  nop
0x18000bf33  lea     eax, [rbx+8]
0x18000bf36  mov     [rsp+0B30h+var_AF2], ax
0x18000bf3b  lea     rdx, aListnotificati; "ListNotificationRequest"
0x18000bf42  lea     rcx, [rbp+0A30h+var_800]
0x18000bf49  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bf4e  nop
0x18000bf4f  mov     r8, rax
0x18000bf52  lea     rdx, [rsp+0B30h+var_AF2]
0x18000bf57  lea     rcx, [rbp+0A30h+var_3A8]
0x18000bf5e  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bf63  nop
0x18000bf64  lea     eax, [rbx+0Fh]
0x18000bf67  mov     [rsp+0B30h+var_AF0], ax
0x18000bf6c  lea     rdx, aNotificationme_0; "NotificationMetadata"
0x18000bf73  lea     rcx, [rbp+0A30h+var_820]
0x18000bf7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bf7f  nop
0x18000bf80  mov     r8, rax
0x18000bf83  lea     rdx, [rsp+0B30h+var_AF0]
0x18000bf88  lea     rcx, [rbp+0A30h+var_380]
0x18000bf8f  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bf94  nop
0x18000bf95  lea     eax, [rbx+0Bh]
0x18000bf98  mov     [rsp+0B30h+var_AEE], ax
0x18000bf9d  lea     rdx, aRetrievenotifi_1; "RetrieveNotificationsListRequest"
0x18000bfa4  lea     rcx, [rbp+0A30h+var_840]
0x18000bfab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bfb0  nop
0x18000bfb1  mov     r8, rax
0x18000bfb4  lea     rdx, [rsp+0B30h+var_AEE]
0x18000bfb9  lea     rcx, [rbp+0A30h+var_358]
0x18000bfc0  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bfc5  nop
0x18000bfc6  lea     eax, [rbx+10h]
0x18000bfc9  mov     [rsp+0B30h+var_AEC], ax
0x18000bfce  lea     rdx, aNotificationse_0; "NotificationSentRequest"
0x18000bfd5  lea     rcx, [rbp+0A30h+var_860]
0x18000bfdc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000bfe1  nop
0x18000bfe2  mov     r8, rax
0x18000bfe5  lea     rdx, [rsp+0B30h+var_AEC]
0x18000bfea  lea     rcx, [rbp+0A30h+var_330]
0x18000bff1  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000bff6  nop
0x18000bff7  lea     eax, [rbx+18h]
0x18000bffa  mov     [rsp+0B30h+var_AEA], ax
0x18000bfff  lea     rdx, aAuthenticatese_2; "AuthenticateServerRequest"
0x18000c006  lea     rcx, [rbp+0A30h+var_880]
0x18000c00d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c012  nop
0x18000c013  mov     r8, rax
0x18000c016  lea     rdx, [rsp+0B30h+var_AEA]
0x18000c01b  lea     rcx, [rbp+0A30h+var_308]
0x18000c022  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c027  nop
0x18000c028  lea     eax, [rbx+21h]
0x18000c02b  mov     [rsp+0B30h+var_AE8], ax
0x18000c030  lea     rdx, aCancelsessionr_2; "CancelSessionRequest"
0x18000c037  lea     rcx, [rbp+0A30h+var_8A0]
0x18000c03e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c043  nop
0x18000c044  mov     r8, rax
0x18000c047  lea     rdx, [rsp+0B30h+var_AE8]
0x18000c04c  lea     rcx, [rbp+0A30h+var_2E0]
0x18000c053  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c058  nop
0x18000c059  lea     eax, [rbx+26h]
0x18000c05c  mov     [rsp+0B30h+var_AE6], ax
0x18000c061  lea     rdx, aLoadrpmpackage_0; "LoadRpmPackageRequest"
0x18000c068  lea     rcx, [rbp+0A30h+var_8C0]
0x18000c06f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c074  nop
0x18000c075  mov     r8, rax
0x18000c078  lea     rdx, [rsp+0B30h+var_AE6]
0x18000c07d  lea     rcx, [rbp+0A30h+var_2B8]
0x18000c084  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c089  nop
0x18000c08a  lea     eax, [rbx+29h]
0x18000c08d  mov     [rsp+0B30h+var_AE4], ax
0x18000c092  lea     rdx, aVerifycommandc; "VerifyCommandCodeRequest"
0x18000c099  lea     rcx, [rbp+0A30h+var_8E0]
0x18000c0a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c0a5  nop
0x18000c0a6  mov     r8, rax
0x18000c0a9  lea     rdx, [rsp+0B30h+var_AE4]
0x18000c0ae  lea     rcx, [rbp+0A30h+var_290]
0x18000c0b5  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c0ba  nop
0x18000c0bb  lea     eax, [rbx+0Dh]
0x18000c0be  mov     [rsp+0B30h+var_AE2], ax
0x18000c0c3  lea     rdx, aProfileinfolis_3; "ProfileInfoListRequest"
0x18000c0ca  lea     rcx, [rbp+0A30h+var_900]
0x18000c0d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c0d6  nop
0x18000c0d7  mov     r8, rax
0x18000c0da  lea     rdx, [rsp+0B30h+var_AE2]
0x18000c0df  lea     rcx, [rbp+0A30h+var_268]
0x18000c0e6  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c0eb  nop
0x18000c0ec  lea     eax, [rbx+11h]
0x18000c0ef  mov     [rsp+0B30h+var_AE0], ax
0x18000c0f4  lea     rdx, aEnableprofiler; "EnableProfileRequest"
0x18000c0fb  lea     rcx, [rbp+0A30h+var_920]
0x18000c102  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c107  nop
0x18000c108  mov     r8, rax
0x18000c10b  lea     rdx, [rsp+0B30h+var_AE0]
0x18000c110  lea     rcx, [rbp+0A30h+var_240]
0x18000c117  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c11c  nop
0x18000c11d  lea     eax, [rbx+12h]
0x18000c120  mov     [rsp+0B30h+var_ADE], ax
0x18000c125  lea     rdx, aDisableprofile_0; "DisableProfileRequest"
0x18000c12c  lea     rcx, [rbp+0A30h+var_940]
0x18000c133  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c138  nop
0x18000c139  mov     r8, rax
0x18000c13c  lea     rdx, [rsp+0B30h+var_ADE]
0x18000c141  lea     rcx, [rbp+0A30h+var_218]
0x18000c148  call    ??$?0GV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$pair@$$CBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAG$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::pair<ushort const,std::wstring>::pair<ushort const,std::wstring>(ushort &&,std::wstring &&)
0x18000c14d  nop
0x18000c14e  lea     eax, [rbx+13h]
0x18000c151  mov     [rsp+0B30h+var_ADC], ax
0x18000c156  lea     rdx, aDeleteprofiler_1; "DeleteProfileRequest"
0x18000c15d  lea     rcx, [rbp+0A30h+var_960]
0x18000c164  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000c169  nop
0x18000c16a  mov     r8, rax
0x18000c16d  lea     rdx, [rsp+0B30h+var_ADC]
0x18000c172  lea     rcx, [rbp+0A30h+var_1F0]
  ... truncated ...
```
