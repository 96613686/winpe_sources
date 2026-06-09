# CreateMemoryFile(ushort const *,ulong,void * *,void * *)

- ea: `0x18005d360`
- end: `0x18005d82d`
- name: `?CreateMemoryFile@@YAKPEBGKPEAPEAX1@Z`
- size: `1229`
- prototype: `__int64 __fastcall(LPCWSTR lpName, DWORD dwMaximumSizeLow, void **, const void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005c69c`
- `0x18005d8e8`

## callees

- `0x18005d360`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d77d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d77d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d7fa`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005d690`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005d690`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005d6db`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005d6db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d7d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005d7d1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005d747`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005d747`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005d76f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005d76f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005d3e5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005d7ec`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005d3e5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005d7ec`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005d64e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18005d64e`
- `iisutil!PuDbgPrintError` at `0x18005d459`
- `iisutil!PuDbgPrintError` at `0x18005d459`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d409`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d46e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d4ac`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d4ed`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d52e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d56f`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d409`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d46e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d4ac`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d4ed`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d52e`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18005d56f`
- `iisutil!FreeWellKnownSid` at `0x18005d78a`
- `iisutil!FreeWellKnownSid` at `0x18005d795`
- `iisutil!FreeWellKnownSid` at `0x18005d7a0`
- `iisutil!FreeWellKnownSid` at `0x18005d7ab`
- `iisutil!FreeWellKnownSid` at `0x18005d7b6`
- `iisutil!FreeWellKnownSid` at `0x18005d7c1`
- `iisutil!FreeWellKnownSid` at `0x18005d78a`
- `iisutil!FreeWellKnownSid` at `0x18005d795`
- `iisutil!FreeWellKnownSid` at `0x18005d7a0`
- `iisutil!FreeWellKnownSid` at `0x18005d7ab`
- `iisutil!FreeWellKnownSid` at `0x18005d7b6`
- `iisutil!FreeWellKnownSid` at `0x18005d7c1`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5cb`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5e0`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5f5`
- `iisutil!SetExplicitAccessSettings` at `0x18005d60c`
- `iisutil!SetExplicitAccessSettings` at `0x18005d621`
- `iisutil!SetExplicitAccessSettings` at `0x18005d639`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5cb`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5e0`
- `iisutil!SetExplicitAccessSettings` at `0x18005d5f5`
- `iisutil!SetExplicitAccessSettings` at `0x18005d60c`
- `iisutil!SetExplicitAccessSettings` at `0x18005d621`
- `iisutil!SetExplicitAccessSettings` at `0x18005d639`

## string_xrefs

- `0x18005d673`: `Setting ACE's into ACL failed.\n`
- `0x18005d594`: `Creating Local System SID failed\n`
- `0x18005d6bb`: `Initializing the security descriptor failed\n`
- `0x18005d706`: `Setting the DACL on the security descriptor failed\n`
- `0x18005d493`: `Creating Power User SID failed\n`
- `0x18005d4d1`: `Creating System Operators SID failed\n`
- `0x18005d553`: `Creating perf log user SID failed\n`
- `0x18005d512`: `Creating perf mon user SID failed\n`
- `0x18005d44e`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005d42e`: `Creating Administrator SID failed\n`
- `0x18005d440`: `CreateMemoryFile`

## pseudocode

```c
__int64 __fastcall CreateMemoryFile(LPCWSTR lpName, DWORD dwMaximumSizeLow, void **a3, const void **a4)
{
  const void *v5; // rcx
  HANDLE v9; // rsi
  const void *v10; // rdi
  signed int v11; // eax
  DWORD LastError; // ebx
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  PACL NewAcl; // [rsp+30h] [rbp-D0h] BYREF
  void *v23; // [rsp+38h] [rbp-C8h] BYREF
  void *v24; // [rsp+40h] [rbp-C0h] BYREF
  void *v25; // [rsp+48h] [rbp-B8h] BYREF
  void *v26; // [rsp+50h] [rbp-B0h] BYREF
  void *v27; // [rsp+58h] [rbp-A8h] BYREF
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+68h] [rbp-98h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+A0h] [rbp-60h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W v33; // [rsp+E0h] [rbp-20h] BYREF
  struct _EXPLICIT_ACCESS_W v34; // [rsp+110h] [rbp+10h] BYREF
  struct _EXPLICIT_ACCESS_W v35; // [rsp+140h] [rbp+40h] BYREF
  struct _EXPLICIT_ACCESS_W v36; // [rsp+170h] [rbp+70h] BYREF
  struct _EXPLICIT_ACCESS_W v37; // [rsp+1A0h] [rbp+A0h] BYREF

  v23 = 0;
  v27 = 0;
  v5 = *a4;
  v28 = 0;
  v24 = 0;
  v25 = 0;
  v9 = 0;
  v26 = 0;
  v10 = 0;
  NewAcl = 0;
  v31 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  if ( v5 )
  {
    UnmapViewOfFile(v5);
    *a4 = 0;
  }
  if ( *a3 )
  {
    CloseHandle(*a3);
    *a3 = 0;
  }
  v11 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &v26);
  LastError = v11;
  if ( v11 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
        3744,
        "CreateMemoryFile",
        v11,
        "Creating Administrator SID failed\n");
    }
  }
  else
  {
    v13 = AllocateAndCreateWellKnownSid(WinBuiltinPowerUsersSid, &v23);
    LastError = v13;
    if ( v13 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
          3760,
          "CreateMemoryFile",
          v13,
          "Creating Power User SID failed\n");
      }
    }
    else
    {
      v14 = AllocateAndCreateWellKnownSid(WinBuiltinSystemOperatorsSid, &v24);
      LastError = v14;
      if ( v14 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
            3777,
            "CreateMemoryFile",
            v14,
            "Creating System Operators SID failed\n");
        }
      }
      else
      {
        v15 = AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v27);
        LastError = v15;
        if ( v15 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            if ( v15 > 0 )
              v15 = (unsigned __int16)v15 | 0x80070000;
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
              3793,
              "CreateMemoryFile",
              v15,
              "Creating perf mon user SID failed\n");
          }
        }
        else
        {
          v16 = AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &v28);
          LastError = v16;
          if ( v16 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              if ( v16 > 0 )
                v16 = (unsigned __int16)v16 | 0x80070000;
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                3810,
                "CreateMemoryFile",
                v16,
                "Creating perf log user SID failed\n");
            }
          }
          else
          {
            v17 = AllocateAndCreateWellKnownSid(WinLocalSystemSid, &v25);
            LastError = v17;
            if ( v17 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                if ( v17 > 0 )
                  v17 = (unsigned __int16)v17 | 0x80070000;
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                  3827,
                  "CreateMemoryFile",
                  v17,
                  "Creating Local System SID failed\n");
              }
            }
            else
            {
              memset_0(&pListOfExplicitEntries, 0, 0x120u);
              SetExplicitAccessSettings(&pListOfExplicitEntries, 4u, SET_ACCESS, v23);
              SetExplicitAccessSettings(&v33, 4u, SET_ACCESS, v26);
              SetExplicitAccessSettings(&v34, 4u, SET_ACCESS, v24);
              SetExplicitAccessSettings(&v35, 0xF001Fu, SET_ACCESS, v25);
              SetExplicitAccessSettings(&v36, 4u, SET_ACCESS, v27);
              SetExplicitAccessSettings(&v37, 4u, SET_ACCESS, v28);
              v18 = SetEntriesInAclW(6u, &pListOfExplicitEntries, 0, &NewAcl);
              LastError = v18;
              if ( v18 )
              {
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  if ( v18 > 0 )
                    v18 = (unsigned __int16)v18 | 0x80070000;
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                    3900,
                    "CreateMemoryFile",
                    v18,
                    "Setting ACE's into ACL failed.\n");
                }
              }
              else if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
              {
                if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
                {
                  FileMappingAttributes.nLength = 24;
                  FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
                  FileMappingAttributes.bInheritHandle = 0;
                  v9 = CreateFileMappingW(
                         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                         &FileMappingAttributes,
                         4u,
                         0,
                         dwMaximumSizeLow,
                         lpName);
                  LastError = GetLastError();
                  if ( !LastError )
                  {
                    v10 = MapViewOfFile(v9, 0xF001Fu, 0, 0, 0);
                    if ( !v10 )
                      LastError = GetLastError();
                  }
                }
                else
                {
                  v20 = GetLastError();
                  LastError = v20;
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    if ( v20 > 0 )
                      v20 = (unsigned __int16)v20 | 0x80070000;
                    PuDbgPrintError(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                      3927,
                      "CreateMemoryFile",
                      v20,
                      "Setting the DACL on the security descriptor failed\n");
                  }
                }
              }
              else
              {
                v19 = GetLastError();
                LastError = v19;
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  if ( v19 > 0 )
                    v19 = (unsigned __int16)v19 | 0x80070000;
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
                    3912,
                    "CreateMemoryFile",
                    v19,
                    "Initializing the security descriptor failed\n");
                }
              }
            }
          }
        }
      }
    }
  }
  FreeWellKnownSid(&v23);
  FreeWellKnownSid(&v24);
  FreeWellKnownSid(&v25);
  FreeWellKnownSid(&v26);
  FreeWellKnownSid(&v27);
  FreeWellKnownSid(&v28);
  if ( NewAcl )
  {
    LocalFree(NewAcl);
    NewAcl = 0;
  }
  if ( LastError )
  {
    if ( v10 )
      UnmapViewOfFile(v10);
    if ( v9 )
      CloseHandle(v9);
  }
  else
  {
    *a4 = v10;
    *a3 = v9;
  }
  return LastError;
}

```

## disassembly

```asm
0x18005d360  push    rbp
0x18005d362  push    rbx
0x18005d363  push    rsi
0x18005d364  push    rdi
0x18005d365  push    r12
0x18005d367  push    r13
0x18005d369  push    r14
0x18005d36b  push    r15
0x18005d36d  lea     rbp, [rsp-0E8h]
0x18005d375  sub     rsp, 1E8h
0x18005d37c  mov     rax, cs:__security_cookie
0x18005d383  xor     rax, rsp
0x18005d386  mov     [rbp+120h+var_50], rax
0x18005d38d  xor     ebx, ebx
0x18005d38f  xor     eax, eax
0x18005d391  xorps   xmm0, xmm0
0x18005d394  mov     [rsp+220h+var_1E8], rbx
0x18005d399  mov     r12, rcx
0x18005d39c  mov     [rsp+220h+var_1C8], rbx
0x18005d3a1  mov     rcx, [r9]; lpBaseAddress
0x18005d3a4  mov     r15, r9
0x18005d3a7  mov     [rsp+220h+var_1C0], rbx
0x18005d3ac  mov     r14, r8
0x18005d3af  mov     [rsp+220h+var_1E0], rbx
0x18005d3b4  mov     r13d, edx
0x18005d3b7  mov     [rsp+220h+var_1D8], rbx
0x18005d3bc  mov     esi, ebx
0x18005d3be  mov     [rsp+220h+var_1D0], rbx
0x18005d3c3  mov     edi, ebx
0x18005d3c5  mov     [rsp+220h+NewAcl], rbx
0x18005d3ca  mov     [rbp+120h+var_180], rax
0x18005d3ce  mov     qword ptr [rsp+220h+FileMappingAttributes.bInheritHandle], rax
0x18005d3d3  movups  [rbp+120h+pSecurityDescriptor], xmm0
0x18005d3d7  movups  [rbp+120h+var_190], xmm0
0x18005d3db  movups  xmmword ptr [rsp+220h+FileMappingAttributes.nLength], xmm0
0x18005d3e0  test    rcx, rcx
0x18005d3e3  jz      short loc_18005D3EE
0x18005d3e5  call    cs:__imp_UnmapViewOfFile
0x18005d3eb  mov     [r15], rbx
0x18005d3ee  mov     rcx, [r14]; hObject
0x18005d3f1  test    rcx, rcx
0x18005d3f4  jz      short loc_18005D3FF
0x18005d3f6  call    cs:__imp_CloseHandle
0x18005d3fc  mov     [r14], rbx
0x18005d3ff  lea     rdx, [rsp+220h+var_1D0]
0x18005d404  mov     ecx, 1Ah
0x18005d409  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d40f  mov     ebx, eax
0x18005d411  test    eax, eax
0x18005d413  jz      short loc_18005D464
0x18005d415  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d41c  jz      loc_18005D785
0x18005d422  test    eax, eax
0x18005d424  jle     short loc_18005D42E
0x18005d426  movzx   eax, ax
0x18005d429  or      eax, 80070000h
0x18005d42e  lea     rcx, aCreatingAdmini; "Creating Administrator SID failed\n"
0x18005d435  mov     r8d, 0EA0h
0x18005d43b  mov     [rsp+220h+lpName], rcx
0x18005d440  lea     r9, aCreatememoryfi; "CreateMemoryFile"
0x18005d447  mov     rcx, cs:g_pDebug
0x18005d44e  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005d455  mov     [rsp+220h+dwMaximumSizeLow], eax
0x18005d459  call    cs:__imp_PuDbgPrintError
0x18005d45f  jmp     loc_18005D785
0x18005d464  lea     rdx, [rsp+220h+var_1E8]
0x18005d469  mov     ecx, 1Dh
0x18005d46e  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d474  mov     ebx, eax
0x18005d476  test    eax, eax
0x18005d478  jz      short loc_18005D4A2
0x18005d47a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d481  jz      loc_18005D785
0x18005d487  test    eax, eax
0x18005d489  jle     short loc_18005D493
0x18005d48b  movzx   eax, ax
0x18005d48e  or      eax, 80070000h
0x18005d493  lea     rcx, aCreatingPowerU; "Creating Power User SID failed\n"
0x18005d49a  mov     r8d, 0EB0h
0x18005d4a0  jmp     short loc_18005D43B
0x18005d4a2  lea     rdx, [rsp+220h+var_1E0]
0x18005d4a7  mov     ecx, 1Fh
0x18005d4ac  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d4b2  mov     ebx, eax
0x18005d4b4  test    eax, eax
0x18005d4b6  jz      short loc_18005D4E3
0x18005d4b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d4bf  jz      loc_18005D785
0x18005d4c5  test    eax, eax
0x18005d4c7  jle     short loc_18005D4D1
0x18005d4c9  movzx   eax, ax
0x18005d4cc  or      eax, 80070000h
0x18005d4d1  lea     rcx, aCreatingSystem; "Creating System Operators SID failed\n"
0x18005d4d8  mov     r8d, 0EC1h
0x18005d4de  jmp     loc_18005D43B
0x18005d4e3  lea     rdx, [rsp+220h+var_1C8]
0x18005d4e8  mov     ecx, 39h ; '9'
0x18005d4ed  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d4f3  mov     ebx, eax
0x18005d4f5  test    eax, eax
0x18005d4f7  jz      short loc_18005D524
0x18005d4f9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d500  jz      loc_18005D785
0x18005d506  test    eax, eax
0x18005d508  jle     short loc_18005D512
0x18005d50a  movzx   eax, ax
0x18005d50d  or      eax, 80070000h
0x18005d512  lea     rcx, aCreatingPerfMo; "Creating perf mon user SID failed\n"
0x18005d519  mov     r8d, 0ED1h
0x18005d51f  jmp     loc_18005D43B
0x18005d524  lea     rdx, [rsp+220h+var_1C0]
0x18005d529  mov     ecx, 3Ah ; ':'
0x18005d52e  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d534  mov     ebx, eax
0x18005d536  test    eax, eax
0x18005d538  jz      short loc_18005D565
0x18005d53a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d541  jz      loc_18005D785
0x18005d547  test    eax, eax
0x18005d549  jle     short loc_18005D553
0x18005d54b  movzx   eax, ax
0x18005d54e  or      eax, 80070000h
0x18005d553  lea     rcx, aCreatingPerfLo; "Creating perf log user SID failed\n"
0x18005d55a  mov     r8d, 0EE2h
0x18005d560  jmp     loc_18005D43B
0x18005d565  lea     rdx, [rsp+220h+var_1D8]
0x18005d56a  mov     ecx, 16h
0x18005d56f  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18005d575  mov     ebx, eax
0x18005d577  test    eax, eax
0x18005d579  jz      short loc_18005D5A6
0x18005d57b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d582  jz      loc_18005D785
0x18005d588  test    eax, eax
0x18005d58a  jle     short loc_18005D594
0x18005d58c  movzx   eax, ax
0x18005d58f  or      eax, 80070000h
0x18005d594  lea     rcx, aCreatingLocalS; "Creating Local System SID failed\n"
0x18005d59b  mov     r8d, 0EF3h
0x18005d5a1  jmp     loc_18005D43B
0x18005d5a6  xor     edx, edx; Val
0x18005d5a8  lea     rcx, [rbp+120h+pListOfExplicitEntries]; void *
0x18005d5ac  mov     r8d, 120h; Size
0x18005d5b2  call    memset_0
0x18005d5b7  mov     r9, [rsp+220h+var_1E8]
0x18005d5bc  lea     rcx, [rbp+120h+pListOfExplicitEntries]
0x18005d5c0  mov     ebx, 2
0x18005d5c5  mov     r8d, ebx
0x18005d5c8  lea     edx, [rbx+2]
0x18005d5cb  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d5d1  mov     r9, [rsp+220h+var_1D0]
0x18005d5d6  lea     edx, [rbx+2]
0x18005d5d9  mov     r8d, ebx
0x18005d5dc  lea     rcx, [rbp+120h+var_140]
0x18005d5e0  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d5e6  mov     r9, [rsp+220h+var_1E0]
0x18005d5eb  lea     edx, [rbx+2]
0x18005d5ee  mov     r8d, ebx
0x18005d5f1  lea     rcx, [rbp+120h+var_110]
0x18005d5f5  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d5fb  mov     r9, [rsp+220h+var_1D8]
0x18005d600  lea     rcx, [rbp+120h+var_E0]
0x18005d604  mov     r8d, ebx
0x18005d607  mov     edx, 0F001Fh
0x18005d60c  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d612  mov     r9, [rsp+220h+var_1C8]
0x18005d617  lea     edx, [rbx+2]
0x18005d61a  mov     r8d, ebx
0x18005d61d  lea     rcx, [rbp+120h+var_B0]
0x18005d621  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d627  mov     r9, [rsp+220h+var_1C0]
0x18005d62c  lea     edx, [rbx+2]
0x18005d62f  mov     r8d, ebx
0x18005d632  lea     rcx, [rbp+120h+var_80]
0x18005d639  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18005d63f  lea     r9, [rsp+220h+NewAcl]; NewAcl
0x18005d644  xor     r8d, r8d; OldAcl
0x18005d647  lea     rdx, [rbp+120h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18005d64b  lea     ecx, [rbx+4]; cCountOfExplicitEntries
0x18005d64e  call    cs:__imp_SetEntriesInAclW
0x18005d654  mov     ebx, eax
0x18005d656  test    eax, eax
0x18005d658  jz      short loc_18005D685
0x18005d65a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d661  jz      loc_18005D785
0x18005d667  test    eax, eax
0x18005d669  jle     short loc_18005D673
0x18005d66b  movzx   eax, ax
0x18005d66e  or      eax, 80070000h
0x18005d673  lea     rcx, aSettingAceSInt; "Setting ACE's into ACL failed.\n"
0x18005d67a  mov     r8d, 0F3Ch
0x18005d680  jmp     loc_18005D43B
0x18005d685  mov     ebx, 1
0x18005d68a  lea     rcx, [rbp+120h+pSecurityDescriptor]; pSecurityDescriptor
0x18005d68e  mov     edx, ebx; dwRevision
0x18005d690  call    cs:__imp_InitializeSecurityDescriptor
0x18005d696  test    eax, eax
0x18005d698  jnz     short loc_18005D6CD
0x18005d69a  call    cs:__imp_GetLastError
0x18005d6a0  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d6a7  mov     ebx, eax
0x18005d6a9  jz      loc_18005D785
0x18005d6af  test    eax, eax
0x18005d6b1  jle     short loc_18005D6BB
0x18005d6b3  movzx   eax, ax
0x18005d6b6  or      eax, 80070000h
0x18005d6bb  lea     rcx, aInitializingTh_0; "Initializing the security descriptor fa"...
0x18005d6c2  mov     r8d, 0F48h
0x18005d6c8  jmp     loc_18005D43B
0x18005d6cd  mov     r8, [rsp+220h+NewAcl]; pDacl
0x18005d6d2  lea     rcx, [rbp+120h+pSecurityDescriptor]; pSecurityDescriptor
0x18005d6d6  xor     r9d, r9d; bDaclDefaulted
0x18005d6d9  mov     edx, ebx; bDaclPresent
0x18005d6db  call    cs:__imp_SetSecurityDescriptorDacl
0x18005d6e1  test    eax, eax
0x18005d6e3  jnz     short loc_18005D718
0x18005d6e5  call    cs:__imp_GetLastError
0x18005d6eb  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005d6f2  mov     ebx, eax
0x18005d6f4  jz      loc_18005D785
0x18005d6fa  test    eax, eax
0x18005d6fc  jle     short loc_18005D706
0x18005d6fe  movzx   eax, ax
0x18005d701  or      eax, 80070000h
0x18005d706  lea     rcx, aSettingTheDacl; "Setting the DACL on the security descri"...
0x18005d70d  mov     r8d, 0F57h
0x18005d713  jmp     loc_18005D43B
0x18005d718  xor     r9d, r9d; dwMaximumSizeHigh
0x18005d71b  mov     [rsp+220h+lpName], r12; lpName
0x18005d720  lea     rax, [rbp+120h+pSecurityDescriptor]
0x18005d724  mov     [rsp+220h+FileMappingAttributes.nLength], 18h
0x18005d72c  lea     rdx, [rsp+220h+FileMappingAttributes]; lpFileMappingAttributes
0x18005d731  mov     [rsp+220h+FileMappingAttributes.lpSecurityDescriptor], rax
0x18005d736  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18005d73a  mov     [rsp+220h+FileMappingAttributes.bInheritHandle], esi
0x18005d73e  lea     r8d, [r9+4]; flProtect
0x18005d742  mov     [rsp+220h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x18005d747  call    cs:__imp_CreateFileMappingW
0x18005d74d  mov     rsi, rax
0x18005d750  call    cs:__imp_GetLastError
0x18005d756  mov     ebx, eax
0x18005d758  test    eax, eax
0x18005d75a  jnz     short loc_18005D785
0x18005d75c  xor     r9d, r9d; dwFileOffsetLow
0x18005d75f  mov     qword ptr [rsp+220h+dwMaximumSizeLow], rdi; dwNumberOfBytesToMap
0x18005d764  xor     r8d, r8d; dwFileOffsetHigh
0x18005d767  mov     edx, 0F001Fh; dwDesiredAccess
0x18005d76c  mov     rcx, rsi; hFileMappingObject
0x18005d76f  call    cs:__imp_MapViewOfFile
0x18005d775  mov     rdi, rax
0x18005d778  test    rax, rax
0x18005d77b  jnz     short loc_18005D785
0x18005d77d  call    cs:__imp_GetLastError
0x18005d783  mov     ebx, eax
0x18005d785  lea     rcx, [rsp+220h+var_1E8]
0x18005d78a  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d790  lea     rcx, [rsp+220h+var_1E0]
0x18005d795  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d79b  lea     rcx, [rsp+220h+var_1D8]
0x18005d7a0  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d7a6  lea     rcx, [rsp+220h+var_1D0]
0x18005d7ab  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d7b1  lea     rcx, [rsp+220h+var_1C8]
0x18005d7b6  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d7bc  lea     rcx, [rsp+220h+var_1C0]
0x18005d7c1  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18005d7c7  mov     rcx, [rsp+220h+NewAcl]; hMem
0x18005d7cc  test    rcx, rcx
0x18005d7cf  jz      short loc_18005D7E0
0x18005d7d1  call    cs:__imp_LocalFree
0x18005d7d7  mov     [rsp+220h+NewAcl], 0
0x18005d7e0  test    ebx, ebx
0x18005d7e2  jz      short loc_18005D802
0x18005d7e4  test    rdi, rdi
0x18005d7e7  jz      short loc_18005D7F2
0x18005d7e9  mov     rcx, rdi; lpBaseAddress
0x18005d7ec  call    cs:__imp_UnmapViewOfFile
0x18005d7f2  test    rsi, rsi
0x18005d7f5  jz      short loc_18005D808
0x18005d7f7  mov     rcx, rsi; hObject
0x18005d7fa  call    cs:__imp_CloseHandle
0x18005d800  jmp     short loc_18005D808
0x18005d802  mov     [r15], rdi
0x18005d805  mov     [r14], rsi
0x18005d808  mov     eax, ebx
0x18005d80a  mov     rcx, [rbp+120h+var_50]
0x18005d811  xor     rcx, rsp; StackCookie
0x18005d814  call    __security_check_cookie
0x18005d819  add     rsp, 1E8h
0x18005d820  pop     r15
0x18005d822  pop     r14
0x18005d824  pop     r13
0x18005d826  pop     r12
0x18005d828  pop     rdi
0x18005d829  pop     rsi
0x18005d82a  pop     rbx
0x18005d82b  pop     rbp
0x18005d82c  retn
```
