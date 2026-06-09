# EtwpProcessLogHeader(_TRACELOG_CONTEXT * *,ulong,uchar)

- ea: `0x1800052b4`
- end: `0x180005cc2`
- name: `?EtwpProcessLogHeader@@YAKPEAPEAU_TRACELOG_CONTEXT@@KE@Z`
- size: `2574`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT **, unsigned int, unsigned __int8)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x180006970`
- `0x180007060`
- `0x180012674`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x180001ee2`
- `0x180001ff0`
- `0x180002014`
- `0x180004768`
- `0x1800052b4`
- `0x180005cc8`
- `0x180010ae0`
- `0x180012120`
- `0x180012c14`
- `0x180012e48`
- `0x180015810`
- `0x180015834`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180005889`
- `ntdll!NtQueryInformationFile` at `0x180005889`
- `ntdll!RtlSetLastWin32Error` at `0x180005b8b`
- `ntdll!RtlSetLastWin32Error` at `0x180005b9f`
- `ntdll!RtlSetLastWin32Error` at `0x180005bbb`
- `ntdll!RtlSetLastWin32Error` at `0x180005bf0`
- `ntdll!RtlSetLastWin32Error` at `0x180005c08`
- `ntdll!RtlSetLastWin32Error` at `0x180005b8b`
- `ntdll!RtlSetLastWin32Error` at `0x180005b9f`
- `ntdll!RtlSetLastWin32Error` at `0x180005bbb`
- `ntdll!RtlSetLastWin32Error` at `0x180005bf0`
- `ntdll!RtlSetLastWin32Error` at `0x180005c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b6f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800053c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800053c0`

## pseudocode

```c
__int64 __fastcall EtwpProcessLogHeader(struct _TRACELOG_CONTEXT **a1, unsigned int a2, char a3)
{
  __int64 v3; // rsi
  struct _TRACELOG_CONTEXT **v5; // r13
  void *v6; // rax
  unsigned int *v7; // r15
  __int64 v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // r14
  struct _TRACELOG_CONTEXT *v12; // r13
  __int64 v13; // r12
  HANDLE FileW; // rax
  unsigned int v15; // eax
  unsigned int NextEventOffsetType; // eax
  DWORD LastError; // r12d
  _OWORD *MofData; // rdx
  unsigned int v19; // r8d
  char *v20; // rcx
  __int64 v21; // rax
  __int128 v22; // xmm1
  wchar_t *v23; // rcx
  size_t v24; // rcx
  unsigned int v25; // eax
  void *v26; // rax
  unsigned int v27; // r15d
  unsigned __int8 v28; // al
  void *v29; // rax
  void *v30; // r12
  struct _TRACELOG_CONTEXT **v31; // rdx
  __int64 v32; // rax
  void *v33; // rcx
  int v34; // ecx
  unsigned int SpecialHeaderEvents; // eax
  unsigned int v36; // r8d
  unsigned int v37; // r12d
  unsigned int v38; // eax
  int v39; // eax
  unsigned __int64 v40; // r8
  unsigned __int64 v41; // r10
  unsigned int v42; // r11d
  __int64 v43; // rcx
  unsigned int v44; // r9d
  unsigned __int64 v45; // rtt
  unsigned __int64 v46; // r8
  unsigned int v47; // eax
  unsigned int v48; // edx
  int v49; // eax
  __int64 v50; // rdx
  int v51; // r9d
  int v52; // ecx
  bool v53; // al
  int v54; // ecx
  int v55; // eax
  int v56; // edx
  __int64 v57; // rax
  __int64 v58; // rax
  ULONG v60; // ecx
  unsigned int v61; // r9d
  struct _TRACELOG_CONTEXT **v62; // r12
  __int64 v63; // rcx
  struct _TRACELOG_CONTEXT *v64; // rdx
  int v65; // r8d
  unsigned int v66; // [rsp+40h] [rbp-C0h]
  char v67; // [rsp+44h] [rbp-BCh]
  char v68; // [rsp+45h] [rbp-BBh]
  size_t v70; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v71; // [rsp+50h] [rbp-B0h]
  struct _TRACELOG_CONTEXT **v72; // [rsp+58h] [rbp-A8h]
  unsigned int v73; // [rsp+60h] [rbp-A0h]
  void *Src; // [rsp+68h] [rbp-98h]
  int v75; // [rsp+70h] [rbp-90h]
  int v76; // [rsp+74h] [rbp-8Ch]
  int v77; // [rsp+78h] [rbp-88h]
  int v78; // [rsp+7Ch] [rbp-84h]
  int v79; // [rsp+80h] [rbp-80h]
  unsigned int v80; // [rsp+84h] [rbp-7Ch]
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  void *v82; // [rsp+90h] [rbp-70h]
  size_t Size; // [rsp+98h] [rbp-68h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_TRACE v85; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+110h] [rbp+10h] BYREF
  __int64 v87; // [rsp+120h] [rbp+20h]
  struct _EVENT_TRACE v88; // [rsp+130h] [rbp+30h] BYREF

  v3 = 0;
  v80 = a2;
  v5 = a1;
  v72 = a1;
  v70 = 0;
  String1 = 0;
  memset_0(&v88, 0, sizeof(v88));
  v87 = 0;
  FileInformation = 0;
  IoStatusBlock = 0;
  v6 = operator new(0x1000u, (const struct std::nothrow_t *)&std::nothrow);
  Src = v6;
  v7 = (unsigned int *)v6;
  if ( !v6 )
  {
LABEL_112:
    LastError = 14;
    RtlSetLastWin32Error(0xEu);
    return LastError;
  }
  memset_0(v6, 0, 0x1000u);
  v8 = 0;
  v76 = 0;
  v77 = 0;
  v9 = 0;
  v78 = 0;
  v10 = 0;
  v79 = 0;
  v11 = 0;
  v67 = 1;
  v68 = 0;
  v75 = 0;
  v71 = 0;
  if ( !a2 )
  {
    LastError = 0;
    Src = v7;
    goto LABEL_124;
  }
  while ( 1 )
  {
    v12 = v5[v8];
    v13 = (unsigned int)v8;
    if ( a3 )
    {
      FileW = CreateFileW(*((LPCWSTR *)v12 + 10), 0x80000000, 7u, 0, 3u, 0x40000080u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        goto LABEL_136;
      }
      *((_QWORD *)v12 + 78) = FileW;
    }
    memset_0(v7, 0, 0x1000u);
    EtwpSynchReadFile(
      *((HANDLE *)v12 + 78),
      v7,
      0x1000u,
      (unsigned int *)&v70 + 1,
      (struct _OVERLAPPED *)((char *)v72[v13] + 592),
      0);
    if ( HIDWORD(v70) < 0x178 )
      break;
    v15 = v7[12];
    if ( v15 < 0x48 )
      break;
    if ( v15 > *v7 )
      break;
    memset_0(&v88, 0, sizeof(v88));
    NextEventOffsetType = EtwpGetNextEventOffsetType(v7, 72, &v70);
    if ( !NextEventOffsetType )
      break;
    if ( (unsigned int)(v70 + 72) > HIDWORD(v70) )
      break;
    v66 = EtwpMapEventToEventTrace(0, v7 + 18, &v88, NextEventOffsetType, (struct _WMI_BUFFER_HEADER *)v7);
    LastError = v66;
    if ( v66 )
      break;
    if ( v88.MofLength < 0x30 )
      break;
    if ( (unsigned int)(v70 + 72) > 0x1000 )
      break;
    MofData = v88.MofData;
    v19 = *((_DWORD *)v88.MofData + 11);
    if ( ((v19 - 4) & 0xFFFFFFFB) != 0 )
      break;
    if ( (*((_DWORD *)v88.MofData + 8) & 0x4000000) != 0 )
    {
      if ( (v7[13] & 0x40) != 0 || (*((_BYTE *)v88.MofData + 32) & 2) != 0 )
        break;
      if ( *v7 > *(_DWORD *)v88.MofData )
      {
        LastError = 1392;
LABEL_109:
        v66 = LastError;
        RtlSetLastWin32Error(LastError);
        goto LABEL_125;
      }
      *((_WORD *)v72[v71] + 277) = *((_WORD *)v7 + 22);
      *v7 = *(_DWORD *)MofData;
      MofData = v88.MofData;
    }
    else if ( *(_DWORD *)v88.MofData != *v7 )
    {
      break;
    }
    v20 = (char *)v12 + 200;
    if ( v19 == 8 )
    {
      v21 = 2;
      do
      {
        *(_OWORD *)v20 = *MofData;
        *((_OWORD *)v20 + 1) = MofData[1];
        *((_OWORD *)v20 + 2) = MofData[2];
        *((_OWORD *)v20 + 3) = MofData[3];
        *((_OWORD *)v20 + 4) = MofData[4];
        *((_OWORD *)v20 + 5) = MofData[5];
        *((_OWORD *)v20 + 6) = MofData[6];
        v22 = MofData[7];
        MofData += 8;
        *((_OWORD *)v20 + 7) = v22;
        v20 += 128;
        --v21;
      }
      while ( v21 );
      *(_OWORD *)v20 = *MofData;
      *((_QWORD *)v20 + 2) = *((_QWORD *)MofData + 2);
      v23 = (wchar_t *)((char *)v88.MofData + 280);
      String1 = (wchar_t *)((char *)v88.MofData + 280);
    }
    else
    {
      EtwpCopyLogHeader((struct _TRACE_LOGFILE_HEADER *)v20, MofData, v19, &String1);
      v23 = String1;
    }
    *((_DWORD *)v12 + 128) = wcscmp_0(v23, L"NT Kernel Logger") == 0;
    *((_DWORD *)v12 + 27) = *((_DWORD *)v12 + 58) & 0xFFFFFEFF;
    v24 = *((unsigned int *)v12 + 50);
    v73 = v24;
    if ( (v24 & 0x3FF) != 0 || (unsigned int)(v24 - 1024) > 0xFFFC00 )
      break;
    v25 = *((_DWORD *)v12 + 53);
    if ( v25 > 0x1000 )
    {
      LastError = 1392;
      goto LABEL_124;
    }
    *((_DWORD *)v12 + 216) = v25;
    if ( HIDWORD(v70) < v7[12] )
    {
      Size = v24;
      v26 = operator new(v24, (const struct std::nothrow_t *)&std::nothrow);
      v82 = v26;
      if ( !v26 )
      {
        operator delete(v7);
        goto LABEL_112;
      }
      memset_0(v26, 0, Size);
      v27 = v73 - HIDWORD(v70);
      memcpy_0(v82, Src, HIDWORD(v70));
      v88.MofData = (char *)v88.MofData + (_BYTE *)v82 - (_BYTE *)Src;
      operator delete(Src);
      Src = v82;
      EtwpSynchReadFile(
        *((HANDLE *)v12 + 78),
        (char *)v82 + HIDWORD(v70),
        v27,
        (unsigned int *)&v70 + 1,
        (struct _OVERLAPPED *)((char *)v72[v71] + 592),
        HIDWORD(v70));
      if ( HIDWORD(v70) != v27 )
        break;
      v7 = (unsigned int *)Src;
      HIDWORD(v70) = v73;
    }
    v28 = *((_BYTE *)v12 + 206);
    if ( v28 > 2u )
    {
      LastError = 777;
      goto LABEL_109;
    }
    if ( a3 )
    {
      if ( (*((_DWORD *)v72[v71] + 8) & 0x100) != 0 )
      {
        v29 = operator new((unsigned int)v70, (const struct std::nothrow_t *)&std::nothrow);
        v30 = v29;
        if ( v29 )
          memset_0(v29, 0, (unsigned int)v70);
        v31 = v72;
        v32 = v71;
        *((_QWORD *)v72[v71] + 80) = v30;
        v33 = (void *)*((_QWORD *)v31[v32] + 80);
        if ( !v33 )
        {
          LastError = 14;
          v60 = 14;
LABEL_115:
          RtlSetLastWin32Error(v60);
          goto LABEL_136;
        }
        memcpy_0(v33, v7 + 18, (unsigned int)v70);
        v34 = v70;
        *((_DWORD *)v72[v71] + 158) = v70;
      }
      else
      {
        v34 = v70;
      }
      SpecialHeaderEvents = EtwpReadSpecialHeaderEvents(v12, (struct _WMI_BUFFER_HEADER *)v7, v34 + 72);
      LastError = SpecialHeaderEvents;
      if ( SpecialHeaderEvents != 1168 && SpecialHeaderEvents )
      {
        v60 = SpecialHeaderEvents;
        goto LABEL_115;
      }
      v36 = v71;
      LastError = 0;
      v66 = 0;
    }
    else
    {
      if ( *((_DWORD *)v12 + 128) && v28 == 1 && *((_BYTE *)v12 + 207) == 2 )
      {
        memset_0(&v85, 0, sizeof(v85));
        v37 = v70 + 72;
        v38 = EtwpGetNextEventOffsetType(v7, (unsigned int)(v70 + 72), &v70);
        if ( !v38 || v37 + (unsigned int)v70 > v7[12] )
        {
LABEL_117:
          LastError = 1392;
          RtlSetLastWin32Error(0x570u);
          goto LABEL_118;
        }
        v66 = EtwpMapEventToEventTrace(0, (char *)v7 + v37, &v85, v38, (struct _WMI_BUFFER_HEADER *)v7);
        LastError = v66;
        if ( !v66 && v85.MofLength >= 0x20 )
          *((_BYTE *)v12 + 764) = (*((_DWORD *)v85.MofData + 1) & 4) != 0;
      }
      v39 = NtQueryInformationFile(
              *((HANDLE *)v12 + 78),
              &IoStatusBlock,
              &FileInformation,
              0x18u,
              FileStandardInformation);
      if ( v39 < 0 )
      {
        LastError = RtlNtStatusToDosError_0(v39);
        v66 = LastError;
        goto LABEL_126;
      }
      v40 = v73;
      v41 = *((_QWORD *)&FileInformation + 1) / (unsigned __int64)v73;
      if ( !*((_QWORD *)v12 + 27) && (*((_DWORD *)v12 + 58) & 0x4000000) == 0 || (v42 = *((_DWORD *)v12 + 59)) == 0 )
      {
        *((_DWORD *)v12 + 59) = v41;
        if ( !(_DWORD)v41 )
          goto LABEL_117;
        v42 = v41;
      }
      *((_DWORD *)v12 + 193) = v42;
      *((_DWORD *)v12 + 192) = *((_DWORD *)v12 + 50);
      if ( (*((_DWORD *)v12 + 58) & 2) != 0 )
      {
        v43 = *((unsigned int *)v12 + 57);
        if ( (_DWORD)v43 )
        {
          v44 = *((_DWORD *)v12 + 60);
          v45 = v43 * ((-(__int64)((*((_DWORD *)v12 + 58) & 0x2000) != 0) & 0xFFFFFFFFFFF00400uLL) + 0x100000);
          v46 = v45 / v40;
          if ( (unsigned int)v46 > (unsigned int)v41 )
            LODWORD(v46) = v41;
          if ( !(_DWORD)v46 )
            LODWORD(v46) = 2;
          if ( (unsigned int)v46 <= v44 || (v47 = *((_DWORD *)v12 + 59), (unsigned int)v46 >= v47) )
            v48 = *((_DWORD *)v12 + 60);
          else
            v48 = v44 + (v47 - v44) % ((unsigned int)v46 - v44);
          *((_DWORD *)v12 + 194) = v44;
          *((_DWORD *)v12 + 195) = v48;
          *((_DWORD *)v12 + 196) = v46;
          if ( v42 > (unsigned int)v46 )
            *((_DWORD *)v12 + 193) = v46;
        }
      }
      v49 = *((_DWORD *)v12 + 118);
      *((_DWORD *)v12 + 9) = v49;
      *((_DWORD *)v12 + 10) = v49;
      *((_QWORD *)v12 + 7) = *((_QWORD *)v12 + 58);
      *((_QWORD *)v12 + 6) = *((_QWORD *)v12 + 57);
      *((_DWORD *)v12 + 11) = *((_DWORD *)v12 + 63);
      EtwpCalculateTimeMultipler(v12);
      v52 = *((_DWORD *)v12 + 58);
      v53 = (v52 & 0x100000) != 0
         || (v52 & 0x400) != 0
         || !*((_QWORD *)v12 + 27) && ((unsigned __int8)v52 & (unsigned __int8)v51) != 0
         || !*((_BYTE *)v12 + 206)
         || *((_BYTE *)v12 + 206) == 1 && *((_BYTE *)v12 + 207) < (unsigned __int8)v51;
      *((_BYTE *)v12 + 765) = v53;
      if ( ((unsigned __int8)v51 & *((_BYTE *)v12 + 32)) != 0 )
      {
        v36 = v71;
        if ( v71 )
        {
          if ( v68 != 1 || v75 != *((_DWORD *)v12 + 9) )
          {
LABEL_119:
            LastError = 87;
LABEL_118:
            v66 = LastError;
LABEL_126:
            if ( v67 == 1 )
            {
              v61 = v80;
              if ( v80 > 1 && (unsigned __int64)(v10 - v9) <= 0xC92A69C000LL )
              {
                v62 = v72;
                v63 = 0;
                do
                {
                  v64 = v62[v63];
                  if ( v64 )
                  {
                    v65 = *((_DWORD *)v64 + 9);
                    if ( ((v65 - 1) & 0xFFFFFFFC) == 0 && v65 != 2 )
                    {
                      *((_QWORD *)v64 + 7) = v9;
                      *((_QWORD *)v64 + 8) = v11;
                    }
                  }
                  v63 = (unsigned int)(v63 + 1);
                }
                while ( (unsigned int)v63 < v61 );
                LastError = v66;
              }
            }
            goto LABEL_136;
          }
        }
        else
        {
          v75 = *((_DWORD *)v12 + 9);
          v68 = 1;
        }
        *((_DWORD *)v12 + 9) = 0;
      }
      else
      {
        if ( v68 == 1 )
          goto LABEL_119;
        v36 = v71;
      }
      v54 = *((_DWORD *)v12 + 9);
      if ( ((v54 - 1) & 0xFFFFFFFC) != 0 || v54 == v51 )
      {
        *((_QWORD *)v12 + 12) = v88.Header.TimeStamp.QuadPart;
      }
      else
      {
        *((_QWORD *)v12 + 8) = v88.Header.TimeStamp.QuadPart;
        *((_QWORD *)v12 + 12) = *((_QWORD *)v12 + 7);
        v88.Header.TimeStamp.QuadPart = *((_QWORD *)v12 + 7);
      }
      if ( !v36 )
      {
        v55 = *(_DWORD *)(v50 + 12);
        v56 = *((_DWORD *)v12 + 9);
        v3 = *((_QWORD *)v12 + 56);
        v9 = *((_QWORD *)v12 + 58);
        v11 = *((_QWORD *)v12 + 8);
        v10 = v9;
        v76 = v55;
        v77 = *((_DWORD *)v12 + 63);
        v78 = *((_DWORD *)v12 + 51);
        v79 = v56;
        v67 = v3 != 0 ? v67 : 0;
        if ( (v56 & 0xFFFFFFFD) != 0 )
          goto LABEL_105;
LABEL_104:
        v67 = 0;
        goto LABEL_105;
      }
      v57 = *((_QWORD *)v12 + 58);
      if ( v57 < v9 )
      {
        v11 = *((_QWORD *)v12 + 8);
        v9 = *((_QWORD *)v12 + 58);
      }
      if ( v57 > v10 )
        v10 = *((_QWORD *)v12 + 58);
      v58 = *((_QWORD *)v12 + 56);
      if ( !v58
        || v3 != v58
        || v76 != *(_DWORD *)(v50 + 12)
        || v77 != *((_DWORD *)v12 + 63)
        || v78 != *((_DWORD *)v12 + 51)
        || v79 != *((_DWORD *)v12 + 9) )
      {
        goto LABEL_104;
      }
    }
LABEL_105:
    v8 = v36 + 1;
    v71 = v8;
    if ( (unsigned int)v8 >= v80 )
      goto LABEL_125;
    v5 = v72;
  }
  LastError = 1392;
  RtlSetLastWin32Error(0x570u);
LABEL_124:
  v66 = LastError;
LABEL_125:
  if ( !a3 )
    goto LABEL_126;
LABEL_136:
  operator delete(Src);
  return LastError;
}

```

## disassembly

```asm
0x1800052b4  push    rbp
0x1800052b6  push    rbx
0x1800052b7  push    rsi
0x1800052b8  push    rdi
0x1800052b9  push    r12
0x1800052bb  push    r13
0x1800052bd  push    r14
0x1800052bf  push    r15
0x1800052c1  lea     rbp, [rsp-0A8h]
0x1800052c9  sub     rsp, 1A8h
0x1800052d0  mov     rax, cs:__security_cookie
0x1800052d7  xor     rax, rsp
0x1800052da  mov     [rbp+0E0h+var_50], rax
0x1800052e1  xor     esi, esi
0x1800052e3  mov     [rsp+1E0h+var_19A], r8b
0x1800052e8  mov     r12d, edx
0x1800052eb  mov     [rbp+0E0h+var_15C], edx
0x1800052ee  mov     r13, rcx
0x1800052f1  mov     [rsp+1E0h+var_188], rcx
0x1800052f6  xor     edx, edx; Val
0x1800052f8  mov     dword ptr [rsp+1E0h+var_198], esi
0x1800052fc  lea     r8d, [rsi+58h]; Size
0x180005300  mov     [rbp+0E0h+String1], rsi
0x180005304  lea     rcx, [rbp+0E0h+var_B0]; void *
0x180005308  mov     dword ptr [rsp+1E0h+var_198+4], esi
0x18000530c  call    memset_0
0x180005311  xorps   xmm0, xmm0
0x180005314  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000531b  xor     eax, eax
0x18000531d  mov     ebx, 1000h
0x180005322  mov     ecx, ebx; unsigned __int64
0x180005324  mov     [rbp+0E0h+var_C0], rax
0x180005328  movups  [rbp+0E0h+FileInformation], xmm0
0x18000532c  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x180005330  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005335  mov     [rsp+1E0h+Src], rax
0x18000533a  mov     r15, rax
0x18000533d  test    rax, rax
0x180005340  jz      loc_180005BB2
0x180005346  mov     r8d, ebx; Size
0x180005349  xor     edx, edx; Val
0x18000534b  mov     rcx, rax; void *
0x18000534e  call    memset_0
0x180005353  xor     r8d, r8d
0x180005356  mov     [rsp+1E0h+var_16C], esi
0x18000535a  mov     [rsp+1E0h+var_168], esi
0x18000535e  mov     edi, esi
0x180005360  mov     [rsp+1E0h+var_164], esi
0x180005364  mov     ebx, esi
0x180005366  mov     [rbp+0E0h+var_160], esi
0x180005369  mov     r14d, esi
0x18000536c  mov     [rsp+1E0h+var_19C], 1
0x180005371  mov     [rsp+1E0h+var_19B], sil
0x180005376  mov     [rsp+1E0h+var_170], esi
0x18000537a  mov     [rsp+1E0h+var_190], r8d
0x18000537f  test    r12d, r12d
0x180005382  jz      loc_180005C40
0x180005388  cmp     [rsp+1E0h+var_19A], 0
0x18000538d  mov     r13, [r13+r8*8+0]
0x180005392  mov     r12d, r8d
0x180005395  jz      short loc_1800053D7
0x180005397  mov     rcx, [r13+50h]; lpFileName
0x18000539b  xor     r9d, r9d; lpSecurityAttributes
0x18000539e  mov     [rsp+1E0h+hTemplateFile], 0; hTemplateFile
0x1800053a7  mov     edx, 80000000h; dwDesiredAccess
0x1800053ac  mov     [rsp+1E0h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1800053b4  mov     [rsp+1E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800053bc  lea     r8d, [r9+7]; dwShareMode
0x1800053c0  call    cs:__imp_CreateFileW
0x1800053c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800053ca  jz      loc_180005B6F
0x1800053d0  mov     [r13+270h], rax
0x1800053d7  xor     edx, edx; Val
0x1800053d9  mov     r8d, 1000h; Size
0x1800053df  mov     rcx, r15; void *
0x1800053e2  call    memset_0
0x1800053e7  mov     rcx, [rsp+1E0h+var_188]
0x1800053ec  lea     r9, [rsp+1E0h+var_198+4]; unsigned int *
0x1800053f1  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], 0; unsigned __int64
0x1800053fa  mov     r8d, 1000h; unsigned int
0x180005400  mov     rdx, r15; void *
0x180005403  mov     rax, [rcx+r12*8]
0x180005407  mov     rcx, [r13+270h]; hFile
0x18000540e  add     rax, 250h
0x180005414  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rax; struct _OVERLAPPED *
0x180005419  call    ?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z; EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)
0x18000541e  cmp     dword ptr [rsp+1E0h+var_198+4], 178h
0x180005426  jb      loc_180005B96
0x18000542c  mov     eax, [r15+30h]
0x180005430  cmp     eax, 48h ; 'H'
0x180005433  jb      loc_180005B96
0x180005439  cmp     eax, [r15]
0x18000543c  ja      loc_180005B96
0x180005442  xor     edx, edx; Val
0x180005444  lea     rcx, [rbp+0E0h+var_B0]; void *
0x180005448  lea     r8d, [rdx+58h]; Size
0x18000544c  call    memset_0
0x180005451  lea     r8, [rsp+1E0h+var_198]
0x180005456  mov     edx, 48h ; 'H'
0x18000545b  mov     rcx, r15
0x18000545e  call    EtwpGetNextEventOffsetType
0x180005463  test    eax, eax
0x180005465  jz      loc_180005B96
0x18000546b  mov     ecx, dword ptr [rsp+1E0h+var_198]
0x18000546f  add     ecx, 48h ; 'H'
0x180005472  cmp     ecx, dword ptr [rsp+1E0h+var_198+4]
0x180005476  ja      loc_180005B96
0x18000547c  lea     rdx, [r15+48h]; void *
0x180005480  mov     qword ptr [rsp+1E0h+dwCreationDisposition], r15; struct _WMI_BUFFER_HEADER *
0x180005485  mov     r9d, eax; unsigned int
0x180005488  lea     r8, [rbp+0E0h+var_B0]; struct _EVENT_TRACE *
0x18000548c  xor     ecx, ecx; struct _TRACELOG_CONTEXT *
0x18000548e  call    ?EtwpMapEventToEventTrace@@YAKPEAU_TRACELOG_CONTEXT@@PEAXPEAU_EVENT_TRACE@@KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpMapEventToEventTrace(_TRACELOG_CONTEXT *,void *,_EVENT_TRACE *,ulong,_WMI_BUFFER_HEADER *)
0x180005493  mov     [rsp+1E0h+var_1A0], eax
0x180005497  mov     r12d, eax
0x18000549a  test    eax, eax
0x18000549c  jnz     loc_180005B96
0x1800054a2  cmp     [rbp+0E0h+var_B0.MofLength], 30h ; '0'
0x1800054a9  jb      loc_180005B96
0x1800054af  mov     eax, dword ptr [rsp+1E0h+var_198]
0x1800054b3  add     eax, 48h ; 'H'
0x1800054b6  cmp     eax, 1000h
0x1800054bb  ja      loc_180005B96
0x1800054c1  mov     rdx, [rbp+0E0h+var_B0.MofData]; void *
0x1800054c5  mov     r8d, [rdx+2Ch]; unsigned int
0x1800054c9  lea     ecx, [r8-4]
0x1800054cd  test    ecx, 0FFFFFFFBh
0x1800054d3  jnz     loc_180005B96
0x1800054d9  test    dword ptr [rdx+20h], 4000000h
0x1800054e0  jz      short loc_180005527
0x1800054e2  test    byte ptr [r15+34h], 40h
0x1800054e7  jnz     loc_180005B96
0x1800054ed  test    byte ptr [rdx+20h], 2
0x1800054f1  jnz     loc_180005B96
0x1800054f7  mov     eax, [rdx]
0x1800054f9  cmp     [r15], eax
0x1800054fc  ja      loc_180005B7D
0x180005502  movzx   eax, word ptr [r15+2Ch]
0x180005507  mov     r9d, [rsp+1E0h+var_190]
0x18000550c  mov     rcx, [rsp+1E0h+var_188]
0x180005511  mov     rcx, [rcx+r9*8]
0x180005515  mov     [rcx+22Ah], ax
0x18000551c  mov     eax, [rdx]
0x18000551e  mov     [r15], eax
0x180005521  mov     rdx, [rbp+0E0h+var_B0.MofData]
0x180005525  jmp     short loc_180005532
0x180005527  mov     eax, [r15]
0x18000552a  cmp     [rdx], eax
0x18000552c  jnz     loc_180005B96
0x180005532  lea     rax, [r13+0C8h]
0x180005539  mov     rcx, rax; struct _TRACE_LOGFILE_HEADER *
0x18000553c  cmp     r8d, 8
0x180005540  jnz     short loc_1800055B3
0x180005542  lea     eax, [r8-6]
0x180005546  lea     r8d, [rax+7Eh]
0x18000554a  movups  xmm0, xmmword ptr [rdx]
0x18000554d  movups  xmmword ptr [rcx], xmm0
0x180005550  movups  xmm1, xmmword ptr [rdx+10h]
0x180005554  movups  xmmword ptr [rcx+10h], xmm1
0x180005558  movups  xmm0, xmmword ptr [rdx+20h]
0x18000555c  movups  xmmword ptr [rcx+20h], xmm0
0x180005560  movups  xmm1, xmmword ptr [rdx+30h]
0x180005564  movups  xmmword ptr [rcx+30h], xmm1
0x180005568  movups  xmm0, xmmword ptr [rdx+40h]
0x18000556c  movups  xmmword ptr [rcx+40h], xmm0
0x180005570  movups  xmm1, xmmword ptr [rdx+50h]
0x180005574  movups  xmmword ptr [rcx+50h], xmm1
0x180005578  movups  xmm0, xmmword ptr [rdx+60h]
0x18000557c  movups  xmmword ptr [rcx+60h], xmm0
0x180005580  movups  xmm1, xmmword ptr [rdx+70h]
0x180005584  add     rdx, r8
0x180005587  movups  xmmword ptr [rcx+70h], xmm1
0x18000558b  add     rcx, r8
0x18000558e  sub     rax, 1
0x180005592  jnz     short loc_18000554A
0x180005594  movups  xmm0, xmmword ptr [rdx]
0x180005597  movups  xmmword ptr [rcx], xmm0
0x18000559a  mov     rax, [rdx+10h]
0x18000559e  mov     [rcx+10h], rax
0x1800055a2  mov     rcx, [rbp+0E0h+var_B0.MofData]
0x1800055a6  add     rcx, 118h
0x1800055ad  mov     [rbp+0E0h+String1], rcx
0x1800055b1  jmp     short loc_1800055C0
0x1800055b3  lea     r9, [rbp+0E0h+String1]; unsigned __int16 **
0x1800055b7  call    ?EtwpCopyLogHeader@@YAXPEAU_TRACE_LOGFILE_HEADER@@PEAXKPEAPEAG@Z; EtwpCopyLogHeader(_TRACE_LOGFILE_HEADER *,void *,ulong,ushort * *)
0x1800055bc  mov     rcx, [rbp+0E0h+String1]; String1
0x1800055c0  lea     rdx, aNtKernelLogger_0; "NT Kernel Logger"
0x1800055c7  call    wcscmp_0
0x1800055cc  xor     ecx, ecx
0x1800055ce  lea     rdx, [r13+0C8h]
0x1800055d5  test    eax, eax
0x1800055d7  setz    cl
0x1800055da  mov     [r13+200h], ecx
0x1800055e1  mov     eax, [rdx+20h]
0x1800055e4  btr     eax, 8
0x1800055e8  mov     [r13+6Ch], eax
0x1800055ec  mov     ecx, [rdx]; unsigned __int64
0x1800055ee  mov     [rsp+1E0h+var_180], ecx
0x1800055f2  test    ecx, 3FFh
0x1800055f8  jnz     loc_180005B96
0x1800055fe  lea     eax, [rcx-400h]
0x180005604  cmp     eax, 0FFFC00h
0x180005609  ja      loc_180005B96
0x18000560f  mov     eax, [rdx+0Ch]
0x180005612  cmp     eax, 1000h
0x180005617  ja      loc_180005C38
0x18000561d  mov     [r13+360h], eax
0x180005624  mov     eax, [r15+30h]
0x180005628  cmp     dword ptr [rsp+1E0h+var_198+4], eax
0x18000562c  jnb     loc_1800056EA
0x180005632  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005639  mov     [rbp+0E0h+Size], rcx
0x18000563d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005642  mov     [rbp+0E0h+var_150], rax
0x180005646  test    rax, rax
0x180005649  jz      loc_180005BAA
0x18000564f  mov     r8, [rbp+0E0h+Size]; Size
0x180005653  xor     edx, edx; Val
0x180005655  mov     rcx, rax; void *
0x180005658  call    memset_0
0x18000565d  mov     r15d, [rsp+1E0h+var_180]
0x180005662  mov     r8d, dword ptr [rsp+1E0h+var_198+4]; Size
0x180005667  mov     rdx, [rsp+1E0h+Src]; Src
0x18000566c  mov     rcx, [rbp+0E0h+var_150]; void *
0x180005670  sub     r15d, dword ptr [rsp+1E0h+var_198+4]
0x180005675  call    memcpy_0
0x18000567a  mov     rcx, [rsp+1E0h+Src]; Block
0x18000567f  mov     rax, [rbp+0E0h+var_150]
0x180005683  sub     rax, rcx
0x180005686  add     [rbp+0E0h+var_B0.MofData], rax
0x18000568a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000568f  mov     r8, [rsp+1E0h+var_188]
0x180005694  mov     eax, dword ptr [rsp+1E0h+var_198+4]
0x180005698  mov     r9d, [rsp+1E0h+var_190]
0x18000569d  mov     rdx, [rbp+0E0h+var_150]
0x1800056a1  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rax; unsigned __int64
0x1800056a6  mov     [rsp+1E0h+Src], rdx
0x1800056ab  add     rdx, rax; void *
0x1800056ae  mov     rcx, [r8+r9*8]
0x1800056b2  lea     r9, [rsp+1E0h+var_198+4]; unsigned int *
0x1800056b7  add     rcx, 250h
0x1800056be  mov     r8d, r15d; unsigned int
0x1800056c1  mov     qword ptr [rsp+1E0h+dwCreationDisposition], rcx; struct _OVERLAPPED *
0x1800056c6  mov     rcx, [r13+270h]; hFile
0x1800056cd  call    ?EtwpSynchReadFile@@YAHPEAX0KPEAKPEAU_OVERLAPPED@@_K@Z; EtwpSynchReadFile(void *,void *,ulong,ulong *,_OVERLAPPED *,unsigned __int64)
0x1800056d2  cmp     dword ptr [rsp+1E0h+var_198+4], r15d
0x1800056d7  jnz     loc_180005B96
0x1800056dd  mov     eax, [rsp+1E0h+var_180]
0x1800056e1  mov     r15, [rsp+1E0h+Src]
0x1800056e6  mov     dword ptr [rsp+1E0h+var_198+4], eax
0x1800056ea  mov     al, [r13+0CEh]
0x1800056f1  mov     ecx, 2
0x1800056f6  cmp     al, cl
0x1800056f8  ja      loc_180005C2D
0x1800056fe  cmp     [rsp+1E0h+var_19A], 0
0x180005703  jz      loc_1800057CE
0x180005709  mov     edx, [rsp+1E0h+var_190]
0x18000570d  mov     rcx, [rsp+1E0h+var_188]
0x180005712  mov     rax, [rcx+rdx*8]
0x180005716  test    dword ptr [rax+20h], 100h
0x18000571d  jz      short loc_180005797
0x18000571f  mov     ecx, dword ptr [rsp+1E0h+var_198]; unsigned __int64
0x180005723  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000572a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000572f  mov     r12, rax
0x180005732  test    rax, rax
0x180005735  jz      short loc_180005746
0x180005737  mov     r8d, dword ptr [rsp+1E0h+var_198]; Size
0x18000573c  xor     edx, edx; Val
0x18000573e  mov     rcx, rax; void *
0x180005741  call    memset_0
0x180005746  mov     ecx, [rsp+1E0h+var_190]
0x18000574a  mov     rdx, [rsp+1E0h+var_188]
0x18000574f  mov     eax, ecx
0x180005751  mov     rcx, [rdx+rcx*8]
0x180005755  mov     [rcx+280h], r12
0x18000575c  mov     rax, [rdx+rax*8]
0x180005760  mov     rcx, [rax+280h]; void *
0x180005767  test    rcx, rcx
0x18000576a  jz      loc_180005BE7
0x180005770  mov     r8d, dword ptr [rsp+1E0h+var_198]; Size
0x180005775  lea     rdx, [r15+48h]; Src
0x180005779  call    memcpy_0
0x18000577e  mov     edx, [rsp+1E0h+var_190]
0x180005782  mov     r8, [rsp+1E0h+var_188]
0x180005787  mov     ecx, dword ptr [rsp+1E0h+var_198]
0x18000578b  mov     rax, [r8+rdx*8]
0x18000578f  mov     [rax+278h], ecx
0x180005795  jmp     short loc_18000579B
0x180005797  mov     ecx, dword ptr [rsp+1E0h+var_198]
0x18000579b  lea     r8d, [rcx+48h]; unsigned int
0x18000579f  mov     rdx, r15; struct _WMI_BUFFER_HEADER *
0x1800057a2  mov     rcx, r13; struct _TRACELOG_CONTEXT *
0x1800057a5  call    ?EtwpReadSpecialHeaderEvents@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@K@Z; EtwpReadSpecialHeaderEvents(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *,ulong)
0x1800057aa  mov     r12d, eax
0x1800057ad  cmp     eax, 490h
0x1800057b2  jz      short loc_1800057BC
0x1800057b4  test    eax, eax
0x1800057b6  jnz     loc_180005BFB
0x1800057bc  mov     r8d, [rsp+1E0h+var_190]
  ... truncated ...
```
