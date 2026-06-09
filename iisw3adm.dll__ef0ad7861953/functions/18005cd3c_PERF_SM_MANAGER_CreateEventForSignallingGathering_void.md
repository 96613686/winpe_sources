# PERF_SM_MANAGER::CreateEventForSignallingGathering(void)

- ea: `0x18005cd3c`
- end: `0x18005d35a`
- name: `?CreateEventForSignallingGathering@PERF_SM_MANAGER@@AEAAKXZ`
- size: `1566`
- prototype: `__int64 __fastcall(PERF_SM_MANAGER *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005d8e8`

## callees

- `0x18005cd3c`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d208`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005d208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d13a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d232`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005d130`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005d130`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005d186`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005d186`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d318`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d318`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005d0e7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005d0e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005d327`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005d327`
- `iisutil!PuDbgPrintError` at `0x18005ce6c`
- `iisutil!PuDbgPrintError` at `0x18005ce6c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005cd75`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005cd75`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005ce8d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005ced4`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cf1e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cf68`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cfb2`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cffc`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005ce8d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005ced4`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cf1e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cf68`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cfb2`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005cffc`
- `iisutil!FreeWellKnownSid` at `0x18005d2d1`
- `iisutil!FreeWellKnownSid` at `0x18005d2dc`
- `iisutil!FreeWellKnownSid` at `0x18005d2e7`
- `iisutil!FreeWellKnownSid` at `0x18005d2f2`
- `iisutil!FreeWellKnownSid` at `0x18005d2fd`
- `iisutil!FreeWellKnownSid` at `0x18005d308`
- `iisutil!FreeWellKnownSid` at `0x18005d2d1`
- `iisutil!FreeWellKnownSid` at `0x18005d2dc`
- `iisutil!FreeWellKnownSid` at `0x18005d2e7`
- `iisutil!FreeWellKnownSid` at `0x18005d2f2`
- `iisutil!FreeWellKnownSid` at `0x18005d2fd`
- `iisutil!FreeWellKnownSid` at `0x18005d308`
- `iisutil!GenerateNameWithGUID` at `0x18005d1f0`
- `iisutil!GenerateNameWithGUID` at `0x18005d1f0`
- `iisutil!SetExplicitAccessSettings` at `0x18005d060`
- `iisutil!SetExplicitAccessSettings` at `0x18005d075`
- `iisutil!SetExplicitAccessSettings` at `0x18005d08a`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0a1`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0b9`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0d1`
- `iisutil!SetExplicitAccessSettings` at `0x18005d060`
- `iisutil!SetExplicitAccessSettings` at `0x18005d075`
- `iisutil!SetExplicitAccessSettings` at `0x18005d08a`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0a1`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0b9`
- `iisutil!SetExplicitAccessSettings` at `0x18005d0d1`

## string_xrefs

- `0x18005d10c`: `Setting ACE's into ACL failed.\n`
- `0x18005d021`: `Creating Local System SID failed\n`
- `0x18005d15b`: `Initializing the security descriptor failed\n`
- `0x18005d1b1`: `Setting the DACL on the security descriptor failed\n`
- `0x18005cef9`: `Creating Power User SID failed\n`
- `0x18005cf43`: `Creating System Operators SID failed\n`
- `0x18005cfd7`: `Creating perf log user SID failed\n`
- `0x18005cf8d`: `Creating perf mon user SID failed\n`
- `0x18005ce65`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005ce41`: `String copy operation failed\n`
- `0x18005ce5e`: `PERF_SM_MANAGER::CreateEventForSignallingGathering`
- `0x18005ceb2`: `Creating Administrator SID failed\n`
- `0x18005d269`: `Failed to create an event for signalling counters\n`

## pseudocode

```c
__int64 __fastcall PERF_SM_MANAGER::CreateEventForSignallingGathering(PERF_SM_MANAGER *this)
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
  v6 = (_WORD *)(v2 + 8);
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
    *(_WORD *)(*((_QWORD *)this + 2) + 2054LL) = 0;
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
          1279,
          "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
            1296,
            "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
              1313,
              "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                1329,
                "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                  1346,
                  "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                    1363,
                    "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                SetExplicitAccessSettings(&pListOfExplicitEntries, 2u, SET_ACCESS, v31);
                SetExplicitAccessSettings(&v43, 2u, SET_ACCESS, v36);
                SetExplicitAccessSettings(&v44, 2u, SET_ACCESS, v32);
                SetExplicitAccessSettings(&v45, 0x1F0003u, SET_ACCESS, v35);
                SetExplicitAccessSettings(&v46, 2u, SET_ACCESS, v33);
                SetExplicitAccessSettings(&v47, 2u, SET_ACCESS, v34);
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
                      1431,
                      "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                      *((_QWORD *)this + 6) = v24;
                      if ( v24 )
                      {
                        if ( GetLastError() == 183 )
                        {
                          CloseHandle(*((HANDLE *)this + 6));
                          *((_QWORD *)this + 6) = 0;
                          NameWithGUID = 183;
                        }
                      }
                      else
                      {
                        NameWithGUID = GetLastError();
                      }
                      if ( *((_QWORD *)this + 6) )
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
                            1500,
                            "PERF_SM_MANAGER::CreateEventForSignallingGathering",
                            v25,
                            "Failed to create an event for signalling counters\n");
                        }
                        goto LABEL_76;
                      }
                    }
                    v26 = lpName;
                    v27 = (_WORD *)(*((_QWORD *)this + 2) + 8LL);
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
                    *(_WORD *)(*((_QWORD *)this + 2) + 2054LL) = 0;
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
                        1458,
                        "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
                      1443,
                      "PERF_SM_MANAGER::CreateEventForSignallingGathering",
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
        1254,
        "PERF_SM_MANAGER::CreateEventForSignallingGathering",
        v10,
        "String copy operation failed\n");
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
0x18005cd3c  mov     [rsp-8+arg_8], rbx
0x18005cd41  mov     [rsp-8+arg_10], rsi
0x18005cd46  push    rbp
0x18005cd47  push    rdi
0x18005cd48  push    r12
0x18005cd4a  push    r14
0x18005cd4c  push    r15
0x18005cd4e  lea     rbp, [rsp-110h]
0x18005cd56  sub     rsp, 210h
0x18005cd5d  mov     rax, cs:__security_cookie
0x18005cd64  xor     rax, rsp
0x18005cd67  mov     [rbp+130h+var_30], rax
0x18005cd6e  mov     rdi, rcx
0x18005cd71  lea     rcx, [rbp+130h+var_188]
0x18005cd75  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18005cd7b  mov     r8, [rdi+10h]
0x18005cd7f  lea     rcx, aNotSet; "NOT SET"
0x18005cd86  xor     r12d, r12d
0x18005cd89  xor     eax, eax
0x18005cd8b  xorps   xmm0, xmm0
0x18005cd8e  mov     [rbp+130h+var_190], rax
0x18005cd92  mov     r15d, 3FFh
0x18005cd98  mov     qword ptr [rsp+230h+EventAttributes.bInheritHandle], rax
0x18005cd9d  mov     [rsp+230h+var_1F8], r12
0x18005cda2  mov     eax, r15d
0x18005cda5  mov     [rsp+230h+var_1F0], r12
0x18005cdaa  lea     r14d, [r12+2]
0x18005cdaf  mov     [rsp+230h+var_1E8], r12
0x18005cdb4  add     r8, 8
0x18005cdb8  lea     esi, [r15+1]
0x18005cdbc  mov     [rsp+230h+var_1E0], r12
0x18005cdc1  mov     r9d, esi
0x18005cdc4  mov     [rsp+230h+var_1D8], r12
0x18005cdc9  mov     [rsp+230h+var_1D0], r12
0x18005cdce  mov     [rsp+230h+NewAcl], r12
0x18005cdd3  movups  [rbp+130h+pSecurityDescriptor], xmm0
0x18005cdd7  movups  [rbp+130h+var_1A0], xmm0
0x18005cddb  movups  xmmword ptr [rsp+230h+EventAttributes.nLength], xmm0
0x18005cde0  test    rax, rax
0x18005cde3  jz      short loc_18005CE00
0x18005cde5  movzx   edx, word ptr [rcx]
0x18005cde8  test    dx, dx
0x18005cdeb  jz      short loc_18005CE00
0x18005cded  mov     [r8], dx
0x18005cdf1  add     rcx, r14
0x18005cdf4  add     r8, r14
0x18005cdf7  dec     rax
0x18005cdfa  sub     r9, 1
0x18005cdfe  jnz     short loc_18005CDE0
0x18005ce00  mov     rax, r9
0x18005ce03  lea     rcx, [r8-2]
0x18005ce07  neg     rax
0x18005ce0a  sbb     edx, edx
0x18005ce0c  not     edx
0x18005ce0e  and     edx, 8007007Ah
0x18005ce14  test    r9, r9
0x18005ce17  cmovnz  rcx, r8
0x18005ce1b  mov     [rcx], r12w
0x18005ce1f  jnz     short loc_18005CE77
0x18005ce21  mov     eax, edx
0x18005ce23  movzx   ebx, dx
0x18005ce26  and     eax, 1FFF0000h
0x18005ce2b  cmp     eax, 70000h
0x18005ce30  jz      short loc_18005CE34
0x18005ce32  mov     ebx, edx
0x18005ce34  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005ce3b  jz      loc_18005D2CC
0x18005ce41  lea     rax, aStringCopyOper; "String copy operation failed\n"
0x18005ce48  mov     r8d, 4E6h
0x18005ce4e  mov     [rsp+230h+var_208], rax
0x18005ce53  mov     [rsp+230h+var_210], edx
0x18005ce57  mov     rcx, cs:g_pDebug
0x18005ce5e  lea     r9, aPerfSmManagerC_0; "PERF_SM_MANAGER::CreateEventForSignalli"...
0x18005ce65  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005ce6c  call    cs:__imp_PuDbgPrintError
0x18005ce72  jmp     loc_18005D2CC
0x18005ce77  mov     rcx, [rdi+10h]
0x18005ce7b  lea     rdx, [rsp+230h+var_1D0]
0x18005ce80  mov     [rcx+806h], r12w
0x18005ce88  mov     ecx, 1Ah
0x18005ce8d  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005ce93  mov     ebx, eax
0x18005ce95  test    eax, eax
0x18005ce97  jz      short loc_18005CECA
0x18005ce99  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cea0  jz      loc_18005D2CC
0x18005cea6  test    eax, eax
0x18005cea8  jle     short loc_18005CEB2
0x18005ceaa  movzx   eax, ax
0x18005cead  or      eax, 80070000h
0x18005ceb2  lea     rcx, aCreatingAdmini; "Creating Administrator SID failed\n"
0x18005ceb9  mov     r8d, 4FFh
0x18005cebf  mov     [rsp+230h+var_208], rcx
0x18005cec4  mov     [rsp+230h+var_210], eax
0x18005cec8  jmp     short loc_18005CE57
0x18005ceca  lea     rdx, [rsp+230h+var_1F8]
0x18005cecf  mov     ecx, 1Dh
0x18005ced4  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005ceda  mov     ebx, eax
0x18005cedc  test    eax, eax
0x18005cede  jz      short loc_18005CF14
0x18005cee0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cee7  jz      loc_18005D2CC
0x18005ceed  test    eax, eax
0x18005ceef  jle     short loc_18005CEF9
0x18005cef1  movzx   eax, ax
0x18005cef4  or      eax, 80070000h
0x18005cef9  lea     rcx, aCreatingPowerU; "Creating Power User SID failed\n"
0x18005cf00  mov     r8d, 510h
0x18005cf06  mov     [rsp+230h+var_208], rcx
0x18005cf0b  mov     [rsp+230h+var_210], eax
0x18005cf0f  jmp     loc_18005CE57
0x18005cf14  lea     rdx, [rsp+230h+var_1F0]
0x18005cf19  mov     ecx, 1Fh
0x18005cf1e  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005cf24  mov     ebx, eax
0x18005cf26  test    eax, eax
0x18005cf28  jz      short loc_18005CF5E
0x18005cf2a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cf31  jz      loc_18005D2CC
0x18005cf37  test    eax, eax
0x18005cf39  jle     short loc_18005CF43
0x18005cf3b  movzx   eax, ax
0x18005cf3e  or      eax, 80070000h
0x18005cf43  lea     rcx, aCreatingSystem; "Creating System Operators SID failed\n"
0x18005cf4a  mov     r8d, 521h
0x18005cf50  mov     [rsp+230h+var_208], rcx
0x18005cf55  mov     [rsp+230h+var_210], eax
0x18005cf59  jmp     loc_18005CE57
0x18005cf5e  lea     rdx, [rsp+230h+var_1E8]
0x18005cf63  mov     ecx, 39h ; '9'
0x18005cf68  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005cf6e  mov     ebx, eax
0x18005cf70  test    eax, eax
0x18005cf72  jz      short loc_18005CFA8
0x18005cf74  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cf7b  jz      loc_18005D2CC
0x18005cf81  test    eax, eax
0x18005cf83  jle     short loc_18005CF8D
0x18005cf85  movzx   eax, ax
0x18005cf88  or      eax, 80070000h
0x18005cf8d  lea     rcx, aCreatingPerfMo; "Creating perf mon user SID failed\n"
0x18005cf94  mov     r8d, 531h
0x18005cf9a  mov     [rsp+230h+var_208], rcx
0x18005cf9f  mov     [rsp+230h+var_210], eax
0x18005cfa3  jmp     loc_18005CE57
0x18005cfa8  lea     rdx, [rsp+230h+var_1E0]
0x18005cfad  mov     ecx, 3Ah ; ':'
0x18005cfb2  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005cfb8  mov     ebx, eax
0x18005cfba  test    eax, eax
0x18005cfbc  jz      short loc_18005CFF2
0x18005cfbe  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005cfc5  jz      loc_18005D2CC
0x18005cfcb  test    eax, eax
0x18005cfcd  jle     short loc_18005CFD7
0x18005cfcf  movzx   eax, ax
0x18005cfd2  or      eax, 80070000h
0x18005cfd7  lea     rcx, aCreatingPerfLo; "Creating perf log user SID failed\n"
0x18005cfde  mov     r8d, 542h
0x18005cfe4  mov     [rsp+230h+var_208], rcx
0x18005cfe9  mov     [rsp+230h+var_210], eax
0x18005cfed  jmp     loc_18005CE57
0x18005cff2  lea     rdx, [rsp+230h+var_1D8]
0x18005cff7  mov     ecx, 16h
0x18005cffc  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d002  mov     ebx, eax
0x18005d004  test    eax, eax
0x18005d006  jz      short loc_18005D03C
0x18005d008  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d00f  jz      loc_18005D2CC
0x18005d015  test    eax, eax
0x18005d017  jle     short loc_18005D021
0x18005d019  movzx   eax, ax
0x18005d01c  or      eax, 80070000h
0x18005d021  lea     rcx, aCreatingLocalS; "Creating Local System SID failed\n"
0x18005d028  mov     r8d, 553h
0x18005d02e  mov     [rsp+230h+var_208], rcx
0x18005d033  mov     [rsp+230h+var_210], eax
0x18005d037  jmp     loc_18005CE57
0x18005d03c  mov     ecx, 120h
0x18005d041  lea     rax, [rbp+130h+pListOfExplicitEntries]
0x18005d045  mov     [rax], r12b
0x18005d048  inc     rax
0x18005d04b  sub     rcx, 1
0x18005d04f  jnz     short loc_18005D045
0x18005d051  mov     r9, [rsp+230h+var_1F8]
0x18005d056  lea     rcx, [rbp+130h+pListOfExplicitEntries]
0x18005d05a  mov     r8d, r14d
0x18005d05d  mov     edx, r14d
0x18005d060  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d066  mov     r9, [rsp+230h+var_1D0]
0x18005d06b  lea     rcx, [rbp+130h+var_120]
0x18005d06f  mov     r8d, r14d
0x18005d072  mov     edx, r14d
0x18005d075  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d07b  mov     r9, [rsp+230h+var_1F0]
0x18005d080  lea     rcx, [rbp+130h+var_F0]
0x18005d084  mov     r8d, r14d
0x18005d087  mov     edx, r14d
0x18005d08a  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d090  mov     r9, [rsp+230h+var_1D8]
0x18005d095  lea     rcx, [rbp+130h+var_C0]
0x18005d099  mov     r8d, r14d
0x18005d09c  mov     edx, 1F0003h
0x18005d0a1  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d0a7  mov     r9, [rsp+230h+var_1E8]
0x18005d0ac  lea     rcx, [rbp+130h+var_90]
0x18005d0b3  mov     r8d, r14d
0x18005d0b6  mov     edx, r14d
0x18005d0b9  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d0bf  mov     r9, [rsp+230h+var_1E0]
0x18005d0c4  lea     rcx, [rbp+130h+var_60]
0x18005d0cb  mov     r8d, r14d
0x18005d0ce  mov     edx, r14d
0x18005d0d1  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d0d7  xor     r8d, r8d; OldAcl
0x18005d0da  lea     r9, [rsp+230h+NewAcl]; NewAcl
0x18005d0df  lea     rdx, [rbp+130h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005d0e3  lea     ecx, [r8+6]; cCountOfExplicitEntries
0x18005d0e7  call    cs:__imp_SetEntriesInAclW
0x18005d0ed  mov     ebx, eax
0x18005d0ef  test    eax, eax
0x18005d0f1  jz      short loc_18005D127
0x18005d0f3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d0fa  jz      loc_18005D2CC
0x18005d100  test    eax, eax
0x18005d102  jle     short loc_18005D10C
0x18005d104  movzx   eax, ax
0x18005d107  or      eax, 80070000h
0x18005d10c  lea     rcx, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18005d113  mov     r8d, 597h
0x18005d119  mov     [rsp+230h+var_208], rcx
0x18005d11e  mov     [rsp+230h+var_210], eax
0x18005d122  jmp     loc_18005CE57
0x18005d127  mov     edx, 1; dwRevision
0x18005d12c  lea     rcx, [rbp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x18005d130  call    cs:__imp_InitializeSecurityDescriptor
0x18005d136  test    eax, eax
0x18005d138  jnz     short loc_18005D176
0x18005d13a  call    cs:__imp_GetLastError
0x18005d140  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d147  mov     ebx, eax
0x18005d149  jz      loc_18005D2CC
0x18005d14f  test    eax, eax
0x18005d151  jle     short loc_18005D15B
0x18005d153  movzx   eax, ax
0x18005d156  or      eax, 80070000h
0x18005d15b  lea     rcx, aInitializingTh_0; "Initializing the security descriptor fa"...
0x18005d162  mov     r8d, 5A3h
0x18005d168  mov     [rsp+230h+var_208], rcx
0x18005d16d  mov     [rsp+230h+var_210], eax
0x18005d171  jmp     loc_18005CE57
0x18005d176  mov     r8, [rsp+230h+NewAcl]; pDacl
0x18005d17b  lea     rcx, [rbp+130h+pSecurityDescriptor]; pSecurityDescriptor
0x18005d17f  xor     r9d, r9d; bDaclDefaulted
0x18005d182  lea     edx, [r9+1]; bDaclPresent
0x18005d186  call    cs:__imp_SetSecurityDescriptorDacl
0x18005d18c  test    eax, eax
0x18005d18e  jnz     short loc_18005D1CC
0x18005d190  call    cs:__imp_GetLastError
0x18005d196  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d19d  mov     ebx, eax
0x18005d19f  jz      loc_18005D2CC
0x18005d1a5  test    eax, eax
0x18005d1a7  jle     short loc_18005D1B1
0x18005d1a9  movzx   eax, ax
0x18005d1ac  or      eax, 80070000h
0x18005d1b1  lea     rcx, aSettingTheDacl; "Setting the DACL on the security descri"...
0x18005d1b8  mov     r8d, 5B2h
0x18005d1be  mov     [rsp+230h+var_208], rcx
0x18005d1c3  mov     [rsp+230h+var_210], eax
0x18005d1c7  jmp     loc_18005CE57
0x18005d1cc  lea     rax, [rbp+130h+pSecurityDescriptor]
0x18005d1d0  mov     [rsp+230h+EventAttributes.nLength], 18h
0x18005d1d8  mov     [rsp+230h+EventAttributes.lpSecurityDescriptor], rax
0x18005d1dd  mov     r14d, r12d
0x18005d1e0  mov     [rsp+230h+EventAttributes.bInheritHandle], r12d
0x18005d1e5  lea     rdx, [rbp+130h+var_188]
0x18005d1e9  lea     rcx, aGlobalWasperfc; "Global\\WASPerfCount-"
0x18005d1f0  call    cs:__imp_?GenerateNameWithGUID@@YAKPEBGPEAVSTRU@@@Z; GenerateNameWithGUID(ushort const *,STRU *)
0x18005d1f6  mov     r9, [rbp+130h+lpName]; lpName
0x18005d1fa  lea     rcx, [rsp+230h+EventAttributes]; lpEventAttributes
0x18005d1ff  xor     r8d, r8d; bInitialState
0x18005d202  mov     ebx, eax
0x18005d204  lea     edx, [r8+1]; bManualReset
0x18005d208  call    cs:__imp_CreateEventW
0x18005d20e  mov     [rdi+30h], rax
0x18005d212  test    rax, rax
0x18005d215  jnz     short loc_18005D221
0x18005d217  call    cs:__imp_GetLastError
0x18005d21d  mov     ebx, eax
0x18005d21f  jmp     short loc_18005D241
0x18005d221  call    cs:__imp_GetLastError
0x18005d227  cmp     eax, 0B7h
0x18005d22c  jnz     short loc_18005D241
0x18005d22e  mov     rcx, [rdi+30h]; hObject
0x18005d232  call    cs:__imp_CloseHandle
0x18005d238  mov     [rdi+30h], r12
0x18005d23c  mov     ebx, 0B7h
  ... truncated ...
```
