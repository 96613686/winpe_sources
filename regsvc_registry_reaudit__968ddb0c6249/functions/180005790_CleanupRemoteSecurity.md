# CleanupRemoteSecurity

- ea: `0x180005790`
- end: `0x18000592e`
- name: `CleanupRemoteSecurity`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008600`

## callees

- `0x180005790`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1800057eb`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1800057eb`
- `ntdll!RtlDeleteResource` at `0x1800057a8`
- `ntdll!RtlDeleteResource` at `0x1800057a8`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180005820`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180005820`
- `ntdll!RtlFreeHeap` at `0x1800057c4`
- `ntdll!RtlFreeHeap` at `0x180005809`
- `ntdll!RtlFreeHeap` at `0x18000583e`
- `ntdll!RtlFreeHeap` at `0x18000585a`
- `ntdll!RtlFreeHeap` at `0x180005886`
- `ntdll!RtlFreeHeap` at `0x1800058ab`
- `ntdll!RtlFreeHeap` at `0x1800058d0`
- `ntdll!RtlFreeHeap` at `0x1800058f5`
- `ntdll!RtlFreeHeap` at `0x1800057c4`
- `ntdll!RtlFreeHeap` at `0x180005809`
- `ntdll!RtlFreeHeap` at `0x18000583e`
- `ntdll!RtlFreeHeap` at `0x18000585a`
- `ntdll!RtlFreeHeap` at `0x180005886`
- `ntdll!RtlFreeHeap` at `0x1800058ab`
- `ntdll!RtlFreeHeap` at `0x1800058d0`
- `ntdll!RtlFreeHeap` at `0x1800058f5`

## pseudocode

```c
__int64 CleanupRemoteSecurity()
{
  __int64 result; // rax
  unsigned __int8 GroupDefaulted; // [rsp+30h] [rbp+8h] BYREF
  PSID Group; // [rsp+38h] [rbp+10h] BYREF

  Group = 0;
  GroupDefaulted = 0;
  RtlDeleteResource(RegSecReloadLock);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, RegSecReloadLock);
  RegSecReloadLock = 0;
  if ( RemoteRegistrySD )
  {
    if ( RtlGetGroupSecurityDescriptor(RemoteRegistrySD, &Group, &GroupDefaulted) >= 0 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Group);
    if ( RtlGetOwnerSecurityDescriptor(RemoteRegistrySD, &Group, &GroupDefaulted) >= 0 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Group);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, RemoteRegistrySD);
    RemoteRegistrySD = 0;
  }
  if ( MachineAllowedPaths )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, MachineAllowedPaths);
  if ( MachineAllowedPathsBase )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, MachineAllowedPathsBase);
  if ( MachineAllowedExactPaths )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, MachineAllowedExactPaths);
  if ( MachineAllowedExactPathsBase )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, MachineAllowedExactPathsBase);
  MachineAllowedPaths = 0;
  result = 1;
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
0x180005790  push    rbx
0x180005792  sub     rsp, 20h
0x180005796  mov     rcx, cs:RegSecReloadLock; Resource
0x18000579d  xor     ebx, ebx
0x18000579f  mov     [rsp+28h+Group], rbx
0x1800057a4  mov     [rsp+28h+GroupDefaulted], bl
0x1800057a8  call    cs:__imp_RtlDeleteResource
0x1800057ae  mov     rcx, gs:60h
0x1800057b7  xor     edx, edx; Flags
0x1800057b9  mov     r8, cs:RegSecReloadLock; P
0x1800057c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800057c4  call    cs:__imp_RtlFreeHeap
0x1800057ca  mov     rcx, cs:RemoteRegistrySD; SecurityDescriptor
0x1800057d1  mov     cs:RegSecReloadLock, rbx
0x1800057d8  test    rcx, rcx
0x1800057db  jz      loc_180005867
0x1800057e1  lea     r8, [rsp+28h+GroupDefaulted]; GroupDefaulted
0x1800057e6  lea     rdx, [rsp+28h+Group]; Group
0x1800057eb  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1800057f1  test    eax, eax
0x1800057f3  js      short loc_18000580F
0x1800057f5  mov     rcx, gs:60h
0x1800057fe  xor     edx, edx; Flags
0x180005800  mov     r8, [rsp+28h+Group]; P
0x180005805  mov     rcx, [rcx+30h]; HeapHandle
0x180005809  call    cs:__imp_RtlFreeHeap
0x18000580f  mov     rcx, cs:RemoteRegistrySD; SecurityDescriptor
0x180005816  lea     r8, [rsp+28h+GroupDefaulted]; OwnerDefaulted
0x18000581b  lea     rdx, [rsp+28h+Group]; Owner
0x180005820  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180005826  test    eax, eax
0x180005828  js      short loc_180005844
0x18000582a  mov     rcx, gs:60h
0x180005833  xor     edx, edx; Flags
0x180005835  mov     r8, [rsp+28h+Group]; P
0x18000583a  mov     rcx, [rcx+30h]; HeapHandle
0x18000583e  call    cs:__imp_RtlFreeHeap
0x180005844  mov     rcx, gs:60h
0x18000584d  xor     edx, edx; Flags
0x18000584f  mov     r8, cs:RemoteRegistrySD; P
0x180005856  mov     rcx, [rcx+30h]; HeapHandle
0x18000585a  call    cs:__imp_RtlFreeHeap
0x180005860  mov     cs:RemoteRegistrySD, rbx
0x180005867  cmp     cs:MachineAllowedPaths, rbx
0x18000586e  jz      short loc_18000588C
0x180005870  mov     rcx, gs:60h
0x180005879  xor     edx, edx; Flags
0x18000587b  mov     r8, cs:MachineAllowedPaths; P
0x180005882  mov     rcx, [rcx+30h]; HeapHandle
0x180005886  call    cs:__imp_RtlFreeHeap
0x18000588c  cmp     cs:MachineAllowedPathsBase, rbx
0x180005893  jz      short loc_1800058B1
0x180005895  mov     rcx, gs:60h
0x18000589e  xor     edx, edx; Flags
0x1800058a0  mov     r8, cs:MachineAllowedPathsBase; P
0x1800058a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800058ab  call    cs:__imp_RtlFreeHeap
0x1800058b1  cmp     cs:MachineAllowedExactPaths, rbx
0x1800058b8  jz      short loc_1800058D6
0x1800058ba  mov     rcx, gs:60h
0x1800058c3  xor     edx, edx; Flags
0x1800058c5  mov     r8, cs:MachineAllowedExactPaths; P
0x1800058cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800058d0  call    cs:__imp_RtlFreeHeap
0x1800058d6  cmp     cs:MachineAllowedExactPathsBase, rbx
0x1800058dd  jz      short loc_1800058FB
0x1800058df  mov     rcx, gs:60h
0x1800058e8  xor     edx, edx; Flags
0x1800058ea  mov     r8, cs:MachineAllowedExactPathsBase; P
0x1800058f1  mov     rcx, [rcx+30h]; HeapHandle
0x1800058f5  call    cs:__imp_RtlFreeHeap
0x1800058fb  mov     cs:MachineAllowedPaths, rbx
0x180005902  mov     eax, 1
0x180005907  mov     cs:MachineAllowedPathsBase, rbx
0x18000590e  mov     cs:MachineAllowedPathsCount, ebx
0x180005914  mov     cs:MachineAllowedExactPaths, rbx
0x18000591b  mov     cs:MachineAllowedExactPathsBase, rbx
0x180005922  mov     cs:MachineAllowedExactPathsCount, ebx
0x180005928  add     rsp, 20h
0x18000592c  pop     rbx
0x18000592d  retn
```
