# CmsVolume::MakePageResident(CmsTransactionContext *,CmsBPlusTable *,SmsPage *,_SmsChecksumBlob *,_SmsPagingContext *,uchar)

- ea: `0x1c002e720`
- end: `0x1c002f925`
- name: `?MakePageResident@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAUSmsPage@@PEAU_SmsChecksumBlob@@PEAU_SmsPagingContext@@E@Z`
- size: `4613`
- prototype: `__int64 __fastcall(CmsVolume *__hidden this, struct CmsTransactionContext *, struct CmsBPlusTable *, struct SmsPage *, struct _SmsChecksumBlob *, struct _SmsPagingContext *, char)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c002e530`

## callees

- `0x1c002b8ec`
- `0x1c002bc48`
- `0x1c002dc84`
- `0x1c002e720`
- `0x1c0030504`
- `0x1c005b4ac`
- `0x1c005ca10`
- `0x1c0062950`
- `0x1c0068960`
- `0x1c0069ae4`
- `0x1c006ac80`
- `0x1c006af80`
- `0x1c00b30fc`
- `0x1c00b318c`
- `0x1c00b3fd4`
- `0x1c00b95cc`
- `0x1c00bb398`
- `0x1c00bc328`
- `0x1c00be570`
- `0x1c00be620`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002f709`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c002f709`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002f855`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c002f855`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f0a4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f1aa`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f2b0`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f3b0`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f673`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f0a4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f1aa`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f2b0`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f3b0`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c002f673`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c002ec7e`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c002ec7e`

## pseudocode

```c
__int64 __fastcall CmsVolume::MakePageResident(
        CmsVolume **this,
        struct CmsTransactionContext *a2,
        struct CmsBPlusTable *a3,
        struct SmsPage *a4,
        struct _SmsChecksumBlob *a5,
        struct _SmsPagingContext *a6,
        char a7)
{
  struct CmsBPlusTable *v8; // rdi
  struct CmsTransactionContext *v9; // rbx
  char v11; // r12
  unsigned int v12; // r15d
  _OWORD *v13; // rax
  _OWORD *v14; // rax
  _OWORD *v15; // rax
  __int64 v16; // rdx
  NTSTATUS MetadataChecksumClass; // r14d
  __int64 v18; // rdi
  union _LCN_TUPLE *v19; // r8
  __int128 v20; // xmm1
  CmsVolume *v21; // rcx
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // rax
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  CmsVolume *v27; // rcx
  __int64 v28; // rax
  struct _SCRUB_PARITY_EXTENT_DATA *v29; // rbx
  struct _SmsScrubIoOutput *v30; // rdi
  __int64 v31; // r8
  unsigned int v32; // r10d
  void *v33; // r11
  __int64 v34; // rdx
  struct _SCB *v35; // rdx
  unsigned int v36; // eax
  char v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r8
  struct CmsChecksum *v42; // r14
  int v43; // r12d
  _QWORD *v44; // rbx
  int v45; // r11d
  struct CmsTransactionCore *v46; // rdx
  __int128 *v47; // rcx
  unsigned int v48; // r9d
  __int64 *v49; // rsi
  __int64 v50; // r8
  __int64 v51; // rax
  CmsBPlusTable *v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r12
  __int64 v55; // r14
  __int64 v56; // r14
  int ActivityIdThread; // eax
  int v58; // edx
  __int64 v59; // rax
  CmsBPlusTable *v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r12
  __int64 v63; // r14
  __int64 v64; // r14
  int v65; // eax
  int v66; // edx
  __int64 v67; // rax
  CmsBPlusTable *v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // r12
  __int64 v71; // r14
  __int64 v72; // r14
  int v73; // eax
  int v74; // edx
  char v75; // r12
  __int64 v76; // rax
  CmsBPlusTable *v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r14
  __int64 v80; // rdi
  __int64 v81; // rdi
  int v82; // eax
  int v83; // edx
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  CmsVolume *v86; // rcx
  unsigned int v87; // ecx
  __int64 *v88; // rax
  int v89; // r12d
  unsigned int v90; // r14d
  _QWORD *v91; // r8
  __int128 *v92; // rcx
  unsigned int v93; // r10d
  __int64 *v94; // r9
  __int64 v95; // rdx
  __int128 *v96; // rax
  _QWORD *v97; // rdx
  __int64 v98; // r8
  struct CmsBPlusTable *v99; // r12
  struct CmsBPlusTable *v100; // rax
  __int64 v101; // rdx
  struct CmsTransactionContext *v102; // rbx
  struct CmsBPlusTable *v103; // rbx
  __int64 v104; // rdi
  __int64 v105; // rax
  __int64 v106; // rdx
  NTSTATUS v107; // edi
  BOOL v108; // edi
  char *PoolWithTag; // rax
  _BYTE *v110; // rbx
  struct CmsBPlusTable *v111; // rdx
  _DWORD *v112; // rax
  char v113; // cl
  struct CmsBPlusTable *v114; // rax
  __int64 v115; // rdx
  unsigned int *v116; // rbx
  struct _SmsChecksumBlob **v117; // rdi
  __int64 v118; // rsi
  struct CmsBPlusTable *v119; // r14
  union _LCN_TUPLE *v121; // [rsp+20h] [rbp-238h]
  unsigned __int8 v122; // [rsp+80h] [rbp-1D8h]
  bool v123; // [rsp+81h] [rbp-1D7h]
  unsigned int v124; // [rsp+84h] [rbp-1D4h]
  char v125; // [rsp+84h] [rbp-1D4h]
  char v126; // [rsp+84h] [rbp-1D4h]
  char v127; // [rsp+84h] [rbp-1D4h]
  unsigned int v128; // [rsp+88h] [rbp-1D0h]
  char v129; // [rsp+8Ch] [rbp-1CCh]
  unsigned __int8 v130[3]; // [rsp+8Dh] [rbp-1CBh] BYREF
  int v131; // [rsp+90h] [rbp-1C8h]
  struct _SmsPagingContext *v132; // [rsp+98h] [rbp-1C0h]
  struct SmsPage *v133; // [rsp+A0h] [rbp-1B8h]
  struct CmsBPlusTable *v134; // [rsp+A8h] [rbp-1B0h]
  CmsVolume *v135; // [rsp+B0h] [rbp-1A8h]
  struct CmsBPlusTable *v136; // [rsp+B8h] [rbp-1A0h]
  int v137; // [rsp+C0h] [rbp-198h] BYREF
  struct CmsTransactionContext *v138; // [rsp+C8h] [rbp-190h]
  struct _SmsChecksumBlob *v139[2]; // [rsp+D0h] [rbp-188h] BYREF
  struct CmsChecksum *v140; // [rsp+E0h] [rbp-178h] BYREF
  _OWORD v141[2]; // [rsp+F0h] [rbp-168h] BYREF
  _OWORD v142[2]; // [rsp+110h] [rbp-148h] BYREF
  _OWORD v143[2]; // [rsp+130h] [rbp-128h] BYREF
  _OWORD v144[2]; // [rsp+150h] [rbp-108h] BYREF
  _OWORD v145[2]; // [rsp+170h] [rbp-E8h] BYREF
  __int128 v146; // [rsp+190h] [rbp-C8h] BYREF
  _OWORD v147[2]; // [rsp+1A0h] [rbp-B8h] BYREF
  _OWORD v148[2]; // [rsp+1C0h] [rbp-98h] BYREF
  __int128 v149; // [rsp+1E0h] [rbp-78h] BYREF
  _OWORD v150[2]; // [rsp+1F0h] [rbp-68h] BYREF

  v8 = a3;
  v136 = a3;
  v9 = a2;
  v138 = a2;
  v135 = (CmsVolume *)this;
  v134 = a3;
  v133 = a4;
  v139[0] = a5;
  v132 = a6;
  v122 = 0;
  v11 = 0;
  v123 = 0;
  v130[0] = 0;
  v12 = 0;
  v140 = 0;
  v137 = 0;
  if ( !a7 )
  {
    MetadataChecksumClass = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *))qword_1C0136998)(
                              *((_QWORD *)a4 + 16),
                              (unsigned int)(*((_DWORD *)a4 + 80) << *((_DWORD *)this + 16)),
                              (char *)a4 + 528);
    v124 = MetadataChecksumClass;
    v128 = MetadataChecksumClass;
    v22 = *((_DWORD *)v132 + 40);
    v123 = (v22 & 2) != 0;
    if ( MetadataChecksumClass < 0 )
      goto LABEL_133;
    v122 = 1;
    if ( *((struct CmsBPlusTable **)v9 + 332) != v8
      || (v23 = *((_QWORD *)v9 + 333)) != 0
      && (v24 = *(unsigned __int8 *)(v23 + 6), (unsigned __int8)v24 < 0xAu)
      && *((_QWORD *)a4 + 1) == *(_QWORD *)(v23 + 8 * v24 + 16) )
    {
      if ( (v22 & 2) == 0 )
      {
LABEL_64:
        if ( MetadataChecksumClass < 0 )
        {
          memset(v145, 0, sizeof(v145));
          v146 = 0;
          if ( MetadataChecksumClass == -1073740688 && dword_1C012D0B4 == 1 )
          {
            if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
            {
              v125 = *((_QWORD *)v9 + 332) == (_QWORD)v8;
              v135 = this[230];
              v51 = *((_QWORD *)a4 + 16);
              v134 = *(struct CmsBPlusTable **)(v51 + 16);
              v133 = (struct SmsPage *)*((_QWORD *)a4 + 1);
              v132 = *(struct _SmsPagingContext **)(v51 + 32);
              v53 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)a4 + 15)) + 10);
              LOBYTE(v54) = 0;
              if ( v53 )
                v54 = *(_QWORD *)(v53 + 384);
              v55 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v52) + 10);
              if ( v55 )
                v56 = *(_QWORD *)(v55 + 376);
              else
                LODWORD(v56) = 0;
              ActivityIdThread = IoGetActivityIdThread();
              McTemplateK0iiiiiit_EtwWriteTransfer(
                (unsigned int)MinstoreEventProvider_Context,
                v58,
                ActivityIdThread,
                v56,
                v54,
                (char)v132,
                (char)v133,
                (char)v134,
                (char)v135,
                v125);
            }
            if ( dword_1C012D0B4 == 1 )
            {
              if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
              {
                v126 = *((_QWORD *)v9 + 332) == (_QWORD)v8;
                v135 = this[230];
                v59 = *((_QWORD *)a4 + 16);
                v134 = *(struct CmsBPlusTable **)(v59 + 16);
                v133 = (struct SmsPage *)*((_QWORD *)a4 + 2);
                v132 = *(struct _SmsPagingContext **)(v59 + 40);
                v61 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)a4 + 15)) + 10);
                LOBYTE(v62) = 0;
                if ( v61 )
                  v62 = *(_QWORD *)(v61 + 384);
                v63 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v60) + 10);
                if ( v63 )
                  v64 = *(_QWORD *)(v63 + 376);
                else
                  LODWORD(v64) = 0;
                v65 = IoGetActivityIdThread();
                McTemplateK0iiiiiit_EtwWriteTransfer(
                  (unsigned int)MinstoreEventProvider_Context,
                  v66,
                  v65,
                  v64,
                  v62,
                  (char)v132,
                  (char)v133,
                  (char)v134,
                  (char)v135,
                  v126);
              }
              if ( dword_1C012D0B4 == 1 )
              {
                if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
                {
                  v127 = *((_QWORD *)v9 + 332) == (_QWORD)v8;
                  v135 = this[230];
                  v67 = *((_QWORD *)a4 + 16);
                  v134 = *(struct CmsBPlusTable **)(v67 + 16);
                  v133 = (struct SmsPage *)*((_QWORD *)a4 + 3);
                  v132 = *(struct _SmsPagingContext **)(v67 + 48);
                  v69 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)a4 + 15)) + 10);
                  LOBYTE(v70) = 0;
                  if ( v69 )
                    v70 = *(_QWORD *)(v69 + 384);
                  v71 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v68) + 10);
                  if ( v71 )
                    v72 = *(_QWORD *)(v71 + 376);
                  else
                    LODWORD(v72) = 0;
                  v73 = IoGetActivityIdThread();
                  McTemplateK0iiiiiit_EtwWriteTransfer(
                    (unsigned int)MinstoreEventProvider_Context,
                    v74,
                    v73,
                    v72,
                    v70,
                    (char)v132,
                    (char)v133,
                    (char)v134,
                    (char)v135,
                    v127);
                }
                if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
                {
                  v75 = *((_QWORD *)v9 + 332) == (_QWORD)v8;
                  v135 = this[230];
                  v76 = *((_QWORD *)a4 + 16);
                  v134 = *(struct CmsBPlusTable **)(v76 + 16);
                  v133 = (struct SmsPage *)*((_QWORD *)a4 + 4);
                  v132 = *(struct _SmsPagingContext **)(v76 + 56);
                  v78 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)a4 + 15)) + 10);
                  LOBYTE(v79) = 0;
                  if ( v78 )
                    v79 = *(_QWORD *)(v78 + 384);
                  v80 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(v77) + 10);
                  if ( v80 )
                    v81 = *(_QWORD *)(v80 + 376);
                  else
                    LODWORD(v81) = 0;
                  v82 = IoGetActivityIdThread();
                  McTemplateK0iiiiiit_EtwWriteTransfer(
                    (unsigned int)MinstoreEventProvider_Context,
                    v83,
                    v82,
                    v81,
                    v79,
                    (char)v132,
                    (char)v133,
                    (char)v134,
                    (char)v135,
                    v75);
                }
              }
            }
          }
          v84 = *(_OWORD *)((char *)a4 + 8);
          v147[0] = v84;
          v85 = *(_OWORD *)((char *)a4 + 24);
          v147[1] = v85;
          if ( (*(_DWORD *)(*((_QWORD *)a4 + 15) + 16LL) & 0x8000000) != 0 )
          {
LABEL_103:
            v89 = *((_DWORD *)this + 16);
            v90 = 1;
            v91 = v145;
            v92 = &v146;
            if ( *(_QWORD *)&v147[0] )
            {
              *(_QWORD *)&v145[0] = *(_QWORD *)&v147[0];
              LODWORD(v146) = 1;
              v93 = 1;
              v94 = (__int64 *)v147 + 1;
              do
              {
                v95 = *v94;
                if ( !*v94 )
                  break;
                if ( v95 == *v91 + *(unsigned int *)v92 )
                {
                  ++*(_DWORD *)v92;
                }
                else
                {
                  ++v91;
                  v92 = (__int128 *)((char *)v92 + 4);
                  ++v90;
                  *v91 = v95;
                  *(_DWORD *)v92 = 1;
                }
                ++v93;
                ++v94;
              }
              while ( v93 < 4 );
              if ( v90 )
              {
                v96 = &v146;
                v97 = v145;
                v98 = v90;
                do
                {
                  *v97 <<= v89;
                  *(_DWORD *)v96 <<= v89;
                  ++v97;
                  v96 = (__int128 *)((char *)v96 + 4);
                  --v98;
                }
                while ( v98 );
              }
            }
            v99 = v136;
            v100 = CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v136 + 4));
            v121 = (union _LCN_TUPLE *)v145;
            MetadataChecksumClass = CmsVolume::SmartIoReadAndRepair(
                                      this,
                                      *(_QWORD *)(*(_QWORD *)(v101 + 48) + 72LL),
                                      *((_QWORD *)v100 + 10) + 376LL,
                                      0);
            v124 = MetadataChecksumClass;
            v128 = MetadataChecksumClass;
            v102 = v138;
            if ( MetadataChecksumClass >= 0 )
            {
              MetadataChecksumClass = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 15), v138, a4);
              v124 = MetadataChecksumClass;
              v128 = MetadataChecksumClass;
              if ( MetadataChecksumClass >= 0 && dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
              {
                v103 = (struct CmsBPlusTable *)*((_QWORD *)v102 + 332);
                v104 = *((_QWORD *)a4 + 1);
                v105 = IoGetActivityIdThread();
                LOBYTE(v121) = v103 == v99;
                McTemplateK0it_EtwWriteTransfer(MinstoreEventProvider_Context, v106, v105, v104);
                v102 = v138;
              }
            }
            v107 = MetadataChecksumClass;
            if ( MetadataChecksumClass < 0 )
            {
              v123 = 1;
              MetadataChecksumClass = -1073740688;
              v124 = -1073740688;
              v128 = -1073740688;
            }
            v108 = v107 >= 0;
            v131 = v108;
            v11 = 1;
            if ( qword_1C0136B28 && (v108 || (*((_BYTE *)v102 + 16) & 0x20) == 0) )
            {
              PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0xC8u, 0x6950534Du);
              v110 = PoolWithTag;
              v111 = v136;
              if ( PoolWithTag )
              {
                *(_DWORD *)PoolWithTag = 11;
                *((_QWORD *)PoolWithTag + 1) = this[6];
                *((_DWORD *)PoolWithTag + 4) = MetadataChecksumClass;
                *(_OWORD *)(PoolWithTag + 24) = *(_OWORD *)(*((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v111 + 4))
                                                            + 10)
                                                          + 376LL);
                v110[40] = v108;
                v110[41] = 1;
                v18 = 4;
                *((_WORD *)v110 + 21) = 4;
                *((_QWORD *)v110 + 6) = (char *)a4 + 8;
                v112 = (_DWORD *)*((_QWORD *)a4 + 16);
                if ( *v112 == 725766989 )
                {
                  *((_QWORD *)v110 + 7) = v112 + 8;
                  *((_QWORD *)v110 + 8) = *((_QWORD *)a4 + 16) + 64LL;
                  *((_DWORD *)v110 + 18) = **((_DWORD **)a4 + 16);
                  *((_QWORD *)v110 + 10) = *(_QWORD *)(*((_QWORD *)a4 + 16) + 16LL);
                  *((_DWORD *)v110 + 22) = *(_DWORD *)(*((_QWORD *)a4 + 16) + 12LL);
                  v113 = *(_BYTE *)(*((_QWORD *)a4 + 16) + 8LL);
                }
                else
                {
                  *((_QWORD *)v110 + 7) = 0;
                  *((_QWORD *)v110 + 8) = 0;
                  *((_DWORD *)v110 + 18) = 0;
                  *((_QWORD *)v110 + 10) = 0;
                  *((_DWORD *)v110 + 22) = 0;
                  v113 = 0;
                }
                v110[92] = v113;
                v110[93] = (*((_DWORD *)this + 779) & 0x40000000) != 0;
                *((_QWORD *)v110 + 12) = this[230];
              }
              else
              {
                v18 = 4;
              }
              v114 = CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v111 + 4));
              LOBYTE(v121) = v131;
              ((void (__fastcall *)(CmsVolume *, _QWORD, __int64, _QWORD))qword_1C0136B28)(
                this[6],
                *(_QWORD *)(*(_QWORD *)(v115 + 48) + 72LL),
                *((_QWORD *)v114 + 10) + 376LL,
                (unsigned int)MetadataChecksumClass);
              v11 = 1;
              if ( v110 )
                ExFreePoolWithTag(v110, 0);
              goto LABEL_37;
            }
          }
          else
          {
            v86 = this[381];
            v144[0] = v84;
            v144[1] = v85;
            LOBYTE(v121) = 0;
            MetadataChecksumClass = CmsVolumeContainer::PinContainerRange(v86, v9, v144, v147);
            v124 = MetadataChecksumClass;
            v128 = MetadataChecksumClass;
            v11 = 1;
            if ( MetadataChecksumClass >= 0 )
            {
              v87 = 0;
              v88 = (__int64 *)v147;
              while ( *v88 >= 0 )
              {
                ++v87;
                ++v88;
                if ( v87 >= 4 )
                  goto LABEL_103;
              }
              MetadataChecksumClass = -1073740688;
              v124 = -1073740688;
              v128 = -1073740688;
              goto LABEL_36;
            }
          }
        }
LABEL_133:
        v18 = 4;
        v16 = v122;
        goto LABEL_38;
      }
    }
    else
    {
      LOWORD(v131) = *(_WORD *)(*(_QWORD *)(v23 + 704) + 4LL);
      v129 = v22 & 1;
      *((_DWORD *)v132 + 40) = v22 & 0xFFFFFFEE;
      v123 = 1;
      v25 = *(_OWORD *)((char *)a4 + 8);
      v150[0] = v25;
      v26 = *(_OWORD *)((char *)a4 + 24);
      v150[1] = v26;
      if ( (*(_DWORD *)(*((_QWORD *)a4 + 15) + 16LL) & 0x8000000) == 0 )
      {
        v27 = this[381];
        v143[0] = v25;
        v143[1] = v26;
        LOBYTE(v121) = 0;
        MetadataChecksumClass = CmsVolumeContainer::PinContainerRange(v27, v9, v143, v150);
        v124 = MetadataChecksumClass;
        v128 = MetadataChecksumClass;
        v11 = 1;
        if ( MetadataChecksumClass < 0 )
          goto LABEL_133;
      }
      v28 = *((_QWORD *)v9 + 333);
      v29 = *(struct _SCRUB_PARITY_EXTENT_DATA **)(v28 + 704);
      v30 = *(struct _SmsScrubIoOutput **)(v28 + 696);
      v31 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v136 + 4)) + 10);
      v35 = *(struct _SCB **)(*(_QWORD *)(v34 + 48) + 72LL);
      v36 = v32 | 2;
      if ( (v37 & 8) == 0 )
        v36 = v32;
      MetadataChecksumClass = CmsVolume::SmartIoScrubPage(
                                (CmsVolume *)this,
                                v35,
                                (union _SmsBigIdentifier *)(v31 + 376),
                                (const union _LCN_TUPLE *)v150,
                                v33,
                                0,
                                v139[0],
                                v36,
                                v30,
                                v29,
                                0,
                                v130);
      v124 = MetadataChecksumClass;
      v128 = MetadataChecksumClass;
      v9 = v138;
      *(_QWORD *)(*((_QWORD *)v138 + 333) + 712LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v138 + 333) + 696LL) + 24LL);
      v11 = 1;
      if ( FsRtlIsTotalDeviceFailure(MetadataChecksumClass) )
        goto LABEL_133;
      if ( MetadataChecksumClass >= 0 )
      {
        v38 = *((_QWORD *)v9 + 333);
        if ( v38 )
        {
          v39 = *(unsigned __int8 *)(v38 + 6);
          if ( (unsigned __int8)v39 < 0xAu )
            *(_QWORD *)(v38 + 8 * v39 + 16) = *((_QWORD *)a4 + 1);
        }
      }
      if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v9 + 333) + 696LL))
        || *(_WORD *)(*(_QWORD *)(v41 + 704) + 4LL) > (unsigned __int16)v131 )
      {
        MsScrubContextCaptureError(v41, v40);
      }
      if ( !v130[0] || MetadataChecksumClass < 0 || v129 || (*((_DWORD *)v132 + 40) & 2) == 0 )
      {
        v11 = 1;
LABEL_36:
        v18 = 4;
LABEL_37:
        v16 = 1;
        goto LABEL_38;
      }
      v8 = v136;
    }
    MetadataChecksumClass = CmsChecksum::GetMetadataChecksumClass(*((_BYTE *)v139[0] + 2), &v140);
    v124 = MetadataChecksumClass;
    v128 = MetadataChecksumClass;
    if ( MetadataChecksumClass < 0 )
      goto LABEL_133;
    v42 = v140;
    (*(void (__fastcall **)(struct CmsChecksum *, _QWORD, _QWORD, int *))(*(_QWORD *)v140 + 56LL))(
      v140,
      *((_QWORD *)v9 + 4),
      *(unsigned int *)(*((_QWORD *)v9 + 4) + 3084LL),
      &v137);
    if ( *((_DWORD *)v139[0] + 1) != v137 )
    {
      MetadataChecksumClass = -1073740520;
      v124 = -1073740520;
      v128 = -1073740520;
      v18 = 4;
      LOBYTE(v16) = 1;
      goto LABEL_48;
    }
    LOBYTE(v121) = 0;
    MetadataChecksumClass = (*(__int64 (__fastcall **)(struct CmsChecksum *, CmsVolume **, _QWORD, _QWORD))(*(_QWORD *)v42 + 128LL))(
                              v42,
                              this,
                              *((_QWORD *)a4 + 16),
                              (unsigned int)(*((_DWORD *)a4 + 80) << *((_DWORD *)this + 16)));
    v124 = MetadataChecksumClass;
    v128 = MetadataChecksumClass;
    if ( MetadataChecksumClass >= 0 )
    {
      MetadataChecksumClass = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 15), v9, a4);
      v124 = MetadataChecksumClass;
      v128 = MetadataChecksumClass;
    }
    goto LABEL_64;
  }
  memset(*((void **)a4 + 16), 0, 0xA0u);
  v13 = (_OWORD *)*((_QWORD *)a4 + 16);
  v13[256] = 0;
  v13[257] = 0;
  v13[258] = 0;
  v13[259] = 0;
  v13[260] = 0;
  v14 = (_OWORD *)*((_QWORD *)a4 + 16);
  v14[512] = 0;
  v14[513] = 0;
  v14[514] = 0;
  v14[515] = 0;
  v14[516] = 0;
  v15 = (_OWORD *)*((_QWORD *)a4 + 16);
  v15[768] = 0;
  v15[769] = 0;
  v15[770] = 0;
  v15[771] = 0;
  v15[772] = 0;
  v132 = (struct _SmsPagingContext *)*((_QWORD *)CmsBPlusTable::BindableUnitTable(v8) + 10);
  CmsVolume::FormatPageHeader(this, *((_QWORD *)a4 + 16), (char *)a4 + 8, (char *)v132 + 376, 725766989);
  MetadataChecksumClass = ((__int64 (__fastcall *)(_QWORD, _QWORD, char *))qword_1C0136998)(
                            *((_QWORD *)a4 + 16),
                            (unsigned int)(*((_DWORD *)a4 + 80) << *((_DWORD *)this + 16)),
                            (char *)a4 + 528);
  v124 = MetadataChecksumClass;
  v128 = MetadataChecksumClass;
  if ( MetadataChecksumClass < 0 )
  {
    v18 = 4;
    LOBYTE(v16) = 0;
    goto LABEL_38;
  }
  v19 = (struct SmsPage *)((char *)a4 + 8);
  if ( (*(_DWORD *)(*((_QWORD *)a4 + 15) + 16LL) & 0x8000000) != 0 )
  {
    *(_OWORD *)((char *)a4 + 40) = *(_OWORD *)v19;
    *(_OWORD *)((char *)a4 + 56) = *(_OWORD *)((char *)a4 + 24);
  }
  else
  {
    MetadataChecksumClass = CmsVolumeContainer::SetContainerStationaryVolatile(
                              this[381],
                              v9,
                              v19,
                              1u,
                              (struct SmsPage *)((char *)a4 + 40));
    v124 = MetadataChecksumClass;
    v128 = MetadataChecksumClass;
    if ( MetadataChecksumClass < 0 )
    {
      v18 = 4;
      LOBYTE(v16) = 0;
      goto LABEL_38;
    }
    _InterlockedOr64((volatile signed __int64 *)a4 + 51, 0x4000000u);
    v138 = this[381];
    v20 = *(_OWORD *)((char *)a4 + 24);
    v141[0] = *(_OWORD *)((char *)a4 + 8);
    v141[1] = v20;
    LOBYTE(v121) = 1;
    MetadataChecksumClass = CmsVolumeContainer::PinContainerRange(v138, v9, v141, 0);
    v124 = MetadataChecksumClass;
    v128 = MetadataChecksumClass;
    if ( MetadataChecksumClass < 0 )
    {
      v18 = 4;
      LOBYTE(v16) = 0;
      goto LABEL_38;
    }
    v21 = this[381];
    v142[0] = *(_OWORD *)((char *)a4 + 8);
    v142[1] = *(_OWORD *)((char *)a4 + 24);
    CmsVolumeContainer::UnpinContainerRange(v21, v9, v142);
  }
  v16 = *((_QWORD *)v9 + 333);
  if ( v16 )
    *(_QWORD *)(v16 + 712) += (unsigned __int64)*((unsigned int *)a4 + 80) << *((_DWORD *)this + 16);
  v18 = 4;
  LOBYTE(v16) = 0;
LABEL_38:
  if ( MetadataChecksumClass >= 0 )
  {
    if ( v11 )
      CmsVolume::CleanBackingPage((CmsVolume *)this, (struct CmsTransactionCore *)v16, a4);
    _InterlockedOr64((volatile signed __int64 *)a4 + 51, 2u);
    return v128;
  }
LABEL_48:
  if ( (_BYTE)v16 )
  {
    ((void (__fastcall *)(_QWORD))qword_1C01369A0)(*((_QWORD *)a4 + 66));
    *((_QWORD *)a4 + 66) = 0;
  }
  if ( v123 )
  {
    memset(v148, 0, sizeof(v148));
    v149 = 0;
    v43 = 0;
    ((void (__fastcall *)(_QWORD, char *))qword_1C0136D48)(*((_QWORD *)a4 + 16), (char *)a4 + 144);
    v44 = (_QWORD *)((char *)a4 + 152);
    do
    {
      if ( *v44 )
      {
        ((void (*)(void))qword_1C01369E8)();
        *v44 = 0;
        *(v44 - 1) = 0;
        ++v43;
      }
      v44 += 4;
      --v18;
    }
    while ( v18 );
    if ( v43 )
    {
      _InterlockedAnd64((volatile signed __int64 *)a4 + 51, 0xFFFFFFFFFFFFFFFEuLL);
      ((void (__fastcall *)(_QWORD, _QWORD, char *))qword_1C0136D50)(
        *((_QWORD *)a4 + 16),
        *((_QWORD *)a4 + 17),
        (char *)a4 + 144);
      *((_QWORD *)a4 + 16) = 0;
      *((_QWORD *)a4 + 17) = 0;
      MetadataChecksumClass = v128;
      v124 = v128;
    }
    v45 = 1;
    v46 = (struct CmsTransactionCore *)v148;
    v47 = &v149;
    if ( *((_QWORD *)a4 + 1) )
    {
      *(_QWORD *)&v148[0] = *((_QWORD *)a4 + 1);
      LODWORD(v149) = 1;
      v48 = 1;
      v49 = (__int64 *)((char *)a4 + 16);
      do
      {
        v50 = *v49;
        if ( !*v49 )
          break;
        if ( v50 == *(_QWORD *)v46 + *(unsigned int *)v47 )
        {
          ++*(_DWORD *)v47;
        }
        else
        {
          v46 = (struct CmsTransactionCore *)((char *)v46 + 8);
          v47 = (__int128 *)((char *)v47 + 4);
          ++v45;
          *(_QWORD *)v46 = v50;
          *(_DWORD *)v47 = 1;
        }
        ++v48;
        ++v49;
      }
      while ( v48 < 4 );
      v12 = v45;
    }
    if ( v12 )
    {
      v116 = (unsigned int *)&v149;
      v117 = (struct _SmsChecksumBlob **)v148;
      v118 = v12;
      v119 = v136;
      do
      {
        v139[0] = *v117;
        v139[1] = (struct _SmsChecksumBlob *)*v116;
        CmsVolume::Purge((CmsVolume *)this, v46, v119, (const struct _RANGE *)v139, (unsigned __int8)v121);
        ++v117;
        ++v116;
        --v118;
      }
      while ( v118 );
      return v124;
    }
  }
  return (unsigned int)MetadataChecksumClass;
}

```

## disassembly

```asm
0x1c002e720  push    rbx
0x1c002e722  push    rsi
0x1c002e723  push    rdi
0x1c002e724  push    r12
0x1c002e726  push    r13
0x1c002e728  push    r14
0x1c002e72a  push    r15
0x1c002e72c  sub     rsp, 220h
0x1c002e733  mov     rax, cs:__security_cookie
0x1c002e73a  xor     rax, rsp
0x1c002e73d  mov     [rsp+258h+var_48], rax
0x1c002e745  mov     rsi, r9
0x1c002e748  mov     rdi, r8
0x1c002e74b  mov     [rsp+258h+var_1A0], r8
0x1c002e753  mov     rbx, rdx
0x1c002e756  mov     [rsp+258h+var_190], rdx
0x1c002e75e  mov     r13, rcx
0x1c002e761  mov     [rsp+258h+var_1A8], rcx
0x1c002e769  mov     [rsp+258h+var_1B0], r8
0x1c002e771  mov     [rsp+258h+var_1B8], r9
0x1c002e779  mov     rax, [rsp+258h+arg_20]
0x1c002e781  mov     [rsp+258h+var_188], rax
0x1c002e789  mov     rax, [rsp+258h+arg_28]
0x1c002e791  mov     [rsp+258h+var_1C0], rax
0x1c002e799  xor     al, al
0x1c002e79b  mov     [rsp+258h+var_1D8], al
0x1c002e7a2  xor     r12b, r12b
0x1c002e7a5  mov     [rsp+258h+var_1D7], al
0x1c002e7ac  mov     [rsp+258h+var_1CB], al
0x1c002e7b3  xor     r15d, r15d
0x1c002e7b6  mov     [rsp+258h+var_178], r15
0x1c002e7be  mov     [rsp+258h+var_198], r15d
0x1c002e7c6  cmp     [rsp+258h+arg_30], al
0x1c002e7cd  jz      loc_1C002EA5C
0x1c002e7d3  xor     edx, edx; Val
0x1c002e7d5  mov     r8d, 0A0h; Size
0x1c002e7db  mov     rcx, [r9+80h]; void *
0x1c002e7e2  call    memset
0x1c002e7e7  mov     rax, [rsi+80h]
0x1c002e7ee  xorps   xmm0, xmm0
0x1c002e7f1  movups  xmmword ptr [rax+1000h], xmm0
0x1c002e7f8  movups  xmmword ptr [rax+1010h], xmm0
0x1c002e7ff  movups  xmmword ptr [rax+1020h], xmm0
0x1c002e806  movups  xmmword ptr [rax+1030h], xmm0
0x1c002e80d  movups  xmmword ptr [rax+1040h], xmm0
0x1c002e814  mov     rax, [rsi+80h]
0x1c002e81b  movups  xmmword ptr [rax+2000h], xmm0
0x1c002e822  movups  xmmword ptr [rax+2010h], xmm0
0x1c002e829  movups  xmmword ptr [rax+2020h], xmm0
0x1c002e830  movups  xmmword ptr [rax+2030h], xmm0
0x1c002e837  movups  xmmword ptr [rax+2040h], xmm0
0x1c002e83e  mov     rax, [rsi+80h]
0x1c002e845  movups  xmmword ptr [rax+3000h], xmm0
0x1c002e84c  movups  xmmword ptr [rax+3010h], xmm0
0x1c002e853  movups  xmmword ptr [rax+3020h], xmm0
0x1c002e85a  movups  xmmword ptr [rax+3030h], xmm0
0x1c002e861  movups  xmmword ptr [rax+3040h], xmm0
0x1c002e868  mov     rcx, rdi; this
0x1c002e86b  call    ?BindableUnitTable@CmsBPlusTable@@QEAAPEAV1@XZ; CmsBPlusTable::BindableUnitTable(void)
0x1c002e870  mov     rcx, [rax+50h]
0x1c002e874  mov     [rsp+258h+var_1C0], rcx
0x1c002e87c  lea     r9, [rcx+178h]
0x1c002e883  mov     rdx, [rsi+80h]
0x1c002e88a  mov     dword ptr [rsp+258h+var_238], 2B42534Dh
0x1c002e892  lea     r8, [rsi+8]
0x1c002e896  mov     rcx, r13
0x1c002e899  call    ?FormatPageHeader@CmsVolume@@QEAAXPEAU_SmsPageHeader@@PEBT_LCN_TUPLE@@PEAT_SmsBigIdentifier@@W4_MS_PAGE_SIGNATURE@@@Z; CmsVolume::FormatPageHeader(_SmsPageHeader *,_LCN_TUPLE const *,_SmsBigIdentifier *,_MS_PAGE_SIGNATURE)
0x1c002e89e  mov     rax, cs:qword_1C0136998
0x1c002e8a5  lea     r8, [rsi+210h]
0x1c002e8ac  mov     ecx, [r13+40h]
0x1c002e8b0  mov     edx, [rsi+140h]
0x1c002e8b6  shl     edx, cl
0x1c002e8b8  mov     rcx, [rsi+80h]
0x1c002e8bf  call    cs:__guard_dispatch_icall_fptr
0x1c002e8c5  mov     r14d, eax
0x1c002e8c8  mov     [rsp+258h+var_1D4], eax
0x1c002e8cf  mov     [rsp+258h+var_1D0], eax
0x1c002e8d6  test    eax, eax
0x1c002e8d8  jns     short loc_1C002E8E5
0x1c002e8da  lea     edi, [r15+4]
0x1c002e8de  xor     dl, dl
0x1c002e8e0  jmp     loc_1C002ED22
0x1c002e8e5  lea     r8, [rsi+8]; union _LCN_TUPLE *
0x1c002e8e9  lea     rdx, [rsi+28h]
0x1c002e8ed  mov     rax, [rsi+78h]
0x1c002e8f1  mov     ecx, [rax+10h]
0x1c002e8f4  bt      rcx, 1Bh
0x1c002e8f9  jb      loc_1C002E9D4
0x1c002e8ff  mov     rcx, [r13+0BE8h]; this
0x1c002e906  mov     [rsp+258h+var_238], rdx; union _LCN_TUPLE *
0x1c002e90b  mov     r9b, 1; unsigned __int8
0x1c002e90e  mov     rdx, rbx; struct CmsTransactionContext *
0x1c002e911  call    ?SetContainerStationaryVolatile@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@E1@Z; CmsVolumeContainer::SetContainerStationaryVolatile(CmsTransactionContext *,_LCN_TUPLE *,uchar,_LCN_TUPLE *)
0x1c002e916  mov     r14d, eax
0x1c002e919  mov     [rsp+258h+var_1D4], eax
0x1c002e920  mov     [rsp+258h+var_1D0], eax
0x1c002e927  test    eax, eax
0x1c002e929  jns     short loc_1C002E937
0x1c002e92b  mov     edi, 4
0x1c002e930  xor     dl, dl
0x1c002e932  jmp     loc_1C002ED22
0x1c002e937  lock or qword ptr [rsi+198h], 4000000h
0x1c002e943  mov     rcx, [r13+0BE8h]
0x1c002e94a  mov     [rsp+258h+var_190], rcx
0x1c002e952  movups  xmm0, xmmword ptr [rsi+8]
0x1c002e956  movups  xmm1, xmmword ptr [rsi+18h]
0x1c002e95a  movaps  [rsp+258h+var_168], xmm0
0x1c002e962  movaps  [rsp+258h+var_158], xmm1
0x1c002e96a  mov     byte ptr [rsp+258h+var_238], 1
0x1c002e96f  xor     r9d, r9d
0x1c002e972  lea     r8, [rsp+258h+var_168]
0x1c002e97a  mov     rdx, rbx
0x1c002e97d  call    ?PinContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@T_LCN_TUPLE@@PEAT3@E@Z; CmsVolumeContainer::PinContainerRange(CmsTransactionContext *,_LCN_TUPLE,_LCN_TUPLE *,uchar)
0x1c002e982  mov     r14d, eax
0x1c002e985  mov     [rsp+258h+var_1D4], eax
0x1c002e98c  mov     [rsp+258h+var_1D0], eax
0x1c002e993  test    eax, eax
0x1c002e995  jns     short loc_1C002E9A3
0x1c002e997  mov     edi, 4
0x1c002e99c  xor     dl, dl
0x1c002e99e  jmp     loc_1C002ED22
0x1c002e9a3  mov     rcx, [r13+0BE8h]
0x1c002e9aa  movups  xmm0, xmmword ptr [rsi+8]
0x1c002e9ae  movaps  [rsp+258h+var_148], xmm0
0x1c002e9b6  movups  xmm1, xmmword ptr [rsi+18h]
0x1c002e9ba  movaps  [rsp+258h+var_138], xmm1
0x1c002e9c2  lea     r8, [rsp+258h+var_148]
0x1c002e9ca  mov     rdx, rbx
0x1c002e9cd  call    ?UnpinContainerRange@CmsVolumeContainer@@QEAAXPEAVCmsTransactionContext@@T_LCN_TUPLE@@@Z; CmsVolumeContainer::UnpinContainerRange(CmsTransactionContext *,_LCN_TUPLE)
0x1c002e9d2  jmp     short loc_1C002E9E4
0x1c002e9d4  movups  xmm0, xmmword ptr [r8]
0x1c002e9d8  movups  xmmword ptr [rdx], xmm0
0x1c002e9db  movups  xmm1, xmmword ptr [r8+10h]
0x1c002e9e0  movups  xmmword ptr [rdx+10h], xmm1
0x1c002e9e4  mov     rdx, [rbx+0A68h]
0x1c002e9eb  test    rdx, rdx
0x1c002e9ee  jz      short loc_1C002EA04
0x1c002e9f0  mov     eax, [rsi+140h]
0x1c002e9f6  mov     ecx, [r13+40h]
0x1c002e9fa  shl     rax, cl
0x1c002e9fd  add     [rdx+2C8h], rax
0x1c002ea04  mov     edi, 4
0x1c002ea09  xor     dl, dl
0x1c002ea0b  jmp     loc_1C002ED22
0x1c002ea10  mov     r14d, eax
0x1c002ea13  mov     [rsp+258h+var_1D4], eax
0x1c002ea1a  mov     [rsp+258h+var_1D0], eax
0x1c002ea21  xor     r15d, r15d
0x1c002ea24  lea     edi, [r15+4]
0x1c002ea28  movzx   edx, r15b
0x1c002ea2c  movzx   r12d, r15b
0x1c002ea30  mov     [rsp+258h+var_1D7], dl
0x1c002ea37  mov     rsi, [rsp+258h+var_1B8]
0x1c002ea3f  mov     rax, [rsp+258h+var_1B0]
0x1c002ea47  mov     [rsp+258h+var_1A0], rax
0x1c002ea4f  mov     r13, [rsp+258h+var_1A8]
0x1c002ea57  jmp     loc_1C002ED22
0x1c002ea5c  mov     rax, cs:qword_1C0136998
0x1c002ea63  lea     r8, [r9+210h]
0x1c002ea6a  mov     ecx, [rcx+40h]
0x1c002ea6d  mov     edx, [r9+140h]
0x1c002ea74  shl     edx, cl
0x1c002ea76  mov     rcx, [r9+80h]
0x1c002ea7d  call    cs:__guard_dispatch_icall_fptr
0x1c002ea83  mov     r14d, eax
0x1c002ea86  mov     [rsp+258h+var_1D4], eax
0x1c002ea8d  mov     [rsp+258h+var_1D0], eax
0x1c002ea94  mov     r10, [rsp+258h+var_1C0]
0x1c002ea9c  mov     r8d, [r10+0A0h]
0x1c002eaa3  mov     r9d, r8d
0x1c002eaa6  shr     r9d, 1
0x1c002eaa9  movzx   ecx, r9b
0x1c002eaad  and     cl, 1
0x1c002eab0  mov     [rsp+258h+var_1D7], cl
0x1c002eab7  test    eax, eax
0x1c002eab9  js      loc_1C002F866
0x1c002eabf  mov     [rsp+258h+var_1D8], 1
0x1c002eac7  cmp     [rbx+0A60h], rdi
0x1c002eace  jnz     loc_1C002ED51
0x1c002ead4  mov     rdx, [rbx+0A68h]
0x1c002eadb  test    rdx, rdx
0x1c002eade  jz      short loc_1C002EAF7
0x1c002eae0  movzx   eax, byte ptr [rdx+6]
0x1c002eae4  cmp     al, 0Ah
0x1c002eae6  jnb     short loc_1C002EAF7
0x1c002eae8  mov     rcx, [rsi+8]
0x1c002eaec  cmp     rcx, [rdx+rax*8+10h]
0x1c002eaf1  jz      loc_1C002ED51
0x1c002eaf7  mov     rax, [rdx+2C0h]
0x1c002eafe  movzx   eax, word ptr [rax+4]
0x1c002eb02  mov     word ptr [rsp+258h+var_1C8], ax
0x1c002eb0a  movzx   eax, r8b
0x1c002eb0e  and     al, 1
0x1c002eb10  mov     [rsp+258h+var_1CC], al
0x1c002eb17  and     r8d, 0FFFFFFEEh
0x1c002eb1b  mov     [r10+0A0h], r8d
0x1c002eb22  mov     [rsp+258h+var_1D7], 1
0x1c002eb2a  movups  xmm0, xmmword ptr [rsi+8]
0x1c002eb2e  movups  [rsp+258h+var_68], xmm0
0x1c002eb36  movups  xmm1, xmmword ptr [rsi+18h]
0x1c002eb3a  movups  [rsp+258h+var_58], xmm1
0x1c002eb42  mov     rax, [rsi+78h]
0x1c002eb46  mov     ecx, [rax+10h]
0x1c002eb49  bt      rcx, 1Bh
0x1c002eb4e  jb      short loc_1C002EBA0
0x1c002eb50  mov     rcx, [r13+0BE8h]
0x1c002eb57  movaps  [rsp+258h+var_128], xmm0
0x1c002eb5f  movaps  [rsp+258h+var_118], xmm1
0x1c002eb67  mov     byte ptr [rsp+258h+var_238], r12b
0x1c002eb6c  lea     r9, [rsp+258h+var_68]
0x1c002eb74  lea     r8, [rsp+258h+var_128]
0x1c002eb7c  mov     rdx, rbx
0x1c002eb7f  call    ?PinContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@T_LCN_TUPLE@@PEAT3@E@Z; CmsVolumeContainer::PinContainerRange(CmsTransactionContext *,_LCN_TUPLE,_LCN_TUPLE *,uchar)
0x1c002eb84  mov     r14d, eax
0x1c002eb87  mov     [rsp+258h+var_1D4], eax
0x1c002eb8e  mov     [rsp+258h+var_1D0], eax
0x1c002eb95  mov     r12b, 1
0x1c002eb98  test    eax, eax
0x1c002eb9a  js      loc_1C002F866
0x1c002eba0  mov     rax, [rbx+0A68h]
0x1c002eba7  mov     rbx, [rax+2C0h]
0x1c002ebae  mov     rdi, [rax+2B8h]
0x1c002ebb5  mov     r9d, [rax+280h]
0x1c002ebbc  mov     r10d, r9d
0x1c002ebbf  and     r10d, 1
0x1c002ebc3  mov     r11, [rsi+80h]
0x1c002ebca  mov     rdx, [rsp+258h+var_1A0]
0x1c002ebd2  mov     rdx, [rdx+20h]
0x1c002ebd6  mov     rcx, rdx; this
0x1c002ebd9  call    ?BindableUnitTable@CmsBPlusTable@@QEAAPEAV1@XZ; CmsBPlusTable::BindableUnitTable(void)
0x1c002ebde  mov     r8, [rax+50h]
0x1c002ebe2  mov     rax, [rdx+30h]
0x1c002ebe6  mov     rdx, [rax+48h]; struct _SCB *
0x1c002ebea  mov     eax, r10d
0x1c002ebed  or      eax, 2
0x1c002ebf0  and     r9b, 8
0x1c002ebf4  cmovz   eax, r10d
0x1c002ebf8  add     r8, 178h; union _SmsBigIdentifier *
0x1c002ebff  lea     rcx, [rsp+258h+var_1CB]
0x1c002ec07  mov     [rsp+258h+var_200], rcx; unsigned __int8 *
0x1c002ec0c  mov     [rsp+258h+var_208], r15b; unsigned __int8
0x1c002ec11  mov     [rsp+258h+var_210], rbx; struct _SCRUB_PARITY_EXTENT_DATA *
0x1c002ec16  mov     [rsp+258h+var_218], rdi; struct _SmsScrubIoOutput *
0x1c002ec1b  mov     [rsp+258h+var_220], eax; unsigned int
0x1c002ec1f  mov     rax, [rsp+258h+var_188]
0x1c002ec27  mov     [rsp+258h+var_228], rax; struct _SmsChecksumBlob *
0x1c002ec2c  mov     [rsp+258h+var_230], r15d; unsigned int
0x1c002ec31  mov     [rsp+258h+var_238], r11; unsigned __int8
0x1c002ec36  lea     r9, [rsp+258h+var_68]; union _LCN_TUPLE *
0x1c002ec3e  mov     rcx, r13; this
0x1c002ec41  call    ?SmartIoScrubPage@CmsVolume@@QEAAJPEAU_SCB@@PEAT_SmsBigIdentifier@@PEBT_LCN_TUPLE@@PEAXKPEAU_SmsChecksumBlob@@KPEAU_SmsScrubIoOutput@@PEAU_SCRUB_PARITY_EXTENT_DATA@@EPEAE@Z; CmsVolume::SmartIoScrubPage(_SCB *,_SmsBigIdentifier *,_LCN_TUPLE const *,void *,ulong,_SmsChecksumBlob *,ulong,_SmsScrubIoOutput *,_SCRUB_PARITY_EXTENT_DATA *,uchar,uchar *)
0x1c002ec46  mov     r14d, eax
0x1c002ec49  mov     [rsp+258h+var_1D4], eax
0x1c002ec50  mov     [rsp+258h+var_1D0], eax
0x1c002ec57  mov     rbx, [rsp+258h+var_190]
0x1c002ec5f  mov     rdx, [rbx+0A68h]
0x1c002ec66  mov     rax, [rdx+2B8h]
0x1c002ec6d  mov     rcx, [rax+18h]
0x1c002ec71  add     [rdx+2C8h], rcx
0x1c002ec78  mov     r12b, 1
0x1c002ec7b  mov     ecx, r14d; Status
0x1c002ec7e  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x1c002ec85  nop     dword ptr [rax+rax+00h]
0x1c002ec8a  test    al, al
0x1c002ec8c  jnz     loc_1C002F866
0x1c002ec92  test    r14d, r14d
0x1c002ec95  js      short loc_1C002ECB4
0x1c002ec97  mov     rdx, [rbx+0A68h]
0x1c002ec9e  test    rdx, rdx
0x1c002eca1  jz      short loc_1C002ECB4
0x1c002eca3  movzx   eax, byte ptr [rdx+6]
0x1c002eca7  cmp     al, 0Ah
0x1c002eca9  jnb     short loc_1C002ECB4
0x1c002ecab  mov     rcx, [rsi+8]
0x1c002ecaf  mov     [rdx+rax*8+10h], rcx
0x1c002ecb4  mov     r8, [rbx+0A68h]
0x1c002ecbb  mov     rcx, [r8+2B8h]
0x1c002ecc2  call    MsScrubIoFoundError
0x1c002ecc7  test    al, al
0x1c002ecc9  jnz     short loc_1C002ECE0
0x1c002eccb  mov     rax, [r8+2C0h]
0x1c002ecd2  movzx   edx, word ptr [rsp+258h+var_1C8]
0x1c002ecda  cmp     [rax+4], dx
0x1c002ecde  jbe     short loc_1C002ECEB
0x1c002ece0  mov     rdx, rcx
0x1c002ece3  mov     rcx, r8
0x1c002ece6  call    MsScrubContextCaptureError
0x1c002eceb  cmp     [rsp+258h+var_1CB], r15b
0x1c002ecf3  jz      short loc_1C002ED16
0x1c002ecf5  test    r14d, r14d
0x1c002ecf8  js      short loc_1C002ED16
0x1c002ecfa  cmp     [rsp+258h+var_1CC], r15b
0x1c002ed02  jnz     short loc_1C002ED16
0x1c002ed04  mov     rax, [rsp+258h+var_1C0]
0x1c002ed0c  mov     eax, [rax+0A0h]
0x1c002ed12  test    al, 2
0x1c002ed14  jnz     short loc_1C002ED5D
0x1c002ed16  mov     r12b, 1
0x1c002ed19  mov     edi, 4
0x1c002ed1e  movzx   edx, r12b; struct CmsTransactionCore *
  ... truncated ...
```
