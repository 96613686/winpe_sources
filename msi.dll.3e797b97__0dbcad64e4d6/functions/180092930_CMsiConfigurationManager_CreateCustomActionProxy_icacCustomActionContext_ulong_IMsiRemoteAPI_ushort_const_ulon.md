# CMsiConfigurationManager::CreateCustomActionProxy(icacCustomActionContext,ulong,IMsiRemoteAPI *,ushort const *,ulong,uchar *,int *,void * *,ulong *,bool,bool,void *)

- ea: `0x180092930`
- end: `0x1800942ea`
- name: `?CreateCustomActionProxy@CMsiConfigurationManager@@UEAAPEAUIMsiCustomAction@@W4icacCustomActionContext@@KPEAUIMsiRemoteAPI@@PEBGKPEAEPEAHPEAPEAXPEAK_N7PEAX@Z`
- size: `6586`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180018ee0`
- `0x180019cc0`
- `0x180027634`
- `0x180045ba4`
- `0x180067fec`
- `0x1800817f8`
- `0x180092280`
- `0x18009244c`
- `0x1800924b8`
- `0x180092930`
- `0x1800945b0`
- `0x1800b9c08`
- `0x1800d04fc`
- `0x180148ae8`
- `0x18014c8cc`
- `0x18015c794`
- `0x18015df24`
- `0x1801b7920`
- `0x1801b79a0`
- `0x1801b79dc`
- `0x1801cbc84`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ntdll!RtlRandom` at `0x180092d44`
- `ntdll!RtlRandom` at `0x180092d44`
- `ADVAPI32!CreateProcessAsUserW` at `0x180093bad`
- `ADVAPI32!CreateProcessAsUserW` at `0x180093bad`
- `ADVAPI32!SetTokenInformation` at `0x180092b61`
- `ADVAPI32!SetTokenInformation` at `0x180092b61`
- `ADVAPI32!GetTokenInformation` at `0x180092b43`
- `ADVAPI32!GetTokenInformation` at `0x180092b43`
- `ADVAPI32!SetThreadToken` at `0x180093cf1`
- `ADVAPI32!SetThreadToken` at `0x180093cf1`
- `ADVAPI32!DuplicateTokenEx` at `0x180092a8e`
- `ADVAPI32!DuplicateTokenEx` at `0x180092bd3`
- `ADVAPI32!DuplicateTokenEx` at `0x180092a8e`
- `ADVAPI32!DuplicateTokenEx` at `0x180092bd3`
- `ADVAPI32!OpenThreadToken` at `0x180092adb`
- `ADVAPI32!OpenThreadToken` at `0x180092c04`
- `ADVAPI32!OpenThreadToken` at `0x180093472`
- `ADVAPI32!OpenThreadToken` at `0x180093686`
- `ADVAPI32!OpenThreadToken` at `0x180092adb`
- `ADVAPI32!OpenThreadToken` at `0x180092c04`
- `ADVAPI32!OpenThreadToken` at `0x180093472`
- `ADVAPI32!OpenThreadToken` at `0x180093686`
- `ADVAPI32!OpenProcessToken` at `0x180092a5b`
- `ADVAPI32!OpenProcessToken` at `0x180092a5b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800933be`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18009341c`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800933be`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18009341c`
- `KERNEL32!CloseHandle` at `0x180092aa7`
- `KERNEL32!CloseHandle` at `0x180092af0`
- `KERNEL32!CloseHandle` at `0x180092b76`
- `KERNEL32!CloseHandle` at `0x180092b8b`
- `KERNEL32!CloseHandle` at `0x180092c67`
- `KERNEL32!CloseHandle` at `0x180092c7c`
- `KERNEL32!CloseHandle` at `0x1800930a4`
- `KERNEL32!CloseHandle` at `0x18009318e`
- `KERNEL32!CloseHandle` at `0x180093218`
- `KERNEL32!CloseHandle` at `0x1800932fb`
- `KERNEL32!CloseHandle` at `0x1800934ed`
- `KERNEL32!CloseHandle` at `0x180093578`
- `KERNEL32!CloseHandle` at `0x18009358d`
- `KERNEL32!CloseHandle` at `0x1800936e8`
- `KERNEL32!CloseHandle` at `0x1800936fd`
- `KERNEL32!CloseHandle` at `0x18009382d`
- `KERNEL32!CloseHandle` at `0x180093842`
- `KERNEL32!CloseHandle` at `0x1800938f9`
- `KERNEL32!CloseHandle` at `0x18009390e`
- `KERNEL32!CloseHandle` at `0x180093afc`
- `KERNEL32!CloseHandle` at `0x180093b1e`
- `KERNEL32!CloseHandle` at `0x180093d57`
- `KERNEL32!CloseHandle` at `0x180093d68`
- `KERNEL32!CloseHandle` at `0x180093d78`
- `KERNEL32!CloseHandle` at `0x180093d8d`
- `KERNEL32!CloseHandle` at `0x180093dce`
- `KERNEL32!CloseHandle` at `0x180093ddf`
- `KERNEL32!CloseHandle` at `0x180093df4`
- `KERNEL32!CloseHandle` at `0x180093ee8`
- `KERNEL32!CloseHandle` at `0x180093f16`
- `KERNEL32!CloseHandle` at `0x180093f39`
- `KERNEL32!CloseHandle` at `0x180093fa9`
- `KERNEL32!CloseHandle` at `0x1800940d6`
- `KERNEL32!CloseHandle` at `0x1800940e6`
- `KERNEL32!CloseHandle` at `0x1800940fb`
- `KERNEL32!CloseHandle` at `0x180094155`
- `KERNEL32!CloseHandle` at `0x18009416a`
- `KERNEL32!CloseHandle` at `0x1800942ac`
- `KERNEL32!CloseHandle` at `0x1800942bd`
- `KERNEL32!CloseHandle` at `0x1800942d2`
- `KERNEL32!CloseHandle` at `0x180092aa7`
- `KERNEL32!CloseHandle` at `0x180092af0`
- `KERNEL32!CloseHandle` at `0x180092b76`
- `KERNEL32!CloseHandle` at `0x180092b8b`
- `KERNEL32!CloseHandle` at `0x180092c67`
- `KERNEL32!CloseHandle` at `0x180092c7c`
- `KERNEL32!CloseHandle` at `0x1800930a4`
- `KERNEL32!CloseHandle` at `0x18009318e`
- `KERNEL32!CloseHandle` at `0x180093218`
- `KERNEL32!CloseHandle` at `0x1800932fb`
- `KERNEL32!CloseHandle` at `0x1800934ed`
- `KERNEL32!CloseHandle` at `0x180093578`
- `KERNEL32!CloseHandle` at `0x18009358d`
- `KERNEL32!CloseHandle` at `0x1800936e8`
- `KERNEL32!CloseHandle` at `0x1800936fd`
- `KERNEL32!CloseHandle` at `0x18009382d`
- `KERNEL32!CloseHandle` at `0x180093842`
- `KERNEL32!CloseHandle` at `0x1800938f9`
- `KERNEL32!CloseHandle` at `0x18009390e`
- `KERNEL32!CloseHandle` at `0x180093afc`
- `KERNEL32!CloseHandle` at `0x180093b1e`
- `KERNEL32!CloseHandle` at `0x180093d57`
- `KERNEL32!CloseHandle` at `0x180093d68`
- `KERNEL32!CloseHandle` at `0x180093d78`
- `KERNEL32!CloseHandle` at `0x180093d8d`
- `KERNEL32!CloseHandle` at `0x180093dce`
- `KERNEL32!CloseHandle` at `0x180093ddf`
- `KERNEL32!CloseHandle` at `0x180093df4`
- `KERNEL32!CloseHandle` at `0x180093ee8`
- `KERNEL32!CloseHandle` at `0x180093f16`
- `KERNEL32!CloseHandle` at `0x180093f39`
- `KERNEL32!CloseHandle` at `0x180093fa9`
- `KERNEL32!CloseHandle` at `0x1800940d6`
- `KERNEL32!CloseHandle` at `0x1800940e6`
- `KERNEL32!CloseHandle` at `0x1800940fb`
- `KERNEL32!CloseHandle` at `0x180094155`
- `KERNEL32!CloseHandle` at `0x18009416a`
- `KERNEL32!CloseHandle` at `0x1800942ac`
- `KERNEL32!CloseHandle` at `0x1800942bd`
- `KERNEL32!CloseHandle` at `0x1800942d2`
- `KERNEL32!LeaveCriticalSection` at `0x180092cd4`
- `KERNEL32!LeaveCriticalSection` at `0x1800930b3`
- `KERNEL32!LeaveCriticalSection` at `0x180093227`
- `KERNEL32!LeaveCriticalSection` at `0x18009359c`
- `KERNEL32!LeaveCriticalSection` at `0x180093870`
- `KERNEL32!LeaveCriticalSection` at `0x18009393c`
- `KERNEL32!LeaveCriticalSection` at `0x180093c7e`
- `KERNEL32!LeaveCriticalSection` at `0x180093e22`
- `KERNEL32!LeaveCriticalSection` at `0x18009423d`
- `KERNEL32!LeaveCriticalSection` at `0x180092cd4`
- `KERNEL32!LeaveCriticalSection` at `0x1800930b3`
- `KERNEL32!LeaveCriticalSection` at `0x180093227`
- `KERNEL32!LeaveCriticalSection` at `0x18009359c`
- `KERNEL32!LeaveCriticalSection` at `0x180093870`
- `KERNEL32!LeaveCriticalSection` at `0x18009393c`
- `KERNEL32!LeaveCriticalSection` at `0x180093c7e`
- `KERNEL32!LeaveCriticalSection` at `0x180093e22`
- `KERNEL32!LeaveCriticalSection` at `0x18009423d`
- `KERNEL32!GetTickCount` at `0x180092d2e`
- `KERNEL32!GetTickCount` at `0x180092d2e`
- `KERNEL32!GetLastError` at `0x18009315a`
- `KERNEL32!GetLastError` at `0x18009369a`
- `KERNEL32!GetLastError` at `0x180093bc2`
- `KERNEL32!GetLastError` at `0x18009315a`
- `KERNEL32!GetLastError` at `0x18009369a`
- `KERNEL32!GetLastError` at `0x180093bc2`
- `KERNEL32!EnterCriticalSection` at `0x1800929c1`
- `KERNEL32!EnterCriticalSection` at `0x180093abb`
- `KERNEL32!EnterCriticalSection` at `0x1800929c1`
- `KERNEL32!EnterCriticalSection` at `0x180093abb`
- `KERNEL32!GetCurrentThread` at `0x180092ac0`
- `KERNEL32!GetCurrentThread` at `0x180092bec`
- `KERNEL32!GetCurrentThread` at `0x180093455`
- `KERNEL32!GetCurrentThread` at `0x180093668`
- `KERNEL32!GetCurrentThread` at `0x180092ac0`
- `KERNEL32!GetCurrentThread` at `0x180092bec`
- `KERNEL32!GetCurrentThread` at `0x180093455`
- `KERNEL32!GetCurrentThread` at `0x180093668`
- `KERNEL32!GetCurrentProcess` at `0x180092a46`
- `KERNEL32!GetCurrentProcess` at `0x180092a46`
- `KERNEL32!GlobalFree` at `0x180093e58`
- `KERNEL32!GlobalFree` at `0x180093e58`
- `KERNEL32!SetEvent` at `0x180093da4`
- `KERNEL32!SetEvent` at `0x180093da4`
- `KERNEL32!CreateEventW` at `0x18009314b`
- `KERNEL32!CreateEventW` at `0x1800932a2`
- `KERNEL32!CreateEventW` at `0x18009314b`
- `KERNEL32!CreateEventW` at `0x1800932a2`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180093a34`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180093a67`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180093a34`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x180093a67`
- `KERNEL32!UpdateProcThreadAttribute` at `0x180093a9b`
- `KERNEL32!UpdateProcThreadAttribute` at `0x180093a9b`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180093c98`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x180093c98`
- `KERNEL32!TerminateProcess` at `0x180093d47`
- `KERNEL32!TerminateProcess` at `0x180093dbe`
- `KERNEL32!TerminateProcess` at `0x180093d47`
- `KERNEL32!TerminateProcess` at `0x180093dbe`
- `USER32!MsgWaitForMultipleObjects` at `0x18009400b`
- `USER32!MsgWaitForMultipleObjects` at `0x18009400b`
- `USER32!PeekMessageW` at `0x180094061`
- `USER32!PeekMessageW` at `0x180094061`
- `USER32!TranslateMessage` at `0x180094031`
- `USER32!TranslateMessage` at `0x180094031`
- `USER32!DispatchMessageW` at `0x180094041`
- `USER32!DispatchMessageW` at `0x180094041`

## string_xrefs

- `0x18009303d`: `Global\MSI`
- `0x180092ca6`: `Failed to create primary token while spawning Custom Action Server.`
- `0x1800931e6`: `Failed to create Custom Action Server wake event.`
- `0x1800932c9`: `Failed to create Custom Action Server event.`
- `0x1800936b4`: `Unable to grab user token for impersonation. Error = %d`
- `0x180093bea`: `Failed to create Custom Action Server. Error %d.`
- `0x180093c37`: `Created Custom Action Server with PID %d (0x%X).`
- `0x180093d14`: `Unable to set thread token in child process.`
- `0x180093f58`: `Failed to create Custom Action Server.`
- `0x18009409b`: `Custom Action Server never connected to service.`

## pseudocode

```c
__int64 __fastcall CMsiConfigurationManager::CreateCustomActionProxy(
        __int64 a1,
        int a2,
        int a3,
        WCHAR *a4,
        const WCHAR *a5,
        int a6,
        _OWORD *a7,
        int *a8,
        HANDLE *a9,
        DWORD *a10,
        char a11,
        char a12,
        HANDLE hExistingToken)
{
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE v17; // rax
  void *v18; // rcx
  HANDLE v19; // rcx
  HANDLE CurrentThread; // rax
  bool v21; // zf
  __int64 i; // rbx
  char v23; // al
  void (*v24)(void); // rax
  struct IMsiRecord *ServerPath; // rax
  int v26; // r8d
  struct IMsiRecord *v27; // rbx
  void *v28; // r15
  _BYTE *v29; // r9
  int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r14
  const wchar_t *v34; // rdx
  int v35; // r12d
  const wchar_t *v36; // rdx
  const wchar_t *v37; // rdx
  __int64 v38; // r8
  WCHAR *p_Name; // rax
  __int64 v40; // rcx
  WCHAR *v41; // rdx
  HANDLE v42; // rcx
  struct _RTL_CRITICAL_SECTION *v43; // rcx
  HANDLE EventW; // rax
  void **v45; // r12
  __int64 v46; // rdi
  PSID *v47; // rax
  PSID *v48; // rax
  HANDLE v49; // rax
  void *v50; // rcx
  __int64 v51; // rcx
  _DWORD *v52; // r12
  WCHAR *v53; // rdx
  struct _RTL_CRITICAL_SECTION *v54; // rcx
  bool v55; // cc
  HANDLE v57; // rax
  DWORD LastError; // eax
  bool v59; // al
  void *v60; // r8
  __int64 v61; // rcx
  LPCWSTR v62; // rax
  __int64 v63; // rcx
  int v64; // eax
  struct _RTL_CRITICAL_SECTION *v65; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *v66; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v67; // rdi
  WCHAR *v68; // rdi
  const WCHAR *v69; // rax
  DWORD v70; // eax
  LPPROC_THREAD_ATTRIBUTE_LIST v71; // rdi
  int v72; // edi
  struct _RTL_CRITICAL_SECTION *v73; // rcx
  CSIDAccess *v74; // rdi
  __int64 v75; // rsi
  DWORD v76; // eax
  const char *v77; // r9
  int v78; // ecx
  __int64 v79; // rcx
  __int64 v80; // rdx
  HANDLE *v81; // rcx
  _QWORD *v82; // rbx
  int *v83; // rax
  _OWORD *v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rdx
  __int64 v87; // rbx
  unsigned int pSid; // [rsp+50h] [rbp-B0h]
  unsigned int pSida; // [rsp+50h] [rbp-B0h]
  unsigned int pSidb; // [rsp+50h] [rbp-B0h]
  void *v91; // [rsp+58h] [rbp-A8h]
  char v92; // [rsp+60h] [rbp-A0h]
  void *v93; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  char v95; // [rsp+78h] [rbp-88h]
  char v96; // [rsp+79h] [rbp-87h]
  HANDLE phNewToken; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  int TokenInformation; // [rsp+90h] [rbp-70h] BYREF
  struct IMsiRecord *v100; // [rsp+98h] [rbp-68h] BYREF
  HANDLE Token; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR *v102; // [rsp+A8h] [rbp-58h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v104; // [rsp+B8h] [rbp-48h]
  LPSECURITY_ATTRIBUTES lpProcessAttributes; // [rsp+C0h] [rbp-40h]
  ULONG_PTR Size; // [rsp+C8h] [rbp-38h] BYREF
  _PROCESS_INFORMATION ProcessInformation; // [rsp+D0h] [rbp-30h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+E8h] [rbp-18h]
  struct tagMSG hMem; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpCurrentDirectory; // [rsp+120h] [rbp+20h]
  ULONG Seed; // [rsp+128h] [rbp+28h] BYREF
  __int64 v112; // [rsp+130h] [rbp+30h] BYREF
  HANDLE *v113; // [rsp+138h] [rbp+38h]
  DWORD *v114; // [rsp+140h] [rbp+40h]
  int *v115; // [rsp+148h] [rbp+48h]
  _OWORD *v116; // [rsp+150h] [rbp+50h]
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+158h] [rbp+58h] BYREF
  LPVOID lpEnvironment; // [rsp+170h] [rbp+70h]
  HANDLE pHandles[3]; // [rsp+178h] [rbp+78h] BYREF
  _STARTUPINFOW StartupInfo; // [rsp+190h] [rbp+90h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v121; // [rsp+1F8h] [rbp+F8h]
  struct _SID_IDENTIFIER_AUTHORITY ReturnLength[2]; // [rsp+200h] [rbp+100h] BYREF
  void *v123; // [rsp+210h] [rbp+110h] BYREF
  int v124; // [rsp+218h] [rbp+118h]
  _BYTE v125[80]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 *v126; // [rsp+270h] [rbp+170h]
  int v127; // [rsp+278h] [rbp+178h]
  _BYTE v128[528]; // [rsp+280h] [rbp+180h] BYREF
  LPWSTR lpCommandLine; // [rsp+490h] [rbp+390h] BYREF
  int v130; // [rsp+498h] [rbp+398h]
  _BYTE v131[528]; // [rsp+4A0h] [rbp+3A0h] BYREF
  void *v132[2]; // [rsp+6B0h] [rbp+5B0h] BYREF
  int v133; // [rsp+6C0h] [rbp+5C0h]
  char v134[16]; // [rsp+6C8h] [rbp+5C8h] BYREF
  int v135; // [rsp+6D8h] [rbp+5D8h]
  _BYTE v136[16]; // [rsp+6E0h] [rbp+5E0h] BYREF
  int v137; // [rsp+6F0h] [rbp+5F0h]
  char v138; // [rsp+6F8h] [rbp+5F8h] BYREF
  WCHAR Name; // [rsp+700h] [rbp+600h] BYREF
  __int128 v140; // [rsp+702h] [rbp+602h]
  _DWORD v141[7]; // [rsp+712h] [rbp+612h] BYREF
  char v142[80]; // [rsp+730h] [rbp+630h] BYREF

  v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
  lpCurrentDirectory = a5;
  v116 = a7;
  v115 = a8;
  v113 = a9;
  v114 = a10;
  v102 = a4;
  LODWORD(lpProcessAttributes) = a3;
  LODWORD(Token) = a2;
  Size = (ULONG_PTR)hExistingToken;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  v104 = (_QWORD *)(a1 + 128);
  if ( !*(_QWORD *)(a1 + 128)
    && (unsigned int)((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64))OLE32::CoCreateInstance)(
                       &CLSID_StdGlobalInterfaceTable,
                       0,
                       1,
                       &IID_IGlobalInterfaceTable,
                       a1 + 128) )
  {
    goto LABEL_33;
  }
  hObject = 0;
  if ( g_scServerContext != 2 || (unsigned int)(a2 - 2) > 3 )
  {
    v92 = 0;
    TokenHandle = 0;
    phNewToken = 0;
    if ( hExistingToken )
    {
      v18 = hExistingToken;
    }
    else
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 2u, 1, &TokenHandle) )
        goto LABEL_22;
      v18 = TokenHandle;
    }
    if ( !DuplicateTokenEx(v18, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, &phNewToken) )
    {
      v19 = 0;
      phNewToken = 0;
LABEL_23:
      if ( v19 )
      {
        if ( !(unsigned int)((__int64 (__fastcall *)(HANDLE, __int64, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, HANDLE *))ADVAPI32::CreateRestrictedToken)(
                              v19,
                              2,
                              0,
                              0,
                              0,
                              0,
                              0,
                              0,
                              &hObject) )
          hObject = 0;
        if ( phNewToken )
          CloseHandle(phNewToken);
      }
      if ( TokenHandle )
        CloseHandle(TokenHandle);
      goto LABEL_30;
    }
LABEL_22:
    v19 = phNewToken;
    goto LABEL_23;
  }
  CElevate::CElevate((CElevate *)&lpAttributeList, 1);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) && TokenHandle )
  {
    if ( !DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, &hObject) )
      hObject = 0;
    CloseHandle(TokenHandle);
  }
  CElevate::~CElevate((CElevate *)&lpAttributeList);
  phNewToken = 0;
  v17 = GetCurrentThread();
  if ( !OpenThreadToken(v17, 8u, 1, &phNewToken) )
  {
    CloseHandle(hObject);
    hObject = 0;
    goto LABEL_31;
  }
  v92 = 1;
  TokenInformation = 0;
  *(_DWORD *)ReturnLength[0].Value = 0;
  CElevate::CElevate((CElevate *)&lpAttributeList, 1);
  if ( !GetTokenInformation(phNewToken, TokenSessionId, &TokenInformation, 4u, (PDWORD)ReturnLength[0].Value)
    || !SetTokenInformation(hObject, TokenSessionId, &TokenInformation, 4u) )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  CloseHandle(phNewToken);
  CElevate::~CElevate((CElevate *)&lpAttributeList);
LABEL_30:
  if ( !hObject )
  {
LABEL_31:
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Failed to create primary token while spawning Custom Action Server.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v91);
LABEL_33:
    LeaveCriticalSection(v13);
    return 0;
  }
  v21 = g_dmDiagnosticMode == 0;
  *(_BYTE *)(a1 + 232) = 0;
  if ( !v21 )
    DebugString(
      10,
      0,
      0,
      "Generating random cookie.",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      "(NULL)",
      pSid,
      v91);
  Seed = GetTickCount();
  for ( i = 0; i != 16; ++i )
    *(_BYTE *)(i + a1 + 232) = RtlRandom(&Seed) % 0xFF;
  memset_0(v128, 0, 0x208u);
  v127 = 260;
  v126 = (unsigned __int16 *)v128;
  v93 = &MsiString::s_NullString;
  if ( (unsigned int)(a2 - 1) > 8 || (v23 = 1, (((_BYTE)a2 - 1) & 1) != 0) )
    v23 = 0;
  v95 = v23;
  v21 = v23 == 0;
  TokenHandle = &MsiString::s_NullString;
  v24 = *(void (**)(void))(MsiString::s_NullString + 16LL);
  if ( v21 )
  {
    v24();
    ServerPath = GetServerPath(*(struct IMsiServices **)(a1 + 16), 0, 0, (const struct IMsiString **)&TokenHandle);
    v26 = 1;
  }
  else
  {
    v24();
    ServerPath = GetServerPath(*(struct IMsiServices **)(a1 + 16), 0, 1, (const struct IMsiString **)&TokenHandle);
    v26 = 0;
  }
  v27 = ServerPath;
  MsiGetSystemDirectory(v126, 0x104u, v26);
  v28 = TokenHandle;
  v100 = v27;
  (*(void (__fastcall **)(void *))(*(_QWORD *)TokenHandle + 8LL))(TokenHandle);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v93 + 16LL))(v93);
  v93 = v28;
  (*(void (__fastcall **)(void *, const wchar_t *, void **))(*(_QWORD *)v28 + 144LL))(v28, L" -Embedding ", &v93);
  memset_0(v125, 0, 0x42u);
  v29 = v125;
  v124 = 33;
  v30 = 0;
  *(_OWORD *)&hMem.hwnd = *(_OWORD *)L"0123456789ABCDEF";
  v123 = v125;
  *(_OWORD *)&hMem.wParam = *(_OWORD *)L"89ABCDEF";
  LOWORD(hMem.time) = a0123456789abcd[16];
  while ( 1 )
  {
    v31 = (unsigned int)v30;
    v32 = 2 * v30++;
    *(_WORD *)&v29[2 * v32] = *((_WORD *)&hMem.hwnd + ((unsigned __int64)*(unsigned __int8 *)(v31 + a1 + 232) >> 4));
    *((_WORD *)v123 + v32 + 1) = *((_WORD *)&hMem.hwnd + (*(_BYTE *)(v31 + a1 + 232) & 0xF));
    if ( v30 >= 16 )
      break;
    v29 = v123;
  }
  *((_WORD *)v123 + 32) = 0;
  (*(void (__fastcall **)(void *, void *, void **))(*(_QWORD *)v93 + 144LL))(v93, v123, &v93);
  v33 = -1;
  if ( (unsigned int)(a2 - 8) <= 1 )
  {
    (*(void (__fastcall **)(void *, const wchar_t *, void **))(*(_QWORD *)v93 + 144LL))(v93, L" U", &v93);
  }
  else
  {
    if ( a11 )
    {
      v34 = L" C";
LABEL_84:
      MsiString::operator+=(&v93, v34);
      goto LABEL_86;
    }
    if ( (unsigned int)(a2 - 6) <= 1 )
    {
      v34 = L" A ";
      goto LABEL_84;
    }
    if ( !v92 )
      goto LABEL_86;
    if ( (unsigned int)(a2 - 2) <= 1 )
    {
      v35 = 0;
      v36 = L" M ";
      if ( !a12 )
        v36 = L" R ";
      MsiString::operator+=(&v93, v36);
    }
    else
    {
      (*(void (__fastcall **)(void *, const wchar_t *, void **))(*(_QWORD *)v93 + 144LL))(v93, L" E ", &v93);
      v35 = 0;
    }
    memset(&EventAttributes, 0, sizeof(EventAttributes));
    EventAttributes.nLength = 24;
    if ( !byte_180313E61 )
    {
      if ( (unsigned int)GetSecurityDescriptor(qword_180314FF0, (DWORD *)&dword_180310C94, 0, 0) )
        goto LABEL_77;
      byte_180313E61 = 1;
    }
    EventAttributes.lpSecurityDescriptor = qword_180314FF0;
    Name = 0;
    v37 = L"Global\\MSI";
    memset(v141, 0, 22);
    v38 = 20;
    p_Name = &Name;
    v40 = 2147483646;
    v140 = 0;
    do
    {
      if ( !v40 )
        break;
      if ( !*v37 )
        break;
      *p_Name++ = *v37++;
      --v40;
      --v38;
    }
    while ( v38 );
    v41 = p_Name - 1;
    if ( v38 )
      v41 = p_Name;
    *v41 = 0;
    if ( !v38 )
    {
      v42 = hObject;
      goto LABEL_68;
    }
    while ( v35 < 0xFFFF )
    {
      HIWORD(v141[0]) = *((_WORD *)&hMem.hwnd + ((v35 >> 12) & 0xF));
      LOWORD(v141[1]) = *((_WORD *)&hMem.hwnd + ((v35 >> 8) & 0xF));
      HIWORD(v141[1]) = *((_WORD *)&hMem.hwnd + ((v35 >> 4) & 0xF));
      v141[2] = *((unsigned __int16 *)&hMem.hwnd + (v35 & 0xF));
      CElevate::CElevate((CElevate *)&lpAttributeList, 1);
      v33 = (__int64)CreateEventW(&EventAttributes, 1, 0, &Name);
      *(_DWORD *)ReturnLength[0].Value = GetLastError();
      CElevate::~CElevate((CElevate *)&lpAttributeList);
      if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        if ( *(_DWORD *)ReturnLength[0].Value != 183 )
          break;
        CloseHandle((HANDLE)v33);
        v33 = 0;
      }
      ++v35;
    }
    (*(void (__fastcall **)(void *, WCHAR *, void **))(*(_QWORD *)v93 + 144LL))(v93, &Name, &v93);
    if ( ((v33 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
LABEL_77:
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          "Failed to create Custom Action Server wake event.",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          pSid,
          v91);
      CloseHandle(hObject);
      LeaveCriticalSection(v13);
      if ( v124 > 33 )
        operator delete(v123);
      if ( v27 )
        (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v27 + 16LL))(v27);
      goto LABEL_115;
    }
  }
LABEL_86:
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 144) = EventW;
  if ( !EventW )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Failed to create Custom Action Server event.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSid,
        v91);
    CloseHandle(hObject);
    if ( v33 == -1 )
    {
LABEL_69:
      v43 = v13;
LABEL_70:
      LeaveCriticalSection(v43);
      goto LABEL_114;
    }
    v42 = (HANDLE)v33;
LABEL_68:
    CloseHandle(v42);
    goto LABEL_69;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, 0x70u);
  StartupInfo.cb = 112;
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  v45 = v132;
  v46 = 3;
  do
  {
    CSIDAccess::CSIDAccess((CSIDAccess *)v45);
    v45 += 3;
    --v46;
  }
  while ( v46 );
  *(_WORD *)&ReturnLength[0].Value[4] = 1280;
  *(_DWORD *)ReturnLength[0].Value = 0;
  v47 = (PSID *)CSIDPointer::operator&(v132);
  if ( !AllocateAndInitializeSid(ReturnLength, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, v47) )
    goto LABEL_109;
  v48 = (PSID *)CSIDPointer::operator&(v134);
  if ( !AllocateAndInitializeSid(ReturnLength, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, v48) )
    goto LABEL_109;
  TokenInformation = 2;
  v133 = 0x1FFFFF;
  v135 = 0x1FFFFF;
  TokenHandle = 0;
  if ( Size )
  {
    v50 = (void *)Size;
  }
  else
  {
    v49 = GetCurrentThread();
    if ( OpenThreadToken(v49, 8u, 1, &TokenHandle) )
    {
      v50 = TokenHandle;
    }
    else
    {
      v50 = 0;
      TokenHandle = 0;
    }
    if ( !v50 )
      goto LABEL_106;
  }
  if ( !GetUserSID(v50, v142) )
  {
    CSIDPointer::operator=(v136, v142);
    TokenInformation = 3;
    v136[8] = 0;
    v137 = v92 != 0 ? 4096 : 1310159;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
LABEL_106:
  v51 = *(_QWORD *)(a1 + 128);
  v52 = (_DWORD *)(a1 + 268);
  v53 = v102;
  *(_DWORD *)(a1 + 248) = (_DWORD)Token;
  if ( (*(unsigned int (__fastcall **)(__int64, WCHAR *, GUID *, __int64))(*(_QWORD *)v51 + 24LL))(
         v51,
         v53,
         &IID_IMsiRemoteAPI,
         a1 + 268) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Unable to register RemoteAPI in GIT for registration.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSida,
        v91);
LABEL_109:
    CloseHandle(hObject);
    if ( v33 != -1 )
      CloseHandle((HANDLE)v33);
LABEL_111:
    v54 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
LABEL_112:
    LeaveCriticalSection(v54);
LABEL_113:
    `vector destructor iterator'(v132, 0x18u, 3u, (void (*)(void *))CSIDAccess::~CSIDAccess);
LABEL_114:
    CTempBuffer<unsigned short,33>::~CTempBuffer<unsigned short,33>(&v123);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
LABEL_115:
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v93 + 16LL))(v93);
    v55 = v127 <= 260;
LABEL_116:
    if ( !v55 )
      operator delete(v126);
    return 0;
  }
  *(_DWORD *)(a1 + 264) = (_DWORD)lpProcessAttributes;
  *(_DWORD *)(a1 + 276) = a6;
  Token = (HANDLE)-1LL;
  if ( Size )
  {
    v59 = 0;
  }
  else
  {
    v57 = GetCurrentThread();
    if ( !OpenThreadToken(v57, 0xF01FFu, 1, &Token) )
    {
      LastError = GetLastError();
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          "Unable to grab user token for impersonation. Error = %d",
          (const char *)LastError,
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          "(NULL)",
          pSida,
          v91);
      CloseHandle(hObject);
      if ( v33 != -1 )
        CloseHandle((HANDLE)v33);
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v104 + 32LL))(*v104, (unsigned int)*v52);
      *v52 = 0;
      goto LABEL_111;
    }
    v59 = IsLocalSystemToken(Token);
  }
  *(_BYTE *)(a1 + 284) = v59;
  CElevate::CElevate((CElevate *)&phNewToken, 1);
  CSecurityDescription::CSecurityDescription(
    (CSecurityDescription *)&hMem,
    v132[0],
    v60,
    (struct CSIDAccess *)v132,
    TokenInformation);
  v61 = 0;
  if ( !BYTE1(hMem.lParam) )
  {
    if ( Token != (HANDLE)-1LL )
      CloseHandle(Token);
    CloseHandle(hObject);
    if ( v33 != -1 )
      CloseHandle((HANDLE)v33);
    v63 = *(_QWORD *)(a1 + 128);
    goto LABEL_143;
  }
  v102 = 0;
  v96 = 0;
  if ( a11 )
  {
    v62 = lpCurrentDirectory;
LABEL_136:
    v102 = (WCHAR *)v62;
    goto LABEL_145;
  }
  if ( v92 )
  {
    if ( MsiUIMessageContext::GetSystemEnvironment((MsiUIMessageContext *)&g_MessageContext) )
    {
      v102 = *(WCHAR **)MsiUIMessageContext::GetSystemEnvironment((MsiUIMessageContext *)&g_MessageContext);
      goto LABEL_145;
    }
  }
  else if ( qword_180313738 )
  {
    v62 = *(LPCWSTR *)qword_180313738;
    goto LABEL_136;
  }
  LOBYTE(v61) = 1;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, WCHAR **))NTDLL::RtlCreateEnvironment)(v61, &v102) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Unable to duplicate environment block for child process.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSida,
        v91);
    CloseHandle(hObject);
    if ( v33 != -1 )
      CloseHandle((HANDLE)v33);
    v63 = *v104;
LABEL_143:
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63 + 32LL))(v63, (unsigned int)*v52);
    *v52 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    CSecurityDescription::~CSecurityDescription((CSecurityDescription *)&hMem);
    CElevate::~CElevate((CElevate *)&phNewToken);
    goto LABEL_113;
  }
  v96 = 1;
LABEL_145:
  memset_0(v131, 0, 0x208u);
  lpCommandLine = (LPWSTR)v131;
  v130 = 260;
  v64 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v93 + 56LL))(v93);
  CTempBuffer<unsigned short,260>::SetSize(&lpCommandLine, (unsigned int)(v64 + 1));
  if ( !lpCommandLine )
  {
    CloseHandle(hObject);
    if ( v33 != -1 )
      CloseHandle((HANDLE)v33);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v104 + 32LL))(*v104, (unsigned int)*v52);
    v65 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
LABEL_149:
    *v52 = 0;
    LeaveCriticalSection(v65);
    if ( v130 > 260 )
      operator delete(lpCommandLine);
    CSecurityDescription::~CSecurityDescription((CSecurityDescription *)&hMem);
    CElevate::~CElevate((CElevate *)&phNewToken);
    `vector destructor iterator'(v132, 0x18u, 3u, (void (*)(void *))CSIDAccess::~CSIDAccess);
    CTempBuffer<unsigned short,33>::~CTempBuffer<unsigned short,33>(&v123);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v93 + 16LL))(v93);
    v55 = v127 <= 260;
    goto LABEL_116;
  }
  (*(void (__fastcall **)(void *, LPWSTR, _QWORD))(*(_QWORD *)v93 + 88LL))(v93, lpCommandLine, (unsigned int)(v130 - 1));
  LOWORD(TokenInformation) = -31132;
  lpAttributeList = 0;
  if ( g_wArchitecture == 12 && g_w64BitCustomActionPlatform == 9 && v95 )
  {
    Size = 0;
    InitializeProcThreadAttributeList(0, 1u, 0, &Size);
    v66 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)operator new(Size);
    lpAttributeList = v66;
    v67 = v66;
    if ( !v66
      || !InitializeProcThreadAttributeList(v66, 1u, 0, &Size)
      || !UpdateProcThreadAttribute(v67, 0, 0x20019u, &TokenInformation, 2u, 0, 0) )
    {
      CloseHandle(hObject);
      if ( v67 )
        operator delete(v67);
      goto LABEL_163;
    }
    v121 = v67;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  lpCurrentDirectory = v126;
  lpEnvironment = v102;
  if ( BYTE1(hMem.lParam) )
    lpProcessAttributes = (LPSECURITY_ATTRIBUTES)((unsigned __int64)&hMem & -(__int64)(*(_QWORD *)&hMem.message != 0));
  else
    lpProcessAttributes = 0;
  v68 = lpCommandLine;
  v69 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v28 + 80LL))(v28);
  LODWORD(lpProcessAttributes) = CreateProcessAsUserW(
                                   hObject,
                                   v69,
                                   v68,
                                   lpProcessAttributes,
                                   0,
                                   0,
                                   0x80420u,
                                   lpEnvironment,
                                   lpCurrentDirectory,
                                   &StartupInfo,
                                   &ProcessInformation);
  if ( (_DWORD)lpProcessAttributes )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Created Custom Action Server with PID %d (0x%X).",
        (const unsigned __int16 *)ProcessInformation.dwProcessId,
        (const unsigned __int16 *)ProcessInformation.dwProcessId,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    *(_DWORD *)(a1 + 280) = ProcessInformation.dwProcessId;
  }
  else
  {
    v70 = GetLastError();
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Failed to create Custom Action Server. Error %d.",
        (const unsigned __int16 *)v70,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v71 = lpAttributeList;
  if ( lpAttributeList )
  {
    DeleteProcThreadAttributeList(lpAttributeList);
    operator delete(v71);
  }
  if ( v96 )
  {
    ((void (__fastcall *)(WCHAR *))NTDLL::RtlDestroyEnvironment)(v102);
    v102 = 0;
  }
  v72 = (int)lpProcessAttributes;
  if ( (_DWORD)lpProcessAttributes )
  {
    if ( v92 )
    {
      if ( Token != (HANDLE)-1LL )
      {
        if ( !SetThreadToken(&ProcessInformation.hThread, Token) )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              10,
              0,
              0,
              "Unable to set thread token in child process.",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              "(NULL)",
              pSidb,
              v91);
          TerminateProcess(ProcessInformation.hProcess, 0);
          CloseHandle(ProcessInformation.hProcess);
          CloseHandle(hObject);
          CloseHandle(Token);
LABEL_163:
          if ( v33 != -1 )
            CloseHandle((HANDLE)v33);
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v104 + 32LL))(*v104, (unsigned int)*v52);
          v65 = lpCriticalSection;
          goto LABEL_149;
        }
        CloseHandle(Token);
        Token = (HANDLE)-1LL;
      }
      if ( !SetEvent((HANDLE)v33) )
      {
        TerminateProcess(ProcessInformation.hProcess, 0);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(hObject);
        if ( v33 != -1 )
          CloseHandle((HANDLE)v33);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v104 + 32LL))(*v104, (unsigned int)*v52);
        v73 = lpCriticalSection;
        *v52 = 0;
        LeaveCriticalSection(v73);
        if ( v130 > 260 )
          operator delete(lpCommandLine);
        if ( LOBYTE(hMem.lParam) && *(_QWORD *)&hMem.message )
        {
          GlobalFree(*(HGLOBAL *)&hMem.message);
          *(_QWORD *)&hMem.message = 0;
        }
        CElevate::~CElevate((CElevate *)&phNewToken);
        v74 = (CSIDAccess *)&v138;
        v75 = 3;
        do
        {
          v74 = (CSIDAccess *)((char *)v74 - 24);
          CSIDAccess::~CSIDAccess(v74);
          --v75;
        }
        while ( v75 );
        if ( v124 > 33 )
          operator delete(v123);
        if ( v27 )
          (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v27 + 16LL))(v27);
        goto LABEL_115;
      }
    }
    CloseHandle(ProcessInformation.hThread);
  }
  if ( v130 > 260 )
    operator delete(lpCommandLine);
  if ( Token != (HANDLE)-1LL )
    CloseHandle(Token);
  CSecurityDescription::~CSecurityDescription((CSecurityDescription *)&hMem);
  CElevate::~CElevate((CElevate *)&phNewToken);
  CloseHandle(hObject);
  if ( !v72 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Failed to create Custom Action Server.",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        pSidb,
        v91);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v104 + 32LL))(*v104, (unsigned int)*v52);
    *v52 = 0;
    if ( v33 != -1 )
      CloseHandle((HANDLE)v33);
    v54 = lpCriticalSection;
    goto LABEL_112;
  }
  `vector destructor iterator'(v132, 0x18u, 3u, (void (*)(void *))CSIDAccess::~CSIDAccess);
  pHandles[0] = ProcessInformation.hProcess;
  pHandles[1] = *(HANDLE *)(a1 + 144);
  while ( 1 )
  {
    while ( 1 )
    {
      v76 = MsgWaitForMultipleObjects(2u, pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
      if ( v76 != 2 )
        break;
      memset(&hMem, 0, sizeof(hMem));
      while ( PeekMessageW(&hMem, 0, 0, 0, 1u) )
      {
        TranslateMessage(&hMem);
        DispatchMessageW(&hMem);
      }
    }
    if ( v76 == 1 )
      break;
    switch ( v76 )
    {
      case 0u:
        if ( g_dmDiagnosticMode )
        {
          v77 = "CA Server Process has terminated.";
          v78 = 9;
LABEL_223:
          DebugString(v78, 0, 0, v77, "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", "(NULL)", pSidb, v91);
        }
LABEL_224:
        CloseHandle(*(HANDLE *)(a1 + 144));
        CloseHandle(ProcessInformation.hProcess);
        if ( v33 != -1 )
          CloseHandle((HANDLE)v33);
        v79 = *(_QWORD *)(a1 + 128);
        v80 = (unsigned int)*v52;
        *(_QWORD *)(a1 + 144) = 0;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 32LL))(v79, v80);
        v43 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
        *v52 = 0;
        goto LABEL_70;
      case 0xFFFFFFFF:
        goto LABEL_224;
      case 0x102u:
        if ( g_dmDiagnosticMode )
        {
          v77 = "Custom Action Server never connected to service.";
          v78 = 10;
          goto LABEL_223;
        }
        goto LABEL_224;
    }
  }
  CloseHandle(*(HANDLE *)(a1 + 144));
  if ( v33 != -1 )
    CloseHandle((HANDLE)v33);
  v81 = v113;
  *(_QWORD *)(a1 + 144) = 0;
  if ( v81 )
    *v81 = ProcessInformation.hProcess;
  if ( v114 )
    *v114 = ProcessInformation.dwProcessId;
  v82 = (_QWORD *)(a1 + 128);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 128) + 32LL))(*(_QWORD *)(a1 + 128), (unsigned int)*v52);
  v83 = v115;
  *v52 = 0;
  if ( v83 )
  {
    v84 = v116;
    if ( v116 )
    {
      if ( *v83 >= 16 )
      {
        *v83 = 16;
        *v84 = *(_OWORD *)(a1 + 232);
      }
    }
  }
  v85 = *v82;
  v86 = *(unsigned int *)(a1 + 272);
  v112 = 0;
  (*(void (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v85 + 40LL))(
    v85,
    v86,
    &IID_IMsiCustomAction,
    &v112);
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v82 + 32LL))(*v82, *(unsigned int *)(a1 + 272));
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v82 + 16LL))(*v82);
  *v82 = 0;
  *(_DWORD *)(a1 + 272) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  v87 = v112;
  CTempBuffer<unsigned short,33>::~CTempBuffer<unsigned short,33>(&v123);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v28 + 16LL))(v28);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v93 + 16LL))(v93);
  if ( v127 > 260 )
    operator delete(v126);
  return v87;
}

```

## disassembly

```asm
0x180092930  mov     [rsp-8+arg_8], rbx
0x180092935  push    rbp
0x180092936  push    rsi
0x180092937  push    rdi
0x180092938  push    r12
0x18009293a  push    r13
0x18009293c  push    r14
0x18009293e  push    r15
0x180092940  lea     rbp, [rsp-690h]
0x180092948  sub     rsp, 790h
0x18009294f  mov     rax, cs:__security_cookie
0x180092956  xor     rax, rsp
0x180092959  mov     [rbp+6C0h+var_40], rax
0x180092960  mov     rax, [rbp+6C0h+arg_20]
0x180092967  lea     rdi, [rcx+98h]
0x18009296e  mov     rbx, [rbp+6C0h+hExistingToken]
0x180092975  mov     r13, rcx
0x180092978  mov     [rbp+6C0h+lpCurrentDirectory], rax
0x18009297c  mov     rcx, rdi; lpCriticalSection
0x18009297f  mov     rax, [rbp+6C0h+arg_30]
0x180092986  mov     r12d, edx
0x180092989  mov     [rbp+6C0h+var_670], rax
0x18009298d  mov     rax, [rbp+6C0h+arg_38]
0x180092994  mov     [rbp+6C0h+var_678], rax
0x180092998  mov     rax, [rbp+6C0h+arg_40]
0x18009299f  mov     [rbp+6C0h+var_688], rax
0x1800929a3  mov     rax, [rbp+6C0h+arg_48]
0x1800929aa  mov     [rbp+6C0h+var_680], rax
0x1800929ae  mov     [rbp+6C0h+var_718], r9
0x1800929b2  mov     dword ptr [rbp+6C0h+lpProcessAttributes], r8d
0x1800929b6  mov     dword ptr [rbp+6C0h+Token], edx
0x1800929b9  mov     [rbp+6C0h+Size], rbx
0x1800929bd  mov     [rbp+6C0h+lpCriticalSection], rdi
0x1800929c1  call    cs:__imp_EnterCriticalSection
0x1800929c8  nop     dword ptr [rax+rax+00h]
0x1800929cd  lea     rax, [r13+80h]
0x1800929d4  xor     r14d, r14d
0x1800929d7  mov     r15d, 1
0x1800929dd  mov     [rbp+6C0h+var_708], rax
0x1800929e1  cmp     [rax], r14
0x1800929e4  jnz     short loc_180092A12
0x1800929e6  mov     qword ptr [rsp+7C0h+TokenType], rax
0x1800929eb  lea     r9, IID_IGlobalInterfaceTable
0x1800929f2  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800929f9  lea     rcx, CLSID_StdGlobalInterfaceTable
0x180092a00  mov     r8d, r15d
0x180092a03  xor     edx, edx
0x180092a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a0a  test    eax, eax
0x180092a0c  jnz     loc_180092CD1
0x180092a12  mov     esi, 2
0x180092a17  mov     [rsp+7C0h+hObject], r14
0x180092a1c  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x180092a22  jnz     loc_180092BA5
0x180092a28  lea     eax, [r12-2]
0x180092a2d  cmp     eax, 3
0x180092a30  ja      loc_180092BA5
0x180092a36  mov     dl, r15b; bool
0x180092a39  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x180092a3d  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180092a42  mov     [rbp+6C0h+TokenHandle], r14
0x180092a46  call    cs:__imp_GetCurrentProcess
0x180092a4d  nop     dword ptr [rax+rax+00h]
0x180092a52  lea     r8, [rbp+6C0h+TokenHandle]; TokenHandle
0x180092a56  mov     edx, esi; DesiredAccess
0x180092a58  mov     rcx, rax; ProcessHandle
0x180092a5b  call    cs:__imp_OpenProcessToken
0x180092a62  nop     dword ptr [rax+rax+00h]
0x180092a67  test    eax, eax
0x180092a69  jz      short loc_180092AB3
0x180092a6b  mov     rcx, [rbp+6C0h+TokenHandle]; hExistingToken
0x180092a6f  test    rcx, rcx
0x180092a72  jz      short loc_180092AB3
0x180092a74  lea     rax, [rsp+7C0h+hObject]
0x180092a79  xor     r9d, r9d; ImpersonationLevel
0x180092a7c  mov     [rsp+7C0h+phNewToken], rax; phNewToken
0x180092a81  xor     r8d, r8d; lpTokenAttributes
0x180092a84  mov     edx, 2000000h; dwDesiredAccess
0x180092a89  mov     [rsp+7C0h+TokenType], r15d; TokenType
0x180092a8e  call    cs:__imp_DuplicateTokenEx
0x180092a95  nop     dword ptr [rax+rax+00h]
0x180092a9a  test    eax, eax
0x180092a9c  jnz     short loc_180092AA3
0x180092a9e  mov     [rsp+7C0h+hObject], r14
0x180092aa3  mov     rcx, [rbp+6C0h+TokenHandle]; hObject
0x180092aa7  call    cs:__imp_CloseHandle
0x180092aae  nop     dword ptr [rax+rax+00h]
0x180092ab3  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x180092ab7  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180092abc  mov     [rbp+6C0h+var_740], r14
0x180092ac0  call    cs:__imp_GetCurrentThread
0x180092ac7  nop     dword ptr [rax+rax+00h]
0x180092acc  lea     r9, [rbp+6C0h+var_740]; TokenHandle
0x180092ad0  mov     r8d, r15d; OpenAsSelf
0x180092ad3  mov     rcx, rax; ThreadHandle
0x180092ad6  mov     edx, 8; DesiredAccess
0x180092adb  call    cs:__imp_OpenThreadToken
0x180092ae2  nop     dword ptr [rax+rax+00h]
0x180092ae7  test    eax, eax
0x180092ae9  jnz     short loc_180092B06
0x180092aeb  mov     rcx, [rsp+7C0h+hObject]; hObject
0x180092af0  call    cs:__imp_CloseHandle
0x180092af7  nop     dword ptr [rax+rax+00h]
0x180092afc  mov     [rsp+7C0h+hObject], r14
0x180092b01  jmp     loc_180092C8F
0x180092b06  mov     dl, r15b; bool
0x180092b09  mov     [rsp+7C0h+var_760], r15b
0x180092b0e  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x180092b12  mov     [rbp+6C0h+TokenInformation], r14d
0x180092b16  mov     [rbp+6C0h+ReturnLength], r14d
0x180092b1d  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x180092b22  mov     rcx, [rbp+6C0h+var_740]; TokenHandle
0x180092b26  lea     rax, [rbp+6C0h+ReturnLength]
0x180092b2d  mov     ebx, 4
0x180092b32  mov     qword ptr [rsp+7C0h+TokenType], rax; ReturnLength
0x180092b37  mov     r9d, ebx; TokenInformationLength
0x180092b3a  lea     r8, [rbp+6C0h+TokenInformation]; TokenInformation
0x180092b3e  lea     esi, [rbx+8]
0x180092b41  mov     edx, esi; TokenInformationClass
0x180092b43  call    cs:__imp_GetTokenInformation
0x180092b4a  nop     dword ptr [rax+rax+00h]
0x180092b4f  test    eax, eax
0x180092b51  jz      short loc_180092B71
0x180092b53  mov     rcx, [rsp+7C0h+hObject]; TokenHandle
0x180092b58  lea     r8, [rbp+6C0h+TokenInformation]; TokenInformation
0x180092b5c  mov     r9d, ebx; TokenInformationLength
0x180092b5f  mov     edx, esi; TokenInformationClass
0x180092b61  call    cs:__imp_SetTokenInformation
0x180092b68  nop     dword ptr [rax+rax+00h]
0x180092b6d  test    eax, eax
0x180092b6f  jnz     short loc_180092B87
0x180092b71  mov     rcx, [rsp+7C0h+hObject]; hObject
0x180092b76  call    cs:__imp_CloseHandle
0x180092b7d  nop     dword ptr [rax+rax+00h]
0x180092b82  mov     [rsp+7C0h+hObject], r14
0x180092b87  mov     rcx, [rbp+6C0h+var_740]; hObject
0x180092b8b  call    cs:__imp_CloseHandle
0x180092b92  nop     dword ptr [rax+rax+00h]
0x180092b97  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x180092b9b  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x180092ba0  jmp     loc_180092C88
0x180092ba5  mov     [rsp+7C0h+var_760], r14b
0x180092baa  mov     [rbp+6C0h+TokenHandle], r14
0x180092bae  mov     [rbp+6C0h+var_740], r14
0x180092bb2  test    rbx, rbx
0x180092bb5  jz      short loc_180092BEC
0x180092bb7  mov     rcx, rbx; hExistingToken
0x180092bba  lea     rax, [rbp+6C0h+var_740]
0x180092bbe  xor     r9d, r9d; ImpersonationLevel
0x180092bc1  mov     [rsp+7C0h+phNewToken], rax; phNewToken
0x180092bc6  xor     r8d, r8d; lpTokenAttributes
0x180092bc9  mov     edx, 2000000h; dwDesiredAccess
0x180092bce  mov     [rsp+7C0h+TokenType], r15d; TokenType
0x180092bd3  call    cs:__imp_DuplicateTokenEx
0x180092bda  nop     dword ptr [rax+rax+00h]
0x180092bdf  test    eax, eax
0x180092be1  jnz     short loc_180092C1A
0x180092be3  mov     rcx, r14
0x180092be6  mov     [rbp+6C0h+var_740], rcx
0x180092bea  jmp     short loc_180092C1E
0x180092bec  call    cs:__imp_GetCurrentThread
0x180092bf3  nop     dword ptr [rax+rax+00h]
0x180092bf8  lea     r9, [rbp+6C0h+TokenHandle]; TokenHandle
0x180092bfc  mov     r8d, r15d; OpenAsSelf
0x180092bff  mov     rcx, rax; ThreadHandle
0x180092c02  mov     edx, esi; DesiredAccess
0x180092c04  call    cs:__imp_OpenThreadToken
0x180092c0b  nop     dword ptr [rax+rax+00h]
0x180092c10  test    eax, eax
0x180092c12  jz      short loc_180092C1A
0x180092c14  mov     rcx, [rbp+6C0h+TokenHandle]
0x180092c18  jmp     short loc_180092BBA
0x180092c1a  mov     rcx, [rbp+6C0h+var_740]
0x180092c1e  test    rcx, rcx
0x180092c21  jz      short loc_180092C73
0x180092c23  lea     rax, [rsp+7C0h+hObject]
0x180092c28  xor     r9d, r9d
0x180092c2b  mov     qword ptr [rsp+7C0h+nSubAuthority6], rax
0x180092c30  xor     r8d, r8d
0x180092c33  mov     rax, cs:?CreateRestrictedToken@ADVAPI32@@3P6AHPEAXKKPEAU_SID_AND_ATTRIBUTES@@KPEAU_LUID_AND_ATTRIBUTES@@K1PEAPEAX@ZEA; int (*ADVAPI32::CreateRestrictedToken)(void *,ulong,ulong,_SID_AND_ATTRIBUTES *,ulong,_LUID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,void * *)
0x180092c3a  mov     edx, esi
0x180092c3c  mov     qword ptr [rsp+7C0h+nSubAuthority5], r14
0x180092c41  mov     [rsp+7C0h+nSubAuthority4], r14d
0x180092c46  mov     [rsp+7C0h+phNewToken], r14
0x180092c4b  mov     [rsp+7C0h+TokenType], r14d
0x180092c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c55  test    eax, eax
0x180092c57  jnz     short loc_180092C5E
0x180092c59  mov     [rsp+7C0h+hObject], r14
0x180092c5e  mov     rcx, [rbp+6C0h+var_740]; hObject
0x180092c62  test    rcx, rcx
0x180092c65  jz      short loc_180092C73
0x180092c67  call    cs:__imp_CloseHandle
0x180092c6e  nop     dword ptr [rax+rax+00h]
0x180092c73  mov     rcx, [rbp+6C0h+TokenHandle]; hObject
0x180092c77  test    rcx, rcx
0x180092c7a  jz      short loc_180092C88
0x180092c7c  call    cs:__imp_CloseHandle
0x180092c83  nop     dword ptr [rax+rax+00h]
0x180092c88  cmp     [rsp+7C0h+hObject], r14
0x180092c8d  jnz     short loc_180092CE5
0x180092c8f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180092c96  jz      short loc_180092CD1
0x180092c98  lea     rsi, aNull_0; "(NULL)"
0x180092c9f  xor     edx, edx; unsigned __int16
0x180092ca1  mov     qword ptr [rsp+7C0h+nSubAuthority7], rsi; char *
0x180092ca6  lea     r9, aFailedToCreate_5; "Failed to create primary token while sp"...
0x180092cad  mov     qword ptr [rsp+7C0h+nSubAuthority6], rsi; char *
0x180092cb2  xor     r8d, r8d; int
0x180092cb5  mov     qword ptr [rsp+7C0h+nSubAuthority5], rsi; char *
0x180092cba  mov     qword ptr [rsp+7C0h+nSubAuthority4], rsi; char *
0x180092cbf  lea     ecx, [rdx+0Ah]; int
0x180092cc2  mov     [rsp+7C0h+phNewToken], rsi; char *
0x180092cc7  mov     qword ptr [rsp+7C0h+TokenType], rsi; char *
0x180092ccc  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180092cd1  mov     rcx, rdi; lpCriticalSection
0x180092cd4  call    cs:__imp_LeaveCriticalSection
0x180092cdb  nop     dword ptr [rax+rax+00h]
0x180092ce0  jmp     loc_180093612
0x180092ce5  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180092cec  lea     rsi, aNull_0; "(NULL)"
0x180092cf3  mov     [r13+0E8h], r14b
0x180092cfa  jz      short loc_180092D2E
0x180092cfc  mov     qword ptr [rsp+7C0h+nSubAuthority7], rsi; char *
0x180092d01  lea     r9, aGeneratingRand; "Generating random cookie."
0x180092d08  mov     qword ptr [rsp+7C0h+nSubAuthority6], rsi; char *
0x180092d0d  xor     edx, edx; unsigned __int16
0x180092d0f  mov     qword ptr [rsp+7C0h+nSubAuthority5], rsi; char *
0x180092d14  xor     r8d, r8d; int
0x180092d17  mov     qword ptr [rsp+7C0h+nSubAuthority4], rsi; char *
0x180092d1c  mov     [rsp+7C0h+phNewToken], rsi; char *
0x180092d21  lea     ecx, [rdx+0Ah]; int
0x180092d24  mov     qword ptr [rsp+7C0h+TokenType], rsi; char *
0x180092d29  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x180092d2e  call    cs:__imp_GetTickCount
0x180092d35  nop     dword ptr [rax+rax+00h]
0x180092d3a  mov     [rbp+6C0h+Seed], eax
0x180092d3d  mov     rbx, r14
0x180092d40  lea     rcx, [rbp+6C0h+Seed]; Seed
0x180092d44  call    cs:__imp_RtlRandom
0x180092d4b  nop     dword ptr [rax+rax+00h]
0x180092d50  mov     r8d, eax
0x180092d53  mov     eax, 80808081h
0x180092d58  mul     r8d
0x180092d5b  shr     edx, 7
0x180092d5e  imul    ecx, edx, 0FFh
0x180092d64  sub     r8d, ecx
0x180092d67  mov     [rbx+r13+0E8h], r8b
0x180092d6f  add     rbx, r15
0x180092d72  cmp     rbx, 10h
0x180092d76  jnz     short loc_180092D40
0x180092d78  xor     edx, edx; Val
0x180092d7a  lea     rcx, [rbp+6C0h+var_540]; void *
0x180092d81  mov     r8d, 208h; Size
0x180092d87  call    memset_0
0x180092d8c  lea     rax, [rbp+6C0h+var_540]
0x180092d93  mov     [rbp+6C0h+var_548], 104h
0x180092d9d  mov     [rbp+6C0h+var_550], rax
0x180092da4  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180092dab  lea     eax, [r12-1]
0x180092db0  mov     [rsp+7C0h+var_758], rcx
0x180092db5  cmp     eax, 8
0x180092db8  ja      short loc_180092DC2
0x180092dba  test    r15b, al
0x180092dbd  mov     al, r15b
0x180092dc0  jz      short loc_180092DC5
0x180092dc2  mov     al, r14b
0x180092dc5  mov     [rsp+7C0h+var_748], al
0x180092dc9  test    al, al
0x180092dcb  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180092dd2  mov     [rbp+6C0h+TokenHandle], rcx
0x180092dd6  mov     rax, [rax+10h]
0x180092dda  jz      short loc_180092DF8
0x180092ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092de1  mov     rcx, [r13+10h]; struct IMsiServices *
0x180092de5  lea     r9, [rbp+6C0h+TokenHandle]; struct IMsiString **
0x180092de9  mov     r8b, r15b; bool
0x180092dec  xor     edx, edx; bool
0x180092dee  call    ?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z; GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)
0x180092df3  xor     r8d, r8d
0x180092df6  jmp     short loc_180092E12
0x180092df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092dfd  mov     rcx, [r13+10h]; struct IMsiServices *
0x180092e01  lea     r9, [rbp+6C0h+TokenHandle]; struct IMsiString **
0x180092e05  xor     r8d, r8d; bool
0x180092e08  xor     edx, edx; bool
0x180092e0a  call    ?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z; GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)
0x180092e0f  mov     r8d, r15d; int
0x180092e12  mov     rcx, [rbp+6C0h+var_550]; unsigned __int16 *
0x180092e19  mov     edx, 104h; unsigned int
0x180092e1e  mov     rbx, rax
0x180092e21  call    ?MsiGetSystemDirectory@@YAIPEAGIH@Z; MsiGetSystemDirectory(ushort *,uint,int)
0x180092e26  mov     r15, [rbp+6C0h+TokenHandle]
0x180092e2a  mov     rcx, r15
0x180092e2d  mov     [rbp+6C0h+var_728], rbx
0x180092e31  mov     rax, [r15]
0x180092e34  mov     rax, [rax+8]
0x180092e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092e3d  mov     rcx, [rsp+7C0h+var_758]
0x180092e42  mov     rax, [rcx]
  ... truncated ...
```
