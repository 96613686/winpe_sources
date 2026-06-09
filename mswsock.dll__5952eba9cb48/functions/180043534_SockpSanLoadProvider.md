# SockpSanLoadProvider

- ea: `0x180043534`
- end: `0x18004407f`
- name: `SockpSanLoadProvider`
- size: `2891`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180044090`

## callees

- `0x1800016a0`
- `0x1800222f0`
- `0x180022ba2`
- `0x180022bae`
- `0x180022bd2`
- `0x1800253fc`
- `0x180038104`
- `0x18003847c`
- `0x180038570`
- `0x18003ae8c`
- `0x18003aec4`
- `0x180043534`
- `0x180053010`

## import_xrefs

- `ntdll!RtlRegisterSecureMemoryCacheCallback` at `0x180043df4`
- `ntdll!RtlRegisterSecureMemoryCacheCallback` at `0x180043df4`
- `ntdll!RtlFreeUnicodeString` at `0x180043d5c`
- `ntdll!RtlFreeUnicodeString` at `0x180043d5c`
- `ntdll!RtlStringFromGUID` at `0x180043b6f`
- `ntdll!RtlStringFromGUID` at `0x180043b6f`
- `ntdll!RtlFreeHeap` at `0x180043d4c`
- `ntdll!RtlFreeHeap` at `0x18004404d`
- `ntdll!RtlFreeHeap` at `0x180043d4c`
- `ntdll!RtlFreeHeap` at `0x18004404d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043efb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043efb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043ebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043dcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044019`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043632`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180043632`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180043daf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x180043daf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800436a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800436a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800436da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800436da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044000`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044000`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043d34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043d34`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043ce1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c5e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043ce1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043bfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043bfe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180043e63`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180043e63`

## string_xrefs

- `0x180043bb9`: `System\CurrentControlSet\Services\Winsock\Parameters\TCP on SAN\`

## pseudocode

```c
__int64 __fastcall SockpSanLoadProvider(__int64 a1)
{
  bool v1; // zf
  int v4; // ecx
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rdi
  _QWORD *v10; // rsi
  __int64 *v11; // r8
  int v12; // eax
  int v13; // ecx
  _QWORD *v14; // r13
  _QWORD *v15; // r12
  __int64 v16; // rdx
  rsize_t v17; // rsi
  __int64 v18; // rax
  wchar_t *v19; // r15
  bool v20; // al
  DWORD v21; // eax
  __int64 v22; // rcx
  NTSTATUS v23; // eax
  _QWORD *v24; // rax
  unsigned int (__fastcall *v25)(HMODULE *); // rax
  int v26; // ecx
  unsigned int v27; // esi
  char LastError; // al
  int v29; // ecx
  char v30; // al
  int v31; // ecx
  int v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE v36[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  HMODULE phModule; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+90h] [rbp-70h] BYREF
  CHAR v42[528]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR MultiByteStr[272]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Src[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  WCHAR Dst[264]; // [rsp+5D0h] [rbp+4D0h] BYREF

  *(_DWORD *)Data = 5;
  v1 = (*(_DWORD *)a1 & 0x80000) == 0;
  v32 = 0;
  v33 = 0;
  GuidString = 0;
  *(_DWORD *)v36 = 6;
  Type = 4;
  cbData = 0;
  hKey = 0;
  if ( !v1 )
    return 3221225659LL;
  v40 = 261;
  if ( (*(unsigned int (__fastcall **)(__int64, WCHAR *, int *, int *))(SockUpcallTable + 40))(a1 + 20, Src, &v40, &v32) == -1 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_Sd(v4, 35, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116, v32);
    if ( v32 != 8 && v32 != 10055 )
      return 3221225473LL;
    return 3221225495LL;
  }
  ExpandEnvironmentStringsW(Src, Dst, 0x105u);
  v5 = (_QWORD *)((__int64 (__fastcall *)(HANDLE, _QWORD, __int64))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 640);
  v6 = v5;
  if ( !v5 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 36, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
    return 3221225495LL;
  }
  memset_0(v5, 0, 0x280u);
  Library = LoadLibraryExW(Dst, 0, 0);
  v6[4] = Library;
  v8 = Library;
  if ( !Library )
  {
    v27 = -1073741502;
LABEL_117:
    RtlFreeHeap(SockPrivateHeap, 0, v6);
    return v27;
  }
  memset_0(v42, 0, 0x204u);
  ProcAddress = GetProcAddress(v8, "WSPStartupEx");
  if ( !ProcAddress )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(v29, 50, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116, LastError);
    }
    goto LABEL_112;
  }
  memset_0(v6 + 8, 0, 0xF0u);
  v10 = v6 + 38;
  *((_OWORD *)v6 + 19) = 0;
  *((_OWORD *)v6 + 20) = 0;
  *((_OWORD *)v6 + 21) = 0;
  v6[44] = 0;
  v11 = SockTcpProviderInfo;
  if ( *(_DWORD *)(a1 + 76) == 23 )
    v11 = SockTcp6ProviderInfo;
  v12 = ((__int64 (__fastcall *)(__int64, CHAR *, __int64 *, __int128 *, _QWORD *))ProcAddress)(
          514,
          v42,
          v11,
          &SockUpcallTable2,
          v6 + 8);
  v32 = v12;
  if ( v12 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_Sd(v13, 49, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116, v12);
    v27 = -1073741502;
    goto LABEL_113;
  }
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPRegisterMemoryGuid,
         16,
         v6 + 38,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    *v10 = 0;
  v14 = v6 + 39;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPDeregisterMemoryGuid,
         16,
         v6 + 39,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    *v14 = 0;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPRegisterRdmaMemoryGuid,
         16,
         v6 + 40,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    v6[40] = 0;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPDeregisterRdmaMemoryGuid,
         16,
         v6 + 41,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    v6[41] = 0;
  v15 = v6 + 42;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPRdmaWriteGuid,
         16,
         v6 + 42,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    *v15 = 0;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPRdmaReadGuid,
         16,
         v6 + 43,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    v6[43] = 0;
  if ( ((unsigned int (__fastcall *)(__int64, __int64, __int64 *, __int64, _QWORD *, int, int *, _QWORD, _QWORD, _QWORD, int *))v6[24])(
         -1,
         3355443206LL,
         SockpWSPMemoryRegistrationCacheCallbackGuid,
         16,
         v6 + 44,
         8,
         &v33,
         0,
         0,
         0,
         &v32) == -1 )
    v6[44] = 0;
  if ( !v6[8]
    || !v6[11]
    || !v6[13]
    || !v6[14]
    || !v6[15]
    || !v6[16]
    || !v6[17]
    || !v6[18]
    || !v6[19]
    || !v6[22]
    || !v6[24]
    || !v6[26]
    || !v6[27]
    || !v6[31]
    || !v6[34]
    || !v6[36]
    || !*v10
    || !*v14 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
    {
      v16 = 37;
      goto LABEL_102;
    }
LABEL_103:
    v25 = (unsigned int (__fastcall *)(HMODULE *))v6[13];
    if ( v25 )
    {
      LODWORD(phModule) = 0;
      if ( v25(&phModule) == -1 && (xmmword_180063D60 & 2) != 0 )
        WPP_SF_Sd(v26, 48, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116, (char)phModule);
    }
LABEL_112:
    v27 = -1073741823;
LABEL_113:
    if ( !FreeLibrary((HMODULE)v6[4]) && (xmmword_180063D60 & 2) != 0 )
    {
      v30 = GetLastError();
      WPP_SF_Sd(v31, 51, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116, v30);
    }
    goto LABEL_117;
  }
  if ( RdmaEnabled && *v15 )
  {
    RdmaEnabled = 1;
    if ( !v6[40] || !v6[41] )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v16 = 38;
LABEL_102:
        WPP_SF_S(1025, v16, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116);
        goto LABEL_103;
      }
      goto LABEL_103;
    }
  }
  else
  {
    RdmaEnabled = 0;
  }
  *((_DWORD *)v6 + 10) = *(_DWORD *)(a1 + 36);
  *((_DWORD *)v6 + 11) = *(_DWORD *)(a1 + 76);
  *((_OWORD *)v6 + 3) = *(_OWORD *)(a1 + 20);
  *((_DWORD *)v6 + 92) = *(_DWORD *)Data;
  *((_DWORD *)v6 + 93) = *(_DWORD *)v36;
  if ( RtlStringFromGUID((const GUID *const)v6 + 3, &GuidString) >= 0 )
  {
    v17 = ((unsigned __int64)GuidString.Length >> 1) + 65;
    v18 = ((__int64 (__fastcall *)(HANDLE, _QWORD, rsize_t))SockAllocateHeapRoutine)(SockPrivateHeap, 0, 2 * v17);
    v19 = (wchar_t *)v18;
    if ( v18 )
    {
      o_wcsncpy_s_0(v18, v17, L"System\\CurrentControlSet\\Services\\Winsock\\Parameters\\TCP on SAN\\", 65);
      wcsncat_s(v19, v17, GuidString.Buffer, (unsigned __int64)GuidString.Length >> 1);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey) )
      {
        if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
          WPP_SF_(1042, 39, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"SendBuffers", 0, &Type, Data, &cbData) )
        {
          if ( *(_DWORD *)Data > 5u )
          {
            if ( *(_DWORD *)Data > 0x100u )
              *((_DWORD *)v6 + 92) = 256;
            else
              *((_DWORD *)v6 + 92) = *(_DWORD *)Data;
          }
          if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
            WPP_SF_d(1042, 40, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, *((unsigned int *)v6 + 92));
        }
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"ReceiveBuffers", 0, &Type, v36, &cbData) )
        {
          if ( *(_DWORD *)v36 > 6u )
          {
            if ( *(_DWORD *)v36 > 0x100u )
              *((_DWORD *)v6 + 93) = 256;
            else
              *((_DWORD *)v6 + 93) = *(_DWORD *)v36;
          }
          if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
            WPP_SF_d(1042, 41, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, *((unsigned int *)v6 + 93));
        }
        RegCloseKey(hKey);
      }
      RtlFreeHeap(SockPrivateHeap, 0, v19);
    }
    RtlFreeUnicodeString(&GuidString);
  }
  v1 = v6[43] == 0;
  v6[2] = 1;
  v20 = !v1;
  v1 = SockSanCacheCallbackRegistered == 0;
  *((_BYTE *)v6 + 364) = v20;
  if ( v1 && v6[44] )
  {
    phModule = 0;
    if ( !GetModuleHandleExA(5u, (LPCSTR)WSPStartup, &phModule) )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v21 = GetLastError();
        WPP_SF_l(v22, 43, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, v21);
      }
      goto LABEL_103;
    }
    v23 = RtlRegisterSecureMemoryCacheCallback(SockSanSecureMemoryCacheCallback);
    if ( v23 < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 44, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, (unsigned int)v23);
      goto LABEL_103;
    }
    SockSanCacheCallbackRegistered = 1;
  }
  v33 = WideCharToMultiByte(0, 0x400u, Src, -1, MultiByteStr, 261, 0, 0);
  if ( v33 )
  {
    StringCbCopyA((STRSAFE_LPSTR)v6 + 376, 0x105u, MultiByteStr);
  }
  else
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_S(1025, 46, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, Src);
    *((_BYTE *)v6 + 376) = 0;
  }
  EnterCriticalSection(&SockSanProvListCritSec);
  v24 = (_QWORD *)qword_180064738;
  if ( *(PVOID **)qword_180064738 != &SockSanProviderList )
    __fastfail(3u);
  *v6 = &SockSanProviderList;
  v6[1] = v24;
  *v24 = v6;
  qword_180064738 = (__int64)v6;
  LeaveCriticalSection(&SockSanProvListCritSec);
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_S(1025, 47, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1 + 116);
  SanTelemeterProviderLoad(v6);
  return 0;
}

```

## disassembly

```asm
0x180043534  push    rbp
0x180043536  push    rbx
0x180043537  push    rsi
0x180043538  push    rdi
0x180043539  push    r12
0x18004353b  push    r13
0x18004353d  push    r14
0x18004353f  push    r15
0x180043541  lea     rbp, [rsp-6F8h]
0x180043549  sub     rsp, 7F8h
0x180043550  mov     rax, cs:__security_cookie
0x180043557  xor     rax, rsp
0x18004355a  mov     [rbp+730h+var_50], rax
0x180043561  xor     r15d, r15d
0x180043564  mov     dword ptr [rsp+830h+Data], 5
0x18004356c  test    dword ptr [rcx], 80000h
0x180043572  xorps   xmm0, xmm0
0x180043575  mov     r14, rcx
0x180043578  mov     [rsp+830h+var_7D0], r15d
0x18004357d  mov     [rsp+830h+var_7CC], r15d
0x180043582  movups  xmmword ptr [rbp+730h+GuidString.Length], xmm0
0x180043586  mov     dword ptr [rsp+830h+var_7C0], 6
0x18004358e  mov     [rsp+830h+Type], 4
0x180043596  mov     [rsp+830h+cbData], r15d
0x18004359b  mov     [rbp+730h+hKey], r15
0x18004359f  jz      short loc_1800435AB
0x1800435a1  mov     eax, 0C00000BBh
0x1800435a6  jmp     loc_18004405B
0x1800435ab  mov     rax, cs:SockUpcallTable
0x1800435b2  lea     r9, [rsp+830h+var_7D0]
0x1800435b7  add     rcx, 14h
0x1800435bb  mov     [rbp+730h+var_7A8], 105h
0x1800435c2  lea     r8, [rbp+730h+var_7A8]
0x1800435c6  lea     rdx, [rbp+730h+Src]
0x1800435cd  mov     rax, [rax+28h]
0x1800435d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435d6  cmp     eax, 0FFFFFFFFh
0x1800435d9  jnz     short loc_18004361E
0x1800435db  test    byte ptr cs:xmmword_180063D60, 2
0x1800435e2  jz      short loc_1800435FF
0x1800435e4  lea     edx, [rax+24h]
0x1800435e7  mov     eax, [rsp+830h+var_7D0]
0x1800435eb  lea     r9, [r14+74h]
0x1800435ef  mov     dword ptr [rsp+830h+phkResult], eax
0x1800435f3  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800435fa  call    WPP_SF_Sd
0x1800435ff  mov     edi, 8
0x180043604  cmp     [rsp+830h+var_7D0], edi
0x180043608  jz      short loc_180043680
0x18004360a  cmp     [rsp+830h+var_7D0], 2747h
0x180043612  jz      short loc_180043680
0x180043614  mov     eax, 0C0000001h
0x180043619  jmp     loc_18004405B
0x18004361e  mov     r8d, 105h; nSize
0x180043624  lea     rdx, [rbp+730h+Dst]; lpDst
0x18004362b  lea     rcx, [rbp+730h+Src]; lpSrc
0x180043632  call    cs:__imp_ExpandEnvironmentStringsW
0x180043639  nop     dword ptr [rax+rax+00h]
0x18004363e  mov     rcx, cs:SockPrivateHeap
0x180043645  mov     edi, 280h
0x18004364a  mov     rax, cs:SockAllocateHeapRoutine
0x180043651  mov     r8d, edi
0x180043654  xor     edx, edx
0x180043656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004365b  mov     rbx, rax
0x18004365e  test    rax, rax
0x180043661  jnz     short loc_18004368A
0x180043663  test    byte ptr cs:xmmword_180063D60, 2
0x18004366a  jz      short loc_180043680
0x18004366c  lea     edx, [rax+24h]
0x18004366f  mov     ecx, 401h
0x180043674  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18004367b  call    WPP_SF_
0x180043680  mov     eax, 0C0000017h
0x180043685  jmp     loc_18004405B
0x18004368a  mov     r8, rdi; Size
0x18004368d  xor     edx, edx; Val
0x18004368f  mov     rcx, rbx; void *
0x180043692  call    memset_0
0x180043697  xor     r8d, r8d; dwFlags
0x18004369a  lea     rcx, [rbp+730h+Dst]; lpLibFileName
0x1800436a1  xor     edx, edx; hFile
0x1800436a3  call    cs:__imp_LoadLibraryExW
0x1800436aa  nop     dword ptr [rax+rax+00h]
0x1800436af  mov     [rbx+20h], rax
0x1800436b3  mov     rdi, rax
0x1800436b6  test    rax, rax
0x1800436b9  jz      loc_18004403C
0x1800436bf  xor     edx, edx; Val
0x1800436c1  lea     rcx, [rbp+730h+var_790]; void *
0x1800436c5  mov     r8d, 204h; Size
0x1800436cb  call    memset_0
0x1800436d0  lea     rdx, aWspstartupex; "WSPStartupEx"
0x1800436d7  mov     rcx, rdi; hModule
0x1800436da  call    cs:__imp_GetProcAddress
0x1800436e1  nop     dword ptr [rax+rax+00h]
0x1800436e6  mov     rdi, rax
0x1800436e9  test    rax, rax
0x1800436ec  jz      loc_180043FC6
0x1800436f2  lea     r15, [rbx+40h]
0x1800436f6  xor     edx, edx; Val
0x1800436f8  mov     rcx, r15; void *
0x1800436fb  mov     r8d, 0F0h; Size
0x180043701  call    memset_0
0x180043706  lea     rsi, [rbx+130h]
0x18004370d  mov     [rsp+830h+phkResult], r15
0x180043712  xorps   xmm0, xmm0
0x180043715  lea     r9, SockUpcallTable2
0x18004371c  movups  xmmword ptr [rsi], xmm0
0x18004371f  xor     eax, eax
0x180043721  mov     ecx, 202h
0x180043726  movups  xmmword ptr [rsi+10h], xmm0
0x18004372a  lea     rdx, [rbp+730h+var_790]
0x18004372e  movups  xmmword ptr [rsi+20h], xmm0
0x180043732  mov     [rsi+30h], rax
0x180043736  lea     r8, SockTcpProviderInfo
0x18004373d  cmp     dword ptr [r14+4Ch], 17h
0x180043742  mov     rax, rdi
0x180043745  jnz     short loc_18004374E
0x180043747  lea     r8, SockTcp6ProviderInfo
0x18004374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043753  xor     r12d, r12d
0x180043756  mov     [rsp+830h+var_7D0], eax
0x18004375a  test    eax, eax
0x18004375c  jnz     loc_180043F9A
0x180043762  lea     rax, [rsp+830h+var_7D0]
0x180043767  mov     edx, 0C8000006h
0x18004376c  mov     [rsp+830h+var_7E0], rax
0x180043771  lea     edi, [r12+8]
0x180043776  mov     [rsp+830h+var_7E8], r12
0x18004377b  lea     rax, [rsp+830h+var_7CC]
0x180043780  mov     [rsp+830h+var_7F0], r12
0x180043785  lea     r9d, [r12+10h]
0x18004378a  mov     [rsp+830h+lpUsedDefaultChar], r12
0x18004378f  lea     r8, SockpWSPRegisterMemoryGuid
0x180043796  mov     [rsp+830h+lpDefaultChar], rax
0x18004379b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004379f  mov     rax, [rbx+0C0h]
0x1800437a6  mov     dword ptr [rsp+830h+lpcbData], edi
0x1800437aa  mov     [rsp+830h+phkResult], rsi
0x1800437af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800437b4  cmp     eax, 0FFFFFFFFh
0x1800437b7  jnz     short loc_1800437BC
0x1800437b9  mov     [rsi], r12
0x1800437bc  lea     rax, [rsp+830h+var_7D0]
0x1800437c1  mov     r9d, 10h
0x1800437c7  mov     [rsp+830h+var_7E0], rax
0x1800437cc  lea     r13, [rbx+138h]
0x1800437d3  mov     [rsp+830h+var_7E8], r12
0x1800437d8  lea     rax, [rsp+830h+var_7CC]
0x1800437dd  mov     [rsp+830h+var_7F0], r12
0x1800437e2  lea     r8, SockpWSPDeregisterMemoryGuid
0x1800437e9  mov     [rsp+830h+lpUsedDefaultChar], r12
0x1800437ee  mov     edx, 0C8000006h
0x1800437f3  mov     [rsp+830h+lpDefaultChar], rax
0x1800437f8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800437fc  mov     rax, [rbx+0C0h]
0x180043803  mov     dword ptr [rsp+830h+lpcbData], edi
0x180043807  mov     [rsp+830h+phkResult], r13
0x18004380c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043811  cmp     eax, 0FFFFFFFFh
0x180043814  jnz     short loc_18004381A
0x180043816  mov     [r13+0], r12
0x18004381a  lea     rax, [rsp+830h+var_7D0]
0x18004381f  mov     r9d, 10h
0x180043825  mov     [rsp+830h+var_7E0], rax
0x18004382a  lea     r12, [rbx+140h]
0x180043831  xor     eax, eax
0x180043833  lea     r8, SockpWSPRegisterRdmaMemoryGuid
0x18004383a  mov     [rsp+830h+var_7E8], rax
0x18004383f  mov     edx, 0C8000006h
0x180043844  mov     [rsp+830h+var_7F0], rax
0x180043849  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004384d  mov     [rsp+830h+lpUsedDefaultChar], rax
0x180043852  lea     rax, [rsp+830h+var_7CC]
0x180043857  mov     [rsp+830h+lpDefaultChar], rax
0x18004385c  mov     rax, [rbx+0C0h]
0x180043863  mov     dword ptr [rsp+830h+lpcbData], edi
0x180043867  mov     [rsp+830h+phkResult], r12
0x18004386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043871  cmp     eax, 0FFFFFFFFh
0x180043874  jnz     short loc_18004387E
0x180043876  mov     qword ptr [r12], 0
0x18004387e  lea     rax, [rsp+830h+var_7D0]
0x180043883  mov     r9d, 10h
0x180043889  mov     [rsp+830h+var_7E0], rax
0x18004388e  lea     r12, [rbx+148h]
0x180043895  xor     eax, eax
0x180043897  lea     r8, SockpWSPDeregisterRdmaMemoryGuid
0x18004389e  mov     [rsp+830h+var_7E8], rax
0x1800438a3  mov     edx, 0C8000006h
0x1800438a8  mov     [rsp+830h+var_7F0], rax
0x1800438ad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800438b1  mov     [rsp+830h+lpUsedDefaultChar], rax
0x1800438b6  lea     rax, [rsp+830h+var_7CC]
0x1800438bb  mov     [rsp+830h+lpDefaultChar], rax
0x1800438c0  mov     rax, [rbx+0C0h]
0x1800438c7  mov     dword ptr [rsp+830h+lpcbData], edi
0x1800438cb  mov     [rsp+830h+phkResult], r12
0x1800438d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800438d5  cmp     eax, 0FFFFFFFFh
0x1800438d8  jnz     short loc_1800438E2
0x1800438da  mov     qword ptr [r12], 0
0x1800438e2  lea     rax, [rsp+830h+var_7D0]
0x1800438e7  mov     r9d, 10h
0x1800438ed  mov     [rsp+830h+var_7E0], rax
0x1800438f2  lea     r12, [rbx+150h]
0x1800438f9  xor     eax, eax
0x1800438fb  lea     r8, SockpWSPRdmaWriteGuid
0x180043902  mov     [rsp+830h+var_7E8], rax
0x180043907  mov     edx, 0C8000006h
0x18004390c  mov     [rsp+830h+var_7F0], rax
0x180043911  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043915  mov     [rsp+830h+lpUsedDefaultChar], rax
0x18004391a  lea     rax, [rsp+830h+var_7CC]
0x18004391f  mov     [rsp+830h+lpDefaultChar], rax
0x180043924  mov     rax, [rbx+0C0h]
0x18004392b  mov     dword ptr [rsp+830h+lpcbData], edi
0x18004392f  mov     [rsp+830h+phkResult], r12
0x180043934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043939  cmp     eax, 0FFFFFFFFh
0x18004393c  jnz     short loc_180043946
0x18004393e  mov     qword ptr [r12], 0
0x180043946  lea     rcx, [rsp+830h+var_7D0]
0x18004394b  mov     r9d, 10h
0x180043951  mov     [rsp+830h+var_7E0], rcx
0x180043956  lea     rax, [rbx+158h]
0x18004395d  xor     ecx, ecx
0x18004395f  lea     r8, SockpWSPRdmaReadGuid
0x180043966  mov     [rsp+830h+var_7E8], rcx
0x18004396b  mov     edx, 0C8000006h
0x180043970  mov     [rsp+830h+var_7F0], rcx
0x180043975  mov     [rsp+830h+lpUsedDefaultChar], rcx
0x18004397a  lea     rcx, [rsp+830h+var_7CC]
0x18004397f  mov     [rsp+830h+lpDefaultChar], rcx
0x180043984  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043988  mov     dword ptr [rsp+830h+lpcbData], edi
0x18004398c  mov     [rsp+830h+phkResult], rax
0x180043991  mov     rax, [rbx+0C0h]
0x180043998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004399d  cmp     eax, 0FFFFFFFFh
0x1800439a0  jnz     short loc_1800439AD
0x1800439a2  mov     qword ptr [rbx+158h], 0
0x1800439ad  lea     rcx, [rsp+830h+var_7D0]
0x1800439b2  mov     r9d, 10h
0x1800439b8  mov     [rsp+830h+var_7E0], rcx
0x1800439bd  lea     rax, [rbx+160h]
0x1800439c4  xor     ecx, ecx
0x1800439c6  lea     r8, SockpWSPMemoryRegistrationCacheCallbackGuid
0x1800439cd  mov     [rsp+830h+var_7E8], rcx
0x1800439d2  mov     edx, 0C8000006h
0x1800439d7  mov     [rsp+830h+var_7F0], rcx
0x1800439dc  mov     [rsp+830h+lpUsedDefaultChar], rcx
0x1800439e1  lea     rcx, [rsp+830h+var_7CC]
0x1800439e6  mov     [rsp+830h+lpDefaultChar], rcx
0x1800439eb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800439ef  mov     dword ptr [rsp+830h+lpcbData], edi
0x1800439f3  mov     [rsp+830h+phkResult], rax
0x1800439f8  mov     rax, [rbx+0C0h]
0x1800439ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a04  cmp     eax, 0FFFFFFFFh
0x180043a07  jnz     short loc_180043A14
0x180043a09  mov     qword ptr [rbx+160h], 0
0x180043a14  cmp     qword ptr [r15], 0
0x180043a18  lea     rdi, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x180043a1f  jz      loc_180043F35
0x180043a25  xor     r15d, r15d
0x180043a28  cmp     [rbx+58h], r15
0x180043a2c  jz      loc_180043F38
0x180043a32  cmp     [rbx+68h], r15
0x180043a36  jz      loc_180043F38
0x180043a3c  cmp     [rbx+70h], r15
0x180043a40  jz      loc_180043F38
0x180043a46  cmp     [rbx+78h], r15
0x180043a4a  jz      loc_180043F38
0x180043a50  cmp     [rbx+80h], r15
0x180043a57  jz      loc_180043F38
0x180043a5d  cmp     [rbx+88h], r15
0x180043a64  jz      loc_180043F38
0x180043a6a  cmp     [rbx+90h], r15
0x180043a71  jz      loc_180043F38
0x180043a77  cmp     [rbx+98h], r15
0x180043a7e  jz      loc_180043F38
0x180043a84  cmp     [rbx+0B0h], r15
0x180043a8b  jz      loc_180043F38
0x180043a91  cmp     [rbx+0C0h], r15
0x180043a98  jz      loc_180043F38
0x180043a9e  cmp     [rbx+0D0h], r15
0x180043aa5  jz      loc_180043F38
0x180043aab  cmp     [rbx+0D8h], r15
0x180043ab2  jz      loc_180043F38
0x180043ab8  cmp     [rbx+0F8h], r15
0x180043abf  jz      loc_180043F38
0x180043ac5  cmp     [rbx+110h], r15
0x180043acc  jz      loc_180043F38
0x180043ad2  cmp     [rbx+120h], r15
0x180043ad9  jz      loc_180043F38
0x180043adf  cmp     [rsi], r15
0x180043ae2  jz      loc_180043F38
0x180043ae8  cmp     [r13+0], r15
  ... truncated ...
```
