# CFileListener::ProcessChangesFromFile(ushort *,ulong,ulong,int *,IIS_CRYPTO_STORAGE *)

- ea: `0x18000d680`
- end: `0x18000e0fb`
- name: `?ProcessChangesFromFile@CFileListener@@AEAAJPEAGKKPEAHPEAVIIS_CRYPTO_STORAGE@@@Z`
- size: `2683`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, unsigned __int16 *, unsigned int, unsigned int, int *, struct IIS_CRYPTO_STORAGE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18000d374`

## callees

- `0x180009ba8`
- `0x180009c14`
- `0x18000aed0`
- `0x18000cf68`
- `0x18000d194`
- `0x18000d680`
- `0x18000e728`
- `0x18000e7d4`
- `0x18002056c`
- `0x180020f18`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18000d9a4`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000d9a4`
- `IisRTL!PuDbgPrintW` at `0x18000d7f3`
- `IisRTL!PuDbgPrintW` at `0x18000d849`
- `IisRTL!PuDbgPrintW` at `0x18000d983`
- `IisRTL!PuDbgPrintW` at `0x18000dc5d`
- `IisRTL!PuDbgPrintW` at `0x18000ddc9`
- `IisRTL!PuDbgPrintW` at `0x18000de72`
- `IisRTL!PuDbgPrintW` at `0x18000df49`
- `IisRTL!PuDbgPrintW` at `0x18000df88`
- `IisRTL!PuDbgPrintW` at `0x18000d7f3`
- `IisRTL!PuDbgPrintW` at `0x18000d849`
- `IisRTL!PuDbgPrintW` at `0x18000d983`
- `IisRTL!PuDbgPrintW` at `0x18000dc5d`
- `IisRTL!PuDbgPrintW` at `0x18000ddc9`
- `IisRTL!PuDbgPrintW` at `0x18000de72`
- `IisRTL!PuDbgPrintW` at `0x18000df49`
- `IisRTL!PuDbgPrintW` at `0x18000df88`

## string_xrefs

- `0x18000df3d`: `[CFileListener::ProcessChanges] Unable to read from %s table. GetColumnValues on %d row failed with hr = 0x%x\n`
- `0x18000dcd3`: `[CFileListener::ProcessChanges] Deleted %s:%d.\n`
- `0x18000dc51`: `[CFileListener::ProcessChanges] Deleted key %s.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::ProcessChangesFromFile(
        CFileListener *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int *a5,
        struct IIS_CRYPTO_STORAGE *a6)
{
  unsigned int v6; // r12d
  WCHAR *v7; // r15
  unsigned int v9; // esi
  struct CWriterGlobalHelper *v10; // r14
  unsigned int v11; // r9d
  bool v12; // cf
  int v13; // ebx
  unsigned int v14; // r9d
  int GlobalHelperAndCopySchemaFile; // eax
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // r9d
  unsigned int i; // r12d
  __int64 v21; // rax
  int v22; // eax
  int v23; // edx
  unsigned int *v24; // rdx
  BOOL v25; // esi
  unsigned __int16 *v26; // r8
  _DWORD *v27; // rcx
  unsigned int v28; // r9d
  int v29; // r15d
  int ChildKey; // eax
  int v31; // eax
  unsigned int v32; // r9d
  int v33; // r15d
  int v34; // r13d
  int v35; // r11d
  int v36; // eax
  int v37; // eax
  unsigned int v38; // edx
  int v39; // eax
  unsigned int v40; // r9d
  int v41; // esi
  int v42; // eax
  unsigned __int16 *v44; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v45; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v46; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v47; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v48; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v49; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v50; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v51; // [rsp+48h] [rbp-B8h]
  unsigned int v53; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v54; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v55; // [rsp+60h] [rbp-A0h]
  struct ISimpleTableWrite2 *v56; // [rsp+68h] [rbp-98h] BYREF
  CWriterGlobalHelper *v57; // [rsp+70h] [rbp-90h] BYREF
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h] BYREF
  int v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  IErrorInfo *pperrinfo; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v63; // [rsp+98h] [rbp-68h] BYREF
  struct IIS_CRYPTO_STORAGE *v64; // [rsp+A0h] [rbp-60h]
  __int128 v65; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v66; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-38h]
  int *v68; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v69; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *v70[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD *v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v73; // [rsp+100h] [rbp+0h]
  unsigned int *v74; // [rsp+108h] [rbp+8h]
  _DWORD *v75; // [rsp+110h] [rbp+10h]
  int *v76; // [rsp+118h] [rbp+18h]
  _DWORD *v77; // [rsp+120h] [rbp+20h]
  _DWORD v78[12]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v79; // [rsp+160h] [rbp+60h] BYREF
  int v80; // [rsp+168h] [rbp+68h]
  int v81; // [rsp+16Ch] [rbp+6Ch]
  __int64 v82; // [rsp+170h] [rbp+70h]
  WCHAR *v83; // [rsp+178h] [rbp+78h]
  int v84; // [rsp+180h] [rbp+80h]
  int v85; // [rsp+184h] [rbp+84h]
  __int64 v86; // [rsp+188h] [rbp+88h]
  __int64 v87; // [rsp+190h] [rbp+90h]
  int v88; // [rsp+198h] [rbp+98h]
  int v89; // [rsp+19Ch] [rbp+9Ch]
  __int64 v90; // [rsp+1A0h] [rbp+A0h]
  _BYTE v91[12]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v92; // [rsp+1BCh] [rbp+BCh]

  v6 = a3;
  v54 = a3;
  v7 = a2;
  v55 = a2;
  v68 = a5;
  v64 = a6;
  v9 = a4;
  v56 = 0;
  v10 = 0;
  v57 = 0;
  pperrinfo = 0;
  v61 = 0;
  v59 = 3;
  v53 = 0;
  v63 = 0;
  memset_0(v70, 0, 0x50u);
  v78[0] = 0;
  v67 = 0;
  v12 = *((_DWORD *)this + 138) != 0;
  v78[1] = 1;
  v78[2] = 2;
  v78[3] = 3;
  v78[4] = 9;
  v78[5] = 4;
  v78[6] = 5;
  v78[7] = 6;
  v78[8] = 7;
  v78[9] = 8;
  v65 = 0;
  v60 = 0;
  v66 = 0;
  v69 = *(unsigned __int16 **)((char *)this + (v12 ? 0x80 : 0) + 104);
  if ( !*((_QWORD *)this + 71) )
  {
    v13 = -2147024883;
    LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C816, 1u, v11, 13, 0, 0, v49, v50, v51);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v44) = -2147024883;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        1764,
        "CFileListener::ProcessChangesFromFile",
        L"[CFileListener::ProcessChanges] Admin base object not initialized. hr = 0x%x\n",
        v44);
    }
    goto LABEL_85;
  }
  *a5 = 0;
  GlobalHelperAndCopySchemaFile = CFileListener::GetGlobalHelperAndCopySchemaFile(this, &v57);
  v13 = GlobalHelperAndCopySchemaFile;
  if ( GlobalHelperAndCopySchemaFile < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        1781,
        "CFileListener::ProcessChangesFromFile",
        L"[CFileListener::ProcessChanges] GetGlobalHelper failed with hr = 0x%x. Hence unable to get meta tables and hence"
         " unable to process changes.\n",
        GlobalHelperAndCopySchemaFile);
    v10 = v57;
    goto LABEL_86;
  }
  v10 = v57;
  v49 = (unsigned __int16 *)&v56;
  v79 = *((_QWORD *)v57 + 31);
  v16 = *((_QWORD *)this + 27);
  v85 = -268435455;
  v89 = -268435455;
  v17 = *((_QWORD *)this + 2);
  v80 = 2;
  v84 = 2;
  v87 = v16;
  v88 = 2;
  v81 = -268435447;
  v82 = 130;
  v83 = v7;
  v86 = 130;
  v90 = 130;
  v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, int *, int, int))(*(_QWORD *)v17 + 24LL))(
          v17,
          L"METABASE",
          L"MBPropertyDiff",
          &v79,
          &v59,
          3,
          2);
  v13 = v18;
  if ( v18 < 0 )
  {
    LogEvent(
      *((struct ICatalogErrorLogger2 **)this + 70),
      0xC002C814,
      1u,
      v19,
      v18,
      0,
      0,
      (unsigned __int16 *)&v56,
      v50,
      v51);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v47) = v13;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        1826,
        "CFileListener::ProcessChangesFromFile",
        L"[CFileListener::ProcessChanges] Unable to get the %s table. hr = 0x%x\n",
        L"MBPropertyDiff",
        v47);
    }
    *a5 = 1;
    goto LABEL_86;
  }
  v58 = -1;
  if ( !GetErrorInfo(0, &pperrinfo)
    && ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
         pperrinfo,
         &IID_ISimpleTableRead2,
         &v61) >= 0 )
  {
    *a5 = 1;
  }
  for ( i = 0; ; ++i )
  {
    LODWORD(v67) = 0;
    v21 = *(_QWORD *)v56;
    LODWORD(v57) = 0;
    v22 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64, _DWORD *, _BYTE *, unsigned __int16 **))(v21 + 32))(
            v56,
            i,
            10,
            v78,
            v91,
            v70);
    v13 = v22;
    if ( v22 == -2145318890 )
    {
      v13 = 0;
      if ( !i && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          1888,
          "CFileListener::ProcessChangesFromFile",
          L"[CFileListener::ProcessChanges] No changes occured.\n");
      goto LABEL_84;
    }
    if ( v22 < 0 )
    {
      LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C815, 1u, v14, v22, 0, 0, v49, v50, v51);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v49) = v13;
        LODWORD(v48) = i;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          1908,
          "CFileListener::ProcessChangesFromFile",
          L"[CFileListener::ProcessChanges] Unable to read from %s table. GetColumnValues on %d row failed with hr = 0x%x\n",
          L"MBPropertyDiff",
          v48);
      }
      goto LABEL_84;
    }
    v23 = *v73 - 46;
    if ( *v73 == 46 )
      v23 = v73[1];
    if ( v23 )
      break;
LABEL_70:
    ;
  }
  v24 = v74;
  v25 = 1;
  v26 = v70[0];
  if ( *v74 == 9989 )
    v25 = *v70[0] != 35;
  v27 = v71;
  v28 = v58;
  v29 = *v71;
  if ( v58 != *v76 )
  {
    v58 = *v76;
    if ( v53 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 71) + 288LL))(
        *((_QWORD *)this + 71),
        v53,
        v70[0]);
      v53 = 0;
    }
    if ( *v77 == 1 )
    {
      v31 = CFileListener::OpenKey(this, v73, 1, &v53, (int *)&v57);
    }
    else
    {
      if ( *v77 != 2 )
      {
        if ( *v77 == 3 )
        {
          v13 = CFileListener::OpenKey(this, v73, 0, &v53, 0);
          if ( v13 == -2147024893 )
          {
LABEL_31:
            v13 = CFileListener::SaveChange(this, i, v56);
            if ( v13 < 0 )
              goto LABEL_72;
            goto LABEL_70;
          }
        }
        else
        {
          if ( *v77 != 4 )
          {
            v13 = -2147024883;
            goto LABEL_72;
          }
          ChildKey = CFileListener::OpenParentKeyAndGetChildKey(this, v73, &v53, &v63);
          v13 = ChildKey;
          if ( ChildKey == -2147024893 )
            goto LABEL_31;
          if ( ChildKey == -2147024883 )
          {
            *v68 = 1;
LABEL_72:
            LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C816, 1u, v28, v13, v73, 0, v49, v50, v51);
            goto LABEL_84;
          }
        }
        goto LABEL_40;
      }
      v31 = CFileListener::OpenKey(this, v73, 0, &v53, 0);
    }
    v13 = v31;
LABEL_40:
    if ( v13 < 0 )
      goto LABEL_72;
    v24 = v74;
    v27 = v71;
    v26 = v70[0];
  }
  v32 = *v24;
  v33 = v29 & 4;
  v34 = 0;
  LODWORD(v65) = *v24;
  DWORD1(v65) = *v27;
  DWORD2(v65) = *v75;
  v35 = *(_DWORD *)v70[1];
  LODWORD(v66) = v92;
  HIDWORD(v65) = v35;
  *((_QWORD *)&v66 + 1) = v72;
  switch ( *v77 )
  {
    case 1:
    case 2:
      if ( !v33 || v64 )
      {
        if ( v25 )
        {
          if ( v32 != 9999 )
          {
            if ( v33 )
            {
              v13 = (*(__int64 (__fastcall **)(struct IIS_CRYPTO_STORAGE *, char *, __int128 *, int *, __int64))(*(_QWORD *)v64 + 8LL))(
                      v64,
                      (char *)&v66 + 8,
                      &v66,
                      &v60,
                      v72);
              if ( v13 < 0 )
                goto LABEL_74;
            }
            v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 71) + 152LL))(
                    *((_QWORD *)this + 71),
                    v53,
                    0,
                    &v65);
            v34 = 1;
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(v46) = v65;
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\listener.cpp",
                2112,
                "CFileListener::ProcessChangesFromFile",
                L"[CFileListener::ProcessChanges] Set %s:%d.\n",
                v73,
                v46);
            }
          }
        }
        else
        {
          v34 = 1;
        }
        goto LABEL_67;
      }
LABEL_59:
      LogEvent(g_pEventLog, 0x8002C83F, 2u, v32, 13, v73, v26, v49, v50, v51);
LABEL_67:
      if ( v13 < 0 )
        goto LABEL_74;
      if ( v34 )
      {
        v13 = CFileListener::SaveChange(this, i, v56);
        if ( v13 < 0 )
          goto LABEL_84;
      }
      goto LABEL_70;
    case 3:
      if ( !v33 || dword_18004875C )
      {
        if ( v25 )
        {
          v37 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 71) + 184LL))(
                  *((_QWORD *)this + 71),
                  v53,
                  0);
          v13 = 0;
          v34 = 1;
          if ( v37 != -2147024893 )
            v13 = v37;
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(v46) = v65;
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\listener.cpp",
              2152,
              "CFileListener::ProcessChangesFromFile",
              L"[CFileListener::ProcessChanges] Deleted %s:%d.\n",
              v73,
              v46);
          }
        }
        goto LABEL_67;
      }
      goto LABEL_59;
    case 4:
      v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 71) + 72LL))(
              *((_QWORD *)this + 71),
              v53,
              v63);
      v13 = 0;
      v34 = 1;
      if ( v36 != -2147024893 )
        v13 = v36;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          2169,
          "CFileListener::ProcessChangesFromFile",
          L"[CFileListener::ProcessChanges] Deleted key %s.\n",
          v73);
      goto LABEL_67;
  }
  v13 = -2147024883;
LABEL_74:
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v45) = v13;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      2181,
      "CFileListener::ProcessChangesFromFile",
      L"[CFileListener::ProcessChanges] Above action failed with hr= 0x%x.\n",
      v45);
  }
  LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C816, 1u, v32, v13, v73, 0, v49, v50, v51);
  if ( (_DWORD)v57 && *v77 == 1 )
    CFileListener::SaveChangeAsNodeWithNoPropertyAdded(this, (void **)v70, v56);
LABEL_84:
  v6 = v54;
  v7 = v55;
LABEL_85:
  v9 = a4;
LABEL_86:
  v38 = v53;
  if ( v53 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 71) + 288LL))(*((_QWORD *)this + 71));
    v53 = 0;
  }
  if ( dword_18004875C )
  {
    if ( dword_18004875C == 1 )
    {
      v42 = MoveFileToHistoryAndCopySchema(v7, v69, v6);
      if ( v13 >= 0 && v42 < 0 )
        v13 = v42;
    }
  }
  else
  {
    if ( v9 == -1 )
      LogEvent(
        *((struct ICatalogErrorLogger2 **)this + 70),
        0x8002C83B,
        dword_18004875C + 2,
        v14,
        v13,
        0,
        0,
        v49,
        v50,
        v51);
    else
      ++v9;
    v39 = CFileListener::ApplyChangeToHistoryFile(this, v10, v56, v7, v6, v9);
    v41 = v39;
    if ( v39 < 0 )
    {
      LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C817, 1u, v40, v39, 0, 0, v49, v50, v51);
      if ( v13 >= 0 )
        v13 = v41;
    }
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(struct ISimpleTableWrite2 *))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v10 )
    CWriterGlobalHelper::`scalar deleting destructor'(v10, v38);
  if ( v61 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    v61 = 0;
  }
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000d680  push    rbp
0x18000d682  push    rbx
0x18000d683  push    rsi
0x18000d684  push    rdi
0x18000d685  push    r12
0x18000d687  push    r13
0x18000d689  push    r14
0x18000d68b  push    r15
0x18000d68d  lea     rbp, [rsp-0E8h]
0x18000d695  sub     rsp, 1E8h
0x18000d69c  mov     rax, cs:__security_cookie
0x18000d6a3  xor     rax, rsp
0x18000d6a6  mov     [rbp+120h+var_48], rax
0x18000d6ad  mov     rax, [rbp+120h+arg_28]
0x18000d6b4  xor     ebx, ebx
0x18000d6b6  mov     r13, [rbp+120h+arg_20]
0x18000d6bd  mov     r12d, r8d
0x18000d6c0  mov     [rsp+220h+var_1C8], r8d
0x18000d6c5  mov     r15, rdx
0x18000d6c8  mov     [rsp+220h+var_1C0], rdx
0x18000d6cd  mov     rdi, rcx
0x18000d6d0  lea     r8d, [rbx+50h]; Size
0x18000d6d4  mov     [rsp+220h+var_1D0], r9d
0x18000d6d9  xor     edx, edx; Val
0x18000d6db  mov     [rbp+120h+var_150], r13
0x18000d6df  lea     rcx, [rbp+120h+var_140]; void *
0x18000d6e3  mov     [rbp+120h+var_180], rax
0x18000d6e7  mov     esi, r9d
0x18000d6ea  mov     [rsp+220h+var_1B8], rbx
0x18000d6ef  mov     r14d, ebx
0x18000d6f2  mov     [rsp+220h+var_1B0], rbx
0x18000d6f7  mov     [rbp+120h+pperrinfo], rbx
0x18000d6fb  mov     [rbp+120h+var_198], rbx
0x18000d6ff  mov     [rsp+220h+var_1A4], 3
0x18000d707  mov     [rsp+220h+var_1CC], ebx
0x18000d70b  mov     [rbp+120h+var_188], rbx
0x18000d70f  call    memset_0
0x18000d714  xor     eax, eax
0x18000d716  mov     [rbp+120h+var_F0], ebx
0x18000d719  mov     [rbp+120h+var_158], rax
0x18000d71d  xorps   xmm0, xmm0
0x18000d720  mov     eax, [rdi+228h]
0x18000d726  neg     eax
0x18000d728  mov     [rbp+120h+var_EC], 1
0x18000d72f  mov     [rbp+120h+var_E8], 2
0x18000d736  sbb     rcx, rcx
0x18000d739  mov     [rbp+120h+var_E4], 3
0x18000d740  and     ecx, 80h
0x18000d746  mov     [rbp+120h+var_E0], 9
0x18000d74d  mov     [rbp+120h+var_DC], 4
0x18000d754  mov     [rbp+120h+var_D8], 5
0x18000d75b  mov     [rbp+120h+var_D4], 6
0x18000d762  mov     [rbp+120h+var_D0], 7
0x18000d769  mov     [rbp+120h+var_CC], 8
0x18000d770  movups  [rbp+120h+var_178], xmm0
0x18000d774  mov     [rbp+120h+var_1A0], ebx
0x18000d777  movups  [rbp+120h+var_168], xmm0
0x18000d77b  mov     rax, [rcx+rdi+68h]
0x18000d780  mov     [rbp+120h+var_148], rax
0x18000d784  cmp     [rdi+238h], rbx
0x18000d78b  jnz     short loc_18000D7FE
0x18000d78d  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000d794  lea     r8d, [r14+1]; unsigned int
0x18000d798  mov     [rsp+220h+var_1F0], r14; unsigned __int16 *
0x18000d79d  mov     esi, 8007000Dh
0x18000d7a2  mov     [rsp+220h+var_1F8], r14; unsigned __int16 *
0x18000d7a7  mov     edx, 0C002C816h; unsigned int
0x18000d7ac  mov     ebx, esi
0x18000d7ae  mov     dword ptr [rsp+220h+var_200], 8007000Dh; char
0x18000d7b6  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000d7bb  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d7c2  jz      loc_18000DF98
0x18000d7c8  mov     rcx, cs:g_pDebug
0x18000d7cf  lea     rax, aCfilelistenerP_4; "[CFileListener::ProcessChanges] Admin b"...
0x18000d7d6  mov     dword ptr [rsp+220h+var_1F8], esi
0x18000d7da  lea     r9, aCfilelistenerP_11; "CFileListener::ProcessChangesFromFile"
0x18000d7e1  mov     r8d, 6E4h
0x18000d7e7  mov     [rsp+220h+var_200], rax
0x18000d7ec  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d7f3  call    cs:__imp_PuDbgPrintW
0x18000d7f9  jmp     loc_18000DF98
0x18000d7fe  lea     rdx, [rsp+220h+var_1B0]; struct CWriterGlobalHelper **
0x18000d803  mov     [r13+0], ebx
0x18000d807  mov     rcx, rdi; this
0x18000d80a  call    ?GetGlobalHelperAndCopySchemaFile@CFileListener@@AEAAJPEAPEAVCWriterGlobalHelper@@@Z; CFileListener::GetGlobalHelperAndCopySchemaFile(CWriterGlobalHelper * *)
0x18000d80f  mov     ebx, eax
0x18000d811  test    eax, eax
0x18000d813  jns     short loc_18000D859
0x18000d815  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d81c  jz      short loc_18000D84F
0x18000d81e  mov     rcx, cs:g_pDebug
0x18000d825  lea     r9, aCfilelistenerP_11; "CFileListener::ProcessChangesFromFile"
0x18000d82c  mov     dword ptr [rsp+220h+var_1F8], eax
0x18000d830  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d837  lea     rax, aCfilelistenerP_2; "[CFileListener::ProcessChanges] GetGlob"...
0x18000d83e  mov     r8d, 6F5h
0x18000d844  mov     [rsp+220h+var_200], rax
0x18000d849  call    cs:__imp_PuDbgPrintW
0x18000d84f  mov     r14, [rsp+220h+var_1B0]
0x18000d854  jmp     loc_18000DF9C
0x18000d859  mov     r14, [rsp+220h+var_1B0]
0x18000d85e  lea     rdx, [rsp+220h+var_1B8]
0x18000d863  mov     [rsp+220h+var_1E8], rdx; unsigned __int16 *
0x18000d868  lea     r8, aMbpropertydiff; "MBPropertyDiff"
0x18000d86f  mov     r9d, 2
0x18000d875  lea     rdx, [rsp+220h+var_1A4]
0x18000d87a  mov     dword ptr [rsp+220h+var_1F0], r9d
0x18000d87f  mov     ecx, 0F0000001h
0x18000d884  mov     rax, [r14+0F8h]
0x18000d88b  mov     [rbp+120h+var_C0], rax
0x18000d88f  mov     rax, [rdi+0D8h]
0x18000d896  mov     [rbp+120h+var_9C], ecx
0x18000d89c  mov     [rbp+120h+var_84], ecx
0x18000d8a2  mov     rcx, [rdi+10h]
0x18000d8a6  mov     [rbp+120h+var_B8], r9d
0x18000d8aa  mov     [rbp+120h+var_A0], r9d
0x18000d8b1  mov     [rbp+120h+var_90], rax
0x18000d8b8  mov     [rbp+120h+var_88], r9d
0x18000d8bf  lea     r9, [rbp+120h+var_C0]
0x18000d8c3  mov     [rbp+120h+var_B4], 0F0000009h
0x18000d8ca  mov     [rbp+120h+var_B0], 82h
0x18000d8d2  mov     [rbp+120h+var_A8], r15
0x18000d8d6  mov     [rbp+120h+var_98], 82h
0x18000d8e1  mov     [rbp+120h+var_80], 82h
0x18000d8ec  mov     rax, [rcx]
0x18000d8ef  mov     dword ptr [rsp+220h+var_1F8], 3
0x18000d8f7  mov     [rsp+220h+var_200], rdx
0x18000d8fc  lea     rdx, aMetabase; "METABASE"
0x18000d903  mov     rax, [rax+18h]
0x18000d907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d90c  mov     ebx, eax
0x18000d90e  test    eax, eax
0x18000d910  jns     loc_18000D996
0x18000d916  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000d91d  mov     edx, 0C002C814h; unsigned int
0x18000d922  mov     [rsp+220h+var_1F0], 0; unsigned __int16 *
0x18000d92b  mov     r8d, 1; unsigned int
0x18000d931  mov     [rsp+220h+var_1F8], 0; unsigned __int16 *
0x18000d93a  mov     dword ptr [rsp+220h+var_200], eax; char
0x18000d93e  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000d943  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d94a  jz      short loc_18000D989
0x18000d94c  mov     rcx, cs:g_pDebug
0x18000d953  lea     rax, aMbpropertydiff; "MBPropertyDiff"
0x18000d95a  mov     dword ptr [rsp+220h+var_1F0], ebx
0x18000d95e  lea     r9, aCfilelistenerP_11; "CFileListener::ProcessChangesFromFile"
0x18000d965  mov     [rsp+220h+var_1F8], rax
0x18000d96a  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d971  lea     rax, aCfilelistenerP_6; "[CFileListener::ProcessChanges] Unable "...
0x18000d978  mov     r8d, 722h
0x18000d97e  mov     [rsp+220h+var_200], rax
0x18000d983  call    cs:__imp_PuDbgPrintW
0x18000d989  mov     dword ptr [r13+0], 1
0x18000d991  jmp     loc_18000DF9C
0x18000d996  lea     rdx, [rbp+120h+pperrinfo]; pperrinfo
0x18000d99a  mov     [rsp+220h+var_1A8], 0FFFFFFFFh
0x18000d9a2  xor     ecx, ecx; dwReserved
0x18000d9a4  call    cs:__imp_GetErrorInfo
0x18000d9aa  test    eax, eax
0x18000d9ac  jnz     short loc_18000D9D4
0x18000d9ae  mov     rcx, [rbp+120h+pperrinfo]
0x18000d9b2  lea     r8, [rbp+120h+var_198]
0x18000d9b6  lea     rdx, IID_ISimpleTableRead2
0x18000d9bd  mov     rax, [rcx]
0x18000d9c0  mov     rax, [rax]
0x18000d9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9c8  test    eax, eax
0x18000d9ca  js      short loc_18000D9D4
0x18000d9cc  mov     dword ptr [r13+0], 1
0x18000d9d4  xor     r12d, r12d
0x18000d9d7  mov     rcx, [rsp+220h+var_1B8]
0x18000d9dc  lea     rdx, [rbp+120h+var_140]
0x18000d9e0  mov     [rsp+220h+var_1F8], rdx
0x18000d9e5  lea     r9, [rbp+120h+var_F0]
0x18000d9e9  lea     rdx, [rbp+120h+var_70]
0x18000d9f0  mov     dword ptr [rbp+120h+var_158], 0
0x18000d9f7  mov     [rsp+220h+var_200], rdx
0x18000d9fc  mov     r8d, 0Ah
0x18000da02  mov     rax, [rcx]
0x18000da05  mov     edx, r12d
0x18000da08  mov     dword ptr [rsp+220h+var_1B0], 0
0x18000da10  mov     rax, [rax+20h]
0x18000da14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da19  mov     ebx, eax
0x18000da1b  cmp     eax, 80210816h
0x18000da20  jz      loc_18000DF51
0x18000da26  test    eax, eax
0x18000da28  js      loc_18000DED3
0x18000da2e  mov     rcx, [rbp+120h+var_120]
0x18000da32  movzx   edx, word ptr [rcx]
0x18000da35  sub     edx, 2Eh ; '.'
0x18000da38  jnz     short loc_18000DA45
0x18000da3a  movzx   edx, word ptr [rcx+2]
0x18000da3e  xor     eax, eax
0x18000da40  movzx   ecx, ax
0x18000da43  sub     edx, ecx
0x18000da45  test    edx, edx
0x18000da47  jz      loc_18000DDFA
0x18000da4d  mov     rdx, [rbp+120h+var_118]
0x18000da51  mov     esi, 1
0x18000da56  mov     r8, [rbp+120h+var_140]
0x18000da5a  cmp     dword ptr [rdx], 2705h
0x18000da60  jnz     short loc_18000DA6C
0x18000da62  xor     eax, eax
0x18000da64  cmp     word ptr [r8], 23h ; '#'
0x18000da69  cmovz   esi, eax
0x18000da6c  mov     rax, [rbp+120h+var_108]
0x18000da70  mov     rcx, [rbp+120h+var_130]
0x18000da74  mov     r9d, [rsp+220h+var_1A8]
0x18000da79  mov     r15d, [rcx]
0x18000da7c  cmp     r9d, [rax]
0x18000da7f  jz      loc_18000DB97
0x18000da85  mov     edx, [rsp+220h+var_1CC]
0x18000da89  mov     eax, [rax]
0x18000da8b  mov     [rsp+220h+var_1A8], eax
0x18000da8f  test    edx, edx
0x18000da91  jz      short loc_18000DAB1
0x18000da93  mov     rcx, [rdi+238h]
0x18000da9a  mov     rax, [rcx]
0x18000da9d  mov     rax, [rax+120h]
0x18000daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa9  mov     [rsp+220h+var_1CC], 0
0x18000dab1  mov     rcx, [rbp+120h+var_100]
0x18000dab5  mov     edx, [rcx]
0x18000dab7  sub     edx, 1
0x18000daba  jz      loc_18000DB60
0x18000dac0  sub     edx, 1
0x18000dac3  jz      loc_18000DB52
0x18000dac9  sub     edx, 1
0x18000dacc  jz      short loc_18000DB2A
0x18000dace  cmp     edx, 1
0x18000dad1  jnz     loc_18000DE02
0x18000dad7  mov     rdx, [rbp+120h+var_120]; unsigned __int16 *
0x18000dadb  lea     r9, [rbp+120h+var_188]; unsigned __int16 **
0x18000dadf  lea     r8, [rsp+220h+var_1CC]; unsigned int *
0x18000dae4  mov     rcx, rdi; this
0x18000dae7  call    ?OpenParentKeyAndGetChildKey@CFileListener@@AEAAJPEAGPEAKPEAPEAG@Z; CFileListener::OpenParentKeyAndGetChildKey(ushort *,ulong *,ushort * *)
0x18000daec  mov     ebx, eax
0x18000daee  cmp     eax, 80070003h
0x18000daf3  jnz     short loc_18000DB14
0x18000daf5  mov     r8, [rsp+220h+var_1B8]; struct ISimpleTableWrite2 *
0x18000dafa  mov     edx, r12d; unsigned int
0x18000dafd  mov     rcx, rdi; this
0x18000db00  call    ?SaveChange@CFileListener@@AEAAJKPEAUISimpleTableWrite2@@@Z; CFileListener::SaveChange(ulong,ISimpleTableWrite2 *)
0x18000db05  mov     ebx, eax
0x18000db07  test    eax, eax
0x18000db09  js      loc_18000DE07
0x18000db0f  jmp     loc_18000DDFA
0x18000db14  cmp     eax, 8007000Dh
0x18000db19  jnz     short loc_18000DB83
0x18000db1b  mov     rax, [rbp+120h+var_150]
0x18000db1f  mov     dword ptr [rax], 1
0x18000db25  jmp     loc_18000DE07
0x18000db2a  mov     rdx, [rbp+120h+var_120]; unsigned __int16 *
0x18000db2e  lea     r9, [rsp+220h+var_1CC]; unsigned int *
0x18000db33  xor     r8d, r8d; int
0x18000db36  mov     [rsp+220h+var_200], 0; int *
0x18000db3f  mov     rcx, rdi; this
0x18000db42  call    ?OpenKey@CFileListener@@AEAAJPEAGHPEAKPEAH@Z; CFileListener::OpenKey(ushort *,int,ulong *,int *)
0x18000db47  mov     ebx, eax
0x18000db49  cmp     eax, 80070003h
0x18000db4e  jnz     short loc_18000DB83
0x18000db50  jmp     short loc_18000DAF5
0x18000db52  mov     [rsp+220h+var_200], 0
0x18000db5b  xor     r8d, r8d
0x18000db5e  jmp     short loc_18000DB70
0x18000db60  lea     rax, [rsp+220h+var_1B0]
0x18000db65  mov     r8d, 1; int
0x18000db6b  mov     [rsp+220h+var_200], rax; int *
0x18000db70  mov     rdx, [rbp+120h+var_120]; unsigned __int16 *
0x18000db74  lea     r9, [rsp+220h+var_1CC]; unsigned int *
0x18000db79  mov     rcx, rdi; this
0x18000db7c  call    ?OpenKey@CFileListener@@AEAAJPEAGHPEAKPEAH@Z; CFileListener::OpenKey(ushort *,int,ulong *,int *)
0x18000db81  mov     ebx, eax
0x18000db83  test    ebx, ebx
0x18000db85  js      loc_18000DE07
0x18000db8b  mov     rdx, [rbp+120h+var_118]
0x18000db8f  mov     rcx, [rbp+120h+var_130]
0x18000db93  mov     r8, [rbp+120h+var_140]
0x18000db97  mov     r9d, [rdx]; unsigned int
0x18000db9a  and     r15d, 4
0x18000db9e  mov     r10, [rbp+120h+var_128]
0x18000dba2  xor     r13d, r13d
0x18000dba5  mov     dword ptr [rbp+120h+var_178], r9d
0x18000dba9  mov     eax, [rcx]
0x18000dbab  mov     dword ptr [rbp+120h+var_178+4], eax
0x18000dbae  mov     rax, [rbp+120h+var_110]
0x18000dbb2  mov     ecx, [rax]
0x18000dbb4  mov     rax, [rbp+120h+var_138]
0x18000dbb8  mov     dword ptr [rbp+120h+var_178+8], ecx
0x18000dbbb  mov     rcx, [rbp+120h+var_100]
0x18000dbbf  mov     r11d, [rax]
0x18000dbc2  mov     eax, [rbp+120h+var_64]
0x18000dbc8  mov     dword ptr [rbp+120h+var_168], eax
0x18000dbcb  mov     dword ptr [rbp+120h+var_178+0Ch], r11d
0x18000dbcf  mov     qword ptr [rbp+120h+var_168+8], r10
0x18000dbd3  mov     edx, [rcx]
0x18000dbd5  sub     edx, 1
0x18000dbd8  jz      loc_18000DCDF
0x18000dbde  sub     edx, 1
  ... truncated ...
```
