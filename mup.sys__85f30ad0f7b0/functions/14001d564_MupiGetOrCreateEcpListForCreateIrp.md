# MupiGetOrCreateEcpListForCreateIrp

- ea: `0x14001d564`
- end: `0x14001d5fb`
- name: `MupiGetOrCreateEcpListForCreateIrp`
- size: `151`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001bbb0`

## callees

- `0x14001d564`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001d5dc`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14001d5dc`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001d589`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14001d589`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001d5af`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001d5af`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14001d5c7`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14001d5c7`

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
0x14001d564  mov     [rsp+arg_0], rbx
0x14001d569  push    rdi
0x14001d56a  sub     rsp, 20h
0x14001d56e  mov     rbx, rdx
0x14001d571  mov     qword ptr [rdx], 0
0x14001d578  lea     rdx, [rsp+28h+EcpList]; EcpList
0x14001d57d  mov     [rsp+28h+EcpList], 0
0x14001d586  mov     rdi, rcx
0x14001d589  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14001d590  nop     dword ptr [rax+rax+00h]
0x14001d595  test    eax, eax
0x14001d597  jns     short loc_14001D5A0
0x14001d599  mov     eax, 0C00000E5h
0x14001d59e  jmp     short loc_14001D5EF
0x14001d5a0  mov     rcx, [rsp+28h+EcpList]; Flags
0x14001d5a5  test    rcx, rcx
0x14001d5a8  jnz     short loc_14001D5EA
0x14001d5aa  lea     rdx, [rsp+28h+EcpList]; EcpList
0x14001d5af  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14001d5b6  nop     dword ptr [rax+rax+00h]
0x14001d5bb  test    eax, eax
0x14001d5bd  js      short loc_14001D5EF
0x14001d5bf  mov     rdx, [rsp+28h+EcpList]; EcpList
0x14001d5c4  mov     rcx, rdi; Irp
0x14001d5c7  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14001d5ce  nop     dword ptr [rax+rax+00h]
0x14001d5d3  mov     rcx, [rsp+28h+EcpList]; EcpList
0x14001d5d8  test    eax, eax
0x14001d5da  jns     short loc_14001D5EA
0x14001d5dc  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14001d5e3  nop     dword ptr [rax+rax+00h]
0x14001d5e8  jmp     short loc_14001D599
0x14001d5ea  xor     eax, eax
0x14001d5ec  mov     [rbx], rcx
0x14001d5ef  mov     rbx, [rsp+28h+arg_0]
0x14001d5f4  add     rsp, 20h
0x14001d5f8  pop     rdi
0x14001d5f9  retn
```
