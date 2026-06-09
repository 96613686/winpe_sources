# lldpDeletePort

- ea: `0x140010aec`
- end: `0x140010c34`
- name: `lldpDeletePort`
- size: `328`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140010150`
- `0x140010530`
- `0x140010560`
- `0x140012640`

## callees

- `0x140003d80`
- `0x140003e30`
- `0x1400044f4`
- `0x140004510`
- `0x140004a90`
- `0x140010aec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010bd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c21`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140010b3a`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140010b3a`
- `NDIS!NdisFreeRWLock` at `0x140010b90`
- `NDIS!NdisFreeRWLock` at `0x140010bb3`
- `NDIS!NdisFreeRWLock` at `0x140010b90`
- `NDIS!NdisFreeRWLock` at `0x140010bb3`

## pseudocode

```c
void __fastcall lldpDeletePort(char *Context)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  struct _NDIS_RW_LOCK_EX *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  if ( Context[150] )
  {
    lldpRemovePortFromDriver();
    Context[150] = 0;
  }
  lldpCancelTimer(Context + 312);
  lldpCancelTimer(Context + 448);
  lldpCancelTimer(Context + 584);
  lldpCancelTimer(Context + 720);
  KeFlushQueuedDpcs();
  if ( (unsigned __int8)lldpPortStateIsVisibleToClients((unsigned int)_InterlockedExchange(
                                                                        (volatile __int32 *)Context + 13,
                                                                        8)) )
    lldpQueueChangeNotificationEx(Context);
  if ( *((_QWORD *)Context + 121) )
  {
    lldpDeleteNeighborOnPort(Context);
    *((_QWORD *)Context + 121) = 0;
  }
  v2 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)Context + 122);
  if ( v2 )
  {
    NdisFreeRWLock(v2);
    *((_QWORD *)Context + 122) = 0;
  }
  v3 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)Context + 120);
  if ( v3 )
  {
    NdisFreeRWLock(v3);
    *((_QWORD *)Context + 120) = 0;
  }
  v4 = (void *)*((_QWORD *)Context + 13);
  if ( v4 )
    ExFreePoolWithTag(v4, 0x50444C4Cu);
  v5 = (void *)*((_QWORD *)Context + 119);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x50444C4Cu);
    *((_QWORD *)Context + 119) = 0;
    *((_DWORD *)Context + 236) = 0;
  }
  *Context = 0;
  ExFreePoolWithTag(Context, 0x50444C4Cu);
}

```

## disassembly

```asm
0x140010aec  push    rbx
0x140010aee  sub     rsp, 20h
0x140010af2  cmp     byte ptr [rcx+96h], 0
0x140010af9  mov     rbx, rcx
0x140010afc  jz      short loc_140010B0A
0x140010afe  call    lldpRemovePortFromDriver
0x140010b03  mov     byte ptr [rbx+96h], 0
0x140010b0a  lea     rcx, [rbx+138h]
0x140010b11  call    lldpCancelTimer
0x140010b16  lea     rcx, [rbx+1C0h]
0x140010b1d  call    lldpCancelTimer
0x140010b22  lea     rcx, [rbx+248h]
0x140010b29  call    lldpCancelTimer
0x140010b2e  lea     rcx, [rbx+2D0h]
0x140010b35  call    lldpCancelTimer
0x140010b3a  call    cs:__imp_KeFlushQueuedDpcs
0x140010b41  nop     dword ptr [rax+rax+00h]
0x140010b46  mov     ecx, 8
0x140010b4b  xchg    ecx, [rbx+34h]
0x140010b4e  call    lldpPortStateIsVisibleToClients
0x140010b53  test    al, al
0x140010b55  jz      short loc_140010B67
0x140010b57  xor     edx, edx
0x140010b59  mov     r8d, 80000000h
0x140010b5f  mov     rcx, rbx; Context
0x140010b62  call    lldpQueueChangeNotificationEx
0x140010b67  cmp     qword ptr [rbx+3C8h], 0
0x140010b6f  jz      short loc_140010B84
0x140010b71  mov     rcx, rbx
0x140010b74  call    lldpDeleteNeighborOnPort
0x140010b79  mov     qword ptr [rbx+3C8h], 0
0x140010b84  mov     rcx, [rbx+3D0h]; Lock
0x140010b8b  test    rcx, rcx
0x140010b8e  jz      short loc_140010BA7
0x140010b90  call    cs:__imp_NdisFreeRWLock
0x140010b97  nop     dword ptr [rax+rax+00h]
0x140010b9c  mov     qword ptr [rbx+3D0h], 0
0x140010ba7  mov     rcx, [rbx+3C0h]; Lock
0x140010bae  test    rcx, rcx
0x140010bb1  jz      short loc_140010BCA
0x140010bb3  call    cs:__imp_NdisFreeRWLock
0x140010bba  nop     dword ptr [rax+rax+00h]
0x140010bbf  mov     qword ptr [rbx+3C0h], 0
0x140010bca  mov     rcx, [rbx+68h]; P
0x140010bce  test    rcx, rcx
0x140010bd1  jz      short loc_140010BE4
0x140010bd3  mov     edx, 50444C4Ch; Tag
0x140010bd8  call    cs:__imp_ExFreePoolWithTag
0x140010bdf  nop     dword ptr [rax+rax+00h]
0x140010be4  mov     rcx, [rbx+3B8h]; P
0x140010beb  test    rcx, rcx
0x140010bee  jz      short loc_140010C16
0x140010bf0  mov     edx, 50444C4Ch; Tag
0x140010bf5  call    cs:__imp_ExFreePoolWithTag
0x140010bfc  nop     dword ptr [rax+rax+00h]
0x140010c01  mov     qword ptr [rbx+3B8h], 0
0x140010c0c  mov     dword ptr [rbx+3B0h], 0
0x140010c16  mov     edx, 50444C4Ch; Tag
0x140010c1b  mov     byte ptr [rbx], 0
0x140010c1e  mov     rcx, rbx; P
0x140010c21  call    cs:__imp_ExFreePoolWithTag
0x140010c28  nop     dword ptr [rax+rax+00h]
0x140010c2d  add     rsp, 20h
0x140010c31  pop     rbx
0x140010c32  retn
```
