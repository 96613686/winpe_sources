# PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)

- ea: `0x14000a014`
- end: `0x14000a0f6`
- name: `?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z`
- size: `226`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, const char *)`
- caller_count: `14`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005b2c`
- `0x1400068b0`
- `0x1400070e0`
- `0x1400071b8`
- `0x1400072cc`
- `0x14000743c`
- `0x14000ab3c`
- `0x14000ada0`
- `0x14000b07c`
- `0x14000bda4`
- `0x14000beb4`
- `0x14000c730`
- `0x14000dbd0`
- `0x14000e398`

## callees

- `0x140003674`
- `0x14000a014`
- `0x14000ae88`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000a06f`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000a06f`
- `ntoskrnl!KeClearEvent` at `0x14000a088`
- `ntoskrnl!KeClearEvent` at `0x14000a088`
- `ntoskrnl!IoQueueWorkItem` at `0x14000a0af`
- `ntoskrnl!IoQueueWorkItem` at `0x14000a0af`

## pseudocode

```c
__int64 __fastcall PmQueueNotificationWorkItem(struct _DEVICE_EXTENSION *a1, const char *a2, int a3)
{
  NTSTATUS v3; // edi
  struct _IO_WORKITEM *v6; // rcx

  v3 = 0;
  if ( !*((_BYTE *)a1 + 816) )
  {
    if ( (ScReadNoFence((unsigned int *)a1 + 129) & 2) != 0 )
    {
      v3 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)((char *)a1 + 120), *((PVOID *)a1 + 106), File, 1u, 0x20u);
      if ( v3 >= 0 )
      {
        KeClearEvent((PRKEVENT)((char *)a1 + 824));
        v6 = (struct _IO_WORKITEM *)*((_QWORD *)a1 + 106);
        *((_BYTE *)a1 + 816) = 1;
        IoQueueWorkItem(v6, (PIO_WORKITEM_ROUTINE)PmNotificationWorkItem, CriticalWorkQueue, 0);
      }
    }
    else
    {
      v3 = -1073741661;
    }
  }
  if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0qdds_EtwWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      a3,
      *((_DWORD *)a1 + 42),
      *((_DWORD *)a1 + 129),
      v3,
      (__int64)a2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000a014  mov     [rsp+arg_0], rbx
0x14000a019  mov     [rsp+arg_8], rsi
0x14000a01e  push    rdi
0x14000a01f  sub     rsp, 40h
0x14000a023  xor     edi, edi
0x14000a025  mov     rsi, rdx
0x14000a028  mov     rbx, rcx
0x14000a02b  cmp     [rcx+330h], dil
0x14000a032  jnz     loc_14000A0BB
0x14000a038  add     rcx, 204h; unsigned int *
0x14000a03f  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x14000a044  test    al, 2
0x14000a046  jnz     short loc_14000A04F
0x14000a048  mov     edi, 0C00000A3h
0x14000a04d  jmp     short loc_14000A0BB
0x14000a04f  mov     rdx, [rbx+350h]; Tag
0x14000a056  lea     rcx, [rbx+78h]; RemoveLock
0x14000a05a  mov     r9d, 1; Line
0x14000a060  mov     [rsp+48h+RemlockSize], 20h ; ' '; RemlockSize
0x14000a068  lea     r8, File; File
0x14000a06f  call    cs:__imp_IoAcquireRemoveLockEx
0x14000a076  nop     dword ptr [rax+rax+00h]
0x14000a07b  mov     edi, eax
0x14000a07d  test    eax, eax
0x14000a07f  js      short loc_14000A0BB
0x14000a081  lea     rcx, [rbx+338h]; Event
0x14000a088  call    cs:__imp_KeClearEvent
0x14000a08f  nop     dword ptr [rax+rax+00h]
0x14000a094  mov     rcx, [rbx+350h]; IoWorkItem
0x14000a09b  lea     rdx, ?PmNotificationWorkItem@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x14000a0a2  xor     r9d, r9d; Context
0x14000a0a5  mov     byte ptr [rbx+330h], 1
0x14000a0ac  xor     r8d, r8d; QueueType
0x14000a0af  call    cs:__imp_IoQueueWorkItem
0x14000a0b6  nop     dword ptr [rax+rax+00h]
0x14000a0bb  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x14000a0c2  jz      short loc_14000A0E3
0x14000a0c4  mov     eax, [rbx+204h]
0x14000a0ca  mov     r9d, [rbx+0A8h]
0x14000a0d1  mov     [rsp+48h+var_18], rsi
0x14000a0d6  mov     [rsp+48h+var_20], edi
0x14000a0da  mov     [rsp+48h+RemlockSize], eax
0x14000a0de  call    McTemplateK0qdds_EtwWriteTransfer
0x14000a0e3  mov     rbx, [rsp+48h+arg_0]
0x14000a0e8  mov     eax, edi
0x14000a0ea  mov     rsi, [rsp+48h+arg_8]
0x14000a0ef  add     rsp, 40h
0x14000a0f3  pop     rdi
0x14000a0f4  retn
```
