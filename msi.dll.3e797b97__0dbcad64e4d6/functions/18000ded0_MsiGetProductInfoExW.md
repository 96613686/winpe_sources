# MsiGetProductInfoExW

- ea: `0x18000ded0`
- end: `0x18000e59e`
- name: `MsiGetProductInfoExW`
- size: `1742`
- prototype: `UINT __stdcall(LPCWSTR szProductCode, LPCWSTR szUserSid, MSIINSTALLCONTEXT dwContext, LPCWSTR szProperty, LPWSTR szValue, LPDWORD pcchValue)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18005a450`
- `0x18018fe30`
- `0x180193bf0`

## callees

- `0x18000c4bc`
- `0x18000d980`
- `0x18000ded0`
- `0x18000e5b0`
- `0x180045ba4`
- `0x18015cbac`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18000e417`
- `ADVAPI32!SetThreadToken` at `0x18000e444`
- `ADVAPI32!SetThreadToken` at `0x18000e4da`
- `ADVAPI32!SetThreadToken` at `0x18000e53e`
- `ADVAPI32!SetThreadToken` at `0x18000e417`
- `ADVAPI32!SetThreadToken` at `0x18000e444`
- `ADVAPI32!SetThreadToken` at `0x18000e4da`
- `ADVAPI32!SetThreadToken` at `0x18000e53e`
- `ADVAPI32!OpenThreadToken` at `0x18000e1bc`
- `ADVAPI32!OpenThreadToken` at `0x18000e259`
- `ADVAPI32!OpenThreadToken` at `0x18000e1bc`
- `ADVAPI32!OpenThreadToken` at `0x18000e259`
- `ADVAPI32!OpenProcessToken` at `0x18000e1f7`
- `ADVAPI32!OpenProcessToken` at `0x18000e298`
- `ADVAPI32!OpenProcessToken` at `0x18000e1f7`
- `ADVAPI32!OpenProcessToken` at `0x18000e298`
- `KERNEL32!CloseHandle` at `0x18000e3d5`
- `KERNEL32!CloseHandle` at `0x18000e3fe`
- `KERNEL32!CloseHandle` at `0x18000e431`
- `KERNEL32!CloseHandle` at `0x18000e45e`
- `KERNEL32!CloseHandle` at `0x18000e3d5`
- `KERNEL32!CloseHandle` at `0x18000e3fe`
- `KERNEL32!CloseHandle` at `0x18000e431`
- `KERNEL32!CloseHandle` at `0x18000e45e`
- `KERNEL32!LeaveCriticalSection` at `0x18000df60`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfd8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e0ab`
- `KERNEL32!LeaveCriticalSection` at `0x18000e11b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e2fc`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3b2`
- `KERNEL32!LeaveCriticalSection` at `0x18000df60`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfd8`
- `KERNEL32!LeaveCriticalSection` at `0x18000e0ab`
- `KERNEL32!LeaveCriticalSection` at `0x18000e11b`
- `KERNEL32!LeaveCriticalSection` at `0x18000e2fc`
- `KERNEL32!LeaveCriticalSection` at `0x18000e3b2`
- `KERNEL32!GetLastError` at `0x18000df82`
- `KERNEL32!GetLastError` at `0x18000df82`
- `KERNEL32!OutputDebugStringW` at `0x18000e2d9`
- `KERNEL32!OutputDebugStringW` at `0x18000e2d9`
- `KERNEL32!EnterCriticalSection` at `0x18000df3e`
- `KERNEL32!EnterCriticalSection` at `0x18000dfb1`
- `KERNEL32!EnterCriticalSection` at `0x18000e02b`
- `KERNEL32!EnterCriticalSection` at `0x18000e102`
- `KERNEL32!EnterCriticalSection` at `0x18000df3e`
- `KERNEL32!EnterCriticalSection` at `0x18000dfb1`
- `KERNEL32!EnterCriticalSection` at `0x18000e02b`
- `KERNEL32!EnterCriticalSection` at `0x18000e102`
- `KERNEL32!GlobalAlloc` at `0x18000e162`
- `KERNEL32!GlobalAlloc` at `0x18000e162`
- `KERNEL32!GetCurrentThread` at `0x18000e19d`
- `KERNEL32!GetCurrentThread` at `0x18000e23a`
- `KERNEL32!GetCurrentThread` at `0x18000e19d`
- `KERNEL32!GetCurrentThread` at `0x18000e23a`
- `KERNEL32!GetCurrentProcess` at `0x18000e1de`
- `KERNEL32!GetCurrentProcess` at `0x18000e27f`
- `KERNEL32!GetCurrentProcess` at `0x18000e1de`
- `KERNEL32!GetCurrentProcess` at `0x18000e27f`
- `KERNEL32!TlsSetValue` at `0x18000df9b`
- `KERNEL32!TlsSetValue` at `0x18000e136`
- `KERNEL32!TlsSetValue` at `0x18000df9b`
- `KERNEL32!TlsSetValue` at `0x18000e136`
- `KERNEL32!TlsGetValue` at `0x18000df6e`
- `KERNEL32!TlsGetValue` at `0x18000df6e`
- `KERNEL32!TlsAlloc` at `0x18000e38e`
- `KERNEL32!TlsAlloc` at `0x18000e38e`

## string_xrefs

- `0x18000e2d2`: `Failed to release Service\n`
- `0x18000e353`: `MsiGetProductInfoExW is returning: %u`
- `0x18000e47c`: `Entering MsiGetProductInfoExW. szProductCode: %s, szUserSid: %s, dwInstallContext: %d, szProperty: %s`

## pseudocode

```c
UINT __stdcall MsiGetProductInfoExW(
        LPCWSTR szProductCode,
        LPCWSTR szUserSid,
        MSIINSTALLCONTEXT dwContext,
        LPCWSTR szProperty,
        LPWSTR szValue,
        LPDWORD pcchValue)
{
  int v10; // eax
  void *Value; // rdi
  char v12; // bp
  DWORD v13; // ebx
  UINT Info; // esi
  int v15; // eax
  DWORD v16; // ebx
  CMsiServices *v18; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v21; // rax
  HANDLE v22; // rax
  BOOL v23; // ebx
  BOOL v24; // ebx
  const unsigned __int16 *v25; // r10
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rax
  void *TokenHandle; // [rsp+60h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-30h] BYREF

  if ( g_dmDiagnosticMode )
  {
    v25 = szProperty;
    if ( !szProperty )
      v25 = &Default;
    v26 = szUserSid;
    v27 = szProductCode;
    if ( !szUserSid )
      v26 = &Default;
    if ( !szProductCode )
      v27 = &Default;
    DebugString(
      9,
      0,
      0,
      L"Entering MsiGetProductInfoExW. szProductCode: %s, szUserSid: %s, dwInstallContext: %d, szProperty: %s",
      v27,
      v26,
      (const unsigned __int16 *)(int)dwContext,
      v25,
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v10 = dword_180310D00;
  Value = 0;
  v12 = 0;
  if ( dword_180310D00 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v23 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180310D00 = v23;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v10 = dword_180310D00;
  }
  if ( g_scServerContext != 2 && v10 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v13 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1
      && (g_dwImpersonationSlot = TlsAlloc(), v13 = g_dwImpersonationSlot, g_dwImpersonationSlot == -1) )
    {
      LeaveCriticalSection(&g_csImpersonationLock);
    }
    else
    {
      LeaveCriticalSection(&g_csImpersonationLock);
      Value = TlsGetValue(v13);
      if ( Value || !GetLastError() )
      {
        TlsSetValue(v13, (LPVOID)0xFFFFFFFF80000000LL);
        v12 = 1;
      }
    }
  }
  EnterCriticalSection(&g_csSharedServicesLock);
  if ( !g_piSharedServices )
  {
    v18 = (CMsiServices *)GlobalAlloc(0x40u, 0x78u);
    if ( v18 )
    {
      g_piSharedServices = CMsiServices::CMsiServices(v18);
      if ( g_piSharedServices )
        goto LABEL_10;
    }
    else
    {
      g_piSharedServices = 0;
    }
    LeaveCriticalSection(&g_csSharedServicesLock);
    goto LABEL_49;
  }
LABEL_10:
  ++g_cSharedServices;
  LeaveCriticalSection(&g_csSharedServicesLock);
  if ( !g_piSharedServices )
  {
LABEL_49:
    Info = 1627;
    goto LABEL_20;
  }
  Info = GetInfoEx(szProductCode, szUserSid, dwContext, 0, szProperty, szValue, pcchValue);
  EnterCriticalSection(&g_csSharedServicesLock);
  if ( !--g_cSharedServices )
  {
    if ( g_piSharedDllsRegKey )
    {
      (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey + 16LL))(g_piSharedDllsRegKey);
      g_piSharedDllsRegKey = 0;
    }
    if ( g_piSharedDllsRegKey32 )
    {
      (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey32 + 16LL))(g_piSharedDllsRegKey32);
      g_piSharedDllsRegKey32 = 0;
    }
    (*(void (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 160LL))(g_piSharedServices);
    while ( (*(int (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 16LL))(g_piSharedServices) > 0 )
      OutputDebugStringW(L"Failed to release Service\r\n");
    g_piSharedServices = 0;
  }
  LeaveCriticalSection(&g_csSharedServicesLock);
LABEL_20:
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"MsiGetProductInfoExW is returning: %u",
      (const unsigned __int16 *)Info,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  v15 = dword_180310D00;
  if ( dword_180310D00 == -1 )
  {
    TokenHandle = (void *)-1LL;
    v21 = GetCurrentThread();
    if ( OpenThreadToken(v21, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    v22 = GetCurrentProcess();
    if ( OpenProcessToken(v22, 8u, &hObject) )
    {
      v24 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180310D00 = v24;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v15 = dword_180310D00;
  }
  if ( v15 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v16 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v16 != -1 )
    {
      if ( v12 )
        TlsSetValue(v16, Value);
    }
  }
  return Info;
}

```

## disassembly

```asm
0x18000ded0  mov     rax, rsp
0x18000ded3  push    rbp
0x18000ded4  push    rsi
0x18000ded5  push    rdi
0x18000ded6  sub     rsp, 80h
0x18000dedd  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18000dee4  mov     rsi, r9
0x18000dee7  mov     [rax+10h], r12
0x18000deeb  mov     [rax+18h], r13
0x18000deef  lea     r13, aNull; "(NULL)"
0x18000def6  mov     [rax-20h], r14
0x18000defa  mov     r14, rdx
0x18000defd  mov     [rax-28h], r15
0x18000df01  mov     r15, rcx
0x18000df04  movsxd  r12, r8d
0x18000df07  jnz     loc_18000E46F
0x18000df0d  mov     eax, cs:dword_180310D00
0x18000df13  xor     edi, edi
0x18000df15  xor     bpl, bpl
0x18000df18  mov     [rsp+98h+arg_0], rbx
0x18000df20  cmp     eax, 0FFFFFFFFh
0x18000df23  jz      loc_18000E194
0x18000df29  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18000df30  jz      short loc_18000DFAA
0x18000df32  cmp     eax, 1
0x18000df35  jnz     short loc_18000DFAA
0x18000df37  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000df3e  call    cs:__imp_EnterCriticalSection
0x18000df45  nop     dword ptr [rax+rax+00h]
0x18000df4a  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18000df50  cmp     ebx, 0FFFFFFFFh
0x18000df53  jz      loc_18000E38E
0x18000df59  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000df60  call    cs:__imp_LeaveCriticalSection
0x18000df67  nop     dword ptr [rax+rax+00h]
0x18000df6c  mov     ecx, ebx; dwTlsIndex
0x18000df6e  call    cs:__imp_TlsGetValue
0x18000df75  nop     dword ptr [rax+rax+00h]
0x18000df7a  mov     rdi, rax
0x18000df7d  test    rax, rax
0x18000df80  jnz     short loc_18000DF92
0x18000df82  call    cs:__imp_GetLastError
0x18000df89  nop     dword ptr [rax+rax+00h]
0x18000df8e  test    eax, eax
0x18000df90  jnz     short loc_18000DFAA
0x18000df92  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x18000df99  mov     ecx, ebx; dwTlsIndex
0x18000df9b  call    cs:__imp_TlsSetValue
0x18000dfa2  nop     dword ptr [rax+rax+00h]
0x18000dfa7  mov     bpl, 1
0x18000dfaa  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dfb1  call    cs:__imp_EnterCriticalSection
0x18000dfb8  nop     dword ptr [rax+rax+00h]
0x18000dfbd  cmp     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18000dfc5  jz      loc_18000E158
0x18000dfcb  inc     cs:?g_cSharedServices@@3HA; int g_cSharedServices
0x18000dfd1  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dfd8  call    cs:__imp_LeaveCriticalSection
0x18000dfdf  nop     dword ptr [rax+rax+00h]
0x18000dfe4  cmp     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18000dfec  jz      loc_18000E308
0x18000dff2  mov     rax, [rsp+98h+pcchValue]
0x18000dffa  xor     r9d, r9d; bool
0x18000dffd  mov     [rsp+98h+var_68], rax; unsigned int *
0x18000e002  mov     r8d, r12d; enum tagMSIINSTALLCONTEXT
0x18000e005  mov     rax, [rsp+98h+szValue]
0x18000e00d  mov     rdx, r14; unsigned __int16 *
0x18000e010  mov     [rsp+98h+var_70], rax; unsigned __int16 *
0x18000e015  mov     rcx, r15; unsigned __int16 *
0x18000e018  mov     [rsp+98h+var_78], rsi; unsigned __int16 *
0x18000e01d  call    ?GetInfoEx@@YAKPEBG0W4tagMSIINSTALLCONTEXT@@_N0PEAGPEAK@Z; GetInfoEx(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,bool,ushort const *,ushort *,ulong *)
0x18000e022  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e029  mov     esi, eax
0x18000e02b  call    cs:__imp_EnterCriticalSection
0x18000e032  nop     dword ptr [rax+rax+00h]
0x18000e037  mov     ecx, cs:?g_cSharedServices@@3HA; int g_cSharedServices
0x18000e03d  sub     ecx, 1
0x18000e040  mov     cs:?g_cSharedServices@@3HA, ecx; int g_cSharedServices
0x18000e046  jnz     short loc_18000E0A4
0x18000e048  mov     rcx, cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey
0x18000e04f  test    rcx, rcx
0x18000e052  jnz     loc_18000E312
0x18000e058  mov     rcx, cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey32
0x18000e05f  test    rcx, rcx
0x18000e062  jnz     loc_18000E32E
0x18000e068  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18000e06f  mov     rax, [rcx]
0x18000e072  mov     rax, [rax+0A0h]
0x18000e079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e07e  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18000e085  mov     rax, [rcx]
0x18000e088  mov     rax, [rax+10h]
0x18000e08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e091  test    eax, eax
0x18000e093  jg      loc_18000E2D2
0x18000e099  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18000e0a4  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e0ab  call    cs:__imp_LeaveCriticalSection
0x18000e0b2  nop     dword ptr [rax+rax+00h]
0x18000e0b7  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18000e0be  mov     r15, [rsp+98h+var_28]
0x18000e0c3  mov     r14, [rsp+98h+var_20]
0x18000e0c8  mov     r12, [rsp+98h+arg_8]
0x18000e0d0  jnz     loc_18000E34A
0x18000e0d6  mov     eax, cs:dword_180310D00
0x18000e0dc  cmp     eax, 0FFFFFFFFh
0x18000e0df  jz      loc_18000E231
0x18000e0e5  mov     r13, [rsp+98h+arg_10]
0x18000e0ed  cmp     eax, 1
0x18000e0f0  jnz     short loc_18000E142
0x18000e0f2  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18000e0f9  jz      short loc_18000E142
0x18000e0fb  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e102  call    cs:__imp_EnterCriticalSection
0x18000e109  nop     dword ptr [rax+rax+00h]
0x18000e10e  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18000e114  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e11b  call    cs:__imp_LeaveCriticalSection
0x18000e122  nop     dword ptr [rax+rax+00h]
0x18000e127  cmp     ebx, 0FFFFFFFFh
0x18000e12a  jz      short loc_18000E142
0x18000e12c  test    bpl, bpl
0x18000e12f  jz      short loc_18000E142
0x18000e131  mov     rdx, rdi; lpTlsValue
0x18000e134  mov     ecx, ebx; dwTlsIndex
0x18000e136  call    cs:__imp_TlsSetValue
0x18000e13d  nop     dword ptr [rax+rax+00h]
0x18000e142  mov     rbx, [rsp+98h+arg_0]
0x18000e14a  mov     eax, esi
0x18000e14c  add     rsp, 80h
0x18000e153  pop     rdi
0x18000e154  pop     rsi
0x18000e155  pop     rbp
0x18000e156  retn
0x18000e158  mov     edx, 78h ; 'x'; dwBytes
0x18000e15d  mov     ecx, 40h ; '@'; uFlags
0x18000e162  call    cs:__imp_GlobalAlloc
0x18000e169  nop     dword ptr [rax+rax+00h]
0x18000e16e  test    rax, rax
0x18000e171  jz      loc_18000E2EA
0x18000e177  mov     rcx, rax; this
0x18000e17a  call    ??0CMsiServices@@QEAA@XZ; CMsiServices::CMsiServices(void)
0x18000e17f  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, rax; IMsiServices * g_piSharedServices
0x18000e186  test    rax, rax
0x18000e189  jnz     loc_18000DFCB
0x18000e18f  jmp     loc_18000E2F5
0x18000e194  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e19d  call    cs:__imp_GetCurrentThread
0x18000e1a4  nop     dword ptr [rax+rax+00h]
0x18000e1a9  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18000e1ae  mov     edx, 4; DesiredAccess
0x18000e1b3  mov     rcx, rax; ThreadHandle
0x18000e1b6  mov     r8d, 1; OpenAsSelf
0x18000e1bc  call    cs:__imp_OpenThreadToken
0x18000e1c3  nop     dword ptr [rax+rax+00h]
0x18000e1c8  test    eax, eax
0x18000e1ca  jnz     loc_18000E4D6
0x18000e1d0  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e1d9  mov     [rsp+98h+hObject], rdi
0x18000e1de  call    cs:__imp_GetCurrentProcess
0x18000e1e5  nop     dword ptr [rax+rax+00h]
0x18000e1ea  lea     r8, [rsp+98h+hObject]; TokenHandle
0x18000e1ef  mov     edx, 8; DesiredAccess
0x18000e1f4  mov     rcx, rax; ProcessHandle
0x18000e1f7  call    cs:__imp_OpenProcessToken
0x18000e1fe  nop     dword ptr [rax+rax+00h]
0x18000e203  test    eax, eax
0x18000e205  jnz     loc_18000E3C3
0x18000e20b  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18000e211  jnz     loc_18000E4F8
0x18000e217  mov     rdx, [rsp+98h+TokenHandle]; Token
0x18000e21c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000e220  jnz     loc_18000E415
0x18000e226  mov     eax, cs:dword_180310D00
0x18000e22c  jmp     loc_18000DF29
0x18000e231  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e23a  call    cs:__imp_GetCurrentThread
0x18000e241  nop     dword ptr [rax+rax+00h]
0x18000e246  lea     r9, [rsp+98h+TokenHandle]; TokenHandle
0x18000e24b  mov     edx, 4; DesiredAccess
0x18000e250  mov     rcx, rax; ThreadHandle
0x18000e253  mov     r8d, 1; OpenAsSelf
0x18000e259  call    cs:__imp_OpenThreadToken
0x18000e260  nop     dword ptr [rax+rax+00h]
0x18000e265  test    eax, eax
0x18000e267  jnz     loc_18000E53A
0x18000e26d  mov     [rsp+98h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e276  mov     [rsp+98h+hObject], 0
0x18000e27f  call    cs:__imp_GetCurrentProcess
0x18000e286  nop     dword ptr [rax+rax+00h]
0x18000e28b  lea     r8, [rsp+98h+hObject]; TokenHandle
0x18000e290  mov     edx, 8; DesiredAccess
0x18000e295  mov     rcx, rax; ProcessHandle
0x18000e298  call    cs:__imp_OpenProcessToken
0x18000e29f  nop     dword ptr [rax+rax+00h]
0x18000e2a4  test    eax, eax
0x18000e2a6  jnz     loc_18000E3EC
0x18000e2ac  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18000e2b2  jnz     loc_18000E55C
0x18000e2b8  mov     rdx, [rsp+98h+TokenHandle]; Token
0x18000e2bd  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18000e2c1  jnz     loc_18000E442
0x18000e2c7  mov     eax, cs:dword_180310D00
0x18000e2cd  jmp     loc_18000E0E5
0x18000e2d2  lea     rcx, aFailedToReleas; "Failed to release Service\r\n"
0x18000e2d9  call    cs:__imp_OutputDebugStringW
0x18000e2e0  nop     dword ptr [rax+rax+00h]
0x18000e2e5  jmp     loc_18000E07E
0x18000e2ea  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, 0; IMsiServices * g_piSharedServices
0x18000e2f5  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e2fc  call    cs:__imp_LeaveCriticalSection
0x18000e303  nop     dword ptr [rax+rax+00h]
0x18000e308  mov     esi, 65Bh
0x18000e30d  jmp     loc_18000E0B7
0x18000e312  mov     rdx, [rcx]
0x18000e315  mov     rax, [rdx+10h]
0x18000e319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e31e  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, 0; IMsiRegKey * g_piSharedDllsRegKey
0x18000e329  jmp     loc_18000E058
0x18000e32e  mov     rax, [rcx]
0x18000e331  mov     rax, [rax+10h]
0x18000e335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33a  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, 0; IMsiRegKey * g_piSharedDllsRegKey32
0x18000e345  jmp     loc_18000E068
0x18000e34a  xor     edx, edx; unsigned __int16
0x18000e34c  mov     eax, esi
0x18000e34e  mov     [rsp+98h+var_40], rdx; void *
0x18000e353  lea     r9, aMsigetproducti_5; "MsiGetProductInfoExW is returning: %u"
0x18000e35a  mov     [rsp+98h+var_48], edx; unsigned int
0x18000e35e  xor     r8d, r8d; int
0x18000e361  mov     [rsp+98h+var_50], r13; unsigned __int16 *
0x18000e366  mov     ecx, 9; int
0x18000e36b  mov     [rsp+98h+var_58], r13; unsigned __int16 *
0x18000e370  mov     [rsp+98h+var_60], r13; unsigned __int16 *
0x18000e375  mov     [rsp+98h+var_68], r13; unsigned __int16 *
0x18000e37a  mov     [rsp+98h+var_70], r13; unsigned __int16 *
0x18000e37f  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x18000e384  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000e389  jmp     loc_18000E0D6
0x18000e38e  call    cs:__imp_TlsAlloc
0x18000e395  nop     dword ptr [rax+rax+00h]
0x18000e39a  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x18000e3a0  mov     ebx, eax
0x18000e3a2  cmp     eax, 0FFFFFFFFh
0x18000e3a5  jnz     loc_18000DF59
0x18000e3ab  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e3b2  call    cs:__imp_LeaveCriticalSection
0x18000e3b9  nop     dword ptr [rax+rax+00h]
0x18000e3be  jmp     loc_18000DFAA
0x18000e3c3  mov     rcx, [rsp+98h+hObject]; void *
0x18000e3c8  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18000e3cd  mov     rcx, [rsp+98h+hObject]; hObject
0x18000e3d2  movzx   ebx, al
0x18000e3d5  call    cs:__imp_CloseHandle
0x18000e3dc  nop     dword ptr [rax+rax+00h]
0x18000e3e1  mov     cs:dword_180310D00, ebx
0x18000e3e7  jmp     loc_18000E217
0x18000e3ec  mov     rcx, [rsp+98h+hObject]; void *
0x18000e3f1  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18000e3f6  mov     rcx, [rsp+98h+hObject]; hObject
0x18000e3fb  movzx   ebx, al
0x18000e3fe  call    cs:__imp_CloseHandle
0x18000e405  nop     dword ptr [rax+rax+00h]
0x18000e40a  mov     cs:dword_180310D00, ebx
0x18000e410  jmp     loc_18000E2B8
0x18000e415  xor     ecx, ecx; Thread
0x18000e417  call    cs:__imp_SetThreadToken
0x18000e41e  nop     dword ptr [rax+rax+00h]
0x18000e423  test    eax, eax
0x18000e425  jnz     short loc_18000E42C
0x18000e427  call    ExitProcessIfNotClient
0x18000e42c  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18000e431  call    cs:__imp_CloseHandle
0x18000e438  nop     dword ptr [rax+rax+00h]
0x18000e43d  jmp     loc_18000E226
0x18000e442  xor     ecx, ecx; Thread
0x18000e444  call    cs:__imp_SetThreadToken
0x18000e44b  nop     dword ptr [rax+rax+00h]
0x18000e450  test    eax, eax
0x18000e452  jnz     short loc_18000E459
0x18000e454  call    ExitProcessIfNotClient
0x18000e459  mov     rcx, [rsp+98h+TokenHandle]; hObject
0x18000e45e  call    cs:__imp_CloseHandle
0x18000e465  nop     dword ptr [rax+rax+00h]
0x18000e46a  jmp     loc_18000E2C7
0x18000e46f  lea     rdx, Default
0x18000e476  test    rsi, rsi
0x18000e479  mov     r10, rsi
0x18000e47c  lea     r9, aEnteringMsiget_3; "Entering MsiGetProductInfoExW. szProduc"...
0x18000e483  cmovz   r10, rdx
0x18000e487  mov     rcx, r14
0x18000e48a  test    r14, r14
0x18000e48d  mov     rax, r15
0x18000e490  cmovz   rcx, rdx
0x18000e494  test    r15, r15
0x18000e497  cmovz   rax, rdx
0x18000e49b  xor     edx, edx; unsigned __int16
0x18000e49d  mov     [rsp+98h+var_40], rdx; void *
0x18000e4a2  xor     r8d, r8d; int
0x18000e4a5  mov     [rsp+98h+var_48], edx; unsigned int
  ... truncated ...
```
