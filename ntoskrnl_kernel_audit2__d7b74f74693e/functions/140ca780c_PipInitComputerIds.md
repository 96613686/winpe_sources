# PipInitComputerIds

- ea: `0x140ca780c`
- end: `0x140ca8d4d`
- name: `PipInitComputerIds`
- size: `5441`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140ca7064`

## callees

- `0x1402c3d18`
- `0x1402e25f0`
- `0x140403380`
- `0x14041e400`
- `0x140471770`
- `0x140481fa0`
- `0x1405e2964`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406ddfe0`
- `0x1406defc0`
- `0x1406f6f80`
- `0x1406f7380`
- `0x140774ed0`
- `0x1408c43e0`
- `0x140908720`
- `0x140909110`
- `0x140923cd0`
- `0x14094b120`
- `0x1409e5ea0`
- `0x140a420e8`
- `0x140a82e94`
- `0x140a95b68`
- `0x140b024a8`
- `0x140bb1410`
- `0x140bb19f0`
- `0x140c68068`
- `0x140c69f94`
- `0x140c6a008`
- `0x140ca780c`

## string_xrefs

- `0x140ca8738`: `ComputerMetadata\`
- `0x140ca78ce`: `ComputerIds`
- `0x140ca8cbd`: `COMPUTER\Generic`
- `0x140ca8c4e`: `COMPUTER`
- `0x140ca8892`: `COMPUTER\`

## pseudocode

```c
__int64 __fastcall PipInitComputerIds(__int64 a1)
{
  unsigned int v2; // r14d
  __int64 v3; // rsi
  __int64 v4; // rcx
  int v5; // eax
  HANDLE v6; // r15
  NTSTATUS v7; // ebx
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
  UNICODE_STRING ValueName; // [rsp+70h] [rbp-90h] BYREF
  __int64 v87; // [rsp+80h] [rbp-80h]
  PVOID v88; // [rsp+88h] [rbp-78h]
  unsigned __int8 v89; // [rsp+90h] [rbp-70h]
  unsigned __int8 v90; // [rsp+91h] [rbp-6Fh]
  __int64 v91; // [rsp+98h] [rbp-68h]
  PVOID v92; // [rsp+A0h] [rbp-60h] BYREF
  int v93; // [rsp+A8h] [rbp-58h] BYREF
  size_t pcchRemaining; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v95; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v96; // [rsp+C8h] [rbp-38h]
  __int128 v97; // [rsp+D8h] [rbp-28h]
  UNICODE_STRING *p_DestinationString; // [rsp+E8h] [rbp-18h]
  HANDLE Handle; // [rsp+F0h] [rbp-10h] BYREF
  HANDLE KeyHandle; // [rsp+F8h] [rbp-8h] BYREF
  PVOID P; // [rsp+100h] [rbp+0h] BYREF
  _WORD v102[16]; // [rsp+108h] [rbp+8h]
  UNICODE_STRING DestinationString; // [rsp+128h] [rbp+28h] BYREF
  UNICODE_STRING v104; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v105[15]; // [rsp+150h] [rbp+50h] BYREF
  _GUID fmtid; // [rsp+240h] [rbp+140h] BYREF
  __int128 pid; // [rsp+250h] [rbp+150h]
  __int128 v108; // [rsp+260h] [rbp+160h]
  UNICODE_STRING v109; // [rsp+270h] [rbp+170h] BYREF
  UNICODE_STRING v110; // [rsp+280h] [rbp+180h] BYREF
  UNICODE_STRING v111; // [rsp+290h] [rbp+190h] BYREF
  UNICODE_STRING v112; // [rsp+2A0h] [rbp+1A0h] BYREF
  UNICODE_STRING v113; // [rsp+2B0h] [rbp+1B0h] BYREF
  UNICODE_STRING v114; // [rsp+2C0h] [rbp+1C0h] BYREF
  UNICODE_STRING v115; // [rsp+2D0h] [rbp+1D0h] BYREF
  UNICODE_STRING v116; // [rsp+2E0h] [rbp+1E0h] BYREF
  UNICODE_STRING v117; // [rsp+2F0h] [rbp+1F0h] BYREF
  UNICODE_STRING v118; // [rsp+300h] [rbp+200h] BYREF
  wchar_t SourceString; // [rsp+310h] [rbp+210h] BYREF
  wchar_t pszDest[8]; // [rsp+318h] [rbp+218h] BYREF

  KeyHandle = 0;
  Handle = 0;
  P = 0;
  v2 = 0;
  v93 = 0;
  v91 = 0;
  p_DestinationString = 0;
  v92 = 0;
  v3 = 0;
  DestinationString = 0;
  v104 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  fmtid = 0;
  pid = 0;
  v108 = 0;
  ValueName = 0;
  memset_0(&v109, 0, 0xA0u);
  v5 = PipHardwareConfigOpenKey(v4, 983103, &KeyHandle);
  v6 = KeyHandle;
  v7 = v5;
  if ( v5 >= 0 )
  {
    PnpCtxRegDeleteTree(*(_QWORD *)&PiPnpRtlCtx, KeyHandle, L"ComputerIds");
    *(_DWORD *)&ValueName.Length = 1572886;
    ValueName.Buffer = L"ComputerIds";
    v7 = IopCreateRegistryKeyEx(&Handle, v6, &ValueName, 983103, 0, 0);
    if ( v7 >= 0 )
    {
      PnpCtxRegDeleteTree(*(_QWORD *)&PiPnpRtlCtx, v6, L"ProductIds");
      *(_DWORD *)&ValueName.Length = 1441812;
      ValueName.Buffer = L"ProductIds";
      LODWORD(v88) = IopCreateRegistryKeyEx(&P, v6, &ValueName, 983103, 0, 0);
      v7 = (int)v88;
      if ( (int)v88 >= 0 )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(a1 + 240) + 56LL);
        if ( v8 )
        {
          v9 = *(_QWORD *)(v8 + 16);
          if ( v9 )
          {
            v10 = *(unsigned int *)(v8 + 12);
            v91 = v10;
            v11 = MmMapIoSpaceEx(v9, v10, 2);
            v87 = v11;
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
                String = PipSmBiosGetString(Struct, v15, v13, v10, &v109);
                LODWORD(v88) = String;
                v7 = String;
                if ( String == -1073741275 )
                {
                  LODWORD(v88) = 0;
                }
                else if ( String < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 27 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = v17[26];
                v20 = PipSmBiosGetString((int)v17, v15, v13, v10, &v110);
                LODWORD(v88) = v20;
                v7 = v20;
                if ( v20 == -1073741275 )
                {
                  LODWORD(v88) = 0;
                }
                else if ( v20 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 6 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = *v18;
                v21 = PipSmBiosGetString((int)v17, v15, v13, v10, &v111);
                LODWORD(v88) = v21;
                v7 = v21;
                if ( v21 == -1073741275 )
                {
                  LODWORD(v88) = 0;
                }
                else if ( v21 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v17 + 26 <= &v17[v17[1]] )
              {
                LOBYTE(v15) = v17[25];
                v22 = PipSmBiosGetString((int)v17, v15, v13, v10, &v112);
                LODWORD(v88) = v22;
                v7 = v22;
                if ( v22 == -1073741275 )
                {
                  LODWORD(v88) = 0;
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
                v23 = PipSmBiosGetString((int)v17, v15, v13, v10, &v118);
                LODWORD(v88) = v23;
                v2 = 0;
                v7 = v23;
                if ( v23 == -1073741275 )
                {
                  LODWORD(v88) = 0;
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
                v28 = PipSmBiosGetString(v24, v25, v13, v10, &v115);
                LODWORD(v88) = v28;
                v7 = v28;
                if ( v28 == -1073741275 )
                {
                  LODWORD(v88) = 0;
                }
                else if ( v28 < 0 )
                {
                  goto LABEL_22;
                }
              }
              if ( v26 + 6 <= v26 + (unsigned __int64)*(unsigned __int8 *)(v26 + 1) )
              {
                LOBYTE(v25) = *v27;
                v29 = PipSmBiosGetString(v26, v25, v13, v10, &v116);
                LODWORD(v88) = v29;
                v7 = v29;
                if ( v29 == -1073741275 )
                {
                  LODWORD(v88) = 0;
                }
                else if ( v29 < 0 )
                {
                  goto LABEL_22;
                }
              }
            }
            v90 = 0;
            v89 = 0;
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
                v93 = v40;
              }
              else
              {
                v40 = v93;
              }
              if ( v40 )
              {
                ValueName.Buffer = L"EnclosureType";
                *(_DWORD *)&ValueName.Length = 1835034;
                ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &v93, 4u);
              }
              for ( i = 0; i != 10; ++i )
              {
                v42 = 16 * i;
                if ( *((_QWORD *)&v109.Buffer + 2 * i) && !*(unsigned __int16 *)((char *)&v109.Length + v42) )
                  RtlFreeAnsiString((UNICODE_STRING *)((char *)&v109 + v42));
              }
              v43 = v89;
              for ( j = 0; j != 10; ++j )
              {
                RtlInitUnicodeString(&ValueName, off_14000B5C0[j]);
                if ( *(&v109.Length + 8 * j) )
                {
                  if ( (int)PnpUnicodeStringToWstr(&v92, 0, &v109 + j) >= 0 )
                  {
                    v45 = v92;
                    v46 = -1;
                    do
                      ++v46;
                    while ( *((_WORD *)v92 + v46) );
                    ZwSetValueKey(KeyHandle, &ValueName, 0, 1u, v92, 2 * v46 + 2);
                    PnpUnicodeStringToWstrFree(v45, &v109 + j);
                    v2 = 0;
                  }
                }
                else
                {
                  ZwDeleteValueKey(KeyHandle, &ValueName);
                }
              }
              Buffer = v109.Buffer;
              v48 = Handle;
              v7 = (int)v88;
              v49 = pcchRemaining;
              if ( v109.Buffer )
              {
                v50 = P;
                if ( v111.Buffer && v113.Buffer && v114.Buffer )
                {
                  LODWORD(Data) = v43;
                  v7 = RtlStringCchPrintfW(pszDest, 8u, L"%02x&%02x", v90, Data);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  RtlInitUnicodeString(&DestinationString, pszDest);
                  if ( v112.Buffer )
                  {
                    v51 = 0;
                    *(_QWORD *)&v95 = &v109;
                    *((_QWORD *)&v95 + 1) = &v110;
                    do
                    {
                      *((_QWORD *)&v96 + v51) = &v111 + v51;
                      ++v51;
                    }
                    while ( v51 != 4 );
                    v102[0] = 0;
                    p_DestinationString = &DestinationString;
                    v7 = PipCreateComputerId(v48, v50, &v95, 7, v105);
                    v49 = 1;
                    if ( v7 < 0 )
                      goto LABEL_151;
                  }
                  *(_QWORD *)&v95 = &v109;
                  *((_QWORD *)&v95 + 1) = &v110;
                  *(_QWORD *)&v96 = &v111;
                  *((_QWORD *)&v96 + 1) = &v113;
                  *(_QWORD *)&v97 = &v114;
                  *((_QWORD *)&v97 + 1) = &DestinationString;
                  v102[v49] = 1;
                  v7 = PipCreateComputerId(v48, v50, &v95, 6, &v105[v49]);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  *(_QWORD *)&v95 = &v109;
                  v52 = v49 + 1;
                  *((_QWORD *)&v95 + 1) = &v111;
                  *(_QWORD *)&v96 = &v113;
                  v102[v52] = 2;
                  *((_QWORD *)&v96 + 1) = &v114;
                  *(_QWORD *)&v97 = &DestinationString;
                  v7 = PipCreateComputerId(v48, v50, &v95, 5, &v105[(unsigned int)v52]);
                  if ( v7 < 0 )
                    goto LABEL_151;
                  Buffer = v109.Buffer;
                  v49 = v52 + 1;
                }
                if ( Buffer )
                {
                  if ( v111.Buffer )
                  {
                    if ( v112.Buffer )
                    {
                      if ( v115.Buffer && v116.Buffer )
                      {
                        v53 = 0;
                        *(_QWORD *)&v95 = &v109;
                        *((_QWORD *)&v95 + 1) = &v110;
                        do
                        {
                          *((_QWORD *)&v96 + v53) = &v111 + v53;
                          ++v53;
                        }
                        while ( v53 != 2 );
                        for ( k = 0; k != 2; ++k )
                          *((_QWORD *)&v97 + k) = &v115 + k;
                        v102[v49] = 3;
                        v7 = PipCreateComputerId(v48, v50, &v95, 6, &v105[v49]);
                        if ( v7 < 0 )
                          goto LABEL_151;
                        ++v49;
                      }
                      v55 = 0;
                      *(_QWORD *)&v95 = &v109;
                      *((_QWORD *)&v95 + 1) = &v110;
                      do
                      {
                        *((_QWORD *)&v96 + v55) = &v111 + v55;
                        ++v55;
                      }
                      while ( v55 != 2 );
                      v102[v49] = 4;
                      v7 = PipCreateComputerId(v48, v50, &v95, 4, &v105[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v95 = &v109;
                    *((_QWORD *)&v95 + 1) = &v110;
                    *(_QWORD *)&v96 = &v111;
                    v102[v49] = 5;
                    v7 = PipCreateComputerId(v48, v50, &v95, 3, &v105[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v109.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v112.Buffer )
                  {
                    if ( v115.Buffer && v116.Buffer )
                    {
                      v56 = 0;
                      *(_QWORD *)&v95 = &v109;
                      *((_QWORD *)&v95 + 1) = &v112;
                      do
                      {
                        *((_QWORD *)&v96 + v56) = &v115 + v56;
                        ++v56;
                      }
                      while ( v56 != 2 );
                      v102[v49] = 6;
                      v7 = PipCreateComputerId(v48, v50, &v95, 4, &v105[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v95 = &v109;
                    *((_QWORD *)&v95 + 1) = &v112;
                    v102[v49] = 7;
                    v7 = PipCreateComputerId(v48, v50, &v95, 2, &v105[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v109.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v111.Buffer )
                  {
                    if ( v115.Buffer && v116.Buffer )
                    {
                      *(_QWORD *)&v95 = &v109;
                      *((_QWORD *)&v95 + 1) = &v111;
                      *(_QWORD *)&v96 = &v115;
                      *((_QWORD *)&v96 + 1) = &v116;
                      v102[v49] = 8;
                      v7 = PipCreateComputerId(v48, v50, &v95, 4, &v105[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v95 = &v109;
                    *((_QWORD *)&v95 + 1) = &v111;
                    v102[v49] = 9;
                    v7 = PipCreateComputerId(v48, v50, &v95, 2, &v105[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v109.Buffer;
                    ++v49;
                  }
                  if ( !Buffer )
                    goto LABEL_149;
                  if ( v110.Buffer )
                  {
                    if ( v116.Buffer && v115.Buffer )
                    {
                      v57 = 0;
                      *(_QWORD *)&v95 = &v109;
                      *((_QWORD *)&v95 + 1) = &v110;
                      do
                      {
                        *((_QWORD *)&v96 + v57) = &v115 + v57;
                        ++v57;
                      }
                      while ( v57 != 2 );
                      v102[v49] = 10;
                      v7 = PipCreateComputerId(v48, v50, &v95, 4, &v105[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      ++v49;
                    }
                    *(_QWORD *)&v95 = &v109;
                    *((_QWORD *)&v95 + 1) = &v110;
                    v102[v49] = 11;
                    v7 = PipCreateComputerId(v48, v50, &v95, 2, &v105[v49]);
                    if ( v7 < 0 )
                      goto LABEL_151;
                    Buffer = v109.Buffer;
                    ++v49;
                  }
                  if ( Buffer )
                  {
                    if ( v93 )
                    {
                      v7 = RtlStringCchPrintfW(&SourceString, 4u, L"%x");
                      if ( v7 < 0 )
                        goto LABEL_151;
                      RtlInitUnicodeString(&v104, &SourceString);
                      *(_QWORD *)&v95 = &v109;
                      *((_QWORD *)&v95 + 1) = &v104;
                      v102[v49] = 12;
                      v7 = PipCreateComputerId(v48, 0, &v95, 2, &v105[v49]);
                      if ( v7 < 0 )
                        goto LABEL_151;
                      Buffer = v109.Buffer;
                      ++v49;
                    }
                    if ( Buffer )
                    {
                      if ( v116.Buffer && v115.Buffer )
                      {
                        v58 = 0;
                        *(_QWORD *)&v95 = &v109;
                        do
                        {
                          *((_QWORD *)&v95 + v58 + 1) = &v115 + v58;
                          ++v58;
                        }
                        while ( v58 != 2 );
                        v102[v49] = 13;
                        v7 = PipCreateComputerId(v48, 0, &v95, 3, &v105[v49]);
                        if ( v7 < 0 )
                          goto LABEL_151;
                        ++v49;
                      }
                      *(_QWORD *)&v95 = &v109;
                      v102[v49] = 14;
                      v7 = PipCreateComputerId(v48, 0, &v95, 1, &v105[v49]);
                      if ( v7 >= 0 )
                      {
                        ++v49;
                        goto LABEL_149;
                      }
LABEL_151:
                      v3 = v87;
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
              v88 = 0;
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
                  v7 = RtlStringFromGUIDEx(&v105[v2], &ValueName, 0);
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
                  v88 = v70;
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
                      if ( *((_BYTE *)qword_14002DF50 + (unsigned __int16)v102[v69]) )
                      {
                        v7 = RtlUnicodeStringCopyStringEx(&ValueName, L"COMPUTER\\", &ValueName, 0);
                        if ( v7 < 0 )
                          goto LABEL_219;
                        v7 = RtlStringFromGUIDEx(&v105[v69], &ValueName, 0);
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
                    v71 = (int)v88;
                  }
                  *v72 = 0;
                  ++ValueName.Buffer;
                  v73 = (wchar_t *)ExAllocatePool2(256, 400, 1852403792);
                  v67 = v73;
                  if ( !v73 )
                    goto LABEL_170;
                  v92 = v73;
                  pcchRemaining = 200;
                  if ( v109.Length <= 2u )
                  {
                    RtlInitUnicodeString(&ValueName, L"Unknown");
                  }
                  else
                  {
                    ValueName.Buffer = v109.Buffer;
                    ValueName.MaximumLength = v109.MaximumLength;
                    if ( v109.Length <= 0x46u )
                      ValueName.Length = v109.Length;
                    else
                      ValueName.Length = 70;
                  }
                  v7 = RtlStringCchPrintfExW(
                         v67,
                         0xC8u,
                         (NTSTRSAFE_PWSTR *)&v92,
                         &pcchRemaining,
                         0x800u,
                         L"MFG_%wZ",
                         &ValueName);
                  if ( v7 < 0 )
                    goto LABEL_219;
                  if ( v110.Length > 2u )
                  {
                    ValueName.Buffer = v110.Buffer;
                    ValueName.MaximumLength = v110.MaximumLength;
                    ValueName.Length = 70;
                    if ( v110.Length <= 0x46u )
                      ValueName.Length = v110.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v92,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v92,
                           &pcchRemaining,
                           0x800u,
                           L"&FAM_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                  }
                  Length = v111.Length;
                  if ( v111.Length > 2u )
                  {
                    ValueName.Buffer = v111.Buffer;
                    ValueName.MaximumLength = v111.MaximumLength;
                    ValueName.Length = 70;
                    if ( v111.Length <= 0x46u )
                      ValueName.Length = v111.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v92,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v92,
                           &pcchRemaining,
                           0x800u,
                           L"&PROD_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                    Length = v111.Length;
                  }
                  if ( v112.Length > 2u )
                  {
                    ValueName.Buffer = v112.Buffer;
                    ValueName.MaximumLength = v112.MaximumLength;
                    ValueName.Length = 70;
                    if ( v112.Length <= 0x46u )
                      ValueName.Length = v112.Length;
                    v7 = RtlStringCchPrintfExW(
                           (NTSTRSAFE_PWSTR)v92,
                           pcchRemaining,
                           (NTSTRSAFE_PWSTR *)&v92,
                           &pcchRemaining,
                           0x800u,
                           L"&SKU_%wZ",
                           &ValueName);
                    if ( v7 < 0 )
                      goto LABEL_219;
                    Length = v111.Length;
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
                    Length = v111.Length;
                  }
                  v78 = (char *)ExAllocatePool2(256, v109.Length + 4LL + Length, 1852403792);
                  v68 = v78;
                  if ( v78 )
                  {
                    v79 = v78;
                    if ( v109.Length < 2u )
                    {
                      v80 = v78;
                    }
                    else
                    {
                      memmove(v78, v109.Buffer, v109.Length);
                      v79 = &v68[2 * ((unsigned __int64)v109.Length >> 1)];
                      v80 = v79;
                    }
                    v81 = v111.Length;
                    if ( v111.Length >= 2u )
                    {
                      if ( v80 != v68 )
                      {
                        *(_WORD *)v79 = 32;
                        v80 += 2;
                        v81 = v111.Length;
                      }
                      memmove(v80, v111.Buffer, v81);
                      v79 = &v80[2 * ((unsigned __int64)v111.Length >> 1)];
                      v80 = v79;
                    }
                    *(_WORD *)v79 = 0;
                    pid = DEVPKEY_Device_FriendlyName.pid;
                    fmtid = DEVPKEY_Device_FriendlyName.fmtid;
                    LODWORD(v108) = 18;
                    *((_QWORD *)&v108 + 1) = v68;
                    DWORD1(v108) = 2 * ((v80 - v68) >> 1) + 2;
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
                    if ( v82 < 0 && (byte_140ED9FEC & 0x10) != 0 )
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
              if ( v88 )
                ExFreePoolWithTag(v88, 0);
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
              v35 = PipSmBiosGetString(v30, v31, v13, v10, &v113);
              LODWORD(v88) = v35;
              v7 = v35;
              if ( v35 == -1073741275 )
              {
                LODWORD(v88) = 0;
              }
              else if ( v35 < 0 )
              {
                goto LABEL_22;
              }
            }
            if ( v33 + 6 <= &v33[v33[1]] )
            {
              LOBYTE(v31) = *v34;
              v36 = PipSmBiosGetString((int)v33, v31, v13, v10, &v114);
              LODWORD(v88) = v36;
              v7 = v36;
              if ( v36 == -1073741275 )
              {
                LODWORD(v88) = 0;
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
                v90 = v33[20];
              if ( (unsigned __int64)(v33 + 22) <= v38 )
                v89 = *v32;
              goto LABEL_59;
            }
            LOBYTE(v31) = v33[8];
            v37 = PipSmBiosGetString((int)v33, v31, v13, v10, &v117);
            LODWORD(v88) = v37;
            v7 = v37;
            if ( v37 == -1073741275 )
            {
              LODWORD(v88) = 0;
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
    RtlFreeAnsiString(&v109 + m);
  v64 = Handle;
  if ( v3 )
  {
    LOBYTE(v63) = 1;
    MiUnmapContiguousMemory(v3, (unsigned int)v91, v63);
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
0x140ca780c  push    rbp
0x140ca780e  push    rbx
0x140ca780f  push    rsi
0x140ca7810  push    rdi
0x140ca7811  push    r12
0x140ca7813  push    r13
0x140ca7815  push    r14
0x140ca7817  push    r15
0x140ca7819  lea     rbp, [rsp-238h]
0x140ca7821  sub     rsp, 338h
0x140ca7828  mov     rax, cs:__security_cookie
0x140ca782f  xor     rax, rsp
0x140ca7832  mov     [rbp+270h+var_48], rax
0x140ca7839  xorps   xmm0, xmm0
0x140ca783c  xor     r12d, r12d
0x140ca783f  mov     rdi, rcx
0x140ca7842  mov     [rbp+270h+KeyHandle], r12
0x140ca7846  xorps   xmm1, xmm1
0x140ca7849  mov     [rbp+270h+Handle], r12
0x140ca784d  xor     eax, eax
0x140ca784f  mov     [rbp+270h+P], r12
0x140ca7853  mov     r14d, r12d
0x140ca7856  mov     [rbp+270h+var_2C8], r12d
0x140ca785a  xor     edx, edx; Val
0x140ca785c  mov     [rbp+270h+var_2D8], r14
0x140ca7860  mov     r8d, 0A0h; Size
0x140ca7866  mov     [rbp+270h+var_288], rax
0x140ca786a  lea     rcx, [rbp+270h+var_100]; void *
0x140ca7871  mov     [rbp+270h+var_2D0], r12
0x140ca7875  mov     esi, r12d
0x140ca7878  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm0
0x140ca787c  movups  xmmword ptr [rbp+270h+var_238.Length], xmm1
0x140ca7880  movups  [rbp+270h+var_2B8], xmm0
0x140ca7884  movups  [rbp+270h+var_2A8], xmm0
0x140ca7888  movups  [rbp+270h+var_298], xmm0
0x140ca788c  movups  [rbp+270h+var_130], xmm0
0x140ca7893  movups  [rbp+270h+var_120], xmm0
0x140ca789a  movups  [rbp+270h+var_110], xmm0
0x140ca78a1  movups  xmmword ptr [rsp+370h+ValueName.Length], xmm0
0x140ca78a6  call    memset_0
0x140ca78ab  lea     r8, [rbp+270h+KeyHandle]
0x140ca78af  mov     edx, 0F003Fh
0x140ca78b4  call    PipHardwareConfigOpenKey
0x140ca78b9  mov     r15, [rbp+270h+KeyHandle]
0x140ca78bd  mov     ebx, eax
0x140ca78bf  test    eax, eax
0x140ca78c1  js      loc_140CA8688
0x140ca78c7  mov     rcx, cs:PiPnpRtlCtx
0x140ca78ce  lea     rbx, aComputerids_0; "ComputerIds"
0x140ca78d5  mov     r8, rbx
0x140ca78d8  mov     rdx, r15
0x140ca78db  call    _PnpCtxRegDeleteTree
0x140ca78e0  mov     r13d, 0F003Fh
0x140ca78e6  mov     qword ptr [rsp+370h+DataSize], r12
0x140ca78eb  mov     r9d, r13d
0x140ca78ee  mov     dword ptr [rsp+370h+ValueName.Length], 180016h
0x140ca78f6  lea     r8, [rsp+370h+ValueName]
0x140ca78fb  mov     [rsp+370h+ValueName.Buffer], rbx
0x140ca7900  mov     rdx, r15
0x140ca7903  mov     dword ptr [rsp+370h+Data], r12d
0x140ca7908  lea     rcx, [rbp+270h+Handle]
0x140ca790c  call    IopCreateRegistryKeyEx
0x140ca7911  mov     ebx, eax
0x140ca7913  test    eax, eax
0x140ca7915  js      loc_140CA8688
0x140ca791b  mov     rcx, cs:PiPnpRtlCtx
0x140ca7922  lea     rbx, aProductids; "ProductIds"
0x140ca7929  mov     r8, rbx
0x140ca792c  mov     rdx, r15
0x140ca792f  call    _PnpCtxRegDeleteTree
0x140ca7934  mov     r9d, r13d
0x140ca7937  mov     qword ptr [rsp+370h+DataSize], r12
0x140ca793c  lea     r8, [rsp+370h+ValueName]
0x140ca7941  mov     dword ptr [rsp+370h+ValueName.Length], 160014h
0x140ca7949  mov     rdx, r15
0x140ca794c  mov     [rsp+370h+ValueName.Buffer], rbx
0x140ca7951  lea     rcx, [rbp+270h+P]
0x140ca7955  mov     dword ptr [rsp+370h+Data], r12d
0x140ca795a  call    IopCreateRegistryKeyEx
0x140ca795f  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7962  mov     ebx, eax
0x140ca7964  test    eax, eax
0x140ca7966  js      loc_140CA8688
0x140ca796c  mov     rax, [rdi+0F0h]
0x140ca7973  mov     rdx, [rax+38h]
0x140ca7977  test    rdx, rdx
0x140ca797a  jnz     short loc_140CA7986
0x140ca797c  mov     ebx, 0C00000BBh
0x140ca7981  jmp     loc_140CA8688
0x140ca7986  mov     rcx, [rdx+10h]
0x140ca798a  test    rcx, rcx
0x140ca798d  jz      short loc_140CA797C
0x140ca798f  mov     r13d, [rdx+0Ch]
0x140ca7993  mov     r8d, 2
0x140ca7999  mov     edx, r13d
0x140ca799c  mov     [rbp+270h+var_2D8], r13
0x140ca79a0  call    MmMapIoSpaceEx
0x140ca79a5  mov     [rbp+270h+var_2F0], rax
0x140ca79a9  mov     r15, rax
0x140ca79ac  test    rax, rax
0x140ca79af  jnz     short loc_140CA79BE
0x140ca79b1  mov     ebx, 0C000009Ah
0x140ca79b6  mov     rsi, rax
0x140ca79b9  jmp     loc_140CA8688
0x140ca79be  mov     r9d, r13d
0x140ca79c1  mov     r8, r15
0x140ca79c4  xor     edx, edx
0x140ca79c6  mov     cl, 1
0x140ca79c8  call    PipSmBiosFindStruct
0x140ca79cd  mov     rdi, rax
0x140ca79d0  mov     r12d, 0C0000225h
0x140ca79d6  test    rax, rax
0x140ca79d9  jz      loc_140CA7B51
0x140ca79df  movzx   ecx, byte ptr [rax+1]
0x140ca79e3  lea     rsi, [rax+5]
0x140ca79e7  add     rcx, rax
0x140ca79ea  cmp     rsi, rcx
0x140ca79ed  ja      short loc_140CA7A24
0x140ca79ef  mov     dl, [rdi+4]; int
0x140ca79f2  lea     rax, [rbp+270h+var_100]
0x140ca79f9  mov     r9d, r13d; int
0x140ca79fc  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7a01  mov     r8, r15; int
0x140ca7a04  mov     rcx, rdi; int
0x140ca7a07  call    PipSmBiosGetString
0x140ca7a0c  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7a0f  mov     ebx, eax
0x140ca7a11  cmp     eax, r12d
0x140ca7a14  jnz     short loc_140CA7A1C
0x140ca7a16  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7a1a  jmp     short loc_140CA7A24
0x140ca7a1c  test    eax, eax
0x140ca7a1e  js      loc_140CA7AAB
0x140ca7a24  movzx   ecx, byte ptr [rdi+1]
0x140ca7a28  lea     rax, [rdi+1Bh]
0x140ca7a2c  add     rcx, rdi
0x140ca7a2f  cmp     rax, rcx
0x140ca7a32  ja      short loc_140CA7A65
0x140ca7a34  mov     dl, [rdi+1Ah]; int
0x140ca7a37  lea     rax, [rbp+270h+var_F0]
0x140ca7a3e  mov     r9d, r13d; int
0x140ca7a41  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7a46  mov     r8, r15; int
0x140ca7a49  mov     rcx, rdi; int
0x140ca7a4c  call    PipSmBiosGetString
0x140ca7a51  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7a54  mov     ebx, eax
0x140ca7a56  cmp     eax, r12d
0x140ca7a59  jnz     short loc_140CA7A61
0x140ca7a5b  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7a5f  jmp     short loc_140CA7A65
0x140ca7a61  test    eax, eax
0x140ca7a63  js      short loc_140CA7AAB
0x140ca7a65  movzx   eax, byte ptr [rdi+1]
0x140ca7a69  lea     r14, [rdi+6]
0x140ca7a6d  add     rax, rdi
0x140ca7a70  cmp     r14, rax
0x140ca7a73  ja      short loc_140CA7AB3
0x140ca7a75  mov     dl, [rsi]; int
0x140ca7a77  lea     rax, [rbp+270h+var_E0]
0x140ca7a7e  mov     r9d, r13d; int
0x140ca7a81  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7a86  mov     r8, r15; int
0x140ca7a89  mov     rcx, rdi; int
0x140ca7a8c  call    PipSmBiosGetString
0x140ca7a91  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7a94  mov     ebx, eax
0x140ca7a96  cmp     eax, r12d
0x140ca7a99  jnz     short loc_140CA7AA4
0x140ca7a9b  xor     r12d, r12d
0x140ca7a9e  mov     dword ptr [rbp+270h+var_2E8], r12d
0x140ca7aa2  jmp     short loc_140CA7AB6
0x140ca7aa4  xor     r12d, r12d
0x140ca7aa7  test    eax, eax
0x140ca7aa9  jns     short loc_140CA7AB6
0x140ca7aab  mov     rsi, r15
0x140ca7aae  jmp     loc_140CA8688
0x140ca7ab3  xor     r12d, r12d
0x140ca7ab6  movzx   ecx, byte ptr [rdi+1]
0x140ca7aba  lea     rax, [rdi+1Ah]
0x140ca7abe  add     rcx, rdi
0x140ca7ac1  cmp     rax, rcx
0x140ca7ac4  ja      short loc_140CA7AF9
0x140ca7ac6  mov     dl, [rdi+19h]; int
0x140ca7ac9  lea     rax, [rbp+270h+var_D0]
0x140ca7ad0  mov     r9d, r13d; int
0x140ca7ad3  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7ad8  mov     r8, r15; int
0x140ca7adb  mov     rcx, rdi; int
0x140ca7ade  call    PipSmBiosGetString
0x140ca7ae3  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7ae6  mov     ebx, eax
0x140ca7ae8  cmp     eax, 0C0000225h
0x140ca7aed  jnz     short loc_140CA7AF5
0x140ca7aef  mov     dword ptr [rbp+270h+var_2E8], r12d
0x140ca7af3  jmp     short loc_140CA7AF9
0x140ca7af5  test    eax, eax
0x140ca7af7  js      short loc_140CA7AAB
0x140ca7af9  movzx   ecx, byte ptr [rdi+1]
0x140ca7afd  lea     rax, [rdi+7]
0x140ca7b01  add     rcx, rdi
0x140ca7b04  cmp     rax, rcx
0x140ca7b07  ja      short loc_140CA7B48
0x140ca7b09  mov     dl, [r14]; int
0x140ca7b0c  lea     rax, [rbp+270h+var_70]
0x140ca7b13  mov     r9d, r13d; int
0x140ca7b16  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7b1b  mov     r8, r15; int
0x140ca7b1e  mov     rcx, rdi; int
0x140ca7b21  call    PipSmBiosGetString
0x140ca7b26  mov     r12d, 0C0000225h
0x140ca7b2c  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7b2f  xor     r14d, r14d
0x140ca7b32  mov     ebx, eax
0x140ca7b34  cmp     eax, r12d
0x140ca7b37  jnz     short loc_140CA7B3F
0x140ca7b39  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7b3d  jmp     short loc_140CA7B51
0x140ca7b3f  test    eax, eax
0x140ca7b41  jns     short loc_140CA7B51
0x140ca7b43  jmp     loc_140CA7AAB
0x140ca7b48  xor     r14d, r14d
0x140ca7b4b  mov     r12d, 0C0000225h
0x140ca7b51  mov     r9d, r13d
0x140ca7b54  mov     r8, r15
0x140ca7b57  mov     edx, 0Ah
0x140ca7b5c  mov     cl, 2
0x140ca7b5e  call    PipSmBiosFindStruct
0x140ca7b63  mov     rdi, rax
0x140ca7b66  test    rax, rax
0x140ca7b69  jz      loc_140CA7BF8
0x140ca7b6f  movzx   ecx, byte ptr [rax+1]
0x140ca7b73  lea     rsi, [rax+5]
0x140ca7b77  add     rcx, rax
0x140ca7b7a  cmp     rsi, rcx
0x140ca7b7d  ja      short loc_140CA7BB4
0x140ca7b7f  mov     dl, [rdi+4]; int
0x140ca7b82  lea     rax, [rbp+270h+var_A0]
0x140ca7b89  mov     r9d, r13d; int
0x140ca7b8c  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7b91  mov     r8, r15; int
0x140ca7b94  mov     rcx, rdi; int
0x140ca7b97  call    PipSmBiosGetString
0x140ca7b9c  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7b9f  mov     ebx, eax
0x140ca7ba1  cmp     eax, r12d
0x140ca7ba4  jnz     short loc_140CA7BAC
0x140ca7ba6  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7baa  jmp     short loc_140CA7BB4
0x140ca7bac  test    eax, eax
0x140ca7bae  js      loc_140CA7AAB
0x140ca7bb4  movzx   ecx, byte ptr [rdi+1]
0x140ca7bb8  lea     rax, [rdi+6]
0x140ca7bbc  add     rcx, rdi
0x140ca7bbf  cmp     rax, rcx
0x140ca7bc2  ja      short loc_140CA7BF8
0x140ca7bc4  mov     dl, [rsi]; int
0x140ca7bc6  lea     rax, [rbp+270h+var_90]
0x140ca7bcd  mov     r9d, r13d; int
0x140ca7bd0  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7bd5  mov     r8, r15; int
0x140ca7bd8  mov     rcx, rdi; int
0x140ca7bdb  call    PipSmBiosGetString
0x140ca7be0  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7be3  mov     ebx, eax
0x140ca7be5  cmp     eax, r12d
0x140ca7be8  jnz     short loc_140CA7BF0
0x140ca7bea  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7bee  jmp     short loc_140CA7BF8
0x140ca7bf0  test    eax, eax
0x140ca7bf2  js      loc_140CA7AAB
0x140ca7bf8  mov     r9d, r13d
0x140ca7bfb  mov     [rbp+270h+var_2DF], r14b
0x140ca7bff  mov     r8, r15
0x140ca7c02  mov     [rbp+270h+var_2E0], r14b
0x140ca7c06  xor     edx, edx
0x140ca7c08  xor     ecx, ecx
0x140ca7c0a  call    PipSmBiosFindStruct
0x140ca7c0f  mov     rdi, rax
0x140ca7c12  test    rax, rax
0x140ca7c15  jz      loc_140CA7D15
0x140ca7c1b  movzx   ecx, byte ptr [rax+1]
0x140ca7c1f  lea     rsi, [rax+5]
0x140ca7c23  add     rcx, rax
0x140ca7c26  cmp     rsi, rcx
0x140ca7c29  ja      short loc_140CA7C62
0x140ca7c2b  mov     dl, [rdi+4]; int
0x140ca7c2e  lea     rax, [rbp+270h+var_C0]
0x140ca7c35  mov     r9d, r13d; int
0x140ca7c38  mov     [rsp+370h+Data], rax; DestinationString
0x140ca7c3d  mov     r8, r15; int
0x140ca7c40  mov     rcx, rdi; int
0x140ca7c43  call    PipSmBiosGetString
0x140ca7c48  mov     dword ptr [rbp+270h+var_2E8], eax
0x140ca7c4b  mov     ebx, eax
0x140ca7c4d  cmp     eax, 0C0000225h
0x140ca7c52  jnz     short loc_140CA7C5A
0x140ca7c54  mov     dword ptr [rbp+270h+var_2E8], r14d
0x140ca7c58  jmp     short loc_140CA7C62
0x140ca7c5a  test    eax, eax
  ... truncated ...
```
