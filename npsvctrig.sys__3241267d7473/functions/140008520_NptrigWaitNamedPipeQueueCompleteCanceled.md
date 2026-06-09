# NptrigWaitNamedPipeQueueCompleteCanceled

- ea: `0x140008520`
- end: `0x1400085a4`
- name: `NptrigWaitNamedPipeQueueCompleteCanceled`
- size: `132`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001500`
- `0x140001928`
- `0x140008330`
- `0x140008520`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140008561`
- `ntoskrnl!KeCancelTimer` at `0x140008561`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140008589`
- `FLTMGR!FltCompletePendedPostOperation` at `0x140008589`

## pseudocode

```c
void __fastcall NptrigWaitNamedPipeQueueCompleteCanceled(
        PFLT_CALLBACK_DATA_QUEUE Cbdq,
        PFLT_CALLBACK_DATA Cbd,
        __int64 a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8

  v3 = Cbd->QueueContext[0];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 32, a3, v3, *v3);
  if ( KeCancelTimer((PKTIMER)(v3 + 15)) )
    NptrigReleaseRequestRef((volatile signed __int32 *)v3, v4, v5);
  NptrigAlterIoStatus((PFLT_CALLBACK_DATA)*v3, -1073741536, v5);
  FltCompletePendedPostOperation((PFLT_CALLBACK_DATA)*v3);
  NptrigReleaseRequestRef((volatile signed __int32 *)v3, v6, v7);
}

```

## disassembly

```asm
0x140008520  push    rbx
0x140008522  sub     rsp, 30h
0x140008526  mov     rbx, [rdx+40h]
0x14000852a  mov     rcx, cs:WPP_GLOBAL_Control
0x140008531  lea     rax, WPP_GLOBAL_Control
0x140008538  cmp     rcx, rax
0x14000853b  jz      short loc_14000855D
0x14000853d  mov     eax, [rcx+2Ch]
0x140008540  test    al, 4
0x140008542  jz      short loc_14000855D
0x140008544  mov     rax, [rbx]
0x140008547  mov     edx, 20h ; ' '
0x14000854c  mov     rcx, [rcx+18h]
0x140008550  mov     r9, rbx
0x140008553  mov     [rsp+38h+var_18], rax
0x140008558  call    WPP_SF_qq
0x14000855d  lea     rcx, [rbx+78h]; PKTIMER
0x140008561  call    cs:__imp_KeCancelTimer
0x140008568  nop     dword ptr [rax+rax+00h]
0x14000856d  test    al, al
0x14000856f  jz      short loc_140008579
0x140008571  mov     rcx, rbx; P
0x140008574  call    NptrigReleaseRequestRef
0x140008579  mov     rcx, [rbx]; Data
0x14000857c  mov     edx, 0C0000120h
0x140008581  call    NptrigAlterIoStatus
0x140008586  mov     rcx, [rbx]; CallbackData
0x140008589  call    cs:__imp_FltCompletePendedPostOperation
0x140008590  nop     dword ptr [rax+rax+00h]
0x140008595  mov     rcx, rbx; P
0x140008598  call    NptrigReleaseRequestRef
0x14000859d  add     rsp, 30h
0x1400085a1  pop     rbx
0x1400085a2  retn
```
