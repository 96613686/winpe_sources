# I8xKeyboardGetSysButtonEvent

- ea: `0x14000d1a8`
- end: `0x14000d45a`
- name: `I8xKeyboardGetSysButtonEvent`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140020210`

## callees

- `0x140004530`
- `0x140007b10`
- `0x14000d128`
- `0x14000d1a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d245`
- `ntoskrnl!ExAllocatePool2` at `0x14000d245`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d2f4`
- `ntoskrnl!IofCompleteRequest` at `0x14000d214`
- `ntoskrnl!IofCompleteRequest` at `0x14000d214`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d317`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d317`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d3fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d3fc`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d26e`
- `ntoskrnl!IoAllocateWorkItem` at `0x14000d26e`
- `ntoskrnl!IoQueueWorkItem` at `0x14000d2dc`
- `ntoskrnl!IoQueueWorkItem` at `0x14000d2dc`

## pseudocode

```c
__int64 __fastcall I8xKeyboardGetSysButtonEvent(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // esi
  int v7; // edx
  int v8; // r9d
  __int64 Pool2; // r12
  PIO_WORKITEM WorkItem; // rax
  int v11; // edx
  KSPIN_LOCK *v12; // r12
  int v13; // edx
  KIRQL v14; // cl
  unsigned int v16; // [rsp+28h] [rbp-40h]
  KIRQL v17; // [rsp+78h] [rbp+10h]

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 8LL) >= 4u )
  {
    if ( *(_BYTE *)(a1 + 585) )
    {
      v6 = -1073741670;
      Pool2 = ExAllocatePool2(64, 24, 842281016, a4);
      if ( Pool2 )
      {
        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)a1);
        *(_QWORD *)Pool2 = WorkItem;
        if ( WorkItem )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v11,
              22,
              16,
              (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          *(_DWORD *)(Pool2 + 8) = *(unsigned __int8 *)(a1 + 585);
          *(_QWORD *)(Pool2 + 16) = a2;
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
          IoQueueWorkItem(*(PIO_WORKITEM *)Pool2, I8xCompleteSysButtonEventWorker, DelayedWorkQueue, (PVOID)Pool2);
          v6 = 259;
        }
        else
        {
          ExFreePoolWithTag((PVOID)Pool2, 0);
        }
      }
      *(_BYTE *)(a1 + 585) = 0;
    }
    else
    {
      v12 = (KSPIN_LOCK *)(a1 + 664);
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 664));
      v17 = v14;
      if ( *(_QWORD *)(a1 + 592) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            25,
            19,
            (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          v14 = v17;
        }
        v6 = -1073741823;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            24,
            18,
            (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
          v14 = v17;
        }
        *(_QWORD *)(a1 + 592) = a2;
        _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&I8xSysButtonCancelRoutine);
        if ( *(_BYTE *)(a2 + 68) && _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
        {
          *(_QWORD *)(a1 + 592) = 0;
          v6 = -1073741536;
        }
        else
        {
          v6 = 259;
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
        }
      }
      KeReleaseSpinLock(v12, v14);
    }
    if ( v6 != 259 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = v6;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          22,
          20,
          (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids,
          v16);
      }
      I8xCompleteSysButtonIrp((PIRP)a2, 0, v6, v8);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        25,
        15,
        (__int64)WPP_9a74d45702a83a61696de9b252942f2f_Traceguids);
    v6 = -1073741306;
    *(_QWORD *)(a2 + 56) = 0;
    *(_DWORD *)(a2 + 48) = -1073741306;
    IofCompleteRequest((PIRP)a2, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x14000d1a8  push    rbx
0x14000d1aa  push    rbp
0x14000d1ab  push    rsi
0x14000d1ac  push    r12
0x14000d1ae  push    r14
0x14000d1b0  push    r15
0x14000d1b2  sub     rsp, 38h
0x14000d1b6  mov     rax, [rdx+0B8h]
0x14000d1bd  mov     rbx, rdx
0x14000d1c0  mov     r14, rcx
0x14000d1c3  cmp     dword ptr [rax+8], 4
0x14000d1c7  jnb     short loc_14000D225
0x14000d1c9  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000d1d0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d1d7  jz      short loc_14000D1FF
0x14000d1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d1e0  lea     r15, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14000d1e7  mov     r9d, 0Fh
0x14000d1ed  mov     [rsp+68h+var_48], r15
0x14000d1f2  mov     rcx, [rcx+40h]
0x14000d1f6  lea     r8d, [r9+0Ah]
0x14000d1fa  call    WPP_RECORDER_SF_
0x14000d1ff  mov     esi, 0C0000206h
0x14000d204  mov     qword ptr [rbx+38h], 0
0x14000d20c  xor     edx, edx; PriorityBoost
0x14000d20e  mov     [rbx+30h], esi
0x14000d211  mov     rcx, rbx; Irp
0x14000d214  call    cs:__imp_IofCompleteRequest
0x14000d21b  nop     dword ptr [rax+rax+00h]
0x14000d220  jmp     loc_14000D449
0x14000d225  cmp     byte ptr [rcx+249h], 0
0x14000d22c  jz      loc_14000D30D
0x14000d232  mov     edx, 18h
0x14000d237  mov     r8d, 32343038h
0x14000d23d  mov     esi, 0C000009Ah
0x14000d242  lea     ecx, [rdx+28h]
0x14000d245  call    cs:__imp_ExAllocatePool2
0x14000d24c  nop     dword ptr [rax+rax+00h]
0x14000d251  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000d258  mov     r12, rax
0x14000d25b  lea     r15, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14000d262  test    rax, rax
0x14000d265  jz      loc_14000D300
0x14000d26b  mov     rcx, [r14]; DeviceObject
0x14000d26e  call    cs:__imp_IoAllocateWorkItem
0x14000d275  nop     dword ptr [rax+rax+00h]
0x14000d27a  mov     [r12], rax
0x14000d27e  test    rax, rax
0x14000d281  jz      short loc_14000D2EF
0x14000d283  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d28a  jz      short loc_14000D2AB
0x14000d28c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d293  mov     r9d, 10h
0x14000d299  mov     [rsp+68h+var_48], r15
0x14000d29e  mov     rcx, [rcx+40h]
0x14000d2a2  lea     r8d, [r9+6]
0x14000d2a6  call    WPP_RECORDER_SF_
0x14000d2ab  movzx   eax, byte ptr [r14+249h]
0x14000d2b3  lea     rdx, I8xCompleteSysButtonEventWorker; WorkerRoutine
0x14000d2ba  mov     [r12+8], eax
0x14000d2bf  mov     r9, r12; Context
0x14000d2c2  mov     [r12+10h], rbx
0x14000d2c7  mov     r8d, 1; QueueType
0x14000d2cd  mov     rax, [rbx+0B8h]
0x14000d2d4  or      byte ptr [rax+3], 1
0x14000d2d8  mov     rcx, [r12]; IoWorkItem
0x14000d2dc  call    cs:__imp_IoQueueWorkItem
0x14000d2e3  nop     dword ptr [rax+rax+00h]
0x14000d2e8  mov     esi, 103h
0x14000d2ed  jmp     short loc_14000D300
0x14000d2ef  xor     edx, edx; Tag
0x14000d2f1  mov     rcx, r12; P
0x14000d2f4  call    cs:__imp_ExFreePoolWithTag
0x14000d2fb  nop     dword ptr [rax+rax+00h]
0x14000d300  mov     byte ptr [r14+249h], 0
0x14000d308  jmp     loc_14000D408
0x14000d30d  lea     r12, [rcx+298h]
0x14000d314  mov     rcx, r12; SpinLock
0x14000d317  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d31e  nop     dword ptr [rax+rax+00h]
0x14000d323  cmp     qword ptr [r14+250h], 0
0x14000d32b  mov     cl, al
0x14000d32d  mov     [rsp+68h+arg_8], al
0x14000d331  jnz     loc_14000D3B8
0x14000d337  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000d33e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d345  lea     r15, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14000d34c  jz      short loc_14000D371
0x14000d34e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d355  mov     r9d, 12h
0x14000d35b  mov     [rsp+68h+var_48], r15
0x14000d360  mov     rcx, [rcx+40h]
0x14000d364  lea     r8d, [r9+6]
0x14000d368  call    WPP_RECORDER_SF_
0x14000d36d  mov     cl, [rsp+68h+arg_8]
0x14000d371  mov     [r14+250h], rbx
0x14000d378  lea     rax, I8xSysButtonCancelRoutine
0x14000d37f  xchg    rax, [rbx+68h]
0x14000d383  cmp     byte ptr [rbx+44h], 0
0x14000d387  jz      short loc_14000D3A6
0x14000d389  xor     eax, eax
0x14000d38b  xchg    rax, [rbx+68h]
0x14000d38f  test    rax, rax
0x14000d392  jz      short loc_14000D3A6
0x14000d394  mov     qword ptr [r14+250h], 0
0x14000d39f  mov     esi, 0C0000120h
0x14000d3a4  jmp     short loc_14000D3F7
0x14000d3a6  mov     rax, [rbx+0B8h]
0x14000d3ad  mov     esi, 103h
0x14000d3b2  or      byte ptr [rax+3], 1
0x14000d3b6  jmp     short loc_14000D3F7
0x14000d3b8  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000d3bf  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d3c6  lea     r15, WPP_9a74d45702a83a61696de9b252942f2f_Traceguids
0x14000d3cd  jz      short loc_14000D3F2
0x14000d3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3d6  mov     r9d, 13h
0x14000d3dc  mov     [rsp+68h+var_48], r15
0x14000d3e1  mov     rcx, [rcx+40h]
0x14000d3e5  lea     r8d, [r9+6]
0x14000d3e9  call    WPP_RECORDER_SF_
0x14000d3ee  mov     cl, [rsp+68h+arg_8]
0x14000d3f2  mov     esi, 0C0000001h
0x14000d3f7  mov     dl, cl; NewIrql
0x14000d3f9  mov     rcx, r12; SpinLock
0x14000d3fc  call    cs:__imp_KeReleaseSpinLock
0x14000d403  nop     dword ptr [rax+rax+00h]
0x14000d408  cmp     esi, 103h
0x14000d40e  jz      short loc_14000D449
0x14000d410  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000d417  jz      short loc_14000D43C
0x14000d419  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d420  mov     r9d, 14h
0x14000d426  mov     [rsp+68h+var_40], esi
0x14000d42a  mov     [rsp+68h+var_48], r15
0x14000d42f  mov     rcx, [rcx+40h]
0x14000d433  lea     r8d, [r9+2]
0x14000d437  call    WPP_RECORDER_SF_D
0x14000d43c  mov     r8d, esi
0x14000d43f  xor     edx, edx
0x14000d441  mov     rcx, rbx; Irp
0x14000d444  call    I8xCompleteSysButtonIrp
0x14000d449  mov     eax, esi
0x14000d44b  add     rsp, 38h
0x14000d44f  pop     r15
0x14000d451  pop     r14
0x14000d453  pop     r12
0x14000d455  pop     rsi
0x14000d456  pop     rbp
0x14000d457  pop     rbx
0x14000d458  retn
```
