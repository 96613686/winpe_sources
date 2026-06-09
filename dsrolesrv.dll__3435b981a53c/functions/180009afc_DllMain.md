# DllMain

- ea: `0x180009afc`
- end: `0x180009bf4`
- name: `DllMain`
- size: `248`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001464`

## callees

- `0x180009afc`
- `0x180027c80`
- `0x18002c01e`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180009b09`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180009b09`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b3c`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b49`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b56`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b3c`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b49`
- `ntdll!RtlInitializeCriticalSection` at `0x180009b56`
- `ntdll!RtlInitializeResource` at `0x180009b2f`
- `ntdll!RtlInitializeResource` at `0x180009b2f`
- `ntdll!RtlDeleteResource` at `0x180009b9b`
- `ntdll!RtlDeleteResource` at `0x180009b9b`
- `ntdll!RtlDeleteCriticalSection` at `0x180009ba8`
- `ntdll!RtlDeleteCriticalSection` at `0x180009bb5`
- `ntdll!RtlDeleteCriticalSection` at `0x180009bcc`
- `ntdll!RtlDeleteCriticalSection` at `0x180009ba8`
- `ntdll!RtlDeleteCriticalSection` at `0x180009bb5`
- `ntdll!RtlDeleteCriticalSection` at `0x180009bcc`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180009b81`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180009b81`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v3; // rax

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    SafeAllocaInitialize();
    memset_0(&DsRolepCurrentOperationHandle, 0, 0xE0u);
    RtlInitializeResource(&DsRolepCurrentOperationHandle);
    RtlInitializeCriticalSection(&LogFileCriticalSection);
    RtlInitializeCriticalSection(&gcsUpdateMessage);
    RtlInitializeCriticalSection(&CriticalSection);
    RtlInitializeGenericTableAvl(&Table, (PRTL_AVL_COMPARE_ROUTINE)compareLists, allocateEvntlogMap, freeEvntlogMap, 0);
    byte_18004DE60 = 1;
  }
  else if ( !fdwReason )
  {
    RtlDeleteResource(&DsRolepCurrentOperationHandle);
    RtlDeleteCriticalSection(&LogFileCriticalSection);
    LODWORD(v3) = RtlDeleteCriticalSection(&gcsUpdateMessage);
    if ( byte_18004DE60 )
    {
      RtlDeleteCriticalSection(&CriticalSection);
      byte_18004DE60 = 0;
      v3 = memset_0(&CriticalSection, 0, 0x98u);
    }
  }
  LOBYTE(v3) = 1;
  return (int)v3;
}

```

## disassembly

```asm
0x180009afc  sub     rsp, 38h
0x180009b00  cmp     edx, 1
0x180009b03  jnz     loc_180009B90
0x180009b09  call    cs:__imp_DisableThreadLibraryCalls
0x180009b0f  call    SafeAllocaInitialize
0x180009b14  xor     edx, edx; Val
0x180009b16  lea     rcx, DsRolepCurrentOperationHandle; void *
0x180009b1d  mov     r8d, 0E0h; Size
0x180009b23  call    memset_0
0x180009b28  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x180009b2f  call    cs:__imp_RtlInitializeResource
0x180009b35  lea     rcx, LogFileCriticalSection; CriticalSection
0x180009b3c  call    cs:__imp_RtlInitializeCriticalSection
0x180009b42  lea     rcx, gcsUpdateMessage; CriticalSection
0x180009b49  call    cs:__imp_RtlInitializeCriticalSection
0x180009b4f  lea     rcx, CriticalSection; CriticalSection
0x180009b56  call    cs:__imp_RtlInitializeCriticalSection
0x180009b5c  lea     r9, freeEvntlogMap; FreeRoutine
0x180009b63  mov     [rsp+38h+TableContext], 0; TableContext
0x180009b6c  lea     r8, allocateEvntlogMap; AllocateRoutine
0x180009b73  lea     rdx, compareLists; CompareRoutine
0x180009b7a  lea     rcx, Table; Table
0x180009b81  call    cs:__imp_RtlInitializeGenericTableAvl
0x180009b87  mov     cs:byte_18004DE60, 1
0x180009b8e  jmp     short loc_180009BED
0x180009b90  test    edx, edx
0x180009b92  jnz     short loc_180009BED
0x180009b94  lea     rcx, DsRolepCurrentOperationHandle; Resource
0x180009b9b  call    cs:__imp_RtlDeleteResource
0x180009ba1  lea     rcx, LogFileCriticalSection; CriticalSection
0x180009ba8  call    cs:__imp_RtlDeleteCriticalSection
0x180009bae  lea     rcx, gcsUpdateMessage; CriticalSection
0x180009bb5  call    cs:__imp_RtlDeleteCriticalSection
0x180009bbb  mov     cl, cs:byte_18004DE60
0x180009bc1  test    cl, cl
0x180009bc3  jz      short loc_180009BED
0x180009bc5  lea     rcx, CriticalSection; CriticalSection
0x180009bcc  call    cs:__imp_RtlDeleteCriticalSection
0x180009bd2  xor     edx, edx; Val
0x180009bd4  mov     cs:byte_18004DE60, 0
0x180009bdb  mov     r8d, 98h; Size
0x180009be1  lea     rcx, CriticalSection; void *
0x180009be8  call    memset_0
0x180009bed  mov     al, 1
0x180009bef  add     rsp, 38h
0x180009bf3  retn
```
