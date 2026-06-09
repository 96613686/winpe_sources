# CreateDriverEntry(_INIENVIRONMENT *,_INIVERSION *,ulong,uchar *,ulong,_INISPOOLER *,_INTERNAL_DRV_FILE *,ulong,ulong,_INIDRIVER *)

- ea: `0x18006b71c`
- end: `0x18006c1ba`
- name: `?CreateDriverEntry@@YAPEAU_INIDRIVER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@KPEAEKPEAU_INISPOOLER@@PEAU_INTERNAL_DRV_FILE@@KKPEAU1@@Z`
- size: `2718`
- prototype: `struct _INIDRIVER *__fastcall(struct _INIENVIRONMENT *, struct _INIVERSION *, unsigned int, unsigned __int8 *, char, struct _INISPOOLER *, struct _INTERNAL_DRV_FILE *, unsigned int, unsigned int, struct _INIDRIVER *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ab60`

## callees

- `0x18000c424`
- `0x18000d944`
- `0x18001de10`
- `0x180033734`
- `0x1800343ac`
- `0x18003ea2c`
- `0x18003fd40`
- `0x180047318`
- `0x18006aa20`
- `0x18006b71c`
- `0x18006d430`
- `0x18006e330`
- `0x18006fb94`
- `0x18007342c`
- `0x18007405c`
- `0x1800caa78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b8e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b8e1`
- `SPOOLSS!DllFreeSplStr` at `0x18006b78e`
- `SPOOLSS!DllFreeSplStr` at `0x18006b79b`
- `SPOOLSS!DllFreeSplStr` at `0x18006b7a8`
- `SPOOLSS!DllFreeSplStr` at `0x18006b78e`
- `SPOOLSS!DllFreeSplStr` at `0x18006b79b`
- `SPOOLSS!DllFreeSplStr` at `0x18006b7a8`
- `SPOOLSS!DllFreeSplMem` at `0x18006c199`
- `SPOOLSS!DllFreeSplMem` at `0x18006c199`
- `SPOOLSS!DllAllocSplMem` at `0x18006b75c`
- `SPOOLSS!DllAllocSplMem` at `0x18006bbbd`
- `SPOOLSS!DllAllocSplMem` at `0x18006be66`
- `SPOOLSS!DllAllocSplMem` at `0x18006bf30`
- `SPOOLSS!DllAllocSplMem` at `0x18006b75c`
- `SPOOLSS!DllAllocSplMem` at `0x18006bbbd`
- `SPOOLSS!DllAllocSplMem` at `0x18006be66`
- `SPOOLSS!DllAllocSplMem` at `0x18006bf30`

## string_xrefs

- `0x18006b9ba`: `CreateDriverEntry`

## pseudocode

```c
struct _INIDRIVER *__fastcall CreateDriverEntry(
        struct _INIENVIRONMENT *a1,
        struct _INIVERSION *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        char a5,
        struct _INISPOOLER *a6,
        struct _INTERNAL_DRV_FILE *a7,
        unsigned int a8,
        unsigned int a9,
        struct _INIDRIVER *a10)
{
  struct _INIENVIRONMENT *v10; // r12
  __int64 v11; // r14
  struct _INIVERSION *v14; // r13
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  struct _INIDRIVER *result; // rax
  struct _INIDRIVER *v18; // rdi
  __int64 v19; // rdx
  _OWORD *v20; // rcx
  struct _INIDRIVER *v21; // rax
  __int128 v22; // xmm1
  int FileName; // eax
  __int64 v24; // r14
  int v25; // eax
  __int64 v26; // r14
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rdx
  int v30; // ecx
  int v31; // r14d
  const unsigned __int16 *v32; // rax
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r13
  int v40; // eax
  __int64 v41; // r12
  __int64 v42; // rcx
  unsigned int MultiSZLen; // eax
  __int64 v44; // r14
  void *v45; // rax
  int i; // r8d
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // r14
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  unsigned int v65; // eax
  __int64 v66; // r14
  void *v67; // rax
  int j; // r8d
  int v69; // eax
  __int64 v70; // r8
  __int64 v71; // rdx
  unsigned int v72; // eax
  __int64 v73; // r14
  void *v74; // rax
  int k; // r8d
  int v76; // eax
  const unsigned __int16 **v77; // r14
  __int64 v78; // r8
  __int64 v79; // rdx
  struct _INISPOOLER *v80; // rsi
  struct _INIDRIVER *v81; // [rsp+20h] [rbp-40h]
  struct _INIDRIVER *v82; // [rsp+20h] [rbp-40h]
  unsigned int v83; // [rsp+28h] [rbp-38h]
  unsigned int v84; // [rsp+28h] [rbp-38h]
  struct _INISPOOLER *v85; // [rsp+30h] [rbp-30h]
  struct _INIVERSION *v86; // [rsp+38h] [rbp-28h]
  unsigned int v87[4]; // [rsp+50h] [rbp-10h] BYREF
  int v90; // [rsp+B8h] [rbp+58h] BYREF

  v10 = a1;
  v87[0] = 1;
  LODWORD(v11) = 0;
  v90 = 0;
  v14 = a2;
  v15 = (_DWORD *)DllAllocSplMem(312);
  v16 = v15;
  if ( !v15 )
    return 0;
  v18 = a10;
  *v15 = 17476;
  if ( v18 )
  {
    DllFreeSplStr(*((_QWORD *)v18 + 33));
    DllFreeSplStr(*((_QWORD *)v18 + 35));
    DllFreeSplStr(*((_QWORD *)v18 + 37));
    *((_DWORD *)v18 + 72) = 0;
    *((_QWORD *)v18 + 33) = 0;
    *((_QWORD *)v18 + 35) = 0;
    *((_QWORD *)v18 + 37) = 0;
    UpdateDriverFileRefCnt(v10, v14, v18, 0, 0, 0);
    v19 = 2;
    v20 = v16;
    v21 = v18;
    do
    {
      *v20 = *(_OWORD *)v21;
      v20[1] = *((_OWORD *)v21 + 1);
      v20[2] = *((_OWORD *)v21 + 2);
      v20[3] = *((_OWORD *)v21 + 3);
      v20[4] = *((_OWORD *)v21 + 4);
      v20[5] = *((_OWORD *)v21 + 5);
      v20[6] = *((_OWORD *)v21 + 6);
      v22 = *((_OWORD *)v21 + 7);
      v21 = (struct _INIDRIVER *)((char *)v21 + 128);
      v20[7] = v22;
      v20 += 8;
      --v19;
    }
    while ( v19 );
    *v20 = *(_OWORD *)v21;
    v20[1] = *((_OWORD *)v21 + 1);
    v20[2] = *((_OWORD *)v21 + 2);
    *((_QWORD *)v20 + 6) = *((_QWORD *)v21 + 6);
  }
  v16[59] = *((_DWORD *)v14 + 8);
  v16[60] = a9;
  v16[76] = OsVersionInfoEx.dwBuildNumber;
  if ( v18 )
    v11 = *((_QWORD *)v18 + 4);
  FileName = FindFileName(*(_QWORD *)a7);
  AllocOrUpdateStringAndTestSame((_DWORD)v16 + 32, FileName, v11, 0, (__int64)&v90, (__int64)v87);
  CheckDriverAttributes(a6, v10, v14, (struct _INIDRIVER *)v16, (const unsigned __int16 *)v81, v83);
  if ( v16[58] == 1 )
  {
    v90 = 1;
    SetLastError(0x78Au);
  }
  else
  {
    v90 = 0;
  }
  if ( a8 > 1 )
  {
    if ( v18 )
      v24 = *((_QWORD *)v18 + 5);
    else
      LODWORD(v24) = 0;
    v25 = FindFileName(*((_QWORD *)a7 + 4));
    AllocOrUpdateStringAndTestSame((_DWORD)v16 + 40, v25, v24, 0, (__int64)&v90, (__int64)v87);
  }
  if ( a8 > 2 )
  {
    if ( v18 )
      v26 = *((_QWORD *)v18 + 6);
    else
      LODWORD(v26) = 0;
    v27 = FindFileName(*((_QWORD *)a7 + 8));
    AllocOrUpdateStringAndTestSame((_DWORD)v16 + 48, v27, v26, 0, (__int64)&v90, (__int64)v87);
  }
  v16[65] = 1;
  switch ( a3 )
  {
    case 2u:
      if ( v18 )
        v78 = *((_QWORD *)v18 + 3);
      else
        LODWORD(v78) = 0;
      v79 = *((_QWORD *)a4 + 1);
      v77 = (const unsigned __int16 **)(v16 + 6);
      LODWORD(a10) = 0;
      AllocOrUpdateStringAndTestSame((_DWORD)v16 + 24, v79, v78, 0, (__int64)&v90, (__int64)&a10);
      *((_QWORD *)v16 + 13) = 0;
      *((_QWORD *)v16 + 11) = 0;
      *((_QWORD *)v16 + 10) = 0;
      *((_QWORD *)v16 + 9) = 0;
      *((_QWORD *)v16 + 7) = 0;
      v16[24] = 0;
      v16[16] = 0;
      goto LABEL_125;
    case 3u:
    case 4u:
      *((_QWORD *)v16 + 16) = 0;
      *((_QWORD *)v16 + 17) = 0;
      *((_QWORD *)v16 + 18) = 0;
      *((_QWORD *)v16 + 19) = 0;
      goto LABEL_30;
    case 6u:
LABEL_30:
      *((_QWORD *)v16 + 20) = 0;
      *((_QWORD *)v16 + 21) = 0;
      v16[44] = 0;
      *((_QWORD *)v16 + 23) = 0;
      *((_QWORD *)v16 + 24) = 0;
      *((_QWORD *)v16 + 25) = 0;
      *((_QWORD *)v16 + 26) = 0;
      *((_QWORD *)v16 + 27) = 0;
      *((_QWORD *)v16 + 28) = 0;
      goto LABEL_31;
  }
  if ( a3 != 8 )
  {
    if ( a3 != 101 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError("CreateDriverEntry", L"Invalid level %d", a3);
      return 0;
    }
    goto LABEL_30;
  }
LABEL_31:
  if ( v18 )
    v28 = *((_QWORD *)v18 + 3);
  else
    LODWORD(v28) = 0;
  v29 = *((_QWORD *)a4 + 1);
  LODWORD(a10) = 0;
  AllocOrUpdateStringAndTestSame((_DWORD)v16 + 24, v29, v28, 0, (__int64)&v90, (__int64)&a10);
  if ( !v87[0] || (v30 = 1, (a5 & 8) == 0) )
    v30 = 0;
  v31 = v90;
  if ( !v90 )
  {
    if ( v18 )
      v32 = (const unsigned __int16 *)*((_QWORD *)v18 + 7);
    else
      v32 = 0;
    if ( !(unsigned int)SetDependentFilesCommon(a3, a4, a7, a8, (struct _INIDRIVER *)v16, v10, v85, v86, v32, v30) )
      v31 = 1;
    v90 = v31;
  }
  if ( v18 )
    v33 = *((_QWORD *)v18 + 10);
  else
    LODWORD(v33) = 0;
  v34 = 40;
  if ( a3 != 101 )
    v34 = 64;
  v35 = *(_QWORD *)&a4[v34];
  LODWORD(a10) = 0;
  AllocOrUpdateStringAndTestSame((_DWORD)v16 + 80, v35, v33, 0, (__int64)&v90, (__int64)&a10);
  if ( v18 )
    v36 = *((_QWORD *)v18 + 11);
  else
    LODWORD(v36) = 0;
  v37 = 48;
  if ( a3 != 101 )
    v37 = 72;
  v38 = *(_QWORD *)&a4[v37];
  LODWORD(a10) = 0;
  AllocOrUpdateStringAndTestSame((_DWORD)v16 + 88, v38, v36, 0, (__int64)&v90, (__int64)&a10);
  v16[24] = 0;
  v39 = 80;
  if ( a3 <= 8 && (v40 = 336, _bittest(&v40, a3)) || a3 == 101 )
  {
    v41 = 56;
    v42 = 56;
    if ( a3 != 101 )
      v42 = 80;
    MultiSZLen = GetMultiSZLen(*(_QWORD *)&a4[v42], 0);
    v44 = MultiSZLen;
    v16[24] = MultiSZLen;
    if ( MultiSZLen )
    {
      v45 = (void *)DllAllocSplMem(2 * MultiSZLen);
      *((_QWORD *)v16 + 13) = v45;
      if ( v45 )
      {
        if ( a3 != 101 )
          v41 = 80;
        memcpy_0(v45, *(const void **)&a4[v41], 2 * v44);
        for ( i = 0; i < 2; ++i )
        {
          v47 = v44 - i;
          *(_WORD *)(*((_QWORD *)v16 + 13) + 2LL * (unsigned int)(v47 - 1)) = 0;
        }
      }
      else
      {
        v90 = 1;
      }
    }
    else
    {
      *((_QWORD *)v16 + 13) = 0;
    }
    if ( ((a3 - 6) & 0xFFFFFFFD) == 0 || a3 == 101 )
    {
      if ( v18 )
        v48 = *((_QWORD *)v18 + 16);
      else
        LODWORD(v48) = 0;
      v49 = 104;
      if ( a3 != 101 )
        v39 = 104;
      v50 = *(_QWORD *)&a4[v39];
      LODWORD(a10) = 0;
      AllocOrUpdateStringAndTestSame((_DWORD)v16 + 128, v50, v48, 0, (__int64)&v90, (__int64)&a10);
      if ( v18 )
        v51 = *((_QWORD *)v18 + 17);
      else
        LODWORD(v51) = 0;
      v52 = 88;
      if ( a3 != 101 )
        v52 = 112;
      v53 = *(_QWORD *)&a4[v52];
      LODWORD(a10) = 0;
      AllocOrUpdateStringAndTestSame((_DWORD)v16 + 136, v53, v51, 0, (__int64)&v90, (__int64)&a10);
      if ( v18 )
        v54 = *((_QWORD *)v18 + 18);
      else
        LODWORD(v54) = 0;
      v55 = 96;
      if ( a3 != 101 )
        v55 = 120;
      v56 = *(_QWORD *)&a4[v55];
      LODWORD(a10) = 0;
      AllocOrUpdateStringAndTestSame((_DWORD)v16 + 144, v56, v54, 0, (__int64)&v90, (__int64)&a10);
      if ( v18 )
        v57 = *((_QWORD *)v18 + 19);
      else
        LODWORD(v57) = 0;
      if ( a3 != 101 )
        v49 = 128;
      v58 = *(_QWORD *)&a4[v49];
      LODWORD(a10) = 0;
      AllocOrUpdateStringAndTestSame((_DWORD)v16 + 152, v58, v57, 0, (__int64)&v90, (__int64)&a10);
      v59 = 72;
      if ( a3 != 101 )
        v59 = 96;
      *((_QWORD *)v16 + 15) = *(_QWORD *)&a4[v59];
      v60 = 64;
      if ( a3 != 101 )
        v60 = 88;
      *((_QWORD *)v16 + 14) = *(_QWORD *)&a4[v60];
    }
  }
  v16[44] = 0;
  v16[51] = 0;
  if ( a3 == 8 )
  {
    v16[50] = *((_DWORD *)a4 + 42);
    if ( v18 )
      v61 = *((_QWORD *)v18 + 20);
    else
      LODWORD(v61) = 0;
    v62 = *((_QWORD *)a4 + 17);
    LODWORD(a10) = 0;
    AllocOrUpdateStringAndTestSame((_DWORD)v16 + 160, v62, v61, 0, (__int64)&v90, (__int64)&a10);
    if ( v18 )
      v63 = *((_QWORD *)v18 + 21);
    else
      LODWORD(v63) = 0;
    v64 = *((_QWORD *)a4 + 18);
    LODWORD(a10) = 0;
    AllocOrUpdateStringAndTestSame((_DWORD)v16 + 168, v64, v63, 0, (__int64)&v90, (__int64)&a10);
    v65 = GetMultiSZLen(*((_QWORD *)a4 + 19), 0);
    v66 = v65;
    v16[44] = v65;
    if ( v65 )
    {
      v67 = (void *)DllAllocSplMem(2 * v65);
      *((_QWORD *)v16 + 23) = v67;
      if ( v67 )
      {
        memcpy_0(v67, *((const void **)a4 + 19), 2 * v66);
        for ( j = 0; j < 2; ++j )
        {
          v69 = v66 - j;
          *(_WORD *)(*((_QWORD *)v16 + 23) + 2LL * (unsigned int)(v69 - 1)) = 0;
        }
      }
      else
      {
        v90 = 1;
      }
    }
    else
    {
      *((_QWORD *)v16 + 23) = 0;
    }
    if ( v18 )
      v70 = *((_QWORD *)v18 + 24);
    else
      LODWORD(v70) = 0;
    v71 = *((_QWORD *)a4 + 20);
    LODWORD(a10) = 0;
    AllocOrUpdateStringAndTestSame((_DWORD)v16 + 192, v71, v70, 0, (__int64)&v90, (__int64)&a10);
    v72 = GetMultiSZLen(*((_QWORD *)a4 + 22), 0);
    v73 = v72;
    v16[51] = v72;
    if ( v72 )
    {
      v74 = (void *)DllAllocSplMem(2 * v72);
      *((_QWORD *)v16 + 26) = v74;
      if ( v74 )
      {
        memcpy_0(v74, *((const void **)a4 + 22), 2 * v73);
        for ( k = 0; k < 2; ++k )
        {
          v76 = v73 - k;
          *(_WORD *)(*((_QWORD *)v16 + 26) + 2LL * (unsigned int)(v76 - 1)) = 0;
        }
      }
      else
      {
        v90 = 1;
      }
    }
    else
    {
      *((_QWORD *)v16 + 26) = 0;
    }
    *((_QWORD *)v16 + 27) = *((_QWORD *)a4 + 23);
    *((_QWORD *)v16 + 28) = *((_QWORD *)a4 + 24);
  }
  v14 = a2;
  v77 = (const unsigned __int16 **)(v16 + 6);
  v10 = a1;
LABEL_125:
  if ( v90 || !(unsigned int)UpdateDriverFileRefCnt(v10, v14, (struct _INIDRIVER *)v16, 0, 0, 1) )
    goto LABEL_137;
  UpdateDriverFileVersion(v14, a7, a8);
  v80 = a6;
  CheckDriverAttributes(a6, v10, v14, (struct _INIDRIVER *)v16, (const unsigned __int16 *)v82, v84);
  CheckXpsDriver((struct _INIDRIVER *)v16);
  if ( (unsigned int)IsMUDDriver(*v77) )
    v16[50] |= 0x20u;
  if ( (unsigned int)WriteDriverIniInternal((struct _INIDRIVER *)v16, v14, v10, v80, 0) )
  {
    if ( !v18 )
    {
      result = (struct _INIDRIVER *)v16;
      *((_QWORD *)v16 + 1) = *((_QWORD *)v14 + 6);
      *((_QWORD *)v14 + 6) = v16;
      return result;
    }
    CopyNewOffsets(v18, v16);
    if ( *((_DWORD *)v18 + 60) && !a9 )
      RemoveDriverTempFiles(v80, v10, v14, v18);
    *((_DWORD *)v18 + 59) = v16[59];
    *((_DWORD *)v18 + 58) = v16[58];
    *((_DWORD *)v18 + 16) = v16[16];
    *((_DWORD *)v18 + 60) = v16[60];
    *((_DWORD *)v18 + 24) = v16[24];
    *((_DWORD *)v18 + 44) = v16[44];
    *((_DWORD *)v18 + 51) = v16[51];
    *((_DWORD *)v18 + 50) = v16[50];
    *((_QWORD *)v18 + 28) = *((_QWORD *)v16 + 28);
    *((_QWORD *)v18 + 27) = *((_QWORD *)v16 + 27);
    *((_DWORD *)v18 + 76) = v16[76];
    if ( ((a3 - 6) & 0xFFFFFFFD) == 0 )
    {
      *((_QWORD *)v18 + 15) = *((_QWORD *)v16 + 15);
      *((_QWORD *)v18 + 14) = *((_QWORD *)v16 + 14);
    }
  }
  else
  {
LABEL_137:
    FreeStructurePointers(v16, v18, IniDriverOffsets);
    v18 = 0;
  }
  DllFreeSplMem(v16);
  return v18;
}

```

## disassembly

```asm
0x18006b71c  mov     [rsp-38h+arg_10], rbx
0x18006b721  mov     [rsp-38h+arg_8], rdx
0x18006b726  mov     [rsp-38h+arg_0], rcx
0x18006b72b  push    rbp
0x18006b72c  push    rsi
0x18006b72d  push    rdi
0x18006b72e  push    r12
0x18006b730  push    r13
0x18006b732  push    r14
0x18006b734  push    r15
0x18006b736  mov     rbp, rsp
0x18006b739  sub     rsp, 60h
0x18006b73d  mov     r12, rcx
0x18006b740  mov     [rbp+var_10], 1
0x18006b747  xor     r14d, r14d
0x18006b74a  mov     ecx, 138h
0x18006b74f  mov     [rbp+arg_18], r14d
0x18006b753  mov     rsi, r9
0x18006b756  mov     r15d, r8d
0x18006b759  mov     r13, rdx
0x18006b75c  call    cs:__imp_DllAllocSplMem
0x18006b762  mov     rbx, rax
0x18006b765  test    rax, rax
0x18006b768  jnz     short loc_18006B771
0x18006b76a  xor     eax, eax
0x18006b76c  jmp     loc_18006C1A2
0x18006b771  mov     rdi, [rbp+arg_48]
0x18006b778  mov     dword ptr [rax], 4444h
0x18006b77e  test    rdi, rdi
0x18006b781  jz      loc_18006B85C
0x18006b787  mov     rcx, [rdi+108h]
0x18006b78e  call    cs:__imp_DllFreeSplStr
0x18006b794  mov     rcx, [rdi+118h]
0x18006b79b  call    cs:__imp_DllFreeSplStr
0x18006b7a1  mov     rcx, [rdi+128h]
0x18006b7a8  call    cs:__imp_DllFreeSplStr
0x18006b7ae  xor     r9d, r9d; unsigned __int16 *
0x18006b7b1  mov     dword ptr [rsp+60h+var_38], r14d; int
0x18006b7b6  mov     r8, rdi; struct _INIDRIVER *
0x18006b7b9  mov     [rdi+120h], r14d
0x18006b7c0  mov     rdx, r13; struct _INIVERSION *
0x18006b7c3  mov     [rdi+108h], r14
0x18006b7ca  mov     rcx, r12; struct _INIENVIRONMENT *
0x18006b7cd  mov     [rdi+118h], r14
0x18006b7d4  mov     [rdi+128h], r14
0x18006b7db  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x18006b7e0  call    UpdateDriverFileRefCnt
0x18006b7e5  mov     edx, 2
0x18006b7ea  mov     rcx, rbx
0x18006b7ed  mov     rax, rdi
0x18006b7f0  lea     r8d, [rdx+7Eh]
0x18006b7f4  movups  xmm0, xmmword ptr [rax]
0x18006b7f7  movups  xmmword ptr [rcx], xmm0
0x18006b7fa  movups  xmm1, xmmword ptr [rax+10h]
0x18006b7fe  movups  xmmword ptr [rcx+10h], xmm1
0x18006b802  movups  xmm0, xmmword ptr [rax+20h]
0x18006b806  movups  xmmword ptr [rcx+20h], xmm0
0x18006b80a  movups  xmm1, xmmword ptr [rax+30h]
0x18006b80e  movups  xmmword ptr [rcx+30h], xmm1
0x18006b812  movups  xmm0, xmmword ptr [rax+40h]
0x18006b816  movups  xmmword ptr [rcx+40h], xmm0
0x18006b81a  movups  xmm1, xmmword ptr [rax+50h]
0x18006b81e  movups  xmmword ptr [rcx+50h], xmm1
0x18006b822  movups  xmm0, xmmword ptr [rax+60h]
0x18006b826  movups  xmmword ptr [rcx+60h], xmm0
0x18006b82a  movups  xmm1, xmmword ptr [rax+70h]
0x18006b82e  add     rax, r8
0x18006b831  movups  xmmword ptr [rcx+70h], xmm1
0x18006b835  add     rcx, r8
0x18006b838  sub     rdx, 1
0x18006b83c  jnz     short loc_18006B7F4
0x18006b83e  movups  xmm0, xmmword ptr [rax]
0x18006b841  movups  xmmword ptr [rcx], xmm0
0x18006b844  movups  xmm1, xmmword ptr [rax+10h]
0x18006b848  movups  xmmword ptr [rcx+10h], xmm1
0x18006b84c  movups  xmm0, xmmword ptr [rax+20h]
0x18006b850  movups  xmmword ptr [rcx+20h], xmm0
0x18006b854  mov     rax, [rax+30h]
0x18006b858  mov     [rcx+30h], rax
0x18006b85c  mov     eax, [r13+20h]
0x18006b860  mov     [rbx+0ECh], eax
0x18006b866  mov     eax, [rbp+arg_40]
0x18006b86c  mov     [rbx+0F0h], eax
0x18006b872  mov     eax, cs:OsVersionInfoEx.dwBuildNumber
0x18006b878  mov     [rbx+130h], eax
0x18006b87e  test    rdi, rdi
0x18006b881  jz      short loc_18006B887
0x18006b883  mov     r14, [rdi+20h]
0x18006b887  mov     rcx, [rbp+arg_30]
0x18006b88b  mov     rcx, [rcx]
0x18006b88e  call    FindFileName
0x18006b893  mov     rdx, rax
0x18006b896  lea     rcx, [rbx+20h]
0x18006b89a  lea     rax, [rbp+var_10]
0x18006b89e  xor     r9d, r9d
0x18006b8a1  mov     [rsp+60h+var_38], rax; unsigned int
0x18006b8a6  mov     r8, r14
0x18006b8a9  lea     rax, [rbp+arg_18]
0x18006b8ad  mov     [rsp+60h+var_40], rax; unsigned __int16 *
0x18006b8b2  call    AllocOrUpdateStringAndTestSame
0x18006b8b7  mov     rcx, [rbp+arg_28]; struct _INISPOOLER *
0x18006b8bb  mov     r9, rbx; struct _INIDRIVER *
0x18006b8be  mov     r8, r13; struct _INIVERSION *
0x18006b8c1  mov     rdx, r12; struct _INIENVIRONMENT *
0x18006b8c4  call    ?CheckDriverAttributes@@YAXPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@PEBGK@Z; CheckDriverAttributes(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ushort const *,ulong)
0x18006b8c9  mov     r14d, 1
0x18006b8cf  cmp     [rbx+0E8h], r14d
0x18006b8d6  jnz     short loc_18006B8E9
0x18006b8d8  mov     ecx, 78Ah; dwErrCode
0x18006b8dd  mov     [rbp+arg_18], r14d
0x18006b8e1  call    cs:__imp_SetLastError
0x18006b8e7  jmp     short loc_18006B8F0
0x18006b8e9  mov     [rbp+arg_18], 0
0x18006b8f0  cmp     [rbp+arg_38], r14d
0x18006b8f4  jbe     short loc_18006B935
0x18006b8f6  test    rdi, rdi
0x18006b8f9  jz      short loc_18006B901
0x18006b8fb  mov     r14, [rdi+28h]
0x18006b8ff  jmp     short loc_18006B904
0x18006b901  xor     r14d, r14d
0x18006b904  mov     rax, [rbp+arg_30]
0x18006b908  mov     rcx, [rax+20h]
0x18006b90c  call    FindFileName
0x18006b911  mov     rdx, rax
0x18006b914  lea     rcx, [rbx+28h]
0x18006b918  lea     rax, [rbp+var_10]
0x18006b91c  xor     r9d, r9d
0x18006b91f  mov     [rsp+60h+var_38], rax
0x18006b924  mov     r8, r14
0x18006b927  lea     rax, [rbp+arg_18]
0x18006b92b  mov     [rsp+60h+var_40], rax
0x18006b930  call    AllocOrUpdateStringAndTestSame
0x18006b935  cmp     [rbp+arg_38], 2
0x18006b939  jbe     short loc_18006B97A
0x18006b93b  test    rdi, rdi
0x18006b93e  jz      short loc_18006B946
0x18006b940  mov     r14, [rdi+30h]
0x18006b944  jmp     short loc_18006B949
0x18006b946  xor     r14d, r14d
0x18006b949  mov     rax, [rbp+arg_30]
0x18006b94d  mov     rcx, [rax+40h]
0x18006b951  call    FindFileName
0x18006b956  mov     rdx, rax
0x18006b959  lea     rcx, [rbx+30h]
0x18006b95d  lea     rax, [rbp+var_10]
0x18006b961  xor     r9d, r9d
0x18006b964  mov     [rsp+60h+var_38], rax
0x18006b969  mov     r8, r14
0x18006b96c  lea     rax, [rbp+arg_18]
0x18006b970  mov     [rsp+60h+var_40], rax
0x18006b975  call    AllocOrUpdateStringAndTestSame
0x18006b97a  mov     eax, r15d
0x18006b97d  mov     r14d, 1
0x18006b983  mov     [rbx+104h], r14d
0x18006b98a  sub     eax, 2
0x18006b98d  jz      loc_18006BFB3
0x18006b993  sub     eax, r14d
0x18006b996  jz      short loc_18006B9CB
0x18006b998  sub     eax, r14d
0x18006b99b  jz      short loc_18006B9CB
0x18006b99d  sub     eax, 2
0x18006b9a0  jz      short loc_18006B9EC
0x18006b9a2  sub     eax, 2
0x18006b9a5  jz      loc_18006BA38
0x18006b9ab  cmp     eax, 5Dh ; ']'
0x18006b9ae  jz      short loc_18006B9EC
0x18006b9b0  mov     r8d, r15d
0x18006b9b3  lea     rdx, aInvalidLevelD; "Invalid level %d"
0x18006b9ba  lea     rcx, aCreatedriveren; "CreateDriverEntry"
0x18006b9c1  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18006b9c6  jmp     loc_18006B76A
0x18006b9cb  xor     r13d, r13d
0x18006b9ce  mov     [rbx+80h], r13
0x18006b9d5  mov     [rbx+88h], r13
0x18006b9dc  mov     [rbx+90h], r13
0x18006b9e3  mov     [rbx+98h], r13
0x18006b9ea  jmp     short loc_18006B9EF
0x18006b9ec  xor     r13d, r13d
0x18006b9ef  mov     [rbx+0A0h], r13
0x18006b9f6  mov     [rbx+0A8h], r13
0x18006b9fd  mov     [rbx+0B0h], r13d
0x18006ba04  mov     [rbx+0B8h], r13
0x18006ba0b  mov     [rbx+0C0h], r13
0x18006ba12  mov     qword ptr [rbx+0C8h], 0
0x18006ba1d  mov     [rbx+0D0h], r13
0x18006ba24  mov     qword ptr [rbx+0D8h], 0
0x18006ba2f  mov     [rbx+0E0h], r13
0x18006ba36  jmp     short loc_18006BA3B
0x18006ba38  xor     r13d, r13d
0x18006ba3b  test    rdi, rdi
0x18006ba3e  jz      short loc_18006BA46
0x18006ba40  mov     r8, [rdi+18h]
0x18006ba44  jmp     short loc_18006BA49
0x18006ba46  mov     r8, r13
0x18006ba49  mov     rdx, [rsi+8]
0x18006ba4d  lea     rax, [rbp+arg_48]
0x18006ba54  mov     [rsp+60h+var_38], rax
0x18006ba59  lea     rcx, [rbx+18h]
0x18006ba5d  lea     rax, [rbp+arg_18]
0x18006ba61  mov     dword ptr [rbp+arg_48], r13d
0x18006ba68  xor     r9d, r9d
0x18006ba6b  mov     [rsp+60h+var_40], rax
0x18006ba70  call    AllocOrUpdateStringAndTestSame
0x18006ba75  cmp     [rbp+var_10], r13d
0x18006ba79  jz      short loc_18006BA84
0x18006ba7b  test    [rbp+arg_20], 8
0x18006ba7f  mov     ecx, r14d
0x18006ba82  jnz     short loc_18006BA87
0x18006ba84  mov     ecx, r13d
0x18006ba87  mov     r14d, [rbp+arg_18]
0x18006ba8b  test    r14d, r14d
0x18006ba8e  jnz     short loc_18006BAD8
0x18006ba90  test    rdi, rdi
0x18006ba93  jz      short loc_18006BA9B
0x18006ba95  mov     rax, [rdi+38h]
0x18006ba99  jmp     short loc_18006BA9E
0x18006ba9b  mov     rax, r13
0x18006ba9e  mov     r9d, [rbp+arg_38]; unsigned int
0x18006baa2  mov     rdx, rsi; unsigned __int8 *
0x18006baa5  mov     r8, [rbp+arg_30]; struct _INTERNAL_DRV_FILE *
0x18006baa9  mov     [rsp+60h+var_18], ecx; int
0x18006baad  mov     ecx, r15d; unsigned int
0x18006bab0  mov     [rsp+60h+var_20], rax; unsigned __int16 *
0x18006bab5  mov     [rsp+60h+var_38], r12; struct _INIENVIRONMENT *
0x18006baba  mov     [rsp+60h+var_40], rbx; struct _INIDRIVER *
0x18006babf  call    ?SetDependentFilesCommon@@YAHKPEAEPEAU_INTERNAL_DRV_FILE@@KPEAU_INIDRIVER@@PEAU_INIENVIRONMENT@@PEAU_INISPOOLER@@PEAU_INIVERSION@@PEBGH@Z; SetDependentFilesCommon(ulong,uchar *,_INTERNAL_DRV_FILE *,ulong,_INIDRIVER *,_INIENVIRONMENT *,_INISPOOLER *,_INIVERSION *,ushort const *,int)
0x18006bac4  xor     r12d, r12d
0x18006bac7  test    eax, eax
0x18006bac9  lea     eax, [r12+1]
0x18006bace  cmovz   r14d, eax
0x18006bad2  mov     [rbp+arg_18], r14d
0x18006bad6  jmp     short loc_18006BADB
0x18006bad8  xor     r12d, r12d
0x18006badb  test    rdi, rdi
0x18006bade  jz      short loc_18006BAE6
0x18006bae0  mov     r8, [rdi+50h]
0x18006bae4  jmp     short loc_18006BAE9
0x18006bae6  mov     r8, r12
0x18006bae9  mov     eax, 28h ; '('
0x18006baee  cmp     r15d, 65h ; 'e'
0x18006baf2  lea     ecx, [rax+18h]
0x18006baf5  cmovnz  eax, ecx
0x18006baf8  lea     rcx, [rbx+50h]
0x18006bafc  xor     r9d, r9d
0x18006baff  mov     rdx, [rax+rsi]
0x18006bb03  lea     rax, [rbp+arg_48]
0x18006bb0a  mov     [rsp+60h+var_38], rax
0x18006bb0f  lea     rax, [rbp+arg_18]
0x18006bb13  mov     [rsp+60h+var_40], rax
0x18006bb18  mov     dword ptr [rbp+arg_48], r12d
0x18006bb1f  call    AllocOrUpdateStringAndTestSame
0x18006bb24  test    rdi, rdi
0x18006bb27  jz      short loc_18006BB2F
0x18006bb29  mov     r8, [rdi+58h]
0x18006bb2d  jmp     short loc_18006BB32
0x18006bb2f  mov     r8, r12
0x18006bb32  mov     eax, 30h ; '0'
0x18006bb37  cmp     r15d, 65h ; 'e'
0x18006bb3b  lea     ecx, [rax+18h]
0x18006bb3e  cmovnz  eax, ecx
0x18006bb41  lea     rcx, [rbx+58h]
0x18006bb45  xor     r9d, r9d
0x18006bb48  mov     rdx, [rax+rsi]
0x18006bb4c  lea     rax, [rbp+arg_48]
0x18006bb53  mov     [rsp+60h+var_38], rax
0x18006bb58  lea     rax, [rbp+arg_18]
0x18006bb5c  mov     [rsp+60h+var_40], rax
0x18006bb61  mov     dword ptr [rbp+arg_48], r12d
0x18006bb68  call    AllocOrUpdateStringAndTestSame
0x18006bb6d  mov     [rbx+60h], r12d
0x18006bb71  mov     r13d, 50h ; 'P'
0x18006bb77  cmp     r15d, 8
0x18006bb7b  ja      short loc_18006BB88
0x18006bb7d  mov     eax, 150h
0x18006bb82  bt      eax, r15d
0x18006bb86  jb      short loc_18006BB92
0x18006bb88  cmp     r15d, 65h ; 'e'
0x18006bb8c  jnz     loc_18006BD9C
0x18006bb92  mov     r12d, 38h ; '8'
0x18006bb98  cmp     r15d, 65h ; 'e'
0x18006bb9c  mov     ecx, r12d
0x18006bb9f  cmovnz  rcx, r13
0x18006bba3  xor     edx, edx
0x18006bba5  mov     rcx, [rcx+rsi]
0x18006bba9  call    GetMultiSZLen
0x18006bbae  mov     r14d, eax
0x18006bbb1  mov     [rbx+60h], r14d
0x18006bbb5  test    eax, eax
0x18006bbb7  jz      short loc_18006BC1A
0x18006bbb9  lea     ecx, [r14+r14]
0x18006bbbd  call    cs:__imp_DllAllocSplMem
0x18006bbc3  mov     [rbx+68h], rax
0x18006bbc7  test    rax, rax
0x18006bbca  jnz     short loc_18006BBD8
0x18006bbcc  mov     [rbp+arg_18], 1
0x18006bbd3  xor     r12d, r12d
0x18006bbd6  jmp     short loc_18006BC21
0x18006bbd8  mov     r8, r14
0x18006bbdb  mov     rcx, rax; void *
0x18006bbde  add     r8, r8; Size
  ... truncated ...
```
