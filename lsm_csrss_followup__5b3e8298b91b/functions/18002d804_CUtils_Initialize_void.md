# CUtils::Initialize(void)

- ea: `0x18002d804`
- end: `0x18002da32`
- name: `?Initialize@CUtils@@SAJXZ`
- size: `558`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045fd4`

## callees

- `0x1800074c0`
- `0x18001288c`
- `0x18001a088`
- `0x18002d804`
- `0x18002da38`
- `0x1800473dc`
- `0x180047dcc`
- `0x18004b460`
- `0x18004b86c`
- `0x18004bf44`
- `0x18007e504`
- `0x18007e544`
- `0x18007e86c`
- `0x18007efd4`
- `0x180093ae4`
- `0x180093c1c`
- `0x180093ca8`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x18002d972`
- `ntdll!RtlVerifyVersionInfo` at `0x18002d972`
- `ntdll!VerSetConditionMask` at `0x18002d962`
- `ntdll!VerSetConditionMask` at `0x18002d962`
- `ntdll!RtlNtStatusToDosError` at `0x18002d8d6`
- `ntdll!RtlNtStatusToDosError` at `0x18002d8d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d8e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8de`

## string_xrefs

- `0x18002d86f`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x18002d8a8`: `NtCreateAnonymousSid failed: 0x%x in %s`
- `0x18002d88d`: `CUtils::CreateAdminSid failed: 0x%x in %s`
- `0x18002d8fd`: `CUtils::CreateRdsMsSid failed: 0x%x in %s`
- `0x18002d8bf`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x18002d939`: `CUtils::CreateLPACCapabilitySid failed: 0x%x in %s`
- `0x18002d91b`: `CUtils::CreateAppContainerSid failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::Initialize(void)
{
  int SystemSid; // ebx
  int AnonymousSid; // eax
  void **v2; // rcx
  NTSTATUS RdsMsSid; // eax
  ULONG v4; // eax
  signed int LastError; // eax
  ULONGLONG v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v10[4]; // [rsp+20h] [rbp-148h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+30h] [rbp-138h] BYREF

  v10[0] = 0;
  memset_0(&VersionInfo, 0, sizeof(VersionInfo));
  g_bDebugSpew = 0;
  CUtils::IsAppServerInstalled(v10);
  CUtils::bIsAppCompat = v10[0];
  SystemSid = CUtils::CreateSystemSid(&CUtils::pSystemSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "CUtil::CreateSystemSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_23;
  }
  SystemSid = CUtils::CreateAdminSid(&CUtils::pAdminSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "CUtils::CreateAdminSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_23;
  }
  AnonymousSid = NtCreateAnonymousSid();
  SystemSid = AnonymousSid | 0x10000000;
  if ( AnonymousSid < 0 )
  {
    _DbgPrintMessage(8, "NtCreateAnonymousSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_23;
  }
  SystemSid = CUtils::CreateNetworkServiceSid(v2);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateNetworkServiceSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_23;
  }
  RdsMsSid = NtCreateRdsMsSid();
  if ( RdsMsSid < 0 )
  {
    v4 = RtlNtStatusToDosError(RdsMsSid);
    SetLastError(v4);
    LastError = GetLastError();
    SystemSid = LastError;
    if ( LastError > 0 )
      SystemSid = (unsigned __int16)LastError | 0x80070000;
    if ( SystemSid < 0 )
    {
      _DbgPrintMessage(8, "CUtils::CreateRdsMsSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
      goto LABEL_23;
    }
  }
  SystemSid = CUtils::CreateAppContainerSid(&CUtils::pAppContainerSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateAppContainerSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_23;
  }
  SystemSid = CUtils::CreateLPACCapabilitySid(&CUtils::pLPACCapabilitySid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateLPACCapabilitySid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_23;
  }
  IsPersonalTerminalServicesEnabled();
  VersionInfo.dwOSVersionInfoSize = 284;
  VersionInfo.wProductType = 1;
  v6 = VerSetConditionMask(0, 0x80u, 1u);
  RtlVerifyVersionInfo(&VersionInfo, 0x80u, v6);
  v7 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
  {
    g_pObjectTracker = 0;
    SystemSid = -2147024882;
LABEL_26:
    CUtils::Destroy();
    return (unsigned int)SystemSid;
  }
  *v7 = 0;
  v7[30] = 0;
  *((_QWORD *)v7 + 2) = v7 + 2;
  *((_QWORD *)v7 + 1) = v7 + 2;
  g_pObjectTracker = v7;
  SystemSid = CResource::Initialize((CResource *)(v7 + 6));
  *v8 = SystemSid >= 0;
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "Tracker.Initialize failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_23;
  }
  SystemSid = COpsMonitorBase::Initialize();
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "COpsMonitorBase::Initialize failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
LABEL_23:
    if ( SystemSid >= 0 )
      return (unsigned int)SystemSid;
    goto LABEL_26;
  }
  return (unsigned int)SystemSid;
}

```

## disassembly

```asm
0x18002d804  mov     [rsp+arg_0], rbx
0x18002d809  push    rdi
0x18002d80a  sub     rsp, 160h
0x18002d811  mov     rax, cs:__security_cookie
0x18002d818  xor     rax, rsp
0x18002d81b  mov     [rsp+168h+var_18], rax
0x18002d823  mov     edi, 11Ch
0x18002d828  mov     [rsp+168h+var_148], 0
0x18002d830  mov     r8d, edi; Size
0x18002d833  lea     rcx, [rsp+168h+VersionInfo]; void *
0x18002d838  xor     edx, edx; Val
0x18002d83a  call    memset_0
0x18002d83f  lea     rcx, [rsp+168h+var_148]; int *
0x18002d844  mov     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x18002d84e  call    ?IsAppServerInstalled@CUtils@@SAJAEAH@Z; CUtils::IsAppServerInstalled(int &)
0x18002d853  mov     eax, [rsp+168h+var_148]
0x18002d857  lea     rcx, ?pSystemSid@CUtils@@0PEAXEA; void **
0x18002d85e  mov     cs:?bIsAppCompat@CUtils@@0HA, eax; int CUtils::bIsAppCompat
0x18002d864  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18002d869  mov     ebx, eax
0x18002d86b  test    eax, eax
0x18002d86d  jns     short loc_18002D87B
0x18002d86f  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x18002d876  jmp     loc_18002D9E0
0x18002d87b  lea     rcx, ?pAdminSid@CUtils@@0PEAXEA; void **
0x18002d882  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x18002d887  mov     ebx, eax
0x18002d889  test    eax, eax
0x18002d88b  jns     short loc_18002D899
0x18002d88d  lea     rdx, aCutilsCreatead; "CUtils::CreateAdminSid failed: 0x%x in "...
0x18002d894  jmp     loc_18002D9E0
0x18002d899  call    NtCreateAnonymousSid
0x18002d89e  mov     ebx, eax
0x18002d8a0  or      ebx, 10000000h
0x18002d8a6  jge     short loc_18002D8B4
0x18002d8a8  lea     rdx, aNtcreateanonym; "NtCreateAnonymousSid failed: 0x%x in %s"
0x18002d8af  jmp     loc_18002D9E0
0x18002d8b4  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x18002d8b9  mov     ebx, eax
0x18002d8bb  test    eax, eax
0x18002d8bd  jns     short loc_18002D8CB
0x18002d8bf  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x18002d8c6  jmp     loc_18002D9E0
0x18002d8cb  call    NtCreateRdsMsSid
0x18002d8d0  test    eax, eax
0x18002d8d2  jns     short loc_18002D909
0x18002d8d4  mov     ecx, eax; Status
0x18002d8d6  call    cs:__imp_RtlNtStatusToDosError
0x18002d8dc  mov     ecx, eax; dwErrCode
0x18002d8de  call    cs:__imp_SetLastError
0x18002d8e4  call    cs:__imp_GetLastError
0x18002d8ea  mov     ebx, eax
0x18002d8ec  test    eax, eax
0x18002d8ee  jle     short loc_18002D8F9
0x18002d8f0  movzx   ebx, ax
0x18002d8f3  or      ebx, 80070000h
0x18002d8f9  test    ebx, ebx
0x18002d8fb  jns     short loc_18002D909
0x18002d8fd  lea     rdx, aCutilsCreaterd; "CUtils::CreateRdsMsSid failed: 0x%x in "...
0x18002d904  jmp     loc_18002D9E0
0x18002d909  lea     rcx, ?pAppContainerSid@CUtils@@0PEAXEA; pSid
0x18002d910  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x18002d915  mov     ebx, eax
0x18002d917  test    eax, eax
0x18002d919  jns     short loc_18002D927
0x18002d91b  lea     rdx, aCutilsCreateap; "CUtils::CreateAppContainerSid failed: 0"...
0x18002d922  jmp     loc_18002D9E0
0x18002d927  lea     rcx, ?pLPACCapabilitySid@CUtils@@0PEAXEA; Sid
0x18002d92e  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x18002d933  mov     ebx, eax
0x18002d935  test    eax, eax
0x18002d937  jns     short loc_18002D945
0x18002d939  lea     rdx, aCutilsCreatelp; "CUtils::CreateLPACCapabilitySid failed:"...
0x18002d940  jmp     loc_18002D9E0
0x18002d945  call    IsPersonalTerminalServicesEnabled
0x18002d94a  mov     ebx, 80h
0x18002d94f  mov     [rsp+168h+VersionInfo.dwOSVersionInfoSize], edi
0x18002d953  mov     edx, ebx; TypeMask
0x18002d955  mov     [rsp+168h+VersionInfo.wProductType], 1
0x18002d95d  mov     r8b, 1; Condition
0x18002d960  xor     ecx, ecx; ConditionMask
0x18002d962  call    cs:__imp_VerSetConditionMask
0x18002d968  mov     edx, ebx; TypeMask
0x18002d96a  lea     rcx, [rsp+168h+VersionInfo]; VersionInfo
0x18002d96f  mov     r8, rax; ConditionMask
0x18002d972  call    cs:__imp_RtlVerifyVersionInfo
0x18002d978  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d97f  mov     ecx, ebx; unsigned __int64
0x18002d981  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d986  mov     rdi, rax
0x18002d989  test    rax, rax
0x18002d98c  jz      short loc_18002D9FA
0x18002d98e  mov     dword ptr [rax], 0
0x18002d994  lea     rcx, [rax+8]
0x18002d998  mov     dword ptr [rax+78h], 0
0x18002d99f  mov     [rcx+8], rcx
0x18002d9a3  mov     [rcx], rcx
0x18002d9a6  lea     rcx, [rax+18h]; this
0x18002d9aa  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, rax; CObjectTracker * g_pObjectTracker
0x18002d9b1  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002d9b6  mov     ecx, eax
0x18002d9b8  mov     ebx, eax
0x18002d9ba  not     ecx
0x18002d9bc  shr     ecx, 1Fh
0x18002d9bf  mov     [rdi], ecx
0x18002d9c1  test    eax, eax
0x18002d9c3  jns     short loc_18002D9CE
0x18002d9c5  lea     rdx, aTrackerInitial; "Tracker.Initialize failed: 0x%x in %s"
0x18002d9cc  jmp     short loc_18002D9E0
0x18002d9ce  call    ?Initialize@COpsMonitorBase@@SAJXZ; COpsMonitorBase::Initialize(void)
0x18002d9d3  mov     ebx, eax
0x18002d9d5  test    eax, eax
0x18002d9d7  jns     short loc_18002DA0F
0x18002d9d9  lea     rdx, aCopsmonitorbas_1; "COpsMonitorBase::Initialize failed: 0x%"...
0x18002d9e0  mov     ecx, 8; int
0x18002d9e5  lea     r9, aCutilsInitiali; "CUtils::Initialize"
0x18002d9ec  mov     r8d, ebx
0x18002d9ef  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d9f4  test    ebx, ebx
0x18002d9f6  js      short loc_18002DA0A
0x18002d9f8  jmp     short loc_18002DA0F
0x18002d9fa  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x18002da05  mov     ebx, 8007000Eh
0x18002da0a  call    ?Destroy@CUtils@@SAXXZ; CUtils::Destroy(void)
0x18002da0f  mov     eax, ebx
0x18002da11  mov     rcx, [rsp+168h+var_18]
0x18002da19  xor     rcx, rsp; StackCookie
0x18002da1c  call    __security_check_cookie
0x18002da21  mov     rbx, [rsp+168h+arg_0]
0x18002da29  add     rsp, 160h
0x18002da30  pop     rdi
0x18002da31  retn
```
