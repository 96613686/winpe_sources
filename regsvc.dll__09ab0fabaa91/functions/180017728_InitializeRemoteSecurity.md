# InitializeRemoteSecurity

- ea: `0x180017728`
- end: `0x180017825`
- name: `InitializeRemoteSecurity`
- size: `253`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008870`

## callees

- `0x180017728`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18001775b`
- `ntdll!RtlInitializeResource` at `0x18001775b`
- `ntdll!RtlFreeHeap` at `0x180017787`
- `ntdll!RtlFreeHeap` at `0x180017787`
- `ntdll!RtlAllocateHeap` at `0x18001773f`
- `ntdll!RtlAllocateHeap` at `0x18001773f`

## pseudocode

```c
__int64 InitializeRemoteSecurity()
{
  struct _RTL_RESOURCE *Heap; // rax
  __int64 result; // rax

  Heap = (struct _RTL_RESOURCE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x60u);
  RegSecReloadLock = Heap;
  if ( !Heap )
    return 0;
  RtlInitializeResource(Heap);
  result = 1;
  RemoteRegistryMappings.GenericRead = 1;
  RemoteRegistryMappings.GenericWrite = 2;
  RemoteRegistryMappings.GenericExecute = 1;
  RemoteRegistryMappings.GenericAll = 3;
  WinregChange = 0;
  AllowedPathsChange = 0;
  AllowedExactPathsChange = 0;
  MachineAllowedPaths = 0;
  MachineAllowedPathsBase = 0;
  LODWORD(MachineAllowedPathsCount) = 0;
  MachineAllowedExactPaths = 0;
  MachineAllowedExactPathsBase = 0;
  MachineAllowedExactPathsCount = 0;
  return result;
}

```

## disassembly

```asm
0x180017728  sub     rsp, 38h
0x18001772c  mov     rcx, gs:60h
0x180017735  xor     edx, edx; Flags
0x180017737  lea     r8d, [rdx+60h]; Size
0x18001773b  mov     rcx, [rcx+30h]; HeapHandle
0x18001773f  call    cs:__imp_RtlAllocateHeap
0x180017745  mov     cs:RegSecReloadLock, rax
0x18001774c  test    rax, rax
0x18001774f  jnz     short loc_180017758
0x180017751  xor     eax, eax
0x180017753  jmp     loc_180017820
0x180017758  mov     rcx, rax; Resource
0x18001775b  call    cs:__imp_RtlInitializeResource
0x180017761  xor     eax, eax
0x180017763  mov     [rsp+38h+var_18], eax
0x180017767  jmp     short loc_18001776D
0x180017769  mov     [rsp+38h+var_18], eax
0x18001776d  test    eax, eax
0x18001776f  jns     short loc_18001779A
0x180017771  mov     rcx, gs:60h
0x18001777a  mov     r8, cs:RegSecReloadLock; P
0x180017781  xor     edx, edx; Flags
0x180017783  mov     rcx, [rcx+30h]; HeapHandle
0x180017787  call    cs:__imp_RtlFreeHeap
0x18001778d  mov     cs:RegSecReloadLock, 0
0x180017798  jmp     short loc_180017751
0x18001779a  mov     eax, 1
0x18001779f  mov     cs:RemoteRegistryMappings.GenericRead, eax
0x1800177a5  mov     cs:RemoteRegistryMappings.GenericWrite, 2
0x1800177af  mov     cs:RemoteRegistryMappings.GenericExecute, eax
0x1800177b5  mov     cs:RemoteRegistryMappings.GenericAll, 3
0x1800177bf  mov     cs:WinregChange, 0
0x1800177ca  mov     cs:AllowedPathsChange, 0
0x1800177d5  mov     cs:AllowedExactPathsChange, 0
0x1800177e0  mov     cs:MachineAllowedPaths, 0
0x1800177eb  mov     cs:MachineAllowedPathsBase, 0
0x1800177f6  mov     cs:MachineAllowedPathsCount, 0
0x180017800  mov     cs:MachineAllowedExactPaths, 0
0x18001780b  mov     cs:MachineAllowedExactPathsBase, 0
0x180017816  mov     cs:MachineAllowedExactPathsCount, 0
0x180017820  add     rsp, 38h
0x180017824  retn
```
