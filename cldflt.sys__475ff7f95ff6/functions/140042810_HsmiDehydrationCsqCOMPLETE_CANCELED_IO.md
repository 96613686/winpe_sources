# HsmiDehydrationCsqCOMPLETE_CANCELED_IO

- ea: `0x140042810`
- end: `0x140042867`
- name: `HsmiDehydrationCsqCOMPLETE_CANCELED_IO`
- size: `87`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140042810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042827`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140042854`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140042854`

## pseudocode

```c
void __fastcall HsmiDehydrationCsqCOMPLETE_CANCELED_IO(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  PVOID v2; // rcx

  v2 = Cbd->QueueContext[0];
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x74436F49u);
    Cbd->QueueContext[0] = 0;
  }
  Cbd->IoStatus.Status = -1073741536;
  Cbd->IoStatus.Information = 0;
  FltCompletePendedPreOperation(Cbd, FLT_PREOP_COMPLETE, 0);
}

```

## disassembly

```asm
0x140042810  push    rbx
0x140042812  sub     rsp, 20h
0x140042816  mov     rcx, [rdx+40h]; P
0x14004281a  mov     rbx, rdx
0x14004281d  test    rcx, rcx
0x140042820  jz      short loc_14004283B
0x140042822  mov     edx, 74436F49h; Tag
0x140042827  call    cs:__imp_ExFreePoolWithTag
0x14004282e  nop     dword ptr [rax+rax+00h]
0x140042833  mov     qword ptr [rbx+40h], 0
0x14004283b  xor     r8d, r8d; Context
0x14004283e  mov     dword ptr [rbx+18h], 0C0000120h
0x140042845  mov     rcx, rbx; CallbackData
0x140042848  mov     qword ptr [rbx+20h], 0
0x140042850  lea     edx, [r8+4]; CallbackStatus
0x140042854  call    cs:__imp_FltCompletePendedPreOperation
0x14004285b  nop     dword ptr [rax+rax+00h]
0x140042860  add     rsp, 20h
0x140042864  pop     rbx
0x140042865  retn
```
