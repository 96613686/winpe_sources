# MdaCreate

- ea: `0x1400316d0`
- end: `0x1400338fb`
- name: `MdaCreate`
- size: `8747`
- prototype: `__int64 __fastcall(int)`
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
  PDEVICE_OBJECT *v7; // r8
  __int64 v8; // rsi
  __int64 v9; // r9
  struct _UNICODE_STRING *v10; // r15
  unsigned __int8 v11; // dl
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 Pool2; // rax
  __int64 *v16; // rsi
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  NTSTATUS appended; // ebx
  int v20; // r9d
  int v21; // eax
  int v22; // r8d
  __int64 v23; // rax
  __int64 v24; // rbx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PWSTR Buffer; // rcx
  PMRX_FOBX v28; // rax
  char v29; // r13
  __int64 *v30; // r12
  char v31; // r14
  __int64 v32; // rdx
  BOOLEAN v33; // r15
  __int64 v34; // rcx
  struct _KMUTANT *v35; // rcx
  int v36; // eax
  __int64 v37; // r8
  int v38; // eax
  int v39; // r8d
  __int64 v40; // r15
  PDEVICE_OBJECT *v41; // r14
  int v42; // eax
  _DWORD *v43; // rax
  _DWORD *v44; // rbx
  void *v45; // rcx
  USHORT Length; // ax
  PDEVICE_OBJECT *v47; // rdx
  PDEVICE_OBJECT v48; // rcx
  __int64 v49; // rdx
  int v50; // ecx
  char v51; // r14
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // ecx
  int v56; // r14d
  char v57; // r15
  unsigned int v58; // r12d
  char v59; // r13
  PDEVICE_OBJECT v60; // rcx
  __int64 v61; // rdx
  char v62; // bl
  __int64 *v63; // r15
  __int64 v64; // rdx
  __int64 v65; // r8
  int v66; // r14d
  __int64 v67; // rcx
  __int64 v68; // rdx
  int v69; // r12d
  __int64 v70; // r9
  __int64 v71; // rcx
  unsigned int v72; // eax
  int v73; // ecx
  __int64 v74; // rcx
  __int64 v75; // rcx
  int v76; // eax
  int v77; // eax
  int v78; // eax
  __int64 v79; // rcx
  struct _KMUTANT *v80; // rcx
  __int64 v81; // rdi
  __int64 v82; // r8
  __int64 v83; // rdx
  int v84; // ecx
  PDEVICE_OBJECT v85; // rcx
  __int64 v86; // rdx
  int v87; // eax
  __int64 v88; // r15
  PDEVICE_OBJECT *v89; // r14
  IRP *v90; // rcx
  ULONG RequestorProcessId; // eax
  __int64 v92; // rcx
  int v93; // eax
  __int64 v94; // rcx
  int v95; // r14d
  __int64 v96; // rdx
  __int64 v97; // r8
  __int64 v98; // rdx
  __int64 v99; // r8
  PMRX_FOBX NetFobx; // rax
  PDEVICE_OBJECT v101; // rcx
  __int64 v102; // rdx
  void *v103; // rcx
  __int64 v104; // rax
  IRP *v105; // rcx
  ULONG v106; // eax
  __int64 v107; // rcx
  int v108; // eax
  __int64 v109; // rcx
  char v111; // [rsp+51h] [rbp-AFh]
  _BYTE v112[9]; // [rsp+53h] [rbp-ADh] BYREF
  char v113; // [rsp+5Ch] [rbp-A4h]
  __int64 v114; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  int v116[2]; // [rsp+78h] [rbp-88h]
  __int64 v117; // [rsp+80h] [rbp-80h]
  int v118; // [rsp+88h] [rbp-78h]
  PDEVICE_OBJECT *v119; // [rsp+90h] [rbp-70h]
  int v120; // [rsp+98h] [rbp-68h]
  __int64 v121; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v122; // [rsp+A8h] [rbp-58h]
  __int64 v123; // [rsp+B0h] [rbp-50h]
  __int128 v124; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v125; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING Source; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v127; // [rsp+E8h] [rbp-18h]
  __int64 v128; // [rsp+F0h] [rbp-10h]
  __int64 v129; // [rsp+F8h] [rbp-8h]
  int v130[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v131[8]; // [rsp+110h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v2 = *(_QWORD *)(a1 + 80);
  v3 = *(_QWORD *)(a1 + 56);
  v114 = v1;
  v5 = *(_QWORD *)(v1 + 48);
  v117 = v2;
  v124 = 0;
  v125 = 0;
  memset(v131, 0, sizeof(v131));
  LOBYTE(v6) = 0;
  *(_OWORD *)v130 = 0;
  *(_WORD *)v112 = 0;
  Source = 0;
  Destination = 0;
  v7 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    v7 = &WPP_GLOBAL_Control;
  }
  *(_QWORD *)v116 = *(_QWORD *)(a1 + 656);
  v119 = *(PDEVICE_OBJECT **)(*(_QWORD *)v116 + 40LL);
  if ( !v119 )
    return 3221225662LL;
  v8 = *(_QWORD *)(a1 + 648);
  v127 = *(_QWORD *)(v8 + 40);
  if ( !v127 )
    return 3221225662LL;
  v9 = *(_QWORD *)(a1 + 56);
  v10 = (struct _UNICODE_STRING *)(v9 + 360);
  v123 = v9 + 360;
  if ( v9 == -360 || (v10->Length & 1) != 0 || (*(_BYTE *)(v9 + 362) & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    appended = -1073741811;
    goto LABEL_461;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      v7 = &WPP_GLOBAL_Control;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        v7 = &WPP_GLOBAL_Control;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          v7 = &WPP_GLOBAL_Control;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            v7 = &WPP_GLOBAL_Control;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              v7 = &WPP_GLOBAL_Control;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                v7 = &WPP_GLOBAL_Control;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                  v7 = &WPP_GLOBAL_Control;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                    v7 = &WPP_GLOBAL_Control;
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                    {
                      WPP_SF_Z(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                        v10);
                      v7 = &WPP_GLOBAL_Control;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          27,
                          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                        v7 = &WPP_GLOBAL_Control;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            28,
                            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                          v7 = &WPP_GLOBAL_Control;
                        }
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            29,
                            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                          v7 = &WPP_GLOBAL_Control;
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
    v1 = v114;
  }
  v11 = *(_BYTE *)(v8 + 77);
  v128 = 0;
  v129 = 0;
  *(_DWORD *)&v112[5] = 0;
  if ( ((unsigned __int8)(v11 - 1) <= 1u || v11 >= 5u)
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
  v12 = *(_DWORD *)(a1 + 540);
  v112[2] = 0;
  if ( (v12 & 1) != 0 || (v111 = 0, (*(_DWORD *)(a1 + 528) & 0x10) != 0) )
    v111 = 1;
  v13 = *(_QWORD *)(a1 + 696);
  if ( v13 )
  {
    v14 = *(unsigned int *)(a1 + 712);
    if ( (_DWORD)v14 )
    {
      v7 = v119;
      v121 = 0;
      v122 = 0;
      if ( ((_DWORD)v119[4] & 0x200) != 0 )
      {
        v6 = MdaFindEAValue(v13, v14, &v121, "NfsActOnLink") == 0;
        *(_DWORD *)&v112[5] = v6;
      }
    }
  }
  if ( *(_DWORD *)(v3 + 192) )
  {
    v16 = *(__int64 **)(v3 + 136);
    v29 = 1;
    v113 = 0;
    appended = 0;
    v47 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
    {
LABEL_181:
      if ( v112[1] )
      {
        if ( !appended )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          appended = -1073741823;
        }
        goto LABEL_348;
      }
      v50 = *(_DWORD *)(a1 + 536);
      v51 = 0;
      LODWORD(v131[0]) = 0;
      LODWORD(v131[1]) = 0;
      LODWORD(v131[2]) = 0;
      LODWORD(v131[3]) = 0;
      LODWORD(v131[5]) = 0;
      HIDWORD(v131[6]) = 0;
      if ( !v50 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        if ( v29 == 1 )
        {
          if ( appended < 0 )
            goto LABEL_209;
          v58 = 0;
          HacAcquireLock(v16[1], v47, v7);
          if ( !*(_QWORD *)(v16[1] + 152) || v111 )
          {
            v59 = 0;
          }
          else
          {
            v131[4] = 0;
            LODWORD(v131[3]) = 1;
            v59 = 1;
          }
          goto LABEL_216;
        }
        goto LABEL_271;
      }
      v52 = v50 - 1;
      if ( v52 )
      {
        v53 = v52 - 1;
        if ( !v53 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          if ( v29 == 1 )
          {
            if ( appended >= 0 )
            {
              appended = -1073741771;
              goto LABEL_348;
            }
            MdaNtAttributesToNfsAttributes(*(_QWORD *)v116, a1, v131);
            v57 = v111;
            if ( !v111 )
            {
              LODWORD(v131[3]) = 1;
              v131[4] = 0;
            }
            LODWORD(v131[5]) = 2;
            MdaCurrentTimeToNfsTime((char *)&v131[5] + 4);
            v131[7] = *(_QWORD *)((char *)&v131[5] + 4);
            HIDWORD(v131[6]) = 2;
          }
          else
          {
            v57 = v111;
          }
          goto LABEL_272;
        }
        v54 = v53 - 1;
        if ( v54 )
        {
          v55 = v54 - 1;
          if ( v55 )
          {
            if ( v55 != 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
              appended = -1073741637;
              goto LABEL_348;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            if ( v29 == 1 )
            {
              if ( appended < 0 )
              {
LABEL_209:
                v56 = v116[0];
                *(_DWORD *)&v112[5] = 2;
                MdaNtAttributesToNfsAttributes(*(_QWORD *)v116, a1, v131);
                v57 = v111;
                if ( !v111 )
                {
                  LODWORD(v131[3]) = 1;
                  v131[4] = 0;
                }
                LODWORD(v131[5]) = 2;
                MdaCurrentTimeToNfsTime((char *)&v131[5] + 4);
                v131[7] = *(_QWORD *)((char *)&v131[5] + 4);
                HIDWORD(v131[6]) = 2;
                v118 = 0;
                goto LABEL_274;
              }
              v58 = 3;
              HacAcquireLock(v16[1], v47, v7);
              if ( !*(_QWORD *)(v16[1] + 152) || v111 )
              {
                v59 = 0;
              }
              else
              {
                v131[4] = 0;
                LODWORD(v131[3]) = 1;
                v59 = 1;
              }
LABEL_216:
              KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
              goto LABEL_369;
            }
            goto LABEL_271;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          if ( appended >= 0 )
          {
            HacAcquireLock(v16[1], &WPP_GLOBAL_Control, v7);
            if ( !*(_QWORD *)(v16[1] + 152) || v111 )
            {
              v59 = 0;
            }
            else
            {
              v131[4] = 0;
              LODWORD(v131[3]) = 1;
              v59 = 1;
            }
            KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
            v58 = 3;
            goto LABEL_369;
          }
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
LABEL_225:
            appended = -1073741809;
            goto LABEL_348;
          }
          v49 = 58;
LABEL_224:
          WPP_SF_d(v48->AttachedDevice, v49, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          goto LABEL_225;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          v47 = &WPP_GLOBAL_Control;
        }
        if ( v29 != 1 )
        {
LABEL_271:
          v57 = v111;
LABEL_272:
          v56 = v116[0];
          *(_DWORD *)&v112[5] = 2;
          v118 = 0;
          if ( !v29 )
          {
            MdaNtAttributesToNfsAttributes(*(_QWORD *)v116, a1, v131);
            v118 = HIDWORD(v131[0]);
          }
LABEL_274:
          v62 = (unsigned __int8)~*(_BYTE *)(v114 + 2) >> 7;
          *(_QWORD *)v130 = MEMORY[0xFFFFF78000000014];
          if ( v57 )
          {
            v63 = v16 + 1;
            appended = NfsCreateOrMkdir(v56, a1, 2, *v16, v123, (__int64)v131, 0, v62, 0, (__int64)(v16 + 1));
            v120 = 2;
            v66 = 2;
          }
          else
          {
            v121 = 0;
            v122 = 0;
            if ( (_BYTE)v6
              || (v67 = *(_QWORD *)(a1 + 696)) == 0
              || (v68 = *(unsigned int *)(a1 + 712), !(_DWORD)v68)
              || (unsigned int)MdaFindEAValue(v67, v68, &v121, "NfsSymlinkTargetName") )
            {
              v69 = 1;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, &v121);
              }
              v69 = 5;
            }
            v70 = *v16;
            v63 = v16 + 1;
            v120 = v69;
            appended = NfsCreateOrMkdir(
                         v56,
                         a1,
                         v69,
                         v70,
                         v123,
                         (__int64)v131,
                         0,
                         v62,
                         (__int64)&v121,
                         (__int64)(v16 + 1));
            v66 = 1;
          }
          v121 = MEMORY[0xFFFFF78000000014];
          LODWORD(v131[0]) &= -(v29 != 0);
          if ( appended < 0 )
          {
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v61 = 66;
              goto LABEL_449;
            }
            goto LABEL_348;
          }
          v71 = *v63;
          v112[2] = 1;
          HacAcquireLock(v71, v64, v65);
          MdaNotifyFullReportChange(*(PFAST_MUTEX *)(v127 + 104), 0, 0, v66, 1, 0);
          KeReleaseMutex(*(PRKMUTEX *)(*v63 + 40), 0);
          if ( !v29 )
          {
            v72 = *(_DWORD *)(a1 + 536);
            if ( v72 > 5 )
            {
              v58 = *(_DWORD *)&v112[5];
              v59 = 0;
              goto LABEL_367;
            }
            v73 = 45;
            if ( _bittest(&v73, v72) )
            {
              v74 = *v63;
              LODWORD(v123) = *(_DWORD *)(*v63 + 208);
              LODWORD(v114) = *(_DWORD *)(v74 + 212);
              HacAcquireLock(v74, v47, v7);
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
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          70,
                          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
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
                              WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                              WPP_SF_q(
                                WPP_GLOBAL_Control->AttachedDevice,
                                73,
                                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                WPP_SF_q(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  74,
                                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
                                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                  WPP_SF_q(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    75,
                                    WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                {
                                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                    WPP_SF_q(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      76,
                                      WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                                  {
                                    WPP_SF_q(
                                      WPP_GLOBAL_Control->AttachedDevice,
                                      77,
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
              v75 = *v63;
              if ( *(_DWORD *)(*v63 + 128) == v120
                && (*(_DWORD *)(v75 + 132) & 0x1FFF) == v118
                && !*(_QWORD *)(v75 + 152)
                && *(_DWORD *)(v75 + 140) == *((_DWORD *)v119 + 9)
                && *(_DWORD *)(v75 + 144) == *((_DWORD *)v119 + 10)
                && (v76 = *(_DWORD *)(v75 + 192), v76 == *(_DWORD *)(v75 + 200))
                && v76 == *(_DWORD *)(v75 + 208)
                && (v77 = *(_DWORD *)(v75 + 196), v77 == *(_DWORD *)(v75 + 204))
                && v77 == *(_DWORD *)(v75 + 212) )
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
                v78 = *(_DWORD *)(a1 + 536);
                switch ( v78 )
                {
                  case 2:
                    v79 = *v63;
                    appended = -1073741771;
LABEL_346:
                    v80 = *(struct _KMUTANT **)(v79 + 40);
                    goto LABEL_347;
                  case 3:
                    v58 = 1;
                    goto LABEL_339;
                  case 0:
                    v58 = 0;
                    if ( !*(_QWORD *)(*v63 + 152) || v111 )
                    {
                      v59 = 0;
                    }
                    else
                    {
                      v131[4] = 0;
                      LODWORD(v131[3]) = 1;
                      v59 = 1;
                    }
                    goto LABEL_340;
                  case 5:
                    v58 = 3;
                    if ( *(_QWORD *)(*v63 + 152) && !v111 )
                    {
                      v131[4] = 0;
                      LODWORD(v131[3]) = 1;
                      v59 = 1;
                      goto LABEL_340;
                    }
LABEL_339:
                    v59 = 0;
LABEL_340:
                    KeReleaseMutex(*(PRKMUTEX *)(*v63 + 40), 0);
LABEL_367:
                    v51 = 1;
                    goto LABEL_369;
                }
              }
              v58 = *(_DWORD *)&v112[5];
              goto LABEL_339;
            }
          }
          v59 = 0;
          v51 = 1;
          v58 = *(_DWORD *)&v112[5];
LABEL_369:
          HacAcquireLock(v16[1], v47, v7);
          v83 = v16[1];
          if ( (*(_BYTE *)(v83 + 48) & 0x10) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            v79 = v16[1];
            appended = -1073741738;
            goto LABEL_346;
          }
          v84 = *(_DWORD *)(a1 + 540);
          if ( (v84 & 1) != 0 )
          {
            if ( (*(_DWORD *)(v117 + 2316) & 2) != 0 || ((_DWORD)v119[4] & 0x1000) != 0 )
            {
              v87 = *(_DWORD *)(v83 + 128);
              if ( v87 != 5 && v87 != 2 )
              {
                v85 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
                {
                  goto LABEL_387;
                }
                v86 = 81;
                goto LABEL_386;
              }
            }
            else if ( *(_DWORD *)(v83 + 128) != 2 )
            {
              v85 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_387;
              }
              v86 = 82;
LABEL_386:
              WPP_SF_(v85->AttachedDevice, v86, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_387:
              KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
              appended = -1073741565;
              goto LABEL_348;
            }
          }
          if ( (v84 & 0x40) != 0 && *(_DWORD *)(v83 + 128) == 2 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
            appended = -1073741638;
            goto LABEL_348;
          }
          v88 = *(_QWORD *)v116;
          if ( !v51 && !(unsigned __int8)MdaAccessCheck(*(_QWORD *)v116, v83 + 128, v82, *(unsigned int *)(a1 + 512)) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
            appended = -1073741790;
            goto LABEL_348;
          }
          v89 = v119;
          if ( ((_DWORD)v119[4] & 1) != 0 && *(_DWORD *)(v16[1] + 128) == 1 )
          {
            v90 = *(IRP **)(a1 + 40);
            *(_QWORD *)&v124 = v88;
            *((_QWORD *)&v124 + 1) = v16[1];
            RequestorProcessId = IoGetRequestorProcessId(v90);
            v92 = *(unsigned int *)(a1 + 532);
            LODWORD(v125) = RequestorProcessId;
            v93 = MdaMapShareAccess(v92);
            v94 = *(unsigned int *)(a1 + 512);
            DWORD1(v125) = v93;
            DWORD2(v125) = MdaMapDesiredAccess(v94);
            if ( *(_QWORD *)((char *)&v125 + 4) )
            {
              v95 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              {
                WPP_SF_Z(
                  WPP_GLOBAL_Control->AttachedDevice,
                  85,
                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                  v16[1] + 64);
              }
              KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
              while ( 1 )
              {
                appended = NlmShareOrUnshare(a1, &v124, 20);
                if ( appended >= 0 )
                {
                  HacAcquireLock(v16[1], v96, v97);
                  v89 = v119;
                  goto LABEL_423;
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                }
                if ( appended == -1073741816 )
                  break;
                if ( v95 || (*(_DWORD *)(a1 + 512) & 0xFFEFFFDF) != 0 )
                  goto LABEL_348;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
                }
                DWORD2(v125) = 1;
                v95 = 1;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_Z(
                  WPP_GLOBAL_Control->AttachedDevice,
                  87,
                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                  v16[1] + 64);
              }
              HacOrphanStaleEntry(v117, v16[1]);
              goto LABEL_348;
            }
          }
LABEL_423:
          KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
          if ( v59 )
          {
            appended = NfsSetAttributes(v88, a1, v16, v131);
            if ( appended < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
LABEL_439:
              if ( ((_DWORD)v89[4] & 1) == 0 )
                goto LABEL_348;
              HacAcquireLock(v16[1], v98, v99);
              v104 = v16[1];
              v80 = *(struct _KMUTANT **)(v104 + 40);
              if ( *(_DWORD *)(v104 + 128) == 1 )
              {
                KeReleaseMutex(v80, 0);
                v105 = *(IRP **)(a1 + 40);
                *(_QWORD *)&v124 = v88;
                *((_QWORD *)&v124 + 1) = v16[1];
                v106 = IoGetRequestorProcessId(v105);
                v107 = *(unsigned int *)(a1 + 532);
                LODWORD(v125) = v106;
                v108 = MdaMapShareAccess(v107);
                v109 = *(unsigned int *)(a1 + 512);
                DWORD1(v125) = v108;
                DWORD2(v125) = MdaMapDesiredAccess(v109);
                if ( !*(_QWORD *)((char *)&v125 + 4) )
                  goto LABEL_348;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                {
                  WPP_SF_Z(
                    WPP_GLOBAL_Control->AttachedDevice,
                    92,
                    WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                    v16[1] + 64);
                }
                if ( (int)NlmShareOrUnshare(a1, &v124, 21) >= 0 )
                  goto LABEL_348;
                v60 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
                {
                  goto LABEL_348;
                }
                v61 = 93;
                goto LABEL_449;
              }
LABEL_347:
              KeReleaseMutex(v80, 0);
              goto LABEL_348;
            }
            HacAcquireLock(v16[1], v98, v99);
            MdaNotifyFullReportChange(*(PFAST_MUTEX *)(v127 + 104), 0, 0, 28, 3, 0);
            KeReleaseMutex(*(PRKMUTEX *)(v16[1] + 40), 0);
          }
          NetFobx = RxCreateNetFobx((PRX_CONTEXT)a1, *(PMRX_SRV_OPEN *)(a1 + 72));
          *(_QWORD *)(a1 + 64) = NetFobx;
          if ( NetFobx )
          {
            NetFobx->UnicodeQueryTemplate.Buffer = (PWSTR)ExAllocatePool2(258, 72, 1179805262);
            v103 = *(void **)(*(_QWORD *)(a1 + 64) + 56LL);
            if ( v103 )
            {
              memset(v103, 0, 0x48u);
              *(_QWORD *)(a1 + 600) = v58;
              MdaFinishCreate(a1, v88);
              appended = 0;
              goto LABEL_461;
            }
            v101 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_438;
            }
            v102 = 91;
          }
          else
          {
            v101 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_438;
            }
            v102 = 90;
          }
          WPP_SF_(v101->AttachedDevice, v102, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_438:
          appended = -1073741670;
          goto LABEL_439;
        }
        if ( appended < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          }
          goto LABEL_209;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
          v47 = &WPP_GLOBAL_Control;
        }
        if ( appended < 0 )
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          {
            goto LABEL_225;
          }
          v49 = 55;
          goto LABEL_224;
        }
        if ( (*(_DWORD *)(a1 + 540) & 0x1000) != 0 )
        {
          appended = CheckForDeleteAccess(a1, *(_QWORD *)v116, v16);
          if ( appended < 0 )
          {
            v60 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              v61 = 56;
LABEL_449:
              WPP_SF_d(v60->AttachedDevice, v61, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
LABEL_348:
            v81 = v117;
            if ( v112[1] )
            {
              if ( v112[2] && v128 )
                HacDereference(v117, v128);
              if ( v113 && v129 )
                HacDereference(v81, v129);
            }
            else
            {
              if ( v112[2] )
              {
                HacDereference(v117, v16[1]);
                v16[1] = 0;
              }
              if ( v113 )
              {
                HacDereference(v81, *v16);
                *v16 = 0;
              }
            }
            goto LABEL_454;
          }
        }
      }
      v58 = 1;
      v59 = 0;
      goto LABEL_369;
    }
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_180:
    v47 = &WPP_GLOBAL_Control;
    goto LABEL_181;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  Pool2 = ExAllocatePool2(258, 40, 1163028046);
  *(_QWORD *)(v3 + 136) = Pool2;
  v16 = (__int64 *)Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)Pool2 = 0;
    *(_OWORD *)(Pool2 + 16) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    if ( FsRtlDoesNameContainWildCards(v10) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v10);
      appended = -1073741773;
      goto LABEL_461;
    }
    MdaDissectNameTail(v10, v130, &Source);
    LOBYTE(v20) = (unsigned __int8)~*(_BYTE *)(v1 + 2) >> 7;
    v21 = MdaParsePathFast(v116[0], a1, (int)v130, v20, (__int64)v16, &Destination, (__int64)&v112[1], (__int64)v112);
    appended = v21;
    if ( v21 == -1073741809 )
    {
      appended = -1073741766;
LABEL_98:
      if ( !v112[1] )
      {
        ExFreePoolWithTag(v16, 0x4552664Eu);
        *(_QWORD *)(v3 + 136) = 0;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_454:
      if ( appended == -1073741809 )
        appended = -1073741772;
      goto LABEL_461;
    }
    if ( v21 == 260 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &Source);
      if ( appended < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        ExFreePoolWithTag(Destination.Buffer, 0);
        goto LABEL_454;
      }
      if ( !v112[0] )
        PrependDriveLetterToTarget((_DWORD)v119, v5, v22, (unsigned int)&Destination, 0);
      v23 = ExAllocatePool2(66, 2 * (unsigned int)Destination.Length + 20 - (unsigned __int64)Source.Length, 2035513426);
      v24 = v23;
      if ( v23 )
      {
        *(_DWORD *)v23 = -1610612724;
        *(_WORD *)(v23 + 4) = 2 * (Destination.Length + 6) - Source.Length;
        *(_WORD *)(v23 + 6) = Source.Length;
        *(_WORD *)(v23 + 8) = Destination.Length;
        *(_WORD *)(v23 + 10) = Destination.Length - Source.Length;
        *(_WORD *)(v23 + 12) = 0;
        *(_WORD *)(v23 + 14) = Destination.Length;
        *(_DWORD *)(v23 + 16) = 0;
        memmove((void *)(v23 + 20), Destination.Buffer, Destination.Length);
        memmove(
          (void *)(v24 + Destination.Length + 20LL),
          Destination.Buffer,
          Destination.Length - (unsigned __int64)Source.Length);
        Buffer = Destination.Buffer;
        *(_QWORD *)(a1 + 800) = v24;
        ExFreePoolWithTag(Buffer, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        appended = -2147483603;
        goto LABEL_461;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
LABEL_88:
        appended = -1073741670;
        ExFreePoolWithTag(Destination.Buffer, 0);
        goto LABEL_461;
      }
      v26 = 35;
LABEL_87:
      WPP_SF_(v25->AttachedDevice, v26, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      goto LABEL_88;
    }
    if ( v21 < 0 )
      goto LABEL_98;
    if ( (*(_BYTE *)(v114 + 2) & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      HacDereference(v117, *v16);
      appended = 0;
      *v16 = 0;
      v28 = RxCreateNetFobx((PRX_CONTEXT)a1, *(PMRX_SRV_OPEN *)(a1 + 72));
      *(_QWORD *)(a1 + 64) = v28;
      if ( v28 )
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
        goto LABEL_461;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_71;
      v18 = 40;
      goto LABEL_70;
    }
    v113 = 1;
    if ( ((_DWORD)v119[4] & 0x100) == 0 && (unsigned int)(*(_DWORD *)(a1 + 536) - 1) > 4 )
    {
      v29 = 0;
      goto LABEL_180;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, v10);
    v30 = v16 + 1;
    v31 = (unsigned __int8)~*(_BYTE *)(v114 + 2) >> 7;
    appended = CaseInsensitiveLookup(v116[0], a1, (_DWORD)v10, *v16, v31, (__int64)(v16 + 1));
    v33 = 1;
    if ( appended < 0 )
      goto LABEL_178;
    v34 = *v30;
    v112[2] = 1;
    HacAcquireLock(v34, v32, v7);
    v35 = *(struct _KMUTANT **)(*v30 + 40);
    if ( *(_DWORD *)(*v30 + 128) != 5 )
    {
      KeReleaseMutex(v35, 0);
      v29 = 1;
      goto LABEL_179;
    }
    KeReleaseMutex(v35, 0);
    v7 = v119;
    v36 = *((_DWORD *)v119 + 8);
    if ( (v36 & 0x200) == 0 )
    {
      if ( (*(_BYTE *)(v117 + 2316) & 2) == 0 && ((_DWORD)v119[4] & 0x1000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        goto LABEL_225;
      }
      if ( (*(_DWORD *)(a1 + 512) & 0x10000) == 0 )
      {
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_225;
        v49 = 50;
        goto LABEL_224;
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
    if ( !v112[5] )
    {
      if ( (v36 & 0x100000) != 0 || !v31 )
        v33 = 0;
      *(_DWORD *)&Destination.Length = 34603008;
      Destination.Buffer = (PWSTR)ExAllocatePool2(258, 528, 827483726);
      if ( Destination.Buffer )
      {
        v112[0] = 0;
        v37 = *v30;
        v129 = *v16;
        v128 = v37;
        v38 = MdaResolveSymbolicLink(
                *(__int64 *)v116,
                (struct _MRX_FCB_ *)a1,
                v37,
                v33,
                &Destination,
                0,
                (__int64 *)v112,
                0,
                (__int64)&v112[1]);
        appended = v38;
        if ( v38 >= 0 )
        {
          v41 = v119;
          if ( !v112[0] )
            PrependDriveLetterToTarget((_DWORD)v119, v5, v39, (unsigned int)&Destination, 0);
          *(_DWORD *)(a1 + 512) &= 0x1FFFFu;
          v42 = *(_DWORD *)(a1 + 512);
          if ( (v42 & 0x10000) != 0 )
          {
            if ( (v42 & 0xFFFEFFFF) != 0 )
            {
              appended = -1073741790;
LABEL_162:
              ExFreePoolWithTag(Destination.Buffer, 0);
              goto LABEL_177;
            }
          }
          else if ( Destination.Length )
          {
            v43 = (_DWORD *)ExAllocatePool2(66, 2 * (unsigned int)Destination.Length + 8 + 12LL, 2035513426);
            v44 = v43;
            if ( !v43 )
            {
              v25 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
              {
                goto LABEL_88;
              }
              v26 = 43;
              goto LABEL_87;
            }
            *v43 = -1610612724;
            v45 = v43 + 5;
            Length = Destination.Length;
            *((_WORD *)v44 + 3) = 0;
            *((_WORD *)v44 + 2) = 2 * (Length + 6);
            *((_WORD *)v44 + 4) = Destination.Length;
            *((_WORD *)v44 + 5) = Destination.Length;
            *((_WORD *)v44 + 6) = 0;
            *((_WORD *)v44 + 7) = Destination.Length;
            v44[4] = 0;
            memmove(v45, Destination.Buffer, Destination.Length);
            memmove((char *)v44 + Destination.Length + 20, Destination.Buffer, Destination.Length);
            *(_QWORD *)(a1 + 800) = v44;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
            }
            appended = -2147483603;
            goto LABEL_162;
          }
          v40 = v117;
        }
        else
        {
          if ( v38 != -1073741766
            || (v40 = v117, v41 = v119, (*(_BYTE *)(v117 + 2316) & 2) == 0 && ((_DWORD)v119[4] & 0x1000) == 0) )
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
        if ( (*(_BYTE *)(v40 + 2316) & 2) == 0 && ((_DWORD)v41[4] & 0x1000) == 0 )
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
      goto LABEL_348;
LABEL_178:
    v29 = 1;
LABEL_179:
    LOBYTE(v6) = v112[5];
    goto LABEL_180;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_71;
  v18 = 33;
LABEL_70:
  WPP_SF_(v17->AttachedDevice, v18, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
LABEL_71:
  appended = -1073741670;
LABEL_461:
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
