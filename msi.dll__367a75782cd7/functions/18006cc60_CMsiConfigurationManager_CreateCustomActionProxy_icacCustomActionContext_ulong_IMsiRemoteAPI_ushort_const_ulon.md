# CMsiConfigurationManager::CreateCustomActionProxy(icacCustomActionContext,ulong,IMsiRemoteAPI *,ushort const *,ulong,uchar *,int *,void * *,ulong *,bool,bool,void *)

- ea: `0x18006cc60`
- end: `0x18006e401`
- name: `?CreateCustomActionProxy@CMsiConfigurationManager@@UEAAPEAUIMsiCustomAction@@W4icacCustomActionContext@@KPEAUIMsiRemoteAPI@@PEBGKPEAEPEAHPEAPEAXPEAK_N7PEAX@Z`
- size: `6049`
- prototype: `__int64 __fastcall(__int64, int, int, WCHAR *, const WCHAR *, int, _OWORD *, int *, HANDLE *, DWORD *, char, char, HANDLE hExistingToken)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a150`
- `0x180025904`
- `0x180025a18`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x180068680`
- `0x18006c044`
- `0x18006c0cc`
- `0x18006c110`
- `0x18006c17c`
- `0x18006cc60`
- `0x18006e6a8`
- `0x1800a9d48`
- `0x1800a9df0`
- `0x1800c2854`
- `0x1801435cc`
- `0x1801473c0`
- `0x180156d80`
- `0x1801583a8`
- `0x1801afce0`
- `0x1801afd60`
- `0x1801afd94`
- `0x1801c36c8`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ntdll!RtlRandom` at `0x18006d002`
- `ntdll!RtlRandom` at `0x18006d002`
- `ADVAPI32!CreateProcessAsUserW` at `0x18006dd94`
- `ADVAPI32!CreateProcessAsUserW` at `0x18006dd94`
- `ADVAPI32!SetTokenInformation` at `0x18006ce5b`
- `ADVAPI32!SetTokenInformation` at `0x18006ce5b`
- `ADVAPI32!GetTokenInformation` at `0x18006ce43`
- `ADVAPI32!GetTokenInformation` at `0x18006ce43`
- `ADVAPI32!SetThreadToken` at `0x18006dec0`
- `ADVAPI32!SetThreadToken` at `0x18006dec0`
- `ADVAPI32!DuplicateTokenEx` at `0x18006cdac`
- `ADVAPI32!DuplicateTokenEx` at `0x18006cebb`
- `ADVAPI32!DuplicateTokenEx` at `0x18006cdac`
- `ADVAPI32!DuplicateTokenEx` at `0x18006cebb`
- `ADVAPI32!OpenThreadToken` at `0x18006cde7`
- `ADVAPI32!OpenThreadToken` at `0x18006cee0`
- `ADVAPI32!OpenThreadToken` at `0x18006d6e2`
- `ADVAPI32!OpenThreadToken` at `0x18006d8d1`
- `ADVAPI32!OpenThreadToken` at `0x18006cde7`
- `ADVAPI32!OpenThreadToken` at `0x18006cee0`
- `ADVAPI32!OpenThreadToken` at `0x18006d6e2`
- `ADVAPI32!OpenThreadToken` at `0x18006d8d1`
- `ADVAPI32!OpenProcessToken` at `0x18006cd7f`
- `ADVAPI32!OpenProcessToken` at `0x18006cd7f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18006d640`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18006d698`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18006d640`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18006d698`
- `KERNEL32!CloseHandle` at `0x18006cdbf`
- `KERNEL32!CloseHandle` at `0x18006cdf6`
- `KERNEL32!CloseHandle` at `0x18006ce6a`
- `KERNEL32!CloseHandle` at `0x18006ce79`
- `KERNEL32!CloseHandle` at `0x18006cf3d`
- `KERNEL32!CloseHandle` at `0x18006cf4c`
- `KERNEL32!CloseHandle` at `0x18006d35c`
- `KERNEL32!CloseHandle` at `0x18006d42e`
- `KERNEL32!CloseHandle` at `0x18006d4b2`
- `KERNEL32!CloseHandle` at `0x18006d583`
- `KERNEL32!CloseHandle` at `0x18006d757`
- `KERNEL32!CloseHandle` at `0x18006d7dc`
- `KERNEL32!CloseHandle` at `0x18006d7eb`
- `KERNEL32!CloseHandle` at `0x18006d927`
- `KERNEL32!CloseHandle` at `0x18006d936`
- `KERNEL32!CloseHandle` at `0x18006da60`
- `KERNEL32!CloseHandle` at `0x18006da6f`
- `KERNEL32!CloseHandle` at `0x18006db1a`
- `KERNEL32!CloseHandle` at `0x18006db29`
- `KERNEL32!CloseHandle` at `0x18006dcef`
- `KERNEL32!CloseHandle` at `0x18006dd0b`
- `KERNEL32!CloseHandle` at `0x18006df16`
- `KERNEL32!CloseHandle` at `0x18006df21`
- `KERNEL32!CloseHandle` at `0x18006df2b`
- `KERNEL32!CloseHandle` at `0x18006df3a`
- `KERNEL32!CloseHandle` at `0x18006df69`
- `KERNEL32!CloseHandle` at `0x18006df74`
- `KERNEL32!CloseHandle` at `0x18006df83`
- `KERNEL32!CloseHandle` at `0x18006e065`
- `KERNEL32!CloseHandle` at `0x18006e08d`
- `KERNEL32!CloseHandle` at `0x18006e0aa`
- `KERNEL32!CloseHandle` at `0x18006e114`
- `KERNEL32!CloseHandle` at `0x18006e223`
- `KERNEL32!CloseHandle` at `0x18006e22d`
- `KERNEL32!CloseHandle` at `0x18006e23c`
- `KERNEL32!CloseHandle` at `0x18006e290`
- `KERNEL32!CloseHandle` at `0x18006e29f`
- `KERNEL32!CloseHandle` at `0x18006e3d5`
- `KERNEL32!CloseHandle` at `0x18006e3e0`
- `KERNEL32!CloseHandle` at `0x18006e3ef`
- `KERNEL32!CloseHandle` at `0x18006cdbf`
- `KERNEL32!CloseHandle` at `0x18006cdf6`
- `KERNEL32!CloseHandle` at `0x18006ce6a`
- `KERNEL32!CloseHandle` at `0x18006ce79`
- `KERNEL32!CloseHandle` at `0x18006cf3d`
- `KERNEL32!CloseHandle` at `0x18006cf4c`
- `KERNEL32!CloseHandle` at `0x18006d35c`
- `KERNEL32!CloseHandle` at `0x18006d42e`
- `KERNEL32!CloseHandle` at `0x18006d4b2`
- `KERNEL32!CloseHandle` at `0x18006d583`
- `KERNEL32!CloseHandle` at `0x18006d757`
- `KERNEL32!CloseHandle` at `0x18006d7dc`
- `KERNEL32!CloseHandle` at `0x18006d7eb`
- `KERNEL32!CloseHandle` at `0x18006d927`
- `KERNEL32!CloseHandle` at `0x18006d936`
- `KERNEL32!CloseHandle` at `0x18006da60`
- `KERNEL32!CloseHandle` at `0x18006da6f`
- `KERNEL32!CloseHandle` at `0x18006db1a`
- `KERNEL32!CloseHandle` at `0x18006db29`
- `KERNEL32!CloseHandle` at `0x18006dcef`
- `KERNEL32!CloseHandle` at `0x18006dd0b`
- `KERNEL32!CloseHandle` at `0x18006df16`
- `KERNEL32!CloseHandle` at `0x18006df21`
- `KERNEL32!CloseHandle` at `0x18006df2b`
- `KERNEL32!CloseHandle` at `0x18006df3a`
- `KERNEL32!CloseHandle` at `0x18006df69`
- `KERNEL32!CloseHandle` at `0x18006df74`
- `KERNEL32!CloseHandle` at `0x18006df83`
- `KERNEL32!CloseHandle` at `0x18006e065`
- `KERNEL32!CloseHandle` at `0x18006e08d`
- `KERNEL32!CloseHandle` at `0x18006e0aa`
- `KERNEL32!CloseHandle` at `0x18006e114`
- `KERNEL32!CloseHandle` at `0x18006e223`
- `KERNEL32!CloseHandle` at `0x18006e22d`
- `KERNEL32!CloseHandle` at `0x18006e23c`
- `KERNEL32!CloseHandle` at `0x18006e290`
- `KERNEL32!CloseHandle` at `0x18006e29f`
- `KERNEL32!CloseHandle` at `0x18006e3d5`
- `KERNEL32!CloseHandle` at `0x18006e3e0`
- `KERNEL32!CloseHandle` at `0x18006e3ef`
- `KERNEL32!LeaveCriticalSection` at `0x18006cf9e`
- `KERNEL32!LeaveCriticalSection` at `0x18006d365`
- `KERNEL32!LeaveCriticalSection` at `0x18006d4bb`
- `KERNEL32!LeaveCriticalSection` at `0x18006d7f4`
- `KERNEL32!LeaveCriticalSection` at `0x18006da97`
- `KERNEL32!LeaveCriticalSection` at `0x18006db51`
- `KERNEL32!LeaveCriticalSection` at `0x18006de59`
- `KERNEL32!LeaveCriticalSection` at `0x18006dfab`
- `KERNEL32!LeaveCriticalSection` at `0x18006e36c`
- `KERNEL32!LeaveCriticalSection` at `0x18006cf9e`
- `KERNEL32!LeaveCriticalSection` at `0x18006d365`
- `KERNEL32!LeaveCriticalSection` at `0x18006d4bb`
- `KERNEL32!LeaveCriticalSection` at `0x18006d7f4`
- `KERNEL32!LeaveCriticalSection` at `0x18006da97`
- `KERNEL32!LeaveCriticalSection` at `0x18006db51`
- `KERNEL32!LeaveCriticalSection` at `0x18006de59`
- `KERNEL32!LeaveCriticalSection` at `0x18006dfab`
- `KERNEL32!LeaveCriticalSection` at `0x18006e36c`
- `KERNEL32!GetTickCount` at `0x18006cff2`
- `KERNEL32!GetTickCount` at `0x18006cff2`
- `KERNEL32!GetLastError` at `0x18006d400`
- `KERNEL32!GetLastError` at `0x18006d8df`
- `KERNEL32!GetLastError` at `0x18006dda3`
- `KERNEL32!GetLastError` at `0x18006d400`
- `KERNEL32!GetLastError` at `0x18006d8df`
- `KERNEL32!GetLastError` at `0x18006dda3`
- `KERNEL32!EnterCriticalSection` at `0x18006ccf1`
- `KERNEL32!EnterCriticalSection` at `0x18006dcb4`
- `KERNEL32!EnterCriticalSection` at `0x18006ccf1`
- `KERNEL32!EnterCriticalSection` at `0x18006dcb4`
- `KERNEL32!GetCurrentThread` at `0x18006cdd2`
- `KERNEL32!GetCurrentThread` at `0x18006cece`
- `KERNEL32!GetCurrentThread` at `0x18006d6cb`
- `KERNEL32!GetCurrentThread` at `0x18006d8b9`
- `KERNEL32!GetCurrentThread` at `0x18006cdd2`
- `KERNEL32!GetCurrentThread` at `0x18006cece`
- `KERNEL32!GetCurrentThread` at `0x18006d6cb`
- `KERNEL32!GetCurrentThread` at `0x18006d8b9`
- `KERNEL32!GetCurrentProcess` at `0x18006cd70`
- `KERNEL32!GetCurrentProcess` at `0x18006cd70`
- `KERNEL32!GlobalFree` at `0x18006dfdb`
- `KERNEL32!GlobalFree` at `0x18006dfdb`
- `KERNEL32!SetEvent` at `0x18006df4b`
- `KERNEL32!SetEvent` at `0x18006df4b`
- `KERNEL32!CreateEventW` at `0x18006d3f7`
- `KERNEL32!CreateEventW` at `0x18006d530`
- `KERNEL32!CreateEventW` at `0x18006d3f7`
- `KERNEL32!CreateEventW` at `0x18006d530`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18006dc3f`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18006dc6c`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18006dc3f`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x18006dc6c`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18006dc9a`
- `KERNEL32!UpdateProcThreadAttribute` at `0x18006dc9a`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18006de6d`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18006de6d`
- `KERNEL32!TerminateProcess` at `0x18006df0c`
- `KERNEL32!TerminateProcess` at `0x18006df5f`
- `KERNEL32!TerminateProcess` at `0x18006df0c`
- `KERNEL32!TerminateProcess` at `0x18006df5f`
- `USER32!MsgWaitForMultipleObjects` at `0x18006e170`
- `USER32!MsgWaitForMultipleObjects` at `0x18006e170`
- `USER32!PeekMessageW` at `0x18006e1b4`
- `USER32!PeekMessageW` at `0x18006e1b4`
- `USER32!TranslateMessage` at `0x18006e190`
- `USER32!TranslateMessage` at `0x18006e190`
- `USER32!DispatchMessageW` at `0x18006e19a`
- `USER32!DispatchMessageW` at `0x18006e19a`

## string_xrefs

- `0x18006d2f5`: `Global\MSI`
- `0x18006cf70`: `Failed to create primary token while spawning Custom Action Server.`
- `0x18006d480`: `Failed to create Custom Action Server wake event.`
- `0x18006d551`: `Failed to create Custom Action Server event.`
- `0x18006d8f3`: `Unable to grab user token for impersonation. Error = %d`
- `0x18006ddc5`: `Failed to create Custom Action Server. Error %d.`
- `0x18006de12`: `Created Custom Action Server with PID %d (0x%X).`
- `0x18006ded9`: `Unable to set thread token in child process.`
- `0x18006e0c3`: `Failed to create Custom Action Server.`
- `0x18006e1e8`: `Custom Action Server never connected to service.`

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
  v30 = 0;
  v123 = v125;
  *(_OWORD *)&hMem.hwnd = *(_OWORD *)L"0123456789ABCDEF";
  LOWORD(hMem.time) = a0123456789abcd[16];
  *(_OWORD *)&hMem.wParam = *(_OWORD *)L"89ABCDEF";
  v124 = 33;
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
    if ( !byte_180309EA1 )
    {
      if ( (unsigned int)GetSecurityDescriptor(qword_18030B020, &dword_180306CD4, 0, 0) )
        goto LABEL_77;
      byte_180309EA1 = 1;
    }
    EventAttributes.lpSecurityDescriptor = qword_18030B020;
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
  else if ( qword_180309788 )
  {
    v62 = *(LPCWSTR *)qword_180309788;
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
0x18006cc60  mov     [rsp-8+arg_8], rbx
0x18006cc65  push    rbp
0x18006cc66  push    rsi
0x18006cc67  push    rdi
0x18006cc68  push    r12
0x18006cc6a  push    r13
0x18006cc6c  push    r14
0x18006cc6e  push    r15
0x18006cc70  lea     rbp, [rsp-690h]
0x18006cc78  sub     rsp, 790h
0x18006cc7f  mov     rax, cs:__security_cookie
0x18006cc86  xor     rax, rsp
0x18006cc89  mov     [rbp+6C0h+var_40], rax
0x18006cc90  mov     rax, [rbp+6C0h+arg_20]
0x18006cc97  lea     rdi, [rcx+98h]
0x18006cc9e  mov     rbx, [rbp+6C0h+hExistingToken]
0x18006cca5  mov     r13, rcx
0x18006cca8  mov     [rbp+6C0h+lpCurrentDirectory], rax
0x18006ccac  mov     rcx, rdi; lpCriticalSection
0x18006ccaf  mov     rax, [rbp+6C0h+arg_30]
0x18006ccb6  mov     r12d, edx
0x18006ccb9  mov     [rbp+6C0h+var_670], rax
0x18006ccbd  mov     rax, [rbp+6C0h+arg_38]
0x18006ccc4  mov     [rbp+6C0h+var_678], rax
0x18006ccc8  mov     rax, [rbp+6C0h+arg_40]
0x18006cccf  mov     [rbp+6C0h+var_688], rax
0x18006ccd3  mov     rax, [rbp+6C0h+arg_48]
0x18006ccda  mov     [rbp+6C0h+var_680], rax
0x18006ccde  mov     [rbp+6C0h+var_718], r9
0x18006cce2  mov     dword ptr [rbp+6C0h+lpProcessAttributes], r8d
0x18006cce6  mov     dword ptr [rbp+6C0h+Token], edx
0x18006cce9  mov     [rbp+6C0h+Size], rbx
0x18006cced  mov     [rbp+6C0h+lpCriticalSection], rdi
0x18006ccf1  call    cs:__imp_EnterCriticalSection
0x18006ccf7  lea     rax, [r13+80h]
0x18006ccfe  xor     r14d, r14d
0x18006cd01  mov     r15d, 1
0x18006cd07  mov     [rbp+6C0h+var_708], rax
0x18006cd0b  cmp     [rax], r14
0x18006cd0e  jnz     short loc_18006CD3C
0x18006cd10  mov     qword ptr [rsp+7C0h+TokenType], rax
0x18006cd15  lea     r9, IID_IGlobalInterfaceTable
0x18006cd1c  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18006cd23  lea     rcx, CLSID_StdGlobalInterfaceTable
0x18006cd2a  mov     r8d, r15d
0x18006cd2d  xor     edx, edx
0x18006cd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd34  test    eax, eax
0x18006cd36  jnz     loc_18006CF9B
0x18006cd3c  mov     esi, 2
0x18006cd41  mov     [rsp+7C0h+hObject], r14
0x18006cd46  cmp     cs:?g_scServerContext@@3W4scEnum@@A, esi; scEnum g_scServerContext
0x18006cd4c  jnz     loc_18006CE8D
0x18006cd52  lea     eax, [r12-2]
0x18006cd57  cmp     eax, 3
0x18006cd5a  ja      loc_18006CE8D
0x18006cd60  mov     dl, r15b; bool
0x18006cd63  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x18006cd67  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18006cd6c  mov     [rbp+6C0h+TokenHandle], r14
0x18006cd70  call    cs:__imp_GetCurrentProcess
0x18006cd76  lea     r8, [rbp+6C0h+TokenHandle]; TokenHandle
0x18006cd7a  mov     edx, esi; DesiredAccess
0x18006cd7c  mov     rcx, rax; ProcessHandle
0x18006cd7f  call    cs:__imp_OpenProcessToken
0x18006cd85  test    eax, eax
0x18006cd87  jz      short loc_18006CDC5
0x18006cd89  mov     rcx, [rbp+6C0h+TokenHandle]; hExistingToken
0x18006cd8d  test    rcx, rcx
0x18006cd90  jz      short loc_18006CDC5
0x18006cd92  lea     rax, [rsp+7C0h+hObject]
0x18006cd97  xor     r9d, r9d; ImpersonationLevel
0x18006cd9a  mov     [rsp+7C0h+phNewToken], rax; phNewToken
0x18006cd9f  xor     r8d, r8d; lpTokenAttributes
0x18006cda2  mov     edx, 2000000h; dwDesiredAccess
0x18006cda7  mov     [rsp+7C0h+TokenType], r15d; TokenType
0x18006cdac  call    cs:__imp_DuplicateTokenEx
0x18006cdb2  test    eax, eax
0x18006cdb4  jnz     short loc_18006CDBB
0x18006cdb6  mov     [rsp+7C0h+hObject], r14
0x18006cdbb  mov     rcx, [rbp+6C0h+TokenHandle]; hObject
0x18006cdbf  call    cs:__imp_CloseHandle
0x18006cdc5  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x18006cdc9  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18006cdce  mov     [rbp+6C0h+var_740], r14
0x18006cdd2  call    cs:__imp_GetCurrentThread
0x18006cdd8  lea     r9, [rbp+6C0h+var_740]; TokenHandle
0x18006cddc  mov     r8d, r15d; OpenAsSelf
0x18006cddf  mov     rcx, rax; ThreadHandle
0x18006cde2  mov     edx, 8; DesiredAccess
0x18006cde7  call    cs:__imp_OpenThreadToken
0x18006cded  test    eax, eax
0x18006cdef  jnz     short loc_18006CE06
0x18006cdf1  mov     rcx, [rsp+7C0h+hObject]; hObject
0x18006cdf6  call    cs:__imp_CloseHandle
0x18006cdfc  mov     [rsp+7C0h+hObject], r14
0x18006ce01  jmp     loc_18006CF59
0x18006ce06  mov     dl, r15b; bool
0x18006ce09  mov     [rsp+7C0h+var_760], r15b
0x18006ce0e  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x18006ce12  mov     [rbp+6C0h+TokenInformation], r14d
0x18006ce16  mov     [rbp+6C0h+ReturnLength], r14d
0x18006ce1d  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x18006ce22  mov     rcx, [rbp+6C0h+var_740]; TokenHandle
0x18006ce26  lea     rax, [rbp+6C0h+ReturnLength]
0x18006ce2d  mov     ebx, 4
0x18006ce32  mov     qword ptr [rsp+7C0h+TokenType], rax; ReturnLength
0x18006ce37  mov     r9d, ebx; TokenInformationLength
0x18006ce3a  lea     r8, [rbp+6C0h+TokenInformation]; TokenInformation
0x18006ce3e  lea     esi, [rbx+8]
0x18006ce41  mov     edx, esi; TokenInformationClass
0x18006ce43  call    cs:__imp_GetTokenInformation
0x18006ce49  test    eax, eax
0x18006ce4b  jz      short loc_18006CE65
0x18006ce4d  mov     rcx, [rsp+7C0h+hObject]; TokenHandle
0x18006ce52  lea     r8, [rbp+6C0h+TokenInformation]; TokenInformation
0x18006ce56  mov     r9d, ebx; TokenInformationLength
0x18006ce59  mov     edx, esi; TokenInformationClass
0x18006ce5b  call    cs:__imp_SetTokenInformation
0x18006ce61  test    eax, eax
0x18006ce63  jnz     short loc_18006CE75
0x18006ce65  mov     rcx, [rsp+7C0h+hObject]; hObject
0x18006ce6a  call    cs:__imp_CloseHandle
0x18006ce70  mov     [rsp+7C0h+hObject], r14
0x18006ce75  mov     rcx, [rbp+6C0h+var_740]; hObject
0x18006ce79  call    cs:__imp_CloseHandle
0x18006ce7f  lea     rcx, [rbp+6C0h+lpAttributeList]; this
0x18006ce83  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x18006ce88  jmp     loc_18006CF52
0x18006ce8d  mov     [rsp+7C0h+var_760], r14b
0x18006ce92  mov     [rbp+6C0h+TokenHandle], r14
0x18006ce96  mov     [rbp+6C0h+var_740], r14
0x18006ce9a  test    rbx, rbx
0x18006ce9d  jz      short loc_18006CECE
0x18006ce9f  mov     rcx, rbx; hExistingToken
0x18006cea2  lea     rax, [rbp+6C0h+var_740]
0x18006cea6  xor     r9d, r9d; ImpersonationLevel
0x18006cea9  mov     [rsp+7C0h+phNewToken], rax; phNewToken
0x18006ceae  xor     r8d, r8d; lpTokenAttributes
0x18006ceb1  mov     edx, 2000000h; dwDesiredAccess
0x18006ceb6  mov     [rsp+7C0h+TokenType], r15d; TokenType
0x18006cebb  call    cs:__imp_DuplicateTokenEx
0x18006cec1  test    eax, eax
0x18006cec3  jnz     short loc_18006CEF0
0x18006cec5  mov     rcx, r14
0x18006cec8  mov     [rbp+6C0h+var_740], rcx
0x18006cecc  jmp     short loc_18006CEF4
0x18006cece  call    cs:__imp_GetCurrentThread
0x18006ced4  lea     r9, [rbp+6C0h+TokenHandle]; TokenHandle
0x18006ced8  mov     r8d, r15d; OpenAsSelf
0x18006cedb  mov     rcx, rax; ThreadHandle
0x18006cede  mov     edx, esi; DesiredAccess
0x18006cee0  call    cs:__imp_OpenThreadToken
0x18006cee6  test    eax, eax
0x18006cee8  jz      short loc_18006CEF0
0x18006ceea  mov     rcx, [rbp+6C0h+TokenHandle]
0x18006ceee  jmp     short loc_18006CEA2
0x18006cef0  mov     rcx, [rbp+6C0h+var_740]
0x18006cef4  test    rcx, rcx
0x18006cef7  jz      short loc_18006CF43
0x18006cef9  lea     rax, [rsp+7C0h+hObject]
0x18006cefe  xor     r9d, r9d
0x18006cf01  mov     qword ptr [rsp+7C0h+nSubAuthority6], rax
0x18006cf06  xor     r8d, r8d
0x18006cf09  mov     rax, cs:?CreateRestrictedToken@ADVAPI32@@3P6AHPEAXKKPEAU_SID_AND_ATTRIBUTES@@KPEAU_LUID_AND_ATTRIBUTES@@K1PEAPEAX@ZEA; int (*ADVAPI32::CreateRestrictedToken)(void *,ulong,ulong,_SID_AND_ATTRIBUTES *,ulong,_LUID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *,void * *)
0x18006cf10  mov     edx, esi
0x18006cf12  mov     qword ptr [rsp+7C0h+nSubAuthority5], r14
0x18006cf17  mov     [rsp+7C0h+nSubAuthority4], r14d
0x18006cf1c  mov     [rsp+7C0h+phNewToken], r14
0x18006cf21  mov     [rsp+7C0h+TokenType], r14d
0x18006cf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf2b  test    eax, eax
0x18006cf2d  jnz     short loc_18006CF34
0x18006cf2f  mov     [rsp+7C0h+hObject], r14
0x18006cf34  mov     rcx, [rbp+6C0h+var_740]; hObject
0x18006cf38  test    rcx, rcx
0x18006cf3b  jz      short loc_18006CF43
0x18006cf3d  call    cs:__imp_CloseHandle
0x18006cf43  mov     rcx, [rbp+6C0h+TokenHandle]; hObject
0x18006cf47  test    rcx, rcx
0x18006cf4a  jz      short loc_18006CF52
0x18006cf4c  call    cs:__imp_CloseHandle
0x18006cf52  cmp     [rsp+7C0h+hObject], r14
0x18006cf57  jnz     short loc_18006CFA9
0x18006cf59  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18006cf60  jz      short loc_18006CF9B
0x18006cf62  lea     rsi, aNull_0; "(NULL)"
0x18006cf69  xor     edx, edx; unsigned __int16
0x18006cf6b  mov     qword ptr [rsp+7C0h+nSubAuthority7], rsi; char *
0x18006cf70  lea     r9, aFailedToCreate_5; "Failed to create primary token while sp"...
0x18006cf77  mov     qword ptr [rsp+7C0h+nSubAuthority6], rsi; char *
0x18006cf7c  xor     r8d, r8d; int
0x18006cf7f  mov     qword ptr [rsp+7C0h+nSubAuthority5], rsi; char *
0x18006cf84  mov     qword ptr [rsp+7C0h+nSubAuthority4], rsi; char *
0x18006cf89  lea     ecx, [rdx+0Ah]; int
0x18006cf8c  mov     [rsp+7C0h+phNewToken], rsi; char *
0x18006cf91  mov     qword ptr [rsp+7C0h+TokenType], rsi; char *
0x18006cf96  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18006cf9b  mov     rcx, rdi; lpCriticalSection
0x18006cf9e  call    cs:__imp_LeaveCriticalSection
0x18006cfa4  jmp     loc_18006D864
0x18006cfa9  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18006cfb0  lea     rsi, aNull_0; "(NULL)"
0x18006cfb7  mov     [r13+0E8h], r14b
0x18006cfbe  jz      short loc_18006CFF2
0x18006cfc0  mov     qword ptr [rsp+7C0h+nSubAuthority7], rsi; char *
0x18006cfc5  lea     r9, aGeneratingRand; "Generating random cookie."
0x18006cfcc  mov     qword ptr [rsp+7C0h+nSubAuthority6], rsi; char *
0x18006cfd1  xor     edx, edx; unsigned __int16
0x18006cfd3  mov     qword ptr [rsp+7C0h+nSubAuthority5], rsi; char *
0x18006cfd8  xor     r8d, r8d; int
0x18006cfdb  mov     qword ptr [rsp+7C0h+nSubAuthority4], rsi; char *
0x18006cfe0  mov     [rsp+7C0h+phNewToken], rsi; char *
0x18006cfe5  lea     ecx, [rdx+0Ah]; int
0x18006cfe8  mov     qword ptr [rsp+7C0h+TokenType], rsi; char *
0x18006cfed  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18006cff2  call    cs:__imp_GetTickCount
0x18006cff8  mov     [rbp+6C0h+Seed], eax
0x18006cffb  mov     rbx, r14
0x18006cffe  lea     rcx, [rbp+6C0h+Seed]; Seed
0x18006d002  call    cs:__imp_RtlRandom
0x18006d008  mov     r8d, eax
0x18006d00b  mov     eax, 80808081h
0x18006d010  mul     r8d
0x18006d013  shr     edx, 7
0x18006d016  imul    ecx, edx, 0FFh
0x18006d01c  sub     r8d, ecx
0x18006d01f  mov     [rbx+r13+0E8h], r8b
0x18006d027  add     rbx, r15
0x18006d02a  cmp     rbx, 10h
0x18006d02e  jnz     short loc_18006CFFE
0x18006d030  xor     edx, edx; Val
0x18006d032  lea     rcx, [rbp+6C0h+var_540]; void *
0x18006d039  mov     r8d, 208h; Size
0x18006d03f  call    memset_0
0x18006d044  lea     rax, [rbp+6C0h+var_540]
0x18006d04b  mov     [rbp+6C0h+var_548], 104h
0x18006d055  mov     [rbp+6C0h+var_550], rax
0x18006d05c  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18006d063  lea     eax, [r12-1]
0x18006d068  mov     [rsp+7C0h+var_758], rcx
0x18006d06d  cmp     eax, 8
0x18006d070  ja      short loc_18006D07A
0x18006d072  test    r15b, al
0x18006d075  mov     al, r15b
0x18006d078  jz      short loc_18006D07D
0x18006d07a  mov     al, r14b
0x18006d07d  mov     [rsp+7C0h+var_748], al
0x18006d081  test    al, al
0x18006d083  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18006d08a  mov     [rbp+6C0h+TokenHandle], rcx
0x18006d08e  mov     rax, [rax+10h]
0x18006d092  jz      short loc_18006D0B0
0x18006d094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d099  mov     rcx, [r13+10h]; struct IMsiServices *
0x18006d09d  lea     r9, [rbp+6C0h+TokenHandle]; struct IMsiString **
0x18006d0a1  mov     r8b, r15b; bool
0x18006d0a4  xor     edx, edx; bool
0x18006d0a6  call    ?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z; GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)
0x18006d0ab  xor     r8d, r8d
0x18006d0ae  jmp     short loc_18006D0CA
0x18006d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0b5  mov     rcx, [r13+10h]; struct IMsiServices *
0x18006d0b9  lea     r9, [rbp+6C0h+TokenHandle]; struct IMsiString **
0x18006d0bd  xor     r8d, r8d; bool
0x18006d0c0  xor     edx, edx; bool
0x18006d0c2  call    ?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z; GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)
0x18006d0c7  mov     r8d, r15d; int
0x18006d0ca  mov     rcx, [rbp+6C0h+var_550]; unsigned __int16 *
0x18006d0d1  mov     edx, 104h; unsigned int
0x18006d0d6  mov     rbx, rax
0x18006d0d9  call    ?MsiGetSystemDirectory@@YAIPEAGIH@Z; MsiGetSystemDirectory(ushort *,uint,int)
0x18006d0de  mov     r15, [rbp+6C0h+TokenHandle]
0x18006d0e2  mov     rcx, r15
0x18006d0e5  mov     [rbp+6C0h+var_728], rbx
0x18006d0e9  mov     rax, [r15]
0x18006d0ec  mov     rax, [rax+8]
0x18006d0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0f5  mov     rcx, [rsp+7C0h+var_758]
0x18006d0fa  mov     rax, [rcx]
0x18006d0fd  mov     rax, [rax+10h]
0x18006d101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d106  mov     [rsp+7C0h+var_758], r15
0x18006d10b  lea     r8, [rsp+7C0h+var_758]
0x18006d110  mov     rax, [r15]
0x18006d113  lea     rdx, aEmbedding; " -Embedding "
0x18006d11a  mov     rcx, r15
0x18006d11d  mov     rax, [rax+90h]
0x18006d124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d129  xor     edx, edx; Val
0x18006d12b  lea     rcx, [rbp+6C0h+var_5A0]; void *
0x18006d132  lea     r8d, [rdx+42h]; Size
0x18006d136  call    memset_0
0x18006d13b  movaps  xmm0, xmmword ptr cs:a0123456789abcd; "0123456789ABCDEF"
0x18006d142  lea     r9, [rbp+6C0h+var_5A0]
0x18006d149  movaps  xmm1, xmmword ptr cs:a0123456789abcd+10h; "89ABCDEF"
0x18006d150  mov     r8d, r14d
0x18006d153  movzx   eax, word ptr cs:a0123456789abcd+20h; ""
0x18006d15a  mov     [rbp+6C0h+var_5B0], r9
0x18006d161  movups  xmmword ptr [rbp+6C0h+hMem], xmm0
  ... truncated ...
```
