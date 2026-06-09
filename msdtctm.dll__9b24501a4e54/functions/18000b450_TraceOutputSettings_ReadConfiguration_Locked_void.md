# TraceOutputSettings::ReadConfiguration_Locked(void)

- ea: `0x18000b450`
- end: `0x18000bb09`
- name: `?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ`
- size: `1721`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd3c`

## callees

- `0x1800063b0`
- `0x18000b450`
- `0x180016f3c`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b74e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b74e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b72d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b72d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b526`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000b526`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b6a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b858`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b935`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b6a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b858`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b935`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ba05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b49f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b660`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b49f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b660`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000baaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b5f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000baaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b704`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b704`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b73a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b73a`

## string_xrefs

- `0x18000b4a5`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x18000b693`: `TraceFilePath`
- `0x18000b4d5`: `Unable to read level for source %S`
- `0x18000b556`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b59b`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b61b`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b768`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b80d`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b897`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b8e6`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b967`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b9b6`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000ba37`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000ba86`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000bacd`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x18000b609`: `Unable to open sources key`
- `0x18000b77a`: `Using new trace file path: %s`
- `0x18000b7d2`: `Ignoring empty-string trace directory`
- `0x18000b7ad`: `Unable to duplicate trace path`
- `0x18000b7f7`: `Unable to read trace path`
- `0x18000b8d4`: `Unable to read memory buffer size`
- `0x18000b9a4`: `Unable to read debug out enabled`
- `0x18000ba74`: `Unable to read Including Image Name in Trace File Name`
- `0x18000babb`: `Unable to open output key`

## pseudocode

```c
void TraceOutputSettings::ReadConfiguration_Locked(void)
{
  LSTATUS v0; // eax
  __int64 v1; // rbx
  __int64 v2; // rdi
  const CHAR *v3; // rdx
  LSTATUS v4; // ecx
  bool v5; // zf
  int v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  LSTATUS v13; // eax
  DWORD v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  __int64 v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _WORD v24[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Sources", 0, 0x101u, &hKey);
  if ( v0 )
  {
    if ( TraceOutputSettings::fInitialized )
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        288,
        L"TraceOutputSettings::ReadConfiguration_Locked",
        v0,
        L"Unable to open sources key");
  }
  else
  {
    v1 = 0;
    v2 = 0;
    do
    {
      v3 = *(const CHAR **)((char *)&TraceSources + v2 + 8);
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v4 = RegQueryValueExA(hKey, v3, 0, &Type, Data, &cbData);
      if ( !v4 && Type == 4 && cbData == 4 )
      {
        v5 = !TraceOutputSettings::fInitialized;
        v6 = *(_DWORD *)Data;
        *(_DWORD *)((char *)&TraceSources + v2 + 16) = *(_DWORD *)Data;
        if ( !v5 )
        {
          LODWORD(v18) = v6;
          TraceStringInline(
            2,
            3,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            267,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            0,
            L"Now tracing %S at level %d",
            *(struct TraceSourceEntry near **)((char *)&TraceSources + v2 + 8),
            v18);
        }
      }
      else if ( TraceOutputSettings::fInitialized )
      {
        TraceStringInline(
          2,
          1,
          L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
          277,
          L"TraceOutputSettings::ReadConfiguration_Locked",
          v4,
          L"Unable to read level for source %S",
          *(struct TraceSourceEntry near **)((char *)&TraceSources + v2 + 8));
      }
      ++v1;
      v2 += 24;
    }
    while ( v1 != 22 );
    RegCloseKey(hKey);
  }
  phkResult = 0;
  v7 = RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Output", 0, 0x101u, &phkResult);
  if ( !v7 )
  {
    Type = 0;
    *(_DWORD *)Data = 522;
    cbData = 0;
    v8 = RegQueryValueExW(phkResult, L"TraceFilePath", 0, &cbData, (LPBYTE)v24, (LPDWORD)Data);
    if ( v8 || cbData != 1 )
    {
      if ( TraceOutputSettings::fInitialized )
        TraceStringInline(
          2,
          1,
          L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
          370,
          L"TraceOutputSettings::ReadConfiguration_Locked",
          v8,
          L"Unable to read trace path");
      goto LABEL_32;
    }
    v24[260] = 0;
    v9 = -1;
    do
      ++v9;
    while ( v24[v9] );
    v10 = v9 + 1;
    if ( v9 + 1 > 1 )
    {
      if ( v24[v10 - 1] != 92 )
        goto LABEL_23;
      if ( v9 > 1 )
      {
        v10 = v9;
LABEL_23:
        v11 = (unsigned __int16 *)LocalAlloc(0, 2 * v10);
        v12 = v11;
        if ( v11 )
        {
          StringCchCopyW(v11, v10, v24);
          EnterCriticalSection(&stru_1801535A8);
          LocalFree(TraceOutputSettings::TraceFilePath);
          TraceOutputSettings::TraceFilePath = v12;
          LeaveCriticalSection(&stru_1801535A8);
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              343,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Using new trace file path: %s",
              TraceOutputSettings::TraceFilePath);
        }
        else if ( TraceOutputSettings::fInitialized )
        {
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            352,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            -2147024882,
            L"Unable to duplicate trace path");
        }
LABEL_32:
        *(_DWORD *)Data = 4;
        v13 = RegQueryValueExW(phkResult, L"MemoryBufferSize", 0, &cbData, (LPBYTE)&Type, (LPDWORD)Data);
        if ( !v13 && cbData == 4 && *(_DWORD *)Data == 4 )
        {
          v14 = Type;
          if ( Type > 0xFFFFFFF )
          {
            v14 = 0xFFFFFFF;
            Type = 0xFFFFFFF;
          }
          TraceOutputSettings::MemoryBufferSize = v14;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v17) = v14;
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              399,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Memory buffer size is now %d",
              v17);
          }
        }
        else if ( TraceOutputSettings::fInitialized )
        {
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            408,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            v13,
            L"Unable to read memory buffer size");
        }
        *(_DWORD *)Data = 4;
        v15 = RegQueryValueExW(phkResult, L"DebugOutEnabled", 0, &cbData, (LPBYTE)&Type, (LPDWORD)Data);
        if ( !v15 && cbData == 4 && *(_DWORD *)Data == 4 )
        {
          TraceOutputSettings::DebugOutEnabled = Type != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v17) = Type;
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              430,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Debug out enabled is now %d",
              v17);
          }
        }
        else if ( TraceOutputSettings::fInitialized )
        {
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            439,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            v15,
            L"Unable to read debug out enabled");
        }
        *(_DWORD *)Data = 4;
        v16 = RegQueryValueExW(phkResult, L"ImageNameInTraceFileNameEnabled", 0, &cbData, (LPBYTE)&Type, (LPDWORD)Data);
        if ( !v16 && cbData == 4 && *(_DWORD *)Data == 4 )
        {
          TraceOutputSettings::ImageNameInTraceFileNameEnabled = Type != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v17) = Type;
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              461,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Including Image Name in Trace File Name is now %d",
              v17);
          }
        }
        else if ( TraceOutputSettings::fInitialized )
        {
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            470,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            v16,
            L"Unable to read Including Image Name in Trace File Name");
        }
        RegCloseKey(phkResult);
        return;
      }
    }
    if ( TraceOutputSettings::fInitialized )
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        362,
        L"TraceOutputSettings::ReadConfiguration_Locked",
        -2147024809,
        L"Ignoring empty-string trace directory");
    goto LABEL_32;
  }
  if ( TraceOutputSettings::fInitialized )
    TraceStringInline(
      2,
      1,
      L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      480,
      L"TraceOutputSettings::ReadConfiguration_Locked",
      v7,
      L"Unable to open output key");
}

```

## disassembly

```asm
0x18000b450  push    rbp
0x18000b452  push    rbx
0x18000b453  push    rsi
0x18000b454  push    rdi
0x18000b455  push    r15
0x18000b457  lea     rbp, [rsp-190h]
0x18000b45f  sub     rsp, 290h
0x18000b466  mov     rax, cs:__security_cookie
0x18000b46d  xor     rax, rsp
0x18000b470  mov     [rbp+1B0h+var_30], rax
0x18000b477  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x18000b47e  lea     rax, [rsp+2B0h+hKey]
0x18000b483  xor     esi, esi
0x18000b485  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000b48a  mov     r9d, 101h; samDesired
0x18000b490  mov     [rsp+2B0h+hKey], rsi
0x18000b495  xor     r8d, r8d; ulOptions
0x18000b498  lea     rdx, aSources; "Sources"
0x18000b49f  call    cs:__imp_RegOpenKeyExW
0x18000b4a5  lea     r15, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x18000b4ac  test    eax, eax
0x18000b4ae  jnz     loc_18000B600
0x18000b4b4  mov     [rsp+2B0h+arg_0], r12
0x18000b4bc  mov     ebx, esi
0x18000b4be  mov     [rsp+2B0h+arg_8], r13
0x18000b4c6  lea     r12, aNowTracingSAtL; "Now tracing %S at level %d"
0x18000b4cd  mov     [rsp+2B0h+arg_10], r14
0x18000b4d5  lea     r13, aUnableToReadLe; "Unable to read level for source %S"
0x18000b4dc  lea     r14, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x18000b4e3  mov     edi, esi
0x18000b4e5  nop     word ptr [rax+rax+00000000h]
0x18000b4f0  mov     rdx, [rdi+r14+8]; lpValueName
0x18000b4f5  lea     rax, [rsp+2B0h+cbData]
0x18000b4fa  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000b4ff  lea     r9, [rsp+2B0h+Type]; lpType
0x18000b504  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000b509  xor     r8d, r8d; lpReserved
0x18000b50c  lea     rax, [rsp+2B0h+Data]
0x18000b511  mov     [rsp+2B0h+Type], esi
0x18000b515  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000b51a  mov     dword ptr [rsp+2B0h+Data], esi
0x18000b51e  mov     [rsp+2B0h+cbData], 4
0x18000b526  call    cs:__imp_RegQueryValueExA
0x18000b52c  mov     ecx, eax
0x18000b52e  test    eax, eax
0x18000b530  jnz     short loc_18000B58D
0x18000b532  cmp     [rsp+2B0h+Type], 4
0x18000b537  jnz     short loc_18000B58D
0x18000b539  cmp     [rsp+2B0h+cbData], 4
0x18000b53e  jnz     short loc_18000B58D
0x18000b540  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b547  mov     eax, dword ptr [rsp+2B0h+Data]
0x18000b54b  mov     [rdi+r14+10h], eax
0x18000b550  jz      short loc_18000B5CA
0x18000b552  mov     [rsp+2B0h+var_270], eax
0x18000b556  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b55d  mov     rax, [rdi+r14+8]
0x18000b562  mov     r9d, 10Bh
0x18000b568  mov     [rsp+2B0h+var_278], rax
0x18000b56d  mov     edx, 3
0x18000b572  mov     [rsp+2B0h+var_280], r12
0x18000b577  mov     ecx, 2
0x18000b57c  mov     [rsp+2B0h+lpcbData], rsi
0x18000b581  mov     [rsp+2B0h+phkResult], r15
0x18000b586  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b58b  jmp     short loc_18000B5CA
0x18000b58d  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b594  jz      short loc_18000B5CA
0x18000b596  mov     rax, [rdi+r14+8]
0x18000b59b  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b5a2  mov     [rsp+2B0h+var_278], rax
0x18000b5a7  mov     r9d, 115h
0x18000b5ad  mov     [rsp+2B0h+var_280], r13
0x18000b5b2  mov     edx, 1
0x18000b5b7  mov     dword ptr [rsp+2B0h+lpcbData], ecx
0x18000b5bb  mov     ecx, 2
0x18000b5c0  mov     [rsp+2B0h+phkResult], r15
0x18000b5c5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b5ca  inc     rbx
0x18000b5cd  add     rdi, 18h
0x18000b5d1  cmp     rbx, 16h
0x18000b5d5  jnz     loc_18000B4F0
0x18000b5db  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000b5e0  mov     r14, [rsp+2B0h+arg_10]
0x18000b5e8  mov     r13, [rsp+2B0h+arg_8]
0x18000b5f0  mov     r12, [rsp+2B0h+arg_0]
0x18000b5f8  call    cs:__imp_RegCloseKey
0x18000b5fe  jmp     short loc_18000B63A
0x18000b600  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b607  jz      short loc_18000B63A
0x18000b609  lea     rcx, aUnableToOpenSo; "Unable to open sources key"
0x18000b610  mov     r9d, 120h
0x18000b616  mov     [rsp+2B0h+var_280], rcx
0x18000b61b  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b622  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18000b626  mov     ecx, 2
0x18000b62b  mov     edx, 1
0x18000b630  mov     [rsp+2B0h+phkResult], r15
0x18000b635  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b63a  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x18000b641  lea     rax, [rsp+2B0h+var_250]
0x18000b646  mov     r9d, 101h; samDesired
0x18000b64c  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000b651  xor     r8d, r8d; ulOptions
0x18000b654  mov     [rsp+2B0h+var_250], rsi
0x18000b659  lea     rdx, aOutput; "Output"
0x18000b660  call    cs:__imp_RegOpenKeyExW
0x18000b666  test    eax, eax
0x18000b668  jnz     loc_18000BAB2
0x18000b66e  mov     rcx, [rsp+2B0h+var_250]; hKey
0x18000b673  lea     rax, [rsp+2B0h+Data]
0x18000b678  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000b67d  lea     r9, [rsp+2B0h+cbData]; lpType
0x18000b682  lea     rax, [rsp+2B0h+var_240]
0x18000b687  mov     [rsp+2B0h+Type], esi
0x18000b68b  xor     r8d, r8d; lpReserved
0x18000b68e  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000b693  lea     rdx, aTracefilepath; "TraceFilePath"
0x18000b69a  mov     dword ptr [rsp+2B0h+Data], 20Ah
0x18000b6a2  mov     [rsp+2B0h+cbData], esi
0x18000b6a6  call    cs:__imp_RegQueryValueExW
0x18000b6ac  test    eax, eax
0x18000b6ae  jnz     loc_18000B7EE
0x18000b6b4  cmp     [rsp+2B0h+cbData], 1
0x18000b6b9  jnz     loc_18000B7EE
0x18000b6bf  mov     [rbp+1B0h+var_38], si
0x18000b6c6  lea     rcx, [rsp+2B0h+var_240]
0x18000b6cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b6d2  inc     rax
0x18000b6d5  cmp     [rcx+rax*2], si
0x18000b6d9  jnz     short loc_18000B6D2
0x18000b6db  lea     rbx, [rax+1]
0x18000b6df  cmp     rbx, 1
0x18000b6e3  jbe     loc_18000B7C9
0x18000b6e9  cmp     word ptr [rsp+rbx*2+2B0h+hKey+6], 5Ch ; '\'
0x18000b6ef  jnz     short loc_18000B6FE
0x18000b6f1  cmp     rax, 1
0x18000b6f5  jbe     loc_18000B7C9
0x18000b6fb  mov     rbx, rax
0x18000b6fe  lea     rdx, [rbx+rbx]; uBytes
0x18000b702  xor     ecx, ecx; uFlags
0x18000b704  call    cs:__imp_LocalAlloc
0x18000b70a  mov     rdi, rax
0x18000b70d  test    rax, rax
0x18000b710  jz      loc_18000B7A4
0x18000b716  lea     r8, [rsp+2B0h+var_240]; unsigned __int16 *
0x18000b71b  mov     rdx, rbx; unsigned __int64
0x18000b71e  mov     rcx, rax; unsigned __int16 *
0x18000b721  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b726  lea     rcx, stru_1801535A8; lpCriticalSection
0x18000b72d  call    cs:__imp_EnterCriticalSection
0x18000b733  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x18000b73a  call    cs:__imp_LocalFree
0x18000b740  lea     rcx, stru_1801535A8; lpCriticalSection
0x18000b747  mov     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rdi; ushort * TraceOutputSettings::TraceFilePath
0x18000b74e  call    cs:__imp_LeaveCriticalSection
0x18000b754  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b75b  jz      loc_18000B828
0x18000b761  mov     rax, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x18000b768  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b76f  mov     [rsp+2B0h+var_278], rax
0x18000b774  mov     r9d, 157h
0x18000b77a  lea     rax, aUsingNewTraceF; "Using new trace file path: %s"
0x18000b781  mov     edx, 3
0x18000b786  mov     [rsp+2B0h+var_280], rax
0x18000b78b  mov     ecx, 2
0x18000b790  mov     [rsp+2B0h+lpcbData], rsi
0x18000b795  mov     [rsp+2B0h+phkResult], r15
0x18000b79a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b79f  jmp     loc_18000B828
0x18000b7a4  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b7ab  jz      short loc_18000B828
0x18000b7ad  lea     rax, aUnableToDuplic; "Unable to duplicate trace path"
0x18000b7b4  mov     r9d, 160h
0x18000b7ba  mov     [rsp+2B0h+var_280], rax
0x18000b7bf  mov     dword ptr [rsp+2B0h+lpcbData], 8007000Eh
0x18000b7c7  jmp     short loc_18000B80D
0x18000b7c9  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b7d0  jz      short loc_18000B828
0x18000b7d2  lea     rax, aIgnoringEmptyS; "Ignoring empty-string trace directory"
0x18000b7d9  mov     r9d, 16Ah
0x18000b7df  mov     [rsp+2B0h+var_280], rax
0x18000b7e4  mov     dword ptr [rsp+2B0h+lpcbData], 80070057h
0x18000b7ec  jmp     short loc_18000B80D
0x18000b7ee  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b7f5  jz      short loc_18000B828
0x18000b7f7  lea     rcx, aUnableToReadTr; "Unable to read trace path"
0x18000b7fe  mov     r9d, 172h
0x18000b804  mov     [rsp+2B0h+var_280], rcx
0x18000b809  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18000b80d  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b814  mov     [rsp+2B0h+phkResult], r15
0x18000b819  mov     edx, 1
0x18000b81e  mov     ecx, 2
0x18000b823  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b828  mov     rcx, [rsp+2B0h+var_250]; hKey
0x18000b82d  lea     rax, [rsp+2B0h+Data]
0x18000b832  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000b837  lea     r9, [rsp+2B0h+cbData]; lpType
0x18000b83c  lea     rax, [rsp+2B0h+Type]
0x18000b841  mov     dword ptr [rsp+2B0h+Data], 4
0x18000b849  xor     r8d, r8d; lpReserved
0x18000b84c  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000b851  lea     rdx, aMemorybuffersi; "MemoryBufferSize"
0x18000b858  call    cs:__imp_RegQueryValueExW
0x18000b85e  test    eax, eax
0x18000b860  jnz     short loc_18000B8CB
0x18000b862  cmp     [rsp+2B0h+cbData], 4
0x18000b867  jnz     short loc_18000B8CB
0x18000b869  cmp     dword ptr [rsp+2B0h+Data], 4
0x18000b86e  jnz     short loc_18000B8CB
0x18000b870  mov     eax, [rsp+2B0h+Type]
0x18000b874  cmp     eax, 0FFFFFFFh
0x18000b879  jbe     short loc_18000B884
0x18000b87b  mov     eax, 0FFFFFFFh
0x18000b880  mov     [rsp+2B0h+Type], eax
0x18000b884  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b88b  mov     cs:?MemoryBufferSize@TraceOutputSettings@@2KA, eax; ulong TraceOutputSettings::MemoryBufferSize
0x18000b891  jz      short loc_18000B905
0x18000b893  mov     dword ptr [rsp+2B0h+var_278], eax
0x18000b897  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b89e  lea     rax, aMemoryBufferSi; "Memory buffer size is now %d"
0x18000b8a5  mov     r9d, 18Fh
0x18000b8ab  mov     [rsp+2B0h+var_280], rax
0x18000b8b0  mov     edx, 3
0x18000b8b5  mov     [rsp+2B0h+lpcbData], rsi
0x18000b8ba  mov     ecx, 2
0x18000b8bf  mov     [rsp+2B0h+phkResult], r15
0x18000b8c4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b8c9  jmp     short loc_18000B905
0x18000b8cb  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b8d2  jz      short loc_18000B905
0x18000b8d4  lea     rcx, aUnableToReadMe; "Unable to read memory buffer size"
0x18000b8db  mov     r9d, 198h
0x18000b8e1  mov     [rsp+2B0h+var_280], rcx
0x18000b8e6  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b8ed  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18000b8f1  mov     ecx, 2
0x18000b8f6  mov     edx, 1
0x18000b8fb  mov     [rsp+2B0h+phkResult], r15
0x18000b900  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b905  mov     rcx, [rsp+2B0h+var_250]; hKey
0x18000b90a  lea     rax, [rsp+2B0h+Data]
0x18000b90f  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000b914  lea     r9, [rsp+2B0h+cbData]; lpType
0x18000b919  lea     rax, [rsp+2B0h+Type]
0x18000b91e  mov     dword ptr [rsp+2B0h+Data], 4
0x18000b926  xor     r8d, r8d; lpReserved
0x18000b929  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000b92e  lea     rdx, aDebugoutenable; "DebugOutEnabled"
0x18000b935  call    cs:__imp_RegQueryValueExW
0x18000b93b  test    eax, eax
0x18000b93d  jnz     short loc_18000B99B
0x18000b93f  cmp     [rsp+2B0h+cbData], 4
0x18000b944  jnz     short loc_18000B99B
0x18000b946  cmp     dword ptr [rsp+2B0h+Data], 4
0x18000b94b  jnz     short loc_18000B99B
0x18000b94d  mov     eax, [rsp+2B0h+Type]
0x18000b951  test    eax, eax
0x18000b953  setnz   cs:?DebugOutEnabled@TraceOutputSettings@@2_NA; bool TraceOutputSettings::DebugOutEnabled
0x18000b95a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b961  jz      short loc_18000B9D5
0x18000b963  mov     dword ptr [rsp+2B0h+var_278], eax
0x18000b967  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b96e  lea     rax, aDebugOutEnable; "Debug out enabled is now %d"
0x18000b975  mov     r9d, 1AEh
0x18000b97b  mov     [rsp+2B0h+var_280], rax
0x18000b980  mov     edx, 3
0x18000b985  mov     [rsp+2B0h+lpcbData], rsi
0x18000b98a  mov     ecx, 2
0x18000b98f  mov     [rsp+2B0h+phkResult], r15
0x18000b994  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b999  jmp     short loc_18000B9D5
0x18000b99b  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000b9a2  jz      short loc_18000B9D5
0x18000b9a4  lea     rcx, aUnableToReadDe; "Unable to read debug out enabled"
0x18000b9ab  mov     r9d, 1B7h
0x18000b9b1  mov     [rsp+2B0h+var_280], rcx
0x18000b9b6  lea     r8, aComComplusDtcS_5; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x18000b9bd  mov     dword ptr [rsp+2B0h+lpcbData], eax
0x18000b9c1  mov     ecx, 2
0x18000b9c6  mov     edx, 1
0x18000b9cb  mov     [rsp+2B0h+phkResult], r15
0x18000b9d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000b9d5  mov     rcx, [rsp+2B0h+var_250]; hKey
0x18000b9da  lea     rax, [rsp+2B0h+Data]
0x18000b9df  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000b9e4  lea     r9, [rsp+2B0h+cbData]; lpType
0x18000b9e9  lea     rax, [rsp+2B0h+Type]
0x18000b9ee  mov     dword ptr [rsp+2B0h+Data], 4
0x18000b9f6  xor     r8d, r8d; lpReserved
0x18000b9f9  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000b9fe  lea     rdx, aImagenameintra; "ImageNameInTraceFileNameEnabled"
0x18000ba05  call    cs:__imp_RegQueryValueExW
0x18000ba0b  test    eax, eax
0x18000ba0d  jnz     short loc_18000BA6B
0x18000ba0f  cmp     [rsp+2B0h+cbData], 4
0x18000ba14  jnz     short loc_18000BA6B
0x18000ba16  cmp     dword ptr [rsp+2B0h+Data], 4
0x18000ba1b  jnz     short loc_18000BA6B
  ... truncated ...
```
