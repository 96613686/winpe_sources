# PipInitComputerIds

- ea: `0x140ca4cbc`
- end: `0x140ca61fd`
- name: `PipInitComputerIds`
- size: `5441`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140ca4514`

## callees

- `0x140393628`
- `0x140393c10`
- `0x1403f2d50`
- `0x140406bc0`
- `0x140461580`
- `0x1404729c0`
- `0x1405dbd84`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406db490`
- `0x1406dc470`
- `0x1406f4480`
- `0x1406f4880`
- `0x140770a60`
- `0x14087b818`
- `0x1408d3940`
- `0x1408d4330`
- `0x1408eeff0`
- `0x14092bbb0`
- `0x14097e5b0`
- `0x1409df8c0`
- `0x140a3b768`
- `0x140a7c404`
- `0x140afc0e8`
- `0x140bae410`
- `0x140bae8e0`
- `0x140c62d98`
- `0x140c64cc4`
- `0x140c64d38`
- `0x140ca4cbc`

## string_xrefs

- `0x140ca4d7e`: `ComputerIds`
- `0x140ca5be8`: `ComputerMetadata\`
- `0x140ca5d42`: `COMPUTER\`
- `0x140ca60fe`: `COMPUTER`
- `0x140ca616d`: `COMPUTER\Generic`

## pseudocode

```c
__int64 __fastcall PipInitComputerIds(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rsi
  __int64 v4; // rcx
  int v5; // eax
  HANDLE v6; // r15
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 Struct; // rax
  int v15; // edx
  unsigned __int64 v16; // rcx
  unsigned __int8 *v17; // rdi
  _BYTE *v18; // rsi
  int String; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // edx
  __int64 v26; // rdi
  _BYTE *v27; // rsi
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // edx
  unsigned __int8 *v32; // rcx
  unsigned __int8 *v33; // rdi
  _BYTE *v34; // rsi
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  __int64 i; // rsi
  __int64 v42; // rax
  int v43; // r12d
  __int64 j; // rsi
  PVOID v45; // r14
  __int64 v46; // rax
  wchar_t *Buffer; // rax
  HANDLE v48; // r13
  unsigned int v49; // edi
  PVOID v50; // rsi
  __int64 v51; // rcx
  __int64 v52; // rdi
  __int64 v53; // rcx
  __int64 k; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  void *Pool2; // rax
  PVOID v60; // rdx
  __int64 m; // rdi
  __int64 v62; // rcx
  __int64 v63; // r8
  HANDLE v64; // r13
  wchar_t *v66; // rcx
  wchar_t *v67; // r12
  char *v68; // rsi
  unsigned int v69; // r14d
  void *v70; // rax
  int v71; // r15d
  wchar_t *v72; // rcx
  wchar_t *v73; // rax
  unsigned __int16 Length; // cx
  wchar_t v75; // dx
  wchar_t *v76; // r8
  wchar_t *v77; // rcx
  char *v78; // rax
  char *v79; // rcx
  char *v80; // rdi
  unsigned __int16 v81; // ax
  int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // r8
  PVOID Data; // [rsp+20h] [rbp-E0h]
  __int64 v86; // [rsp+30h] [rbp-D0h]
  __int64 v87; // [rsp+30h] [rbp-D0h]
  UNICODE_STRING ValueName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v89; // [rsp+80h] [rbp-80h]
  PVOID v90; // [rsp+88h] [rbp-78h]
  unsigned __int8 v91; // [rsp+90h] [rbp-70h]
  unsigned __int8 v92; // [rsp+91h] [rbp-6Fh]
  __int64 v93; // [rsp+98h] [rbp-68h]
  PVOID v94; // [rsp+A0h] [rbp-60h] BYREF
  int v95; // [rsp+A8h] [rbp-58h] BYREF
  size_t pcchRemaining; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v97; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v98; // [rsp+C8h] [rbp-38h]
  __int128 v99; // [rsp+D8h] [rbp-28h]
  UNICODE_STRING *p_DestinationString; // [rsp+E8h] [rbp-18h]
  HANDLE Handle; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE KeyHandle; // [rsp+F8h] [rbp-8h] BYREF
  PVOID P; // [rsp+100h] [rbp+0h] BYREF
  _WORD v104[16]; // [rsp+108h] [rbp+8h]
  UNICODE_STRING DestinationString; // [rsp+128h] [rbp+28h] BYREF
  UNICODE_STRING v106; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v107[15]; // [rsp+150h] [rbp+50h] BYREF
  _GUID fmtid; // [rsp+240h] [rbp+140h] BYREF
  __int128 pid; // [rsp+250h] [rbp+150h]
  __int128 v110; // [rsp+260h] [rbp+160h]
  UNICODE_STRING v111; // [rsp+270h] [rbp+170h] BYREF
  UNICODE_STRING v112; // [rsp+280h] [rbp+180h] BYREF
  UNICODE_STRING v113; // [rsp+290h] [rbp+190h] BYREF
  UNICODE_STRING v114; // [rsp+2A0h] [rbp+1A0h] BYREF
  UNICODE_STRING v115; // [rsp+2B0h] [rbp+1B0h] BYREF
  UNICODE_STRING v116; // [rsp+2C0h] [rbp+1C0h] BYREF
  UNICODE_STRING v117; // [rsp+2D0h] [rbp+1D0h] BYREF
  UNICODE_STRING v118; // [rsp+2E0h] [rbp+1E0h] BYREF
  UNICODE_STRING v119; // [rsp+2F0h] [rbp+1F0h] BYREF
  UNICODE_STRING v120; // [rsp+300h] [rbp+200h] BYREF
  wchar_t SourceString; // [rsp+310h] [rbp+210h] BYREF
  wchar_t pszDest[8]; // [rsp+318h] [rbp+218h] BYREF

  KeyHandle = 0;
  Handle = 0;
  P = 0;
  v2 = 0;
  v95 = 0;
  v93 = 0;
  p_DestinationString = 0;
  v94 = 0;
  v3 = 0;
  DestinationString = 0;
  v106 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  fmtid = 0;
  pid = 0;
  v110 = 0;
  ValueName = 0;
  memset_0(&v111, 0, 0xA0u);
  v5 = PipHardwareConfigOpenKey(v4, 983103, &KeyHandle);
  v6 = KeyHandle;
  v7 = v5;
  if ( v5 >= 0 )
  {
    PnpCtxRegDeleteTree(*(_QWORD *)&PiPnpRtlCtx, KeyHandle, L"ComputerIds");
    *(_DWORD *)&ValueName.Length = 1572886;
    ValueName.Buffer = L"ComputerIds";
    v7 = IopCreateRegistryKeyEx(&Handle, v6, &ValueName, 983103, 0, 0, v86);
    if ( v7 >= 0 )
    {
      PnpCtxRegDeleteTree(*(_QWORD *)&PiPnpRtlCtx, v6, L"ProductIds");
      *(_DWORD *)&ValueName.Length = 1441812;
      ValueName.Buffer = L"ProductIds";
      LODWORD(v90) = IopCreateRegistryKeyEx(&P, v6, &ValueName, 983103, 0, 0, v87);
      v7 = (int)v90;
      if ( (int)v90 >= 0 )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(a1 + 240) + 56LL);
        if ( v8 )
        {
          v9 = *(_QWORD *)(v8 + 16);
          if ( v9 )
          {
            v10 = *(unsigned int *)(v8 + 12);
            v93 = v10;
            v11 = MmMapIoSpaceEx(v9, v10, 2);
            v89 = v11;
            v13 = v11;
            if ( !v11 )
            {
              v7 = -1073741670;
              v3 = 0;
              goto LABEL_152;
            }
            LOBYTE(v12) = 1;
            Struct = PipSmBiosFindStruct(v12, 0, v11, (unsigned int)v10);
            v17 = (unsigned __int8 *)Struct;
            if ( Struct )
            {
              v18 = (_BYTE *)(Struct + 5);
              if ( Struct + 5 <= Struct + (unsigned __int64)*(unsigned __int8 *)(Struct + 1) )
              {
                LOBYTE(v15) = *(_BYTE *)(Struct + 4);
                String = PipSmBiosGetString(Struct, v15, v13, v10, &v111);
                LODWORD(v90) = String;
                v7 = String;
                if ( String == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( String < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 27 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = v17[26];
                v20 = PipSmBiosGetString((int)v17, v15, v13, v10, &v112);
                LODWORD(v90) = v20;
                v7 = v20;
                if ( v20 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v20 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 6 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = *v18;
                v21 = PipSmBiosGetString((int)v17, v15, v13, v10, &v113);
                LODWORD(v90) = v21;
                v7 = v21;
                if ( v21 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v21 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 26 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = v17[25];
                v22 = PipSmBiosGetString((int)v17, v15, v13, v10, &v114);
                LODWORD(v90) = v22;
                v7 = v22;
                if ( v22 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v22 < 0 )
                {
                  goto LABEL_22;
                }
              }
              v16 = (unsigned __int64)&v17[v17[1]];
              if ( (unsigned __int64)(v17 + 7) > v16 )
              {
                v2 = 0;
              }
              else
              {
                LOBYTE(v15) = v17[6];
                v23 = PipSmBiosGetString((int)v17, v15, v13, v10, &v120);
                LODWORD(v90) = v23;
                v2 = 0;
                v7 = v23;
                if ( v23 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v23 < 0 )
                {
                  goto LABEL_22;
                }
              }
            }
            LOBYTE(v16) = 2;
            v24 = PipSmBiosFindStruct(v16, 10, v13, (unsigned int)v10);
            v26 = v24;
            if ( v24 )
            {
              v27 = (_BYTE *)(v24 + 5);
              if ( v24 + 5 <= v24 + (unsigned __int64)*(unsigned __int8 *)(v24 + 1) )
              {
                LOBYTE(v25) = *(_BYTE *)(v24 + 4);
                v28 = PipSmBiosGetString(v24, v25, v13, v10, &v117);
                LODWORD(v90) = v28;
                v7 = v28;
                if ( v28 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v28 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v26 + 6 <= v26 + (unsigned __int64)*(unsigned __int8 *)(v26 + 1) )
              {
                LOBYTE(v25) = *v27;
                v29 = PipSmBiosGetString(v26, v25, v13, v10, &v118);
                LODWORD(v90) = v29;
                v7 = v29;
                if ( v29 == -1073741275 )
                {
                  LODWORD(v90) = 0;
                }
                else if ( v29 < 0 )
                {
                  goto LABEL_22;
                }
              }
            }
            v92 = 0;
            v91 = 0;
            v30 = PipSmBiosFindStruct(0, 0, v13, (unsigned int)v10);
            v33 = (unsigned __int8 *)v30;
            if ( !v30 )
            {
LABEL_59:
              LODWORD(pcchRemaining) = 0;
              LOBYTE(v32) = 3;
              v39 = PipSmBiosFindStruct(v32, 0, v13, (unsigned int)v10);
              if ( v39 && v39 + 6 <= v39 + (unsigned __int64)*(unsigned __int8 *)(v39 + 1) )
              {
                v40 = *(_BYTE *)(v39 + 5) & 0x7F;
                v95 = v40;
              }
              else
              {
                v40 = v95;
              }
              if ( v40 )
              {
                ValueName.Buffer = L"EnclosureType";
                *(_DWORD *)&ValueName.Length = 1835034;
                ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &v95, 4u);
              }
              for ( i = 0; i != 10; ++i )
              {
                v42 = 16 * i;
                if ( *((_QWORD *)&v111.Buffer + 2 * i) && !*(unsigned __int16 *)((char *)&v111.Length + v42) )
                  RtlFreeAnsiString((UNICODE_STRING *)((char *)&v111 + v42));
              }
              v43 = v91;
              for ( j = 0; j != 10; ++j )
              {
                RtlInitUnicodeString(&ValueName, off_14000B690[j]);
                if ( *(&v111.Length + 8 * j) )
                {
                  if ( (int)PnpUnicodeStringToWstr(&v94, 0, &v111 + j) >= 0 )
                  {
                    v45 = v94;
                    v46 = -1;
                    do
                      ++v46;
                    while ( *((_WORD *)v94 + v46) );
                    ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, v94, 2 * v46 + 2);
                    PnpUnicodeStringToWstrFree(v45, &v111 + j);
                    v2 = 0;
                  }
                }
                else
                {
                  ZwDeleteValueKey(KeyHandle, &ValueName);
                }
              }
              Buffer = v111.Buffer;
              v48 = Handle;
              v7 = (int)v90;
              v49 = pcchRemaining;
              if ( v111.Buffer )
              {
                v50 = P;
                if ( v113.Buffer && v115.Buffer && v116.Buffer )
                {
                  LODWORD(Data) = v43;
                  v7 = RtlStringCchPrintfW(pszDest, 8u, L"%02x&%02x", v92, Data);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  RtlInitUnicodeString(&DestinationString, pszDest);
                  if ( v114.Buffer )
                  {
                    v51 = 0;
                    *(_QWORD *)&v97 = &v111;
                    *((_QWORD *)&v97 + 1) = &v112;
                    do
                    {
                      *((_QWORD *)&v98 + v51) = &v113 + v51;
                      ++v51;
                    }
                    while ( v51 != 4 );
                    v104[0] = 0;
                    p_DestinationString = &DestinationString;
                    v7 = PipCreateComputerId(v48, v50, &v97, 7, v107);
                    v49 = 1;
                    if ( v7 < 0 )
                      goto LABEL_151;
                  }
                  *(_QWORD *)&v97 = &v111;
                  *((_QWORD *)&v97 + 1) = &v112;
                  *(_QWORD *)&v98 = &v113;
                  *((_QWORD *)&v98 + 1) = &v115;
                  *(_QWORD *)&v99 = &v116;
                  *((_QWORD *)&v99 + 1) = &DestinationString;
                  v104[v49] = 1;
                  v7 = PipCreateComputerId(v48, v50, &v97, 6, &v107[v49]);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  *(_QWORD *)&v97 = &v111;
                  v52 = v49 + 1;
                  *((_QWORD *)&v97 + 1) = &v113;
                  *(_QWORD *)&v98 = &v115;
                  v104[v52] = 2;
                  *((_QWORD *)&v98 + 1) = &v116;
                  *(_QWORD *)&v99 = &DestinationString;
                  v7 = PipCreateComputerId(v48, v50, &v97, 5, &v107[(unsigned int)v52]);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  Buffer = v111.Buffer;
                  v49 = v52 + 1;
                }
                if ( Buffer )
                {
                  if ( v113.Buffer )
                  {
                    if ( v114.Buffer )
                    {
                      if ( v117.Buffer && v118.Buffer )
                      {
                        v53 = 0;
                        *(_QWORD *)&v97 = &v111;
                        *((_QWORD *)&v97 + 1) = &v112;
                        do
                        {
                          *((_QWORD *)&v98 + v53) = &v113 + v53;
                          ++v53;
                        }
                        while ( v53 != 2 );
                        for ( k = 0; k != 2; ++k )
                          *((_QWORD *)&v99 + k) = &v117 + k;
                        v104[v49] = 3;
                        v7 = PipCreateComputerId(v48, v50, &v97, 6, &v107[v49]);
                        if ( v7 < 0 )
                          goto LABEL_151;
                        ++v49;
                      }
                      v55 = 0;
                      *(_QWORD *)&v97 = &v111;
                      *((_QWORD *)&v97 + 1) = &v112;
                      do
                      {
                        *((_QWORD *)&v98 + v55) = &v113 + v55;
                        ++v55;
                      }
                      while ( v55 != 2 );
                      v104[v49] = 4;
                      v7 = PipCreateComputerId(v48, v50, &v97, 4, &v107[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v97 = &v111;
                    *((_QWORD *)&v97 + 1) = &v112;
                    *(_QWORD *)&v98 = &v113;
                    v104[v49] = 5;
                    v7 = PipCreateComputerId(v48, v50, &v97, 3, &v107[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v111.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v114.Buffer )
                  {
                    if ( v117.Buffer && v118.Buffer )
                    {
                      v56 = 0;
                      *(_QWORD *)&v97 = &v111;
                      *((_QWORD *)&v97 + 1) = &v114;
                      do
                      {
                        *((_QWORD *)&v98 + v56) = &v117 + v56;
                        ++v56;
                      }
                      while ( v56 != 2 );
                      v104[v49] = 6;
                      v7 = PipCreateComputerId(v48, v50, &v97, 4, &v107[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v97 = &v111;
                    *((_QWORD *)&v97 + 1) = &v114;
                    v104[v49] = 7;
                    v7 = PipCreateComputerId(v48, v50, &v97, 2, &v107[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v111.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v113.Buffer )
                  {
                    if ( v117.Buffer && v118.Buffer )
                    {
                      *(_QWORD *)&v97 = &v111;
                      *((_QWORD *)&v97 + 1) = &v113;
                      *(_QWORD *)&v98 = &v117;
                      *((_QWORD *)&v98 + 1) = &v118;
                      v104[v49] = 8;
                      v7 = PipCreateComputerId(v48, v50, &v97, 4, &v107[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v97 = &v111;
                    *((_QWORD *)&v97 + 1) = &v113;
                    v104[v49] = 9;
                    v7 = PipCreateComputerId(v48, v50, &v97, 2, &v107[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v111.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v112.Buffer )
                  {
                    if ( v118.Buffer && v117.Buffer )
                    {
                      v57 = 0;
                      *(_QWORD *)&v97 = &v111;
                      *((_QWORD *)&v97 + 1) = &v112;
                      do
                      {
                        *((_QWORD *)&v98 + v57) = &v117 + v57;
                        ++v57;
                      }
                      while ( v57 != 2 );
                      v104[v49] = 10;
                      v7 = PipCreateComputerId(v48, v50, &v97, 4, &v107[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v97 = &v111;
                    *((_QWORD *)&v97 + 1) = &v112;
                    v104[v49] = 11;
                    v7 = PipCreateComputerId(v48, v50, &v97, 2, &v107[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v111.Buffer;
                    ++v49;
                  }
                  if ( Buffer )
                  {
                    if ( v95 )
                    {
                      v7 = RtlStringCchPrintfW(&SourceString, 4u, L"%x");
                      if ( v7 < 0 )
                        goto LABEL_151;
                      RtlInitUnicodeString(&v106, &SourceString);
                      *(_QWORD *)&v97 = &v111;
                      *((_QWORD *)&v97 + 1) = &v106;
                      v104[v49] = 12;
                      v7 = PipCreateComputerId(v48, 0, &v97, 2, &v107[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      Buffer = v111.Buffer;
                      ++v49;
                    }
                    if ( Buffer )
                    {
                      if ( v118.Buffer && v117.Buffer )
                      {
                        v58 = 0;
                        *(_QWORD *)&v97 = &v111;
                        do
                        {
                          *((_QWORD *)&v97 + v58 + 1) = &v117 + v58;
                          ++v58;
                        }
                        while ( v58 != 2 );
                        v104[v49] = 13;
                        v7 = PipCreateComputerId(v48, 0, &v97, 3, &v107[v49]);
                        if ( v7 < 0 )
                          goto LABEL_151;
                        ++v49;
                      }
                      *(_QWORD *)&v97 = &v111;
                      v104[v49] = 14;
                      v7 = PipCreateComputerId(v48, 0, &v97, 1, &v107[v49]);
                      if ( v7 >= 0 )
                      {
                        ++v49;
                        goto LABEL_149;
                      }
LABEL_151:
                      v3 = v89;
                      goto LABEL_152;
                    }
                  }
                }
              }
LABEL_149:
              Pool2 = (void *)ExAllocatePool2(256, 112 * v49 + 2, 1852403792);
              P = Pool2;
              v60 = Pool2;
              if ( !Pool2 )
              {
                v7 = -1073741670;
                goto LABEL_151;
              }
              v66 = (wchar_t *)Pool2;
              ValueName.Buffer = (wchar_t *)Pool2;
              v90 = 0;
              ValueName.MaximumLength = 112 * v49 + 2;
              v67 = 0;
              v68 = 0;
              if ( v49 )
              {
                while ( 1 )
                {
                  ValueName.Length = 0;
                  v7 = RtlUnicodeStringCopyStringEx(&ValueName, L"ComputerMetadata\\", &ValueName, 0);
                  if ( v7 < 0 )
                    goto LABEL_219;
                  v7 = RtlStringFromGUIDEx(&v107[v2], &ValueName, 0);
                  if ( v7 < 0 )
                    goto LABEL_219;
                  v7 = RtlUpcaseUnicodeString(&ValueName, &ValueName, 0);
                  if ( v7 < 0 )
                    goto LABEL_219;
                  ValueName.MaximumLength -= 78;
                  v66 = ValueName.Buffer + 39;
                  ++v2;
                  ValueName.Buffer += 39;
                  if ( v2 >= v49 )
                  {
                    v60 = P;
                    break;
                  }
                }
              }
              v69 = 0;
              if ( v7 >= 0 )
              {
                *v66 = 0;
                ++ValueName.Buffer;
                v7 = PnpSetObjectProperty(
                       PiPnpRtlCtx,
                       (unsigned int)L"{00000000-0000-0000-FFFF-FFFFFFFFFFFF}",
                       5,
                       0,
                       (__int64)&DEVPKEY_Device_HardwareIds,
                       8210,
                       (__int64)v60,
                       112 * v49 + 2,
                       0);
                if ( v7 >= 0 )
                {
                  v70 = (void *)ExAllocatePool2(256, 96 * v49 + 2, 1852403792);
                  v90 = v70;
                  v71 = (int)v70;
                  if ( !v70 )
                    goto LABEL_170;
                  ValueName.Buffer = (wchar_t *)v70;
                  ValueName.MaximumLength = 96 * v49 + 2;
                  v72 = (wchar_t *)v70;
                  if ( v49 )
                  {
                    do
                    {
                      ValueName.Length = 0;
                      if ( *((_BYTE *)qword_14002DFC0 + (unsigned __int16)v104[v69]) )
                      {
                        v7 = RtlUnicodeStringCopyStringEx(&ValueName, L"COMPUTER\\", &ValueName, 0);
                        if ( v7 < 0 )
                          goto LABEL_219;
                        v7 = RtlStringFromGUIDEx(&v107[v69], &ValueName, 0);
                        if ( v7 < 0 )
                          goto LABEL_219;
                        v7 = RtlUpcaseUnicodeString(&ValueName, &ValueName, 0);
                        if ( v7 < 0 )
                          goto LABEL_219;
                        v72 = ValueName.Buffer + 39;
                        ValueName.MaximumLength -= 78;
                        ValueName.Buffer += 39;
                      }
                      ++v69;
                    }
                    while ( v69 < v49 );
                    v71 = (int)v90;
                  }
                  *v72 = 0;
                  ++ValueName.Buffer;
                  v73 = (wchar_t *)ExAllocatePool2(256, 400, 1852403792);
                  v67 = v73;
                  if ( !v73 )
                    goto LABEL_170;
                  v94 = v73;
                  pcchRemaining = 200;
                  if ( v111.Length <= 2u )
                  {
                    RtlInitUnicodeString(&ValueName, L"Unknown");
                  }
                  else
                  {
                    ValueName.Buffer = v111.Buffer;
                    ValueName.MaximumLength = v111.MaximumLength;
                    if ( v111.Length <= 0x46u )
                      ValueName.Length = v111.Length;
                    else
                      ValueName.Length = 70;
                  }
                  v7 = RtlStringCchPrintfExW(
                         v67,
                         0xC8u,
                         (NTSTRSAFE_PWSTR *)&v94,
                         &pcchRemaining,
                         0x800u,
                         L"MFG_%wZ",
                         &ValueName);
                  if ( v7 < 0 )
                    goto LABEL_219;
                  if ( v112.Length > 2u )
                  {
                    ValueName.Buffer = v112.Buffer;
                    ValueName.MaximumLength = v112.MaximumLength;
                    ValueName.Length = 70;
                    if ( v112.Length <= 0x46u )
                      ValueName.Length = v112.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v94,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v94,
                           &pcchRemaining,
                           0x800u,
                           L"&FAM_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                  }
                  Length = v113.Length;
                  if ( v113.Length > 2u )
                  {
                    ValueName.Buffer = v113.Buffer;
                    ValueName.MaximumLength = v113.MaximumLength;
                    ValueName.Length = 70;
                    if ( v113.Length <= 0x46u )
                      ValueName.Length = v113.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v94,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v94,
                           &pcchRemaining,
                           0x800u,
                           L"&PROD_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                    Length = v113.Length;
                  }
                  if ( v114.Length > 2u )
                  {
                    ValueName.Buffer = v114.Buffer;
                    ValueName.MaximumLength = v114.MaximumLength;
                    ValueName.Length = 70;
                    if ( v114.Length <= 0x46u )
                      ValueName.Length = v114.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v94,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v94,
                           &pcchRemaining,
                           0x800u,
                           L"&SKU_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                    Length = v113.Length;
                  }
                  v75 = *v67;
                  v76 = v67;
                  if ( *v67 )
                  {
                    v77 = v67;
                    do
                    {
                      if ( (unsigned __int16)(v75 - 33) > 0x5Eu || v75 == 44 || v75 == 92 )
                        *v76 = 95;
                      v76 = v77 + 1;
                      v75 = v77[1];
                      ++v77;
                    }
                    while ( v75 );
                    Length = v113.Length;
                  }
                  v78 = (char *)ExAllocatePool2(256, v111.Length + 4LL + Length, 1852403792);
                  v68 = v78;
                  if ( v78 )
                  {
                    v79 = v78;
                    if ( v111.Length < 2u )
                    {
                      v80 = v78;
                    }
                    else
                    {
                      memmove(v78, v111.Buffer, v111.Length);
                      v79 = &v68[2 * ((unsigned __int64)v111.Length >> 1)];
                      v80 = v79;
                    }
                    v81 = v113.Length;
                    if ( v113.Length >= 2u )
                    {
                      if ( v80 != v68 )
                      {
                        *(_WORD *)v79 = 32;
                        v80 += 2;
                        v81 = v113.Length;
                      }
                      memmove(v80, v113.Buffer, v81);
                      v79 = &v80[2 * ((unsigned __int64)v113.Length >> 1)];
                      v80 = v79;
                    }
                    *(_WORD *)v79 = 0;
                    pid = DEVPKEY_Device_FriendlyName.pid;
                    fmtid = DEVPKEY_Device_FriendlyName.fmtid;
                    LODWORD(v110) = 18;
                    *((_QWORD *)&v110 + 1) = v68;
                    DWORD1(v110) = 2 * ((v80 - v68) >> 1) + 2;
                    v82 = PiSwStartCreate(
                            (unsigned int)L"COMPUTER",
                            *((_QWORD *)IopRootDeviceNode + 6),
                            (_DWORD)v67,
                            v71,
                            (__int64)L"COMPUTER\\Generic",
                            0,
                            0,
                            (__int64)v68,
                            0,
                            0,
                            0,
                            (__int64)&fmtid,
                            1);
                    if ( v82 < 0 && (byte_140EDA02C & 0x10) != 0 )
                      McTemplateK0d_EtwWriteTransfer(v83, KMPnPEvt_CreateOemDevice_Failure, v84, (unsigned int)v82);
                  }
                  else
                  {
LABEL_170:
                    v7 = -1073741670;
                  }
                }
              }
LABEL_219:
              ExFreePoolWithTag(P, 0);
              if ( v90 )
                ExFreePoolWithTag(v90, 0);
              if ( v67 )
                ExFreePoolWithTag(v67, 0);
              if ( v68 )
                ExFreePoolWithTag(v68, 0);
              goto LABEL_151;
            }
            v34 = (_BYTE *)(v30 + 5);
            if ( v30 + 5 <= v30 + (unsigned __int64)*(unsigned __int8 *)(v30 + 1) )
            {
              LOBYTE(v31) = *(_BYTE *)(v30 + 4);
              v35 = PipSmBiosGetString(v30, v31, v13, v10, &v115);
              LODWORD(v90) = v35;
              v7 = v35;
              if ( v35 == -1073741275 )
              {
                LODWORD(v90) = 0;
              }
              else if ( v35 < 0 )
              {
                goto LABEL_22;
              }
            }
            if ( v33 + 6 <= &v33[v33[1]] )
            {
              LOBYTE(v31) = *v34;
              v36 = PipSmBiosGetString((int)v33, v31, v13, v10, &v116);
              LODWORD(v90) = v36;
              v7 = v36;
              if ( v36 == -1073741275 )
              {
                LODWORD(v90) = 0;
              }
              else if ( v36 < 0 )
              {
                goto LABEL_22;
              }
            }
            if ( v33 + 9 > &v33[v33[1]] )
            {
LABEL_55:
              v32 = v33 + 21;
              v38 = (unsigned __int64)&v33[v33[1]];
              if ( (unsigned __int64)(v33 + 21) <= v38 )
                v92 = v33[20];
              if ( (unsigned __int64)(v33 + 22) <= v38 )
                v91 = *v32;
              goto LABEL_59;
            }
            LOBYTE(v31) = v33[8];
            v37 = PipSmBiosGetString((int)v33, v31, v13, v10, &v119);
            LODWORD(v90) = v37;
            v7 = v37;
            if ( v37 == -1073741275 )
            {
              LODWORD(v90) = 0;
              goto LABEL_55;
            }
            if ( v37 >= 0 )
              goto LABEL_55;
LABEL_22:
            v3 = v13;
            goto LABEL_152;
          }
        }
        v7 = -1073741637;
      }
    }
  }
LABEL_152:
  for ( m = 0; m != 10; ++m )
    RtlFreeAnsiString(&v111 + m);
  v64 = Handle;
  if ( v3 )
  {
    LOBYTE(v63) = 1;
    MiUnmapContiguousMemory(v3, (unsigned int)v93, v63);
  }
  if ( v64 )
    ZwClose(v64);
  if ( KeyHandle )
    PnpCtxRegCloseKey(v62, KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140ca4cbc  push    rbp
0x140ca4cbe  push    rbx
0x140ca4cbf  push    rsi
0x140ca4cc0  push    rdi
0x140ca4cc1  push    r12
0x140ca4cc3  push    r13
0x140ca4cc5  push    r14
0x140ca4cc7  push    r15
0x140ca4cc9  lea     rbp, [rsp-238h]
0x140ca4cd1  sub     rsp, 338h
0x140ca4cd8  mov     rax, cs:__security_cookie
0x140ca4cdf  xor     rax, rsp
0x140ca4ce2  mov     [rbp+270h+var_48], rax
0x140ca4ce9  xorps   xmm0, xmm0
0x140ca4cec  xor     r12d, r12d
0x140ca4cef  mov     rdi, rcx
0x140ca4cf2  mov     [rbp+270h+KeyHandle], r12
0x140ca4cf6  xorps   xmm1, xmm1
0x140ca4cf9  mov     [rbp+270h+Handle], r12
0x140ca4cfd  xor     eax, eax
0x140ca4cff  mov     [rbp+270h+P], r12
0x140ca4d03  mov     r14d, r12d
0x140ca4d06  mov     [rbp+270h+var_2C8], r12d
0x140ca4d0a  xor     edx, edx; Val
0x140ca4d0c  mov     [rbp+270h+var_2D8], r14
0x140ca4d10  mov     r8d, 0A0h; Size
0x140ca4d16  mov     [rbp+270h+var_288], rax
0x140ca4d1a  lea     rcx, [rbp+270h+var_100]; void *
0x140ca4d21  mov     [rbp+270h+var_2D0], r12
0x140ca4d25  mov     esi, r12d
0x140ca4d28  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm0
0x140ca4d2c  movups  xmmword ptr [rbp+270h+var_238.Length], xmm1
0x140ca4d30  movups  [rbp+270h+var_2B8], xmm0
0x140ca4d34  movups  [rbp+270h+var_2A8], xmm0
0x140ca4d38  movups  [rbp+270h+var_298], xmm0
0x140ca4d3c  movups  [rbp+270h+var_130], xmm0
0x140ca4d43  movups  [rbp+270h+var_120], xmm0
0x140ca4d4a  movups  [rbp+270h+var_110], xmm0
0x140ca4d51  movups  xmmword ptr [rsp+370h+ValueName.Length], xmm0
0x140ca4d56  call    memset_0
0x140ca4d5b  lea     r8, [rbp+270h+KeyHandle]
0x140ca4d5f  mov     edx, 0F003Fh
0x140ca4d64  call    PipHardwareConfigOpenKey
0x140ca4d69  mov     r15, [rbp+270h+KeyHandle]
0x140ca4d6d  mov     ebx, eax
0x140ca4d6f  test    eax, eax
0x140ca4d71  js      loc_140CA5B38
0x140ca4d77  mov     rcx, cs:PiPnpRtlCtx
0x140ca4d7e  lea     rbx, aComputerids_0; "ComputerIds"
0x140ca4d85  mov     r8, rbx
0x140ca4d88  mov     rdx, r15
0x140ca4d8b  call    _PnpCtxRegDeleteTree
0x140ca4d90  mov     r13d, 0F003Fh
0x140ca4d96  mov     qword ptr [rsp+370h+DataSize], r12
0x140ca4d9b  mov     r9d, r13d
0x140ca4d9e  mov     dword ptr [rsp+370h+ValueName.Length], 180016h
0x140ca4da6  lea     r8, [rsp+370h+ValueName]
0x140ca4dab  mov     [rsp+370h+ValueName.Buffer], rbx
0x140ca4db0  mov     rdx, r15
0x140ca4db3  mov     dword ptr [rsp+370h+Data], r12d
0x140ca4db8  lea     rcx, [rbp+270h+Handle]
0x140ca4dbc  call    IopCreateRegistryKeyEx
0x140ca4dc1  mov     ebx, eax
0x140ca4dc3  test    eax, eax
0x140ca4dc5  js      loc_140CA5B38
0x140ca4dcb  mov     rcx, cs:PiPnpRtlCtx
0x140ca4dd2  lea     rbx, aProductids; "ProductIds"
0x140ca4dd9  mov     r8, rbx
0x140ca4ddc  mov     rdx, r15
0x140ca4ddf  call    _PnpCtxRegDeleteTree
0x140ca4de4  mov     r9d, r13d
0x140ca4de7  mov     qword ptr [rsp+370h+DataSize], r12
0x140ca4dec  lea     r8, [rsp+370h+ValueName]
0x140ca4df1  mov     dword ptr [rsp+370h+ValueName.Length], 160014h
0x140ca4df9  mov     rdx, r15
0x140ca4dfc  mov     [rsp+370h+ValueName.Buffer], rbx
0x140ca4e01  lea     rcx, [rbp+270h+P]
0x140ca4e05  mov     dword ptr [rsp+370h+Data], r12d
0x140ca4e0a  call    IopCreateRegistryKeyEx
0x140ca4e0f  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4e12  mov     ebx, eax
0x140ca4e14  test    eax, eax
0x140ca4e16  js      loc_140CA5B38
0x140ca4e1c  mov     rax, [rdi+0F0h]
0x140ca4e23  mov     rdx, [rax+38h]
0x140ca4e27  test    rdx, rdx
0x140ca4e2a  jnz     short loc_140CA4E36
0x140ca4e2c  mov     ebx, 0C00000BBh
0x140ca4e31  jmp     loc_140CA5B38
0x140ca4e36  mov     rcx, [rdx+10h]
0x140ca4e3a  test    rcx, rcx
0x140ca4e3d  jz      short loc_140CA4E2C
0x140ca4e3f  mov     r13d, [rdx+0Ch]
0x140ca4e43  mov     r8d, 2
0x140ca4e49  mov     edx, r13d
0x140ca4e4c  mov     [rbp+270h+var_2D8], r13
0x140ca4e50  call    MmMapIoSpaceEx
0x140ca4e55  mov     [rbp+270h+var_2F0], rax
0x140ca4e59  mov     r15, rax
0x140ca4e5c  test    rax, rax
0x140ca4e5f  jnz     short loc_140CA4E6E
0x140ca4e61  mov     ebx, 0C000009Ah
0x140ca4e66  mov     rsi, rax
0x140ca4e69  jmp     loc_140CA5B38
0x140ca4e6e  mov     r9d, r13d
0x140ca4e71  mov     r8, r15
0x140ca4e74  xor     edx, edx
0x140ca4e76  mov     cl, 1
0x140ca4e78  call    PipSmBiosFindStruct
0x140ca4e7d  mov     rdi, rax
0x140ca4e80  mov     r12d, 0C0000225h
0x140ca4e86  test    rax, rax
0x140ca4e89  jz      loc_140CA5001
0x140ca4e8f  movzx   ecx, byte ptr [rax+1]
0x140ca4e93  lea     rsi, [rax+5]
0x140ca4e97  add     rcx, rax
0x140ca4e9a  cmp     rsi, rcx
0x140ca4e9d  ja      short loc_140CA4ED4
0x140ca4e9f  mov     dl, [rdi+4]; int
0x140ca4ea2  lea     rax, [rbp+270h+var_100]
0x140ca4ea9  mov     r9d, r13d; int
0x140ca4eac  mov     [rsp+370h+Data], rax; DestinationString
0x140ca4eb1  mov     r8, r15; int
0x140ca4eb4  mov     rcx, rdi; int
0x140ca4eb7  call    PipSmBiosGetString
0x140ca4ebc  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4ebf  mov     ebx, eax
0x140ca4ec1  cmp     eax, r12d
0x140ca4ec4  jnz     short loc_140CA4ECC
0x140ca4ec6  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca4eca  jmp     short loc_140CA4ED4
0x140ca4ecc  test    eax, eax
0x140ca4ece  js      loc_140CA4F5B
0x140ca4ed4  movzx   ecx, byte ptr [rdi+1]
0x140ca4ed8  lea     rax, [rdi+1Bh]
0x140ca4edc  add     rcx, rdi
0x140ca4edf  cmp     rax, rcx
0x140ca4ee2  ja      short loc_140CA4F15
0x140ca4ee4  mov     dl, [rdi+1Ah]; int
0x140ca4ee7  lea     rax, [rbp+270h+var_F0]
0x140ca4eee  mov     r9d, r13d; int
0x140ca4ef1  mov     [rsp+370h+Data], rax; DestinationString
0x140ca4ef6  mov     r8, r15; int
0x140ca4ef9  mov     rcx, rdi; int
0x140ca4efc  call    PipSmBiosGetString
0x140ca4f01  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4f04  mov     ebx, eax
0x140ca4f06  cmp     eax, r12d
0x140ca4f09  jnz     short loc_140CA4F11
0x140ca4f0b  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca4f0f  jmp     short loc_140CA4F15
0x140ca4f11  test    eax, eax
0x140ca4f13  js      short loc_140CA4F5B
0x140ca4f15  movzx   eax, byte ptr [rdi+1]
0x140ca4f19  lea     r14, [rdi+6]
0x140ca4f1d  add     rax, rdi
0x140ca4f20  cmp     r14, rax
0x140ca4f23  ja      short loc_140CA4F63
0x140ca4f25  mov     dl, [rsi]; int
0x140ca4f27  lea     rax, [rbp+270h+var_E0]
0x140ca4f2e  mov     r9d, r13d; int
0x140ca4f31  mov     [rsp+370h+Data], rax; DestinationString
0x140ca4f36  mov     r8, r15; int
0x140ca4f39  mov     rcx, rdi; int
0x140ca4f3c  call    PipSmBiosGetString
0x140ca4f41  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4f44  mov     ebx, eax
0x140ca4f46  cmp     eax, r12d
0x140ca4f49  jnz     short loc_140CA4F54
0x140ca4f4b  xor     r12d, r12d
0x140ca4f4e  mov     dword ptr [rbp+270h+var_2E8], r12d
0x140ca4f52  jmp     short loc_140CA4F66
0x140ca4f54  xor     r12d, r12d
0x140ca4f57  test    eax, eax
0x140ca4f59  jns     short loc_140CA4F66
0x140ca4f5b  mov     rsi, r15
0x140ca4f5e  jmp     loc_140CA5B38
0x140ca4f63  xor     r12d, r12d
0x140ca4f66  movzx   ecx, byte ptr [rdi+1]
0x140ca4f6a  lea     rax, [rdi+1Ah]
0x140ca4f6e  add     rcx, rdi
0x140ca4f71  cmp     rax, rcx
0x140ca4f74  ja      short loc_140CA4FA9
0x140ca4f76  mov     dl, [rdi+19h]; int
0x140ca4f79  lea     rax, [rbp+270h+var_D0]
0x140ca4f80  mov     r9d, r13d; int
0x140ca4f83  mov     [rsp+370h+Data], rax; DestinationString
0x140ca4f88  mov     r8, r15; int
0x140ca4f8b  mov     rcx, rdi; int
0x140ca4f8e  call    PipSmBiosGetString
0x140ca4f93  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4f96  mov     ebx, eax
0x140ca4f98  cmp     eax, 0C0000225h
0x140ca4f9d  jnz     short loc_140CA4FA5
0x140ca4f9f  mov     dword ptr [rbp+270h+var_2E8], r12d
0x140ca4fa3  jmp     short loc_140CA4FA9
0x140ca4fa5  test    eax, eax
0x140ca4fa7  js      short loc_140CA4F5B
0x140ca4fa9  movzx   ecx, byte ptr [rdi+1]
0x140ca4fad  lea     rax, [rdi+7]
0x140ca4fb1  add     rcx, rdi
0x140ca4fb4  cmp     rax, rcx
0x140ca4fb7  ja      short loc_140CA4FF8
0x140ca4fb9  mov     dl, [r14]; int
0x140ca4fbc  lea     rax, [rbp+270h+var_70]
0x140ca4fc3  mov     r9d, r13d; int
0x140ca4fc6  mov     [rsp+370h+Data], rax; DestinationString
0x140ca4fcb  mov     r8, r15; int
0x140ca4fce  mov     rcx, rdi; int
0x140ca4fd1  call    PipSmBiosGetString
0x140ca4fd6  mov     r12d, 0C0000225h
0x140ca4fdc  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca4fdf  xor     r14d, r14d
0x140ca4fe2  mov     ebx, eax
0x140ca4fe4  cmp     eax, r12d
0x140ca4fe7  jnz     short loc_140CA4FEF
0x140ca4fe9  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca4fed  jmp     short loc_140CA5001
0x140ca4fef  test    eax, eax
0x140ca4ff1  jns     short loc_140CA5001
0x140ca4ff3  jmp     loc_140CA4F5B
0x140ca4ff8  xor     r14d, r14d
0x140ca4ffb  mov     r12d, 0C0000225h
0x140ca5001  mov     r9d, r13d
0x140ca5004  mov     r8, r15
0x140ca5007  mov     edx, 0Ah
0x140ca500c  mov     cl, 2
0x140ca500e  call    PipSmBiosFindStruct
0x140ca5013  mov     rdi, rax
0x140ca5016  test    rax, rax
0x140ca5019  jz      loc_140CA50A8
0x140ca501f  movzx   ecx, byte ptr [rax+1]
0x140ca5023  lea     rsi, [rax+5]
0x140ca5027  add     rcx, rax
0x140ca502a  cmp     rsi, rcx
0x140ca502d  ja      short loc_140CA5064
0x140ca502f  mov     dl, [rdi+4]; int
0x140ca5032  lea     rax, [rbp+270h+var_A0]
0x140ca5039  mov     r9d, r13d; int
0x140ca503c  mov     [rsp+370h+Data], rax; DestinationString
0x140ca5041  mov     r8, r15; int
0x140ca5044  mov     rcx, rdi; int
0x140ca5047  call    PipSmBiosGetString
0x140ca504c  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca504f  mov     ebx, eax
0x140ca5051  cmp     eax, r12d
0x140ca5054  jnz     short loc_140CA505C
0x140ca5056  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca505a  jmp     short loc_140CA5064
0x140ca505c  test    eax, eax
0x140ca505e  js      loc_140CA4F5B
0x140ca5064  movzx   ecx, byte ptr [rdi+1]
0x140ca5068  lea     rax, [rdi+6]
0x140ca506c  add     rcx, rdi
0x140ca506f  cmp     rax, rcx
0x140ca5072  ja      short loc_140CA50A8
0x140ca5074  mov     dl, [rsi]; int
0x140ca5076  lea     rax, [rbp+270h+var_90]
0x140ca507d  mov     r9d, r13d; int
0x140ca5080  mov     [rsp+370h+Data], rax; DestinationString
0x140ca5085  mov     r8, r15; int
0x140ca5088  mov     rcx, rdi; int
0x140ca508b  call    PipSmBiosGetString
0x140ca5090  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca5093  mov     ebx, eax
0x140ca5095  cmp     eax, r12d
0x140ca5098  jnz     short loc_140CA50A0
0x140ca509a  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca509e  jmp     short loc_140CA50A8
0x140ca50a0  test    eax, eax
0x140ca50a2  js      loc_140CA4F5B
0x140ca50a8  mov     r9d, r13d
0x140ca50ab  mov     [rbp+270h+var_2DF], r14b
0x140ca50af  mov     r8, r15
0x140ca50b2  mov     [rbp+270h+var_2E0], r14b
0x140ca50b6  xor     edx, edx
0x140ca50b8  xor     ecx, ecx
0x140ca50ba  call    PipSmBiosFindStruct
0x140ca50bf  mov     rdi, rax
0x140ca50c2  test    rax, rax
0x140ca50c5  jz      loc_140CA51C5
0x140ca50cb  movzx   ecx, byte ptr [rax+1]
0x140ca50cf  lea     rsi, [rax+5]
0x140ca50d3  add     rcx, rax
0x140ca50d6  cmp     rsi, rcx
0x140ca50d9  ja      short loc_140CA5112
0x140ca50db  mov     dl, [rdi+4]; int
0x140ca50de  lea     rax, [rbp+270h+var_C0]
0x140ca50e5  mov     r9d, r13d; int
0x140ca50e8  mov     [rsp+370h+Data], rax; DestinationString
0x140ca50ed  mov     r8, r15; int
0x140ca50f0  mov     rcx, rdi; int
0x140ca50f3  call    PipSmBiosGetString
0x140ca50f8  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca50fb  mov     ebx, eax
0x140ca50fd  cmp     eax, 0C0000225h
0x140ca5102  jnz     short loc_140CA510A
0x140ca5104  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca5108  jmp     short loc_140CA5112
0x140ca510a  test    eax, eax
  ... truncated ...
```
