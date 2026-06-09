# MRxSmbQueryDirectory

- ea: `0x14002a430`
- end: `0x14002b7bf`
- name: `MRxSmbQueryDirectory`
- size: `5007`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000e46c`
- `0x14000e998`
- `0x14000ea10`
- `0x14000eb18`
- `0x14000ebd8`
- `0x14000ed10`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`
- `0x1400283f8`
- `0x14002a430`
- `0x14002b7c8`
- `0x14002c464`
- `0x14002cc54`
- `0x14003ef9c`
- `0x140043368`
- `0x140043f30`
- `0x140043f88`
- `0x14004ab70`
- `0x140052fa0`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002b01e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002b01e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002af09`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002af09`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002abc2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14002abc2`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002a872`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002aeed`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002a872`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x14002aeed`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a5cd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002abaf`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002a5cd`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14002abaf`
- `ntoskrnl!ExAllocatePool2` at `0x14002a8e9`
- `ntoskrnl!ExAllocatePool2` at `0x14002af3b`
- `ntoskrnl!ExAllocatePool2` at `0x14002b3a2`
- `ntoskrnl!ExAllocatePool2` at `0x14002a8e9`
- `ntoskrnl!ExAllocatePool2` at `0x14002af3b`
- `ntoskrnl!ExAllocatePool2` at `0x14002b3a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b789`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a9bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b789`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14002ac0f`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14002ac0f`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14002abde`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14002abde`
- `rdbss!RxDowngradeFcbToSharedInMRx` at `0x14002a5e6`
- `rdbss!RxDowngradeFcbToSharedInMRx` at `0x14002a5e6`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002ac85`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002ad1d`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002b300`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002b648`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002ac85`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002ad1d`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002b300`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x14002b648`

## pseudocode

```c
__int64 __fastcall MRxSmbQueryDirectory(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rbx
  __int64 v4; // rdi
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // r12
  int v8; // eax
  unsigned int v9; // edx
  bool v10; // r10
  __int64 v11; // r14
  __int16 v12; // r12
  int v13; // ebx
  __int64 result; // rax
  __int64 v15; // r8
  UNICODE_STRING *v16; // r9
  int v17; // esi
  PDEVICE_OBJECT v18; // rcx
  int v19; // edx
  __int16 v20; // ax
  __int16 v21; // cx
  _WORD *v22; // r15
  __int64 v23; // rbx
  int v24; // edx
  unsigned int v25; // edx
  void *Pool2; // rax
  PVOID v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // esi
  unsigned int v30; // eax
  __int64 v31; // r9
  int v32; // ecx
  __int64 v33; // rdx
  BOOLEAN IsResourceAcquiredExclusiveLite; // r14
  ULONG IsResourceAcquiredSharedLite; // eax
  ULONG v36; // esi
  int v37; // eax
  unsigned int v38; // eax
  __int64 v39; // rsi
  int v40; // ebx
  int v41; // esi
  int v42; // eax
  int v43; // r8d
  int v44; // ecx
  unsigned int v45; // r11d
  unsigned int v46; // eax
  __int16 v47; // dx
  __int64 v48; // rsi
  UNICODE_STRING *v49; // r14
  BOOLEAN DoesNameContainWildCards; // al
  __int64 v51; // rbx
  size_t Length; // r12
  __int64 v53; // rax
  __int64 v54; // r15
  _WORD *v55; // rsi
  int v56; // esi
  bool v57; // r12
  _WORD *v58; // rcx
  __int16 v59; // ax
  __int64 *v60; // r15
  _WORD *v61; // rbx
  int v62; // esi
  int v63; // r14d
  __int16 v64; // ax
  __int64 v65; // rax
  int v66; // ecx
  PDEVICE_OBJECT *v67; // r8
  int *v68; // rdx
  __int16 v69; // cx
  int v70; // eax
  char v71; // al
  int v72; // r14d
  unsigned int v73; // r12d
  char v74; // si
  char v75; // cl
  __int64 v76; // r15
  __int64 v77; // r14
  __int64 v78; // r12
  __int64 v79; // r14
  __int64 v80; // r9
  __int64 v81; // rsi
  const void *v82; // rdx
  unsigned int v83; // edx
  int *v84; // r14
  __int64 v85; // r12
  int v86; // esi
  int v87; // eax
  void *v88; // rcx
  bool v89; // [rsp+80h] [rbp-80h]
  unsigned int v90; // [rsp+84h] [rbp-7Ch]
  char v91; // [rsp+88h] [rbp-78h]
  unsigned int v92; // [rsp+8Ch] [rbp-74h]
  __int16 v93; // [rsp+90h] [rbp-70h]
  unsigned int DirectoryFromCache; // [rsp+94h] [rbp-6Ch] BYREF
  char v95; // [rsp+98h] [rbp-68h]
  __int64 v96; // [rsp+A0h] [rbp-60h]
  int v97; // [rsp+A8h] [rbp-58h]
  int v98; // [rsp+ACh] [rbp-54h]
  __int16 v99; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v100; // [rsp+B8h] [rbp-48h]
  unsigned int v101; // [rsp+C0h] [rbp-40h]
  __int64 v102; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v103; // [rsp+D0h] [rbp-30h]
  PVOID P[2]; // [rsp+D8h] [rbp-28h] BYREF
  int *v105; // [rsp+E8h] [rbp-18h]
  PVOID v106; // [rsp+F0h] [rbp-10h]
  __int64 v107; // [rsp+F8h] [rbp-8h]
  __int64 v108; // [rsp+100h] [rbp+0h]
  __int64 v109; // [rsp+108h] [rbp+8h]
  _DWORD v110[28]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v111[80]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v112; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v113; // [rsp+1D8h] [rbp+D8h]
  __int64 v114; // [rsp+1E0h] [rbp+E0h] BYREF
  int v115; // [rsp+1E8h] [rbp+E8h]

  v1 = *(_QWORD *)(a1 + 64);
  v2 = *(_QWORD *)(a1 + 56);
  DirectoryFromCache = 0;
  v4 = 0;
  v102 = v2;
  v100 = v1;
  if ( v1 )
    v4 = *(_QWORD *)(v1 + 56);
  v5 = *(_QWORD *)(v1 + 32);
  v109 = v5;
  v6 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 40) + 40LL) + 96LL);
  v99 = 0;
  v107 = v6;
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 32LL) + 32LL);
  v96 = v7;
  memset(v110, 0, 0x68u);
  v112 = 0;
  v113 = 0;
  memset(v111, 0, 0x48u);
  v114 = 0;
  v115 = 0;
  v8 = *(_DWORD *)(a1 + 120);
  if ( (v8 & 0x1000) != 0 )
  {
    if ( (v8 & 2) == 0 )
    {
      *(_BYTE *)(a1 + 35) = 1;
      return 3225485315LL;
    }
    *(_DWORD *)(a1 + 120) = v8 & 0xFFFFEFFF;
  }
  v98 = 6;
  v9 = 0;
  v10 = 0;
  v97 = 0;
  v90 = 0;
  v106 = 0;
  LOBYTE(v101) = 1;
  v108 = 0;
  v91 = 0;
  v89 = 0;
  v93 = 0;
  v95 = 0;
  if ( !*(_BYTE *)(a1 + 518) )
  {
    v92 = *(_DWORD *)(a1 + 448);
    v103 = *(_QWORD *)(a1 + 456);
    v105 = (int *)(a1 + 472);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v2 + 360);
    if ( ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v2 + 8)) )
      RxDowngradeFcbToSharedInMRx(a1, v2);
    if ( v92 == 1 )
    {
      v20 = 257;
      *(_DWORD *)(v4 + 54) = 3932224;
    }
    else
    {
      if ( v92 == 2 )
      {
        *(_DWORD *)(v4 + 54) = 3932228;
        LOWORD(v97) = 258;
        goto LABEL_48;
      }
      if ( v92 == 3 )
      {
        v20 = 260;
        *(_DWORD *)(v4 + 54) = 3932254;
      }
      else
      {
        if ( v92 != 12 )
        {
          if ( v92 == 37 )
          {
            *(_DWORD *)(v4 + 54) = 3932264;
            LOWORD(v97) = 262;
            if ( !*(_DWORD *)(v7 + 432) )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
              {
                goto LABEL_37;
              }
              v19 = 28;
              goto LABEL_36;
            }
          }
          else
          {
            if ( v92 != 38 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
              }
              v13 = -1073741496;
              v11 = v7;
              goto LABEL_24;
            }
            *(_DWORD *)(v4 + 54) = 3932240;
            LOWORD(v97) = 261;
            if ( !*(_DWORD *)(v7 + 432) )
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
              {
                goto LABEL_37;
              }
              v19 = 27;
LABEL_36:
              WPP_SF_qZ(
                v18->AttachedDevice,
                v19,
                (unsigned int)WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
                v7,
                v7 + 80);
LABEL_37:
              v13 = -1073741637;
              v11 = v7;
              goto LABEL_38;
            }
          }
LABEL_48:
          if ( *(_BYTE *)(a1 + 516) )
          {
            *(_WORD *)(v4 + 52) &= ~1u;
            MRxSmbDeallocateSideBuffer(a1, v4, "Restart");
          }
          v21 = *(_WORD *)(v4 + 52);
          if ( (v21 & 1) != 0 && (v21 & 0x220) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
            {
              WPP_SF_ZZdd(
                WPP_GLOBAL_Control->AttachedDevice,
                v21 & 0x200,
                (_DWORD)WPP_GLOBAL_Control,
                *(_QWORD *)(a1 + 56) + 360,
                v1 + 80,
                0,
                v21 & 0x20);
            }
            *(_BYTE *)(v4 + 28) = 1;
            v13 = -2147483642;
            *(_DWORD *)(v4 + 48) = -2147483642;
            *(_WORD *)(v4 + 52) &= ~0x20u;
            goto LABEL_56;
          }
          v22 = (_WORD *)(v1 + 80);
          if ( *(_WORD *)(v1 + 80)
            && !FsRtlDoesNameContainWildCards((PUNICODE_STRING)(v1 + 80))
            && (*(_BYTE *)(v4 + 52) & 1) == 0 )
          {
            v23 = *(_QWORD *)(a1 + 56);
            v24 = (unsigned __int16)*v22;
            P[0] = 0;
            P[1] = 0;
            v25 = *(unsigned __int16 *)(v23 + 360) + 2 + v24;
            if ( v25 > 0xFFFF )
            {
              v13 = -1073741811;
              goto LABEL_62;
            }
            WORD1(P[0]) = v25;
            LOWORD(P[0]) = v25;
            Pool2 = (void *)ExAllocatePool2(258, (unsigned __int16)v25, 1665428819);
            P[1] = Pool2;
            if ( !Pool2 )
            {
              v13 = -1073741670;
              goto LABEL_62;
            }
            memmove(Pool2, *(const void **)(v23 + 368), *(unsigned __int16 *)(v23 + 360));
            *((_WORD *)P[1] + ((unsigned __int64)*(unsigned __int16 *)(v23 + 360) >> 1)) = 92;
            memmove(
              (char *)P[1] + 2 * ((unsigned __int64)*(unsigned __int16 *)(v23 + 360) >> 1) + 2,
              *(const void **)(v1 + 88),
              (unsigned __int16)*v22);
            if ( (unsigned __int8)MRxSmbIsFileInfoCacheFound(a1, v111, &DirectoryFromCache, P) )
            {
              if ( !DirectoryFromCache )
              {
                DirectoryFromCache = MRxSmbQueryDirectoryFromCache(a1, v111);
                v13 = DirectoryFromCache;
                if ( DirectoryFromCache != -1073741802 )
                {
                  v27 = P[1];
                  *(_WORD *)(v4 + 52) |= 0x21u;
                  ExFreePoolWithTag(v27, 0);
                  goto LABEL_56;
                }
              }
            }
            ExFreePoolWithTag(P[1], 0);
            v2 = v102;
            LOWORD(v98) = 7;
            *(_WORD *)(v4 + 52) |= 0x200u;
          }
          v28 = *(unsigned __int16 *)(v4 + 52);
          v29 = 31;
          v30 = v92;
          v31 = v100;
          if ( (v28 & 1) != 0 || v92 != 3 )
            goto LABEL_90;
          v32 = *(_DWORD *)(v96 + 420);
          if ( (v32 & 0x10040020) != 0
            && *(_DWORD *)(v96 + 416) == 5
            && !*(_BYTE *)(v96 + 506)
            && !*(_QWORD *)(v4 + 16)
            && (v32 & 0x40000) != 0
            && (*(_DWORD *)(v100 + 72) & 4) == 0 )
          {
            if ( (*(_DWORD *)(v107 + 136) & 8) != 0 )
            {
LABEL_88:
              v30 = v92;
LABEL_90:
              if ( (v28 & 0x400) != 0 && *(_QWORD *)(v4 + 16) && v30 == 3 && *v22 == 2 && **(_WORD **)(v100 + 88) == 42 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                {
                  WPP_SF_ZZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    31,
                    (unsigned int)WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
                    *(_QWORD *)(a1 + 56) + 360,
                    (__int64)v22);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                {
                  WPP_SF_ZZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    32,
                    (unsigned int)WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
                    *(_QWORD *)(a1 + 56) + 360,
                    (__int64)v22);
                }
                MRxSmbInvalidateFullDirectoryCache(a1, v28, v15, v31);
              }
LABEL_102:
              if ( (*(_DWORD *)(v5 + 72) & 0x100000) != 0 )
              {
                IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v2 + 8));
                IsResourceAcquiredSharedLite = ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v2 + 8));
                v36 = IsResourceAcquiredSharedLite;
                if ( IsResourceAcquiredExclusiveLite || IsResourceAcquiredSharedLite )
                  RxReleaseFcbResourceInMRx(0);
                SmbCeReconnect(*(PVOID *)(*(_QWORD *)(v109 + 40) + 40LL));
                v13 = v37;
                if ( IsResourceAcquiredExclusiveLite || v36 )
                  RxAcquireExclusiveFcbResourceInMRx(0);
                if ( v13 )
                  goto LABEL_239;
                v29 = 31;
              }
              v11 = v96;
              v38 = *(_DWORD *)(v96 + 420);
              if ( (v38 & 0x10040020) == 0 )
              {
                v39 = v103;
                v40 = *(_DWORD *)(a1 + 472);
                result = MRxSmbCoreInformation(a1, (unsigned __int16)v97, v103, (int)a1 + 472, 0);
                if ( (int)result >= 0 )
                  return FsRtlValidateFileInformationBufferEx(
                           a1,
                           v92,
                           v39,
                           (unsigned int)(v40 - *(_DWORD *)(a1 + 472)),
                           0,
                           0,
                           result);
                return result;
              }
              if ( !*(_QWORD *)(v4 + 16) )
              {
                v43 = *(_DWORD *)(v96 + 416);
                v16 = (UNICODE_STRING *)v100;
                v45 = v38 >> 15;
                v44 = *(_DWORD *)(v96 + 420);
                LOBYTE(v45) = (v44 & 0x8000) != 0;
                v91 = 1;
                v101 = v45;
                if ( v43 == 5 )
                  v29 = 12;
                v10 = v43 != 5;
                v89 = v43 != 5;
                v46 = 0x4000 / v29;
                v17 = v98;
                v12 = v46 + 1;
                v93 = v46 + 1;
                if ( (v44 & 0x40000) != 0 && (*(_DWORD *)(v100 + 72) & 4) != 0 )
                {
                  LOWORD(v17) = v98 | 0x10;
                  v98 = v17;
                }
                if ( v43 != 5 )
                {
                  v101 = v45;
                  LOWORD(v17) = v17 & 0xFFFC;
                  v89 = v43 != 5;
                  v98 = v17;
                }
                goto LABEL_136;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
              }
              v41 = *(_DWORD *)(a1 + 472);
              v42 = MrxSmbUnalignedDirEntryCopyTail(a1, v92, v103, (int)a1 + 472, v4);
              v13 = v42;
              if ( v42 >= 0 )
              {
                v13 = FsRtlValidateFileInformationBufferEx(
                        a1,
                        v92,
                        v103,
                        (unsigned int)(v41 - *(_DWORD *)(a1 + 472)),
                        0,
                        0,
                        v42);
                if ( v13 >= 0 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                  {
                    WPP_SF_ZZ(
                      WPP_GLOBAL_Control->AttachedDevice,
                      34,
                      (unsigned int)WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
                      *(_QWORD *)(a1 + 56) + 360,
                      (__int64)v22);
                  }
                  if ( !*(_QWORD *)(v4 + 16) && (*(_WORD *)(v4 + 52) & 0x400) != 0 )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                    {
                      WPP_SF_ZZ(
                        WPP_GLOBAL_Control->AttachedDevice,
                        35,
                        (unsigned int)WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
                        *(_QWORD *)(a1 + 56) + 360,
                        (__int64)v22);
                    }
                    *(_WORD *)(v4 + 52) = *(_WORD *)(v4 + 52) & 0xFBDF | 0x20;
                  }
                  return (unsigned int)v13;
                }
              }
LABEL_62:
              v10 = 0;
              goto LABEL_63;
            }
            v15 = a1 + 472;
            if ( *(_DWORD *)(a1 + 472) <= 0x1000u )
            {
              if ( (v32 & 0x8000) != 0
                && *(_WORD *)(*(_QWORD *)(a1 + 56) + 360LL)
                && *v22 == 2
                && **(_WORD **)(v100 + 88) == 42
                && MRxSmbEnableOpDirCache )
              {
                v33 = *(_QWORD *)(a1 + 456);
                v95 = 1;
                if ( (unsigned __int8)MRxSmbIsFullDirectoryCached(a1, v33, v15, v4, (__int64)&DirectoryFromCache) )
                {
                  v13 = DirectoryFromCache;
                  goto LABEL_62;
                }
                goto LABEL_102;
              }
              goto LABEL_88;
            }
          }
          v30 = v92;
          goto LABEL_90;
        }
        v20 = 259;
        *(_DWORD *)(v4 + 54) = 524300;
      }
    }
    LOWORD(v97) = v20;
    goto LABEL_48;
  }
  v11 = v7;
  v92 = 0;
  v12 = 0;
  v103 = 0;
  v105 = 0;
  v13 = -1073741822;
  while ( 1 )
  {
    while ( 1 )
    {
      v16 = (UNICODE_STRING *)v100;
      LOWORD(v17) = v98;
      if ( v13 != -1073741802 )
      {
        if ( v13 != -1073741628 || (*(_DWORD *)(v11 + 420) & 0x10000000) == 0 || v9 >= 0xA )
          goto LABEL_248;
        ++MRxSmbWin95Retries;
        v90 = v9 + 1;
      }
LABEL_136:
      v47 = *(_WORD *)(v4 + 52);
      if ( (*(_BYTE *)(v107 + 136) & 8) != 0 && (v47 & 1) != 0 && *(_DWORD *)(v4 + 4) != *(_DWORD *)(v11 + 400) )
      {
        v47 &= ~1u;
        *(_WORD *)(v4 + 52) = v47;
      }
      if ( (v47 & 1) == 0 )
        break;
      if ( !*(_QWORD *)(v4 + 8) )
      {
        *(_BYTE *)(v4 + 28) = 1;
        v13 = -2147483642;
        *(_DWORD *)(v4 + 48) = -2147483642;
        *(_WORD *)(v4 + 52) = v47 & 0xFFDF;
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
        v10 = v89;
      }
      v13 = *(_DWORD *)(v4 + 48);
      if ( !v13 )
      {
        v99 = 2;
        v61 = *(_WORD **)(v4 + 8);
        *v61 = *(_WORD *)v4;
        v64 = 2;
        v61[1] = v12;
        if ( !v10 )
          v64 = v97;
        v57 = v89;
        v60 = &v114;
        v61[2] = v64;
        v63 = 8;
        v61[5] = v17;
        v62 = *(unsigned __int16 *)(*(_QWORD *)(v4 + 8) + 528LL);
        if ( v10 )
          v63 = 10;
        goto LABEL_172;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
        goto LABEL_25;
      }
LABEL_26:
      v9 = v90;
    }
    v48 = *(_QWORD *)(a1 + 56);
    v49 = v16 + 5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
    *(_DWORD *)(v4 + 48) = 0;
    DoesNameContainWildCards = FsRtlDoesNameContainWildCards(v49);
    *(_BYTE *)(v4 + 58) = DoesNameContainWildCards;
    if ( DoesNameContainWildCards )
      RtlUpcaseUnicodeString(v49, v49, 0);
    v99 = 1;
    v51 = *(unsigned __int16 *)(v48 + 360);
    Length = v49->Length;
    DirectoryFromCache = Length + v51 + 21;
    v53 = ExAllocatePool2(258, DirectoryFromCache, 1665428819);
    v106 = (PVOID)v53;
    if ( !v53 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
      }
      v13 = -1073741670;
      goto LABEL_254;
    }
    v54 = v53 + 12;
    v102 = v53 + 12;
    if ( (_BYTE)v101 )
    {
      memmove((void *)(v53 + 12), *(const void **)(v48 + 368), (unsigned int)v51);
      v55 = (_WORD *)(v54 + v51);
      if ( *(_WORD *)(v54 + v51 - 2) != 92 )
        *v55++ = 92;
      memmove(v55, v49->Buffer, Length);
      *(_WORD *)((char *)v55 + Length) = 0;
      v56 = Length + (_DWORD)v55 + 2;
      v57 = v89;
    }
    else
    {
      *(_OWORD *)P = 0;
      SmbPutUnicodeStringAsOemString(&v102, v48 + 360, &DirectoryFromCache);
      if ( *(_WORD *)(v48 + 360)
        && *(_WORD *)(*(_QWORD *)(v48 + 368) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v48 + 360) >> 1) - 2) == 92 )
      {
        --v102;
        ++DirectoryFromCache;
      }
      else
      {
        *(_BYTE *)(v102 - 1) = 92;
      }
      v57 = v89;
      if ( v89 )
      {
        RtlInitUnicodeString((PUNICODE_STRING)P, L"*.*");
        v49 = (UNICODE_STRING *)P;
      }
      SmbPutUnicodeStringAsOemString(&v102, v49, &DirectoryFromCache);
      v56 = v102;
    }
    v58 = v106;
    *((_WORD *)v106 + 1) = v93;
    v58[2] = v98;
    v59 = 2;
    *v58 = 22;
    if ( !v57 )
      v59 = v97;
    v58[3] = v59;
    v60 = &v112;
    *((_DWORD *)v58 + 2) = 0;
    v61 = v58;
    v62 = v56 - (_DWORD)v58;
    v63 = 10;
LABEL_172:
    if ( v91 )
      break;
    v65 = v103;
    v66 = *v105;
LABEL_178:
    v13 = SmbCeTransact(
            a1,
            (int)&RxDefaultTransactionOptions,
            (int)&v99,
            2,
            0,
            0,
            (__int64)v61,
            v62,
            (__int64)v60,
            v63,
            0,
            0,
            v65,
            v66,
            (__int64)v110);
    if ( v13 < 0 )
      goto LABEL_239;
    v68 = v105;
    v69 = *(_WORD *)(v4 + 52) | 1;
    v90 = 0;
    v70 = *v105;
    *(_WORD *)(v4 + 52) = v69;
    DirectoryFromCache = v70;
    *(_DWORD *)(v4 + 40) = v110[15];
    if ( v99 == 1 )
    {
      *(_WORD *)v4 = v112;
      *(_DWORD *)(v4 + 4) = v110[18];
      *(_WORD *)(v4 + 52) = v69 | 2;
      v71 = BYTE4(v112);
      v72 = WORD1(v112);
      v73 = v113;
    }
    else
    {
      v71 = BYTE2(v114);
      v72 = (unsigned __int16)v114;
      v73 = HIWORD(v114);
    }
    v74 = 0;
    if ( !v89 )
      v74 = v71;
    if ( !v13 && !v72 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
        v68 = v105;
      }
      v74 = 1;
      v13 = -2147483642;
    }
    v75 = v91;
    if ( v91 )
    {
      if ( !v74 )
        goto LABEL_197;
      goto LABEL_198;
    }
    if ( v74 )
      goto LABEL_194;
    v13 = FsRtlValidateFileInformationBufferEx(a1, v92, v103, (unsigned int)*v68, 0, 0, v13);
    if ( v13 >= 0 )
    {
      v68 = v105;
      v75 = 0;
LABEL_194:
      *v68 -= v110[15];
      if ( v74 )
      {
        *(_DWORD *)(v4 + 48) = -2147483642;
        goto LABEL_198;
      }
LABEL_197:
      if ( (v98 & 1) != 0 )
LABEL_198:
        *(_WORD *)(v4 + 52) &= ~2u;
      if ( (*(_BYTE *)(v4 + 52) & 2) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
            *(_QWORD *)(v4 + 8));
        }
        v76 = *(_QWORD *)(v4 + 8);
        if ( !v76 )
        {
          *(_QWORD *)(v4 + 8) = ExAllocatePool2(256, 530, 1665428819);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, 0);
          }
          v76 = *(_QWORD *)(v4 + 8);
          if ( !v76 )
            goto LABEL_247;
        }
        v67 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v76);
            v67 = &WPP_GLOBAL_Control;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              47,
              WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
              DirectoryFromCache,
              v110[15]);
            v67 = &WPP_GLOBAL_Control;
          }
        }
        if ( !v91 )
        {
          v77 = v73;
          v78 = v103;
          v79 = v103 + v77;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v79);
          }
          if ( (unsigned __int16)v97 >= 0x101u )
          {
            v80 = *(unsigned int *)(v79 + 4);
            *(_DWORD *)(v76 + 6) = v80;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids, v80);
            }
            v81 = *(unsigned int *)(*(unsigned __int16 *)(v4 + 56) + v79);
            if ( (unsigned int)v81 <= 0x200 )
            {
              v82 = (const void *)(v79 + *(unsigned __int16 *)(v4 + 54));
              if ( (unsigned __int64)v82 + v81 <= v78 + (unsigned __int64)DirectoryFromCache )
              {
                memmove((void *)(v76 + 12), v82, (unsigned int)v81);
                *(_BYTE *)(v76 + v81 + 12) = 0;
                *(_BYTE *)((unsigned int)(v81 + 1) + v76 + 12) = 0;
                *(_WORD *)(*(_QWORD *)(v4 + 8) + 528LL) = v81 + 14;
                goto LABEL_225;
              }
            }
            v13 = -1073741629;
LABEL_56:
            v11 = v96;
LABEL_24:
            v12 = v93;
LABEL_25:
            v10 = v89;
            goto LABEL_26;
          }
          goto LABEL_239;
        }
LABEL_228:
        if ( !v13 )
        {
          *(_DWORD *)(v4 + 32) = v72;
          *(_DWORD *)(v4 + 36) = 0;
          *(_BYTE *)(v4 + 28) = v74;
          if ( v95 )
          {
            v83 = *(_DWORD *)(v4 + 40);
            if ( v83 <= 0x1000 )
            {
              if ( v74 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                {
                  WPP_SF_Zldd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    v83,
                    (_DWORD)v67,
                    *(_QWORD *)(a1 + 56) + 360,
                    v83,
                    v74,
                    v72);
                }
                MRxSmbCacheFullDirectory(a1, *(_QWORD *)(a1 + 456), *(unsigned int *)(v4 + 40), v4);
                *(_WORD *)(v4 + 52) |= 0x400u;
              }
            }
          }
          v84 = v105;
          v85 = v103;
          v86 = *v105;
          v87 = MrxSmbUnalignedDirEntryCopyTail(a1, v92, v103, (_DWORD)v105, v4);
          v13 = v87;
          if ( v87 < 0 )
            goto LABEL_225;
          v13 = FsRtlValidateFileInformationBufferEx(a1, v92, v85, (unsigned int)(v86 - *v84), 0, 0, v87);
          goto LABEL_56;
        }
      }
      else if ( v75 )
      {
        goto LABEL_228;
      }
LABEL_239:
      v11 = v96;
LABEL_38:
      v10 = v89;
      v12 = v93;
      goto LABEL_26;
    }
LABEL_225:
    v10 = v89;
LABEL_63:
    v11 = v96;
    v9 = 0;
    v12 = v93;
  }
  if ( *(_QWORD *)(v4 + 16) )
  {
LABEL_176:
    v65 = v108;
    v66 = 0x4000;
    goto LABEL_178;
  }
  _MRxSmbAllocateSideBuffer(a1, v4);
  v108 = *(_QWORD *)(v4 + 16);
  if ( v108 )
  {
    *(_BYTE *)(v4 + 29) = v101;
    *(_BYTE *)(v4 + 30) = v57;
    goto LABEL_176;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
LABEL_247:
  v13 = -1073741670;
LABEL_248:
  if ( v106 )
    ExFreePoolWithTag(v106, 0);
  if ( v13 < 0 )
  {
    if ( v13 == -2147483642 && *(_BYTE *)(a1 + 519) )
      v13 = -1073741809;
LABEL_254:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        52,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        (unsigned int)v13);
    *(_DWORD *)(v4 + 48) = v13;
    MRxSmbDeallocateSideBuffer(a1, v4, "ErrOut");
    v88 = *(void **)(v4 + 8);
    if ( v88 )
    {
      ExFreePoolWithTag(v88, 0);
      *(_QWORD *)(v4 + 8) = 0;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002a430  push    rbp
0x14002a432  push    rbx
0x14002a433  push    rsi
0x14002a434  push    rdi
0x14002a435  push    r12
0x14002a437  push    r13
0x14002a439  push    r14
0x14002a43b  push    r15
0x14002a43d  lea     rbp, [rsp-108h]
0x14002a445  sub     rsp, 208h
0x14002a44c  mov     rax, cs:__security_cookie
0x14002a453  xor     rax, rsp
0x14002a456  mov     [rbp+140h+var_50], rax
0x14002a45d  mov     rsi, [rcx+40h]
0x14002a461  xor     edx, edx; Val
0x14002a463  mov     rbx, [rcx+38h]
0x14002a467  mov     r13, rcx
0x14002a46a  mov     [rbp+140h+var_1AC], edx
0x14002a46d  mov     edi, edx
0x14002a46f  mov     [rbp+140h+var_178], rbx
0x14002a473  mov     [rbp+140h+var_188], rsi
0x14002a477  test    rsi, rsi
0x14002a47a  jz      short loc_14002A480
0x14002a47c  mov     rdi, [rsi+38h]
0x14002a480  mov     r14, [rsi+20h]
0x14002a484  mov     r8d, 68h ; 'h'; Size
0x14002a48a  mov     [rbp+140h+var_138], r14
0x14002a48e  mov     rax, [r14+28h]
0x14002a492  mov     rcx, [rax+28h]
0x14002a496  mov     rax, [rcx+60h]
0x14002a49a  mov     [rbp+140h+var_190], dx
0x14002a49e  mov     [rbp+140h+var_148], rax
0x14002a4a2  mov     rax, [rbx+78h]
0x14002a4a6  mov     rcx, [rax+20h]
0x14002a4aa  mov     r12, [rcx+20h]
0x14002a4ae  lea     rcx, [rbp+140h+var_130]; void *
0x14002a4b2  mov     [rbp+140h+var_1A0], r12
0x14002a4b6  call    memset
0x14002a4bb  xor     eax, eax
0x14002a4bd  lea     rcx, [rbp+140h+var_C0]; void *
0x14002a4c4  xor     edx, edx; Val
0x14002a4c6  mov     [rbp+140h+var_70], rax
0x14002a4cd  mov     [rbp+140h+var_68], ax
0x14002a4d4  lea     r8d, [rax+48h]; Size
0x14002a4d8  call    memset
0x14002a4dd  xor     eax, eax
0x14002a4df  mov     [rbp+140h+var_60], rax
0x14002a4e6  mov     [rbp+140h+var_58], eax
0x14002a4ec  mov     eax, [r13+78h]
0x14002a4f0  bt      eax, 0Ch
0x14002a4f4  jnb     short loc_14002A502
0x14002a4f6  test    al, 2
0x14002a4f8  jz      short loc_14002A569
0x14002a4fa  btr     eax, 0Ch
0x14002a4fe  mov     [r13+78h], eax
0x14002a502  xor     r11d, r11d
0x14002a505  mov     [rbp+140h+var_194], 6
0x14002a50c  lea     r8, WPP_GLOBAL_Control
0x14002a513  mov     edx, r11d
0x14002a516  mov     r10b, r11b
0x14002a519  mov     [rbp+140h+var_198], r11d
0x14002a51d  mov     [rbp+140h+var_1BC], edx
0x14002a520  lea     r15d, [r11+1]
0x14002a524  mov     [rbp+140h+var_150], r11
0x14002a528  lea     ecx, [r11+0Ah]
0x14002a52c  mov     byte ptr [rbp+140h+var_180], r15b
0x14002a530  mov     [rbp+140h+var_140], r11
0x14002a534  mov     [rbp+140h+var_1B8], r11b
0x14002a538  mov     [rbp+140h+var_1C0], r11b
0x14002a53c  mov     [rbp+140h+var_1B0], r11d
0x14002a540  mov     [rbp+140h+var_1A8], r11b
0x14002a544  cmp     [r13+206h], r11b
0x14002a54b  jz      short loc_14002A578
0x14002a54d  mov     r14, r12
0x14002a550  mov     [rbp+140h+var_1B4], r11d
0x14002a554  mov     r12d, r11d
0x14002a557  mov     [rbp+140h+var_170], r11
0x14002a55b  mov     [rbp+140h+var_158], r11
0x14002a55f  mov     ebx, 0C0000002h
0x14002a564  jmp     loc_14002A67A
0x14002a569  mov     byte ptr [r13+23h], 1
0x14002a56e  mov     eax, 0C0410003h
0x14002a573  jmp     loc_14002B79B
0x14002a578  mov     eax, [r13+1C0h]
0x14002a57f  mov     [rbp+140h+var_1B4], eax
0x14002a582  mov     rax, [r13+1C8h]
0x14002a589  mov     [rbp+140h+var_170], rax
0x14002a58d  lea     rax, [r13+1D8h]
0x14002a594  mov     [rbp+140h+var_158], rax
0x14002a598  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a59f  cmp     rcx, r8
0x14002a5a2  jz      short loc_14002A5C9
0x14002a5a4  test    dword ptr [rcx+2Ch], 400h
0x14002a5ab  jz      short loc_14002A5C9
0x14002a5ad  mov     rcx, [rcx+18h]
0x14002a5b1  lea     r9, [rbx+168h]
0x14002a5b8  mov     edx, 1Ah
0x14002a5bd  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002a5c4  call    WPP_SF_Z
0x14002a5c9  mov     rcx, [rbx+8]; Resource
0x14002a5cd  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14002a5d4  nop     dword ptr [rax+rax+00h]
0x14002a5d9  xor     r11d, r11d
0x14002a5dc  test    al, al
0x14002a5de  jz      short loc_14002A5F5
0x14002a5e0  mov     rdx, rbx
0x14002a5e3  mov     rcx, r13
0x14002a5e6  call    cs:__imp_RxDowngradeFcbToSharedInMRx
0x14002a5ed  nop     dword ptr [rax+rax+00h]
0x14002a5f2  xor     r11d, r11d
0x14002a5f5  mov     ecx, [rbp+140h+var_1B4]
0x14002a5f8  sub     ecx, r15d
0x14002a5fb  jz      loc_14002A7A5
0x14002a601  sub     ecx, r15d
0x14002a604  jz      loc_14002A791
0x14002a60a  sub     ecx, r15d
0x14002a60d  jz      loc_14002A783
0x14002a613  sub     ecx, 9
0x14002a616  jz      loc_14002A775
0x14002a61c  sub     ecx, 19h
0x14002a61f  jz      loc_14002A738
0x14002a625  cmp     ecx, r15d
0x14002a628  jz      loc_14002A6C4
0x14002a62e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a635  lea     rax, WPP_GLOBAL_Control
0x14002a63c  cmp     rcx, rax
0x14002a63f  jz      short loc_14002A65F
0x14002a641  test    dword ptr [rcx+2Ch], 400h
0x14002a648  jz      short loc_14002A65F
0x14002a64a  mov     rcx, [rcx+18h]
0x14002a64e  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002a655  mov     edx, 1Dh
0x14002a65a  call    WPP_SF_
0x14002a65f  mov     ebx, 0C0000148h
0x14002a664  mov     r14, r12
0x14002a667  mov     r12d, [rbp+140h+var_1B0]
0x14002a66b  mov     r10b, [rbp+140h+var_1C0]
0x14002a66f  xor     r11d, r11d
0x14002a672  mov     edx, [rbp+140h+var_1BC]
0x14002a675  mov     ecx, 0Ah
0x14002a67a  mov     r9, [rbp+140h+var_188]
0x14002a67e  mov     esi, [rbp+140h+var_194]
0x14002a681  cmp     ebx, 0C0000016h
0x14002a687  jz      loc_14002AE6B
0x14002a68d  cmp     ebx, 0C00000C4h
0x14002a693  jnz     loc_14002B6FA
0x14002a699  test    dword ptr [r14+1A4h], 10000000h
0x14002a6a4  jz      loc_14002B6FA
0x14002a6aa  cmp     edx, ecx
0x14002a6ac  jnb     loc_14002B6FA
0x14002a6b2  add     edx, r15d
0x14002a6b5  add     cs:MRxSmbWin95Retries, r15d
0x14002a6bc  mov     [rbp+140h+var_1BC], edx
0x14002a6bf  jmp     loc_14002AE6B
0x14002a6c4  mov     eax, 105h
0x14002a6c9  mov     dword ptr [rdi+36h], 3C0050h
0x14002a6d0  mov     word ptr [rbp+140h+var_198], ax
0x14002a6d4  cmp     [r12+1B0h], r11d
0x14002a6dc  jnz     loc_14002A7B5
0x14002a6e2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a6e9  lea     rax, WPP_GLOBAL_Control
0x14002a6f0  cmp     rcx, rax
0x14002a6f3  jz      short loc_14002A723
0x14002a6f5  test    dword ptr [rcx+2Ch], 100h
0x14002a6fc  jz      short loc_14002A723
0x14002a6fe  mov     edx, 1Bh
0x14002a703  mov     rcx, [rcx+18h]
0x14002a707  lea     rax, [r12+50h]
0x14002a70c  mov     r9, r12
0x14002a70f  mov     [rsp+240h+var_220], rax
0x14002a714  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x14002a71b  call    WPP_SF_qZ
0x14002a720  xor     r11d, r11d
0x14002a723  mov     ebx, 0C00000BBh
0x14002a728  mov     r14, r12
0x14002a72b  mov     r10b, [rbp+140h+var_1C0]
0x14002a72f  mov     r12d, [rbp+140h+var_1B0]
0x14002a733  jmp     loc_14002A672
0x14002a738  mov     eax, 106h
0x14002a73d  mov     dword ptr [rdi+36h], 3C0068h
0x14002a744  mov     word ptr [rbp+140h+var_198], ax
0x14002a748  cmp     [r12+1B0h], r11d
0x14002a750  jnz     short loc_14002A7B5
0x14002a752  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a759  lea     rax, WPP_GLOBAL_Control
0x14002a760  cmp     rcx, rax
0x14002a763  jz      short loc_14002A723
0x14002a765  test    dword ptr [rcx+2Ch], 100h
0x14002a76c  jz      short loc_14002A723
0x14002a76e  mov     edx, 1Ch
0x14002a773  jmp     short loc_14002A703
0x14002a775  mov     eax, 103h
0x14002a77a  mov     dword ptr [rdi+36h], 8000Ch
0x14002a781  jmp     short loc_14002A7B1
0x14002a783  mov     eax, 104h
0x14002a788  mov     dword ptr [rdi+36h], 3C005Eh
0x14002a78f  jmp     short loc_14002A7B1
0x14002a791  mov     r12d, 102h
0x14002a797  mov     dword ptr [rdi+36h], 3C0044h
0x14002a79e  mov     word ptr [rbp+140h+var_198], r12w
0x14002a7a3  jmp     short loc_14002A7BB
0x14002a7a5  mov     eax, 101h
0x14002a7aa  mov     dword ptr [rdi+36h], 3C0040h
0x14002a7b1  mov     word ptr [rbp+140h+var_198], ax
0x14002a7b5  mov     r12d, 102h
0x14002a7bb  cmp     [r13+204h], r11b
0x14002a7c2  jz      short loc_14002A7E2
0x14002a7c4  mov     eax, 0FFFEh
0x14002a7c9  lea     r8, aRestart; "Restart"
0x14002a7d0  and     [rdi+34h], ax
0x14002a7d4  mov     rdx, rdi
0x14002a7d7  mov     rcx, r13
0x14002a7da  call    MRxSmbDeallocateSideBuffer
0x14002a7df  xor     r11d, r11d
0x14002a7e2  movzx   ecx, word ptr [rdi+34h]
0x14002a7e6  test    r15b, cl
0x14002a7e9  jz      short loc_14002A861
0x14002a7eb  mov     eax, 220h
0x14002a7f0  test    ax, cx
0x14002a7f3  jz      short loc_14002A861
0x14002a7f5  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a7fc  lea     rax, WPP_GLOBAL_Control
0x14002a803  cmp     r8, rax
0x14002a806  jz      short loc_14002A841
0x14002a808  mov     r9d, 200h
0x14002a80e  test    [r8+2Ch], r9d
0x14002a812  jz      short loc_14002A841
0x14002a814  mov     edx, ecx
0x14002a816  lea     rax, [rsi+50h]
0x14002a81a  and     edx, r9d
0x14002a81d  and     ecx, 20h
0x14002a820  mov     r9, [r13+38h]
0x14002a824  mov     dword ptr [rsp+240h+var_210], ecx
0x14002a828  add     r9, 168h
0x14002a82f  mov     rcx, [r8+18h]
0x14002a833  mov     dword ptr [rsp+240h+var_218], edx
0x14002a837  mov     [rsp+240h+var_220], rax
0x14002a83c  call    WPP_SF_ZZdd
0x14002a841  mov     eax, 80000006h
0x14002a846  mov     [rdi+1Ch], r15b
0x14002a84a  mov     ebx, eax
0x14002a84c  mov     [rdi+30h], eax
0x14002a84f  mov     eax, 0FFDFh
0x14002a854  and     [rdi+34h], ax
0x14002a858  mov     r14, [rbp+140h+var_1A0]
0x14002a85c  jmp     loc_14002A667
0x14002a861  lea     r15, [rsi+50h]
0x14002a865  cmp     [r15], r11w
0x14002a869  jz      loc_14002A9E4
0x14002a86f  mov     rcx, r15; Name
0x14002a872  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14002a879  nop     dword ptr [rax+rax+00h]
0x14002a87e  xor     r11d, r11d
0x14002a881  test    al, al
0x14002a883  jnz     loc_14002A9E4
0x14002a889  test    byte ptr [rdi+34h], 1
0x14002a88d  jnz     loc_14002A9E4
0x14002a893  mov     rbx, [r13+38h]
0x14002a897  movzx   edx, word ptr [r15]
0x14002a89b  mov     [rbp+140h+P], r11
0x14002a89f  mov     [rbp+140h+P+8], r11
0x14002a8a3  movzx   ecx, word ptr [rbx+168h]
0x14002a8aa  add     ecx, 2
0x14002a8ad  add     edx, ecx
0x14002a8af  cmp     edx, 0FFFFh
0x14002a8b5  jbe     short loc_14002A8D5
0x14002a8b7  mov     ebx, 0C000000Dh
0x14002a8bc  mov     r15d, 1
0x14002a8c2  mov     r10b, r11b
0x14002a8c5  mov     r14, [rbp+140h+var_1A0]
0x14002a8c9  mov     edx, r11d
0x14002a8cc  mov     r12d, [rbp+140h+var_1B0]
0x14002a8d0  jmp     loc_14002A675
0x14002a8d5  movzx   edx, dx
0x14002a8d8  mov     r8d, 63446D53h
0x14002a8de  mov     rcx, r12
0x14002a8e1  mov     word ptr [rbp+140h+P+2], dx
0x14002a8e5  mov     word ptr [rbp+140h+P], dx
0x14002a8e9  call    cs:__imp_ExAllocatePool2
0x14002a8f0  nop     dword ptr [rax+rax+00h]
0x14002a8f5  xor     r11d, r11d
0x14002a8f8  mov     [rbp+140h+P+8], rax
0x14002a8fc  test    rax, rax
0x14002a8ff  jnz     short loc_14002A908
0x14002a901  mov     ebx, 0C000009Ah
0x14002a906  jmp     short loc_14002A8BC
0x14002a908  movzx   r8d, word ptr [rbx+168h]; Size
0x14002a910  mov     rcx, rax; void *
0x14002a913  mov     rdx, [rbx+170h]; Src
0x14002a91a  call    memmove
0x14002a91f  movzx   ecx, word ptr [rbx+168h]
0x14002a926  mov     rax, [rbp+140h+P+8]
0x14002a92a  shr     rcx, 1
0x14002a92d  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x14002a933  movzx   ecx, word ptr [rbx+168h]
0x14002a93a  mov     rax, [rbp+140h+P+8]
0x14002a93e  movzx   r8d, word ptr [r15]; Size
0x14002a942  add     rax, 2
0x14002a946  mov     rdx, [r15+8]; Src
0x14002a94a  shr     rcx, 1
  ... truncated ...
```
