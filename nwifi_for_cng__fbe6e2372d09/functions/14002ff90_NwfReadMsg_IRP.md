# NwfReadMsg(_IRP *)

- ea: `0x14002ff90`
- end: `0x140030120`
- name: `?NwfReadMsg@@YAJPEAU_IRP@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400bd220`

## callees

- `0x14000d21c`
- `0x14002ff90`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fff7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002fff7`
- `ntoskrnl!IofCompleteRequest` at `0x140030108`
- `ntoskrnl!IofCompleteRequest` at `0x140030108`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14003007a`
- `ntoskrnl!IoCsqInsertIrpEx` at `0x14003007a`
- `NDIS!NdisReleaseRWLock` at `0x1400300ab`
- `NDIS!NdisReleaseRWLock` at `0x1400300f4`
- `NDIS!NdisReleaseRWLock` at `0x1400300ab`
- `NDIS!NdisReleaseRWLock` at `0x1400300f4`
- `NDIS!NdisAcquireRWLockRead` at `0x140030048`
- `NDIS!NdisAcquireRWLockRead` at `0x140030048`

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
0x14002ff90  push    rbx
0x14002ff92  push    rbp
0x14002ff93  push    rsi
0x14002ff94  push    rdi
0x14002ff95  sub     rsp, 38h
0x14002ff99  mov     rax, [rcx+0B8h]
0x14002ffa0  mov     rdi, rcx
0x14002ffa3  mov     rbp, [rax+30h]
0x14002ffa7  xor     eax, eax
0x14002ffa9  mov     rbx, [rbp+18h]
0x14002ffad  mov     [rcx+30h], eax
0x14002ffb0  mov     [rcx+38h], rax
0x14002ffb4  mov     rcx, [rcx+8]; MemoryDescriptorList
0x14002ffb8  mov     [rsp+58h+LockState.OldIrql], 0
0x14002ffbd  mov     word ptr [rsp+58h+LockState.LockState], ax
0x14002ffc2  test    rcx, rcx
0x14002ffc5  jnz     short loc_14002FFD1
0x14002ffc7  mov     ebx, 0C000000Dh
0x14002ffcc  jmp     loc_140030100
0x14002ffd1  cmp     [rcx], rax
0x14002ffd4  jnz     short loc_14002FFC7
0x14002ffd6  test    byte ptr [rcx+0Ah], 5
0x14002ffda  jz      short loc_14002FFE2
0x14002ffdc  mov     rax, [rcx+18h]
0x14002ffe0  jmp     short loc_140030003
0x14002ffe2  xor     r9d, r9d; RequestedAddress
0x14002ffe5  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002ffed  xor     edx, edx; AccessMode
0x14002ffef  mov     [rsp+58h+BugCheckOnFailure], eax; BugCheckOnFailure
0x14002fff3  lea     r8d, [r9+1]; CacheType
0x14002fff7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002fffe  nop     dword ptr [rax+rax+00h]
0x140030003  test    rax, rax
0x140030006  jnz     short loc_140030012
0x140030008  mov     ebx, 0C000009Ah
0x14003000d  jmp     loc_140030100
0x140030012  mov     rax, [rdi+8]
0x140030016  test    byte ptr [rax+18h], 3
0x14003001a  jz      short loc_140030026
0x14003001c  mov     ebx, 80000002h
0x140030021  jmp     loc_140030100
0x140030026  test    rbx, rbx
0x140030029  jnz     short loc_140030035
0x14003002b  mov     ebx, 0C0000010h
0x140030030  jmp     loc_140030100
0x140030035  mov     rsi, [rbx+10h]
0x140030039  lea     rdx, [rsp+58h+LockState]; LockState
0x14003003e  xor     r8d, r8d; Flags
0x140030041  mov     rcx, [rsi+90h]; Lock
0x140030048  call    cs:__imp_NdisAcquireRWLockRead
0x14003004f  nop     dword ptr [rax+rax+00h]
0x140030054  cmp     [rsi+16F8h], rbp
0x14003005b  jz      short loc_14003006D
0x14003005d  cmp     [rsi+16F0h], rbp
0x140030064  jz      short loc_14003006D
0x140030066  mov     ebx, 0C0000010h
0x14003006b  jmp     short loc_1400300E8
0x14003006d  lea     rcx, [rbx+28h]; Csq
0x140030071  xor     r9d, r9d; InsertContext
0x140030074  xor     r8d, r8d; Context
0x140030077  mov     rdx, rdi; Irp
0x14003007a  call    cs:__imp_IoCsqInsertIrpEx
0x140030081  nop     dword ptr [rax+rax+00h]
0x140030086  mov     ebx, eax
0x140030088  cmp     eax, 0C0000016h
0x14003008d  jz      short loc_1400300C0
0x14003008f  cmp     eax, 0C0000023h
0x140030094  jz      short loc_1400300BB
0x140030096  mov     ebp, 103h
0x14003009b  cmp     eax, ebp
0x14003009d  jnz     short loc_1400300E8
0x14003009f  mov     rcx, [rsi+90h]; Lock
0x1400300a6  lea     rdx, [rsp+58h+LockState]; LockState
0x1400300ab  call    cs:__imp_NdisReleaseRWLock
0x1400300b2  nop     dword ptr [rax+rax+00h]
0x1400300b7  mov     eax, ebp
0x1400300b9  jmp     short loc_140030116
0x1400300bb  mov     ebx, [rdi+30h]
0x1400300be  jmp     short loc_1400300E8
0x1400300c0  xor     ebx, ebx
0x1400300c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400300c9  lea     rax, WPP_GLOBAL_Control
0x1400300d0  cmp     rcx, rax
0x1400300d3  jz      short loc_1400300E8
0x1400300d5  mov     rcx, [rcx+18h]
0x1400300d9  lea     edx, [rbx+0Bh]
0x1400300dc  lea     r8, WPP_d79e04fe7ab43cb3fdea0d83dcb69abf_Traceguids
0x1400300e3  call    WPP_SF_
0x1400300e8  mov     rcx, [rsi+90h]; Lock
0x1400300ef  lea     rdx, [rsp+58h+LockState]; LockState
0x1400300f4  call    cs:__imp_NdisReleaseRWLock
0x1400300fb  nop     dword ptr [rax+rax+00h]
0x140030100  mov     dl, 2; PriorityBoost
0x140030102  mov     [rdi+30h], ebx
0x140030105  mov     rcx, rdi; Irp
0x140030108  call    cs:__imp_IofCompleteRequest
0x14003010f  nop     dword ptr [rax+rax+00h]
0x140030114  mov     eax, ebx
0x140030116  add     rsp, 38h
0x14003011a  pop     rdi
0x14003011b  pop     rsi
0x14003011c  pop     rbp
0x14003011d  pop     rbx
0x14003011e  retn
```
