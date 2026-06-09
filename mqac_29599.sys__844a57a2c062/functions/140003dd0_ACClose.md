# ACClose

- ea: `0x140003dd0`
- end: `0x140003ec6`
- name: `ACClose`
- size: `246`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001c04`
- `0x140003d84`
- `0x140003dd0`
- `0x140009834`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140003e18`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003e18`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003e27`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003e27`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003ea0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003ea0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003eac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003eac`
- `ntoskrnl!IofCompleteRequest` at `0x140003e91`
- `ntoskrnl!IofCompleteRequest` at `0x140003e91`

## pseudocode

```c
__int64 __fastcall ACClose(struct _DEVICE_OBJECT *a1, PIRP Irp)
{
  char *DeviceExtension; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_267336381a143880ad9a6d598fdda2de_Traceguids);
  }
  DeviceExtension = (char *)a1->DeviceExtension;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  if ( _InterlockedExchangeAdd64((volatile signed __int64 *)DeviceExtension + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    ACpSetPerformanceBuffer(a1, 0, 0, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, &WPP_267336381a143880ad9a6d598fdda2de_Traceguids, Irp);
  }
  Irp->IoStatus.Information = 0;
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(DeviceExtension + 8));
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x140003dd0  push    rbx
0x140003dd2  push    rbp
0x140003dd3  push    rsi
0x140003dd4  push    rdi
0x140003dd5  push    r14
0x140003dd7  sub     rsp, 30h
0x140003ddb  mov     rdi, rdx
0x140003dde  mov     rbp, rcx
0x140003de1  mov     rcx, cs:WPP_GLOBAL_Control
0x140003de8  lea     r14, WPP_GLOBAL_Control
0x140003def  cmp     rcx, r14
0x140003df2  jz      short loc_140003E10
0x140003df4  mov     eax, [rcx+6Ch]
0x140003df7  test    al, 4
0x140003df9  jz      short loc_140003E10
0x140003dfb  mov     rcx, [rcx+58h]
0x140003dff  lea     r8, WPP_267336381a143880ad9a6d598fdda2de_Traceguids
0x140003e06  mov     edx, 0Ah
0x140003e0b  call    WPP_SF_
0x140003e10  mov     rbx, [rbp+40h]
0x140003e14  lea     rsi, [rbx+8]
0x140003e18  call    cs:__imp_KeEnterCriticalRegion
0x140003e1f  nop     dword ptr [rax+rax+00h]
0x140003e24  mov     rcx, rsi; FastMutex
0x140003e27  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140003e2e  nop     dword ptr [rax+rax+00h]
0x140003e33  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003e37  lock xadd [rbx+40h], rax
0x140003e3d  xor     ebx, ebx
0x140003e3f  cmp     rax, 1
0x140003e43  jnz     short loc_140003E5A
0x140003e45  xor     r9d, r9d; struct QueueCounters *
0x140003e48  mov     [rsp+58h+var_38], rbx; struct _QmCounters *
0x140003e4d  xor     r8d, r8d; void *
0x140003e50  xor     edx, edx; void *
0x140003e52  mov     rcx, rbp; struct _DEVICE_OBJECT *
0x140003e55  call    ?ACpSetPerformanceBuffer@@YAJPEAU_DEVICE_OBJECT@@PEAX1PEAUQueueCounters@@PEAU_QmCounters@@@Z; ACpSetPerformanceBuffer(_DEVICE_OBJECT *,void *,void *,QueueCounters *,_QmCounters *)
0x140003e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e61  cmp     rcx, r14
0x140003e64  jz      short loc_140003E85
0x140003e66  mov     eax, [rcx+6Ch]
0x140003e69  test    al, 4
0x140003e6b  jz      short loc_140003E85
0x140003e6d  mov     rcx, [rcx+58h]
0x140003e71  lea     r8, WPP_267336381a143880ad9a6d598fdda2de_Traceguids
0x140003e78  mov     edx, 0Bh
0x140003e7d  mov     r9, rdi
0x140003e80  call    WPP_SF_q
0x140003e85  xor     edx, edx; PriorityBoost
0x140003e87  mov     [rdi+38h], rbx
0x140003e8b  mov     rcx, rdi; Irp
0x140003e8e  mov     [rdi+30h], ebx
0x140003e91  call    cs:__imp_IofCompleteRequest
0x140003e98  nop     dword ptr [rax+rax+00h]
0x140003e9d  mov     rcx, rsi; FastMutex
0x140003ea0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140003ea7  nop     dword ptr [rax+rax+00h]
0x140003eac  call    cs:__imp_KeLeaveCriticalRegion
0x140003eb3  nop     dword ptr [rax+rax+00h]
0x140003eb8  xor     eax, eax
0x140003eba  add     rsp, 30h
0x140003ebe  pop     r14
0x140003ec0  pop     rdi
0x140003ec1  pop     rsi
0x140003ec2  pop     rbp
0x140003ec3  pop     rbx
0x140003ec4  retn
```
