# EtwpAddLogHeaderToLogFile

- ea: `0x180035a70`
- end: `0x180036817`
- name: `EtwpAddLogHeaderToLogFile`
- size: `3495`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18007d3dc`
- `0x18007e490`
- `0x180158eec`

## callees

- `0x1800165d0`
- `0x18001861c`
- `0x18001b984`
- `0x18001c520`
- `0x18001d490`
- `0x1800353f0`
- `0x1800355d8`
- `0x180035790`
- `0x1800358dc`
- `0x180035a70`
- `0x1800369a0`
- `0x1800369d4`
- `0x180036a60`
- `0x180036bc0`
- `0x180036d44`
- `0x180036e70`
- `0x18012c720`
- `0x18012c830`
- `0x18012cc90`
- `0x18012cda0`
- `0x18015e390`
- `0x18015e3d0`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x18015e770`
- `0x18015e7b0`
- `0x18015e990`
- `0x18015ebf0`
- `0x18015ed70`
- `0x180162000`
- `0x180163a80`
- `0x180163d50`
- `0x18016f030`

## string_xrefs

- `0x180036202`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x1800366d8`: `\Registry\Machine\System\CurrentControlSet\Control`

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
0x180035a70  mov     [rsp-8+arg_18], rbx
0x180035a75  push    rbp
0x180035a76  push    rsi
0x180035a77  push    rdi
0x180035a78  push    r12
0x180035a7a  push    r13
0x180035a7c  push    r14
0x180035a7e  push    r15
0x180035a80  lea     rbp, [rsp-9F0h]
0x180035a88  sub     rsp, 0AF0h
0x180035a8f  mov     rax, cs:__security_cookie
0x180035a96  xor     rax, rsp
0x180035a99  mov     [rbp+0A20h+var_40], rax
0x180035aa0  xorps   xmm0, xmm0
0x180035aa3  mov     r13d, r8d
0x180035aa6  xor     eax, eax
0x180035aa8  mov     [rbp+0A20h+Src], rdx
0x180035aac  test    byte ptr [rcx+134h], 8
0x180035ab3  xorps   xmm1, xmm1
0x180035ab6  movups  xmmword ptr [rbp+0A20h+var_9E0], xmm0
0x180035aba  movzx   r12d, r9b
0x180035abe  mov     r15, rdx
0x180035ac1  movups  xmmword ptr [rbp+0A20h+var_9E0+0Ch], xmm0
0x180035ac5  mov     rbx, rcx
0x180035ac8  mov     [rsp+0B20h+var_AB8], eax
0x180035acc  mov     dword ptr [rsp+0B20h+var_AB0], eax
0x180035ad0  movups  [rbp+0A20h+var_970], xmm0
0x180035ad7  mov     [rbp+0A20h+var_960], rax
0x180035ade  movups  [rbp+0A20h+var_A60], xmm0
0x180035ae2  movups  [rbp+0A20h+SystemInformation], xmm1
0x180035ae9  movups  [rbp+0A20h+var_940], xmm1
0x180035af0  movups  [rbp+0A20h+var_930], xmm1
0x180035af7  movups  [rbp+0A20h+var_920], xmm1
0x180035afe  movups  [rbp+0A20h+var_910], xmm0
0x180035b05  movups  [rbp+0A20h+var_900], xmm0
0x180035b0c  movups  [rbp+0A20h+var_8F0], xmm0
0x180035b13  movups  [rbp+0A20h+var_9F0], xmm0
0x180035b17  movups  [rbp+0A20h+var_990], xmm0
0x180035b1e  movups  [rbp+0A20h+var_980], xmm0
0x180035b25  jz      loc_180035BF2
0x180035b2b  mov     rcx, [rcx+0B0h]; Str
0x180035b32  mov     edx, 25h ; '%'; Ch
0x180035b37  call    wcschr
0x180035b3c  mov     rdi, rax
0x180035b3f  test    rax, rax
0x180035b42  jz      loc_180035F8E
0x180035b48  mov     rcx, [rbx+0B0h]; Str
0x180035b4f  mov     edx, 25h ; '%'; Ch
0x180035b54  call    wcsrchr
0x180035b59  cmp     rdi, rax
0x180035b5c  jnz     loc_180035F8E
0x180035b62  mov     rcx, [rbx+0B0h]; Str
0x180035b69  lea     rdx, aD_2; "%d"
0x180035b70  call    wcsstr
0x180035b75  test    rax, rax
0x180035b78  jz      loc_180035F8E
0x180035b7e  mov     r9d, 1
0x180035b84  lock xadd [rbx+0B8h], r9d
0x180035b8d  mov     r8, [rbx+0B0h]; pszFormat
0x180035b94  lea     rcx, [rbp+0A20h+pszDest]; pszDest
0x180035b9b  inc     r9d
0x180035b9e  mov     edx, 800h; cbDest
0x180035ba3  call    StringCbPrintfW
0x180035ba8  test    eax, eax
0x180035baa  jnz     loc_180035F9D
0x180035bb0  movzx   r8d, word ptr [rbx+0A8h]; Size
0x180035bb8  lea     rdx, [rbp+0A20h+pszDest]; Buf2
0x180035bbf  mov     rcx, [rbx+0B0h]; Buf1
0x180035bc6  call    memcmp
0x180035bcb  test    eax, eax
0x180035bcd  jz      loc_180035F9D
0x180035bd3  lea     rcx, [rbx+98h]; UnicodeString
0x180035bda  call    RtlFreeAnsiString
0x180035bdf  lea     rdx, [rbp+0A20h+pszDest]
0x180035be6  lea     rcx, [rbx+98h]
0x180035bed  call    RtlCreateUnicodeString
0x180035bf2  mov     rsi, [rbx+0A0h]
0x180035bf9  mov     r14d, [rbx+0C0h]
0x180035c00  test    r15, r15
0x180035c03  jz      loc_180036476
0x180035c09  mov     [rsp+0B20h+var_AC0], r13d
0x180035c0e  lea     edx, [r13+4Fh]
0x180035c12  mov     rcx, gs:60h
0x180035c1b  mov     r8, r14
0x180035c1e  mov     dword ptr [rsp+0B20h+Handle], edx
0x180035c22  mov     edx, 8
0x180035c27  mov     rcx, [rcx+30h]
0x180035c2b  call    RtlAllocateHeap_0
0x180035c30  mov     rdi, rax
0x180035c33  test    rax, rax
0x180035c36  jz      loc_1800367F8
0x180035c3c  xorps   xmm0, xmm0
0x180035c3f  xor     eax, eax
0x180035c41  xor     ecx, ecx
0x180035c43  mov     eax, 3
0x180035c48  cmp     r12b, 1
0x180035c4c  mov     [rbp+0A20h+var_A68], rcx
0x180035c50  mov     edx, 5
0x180035c55  mov     r15d, ecx
0x180035c58  cmovnz  eax, edx
0x180035c5b  mov     dword ptr [rbp+0A20h+var_AA0], eax
0x180035c5e  movups  [rbp+0A20h+var_A10], xmm0
0x180035c62  movups  [rbp+0A20h+var_A78], xmm0
0x180035c66  movups  [rbp+0A20h+var_A20], xmm0
0x180035c6a  movups  [rbp+0A20h+var_A10+0Ch], xmm0
0x180035c6e  movups  [rbp+0A20h+var_A30], xmm0
0x180035c72  test    rsi, rsi
0x180035c75  jz      loc_180036767
0x180035c7b  mov     rcx, rsi; String
0x180035c7e  call    wcslen
0x180035c83  add     rax, rax
0x180035c86  mov     ecx, 0FFFCh
0x180035c8b  cmp     rax, 0FFFEh
0x180035c91  cmovnb  rax, rcx
0x180035c95  xor     edx, edx
0x180035c97  xor     cl, cl
0x180035c99  mov     qword ptr [rbp+0A20h+var_A78], rdx
0x180035c9d  mov     qword ptr [rbp+0A20h+var_A78+8], rdx
0x180035ca1  mov     dword ptr [rsp+0B20h+var_AB0], ecx
0x180035ca5  cmp     ax, 1
0x180035ca9  ja      loc_180036780
0x180035caf  mov     rcx, rsi; String
0x180035cb2  mov     [rbp+0A20h+var_A98], rdx
0x180035cb6  mov     [rbp+0A20h+var_A90], rsi
0x180035cba  call    wcslen
0x180035cbf  cmp     rax, 7FFEh
0x180035cc5  ja      loc_1800367EE
0x180035ccb  add     ax, ax
0x180035cce  mov     word ptr [rbp+0A20h+var_A98], ax
0x180035cd2  add     ax, 2
0x180035cd6  mov     word ptr [rbp+0A20h+var_A98+2], ax
0x180035cda  xor     ecx, ecx
0x180035cdc  mov     [rsp+0B20h+var_AF0], rcx
0x180035ce1  lea     r9, [rbp+0A20h+var_A78]
0x180035ce5  mov     [rsp+0B20h+var_AF8], rcx
0x180035cea  lea     rdx, [rbp+0A20h+var_A98]
0x180035cee  mov     [rsp+0B20h+var_B00], rcx
0x180035cf3  xor     r8d, r8d
0x180035cf6  xor     ecx, ecx
0x180035cf8  call    RtlpDosPathNameToRelativeNtPathName
0x180035cfd  mov     esi, eax
0x180035cff  test    eax, eax
0x180035d01  js      loc_180035D93
0x180035d07  xor     ecx, ecx
0x180035d09  mov     dword ptr [rbp+0A20h+var_A20], 30h ; '0'
0x180035d10  mov     [rsp+0B20h+var_AD0], ecx
0x180035d14  lea     rax, [rbp+0A20h+var_A78]
0x180035d18  mov     [rsp+0B20h+var_AD8], rcx
0x180035d1d  lea     r9, [rbp+0A20h+var_A30]
0x180035d21  mov     dword ptr [rsp+0B20h+var_AE0], 68h ; 'h'
0x180035d29  lea     r8, [rbp+0A20h+var_A20]
0x180035d2d  mov     qword ptr [rbp+0A20h+var_A10], rax
0x180035d31  xorps   xmm0, xmm0
0x180035d34  mov     eax, dword ptr [rbp+0A20h+var_AA0]
0x180035d37  mov     edx, 0C0100080h
0x180035d3c  mov     dword ptr [rsp+0B20h+var_AE8], eax
0x180035d40  mov     dword ptr [rsp+0B20h+var_AF0], 5
0x180035d48  mov     qword ptr [rbp+0A20h+var_A20+8], rcx
0x180035d4c  mov     dword ptr [rsp+0B20h+var_AF8], 80h
0x180035d54  mov     [rsp+0B20h+var_B00], rcx
0x180035d59  lea     rcx, [rbp+0A20h+var_A68]
0x180035d5d  mov     dword ptr [rbp+0A20h+var_A10+8], 40h ; '@'
0x180035d64  movdqu  [rbp+0A20h+var_A00], xmm0
0x180035d69  call    ZwCreateFile
0x180035d6e  mov     esi, eax
0x180035d70  test    eax, eax
0x180035d72  js      short loc_180035D93
0x180035d74  cmp     r12b, 1
0x180035d78  jnz     short loc_180035D84
0x180035d7a  cmp     qword ptr [rbp+0A20h+var_A30+8], 2
0x180035d7f  jnz     short loc_180035D84
0x180035d81  xor     r12b, r12b
0x180035d84  cmp     byte ptr [rsp+0B20h+var_AB0], r15b
0x180035d89  jz      loc_1800367AA
0x180035d8f  mov     r15, [rbp+0A20h+var_A68]
0x180035d93  mov     rcx, qword ptr [rbp+0A20h+var_A78+8]
0x180035d97  test    rcx, rcx
0x180035d9a  jz      short loc_180035DA8
0x180035d9c  call    RtlpSysVolFree
0x180035da1  xorps   xmm0, xmm0
0x180035da4  movups  [rbp+0A20h+var_A78], xmm0
0x180035da8  test    esi, esi
0x180035daa  js      loc_180035F3D
0x180035db0  test    r12b, r12b
0x180035db3  jnz     loc_1800362A7
0x180035db9  mov     eax, dword ptr [rsp+0B20h+Handle]
0x180035dbd  lea     r9, [rdi+48h]
0x180035dc1  mov     rsi, [rbp+0A20h+Src]
0x180035dc5  and     eax, 0FFFFFFF8h
0x180035dc8  mov     [rdi], r14d
0x180035dcb  mov     r8d, 1
0x180035dd1  mov     dword ptr [rdi+34h], 40001h
0x180035dd8  mov     r12d, 100000h
0x180035dde  mov     [rdi+30h], eax
0x180035de1  test    rsi, rsi
0x180035de4  jz      loc_180035FAC
0x180035dea  xor     ecx, ecx
0x180035dec  xor     edx, edx
0x180035dee  test    r13d, r13d
0x180035df1  jz      short loc_180035E6A
0x180035df3  lea     r8, [rdx+rsi]
0x180035df7  mov     eax, edx
0x180035df9  lea     rcx, [rsi+20h]
0x180035dfd  add     rcx, rax
0x180035e00  mov     eax, [rbx+134h]
0x180035e06  and     eax, 4101000h
0x180035e0b  mov     dword ptr [r8+44h], 1
0x180035e13  or      eax, 10001h
0x180035e18  mov     [r8+40h], eax
0x180035e1c  mov     eax, [rbx+0C0h]
0x180035e22  mov     [r8+20h], eax
0x180035e26  test    dword ptr [rbx+134h], 4000000h
0x180035e30  jnz     short loc_180035E48
0x180035e32  cmp     [rbx+0C0h], r12d
0x180035e39  ja      short loc_180035E48
0x180035e3b  cmp     dword ptr [rcx+0Ch], 100h
0x180035e42  jbe     loc_18003680D
0x180035e48  xor     al, al
0x180035e4a  mov     r10b, 2
0x180035e4d  mov     [rcx+6], r10b
0x180035e51  mov     [rcx+7], al
0x180035e54  movzx   eax, word ptr [r8+4]
0x180035e59  add     eax, 7
0x180035e5c  and     eax, 0FFFFFFF8h
0x180035e5f  add     edx, eax
0x180035e61  cmp     edx, r13d
0x180035e64  jb      short loc_180035DF3
0x180035e66  lea     r9, [rdi+48h]
0x180035e6a  cmp     dword ptr [rcx+2Ch], 4
0x180035e6e  mov     edx, 110h
0x180035e73  mov     eax, 108h
0x180035e78  mov     r8, r13; Size
0x180035e7b  cmovnz  eax, edx
0x180035e7e  mov     rdx, rsi; Src
0x180035e81  mov     eax, [rax+rcx]
0x180035e84  mov     rcx, r9; void *
0x180035e87  mov     [rbx+10h], eax
0x180035e8a  call    memmove
0x180035e8f  xor     r13d, r13d
0x180035e92  test    dword ptr [rbx+134h], 4000000h
0x180035e9c  jnz     loc_18003654E
0x180035ea2  mov     ecx, [rdi+30h]
0x180035ea5  lea     rsi, [rbx+1D0h]
0x180035eac  mov     [rdi+4], ecx
0x180035eaf  cmp     [rsi], rsi
0x180035eb2  jnz     short loc_180035EC0
0x180035eb4  lea     rax, [rbx+1C0h]
0x180035ebb  cmp     [rax], rax
0x180035ebe  jz      short loc_180035EFA
0x180035ec0  cmp     ecx, r14d
0x180035ec3  jnb     short loc_180035EFA
0x180035ec5  cmp     ecx, 180h
0x180035ecb  jb      short loc_180035EFA
0x180035ecd  lea     rax, [rbx+1C0h]
0x180035ed4  cmp     [rax], rax
0x180035ed7  jz      short loc_180035EE7
0x180035ed9  mov     r8d, r14d
0x180035edc  mov     rdx, rdi
0x180035edf  mov     rcx, rbx
0x180035ee2  call    EtwpAddDebugInfoEvents
0x180035ee7  cmp     [rsi], rsi
0x180035eea  jz      short loc_180035EFA
0x180035eec  mov     r8d, r14d
0x180035eef  mov     rdx, rdi
0x180035ef2  mov     rcx, rbx
0x180035ef5  call    EtwpAddBinaryInfoEvents
0x180035efa  mov     ecx, [rdi+30h]
0x180035efd  cmp     ecx, r14d
0x180035f00  jb      loc_1800365A4
0x180035f06  mov     [rsp+0B20h+var_AE0], r13
0x180035f0b  lea     rax, [rbp+0A20h+var_A60]
0x180035f0f  mov     [rsp+0B20h+var_AE8], r13
0x180035f14  xor     r9d, r9d
0x180035f17  mov     dword ptr [rsp+0B20h+var_AF0], r14d
0x180035f1c  xor     r8d, r8d
0x180035f1f  mov     [rsp+0B20h+var_AF8], rdi
0x180035f24  xor     edx, edx
0x180035f26  mov     rcx, r15
0x180035f29  mov     [rsp+0B20h+var_B00], rax
0x180035f2e  call    NtWriteFile
0x180035f33  mov     esi, eax
0x180035f35  test    eax, eax
0x180035f37  jns     loc_1800363D4
0x180035f3d  test    r15, r15
0x180035f40  jz      short loc_180035F4A
0x180035f42  mov     rcx, r15; Handle
0x180035f45  call    NtClose
0x180035f4a  mov     rcx, gs:60h
0x180035f53  mov     r8, rdi
0x180035f56  xor     edx, edx
0x180035f58  mov     rcx, [rcx+30h]
0x180035f5c  call    RtlFreeHeap_0
0x180035f61  mov     eax, esi
0x180035f63  mov     rcx, [rbp+0A20h+var_40]
0x180035f6a  xor     rcx, rsp; StackCookie
0x180035f6d  call    __security_check_cookie
0x180035f72  mov     rbx, [rsp+0B20h+arg_18]
0x180035f7a  add     rsp, 0AF0h
0x180035f81  pop     r15
0x180035f83  pop     r14
  ... truncated ...
```
