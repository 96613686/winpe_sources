# CRunAnalysis::RunOperation(void)

- ea: `0x180053410`
- end: `0x180054650`
- name: `?RunOperation@CRunAnalysis@@UEAAJXZ`
- size: `4672`
- prototype: `__int64 __fastcall(CRunAnalysis *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800010dc`
- `0x1800014bc`
- `0x180001568`
- `0x180001620`
- `0x180006400`
- `0x18000ad50`
- `0x18000c644`
- `0x18000c794`
- `0x18000c848`
- `0x180011ac4`
- `0x1800140bc`
- `0x18001913c`
- `0x18001ff18`
- `0x180021430`
- `0x1800298ec`
- `0x18002acc4`
- `0x18002d66c`
- `0x18002dd8c`
- `0x1800384b8`
- `0x180046494`
- `0x180053410`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180053610`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180053610`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18005357b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180054175`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18005357b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180054175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CRunAnalysis::RunOperation(CRunAnalysis *this)
{
  unsigned int v2; // ebx
  int v3; // r15d
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r13
  __int16 v9; // ax
  struct IVolume *v10; // rbx
  __int64 (__fastcall *v11)(struct IVolume *, __int64, __int64 *); // r14
  __int64 v12; // rcx
  struct IVolume *v13; // rbx
  __int64 (__fastcall *v14)(struct IVolume *, __int64, __int64 *); // r14
  __int64 v15; // rcx
  struct IVolume *v16; // rbx
  __int64 (__fastcall *v17)(struct IVolume *, _QWORD, __int64 *); // r14
  __int64 v18; // rcx
  int v19; // r14d
  _OWORD *v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // rbx
  struct IFreeSpaceManager *v24; // rcx
  int BootOptSettings; // ebx
  int v26; // eax
  CSxGlobalTracer *v27; // rcx
  int BootOptimizationFile; // ecx
  int v29; // ecx
  unsigned __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ebx
  int v33; // eax
  __int64 v34; // rcx
  _BYTE *v35; // rax
  __int64 v36; // rax
  bool v37; // sf
  unsigned __int64 v38; // rax
  __int64 v39; // rcx
  __int128 *v40; // rax
  int v41; // eax
  _OWORD *v42; // rax
  _OWORD *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  unsigned int v53; // ebx
  struct IFreeSpaceManager *v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  struct IVolume *v59; // rcx
  unsigned int v61; // [rsp+110h] [rbp-80h] BYREF
  struct IVolume *v62; // [rsp+118h] [rbp-78h] BYREF
  unsigned int v63; // [rsp+120h] [rbp-70h] BYREF
  int v64; // [rsp+128h] [rbp-68h] BYREF
  __int16 v65; // [rsp+12Ch] [rbp-64h]
  __int16 v66; // [rsp+12Eh] [rbp-62h]
  __int64 v67; // [rsp+160h] [rbp-30h] BYREF
  int v68; // [rsp+168h] [rbp-28h] BYREF
  int v69; // [rsp+16Ch] [rbp-24h] BYREF
  struct IFreeSpaceManager *v70; // [rsp+170h] [rbp-20h] BYREF
  __int64 v71; // [rsp+178h] [rbp-18h] BYREF
  __int64 v72; // [rsp+180h] [rbp-10h] BYREF
  __int64 v73; // [rsp+188h] [rbp-8h] BYREF
  struct _SYSTEMTIME v74; // [rsp+190h] [rbp+0h] BYREF
  int v75; // [rsp+1A0h] [rbp+10h] BYREF
  int v76; // [rsp+1A4h] [rbp+14h] BYREF
  int v77; // [rsp+1A8h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+1B0h] [rbp+20h] BYREF
  unsigned __int64 v79; // [rsp+1B8h] [rbp+28h] BYREF
  __int64 v80; // [rsp+1C0h] [rbp+30h] BYREF
  const unsigned __int16 *v81; // [rsp+1C8h] [rbp+38h] BYREF
  unsigned __int64 v82; // [rsp+1D0h] [rbp+40h] BYREF
  int v83; // [rsp+1D8h] [rbp+48h] BYREF
  int v84; // [rsp+1DCh] [rbp+4Ch] BYREF
  int v85; // [rsp+1E0h] [rbp+50h] BYREF
  int v86; // [rsp+1E4h] [rbp+54h] BYREF
  int v87; // [rsp+1E8h] [rbp+58h] BYREF
  int v88; // [rsp+1ECh] [rbp+5Ch] BYREF
  int v89; // [rsp+1F0h] [rbp+60h] BYREF
  int v90; // [rsp+1F4h] [rbp+64h] BYREF
  int v91; // [rsp+1F8h] [rbp+68h] BYREF
  int v92; // [rsp+1FCh] [rbp+6Ch] BYREF
  int v93; // [rsp+200h] [rbp+70h] BYREF
  unsigned __int64 v94; // [rsp+208h] [rbp+78h] BYREF
  unsigned __int64 v95; // [rsp+210h] [rbp+80h] BYREF
  unsigned __int64 v96; // [rsp+218h] [rbp+88h] BYREF
  const unsigned __int16 *v97; // [rsp+220h] [rbp+90h] BYREF
  __int64 v98; // [rsp+228h] [rbp+98h] BYREF
  int v99; // [rsp+230h] [rbp+A0h] BYREF
  int v100; // [rsp+234h] [rbp+A4h] BYREF
  __int64 v101; // [rsp+238h] [rbp+A8h] BYREF
  __int64 v102; // [rsp+240h] [rbp+B0h] BYREF
  __int64 v103; // [rsp+248h] [rbp+B8h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+250h] [rbp+C0h] BYREF
  __int128 *v105; // [rsp+258h] [rbp+C8h] BYREF
  __int64 v106; // [rsp+260h] [rbp+D0h] BYREF
  unsigned __int64 v107; // [rsp+268h] [rbp+D8h] BYREF
  __int64 v108; // [rsp+270h] [rbp+E0h] BYREF
  __int64 v109; // [rsp+278h] [rbp+E8h] BYREF
  __int64 v110; // [rsp+280h] [rbp+F0h] BYREF
  __int64 v111; // [rsp+288h] [rbp+F8h] BYREF
  __int64 v112; // [rsp+290h] [rbp+100h] BYREF
  __int64 v113; // [rsp+298h] [rbp+108h] BYREF
  __int64 v114; // [rsp+2A0h] [rbp+110h] BYREF
  __int64 v115; // [rsp+2A8h] [rbp+118h] BYREF
  __int64 v116; // [rsp+2B0h] [rbp+120h] BYREF
  __int64 v117; // [rsp+2B8h] [rbp+128h] BYREF
  _BYTE v118[88]; // [rsp+2C0h] [rbp+130h] BYREF
  unsigned __int64 v119; // [rsp+318h] [rbp+188h]
  unsigned int v120; // [rsp+320h] [rbp+190h]
  __int64 v121; // [rsp+330h] [rbp+1A0h]
  __int64 v122; // [rsp+338h] [rbp+1A8h]
  unsigned __int64 v123; // [rsp+340h] [rbp+1B0h]
  unsigned __int64 v124; // [rsp+348h] [rbp+1B8h]
  unsigned __int64 v125; // [rsp+350h] [rbp+1C0h]
  int v126; // [rsp+380h] [rbp+1F0h]
  int v127; // [rsp+384h] [rbp+1F4h]
  unsigned int v128; // [rsp+38Ch] [rbp+1FCh]
  _BYTE v129[72]; // [rsp+4F8h] [rbp+368h] BYREF
  __int128 v130; // [rsp+540h] [rbp+3B0h] BYREF
  __int128 v131; // [rsp+550h] [rbp+3C0h] BYREF
  __int128 v132; // [rsp+560h] [rbp+3D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+570h] [rbp+3E0h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v64, "CRunAnalysis::RunOperation", 117, 1);
  v62 = 0;
  v73 = 0;
  v72 = 0;
  v71 = 0;
  v130 = 0;
  v63 = 0;
  v82 = 0;
  v103 = 1;
  v2 = 0;
  v61 = 0;
  memset_0(v118, 0, 0x280u);
  v67 = 0;
  v96 = 0;
  v3 = 0;
  v132 = 0;
  v77 = 0;
  v76 = 0;
  v68 = 0;
  pv = 0;
  v95 = 0;
  v94 = 0;
  v75 = 0;
  v99 = 0;
  v69 = 0;
  v93 = 0;
  v70 = 0;
  SystemTime = 0;
  v79 = 0;
  UnbiasedTime = 0;
  v131 = 0;
  v4 = 0;
  v102 = 0;
  v101 = 0;
  (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 5) + 152LL))(*((_QWORD *)this + 5), &v131);
  v8 = 5;
  if ( (unsigned int)dword_1800840E0 > 5 )
  {
    v81 = (const unsigned __int16 *)*((_QWORD *)this + 87);
    v80 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v5,
      (__int64)byte_18007795B,
      v6,
      v7,
      (__int64)&v80,
      &v81);
  }
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v64 = CDefragOperation::_ClearAnalysisStatistics(this);
  v9 = 171;
  if ( v64 < 0 )
    goto LABEL_141;
  v65 = 171;
  v64 = CDefragOperation::_SetPhase(this, 1u);
  v9 = 173;
  if ( v64 < 0 )
    goto LABEL_141;
  v65 = 173;
  v10 = (struct IVolume *)*((_QWORD *)this + 93);
  if ( v10 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*((_QWORD *)this + 93));
    v62 = v10;
  }
  else
  {
    v3 = 1;
    v64 = CDefragOperation::_CreateVolumeForFileSystem(this, &v62);
    v9 = 184;
    if ( v64 < 0 )
    {
      v2 = v61;
LABEL_141:
      v66 = v9;
      goto LABEL_142;
    }
    v65 = 184;
    GetLocalTime(&SystemTime);
    v10 = v62;
  }
  v11 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v10 + 104LL);
  v12 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v64 = v11(v10, 1, &v73);
  v9 = 193;
  if ( v64 < 0 )
    goto LABEL_140;
  v65 = 193;
  v13 = v62;
  v14 = *(__int64 (__fastcall **)(struct IVolume *, __int64, __int64 *))(*(_QWORD *)v62 + 104LL);
  v15 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v64 = v14(v13, 2, &v71);
  v9 = 194;
  if ( v64 < 0 )
    goto LABEL_140;
  v65 = 194;
  v16 = v62;
  v17 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64 *))(*(_QWORD *)v62 + 104LL);
  v18 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v64 = v17(v16, 0, &v72);
  v19 = 0;
  v9 = 195;
  if ( v64 < 0
    || (v65 = 195,
        v64 = (*(__int64 (__fastcall **)(struct IVolume *, _BYTE *))(*(_QWORD *)v62 + 48LL))(v62, v118),
        v9 = 198,
        v64 < 0) )
  {
LABEL_140:
    v2 = 0;
    goto LABEL_141;
  }
  v65 = 198;
  v20 = (_OWORD *)((char *)this + 56);
  v21 = v118;
  v22 = 5;
  do
  {
    *v20 = *v21;
    v20[1] = v21[1];
    v20[2] = v21[2];
    v20[3] = v21[3];
    v20[4] = v21[4];
    v20[5] = v21[5];
    v20[6] = v21[6];
    v20[7] = v21[7];
    v20 += 8;
    v21 += 8;
    --v22;
  }
  while ( v22 );
  v9 = 201;
  if ( !v120 )
  {
    v64 = -2147024809;
    goto LABEL_140;
  }
  v64 = 0;
  v65 = 201;
  v123 = 0x4000000uLL / v120;
  v124 = v123;
  if ( CDefragOperation::GetMoveSizeInBytes() / *((unsigned int *)this + 38) <= 1 )
  {
    v125 = 1;
  }
  else
  {
    v23 = *((unsigned int *)this + 38);
    v125 = CDefragOperation::GetMoveSizeInBytes() / v23;
  }
  if ( v120 > 0x4000 )
    v128 = 0;
  else
    v128 = 0x4000 / v120;
  v64 = (*(__int64 (__fastcall **)(struct IVolume *, _BYTE *))(*(_QWORD *)v62 + 368LL))(v62, v129);
  v9 = 222;
  if ( v64 < 0 )
    goto LABEL_140;
  v65 = 222;
  v24 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v64 = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), v119, &v70);
  v9 = 225;
  if ( v64 < 0 )
    goto LABEL_33;
  v65 = 225;
  v64 = (*(__int64 (__fastcall **)(struct IVolume *, int *, int *, int *, int *))(*(_QWORD *)v62 + 192LL))(
          v62,
          &v68,
          &v99,
          &v69,
          &v93);
  v9 = 228;
  if ( v64 < 0 )
    goto LABEL_33;
  BootOptSettings = 0;
  v65 = 228;
  if ( v69 )
  {
    *(_QWORD *)&v74.wYear = v122;
    *(_QWORD *)&v74.wHour = v121;
    (*(void (__fastcall **)(struct IFreeSpaceManager *, struct _SYSTEMTIME *))(*(_QWORD *)v70 + 48LL))(v70, &v74);
  }
  v26 = v68;
  if ( v68 )
  {
    if ( *((_DWORD *)this + 192) )
    {
      *(_QWORD *)&v74.wYear = &qword_18006F470;
      *(_QWORD *)&v74.wHour = 0;
      v132 = *(_OWORD *)((char *)this + 776);
      v95 = *((_QWORD *)this + 99);
      v94 = *((_QWORD *)this + 100);
      CBsString::Set((CBsString *)&v74, *((const unsigned __int16 **)this + 101));
      CBsString::Detach((CBsString *)&v74, (unsigned __int16 **)&pv);
      CBsString::_Release((LPVOID *)&v74);
    }
    else
    {
      BootOptSettings = CDefragOperation::_GetBootOptSettings(
                          this,
                          0,
                          (struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *)&v132,
                          &v68,
                          0,
                          &v95,
                          &v94,
                          (unsigned __int16 **)&pv);
    }
    v26 = v68;
  }
  if ( *((_DWORD *)this + 190) )
  {
    if ( *((_DWORD *)this + 191) )
    {
      if ( !v26 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_2f8400b1517734b788873a81a44fdf8e_Traceguids,
            (unsigned int)BootOptSettings);
          v27 = WPP_GLOBAL_Control;
        }
        v64 = BootOptSettings;
        v9 = 314;
        if ( BootOptSettings >= 0 )
        {
          v65 = 314;
          if ( v27 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v27 + 7) & 0x2000000) != 0 )
            WPP_SF_d(
              *((_QWORD *)v27 + 2),
              11,
              WPP_2f8400b1517734b788873a81a44fdf8e_Traceguids,
              (unsigned int)BootOptSettings);
          v64 = -1996488680;
          v9 = 325;
        }
        goto LABEL_33;
      }
      v64 = BootOptSettings;
      if ( BootOptSettings < 0 )
      {
        v66 = 332;
LABEL_55:
        v2 = v61;
        goto LABEL_142;
      }
      v65 = 332;
    }
    if ( v26 )
    {
      BootOptimizationFile = CDefragOperation::_ReadBootOptimizationFile(this, v95, v94, v62, (LPCWSTR)pv);
      v64 = BootOptimizationFile;
      v9 = 344;
      if ( BootOptimizationFile < 0 )
      {
LABEL_33:
        v2 = v61;
        goto LABEL_141;
      }
      v65 = 344;
      if ( BootOptimizationFile == 1 && *((_DWORD *)this + 191) )
      {
        v64 = -1996488677;
        v9 = 348;
        v2 = v61;
        goto LABEL_141;
      }
    }
  }
  v29 = (*(__int64 (__fastcall **)(struct IVolume *, unsigned int *, __int128 *, unsigned __int64 *))(*(_QWORD *)v62 + 32LL))(
          v62,
          &v63,
          &v130,
          &v82);
  v64 = v29;
  v9 = 352;
  if ( v29 < 0 )
    goto LABEL_33;
  v65 = 352;
  v30 = v82;
  if ( v69 )
  {
    v127 = v82;
    v126 = v82;
  }
  if ( v29 != 1 )
  {
    while ( v30 )
    {
      v31 = *(_QWORD *)v62;
      if ( v67 )
      {
        v64 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64, _QWORD))(v31 + 56))(v62, v63, v67, 0);
        v9 = 373;
        if ( v64 < 0 )
          goto LABEL_123;
        v65 = 373;
      }
      else
      {
        v64 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, _QWORD, __int64 *))(v31 + 56))(v62, v63, 0, &v67);
        if ( v64 < 0 )
        {
          v66 = 368;
          v4 = 0;
          goto LABEL_55;
        }
        v65 = 368;
      }
      v64 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v67 + 128LL))(v67, v118);
      v9 = 380;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 380;
      v64 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v67 + 64LL))(v67, 1, &v75);
      v9 = 383;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 383;
      if ( v75 )
      {
        v32 = 0;
        goto LABEL_97;
      }
      v64 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64 *))(*(_QWORD *)v67 + 40LL))(
              v67,
              v123,
              &v96);
      v9 = 388;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 388;
      v64 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v67 + 64LL))(v67, 128, &v76);
      v9 = 391;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 391;
      if ( v76 )
      {
        if ( v96 <= 2 )
          goto LABEL_79;
      }
      else if ( v96 <= 1 )
      {
        goto LABEL_79;
      }
      if ( !v3 )
      {
        v64 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v73 + 24LL))(v73, v63);
        v9 = 402;
        if ( v64 < 0 )
          goto LABEL_123;
        v65 = 402;
        v19 = 1;
        v32 = 1;
LABEL_87:
        v33 = (*(__int64 (__fastcall **)(__int64, struct IVolume *))(*(_QWORD *)v67 + 136LL))(v67, v62);
        v64 = v33;
        if ( v33 < 0 )
        {
          v9 = 410;
LABEL_123:
          v4 = 0;
          goto LABEL_33;
        }
        v65 = 410;
        if ( v33 != 1 )
          v19 = 1;
        goto LABEL_90;
      }
LABEL_79:
      v32 = 0;
      if ( !v3 || (*(int (__fastcall **)(struct IVolume *))(*(_QWORD *)v62 + 224LL))(v62) >= 0 )
        goto LABEL_87;
      v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 88LL))(v67);
      v9 = 422;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 422;
LABEL_90:
      if ( *((_DWORD *)this + 190) && v68 )
      {
        v64 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v67 + 64LL))(v67, 32, &v77);
        v9 = 435;
        if ( v64 < 0 )
          goto LABEL_123;
        v65 = 435;
        if ( v77 )
        {
          v64 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v71 + 24LL))(v71, v63);
          v9 = 439;
          if ( v64 < 0 )
            goto LABEL_123;
          v65 = 439;
          v19 = 1;
        }
      }
LABEL_97:
      if ( !v3 && !v32 && *((_DWORD *)this + 206) )
      {
        v4 = CoTaskMemAlloc(0x60u);
        v9 = 454;
        if ( !v4 )
        {
          v64 = -2147024882;
          goto LABEL_33;
        }
        v64 = 0;
        v65 = 454;
        v34 = 96;
        v35 = v4;
        do
        {
          *v35++ = 0;
          --v34;
        }
        while ( v34 );
        v64 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v67 + 232LL))(v67, &v101);
        v9 = 457;
        if ( v64 < 0 )
          goto LABEL_33;
        v65 = 457;
        v64 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v67 + 40LL))(v67, 0, &v102);
        v9 = 458;
        if ( v64 < 0 )
          goto LABEL_33;
        v65 = 458;
        v36 = v101 * v120;
        v4[2] = v36;
        v4[5] = v36;
        v4[6] = v102;
        (*(void (__fastcall **)(__int64, struct IVolume *, _QWORD *))(*(_QWORD *)v67 + 216LL))(v67, v62, v4 + 10);
        v64 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _BYTE *))(*(_QWORD *)v67 + 224LL))(v67, v4, v118);
        v9 = 465;
        if ( v64 < 0 )
          goto LABEL_33;
        v65 = 465;
        v64 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 6) + 176LL))(*((_QWORD *)this + 6), v4);
        v9 = 467;
        if ( v64 < 0 )
          goto LABEL_33;
        v65 = 467;
      }
      if ( v19 )
      {
        v64 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v72 + 24LL))(v72, v63);
        v19 = 0;
        v37 = v64 < 0;
        v9 = 481;
      }
      else
      {
        v64 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD))(*(_QWORD *)v62 + 152LL))(v62, v63);
        v19 = 0;
        v37 = v64 < 0;
        v9 = 476;
      }
      if ( v37 )
        goto LABEL_123;
      v65 = v9;
      v64 = (*(__int64 (__fastcall **)(CRunAnalysis *))(*(_QWORD *)this + 32LL))(this);
      v9 = 485;
      if ( v64 < 0 )
        goto LABEL_123;
      v65 = 485;
      v38 = 100 * v103 / v82;
      v2 = v38;
      if ( (unsigned int)v38 <= v61 )
      {
        v2 = v61;
      }
      else
      {
        v64 = CDefragOperation::_SetPercentComplete(this, v38);
        v9 = 491;
        if ( v64 < 0 )
          goto LABEL_123;
        v65 = 491;
        v61 = v2;
      }
      v39 = 16;
      v40 = &v130;
      do
      {
        *(_BYTE *)v40 = 0;
        v40 = (__int128 *)((char *)v40 + 1);
        --v39;
      }
      while ( v39 );
      v63 = 0;
      v41 = (*(__int64 (__fastcall **)(struct IVolume *, unsigned int *, __int128 *, __int64 *))(*(_QWORD *)v62 + 40LL))(
              v62,
              &v63,
              &v130,
              &v103);
      v64 = v41;
      if ( v41 < 0 )
      {
        v9 = 498;
        goto LABEL_128;
      }
      v65 = 498;
      if ( v41 == 1 )
        break;
      v30 = v82;
    }
  }
  v64 = CalculateAggregateStatistics(v118, v70);
  v2 = v61;
  v9 = 503;
  if ( v64 < 0 )
    goto LABEL_128;
  v65 = 503;
  if ( v61 == 100 )
    goto LABEL_133;
  v64 = CDefragOperation::_SetPercentComplete(this, 0x64u);
  v9 = 508;
  if ( v64 < 0 )
  {
LABEL_128:
    v4 = 0;
    goto LABEL_141;
  }
  v65 = 508;
LABEL_133:
  v42 = (_OWORD *)((char *)this + 56);
  v43 = v118;
  do
  {
    *v42 = *v43;
    v42[1] = v43[1];
    v42[2] = v43[2];
    v42[3] = v43[3];
    v42[4] = v43[4];
    v42[5] = v43[5];
    v42[6] = v43[6];
    v42[7] = v43[7];
    v42 += 8;
    v43 += 8;
    --v8;
  }
  while ( v8 );
  if ( v3 )
  {
    v44 = *((_QWORD *)this + 6);
    v74 = SystemTime;
    (*(void (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v44 + 80LL))(v44, &v74);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 112LL))(
      *((_QWORD *)this + 6),
      *((unsigned int *)this + 14));
  }
  v64 = CDefragOperation::_SetPhase(this, 0xDu);
  v4 = 0;
  v9 = 524;
  if ( v64 < 0 )
    goto LABEL_141;
  v65 = 524;
  v64 = 0;
LABEL_142:
  QueryUnbiasedInterruptTime(&v79);
  v79 = (v79 - UnbiasedTime + 9999) / 0x2710;
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 152LL))(*((_QWORD *)this + 6));
  if ( v64 >= 0 && v64 != 1 && dword_1800840E0 && (unsigned __int8)tlgKeywordOn(v45, 0x400000000000LL) )
  {
    v105 = &v131;
    v106 = v2;
    v107 = v79;
    v108 = *((_QWORD *)this + 34);
    v109 = *((_QWORD *)this + 28);
    v110 = *((_QWORD *)this + 26);
    v111 = *((_QWORD *)this + 27);
    v100 = *((_DWORD *)this + 24);
    v83 = *((_DWORD *)this + 26);
    v117 = *((_QWORD *)this + 79);
    v112 = *((_QWORD *)this + 77);
    v84 = *((_DWORD *)this + 22);
    v85 = *((_DWORD *)this + 21);
    v86 = *((_DWORD *)this + 18);
    v87 = *((_DWORD *)this + 20);
    v113 = *((_QWORD *)this + 14);
    v114 = *((_QWORD *)this + 29);
    v88 = *((_DWORD *)this + 30);
    v89 = *((_DWORD *)this + 156);
    v90 = *((_DWORD *)this + 16);
    v91 = *((_DWORD *)this + 15);
    v92 = *((_DWORD *)this + 14);
    v115 = *((_QWORD *)this + 16);
    v116 = *((_QWORD *)this + 17);
    v98 = *((_QWORD *)this + 18);
    LODWORD(v80) = *((_DWORD *)this + 38);
    LOBYTE(v61) = *((_BYTE *)this + 264);
    v97 = (const unsigned __int16 *)*((_QWORD *)this + 87);
    LODWORD(v81) = 2;
    *(_QWORD *)&v74.wYear = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
      v46,
      (__int64)word_18007770A,
      v47,
      v48,
      (__int64)&v74,
      (__int64)&v81,
      &v97,
      (__int64)&v61,
      (__int64)&v80,
      (__int64)&v98,
      (__int64)&v116,
      (__int64)&v115,
      (__int64)&v92,
      (__int64)&v91,
      (__int64)&v90,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v114,
      (__int64)&v113,
      (__int64)&v87,
      (__int64)&v86,
      (__int64)&v85,
      (__int64)&v84,
      (__int64)&v112,
      (__int64)&v117,
      (__int64)&v83,
      (__int64)&v100,
      (__int64)&v111,
      (__int64)&v110,
      (__int64)&v109,
      (__int64)&v108,
      (__int64)&v107,
      (__int64)&v106,
      (__int64 *)&v105);
  }
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v4);
  if ( dword_1800840E0 && (unsigned __int8)tlgKeywordOn(v49, 0x400000000000LL) )
  {
    LODWORD(v81) = v64;
    LOWORD(v61) = v66;
    *(_QWORD *)&v74.wYear = &v131;
    v97 = (const unsigned __int16 *)v79;
    LODWORD(v80) = 2;
    v98 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v50,
      (__int64)byte_18007769B,
      v51,
      v52,
      (__int64)&v98,
      (__int64)&v80,
      (__int64)&v97,
      (__int64 *)&v74,
      (__int64)&v61,
      (__int64)&v81);
  }
  if ( v3 )
    Log_DF_OPTIMIZE_RESULT(
      (struct CSxFunctionTracer *)&v64,
      0x250u,
      *((const unsigned __int16 **)this + 89),
      0x329u,
      v64,
      0);
  v53 = v64;
  v54 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v54 + 16LL))(v54);
  }
  v55 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  }
  v56 = v71;
  if ( v71 )
  {
    v71 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  }
  v57 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
  }
  v58 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  }
  v59 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v59 + 16LL))(v59);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v64);
  return v53;
}

```

## disassembly

```asm
0x180053410  push    rbp
0x180053412  push    rbx
0x180053413  push    rsi
0x180053414  push    rdi
0x180053415  push    r12
0x180053417  push    r13
0x180053419  push    r14
0x18005341b  push    r15
0x18005341d  lea     rbp, [rsp-408h]
0x180053425  sub     rsp, 598h
0x18005342c  mov     rax, cs:__security_cookie
0x180053433  xor     rax, rsp
0x180053436  mov     [rbp+440h+var_50], rax
0x18005343d  mov     rsi, rcx
0x180053440  mov     r12d, 1
0x180053446  mov     r9d, r12d; unsigned __int16
0x180053449  lea     r8d, [r12+74h]; unsigned __int16
0x18005344e  lea     rdx, aCrunanalysisRu; "CRunAnalysis::RunOperation"
0x180053455  lea     rcx, [rbp+440h+var_4A8]; this
0x180053459  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005345e  nop
0x18005345f  xor     r14d, r14d
0x180053462  mov     [rbp+440h+var_4B8], r14
0x180053466  mov     [rbp+440h+var_448], r14
0x18005346a  mov     [rbp+440h+var_450], r14
0x18005346e  mov     [rbp+440h+var_458], r14
0x180053472  xorps   xmm0, xmm0
0x180053475  movups  [rbp+440h+var_90], xmm0
0x18005347c  mov     [rbp+440h+var_4B0], r14d
0x180053480  mov     [rbp+440h+var_400], r14
0x180053484  mov     [rbp+440h+var_388], r12
0x18005348b  mov     ebx, r14d
0x18005348e  mov     [rbp+440h+var_4C0], ebx
0x180053491  xor     edx, edx; Val
0x180053493  mov     r8d, 280h; Size
0x180053499  lea     rcx, [rbp+440h+var_310]; void *
0x1800534a0  call    memset_0
0x1800534a5  mov     [rbp+440h+var_470], r14
0x1800534a9  mov     [rbp+440h+var_3B8], r14
0x1800534b0  mov     r15d, r14d
0x1800534b3  xorps   xmm0, xmm0
0x1800534b6  movups  [rbp+440h+var_70], xmm0
0x1800534bd  mov     [rbp+440h+var_428], r14d
0x1800534c1  mov     [rbp+440h+var_42C], r14d
0x1800534c5  mov     [rbp+440h+var_468], r14d
0x1800534c9  mov     [rbp+440h+pv], r14
0x1800534cd  mov     [rbp+440h+var_3C0], r14
0x1800534d4  mov     [rbp+440h+var_3C8], r14
0x1800534d8  mov     [rbp+440h+var_430], r14d
0x1800534dc  mov     [rbp+440h+var_3A0], r14d
0x1800534e3  mov     [rbp+440h+var_464], r14d
0x1800534e7  mov     [rbp+440h+var_3D0], r14d
0x1800534eb  mov     [rbp+440h+var_460], r14
0x1800534ef  movups  xmmword ptr [rbp+440h+SystemTime.wYear], xmm0
0x1800534f6  mov     [rbp+440h+var_418], r14
0x1800534fa  mov     [rbp+440h+UnbiasedTime], r14
0x180053501  movups  [rbp+440h+var_80], xmm0
0x180053508  mov     edi, r14d
0x18005350b  mov     [rbp+440h+var_390], r14
0x180053512  mov     [rbp+440h+var_398], r14
0x180053519  mov     rcx, [rsi+28h]
0x18005351d  mov     rax, [rcx]
0x180053520  lea     rdx, [rbp+440h+var_80]
0x180053527  mov     rax, [rax+98h]
0x18005352e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053533  mov     eax, cs:dword_1800840E0
0x180053539  lea     r13d, [r12+4]
0x18005353e  cmp     eax, r13d
0x180053541  jbe     short loc_180053574
0x180053543  mov     rax, [rsi+2B8h]
0x18005354a  mov     [rbp+440h+var_408], rax
0x18005354e  mov     [rbp+440h+var_410], 1000000h
0x180053556  lea     rax, [rbp+440h+var_408]
0x18005355a  mov     [rsp+5D0h+var_5A8], rax
0x18005355f  lea     rax, [rbp+440h+var_410]
0x180053563  mov     [rsp+5D0h+lpFileName], rax
0x180053568  lea     rdx, byte_18007795B
0x18005356f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180053574  lea     rcx, [rbp+440h+UnbiasedTime]; UnbiasedTime
0x18005357b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180053581  mov     rcx, rsi; this
0x180053584  call    ?_ClearAnalysisStatistics@CDefragOperation@@IEAAJXZ; CDefragOperation::_ClearAnalysisStatistics(void)
0x180053589  mov     [rbp+440h+var_4A8], eax
0x18005358c  test    eax, eax
0x18005358e  mov     eax, 0ABh
0x180053593  js      loc_18005416D
0x180053599  mov     [rbp+440h+var_4A4], ax
0x18005359d  mov     edx, r12d
0x1800535a0  mov     rcx, rsi
0x1800535a3  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x1800535a8  mov     [rbp+440h+var_4A8], eax
0x1800535ab  test    eax, eax
0x1800535ad  mov     eax, 0ADh
0x1800535b2  js      loc_18005416D
0x1800535b8  mov     [rbp+440h+var_4A4], ax
0x1800535bc  mov     rbx, [rsi+2E8h]
0x1800535c3  test    rbx, rbx
0x1800535c6  jnz     short loc_18005361C
0x1800535c8  mov     r15d, r12d
0x1800535cb  mov     rcx, [rbp+440h+var_4B8]
0x1800535cf  test    rcx, rcx
0x1800535d2  jz      short loc_1800535E5
0x1800535d4  mov     [rbp+440h+var_4B8], r14
0x1800535d8  mov     rax, [rcx]
0x1800535db  mov     rax, [rax+10h]
0x1800535df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535e4  nop
0x1800535e5  lea     rdx, [rbp+440h+var_4B8]; struct IVolume **
0x1800535e9  mov     rcx, rsi; this
0x1800535ec  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x1800535f1  mov     [rbp+440h+var_4A8], eax
0x1800535f4  test    eax, eax
0x1800535f6  mov     eax, 0B8h
0x1800535fb  jns     short loc_180053605
0x1800535fd  mov     ebx, [rbp+440h+var_4C0]
0x180053600  jmp     loc_18005416D
0x180053605  mov     [rbp+440h+var_4A4], ax
0x180053609  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x180053610  call    cs:__imp_GetLocalTime
0x180053616  mov     rbx, [rbp+440h+var_4B8]
0x18005361a  jmp     short loc_18005364A
0x18005361c  mov     rax, [rbx]
0x18005361f  mov     rcx, rbx
0x180053622  mov     rax, [rax+8]
0x180053626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005362b  nop
0x18005362c  mov     rcx, [rbp+440h+var_4B8]
0x180053630  test    rcx, rcx
0x180053633  jz      short loc_180053646
0x180053635  mov     [rbp+440h+var_4B8], r14
0x180053639  mov     rax, [rcx]
0x18005363c  mov     rax, [rax+10h]
0x180053640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053645  nop
0x180053646  mov     [rbp+440h+var_4B8], rbx
0x18005364a  mov     rax, [rbx]
0x18005364d  mov     r14, [rax+68h]
0x180053651  mov     rcx, [rbp+440h+var_448]
0x180053655  test    rcx, rcx
0x180053658  jz      short loc_18005366F
0x18005365a  mov     [rbp+440h+var_448], 0
0x180053662  mov     rax, [rcx]
0x180053665  mov     rax, [rax+10h]
0x180053669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005366e  nop
0x18005366f  lea     r8, [rbp+440h+var_448]
0x180053673  mov     edx, r12d
0x180053676  mov     rcx, rbx
0x180053679  mov     rax, r14
0x18005367c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053681  mov     [rbp+440h+var_4A8], eax
0x180053684  xor     r14d, r14d
0x180053687  test    eax, eax
0x180053689  mov     eax, 0C1h
0x18005368e  js      loc_18005416A
0x180053694  mov     [rbp+440h+var_4A4], ax
0x180053698  mov     rbx, [rbp+440h+var_4B8]
0x18005369c  mov     rax, [rbx]
0x18005369f  mov     r14, [rax+68h]
0x1800536a3  mov     rcx, [rbp+440h+var_458]
0x1800536a7  test    rcx, rcx
0x1800536aa  jz      short loc_1800536C1
0x1800536ac  mov     [rbp+440h+var_458], 0
0x1800536b4  mov     rax, [rcx]
0x1800536b7  mov     rax, [rax+10h]
0x1800536bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536c0  nop
0x1800536c1  lea     r8, [rbp+440h+var_458]
0x1800536c5  mov     edx, 2
0x1800536ca  mov     rcx, rbx
0x1800536cd  mov     rax, r14
0x1800536d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536d5  mov     [rbp+440h+var_4A8], eax
0x1800536d8  xor     r14d, r14d
0x1800536db  test    eax, eax
0x1800536dd  mov     eax, 0C2h
0x1800536e2  js      loc_18005416A
0x1800536e8  mov     [rbp+440h+var_4A4], ax
0x1800536ec  mov     rbx, [rbp+440h+var_4B8]
0x1800536f0  mov     rax, [rbx]
0x1800536f3  mov     r14, [rax+68h]
0x1800536f7  mov     rcx, [rbp+440h+var_450]
0x1800536fb  test    rcx, rcx
0x1800536fe  jz      short loc_180053715
0x180053700  mov     [rbp+440h+var_450], 0
0x180053708  mov     rax, [rcx]
0x18005370b  mov     rax, [rax+10h]
0x18005370f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053714  nop
0x180053715  lea     r8, [rbp+440h+var_450]
0x180053719  xor     edx, edx
0x18005371b  mov     rcx, rbx
0x18005371e  mov     rax, r14
0x180053721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053726  mov     [rbp+440h+var_4A8], eax
0x180053729  xor     r14d, r14d
0x18005372c  test    eax, eax
0x18005372e  mov     eax, 0C3h
0x180053733  js      loc_18005416A
0x180053739  mov     [rbp+440h+var_4A4], ax
0x18005373d  mov     rcx, [rbp+440h+var_4B8]
0x180053741  mov     rax, [rcx]
0x180053744  lea     rdx, [rbp+440h+var_310]
0x18005374b  mov     rax, [rax+30h]
0x18005374f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053754  mov     [rbp+440h+var_4A8], eax
0x180053757  test    eax, eax
0x180053759  mov     eax, 0C6h
0x18005375e  js      loc_18005416A
0x180053764  mov     [rbp+440h+var_4A4], ax
0x180053768  lea     r12, [rsi+38h]
0x18005376c  mov     rax, r12
0x18005376f  lea     rcx, [rbp+440h+var_310]
0x180053776  mov     rdx, r13
0x180053779  mov     r8d, 80h
0x18005377f  movups  xmm0, xmmword ptr [rcx]
0x180053782  movups  xmmword ptr [rax], xmm0
0x180053785  movups  xmm1, xmmword ptr [rcx+10h]
0x180053789  movups  xmmword ptr [rax+10h], xmm1
0x18005378d  movups  xmm0, xmmword ptr [rcx+20h]
0x180053791  movups  xmmword ptr [rax+20h], xmm0
0x180053795  movups  xmm1, xmmword ptr [rcx+30h]
0x180053799  movups  xmmword ptr [rax+30h], xmm1
0x18005379d  movups  xmm0, xmmword ptr [rcx+40h]
0x1800537a1  movups  xmmword ptr [rax+40h], xmm0
0x1800537a5  movups  xmm1, xmmword ptr [rcx+50h]
0x1800537a9  movups  xmmword ptr [rax+50h], xmm1
0x1800537ad  movups  xmm0, xmmword ptr [rcx+60h]
0x1800537b1  movups  xmmword ptr [rax+60h], xmm0
0x1800537b5  movups  xmm1, xmmword ptr [rcx+70h]
0x1800537b9  movups  xmmword ptr [rax+70h], xmm1
0x1800537bd  add     rax, r8
0x1800537c0  add     rcx, r8
0x1800537c3  sub     rdx, 1
0x1800537c7  jnz     short loc_18005377F
0x1800537c9  mov     ecx, [rbp+440h+var_2B0]
0x1800537cf  mov     eax, 0C9h
0x1800537d4  test    ecx, ecx
0x1800537d6  jz      loc_18005415D
0x1800537dc  mov     [rbp+440h+var_4A8], r14d
0x1800537e0  mov     [rbp+440h+var_4A4], ax
0x1800537e4  mov     eax, 4000000h
0x1800537e9  div     rcx
0x1800537ec  mov     [rbp+440h+var_290], rax
0x1800537f3  mov     [rbp+440h+var_288], rax
0x1800537fa  call    ?GetMoveSizeInBytes@CDefragOperation@@SA_KXZ; CDefragOperation::GetMoveSizeInBytes(void)
0x1800537ff  mov     ecx, [rsi+98h]
0x180053805  xor     edx, edx
0x180053807  div     rcx
0x18005380a  mov     ecx, 1
0x18005380f  cmp     rax, rcx
0x180053812  jbe     short loc_18005382D
0x180053814  mov     ebx, [rsi+98h]
0x18005381a  call    ?GetMoveSizeInBytes@CDefragOperation@@SA_KXZ; CDefragOperation::GetMoveSizeInBytes(void)
0x18005381f  xor     edx, edx
0x180053821  div     rbx
0x180053824  mov     [rbp+440h+var_280], rax
0x18005382b  jmp     short loc_180053834
0x18005382d  mov     [rbp+440h+var_280], rcx
0x180053834  mov     eax, 4000h
0x180053839  cmp     [rbp+440h+var_2B0], eax
0x18005383f  ja      short loc_180053851
0x180053841  xor     edx, edx
0x180053843  div     [rbp+440h+var_2B0]
0x180053849  mov     [rbp+440h+var_244], eax
0x18005384f  jmp     short loc_180053858
0x180053851  mov     [rbp+440h+var_244], r14d
0x180053858  mov     rcx, [rbp+440h+var_4B8]
0x18005385c  mov     rax, [rcx]
0x18005385f  lea     rdx, [rbp+440h+var_D8]
0x180053866  mov     rax, [rax+170h]
0x18005386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053872  mov     [rbp+440h+var_4A8], eax
0x180053875  test    eax, eax
0x180053877  mov     eax, 0DEh
0x18005387c  js      loc_180054164
0x180053882  mov     [rbp+440h+var_4A4], ax
0x180053886  mov     rcx, [rbp+440h+var_460]
0x18005388a  test    rcx, rcx
0x18005388d  jz      short loc_1800538A0
0x18005388f  mov     [rbp+440h+var_460], r14
0x180053893  mov     rax, [rcx]
0x180053896  mov     rax, [rax+10h]
0x18005389a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005389f  nop
0x1800538a0  lea     r8, [rbp+440h+var_460]; struct IFreeSpaceManager **
0x1800538a4  mov     rdx, [rbp+440h+var_2B8]; unsigned __int64
0x1800538ab  mov     rcx, [rsi+2B8h]; unsigned __int16 *
0x1800538b2  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x1800538b7  mov     [rbp+440h+var_4A8], eax
0x1800538ba  test    eax, eax
0x1800538bc  mov     eax, 0E1h
0x1800538c1  jns     short loc_1800538D1
0x1800538c3  mov     ebx, [rbp+440h+var_4C0]
0x1800538c6  mov     r12d, 1
0x1800538cc  jmp     loc_18005416D
0x1800538d1  mov     [rbp+440h+var_4A4], ax
0x1800538d5  mov     rcx, [rbp+440h+var_4B8]
0x1800538d9  mov     rax, [rcx]
0x1800538dc  lea     rdx, [rbp+440h+var_3D0]
  ... truncated ...
```
