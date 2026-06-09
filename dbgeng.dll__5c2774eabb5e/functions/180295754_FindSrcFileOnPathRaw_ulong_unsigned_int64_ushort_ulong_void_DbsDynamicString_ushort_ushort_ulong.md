# FindSrcFileOnPathRaw(ulong,unsigned __int64,ushort *,ulong,void *,DbsDynamicString<ushort> *,ushort * *,ulong *)

- ea: `0x180295754`
- end: `0x180295ff9`
- name: `?FindSrcFileOnPathRaw@@YAHK_KPEAGKPEAXPEAV?$DbsDynamicString@G@@PEAPEAGPEAK@Z`
- size: `2213`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800e6ec8`

## callees

- `0x18007daa4`
- `0x18008b234`
- `0x1800c12b8`
- `0x1800f2560`
- `0x180294ac0`
- `0x180294ce0`
- `0x180295754`
- `0x180296000`
- `0x180296754`
- `0x180296d34`
- `0x180296e48`
- `0x180297e98`
- `0x1802982ac`
- `0x1802984ac`
- `0x1802e3d18`
- `0x18038605c`
- `0x180415948`
- `0x18041b198`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295c2b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295c46`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295fbe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295c2b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295c46`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180295fbe`
- `api-ms-win-crt-string-l1-1-0!_wcsdup` at `0x18029587e`
- `api-ms-win-crt-string-l1-1-0!_wcsdup` at `0x18029587e`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180295e44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180295e74`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180295e44`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180295e74`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180295e56`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180295e56`

## string_xrefs

- `0x180295820`: `    Unable to compare checksum for '%s'!\n`
- `0x180295d6b`: `    Unable to compare checksum for '%s'!\n`
- `0x180295ecc`: `    Unable to compare checksum for '%s'!\n`
- `0x1802959a1`: `Scan paths for partial path match:\n`
- `0x180295bb5`: `    Unable to compare checksum  for '%s'!\n`
- `0x180295c5d`: `Scan all paths for:\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindSrcFileOnPathRaw(
        unsigned int a1,
        unsigned __int64 a2,
        WCHAR *a3,
        char a4,
        __int64 a5,
        LPCWSTR *a6,
        _QWORD *a7,
        int *a8)
{
  __int64 v11; // r14
  unsigned int v12; // esi
  int v13; // ebx
  struct _SRCCHECKSUMINFO *v14; // r12
  const unsigned __int16 *v15; // rdx
  bool v16; // al
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // rdx
  wchar_t *PathElement; // rcx
  LPCWSTR *v20; // rbx
  unsigned __int64 v21; // r8
  unsigned int v22; // r13d
  __int64 v23; // rax
  unsigned __int16 *v24; // r15
  unsigned __int16 *v25; // r14
  wchar_t *v26; // r14
  wchar_t *v27; // r8
  unsigned __int16 *v28; // r13
  unsigned __int16 *v29; // rbx
  int v30; // r15d
  wchar_t *v31; // rax
  wchar_t *v32; // rdx
  wchar_t *v33; // rcx
  __int64 v34; // rcx
  unsigned __int16 *v35; // r12
  unsigned __int16 *v36; // rax
  unsigned __int16 *v37; // rcx
  unsigned __int16 v38; // r13
  unsigned __int16 **v39; // r8
  bool v40; // al
  Debugger::Utils *v41; // r14
  wchar_t *v42; // r15
  wchar_t *v43; // rax
  unsigned __int16 *v44; // r13
  __int64 v45; // rcx
  const unsigned __int16 *v46; // rdx
  __int64 v47; // r8
  bool v48; // zf
  bool v49; // al
  __int16 v50; // ax
  Debugger::Utils *v51; // rcx
  Debugger::Utils *v52; // rdx
  UINT v53; // r15d
  DWORD FileAttributesW; // r13d
  bool v55; // al
  bool v57[8]; // [rsp+48h] [rbp-89h] BYREF
  wchar_t *v58; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int16 *v59; // [rsp+58h] [rbp-79h]
  __int64 v60; // [rsp+60h] [rbp-71h] BYREF
  __int64 v61; // [rsp+68h] [rbp-69h]
  __int16 v62; // [rsp+70h] [rbp-61h]
  int v63; // [rsp+74h] [rbp-5Dh]
  unsigned __int16 *v64; // [rsp+78h] [rbp-59h] BYREF
  wchar_t *v65; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v66; // [rsp+88h] [rbp-49h] BYREF
  struct _SRCCHECKSUMINFO *v67; // [rsp+90h] [rbp-41h]
  unsigned __int16 *v68; // [rsp+98h] [rbp-39h]
  unsigned __int16 *v69; // [rsp+A0h] [rbp-31h] BYREF
  unsigned __int16 *v70; // [rsp+A8h] [rbp-29h]
  unsigned __int16 *v71; // [rsp+B0h] [rbp-21h]
  wchar_t *Str; // [rsp+B8h] [rbp-19h]
  __int64 v73; // [rsp+C0h] [rbp-11h]
  void **v74; // [rsp+C8h] [rbp-9h]
  char v75; // [rsp+D0h] [rbp-1h]

  v73 = -2;
  v11 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 256;
  v12 = 1;
  v63 = 64;
  FeatureUsageTracker::FeatureUsed(L"SourceSearch", L"FindSourceFile", 1u);
  v13 = a4 & 0x30;
  v14 = (struct _SRCCHECKSUMINFO *)(a5 & -(__int64)(v13 != 0));
  v67 = v14;
  LogSourceChecksum(v14);
  if ( v13 && (unsigned int)Debugger::Utils::IsAbsolutePath((Debugger::Utils *)a3, v15) && FileExists(a3) )
  {
    v57[0] = 1;
    if ( !v14
      || ((int)SrcChecksumMatches(a3, v14, v57) >= 0
        ? (v16 = v57[0])
        : (SrcOut(L"    Unable to compare checksum for '%s'!\n", a3), v16 = 0),
          v16) )
    {
      SrcOut(L"    found file '%s'\n", a3);
      if ( DbsDynamicString<unsigned short>::CopyStr(a6, a3, 0xFFFFFFFFLL) )
      {
        *a7 = a3;
        *a8 = -1;
        goto LABEL_130;
      }
LABEL_129:
      v12 = 0;
      goto LABEL_130;
    }
  }
  v17 = _wcsdup(g_SrcPath);
  v58 = v17;
  if ( !v17 )
    goto LABEL_129;
  v74 = (void **)&v58;
  v75 = 1;
  PathElement = FindPathElement(v17, a1, &v69);
  Str = PathElement;
  v20 = a6;
  if ( !PathElement )
  {
LABEL_104:
    SrcOut(L"Check plain file:\n");
    SrcOut(L"  '%s' - ", a3);
    v53 = 0;
    if ( (g_SymOptions & 0x200) != 0 )
      v53 = SetErrorMode(1u);
    FileAttributesW = GetFileAttributesW(a3);
    if ( (g_SymOptions & 0x200) != 0 )
      SetErrorMode(v53);
    if ( FileAttributesW != -1 )
    {
      if ( !DbsDynamicString<unsigned short>::CopyStr(v20, a3, 0xFFFFFFFFLL) )
      {
LABEL_127:
        if ( v58 )
          free(v58);
        goto LABEL_129;
      }
      v57[0] = 1;
      if ( !v67
        || ((int)SrcChecksumMatches(*v20, v67, v57) >= 0
          ? (v55 = v57[0])
          : (SrcOut(L"    Unable to compare checksum for '%s'!\n", *v20), v55 = 0),
            v55) )
      {
        SrcOut(L"    found '%s'\n", *v20);
        *a7 = a3;
        *a8 = -1;
        goto LABEL_65;
      }
      if ( !HIDWORD(v61) )
      {
        DbsDynamicString<unsigned short>::CopyStr(&v60, *v20, 0xFFFFFFFFLL);
        v11 = v60;
      }
      SrcOut(L"    Checksum mismatch on '%s'!\n", *v20);
    }
    if ( HIDWORD(v61) )
    {
      if ( (a4 & 0x20) == 0 )
      {
        SrcOut(L"WARNING: Unable to find source file with matching checksum.  Found '%s' with mismatch!\n", v11);
        if ( (g_SourceNoisy & 1) == 0 )
          WarnOut(L"WARNING: Unable to find source file with matching checksum.  Found '%s' with mismatch!\n", v11);
        if ( DbsDynamicString<unsigned short>::CopyStr(v20, v11, 0xFFFFFFFFLL) )
          goto LABEL_65;
      }
    }
    else
    {
      SrcOut(L"A matching source file was not found.\n");
    }
    goto LABEL_127;
  }
  if ( (a4 & 4) != 0 )
  {
    v22 = a1;
  }
  else
  {
    v21 = a2;
    v22 = a1;
    if ( (unsigned int)FindSrcFileOnServer(a1, PathElement, v21, (__int64)a3, a5, a6, a8) )
    {
      SrcOut(L"Found source file using srcsrv.\n");
      *a7 = a3;
      goto LABEL_65;
    }
  }
  v23 = -1;
  do
    ++v23;
  while ( a3[v23] );
  v24 = &a3[v23];
  if ( (unsigned int)Debugger::Utils::IsAbsolutePath((Debugger::Utils *)a3, v18) )
  {
LABEL_70:
    v41 = (Debugger::Utils *)a3;
    while ( 1 )
    {
      SrcOut(L"Scan all paths for:\n");
      SrcOut(L"  '%s'\n", v41);
      v42 = Str;
      *(_DWORD *)&v57[4] = v22;
      while ( v42 && *v42 )
      {
        v43 = wcschr(v42, 0x3Bu);
        v44 = v43;
        if ( !v43 )
        {
          v45 = -1;
          do
            ++v45;
          while ( v42[v45] );
          v44 = &v42[v45];
        }
        if ( !(unsigned __int8)IsSourceServerShare(v42, v43, 0, 0)
          && (unsigned int)SrcFileExists(v42, v44, 0, (unsigned __int16 *)v41, 0) )
        {
          v57[0] = 1;
          if ( (unsigned int)Debugger::Utils::IsAbsolutePath(v41, v46) )
            v48 = DbsDynamicString<unsigned short>::CopyStr(v20, v41, 0xFFFFFFFFLL) == 0;
          else
            v48 = (unsigned int)ConcatPathComponents(v42, v44, v47, v41, v20) == 0;
          if ( v48 )
            goto LABEL_127;
          EditPathSlashes((unsigned __int16 *)*v20);
          if ( !v67
            || ((int)SrcChecksumMatches(*v20, v67, v57) >= 0
              ? (v49 = v57[0])
              : (SrcOut(L"    Unable to compare checksum for '%s'!\n", *v20), v49 = 0),
                v49) )
          {
            SrcOut(L"    found file '%s'\n", *v20);
            *a7 = v41;
            goto LABEL_64;
          }
          if ( !HIDWORD(v61) )
            DbsDynamicString<unsigned short>::CopyStr(&v60, *v20, 0xFFFFFFFFLL);
          SrcOut(L"    Checksum mismatch on '%s'!\n", *v20);
        }
        v42 = v44;
        if ( *v44 )
          v42 = v44 + 1;
        ++*(_DWORD *)&v57[4];
      }
      v50 = *(_WORD *)v41;
      if ( !*(_WORD *)v41 )
        break;
      v51 = v41;
      v52 = v41;
      while ( v50 != 47 && v50 != 92 && (v50 != 58 || *((_WORD *)v52 + 1) == 47 || *((_WORD *)v52 + 1) == 92) )
      {
        v41 = (Debugger::Utils *)((char *)v41 + 2);
        v50 = *(_WORD *)v41;
        v51 = v41;
        v52 = v41;
        if ( !*(_WORD *)v41 )
          goto LABEL_103;
      }
      v41 = (Debugger::Utils *)((char *)v51 + 2);
      v22 = a1;
    }
LABEL_103:
    v11 = v60;
    goto LABEL_104;
  }
  do
  {
LABEL_20:
    v25 = v24;
    v68 = v24--;
    v69 = v24;
  }
  while ( v24 >= a3 && *v24 != 47 && *v24 != 92 && (*v24 != 58 || *v25 == 47 || *v25 == 92) );
  if ( v25 == a3 )
    goto LABEL_70;
  v71 = 0;
  *(_DWORD *)&v57[4] = 0;
  v66 = 0;
  v64 = 0;
  *(_WORD *)v57 = *v24;
  *v24 = 0;
  SrcOut(L"Scan paths for partial path match:\n");
  SrcOut(L"  prefix '%s'\n", a3);
  SrcOut(L"  suffix '%s'\n", v25);
  v26 = Str;
  LODWORD(v59) = v22;
  v27 = 0;
  v65 = 0;
  v28 = v24;
  v70 = v24;
  if ( !*Str )
    goto LABEL_52;
  v29 = v68;
  v30 = (int)v59;
  while ( 1 )
  {
    v31 = wcschr(v26, 0x3Bu);
    v32 = v31;
    v33 = v31;
    if ( v31 )
    {
      v35 = v31;
    }
    else
    {
      v34 = -1;
      do
        ++v34;
      while ( v26[v34] );
      v33 = &v26[v34];
      v35 = v33;
    }
    v36 = v35 - 1;
    v59 = v35 - 1;
    if ( *v33 )
      v36 = v35;
    v68 = v36;
    if ( !(unsigned __int8)IsSourceServerShare(v26, v32, 0, 0) )
    {
      if ( v35 <= v26 || (v37 = v59, v38 = *v59, *v59 != 47) && v38 != 92 )
      {
        v37 = v35;
        v38 = *v35;
        v59 = v35;
      }
      if ( v38 )
        *v37 = 0;
      MatchLongestPathComponentSuffix(v26, a3, &v66, &v64);
      SrcOut(L"    match '%s' against '%s': %d (match '%s')\n", v26, a3, v64 - a3, v64 + 1);
      *v59 = v38;
      v28 = v70;
      if ( v64 < v70 - 1 )
      {
        if ( (unsigned int)SrcFileExists(v26, v66 + 1, v39, v64 + 1, v29) )
          break;
      }
    }
    v27 = v65;
LABEL_50:
    v26 = v68 + 1;
    ++v30;
    if ( !v68[1] )
      goto LABEL_51;
  }
  v27 = v26;
  v65 = v26;
  v71 = v66 + 1;
  v28 = v64 + 1;
  v70 = v64 + 1;
  *(_DWORD *)&v57[4] = v30;
  if ( v66 >= v26 && v64 >= a3 && (a4 & 2) != 0 )
    goto LABEL_50;
LABEL_51:
  v20 = a6;
  v24 = v69;
LABEL_52:
  *v24 = *(_WORD *)v57;
  if ( !v27 )
  {
LABEL_62:
    v22 = a1;
    goto LABEL_20;
  }
  if ( (unsigned int)ConcatPathComponents(v27, v71, v27, v28, v20) )
  {
    EditPathSlashes((unsigned __int16 *)*v20);
    v57[0] = 1;
    if ( v67 )
    {
      if ( (int)SrcChecksumMatches(*v20, v67, v57) >= 0 )
      {
        v40 = v57[0];
      }
      else
      {
        SrcOut(L"    Unable to compare checksum  for '%s'!\n", *v20);
        v40 = 0;
      }
      if ( !v40 )
      {
        if ( !HIDWORD(v61) )
          DbsDynamicString<unsigned short>::CopyStr(&v60, *v20, 0xFFFFFFFFLL);
        SrcOut(L"    Checksum mismatch on '%s'!\n", *v20);
        goto LABEL_62;
      }
    }
    SrcOut(L"    found file '%s'\n", *v20);
    *a7 = v28;
LABEL_64:
    *a8 = *(_DWORD *)&v57[4];
LABEL_65:
    if ( v58 )
      free(v58);
  }
  else
  {
    if ( v58 )
      free(v58);
    v12 = 0;
  }
LABEL_130:
  DbsDynamicBuffer::Delete((DbsDynamicBuffer *)&v60);
  return v12;
}

```

## disassembly

```asm
0x180295754  mov     rax, rsp
0x180295757  mov     [rax+20h], r9d
0x18029575b  mov     [rax+8], ecx
0x18029575e  push    rbp
0x18029575f  push    rsi
0x180295760  push    rdi
0x180295761  push    r12
0x180295763  push    r13
0x180295765  push    r14
0x180295767  push    r15
0x180295769  lea     rbp, [rax-3Fh]
0x18029576d  sub     rsp, 0D0h
0x180295774  mov     [rbp+37h+var_48], 0FFFFFFFFFFFFFFFEh
0x18029577c  mov     [rax+10h], rbx
0x180295780  mov     ebx, r9d
0x180295783  mov     rdi, r8
0x180295786  mov     r13, rdx
0x180295789  xor     eax, eax
0x18029578b  mov     r14d, eax
0x18029578e  mov     [rbp+37h+var_A8], rax
0x180295792  mov     [rbp+37h+var_A0], rax
0x180295796  mov     [rbp+37h+var_98], 100h
0x18029579c  lea     esi, [rax+1]
0x18029579f  mov     [rbp+37h+var_94], 40h ; '@'
0x1802957a6  mov     r8d, esi; unsigned int
0x1802957a9  lea     rdx, aFindsourcefile; "FindSourceFile"
0x1802957b0  lea     rcx, aSourcesearch; "SourceSearch"
0x1802957b7  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1802957bc  and     ebx, 30h
0x1802957bf  mov     eax, ebx
0x1802957c1  neg     eax
0x1802957c3  sbb     r12, r12
0x1802957c6  mov     r15, [rbp+37h+arg_20]
0x1802957ca  and     r12, r15
0x1802957cd  mov     [rbp+37h+var_78], r12
0x1802957d1  mov     rcx, r12; struct _SRCCHECKSUMINFO *
0x1802957d4  call    ?LogSourceChecksum@@YAXQEAU_SRCCHECKSUMINFO@@@Z; LogSourceChecksum(_SRCCHECKSUMINFO * const)
0x1802957d9  test    ebx, ebx
0x1802957db  jz      loc_180295877
0x1802957e1  mov     rcx, rdi; this
0x1802957e4  call    ?IsAbsolutePath@Utils@Debugger@@YAHPEBG@Z; Debugger::Utils::IsAbsolutePath(ushort const *)
0x1802957e9  xor     ebx, ebx
0x1802957eb  test    eax, eax
0x1802957ed  jz      loc_180295877
0x1802957f3  mov     rcx, rdi; unsigned __int16 *
0x1802957f6  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x1802957fb  test    al, al
0x1802957fd  jz      short loc_180295877
0x1802957ff  mov     [rsp+100h+var_C0], sil
0x180295804  test    r12, r12
0x180295807  jz      short loc_180295838
0x180295809  lea     r8, [rsp+100h+var_C0]; bool *
0x18029580e  mov     rdx, r12; struct _SRCCHECKSUMINFO *
0x180295811  mov     rcx, rdi; lpFileName
0x180295814  call    ?SrcChecksumMatches@@YAJPEBGPEAU_SRCCHECKSUMINFO@@PEA_N@Z; SrcChecksumMatches(ushort const *,_SRCCHECKSUMINFO *,bool *)
0x180295819  test    eax, eax
0x18029581b  jns     short loc_180295830
0x18029581d  mov     rdx, rdi
0x180295820  lea     rcx, aUnableToCompar_0; "    Unable to compare checksum for '%s'"...
0x180295827  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x18029582c  mov     al, bl
0x18029582e  jmp     short loc_180295834
0x180295830  mov     al, [rsp+100h+var_C0]
0x180295834  test    al, al
0x180295836  jz      short loc_180295877
0x180295838  mov     rdx, rdi
0x18029583b  lea     rcx, aFoundFileS; "    found file '%s'\n"
0x180295842  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180295847  or      ebx, 0FFFFFFFFh
0x18029584a  mov     r8d, ebx
0x18029584d  mov     rdx, rdi
0x180295850  mov     rcx, [rbp+37h+arg_28]
0x180295854  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x180295859  xor     r15d, r15d
0x18029585c  test    rax, rax
0x18029585f  jz      loc_180295FCF
0x180295865  mov     rax, [rbp+37h+arg_30]
0x180295869  mov     [rax], rdi
0x18029586c  mov     rax, [rbp+37h+arg_38]
0x180295870  mov     [rax], ebx
0x180295872  jmp     loc_180295FD2
0x180295877  mov     rcx, cs:?g_SrcPath@@3PEAGEA; String
0x18029587e  call    cs:__imp__wcsdup
0x180295885  nop     dword ptr [rax+rax+00h]
0x18029588a  mov     [rsp+100h+var_B8], rax
0x18029588f  test    rax, rax
0x180295892  jz      loc_180295FCC
0x180295898  lea     rcx, [rsp+100h+var_B8]
0x18029589d  mov     [rbp+37h+var_40], rcx
0x1802958a1  mov     [rbp+37h+var_38], sil
0x1802958a5  lea     r8, [rbp+37h+var_68]; unsigned __int16 **
0x1802958a9  mov     edx, [rbp+37h+arg_0]; unsigned int
0x1802958ac  mov     rcx, rax; Str
0x1802958af  call    ?FindPathElement@@YAPEAGPEAGKPEAPEAG@Z; FindPathElement(ushort *,ulong,ushort * *)
0x1802958b4  mov     rcx, rax
0x1802958b7  mov     [rbp+37h+Str], rax
0x1802958bb  or      r12d, 0FFFFFFFFh
0x1802958bf  mov     rbx, [rbp+37h+arg_28]
0x1802958c3  test    rax, rax
0x1802958c6  jz      loc_180295E18
0x1802958cc  test    [rbp+37h+arg_18], 4
0x1802958d0  jnz     short loc_180295919
0x1802958d2  mov     rax, [rbp+37h+arg_38]
0x1802958d6  mov     [rsp+30h], rax
0x1802958db  mov     [rsp+100h+var_D8], rbx
0x1802958e0  mov     [rsp+100h+var_E0], r15
0x1802958e5  mov     r9, rdi
0x1802958e8  mov     r8, r13
0x1802958eb  mov     rdx, rcx
0x1802958ee  mov     r13d, [rbp+37h+arg_0]
0x1802958f2  mov     ecx, r13d
0x1802958f5  call    ?FindSrcFileOnServer@@YAHKPEAG_K0PEAXPEAV?$DbsDynamicString@G@@PEAK@Z; FindSrcFileOnServer(ulong,ushort *,unsigned __int64,ushort *,void *,DbsDynamicString<ushort> *,ulong *)
0x1802958fa  xor     r14d, r14d
0x1802958fd  test    eax, eax
0x1802958ff  jz      short loc_180295920
0x180295901  lea     rcx, aFoundSourceFil; "Found source file using srcsrv.\n"
0x180295908  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x18029590d  mov     rax, [rbp+37h+arg_30]
0x180295911  mov     [rax], rdi
0x180295914  jmp     loc_180295C1D
0x180295919  mov     r13d, [rbp+37h+arg_0]
0x18029591d  xor     r14d, r14d
0x180295920  or      rax, 0FFFFFFFFFFFFFFFFh
0x180295924  inc     rax
0x180295927  cmp     [rdi+rax*2], r14w
0x18029592c  jnz     short loc_180295924
0x18029592e  lea     r15, [rdi+rax*2]
0x180295932  mov     rcx, rdi; this
0x180295935  call    ?IsAbsolutePath@Utils@Debugger@@YAHPEBG@Z; Debugger::Utils::IsAbsolutePath(ushort const *)
0x18029593a  xor     ecx, ecx
0x18029593c  test    eax, eax
0x18029593e  jnz     loc_180295C5A
0x180295944  mov     r14, r15
0x180295947  mov     [rbp+37h+var_70], r15
0x18029594b  add     r15, 0FFFFFFFFFFFFFFFEh
0x18029594f  mov     [rbp+37h+var_68], r15
0x180295953  cmp     r15, rdi
0x180295956  jb      short loc_18029597B
0x180295958  cmp     word ptr [r15], 2Fh ; '/'
0x18029595d  jz      short loc_18029597B
0x18029595f  cmp     word ptr [r15], 5Ch ; '\'
0x180295964  jz      short loc_18029597B
0x180295966  cmp     word ptr [r15], 3Ah ; ':'
0x18029596b  jnz     short loc_180295944
0x18029596d  cmp     word ptr [r14], 2Fh ; '/'
0x180295972  jz      short loc_180295944
0x180295974  cmp     word ptr [r14], 5Ch ; '\'
0x180295979  jz      short loc_180295944
0x18029597b  cmp     r14, rdi
0x18029597e  jz      loc_180295C5A
0x180295984  mov     [rbp+37h+var_58], rcx
0x180295988  mov     dword ptr [rsp+100h+var_C0+4], ecx
0x18029598c  mov     [rbp+37h+var_80], rcx
0x180295990  mov     [rbp+37h+var_90], rcx
0x180295994  movzx   eax, word ptr [r15]
0x180295998  mov     word ptr [rsp+100h+var_C0], ax
0x18029599d  mov     [r15], cx
0x1802959a1  lea     rcx, aScanPathsForPa; "Scan paths for partial path match:\n"
0x1802959a8  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x1802959ad  mov     rdx, rdi
0x1802959b0  lea     rcx, aPrefixS; "  prefix '%s'\n"
0x1802959b7  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x1802959bc  mov     rdx, r14
0x1802959bf  lea     rcx, aSuffixS; "  suffix '%s'\n"
0x1802959c6  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x1802959cb  mov     rax, [rbp+37h+Str]
0x1802959cf  mov     r14, rax
0x1802959d2  mov     dword ptr [rbp+37h+var_B0], r13d
0x1802959d6  xor     ecx, ecx
0x1802959d8  mov     r8d, ecx
0x1802959db  mov     [rbp+37h+var_88], rcx
0x1802959df  mov     r13, r15
0x1802959e2  mov     [rbp+37h+var_60], r15
0x1802959e6  cmp     [rax], cx
0x1802959e9  jz      loc_180295B57
0x1802959ef  mov     rbx, [rbp+37h+var_70]
0x1802959f3  mov     r15d, dword ptr [rbp+37h+var_B0]
0x1802959f7  xor     r12d, r12d
0x1802959fa  mov     edx, 3Bh ; ';'; Ch
0x1802959ff  mov     rcx, r14; Str
0x180295a02  call    wcschr
0x180295a07  mov     rdx, rax
0x180295a0a  mov     rcx, rax
0x180295a0d  test    rax, rax
0x180295a10  jnz     short loc_180295A29
0x180295a12  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180295a16  inc     rcx
0x180295a19  cmp     [r14+rcx*2], r12w
0x180295a1e  jnz     short loc_180295A16
0x180295a20  lea     rcx, [r14+rcx*2]
0x180295a24  mov     r12, rcx
0x180295a27  jmp     short loc_180295A2C
0x180295a29  mov     r12, rdx
0x180295a2c  lea     rax, [r12-2]
0x180295a31  mov     [rbp+37h+var_B0], rax
0x180295a35  xor     r8d, r8d
0x180295a38  cmp     [rcx], r8w
0x180295a3c  cmovnz  rax, r12
0x180295a40  mov     [rbp+37h+var_70], rax
0x180295a44  xor     r9d, r9d
0x180295a47  mov     rcx, r14
0x180295a4a  call    ?IsSourceServerShare@@YA_NPEBG0PEAV?$DbsDeclDynamicString@G$0MI@$00@@1@Z; IsSourceServerShare(ushort const *,ushort const *,DbsDeclDynamicString<ushort,200,1> *,DbsDeclDynamicString<ushort,200,1> *)
0x180295a4f  test    al, al
0x180295a51  jnz     loc_180295B2F
0x180295a57  cmp     r12, r14
0x180295a5a  jbe     short loc_180295A72
0x180295a5c  mov     rcx, [rbp+37h+var_B0]
0x180295a60  movzx   r13d, word ptr [rcx]
0x180295a64  cmp     r13w, 2Fh ; '/'
0x180295a69  jz      short loc_180295A7E
0x180295a6b  cmp     r13w, 5Ch ; '\'
0x180295a70  jz      short loc_180295A7E
0x180295a72  mov     rcx, r12
0x180295a75  movzx   r13d, word ptr [r12]
0x180295a7a  mov     [rbp+37h+var_B0], rcx
0x180295a7e  xor     r12d, r12d
0x180295a81  test    r13w, r13w
0x180295a85  jz      short loc_180295A8B
0x180295a87  mov     [rcx], r12w
0x180295a8b  lea     r9, [rbp+37h+var_90]; unsigned __int16 **
0x180295a8f  lea     r8, [rbp+37h+var_80]; unsigned __int16 **
0x180295a93  mov     rdx, rdi; unsigned __int16 *
0x180295a96  mov     rcx, r14; unsigned __int16 *
0x180295a99  call    ?MatchLongestPathComponentSuffix@@YAHPEAG0PEAPEAG1@Z; MatchLongestPathComponentSuffix(ushort *,ushort *,ushort * *,ushort * *)
0x180295a9e  mov     r9, [rbp+37h+var_90]
0x180295aa2  lea     rax, [r9+2]
0x180295aa6  sub     r9, rdi
0x180295aa9  sar     r9, 1
0x180295aac  mov     [rsp+100h+var_E0], rax
0x180295ab1  mov     r8, rdi
0x180295ab4  mov     rdx, r14
0x180295ab7  lea     rcx, aMatchSAgainstS; "    match '%s' against '%s': %d (match "...
0x180295abe  call    ?SrcOut@@YAXPEBGZZ; SrcOut(ushort const *,...)
0x180295ac3  mov     rax, [rbp+37h+var_B0]
0x180295ac7  mov     [rax], r13w
0x180295acb  mov     r13, [rbp+37h+var_60]
0x180295acf  lea     rax, [r13-2]
0x180295ad3  mov     r9, [rbp+37h+var_90]
0x180295ad7  cmp     r9, rax
0x180295ada  jnb     short loc_180295B32
0x180295adc  add     r9, 2; unsigned __int16 *
0x180295ae0  mov     rdx, [rbp+37h+var_80]
0x180295ae4  add     rdx, 2; unsigned __int16 *
0x180295ae8  mov     [rsp+100h+var_E0], rbx; unsigned __int16 *
0x180295aed  mov     rcx, r14; String2
0x180295af0  call    ?SrcFileExists@@YAHPEAG0PEAPEAG00@Z; SrcFileExists(ushort *,ushort *,ushort * *,ushort *,ushort *)
0x180295af5  test    eax, eax
0x180295af7  jz      short loc_180295B32
0x180295af9  mov     r8, r14
0x180295afc  mov     [rbp+37h+var_88], r14
0x180295b00  mov     rax, [rbp+37h+var_80]
0x180295b04  lea     rcx, [rax+2]
0x180295b08  mov     [rbp+37h+var_58], rcx
0x180295b0c  mov     rcx, [rbp+37h+var_90]
0x180295b10  lea     r13, [rcx+2]
0x180295b14  mov     [rbp+37h+var_60], r13
0x180295b18  mov     dword ptr [rsp+100h+var_C0+4], r15d
0x180295b1d  cmp     rax, r14
0x180295b20  jb      short loc_180295B4B
0x180295b22  cmp     rcx, rdi
0x180295b25  jb      short loc_180295B4B
0x180295b27  test    [rbp+37h+arg_18], 2
0x180295b2b  jz      short loc_180295B4B
0x180295b2d  jmp     short loc_180295B36
0x180295b2f  xor     r12d, r12d
0x180295b32  mov     r8, [rbp+37h+var_88]
0x180295b36  mov     r14, [rbp+37h+var_70]
0x180295b3a  add     r14, 2
0x180295b3e  add     r15d, esi
0x180295b41  cmp     [r14], r12w
0x180295b45  jnz     loc_1802959FA
0x180295b4b  mov     rbx, [rbp+37h+arg_28]
0x180295b4f  mov     r15, [rbp+37h+var_68]
0x180295b53  or      r12d, 0FFFFFFFFh
0x180295b57  movzx   eax, word ptr [rsp+100h+var_C0]
0x180295b5c  mov     [r15], ax
0x180295b60  xor     r14d, r14d
0x180295b63  test    r8, r8
0x180295b66  jz      loc_180295BF2
0x180295b6c  mov     [rsp+100h+var_E0], rbx
0x180295b71  mov     r9, r13
0x180295b74  mov     rdx, [rbp+37h+var_58]
0x180295b78  mov     rcx, r8
0x180295b7b  call    ?ConcatPathComponents@@YAHPEAG0PEAPEAG0PEAV?$DbsDynamicString@G@@@Z; ConcatPathComponents(ushort *,ushort *,ushort * *,ushort *,DbsDynamicString<ushort> *)
0x180295b80  test    eax, eax
0x180295b82  jz      loc_180295C3C
0x180295b88  mov     rcx, [rbx]; unsigned __int16 *
0x180295b8b  call    ?EditPathSlashes@@YAXPEAG@Z; EditPathSlashes(ushort *)
0x180295b90  mov     [rsp+100h+var_C0], sil
0x180295b95  mov     rax, [rbp+37h+var_78]
0x180295b99  test    rax, rax
0x180295b9c  jz      short loc_180295BFD
0x180295b9e  lea     r8, [rsp+100h+var_C0]; bool *
0x180295ba3  mov     rdx, rax; struct _SRCCHECKSUMINFO *
0x180295ba6  mov     rcx, [rbx]; lpFileName
0x180295ba9  call    ?SrcChecksumMatches@@YAJPEBGPEAU_SRCCHECKSUMINFO@@PEA_N@Z; SrcChecksumMatches(ushort const *,_SRCCHECKSUMINFO *,bool *)
0x180295bae  test    eax, eax
0x180295bb0  jns     short loc_180295BC6
0x180295bb2  mov     rdx, [rbx]
0x180295bb5  lea     rcx, aUnableToCompar; "    Unable to compare checksum  for '%s"...
  ... truncated ...
```
