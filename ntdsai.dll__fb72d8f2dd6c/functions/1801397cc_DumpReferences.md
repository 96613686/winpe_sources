# DumpReferences

- ea: `0x1801397cc`
- end: `0x18013a029`
- name: `DumpReferences`
- size: `2141`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180066310`

## callees

- `0x180006330`
- `0x1800067d0`
- `0x18000dc7c`
- `0x18000ef30`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180034894`
- `0x18003ce4c`
- `0x18003da6c`
- `0x1800f80e0`
- `0x1800f8280`
- `0x1800fc54c`
- `0x180133608`
- `0x18013572c`
- `0x1801397cc`
- `0x18013b4d4`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1801c4a34`
- `0x1801d0ea0`
- `0x1801d614c`
- `0x18047b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1801398af`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1801398af`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1801398e5`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1801398e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180139fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18045f9cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180139fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18045f9cb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139cd7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139cfc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139d1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139d3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139cd7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139cfc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139d1c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180139d3c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180139989`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180139989`

## string_xrefs

- `0x180139a5c`: `CreateFile`
- `0x180139e19`: `Error: could not move cursor to the next record in database (Jet Error %lld)\n`
- `0x180139cd0`: `Non-linked references to `

## pseudocode

```c
int __fastcall DumpReferences(__int64 a1, __int64 a2)
{
  void *v3; // r15
  __int64 v4; // r13
  int v5; // r14d
  __int64 v6; // rsi
  __int64 FileA; // rdi
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // r9
  int v11; // r8d
  int v12; // r9d
  char *v13; // rax
  char *v14; // rax
  __int64 v15; // rbx
  LPOVERLAPPED v16; // rbx
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  const char *v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // r8
  unsigned int v27; // eax
  LPOVERLAPPED v28; // r14
  int result; // eax
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-5A0h] BYREF
  unsigned int v31; // [rsp+4Ch] [rbp-59Ch]
  int v32; // [rsp+50h] [rbp-598h] BYREF
  _DWORD v33[3]; // [rsp+54h] [rbp-594h] BYREF
  int v34[2]; // [rsp+60h] [rbp-588h] BYREF
  __int64 v35; // [rsp+68h] [rbp-580h]
  int v36[2]; // [rsp+70h] [rbp-578h]
  int v37; // [rsp+78h] [rbp-570h] BYREF
  unsigned int v38; // [rsp+7Ch] [rbp-56Ch]
  void *v39; // [rsp+80h] [rbp-568h]
  __int64 v40; // [rsp+88h] [rbp-560h]
  __int64 v41; // [rsp+90h] [rbp-558h] BYREF
  __int64 v42; // [rsp+98h] [rbp-550h]
  void *v43; // [rsp+A0h] [rbp-548h]
  __int64 v44; // [rsp+B0h] [rbp-538h] BYREF
  int v45; // [rsp+B8h] [rbp-530h]
  DWORD Offset; // [rsp+BCh] [rbp-52Ch]
  int v47; // [rsp+C0h] [rbp-528h]
  int v48; // [rsp+C8h] [rbp-520h]
  int v49; // [rsp+CCh] [rbp-51Ch]
  __int64 v50; // [rsp+D0h] [rbp-518h]
  __int64 v51; // [rsp+D8h] [rbp-510h]
  __int64 v52; // [rsp+E0h] [rbp-508h]
  __int64 v53; // [rsp+F0h] [rbp-4F8h]
  int v54; // [rsp+F8h] [rbp-4F0h]
  int *v55; // [rsp+108h] [rbp-4E0h]
  __int64 v56; // [rsp+110h] [rbp-4D8h] BYREF
  int v57; // [rsp+118h] [rbp-4D0h]
  DWORD v58; // [rsp+11Ch] [rbp-4CCh]
  int v59; // [rsp+120h] [rbp-4C8h]
  int v60; // [rsp+128h] [rbp-4C0h]
  int v61; // [rsp+12Ch] [rbp-4BCh]
  __int64 v62; // [rsp+130h] [rbp-4B8h]
  __int64 v63; // [rsp+138h] [rbp-4B0h]
  __int64 v64; // [rsp+140h] [rbp-4A8h]
  __int64 v65; // [rsp+150h] [rbp-498h]
  int v66; // [rsp+158h] [rbp-490h]
  int *v67; // [rsp+168h] [rbp-480h]
  int v68; // [rsp+170h] [rbp-478h] BYREF
  __int64 *v69; // [rsp+178h] [rbp-470h]
  __int64 v70; // [rsp+188h] [rbp-460h] BYREF
  int v71; // [rsp+190h] [rbp-458h]
  void *v72; // [rsp+198h] [rbp-450h]
  int v73; // [rsp+390h] [rbp-258h] BYREF
  const char *v74; // [rsp+398h] [rbp-250h]
  int v75; // [rsp+3B0h] [rbp-238h]
  __int64 LastError; // [rsp+3C8h] [rbp-220h]

  *(_QWORD *)v36 = a2;
  v35 = a1;
  NumberOfBytesWritten = 0;
  v32 = 0;
  *(_QWORD *)v34 = 0;
  v37 = 0;
  v33[0] = -1;
  v41 = 0;
  v3 = 0;
  v39 = 0;
  v4 = 0;
  v40 = 0;
  v5 = 0;
  v6 = 0;
  *(_QWORD *)&v33[1] = 0;
  FileA = -1;
  v42 = -1;
  v8 = DumpAccessCheck();
  LODWORD(v9) = v8;
  if ( v8 )
  {
    v10 = 52499292;
LABEL_3:
    DoSetSvcError(5012, v8, 0, v10);
    goto LABEL_61;
  }
  v8 = ImpersonateAnyClient();
  LODWORD(v9) = v8;
  if ( v8 )
  {
    v10 = 52499303;
    goto LABEL_3;
  }
  v5 = 1;
  v13 = strrchr(szJetFilePath, 92);
  if ( !v13 )
  {
    LODWORD(v9) = 161;
    DoSetSvcError(5012, 161, 0, 52499310);
    goto LABEL_61;
  }
  v14 = strchr(v13, 46);
  if ( v14 )
  {
    LODWORD(v15) = (_DWORD)v14 - (unsigned int)szJetFilePath;
  }
  else
  {
    v15 = -1;
    do
      ++v15;
    while ( szJetFilePath[v15] );
  }
  v43 = (void *)THAlloc_(a1, 1, (int)v15 + 9, 1, 0, 52499328);
  memcpy_0(v43, szJetFilePath, (int)v15);
  StringCchCopyA((STRSAFE_LPSTR)v43 + (int)v15, (int)v15 + 9, ".ref.dmp");
  FileA = (__int64)CreateFileA((LPCSTR)v43, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v42 = FileA;
  UnImpersonateAnyClient();
  if ( FileA == -1 )
  {
    v5 = 0;
    v16 = gpDsEventConfig;
    if ( gpDsEventConfig )
    {
      if ( (gpDsEventConfig[4].OffsetHigh & 0x80000000) == 0
        || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(801, 0) )
      {
        goto LABEL_19;
      }
      if ( (unsigned int)DoLogMsgOverride(3221226875LL) )
      {
        v16 = gpDsEventConfig;
LABEL_19:
        memset_0(&v44, 0, 0x60u);
        v44 = 0;
        Offset = v16[4].Offset;
        v47 = 0;
        v45 = -1073740421;
        v48 = 0;
        v49 = 1;
        v55 = &v73;
        v73 = 0;
        v74 = "CreateFile";
        v44 = 1;
        v75 = 3;
        LastError = GetLastError();
        *(_QWORD *)&v55[8 * v44 + 2] = &v55[8 * v44 + 6];
        ++v44;
        v52 = 0;
        v51 = 801;
        v50 = 1;
        v53 = 0;
        v54 = 0;
        DoLogEventAndTrace(&v44);
      }
    }
    LODWORD(v9) = 31;
    goto LABEL_61;
  }
  v5 = 0;
  DBOpen2(1, &v33[1]);
  v17 = *(_QWORD *)v36;
  v18 = DsaSafeAdd(*(unsigned int *)(*(_QWORD *)v36 + 16LL), 1);
  v3 = (void *)THAlloc_(a1, 1, v18, 1, 0, 52499371);
  v39 = v3;
  memcpy_0(v3, *(const void **)(v17 + 8), *(unsigned int *)(v17 + 16));
  *((_BYTE *)v3 + *(unsigned int *)(v17 + 16)) = 0;
  v19 = -1;
  do
    ++v19;
  while ( *((_BYTE *)v3 + v19) );
  v20 = UnicodeStringFromString8Ex(0, 65001, v3, v19 + 1, 0);
  v4 = v20;
  v40 = v20;
  if ( !v20 )
  {
    if ( GetLastError() )
      LODWORD(v9) = GetLastError();
    else
      LODWORD(v9) = 31;
    DumpErrorMessageLLD(FileA, "Error: Could not convert dsname string to Unicode. (Error %lld)\n", (unsigned int)v9);
    goto LABEL_28;
  }
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(v20 + 2 * v21) );
  LODWORD(v9) = UserFriendlyNameToDSNameEx(v20, v21, 0, (unsigned int)&v41, 0);
  if ( (_DWORD)v9 )
  {
    DumpErrorMessageLLD(FileA, "Error: Could not convert dsname string to dsname. (Error %lld)\n", (unsigned int)v9);
LABEL_28:
    v6 = *(_QWORD *)&v33[1];
    goto LABEL_61;
  }
  v6 = *(_QWORD *)&v33[1];
  v22 = DBFindDSName(*(_QWORD *)&v33[1], v41);
  v9 = v22;
  if ( v22 && v22 != 8352 )
  {
    v23 = "Error: Could not locate target dsname in DIT. (Error %lld)\n";
    goto LABEL_36;
  }
  v36[0] = *(_DWORD *)(v6 + 24);
  v25 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pFnJetSetCurrentIndexA)(
          *(_QWORD *)(v6 + 40),
          *(_QWORD *)(v6 + 64),
          0);
  v9 = v25;
  if ( !v25 )
  {
    LODWORD(v9) = GetReferenceAtts(a1, &v32, v34);
    if ( (_DWORD)v9 )
    {
      DumpErrorMessageLLD(FileA, "Error: failed to get list of reference attributes (Error %lld)\n", (unsigned int)v9);
      goto LABEL_61;
    }
    WriteFile((HANDLE)FileA, "Non-linked references to ", 0x19u, &NumberOfBytesWritten, 0);
    v26 = -1;
    do
      ++v26;
    while ( *((_BYTE *)v3 + v26) );
    WriteFile((HANDLE)FileA, v3, v26, &NumberOfBytesWritten, 0);
    WriteFile((HANDLE)FileA, "\n\nDNT\tAttribute(s)", 0x12u, &NumberOfBytesWritten, 0);
    WriteFile((HANDLE)FileA, "\r\n", 2u, &NumberOfBytesWritten, 0);
    v31 = 0;
    v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD))pFnJetMove)(
            *(_QWORD *)(v6 + 40),
            *(_QWORD *)(v6 + 64),
            0x80000000LL,
            0);
    v38 = v27;
    while ( !v27 )
    {
      LODWORD(v9) = DumpAttsThatReferToDNT(a1, v6, v32, v34[0], (__int64)&v37, v36[0], (__int64)v33, (HANDLE)FileA);
      if ( (_DWORD)v9 )
      {
        DumpErrorMessageLLD(
          FileA,
          "Error: failed to check for attributes of object %lld that refer to target, continuing.\n",
          v33[0]);
        DumpErrorMessageLLD(FileA, "\tExtended Error: error code %d\n", v9);
      }
      else
      {
        ++v31;
      }
      v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))pFnJetMove)(*(_QWORD *)(v6 + 40), *(_QWORD *)(v6 + 64), 1);
      v38 = v27;
      if ( v27 == -1603 )
        goto LABEL_53;
    }
    if ( v27 != -1603 )
    {
      LODWORD(v9) = v27;
      v24 = v27;
      v23 = "Error: could not move cursor to the next record in database (Jet Error %lld)\n";
      goto LABEL_37;
    }
LABEL_53:
    v28 = gpDsEventConfig;
    if ( !gpDsEventConfig )
      goto LABEL_60;
    if ( (gpDsEventConfig[4].OffsetHigh & 0x80000000) != 0
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(801, 0)) )
    {
      if ( !(unsigned int)DoLogMsgOverride(1073743226) )
      {
LABEL_60:
        v5 = 0;
        goto LABEL_61;
      }
      v28 = gpDsEventConfig;
    }
    memset_0(&v56, 0, 0x60u);
    v56 = 0;
    v58 = v28[4].Offset;
    v59 = 0;
    v57 = 1073743226;
    v60 = 0;
    v61 = 1;
    v67 = &v68;
    v68 = 3;
    v70 = v31;
    v69 = &v70;
    v71 = 0;
    v72 = v43;
    v56 = 2;
    v64 = 0;
    v63 = 801;
    v62 = 1;
    v65 = 0;
    v66 = 0;
    DoLogEventAndTrace(&v56);
    goto LABEL_60;
  }
  v23 = "Error: could not set the current database index (Jet Error %lld)\n";
LABEL_36:
  v24 = v9;
LABEL_37:
  DumpErrorMessageLLD(FileA, v23, v24);
LABEL_61:
  result = v34[0];
  if ( *(_QWORD *)v34 )
    result = THFreeAux(a1, v34[0], v11, v12, 52499564);
  if ( v3 )
    result = THFreeAux(a1, (_DWORD)v3, v11, v12, 52499568);
  if ( v4 )
    result = THFreeAux(a1, v4, v11, v12, 52499572);
  if ( v6 )
  {
    result = DBClose(v6, 0);
    LODWORD(v9) = result;
  }
  if ( FileA != -1 )
    result = CloseHandle((HANDLE)FileA);
  if ( v5 )
    result = UnImpersonateAnyClient();
  if ( (_DWORD)v9 )
  {
    if ( !*(_DWORD *)(a1 + 5560) )
      return DoSetSvcError(5012, 8341, (unsigned int)v9, 52499599);
  }
  return result;
}

```

## disassembly

```asm
0x1801397cc  mov     r11, rsp
0x1801397cf  mov     [r11+18h], rbx
0x1801397d3  mov     [r11+20h], rsi
0x1801397d7  push    rdi
0x1801397d8  push    r12
0x1801397da  push    r13
0x1801397dc  push    r14
0x1801397de  push    r15
0x1801397e0  sub     rsp, 5C0h
0x1801397e7  mov     rax, cs:__security_cookie
0x1801397ee  xor     rax, rsp
0x1801397f1  mov     [rsp+5E8h+var_38], rax
0x1801397f9  mov     qword ptr [rsp+5E8h+var_578], rdx
0x1801397fe  mov     r12, rcx
0x180139801  mov     [rsp+5E8h+var_580], rcx
0x180139806  xor     eax, eax
0x180139808  mov     [rsp+5E8h+NumberOfBytesWritten], eax
0x18013980c  mov     [rsp+5E8h+var_5A8], eax
0x180139810  mov     [rsp+5E8h+var_598], eax
0x180139814  mov     qword ptr [rsp+5E8h+var_588], rax
0x180139819  mov     dword ptr [rsp+5E8h+var_570], eax
0x18013981d  mov     dword ptr [rsp+5E8h+var_594], 0FFFFFFFFh
0x180139825  mov     [r11-558h], rax
0x18013982c  mov     r15d, eax
0x18013982f  mov     [r11-568h], rax
0x180139836  mov     r13d, eax
0x180139839  mov     [r11-560h], rax
0x180139840  mov     r14d, eax
0x180139843  mov     [rsp+5E8h+var_5A4], eax
0x180139847  mov     esi, eax
0x180139849  mov     qword ptr [rsp+5E8h+var_594+4], rax
0x18013984e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180139852  mov     [r11-550h], rdi
0x180139859  call    DumpAccessCheck
0x18013985e  mov     ebx, eax
0x180139860  mov     [rsp+5E8h+var_5A8], eax
0x180139864  test    eax, eax
0x180139866  jz      short loc_180139882
0x180139868  mov     r9d, 321135Ch
0x18013986e  mov     ecx, 1394h
0x180139873  xor     r8d, r8d
0x180139876  mov     edx, eax
0x180139878  call    DoSetSvcError
0x18013987d  jmp     loc_180139F5C
0x180139882  call    ImpersonateAnyClient
0x180139887  mov     ebx, eax
0x180139889  mov     [rsp+5E8h+var_5A8], eax
0x18013988d  test    eax, eax
0x18013988f  jz      short loc_180139899
0x180139891  mov     r9d, 3211367h
0x180139897  jmp     short loc_18013986E
0x180139899  mov     r14d, 1
0x18013989f  mov     [rsp+5E8h+var_5A4], r14d
0x1801398a4  lea     edx, [r14+5Bh]; Ch
0x1801398a8  lea     rcx, szJetFilePath; Str
0x1801398af  call    cs:__imp_strrchr
0x1801398b5  test    rax, rax
0x1801398b8  jnz     short loc_1801398DD
0x1801398ba  mov     ecx, 1394h
0x1801398bf  mov     r9d, 321136Eh
0x1801398c5  xor     r8d, r8d
0x1801398c8  mov     ebx, 0A1h
0x1801398cd  mov     edx, ebx
0x1801398cf  call    DoSetSvcError
0x1801398d4  mov     [rsp+5E8h+var_5A8], ebx
0x1801398d8  jmp     loc_180139F5C
0x1801398dd  mov     edx, 2Eh ; '.'; Val
0x1801398e2  mov     rcx, rax; Str
0x1801398e5  call    cs:__imp_strchr
0x1801398eb  mov     rbx, rax
0x1801398ee  xor     ecx, ecx
0x1801398f0  test    rax, rax
0x1801398f3  lea     rax, szJetFilePath
0x1801398fa  jz      short loc_180139900
0x1801398fc  sub     ebx, eax
0x1801398fe  jmp     short loc_18013990C
0x180139900  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180139904  inc     rbx
0x180139907  cmp     [rax+rbx], cl
0x18013990a  jnz     short loc_180139904
0x18013990c  lea     eax, [rbx+9]
0x18013990f  movsxd  rdi, eax
0x180139912  mov     [rsp+5E8h+dwFlagsAndAttributes], 3211380h
0x18013991a  mov     [rsp+5E8h+dwCreationDisposition], ecx
0x18013991e  mov     r9d, r14d
0x180139921  mov     r8, rdi
0x180139924  mov     rdx, r14
0x180139927  mov     rcx, r12
0x18013992a  call    THAlloc_
0x18013992f  mov     r14, rax
0x180139932  mov     [rsp+5E8h+var_548], rax
0x18013993a  movsxd  rbx, ebx
0x18013993d  mov     r8, rbx; Size
0x180139940  lea     rdx, szJetFilePath; Src
0x180139947  mov     rcx, rax; void *
0x18013994a  call    memcpy_0
0x18013994f  lea     rcx, [rbx+r14]; pszDest
0x180139953  lea     r8, aRefDmp; ".ref.dmp"
0x18013995a  mov     rdx, rdi; cchDest
0x18013995d  call    StringCchCopyA
0x180139962  mov     [rsp+5E8h+hTemplateFile], 0; hTemplateFile
0x18013996b  mov     [rsp+5E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180139973  mov     [rsp+5E8h+dwCreationDisposition], 2; dwCreationDisposition
0x18013997b  xor     r9d, r9d; lpSecurityAttributes
0x18013997e  xor     r8d, r8d; dwShareMode
0x180139981  mov     edx, 40000000h; dwDesiredAccess
0x180139986  mov     rcx, r14; lpFileName
0x180139989  call    cs:__imp_CreateFileA
0x18013998f  mov     rdi, rax
0x180139992  mov     [rsp+5E8h+var_550], rax
0x18013999a  call    UnImpersonateAnyClient
0x18013999f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801399a3  jnz     loc_180139B0D
0x1801399a9  xor     eax, eax
0x1801399ab  mov     r14d, eax
0x1801399ae  mov     [rsp+5E8h+var_5A4], eax
0x1801399b2  mov     rbx, cs:gpDsEventConfig
0x1801399b9  test    rbx, rbx
0x1801399bc  jz      loc_180139B03
0x1801399c2  cmp     [rbx+94h], eax
0x1801399c8  jge     short loc_1801399F8
0x1801399ca  cmp     [rbx+4], eax
0x1801399cd  jz      short loc_1801399DF
0x1801399cf  xor     edx, edx
0x1801399d1  mov     ecx, 321h
0x1801399d6  call    DoLogOverride
0x1801399db  test    eax, eax
0x1801399dd  jnz     short loc_1801399F8
0x1801399df  mov     ecx, 0C000057Bh
0x1801399e4  call    DoLogMsgOverride
0x1801399e9  test    eax, eax
0x1801399eb  jz      loc_180139B03
0x1801399f1  mov     rbx, cs:gpDsEventConfig
0x1801399f8  xor     edx, edx; Val
0x1801399fa  lea     r8d, [rdx+60h]; Size
0x1801399fe  lea     rcx, [rsp+5E8h+var_538]; void *
0x180139a06  call    memset_0
0x180139a0b  mov     [rsp+5E8h+var_538], r14
0x180139a13  mov     eax, [rbx+90h]
0x180139a19  mov     [rsp+5E8h+var_52C], eax
0x180139a20  xor     ebx, ebx
0x180139a22  mov     [rsp+5E8h+var_528], ebx
0x180139a29  mov     [rsp+5E8h+var_530], 0C000057Bh
0x180139a34  mov     [rsp+5E8h+var_520], ebx
0x180139a3b  lea     ecx, [rbx+1]
0x180139a3e  mov     [rsp+5E8h+var_51C], ecx
0x180139a45  lea     rax, [rsp+5E8h+var_258]
0x180139a4d  mov     [rsp+5E8h+var_4E0], rax
0x180139a55  mov     [rsp+5E8h+var_258], ebx
0x180139a5c  lea     rax, aCreatefile; "CreateFile"
0x180139a63  mov     [rsp+5E8h+var_250], rax
0x180139a6b  mov     [rsp+5E8h+var_538], rcx
0x180139a73  mov     [rsp+5E8h+var_238], 3
0x180139a7e  call    cs:__imp_GetLastError
0x180139a84  mov     edx, eax
0x180139a86  mov     rcx, [rsp+5E8h+var_538]
0x180139a8e  shl     rcx, 5
0x180139a92  mov     rax, [rsp+5E8h+var_4E0]
0x180139a9a  mov     [rcx+rax+18h], rdx
0x180139a9f  mov     rdx, [rsp+5E8h+var_538]
0x180139aa7  shl     rdx, 5
0x180139aab  mov     rcx, [rsp+5E8h+var_4E0]
0x180139ab3  lea     rax, [rcx+18h]
0x180139ab7  add     rax, rdx
0x180139aba  mov     [rdx+rcx+8], rax
0x180139abf  inc     [rsp+5E8h+var_538]
0x180139ac7  mov     [rsp+5E8h+var_508], rbx
0x180139acf  mov     [rsp+5E8h+var_510], 321h
0x180139adb  mov     [rsp+5E8h+var_518], 1
0x180139ae7  mov     [rsp+5E8h+var_4F8], rbx
0x180139aef  mov     [rsp+5E8h+var_4F0], ebx
0x180139af6  lea     rcx, [rsp+5E8h+var_538]
0x180139afe  call    DoLogEventAndTrace
0x180139b03  mov     ebx, 1Fh
0x180139b08  jmp     loc_1801398D4
0x180139b0d  xor     esi, esi
0x180139b0f  mov     r14d, esi
0x180139b12  mov     [rsp+5E8h+var_5A4], esi
0x180139b16  lea     rdx, [rsp+5E8h+var_594+4]
0x180139b1b  lea     r15d, [rsi+1]
0x180139b1f  mov     ecx, r15d
0x180139b22  call    DBOpen2
0x180139b27  mov     rbx, qword ptr [rsp+5E8h+var_578]
0x180139b2c  mov     ecx, [rbx+10h]
0x180139b2f  mov     edx, r15d
0x180139b32  call    DsaSafeAdd
0x180139b37  mov     r8d, eax
0x180139b3a  mov     [rsp+5E8h+dwFlagsAndAttributes], 32113ABh
0x180139b42  mov     [rsp+5E8h+dwCreationDisposition], esi
0x180139b46  mov     r9d, r15d
0x180139b49  mov     edx, r15d
0x180139b4c  mov     rcx, r12
0x180139b4f  call    THAlloc_
0x180139b54  mov     r15, rax
0x180139b57  mov     [rsp+5E8h+var_568], rax
0x180139b5f  mov     r8d, [rbx+10h]; Size
0x180139b63  mov     rdx, [rbx+8]; Src
0x180139b67  mov     rcx, rax; void *
0x180139b6a  call    memcpy_0
0x180139b6f  mov     ecx, [rbx+10h]
0x180139b72  mov     [rcx+r15], sil
0x180139b76  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180139b7a  mov     r9, rbx
0x180139b7d  inc     r9
0x180139b80  cmp     [r15+r9], sil
0x180139b84  jnz     short loc_180139B7D
0x180139b86  inc     r9
0x180139b89  mov     qword ptr [rsp+5E8h+dwCreationDisposition], rsi
0x180139b8e  mov     r8, r15
0x180139b91  mov     edx, 0FDE9h
0x180139b96  xor     ecx, ecx
0x180139b98  call    UnicodeStringFromString8Ex
0x180139b9d  mov     r13, rax
0x180139ba0  mov     [rsp+5E8h+var_560], rax
0x180139ba8  test    rax, rax
0x180139bab  jnz     short loc_180139BE6
0x180139bad  call    cs:__imp_GetLastError
0x180139bb3  test    eax, eax
0x180139bb5  jz      short loc_180139BC1
0x180139bb7  call    cs:__imp_GetLastError
0x180139bbd  mov     ebx, eax
0x180139bbf  jmp     short loc_180139BC6
0x180139bc1  mov     ebx, 1Fh
0x180139bc6  mov     [rsp+5E8h+var_5A8], ebx
0x180139bca  mov     r8d, ebx
0x180139bcd  lea     rdx, aErrorCouldNotC; "Error: Could not convert dsname string "...
0x180139bd4  mov     rcx, rdi
0x180139bd7  call    DumpErrorMessageLLD
0x180139bdc  mov     rsi, qword ptr [rsp+5E8h+var_594+4]
0x180139be1  jmp     loc_180139F5C
0x180139be6  mov     rdx, rbx
0x180139be9  inc     rdx
0x180139bec  cmp     [rax+rdx*2], si
0x180139bf0  jnz     short loc_180139BE9
0x180139bf2  mov     qword ptr [rsp+5E8h+dwCreationDisposition], rsi
0x180139bf7  lea     r9, [rsp+5E8h+var_558]
0x180139bff  xor     r8d, r8d
0x180139c02  mov     rcx, rax
0x180139c05  call    UserFriendlyNameToDSNameEx
0x180139c0a  mov     ebx, eax
0x180139c0c  mov     [rsp+5E8h+var_5A8], ebx
0x180139c10  test    eax, eax
0x180139c12  jz      short loc_180139C20
0x180139c14  mov     r8d, ebx
0x180139c17  lea     rdx, aErrorCouldNotC_0; "Error: Could not convert dsname string "...
0x180139c1e  jmp     short loc_180139BD4
0x180139c20  mov     rdx, [rsp+5E8h+var_558]
0x180139c28  mov     rsi, qword ptr [rsp+5E8h+var_594+4]
0x180139c2d  mov     rcx, rsi
0x180139c30  call    DBFindDSName
0x180139c35  mov     ebx, eax
0x180139c37  mov     [rsp+5E8h+var_5A8], ebx
0x180139c3b  test    eax, eax
0x180139c3d  jz      short loc_180139C62
0x180139c3f  sub     eax, 208Dh
0x180139c44  jz      short loc_180139C4B
0x180139c46  cmp     eax, 13h
0x180139c49  jz      short loc_180139C62
0x180139c4b  lea     rdx, aErrorCouldNotL; "Error: Could not locate target dsname i"...
0x180139c52  mov     r8, rbx
0x180139c55  mov     rcx, rdi
0x180139c58  call    DumpErrorMessageLLD
0x180139c5d  jmp     loc_180139F5C
0x180139c62  mov     eax, [rsi+18h]
0x180139c65  mov     [rsp+5E8h+var_578], eax
0x180139c69  xor     r8d, r8d
0x180139c6c  mov     rdx, [rsi+40h]
0x180139c70  mov     rcx, [rsi+28h]
0x180139c74  mov     rax, cs:pFnJetSetCurrentIndexA
0x180139c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139c80  mov     ebx, eax
0x180139c82  mov     [rsp+5E8h+var_5A8], ebx
0x180139c86  test    eax, eax
0x180139c88  jz      short loc_180139C93
0x180139c8a  lea     rdx, aErrorCouldNotS_0; "Error: could not set the current databa"...
0x180139c91  jmp     short loc_180139C52
0x180139c93  lea     r8, [rsp+5E8h+var_588]
0x180139c98  lea     rdx, [rsp+5E8h+var_598]
0x180139c9d  mov     rcx, r12
0x180139ca0  call    GetReferenceAtts
0x180139ca5  mov     ebx, eax
0x180139ca7  mov     [rsp+5E8h+var_5A8], ebx
0x180139cab  xor     eax, eax
0x180139cad  mov     rcx, rdi; hFile
0x180139cb0  test    ebx, ebx
0x180139cb2  jz      short loc_180139CC0
0x180139cb4  mov     r8d, ebx
0x180139cb7  lea     rdx, aErrorFailedToG; "Error: failed to get list of reference "...
0x180139cbe  jmp     short loc_180139C58
0x180139cc0  mov     qword ptr [rsp+5E8h+dwCreationDisposition], rax; lpOverlapped
0x180139cc5  lea     r9, [rsp+5E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180139cca  mov     r8d, 19h; nNumberOfBytesToWrite
0x180139cd0  lea     rdx, aNonLinkedRefer; "Non-linked references to "
0x180139cd7  call    cs:__imp_WriteFile
0x180139cdd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180139ce1  xor     eax, eax
0x180139ce3  inc     r8; nNumberOfBytesToWrite
0x180139ce6  cmp     [r15+r8], al
0x180139cea  jnz     short loc_180139CE3
0x180139cec  mov     qword ptr [rsp+5E8h+dwCreationDisposition], rax; lpOverlapped
  ... truncated ...
```
