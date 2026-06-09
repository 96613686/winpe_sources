# HsmiDehydrationCsqCOMPLETE_CANCELED_IO

- ea: `0x140042720`
- end: `0x140042777`
- name: `HsmiDehydrationCsqCOMPLETE_CANCELED_IO`
- size: `87`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140042720`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042737`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042737`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140042764`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140042764`

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
0x140042720  push    rbx
0x140042722  sub     rsp, 20h
0x140042726  mov     rcx, [rdx+40h]; P
0x14004272a  mov     rbx, rdx
0x14004272d  test    rcx, rcx
0x140042730  jz      short loc_14004274B
0x140042732  mov     edx, 74436F49h; Tag
0x140042737  call    cs:__imp_ExFreePoolWithTag
0x14004273e  nop     dword ptr [rax+rax+00h]
0x140042743  mov     qword ptr [rbx+40h], 0
0x14004274b  xor     r8d, r8d; Context
0x14004274e  mov     dword ptr [rbx+18h], 0C0000120h
0x140042755  mov     rcx, rbx; CallbackData
0x140042758  mov     qword ptr [rbx+20h], 0
0x140042760  lea     edx, [r8+4]; CallbackStatus
0x140042764  call    cs:__imp_FltCompletePendedPreOperation
0x14004276b  nop     dword ptr [rax+rax+00h]
0x140042770  add     rsp, 20h
0x140042774  pop     rbx
0x140042775  retn
```
