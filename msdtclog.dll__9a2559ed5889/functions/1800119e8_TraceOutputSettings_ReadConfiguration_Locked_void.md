# TraceOutputSettings::ReadConfiguration_Locked(void)

- ea: `0x1800119e8`
- end: `0x18001207d`
- name: `?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ`
- size: `1685`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011920`

## callees

- `0x18000ad1c`
- `0x18000ad90`
- `0x1800119e8`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011cd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011cd3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011cb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011cb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011aa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011aa3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011bea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011b83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012020`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011c30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011dff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011eca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011c30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011dff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011eca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011f89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011cbf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011c89`

## string_xrefs

- `0x180011a4e`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x180011a47`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011b04`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011b4e`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011b89`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011ce0`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011d31`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011d61`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011dcb`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180011b42`: `Unable to read level for source %S`
- `0x180011b9b`: `Unable to open sources key`
- `0x180011c1d`: `TraceFilePath`
- `0x180011d02`: `Using new trace file path: %s`
- `0x180011d3e`: `Unable to duplicate trace path`
- `0x180011d6a`: `Ignoring empty-string trace directory`
- `0x180011da2`: `Unable to read trace path`
- `0x180011e74`: `Unable to read memory buffer size`
- `0x180011f33`: `Unable to read debug out enabled`
- `0x180011ff2`: `Unable to read Including Image Name in Trace File Name`
- `0x180012031`: `Unable to open output key`

## pseudocode

```c
void TraceOutputSettings::ReadConfiguration_Locked(void)
{
  LSTATUS v0; // eax
  __int64 v1; // rdi
  __int64 v2; // rbx
  const CHAR *v3; // rdx
  LSTATUS Value; // ecx
  bool v5; // zf
  DWORD v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  LSTATUS v13; // eax
  unsigned int v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  __int64 v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+40h] [rbp-C0h]
  DWORD Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _WORD v22[264]; // [rsp+70h] [rbp-90h] BYREF

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
      Data[2] = 0;
      *(_QWORD *)Data = 0x400000000LL;
      Value = RegQueryValueExA(hKey, v3, 0, &Data[2], (LPBYTE)Data, &Data[1]);
      if ( Value || *(_QWORD *)&Data[1] != 0x400000004LL )
      {
        if ( TraceOutputSettings::fInitialized )
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            277,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            Value,
            L"Unable to read level for source %S",
            *(struct TraceSourceEntry near **)((char *)&TraceSources + v2 + 8));
      }
      else
      {
        v5 = !TraceOutputSettings::fInitialized;
        v6 = Data[0];
        *(_DWORD *)((char *)&TraceSources + v2 + 16) = Data[0];
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
    Data[2] = 0;
    *(_QWORD *)Data = 522;
    v8 = RegQueryValueExW(phkResult, L"TraceFilePath", 0, &Data[1], (LPBYTE)v22, Data);
    if ( v8 || Data[1] != 1 )
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
      goto LABEL_31;
    }
    v22[260] = 0;
    v9 = -1;
    do
      ++v9;
    while ( v22[v9] );
    v10 = v9 + 1;
    if ( v9 + 1 > 1 )
    {
      if ( v22[v10 - 1] != 92 )
        goto LABEL_22;
      if ( v9 > 1 )
      {
        v10 = v9;
LABEL_22:
        v11 = (unsigned __int16 *)LocalAlloc(0, 2 * v10);
        v12 = v11;
        if ( v11 )
        {
          StringCchCopyW(v11, v10, v22);
          EnterCriticalSection(&stru_18001F9D8);
          LocalFree(TraceOutputSettings::TraceFilePath);
          TraceOutputSettings::TraceFilePath = v12;
          LeaveCriticalSection(&stru_18001F9D8);
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
LABEL_31:
        Data[0] = 4;
        v13 = RegQueryValueExW(phkResult, L"MemoryBufferSize", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v13 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              408,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              v13,
              L"Unable to read memory buffer size");
        }
        else
        {
          v14 = Data[2];
          if ( Data[2] > 0xFFFFFFF )
          {
            v14 = 0xFFFFFFF;
            Data[2] = 0xFFFFFFF;
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
        Data[0] = 4;
        v15 = RegQueryValueExW(phkResult, L"DebugOutEnabled", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v15 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              439,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              v15,
              L"Unable to read debug out enabled");
        }
        else
        {
          TraceOutputSettings::DebugOutEnabled = Data[2] != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v17) = Data[2];
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
        Data[0] = 4;
        v16 = RegQueryValueExW(phkResult, L"ImageNameInTraceFileNameEnabled", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v16 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              470,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              v16,
              L"Unable to read Including Image Name in Trace File Name");
        }
        else
        {
          TraceOutputSettings::ImageNameInTraceFileNameEnabled = Data[2] != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v17) = Data[2];
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
    goto LABEL_31;
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
0x1800119e8  push    rbp
0x1800119ea  push    rbx
0x1800119eb  push    rsi
0x1800119ec  push    rdi
0x1800119ed  push    r12
0x1800119ef  push    r13
0x1800119f1  push    r14
0x1800119f3  push    r15
0x1800119f5  lea     rbp, [rsp-198h]
0x1800119fd  sub     rsp, 298h
0x180011a04  mov     rax, cs:__security_cookie
0x180011a0b  xor     rax, rsp
0x180011a0e  mov     [rbp+1D0h+var_50], rax
0x180011a15  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180011a1c  lea     rax, [rsp+2D0h+hKey]
0x180011a21  xor     esi, esi
0x180011a23  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180011a28  mov     r9d, 101h; samDesired
0x180011a2e  mov     [rsp+2D0h+hKey], rsi
0x180011a33  xor     r8d, r8d; ulOptions
0x180011a36  lea     rdx, aSources; "Sources"
0x180011a3d  call    cs:__imp_RegOpenKeyExW
0x180011a43  lea     r15d, [rsi+4]
0x180011a47  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011a4e  lea     r12, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x180011a55  lea     r13d, [rsi+2]
0x180011a59  lea     r14d, [rsi+1]
0x180011a5d  test    eax, eax
0x180011a5f  jnz     loc_180011B92
0x180011a65  mov     edi, esi
0x180011a67  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180011a6e  mov     ebx, esi
0x180011a70  mov     rdx, [rbx+rcx+8]; lpValueName
0x180011a75  lea     rax, [rsp+2D0h+Data+4]
0x180011a7a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180011a7f  lea     r9, [rsp+2D0h+Data+8]; lpType
0x180011a84  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180011a89  xor     r8d, r8d; lpReserved
0x180011a8c  lea     rax, [rsp+2D0h+Data]
0x180011a91  mov     [rsp+2D0h+Data+8], esi
0x180011a95  mov     [rsp+2D0h+phkResult], rax; lpData
0x180011a9a  mov     [rsp+2D0h+Data], esi
0x180011a9e  mov     [rsp+2D0h+Data+4], r15d
0x180011aa3  call    cs:__imp_RegQueryValueExA
0x180011aa9  mov     ecx, eax
0x180011aab  test    eax, eax
0x180011aad  jnz     short loc_180011B1C
0x180011aaf  cmp     [rsp+2D0h+Data+8], r15d
0x180011ab4  jnz     short loc_180011B1C
0x180011ab6  cmp     [rsp+2D0h+Data+4], r15d
0x180011abb  jnz     short loc_180011B1C
0x180011abd  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011ac4  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180011acb  mov     eax, [rsp+2D0h+Data]
0x180011acf  mov     [rbx+rcx+10h], eax
0x180011ad3  jz      loc_180011B6D
0x180011ad9  mov     [rsp+2D0h+var_290], eax
0x180011add  mov     r9d, 10Bh
0x180011ae3  mov     rax, [rbx+rcx+8]
0x180011ae8  mov     r8, r12
0x180011aeb  mov     [rsp+2D0h+var_298], rax
0x180011af0  mov     edx, 3
0x180011af5  lea     rax, aNowTracingSAtL; "Now tracing %S at level %d"
0x180011afc  mov     ecx, r13d
0x180011aff  mov     [rsp+2D0h+var_2A0], rax
0x180011b04  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011b0b  mov     [rsp+2D0h+lpcbData], rsi
0x180011b10  mov     [rsp+2D0h+phkResult], rax
0x180011b15  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011b1a  jmp     short loc_180011B66
0x180011b1c  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011b23  jz      short loc_180011B66
0x180011b25  lea     rax, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180011b2c  mov     r9d, 115h
0x180011b32  mov     rax, [rbx+rax+8]
0x180011b37  mov     r8, r12
0x180011b3a  mov     [rsp+2D0h+var_298], rax
0x180011b3f  mov     edx, r14d
0x180011b42  lea     rax, aUnableToReadLe; "Unable to read level for source %S"
0x180011b49  mov     [rsp+2D0h+var_2A0], rax
0x180011b4e  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011b55  mov     dword ptr [rsp+2D0h+lpcbData], ecx
0x180011b59  mov     ecx, r13d
0x180011b5c  mov     [rsp+2D0h+phkResult], rax
0x180011b61  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011b66  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180011b6d  add     rdi, r14
0x180011b70  add     rbx, 18h
0x180011b74  cmp     rdi, 16h
0x180011b78  jnz     loc_180011A70
0x180011b7e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180011b83  call    cs:__imp_RegCloseKey
0x180011b89  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011b90  jmp     short loc_180011BC4
0x180011b92  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011b99  jz      short loc_180011BC4
0x180011b9b  lea     rcx, aUnableToOpenSo; "Unable to open sources key"
0x180011ba2  mov     r9d, 120h
0x180011ba8  mov     [rsp+2D0h+var_2A0], rcx
0x180011bad  mov     r8, r12
0x180011bb0  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180011bb4  mov     ecx, r13d
0x180011bb7  mov     edx, r14d
0x180011bba  mov     [rsp+2D0h+phkResult], rbx
0x180011bbf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011bc4  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180011bcb  lea     rax, [rsp+2D0h+var_270]
0x180011bd0  mov     r9d, 101h; samDesired
0x180011bd6  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180011bdb  xor     r8d, r8d; ulOptions
0x180011bde  mov     [rsp+2D0h+var_270], rsi
0x180011be3  lea     rdx, aOutput; "Output"
0x180011bea  call    cs:__imp_RegOpenKeyExW
0x180011bf0  test    eax, eax
0x180011bf2  jnz     loc_180012028
0x180011bf8  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180011bfd  lea     rax, [rsp+2D0h+Data]
0x180011c02  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180011c07  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180011c0c  lea     rax, [rsp+2D0h+var_260]
0x180011c11  mov     [rsp+2D0h+Data+8], esi
0x180011c15  xor     r8d, r8d; lpReserved
0x180011c18  mov     [rsp+2D0h+phkResult], rax; lpData
0x180011c1d  lea     rdx, aTracefilepath; "TraceFilePath"
0x180011c24  mov     [rsp+2D0h+Data], 20Ah
0x180011c2c  mov     [rsp+2D0h+Data+4], esi
0x180011c30  call    cs:__imp_RegQueryValueExW
0x180011c36  test    eax, eax
0x180011c38  jnz     loc_180011D99
0x180011c3e  cmp     [rsp+2D0h+Data+4], r14d
0x180011c43  jnz     loc_180011D99
0x180011c49  mov     [rbp+1D0h+var_58], si
0x180011c50  lea     rcx, [rsp+2D0h+var_260]
0x180011c55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011c59  inc     rax
0x180011c5c  cmp     [rcx+rax*2], si
0x180011c60  jnz     short loc_180011C59
0x180011c62  lea     rbx, [rax+1]
0x180011c66  cmp     rbx, r14
0x180011c69  jbe     loc_180011D5A
0x180011c6f  cmp     word ptr [rsp+rbx*2+2D0h+hKey+6], 5Ch ; '\'
0x180011c75  jnz     short loc_180011C83
0x180011c77  cmp     rax, r14
0x180011c7a  jbe     loc_180011D5A
0x180011c80  mov     rbx, rax
0x180011c83  lea     rdx, [rbx+rbx]; uBytes
0x180011c87  xor     ecx, ecx; uFlags
0x180011c89  call    cs:__imp_LocalAlloc
0x180011c8f  mov     rdi, rax
0x180011c92  test    rax, rax
0x180011c95  jz      loc_180011D2A
0x180011c9b  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x180011ca0  mov     rdx, rbx; unsigned __int64
0x180011ca3  mov     rcx, rax; unsigned __int16 *
0x180011ca6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011cab  lea     rcx, stru_18001F9D8; lpCriticalSection
0x180011cb2  call    cs:__imp_EnterCriticalSection
0x180011cb8  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x180011cbf  call    cs:__imp_LocalFree
0x180011cc5  lea     rcx, stru_18001F9D8; lpCriticalSection
0x180011ccc  mov     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rdi; ushort * TraceOutputSettings::TraceFilePath
0x180011cd3  call    cs:__imp_LeaveCriticalSection
0x180011cd9  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011ce0  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011ce7  jz      loc_180011DD2
0x180011ced  mov     rax, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180011cf4  mov     r9d, 157h
0x180011cfa  mov     [rsp+2D0h+var_298], rax
0x180011cff  mov     r8, r12
0x180011d02  lea     rax, aUsingNewTraceF; "Using new trace file path: %s"
0x180011d09  mov     edx, 3
0x180011d0e  mov     [rsp+2D0h+var_2A0], rax
0x180011d13  mov     ecx, r13d
0x180011d16  mov     [rsp+2D0h+lpcbData], rsi
0x180011d1b  mov     [rsp+2D0h+phkResult], rbx
0x180011d20  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011d25  jmp     loc_180011DD2
0x180011d2a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011d31  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011d38  jz      loc_180011DD2
0x180011d3e  lea     rax, aUnableToDuplic; "Unable to duplicate trace path"
0x180011d45  mov     r9d, 160h
0x180011d4b  mov     [rsp+2D0h+var_2A0], rax
0x180011d50  mov     dword ptr [rsp+2D0h+lpcbData], 8007000Eh
0x180011d58  jmp     short loc_180011D84
0x180011d5a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011d61  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011d68  jz      short loc_180011DD2
0x180011d6a  lea     rax, aIgnoringEmptyS; "Ignoring empty-string trace directory"
0x180011d71  mov     r9d, 16Ah
0x180011d77  mov     [rsp+2D0h+var_2A0], rax
0x180011d7c  mov     dword ptr [rsp+2D0h+lpcbData], 80070057h
0x180011d84  mov     r8, r12
0x180011d87  mov     [rsp+2D0h+phkResult], rbx
0x180011d8c  mov     edx, r14d
0x180011d8f  mov     ecx, r13d
0x180011d92  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011d97  jmp     short loc_180011DD2
0x180011d99  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011da0  jz      short loc_180011DCB
0x180011da2  lea     rcx, aUnableToReadTr; "Unable to read trace path"
0x180011da9  mov     r9d, 172h
0x180011daf  mov     [rsp+2D0h+var_2A0], rcx
0x180011db4  mov     r8, r12
0x180011db7  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180011dbb  mov     ecx, r13d
0x180011dbe  mov     edx, r14d
0x180011dc1  mov     [rsp+2D0h+phkResult], rbx
0x180011dc6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011dcb  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180011dd2  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180011dd7  lea     rax, [rsp+2D0h+Data]
0x180011ddc  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180011de1  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180011de6  lea     rax, [rsp+2D0h+Data+8]
0x180011deb  mov     [rsp+2D0h+Data], r15d
0x180011df0  xor     r8d, r8d; lpReserved
0x180011df3  mov     [rsp+2D0h+phkResult], rax; lpData
0x180011df8  lea     rdx, aMemorybuffersi; "MemoryBufferSize"
0x180011dff  call    cs:__imp_RegQueryValueExW
0x180011e05  test    eax, eax
0x180011e07  jnz     short loc_180011E6B
0x180011e09  cmp     [rsp+2D0h+Data+4], r15d
0x180011e0e  jnz     short loc_180011E6B
0x180011e10  cmp     [rsp+2D0h+Data], r15d
0x180011e15  jnz     short loc_180011E6B
0x180011e17  mov     eax, [rsp+2D0h+Data+8]
0x180011e1b  mov     ecx, 0FFFFFFFh
0x180011e20  cmp     eax, ecx
0x180011e22  jbe     short loc_180011E2A
0x180011e24  mov     eax, ecx
0x180011e26  mov     [rsp+2D0h+Data+8], ecx
0x180011e2a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011e31  mov     cs:?MemoryBufferSize@TraceOutputSettings@@2KA, eax; ulong TraceOutputSettings::MemoryBufferSize
0x180011e37  jz      short loc_180011E9D
0x180011e39  mov     dword ptr [rsp+2D0h+var_298], eax
0x180011e3d  mov     r9d, 18Fh
0x180011e43  lea     rax, aMemoryBufferSi; "Memory buffer size is now %d"
0x180011e4a  mov     r8, r12
0x180011e4d  mov     [rsp+2D0h+var_2A0], rax
0x180011e52  mov     edx, 3
0x180011e57  mov     [rsp+2D0h+lpcbData], rsi
0x180011e5c  mov     ecx, r13d
0x180011e5f  mov     [rsp+2D0h+phkResult], rbx
0x180011e64  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011e69  jmp     short loc_180011E9D
0x180011e6b  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011e72  jz      short loc_180011E9D
0x180011e74  lea     rcx, aUnableToReadMe; "Unable to read memory buffer size"
0x180011e7b  mov     r9d, 198h
0x180011e81  mov     [rsp+2D0h+var_2A0], rcx
0x180011e86  mov     r8, r12
0x180011e89  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180011e8d  mov     ecx, r13d
0x180011e90  mov     edx, r14d
0x180011e93  mov     [rsp+2D0h+phkResult], rbx
0x180011e98  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011e9d  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180011ea2  lea     rax, [rsp+2D0h+Data]
0x180011ea7  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180011eac  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180011eb1  lea     rax, [rsp+2D0h+Data+8]
0x180011eb6  mov     [rsp+2D0h+Data], r15d
0x180011ebb  xor     r8d, r8d; lpReserved
0x180011ebe  mov     [rsp+2D0h+phkResult], rax; lpData
0x180011ec3  lea     rdx, aDebugoutenable; "DebugOutEnabled"
0x180011eca  call    cs:__imp_RegQueryValueExW
0x180011ed0  test    eax, eax
0x180011ed2  jnz     short loc_180011F2A
0x180011ed4  cmp     [rsp+2D0h+Data+4], r15d
0x180011ed9  jnz     short loc_180011F2A
0x180011edb  cmp     [rsp+2D0h+Data], r15d
0x180011ee0  jnz     short loc_180011F2A
0x180011ee2  mov     eax, [rsp+2D0h+Data+8]
0x180011ee6  test    eax, eax
0x180011ee8  setnz   cs:?DebugOutEnabled@TraceOutputSettings@@2_NA; bool TraceOutputSettings::DebugOutEnabled
0x180011eef  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011ef6  jz      short loc_180011F5C
0x180011ef8  mov     dword ptr [rsp+2D0h+var_298], eax
0x180011efc  mov     r9d, 1AEh
0x180011f02  lea     rax, aDebugOutEnable; "Debug out enabled is now %d"
0x180011f09  mov     r8, r12
0x180011f0c  mov     [rsp+2D0h+var_2A0], rax
0x180011f11  mov     edx, 3
0x180011f16  mov     [rsp+2D0h+lpcbData], rsi
0x180011f1b  mov     ecx, r13d
0x180011f1e  mov     [rsp+2D0h+phkResult], rbx
0x180011f23  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011f28  jmp     short loc_180011F5C
0x180011f2a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180011f31  jz      short loc_180011F5C
0x180011f33  lea     rcx, aUnableToReadDe; "Unable to read debug out enabled"
0x180011f3a  mov     r9d, 1B7h
0x180011f40  mov     [rsp+2D0h+var_2A0], rcx
0x180011f45  mov     r8, r12
0x180011f48  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180011f4c  mov     ecx, r13d
0x180011f4f  mov     edx, r14d
0x180011f52  mov     [rsp+2D0h+phkResult], rbx
0x180011f57  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
  ... truncated ...
```
