# Debugger::DataModel::Libraries::KernelTargetDetails::DumpFileDetails::AddKernelVersionDetailsKdData(Debugger::DataModel::ClientEx::Object const &)

- ea: `0x1803af5f0`
- end: `0x1803b3938`
- name: `?AddKernelVersionDetailsKdData@DumpFileDetails@KernelTargetDetails@Libraries@DataModel@Debugger@@QEAA?AVObject@ClientEx@45@AEBV6745@@Z`
- size: `17224`
- prototype: `struct Debugger::DataModel::ClientEx::Object __high(const struct Debugger::DataModel::ClientEx::Object *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180075b88`
- `0x1800902b4`
- `0x1800ad4f4`
- `0x1800d3590`
- `0x1803ad5dc`
- `0x1803ad634`
- `0x1803ad8a0`
- `0x1803aee8c`
- `0x1803af5f0`
- `0x1803b3c9c`
- `0x1803b4210`
- `0x1804f4010`

## string_xrefs

- `0x1803af767`: `Blink`
- `0x1803af6f9`: `Flink`
- `0x1803b16c0`: `MmTotalCommitLimitMaximum`
- `0x1803b1657`: `MmPeakCommitment`
- `0x1803b18cd`: `MmSystemParentTablePage`
- `0x1803b1a08`: `OffsetKThreadTeb`
- `0x1803b1a71`: `OffsetKThreadKernelStack`
- `0x1803b199f`: `OffsetKThreadNextProcessor`
- `0x1803b1bac`: `OffsetKThreadState`
- `0x1803b1c15`: `OffsetKThreadBStore`
- `0x1803b1ada`: `OffsetKThreadInitialStack`
- `0x1803b1b43`: `OffsetKThreadApcProcess`
- `0x1803b1c7e`: `OffsetKThreadBStoreLimit`
- `0x1803b1f5d`: `OffsetPrcbCurrentThread`
- `0x1803b1e22`: `OffsetEprocessDirectoryTableBase`
- `0x1803b21d3`: `SizeEThread`
- `0x1803b2f69`: `OffsetKThreadStackLimit`
- `0x1803b2fd2`: `OffsetKThreadStackBase`
- `0x1803b310d`: `OffsetPrcbIdleThread`
- `0x1803b303b`: `OffsetKThreadQueueListEntry`
- `0x1803b30a4`: `OffsetEThreadIrpList`
- `0x1803b3327`: `OffsetKPriQueueThreadListHead`
- `0x1803b3390`: `OffsetKThreadWaitReason`
- `0x1803b3708`: `OffsetKThreadShadowStackLimit`
- `0x1803b3771`: `OffsetKThreadShadowStackBase`
- `0x1803afde5`: `ExpPagedPoolDescriptor`
- `0x1803b00c7`: `MmSystemCacheStart`
- `0x1803b000d`: `ObpRootDirectoryObject`
- `0x1803b023b`: `MmSystemPtesStart`
- `0x1803b0124`: `MmSystemCacheEnd`
- `0x1803b0181`: `MmSystemCacheWs`
- `0x1803b0298`: `MmSystemPtesEnd`
- `0x1803b07fc`: `MmSizeOfPagedPoolInBytes`
- `0x1803b0865`: `MmTotalCommitLimit`
- `0x1803b09a0`: `MmDriverCommit`
- `0x1803b0a09`: `MmProcessCommit`
- `0x1803b08ce`: `MmTotalCommittedPages`
- `0x1803b0937`: `MmSharedCommit`
- `0x1803b0a72`: `MmPagedPoolCommit`
- `0x1803b0adb`: `MmExtendedCommit`
- `0x1803b0ce8`: `MmModifiedNoWritePageListHead`
- `0x1803b0e8c`: `NonPagedPoolDescriptor`
- `0x1803b0dba`: `MmResidentAvailablePages`
- `0x1803b1102`: `KdPrintWritePointer`

## pseudocode

```c
// Hidden C++ exception states: #wind=173
const struct Debugger::DataModel::ClientEx::Object *__fastcall Debugger::DataModel::Libraries::KernelTargetDetails::DumpFileDetails::AddKernelVersionDetailsKdData(
        __int64 a1,
        const struct Debugger::DataModel::ClientEx::Object *a2,
        Debugger::DataModel::Libraries::KernelTargetDetails *a3)
{
  struct TargetInfo *TargetFromContext; // r14
  char *v5; // r14
  __int64 v6; // rdi
  __int64 *v7; // rcx
  __int64 *v8; // rcx
  __int64 v9; // rbx
  _DWORD *v10; // r15
  __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v33; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v35; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v39; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v40; // [rsp+100h] [rbp+0h] BYREF
  __int64 v41; // [rsp+108h] [rbp+8h] BYREF
  __int64 v42; // [rsp+110h] [rbp+10h] BYREF
  __int64 v43; // [rsp+118h] [rbp+18h] BYREF
  __int64 v44; // [rsp+120h] [rbp+20h] BYREF
  __int64 v45; // [rsp+128h] [rbp+28h] BYREF
  __int64 v46; // [rsp+130h] [rbp+30h] BYREF
  __int64 v47; // [rsp+138h] [rbp+38h] BYREF
  __int64 v48; // [rsp+140h] [rbp+40h] BYREF
  __int64 v49; // [rsp+148h] [rbp+48h] BYREF
  __int64 v50; // [rsp+150h] [rbp+50h] BYREF
  __int64 v51; // [rsp+158h] [rbp+58h] BYREF
  __int64 v52; // [rsp+160h] [rbp+60h] BYREF
  __int64 v53; // [rsp+168h] [rbp+68h] BYREF
  __int64 v54; // [rsp+170h] [rbp+70h] BYREF
  __int64 v55; // [rsp+178h] [rbp+78h] BYREF
  __int64 v56; // [rsp+180h] [rbp+80h] BYREF
  __int64 v57; // [rsp+188h] [rbp+88h] BYREF
  __int64 v58; // [rsp+190h] [rbp+90h] BYREF
  __int64 v59; // [rsp+198h] [rbp+98h] BYREF
  __int64 v60; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v61; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v62; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v63; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v64; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v65; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v66; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v67; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v68; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v69; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v70; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v71; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v72; // [rsp+200h] [rbp+100h] BYREF
  __int64 v73; // [rsp+208h] [rbp+108h] BYREF
  __int64 v74; // [rsp+210h] [rbp+110h] BYREF
  __int64 v75; // [rsp+218h] [rbp+118h] BYREF
  __int64 v76; // [rsp+220h] [rbp+120h] BYREF
  __int64 v77; // [rsp+228h] [rbp+128h] BYREF
  __int64 v78; // [rsp+230h] [rbp+130h] BYREF
  __int64 v79; // [rsp+238h] [rbp+138h] BYREF
  __int64 v80; // [rsp+240h] [rbp+140h] BYREF
  __int64 v81; // [rsp+248h] [rbp+148h] BYREF
  __int64 v82; // [rsp+250h] [rbp+150h] BYREF
  __int64 v83; // [rsp+258h] [rbp+158h] BYREF
  __int64 v84; // [rsp+260h] [rbp+160h] BYREF
  __int64 v85; // [rsp+268h] [rbp+168h] BYREF
  __int64 v86; // [rsp+270h] [rbp+170h] BYREF
  __int64 v87; // [rsp+278h] [rbp+178h] BYREF
  __int64 v88; // [rsp+280h] [rbp+180h] BYREF
  __int64 v89; // [rsp+288h] [rbp+188h] BYREF
  __int64 v90; // [rsp+290h] [rbp+190h] BYREF
  __int64 v91; // [rsp+298h] [rbp+198h] BYREF
  __int64 v92; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v93; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int64 v94; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v95; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v96; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v97; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int64 v98; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v99; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v100; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v101; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v102; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v103; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v104; // [rsp+300h] [rbp+200h] BYREF
  __int64 v105; // [rsp+308h] [rbp+208h] BYREF
  __int64 v106; // [rsp+310h] [rbp+210h] BYREF
  __int64 v107; // [rsp+318h] [rbp+218h] BYREF
  __int64 v108; // [rsp+320h] [rbp+220h] BYREF
  __int64 v109; // [rsp+328h] [rbp+228h] BYREF
  __int64 v110; // [rsp+330h] [rbp+230h] BYREF
  __int64 v111; // [rsp+338h] [rbp+238h] BYREF
  __int64 v112; // [rsp+340h] [rbp+240h] BYREF
  __int64 v113; // [rsp+348h] [rbp+248h] BYREF
  __int64 v114; // [rsp+350h] [rbp+250h] BYREF
  __int64 v115; // [rsp+358h] [rbp+258h] BYREF
  __int64 v116; // [rsp+360h] [rbp+260h] BYREF
  __int64 v117; // [rsp+368h] [rbp+268h] BYREF
  __int64 v118; // [rsp+370h] [rbp+270h] BYREF
  __int64 v119; // [rsp+378h] [rbp+278h] BYREF
  __int64 v120; // [rsp+380h] [rbp+280h] BYREF
  __int64 v121; // [rsp+388h] [rbp+288h] BYREF
  __int64 v122; // [rsp+390h] [rbp+290h] BYREF
  __int64 v123; // [rsp+398h] [rbp+298h] BYREF
  __int64 v124; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int64 v125; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int64 v126; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v127; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int64 v128; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v129; // [rsp+3C8h] [rbp+2C8h] BYREF
  __int64 v130; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v131; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v132; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int64 v133; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v134; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v135; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v136; // [rsp+400h] [rbp+300h] BYREF
  __int64 v137; // [rsp+408h] [rbp+308h] BYREF
  __int64 v138; // [rsp+410h] [rbp+310h] BYREF
  __int64 v139; // [rsp+418h] [rbp+318h] BYREF
  __int64 v140; // [rsp+420h] [rbp+320h] BYREF
  __int64 v141; // [rsp+428h] [rbp+328h] BYREF
  __int64 v142; // [rsp+430h] [rbp+330h] BYREF
  __int64 v143; // [rsp+438h] [rbp+338h] BYREF
  __int64 v144; // [rsp+440h] [rbp+340h] BYREF
  __int64 v145; // [rsp+448h] [rbp+348h] BYREF
  __int64 v146; // [rsp+450h] [rbp+350h] BYREF
  __int64 v147; // [rsp+458h] [rbp+358h] BYREF
  __int64 v148; // [rsp+460h] [rbp+360h] BYREF
  __int64 v149; // [rsp+468h] [rbp+368h] BYREF
  __int64 v150; // [rsp+470h] [rbp+370h] BYREF
  __int64 v151; // [rsp+478h] [rbp+378h] BYREF
  __int64 v152; // [rsp+480h] [rbp+380h] BYREF
  __int64 v153; // [rsp+488h] [rbp+388h] BYREF
  __int64 v154; // [rsp+490h] [rbp+390h] BYREF
  __int64 v155; // [rsp+498h] [rbp+398h] BYREF
  __int64 v156; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v157; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int64 v158; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v159; // [rsp+4B8h] [rbp+3B8h] BYREF
  __int64 v160; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v161; // [rsp+4C8h] [rbp+3C8h] BYREF
  __int64 v162; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v163; // [rsp+4D8h] [rbp+3D8h] BYREF
  __int64 v164; // [rsp+4E0h] [rbp+3E0h] BYREF
  __int64 v165; // [rsp+4E8h] [rbp+3E8h] BYREF
  __int64 v166; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v167; // [rsp+4F8h] [rbp+3F8h] BYREF
  __int64 v168; // [rsp+500h] [rbp+400h] BYREF
  __int64 v169; // [rsp+508h] [rbp+408h] BYREF
  __int64 v170; // [rsp+510h] [rbp+410h] BYREF
  __int64 v171; // [rsp+518h] [rbp+418h] BYREF
  __int64 v172; // [rsp+520h] [rbp+420h] BYREF
  __int64 v173; // [rsp+528h] [rbp+428h] BYREF
  __int64 v174; // [rsp+530h] [rbp+430h] BYREF
  __int64 v175; // [rsp+538h] [rbp+438h] BYREF
  __int64 v176; // [rsp+540h] [rbp+440h] BYREF
  __int64 v177; // [rsp+548h] [rbp+448h] BYREF
  __int64 v178; // [rsp+550h] [rbp+450h] BYREF
  __int64 v179; // [rsp+558h] [rbp+458h] BYREF
  _QWORD v180[2]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v181[8]; // [rsp+570h] [rbp+470h] BYREF
  __int64 v182; // [rsp+578h] [rbp+478h] BYREF
  _BYTE v183[8]; // [rsp+580h] [rbp+480h] BYREF
  __int64 v184; // [rsp+588h] [rbp+488h] BYREF
  _BYTE v185[8]; // [rsp+590h] [rbp+490h] BYREF
  _QWORD v186[9]; // [rsp+598h] [rbp+498h] BYREF
  unsigned int v187; // [rsp+608h] [rbp+508h] BYREF

  v186[1] = -2;
  TargetFromContext = Debugger::DataModel::Libraries::KernelTargetDetails::GetTargetFromContext(a3, a2);
  if ( (*(unsigned int (__fastcall **)(struct TargetInfo *))(*(_QWORD *)TargetFromContext + 184LL))(TargetFromContext) )
  {
    v5 = (char *)TargetFromContext + 800;
    v181[0] = 0;
    v182 = 0;
    Debugger::DataModel::ClientEx::Object::Create<>(&v14, v181);
    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v182);
    v183[0] = 0;
    v184 = 0;
    Debugger::DataModel::ClientEx::Object::Create<>(&v15, v183);
    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v184);
    v185[0] = 0;
    v186[0] = 0;
    Debugger::DataModel::ClientEx::Object::Create<>(&v16, v185);
    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(v186);
    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v19, (unsigned __int64 *)v5);
    v6 = v16;
    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v16 + 192LL))(
             v16,
             L"Flink",
             v19,
             0);
    if ( (v187 & 0x80000000) == 0 )
    {
      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v19);
      Debugger::DataModel::ClientEx::Object::Object(
        (Debugger::DataModel::ClientEx::Object *)&v20,
        (unsigned __int64 *)v5 + 1);
      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v6 + 192LL))(
               v6,
               L"Blink",
               v20,
               0);
      if ( (v187 & 0x80000000) == 0 )
      {
        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v20);
        v9 = v15;
        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v15 + 192LL))(
                 v15,
                 L"List",
                 v6,
                 0);
        if ( (v187 & 0x80000000) == 0 )
        {
          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v16);
          Debugger::DataModel::ClientEx::Object::Object(
            (Debugger::DataModel::ClientEx::Object *)&v21,
            (unsigned int *)v5 + 4);
          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v9 + 192LL))(
                   v9,
                   L"OwnerTag",
                   v21,
                   0);
          if ( (v187 & 0x80000000) == 0 )
          {
            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v21);
            v10 = v5 + 20;
            Debugger::DataModel::ClientEx::Object::Object(
              (Debugger::DataModel::ClientEx::Object *)&v22,
              (unsigned int *)v5 + 5);
            v187 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)v9 + 192LL))(
                     v9,
                     L"Size",
                     v22,
                     0);
            if ( (v187 & 0x80000000) == 0 )
            {
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v22);
              v11 = v14;
              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v14 + 192LL))(
                       v14,
                       L"Header",
                       v9,
                       0);
              if ( (v187 & 0x80000000) != 0 )
              {
                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                goto LABEL_351;
              }
              Debugger::DataModel::ClientEx::Object::Object(
                (Debugger::DataModel::ClientEx::Object *)&v23,
                (unsigned __int64 *)v5 + 3);
              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                       v11,
                       L"KernBase",
                       v23,
                       0);
              if ( (v187 & 0x80000000) == 0 )
              {
                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v23);
                Debugger::DataModel::ClientEx::Object::Object(
                  (Debugger::DataModel::ClientEx::Object *)&v24,
                  (unsigned __int64 *)v5 + 4);
                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                         v11,
                         L"BreakpointWithStatus",
                         v24,
                         0);
                if ( (v187 & 0x80000000) == 0 )
                {
                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v24);
                  Debugger::DataModel::ClientEx::Object::Object(
                    (Debugger::DataModel::ClientEx::Object *)&v25,
                    (unsigned __int64 *)v5 + 5);
                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                           v11,
                           L"SavedContext",
                           v25,
                           0);
                  if ( (v187 & 0x80000000) == 0 )
                  {
                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v25);
                    Debugger::DataModel::ClientEx::Object::Object(
                      (Debugger::DataModel::ClientEx::Object *)&v26,
                      (unsigned __int16 *)v5 + 24);
                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                             v11,
                             L"ThCallbackStack",
                             v26,
                             0);
                    if ( (v187 & 0x80000000) == 0 )
                    {
                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v26);
                      Debugger::DataModel::ClientEx::Object::Object(
                        (Debugger::DataModel::ClientEx::Object *)&v27,
                        (unsigned __int16 *)v5 + 25);
                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11
                                                                                                  + 192LL))(
                               v11,
                               L"NextCallback",
                               v27,
                               0);
                      if ( (v187 & 0x80000000) == 0 )
                      {
                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v27);
                        Debugger::DataModel::ClientEx::Object::Object(
                          (Debugger::DataModel::ClientEx::Object *)&v28,
                          (unsigned __int16 *)v5 + 26);
                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                 v11,
                                 L"FramePointer",
                                 v28,
                                 0);
                        if ( (v187 & 0x80000000) == 0 )
                        {
                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v28);
                          LOWORD(v187) = *((_WORD *)v5 + 27) & 1;
                          v17 = 0;
                          Debugger::DataModel::ClientEx::Details::BoxObjectIntrinsic<unsigned short>::Box(&v29, &v187);
                          v12 = v29;
                          v29 = 0;
                          Microsoft::WRL::ComPtr<Debugger::DataModel::Host::ConstructedBasicHostTypeSymbol>::Attach(
                            &v17,
                            v12);
                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v29);
                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                   v11,
                                   L"PaeEnabled",
                                   v17,
                                   0);
                          if ( (v187 & 0x80000000) == 0 )
                          {
                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v17);
                            Debugger::DataModel::ClientEx::Object::Object(
                              (Debugger::DataModel::ClientEx::Object *)&v30,
                              (unsigned __int64 *)v5 + 7);
                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                     v11,
                                     L"KiCallUserMode",
                                     v30,
                                     0);
                            if ( (v187 & 0x80000000) == 0 )
                            {
                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v30);
                              Debugger::DataModel::ClientEx::Object::Object(
                                (Debugger::DataModel::ClientEx::Object *)&v31,
                                (unsigned __int64 *)v5 + 8);
                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                       v11,
                                       L"KeUserCallbackDispatcher",
                                       v31,
                                       0);
                              if ( (v187 & 0x80000000) == 0 )
                              {
                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v31);
                                Debugger::DataModel::ClientEx::Object::Object(
                                  (Debugger::DataModel::ClientEx::Object *)&v32,
                                  (unsigned __int64 *)v5 + 9);
                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                         v11,
                                         L"PsLoadedModuleList",
                                         v32,
                                         0);
                                if ( (v187 & 0x80000000) == 0 )
                                {
                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v32);
                                  Debugger::DataModel::ClientEx::Object::Object(
                                    (Debugger::DataModel::ClientEx::Object *)&v33,
                                    (unsigned __int64 *)v5 + 10);
                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                           v11,
                                           L"PsActiveProcessHead",
                                           v33,
                                           0);
                                  if ( (v187 & 0x80000000) == 0 )
                                  {
                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v33);
                                    Debugger::DataModel::ClientEx::Object::Object(
                                      (Debugger::DataModel::ClientEx::Object *)&v34,
                                      (unsigned __int64 *)v5 + 11);
                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                             v11,
                                             L"PspCidTable",
                                             v34,
                                             0);
                                    if ( (v187 & 0x80000000) == 0 )
                                    {
                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v34);
                                      Debugger::DataModel::ClientEx::Object::Object(
                                        (Debugger::DataModel::ClientEx::Object *)&v18,
                                        (unsigned __int64 *)v5 + 12);
                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                               v11,
                                               L"ExpSystemResourcesList",
                                               v18,
                                               0);
                                      if ( (v187 & 0x80000000) == 0 )
                                      {
                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v18);
                                        Debugger::DataModel::ClientEx::Object::Object(
                                          (Debugger::DataModel::ClientEx::Object *)&v36,
                                          (unsigned __int64 *)v5 + 13);
                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                 v11,
                                                 L"ExpPagedPoolDescriptor",
                                                 v36,
                                                 0);
                                        if ( (v187 & 0x80000000) == 0 )
                                        {
                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v36);
                                          Debugger::DataModel::ClientEx::Object::Object(
                                            (Debugger::DataModel::ClientEx::Object *)&v37,
                                            (unsigned __int64 *)v5 + 14);
                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                   v11,
                                                   L"ExpNumberOfPagedPools",
                                                   v37,
                                                   0);
                                          if ( (v187 & 0x80000000) == 0 )
                                          {
                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v37);
                                            Debugger::DataModel::ClientEx::Object::Object(
                                              (Debugger::DataModel::ClientEx::Object *)&v38,
                                              (unsigned __int64 *)v5 + 15);
                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                     v11,
                                                     L"KeTimeIncrement",
                                                     v38,
                                                     0);
                                            if ( (v187 & 0x80000000) == 0 )
                                            {
                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v38);
                                              Debugger::DataModel::ClientEx::Object::Object(
                                                (Debugger::DataModel::ClientEx::Object *)&v39,
                                                (unsigned __int64 *)v5 + 16);
                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                       v11,
                                                       L"KeBugCheckCallbackListHead",
                                                       v39,
                                                       0);
                                              if ( (v187 & 0x80000000) == 0 )
                                              {
                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v39);
                                                Debugger::DataModel::ClientEx::Object::Object(
                                                  (Debugger::DataModel::ClientEx::Object *)&v40,
                                                  (unsigned __int64 *)v5 + 17);
                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                         v11,
                                                         L"KiBugcheckData",
                                                         v40,
                                                         0);
                                                if ( (v187 & 0x80000000) == 0 )
                                                {
                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v40);
                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                    (Debugger::DataModel::ClientEx::Object *)&v41,
                                                    (unsigned __int64 *)v5 + 18);
                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                           v11,
                                                           L"IopErrorLogListHead",
                                                           v41,
                                                           0);
                                                  if ( (v187 & 0x80000000) == 0 )
                                                  {
                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v41);
                                                    Debugger::DataModel::ClientEx::Object::Object(
                                                      (Debugger::DataModel::ClientEx::Object *)&v42,
                                                      (unsigned __int64 *)v5 + 19);
                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                             v11,
                                                             L"ObpRootDirectoryObject",
                                                             v42,
                                                             0);
                                                    if ( (v187 & 0x80000000) == 0 )
                                                    {
                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v42);
                                                      Debugger::DataModel::ClientEx::Object::Object(
                                                        (Debugger::DataModel::ClientEx::Object *)&v43,
                                                        (unsigned __int64 *)v5 + 20);
                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                               v11,
                                                               L"ObpTypeObjectType",
                                                               v43,
                                                               0);
                                                      if ( (v187 & 0x80000000) == 0 )
                                                      {
                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v43);
                                                        Debugger::DataModel::ClientEx::Object::Object(
                                                          (Debugger::DataModel::ClientEx::Object *)&v44,
                                                          (unsigned __int64 *)v5 + 21);
                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                 v11,
                                                                 L"MmSystemCacheStart",
                                                                 v44,
                                                                 0);
                                                        if ( (v187 & 0x80000000) == 0 )
                                                        {
                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v44);
                                                          Debugger::DataModel::ClientEx::Object::Object(
                                                            (Debugger::DataModel::ClientEx::Object *)&v45,
                                                            (unsigned __int64 *)v5 + 22);
                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                   v11,
                                                                   L"MmSystemCacheEnd",
                                                                   v45,
                                                                   0);
                                                          if ( (v187 & 0x80000000) == 0 )
                                                          {
                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v45);
                                                            Debugger::DataModel::ClientEx::Object::Object(
                                                              (Debugger::DataModel::ClientEx::Object *)&v46,
                                                              (unsigned __int64 *)v5 + 23);
                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                     v11,
                                                                     L"MmSystemCacheWs",
                                                                     v46,
                                                                     0);
                                                            if ( (v187 & 0x80000000) == 0 )
                                                            {
                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v46);
                                                              Debugger::DataModel::ClientEx::Object::Object(
                                                                (Debugger::DataModel::ClientEx::Object *)&v47,
                                                                (unsigned __int64 *)v5 + 24);
                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                       v11,
                                                                       L"MmPfnDatabase",
                                                                       v47,
                                                                       0);
                                                              if ( (v187 & 0x80000000) == 0 )
                                                              {
                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v47);
                                                                Debugger::DataModel::ClientEx::Object::Object(
                                                                  (Debugger::DataModel::ClientEx::Object *)&v48,
                                                                  (unsigned __int64 *)v5 + 25);
                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                         v11,
                                                                         L"MmSystemPtesStart",
                                                                         v48,
                                                                         0);
                                                                if ( (v187 & 0x80000000) == 0 )
                                                                {
                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v48);
                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                    (Debugger::DataModel::ClientEx::Object *)&v49,
                                                                    (unsigned __int64 *)v5 + 26);
                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                           v11,
                                                                           L"MmSystemPtesEnd",
                                                                           v49,
                                                                           0);
                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                  {
                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v49);
                                                                    Debugger::DataModel::ClientEx::Object::Object(
                                                                      (Debugger::DataModel::ClientEx::Object *)&v50,
                                                                      (unsigned __int64 *)v5 + 27);
                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                             v11,
                                                                             L"MmSubsectionBase",
                                                                             v50,
                                                                             0);
                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                    {
                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v50);
                                                                      Debugger::DataModel::ClientEx::Object::Object(
                                                                        (Debugger::DataModel::ClientEx::Object *)&v51,
                                                                        (unsigned __int64 *)v5 + 28);
                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                               v11,
                                                                               L"MmNumberOfPagingFiles",
                                                                               v51,
                                                                               0);
                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                      {
                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v51);
                                                                        Debugger::DataModel::ClientEx::Object::Object(
                                                                          (Debugger::DataModel::ClientEx::Object *)&v52,
                                                                          (unsigned __int64 *)v5 + 29);
                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                 v11,
                                                                                 L"MmLowestPhysicalPage",
                                                                                 v52,
                                                                                 0);
                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                        {
                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v52);
                                                                          Debugger::DataModel::ClientEx::Object::Object(
                                                                            (Debugger::DataModel::ClientEx::Object *)&v53,
                                                                            (unsigned __int64 *)v5 + 30);
                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                   v11,
                                                                                   L"MmHighestPhysicalPage",
                                                                                   v53,
                                                                                   0);
                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                          {
                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v53);
                                                                            Debugger::DataModel::ClientEx::Object::Object(
                                                                              (Debugger::DataModel::ClientEx::Object *)&v54,
                                                                              (unsigned __int64 *)v5 + 31);
                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                     v11,
                                                                                     L"MmNumberOfPhysicalPages",
                                                                                     v54,
                                                                                     0);
                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                            {
                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v54);
                                                                              Debugger::DataModel::ClientEx::Object::Object(
                                                                                (Debugger::DataModel::ClientEx::Object *)&v55,
                                                                                (unsigned __int64 *)v5 + 32);
                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                       v11,
                                                                                       L"MmMaximumNonPagedPoolInBytes",
                                                                                       v55,
                                                                                       0);
                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                              {
                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v55);
                                                                                Debugger::DataModel::ClientEx::Object::Object(
                                                                                  (Debugger::DataModel::ClientEx::Object *)&v35,
                                                                                  (unsigned __int64 *)v5 + 33);
                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                         v11,
                                                                                         L"MmNonPagedSystemStart",
                                                                                         v35,
                                                                                         0);
                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                {
                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v35);
                                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                                    (Debugger::DataModel::ClientEx::Object *)&v57,
                                                                                    (unsigned __int64 *)v5 + 34);
                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                           v11,
                                                                                           L"MmNonPagedPoolStart",
                                                                                           v57,
                                                                                           0);
                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                  {
                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v57);
                                                                                    Debugger::DataModel::ClientEx::Object::Object(
                                                                                      (Debugger::DataModel::ClientEx::Object *)&v58,
                                                                                      (unsigned __int64 *)v5 + 35);
                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                             v11,
                                                                                             L"MmNonPagedPoolEnd",
                                                                                             v58,
                                                                                             0);
                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                    {
                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v58);
                                                                                      Debugger::DataModel::ClientEx::Object::Object(
                                                                                        (Debugger::DataModel::ClientEx::Object *)&v59,
                                                                                        (unsigned __int64 *)v5 + 36);
                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                               v11,
                                                                                               L"MmPagedPoolStart",
                                                                                               v59,
                                                                                               0);
                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                      {
                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v59);
                                                                                        Debugger::DataModel::ClientEx::Object::Object(
                                                                                          (Debugger::DataModel::ClientEx::Object *)&v60,
                                                                                          (unsigned __int64 *)v5 + 37);
                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                                 v11,
                                                                                                 L"MmPagedPoolEnd",
                                                                                                 v60,
                                                                                                 0);
                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                        {
                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v60);
                                                                                          Debugger::DataModel::ClientEx::Object::Object(
                                                                                            (Debugger::DataModel::ClientEx::Object *)&v61,
                                                                                            (unsigned __int64 *)v5 + 38);
                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                                   v11,
                                                                                                   L"MmPagedPoolInformation",
                                                                                                   v61,
                                                                                                   0);
                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                          {
                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v61);
                                                                                            Debugger::DataModel::ClientEx::Object::Object(
                                                                                              (Debugger::DataModel::ClientEx::Object *)&v62,
                                                                                              (unsigned __int64 *)v5
                                                                                            + 39);
                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(
                                                                                                     v11,
                                                                                                     L"MmPageSize",
                                                                                                     v62,
                                                                                                     0);
                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                            {
                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v62);
                                                                                              Debugger::DataModel::ClientEx::Object::Object(
                                                                                                (Debugger::DataModel::ClientEx::Object *)&v63,
                                                                                                (unsigned __int64 *)v5
                                                                                              + 40);
                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSizeOfPagedPoolInBytes", v63, 0);
                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                              {
                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v63);
                                                                                                Debugger::DataModel::ClientEx::Object::Object(
                                                                                                  (Debugger::DataModel::ClientEx::Object *)&v64,
                                                                                                  (unsigned __int64 *)v5
                                                                                                + 41);
                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmTotalCommitLimit", v64, 0);
                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                {
                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v64);
                                                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                                                    (Debugger::DataModel::ClientEx::Object *)&v65,
                                                                                                    (unsigned __int64 *)v5 + 42);
                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmTotalCommittedPages", v65, 0);
                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                  {
                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v65);
                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v66, (unsigned __int64 *)v5 + 43);
                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSharedCommit", v66, 0);
                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                    {
                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v66);
                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v67, (unsigned __int64 *)v5 + 44);
                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmDriverCommit", v67, 0);
                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                      {
                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v67);
                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v68, (unsigned __int64 *)v5 + 45);
                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmProcessCommit", v68, 0);
                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                        {
                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v68);
                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v69, (unsigned __int64 *)v5 + 46);
                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmPagedPoolCommit", v69, 0);
                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                          {
                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v69);
                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v70, (unsigned __int64 *)v5 + 47);
                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmExtendedCommit", v70, 0);
                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                            {
                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v70);
                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v71, (unsigned __int64 *)v5 + 48);
                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmZeroedPageListHead", v71, 0);
                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                              {
                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v71);
                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v72, (unsigned __int64 *)v5 + 49);
                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmFreePageListHead", v72, 0);
                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                {
                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v72);
                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v73, (unsigned __int64 *)v5 + 50);
                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmStandbyPageListHead", v73, 0);
                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                  {
                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v73);
                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v74, (unsigned __int64 *)v5 + 51);
                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmModifiedPageListHead", v74, 0);
                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                    {
                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v74);
                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v75, (unsigned __int64 *)v5 + 52);
                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmModifiedNoWritePageListHead", v75, 0);
                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                      {
                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v75);
                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v76, (unsigned __int64 *)v5 + 53);
                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmAvailablePages", v76, 0);
                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                        {
                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v76);
                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v77, (unsigned __int64 *)v5 + 54);
                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmResidentAvailablePages", v77, 0);
                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                          {
                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v77);
                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v78, (unsigned __int64 *)v5 + 55);
                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"PoolTrackTable", v78, 0);
                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                            {
                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v78);
                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v79, (unsigned __int64 *)v5 + 56);
                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"NonPagedPoolDescriptor", v79, 0);
                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                              {
                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v79);
                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v80, (unsigned __int64 *)v5 + 57);
                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmHighestUserAddress", v80, 0);
                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                {
                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v80);
                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v81, (unsigned __int64 *)v5 + 58);
                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSystemRangeStart", v81, 0);
                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                  {
                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v81);
                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v82, (unsigned __int64 *)v5 + 59);
                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmUserProbeAddress", v82, 0);
                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                    {
                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v82);
                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v83, (unsigned __int64 *)v5 + 60);
                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintCircularBuffer", v83, 0);
                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                      {
                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v83);
                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v84, (unsigned __int64 *)v5 + 61);
                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintCircularBufferEnd", v84, 0);
                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                        {
                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v84);
                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v85, (unsigned __int64 *)v5 + 62);
                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintWritePointer", v85, 0);
                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                          {
                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v85);
                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v86, (unsigned __int64 *)v5 + 63);
                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintRolloverCount", v86, 0);
                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                            {
                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v86);
                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v87, (unsigned __int64 *)v5 + 64);
                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmLoadedUserImageList", v87, 0);
                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                              {
                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v87);
                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v88, (unsigned __int64 *)v5 + 65);
                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"NtBuildLab", v88, 0);
                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                {
                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v88);
                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v89, (unsigned __int64 *)v5 + 66);
                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KiNormalSystemCall", v89, 0);
                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                  {
                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v89);
                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v90, (unsigned __int64 *)v5 + 67);
                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KiProcessorBlock", v90, 0);
                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                    {
                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v90);
                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v91, (unsigned __int64 *)v5 + 68);
                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmUnloadedDrivers", v91, 0);
                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                      {
                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v91);
                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v92, (unsigned __int64 *)v5 + 69);
                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmLastUnloadedDriver", v92, 0);
                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                        {
                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v92);
                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v93, (unsigned __int64 *)v5 + 70);
                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmTriageActionTaken", v93, 0);
                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                          {
                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v93);
                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v94, (unsigned __int64 *)v5 + 71);
                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSpecialPoolTag", v94, 0);
                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                            {
                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v94);
                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v95, (unsigned __int64 *)v5 + 72);
                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KernelVerifier", v95, 0);
                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                              {
                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v95);
                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v96, (unsigned __int64 *)v5 + 73);
                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmVerifierData", v96, 0);
                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                {
                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v96);
                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v97, (unsigned __int64 *)v5 + 74);
                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmAllocatedNonPagedPool", v97, 0);
                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                  {
                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v97);
                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v98, (unsigned __int64 *)v5 + 75);
                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmPeakCommitment", v98, 0);
                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                    {
                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v98);
                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v99, (unsigned __int64 *)v5 + 76);
                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmTotalCommitLimitMaximum", v99, 0);
                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                      {
                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v99);
                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v100, (unsigned __int64 *)v5 + 77);
                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"CmNtCSDVersion", v100, 0);
                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                        {
                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v100);
                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v101, (unsigned __int64 *)v5 + 78);
                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmPhysicalMemoryBlock", v101, 0);
                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                          {
                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v101);
                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v102, (unsigned __int64 *)v5 + 79);
                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSessionBase", v102, 0);
                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                            {
                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v102);
                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v103, (unsigned __int64 *)v5 + 80);
                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSessionSize", v103, 0);
                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                              {
                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v103);
                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v104, (unsigned __int64 *)v5 + 81);
                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmSystemParentTablePage", v104, 0);
                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                {
                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v104);
                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v105, (unsigned __int64 *)v5 + 82);
                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmVirtualTranslationBase", v105, 0);
                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                  {
                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v105);
                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v106, (unsigned __int16 *)v5 + 332);
                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadNextProcessor", v106, 0);
                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                    {
                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v106);
                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v107, (unsigned __int16 *)v5 + 333);
                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadTeb", v107, 0);
                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                      {
                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v107);
                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v108, (unsigned __int16 *)v5 + 334);
                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadKernelStack", v108, 0);
                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                        {
                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v108);
                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v109, (unsigned __int16 *)v5 + 335);
                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadInitialStack", v109, 0);
                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                          {
                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v109);
                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v110, (unsigned __int16 *)v5 + 336);
                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadApcProcess", v110, 0);
                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                            {
                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v110);
                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v111, (unsigned __int16 *)v5 + 337);
                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadState", v111, 0);
                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                              {
                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v111);
                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v112, (unsigned __int16 *)v5 + 338);
                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadBStore", v112, 0);
                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                {
                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v112);
                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v113, (unsigned __int16 *)v5 + 339);
                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadBStoreLimit", v113, 0);
                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                  {
                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v113);
                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v114, (unsigned __int16 *)v5 + 340);
                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"SizeEProcess", v114, 0);
                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                    {
                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v114);
                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v115, (unsigned __int16 *)v5 + 341);
                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetEprocessPeb", v115, 0);
                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                      {
                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v115);
                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v116, (unsigned __int16 *)v5 + 342);
                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetEprocessParentCID", v116, 0);
                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                        {
                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v116);
                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v117, (unsigned __int16 *)v5 + 343);
                                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetEprocessDirectoryTableBase", v117, 0);
                                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                          {
                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v117);
                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v118, (unsigned __int16 *)v5 + 344);
                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"SizePrcb", v118, 0);
                                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                            {
                                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v118);
                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v119, (unsigned __int16 *)v5 + 345);
                                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbDpcRoutine", v119, 0);
                                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                              {
                                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v119);
                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v120, (unsigned __int16 *)v5 + 346);
                                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbCurrentThread", v120, 0);
                                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                {
                                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v120);
                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v121, (unsigned __int16 *)v5 + 347);
                                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbMhz", v121, 0);
                                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                  {
                                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v121);
                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v122, (unsigned __int16 *)v5 + 348);
                                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbCpuType", v122, 0);
                                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                    {
                                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v122);
                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v123, (unsigned __int16 *)v5 + 349);
                                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbVendorString", v123, 0);
                                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                      {
                                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v123);
                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v124, (unsigned __int16 *)v5 + 350);
                                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbProcStateContext", v124, 0);
                                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                        {
                                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v124);
                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v125, (unsigned __int16 *)v5 + 351);
                                                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbNumber", v125, 0);
                                                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                          {
                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v125);
                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v126, (unsigned __int16 *)v5 + 352);
                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"SizeEThread", v126, 0);
                                                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                            {
                                                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v126);
                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v127, (unsigned __int64 *)v5 + 89);
                                                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintCircularBufferPtr", v127, 0);
                                                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v127);
                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v128, (unsigned __int64 *)v5 + 90);
                                                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KdPrintBufferSize", v128, 0);
                                                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v128);
                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v129, (unsigned __int64 *)v5 + 91);
                                                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"KeLoaderBlock", v129, 0);
                                                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v129);
                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v130, (unsigned __int16 *)v5 + 368);
                                                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"SizePcr", v130, 0);
                                                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v130);
                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v131, (unsigned __int16 *)v5 + 369);
                                                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrSelfPcr", v131, 0);
                                                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v131);
                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v132, (unsigned __int16 *)v5 + 370);
                                                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrCurrentPrcb", v132, 0);
                                                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v132);
                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v133, (unsigned __int16 *)v5 + 371);
                                                                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrContainedPrcb", v133, 0);
                                                                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v133);
                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v134, (unsigned __int16 *)v5 + 372);
                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrInitialBStore", v134, 0);
                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v134);
                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v135, (unsigned __int16 *)v5 + 373);
                                                                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrBStoreLimit", v135, 0);
                                                                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v135);
                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v136, (unsigned __int16 *)v5 + 374);
                                                                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrInitialStack", v136, 0);
                                                                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v136);
                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v137, (unsigned __int16 *)v5 + 375);
                                                                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPcrStackLimit", v137, 0);
                                                                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v137);
                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v138, (unsigned __int16 *)v5 + 376);
                                                                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbPcrPage", v138, 0);
                                                                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v138);
                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v139, (unsigned __int16 *)v5 + 377);
                                                                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbProcStateSpecialReg", v139, 0);
                                                                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v139);
                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v140, (unsigned __int16 *)v5 + 378);
                                                                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR0Code", v140, 0);
                                                                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v140);
                                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v141, (unsigned __int16 *)v5 + 379);
                                                                                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR0Data", v141, 0);
                                                                                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v141);
                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v142, (unsigned __int16 *)v5 + 380);
                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR0Pcr", v142, 0);
                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v142);
                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v143, (unsigned __int16 *)v5 + 381);
                                                                                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR3Code", v143, 0);
                                                                                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v143);
                                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v144, (unsigned __int16 *)v5 + 382);
                                                                                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR3Data", v144, 0);
                                                                                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v144);
                                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v145, (unsigned __int16 *)v5 + 383);
                                                                                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtR3Teb", v145, 0);
                                                                                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v145);
                                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v146, (unsigned __int16 *)v5 + 384);
                                                                                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtLdt", v146, 0);
                                                                                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v146);
                                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v147, (unsigned __int16 *)v5 + 385);
                                                                                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"GdtTss", v147, 0);
                                                                                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v147);
                                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v148, (unsigned __int16 *)v5 + 386);
                                                                                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"Gdt64R3CmCode", v148, 0);
                                                                                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v148);
                                                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v149, (unsigned __int16 *)v5 + 387);
                                                                                                                                                                                                                                                                          v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"Gdt64R3CmTeb", v149, 0);
                                                                                                                                                                                                                                                                          if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v149);
                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v150, (unsigned __int64 *)v5 + 97);
                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"IopNumTriageDumpDataBlocks", v150, 0);
                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v150);
                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v151, (unsigned __int64 *)v5 + 98);
                                                                                                                                                                                                                                                                              v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"IopTriageDumpDataBlocks", v151, 0);
                                                                                                                                                                                                                                                                              if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                                                Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v151);
                                                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v152, (unsigned __int64 *)v5 + 99);
                                                                                                                                                                                                                                                                                v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"VfCrashDataBlock", v152, 0);
                                                                                                                                                                                                                                                                                if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                                                  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v152);
                                                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v153, (unsigned __int64 *)v5 + 100);
                                                                                                                                                                                                                                                                                  v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmBadPagesDetected", v153, 0);
                                                                                                                                                                                                                                                                                  if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                                                    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v153);
                                                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v154, (unsigned __int64 *)v5 + 101);
                                                                                                                                                                                                                                                                                    v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"MmZeroedPageSingleBitErrorsDetected", v154, 0);
                                                                                                                                                                                                                                                                                    if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                                                      Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v154);
                                                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v155, (unsigned __int64 *)v5 + 102);
                                                                                                                                                                                                                                                                                      v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"EtwpDebuggerData", v155, 0);
                                                                                                                                                                                                                                                                                      if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                                                        Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v155);
                                                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v156, (unsigned __int16 *)v5 + 412);
                                                                                                                                                                                                                                                                                        v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbContext", v156, 0);
                                                                                                                                                                                                                                                                                        if ( (v187 & 0x80000000) == 0 )
                                                                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                                                                          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v156);
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x35Au )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v157, (unsigned __int16 *)v5 + 413);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbMaxBreakpoints", v157, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v157;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v157);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v158, (unsigned __int16 *)v5 + 414);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbMaxWatchpoints", v158, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v158;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v158);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v159, (unsigned int *)v5 + 208);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadStackLimit", v159, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v159;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v159);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v160, (unsigned int *)v5 + 209);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadStackBase", v160, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v160;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v160);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v161, (unsigned int *)v5 + 210);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadQueueListEntry", v161, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v161;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v161);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v162, (unsigned int *)v5 + 211);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetEThreadIrpList", v162, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v162;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v162);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v163, (unsigned __int16 *)v5 + 424);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbIdleThread", v163, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v163;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v163);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v164, (unsigned __int16 *)v5 + 425);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbNormalDpcState", v164, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v164;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v164);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v165, (unsigned __int16 *)v5 + 426);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbDpcStack", v165, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v165;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v165);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v166, (unsigned __int16 *)v5 + 427);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbIsrStack", v166, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v166;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v166);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v167, (unsigned __int16 *)v5 + 428);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"SizeKDPC_STACK_FRAME", v167, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v167;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v167);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x35Eu )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v168, (unsigned __int16 *)v5 + 429);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKPriQueueThreadListHead", v168, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v168;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v168);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v169, (unsigned __int16 *)v5 + 430);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadWaitReason", v169, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v169;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v169);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x368u )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v170, (unsigned __int16 *)v5 + 431);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"Padding1", v170, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v170;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v170);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v171, (unsigned __int64 *)v5 + 108);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"PteBase", v171, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v171;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v171);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x37Cu )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v172, (unsigned __int64 *)v5 + 109);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"RetpolineStubFunctionTable", v172, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v172;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v172);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v173, (unsigned int *)v5 + 220);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"RetpolineStubFunctionTableSize", v173, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v173;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v173);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v174, (unsigned int *)v5 + 221);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"RetpolineStubOffset", v174, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v174;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v174);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v175, (unsigned int *)v5 + 222);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"RetpolineStubSize", v175, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v175;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v175);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x380u )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v176, (unsigned __int16 *)v5 + 446);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetEProcessMmHotPatchContext", v176, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v176;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v176);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x390u )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v177, (unsigned int *)v5 + 224);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadShadowStackLimit", v177, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v177;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v177);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v178, (unsigned int *)v5 + 225);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetKThreadShadowStackBase", v178, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v178;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v178);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v179, (unsigned __int64 *)v5 + 113);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"ShadowStackEnabled", v179, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v179;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v179);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          if ( *v10 >= 0x3A0u )
                                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)v180, (unsigned __int64 *)v5 + 114);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"PointerAuthMask", v180[0], 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = v180;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(v180);
                                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object((Debugger::DataModel::ClientEx::Object *)&v56, (unsigned __int16 *)v5 + 460);
                                                                                                                                                                                                                                                                                            v187 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD))(*(_QWORD *)v11 + 192LL))(v11, L"OffsetPrcbExceptionStack", v56, 0);
                                                                                                                                                                                                                                                                                            if ( (v187 & 0x80000000) != 0 )
                                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                              v8 = &v56;
                                                                                                                                                                                                                                                                                              goto LABEL_7;
                                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                                            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v56);
                                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v14);
                                                                                                                                                                                                                                                                                          goto LABEL_351;
                                                                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                        v8 = &v156;
                                                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                                                      else
                                                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                        v8 = &v155;
                                                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                                                    else
                                                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                      v8 = &v154;
                                                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                                                  else
                                                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                    v8 = &v153;
                                                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                                                                else
                                                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                  v8 = &v152;
                                                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                                                              else
                                                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                                v8 = &v151;
                                                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                            else
                                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                              v8 = &v150;
                                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                          else
                                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                            v8 = &v149;
                                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                                        else
                                                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                          v8 = &v148;
                                                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                                      else
                                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                        v8 = &v147;
                                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                                    else
                                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                      v8 = &v146;
                                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                                  else
                                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                    v8 = &v145;
                                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                                                else
                                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                  v8 = &v144;
                                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                                              else
                                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                                v8 = &v143;
                                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                            else
                                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                              v8 = &v142;
                                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                          else
                                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                            v8 = &v141;
                                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                        else
                                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                          v8 = &v140;
                                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                      else
                                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                        v8 = &v139;
                                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                    else
                                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                      v8 = &v138;
                                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                  else
                                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                    v8 = &v137;
                                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                                else
                                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                  v8 = &v136;
                                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                              else
                                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                                v8 = &v135;
                                                                                                                                                                                                                                              }
                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                            else
                                                                                                                                                                                                                                            {
                                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                              v8 = &v134;
                                                                                                                                                                                                                                            }
                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                          else
                                                                                                                                                                                                                                          {
                                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                            v8 = &v133;
                                                                                                                                                                                                                                          }
                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                        else
                                                                                                                                                                                                                                        {
                                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                          v8 = &v132;
                                                                                                                                                                                                                                        }
                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                      else
                                                                                                                                                                                                                                      {
                                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                        v8 = &v131;
                                                                                                                                                                                                                                      }
                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                    else
                                                                                                                                                                                                                                    {
                                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                      v8 = &v130;
                                                                                                                                                                                                                                    }
                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                  else
                                                                                                                                                                                                                                  {
                                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                    v8 = &v129;
                                                                                                                                                                                                                                  }
                                                                                                                                                                                                                                }
                                                                                                                                                                                                                                else
                                                                                                                                                                                                                                {
                                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                  v8 = &v128;
                                                                                                                                                                                                                                }
                                                                                                                                                                                                                              }
                                                                                                                                                                                                                              else
                                                                                                                                                                                                                              {
                                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                                v8 = &v127;
                                                                                                                                                                                                                              }
                                                                                                                                                                                                                            }
                                                                                                                                                                                                                            else
                                                                                                                                                                                                                            {
                                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                              v8 = &v126;
                                                                                                                                                                                                                            }
                                                                                                                                                                                                                          }
                                                                                                                                                                                                                          else
                                                                                                                                                                                                                          {
                                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                            v8 = &v125;
                                                                                                                                                                                                                          }
                                                                                                                                                                                                                        }
                                                                                                                                                                                                                        else
                                                                                                                                                                                                                        {
                                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                          v8 = &v124;
                                                                                                                                                                                                                        }
                                                                                                                                                                                                                      }
                                                                                                                                                                                                                      else
                                                                                                                                                                                                                      {
                                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                        v8 = &v123;
                                                                                                                                                                                                                      }
                                                                                                                                                                                                                    }
                                                                                                                                                                                                                    else
                                                                                                                                                                                                                    {
                                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                      v8 = &v122;
                                                                                                                                                                                                                    }
                                                                                                                                                                                                                  }
                                                                                                                                                                                                                  else
                                                                                                                                                                                                                  {
                                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                    v8 = &v121;
                                                                                                                                                                                                                  }
                                                                                                                                                                                                                }
                                                                                                                                                                                                                else
                                                                                                                                                                                                                {
                                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                  v8 = &v120;
                                                                                                                                                                                                                }
                                                                                                                                                                                                              }
                                                                                                                                                                                                              else
                                                                                                                                                                                                              {
                                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                                v8 = &v119;
                                                                                                                                                                                                              }
                                                                                                                                                                                                            }
                                                                                                                                                                                                            else
                                                                                                                                                                                                            {
                                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                              v8 = &v118;
                                                                                                                                                                                                            }
                                                                                                                                                                                                          }
                                                                                                                                                                                                          else
                                                                                                                                                                                                          {
                                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                            v8 = &v117;
                                                                                                                                                                                                          }
                                                                                                                                                                                                        }
                                                                                                                                                                                                        else
                                                                                                                                                                                                        {
                                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                          v8 = &v116;
                                                                                                                                                                                                        }
                                                                                                                                                                                                      }
                                                                                                                                                                                                      else
                                                                                                                                                                                                      {
                                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                        v8 = &v115;
                                                                                                                                                                                                      }
                                                                                                                                                                                                    }
                                                                                                                                                                                                    else
                                                                                                                                                                                                    {
                                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                      v8 = &v114;
                                                                                                                                                                                                    }
                                                                                                                                                                                                  }
                                                                                                                                                                                                  else
                                                                                                                                                                                                  {
                                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                    v8 = &v113;
                                                                                                                                                                                                  }
                                                                                                                                                                                                }
                                                                                                                                                                                                else
                                                                                                                                                                                                {
                                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                  v8 = &v112;
                                                                                                                                                                                                }
                                                                                                                                                                                              }
                                                                                                                                                                                              else
                                                                                                                                                                                              {
                                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                                v8 = &v111;
                                                                                                                                                                                              }
                                                                                                                                                                                            }
                                                                                                                                                                                            else
                                                                                                                                                                                            {
                                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                              v8 = &v110;
                                                                                                                                                                                            }
                                                                                                                                                                                          }
                                                                                                                                                                                          else
                                                                                                                                                                                          {
                                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                            v8 = &v109;
                                                                                                                                                                                          }
                                                                                                                                                                                        }
                                                                                                                                                                                        else
                                                                                                                                                                                        {
                                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                          v8 = &v108;
                                                                                                                                                                                        }
                                                                                                                                                                                      }
                                                                                                                                                                                      else
                                                                                                                                                                                      {
                                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                        v8 = &v107;
                                                                                                                                                                                      }
                                                                                                                                                                                    }
                                                                                                                                                                                    else
                                                                                                                                                                                    {
                                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                      v8 = &v106;
                                                                                                                                                                                    }
                                                                                                                                                                                  }
                                                                                                                                                                                  else
                                                                                                                                                                                  {
                                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                    v8 = &v105;
                                                                                                                                                                                  }
                                                                                                                                                                                }
                                                                                                                                                                                else
                                                                                                                                                                                {
                                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                  v8 = &v104;
                                                                                                                                                                                }
                                                                                                                                                                              }
                                                                                                                                                                              else
                                                                                                                                                                              {
                                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                                v8 = &v103;
                                                                                                                                                                              }
                                                                                                                                                                            }
                                                                                                                                                                            else
                                                                                                                                                                            {
                                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                              v8 = &v102;
                                                                                                                                                                            }
                                                                                                                                                                          }
                                                                                                                                                                          else
                                                                                                                                                                          {
                                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                            v8 = &v101;
                                                                                                                                                                          }
                                                                                                                                                                        }
                                                                                                                                                                        else
                                                                                                                                                                        {
                                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                          v8 = &v100;
                                                                                                                                                                        }
                                                                                                                                                                      }
                                                                                                                                                                      else
                                                                                                                                                                      {
                                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                        v8 = &v99;
                                                                                                                                                                      }
                                                                                                                                                                    }
                                                                                                                                                                    else
                                                                                                                                                                    {
                                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                      v8 = &v98;
                                                                                                                                                                    }
                                                                                                                                                                  }
                                                                                                                                                                  else
                                                                                                                                                                  {
                                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                    v8 = &v97;
                                                                                                                                                                  }
                                                                                                                                                                }
                                                                                                                                                                else
                                                                                                                                                                {
                                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                  v8 = &v96;
                                                                                                                                                                }
                                                                                                                                                              }
                                                                                                                                                              else
                                                                                                                                                              {
                                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                                v8 = &v95;
                                                                                                                                                              }
                                                                                                                                                            }
                                                                                                                                                            else
                                                                                                                                                            {
                                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                              v8 = &v94;
                                                                                                                                                            }
                                                                                                                                                          }
                                                                                                                                                          else
                                                                                                                                                          {
                                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                            v8 = &v93;
                                                                                                                                                          }
                                                                                                                                                        }
                                                                                                                                                        else
                                                                                                                                                        {
                                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                          v8 = &v92;
                                                                                                                                                        }
                                                                                                                                                      }
                                                                                                                                                      else
                                                                                                                                                      {
                                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                        v8 = &v91;
                                                                                                                                                      }
                                                                                                                                                    }
                                                                                                                                                    else
                                                                                                                                                    {
                                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                      v8 = &v90;
                                                                                                                                                    }
                                                                                                                                                  }
                                                                                                                                                  else
                                                                                                                                                  {
                                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                    v8 = &v89;
                                                                                                                                                  }
                                                                                                                                                }
                                                                                                                                                else
                                                                                                                                                {
                                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                  v8 = &v88;
                                                                                                                                                }
                                                                                                                                              }
                                                                                                                                              else
                                                                                                                                              {
                                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                                v8 = &v87;
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            else
                                                                                                                                            {
                                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                              v8 = &v86;
                                                                                                                                            }
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                            v8 = &v85;
                                                                                                                                          }
                                                                                                                                        }
                                                                                                                                        else
                                                                                                                                        {
                                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                          v8 = &v84;
                                                                                                                                        }
                                                                                                                                      }
                                                                                                                                      else
                                                                                                                                      {
                                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                        v8 = &v83;
                                                                                                                                      }
                                                                                                                                    }
                                                                                                                                    else
                                                                                                                                    {
                                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                      v8 = &v82;
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                  else
                                                                                                                                  {
                                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                    v8 = &v81;
                                                                                                                                  }
                                                                                                                                }
                                                                                                                                else
                                                                                                                                {
                                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                  v8 = &v80;
                                                                                                                                }
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                                v8 = &v79;
                                                                                                                              }
                                                                                                                            }
                                                                                                                            else
                                                                                                                            {
                                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                              v8 = &v78;
                                                                                                                            }
                                                                                                                          }
                                                                                                                          else
                                                                                                                          {
                                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                            v8 = &v77;
                                                                                                                          }
                                                                                                                        }
                                                                                                                        else
                                                                                                                        {
                                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                          v8 = &v76;
                                                                                                                        }
                                                                                                                      }
                                                                                                                      else
                                                                                                                      {
                                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                        v8 = &v75;
                                                                                                                      }
                                                                                                                    }
                                                                                                                    else
                                                                                                                    {
                                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                      v8 = &v74;
                                                                                                                    }
                                                                                                                  }
                                                                                                                  else
                                                                                                                  {
                                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                    v8 = &v73;
                                                                                                                  }
                                                                                                                }
                                                                                                                else
                                                                                                                {
                                                                                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                  v8 = &v72;
                                                                                                                }
                                                                                                              }
                                                                                                              else
                                                                                                              {
                                                                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                                v8 = &v71;
                                                                                                              }
                                                                                                            }
                                                                                                            else
                                                                                                            {
                                                                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                              v8 = &v70;
                                                                                                            }
                                                                                                          }
                                                                                                          else
                                                                                                          {
                                                                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                            v8 = &v69;
                                                                                                          }
                                                                                                        }
                                                                                                        else
                                                                                                        {
                                                                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                          v8 = &v68;
                                                                                                        }
                                                                                                      }
                                                                                                      else
                                                                                                      {
                                                                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                        v8 = &v67;
                                                                                                      }
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                      v8 = &v66;
                                                                                                    }
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                                                    v8 = &v65;
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                                                    a2,
                                                                                                    &v187);
                                                                                                  v8 = &v64;
                                                                                                }
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                Debugger::DataModel::ClientEx::Object::Object(
                                                                                                  a2,
                                                                                                  &v187);
                                                                                                v8 = &v63;
                                                                                              }
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              Debugger::DataModel::ClientEx::Object::Object(
                                                                                                a2,
                                                                                                &v187);
                                                                                              v8 = &v62;
                                                                                            }
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            Debugger::DataModel::ClientEx::Object::Object(
                                                                                              a2,
                                                                                              &v187);
                                                                                            v8 = &v61;
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          Debugger::DataModel::ClientEx::Object::Object(
                                                                                            a2,
                                                                                            &v187);
                                                                                          v8 = &v60;
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        Debugger::DataModel::ClientEx::Object::Object(
                                                                                          a2,
                                                                                          &v187);
                                                                                        v8 = &v59;
                                                                                      }
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      Debugger::DataModel::ClientEx::Object::Object(
                                                                                        a2,
                                                                                        &v187);
                                                                                      v8 = &v58;
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    Debugger::DataModel::ClientEx::Object::Object(
                                                                                      a2,
                                                                                      &v187);
                                                                                    v8 = &v57;
                                                                                  }
                                                                                }
                                                                                else
                                                                                {
                                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                                    a2,
                                                                                    &v187);
                                                                                  v8 = &v35;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                Debugger::DataModel::ClientEx::Object::Object(
                                                                                  a2,
                                                                                  &v187);
                                                                                v8 = &v55;
                                                                              }
                                                                            }
                                                                            else
                                                                            {
                                                                              Debugger::DataModel::ClientEx::Object::Object(
                                                                                a2,
                                                                                &v187);
                                                                              v8 = &v54;
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            Debugger::DataModel::ClientEx::Object::Object(
                                                                              a2,
                                                                              &v187);
                                                                            v8 = &v53;
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          Debugger::DataModel::ClientEx::Object::Object(
                                                                            a2,
                                                                            &v187);
                                                                          v8 = &v52;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        Debugger::DataModel::ClientEx::Object::Object(
                                                                          a2,
                                                                          &v187);
                                                                        v8 = &v51;
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      Debugger::DataModel::ClientEx::Object::Object(
                                                                        a2,
                                                                        &v187);
                                                                      v8 = &v50;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    Debugger::DataModel::ClientEx::Object::Object(
                                                                      a2,
                                                                      &v187);
                                                                    v8 = &v49;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  Debugger::DataModel::ClientEx::Object::Object(
                                                                    a2,
                                                                    &v187);
                                                                  v8 = &v48;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                                v8 = &v47;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                              v8 = &v46;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                            v8 = &v45;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                          v8 = &v44;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                        v8 = &v43;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                      v8 = &v42;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                    v8 = &v41;
                                                  }
                                                }
                                                else
                                                {
                                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                  v8 = &v40;
                                                }
                                              }
                                              else
                                              {
                                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                                v8 = &v39;
                                              }
                                            }
                                            else
                                            {
                                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                              v8 = &v38;
                                            }
                                          }
                                          else
                                          {
                                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                            v8 = &v37;
                                          }
                                        }
                                        else
                                        {
                                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                          v8 = &v36;
                                        }
                                      }
                                      else
                                      {
                                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                        v8 = &v18;
                                      }
                                    }
                                    else
                                    {
                                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                      v8 = &v34;
                                    }
                                  }
                                  else
                                  {
                                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                    v8 = &v33;
                                  }
                                }
                                else
                                {
                                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                  v8 = &v32;
                                }
                              }
                              else
                              {
                                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                                v8 = &v31;
                              }
                            }
                            else
                            {
                              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                              v8 = &v30;
                            }
                          }
                          else
                          {
                            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                            v8 = &v17;
                          }
                        }
                        else
                        {
                          Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                          v8 = &v28;
                        }
                      }
                      else
                      {
                        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                        v8 = &v27;
                      }
                    }
                    else
                    {
                      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                      v8 = &v26;
                    }
                  }
                  else
                  {
                    Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                    v8 = &v25;
                  }
                }
                else
                {
                  Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                  v8 = &v24;
                }
              }
              else
              {
                Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
                v8 = &v23;
              }
            }
            else
            {
              Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
              v8 = &v22;
            }
          }
          else
          {
            Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
            v8 = &v21;
          }
LABEL_7:
          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(v8);
LABEL_351:
          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v15);
          Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v14);
          return a2;
        }
        Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
LABEL_6:
        v8 = &v16;
        goto LABEL_7;
      }
      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
      v7 = &v20;
    }
    else
    {
      Debugger::DataModel::ClientEx::Object::Object(a2, &v187);
      v7 = &v19;
    }
    Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(v7);
    goto LABEL_6;
  }
  Debugger::DataModel::ClientEx::Object::CreateNoValue(a2);
  return a2;
}

```

## disassembly

```asm
0x1803af5f0  push    rbp
0x1803af5f2  push    rbx
0x1803af5f3  push    rsi
0x1803af5f4  push    rdi
0x1803af5f5  push    r14
0x1803af5f7  push    r15
0x1803af5f9  lea     rbp, [rsp-4B8h]
0x1803af601  sub     rsp, 5B8h
0x1803af608  mov     [rbp+4E0h+var_40], 0FFFFFFFFFFFFFFFEh
0x1803af613  mov     rsi, rdx
0x1803af616  mov     rcx, r8; this
0x1803af619  call    ?GetTargetFromContext@KernelTargetDetails@Libraries@DataModel@Debugger@@YAPEAVTargetInfo@@AEBVObject@ClientEx@34@@Z; Debugger::DataModel::Libraries::KernelTargetDetails::GetTargetFromContext(Debugger::DataModel::ClientEx::Object const &)
0x1803af61e  mov     r14, rax
0x1803af621  mov     rcx, [rax]
0x1803af624  mov     rax, [rcx+0B8h]
0x1803af62b  mov     rcx, r14
0x1803af62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af633  test    eax, eax
0x1803af635  jnz     short loc_1803AF644
0x1803af637  mov     rcx, rsi
0x1803af63a  call    ?CreateNoValue@Object@ClientEx@DataModel@Debugger@@SA?AV1234@XZ; Debugger::DataModel::ClientEx::Object::CreateNoValue(void)
0x1803af63f  jmp     loc_1803B3924
0x1803af644  add     r14, 320h
0x1803af64b  mov     [rbp+4E0h+var_70], 0
0x1803af652  mov     [rbp+4E0h+var_68], 0
0x1803af65d  lea     rdx, [rbp+4E0h+var_70]
0x1803af664  lea     rcx, [rsp+5E0h+var_5B0]
0x1803af669  call    ??$Create@$$V@Object@ClientEx@DataModel@Debugger@@SA?AV0123@AEBVHostContext@123@@Z; Debugger::DataModel::ClientEx::Object::Create<>(Debugger::DataModel::ClientEx::HostContext const &)
0x1803af66e  nop
0x1803af66f  lea     rcx, [rbp+4E0h+var_68]
0x1803af676  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af67b  mov     [rbp+4E0h+var_60], 0
0x1803af682  mov     [rbp+4E0h+var_58], 0
0x1803af68d  lea     rdx, [rbp+4E0h+var_60]
0x1803af694  lea     rcx, [rsp+5E0h+var_5A8]
0x1803af699  call    ??$Create@$$V@Object@ClientEx@DataModel@Debugger@@SA?AV0123@AEBVHostContext@123@@Z; Debugger::DataModel::ClientEx::Object::Create<>(Debugger::DataModel::ClientEx::HostContext const &)
0x1803af69e  nop
0x1803af69f  lea     rcx, [rbp+4E0h+var_58]
0x1803af6a6  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af6ab  mov     [rbp+4E0h+var_50], 0
0x1803af6b2  mov     [rbp+4E0h+var_48], 0
0x1803af6bd  lea     rdx, [rbp+4E0h+var_50]
0x1803af6c4  lea     rcx, [rsp+5E0h+var_5A0]
0x1803af6c9  call    ??$Create@$$V@Object@ClientEx@DataModel@Debugger@@SA?AV0123@AEBVHostContext@123@@Z; Debugger::DataModel::ClientEx::Object::Create<>(Debugger::DataModel::ClientEx::HostContext const &)
0x1803af6ce  nop
0x1803af6cf  lea     rcx, [rbp+4E0h+var_48]
0x1803af6d6  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af6db  mov     rdx, r14; unsigned __int64 *
0x1803af6de  lea     rcx, [rsp+5E0h+var_588]; this
0x1803af6e3  call    ??$?0AEA_KX@Object@ClientEx@DataModel@Debugger@@QEAA@AEA_K@Z; Debugger::DataModel::ClientEx::Object::Object(unsigned __int64 &)
0x1803af6e8  nop
0x1803af6e9  mov     rdi, [rsp+5E0h+var_5A0]
0x1803af6ee  mov     rax, [rdi]
0x1803af6f1  xor     r9d, r9d
0x1803af6f4  mov     r8, [rsp+5E0h+var_588]
0x1803af6f9  lea     rdx, aFlink; "Flink"
0x1803af700  mov     rcx, rdi
0x1803af703  mov     rax, [rax+0C0h]
0x1803af70a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af70f  mov     [rbp+4E0h+arg_18], eax
0x1803af715  test    eax, eax
0x1803af717  jns     short loc_1803AF743
0x1803af719  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af720  mov     rcx, rsi; this
0x1803af723  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af728  nop
0x1803af729  lea     rcx, [rsp+5E0h+var_588]
0x1803af72e  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af733  nop
0x1803af734  lea     rcx, [rsp+5E0h+var_5A0]
0x1803af739  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af73e  jmp     loc_1803B390F
0x1803af743  lea     rcx, [rsp+5E0h+var_588]
0x1803af748  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af74d  lea     rdx, [r14+8]; unsigned __int64 *
0x1803af751  lea     rcx, [rsp+5E0h+var_580]; this
0x1803af756  call    ??$?0AEA_KX@Object@ClientEx@DataModel@Debugger@@QEAA@AEA_K@Z; Debugger::DataModel::ClientEx::Object::Object(unsigned __int64 &)
0x1803af75b  nop
0x1803af75c  mov     rax, [rdi]
0x1803af75f  xor     r9d, r9d
0x1803af762  mov     r8, [rsp+5E0h+var_580]
0x1803af767  lea     rdx, aBlink; "Blink"
0x1803af76e  mov     rcx, rdi
0x1803af771  mov     rax, [rax+0C0h]
0x1803af778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af77d  mov     [rbp+4E0h+arg_18], eax
0x1803af783  test    eax, eax
0x1803af785  jns     short loc_1803AF79E
0x1803af787  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af78e  mov     rcx, rsi; this
0x1803af791  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af796  nop
0x1803af797  lea     rcx, [rsp+5E0h+var_580]
0x1803af79c  jmp     short loc_1803AF72E
0x1803af79e  lea     rcx, [rsp+5E0h+var_580]
0x1803af7a3  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af7a8  mov     rbx, [rsp+5E0h+var_5A8]
0x1803af7ad  mov     rax, [rbx]
0x1803af7b0  xor     r9d, r9d
0x1803af7b3  mov     r8, rdi
0x1803af7b6  lea     rdx, aList; "List"
0x1803af7bd  mov     rcx, rbx
0x1803af7c0  mov     rax, [rax+0C0h]
0x1803af7c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af7cc  mov     [rbp+4E0h+arg_18], eax
0x1803af7d2  test    eax, eax
0x1803af7d4  jns     short loc_1803AF7EA
0x1803af7d6  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af7dd  mov     rcx, rsi; this
0x1803af7e0  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af7e5  jmp     loc_1803AF734
0x1803af7ea  lea     rcx, [rsp+5E0h+var_5A0]
0x1803af7ef  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af7f4  lea     rdx, [r14+10h]; unsigned int *
0x1803af7f8  lea     rcx, [rsp+5E0h+var_578]; this
0x1803af7fd  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af802  nop
0x1803af803  mov     rax, [rbx]
0x1803af806  xor     r9d, r9d
0x1803af809  mov     r8, [rsp+5E0h+var_578]
0x1803af80e  lea     rdx, aOwnertag; "OwnerTag"
0x1803af815  mov     rcx, rbx
0x1803af818  mov     rax, [rax+0C0h]
0x1803af81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af824  mov     [rbp+4E0h+arg_18], eax
0x1803af82a  test    eax, eax
0x1803af82c  jns     short loc_1803AF848
0x1803af82e  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af835  mov     rcx, rsi; this
0x1803af838  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af83d  nop
0x1803af83e  lea     rcx, [rsp+5E0h+var_578]
0x1803af843  jmp     loc_1803AF739
0x1803af848  lea     rcx, [rsp+5E0h+var_578]
0x1803af84d  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af852  lea     r15, [r14+14h]
0x1803af856  mov     rdx, r15; unsigned int *
0x1803af859  lea     rcx, [rsp+5E0h+var_570]; this
0x1803af85e  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af863  nop
0x1803af864  mov     rax, [rbx]
0x1803af867  xor     r9d, r9d
0x1803af86a  mov     r8, [rsp+5E0h+var_570]
0x1803af86f  lea     rdx, aSize_0; "Size"
0x1803af876  mov     rcx, rbx
0x1803af879  mov     rax, [rax+0C0h]
0x1803af880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af885  mov     [rbp+4E0h+arg_18], eax
0x1803af88b  test    eax, eax
0x1803af88d  jns     short loc_1803AF8A9
0x1803af88f  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af896  mov     rcx, rsi; this
0x1803af899  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af89e  nop
0x1803af89f  lea     rcx, [rsp+5E0h+var_570]
0x1803af8a4  jmp     loc_1803AF739
0x1803af8a9  lea     rcx, [rsp+5E0h+var_570]
0x1803af8ae  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af8b3  mov     rdi, [rsp+5E0h+var_5B0]
0x1803af8b8  mov     rax, [rdi]
0x1803af8bb  xor     r9d, r9d
0x1803af8be  mov     r8, rbx
0x1803af8c1  lea     rdx, aHeader; "Header"
0x1803af8c8  mov     rcx, rdi
0x1803af8cb  mov     rax, [rax+0C0h]
0x1803af8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af8d7  mov     [rbp+4E0h+arg_18], eax
0x1803af8dd  test    eax, eax
0x1803af8df  jns     short loc_1803AF8F5
0x1803af8e1  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af8e8  mov     rcx, rsi; this
0x1803af8eb  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af8f0  jmp     loc_1803B390F
0x1803af8f5  lea     rdx, [r14+18h]; unsigned __int64 *
0x1803af8f9  lea     rcx, [rsp+5E0h+var_568]; this
0x1803af8fe  call    ??$?0AEA_KX@Object@ClientEx@DataModel@Debugger@@QEAA@AEA_K@Z; Debugger::DataModel::ClientEx::Object::Object(unsigned __int64 &)
0x1803af903  nop
0x1803af904  mov     rax, [rdi]
0x1803af907  xor     r9d, r9d
0x1803af90a  mov     r8, [rsp+5E0h+var_568]
0x1803af90f  lea     rdx, aKernbase; "KernBase"
0x1803af916  mov     rcx, rdi
0x1803af919  mov     rax, [rax+0C0h]
0x1803af920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af925  mov     [rbp+4E0h+arg_18], eax
0x1803af92b  test    eax, eax
0x1803af92d  jns     short loc_1803AF949
0x1803af92f  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af936  mov     rcx, rsi; this
0x1803af939  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af93e  nop
0x1803af93f  lea     rcx, [rsp+5E0h+var_568]
0x1803af944  jmp     loc_1803AF739
0x1803af949  lea     rcx, [rsp+5E0h+var_568]
0x1803af94e  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af953  lea     rdx, [r14+20h]; unsigned __int64 *
0x1803af957  lea     rcx, [rbp+4E0h+var_560]; this
0x1803af95b  call    ??$?0AEA_KX@Object@ClientEx@DataModel@Debugger@@QEAA@AEA_K@Z; Debugger::DataModel::ClientEx::Object::Object(unsigned __int64 &)
0x1803af960  nop
0x1803af961  mov     rax, [rdi]
0x1803af964  xor     r9d, r9d
0x1803af967  mov     r8, [rbp+4E0h+var_560]
0x1803af96b  lea     rdx, aBreakpointwith; "BreakpointWithStatus"
0x1803af972  mov     rcx, rdi
0x1803af975  mov     rax, [rax+0C0h]
0x1803af97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af981  mov     [rbp+4E0h+arg_18], eax
0x1803af987  test    eax, eax
0x1803af989  jns     short loc_1803AF9A4
0x1803af98b  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af992  mov     rcx, rsi; this
0x1803af995  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af99a  nop
0x1803af99b  lea     rcx, [rbp+4E0h+var_560]
0x1803af99f  jmp     loc_1803AF739
0x1803af9a4  lea     rcx, [rbp+4E0h+var_560]
0x1803af9a8  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803af9ad  lea     rdx, [r14+28h]; unsigned __int64 *
0x1803af9b1  lea     rcx, [rbp+4E0h+var_558]; this
0x1803af9b5  call    ??$?0AEA_KX@Object@ClientEx@DataModel@Debugger@@QEAA@AEA_K@Z; Debugger::DataModel::ClientEx::Object::Object(unsigned __int64 &)
0x1803af9ba  nop
0x1803af9bb  mov     rax, [rdi]
0x1803af9be  xor     r9d, r9d
0x1803af9c1  mov     r8, [rbp+4E0h+var_558]
0x1803af9c5  lea     rdx, aSavedcontext; "SavedContext"
0x1803af9cc  mov     rcx, rdi
0x1803af9cf  mov     rax, [rax+0C0h]
0x1803af9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803af9db  mov     [rbp+4E0h+arg_18], eax
0x1803af9e1  test    eax, eax
0x1803af9e3  jns     short loc_1803AF9FE
0x1803af9e5  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803af9ec  mov     rcx, rsi; this
0x1803af9ef  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803af9f4  nop
0x1803af9f5  lea     rcx, [rbp+4E0h+var_558]
0x1803af9f9  jmp     loc_1803AF739
0x1803af9fe  lea     rcx, [rbp+4E0h+var_558]
0x1803afa02  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803afa07  lea     rdx, [r14+30h]; unsigned __int16 *
0x1803afa0b  lea     rcx, [rbp+4E0h+var_550]; this
0x1803afa0f  call    ??$?0AEAGX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAG@Z; Debugger::DataModel::ClientEx::Object::Object(ushort &)
0x1803afa14  nop
0x1803afa15  mov     rax, [rdi]
0x1803afa18  xor     r9d, r9d
0x1803afa1b  mov     r8, [rbp+4E0h+var_550]
0x1803afa1f  lea     rdx, aThcallbackstac_0; "ThCallbackStack"
0x1803afa26  mov     rcx, rdi
0x1803afa29  mov     rax, [rax+0C0h]
0x1803afa30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803afa35  mov     [rbp+4E0h+arg_18], eax
0x1803afa3b  test    eax, eax
0x1803afa3d  jns     short loc_1803AFA58
0x1803afa3f  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803afa46  mov     rcx, rsi; this
0x1803afa49  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803afa4e  nop
0x1803afa4f  lea     rcx, [rbp+4E0h+var_550]
0x1803afa53  jmp     loc_1803AF739
0x1803afa58  lea     rcx, [rbp+4E0h+var_550]
0x1803afa5c  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803afa61  lea     rdx, [r14+32h]; unsigned __int16 *
0x1803afa65  lea     rcx, [rbp+4E0h+var_548]; this
0x1803afa69  call    ??$?0AEAGX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAG@Z; Debugger::DataModel::ClientEx::Object::Object(ushort &)
0x1803afa6e  nop
0x1803afa6f  mov     rax, [rdi]
0x1803afa72  xor     r9d, r9d
0x1803afa75  mov     r8, [rbp+4E0h+var_548]
0x1803afa79  lea     rdx, aNextcallback; "NextCallback"
0x1803afa80  mov     rcx, rdi
0x1803afa83  mov     rax, [rax+0C0h]
0x1803afa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803afa8f  mov     [rbp+4E0h+arg_18], eax
0x1803afa95  test    eax, eax
0x1803afa97  jns     short loc_1803AFAB2
0x1803afa99  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803afaa0  mov     rcx, rsi; this
0x1803afaa3  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
0x1803afaa8  nop
0x1803afaa9  lea     rcx, [rbp+4E0h+var_548]
0x1803afaad  jmp     loc_1803AF739
0x1803afab2  lea     rcx, [rbp+4E0h+var_548]
0x1803afab6  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1803afabb  lea     rdx, [r14+34h]; unsigned __int16 *
0x1803afabf  lea     rcx, [rbp+4E0h+var_540]; this
0x1803afac3  call    ??$?0AEAGX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAG@Z; Debugger::DataModel::ClientEx::Object::Object(ushort &)
0x1803afac8  nop
0x1803afac9  mov     rax, [rdi]
0x1803afacc  xor     r9d, r9d
0x1803afacf  mov     r8, [rbp+4E0h+var_540]
0x1803afad3  lea     rdx, aFramepointer; "FramePointer"
0x1803afada  mov     rcx, rdi
0x1803afadd  mov     rax, [rax+0C0h]
0x1803afae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803afae9  mov     [rbp+4E0h+arg_18], eax
0x1803afaef  test    eax, eax
0x1803afaf1  jns     short loc_1803AFB0C
0x1803afaf3  lea     rdx, [rbp+4E0h+arg_18]; unsigned int *
0x1803afafa  mov     rcx, rsi; this
0x1803afafd  call    ??$?0AEAKX@Object@ClientEx@DataModel@Debugger@@QEAA@AEAK@Z; Debugger::DataModel::ClientEx::Object::Object(ulong &)
  ... truncated ...
```
