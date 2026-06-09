# MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)

- ea: `0x18004dcac`
- end: `0x18004e854`
- name: `?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z`
- size: `2984`
- prototype: `bool __fastcall(MsiUIMessageContext *__hidden this, bool, const struct CEngineMainThreadData *)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009c38`
- `0x18004d644`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x180006970`
- `0x1800069f8`
- `0x18000ca3c`
- `0x18000d6d8`
- `0x180010ac0`
- `0x180013d64`
- `0x180014160`
- `0x1800141e0`
- `0x180014e38`
- `0x180014f18`
- `0x18002e870`
- `0x18004dcac`
- `0x1800586a0`
- `0x180061c4c`
- `0x180077470`
- `0x180086264`
- `0x180087d44`
- `0x1800a5e58`
- `0x1800ae46c`
- `0x1800c08f8`
- `0x1800ee66c`
- `0x18014ae8c`
- `0x18014fd24`
- `0x18015a7e8`
- `0x18016c588`
- `0x18016cf90`
- `0x1801c8bd8`
- `0x1801cf058`
- `0x1801d86f0`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004e606`
- `msvcrt!_wcsicmp` at `0x18004e606`
- `msvcrt!wcsrchr` at `0x18004e5eb`
- `msvcrt!wcsrchr` at `0x18004e5eb`
- `ADVAPI32!SetThreadToken` at `0x18004e431`
- `ADVAPI32!SetThreadToken` at `0x18004e4a8`
- `ADVAPI32!SetThreadToken` at `0x18004e431`
- `ADVAPI32!SetThreadToken` at `0x18004e4a8`
- `ADVAPI32!OpenThreadToken` at `0x18004e419`
- `ADVAPI32!OpenThreadToken` at `0x18004e419`
- `KERNEL32!GetModuleFileNameW` at `0x18004e73d`
- `KERNEL32!GetModuleFileNameW` at `0x18004e73d`
- `KERNEL32!GetCurrentThread` at `0x18004e3f2`
- `KERNEL32!GetCurrentThread` at `0x18004e3f2`
- `KERNEL32!GlobalFree` at `0x18004df02`
- `KERNEL32!GlobalFree` at `0x18004e2b1`
- `KERNEL32!GlobalFree` at `0x18004e5d3`
- `KERNEL32!GlobalFree` at `0x18004e65e`
- `KERNEL32!GlobalFree` at `0x18004df02`
- `KERNEL32!GlobalFree` at `0x18004e2b1`
- `KERNEL32!GlobalFree` at `0x18004e5d3`
- `KERNEL32!GlobalFree` at `0x18004e65e`
- `KERNEL32!lstrcmpiW` at `0x18004e571`
- `KERNEL32!lstrcmpiW` at `0x18004e571`

## string_xrefs

- `0x18004e00c`: `CURRENTDIRECTORY`
- `0x18004e08c`: `MsiLogging`

## pseudocode

```c
char __fastcall MsiUIMessageContext::InitializeLog(
        MsiUIMessageContext *this,
        char a2,
        const struct CEngineMainThreadData *a3)
{
  char v4; // r14
  char v6; // r15
  char v7; // r12
  unsigned __int16 *v8; // rbx
  bool v9; // bl
  const WCHAR *v10; // rax
  unsigned __int16 *v11; // rcx
  const struct IMsiString **v12; // rax
  struct IMsiRecord *PropertyFromDatabase; // rax
  const WCHAR *v14; // rax
  void *v15; // rcx
  const WCHAR *v16; // rax
  __int64 v17; // rcx
  MsiString *v18; // rax
  const struct IMsiString **v19; // rax
  void *v20; // r14
  const struct IMsiString *v21; // rdi
  struct IMsiString *v22; // rsi
  const struct IMsiString *v23; // rbx
  const unsigned __int16 *v24; // rax
  struct IMsiRecord *v25; // rax
  int v26; // eax
  int v27; // eax
  HGLOBAL v28; // rcx
  const unsigned __int16 *v29; // rax
  unsigned int v30; // eax
  char v31; // al
  struct IMsiServices *Services; // r14
  const struct IMsiString *TempDirectory; // rax
  __int64 v34; // rcx
  const struct IMsiString *v35; // rdi
  char v36; // r12
  __int64 (__fastcall *v37)(struct IMsiServices *, __int64, __int64); // rsi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rbx
  struct IMsiString *v41; // rsi
  __int64 (__fastcall *v42)(struct IMsiString *, const WCHAR *, const wchar_t *, _QWORD, struct IMsiString **, _QWORD); // rbx
  __int64 v43; // rax
  HANDLE CurrentThread; // rax
  struct IMsiString *v45; // rsi
  __int64 (__fastcall *v46)(struct IMsiString *, const WCHAR *, const wchar_t *, _QWORD, struct IMsiString **, _QWORD); // rbx
  __int64 v47; // rax
  BOOL v48; // eax
  wchar_t *v50; // rax
  unsigned int v51; // ecx
  bool v52; // di
  unsigned __int8 v53; // si
  char v54; // bl
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // [rsp+38h] [rbp-C8h]
  __int64 v58; // [rsp+48h] [rbp-B8h]
  int v59; // [rsp+60h] [rbp-A0h]
  struct IMsiString *v60; // [rsp+70h] [rbp-90h] BYREF
  char v61; // [rsp+78h] [rbp-88h]
  struct IMsiString *v62; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  struct IMsiString *v65; // [rsp+98h] [rbp-68h] BYREF
  void *v66; // [rsp+A0h] [rbp-60h] BYREF
  void *Thread; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *Src; // [rsp+B0h] [rbp-50h] BYREF
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  _WORD v71[8]; // [rsp+C0h] [rbp-40h] BYREF
  HGLOBAL v72; // [rsp+D0h] [rbp-30h] BYREF
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  unsigned __int16 v75[32]; // [rsp+E0h] [rbp-20h] BYREF
  HGLOBAL hMem; // [rsp+120h] [rbp+20h] BYREF
  int v77; // [rsp+128h] [rbp+28h]
  int v78; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v79[502]; // [rsp+130h] [rbp+30h] BYREF
  __int16 v80; // [rsp+326h] [rbp+226h]

  v61 = a2;
  v4 = a2;
  v6 = 1;
  if ( hObject )
    return v6;
  v7 = 0;
  if ( !g_dwLogMode && !g_scServerContext )
  {
    v73 = 25;
    v8 = v75;
    v72 = v75;
    v75[0] = 0;
    if ( !a3 )
    {
LABEL_36:
      if ( *v8 || (v74 = 25, GetStringPolicyValue(9, 1, &v72), v8 = (unsigned __int16 *)v72, *(_WORD *)v72) )
      {
        LODWORD(v60) = 0;
        if ( !StringToModeBits(v8, L"mewuifsoarpcvxgh!", (unsigned int *)&v60) )
        {
          v30 = (unsigned int)v60;
          g_fFlushEachLine = 0;
          if ( ((unsigned int)v60 & 0x10000) != 0 )
          {
            g_fFlushEachLine = 1;
            v30 = (unsigned int)v60 & 0xFFFEFFFF;
          }
          g_dwLogMode = v30;
          v7 = 1;
        }
      }
      if ( v73 > 25 )
        GlobalFree(v8);
      goto LABEL_44;
    }
    if ( (unsigned int)GetIntegerPolicyValue(25, 1, a3) )
    {
LABEL_35:
      v8 = (unsigned __int16 *)v72;
      goto LABEL_36;
    }
    v63 = 0;
    v62 = (struct IMsiString *)&MsiString::s_NullString;
    v60 = (struct IMsiString *)&MsiString::s_NullString;
    if ( *(_DWORD *)a3 )
    {
      v9 = 0;
      if ( *(_DWORD *)a3 == 1 )
      {
        v77 = 260;
        v78 = 260;
        v11 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
        hMem = v79;
        if ( (unsigned int)ExpandPath(v11) )
        {
          MsiString::operator=(&v62, hMem);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
          v60 = (struct IMsiString *)&MsiString::s_NullString;
          v12 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&v66, L"ProductCode");
          PropertyFromDatabase = GetPropertyFromDatabase(
                                   0,
                                   v62,
                                   (const struct IMsiString *)&MsiString::s_NullString,
                                   *v12,
                                   &v60);
          CComPointer<IMsiDatabase>::operator=(&v63, PropertyFromDatabase);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v66 + 16LL))(v66);
          if ( !v63 && (*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 56LL))(v60) )
          {
            v71[0] = 0;
            Src = v71;
            v69 = 1;
            v70 = 1;
            v14 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 80LL))(v60);
            v9 = (unsigned int)GetProductInfo(v14, L"LocalPackage") != 0;
            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&Src);
          }
          (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
        }
        if ( v77 > 260 )
          GlobalFree(hMem);
      }
    }
    else
    {
      v9 = 1;
      MsiString::operator=(&v60, *((_QWORD *)a3 + 1));
      v71[0] = 0;
      Src = v71;
      v69 = 1;
      v70 = 1;
      v10 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 80LL))(v60);
      if ( (unsigned int)GetProductInfo(v10, L"LocalPackage") )
        MsiString::operator=(&v62, Src);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&Src);
    }
    if ( !(*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v62 + 56LL))(v62) )
    {
LABEL_34:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v63);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v62 + 16LL))(v62);
      goto LABEL_35;
    }
    v15 = &MsiString::s_NullString;
    TokenHandle = &MsiString::s_NullString;
    if ( v9 )
    {
      if ( (*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 56LL))(v60) )
      {
        v71[0] = 0;
        Src = v71;
        v69 = 1;
        v70 = 1;
        v16 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 80LL))(v60);
        if ( (unsigned int)GetExpandedProductInfo(v16, L"Transforms") )
          MsiString::operator=(&TokenHandle, Src);
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&Src);
        goto LABEL_26;
      }
      v15 = TokenHandle;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    v17 = *((_QWORD *)a3 + 3);
    TokenHandle = &MsiString::s_NullString;
    ProcessCommandLine(v17, 0, &TokenHandle, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0);
LABEL_26:
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v66 = &MsiString::s_NullString;
    v18 = MsiString::MsiString((MsiString *)&Thread, L"CURRENTDIRECTORY");
    LOBYTE(v59) = 0;
    ProcessCommandLine(*((_QWORD *)a3 + 3), 0, 0, 0, 0, 0, 0, *(_QWORD *)v18, &v66, 1, 0, 0, v59);
    (*(void (__fastcall **)(void *))(*(_QWORD *)Thread + 16LL))(Thread);
    v65 = (struct IMsiString *)&MsiString::s_NullString;
    (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
    v65 = (struct IMsiString *)&MsiString::s_NullString;
    v19 = (const struct IMsiString **)MsiString::MsiString((MsiString *)&Thread, L"MsiLogging");
    v20 = v66;
    v21 = (const struct IMsiString *)TokenHandle;
    v22 = v62;
    v23 = *v19;
    v24 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v66 + 80LL))(v66);
    v25 = GetPropertyFromDatabase(v24, v22, v21, v23, &v65);
    CComPointer<IMsiDatabase>::operator=(&v63, v25);
    (*(void (__fastcall **)(void *))(*(_QWORD *)Thread + 16LL))(Thread);
    if ( !v63 && (*(unsigned int (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 56LL))(v65) )
    {
      v26 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 56LL))(v65);
      if ( v73 < v26 + 1 )
      {
        v27 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 56LL))(v65);
        if ( !(unsigned __int8)CAPITempBuffer<unsigned short,25>::SetSize(&v72, (unsigned int)(v27 + 1)) )
        {
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 16LL))(v65);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
          (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v63);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v62 + 16LL))(v62);
          if ( v73 > 25 )
          {
            v28 = v72;
LABEL_78:
            GlobalFree(v28);
            return 0;
          }
          return 0;
        }
      }
      v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 80LL))(v65);
      StringCchCopyW((unsigned __int16 *)v72, v73, v29);
    }
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v65 + 16LL))(v65);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
    v4 = v61;
    goto LABEL_34;
  }
LABEL_44:
  if ( (g_dwLogMode & 0x4000) != 0 || (v31 = 0, g_dwLogMode == 0x8000) )
    v31 = 1;
  *((_BYTE *)this + 304) = v31;
  if ( v7 || v4 )
  {
    *((_BYTE *)this + 184) = 1;
    v60 = (struct IMsiString *)&MsiString::s_NullString;
    Services = LoadServices();
    TempDirectory = GetTempDirectory();
    v34 = *(_QWORD *)Services;
    v35 = TempDirectory;
    v62 = 0;
    v36 = 0;
    v37 = *(__int64 (__fastcall **)(struct IMsiServices *, __int64, __int64))(v34 + 120);
    v38 = CComPointer<IEnumMsiRecord>::operator=(&v62);
    v39 = (*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v35 + 80LL))(v35);
    v63 = v37(Services, v39, v38);
    v40 = v63;
    if ( !v63 )
    {
      v41 = v62;
      v42 = *(__int64 (__fastcall **)(struct IMsiString *, const WCHAR *, const wchar_t *, _QWORD, struct IMsiString **, _QWORD))(*(_QWORD *)v62 + 304LL);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = (struct IMsiString *)&MsiString::s_NullString;
      v43 = v42(v41, L"MSI", L"LOG", 0, &v60, 0);
      CComPointer<IMsiDatabase>::operator=(&v63, v43);
      v40 = v63;
    }
    if ( !v40 )
      goto LABEL_60;
    if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 56LL))(v40, 2) == 5 )
    {
      CurrentThread = GetCurrentThread();
      TokenHandle = (void *)-1LL;
      Thread = CurrentThread;
      if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
      {
        if ( SetThreadToken(0, 0) )
        {
          v45 = v62;
          v46 = *(__int64 (__fastcall **)(struct IMsiString *, const WCHAR *, const wchar_t *, _QWORD, struct IMsiString **, _QWORD))(*(_QWORD *)v62 + 304LL);
          (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
          v60 = (struct IMsiString *)&MsiString::s_NullString;
          v47 = v46(v45, L"MSI", L"LOG", 0, &v60, 0);
          CComPointer<IMsiDatabase>::operator=(&v63, v47);
          v48 = SetThreadToken(&Thread, TokenHandle);
          v40 = v63;
          if ( !v48 )
            v36 = 1;
        }
      }
      CHandle::~CHandle((CHandle *)&TokenHandle);
    }
    if ( v40 )
    {
      v36 = 1;
    }
    else
    {
LABEL_60:
      (*(void (__fastcall **)(struct IMsiString *, LPCWSTR, _QWORD))(*(_QWORD *)v60 + 88LL))(
        v60,
        g_rgchLogFile,
        (unsigned int)(dword_18030FF08 - 1));
      if ( !g_dwLogMode )
        g_dwLogMode = 6;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v63);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v62);
    FreeServices();
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v35 + 16LL))(v35);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)v60 + 16LL))(v60);
    if ( v36 )
      return 0;
    v4 = v61;
  }
  if ( g_dwLogMode )
  {
    if ( !g_scServerContext && lstrcmpiW(g_rgchLogFile, L"NUL") )
    {
      hMem = v79;
      v77 = 261;
      v78 = 261;
      if ( !(unsigned int)ExpandPath((unsigned __int16 *)g_rgchLogFile)
        || (int)StringCchCopyW((unsigned __int16 *)g_rgchLogFile, dword_18030FF08, (const unsigned __int16 *)hMem) < 0 )
      {
        *g_rgchLogFile = 0;
        if ( v77 > 261 )
        {
          v28 = hMem;
          goto LABEL_78;
        }
        return 0;
      }
      if ( v77 > 261 )
        GlobalFree(hMem);
    }
    v50 = wcsrchr(g_rgchLogFile, 0x2Eu);
    if ( v50
      && !_wcsicmp(L".hta", v50)
      && (int)StringCchCatW((unsigned __int16 *)g_rgchLogFile, dword_18030FF08 - 1, L".LOG") < 0 )
    {
      *g_rgchLogFile = 0;
      return 0;
    }
    v51 = g_dwLogMode;
    if ( (g_dwLogMode & 0x1010) == 0x1000 )
    {
      v51 = g_dwLogMode | 0x10;
      g_dwLogMode |= 0x10u;
    }
    if ( (v51 & 0x2010) == 0x2000 )
      g_dwLogMode = v51 | 0x10;
    if ( g_scServerContext == 2 )
    {
      v52 = 1;
      v53 = 1;
    }
    else
    {
      v52 = 0;
      v53 = g_fLogAppend != 0;
    }
    v54 = IsAdmin();
    CImpersonate::CImpersonate((CImpersonate *)&v66, v52);
    if ( !CreateLog(g_rgchLogFile, v53, v4, v54) )
    {
      CImpersonate::~CImpersonate((CImpersonate *)&v66);
      return 0;
    }
    *((_DWORD *)this + 32) = g_dwLogMode & 0xB9F;
    SetDiagnosticMode();
    if ( FDiagnosticModeSet(8) && !g_scServerContext )
    {
      if ( GetModuleFileNameW(0, (LPWSTR)&hMem, 0x103u) )
      {
        v80 = 0;
        CTempBuffer<unsigned short,1>::CTempBuffer<unsigned short,1>(&Src, 460);
        if ( Src )
        {
          v55 = ((__int64 (__fastcall *)(void ***))g_MsiStringTime[10])(&g_MsiStringTime);
          v56 = ((__int64 (__fastcall *)(void ***))g_MsiStringDate[10])(&g_MsiStringDate);
          LODWORD(v58) = 10011;
          LODWORD(v57) = 5;
          if ( (int)StringCchPrintfW(
                      Src,
                      v69,
                      L"=== Verbose logging started: %s  %s  Build type: %s %s %d.%02d.%04d.%02d  Calling process: %s ===",
                      v56,
                      v55,
                      L"SHIP",
                      L"UNICODE",
                      v57,
                      0,
                      v58,
                      0,
                      &hMem) >= 0 )
            WriteLog(Src);
        }
        CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&Src);
      }
      else
      {
        v6 = 0;
      }
    }
    CImpersonate::~CImpersonate((CImpersonate *)&v66);
  }
  return v6;
}

```

## disassembly

```asm
0x18004dcac  mov     [rsp-8+arg_8], rbx
0x18004dcb1  push    rbp
0x18004dcb2  push    rsi
0x18004dcb3  push    rdi
0x18004dcb4  push    r12
0x18004dcb6  push    r13
0x18004dcb8  push    r14
0x18004dcba  push    r15
0x18004dcbc  lea     rbp, [rsp-250h]
0x18004dcc4  sub     rsp, 350h
0x18004dccb  mov     rax, cs:__security_cookie
0x18004dcd2  xor     rax, rsp
0x18004dcd5  mov     [rbp+280h+var_40], rax
0x18004dcdc  xor     esi, esi
0x18004dcde  mov     [rsp+380h+var_308], dl
0x18004dce2  cmp     cs:hObject, rsi
0x18004dce9  mov     rdi, r8
0x18004dcec  mov     r14b, dl
0x18004dcef  mov     r13, rcx
0x18004dcf2  lea     r15d, [rsi+1]
0x18004dcf6  jnz     loc_18004E826
0x18004dcfc  cmp     cs:?g_dwLogMode@@3KA, esi; ulong g_dwLogMode
0x18004dd02  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004dd09  mov     r12b, sil
0x18004dd0c  jnz     loc_18004E2C4
0x18004dd12  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x18004dd18  jnz     loc_18004E2C4
0x18004dd1e  mov     [rbp+280h+var_2A8], 19h
0x18004dd25  lea     rbx, [rbp+280h+var_2A0]
0x18004dd29  mov     [rbp+280h+var_2B0], rbx
0x18004dd2d  mov     [rbp+280h+var_2A0], si
0x18004dd31  test    r8, r8
0x18004dd34  jz      loc_18004E241
0x18004dd3a  mov     edx, r15d
0x18004dd3d  lea     ecx, [rsi+19h]
0x18004dd40  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x18004dd45  test    eax, eax
0x18004dd47  jnz     loc_18004E23D
0x18004dd4d  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004dd54  mov     [rbp+280h+var_2F8], rsi
0x18004dd58  mov     [rbp+280h+var_300], rax
0x18004dd5c  mov     [rsp+380h+var_310], rax
0x18004dd61  cmp     [rdi], esi
0x18004dd63  jnz     short loc_18004DDCF
0x18004dd65  mov     rdx, [rdi+8]
0x18004dd69  lea     rcx, [rsp+380h+var_310]
0x18004dd6e  mov     bl, r15b
0x18004dd71  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x18004dd76  mov     rcx, [rsp+380h+var_310]
0x18004dd7b  xor     eax, eax
0x18004dd7d  mov     [rbp+280h+var_2C0], ax
0x18004dd81  lea     rax, [rbp+280h+var_2C0]
0x18004dd85  mov     [rbp+280h+Src], rax
0x18004dd89  mov     [rbp+280h+var_2C8], r15d
0x18004dd8d  mov     [rbp+280h+var_2C4], r15d
0x18004dd91  mov     rax, [rcx]
0x18004dd94  mov     rax, [rax+50h]
0x18004dd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd9d  lea     r8, [rbp+280h+Src]
0x18004dda1  mov     rcx, rax; szProduct
0x18004dda4  lea     rdx, aLocalpackage_0; "LocalPackage"
0x18004ddab  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x18004ddb0  test    eax, eax
0x18004ddb2  jz      short loc_18004DDC1
0x18004ddb4  mov     rdx, [rbp+280h+Src]
0x18004ddb8  lea     rcx, [rbp+280h+var_300]
0x18004ddbc  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x18004ddc1  lea     rcx, [rbp+280h+Src]
0x18004ddc5  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x18004ddca  jmp     loc_18004DF0E
0x18004ddcf  mov     bl, sil
0x18004ddd2  cmp     [rdi], r15d
0x18004ddd5  jnz     loc_18004DF0E
0x18004dddb  mov     ecx, 104h
0x18004dde0  lea     rax, [rbp+280h+var_250]
0x18004dde4  mov     [rbp+280h+var_258], ecx
0x18004dde7  lea     rdx, [rbp+280h+hMem]
0x18004ddeb  mov     [rbp+280h+var_254], ecx
0x18004ddee  xor     r8d, r8d
0x18004ddf1  mov     rcx, [rdi+8]; unsigned __int16 *
0x18004ddf5  mov     [rbp+280h+hMem], rax
0x18004ddf9  call    ?ExpandPath@@YA?AW4Bool@@PEBGAEAV?$CAPITempBufferRef@G@@0@Z; ExpandPath(ushort const *,CAPITempBufferRef<ushort> &,ushort const *)
0x18004ddfe  test    eax, eax
0x18004de00  jz      loc_18004DEF5
0x18004de06  mov     rdx, [rbp+280h+hMem]
0x18004de0a  lea     rcx, [rbp+280h+var_300]
0x18004de0e  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x18004de13  mov     rcx, [rsp+380h+var_310]
0x18004de18  mov     rax, [rcx]
0x18004de1b  mov     rax, [rax+10h]
0x18004de1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de24  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004de2b  mov     [rsp+380h+var_310], rcx
0x18004de30  lea     rdx, aProductcode; "ProductCode"
0x18004de37  lea     rcx, [rbp+280h+var_2E0]; this
0x18004de3b  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18004de40  mov     rdx, [rbp+280h+var_300]; struct IMsiString *
0x18004de44  lea     rcx, [rsp+380h+var_310]
0x18004de49  mov     [rsp+380h+var_360], rcx; struct IMsiString **
0x18004de4e  lea     r8, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; struct IMsiString *
0x18004de55  xor     ecx, ecx; unsigned __int16 *
0x18004de57  mov     r9, [rax]; struct IMsiString *
0x18004de5a  call    ?GetPropertyFromDatabase@@YAPEAVIMsiRecord@@PEBGAEBVIMsiString@@11AEAPEBV2@@Z; GetPropertyFromDatabase(ushort const *,IMsiString const &,IMsiString const &,IMsiString const &,IMsiString const * &)
0x18004de5f  mov     rdx, rax
0x18004de62  lea     rcx, [rbp+280h+var_2F8]
0x18004de66  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18004de6b  mov     rcx, [rbp+280h+var_2E0]
0x18004de6f  mov     rax, [rcx]
0x18004de72  mov     rax, [rax+10h]
0x18004de76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de7b  cmp     [rbp+280h+var_2F8], rsi
0x18004de7f  jnz     short loc_18004DEDE
0x18004de81  mov     rcx, [rsp+380h+var_310]
0x18004de86  mov     rax, [rcx]
0x18004de89  mov     rax, [rax+38h]
0x18004de8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de92  test    eax, eax
0x18004de94  jz      short loc_18004DEDE
0x18004de96  mov     rcx, [rsp+380h+var_310]
0x18004de9b  xor     eax, eax
0x18004de9d  mov     [rbp+280h+var_2C0], ax
0x18004dea1  lea     rax, [rbp+280h+var_2C0]
0x18004dea5  mov     [rbp+280h+Src], rax
0x18004dea9  mov     [rbp+280h+var_2C8], r15d
0x18004dead  mov     [rbp+280h+var_2C4], r15d
0x18004deb1  mov     rax, [rcx]
0x18004deb4  mov     rax, [rax+50h]
0x18004deb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004debd  lea     r8, [rbp+280h+Src]
0x18004dec1  mov     rcx, rax; szProduct
0x18004dec4  lea     rdx, aLocalpackage_0; "LocalPackage"
0x18004decb  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x18004ded0  test    eax, eax
0x18004ded2  lea     rcx, [rbp+280h+Src]
0x18004ded6  setnz   bl
0x18004ded9  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x18004dede  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004dee5  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004deec  mov     rax, [rax+10h]
0x18004def0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004def5  cmp     [rbp+280h+var_258], 104h
0x18004defc  jle     short loc_18004DF0E
0x18004defe  mov     rcx, [rbp+280h+hMem]; hMem
0x18004df02  call    cs:__imp_GlobalFree
0x18004df09  nop     dword ptr [rax+rax+00h]
0x18004df0e  mov     rcx, [rbp+280h+var_300]
0x18004df12  mov     rax, [rcx]
0x18004df15  mov     rax, [rax+38h]
0x18004df19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df1e  test    eax, eax
0x18004df20  jz      loc_18004E213
0x18004df26  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004df2d  mov     rcx, r14
0x18004df30  mov     [rbp+280h+TokenHandle], rcx
0x18004df34  test    bl, bl
0x18004df36  jz      short loc_18004DFAA
0x18004df38  mov     rcx, [rsp+380h+var_310]
0x18004df3d  mov     rax, [rcx]
0x18004df40  mov     rax, [rax+38h]
0x18004df44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df49  test    eax, eax
0x18004df4b  jz      short loc_18004DFA6
0x18004df4d  mov     rcx, [rsp+380h+var_310]
0x18004df52  xor     eax, eax
0x18004df54  mov     [rbp+280h+var_2C0], ax
0x18004df58  lea     rax, [rbp+280h+var_2C0]
0x18004df5c  mov     [rbp+280h+Src], rax
0x18004df60  mov     [rbp+280h+var_2C8], r15d
0x18004df64  mov     [rbp+280h+var_2C4], r15d
0x18004df68  mov     rax, [rcx]
0x18004df6b  mov     rax, [rax+50h]
0x18004df6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df74  xor     r9d, r9d
0x18004df77  lea     r8, [rbp+280h+Src]
0x18004df7b  lea     rdx, aTransforms_1; "Transforms"
0x18004df82  mov     rcx, rax; szProduct
0x18004df85  call    ?GetExpandedProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@_N@Z; GetExpandedProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &,bool)
0x18004df8a  test    eax, eax
0x18004df8c  jz      short loc_18004DF9B
0x18004df8e  mov     rdx, [rbp+280h+Src]
0x18004df92  lea     rcx, [rbp+280h+TokenHandle]
0x18004df96  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x18004df9b  lea     rcx, [rbp+280h+Src]
0x18004df9f  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x18004dfa4  jmp     short loc_18004DFF9
0x18004dfa6  mov     rcx, [rbp+280h+TokenHandle]
0x18004dfaa  mov     rax, [rcx]
0x18004dfad  mov     rax, [rax+10h]
0x18004dfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfb6  mov     rcx, [rdi+18h]
0x18004dfba  lea     r8, [rbp+280h+TokenHandle]
0x18004dfbe  mov     byte ptr [rsp+380h+var_320], sil
0x18004dfc3  xor     r9d, r9d
0x18004dfc6  mov     [rsp+380h+var_328], rsi
0x18004dfcb  xor     edx, edx
0x18004dfcd  mov     [rsp+380h+var_330], rsi
0x18004dfd2  mov     dword ptr [rsp+380h+var_338], r15d
0x18004dfd7  mov     [rsp+380h+var_340], rsi
0x18004dfdc  mov     [rsp+380h+var_348], rsi
0x18004dfe1  mov     [rsp+380h+var_350], rsi
0x18004dfe6  mov     [rsp+380h+var_358], rsi
0x18004dfeb  mov     [rsp+380h+var_360], rsi
0x18004dff0  mov     [rbp+280h+TokenHandle], r14
0x18004dff4  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18004dff9  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004e000  mov     rcx, r14
0x18004e003  mov     rax, [rax+10h]
0x18004e007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e00c  lea     rdx, aCurrentdirecto_0; "CURRENTDIRECTORY"
0x18004e013  mov     [rbp+280h+var_2E0], r14
0x18004e017  lea     rcx, [rbp+280h+Thread]; this
0x18004e01b  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18004e020  mov     byte ptr [rsp+380h+var_320], sil
0x18004e025  xor     r9d, r9d
0x18004e028  mov     [rsp+380h+var_328], rsi
0x18004e02d  xor     r8d, r8d
0x18004e030  mov     [rsp+380h+var_330], rsi
0x18004e035  xor     edx, edx
0x18004e037  mov     rcx, [rax]
0x18004e03a  lea     rax, [rbp+280h+var_2E0]
0x18004e03e  mov     dword ptr [rsp+380h+var_338], r15d
0x18004e043  mov     [rsp+380h+var_340], rax
0x18004e048  mov     [rsp+380h+var_348], rcx
0x18004e04d  mov     rcx, [rdi+18h]
0x18004e051  mov     [rsp+380h+var_350], rsi
0x18004e056  mov     [rsp+380h+var_358], rsi
0x18004e05b  mov     [rsp+380h+var_360], rsi
0x18004e060  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18004e065  mov     rcx, [rbp+280h+Thread]
0x18004e069  mov     rax, [rcx]
0x18004e06c  mov     rax, [rax+10h]
0x18004e070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e075  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18004e07c  mov     rcx, r14
0x18004e07f  mov     [rbp+280h+var_2E8], r14
0x18004e083  mov     rax, [rax+10h]
0x18004e087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e08c  lea     rdx, aMsilogging; "MsiLogging"
0x18004e093  mov     [rbp+280h+var_2E8], r14
0x18004e097  lea     rcx, [rbp+280h+Thread]; this
0x18004e09b  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18004e0a0  mov     r14, [rbp+280h+var_2E0]
0x18004e0a4  mov     rdi, [rbp+280h+TokenHandle]
0x18004e0a8  mov     rcx, r14
0x18004e0ab  mov     rsi, [rbp+280h+var_300]
0x18004e0af  mov     rbx, [rax]
0x18004e0b2  mov     rax, [r14]
0x18004e0b5  mov     rax, [rax+50h]
0x18004e0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0be  lea     rcx, [rbp+280h+var_2E8]
0x18004e0c2  mov     r9, rbx; struct IMsiString *
0x18004e0c5  mov     [rsp+380h+var_360], rcx; struct IMsiString **
0x18004e0ca  mov     r8, rdi; struct IMsiString *
0x18004e0cd  mov     rcx, rax; unsigned __int16 *
0x18004e0d0  mov     rdx, rsi; struct IMsiString *
0x18004e0d3  call    ?GetPropertyFromDatabase@@YAPEAVIMsiRecord@@PEBGAEBVIMsiString@@11AEAPEBV2@@Z; GetPropertyFromDatabase(ushort const *,IMsiString const &,IMsiString const &,IMsiString const &,IMsiString const * &)
0x18004e0d8  mov     rdx, rax
0x18004e0db  lea     rcx, [rbp+280h+var_2F8]
0x18004e0df  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18004e0e4  mov     rcx, [rbp+280h+Thread]
0x18004e0e8  mov     rax, [rcx]
0x18004e0eb  mov     rax, [rax+10h]
0x18004e0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0f4  xor     esi, esi
0x18004e0f6  cmp     [rbp+280h+var_2F8], rsi
0x18004e0fa  jnz     loc_18004E1DF
0x18004e100  mov     rcx, [rbp+280h+var_2E8]
0x18004e104  mov     rax, [rcx]
0x18004e107  mov     rax, [rax+38h]
0x18004e10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e110  test    eax, eax
0x18004e112  jz      loc_18004E1DF
0x18004e118  mov     rcx, [rbp+280h+var_2E8]
0x18004e11c  mov     rax, [rcx]
0x18004e11f  mov     rax, [rax+38h]
0x18004e123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e128  inc     eax
0x18004e12a  cmp     [rbp+280h+var_2A8], eax
0x18004e12d  jge     loc_18004E1BF
0x18004e133  mov     rcx, [rbp+280h+var_2E8]
0x18004e137  mov     rax, [rcx]
0x18004e13a  mov     rax, [rax+38h]
0x18004e13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e143  lea     rcx, [rbp+280h+var_2B0]
0x18004e147  lea     edx, [rax+1]
0x18004e14a  call    ?SetSize@?$CAPITempBuffer@G$0BJ@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,25>::SetSize(int,bool)
0x18004e14f  test    al, al
0x18004e151  jnz     short loc_18004E1BF
0x18004e153  mov     rcx, [rbp+280h+var_2E8]
0x18004e157  mov     rax, [rcx]
0x18004e15a  mov     rax, [rax+10h]
0x18004e15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e163  mov     rax, [r14]
0x18004e166  mov     rcx, r14
0x18004e169  mov     rax, [rax+10h]
0x18004e16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e172  mov     rcx, [rbp+280h+TokenHandle]
0x18004e176  mov     rax, [rcx]
0x18004e179  mov     rax, [rax+10h]
0x18004e17d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
