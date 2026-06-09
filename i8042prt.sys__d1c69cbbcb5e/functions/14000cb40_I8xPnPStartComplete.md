# I8xPnPStartComplete

- ea: `0x14000cb40`
- end: `0x14000cbd7`
- name: `I8xPnPStartComplete`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004530`
- `0x14000cb40`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14000cbb5`
- `ntoskrnl!IoQueueWorkItem` at `0x14000cbb5`

## pseudocode

```c
__int64 __fastcall I8xPnPStartComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi

  v3 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      12,
      (__int64)WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids);
  if ( *(_BYTE *)(v3 + 565) )
    *(_QWORD *)(a3 + 16) = a2;
  else
    *(_QWORD *)(a3 + 8) = a2;
  IoQueueWorkItem(*(PIO_WORKITEM *)a3, I8xStartDeviceCallback, DelayedWorkQueue, (PVOID)a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000cb40  mov     [rsp+arg_0], rbx
0x14000cb45  mov     [rsp+arg_8], rsi
0x14000cb4a  push    rdi
0x14000cb4b  sub     rsp, 30h
0x14000cb4f  mov     rsi, [rcx+40h]
0x14000cb53  mov     rbx, r8
0x14000cb56  mov     rdi, rdx
0x14000cb59  lea     rax, WPP_RECORDER_INITIALIZED
0x14000cb60  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000cb67  jz      short loc_14000CB8F
0x14000cb69  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb70  lea     rax, WPP_2842e8c1d8f03f4a13b4c4f7b213f744_Traceguids
0x14000cb77  mov     r9d, 0Ch
0x14000cb7d  mov     [rsp+38h+var_18], rax
0x14000cb82  mov     rcx, [rcx+40h]
0x14000cb86  lea     r8d, [r9+3]
0x14000cb8a  call    WPP_RECORDER_SF_
0x14000cb8f  cmp     byte ptr [rsi+235h], 0
0x14000cb96  jz      short loc_14000CB9E
0x14000cb98  mov     [rbx+10h], rdi
0x14000cb9c  jmp     short loc_14000CBA2
0x14000cb9e  mov     [rbx+8], rdi
0x14000cba2  mov     rcx, [rbx]; IoWorkItem
0x14000cba5  lea     rdx, I8xStartDeviceCallback; WorkerRoutine
0x14000cbac  mov     r9, rbx; Context
0x14000cbaf  mov     r8d, 1; QueueType
0x14000cbb5  call    cs:__imp_IoQueueWorkItem
0x14000cbbc  nop     dword ptr [rax+rax+00h]
0x14000cbc1  mov     rbx, [rsp+38h+arg_0]
0x14000cbc6  mov     eax, 0C0000016h
0x14000cbcb  mov     rsi, [rsp+38h+arg_8]
0x14000cbd0  add     rsp, 30h
0x14000cbd4  pop     rdi
0x14000cbd5  retn
```
