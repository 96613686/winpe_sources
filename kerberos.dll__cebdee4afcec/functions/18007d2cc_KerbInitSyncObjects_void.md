# KerbInitSyncObjects(void)

- ea: `0x18007d2cc`
- end: `0x18007d3b2`
- name: `?KerbInitSyncObjects@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800802c0`

## callees

- `0x18007d2cc`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d318`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007d318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d32a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d397`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007d397`
- `ntdll!RtlInitializeResource` at `0x18007d35d`
- `ntdll!RtlInitializeResource` at `0x18007d35d`
- `ntdll!RtlDeleteCriticalSection` at `0x18007d3a4`
- `ntdll!RtlDeleteCriticalSection` at `0x18007d3a4`
- `ntdll!RtlInitializeCriticalSection` at `0x18007d2d9`
- `ntdll!RtlInitializeCriticalSection` at `0x18007d2d9`

## string_xrefs

- `0x18007d336`: `CreateEventW failed: %#x\n`

## pseudocode

```c
__int64 KerbInitSyncObjects(void)
{
  NTSTATUS v0; // eax
  DWORD LastError; // ebx

  v0 = RtlInitializeCriticalSection(&KerbGlobalKerbKdcCallLock);
  LastError = v0;
  if ( v0 >= 0 )
  {
    KerbGlobalKerbKdcCallEvent = CreateEventW(0, 1, 1, 0);
    if ( KerbGlobalKerbKdcCallEvent )
    {
      RtlInitializeResource(&KerbGlobalS4U2ProxyCacheLock);
      return 0;
    }
    LastError = GetLastError();
    KerbTracerT::Log(1, "KerbInitSyncObjects", 1747, "CreateEventW failed: %#x\n", LastError);
    RtlDeleteCriticalSection(&KerbGlobalKerbKdcCallLock);
  }
  else
  {
    KerbTracerT::Log(1, "KerbInitSyncObjects", 1733, "RtlInitializeCriticalSection failed: %#x\n", v0);
  }
  return LastError;
}

```

## disassembly

```asm
0x18007d2cc  push    rbx
0x18007d2ce  sub     rsp, 30h
0x18007d2d2  lea     rcx, ?KerbGlobalKerbKdcCallLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007d2d9  call    cs:__imp_RtlInitializeCriticalSection
0x18007d2df  mov     ebx, eax
0x18007d2e1  test    eax, eax
0x18007d2e3  jns     short loc_18007D30C
0x18007d2e5  mov     [rsp+38h+var_18], eax
0x18007d2e9  lea     r9, aRtlinitializec; "RtlInitializeCriticalSection failed: %#"...
0x18007d2f0  mov     r8d, 6C5h
0x18007d2f6  lea     rdx, aKerbinitsyncob; "KerbInitSyncObjects"
0x18007d2fd  mov     ecx, 1
0x18007d302  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d307  jmp     loc_18007D3AA
0x18007d30c  xor     r9d, r9d; lpName
0x18007d30f  lea     edx, [r9+1]; bManualReset
0x18007d313  xor     ecx, ecx; lpEventAttributes
0x18007d315  mov     r8d, edx; bInitialState
0x18007d318  call    cs:__imp_CreateEventW
0x18007d31e  mov     cs:?KerbGlobalKerbKdcCallEvent@@3PEAXEA, rax; void * KerbGlobalKerbKdcCallEvent
0x18007d325  test    rax, rax
0x18007d328  jnz     short loc_18007D356
0x18007d32a  call    cs:__imp_GetLastError
0x18007d330  mov     ebx, eax
0x18007d332  mov     [rsp+38h+var_18], eax
0x18007d336  lea     r9, aCreateeventwFa; "CreateEventW failed: %#x\n"
0x18007d33d  mov     r8d, 6D3h
0x18007d343  lea     rdx, aKerbinitsyncob; "KerbInitSyncObjects"
0x18007d34a  mov     ecx, 1
0x18007d34f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d354  jmp     short loc_18007D39D
0x18007d356  lea     rcx, ?KerbGlobalS4U2ProxyCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18007d35d  call    cs:__imp_RtlInitializeResource
0x18007d363  nop
0x18007d364  xor     eax, eax
0x18007d366  jmp     short loc_18007D3AC
0x18007d368  mov     ebx, 0C000009Ah
0x18007d36d  mov     [rsp+38h+var_18], ebx
0x18007d371  lea     r9, aRtlinitializer; "RtlInitializeResource failed: %#x\n"
0x18007d378  mov     r8d, 6DEh
0x18007d37e  lea     rdx, aKerbinitsyncob; "KerbInitSyncObjects"
0x18007d385  mov     ecx, 1
0x18007d38a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18007d38f  nop
0x18007d390  mov     rcx, cs:?KerbGlobalKerbKdcCallEvent@@3PEAXEA; hObject
0x18007d397  call    cs:__imp_CloseHandle
0x18007d39d  lea     rcx, ?KerbGlobalKerbKdcCallLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007d3a4  call    cs:__imp_RtlDeleteCriticalSection
0x18007d3aa  mov     eax, ebx
0x18007d3ac  add     rsp, 30h
0x18007d3b0  pop     rbx
0x18007d3b1  retn
```
