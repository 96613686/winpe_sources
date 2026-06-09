# MupiGetOrCreateEcpListForCreateIrp

- ea: `0x14001d514`
- end: `0x14001d5ab`
- name: `MupiGetOrCreateEcpListForCreateIrp`
- size: `151`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001bb60`

## callees

- `0x14001d514`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001d58c`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001d58c`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001d539`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001d539`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001d55f`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001d55f`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14001d577`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14001d577`

## pseudocode

```c
NTSTATUS __fastcall MupiGetOrCreateEcpListForCreateIrp(PIRP Irp, PECP_LIST *a2)
{
  NTSTATUS result; // eax
  PECP_LIST v5; // rcx
  NTSTATUS v6; // eax
  PECP_LIST EcpList; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  EcpList = 0;
  if ( FsRtlGetEcpListFromIrp(Irp, &EcpList) < 0 )
    return -1073741595;
  v5 = EcpList;
  if ( !EcpList )
  {
    result = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
    if ( result < 0 )
      return result;
    v6 = FsRtlSetEcpListIntoIrp(Irp, EcpList);
    v5 = EcpList;
    if ( v6 < 0 )
    {
      FsRtlFreeExtraCreateParameterList(EcpList);
      return -1073741595;
    }
  }
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x14001d514  mov     [rsp+arg_0], rbx
0x14001d519  push    rdi
0x14001d51a  sub     rsp, 20h
0x14001d51e  mov     rbx, rdx
0x14001d521  mov     qword ptr [rdx], 0
0x14001d528  lea     rdx, [rsp+28h+EcpList]; EcpList
0x14001d52d  mov     [rsp+28h+EcpList], 0
0x14001d536  mov     rdi, rcx
0x14001d539  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14001d540  nop     dword ptr [rax+rax+00h]
0x14001d545  test    eax, eax
0x14001d547  jns     short loc_14001D550
0x14001d549  mov     eax, 0C00000E5h
0x14001d54e  jmp     short loc_14001D59F
0x14001d550  mov     rcx, [rsp+28h+EcpList]; Flags
0x14001d555  test    rcx, rcx
0x14001d558  jnz     short loc_14001D59A
0x14001d55a  lea     rdx, [rsp+28h+EcpList]; EcpList
0x14001d55f  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14001d566  nop     dword ptr [rax+rax+00h]
0x14001d56b  test    eax, eax
0x14001d56d  js      short loc_14001D59F
0x14001d56f  mov     rdx, [rsp+28h+EcpList]; EcpList
0x14001d574  mov     rcx, rdi; Irp
0x14001d577  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14001d57e  nop     dword ptr [rax+rax+00h]
0x14001d583  mov     rcx, [rsp+28h+EcpList]; EcpList
0x14001d588  test    eax, eax
0x14001d58a  jns     short loc_14001D59A
0x14001d58c  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14001d593  nop     dword ptr [rax+rax+00h]
0x14001d598  jmp     short loc_14001D549
0x14001d59a  xor     eax, eax
0x14001d59c  mov     [rbx], rcx
0x14001d59f  mov     rbx, [rsp+28h+arg_0]
0x14001d5a4  add     rsp, 20h
0x14001d5a8  pop     rdi
0x14001d5a9  retn
```
