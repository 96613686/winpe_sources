# EtwpAddLogHeaderToLogFile

- ea: `0x180034bd0`
- end: `0x180035977`
- name: `EtwpAddLogHeaderToLogFile`
- size: `3495`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18005cd7c`
- `0x18005de30`
- `0x18015987c`

## callees

- `0x1800165d0`
- `0x18001861c`
- `0x18001b984`
- `0x18001c520`
- `0x18001d490`
- `0x180034bd0`
- `0x180035b00`
- `0x180035b34`
- `0x180035bc0`
- `0x180035d20`
- `0x180035ea4`
- `0x180035fd0`
- `0x180035ffc`
- `0x180036190`
- `0x1800362dc`
- `0x180036494`
- `0x18012d210`
- `0x18012d320`
- `0x18012d780`
- `0x18012d890`
- `0x18015eba0`
- `0x18015ebe0`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x18015ef80`
- `0x18015efc0`
- `0x18015f1a0`
- `0x18015f400`
- `0x18015f580`
- `0x180162810`
- `0x180164280`
- `0x180164550`
- `0x18016f030`

## string_xrefs

- `0x180035362`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x180035838`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
NTSTATUS __fastcall EtwpAddLogHeaderToLogFile(__int64 a1, void *a2, unsigned int a3, bool a4)
{
  size_t v4; // r13
  wchar_t *v8; // rdi
  const wchar_t *v9; // rsi
  __int64 v10; // r14
  int v11; // edx
  __int64 Heap_0; // rdi
  int v13; // eax
  void *v14; // r15
  size_t v15; // rax
  int v16; // ecx
  size_t v17; // rax
  int v18; // esi
  _DWORD *v19; // r9
  char *v20; // rsi
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  char *v24; // r8
  int v25; // eax
  char v26; // al
  char v27; // r10
  __int64 v28; // rax
  unsigned int v29; // ecx
  _QWORD *v30; // rsi
  __int64 v31; // rcx
  NTSTATUS result; // eax
  struct _PEB *v33; // rcx
  char v34; // al
  char v35; // dl
  __int64 v36; // rcx
  __int64 v37; // r13
  size_t v38; // rax
  int v39; // eax
  bool v40; // zf
  unsigned __int64 v41; // rax
  __int64 v42; // r13
  int v43; // r14d
  int v44; // eax
  __int64 v45; // rax
  __int64 v46; // rcx
  int v47; // edx
  int v48; // eax
  int v49; // eax
  size_t v50; // rax
  int RegString; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  int RegDwordValue; // eax
  _OWORD *v55; // r13
  int v56; // [rsp+60h] [rbp-A0h]
  int v57; // [rsp+60h] [rbp-A0h]
  unsigned int v58; // [rsp+68h] [rbp-98h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v63; // [rsp+90h] [rbp-70h]
  void *Src[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v65; // [rsp+A8h] [rbp-58h] BYREF
  void *v66; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v68[2]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v69[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v70; // [rsp+E8h] [rbp-18h]
  __int128 v71; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v72[48]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v73[3]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v74[48]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v75; // [rsp+190h] [rbp+90h] BYREF
  __int128 v76; // [rsp+1A0h] [rbp+A0h]
  __int128 v77; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v78; // [rsp+1C0h] [rbp+C0h]
  _OWORD SystemInformation[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _OWORD v80[2]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v81; // [rsp+230h] [rbp+130h]
  _BYTE v82[80]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v83[80]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t pszDest[1024]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v4 = a3;
  Src[0] = a2;
  v40 = (*(_BYTE *)(a1 + 308) & 8) == 0;
  v58 = 0;
  LODWORD(v59) = 0;
  v77 = 0;
  v78 = 0;
  v67 = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  memset(v80, 0, sizeof(v80));
  v81 = 0;
  memset(v73, 0, 44);
  v75 = 0;
  v76 = 0;
  if ( !v40 )
  {
    v8 = wcschr(*(const wchar_t **)(a1 + 176), 0x25u);
    if ( v8 && v8 == wcsrchr(*(const wchar_t **)(a1 + 176), 0x25u) && wcsstr(*(const wchar_t **)(a1 + 176), L"%d") )
    {
      if ( StringCbPrintfW(
             pszDest,
             0x800u,
             *(STRSAFE_LPCWSTR *)(a1 + 176),
             (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 184)))
        || !memcmp(*(const void **)(a1 + 176), pszDest, *(unsigned __int16 *)(a1 + 168)) )
      {
        RtlNtStatusToDosError(-1073741776);
      }
      else
      {
        RtlFreeAnsiString((PUNICODE_STRING)(a1 + 152));
        RtlCreateUnicodeString(a1 + 152, pszDest);
      }
    }
    else
    {
      RtlNtStatusToDosError(-1073741773);
    }
  }
  v9 = *(const wchar_t **)(a1 + 160);
  v10 = *(unsigned int *)(a1 + 192);
  if ( a2 )
  {
    v56 = v4;
    v11 = v4 + 79;
    goto LABEL_10;
  }
  result = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  if ( result >= 0 )
  {
    result = ZwQueryInformationThread(-2, 0, v73, 48, 0);
    if ( result >= 0 )
    {
      result = ZwQueryInformationThread(-2, 1, &v75, 32, 0);
      if ( result >= 0 )
      {
        result = NtQuerySystemInformation(SystemTimeOfDayInformation, v80, 0x30u, 0);
        if ( result >= 0 )
        {
          result = EtwpGetCpuSpeedFromRegistry(&v59);
          if ( result >= 0 )
          {
            v47 = *(unsigned __int16 *)(a1 + 136) + *(unsigned __int16 *)(a1 + 152);
            v48 = v47 + 316;
            v11 = v47 + 395;
            v56 = v48;
            v58 = v59;
LABEL_10:
            LODWORD(Handle) = v11;
            Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v10);
            if ( !Heap_0 )
              return -1073741801;
            v13 = 3;
            v66 = 0;
            v14 = 0;
            if ( !a4 )
              v13 = 5;
            LODWORD(v61) = v13;
            v65 = 0;
            memset(v72, 0, 44);
            v71 = 0;
            if ( v9 )
            {
              v15 = 2 * wcslen(v9);
              v16 = 65532;
              if ( v15 >= 0xFFFE )
                LOWORD(v15) = -4;
              LOBYTE(v16) = 0;
              v65 = 0u;
              LODWORD(v59) = v16;
              if ( (unsigned __int16)v15 > 1u )
                LODWORD(v59) = v9[((unsigned __int64)(unsigned __int16)v15 >> 1) - 1] == 92;
              v62 = 0;
              v63 = v9;
              v17 = wcslen(v9);
              if ( v17 > 0x7FFE )
              {
                v18 = -1073741562;
                goto LABEL_27;
              }
              LOWORD(v62) = 2 * v17;
              WORD1(v62) = 2 * v17 + 2;
            }
            else
            {
              v65 = 0u;
              LOBYTE(v59) = 0;
              v62 = 0;
              v63 = 0;
            }
            v18 = RtlpDosPathNameToRelativeNtPathName(0, (unsigned int)&v62, 0, (unsigned int)&v65, 0, 0, 0);
            if ( v18 >= 0 )
            {
              *(_DWORD *)v72 = 48;
              *(_QWORD *)&v72[16] = &v65;
              *(_QWORD *)&v72[8] = 0;
              *(_DWORD *)&v72[24] = 64;
              *(_OWORD *)&v72[32] = 0;
              v18 = ZwCreateFile(&v66, 3222274176LL, v72, &v71, 0, 128, 5, v61, 104, 0, 0);
              if ( v18 >= 0 )
              {
                if ( a4 )
                  a4 = *((_QWORD *)&v71 + 1) != 2;
                if ( !(_BYTE)v59 )
                {
                  *(_QWORD *)&v74[32] = 0x2000;
                  memset(v74, 0, 32);
                  v18 = ZwSetInformationFile(v66, &v71, v74, 40, 4);
                }
                v14 = v66;
              }
            }
LABEL_27:
            if ( *((_QWORD *)&v65 + 1) )
            {
              RtlpSysVolFree(*((_QWORD *)&v65 + 1));
              v65 = 0;
            }
            if ( v18 >= 0 )
            {
              if ( !a4 )
              {
                v19 = (_DWORD *)(Heap_0 + 72);
                v20 = (char *)Src[0];
                v21 = (unsigned int)Handle & 0xFFFFFFF8;
                *(_DWORD *)Heap_0 = v10;
                *(_DWORD *)(Heap_0 + 52) = 262145;
                *(_DWORD *)(Heap_0 + 48) = v21;
                if ( v20 )
                {
                  v22 = 0;
                  v23 = 0;
                  if ( (_DWORD)v4 )
                  {
                    do
                    {
                      v24 = &v20[v23];
                      v22 = (__int64)&v20[(unsigned int)v23 + 32];
                      v25 = *(_DWORD *)(a1 + 308) & 0x4101000;
                      *((_DWORD *)v24 + 17) = 1;
                      *((_DWORD *)v24 + 16) = v25 | 0x10001;
                      *((_DWORD *)v24 + 8) = *(_DWORD *)(a1 + 192);
                      if ( (*(_DWORD *)(a1 + 308) & 0x4000000) != 0
                        || *(_DWORD *)(a1 + 192) > 0x100000u
                        || *(_DWORD *)(v22 + 12) > 0x100u )
                      {
                        v26 = 0;
                        v27 = 2;
                      }
                      else
                      {
                        v26 = 5;
                        v27 = 1;
                      }
                      *(_BYTE *)(v22 + 6) = v27;
                      *(_BYTE *)(v22 + 7) = v26;
                      v23 = ((*((unsigned __int16 *)v24 + 2) + 7) & 0xFFFFFFF8) + (unsigned int)v23;
                    }
                    while ( (unsigned int)v23 < (unsigned int)v4 );
                    v19 = (_DWORD *)(Heap_0 + 72);
                  }
                  v28 = 264;
                  if ( *(_DWORD *)(v22 + 44) != 4 )
                    v28 = 272;
                  *(_DWORD *)(a1 + 16) = *(_DWORD *)(v28 + v22);
                  memmove(v19, v20, v4);
                }
                else
                {
                  *(_DWORD *)(Heap_0 + 76) = v56;
                  *v19 = -1073610752;
                  *(_DWORD *)(Heap_0 + 84) = v73[1];
                  *(_DWORD *)(Heap_0 + 80) = DWORD2(v73[1]);
                  *(_DWORD *)(Heap_0 + 96) = (__int64)v76 / DWORD1(SystemInformation[0]);
                  *(_DWORD *)(Heap_0 + 100) = *((_QWORD *)&v76 + 1) / (__int64)DWORD1(SystemInformation[0]);
                  *(_QWORD *)(Heap_0 + 88) = *(_QWORD *)(a1 + 8);
                  v33 = NtCurrentPeb();
                  *(_BYTE *)(Heap_0 + 108) = v33->OSMajorVersion;
                  *(_BYTE *)(Heap_0 + 109) = v33->OSMinorVersion;
                  if ( (*(_DWORD *)(a1 + 308) & 0x4000000) != 0
                    || *(_DWORD *)(a1 + 192) > 0x100000u
                    || *(_DWORD *)(a1 + 188) > 0x100u )
                  {
                    v34 = 0;
                    v35 = 2;
                  }
                  else
                  {
                    v34 = 5;
                    v35 = 1;
                  }
                  *(_BYTE *)(Heap_0 + 110) = v35;
                  *(_BYTE *)(Heap_0 + 111) = v34;
                  *(_DWORD *)(Heap_0 + 112) = v33->OSBuildNumber;
                  *(_DWORD *)(Heap_0 + 376) = *(_DWORD *)(a1 + 16);
                  *(_DWORD *)(Heap_0 + 116) = *(_DWORD *)(a1 + 188);
                  *(_DWORD *)(Heap_0 + 144) = 1;
                  *(_DWORD *)(Heap_0 + 140) = 1;
                  *(_DWORD *)(Heap_0 + 148) = 8;
                  *(_DWORD *)(Heap_0 + 104) = v10;
                  *(_DWORD *)(Heap_0 + 132) = *(_DWORD *)(a1 + 304);
                  *(_DWORD *)(Heap_0 + 136) = *(_DWORD *)(a1 + 308);
                  *(_DWORD *)(Heap_0 + 128) = DWORD1(SystemInformation[0]);
                  *(_QWORD *)(Heap_0 + 352) = *(_QWORD *)&v80[0] - v81;
                  *(_DWORD *)(Heap_0 + 156) = v58;
                  *(_QWORD *)(Heap_0 + 160) = 0;
                  *(_QWORD *)(Heap_0 + 168) = 0;
                  memmove((void *)(Heap_0 + 384), *(const void **)(a1 + 144), *(unsigned __int16 *)(a1 + 136) + 2LL);
                  memmove(
                    (void *)(Heap_0 + *(unsigned __int16 *)(a1 + 136) + 386LL),
                    *(const void **)(a1 + 160),
                    *(unsigned __int16 *)(a1 + 152) + 2LL);
                  EtwpGetTimeZoneInformation((void *)(Heap_0 + 176));
                  *(_QWORD *)(Heap_0 + 360) = MEMORY[0x7FFE0300];
                  *(_QWORD *)(Heap_0 + 368) = *(_QWORD *)a1;
                  v36 = *(unsigned int *)(Heap_0 + 48);
                  if ( (unsigned int)(v36 + 80) <= *(_DWORD *)Heap_0 )
                  {
                    v37 = Heap_0 + v36;
                    *(_DWORD *)(v37 + 4) = 5242960;
                    *(_DWORD *)v37 = -1073610750;
                    *(_DWORD *)(v37 + 8) = DWORD2(v73[1]);
                    *(_DWORD *)(v37 + 12) = v73[1];
                    v68[0] = 4980812;
                    *(_DWORD *)(v37 + 24) = (__int64)v76 / DWORD1(SystemInformation[0]);
                    *(_DWORD *)(v37 + 28) = *((_QWORD *)&v76 + 1) / (__int64)DWORD1(SystemInformation[0]);
                    *(_QWORD *)(v37 + 16) = *(_QWORD *)(a1 + 8);
                    *(_QWORD *)(v37 + 32) = 0;
                    v69[1] = 0;
                    memset_thunk_772440563353939046(v82, 0, 0x4Cu);
                    memset_thunk_772440563353939046(v83, 0, 0x4Cu);
                    v58 = 38;
                    Handle = 0;
                    v62 = 0;
                    v68[1] = v82;
                    v63 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
                    memset(v74, 0, 44);
                    v38 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control");
                    *(_QWORD *)v74 = 48;
                    *(_QWORD *)&v74[24] = 64;
                    if ( v38 >= 0xFFFE )
                      LOWORD(v38) = -4;
                    LOWORD(v62) = v38;
                    WORD1(v62) = v38 + 2;
                    *(_QWORD *)&v74[8] = 0;
                    *(_QWORD *)&v74[16] = &v62;
                    *(_OWORD *)&v74[32] = 0;
                    v39 = NtOpenKey(&Handle, 131097, v74);
                    v40 = v39 == 0;
                    if ( v39 >= 0 )
                    {
                      v41 = 2LL * v58;
                      if ( v41 > 0xFFFFFFFF || (LODWORD(v61) = v41 + 12, (int)v41 + 12 < (unsigned int)v41) )
                      {
                        NtClose(Handle);
                        goto LABEL_42;
                      }
                      v59 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, (unsigned int)(v41 + 12));
                      if ( v59 )
                      {
                        Src[0] = 0;
                        Src[1] = (void *)L"ContainerId";
                        v50 = 2 * wcslen(L"ContainerId");
                        if ( v50 >= 0xFFFE )
                          LOWORD(v50) = -4;
                        LOWORD(Src[0]) = v50;
                        WORD1(Src[0]) = v50 + 2;
                        v57 = NtQueryValueKey(Handle, Src, 2, v59, v61, &v58);
                        if ( v57 >= 0 )
                          memmove(v82, (const void *)(v59 + 12), *(unsigned int *)(v59 + 8));
                        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v59);
                      }
                      else
                      {
                        v57 = -1073741801;
                      }
                      NtClose(Handle);
                      v39 = v57;
                      v40 = v57 == 0;
                    }
                    if ( v40 || v39 == -1073741772 )
                    {
                      v69[0] = 4980812;
                      v70 = v83;
                      RegString = EtwpQueryRegString(
                                    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control",
                                    L"ContainerCorrelationId",
                                    v83,
                                    38);
                      if ( !RegString || RegString == -1073741772 )
                      {
                        RegDwordValue = EtwpGetRegDwordValue(v53, v52, v37 + 36);
                        if ( !RegDwordValue || RegDwordValue == -1073741772 )
                        {
                          *(_QWORD *)(v37 + 40) = 0;
                          Src[0] = (void *)(v37 + 64);
                          if ( (unsigned int)StringToGuidNoBrackets(v68, v37 + 48) )
                            *(_OWORD *)(v37 + 48) = NullGuid;
                          v55 = Src[0];
                          if ( (unsigned int)StringToGuidNoBrackets(v69, Src[0]) )
                            *v55 = NullGuid;
                          *(_DWORD *)(Heap_0 + 48) += 80;
                        }
                      }
                    }
                  }
                }
LABEL_42:
                if ( (*(_DWORD *)(a1 + 308) & 0x4000000) != 0 )
                {
                  *(_DWORD *)(Heap_0 + 44) = 3;
                  if ( (int)ZwQueryVolumeInformationFile(v14, &v67, &v77, 24, 3) >= 0 )
                  {
                    v49 = *(_DWORD *)(Heap_0 + 48) + 80;
                    if ( !v20 )
                      v49 = *(_DWORD *)(Heap_0 + 48);
                    LODWORD(v10) = -HIDWORD(v78) & (v49 + HIDWORD(v78) - 1);
                    *(_DWORD *)Heap_0 = v10;
                  }
                }
                v29 = *(_DWORD *)(Heap_0 + 48);
                v30 = (_QWORD *)(a1 + 464);
                *(_DWORD *)(Heap_0 + 4) = v29;
                if ( ((_QWORD *)*v30 != v30 || *(_QWORD *)(a1 + 448) != a1 + 448)
                  && v29 < (unsigned int)v10
                  && v29 >= 0x180 )
                {
                  if ( *(_QWORD *)(a1 + 448) != a1 + 448 )
                    EtwpAddDebugInfoEvents(a1, Heap_0, (unsigned int)v10);
                  if ( (_QWORD *)*v30 != v30 )
                    EtwpAddBinaryInfoEvents(a1, Heap_0, (unsigned int)v10);
                }
                v31 = *(unsigned int *)(Heap_0 + 48);
                if ( (unsigned int)v31 < (unsigned int)v10 && (unsigned int)v31 > 0x48 )
                  memset_thunk_772440563353939046((void *)(Heap_0 + v31), 255, (unsigned int)(v10 - v31));
                v18 = NtWriteFile(v14, 0, 0, 0, &v67, Heap_0, v10, 0, 0);
                if ( v18 >= 0 )
                {
                  v45 = *(unsigned int *)(a1 + 304);
                  if ( !(_DWORD)v45 || (*(_DWORD *)(a1 + 308) & 0x20) == 0 )
                    goto LABEL_84;
                  v46 = 1024;
                  if ( (*(_DWORD *)(a1 + 308) & 0x2000) == 0 )
                    v46 = 0x100000;
                  Src[0] = (void *)(v45 * v46);
                  v18 = ZwSetInformationFile(v14, &v67, Src, 8, 20);
                  if ( v18 >= 0 )
                  {
LABEL_84:
                    v40 = (*(_DWORD *)(a1 + 308) & 0x4000000) == 0;
                    *(_DWORD *)(a1 + 376) = 1;
                    *(_DWORD *)(a1 + 320) = 1;
                    *(_QWORD *)(a1 + 344) = (unsigned int)v10;
                    *(_QWORD *)(a1 + 336) = (unsigned int)v10;
                    *(_QWORD *)(a1 + 128) = v14;
                    if ( !v40 )
                    {
                      *(_QWORD *)(a1 + 440) = 0;
                      *(_DWORD *)(a1 + 436) = 0;
                    }
                    goto LABEL_55;
                  }
                }
                goto LABEL_53;
              }
              v61 = 0;
              v18 = NtReadFile(v14, 0, 0, 0, &v67, Heap_0, v10, &v61, 0);
              if ( v18 >= 0 )
              {
                if ( (*(_BYTE *)(Heap_0 + 136) & 2) == 0
                  && *(_BYTE *)(Heap_0 + 108) == MEMORY[0x7FFE026C]
                  && *(_BYTE *)(Heap_0 + 109) == MEMORY[0x7FFE0270]
                  && *(_DWORD *)(Heap_0 + 148) == 8 )
                {
                  v42 = *(unsigned int *)(Heap_0 + 104);
                  if ( (unsigned int)(v42 - 1024) <= 0xFFFC00 )
                  {
                    v43 = *(_DWORD *)(Heap_0 + 140);
                    if ( v43 )
                    {
                      if ( *(_QWORD *)(Heap_0 + 120) && *(_DWORD *)(Heap_0 + 116) == *(_DWORD *)(a1 + 188) )
                      {
                        *(_QWORD *)(Heap_0 + 120) = 0;
                        v44 = NtWriteFile(v14, 0, 0, 0, &v67, Heap_0, *(_DWORD *)(a1 + 192), &v61, 0);
                        *(_DWORD *)(a1 + 376) = v43;
                        v18 = v44;
                        *(_DWORD *)(a1 + 320) = v43;
                        *(_DWORD *)(a1 + 192) = v42;
                        *(_QWORD *)(a1 + 336) = v42;
                        *(_QWORD *)(a1 + 128) = v14;
                        *(_QWORD *)(a1 + 344) = (unsigned int)(v42 * v43);
LABEL_55:
                        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
                        return v18;
                      }
                    }
                  }
                }
                v18 = -1073741811;
              }
            }
LABEL_53:
            if ( v14 )
              NtClose(v14);
            goto LABEL_55;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180034bd0  mov     [rsp-8+arg_18], rbx
0x180034bd5  push    rbp
0x180034bd6  push    rsi
0x180034bd7  push    rdi
0x180034bd8  push    r12
0x180034bda  push    r13
0x180034bdc  push    r14
0x180034bde  push    r15
0x180034be0  lea     rbp, [rsp-9F0h]
0x180034be8  sub     rsp, 0AF0h
0x180034bef  mov     rax, cs:__security_cookie
0x180034bf6  xor     rax, rsp
0x180034bf9  mov     [rbp+0A20h+var_40], rax
0x180034c00  xorps   xmm0, xmm0
0x180034c03  mov     r13d, r8d
0x180034c06  xor     eax, eax
0x180034c08  mov     [rbp+0A20h+Src], rdx
0x180034c0c  test    byte ptr [rcx+134h], 8
0x180034c13  xorps   xmm1, xmm1
0x180034c16  movups  xmmword ptr [rbp+0A20h+var_9E0], xmm0
0x180034c1a  movzx   r12d, r9b
0x180034c1e  mov     r15, rdx
0x180034c21  movups  xmmword ptr [rbp+0A20h+var_9E0+0Ch], xmm0
0x180034c25  mov     rbx, rcx
0x180034c28  mov     [rsp+0B20h+var_AB8], eax
0x180034c2c  mov     dword ptr [rsp+0B20h+var_AB0], eax
0x180034c30  movups  [rbp+0A20h+var_970], xmm0
0x180034c37  mov     [rbp+0A20h+var_960], rax
0x180034c3e  movups  [rbp+0A20h+var_A60], xmm0
0x180034c42  movups  [rbp+0A20h+SystemInformation], xmm1
0x180034c49  movups  [rbp+0A20h+var_940], xmm1
0x180034c50  movups  [rbp+0A20h+var_930], xmm1
0x180034c57  movups  [rbp+0A20h+var_920], xmm1
0x180034c5e  movups  [rbp+0A20h+var_910], xmm0
0x180034c65  movups  [rbp+0A20h+var_900], xmm0
0x180034c6c  movups  [rbp+0A20h+var_8F0], xmm0
0x180034c73  movups  [rbp+0A20h+var_9F0], xmm0
0x180034c77  movups  [rbp+0A20h+var_990], xmm0
0x180034c7e  movups  [rbp+0A20h+var_980], xmm0
0x180034c85  jz      loc_180034D52
0x180034c8b  mov     rcx, [rcx+0B0h]; Str
0x180034c92  mov     edx, 25h ; '%'; Ch
0x180034c97  call    wcschr
0x180034c9c  mov     rdi, rax
0x180034c9f  test    rax, rax
0x180034ca2  jz      loc_1800350EE
0x180034ca8  mov     rcx, [rbx+0B0h]; Str
0x180034caf  mov     edx, 25h ; '%'; Ch
0x180034cb4  call    wcsrchr
0x180034cb9  cmp     rdi, rax
0x180034cbc  jnz     loc_1800350EE
0x180034cc2  mov     rcx, [rbx+0B0h]; Str
0x180034cc9  lea     rdx, aD_1; "%d"
0x180034cd0  call    wcsstr
0x180034cd5  test    rax, rax
0x180034cd8  jz      loc_1800350EE
0x180034cde  mov     r9d, 1
0x180034ce4  lock xadd [rbx+0B8h], r9d
0x180034ced  mov     r8, [rbx+0B0h]; pszFormat
0x180034cf4  lea     rcx, [rbp+0A20h+pszDest]; pszDest
0x180034cfb  inc     r9d
0x180034cfe  mov     edx, 800h; cbDest
0x180034d03  call    StringCbPrintfW
0x180034d08  test    eax, eax
0x180034d0a  jnz     loc_1800350FD
0x180034d10  movzx   r8d, word ptr [rbx+0A8h]; Size
0x180034d18  lea     rdx, [rbp+0A20h+pszDest]; Buf2
0x180034d1f  mov     rcx, [rbx+0B0h]; Buf1
0x180034d26  call    memcmp
0x180034d2b  test    eax, eax
0x180034d2d  jz      loc_1800350FD
0x180034d33  lea     rcx, [rbx+98h]; UnicodeString
0x180034d3a  call    RtlFreeAnsiString
0x180034d3f  lea     rdx, [rbp+0A20h+pszDest]
0x180034d46  lea     rcx, [rbx+98h]
0x180034d4d  call    RtlCreateUnicodeString
0x180034d52  mov     rsi, [rbx+0A0h]
0x180034d59  mov     r14d, [rbx+0C0h]
0x180034d60  test    r15, r15
0x180034d63  jz      loc_1800355D6
0x180034d69  mov     [rsp+0B20h+var_AC0], r13d
0x180034d6e  lea     edx, [r13+4Fh]
0x180034d72  mov     rcx, gs:60h
0x180034d7b  mov     r8, r14
0x180034d7e  mov     dword ptr [rsp+0B20h+Handle], edx
0x180034d82  mov     edx, 8
0x180034d87  mov     rcx, [rcx+30h]
0x180034d8b  call    RtlAllocateHeap_0
0x180034d90  mov     rdi, rax
0x180034d93  test    rax, rax
0x180034d96  jz      loc_180035958
0x180034d9c  xorps   xmm0, xmm0
0x180034d9f  xor     eax, eax
0x180034da1  xor     ecx, ecx
0x180034da3  mov     eax, 3
0x180034da8  cmp     r12b, 1
0x180034dac  mov     [rbp+0A20h+var_A68], rcx
0x180034db0  mov     edx, 5
0x180034db5  mov     r15d, ecx
0x180034db8  cmovnz  eax, edx
0x180034dbb  mov     dword ptr [rbp+0A20h+var_AA0], eax
0x180034dbe  movups  [rbp+0A20h+var_A10], xmm0
0x180034dc2  movups  [rbp+0A20h+var_A78], xmm0
0x180034dc6  movups  [rbp+0A20h+var_A20], xmm0
0x180034dca  movups  [rbp+0A20h+var_A10+0Ch], xmm0
0x180034dce  movups  [rbp+0A20h+var_A30], xmm0
0x180034dd2  test    rsi, rsi
0x180034dd5  jz      loc_1800358C7
0x180034ddb  mov     rcx, rsi; String
0x180034dde  call    wcslen
0x180034de3  add     rax, rax
0x180034de6  mov     ecx, 0FFFCh
0x180034deb  cmp     rax, 0FFFEh
0x180034df1  cmovnb  rax, rcx
0x180034df5  xor     edx, edx
0x180034df7  xor     cl, cl
0x180034df9  mov     qword ptr [rbp+0A20h+var_A78], rdx
0x180034dfd  mov     qword ptr [rbp+0A20h+var_A78+8], rdx
0x180034e01  mov     dword ptr [rsp+0B20h+var_AB0], ecx
0x180034e05  cmp     ax, 1
0x180034e09  ja      loc_1800358E0
0x180034e0f  mov     rcx, rsi; String
0x180034e12  mov     [rbp+0A20h+var_A98], rdx
0x180034e16  mov     [rbp+0A20h+var_A90], rsi
0x180034e1a  call    wcslen
0x180034e1f  cmp     rax, 7FFEh
0x180034e25  ja      loc_18003594E
0x180034e2b  add     ax, ax
0x180034e2e  mov     word ptr [rbp+0A20h+var_A98], ax
0x180034e32  add     ax, 2
0x180034e36  mov     word ptr [rbp+0A20h+var_A98+2], ax
0x180034e3a  xor     ecx, ecx
0x180034e3c  mov     [rsp+0B20h+var_AF0], rcx
0x180034e41  lea     r9, [rbp+0A20h+var_A78]
0x180034e45  mov     [rsp+0B20h+var_AF8], rcx
0x180034e4a  lea     rdx, [rbp+0A20h+var_A98]
0x180034e4e  mov     [rsp+0B20h+var_B00], rcx
0x180034e53  xor     r8d, r8d
0x180034e56  xor     ecx, ecx
0x180034e58  call    RtlpDosPathNameToRelativeNtPathName
0x180034e5d  mov     esi, eax
0x180034e5f  test    eax, eax
0x180034e61  js      loc_180034EF3
0x180034e67  xor     ecx, ecx
0x180034e69  mov     dword ptr [rbp+0A20h+var_A20], 30h ; '0'
0x180034e70  mov     [rsp+0B20h+var_AD0], ecx
0x180034e74  lea     rax, [rbp+0A20h+var_A78]
0x180034e78  mov     [rsp+0B20h+var_AD8], rcx
0x180034e7d  lea     r9, [rbp+0A20h+var_A30]
0x180034e81  mov     dword ptr [rsp+0B20h+var_AE0], 68h ; 'h'
0x180034e89  lea     r8, [rbp+0A20h+var_A20]
0x180034e8d  mov     qword ptr [rbp+0A20h+var_A10], rax
0x180034e91  xorps   xmm0, xmm0
0x180034e94  mov     eax, dword ptr [rbp+0A20h+var_AA0]
0x180034e97  mov     edx, 0C0100080h
0x180034e9c  mov     dword ptr [rsp+0B20h+var_AE8], eax
0x180034ea0  mov     dword ptr [rsp+0B20h+var_AF0], 5
0x180034ea8  mov     qword ptr [rbp+0A20h+var_A20+8], rcx
0x180034eac  mov     dword ptr [rsp+0B20h+var_AF8], 80h
0x180034eb4  mov     [rsp+0B20h+var_B00], rcx
0x180034eb9  lea     rcx, [rbp+0A20h+var_A68]
0x180034ebd  mov     dword ptr [rbp+0A20h+var_A10+8], 40h ; '@'
0x180034ec4  movdqu  [rbp+0A20h+var_A00], xmm0
0x180034ec9  call    ZwCreateFile
0x180034ece  mov     esi, eax
0x180034ed0  test    eax, eax
0x180034ed2  js      short loc_180034EF3
0x180034ed4  cmp     r12b, 1
0x180034ed8  jnz     short loc_180034EE4
0x180034eda  cmp     qword ptr [rbp+0A20h+var_A30+8], 2
0x180034edf  jnz     short loc_180034EE4
0x180034ee1  xor     r12b, r12b
0x180034ee4  cmp     byte ptr [rsp+0B20h+var_AB0], r15b
0x180034ee9  jz      loc_18003590A
0x180034eef  mov     r15, [rbp+0A20h+var_A68]
0x180034ef3  mov     rcx, qword ptr [rbp+0A20h+var_A78+8]
0x180034ef7  test    rcx, rcx
0x180034efa  jz      short loc_180034F08
0x180034efc  call    RtlpSysVolFree
0x180034f01  xorps   xmm0, xmm0
0x180034f04  movups  [rbp+0A20h+var_A78], xmm0
0x180034f08  test    esi, esi
0x180034f0a  js      loc_18003509D
0x180034f10  test    r12b, r12b
0x180034f13  jnz     loc_180035407
0x180034f19  mov     eax, dword ptr [rsp+0B20h+Handle]
0x180034f1d  lea     r9, [rdi+48h]
0x180034f21  mov     rsi, [rbp+0A20h+Src]
0x180034f25  and     eax, 0FFFFFFF8h
0x180034f28  mov     [rdi], r14d
0x180034f2b  mov     r8d, 1
0x180034f31  mov     dword ptr [rdi+34h], 40001h
0x180034f38  mov     r12d, 100000h
0x180034f3e  mov     [rdi+30h], eax
0x180034f41  test    rsi, rsi
0x180034f44  jz      loc_18003510C
0x180034f4a  xor     ecx, ecx
0x180034f4c  xor     edx, edx
0x180034f4e  test    r13d, r13d
0x180034f51  jz      short loc_180034FCA
0x180034f53  lea     r8, [rdx+rsi]
0x180034f57  mov     eax, edx
0x180034f59  lea     rcx, [rsi+20h]
0x180034f5d  add     rcx, rax
0x180034f60  mov     eax, [rbx+134h]
0x180034f66  and     eax, 4101000h
0x180034f6b  mov     dword ptr [r8+44h], 1
0x180034f73  or      eax, 10001h
0x180034f78  mov     [r8+40h], eax
0x180034f7c  mov     eax, [rbx+0C0h]
0x180034f82  mov     [r8+20h], eax
0x180034f86  test    dword ptr [rbx+134h], 4000000h
0x180034f90  jnz     short loc_180034FA8
0x180034f92  cmp     [rbx+0C0h], r12d
0x180034f99  ja      short loc_180034FA8
0x180034f9b  cmp     dword ptr [rcx+0Ch], 100h
0x180034fa2  jbe     loc_18003596D
0x180034fa8  xor     al, al
0x180034faa  mov     r10b, 2
0x180034fad  mov     [rcx+6], r10b
0x180034fb1  mov     [rcx+7], al
0x180034fb4  movzx   eax, word ptr [r8+4]
0x180034fb9  add     eax, 7
0x180034fbc  and     eax, 0FFFFFFF8h
0x180034fbf  add     edx, eax
0x180034fc1  cmp     edx, r13d
0x180034fc4  jb      short loc_180034F53
0x180034fc6  lea     r9, [rdi+48h]
0x180034fca  cmp     dword ptr [rcx+2Ch], 4
0x180034fce  mov     edx, 110h
0x180034fd3  mov     eax, 108h
0x180034fd8  mov     r8, r13; Size
0x180034fdb  cmovnz  eax, edx
0x180034fde  mov     rdx, rsi; Src
0x180034fe1  mov     eax, [rax+rcx]
0x180034fe4  mov     rcx, r9; void *
0x180034fe7  mov     [rbx+10h], eax
0x180034fea  call    memmove
0x180034fef  xor     r13d, r13d
0x180034ff2  test    dword ptr [rbx+134h], 4000000h
0x180034ffc  jnz     loc_1800356AE
0x180035002  mov     ecx, [rdi+30h]
0x180035005  lea     rsi, [rbx+1D0h]
0x18003500c  mov     [rdi+4], ecx
0x18003500f  cmp     [rsi], rsi
0x180035012  jnz     short loc_180035020
0x180035014  lea     rax, [rbx+1C0h]
0x18003501b  cmp     [rax], rax
0x18003501e  jz      short loc_18003505A
0x180035020  cmp     ecx, r14d
0x180035023  jnb     short loc_18003505A
0x180035025  cmp     ecx, 180h
0x18003502b  jb      short loc_18003505A
0x18003502d  lea     rax, [rbx+1C0h]
0x180035034  cmp     [rax], rax
0x180035037  jz      short loc_180035047
0x180035039  mov     r8d, r14d
0x18003503c  mov     rdx, rdi
0x18003503f  mov     rcx, rbx
0x180035042  call    EtwpAddDebugInfoEvents
0x180035047  cmp     [rsi], rsi
0x18003504a  jz      short loc_18003505A
0x18003504c  mov     r8d, r14d
0x18003504f  mov     rdx, rdi
0x180035052  mov     rcx, rbx
0x180035055  call    EtwpAddBinaryInfoEvents
0x18003505a  mov     ecx, [rdi+30h]
0x18003505d  cmp     ecx, r14d
0x180035060  jb      loc_180035704
0x180035066  mov     [rsp+0B20h+var_AE0], r13
0x18003506b  lea     rax, [rbp+0A20h+var_A60]
0x18003506f  mov     [rsp+0B20h+var_AE8], r13
0x180035074  xor     r9d, r9d
0x180035077  mov     dword ptr [rsp+0B20h+var_AF0], r14d
0x18003507c  xor     r8d, r8d
0x18003507f  mov     [rsp+0B20h+var_AF8], rdi
0x180035084  xor     edx, edx
0x180035086  mov     rcx, r15
0x180035089  mov     [rsp+0B20h+var_B00], rax
0x18003508e  call    NtWriteFile
0x180035093  mov     esi, eax
0x180035095  test    eax, eax
0x180035097  jns     loc_180035534
0x18003509d  test    r15, r15
0x1800350a0  jz      short loc_1800350AA
0x1800350a2  mov     rcx, r15; Handle
0x1800350a5  call    NtClose
0x1800350aa  mov     rcx, gs:60h
0x1800350b3  mov     r8, rdi
0x1800350b6  xor     edx, edx
0x1800350b8  mov     rcx, [rcx+30h]
0x1800350bc  call    RtlFreeHeap_0
0x1800350c1  mov     eax, esi
0x1800350c3  mov     rcx, [rbp+0A20h+var_40]
0x1800350ca  xor     rcx, rsp; StackCookie
0x1800350cd  call    __security_check_cookie
0x1800350d2  mov     rbx, [rsp+0B20h+arg_18]
0x1800350da  add     rsp, 0AF0h
0x1800350e1  pop     r15
0x1800350e3  pop     r14
  ... truncated ...
```
