# PerflibciInitialize(void)

- ea: `0x18000d93c`
- end: `0x18000d9bc`
- name: `?PerflibciInitialize@@YAEXZ`
- size: `128`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e50`

## callees

- `0x18000d93c`
- `0x18000dca0`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18000d9ae`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18000d9ae`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000d953`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000d953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d96e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d96e`

## pseudocode

```c
char PerflibciInitialize(void)
{
  HANDLE MutexW; // rax
  char v1; // bl

  if ( g_hGlobalMutex )
    goto LABEL_7;
  MutexW = CreateMutexW(0, 0, 0);
  if ( MutexW && _InterlockedCompareExchange64((volatile signed __int64 *)&g_hGlobalMutex, (signed __int64)MutexW, 0) )
    CloseHandle(MutexW);
  if ( g_hGlobalMutex )
LABEL_7:
    v1 = 1;
  else
    v1 = 0;
  PerflibciValidateCode();
  RtlInitializeGenericTableAvl(&Table, PerflibCompareResources, PerflibAllocateMemory, PerflibFreeMemory, 0);
  return v1;
}

```

## disassembly

```asm
0x18000d93c  push    rbx
0x18000d93e  sub     rsp, 30h
0x18000d942  cmp     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x18000d94a  jnz     short loc_18000D982
0x18000d94c  xor     r8d, r8d; lpName
0x18000d94f  xor     edx, edx; bInitialOwner
0x18000d951  xor     ecx, ecx; lpMutexAttributes
0x18000d953  call    cs:__imp_CreateMutexW
0x18000d959  mov     rcx, rax; hObject
0x18000d95c  test    rax, rax
0x18000d95f  jz      short loc_18000D974
0x18000d961  xor     eax, eax
0x18000d963  lock cmpxchg cs:?g_hGlobalMutex@@3PEAXEA, rcx; void * g_hGlobalMutex
0x18000d96c  jz      short loc_18000D974
0x18000d96e  call    cs:__imp_CloseHandle
0x18000d974  cmp     cs:?g_hGlobalMutex@@3PEAXEA, 0; void * g_hGlobalMutex
0x18000d97c  jnz     short loc_18000D982
0x18000d97e  xor     bl, bl
0x18000d980  jmp     short loc_18000D984
0x18000d982  mov     bl, 1
0x18000d984  call    ?PerflibciValidateCode@@YAKXZ; PerflibciValidateCode(void)
0x18000d989  lea     r9, PerflibFreeMemory; FreeRoutine
0x18000d990  mov     [rsp+38h+TableContext], 0; TableContext
0x18000d999  lea     r8, PerflibAllocateMemory; AllocateRoutine
0x18000d9a0  lea     rdx, PerflibCompareResources; CompareRoutine
0x18000d9a7  lea     rcx, Table; Table
0x18000d9ae  call    cs:__imp_RtlInitializeGenericTableAvl
0x18000d9b4  mov     al, bl
0x18000d9b6  add     rsp, 30h
0x18000d9ba  pop     rbx
0x18000d9bb  retn
```
