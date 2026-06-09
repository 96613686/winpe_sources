# CUtils::Initialize(void)

- ea: `0x18002f7c0`
- end: `0x18002f9d4`
- name: `?Initialize@CUtils@@SAJXZ`
- size: `532`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800492f0`

## callees

- `0x1800077a0`
- `0x180009490`
- `0x180016740`
- `0x18002f7c0`
- `0x18002f9dc`
- `0x180049dbc`
- `0x18004af10`
- `0x18004e850`
- `0x18004ec5c`
- `0x18004f354`
- `0x180082efc`
- `0x180082f50`
- `0x18008300c`
- `0x18008333c`
- `0x180083b6c`
- `0x180098fe0`
- `0x180099130`

## import_xrefs

- `ntdll!RtlVerifyVersionInfo` at `0x18002f90d`
- `ntdll!RtlVerifyVersionInfo` at `0x18002f90d`
- `ntdll!VerSetConditionMask` at `0x18002f8f7`
- `ntdll!VerSetConditionMask` at `0x18002f8f7`

## string_xrefs

- `0x18002f82b`: `CUtil::CreateSystemSid failed: 0x%x in %s`
- `0x18002f849`: `CUtils::CreateAdminSid failed: 0x%x in %s`
- `0x18002f87b`: `CUtils::CreateNetworkServiceSid failed: 0x%x in %s`
- `0x18002f864`: `NtCreateAnonymousSid failed: 0x%x in %s`
- `0x18002f8b0`: `CUtils::CreateAppContainerSid failed: 0x%x in %s`
- `0x18002f892`: `CUtils::CreateRdsMsSid failed: 0x%x in %s`
- `0x18002f8ce`: `CUtils::CreateLPACCapabilitySid failed: 0x%x in %s`

## pseudocode

```c
__int64 CUtils::Initialize(void)
{
  int SystemSid; // ebx
  int AnonymousSid; // eax
  void **v2; // rcx
  void **v3; // rcx
  ULONGLONG v4; // rax
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  int v8[4]; // [rsp+20h] [rbp-148h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+30h] [rbp-138h] BYREF

  v8[0] = 0;
  memset_0(&VersionInfo, 0, sizeof(VersionInfo));
  g_bDebugSpew = 0;
  CUtils::IsAppServerInstalled(v8);
  CUtils::bIsAppCompat = v8[0];
  SystemSid = CUtils::CreateSystemSid(&CUtils::pSystemSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "CUtil::CreateSystemSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = CUtils::CreateAdminSid(&CUtils::pAdminSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "CUtils::CreateAdminSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_20;
  }
  AnonymousSid = NtCreateAnonymousSid();
  SystemSid = AnonymousSid | 0x10000000;
  if ( AnonymousSid < 0 )
  {
    _DbgPrintMessage(8, "NtCreateAnonymousSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = CUtils::CreateNetworkServiceSid(v2);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateNetworkServiceSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = CUtils::CreateRdsMsSid(v3);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "CUtils::CreateRdsMsSid failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = CUtils::CreateAppContainerSid(&CUtils::pAppContainerSid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateAppContainerSid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = CUtils::CreateLPACCapabilitySid(&CUtils::pLPACCapabilitySid);
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(
      8,
      "CUtils::CreateLPACCapabilitySid failed: 0x%x in %s",
      (unsigned int)SystemSid,
      "CUtils::Initialize");
    goto LABEL_20;
  }
  IsPersonalTerminalServicesEnabled();
  VersionInfo.dwOSVersionInfoSize = 284;
  VersionInfo.wProductType = 1;
  v4 = VerSetConditionMask(0, 0x80u, 1u);
  RtlVerifyVersionInfo(&VersionInfo, 0x80u, v4);
  v5 = operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    g_pObjectTracker = 0;
    SystemSid = -2147024882;
LABEL_23:
    CUtils::Destroy();
    return (unsigned int)SystemSid;
  }
  *v5 = 0;
  v5[30] = 0;
  *((_QWORD *)v5 + 2) = v5 + 2;
  *((_QWORD *)v5 + 1) = v5 + 2;
  g_pObjectTracker = v5;
  SystemSid = CResource::Initialize((CResource *)(v5 + 6));
  *v6 = SystemSid >= 0;
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "Tracker.Initialize failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
    goto LABEL_20;
  }
  SystemSid = COpsMonitorBase::Initialize();
  if ( SystemSid < 0 )
  {
    _DbgPrintMessage(8, "COpsMonitorBase::Initialize failed: 0x%x in %s", (unsigned int)SystemSid, "CUtils::Initialize");
LABEL_20:
    if ( SystemSid >= 0 )
      return (unsigned int)SystemSid;
    goto LABEL_23;
  }
  return (unsigned int)SystemSid;
}

```

## disassembly

```asm
0x18002f7c0  mov     [rsp+arg_0], rbx
0x18002f7c5  push    rdi
0x18002f7c6  sub     rsp, 160h
0x18002f7cd  mov     rax, cs:__security_cookie
0x18002f7d4  xor     rax, rsp
0x18002f7d7  mov     [rsp+168h+var_18], rax
0x18002f7df  mov     edi, 11Ch
0x18002f7e4  mov     [rsp+168h+var_148], 0
0x18002f7ec  mov     r8d, edi; Size
0x18002f7ef  lea     rcx, [rsp+168h+VersionInfo]; void *
0x18002f7f4  xor     edx, edx; Val
0x18002f7f6  call    memset_0
0x18002f7fb  lea     rcx, [rsp+168h+var_148]; int *
0x18002f800  mov     cs:?g_bDebugSpew@@3HA, 0; int g_bDebugSpew
0x18002f80a  call    ?IsAppServerInstalled@CUtils@@SAJAEAH@Z; CUtils::IsAppServerInstalled(int &)
0x18002f80f  mov     eax, [rsp+168h+var_148]
0x18002f813  lea     rcx, ?pSystemSid@CUtils@@0PEAXEA; void **
0x18002f81a  mov     cs:?bIsAppCompat@CUtils@@0HA, eax; int CUtils::bIsAppCompat
0x18002f820  call    ?CreateSystemSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateSystemSid(void * *)
0x18002f825  mov     ebx, eax
0x18002f827  test    eax, eax
0x18002f829  jns     short loc_18002F837
0x18002f82b  lea     rdx, aCutilCreatesys; "CUtil::CreateSystemSid failed: 0x%x in "...
0x18002f832  jmp     loc_18002F981
0x18002f837  lea     rcx, ?pAdminSid@CUtils@@0PEAXEA; void **
0x18002f83e  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x18002f843  mov     ebx, eax
0x18002f845  test    eax, eax
0x18002f847  jns     short loc_18002F855
0x18002f849  lea     rdx, aCutilsCreatead; "CUtils::CreateAdminSid failed: 0x%x in "...
0x18002f850  jmp     loc_18002F981
0x18002f855  call    NtCreateAnonymousSid
0x18002f85a  mov     ebx, eax
0x18002f85c  or      ebx, 10000000h
0x18002f862  jge     short loc_18002F870
0x18002f864  lea     rdx, aNtcreateanonym; "NtCreateAnonymousSid failed: 0x%x in %s"
0x18002f86b  jmp     loc_18002F981
0x18002f870  call    ?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateNetworkServiceSid(void * *)
0x18002f875  mov     ebx, eax
0x18002f877  test    eax, eax
0x18002f879  jns     short loc_18002F887
0x18002f87b  lea     rdx, aCutilsCreatene; "CUtils::CreateNetworkServiceSid failed:"...
0x18002f882  jmp     loc_18002F981
0x18002f887  call    ?CreateRdsMsSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateRdsMsSid(void * *)
0x18002f88c  mov     ebx, eax
0x18002f88e  test    eax, eax
0x18002f890  jns     short loc_18002F89E
0x18002f892  lea     rdx, aCutilsCreaterd; "CUtils::CreateRdsMsSid failed: 0x%x in "...
0x18002f899  jmp     loc_18002F981
0x18002f89e  lea     rcx, ?pAppContainerSid@CUtils@@0PEAXEA; pSid
0x18002f8a5  call    ?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAppContainerSid(void * *)
0x18002f8aa  mov     ebx, eax
0x18002f8ac  test    eax, eax
0x18002f8ae  jns     short loc_18002F8BC
0x18002f8b0  lea     rdx, aCutilsCreateap; "CUtils::CreateAppContainerSid failed: 0"...
0x18002f8b7  jmp     loc_18002F981
0x18002f8bc  lea     rcx, ?pLPACCapabilitySid@CUtils@@0PEAXEA; Sid
0x18002f8c3  call    ?CreateLPACCapabilitySid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateLPACCapabilitySid(void * *)
0x18002f8c8  mov     ebx, eax
0x18002f8ca  test    eax, eax
0x18002f8cc  jns     short loc_18002F8DA
0x18002f8ce  lea     rdx, aCutilsCreatelp; "CUtils::CreateLPACCapabilitySid failed:"...
0x18002f8d5  jmp     loc_18002F981
0x18002f8da  call    IsPersonalTerminalServicesEnabled
0x18002f8df  mov     ebx, 80h
0x18002f8e4  mov     [rsp+168h+VersionInfo.dwOSVersionInfoSize], edi
0x18002f8e8  mov     edx, ebx; TypeMask
0x18002f8ea  mov     [rsp+168h+VersionInfo.wProductType], 1
0x18002f8f2  mov     r8b, 1; Condition
0x18002f8f5  xor     ecx, ecx; ConditionMask
0x18002f8f7  call    cs:__imp_VerSetConditionMask
0x18002f8fe  nop     dword ptr [rax+rax+00h]
0x18002f903  mov     edx, ebx; TypeMask
0x18002f905  lea     rcx, [rsp+168h+VersionInfo]; VersionInfo
0x18002f90a  mov     r8, rax; ConditionMask
0x18002f90d  call    cs:__imp_RtlVerifyVersionInfo
0x18002f914  nop     dword ptr [rax+rax+00h]
0x18002f919  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f920  mov     ecx, ebx; unsigned __int64
0x18002f922  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f927  mov     rdi, rax
0x18002f92a  test    rax, rax
0x18002f92d  jz      short loc_18002F99B
0x18002f92f  mov     dword ptr [rax], 0
0x18002f935  lea     rcx, [rax+8]
0x18002f939  mov     dword ptr [rax+78h], 0
0x18002f940  mov     [rcx+8], rcx
0x18002f944  mov     [rcx], rcx
0x18002f947  lea     rcx, [rax+18h]; this
0x18002f94b  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, rax; CObjectTracker * g_pObjectTracker
0x18002f952  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18002f957  mov     ecx, eax
0x18002f959  mov     ebx, eax
0x18002f95b  not     ecx
0x18002f95d  shr     ecx, 1Fh
0x18002f960  mov     [rdi], ecx
0x18002f962  test    eax, eax
0x18002f964  jns     short loc_18002F96F
0x18002f966  lea     rdx, aTrackerInitial; "Tracker.Initialize failed: 0x%x in %s"
0x18002f96d  jmp     short loc_18002F981
0x18002f96f  call    ?Initialize@COpsMonitorBase@@SAJXZ; COpsMonitorBase::Initialize(void)
0x18002f974  mov     ebx, eax
0x18002f976  test    eax, eax
0x18002f978  jns     short loc_18002F9B0
0x18002f97a  lea     rdx, aCopsmonitorbas_1; "COpsMonitorBase::Initialize failed: 0x%"...
0x18002f981  mov     ecx, 8; int
0x18002f986  lea     r9, aCutilsInitiali; "CUtils::Initialize"
0x18002f98d  mov     r8d, ebx
0x18002f990  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f995  test    ebx, ebx
0x18002f997  js      short loc_18002F9AB
0x18002f999  jmp     short loc_18002F9B0
0x18002f99b  mov     cs:?g_pObjectTracker@@3PEAVCObjectTracker@@EA, 0; CObjectTracker * g_pObjectTracker
0x18002f9a6  mov     ebx, 8007000Eh
0x18002f9ab  call    ?Destroy@CUtils@@SAXXZ; CUtils::Destroy(void)
0x18002f9b0  mov     eax, ebx
0x18002f9b2  mov     rcx, [rsp+168h+var_18]
0x18002f9ba  xor     rcx, rsp; StackCookie
0x18002f9bd  call    __security_check_cookie
0x18002f9c2  mov     rbx, [rsp+168h+arg_0]
0x18002f9ca  add     rsp, 160h
0x18002f9d1  pop     rdi
0x18002f9d2  retn
```
