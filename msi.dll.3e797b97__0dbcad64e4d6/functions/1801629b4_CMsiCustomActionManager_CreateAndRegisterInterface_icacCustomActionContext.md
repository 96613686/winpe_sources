# CMsiCustomActionManager::CreateAndRegisterInterface(icacCustomActionContext)

- ea: `0x1801629b4`
- end: `0x180163250`
- name: `?CreateAndRegisterInterface@CMsiCustomActionManager@@AEAAKW4icacCustomActionContext@@@Z`
- size: `2204`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18020a690`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x18001386c`
- `0x180013d64`
- `0x180014f18`
- `0x180027634`
- `0x180068150`
- `0x1800b9c08`
- `0x18011a2f8`
- `0x180148a10`
- `0x180148a30`
- `0x1801629b4`
- `0x1801c802c`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180162c66`
- `ADVAPI32!SetThreadToken` at `0x180162d0d`
- `ADVAPI32!SetThreadToken` at `0x180162e8c`
- `ADVAPI32!SetThreadToken` at `0x180163071`
- `ADVAPI32!SetThreadToken` at `0x180162c66`
- `ADVAPI32!SetThreadToken` at `0x180162d0d`
- `ADVAPI32!SetThreadToken` at `0x180162e8c`
- `ADVAPI32!SetThreadToken` at `0x180163071`
- `ADVAPI32!DuplicateTokenEx` at `0x180162e36`
- `ADVAPI32!DuplicateTokenEx` at `0x180162e36`
- `ADVAPI32!OpenThreadToken` at `0x180162dc6`
- `ADVAPI32!OpenThreadToken` at `0x180162dc6`
- `ADVAPI32!OpenProcessToken` at `0x180162e03`
- `ADVAPI32!OpenProcessToken` at `0x180162e03`
- `KERNEL32!CloseHandle` at `0x180162aa8`
- `KERNEL32!CloseHandle` at `0x180162e64`
- `KERNEL32!CloseHandle` at `0x180162ea0`
- `KERNEL32!CloseHandle` at `0x180162eb5`
- `KERNEL32!CloseHandle` at `0x180162ed1`
- `KERNEL32!CloseHandle` at `0x180163085`
- `KERNEL32!CloseHandle` at `0x180163094`
- `KERNEL32!CloseHandle` at `0x1801630e9`
- `KERNEL32!CloseHandle` at `0x1801631fd`
- `KERNEL32!CloseHandle` at `0x180162aa8`
- `KERNEL32!CloseHandle` at `0x180162e64`
- `KERNEL32!CloseHandle` at `0x180162ea0`
- `KERNEL32!CloseHandle` at `0x180162eb5`
- `KERNEL32!CloseHandle` at `0x180162ed1`
- `KERNEL32!CloseHandle` at `0x180163085`
- `KERNEL32!CloseHandle` at `0x180163094`
- `KERNEL32!CloseHandle` at `0x1801630e9`
- `KERNEL32!CloseHandle` at `0x1801631fd`
- `KERNEL32!GetLastError` at `0x180162ddb`
- `KERNEL32!GetLastError` at `0x180162ddb`
- `KERNEL32!GetCurrentThread` at `0x180162dae`
- `KERNEL32!GetCurrentThread` at `0x180162dae`
- `KERNEL32!GetCurrentProcess` at `0x180162dee`
- `KERNEL32!GetCurrentProcess` at `0x180162dee`
- `KERNEL32!GlobalFree` at `0x180162a69`
- `KERNEL32!GlobalFree` at `0x180162a97`
- `KERNEL32!GlobalFree` at `0x180162b59`
- `KERNEL32!GlobalFree` at `0x180162b73`
- `KERNEL32!GlobalFree` at `0x180162a69`
- `KERNEL32!GlobalFree` at `0x180162a97`
- `KERNEL32!GlobalFree` at `0x180162b59`
- `KERNEL32!GlobalFree` at `0x180162b73`
- `KERNEL32!GetCurrentProcessId` at `0x180162a11`
- `KERNEL32!GetCurrentProcessId` at `0x180162bcc`
- `KERNEL32!GetCurrentProcessId` at `0x180162c92`
- `KERNEL32!GetCurrentProcessId` at `0x180162f6a`
- `KERNEL32!GetCurrentProcessId` at `0x180163159`
- `KERNEL32!GetCurrentProcessId` at `0x180162a11`
- `KERNEL32!GetCurrentProcessId` at `0x180162bcc`
- `KERNEL32!GetCurrentProcessId` at `0x180162c92`
- `KERNEL32!GetCurrentProcessId` at `0x180162f6a`
- `KERNEL32!GetCurrentProcessId` at `0x180163159`
- `KERNEL32!ExitProcess` at `0x180162d30`
- `KERNEL32!ExitProcess` at `0x1801630ce`
- `KERNEL32!ExitProcess` at `0x180162d30`
- `KERNEL32!ExitProcess` at `0x1801630ce`
- `KERNEL32!OpenProcess` at `0x180162a27`
- `KERNEL32!OpenProcess` at `0x180162fe9`
- `KERNEL32!OpenProcess` at `0x180162a27`
- `KERNEL32!OpenProcess` at `0x180162fe9`

## string_xrefs

- `0x180162afb`: `MSI_LUA: No elevated token available`
- `0x180162f19`: `Connected to service for CA interface.`

## pseudocode

```c
__int64 __fastcall CMsiCustomActionManager::CreateAndRegisterInterface(__int64 a1, unsigned int a2)
{
  __int64 v2; // r14
  DWORD CurrentProcessId; // eax
  HANDLE v5; // rax
  bool v6; // dl
  void *AISToken; // rax
  bool v8; // dl
  struct IMsiConfigurationManager *ConfigurationManager; // rbx
  __int64 v10; // rax
  char v11; // bl
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(void *, _QWORD, _QWORD, __int64, _QWORD, _DWORD, __int128 *, int *, __int64, __int64, _BYTE, char, _QWORD); // rsi
  DWORD v14; // eax
  __int64 v15; // r15
  DWORD *v16; // r12
  struct IMsiServer *v17; // rax
  __int64 v18; // rax
  char v19; // bl
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(void *, _QWORD, _QWORD, __int64, _QWORD, _DWORD, __int128 *, int *, __int64, __int64, _BYTE, char, struct IMsiServer *); // rsi
  DWORD v22; // eax
  _WORD *EnvironmentStringsW; // rax
  _WORD *v24; // rbx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rdx
  struct IMsiServer *v30; // rdi
  unsigned __int16 v31; // bx
  __int64 v32; // rsi
  __int64 v33; // rax
  char v34; // di
  unsigned int (__fastcall *v35)(struct IMsiServer *, _QWORD, _QWORD, __int64, _WORD *, int, unsigned int, __int128 *, int *, __int64 *, DWORD *, _DWORD, unsigned __int16); // r14
  DWORD v36; // eax
  HANDLE v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rbx
  unsigned int (__fastcall *v41)(__int64, _QWORD, __int64); // rdi
  DWORD v42; // eax
  __int64 result; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  DWORD v46; // ecx
  __int64 v47; // rcx
  unsigned int v48; // [rsp+50h] [rbp-B0h]
  void *v49; // [rsp+58h] [rbp-A8h]
  char v50; // [rsp+70h] [rbp-90h]
  __int64 v51; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  int v53; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwProcessId; // [rsp+98h] [rbp-68h] BYREF
  struct IMsiServer *MsiServer; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v58; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v59; // [rsp+B8h] [rbp-48h]
  int v60; // [rsp+C0h] [rbp-40h]
  unsigned int v61; // [rsp+C4h] [rbp-3Ch]
  HGLOBAL hMem; // [rsp+D0h] [rbp-30h] BYREF
  int v63; // [rsp+D8h] [rbp-28h]
  int v64; // [rsp+DCh] [rbp-24h]
  char v65[80]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v66; // [rsp+130h] [rbp+30h] BYREF

  v2 = (int)a2;
  v61 = a2;
  v53 = 16;
  v51 = 0;
  if ( (a2 & 0xFFFFFFF6) == 0 )
  {
    CImpersonate::CImpersonate((CImpersonate *)&v57, 1);
    CurrentProcessId = GetCurrentProcessId();
    v5 = OpenProcess(0x100000u, 0, CurrentProcessId);
    if ( v5 )
    {
      CloseHandle(v5);
    }
    else
    {
      v63 = 72;
      hMem = v65;
      v64 = 72;
      if ( (unsigned int)GetCurrentUserSID(&hMem) || !SetInteractiveSynchronizeRightsForSID((unsigned __int8 *)hMem, v6) )
      {
        if ( v63 > 72 )
          GlobalFree(hMem);
        v63 = 72;
        hMem = v65;
        CImpersonate::~CImpersonate((CImpersonate *)&v57);
        return 0;
      }
      if ( v63 > 72 )
        GlobalFree(hMem);
    }
    CImpersonate::~CImpersonate((CImpersonate *)&v57);
  }
  if ( (unsigned int)(v2 - 6) > 1 )
    goto LABEL_22;
  v63 = 72;
  hMem = v65;
  AISToken = GetAISToken();
  if ( AISToken )
  {
    if ( GetUserSID(AISToken, v65) || !SetInteractiveSynchronizeRightsForSID((unsigned __int8 *)hMem, v8) )
    {
LABEL_18:
      if ( v63 > 72 )
        GlobalFree(hMem);
      return 0;
    }
    if ( v63 > 72 )
      GlobalFree(hMem);
LABEL_22:
    if ( g_scServerContext == 2 )
    {
      ConfigurationManager = CreateConfigurationManager();
      TokenHandle = ConfigurationManager;
      if ( (unsigned int)(v2 - 6) <= 1 )
      {
        v17 = (struct IMsiServer *)GetAISToken();
        MsiServer = v17;
        if ( !v17 )
        {
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&TokenHandle);
          return 0;
        }
        if ( !SetThreadToken(0, v17) )
          goto LABEL_29;
        v18 = *(_QWORD *)ConfigurationManager;
        v19 = *(_BYTE *)(a1 + 240);
        v20 = *(_QWORD *)(a1 + 200);
        v21 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64, _QWORD, _DWORD, __int128 *, int *, __int64, __int64, _BYTE, char, struct IMsiServer *))(v18 + 352);
        v22 = GetCurrentProcessId();
        v57 = v2;
        v15 = a1 + 16 * v2;
        v16 = (DWORD *)(v15 + 12);
        v51 = v21(TokenHandle, (unsigned int)v2, v22, v20, 0, 0, &v66, &v53, v15, v15 + 12, 0, v19, MsiServer);
        if ( !SetThreadToken(0, 0) )
LABEL_29:
          ExitProcess(0xFFFFFFFF);
      }
      else
      {
        CImpersonate::CImpersonate((CImpersonate *)&MsiServer, 1);
        v10 = *(_QWORD *)ConfigurationManager;
        v11 = *(_BYTE *)(a1 + 240);
        v12 = *(_QWORD *)(a1 + 200);
        v13 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64, _QWORD, _DWORD, __int128 *, int *, __int64, __int64, _BYTE, char, _QWORD))(v10 + 352);
        v14 = GetCurrentProcessId();
        v57 = v2;
        v15 = a1 + 16 * v2;
        v16 = (DWORD *)(v15 + 12);
        v51 = v13(TokenHandle, (unsigned int)v2, v14, v12, 0, 0, &v66, &v53, v15, v15 + 12, 0, v11, 0);
        CImpersonate::~CImpersonate((CImpersonate *)&MsiServer);
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&TokenHandle);
      goto LABEL_72;
    }
    v57 = v2;
    v15 = a1 + 16 * v2;
    *(_DWORD *)(v15 + 8) = 0;
    v16 = (DWORD *)(v15 + 12);
    *(_DWORD *)(v15 + 12) = 0;
    EnvironmentStringsW = (_WORD *)KERNEL32::GetEnvironmentStringsW();
    v59 = EnvironmentStringsW;
    v24 = EnvironmentStringsW;
    if ( EnvironmentStringsW )
    {
      if ( !*EnvironmentStringsW )
        goto LABEL_34;
      do
      {
        do
          ++v24;
        while ( *v24 );
LABEL_34:
        ++v24;
      }
      while ( *v24 );
    }
    v58 = 0;
    TokenHandle = (void *)-1LL;
    hObject = (HANDLE)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 2u, 0, &TokenHandle) )
    {
      v50 = 1;
    }
    else
    {
      v50 = 0;
      if ( GetLastError() == 1008 )
      {
        CurrentProcess = GetCurrentProcess();
        OpenProcessToken(CurrentProcess, 2u, &TokenHandle);
      }
    }
    v27 = TokenHandle;
    if ( TokenHandle != (void *)-1LL )
    {
      if ( DuplicateTokenEx(TokenHandle, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
      {
        v28 = (__int64)hObject;
      }
      else
      {
        v28 = -1;
        hObject = (HANDLE)-1LL;
      }
      if ( !EnableAndMapDisabledPrivileges((HANDLE)v28, &v58) )
      {
        CloseHandle(hObject);
        v27 = TokenHandle;
        v29 = -1;
        hObject = (HANDLE)-1LL;
        goto LABEL_47;
      }
      v27 = TokenHandle;
    }
    v29 = (__int64)hObject;
LABEL_47:
    if ( v29 != -1 )
    {
      if ( SetThreadToken(0, (HANDLE)v29) )
      {
        CloseHandle(hObject);
        hObject = (HANDLE)-1LL;
        MsiServer = CreateMsiServer();
        v30 = MsiServer;
        if ( MsiServer )
        {
          v60 = v24 - v59 + 1;
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              "Connected to service for CA interface.",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              v48,
              v49);
          v31 = g_w64BitCustomActionPlatform;
          dwProcessId = 0;
          v32 = *(_QWORD *)(a1 + 200);
          v53 = 16;
          v33 = *(_QWORD *)v30;
          v34 = *(_BYTE *)(a1 + 256);
          v35 = *(unsigned int (__fastcall **)(struct IMsiServer *, _QWORD, _QWORD, __int64, _WORD *, int, unsigned int, __int128 *, int *, __int64 *, DWORD *, _DWORD, unsigned __int16))(v33 + 120);
          v36 = GetCurrentProcessId();
          LOBYTE(v49) = v34;
          if ( !v35(MsiServer, v61, v36, v32, v59, v60, v58, &v66, &v53, &v51, &dwProcessId, (_DWORD)v49, v31) && v51 )
          {
            v37 = OpenProcess(0x100000u, 0, dwProcessId);
            *(_QWORD *)v15 = v37;
            if ( v37 && (unsigned int)((__int64 (__fastcall *)(__int64))OLE32::CoIsHandlerConnected)(v51) )
            {
              v38 = v51;
            }
            else
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              v38 = 0;
              v51 = 0;
            }
            if ( v53 != 16 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              v51 = 0;
            }
            *v16 = dwProcessId;
          }
        }
        ((void (__fastcall *)(_WORD *))KERNEL32::FreeEnvironmentStringsW)(v59);
        if ( !SetThreadToken(0, (HANDLE)((unsigned __int64)TokenHandle & -(__int64)(v50 != 0))) )
        {
          CloseHandle(TokenHandle);
          CloseHandle(*(HANDLE *)v15);
          v39 = v51;
          *(_QWORD *)v15 = 0;
          *v16 = 0;
          if ( v39 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            v51 = 0;
          }
          if ( g_scServerContext == 2 )
            ExitProcess(0xFFFFFFFF);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&MsiServer);
          return 0;
        }
        CloseHandle(TokenHandle);
        TokenHandle = (void *)-1LL;
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&MsiServer);
LABEL_72:
        if ( !v51
          || (*(unsigned int (__fastcall **)(_QWORD, __int64, GUID *, __int64))(**(_QWORD **)(a1 + 232) + 24LL))(
               *(_QWORD *)(a1 + 232),
               v51,
               &IID_IMsiCustomAction,
               v15 + 8) )
        {
          CloseHandle(*(HANDLE *)v15);
          v47 = v51;
          *(_QWORD *)v15 = 0;
          *v16 = 0;
          if ( v47 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        else
        {
          if ( !*(_BYTE *)(a1 + 256)
            || (v40 = *(_QWORD *)(a1 + 200),
                v41 = *(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v51 + 304LL),
                v42 = GetCurrentProcessId(),
                !v41(v51, v42, v40)) )
          {
            result = 1;
            v44 = *(_QWORD *)(a1 + 200);
            v45 = 3 * v57;
            v46 = *v16;
            *(_OWORD *)(v44 + 8 * v45 + 12) = v66;
            *(_DWORD *)(v44 + 8 * v45 + 8) = 0;
            *(_DWORD *)(v44 + 8 * v45 + 28) = v46;
            return result;
          }
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              L"EEUI - Could not join existing EEUI",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
        }
        return 0;
      }
      CloseHandle(hObject);
      v27 = TokenHandle;
    }
    if ( v27 != (void *)-1LL )
      CloseHandle(v27);
    ((void (__fastcall *)(_WORD *))KERNEL32::FreeEnvironmentStringsW)(v59);
    return 0;
  }
  if ( g_dmDiagnosticMode )
  {
    DebugString(
      10,
      0,
      0,
      L"MSI_LUA: No elevated token available",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
    goto LABEL_18;
  }
  return 0;
}

```

## disassembly

```asm
0x1801629b4  mov     [rsp-8+arg_10], rbx
0x1801629b9  push    rbp
0x1801629ba  push    rsi
0x1801629bb  push    rdi
0x1801629bc  push    r12
0x1801629be  push    r13
0x1801629c0  push    r14
0x1801629c2  push    r15
0x1801629c4  lea     rbp, [rsp-50h]
0x1801629c9  sub     rsp, 150h
0x1801629d0  mov     rax, cs:__security_cookie
0x1801629d7  xor     rax, rsp
0x1801629da  mov     [rbp+80h+var_40], rax
0x1801629de  xor     esi, esi
0x1801629e0  movsxd  r14, edx
0x1801629e3  mov     [rbp+80h+var_BC], r14d
0x1801629e7  mov     r13, rcx
0x1801629ea  mov     [rbp+80h+var_F8], 10h
0x1801629f1  mov     [rsp+180h+var_108], rsi
0x1801629f6  lea     ebx, [rsi+48h]
0x1801629f9  test    r14d, 0FFFFFFF6h
0x180162a00  jnz     loc_180162ABD
0x180162a06  mov     dl, 1; bool
0x180162a08  lea     rcx, [rbp+80h+var_D8]; this
0x180162a0c  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x180162a11  call    cs:__imp_GetCurrentProcessId
0x180162a18  nop     dword ptr [rax+rax+00h]
0x180162a1d  xor     edx, edx; bInheritHandle
0x180162a1f  mov     ecx, 100000h; dwDesiredAccess
0x180162a24  mov     r8d, eax; dwProcessId
0x180162a27  call    cs:__imp_OpenProcess
0x180162a2e  nop     dword ptr [rax+rax+00h]
0x180162a33  test    rax, rax
0x180162a36  jnz     short loc_180162AA5
0x180162a38  lea     rax, [rbp+80h+var_A0]
0x180162a3c  mov     [rbp+80h+var_A8], ebx
0x180162a3f  lea     rcx, [rbp+80h+hMem]
0x180162a43  mov     [rbp+80h+hMem], rax
0x180162a47  mov     [rbp+80h+var_A4], ebx
0x180162a4a  call    ?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z; GetCurrentUserSID(CAPITempBufferRef<uchar> &)
0x180162a4f  test    eax, eax
0x180162a51  jnz     short loc_180162A60
0x180162a53  mov     rcx, [rbp+80h+hMem]; unsigned __int8 *
0x180162a57  call    ?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z; SetInteractiveSynchronizeRightsForSID(uchar *,bool)
0x180162a5c  test    al, al
0x180162a5e  jnz     short loc_180162A8E
0x180162a60  cmp     [rbp+80h+var_A8], ebx
0x180162a63  jle     short loc_180162A75
0x180162a65  mov     rcx, [rbp+80h+hMem]; hMem
0x180162a69  call    cs:__imp_GlobalFree
0x180162a70  nop     dword ptr [rax+rax+00h]
0x180162a75  lea     rax, [rbp+80h+var_A0]
0x180162a79  mov     [rbp+80h+var_A8], ebx
0x180162a7c  lea     rcx, [rbp+80h+var_D8]; this
0x180162a80  mov     [rbp+80h+hMem], rax
0x180162a84  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180162a89  jmp     loc_180163226
0x180162a8e  cmp     [rbp+80h+var_A8], ebx
0x180162a91  jle     short loc_180162AB4
0x180162a93  mov     rcx, [rbp+80h+hMem]; hMem
0x180162a97  call    cs:__imp_GlobalFree
0x180162a9e  nop     dword ptr [rax+rax+00h]
0x180162aa3  jmp     short loc_180162AB4
0x180162aa5  mov     rcx, rax; hObject
0x180162aa8  call    cs:__imp_CloseHandle
0x180162aaf  nop     dword ptr [rax+rax+00h]
0x180162ab4  lea     rcx, [rbp+80h+var_D8]; this
0x180162ab8  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180162abd  lea     eax, [r14-6]
0x180162ac1  cmp     eax, 1
0x180162ac4  ja      loc_180162B7F
0x180162aca  lea     rax, [rbp+80h+var_A0]
0x180162ace  mov     [rbp+80h+var_A8], ebx
0x180162ad1  mov     [rbp+80h+hMem], rax
0x180162ad5  call    ?GetAISToken@@YAPEAXXZ; GetAISToken(void)
0x180162ada  test    rax, rax
0x180162add  jnz     short loc_180162B2F
0x180162adf  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x180162ae5  jz      loc_180163226
0x180162aeb  mov     [rsp+180h+var_128], rsi; void *
0x180162af0  lea     rax, aNull; "(NULL)"
0x180162af7  mov     [rsp+180h+var_130], esi; unsigned int
0x180162afb  lea     r9, aMsiLuaNoElevat; "MSI_LUA: No elevated token available"
0x180162b02  mov     [rsp+180h+var_138], rax; unsigned __int16 *
0x180162b07  xor     edx, edx; unsigned __int16
0x180162b09  mov     [rsp+180h+var_140], rax; unsigned __int16 *
0x180162b0e  xor     r8d, r8d; int
0x180162b11  mov     [rsp+180h+var_148], rax; unsigned __int16 *
0x180162b16  mov     [rsp+180h+var_150], rax; unsigned __int16 *
0x180162b1b  mov     [rsp+180h+phNewToken], rax; unsigned __int16 *
0x180162b20  lea     ecx, [rdx+0Ah]; int
0x180162b23  mov     qword ptr [rsp+180h+TokenType], rax; unsigned __int16 *
0x180162b28  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180162b2d  jmp     short loc_180162B4C
0x180162b2f  lea     rdx, [rbp+80h+var_A0]; char *
0x180162b33  mov     rcx, rax; void *
0x180162b36  call    ?GetUserSID@@YAKPEAXQEAD@Z; GetUserSID(void *,char * const)
0x180162b3b  test    eax, eax
0x180162b3d  jnz     short loc_180162B4C
0x180162b3f  mov     rcx, [rbp+80h+hMem]; unsigned __int8 *
0x180162b43  call    ?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z; SetInteractiveSynchronizeRightsForSID(uchar *,bool)
0x180162b48  test    al, al
0x180162b4a  jnz     short loc_180162B6A
0x180162b4c  cmp     [rbp+80h+var_A8], ebx
0x180162b4f  jle     loc_180163226
0x180162b55  mov     rcx, [rbp+80h+hMem]; hMem
0x180162b59  call    cs:__imp_GlobalFree
0x180162b60  nop     dword ptr [rax+rax+00h]
0x180162b65  jmp     loc_180163226
0x180162b6a  cmp     [rbp+80h+var_A8], ebx
0x180162b6d  jle     short loc_180162B7F
0x180162b6f  mov     rcx, [rbp+80h+hMem]; hMem
0x180162b73  call    cs:__imp_GlobalFree
0x180162b7a  nop     dword ptr [rax+rax+00h]
0x180162b7f  mov     edi, 2
0x180162b84  cmp     cs:?g_scServerContext@@3W4scEnum@@A, edi; scEnum g_scServerContext
0x180162b8a  jnz     loc_180162D4B
0x180162b90  call    ?CreateConfigurationManager@@YAPEAVIMsiConfigurationManager@@XZ; CreateConfigurationManager(void)
0x180162b95  mov     rbx, rax
0x180162b98  mov     [rbp+80h+TokenHandle], rax
0x180162b9c  lea     eax, [r14-6]
0x180162ba0  cmp     eax, 1
0x180162ba3  jbe     loc_180162C4F
0x180162ba9  mov     dl, 1; bool
0x180162bab  lea     rcx, [rbp+80h+var_E0]; this
0x180162baf  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x180162bb4  mov     rax, [rbx]
0x180162bb7  mov     bl, [r13+0F0h]
0x180162bbe  mov     rdi, [r13+0C8h]
0x180162bc5  mov     rsi, [rax+160h]
0x180162bcc  call    cs:__imp_GetCurrentProcessId
0x180162bd3  nop     dword ptr [rax+rax+00h]
0x180162bd8  xor     ecx, ecx
0x180162bda  mov     r9, rdi
0x180162bdd  mov     [rsp+180h+var_120], rcx
0x180162be2  mov     r8d, eax
0x180162be5  mov     byte ptr [rsp+180h+var_128], bl
0x180162be9  mov     rax, r14
0x180162bec  mov     byte ptr [rsp+180h+var_130], cl
0x180162bf0  mov     edx, r14d
0x180162bf3  mov     [rbp+80h+var_D8], rax
0x180162bf7  add     rax, rax
0x180162bfa  lea     r15, ds:0[rax*8]
0x180162c02  add     r15, r13
0x180162c05  lea     rax, [rbp+80h+var_F8]
0x180162c09  lea     r12, [r15+0Ch]
0x180162c0d  mov     [rsp+180h+var_138], r12
0x180162c12  mov     [rsp+180h+var_140], r15
0x180162c17  mov     [rsp+180h+var_148], rax
0x180162c1c  lea     rax, [rbp+80h+var_50]
0x180162c20  mov     [rsp+180h+var_150], rax
0x180162c25  mov     rax, rsi
0x180162c28  mov     dword ptr [rsp+180h+phNewToken], ecx
0x180162c2c  mov     qword ptr [rsp+180h+TokenType], rcx
0x180162c31  mov     rcx, [rbp+80h+TokenHandle]
0x180162c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162c3a  lea     rcx, [rbp+80h+var_E0]; this
0x180162c3e  mov     [rsp+180h+var_108], rax
0x180162c43  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180162c48  xor     esi, esi
0x180162c4a  jmp     loc_180162D1F
0x180162c4f  call    ?GetAISToken@@YAPEAXXZ; GetAISToken(void)
0x180162c54  mov     [rbp+80h+var_E0], rax
0x180162c58  test    rax, rax
0x180162c5b  jz      loc_180162D3D
0x180162c61  mov     rdx, rax; Token
0x180162c64  xor     ecx, ecx; Thread
0x180162c66  call    cs:__imp_SetThreadToken
0x180162c6d  nop     dword ptr [rax+rax+00h]
0x180162c72  test    eax, eax
0x180162c74  jz      loc_180162D2D
0x180162c7a  mov     rax, [rbx]
0x180162c7d  mov     bl, [r13+0F0h]
0x180162c84  mov     rdi, [r13+0C8h]
0x180162c8b  mov     rsi, [rax+160h]
0x180162c92  call    cs:__imp_GetCurrentProcessId
0x180162c99  nop     dword ptr [rax+rax+00h]
0x180162c9e  xor     ecx, ecx
0x180162ca0  mov     r9, rdi
0x180162ca3  mov     r8d, eax
0x180162ca6  mov     edx, r14d
0x180162ca9  mov     rax, r14
0x180162cac  mov     [rbp+80h+var_D8], rax
0x180162cb0  add     rax, rax
0x180162cb3  lea     r15, ds:0[rax*8]
0x180162cbb  mov     rax, [rbp+80h+var_E0]
0x180162cbf  mov     [rsp+180h+var_120], rax
0x180162cc4  add     r15, r13
0x180162cc7  mov     byte ptr [rsp+180h+var_128], bl
0x180162ccb  lea     rax, [rbp+80h+var_F8]
0x180162ccf  mov     byte ptr [rsp+180h+var_130], cl
0x180162cd3  lea     r12, [r15+0Ch]
0x180162cd7  mov     [rsp+180h+var_138], r12
0x180162cdc  mov     [rsp+180h+var_140], r15
0x180162ce1  mov     [rsp+180h+var_148], rax
0x180162ce6  lea     rax, [rbp+80h+var_50]
0x180162cea  mov     [rsp+180h+var_150], rax
0x180162cef  mov     rax, rsi
0x180162cf2  mov     dword ptr [rsp+180h+phNewToken], ecx
0x180162cf6  mov     qword ptr [rsp+180h+TokenType], rcx
0x180162cfb  mov     rcx, [rbp+80h+TokenHandle]
0x180162cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162d04  xor     edx, edx; Token
0x180162d06  mov     [rsp+180h+var_108], rax
0x180162d0b  xor     ecx, ecx; Thread
0x180162d0d  call    cs:__imp_SetThreadToken
0x180162d14  nop     dword ptr [rax+rax+00h]
0x180162d19  xor     esi, esi
0x180162d1b  test    eax, eax
0x180162d1d  jz      short loc_180162D2D
0x180162d1f  lea     rcx, [rbp+80h+TokenHandle]
0x180162d23  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180162d28  jmp     loc_180163102
0x180162d2d  or      ecx, 0FFFFFFFFh; uExitCode
0x180162d30  call    cs:__imp_ExitProcess
0x180162d3d  lea     rcx, [rbp+80h+TokenHandle]
0x180162d41  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180162d46  jmp     loc_180163226
0x180162d4b  mov     rax, r14
0x180162d4e  mov     [rbp+80h+var_D8], rax
0x180162d52  add     rax, rax
0x180162d55  lea     r15, ds:0[rax*8]
0x180162d5d  add     r15, r13
0x180162d60  mov     [r15+8], esi
0x180162d64  lea     r12, [r15+0Ch]
0x180162d68  mov     [r12], esi
0x180162d6c  mov     rax, cs:?GetEnvironmentStringsW@KERNEL32@@3P6APEAXXZEA; void * (*KERNEL32::GetEnvironmentStringsW)(void)
0x180162d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162d78  mov     [rbp+80h+var_C8], rax
0x180162d7c  mov     rbx, rax
0x180162d7f  test    rax, rax
0x180162d82  jz      short loc_180162D9F
0x180162d84  movzx   eax, word ptr [rax]
0x180162d87  test    ax, ax
0x180162d8a  jz      short loc_180162D94
0x180162d8c  add     rbx, rdi
0x180162d8f  cmp     [rbx], si
0x180162d92  jnz     short loc_180162D8C
0x180162d94  add     rbx, rdi
0x180162d97  movzx   eax, word ptr [rbx]
0x180162d9a  test    ax, ax
0x180162d9d  jnz     short loc_180162D8C
0x180162d9f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180162da3  mov     [rbp+80h+var_D0], esi
0x180162da6  mov     [rbp+80h+TokenHandle], r14
0x180162daa  mov     [rbp+80h+hObject], r14
0x180162dae  call    cs:__imp_GetCurrentThread
0x180162db5  nop     dword ptr [rax+rax+00h]
0x180162dba  lea     r9, [rbp+80h+TokenHandle]; TokenHandle
0x180162dbe  xor     r8d, r8d; OpenAsSelf
0x180162dc1  mov     rcx, rax; ThreadHandle
0x180162dc4  mov     edx, edi; DesiredAccess
0x180162dc6  call    cs:__imp_OpenThreadToken
0x180162dcd  nop     dword ptr [rax+rax+00h]
0x180162dd2  test    eax, eax
0x180162dd4  jnz     short loc_180162E11
0x180162dd6  mov     [rsp+180h+var_110], sil
0x180162ddb  call    cs:__imp_GetLastError
0x180162de2  nop     dword ptr [rax+rax+00h]
0x180162de7  cmp     eax, 3F0h
0x180162dec  jnz     short loc_180162E16
0x180162dee  call    cs:__imp_GetCurrentProcess
0x180162df5  nop     dword ptr [rax+rax+00h]
0x180162dfa  lea     r8, [rbp+80h+TokenHandle]; TokenHandle
0x180162dfe  mov     edx, edi; DesiredAccess
0x180162e00  mov     rcx, rax; ProcessHandle
0x180162e03  call    cs:__imp_OpenProcessToken
0x180162e0a  nop     dword ptr [rax+rax+00h]
0x180162e0f  jmp     short loc_180162E16
0x180162e11  mov     [rsp+180h+var_110], 1
0x180162e16  mov     rcx, [rbp+80h+TokenHandle]; hExistingToken
0x180162e1a  cmp     rcx, r14
0x180162e1d  jz      short loc_180162E81
0x180162e1f  xor     r8d, r8d; lpTokenAttributes
0x180162e22  lea     rax, [rbp+80h+hObject]
0x180162e26  mov     [rsp+180h+phNewToken], rax; phNewToken
0x180162e2b  mov     r9d, edi; ImpersonationLevel
0x180162e2e  mov     [rsp+180h+TokenType], edi; TokenType
0x180162e32  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180162e36  call    cs:__imp_DuplicateTokenEx
0x180162e3d  nop     dword ptr [rax+rax+00h]
0x180162e42  test    eax, eax
0x180162e44  jnz     short loc_180162E4F
0x180162e46  mov     rcx, r14
0x180162e49  mov     [rbp+80h+hObject], rcx
0x180162e4d  jmp     short loc_180162E53
0x180162e4f  mov     rcx, [rbp+80h+hObject]; TokenHandle
0x180162e53  lea     rdx, [rbp+80h+var_D0]; unsigned int *
0x180162e57  call    ?EnableAndMapDisabledPrivileges@@YA_NPEAXAEAK@Z; EnableAndMapDisabledPrivileges(void *,ulong &)
0x180162e5c  test    al, al
0x180162e5e  jnz     short loc_180162E7D
0x180162e60  mov     rcx, [rbp+80h+hObject]; hObject
0x180162e64  call    cs:__imp_CloseHandle
0x180162e6b  nop     dword ptr [rax+rax+00h]
0x180162e70  mov     rcx, [rbp+80h+TokenHandle]
0x180162e74  mov     rdx, r14
0x180162e77  mov     [rbp+80h+hObject], rdx
0x180162e7b  jmp     short loc_180162E85
0x180162e7d  mov     rcx, [rbp+80h+TokenHandle]
0x180162e81  mov     rdx, [rbp+80h+hObject]; Token
  ... truncated ...
```
