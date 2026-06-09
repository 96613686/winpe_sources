# I8xCompleteSysButtonIrp

- ea: `0x14000d128`
- end: `0x14000d1a0`
- name: `I8xCompleteSysButtonIrp`
- size: `120`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b1a0`
- `0x14000d1a8`
- `0x14000d460`
- `0x14001d150`
- `0x14001d300`

## callees

- `0x14000d128`
- `0x14000d780`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d183`
- `ntoskrnl!IofCompleteRequest` at `0x14000d183`

## pseudocode

```c
void __fastcall I8xCompleteSysButtonIrp(PIRP Irp, int a2, NTSTATUS a3, int a4)
{
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdD(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
  *(_DWORD *)Irp->AssociatedIrp.MasterIrp = a2;
  Irp->IoStatus.Information = 4;
  Irp->IoStatus.Status = a3;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x14000d128  mov     [rsp+arg_0], rbx
0x14000d12d  mov     [rsp+arg_8], rsi
0x14000d132  push    rdi
0x14000d133  sub     rsp, 40h
0x14000d137  mov     edi, r8d
0x14000d13a  mov     esi, edx
0x14000d13c  mov     rbx, rcx
0x14000d13f  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d146  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d14d  jz      short loc_14000D16D
0x14000d14f  mov     [rsp+48h+var_10], r8d
0x14000d154  mov     [rsp+48h+var_18], edx
0x14000d158  mov     [rsp+48h+var_20], rcx
0x14000d15d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d164  mov     rcx, [rcx+40h]
0x14000d168  call    WPP_RECORDER_SF_qdD
0x14000d16d  mov     rax, [rbx+18h]
0x14000d171  xor     edx, edx; PriorityBoost
0x14000d173  mov     rcx, rbx; Irp
0x14000d176  mov     [rax], esi
0x14000d178  mov     qword ptr [rbx+38h], 4
0x14000d180  mov     [rbx+30h], edi
0x14000d183  call    cs:__imp_IofCompleteRequest
0x14000d18a  nop     dword ptr [rax+rax+00h]
0x14000d18f  mov     rbx, [rsp+48h+arg_0]
0x14000d194  mov     rsi, [rsp+48h+arg_8]
0x14000d199  add     rsp, 40h
0x14000d19d  pop     rdi
0x14000d19e  retn
```
