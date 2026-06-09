# CGenerateMSI::AddDll(ushort const *,ulong,ulong,ulong,_tagCLASSINFO *)

- ea: `0x18002b820`
- end: `0x18002c042`
- name: `?AddDll@CGenerateMSI@@UEAAJPEBGKKKPEAU_tagCLASSINFO@@@Z`
- size: `2082`
- prototype: `__int64 __fastcall(CGenerateMSI *this, WCHAR *, unsigned int, int, unsigned int, GUID *rguid)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18002b820`
- `0x18002dda8`
- `0x18002deac`
- `0x18002e0c8`
- `0x18002e620`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b99e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b96f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b96f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b960`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002b960`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b992`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bbb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002beee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bbb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bc82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bd30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002beee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfe4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c002`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c00c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bf3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bf3b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b899`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002bac8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b899`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002bac8`

## string_xrefs

- `0x18002ba1a`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002bd57`: `CLSID\%s\InprocServer32`
- `0x18002b8c3`: `Dll_%s`
- `0x18002bb25`: `CLSID\%s`
- `0x18002bbe0`: `CLSID\%s\ProgID`
- `0x18002bca9`: `CLSID\%s\InstalledVersion`
- `0x18002bd13`: `CLSID%sThreading`
- `0x18002bd7b`: `ThreadingModel`
- `0x18002bf52`: `%s\CLSID`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddDll(
        CGenerateMSI *this,
        WCHAR *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        GUID *rguid)
{
  int inserted; // ebx
  unsigned __int16 *v11; // r12
  void *v12; // rdi
  CGenerateMSI *v13; // rcx
  int Identifier; // eax
  HANDLE FileW; // rax
  void *v16; // rbx
  signed int LastError; // eax
  DWORD FileSize; // r14d
  CGenerateMSI *v19; // rcx
  CGenerateMSI *v20; // rcx
  unsigned __int16 *v21; // rdx
  unsigned __int16 *v22; // rax
  unsigned int i; // r14d
  const unsigned __int16 *v24; // rsi
  GUID *v25; // r13
  CGenerateMSI *v26; // rcx
  const unsigned __int16 *v27; // rax
  CGenerateMSI *v28; // rcx
  const unsigned __int16 *v29; // rax
  CGenerateMSI *v30; // rcx
  CGenerateMSI *v31; // rcx
  DWORD j; // esi
  CGenerateMSI *v33; // rcx
  __int64 v34; // r14
  __int64 v35; // rax
  unsigned __int64 v36; // rbx
  void *v37; // rax
  const unsigned __int16 *v38; // rdi
  const unsigned __int16 *v39; // rcx
  const unsigned __int16 *v40; // r8
  CGenerateMSI *v41; // rcx
  __int64 v42; // rax
  unsigned __int64 v43; // rbx
  void *v44; // rax
  const unsigned __int16 *v45; // rdi
  const unsigned __int16 *v46; // rax
  const unsigned __int16 *v47; // r8
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+68h] [rbp-98h]
  unsigned int v52; // [rsp+6Ch] [rbp-94h]
  LPVOID v53; // [rsp+70h] [rbp-90h]
  unsigned int v54; // [rsp+78h] [rbp-88h]
  int v55; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v56; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v57; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v58; // [rsp+90h] [rbp-70h] BYREF
  GUID *v59; // [rsp+98h] [rbp-68h]
  OLECHAR sz[40]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v61[64]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v62[64]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v63[48]; // [rsp+1F0h] [rbp+F0h] BYREF

  inserted = 0;
  v54 = a3;
  v55 = a4;
  v59 = rguid;
  pv = 0;
  v56 = 0;
  v53 = 0;
  v57 = 0;
  v11 = 0;
  v58 = 0;
  v12 = 0;
  if ( !StringFromGUID2(rguid, sz, 39) )
  {
LABEL_78:
    inserted = -2147418113;
    goto LABEL_79;
  }
  v51 = 0;
  if ( !a2 || !*a2 )
    goto LABEL_21;
  inserted = StringCchPrintfW(v63, 0x2Cu, L"Dll_%s", sz);
  if ( inserted < 0 )
    goto LABEL_79;
  Identifier = CGenerateMSI::GenerateIdentifier(v13, (unsigned __int16 **)&pv, v63);
  v11 = (unsigned __int16 *)pv;
  inserted = Identifier;
  if ( Identifier < 0 )
    goto LABEL_79;
  inserted = CGenerateMSI::_InsertComponent(this, (const unsigned __int16 *)pv, sz, *((_DWORD *)this + 162));
  if ( inserted < 0 )
    goto LABEL_79;
  v51 = 1;
  if ( (a3 & 0x20) != 0 && (unsigned int)(a4 - 7) > 2 )
  {
LABEL_21:
    for ( i = 0; ; ++i )
    {
      v52 = i;
      if ( i >= a5 )
        goto LABEL_79;
      v24 = 0;
      v25 = &v59[3 * i];
      if ( *(_DWORD *)v25[1].Data4 )
        v24 = **(const unsigned __int16 ***)v25[2].Data4;
      if ( !StringFromGUID2(&v59[3 * i], sz, 39) )
        goto LABEL_78;
      inserted = StringCchPrintfW(v61, 0x3Du, L"%s_APPID", sz);
      if ( inserted < 0 )
        goto LABEL_79;
      CoTaskMemFree(v12);
      pv = 0;
      inserted = CGenerateMSI::GenerateIdentifier(v26, (unsigned __int16 **)&pv, v61);
      if ( inserted < 0 )
        goto LABEL_77;
      inserted = StringCchPrintfW(v62, 0x40u, L"CLSID\\%s", sz);
      if ( inserted < 0 )
        goto LABEL_77;
      v27 = v11;
      if ( !v51 )
        v27 = (const unsigned __int16 *)*((_QWORD *)this + 79);
      v12 = pv;
      inserted = CGenerateMSI::_AddRegKey(
                   this,
                   (const unsigned __int16 *)pv,
                   v62,
                   L"AppID",
                   *((const unsigned __int16 **)this + 80),
                   v27);
      if ( inserted < 0 )
        goto LABEL_79;
      if ( v24 )
      {
        inserted = StringCchPrintfW(v61, 0x3Du, L"%s_PRGID", sz);
        if ( inserted < 0 )
          goto LABEL_79;
        CoTaskMemFree(v12);
        pv = 0;
        inserted = CGenerateMSI::GenerateIdentifier(v28, (unsigned __int16 **)&pv, v61);
        if ( inserted < 0 )
          goto LABEL_77;
        inserted = StringCchPrintfW(v62, 0x40u, L"CLSID\\%s\\ProgID", sz);
        if ( inserted < 0 )
          goto LABEL_77;
        v29 = v11;
        if ( !v51 )
          v29 = (const unsigned __int16 *)*((_QWORD *)this + 79);
        v12 = pv;
        inserted = CGenerateMSI::_AddRegKey(this, (const unsigned __int16 *)pv, v62, &word_18005C890, v24, v29);
        if ( inserted < 0 )
          goto LABEL_79;
      }
      if ( (v54 & 0x20) != 0 && (unsigned int)(v55 - 8) > 1 )
        break;
LABEL_75:
      ;
    }
    inserted = StringCchPrintfW(v61, 0x3Du, L"%s_InstVer", sz);
    if ( inserted < 0 )
      goto LABEL_79;
    CoTaskMemFree(v12);
    pv = 0;
    inserted = CGenerateMSI::GenerateIdentifier(v30, (unsigned __int16 **)&pv, v61);
    if ( inserted >= 0 )
    {
      inserted = StringCchPrintfW(v62, 0x40u, L"CLSID\\%s\\InstalledVersion", sz);
      if ( inserted >= 0 )
      {
        v12 = pv;
        inserted = CGenerateMSI::_AddRegKey(
                     this,
                     (const unsigned __int16 *)pv,
                     v62,
                     &word_18005C890,
                     L"1,0,0,0",
                     *((const unsigned __int16 **)this + 79));
        if ( inserted < 0 )
          goto LABEL_79;
        if ( *(_QWORD *)&v25[2].Data1 )
        {
          inserted = StringCchPrintfW(v61, 0x3Du, L"CLSID%sThreading", sz);
          if ( inserted < 0 )
            goto LABEL_79;
          CoTaskMemFree(v12);
          pv = 0;
          inserted = CGenerateMSI::GenerateIdentifier(v31, (unsigned __int16 **)&pv, v61);
          if ( inserted < 0 )
            goto LABEL_77;
          inserted = StringCchPrintfW(v62, 0x40u, L"CLSID\\%s\\InprocServer32", sz);
          if ( inserted < 0 )
            goto LABEL_77;
          v12 = pv;
          inserted = CGenerateMSI::_AddRegKey(
                       this,
                       (const unsigned __int16 *)pv,
                       v62,
                       L"ThreadingModel",
                       *(const unsigned __int16 **)&v25[2].Data1,
                       *((const unsigned __int16 **)this + 79));
          if ( inserted < 0 )
            goto LABEL_79;
        }
        for ( j = 0; ; ++j )
        {
          if ( j >= *(_DWORD *)v25[1].Data4 )
          {
            i = v52;
            goto LABEL_75;
          }
          if ( j )
          {
            dwCreationDisposition[0] = j;
            inserted = StringCchPrintfW(v61, 0x3Du, L"PROGID%s%xCurVer", sz, *(_QWORD *)dwCreationDisposition);
            if ( inserted < 0 )
              goto LABEL_79;
            CoTaskMemFree(v12);
            pv = 0;
            inserted = CGenerateMSI::GenerateIdentifier(v33, (unsigned __int16 **)&pv, v61);
            if ( inserted < 0 )
              goto LABEL_77;
            v34 = j;
            v35 = -1;
            do
              ++v35;
            while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)v25[2].Data4 + 8LL * j) + 2 * v35) );
            v36 = v35 + 8;
            CoTaskMemFree(v53);
            v37 = CoTaskMemAlloc(2 * v36);
            v53 = v37;
            v38 = (const unsigned __int16 *)v37;
            if ( !v37 )
              break;
            inserted = StringCchPrintfW(
                         (unsigned __int16 *)v37,
                         v36,
                         L"%s\\CurVer",
                         *(_QWORD *)(*(_QWORD *)v25[2].Data4 + 8LL * j));
            if ( inserted < 0 )
              goto LABEL_77;
            v39 = v11;
            if ( !v51 )
              v39 = (const unsigned __int16 *)*((_QWORD *)this + 79);
            v40 = v38;
            v12 = pv;
            inserted = CGenerateMSI::_AddRegKey(
                         this,
                         (const unsigned __int16 *)pv,
                         v40,
                         &word_18005C890,
                         **(const unsigned __int16 ***)v25[2].Data4,
                         v39);
            if ( inserted < 0 )
              goto LABEL_79;
          }
          else
          {
            v34 = 0;
          }
          dwCreationDisposition[0] = j;
          inserted = StringCchPrintfW(v61, 0x3Du, L"PROGID%s%x", sz, *(_QWORD *)dwCreationDisposition);
          if ( inserted < 0 )
            goto LABEL_79;
          CoTaskMemFree(v12);
          pv = 0;
          inserted = CGenerateMSI::GenerateIdentifier(v41, (unsigned __int16 **)&pv, v61);
          if ( inserted < 0 )
            goto LABEL_77;
          v42 = -1;
          do
            ++v42;
          while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)v25[2].Data4 + 8 * v34) + 2 * v42) );
          v43 = v42 + 7;
          CoTaskMemFree(v53);
          v44 = CoTaskMemAlloc(2 * v43);
          v53 = v44;
          v45 = (const unsigned __int16 *)v44;
          if ( !v44 )
            break;
          inserted = StringCchPrintfW(
                       (unsigned __int16 *)v44,
                       v43,
                       L"%s\\CLSID",
                       *(_QWORD *)(*(_QWORD *)v25[2].Data4 + 8 * v34));
          if ( inserted < 0 )
            goto LABEL_77;
          v46 = v11;
          if ( !v51 )
            v46 = (const unsigned __int16 *)*((_QWORD *)this + 79);
          v47 = v45;
          v12 = pv;
          inserted = CGenerateMSI::_AddRegKey(this, (const unsigned __int16 *)pv, v47, &word_18005C890, sz, v46);
          if ( inserted < 0 )
            goto LABEL_79;
        }
        inserted = -2147024882;
      }
    }
LABEL_77:
    v12 = pv;
    goto LABEL_79;
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
  v16 = FileW;
  if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, 0), CloseHandle(v16), FileSize == -1) )
  {
    LastError = GetLastError();
    inserted = LastError;
    if ( LastError > 0 )
      inserted = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    inserted = CGenerateMSI::GenerateMSIFileName(v19, a2, &v56);
    if ( inserted >= 0 )
    {
      CGenerateMSI::GenerateMSIFileVerAndLocale(v20, a2, &v57, &v58);
      v21 = L"0";
      if ( v58 )
        v21 = v58;
      v22 = L"1.1.1.2";
      if ( v57 )
        v22 = v57;
      inserted = CGenerateMSI::_InsertRow(
                   this,
                   L"File",
                   L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                   L"'%s', '%s', '%s', %ld, '%s', '%s', %d, %d",
                   v11,
                   v11,
                   v56,
                   FileSize,
                   v22,
                   v21,
                   0,
                   *((_DWORD *)this + 20));
      if ( inserted >= 0 )
      {
        inserted = CGenerateMSI::_GetMakeCab(this, a3);
        if ( inserted >= 0 )
        {
          inserted = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, unsigned __int16 *))(**((_QWORD **)this + 77) + 32LL))(
                       *((_QWORD *)this + 77),
                       a2,
                       v11);
          if ( inserted >= 0 )
            goto LABEL_21;
        }
      }
    }
  }
LABEL_79:
  CoTaskMemFree(v56);
  CoTaskMemFree(v11);
  CoTaskMemFree(v12);
  CoTaskMemFree(v53);
  CoTaskMemFree(v57);
  CoTaskMemFree(v58);
  ++*((_DWORD *)this + 20);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002b820  mov     [rsp-8+arg_18], rbx
0x18002b825  push    rbp
0x18002b826  push    rsi
0x18002b827  push    rdi
0x18002b828  push    r12
0x18002b82a  push    r13
0x18002b82c  push    r14
0x18002b82e  push    r15
0x18002b830  lea     rbp, [rsp-160h]
0x18002b838  sub     rsp, 260h
0x18002b83f  mov     rax, cs:__security_cookie
0x18002b846  xor     rax, rsp
0x18002b849  mov     [rbp+190h+var_40], rax
0x18002b850  mov     rax, [rbp+190h+rguid]
0x18002b857  xor     ebx, ebx
0x18002b859  mov     r13d, r8d
0x18002b85c  mov     [rsp+290h+var_218], r8d
0x18002b861  mov     rsi, rdx
0x18002b864  mov     [rsp+290h+var_214], r9d
0x18002b869  mov     r15, rcx
0x18002b86c  mov     [rbp+190h+var_1F8], rax
0x18002b870  lea     r8d, [rbx+27h]; cchMax
0x18002b874  mov     [rsp+290h+pv], rbx
0x18002b879  lea     rdx, [rbp+190h+sz]; lpsz
0x18002b87d  mov     [rbp+190h+var_210], rbx
0x18002b881  mov     rcx, rax; rguid
0x18002b884  mov     [rsp+290h+var_220], rbx
0x18002b889  mov     r14d, r9d
0x18002b88c  mov     [rbp+190h+var_208], rbx
0x18002b890  mov     r12d, ebx
0x18002b893  mov     [rbp+190h+var_200], rbx
0x18002b897  mov     edi, ebx
0x18002b899  call    cs:__imp_StringFromGUID2
0x18002b89f  test    eax, eax
0x18002b8a1  jz      loc_18002BFD2
0x18002b8a7  xor     edx, edx
0x18002b8a9  mov     [rsp+290h+var_228], edx
0x18002b8ad  test    rsi, rsi
0x18002b8b0  jz      loc_18002BA87
0x18002b8b6  cmp     [rsi], dx
0x18002b8b9  jz      loc_18002BA87
0x18002b8bf  lea     r9, [rbp+190h+sz]
0x18002b8c3  lea     r8, aDllS; "Dll_%s"
0x18002b8ca  lea     edx, [rbx+2Ch]; unsigned __int64
0x18002b8cd  lea     rcx, [rbp+190h+var_A0]; unsigned __int16 *
0x18002b8d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b8d9  mov     ebx, eax
0x18002b8db  test    eax, eax
0x18002b8dd  js      loc_18002BFD7
0x18002b8e3  lea     r8, [rbp+190h+var_A0]; unsigned __int16 *
0x18002b8ea  lea     rdx, [rsp+290h+pv]; unsigned __int16 **
0x18002b8ef  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002b8f4  mov     r12, [rsp+290h+pv]
0x18002b8f9  mov     ebx, eax
0x18002b8fb  test    eax, eax
0x18002b8fd  js      loc_18002BFD7
0x18002b903  mov     r9d, [r15+288h]; unsigned int
0x18002b90a  lea     r8, [rbp+190h+sz]; unsigned __int16 *
0x18002b90e  mov     rdx, r12; unsigned __int16 *
0x18002b911  mov     rcx, r15; this
0x18002b914  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002b919  xor     edx, edx
0x18002b91b  mov     ebx, eax
0x18002b91d  test    eax, eax
0x18002b91f  js      loc_18002BFD7
0x18002b925  mov     [rsp+290h+var_228], 1
0x18002b92d  test    r13b, 20h
0x18002b931  jz      short loc_18002B940
0x18002b933  lea     eax, [r14-7]
0x18002b937  cmp     eax, 2
0x18002b93a  ja      loc_18002BA87
0x18002b940  mov     [rsp+290h+hTemplateFile], rdx; hTemplateFile
0x18002b945  xor     r9d, r9d; lpSecurityAttributes
0x18002b948  mov     [rsp+290h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x18002b94c  mov     rcx, rsi; lpFileName
0x18002b94f  mov     edx, 80000000h; dwDesiredAccess
0x18002b954  mov     [rsp+290h+dwCreationDisposition], 3; dwCreationDisposition
0x18002b95c  lea     r8d, [r9+1]; dwShareMode
0x18002b960  call    cs:__imp_CreateFileW
0x18002b966  mov     rbx, rax
0x18002b969  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b96d  jnz     short loc_18002B98D
0x18002b96f  call    cs:__imp_GetLastError
0x18002b975  mov     ebx, eax
0x18002b977  test    eax, eax
0x18002b979  jle     loc_18002BFD7
0x18002b97f  movzx   ebx, ax
0x18002b982  or      ebx, 80070000h
0x18002b988  jmp     loc_18002BFD7
0x18002b98d  xor     edx, edx; lpFileSizeHigh
0x18002b98f  mov     rcx, rbx; hFile
0x18002b992  call    cs:__imp_GetFileSize
0x18002b998  mov     rcx, rbx; hObject
0x18002b99b  mov     r14d, eax
0x18002b99e  call    cs:__imp_CloseHandle
0x18002b9a4  cmp     r14d, 0FFFFFFFFh
0x18002b9a8  jz      short loc_18002B96F
0x18002b9aa  lea     r8, [rbp+190h+var_210]; unsigned __int16 **
0x18002b9ae  mov     rdx, rsi; unsigned __int16 *
0x18002b9b1  call    ?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z; CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)
0x18002b9b6  mov     ebx, eax
0x18002b9b8  test    eax, eax
0x18002b9ba  js      loc_18002BFD7
0x18002b9c0  lea     r9, [rbp+190h+var_200]; unsigned __int16 **
0x18002b9c4  mov     rdx, rsi; unsigned __int16 *
0x18002b9c7  lea     r8, [rbp+190h+var_208]; unsigned __int16 **
0x18002b9cb  call    ?GenerateMSIFileVerAndLocale@CGenerateMSI@@AEAAJPEAGPEAPEAG1@Z; CGenerateMSI::GenerateMSIFileVerAndLocale(ushort *,ushort * *,ushort * *)
0x18002b9d0  mov     rax, [rbp+190h+var_200]
0x18002b9d4  lea     rdx, Default; "0"
0x18002b9db  mov     r8, [rbp+190h+var_208]
0x18002b9df  xor     r9d, r9d
0x18002b9e2  mov     ecx, [r15+50h]
0x18002b9e6  test    rax, rax
0x18002b9e9  mov     [rsp+290h+var_238], ecx
0x18002b9ed  mov     rcx, r15; this
0x18002b9f0  mov     [rsp+290h+var_240], r9
0x18002b9f5  cmovnz  rdx, rax
0x18002b9f9  mov     [rsp+290h+var_248], rdx
0x18002b9fe  lea     rax, a1112; "1.1.1.2"
0x18002ba05  test    r8, r8
0x18002ba08  lea     r9, aSSSLdSSDD; "'%s', '%s', '%s', %ld, '%s', '%s', %d, "...
0x18002ba0f  lea     rdx, aFile_0; "File"
0x18002ba16  cmovnz  rax, r8
0x18002ba1a  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002ba21  mov     [rsp+290h+var_250], rax
0x18002ba26  mov     rax, [rbp+190h+var_210]
0x18002ba2a  mov     [rsp+290h+var_258], r14d
0x18002ba2f  mov     [rsp+290h+hTemplateFile], rax
0x18002ba34  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], r12
0x18002ba39  mov     qword ptr [rsp+290h+dwCreationDisposition], r12
0x18002ba3e  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002ba43  mov     ebx, eax
0x18002ba45  test    eax, eax
0x18002ba47  js      loc_18002BFD7
0x18002ba4d  mov     edx, r13d; unsigned int
0x18002ba50  mov     rcx, r15; this
0x18002ba53  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002ba58  mov     ebx, eax
0x18002ba5a  test    eax, eax
0x18002ba5c  js      loc_18002BFD7
0x18002ba62  mov     rcx, [r15+268h]
0x18002ba69  mov     r8, r12
0x18002ba6c  mov     rdx, rsi
0x18002ba6f  mov     rax, [rcx]
0x18002ba72  mov     rax, [rax+20h]
0x18002ba76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba7b  xor     edx, edx
0x18002ba7d  mov     ebx, eax
0x18002ba7f  test    eax, eax
0x18002ba81  js      loc_18002BFD7
0x18002ba87  mov     r14d, edx
0x18002ba8a  mov     [rsp+290h+var_224], r14d
0x18002ba8f  cmp     r14d, [rbp+190h+arg_20]
0x18002ba96  jnb     loc_18002BFD7
0x18002ba9c  mov     eax, r14d
0x18002ba9f  mov     rsi, rdx
0x18002baa2  lea     r13, [rax+rax*2]
0x18002baa6  shl     r13, 4
0x18002baaa  add     r13, [rbp+190h+var_1F8]
0x18002baae  cmp     [r13+18h], edx
0x18002bab2  jbe     short loc_18002BABB
0x18002bab4  mov     rax, [r13+28h]
0x18002bab8  mov     rsi, [rax]
0x18002babb  mov     r8d, 27h ; '''; cchMax
0x18002bac1  lea     rdx, [rbp+190h+sz]; lpsz
0x18002bac5  mov     rcx, r13; rguid
0x18002bac8  call    cs:__imp_StringFromGUID2
0x18002bace  test    eax, eax
0x18002bad0  jz      loc_18002BFD2
0x18002bad6  lea     r9, [rbp+190h+sz]
0x18002bada  mov     edx, 3Dh ; '='; unsigned __int64
0x18002badf  lea     r8, aSAppid; "%s_APPID"
0x18002bae6  lea     rcx, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002baea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002baef  mov     ebx, eax
0x18002baf1  test    eax, eax
0x18002baf3  js      loc_18002BFD7
0x18002baf9  mov     rcx, rdi; pv
0x18002bafc  call    cs:__imp_CoTaskMemFree
0x18002bb02  xor     edi, edi
0x18002bb04  lea     r8, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002bb08  lea     rdx, [rsp+290h+pv]; unsigned __int16 **
0x18002bb0d  mov     [rsp+290h+pv], rdi
0x18002bb12  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002bb17  mov     ebx, eax
0x18002bb19  test    eax, eax
0x18002bb1b  js      loc_18002BFCB
0x18002bb21  lea     r9, [rbp+190h+sz]
0x18002bb25  lea     r8, aClsidS; "CLSID\\%s"
0x18002bb2c  lea     edx, [rdi+40h]; unsigned __int64
0x18002bb2f  lea     rcx, [rbp+190h+var_120]; unsigned __int16 *
0x18002bb33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb38  mov     ebx, eax
0x18002bb3a  test    eax, eax
0x18002bb3c  js      loc_18002BFCB
0x18002bb42  mov     rax, r12
0x18002bb45  cmp     [rsp+290h+var_228], edi
0x18002bb49  jnz     short loc_18002BB52
0x18002bb4b  mov     rax, [r15+278h]
0x18002bb52  mov     rdi, [rsp+290h+pv]
0x18002bb57  lea     r9, aAppid; "AppID"
0x18002bb5e  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002bb63  lea     r8, [rbp+190h+var_120]; unsigned __int16 *
0x18002bb67  mov     rax, [r15+280h]
0x18002bb6e  mov     rdx, rdi; unsigned __int16 *
0x18002bb71  mov     rcx, r15; this
0x18002bb74  mov     qword ptr [rsp+290h+dwCreationDisposition], rax; unsigned __int16 *
0x18002bb79  call    ?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z; CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002bb7e  mov     ebx, eax
0x18002bb80  test    eax, eax
0x18002bb82  js      loc_18002BFD7
0x18002bb88  test    rsi, rsi
0x18002bb8b  jz      loc_18002BC3C
0x18002bb91  lea     r9, [rbp+190h+sz]
0x18002bb95  mov     edx, 3Dh ; '='; unsigned __int64
0x18002bb9a  lea     r8, aSPrgid; "%s_PRGID"
0x18002bba1  lea     rcx, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002bba5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bbaa  mov     ebx, eax
0x18002bbac  test    eax, eax
0x18002bbae  js      loc_18002BFD7
0x18002bbb4  mov     rcx, rdi; pv
0x18002bbb7  call    cs:__imp_CoTaskMemFree
0x18002bbbd  xor     edi, edi
0x18002bbbf  lea     r8, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002bbc3  lea     rdx, [rsp+290h+pv]; unsigned __int16 **
0x18002bbc8  mov     [rsp+290h+pv], rdi
0x18002bbcd  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002bbd2  mov     ebx, eax
0x18002bbd4  test    eax, eax
0x18002bbd6  js      loc_18002BFCB
0x18002bbdc  lea     r9, [rbp+190h+sz]
0x18002bbe0  lea     r8, aClsidSProgid; "CLSID\\%s\\ProgID"
0x18002bbe7  lea     edx, [rdi+40h]; unsigned __int64
0x18002bbea  lea     rcx, [rbp+190h+var_120]; unsigned __int16 *
0x18002bbee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bbf3  mov     ebx, eax
0x18002bbf5  test    eax, eax
0x18002bbf7  js      loc_18002BFCB
0x18002bbfd  mov     rax, r12
0x18002bc00  cmp     [rsp+290h+var_228], edi
0x18002bc04  jnz     short loc_18002BC0D
0x18002bc06  mov     rax, [r15+278h]
0x18002bc0d  mov     rdi, [rsp+290h+pv]
0x18002bc12  lea     r9, word_18005C890; unsigned __int16 *
0x18002bc19  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002bc1e  lea     r8, [rbp+190h+var_120]; unsigned __int16 *
0x18002bc22  mov     rdx, rdi; unsigned __int16 *
0x18002bc25  mov     qword ptr [rsp+290h+dwCreationDisposition], rsi; unsigned __int16 *
0x18002bc2a  mov     rcx, r15; this
0x18002bc2d  call    ?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z; CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002bc32  mov     ebx, eax
0x18002bc34  test    eax, eax
0x18002bc36  js      loc_18002BFD7
0x18002bc3c  test    byte ptr [rsp+290h+var_218], 20h
0x18002bc41  jz      loc_18002BFBC
0x18002bc47  mov     eax, [rsp+290h+var_214]
0x18002bc4b  add     eax, 0FFFFFFF8h
0x18002bc4e  cmp     eax, 1
0x18002bc51  jbe     loc_18002BFBC
0x18002bc57  mov     esi, 3Dh ; '='
0x18002bc5c  lea     r9, [rbp+190h+sz]
0x18002bc60  mov     edx, esi; unsigned __int64
0x18002bc62  lea     r8, aSInstver; "%s_InstVer"
0x18002bc69  lea     rcx, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002bc6d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bc72  xor     r14d, r14d
0x18002bc75  mov     ebx, eax
0x18002bc77  test    eax, eax
0x18002bc79  js      loc_18002BFD7
0x18002bc7f  mov     rcx, rdi; pv
0x18002bc82  call    cs:__imp_CoTaskMemFree
0x18002bc88  lea     r8, [rbp+190h+var_1A0]; unsigned __int16 *
0x18002bc8c  mov     [rsp+290h+pv], r14
0x18002bc91  lea     rdx, [rsp+290h+pv]; unsigned __int16 **
0x18002bc96  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002bc9b  mov     ebx, eax
0x18002bc9d  test    eax, eax
0x18002bc9f  js      loc_18002BFCB
0x18002bca5  lea     r9, [rbp+190h+sz]
0x18002bca9  lea     r8, aClsidSInstalle; "CLSID\\%s\\InstalledVersion"
0x18002bcb0  lea     edx, [rsi+3]; unsigned __int64
0x18002bcb3  lea     rcx, [rbp+190h+var_120]; unsigned __int16 *
0x18002bcb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bcbc  mov     ebx, eax
0x18002bcbe  test    eax, eax
0x18002bcc0  js      loc_18002BFCB
0x18002bcc6  mov     rax, [r15+278h]
0x18002bccd  lea     r9, word_18005C890; unsigned __int16 *
0x18002bcd4  mov     rdi, [rsp+290h+pv]
0x18002bcd9  lea     r8, [rbp+190h+var_120]; unsigned __int16 *
0x18002bcdd  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18002bce2  mov     rdx, rdi; unsigned __int16 *
0x18002bce5  lea     rax, a1000; "1,0,0,0"
0x18002bcec  mov     rcx, r15; this
0x18002bcef  mov     qword ptr [rsp+290h+dwCreationDisposition], rax; unsigned __int16 *
0x18002bcf4  call    ?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z; CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002bcf9  mov     ebx, eax
0x18002bcfb  test    eax, eax
0x18002bcfd  js      loc_18002BFD7
  ... truncated ...
```
