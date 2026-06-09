# ReadInstallationConfig(InstallationConfigInfo &)

- ea: `0x140019fc4`
- end: `0x14001a58e`
- name: `?ReadInstallationConfig@@YAJAEAUInstallationConfigInfo@@@Z`
- size: `1482`
- prototype: `__int64 __fastcall(struct InstallationConfigInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140002c10`
- `0x140004950`
- `0x140019fc4`
- `0x14001a590`
- `0x1400283cc`
- `0x14002c814`
- `0x140033ab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14001a398`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14001a398`

## string_xrefs

- `0x14001a0e9`: `ChannelManifestId`
- `0x14001a1af`: `InstallationName`
- `0x14001a1f1`: `InstallationVersion`
- `0x14001a233`: `InstallationUserDataFilePath`
- `0x14001a275`: `InstallationLogsDirectory`
- `0x14001a2f9`: `SetupEngineFilePath`
- `0x14001a4d0`: `InstallationWorkloads`
- `0x14001a512`: `InstallationPackages`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ReadInstallationConfig(struct InstallationConfigInfo *a1)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  int updated; // edi
  unsigned __int16 *v3; // rbx
  __int64 v4; // rcx
  __int64 Value; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rdx
  __int64 v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  _QWORD *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rcx
  _QWORD *v43; // rdx
  const wchar_t **v44; // rax
  __int64 v45; // rcx
  _QWORD *v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  _QWORD *v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rcx
  _QWORD *v52; // rdx
  __int64 v53; // rax
  __int64 v54; // rcx
  _QWORD *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rcx
  _QWORD *v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rcx
  _QWORD *v61; // rdx
  __int64 v62; // rax
  _QWORD *v63; // rdx
  unsigned __int16 *v65; // [rsp+40h] [rbp+20h] BYREF
  __int64 v66; // [rsp+48h] [rbp+28h] BYREF
  __int64 v67; // [rsp+50h] [rbp+30h] BYREF

  v65 = (unsigned __int16 *)a1;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v65 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                           + 24);
  updated = anonymous_namespace_::ComputeIsolationFilePath(&v65);
  v3 = v65;
  if ( updated >= 0 )
  {
    updated = UpdateIsolationConfigCache(v65);
    if ( updated >= 0 )
    {
      Value = CIsolationFile::GetValue(v4, &v66, L"AlphaPacksCount");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0B8, Value);
      v7 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
      }
      v8 = CIsolationFile::GetValue(v6, &v67, L"CampaignId");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0C0, v8);
      v10 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
      }
      v11 = CIsolationFile::GetValue(v9, &v66, L"ChannelId");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0C8, v11);
      v13 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
      }
      v14 = CIsolationFile::GetValue(v12, &v67, L"ChannelManifestId");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0D0, v14);
      v16 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
      }
      v17 = CIsolationFile::GetValue(v15, &v66, L"ChannelTitle");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0D8, v17);
      v19 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
      }
      v20 = CIsolationFile::GetValue(v18, &v67, L"ChannelSuffix");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0E0, v20);
      v22 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
      }
      v23 = CIsolationFile::GetValue(v21, &v66, L"InstallationName");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0E8, v23);
      v25 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
      }
      v26 = CIsolationFile::GetValue(v24, &v67, L"InstallationVersion");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0F0, v26);
      v28 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 8LL))(*v28);
      }
      v29 = CIsolationFile::GetValue(v27, &v66, L"InstallationUserDataFilePath");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D108, v29);
      v31 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 8LL))(*v31);
      }
      v32 = CIsolationFile::GetValue(v30, &v67, L"InstallationLogsDirectory");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D110, v32);
      v34 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 8LL))(*v34);
      }
      v35 = CIsolationFile::GetValue(v33, &v66, L"ProductArch");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D118, v35);
      v37 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v37 + 8LL))(*v37);
      }
      v38 = CIsolationFile::GetValue(v36, &v67, L"SetupEngineFilePath");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D120, v38);
      v40 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
      }
      v41 = CIsolationFile::GetValue(v39, &v66, L"SetupResult");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D128, v41);
      v43 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v43 + 8LL))(*v43);
      }
      v44 = (const wchar_t **)CIsolationFile::GetValue(v42, &v67, L"SetupFinished");
      CAppIdExtImpl::m_installationConfigInfo = _wcsicmp(*v44, L"true") == 0;
      v46 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v46 + 8LL))(*v46);
      }
      v47 = CIsolationFile::GetValue(v45, &v66, L"SKU");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&lpValue, v47);
      v49 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v49 + 8LL))(*v49);
      }
      v50 = CIsolationFile::GetValue(v48, &v67, L"Nickname");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D138, v50);
      v52 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v52 + 8LL))(*v52);
      }
      v53 = CIsolationFile::GetValue(v51, &v66, L"DisplayVersion");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D140, v53);
      v55 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v55 + 8LL))(*v55);
      }
      v56 = CIsolationFile::GetValue(v54, &v67, L"SemanticVersion");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D148, v56);
      v58 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v58 + 8LL))(*v58);
      }
      v59 = CIsolationFile::GetValue(v57, &v66, L"InstallationWorkloads");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D0F8, v59);
      v61 = (_QWORD *)(v66 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v61 + 8LL))(*v61);
      }
      v62 = CIsolationFile::GetValue(v60, &v67, L"InstallationPackages");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&qword_14009D100, v62);
      v63 = (_QWORD *)(v67 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v67 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v63 + 8LL))(*v63);
      }
      updated = 0;
    }
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)v3 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v3 - 3) + 8LL))(*((_QWORD *)v3 - 3));
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140019fc4  mov     [rsp-18h+arg_18], rbx
0x140019fc9  mov     [rsp-18h+arg_0], rcx
0x140019fce  push    rbp
0x140019fcf  push    rsi
0x140019fd0  push    rdi
0x140019fd1  mov     rbp, rsp
0x140019fd4  sub     rsp, 20h
0x140019fd8  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140019fdd  mov     rcx, rax
0x140019fe0  test    rax, rax
0x140019fe3  jz      loc_14001A583
0x140019fe9  mov     rax, [rax]
0x140019fec  call    qword ptr [rax+18h]
0x140019fef  add     rax, 18h
0x140019ff3  mov     [rbp+arg_0], rax
0x140019ff7  lea     rcx, [rbp+arg_0]
0x140019ffb  call    _anonymous_namespace___ComputeIsolationFilePath
0x14001a000  mov     edi, eax
0x14001a002  or      esi, 0FFFFFFFFh
0x14001a005  mov     rbx, [rbp+arg_0]
0x14001a009  test    eax, eax
0x14001a00b  js      loc_14001A556
0x14001a011  mov     rcx, rbx; unsigned __int16 *
0x14001a014  call    ?UpdateIsolationConfigCache@@YAJPEBG@Z; UpdateIsolationConfigCache(ushort const *)
0x14001a019  mov     edi, eax
0x14001a01b  test    eax, eax
0x14001a01d  js      loc_14001A556
0x14001a023  lea     r8, aAlphapackscoun; "AlphaPacksCount"
0x14001a02a  lea     rdx, [rbp+arg_8]
0x14001a02e  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a033  nop
0x14001a034  mov     rdx, rax
0x14001a037  lea     rcx, qword_14009D0B8
0x14001a03e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a043  nop
0x14001a044  mov     rdx, [rbp+arg_8]
0x14001a048  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a04c  mov     eax, esi
0x14001a04e  lock xadd [rdx+10h], eax
0x14001a053  add     eax, esi
0x14001a055  test    eax, eax
0x14001a057  jg      short loc_14001A065
0x14001a059  lfence
0x14001a05c  mov     rcx, [rdx]
0x14001a05f  mov     rax, [rcx]
0x14001a062  call    qword ptr [rax+8]
0x14001a065  lea     r8, aCampaignid; "CampaignId"
0x14001a06c  lea     rdx, [rbp+arg_10]
0x14001a070  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a075  nop
0x14001a076  mov     rdx, rax
0x14001a079  lea     rcx, qword_14009D0C0
0x14001a080  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a085  nop
0x14001a086  mov     rdx, [rbp+arg_10]
0x14001a08a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a08e  mov     eax, esi
0x14001a090  lock xadd [rdx+10h], eax
0x14001a095  add     eax, esi
0x14001a097  test    eax, eax
0x14001a099  jg      short loc_14001A0A7
0x14001a09b  lfence
0x14001a09e  mov     rcx, [rdx]
0x14001a0a1  mov     rax, [rcx]
0x14001a0a4  call    qword ptr [rax+8]
0x14001a0a7  lea     r8, aChannelid; "ChannelId"
0x14001a0ae  lea     rdx, [rbp+arg_8]
0x14001a0b2  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a0b7  nop
0x14001a0b8  mov     rdx, rax
0x14001a0bb  lea     rcx, qword_14009D0C8
0x14001a0c2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a0c7  nop
0x14001a0c8  mov     rdx, [rbp+arg_8]
0x14001a0cc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a0d0  mov     eax, esi
0x14001a0d2  lock xadd [rdx+10h], eax
0x14001a0d7  add     eax, esi
0x14001a0d9  test    eax, eax
0x14001a0db  jg      short loc_14001A0E9
0x14001a0dd  lfence
0x14001a0e0  mov     rcx, [rdx]
0x14001a0e3  mov     rax, [rcx]
0x14001a0e6  call    qword ptr [rax+8]
0x14001a0e9  lea     r8, aChannelmanifes; "ChannelManifestId"
0x14001a0f0  lea     rdx, [rbp+arg_10]
0x14001a0f4  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a0f9  nop
0x14001a0fa  mov     rdx, rax
0x14001a0fd  lea     rcx, qword_14009D0D0
0x14001a104  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a109  nop
0x14001a10a  mov     rdx, [rbp+arg_10]
0x14001a10e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a112  mov     eax, esi
0x14001a114  lock xadd [rdx+10h], eax
0x14001a119  add     eax, esi
0x14001a11b  test    eax, eax
0x14001a11d  jg      short loc_14001A12B
0x14001a11f  lfence
0x14001a122  mov     rcx, [rdx]
0x14001a125  mov     rax, [rcx]
0x14001a128  call    qword ptr [rax+8]
0x14001a12b  lea     r8, aChanneltitle; "ChannelTitle"
0x14001a132  lea     rdx, [rbp+arg_8]
0x14001a136  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a13b  nop
0x14001a13c  mov     rdx, rax
0x14001a13f  lea     rcx, qword_14009D0D8
0x14001a146  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a14b  nop
0x14001a14c  mov     rdx, [rbp+arg_8]
0x14001a150  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a154  mov     eax, esi
0x14001a156  lock xadd [rdx+10h], eax
0x14001a15b  add     eax, esi
0x14001a15d  test    eax, eax
0x14001a15f  jg      short loc_14001A16D
0x14001a161  lfence
0x14001a164  mov     rcx, [rdx]
0x14001a167  mov     rax, [rcx]
0x14001a16a  call    qword ptr [rax+8]
0x14001a16d  lea     r8, aChannelsuffix; "ChannelSuffix"
0x14001a174  lea     rdx, [rbp+arg_10]
0x14001a178  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a17d  nop
0x14001a17e  mov     rdx, rax
0x14001a181  lea     rcx, qword_14009D0E0
0x14001a188  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a18d  nop
0x14001a18e  mov     rdx, [rbp+arg_10]
0x14001a192  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a196  mov     eax, esi
0x14001a198  lock xadd [rdx+10h], eax
0x14001a19d  add     eax, esi
0x14001a19f  test    eax, eax
0x14001a1a1  jg      short loc_14001A1AF
0x14001a1a3  lfence
0x14001a1a6  mov     rcx, [rdx]
0x14001a1a9  mov     rax, [rcx]
0x14001a1ac  call    qword ptr [rax+8]
0x14001a1af  lea     r8, aInstallationna; "InstallationName"
0x14001a1b6  lea     rdx, [rbp+arg_8]
0x14001a1ba  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a1bf  nop
0x14001a1c0  mov     rdx, rax
0x14001a1c3  lea     rcx, qword_14009D0E8
0x14001a1ca  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a1cf  nop
0x14001a1d0  mov     rdx, [rbp+arg_8]
0x14001a1d4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a1d8  mov     eax, esi
0x14001a1da  lock xadd [rdx+10h], eax
0x14001a1df  add     eax, esi
0x14001a1e1  test    eax, eax
0x14001a1e3  jg      short loc_14001A1F1
0x14001a1e5  lfence
0x14001a1e8  mov     rcx, [rdx]
0x14001a1eb  mov     rax, [rcx]
0x14001a1ee  call    qword ptr [rax+8]
0x14001a1f1  lea     r8, aInstallationve; "InstallationVersion"
0x14001a1f8  lea     rdx, [rbp+arg_10]
0x14001a1fc  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a201  nop
0x14001a202  mov     rdx, rax
0x14001a205  lea     rcx, qword_14009D0F0
0x14001a20c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a211  nop
0x14001a212  mov     rdx, [rbp+arg_10]
0x14001a216  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a21a  mov     eax, esi
0x14001a21c  lock xadd [rdx+10h], eax
0x14001a221  add     eax, esi
0x14001a223  test    eax, eax
0x14001a225  jg      short loc_14001A233
0x14001a227  lfence
0x14001a22a  mov     rcx, [rdx]
0x14001a22d  mov     rax, [rcx]
0x14001a230  call    qword ptr [rax+8]
0x14001a233  lea     r8, aInstallationus; "InstallationUserDataFilePath"
0x14001a23a  lea     rdx, [rbp+arg_8]
0x14001a23e  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a243  nop
0x14001a244  mov     rdx, rax
0x14001a247  lea     rcx, qword_14009D108
0x14001a24e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a253  nop
0x14001a254  mov     rdx, [rbp+arg_8]
0x14001a258  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a25c  mov     eax, esi
0x14001a25e  lock xadd [rdx+10h], eax
0x14001a263  add     eax, esi
0x14001a265  test    eax, eax
0x14001a267  jg      short loc_14001A275
0x14001a269  lfence
0x14001a26c  mov     rcx, [rdx]
0x14001a26f  mov     rax, [rcx]
0x14001a272  call    qword ptr [rax+8]
0x14001a275  lea     r8, aInstallationlo; "InstallationLogsDirectory"
0x14001a27c  lea     rdx, [rbp+arg_10]
0x14001a280  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a285  nop
0x14001a286  mov     rdx, rax
0x14001a289  lea     rcx, qword_14009D110
0x14001a290  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a295  nop
0x14001a296  mov     rdx, [rbp+arg_10]
0x14001a29a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a29e  mov     eax, esi
0x14001a2a0  lock xadd [rdx+10h], eax
0x14001a2a5  add     eax, esi
0x14001a2a7  test    eax, eax
0x14001a2a9  jg      short loc_14001A2B7
0x14001a2ab  lfence
0x14001a2ae  mov     rcx, [rdx]
0x14001a2b1  mov     rax, [rcx]
0x14001a2b4  call    qword ptr [rax+8]
0x14001a2b7  lea     r8, aProductarch; "ProductArch"
0x14001a2be  lea     rdx, [rbp+arg_8]
0x14001a2c2  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a2c7  nop
0x14001a2c8  mov     rdx, rax
0x14001a2cb  lea     rcx, qword_14009D118
0x14001a2d2  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a2d7  nop
0x14001a2d8  mov     rdx, [rbp+arg_8]
0x14001a2dc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a2e0  mov     eax, esi
0x14001a2e2  lock xadd [rdx+10h], eax
0x14001a2e7  add     eax, esi
0x14001a2e9  test    eax, eax
0x14001a2eb  jg      short loc_14001A2F9
0x14001a2ed  lfence
0x14001a2f0  mov     rcx, [rdx]
0x14001a2f3  mov     rax, [rcx]
0x14001a2f6  call    qword ptr [rax+8]
0x14001a2f9  lea     r8, aSetupenginefil; "SetupEngineFilePath"
0x14001a300  lea     rdx, [rbp+arg_10]
0x14001a304  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a309  nop
0x14001a30a  mov     rdx, rax
0x14001a30d  lea     rcx, qword_14009D120
0x14001a314  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a319  nop
0x14001a31a  mov     rdx, [rbp+arg_10]
0x14001a31e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a322  mov     eax, esi
0x14001a324  lock xadd [rdx+10h], eax
0x14001a329  add     eax, esi
0x14001a32b  test    eax, eax
0x14001a32d  jg      short loc_14001A33B
0x14001a32f  lfence
0x14001a332  mov     rcx, [rdx]
0x14001a335  mov     rax, [rcx]
0x14001a338  call    qword ptr [rax+8]
0x14001a33b  lea     r8, aSetupresult; "SetupResult"
0x14001a342  lea     rdx, [rbp+arg_8]
0x14001a346  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a34b  nop
0x14001a34c  mov     rdx, rax
0x14001a34f  lea     rcx, qword_14009D128
0x14001a356  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001a35b  nop
0x14001a35c  mov     rdx, [rbp+arg_8]
0x14001a360  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a364  mov     eax, esi
0x14001a366  lock xadd [rdx+10h], eax
0x14001a36b  add     eax, esi
0x14001a36d  test    eax, eax
0x14001a36f  jg      short loc_14001A37D
0x14001a371  lfence
0x14001a374  mov     rcx, [rdx]
0x14001a377  mov     rax, [rcx]
0x14001a37a  call    qword ptr [rax+8]
0x14001a37d  lea     r8, aSetupfinished; "SetupFinished"
0x14001a384  lea     rdx, [rbp+arg_10]
0x14001a388  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a38d  nop
0x14001a38e  lea     rdx, aTrue; "true"
0x14001a395  mov     rcx, [rax]; String1
0x14001a398  call    cs:__imp__wcsicmp
0x14001a39e  test    eax, eax
0x14001a3a0  setz    cs:?m_installationConfigInfo@CAppIdExtImpl@@1UInstallationConfigInfo@@A; InstallationConfigInfo CAppIdExtImpl::m_installationConfigInfo
0x14001a3a7  mov     rdx, [rbp+arg_10]
0x14001a3ab  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001a3af  mov     eax, esi
0x14001a3b1  lock xadd [rdx+10h], eax
0x14001a3b6  add     eax, esi
0x14001a3b8  test    eax, eax
0x14001a3ba  jg      short loc_14001A3C8
0x14001a3bc  lfence
0x14001a3bf  mov     rcx, [rdx]
0x14001a3c2  mov     rax, [rcx]
0x14001a3c5  call    qword ptr [rax+8]
0x14001a3c8  lea     r8, aSku; "SKU"
0x14001a3cf  lea     rdx, [rbp+arg_8]
0x14001a3d3  call    ?GetValue@CIsolationFile@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; CIsolationFile::GetValue(ushort const *)
0x14001a3d8  nop
0x14001a3d9  mov     rdx, rax
0x14001a3dc  lea     rcx, lpValue
  ... truncated ...
```
