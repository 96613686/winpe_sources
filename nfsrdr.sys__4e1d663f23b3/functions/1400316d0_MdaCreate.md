# MdaCreate

- ea: `0x1400316d0`
- end: `0x1400338fb`
- name: `MdaCreate`
- size: `8747`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `28`
- tags: `reparse_path, authz_impersonation`

## callees

- `0x1400022c0`
- `0x140003510`
- `0x140005c90`
- `0x140008140`
- `0x1400081f0`
- `0x140009380`
- `0x1400095b0`
- `0x14000fbc0`
- `0x1400145f0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140017590`
- `0x14001f178`
- `0x140027eec`
- `0x14002a9e0`
- `0x14002fe10`
- `0x1400316d0`
- `0x140033904`
- `0x140033af0`
- `0x140033c50`
- `0x140033c90`
- `0x140033dc0`
- `0x140035384`
- `0x1400374f8`
- `0x14003aba0`
- `0x14003adc0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140031d15`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140031d15`
- `ntoskrnl!IoGetRequestorProcessId` at `0x1400333f9`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140033756`
- `ntoskrnl!IoGetRequestorProcessId` at `0x1400333f9`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140033756`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140031c55`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140031c55`
- `ntoskrnl!KeReleaseMutex` at `0x140032105`
- `ntoskrnl!KeReleaseMutex` at `0x1400325bb`
- `ntoskrnl!KeReleaseMutex` at `0x14003279d`
- `ntoskrnl!KeReleaseMutex` at `0x140032856`
- `ntoskrnl!KeReleaseMutex` at `0x140032cbe`
- `ntoskrnl!KeReleaseMutex` at `0x1400330b0`
- `ntoskrnl!KeReleaseMutex` at `0x140033102`
- `ntoskrnl!KeReleaseMutex` at `0x1400332ef`
- `ntoskrnl!KeReleaseMutex` at `0x140033345`
- `ntoskrnl!KeReleaseMutex` at `0x1400333ae`
- `ntoskrnl!KeReleaseMutex` at `0x14003346f`
- `ntoskrnl!KeReleaseMutex` at `0x140033587`
- `ntoskrnl!KeReleaseMutex` at `0x140033653`
- `ntoskrnl!KeReleaseMutex` at `0x14003373a`
- `ntoskrnl!KeReleaseMutex` at `0x140032105`
- `ntoskrnl!KeReleaseMutex` at `0x1400325bb`
- `ntoskrnl!KeReleaseMutex` at `0x14003279d`
- `ntoskrnl!KeReleaseMutex` at `0x140032856`
- `ntoskrnl!KeReleaseMutex` at `0x140032cbe`
- `ntoskrnl!KeReleaseMutex` at `0x1400330b0`
- `ntoskrnl!KeReleaseMutex` at `0x140033102`
- `ntoskrnl!KeReleaseMutex` at `0x1400332ef`
- `ntoskrnl!KeReleaseMutex` at `0x140033345`
- `ntoskrnl!KeReleaseMutex` at `0x1400333ae`
- `ntoskrnl!KeReleaseMutex` at `0x14003346f`
- `ntoskrnl!KeReleaseMutex` at `0x140033587`
- `ntoskrnl!KeReleaseMutex` at `0x140033653`
- `ntoskrnl!KeReleaseMutex` at `0x14003373a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ece`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032434`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031db5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ece`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032434`
- `ntoskrnl!ExAllocatePool2` at `0x140031bf0`
- `ntoskrnl!ExAllocatePool2` at `0x140031d68`
- `ntoskrnl!ExAllocatePool2` at `0x140032154`
- `ntoskrnl!ExAllocatePool2` at `0x1400322b3`
- `ntoskrnl!ExAllocatePool2` at `0x1400336b3`
- `ntoskrnl!ExAllocatePool2` at `0x140031bf0`
- `ntoskrnl!ExAllocatePool2` at `0x140031d68`
- `ntoskrnl!ExAllocatePool2` at `0x140032154`
- `ntoskrnl!ExAllocatePool2` at `0x1400322b3`
- `ntoskrnl!ExAllocatePool2` at `0x1400336b3`
- `rdbss!RxFinishFcbInitialization` at `0x140031ff5`
- `rdbss!RxFinishFcbInitialization` at `0x140031ff5`
- `rdbss!RxCreateNetFobx` at `0x140031f9e`
- `rdbss!RxCreateNetFobx` at `0x140033666`
- `rdbss!RxCreateNetFobx` at `0x140031f9e`
- `rdbss!RxCreateNetFobx` at `0x140033666`

## string_xrefs

- `0x140032b74`: `NfsSymlinkTargetName`
- `0x140031b86`: `NfsActOnLink`

## pseudocode

```c
__int64 __fastcall MdaCreate(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  __int64 v3; // r14
  __int64 v5; // r13
  int v6; // r12d
  __int64 v7; // rsi
  __int64 v8; // r9
  struct _UNICODE_STRING *v9; // r15
  unsigned __int8 v10; // dl
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 Pool2; // rax
  __int64 *v15; // rsi
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  NTSTATUS appended; // ebx
  int v19; // r9d
  int v20; // eax
  int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rbx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  PWSTR Buffer; // rcx
  PMRX_FOBX v27; // rax
  char v28; // r13
  __int64 *v29; // r12
  char v30; // r14
  BOOLEAN v31; // r15
  __int64 v32; // rcx
  struct _KMUTANT *v33; // rcx
  int v34; // eax
  __int64 v35; // r8
  int v36; // eax
  int v37; // r8d
  __int64 v38; // r15
  _DWORD *v39; // r14
  int v40; // eax
  _DWORD *v41; // rax
  _DWORD *v42; // rbx
  void *v43; // rcx
  USHORT Length; // ax
  PDEVICE_OBJECT v45; // rcx
  __int64 v46; // rdx
  int v47; // ecx
  char v48; // r14
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // r14d
  char v54; // r15
  unsigned int v55; // r12d
  char v56; // r13
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  char v59; // bl
  __int64 *v60; // r15
  int v61; // r14d
  __int64 v62; // rcx
  __int64 v63; // rdx
  int v64; // r12d
  __int64 v65; // r9
  __int64 v66; // rcx
  unsigned int v67; // eax
  int v68; // ecx
  __int64 v69; // rcx
  __int64 v70; // rbx
  unsigned int v71; // r14d
  __int64 v72; // r12
  unsigned int v73; // r13d
  __int64 v74; // rcx
  int v75; // eax
  int v76; // eax
  int v77; // eax
  __int64 v78; // rcx
  struct _KMUTANT *v79; // rcx
  __int64 v80; // rdi
  __int64 v81; // r8
  __int64 v82; // rdx
  int v83; // ecx
  PDEVICE_OBJECT v84; // rcx
  __int64 v85; // rdx
  int v86; // eax
  __int64 v87; // r15
  _DWORD *v88; // r14
  IRP *v89; // rcx
  ULONG RequestorProcessId; // eax
  __int64 v91; // rcx
  int v92; // eax
  __int64 v93; // rcx
  int v94; // r14d
  PMRX_FOBX NetFobx; // rax
  PDEVICE_OBJECT v96; // rcx
  __int64 v97; // rdx
  void *v98; // rcx
  __int64 v99; // rax
  IRP *v100; // rcx
  ULONG v101; // eax
  __int64 v102; // rcx
  int v103; // eax
  __int64 v104; // rcx
  char v106; // [rsp+51h] [rbp-AFh]
  _BYTE v107[9]; // [rsp+53h] [rbp-ADh] BYREF
  char v108; // [rsp+5Ch] [rbp-A4h]
  __int64 v109; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  int v111[2]; // [rsp+78h] [rbp-88h]
  __int64 v112; // [rsp+80h] [rbp-80h]
  int v113; // [rsp+88h] [rbp-78h]
  _DWORD *v114; // [rsp+90h] [rbp-70h]
  int v115; // [rsp+98h] [rbp-68h]
  __int64 v116; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v117; // [rsp+A8h] [rbp-58h]
  __int64 v118; // [rsp+B0h] [rbp-50h]
  __int128 v119; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v120; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING Source; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v122; // [rsp+E8h] [rbp-18h]
  __int64 v123; // [rsp+F0h] [rbp-10h]
  __int64 v124; // [rsp+F8h] [rbp-8h]
  int v125[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v126[8]; // [rsp+110h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v2 = *(_QWORD *)(a1 + 80);
  v3 = *(_QWORD *)(a1 + 56);
  v109 = v1;
  v5 = *(_QWORD *)(v1 + 48);
  v112 = v2;
  v119 = 0;
  v120 = 0;
  memset(v126, 0, sizeof(v126));
  LOBYTE(v6) = 0;
  *(_OWORD *)v125 = 0;
  *(_WORD *)v107 = 0;
  Source = 0;
  Destination = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  *(_QWORD *)v111 = *(_QWORD *)(a1 + 656);
  v114 = *(_DWORD **)(*(_QWORD *)v111 + 40LL);
  if ( !v114 )
    return 3221225662LL;
  v7 = *(_QWORD *)(a1 + 648);
  v122 = *(_QWORD *)(v7 + 40);
  if ( !v122 )
    return 3221225662LL;
  v8 = *(_QWORD *)(a1 + 56);
  v9 = (struct _UNICODE_STRING *)(v8 + 360);
  v118 = v8 + 360;
  if ( v8 == -360 || (v9->Length & 1) != 0 || (*(_BYTE *)(v8 + 362) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    appended = -1073741811;
    goto LABEL_460;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
          *(_QWORD *)(a1 + 640));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
            *(_QWORD *)(a1 + 648));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
              *(_QWORD *)(a1 + 656));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                *(_QWORD *)(a1 + 72));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                      WPP_SF_Z(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                        v9);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          27,
                          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            28,
                            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            29,
                            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v1 = v109;
  }
  v10 = *(_BYTE *)(v7 + 77);
  v123 = 0;
  v124 = 0;
  *(_DWORD *)&v107[5] = 0;
  if ( ((unsigned __int8)(v10 - 1) <= 1u || v10 >= 5u)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  }
  if ( (*(_DWORD *)(v3 + 156) & 1) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  }
  v11 = *(_DWORD *)(a1 + 540);
  v107[2] = 0;
  if ( (v11 & 1) != 0 || (v106 = 0, (*(_DWORD *)(a1 + 528) & 0x10) != 0) )
    v106 = 1;
  v12 = *(_QWORD *)(a1 + 696);
  if ( v12 )
  {
    v13 = *(unsigned int *)(a1 + 712);
    if ( (_DWORD)v13 )
    {
      v116 = 0;
      v117 = 0;
      if ( (v114[8] & 0x200) != 0 )
      {
        v6 = MdaFindEAValue(v12, v13, &v116, "NfsActOnLink") == 0;
        *(_DWORD *)&v107[5] = v6;
      }
    }
  }
  if ( *(_DWORD *)(v3 + 192) )
  {
    v15 = *(__int64 **)(v3 + 136);
    v28 = 1;
    v108 = 0;
    appended = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_180:
    if ( v107[1] )
    {
      if ( !appended )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        appended = -1073741823;
      }
      goto LABEL_347;
    }
    v47 = *(_DWORD *)(a1 + 536);
    v48 = 0;
    LODWORD(v126[0]) = 0;
    LODWORD(v126[1]) = 0;
    LODWORD(v126[2]) = 0;
    LODWORD(v126[3]) = 0;
    LODWORD(v126[5]) = 0;
    HIDWORD(v126[6]) = 0;
    if ( !v47 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      if ( v28 == 1 )
      {
        if ( appended < 0 )
          goto LABEL_208;
        v55 = 0;
        HacAcquireLock(v15[1]);
        if ( !*(_QWORD *)(v15[1] + 152) || v106 )
        {
          v56 = 0;
        }
        else
        {
          v126[4] = 0;
          LODWORD(v126[3]) = 1;
          v56 = 1;
        }
        goto LABEL_215;
      }
      goto LABEL_270;
    }
    v49 = v47 - 1;
    if ( v49 )
    {
      v50 = v49 - 1;
      if ( !v50 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        if ( v28 == 1 )
        {
          if ( appended >= 0 )
          {
            appended = -1073741771;
            goto LABEL_347;
          }
          MdaNtAttributesToNfsAttributes(*(_QWORD *)v111, a1, v126);
          v54 = v106;
          if ( !v106 )
          {
            LODWORD(v126[3]) = 1;
            v126[4] = 0;
          }
          LODWORD(v126[5]) = 2;
          MdaCurrentTimeToNfsTime((char *)&v126[5] + 4);
          v126[7] = *(_QWORD *)((char *)&v126[5] + 4);
          HIDWORD(v126[6]) = 2;
        }
        else
        {
          v54 = v106;
        }
        goto LABEL_271;
      }
      v51 = v50 - 1;
      if ( v51 )
      {
        v52 = v51 - 1;
        if ( v52 )
        {
          if ( v52 != 1 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            appended = -1073741637;
            goto LABEL_347;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          if ( v28 == 1 )
          {
            if ( appended < 0 )
            {
LABEL_208:
              v53 = v111[0];
              *(_DWORD *)&v107[5] = 2;
              MdaNtAttributesToNfsAttributes(*(_QWORD *)v111, a1, v126);
              v54 = v106;
              if ( !v106 )
              {
                LODWORD(v126[3]) = 1;
                v126[4] = 0;
              }
              LODWORD(v126[5]) = 2;
              MdaCurrentTimeToNfsTime((char *)&v126[5] + 4);
              v126[7] = *(_QWORD *)((char *)&v126[5] + 4);
              HIDWORD(v126[6]) = 2;
              v113 = 0;
              goto LABEL_273;
            }
            v55 = 3;
            HacAcquireLock(v15[1]);
            if ( !*(_QWORD *)(v15[1] + 152) || v106 )
            {
              v56 = 0;
            }
            else
            {
              v126[4] = 0;
              LODWORD(v126[3]) = 1;
              v56 = 1;
            }
LABEL_215:
            KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
            goto LABEL_368;
          }
          goto LABEL_270;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        if ( appended >= 0 )
        {
          HacAcquireLock(v15[1]);
          if ( !*(_QWORD *)(v15[1] + 152) || v106 )
          {
            v56 = 0;
          }
          else
          {
            v126[4] = 0;
            LODWORD(v126[3]) = 1;
            v56 = 1;
          }
          KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
          v55 = 3;
          goto LABEL_368;
        }
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        {
LABEL_224:
          appended = -1073741809;
          goto LABEL_347;
        }
        v46 = 58;
LABEL_223:
        WPP_SF_d(v45->AttachedDevice, v46, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        goto LABEL_224;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      if ( v28 != 1 )
      {
LABEL_270:
        v54 = v106;
LABEL_271:
        v53 = v111[0];
        *(_DWORD *)&v107[5] = 2;
        v113 = 0;
        if ( !v28 )
        {
          MdaNtAttributesToNfsAttributes(*(_QWORD *)v111, a1, v126);
          v113 = HIDWORD(v126[0]);
        }
LABEL_273:
        v59 = (unsigned __int8)~*(_BYTE *)(v109 + 2) >> 7;
        *(_QWORD *)v125 = MEMORY[0xFFFFF78000000014];
        if ( v54 )
        {
          v60 = v15 + 1;
          appended = NfsCreateOrMkdir(v53, a1, 2, *v15, v118, (__int64)v126, 0, v59, 0, (__int64)(v15 + 1));
          v115 = 2;
          v61 = 2;
        }
        else
        {
          v116 = 0;
          v117 = 0;
          if ( (_BYTE)v6
            || (v62 = *(_QWORD *)(a1 + 696)) == 0
            || (v63 = *(unsigned int *)(a1 + 712), !(_DWORD)v63)
            || (unsigned int)MdaFindEAValue(v62, v63, &v116, "NfsSymlinkTargetName") )
          {
            v64 = 1;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, &v116);
            }
            v64 = 5;
          }
          v65 = *v15;
          v60 = v15 + 1;
          v115 = v64;
          appended = NfsCreateOrMkdir(
                       v53,
                       a1,
                       v64,
                       v65,
                       v118,
                       (__int64)v126,
                       0,
                       v59,
                       (__int64)&v116,
                       (__int64)(v15 + 1));
          v61 = 1;
        }
        v116 = MEMORY[0xFFFFF78000000014];
        LODWORD(v126[0]) &= -(v28 != 0);
        if ( appended < 0 )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v58 = 66;
            goto LABEL_448;
          }
          goto LABEL_347;
        }
        v66 = *v60;
        v107[2] = 1;
        HacAcquireLock(v66);
        MdaNotifyFullReportChange(*(PFAST_MUTEX *)(v122 + 104), 0, 0, v61, 1, 0);
        KeReleaseMutex(*(PRKMUTEX *)(*v60 + 40), 0);
        if ( !v28 )
        {
          v67 = *(_DWORD *)(a1 + 536);
          if ( v67 > 5 )
          {
            v55 = *(_DWORD *)&v107[5];
            v56 = 0;
            goto LABEL_366;
          }
          v68 = 45;
          if ( _bittest(&v68, v67) )
          {
            v69 = *v60;
            v70 = *(unsigned int *)(*v60 + 192);
            v71 = *(_DWORD *)(*v60 + 196);
            v72 = *(unsigned int *)(*v60 + 200);
            v73 = *(_DWORD *)(*v60 + 204);
            LODWORD(v118) = *(_DWORD *)(*v60 + 208);
            LODWORD(v109) = *(_DWORD *)(v69 + 212);
            HacAcquireLock(v69);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          71,
                          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                          WPP_SF_q(
                            WPP_GLOBAL_Control->AttachedDevice,
                            72,
                            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                            *(_QWORD *)(*v60 + 152));
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                            WPP_SF_q(
                              WPP_GLOBAL_Control->AttachedDevice,
                              73,
                              WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                              v71 / 0x64 + 10000000 * (v70 + 0x2B6109100LL));
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                74,
                                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                                v73 / 0x64 + 10000000 * (v72 + 0x2B6109100LL));
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                WPP_SF_q(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  75,
                                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                                  (unsigned int)v109 / 0x64 + 10000000 * ((unsigned int)v118 + 0x2B6109100LL));
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
                                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                  WPP_SF_q(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    76,
                                    WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                                    *(_QWORD *)v125);
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                {
                                  WPP_SF_q(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    77,
                                    WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                                    v116);
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            v74 = *v60;
            if ( *(_DWORD *)(*v60 + 128) == v115
              && (*(_DWORD *)(v74 + 132) & 0x1FFF) == v113
              && !*(_QWORD *)(v74 + 152)
              && *(_DWORD *)(v74 + 140) == v114[9]
              && *(_DWORD *)(v74 + 144) == v114[10]
              && (v75 = *(_DWORD *)(v74 + 192), v75 == *(_DWORD *)(v74 + 200))
              && v75 == *(_DWORD *)(v74 + 208)
              && (v76 = *(_DWORD *)(v74 + 196), v76 == *(_DWORD *)(v74 + 204))
              && v76 == *(_DWORD *)(v74 + 212) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
              v77 = *(_DWORD *)(a1 + 536);
              switch ( v77 )
              {
                case 2:
                  v78 = *v60;
                  appended = -1073741771;
LABEL_345:
                  v79 = *(struct _KMUTANT **)(v78 + 40);
                  goto LABEL_346;
                case 3:
                  v55 = 1;
                  goto LABEL_338;
                case 0:
                  v55 = 0;
                  if ( !*(_QWORD *)(*v60 + 152) || v106 )
                  {
                    v56 = 0;
                  }
                  else
                  {
                    v126[4] = 0;
                    LODWORD(v126[3]) = 1;
                    v56 = 1;
                  }
                  goto LABEL_339;
                case 5:
                  v55 = 3;
                  if ( *(_QWORD *)(*v60 + 152) && !v106 )
                  {
                    v126[4] = 0;
                    LODWORD(v126[3]) = 1;
                    v56 = 1;
                    goto LABEL_339;
                  }
LABEL_338:
                  v56 = 0;
LABEL_339:
                  KeReleaseMutex(*(PRKMUTEX *)(*v60 + 40), 0);
LABEL_366:
                  v48 = 1;
                  goto LABEL_368;
              }
            }
            v55 = *(_DWORD *)&v107[5];
            goto LABEL_338;
          }
        }
        v56 = 0;
        v48 = 1;
        v55 = *(_DWORD *)&v107[5];
LABEL_368:
        HacAcquireLock(v15[1]);
        v82 = v15[1];
        if ( (*(_BYTE *)(v82 + 48) & 0x10) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          v78 = v15[1];
          appended = -1073741738;
          goto LABEL_345;
        }
        v83 = *(_DWORD *)(a1 + 540);
        if ( (v83 & 1) != 0 )
        {
          if ( (*(_DWORD *)(v112 + 2316) & 2) != 0 || (v114[8] & 0x1000) != 0 )
          {
            v86 = *(_DWORD *)(v82 + 128);
            if ( v86 != 5 && v86 != 2 )
            {
              v84 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_386;
              }
              v85 = 81;
              goto LABEL_385;
            }
          }
          else if ( *(_DWORD *)(v82 + 128) != 2 )
          {
            v84 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
            {
              goto LABEL_386;
            }
            v85 = 82;
LABEL_385:
            WPP_SF_(v84->AttachedDevice, v85, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_386:
            KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
            appended = -1073741565;
            goto LABEL_347;
          }
        }
        if ( (v83 & 0x40) != 0 && *(_DWORD *)(v82 + 128) == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
          appended = -1073741638;
          goto LABEL_347;
        }
        v87 = *(_QWORD *)v111;
        if ( !v48 && !(unsigned __int8)MdaAccessCheck(*(_QWORD *)v111, v82 + 128, v81, *(unsigned int *)(a1 + 512)) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
          appended = -1073741790;
          goto LABEL_347;
        }
        v88 = v114;
        if ( (v114[8] & 1) != 0 && *(_DWORD *)(v15[1] + 128) == 1 )
        {
          v89 = *(IRP **)(a1 + 40);
          *(_QWORD *)&v119 = v87;
          *((_QWORD *)&v119 + 1) = v15[1];
          RequestorProcessId = IoGetRequestorProcessId(v89);
          v91 = *(unsigned int *)(a1 + 532);
          LODWORD(v120) = RequestorProcessId;
          v92 = MdaMapShareAccess(v91);
          v93 = *(unsigned int *)(a1 + 512);
          DWORD1(v120) = v92;
          DWORD2(v120) = MdaMapDesiredAccess(v93);
          if ( *(_QWORD *)((char *)&v120 + 4) )
          {
            v94 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
            {
              WPP_SF_Z(
                WPP_GLOBAL_Control->AttachedDevice,
                85,
                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                v15[1] + 64);
            }
            KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
            while ( 1 )
            {
              appended = NlmShareOrUnshare(a1, &v119, 20);
              if ( appended >= 0 )
              {
                HacAcquireLock(v15[1]);
                v88 = v114;
                goto LABEL_422;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
              if ( appended == -1073741816 )
                break;
              if ( v94 || (*(_DWORD *)(a1 + 512) & 0xFFEFFFDF) != 0 )
                goto LABEL_347;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
              DWORD2(v120) = 1;
              v94 = 1;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_Z(
                WPP_GLOBAL_Control->AttachedDevice,
                87,
                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                v15[1] + 64);
            }
            HacOrphanStaleEntry(v112, v15[1]);
            goto LABEL_347;
          }
        }
LABEL_422:
        KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
        if ( v56 )
        {
          appended = NfsSetAttributes(v87, a1, v15, v126);
          if ( appended < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
LABEL_438:
            if ( (v88[8] & 1) == 0 )
              goto LABEL_347;
            HacAcquireLock(v15[1]);
            v99 = v15[1];
            v79 = *(struct _KMUTANT **)(v99 + 40);
            if ( *(_DWORD *)(v99 + 128) == 1 )
            {
              KeReleaseMutex(v79, 0);
              v100 = *(IRP **)(a1 + 40);
              *(_QWORD *)&v119 = v87;
              *((_QWORD *)&v119 + 1) = v15[1];
              v101 = IoGetRequestorProcessId(v100);
              v102 = *(unsigned int *)(a1 + 532);
              LODWORD(v120) = v101;
              v103 = MdaMapShareAccess(v102);
              v104 = *(unsigned int *)(a1 + 512);
              DWORD1(v120) = v103;
              DWORD2(v120) = MdaMapDesiredAccess(v104);
              if ( !*(_QWORD *)((char *)&v120 + 4) )
                goto LABEL_347;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              {
                WPP_SF_Z(
                  WPP_GLOBAL_Control->AttachedDevice,
                  92,
                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                  v15[1] + 64);
              }
              if ( (int)NlmShareOrUnshare(a1, &v119, 21) >= 0 )
                goto LABEL_347;
              v57 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_347;
              }
              v58 = 93;
              goto LABEL_448;
            }
LABEL_346:
            KeReleaseMutex(v79, 0);
            goto LABEL_347;
          }
          HacAcquireLock(v15[1]);
          MdaNotifyFullReportChange(*(PFAST_MUTEX *)(v122 + 104), 0, 0, 28, 3, 0);
          KeReleaseMutex(*(PRKMUTEX *)(v15[1] + 40), 0);
        }
        NetFobx = RxCreateNetFobx((PRX_CONTEXT)a1, *(PMRX_SRV_OPEN *)(a1 + 72));
        *(_QWORD *)(a1 + 64) = NetFobx;
        if ( NetFobx )
        {
          NetFobx->UnicodeQueryTemplate.Buffer = (PWSTR)ExAllocatePool2(258, 72, 1179805262);
          v98 = *(void **)(*(_QWORD *)(a1 + 64) + 56LL);
          if ( v98 )
          {
            memset(v98, 0, 0x48u);
            *(_QWORD *)(a1 + 600) = v55;
            MdaFinishCreate(a1, v87);
            appended = 0;
            goto LABEL_460;
          }
          v96 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_437;
          }
          v97 = 91;
        }
        else
        {
          v96 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_437;
          }
          v97 = 90;
        }
        WPP_SF_(v96->AttachedDevice, v97, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_437:
        appended = -1073741670;
        goto LABEL_438;
      }
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        goto LABEL_208;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      if ( appended < 0 )
      {
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_224;
        v46 = 55;
        goto LABEL_223;
      }
      if ( (*(_DWORD *)(a1 + 540) & 0x1000) != 0 )
      {
        appended = CheckForDeleteAccess(a1, *(_QWORD *)v111, v15);
        if ( appended < 0 )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            v58 = 56;
LABEL_448:
            WPP_SF_d(v57->AttachedDevice, v58, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
LABEL_347:
          v80 = v112;
          if ( v107[1] )
          {
            if ( v107[2] && v123 )
              HacDereference(v112, v123);
            if ( v108 && v124 )
              HacDereference(v80, v124);
          }
          else
          {
            if ( v107[2] )
            {
              HacDereference(v112, v15[1]);
              v15[1] = 0;
            }
            if ( v108 )
            {
              HacDereference(v80, *v15);
              *v15 = 0;
            }
          }
          goto LABEL_453;
        }
      }
    }
    v55 = 1;
    v56 = 0;
    goto LABEL_368;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  Pool2 = ExAllocatePool2(258, 40, 1163028046);
  *(_QWORD *)(v3 + 136) = Pool2;
  v15 = (__int64 *)Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)Pool2 = 0;
    *(_OWORD *)(Pool2 + 16) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    if ( FsRtlDoesNameContainWildCards(v9) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v9);
      appended = -1073741773;
      goto LABEL_460;
    }
    MdaDissectNameTail(v9, v125, &Source);
    LOBYTE(v19) = (unsigned __int8)~*(_BYTE *)(v1 + 2) >> 7;
    v20 = MdaParsePathFast(v111[0], a1, (int)v125, v19, (__int64)v15, &Destination, (__int64)&v107[1], (__int64)v107);
    appended = v20;
    if ( v20 == -1073741809 )
    {
      appended = -1073741766;
LABEL_98:
      if ( !v107[1] )
      {
        ExFreePoolWithTag(v15, 0x4552664Eu);
        *(_QWORD *)(v3 + 136) = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_453:
      if ( appended == -1073741809 )
        appended = -1073741772;
      goto LABEL_460;
    }
    if ( v20 == 260 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        ExFreePoolWithTag(Destination.Buffer, 0);
        goto LABEL_453;
      }
      if ( !v107[0] )
        PrependDriveLetterToTarget((_DWORD)v114, v5, v21, (unsigned int)&Destination, 0);
      v22 = ExAllocatePool2(66, 2 * (unsigned int)Destination.Length + 20 - (unsigned __int64)Source.Length, 2035513426);
      v23 = v22;
      if ( v22 )
      {
        *(_DWORD *)v22 = -1610612724;
        *(_WORD *)(v22 + 4) = 2 * (Destination.Length + 6) - Source.Length;
        *(_WORD *)(v22 + 6) = Source.Length;
        *(_WORD *)(v22 + 8) = Destination.Length;
        *(_WORD *)(v22 + 10) = Destination.Length - Source.Length;
        *(_WORD *)(v22 + 12) = 0;
        *(_WORD *)(v22 + 14) = Destination.Length;
        *(_DWORD *)(v22 + 16) = 0;
        memmove((void *)(v22 + 20), Destination.Buffer, Destination.Length);
        memmove(
          (void *)(v23 + Destination.Length + 20LL),
          Destination.Buffer,
          Destination.Length - (unsigned __int64)Source.Length);
        Buffer = Destination.Buffer;
        *(_QWORD *)(a1 + 800) = v23;
        ExFreePoolWithTag(Buffer, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        appended = -2147483603;
        goto LABEL_460;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_88:
        appended = -1073741670;
        ExFreePoolWithTag(Destination.Buffer, 0);
        goto LABEL_460;
      }
      v25 = 35;
LABEL_87:
      WPP_SF_(v24->AttachedDevice, v25, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      goto LABEL_88;
    }
    if ( v20 < 0 )
      goto LABEL_98;
    if ( (*(_BYTE *)(v109 + 2) & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      HacDereference(v112, *v15);
      appended = 0;
      *v15 = 0;
      v27 = RxCreateNetFobx((PRX_CONTEXT)a1, *(PMRX_SRV_OPEN *)(a1 + 72));
      *(_QWORD *)(a1 + 64) = v27;
      if ( v27 )
      {
        *(_QWORD *)(a1 + 600) = 1;
        if ( *(_DWORD *)(v3 + 192) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
        }
        else
        {
          RxFinishFcbInitialization((PMRX_FCB)v3, (RX_FILE_TYPE)60452, 0);
        }
        *(_QWORD *)(a1 + 736) = 0;
        goto LABEL_460;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_71;
      v17 = 40;
      goto LABEL_70;
    }
    v108 = 1;
    if ( (v114[8] & 0x100) == 0 && (unsigned int)(*(_DWORD *)(a1 + 536) - 1) > 4 )
    {
      v28 = 0;
      goto LABEL_180;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v9);
    v29 = v15 + 1;
    v30 = (unsigned __int8)~*(_BYTE *)(v109 + 2) >> 7;
    appended = CaseInsensitiveLookup(v111[0], a1, (_DWORD)v9, *v15, v30, (__int64)(v15 + 1));
    v31 = 1;
    if ( appended < 0 )
      goto LABEL_178;
    v32 = *v29;
    v107[2] = 1;
    HacAcquireLock(v32);
    v33 = *(struct _KMUTANT **)(*v29 + 40);
    if ( *(_DWORD *)(*v29 + 128) != 5 )
    {
      KeReleaseMutex(v33, 0);
      v28 = 1;
      goto LABEL_179;
    }
    KeReleaseMutex(v33, 0);
    v34 = v114[8];
    if ( (v34 & 0x200) == 0 )
    {
      if ( (*(_BYTE *)(v112 + 2316) & 2) == 0 && (v114[8] & 0x1000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        goto LABEL_224;
      }
      if ( (*(_DWORD *)(a1 + 512) & 0x10000) == 0 )
      {
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_224;
        v46 = 50;
        goto LABEL_223;
      }
      if ( (unsigned __int16)*(_DWORD *)(a1 + 512) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      }
      else
      {
        appended = 0;
      }
      goto LABEL_177;
    }
    if ( !v107[5] )
    {
      if ( (v34 & 0x100000) != 0 || !v30 )
        v31 = 0;
      *(_DWORD *)&Destination.Length = 34603008;
      Destination.Buffer = (PWSTR)ExAllocatePool2(258, 528, 827483726);
      if ( Destination.Buffer )
      {
        v107[0] = 0;
        v35 = *v29;
        v124 = *v15;
        v123 = v35;
        v36 = MdaResolveSymbolicLink(
                *(__int64 *)v111,
                (struct _MRX_FCB_ *)a1,
                v35,
                v31,
                &Destination,
                0,
                (__int64 *)v107,
                0,
                &v107[1]);
        appended = v36;
        if ( v36 >= 0 )
        {
          v39 = v114;
          if ( !v107[0] )
            PrependDriveLetterToTarget((_DWORD)v114, v5, v37, (unsigned int)&Destination, 0);
          *(_DWORD *)(a1 + 512) &= 0x1FFFFu;
          v40 = *(_DWORD *)(a1 + 512);
          if ( (v40 & 0x10000) != 0 )
          {
            if ( (v40 & 0xFFFEFFFF) != 0 )
            {
              appended = -1073741790;
LABEL_162:
              ExFreePoolWithTag(Destination.Buffer, 0);
              goto LABEL_177;
            }
          }
          else if ( Destination.Length )
          {
            v41 = (_DWORD *)ExAllocatePool2(66, 2 * (unsigned int)Destination.Length + 8 + 12LL, 2035513426);
            v42 = v41;
            if ( !v41 )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_88;
              }
              v25 = 43;
              goto LABEL_87;
            }
            *v41 = -1610612724;
            v43 = v41 + 5;
            Length = Destination.Length;
            *((_WORD *)v42 + 3) = 0;
            *((_WORD *)v42 + 2) = 2 * (Length + 6);
            *((_WORD *)v42 + 4) = Destination.Length;
            *((_WORD *)v42 + 5) = Destination.Length;
            *((_WORD *)v42 + 6) = 0;
            *((_WORD *)v42 + 7) = Destination.Length;
            v42[4] = 0;
            memmove(v43, Destination.Buffer, Destination.Length);
            memmove((char *)v42 + Destination.Length + 20, Destination.Buffer, Destination.Length);
            *(_QWORD *)(a1 + 800) = v42;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            appended = -2147483603;
            goto LABEL_162;
          }
          v38 = v112;
        }
        else
        {
          if ( v36 != -1073741766
            || (v38 = v112, v39 = v114, (*(_BYTE *)(v112 + 2316) & 2) == 0 && (v114[8] & 0x1000) == 0) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            goto LABEL_162;
          }
          Destination.Length = 0;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        *(_WORD *)(a1 + 746) &= ~8u;
        if ( (*(_BYTE *)(v38 + 2316) & 2) == 0 && (v39[8] & 0x1000) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          appended = -1073741809;
        }
        else
        {
          appended = 0;
        }
        goto LABEL_162;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      appended = -1073741670;
    }
LABEL_177:
    if ( appended )
      goto LABEL_347;
LABEL_178:
    v28 = 1;
LABEL_179:
    LOBYTE(v6) = v107[5];
    goto LABEL_180;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_71;
  v17 = 33;
LABEL_70:
  WPP_SF_(v16->AttachedDevice, v17, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_71:
  appended = -1073741670;
LABEL_460:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400316d0  push    rbp
0x1400316d2  push    rbx
0x1400316d3  push    rsi
0x1400316d4  push    rdi
0x1400316d5  push    r12
0x1400316d7  push    r13
0x1400316d9  push    r14
0x1400316db  push    r15
0x1400316dd  lea     rbp, [rsp-68h]
0x1400316e2  sub     rsp, 168h
0x1400316e9  mov     rax, cs:__security_cookie
0x1400316f0  xor     rax, rsp
0x1400316f3  mov     [rbp+0A0h+var_50], rax
0x1400316f7  mov     rbx, [rcx+30h]
0x1400316fb  xorps   xmm0, xmm0
0x1400316fe  mov     rax, [rcx+50h]
0x140031702  xor     edx, edx; Val
0x140031704  mov     r14, [rcx+38h]
0x140031708  mov     rdi, rcx
0x14003170b  lea     rcx, [rbp+0A0h+var_90]; void *
0x14003170f  mov     [rsp+1A0h+var_140], rbx
0x140031714  mov     r13, [rbx+30h]
0x140031718  lea     r8d, [rdx+40h]; Size
0x14003171c  mov     [rbp+0A0h+var_120], rax
0x140031720  movups  [rbp+0A0h+var_E8], xmm0
0x140031724  movups  [rbp+0A0h+var_D8], xmm0
0x140031728  call    memset
0x14003172d  xorps   xmm0, xmm0
0x140031730  xor     r12d, r12d
0x140031733  xorps   xmm1, xmm1
0x140031736  mov     [rsp+1A0h+var_14D+1], r12b
0x14003173b  movups  xmmword ptr [rbp+0A0h+var_A0], xmm0
0x14003173f  mov     [rsp+1A0h+var_14D], r12b
0x140031744  movups  xmmword ptr [rbp+0A0h+Source.Length], xmm1
0x140031748  movups  xmmword ptr [rsp+1A0h+Destination.Length], xmm0
0x14003174d  mov     rcx, cs:WPP_GLOBAL_Control
0x140031754  lea     r8, WPP_GLOBAL_Control
0x14003175b  cmp     rcx, r8
0x14003175e  jz      short loc_140031783
0x140031760  mov     eax, [rcx+2Ch]
0x140031763  test    al, 8
0x140031765  jz      short loc_140031783
0x140031767  mov     rcx, [rcx+18h]
0x14003176b  lea     edx, [r12+10h]
0x140031770  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031777  call    WPP_SF_
0x14003177c  lea     r8, WPP_GLOBAL_Control
0x140031783  mov     rax, [rdi+290h]
0x14003178a  mov     qword ptr [rsp+1A0h+var_128], rax
0x14003178f  mov     rax, [rax+28h]
0x140031793  mov     [rbp+0A0h+var_110], rax
0x140031797  test    rax, rax
0x14003179a  jz      loc_1400338D5
0x1400317a0  mov     rsi, [rdi+288h]
0x1400317a7  mov     rax, [rsi+28h]
0x1400317ab  mov     [rbp+0A0h+var_B8], rax
0x1400317af  test    rax, rax
0x1400317b2  jz      loc_1400338D5
0x1400317b8  mov     r9, [rdi+38h]
0x1400317bc  mov     edx, 1
0x1400317c1  lea     r15, [r9+168h]
0x1400317c8  mov     [rbp+0A0h+var_F0], r15
0x1400317cc  test    r15, r15
0x1400317cf  jz      loc_140033872
0x1400317d5  test    [r15], dl
0x1400317d8  jnz     loc_140033872
0x1400317de  test    [r15+2], dl
0x1400317e2  jnz     loc_140033872
0x1400317e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400317ef  cmp     rcx, r8
0x1400317f2  jz      loc_140031A92
0x1400317f8  mov     eax, [rcx+2Ch]
0x1400317fb  mov     rbx, [rdi+48h]
0x1400317ff  test    al, 4
0x140031801  jz      short loc_14003181F
0x140031803  mov     rcx, [rcx+18h]
0x140031807  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14003180e  mov     edx, 12h
0x140031813  call    WPP_SF_q
0x140031818  lea     r8, WPP_GLOBAL_Control
0x14003181f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031826  cmp     rcx, r8
0x140031829  jz      loc_140031A8D
0x14003182f  mov     eax, [rcx+2Ch]
0x140031832  test    al, 4
0x140031834  jz      short loc_140031859
0x140031836  mov     r9, [rdi+280h]
0x14003183d  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031844  mov     rcx, [rcx+18h]
0x140031848  mov     edx, 13h
0x14003184d  call    WPP_SF_q
0x140031852  lea     r8, WPP_GLOBAL_Control
0x140031859  mov     rcx, cs:WPP_GLOBAL_Control
0x140031860  cmp     rcx, r8
0x140031863  jz      loc_140031A8D
0x140031869  mov     eax, [rcx+2Ch]
0x14003186c  test    al, 4
0x14003186e  jz      short loc_140031893
0x140031870  mov     r9, [rdi+288h]
0x140031877  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14003187e  mov     rcx, [rcx+18h]
0x140031882  mov     edx, 14h
0x140031887  call    WPP_SF_q
0x14003188c  lea     r8, WPP_GLOBAL_Control
0x140031893  mov     rcx, cs:WPP_GLOBAL_Control
0x14003189a  cmp     rcx, r8
0x14003189d  jz      loc_140031A8D
0x1400318a3  mov     eax, [rcx+2Ch]
0x1400318a6  test    al, 4
0x1400318a8  jz      short loc_1400318CD
0x1400318aa  mov     r9, [rdi+290h]
0x1400318b1  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400318b8  mov     rcx, [rcx+18h]
0x1400318bc  mov     edx, 15h
0x1400318c1  call    WPP_SF_q
0x1400318c6  lea     r8, WPP_GLOBAL_Control
0x1400318cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400318d4  cmp     rcx, r8
0x1400318d7  jz      loc_140031A8D
0x1400318dd  mov     eax, [rcx+2Ch]
0x1400318e0  test    al, 4
0x1400318e2  jz      short loc_140031904
0x1400318e4  mov     r9, [rdi+48h]
0x1400318e8  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400318ef  mov     rcx, [rcx+18h]
0x1400318f3  mov     edx, 16h
0x1400318f8  call    WPP_SF_q
0x1400318fd  lea     r8, WPP_GLOBAL_Control
0x140031904  mov     rcx, cs:WPP_GLOBAL_Control
0x14003190b  cmp     rcx, r8
0x14003190e  jz      loc_140031A8D
0x140031914  mov     eax, [rcx+2Ch]
0x140031917  test    al, 4
0x140031919  jz      short loc_14003193E
0x14003191b  mov     r9d, [rdi+2C8h]
0x140031922  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031929  mov     rcx, [rcx+18h]
0x14003192d  mov     edx, 17h
0x140031932  call    WPP_SF_d
0x140031937  lea     r8, WPP_GLOBAL_Control
0x14003193e  mov     rcx, cs:WPP_GLOBAL_Control
0x140031945  cmp     rcx, r8
0x140031948  jz      loc_140031A8D
0x14003194e  mov     eax, [rcx+2Ch]
0x140031951  test    al, 4
0x140031953  jz      short loc_140031978
0x140031955  mov     r9d, [rdi+2CCh]
0x14003195c  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031963  mov     rcx, [rcx+18h]
0x140031967  mov     edx, 18h
0x14003196c  call    WPP_SF_d
0x140031971  lea     r8, WPP_GLOBAL_Control
0x140031978  mov     rcx, cs:WPP_GLOBAL_Control
0x14003197f  cmp     rcx, r8
0x140031982  jz      loc_140031A8D
0x140031988  mov     eax, [rcx+2Ch]
0x14003198b  test    al, 4
0x14003198d  jz      short loc_1400319B7
0x14003198f  movzx   r9d, byte ptr [rdi+2EDh]
0x140031997  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14003199e  mov     rcx, [rcx+18h]
0x1400319a2  and     r9d, 1
0x1400319a6  mov     edx, 19h
0x1400319ab  call    WPP_SF_d
0x1400319b0  lea     r8, WPP_GLOBAL_Control
0x1400319b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400319be  cmp     rcx, r8
0x1400319c1  jz      loc_140031A8D
0x1400319c7  mov     eax, [rcx+2Ch]
0x1400319ca  test    al, 4
0x1400319cc  jz      short loc_1400319ED
0x1400319ce  mov     rcx, [rcx+18h]
0x1400319d2  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400319d9  mov     edx, 1Ah
0x1400319de  mov     r9, r15
0x1400319e1  call    WPP_SF_Z
0x1400319e6  lea     r8, WPP_GLOBAL_Control
0x1400319ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400319f4  cmp     rcx, r8
0x1400319f7  jz      loc_140031A8D
0x1400319fd  mov     eax, [rcx+2Ch]
0x140031a00  test    al, 4
0x140031a02  jz      short loc_140031A24
0x140031a04  mov     r9d, [rbx+78h]
0x140031a08  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031a0f  mov     rcx, [rcx+18h]
0x140031a13  mov     edx, 1Bh
0x140031a18  call    WPP_SF_d
0x140031a1d  lea     r8, WPP_GLOBAL_Control
0x140031a24  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a2b  cmp     rcx, r8
0x140031a2e  jz      short loc_140031A8D
0x140031a30  mov     eax, [rcx+2Ch]
0x140031a33  test    al, 4
0x140031a35  jz      short loc_140031A57
0x140031a37  mov     r9d, [rbx+7Ch]
0x140031a3b  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031a42  mov     rcx, [rcx+18h]
0x140031a46  mov     edx, 1Ch
0x140031a4b  call    WPP_SF_d
0x140031a50  lea     r8, WPP_GLOBAL_Control
0x140031a57  mov     rcx, cs:WPP_GLOBAL_Control
0x140031a5e  cmp     rcx, r8
0x140031a61  jz      short loc_140031A8D
0x140031a63  mov     eax, [rcx+2Ch]
0x140031a66  test    al, 4
0x140031a68  jz      short loc_140031A8D
0x140031a6a  mov     r9d, [rbx+84h]
0x140031a71  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031a78  mov     rcx, [rcx+18h]
0x140031a7c  mov     edx, 1Dh
0x140031a81  call    WPP_SF_d
0x140031a86  lea     r8, WPP_GLOBAL_Control
0x140031a8d  mov     rbx, [rsp+1A0h+var_140]
0x140031a92  movzx   edx, byte ptr [rsi+4Dh]
0x140031a96  mov     r9d, 1
0x140031a9c  mov     al, dl
0x140031a9e  mov     [rbp+0A0h+var_B0], r12
0x140031aa2  sub     al, r9b
0x140031aa5  mov     [rbp+0A0h+var_A8], r12
0x140031aa9  mov     dword ptr [rsp+1A0h+var_14D+5], r12d
0x140031aae  cmp     al, r9b
0x140031ab1  jbe     short loc_140031AB8
0x140031ab3  cmp     dl, 5
0x140031ab6  jb      short loc_140031AEA
0x140031ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140031abf  cmp     rcx, r8
0x140031ac2  jz      short loc_140031AEA
0x140031ac4  mov     eax, [rcx+2Ch]
0x140031ac7  test    r9b, al
0x140031aca  jz      short loc_140031AEA
0x140031acc  mov     rcx, [rcx+18h]
0x140031ad0  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031ad7  mov     r9d, edx
0x140031ada  mov     edx, 1Eh
0x140031adf  call    WPP_SF_d
0x140031ae4  mov     r9d, 1
0x140031aea  mov     eax, [r14+9Ch]
0x140031af1  test    r9b, al
0x140031af4  jz      short loc_140031B2D
0x140031af6  mov     rcx, cs:WPP_GLOBAL_Control
0x140031afd  lea     rsi, WPP_GLOBAL_Control
0x140031b04  cmp     rcx, rsi
0x140031b07  jz      short loc_140031B34
0x140031b09  mov     eax, [rcx+2Ch]
0x140031b0c  test    al, 2
0x140031b0e  jz      short loc_140031B34
0x140031b10  mov     rcx, [rcx+18h]
0x140031b14  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031b1b  mov     edx, 1Fh
0x140031b20  call    WPP_SF_
0x140031b25  mov     r9d, 1
0x140031b2b  jmp     short loc_140031B34
0x140031b2d  lea     rsi, WPP_GLOBAL_Control
0x140031b34  mov     eax, [rdi+21Ch]
0x140031b3a  mov     [rsp+1A0h+var_14D+2], r12b
0x140031b3f  test    r9b, al
0x140031b42  jnz     short loc_140031B53
0x140031b44  mov     eax, [rdi+210h]
0x140031b4a  mov     [rsp+1A0h+var_14F], r12b
0x140031b4f  test    al, 10h
0x140031b51  jz      short loc_140031B58
0x140031b53  mov     [rsp+1A0h+var_14F], r9b
0x140031b58  mov     rcx, [rdi+2B8h]
0x140031b5f  test    rcx, rcx
0x140031b62  jz      short loc_140031BAA
0x140031b64  mov     edx, [rdi+2C8h]
0x140031b6a  test    edx, edx
0x140031b6c  jz      short loc_140031BAA
0x140031b6e  mov     r8, [rbp+0A0h+var_110]
0x140031b72  xor     eax, eax
0x140031b74  mov     [rbp+0A0h+var_100], rax
0x140031b78  mov     [rbp+0A0h+var_F8], rax
0x140031b7c  test    dword ptr [r8+20h], 200h
0x140031b84  jz      short loc_140031BAA
0x140031b86  lea     r9, aNfsactonlink; "NfsActOnLink"
0x140031b8d  lea     r8, [rbp+0A0h+var_100]
0x140031b91  call    MdaFindEAValue
0x140031b96  test    eax, eax
0x140031b98  movzx   r12d, r12b
0x140031b9c  mov     eax, 1
0x140031ba1  cmovz   r12d, eax
0x140031ba5  mov     dword ptr [rsp+1A0h+var_14D+5], r12d
0x140031baa  cmp     dword ptr [r14+0C0h], 0
0x140031bb2  jnz     loc_1400325CF
0x140031bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140031bbf  cmp     rcx, rsi
0x140031bc2  jz      short loc_140031BE0
0x140031bc4  mov     eax, [rcx+2Ch]
0x140031bc7  test    al, 4
0x140031bc9  jz      short loc_140031BE0
0x140031bcb  mov     rcx, [rcx+18h]
0x140031bcf  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031bd6  mov     edx, 20h ; ' '
0x140031bdb  call    WPP_SF_
0x140031be0  mov     edx, 28h ; '('
0x140031be5  mov     ecx, 102h
0x140031bea  mov     r8d, 4552664Eh
0x140031bf0  call    cs:__imp_ExAllocatePool2
0x140031bf7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
