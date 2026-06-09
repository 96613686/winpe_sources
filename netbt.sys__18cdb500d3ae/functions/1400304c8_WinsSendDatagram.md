# WinsSendDatagram

- ea: `0x1400304c8`
- end: `0x1400308a9`
- name: `WinsSendDatagram`
- size: `993`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140052100`
- `0x1400527ac`

## callees

- `0x140004880`
- `0x140006900`
- `0x14000b2f0`
- `0x14000b540`
- `0x14000dc40`
- `0x14000dccc`
- `0x1400304c8`
- `0x140031140`
- `0x1400400a4`
- `0x1400522e4`
- `0x14005231c`
- `0x140052b08`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030526`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030526`
- `ntoskrnl!IofCompleteRequest` at `0x140030837`
- `ntoskrnl!IofCompleteRequest` at `0x140030885`
- `ntoskrnl!IofCompleteRequest` at `0x140030837`
- `ntoskrnl!IofCompleteRequest` at `0x140030885`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030584`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030584`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400305e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030695`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400306c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030781`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003081e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030865`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400305e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030695`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400306c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030781`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400307fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003081e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030865`

## pseudocode

```c
__int64 __fastcall WinsSendDatagram(struct _DEVICE_OBJECT *a1, IRP *a2, char a3)
{
  PMDL MdlAddress; // rcx
  int *FsContext; // r14
  unsigned int *MappedSystemVa; // rsi
  int v9; // ebx
  __int64 ByteCount; // rcx
  unsigned int v11; // ebx
  KIRQL v12; // al
  __int64 v13; // r8
  KIRQL v14; // bp
  struct _LIST_ENTRY *v15; // rax
  struct _LIST_ENTRY *v16; // r14
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // rsi
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rcx
  ULONG_PTR v20; // r12
  void *v21; // rax
  void *v22; // r13
  __int64 v23; // rbx
  unsigned int v24; // eax
  char v26; // [rsp+78h] [rbp+10h]
  __int64 v27; // [rsp+88h] [rbp+20h] BYREF

  MdlAddress = a2->MdlAddress;
  v27 = 0;
  FsContext = (int *)a2->Tail.Overlay.CurrentStackLocation->FileObject->FsContext;
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = (unsigned int *)MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = (unsigned int *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u);
  if ( !MappedSystemVa )
  {
    v9 = -1073741670;
LABEL_41:
    a2->IoStatus.Status = v9;
    goto LABEL_42;
  }
  ByteCount = a2->MdlAddress->ByteCount;
  if ( (unsigned int)ByteCount < 0xC || ByteCount - 12 < (unsigned __int64)MappedSystemVa[2] )
  {
    v9 = -1073741453;
    goto LABEL_41;
  }
  v11 = -1073741823;
  if ( *(_WORD *)MappedSystemVa == 1 )
    v11 = CheckIfLocalNameActive(MappedSystemVa, 1);
  v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v14 = v12;
  if ( !FsContext || FsContext != (int *)pWinsInfo )
  {
    KeReleaseSpinLock(&SpinLock, v12);
    v9 = -1073741816;
    goto LABEL_41;
  }
  v26 = 0;
  if ( a1 == pWinsDeviceContext )
  {
    a1 = *(struct _DEVICE_OBJECT **)(pWinsInfo + 56);
    if ( !a1 || (LOBYTE(v13) = 1, v26 = 1, !(unsigned __int8)NBT_REFERENCE_DEVICE(a1, 12, v13)) )
    {
      KeReleaseSpinLock(&SpinLock, v14);
      a2->IoStatus.Status = 0;
      v9 = 0;
LABEL_42:
      IofCompleteRequest(a2, 0);
      return (unsigned int)v9;
    }
  }
  if ( FsContext[20] < (unsigned int)FsContext[21] || a3 )
  {
    if ( MappedSystemVa[1] )
    {
      v20 = MappedSystemVa[2];
      v21 = (void *)WinsAllocMem(FsContext, v20);
      v22 = v21;
      if ( v21 )
      {
        memmove(v21, MappedSystemVa + 3, (unsigned int)v20);
        if ( (int)GetTracker(&v27, 19) >= 0 )
        {
          v23 = v27;
          *(_QWORD *)(v27 + 80) = 0;
          *(_DWORD *)(v23 + 72) = 0;
          *(_QWORD *)(v23 + 64) = v22;
          *(_DWORD *)(v23 + 56) = v20;
          *(_QWORD *)(v23 + 24) = 0;
          *(_QWORD *)(v23 + 32) = a1;
          *(_QWORD *)(v23 + 48) = 0;
          *(_QWORD *)(v23 + 40) = 0;
          *(_QWORD *)(v23 + 312) = 0;
          *(_QWORD *)(v23 + 96) = 0;
          *(_DWORD *)(v23 + 136) = v20;
          *(_QWORD *)(v23 + 176) = FsContext[22];
          KeReleaseSpinLock(&SpinLock, v14);
          v24 = UdpSendDatagram(
                  v23,
                  _byteswap_ulong(MappedSystemVa[1]),
                  (unsigned int)WinsDgramCompletion,
                  v23,
                  __ROR2__(*((_WORD *)MappedSystemVa + 1), 8),
                  16);
          if ( (BYTE2(xmmword_140038420) & 1) != 0 )
            WPP_SF_d(1040, 23, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, v24);
          v9 = 0;
          a2->IoStatus.Information = v20;
          goto LABEL_36;
        }
        WinsFreeMem(FsContext, v22, (unsigned int)v20, 0);
      }
      KeReleaseSpinLock(&SpinLock, v14);
      v9 = -1073741670;
    }
    else
    {
      KeReleaseSpinLock(&SpinLock, v14);
      v9 = -1073741811;
    }
LABEL_36:
    a2->IoStatus.Status = v9;
    IofCompleteRequest(a2, 0);
    goto LABEL_37;
  }
  if ( (BYTE2(xmmword_140038420) & 1) != 0 )
    WPP_SF_d(1040, 24, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, v11);
  v15 = (struct _LIST_ENTRY *)*((_QWORD *)FsContext + 6);
  v16 = (struct _LIST_ENTRY *)(FsContext + 10);
  if ( v15->Flink != v16 )
    goto LABEL_26;
  p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  a2->Tail.Overlay.ListEntry.Flink = v16;
  a2->Tail.Overlay.ListEntry.Blink = v15;
  v15->Flink = &a2->Tail.Overlay.ListEntry;
  v16->Blink = &a2->Tail.Overlay.ListEntry;
  v9 = NTCheckSetCancelRoutine(a2, &NbtCancelWinsSendIrp);
  if ( v9 < 0 )
  {
    Flink = p_ListEntry->ListEntry.Flink;
    if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)p_ListEntry->ListEntry.Flink->Blink == p_ListEntry )
    {
      Blink = a2->Tail.Overlay.ListEntry.Blink;
      if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)Blink->Flink == p_ListEntry )
      {
        Blink->Flink = Flink;
        Flink->Blink = Blink;
        KeReleaseSpinLock(&SpinLock, v14);
        NTIoComplete(a2);
        goto LABEL_37;
      }
    }
LABEL_26:
    __fastfail(3u);
  }
  v9 = 259;
  KeReleaseSpinLock(&SpinLock, v14);
LABEL_37:
  if ( v26 )
    NBT_DEREFERENCE_DEVICE(a1, 12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400304c8  mov     rax, rsp
0x1400304cb  mov     [rax+8], rbx
0x1400304cf  push    rbp
0x1400304d0  push    rsi
0x1400304d1  push    rdi
0x1400304d2  push    r12
0x1400304d4  push    r13
0x1400304d6  push    r14
0x1400304d8  push    r15
0x1400304da  sub     rsp, 30h
0x1400304de  xor     r13d, r13d
0x1400304e1  mov     r15, rcx
0x1400304e4  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400304e8  mov     rdi, rdx
0x1400304eb  mov     [rax+20h], r13
0x1400304ef  mov     r12b, r8b
0x1400304f2  mov     rax, [rdx+0B8h]
0x1400304f9  lea     edx, [r13+1]
0x1400304fd  test    byte ptr [rcx+0Ah], 5
0x140030501  mov     r9, [rax+30h]
0x140030505  mov     r14, [r9+18h]
0x140030509  jz      short loc_140030511
0x14003050b  mov     rsi, [rcx+18h]
0x14003050f  jmp     short loc_14003053A
0x140030511  mov     r8d, edx; CacheType
0x140030514  mov     [rsp+68h+Priority], 40000020h; Priority
0x14003051c  xor     edx, edx; AccessMode
0x14003051e  mov     [rsp+68h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140030523  xor     r9d, r9d; RequestedAddress
0x140030526  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14003052d  nop     dword ptr [rax+rax+00h]
0x140030532  mov     rsi, rax
0x140030535  mov     edx, 1
0x14003053a  test    rsi, rsi
0x14003053d  jnz     short loc_140030549
0x14003053f  mov     ebx, 0C000009Ah
0x140030544  jmp     loc_14003087D
0x140030549  mov     rax, [rdi+8]
0x14003054d  mov     ecx, [rax+28h]
0x140030550  cmp     ecx, 0Ch
0x140030553  jb      loc_140030878
0x140030559  mov     eax, [rsi+8]
0x14003055c  sub     rcx, 0Ch
0x140030560  cmp     rcx, rax
0x140030563  jb      loc_140030878
0x140030569  mov     ebx, 0C0000001h
0x14003056e  cmp     [rsi], dx
0x140030571  jnz     short loc_14003057D
0x140030573  mov     rcx, rsi
0x140030576  call    CheckIfLocalNameActive
0x14003057b  mov     ebx, eax
0x14003057d  lea     rcx, SpinLock; SpinLock
0x140030584  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14003058b  nop     dword ptr [rax+rax+00h]
0x140030590  mov     bpl, al
0x140030593  test    r14, r14
0x140030596  jz      loc_14003085B
0x14003059c  mov     rcx, cs:pWinsInfo
0x1400305a3  cmp     r14, rcx
0x1400305a6  jnz     loc_14003085B
0x1400305ac  cmp     r15, cs:pWinsDeviceContext
0x1400305b3  mov     [rsp+68h+arg_8], r13b
0x1400305b8  jnz     short loc_1400305FE
0x1400305ba  mov     r15, [rcx+38h]
0x1400305be  test    r15, r15
0x1400305c1  jz      short loc_1400305DC
0x1400305c3  mov     r8b, 1
0x1400305c6  mov     [rsp+68h+arg_8], 1
0x1400305cb  mov     edx, 0Ch
0x1400305d0  mov     rcx, r15
0x1400305d3  call    NBT_REFERENCE_DEVICE
0x1400305d8  test    al, al
0x1400305da  jnz     short loc_1400305FE
0x1400305dc  mov     dl, bpl; NewIrql
0x1400305df  lea     rcx, SpinLock; SpinLock
0x1400305e6  call    cs:__imp_KeReleaseSpinLock
0x1400305ed  nop     dword ptr [rax+rax+00h]
0x1400305f2  mov     [rdi+30h], r13d
0x1400305f6  mov     ebx, r13d
0x1400305f9  jmp     loc_140030880
0x1400305fe  mov     eax, [r14+54h]
0x140030602  cmp     [r14+50h], eax
0x140030606  jb      loc_1400306DA
0x14003060c  test    r12b, r12b
0x14003060f  jnz     loc_1400306DA
0x140030615  test    byte ptr cs:xmmword_140038420+2, 1
0x14003061c  jz      short loc_140030637
0x14003061e  mov     edx, 18h
0x140030623  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x14003062a  mov     ecx, 410h
0x14003062f  mov     r9d, ebx
0x140030632  call    WPP_SF_d
0x140030637  mov     rax, [r14+30h]
0x14003063b  add     r14, 28h ; '('
0x14003063f  cmp     [rax], r14
0x140030642  jnz     loc_1400306D3
0x140030648  lea     rsi, [rdi+0A8h]
0x14003064f  mov     rcx, rdi
0x140030652  mov     [rsi], r14
0x140030655  lea     rdx, NbtCancelWinsSendIrp
0x14003065c  mov     [rsi+8], rax
0x140030660  mov     [rax], rsi
0x140030663  mov     [r14+8], rsi
0x140030667  call    NTCheckSetCancelRoutine
0x14003066c  mov     ebx, eax
0x14003066e  test    eax, eax
0x140030670  jns     short loc_1400306B3
0x140030672  mov     rax, [rsi]
0x140030675  cmp     [rax+8], rsi
0x140030679  jnz     short loc_1400306D3
0x14003067b  mov     rcx, [rsi+8]
0x14003067f  cmp     [rcx], rsi
0x140030682  jnz     short loc_1400306D3
0x140030684  mov     [rcx], rax
0x140030687  mov     dl, bpl; NewIrql
0x14003068a  mov     [rax+8], rcx
0x14003068e  lea     rcx, SpinLock; SpinLock
0x140030695  call    cs:__imp_KeReleaseSpinLock
0x14003069c  nop     dword ptr [rax+rax+00h]
0x1400306a1  xor     r8d, r8d
0x1400306a4  mov     edx, ebx
0x1400306a6  mov     rcx, rdi; Irp
0x1400306a9  call    NTIoComplete
0x1400306ae  jmp     loc_140030843
0x1400306b3  mov     dl, bpl; NewIrql
0x1400306b6  lea     rcx, SpinLock; SpinLock
0x1400306bd  mov     ebx, 103h
0x1400306c2  call    cs:__imp_KeReleaseSpinLock
0x1400306c9  nop     dword ptr [rax+rax+00h]
0x1400306ce  jmp     loc_140030843
0x1400306d3  mov     ecx, 3
0x1400306d8  int     29h; Win8: RtlFailFast(ecx)
0x1400306da  cmp     [rsi+4], r13d
0x1400306de  jz      loc_140030814
0x1400306e4  mov     r12d, [rsi+8]
0x1400306e8  mov     rcx, r14
0x1400306eb  mov     edx, r12d
0x1400306ee  call    WinsAllocMem
0x1400306f3  mov     r13, rax
0x1400306f6  test    rax, rax
0x1400306f9  jz      loc_1400307F4
0x1400306ff  mov     r8d, r12d; Size
0x140030702  lea     rdx, [rsi+0Ch]; Src
0x140030706  mov     rcx, rax; void *
0x140030709  call    memmove
0x14003070e  mov     edx, 13h
0x140030713  lea     rcx, [rsp+68h+arg_18]
0x14003071b  call    GetTracker
0x140030720  test    eax, eax
0x140030722  js      loc_1400307E3
0x140030728  mov     rbx, [rsp+68h+arg_18]
0x140030730  lea     rcx, SpinLock; SpinLock
0x140030737  mov     dl, bpl; NewIrql
0x14003073a  mov     qword ptr [rbx+50h], 0
0x140030742  mov     dword ptr [rbx+48h], 0
0x140030749  mov     [rbx+40h], r13
0x14003074d  xor     r13d, r13d
0x140030750  mov     [rbx+38h], r12d
0x140030754  mov     [rbx+18h], r13
0x140030758  mov     [rbx+20h], r15
0x14003075c  mov     [rbx+30h], r13
0x140030760  mov     [rbx+28h], r13
0x140030764  mov     [rbx+138h], r13
0x14003076b  mov     [rbx+60h], r13
0x14003076f  mov     [rbx+88h], r12d
0x140030776  movsxd  rax, dword ptr [r14+58h]
0x14003077a  mov     [rbx+0B0h], rax
0x140030781  call    cs:__imp_KeReleaseSpinLock
0x140030788  nop     dword ptr [rax+rax+00h]
0x14003078d  movzx   eax, word ptr [rsi+2]
0x140030791  lea     r8, WinsDgramCompletion
0x140030798  mov     edx, [rsi+4]
0x14003079b  mov     r9, rbx
0x14003079e  ror     ax, 8
0x1400307a2  mov     rcx, rbx
0x1400307a5  bswap   edx
0x1400307a7  mov     [rsp+68h+Priority], 10h
0x1400307af  mov     word ptr [rsp+68h+BugCheckOnFailure], ax
0x1400307b4  call    UdpSendDatagram
0x1400307b9  test    byte ptr cs:xmmword_140038420+2, 1
0x1400307c0  jz      short loc_1400307DA
0x1400307c2  lea     edx, [r13+17h]
0x1400307c6  mov     ecx, 410h
0x1400307cb  mov     r9d, eax
0x1400307ce  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400307d5  call    WPP_SF_d
0x1400307da  mov     ebx, r13d
0x1400307dd  mov     [rdi+38h], r12
0x1400307e1  jmp     short loc_14003082F
0x1400307e3  xor     r9d, r9d
0x1400307e6  mov     r8d, r12d
0x1400307e9  mov     rdx, r13
0x1400307ec  mov     rcx, r14
0x1400307ef  call    WinsFreeMem
0x1400307f4  mov     dl, bpl; NewIrql
0x1400307f7  lea     rcx, SpinLock; SpinLock
0x1400307fe  call    cs:__imp_KeReleaseSpinLock
0x140030805  nop     dword ptr [rax+rax+00h]
0x14003080a  xor     r13d, r13d
0x14003080d  mov     ebx, 0C000009Ah
0x140030812  jmp     short loc_14003082F
0x140030814  mov     dl, bpl; NewIrql
0x140030817  lea     rcx, SpinLock; SpinLock
0x14003081e  call    cs:__imp_KeReleaseSpinLock
0x140030825  nop     dword ptr [rax+rax+00h]
0x14003082a  mov     ebx, 0C000000Dh
0x14003082f  xor     edx, edx; PriorityBoost
0x140030831  mov     [rdi+30h], ebx
0x140030834  mov     rcx, rdi; Irp
0x140030837  call    cs:__imp_IofCompleteRequest
0x14003083e  nop     dword ptr [rax+rax+00h]
0x140030843  cmp     [rsp+68h+arg_8], r13b
0x140030848  jz      short loc_140030891
0x14003084a  xor     r8d, r8d
0x14003084d  mov     rcx, r15
0x140030850  lea     edx, [r8+0Ch]
0x140030854  call    NBT_DEREFERENCE_DEVICE
0x140030859  jmp     short loc_140030891
0x14003085b  mov     dl, bpl; NewIrql
0x14003085e  lea     rcx, SpinLock; SpinLock
0x140030865  call    cs:__imp_KeReleaseSpinLock
0x14003086c  nop     dword ptr [rax+rax+00h]
0x140030871  mov     ebx, 0C0000008h
0x140030876  jmp     short loc_14003087D
0x140030878  mov     ebx, 0C0000173h
0x14003087d  mov     [rdi+30h], ebx
0x140030880  xor     edx, edx; PriorityBoost
0x140030882  mov     rcx, rdi; Irp
0x140030885  call    cs:__imp_IofCompleteRequest
0x14003088c  nop     dword ptr [rax+rax+00h]
0x140030891  mov     eax, ebx
0x140030893  mov     rbx, [rsp+68h+arg_0]
0x140030898  add     rsp, 30h
0x14003089c  pop     r15
0x14003089e  pop     r14
0x1400308a0  pop     r13
0x1400308a2  pop     r12
0x1400308a4  pop     rdi
0x1400308a5  pop     rsi
0x1400308a6  pop     rbp
0x1400308a7  retn
```
