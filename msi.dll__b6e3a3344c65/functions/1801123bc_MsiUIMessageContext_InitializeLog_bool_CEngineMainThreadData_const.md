# MsiUIMessageContext::InitializeLog(bool,CEngineMainThreadData const *)

- ea: `0x1801123bc`
- end: `0x180112f1b`
- name: `?InitializeLog@MsiUIMessageContext@@AEAA_N_NPEBUCEngineMainThreadData@@@Z`
- size: `2911`
- prototype: `bool __fastcall(MsiUIMessageContext *__hidden this, bool, const struct CEngineMainThreadData *)`
- caller_count: `2`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009bc00`
- `0x180111d80`

## callees

- `0x18001de18`
- `0x18001e9f8`
- `0x180022120`
- `0x180025560`
- `0x1800255e0`
- `0x180035a8c`
- `0x180064a78`
- `0x180064b4c`
- `0x180064f18`
- `0x180066074`
- `0x180076e28`
- `0x180079dd0`
- `0x18008f3e8`
- `0x180090e50`
- `0x180098b50`
- `0x180098bd8`
- `0x18009dadc`
- `0x1800a5fc4`
- `0x1800b8034`
- `0x1800cb7a0`
- `0x1800da080`
- `0x1800e80a4`
- `0x1801123bc`
- `0x180146548`
- `0x18014a6fc`
- `0x180154dcc`
- `0x1801665f8`
- `0x180166ff0`
- `0x1801c0700`
- `0x1801c68f0`
- `0x1801cf9a8`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180112ce0`
- `msvcrt!_wcsicmp` at `0x180112ce0`
- `msvcrt!wcsrchr` at `0x180112ccb`
- `msvcrt!wcsrchr` at `0x180112ccb`
- `ADVAPI32!SetThreadToken` at `0x180112b29`
- `ADVAPI32!SetThreadToken` at `0x180112b9a`
- `ADVAPI32!SetThreadToken` at `0x180112b29`
- `ADVAPI32!SetThreadToken` at `0x180112b9a`
- `ADVAPI32!OpenThreadToken` at `0x180112b17`
- `ADVAPI32!OpenThreadToken` at `0x180112b17`
- `KERNEL32!GetModuleFileNameW` at `0x180112e0b`
- `KERNEL32!GetModuleFileNameW` at `0x180112e0b`
- `KERNEL32!GetCurrentThread` at `0x180112af6`
- `KERNEL32!GetCurrentThread` at `0x180112af6`
- `KERNEL32!GlobalFree` at `0x180112612`
- `KERNEL32!GlobalFree` at `0x1801129bb`
- `KERNEL32!GlobalFree` at `0x180112cb9`
- `KERNEL32!GlobalFree` at `0x180112d32`
- `KERNEL32!GlobalFree` at `0x180112612`
- `KERNEL32!GlobalFree` at `0x1801129bb`
- `KERNEL32!GlobalFree` at `0x180112cb9`
- `KERNEL32!GlobalFree` at `0x180112d32`
- `KERNEL32!lstrcmpiW` at `0x180112c5d`
- `KERNEL32!lstrcmpiW` at `0x180112c5d`

## string_xrefs

- `0x180112716`: `CURRENTDIRECTORY`
- `0x180112796`: `MsiLogging`

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
  char v52; // di
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
        (unsigned int)(dword_180305F08 - 1));
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
        || (int)StringCchCopyW((unsigned __int16 *)g_rgchLogFile, dword_180305F08, (const unsigned __int16 *)hMem) < 0 )
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
      && (int)StringCchCatW((unsigned __int16 *)g_rgchLogFile, dword_180305F08 - 1, L".LOG") < 0 )
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
0x1801123bc  mov     [rsp-8+arg_8], rbx
0x1801123c1  push    rbp
0x1801123c2  push    rsi
0x1801123c3  push    rdi
0x1801123c4  push    r12
0x1801123c6  push    r13
0x1801123c8  push    r14
0x1801123ca  push    r15
0x1801123cc  lea     rbp, [rsp-250h]
0x1801123d4  sub     rsp, 350h
0x1801123db  mov     rax, cs:__security_cookie
0x1801123e2  xor     rax, rsp
0x1801123e5  mov     [rbp+280h+var_40], rax
0x1801123ec  xor     esi, esi
0x1801123ee  mov     [rsp+380h+var_308], dl
0x1801123f2  cmp     cs:hObject, rsi
0x1801123f9  mov     rdi, r8
0x1801123fc  mov     r14b, dl
0x1801123ff  mov     r13, rcx
0x180112402  lea     r15d, [rsi+1]
0x180112406  jnz     loc_180112EEE
0x18011240c  cmp     cs:?g_dwLogMode@@3KA, esi; ulong g_dwLogMode
0x180112412  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180112419  mov     r12b, sil
0x18011241c  jnz     loc_1801129C8
0x180112422  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x180112428  jnz     loc_1801129C8
0x18011242e  mov     [rbp+280h+var_2A8], 19h
0x180112435  lea     rbx, [rbp+280h+var_2A0]
0x180112439  mov     [rbp+280h+var_2B0], rbx
0x18011243d  mov     [rbp+280h+var_2A0], si
0x180112441  test    r8, r8
0x180112444  jz      loc_18011294B
0x18011244a  mov     edx, r15d
0x18011244d  lea     ecx, [rsi+19h]
0x180112450  call    ?GetIntegerPolicyValue@@YAIW4iePolicyIndex@@W4Bool@@PEAW42@@Z; GetIntegerPolicyValue(iePolicyIndex,Bool,Bool *)
0x180112455  test    eax, eax
0x180112457  jnz     loc_180112947
0x18011245d  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180112464  mov     [rbp+280h+var_2F8], rsi
0x180112468  mov     [rbp+280h+var_300], rax
0x18011246c  mov     [rsp+380h+var_310], rax
0x180112471  cmp     [rdi], esi
0x180112473  jnz     short loc_1801124DF
0x180112475  mov     rdx, [rdi+8]
0x180112479  lea     rcx, [rsp+380h+var_310]
0x18011247e  mov     bl, r15b
0x180112481  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x180112486  mov     rcx, [rsp+380h+var_310]
0x18011248b  xor     eax, eax
0x18011248d  mov     [rbp+280h+var_2C0], ax
0x180112491  lea     rax, [rbp+280h+var_2C0]
0x180112495  mov     [rbp+280h+Src], rax
0x180112499  mov     [rbp+280h+var_2C8], r15d
0x18011249d  mov     [rbp+280h+var_2C4], r15d
0x1801124a1  mov     rax, [rcx]
0x1801124a4  mov     rax, [rax+50h]
0x1801124a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801124ad  lea     r8, [rbp+280h+Src]
0x1801124b1  mov     rcx, rax; szProduct
0x1801124b4  lea     rdx, aLocalpackage_0; "LocalPackage"
0x1801124bb  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x1801124c0  test    eax, eax
0x1801124c2  jz      short loc_1801124D1
0x1801124c4  mov     rdx, [rbp+280h+Src]
0x1801124c8  lea     rcx, [rbp+280h+var_300]
0x1801124cc  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801124d1  lea     rcx, [rbp+280h+Src]
0x1801124d5  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801124da  jmp     loc_180112618
0x1801124df  mov     bl, sil
0x1801124e2  cmp     [rdi], r15d
0x1801124e5  jnz     loc_180112618
0x1801124eb  mov     ecx, 104h
0x1801124f0  lea     rax, [rbp+280h+var_250]
0x1801124f4  mov     [rbp+280h+var_258], ecx
0x1801124f7  lea     rdx, [rbp+280h+hMem]
0x1801124fb  mov     [rbp+280h+var_254], ecx
0x1801124fe  xor     r8d, r8d
0x180112501  mov     rcx, [rdi+8]; unsigned __int16 *
0x180112505  mov     [rbp+280h+hMem], rax
0x180112509  call    ?ExpandPath@@YA?AW4Bool@@PEBGAEAV?$CAPITempBufferRef@G@@0@Z; ExpandPath(ushort const *,CAPITempBufferRef<ushort> &,ushort const *)
0x18011250e  test    eax, eax
0x180112510  jz      loc_180112605
0x180112516  mov     rdx, [rbp+280h+hMem]
0x18011251a  lea     rcx, [rbp+280h+var_300]
0x18011251e  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x180112523  mov     rcx, [rsp+380h+var_310]
0x180112528  mov     rax, [rcx]
0x18011252b  mov     rax, [rax+10h]
0x18011252f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112534  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18011253b  mov     [rsp+380h+var_310], rcx
0x180112540  lea     rdx, aProductcode; "ProductCode"
0x180112547  lea     rcx, [rbp+280h+var_2E0]; this
0x18011254b  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x180112550  mov     rdx, [rbp+280h+var_300]; struct IMsiString *
0x180112554  lea     rcx, [rsp+380h+var_310]
0x180112559  mov     [rsp+380h+var_360], rcx; struct IMsiString **
0x18011255e  lea     r8, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; struct IMsiString *
0x180112565  xor     ecx, ecx; unsigned __int16 *
0x180112567  mov     r9, [rax]; struct IMsiString *
0x18011256a  call    ?GetPropertyFromDatabase@@YAPEAVIMsiRecord@@PEBGAEBVIMsiString@@11AEAPEBV2@@Z; GetPropertyFromDatabase(ushort const *,IMsiString const &,IMsiString const &,IMsiString const &,IMsiString const * &)
0x18011256f  mov     rdx, rax
0x180112572  lea     rcx, [rbp+280h+var_2F8]
0x180112576  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x18011257b  mov     rcx, [rbp+280h+var_2E0]
0x18011257f  mov     rax, [rcx]
0x180112582  mov     rax, [rax+10h]
0x180112586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011258b  cmp     [rbp+280h+var_2F8], rsi
0x18011258f  jnz     short loc_1801125EE
0x180112591  mov     rcx, [rsp+380h+var_310]
0x180112596  mov     rax, [rcx]
0x180112599  mov     rax, [rax+38h]
0x18011259d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801125a2  test    eax, eax
0x1801125a4  jz      short loc_1801125EE
0x1801125a6  mov     rcx, [rsp+380h+var_310]
0x1801125ab  xor     eax, eax
0x1801125ad  mov     [rbp+280h+var_2C0], ax
0x1801125b1  lea     rax, [rbp+280h+var_2C0]
0x1801125b5  mov     [rbp+280h+Src], rax
0x1801125b9  mov     [rbp+280h+var_2C8], r15d
0x1801125bd  mov     [rbp+280h+var_2C4], r15d
0x1801125c1  mov     rax, [rcx]
0x1801125c4  mov     rax, [rax+50h]
0x1801125c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801125cd  lea     r8, [rbp+280h+Src]
0x1801125d1  mov     rcx, rax; szProduct
0x1801125d4  lea     rdx, aLocalpackage_0; "LocalPackage"
0x1801125db  call    ?GetProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@@Z; GetProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &)
0x1801125e0  test    eax, eax
0x1801125e2  lea     rcx, [rbp+280h+Src]
0x1801125e6  setnz   bl
0x1801125e9  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801125ee  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801125f5  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801125fc  mov     rax, [rax+10h]
0x180112600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112605  cmp     [rbp+280h+var_258], 104h
0x18011260c  jle     short loc_180112618
0x18011260e  mov     rcx, [rbp+280h+hMem]; hMem
0x180112612  call    cs:__imp_GlobalFree
0x180112618  mov     rcx, [rbp+280h+var_300]
0x18011261c  mov     rax, [rcx]
0x18011261f  mov     rax, [rax+38h]
0x180112623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112628  test    eax, eax
0x18011262a  jz      loc_18011291D
0x180112630  lea     r14, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180112637  mov     rcx, r14
0x18011263a  mov     [rbp+280h+TokenHandle], rcx
0x18011263e  test    bl, bl
0x180112640  jz      short loc_1801126B4
0x180112642  mov     rcx, [rsp+380h+var_310]
0x180112647  mov     rax, [rcx]
0x18011264a  mov     rax, [rax+38h]
0x18011264e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112653  test    eax, eax
0x180112655  jz      short loc_1801126B0
0x180112657  mov     rcx, [rsp+380h+var_310]
0x18011265c  xor     eax, eax
0x18011265e  mov     [rbp+280h+var_2C0], ax
0x180112662  lea     rax, [rbp+280h+var_2C0]
0x180112666  mov     [rbp+280h+Src], rax
0x18011266a  mov     [rbp+280h+var_2C8], r15d
0x18011266e  mov     [rbp+280h+var_2C4], r15d
0x180112672  mov     rax, [rcx]
0x180112675  mov     rax, [rax+50h]
0x180112679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011267e  xor     r9d, r9d
0x180112681  lea     r8, [rbp+280h+Src]
0x180112685  lea     rdx, aTransforms_1; "Transforms"
0x18011268c  mov     rcx, rax; szPatch
0x18011268f  call    ?GetExpandedProductInfo@@YA?AW4Bool@@PEBG0AEAV?$CTempBufferRef@G@@_N@Z; GetExpandedProductInfo(ushort const *,ushort const *,CTempBufferRef<ushort> &,bool)
0x180112694  test    eax, eax
0x180112696  jz      short loc_1801126A5
0x180112698  mov     rdx, [rbp+280h+Src]
0x18011269c  lea     rcx, [rbp+280h+TokenHandle]
0x1801126a0  call    ??4MsiString@@QEAAAEAV0@PEBG@Z; MsiString::operator=(ushort const *)
0x1801126a5  lea     rcx, [rbp+280h+Src]
0x1801126a9  call    ??1?$CTempBuffer@G$00@@QEAA@XZ; CTempBuffer<ushort,1>::~CTempBuffer<ushort,1>(void)
0x1801126ae  jmp     short loc_180112703
0x1801126b0  mov     rcx, [rbp+280h+TokenHandle]
0x1801126b4  mov     rax, [rcx]
0x1801126b7  mov     rax, [rax+10h]
0x1801126bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801126c0  mov     rcx, [rdi+18h]
0x1801126c4  lea     r8, [rbp+280h+TokenHandle]
0x1801126c8  mov     byte ptr [rsp+380h+var_320], sil
0x1801126cd  xor     r9d, r9d
0x1801126d0  mov     [rsp+380h+var_328], rsi
0x1801126d5  xor     edx, edx
0x1801126d7  mov     [rsp+380h+var_330], rsi
0x1801126dc  mov     dword ptr [rsp+380h+var_338], r15d
0x1801126e1  mov     [rsp+380h+var_340], rsi
0x1801126e6  mov     [rsp+380h+var_348], rsi
0x1801126eb  mov     [rsp+380h+var_350], rsi
0x1801126f0  mov     [rsp+380h+var_358], rsi
0x1801126f5  mov     [rsp+380h+var_360], rsi
0x1801126fa  mov     [rbp+280h+TokenHandle], r14
0x1801126fe  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x180112703  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18011270a  mov     rcx, r14
0x18011270d  mov     rax, [rax+10h]
0x180112711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112716  lea     rdx, aCurrentdirecto_0; "CURRENTDIRECTORY"
0x18011271d  mov     [rbp+280h+var_2E0], r14
0x180112721  lea     rcx, [rbp+280h+Thread]; this
0x180112725  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x18011272a  mov     byte ptr [rsp+380h+var_320], sil
0x18011272f  xor     r9d, r9d
0x180112732  mov     [rsp+380h+var_328], rsi
0x180112737  xor     r8d, r8d
0x18011273a  mov     [rsp+380h+var_330], rsi
0x18011273f  xor     edx, edx
0x180112741  mov     rcx, [rax]
0x180112744  lea     rax, [rbp+280h+var_2E0]
0x180112748  mov     dword ptr [rsp+380h+var_338], r15d
0x18011274d  mov     [rsp+380h+var_340], rax
0x180112752  mov     [rsp+380h+var_348], rcx
0x180112757  mov     rcx, [rdi+18h]
0x18011275b  mov     [rsp+380h+var_350], rsi
0x180112760  mov     [rsp+380h+var_358], rsi
0x180112765  mov     [rsp+380h+var_360], rsi
0x18011276a  call    ?ProcessCommandLine@@YA?AW4Bool@@PEBGPEAPEBVIMsiString@@11111PEBV2@1W41@1PEAVIMsiEngine@@_N@Z; ProcessCommandLine(ushort const *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const * *,IMsiString const *,IMsiString const * *,Bool,IMsiString const * *,IMsiEngine *,bool)
0x18011276f  mov     rcx, [rbp+280h+Thread]
0x180112773  mov     rax, [rcx]
0x180112776  mov     rax, [rax+10h]
0x18011277a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011277f  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180112786  mov     rcx, r14
0x180112789  mov     [rbp+280h+var_2E8], r14
0x18011278d  mov     rax, [rax+10h]
0x180112791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112796  lea     rdx, aMsilogging; "MsiLogging"
0x18011279d  mov     [rbp+280h+var_2E8], r14
0x1801127a1  lea     rcx, [rbp+280h+Thread]; this
0x1801127a5  call    ??0MsiString@@QEAA@AEBG@Z; MsiString::MsiString(ushort const &)
0x1801127aa  mov     r14, [rbp+280h+var_2E0]
0x1801127ae  mov     rdi, [rbp+280h+TokenHandle]
0x1801127b2  mov     rcx, r14
0x1801127b5  mov     rsi, [rbp+280h+var_300]
0x1801127b9  mov     rbx, [rax]
0x1801127bc  mov     rax, [r14]
0x1801127bf  mov     rax, [rax+50h]
0x1801127c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801127c8  lea     rcx, [rbp+280h+var_2E8]
0x1801127cc  mov     r9, rbx; struct IMsiString *
0x1801127cf  mov     [rsp+380h+var_360], rcx; struct IMsiString **
0x1801127d4  mov     r8, rdi; struct IMsiString *
0x1801127d7  mov     rcx, rax; unsigned __int16 *
0x1801127da  mov     rdx, rsi; struct IMsiString *
0x1801127dd  call    ?GetPropertyFromDatabase@@YAPEAVIMsiRecord@@PEBGAEBVIMsiString@@11AEAPEBV2@@Z; GetPropertyFromDatabase(ushort const *,IMsiString const &,IMsiString const &,IMsiString const &,IMsiString const * &)
0x1801127e2  mov     rdx, rax
0x1801127e5  lea     rcx, [rbp+280h+var_2F8]
0x1801127e9  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1801127ee  mov     rcx, [rbp+280h+Thread]
0x1801127f2  mov     rax, [rcx]
0x1801127f5  mov     rax, [rax+10h]
0x1801127f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801127fe  xor     esi, esi
0x180112800  cmp     [rbp+280h+var_2F8], rsi
0x180112804  jnz     loc_1801128E9
0x18011280a  mov     rcx, [rbp+280h+var_2E8]
0x18011280e  mov     rax, [rcx]
0x180112811  mov     rax, [rax+38h]
0x180112815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011281a  test    eax, eax
0x18011281c  jz      loc_1801128E9
0x180112822  mov     rcx, [rbp+280h+var_2E8]
0x180112826  mov     rax, [rcx]
0x180112829  mov     rax, [rax+38h]
0x18011282d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112832  inc     eax
0x180112834  cmp     [rbp+280h+var_2A8], eax
0x180112837  jge     loc_1801128C9
0x18011283d  mov     rcx, [rbp+280h+var_2E8]
0x180112841  mov     rax, [rcx]
0x180112844  mov     rax, [rax+38h]
0x180112848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011284d  lea     rcx, [rbp+280h+var_2B0]
0x180112851  lea     edx, [rax+1]
0x180112854  call    ?SetSize@?$CAPITempBuffer@G$0BJ@@@QEAA_NH_N@Z; CAPITempBuffer<ushort,25>::SetSize(int,bool)
0x180112859  test    al, al
0x18011285b  jnz     short loc_1801128C9
0x18011285d  mov     rcx, [rbp+280h+var_2E8]
0x180112861  mov     rax, [rcx]
0x180112864  mov     rax, [rax+10h]
0x180112868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011286d  mov     rax, [r14]
0x180112870  mov     rcx, r14
0x180112873  mov     rax, [rax+10h]
0x180112877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011287c  mov     rcx, [rbp+280h+TokenHandle]
0x180112880  mov     rax, [rcx]
0x180112883  mov     rax, [rax+10h]
0x180112887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011288c  lea     rcx, [rbp+280h+var_2F8]
  ... truncated ...
```
