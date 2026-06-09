# _AttributesFromBOE(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x180074370`
- end: `0x1800755e7`
- name: `?_AttributesFromBOE@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `4727`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dcec`
- `0x1800653f4`
- `0x180066c10`
- `0x18006d698`
- `0x18006e298`
- `0x180073f4c`
- `0x180074370`
- `0x18007778c`
- `0x180077d38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180074ef0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180074ef0`
- `ntdll!RtlAllocateHeap` at `0x180074e34`
- `ntdll!RtlAllocateHeap` at `0x180074f2d`
- `ntdll!RtlAllocateHeap` at `0x180074e34`
- `ntdll!RtlAllocateHeap` at `0x180074f2d`
- `ntdll!RtlFreeHeap` at `0x180074974`
- `ntdll!RtlFreeHeap` at `0x180074ac3`
- `ntdll!RtlFreeHeap` at `0x180074b24`
- `ntdll!RtlFreeHeap` at `0x180074cd9`
- `ntdll!RtlFreeHeap` at `0x180074d3c`
- `ntdll!RtlFreeHeap` at `0x180074d9b`
- `ntdll!RtlFreeHeap` at `0x180074df6`
- `ntdll!RtlFreeHeap` at `0x18007555c`
- `ntdll!RtlFreeHeap` at `0x18007557e`
- `ntdll!RtlFreeHeap` at `0x18007559b`
- `ntdll!RtlFreeHeap` at `0x1800755b8`
- `ntdll!RtlFreeHeap` at `0x180074974`
- `ntdll!RtlFreeHeap` at `0x180074ac3`
- `ntdll!RtlFreeHeap` at `0x180074b24`
- `ntdll!RtlFreeHeap` at `0x180074cd9`
- `ntdll!RtlFreeHeap` at `0x180074d3c`
- `ntdll!RtlFreeHeap` at `0x180074d9b`
- `ntdll!RtlFreeHeap` at `0x180074df6`
- `ntdll!RtlFreeHeap` at `0x18007555c`
- `ntdll!RtlFreeHeap` at `0x18007557e`
- `ntdll!RtlFreeHeap` at `0x18007559b`
- `ntdll!RtlFreeHeap` at `0x1800755b8`

## string_xrefs

- `0x18007502b`: `AeComputeProgramIdentityHash failed [%x]`
- `0x18007551c`: `StringCbCopyW failed [%x]`
- `0x180074411`: `_SetFileAttributeValue`
- `0x1800750e0`: `_SetFileAttributeValue`
- `0x180075246`: `_SetFileAttributeValue`
- `0x180075368`: `_SetFileAttributeValue`
- `0x180075487`: `_SetFileAttributeValue`
- `0x180074407`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x180074fda`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromBOE(const wchar_t ***a1, _DWORD *a2, __int64 a3)
{
  const WCHAR **v5; // rcx
  _WORD *v6; // r15
  const WCHAR *v7; // rcx
  int v8; // r10d
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rdx
  const wchar_t *v12; // rcx
  _WORD *v13; // r8
  _WORD *v14; // rcx
  int v15; // r10d
  __int64 v16; // rax
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  _WORD *v19; // r8
  _WORD *v20; // rcx
  int v21; // r10d
  __int64 v22; // r8
  const wchar_t *v23; // rax
  __int64 v24; // rdx
  _WORD *v25; // r9
  _WORD *v26; // rcx
  int v27; // r10d
  __int64 v28; // r13
  const unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  _WORD *v31; // r8
  _WORD *v32; // rcx
  int v33; // r11d
  __int64 v34; // rax
  const wchar_t *v35; // rcx
  _WORD *v36; // r10
  _WORD *v37; // r9
  unsigned int v38; // ebx
  int FileKindDetail; // eax
  int Attribute; // eax
  int v41; // ebx
  const wchar_t ***v42; // r14
  int v43; // eax
  int v44; // eax
  const char *v45; // r9
  __int64 v46; // r8
  unsigned __int16 *v47; // r14
  int v48; // eax
  int v49; // ebx
  int v50; // eax
  int v51; // eax
  int v52; // eax
  const char *v53; // r9
  __int64 v54; // r8
  int v55; // ebx
  unsigned __int16 *v56; // rax
  int v57; // eax
  _WORD *v58; // r8
  const wchar_t *v59; // rbx
  wchar_t *v60; // rax
  __int64 v61; // r14
  SIZE_T v62; // r14
  _WORD *Heap; // rax
  unsigned __int64 v64; // r14
  __int64 v65; // rax
  _WORD *v66; // rdx
  _WORD *v67; // rcx
  __int64 v68; // r14
  int v69; // eax
  int v70; // r10d
  __int64 v71; // rax
  __int64 v72; // rdx
  _WORD *v73; // rcx
  _WORD *v74; // r8
  _WORD *v75; // rcx
  __int64 v76; // rdx
  const wchar_t *v77; // rbx
  __int64 v78; // rdx
  int v79; // r10d
  __int64 v80; // rax
  _WORD *v81; // r8
  const wchar_t *v82; // rcx
  __int64 v83; // rdx
  _WORD *v84; // rcx
  __int64 v85; // rdx
  int v86; // r10d
  __int64 v87; // rax
  _WORD *v88; // r8
  const wchar_t *v89; // rcx
  __int64 v90; // rdx
  _WORD *v91; // rcx
  __int64 v92; // rax
  int v93; // r9d
  __int64 v94; // rax
  _WORD *v95; // r8
  _WORD *v96; // rcx
  __int64 v98; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v99; // [rsp+30h] [rbp-D0h]
  PVOID v100; // [rsp+38h] [rbp-C8h] BYREF
  PVOID v101; // [rsp+40h] [rbp-C0h]
  PVOID v102; // [rsp+48h] [rbp-B8h]
  PVOID v103; // [rsp+50h] [rbp-B0h] BYREF
  int v104; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v106; // [rsp+68h] [rbp-98h] BYREF
  __int64 v107; // [rsp+70h] [rbp-90h]
  _QWORD v108[5]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v109[12]; // [rsp+A0h] [rbp-60h] BYREF

  v107 = a3;
  v104 = 0;
  memset_0(v109, 0, 0x5Au);
  v102 = 0;
  v5 = *a1;
  v6 = 0;
  P = 0;
  v101 = 0;
  v103 = 0;
  v7 = *v5;
  v100 = 0;
  v106 = 0;
  if ( (unsigned int)_IsOsComponent(v7) )
  {
    if ( !a2 )
      return 0;
    v8 = dword_1801556E4;
    v9 = 260;
    if ( (unsigned int)dword_1801556E4 <= 2 )
    {
      a2[4896] = 3145776;
    }
    else if ( dword_1801556E4 == 3 )
    {
      *((_QWORD *)a2 + 2448) = 0x30003000300030LL;
    }
    else
    {
      if ( dword_1801556E4 != 4 )
        goto LABEL_17;
      v10 = 45;
      v11 = 260;
      v12 = L"0000f519feec486de87ed73cb92d3cac802400000000";
      v13 = a2 + 4896;
      do
      {
        if ( !v10 )
          break;
        if ( !*v12 )
          break;
        *v13++ = *v12++;
        --v10;
        --v11;
      }
      while ( v11 );
      v14 = v13 - 1;
      if ( v11 )
        v14 = v13;
      *v14 = 0;
      if ( !v11 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          36,
          -2147024774);
        goto LABEL_17;
      }
    }
    a2[5026] = 36;
    a2[5027] = v8;
    a2[5028] = 1;
LABEL_17:
    v15 = dword_1801556FC;
    if ( (unsigned int)dword_1801556FC <= 2 )
    {
      a2[5032] = 6881357;
    }
    else if ( dword_1801556FC == 3 )
    {
      *((_QWORD *)a2 + 2516) = 0x7200630069004DLL;
    }
    else
    {
      if ( dword_1801556FC != 4 )
        goto LABEL_31;
      v16 = 35;
      v17 = L"Microsoft Windows Operating System";
      v18 = 260;
      v19 = a2 + 5032;
      do
      {
        if ( !v16 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v16;
        --v18;
      }
      while ( v18 );
      v20 = v19 - 1;
      if ( v18 )
        v20 = v19;
      *v20 = 0;
      if ( !v18 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          37,
          -2147024774);
        goto LABEL_31;
      }
    }
    a2[5162] = 37;
    a2[5163] = v15;
    a2[5164] = 1;
LABEL_31:
    v21 = dword_180155714;
    if ( (unsigned int)dword_180155714 <= 2 )
    {
      a2[5168] = 6881357;
    }
    else if ( dword_180155714 == 3 )
    {
      *((_QWORD *)a2 + 2584) = 0x7200630069004DLL;
    }
    else
    {
      if ( dword_180155714 != 4 )
        goto LABEL_45;
      v22 = 22;
      v23 = L"Microsoft Corporation";
      v24 = 260;
      v25 = a2 + 5168;
      do
      {
        if ( !v22 )
          break;
        if ( !*v23 )
          break;
        *v25++ = *v23++;
        --v22;
        --v24;
      }
      while ( v24 );
      v26 = v25 - 1;
      if ( v24 )
        v26 = v25;
      *v26 = 0;
      if ( !v24 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          38,
          -2147024774);
        goto LABEL_45;
      }
    }
    a2[5298] = 38;
    a2[5299] = v21;
    a2[5300] = 1;
LABEL_45:
    v27 = dword_18015572C;
    if ( (unsigned int)dword_18015572C <= 2 )
    {
      a2[5304] = 3014704;
    }
    else if ( dword_18015572C == 3 )
    {
      *((_QWORD *)a2 + 2652) = 0x2E0030002E0030LL;
    }
    else
    {
      if ( dword_18015572C != 4 )
      {
LABEL_59:
        v33 = dword_180155744;
        if ( (unsigned int)dword_180155744 <= 2 )
        {
          a2[5440] = *(_DWORD *)L"0";
          goto LABEL_72;
        }
        if ( dword_180155744 == 3 )
        {
          *((_QWORD *)a2 + 2720) = *(_QWORD *)L"0";
          goto LABEL_72;
        }
        if ( dword_180155744 == 4 )
        {
          v34 = 2;
          v35 = L"0";
          v36 = a2 + 5440;
          do
          {
            if ( !v34 )
              break;
            if ( !*v35 )
              break;
            *v36++ = *v35++;
            --v34;
            --v9;
          }
          while ( v9 );
          v37 = v36 - 1;
          if ( v9 )
            v37 = v36;
          *v37 = 0;
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              40,
              -2147024774);
            return 0;
          }
LABEL_72:
          a2[5570] = 40;
          a2[5571] = v33;
          a2[5572] = 1;
        }
        return 0;
      }
      v28 = 8;
      v29 = L"0.0.0.0";
      v30 = 260;
      v31 = a2 + 5304;
      do
      {
        if ( !v28 )
          break;
        if ( !*v29 )
          break;
        *v31++ = *v29++;
        --v28;
        --v30;
      }
      while ( v30 );
      v32 = v31 - 1;
      if ( v30 )
        v32 = v31;
      *v32 = 0;
      if ( !v30 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          39,
          -2147024774);
        goto LABEL_59;
      }
    }
    a2[5434] = 39;
    a2[5435] = v27;
    a2[5436] = 1;
    goto LABEL_59;
  }
  FileKindDetail = AslFileMappingGetFileKindDetail(&v104, *a1);
  if ( FileKindDetail < 0 )
  {
    v38 = FileKindDetail | 0x10000000;
    AslLogCallPrintf(
      1,
      "_AttributesFromBOE",
      2211,
      "AslFileMapping::GetFileKindDetails failed [%x]",
      FileKindDetail | 0x10000000);
    return v38;
  }
  v99 = 0;
  if ( v104 <= 4 )
  {
LABEL_147:
    v59 = **a1;
    v60 = wcsrchr(v59, 0x5Cu);
    if ( v60 )
      v59 = v60 + 1;
    v61 = -1;
    do
      ++v61;
    while ( v59[v61] );
    v62 = 2 * v61 + 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v62);
    v102 = Heap;
    v58 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "_AttributesFromBOE", 2341, "Failed to alloc name string");
      v38 = -2147024882;
LABEL_251:
      v47 = v99;
      goto LABEL_252;
    }
    v64 = v62 >> 1;
    if ( !v64 )
    {
      v38 = -2147024809;
      goto LABEL_249;
    }
    if ( v64 > 0x7FFFFFFF )
    {
      v38 = -2147024809;
      *Heap = 0;
LABEL_249:
      v53 = "StringCbCopyW failed [%x]";
      v54 = 2349;
      goto LABEL_250;
    }
    v65 = 2147483646;
    v66 = v58;
    do
    {
      if ( !v65 )
        break;
      if ( !*v59 )
        break;
      *v66++ = *v59++;
      --v65;
      --v64;
    }
    while ( v64 );
    v67 = v66 - 1;
    v38 = v64 == 0 ? 0x8007007A : 0;
    if ( v64 )
      v67 = v66;
    *v67 = 0;
    if ( !v64 )
      goto LABEL_249;
LABEL_163:
    v68 = 260;
    if ( (v107 & 0x1000000000LL) != 0 )
    {
      v108[1] = v101;
      v108[3] = v99;
      v108[0] = v58;
      v108[2] = v6;
      v69 = AeComputeProgramIdentityHash(v108, v109);
      v38 = v69;
      if ( v69 < 0 )
      {
        LODWORD(v98) = v69;
        AslLogCallPrintf(1, "_AttributesFromBOE", 2368, "AeComputeProgramIdentityHash failed [%x]", v98);
        goto LABEL_251;
      }
      HIWORD(v109[0]) = 54;
      if ( a2 )
      {
        v70 = dword_1801556E4;
        if ( (unsigned int)dword_1801556E4 <= 2 )
        {
          a2[4896] = v109[0];
          goto LABEL_180;
        }
        if ( dword_1801556E4 == 3 )
        {
          *((_QWORD *)a2 + 2448) = v109[0];
          goto LABEL_180;
        }
        if ( dword_1801556E4 == 4 )
        {
          v71 = 45;
          v72 = 260;
          v73 = v109;
          v74 = a2 + 4896;
          do
          {
            if ( !v71 )
              break;
            if ( !*v73 )
              break;
            *v74++ = *v73++;
            --v71;
            --v72;
          }
          while ( v72 );
          v75 = v74 - 1;
          if ( v72 )
            v75 = v74;
          *v75 = 0;
          if ( !v72 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              36,
              -2147024774);
            goto LABEL_181;
          }
LABEL_180:
          a2[5026] = 36;
          a2[5027] = v70;
          a2[5028] = 1;
        }
      }
    }
LABEL_181:
    if ( !v102 || !*(_WORD *)v102 )
    {
      AslLogCallPrintf(1, "_AttributesFromBOE", 2400, "Failed to get a value to use for BOE App name.");
      v38 = -2147467259;
      goto LABEL_251;
    }
    v76 = -1;
    do
      ++v76;
    while ( *((_WORD *)v102 + v76) );
    _SetFileAttributeValue(v102, (unsigned int)(2 * v76 + 2), 37, a2);
    v77 = &S2;
    if ( v101 && *(_WORD *)v101 )
    {
      v78 = -1;
      do
        ++v78;
      while ( *((_WORD *)v102 + v78) );
      _SetFileAttributeValue(v102, (unsigned int)(2 * v78 + 2), 38, a2);
    }
    else if ( a2 )
    {
      v79 = dword_180155714;
      if ( (unsigned int)dword_180155714 <= 2 )
      {
        a2[5168] = 0;
      }
      else if ( dword_180155714 == 3 )
      {
        *((_QWORD *)a2 + 2584) = 0;
      }
      else
      {
        if ( dword_180155714 != 4 )
          goto LABEL_205;
        v80 = 1;
        v81 = a2 + 5168;
        v82 = &S2;
        v83 = 260;
        do
        {
          if ( !v80 )
            break;
          if ( !*v82 )
            break;
          *v81++ = *v82++;
          --v80;
          --v83;
        }
        while ( v83 );
        v84 = v81 - 1;
        if ( v83 )
          v84 = v81;
        *v84 = 0;
        if ( !v83 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            38,
            -2147024774);
          goto LABEL_205;
        }
      }
      a2[5298] = 38;
      a2[5299] = v79;
      a2[5300] = 1;
    }
LABEL_205:
    if ( v6 && *v6 )
    {
      v85 = -1;
      do
        ++v85;
      while ( v6[v85] );
      _SetFileAttributeValue(v6, (unsigned int)(2 * v85 + 2), 39, a2);
    }
    else if ( a2 )
    {
      v86 = dword_18015572C;
      if ( (unsigned int)dword_18015572C <= 2 )
      {
        a2[5304] = 0;
      }
      else if ( dword_18015572C == 3 )
      {
        *((_QWORD *)a2 + 2652) = 0;
      }
      else
      {
        if ( dword_18015572C != 4 )
          goto LABEL_225;
        v87 = 1;
        v88 = a2 + 5304;
        v89 = &S2;
        v90 = 260;
        do
        {
          if ( !v87 )
            break;
          if ( !*v89 )
            break;
          *v88++ = *v89++;
          --v87;
          --v90;
        }
        while ( v90 );
        v91 = v88 - 1;
        if ( v90 )
          v91 = v88;
        *v91 = 0;
        if ( !v90 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            39,
            -2147024774);
          goto LABEL_225;
        }
      }
      a2[5434] = 39;
      a2[5435] = v86;
      a2[5436] = 1;
    }
LABEL_225:
    if ( v99 && *v99 )
    {
      v47 = v99;
      v92 = -1;
      do
        ++v92;
      while ( v99[v92] );
      _SetFileAttributeValue(v99, (unsigned int)(2 * v92 + 2), 40, a2);
      goto LABEL_246;
    }
    if ( a2 )
    {
      v93 = dword_180155744;
      if ( (unsigned int)dword_180155744 <= 2 )
      {
        a2[5440] = 0;
        goto LABEL_244;
      }
      if ( dword_180155744 == 3 )
      {
        *((_QWORD *)a2 + 2720) = 0;
        goto LABEL_244;
      }
      if ( dword_180155744 == 4 )
      {
        v94 = 1;
        v95 = a2 + 5440;
        do
        {
          if ( !v94 )
            break;
          if ( !*v77 )
            break;
          *v95++ = *v77++;
          --v94;
          --v68;
        }
        while ( v68 );
        v96 = v95 - 1;
        if ( v68 )
          v96 = v95;
        *v96 = 0;
        if ( !v68 )
        {
          AslLogCallPrintf(
            1,
            "_SetFileAttributeValue",
            3178,
            "StringCbCopy failed to copy string attribute (index %d) [%x]",
            40,
            -2147024774);
          v47 = v99;
LABEL_246:
          v38 = 0;
          goto LABEL_252;
        }
LABEL_244:
        v47 = v99;
        a2[5570] = 40;
        a2[5571] = v93;
        a2[5572] = 1;
        goto LABEL_246;
      }
    }
    v47 = v99;
    goto LABEL_246;
  }
  Attribute = AslFileMapping::GetAttribute(a1, 0, 8);
  v41 = Attribute;
  if ( Attribute >= 0 )
  {
    v42 = a1 + 1;
    v41 = AslFileAttributeToString(&P, a1 + 1, 8);
    if ( v41 >= 0 )
    {
      v102 = P;
      if ( P && !*(_WORD *)P )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        v102 = 0;
      }
      goto LABEL_85;
    }
    v102 = P;
  }
  else
  {
    if ( Attribute != -1073741275 )
      AslLogCallPrintf(
        1,
        "AslFileMapping::AttributeToString",
        2669,
        "Failed to get attribute index %u [%x]",
        8,
        Attribute);
    v42 = a1 + 1;
  }
  if ( v41 != -1073741275 )
  {
    v45 = "AslFileMapping::GetAttribute failed to get PRODUCT_NAME [%x]";
    v46 = 2246;
    goto LABEL_97;
  }
LABEL_85:
  v43 = AslFileMapping::GetAttribute(a1, 0, 7);
  v41 = v43;
  if ( v43 >= 0 )
  {
    v41 = AslFileAttributeToString(&v103, v42, 7);
    v101 = v103;
    if ( v41 >= 0 )
    {
      if ( !v103 || *(_WORD *)v103 )
        goto LABEL_106;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v103);
      v101 = 0;
      v103 = 0;
LABEL_89:
      v44 = AslFileMapping::GetAttribute(a1, 0, 6);
      v41 = v44;
      if ( v44 >= 0 )
      {
        v41 = AslFileAttributeToString(&v103, v42, 6);
        v101 = v103;
        if ( v41 >= 0 )
        {
          if ( v103 && !*(_WORD *)v103 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v103);
            v101 = 0;
          }
          goto LABEL_106;
        }
      }
      else if ( v44 != -1073741275 )
      {
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 6, v44);
      }
      if ( v41 != -1073741275 )
        goto LABEL_93;
LABEL_106:
      v48 = AslFileMapping::GetAttribute(a1, 0, 5);
      v49 = v48;
      if ( v48 >= 0 )
      {
        v49 = AslFileAttributeToString(&v100, v42, 5);
        v6 = v100;
        if ( v49 >= 0 )
        {
          if ( !v100 || *(_WORD *)v100 )
            goto LABEL_139;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
          v6 = 0;
          v100 = 0;
          goto LABEL_110;
        }
      }
      else
      {
        if ( v48 == -1073741275 )
          goto LABEL_110;
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 5, v48);
      }
      if ( v49 != -1073741275 )
        goto LABEL_122;
LABEL_110:
      v50 = AslFileMapping::GetAttribute(a1, 0, 9);
      v49 = v50;
      if ( v50 >= 0 )
      {
        v49 = AslFileAttributeToString(&v100, v42, 9);
        v6 = v100;
        if ( v49 >= 0 )
        {
          if ( !v100 || *(_WORD *)v100 )
            goto LABEL_139;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
          v6 = 0;
          v100 = 0;
LABEL_114:
          v51 = AslFileMapping::GetAttribute(a1, 0, 4);
          v49 = v51;
          if ( v51 >= 0 )
          {
            v49 = AslFileAttributeToString(&v100, v42, 4);
            v6 = v100;
            if ( v49 >= 0 )
            {
              if ( !v100 || *(_WORD *)v100 )
                goto LABEL_139;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
              v6 = 0;
              v100 = 0;
LABEL_118:
              v52 = AslFileMapping::GetAttribute(a1, 0, 3);
              v49 = v52;
              if ( v52 >= 0 )
              {
                v49 = AslFileAttributeToString(&v100, v42, 3);
                v6 = v100;
                if ( v49 >= 0 )
                {
                  if ( v100 && !*(_WORD *)v100 )
                  {
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v100);
                    v6 = 0;
                  }
                  goto LABEL_139;
                }
              }
              else if ( v52 != -1073741275 )
              {
                AslLogCallPrintf(
                  1,
                  "AslFileMapping::AttributeToString",
                  2669,
                  "Failed to get attribute index %u [%x]",
                  3,
                  v52);
              }
              if ( v49 != -1073741275 )
                goto LABEL_122;
LABEL_139:
              v55 = AslFileMapping::GetAttribute(a1, &v106, 24);
              if ( v55 < 0 )
              {
                if ( v55 != -1073741275 )
                {
                  v38 = v55 | 0x10000000;
                  v53 = "AslFileMapping::GetAttribute failed to get VER_LANGUAGE [%x]";
                  v54 = 2325;
                  goto LABEL_250;
                }
              }
              else
              {
                v56 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x16u);
                v99 = v56;
                v47 = v56;
                if ( !v56 )
                {
                  AslLogCallPrintf(1, "_AttributesFromBOE", 2310, "Failed to alloc language string");
                  v38 = -2147024882;
                  goto LABEL_252;
                }
                v57 = StringCchPrintfW(v56, 0xBu, L"%d", *(unsigned int *)(v106 + 16));
                v38 = v57;
                if ( v57 < 0 )
                {
                  AslLogCallPrintf(1, "_AttributesFromBOE", 2318, "StringCchPrintfW failed [%x]", v57);
                  goto LABEL_252;
                }
              }
              v58 = v102;
              if ( v102 )
                goto LABEL_163;
              goto LABEL_147;
            }
          }
          else if ( v51 != -1073741275 )
          {
            AslLogCallPrintf(
              1,
              "AslFileMapping::AttributeToString",
              2669,
              "Failed to get attribute index %u [%x]",
              4,
              v51);
          }
          if ( v49 == -1073741275 )
            goto LABEL_118;
LABEL_122:
          v38 = v49 | 0x10000000;
          v53 = "AslFileMapping::GetAttribute failed [%x]";
          v54 = 2296;
LABEL_250:
          LODWORD(v98) = v38;
          AslLogCallPrintf(1, "_AttributesFromBOE", v54, v53, v98);
          goto LABEL_251;
        }
      }
      else if ( v50 != -1073741275 )
      {
        AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 9, v50);
      }
      if ( v49 != -1073741275 )
        goto LABEL_122;
      goto LABEL_114;
    }
  }
  else if ( v43 != -1073741275 )
  {
    AslLogCallPrintf(1, "AslFileMapping::AttributeToString", 2669, "Failed to get attribute index %u [%x]", 7, v43);
  }
  if ( v41 == -1073741275 )
    goto LABEL_89;
LABEL_93:
  v45 = "AslFileMapping::GetAttribute failed (BOE Publisher) [%x]";
  v46 = 2265;
LABEL_97:
  v38 = v41 | 0x10000000;
  LODWORD(v98) = v38;
  AslLogCallPrintf(1, "_AttributesFromBOE", v46, v45, v98);
  v47 = 0;
LABEL_252:
  if ( v102 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v102);
  if ( v101 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v101);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( v47 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v47);
  return v38;
}

```

## disassembly

```asm
0x180074370  mov     [rsp-8+arg_10], rbx
0x180074375  push    rbp
0x180074376  push    rsi
0x180074377  push    rdi
0x180074378  push    r12
0x18007437a  push    r13
0x18007437c  push    r14
0x18007437e  push    r15
0x180074380  lea     rbp, [rsp-10h]
0x180074385  sub     rsp, 110h
0x18007438c  mov     rax, cs:__security_cookie
0x180074393  xor     rax, rsp
0x180074396  mov     [rbp+40h+var_40], rax
0x18007439a  xor     ebx, ebx
0x18007439c  mov     [rsp+140h+var_D0], r8
0x1800743a1  mov     rdi, rdx
0x1800743a4  mov     [rsp+140h+var_E8], ebx
0x1800743a8  mov     r12, rcx
0x1800743ab  xor     edx, edx; Val
0x1800743ad  lea     rcx, [rbp+40h+var_A0]; void *
0x1800743b1  lea     r8d, [rbx+5Ah]; Size
0x1800743b5  call    memset_0
0x1800743ba  mov     ecx, ebx
0x1800743bc  mov     [rsp+140h+var_F8], rbx
0x1800743c1  mov     rcx, [r12]
0x1800743c5  mov     r15d, ebx
0x1800743c8  mov     [rsp+140h+P], rbx
0x1800743cd  mov     [rsp+140h+var_100], rbx
0x1800743d2  mov     [rsp+140h+var_F0], rbx
0x1800743d7  mov     rcx, [rcx]; lpFileName
0x1800743da  mov     [rsp+140h+var_108], rbx
0x1800743df  mov     [rsp+140h+var_D8], rbx
0x1800743e4  call    ?_IsOsComponent@@YAHPEBG@Z; _IsOsComponent(ushort const *)
0x1800743e9  xor     r11d, r11d
0x1800743ec  test    eax, eax
0x1800743ee  jz      loc_180074886
0x1800743f4  test    rdi, rdi
0x1800743f7  jz      loc_18007487E
0x1800743fd  mov     r10d, cs:dword_1801556E4
0x180074404  lea     esi, [rbx+1]
0x180074407  lea     r12, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x18007440e  mov     ecx, r10d
0x180074411  lea     r15, aSetfileattribu_0; "_SetFileAttributeValue"
0x180074418  mov     r14d, 104h
0x18007441e  mov     r13d, 8007007Ah
0x180074424  mov     ebx, 0C6Ah
0x180074429  test    r10d, r10d
0x18007442c  jz      loc_1800744DE
0x180074432  sub     ecx, esi
0x180074434  jz      loc_1800744DE
0x18007443a  sub     ecx, esi
0x18007443c  jz      loc_1800744DE
0x180074442  sub     ecx, esi
0x180074444  jz      loc_1800744CB
0x18007444a  cmp     ecx, esi
0x18007444c  jnz     loc_1800744FF
0x180074452  lea     eax, [rsi+2Ch]
0x180074455  mov     edx, r14d
0x180074458  lea     rcx, a0000f519feec48; "0000f519feec486de87ed73cb92d3cac8024000"...
0x18007445f  lea     r8, [rdi+4C80h]
0x180074466  test    rax, rax
0x180074469  jz      short loc_180074489
0x18007446b  movzx   r9d, word ptr [rcx]
0x18007446f  test    r9w, r9w
0x180074473  jz      short loc_180074489
0x180074475  mov     [r8], r9w
0x180074479  add     rcx, 2
0x18007447d  add     r8, 2
0x180074481  sub     rax, rsi
0x180074484  sub     rdx, rsi
0x180074487  jnz     short loc_180074466
0x180074489  mov     rax, rdx
0x18007448c  lea     rcx, [r8-2]
0x180074490  neg     rax
0x180074493  sbb     r9d, r9d
0x180074496  not     r9d
0x180074499  and     r9d, r13d
0x18007449c  test    rdx, rdx
0x18007449f  cmovnz  rcx, r8
0x1800744a3  mov     [rcx], r11w
0x1800744a7  jnz     short loc_1800744E8
0x1800744a9  mov     [rsp+140h+var_118], r9d
0x1800744ae  mov     r8, rbx
0x1800744b1  mov     r9, r12
0x1800744b4  mov     dword ptr [rsp+140h+var_120], 24h ; '$'
0x1800744bc  mov     rdx, r15
0x1800744bf  mov     ecx, esi
0x1800744c1  call    AslLogCallPrintf
0x1800744c6  xor     r11d, r11d
0x1800744c9  jmp     short loc_1800744FF
0x1800744cb  mov     rax, 30003000300030h
0x1800744d5  mov     [rdi+4C80h], rax
0x1800744dc  jmp     short loc_1800744E8
0x1800744de  mov     dword ptr [rdi+4C80h], 300030h
0x1800744e8  mov     dword ptr [rdi+4E88h], 24h ; '$'
0x1800744f2  mov     [rdi+4E8Ch], r10d
0x1800744f9  mov     [rdi+4E90h], esi
0x1800744ff  mov     r10d, cs:dword_1801556FC
0x180074506  mov     rax, 7200630069004Dh
0x180074510  mov     ecx, r10d
0x180074513  test    r10d, r10d
0x180074516  jz      loc_1800745C0
0x18007451c  sub     ecx, esi
0x18007451e  jz      loc_1800745C0
0x180074524  sub     ecx, esi
0x180074526  jz      loc_1800745C0
0x18007452c  sub     ecx, esi
0x18007452e  jz      loc_1800745B7
0x180074534  cmp     ecx, esi
0x180074536  jnz     loc_1800745E1
0x18007453c  mov     eax, 23h ; '#'
0x180074541  lea     rcx, aMicrosoftWindo; "Microsoft Windows Operating System"
0x180074548  mov     rdx, r14
0x18007454b  lea     r8, [rdi+4EA0h]
0x180074552  test    rax, rax
0x180074555  jz      short loc_180074575
0x180074557  movzx   r9d, word ptr [rcx]
0x18007455b  test    r9w, r9w
0x18007455f  jz      short loc_180074575
0x180074561  mov     [r8], r9w
0x180074565  add     rcx, 2
0x180074569  add     r8, 2
0x18007456d  sub     rax, rsi
0x180074570  sub     rdx, rsi
0x180074573  jnz     short loc_180074552
0x180074575  mov     rax, rdx
0x180074578  lea     rcx, [r8-2]
0x18007457c  neg     rax
0x18007457f  sbb     r9d, r9d
0x180074582  not     r9d
0x180074585  and     r9d, r13d
0x180074588  test    rdx, rdx
0x18007458b  cmovnz  rcx, r8
0x18007458f  mov     [rcx], r11w
0x180074593  jnz     short loc_1800745CA
0x180074595  mov     [rsp+140h+var_118], r9d
0x18007459a  mov     r8, rbx
0x18007459d  mov     r9, r12
0x1800745a0  mov     dword ptr [rsp+140h+var_120], 25h ; '%'
0x1800745a8  mov     rdx, r15
0x1800745ab  mov     ecx, esi
0x1800745ad  call    AslLogCallPrintf
0x1800745b2  xor     r11d, r11d
0x1800745b5  jmp     short loc_1800745E1
0x1800745b7  mov     [rdi+4EA0h], rax
0x1800745be  jmp     short loc_1800745CA
0x1800745c0  mov     dword ptr [rdi+4EA0h], 69004Dh
0x1800745ca  mov     dword ptr [rdi+50A8h], 25h ; '%'
0x1800745d4  mov     [rdi+50ACh], r10d
0x1800745db  mov     [rdi+50B0h], esi
0x1800745e1  mov     r10d, cs:dword_180155714
0x1800745e8  mov     ecx, r10d
0x1800745eb  test    r10d, r10d
0x1800745ee  jz      loc_1800746A1
0x1800745f4  sub     ecx, esi
0x1800745f6  jz      loc_1800746A1
0x1800745fc  sub     ecx, esi
0x1800745fe  jz      loc_1800746A1
0x180074604  sub     ecx, esi
0x180074606  jz      loc_18007468E
0x18007460c  cmp     ecx, esi
0x18007460e  jnz     loc_1800746C2
0x180074614  mov     r8d, 16h
0x18007461a  lea     rax, aMicrosoftCorpo; "Microsoft Corporation"
0x180074621  mov     rdx, r14
0x180074624  lea     r9, [rdi+50C0h]
0x18007462b  test    r8, r8
0x18007462e  jz      short loc_18007464C
0x180074630  movzx   ecx, word ptr [rax]
0x180074633  test    cx, cx
0x180074636  jz      short loc_18007464C
0x180074638  mov     [r9], cx
0x18007463c  add     rax, 2
0x180074640  add     r9, 2
0x180074644  sub     r8, rsi
0x180074647  sub     rdx, rsi
0x18007464a  jnz     short loc_18007462B
0x18007464c  mov     rax, rdx
0x18007464f  lea     rcx, [r9-2]
0x180074653  neg     rax
0x180074656  sbb     r8d, r8d
0x180074659  not     r8d
0x18007465c  and     r8d, r13d
0x18007465f  test    rdx, rdx
0x180074662  cmovnz  rcx, r9
0x180074666  mov     [rcx], r11w
0x18007466a  jnz     short loc_1800746AB
0x18007466c  mov     [rsp+140h+var_118], r8d
0x180074671  mov     r9, r12
0x180074674  mov     r8, rbx
0x180074677  mov     dword ptr [rsp+140h+var_120], 26h ; '&'
0x18007467f  mov     rdx, r15
0x180074682  mov     ecx, esi
0x180074684  call    AslLogCallPrintf
0x180074689  xor     r11d, r11d
0x18007468c  jmp     short loc_1800746C2
0x18007468e  mov     rax, 7200630069004Dh
0x180074698  mov     [rdi+50C0h], rax
0x18007469f  jmp     short loc_1800746AB
0x1800746a1  mov     dword ptr [rdi+50C0h], 69004Dh
0x1800746ab  mov     dword ptr [rdi+52C8h], 26h ; '&'
0x1800746b5  mov     [rdi+52CCh], r10d
0x1800746bc  mov     [rdi+52D0h], esi
0x1800746c2  mov     r10d, cs:dword_18015572C
0x1800746c9  mov     ecx, r10d
0x1800746cc  test    r10d, r10d
0x1800746cf  jz      loc_180074785
0x1800746d5  sub     ecx, esi
0x1800746d7  jz      loc_180074785
0x1800746dd  sub     ecx, esi
0x1800746df  jz      loc_180074785
0x1800746e5  sub     ecx, esi
0x1800746e7  jz      loc_180074772
0x1800746ed  cmp     ecx, esi
0x1800746ef  jnz     loc_1800747A6
0x1800746f5  mov     r13d, 8
0x1800746fb  lea     rax, a0000; "0.0.0.0"
0x180074702  mov     rdx, r14
0x180074705  lea     r8, [rdi+52E0h]
0x18007470c  test    r13, r13
0x18007470f  jz      short loc_18007472D
0x180074711  movzx   ecx, word ptr [rax]
0x180074714  test    cx, cx
0x180074717  jz      short loc_18007472D
0x180074719  mov     [r8], cx
0x18007471d  add     rax, 2
0x180074721  add     r8, 2
0x180074725  sub     r13, rsi
0x180074728  sub     rdx, rsi
0x18007472b  jnz     short loc_18007470C
0x18007472d  mov     rax, rdx
0x180074730  lea     rcx, [r8-2]
0x180074734  neg     rax
0x180074737  mov     r13d, 8007007Ah
0x18007473d  sbb     r9d, r9d
0x180074740  not     r9d
0x180074743  and     r9d, r13d
0x180074746  test    rdx, rdx
0x180074749  cmovnz  rcx, r8
0x18007474d  mov     [rcx], r11w
0x180074751  jnz     short loc_18007478F
0x180074753  mov     [rsp+140h+var_118], r9d
0x180074758  mov     r8, rbx
0x18007475b  mov     r9, r12
0x18007475e  mov     dword ptr [rsp+140h+var_120], 27h ; '''
0x180074766  mov     rdx, r15
0x180074769  mov     ecx, esi
0x18007476b  call    AslLogCallPrintf
0x180074770  jmp     short loc_1800747A6
0x180074772  mov     rax, 2E0030002E0030h
0x18007477c  mov     [rdi+52E0h], rax
0x180074783  jmp     short loc_18007478F
0x180074785  mov     dword ptr [rdi+52E0h], 2E0030h
0x18007478f  mov     dword ptr [rdi+54E8h], 27h ; '''
0x180074799  mov     [rdi+54ECh], r10d
0x1800747a0  mov     [rdi+54F0h], esi
0x1800747a6  mov     r11d, cs:dword_180155744
0x1800747ad  xor     r8d, r8d
0x1800747b0  mov     ecx, r11d
0x1800747b3  test    r11d, r11d
0x1800747b6  jz      loc_180074857
0x1800747bc  sub     ecx, esi
0x1800747be  jz      loc_180074857
0x1800747c4  sub     ecx, esi
0x1800747c6  jz      loc_180074857
0x1800747cc  sub     ecx, esi
0x1800747ce  jz      short loc_180074847
0x1800747d0  cmp     ecx, esi
0x1800747d2  jnz     loc_18007487B
0x1800747d8  lea     eax, [r8+2]
0x1800747dc  lea     rcx, a0_0; "0"
0x1800747e3  lea     r10, [rdi+5500h]
0x1800747ea  test    rax, rax
0x1800747ed  jz      short loc_18007480B
0x1800747ef  movzx   edx, word ptr [rcx]
0x1800747f2  test    dx, dx
0x1800747f5  jz      short loc_18007480B
0x1800747f7  mov     [r10], dx
0x1800747fb  add     rcx, 2
0x1800747ff  add     r10, 2
0x180074803  sub     rax, rsi
0x180074806  sub     r14, rsi
0x180074809  jnz     short loc_1800747EA
0x18007480b  mov     rax, r14
0x18007480e  lea     r9, [r10-2]
0x180074812  neg     rax
0x180074815  sbb     ecx, ecx
0x180074817  not     ecx
0x180074819  and     ecx, r13d
0x18007481c  test    r14, r14
0x18007481f  cmovnz  r9, r10
0x180074823  mov     [r9], r8w
0x180074827  jnz     short loc_180074864
0x180074829  mov     [rsp+140h+var_118], ecx
0x18007482d  mov     r9, r12
0x180074830  mov     ecx, esi
0x180074832  mov     dword ptr [rsp+140h+var_120], 28h ; '('
0x18007483a  mov     r8, rbx
0x18007483d  mov     rdx, r15
0x180074840  call    AslLogCallPrintf
  ... truncated ...
```
