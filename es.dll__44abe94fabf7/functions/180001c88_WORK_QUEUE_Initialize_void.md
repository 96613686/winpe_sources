# WORK_QUEUE::Initialize(void)

- ea: `0x180001c88`
- end: `0x180001e3d`
- name: `?Initialize@WORK_QUEUE@@QEAAHXZ`
- size: `437`
- prototype: `__int64 __fastcall(WORK_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800029d8`

## callees

- `0x180001c88`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180001cff`
- `ntdll!RtlDeleteCriticalSection` at `0x180001d08`
- `ntdll!RtlDeleteCriticalSection` at `0x180001cff`
- `ntdll!RtlDeleteCriticalSection` at `0x180001d08`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180001cb1`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180001cca`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180001cb1`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180001cca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180001e0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180001e0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001d93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001d58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001dea`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180001ce5`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180001ce5`

## string_xrefs

- `0x180001d34`: `Software\Microsoft\COM3\MTAThreadPool`
- `0x180001d8c`: `MaxThreadsPerCPU`

## pseudocode

```c
__int64 __fastcall WORK_QUEUE::Initialize(WORK_QUEUE *this)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  HANDLE IoCompletionPort; // rax
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+38h] [rbp-40h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+30h] BYREF
  int Data; // [rsp+B0h] [rbp+38h] BYREF
  unsigned int v11; // [rsp+B8h] [rbp+40h] BYREF

  if ( !*((_QWORD *)this + 2) )
    return 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  if ( !RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 104), 0x80000FA0) )
  {
    if ( RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 144), 0x80000FA0) )
    {
      v4 = v3;
LABEL_9:
      RtlDeleteCriticalSection(v4);
      goto LABEL_10;
    }
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    *(_QWORD *)this = IoCompletionPort;
    if ( !IoCompletionPort )
    {
      RtlDeleteCriticalSection(v3);
      v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
      goto LABEL_9;
    }
    *((_DWORD *)this + 7) = 1;
  }
LABEL_10:
  WORK_QUEUE::sm_dwMTAThreadPoolMaxSize = 0;
  WORK_QUEUE::sm_dwMTAThreadPoolThrottle = 0;
  hKey = 0;
  Data = 0;
  v11 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\MTAThreadPool", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    Type = 4;
    if ( RegQueryValueExW(hKey, L"MaxThreadsPerCPU", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
      Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Throttle", 0, &Type, (LPBYTE)&v11, &cbData) || Type != 4 )
      v11 = 0;
    RegCloseKey(hKey);
  }
  if ( !WORK_QUEUE::sm_dwMTAThreadPoolMaxSize )
  {
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    WORK_QUEUE::sm_dwMTAThreadPoolMaxSize = Data * SystemInfo.dwNumberOfProcessors;
  }
  if ( !WORK_QUEUE::sm_dwMTAThreadPoolThrottle )
    WORK_QUEUE::sm_dwMTAThreadPoolThrottle = v11;
  return *((unsigned int *)this + 7);
}

```

## disassembly

```asm
0x180001c88  push    rbp
0x180001c8a  push    rbx
0x180001c8b  push    rsi
0x180001c8c  push    rdi
0x180001c8d  mov     rbp, rsp
0x180001c90  sub     rsp, 78h
0x180001c94  cmp     qword ptr [rcx+10h], 0
0x180001c99  mov     rbx, rcx
0x180001c9c  jnz     short loc_180001CA5
0x180001c9e  xor     eax, eax
0x180001ca0  jmp     loc_180001E34
0x180001ca5  lea     rdi, [rcx+68h]
0x180001ca9  mov     edx, 80000FA0h; SpinCount
0x180001cae  mov     rcx, rdi; CriticalSection
0x180001cb1  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180001cb7  test    eax, eax
0x180001cb9  jnz     short loc_180001D0E
0x180001cbb  lea     rsi, [rbx+90h]
0x180001cc2  mov     edx, 80000FA0h; SpinCount
0x180001cc7  mov     rcx, rsi; CriticalSection
0x180001cca  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180001cd0  test    eax, eax
0x180001cd2  jz      short loc_180001CD9
0x180001cd4  mov     rcx, rdi
0x180001cd7  jmp     short loc_180001D08
0x180001cd9  xor     r9d, r9d; NumberOfConcurrentThreads
0x180001cdc  xor     r8d, r8d; CompletionKey
0x180001cdf  xor     edx, edx; ExistingCompletionPort
0x180001ce1  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180001ce5  call    cs:__imp_CreateIoCompletionPort
0x180001ceb  mov     [rbx], rax
0x180001cee  test    rax, rax
0x180001cf1  jz      short loc_180001CFC
0x180001cf3  mov     dword ptr [rbx+1Ch], 1
0x180001cfa  jmp     short loc_180001D0E
0x180001cfc  mov     rcx, rdi; CriticalSection
0x180001cff  call    cs:__imp_RtlDeleteCriticalSection
0x180001d05  mov     rcx, rsi; CriticalSection
0x180001d08  call    cs:__imp_RtlDeleteCriticalSection
0x180001d0e  lea     rax, [rbp+hKey]
0x180001d12  mov     cs:?sm_dwMTAThreadPoolMaxSize@WORK_QUEUE@@0KA, 0; ulong WORK_QUEUE::sm_dwMTAThreadPoolMaxSize
0x180001d1c  mov     r9d, 20019h; samDesired
0x180001d22  mov     [rsp+78h+phkResult], rax; phkResult
0x180001d27  xor     r8d, r8d; ulOptions
0x180001d2a  mov     cs:?sm_dwMTAThreadPoolThrottle@WORK_QUEUE@@0KA, 0; ulong WORK_QUEUE::sm_dwMTAThreadPoolThrottle
0x180001d34  lea     rdx, SubKey; "Software\\Microsoft\\COM3\\MTAThreadPoo"...
0x180001d3b  mov     [rbp+hKey], 0
0x180001d43  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001d4a  mov     [rbp+Data], 0
0x180001d51  mov     [rbp+arg_18], 0
0x180001d58  call    cs:__imp_RegOpenKeyExW
0x180001d5e  test    eax, eax
0x180001d60  jnz     loc_180001DF0
0x180001d66  mov     rcx, [rbp+hKey]; hKey
0x180001d6a  lea     edi, [rax+4]
0x180001d6d  lea     rax, [rbp+cbData]
0x180001d71  mov     [rbp+cbData], edi
0x180001d74  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180001d79  lea     r9, [rbp+Type]; lpType
0x180001d7d  lea     rax, [rbp+Data]
0x180001d81  mov     [rbp+Type], edi
0x180001d84  xor     r8d, r8d; lpReserved
0x180001d87  mov     [rsp+78h+phkResult], rax; lpData
0x180001d8c  lea     rdx, ValueName; "MaxThreadsPerCPU"
0x180001d93  call    cs:__imp_RegQueryValueExW
0x180001d99  test    eax, eax
0x180001d9b  jnz     short loc_180001DA2
0x180001d9d  cmp     [rbp+Type], edi
0x180001da0  jz      short loc_180001DA9
0x180001da2  mov     [rbp+Data], 0
0x180001da9  mov     rcx, [rbp+hKey]; hKey
0x180001dad  lea     rax, [rbp+cbData]
0x180001db1  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180001db6  lea     r9, [rbp+Type]; lpType
0x180001dba  lea     rax, [rbp+arg_18]
0x180001dbe  mov     [rbp+cbData], edi
0x180001dc1  xor     r8d, r8d; lpReserved
0x180001dc4  mov     [rsp+78h+phkResult], rax; lpData
0x180001dc9  lea     rdx, aThrottle; "Throttle"
0x180001dd0  call    cs:__imp_RegQueryValueExW
0x180001dd6  test    eax, eax
0x180001dd8  jnz     short loc_180001DDF
0x180001dda  cmp     [rbp+Type], edi
0x180001ddd  jz      short loc_180001DE6
0x180001ddf  mov     [rbp+arg_18], 0
0x180001de6  mov     rcx, [rbp+hKey]; hKey
0x180001dea  call    cs:__imp_RegCloseKey
0x180001df0  cmp     cs:?sm_dwMTAThreadPoolMaxSize@WORK_QUEUE@@0KA, 0; ulong WORK_QUEUE::sm_dwMTAThreadPoolMaxSize
0x180001df7  jnz     short loc_180001E1F
0x180001df9  xorps   xmm0, xmm0
0x180001dfc  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180001e00  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180001e04  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180001e08  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180001e0c  call    cs:__imp_GetSystemInfo
0x180001e12  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180001e15  imul    eax, [rbp+Data]
0x180001e19  mov     cs:?sm_dwMTAThreadPoolMaxSize@WORK_QUEUE@@0KA, eax; ulong WORK_QUEUE::sm_dwMTAThreadPoolMaxSize
0x180001e1f  cmp     cs:?sm_dwMTAThreadPoolThrottle@WORK_QUEUE@@0KA, 0; ulong WORK_QUEUE::sm_dwMTAThreadPoolThrottle
0x180001e26  jnz     short loc_180001E31
0x180001e28  mov     eax, [rbp+arg_18]
0x180001e2b  mov     cs:?sm_dwMTAThreadPoolThrottle@WORK_QUEUE@@0KA, eax; ulong WORK_QUEUE::sm_dwMTAThreadPoolThrottle
0x180001e31  mov     eax, [rbx+1Ch]
0x180001e34  add     rsp, 78h
0x180001e38  pop     rdi
0x180001e39  pop     rsi
0x180001e3a  pop     rbx
0x180001e3b  pop     rbp
0x180001e3c  retn
```
