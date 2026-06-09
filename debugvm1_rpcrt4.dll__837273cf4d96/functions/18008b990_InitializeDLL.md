# _InitializeDLL

- ea: `0x18008b990`
- end: `0x18008bacd`
- name: `_InitializeDLL`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008b950`

## callees

- `0x1800280b0`
- `0x18004ab8c`
- `0x18008b990`
- `0x18008bad4`
- `0x1800a1d2c`
- `0x1800a1fa0`
- `0x1800a260c`
- `0x1800b76cc`
- `0x1800c9934`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18008ba82`
- `ntdll!RtlDeleteCriticalSection` at `0x18008ba82`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008b9c1`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18008b9c1`
- `ntdll!RtlImageNtHeader` at `0x18008b9f2`
- `ntdll!RtlImageNtHeader` at `0x18008b9f2`
- `ntdll!EtwEventUnregister` at `0x18008bac2`
- `ntdll!EtwEventUnregister` at `0x18008bac2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008b9d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18008b9d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008baa6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008baa6`

## pseudocode

```c
char __fastcall InitializeDLL(__int64 a1, int a2, __int64 a3)
{
  int v4; // edx
  struct _PEB *v6; // rcx
  PIMAGE_NT_HEADERS v7; // rax
  __int64 v8; // rcx
  __int64 SizeOfStackCommit; // rdx
  unsigned int v10; // edx
  THREAD *ThreadPointer; // rcx

  if ( a2 )
  {
    v4 = a2 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        ThreadPointer = RpcpGetThreadPointer();
        NtCurrentTeb()->ReservedForNtRpc = 0;
        if ( ThreadPointer )
          THREAD::`scalar deleting destructor'(ThreadPointer, v10);
      }
    }
    else
    {
      TlgRegisterAggregateProviderEx();
      RtlInitializeCriticalSectionAndSpinCount(&GlobalMutex, 0);
      GlobalMutexInitialized = 1;
      InitializeCriticalSection(&NdrOle_CS);
      v6 = NtCurrentPeb();
      byte_1800F9EC4 = 1;
      v7 = RtlImageNtHeader(v6->ImageBaseAddress);
      SizeOfStackCommit = 1024;
      if ( v7->OptionalHeader.SizeOfStackCommit < 0x400 )
        SizeOfStackCommit = v7->OptionalHeader.SizeOfStackCommit;
      SafeAllocaInitialize(v8, SizeOfStackCommit);
    }
  }
  else
  {
    TlgUnregisterAggregateProvider();
    if ( !a3 )
    {
      RpcpExtFreeExtensions();
      if ( GlobalMutexInitialized == 1 )
      {
        RtlDeleteCriticalSection(&GlobalMutex);
        GlobalMutexInitialized = 0;
      }
      if ( byte_1800F9EC4 )
      {
        DeleteCriticalSection(&NdrOle_CS);
        byte_1800F9EC4 = 0;
      }
    }
    if ( g_SqmEnabled )
      UploadAllSqmData();
    if ( RpcEtwGuid_Context )
      EtwEventUnregister();
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18008b990  push    rbx
0x18008b992  sub     rsp, 20h
0x18008b996  mov     rbx, r8
0x18008b999  test    edx, edx
0x18008b99b  jz      short loc_18008BA0D
0x18008b99d  sub     edx, 1
0x18008b9a0  jz      short loc_18008B9B3
0x18008b9a2  cmp     edx, 2
0x18008b9a5  jz      loc_18008BA3E
0x18008b9ab  mov     al, 1
0x18008b9ad  add     rsp, 20h
0x18008b9b1  pop     rbx
0x18008b9b2  retn
0x18008b9b3  call    TlgRegisterAggregateProviderEx
0x18008b9b8  xor     edx, edx; SpinCount
0x18008b9ba  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008b9c1  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x18008b9c7  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008b9ce  mov     cs:?GlobalMutexInitialized@@3HA, 1; int GlobalMutexInitialized
0x18008b9d8  call    cs:__imp_InitializeCriticalSection
0x18008b9de  mov     rcx, gs:60h
0x18008b9e7  mov     cs:byte_1800F9EC4, 1
0x18008b9ee  mov     rcx, [rcx+10h]; BaseAddress
0x18008b9f2  call    cs:__imp_RtlImageNtHeader
0x18008b9f8  mov     edx, 400h
0x18008b9fd  cmp     [rax+68h], rdx
0x18008ba01  cmovb   rdx, [rax+68h]
0x18008ba06  call    SafeAllocaInitialize
0x18008ba0b  jmp     short loc_18008B9AB
0x18008ba0d  call    TlgUnregisterAggregateProvider
0x18008ba12  test    rbx, rbx
0x18008ba15  jz      short loc_18008BA6D
0x18008ba17  cmp     cs:?g_SqmEnabled@@3HA, 0; int g_SqmEnabled
0x18008ba1e  jnz     loc_18008BAB8
0x18008ba24  mov     rcx, cs:RpcEtwGuid_Context
0x18008ba2b  test    rcx, rcx
0x18008ba2e  jnz     loc_18008BAC2
0x18008ba34  call    McGenEventUnregister_EtwEventUnregister
0x18008ba39  jmp     loc_18008B9AB
0x18008ba3e  call    ?RpcpGetThreadPointer@@YAPEAVTHREAD@@XZ; RpcpGetThreadPointer(void)
0x18008ba43  mov     rcx, rax; this
0x18008ba46  mov     rax, gs:30h
0x18008ba4f  mov     qword ptr [rax+1698h], 0
0x18008ba5a  test    rcx, rcx
0x18008ba5d  jz      loc_18008B9AB
0x18008ba63  call    ??_GTHREAD@@QEAAPEAXI@Z; THREAD::`scalar deleting destructor'(uint)
0x18008ba68  jmp     loc_18008B9AB
0x18008ba6d  call    RpcpExtFreeExtensions
0x18008ba72  cmp     cs:?GlobalMutexInitialized@@3HA, 1; int GlobalMutexInitialized
0x18008ba79  jnz     short loc_18008BA92
0x18008ba7b  lea     rcx, ?GlobalMutex@@3PADA; CriticalSection
0x18008ba82  call    cs:__imp_RtlDeleteCriticalSection
0x18008ba88  mov     cs:?GlobalMutexInitialized@@3HA, 0; int GlobalMutexInitialized
0x18008ba92  cmp     cs:byte_1800F9EC4, 0
0x18008ba99  jz      loc_18008BA17
0x18008ba9f  lea     rcx, ?NdrOle_CS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18008baa6  call    cs:__imp_DeleteCriticalSection
0x18008baac  mov     cs:byte_1800F9EC4, 0
0x18008bab3  jmp     loc_18008BA17
0x18008bab8  call    ?UploadAllSqmData@@YAXXZ; UploadAllSqmData(void)
0x18008babd  jmp     loc_18008BA24
0x18008bac2  call    cs:__imp_EtwEventUnregister
0x18008bac8  jmp     loc_18008BA34
```
