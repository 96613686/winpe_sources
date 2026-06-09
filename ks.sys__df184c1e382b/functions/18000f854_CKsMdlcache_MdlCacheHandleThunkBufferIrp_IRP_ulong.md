# CKsMdlcache::MdlCacheHandleThunkBufferIrp(_IRP *,ulong)

- ea: `0x18000f854`
- end: `0x18000fb10`
- name: `?MdlCacheHandleThunkBufferIrp@CKsMdlcache@@QEAAJPEAU_IRP@@K@Z`
- size: `700`
- prototype: `__int64 __fastcall(CKsMdlcache *this, struct _IRP *, ULONG)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009c40`
- `0x180009c9c`

## callees

- `0x18000f854`
- `0x180065d20`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x18000f9c1`
- `ntoskrnl!MmUnlockPages` at `0x18000fac4`
- `ntoskrnl!MmUnlockPages` at `0x18000f9c1`
- `ntoskrnl!MmUnlockPages` at `0x18000fac4`
- `ntoskrnl!MmProbeAndLockPages` at `0x18000fa1c`
- `ntoskrnl!MmProbeAndLockPages` at `0x18000fa1c`
- `ntoskrnl!IoAllocateMdl` at `0x18000f918`
- `ntoskrnl!IoAllocateMdl` at `0x18000f972`
- `ntoskrnl!IoAllocateMdl` at `0x18000f918`
- `ntoskrnl!IoAllocateMdl` at `0x18000f972`
- `ntoskrnl!IoFreeMdl` at `0x18000f9d0`
- `ntoskrnl!IoFreeMdl` at `0x18000fad3`
- `ntoskrnl!IoFreeMdl` at `0x18000f9d0`
- `ntoskrnl!IoFreeMdl` at `0x18000fad3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fa61`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fa61`
- `ntoskrnl!ExRaiseStatus` at `0x18000fa77`
- `ntoskrnl!ExRaiseStatus` at `0x18000fa77`

## pseudocode

```c
__int64 __fastcall CKsMdlcache::MdlCacheHandleThunkBufferIrp(CKsMdlcache *this, struct _IRP *a2, ULONG a3)
{
  unsigned int v5; // ebx
  char v6; // r15
  ULONG Length; // r14d
  struct _IRP *UserBuffer; // rdi
  unsigned int Status; // ecx
  unsigned int v10; // r12d
  ULONG Flink; // edx
  struct _LIST_ENTRY *Blink; // rcx
  PVOID v13; // rcx
  ULONG v14; // edx
  __int64 v15; // rax
  PMDL MdlAddress; // rdi
  struct _MDL *Next; // r14
  PMDL i; // rdi

  v5 = 0;
  v6 = 1;
  Length = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( !a2->AssociatedIrp.MasterIrp )
  {
    UserBuffer = (struct _IRP *)a2->UserBuffer;
    a2->AssociatedIrp.MasterIrp = UserBuffer;
    if ( Length >= 0x38 )
    {
      while ( 1 )
      {
        if ( Length < 0x38 )
          goto LABEL_28;
        Status = UserBuffer->IoStatus.Status;
        if ( (Status & 0x18000) == 0x10000 )
          goto LABEL_20;
        if ( (Status & 0x8000) == 0 )
          break;
        if ( (struct _KTHREAD *)a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink != KeGetCurrentThread() )
        {
          v5 = -1073740004;
          goto LABEL_21;
        }
        if ( !UserBuffer->ThreadListEntry.Blink )
          goto LABEL_20;
        v10 = *(_DWORD *)&UserBuffer->Type;
        if ( (Status & 0x10000) != 0 )
        {
          Flink = 4096;
          Blink = 0;
        }
        else
        {
          Flink = (ULONG)UserBuffer->ThreadListEntry.Flink;
          Blink = UserBuffer->ThreadListEntry.Blink;
        }
        if ( !IoAllocateMdl(Blink, Flink, a2->MdlAddress != 0, 1u, a2) )
        {
LABEL_12:
          v5 = -1073741670;
          goto LABEL_21;
        }
        if ( (UserBuffer->IoStatus.Status & 0x1000) != 0 && v10 > 0x80 )
        {
          v13 = UserBuffer->Tail.Overlay.DriverContext[2];
          if ( !v13 || (v14 = *((_DWORD *)&UserBuffer->Tail.CompletionKey + 2)) == 0 )
          {
LABEL_20:
            v5 = -1073741811;
LABEL_21:
            MdlAddress = a2->MdlAddress;
            if ( MdlAddress )
            {
              while ( MdlAddress )
              {
                Next = MdlAddress->Next;
                if ( (MdlAddress->MdlFlags & 2) != 0 )
                  MmUnlockPages(MdlAddress);
                IoFreeMdl(MdlAddress);
                MdlAddress = Next;
              }
              a2->MdlAddress = 0;
            }
            return v5;
          }
          if ( !IoAllocateMdl(v13, v14, 1u, 1u, a2) )
            goto LABEL_12;
        }
        v15 = *(unsigned int *)&UserBuffer->Type;
        UserBuffer = (struct _IRP *)((char *)UserBuffer + v15);
        Length -= v15;
      }
      v6 = 0;
LABEL_28:
      if ( v6 )
      {
        for ( i = a2->MdlAddress; i; i = i->Next )
        {
          if ( i->StartVa )
          {
            MmProbeAndLockPages(i, a2->RequestorMode, IoWriteAccess);
            if ( (a3 & 0x40) != 0 )
            {
              i->MdlFlags |= 0x2000u;
              if ( !((i->MdlFlags & 5) != 0
                   ? i->MappedSystemVa
                   : MmMapLockedPagesSpecifyCache(i, 0, MmCached, 0, 0, 0x40000000u)) )
                ExRaiseStatus(-1073741670);
            }
          }
        }
      }
      else
      {
        return (unsigned int)KsProbeStreamIrp(a2, a3, 0);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000f854  mov     r11, rsp
0x18000f857  mov     [r11+8], rbx
0x18000f85b  mov     [r11+18h], rsi
0x18000f85f  mov     [r11+10h], rdx
0x18000f863  push    rdi
0x18000f864  push    r12
0x18000f866  push    r13
0x18000f868  push    r14
0x18000f86a  push    r15
0x18000f86c  sub     rsp, 40h
0x18000f870  mov     r13d, r8d
0x18000f873  mov     rsi, rdx
0x18000f876  xor     ebx, ebx
0x18000f878  mov     r15b, 1
0x18000f87b  mov     rax, [rdx+0B8h]
0x18000f882  mov     r14d, [rax+8]
0x18000f886  cmp     [rdx+18h], rbx
0x18000f88a  jnz     loc_18000FA9F
0x18000f890  mov     rdi, [rdx+70h]
0x18000f894  mov     [rdx+18h], rdi
0x18000f898  cmp     r14d, 38h ; '8'
0x18000f89c  jb      loc_18000FA9F
0x18000f8a2  mov     [r11-30h], rdi
0x18000f8a6  cmp     r14d, 38h ; '8'
0x18000f8aa  jb      loc_18000F9F1
0x18000f8b0  mov     ecx, [rdi+30h]
0x18000f8b3  mov     eax, ecx
0x18000f8b5  and     eax, 18000h
0x18000f8ba  cmp     eax, 10000h
0x18000f8bf  jz      loc_18000F99A
0x18000f8c5  bt      ecx, 0Fh
0x18000f8c9  jnb     loc_18000F9EE
0x18000f8cf  mov     rax, gs:188h
0x18000f8d8  cmp     [rsi+78h], rax
0x18000f8dc  jz      short loc_18000F8E8
0x18000f8de  mov     ebx, 0C000071Ch
0x18000f8e3  jmp     loc_18000F99F
0x18000f8e8  mov     rax, [rdi+28h]
0x18000f8ec  test    rax, rax
0x18000f8ef  jz      loc_18000F99A
0x18000f8f5  mov     r12d, [rdi]
0x18000f8f8  mov     rdx, [rsi+8]
0x18000f8fc  mov     [rsp+68h+Irp], rsi; Irp
0x18000f901  mov     r9b, 1; ChargeQuota
0x18000f904  bt      ecx, 10h
0x18000f908  jnb     short loc_18000F930
0x18000f90a  test    rdx, rdx
0x18000f90d  setnz   r8b; SecondaryBuffer
0x18000f911  mov     edx, 1000h; Length
0x18000f916  xor     ecx, ecx; VirtualAddress
0x18000f918  call    cs:__imp_IoAllocateMdl
0x18000f91f  nop     dword ptr [rax+rax+00h]
0x18000f924  test    rax, rax
0x18000f927  jnz     short loc_18000F93F
0x18000f929  mov     ebx, 0C000009Ah
0x18000f92e  jmp     short loc_18000F99F
0x18000f930  test    rdx, rdx
0x18000f933  setnz   r8b
0x18000f937  mov     edx, [rdi+20h]
0x18000f93a  mov     rcx, rax
0x18000f93d  jmp     short loc_18000F918
0x18000f93f  test    dword ptr [rdi+30h], 1000h
0x18000f946  jz      short loc_18000F983
0x18000f948  cmp     r12d, 80h
0x18000f94f  jbe     short loc_18000F983
0x18000f951  mov     rcx, [rdi+88h]; VirtualAddress
0x18000f958  test    rcx, rcx
0x18000f95b  jz      short loc_18000F99A
0x18000f95d  mov     edx, [rdi+80h]; Length
0x18000f963  test    edx, edx
0x18000f965  jz      short loc_18000F99A
0x18000f967  mov     [rsp+68h+Irp], rsi; Irp
0x18000f96c  mov     r9b, 1; ChargeQuota
0x18000f96f  mov     r8b, r9b; SecondaryBuffer
0x18000f972  call    cs:__imp_IoAllocateMdl
0x18000f979  nop     dword ptr [rax+rax+00h]
0x18000f97e  test    rax, rax
0x18000f981  jz      short loc_18000F929
0x18000f983  mov     eax, [rdi]
0x18000f985  add     rdi, rax
0x18000f988  mov     [rsp+68h+var_30], rdi
0x18000f98d  sub     r14d, eax
0x18000f990  mov     [rsp+68h+var_34], r14d
0x18000f995  jmp     loc_18000F8A6
0x18000f99a  mov     ebx, 0C000000Dh
0x18000f99f  mov     [rsp+68h+var_38], ebx
0x18000f9a3  mov     rdi, [rsi+8]
0x18000f9a7  test    rdi, rdi
0x18000f9aa  jz      loc_18000FA9F
0x18000f9b0  test    rdi, rdi
0x18000f9b3  jz      short loc_18000F9E1
0x18000f9b5  mov     r14, [rdi]
0x18000f9b8  test    byte ptr [rdi+0Ah], 2
0x18000f9bc  jz      short loc_18000F9CD
0x18000f9be  mov     rcx, rdi; MemoryDescriptorList
0x18000f9c1  call    cs:__imp_MmUnlockPages
0x18000f9c8  nop     dword ptr [rax+rax+00h]
0x18000f9cd  mov     rcx, rdi; Mdl
0x18000f9d0  call    cs:__imp_IoFreeMdl
0x18000f9d7  nop     dword ptr [rax+rax+00h]
0x18000f9dc  mov     rdi, r14
0x18000f9df  jmp     short loc_18000F9B0
0x18000f9e1  mov     qword ptr [rsi+8], 0
0x18000f9e9  jmp     loc_18000FA9F
0x18000f9ee  xor     r15b, r15b
0x18000f9f1  test    r15b, r15b
0x18000f9f4  jz      loc_18000FA8B
0x18000f9fa  mov     rdi, [rsi+8]
0x18000f9fe  test    rdi, rdi
0x18000fa01  jz      loc_18000FA9F
0x18000fa07  cmp     qword ptr [rdi+20h], 0
0x18000fa0c  jnz     short loc_18000FA10
0x18000fa0e  jmp     short loc_18000FA83
0x18000fa10  mov     r8d, 1; Operation
0x18000fa16  mov     dl, [rsi+40h]; AccessMode
0x18000fa19  mov     rcx, rdi; MemoryDescriptorList
0x18000fa1c  call    cs:__imp_MmProbeAndLockPages
0x18000fa23  nop     dword ptr [rax+rax+00h]
0x18000fa28  test    r13b, 40h
0x18000fa2c  jz      short loc_18000FA83
0x18000fa2e  mov     eax, 2000h
0x18000fa33  or      [rdi+0Ah], ax
0x18000fa37  movzx   eax, word ptr [rdi+0Ah]
0x18000fa3b  test    al, 5
0x18000fa3d  jz      short loc_18000FA45
0x18000fa3f  mov     rax, [rdi+18h]
0x18000fa43  jmp     short loc_18000FA6D
0x18000fa45  mov     [rsp+68h+Priority], 40000000h; Priority
0x18000fa4d  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x18000fa55  xor     r9d, r9d; RequestedAddress
0x18000fa58  xor     edx, edx; AccessMode
0x18000fa5a  lea     r8d, [r9+1]; CacheType
0x18000fa5e  mov     rcx, rdi; MemoryDescriptorList
0x18000fa61  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fa68  nop     dword ptr [rax+rax+00h]
0x18000fa6d  test    rax, rax
0x18000fa70  jnz     short loc_18000FA83
0x18000fa72  mov     ecx, 0C000009Ah; Status
0x18000fa77  call    cs:__imp_ExRaiseStatus
0x18000fa83  mov     rdi, [rdi]
0x18000fa86  jmp     loc_18000F9FE
0x18000fa8b  xor     r8d, r8d; HeaderSize
0x18000fa8e  mov     edx, r13d; ProbeFlags
0x18000fa91  mov     rcx, rsi; Irp
0x18000fa94  call    KsProbeStreamIrp
0x18000fa99  mov     ebx, eax
0x18000fa9b  mov     [rsp+68h+var_38], eax
0x18000fa9f  jmp     short loc_18000FAF3
0x18000faa1  mov     ebx, eax
0x18000faa3  mov     rsi, [rsp+68h+arg_8]
0x18000faa8  cmp     qword ptr [rsi+8], 0
0x18000faad  jz      short loc_18000FAEF
0x18000faaf  mov     rdi, [rsi+8]
0x18000fab3  test    rdi, rdi
0x18000fab6  jz      short loc_18000FAE7
0x18000fab8  mov     r14, [rdi]
0x18000fabb  test    byte ptr [rdi+0Ah], 2
0x18000fabf  jz      short loc_18000FAD0
0x18000fac1  mov     rcx, rdi; MemoryDescriptorList
0x18000fac4  call    cs:__imp_MmUnlockPages
0x18000facb  nop     dword ptr [rax+rax+00h]
0x18000fad0  mov     rcx, rdi; Mdl
0x18000fad3  call    cs:__imp_IoFreeMdl
0x18000fada  nop     dword ptr [rax+rax+00h]
0x18000fadf  mov     rdi, r14
0x18000fae2  test    r14, r14
0x18000fae5  jnz     short loc_18000FAB8
0x18000fae7  mov     qword ptr [rsi+8], 0
0x18000faef  mov     [rsp+68h+var_38], ebx
0x18000faf3  mov     eax, ebx
0x18000faf5  lea     r11, [rsp+68h+var_28]
0x18000fafa  mov     rbx, [r11+30h]
0x18000fafe  mov     rsi, [r11+40h]
0x18000fb02  mov     rsp, r11
0x18000fb05  pop     r15
0x18000fb07  pop     r14
0x18000fb09  pop     r13
0x18000fb0b  pop     r12
0x18000fb0d  pop     rdi
0x18000fb0e  retn
```
