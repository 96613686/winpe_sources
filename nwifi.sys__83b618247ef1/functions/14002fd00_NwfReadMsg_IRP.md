# NwfReadMsg(_IRP *)

- ea: `0x14002fd00`
- end: `0x14002fe90`
- name: `?NwfReadMsg@@YAJPEAU_IRP@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400ba270`

## callees

- `0x14000d22c`
- `0x14002fd00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fd67`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fd67`
- `ntoskrnl!IofCompleteRequest` at `0x14002fe78`
- `ntoskrnl!IofCompleteRequest` at `0x14002fe78`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002fdea`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14002fdea`
- `NDIS!NdisReleaseRWLock` at `0x14002fe1b`
- `NDIS!NdisReleaseRWLock` at `0x14002fe64`
- `NDIS!NdisReleaseRWLock` at `0x14002fe1b`
- `NDIS!NdisReleaseRWLock` at `0x14002fe64`
- `NDIS!NdisAcquireRWLockRead` at `0x14002fdb8`
- `NDIS!NdisAcquireRWLockRead` at `0x14002fdb8`

## pseudocode

```c
__int64 __fastcall NwfReadMsg(PIRP Irp)
{
  _FILE_OBJECT *FileObject; // rbp
  char *FsContext; // rbx
  _MDL *MdlAddress; // rcx
  unsigned int Status; // ebx
  PVOID MappedSystemVa; // rax
  __int64 v7; // rsi
  NTSTATUS inserted; // eax
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  FileObject = Irp->Tail.Overlay.CurrentStackLocation->FileObject;
  FsContext = (char *)FileObject->FsContext;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  MdlAddress = Irp->MdlAddress;
  LockState.OldIrql = 0;
  *(_WORD *)&LockState.LockState = 0;
  if ( !MdlAddress || MdlAddress->Next )
  {
    Status = -1073741811;
  }
  else
  {
    if ( (MdlAddress->MdlFlags & 5) != 0 )
      MappedSystemVa = MdlAddress->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    if ( MappedSystemVa )
    {
      if ( ((__int64)Irp->MdlAddress->MappedSystemVa & 3) != 0 )
      {
        Status = -2147483646;
      }
      else if ( FsContext )
      {
        v7 = *((_QWORD *)FsContext + 2);
        NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState, 0);
        if ( *(_FILE_OBJECT **)(v7 + 5880) == FileObject || *(_FILE_OBJECT **)(v7 + 5872) == FileObject )
        {
          inserted = IoCsqInsertIrpEx((PIO_CSQ)(FsContext + 40), Irp, 0, 0);
          Status = inserted;
          switch ( inserted )
          {
            case -1073741802:
              Status = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d79e04fe7ab43cb3fdea0d83dcb69abf_Traceguids);
              break;
            case -1073741789:
              Status = Irp->IoStatus.Status;
              break;
            case 259:
              NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
              return 259;
          }
        }
        else
        {
          Status = -1073741808;
        }
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v7 + 144), &LockState);
      }
      else
      {
        Status = -1073741808;
      }
    }
    else
    {
      Status = -1073741670;
    }
  }
  Irp->IoStatus.Status = Status;
  IofCompleteRequest(Irp, 2);
  return Status;
}

```

## disassembly

```asm
0x14002fd00  push    rbx
0x14002fd02  push    rbp
0x14002fd03  push    rsi
0x14002fd04  push    rdi
0x14002fd05  sub     rsp, 38h
0x14002fd09  mov     rax, [rcx+0B8h]
0x14002fd10  mov     rdi, rcx
0x14002fd13  mov     rbp, [rax+30h]
0x14002fd17  xor     eax, eax
0x14002fd19  mov     rbx, [rbp+18h]
0x14002fd1d  mov     [rcx+30h], eax
0x14002fd20  mov     [rcx+38h], rax
0x14002fd24  mov     rcx, [rcx+8]; MemoryDescriptorList
0x14002fd28  mov     [rsp+58h+LockState.OldIrql], 0
0x14002fd2d  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14002fd32  test    rcx, rcx
0x14002fd35  jnz     short loc_14002FD41
0x14002fd37  mov     ebx, 0C000000Dh
0x14002fd3c  jmp     loc_14002FE70
0x14002fd41  cmp     [rcx], rax
0x14002fd44  jnz     short loc_14002FD37
0x14002fd46  test    byte ptr [rcx+0Ah], 5
0x14002fd4a  jz      short loc_14002FD52
0x14002fd4c  mov     rax, [rcx+18h]
0x14002fd50  jmp     short loc_14002FD73
0x14002fd52  xor     r9d, r9d; RequestedAddress
0x14002fd55  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002fd5d  xor     edx, edx; AccessMode
0x14002fd5f  mov     [rsp+58h+BugCheckOnFailure], eax; BugCheckOnFailure
0x14002fd63  lea     r8d, [r9+1]; CacheType
0x14002fd67  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002fd6e  nop     dword ptr [rax+rax+00h]
0x14002fd73  test    rax, rax
0x14002fd76  jnz     short loc_14002FD82
0x14002fd78  mov     ebx, 0C000009Ah
0x14002fd7d  jmp     loc_14002FE70
0x14002fd82  mov     rax, [rdi+8]
0x14002fd86  test    byte ptr [rax+18h], 3
0x14002fd8a  jz      short loc_14002FD96
0x14002fd8c  mov     ebx, 80000002h
0x14002fd91  jmp     loc_14002FE70
0x14002fd96  test    rbx, rbx
0x14002fd99  jnz     short loc_14002FDA5
0x14002fd9b  mov     ebx, 0C0000010h
0x14002fda0  jmp     loc_14002FE70
0x14002fda5  mov     rsi, [rbx+10h]
0x14002fda9  lea     rdx, [rsp+58h+LockState]; LockState
0x14002fdae  xor     r8d, r8d; Flags
0x14002fdb1  mov     rcx, [rsi+90h]; Lock
0x14002fdb8  call    cs:__imp_NdisAcquireRWLockRead
0x14002fdbf  nop     dword ptr [rax+rax+00h]
0x14002fdc4  cmp     [rsi+16F8h], rbp
0x14002fdcb  jz      short loc_14002FDDD
0x14002fdcd  cmp     [rsi+16F0h], rbp
0x14002fdd4  jz      short loc_14002FDDD
0x14002fdd6  mov     ebx, 0C0000010h
0x14002fddb  jmp     short loc_14002FE58
0x14002fddd  lea     rcx, [rbx+28h]; Csq
0x14002fde1  xor     r9d, r9d; InsertContext
0x14002fde4  xor     r8d, r8d; Context
0x14002fde7  mov     rdx, rdi; Irp
0x14002fdea  call    cs:__imp_IoCsqInsertIrpEx
0x14002fdf1  nop     dword ptr [rax+rax+00h]
0x14002fdf6  mov     ebx, eax
0x14002fdf8  cmp     eax, 0C0000016h
0x14002fdfd  jz      short loc_14002FE30
0x14002fdff  cmp     eax, 0C0000023h
0x14002fe04  jz      short loc_14002FE2B
0x14002fe06  mov     ebp, 103h
0x14002fe0b  cmp     eax, ebp
0x14002fe0d  jnz     short loc_14002FE58
0x14002fe0f  mov     rcx, [rsi+90h]; Lock
0x14002fe16  lea     rdx, [rsp+58h+LockState]; LockState
0x14002fe1b  call    cs:__imp_NdisReleaseRWLock
0x14002fe22  nop     dword ptr [rax+rax+00h]
0x14002fe27  mov     eax, ebp
0x14002fe29  jmp     short loc_14002FE86
0x14002fe2b  mov     ebx, [rdi+30h]
0x14002fe2e  jmp     short loc_14002FE58
0x14002fe30  xor     ebx, ebx
0x14002fe32  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe39  lea     rax, WPP_GLOBAL_Control
0x14002fe40  cmp     rcx, rax
0x14002fe43  jz      short loc_14002FE58
0x14002fe45  mov     rcx, [rcx+18h]
0x14002fe49  lea     edx, [rbx+0Bh]
0x14002fe4c  lea     r8, WPP_d79e04fe7ab43cb3fdea0d83dcb69abf_Traceguids
0x14002fe53  call    WPP_SF_
0x14002fe58  mov     rcx, [rsi+90h]; Lock
0x14002fe5f  lea     rdx, [rsp+58h+LockState]; LockState
0x14002fe64  call    cs:__imp_NdisReleaseRWLock
0x14002fe6b  nop     dword ptr [rax+rax+00h]
0x14002fe70  mov     dl, 2; PriorityBoost
0x14002fe72  mov     [rdi+30h], ebx
0x14002fe75  mov     rcx, rdi; Irp
0x14002fe78  call    cs:__imp_IofCompleteRequest
0x14002fe7f  nop     dword ptr [rax+rax+00h]
0x14002fe84  mov     eax, ebx
0x14002fe86  add     rsp, 38h
0x14002fe8a  pop     rdi
0x14002fe8b  pop     rsi
0x14002fe8c  pop     rbp
0x14002fe8d  pop     rbx
0x14002fe8e  retn
```
