# CMsiCustomActionManager::CreateAndRegisterInterface(icacCustomActionContext)

- ea: `0x18015cd14`
- end: `0x18015d4ef`
- name: `?CreateAndRegisterInterface@CMsiCustomActionManager@@AEAAKW4icacCustomActionContext@@@Z`
- size: `2011`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180201420`

## callees

- `0x18000a150`
- `0x1800252a8`
- `0x180025a18`
- `0x180064b4c`
- `0x180064f18`
- `0x180066074`
- `0x1800687b8`
- `0x1800a9df0`
- `0x180110d98`
- `0x180143d44`
- `0x180143d60`
- `0x18015cd14`
- `0x1801bfbe0`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18015cf96`
- `ADVAPI32!SetThreadToken` at `0x18015d031`
- `ADVAPI32!SetThreadToken` at `0x18015d17a`
- `ADVAPI32!SetThreadToken` at `0x18015d33b`
- `ADVAPI32!SetThreadToken` at `0x18015cf96`
- `ADVAPI32!SetThreadToken` at `0x18015d031`
- `ADVAPI32!SetThreadToken` at `0x18015d17a`
- `ADVAPI32!SetThreadToken` at `0x18015d33b`
- `ADVAPI32!DuplicateTokenEx` at `0x18015d130`
- `ADVAPI32!DuplicateTokenEx` at `0x18015d130`
- `ADVAPI32!OpenThreadToken` at `0x18015d0d8`
- `ADVAPI32!OpenThreadToken` at `0x18015d0d8`
- `ADVAPI32!OpenProcessToken` at `0x18015d103`
- `ADVAPI32!OpenProcessToken` at `0x18015d103`
- `KERNEL32!CloseHandle` at `0x18015cdf0`
- `KERNEL32!CloseHandle` at `0x18015d158`
- `KERNEL32!CloseHandle` at `0x18015d188`
- `KERNEL32!CloseHandle` at `0x18015d197`
- `KERNEL32!CloseHandle` at `0x18015d1ad`
- `KERNEL32!CloseHandle` at `0x18015d349`
- `KERNEL32!CloseHandle` at `0x18015d352`
- `KERNEL32!CloseHandle` at `0x18015d39b`
- `KERNEL32!CloseHandle` at `0x18015d4a3`
- `KERNEL32!CloseHandle` at `0x18015cdf0`
- `KERNEL32!CloseHandle` at `0x18015d158`
- `KERNEL32!CloseHandle` at `0x18015d188`
- `KERNEL32!CloseHandle` at `0x18015d197`
- `KERNEL32!CloseHandle` at `0x18015d1ad`
- `KERNEL32!CloseHandle` at `0x18015d349`
- `KERNEL32!CloseHandle` at `0x18015d352`
- `KERNEL32!CloseHandle` at `0x18015d39b`
- `KERNEL32!CloseHandle` at `0x18015d4a3`
- `KERNEL32!GetLastError` at `0x18015d0e7`
- `KERNEL32!GetLastError` at `0x18015d0e7`
- `KERNEL32!GetCurrentThread` at `0x18015d0c6`
- `KERNEL32!GetCurrentThread` at `0x18015d0c6`
- `KERNEL32!GetCurrentProcess` at `0x18015d0f4`
- `KERNEL32!GetCurrentProcess` at `0x18015d0f4`
- `KERNEL32!GlobalFree` at `0x18015cdbd`
- `KERNEL32!GlobalFree` at `0x18015cde5`
- `KERNEL32!GlobalFree` at `0x18015ce9b`
- `KERNEL32!GlobalFree` at `0x18015ceaf`
- `KERNEL32!GlobalFree` at `0x18015cdbd`
- `KERNEL32!GlobalFree` at `0x18015cde5`
- `KERNEL32!GlobalFree` at `0x18015ce9b`
- `KERNEL32!GlobalFree` at `0x18015ceaf`
- `KERNEL32!GetCurrentProcessId` at `0x18015cd71`
- `KERNEL32!GetCurrentProcessId` at `0x18015cf02`
- `KERNEL32!GetCurrentProcessId` at `0x18015cfbc`
- `KERNEL32!GetCurrentProcessId` at `0x18015d240`
- `KERNEL32!GetCurrentProcessId` at `0x18015d405`
- `KERNEL32!GetCurrentProcessId` at `0x18015cd71`
- `KERNEL32!GetCurrentProcessId` at `0x18015cf02`
- `KERNEL32!GetCurrentProcessId` at `0x18015cfbc`
- `KERNEL32!GetCurrentProcessId` at `0x18015d240`
- `KERNEL32!GetCurrentProcessId` at `0x18015d405`
- `KERNEL32!ExitProcess` at `0x18015d04e`
- `KERNEL32!ExitProcess` at `0x18015d386`
- `KERNEL32!ExitProcess` at `0x18015d04e`
- `KERNEL32!ExitProcess` at `0x18015d386`
- `KERNEL32!OpenProcess` at `0x18015cd81`
- `KERNEL32!OpenProcess` at `0x18015d2b9`
- `KERNEL32!OpenProcess` at `0x18015cd81`
- `KERNEL32!OpenProcess` at `0x18015d2b9`

## string_xrefs

- `0x18015ce3d`: `MSI_LUA: No elevated token available`
- `0x18015d1ef`: `Connected to service for CA interface.`

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
0x18015cd14  mov     [rsp-8+arg_10], rbx
0x18015cd19  push    rbp
0x18015cd1a  push    rsi
0x18015cd1b  push    rdi
0x18015cd1c  push    r12
0x18015cd1e  push    r13
0x18015cd20  push    r14
0x18015cd22  push    r15
0x18015cd24  lea     rbp, [rsp-50h]
0x18015cd29  sub     rsp, 150h
0x18015cd30  mov     rax, cs:__security_cookie
0x18015cd37  xor     rax, rsp
0x18015cd3a  mov     [rbp+80h+var_40], rax
0x18015cd3e  xor     esi, esi
0x18015cd40  movsxd  r14, edx
0x18015cd43  mov     [rbp+80h+var_BC], r14d
0x18015cd47  mov     r13, rcx
0x18015cd4a  mov     [rbp+80h+var_F8], 10h
0x18015cd51  mov     [rsp+180h+var_108], rsi
0x18015cd56  lea     ebx, [rsi+48h]
0x18015cd59  test    r14d, 0FFFFFFF6h
0x18015cd60  jnz     loc_18015CDFF
0x18015cd66  mov     dl, 1; bool
0x18015cd68  lea     rcx, [rbp+80h+var_D8]; this
0x18015cd6c  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x18015cd71  call    cs:__imp_GetCurrentProcessId
0x18015cd77  xor     edx, edx; bInheritHandle
0x18015cd79  mov     ecx, 100000h; dwDesiredAccess
0x18015cd7e  mov     r8d, eax; dwProcessId
0x18015cd81  call    cs:__imp_OpenProcess
0x18015cd87  test    rax, rax
0x18015cd8a  jnz     short loc_18015CDED
0x18015cd8c  lea     rax, [rbp+80h+var_A0]
0x18015cd90  mov     [rbp+80h+var_A8], ebx
0x18015cd93  lea     rcx, [rbp+80h+hMem]
0x18015cd97  mov     [rbp+80h+hMem], rax
0x18015cd9b  mov     [rbp+80h+var_A4], ebx
0x18015cd9e  call    ?GetCurrentUserSID@@YAKAEAV?$CAPITempBufferRef@E@@@Z; GetCurrentUserSID(CAPITempBufferRef<uchar> &)
0x18015cda3  test    eax, eax
0x18015cda5  jnz     short loc_18015CDB4
0x18015cda7  mov     rcx, [rbp+80h+hMem]; unsigned __int8 *
0x18015cdab  call    ?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z; SetInteractiveSynchronizeRightsForSID(uchar *,bool)
0x18015cdb0  test    al, al
0x18015cdb2  jnz     short loc_18015CDDC
0x18015cdb4  cmp     [rbp+80h+var_A8], ebx
0x18015cdb7  jle     short loc_18015CDC3
0x18015cdb9  mov     rcx, [rbp+80h+hMem]; hMem
0x18015cdbd  call    cs:__imp_GlobalFree
0x18015cdc3  lea     rax, [rbp+80h+var_A0]
0x18015cdc7  mov     [rbp+80h+var_A8], ebx
0x18015cdca  lea     rcx, [rbp+80h+var_D8]; this
0x18015cdce  mov     [rbp+80h+hMem], rax
0x18015cdd2  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18015cdd7  jmp     loc_18015D4C6
0x18015cddc  cmp     [rbp+80h+var_A8], ebx
0x18015cddf  jle     short loc_18015CDF6
0x18015cde1  mov     rcx, [rbp+80h+hMem]; hMem
0x18015cde5  call    cs:__imp_GlobalFree
0x18015cdeb  jmp     short loc_18015CDF6
0x18015cded  mov     rcx, rax; hObject
0x18015cdf0  call    cs:__imp_CloseHandle
0x18015cdf6  lea     rcx, [rbp+80h+var_D8]; this
0x18015cdfa  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18015cdff  lea     eax, [r14-6]
0x18015ce03  cmp     eax, 1
0x18015ce06  ja      loc_18015CEB5
0x18015ce0c  lea     rax, [rbp+80h+var_A0]
0x18015ce10  mov     [rbp+80h+var_A8], ebx
0x18015ce13  mov     [rbp+80h+hMem], rax
0x18015ce17  call    ?GetAISToken@@YAPEAXXZ; GetAISToken(void)
0x18015ce1c  test    rax, rax
0x18015ce1f  jnz     short loc_18015CE71
0x18015ce21  cmp     cs:?g_dmDiagnosticMode@@3HA, esi; int g_dmDiagnosticMode
0x18015ce27  jz      loc_18015D4C6
0x18015ce2d  mov     [rsp+180h+var_128], rsi; void *
0x18015ce32  lea     rax, aNull; "(NULL)"
0x18015ce39  mov     [rsp+180h+var_130], esi; unsigned int
0x18015ce3d  lea     r9, aMsiLuaNoElevat; "MSI_LUA: No elevated token available"
0x18015ce44  mov     [rsp+180h+var_138], rax; unsigned __int16 *
0x18015ce49  xor     edx, edx; unsigned __int16
0x18015ce4b  mov     [rsp+180h+var_140], rax; unsigned __int16 *
0x18015ce50  xor     r8d, r8d; int
0x18015ce53  mov     [rsp+180h+var_148], rax; unsigned __int16 *
0x18015ce58  mov     [rsp+180h+var_150], rax; unsigned __int16 *
0x18015ce5d  mov     [rsp+180h+phNewToken], rax; unsigned __int16 *
0x18015ce62  lea     ecx, [rdx+0Ah]; int
0x18015ce65  mov     qword ptr [rsp+180h+TokenType], rax; unsigned __int16 *
0x18015ce6a  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18015ce6f  jmp     short loc_18015CE8E
0x18015ce71  lea     rdx, [rbp+80h+var_A0]; char *
0x18015ce75  mov     rcx, rax; void *
0x18015ce78  call    ?GetUserSID@@YAKPEAXQEAD@Z; GetUserSID(void *,char * const)
0x18015ce7d  test    eax, eax
0x18015ce7f  jnz     short loc_18015CE8E
0x18015ce81  mov     rcx, [rbp+80h+hMem]; unsigned __int8 *
0x18015ce85  call    ?SetInteractiveSynchronizeRightsForSID@@YA_NPEAE_N@Z; SetInteractiveSynchronizeRightsForSID(uchar *,bool)
0x18015ce8a  test    al, al
0x18015ce8c  jnz     short loc_18015CEA6
0x18015ce8e  cmp     [rbp+80h+var_A8], ebx
0x18015ce91  jle     loc_18015D4C6
0x18015ce97  mov     rcx, [rbp+80h+hMem]; hMem
0x18015ce9b  call    cs:__imp_GlobalFree
0x18015cea1  jmp     loc_18015D4C6
0x18015cea6  cmp     [rbp+80h+var_A8], ebx
0x18015cea9  jle     short loc_18015CEB5
0x18015ceab  mov     rcx, [rbp+80h+hMem]; hMem
0x18015ceaf  call    cs:__imp_GlobalFree
0x18015ceb5  mov     edi, 2
0x18015ceba  cmp     cs:?g_scServerContext@@3W4scEnum@@A, edi; scEnum g_scServerContext
0x18015cec0  jnz     loc_18015D063
0x18015cec6  call    ?CreateConfigurationManager@@YAPEAVIMsiConfigurationManager@@XZ; CreateConfigurationManager(void)
0x18015cecb  mov     rbx, rax
0x18015cece  mov     [rbp+80h+TokenHandle], rax
0x18015ced2  lea     eax, [r14-6]
0x18015ced6  cmp     eax, 1
0x18015ced9  jbe     loc_18015CF7F
0x18015cedf  mov     dl, 1; bool
0x18015cee1  lea     rcx, [rbp+80h+var_E0]; this
0x18015cee5  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x18015ceea  mov     rax, [rbx]
0x18015ceed  mov     bl, [r13+0F0h]
0x18015cef4  mov     rdi, [r13+0C8h]
0x18015cefb  mov     rsi, [rax+160h]
0x18015cf02  call    cs:__imp_GetCurrentProcessId
0x18015cf08  xor     ecx, ecx
0x18015cf0a  mov     r9, rdi
0x18015cf0d  mov     [rsp+180h+var_120], rcx
0x18015cf12  mov     r8d, eax
0x18015cf15  mov     byte ptr [rsp+180h+var_128], bl
0x18015cf19  mov     rax, r14
0x18015cf1c  mov     byte ptr [rsp+180h+var_130], cl
0x18015cf20  mov     edx, r14d
0x18015cf23  mov     [rbp+80h+var_D8], rax
0x18015cf27  add     rax, rax
0x18015cf2a  lea     r15, ds:0[rax*8]
0x18015cf32  add     r15, r13
0x18015cf35  lea     rax, [rbp+80h+var_F8]
0x18015cf39  lea     r12, [r15+0Ch]
0x18015cf3d  mov     [rsp+180h+var_138], r12
0x18015cf42  mov     [rsp+180h+var_140], r15
0x18015cf47  mov     [rsp+180h+var_148], rax
0x18015cf4c  lea     rax, [rbp+80h+var_50]
0x18015cf50  mov     [rsp+180h+var_150], rax
0x18015cf55  mov     rax, rsi
0x18015cf58  mov     dword ptr [rsp+180h+phNewToken], ecx
0x18015cf5c  mov     qword ptr [rsp+180h+TokenType], rcx
0x18015cf61  mov     rcx, [rbp+80h+TokenHandle]
0x18015cf65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015cf6a  lea     rcx, [rbp+80h+var_E0]; this
0x18015cf6e  mov     [rsp+180h+var_108], rax
0x18015cf73  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x18015cf78  xor     esi, esi
0x18015cf7a  jmp     loc_18015D03D
0x18015cf7f  call    ?GetAISToken@@YAPEAXXZ; GetAISToken(void)
0x18015cf84  mov     [rbp+80h+var_E0], rax
0x18015cf88  test    rax, rax
0x18015cf8b  jz      loc_18015D055
0x18015cf91  mov     rdx, rax; Token
0x18015cf94  xor     ecx, ecx; Thread
0x18015cf96  call    cs:__imp_SetThreadToken
0x18015cf9c  test    eax, eax
0x18015cf9e  jz      loc_18015D04B
0x18015cfa4  mov     rax, [rbx]
0x18015cfa7  mov     bl, [r13+0F0h]
0x18015cfae  mov     rdi, [r13+0C8h]
0x18015cfb5  mov     rsi, [rax+160h]
0x18015cfbc  call    cs:__imp_GetCurrentProcessId
0x18015cfc2  xor     ecx, ecx
0x18015cfc4  mov     r9, rdi
0x18015cfc7  mov     r8d, eax
0x18015cfca  mov     edx, r14d
0x18015cfcd  mov     rax, r14
0x18015cfd0  mov     [rbp+80h+var_D8], rax
0x18015cfd4  add     rax, rax
0x18015cfd7  lea     r15, ds:0[rax*8]
0x18015cfdf  mov     rax, [rbp+80h+var_E0]
0x18015cfe3  mov     [rsp+180h+var_120], rax
0x18015cfe8  add     r15, r13
0x18015cfeb  mov     byte ptr [rsp+180h+var_128], bl
0x18015cfef  lea     rax, [rbp+80h+var_F8]
0x18015cff3  mov     byte ptr [rsp+180h+var_130], cl
0x18015cff7  lea     r12, [r15+0Ch]
0x18015cffb  mov     [rsp+180h+var_138], r12
0x18015d000  mov     [rsp+180h+var_140], r15
0x18015d005  mov     [rsp+180h+var_148], rax
0x18015d00a  lea     rax, [rbp+80h+var_50]
0x18015d00e  mov     [rsp+180h+var_150], rax
0x18015d013  mov     rax, rsi
0x18015d016  mov     dword ptr [rsp+180h+phNewToken], ecx
0x18015d01a  mov     qword ptr [rsp+180h+TokenType], rcx
0x18015d01f  mov     rcx, [rbp+80h+TokenHandle]
0x18015d023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d028  xor     edx, edx; Token
0x18015d02a  mov     [rsp+180h+var_108], rax
0x18015d02f  xor     ecx, ecx; Thread
0x18015d031  call    cs:__imp_SetThreadToken
0x18015d037  xor     esi, esi
0x18015d039  test    eax, eax
0x18015d03b  jz      short loc_18015D04B
0x18015d03d  lea     rcx, [rbp+80h+TokenHandle]
0x18015d041  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18015d046  jmp     loc_18015D3AE
0x18015d04b  or      ecx, 0FFFFFFFFh; uExitCode
0x18015d04e  call    cs:__imp_ExitProcess
0x18015d055  lea     rcx, [rbp+80h+TokenHandle]
0x18015d059  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18015d05e  jmp     loc_18015D4C6
0x18015d063  mov     rax, r14
0x18015d066  mov     [rbp+80h+var_D8], rax
0x18015d06a  add     rax, rax
0x18015d06d  lea     r15, ds:0[rax*8]
0x18015d075  add     r15, r13
0x18015d078  mov     [r15+8], esi
0x18015d07c  lea     r12, [r15+0Ch]
0x18015d080  mov     [r12], esi
0x18015d084  mov     rax, cs:?GetEnvironmentStringsW@KERNEL32@@3P6APEAXXZEA; void * (*KERNEL32::GetEnvironmentStringsW)(void)
0x18015d08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d090  mov     [rbp+80h+var_C8], rax
0x18015d094  mov     rbx, rax
0x18015d097  test    rax, rax
0x18015d09a  jz      short loc_18015D0B7
0x18015d09c  movzx   eax, word ptr [rax]
0x18015d09f  test    ax, ax
0x18015d0a2  jz      short loc_18015D0AC
0x18015d0a4  add     rbx, rdi
0x18015d0a7  cmp     [rbx], si
0x18015d0aa  jnz     short loc_18015D0A4
0x18015d0ac  add     rbx, rdi
0x18015d0af  movzx   eax, word ptr [rbx]
0x18015d0b2  test    ax, ax
0x18015d0b5  jnz     short loc_18015D0A4
0x18015d0b7  or      r14, 0FFFFFFFFFFFFFFFFh
0x18015d0bb  mov     [rbp+80h+var_D0], esi
0x18015d0be  mov     [rbp+80h+TokenHandle], r14
0x18015d0c2  mov     [rbp+80h+hObject], r14
0x18015d0c6  call    cs:__imp_GetCurrentThread
0x18015d0cc  lea     r9, [rbp+80h+TokenHandle]; TokenHandle
0x18015d0d0  xor     r8d, r8d; OpenAsSelf
0x18015d0d3  mov     rcx, rax; ThreadHandle
0x18015d0d6  mov     edx, edi; DesiredAccess
0x18015d0d8  call    cs:__imp_OpenThreadToken
0x18015d0de  test    eax, eax
0x18015d0e0  jnz     short loc_18015D10B
0x18015d0e2  mov     [rsp+180h+var_110], sil
0x18015d0e7  call    cs:__imp_GetLastError
0x18015d0ed  cmp     eax, 3F0h
0x18015d0f2  jnz     short loc_18015D110
0x18015d0f4  call    cs:__imp_GetCurrentProcess
0x18015d0fa  lea     r8, [rbp+80h+TokenHandle]; TokenHandle
0x18015d0fe  mov     edx, edi; DesiredAccess
0x18015d100  mov     rcx, rax; ProcessHandle
0x18015d103  call    cs:__imp_OpenProcessToken
0x18015d109  jmp     short loc_18015D110
0x18015d10b  mov     [rsp+180h+var_110], 1
0x18015d110  mov     rcx, [rbp+80h+TokenHandle]; hExistingToken
0x18015d114  cmp     rcx, r14
0x18015d117  jz      short loc_18015D16F
0x18015d119  xor     r8d, r8d; lpTokenAttributes
0x18015d11c  lea     rax, [rbp+80h+hObject]
0x18015d120  mov     [rsp+180h+phNewToken], rax; phNewToken
0x18015d125  mov     r9d, edi; ImpersonationLevel
0x18015d128  mov     [rsp+180h+TokenType], edi; TokenType
0x18015d12c  lea     edx, [r8+2Ch]; dwDesiredAccess
0x18015d130  call    cs:__imp_DuplicateTokenEx
0x18015d136  test    eax, eax
0x18015d138  jnz     short loc_18015D143
0x18015d13a  mov     rcx, r14
0x18015d13d  mov     [rbp+80h+hObject], rcx
0x18015d141  jmp     short loc_18015D147
0x18015d143  mov     rcx, [rbp+80h+hObject]; TokenHandle
0x18015d147  lea     rdx, [rbp+80h+var_D0]; unsigned int *
0x18015d14b  call    ?EnableAndMapDisabledPrivileges@@YA_NPEAXAEAK@Z; EnableAndMapDisabledPrivileges(void *,ulong &)
0x18015d150  test    al, al
0x18015d152  jnz     short loc_18015D16B
0x18015d154  mov     rcx, [rbp+80h+hObject]; hObject
0x18015d158  call    cs:__imp_CloseHandle
0x18015d15e  mov     rcx, [rbp+80h+TokenHandle]
0x18015d162  mov     rdx, r14
0x18015d165  mov     [rbp+80h+hObject], rdx
0x18015d169  jmp     short loc_18015D173
0x18015d16b  mov     rcx, [rbp+80h+TokenHandle]
0x18015d16f  mov     rdx, [rbp+80h+hObject]; Token
0x18015d173  cmp     rdx, r14
0x18015d176  jz      short loc_18015D192
0x18015d178  xor     ecx, ecx; Thread
0x18015d17a  call    cs:__imp_SetThreadToken
0x18015d180  mov     rcx, [rbp+80h+hObject]; hObject
0x18015d184  test    eax, eax
0x18015d186  jnz     short loc_18015D1AD
0x18015d188  call    cs:__imp_CloseHandle
0x18015d18e  mov     rcx, [rbp+80h+TokenHandle]; hObject
0x18015d192  cmp     rcx, r14
0x18015d195  jz      short loc_18015D19D
0x18015d197  call    cs:__imp_CloseHandle
0x18015d19d  mov     rcx, [rbp+80h+var_C8]
0x18015d1a1  mov     rax, cs:?FreeEnvironmentStringsW@KERNEL32@@3P6AHPEAG@ZEA; int (*KERNEL32::FreeEnvironmentStringsW)(ushort *)
0x18015d1a8  jmp     loc_18015D4C1
0x18015d1ad  call    cs:__imp_CloseHandle
0x18015d1b3  mov     [rbp+80h+hObject], r14
0x18015d1b7  call    ?CreateMsiServer@@YAPEAUIMsiServer@@XZ; CreateMsiServer(void)
  ... truncated ...
```
