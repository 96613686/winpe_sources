# PhonebookEntryToRasEntry

- ea: `0x180012ff8`
- end: `0x180015227`
- name: `PhonebookEntryToRasEntry`
- size: `8751`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028050`
- `0x18002d410`

## callees

- `0x180001e10`
- `0x180006afc`
- `0x180009cb4`
- `0x18000a720`
- `0x180012f7c`
- `0x180012ff8`
- `0x180015230`
- `0x1800153a8`
- `0x180015664`
- `0x1800157e8`
- `0x180015894`
- `0x1800203dc`
- `0x18003e0a8`
- `0x18004e580`
- `0x18004e984`
- `0x18007e3a8`
- `0x18007e5f0`
- `0x18007f140`
- `0x1800a4dac`
- `0x1800c1288`
- `0x1800c1ef4`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!_stricmp` at `0x180013bad`
- `msvcrt!_stricmp` at `0x180013bad`
- `msvcrt!_wcslwr` at `0x1800147f1`
- `msvcrt!_wcslwr` at `0x1800147f1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013bdd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014277`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013bdd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180014277`
- `rtutils!TracePrintfExA` at `0x180014032`
- `rtutils!TracePrintfExA` at `0x1800146b3`
- `rtutils!TracePrintfExA` at `0x180014032`
- `rtutils!TracePrintfExA` at `0x1800146b3`

## string_xrefs

- `0x180014026`: `StringCchCopy failed due to error 0x%x`
- `0x1800146a7`: `StringCchCopy failed due to error 0x%x`

## pseudocode

```c
__int64 __fastcall PhonebookEntryToRasEntry(int a1, __int64 a2, int a3, unsigned int *a4, unsigned int *a5)
{
  unsigned int v8; // r8d
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r13
  unsigned int SizeofRasentry; // eax
  unsigned int v15; // ebx
  __int64 v16; // r15
  unsigned int v17; // r15d
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  _WORD *v22; // r15
  __int64 v23; // rax
  __int64 v24; // rax
  size_t v25; // r8
  _QWORD *v26; // rcx
  __int64 v27; // r12
  __int64 v28; // r13
  __int64 v29; // rax
  __int64 v30; // r15
  unsigned int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // r12
  __int64 PhoneNode; // rax
  _DWORD *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // eax
  unsigned int v38; // ebx
  _DWORD *v39; // rcx
  __int64 v40; // rdx
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rcx
  unsigned int RasDevices; // eax
  unsigned int i; // ebx
  __int64 v52; // r8
  unsigned int v53; // eax
  unsigned int v54; // eax
  __int64 v55; // rbx
  __int64 v56; // r13
  unsigned int v57; // r15d
  __int64 *v58; // rax
  __int64 v59; // rax
  _WORD *v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // eax
  wchar_t *v63; // rcx
  __int64 v64; // rdx
  char *v65; // r10
  _WORD *v66; // r9
  _WORD *v67; // rdx
  unsigned int v68; // eax
  wchar_t *v69; // r13
  _QWORD **v70; // rax
  _QWORD *j; // rax
  __int64 v72; // rbx
  _WORD *v73; // rax
  unsigned int v74; // eax
  unsigned int v75; // eax
  _WORD *v76; // r15
  __int64 v77; // r12
  _QWORD *v78; // r10
  int v79; // ecx
  int v80; // ecx
  int v81; // ecx
  bool v82; // zf
  int v83; // ecx
  unsigned int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // r9
  int v87; // ecx
  int v88; // ecx
  wchar_t *v89; // rcx
  const WCHAR *v90; // rax
  __int64 v91; // r9
  _WORD *v92; // r8
  _WORD *v93; // rdx
  unsigned int RasmanDeviceType; // eax
  int v95; // r15d
  _OWORD *v96; // rax
  int v97; // eax
  unsigned int v98; // eax
  unsigned int v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // eax
  unsigned int v102; // eax
  unsigned int v103; // eax
  unsigned int v104; // eax
  _WORD *v105; // rax
  unsigned int v106; // eax
  __int64 v107; // r9
  unsigned int v108; // eax
  _QWORD *v109; // rcx
  __int64 v110; // r9
  unsigned int v111; // eax
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v113; // [rsp+38h] [rbp-C8h]
  int v114; // [rsp+3Ch] [rbp-C4h]
  __int64 v115; // [rsp+40h] [rbp-C0h]
  size_t Size; // [rsp+48h] [rbp-B8h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+50h] [rbp-B0h] BYREF
  STRSAFE_LPWSTR v118; // [rsp+58h] [rbp-A8h] BYREF
  char String2[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v120[270]; // [rsp+62h] [rbp-9Eh] BYREF

  LODWORD(v118) = a3;
  v114 = a1;
  v8 = a1;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 467, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v8, a3);
    v9 = WPP_GLOBAL_Control;
    v8 = v114;
  }
  v10 = **(_QWORD **)(a2 + 32);
  if ( !v10 )
  {
    if ( v9 == &WPP_GLOBAL_Control )
      return 623;
    if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      WPP_SF_d(v9[2], 468, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 623);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x800) == 0 || *((_BYTE *)v9 + 25) < 6u )
      return 623;
    v11 = 469;
LABEL_23:
    WPP_SF_d(v9[2], v11, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 623);
    return 623;
  }
  v12 = *(_QWORD *)(v10 + 16);
  v115 = v12;
  if ( !v12 )
  {
    if ( v9 == &WPP_GLOBAL_Control )
      return 623;
    if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      WPP_SF_d(v9[2], 470, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 623);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 == &WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x800) == 0 || *((_BYTE *)v9 + 25) < 6u )
      return 623;
    v11 = 471;
    goto LABEL_23;
  }
  v113 = 0;
  if ( a4 )
  {
    v15 = *a4;
  }
  else
  {
    SizeofRasentry = GetSizeofRasentry(v8);
    v9 = WPP_GLOBAL_Control;
    v15 = SizeofRasentry;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    WPP_SF_d(v9[2], 472, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
    v9 = WPP_GLOBAL_Control;
  }
  v16 = *(_QWORD *)(v12 + 168);
  if ( v16 )
    v17 = *(_DWORD *)(v16 + 16);
  else
    v17 = 0;
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    WPP_SF_d(v9[2], 473, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v17);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v17 )
  {
    v18 = **(_QWORD **)(v12 + 168);
    if ( !v18 )
    {
      if ( v9 != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 2u )
        {
          WPP_SF_d(v9[2], 474, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
        {
          v19 = 475;
LABEL_382:
          WPP_SF_d(v9[2], v19, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
        }
      }
      return 625;
    }
    if ( (*(_BYTE *)(a2 + 136) & 2) != 0 )
    {
      v18 = *(_QWORD *)(v18 + 8);
      --v17;
    }
    else if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    {
      WPP_SF_(v9[2], 476, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    v113 = v17;
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    {
      WPP_SF_d(v9[2], 477, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v17);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v17 )
    {
      while ( v18 )
      {
        v20 = *(_QWORD *)(v18 + 16);
        if ( !v20 )
        {
          if ( v9 != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 2u )
            {
              WPP_SF_d(v9[2], 478, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
            {
              v19 = 479;
              goto LABEL_382;
            }
          }
          return 625;
        }
        v21 = *(_QWORD *)(v20 + 16);
        if ( !v21 )
        {
          if ( v9 != &WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 2u )
            {
              WPP_SF_d(v9[2], 480, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
            {
              v19 = 481;
              goto LABEL_382;
            }
          }
          return 625;
        }
        v22 = *(_WORD **)(v20 + 40);
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v21 + 2 * v23) );
        v15 += 2 * v23 + 2;
        if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
        {
          WPP_SF_d(v9[2], 482, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v22 )
        {
          if ( *v22 )
          {
            v24 = -1;
            do
              ++v24;
            while ( v22[v24] );
            v15 += 2 * v24 + 2;
            if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
            {
              WPP_SF_d(v9[2], 483, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
              v9 = WPP_GLOBAL_Control;
            }
          }
        }
        v18 = *(_QWORD *)(v18 + 8);
      }
      v15 += 2;
      if ( v9 == &WPP_GLOBAL_Control )
        goto LABEL_102;
      if ( (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
      {
        WPP_SF_d(v9[2], 484, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
        v9 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_d(v9[2], 485, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v15);
LABEL_102:
  v25 = *a5;
  LODWORD(Size) = *a5;
  *a5 = v15;
  if ( !a4 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        487,
        WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
        (unsigned int)v25,
        v15);
      v26 = WPP_GLOBAL_Control;
    }
    goto LABEL_654;
  }
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      486,
      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
      (unsigned int)v25,
      v15);
    v26 = WPP_GLOBAL_Control;
    v25 = (unsigned int)Size;
  }
  if ( (unsigned int)v25 < v15 )
  {
LABEL_654:
    if ( v26 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v26 + 7) & 0x800) != 0 && *((_BYTE *)v26 + 25) >= 2u )
      {
        WPP_SF_d(v26[2], 488, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 603);
        v26 = WPP_GLOBAL_Control;
      }
      if ( v26 != &WPP_GLOBAL_Control && (*((_DWORD *)v26 + 7) & 0x800) != 0 && *((_BYTE *)v26 + 25) >= 6u )
        WPP_SF_d(v26[2], 489, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 603);
    }
    return 603;
  }
  v27 = v115;
  v28 = 0;
  v29 = *(_QWORD *)(v115 + 168);
  if ( v29 && *(_QWORD *)v29 )
    v30 = *(_QWORD *)(*(_QWORD *)v29 + 16LL);
  else
    v30 = 0;
  v31 = *a4;
  memset_0(a4, 0, v25);
  *a4 = v31;
  if ( v30 && *(_DWORD *)(v30 + 24) )
    a4[1] |= 1u;
  if ( *(_DWORD *)(a2 + 320) == 2 )
    a4[1] |= 2u;
  if ( *(_DWORD *)(a2 + 324) == 2 )
    a4[1] |= 4u;
  if ( *(_DWORD *)(a2 + 276) )
    a4[1] |= 8u;
  if ( !*(_DWORD *)(a2 + 240) )
    a4[1] |= 0x20u;
  if ( *(_DWORD *)(v27 + 88) )
    a4[1] |= 0x40u;
  if ( *(_DWORD *)(a2 + 212) )
    a4[1] |= 0x80u;
  if ( *(_DWORD *)(a2 + 48) )
    a4[1] |= 0x100u;
  if ( *(_DWORD *)(a2 + 244) )
    a4[1] |= 0x200u;
  if ( (*(_DWORD *)(a2 + 164) & 0x888) == 0 )
    a4[1] |= 0x400u;
  if ( (*(_DWORD *)(a2 + 164) & 0x8A8) == 0 )
    a4[1] |= 0x800u;
  if ( (*(_DWORD *)(a2 + 172) & 0xFFFFFFF7) != 0 )
    a4[1] |= 0x1000u;
  if ( *(_DWORD *)(a2 + 176) )
    a4[1] |= 0x4000u;
  if ( *(_DWORD *)(v27 + 180) )
    a4[1] |= 0x8000u;
  v33 = 0;
  if ( !*(_DWORD *)(a2 + 256) || !*(_DWORD *)(a2 + 260) )
    a4[1] |= 0x10000u;
  if ( v30 )
    goto LABEL_155;
  PhoneNode = CreatePhoneNode();
  v28 = PhoneNode;
  if ( PhoneNode )
  {
    v30 = *(_QWORD *)(PhoneNode + 16);
LABEL_155:
    a4[2] = *(_DWORD *)(v30 + 12);
    a4[3] = *(_DWORD *)(v30 + 8);
    if ( *(_QWORD *)v30 )
    {
      v37 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 8);
      v38 = v37;
      if ( v37 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 492, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v37);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 493;
        goto LABEL_165;
      }
    }
    if ( v28 )
    {
      DestroyPhoneNode(v28);
      v30 = 0;
    }
    if ( (a4[1] & 2) != 0 )
    {
      v41 = StringToIpAddr(*(_QWORD *)(a2 + 280), a4 + 75);
      v38 = v41;
      if ( v41 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 494, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v41);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 495;
        goto LABEL_165;
      }
    }
    if ( (a4[1] & 4) != 0 )
    {
      v42 = StringToIpAddr(*(_QWORD *)(a2 + 288), a4 + 76);
      v38 = v42;
      if ( v42 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 496, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v42);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 497;
        goto LABEL_165;
      }
      v43 = StringToIpAddr(*(_QWORD *)(a2 + 296), a4 + 77);
      v38 = v43;
      if ( v43 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 498, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v43);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 499;
        goto LABEL_165;
      }
      v44 = StringToIpAddr(*(_QWORD *)(a2 + 304), a4 + 78);
      v38 = v44;
      if ( v44 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 500, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v44);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 501;
        goto LABEL_165;
      }
      v45 = StringToIpAddr(*(_QWORD *)(a2 + 312), a4 + 79);
      v38 = v45;
      if ( v45 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 502, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v45);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 503;
        goto LABEL_165;
      }
    }
    v46 = a4[81];
    a4[82] = 1;
    if ( (*(_BYTE *)(a2 + 236) & 4) == 0 )
    {
      v46 |= 4u;
      a4[81] = v46;
    }
    if ( (*(_BYTE *)(a2 + 236) & 8) == 0 )
      a4[81] = v46 | 8;
    if ( *(_DWORD *)(a2 + 272) )
      a4[1] |= 0x10u;
    a4[81] &= DwGetInstalledProtocolsEx(0, v32, 0);
    if ( *(_DWORD *)(a2 + 212) )
      a4[1] |= 0x80u;
    if ( *(_DWORD *)(a2 + 216) )
    {
      if ( ((unsigned __int16)v118 & 0x400) == 0 )
      {
        *(_WORD *)String2 = 0;
        memset_0(v120, 0, 0x102u);
        v47 = *(_QWORD *)(a2 + 224);
        LODWORD(ppszDestEnd) = 0;
        hMem = 0;
        StrncpyWtoA(String2, v47, 260, 65001);
        RasDevices = GetRasDevices(v49, v48, &hMem, &ppszDestEnd);
        v38 = RasDevices;
        if ( RasDevices )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v38;
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              504,
              WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
              RasDevices);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
            return v38;
          v40 = 505;
          goto LABEL_165;
        }
        for ( i = 0; i < (unsigned int)ppszDestEnd; ++i )
        {
          if ( !_stricmp((const char *)hMem + 129 * i, String2) )
          {
            StringCchPrintfW((STRSAFE_LPWSTR)a4 + 166, 0x104u, L"[%s", *(_QWORD *)(a2 + 224));
            break;
          }
        }
        GlobalFree(hMem);
      }
      if ( !*((_WORD *)a4 + 166) )
        StringCchPrintfW((STRSAFE_LPWSTR)a4 + 166, 0x104u, L"%s", *(_QWORD *)(a2 + 224));
    }
    v52 = *(_QWORD *)(a2 + 432);
    if ( v52 && *(_QWORD *)(a2 + 440) )
    {
      v53 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 426);
      v38 = v53;
      if ( v53 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 506, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v53);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 507;
        goto LABEL_165;
      }
      v54 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 686);
      v38 = v54;
      if ( v54 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v54);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 509;
        goto LABEL_165;
      }
    }
    if ( v30 )
    {
      v52 = *(_QWORD *)v30;
      if ( *(_QWORD *)v30 )
      {
        v38 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 8);
        if ( v38 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return v38;
          }
          v40 = 510;
          goto LABEL_165;
        }
      }
    }
    v55 = v115;
    a4[865] = *(_DWORD *)(a2 + 548);
    v56 = 2147483646;
    v57 = -2147024809;
    if ( (*(_BYTE *)(a2 + 136) & 2) == 0 || (v58 = *(__int64 **)(v55 + 168)) == 0 || (v33 = *v58) == 0 )
    {
LABEL_315:
      if ( v113 )
      {
        v68 = GetSizeofRasentry((unsigned int)v114);
        v69 = (wchar_t *)((char *)a4 + v68);
        a4[74] = v68;
        v70 = (_QWORD **)(v33 + 8);
        if ( !v33 )
          v70 = *(_QWORD ***)(v55 + 168);
        for ( j = *v70; ; j = (_QWORD *)*((_QWORD *)hMem + 1) )
        {
          hMem = j;
          if ( !j )
          {
            v55 = v115;
            v57 = -2147024809;
            *v69 = 0;
            v56 = 2147483646;
            goto LABEL_385;
          }
          v72 = j[2];
          memset_0(String2, 0, 0x102u);
          if ( !v72 )
            break;
          if ( !*(_QWORD *)(v72 + 16) )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 519, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
                v9 = WPP_GLOBAL_Control;
              }
              if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
              {
                v19 = 520;
                goto LABEL_382;
              }
            }
            return 625;
          }
          v73 = *(_WORD **)(v72 + 40);
          if ( v73 && *v73 )
          {
            v74 = StringCchPrintfWrapW(String2, 129, L"%s;%s", *(_QWORD *)(v72 + 16), *(_QWORD *)(v72 + 40));
            v38 = v74;
            if ( v74 )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    521,
                    WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                    v74);
                  v39 = WPP_GLOBAL_Control;
                }
                if ( v39 != (_DWORD *)&WPP_GLOBAL_Control && (v39[7] & 0x800) != 0 && *((_BYTE *)v39 + 25) >= 6u )
                {
                  v40 = 522;
                  goto LABEL_165;
                }
              }
              return v38;
            }
          }
          else
          {
            v75 = StringCchCopyWrapW((STRSAFE_LPWSTR)String2);
            v38 = v75;
            if ( v75 )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    523,
                    WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                    v75);
                  v39 = WPP_GLOBAL_Control;
                }
                if ( v39 != (_DWORD *)&WPP_GLOBAL_Control && (v39[7] & 0x800) != 0 && *((_BYTE *)v39 + 25) >= 6u )
                {
                  v40 = 524;
                  goto LABEL_165;
                }
              }
              return v38;
            }
          }
          v76 = (_WORD *)StrDup(String2);
          if ( !v76 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 525, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 8);
                v35 = WPP_GLOBAL_Control;
              }
              if ( v35 != (_DWORD *)&WPP_GLOBAL_Control && (v35[7] & 0x800) != 0 && *((_BYTE *)v35 + 25) >= 6u )
              {
                v36 = 526;
                goto LABEL_356;
              }
            }
            return 8;
          }
          v77 = -1;
          do
            ++v77;
          while ( v76[v77] );
          v38 = StringCchCopyWrapW(v69);
          if ( v38
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 527, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v38);
          }
          GlobalFree(v76);
          if ( v38 )
          {
            v39 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
            {
              v40 = 528;
              goto LABEL_165;
            }
            return v38;
          }
          v69 += (unsigned int)(v77 + 1);
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 517, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 625);
            v9 = WPP_GLOBAL_Control;
          }
          if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800) != 0 && *((_BYTE *)v9 + 25) >= 6u )
          {
            v19 = 518;
            goto LABEL_382;
          }
        }
        return 625;
      }
LABEL_385:
      v78 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          529,
          WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
          *(unsigned int *)(v55 + 40));
        v78 = WPP_GLOBAL_Control;
      }
      v79 = *(_DWORD *)(v55 + 40);
      if ( v79 > 13 )
      {
        v87 = v79 - 14;
        if ( v87 )
        {
          v88 = v87 - 1;
          if ( v88 )
          {
            v83 = v88 - 1;
            v82 = v83 == 0;
            goto LABEL_406;
          }
        }
      }
      else if ( v79 != 13 )
      {
        v80 = v79 - 2;
        if ( v80 )
        {
          v81 = v80 - 4;
          if ( !v81 )
          {
            if ( v78 != &WPP_GLOBAL_Control && (*((_DWORD *)v78 + 7) & 0x800) != 0 && *((_BYTE *)v78 + 25) >= 5u )
              WPP_SF_(v78[2], 530, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
            v84 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 946);
            v38 = v84;
            if ( v84 )
            {
              v39 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v38;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_430;
              v85 = 531;
              v86 = v84;
              goto LABEL_429;
            }
LABEL_448:
            SetDevicePortNameFromLink(v115, (char *)a4 + 1926);
            v95 = v114;
            if ( v114 >= 2 )
            {
              a4[867] = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 16LL);
              a4[868] = *(_DWORD *)(a2 + 132);
              *(_QWORD *)(a4 + 869) = 0;
              *(_QWORD *)(a4 + 871) = 0;
              a4[873] = *(_DWORD *)(a2 + 156);
              if ( *(_DWORD *)(a2 + 232) == 1 )
                a4[1] |= 0x80000000;
            }
            if ( v95 >= 3 )
            {
              v96 = *(_OWORD **)(a2 + 464);
              if ( v96 )
                *(_OWORD *)(a4 + 877) = *v96;
              a4[874] = *(_DWORD *)(a2 + 24);
              v97 = *(_DWORD *)(a2 + 172);
              if ( v97 )
              {
                switch ( v97 )
                {
                  case 256:
                    a4[875] = 1;
                    break;
                  case 512:
                    a4[875] = 2;
                    break;
                  case 8:
                    a4[875] = 3;
                    break;
                }
              }
              else
              {
                a4[875] = 0;
              }
              if ( (*(_DWORD *)(a2 + 164) & 0x200) != 0 )
                a4[1] |= 0x20000000u;
              if ( (*(_BYTE *)(a2 + 164) & 8) != 0 )
                a4[1] |= 0x40000u;
              if ( (*(_BYTE *)(a2 + 164) & 0x20) != 0 )
                a4[1] |= 0x8000000u;
              if ( *(char *)(a2 + 164) < 0 )
              {
                a4[1] |= 0x20000u;
                v98 = *(_DWORD *)(a2 + 192);
                if ( v98 )
                  a4[876] = v98;
              }
              if ( *(_QWORD *)(a2 + 448) )
              {
                v99 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 1762);
                v38 = v99;
                if ( v99 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      538,
                      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                      v99);
                    v39 = WPP_GLOBAL_Control;
                  }
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 539;
                  goto LABEL_165;
                }
              }
              if ( *(_DWORD *)(a2 + 124) )
                a4[1] |= 0x200000u;
              if ( *(_DWORD *)(a2 + 40) )
                a4[1] |= 0x800000u;
              if ( *(_DWORD *)(a2 + 116) )
                a4[1] |= 0x1000000u;
              if ( *(_DWORD *)(a2 + 120) )
                a4[1] |= 0x2000000u;
              if ( *(_DWORD *)(a2 + 112) )
                a4[1] |= 0x4000000u;
              a4[1011] = *(_DWORD *)(a2 + 168);
            }
            if ( v95 >= 4 )
            {
              if ( !*(_DWORD *)(a2 + 256) )
                a4[1012] |= 1u;
              if ( !*(_DWORD *)(a2 + 260) )
                a4[1012] |= 2u;
              if ( !*(_DWORD *)(a2 + 248) )
                a4[1012] |= 4u;
              if ( !*(_DWORD *)(a2 + 180) )
                a4[1012] |= 8u;
              if ( (*(_BYTE *)(a2 + 140) & 1) != 0 )
                a4[1012] |= 0x10u;
              if ( (*(_BYTE *)(a2 + 332) & 1) == 0 )
                a4[1012] |= 0x40u;
              if ( (*(_BYTE *)(a2 + 136) & 1) != 0 )
                a4[1012] |= 0x20u;
              if ( *(_DWORD *)(a2 + 44) )
                a4[1012] |= 0x80u;
              if ( *(_QWORD *)(a2 + 344) )
              {
                v100 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 2028);
                v38 = v100;
                if ( v100 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      540,
                      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                      v100);
                    v39 = WPP_GLOBAL_Control;
                  }
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 541;
                  goto LABEL_165;
                }
              }
              if ( *(_QWORD *)(a2 + 56) )
              {
                if ( *(_DWORD *)(a2 + 24) == 2 )
                {
                  v101 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 2546);
                  v38 = v101;
                  if ( v101 )
                  {
                    v39 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                      return v38;
                    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        542,
                        WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                        v101);
                      v39 = WPP_GLOBAL_Control;
                    }
                    if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                      return v38;
                    v40 = 543;
                    goto LABEL_165;
                  }
                }
              }
              if ( *(_QWORD *)(a2 + 64) )
              {
                if ( *(_DWORD *)(a2 + 24) == 2 )
                {
                  v102 = StringCchCopyWrapW((STRSAFE_LPWSTR)a4 + 2286);
                  v38 = v102;
                  if ( v102 )
                  {
                    v39 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                      return v38;
                    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        544,
                        WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                        v102);
                      v39 = WPP_GLOBAL_Control;
                    }
                    if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                      return v38;
                    v40 = 545;
                    goto LABEL_165;
                  }
                }
              }
              a4[1142] = *(_DWORD *)(a2 + 336);
              a4[1402] = *(_DWORD *)(a2 + 148);
              a4[1403] = *(_DWORD *)(a2 + 152);
              if ( *(_DWORD *)(a2 + 160) )
                a4[1012] |= 0x100u;
              if ( *(_DWORD *)(a2 + 40) )
                a4[1012] |= 0x200u;
            }
            if ( v95 >= 5 )
            {
              if ( *(_DWORD *)(a2 + 372) )
                a4[1012] |= 0x2000u;
              if ( *(_DWORD *)(a2 + 376) == 2 )
              {
                a4[1012] |= 0x1000u;
                v103 = StringToIpv6Addr(*(_QWORD *)(a2 + 384), a4 + 1404);
                v38 = v103;
                if ( v103 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      546,
                      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                      v103);
                    v39 = WPP_GLOBAL_Control;
                  }
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 547;
                  goto LABEL_165;
                }
                v104 = StringToIpv6Addr(*(_QWORD *)(a2 + 392), a4 + 1408);
                v38 = v104;
                if ( v104 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      548,
                      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                      v104);
                    v39 = WPP_GLOBAL_Control;
                  }
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 549;
                  goto LABEL_165;
                }
              }
              if ( (*(_BYTE *)(a2 + 328) & 1) != 0 )
                a4[1012] |= 0x4000u;
              v105 = *(_WORD **)(a2 + 344);
              if ( v105 && *v105 && (*(_BYTE *)(a2 + 328) & 2) != 0 )
                a4[1012] |= 0x8000u;
              if ( *(_DWORD *)(a2 + 352) )
              {
                a4[1012] |= 0x10000u;
                a4[1412] = *(_DWORD *)(a2 + 352);
              }
              if ( *(_DWORD *)(a2 + 416) )
              {
                a4[1012] |= 0x20000u;
                a4[1413] = *(_DWORD *)(a2 + 416);
              }
              if ( *(_DWORD *)(a2 + 188) )
                a4[1012] |= 0x40000u;
            }
            if ( v95 >= 6 )
            {
              if ( *(_DWORD *)(a2 + 544) )
                a4[1012] |= 0x80000u;
              if ( *(_DWORD *)(a2 + 356) == 2 )
              {
                a4[1012] |= 0x100000u;
                v106 = StringToIpv6Addr(*(_QWORD *)(a2 + 360), a4 + 1414);
                v38 = v106;
                if ( v106 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      550,
                      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                      v106);
                    v39 = WPP_GLOBAL_Control;
                  }
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 551;
                  goto LABEL_165;
                }
                a4[1418] = *(_DWORD *)(a2 + 368);
              }
              a4[1419] = *(_DWORD *)(a2 + 492);
              if ( *(_DWORD *)(a2 + 488) )
                a4[1012] |= 0x200000u;
              if ( (*(_DWORD *)(a2 + 164) & 0x800) != 0 )
                a4[1012] |= 0x400000u;
              if ( (*(_DWORD *)(a2 + 164) & 0x1000) != 0 )
                a4[1012] |= 0x800000u;
              if ( (*(_BYTE *)(a2 + 140) & 2) != 0 )
                a4[1012] |= 0x1000000u;
            }
            if ( v95 >= 7 )
            {
              if ( *(_DWORD *)(a2 + 128) )
                a4[1012] |= 0x2000000u;
              if ( *(_DWORD *)(a2 + 704) )
                a4[1012] |= 0x4000000u;
              if ( *(_QWORD *)(a2 + 760) )
                a4[1012] |= 0x8000000u;
              if ( *(_DWORD *)(a2 + 816) )
                a4[1012] |= 0x10000000u;
            }
            if ( v95 < 15 )
              goto LABEL_640;
            a4[1678] = *(_DWORD *)(a2 + 516);
            a4[1679] = *(_DWORD *)(a2 + 520);
            a4[1677] = *(_DWORD *)(a2 + 512);
            v107 = *(_QWORD *)(a2 + 496);
            if ( v107 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  552,
                  WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                  v107);
              }
              v108 = StringCchCopyW((STRSAFE_LPWSTR)a4 + 2840, 0x100u, *(STRSAFE_LPCWSTR *)(a2 + 496));
              if ( !v108 )
                goto LABEL_625;
              v109 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  553,
                  WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                  v108);
LABEL_625:
                v109 = WPP_GLOBAL_Control;
              }
            }
            else
            {
              v109 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 554, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
                goto LABEL_625;
              }
            }
            v110 = *(_QWORD *)(a2 + 504);
            if ( v110 )
            {
              if ( v109 != &WPP_GLOBAL_Control && (*((_DWORD *)v109 + 7) & 0x800) != 0 && *((_BYTE *)v109 + 25) >= 5u )
                WPP_SF_S(v109[2], 555, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v110);
              v111 = StringCchCopyW((STRSAFE_LPWSTR)a4 + 3097, 0x100u, *(STRSAFE_LPCWSTR *)(a2 + 504));
              if ( v111 )
              {
                v109 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_641;
                }
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  556,
                  WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                  v111);
              }
            }
            else
            {
              if ( v109 == &WPP_GLOBAL_Control || (*((_DWORD *)v109 + 7) & 0x800) == 0 || *((_BYTE *)v109 + 25) < 5u )
                goto LABEL_641;
              WPP_SF_(v109[2], 557, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
            }
LABEL_640:
            v109 = WPP_GLOBAL_Control;
LABEL_641:
            if ( v95 >= 16 )
            {
              a4[1680] = *(_DWORD *)(a2 + 524);
              if ( *(_DWORD *)(a2 + 528) )
                a4[1012] |= 0x80000000;
              v109 = WPP_GLOBAL_Control;
            }
            if ( v109 != &WPP_GLOBAL_Control && (*((_DWORD *)v109 + 7) & 0x800) != 0 && *((_BYTE *)v109 + 25) >= 6u )
              WPP_SF_d(v109[2], 558, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 0);
            return 0;
          }
          v83 = v81 - 4;
          v82 = v83 == 0;
LABEL_406:
          if ( !v82 && (unsigned int)(v83 - 1) >= 2 )
          {
            if ( v78 != &WPP_GLOBAL_Control && (*((_DWORD *)v78 + 7) & 0x800) != 0 && *((_BYTE *)v78 + 25) >= 5u )
              WPP_SF_(v78[2], 535, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
            v89 = (wchar_t *)(a4 + 473);
            if ( a4 == (unsigned int *)-1892LL )
            {
              *v89 = 0;
            }
            else
            {
              v38 = 0;
              v90 = L"modem";
              v91 = 17;
              v92 = a4 + 473;
              do
              {
                if ( !v56 )
                  break;
                if ( !*v90 )
                  break;
                *v92++ = *v90++;
                --v56;
                --v91;
              }
              while ( v91 );
              v93 = v92 - 1;
              v57 = v91 == 0 ? 0x8007007A : 0;
              if ( v91 )
                v93 = v92;
              *v93 = 0;
              if ( v91 )
              {
LABEL_424:
                if ( v38 )
                {
                  v39 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                    return v38;
                  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                    goto LABEL_430;
                  v85 = 536;
                  v86 = v38;
LABEL_429:
                  WPP_SF_d(*((_QWORD *)v39 + 2), v85, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v86);
                  v39 = WPP_GLOBAL_Control;
LABEL_430:
                  if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
                    return v38;
                  v40 = 537;
                  goto LABEL_165;
                }
                goto LABEL_448;
              }
              StringExHandleOtherFlagsW(v89, 0x22u, (size_t)v92, &v118, (size_t *)&hMem, 0x900u);
            }
            v38 = (unsigned __int16)v57;
            if ( g_dwTraceId != -1 )
              TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v57);
            goto LABEL_424;
          }
        }
      }
      if ( v78 != &WPP_GLOBAL_Control && (*((_DWORD *)v78 + 7) & 0x800) != 0 && *((_BYTE *)v78 + 25) >= 5u )
        WPP_SF_(v78[2], 532, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
      RasmanDeviceType = GetRasmanDeviceType(v55, a4 + 473, v52, ((unsigned __int16)v118 & 0x400) == 0);
      v38 = RasmanDeviceType;
      if ( !RasmanDeviceType )
      {
        _wcslwr((wchar_t *)a4 + 946);
        goto LABEL_448;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v38;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          533,
          WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
          RasmanDeviceType);
        v39 = WPP_GLOBAL_Control;
      }
      if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
        return v38;
      v40 = 534;
LABEL_165:
      WPP_SF_d(*((_QWORD *)v39 + 2), v40, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v38);
      return v38;
    }
    v59 = *(_QWORD *)(v33 + 16);
    v60 = *(_WORD **)(v59 + 40);
    if ( v60 && *v60 )
    {
      v61 = StringCchPrintfWrapW(String2, 129, L"%s;%s", *(_QWORD *)(v59 + 16), *(_QWORD *)(v59 + 40));
      v38 = v61;
      if ( v61 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v61);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 512;
        goto LABEL_165;
      }
    }
    else
    {
      v62 = StringCchCopyWrapW((STRSAFE_LPWSTR)String2);
      v38 = v62;
      if ( v62 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v38;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 513, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v62);
          v39 = WPP_GLOBAL_Control;
        }
        if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
          return v38;
        v40 = 514;
        goto LABEL_165;
      }
    }
    v63 = (wchar_t *)a4 + 19;
    if ( a4 == (unsigned int *)-38LL )
    {
      *v63 = 0;
    }
    else
    {
      v64 = 2147483646;
      v65 = String2;
      v52 = 129;
      v66 = (_WORD *)a4 + 19;
      do
      {
        if ( !v64 )
          break;
        if ( !*(_WORD *)v65 )
          break;
        *v66 = *(_WORD *)v65;
        v65 += 2;
        ++v66;
        --v64;
        --v52;
      }
      while ( v52 );
      v67 = v66 - 1;
      v57 = v52 == 0 ? 0x8007007A : 0;
      if ( v52 )
        v67 = v66;
      *v67 = 0;
      if ( v52 )
      {
LABEL_314:
        v55 = v115;
        v57 = -2147024809;
        goto LABEL_315;
      }
      StringExHandleOtherFlagsW(v63, 0x102u, 0, &ppszDestEnd, (size_t *)&hMem, 0x900u);
    }
    v38 = (unsigned __int16)v57;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v57);
    if ( (_WORD)v57 )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v38;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          515,
          WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
          (unsigned __int16)v57);
        v39 = WPP_GLOBAL_Control;
      }
      if ( v39 == (_DWORD *)&WPP_GLOBAL_Control || (v39[7] & 0x800) == 0 || *((_BYTE *)v39 + 25) < 6u )
        return v38;
      v40 = 516;
      goto LABEL_165;
    }
    goto LABEL_314;
  }
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 490, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 8);
      v35 = WPP_GLOBAL_Control;
    }
    if ( v35 != (_DWORD *)&WPP_GLOBAL_Control && (v35[7] & 0x800) != 0 && *((_BYTE *)v35 + 25) >= 6u )
    {
      v36 = 491;
LABEL_356:
      WPP_SF_d(*((_QWORD *)v35 + 2), v36, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, 8);
    }
  }
  return 8;
}

```

## disassembly

```asm
0x180012ff8  mov     [rsp-8+arg_10], rbx
0x180012ffd  push    rbp
0x180012ffe  push    rsi
0x180012fff  push    rdi
0x180013000  push    r12
0x180013002  push    r13
0x180013004  push    r14
0x180013006  push    r15
0x180013008  lea     rbp, [rsp-80h]
0x18001300d  sub     rsp, 180h
0x180013014  mov     rax, cs:__security_cookie
0x18001301b  xor     rax, rsp
0x18001301e  mov     [rbp+0B0h+var_40], rax
0x180013022  mov     r12, [rbp+0B0h+arg_20]
0x180013029  mov     eax, r8d
0x18001302c  mov     dword ptr [rsp+1B0h+var_158], eax
0x180013030  mov     rdi, r9
0x180013033  mov     rsi, rdx
0x180013036  mov     [rsp+1B0h+var_174], ecx
0x18001303a  mov     r8d, ecx
0x18001303d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013044  lea     rbx, WPP_GLOBAL_Control
0x18001304b  lea     r15, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180013052  mov     r14d, 800h
0x180013058  cmp     rcx, rbx
0x18001305b  jz      short loc_18001308D
0x18001305d  test    [rcx+1Ch], r14d
0x180013061  jz      short loc_18001308D
0x180013063  cmp     byte ptr [rcx+19h], 6
0x180013067  jb      short loc_18001308D
0x180013069  mov     rcx, [rcx+10h]
0x18001306d  mov     r9d, r8d
0x180013070  mov     r8, r15
0x180013073  mov     dword ptr [rsp+1B0h+pcchRemaining], eax
0x180013077  mov     edx, 1D3h
0x18001307c  call    WPP_SF_Dd
0x180013081  mov     rcx, cs:WPP_GLOBAL_Control
0x180013088  mov     r8d, [rsp+1B0h+var_174]
0x18001308d  mov     rax, [rsi+20h]
0x180013091  mov     rdx, [rax]
0x180013094  xor     eax, eax
0x180013096  test    rdx, rdx
0x180013099  jnz     short loc_1800130F4
0x18001309b  cmp     rcx, rbx
0x18001309e  jz      loc_180013163
0x1800130a4  test    [rcx+1Ch], r14d
0x1800130a8  jz      short loc_1800130D8
0x1800130aa  lea     r14d, [rax+2]
0x1800130ae  cmp     [rcx+19h], r14b
0x1800130b2  jb      short loc_1800130D2
0x1800130b4  mov     rcx, [rcx+10h]
0x1800130b8  mov     edx, 1D4h
0x1800130bd  mov     r9d, 26Fh
0x1800130c3  mov     r8, r15
0x1800130c6  call    WPP_SF_d
0x1800130cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130d2  mov     r14d, 800h
0x1800130d8  cmp     rcx, rbx
0x1800130db  jz      loc_180013163
0x1800130e1  test    [rcx+1Ch], r14d
0x1800130e5  jz      short loc_180013163
0x1800130e7  cmp     byte ptr [rcx+19h], 6
0x1800130eb  jb      short loc_180013163
0x1800130ed  mov     edx, 1D5h
0x1800130f2  jmp     short loc_180013151
0x1800130f4  mov     r13, [rdx+10h]
0x1800130f8  mov     [rsp+1B0h+var_170], r13
0x1800130fd  test    r13, r13
0x180013100  jnz     short loc_18001316D
0x180013102  cmp     rcx, rbx
0x180013105  jz      short loc_180013163
0x180013107  test    [rcx+1Ch], r14d
0x18001310b  jz      short loc_18001313B
0x18001310d  lea     r14d, [r13+2]
0x180013111  cmp     [rcx+19h], r14b
0x180013115  jb      short loc_180013135
0x180013117  mov     rcx, [rcx+10h]
0x18001311b  mov     edx, 1D6h
0x180013120  mov     r9d, 26Fh
0x180013126  mov     r8, r15
0x180013129  call    WPP_SF_d
0x18001312e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013135  mov     r14d, 800h
0x18001313b  cmp     rcx, rbx
0x18001313e  jz      short loc_180013163
0x180013140  test    [rcx+1Ch], r14d
0x180013144  jz      short loc_180013163
0x180013146  cmp     byte ptr [rcx+19h], 6
0x18001314a  jb      short loc_180013163
0x18001314c  mov     edx, 1D7h
0x180013151  mov     rcx, [rcx+10h]
0x180013155  mov     r9d, 26Fh
0x18001315b  mov     r8, r15
0x18001315e  call    WPP_SF_d
0x180013163  mov     eax, 26Fh
0x180013168  jmp     loc_180015200
0x18001316d  mov     [rsp+1B0h+var_178], eax
0x180013171  test    rdi, rdi
0x180013174  jnz     short loc_180013189
0x180013176  mov     ecx, r8d
0x180013179  call    GetSizeofRasentry
0x18001317e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013185  mov     ebx, eax
0x180013187  jmp     short loc_18001318B
0x180013189  mov     ebx, [rdi]
0x18001318b  lea     r9, WPP_GLOBAL_Control
0x180013192  cmp     rcx, r9
0x180013195  jz      short loc_1800131C5
0x180013197  test    [rcx+1Ch], r14d
0x18001319b  jz      short loc_1800131C5
0x18001319d  cmp     byte ptr [rcx+19h], 5
0x1800131a1  jb      short loc_1800131C5
0x1800131a3  mov     rcx, [rcx+10h]
0x1800131a7  mov     edx, 1D8h
0x1800131ac  mov     r9d, ebx
0x1800131af  mov     r8, r15
0x1800131b2  call    WPP_SF_d
0x1800131b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131be  lea     r9, WPP_GLOBAL_Control
0x1800131c5  mov     r15, [r13+0A8h]
0x1800131cc  xor     r8d, r8d
0x1800131cf  test    r15, r15
0x1800131d2  jz      short loc_1800131DA
0x1800131d4  mov     r15d, [r15+10h]
0x1800131d8  jmp     short loc_1800131DD
0x1800131da  mov     r15d, r8d
0x1800131dd  cmp     rcx, r9
0x1800131e0  jz      short loc_180013217
0x1800131e2  test    [rcx+1Ch], r14d
0x1800131e6  jz      short loc_180013217
0x1800131e8  cmp     byte ptr [rcx+19h], 5
0x1800131ec  jb      short loc_180013217
0x1800131ee  mov     rcx, [rcx+10h]
0x1800131f2  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800131f9  mov     edx, 1D9h
0x1800131fe  mov     r9d, r15d
0x180013201  call    WPP_SF_d
0x180013206  mov     rcx, cs:WPP_GLOBAL_Control
0x18001320d  lea     r9, WPP_GLOBAL_Control
0x180013214  xor     r8d, r8d
0x180013217  mov     r14d, 2
0x18001321d  test    r15d, r15d
0x180013220  jz      loc_180013527
0x180013226  mov     rax, [r13+0A8h]
0x18001322d  mov     r13, [rax]
0x180013230  test    r13, r13
0x180013233  jnz     short loc_1800132A0
0x180013235  cmp     rcx, r9
0x180013238  jz      loc_180014493
0x18001323e  test    dword ptr [rcx+1Ch], 800h
0x180013245  jz      short loc_180013276
0x180013247  cmp     [rcx+19h], r14b
0x18001324b  jb      short loc_180013276
0x18001324d  mov     rcx, [rcx+10h]
0x180013251  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180013258  mov     edx, 1DAh
0x18001325d  mov     r9d, 271h
0x180013263  call    WPP_SF_d
0x180013268  mov     rcx, cs:WPP_GLOBAL_Control
0x18001326f  lea     r9, WPP_GLOBAL_Control
0x180013276  cmp     rcx, r9
0x180013279  jz      loc_180014493
0x18001327f  test    dword ptr [rcx+1Ch], 800h
0x180013286  jz      loc_180014493
0x18001328c  cmp     byte ptr [rcx+19h], 6
0x180013290  jb      loc_180014493
0x180013296  mov     edx, 1DBh
0x18001329b  jmp     loc_18001447D
0x1800132a0  test    [rsi+88h], r14b
0x1800132a7  jnz     short loc_1800132E5
0x1800132a9  cmp     rcx, r9
0x1800132ac  jz      short loc_1800132EC
0x1800132ae  test    dword ptr [rcx+1Ch], 800h
0x1800132b5  jz      short loc_1800132EC
0x1800132b7  cmp     byte ptr [rcx+19h], 5
0x1800132bb  jb      short loc_1800132EC
0x1800132bd  mov     rcx, [rcx+10h]
0x1800132c1  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800132c8  mov     edx, 1DCh
0x1800132cd  call    WPP_SF_
0x1800132d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132d9  lea     r9, WPP_GLOBAL_Control
0x1800132e0  xor     r8d, r8d
0x1800132e3  jmp     short loc_1800132EC
0x1800132e5  mov     r13, [r13+8]
0x1800132e9  dec     r15d
0x1800132ec  mov     [rsp+1B0h+var_178], r15d
0x1800132f1  cmp     rcx, r9
0x1800132f4  jz      short loc_18001332E
0x1800132f6  test    dword ptr [rcx+1Ch], 800h
0x1800132fd  jz      short loc_18001332E
0x1800132ff  cmp     byte ptr [rcx+19h], 5
0x180013303  jb      short loc_18001332E
0x180013305  mov     rcx, [rcx+10h]
0x180013309  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180013310  mov     edx, 1DDh
0x180013315  mov     r9d, r15d
0x180013318  call    WPP_SF_d
0x18001331d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013324  lea     r9, WPP_GLOBAL_Control
0x18001332b  xor     r8d, r8d
0x18001332e  test    r15d, r15d
0x180013331  jz      loc_180013527
0x180013337  test    r13, r13
0x18001333a  jz      loc_1800134EA
0x180013340  mov     rax, [r13+10h]
0x180013344  test    rax, rax
0x180013347  jz      loc_18001347F
0x18001334d  mov     rdx, [rax+10h]
0x180013351  test    rdx, rdx
0x180013354  jz      loc_180013414
0x18001335a  mov     r15, [rax+28h]
0x18001335e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013362  inc     rax
0x180013365  cmp     [rdx+rax*2], r8w
0x18001336a  jnz     short loc_180013362
0x18001336c  lea     ebx, [rbx+rax*2]
0x18001336f  add     ebx, r14d
0x180013372  cmp     rcx, r9
0x180013375  jz      short loc_1800133AF
0x180013377  test    dword ptr [rcx+1Ch], 800h
0x18001337e  jz      short loc_1800133AF
0x180013380  cmp     byte ptr [rcx+19h], 5
0x180013384  jb      short loc_1800133AF
0x180013386  mov     rcx, [rcx+10h]
0x18001338a  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180013391  mov     edx, 1E2h
0x180013396  mov     r9d, ebx
0x180013399  call    WPP_SF_d
0x18001339e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133a5  lea     r9, WPP_GLOBAL_Control
0x1800133ac  xor     r8d, r8d
0x1800133af  test    r15, r15
0x1800133b2  jz      short loc_180013404
0x1800133b4  cmp     [r15], r8w
0x1800133b8  jz      short loc_180013404
0x1800133ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800133be  inc     rax
0x1800133c1  cmp     [r15+rax*2], r8w
0x1800133c6  jnz     short loc_1800133BE
0x1800133c8  lea     ebx, [rbx+rax*2]
0x1800133cb  add     ebx, r14d
0x1800133ce  cmp     rcx, r9
0x1800133d1  jz      short loc_180013404
0x1800133d3  test    dword ptr [rcx+1Ch], 800h
0x1800133da  jz      short loc_180013404
0x1800133dc  cmp     byte ptr [rcx+19h], 5
0x1800133e0  jb      short loc_180013404
0x1800133e2  mov     rcx, [rcx+10h]
0x1800133e6  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800133ed  mov     edx, 1E3h
0x1800133f2  mov     r9d, ebx
0x1800133f5  call    WPP_SF_d
0x1800133fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180013401  xor     r8d, r8d
0x180013404  mov     r13, [r13+8]
0x180013408  lea     r9, WPP_GLOBAL_Control
0x18001340f  jmp     loc_180013337
0x180013414  cmp     rcx, r9
0x180013417  jz      loc_180014493
0x18001341d  test    dword ptr [rcx+1Ch], 800h
0x180013424  jz      short loc_180013455
0x180013426  cmp     [rcx+19h], r14b
0x18001342a  jb      short loc_180013455
0x18001342c  mov     rcx, [rcx+10h]
0x180013430  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180013437  mov     edx, 1E0h
0x18001343c  mov     r9d, 271h
0x180013442  call    WPP_SF_d
0x180013447  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344e  lea     r9, WPP_GLOBAL_Control
0x180013455  cmp     rcx, r9
0x180013458  jz      loc_180014493
0x18001345e  test    dword ptr [rcx+1Ch], 800h
0x180013465  jz      loc_180014493
0x18001346b  cmp     byte ptr [rcx+19h], 6
0x18001346f  jb      loc_180014493
0x180013475  mov     edx, 1E1h
0x18001347a  jmp     loc_18001447D
0x18001347f  cmp     rcx, r9
0x180013482  jz      loc_180014493
0x180013488  test    dword ptr [rcx+1Ch], 800h
0x18001348f  jz      short loc_1800134C0
0x180013491  cmp     [rcx+19h], r14b
0x180013495  jb      short loc_1800134C0
0x180013497  mov     rcx, [rcx+10h]
0x18001349b  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800134a2  mov     edx, 1DEh
0x1800134a7  mov     r9d, 271h
0x1800134ad  call    WPP_SF_d
0x1800134b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134b9  lea     r9, WPP_GLOBAL_Control
0x1800134c0  cmp     rcx, r9
0x1800134c3  jz      loc_180014493
0x1800134c9  test    dword ptr [rcx+1Ch], 800h
0x1800134d0  jz      loc_180014493
0x1800134d6  cmp     byte ptr [rcx+19h], 6
0x1800134da  jb      loc_180014493
0x1800134e0  mov     edx, 1DFh
0x1800134e5  jmp     loc_18001447D
  ... truncated ...
```
