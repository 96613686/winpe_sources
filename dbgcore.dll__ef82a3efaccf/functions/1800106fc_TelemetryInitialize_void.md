# TelemetryInitialize(void)

- ea: `0x1800106fc`
- end: `0x18001096c`
- name: `?TelemetryInitialize@@YAXXZ`
- size: `624`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800100f0`

## callees

- `0x180001710`
- `0x1800021ac`
- `0x1800021b8`
- `0x1800106fc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800107d8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800107d8`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800107c8`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800107c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001072f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001072f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010948`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001085c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001085c`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800107b1`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800107b1`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180010768`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x180010768`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001079c`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001079c`
- `api-ms-win-core-sysinfo-l1-1-0!SystemTimeToFileTime` at `0x18001083a`
- `api-ms-win-core-sysinfo-l1-1-0!SystemTimeToFileTime` at `0x18001083a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001082c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001082c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010849`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010849`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800108fd`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800108fd`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001092e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001092e`

## string_xrefs

- `0x1800107c1`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void TelemetryInitialize(void)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  ULONGLONG v2; // rbx
  DWORD CurrentProcessId; // eax
  int v4; // eax
  signed int v5; // eax
  bool v6; // sf
  BYTE Data[8]; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+48h] [rbp-28h]
  _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  v10 = -2;
  AcquireSRWLockExclusive(&g_telemetry_lock);
  *(_QWORD *)&SystemTime.wYear = &g_telemetry_lock;
  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\SqmClient", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"MSFTInternal", 0, 0, Data, &cbData) )
      *(_DWORD *)Data = 0;
    RegCloseKey(hKey);
  }
  if ( *(_DWORD *)Data )
    goto LABEL_15;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetDeviceFamilyInfoEnum");
  if ( ProcAddress )
  {
    *(_DWORD *)Data = 0;
    ((void (__fastcall *)(_QWORD, BYTE *, _QWORD))ProcAddress)(0, Data, 0);
    if ( *(_DWORD *)Data == 5 || (unsigned int)(*(_DWORD *)Data - 11) <= 1 )
      goto LABEL_15;
  }
  if ( !g_seedSet )
  {
    SystemTime = 0;
    hKey = 0;
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, (LPFILETIME)&hKey) )
      LODWORD(v2) = (_DWORD)hKey;
    else
      v2 = GetTickCount64() % 0xFFFFFFFF;
    CurrentProcessId = GetCurrentProcessId();
    o_srand_0((unsigned int)v2 + CurrentProcessId);
    g_seedSet = 1;
  }
  v4 = o_rand_0();
  if ( v4 == 100 * (v4 / 100) )
  {
LABEL_15:
    if ( g_refCount )
    {
      ++g_refCount;
      goto LABEL_26;
    }
    SystemTime = (_SYSTEMTIME)*((_OWORD *)off_18003C008 - 1);
    if ( RegHandle )
      __fastfail(5u);
    xmmword_18003C028 = 0;
    v5 = EventRegister((LPCGUID)&SystemTime, tlgEnableCallback, &dword_18003C000, &RegHandle);
    v6 = v5 < 0;
    if ( !v5 )
    {
      EventSetInformation(RegHandle, 2, off_18003C008, (unsigned __int16)*off_18003C008);
LABEL_25:
      ++g_refCount;
      g_telemetryEnabled = 1;
      goto LABEL_26;
    }
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
      goto LABEL_25;
  }
LABEL_26:
  ReleaseSRWLockExclusive(&g_telemetry_lock);
}

```

## disassembly

```asm
0x1800106fc  mov     rax, rsp
0x1800106ff  push    rbp
0x180010700  mov     rbp, rsp
0x180010703  sub     rsp, 70h
0x180010707  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x18001070f  mov     [rax+8], rbx
0x180010713  mov     [rax+10h], rsi
0x180010717  mov     rax, cs:__security_cookie
0x18001071e  xor     rax, rsp
0x180010721  mov     [rbp+var_10], rax
0x180010725  lea     rsi, ?g_telemetry_lock@@3Vsrwlock@wil@@A; wil::srwlock g_telemetry_lock
0x18001072c  mov     rcx, rsi; SRWLock
0x18001072f  call    cs:__imp_AcquireSRWLockExclusive
0x180010735  mov     qword ptr [rbp+SystemTime.wYear], rsi
0x180010739  mov     [rbp+hKey], 0
0x180010741  mov     dword ptr [rbp+Data], 0
0x180010748  lea     rax, [rbp+hKey]
0x18001074c  mov     [rsp+70h+phkResult], rax; phkResult
0x180010751  mov     r9d, 20019h; samDesired
0x180010757  xor     r8d, r8d; ulOptions
0x18001075a  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\SqmClien"...
0x180010761  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010768  call    cs:__imp_RegOpenKeyExW
0x18001076e  test    eax, eax
0x180010770  jnz     short loc_1800107B7
0x180010772  mov     [rbp+cbData], 4
0x180010779  lea     rax, [rbp+cbData]
0x18001077d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180010782  lea     rax, [rbp+Data]
0x180010786  mov     [rsp+70h+phkResult], rax; lpData
0x18001078b  xor     r9d, r9d; lpType
0x18001078e  xor     r8d, r8d; lpReserved
0x180010791  lea     rdx, ValueName; "MSFTInternal"
0x180010798  mov     rcx, [rbp+hKey]; hKey
0x18001079c  call    cs:__imp_RegQueryValueExW
0x1800107a2  test    eax, eax
0x1800107a4  jz      short loc_1800107AD
0x1800107a6  mov     dword ptr [rbp+Data], 0
0x1800107ad  mov     rcx, [rbp+hKey]; hKey
0x1800107b1  call    cs:__imp_RegCloseKey
0x1800107b7  cmp     dword ptr [rbp+Data], 0
0x1800107bb  jnz     loc_18001089D
0x1800107c1  lea     rcx, ModuleName; "ntdll.dll"
0x1800107c8  call    cs:__imp_GetModuleHandleW
0x1800107ce  mov     rcx, rax; hModule
0x1800107d1  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x1800107d8  call    cs:__imp_GetProcAddress
0x1800107de  test    rax, rax
0x1800107e1  jz      short loc_180010810
0x1800107e3  mov     dword ptr [rbp+Data], 0
0x1800107ea  xor     r8d, r8d
0x1800107ed  lea     rdx, [rbp+Data]
0x1800107f1  xor     ecx, ecx
0x1800107f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f8  mov     eax, dword ptr [rbp+Data]
0x1800107fb  cmp     eax, 5
0x1800107fe  jz      loc_18001089D
0x180010804  add     eax, 0FFFFFFF5h
0x180010807  cmp     eax, 1
0x18001080a  jbe     loc_18001089D
0x180010810  cmp     cs:?g_seedSet@@3HA, 0; int g_seedSet
0x180010817  jnz     short loc_180010874
0x180010819  xorps   xmm0, xmm0
0x18001081c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180010820  mov     [rbp+hKey], 0
0x180010828  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18001082c  call    cs:__imp_GetSystemTime
0x180010832  lea     rdx, [rbp+hKey]; lpFileTime
0x180010836  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18001083a  call    cs:__imp_SystemTimeToFileTime
0x180010840  test    eax, eax
0x180010842  jz      short loc_180010849
0x180010844  mov     ebx, dword ptr [rbp+hKey]
0x180010847  jmp     short loc_18001085C
0x180010849  call    cs:__imp_GetTickCount64
0x18001084f  xor     edx, edx
0x180010851  mov     ecx, 0FFFFFFFFh
0x180010856  div     rcx
0x180010859  mov     rbx, rdx
0x18001085c  call    cs:__imp_GetCurrentProcessId
0x180010862  lea     ecx, [rbx+rax]
0x180010865  call    _o_srand_0
0x18001086a  mov     cs:?g_seedSet@@3HA, 1; int g_seedSet
0x180010874  call    _o_rand_0
0x180010879  mov     r9d, eax
0x18001087c  mov     eax, 51EB851Fh
0x180010881  imul    r9d
0x180010884  sar     edx, 5
0x180010887  mov     r8d, edx
0x18001088a  shr     r8d, 1Fh
0x18001088e  add     edx, r8d
0x180010891  imul    edx, 64h ; 'd'
0x180010894  cmp     r9d, edx
0x180010897  jnz     loc_180010945
0x18001089d  mov     rax, cs:?g_refCount@@3_KA; unsigned __int64 g_refCount
0x1800108a4  test    rax, rax
0x1800108a7  jz      short loc_1800108B8
0x1800108a9  inc     rax
0x1800108ac  mov     cs:?g_refCount@@3_KA, rax; unsigned __int64 g_refCount
0x1800108b3  jmp     loc_180010945
0x1800108b8  mov     rax, cs:off_18003C008
0x1800108bf  movups  xmm0, xmmword ptr [rax-10h]
0x1800108c3  movdqu  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800108c8  cmp     cs:RegHandle, 0
0x1800108d0  jz      short loc_1800108D9
0x1800108d2  mov     ecx, 5
0x1800108d7  int     29h; Win8: RtlFailFast(ecx)
0x1800108d9  xorps   xmm0, xmm0
0x1800108dc  movdqu  cs:xmmword_18003C028, xmm0
0x1800108e4  lea     r9, RegHandle; RegHandle
0x1800108eb  lea     r8, dword_18003C000; CallbackContext
0x1800108f2  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800108f9  lea     rcx, [rbp+SystemTime]; ProviderId
0x1800108fd  call    cs:__imp_EventRegister
0x180010903  test    eax, eax
0x180010905  jz      short loc_180010917
0x180010907  jle     short loc_180010913
0x180010909  movzx   eax, ax
0x18001090c  or      eax, 80070000h
0x180010911  test    eax, eax
0x180010913  js      short loc_180010945
0x180010915  jmp     short loc_180010934
0x180010917  mov     r8, cs:off_18003C008
0x18001091e  movzx   r9d, word ptr [r8]
0x180010922  mov     edx, 2
0x180010927  mov     rcx, cs:RegHandle
0x18001092e  call    cs:__imp_EventSetInformation
0x180010934  inc     cs:?g_refCount@@3_KA; unsigned __int64 g_refCount
0x18001093b  mov     cs:?g_telemetryEnabled@@3HA, 1; int g_telemetryEnabled
0x180010945  mov     rcx, rsi; SRWLock
0x180010948  call    cs:__imp_ReleaseSRWLockExclusive
0x18001094e  mov     rcx, [rbp+var_10]
0x180010952  xor     rcx, rsp; StackCookie
0x180010955  call    __security_check_cookie
0x18001095a  lea     r11, [rsp+70h+var_s0]
0x18001095f  mov     rbx, [r11+10h]
0x180010963  mov     rsi, [r11+18h]
0x180010967  mov     rsp, r11
0x18001096a  pop     rbp
0x18001096b  retn
```
