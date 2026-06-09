# CKsMdlcache::MdlCacheHandleThunkBufferIrp(_IRP *,ulong)

- ea: `0x18000f840`
- end: `0x18000fafc`
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

- `0x18000f840`
- `0x180066360`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x18000f9ad`
- `ntoskrnl!MmUnlockPages` at `0x18000fab0`
- `ntoskrnl!MmUnlockPages` at `0x18000f9ad`
- `ntoskrnl!MmUnlockPages` at `0x18000fab0`
- `ntoskrnl!MmProbeAndLockPages` at `0x18000fa08`
- `ntoskrnl!MmProbeAndLockPages` at `0x18000fa08`
- `ntoskrnl!IoAllocateMdl` at `0x18000f904`
- `ntoskrnl!IoAllocateMdl` at `0x18000f95e`
- `ntoskrnl!IoAllocateMdl` at `0x18000f904`
- `ntoskrnl!IoAllocateMdl` at `0x18000f95e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fa4d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000fa4d`
- `ntoskrnl!ExRaiseStatus` at `0x18000fa63`
- `ntoskrnl!ExRaiseStatus` at `0x18000fa63`
- `ntoskrnl!IoFreeMdl` at `0x18000f9bc`
- `ntoskrnl!IoFreeMdl` at `0x18000fabf`
- `ntoskrnl!IoFreeMdl` at `0x18000f9bc`
- `ntoskrnl!IoFreeMdl` at `0x18000fabf`

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
0x18000f840  mov     r11, rsp
0x18000f843  mov     [r11+8], rbx
0x18000f847  mov     [r11+18h], rsi
0x18000f84b  mov     [r11+10h], rdx
0x18000f84f  push    rdi
0x18000f850  push    r12
0x18000f852  push    r13
0x18000f854  push    r14
0x18000f856  push    r15
0x18000f858  sub     rsp, 40h
0x18000f85c  mov     r13d, r8d
0x18000f85f  mov     rsi, rdx
0x18000f862  xor     ebx, ebx
0x18000f864  mov     r15b, 1
0x18000f867  mov     rax, [rdx+0B8h]
0x18000f86e  mov     r14d, [rax+8]
0x18000f872  cmp     [rdx+18h], rbx
0x18000f876  jnz     loc_18000FA8B
0x18000f87c  mov     rdi, [rdx+70h]
0x18000f880  mov     [rdx+18h], rdi
0x18000f884  cmp     r14d, 38h ; '8'
0x18000f888  jb      loc_18000FA8B
0x18000f88e  mov     [r11-30h], rdi
0x18000f892  cmp     r14d, 38h ; '8'
0x18000f896  jb      loc_18000F9DD
0x18000f89c  mov     ecx, [rdi+30h]
0x18000f89f  mov     eax, ecx
0x18000f8a1  and     eax, 18000h
0x18000f8a6  cmp     eax, 10000h
0x18000f8ab  jz      loc_18000F986
0x18000f8b1  bt      ecx, 0Fh
0x18000f8b5  jnb     loc_18000F9DA
0x18000f8bb  mov     rax, gs:188h
0x18000f8c4  cmp     [rsi+78h], rax
0x18000f8c8  jz      short loc_18000F8D4
0x18000f8ca  mov     ebx, 0C000071Ch
0x18000f8cf  jmp     loc_18000F98B
0x18000f8d4  mov     rax, [rdi+28h]
0x18000f8d8  test    rax, rax
0x18000f8db  jz      loc_18000F986
0x18000f8e1  mov     r12d, [rdi]
0x18000f8e4  mov     rdx, [rsi+8]
0x18000f8e8  mov     [rsp+68h+Irp], rsi; Irp
0x18000f8ed  mov     r9b, 1; ChargeQuota
0x18000f8f0  bt      ecx, 10h
0x18000f8f4  jnb     short loc_18000F91C
0x18000f8f6  test    rdx, rdx
0x18000f8f9  setnz   r8b; SecondaryBuffer
0x18000f8fd  mov     edx, 1000h; Length
0x18000f902  xor     ecx, ecx; VirtualAddress
0x18000f904  call    cs:__imp_IoAllocateMdl
0x18000f90b  nop     dword ptr [rax+rax+00h]
0x18000f910  test    rax, rax
0x18000f913  jnz     short loc_18000F92B
0x18000f915  mov     ebx, 0C000009Ah
0x18000f91a  jmp     short loc_18000F98B
0x18000f91c  test    rdx, rdx
0x18000f91f  setnz   r8b
0x18000f923  mov     edx, [rdi+20h]
0x18000f926  mov     rcx, rax
0x18000f929  jmp     short loc_18000F904
0x18000f92b  test    dword ptr [rdi+30h], 1000h
0x18000f932  jz      short loc_18000F96F
0x18000f934  cmp     r12d, 80h
0x18000f93b  jbe     short loc_18000F96F
0x18000f93d  mov     rcx, [rdi+88h]; VirtualAddress
0x18000f944  test    rcx, rcx
0x18000f947  jz      short loc_18000F986
0x18000f949  mov     edx, [rdi+80h]; Length
0x18000f94f  test    edx, edx
0x18000f951  jz      short loc_18000F986
0x18000f953  mov     [rsp+68h+Irp], rsi; Irp
0x18000f958  mov     r9b, 1; ChargeQuota
0x18000f95b  mov     r8b, r9b; SecondaryBuffer
0x18000f95e  call    cs:__imp_IoAllocateMdl
0x18000f965  nop     dword ptr [rax+rax+00h]
0x18000f96a  test    rax, rax
0x18000f96d  jz      short loc_18000F915
0x18000f96f  mov     eax, [rdi]
0x18000f971  add     rdi, rax
0x18000f974  mov     [rsp+68h+var_30], rdi
0x18000f979  sub     r14d, eax
0x18000f97c  mov     [rsp+68h+var_34], r14d
0x18000f981  jmp     loc_18000F892
0x18000f986  mov     ebx, 0C000000Dh
0x18000f98b  mov     [rsp+68h+var_38], ebx
0x18000f98f  mov     rdi, [rsi+8]
0x18000f993  test    rdi, rdi
0x18000f996  jz      loc_18000FA8B
0x18000f99c  test    rdi, rdi
0x18000f99f  jz      short loc_18000F9CD
0x18000f9a1  mov     r14, [rdi]
0x18000f9a4  test    byte ptr [rdi+0Ah], 2
0x18000f9a8  jz      short loc_18000F9B9
0x18000f9aa  mov     rcx, rdi; MemoryDescriptorList
0x18000f9ad  call    cs:__imp_MmUnlockPages
0x18000f9b4  nop     dword ptr [rax+rax+00h]
0x18000f9b9  mov     rcx, rdi; Mdl
0x18000f9bc  call    cs:__imp_IoFreeMdl
0x18000f9c3  nop     dword ptr [rax+rax+00h]
0x18000f9c8  mov     rdi, r14
0x18000f9cb  jmp     short loc_18000F99C
0x18000f9cd  mov     qword ptr [rsi+8], 0
0x18000f9d5  jmp     loc_18000FA8B
0x18000f9da  xor     r15b, r15b
0x18000f9dd  test    r15b, r15b
0x18000f9e0  jz      loc_18000FA77
0x18000f9e6  mov     rdi, [rsi+8]
0x18000f9ea  test    rdi, rdi
0x18000f9ed  jz      loc_18000FA8B
0x18000f9f3  cmp     qword ptr [rdi+20h], 0
0x18000f9f8  jnz     short loc_18000F9FC
0x18000f9fa  jmp     short loc_18000FA6F
0x18000f9fc  mov     r8d, 1; Operation
0x18000fa02  mov     dl, [rsi+40h]; AccessMode
0x18000fa05  mov     rcx, rdi; MemoryDescriptorList
0x18000fa08  call    cs:__imp_MmProbeAndLockPages
0x18000fa0f  nop     dword ptr [rax+rax+00h]
0x18000fa14  test    r13b, 40h
0x18000fa18  jz      short loc_18000FA6F
0x18000fa1a  mov     eax, 2000h
0x18000fa1f  or      [rdi+0Ah], ax
0x18000fa23  movzx   eax, word ptr [rdi+0Ah]
0x18000fa27  test    al, 5
0x18000fa29  jz      short loc_18000FA31
0x18000fa2b  mov     rax, [rdi+18h]
0x18000fa2f  jmp     short loc_18000FA59
0x18000fa31  mov     [rsp+68h+Priority], 40000000h; Priority
0x18000fa39  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x18000fa41  xor     r9d, r9d; RequestedAddress
0x18000fa44  xor     edx, edx; AccessMode
0x18000fa46  lea     r8d, [r9+1]; CacheType
0x18000fa4a  mov     rcx, rdi; MemoryDescriptorList
0x18000fa4d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x18000fa54  nop     dword ptr [rax+rax+00h]
0x18000fa59  test    rax, rax
0x18000fa5c  jnz     short loc_18000FA6F
0x18000fa5e  mov     ecx, 0C000009Ah; Status
0x18000fa63  call    cs:__imp_ExRaiseStatus
0x18000fa6f  mov     rdi, [rdi]
0x18000fa72  jmp     loc_18000F9EA
0x18000fa77  xor     r8d, r8d; HeaderSize
0x18000fa7a  mov     edx, r13d; ProbeFlags
0x18000fa7d  mov     rcx, rsi; Irp
0x18000fa80  call    KsProbeStreamIrp
0x18000fa85  mov     ebx, eax
0x18000fa87  mov     [rsp+68h+var_38], eax
0x18000fa8b  jmp     short loc_18000FADF
0x18000fa8d  mov     ebx, eax
0x18000fa8f  mov     rsi, [rsp+68h+arg_8]
0x18000fa94  cmp     qword ptr [rsi+8], 0
0x18000fa99  jz      short loc_18000FADB
0x18000fa9b  mov     rdi, [rsi+8]
0x18000fa9f  test    rdi, rdi
0x18000faa2  jz      short loc_18000FAD3
0x18000faa4  mov     r14, [rdi]
0x18000faa7  test    byte ptr [rdi+0Ah], 2
0x18000faab  jz      short loc_18000FABC
0x18000faad  mov     rcx, rdi; MemoryDescriptorList
0x18000fab0  call    cs:__imp_MmUnlockPages
0x18000fab7  nop     dword ptr [rax+rax+00h]
0x18000fabc  mov     rcx, rdi; Mdl
0x18000fabf  call    cs:__imp_IoFreeMdl
0x18000fac6  nop     dword ptr [rax+rax+00h]
0x18000facb  mov     rdi, r14
0x18000face  test    r14, r14
0x18000fad1  jnz     short loc_18000FAA4
0x18000fad3  mov     qword ptr [rsi+8], 0
0x18000fadb  mov     [rsp+68h+var_38], ebx
0x18000fadf  mov     eax, ebx
0x18000fae1  lea     r11, [rsp+68h+var_28]
0x18000fae6  mov     rbx, [r11+30h]
0x18000faea  mov     rsi, [r11+40h]
0x18000faee  mov     rsp, r11
0x18000faf1  pop     r15
0x18000faf3  pop     r14
0x18000faf5  pop     r13
0x18000faf7  pop     r12
0x18000faf9  pop     rdi
0x18000fafa  retn
```
