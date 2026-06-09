# LoadEventTable

- ea: `0x180182fb0`
- end: `0x180183295`
- name: `LoadEventTable`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800a504c`

## callees

- `0x18000bb20`
- `0x18000ed84`
- `0x180182fb0`
- `0x1801843d0`
- `0x180184740`
- `0x1801848f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801830b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801830b1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180183104`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180183104`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180183168`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180183168`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180183048`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180183048`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1801830da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1801830da`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180183269`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180183269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18018313e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18018313e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1801831ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1801831ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801831e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1801831e6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1801830a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1801830a7`

## string_xrefs

- `0x180183081`: `%SystemRoot%\adam\adammsg.dll`
- `0x180183088`: `%SystemRoot%\system32\ntdsmsg.dll`

## pseudocode

```c
HANDLE LoadEventTable()
{
  __int64 v0; // rdx
  int v1; // eax
  DWORD LastError; // r14d
  const CHAR *v3; // rcx
  __int64 v4; // r15
  __int64 v5; // r14
  const CHAR *v6; // rdx
  __int64 v7; // rdx
  int v8; // eax
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD Type; // [rsp+78h] [rbp+10h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF

  Type = 0;
  cbData = 0;
  if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 1) )
  {
    v1 = CheckWPPLevelFlagsEnabledForProvider(0, v0, 1);
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      133274,
      4,
      1,
      v1,
      0,
      26,
      &WPP_23b878d81fc4362e33a6463acfbe4670_Traceguids);
  }
  if ( !dword_18050D4D0 )
  {
    InitializeCriticalSection(&stru_18050D4D8);
    dword_18050D4D0 = 1;
  }
  if ( !gszMsgFile )
  {
    LastError = 0;
    v3 = "%SystemRoot%\\adam\\adammsg.dll";
    if ( !gpszAdamServiceName )
      v3 = (const CHAR *)"%SystemRoot%\\system32\\ntdsmsg.dll";
    if ( !ExpandEnvironmentStringsA(v3, &gszMsgFile, 0x104u) )
      LastError = GetLastError();
    if ( LastError )
      goto LABEL_28;
  }
  if ( ghMsgFile || (ghMsgFile = LoadLibraryExA(&gszMsgFile, 0, 0x22u)) != 0 )
  {
    if ( !ghevLoggingChange )
      ghevLoggingChange = CreateEventA(0, 1, 0, 0);
    if ( ghkLoggingKey
      || (RegOpenKeyExA(HKEY_LOCAL_MACHINE, gpszDSAEventSection, 0, 0x2000000u, &ghkLoggingKey), ghkLoggingKey) )
    {
      if ( !srw_gLogMsgOverrides_initialized )
      {
        srw_gLogMsgOverrides_initialized = 1;
        InitializeSRWLock(&srw_gLogMsgOverrides);
      }
      v4 = 0;
      v5 = 0;
      do
      {
        v6 = *(const CHAR **)&DsEventConfig[v5 * 8 + 24];
        if ( v6 )
        {
          cbData = 4;
          if ( RegQueryValueExA(ghkLoggingKey, v6, 0, &Type, (LPBYTE)&qword_18050D320[v5] + 4, &cbData) )
          {
            Data = 0;
            RegSetValueExA(ghkLoggingKey, *(LPCSTR *)&DsEventConfig[v5 * 8 + 24], 0, 4u, (const BYTE *)&Data, 4u);
          }
        }
        ++v4;
        v5 += 2;
      }
      while ( v4 != 27 );
      RegisterLogOverrides();
      RegisterLogMsgOverrides();
      if ( (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 1) )
      {
        v8 = CheckWPPLevelFlagsEnabledForProvider(0, v7, 1);
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133393,
          4,
          1,
          v8,
          0,
          27,
          &WPP_23b878d81fc4362e33a6463acfbe4670_Traceguids);
      }
      RegNotifyChangeKeyValue(ghkLoggingKey, 1, 7u, ghevLoggingChange, 1);
    }
    return ghevLoggingChange;
  }
  else
  {
LABEL_28:
    UnloadEventTable();
    return 0;
  }
}

```

## disassembly

```asm
0x180182fb0  mov     [rsp+arg_18], rsi
0x180182fb5  push    rdi
0x180182fb6  push    r12
0x180182fb8  push    r13
0x180182fba  push    r14
0x180182fbc  push    r15
0x180182fbe  sub     rsp, 40h
0x180182fc2  mov     [rsp+68h+Type], 0
0x180182fca  mov     [rsp+68h+cbData], 0
0x180182fd2  mov     edi, 1
0x180182fd7  mov     r8d, edi
0x180182fda  lea     esi, [rdi+3]
0x180182fdd  mov     edx, esi
0x180182fdf  xor     ecx, ecx
0x180182fe1  call    CheckWPPLevelFlagsEnabledForProvider
0x180182fe6  test    eax, eax
0x180182fe8  jz      short loc_180183030
0x180182fea  mov     r8d, edi
0x180182fed  xor     ecx, ecx
0x180182fef  call    CheckWPPLevelFlagsEnabledForProvider
0x180182ff4  lea     r12, WPP_23b878d81fc4362e33a6463acfbe4670_Traceguids
0x180182ffb  mov     [rsp+68h+var_30], r12; LPCGUID
0x180183000  mov     [rsp+68h+var_38], 1Ah; __int16
0x180183007  mov     dword ptr [rsp+68h+lpcbData], 0; int
0x18018300f  mov     dword ptr [rsp+68h+phkResult], eax; int
0x180183013  mov     r9d, edi; int
0x180183016  mov     r8d, esi; int
0x180183019  mov     edx, 2089Ah; int
0x18018301e  mov     rcx, cs:WPP_GLOBAL_Control
0x180183025  mov     rcx, [rcx+10h]; int
0x180183029  call    WPP_SF_
0x18018302e  jmp     short loc_180183037
0x180183030  lea     r12, WPP_23b878d81fc4362e33a6463acfbe4670_Traceguids
0x180183037  mov     eax, cs:dword_18050D4D0
0x18018303d  test    eax, eax
0x18018303f  jnz     short loc_180183075
0x180183041  lea     rcx, stru_18050D4D8; lpCriticalSection
0x180183048  call    cs:__imp_InitializeCriticalSection
0x18018304e  mov     eax, edi
0x180183050  mov     cs:dword_18050D4D0, eax
0x180183056  jmp     short loc_18018306D
0x180183058  mov     edi, 1
0x18018305d  lea     esi, [rdi+3]
0x180183060  lea     r12, WPP_23b878d81fc4362e33a6463acfbe4670_Traceguids
0x180183067  mov     eax, cs:dword_18050D4D0
0x18018306d  test    eax, eax
0x18018306f  jz      loc_180183278
0x180183075  cmp     cs:gszMsgFile, 0
0x18018307c  jnz     short loc_1801830C3
0x18018307e  xor     r14d, r14d
0x180183081  lea     rcx, aSystemrootAdam; "%SystemRoot%\\adam\\adammsg.dll"
0x180183088  lea     rax, Data; "%SystemRoot%\\system32\\ntdsmsg.dll"
0x18018308f  cmp     cs:gpszAdamServiceName, r14
0x180183096  cmovz   rcx, rax; lpSrc
0x18018309a  mov     r8d, 104h; nSize
0x1801830a0  lea     rdx, gszMsgFile; lpDst
0x1801830a7  call    cs:__imp_ExpandEnvironmentStringsA
0x1801830ad  test    eax, eax
0x1801830af  jnz     short loc_1801830BA
0x1801830b1  call    cs:__imp_GetLastError
0x1801830b7  mov     r14d, eax
0x1801830ba  test    r14d, r14d
0x1801830bd  jnz     loc_180183278
0x1801830c3  cmp     cs:ghMsgFile, 0
0x1801830cb  jnz     short loc_1801830F0
0x1801830cd  xor     edx, edx; hFile
0x1801830cf  lea     r8d, [rdx+22h]; dwFlags
0x1801830d3  lea     rcx, gszMsgFile; lpLibFileName
0x1801830da  call    cs:__imp_LoadLibraryExA
0x1801830e0  mov     cs:ghMsgFile, rax
0x1801830e7  test    rax, rax
0x1801830ea  jz      loc_180183278
0x1801830f0  cmp     cs:ghevLoggingChange, 0
0x1801830f8  jnz     short loc_180183111
0x1801830fa  xor     r9d, r9d; lpName
0x1801830fd  xor     r8d, r8d; bInitialState
0x180183100  mov     edx, edi; bManualReset
0x180183102  xor     ecx, ecx; lpEventAttributes
0x180183104  call    cs:__imp_CreateEventA
0x18018310a  mov     cs:ghevLoggingChange, rax
0x180183111  cmp     cs:ghkLoggingKey, 0
0x180183119  jnz     short loc_180183152
0x18018311b  lea     rax, ghkLoggingKey
0x180183122  mov     [rsp+68h+phkResult], rax; phkResult
0x180183127  mov     r9d, 2000000h; samDesired
0x18018312d  xor     r8d, r8d; ulOptions
0x180183130  mov     rdx, cs:gpszDSAEventSection; lpSubKey
0x180183137  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18018313e  call    cs:__imp_RegOpenKeyExA
0x180183144  cmp     cs:ghkLoggingKey, 0
0x18018314c  jz      loc_18018326F
0x180183152  cmp     cs:srw_gLogMsgOverrides_initialized, 0
0x180183159  jnz     short loc_18018316E
0x18018315b  mov     cs:srw_gLogMsgOverrides_initialized, edi
0x180183161  lea     rcx, srw_gLogMsgOverrides; SRWLock
0x180183168  call    cs:__imp_InitializeSRWLock
0x18018316e  xor     r15d, r15d
0x180183171  xor     r14d, r14d
0x180183174  lea     r13, DsEventConfig
0x18018317b  mov     rdx, [r14+r13+18h]; lpValueName
0x180183180  test    rdx, rdx
0x180183183  jz      short loc_1801831EC
0x180183185  mov     [rsp+68h+cbData], esi
0x180183189  lea     rax, [r13+14h]
0x18018318d  add     rax, r14
0x180183190  lea     rcx, [rsp+68h+cbData]
0x180183195  mov     [rsp+68h+lpcbData], rcx; lpcbData
0x18018319a  mov     [rsp+68h+phkResult], rax; lpData
0x18018319f  lea     r9, [rsp+68h+Type]; lpType
0x1801831a4  xor     r8d, r8d; lpReserved
0x1801831a7  mov     rcx, cs:ghkLoggingKey; hKey
0x1801831ae  call    cs:__imp_RegQueryValueExA
0x1801831b4  test    eax, eax
0x1801831b6  jz      short loc_1801831EC
0x1801831b8  mov     [rsp+68h+Data], 0
0x1801831c3  mov     dword ptr [rsp+68h+lpcbData], esi; cbData
0x1801831c7  lea     rax, [rsp+68h+Data]
0x1801831cf  mov     [rsp+68h+phkResult], rax; lpData
0x1801831d4  mov     r9d, esi; dwType
0x1801831d7  xor     r8d, r8d; Reserved
0x1801831da  mov     rdx, [r14+r13+18h]; lpValueName
0x1801831df  mov     rcx, cs:ghkLoggingKey; hKey
0x1801831e6  call    cs:__imp_RegSetValueExA
0x1801831ec  add     r15, rdi
0x1801831ef  add     r14, 10h
0x1801831f3  cmp     r15, 1Bh
0x1801831f7  jnz     short loc_18018317B
0x1801831f9  call    RegisterLogOverrides
0x1801831fe  call    RegisterLogMsgOverrides
0x180183203  mov     r8d, edi
0x180183206  mov     edx, esi
0x180183208  xor     ecx, ecx
0x18018320a  call    CheckWPPLevelFlagsEnabledForProvider
0x18018320f  test    eax, eax
0x180183211  jz      short loc_18018324F
0x180183213  mov     r8d, edi
0x180183216  xor     ecx, ecx
0x180183218  call    CheckWPPLevelFlagsEnabledForProvider
0x18018321d  mov     [rsp+68h+var_30], r12; LPCGUID
0x180183222  mov     [rsp+68h+var_38], r15w; __int16
0x180183228  mov     dword ptr [rsp+68h+lpcbData], 0; int
0x180183230  mov     dword ptr [rsp+68h+phkResult], eax; int
0x180183234  mov     r9d, edi; int
0x180183237  mov     r8d, esi; int
0x18018323a  mov     edx, 20911h; int
0x18018323f  mov     rcx, cs:WPP_GLOBAL_Control
0x180183246  mov     rcx, [rcx+10h]; int
0x18018324a  call    WPP_SF_
0x18018324f  mov     dword ptr [rsp+68h+phkResult], edi; fAsynchronous
0x180183253  mov     r9, cs:ghevLoggingChange; hEvent
0x18018325a  mov     r8d, 7; dwNotifyFilter
0x180183260  mov     edx, edi; bWatchSubtree
0x180183262  mov     rcx, cs:ghkLoggingKey; hKey
0x180183269  call    cs:__imp_RegNotifyChangeKeyValue
0x18018326f  mov     rax, cs:ghevLoggingChange
0x180183276  jmp     short loc_18018327F
0x180183278  call    UnloadEventTable
0x18018327d  xor     eax, eax
0x18018327f  mov     rsi, [rsp+68h+arg_18]
0x180183287  add     rsp, 40h
0x18018328b  pop     r15
0x18018328d  pop     r14
0x18018328f  pop     r13
0x180183291  pop     r12
0x180183293  pop     rdi
0x180183294  retn
```
