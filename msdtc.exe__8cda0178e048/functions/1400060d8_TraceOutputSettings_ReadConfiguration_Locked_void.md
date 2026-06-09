# TraceOutputSettings::ReadConfiguration_Locked(void)

- ea: `0x1400060d8`
- end: `0x14000676d`
- name: `?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ`
- size: `1685`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006010`

## callees

- `0x140001f9c`
- `0x140002980`
- `0x1400060d8`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006710`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006273`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006710`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000612d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000612d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400062da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006320`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400064ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400065ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006679`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006320`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400064ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400065ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140006679`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x140006193`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x140006193`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400063a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400063a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400063c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400063c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006379`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140006379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400063af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400063af`

## string_xrefs

- `0x14000613e`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x140006137`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x1400061f4`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x14000623e`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x140006279`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x1400063d0`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x140006421`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x140006451`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x1400064bb`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x140006232`: `Unable to read level for source %S`
- `0x14000628b`: `Unable to open sources key`
- `0x14000630d`: `TraceFilePath`
- `0x1400063f2`: `Using new trace file path: %s`
- `0x14000642e`: `Unable to duplicate trace path`
- `0x14000645a`: `Ignoring empty-string trace directory`
- `0x140006492`: `Unable to read trace path`
- `0x140006564`: `Unable to read memory buffer size`
- `0x140006623`: `Unable to read debug out enabled`
- `0x1400066e2`: `Unable to read Including Image Name in Trace File Name`
- `0x140006721`: `Unable to open output key`

## pseudocode

```c
void TraceOutputSettings::ReadConfiguration_Locked(void)
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  const CHAR *v2; // rdx
  bool v3; // zf
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rdi
  DWORD v8; // eax
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _WORD v14[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Sources", 0, 0x101u, &hKey) )
  {
    if ( TraceOutputSettings::fInitialized )
      TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
  }
  else
  {
    v0 = 0;
    v1 = 0;
    do
    {
      v2 = *(const CHAR **)((char *)&TraceSources + v1 + 8);
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExA(hKey, v2, 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
      {
        v3 = !TraceOutputSettings::fInitialized;
        *(_DWORD *)((char *)&TraceSources + v1 + 16) = *(_DWORD *)Data;
        if ( !v3 )
          TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
      }
      else if ( TraceOutputSettings::fInitialized )
      {
        TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
      }
      ++v0;
      v1 += 24;
    }
    while ( v0 != 22 );
    RegCloseKey(hKey);
  }
  phkResult = 0;
  if ( !RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Output", 0, 0x101u, &phkResult) )
  {
    Type = 0;
    *(_DWORD *)Data = 522;
    cbData = 0;
    if ( RegQueryValueExW(phkResult, L"TraceFilePath", 0, &cbData, (LPBYTE)v14, (LPDWORD)Data) || cbData != 1 )
    {
      if ( !TraceOutputSettings::fInitialized )
        goto LABEL_32;
      goto LABEL_31;
    }
    v14[260] = 0;
    v4 = -1;
    do
      ++v4;
    while ( v14[v4] );
    v5 = v4 + 1;
    if ( v4 + 1 > 1 )
    {
      if ( v14[v5 - 1] != 92 )
        goto LABEL_23;
      if ( v4 > 1 )
      {
        v5 = v4;
LABEL_23:
        v6 = (unsigned __int16 *)LocalAlloc(0, 2 * v5);
        v7 = v6;
        if ( v6 )
        {
          StringCchCopyW(v6, v5, v14);
          EnterCriticalSection(&stru_140010720);
          LocalFree(TraceOutputSettings::TraceFilePath);
          TraceOutputSettings::TraceFilePath = v7;
          LeaveCriticalSection(&stru_140010720);
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          goto LABEL_32;
        }
        if ( !TraceOutputSettings::fInitialized )
        {
LABEL_32:
          *(_DWORD *)Data = 4;
          if ( !RegQueryValueExW(phkResult, L"MemoryBufferSize", 0, &cbData, (LPBYTE)&Type, (LPDWORD)Data)
            && cbData == 4
            && *(_DWORD *)Data == 4 )
          {
            v8 = Type;
            if ( Type > 0xFFFFFFF )
            {
              v8 = 0xFFFFFFF;
              Type = 0xFFFFFFF;
            }
            TraceOutputSettings::MemoryBufferSize = v8;
            if ( TraceOutputSettings::fInitialized )
              TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          else if ( TraceOutputSettings::fInitialized )
          {
            TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          *(_DWORD *)Data = 4;
          if ( !RegQueryValueExW(phkResult, L"DebugOutEnabled", 0, &cbData, (LPBYTE)&Type, (LPDWORD)Data)
            && cbData == 4
            && *(_DWORD *)Data == 4 )
          {
            TraceOutputSettings::DebugOutEnabled = Type != 0;
            if ( TraceOutputSettings::fInitialized )
              TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          else if ( TraceOutputSettings::fInitialized )
          {
            TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          *(_DWORD *)Data = 4;
          if ( !RegQueryValueExW(
                  phkResult,
                  L"ImageNameInTraceFileNameEnabled",
                  0,
                  &cbData,
                  (LPBYTE)&Type,
                  (LPDWORD)Data)
            && cbData == 4
            && *(_DWORD *)Data == 4 )
          {
            TraceOutputSettings::ImageNameInTraceFileNameEnabled = Type != 0;
            if ( TraceOutputSettings::fInitialized )
              TraceStringInline(2, 3, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          else if ( TraceOutputSettings::fInitialized )
          {
            TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
          }
          RegCloseKey(phkResult);
          return;
        }
LABEL_31:
        TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
        goto LABEL_32;
      }
    }
    if ( !TraceOutputSettings::fInitialized )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( TraceOutputSettings::fInitialized )
    TraceStringInline(2, 1, L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp");
}

```

## disassembly

```asm
0x1400060d8  push    rbp
0x1400060da  push    rbx
0x1400060db  push    rsi
0x1400060dc  push    rdi
0x1400060dd  push    r12
0x1400060df  push    r13
0x1400060e1  push    r14
0x1400060e3  push    r15
0x1400060e5  lea     rbp, [rsp-198h]
0x1400060ed  sub     rsp, 298h
0x1400060f4  mov     rax, cs:__security_cookie
0x1400060fb  xor     rax, rsp
0x1400060fe  mov     [rbp+1D0h+var_50], rax
0x140006105  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x14000610c  lea     rax, [rsp+2D0h+hKey]
0x140006111  xor     esi, esi
0x140006113  mov     [rsp+2D0h+phkResult], rax; phkResult
0x140006118  mov     r9d, 101h; samDesired
0x14000611e  mov     [rsp+2D0h+hKey], rsi
0x140006123  xor     r8d, r8d; ulOptions
0x140006126  lea     rdx, aSources; "Sources"
0x14000612d  call    cs:__imp_RegOpenKeyExW
0x140006133  lea     r15d, [rsi+4]
0x140006137  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x14000613e  lea     r12, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x140006145  lea     r13d, [rsi+2]
0x140006149  lea     r14d, [rsi+1]
0x14000614d  test    eax, eax
0x14000614f  jnz     loc_140006282
0x140006155  mov     edi, esi
0x140006157  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x14000615e  mov     ebx, esi
0x140006160  mov     rdx, [rbx+rcx+8]; lpValueName
0x140006165  lea     rax, [rsp+2D0h+cbData]
0x14000616a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14000616f  lea     r9, [rsp+2D0h+Type]; lpType
0x140006174  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x140006179  xor     r8d, r8d; lpReserved
0x14000617c  lea     rax, [rsp+2D0h+Data]
0x140006181  mov     [rsp+2D0h+Type], esi
0x140006185  mov     [rsp+2D0h+phkResult], rax; lpData
0x14000618a  mov     dword ptr [rsp+2D0h+Data], esi
0x14000618e  mov     [rsp+2D0h+cbData], r15d
0x140006193  call    cs:__imp_RegQueryValueExA
0x140006199  mov     ecx, eax
0x14000619b  test    eax, eax
0x14000619d  jnz     short loc_14000620C
0x14000619f  cmp     [rsp+2D0h+Type], r15d
0x1400061a4  jnz     short loc_14000620C
0x1400061a6  cmp     [rsp+2D0h+cbData], r15d
0x1400061ab  jnz     short loc_14000620C
0x1400061ad  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x1400061b4  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x1400061bb  mov     eax, dword ptr [rsp+2D0h+Data]
0x1400061bf  mov     [rbx+rcx+10h], eax
0x1400061c3  jz      loc_14000625D
0x1400061c9  mov     [rsp+2D0h+var_290], eax
0x1400061cd  mov     r9d, 10Bh
0x1400061d3  mov     rax, [rbx+rcx+8]
0x1400061d8  mov     r8, r12
0x1400061db  mov     [rsp+2D0h+var_298], rax
0x1400061e0  mov     edx, 3
0x1400061e5  lea     rax, aNowTracingSAtL; "Now tracing %S at level %d"
0x1400061ec  mov     ecx, r13d
0x1400061ef  mov     [rsp+2D0h+var_2A0], rax
0x1400061f4  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x1400061fb  mov     [rsp+2D0h+lpcbData], rsi
0x140006200  mov     [rsp+2D0h+phkResult], rax
0x140006205  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x14000620a  jmp     short loc_140006256
0x14000620c  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006213  jz      short loc_140006256
0x140006215  lea     rax, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x14000621c  mov     r9d, 115h
0x140006222  mov     rax, [rbx+rax+8]
0x140006227  mov     r8, r12
0x14000622a  mov     [rsp+2D0h+var_298], rax
0x14000622f  mov     edx, r14d
0x140006232  lea     rax, aUnableToReadLe; "Unable to read level for source %S"
0x140006239  mov     [rsp+2D0h+var_2A0], rax
0x14000623e  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x140006245  mov     dword ptr [rsp+2D0h+lpcbData], ecx
0x140006249  mov     ecx, r13d
0x14000624c  mov     [rsp+2D0h+phkResult], rax
0x140006251  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140006256  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x14000625d  add     rdi, r14
0x140006260  add     rbx, 18h
0x140006264  cmp     rdi, 16h
0x140006268  jnz     loc_140006160
0x14000626e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x140006273  call    cs:__imp_RegCloseKey
0x140006279  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x140006280  jmp     short loc_1400062B4
0x140006282  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006289  jz      short loc_1400062B4
0x14000628b  lea     rcx, aUnableToOpenSo; "Unable to open sources key"
0x140006292  mov     r9d, 120h
0x140006298  mov     [rsp+2D0h+var_2A0], rcx
0x14000629d  mov     r8, r12
0x1400062a0  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x1400062a4  mov     ecx, r13d
0x1400062a7  mov     edx, r14d
0x1400062aa  mov     [rsp+2D0h+phkResult], rbx
0x1400062af  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1400062b4  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x1400062bb  lea     rax, [rsp+2D0h+var_270]
0x1400062c0  mov     r9d, 101h; samDesired
0x1400062c6  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1400062cb  xor     r8d, r8d; ulOptions
0x1400062ce  mov     [rsp+2D0h+var_270], rsi
0x1400062d3  lea     rdx, aOutput; "Output"
0x1400062da  call    cs:__imp_RegOpenKeyExW
0x1400062e0  test    eax, eax
0x1400062e2  jnz     loc_140006718
0x1400062e8  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1400062ed  lea     rax, [rsp+2D0h+Data]
0x1400062f2  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1400062f7  lea     r9, [rsp+2D0h+cbData]; lpType
0x1400062fc  lea     rax, [rsp+2D0h+var_260]
0x140006301  mov     [rsp+2D0h+Type], esi
0x140006305  xor     r8d, r8d; lpReserved
0x140006308  mov     [rsp+2D0h+phkResult], rax; lpData
0x14000630d  lea     rdx, aTracefilepath; "TraceFilePath"
0x140006314  mov     dword ptr [rsp+2D0h+Data], 20Ah
0x14000631c  mov     [rsp+2D0h+cbData], esi
0x140006320  call    cs:__imp_RegQueryValueExW
0x140006326  test    eax, eax
0x140006328  jnz     loc_140006489
0x14000632e  cmp     [rsp+2D0h+cbData], r14d
0x140006333  jnz     loc_140006489
0x140006339  mov     [rbp+1D0h+var_58], si
0x140006340  lea     rcx, [rsp+2D0h+var_260]
0x140006345  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006349  inc     rax
0x14000634c  cmp     [rcx+rax*2], si
0x140006350  jnz     short loc_140006349
0x140006352  lea     rbx, [rax+1]
0x140006356  cmp     rbx, r14
0x140006359  jbe     loc_14000644A
0x14000635f  cmp     word ptr [rsp+rbx*2+2D0h+hKey+6], 5Ch ; '\'
0x140006365  jnz     short loc_140006373
0x140006367  cmp     rax, r14
0x14000636a  jbe     loc_14000644A
0x140006370  mov     rbx, rax
0x140006373  lea     rdx, [rbx+rbx]; uBytes
0x140006377  xor     ecx, ecx; uFlags
0x140006379  call    cs:__imp_LocalAlloc
0x14000637f  mov     rdi, rax
0x140006382  test    rax, rax
0x140006385  jz      loc_14000641A
0x14000638b  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x140006390  mov     rdx, rbx; unsigned __int64
0x140006393  mov     rcx, rax; unsigned __int16 *
0x140006396  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000639b  lea     rcx, stru_140010720; lpCriticalSection
0x1400063a2  call    cs:__imp_EnterCriticalSection
0x1400063a8  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x1400063af  call    cs:__imp_LocalFree
0x1400063b5  lea     rcx, stru_140010720; lpCriticalSection
0x1400063bc  mov     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rdi; ushort * TraceOutputSettings::TraceFilePath
0x1400063c3  call    cs:__imp_LeaveCriticalSection
0x1400063c9  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x1400063d0  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x1400063d7  jz      loc_1400064C2
0x1400063dd  mov     rax, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x1400063e4  mov     r9d, 157h
0x1400063ea  mov     [rsp+2D0h+var_298], rax
0x1400063ef  mov     r8, r12
0x1400063f2  lea     rax, aUsingNewTraceF; "Using new trace file path: %s"
0x1400063f9  mov     edx, 3
0x1400063fe  mov     [rsp+2D0h+var_2A0], rax
0x140006403  mov     ecx, r13d
0x140006406  mov     [rsp+2D0h+lpcbData], rsi
0x14000640b  mov     [rsp+2D0h+phkResult], rbx
0x140006410  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140006415  jmp     loc_1400064C2
0x14000641a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006421  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x140006428  jz      loc_1400064C2
0x14000642e  lea     rax, aUnableToDuplic; "Unable to duplicate trace path"
0x140006435  mov     r9d, 160h
0x14000643b  mov     [rsp+2D0h+var_2A0], rax
0x140006440  mov     dword ptr [rsp+2D0h+lpcbData], 8007000Eh
0x140006448  jmp     short loc_140006474
0x14000644a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006451  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x140006458  jz      short loc_1400064C2
0x14000645a  lea     rax, aIgnoringEmptyS; "Ignoring empty-string trace directory"
0x140006461  mov     r9d, 16Ah
0x140006467  mov     [rsp+2D0h+var_2A0], rax
0x14000646c  mov     dword ptr [rsp+2D0h+lpcbData], 80070057h
0x140006474  mov     r8, r12
0x140006477  mov     [rsp+2D0h+phkResult], rbx
0x14000647c  mov     edx, r14d
0x14000647f  mov     ecx, r13d
0x140006482  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140006487  jmp     short loc_1400064C2
0x140006489  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006490  jz      short loc_1400064BB
0x140006492  lea     rcx, aUnableToReadTr; "Unable to read trace path"
0x140006499  mov     r9d, 172h
0x14000649f  mov     [rsp+2D0h+var_2A0], rcx
0x1400064a4  mov     r8, r12
0x1400064a7  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x1400064ab  mov     ecx, r13d
0x1400064ae  mov     edx, r14d
0x1400064b1  mov     [rsp+2D0h+phkResult], rbx
0x1400064b6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1400064bb  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x1400064c2  mov     rcx, [rsp+2D0h+var_270]; hKey
0x1400064c7  lea     rax, [rsp+2D0h+Data]
0x1400064cc  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x1400064d1  lea     r9, [rsp+2D0h+cbData]; lpType
0x1400064d6  lea     rax, [rsp+2D0h+Type]
0x1400064db  mov     dword ptr [rsp+2D0h+Data], r15d
0x1400064e0  xor     r8d, r8d; lpReserved
0x1400064e3  mov     [rsp+2D0h+phkResult], rax; lpData
0x1400064e8  lea     rdx, aMemorybuffersi; "MemoryBufferSize"
0x1400064ef  call    cs:__imp_RegQueryValueExW
0x1400064f5  test    eax, eax
0x1400064f7  jnz     short loc_14000655B
0x1400064f9  cmp     [rsp+2D0h+cbData], r15d
0x1400064fe  jnz     short loc_14000655B
0x140006500  cmp     dword ptr [rsp+2D0h+Data], r15d
0x140006505  jnz     short loc_14000655B
0x140006507  mov     eax, [rsp+2D0h+Type]
0x14000650b  mov     ecx, 0FFFFFFFh
0x140006510  cmp     eax, ecx
0x140006512  jbe     short loc_14000651A
0x140006514  mov     eax, ecx
0x140006516  mov     [rsp+2D0h+Type], ecx
0x14000651a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006521  mov     cs:?MemoryBufferSize@TraceOutputSettings@@2KA, eax; ulong TraceOutputSettings::MemoryBufferSize
0x140006527  jz      short loc_14000658D
0x140006529  mov     dword ptr [rsp+2D0h+var_298], eax
0x14000652d  mov     r9d, 18Fh
0x140006533  lea     rax, aMemoryBufferSi; "Memory buffer size is now %d"
0x14000653a  mov     r8, r12
0x14000653d  mov     [rsp+2D0h+var_2A0], rax
0x140006542  mov     edx, 3
0x140006547  mov     [rsp+2D0h+lpcbData], rsi
0x14000654c  mov     ecx, r13d
0x14000654f  mov     [rsp+2D0h+phkResult], rbx
0x140006554  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140006559  jmp     short loc_14000658D
0x14000655b  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006562  jz      short loc_14000658D
0x140006564  lea     rcx, aUnableToReadMe; "Unable to read memory buffer size"
0x14000656b  mov     r9d, 198h
0x140006571  mov     [rsp+2D0h+var_2A0], rcx
0x140006576  mov     r8, r12
0x140006579  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x14000657d  mov     ecx, r13d
0x140006580  mov     edx, r14d
0x140006583  mov     [rsp+2D0h+phkResult], rbx
0x140006588  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x14000658d  mov     rcx, [rsp+2D0h+var_270]; hKey
0x140006592  lea     rax, [rsp+2D0h+Data]
0x140006597  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x14000659c  lea     r9, [rsp+2D0h+cbData]; lpType
0x1400065a1  lea     rax, [rsp+2D0h+Type]
0x1400065a6  mov     dword ptr [rsp+2D0h+Data], r15d
0x1400065ab  xor     r8d, r8d; lpReserved
0x1400065ae  mov     [rsp+2D0h+phkResult], rax; lpData
0x1400065b3  lea     rdx, aDebugoutenable; "DebugOutEnabled"
0x1400065ba  call    cs:__imp_RegQueryValueExW
0x1400065c0  test    eax, eax
0x1400065c2  jnz     short loc_14000661A
0x1400065c4  cmp     [rsp+2D0h+cbData], r15d
0x1400065c9  jnz     short loc_14000661A
0x1400065cb  cmp     dword ptr [rsp+2D0h+Data], r15d
0x1400065d0  jnz     short loc_14000661A
0x1400065d2  mov     eax, [rsp+2D0h+Type]
0x1400065d6  test    eax, eax
0x1400065d8  setnz   cs:?DebugOutEnabled@TraceOutputSettings@@2_NA; bool TraceOutputSettings::DebugOutEnabled
0x1400065df  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x1400065e6  jz      short loc_14000664C
0x1400065e8  mov     dword ptr [rsp+2D0h+var_298], eax
0x1400065ec  mov     r9d, 1AEh
0x1400065f2  lea     rax, aDebugOutEnable; "Debug out enabled is now %d"
0x1400065f9  mov     r8, r12
0x1400065fc  mov     [rsp+2D0h+var_2A0], rax
0x140006601  mov     edx, 3
0x140006606  mov     [rsp+2D0h+lpcbData], rsi
0x14000660b  mov     ecx, r13d
0x14000660e  mov     [rsp+2D0h+phkResult], rbx
0x140006613  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x140006618  jmp     short loc_14000664C
0x14000661a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x140006621  jz      short loc_14000664C
0x140006623  lea     rcx, aUnableToReadDe; "Unable to read debug out enabled"
0x14000662a  mov     r9d, 1B7h
0x140006630  mov     [rsp+2D0h+var_2A0], rcx
0x140006635  mov     r8, r12
0x140006638  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x14000663c  mov     ecx, r13d
0x14000663f  mov     edx, r14d
0x140006642  mov     [rsp+2D0h+phkResult], rbx
0x140006647  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
  ... truncated ...
```
