# CmsVolume::PinSinglePageWorker(CmsTransactionContext *,_SmsView *,_LCN_TUPLE const *,ulong,ulong,ushort *,_SmsChecksumBlob *,_SmsPageHeader * *,SmsPage * *,uchar *,uchar *,SmsPage * *)

- ea: `0x1c0017a30`
- end: `0x1c0018e18`
- name: `?PinSinglePageWorker@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsView@@PEBT_LCN_TUPLE@@KKPEAGPEAU_SmsChecksumBlob@@PEAPEAU_SmsPageHeader@@PEAPEAUSmsPage@@PEAE76@Z`
- size: `5096`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct _SmsView *, const union _LCN_TUPLE *, unsigned int, unsigned int, unsigned __int16 *, struct _SmsChecksumBlob *, struct _SmsPageHeader **, struct SmsPage **, unsigned __int8 *, unsigned __int8 *, struct SmsPage **)`
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0017350`
- `0x1c0032c14`

## callees

- `0x1c0002b40`
- `0x1c0017a30`
- `0x1c001953c`
- `0x1c0019730`
- `0x1c0019910`
- `0x1c0019b60`
- `0x1c001afd4`
- `0x1c001d31c`
- `0x1c001db20`
- `0x1c002b8ec`
- `0x1c0036a10`
- `0x1c0043c44`
- `0x1c0043fac`
- `0x1c0044070`
- `0x1c0044550`
- `0x1c00446d4`
- `0x1c00581b0`
- `0x1c0059bb8`
- `0x1c005b360`
- `0x1c005b4ac`
- `0x1c005ca10`
- `0x1c005fa4c`
- `0x1c006551c`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c00b30fc`
- `0x1c00b318c`
- `0x1c00b5fe8`
- `0x1c00b6970`
- `0x1c00b6998`
- `0x1c00b75bc`
- `0x1c00bc328`
- `0x1c00be4d0`
- `0x1c00bebd0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00188ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0018c28`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0018d2c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00188ea`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0018c28`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0018d2c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0075bb3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0075bb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0075a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0075b10`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0075a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0075b10`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018979`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018cb7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018db3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018979`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018cb7`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0018db3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c0017d58`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001835d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001880c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c0018a38`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c0017d58`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001835d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c001880c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1c0018a38`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0018a56`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0018bdc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0075d97`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0076229`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0018a56`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0018bdc`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0075d97`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c0076229`
- `ntoskrnl!KeInitializeEvent` at `0x1c0017b51`
- `ntoskrnl!KeInitializeEvent` at `0x1c00182e0`
- `ntoskrnl!KeInitializeEvent` at `0x1c0017b51`
- `ntoskrnl!KeInitializeEvent` at `0x1c00182e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0018cde`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c007619b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0018cde`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c007619b`
- `ntoskrnl!KeClearEvent` at `0x1c00188c2`
- `ntoskrnl!KeClearEvent` at `0x1c00188c2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0017f3e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0017f6a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00187af`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0017f3e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c0017f6a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1c00187af`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0075de8`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0075e47`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0075de8`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0075e47`
- `ntoskrnl!KeSetEvent` at `0x1c001894d`
- `ntoskrnl!KeSetEvent` at `0x1c0018c8b`
- `ntoskrnl!KeSetEvent` at `0x1c0018d8b`
- `ntoskrnl!KeSetEvent` at `0x1c001894d`
- `ntoskrnl!KeSetEvent` at `0x1c0018c8b`
- `ntoskrnl!KeSetEvent` at `0x1c0018d8b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001814d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0075b82`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001814d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0075b82`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c00182c8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1c00182c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00180e0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00180e0`

## pseudocode

```c
__int64 __fastcall CmsVolume::PinSinglePageWorker(
        unsigned __int64 this,
        struct CmsTransactionContext *a2,
        struct _SmsView *a3,
        const union _LCN_TUPLE *a4,
        unsigned int a5,
        __int16 a6,
        unsigned __int16 *a7,
        struct _SmsChecksumBlob *a8,
        struct _SmsPageHeader **a9,
        struct SmsPage **a10,
        unsigned __int8 *a11,
        unsigned __int8 *a12,
        struct SmsPage **a13)
{
  struct CmsTransactionContext *v13; // r14
  unsigned __int64 v15; // rax
  SmsPage *v16; // rbx
  unsigned __int64 v17; // rdx
  int v18; // esi
  __int64 v19; // rcx
  CmsHashTable *v20; // rcx
  struct SmsHashEntry *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  bool v25; // r15
  bool v26; // r10
  unsigned __int16 *v27; // rax
  unsigned __int16 v28; // r12
  int v29; // esi
  int v30; // r8d
  char v31; // r15
  CmsBPlusTable *v32; // rdi
  int v33; // esi
  BOOLEAN v34; // r15
  struct _ERESOURCE *v35; // rcx
  char v36; // al
  _DWORD *v37; // rax
  char v38; // r9
  int v39; // eax
  __int64 v40; // rax
  struct CmsVolume *v41; // r12
  __int64 v42; // rdx
  struct _SmsPageHeader **v43; // rcx
  BOOLEAN v45; // al
  bool v46; // cl
  unsigned __int64 v47; // rdx
  __int64 v48; // rax
  unsigned int v49; // eax
  unsigned __int64 v50; // rsi
  ULONG CurrentProcessorNumber; // eax
  unsigned int v52; // ecx
  struct _SmsLookaside **v53; // rdi
  struct _PAGED_LOOKASIDE_LIST *v54; // rcx
  _QWORD *PoolWithTag; // r10
  bool v56; // zf
  int *v57; // r10
  unsigned int v58; // eax
  unsigned __int64 *v59; // r11
  unsigned __int16 v60; // r9
  __int64 *v61; // rax
  __int64 v62; // rdx
  char *v63; // rcx
  __int128 v64; // xmm0
  __int128 v65; // xmm0
  unsigned __int64 *v66; // rsi
  char *v67; // rdi
  int v68; // eax
  struct SmsHashEntry *v69; // rdx
  struct SmsPage *v70; // rax
  struct _ERESOURCE *v71; // rcx
  CmsHashTable *v72; // rcx
  CmsHashTable *v73; // r15
  struct SmsPage *v74; // rax
  unsigned __int64 v75; // rsi
  __int64 v76; // rdi
  struct SmsHashEntry *v77; // rax
  SmsHashEntry *v78; // rdi
  void *v79; // r15
  unsigned __int64 v80; // r8
  CmsHashTable *v81; // rdx
  _DWORD *v82; // rdx
  char v83; // dl
  __int64 v84; // r15
  __int64 v85; // rax
  CmsHashTable *v86; // r10
  signed __int32 v87; // eax
  unsigned __int64 v88; // rdx
  struct SmsHashEntry *v89; // rax
  struct CmsTransactionCore *v90; // rdx
  __int64 v91; // rdx
  int v92; // eax
  __int64 v93; // rax
  signed __int64 v94; // rax
  char v95; // al
  char v96; // r9
  _QWORD *v97; // rax
  struct CmsBPlusTable *v98; // rax
  __int64 v99; // r9
  __int64 v100; // rcx
  struct SmsHashEntry *v101; // rdx
  struct SmsHashEntry *v102; // rax
  struct SmsHashEntry **v103; // rdx
  unsigned __int32 v104; // ecx
  unsigned int v105; // r8d
  int v106; // eax
  __int64 v107; // rdx
  char v108; // r11
  unsigned __int8 *v109; // r15
  unsigned __int8 *v110; // rax
  unsigned __int16 v111; // di
  unsigned __int16 v112; // r13
  CmsVolume *v113; // rsi
  __int16 v114; // bx
  unsigned int v115; // r9d
  struct _SmsPageHeader **v116; // rcx
  __int64 v117; // rcx
  struct _ERESOURCE *v118; // r8
  CmsVolume *v119; // rcx
  __int64 v120; // rcx
  struct SmsHashEntry *v121; // rdx
  struct SmsHashEntry *v122; // rax
  struct SmsHashEntry **v123; // rdx
  __int64 v124; // rcx
  SmsHashEntry *v125; // rax
  __int64 *v126; // rdi
  __int64 **v127; // rax
  __int64 v128; // rdx
  int v129; // eax
  int v130; // edx
  int v131; // eax
  SIZE_T v132; // rsi
  __int16 v133; // ax
  CmsVolume *v134; // rcx
  __int64 v135; // r14
  char v136; // si
  int v137; // edi
  int ActivityIdThread; // eax
  int v139; // edx
  __int64 v140; // r14
  char v141; // si
  int v142; // edi
  int v143; // eax
  int v144; // edx
  __int64 v145; // rdx
  int v146; // eax
  int v147; // edx
  __int64 v148; // rdx
  __int64 v149; // rax
  __int128 v150; // xmm0
  __int128 v151; // xmm1
  __int64 v152; // rax
  unsigned __int16 v153; // r15
  __int64 v154; // rcx
  __int64 v155; // rax
  struct _SCRUB_PARITY_EXTENT_DATA *v156; // rdi
  struct _SmsScrubIoOutput *v157; // rsi
  __int64 v158; // r8
  unsigned int v159; // r10d
  void *v160; // r11
  __int64 v161; // rdx
  struct _SCB *v162; // rdx
  unsigned int v163; // eax
  char v164; // r9
  int v165; // eax
  __int64 v166; // rdx
  __int64 v167; // rax
  __int64 v168; // rcx
  __int64 v169; // r8
  __int64 v170; // rax
  __int64 v171; // r15
  struct _SmsHashLocation *v172; // [rsp+38h] [rbp-C8h]
  struct _SmsHashLocation *v173; // [rsp+38h] [rbp-C8h]
  struct SmsHashEntry **v174; // [rsp+40h] [rbp-C0h]
  struct SmsHashEntry **v175; // [rsp+40h] [rbp-C0h]
  bool v176; // [rsp+60h] [rbp-A0h]
  bool v177; // [rsp+60h] [rbp-A0h]
  bool v178; // [rsp+60h] [rbp-A0h]
  char i; // [rsp+60h] [rbp-A0h]
  int v180; // [rsp+64h] [rbp-9Ch]
  int v181; // [rsp+64h] [rbp-9Ch]
  char v182; // [rsp+68h] [rbp-98h]
  bool v183; // [rsp+69h] [rbp-97h]
  char v184; // [rsp+6Ah] [rbp-96h]
  char v185; // [rsp+6Bh] [rbp-95h] BYREF
  char v186; // [rsp+6Ch] [rbp-94h]
  char v187; // [rsp+6Dh] [rbp-93h]
  int v188; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v189; // [rsp+78h] [rbp-88h]
  struct SmsPage *v190; // [rsp+80h] [rbp-80h] BYREF
  int v191; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v192; // [rsp+90h] [rbp-70h]
  struct SmsHashEntry *v193; // [rsp+98h] [rbp-68h]
  SmsHashEntry *v194; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v195; // [rsp+A8h] [rbp-58h]
  CmsHashTable *v196; // [rsp+B0h] [rbp-50h]
  int v197; // [rsp+B8h] [rbp-48h]
  struct SmsHashEntry *v198; // [rsp+C0h] [rbp-40h]
  void *v199; // [rsp+C8h] [rbp-38h]
  struct CmsVolume *v200; // [rsp+D0h] [rbp-30h]
  int v201; // [rsp+D8h] [rbp-28h]
  struct SmsHashEntry *v202; // [rsp+E0h] [rbp-20h] BYREF
  struct SmsHashEntry *v203; // [rsp+E8h] [rbp-18h] BYREF
  int v204; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v205[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v206; // [rsp+108h] [rbp+8h]
  struct CmsTransactionContext *v207; // [rsp+110h] [rbp+10h]
  struct _SmsChecksumBlob *v208; // [rsp+118h] [rbp+18h]
  struct SmsPage **v209; // [rsp+120h] [rbp+20h]
  struct _SmsPageHeader **v210; // [rsp+128h] [rbp+28h]
  int v211; // [rsp+130h] [rbp+30h]
  int v212; // [rsp+134h] [rbp+34h]
  unsigned __int64 *v213; // [rsp+138h] [rbp+38h]
  int v214; // [rsp+140h] [rbp+40h]
  _DWORD v215[5]; // [rsp+144h] [rbp+44h] BYREF
  __int128 v216; // [rsp+158h] [rbp+58h] BYREF
  __int128 v217; // [rsp+168h] [rbp+68h]
  struct SmsPage *v218; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v219[5]; // [rsp+188h] [rbp+88h] BYREF
  bool v220; // [rsp+1B0h] [rbp+B0h]
  bool v221; // [rsp+1B1h] [rbp+B1h]
  _BYTE v222[6]; // [rsp+1B2h] [rbp+B2h] BYREF
  __int128 v223; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v224; // [rsp+1C8h] [rbp+C8h]
  __int128 v225; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v226; // [rsp+1E0h] [rbp+E0h]
  _QWORD v227[5]; // [rsp+1E8h] [rbp+E8h] BYREF
  _OWORD v228[2]; // [rsp+210h] [rbp+110h] BYREF
  int v229; // [rsp+230h] [rbp+130h] BYREF
  __int64 v230; // [rsp+238h] [rbp+138h]
  int v231; // [rsp+240h] [rbp+140h]
  SmsPage *v232; // [rsp+248h] [rbp+148h]
  PVOID P; // [rsp+250h] [rbp+150h]
  char v234; // [rsp+258h] [rbp+158h]
  int v235; // [rsp+25Ch] [rbp+15Ch]
  char v236; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v237[2]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v13 = a2;
  v208 = a8;
  v210 = a9;
  v209 = a10;
  v207 = a2;
  v192 = a11;
  v196 = a4;
  v200 = (struct CmsVolume *)this;
  v195 = a7;
  LOBYTE(this) = (a6 & 4) != 0;
  v189 = a12;
  LOWORD(v188) = 0;
  v191 = 0;
  v184 = 0;
  v182 = 0;
  v183 = 0;
  v186 = this;
  v197 = a6 & 1;
  v201 = a6 & 8;
  v204 = a6 & 0x80;
  if ( a13 && *a13 )
  {
    *a12 = 0;
    v16 = *a13;
    v188 = 0;
    v26 = (a6 & 4) != 0;
    v187 = 1;
    goto LABEL_54;
  }
  *a12 = 0;
  v187 = 0;
  memset(v227, 0, 32);
  KeInitializeEvent((PRKEVENT)&v227[1], NotificationEvent, 0);
  P = &v236;
  v15 = *(_QWORD *)a3;
  v16 = 0;
  v202 = 0;
  v17 = *(_QWORD *)v196;
  v18 = -1073741772;
  v19 = *(_QWORD *)(v15 + 32);
  v235 = 64;
  v234 = 0;
  v20 = (CmsHashTable *)(*(_QWORD *)(v19 + 48) + 16LL);
  v224 = 0;
  v223 = 0;
  v180 = -1073741772;
  v21 = CmsHashTable::FindAndLockEntryInternal(
          v20,
          v17,
          0,
          0,
          *((_QWORD *)v20 + 3) != 0,
          (struct _SmsHashLocation *)&v223,
          &v202,
          v172,
          v174);
  if ( !v21 )
    goto LABEL_262;
  v22 = *((_QWORD *)v21 + 1);
  if ( (*(_BYTE *)(v22 + 8) & 0x40) != 0 )
  {
    v229 = 12;
    v230 = v22 + 12;
    v231 = *(unsigned __int16 *)(v22 + 10);
    v232 = (SmsPage *)v22;
  }
  else
  {
    v229 = *(unsigned __int16 *)(v22 + 6);
    v230 = v22 + *(unsigned __int16 *)(v22 + 4);
    v231 = *(_DWORD *)(v22 + 12);
    v232 = (SmsPage *)(v22 + *(unsigned __int16 *)(v22 + 10));
  }
  v18 = AddPinCountOrFailIfTearingDown(v13, (struct _CmsRow *)&v229, v227);
  v180 = v18;
  v23 = _InterlockedExchange64((volatile __int64 *)v202, v223);
  *(_QWORD *)&v223 = 0;
  if ( v23 == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_1C0137CC0, 0);
    v100 = qword_1C0137CC8;
    if ( (__int64 *)qword_1C0137CC8 != &qword_1C0137CC8 )
    {
      v101 = v202;
      do
      {
        v102 = *(struct SmsHashEntry **)v100;
        v193 = *(struct SmsHashEntry **)v100;
        if ( *(struct SmsHashEntry **)(v100 + 24) == v101 )
        {
          if ( *((_QWORD *)v102 + 1) != v100
            || (v103 = *(struct SmsHashEntry ***)(v100 + 8), *v103 != (struct SmsHashEntry *)v100) )
          {
LABEL_295:
            __fastfail(3u);
          }
          *v103 = v102;
          *((_QWORD *)v102 + 1) = v103;
          *(_QWORD *)v100 = 0;
          KeSetEvent(*(PRKEVENT *)(v100 + 16), 0, 0);
          v102 = v193;
          v101 = v202;
        }
        v100 = (__int64)v102;
      }
      while ( v102 != (struct SmsHashEntry *)&qword_1C0137CC8 );
    }
    ExReleasePushLockEx(&qword_1C0137CC0, 0);
  }
  if ( v18 >= 0 )
  {
    this = *((_QWORD *)v232 + 51);
    if ( (this & 0x10000) != 0 )
      MsUnsupportedOperationBugCheck("Pinning abandoned page but didn't allocate it");
    v16 = v232;
    if ( v234 )
    {
      this = (unsigned __int64)P;
      if ( P )
        ExFreePoolWithTag(P, 0);
    }
    if ( v16 )
    {
      v24 = *((_DWORD *)v16 + 84);
      LOWORD(v188) = 1;
      if ( !v24 )
      {
LABEL_12:
        if ( (*((_QWORD *)v16 + 51) & 0x200000LL) == 0 )
          goto LABEL_13;
        v182 = 1;
        v26 = 0;
LABEL_54:
        v176 = v26;
LABEL_16:
        v27 = v195;
        goto LABEL_17;
      }
      this = *(_QWORD *)a3;
      v128 = *((_QWORD *)v16 + 15);
      if ( *(_QWORD *)a3 == v128 || this == *(_QWORD *)(v128 + 32) )
      {
        if ( *((_DWORD *)a3 + 4) != v24 )
          goto LABEL_12;
      }
      else
      {
        this = (unsigned int)(*((_DWORD *)a3 + 4) - *(_DWORD *)(this + 116));
        v129 = *((_DWORD *)v16 + 84);
        v130 = this + *(_DWORD *)(*((_QWORD *)v16 + 15) + 116LL);
        if ( !v129 )
          goto LABEL_12;
        if ( !v130 )
        {
          v130 = *(_DWORD *)(*((_QWORD *)v16 + 15) + 116LL);
          v129 = *((_DWORD *)v16 + 84);
        }
        if ( v130 != v129 )
          goto LABEL_12;
      }
      v182 = 1;
      v26 = 0;
      goto LABEL_54;
    }
  }
  else
  {
LABEL_262:
    if ( v234 && P )
      ExFreePoolWithTag(P, 0);
    if ( v18 == -1073739772 )
    {
      KeWaitForSingleObject(&v227[1], Executive, 0, 0, 0);
      v109 = v189;
      v110 = v192;
      *v189 = 1;
      goto LABEL_201;
    }
  }
  if ( (a6 & 0x100) != 0 )
  {
    v18 = -1073741738;
    goto LABEL_265;
  }
  if ( (a6 & 0x200) != 0 )
  {
    v18 = -1073741709;
    goto LABEL_265;
  }
  v177 = (_BYTE)v197 || (a6 & 0x800) != 0;
  v193 = *(struct SmsHashEntry **)a3;
  v212 = 0;
  v48 = *((_QWORD *)v193 + 4);
  memset(v215, 0, 12);
  v198 = *(struct SmsHashEntry **)(v48 + 48);
  if ( qword_1C014C028 < &qword_1C014C020 || &qword_1C014C028[1] > &qword_1C014C028[68] )
    v49 = (_SmsIndexEntry::MmsKeyLengthOutsideData(
             (struct _CmsKey *)&qword_1C014C000,
             (struct _CmsData *)&qword_1C014C010)
         + 7)
        & 0xFFFFFFF8;
  else
    v49 = 0;
  v50 = v49 + 568;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  if ( NumProcessors == 56 )
    v52 = CurrentProcessorNumber % 0x38;
  else
    v52 = CurrentProcessorNumber % NumProcessors;
  v53 = &LookasideLists[24 * v52];
  if ( v50 <= *(unsigned int *)v53 )
  {
    if ( *((_BYTE *)v53 + 8) )
    {
      v54 = (struct _PAGED_LOOKASIDE_LIST *)(v53 + 8);
      if ( *((_BYTE *)v53 + 9) )
      {
        ++*((_DWORD *)v53 + 21);
        PoolWithTag = ExpInterlockedPopEntrySList(&v54->L.ListHead);
        if ( PoolWithTag )
          goto LABEL_84;
        ++*((_DWORD *)v53 + 22);
        v97 = (_QWORD *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v53[14])(
                          *((unsigned int *)v53 + 25),
                          *((unsigned int *)v53 + 27),
                          *((unsigned int *)v53 + 26));
      }
      else
      {
        v97 = ExAllocateFromPagedLookasideList(v54);
      }
LABEL_168:
      PoolWithTag = v97;
LABEL_84:
      if ( PoolWithTag )
        goto LABEL_85;
      goto LABEL_274;
    }
    if ( *((_DWORD *)v53 + 20) > *((_DWORD *)v53 + 22) )
    {
      v131 = _InterlockedDecrement((volatile signed __int32 *)v53 + 20);
      if ( v131 >= *((_DWORD *)v53 + 22) && v131 >= 0 )
      {
        v97 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v53 + 4);
        goto LABEL_168;
      }
      _InterlockedIncrement((volatile signed __int32 *)v53 + 20);
    }
LABEL_274:
    v132 = *((unsigned int *)v53 + 1);
    goto LABEL_276;
  }
  v53 = 0;
  v132 = v50 + 8;
LABEL_276:
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v132, 0x6950534Du);
  if ( !PoolWithTag )
    goto LABEL_277;
LABEL_85:
  *PoolWithTag = v53;
  v56 = PoolWithTag + 1 == 0;
  v57 = (int *)(PoolWithTag + 1);
  v199 = v57;
  if ( v56 )
  {
LABEL_277:
    v110 = v192;
    v109 = v189;
    v18 = -1073741670;
    v190 = 0;
    v180 = -1073741670;
    goto LABEL_201;
  }
  if ( qword_1C014C028 < &qword_1C014C020 || &qword_1C014C028[1] > &qword_1C014C028[68] )
    v58 = (_SmsIndexEntry::MmsKeyLengthOutsideData(
             (struct _CmsKey *)&qword_1C014C000,
             (struct _CmsData *)&qword_1C014C010)
         + 7)
        & 0xFFFFFFF8;
  else
    v58 = 0;
  v57[3] = 552;
  *v57 = v58 + 568;
  v59 = (unsigned __int64 *)(v57 + 3);
  v57[1] = 524304;
  v60 = 16;
  v57[2] = 0x100000;
  if ( qword_1C014C028 < &qword_1C014C020 || &qword_1C014C028[1] > &qword_1C014C028[68] )
  {
    v133 = _SmsIndexEntry::MmsKeyLengthOutsideData(
             (struct _CmsKey *)&qword_1C014C000,
             (struct _CmsData *)&qword_1C014C010);
    *((_WORD *)v57 + 5) = ((v133 + 7) & 0xFFF8) + 16;
    *((_QWORD *)v57 + 2) = 0;
    *((_QWORD *)v57 + 2) = 0;
    v60 = *((_WORD *)v57 + 5);
  }
  else
  {
    *((_WORD *)v57 + 2) = (unsigned __int16)qword_1C014C028 - (unsigned __int16)&qword_1C014C020 + 16;
  }
  v61 = &qword_1C014C020;
  v62 = 4;
  v63 = (char *)v57 + v60;
  do
  {
    v63 += 128;
    v64 = *(_OWORD *)v61;
    v61 += 16;
    *((_OWORD *)v63 - 8) = v64;
    *((_OWORD *)v63 - 7) = *((_OWORD *)v61 - 7);
    *((_OWORD *)v63 - 6) = *((_OWORD *)v61 - 6);
    *((_OWORD *)v63 - 5) = *((_OWORD *)v61 - 5);
    *((_OWORD *)v63 - 4) = *((_OWORD *)v61 - 4);
    *((_OWORD *)v63 - 3) = *((_OWORD *)v61 - 3);
    *((_OWORD *)v63 - 2) = *((_OWORD *)v61 - 2);
    *((_OWORD *)v63 - 1) = *((_OWORD *)v61 - 1);
    --v62;
  }
  while ( v62 );
  v65 = *(_OWORD *)v61;
  *(_QWORD *)&v215[3] = v57;
  *(_OWORD *)v63 = v65;
  *((_OWORD *)v63 + 1) = *((_OWORD *)v61 + 1);
  *((_QWORD *)v63 + 4) = v61[4];
  if ( (v57[2] & 0x40) != 0 )
  {
    v68 = *v57;
    v66 = v59;
    v211 = 12;
    v67 = (char *)v57;
    v213 = v59;
    *(_QWORD *)&v215[1] = v57;
  }
  else
  {
    v66 = (unsigned __int64 *)((char *)v57 + *((unsigned __int16 *)v57 + 2));
    v67 = (char *)v57 + *((unsigned __int16 *)v57 + 5);
    v211 = *((unsigned __int16 *)v57 + 3);
    v68 = *(_DWORD *)v59;
    *(_QWORD *)&v215[1] = v67;
    v213 = v66;
  }
  v214 = v68;
  ExInitializeResourceLite((PERESOURCE)v67 + 4);
  KeInitializeEvent((PRKEVENT)v67 + 16, NotificationEvent, 0);
  v69 = v193;
  *((_QWORD *)v67 + 15) = v193;
  *((_QWORD *)v67 + 34) = v13;
  v67[328] = -8;
  *((_QWORD *)v67 + 51) = 0;
  v190 = (struct SmsPage *)v67;
  *((_DWORD *)v67 + 81) = 1;
  *((_DWORD *)v190 + 74) = *((_DWORD *)a3 + 4);
  v70 = v190;
  *(_OWORD *)((char *)v190 + 344) = 0;
  *(_OWORD *)((char *)v70 + 360) = 0;
  if ( v177 )
  {
    (*(void (__fastcall **)(_QWORD, struct _SmsView *, struct SmsPage **))(**((_QWORD **)v69 + 12) + 64LL))(
      *((_QWORD *)v69 + 12),
      a3,
      &v190);
    _InterlockedOr64((volatile signed __int64 *)v190 + 51, 0x2000180u);
    v67 = *(char **)&v215[1];
    v66 = v213;
  }
  v71 = (struct _ERESOURCE *)((char *)v190 + 416);
  if ( (a6 & 4) == 0 )
  {
    ExAcquireResourceSharedLite(v71, 1u);
    if ( CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v190 + 15)) )
      goto LABEL_101;
    goto LABEL_100;
  }
  ExAcquireResourceExclusiveLite(v71, 1u);
  if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v190 + 15)) )
LABEL_100:
    ++*((_DWORD *)v13 + 6);
LABEL_101:
  v72 = v196;
  v190 = (struct SmsPage *)v67;
  v73 = (struct SmsHashEntry *)((char *)v198 + 16);
  v196 = (struct SmsHashEntry *)((char *)v198 + 16);
  *v66 = *(_QWORD *)v72;
  v74 = v190;
  *(_OWORD *)((char *)v190 + 8) = *(_OWORD *)v72;
  *(_OWORD *)((char *)v74 + 24) = *((_OWORD *)v72 + 1);
  *(_OWORD *)v205 = 0;
  *((_DWORD *)v190 + 80) = a5;
  v75 = *v66;
  v206 = 0;
  v178 = 0;
  v198 = (struct SmsHashEntry *)v75;
  if ( !v75 )
  {
    v79 = v199;
    v18 = -1073741811;
    goto LABEL_219;
  }
  v76 = *((_QWORD *)v73 + 3);
  v194 = 0;
  v77 = CmsHashTable::FindAndLockEntryInternal(
          v73,
          v75,
          1u,
          0,
          v76 != 0,
          (struct _SmsHashLocation *)v205,
          &v194,
          v173,
          v175);
  if ( !v76 && *((_QWORD *)v73 + 3) )
  {
    if ( v194 )
      SmsHashEntry::Unlock(v194, v205);
    v77 = CmsHashTable::FindAndLockEntryInternal(v73, v75, 1u, 0, 1, (struct _SmsHashLocation *)v205, &v194, v173, v175);
  }
  v78 = v194;
  if ( v77 || v194 )
  {
    v180 = 0;
    v18 = 0;
    if ( v77 )
    {
      v79 = v199;
      *(_QWORD *)v77 = v198;
      *((_QWORD *)v77 + 1) = v79;
      ++*(_WORD *)(*((_QWORD *)v78 + 1) + 2LL);
    }
    else if ( v205[0] )
    {
      v106 = CmsHashTable::CreateOrExpandOverflowBucket(0, (struct _SmsHashLocation *)v205, v194);
      v79 = v199;
      v18 = v106;
      v180 = v106;
      if ( v106 < 0 )
      {
        v81 = v196;
LABEL_109:
        if ( v18 >= 0 && (*((_BYTE *)v81 + 16 * LODWORD(v205[1]) + 20) & 3) == 3 )
        {
          if ( !*((_QWORD *)v81 + 3) )
            v178 = *((_DWORD *)v81 + 4) << word_1C01368AC < *((_DWORD *)v81 + 5);
          v104 = *((_DWORD *)v81 + 5) + *((_DWORD *)v81 + 9);
          v105 = *((_DWORD *)v81 + 4) + *((_DWORD *)v81 + 8);
          if ( dword_1C01368C8 < v104 )
          {
            _InterlockedCompareExchange(&dword_1C01368C8, v104, dword_1C01368C8);
            v78 = v194;
          }
          if ( v105 < v104 && dword_1C01368CC < v104 - v105 )
          {
            _InterlockedCompareExchange(&dword_1C01368CC, v104 - v105, dword_1C01368CC);
            v78 = v194;
          }
          if ( v104 > *((_DWORD *)v81 + 10) )
            *((_DWORD *)v81 + 10) = v104;
        }
        if ( v78 && _InterlockedExchange64((volatile __int64 *)v78, v205[0]) == -3 )
        {
          ExAcquirePushLockExclusiveEx(&qword_1C0137CC0, 0);
          v124 = qword_1C0137CC8;
          if ( (__int64 *)qword_1C0137CC8 != &qword_1C0137CC8 )
          {
            v125 = v194;
            do
            {
              v126 = *(__int64 **)v124;
              if ( *(SmsHashEntry **)(v124 + 24) == v125 )
              {
                if ( v126[1] != v124 )
                  goto LABEL_295;
                v127 = *(__int64 ***)(v124 + 8);
                if ( *v127 != (__int64 *)v124 )
                  goto LABEL_295;
                *v127 = v126;
                v126[1] = (__int64)v127;
                *(_QWORD *)v124 = 0;
                KeSetEvent(*(PRKEVENT *)(v124 + 16), 0, 0);
                v125 = v194;
              }
              v124 = (__int64)v126;
            }
            while ( v126 != &qword_1C0137CC8 );
          }
          ExReleasePushLockEx(&qword_1C0137CC0, 0);
        }
        if ( v178 )
          CmsHashTable::AttemptResize(v196, 1u);
        if ( v18 < 0 )
          goto LABEL_220;
        if ( v18 != 0x40000000 )
        {
          *((_QWORD *)v13 + 2) |= 0x400000uLL;
          this = *(unsigned int *)(*((_QWORD *)v193 + 4) + 124LL);
          if ( (this & 8) == 0 )
            _InterlockedOr((volatile signed __int32 *)(*((_QWORD *)v193 + 4) + 124LL), 8u);
          goto LABEL_119;
        }
        goto LABEL_218;
      }
      v107 = *((_QWORD *)v78 + 1);
      *(_QWORD *)(*(_QWORD *)(v107 + 8) + 16LL * *(unsigned __int16 *)(v107 + 2)) = v198;
      *(_QWORD *)(*(_QWORD *)(v107 + 8) + 16LL * (unsigned __int16)(*(_WORD *)(v107 + 2))++ + 8) = v79;
    }
    else
    {
      v79 = v199;
      v80 = (unsigned __int64)v198;
      *((_QWORD *)v194 + 1) = v199;
      v205[0] = v80;
    }
    v81 = v196;
    _InterlockedIncrement((volatile signed __int32 *)v196 + 4 * LODWORD(v205[1]) + 5);
    v78 = v194;
    goto LABEL_109;
  }
  v79 = v199;
LABEL_218:
  v18 = -1073741771;
LABEL_219:
  v180 = v18;
LABEL_220:
  if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v190 + 15)) )
    --*((_DWORD *)v13 + 6);
  ExReleaseResourceLite(v118 + 4);
  CmsVolume::TeardownPageInternals(v119, v190);
  CmsLookasides::Free(v79);
  v190 = 0;
LABEL_119:
  if ( v18 == -1073741771 )
  {
    v109 = v189;
    v18 = -1073739772;
    v110 = v192;
    v180 = -1073739772;
    *v189 = 1;
    goto LABEL_201;
  }
  if ( v18 < 0 )
    goto LABEL_324;
  v183 = (_BYTE)v197 || (a6 & 0x800) != 0;
  v16 = v190;
  v191 = 1;
  LOWORD(v188) = 1;
  if ( (_BYTE)v197 || (a6 & 0x800) != 0 )
  {
    v26 = v186;
    goto LABEL_54;
  }
LABEL_13:
  if ( v201 && *((_QWORD *)v16 + 36) )
  {
    v83 = 0;
    for ( i = 0; ; v83 = i )
    {
      this = *(unsigned int *)(*(_QWORD *)a3 + 124LL);
      if ( (this & 0x80u) != 0LL )
      {
        ExAcquireResourceSharedLite((PERESOURCE)v16 + 4, 1u);
        v83 = 1;
        i = 1;
      }
      v84 = *((_QWORD *)v16 + 36);
      if ( !v84 || *(_DWORD *)(v84 + 296) > *((_DWORD *)a3 + 4) )
      {
LABEL_152:
        if ( i )
          ExReleaseResourceLite((PERESOURCE)v16 + 4);
        break;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v84 + 324));
      if ( v83 )
      {
        ExReleaseResourceLite((PERESOURCE)v16 + 4);
        i = 0;
      }
      v85 = *((_QWORD *)v16 + 15);
      v185 = 122;
      this = *(_QWORD *)(v85 + 32);
      v86 = (CmsHashTable *)(*(_QWORD *)(this + 48) + 16LL);
      v56 = (*((_QWORD *)v16 + 51) & 0x20) == 0;
      v196 = v86;
      v87 = *((_DWORD *)v16 + 81);
      if ( !v56 )
      {
        *((_DWORD *)v16 + 81) = v87 - 1;
        goto LABEL_151;
      }
      if ( v87 == 1
        || (this = (unsigned int)(v87 - 1),
            v87 != _InterlockedCompareExchange((volatile signed __int32 *)v16 + 81, this, v87)) )
      {
        v88 = *((_QWORD *)v16 + 1);
        v56 = *((_QWORD *)v86 + 3) == 0;
        v226 = 0;
        v203 = 0;
        v225 = 0;
        v89 = CmsHashTable::FindAndLockEntryInternal(
                v86,
                v88,
                0,
                0,
                !v56,
                (struct _SmsHashLocation *)&v225,
                &v203,
                v173,
                v175);
        v193 = v89;
        if ( v89 )
        {
          v91 = *((_QWORD *)v89 + 1);
          v216 = 0;
          v217 = 0;
          if ( (*(_BYTE *)(v91 + 8) & 0x40) != 0 )
          {
            LODWORD(v216) = 12;
            *((_QWORD *)&v216 + 1) = v91 + 12;
            LODWORD(v217) = *(unsigned __int16 *)(v91 + 10);
            *((_QWORD *)&v217 + 1) = v91;
          }
          else
          {
            LODWORD(v216) = *(unsigned __int16 *)(v91 + 6);
            *((_QWORD *)&v216 + 1) = v91 + *(unsigned __int16 *)(v91 + 4);
            LODWORD(v217) = *(_DWORD *)(v91 + 12);
            *((_QWORD *)&v217 + 1) = v91 + *(unsigned __int16 *)(v91 + 10);
          }
          v92 = DerefPageOrEnterTeardownState(v13, (struct _CmsRow *)&v216, &v185);
          this = (unsigned __int64)v203;
          v198 = v203;
          if ( v92 == -1073741444 )
          {
            CmsHashTable::DeleteInternal(v196, (struct _SmsHashLocation *)&v225, v193, v203, 1u, 0);
            this = (unsigned __int64)v198;
          }
          if ( _InterlockedExchange64((volatile __int64 *)this, v225) == -3 )
          {
            ExAcquirePushLockExclusiveEx(&qword_1C0137CC0, 0);
            v120 = qword_1C0137CC8;
            if ( (__int64 *)qword_1C0137CC8 != &qword_1C0137CC8 )
            {
              v121 = v203;
              do
              {
                v122 = *(struct SmsHashEntry **)v120;
                v193 = *(struct SmsHashEntry **)v120;
                if ( *(struct SmsHashEntry **)(v120 + 24) == v121 )
                {
                  if ( *((_QWORD *)v122 + 1) != v120 )
                    goto LABEL_295;
                  v123 = *(struct SmsHashEntry ***)(v120 + 8);
                  if ( *v123 != (struct SmsHashEntry *)v120 )
                    goto LABEL_295;
                  *v123 = v122;
                  *((_QWORD *)v122 + 1) = v123;
                  *(_QWORD *)v120 = 0;
                  KeSetEvent(*(PRKEVENT *)(v120 + 16), 0, 0);
                  v122 = v193;
                  v121 = v203;
                }
                v120 = (__int64)v122;
              }
              while ( v122 != (struct SmsHashEntry *)&qword_1C0137CC8 );
            }
            ExReleasePushLockEx(&qword_1C0137CC0, 0);
          }
        }
        if ( v185 != 45 )
        {
          if ( v185 != 116 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16 + 81, 0xFFFFFFFF) != 1 )
              goto LABEL_151;
            *((_BYTE *)v16 + 329) = 1;
          }
          CmsVolume::CleanAndUnmapPage(v200, v90, v16);
          if ( (*((_QWORD *)v16 + 51) & 0x4000000LL) != 0 )
            CmsVolumeContainer::SetContainerStationaryVolatile(
              *((CmsVolumeContainer **)v200 + 381),
              v13,
              (SmsPage *)((char *)v16 + 8),
              0,
              0);
          CmsVolume::TeardownPageTableEntry(v134, v13, v16);
        }
      }
LABEL_151:
      v16 = (SmsPage *)v84;
      if ( !*(_QWORD *)(v84 + 288) )
        goto LABEL_152;
    }
  }
  v25 = v186;
  v176 = v186;
  v26 = v186;
  LOWORD(v188) = 1;
  if ( (a6 & 0x40) == 0 )
    goto LABEL_16;
  v176 = v186;
  LOWORD(v188) = 1;
  if ( SmsPage::IsDirty(v16, a3) )
    goto LABEL_16;
  v93 = *((_QWORD *)v13 + 2);
  if ( (v93 & 0x20000000000LL) == 0
    && (v93 & 0x40) == 0
    && !*((_DWORD *)v13 + 6)
    && !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v16 + 15)) )
  {
    v117 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 3072LL) + 8LL);
    (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, _QWORD))(*(_QWORD *)v117 + 64LL))(v117, v13, 0);
  }
  v94 = *((_QWORD *)v16 + 51);
  if ( (v94 & 0x1008) != 0 )
  {
LABEL_244:
    v95 = 0;
  }
  else
  {
    while ( v94 != _InterlockedCompareExchange64((volatile signed __int64 *)v16 + 51, v94 | 8, v94) )
    {
      v94 = *((_QWORD *)v16 + 51);
      if ( (v94 & 0x1008) != 0 )
        goto LABEL_244;
    }
    v95 = 1;
  }
  v96 = v95 ^ 1;
  v176 = v25;
  v184 = v95 ^ 1;
  v26 = v25;
  *v192 = v95;
  this = 1;
  v188 = 1;
  if ( !v95 )
    goto LABEL_16;
  v27 = v195;
  v176 = v25;
  v188 = 1;
  v184 = v96;
  *v195 = 1;
LABEL_17:
  v28 = *v27;
  v29 = v188;
  v30 = *((_DWORD *)v16 + 75);
  v181 = v30;
  if ( (_WORD)v188 != *v27 )
  {
    do
    {
      _InterlockedIncrement((volatile signed __int32 *)v16 + 81);
      v28 = *v27;
      LOWORD(v29) = v29 + 1;
    }
    while ( (_WORD)v29 != *v27 );
    v188 = v29;
  }
  v31 = *((_BYTE *)v13 + 16);
  v32 = *(CmsBPlusTable **)a3;
  v33 = v191;
  v193 = *(struct SmsHashEntry **)a3;
  v34 = (v31 & 0x40) == 0;
  if ( (_WORD)v191 != v28 )
  {
    while ( 1 )
    {
      v35 = (struct _ERESOURCE *)((char *)v16 + 416);
      if ( v26 )
      {
        if ( !ExAcquireResourceExclusiveLite(v35, 0) )
        {
          if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
          {
            v135 = *((_QWORD *)v16 + 1);
            v136 = CmsBPlusTable::EtwTableIdLow(v32);
            v137 = CmsBPlusTable::EtwTableIdHigh(v32);
            ActivityIdThread = IoGetActivityIdThread();
            McTemplateK0iiid_EtwWriteTransfer(
              (unsigned int)MinstoreEventProvider_Context,
              v139,
              ActivityIdThread,
              v137,
              v136,
              v135);
            v13 = v207;
            v33 = v191;
            v32 = v193;
          }
          v45 = ExAcquireResourceExclusiveLite((PERESOURCE)v16 + 4, v34);
LABEL_171:
          if ( !v45 )
            goto LABEL_24;
        }
      }
      else if ( !ExAcquireResourceSharedLite(v35, 0) )
      {
        if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
        {
          v140 = *((_QWORD *)v16 + 1);
          v141 = CmsBPlusTable::EtwTableIdLow(v32);
          v142 = CmsBPlusTable::EtwTableIdHigh(v32);
          v143 = IoGetActivityIdThread();
          McTemplateK0iiid_EtwWriteTransfer((unsigned int)MinstoreEventProvider_Context, v144, v143, v142, v141, v140);
          v13 = v207;
          v33 = v191;
          v32 = v193;
        }
        v45 = ExAcquireResourceSharedLite((PERESOURCE)v16 + 4, v34);
        goto LABEL_171;
      }
      if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v16 + 15)) )
        ++*((_DWORD *)v13 + 6);
      v26 = v176;
      LOWORD(v33) = v33 + 1;
      v191 = v33;
      if ( (_WORD)v33 == v28 )
      {
LABEL_24:
        if ( (_WORD)v33 == v28 )
        {
          v30 = v181;
          break;
        }
        v18 = -1073741608;
LABEL_265:
        v109 = v189;
LABEL_247:
        v110 = v192;
        v180 = v18;
LABEL_201:
        if ( *v110 )
        {
          *v110 = 0;
          _InterlockedAnd64((volatile signed __int64 *)v16 + 51, 0xFFFFFFFFFFFFFFF7uLL);
        }
        goto LABEL_203;
      }
    }
  }
  v36 = *((_BYTE *)a3 + 21);
  if ( *((_BYTE *)v16 + 328) != v36 && v36 != -7 )
    *((_BYTE *)v16 + 328) = v36;
  v37 = (_DWORD *)*((_QWORD *)a3 + 1);
  if ( v37 && *((_DWORD *)v16 + 20) > *v37 )
    v38 = 1;
  else
    v38 = v182;
  if ( (*((_DWORD *)v13 + 4) & 0x800LL) == 0
    && ((*((_QWORD *)v16 + 51) & 1) == 0 || (*((_QWORD *)v16 + 51) & 2) == 0)
    && !(_BYTE)v197 )
  {
    v82 = (_DWORD *)*((_QWORD *)a3 + 1);
    if ( v82 )
    {
      this = *(unsigned int *)(*(_QWORD *)a3 + 112LL);
      if ( (_DWORD)this != *v82 )
        v38 = 1;
    }
  }
  if ( (*((_QWORD *)v16 + 51) & 0x200000LL) == 0 && !v38 )
  {
    v39 = *((_DWORD *)v16 + 84);
    if ( !v39 )
      goto LABEL_36;
    this = *(_QWORD *)a3;
    v145 = *((_QWORD *)v16 + 15);
    if ( *(_QWORD *)a3 != v145 && this != *(_QWORD *)(v145 + 32) )
    {
      this = (unsigned int)(*((_DWORD *)a3 + 4) - *(_DWORD *)(this + 116));
      v146 = *((_DWORD *)v16 + 84);
      v147 = this + *(_DWORD *)(*((_QWORD *)v16 + 15) + 116LL);
      if ( v146 )
      {
        if ( !v147 )
        {
          v147 = *(_DWORD *)(*((_QWORD *)v16 + 15) + 116LL);
          v146 = *((_DWORD *)v16 + 84);
        }
        if ( v147 == v146 )
          goto LABEL_310;
      }
LABEL_36:
      if ( v30 == *((_DWORD *)v16 + 75) )
      {
        if ( v201 )
        {
          v40 = *((_QWORD *)v16 + 36);
          if ( v40 )
          {
            if ( *(_DWORD *)(v40 + 296) <= *((_DWORD *)a3 + 4) )
            {
              v109 = v189;
              v18 = -1073739772;
              *v189 = 1;
              goto LABEL_247;
            }
          }
        }
        if ( (*((_QWORD *)v16 + 51) & 0x10000LL) != 0 )
        {
          v109 = v189;
          v18 = -1073739772;
          *v189 = 1;
          goto LABEL_247;
        }
        if ( v204 || (*((_QWORD *)v16 + 51) & 2) != 0 )
        {
          v41 = v200;
          if ( *((_DWORD *)v200 + 746) <= 1u
            || *((_QWORD *)v13 + 332) != *(_QWORD *)a3
            || (v148 = *((_QWORD *)v13 + 333)) != 0
            && (v149 = *(unsigned __int8 *)(v148 + 6), (unsigned __int8)v149 < 0xAu)
            && *((_QWORD *)v16 + 1) == *(_QWORD *)(v148 + 8 * v149 + 16)
            || SmsPage::IsDirty(v16, a3)
            || SmsPage::IsDirty(v16, *((_DWORD *)a3 + 4) - 1)
            || (*((_QWORD *)v16 + 51) & 0x10) != 0 )
          {
            v42 = *((_QWORD *)v13 + 333);
            if ( v42 )
            {
              if ( *((_QWORD *)v13 + 332) == *(_QWORD *)a3 )
              {
                v170 = *(unsigned __int8 *)(v42 + 6);
                if ( (unsigned __int8)v170 >= 0xAu || *((_QWORD *)v16 + 1) != *(_QWORD *)(v42 + 8 * v170 + 16) )
                  *(_QWORD *)(v42 + 712) += (unsigned __int64)*((unsigned int *)v16 + 80) << *((_DWORD *)v41 + 16);
              }
            }
          }
          else
          {
            CmsTransactionContext::GetScrubBuffer(v13, *((_DWORD *)v16 + 80) << *((_DWORD *)v41 + 16));
            if ( *((_QWORD *)v13 + 334) )
            {
              v150 = *(_OWORD *)((char *)v16 + 8);
              v151 = *(_OWORD *)((char *)v16 + 24);
              v152 = *((_QWORD *)v16 + 15);
              v153 = *(_WORD *)(*(_QWORD *)(*((_QWORD *)v13 + 333) + 704LL) + 4LL);
              v237[0] = v150;
              v237[1] = v151;
              if ( (*(_DWORD *)(v152 + 16) & 0x8000000) == 0 )
              {
                v154 = *((_QWORD *)v41 + 381);
                v228[0] = v150;
                v228[1] = v151;
                v180 = CmsVolumeContainer::PinContainerRange(v154, v13, v228, v237);
                v18 = v180;
                if ( v180 < 0 )
                  goto LABEL_324;
              }
              v155 = *((_QWORD *)v13 + 333);
              v156 = *(struct _SCRUB_PARITY_EXTENT_DATA **)(v155 + 704);
              v157 = *(struct _SmsScrubIoOutput **)(v155 + 696);
              v158 = *((_QWORD *)CmsBPlusTable::BindableUnitTable(*(CmsBPlusTable **)(*(_QWORD *)a3 + 32LL)) + 10);
              v162 = *(struct _SCB **)(*(_QWORD *)(v161 + 48) + 72LL);
              v163 = v159 | 2;
              if ( (v164 & 8) == 0 )
                v163 = v159;
              v165 = CmsVolume::SmartIoScrubPage(
                       v41,
                       v162,
                       (union _SmsBigIdentifier *)(v158 + 376),
                       (const union _LCN_TUPLE *)v237,
                       v160,
                       0,
                       v208,
                       v163,
                       v157,
                       v156,
                       0,
                       0);
              *(_QWORD *)(*((_QWORD *)v13 + 333) + 712LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 333) + 696LL)
                                                                       + 24LL);
              if ( v165 >= 0 )
              {
                v166 = *((_QWORD *)v13 + 333);
                if ( v166 )
                {
                  v167 = *(unsigned __int8 *)(v166 + 6);
                  if ( (unsigned __int8)v167 < 0xAu )
                    *(_QWORD *)(v166 + 8 * v167 + 16) = *((_QWORD *)v16 + 1);
                }
              }
              if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v13 + 333) + 696LL))
                || *(_WORD *)(*(_QWORD *)(v169 + 704) + 4LL) > v153 )
              {
                MsScrubContextCaptureError(v169, v168);
              }
            }
          }
          goto LABEL_45;
        }
        v46 = (*((_QWORD *)v16 + 51) & 0x100LL) != 0 || (a6 & 0x800) != 0;
        v41 = v200;
        v47 = *(_QWORD *)a3;
        memset(v222, 0, sizeof(v222));
        if ( (*((_DWORD *)v200 + 779) & 0x20000000) != 0 )
        {
          v110 = v192;
          v18 = -1073741202;
          v109 = v189;
          v180 = -1073741202;
          goto LABEL_201;
        }
        v219[3] = v208;
        v220 = v176;
        v219[1] = v47;
        v221 = v46;
        v219[0] = v13;
        v219[2] = v16;
        v219[4] = v200;
        v180 = ((__int64 (__fastcall *)(void (__fastcall *)(void *), _QWORD *, __int64, _QWORD, _QWORD))qword_1C0136AC0)(
                 CmsVolume::ReadPageCallout,
                 v219,
                 12288,
                 0,
                 0);
        v18 = v180;
        if ( v180 >= 0 )
        {
          v18 = *(_DWORD *)&v222[2];
          v180 = *(_DWORD *)&v222[2];
        }
        if ( v18 >= 0 )
        {
LABEL_45:
          if ( v184 )
          {
            v109 = v189;
            v18 = -1073739772;
            v180 = -1073739772;
            *v189 = 1;
            KeWaitForSingleObject((char *)v16 + 384, Executive, 0, 0, 0);
            v110 = v192;
            goto LABEL_201;
          }
          if ( *v192 )
            KeClearEvent((PRKEVENT)v16 + 16);
          v18 = 0;
          v43 = v210;
          *v209 = v16;
          if ( v43 )
            *v43 = (struct _SmsPageHeader *)*((_QWORD *)v16 + 16);
          if ( v183 )
          {
            v98 = CmsBPlusTable::BindableUnitTable(*(CmsBPlusTable **)a3);
            MspAddDirtyPageCount(v41, *((struct _SmsBindable **)v98 + 10), a5, (*(_DWORD *)(v99 + 16) & 0x40000LL) != 0);
          }
          return (unsigned int)v18;
        }
LABEL_324:
        v110 = v192;
        v109 = v189;
        goto LABEL_201;
      }
      goto LABEL_310;
    }
    if ( *((_DWORD *)a3 + 4) != v39 )
      goto LABEL_36;
LABEL_310:
    v109 = v189;
    goto LABEL_200;
  }
  if ( SmsPage::IsDeleted(v16, a3) )
    goto LABEL_310;
  v109 = v189;
  if ( (*((_QWORD *)v16 + 51) & 0x200000LL) == 0 && !v108 )
    *v189 = 1;
LABEL_200:
  v110 = v192;
  v18 = -1073741738;
  v180 = -1073741738;
  if ( !*v192 )
    goto LABEL_201;
  CmsVolume::ClearPageCopyingState((CmsVolume *)this, v16, 0);
  *v192 = 0;
LABEL_203:
  if ( v183 )
  {
    *((_DWORD *)v16 + 83) = 0;
    _InterlockedAnd64((volatile signed __int64 *)v16 + 51, 0xFFFFFFFFFFFFFF7FuLL);
    _InterlockedOr64((volatile signed __int64 *)v16 + 51, 0x2000u);
  }
  v111 = v191;
  v112 = v188;
  if ( (unsigned __int16)v191 > (unsigned __int16)v188 )
  {
    v171 = (unsigned __int16)(v191 - v188);
    do
    {
      if ( !CmsBPlusTable::WasUpdateDeferred(*((CmsBPlusTable **)v16 + 15)) )
        --*((_DWORD *)v13 + 6);
      ExReleaseResourceLite((PERESOURCE)v16 + 4);
      --v111;
      --v171;
    }
    while ( v171 );
    v18 = v180;
    v109 = v189;
  }
  if ( v112 )
  {
    v113 = v200;
    v218 = v16;
    do
    {
      v114 = v112 - 1;
      if ( v112 > v111 )
      {
        v115 = 2;
      }
      else
      {
        --v111;
        v115 = 3;
      }
      CmsVolume::UnpinCommon(v113, v13, &v218, v115);
      --v112;
    }
    while ( v114 );
    v18 = v180;
  }
  v116 = v210;
  *v209 = 0;
  if ( v116 )
    *v116 = 0;
  if ( v187 )
  {
    v18 = -1073741738;
    *v109 = 0;
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1c0017a30  push    rbp
0x1c0017a32  push    rbx
0x1c0017a33  push    rsi
0x1c0017a34  push    rdi
0x1c0017a35  push    r12
0x1c0017a37  push    r13
0x1c0017a39  push    r14
0x1c0017a3b  push    r15
0x1c0017a3d  lea     rbp, [rsp-1D8h]
0x1c0017a45  sub     rsp, 2D8h
0x1c0017a4c  mov     rax, cs:__security_cookie
0x1c0017a53  xor     rax, rsp
0x1c0017a56  mov     [rbp+210h+var_50], rax
0x1c0017a5d  mov     edi, dword ptr [rbp+210h+arg_28]
0x1c0017a63  xor     r10d, r10d
0x1c0017a66  mov     rax, [rbp+210h+arg_38]
0x1c0017a6d  mov     r14, rdx
0x1c0017a70  mov     rbx, [rbp+210h+arg_30]
0x1c0017a77  mov     r15d, edi
0x1c0017a7a  mov     [rbp+210h+var_1F8], rax
0x1c0017a7e  mov     r13, r8
0x1c0017a81  mov     rax, [rbp+210h+arg_40]
0x1c0017a88  movzx   esi, r10w
0x1c0017a8c  mov     r8, [rbp+210h+arg_58]
0x1c0017a93  mov     [rbp+210h+var_1E8], rax
0x1c0017a97  mov     rax, [rbp+210h+arg_48]
0x1c0017a9e  mov     [rbp+210h+var_1F0], rax
0x1c0017aa2  mov     rax, [rbp+210h+arg_50]
0x1c0017aa9  mov     [rbp+210h+var_200], rdx
0x1c0017aad  mov     edx, edi
0x1c0017aaf  mov     [rbp+210h+var_280], rax
0x1c0017ab3  xor     al, al
0x1c0017ab5  mov     [rbp+210h+var_260], r9
0x1c0017ab9  xor     r9b, r9b
0x1c0017abc  and     r15d, 4
0x1c0017ac0  mov     [rbp+210h+var_240], rcx
0x1c0017ac4  mov     [rbp+210h+var_268], rbx
0x1c0017ac8  mov     rbx, [rbp+210h+arg_60]
0x1c0017acf  setnz   cl
0x1c0017ad2  and     edx, 1
0x1c0017ad5  mov     [rsp+310h+var_298], r8
0x1c0017ada  mov     word ptr [rsp+310h+var_2A0], r10w
0x1c0017ae0  mov     [rbp+210h+var_288], esi
0x1c0017ae3  mov     [rsp+310h+var_2A6], r9b
0x1c0017ae8  mov     [rsp+310h+var_2A8], al
0x1c0017aec  mov     [rsp+310h+var_2A7], al
0x1c0017af0  mov     [rsp+310h+var_2A4], cl
0x1c0017af4  mov     [rbp+210h+var_258], edx
0x1c0017af7  bt      edi, 0Bh
0x1c0017afb  jb      loc_1C0075A2A
0x1c0017b01  mov     [rsp+310h+var_2AF], al
0x1c0017b05  mov     eax, edi
0x1c0017b07  mov     r12d, edi
0x1c0017b0a  and     eax, 8
0x1c0017b0d  and     r12d, 40h
0x1c0017b11  mov     [rbp+210h+var_238], eax
0x1c0017b14  mov     eax, edi
0x1c0017b16  and     eax, 80h
0x1c0017b1b  mov     [rbp+210h+var_220], eax
0x1c0017b1e  test    rbx, rbx
0x1c0017b21  jz      short loc_1C0017B2C
0x1c0017b23  cmp     [rbx], r10
0x1c0017b26  jnz     loc_1C0017F03
0x1c0017b2c  xorps   xmm0, xmm0
0x1c0017b2f  mov     [r8], r9b
0x1c0017b32  xor     r8d, r8d; State
0x1c0017b35  mov     [rsp+310h+var_2A3], r9b
0x1c0017b3a  xor     edx, edx; Type
0x1c0017b3c  lea     rcx, [rbp+210h+Event]; Event
0x1c0017b43  movups  xmmword ptr [rbp+0E8h], xmm0
0x1c0017b4a  movups  xmmword ptr [rbp+210h+Event.Header.WaitListHead.Flink], xmm0
0x1c0017b51  call    cs:__imp_KeInitializeEvent
0x1c0017b58  nop     dword ptr [rax+rax+00h]
0x1c0017b5d  mov     rdx, [rbp+210h+var_260]
0x1c0017b61  lea     rax, [rbp+210h+var_B0]
0x1c0017b68  xor     r8d, r8d
0x1c0017b6b  mov     [rbp+210h+P], rax
0x1c0017b72  mov     rax, [r13+0]
0x1c0017b76  mov     ebx, r8d
0x1c0017b79  mov     [rbp+210h+var_230], r8
0x1c0017b7d  xorps   xmm0, xmm0
0x1c0017b80  mov     rdx, [rdx]; unsigned __int64
0x1c0017b83  lea     r8, [rbp+210h+var_230]
0x1c0017b87  mov     [rsp+310h+var_2E0], r8; struct SmsHashEntry **
0x1c0017b8c  mov     esi, 0C0000034h
0x1c0017b91  mov     rcx, [rax+20h]
0x1c0017b95  lea     r8, [rbp+210h+var_158]
0x1c0017b9c  xor     eax, eax
0x1c0017b9e  mov     [rbp+210h+var_B4], 40h ; '@'
0x1c0017ba8  mov     [rbp+210h+var_B8], 0
0x1c0017baf  mov     [rsp+310h+var_2E8], r8; struct _SmsHashLocation *
0x1c0017bb4  mov     rcx, [rcx+30h]
0x1c0017bb8  add     rcx, 10h; this
0x1c0017bbc  mov     [rbp+210h+var_148], rax
0x1c0017bc3  movups  [rbp+210h+var_158], xmm0
0x1c0017bca  mov     [rsp+310h+var_2AC], esi
0x1c0017bce  cmp     [rcx+18h], rax
0x1c0017bd2  setnz   al
0x1c0017bd5  xor     r9d, r9d; unsigned __int8
0x1c0017bd8  xor     r8d, r8d; unsigned __int8
0x1c0017bdb  mov     byte ptr [rsp+310h+Timeout], al; char
0x1c0017bdf  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x1c0017be4  test    rax, rax
0x1c0017be7  jz      loc_1C0018045
0x1c0017bed  mov     rcx, [rax+8]
0x1c0017bf1  test    byte ptr [rcx+8], 40h
0x1c0017bf5  lea     rdx, [rcx+0Ch]
0x1c0017bf9  jnz     loc_1C0075A34
0x1c0017bff  movzx   eax, word ptr [rcx+6]
0x1c0017c03  mov     [rbp+210h+var_E0], eax
0x1c0017c09  movzx   eax, word ptr [rcx+4]
0x1c0017c0d  add     rax, rcx
0x1c0017c10  mov     [rbp+210h+var_D8], rax
0x1c0017c17  mov     eax, [rdx]
0x1c0017c19  mov     [rbp+210h+var_D0], eax
0x1c0017c1f  movzx   eax, word ptr [rcx+0Ah]
0x1c0017c23  add     rax, rcx
0x1c0017c26  mov     [rbp+210h+var_C8], rax
0x1c0017c2d  lea     r8, [rbp+210h+var_128]; void *
0x1c0017c34  mov     rcx, r14; struct CmsTransactionCore *
0x1c0017c37  lea     rdx, [rbp+210h+var_E0]; struct _CmsRow *
0x1c0017c3e  call    ?AddPinCountOrFailIfTearingDown@@YAJPEAVCmsTransactionCore@@PEAU_CmsRow@@PEAX@Z; AddPinCountOrFailIfTearingDown(CmsTransactionCore *,_CmsRow *,void *)
0x1c0017c43  mov     rcx, qword ptr [rbp+210h+var_158]
0x1c0017c4a  mov     esi, eax
0x1c0017c4c  mov     [rsp+310h+var_2AC], eax
0x1c0017c50  mov     rax, [rbp+210h+var_230]
0x1c0017c54  xchg    rcx, [rax]
0x1c0017c57  xor     eax, eax
0x1c0017c59  mov     qword ptr [rbp+210h+var_158], rax
0x1c0017c60  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1c0017c64  jz      loc_1C00188E1
0x1c0017c6a  test    esi, esi
0x1c0017c6c  js      loc_1C0018045
0x1c0017c72  mov     rax, [rbp+210h+var_C8]
0x1c0017c79  mov     rcx, [rax+198h]
0x1c0017c80  bt      rcx, 10h
0x1c0017c85  jb      loc_1C0075A5B
0x1c0017c8b  cmp     [rbp+210h+var_B8], 0
0x1c0017c92  mov     rbx, [rbp+210h+var_C8]
0x1c0017c99  jnz     loc_1C0075A68
0x1c0017c9f  test    rbx, rbx
0x1c0017ca2  jz      loc_1C001805D
0x1c0017ca8  mov     eax, [rbx+150h]
0x1c0017cae  mov     edi, 1
0x1c0017cb3  mov     word ptr [rsp+310h+var_2A0], di
0x1c0017cb8  test    eax, eax
0x1c0017cba  jnz     loc_1C0075A8C
0x1c0017cc0  mov     rax, [rbx+198h]
0x1c0017cc7  bt      rax, 15h
0x1c0017ccc  jb      loc_1C0075AF1
0x1c0017cd2  cmp     [rbp+210h+var_238], 0
0x1c0017cd6  jz      short loc_1C0017CE6
0x1c0017cd8  cmp     qword ptr [rbx+120h], 0
0x1c0017ce0  jnz     loc_1C001857D
0x1c0017ce6  movzx   r15d, [rsp+310h+var_2A4]
0x1c0017cec  mov     [rsp+310h+var_2B0], r15b
0x1c0017cf1  movzx   r10d, r15b
0x1c0017cf5  mov     word ptr [rsp+310h+var_2A0], di
0x1c0017cfa  test    r12d, r12d
0x1c0017cfd  jnz     loc_1C00186F3
0x1c0017d03  mov     rax, [rbp+210h+var_268]
0x1c0017d07  movzx   r12d, word ptr [rax]
0x1c0017d0b  mov     esi, [rsp+310h+var_2A0]
0x1c0017d0f  mov     r8d, [rbx+12Ch]
0x1c0017d16  mov     [rsp+310h+var_2AC], r8d
0x1c0017d1b  cmp     si, r12w
0x1c0017d1f  jnz     loc_1C0017F21
0x1c0017d25  movzx   r15d, byte ptr [r14+10h]
0x1c0017d2a  mov     rdi, [r13+0]
0x1c0017d2e  mov     esi, [rbp+210h+var_288]
0x1c0017d31  shr     r15b, 6
0x1c0017d35  not     r15b
0x1c0017d38  mov     [rbp+210h+var_278], rdi
0x1c0017d3c  and     r15b, 1
0x1c0017d40  cmp     si, r12w
0x1c0017d44  jz      short loc_1C0017D9E
0x1c0017d46  xor     edx, edx; Wait
0x1c0017d48  lea     rcx, [rbx+1A0h]; Resource
0x1c0017d4f  test    r10b, r10b
0x1c0017d52  jnz     loc_1C0017F3E
0x1c0017d58  call    cs:__imp_ExAcquireResourceSharedLite
0x1c0017d5f  nop     dword ptr [rax+rax+00h]
0x1c0017d64  test    al, al
0x1c0017d66  jz      loc_1C00187F4
0x1c0017d6c  mov     rcx, [rbx+78h]; this
0x1c0017d70  call    ?WasUpdateDeferred@CmsBPlusTable@@QEAAEXZ; CmsBPlusTable::WasUpdateDeferred(void)
0x1c0017d75  test    al, al
0x1c0017d77  jnz     short loc_1C0017D7D
0x1c0017d79  inc     dword ptr [r14+18h]
0x1c0017d7d  movzx   r10d, [rsp+310h+var_2B0]
0x1c0017d83  inc     si
0x1c0017d86  mov     [rbp+210h+var_288], esi
0x1c0017d89  cmp     si, r12w
0x1c0017d8d  jnz     short loc_1C0017D46
0x1c0017d8f  cmp     si, r12w
0x1c0017d93  jnz     loc_1C0075E7F
0x1c0017d99  mov     r8d, [rsp+310h+var_2AC]
0x1c0017d9e  movzx   eax, byte ptr [r13+15h]
0x1c0017da3  cmp     [rbx+148h], al
0x1c0017da9  jnz     loc_1C001855A
0x1c0017daf  mov     rax, [r13+8]
0x1c0017db3  test    rax, rax
0x1c0017db6  jz      short loc_1C0017DC3
0x1c0017db8  mov     eax, [rax]
0x1c0017dba  cmp     [rbx+50h], eax
0x1c0017dbd  jg      loc_1C0018B6F
0x1c0017dc3  movzx   r9d, [rsp+310h+var_2A8]
0x1c0017dc9  xor     r11b, r11b
0x1c0017dcc  mov     eax, [r14+10h]
0x1c0017dd0  bt      rax, 0Bh
0x1c0017dd5  jb      short loc_1C0017DF5
0x1c0017dd7  mov     rax, [rbx+198h]
0x1c0017dde  test    al, 1
0x1c0017de0  jz      loc_1C001852F
0x1c0017de6  mov     rax, [rbx+198h]
0x1c0017ded  test    al, 2
0x1c0017def  jz      loc_1C001852F
0x1c0017df5  mov     rax, [rbx+198h]
0x1c0017dfc  bt      rax, 15h
0x1c0017e01  jb      loc_1C0075E95
0x1c0017e07  test    r9b, r9b
0x1c0017e0a  jnz     loc_1C0018A88
0x1c0017e10  mov     eax, [rbx+150h]
0x1c0017e16  test    eax, eax
0x1c0017e18  jnz     loc_1C0075E9D
0x1c0017e1e  cmp     r8d, [rbx+12Ch]
0x1c0017e25  jnz     loc_1C0075EE9
0x1c0017e2b  cmp     [rbp+210h+var_238], 0
0x1c0017e2f  jz      short loc_1C0017E45
0x1c0017e31  mov     rax, [rbx+120h]
0x1c0017e38  mov     ecx, [r13+10h]
0x1c0017e3c  test    rax, rax
0x1c0017e3f  jnz     loc_1C0018DF1
0x1c0017e45  mov     rax, [rbx+198h]
0x1c0017e4c  bt      rax, 10h
0x1c0017e51  jb      loc_1C0075EFE
0x1c0017e57  cmp     [rbp+210h+var_220], 0
0x1c0017e5b  jnz     short loc_1C0017E6C
0x1c0017e5d  mov     rax, [rbx+198h]
0x1c0017e64  test    al, 2
0x1c0017e66  jz      loc_1C0017F7B
0x1c0017e6c  mov     r12, [rbp+210h+var_240]
0x1c0017e70  cmp     dword ptr [r12+0BA8h], 1
0x1c0017e79  jbe     short loc_1C0017E8C
0x1c0017e7b  mov     rax, [r13+0]
0x1c0017e7f  cmp     [r14+0A60h], rax
0x1c0017e86  jz      loc_1C0075F28
0x1c0017e8c  mov     rdx, [r14+0A68h]
0x1c0017e93  test    rdx, rdx
0x1c0017e96  jnz     loc_1C0076133
0x1c0017e9c  xor     edi, edi
0x1c0017e9e  cmp     [rsp+310h+var_2A6], 0
0x1c0017ea3  jnz     loc_1C0076175
0x1c0017ea9  mov     rax, [rbp+210h+var_280]
0x1c0017ead  cmp     byte ptr [rax], 0
0x1c0017eb0  jnz     loc_1C00188BB
0x1c0017eb6  mov     rax, [rbp+210h+var_1F0]
0x1c0017eba  mov     esi, edi
0x1c0017ebc  mov     rcx, [rbp+210h+var_1E8]
0x1c0017ec0  mov     [rax], rbx
0x1c0017ec3  test    rcx, rcx
0x1c0017ec6  jz      short loc_1C0017ED2
0x1c0017ec8  mov     rax, [rbx+80h]
0x1c0017ecf  mov     [rcx], rax
0x1c0017ed2  cmp     [rsp+310h+var_2A7], 0
0x1c0017ed7  jnz     loc_1C0018875
0x1c0017edd  mov     eax, esi
0x1c0017edf  mov     rcx, [rbp+210h+var_50]
0x1c0017ee6  xor     rcx, rsp; StackCookie
0x1c0017ee9  call    __security_check_cookie
0x1c0017eee  add     rsp, 2D8h
0x1c0017ef5  pop     r15
0x1c0017ef7  pop     r14
0x1c0017ef9  pop     r13
0x1c0017efb  pop     r12
0x1c0017efd  pop     rdi
0x1c0017efe  pop     rsi
0x1c0017eff  pop     rbx
0x1c0017f00  pop     rbp
0x1c0017f01  retn
0x1c0017f03  mov     [r8], r9b
0x1c0017f06  mov     rbx, [rbx]
0x1c0017f09  mov     [rsp+310h+var_2A0], r10d
0x1c0017f0e  movzx   r10d, cl
0x1c0017f12  mov     [rsp+310h+var_2A3], 1
0x1c0017f17  mov     [rsp+310h+var_2B0], r10b
0x1c0017f1c  jmp     loc_1C0017D03
0x1c0017f21  lock inc dword ptr [rbx+144h]
0x1c0017f28  movzx   r12d, word ptr [rax]
0x1c0017f2c  inc     si
0x1c0017f2f  cmp     si, r12w
0x1c0017f33  jnz     short loc_1C0017F21
0x1c0017f35  mov     [rsp+310h+var_2A0], esi
0x1c0017f39  jmp     loc_1C0017D25
0x1c0017f3e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1c0017f45  nop     dword ptr [rax+rax+00h]
0x1c0017f4a  test    al, al
0x1c0017f4c  jnz     loc_1C0017D6C
0x1c0017f52  cmp     cs:dword_1C012D0B4, 1
0x1c0017f59  jz      loc_1C0075DC1
  ... truncated ...
```
