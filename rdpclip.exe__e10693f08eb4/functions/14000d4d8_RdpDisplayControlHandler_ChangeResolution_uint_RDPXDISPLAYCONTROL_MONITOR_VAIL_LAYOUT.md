# RdpDisplayControlHandler::ChangeResolution(uint,_RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT *)

- ea: `0x14000d4d8`
- end: `0x14000e2ca`
- name: `?ChangeResolution@RdpDisplayControlHandler@@AEAAJIPEAU_RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT@@@Z`
- size: `3570`
- prototype: `__int64 __fastcall(RdpDisplayControlHandler *__hidden this, unsigned int, struct _RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f9b0`

## callees

- `0x1400028b4`
- `0x1400028f4`
- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x14000622c`
- `0x1400091fc`
- `0x1400092fc`
- `0x14000cae0`
- `0x14000d0a4`
- `0x14000d4d8`
- `0x140010500`
- `0x140010528`
- `0x140010d18`
- `0x140010e24`
- `0x140010e7c`
- `0x140010f38`
- `0x140010fc0`
- `0x140011054`
- `0x140031684`
- `0x1400318e8`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!ChangeDisplaySettingsExW` at `0x14000ddfc`
- `USER32!ChangeDisplaySettingsExW` at `0x14000defc`
- `USER32!ChangeDisplaySettingsExW` at `0x14000dfb2`
- `USER32!ChangeDisplaySettingsExW` at `0x14000e0c1`
- `USER32!ChangeDisplaySettingsExW` at `0x14000ddfc`
- `USER32!ChangeDisplaySettingsExW` at `0x14000defc`
- `USER32!ChangeDisplaySettingsExW` at `0x14000dfb2`
- `USER32!ChangeDisplaySettingsExW` at `0x14000e0c1`
- `USER32!EnumDisplayDevicesW` at `0x14000dd7a`
- `USER32!EnumDisplayDevicesW` at `0x14000df91`
- `USER32!EnumDisplayDevicesW` at `0x14000dd7a`
- `USER32!EnumDisplayDevicesW` at `0x14000df91`
- `USER32!EnumDisplaySettingsW` at `0x14000ddae`
- `USER32!EnumDisplaySettingsW` at `0x14000ddae`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000d73f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x14000d73f`
- `ntdll!EtwEventActivityIdControl` at `0x14000d709`
- `ntdll!EtwEventActivityIdControl` at `0x14000d709`

## string_xrefs

- `0x14000db16`: `RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION`
- `0x14000e201`: `ITSThread::ThreadWaitForMultipleObjects failed`

## pseudocode

```c
__int64 __fastcall RdpDisplayControlHandler::ChangeResolution(
        RdpDisplayControlHandler *this,
        DWORD a2,
        struct _RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT *a3)
{
  __int64 v3; // r12
  struct _RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT *v4; // r13
  unsigned int v6; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // ebx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  CTSReaderWriterLock *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  void *v15; // rcx
  __int64 *v16; // rbx
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r10
  __int64 v20; // r14
  int v21; // ecx
  int v22; // eax
  int v23; // edx
  _DWORD *v24; // rax
  int v25; // ecx
  bool v26; // zf
  __int64 v27; // rdx
  __int128 v28; // xmm0
  __int64 v29; // rcx
  _OWORD *v30; // rax
  __int128 *v31; // rcx
  __int128 v32; // xmm0
  int v33; // r12d
  PVOID *v34; // rcx
  int v35; // ebx
  unsigned int v36; // eax
  int v37; // ebx
  unsigned int v38; // eax
  __int64 v39; // rdx
  int v40; // ebx
  int v41; // r8d
  int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // ebx
  _QWORD *v45; // rax
  _QWORD *v46; // r14
  unsigned int v47; // eax
  char *v48; // rdx
  DWORD v49; // r10d
  __int64 v50; // r11
  __int64 v51; // r9
  int v52; // eax
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  __int64 v56; // rcx
  DWORD v57; // ebx
  int v58; // r14d
  unsigned int v59; // eax
  unsigned int v60; // eax
  __int64 v61; // r9
  int v62; // ecx
  DWORD v63; // eax
  unsigned int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  __int64 v70; // rdx
  __int64 v71; // r8
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  __int64 v78; // [rsp+28h] [rbp-D8h]
  int *v79; // [rsp+28h] [rbp-D8h]
  DWORD v81; // [rsp+54h] [rbp-ACh]
  __int64 v82; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v84; // [rsp+68h] [rbp-98h]
  RdpDisplayControlHandler *v85; // [rsp+70h] [rbp-90h]
  __int64 v86; // [rsp+78h] [rbp-88h] BYREF
  __int64 v87; // [rsp+80h] [rbp-80h]
  _DWORD v88[4]; // [rsp+88h] [rbp-78h]
  struct _RDPXDISPLAYCONTROL_MONITOR_VAIL_LAYOUT *v89; // [rsp+98h] [rbp-68h]
  char *v90; // [rsp+A0h] [rbp-60h]
  __m128i si128; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v92; // [rsp+B8h] [rbp-48h]
  DEVMODEW DevMode; // [rsp+C0h] [rbp-40h] BYREF
  CHAR InData[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _DWORD v95[163]; // [rsp+1A4h] [rbp+A4h] BYREF
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+430h] [rbp+330h] BYREF

  v3 = a2;
  v4 = a3;
  v89 = a3;
  v85 = this;
  memset_0(&DisplayDevice, 0, sizeof(DisplayDevice));
  *(_DWORD *)InData = 0;
  v6 = -1;
  memset_0(v95, 0, sizeof(v95));
  v83 = 0;
  v92 = -1;
  v86 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( (unsigned int)v3 > 0x10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024809);
    }
    v8 = -2147024809;
    goto LABEL_26;
  }
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
        v9,
        (__int64)"pMonitors");
    }
    v8 = -2147467261;
    goto LABEL_26;
  }
  if ( !(unsigned __int8)utl::vector<_UMRDP_MONITOR_CONTAINER_ATTRIBUTES,utl::allocator<_UMRDP_MONITOR_CONTAINER_ATTRIBUTES>>::_Resize<,0>(
                           &si128,
                           v3) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
        v10,
        -2147467259);
    }
    goto LABEL_18;
  }
  CTSReaderWriterLock::ReadLock((RdpDisplayControlHandler *)((char *)this + 112));
  if ( !*((_DWORD *)this + 32) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v11);
    }
    v12 = (RdpDisplayControlHandler *)((char *)this + 112);
    v8 = 1;
    CTSReaderWriterLock::ReadUnlock(v12);
    goto LABEL_25;
  }
  v15 = (void *)*((_QWORD *)this + 21);
  v90 = (char *)this + 168;
  ResetEvent(v15);
  CTSReaderWriterLock::ReadUnlock((RdpDisplayControlHandler *)((char *)this + 112));
  v16 = (__int64 *)_acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
                     (char *)this + 256,
                     &v82);
  if ( &v86 != v16 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v86,
      *v16);
    *v16 = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v82);
  v17 = si128.m128i_i64[0];
  v81 = 0;
  v82 = si128.m128i_i64[0];
  v95[0] = 1417290573;
  *(_DWORD *)InData = 656;
  v95[2] = v3;
  if ( (_DWORD)v3 )
  {
    v18 = 0;
    v87 = 0;
    do
    {
      v19 = 5 * v18;
      v88[0] = 100;
      v20 = 580 * v18;
      v88[1] = 140;
      v88[2] = 180;
      v84 = v19;
      v21 = *((_DWORD *)v4 + 145 * v18 + 1);
      v22 = *((_DWORD *)v4 + 145 * v18 + 3) - 1;
      v23 = *((_DWORD *)v4 + 145 * v18 + 2);
      v95[v19 + 3] = v21;
      v95[v19 + 5] = v22 + v21;
      v24 = &v95[5 * v18 + 7];
      v25 = *((_DWORD *)v4 + 145 * v18 + 4) - 1;
      v95[v19 + 4] = v23;
      v26 = (*((_BYTE *)v4 + 580 * v18) & 1) == 0;
      v95[v19 + 6] = v23 + v25;
      if ( !v26 )
        *v24 |= 1u;
      if ( (*((_BYTE *)v4 + v20) & 2) != 0 )
        *v24 |= 2u;
      v27 = 4;
      v28 = *(_OWORD *)((char *)v4 + v20 + 40);
      v95[5 * v18 + 83] = *(_DWORD *)((char *)v4 + v20 + 20);
      v95[5 * v18 + 84] = *(_DWORD *)((char *)v4 + v20 + 24);
      v29 = 540 * v18;
      *(_OWORD *)(v29 + v17) = v28;
      *(_DWORD *)(v29 + v17 + 16) = *(_DWORD *)((char *)v4 + v20 + 56);
      *(_DWORD *)(v29 + v17 + 20) = *(_DWORD *)((char *)v4 + v20 + 60);
      *(_DWORD *)(v29 + v17 + 536) = *(_DWORD *)((char *)v4 + v20 + 64);
      v30 = (_OWORD *)(v17 + 540 * v18 + 24);
      v31 = (__int128 *)((char *)v4 + v20 + 68);
      do
      {
        v32 = *v31;
        v31 += 8;
        *v30 = v32;
        v30 += 8;
        *(v30 - 7) = *(v31 - 7);
        *(v30 - 6) = *(v31 - 6);
        *(v30 - 5) = *(v31 - 5);
        *(v30 - 4) = *(v31 - 4);
        *(v30 - 3) = *(v31 - 3);
        *(v30 - 2) = *(v31 - 2);
        *(v30 - 1) = *(v31 - 1);
        --v27;
      }
      while ( v27 );
      v33 = *(_DWORD *)((char *)v4 + v20 + 20);
      if ( v33 )
      {
        if ( (unsigned int)(v33 - 10) <= 0x2706 && (unsigned int)(*(_DWORD *)((char *)v4 + v20 + 24) - 10) <= 0x2706 )
        {
LABEL_61:
          v34 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_46;
        }
      }
      else if ( !*(_DWORD *)((char *)v4 + v20 + 24) )
      {
        goto LABEL_61;
      }
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v35 = *(_DWORD *)((char *)v4 + v20 + 24);
        v36 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
          v36,
          v33,
          v35);
        v34 = (PVOID *)WPP_GLOBAL_Control;
        v19 = v84;
      }
      *(_QWORD *)&v95[v19 + 83] = 0;
LABEL_46:
      v37 = *(_DWORD *)((char *)v4 + v20 + 28);
      if ( v37 && v37 != 90 && v37 != 180 && v37 != 270 )
      {
        if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x100) != 0 && *((_BYTE *)v34 + 25) >= 3u )
        {
          v38 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v38, v37);
          v34 = (PVOID *)WPP_GLOBAL_Control;
          v19 = v84;
        }
        v37 = 0;
      }
      v95[v19 + 85] = v37;
      v39 = 0;
      v40 = *(_DWORD *)((char *)v4 + v20 + 32);
      v41 = *(_DWORD *)((char *)v4 + v20 + 36);
      while ( v41 != v88[v39] )
      {
        v39 = (unsigned int)(v39 + 1);
        if ( (unsigned int)v39 >= 3 )
        {
          v42 = 0;
          goto LABEL_63;
        }
      }
      v42 = 1;
LABEL_63:
      if ( (unsigned int)(v40 - 100) > 0x190 || !v42 )
      {
        if ( v34 != &WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x100) != 0 && *((_BYTE *)v34 + 25) >= 3u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83,
            &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
            v43,
            v40,
            v40);
          v19 = v84;
        }
        v41 = 0;
        v40 = 0;
      }
      LODWORD(v3) = a2;
      v95[v19 + 86] = v40;
      v95[v19 + 87] = v41;
      v18 = v87 + 1;
      ++v81;
      ++v87;
      v17 = v82;
    }
    while ( v81 < a2 );
  }
  v44 = 136 * v3 + 24;
  v45 = operator new(v44);
  v46 = v45;
  if ( !v45 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v47 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
        v47,
        (__int64)"RDPIDD_OPCODE_SET_MONITOR_CONFIGURATION");
    }
    LODWORD(v3) = a2;
    v8 = -2147024882;
    goto LABEL_25;
  }
  memset_0(v45, 0, v44);
  LODWORD(v3) = a2;
  v48 = (char *)(v46 + 3);
  v49 = 0;
  v46[1] = 10;
  *(_DWORD *)v46 = v44;
  if ( !a2 )
    goto LABEL_89;
  v50 = v82;
  v51 = 0;
  do
  {
    *(_DWORD *)v48 = 136;
    *((_DWORD *)v48 + 1) = 1;
    *((_DWORD *)v48 + 5) = v49;
    *((_DWORD *)v48 + 6) = 48;
    *((_DWORD *)v48 + 7) = 2;
    *((_DWORD *)v48 + 8) = v95[5 * v51 + 3];
    *((_DWORD *)v48 + 9) = v95[5 * v51 + 4];
    *((_DWORD *)v48 + 10) = v95[5 * v51 + 5] - v95[5 * v51 + 3] + 1;
    v52 = v95[5 * v51 + 6] - v95[5 * v51 + 4] + 1;
    *((_DWORD *)v48 + 14) = 32;
    *((_DWORD *)v48 + 11) = v52;
    *((_DWORD *)v48 + 15) = 1;
    *((_DWORD *)v48 + 16) = 1;
    *((_DWORD *)v48 + 17) = 1;
    v53 = v95[5 * v51 + 85];
    if ( v53 )
    {
      v54 = v53 - 90;
      if ( !v54 )
      {
        *((_DWORD *)v48 + 13) = 90;
        goto LABEL_87;
      }
      v55 = v54 - 90;
      if ( !v55 )
      {
        *((_DWORD *)v48 + 13) = 180;
        goto LABEL_87;
      }
      if ( v55 == 90 )
      {
        *((_DWORD *)v48 + 13) = 270;
        goto LABEL_87;
      }
    }
    *((_DWORD *)v48 + 13) = 0;
LABEL_87:
    *((_DWORD *)v48 + 18) = 16;
    ++v49;
    *((_DWORD *)v48 + 19) = 3;
    *((_DWORD *)v48 + 20) = v95[5 * v51 + 86];
    *((_DWORD *)v48 + 21) = v95[5 * v51 + 87];
    *((_DWORD *)v48 + 22) = 16;
    *((_DWORD *)v48 + 23) = 4;
    *((_DWORD *)v48 + 24) = v95[5 * v51 + 83];
    *((_DWORD *)v48 + 25) = v95[5 * v51 + 84];
    v56 = 540 * v51;
    *((_DWORD *)v48 + 26) = 32;
    ++v51;
    *((_DWORD *)v48 + 27) = 8;
    *((_QWORD *)v48 + 14) = *(_QWORD *)(v56 + v50);
    *((_DWORD *)v48 + 30) = *(_DWORD *)(v56 + v50 + 8);
    *((_DWORD *)v48 + 31) = *(_DWORD *)(v56 + v50 + 12);
    *((_DWORD *)v48 + 32) = *(_DWORD *)(v56 + v50 + 16);
    *((_DWORD *)v48 + 33) = *(_DWORD *)(v56 + v50 + 20);
    v48 += 136;
  }
  while ( v49 < a2 );
  v4 = v89;
LABEL_89:
  v8 = SendToRDPIDD(2147483716LL, *(_DWORD *)v46, v46);
  operator delete(v46);
  if ( v8 >= 0 )
  {
LABEL_25:
    v6 = -1;
    goto LABEL_26;
  }
  v57 = 0;
  v58 = SendToRDPUDD(75266, 656, InData);
  if ( v58 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v59 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v78) = v58;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
      v59,
      (__int64)"SendToRDPUDD failed. Try to change the resolution anyway",
      v78);
  }
  DisplayDevice.cb = 840;
  if ( !EnumDisplayDevicesW(0, 0, &DisplayDevice, 0) )
  {
LABEL_120:
    v6 = ChangeDisplaySettingsExW(0, 0, 0, 0, 0);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v67 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v67, v6);
      }
      goto LABEL_18;
    }
    v6 = ChangeDisplaySettingsExW(0, 0, 0, 0x20000000u, 0);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v72 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v72, v6);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v73 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v73);
      }
      v79 = &v83;
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)v85 + 20) + 80LL))(
             *((_QWORD *)v85 + 20),
             1,
             v90);
      if ( v8 == -2092630012 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v74 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v74);
        }
        goto LABEL_26;
      }
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v75 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v79) = v8;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
            v75,
            (__int64)"ITSThread::ThreadWaitForMultipleObjects failed",
            v79);
        }
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v76 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v76);
      }
    }
    v8 = 0;
    goto LABEL_26;
  }
  while ( 2 )
  {
    memset_0(&DevMode, 0, sizeof(DevMode));
    DevMode.dmSize = 220;
    if ( !EnumDisplaySettingsW(DisplayDevice.DeviceName, 0, &DevMode) )
    {
LABEL_119:
      memset_0(DisplayDevice.DeviceName, 0, 0x344u);
      ++v57;
      DisplayDevice.cb = 840;
      if ( !EnumDisplayDevicesW(0, v57, &DisplayDevice, 0) )
        goto LABEL_120;
      continue;
    }
    break;
  }
  if ( v57 >= a2 )
  {
    if ( (DisplayDevice.StateFlags & 1) != 0 )
    {
      *(_QWORD *)&DevMode.dmOrientation = 0;
      *(_QWORD *)&DevMode.dmPelsWidth = 0;
      DevMode.dmFields = 1572896;
      v6 = ChangeDisplaySettingsExW(DisplayDevice.DeviceName, &DevMode, 0, 0x10000001u, 0);
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v68 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v68, v57);
        }
        goto LABEL_18;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v60 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6 + 87,
          &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
          v60,
          v57);
      }
    }
    goto LABEL_119;
  }
  v61 = 580LL * v57;
  DevMode.dmPelsWidth = *(_DWORD *)((char *)v4 + v61 + 12);
  DevMode.dmPelsHeight = *(_DWORD *)((char *)v4 + v61 + 16);
  *(_QWORD *)&DevMode.dmOrientation = *(_QWORD *)((char *)v4 + v61 + 4);
  if ( *((_DWORD *)v85 + 59) )
  {
    DevMode.dmFields = 1572896;
  }
  else
  {
    v62 = *(_DWORD *)((char *)v4 + v61 + 28);
    if ( v62 == 90 )
    {
      DevMode.dmDisplayOrientation = 1;
    }
    else if ( v62 == 180 )
    {
      DevMode.dmDisplayOrientation = 2;
    }
    else
    {
      v63 = 0;
      if ( v62 == 270 )
        v63 = 3;
      DevMode.dmDisplayOrientation = v63;
    }
    DevMode.dmFields = 1573024;
  }
  v6 = ChangeDisplaySettingsExW(
         DisplayDevice.DeviceName,
         &DevMode,
         0,
         16 * (*(_DWORD *)((_BYTE *)v4 + v61) & 1) + 268435585,
         0);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v64 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v65,
        v66,
        v64,
        v57,
        DevMode.dmPelsWidth,
        DevMode.dmPelsHeight,
        DevMode.dmPosition.x,
        DevMode.dmPosition.y);
    }
    goto LABEL_119;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v69 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v70,
      v71,
      v69,
      v57,
      DevMode.dmPelsWidth,
      DevMode.dmPelsHeight,
      DevMode.dmPosition.x,
      DevMode.dmPosition.y,
      v6);
  }
LABEL_18:
  v8 = -2147467259;
LABEL_26:
  EtwEventActivityIdControl(2, (char *)v85 + 240);
  if ( v8 < 0 )
  {
    if ( (Microsoft_Windows_RemoteDesktopServices_SessionServicesEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v14, v13, v6);
  }
  else if ( (Microsoft_Windows_RemoteDesktopServices_SessionServicesEnableBits & 1) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(v14, v13, (unsigned int)v3);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v86);
  utl::vector<void *,utl::allocator<void *>>::_Uninit(&si128);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000d4d8  mov     [rsp-8+arg_18], rbx
0x14000d4dd  push    rbp
0x14000d4de  push    rsi
0x14000d4df  push    rdi
0x14000d4e0  push    r12
0x14000d4e2  push    r13
0x14000d4e4  push    r14
0x14000d4e6  push    r15
0x14000d4e8  lea     rbp, [rsp-690h]
0x14000d4f0  sub     rsp, 790h
0x14000d4f7  mov     rax, cs:__security_cookie
0x14000d4fe  xor     rax, rsp
0x14000d501  mov     [rbp+6C0h+var_40], rax
0x14000d508  mov     r12d, edx
0x14000d50b  mov     r13, r8
0x14000d50e  mov     [rbp+6C0h+var_728], r8
0x14000d512  mov     rbx, rcx
0x14000d515  mov     [rsp+7C0h+var_750], rcx
0x14000d51a  xor     edx, edx; Val
0x14000d51c  mov     r8d, 348h; Size
0x14000d522  mov     [rsp+7C0h+var_770], r12d
0x14000d527  lea     rcx, [rbp+6C0h+DisplayDevice]; void *
0x14000d52e  call    memset_0
0x14000d533  xor     edi, edi
0x14000d535  lea     rcx, [rbp+6C0h+var_61C]; void *
0x14000d53c  xor     edx, edx; Val
0x14000d53e  mov     dword ptr [rbp+6C0h+InData], edi
0x14000d544  mov     r8d, 28Ch; Size
0x14000d54a  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000d54e  call    memset_0
0x14000d553  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000d55b  mov     [rsp+7C0h+var_760], edi
0x14000d55f  mov     [rbp+6C0h+var_708], r14
0x14000d563  mov     [rsp+7C0h+var_748], rdi
0x14000d568  movdqu  [rbp+6C0h+var_718], xmm0
0x14000d56d  cmp     r12d, 10h
0x14000d571  jbe     short loc_14000D5C7
0x14000d573  mov     rax, cs:WPP_GLOBAL_Control
0x14000d57a  lea     rdi, WPP_GLOBAL_Control
0x14000d581  cmp     rax, rdi
0x14000d584  jz      short loc_14000D5BD
0x14000d586  test    byte ptr [rax+1Ch], 8
0x14000d58a  jz      short loc_14000D5BD
0x14000d58c  cmp     byte ptr [rax+19h], 2
0x14000d590  jb      short loc_14000D5BD
0x14000d592  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d597  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d59e  lea     edx, [r14+4Eh]
0x14000d5a2  mov     r9d, eax
0x14000d5a5  mov     dword ptr [rsp+7C0h+lParam], 80070057h
0x14000d5ad  lea     r8, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000d5b4  mov     rcx, [rcx+10h]
0x14000d5b8  call    WPP_SF_Dd
0x14000d5bd  mov     ebx, 80070057h
0x14000d5c2  jmp     loc_14000D6F8
0x14000d5c7  test    r13, r13
0x14000d5ca  jnz     short loc_14000D624
0x14000d5cc  mov     rax, cs:WPP_GLOBAL_Control
0x14000d5d3  lea     rdi, WPP_GLOBAL_Control
0x14000d5da  cmp     rax, rdi
0x14000d5dd  jz      short loc_14000D61A
0x14000d5df  test    byte ptr [rax+1Ch], 8
0x14000d5e3  jz      short loc_14000D61A
0x14000d5e5  cmp     byte ptr [rax+19h], 2
0x14000d5e9  jb      short loc_14000D61A
0x14000d5eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d5f0  lea     rcx, aPmonitors; "pMonitors"
0x14000d5f7  mov     r9d, eax
0x14000d5fa  mov     [rsp+7C0h+lParam], rcx
0x14000d5ff  lea     edx, [r13+4Eh]
0x14000d603  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d60a  lea     r8, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000d611  mov     rcx, [rcx+10h]
0x14000d615  call    WPP_SF_Ds
0x14000d61a  mov     ebx, 80004003h
0x14000d61f  jmp     loc_14000D6F8
0x14000d624  mov     rdx, r12
0x14000d627  lea     rcx, [rbp+6C0h+var_718]
0x14000d62b  call    ??$_Resize@$$V$0A@@?$vector@U_UMRDP_MONITOR_CONTAINER_ATTRIBUTES@@V?$allocator@U_UMRDP_MONITOR_CONTAINER_ATTRIBUTES@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<_UMRDP_MONITOR_CONTAINER_ATTRIBUTES,utl::allocator<_UMRDP_MONITOR_CONTAINER_ATTRIBUTES>>::_Resize<,0>(unsigned __int64)
0x14000d630  test    al, al
0x14000d632  jnz     short loc_14000D686
0x14000d634  mov     rax, cs:WPP_GLOBAL_Control
0x14000d63b  lea     rdi, WPP_GLOBAL_Control
0x14000d642  cmp     rax, rdi
0x14000d645  jz      short loc_14000D67F
0x14000d647  test    byte ptr [rax+1Ch], 8
0x14000d64b  jz      short loc_14000D67F
0x14000d64d  cmp     byte ptr [rax+19h], 2
0x14000d651  jb      short loc_14000D67F
0x14000d653  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d658  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d65f  lea     r8, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000d666  mov     edx, 4Fh ; 'O'
0x14000d66b  mov     dword ptr [rsp+7C0h+lParam], 80004005h
0x14000d673  mov     r9d, eax
0x14000d676  mov     rcx, [rcx+10h]
0x14000d67a  call    WPP_SF_Dd
0x14000d67f  mov     ebx, 80004005h
0x14000d684  jmp     short loc_14000D6F8
0x14000d686  lea     r14, [rbx+70h]
0x14000d68a  mov     rcx, r14; this
0x14000d68d  call    ?ReadLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadLock(void)
0x14000d692  cmp     [rbx+80h], edi
0x14000d698  jnz     loc_14000D731
0x14000d69e  mov     rax, cs:WPP_GLOBAL_Control
0x14000d6a5  lea     rdi, WPP_GLOBAL_Control
0x14000d6ac  cmp     rax, rdi
0x14000d6af  jz      short loc_14000D6E7
0x14000d6b1  mov     r15d, 100h
0x14000d6b7  test    [rax+1Ch], r15d
0x14000d6bb  jz      short loc_14000D6E7
0x14000d6bd  cmp     byte ptr [rax+19h], 4
0x14000d6c1  jb      short loc_14000D6E7
0x14000d6c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d6cf  lea     r8, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000d6d6  mov     edx, 50h ; 'P'
0x14000d6db  mov     r9d, eax
0x14000d6de  mov     rcx, [rcx+10h]
0x14000d6e2  call    WPP_SF_d
0x14000d6e7  mov     rcx, r14; this
0x14000d6ea  mov     ebx, 1
0x14000d6ef  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x14000d6f4  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000d6f8  mov     rdx, [rsp+7C0h+var_750]
0x14000d6fd  mov     ecx, 2
0x14000d702  add     rdx, 0F0h
0x14000d709  call    cs:__imp_EtwEventActivityIdControl
0x14000d70f  test    ebx, ebx
0x14000d711  js      loc_14000E27A
0x14000d717  test    cs:Microsoft_Windows_RemoteDesktopServices_SessionServicesEnableBits, 1
0x14000d71e  jz      loc_14000E28B
0x14000d724  mov     r8d, r12d
0x14000d727  call    McTemplateU0q_EventWriteTransfer
0x14000d72c  jmp     loc_14000E28B
0x14000d731  lea     rax, [rbx+0A8h]
0x14000d738  mov     rcx, [rax]; hEvent
0x14000d73b  mov     [rbp+6C0h+var_720], rax
0x14000d73f  call    cs:__imp_ResetEvent
0x14000d745  mov     rcx, r14; this
0x14000d748  call    ?ReadUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::ReadUnlock(void)
0x14000d74d  lea     rdx, [rsp+7C0h+var_768]
0x14000d752  lea     rcx, [rbx+100h]
0x14000d759  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000d75e  mov     rbx, rax
0x14000d761  lea     rax, [rsp+7C0h+var_748]
0x14000d766  cmp     rax, rbx
0x14000d769  jz      short loc_14000D77B
0x14000d76b  mov     rdx, [rbx]
0x14000d76e  lea     rcx, [rsp+7C0h+var_748]
0x14000d773  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000d778  mov     [rbx], rdi
0x14000d77b  lea     rcx, [rsp+7C0h+var_768]
0x14000d780  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000d785  mov     r9, qword ptr [rbp+6C0h+var_718]
0x14000d789  lea     rsi, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000d790  mov     [rsp+7C0h+var_76C], edi
0x14000d794  lea     rdi, WPP_GLOBAL_Control
0x14000d79b  mov     [rsp+7C0h+var_768], r9
0x14000d7a0  mov     r15d, 100h
0x14000d7a6  mov     [rbp+6C0h+var_61C], 547A234Dh
0x14000d7b0  mov     r11d, 3
0x14000d7b6  mov     dword ptr [rbp+6C0h+InData], 290h
0x14000d7c0  mov     [rbp+6C0h+var_614], r12d
0x14000d7c7  test    r12d, r12d
0x14000d7ca  jz      loc_14000DADD
0x14000d7d0  xor     r8d, r8d
0x14000d7d3  mov     [rbp+6C0h+var_740], r8
0x14000d7d7  jmp     short loc_14000D7DF
0x14000d7d9  mov     r11d, 3
0x14000d7df  lea     r10, [r8+r8*4]
0x14000d7e3  mov     [rbp+6C0h+var_738], 64h ; 'd'
0x14000d7ea  imul    r14, r8, 244h
0x14000d7f1  mov     [rbp+6C0h+var_734], 8Ch
0x14000d7f8  mov     [rbp+6C0h+var_730], 0B4h
0x14000d7ff  mov     [rsp+7C0h+var_758], r10
0x14000d804  mov     eax, [r14+r13+0Ch]
0x14000d809  mov     ecx, [r14+r13+4]
0x14000d80e  dec     eax
0x14000d810  mov     edx, [r14+r13+8]
0x14000d815  mov     [rbp+r10*4+6C0h+var_610], ecx
0x14000d81d  add     ecx, eax
0x14000d81f  mov     [rbp+r10*4+6C0h+var_608], ecx
0x14000d827  lea     rax, [rbp+6C0h+var_600]
0x14000d82e  mov     ecx, [r14+r13+10h]
0x14000d833  lea     rax, [rax+r10*4]
0x14000d837  dec     ecx
0x14000d839  mov     [rbp+r10*4+6C0h+var_60C], edx
0x14000d841  add     ecx, edx
0x14000d843  test    byte ptr [r14+r13], 1
0x14000d848  mov     [rbp+r10*4+6C0h+var_604], ecx
0x14000d850  jz      short loc_14000D855
0x14000d852  or      dword ptr [rax], 1
0x14000d855  test    byte ptr [r14+r13], 2
0x14000d85a  jz      short loc_14000D85F
0x14000d85c  or      dword ptr [rax], 2
0x14000d85f  mov     eax, [r14+r13+14h]
0x14000d864  mov     edx, 4
0x14000d869  movups  xmm0, xmmword ptr [r14+r13+28h]
0x14000d86f  mov     dword ptr [rbp+r10*4+6C0h+var_4D0], eax
0x14000d877  mov     eax, [r14+r13+18h]
0x14000d87c  mov     dword ptr [rbp+r10*4+6C0h+var_4D0+4], eax
0x14000d884  imul    rcx, r8, 21Ch
0x14000d88b  movdqu  xmmword ptr [rcx+r9], xmm0
0x14000d891  mov     eax, [r14+r13+38h]
0x14000d896  mov     [rcx+r9+10h], eax
0x14000d89b  mov     eax, [r14+r13+3Ch]
0x14000d8a0  mov     [rcx+r9+14h], eax
0x14000d8a5  mov     eax, [r14+r13+40h]
0x14000d8aa  mov     [rcx+r9+218h], eax
0x14000d8b2  lea     rax, [rcx+18h]
0x14000d8b6  add     rax, r9
0x14000d8b9  lea     rcx, [r13+44h]
0x14000d8bd  add     rcx, r14
0x14000d8c0  movups  xmm0, xmmword ptr [rcx]
0x14000d8c3  lea     rcx, [rcx+80h]
0x14000d8ca  movups  xmmword ptr [rax], xmm0
0x14000d8cd  lea     rax, [rax+80h]
0x14000d8d4  movups  xmm1, xmmword ptr [rcx-70h]
0x14000d8d8  movups  xmmword ptr [rax-70h], xmm1
0x14000d8dc  movups  xmm0, xmmword ptr [rcx-60h]
0x14000d8e0  movups  xmmword ptr [rax-60h], xmm0
0x14000d8e4  movups  xmm1, xmmword ptr [rcx-50h]
0x14000d8e8  movups  xmmword ptr [rax-50h], xmm1
0x14000d8ec  movups  xmm0, xmmword ptr [rcx-40h]
0x14000d8f0  movups  xmmword ptr [rax-40h], xmm0
0x14000d8f4  movups  xmm1, xmmword ptr [rcx-30h]
0x14000d8f8  movups  xmmword ptr [rax-30h], xmm1
0x14000d8fc  movups  xmm0, xmmword ptr [rcx-20h]
0x14000d900  movups  xmmword ptr [rax-20h], xmm0
0x14000d904  movups  xmm1, xmmword ptr [rcx-10h]
0x14000d908  movups  xmmword ptr [rax-10h], xmm1
0x14000d90c  sub     rdx, 1
0x14000d910  jnz     short loc_14000D8C0
0x14000d912  mov     r12d, [r14+r13+14h]
0x14000d917  test    r12d, r12d
0x14000d91a  jnz     loc_14000DA1E
0x14000d920  cmp     [r14+r13+18h], r12d
0x14000d925  jz      loc_14000DA41
0x14000d92b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d932  cmp     rcx, rdi
0x14000d935  jz      short loc_14000D983
0x14000d937  test    [rcx+1Ch], r15d
0x14000d93b  jz      short loc_14000D983
0x14000d93d  cmp     [rcx+19h], r11b
0x14000d941  jb      short loc_14000D983
0x14000d943  mov     ebx, [r14+r13+18h]
0x14000d948  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d94d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d954  mov     edx, 51h ; 'Q'
0x14000d959  mov     dword ptr [rsp+7C0h+var_798], ebx
0x14000d95d  mov     r9d, eax
0x14000d960  mov     r8, rsi
0x14000d963  mov     dword ptr [rsp+7C0h+lParam], r12d
0x14000d968  mov     rcx, [rcx+10h]
0x14000d96c  call    WPP_SF_DdD
0x14000d971  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d978  mov     r11d, 3
0x14000d97e  mov     r10, [rsp+7C0h+var_758]
0x14000d983  mov     [rbp+r10*4+6C0h+var_4D0], 0
0x14000d98f  mov     ebx, [r14+r13+1Ch]
0x14000d994  test    ebx, ebx
0x14000d996  jz      short loc_14000D9F0
0x14000d998  cmp     ebx, 5Ah ; 'Z'
0x14000d99b  jz      short loc_14000D9F0
0x14000d99d  cmp     ebx, 0B4h
0x14000d9a3  jz      short loc_14000D9F0
0x14000d9a5  cmp     ebx, 10Eh
0x14000d9ab  jz      short loc_14000D9F0
0x14000d9ad  cmp     rcx, rdi
0x14000d9b0  jz      short loc_14000D9EE
0x14000d9b2  test    [rcx+1Ch], r15d
0x14000d9b6  jz      short loc_14000D9EE
0x14000d9b8  cmp     [rcx+19h], r11b
0x14000d9bc  jb      short loc_14000D9EE
0x14000d9be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000d9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9ca  mov     edx, 52h ; 'R'
0x14000d9cf  mov     r9d, eax
0x14000d9d2  mov     dword ptr [rsp+7C0h+lParam], ebx
0x14000d9d6  mov     r8, rsi
0x14000d9d9  mov     rcx, [rcx+10h]
0x14000d9dd  call    WPP_SF_Dd
0x14000d9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d9e9  mov     r10, [rsp+7C0h+var_758]
0x14000d9ee  xor     ebx, ebx
0x14000d9f0  mov     [rbp+r10*4+6C0h+var_4C8], ebx
0x14000d9f8  xor     edx, edx
0x14000d9fa  mov     ebx, [r14+r13+20h]
0x14000d9ff  mov     r8d, [r14+r13+24h]
0x14000da04  lea     r11d, [rdx+3]
0x14000da08  lea     r9d, [rbx-64h]
0x14000da0c  cmp     r8d, [rbp+rdx*4+6C0h+var_738]
0x14000da11  jz      short loc_14000DA4D
0x14000da13  inc     edx
0x14000da15  cmp     edx, r11d
0x14000da18  jb      short loc_14000DA0C
0x14000da1a  xor     eax, eax
0x14000da1c  jmp     short loc_14000DA52
0x14000da1e  lea     eax, [r12-0Ah]
  ... truncated ...
```
