# DsRolepFreeInterfaceSDs

- ea: `0x180015574`
- end: `0x180015667`
- name: `DsRolepFreeInterfaceSDs`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009ee0`
- `0x18001530c`

## callees

- `0x180015574`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001561b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800155fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001561b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180015638`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001564a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180015638`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001564a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180015660`
- `ntdll!RtlFreeHeap` at `0x180015599`
- `ntdll!RtlFreeHeap` at `0x180015599`

## pseudocode

```c
BOOL DsRolepFreeInterfaceSDs()
{
  _QWORD *v0; // rax

  _mm_lfence();
  if ( *(_QWORD *)DsRolepAllowedSids[0] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)DsRolepAllowedSids[0]);
    v0 = (_QWORD *)DsRolepAllowedSids[0];
    DsRolepAllowedSids[0] = 0;
    *v0 = 0;
  }
  if ( DsRolepPromoteAcl )
  {
    LocalFree(DsRolepPromoteAcl);
    DsRolepPromoteAcl = 0;
  }
  if ( DsRolepDemoteAcl )
  {
    LocalFree(DsRolepDemoteAcl);
    DsRolepDemoteAcl = 0;
  }
  if ( DsRolepCallDsRoleInterfaceAcl )
  {
    LocalFree(DsRolepCallDsRoleInterfaceAcl);
    DsRolepCallDsRoleInterfaceAcl = 0;
  }
  if ( DsRolepSacl )
  {
    LocalFree(DsRolepSacl);
    DsRolepSacl = 0;
  }
  InitializeSecurityDescriptor(DsRolepPromoteSD, 1u);
  InitializeSecurityDescriptor(DsRolepDemoteSD, 1u);
  return InitializeSecurityDescriptor(DsRolepCallDsRoleInterfaceSD, 1u);
}

```

## disassembly

```asm
0x180015574  sub     rsp, 28h
0x180015578  lfence
0x18001557b  mov     rax, cs:DsRolepAllowedSids
0x180015582  mov     r8, [rax]; P
0x180015585  test    r8, r8
0x180015588  jz      short loc_1800155B8
0x18001558a  mov     rcx, gs:60h
0x180015593  xor     edx, edx; Flags
0x180015595  mov     rcx, [rcx+30h]; HeapHandle
0x180015599  call    cs:__imp_RtlFreeHeap
0x18001559f  mov     rax, cs:DsRolepAllowedSids
0x1800155a6  mov     cs:DsRolepAllowedSids, 0
0x1800155b1  mov     qword ptr [rax], 0
0x1800155b8  mov     rcx, cs:DsRolepPromoteAcl; hMem
0x1800155bf  test    rcx, rcx
0x1800155c2  jz      short loc_1800155D5
0x1800155c4  call    cs:__imp_LocalFree
0x1800155ca  mov     cs:DsRolepPromoteAcl, 0
0x1800155d5  mov     rcx, cs:DsRolepDemoteAcl; hMem
0x1800155dc  test    rcx, rcx
0x1800155df  jz      short loc_1800155F2
0x1800155e1  call    cs:__imp_LocalFree
0x1800155e7  mov     cs:DsRolepDemoteAcl, 0
0x1800155f2  mov     rcx, cs:DsRolepCallDsRoleInterfaceAcl; hMem
0x1800155f9  test    rcx, rcx
0x1800155fc  jz      short loc_18001560F
0x1800155fe  call    cs:__imp_LocalFree
0x180015604  mov     cs:DsRolepCallDsRoleInterfaceAcl, 0
0x18001560f  mov     rcx, cs:DsRolepSacl; hMem
0x180015616  test    rcx, rcx
0x180015619  jz      short loc_18001562C
0x18001561b  call    cs:__imp_LocalFree
0x180015621  mov     cs:DsRolepSacl, 0
0x18001562c  mov     edx, 1; dwRevision
0x180015631  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x180015638  call    cs:__imp_InitializeSecurityDescriptor
0x18001563e  mov     edx, 1; dwRevision
0x180015643  lea     rcx, DsRolepDemoteSD; pSecurityDescriptor
0x18001564a  call    cs:__imp_InitializeSecurityDescriptor
0x180015650  mov     edx, 1
0x180015655  lea     rcx, DsRolepCallDsRoleInterfaceSD
0x18001565c  add     rsp, 28h
0x180015660  jmp     cs:__imp_InitializeSecurityDescriptor
```
