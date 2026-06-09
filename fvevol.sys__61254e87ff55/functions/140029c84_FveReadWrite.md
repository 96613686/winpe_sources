# FveReadWrite

- ea: `0x140029c84`
- end: `0x140029ea3`
- name: `FveReadWrite`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400291d8`

## callees

- `0x140008348`
- `0x14000a210`
- `0x140029c84`
- `0x140029eb0`
- `0x14002a3a0`
- `0x14002a4e4`
- `0x1400ebc00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140029dec`
- `ntoskrnl!IofCompleteRequest` at `0x140029dec`
- `ntoskrnl!IoGetFsTrackOffsetState` at `0x140029ce4`
- `ntoskrnl!IoGetFsTrackOffsetState` at `0x140029ce4`
- `ntoskrnl!IoAllocateWorkItem` at `0x140029e45`
- `ntoskrnl!IoAllocateWorkItem` at `0x140029e45`
- `ntoskrnl!IoQueueWorkItem` at `0x140029e70`
- `ntoskrnl!IoQueueWorkItem` at `0x140029e70`

## pseudocode

```c
__int64 __fastcall FveReadWrite(__int64 a1, __int64 a2, char a3, unsigned __int64 a4, ULONG a5)
{
  __int64 v9; // r8
  char v10; // si
  int v11; // eax
  __int64 v13; // rax
  __int64 v14; // r8
  struct _IO_WORKITEM *WorkItem; // rax
  _QWORD v16[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 840) )
  {
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    return 259;
  }
  if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(a1, a2)
    || !*(_BYTE *)(a1 + 4824)
    || (v13 = *(_QWORD *)(a1 + 4752)) == 0
    || !*(_DWORD *)(v13 + 88) )
  {
    v17 = 0;
    v16[0] = 0;
    if ( (int)IoGetFsTrackOffsetState(a2, &v17, v16) >= 0
      && v17
      && (*(_BYTE *)(v17 + 2) & 1) != 0
      && v16[0] != -1
      && *(_QWORD *)(v17 + 16) )
    {
      v10 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v16[0]);
      }
    }
    else
    {
      v10 = 0;
    }
    v11 = *(_DWORD *)(a1 + 836);
    if ( v11 == 2 && !v10 || !a5 )
    {
      LOBYTE(v9) = a3;
      return FveRequestPassThrough(a1, a2, v9);
    }
    if ( v11 != 1 )
    {
      if ( (unsigned int)(v11 - 5) > 3 )
        return FveFilterReadWrite(a1, (IRP *)a2, a3, a4, a5);
      v14 = *(unsigned int *)(a1 + 816);
      return FveFailRundownReadWriteIrp(a1, a2, v14, (unsigned __int8)BYTE1(*(_DWORD *)(a2 + 120)));
    }
    FvepInformRundownFinishedWithDisk(a1, a2, BYTE1(*(_DWORD *)(a2 + 120)));
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
    WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)a1);
    if ( WorkItem )
    {
      *(_QWORD *)(a2 + 128) = WorkItem;
      IoQueueWorkItem(WorkItem, FveDiscoverVolumeWorker, DelayedWorkQueue, (PVOID)a2);
    }
    else
    {
      *(_DWORD *)(a2 + 48) = -1073741670;
      IofCompleteRequest((PIRP)a2, 0);
    }
    return 259;
  }
  v14 = 3221225486LL;
  return FveFailRundownReadWriteIrp(a1, a2, v14, (unsigned __int8)BYTE1(*(_DWORD *)(a2 + 120)));
}

```

## disassembly

```asm
0x140029c84  mov     [rsp+arg_8], rbx
0x140029c89  mov     [rsp+arg_10], rbp
0x140029c8e  push    rsi
0x140029c8f  push    rdi
0x140029c90  push    r14
0x140029c92  sub     rsp, 40h
0x140029c96  cmp     dword ptr [rcx+348h], 0
0x140029c9d  mov     r14, r9
0x140029ca0  mov     bpl, r8b
0x140029ca3  mov     rbx, rdx
0x140029ca6  mov     rdi, rcx
0x140029ca9  jnz     loc_140029DD3
0x140029caf  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x140029cb4  test    eax, eax
0x140029cb6  jz      short loc_140029CC5
0x140029cb8  cmp     byte ptr [rdi+12D8h], 0
0x140029cbf  jnz     loc_140029E02
0x140029cc5  lea     r8, [rsp+58h+var_28]
0x140029cca  mov     [rsp+58h+arg_0], 0
0x140029cd3  lea     rdx, [rsp+58h+arg_0]
0x140029cd8  mov     [rsp+58h+var_28], 0
0x140029ce1  mov     rcx, rbx
0x140029ce4  call    cs:__imp_IoGetFsTrackOffsetState
0x140029ceb  nop     dword ptr [rax+rax+00h]
0x140029cf0  test    eax, eax
0x140029cf2  jns     short loc_140029D60
0x140029cf4  xor     sil, sil
0x140029cf7  mov     eax, [rdi+344h]
0x140029cfd  cmp     eax, 2
0x140029d00  jnz     short loc_140029D29
0x140029d02  test    sil, sil
0x140029d05  jnz     short loc_140029D29
0x140029d07  mov     r8b, bpl
0x140029d0a  mov     rdx, rbx
0x140029d0d  mov     rcx, rdi
0x140029d10  call    FveRequestPassThrough
0x140029d15  mov     rbx, [rsp+58h+arg_8]
0x140029d1a  mov     rbp, [rsp+58h+arg_10]
0x140029d1f  add     rsp, 40h
0x140029d23  pop     r14
0x140029d25  pop     rdi
0x140029d26  pop     rsi
0x140029d27  retn
0x140029d29  mov     ecx, [rsp+58h+arg_20]
0x140029d30  test    ecx, ecx
0x140029d32  jz      short loc_140029D07
0x140029d34  cmp     eax, 1
0x140029d37  jz      loc_140029E24
0x140029d3d  add     eax, 0FFFFFFFBh
0x140029d40  cmp     eax, 3
0x140029d43  jbe     loc_140029E81
0x140029d49  mov     [rsp+58h+var_38], ecx
0x140029d4d  mov     r9, r14
0x140029d50  mov     rcx, rdi
0x140029d53  mov     r8b, bpl
0x140029d56  mov     rdx, rbx
0x140029d59  call    FveFilterReadWrite
0x140029d5e  jmp     short loc_140029D15
0x140029d60  mov     rcx, [rsp+58h+arg_0]
0x140029d65  test    rcx, rcx
0x140029d68  jz      short loc_140029CF4
0x140029d6a  test    byte ptr [rcx+2], 1
0x140029d6e  jz      short loc_140029CF4
0x140029d70  mov     r9, [rsp+58h+var_28]
0x140029d75  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x140029d79  jz      loc_140029CF4
0x140029d7f  cmp     qword ptr [rcx+10h], 0
0x140029d84  jz      loc_140029CF4
0x140029d8a  mov     sil, 1
0x140029d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029d94  lea     rax, WPP_GLOBAL_Control
0x140029d9b  cmp     rcx, rax
0x140029d9e  jz      loc_140029CF7
0x140029da4  mov     eax, [rcx+2Ch]
0x140029da7  test    al, 40h
0x140029da9  jz      loc_140029CF7
0x140029daf  cmp     byte ptr [rcx+29h], 5
0x140029db3  jb      loc_140029CF7
0x140029db9  mov     rcx, [rcx+18h]
0x140029dbd  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140029dc4  mov     edx, 0Dh
0x140029dc9  call    WPP_SF_q
0x140029dce  jmp     loc_140029CF7
0x140029dd3  mov     rax, [rdx+0B8h]
0x140029dda  or      byte ptr [rax+3], 1
0x140029dde  jmp     short loc_140029DF8
0x140029de0  xor     edx, edx; PriorityBoost
0x140029de2  mov     dword ptr [rbx+30h], 0C000009Ah
0x140029de9  mov     rcx, rbx; Irp
0x140029dec  call    cs:__imp_IofCompleteRequest
0x140029df3  nop     dword ptr [rax+rax+00h]
0x140029df8  mov     eax, 103h
0x140029dfd  jmp     loc_140029D15
0x140029e02  mov     rax, [rdi+1290h]
0x140029e09  test    rax, rax
0x140029e0c  jz      loc_140029CC5
0x140029e12  cmp     dword ptr [rax+58h], 0
0x140029e16  jz      loc_140029CC5
0x140029e1c  mov     r8d, 0C000000Eh
0x140029e22  jmp     short loc_140029E88
0x140029e24  mov     r8d, [rbx+78h]
0x140029e28  mov     rdx, rbx
0x140029e2b  shr     r8, 8
0x140029e2f  mov     rcx, rdi
0x140029e32  call    FvepInformRundownFinishedWithDisk
0x140029e37  mov     rax, [rbx+0B8h]
0x140029e3e  or      byte ptr [rax+3], 1
0x140029e42  mov     rcx, [rdi]; DeviceObject
0x140029e45  call    cs:__imp_IoAllocateWorkItem
0x140029e4c  nop     dword ptr [rax+rax+00h]
0x140029e51  test    rax, rax
0x140029e54  jz      short loc_140029DE0
0x140029e56  mov     r9, rbx; Context
0x140029e59  mov     [rbx+80h], rax
0x140029e60  mov     r8d, 1; QueueType
0x140029e66  lea     rdx, FveDiscoverVolumeWorker; WorkerRoutine
0x140029e6d  mov     rcx, rax; IoWorkItem
0x140029e70  call    cs:__imp_IoQueueWorkItem
0x140029e77  nop     dword ptr [rax+rax+00h]
0x140029e7c  jmp     loc_140029DF8
0x140029e81  mov     r8d, [rdi+330h]
0x140029e88  mov     eax, [rbx+78h]
0x140029e8b  mov     rdx, rbx
0x140029e8e  shr     rax, 8
0x140029e92  mov     rcx, rdi
0x140029e95  movzx   r9d, al
0x140029e99  call    FveFailRundownReadWriteIrp
0x140029e9e  jmp     loc_140029D15
```
