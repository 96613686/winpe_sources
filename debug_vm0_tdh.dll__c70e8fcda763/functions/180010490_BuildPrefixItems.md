# BuildPrefixItems

- ea: `0x180010490`
- end: `0x1800110e1`
- name: `BuildPrefixItems`
- size: `3153`
- prototype: `__int64 __fastcall(struct FormatContext *, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000fee0`

## callees

- `0x180010490`
- `0x1800113a8`
- `0x1800117c8`
- `0x180012ef4`
- `0x180012f5c`
- `0x1800207c0`
- `0x180023b05`
- `0x18003ebb0`
- `0x18003f038`
- `0x180042550`
- `0x180042f7c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800107fa`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800107fa`

## string_xrefs

- `0x180010dbc`: `Param %%03 (Thread ID) 0x%X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildPrefixItems(struct FormatContext *a1, __int64 *a2, __int64 a3, int a4)
{
  bool v4; // zf
  void *v6; // r9
  _WORD *v10; // rax
  _WORD *v11; // rsi
  __int64 v12; // rdi
  unsigned int v13; // r12d
  unsigned int v14; // edi
  const void *v15; // rdx
  size_t v16; // r8
  unsigned int v17; // r12d
  unsigned __int16 *v18; // rbx
  _WORD *v19; // rdi
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // r10d
  unsigned __int64 v23; // rdx
  _WORD *v24; // r9
  __int64 v25; // rcx
  char *v26; // rax
  _WORD *v27; // r8
  char *v28; // rcx
  int v29; // eax
  __int64 v30; // r8
  unsigned int (*v31)(unsigned __int16 *, ...); // r11
  __int64 v32; // rax
  int v33; // eax
  unsigned int v34; // r9d
  unsigned __int64 v35; // rdx
  char *v36; // rsi
  unsigned __int16 *v37; // rcx
  char *v38; // rax
  __int64 v39; // r8
  char *v40; // rcx
  __int64 v41; // rcx
  unsigned __int16 *v42; // rdx
  unsigned int v43; // ecx
  unsigned int v44; // r12d
  unsigned __int16 *v45; // rbx
  FILETIME *v46; // rax
  __int64 v47; // rcx
  FILETIME v48; // r9
  unsigned __int64 v49; // rcx
  FILETIME v50; // rdx
  const union _LARGE_INTEGER *v51; // r9
  __int64 v52; // r11
  __int64 v53; // rcx
  unsigned int v54; // ecx
  unsigned int v55; // r12d
  _WORD *v56; // rbx
  unsigned int v57; // r8d
  unsigned int v58; // r9d
  unsigned int v59; // r8d
  unsigned int v60; // r9d
  unsigned int v61; // r8d
  unsigned int v62; // r9d
  __int64 v63; // rcx
  unsigned int v64; // ecx
  unsigned int v65; // r12d
  _WORD *v66; // rbx
  unsigned int v67; // r8d
  unsigned int v68; // r9d
  unsigned int v69; // r8d
  unsigned int v70; // r9d
  unsigned int v71; // r8d
  unsigned int v72; // r9d
  __int64 v73; // rcx
  unsigned int v74; // ecx
  unsigned int (*v75)(unsigned __int16 *, ...); // r8
  __int64 v76; // rcx
  unsigned __int64 v77; // rdx
  __int64 result; // rax
  unsigned __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rdx
  __int64 v83; // rdx
  const unsigned __int16 *v84; // r8
  __int64 v85; // rax
  int v86; // eax
  unsigned int v87; // r15d
  int v88; // r13d
  _WORD *v89; // rdx
  _DWORD *v90; // r15
  unsigned int v91; // esi
  bool v92; // cc
  int v93; // r13d
  int v94; // eax
  _WORD *v95; // rdx
  unsigned int v96; // esi
  int v97; // eax
  _WORD *v98; // rdx
  unsigned int v99; // esi
  _WORD *v100; // rdx
  __int64 v101; // rax
  int v102; // eax
  unsigned int v103; // eax
  int v104; // eax
  int v105; // [rsp+30h] [rbp-69h]
  char *v106; // [rsp+38h] [rbp-61h]
  int v107; // [rsp+40h] [rbp-59h]
  int v108; // [rsp+48h] [rbp-51h] BYREF
  char *v109; // [rsp+50h] [rbp-49h] BYREF
  __int64 v110; // [rsp+58h] [rbp-41h]
  FILETIME FileTime; // [rsp+60h] [rbp-39h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-31h] BYREF
  _WORD *v113; // [rsp+78h] [rbp-21h]
  char v114[4]; // [rsp+84h] [rbp-15h] BYREF
  char v115[3]; // [rsp+88h] [rbp-11h] BYREF
  char v116; // [rsp+8Bh] [rbp-Eh] BYREF
  _BYTE v117[7]; // [rsp+99h] [rbp+0h] BYREF

  v4 = *((_BYTE *)a1 + 162) == 0;
  v6 = (void *)a2[261];
  v105 = a4;
  v108 = a4;
  v110 = *a2;
  v10 = (_WORD *)a2[3];
  v113 = v10;
  v106 = (char *)v10;
  v109 = (char *)v10;
  FileTime = (FILETIME)v6;
  if ( !v4 )
  {
    v106 = (char *)(v10 + 64);
    v109 = (char *)(v10 + 64);
  }
  a2[5] = (__int64)v6;
  v11 = (_WORD *)a2 + 1058;
  v12 = -1;
  v13 = *((_DWORD *)a1 + 564) - 1;
  do
    v4 = v11[++v12] == 0;
  while ( !v4 );
  v14 = 2 * v12 + 2;
  v15 = (char *)a2 + 2116;
  v16 = v14;
  if ( v14 >= v13 )
    v16 = v13;
  memcpy_0(v6, v15, v16);
  v17 = v13 - v14;
  v18 = (unsigned __int16 *)(*(_QWORD *)&FileTime + v14);
  v4 = *((_BYTE *)a1 + 162) == 0;
  v19 = v113;
  FileTime.dwLowDateTime = 1;
  if ( v4 )
  {
    v29 = v105;
  }
  else
  {
    if ( *(_WORD *)(a3 + 56) != 1 )
      *(_OWORD *)(v113 + 52) = *(_OWORD *)*(_QWORD *)(a3 + 24);
    v20 = -1;
    *(_OWORD *)(v19 + 2) = *(_OWORD *)*(_QWORD *)(a3 + 24);
    do
      v4 = v11[++v20] == 0;
    while ( !v4 );
    v21 = 2 * v20 + 2;
    v22 = v105;
    if ( v21 < v105 )
      v22 = v21;
    v23 = (unsigned __int64)v105 >> 1;
    if ( !v23 )
      goto LABEL_85;
    if ( v23 > 0x7FFFFFFF )
    {
      v36 = v106;
      *(_WORD *)v106 = 0;
      goto LABEL_86;
    }
    v24 = v106;
    v25 = 2147483646;
    v26 = v106;
    v27 = v11;
    do
    {
      if ( !v25 )
        break;
      if ( !*v27 )
        break;
      *(_WORD *)v26 = *v27++;
      v26 += 2;
      --v25;
      --v23;
    }
    while ( v23 );
    v28 = v26 - 2;
    if ( v23 )
      v28 = v26;
    *(_WORD *)v28 = 0;
    if ( !v23 )
      goto LABEL_85;
    *((_DWORD *)v19 + 5) = (_DWORD)v106 - (_DWORD)v19;
    v29 = v105 - v22;
    v106 += v22;
    v105 = v29;
    v108 = v29;
    v109 = (char *)v24 + v22;
  }
  v107 = v29;
  if ( v110 && *(_QWORD *)(v110 + 40) )
  {
    StringCchPrintfW(v18, (unsigned __int64)v17 >> 1, L"%s");
    v80 = v110;
    a2[263] = *(_QWORD *)(v110 + 56);
    v30 = *(unsigned int *)(v80 + 52);
  }
  else
  {
    StringCchPrintfW(v18, (unsigned __int64)v17 >> 1, L"%3d", *(unsigned __int16 *)(a3 + 52));
    v30 = 0;
  }
  *((_DWORD *)a2 + 528) = v30;
  v31 = TracePrinter;
  if ( TracePrinter )
  {
    v81 = a2[263];
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Type %s, TypeOf %d,\nFormat %s\n", v11, v30, v81);
    else
      TracePrinter(L"Type %s, TypeOf %d,\nFormat %s\n", v11, v30, v81);
    v31 = TracePrinter;
  }
  if ( !*((_BYTE *)a1 + 162) )
  {
    v36 = v106;
    goto LABEL_43;
  }
  v32 = -1;
  do
    v4 = v18[++v32] == 0;
  while ( !v4 );
  v33 = 2 * v32 + 2;
  v34 = v107;
  if ( v33 < v105 )
    v34 = v33;
  v35 = (unsigned __int64)v107 >> 1;
  if ( !v35 )
  {
LABEL_85:
    v36 = v106;
    goto LABEL_86;
  }
  v36 = v106;
  if ( v35 > 0x7FFFFFFF )
  {
    *(_WORD *)v106 = 0;
    goto LABEL_86;
  }
  v37 = v18;
  v38 = v106;
  v39 = 2147483646;
  do
  {
    if ( !v39 )
      break;
    if ( !*v37 )
      break;
    *(_WORD *)v38 = *v37++;
    v38 += 2;
    --v39;
    --v35;
  }
  while ( v35 );
  v40 = v38 - 2;
  if ( v35 )
    v40 = v38;
  *(_WORD *)v40 = 0;
  if ( !v35 )
    goto LABEL_86;
  *((_DWORD *)v19 + 6) = (_DWORD)v106 - (_DWORD)v19;
  v36 = &v106[v34];
  v106 = v36;
  v105 -= v34;
  v108 = v105;
  v109 = v36;
LABEL_43:
  v41 = -1;
  a2[6] = (__int64)v18;
  v42 = v18;
  do
    v4 = v18[++v41] == 0;
  while ( !v4 );
  v43 = 2 * v41 + 2;
  v44 = v17 - v43;
  v45 = (unsigned __int16 *)((char *)v18 + v43);
  if ( v31 )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"\n-> 2 %s \n", v42);
    else
      v31(L"\n-> 2 %s \n", v42);
    v31 = TracePrinter;
  }
  *((_DWORD *)a2 + 14) = *(_DWORD *)a3;
  if ( v31 )
  {
    v82 = a2[7];
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Param %%03 (Thread ID) 0x%X\n", v82);
    else
      v31(L"Param %%03 (Thread ID) 0x%X\n", v82);
  }
  if ( *((_BYTE *)a1 + 162) )
  {
    *((_DWORD *)v19 + 7) = *(_DWORD *)a3;
    if ( *((_BYTE *)a1 + 162) )
    {
      v46 = *(FILETIME **)(a3 + 16);
      if ( *((_BYTE *)a1 + 158) )
      {
        v50 = *v46;
      }
      else
      {
        v47 = *((int *)a1 + 38);
        v48 = *v46;
        if ( (int)v47 < 0 )
        {
          v50 = 0;
          v79 = 600000000LL * -(int)v47;
          if ( *(_QWORD *)&v48 >= v79 )
            v50 = (FILETIME)(*(_QWORD *)&v48 - v79);
        }
        else
        {
          v49 = 600000000 * v47;
          v50 = (FILETIME)(v49 + *(_QWORD *)&v48);
          if ( v49 + *(_QWORD *)&v48 < v49 )
            v50 = (FILETIME)-1LL;
        }
      }
      FileTime = v50;
      SystemTime = 0;
      FileTimeToSystemTime(&FileTime, &SystemTime);
      *((_SYSTEMTIME *)v19 + 2) = SystemTime;
      *((_QWORD *)v19 + 12) = **(_QWORD **)(a3 + 16);
    }
  }
  v51 = *(const union _LARGE_INTEGER **)(a3 + 16);
  if ( a2[263] )
    FormatFileTime(a1, v45, v44 >> 1, v51, 1);
  else
    StringCchPrintfW(v45, (unsigned __int64)v44 >> 1, L"%20I64u", v51->QuadPart);
  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Param %%04 (System Time) %s\n", v45);
    else
      TracePrinter(L"Param %%04 (System Time) %s\n", v45);
  }
  v52 = -1;
  a2[8] = (__int64)v45;
  v53 = -1;
  do
    v4 = v45[++v53] == 0;
  while ( !v4 );
  v54 = 2 * v53 + 2;
  v55 = v44 - v54;
  v56 = (unsigned __int16 *)((char *)v45 + v54);
  if ( (v55 & 0xFFFFFFFE) > 0x10 )
  {
    v57 = *((_DWORD *)a1 + 28) * *(_DWORD *)(a3 + 12);
    v56[8] = 0;
    v58 = v57 / 0xA;
    v56[7] = v57 % 0xA + 48;
    v59 = v57 / 0xA / 0xA;
    v56[6] = v58 - 10 * v59 + 48;
    v60 = v59 / 0xA;
    v56[5] = v59 % 0xA + 48;
    v61 = v59 / 0xA / 0xA;
    v56[4] = v60 - 10 * v61 + 48;
    v62 = v61 / 0xA / 0xA;
    v56[3] = v61 % 0xA + 48;
    v56[2] = v61 / 0xA % 0xA + 48;
    v56[1] = v62 % 0xA + 48;
    *v56 = v62 / 0xA % 0xA + 48;
  }
  a2[9] = (__int64)v56;
  v63 = -1;
  do
    v4 = v56[++v63] == 0;
  while ( !v4 );
  v64 = 2 * v63 + 2;
  v65 = v55 - v64;
  v66 = (_WORD *)((char *)v56 + v64);
  if ( *((_BYTE *)a1 + 162) )
    *((_DWORD *)v19 + 13) = *((_DWORD *)a1 + 28) * *(_DWORD *)(a3 + 12);
  if ( (v65 & 0xFFFFFFFE) > 0x10 )
  {
    v67 = *((_DWORD *)a1 + 28) * *(_DWORD *)(a3 + 8);
    v66[8] = 0;
    v68 = v67 / 0xA;
    v66[7] = v67 % 0xA + 48;
    v69 = v67 / 0xA / 0xA;
    v66[6] = v68 - 10 * v69 + 48;
    v70 = v69 / 0xA;
    v66[5] = v69 % 0xA + 48;
    v71 = v69 / 0xA / 0xA;
    v66[4] = v70 - 10 * v71 + 48;
    v72 = v71 / 0xA / 0xA;
    v66[3] = v71 % 0xA + 48;
    v66[2] = v71 / 0xA % 0xA + 48;
    v66[1] = v72 % 0xA + 48;
    *v66 = v72 / 0xA % 0xA + 48;
  }
  a2[10] = (__int64)v66;
  v73 = -1;
  do
    v4 = v66[++v73] == 0;
  while ( !v4 );
  v74 = 2 * v73 + 2;
  v17 = v65 - v74;
  v18 = (_WORD *)((char *)v66 + v74);
  if ( *((_BYTE *)a1 + 162) )
    *((_DWORD *)v19 + 12) = *((_DWORD *)a1 + 28) * *(_DWORD *)(a3 + 8);
  a2[11] = *(_QWORD *)(a3 + 40);
  if ( *((_BYTE *)a1 + 162) )
    *((_DWORD *)v19 + 14) = *(_DWORD *)(a3 + 40);
  v75 = TracePrinter;
  *((_DWORD *)a2 + 24) = *(_DWORD *)(a3 + 4);
  if ( v75 )
  {
    v83 = a2[12];
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Param %%08 (Process ID) 0x%X\n", v83);
    else
      v75(L"Param %%08 (Process ID) 0x%X\n", v83);
    v75 = TracePrinter;
    v52 = -1;
  }
  if ( *((_BYTE *)a1 + 162) )
    *((_DWORD *)v19 + 15) = *(_DWORD *)(a3 + 4);
  a2[13] = *(unsigned int *)(a3 + 48);
  if ( v75 )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"Param %%09 (CPU Number) 0x%X\n");
    else
      v75(L"Param %%09 (CPU Number) 0x%X\n");
    v52 = -1;
  }
  v4 = *((_BYTE *)a1 + 162) == 0;
  FileTime.dwLowDateTime = 9;
  if ( v4 )
    goto LABEL_83;
  v76 = v110;
  *((_DWORD *)v19 + 16) = *(_DWORD *)(a3 + 48);
  if ( v76 )
  {
    *((_DWORD *)v19 + 17) = *(_DWORD *)(v76 + 104);
    v84 = *(const unsigned __int16 **)(v76 + 64);
    if ( !v84 )
    {
      v88 = v105;
      goto LABEL_127;
    }
    v85 = -1;
    do
      v4 = v84[++v85] == 0;
    while ( !v4 );
    v86 = 2 * v85 + 2;
    v87 = v105;
    if ( v86 < v105 )
      v87 = v86;
    if ( (int)StringCchCopyW((unsigned __int16 *)v36, (unsigned __int64)v105 >> 1, v84) >= 0 )
    {
      v76 = v110;
      *((_DWORD *)v19 + 20) = (_DWORD)v36 - (_DWORD)v19;
      v36 += v87;
      v88 = v105 - v87;
      v106 = v36;
      v105 -= v87;
LABEL_127:
      v89 = *(_WORD **)(v76 + 88);
      if ( v89 )
      {
        do
          v4 = v89[++v52] == 0;
        while ( !v4 );
        v91 = v88;
        v92 = 2 * (int)v52 + 2 < v88;
        v93 = (int)v106;
        if ( v92 )
          v91 = 2 * v52 + 2;
        memcpy_0(v106, v89, v91);
        v90 = v113;
        v76 = v110;
        v106 += v91;
        v94 = v93 - (_DWORD)v113;
        v52 = -1;
        v88 = v105 - v91;
        *((_DWORD *)v113 + 18) = v94;
        v36 = v106;
        v105 = v88;
      }
      else
      {
        v90 = v113;
      }
      v95 = *(_WORD **)(v76 + 96);
      if ( v95 )
      {
        do
          v4 = v95[++v52] == 0;
        while ( !v4 );
        v96 = v88;
        if ( 2 * (int)v52 + 2 < v88 )
          v96 = 2 * v52 + 2;
        memcpy_0(v106, v95, v96);
        v76 = v110;
        v97 = (_DWORD)v106 - (_DWORD)v90;
        v106 += v96;
        v52 = -1;
        v88 = v105 - v96;
        v90[19] = v97;
        v36 = v106;
        v105 = v88;
      }
      v98 = *(_WORD **)(v76 + 72);
      if ( v98 )
      {
        do
          v4 = v98[++v52] == 0;
        while ( !v4 );
        v99 = v88;
        if ( 2 * (int)v52 + 2 < v88 )
          v99 = 2 * v52 + 2;
        memcpy_0(v106, v98, v99);
        v76 = v110;
        v52 = -1;
        v88 = v105 - v99;
        v90[21] = (_DWORD)v106 - (_DWORD)v90;
        v36 = &v106[v99];
      }
      v100 = *(_WORD **)(v76 + 80);
      if ( v100 )
      {
        do
          v4 = v100[++v52] == 0;
        while ( !v4 );
        if ( 2 * (int)v52 + 2 < v88 )
          v88 = 2 * v52 + 2;
        memcpy_0(v36, v100, (unsigned int)v88);
        v90[22] = (_DWORD)v36 - (_DWORD)v90;
        v36 += (unsigned int)v88;
      }
      goto LABEL_83;
    }
LABEL_86:
    result = 122;
    goto LABEL_84;
  }
  if ( *(_BYTE *)(a3 + 58) )
  {
    v101 = utl::_ToCharsConstWrite<unsigned int,char>(v114, *(unsigned __int8 *)(a3 + 58));
    utl::_ToCharsResult<utl::to_chars_result,char>(
      (unsigned int)&SystemTime,
      (unsigned int)v115,
      (unsigned int)&v116,
      v101,
      (__int64)&v114[-v101]);
    v102 = CopyIn(
             (unsigned int)v115,
             *(_DWORD *)&SystemTime.wYear - ((unsigned int)v117 - 17),
             (_DWORD)v19,
             (unsigned int)&v109,
             (__int64)&v108);
    v36 = v109;
    *((_DWORD *)v19 + 19) = v102;
  }
  v77 = *(_QWORD *)(a3 + 32);
  if ( v77 )
  {
    v103 = TraceprtFormatKeyword(v115, v77);
    v104 = CopyIn((unsigned int)v115, v103, (_DWORD)v19, (unsigned int)&v109, (__int64)&v108);
    v36 = v109;
    *((_DWORD *)v19 + 18) = v104;
  }
LABEL_83:
  result = 0;
LABEL_84:
  *((_DWORD *)a2 + 5) = FileTime.dwLowDateTime;
  a2[4] = (__int64)v36;
  *((_DWORD *)a2 + 524) = v17;
  a2[261] = (__int64)v18;
  return result;
}

```

## disassembly

```asm
0x180010490  push    rbp
0x180010492  push    rbx
0x180010493  push    rsi
0x180010494  push    rdi
0x180010495  push    r12
0x180010497  push    r13
0x180010499  push    r14
0x18001049b  push    r15
0x18001049d  lea     rbp, [rsp-1Fh]
0x1800104a2  sub     rsp, 0B8h
0x1800104a9  mov     rax, cs:__security_cookie
0x1800104b0  xor     rax, rsp
0x1800104b3  mov     [rbp+57h+var_50], rax
0x1800104b7  cmp     byte ptr [rcx+0A2h], 0
0x1800104be  mov     eax, r9d
0x1800104c1  mov     r9, [rdx+828h]
0x1800104c8  mov     r15, r8
0x1800104cb  mov     [rbp+57h+var_C0], eax
0x1800104ce  mov     r14, rdx
0x1800104d1  mov     [rbp+57h+var_A8], eax
0x1800104d4  mov     r13, rcx
0x1800104d7  mov     rax, [rdx]
0x1800104da  mov     [rbp+57h+var_98], rax
0x1800104de  mov     rax, [rdx+18h]
0x1800104e2  mov     [rbp+57h+var_78], rax
0x1800104e6  mov     [rbp+57h+var_B8], rax
0x1800104ea  mov     [rbp+57h+var_A0], rax
0x1800104ee  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r9
0x1800104f2  jz      short loc_180010500
0x1800104f4  sub     rax, 0FFFFFFFFFFFFFF80h
0x1800104f8  mov     [rbp+57h+var_B8], rax
0x1800104fc  mov     [rbp+57h+var_A0], rax
0x180010500  mov     [rdx+28h], r9
0x180010504  lea     rsi, [rdx+844h]
0x18001050b  mov     r12d, [rcx+8D0h]
0x180010512  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180010519  dec     r12d
0x18001051c  nop     dword ptr [rax+00h]
0x180010520  cmp     word ptr [rsi+rdi*2+2], 0
0x180010526  lea     rdi, [rdi+1]
0x18001052a  jnz     short loc_180010520
0x18001052c  lea     edi, ds:2[rdi*2]
0x180010533  mov     rdx, rsi; Src
0x180010536  mov     r8d, edi
0x180010539  cmp     edi, r12d
0x18001053c  mov     rcx, r9; void *
0x18001053f  cmovnb  r8d, r12d; Size
0x180010543  call    memcpy_0
0x180010548  mov     ebx, edi
0x18001054a  sub     r12d, edi
0x18001054d  add     rbx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180010551  cmp     byte ptr [r13+0A2h], 0
0x180010559  mov     rdi, [rbp+57h+var_78]
0x18001055d  mov     [rbp+57h+FileTime.dwLowDateTime], 1
0x180010564  jz      loc_18001063A
0x18001056a  cmp     word ptr [r15+38h], 1
0x180010570  jnz     loc_180010CEF
0x180010576  mov     rax, [r15+18h]
0x18001057a  movups  xmm0, xmmword ptr [rax]
0x18001057d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010584  movups  xmmword ptr [rdi+4], xmm0
0x180010588  nop     dword ptr [rax+rax+00000000h]
0x180010590  cmp     word ptr [rsi+rax*2+2], 0
0x180010596  lea     rax, [rax+1]
0x18001059a  jnz     short loc_180010590
0x18001059c  movsxd  r11, [rbp+57h+var_C0]
0x1800105a0  lea     eax, ds:2[rax*2]
0x1800105a7  cmp     eax, r11d
0x1800105aa  mov     r10d, r11d
0x1800105ad  mov     rdx, r11
0x1800105b0  cmovl   r10d, eax
0x1800105b4  shr     rdx, 1
0x1800105b7  jz      loc_180010CA0
0x1800105bd  cmp     rdx, 7FFFFFFFh
0x1800105c4  ja      loc_180010CFF
0x1800105ca  mov     r9, [rbp+57h+var_B8]
0x1800105ce  mov     ecx, 7FFFFFFEh
0x1800105d3  mov     rax, r9
0x1800105d6  mov     r8, rsi
0x1800105d9  test    rcx, rcx
0x1800105dc  jz      short loc_1800105FD
0x1800105de  movzx   r11d, word ptr [r8]
0x1800105e2  test    r11w, r11w
0x1800105e6  jz      short loc_1800105FD
0x1800105e8  mov     [rax], r11w
0x1800105ec  add     r8, 2
0x1800105f0  add     rax, 2
0x1800105f4  dec     rcx
0x1800105f7  sub     rdx, 1
0x1800105fb  jnz     short loc_1800105D9
0x1800105fd  test    rdx, rdx
0x180010600  lea     rcx, [rax-2]
0x180010604  cmovnz  rcx, rax
0x180010608  xor     eax, eax
0x18001060a  mov     [rcx], ax
0x18001060d  test    rdx, rdx
0x180010610  jz      loc_180010CA0
0x180010616  mov     eax, r9d
0x180010619  sub     eax, edi
0x18001061b  mov     [rdi+14h], eax
0x18001061e  mov     eax, r10d
0x180010621  add     r9, rax
0x180010624  mov     eax, [rbp+57h+var_C0]
0x180010627  sub     eax, r10d
0x18001062a  mov     [rbp+57h+var_B8], r9
0x18001062e  mov     [rbp+57h+var_C0], eax
0x180010631  mov     [rbp+57h+var_A8], eax
0x180010634  mov     [rbp+57h+var_A0], r9
0x180010638  jmp     short loc_18001063D
0x18001063a  mov     eax, [rbp+57h+var_C0]
0x18001063d  mov     [rbp+57h+var_B0], eax
0x180010640  mov     rax, [rbp+57h+var_98]
0x180010644  test    rax, rax
0x180010647  jnz     loc_180010D0A
0x18001064d  movzx   r9d, word ptr [r15+34h]
0x180010652  lea     r8, a3d; "%3d"
0x180010659  mov     edx, r12d
0x18001065c  mov     rcx, rbx; unsigned __int16 *
0x18001065f  shr     rdx, 1; unsigned __int64
0x180010662  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010667  xor     r8d, r8d
0x18001066a  mov     [r14+840h], r8d
0x180010671  mov     r11, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180010678  test    r11, r11
0x18001067b  jnz     loc_180010D44
0x180010681  cmp     byte ptr [r13+0A2h], 0
0x180010689  jz      loc_180010CAB
0x18001068f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180010696  nop     word ptr [rax+rax+00000000h]
0x1800106a0  cmp     word ptr [rbx+rax*2+2], 0
0x1800106a6  lea     rax, [rax+1]
0x1800106aa  jnz     short loc_1800106A0
0x1800106ac  movsxd  rcx, [rbp+57h+var_B0]
0x1800106b0  lea     eax, ds:2[rax*2]
0x1800106b7  cmp     eax, [rbp+57h+var_C0]
0x1800106ba  mov     r9d, ecx
0x1800106bd  mov     rdx, rcx
0x1800106c0  cmovl   r9d, eax
0x1800106c4  shr     rdx, 1
0x1800106c7  jz      loc_180010CA0
0x1800106cd  mov     rsi, [rbp+57h+var_B8]
0x1800106d1  cmp     rdx, 7FFFFFFFh
0x1800106d8  ja      loc_180010D79
0x1800106de  mov     rcx, rbx
0x1800106e1  mov     rax, rsi
0x1800106e4  mov     r8d, 7FFFFFFEh
0x1800106ea  test    r8, r8
0x1800106ed  jz      short loc_18001070E
0x1800106ef  movzx   r10d, word ptr [rcx]
0x1800106f3  test    r10w, r10w
0x1800106f7  jz      short loc_18001070E
0x1800106f9  mov     [rax], r10w
0x1800106fd  add     rcx, 2
0x180010701  add     rax, 2
0x180010705  dec     r8
0x180010708  sub     rdx, 1
0x18001070c  jnz     short loc_1800106EA
0x18001070e  test    rdx, rdx
0x180010711  lea     rcx, [rax-2]
0x180010715  cmovnz  rcx, rax
0x180010719  xor     eax, eax
0x18001071b  mov     [rcx], ax
0x18001071e  test    rdx, rdx
0x180010721  jz      loc_180010CA4
0x180010727  mov     r10d, [rbp+57h+var_C0]
0x18001072b  mov     eax, esi
0x18001072d  sub     eax, edi
0x18001072f  mov     [rdi+18h], eax
0x180010732  mov     eax, r9d
0x180010735  add     rsi, rax
0x180010738  sub     r10d, r9d
0x18001073b  mov     [rbp+57h+var_B8], rsi
0x18001073f  mov     [rbp+57h+var_C0], r10d
0x180010743  mov     [rbp+57h+var_A8], r10d
0x180010747  mov     [rbp+57h+var_A0], rsi
0x18001074b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180010752  mov     [rbp+57h+var_B0], 0
0x180010759  mov     rcx, r8
0x18001075c  mov     [r14+30h], rbx
0x180010760  mov     rdx, rbx
0x180010763  cmp     word ptr [rbx+rcx*2+2], 0
0x180010769  lea     rcx, [rcx+1]
0x18001076d  jnz     short loc_180010763
0x18001076f  lea     ecx, ds:2[rcx*2]
0x180010776  mov     eax, ecx
0x180010778  sub     r12d, ecx
0x18001077b  add     rbx, rax
0x18001077e  test    r11, r11
0x180010781  jnz     loc_180010D83
0x180010787  mov     eax, [r15]
0x18001078a  mov     [r14+38h], eax
0x18001078e  test    r11, r11
0x180010791  jnz     loc_180010DB5
0x180010797  cmp     byte ptr [r13+0A2h], 0
0x18001079f  jz      short loc_180010813
0x1800107a1  mov     eax, [r15]
0x1800107a4  mov     [rdi+1Ch], eax
0x1800107a7  cmp     byte ptr [r13+0A2h], 0
0x1800107af  jz      short loc_180010813
0x1800107b1  cmp     byte ptr [r13+9Eh], 0
0x1800107b9  mov     rax, [r15+10h]
0x1800107bd  jnz     loc_180010DE4
0x1800107c3  movsxd  rcx, dword ptr [r13+98h]
0x1800107ca  mov     r9, [rax]
0x1800107cd  test    ecx, ecx
0x1800107cf  js      loc_180010CB4
0x1800107d5  imul    rcx, 23C34600h
0x1800107dc  lea     rdx, [rcx+r9]
0x1800107e0  cmp     rdx, rcx
0x1800107e3  cmovb   rdx, r8
0x1800107e7  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rdx
0x1800107eb  lea     rcx, [rbp+57h+FileTime]; lpFileTime
0x1800107ef  xorps   xmm0, xmm0
0x1800107f2  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x1800107f6  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1800107fa  call    cs:__imp_FileTimeToSystemTime
0x180010800  movups  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x180010804  movups  xmmword ptr [rdi+20h], xmm0
0x180010808  mov     rax, [r15+10h]
0x18001080c  mov     rcx, [rax]
0x18001080f  mov     [rdi+60h], rcx
0x180010813  cmp     qword ptr [r14+838h], 0
0x18001081b  mov     r9, [r15+10h]; union _LARGE_INTEGER *
0x18001081f  jnz     loc_180010CD4
0x180010825  mov     r9, [r9]
0x180010828  lea     r8, a20i64u; "%20I64u"
0x18001082f  mov     edx, r12d
0x180010832  mov     rcx, rbx; unsigned __int16 *
0x180010835  shr     rdx, 1; unsigned __int64
0x180010838  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001083d  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180010844  test    rax, rax
0x180010847  jnz     loc_180010DEC
0x18001084d  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180010854  mov     [r14+40h], rbx
0x180010858  mov     rcx, r11
0x18001085b  nop     dword ptr [rax+rax+00h]
0x180010860  cmp     word ptr [rbx+rcx*2+2], 0
0x180010866  lea     rcx, [rcx+1]
0x18001086a  jnz     short loc_180010860
0x18001086c  lea     ecx, ds:2[rcx*2]
0x180010873  mov     eax, ecx
0x180010875  sub     r12d, ecx
0x180010878  add     rbx, rax
0x18001087b  mov     eax, r12d
0x18001087e  and     eax, 0FFFFFFFEh
0x180010881  cmp     eax, 10h
0x180010884  jbe     loc_1800109E9
0x18001088a  mov     r8d, [r15+0Ch]
0x18001088e  xor     eax, eax
0x180010890  imul    r8d, [r13+70h]
0x180010895  mov     [rbx+10h], ax
0x180010899  mov     eax, 0CCCCCCCDh
0x18001089e  mul     r8d
0x1800108a1  mov     r9d, edx
0x1800108a4  shr     r9d, 3
0x1800108a8  movzx   eax, r9w
0x1800108ac  shl     ax, 2
0x1800108b0  lea     ecx, [rax+r9]
0x1800108b4  mov     eax, 0CCCCCCCDh
0x1800108b9  mul     r9d
0x1800108bc  add     cx, cx
0x1800108bf  sub     r8w, cx
0x1800108c3  add     r8w, 30h ; '0'
0x1800108c8  mov     [rbx+0Eh], r8w
0x1800108cd  mov     r8d, edx
0x1800108d0  shr     r8d, 3
0x1800108d4  movzx   eax, r8w
0x1800108d8  shl     ax, 2
0x1800108dc  lea     ecx, [rax+r8]
0x1800108e0  mov     eax, 0CCCCCCCDh
0x1800108e5  mul     r8d
0x1800108e8  add     cx, cx
0x1800108eb  sub     r9w, cx
0x1800108ef  add     r9w, 30h ; '0'
0x1800108f4  mov     [rbx+0Ch], r9w
0x1800108f9  mov     r9d, edx
0x1800108fc  shr     r9d, 3
0x180010900  movzx   eax, r9w
0x180010904  shl     ax, 2
0x180010908  lea     ecx, [rax+r9]
0x18001090c  mov     eax, 0CCCCCCCDh
0x180010911  mul     r9d
0x180010914  add     cx, cx
0x180010917  sub     r8w, cx
0x18001091b  add     r8w, 30h ; '0'
0x180010920  mov     [rbx+0Ah], r8w
0x180010925  mov     r8d, edx
0x180010928  shr     r8d, 3
0x18001092c  movzx   eax, r8w
0x180010930  shl     ax, 2
0x180010934  lea     ecx, [rax+r8]
0x180010938  mov     eax, 0CCCCCCCDh
0x18001093d  mul     r8d
0x180010940  add     cx, cx
0x180010943  sub     r9w, cx
0x180010947  mov     r10d, edx
0x18001094a  shr     r10d, 3
0x18001094e  add     r9w, 30h ; '0'
0x180010953  movzx   eax, r10w
  ... truncated ...
```
