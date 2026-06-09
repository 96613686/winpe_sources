# CDimInterfaceTable::SetInfoEx(void * const,_MPRI_INTERFACE_INFO_EX *)

- ea: `0x1800042a8`
- end: `0x18000512b`
- name: `?SetInfoEx@CDimInterfaceTable@@QEAAKQEAXPEAU_MPRI_INTERFACE_INFO_EX@@@Z`
- size: `3715`
- prototype: `unsigned int __fastcall(CDimInterfaceTable *__hidden this, void *const, struct _MPRI_INTERFACE_INFO_EX *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e8a0`

## callees

- `0x180002690`
- `0x180002c78`
- `0x180002d80`
- `0x180002ddc`
- `0x180003f40`
- `0x180003f58`
- `0x1800042a8`
- `0x180005340`
- `0x1800055f0`
- `0x180005670`
- `0x1800056c4`
- `0x18000b534`
- `0x18000d854`
- `0x18000def0`
- `0x18000df70`
- `0x180010e38`
- `0x180012be0`
- `0x18001e4d4`
- `0x18001e788`
- `0x18002223c`
- `0x1800244d0`
- `0x180025c24`
- `0x18002737c`
- `0x180035118`
- `0x180037d0c`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!malloc` at `0x18000453f`
- `msvcrt!malloc` at `0x18000453f`
- `msvcrt!free` at `0x18000503a`
- `msvcrt!free` at `0x18000503a`
- `MPRDDM!TimerQInsert` at `0x180005028`
- `MPRDDM!TimerQInsert` at `0x180005028`
- `MPRDDM!ReConnectPersistentInterface` at `0x180004ff8`
- `MPRDDM!ReConnectPersistentInterface` at `0x180005019`
- `MPRDDM!TimerQRemove` at `0x180005002`
- `MPRDDM!TimerQRemove` at `0x180005002`
- `MPRDDM!DDMAdminUpdateQoSPolicies` at `0x1800048b5`
- `MPRDDM!DDMAdminUpdateQoSPolicies` at `0x1800048b5`
- `MPRDDM!IfObjectUpdatePbkInfo` at `0x1800045e3`
- `MPRDDM!IfObjectUpdatePbkInfo` at `0x1800045e3`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x1800045d6`
- `MPRDDM!IfObjectLoadPhonebookInfo` at `0x1800045d6`

## string_xrefs

- `0x180004d3a`: `PlumbRDIkev2Policy failed to remove ikev2 policy. Error:%d`
- `0x180004c5a`: `Failed to delete PSK specific IKEv2 policies. Error:%d`
- `0x180004977`: `Failed to update QoS Policies with DDM. Error:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDimInterfaceTable::SetInfoEx(
        CDimInterfaceTable *this,
        unsigned __int64 a2,
        struct _MPRI_INTERFACE_INFO_EX *a3)
{
  CDimInterfaceTable *v5; // r13
  int v6; // edi
  char v7; // r12
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int *v10; // rbx
  unsigned int v11; // edi
  void *v12; // rax
  int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int updated; // esi
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 *v19; // rdx
  __int128 *v20; // r9
  struct IDimSRWLock *v21; // rcx
  struct IDimSRWLock *v22; // r9
  unsigned int *v23; // rcx
  unsigned int i; // edx
  unsigned int j; // r8d
  int v26; // eax
  int v27; // eax
  char v28; // al
  __int64 (*v29)(void); // rax
  struct IDimSRWLock *v30; // rdi
  __int64 v31; // rbx
  int v32; // eax
  struct IDimSRWLock *v33; // rdi
  __int64 v34; // rbx
  int v35; // eax
  __int64 v36; // rdx
  char v37; // bl
  struct IDimSRWLock *v38; // rdi
  __int64 v39; // rbx
  int v40; // eax
  __int64 v41; // rax
  __int128 *v42; // r9
  __int64 v43; // rax
  __int128 *v44; // r9
  __int64 v45; // rax
  __int128 *v46; // r9
  __int64 v47; // rax
  __int128 *v48; // r9
  bool v49; // zf
  __int64 v50; // rax
  __int64 v51; // rax
  struct IDimSRWLock *v53; // [rsp+30h] [rbp-D0h] BYREF
  std::tr1::_Ref_count_base *v54; // [rsp+38h] [rbp-C8h]
  char v55; // [rsp+40h] [rbp-C0h]
  char v56; // [rsp+41h] [rbp-BFh]
  int v57; // [rsp+44h] [rbp-BCh]
  BOOL v58; // [rsp+48h] [rbp-B8h]
  int v59; // [rsp+4Ch] [rbp-B4h]
  int v60; // [rsp+50h] [rbp-B0h]
  int v61; // [rsp+54h] [rbp-ACh]
  CDimFullRouterInterface *v62; // [rsp+58h] [rbp-A8h] BYREF
  std::tr1::_Ref_count_base *v63; // [rsp+60h] [rbp-A0h]
  _BYTE v64[8]; // [rsp+68h] [rbp-98h] BYREF
  int v65; // [rsp+70h] [rbp-90h] BYREF
  __int128 v66; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v67; // [rsp+84h] [rbp-7Ch]
  int v68; // [rsp+2ACh] [rbp+1ACh]
  __int128 v69; // [rsp+2B0h] [rbp+1B0h]
  int v70; // [rsp+2C0h] [rbp+1C0h]
  int v71; // [rsp+2C4h] [rbp+1C4h]
  int v72; // [rsp+2C8h] [rbp+1C8h]
  int v73; // [rsp+2CCh] [rbp+1CCh]
  int v74; // [rsp+2D0h] [rbp+1D0h]
  int v75; // [rsp+2D4h] [rbp+1D4h]
  int v76; // [rsp+2D8h] [rbp+1D8h]
  int v77; // [rsp+2DCh] [rbp+1DCh]
  int v78; // [rsp+2E0h] [rbp+1E0h]
  int v79; // [rsp+2E4h] [rbp+1E4h]
  int v80; // [rsp+2E8h] [rbp+1E8h]
  int v81; // [rsp+2ECh] [rbp+1ECh]
  int v82; // [rsp+2F0h] [rbp+1F0h]
  int v83; // [rsp+2F4h] [rbp+1F4h]
  unsigned int v84; // [rsp+2F8h] [rbp+1F8h]
  void *Block; // [rsp+300h] [rbp+200h]
  int v86; // [rsp+308h] [rbp+208h]
  int v87; // [rsp+30Ch] [rbp+20Ch]
  __int128 v88; // [rsp+310h] [rbp+210h]
  __int64 v89; // [rsp+320h] [rbp+220h]
  __int64 v90; // [rsp+328h] [rbp+228h]
  int v91; // [rsp+330h] [rbp+230h]
  __int128 v92; // [rsp+340h] [rbp+240h] BYREF
  GUID ActivityId; // [rsp+350h] [rbp+250h] BYREF
  int v94; // [rsp+360h] [rbp+260h] BYREF
  __int128 v95; // [rsp+364h] [rbp+264h]
  __int128 v96; // [rsp+374h] [rbp+274h]
  int v97; // [rsp+384h] [rbp+284h]
  int v98; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v99[2044]; // [rsp+394h] [rbp+294h] BYREF

  v5 = g_pCDimInterfaceTable;
  ActivityId = 0;
  v92 = 0;
  v98 = 0;
  memset_0(v99, 0, sizeof(v99));
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v6 = SetRasServerActivityId(&ActivityId);
  if ( !*((_BYTE *)v5 + 117) )
    UpdateGlobalPhoneBookContext();
  if ( !a3 || *(_BYTE *)a3 != 1 )
  {
    updated = 87;
    goto LABEL_161;
  }
  CDimInterfaceTable::AcquireExclusive(v5);
  CDimInterfaceTable::GetCDimInterface((__int64)v5, &v53, a2);
  if ( !v53 )
  {
    updated = 6;
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceError,
        L"CDimInterfaceTable::SetInfoEx Interface not found");
    goto LABEL_157;
  }
  v60 = SetActivityId((LPGUID)v53 + 194);
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v64, v53);
  v7 = 0;
  v65 = 0;
  memset_0(&v66, 0, 0x2C4u);
  v57 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53);
  v61 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53);
  (*(void (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53);
  v10 = (unsigned int *)((char *)a3 + 572);
  v65 = *((_DWORD *)a3 + 143);
  v66 = *((_OWORD *)a3 + 36);
  v67 = *((_QWORD *)a3 + 74);
  v68 = *((_DWORD *)a3 + 150);
  v69 = *((_OWORD *)a3 + 70);
  v70 = *((_DWORD *)a3 + 284);
  v71 = *((_DWORD *)a3 + 290);
  v72 = *((_DWORD *)a3 + 291);
  v73 = *((_DWORD *)a3 + 292);
  v74 = *((_DWORD *)a3 + 293);
  v75 = *((_DWORD *)a3 + 294);
  v76 = *((_DWORD *)a3 + 295);
  v77 = *((_DWORD *)a3 + 296);
  v78 = *((_DWORD *)a3 + 297);
  v79 = *((_DWORD *)a3 + 298);
  v80 = *((_DWORD *)a3 + 299);
  v81 = *((_DWORD *)a3 + 300);
  v82 = *((_DWORD *)a3 + 301);
  v83 = *((_DWORD *)a3 + 302);
  v11 = *((_DWORD *)a3 + 310);
  v84 = v11;
  v91 = *((_DWORD *)a3 + 319);
  v88 = *(_OWORD *)((char *)a3 + 1256);
  if ( *((_QWORD *)a3 + 156) )
  {
    v12 = malloc(8LL * v11);
    Block = v12;
    v9 = 0;
    if ( v11 )
    {
      while ( 1 )
      {
        *((_QWORD *)v12 + v9) = *(_QWORD *)(*((_QWORD *)a3 + 156) + 8 * v9);
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= v84 )
          break;
        v12 = Block;
      }
    }
  }
  v86 = *((_DWORD *)a3 + 303);
  v87 = *((_DWORD *)a3 + 304);
  v89 = *((_QWORD *)a3 + 153);
  v90 = *((_QWORD *)a3 + 154);
  CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(v5, &v53, v8, v9);
  CDimInterfaceTable::RemoveInterfaceFromHostNameMap(v5, &v53);
  v13 = 0;
  if ( *((_BYTE *)v5 + 117) )
    IfObjectUpdatePbkInfo(v53, &v65);
  else
    IfObjectLoadPhonebookInfo(v53, 0);
  CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(v5, &v53);
  CDimInterfaceTable::InsertInterfaceInHostNameMap(v5, &v53);
  if ( *((_BYTE *)v5 + 116) )
  {
    v14 = *((_QWORD *)v53 + 388) - *(_QWORD *)((char *)a3 + 556);
    if ( !v14 )
      v14 = *((_QWORD *)v53 + 389) - *(_QWORD *)((char *)a3 + 564);
    if ( v14 )
      goto LABEL_143;
  }
  if ( *v10 && (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) != 2 )
    goto LABEL_143;
  v15 = *(_QWORD *)((char *)a3 + 556) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v15 )
    v15 = *(_QWORD *)((char *)a3 + 564) - *(_QWORD *)GUID_NULL.Data4;
  if ( v15
    && (!*((_BYTE *)v5 + 116) || (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) != 2) )
  {
LABEL_143:
    updated = 87;
    goto LABEL_144;
  }
  updated = 0;
  if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) == 3
    || (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) == 6
    || (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) == 4 )
  {
    if ( *((_DWORD *)a3 + 134) )
      goto LABEL_144;
    goto LABEL_143;
  }
  if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 72LL))(v53) != 2 )
    goto LABEL_144;
  v17 = ValidateQoSPolicies((char *)a3 + 572);
  updated = v17;
  if ( v17 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_144;
    LOWORD(v98) = 0;
    LOWORD(v94) = 0;
    FormatRRASErrorString(&v98, L"Specified QoS Policies are not valid Error:%d", v17);
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_144;
    v18 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
    v19 = RasDimParamTraceError;
LABEL_32:
    v20 = &v92;
    if ( v53 != (struct IDimSRWLock *)-3104LL )
      LODWORD(v20) = (_DWORD)v53 + 3104;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (_DWORD)v19,
      (unsigned int)&v98,
      (_DWORD)v20,
      v18,
      (__int64)&v94);
    goto LABEL_144;
  }
  if ( *((_BYTE *)v5 + 116) )
    StringCchCopyW((STRSAFE_LPWSTR)v53 + 498, 0x101u, (STRSAFE_LPCWSTR)a3 + 302);
  if ( *((_DWORD *)a3 + 150) )
    *((_DWORD *)v53 + 506) |= 1u;
  else
    *((_DWORD *)v53 + 506) &= ~1u;
  v21 = v53;
  *(_OWORD *)((char *)v53 + 2028) = *((_OWORD *)a3 + 70);
  *((_DWORD *)v21 + 511) = *((_DWORD *)a3 + 284);
  if ( a3 == (struct _MPRI_INTERFACE_INFO_EX *)-572LL )
    goto LABEL_54;
  v22 = v53;
  v23 = (unsigned int *)((char *)v53 + 960);
  if ( v53 != (struct IDimSRWLock *)-960LL )
  {
    if ( *v10 == *v23 )
    {
      for ( i = 0; i < *v10; ++i )
      {
        for ( j = 0; j < *v23; ++j )
        {
          if ( v10[3 * i + 2] == v23[3 * j + 2] && v10[3 * i + 1] != v23[3 * j + 1] )
            goto LABEL_51;
        }
        v13 = 0;
      }
      goto LABEL_55;
    }
LABEL_51:
    CopyValidQoSPoliciesFromUserBuffer(v23, (char *)a3 + 572);
    if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 40LL))(v53) != 2 )
      goto LABEL_54;
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      updated = DDMAdminUpdateQoSPolicies((char *)v53 + 960);
      if ( !updated )
      {
LABEL_54:
        v22 = v53;
        v13 = 0;
        goto LABEL_55;
      }
    }
    else
    {
      updated = 903;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_144;
    LOWORD(v98) = 0;
    LOWORD(v94) = 0;
    FormatRRASErrorString(&v98, L"Failed to update QoS Policies with DDM. Error:%d", updated);
    if ( (Microsoft_Windows_RRASEnableBits & 8) == 0 )
      goto LABEL_144;
    v18 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
    v19 = RasDimParamTraceInfo;
    goto LABEL_32;
  }
LABEL_55:
  v56 = 0;
  LOBYTE(v10) = 0;
  v58 = (int)v10;
  v55 = 0;
  LOBYTE(v59) = 0;
  v57 &= 4u;
  if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v22 + 120LL))(v22) & 0x10000000) == 0 )
    v13 = IsCustomIkev2PolicyConfiguredForRoutingDomain((struct _GUID *)v53 + 194);
  v26 = v57;
  if ( !*((_DWORD *)a3 + 134) && v57 )
  {
    if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53) & 0x10000000) != 0 )
    {
      v55 = 1;
    }
    else
    {
      v27 = (unsigned __int8)v59;
      if ( v13 )
        v27 = 1;
      v59 = v27;
    }
    v26 = v57;
  }
  if ( *((_DWORD *)a3 + 134) )
  {
    if ( !v26 )
    {
      v7 = 1;
      if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53) & 0x10000000) != 0 )
      {
        if ( (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v5, &v53, 14) )
        {
          updated = 870;
          goto LABEL_144;
        }
        v56 = 1;
      }
      else
      {
        LOBYTE(v10) = v13 != 0;
        v58 = v13 != 0;
      }
    }
    if ( *((_DWORD *)a3 + 134)
      && !v57
      && (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 456LL))(v53) == 9
      && (unsigned __int8)CDimInterfaceTable::DoesInterfaceExistWithSameRemoteEndPoints(v5, &v53, 44) )
    {
      updated = 872;
      goto LABEL_144;
    }
  }
  if ( (v61 & 0x10000000) == 0
    || ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53) & 0x10000000) != 0 )
  {
    if ( ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53) & 4) != 0
      && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 120LL))(v53) & 0x10000000) != 0 )
    {
      v56 = 1;
    }
    else
    {
      v28 = (char)v10;
      if ( v13 )
        v28 = 1;
      LOBYTE(v58) = v28;
    }
  }
  else
  {
    v55 = 1;
    if ( v13 && ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53) & 4) != 0 )
      LOBYTE(v58) = 1;
  }
  v29 = *(__int64 (**)(void))(*(_QWORD *)v53 + 104LL);
  if ( !*((_DWORD *)a3 + 134) )
  {
    v37 = 0;
    if ( (v29() & 4) != 0 )
    {
      v38 = v53;
      v39 = *(_QWORD *)v53;
      v40 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53);
      (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v39 + 112))(v38, v40 & 0xFFFFFFFB);
      v37 = 1;
    }
    if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 40LL))(v53) || !v37 )
      goto LABEL_100;
    goto LABEL_99;
  }
  if ( (v29() & 4) == 0 )
  {
    v30 = v53;
    v31 = *(_QWORD *)v53;
    v32 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53);
    (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v31 + 112))(v30, v32 | 4u);
    v33 = v53;
    v34 = *(_QWORD *)v53;
    v35 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53);
    (*(void (__fastcall **)(struct IDimSRWLock *, _QWORD))(v34 + 112))(v33, v35 & 0xFFFFBFFF);
LABEL_99:
    LOBYTE(v36) = *((_DWORD *)a3 + 134) != 0;
    CDimInterface::NotifyOfReachabilityChange(v53, v36, 2);
  }
LABEL_100:
  if ( v55 )
  {
    std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v62, (__int64 *)&v53);
    updated = CDimFullRouterInterface::PlumbIkev2PskPolicy(v62, 1);
    if ( updated )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        FormatRRASErrorString(&v98, L"Failed to delete PSK specific IKEv2 policies. Error:%d", updated);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v41 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
          v42 = &v92;
          if ( v53 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v42) = (_DWORD)v53 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v98,
            (_DWORD)v42,
            v41,
            (__int64)&v94);
        }
      }
      updated = 0;
    }
    if ( v63 )
      std::tr1::_Ref_count_base::_Decref(v63);
  }
  else if ( (_BYTE)v59 )
  {
    if ( CDimInterface::IsDimFullRouterInterface(v53) )
    {
      updated = CDimInterfaceTable::PlumbRDIkev2Policy(v5);
      if ( updated )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v98) = 0;
          LOWORD(v94) = 0;
          FormatRRASErrorString(&v98, L"PlumbRDIkev2Policy failed to remove ikev2 policy. Error:%d", updated);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v43 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
            v44 = &v92;
            if ( v53 != (struct IDimSRWLock *)-3104LL )
              LODWORD(v44) = (_DWORD)v53 + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v98,
              (_DWORD)v44,
              v43,
              (__int64)&v94);
          }
        }
        updated = 0;
      }
    }
  }
  if ( v56 )
  {
    std::tr1::static_pointer_cast<CDimFullRouterInterface,CDimInterface>(&v62, (__int64 *)&v53);
    updated = CDimFullRouterInterface::PlumbIkev2PskPolicy(v62, 0);
    if ( updated )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        FormatRRASErrorString(&v98, L"Failed to plumb PSK specific IKEv2 policies. Error:%d", updated);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          v45 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
          v46 = &v92;
          if ( v53 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v46) = (_DWORD)v53 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminError,
            (unsigned int)&v98,
            (_DWORD)v46,
            v45,
            (__int64)&v94);
        }
      }
      updated = 0;
    }
    if ( v63 )
      std::tr1::_Ref_count_base::_Decref(v63);
  }
  else if ( v58 )
  {
    CDimInterfaceTable::PlumbRDIkev2Policy(v5);
    updated = CDimInterfaceTable::PlumbRDIkev2Policy(v5);
    if ( updated )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v98) = 0;
        LOWORD(v94) = 0;
        FormatRRASErrorString(&v98, L"PlumbRDIkev2Policy failed to add ikev2 policy. Error:%d", updated);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v47 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 280LL))(v53);
          v48 = &v92;
          if ( v53 != (struct IDimSRWLock *)-3104LL )
            LODWORD(v48) = (_DWORD)v53 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v98,
            (_DWORD)v48,
            v47,
            (__int64)&v94);
        }
      }
      if ( !v7 || ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53) & 4) != 0 )
        updated = 0;
      else
        updated = 871;
    }
  }
LABEL_144:
  if ( (*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 456LL))(v53) != 9 )
  {
    if ( !v7 )
      goto LABEL_152;
    v49 = ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53) & 0x8000) == 0;
    goto LABEL_150;
  }
  if ( v7 )
  {
LABEL_151:
    v50 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 16LL))(v53);
    TimerQRemove(v50, ReConnectPersistentInterface);
    v51 = (*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 16LL))(v53);
    TimerQInsert(v51, 1, ReConnectPersistentInterface);
    goto LABEL_152;
  }
  if ( !(*(unsigned int (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 40LL))(v53) )
  {
    v49 = ((*(__int64 (__fastcall **)(struct IDimSRWLock *))(*(_QWORD *)v53 + 104LL))(v53) & 4) == 0;
LABEL_150:
    if ( !v49 )
      goto LABEL_151;
  }
LABEL_152:
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  scoped_lock::~scoped_lock((scoped_lock *)v64);
  v6 = v60;
LABEL_157:
  CDimInterfaceTable::ReleaseExclusive(v5);
  if ( v54 )
    std::tr1::_Ref_count_base::_Decref(v54);
LABEL_161:
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v98) = 0;
    FormatRRASErrorString(&v98, L"CDimInterfaceTable::SetInfoEx: returned %d", updated);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v98);
  }
  if ( v6 )
    ReSetActivityId(&ActivityId);
  return updated;
}

```

## disassembly

```asm
0x1800042a8  mov     [rsp-8+arg_0], rbx
0x1800042ad  mov     [rsp-8+arg_8], rsi
0x1800042b2  push    rbp
0x1800042b3  push    rdi
0x1800042b4  push    r12
0x1800042b6  push    r13
0x1800042b8  push    r14
0x1800042ba  lea     rbp, [rsp-0AA0h]
0x1800042c2  sub     rsp, 0BA0h
0x1800042c9  mov     rax, cs:__security_cookie
0x1800042d0  xor     rax, rsp
0x1800042d3  mov     [rbp+0AC0h+var_30], rax
0x1800042da  mov     r14, r8
0x1800042dd  mov     rbx, rdx
0x1800042e0  mov     r13, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x1800042e7  xorps   xmm0, xmm0
0x1800042ea  movups  xmmword ptr [rbp+0AC0h+ActivityId.Data1], xmm0
0x1800042f1  xorps   xmm1, xmm1
0x1800042f4  movups  [rbp+0AC0h+var_880], xmm1
0x1800042fb  xor     eax, eax
0x1800042fd  mov     [rbp+0AC0h+var_830], eax
0x180004303  xor     edx, edx; Val
0x180004305  mov     r8d, 7FCh; Size
0x18000430b  lea     rcx, [rbp+0AC0h+var_82C]; void *
0x180004312  call    memset_0
0x180004317  xor     eax, eax
0x180004319  mov     [rbp+0AC0h+var_860], eax
0x18000431f  xorps   xmm0, xmm0
0x180004322  movups  [rbp+0AC0h+var_85C], xmm0
0x180004329  movups  [rbp+0AC0h+var_84C], xmm0
0x180004330  mov     [rbp+0AC0h+var_83C], eax
0x180004336  lea     rcx, [rbp+0AC0h+ActivityId]; ActivityId
0x18000433d  call    SetRasServerActivityId
0x180004342  mov     edi, eax
0x180004344  cmp     byte ptr [r13+75h], 0
0x180004349  jnz     short loc_180004350
0x18000434b  call    ?UpdateGlobalPhoneBookContext@@YAXXZ; UpdateGlobalPhoneBookContext(void)
0x180004350  test    r14, r14
0x180004353  jz      loc_18000509E
0x180004359  mov     esi, 1
0x18000435e  cmp     [r14], sil
0x180004361  jnz     loc_18000509E
0x180004367  mov     rcx, r13; this
0x18000436a  call    ?AcquireExclusive@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireExclusive(void)
0x18000436f  mov     r8, rbx
0x180004372  lea     rdx, [rsp+0BC0h+var_B90]
0x180004377  mov     rcx, r13
0x18000437a  call    ?GetCDimInterface@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@QEAX@Z; CDimInterfaceTable::GetCDimInterface(void * const)
0x18000437f  nop
0x180004380  mov     rcx, [rsp+0BC0h+var_B90]
0x180004385  test    rcx, rcx
0x180004388  jz      loc_18000505B
0x18000438e  add     rcx, 0C20h; ActivityId
0x180004395  lea     rdx, [rbp+0AC0h+ActivityId]
0x18000439c  call    SetActivityId
0x1800043a1  mov     [rsp+0BC0h+var_B70], eax
0x1800043a5  mov     rdx, [rsp+0BC0h+var_B90]; struct IDimSRWLock *
0x1800043aa  lea     rcx, [rsp+0BC0h+var_B58]; this
0x1800043af  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x1800043b4  nop
0x1800043b5  xor     r12b, r12b
0x1800043b8  mov     [rsp+0BC0h+var_B50], 0
0x1800043c0  xor     edx, edx; Val
0x1800043c2  mov     r8d, 2C4h; Size
0x1800043c8  lea     rcx, [rsp+0BC0h+var_B4C]; void *
0x1800043cd  call    memset_0
0x1800043d2  mov     rcx, [rsp+0BC0h+var_B90]
0x1800043d7  mov     rax, [rcx]
0x1800043da  mov     rax, [rax+68h]
0x1800043de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e3  mov     [rsp+0BC0h+var_B7C], eax
0x1800043e7  mov     rdx, [rsp+0BC0h+var_B90]
0x1800043ec  mov     rcx, [rdx]
0x1800043ef  mov     rax, [rcx+78h]
0x1800043f3  mov     rcx, rdx
0x1800043f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fb  mov     [rsp+0BC0h+var_B6C], eax
0x1800043ff  mov     rdx, [rsp+0BC0h+var_B90]
0x180004404  mov     rcx, [rdx]
0x180004407  mov     rax, [rcx+78h]
0x18000440b  mov     rcx, rdx
0x18000440e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004413  lea     rbx, [r14+23Ch]
0x18000441a  mov     ecx, [rbx]
0x18000441c  mov     [rsp+0BC0h+var_B50], ecx
0x180004420  movups  xmm0, xmmword ptr [rbx+4]
0x180004424  movups  [rsp+0BC0h+var_B4C], xmm0
0x180004429  movsd   xmm1, qword ptr [rbx+14h]
0x18000442e  movsd   [rbp+0AC0h+var_B3C], xmm1
0x180004433  mov     eax, [r14+258h]
0x18000443a  mov     [rbp+0AC0h+var_914], eax
0x180004440  movups  xmm0, xmmword ptr [r14+460h]
0x180004448  movaps  [rbp+0AC0h+var_910], xmm0
0x18000444f  mov     eax, [r14+470h]
0x180004456  mov     [rbp+0AC0h+var_900], eax
0x18000445c  mov     eax, [r14+488h]
0x180004463  mov     [rbp+0AC0h+var_8FC], eax
0x180004469  mov     eax, [r14+48Ch]
0x180004470  mov     [rbp+0AC0h+var_8F8], eax
0x180004476  mov     eax, [r14+490h]
0x18000447d  mov     [rbp+0AC0h+var_8F4], eax
0x180004483  mov     eax, [r14+494h]
0x18000448a  mov     [rbp+0AC0h+var_8F0], eax
0x180004490  mov     eax, [r14+498h]
0x180004497  mov     [rbp+0AC0h+var_8EC], eax
0x18000449d  mov     eax, [r14+49Ch]
0x1800044a4  mov     [rbp+0AC0h+var_8E8], eax
0x1800044aa  mov     eax, [r14+4A0h]
0x1800044b1  mov     [rbp+0AC0h+var_8E4], eax
0x1800044b7  mov     eax, [r14+4A4h]
0x1800044be  mov     [rbp+0AC0h+var_8E0], eax
0x1800044c4  mov     eax, [r14+4A8h]
0x1800044cb  mov     [rbp+0AC0h+var_8DC], eax
0x1800044d1  mov     eax, [r14+4ACh]
0x1800044d8  mov     [rbp+0AC0h+var_8D8], eax
0x1800044de  mov     eax, [r14+4B0h]
0x1800044e5  mov     [rbp+0AC0h+var_8D4], eax
0x1800044eb  mov     eax, [r14+4B4h]
0x1800044f2  mov     [rbp+0AC0h+var_8D0], eax
0x1800044f8  mov     eax, [r14+4B8h]
0x1800044ff  mov     [rbp+0AC0h+var_8CC], eax
0x180004505  mov     edi, [r14+4D8h]
0x18000450c  mov     [rbp+0AC0h+var_8C8], edi
0x180004512  mov     eax, [r14+4FCh]
0x180004519  mov     [rbp+0AC0h+var_890], eax
0x18000451f  movups  xmm0, xmmword ptr [r14+4E8h]
0x180004527  movdqu  [rbp+0AC0h+var_8B0], xmm0
0x18000452f  cmp     qword ptr [r14+4E0h], 0
0x180004537  jz      short loc_180004577
0x180004539  mov     ecx, edi
0x18000453b  shl     rcx, 3; Size
0x18000453f  call    cs:__imp_malloc
0x180004545  mov     [rbp+0AC0h+Block], rax
0x18000454c  xor     r9d, r9d
0x18000454f  test    edi, edi
0x180004551  jz      short loc_180004577
0x180004553  mov     rcx, [r14+4E0h]
0x18000455a  mov     rdx, [rcx+r9*8]
0x18000455e  mov     [rax+r9*8], rdx
0x180004562  add     r9d, esi
0x180004565  cmp     r9d, [rbp+0AC0h+var_8C8]
0x18000456c  jnb     short loc_180004577
0x18000456e  mov     rax, [rbp+0AC0h+Block]
0x180004575  jmp     short loc_180004553
0x180004577  mov     eax, [r14+4BCh]
0x18000457e  mov     [rbp+0AC0h+var_8B8], eax
0x180004584  mov     eax, [r14+4C0h]
0x18000458b  mov     [rbp+0AC0h+var_8B4], eax
0x180004591  mov     rax, [r14+4C8h]
0x180004598  mov     [rbp+0AC0h+var_8A0], rax
0x18000459f  mov     rax, [r14+4D0h]
0x1800045a6  mov     [rbp+0AC0h+var_898], rax
0x1800045ad  lea     rdx, [rsp+0BC0h+var_B90]
0x1800045b2  mov     rcx, r13
0x1800045b5  call    ?RemoveInterfaceFromRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800045ba  lea     rdx, [rsp+0BC0h+var_B90]
0x1800045bf  mov     rcx, r13
0x1800045c2  call    ?RemoveInterfaceFromHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::RemoveInterfaceFromHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800045c7  xor     edi, edi
0x1800045c9  mov     rcx, [rsp+0BC0h+var_B90]
0x1800045ce  cmp     [r13+75h], dil
0x1800045d2  jnz     short loc_1800045DE
0x1800045d4  xor     edx, edx
0x1800045d6  call    cs:__imp_IfObjectLoadPhonebookInfo
0x1800045dc  jmp     short loc_1800045E9
0x1800045de  lea     rdx, [rsp+0BC0h+var_B50]
0x1800045e3  call    cs:__imp_IfObjectUpdatePbkInfo
0x1800045e9  lea     rdx, [rsp+0BC0h+var_B90]
0x1800045ee  mov     rcx, r13
0x1800045f1  call    ?InsertInterfaceInRouterIpAddressMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInRouterIpAddressMap(std::tr1::shared_ptr<CDimInterface> const &)
0x1800045f6  lea     rdx, [rsp+0BC0h+var_B90]
0x1800045fb  mov     rcx, r13
0x1800045fe  call    ?InsertInterfaceInHostNameMap@CDimInterfaceTable@@AEAAXAEBV?$shared_ptr@VCDimInterface@@@tr1@std@@@Z; CDimInterfaceTable::InsertInterfaceInHostNameMap(std::tr1::shared_ptr<CDimInterface> const &)
0x180004603  cmp     [r13+74h], dil
0x180004607  jz      short loc_180004635
0x180004609  mov     rcx, [rsp+0BC0h+var_B90]
0x18000460e  mov     rax, [rcx+0C20h]
0x180004615  sub     rax, [r14+22Ch]
0x18000461c  jnz     short loc_18000462C
0x18000461e  mov     rax, [rcx+0C28h]
0x180004625  sub     rax, [r14+234h]
0x18000462c  test    rax, rax
0x18000462f  jnz     loc_180004F7D
0x180004635  cmp     [rbx], edi
0x180004637  jz      short loc_180004653
0x180004639  mov     rcx, [rsp+0BC0h+var_B90]
0x18000463e  mov     rax, [rcx]
0x180004641  mov     rax, [rax+48h]
0x180004645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464a  cmp     eax, 2
0x18000464d  jnz     loc_180004F7D
0x180004653  mov     rax, [r14+22Ch]
0x18000465a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180004661  jnz     short loc_180004671
0x180004663  mov     rax, [r14+234h]
0x18000466a  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180004671  test    rax, rax
0x180004674  jz      short loc_18000469A
0x180004676  cmp     [r13+74h], dil
0x18000467a  jz      loc_180004F7D
0x180004680  mov     rcx, [rsp+0BC0h+var_B90]
0x180004685  mov     rax, [rcx]
0x180004688  mov     rax, [rax+48h]
0x18000468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004691  cmp     eax, 2
0x180004694  jnz     loc_180004F7D
0x18000469a  mov     esi, edi
0x18000469c  mov     rcx, [rsp+0BC0h+var_B90]
0x1800046a1  mov     rax, [rcx]
0x1800046a4  mov     rax, [rax+48h]
0x1800046a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ad  cmp     eax, 3
0x1800046b0  jz      loc_180004F74
0x1800046b6  mov     rcx, [rsp+0BC0h+var_B90]
0x1800046bb  mov     rax, [rcx]
0x1800046be  mov     rax, [rax+48h]
0x1800046c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c7  cmp     eax, 6
0x1800046ca  jz      loc_180004F74
0x1800046d0  mov     rcx, [rsp+0BC0h+var_B90]
0x1800046d5  mov     rax, [rcx]
0x1800046d8  mov     rax, [rax+48h]
0x1800046dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e1  cmp     eax, 4
0x1800046e4  jz      loc_180004F74
0x1800046ea  mov     rcx, [rsp+0BC0h+var_B90]
0x1800046ef  mov     rax, [rcx]
0x1800046f2  mov     rax, [rax+48h]
0x1800046f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fb  cmp     eax, 2
0x1800046fe  jnz     loc_180004F82
0x180004704  mov     rcx, rbx
0x180004707  call    ValidateQoSPolicies
0x18000470c  mov     esi, eax
0x18000470e  test    eax, eax
0x180004710  jz      loc_1800047B1
0x180004716  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18000471d  jz      loc_180004F82
0x180004723  xor     ecx, ecx
0x180004725  mov     word ptr [rbp+0AC0h+var_830], cx
0x18000472c  mov     word ptr [rbp+0AC0h+var_860], cx
0x180004733  mov     r8d, eax
0x180004736  lea     rdx, aSpecifiedQosPo; "Specified QoS Policies are not valid Er"...
0x18000473d  lea     rcx, [rbp+0AC0h+var_830]
0x180004744  call    FormatRRASErrorString
0x180004749  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180004750  jz      loc_180004F82
0x180004756  mov     rcx, [rsp+0BC0h+var_B90]
0x18000475b  mov     rax, [rcx]
0x18000475e  mov     rax, [rax+118h]
0x180004765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476a  lea     rdx, RasDimParamTraceError
0x180004771  mov     rcx, [rsp+0BC0h+var_B90]
0x180004776  lea     r9, [rbp+0AC0h+var_880]
0x18000477d  add     rcx, 0C20h
0x180004784  cmovnz  r9, rcx
0x180004788  lea     rcx, [rbp+0AC0h+var_860]
0x18000478f  mov     [rsp+0BC0h+var_B98], rcx
0x180004794  lea     r8, [rbp+0AC0h+var_830]
0x18000479b  mov     [rsp+0BC0h+var_BA0], rax
0x1800047a0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800047a7  call    McTemplateU0zjzz_EventWriteTransfer
0x1800047ac  jmp     loc_180004F82
0x1800047b1  cmp     [r13+74h], dil
0x1800047b5  jz      short loc_1800047D4
0x1800047b7  lea     r8, [r14+25Ch]; pszSrc
0x1800047be  mov     rcx, [rsp+0BC0h+var_B90]
0x1800047c3  add     rcx, 3E4h; pszDest
0x1800047ca  mov     edx, 101h; cchDest
0x1800047cf  call    StringCchCopyW
0x1800047d4  mov     rax, [rsp+0BC0h+var_B90]
0x1800047d9  cmp     [r14+258h], edi
0x1800047e0  jz      short loc_1800047EF
0x1800047e2  mov     ecx, 1
0x1800047e7  or      [rax+7E8h], ecx
0x1800047ed  jmp     short loc_1800047F6
0x1800047ef  and     dword ptr [rax+7E8h], 0FFFFFFFEh
0x1800047f6  mov     rcx, [rsp+0BC0h+var_B90]
0x1800047fb  movups  xmm0, xmmword ptr [r14+460h]
0x180004803  movups  xmmword ptr [rcx+7ECh], xmm0
0x18000480a  mov     eax, [r14+470h]
0x180004811  mov     [rcx+7FCh], eax
0x180004817  test    rbx, rbx
0x18000481a  jz      loc_1800048C5
0x180004820  mov     r9, [rsp+0BC0h+var_B90]
0x180004825  lea     rcx, [r9+3C0h]
0x18000482c  test    rcx, rcx
0x18000482f  jz      loc_1800048CC
0x180004835  mov     r11d, [rbx]
0x180004838  cmp     r11d, [rcx]
0x18000483b  jnz     short loc_18000487E
0x18000483d  mov     edx, edi
0x18000483f  cmp     edx, r11d
0x180004842  jnb     loc_1800048CC
0x180004848  mov     r8d, edi
0x18000484b  mov     eax, edx
0x18000484d  lea     rdi, [rax+rax*2]
0x180004851  cmp     r8d, [rcx]
0x180004854  jnb     short loc_180004878
0x180004856  mov     eax, r8d
  ... truncated ...
```
