# CCollection::Save(void)

- ea: `0x180016234`
- end: `0x180016fb6`
- name: `?Save@CCollection@@QEAAKXZ`
- size: `3458`
- prototype: `unsigned int __fastcall(CCollection *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005f624`

## callees

- `0x1800095c8`
- `0x18000f460`
- `0x180016234`
- `0x18004e958`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180016323`
- `KERNEL32!CloseHandle` at `0x180016f2b`
- `KERNEL32!CloseHandle` at `0x180016f7d`
- `KERNEL32!CloseHandle` at `0x180016323`
- `KERNEL32!CloseHandle` at `0x180016f2b`
- `KERNEL32!CloseHandle` at `0x180016f7d`
- `KERNEL32!CreateFileA` at `0x1800162b4`
- `KERNEL32!CreateFileA` at `0x180016f61`
- `KERNEL32!CreateFileA` at `0x1800162b4`
- `KERNEL32!CreateFileA` at `0x180016f61`
- `KERNEL32!WriteFile` at `0x180016312`
- `KERNEL32!WriteFile` at `0x18001636e`
- `KERNEL32!WriteFile` at `0x1800163ba`
- `KERNEL32!WriteFile` at `0x180016403`
- `KERNEL32!WriteFile` at `0x180016476`
- `KERNEL32!WriteFile` at `0x1800164c2`
- `KERNEL32!WriteFile` at `0x180016517`
- `KERNEL32!WriteFile` at `0x180016560`
- `KERNEL32!WriteFile` at `0x1800165ae`
- `KERNEL32!WriteFile` at `0x1800165f7`
- `KERNEL32!WriteFile` at `0x180016661`
- `KERNEL32!WriteFile` at `0x1800166ae`
- `KERNEL32!WriteFile` at `0x180016708`
- `KERNEL32!WriteFile` at `0x18001675d`
- `KERNEL32!WriteFile` at `0x1800167b2`
- `KERNEL32!WriteFile` at `0x180016807`
- `KERNEL32!WriteFile` at `0x180016850`
- `KERNEL32!WriteFile` at `0x18001689e`
- `KERNEL32!WriteFile` at `0x1800168e7`
- `KERNEL32!WriteFile` at `0x18001695c`
- `KERNEL32!WriteFile` at `0x1800169b3`
- `KERNEL32!WriteFile` at `0x180016a01`
- `KERNEL32!WriteFile` at `0x180016a57`
- `KERNEL32!WriteFile` at `0x180016aa4`
- `KERNEL32!WriteFile` at `0x180016afd`
- `KERNEL32!WriteFile` at `0x180016b56`
- `KERNEL32!WriteFile` at `0x180016baf`
- `KERNEL32!WriteFile` at `0x180016c08`
- `KERNEL32!WriteFile` at `0x180016c55`
- `KERNEL32!WriteFile` at `0x180016ca2`
- `KERNEL32!WriteFile` at `0x180016cf9`
- `KERNEL32!WriteFile` at `0x180016d52`
- `KERNEL32!WriteFile` at `0x180016d9f`
- `KERNEL32!WriteFile` at `0x180016de8`
- `KERNEL32!WriteFile` at `0x180016e32`
- `KERNEL32!WriteFile` at `0x180016e84`
- `KERNEL32!WriteFile` at `0x180016ecd`
- `KERNEL32!WriteFile` at `0x180016f16`
- `KERNEL32!WriteFile` at `0x180016312`
- `KERNEL32!WriteFile` at `0x18001636e`
- `KERNEL32!WriteFile` at `0x1800163ba`
- `KERNEL32!WriteFile` at `0x180016403`
- `KERNEL32!WriteFile` at `0x180016476`
- `KERNEL32!WriteFile` at `0x1800164c2`
- `KERNEL32!WriteFile` at `0x180016517`
- `KERNEL32!WriteFile` at `0x180016560`
- `KERNEL32!WriteFile` at `0x1800165ae`
- `KERNEL32!WriteFile` at `0x1800165f7`
- `KERNEL32!WriteFile` at `0x180016661`
- `KERNEL32!WriteFile` at `0x1800166ae`
- `KERNEL32!WriteFile` at `0x180016708`
- `KERNEL32!WriteFile` at `0x18001675d`
- `KERNEL32!WriteFile` at `0x1800167b2`
- `KERNEL32!WriteFile` at `0x180016807`
- `KERNEL32!WriteFile` at `0x180016850`
- `KERNEL32!WriteFile` at `0x18001689e`
- `KERNEL32!WriteFile` at `0x1800168e7`
- `KERNEL32!WriteFile` at `0x18001695c`
- `KERNEL32!WriteFile` at `0x1800169b3`
- `KERNEL32!WriteFile` at `0x180016a01`
- `KERNEL32!WriteFile` at `0x180016a57`
- `KERNEL32!WriteFile` at `0x180016aa4`
- `KERNEL32!WriteFile` at `0x180016afd`
- `KERNEL32!WriteFile` at `0x180016b56`
- `KERNEL32!WriteFile` at `0x180016baf`
- `KERNEL32!WriteFile` at `0x180016c08`
- `KERNEL32!WriteFile` at `0x180016c55`
- `KERNEL32!WriteFile` at `0x180016ca2`
- `KERNEL32!WriteFile` at `0x180016cf9`
- `KERNEL32!WriteFile` at `0x180016d52`
- `KERNEL32!WriteFile` at `0x180016d9f`
- `KERNEL32!WriteFile` at `0x180016de8`
- `KERNEL32!WriteFile` at `0x180016e32`
- `KERNEL32!WriteFile` at `0x180016e84`
- `KERNEL32!WriteFile` at `0x180016ecd`
- `KERNEL32!WriteFile` at `0x180016f16`

## string_xrefs

- `0x1800162d7`: `<XML>\n`
- `0x18001676f`: `	<LocPath value="%s"/>\n`
- `0x1800168ac`: `<DocCompilations>\n`
- `0x180016921`: `<DocCompilation>\n`
- `0x180016974`: `	<DocCompId value="%s"/>\n`
- `0x1800169c6`: `	<DocCompLanguage value=%d/>\n`
- `0x180016dff`: `</DocCompilation>\n`
- `0x180016e49`: `</DocCompilations>\n`
- `0x180016edb`: `</XML>\n`

## pseudocode

```c
__int64 __fastcall CCollection::Save(CCollection *this)
{
  bool v2; // r14
  HANDLE v3; // rax
  __int64 v5; // r8
  void *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 i; // rdi
  __int64 v11; // r8
  __int64 v12; // r8
  const CHAR *v13; // r9
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 j; // rdi
  __int64 v19; // r8
  __int64 v20; // r8
  const CHAR *v21; // r9
  __int64 v22; // r8
  const CHAR *v23; // r9
  __int64 v24; // r8
  const CHAR *v25; // r9
  __int64 v26; // r8
  const CHAR *v27; // r9
  __int64 v28; // r8
  __int64 v29; // r8
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 k; // rsi
  __int64 v33; // rax
  __int64 v34; // r8
  const CHAR *v35; // r9
  __int64 v36; // r8
  __int64 v37; // r8
  __int64 m; // rdi
  __int64 v39; // r8
  __int64 v40; // r8
  const CHAR *v41; // r9
  __int64 v42; // r8
  const CHAR *v43; // r9
  __int64 v44; // r8
  const CHAR *v45; // r9
  __int64 v46; // r8
  const CHAR *v47; // r9
  __int64 v48; // r8
  __int64 v49; // r8
  __int64 v50; // r8
  const CHAR *v51; // r9
  __int64 v52; // r8
  const CHAR *v53; // r9
  __int64 v54; // r8
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r8
  __int64 v60; // r8
  BOOL v61; // eax
  HANDLE v62; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-B8h] BYREF
  char Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  NumberOfBytesWritten = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v2 = HHCheckGlobalAccess();
  v3 = CreateFileA(&gszColReg, 0x40000000u, 1u, &SecurityAttributes, 2u, 0x80u, 0);
  *((_QWORD *)this + 120) = v3;
  if ( v3 == (HANDLE)-1LL )
    return 1;
  StringCchCopyA(Buffer, 0x400u, "<XML>\r\n");
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v5, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchCopyA(Buffer, 0x400u, "<HTMLHelpDocInfo>\r\n");
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v7, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchPrintfA(Buffer, 0x400u, "<NextCollectionId value=%d/>\r\n", *((_DWORD *)this + 232));
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v8, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchCopyA(Buffer, 0x400u, "<Collections>\r\n");
  v9 = -1;
  do
    ++v9;
  while ( Buffer[v9] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v9, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  for ( i = *((_QWORD *)this + 122); i; i = *(_QWORD *)(i + 16) )
  {
    if ( v2 || *(_DWORD *)i >= 0xF4240u )
    {
      StringCchCopyA(Buffer, 0x400u, "<Collection>\r\n");
      v11 = -1;
      do
        ++v11;
      while ( Buffer[v11] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v11, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      StringCchPrintfA(Buffer, 0x400u, "\t<ColNum value=%d/>\r\n", *(_DWORD *)i);
      v12 = -1;
      do
        ++v12;
      while ( Buffer[v12] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v12, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v13 = Class;
      if ( *(_QWORD *)(i + 8) )
        v13 = *(const CHAR **)(i + 8);
      StringCchPrintfA(Buffer, 0x400u, "\t<ColName value=\"%s\"/>\r\n", v13);
      v14 = -1;
      do
        ++v14;
      while ( Buffer[v14] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v14, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      StringCchCopyA(Buffer, 0x400u, "</Collection>\r\n");
      v15 = -1;
      do
        ++v15;
      while ( Buffer[v15] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v15, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
    }
  }
  StringCchCopyA(Buffer, 0x400u, "</Collections>\r\n");
  v16 = -1;
  do
    ++v16;
  while ( Buffer[v16] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v16, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchCopyA(Buffer, 0x400u, "<Locations>\r\n");
  v17 = -1;
  do
    ++v17;
  while ( Buffer[v17] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v17, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  for ( j = *((_QWORD *)this + 10); j; j = *(_QWORD *)(j + 64) )
  {
    if ( v2 || *(_DWORD *)(j + 72) >= 0xF4240u )
    {
      StringCchCopyA(Buffer, 0x400u, "<Location>\r\n");
      v19 = -1;
      do
        ++v19;
      while ( Buffer[v19] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v19, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      StringCchPrintfA(Buffer, 0x400u, "\t<LocColNum value=%d/>\r\n", *(_DWORD *)(j + 72));
      v20 = -1;
      do
        ++v20;
      while ( Buffer[v20] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v20, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v21 = Class;
      if ( *(_QWORD *)j )
        v21 = *(const CHAR **)j;
      StringCchPrintfA(Buffer, 0x400u, "\t<LocName value=\"%s\"/>\r\n", v21);
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v22, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v23 = Class;
      if ( *(_QWORD *)(j + 8) )
        v23 = *(const CHAR **)(j + 8);
      StringCchPrintfA(Buffer, 0x400u, "\t<TitleString value=\"%s\"/>\r\n", v23);
      v24 = -1;
      do
        ++v24;
      while ( Buffer[v24] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v24, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v25 = Class;
      if ( *(_QWORD *)(j + 16) )
        v25 = *(const CHAR **)(j + 16);
      StringCchPrintfA(Buffer, 0x400u, "\t<LocPath value=\"%s\"/>\r\n", v25);
      v26 = -1;
      do
        ++v26;
      while ( Buffer[v26] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v26, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v27 = Class;
      if ( *(_QWORD *)(j + 24) )
        v27 = *(const CHAR **)(j + 24);
      StringCchPrintfA(Buffer, 0x400u, "\t<Volume value=\"%s\"/>\r\n", v27);
      v28 = -1;
      do
        ++v28;
      while ( Buffer[v28] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v28, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      StringCchCopyA(Buffer, 0x400u, "</Location>\r\n");
      v29 = -1;
      do
        ++v29;
      while ( Buffer[v29] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v29, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
    }
  }
  StringCchCopyA(Buffer, 0x400u, "</Locations>\r\n");
  v30 = -1;
  do
    ++v30;
  while ( Buffer[v30] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v30, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchCopyA(Buffer, 0x400u, "<DocCompilations>\r\n");
  v31 = -1;
  do
    ++v31;
  while ( Buffer[v31] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v31, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  for ( k = *((_QWORD *)this + 8); k; k = *(_QWORD *)(k + 24) )
  {
    v33 = *(_QWORD *)(k + 32);
    if ( v33 && (v2 || *(_DWORD *)(v33 + 40) >= 0xF4240u) )
    {
      StringCchCopyA(Buffer, 0x400u, "<DocCompilation>\r\n");
      v34 = -1;
      do
        ++v34;
      while ( Buffer[v34] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v34, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      v35 = Class;
      if ( *(_QWORD *)k )
        v35 = *(const CHAR **)k;
      StringCchPrintfA(Buffer, 0x400u, "\t<DocCompId value=\"%s\"/>\r\n", v35);
      v36 = -1;
      do
        ++v36;
      while ( Buffer[v36] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v36, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      StringCchPrintfA(Buffer, 0x400u, "\t<DocCompLanguage value=%d/>\r\n", *(unsigned __int16 *)(k + 16));
      v37 = -1;
      do
        ++v37;
      while ( Buffer[v37] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v37, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
      for ( m = *(_QWORD *)(k + 32); m; m = *(_QWORD *)(m + 56) )
      {
        StringCchCopyA(Buffer, 0x400u, "\t<LocationHistory>\r\n");
        v39 = -1;
        do
          ++v39;
        while ( Buffer[v39] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v39, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        StringCchPrintfA(Buffer, 0x400u, "\t\t<ColNum value=%d/>\r\n", *(_DWORD *)(m + 40));
        v40 = -1;
        do
          ++v40;
        while ( Buffer[v40] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v40, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v41 = Class;
        if ( *(_QWORD *)(m + 8) )
          v41 = *(const CHAR **)(m + 8);
        StringCchPrintfA(Buffer, 0x400u, "\t\t<TitleLocation value=\"%s\"/>\r\n", v41);
        v42 = -1;
        do
          ++v42;
        while ( Buffer[v42] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v42, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v43 = Class;
        if ( *(_QWORD *)(m + 16) )
          v43 = *(const CHAR **)(m + 16);
        StringCchPrintfA(Buffer, 0x400u, "\t\t<IndexLocation value=\"%s\"/>\r\n", v43);
        v44 = -1;
        do
          ++v44;
        while ( Buffer[v44] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v44, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v45 = Class;
        if ( *(_QWORD *)(m + 24) )
          v45 = *(const CHAR **)(m + 24);
        StringCchPrintfA(Buffer, 0x400u, "\t\t<QueryLocation value=\"%s\"/>\r\n", v45);
        v46 = -1;
        do
          ++v46;
        while ( Buffer[v46] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v46, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v47 = Class;
        if ( *(_QWORD *)(m + 32) )
          v47 = *(const CHAR **)(m + 32);
        StringCchPrintfA(Buffer, 0x400u, "\t\t<LocationRef value=\"%s\"/>\r\n", v47);
        v48 = -1;
        do
          ++v48;
        while ( Buffer[v48] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v48, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        StringCchPrintfA(Buffer, 0x400u, "\t\t<Version value=%ld/>\r\n", *(_DWORD *)(m + 44));
        v49 = -1;
        do
          ++v49;
        while ( Buffer[v49] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v49, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        StringCchPrintfA(Buffer, 0x400u, "\t\t<LastPromptedVersion value=%ld/>\r\n", *(_DWORD *)(m + 48));
        v50 = -1;
        do
          ++v50;
        while ( Buffer[v50] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v50, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v51 = Class;
        if ( *(_QWORD *)m )
          v51 = *(const CHAR **)m;
        StringCchPrintfA(Buffer, 0x400u, "\t\t<TitleSampleLocation value=\"%s\"/>\r\n", v51);
        v52 = -1;
        do
          ++v52;
        while ( Buffer[v52] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v52, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        v53 = Class;
        if ( *(_QWORD *)(m + 64) )
          v53 = *(const CHAR **)(m + 64);
        StringCchPrintfA(Buffer, 0x400u, "\t\t<TitleQueryLocation value=\"%s\"/>\r\n", v53);
        v54 = -1;
        do
          ++v54;
        while ( Buffer[v54] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v54, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        StringCchPrintfA(Buffer, 0x400u, "\t\t<SupportsMerge value=%d/>\r\n", *(_DWORD *)(m + 52));
        v55 = -1;
        do
          ++v55;
        while ( Buffer[v55] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v55, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
        StringCchCopyA(Buffer, 0x400u, "\t</LocationHistory>\r\n");
        v56 = -1;
        do
          ++v56;
        while ( Buffer[v56] );
        if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v56, &NumberOfBytesWritten, 0) )
          goto LABEL_6;
      }
      StringCchCopyA(Buffer, 0x400u, "</DocCompilation>\r\n");
      v57 = -1;
      do
        ++v57;
      while ( Buffer[v57] );
      if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v57, &NumberOfBytesWritten, 0) )
        goto LABEL_6;
    }
  }
  StringCchCopyA(Buffer, 0x400u, "</DocCompilations>\r\n");
  v58 = -1;
  do
    ++v58;
  while ( Buffer[v58] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v58, &NumberOfBytesWritten, 0) )
    goto LABEL_6;
  StringCchCopyA(Buffer, 0x400u, "</HTMLHelpDocInfo>\r\n");
  v59 = -1;
  do
    ++v59;
  while ( Buffer[v59] );
  if ( !WriteFile(*((HANDLE *)this + 120), Buffer, v59, &NumberOfBytesWritten, 0) )
  {
LABEL_6:
    v6 = (void *)*((_QWORD *)this + 120);
LABEL_7:
    CloseHandle(v6);
    return 3;
  }
  StringCchCopyA(Buffer, 0x400u, "</XML>\r\n");
  v60 = -1;
  do
    ++v60;
  while ( Buffer[v60] );
  v61 = WriteFile(*((HANDLE *)this + 120), Buffer, v60, &NumberOfBytesWritten, 0);
  v6 = (void *)*((_QWORD *)this + 120);
  if ( !v61 )
    goto LABEL_7;
  if ( !CloseHandle(v6) )
    return 17;
  v62 = CreateFileA(&gszColReg, 0x80000000, 1u, &SecurityAttributes, 3u, 0x80u, 0);
  *((_QWORD *)this + 120) = v62;
  if ( v62 == (HANDLE)-1LL )
    return 19;
  else
    return !CloseHandle(v62) ? 0x11 : 0;
}

```

## disassembly

```asm
0x180016234  push    rbp
0x180016236  push    rbx
0x180016237  push    rsi
0x180016238  push    rdi
0x180016239  push    r12
0x18001623b  push    r13
0x18001623d  push    r14
0x18001623f  push    r15
0x180016241  lea     rbp, [rsp-378h]
0x180016249  sub     rsp, 478h
0x180016250  mov     rax, cs:__security_cookie
0x180016257  xor     rax, rsp
0x18001625a  mov     [rbp+3B0h+var_50], rax
0x180016261  xor     r15d, r15d
0x180016264  mov     qword ptr [rsp+4B0h+SecurityAttributes.nLength], 18h
0x18001626d  mov     [rsp+4B0h+NumberOfBytesWritten], r15d
0x180016272  mov     rbx, rcx
0x180016275  mov     qword ptr [rsp+4B0h+SecurityAttributes.bInheritHandle], r15
0x18001627a  mov     [rsp+4B0h+SecurityAttributes.lpSecurityDescriptor], r15
0x18001627f  call    ?HHCheckGlobalAccess@@YA_NXZ; HHCheckGlobalAccess(void)
0x180016284  mov     [rsp+4B0h+hTemplateFile], r15; hTemplateFile
0x180016289  lea     edi, [r15+1]
0x18001628d  mov     r8d, edi; dwShareMode
0x180016290  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180016298  lea     r9, [rsp+4B0h+SecurityAttributes]; lpSecurityAttributes
0x18001629d  mov     [rsp+4B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800162a5  mov     edx, 40000000h; dwDesiredAccess
0x1800162aa  lea     rcx, ?gszColReg@@3PADA; lpFileName
0x1800162b1  mov     r14b, al
0x1800162b4  call    cs:__imp_CreateFileA
0x1800162ba  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800162be  mov     [rbx+3C0h], rax
0x1800162c5  cmp     rax, r12
0x1800162c8  jnz     short loc_1800162D1
0x1800162ca  mov     eax, edi
0x1800162cc  jmp     loc_180016F93
0x1800162d1  mov     r13d, 400h
0x1800162d7  lea     r8, aXml_0; "<XML>\r\n"
0x1800162de  mov     edx, r13d; unsigned __int64
0x1800162e1  lea     rcx, [rsp+4B0h+Buffer]; char *
0x1800162e6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800162eb  mov     r8, r12
0x1800162ee  lea     r10, [rsp+4B0h+Buffer]
0x1800162f3  inc     r8; nNumberOfBytesToWrite
0x1800162f6  cmp     [r10+r8], r15b
0x1800162fa  jnz     short loc_1800162F3
0x1800162fc  mov     rcx, [rbx+3C0h]; hFile
0x180016303  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016308  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x18001630d  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016312  call    cs:__imp_WriteFile
0x180016318  test    eax, eax
0x18001631a  jnz     short loc_180016333
0x18001631c  mov     rcx, [rbx+3C0h]; hObject
0x180016323  call    cs:__imp_CloseHandle
0x180016329  mov     eax, 3
0x18001632e  jmp     loc_180016F93
0x180016333  lea     r8, aHtmlhelpdocinf_0; "<HTMLHelpDocInfo>\r\n"
0x18001633a  mov     rdx, r13; unsigned __int64
0x18001633d  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016342  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180016347  mov     r8, r12
0x18001634a  lea     r10, [rsp+4B0h+Buffer]
0x18001634f  inc     r8; nNumberOfBytesToWrite
0x180016352  cmp     [r10+r8], r15b
0x180016356  jnz     short loc_18001634F
0x180016358  mov     rcx, [rbx+3C0h]; hFile
0x18001635f  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016364  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180016369  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x18001636e  call    cs:__imp_WriteFile
0x180016374  test    eax, eax
0x180016376  jz      short loc_18001631C
0x180016378  mov     r9d, [rbx+3A0h]
0x18001637f  lea     r8, aNextcollection; "<NextCollectionId value=%d/>\r\n"
0x180016386  mov     rdx, r13; unsigned __int64
0x180016389  lea     rcx, [rsp+4B0h+Buffer]; char *
0x18001638e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016393  lea     rax, [rsp+4B0h+Buffer]
0x180016398  mov     r8, r12
0x18001639b  inc     r8; nNumberOfBytesToWrite
0x18001639e  cmp     [rax+r8], r15b
0x1800163a2  jnz     short loc_18001639B
0x1800163a4  mov     rcx, [rbx+3C0h]; hFile
0x1800163ab  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800163b0  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800163b5  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1800163ba  call    cs:__imp_WriteFile
0x1800163c0  test    eax, eax
0x1800163c2  jz      loc_18001631C
0x1800163c8  lea     r8, aCollections_0; "<Collections>\r\n"
0x1800163cf  mov     rdx, r13; unsigned __int64
0x1800163d2  lea     rcx, [rsp+4B0h+Buffer]; char *
0x1800163d7  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800163dc  mov     r8, r12
0x1800163df  lea     r10, [rsp+4B0h+Buffer]
0x1800163e4  inc     r8; nNumberOfBytesToWrite
0x1800163e7  cmp     [r10+r8], r15b
0x1800163eb  jnz     short loc_1800163E4
0x1800163ed  mov     rcx, [rbx+3C0h]; hFile
0x1800163f4  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800163f9  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800163fe  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016403  call    cs:__imp_WriteFile
0x180016409  test    eax, eax
0x18001640b  jz      loc_18001631C
0x180016411  mov     rdi, [rbx+3D0h]
0x180016418  lea     rsi, Class
0x18001641f  test    rdi, rdi
0x180016422  jz      loc_180016573
0x180016428  test    r14b, r14b
0x18001642b  jnz     short loc_18001643B
0x18001642d  cmp     dword ptr [rdi], 0F4240h
0x180016433  jnb     short loc_18001643B
0x180016435  mov     rdi, [rdi+10h]
0x180016439  jmp     short loc_18001641F
0x18001643b  lea     r8, aCollection_1; "<Collection>\r\n"
0x180016442  mov     rdx, r13; unsigned __int64
0x180016445  lea     rcx, [rsp+4B0h+Buffer]; char *
0x18001644a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001644f  mov     r8, r12
0x180016452  lea     r10, [rsp+4B0h+Buffer]
0x180016457  inc     r8; nNumberOfBytesToWrite
0x18001645a  cmp     [r10+r8], r15b
0x18001645e  jnz     short loc_180016457
0x180016460  mov     rcx, [rbx+3C0h]; hFile
0x180016467  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001646c  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180016471  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016476  call    cs:__imp_WriteFile
0x18001647c  test    eax, eax
0x18001647e  jz      loc_18001631C
0x180016484  mov     r9d, [rdi]
0x180016487  lea     r8, aColnumValueD_0; "\t<ColNum value=%d/>\r\n"
0x18001648e  mov     rdx, r13; unsigned __int64
0x180016491  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016496  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001649b  lea     rax, [rsp+4B0h+Buffer]
0x1800164a0  mov     r8, r12
0x1800164a3  inc     r8; nNumberOfBytesToWrite
0x1800164a6  cmp     [rax+r8], r15b
0x1800164aa  jnz     short loc_1800164A3
0x1800164ac  mov     rcx, [rbx+3C0h]; hFile
0x1800164b3  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800164b8  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800164bd  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1800164c2  call    cs:__imp_WriteFile
0x1800164c8  test    eax, eax
0x1800164ca  jz      loc_18001631C
0x1800164d0  cmp     [rdi+8], r15
0x1800164d4  lea     r8, aColnameValueS; "\t<ColName value=\"%s\"/>\r\n"
0x1800164db  mov     r9, rsi
0x1800164de  lea     rcx, [rsp+4B0h+Buffer]; char *
0x1800164e3  cmovnz  r9, [rdi+8]
0x1800164e8  mov     rdx, r13; unsigned __int64
0x1800164eb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800164f0  lea     rax, [rsp+4B0h+Buffer]
0x1800164f5  mov     r8, r12
0x1800164f8  inc     r8; nNumberOfBytesToWrite
0x1800164fb  cmp     [rax+r8], r15b
0x1800164ff  jnz     short loc_1800164F8
0x180016501  mov     rcx, [rbx+3C0h]; hFile
0x180016508  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001650d  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180016512  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016517  call    cs:__imp_WriteFile
0x18001651d  test    eax, eax
0x18001651f  jz      loc_18001631C
0x180016525  lea     r8, aCollection_0; "</Collection>\r\n"
0x18001652c  mov     rdx, r13; unsigned __int64
0x18001652f  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016534  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180016539  mov     r8, r12
0x18001653c  lea     r10, [rsp+4B0h+Buffer]
0x180016541  inc     r8; nNumberOfBytesToWrite
0x180016544  cmp     [r10+r8], r15b
0x180016548  jnz     short loc_180016541
0x18001654a  mov     rcx, [rbx+3C0h]; hFile
0x180016551  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016556  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x18001655b  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016560  call    cs:__imp_WriteFile
0x180016566  test    eax, eax
0x180016568  jnz     loc_180016435
0x18001656e  jmp     loc_18001631C
0x180016573  lea     r8, aCollections; "</Collections>\r\n"
0x18001657a  mov     rdx, r13; unsigned __int64
0x18001657d  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016582  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180016587  mov     r8, r12
0x18001658a  lea     r10, [rsp+4B0h+Buffer]
0x18001658f  inc     r8; nNumberOfBytesToWrite
0x180016592  cmp     [r10+r8], r15b
0x180016596  jnz     short loc_18001658F
0x180016598  mov     rcx, [rbx+3C0h]; hFile
0x18001659f  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800165a4  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800165a9  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1800165ae  call    cs:__imp_WriteFile
0x1800165b4  test    eax, eax
0x1800165b6  jz      loc_18001631C
0x1800165bc  lea     r8, aLocations_0; "<Locations>\r\n"
0x1800165c3  mov     rdx, r13; unsigned __int64
0x1800165c6  lea     rcx, [rsp+4B0h+Buffer]; char *
0x1800165cb  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800165d0  mov     r8, r12
0x1800165d3  lea     r10, [rsp+4B0h+Buffer]
0x1800165d8  inc     r8; nNumberOfBytesToWrite
0x1800165db  cmp     [r10+r8], r15b
0x1800165df  jnz     short loc_1800165D8
0x1800165e1  mov     rcx, [rbx+3C0h]; hFile
0x1800165e8  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800165ed  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800165f2  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1800165f7  call    cs:__imp_WriteFile
0x1800165fd  test    eax, eax
0x1800165ff  jz      loc_18001631C
0x180016605  mov     rdi, [rbx+50h]
0x180016609  test    rdi, rdi
0x18001660c  jz      loc_180016863
0x180016612  test    r14b, r14b
0x180016615  jnz     short loc_180016626
0x180016617  cmp     dword ptr [rdi+48h], 0F4240h
0x18001661e  jnb     short loc_180016626
0x180016620  mov     rdi, [rdi+40h]
0x180016624  jmp     short loc_180016609
0x180016626  lea     r8, aLocation; "<Location>\r\n"
0x18001662d  mov     rdx, r13; unsigned __int64
0x180016630  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016635  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001663a  mov     r8, r12
0x18001663d  lea     r10, [rsp+4B0h+Buffer]
0x180016642  inc     r8; nNumberOfBytesToWrite
0x180016645  cmp     [r10+r8], r15b
0x180016649  jnz     short loc_180016642
0x18001664b  mov     rcx, [rbx+3C0h]; hFile
0x180016652  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016657  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x18001665c  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016661  call    cs:__imp_WriteFile
0x180016667  test    eax, eax
0x180016669  jz      loc_18001631C
0x18001666f  mov     r9d, [rdi+48h]
0x180016673  lea     r8, aLoccolnumValue; "\t<LocColNum value=%d/>\r\n"
0x18001667a  mov     rdx, r13; unsigned __int64
0x18001667d  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016682  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016687  lea     rax, [rsp+4B0h+Buffer]
0x18001668c  mov     r8, r12
0x18001668f  inc     r8; nNumberOfBytesToWrite
0x180016692  cmp     [rax+r8], r15b
0x180016696  jnz     short loc_18001668F
0x180016698  mov     rcx, [rbx+3C0h]; hFile
0x18001669f  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800166a4  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x1800166a9  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1800166ae  call    cs:__imp_WriteFile
0x1800166b4  test    eax, eax
0x1800166b6  jz      loc_18001631C
0x1800166bc  cmp     [rdi], r15
0x1800166bf  lea     rsi, Class
0x1800166c6  mov     r9, rsi
0x1800166c9  lea     r8, aLocnameValueS; "\t<LocName value=\"%s\"/>\r\n"
0x1800166d0  cmovnz  r9, [rdi]
0x1800166d4  lea     rcx, [rsp+4B0h+Buffer]; char *
0x1800166d9  mov     rdx, r13; unsigned __int64
0x1800166dc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800166e1  lea     rax, [rsp+4B0h+Buffer]
0x1800166e6  mov     r8, r12
0x1800166e9  inc     r8; nNumberOfBytesToWrite
0x1800166ec  cmp     [rax+r8], r15b
0x1800166f0  jnz     short loc_1800166E9
0x1800166f2  mov     rcx, [rbx+3C0h]; hFile
0x1800166f9  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800166fe  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180016703  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180016708  call    cs:__imp_WriteFile
0x18001670e  test    eax, eax
0x180016710  jz      loc_18001631C
0x180016716  cmp     [rdi+8], r15
0x18001671a  lea     r8, aTitlestringVal; "\t<TitleString value=\"%s\"/>\r\n"
0x180016721  mov     r9, rsi
0x180016724  lea     rcx, [rsp+4B0h+Buffer]; char *
0x180016729  cmovnz  r9, [rdi+8]
0x18001672e  mov     rdx, r13; unsigned __int64
0x180016731  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016736  lea     rax, [rsp+4B0h+Buffer]
0x18001673b  mov     r8, r12
0x18001673e  inc     r8; nNumberOfBytesToWrite
0x180016741  cmp     [rax+r8], r15b
0x180016745  jnz     short loc_18001673E
0x180016747  mov     rcx, [rbx+3C0h]; hFile
0x18001674e  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180016753  lea     rdx, [rsp+4B0h+Buffer]; lpBuffer
0x180016758  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x18001675d  call    cs:__imp_WriteFile
0x180016763  test    eax, eax
0x180016765  jz      loc_18001631C
0x18001676b  cmp     [rdi+10h], r15
0x18001676f  lea     r8, aLocpathValueS; "\t<LocPath value=\"%s\"/>\r\n"
  ... truncated ...
```
