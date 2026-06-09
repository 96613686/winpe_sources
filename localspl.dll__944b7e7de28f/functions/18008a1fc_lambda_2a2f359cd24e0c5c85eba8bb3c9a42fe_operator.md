# _lambda_2a2f359cd24e0c5c85eba8bb3c9a42fe_::operator()

- ea: `0x18008a1fc`
- end: `0x18008aab6`
- name: `_lambda_2a2f359cd24e0c5c85eba8bb3c9a42fe_::operator()`
- size: `2234`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800893d8`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000eb40`
- `0x180013b00`
- `0x180020448`
- `0x180032954`
- `0x18003e5f8`
- `0x18003ea2c`
- `0x180041ce8`
- `0x180047318`
- `0x18008a1fc`
- `0x18009aac4`
- `0x18009efe0`
- `0x18009f050`
- `0x1800a02ec`
- `0x1800a0318`
- `0x1800e3894`
- `0x1800e38a0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a9de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a267`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008aa3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008aa3c`
- `SPOOLSS!DllFreeSplStr` at `0x18008a9ff`
- `SPOOLSS!DllFreeSplStr` at `0x18008aa09`
- `SPOOLSS!DllFreeSplStr` at `0x18008a9ff`
- `SPOOLSS!DllFreeSplStr` at `0x18008aa09`
- `SPOOLSS!DllFreeSplMem` at `0x18008a990`
- `SPOOLSS!DllFreeSplMem` at `0x18008a999`
- `SPOOLSS!DllFreeSplMem` at `0x18008aa13`
- `SPOOLSS!DllFreeSplMem` at `0x18008aa1c`
- `SPOOLSS!DllFreeSplMem` at `0x18008a990`
- `SPOOLSS!DllFreeSplMem` at `0x18008a999`
- `SPOOLSS!DllFreeSplMem` at `0x18008aa13`
- `SPOOLSS!DllFreeSplMem` at `0x18008aa1c`
- `SPOOLSS!DllAllocSplMem` at `0x18008a4b7`
- `SPOOLSS!DllAllocSplMem` at `0x18008a4cd`
- `SPOOLSS!DllAllocSplMem` at `0x18008a4b7`
- `SPOOLSS!DllAllocSplMem` at `0x18008a4cd`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008a2ef`
- `SPOOLSS!RevertToPrinterSelf` at `0x18008a2ef`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008a37c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18008a37c`

## string_xrefs

- `0x18008a315`: `ConfigDriverData`
- `0x18008a5d1`: `CopyFiles\`

## pseudocode

```c
void __fastcall lambda_2a2f359cd24e0c5c85eba8bb3c9a42fe_::operator()(__int64 a1)
{
  struct _SPOOL **v1; // rax
  struct _SPOOL *v3; // rbx
  __int64 v4; // rcx
  _WORD *v5; // rcx
  _DWORD **v6; // rax
  __int64 v7; // r14
  unsigned __int8 *v8; // r12
  _QWORD *v9; // rax
  _DWORD *v10; // rcx
  __int64 v11; // rdi
  int **v12; // rdi
  HANDLE v13; // rax
  __int64 v14; // rbx
  void *v15; // r13
  _DWORD *v16; // rcx
  int v17; // eax
  _DWORD *v18; // rbx
  int **v19; // rbx
  struct PrintConfigDataHelper::ConfigProviderHandle **v20; // r9
  int ConfigProviderHandle; // eax
  int *v22; // rcx
  PrintConfigDataHelper::ConfigProviderHandle *v23; // r13
  unsigned int *v24; // rcx
  int v25; // ebx
  int *v26; // rbx
  int v27; // eax
  unsigned int v28; // r14d
  unsigned __int16 *v29; // r13
  bool v30; // zf
  int *v31; // rbx
  int v32; // eax
  int v33; // eax
  _DWORD *v34; // r8
  int v35; // eax
  _DWORD *v36; // r8
  struct _SPOOL *v37; // r14
  const unsigned __int16 *v38; // rbx
  __int64 v39; // rax
  unsigned int v40; // r9d
  unsigned int **v41; // rax
  int v42; // eax
  _DWORD *v43; // r8
  int v44; // eax
  int v45; // r9d
  _DWORD *v46; // r8
  __int64 v47; // rax
  unsigned int v48; // r9d
  unsigned int **v49; // rax
  int v50; // eax
  _DWORD *v51; // r8
  int v52; // eax
  int v53; // r9d
  _DWORD *v54; // r8
  __int64 v55; // rbx
  unsigned int v56; // r9d
  unsigned __int16 *v57; // r11
  unsigned int v58; // r10d
  _QWORD *v59; // r8
  __int64 v60; // rdx
  int v61; // r14d
  unsigned int *v62; // r13
  unsigned int v63; // r14d
  unsigned int v64; // edx
  int v65; // r8d
  unsigned int v66; // eax
  unsigned __int16 **v67; // r14
  unsigned int v68; // r9d
  unsigned __int16 *v69; // r11
  unsigned __int16 *v70; // r8
  unsigned int v71; // r9d
  unsigned __int16 *v72; // r11
  unsigned int v73; // r10d
  int v74; // eax
  __int64 v75; // rcx
  unsigned int v76; // eax
  void *v77; // rax
  size_t v78; // r8
  const unsigned __int16 *v79; // r10
  struct _SPOOL *v80; // rcx
  unsigned int **v81; // rax
  int *v82; // rax
  _DWORD *v83; // rbx
  _DWORD *v84; // rbx
  int *v85; // rax
  unsigned int v86; // [rsp+20h] [rbp-79h]
  unsigned int v87[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v88; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v89; // [rsp+5Ch] [rbp-3Dh] BYREF
  unsigned int v90; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v91; // [rsp+64h] [rbp-35h]
  PrintConfigDataHelper::ConfigProviderHandle *v92; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v93; // [rsp+70h] [rbp-29h]
  HKEY hKey; // [rsp+78h] [rbp-21h] BYREF
  PrintConfigDataHelper::ConfigProviderHandle *v95; // [rsp+80h] [rbp-19h] BYREF
  unsigned int v96; // [rsp+88h] [rbp-11h]
  unsigned __int16 *v97; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int16 *v98; // [rsp+98h] [rbp-1h] BYREF
  __int64 v99; // [rsp+A0h] [rbp+7h]
  struct _SPOOL *v100; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  unsigned int v102; // [rsp+100h] [rbp+67h] BYREF
  int v103; // [rsp+108h] [rbp+6Fh]
  unsigned int v104; // [rsp+110h] [rbp+77h] BYREF
  int v105; // [rsp+118h] [rbp+7Fh]

  v1 = *(struct _SPOOL ***)a1;
  v98 = 0;
  v97 = 0;
  v100 = *v1;
  v3 = v100;
  hKey = 0;
  v104 = 0;
  v102 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  EnterSplSem(0);
  if ( !(unsigned int)ValidateSpoolHandle(v100, 16) )
  {
    LeaveSplSem(v4);
    SetLastError(6u);
    **(_DWORD **)(a1 + 8) = 6;
    return;
  }
  v5 = **(_WORD ***)(a1 + 16);
  if ( !v5 || !*v5 )
  {
    LeaveSplSem(v5);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x65F,
      (unsigned int)"printscan\\print\\spooler\\localspl\\prndata.c",
      (const char *)0x57,
      v86);
  }
  v6 = *(_DWORD ***)(a1 + 24);
  v7 = 0;
  v105 = 0;
  v8 = 0;
  v93 = 0;
  v92 = 0;
  **v6 = 0;
  v9 = *(_QWORD **)(a1 + 32);
  v10 = (_DWORD *)*v9;
  *(_DWORD *)*v9 = 0;
  v11 = *((_QWORD *)v3 + 8);
  v99 = v11;
  if ( (*(_BYTE *)(v11 + 136) & 0x40) != 0 )
  {
    LeaveSplSem(v10);
    v12 = (int **)(a1 + 8);
    **(_DWORD **)(a1 + 8) = 1906;
    goto LABEL_98;
  }
  v13 = RevertToPrinterSelf();
  v14 = *(_QWORD *)(v11 + 88);
  v103 = 0;
  v15 = v13;
  if ( v14 && *(_DWORD *)(v14 + 236) == 4 )
  {
    if ( !wcscmp_0(**(const wchar_t ***)(a1 + 16), L"ConfigDriverData") )
    {
      SafeIncrementReference((unsigned int *)(v14 + 16));
      v12 = (int **)(a1 + 8);
      v103 = 1;
      v7 = v14;
      goto LABEL_14;
    }
    v103 = 0;
  }
  v17 = OpenPrinterKey(v11, 0x20019u, &hKey, **(_WORD ***)(a1 + 16), 1);
  v12 = (int **)(a1 + 8);
  v16 = *(_DWORD **)(a1 + 8);
  *v16 = v17;
LABEL_14:
  if ( !v15 || ImpersonatePrinterClient(v15) )
  {
    v19 = v12;
  }
  else
  {
    v18 = *v12;
    *v18 = GetLastError();
    v19 = (int **)(a1 + 8);
  }
  LeaveSplSem(v16);
  if ( **v12 || !v103 )
  {
    v23 = 0;
    v19 = v12;
  }
  else
  {
    v95 = 0;
    ConfigProviderHandle = PrintConfigDataHelper::CreateConfigProviderHandle(
                             *((PrintConfigDataHelper **)v100 + 3),
                             (const unsigned __int16 *)v7,
                             (struct _INIDRIVER *)&v95,
                             v20);
    v22 = *v12;
    v23 = v95;
    v92 = v95;
    *v22 = ConfigProviderHandle;
  }
  if ( v7 )
  {
    EnterSplSem(0);
    v24 = (unsigned int *)(v7 + 16);
    if ( *(_DWORD *)(v7 + 16) )
      SafeDecrementReference(v24);
    LeaveSplSem(v24);
  }
  if ( **v19 )
  {
    LODWORD(v7) = 0;
    goto LABEL_98;
  }
  v96 = 0;
  v87[1] = 0;
LABEL_28:
  v25 = v103;
  if ( v103 )
  {
    if ( v23 )
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, unsigned int *))(**((_QWORD **)v23 + 1) + 48LL))(
              *((_QWORD *)v23 + 1),
              **(_QWORD **)(a1 + 32),
              &v104,
              &v102);
    else
      v27 = 87;
    **v12 = v27;
  }
  else
  {
    v26 = *v12;
    *v26 = SplRegQueryInfoKey(
             hKey,
             0,
             0,
             **(unsigned int ***)(a1 + 32),
             &v104,
             &v102,
             0,
             0,
             *(struct _INISPOOLER **)(v99 + 280));
    v25 = v103;
  }
  if ( **v12 )
  {
    v93 = 0;
    goto LABEL_95;
  }
  ++v104;
  v102 = (v102 + 1) & 0xFFFFFFFE;
  v93 = (unsigned __int16 *)DllAllocSplMem(2 * v104);
  if ( !v93 )
  {
    v84 = *v12;
    *v84 = GetLastError();
LABEL_95:
    v8 = 0;
    goto LABEL_96;
  }
  v8 = (unsigned __int8 *)DllAllocSplMem(v102);
  if ( !v8 )
    goto LABEL_92;
  v28 = 0;
  if ( !**v12 )
  {
    v29 = v93;
    do
    {
      if ( v28 >= ***(_DWORD ***)(a1 + 32) )
        break;
      v88 = v104;
      v30 = v25 == 0;
      v31 = *v12;
      v89 = v102;
      v32 = v30
          ? SplRegEnumValue(hKey, v28, v29, &v88, &v90, v8, &v89, *(struct _INISPOOLER **)(v99 + 280))
          : EnumConfigDataValue(
              (_DWORD)v92,
              v28,
              (_DWORD)v29,
              (unsigned int)&v88,
              (__int64)&v90,
              (__int64)v8,
              (__int64)&v89);
      *v31 = v32;
      v33 = AlignToRegType(***(unsigned int ***)(a1 + 24), 1);
      *v34 = v33 + 2 * v88 + 2;
      v35 = AlignToRegType(***(unsigned int ***)(a1 + 24), v90);
      ++v28;
      v25 = v103;
      *v36 = v89 + v35;
    }
    while ( !**v12 );
  }
  v37 = v100;
  if ( *((char *)v100 + 88) < 0 )
  {
    v38 = **(const unsigned __int16 ***)(a1 + 16);
    if ( !wcsncmp_0(v38, L"CopyFiles\\", 0xAu) )
    {
      if ( !(unsigned int)GenerateDirectoryNamesForCopyFilesKey(v37, hKey, v38, &v98, &v97, v102) )
      {
LABEL_92:
        v83 = *v12;
        *v83 = GetLastError();
        goto LABEL_96;
      }
      if ( v98 )
      {
        v39 = -1;
        do
          ++v39;
        while ( v98[v39] );
        v40 = 2 * v39 + 2;
        v41 = *(unsigned int ***)(a1 + 24);
        v96 = v40;
        v42 = AlignToRegType(**v41, 1);
        *v43 = v42 + 22;
        v44 = AlignToRegType(***(unsigned int ***)(a1 + 24), 1);
        *v46 = v45 + v44;
        ++***(_DWORD ***)(a1 + 32);
      }
      if ( v97 )
      {
        v47 = -1;
        do
          ++v47;
        while ( v97[v47] );
        v48 = 2 * v47 + 2;
        v49 = *(unsigned int ***)(a1 + 24);
        v87[1] = v48;
        v50 = AlignToRegType(**v49, 1);
        *v51 = v50 + 22;
        v52 = AlignToRegType(***(unsigned int ***)(a1 + 24), 1);
        *v54 = v53 + v52;
        ++***(_DWORD ***)(a1 + 32);
      }
    }
  }
  ***(_DWORD ***)(a1 + 24) += 32 * ***(_DWORD ***)(a1 + 32);
  if ( **v12 )
    goto LABEL_87;
  if ( ***(_DWORD ***)(a1 + 24) <= **(_DWORD **)(a1 + 40) )
  {
    v55 = **(_QWORD **)(a1 + 48);
    v57 = (unsigned __int16 *)AlignToRegType(v55 + 32LL * ***(unsigned int ***)(a1 + 32), 1);
    v95 = (PrintConfigDataHelper::ConfigProviderHandle *)v57;
    v58 = 0;
    v91 = 0;
    while ( 1 )
    {
      if ( v58 >= ***(_DWORD ***)(a1 + 32)
        || (v59 = *(_QWORD **)(a1 + 48), v60 = **(int **)(a1 + 40), v55 - *v59 >= v60) )
      {
LABEL_85:
        if ( **v12 == 259 )
          **v12 = 0;
LABEL_87:
        DllFreeSplMem(v93);
        DllFreeSplMem(v8);
        v82 = *v12;
        v8 = 0;
        v93 = 0;
        if ( *v82 != 234 )
          goto LABEL_90;
        v23 = v92;
        goto LABEL_28;
      }
      v61 = *(_DWORD *)v59;
      v62 = (unsigned int *)(v55 + 24);
      *(_QWORD *)v55 = v57;
      v63 = v60 - (_DWORD)v57 + v61;
      v87[0] = v63;
      v64 = v63;
      if ( v63 >= 2 * (unsigned __int64)v104 )
        v64 = 2 * v104;
      *(_DWORD *)(v55 + 8) = v64;
      *v62 = v102;
      v65 = ***(_DWORD ***)(a1 + 32);
      if ( v58 == v65 - 2 )
      {
        v66 = v96;
        if ( v96 )
          break;
      }
      if ( v58 == v65 - 1 && v56 )
      {
        *v62 = v56;
        *(_DWORD *)(v55 + 12) = 1;
        *(_DWORD *)(v55 + 8) = 22;
        v67 = (unsigned __int16 **)(v55 + 16);
        *(_QWORD *)(v55 + 16) = AlignToRegType(v57 + 11, 1);
        StringCbCopyW(v72, v71, L"TargetDir");
        v70 = v97;
        goto LABEL_68;
      }
      v87[0] = v64 >> 1;
      if ( v103 )
        v74 = EnumConfigDataValue((_DWORD)v92, v58, (_DWORD)v57, (unsigned int)v87, v55 + 12, (__int64)v8, v55 + 24);
      else
        v74 = SplRegEnumValue(
                hKey,
                v58,
                v57,
                v87,
                (unsigned int *)(v55 + 12),
                v8,
                (unsigned int *)(v55 + 24),
                *(struct _INISPOOLER **)(v99 + 280));
      **v12 = v74;
      if ( **v12 )
        goto LABEL_85;
      v75 = 2 * v87[0] + 2;
      v76 = *v62 + v75;
      *(_DWORD *)(v55 + 8) = v75;
      if ( v76 > v63 )
      {
        **v12 = 234;
        goto LABEL_85;
      }
      v67 = (unsigned __int16 **)(v55 + 16);
      v77 = (void *)AlignToRegType(*(_QWORD *)v55 + v75, *(unsigned int *)(v55 + 12));
      v80 = v100;
      *(_QWORD *)(v55 + 16) = v77;
      if ( *((char *)v80 + 88) >= 0 )
        memcpy_0(v77, v8, v78);
      else
        FixColorProfilesDataForDownLevelClients(
          **(const unsigned __int16 ***)(a1 + 16),
          v79,
          v8,
          (unsigned __int8 *)v77,
          v78);
      v57 = (unsigned __int16 *)v95;
      v73 = v91;
LABEL_78:
      v81 = *(unsigned int ***)(a1 + 32);
      v58 = v73 + 1;
      v91 = v58;
      if ( v58 < **v81 )
      {
        v57 = (unsigned __int16 *)AlignToRegType((char *)*v67 + *v62, 1);
        v95 = (PrintConfigDataHelper::ConfigProviderHandle *)v57;
      }
      if ( !*v62 )
        *v67 = 0;
      v55 += 32;
      v56 = v87[1];
      if ( **v12 )
        goto LABEL_85;
    }
    *(_DWORD *)(v55 + 12) = 1;
    *(_DWORD *)(v55 + 8) = 22;
    *v62 = v66;
    v67 = (unsigned __int16 **)(v55 + 16);
    *(_QWORD *)(v55 + 16) = AlignToRegType(v57 + 11, 1);
    StringCbCopyW(v69, v68, L"SourceDir");
    v70 = v98;
LABEL_68:
    StringCbCopyW(*v67, v87[0], v70);
    goto LABEL_78;
  }
  **v12 = 234;
LABEL_90:
  if ( !**v12 )
  {
    LODWORD(v7) = 1;
    goto LABEL_98;
  }
LABEL_96:
  LODWORD(v7) = v105;
LABEL_98:
  DllFreeSplStr(v97);
  DllFreeSplStr(v98);
  DllFreeSplMem(v93);
  DllFreeSplMem(v8);
  if ( v92 )
    PrintConfigDataHelper::ConfigProviderHandle::`scalar deleting destructor'(v92);
  if ( hKey )
    RegCloseKey(hKey);
  if ( !(_DWORD)v7 && !**v12 )
    **v12 = 87;
  v85 = *v12;
  if ( **v12 != 2 && *v85 != 234 )
  {
    if ( *v85 )
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplEnumPrinterDataEx::<lambda_2a2f359cd24e0c5c85eba8bb3c9a42fe>::operator ()",
        L"Failed to enumerate printer data for key '%ws'.",
        **(_QWORD **)(a1 + 16));
  }
}

```

## disassembly

```asm
0x18008a1fc  push    rbp
0x18008a1fe  push    rbx
0x18008a1ff  push    rsi
0x18008a200  push    rdi
0x18008a201  push    r12
0x18008a203  push    r13
0x18008a205  push    r14
0x18008a207  push    r15
0x18008a209  lea     rbp, [rsp-1Fh]
0x18008a20e  sub     rsp, 0B8h
0x18008a215  mov     rax, [rcx]
0x18008a218  xor     r13d, r13d
0x18008a21b  mov     rsi, rcx
0x18008a21e  mov     [rbp+57h+var_58], r13
0x18008a222  xor     ecx, ecx
0x18008a224  mov     [rbp+57h+var_60], r13
0x18008a228  mov     rbx, [rax]
0x18008a22b  mov     [rbp+57h+var_48], rbx
0x18008a22f  mov     [rbp+57h+hKey], r13
0x18008a233  mov     [rbp+57h+arg_10], r13d
0x18008a237  mov     [rbp+57h+arg_0], r13d
0x18008a23b  mov     [rbp+57h+var_98], r13d
0x18008a23f  mov     [rbp+57h+var_94], r13d
0x18008a243  mov     [rbp+57h+var_90], r13d
0x18008a247  call    EnterSplSem
0x18008a24c  lea     edx, [r13+10h]
0x18008a250  mov     rcx, rbx
0x18008a253  call    ValidateSpoolHandle
0x18008a258  test    eax, eax
0x18008a25a  jnz     short loc_18008A287
0x18008a25c  call    LeaveSplSem
0x18008a261  lea     ebx, [r13+6]
0x18008a265  mov     ecx, ebx; dwErrCode
0x18008a267  call    cs:__imp_SetLastError
0x18008a26d  mov     rax, [rsi+8]
0x18008a271  mov     [rax], ebx
0x18008a273  add     rsp, 0B8h
0x18008a27a  pop     r15
0x18008a27c  pop     r14
0x18008a27e  pop     r13
0x18008a280  pop     r12
0x18008a282  pop     rdi
0x18008a283  pop     rsi
0x18008a284  pop     rbx
0x18008a285  pop     rbp
0x18008a286  retn
0x18008a287  mov     rax, [rsi+10h]
0x18008a28b  mov     rcx, [rax]
0x18008a28e  test    rcx, rcx
0x18008a291  jz      loc_18008AA95
0x18008a297  cmp     [rcx], r13w
0x18008a29b  jz      loc_18008AA95
0x18008a2a1  mov     rax, [rsi+18h]
0x18008a2a5  mov     r14d, r13d
0x18008a2a8  mov     [rbp+57h+arg_18], r13d
0x18008a2ac  mov     r12, r13
0x18008a2af  mov     [rbp+57h+var_80], r13
0x18008a2b3  mov     [rbp+57h+var_88], r13
0x18008a2b7  mov     rcx, [rax]
0x18008a2ba  mov     [rcx], r13d
0x18008a2bd  mov     rax, [rsi+20h]
0x18008a2c1  mov     rcx, [rax]
0x18008a2c4  mov     [rcx], r13d
0x18008a2c7  mov     rdi, [rbx+40h]
0x18008a2cb  mov     [rbp+57h+var_50], rdi
0x18008a2cf  test    byte ptr [rdi+88h], 40h
0x18008a2d6  jz      short loc_18008A2EF
0x18008a2d8  call    LeaveSplSem
0x18008a2dd  lea     rdi, [rsi+8]
0x18008a2e1  mov     rax, [rdi]
0x18008a2e4  mov     dword ptr [rax], 772h
0x18008a2ea  jmp     loc_18008A9FB
0x18008a2ef  call    cs:__imp_RevertToPrinterSelf
0x18008a2f5  mov     rbx, [rdi+58h]
0x18008a2f9  xor     r15d, r15d
0x18008a2fc  mov     [rbp+57h+arg_8], r15d
0x18008a300  mov     r13, rax
0x18008a303  test    rbx, rbx
0x18008a306  jz      short loc_18008A348
0x18008a308  cmp     dword ptr [rbx+0ECh], 4
0x18008a30f  jnz     short loc_18008A348
0x18008a311  mov     rcx, [rsi+10h]
0x18008a315  lea     rdx, aConfigdriverda; "ConfigDriverData"
0x18008a31c  mov     rcx, [rcx]; String1
0x18008a31f  call    wcscmp_0
0x18008a324  test    eax, eax
0x18008a326  jnz     short loc_18008A344
0x18008a328  lea     rcx, [rbx+10h]; unsigned int *
0x18008a32c  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18008a331  mov     r15d, 1
0x18008a337  lea     rdi, [rsi+8]
0x18008a33b  mov     [rbp+57h+arg_8], r15d
0x18008a33f  mov     r14, rbx
0x18008a342  jmp     short loc_18008A374
0x18008a344  mov     [rbp+57h+arg_8], r15d
0x18008a348  mov     r9, [rsi+10h]
0x18008a34c  lea     r8, [rbp+57h+hKey]
0x18008a350  mov     r15d, 1
0x18008a356  mov     edx, 20019h
0x18008a35b  mov     rcx, rdi
0x18008a35e  mov     dword ptr [rsp+0F0h+var_D0], r15d
0x18008a363  mov     r9, [r9]
0x18008a366  call    OpenPrinterKey
0x18008a36b  lea     rdi, [rsi+8]
0x18008a36f  mov     rcx, [rdi]
0x18008a372  mov     [rcx], eax
0x18008a374  test    r13, r13
0x18008a377  jz      short loc_18008A397
0x18008a379  mov     rcx, r13; hToken
0x18008a37c  call    cs:__imp_ImpersonatePrinterClient
0x18008a382  test    eax, eax
0x18008a384  jnz     short loc_18008A397
0x18008a386  mov     rbx, [rdi]
0x18008a389  call    cs:__imp_GetLastError
0x18008a38f  mov     [rbx], eax
0x18008a391  lea     rbx, [rsi+8]
0x18008a395  jmp     short loc_18008A39A
0x18008a397  mov     rbx, rdi
0x18008a39a  call    LeaveSplSem
0x18008a39f  mov     rax, [rdi]
0x18008a3a2  xor     ecx, ecx
0x18008a3a4  cmp     [rax], ecx
0x18008a3a6  jnz     short loc_18008A3D6
0x18008a3a8  cmp     [rbp+57h+arg_8], ecx
0x18008a3ab  jz      short loc_18008A3D6
0x18008a3ad  mov     rax, [rbp+57h+var_48]
0x18008a3b1  lea     r8, [rbp+57h+var_70]; struct _INIDRIVER *
0x18008a3b5  mov     [rbp+57h+var_70], rcx
0x18008a3b9  mov     rdx, r14; unsigned __int16 *
0x18008a3bc  mov     rcx, [rax+18h]; this
0x18008a3c0  call    ?CreateConfigProviderHandle@PrintConfigDataHelper@@YAKPEBGPEAU_INIDRIVER@@PEAPEAUConfigProviderHandle@1@@Z; PrintConfigDataHelper::CreateConfigProviderHandle(ushort const *,_INIDRIVER *,PrintConfigDataHelper::ConfigProviderHandle * *)
0x18008a3c5  mov     rcx, [rdi]
0x18008a3c8  mov     r13, [rbp+57h+var_70]
0x18008a3cc  mov     [rbp+57h+var_88], r13
0x18008a3d0  mov     [rcx], eax
0x18008a3d2  xor     ecx, ecx
0x18008a3d4  jmp     short loc_18008A3DC
0x18008a3d6  mov     r13, rcx
0x18008a3d9  mov     rbx, rdi
0x18008a3dc  test    r14, r14
0x18008a3df  jz      short loc_18008A3FD
0x18008a3e1  xor     ecx, ecx
0x18008a3e3  call    EnterSplSem
0x18008a3e8  lea     rcx, [r14+10h]; unsigned int *
0x18008a3ec  cmp     [rcx], r12d
0x18008a3ef  jz      short loc_18008A3F6
0x18008a3f1  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18008a3f6  call    LeaveSplSem
0x18008a3fb  xor     ecx, ecx
0x18008a3fd  mov     rax, [rbx]
0x18008a400  cmp     [rax], ecx
0x18008a402  jnz     loc_18008A9F5
0x18008a408  mov     [rbp+57h+var_68], ecx
0x18008a40b  mov     [rbp+57h+var_A0+4], ecx
0x18008a40e  mov     ebx, [rbp+57h+arg_8]
0x18008a411  test    ebx, ebx
0x18008a413  jnz     short loc_18008A463
0x18008a415  mov     r9, [rsi+20h]
0x18008a419  xor     r13d, r13d
0x18008a41c  mov     rax, [rbp+57h+var_50]
0x18008a420  xor     r8d, r8d; unsigned int *
0x18008a423  mov     rcx, [rbp+57h+hKey]; void *
0x18008a427  xor     edx, edx; unsigned int *
0x18008a429  mov     rbx, [rdi]
0x18008a42c  mov     r9, [r9]; unsigned int *
0x18008a42f  mov     rax, [rax+118h]
0x18008a436  mov     [rsp+0F0h+var_B0], rax; struct _INISPOOLER *
0x18008a43b  lea     rax, [rbp+57h+arg_0]
0x18008a43f  mov     [rsp+0F0h+var_B8], r13; struct _FILETIME *
0x18008a444  mov     [rsp+0F0h+var_C0], r13; unsigned int *
0x18008a449  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18008a44e  lea     rax, [rbp+57h+arg_10]
0x18008a452  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18008a457  call    ?SplRegQueryInfoKey@@YAJPEAXPEAK11111PEAU_FILETIME@@PEAU_INISPOOLER@@@Z; SplRegQueryInfoKey(void *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,_FILETIME *,_INISPOOLER *)
0x18008a45c  mov     [rbx], eax
0x18008a45e  mov     ebx, [rbp+57h+arg_8]
0x18008a461  jmp     short loc_18008A495
0x18008a463  test    r13, r13
0x18008a466  jnz     short loc_18008A46E
0x18008a468  lea     eax, [r13+57h]
0x18008a46c  jmp     short loc_18008A48D
0x18008a46e  mov     rcx, [r13+8]
0x18008a472  lea     r9, [rbp+57h+arg_0]
0x18008a476  mov     rdx, [rsi+20h]
0x18008a47a  lea     r8, [rbp+57h+arg_10]
0x18008a47e  mov     rax, [rcx]
0x18008a481  mov     rdx, [rdx]
0x18008a484  mov     rax, [rax+30h]
0x18008a488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a48d  mov     rcx, [rdi]
0x18008a490  xor     r13d, r13d
0x18008a493  mov     [rcx], eax
0x18008a495  mov     rax, [rdi]
0x18008a498  cmp     [rax], r13d
0x18008a49b  jnz     loc_18008A9E8
0x18008a4a1  mov     ecx, [rbp+57h+arg_10]
0x18008a4a4  mov     eax, [rbp+57h+arg_0]
0x18008a4a7  add     ecx, r15d
0x18008a4aa  inc     eax
0x18008a4ac  mov     [rbp+57h+arg_10], ecx
0x18008a4af  and     eax, 0FFFFFFFEh
0x18008a4b2  add     ecx, ecx
0x18008a4b4  mov     [rbp+57h+arg_0], eax
0x18008a4b7  call    cs:__imp_DllAllocSplMem
0x18008a4bd  mov     [rbp+57h+var_80], rax
0x18008a4c1  test    rax, rax
0x18008a4c4  jz      loc_18008A9DB
0x18008a4ca  mov     ecx, [rbp+57h+arg_0]
0x18008a4cd  call    cs:__imp_DllAllocSplMem
0x18008a4d3  mov     r12, rax
0x18008a4d6  test    rax, rax
0x18008a4d9  jz      loc_18008A9CE
0x18008a4df  mov     rcx, [rdi]
0x18008a4e2  mov     r14d, r13d
0x18008a4e5  cmp     [rcx], r13d
0x18008a4e8  jnz     loc_18008A5BE
0x18008a4ee  mov     r13, [rbp+57h+var_80]
0x18008a4f2  mov     rcx, [rsi+20h]
0x18008a4f6  mov     rdx, [rcx]
0x18008a4f9  cmp     r14d, [rdx]
0x18008a4fc  jnb     loc_18008A5BB
0x18008a502  mov     eax, [rbp+57h+arg_10]
0x18008a505  lea     r9, [rbp+57h+var_98]; unsigned int *
0x18008a509  mov     [rbp+57h+var_98], eax
0x18008a50c  test    ebx, ebx
0x18008a50e  mov     eax, [rbp+57h+arg_0]
0x18008a511  mov     r8, r13; unsigned __int16 *
0x18008a514  mov     rbx, [rdi]
0x18008a517  mov     edx, r14d; unsigned int
0x18008a51a  mov     [rbp+57h+var_94], eax
0x18008a51d  jnz     short loc_18008A551
0x18008a51f  mov     rax, [rbp+57h+var_50]
0x18008a523  mov     rcx, [rbp+57h+hKey]; void *
0x18008a527  mov     rax, [rax+118h]
0x18008a52e  mov     [rsp+0F0h+var_B8], rax; struct _INISPOOLER *
0x18008a533  lea     rax, [rbp+57h+var_94]
0x18008a537  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x18008a53c  lea     rax, [rbp+57h+var_90]
0x18008a540  mov     [rsp+0F0h+var_C8], r12; unsigned __int8 *
0x18008a545  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18008a54a  call    ?SplRegEnumValue@@YAJPEAXKPEAGPEAK2PEAE2PEAU_INISPOOLER@@@Z; SplRegEnumValue(void *,ulong,ushort *,ulong *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18008a54f  jmp     short loc_18008A571
0x18008a551  mov     rcx, [rbp+57h+var_88]
0x18008a555  lea     rax, [rbp+57h+var_94]
0x18008a559  mov     [rsp+0F0h+var_C0], rax
0x18008a55e  lea     rax, [rbp+57h+var_90]
0x18008a562  mov     [rsp+0F0h+var_C8], r12
0x18008a567  mov     [rsp+0F0h+var_D0], rax
0x18008a56c  call    EnumConfigDataValue
0x18008a571  mov     [rbx], eax
0x18008a573  mov     edx, r15d
0x18008a576  mov     rax, [rsi+18h]
0x18008a57a  mov     r8, [rax]
0x18008a57d  mov     ecx, [r8]
0x18008a580  call    AlignToRegType
0x18008a585  mov     ecx, [rbp+57h+var_98]
0x18008a588  lea     eax, [rax+rcx*2]
0x18008a58b  add     eax, 2
0x18008a58e  mov     [r8], eax
0x18008a591  mov     rax, [rsi+18h]
0x18008a595  mov     edx, [rbp+57h+var_90]
0x18008a598  mov     r8, [rax]
0x18008a59b  mov     ecx, [r8]
0x18008a59e  call    AlignToRegType
0x18008a5a3  add     eax, [rbp+57h+var_94]
0x18008a5a6  add     r14d, r15d
0x18008a5a9  mov     ebx, [rbp+57h+arg_8]
0x18008a5ac  mov     [r8], eax
0x18008a5af  mov     rax, [rdi]
0x18008a5b2  cmp     dword ptr [rax], 0
0x18008a5b5  jz      loc_18008A4F2
0x18008a5bb  xor     r13d, r13d
0x18008a5be  mov     r14, [rbp+57h+var_48]
0x18008a5c2  test    byte ptr [r14+58h], 80h
0x18008a5c7  jz      loc_18008A6D8
0x18008a5cd  mov     rax, [rsi+10h]
0x18008a5d1  lea     rdx, aCopyfiles; "CopyFiles\\"
0x18008a5d8  mov     r8d, 0Ah; MaxCount
0x18008a5de  mov     rbx, [rax]
0x18008a5e1  mov     rcx, rbx; String1
0x18008a5e4  call    wcsncmp_0
0x18008a5e9  test    eax, eax
0x18008a5eb  jnz     loc_18008A6D8
0x18008a5f1  mov     eax, [rbp+57h+arg_0]
0x18008a5f4  lea     r9, [rbp+57h+var_58]; unsigned __int16 **
0x18008a5f8  mov     rdx, [rbp+57h+hKey]; void *
0x18008a5fc  mov     r8, rbx; unsigned __int16 *
0x18008a5ff  mov     dword ptr [rsp+0F0h+var_C8], eax; unsigned int
0x18008a603  mov     rcx, r14; struct _SPOOL *
0x18008a606  lea     rax, [rbp+57h+var_60]
0x18008a60a  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 **
0x18008a60f  call    ?GenerateDirectoryNamesForCopyFilesKey@@YAHPEAU_SPOOL@@PEAXPEBGPEAPEAG3K@Z; GenerateDirectoryNamesForCopyFilesKey(_SPOOL *,void *,ushort const *,ushort * *,ushort * *,ulong)
0x18008a614  test    eax, eax
0x18008a616  jz      loc_18008A9CE
0x18008a61c  mov     rcx, [rbp+57h+var_58]
0x18008a620  test    rcx, rcx
0x18008a623  jz      short loc_18008A679
0x18008a625  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008a629  inc     rax
0x18008a62c  cmp     [rcx+rax*2], r13w
  ... truncated ...
```
