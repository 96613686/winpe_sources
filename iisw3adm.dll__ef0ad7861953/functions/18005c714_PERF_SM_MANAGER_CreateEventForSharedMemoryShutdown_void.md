# PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown(void)

- ea: `0x18005c714`
- end: `0x18005cd34`
- name: `?CreateEventForSharedMemoryShutdown@PERF_SM_MANAGER@@AEAAKXZ`
- size: `1568`
- prototype: `__int64 __fastcall(PERF_SM_MANAGER *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005d8e8`

## callees

- `0x18005c714`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cbe0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cbe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cc0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cc0a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005cb08`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005cb08`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005cb5e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005cb5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ccf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ccf2`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005cabf`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005cabf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005cd01`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005cd01`
- `iisutil!PuDbgPrintError` at `0x18005c847`
- `iisutil!PuDbgPrintError` at `0x18005c847`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c74d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c74d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c868`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c8af`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c8f9`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c943`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c98d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c9d7`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c868`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c8af`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c8f9`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c943`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c98d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005c9d7`
- `iisutil!FreeWellKnownSid` at `0x18005ccab`
- `iisutil!FreeWellKnownSid` at `0x18005ccb6`
- `iisutil!FreeWellKnownSid` at `0x18005ccc1`
- `iisutil!FreeWellKnownSid` at `0x18005cccc`
- `iisutil!FreeWellKnownSid` at `0x18005ccd7`
- `iisutil!FreeWellKnownSid` at `0x18005cce2`
- `iisutil!FreeWellKnownSid` at `0x18005ccab`
- `iisutil!FreeWellKnownSid` at `0x18005ccb6`
- `iisutil!FreeWellKnownSid` at `0x18005ccc1`
- `iisutil!FreeWellKnownSid` at `0x18005cccc`
- `iisutil!FreeWellKnownSid` at `0x18005ccd7`
- `iisutil!FreeWellKnownSid` at `0x18005cce2`
- `iisutil!GenerateNameWithGUID` at `0x18005cbc8`
- `iisutil!GenerateNameWithGUID` at `0x18005cbc8`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca3f`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca53`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca67`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca7b`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca92`
- `iisutil!SetExplicitAccessSettings` at `0x18005caa9`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca3f`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca53`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca67`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca7b`
- `iisutil!SetExplicitAccessSettings` at `0x18005ca92`
- `iisutil!SetExplicitAccessSettings` at `0x18005caa9`

## string_xrefs

- `0x18005cae4`: `Setting ACE's into ACL failed.\n`
- `0x18005c9fc`: `Creating Local System SID failed\n`
- `0x18005cb33`: `Initializing the security descriptor failed\n`
- `0x18005cb89`: `Setting the DACL on the security descriptor failed\n`
- `0x18005c8d4`: `Creating Power User SID failed\n`
- `0x18005c91e`: `Creating System Operators SID failed\n`
- `0x18005c9b2`: `Creating perf log user SID failed\n`
- `0x18005c968`: `Creating perf mon user SID failed\n`
- `0x18005c840`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005c88d`: `Creating Administrator SID failed\n`
- `0x18005c839`: `PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown`
- `0x18005cc41`: `Failed to create an event for shutting down shared memory\n`

## pseudocode

```c
__int64 __fastcall PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown(PERF_SM_MANAGER *this)
{
  __int64 v2; // r8
  const wchar_t *v3; // rcx
  __int64 v4; // r15
  __int64 v5; // rax
  _WORD *v6; // r8
  __int64 v7; // rsi
  __int64 v8; // r9
  _WORD *v9; // rcx
  unsigned int v10; // edx
  signed int NameWithGUID; // ebx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  __int64 v18; // rcx
  struct _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  signed int v20; // eax
  signed int v21; // eax
  signed int LastError; // eax
  int v23; // r14d
  HANDLE v24; // rax
  unsigned int v25; // eax
  LPCWSTR v26; // rcx
  _WORD *v27; // rax
  _WORD *v28; // rcx
  PACL NewAcl; // [rsp+30h] [rbp-D0h] BYREF
  void *v31; // [rsp+38h] [rbp-C8h] BYREF
  void *v32; // [rsp+40h] [rbp-C0h] BYREF
  void *v33; // [rsp+48h] [rbp-B8h] BYREF
  void *v34; // [rsp+50h] [rbp-B0h] BYREF
  void *v35; // [rsp+58h] [rbp-A8h] BYREF
  void *v36; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+68h] [rbp-98h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-60h]
  _BYTE v40[32]; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpName; // [rsp+C8h] [rbp-38h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+E0h] [rbp-20h] BYREF
  struct _EXPLICIT_ACCESS_W v43; // [rsp+110h] [rbp+10h] BYREF
  struct _EXPLICIT_ACCESS_W v44; // [rsp+140h] [rbp+40h] BYREF
  struct _EXPLICIT_ACCESS_W v45; // [rsp+170h] [rbp+70h] BYREF
  struct _EXPLICIT_ACCESS_W v46; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _EXPLICIT_ACCESS_W v47; // [rsp+1D0h] [rbp+D0h] BYREF

  STRU::STRU((STRU *)v40);
  v2 = *((_QWORD *)this + 2);
  v3 = L"NOT SET";
  v39 = 0;
  v4 = 1023;
  v31 = 0;
  v5 = 1023;
  v32 = 0;
  v33 = 0;
  v6 = (_WORD *)(v2 + 2056);
  v7 = 1024;
  v34 = 0;
  v8 = 1024;
  v35 = 0;
  v36 = 0;
  NewAcl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  do
  {
    if ( !v5 )
      break;
    if ( !*v3 )
      break;
    *v6++ = *v3++;
    --v5;
    --v8;
  }
  while ( v8 );
  v9 = v6 - 1;
  v10 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v9 = v6;
  *v9 = 0;
  if ( v8 )
  {
    *(_WORD *)(*((_QWORD *)this + 2) + 4102LL) = 0;
    v12 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v36);
    NameWithGUID = v12;
    if ( v12 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
          1636,
          "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
          v12,
          "Creating Administrator SID failed\n");
      }
    }
    else
    {
      v13 = AllocateAndCreateWellKnownSid(WinBuiltinPowerUsersSid, &v31);
      NameWithGUID = v13;
      if ( v13 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          if ( v13 > 0 )
            v13 = (unsigned __int16)v13 | 0x80070000;
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
            1653,
            "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
            v13,
            "Creating Power User SID failed\n");
        }
      }
      else
      {
        v14 = AllocateAndCreateWellKnownSid(WinBuiltinSystemOperatorsSid, &v32);
        NameWithGUID = v14;
        if ( v14 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
              1670,
              "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
              v14,
              "Creating System Operators SID failed\n");
          }
        }
        else
        {
          v15 = AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v33);
          NameWithGUID = v15;
          if ( v15 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              if ( v15 > 0 )
                v15 = (unsigned __int16)v15 | 0x80070000;
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                1686,
                "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                v15,
                "Creating perf mon user SID failed\n");
            }
          }
          else
          {
            v16 = AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &v34);
            NameWithGUID = v16;
            if ( v16 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                if ( v16 > 0 )
                  v16 = (unsigned __int16)v16 | 0x80070000;
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                  1703,
                  "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                  v16,
                  "Creating perf log user SID failed\n");
              }
            }
            else
            {
              v17 = AllocateAndCreateWellKnownSid(WinLocalSystemSid, &v35);
              NameWithGUID = v17;
              if ( v17 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  if ( v17 > 0 )
                    v17 = (unsigned __int16)v17 | 0x80070000;
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                    1720,
                    "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                    v17,
                    "Creating Local System SID failed\n");
                }
              }
              else
              {
                v18 = 288;
                p_pListOfExplicitEntries = &pListOfExplicitEntries;
                do
                {
                  LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
                  p_pListOfExplicitEntries = (struct _EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
                  --v18;
                }
                while ( v18 );
                SetExplicitAccessSettings(&pListOfExplicitEntries, 0x100000u, SET_ACCESS, v31);
                SetExplicitAccessSettings(&v43, 0x100000u, SET_ACCESS, v36);
                SetExplicitAccessSettings(&v44, 0x100000u, SET_ACCESS, v32);
                SetExplicitAccessSettings(&v45, 0x100000u, SET_ACCESS, v35);
                SetExplicitAccessSettings(&v46, 0x100000u, SET_ACCESS, v33);
                SetExplicitAccessSettings(&v47, 0x100000u, SET_ACCESS, v34);
                v20 = SetEntriesInAclW(6u, &pListOfExplicitEntries, 0, &NewAcl);
                NameWithGUID = v20;
                if ( v20 )
                {
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    if ( v20 > 0 )
                      v20 = (unsigned __int16)v20 | 0x80070000;
                    PuDbgPrintError(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                      1788,
                      "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                      v20,
                      "Setting ACE's into ACL failed.\n");
                  }
                }
                else if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
                {
                  if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
                  {
                    EventAttributes.nLength = 24;
                    EventAttributes.lpSecurityDescriptor = pSecurityDescriptor;
                    v23 = 0;
                    EventAttributes.bInheritHandle = 0;
                    while ( 1 )
                    {
                      NameWithGUID = GenerateNameWithGUID(L"Global\\WASPerfCount-", (struct STRU *)v40);
                      v24 = CreateEventW(&EventAttributes, 1, 0, lpName);
                      *((_QWORD *)this + 7) = v24;
                      if ( v24 )
                      {
                        if ( GetLastError() == 183 )
                        {
                          CloseHandle(*((HANDLE *)this + 7));
                          *((_QWORD *)this + 7) = 0;
                          NameWithGUID = 183;
                        }
                      }
                      else
                      {
                        NameWithGUID = GetLastError();
                      }
                      if ( *((_QWORD *)this + 7) )
                        break;
                      if ( (unsigned int)++v23 >= 0xA )
                      {
                        if ( (g_dwDebugFlags & 0xF) != 0 )
                        {
                          if ( NameWithGUID > 0 )
                            v25 = (unsigned __int16)NameWithGUID | 0x80070000;
                          else
                            v25 = NameWithGUID;
                          PuDbgPrintError(
                            g_pDebug,
                            "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                            1857,
                            "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                            v25,
                            "Failed to create an event for shutting down shared memory\n");
                        }
                        goto LABEL_76;
                      }
                    }
                    v26 = lpName;
                    v27 = (_WORD *)(*((_QWORD *)this + 2) + 2056LL);
                    do
                    {
                      if ( !v4 )
                        break;
                      if ( !*v26 )
                        break;
                      *v27++ = *v26++;
                      --v4;
                      --v7;
                    }
                    while ( v7 );
                    v28 = v27 - 1;
                    if ( v7 )
                      v28 = v27;
                    *v28 = 0;
                    *(_WORD *)(*((_QWORD *)this + 2) + 4102LL) = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    NameWithGUID = LastError;
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      if ( LastError > 0 )
                        LastError = (unsigned __int16)LastError | 0x80070000;
                      PuDbgPrintError(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                        1815,
                        "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                        LastError,
                        "Setting the DACL on the security descriptor failed\n");
                    }
                  }
                }
                else
                {
                  v21 = GetLastError();
                  NameWithGUID = v21;
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    if ( v21 > 0 )
                      v21 = (unsigned __int16)v21 | 0x80070000;
                    PuDbgPrintError(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                      1800,
                      "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
                      v21,
                      "Initializing the security descriptor failed\n");
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    NameWithGUID = (unsigned __int16)v10;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
        1610,
        "PERF_SM_MANAGER::CreateEventForSharedMemoryShutdown",
        v10,
        "String operation failed\n");
  }
LABEL_76:
  FreeWellKnownSid(&v31);
  FreeWellKnownSid(&v32);
  FreeWellKnownSid(&v33);
  FreeWellKnownSid(&v34);
  FreeWellKnownSid(&v35);
  FreeWellKnownSid(&v36);
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  STRU::~STRU((STRU *)v40);
  return (unsigned int)NameWithGUID;
}

```

## disassembly

```asm
0x18005c714  mov     [rsp-8+arg_8], rbx
0x18005c719  mov     [rsp-8+arg_10], rsi
0x18005c71e  push    rbp
0x18005c71f  push    rdi
0x18005c720  push    r12
0x18005c722  push    r14
0x18005c724  push    r15
0x18005c726  lea     rbp, [rsp-110h]
0x18005c72e  sub     rsp, 210h
0x18005c735  mov     rax, cs:__security_cookie
0x18005c73c  xor     rax, rsp
0x18005c73f  mov     [rbp+130h+var_30], rax
0x18005c746  mov     rdi, rcx
0x18005c749  lea     rcx, [rbp+130h+var_188]
0x18005c74d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18005c753  mov     r8, [rdi+10h]
0x18005c757  lea     rcx, aNotSet; "NOT SET"
0x18005c75e  xor     r12d, r12d
0x18005c761  xor     eax, eax
0x18005c763  xorps   xmm0, xmm0
0x18005c766  mov     [rbp+130h+var_190], rax
0x18005c76a  mov     r15d, 3FFh
0x18005c770  mov     qword ptr [rsp+230h+EventAttributes.bInheritHandle], rax
0x18005c775  mov     [rsp+230h+var_1F8], r12
0x18005c77a  mov     eax, r15d
0x18005c77d  mov     [rsp+230h+var_1F0], r12
0x18005c782  lea     r14d, [r12+2]
0x18005c787  mov     [rsp+230h+var_1E8], r12
0x18005c78c  add     r8, 808h
0x18005c793  lea     esi, [r15+1]
0x18005c797  mov     [rsp+230h+var_1E0], r12
0x18005c79c  mov     r9d, esi
0x18005c79f  mov     [rsp+230h+var_1D8], r12
0x18005c7a4  mov     [rsp+230h+var_1D0], r12
0x18005c7a9  mov     [rsp+230h+NewAcl], r12
0x18005c7ae  movups  [rbp+130h+pSecurityDescriptor], xmm0
0x18005c7b2  movups  [rbp+130h+var_1A0], xmm0
0x18005c7b6  movups  xmmword ptr [rsp+230h+EventAttributes.nLength], xmm0
0x18005c7bb  test    rax, rax
0x18005c7be  jz      short loc_18005C7DB
0x18005c7c0  movzx   edx, word ptr [rcx]
0x18005c7c3  test    dx, dx
0x18005c7c6  jz      short loc_18005C7DB
0x18005c7c8  mov     [r8], dx
0x18005c7cc  add     rcx, r14
0x18005c7cf  add     r8, r14
0x18005c7d2  dec     rax
0x18005c7d5  sub     r9, 1
0x18005c7d9  jnz     short loc_18005C7BB
0x18005c7db  mov     rax, r9
0x18005c7de  lea     rcx, [r8-2]
0x18005c7e2  neg     rax
0x18005c7e5  sbb     edx, edx
0x18005c7e7  not     edx
0x18005c7e9  and     edx, 8007007Ah
0x18005c7ef  test    r9, r9
0x18005c7f2  cmovnz  rcx, r8
0x18005c7f6  mov     [rcx], r12w
0x18005c7fa  jnz     short loc_18005C852
0x18005c7fc  mov     eax, edx
0x18005c7fe  movzx   ebx, dx
0x18005c801  and     eax, 1FFF0000h
0x18005c806  cmp     eax, 70000h
0x18005c80b  jz      short loc_18005C80F
0x18005c80d  mov     ebx, edx
0x18005c80f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c816  jz      loc_18005CCA6
0x18005c81c  lea     rax, aStringOperatio; "String operation failed\n"
0x18005c823  mov     r8d, 64Ah
0x18005c829  mov     [rsp+230h+var_208], rax
0x18005c82e  mov     [rsp+230h+var_210], edx
0x18005c832  mov     rcx, cs:g_pDebug
0x18005c839  lea     r9, aPerfSmManagerC; "PERF_SM_MANAGER::CreateEventForSharedMe"...
0x18005c840  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005c847  call    cs:__imp_PuDbgPrintError
0x18005c84d  jmp     loc_18005CCA6
0x18005c852  mov     rcx, [rdi+10h]
0x18005c856  lea     rdx, [rsp+230h+var_1D0]
0x18005c85b  mov     [rcx+1006h], r12w
0x18005c863  mov     ecx, 1Ah
0x18005c868  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c86e  mov     ebx, eax
0x18005c870  test    eax, eax
0x18005c872  jz      short loc_18005C8A5
0x18005c874  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c87b  jz      loc_18005CCA6
0x18005c881  test    eax, eax
0x18005c883  jle     short loc_18005C88D
0x18005c885  movzx   eax, ax
0x18005c888  or      eax, 80070000h
0x18005c88d  lea     rcx, aCreatingAdmini; "Creating Administrator SID failed\n"
0x18005c894  mov     r8d, 664h
0x18005c89a  mov     [rsp+230h+var_208], rcx
0x18005c89f  mov     [rsp+230h+var_210], eax
0x18005c8a3  jmp     short loc_18005C832
0x18005c8a5  lea     rdx, [rsp+230h+var_1F8]
0x18005c8aa  mov     ecx, 1Dh
0x18005c8af  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c8b5  mov     ebx, eax
0x18005c8b7  test    eax, eax
0x18005c8b9  jz      short loc_18005C8EF
0x18005c8bb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c8c2  jz      loc_18005CCA6
0x18005c8c8  test    eax, eax
0x18005c8ca  jle     short loc_18005C8D4
0x18005c8cc  movzx   eax, ax
0x18005c8cf  or      eax, 80070000h
0x18005c8d4  lea     rcx, aCreatingPowerU; "Creating Power User SID failed\n"
0x18005c8db  mov     r8d, 675h
0x18005c8e1  mov     [rsp+230h+var_208], rcx
0x18005c8e6  mov     [rsp+230h+var_210], eax
0x18005c8ea  jmp     loc_18005C832
0x18005c8ef  lea     rdx, [rsp+230h+var_1F0]
0x18005c8f4  mov     ecx, 1Fh
0x18005c8f9  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c8ff  mov     ebx, eax
0x18005c901  test    eax, eax
0x18005c903  jz      short loc_18005C939
0x18005c905  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c90c  jz      loc_18005CCA6
0x18005c912  test    eax, eax
0x18005c914  jle     short loc_18005C91E
0x18005c916  movzx   eax, ax
0x18005c919  or      eax, 80070000h
0x18005c91e  lea     rcx, aCreatingSystem; "Creating System Operators SID failed\n"
0x18005c925  mov     r8d, 686h
0x18005c92b  mov     [rsp+230h+var_208], rcx
0x18005c930  mov     [rsp+230h+var_210], eax
0x18005c934  jmp     loc_18005C832
0x18005c939  lea     rdx, [rsp+230h+var_1E8]
0x18005c93e  mov     ecx, 39h ; '9'
0x18005c943  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c949  mov     ebx, eax
0x18005c94b  test    eax, eax
0x18005c94d  jz      short loc_18005C983
0x18005c94f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c956  jz      loc_18005CCA6
0x18005c95c  test    eax, eax
0x18005c95e  jle     short loc_18005C968
0x18005c960  movzx   eax, ax
0x18005c963  or      eax, 80070000h
0x18005c968  lea     rcx, aCreatingPerfMo; "Creating perf mon user SID failed\n"
0x18005c96f  mov     r8d, 696h
0x18005c975  mov     [rsp+230h+var_208], rcx
0x18005c97a  mov     [rsp+230h+var_210], eax
0x18005c97e  jmp     loc_18005C832
0x18005c983  lea     rdx, [rsp+230h+var_1E0]
0x18005c988  mov     ecx, 3Ah ; ':'
0x18005c98d  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c993  mov     ebx, eax
0x18005c995  test    eax, eax
0x18005c997  jz      short loc_18005C9CD
0x18005c999  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c9a0  jz      loc_18005CCA6
0x18005c9a6  test    eax, eax
0x18005c9a8  jle     short loc_18005C9B2
0x18005c9aa  movzx   eax, ax
0x18005c9ad  or      eax, 80070000h
0x18005c9b2  lea     rcx, aCreatingPerfLo; "Creating perf log user SID failed\n"
0x18005c9b9  mov     r8d, 6A7h
0x18005c9bf  mov     [rsp+230h+var_208], rcx
0x18005c9c4  mov     [rsp+230h+var_210], eax
0x18005c9c8  jmp     loc_18005C832
0x18005c9cd  lea     rdx, [rsp+230h+var_1D8]
0x18005c9d2  mov     ecx, 16h
0x18005c9d7  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005c9dd  mov     ebx, eax
0x18005c9df  test    eax, eax
0x18005c9e1  jz      short loc_18005CA17
0x18005c9e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c9ea  jz      loc_18005CCA6
0x18005c9f0  test    eax, eax
0x18005c9f2  jle     short loc_18005C9FC
0x18005c9f4  movzx   eax, ax
0x18005c9f7  or      eax, 80070000h
0x18005c9fc  lea     rcx, aCreatingLocalS; "Creating Local System SID failed\n"
0x18005ca03  mov     r8d, 6B8h
0x18005ca09  mov     [rsp+230h+var_208], rcx
0x18005ca0e  mov     [rsp+230h+var_210], eax
0x18005ca12  jmp     loc_18005C832
0x18005ca17  mov     ecx, 120h
0x18005ca1c  lea     rax, [rbp+130h+pListOfExplicitEntries]
0x18005ca20  mov     [rax], r12b
0x18005ca23  inc     rax
0x18005ca26  sub     rcx, 1
0x18005ca2a  jnz     short loc_18005CA20
0x18005ca2c  mov     r9, [rsp+230h+var_1F8]
0x18005ca31  lea     rcx, [rbp+130h+pListOfExplicitEntries]
0x18005ca35  mov     ebx, 100000h
0x18005ca3a  mov     r8d, r14d
0x18005ca3d  mov     edx, ebx
0x18005ca3f  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005ca45  mov     r9, [rsp+230h+var_1D0]
0x18005ca4a  lea     rcx, [rbp+130h+var_120]
0x18005ca4e  mov     r8d, r14d
0x18005ca51  mov     edx, ebx
0x18005ca53  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005ca59  mov     r9, [rsp+230h+var_1F0]
0x18005ca5e  lea     rcx, [rbp+130h+var_F0]
0x18005ca62  mov     r8d, r14d
0x18005ca65  mov     edx, ebx
0x18005ca67  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005ca6d  mov     r9, [rsp+230h+var_1D8]
0x18005ca72  lea     rcx, [rbp+130h+var_C0]
0x18005ca76  mov     r8d, r14d
0x18005ca79  mov     edx, ebx
0x18005ca7b  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005ca81  mov     r9, [rsp+230h+var_1E8]
0x18005ca86  lea     rcx, [rbp+130h+var_90]
0x18005ca8d  mov     r8d, r14d
0x18005ca90  mov     edx, ebx
0x18005ca92  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005ca98  mov     r9, [rsp+230h+var_1E0]
0x18005ca9d  lea     rcx, [rbp+130h+var_60]
0x18005caa4  mov     r8d, r14d
0x18005caa7  mov     edx, ebx
0x18005caa9  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005caaf  xor     r8d, r8d; OldAcl
0x18005cab2  lea     r9, [rsp+230h+NewAcl]; NewAcl
0x18005cab7  lea     rdx, [rbp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005cabb  lea     ecx, [r8+6]; cCountOfExplicitEntries
0x18005cabf  call    cs:__imp_SetEntriesInAclW
0x18005cac5  mov     ebx, eax
0x18005cac7  test    eax, eax
0x18005cac9  jz      short loc_18005CAFF
0x18005cacb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cad2  jz      loc_18005CCA6
0x18005cad8  test    eax, eax
0x18005cada  jle     short loc_18005CAE4
0x18005cadc  movzx   eax, ax
0x18005cadf  or      eax, 80070000h
0x18005cae4  lea     rcx, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18005caeb  mov     r8d, 6FCh
0x18005caf1  mov     [rsp+230h+var_208], rcx
0x18005caf6  mov     [rsp+230h+var_210], eax
0x18005cafa  jmp     loc_18005C832
0x18005caff  mov     edx, 1; dwRevision
0x18005cb04  lea     rcx, [rbp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x18005cb08  call    cs:__imp_InitializeSecurityDescriptor
0x18005cb0e  test    eax, eax
0x18005cb10  jnz     short loc_18005CB4E
0x18005cb12  call    cs:__imp_GetLastError
0x18005cb18  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cb1f  mov     ebx, eax
0x18005cb21  jz      loc_18005CCA6
0x18005cb27  test    eax, eax
0x18005cb29  jle     short loc_18005CB33
0x18005cb2b  movzx   eax, ax
0x18005cb2e  or      eax, 80070000h
0x18005cb33  lea     rcx, aInitializingTh_0; "Initializing the security descriptor fa"...
0x18005cb3a  mov     r8d, 708h
0x18005cb40  mov     [rsp+230h+var_208], rcx
0x18005cb45  mov     [rsp+230h+var_210], eax
0x18005cb49  jmp     loc_18005C832
0x18005cb4e  mov     r8, [rsp+230h+NewAcl]; pDacl
0x18005cb53  lea     rcx, [rbp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x18005cb57  xor     r9d, r9d; bDaclDefaulted
0x18005cb5a  lea     edx, [r9+1]; bDaclPresent
0x18005cb5e  call    cs:__imp_SetSecurityDescriptorDacl
0x18005cb64  test    eax, eax
0x18005cb66  jnz     short loc_18005CBA4
0x18005cb68  call    cs:__imp_GetLastError
0x18005cb6e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cb75  mov     ebx, eax
0x18005cb77  jz      loc_18005CCA6
0x18005cb7d  test    eax, eax
0x18005cb7f  jle     short loc_18005CB89
0x18005cb81  movzx   eax, ax
0x18005cb84  or      eax, 80070000h
0x18005cb89  lea     rcx, aSettingTheDacl; "Setting the DACL on the security descri"...
0x18005cb90  mov     r8d, 717h
0x18005cb96  mov     [rsp+230h+var_208], rcx
0x18005cb9b  mov     [rsp+230h+var_210], eax
0x18005cb9f  jmp     loc_18005C832
0x18005cba4  lea     rax, [rbp+130h+pSecurityDescriptor]
0x18005cba8  mov     [rsp+230h+EventAttributes.nLength], 18h
0x18005cbb0  mov     [rsp+230h+EventAttributes.lpSecurityDescriptor], rax
0x18005cbb5  mov     r14d, r12d
0x18005cbb8  mov     [rsp+230h+EventAttributes.bInheritHandle], r12d
0x18005cbbd  lea     rdx, [rbp+130h+var_188]
0x18005cbc1  lea     rcx, aGlobalWasperfc; "Global\\WASPerfCount-"
0x18005cbc8  call    cs:__imp_?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z; GenerateNameWithGUID(ushort const *,STRU *)
0x18005cbce  mov     r9, [rbp+130h+lpName]; lpName
0x18005cbd2  lea     rcx, [rsp+230h+EventAttributes]; lpEventAttributes
0x18005cbd7  xor     r8d, r8d; bInitialState
0x18005cbda  mov     ebx, eax
0x18005cbdc  lea     edx, [r8+1]; bManualReset
0x18005cbe0  call    cs:__imp_CreateEventW
0x18005cbe6  mov     [rdi+38h], rax
0x18005cbea  test    rax, rax
0x18005cbed  jnz     short loc_18005CBF9
0x18005cbef  call    cs:__imp_GetLastError
0x18005cbf5  mov     ebx, eax
0x18005cbf7  jmp     short loc_18005CC19
0x18005cbf9  call    cs:__imp_GetLastError
0x18005cbff  cmp     eax, 0B7h
0x18005cc04  jnz     short loc_18005CC19
0x18005cc06  mov     rcx, [rdi+38h]; hObject
0x18005cc0a  call    cs:__imp_CloseHandle
0x18005cc10  mov     [rdi+38h], r12
  ... truncated ...
```
