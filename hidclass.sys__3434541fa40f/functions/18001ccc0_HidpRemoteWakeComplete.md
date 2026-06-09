# HidpRemoteWakeComplete

- ea: `0x18001ccc0`
- end: `0x18001cfbc`
- name: `HidpRemoteWakeComplete`
- size: `764`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009a78`
- `0x180013860`
- `0x18001ccc0`
- `0x18001cfc4`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x18001cef3`
- `ntoskrnl!IoQueueWorkItem` at `0x18001cef3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ce35`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001cf15`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ce35`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001cf15`
- `ntoskrnl!IoFreeWorkItem` at `0x18001cf04`
- `ntoskrnl!IoFreeWorkItem` at `0x18001cf04`
- `ntoskrnl!ExAllocatePool2` at `0x18001cdfb`
- `ntoskrnl!ExAllocatePool2` at `0x18001cdfb`
- `ntoskrnl!IoAllocateWorkItem` at `0x18001ce17`
- `ntoskrnl!IoAllocateWorkItem` at `0x18001ce17`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001ced2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18001ced2`

## pseudocode

```c
void __fastcall HidpRemoteWakeComplete(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        char *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  __int64 v5; // rbp
  int Status; // eax
  char v8; // si
  char v9; // r10
  char v10; // dl
  __int64 v11; // r8
  __int64 v12; // rax
  _QWORD *Pool2; // rdi
  int v14; // r8d
  PIO_WORKITEM WorkItem; // rax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  NTSTATUS v18; // eax
  struct _IO_WORKITEM *v19; // rcx
  __int16 v20; // [rsp+30h] [rbp-68h]
  __int64 v21; // [rsp+40h] [rbp-58h]
  int v22; // [rsp+48h] [rbp-50h]
  __int64 v23; // [rsp+50h] [rbp-48h]

  v5 = *((_QWORD *)Context + 8);
  _InterlockedExchange64((volatile __int64 *)Context + 12, 0);
  _InterlockedExchange((volatile __int32 *)Context + 26, 0);
  Status = IoStatus->Status;
  if ( IoStatus->Status != -2147483631
    && Status != -1073741536
    && Status != -1073741436
    && Status != -1073741101
    && Status != -1072431071 )
  {
    if ( Status )
    {
      HidpToggleRemoteWake((__int64)Context, 0);
      return;
    }
    v8 = 1;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || (v9 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      v9 = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (v10 = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      v10 = 0;
    }
    if ( v9 || v10 )
    {
      v11 = *((_QWORD *)Context + 8);
      v12 = *(_QWORD *)(v11 + 32);
      LOBYTE(v11) = v10;
      WPP_RECORDER_AND_TRACE_SF_qdqL(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        *(_QWORD *)(v5 + 704),
        5,
        7,
        10,
        (__int64)WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids,
        v12,
        *((_DWORD *)Context + 2),
        *((_QWORD *)Context + 6),
        0);
    }
    if ( Context[84] )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(64, 32, 1130654024);
      if ( Pool2 )
      {
        WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)Context + 6));
        Pool2[2] = WorkItem;
        if ( WorkItem )
        {
          Pool2[1] = Context;
          *Pool2 = 0;
          v18 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(Context + 16), Pool2, File, 1u, 0x20u);
          v19 = (struct _IO_WORKITEM *)Pool2[2];
          if ( v18 < 0 )
          {
            IoFreeWorkItem(v19);
            ExFreePoolWithTag(Pool2, 0);
          }
          else
          {
            IoQueueWorkItem(v19, HidpCreateRemoteWakeIrpWorker, DelayedWorkQueue, Pool2);
          }
        }
        else
        {
          ExFreePoolWithTag(Pool2, 0);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
          {
            v8 = 0;
          }
          LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v17 = *((_QWORD *)Context + 8);
            v23 = *((_QWORD *)Context + 6);
            v22 = *((_DWORD *)Context + 2);
            v21 = *(_QWORD *)(v17 + 32);
            v20 = 11;
LABEL_38:
            LOBYTE(v17) = v8;
            WPP_RECORDER_AND_TRACE_SF_qdq(
              v16->AttachedDevice,
              v17,
              v14,
              *(_QWORD *)(v5 + 704),
              3,
              7,
              v20,
              (__int64)WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids,
              v21,
              v22,
              v23);
          }
        }
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
        {
          v8 = 0;
        }
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = *((_QWORD *)Context + 8);
          v23 = *((_QWORD *)Context + 6);
          v22 = *((_DWORD *)Context + 2);
          v21 = *(_QWORD *)(v17 + 32);
          v20 = 12;
          goto LABEL_38;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001ccc0  push    rbx
0x18001ccc2  push    rbp
0x18001ccc3  push    rsi
0x18001ccc4  push    rdi
0x18001ccc5  push    r12
0x18001ccc7  push    r14
0x18001ccc9  sub     rsp, 68h
0x18001cccd  mov     rbp, [r9+40h]
0x18001ccd1  xor     r14d, r14d
0x18001ccd4  mov     rcx, [rsp+98h+IoStatus]
0x18001ccdc  mov     eax, r14d
0x18001ccdf  xchg    rax, [r9+60h]
0x18001cce3  mov     eax, r14d
0x18001cce6  mov     rbx, r9
0x18001cce9  xchg    eax, [r9+68h]
0x18001cced  mov     eax, [rcx]
0x18001ccef  cmp     eax, 80000011h
0x18001ccf4  jz      loc_18001CFAE
0x18001ccfa  cmp     eax, 0C0000120h
0x18001ccff  jz      loc_18001CFAE
0x18001cd05  cmp     eax, 0C0000184h
0x18001cd0a  jz      loc_18001CFAE
0x18001cd10  cmp     eax, 0C00002D3h
0x18001cd15  jz      loc_18001CFAE
0x18001cd1b  cmp     eax, 0C0140021h
0x18001cd20  jz      loc_18001CFAE
0x18001cd26  test    eax, eax
0x18001cd28  jz      short loc_18001CD39
0x18001cd2a  xor     edx, edx
0x18001cd2c  mov     rcx, rbx
0x18001cd2f  call    HidpToggleRemoteWake
0x18001cd34  jmp     loc_18001CFAE
0x18001cd39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd40  lea     r12, WPP_GLOBAL_Control
0x18001cd47  mov     esi, 1
0x18001cd4c  cmp     rcx, r12
0x18001cd4f  jz      short loc_18001CD61
0x18001cd51  mov     eax, [rcx+2Ch]
0x18001cd54  test    al, 40h
0x18001cd56  jz      short loc_18001CD61
0x18001cd58  cmp     byte ptr [rcx+29h], 5
0x18001cd5c  mov     r10b, sil
0x18001cd5f  jnb     short loc_18001CD64
0x18001cd61  mov     r10b, r14b
0x18001cd64  lea     rax, WPP_RECORDER_INITIALIZED
0x18001cd6b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001cd72  jz      short loc_18001CD7E
0x18001cd74  mov     dl, sil
0x18001cd77  cmp     [rcx+48h], r14w
0x18001cd7c  jnz     short loc_18001CD81
0x18001cd7e  mov     dl, r14b
0x18001cd81  lea     r11, WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids
0x18001cd88  test    r10b, r10b
0x18001cd8b  jnz     short loc_18001CD91
0x18001cd8d  test    dl, dl
0x18001cd8f  jz      short loc_18001CDE3
0x18001cd91  mov     rax, [r9+30h]
0x18001cd95  mov     r8, [r9+40h]
0x18001cd99  mov     rcx, [rcx+18h]
0x18001cd9d  mov     [rsp+98h+var_40], r14d
0x18001cda2  mov     [rsp+98h+var_48], rax
0x18001cda7  mov     eax, [r9+8]
0x18001cdab  mov     r9, [rbp+2C0h]
0x18001cdb2  mov     [rsp+98h+var_50], eax
0x18001cdb6  mov     rax, [r8+20h]
0x18001cdba  mov     r8b, dl
0x18001cdbd  mov     [rsp+98h+var_58], rax
0x18001cdc2  mov     dl, r10b
0x18001cdc5  mov     [rsp+98h+var_60], r11
0x18001cdca  mov     [rsp+98h+var_68], 0Ah
0x18001cdd1  mov     [rsp+98h+var_70], 7
0x18001cdd9  mov     byte ptr [rsp+98h+RemlockSize], 5
0x18001cdde  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x18001cde3  cmp     [rbx+54h], r14b
0x18001cde7  jz      loc_18001CFAE
0x18001cded  mov     edx, 20h ; ' '
0x18001cdf2  mov     r8d, 43646948h
0x18001cdf8  lea     ecx, [rdx+20h]
0x18001cdfb  call    cs:__imp_ExAllocatePool2
0x18001ce02  nop     dword ptr [rax+rax+00h]
0x18001ce07  mov     rdi, rax
0x18001ce0a  test    rax, rax
0x18001ce0d  jz      loc_18001CF26
0x18001ce13  mov     rcx, [rbx+30h]; DeviceObject
0x18001ce17  call    cs:__imp_IoAllocateWorkItem
0x18001ce1e  nop     dword ptr [rax+rax+00h]
0x18001ce23  mov     [rdi+10h], rax
0x18001ce27  test    rax, rax
0x18001ce2a  jnz     loc_18001CEB2
0x18001ce30  xor     edx, edx; Tag
0x18001ce32  mov     rcx, rdi; P
0x18001ce35  call    cs:__imp_ExFreePoolWithTag
0x18001ce3c  nop     dword ptr [rax+rax+00h]
0x18001ce41  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce48  cmp     rcx, r12
0x18001ce4b  jz      short loc_18001CE5A
0x18001ce4d  mov     eax, [rcx+2Ch]
0x18001ce50  test    al, 40h
0x18001ce52  jz      short loc_18001CE5A
0x18001ce54  cmp     byte ptr [rcx+29h], 3
0x18001ce58  jnb     short loc_18001CE5D
0x18001ce5a  mov     sil, r14b
0x18001ce5d  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ce64  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ce6b  setnz   r8b
0x18001ce6f  test    sil, sil
0x18001ce72  jnz     short loc_18001CE7D
0x18001ce74  test    r8b, r8b
0x18001ce77  jz      loc_18001CFAE
0x18001ce7d  mov     rax, [rbx+30h]
0x18001ce81  mov     rdx, [rbx+40h]
0x18001ce85  mov     [rsp+98h+var_48], rax
0x18001ce8a  mov     eax, [rbx+8]
0x18001ce8d  mov     [rsp+98h+var_50], eax
0x18001ce91  mov     rax, [rdx+20h]
0x18001ce95  mov     [rsp+98h+var_58], rax
0x18001ce9a  lea     rax, WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids
0x18001cea1  mov     [rsp+98h+var_60], rax
0x18001cea6  mov     [rsp+98h+var_68], 0Bh
0x18001cead  jmp     loc_18001CF8E
0x18001ceb2  lea     rcx, [rbx+10h]; RemoveLock
0x18001ceb6  mov     [rdi+8], rbx
0x18001ceba  mov     r9d, esi; Line
0x18001cebd  mov     [rdi], r14
0x18001cec0  lea     r8, File; File
0x18001cec7  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x18001cecf  mov     rdx, rdi; Tag
0x18001ced2  call    cs:__imp_IoAcquireRemoveLockEx
0x18001ced9  nop     dword ptr [rax+rax+00h]
0x18001cede  mov     rcx, [rdi+10h]; IoWorkItem
0x18001cee2  test    eax, eax
0x18001cee4  js      short loc_18001CF04
0x18001cee6  mov     r9, rdi; Context
0x18001cee9  lea     rdx, HidpCreateRemoteWakeIrpWorker; WorkerRoutine
0x18001cef0  mov     r8d, esi; QueueType
0x18001cef3  call    cs:__imp_IoQueueWorkItem
0x18001cefa  nop     dword ptr [rax+rax+00h]
0x18001ceff  jmp     loc_18001CFAE
0x18001cf04  call    cs:__imp_IoFreeWorkItem
0x18001cf0b  nop     dword ptr [rax+rax+00h]
0x18001cf10  xor     edx, edx; Tag
0x18001cf12  mov     rcx, rdi; P
0x18001cf15  call    cs:__imp_ExFreePoolWithTag
0x18001cf1c  nop     dword ptr [rax+rax+00h]
0x18001cf21  jmp     loc_18001CFAE
0x18001cf26  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf2d  cmp     rcx, r12
0x18001cf30  jz      short loc_18001CF3F
0x18001cf32  mov     eax, [rcx+2Ch]
0x18001cf35  test    al, 40h
0x18001cf37  jz      short loc_18001CF3F
0x18001cf39  cmp     byte ptr [rcx+29h], 3
0x18001cf3d  jnb     short loc_18001CF42
0x18001cf3f  mov     sil, r14b
0x18001cf42  lea     rax, WPP_RECORDER_INITIALIZED
0x18001cf49  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001cf50  setnz   r8b
0x18001cf54  test    sil, sil
0x18001cf57  jnz     short loc_18001CF5E
0x18001cf59  test    r8b, r8b
0x18001cf5c  jz      short loc_18001CFAE
0x18001cf5e  mov     rax, [rbx+30h]
0x18001cf62  mov     rdx, [rbx+40h]
0x18001cf66  mov     [rsp+98h+var_48], rax
0x18001cf6b  mov     eax, [rbx+8]
0x18001cf6e  mov     [rsp+98h+var_50], eax
0x18001cf72  mov     rax, [rdx+20h]
0x18001cf76  mov     [rsp+98h+var_58], rax
0x18001cf7b  lea     rax, WPP_dd13b2c258423fde134ba0212f7c41a6_Traceguids
0x18001cf82  mov     [rsp+98h+var_60], rax
0x18001cf87  mov     [rsp+98h+var_68], 0Ch
0x18001cf8e  mov     r9, [rbp+2C0h]
0x18001cf95  mov     dl, sil
0x18001cf98  mov     rcx, [rcx+18h]
0x18001cf9c  mov     [rsp+98h+var_70], 7
0x18001cfa4  mov     byte ptr [rsp+98h+RemlockSize], 3
0x18001cfa9  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x18001cfae  add     rsp, 68h
0x18001cfb2  pop     r14
0x18001cfb4  pop     r12
0x18001cfb6  pop     rdi
0x18001cfb7  pop     rsi
0x18001cfb8  pop     rbp
0x18001cfb9  pop     rbx
0x18001cfba  retn
```
