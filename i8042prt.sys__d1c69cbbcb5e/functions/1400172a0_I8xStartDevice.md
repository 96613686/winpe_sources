# I8xStartDevice

- ea: `0x1400172a0`
- end: `0x1400173e9`
- name: `I8xStartDevice`
- size: `329`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400173f0`
- `0x14001fa30`

## callees

- `0x1400043e0`
- `0x1400172a0`
- `0x1400198e0`
- `0x14001c068`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400173d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400173d1`
- `ntoskrnl!IofCompleteRequest` at `0x14001738d`
- `ntoskrnl!IofCompleteRequest` at `0x14001738d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400172ba`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400172ba`
- `ntoskrnl!IoFreeWorkItem` at `0x1400173ba`
- `ntoskrnl!IoFreeWorkItem` at `0x1400173ba`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140017371`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140017371`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400173a6`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400173a6`

## pseudocode

```c
__int64 __fastcall I8xStartDevice(__int64 a1, __int64 a2)
{
  __int64 v2; // rbp
  const char *v5; // rcx
  IRP *v6; // rbx
  void *v7; // rcx
  int started; // eax
  unsigned int v9; // esi

  v2 = *(_QWORD *)(a1 + 64);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
  if ( *(_BYTE *)(v2 + 566) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v5 = "kb";
    if ( !*(_BYTE *)(v2 + 565) )
      v5 = "mouse";
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)"mouse",
      17,
      37,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
      (__int64)v5);
  }
  v6 = *(IRP **)(a2 + 16);
  v7 = *(void **)(a1 + 64);
  if ( v6 )
  {
    started = I8xKeyboardStartDevice(v7, v6->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName);
  }
  else
  {
    v6 = *(IRP **)(a2 + 8);
    started = I8xMouseStartDevice(v7);
  }
  v9 = started;
  if ( started >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.DeviceQueue.Type);
    *(_BYTE *)(v2 + 566) = 1;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
  v6->IoStatus.Status = v9;
  v6->IoStatus.Information = 0;
  IofCompleteRequest(v6, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), v6, 0x20u);
  if ( *(_QWORD *)a2 )
    IoFreeWorkItem(*(PIO_WORKITEM *)a2);
  if ( !*(_BYTE *)(a2 + 24) )
    ExFreePoolWithTag((PVOID)a2, 0);
  return v9;
}

```

## disassembly

```asm
0x1400172a0  push    rbx
0x1400172a2  push    rbp
0x1400172a3  push    rsi
0x1400172a4  push    rdi
0x1400172a5  sub     rsp, 38h
0x1400172a9  mov     rbp, [rcx+40h]
0x1400172ad  mov     rsi, rcx
0x1400172b0  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; FastMutex
0x1400172b7  mov     rdi, rdx
0x1400172ba  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400172c1  nop     dword ptr [rax+rax+00h]
0x1400172c6  cmp     byte ptr [rbp+236h], 0
0x1400172cd  jz      short loc_140017323
0x1400172cf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400172d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400172dd  jz      short loc_140017323
0x1400172df  cmp     byte ptr [rbp+235h], 0
0x1400172e6  lea     rdx, aMouse_0; "mouse"
0x1400172ed  mov     r9d, 25h ; '%'
0x1400172f3  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x1400172fa  lea     rcx, aKb; "kb"
0x140017301  cmovz   rcx, rdx
0x140017305  mov     [rsp+58h+var_30], rcx
0x14001730a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017311  lea     r8d, [r9-14h]
0x140017315  mov     [rsp+58h+var_38], rax
0x14001731a  mov     rcx, [rcx+40h]
0x14001731e  call    WPP_RECORDER_SF_s
0x140017323  mov     rbx, [rdi+10h]
0x140017327  mov     rcx, [rsi+40h]; Context
0x14001732b  test    rbx, rbx
0x14001732e  jz      short loc_140017342
0x140017330  mov     rdx, [rbx+0B8h]
0x140017337  mov     rdx, [rdx+10h]
0x14001733b  call    I8xKeyboardStartDevice
0x140017340  jmp     short loc_140017356
0x140017342  mov     rbx, [rdi+8]
0x140017346  mov     rdx, [rbx+0B8h]
0x14001734d  mov     rdx, [rdx+10h]
0x140017351  call    I8xMouseStartDevice
0x140017356  mov     esi, eax
0x140017358  test    eax, eax
0x14001735a  js      short loc_14001736A
0x14001735c  lock inc dword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140017363  mov     byte ptr [rbp+236h], 1
0x14001736a  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; FastMutex
0x140017371  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140017378  nop     dword ptr [rax+rax+00h]
0x14001737d  xor     edx, edx; PriorityBoost
0x14001737f  mov     [rbx+30h], esi
0x140017382  mov     rcx, rbx; Irp
0x140017385  mov     qword ptr [rbx+38h], 0
0x14001738d  call    cs:__imp_IofCompleteRequest
0x140017394  nop     dword ptr [rax+rax+00h]
0x140017399  lea     rcx, [rbp+28h]; RemoveLock
0x14001739d  mov     r8d, 20h ; ' '; RemlockSize
0x1400173a3  mov     rdx, rbx; Tag
0x1400173a6  call    cs:__imp_IoReleaseRemoveLockEx
0x1400173ad  nop     dword ptr [rax+rax+00h]
0x1400173b2  mov     rcx, [rdi]; IoWorkItem
0x1400173b5  test    rcx, rcx
0x1400173b8  jz      short loc_1400173C6
0x1400173ba  call    cs:__imp_IoFreeWorkItem
0x1400173c1  nop     dword ptr [rax+rax+00h]
0x1400173c6  cmp     byte ptr [rdi+18h], 0
0x1400173ca  jnz     short loc_1400173DD
0x1400173cc  xor     edx, edx; Tag
0x1400173ce  mov     rcx, rdi; P
0x1400173d1  call    cs:__imp_ExFreePoolWithTag
0x1400173d8  nop     dword ptr [rax+rax+00h]
0x1400173dd  mov     eax, esi
0x1400173df  add     rsp, 38h
0x1400173e3  pop     rdi
0x1400173e4  pop     rsi
0x1400173e5  pop     rbp
0x1400173e6  pop     rbx
0x1400173e7  retn
```
