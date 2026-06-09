# NgscbCheckParseHSTIResults(uchar *,ulong,bool *,_NGSCB_HSTI_RESULTS * *,_NGSCB_HSTI_PARSING_STATUS *)

- ea: `0x1800d4db0`
- end: `0x1800d5f52`
- name: `?NgscbCheckParseHSTIResults@@YAJPEAEKPEA_NPEAPEAU_NGSCB_HSTI_RESULTS@@PEAU_NGSCB_HSTI_PARSING_STATUS@@@Z`
- size: `4514`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, bool *, struct _NGSCB_HSTI_RESULTS **, struct _NGSCB_HSTI_PARSING_STATUS *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017dd8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180016da8`
- `0x1800379e4`
- `0x180037db0`
- `0x180037edc`
- `0x180038730`
- `0x18003caa4`
- `0x18003f658`
- `0x18003f87c`
- `0x180042448`
- `0x180042998`
- `0x180043f04`
- `0x18004426c`
- `0x1800445b4`
- `0x180044730`
- `0x1800450c4`
- `0x180045d24`
- `0x180060196`
- `0x1800d4db0`
- `0x1800d6b24`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800d5a49`
- `msvcrt!_stricmp` at `0x1800d5a49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5e7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5f1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5e7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ec8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5ef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5f1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d565f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5eb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5edd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5f07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d565f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5e8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5eb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5edd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5f07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5673`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5673`

## string_xrefs

- `0x1800d4ed7`: `ngscb_common_um`
- `0x1800d5095`: `ngscb_common_um`
- `0x1800d5144`: `ngscb_common_um`
- `0x1800d52c9`: `ngscb_common_um`
- `0x1800d53af`: `ngscb_common_um`
- `0x1800d5414`: `ngscb_common_um`
- `0x1800d54c2`: `ngscb_common_um`
- `0x1800d556f`: `ngscb_common_um`
- `0x1800d584c`: `ngscb_common_um`
- `0x1800d59a7`: `ngscb_common_um`
- `0x1800d5b3a`: `ngscb_common_um`
- `0x1800d5d0c`: `ngscb_common_um`

## pseudocode

```c
__int64 __fastcall NgscbCheckParseHSTIResults(
        unsigned __int8 *a1,
        unsigned int a2,
        bool *a3,
        struct _NGSCB_HSTI_RESULTS **a4,
        struct _NGSCB_HSTI_PARSING_STATUS *a5)
{
  unsigned __int8 *v7; // r14
  int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // r9d
  unsigned int i; // esi
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned __int8 *v17; // rcx
  unsigned int *v18; // r14
  int v19; // eax
  int v20; // edx
  int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // r14d
  unsigned __int8 *v27; // r9
  unsigned int j; // esi
  unsigned __int16 *v29; // rbx
  __int64 v30; // rax
  const EVENT_DESCRIPTOR *v31; // rcx
  PVOID *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // r11d
  unsigned int v37; // edx
  unsigned int v38; // eax
  unsigned int v39; // r14d
  HANDLE ProcessHeap; // rax
  void *v41; // rax
  struct _NGSCB_HSTI_RESULTS *v42; // r12
  unsigned int v43; // r8d
  unsigned int v44; // ecx
  unsigned int v45; // edx
  unsigned int v46; // eax
  unsigned __int8 *v47; // rsi
  unsigned int v48; // r9d
  unsigned int v49; // r13d
  unsigned __int8 *v50; // rbx
  unsigned int v51; // r10d
  unsigned __int8 *v52; // rsi
  __int64 v53; // rax
  unsigned int v54; // r12d
  unsigned __int8 *v55; // r11
  _BYTE *v56; // rcx
  unsigned int v57; // edx
  __int64 v58; // r14
  unsigned __int8 v59; // al
  __int64 v60; // rax
  unsigned __int8 v61; // al
  __int128 *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // r9
  char *v66; // r10
  char *v67; // rax
  __int128 v68; // xmm0
  _BYTE *v69; // r13
  bool v70; // al
  __int64 v71; // rax
  unsigned int v72; // ecx
  unsigned int v73; // eax
  unsigned int v74; // r8d
  _BYTE *v75; // rsi
  unsigned int v76; // r9d
  unsigned __int8 v77; // dl
  __int64 v78; // rax
  struct _NGSCB_HSTI_PARSING_STATUS *v79; // r13
  unsigned int k; // r14d
  unsigned __int8 *v81; // rsi
  unsigned int v82; // eax
  __int64 v83; // rax
  void *v84; // rdi
  HANDLE v85; // rax
  void *v86; // rdi
  HANDLE v87; // rax
  HANDLE v88; // rax
  char *v89; // rdi
  HANDLE v90; // rax
  unsigned __int16 *v91; // rdi
  HANDLE v92; // rax
  char v94; // [rsp+30h] [rbp-D0h]
  unsigned int Size; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int8 Size_4; // [rsp+38h] [rbp-C8h] BYREF
  void *v97; // [rsp+40h] [rbp-C0h]
  char v98; // [rsp+48h] [rbp-B8h] BYREF
  bool v99; // [rsp+49h] [rbp-B7h] BYREF
  unsigned int v100; // [rsp+4Ch] [rbp-B4h] BYREF
  char v101; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v102; // [rsp+58h] [rbp-A8h]
  unsigned int v103; // [rsp+60h] [rbp-A0h]
  int v104; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v105; // [rsp+68h] [rbp-98h]
  unsigned int v106; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v107; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  void *lpMem; // [rsp+80h] [rbp-80h] BYREF
  int v110; // [rsp+88h] [rbp-78h] BYREF
  char *String1; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v112; // [rsp+98h] [rbp-68h]
  struct _NGSCB_HSTI_PARSING_STATUS *v113; // [rsp+A0h] [rbp-60h]
  bool *v114; // [rsp+A8h] [rbp-58h]
  struct _NGSCB_HSTI_RESULTS **v115; // [rsp+B0h] [rbp-50h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *p_Size_4; // [rsp+D0h] [rbp-30h]
  __int64 v118; // [rsp+D8h] [rbp-28h]
  wchar_t *v119; // [rsp+E0h] [rbp-20h]
  __int64 v120; // [rsp+E8h] [rbp-18h]
  wchar_t *v121; // [rsp+F0h] [rbp-10h]
  int v122; // [rsp+F8h] [rbp-8h]
  int v123; // [rsp+FCh] [rbp-4h]
  unsigned __int16 v124[256]; // [rsp+110h] [rbp+10h] BYREF

  v105 = a2;
  v102 = a1;
  v7 = a1;
  v115 = a4;
  v114 = a3;
  v113 = a5;
  v104 = 0;
  Size = 0;
  Src = 0;
  lpMem = 0;
  Size_4 = 0;
  String1 = 0;
  v107 = 0;
  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x48u);
  v110 = 1;
  v98 = 1;
  v101 = 0;
  v99 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    memset_0(a5, 0, 0x5A18u);
  if ( !a3 )
  {
    v9 = -2147467261;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_247;
    v11 = 47;
    goto LABEL_9;
  }
  *a3 = 0;
  NgscbTryOpenEventLog();
  if ( a5 )
  {
    *(_DWORD *)a5 = a2;
    *((_DWORD *)a5 + 1) = *(_DWORD *)v7;
  }
  UserData.Ptr = (ULONGLONG)v7;
  p_Size_4 = (unsigned __int16 *)&v110;
  v12 = -1;
  *(_QWORD *)&UserData.Size = 4;
  v118 = 4;
  v119 = aNgscbCommonUm;
  do
    ++v12;
  while ( aNgscbCommonUm[v12] );
  v120 = (unsigned int)(2 * v12 + 2);
  NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_DATA_VERSION, 3u, &UserData);
  if ( *(_DWORD *)v7 != 1 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        *(unsigned int *)v7);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    v9 = -2147024883;
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 0x40) == 0 )
      goto LABEL_247;
    v11 = 49;
LABEL_9:
    WPP_SF_d(v10[2], v11, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, (unsigned int)v9);
    goto LABEL_247;
  }
  v13 = Size;
  v9 = 0;
  for ( i = 0; i < *((_DWORD *)v7 + 1); ++i )
  {
    if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(v7, i, v105) )
    {
      v16 = NgscbpHSTICheckProviderInfo(v15, i);
      v9 = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v16);
        if ( v9 < 0 )
          goto LABEL_247;
      }
      v17 = &v7[*(unsigned int *)&v7[12 * i + 8]];
      if ( a5 )
        ++*((_DWORD *)a5 + 2);
      v13 = Size;
      v18 = (unsigned int *)(v17 + 520);
      v19 = *((_DWORD *)v17 + 130);
      if ( Size )
      {
        if ( v19 != v104 )
        {
          NgscbpHSTIGetImplementationID(v17, v124);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, v21, (unsigned int)v124, v104, *v18);
          *(_QWORD *)&UserData.Size = 512;
          UserData.Ptr = (ULONGLONG)v124;
          v118 = 4;
          p_Size_4 = (unsigned __int16 *)&v104;
          v22 = -1;
          v119 = (wchar_t *)v18;
          v120 = 4;
          v121 = aNgscbCommonUm;
          do
            ++v22;
          while ( aNgscbCommonUm[v22] );
          v123 = 0;
          v122 = 2 * v22 + 2;
          NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_SEC_FEAT_SIZE_MISMATCH, 4u, &UserData);
          v13 = Size;
          if ( *v18 > Size )
          {
            v13 = *v18;
            Size = *v18;
          }
        }
      }
      else
      {
        v13 = *((_DWORD *)v17 + 130);
        Size = v13;
        v104 = v19;
      }
      v7 = v102;
    }
  }
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&Size;
    v23 = -1;
    p_Size_4 = aNgscbCommonUm;
    do
      ++v23;
    while ( aNgscbCommonUm[v23] );
    v118 = (unsigned int)(2 * v23 + 2);
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PROVIDER_COUNT, 2u, &UserData);
    goto LABEL_247;
  }
  v97 = 0;
  if ( a5 )
    *((_DWORD *)a5 + 5) = v13;
  v24 = HeapAllocateByByteCount<unsigned char>(&Src, v13);
  v9 = v24;
  if ( v24 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v24);
    if ( v9 < 0 )
      goto LABEL_236;
  }
  v25 = HeapAllocateByByteCount<unsigned char>(&lpMem, Size);
  v9 = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v25);
    if ( v9 < 0 )
      goto LABEL_236;
  }
  v94 = 0;
  v26 = -1;
  v103 = 0;
  memset_0(Src, 0, Size);
  memset_0(lpMem, 0, Size);
  v27 = v102;
  for ( j = 0; j < *((_DWORD *)v27 + 1); ++j )
  {
    if ( !(unsigned __int8)NgscbpHSTIHasProviderInfo(v27, j, v105) )
      continue;
    v29 = (unsigned __int16 *)&v27[*(unsigned int *)&v27[12 * j + 8]];
    if ( *(_DWORD *)v29 == 3 )
    {
      if ( a5 )
        ++*((_DWORD *)a5 + 3);
      if ( v103 + 1 < v103 )
      {
        v32 = (PVOID *)WPP_GLOBAL_Control;
        v9 = -2147024362;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v33 = 56;
LABEL_235:
          WPP_SF_d(v32[2], v33, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, 2147942934LL);
          goto LABEL_236;
        }
        goto LABEL_236;
      }
      ++v103;
      NgscbpHSTIGetImplementationID(v29, v124);
      if ( *((_DWORD *)v29 + 1) == 1 )
      {
        if ( a5 )
        {
          ++*((_DWORD *)a5 + 4);
          if ( *((_WORD *)a5 + 12) )
            StringCbCatW((unsigned __int16 *)a5 + 12, 0x200u, L"|");
          StringCbCatW((unsigned __int16 *)a5 + 12, 0x200u, v124);
        }
        if ( v26 != -1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v124);
          *(_QWORD *)&UserData.Size = 512;
          UserData.Ptr = (ULONGLONG)v124;
          v118 = 1;
          p_Size_4 = (unsigned __int16 *)&v98;
          v30 = -1;
          v119 = aNgscbCommonUm;
          do
            ++v30;
          while ( aNgscbCommonUm[v30] );
          v94 = 1;
          v31 = (const EVENT_DESCRIPTOR *)FVE_AUTODE_HSTI_REPORT_EXTRA_PLATSECROLEREF_PROVIDER;
          goto LABEL_103;
        }
        v26 = j;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v124);
        *(_QWORD *)&UserData.Size = 512;
        UserData.Ptr = (ULONGLONG)v124;
        v118 = 1;
        p_Size_4 = (unsigned __int16 *)&v98;
        v30 = -1;
        v119 = aNgscbCommonUm;
        do
          ++v30;
        while ( aNgscbCommonUm[v30] );
      }
      else
      {
        if ( a5 )
        {
          if ( *((_WORD *)a5 + 268) )
            StringCbCatW((unsigned __int16 *)a5 + 268, 0x800u, L"|");
          StringCbCatW((unsigned __int16 *)a5 + 268, 0x800u, v124);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v124);
        *(_QWORD *)&UserData.Size = 512;
        UserData.Ptr = (ULONGLONG)v124;
        v118 = 1;
        p_Size_4 = (unsigned __int16 *)&v101;
        v30 = -1;
        v119 = aNgscbCommonUm;
        do
          ++v30;
        while ( aNgscbCommonUm[v30] );
      }
      v31 = &FVE_AUTODE_HSTI_REPORT_PLATSECROLEREF_PROVIDER;
    }
    else
    {
      NgscbpHSTIGetImplementationID(&v27[*(unsigned int *)&v27[12 * j + 8]], v124);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)&WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          (unsigned int)v124,
          *(_DWORD *)v29);
      p_Size_4 = v29;
      UserData.Ptr = (ULONGLONG)v124;
      *(_QWORD *)&UserData.Size = 512;
      v30 = -1;
      v118 = 4;
      v119 = aNgscbCommonUm;
      do
        ++v30;
      while ( aNgscbCommonUm[v30] );
      v31 = (const EVENT_DESCRIPTOR *)FVE_AUTODE_HSTI_REPORT_UNKNOWN_VERSIONED_PROVIDER;
    }
LABEL_103:
    v120 = (unsigned int)(2 * v30 + 2);
    NgscbTryWriteEventLog(v31, 3u, &UserData);
    v27 = v102;
  }
  if ( v26 == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
    v34 = -1;
    UserData.Ptr = (ULONGLONG)aNgscbCommonUm;
    do
      ++v34;
    while ( aNgscbCommonUm[v34] );
    UserData.Reserved = 0;
    UserData.Size = 2 * v34 + 2;
    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_NO_PLATSECROLEREF_PROVIDER, 1u, &UserData);
    v94 = 1;
  }
  if ( Size >= 0xFFFFFDF8 )
  {
    v32 = (PVOID *)WPP_GLOBAL_Control;
    v9 = -2147024362;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v33 = 61;
      goto LABEL_235;
    }
    goto LABEL_236;
  }
  v100 = Size + 520;
  v35 = ULongLongToULong(v103 * (unsigned __int64)(Size + 520), &v100);
  v9 = v35;
  if ( v35 )
  {
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v35);
      v36 = Size;
      v32 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 < 0 )
      goto LABEL_236;
  }
  else
  {
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  v37 = v100 + v36;
  if ( v100 + v36 < v100 )
  {
    v9 = -2147024362;
    if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x40) != 0 )
    {
      v33 = 63;
      goto LABEL_235;
    }
    goto LABEL_236;
  }
  v38 = v37 + v36;
  if ( v37 + v36 < v37 )
  {
    v9 = -2147024362;
    if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x40) != 0 )
    {
      v33 = 64;
      goto LABEL_235;
    }
    goto LABEL_236;
  }
  v39 = v38 + 28;
  if ( v38 + 28 < v38 )
  {
    v9 = -2147024362;
    if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x40) != 0 )
    {
      v33 = 65;
      goto LABEL_235;
    }
LABEL_236:
    v42 = (struct _NGSCB_HSTI_RESULTS *)v97;
  }
  else
  {
    if ( v39 < 0x1CuLL )
    {
      v9 = -2147024809;
LABEL_130:
      v100 = v9;
      if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x40) != 0 )
        WPP_SF_d(v32[2], 66, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, (unsigned int)v9);
      goto LABEL_236;
    }
    ProcessHeap = GetProcessHeap();
    v41 = HeapAlloc(ProcessHeap, 0, v39);
    if ( !v41 )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      v9 = -2147024882;
      goto LABEL_130;
    }
    v97 = v41;
    v9 = 0;
    v100 = 0;
    v42 = (struct _NGSCB_HSTI_RESULTS *)v41;
    memset_0(v41, 0, v39);
    v43 = v103;
    *((_DWORD *)v42 + 5) = v103;
    *((_DWORD *)v42 + 6) = -1;
    *(_DWORD *)v42 = v39;
    *((_DWORD *)v42 + 4) = 28;
    v44 = v43 * (Size + 520) + 28;
    *((_DWORD *)v42 + 1) = v44;
    v45 = v44 + Size;
    *((_DWORD *)v42 + 2) = v44 + Size;
    v46 = Size;
    *((_DWORD *)v42 + 3) = Size;
    if ( v45 >= v44 && v44 >= 0x1C && v45 + v46 == v39 )
    {
      v47 = v102;
      v48 = 0;
      v106 = 0;
      v49 = 0;
      if ( *((_DWORD *)v102 + 1) )
      {
        v50 = v102;
        do
        {
          if ( v48 >= v43 )
            break;
          if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(v50, v49, v105) )
          {
            v52 = &v50[*(unsigned int *)&v50[12 * v49 + 8]];
            if ( *(_DWORD *)v52 == 3 )
            {
              v53 = *((unsigned int *)v52 + 130);
              v54 = v51;
              v55 = &v52[2 * v53 + 524];
              v112 = v55;
              if ( (_DWORD)v53 )
              {
                v56 = lpMem;
                while ( 1 )
                {
                  v57 = Size;
                  if ( v54 >= Size )
                    break;
                  v58 = v54;
                  v59 = v52[v54 + 524];
                  if ( *((_DWORD *)v52 + 1) == 1 )
                  {
                    *((_BYTE *)Src + v54) |= v59;
                    if ( *((_DWORD *)v97 + 6) == -1 )
                      *((_DWORD *)v97 + 6) = v48;
                  }
                  else if ( v59 )
                  {
                    NgscbpHSTIGetImplementationID(v52, v124);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        68,
                        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                        v124);
                    *(_QWORD *)&UserData.Size = 512;
                    UserData.Ptr = (ULONGLONG)v124;
                    v60 = -1;
                    p_Size_4 = aNgscbCommonUm;
                    do
                      ++v60;
                    while ( aNgscbCommonUm[v60] );
                    v118 = (unsigned int)(2 * v60 + 2);
                    NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PLATSECROLEREF_PROVIDER, 2u, &UserData);
                    v48 = v106;
                    v55 = v112;
                    v56 = lpMem;
                    v94 = 1;
                  }
                  v61 = v55[v54++];
                  v56[v58] |= v61;
                  if ( v54 >= *((_DWORD *)v52 + 130) )
                    goto LABEL_156;
                }
              }
              else
              {
LABEL_156:
                v57 = Size;
              }
              v42 = (struct _NGSCB_HSTI_RESULTS *)v97;
              v62 = (__int128 *)(v52 + 8);
              v63 = v48;
              v64 = 4;
              v65 = *((unsigned int *)v97 + 4);
              v66 = (char *)v97 + v63 * (*((unsigned int *)v97 + 3) + 520LL);
              *(_DWORD *)&v66[v65] = v57 + 520;
              *(_DWORD *)&v66[v65 + 4] = Size;
              v67 = &v66[v65 + 8];
              do
              {
                v68 = *v62;
                v62 += 8;
                *(_OWORD *)v67 = v68;
                v67 += 128;
                *((_OWORD *)v67 - 7) = *(v62 - 7);
                *((_OWORD *)v67 - 6) = *(v62 - 6);
                *((_OWORD *)v67 - 5) = *(v62 - 5);
                *((_OWORD *)v67 - 4) = *(v62 - 4);
                *((_OWORD *)v67 - 3) = *(v62 - 3);
                *((_OWORD *)v67 - 2) = *(v62 - 2);
                *((_OWORD *)v67 - 1) = *(v62 - 1);
                --v64;
              }
              while ( v64 );
              memcpy_0(&v66[v65 + 520], v55, Size);
              v48 = ++v106;
            }
          }
          v43 = v103;
          ++v49;
        }
        while ( v49 < *((_DWORD *)v50 + 1) );
        v9 = v100;
        v47 = v102;
      }
      memcpy_0((char *)v42 + *((unsigned int *)v42 + 1), Src, Size);
      v69 = lpMem;
      v70 = (*((_BYTE *)lpMem + 1) & 8) != 0;
      *(_QWORD *)&UserData.Size = 4;
      v99 = v70;
      p_Size_4 = aNgscbCommonUm;
      UserData.Ptr = (ULONGLONG)&v99;
      v71 = -1;
      do
        ++v71;
      while ( aNgscbCommonUm[v71] );
      v118 = (unsigned int)(2 * v71 + 2);
      NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_THUNDERBOLT_CONFIG, 2u, &UserData);
      if ( NgscbGet_TEST_BooleanOverride(L"ReportDEPlatformHstiSecureThunderboltBit", (bool *)&Size_4)
        && Size_4
        && (int)NgscbGetCpuVendorA(&String1) >= 0
        && String1
        && !_stricmp(String1, "GenuineIntel")
        && Size >= 2 )
      {
        if ( (v69[1] & 8) != 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
          v69[1] |= 8u;
        }
      }
      memcpy_0((char *)v42 + *((unsigned int *)v42 + 2), v69, Size);
      v72 = Size;
      v73 = 0;
      v100 = 0;
      v74 = 0;
      if ( Size )
      {
        v75 = Src;
        v76 = 0;
        do
        {
          v77 = v75[v76] & ~v69[v73];
          Size_4 = v77;
          if ( v77 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                71,
                &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                v74,
                v77);
            *(_QWORD *)&UserData.Size = 4;
            UserData.Ptr = (ULONGLONG)&v100;
            v118 = 1;
            p_Size_4 = (unsigned __int16 *)&Size_4;
            v78 = -1;
            v119 = aNgscbCommonUm;
            do
              ++v78;
            while ( aNgscbCommonUm[v78] );
            v120 = (unsigned int)(2 * v78 + 2);
            NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_MISSING_FEATURES, 3u, &UserData);
            v72 = Size;
            v74 = v100;
            v94 = 1;
          }
          v100 = ++v74;
          v73 = v74;
          v76 = v74;
        }
        while ( v74 < v72 );
        v47 = v102;
      }
      if ( v94 )
      {
        v79 = v113;
        for ( k = 0; k < *((_DWORD *)v47 + 1); ++k )
        {
          if ( (unsigned __int8)NgscbpHSTIHasProviderInfo(v47, k, v105) )
          {
            v81 = &v47[*(unsigned int *)&v47[12 * k + 8]];
            if ( *(_DWORD *)v81 == 3 )
            {
              v82 = HeapAllocateByByteCount<unsigned short>(&v107, 20480);
              v9 = v82;
              if ( v82 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    72,
                    &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                    v82);
                if ( v9 < 0 )
                  goto LABEL_236;
              }
              NgscbpHSTIGetImplementationID(v81, v124);
              if ( v107
                && (int)StringCchCopyNW(
                          v107,
                          0x2800u,
                          (const unsigned __int16 *)&v81[2 * *((unsigned int *)v81 + 130)
                                                       + 524
                                                       + *((unsigned int *)v81 + 130)],
                          0x27FFu) < 0 )
              {
                *(_DWORD *)v107 = 63;
              }
              if ( v79 )
              {
                if ( *((_WORD *)v79 + 1292) )
                  StringCbCatW((unsigned __int16 *)v79 + 1292, 0x5000u, L"|");
                StringCbCatW((unsigned __int16 *)v79 + 1292, 0x5000u, v107);
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  73,
                  (unsigned int)&WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                  (unsigned int)v124,
                  (__int64)v107);
              *(_QWORD *)&UserData.Size = 512;
              UserData.Ptr = (ULONGLONG)v124;
              p_Size_4 = v107;
              v83 = -1;
              v118 = 20480;
              v119 = aNgscbCommonUm;
              do
                ++v83;
              while ( aNgscbCommonUm[v83] );
              v120 = (unsigned int)(2 * v83 + 2);
              NgscbTryWriteEventLog(&FVE_AUTODE_HSTI_REPORT_PROVIDER_ERROR, 3u, &UserData);
            }
            v47 = v102;
          }
        }
        v42 = (struct _NGSCB_HSTI_RESULTS *)v97;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
        *v114 = 1;
      }
      *v115 = v42;
      v42 = 0;
    }
    else
    {
      v9 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          2147549183LL);
    }
  }
  v84 = Src;
  if ( Src )
  {
    v85 = GetProcessHeap();
    HeapFree(v85, 0, v84);
  }
  v86 = lpMem;
  if ( lpMem )
  {
    v87 = GetProcessHeap();
    HeapFree(v87, 0, v86);
  }
  if ( v42 )
  {
    v88 = GetProcessHeap();
    HeapFree(v88, 0, v42);
  }
  v89 = String1;
  if ( String1 )
  {
    v90 = GetProcessHeap();
    HeapFree(v90, 0, v89);
  }
  v91 = v107;
  if ( v107 )
  {
    v92 = GetProcessHeap();
    HeapFree(v92, 0, v91);
  }
LABEL_247:
  NgscbTryCloseEventLog();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d4db0  push    rbp
0x1800d4db2  push    rbx
0x1800d4db3  push    rsi
0x1800d4db4  push    rdi
0x1800d4db5  push    r12
0x1800d4db7  push    r13
0x1800d4db9  push    r14
0x1800d4dbb  push    r15
0x1800d4dbd  lea     rbp, [rsp-228h]
0x1800d4dc5  sub     rsp, 328h
0x1800d4dcc  mov     rax, cs:__security_cookie
0x1800d4dd3  xor     rax, rsp
0x1800d4dd6  mov     [rbp+260h+var_50], rax
0x1800d4ddd  mov     r12, [rbp+260h+arg_20]
0x1800d4de4  xor     r15d, r15d
0x1800d4de7  mov     rbx, r8
0x1800d4dea  mov     [rsp+360h+var_2F8], edx
0x1800d4dee  mov     edi, edx
0x1800d4df0  mov     [rsp+360h+var_308], rcx
0x1800d4df5  mov     r14, rcx
0x1800d4df8  mov     [rbp+260h+var_2B0], r9
0x1800d4dfc  lea     r8d, [r15+48h]; Size
0x1800d4e00  mov     [rbp+260h+var_2B8], rbx
0x1800d4e04  xor     edx, edx; Val
0x1800d4e06  mov     [rbp+260h+var_2C0], r12
0x1800d4e0a  lea     rcx, [rbp+260h+UserData.Size]; void *
0x1800d4e0e  mov     [rsp+360h+var_2FC], r15d
0x1800d4e13  mov     rsi, r9
0x1800d4e16  mov     dword ptr [rsp+360h+Size], r15d
0x1800d4e1b  mov     [rsp+360h+Src], r15
0x1800d4e20  mov     [rbp+260h+lpMem], r15
0x1800d4e24  mov     byte ptr [rsp+360h+Size+4], r15b
0x1800d4e29  mov     [rbp+260h+String1], r15
0x1800d4e2d  mov     [rsp+360h+var_2F0], r15
0x1800d4e32  mov     [rbp+260h+UserData.Ptr], r15
0x1800d4e36  call    memset_0
0x1800d4e3b  mov     [rbp+260h+var_2D8], 1
0x1800d4e42  mov     [rsp+360h+var_318], 1
0x1800d4e47  mov     [rsp+360h+var_310], r15b
0x1800d4e4c  mov     [rsp+360h+var_317], r15b
0x1800d4e51  test    rsi, rsi
0x1800d4e54  jz      short loc_1800D4E59
0x1800d4e56  mov     [rsi], r15
0x1800d4e59  test    r12, r12
0x1800d4e5c  jz      short loc_1800D4E6E
0x1800d4e5e  xor     edx, edx; Val
0x1800d4e60  mov     r8d, 5A18h; Size
0x1800d4e66  mov     rcx, r12; void *
0x1800d4e69  call    memset_0
0x1800d4e6e  test    rbx, rbx
0x1800d4e71  jnz     short loc_1800D4EB6
0x1800d4e73  mov     ebx, 80004003h
0x1800d4e78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4e7f  lea     rdi, WPP_GLOBAL_Control
0x1800d4e86  cmp     rcx, rdi
0x1800d4e89  jz      loc_1800D5F27
0x1800d4e8f  test    byte ptr [rcx+1Ch], 40h
0x1800d4e93  jz      loc_1800D5F27
0x1800d4e99  mov     edx, 2Fh ; '/'
0x1800d4e9e  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d4ea5  mov     rcx, [rcx+10h]
0x1800d4ea9  mov     r9d, ebx
0x1800d4eac  call    WPP_SF_d
0x1800d4eb1  jmp     loc_1800D5F27
0x1800d4eb6  mov     [rbx], r15b
0x1800d4eb9  call    ?NgscbTryOpenEventLog@@YAXXZ; NgscbTryOpenEventLog(void)
0x1800d4ebe  test    r12, r12
0x1800d4ec1  jz      short loc_1800D4ECF
0x1800d4ec3  mov     [r12], edi
0x1800d4ec7  mov     eax, [r14]
0x1800d4eca  mov     [r12+4], eax
0x1800d4ecf  lea     rax, [rbp+260h+var_2D8]
0x1800d4ed3  mov     [rbp+260h+UserData.Ptr], r14
0x1800d4ed7  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x1800d4ede  mov     [rbp+260h+var_290], rax
0x1800d4ee2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d4ee6  mov     qword ptr [rbp+260h+UserData.Size], 4
0x1800d4eee  mov     [rbp+260h+var_288], 4
0x1800d4ef6  mov     [rbp+260h+var_280], rcx
0x1800d4efa  inc     rax
0x1800d4efd  cmp     [rcx+rax*2], r15w
0x1800d4f02  jnz     short loc_1800D4EFA
0x1800d4f04  lea     eax, ds:2[rax*2]
0x1800d4f0b  mov     dword ptr [rbp+260h+var_278+4], r15d
0x1800d4f0f  lea     r8, [rbp+260h+UserData]; UserData
0x1800d4f13  mov     dword ptr [rbp+260h+var_278], eax
0x1800d4f16  mov     edx, 3; UserDataCount
0x1800d4f1b  lea     rcx, FVE_AUTODE_HSTI_REPORT_DATA_VERSION; EventDescriptor
0x1800d4f22  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800d4f27  cmp     dword ptr [r14], 1
0x1800d4f2b  jz      short loc_1800D4F8D
0x1800d4f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4f34  lea     rdi, WPP_GLOBAL_Control
0x1800d4f3b  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d4f42  cmp     rcx, rdi
0x1800d4f45  jz      short loc_1800D4F68
0x1800d4f47  test    byte ptr [rcx+1Ch], 2
0x1800d4f4b  jz      short loc_1800D4F68
0x1800d4f4d  mov     r9d, [r14]
0x1800d4f50  mov     edx, 30h ; '0'
0x1800d4f55  mov     rcx, [rcx+10h]
0x1800d4f59  mov     r8, r15
0x1800d4f5c  call    WPP_SF_d
0x1800d4f61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4f68  mov     ebx, 8007000Dh
0x1800d4f6d  cmp     rcx, rdi
0x1800d4f70  jz      loc_1800D5F27
0x1800d4f76  test    byte ptr [rcx+1Ch], 40h
0x1800d4f7a  jz      loc_1800D5F27
0x1800d4f80  mov     edx, 31h ; '1'
0x1800d4f85  mov     r8, r15
0x1800d4f88  jmp     loc_1800D4EA5
0x1800d4f8d  mov     r9d, dword ptr [rsp+360h+Size]
0x1800d4f92  lea     rdi, WPP_GLOBAL_Control
0x1800d4f99  mov     ebx, r15d
0x1800d4f9c  mov     esi, r15d
0x1800d4f9f  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d4fa6  mov     r13d, 40h ; '@'
0x1800d4fac  cmp     esi, [r14+4]
0x1800d4fb0  jnb     loc_1800D510C
0x1800d4fb6  mov     r8d, [rsp+360h+var_2F8]
0x1800d4fbb  mov     edx, esi
0x1800d4fbd  mov     rcx, r14
0x1800d4fc0  call    NgscbpHSTIHasProviderInfo
0x1800d4fc5  test    al, al
0x1800d4fc7  jz      loc_1800D5105
0x1800d4fcd  mov     edx, esi
0x1800d4fcf  call    NgscbpHSTICheckProviderInfo
0x1800d4fd4  mov     ebx, eax
0x1800d4fd6  test    eax, eax
0x1800d4fd8  jz      short loc_1800D5008
0x1800d4fda  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4fe1  cmp     rcx, rdi
0x1800d4fe4  jz      short loc_1800D5000
0x1800d4fe6  test    [rcx+1Ch], r13b
0x1800d4fea  jz      short loc_1800D5000
0x1800d4fec  mov     rcx, [rcx+10h]
0x1800d4ff0  mov     edx, 32h ; '2'
0x1800d4ff5  mov     r9d, eax
0x1800d4ff8  mov     r8, r15
0x1800d4ffb  call    WPP_SF_d
0x1800d5000  test    ebx, ebx
0x1800d5002  js      loc_1800D5F27
0x1800d5008  mov     eax, esi
0x1800d500a  lea     rcx, [rax+rax*2]
0x1800d500e  mov     ecx, [r14+rcx*4+8]
0x1800d5013  add     rcx, r14
0x1800d5016  test    r12, r12
0x1800d5019  jz      short loc_1800D5020
0x1800d501b  inc     dword ptr [r12+8]
0x1800d5020  mov     r9d, dword ptr [rsp+360h+Size]
0x1800d5025  lea     r14, [rcx+208h]
0x1800d502c  mov     eax, [r14]
0x1800d502f  test    r9d, r9d
0x1800d5032  jnz     short loc_1800D5044
0x1800d5034  mov     r9d, eax
0x1800d5037  mov     dword ptr [rsp+360h+Size], eax
0x1800d503b  mov     [rsp+360h+var_2FC], eax
0x1800d503f  jmp     loc_1800D5100
0x1800d5044  cmp     eax, [rsp+360h+var_2FC]
0x1800d5048  jz      loc_1800D5100
0x1800d504e  lea     rdx, [rbp+260h+var_250]
0x1800d5052  call    NgscbpHSTIGetImplementationID
0x1800d5057  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d505e  cmp     rcx, rdi
0x1800d5061  jz      short loc_1800D5085
0x1800d5063  test    byte ptr [rcx+1Ch], 4
0x1800d5067  jz      short loc_1800D5085
0x1800d5069  mov     eax, [r14]
0x1800d506c  lea     r9, [rbp+260h+var_250]
0x1800d5070  mov     rcx, [rcx+10h]
0x1800d5074  mov     [rsp+360h+var_338], eax
0x1800d5078  mov     eax, [rsp+360h+var_2FC]
0x1800d507c  mov     dword ptr [rsp+360h+var_340], eax
0x1800d5080  call    WPP_SF_Sdd
0x1800d5085  lea     rax, [rbp+260h+var_250]
0x1800d5089  mov     qword ptr [rbp+260h+UserData.Size], 200h
0x1800d5091  mov     [rbp+260h+UserData.Ptr], rax
0x1800d5095  lea     rdx, aNgscbCommonUm; "ngscb_common_um"
0x1800d509c  lea     rax, [rsp+360h+var_2FC]
0x1800d50a1  mov     [rbp+260h+var_288], 4
0x1800d50a9  xor     ecx, ecx
0x1800d50ab  mov     [rbp+260h+var_290], rax
0x1800d50af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d50b3  mov     [rbp+260h+var_280], r14
0x1800d50b7  mov     [rbp+260h+var_278], 4
0x1800d50bf  mov     [rbp+260h+var_270], rdx
0x1800d50c3  inc     rax
0x1800d50c6  cmp     [rdx+rax*2], cx
0x1800d50ca  jnz     short loc_1800D50C3
0x1800d50cc  lea     eax, ds:2[rax*2]
0x1800d50d3  mov     [rbp+260h+var_264], ecx
0x1800d50d6  lea     rcx, FVE_AUTODE_HSTI_REPORT_SEC_FEAT_SIZE_MISMATCH; EventDescriptor
0x1800d50dd  mov     [rbp+260h+var_268], eax
0x1800d50e0  lea     r8, [rbp+260h+UserData]; UserData
0x1800d50e4  mov     edx, 4; UserDataCount
0x1800d50e9  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800d50ee  mov     r9d, dword ptr [rsp+360h+Size]
0x1800d50f3  cmp     [r14], r9d
0x1800d50f6  jbe     short loc_1800D5100
0x1800d50f8  mov     r9d, [r14]
0x1800d50fb  mov     dword ptr [rsp+360h+Size], r9d
0x1800d5100  mov     r14, [rsp+360h+var_308]
0x1800d5105  inc     esi
0x1800d5107  jmp     loc_1800D4FAC
0x1800d510c  xor     edx, edx
0x1800d510e  test    r9d, r9d
0x1800d5111  jnz     short loc_1800D5187
0x1800d5113  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d511a  cmp     rcx, rdi
0x1800d511d  jz      short loc_1800D5137
0x1800d511f  test    byte ptr [rcx+1Ch], 4
0x1800d5123  jz      short loc_1800D5137
0x1800d5125  mov     rcx, [rcx+10h]
0x1800d5129  lea     edx, [r9+34h]
0x1800d512d  mov     r8, r15
0x1800d5130  call    WPP_SF_
0x1800d5135  xor     edx, edx
0x1800d5137  lea     rax, [rsp+360h+Size]
0x1800d513c  mov     qword ptr [rbp+260h+UserData.Size], 4
0x1800d5144  lea     rcx, aNgscbCommonUm; "ngscb_common_um"
0x1800d514b  mov     [rbp+260h+UserData.Ptr], rax
0x1800d514f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d5153  mov     [rbp+260h+var_290], rcx
0x1800d5157  inc     rax
0x1800d515a  cmp     [rcx+rax*2], dx
0x1800d515e  jnz     short loc_1800D5157
0x1800d5160  lea     eax, ds:2[rax*2]
0x1800d5167  mov     dword ptr [rbp+260h+var_288+4], edx
0x1800d516a  mov     edx, 2; UserDataCount
0x1800d516f  mov     dword ptr [rbp+260h+var_288], eax
0x1800d5172  lea     r8, [rbp+260h+UserData]; UserData
0x1800d5176  lea     rcx, FVE_AUTODE_HSTI_REPORT_PROVIDER_COUNT; EventDescriptor
0x1800d517d  call    ?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x1800d5182  jmp     loc_1800D5F27
0x1800d5187  mov     [rsp+360h+var_320], rdx
0x1800d518c  test    r12, r12
0x1800d518f  jz      short loc_1800D5196
0x1800d5191  mov     [r12+14h], r9d
0x1800d5196  mov     edx, r9d
0x1800d5199  lea     rcx, [rsp+360h+Src]
0x1800d519e  call    ??$HeapAllocateByByteCount@E@@YAJPEAPEAE_K@Z; HeapAllocateByByteCount<uchar>(uchar * *,unsigned __int64)
0x1800d51a3  mov     ebx, eax
0x1800d51a5  test    eax, eax
0x1800d51a7  jz      short loc_1800D51D7
0x1800d51a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d51b0  cmp     rcx, rdi
0x1800d51b3  jz      short loc_1800D51CF
0x1800d51b5  test    [rcx+1Ch], r13b
0x1800d51b9  jz      short loc_1800D51CF
0x1800d51bb  mov     rcx, [rcx+10h]
0x1800d51bf  mov     edx, 35h ; '5'
0x1800d51c4  mov     r9d, eax
0x1800d51c7  mov     r8, r15
0x1800d51ca  call    WPP_SF_d
0x1800d51cf  test    ebx, ebx
0x1800d51d1  js      loc_1800D5E57
0x1800d51d7  mov     edx, dword ptr [rsp+360h+Size]
0x1800d51db  lea     rcx, [rbp+260h+lpMem]
0x1800d51df  call    ??$HeapAllocateByByteCount@E@@YAJPEAPEAE_K@Z; HeapAllocateByByteCount<uchar>(uchar * *,unsigned __int64)
0x1800d51e4  mov     ebx, eax
0x1800d51e6  test    eax, eax
0x1800d51e8  jz      short loc_1800D5218
0x1800d51ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d51f1  cmp     rcx, rdi
0x1800d51f4  jz      short loc_1800D5210
0x1800d51f6  test    [rcx+1Ch], r13b
0x1800d51fa  jz      short loc_1800D5210
0x1800d51fc  mov     rcx, [rcx+10h]
0x1800d5200  mov     edx, 36h ; '6'
0x1800d5205  mov     r9d, eax
0x1800d5208  mov     r8, r15
0x1800d520b  call    WPP_SF_d
0x1800d5210  test    ebx, ebx
0x1800d5212  js      loc_1800D5E57
0x1800d5218  mov     r8d, dword ptr [rsp+360h+Size]; Size
0x1800d521d  xor     ebx, ebx
0x1800d521f  mov     rcx, [rsp+360h+Src]; void *
0x1800d5224  xor     edx, edx; Val
0x1800d5226  mov     [rsp+360h+var_330], bl
0x1800d522a  or      r14d, 0FFFFFFFFh
0x1800d522e  mov     [rsp+360h+var_300], ebx
0x1800d5232  call    memset_0
0x1800d5237  mov     r8d, dword ptr [rsp+360h+Size]; Size
0x1800d523c  xor     edx, edx; Val
0x1800d523e  mov     rcx, [rbp+260h+lpMem]; void *
0x1800d5242  call    memset_0
0x1800d5247  mov     r9, [rsp+360h+var_308]
0x1800d524c  mov     esi, ebx
0x1800d524e  cmp     esi, [r9+4]
0x1800d5252  jnb     loc_1800D5546
0x1800d5258  mov     r8d, [rsp+360h+var_2F8]
0x1800d525d  mov     edx, esi
0x1800d525f  mov     rcx, r9
0x1800d5262  call    NgscbpHSTIHasProviderInfo
0x1800d5267  test    al, al
0x1800d5269  jz      loc_1800D5512
0x1800d526f  mov     eax, esi
0x1800d5271  lea     rcx, [rax+rax*2]
0x1800d5275  mov     ebx, [r9+rcx*4+8]
  ... truncated ...
```
