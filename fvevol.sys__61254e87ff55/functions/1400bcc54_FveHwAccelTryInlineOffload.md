# FveHwAccelTryInlineOffload

- ea: `0x1400bcc54`
- end: `0x1400bd070`
- name: `FveHwAccelTryInlineOffload`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ebc00`

## callees

- `0x1400089c4`
- `0x14002a2a0`
- `0x14002d140`
- `0x1400bcc54`
- `0x1400be3c0`
- `0x1400cebf8`
- `0x1400cec8c`
- `0x1400d0568`
- `0x1400d1184`
- `0x1400db940`
- `0x1400dfbcc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400bd02c`
- `ntoskrnl!IofCallDriver` at `0x1400bd02c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400bcd5c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400bcd5c`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400bcd70`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400bcd70`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bccf0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400bccf0`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bce3f`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400bce3f`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400bcea2`
- `ntoskrnl!MmAreMdlPagesCached` at `0x1400bcea2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bcdaf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bcdaf`
- `ntoskrnl!IoAllocateMdl` at `0x1400bcd41`
- `ntoskrnl!IoAllocateMdl` at `0x1400bcd41`
- `ntoskrnl!ExAllocatePool2` at `0x1400bcd15`
- `ntoskrnl!ExAllocatePool2` at `0x1400bcd15`

## pseudocode

```c
__int64 __fastcall FveHwAccelTryInlineOffload(__int64 a1, __int64 a2, IRP *a3, __int64 a4, ULONG Length)
{
  __int64 v5; // rbx
  void *Pool2; // rbp
  struct _MDL *v10; // r14
  char v11; // r13
  __int64 v12; // rdx
  __int64 v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // ebx
  __int64 v17; // rcx
  PVOID v18; // rax
  struct _MDL *Mdl; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  PMDL MdlAddress; // rcx
  PVOID v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r9
  int Flink_low_high; // eax
  int v29; // eax
  __int64 v30; // r8
  PVOID v31; // rax
  __int64 v32; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v34; // rax
  int Irp; // [rsp+20h] [rbp-88h]
  char v36; // [rsp+B8h] [rbp+10h]

  v36 = a2;
  v5 = *(_QWORD *)(a1 + 8);
  if ( (*(_DWORD *)(v5 + 9928) & 0x8000000) != 0 )
    return 3221225473LL;
  Pool2 = 0;
  v10 = 0;
  v11 = 0;
  v13 = AcquireInlineControl(a1, a2, a3);
  if ( v13 )
  {
    if ( v36 )
    {
      if ( Length > *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v5 + 884) + 1592) )
      {
        v16 = -1073741823;
        goto LABEL_32;
      }
      v17 = *(_QWORD *)(a1 + 2024);
      v18 = v17
          ? (PVOID)PplAllocateFromLookasideList(v17, v12, v14, v15)
          : ExAllocateFromNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(a1 + 2016));
      Pool2 = v18;
      v11 = 1;
      if ( v18 )
        goto LABEL_12;
    }
    Pool2 = (void *)ExAllocatePool2(74, Length, 1883592262);
    v11 = 2;
    if ( Pool2 )
    {
LABEL_12:
      Mdl = IoAllocateMdl(Pool2, Length, 0, 0, 0);
      v10 = Mdl;
      if ( Mdl )
      {
        MmBuildMdlForNonPagedPool(Mdl);
        MmMdlPageContentsState(v10, 1);
        MdlAddress = a3->MdlAddress;
        v24 = (MdlAddress->MdlFlags & 5) != 0
            ? MdlAddress->MappedSystemVa
            : MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
        if ( v24 )
        {
          v25 = FveHwAccelAcquireDescriptor(a1, v20, v21, v22);
          *(_QWORD *)(v13 + 304) = v25;
          if ( v25 )
          {
            v26 = FveHwAccelAcquireWorkRequest(a1);
            *(_QWORD *)(v13 + 296) = v26;
            if ( v26 )
            {
              *(_QWORD *)v13 = a3;
              *(_QWORD *)(v13 + 8) = MEMORY[0xFFFFF78000000008];
              *(_QWORD *)(v13 + 64) = a4;
              *(_BYTE *)(v13 + 274) = v36;
              *(_DWORD *)(v13 + 72) = Length;
              *(_BYTE *)(v13 + 273) = FveIsPagingRequest(a1, a3, a4, Length);
              *(_DWORD *)(v13 + 76) = IoGetIoPriorityHint(a3);
              *(_BYTE *)(v13 + 80) = a3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
              *(_DWORD *)(v13 + 84) = (unsigned __int8)BYTE1(LODWORD(a3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
              if ( *(_BYTE *)(a1 + 1477) )
                Flink_low_high = (unsigned __int8)HIBYTE(LODWORD(a3->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink));
              else
                Flink_low_high = GetPriorityFromIrpEx(a1, a3, 8, v27);
              *(_DWORD *)(v13 + 136) = Flink_low_high;
              *(_QWORD *)(v13 + 24) = 0;
              *(_QWORD *)(v13 + 32) = 0;
              *(_QWORD *)(v13 + 40) = 0;
              v29 = MmAreMdlPagesCached(a3->MdlAddress);
              *(_BYTE *)(v13 + 276) = 0;
              *(_BYTE *)(v13 + 272) = v29 != 0;
              if ( v36 )
              {
                v31 = v24;
                v24 = Pool2;
              }
              else
              {
                v31 = Pool2;
              }
              LOBYTE(v30) = v36;
              v16 = FveHwAccelInitializeWorkRequest(
                      a1,
                      *(_QWORD *)(v13 + 296),
                      v30,
                      1,
                      *(_QWORD *)(v13 + 304),
                      v13,
                      a4,
                      v31,
                      Length,
                      v24,
                      Length);
              if ( v16 < 0 )
                goto LABEL_32;
              *(_QWORD *)(*(_QWORD *)(v13 + 296) + 128LL) = Pool2;
              *(_QWORD *)(*(_QWORD *)(v13 + 296) + 144LL) = v10;
              *(_BYTE *)(*(_QWORD *)(v13 + 296) + 136LL) = v11;
              *(_QWORD *)(*(_QWORD *)(v13 + 296) + 152LL) = a3->MdlAddress;
              if ( v36 )
              {
                v32 = *(_QWORD *)(v13 + 296);
                *(_QWORD *)(v13 + 32) = MEMORY[0xFFFFF78000000008];
                *(_DWORD *)(v13 + 40) = Length;
                v16 = FveHwAccelSubmitCryptoWork(a1, v32);
                if ( v16 < 0 )
                  goto LABEL_32;
              }
              else
              {
                CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
                a3->MdlAddress = v10;
                *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
                *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
                *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                           + 6);
                CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
                CurrentStackLocation[-1].Control = 0;
                *(_QWORD *)(v13 + 24) = MEMORY[0xFFFFF78000000008];
                *(_DWORD *)(v13 + 44) = Length;
                v34 = a3->Tail.Overlay.CurrentStackLocation;
                v34[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FveHwAccelInlineReadCompletionRoutine;
                v34[-1].Context = (PVOID)v13;
                v34[-1].Control = -32;
                FvePerfTraceDevPtr(a1, FVE_PERF_READ_SUBREQUEST_START, a3);
                IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 112), a3);
              }
              v13 = 0;
              Pool2 = 0;
              v10 = 0;
              goto LABEL_32;
            }
          }
        }
      }
    }
  }
  v16 = -1073741670;
LABEL_32:
  LOBYTE(Irp) = v11;
  FveReleaseInlineResources(a1, v13, Pool2, v10, Irp);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400bcc54  mov     [rsp+arg_0], rbx
0x1400bcc59  mov     [rsp+arg_18], r9
0x1400bcc5e  mov     [rsp+arg_8], dl
0x1400bcc62  push    rbp
0x1400bcc63  push    rsi
0x1400bcc64  push    rdi
0x1400bcc65  push    r12
0x1400bcc67  push    r13
0x1400bcc69  push    r14
0x1400bcc6b  push    r15
0x1400bcc6d  sub     rsp, 70h
0x1400bcc71  mov     rbx, [rcx+8]
0x1400bcc75  mov     r15, r8
0x1400bcc78  mov     rsi, rcx
0x1400bcc7b  test    dword ptr [rbx+26C8h], 8000000h
0x1400bcc85  jz      short loc_1400BCC91
0x1400bcc87  mov     eax, 0C0000001h
0x1400bcc8c  jmp     loc_1400BD057
0x1400bcc91  xor     ebp, ebp
0x1400bcc93  xor     r14d, r14d
0x1400bcc96  xor     r13b, r13b
0x1400bcc99  call    AcquireInlineControl
0x1400bcc9e  mov     rdi, rax
0x1400bcca1  test    rax, rax
0x1400bcca4  jnz     short loc_1400BCCB0
0x1400bcca6  mov     ebx, 0C000009Ah
0x1400bccab  jmp     loc_1400BD03F
0x1400bccb0  mov     r12d, [rsp+0A8h+Length]
0x1400bccb8  cmp     [rsp+0A8h+arg_8], bpl
0x1400bccc0  jz      short loc_1400BCD07
0x1400bccc2  mov     eax, [rbx+374h]
0x1400bccc8  cmp     r12d, [rsi+rax*4+638h]
0x1400bccd0  ja      loc_1400BCD8C
0x1400bccd6  mov     rcx, [rsi+7E8h]
0x1400bccdd  test    rcx, rcx
0x1400bcce0  jz      short loc_1400BCCE9
0x1400bcce2  call    PplAllocateFromLookasideList
0x1400bcce7  jmp     short loc_1400BCCFC
0x1400bcce9  mov     rcx, [rsi+7E0h]; Lookaside
0x1400bccf0  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400bccf7  nop     dword ptr [rax+rax+00h]
0x1400bccfc  mov     rbp, rax
0x1400bccff  mov     r13b, 1
0x1400bcd02  test    rax, rax
0x1400bcd05  jnz     short loc_1400BCD30
0x1400bcd07  mov     rdx, r12
0x1400bcd0a  mov     ecx, 4Ah ; 'J'
0x1400bcd0f  mov     r8d, 70455646h
0x1400bcd15  call    cs:__imp_ExAllocatePool2
0x1400bcd1c  nop     dword ptr [rax+rax+00h]
0x1400bcd21  mov     rbp, rax
0x1400bcd24  mov     r13b, 2
0x1400bcd27  test    rax, rax
0x1400bcd2a  jz      loc_1400BCCA6
0x1400bcd30  xor     r9d, r9d; ChargeQuota
0x1400bcd33  mov     [rsp+0A8h+Irp], r14; Irp
0x1400bcd38  xor     r8d, r8d; SecondaryBuffer
0x1400bcd3b  mov     edx, r12d; Length
0x1400bcd3e  mov     rcx, rbp; VirtualAddress
0x1400bcd41  call    cs:__imp_IoAllocateMdl
0x1400bcd48  nop     dword ptr [rax+rax+00h]
0x1400bcd4d  mov     r14, rax
0x1400bcd50  test    rax, rax
0x1400bcd53  jz      loc_1400BCCA6
0x1400bcd59  mov     rcx, rax; MemoryDescriptorList
0x1400bcd5c  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400bcd63  nop     dword ptr [rax+rax+00h]
0x1400bcd68  mov     edx, 1
0x1400bcd6d  mov     rcx, r14
0x1400bcd70  call    cs:__imp_MmMdlPageContentsState
0x1400bcd77  nop     dword ptr [rax+rax+00h]
0x1400bcd7c  mov     rcx, [r15+8]; MemoryDescriptorList
0x1400bcd80  test    byte ptr [rcx+0Ah], 5
0x1400bcd84  jz      short loc_1400BCD96
0x1400bcd86  mov     rbx, [rcx+18h]
0x1400bcd8a  jmp     short loc_1400BCDBE
0x1400bcd8c  mov     ebx, 0C0000001h
0x1400bcd91  jmp     loc_1400BD03F
0x1400bcd96  xor     r9d, r9d; RequestedAddress
0x1400bcd99  mov     [rsp+0A8h+Priority], 40000010h; Priority
0x1400bcda1  xor     edx, edx; AccessMode
0x1400bcda3  mov     dword ptr [rsp+0A8h+Irp], 0; BugCheckOnFailure
0x1400bcdab  lea     r8d, [r9+1]; CacheType
0x1400bcdaf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400bcdb6  nop     dword ptr [rax+rax+00h]
0x1400bcdbb  mov     rbx, rax
0x1400bcdbe  test    rbx, rbx
0x1400bcdc1  jz      loc_1400BCCA6
0x1400bcdc7  mov     rcx, rsi
0x1400bcdca  call    FveHwAccelAcquireDescriptor
0x1400bcdcf  mov     [rdi+130h], rax
0x1400bcdd6  test    rax, rax
0x1400bcdd9  jz      loc_1400BCCA6
0x1400bcddf  mov     rcx, rsi
0x1400bcde2  call    FveHwAccelAcquireWorkRequest
0x1400bcde7  mov     [rdi+128h], rax
0x1400bcdee  test    rax, rax
0x1400bcdf1  jz      loc_1400BCCA6
0x1400bcdf7  mov     rcx, [rsp+0A8h+arg_18]
0x1400bcdff  mov     r9d, r12d
0x1400bce02  mov     [rdi], r15
0x1400bce05  mov     r8, rcx
0x1400bce08  mov     rax, ds:0FFFFF78000000008h
0x1400bce12  mov     rdx, r15
0x1400bce15  mov     [rdi+8], rax
0x1400bce19  mov     al, [rsp+0A8h+arg_8]
0x1400bce20  mov     [rdi+40h], rcx
0x1400bce24  mov     rcx, rsi
0x1400bce27  mov     [rdi+112h], al
0x1400bce2d  mov     [rdi+48h], r12d
0x1400bce31  call    FveIsPagingRequest
0x1400bce36  mov     rcx, r15; Irp
0x1400bce39  mov     [rdi+111h], al
0x1400bce3f  call    cs:__imp_IoGetIoPriorityHint
0x1400bce46  nop     dword ptr [rax+rax+00h]
0x1400bce4b  mov     [rdi+4Ch], eax
0x1400bce4e  mov     rax, [r15+78h]
0x1400bce52  mov     [rdi+50h], al
0x1400bce55  mov     eax, [r15+78h]
0x1400bce59  shr     rax, 8
0x1400bce5d  movzx   eax, al
0x1400bce60  mov     [rdi+54h], eax
0x1400bce63  cmp     byte ptr [rsi+5C5h], 0
0x1400bce6a  jz      short loc_1400BCE79
0x1400bce6c  mov     eax, [r15+78h]
0x1400bce70  shr     rax, 18h
0x1400bce74  movzx   eax, al
0x1400bce77  jmp     short loc_1400BCE8A
0x1400bce79  mov     r8d, 8
0x1400bce7f  mov     rdx, r15
0x1400bce82  mov     rcx, rsi
0x1400bce85  call    GetPriorityFromIrpEx
0x1400bce8a  mov     [rdi+88h], eax
0x1400bce90  xor     eax, eax
0x1400bce92  mov     [rdi+18h], rax
0x1400bce96  mov     [rdi+20h], rax
0x1400bce9a  mov     [rdi+28h], rax
0x1400bce9e  mov     rcx, [r15+8]
0x1400bcea2  call    cs:__imp_MmAreMdlPagesCached
0x1400bcea9  nop     dword ptr [rax+rax+00h]
0x1400bceae  mov     cl, [rsp+0A8h+arg_8]
0x1400bceb5  lea     rdx, FveHwAccelInlineWriteCallback
0x1400bcebc  test    eax, eax
0x1400bcebe  mov     byte ptr [rdi+114h], 0
0x1400bcec5  setnz   al
0x1400bcec8  test    cl, cl
0x1400bceca  mov     [rdi+110h], al
0x1400bced0  lea     rax, FveHwAccelInlineReadCallback
0x1400bced7  cmovz   rdx, rax
0x1400bcedb  jz      short loc_1400BCEE5
0x1400bcedd  mov     rax, rbx
0x1400bcee0  mov     rbx, rbp
0x1400bcee3  jmp     short loc_1400BCEE8
0x1400bcee5  mov     rax, rbp
0x1400bcee8  mov     [rsp+0A8h+var_48], rdx
0x1400bceed  mov     r8b, cl
0x1400bcef0  mov     rdx, [rdi+128h]
0x1400bcef7  mov     r9d, 1
0x1400bcefd  mov     [rsp+0A8h+var_58], r12d
0x1400bcf02  mov     rcx, rsi
0x1400bcf05  mov     [rsp+0A8h+var_60], rbx
0x1400bcf0a  mov     [rsp+0A8h+var_68], r12d
0x1400bcf0f  mov     [rsp+0A8h+var_70], rax
0x1400bcf14  mov     rax, [rsp+0A8h+arg_18]
0x1400bcf1c  mov     [rsp+0A8h+var_78], rax
0x1400bcf21  mov     rax, [rdi+130h]
0x1400bcf28  mov     qword ptr [rsp+0A8h+Priority], rdi
0x1400bcf2d  mov     [rsp+0A8h+Irp], rax
0x1400bcf32  call    FveHwAccelInitializeWorkRequest
0x1400bcf37  mov     ebx, eax
0x1400bcf39  test    eax, eax
0x1400bcf3b  js      loc_1400BD03F
0x1400bcf41  cmp     [rsp+0A8h+arg_8], 0
0x1400bcf49  mov     rcx, [rdi+128h]
0x1400bcf50  mov     [rcx+80h], rbp
0x1400bcf57  mov     rcx, [rdi+128h]
0x1400bcf5e  mov     [rcx+90h], r14
0x1400bcf65  mov     rcx, [rdi+128h]
0x1400bcf6c  mov     [rcx+88h], r13b
0x1400bcf73  mov     rdx, [rdi+128h]
0x1400bcf7a  mov     rcx, [r15+8]
0x1400bcf7e  mov     [rdx+98h], rcx
0x1400bcf85  jz      short loc_1400BCFB7
0x1400bcf87  mov     rax, ds:0FFFFF78000000008h
0x1400bcf91  mov     rcx, rsi
0x1400bcf94  mov     rdx, [rdi+128h]
0x1400bcf9b  mov     [rdi+20h], rax
0x1400bcf9f  mov     [rdi+28h], r12d
0x1400bcfa3  call    FveHwAccelSubmitCryptoWork
0x1400bcfa8  mov     ebx, eax
0x1400bcfaa  test    eax, eax
0x1400bcfac  js      loc_1400BD03F
0x1400bcfb2  jmp     loc_1400BD038
0x1400bcfb7  mov     rax, [r15+0B8h]
0x1400bcfbe  lea     rcx, FveHwAccelInlineReadCompletionRoutine
0x1400bcfc5  mov     [r15+8], r14
0x1400bcfc9  lea     rdx, FVE_PERF_READ_SUBREQUEST_START
0x1400bcfd0  mov     r8, r15
0x1400bcfd3  movups  xmm0, xmmword ptr [rax]
0x1400bcfd6  movups  xmmword ptr [rax-48h], xmm0
0x1400bcfda  movups  xmm1, xmmword ptr [rax+10h]
0x1400bcfde  movups  xmmword ptr [rax-38h], xmm1
0x1400bcfe2  movups  xmm0, xmmword ptr [rax+20h]
0x1400bcfe6  movups  xmmword ptr [rax-28h], xmm0
0x1400bcfea  movsd   xmm1, qword ptr [rax+30h]
0x1400bcfef  movsd   qword ptr [rax-18h], xmm1
0x1400bcff4  mov     byte ptr [rax-45h], 0
0x1400bcff8  mov     rax, ds:0FFFFF78000000008h
0x1400bd002  mov     [rdi+18h], rax
0x1400bd006  mov     [rdi+2Ch], r12d
0x1400bd00a  mov     rax, [r15+0B8h]
0x1400bd011  mov     [rax-10h], rcx
0x1400bd015  mov     rcx, rsi
0x1400bd018  mov     [rax-8], rdi
0x1400bd01c  mov     byte ptr [rax-45h], 0E0h
0x1400bd020  call    FvePerfTraceDevPtr
0x1400bd025  mov     rcx, [rsi+70h]; DeviceObject
0x1400bd029  mov     rdx, r15; Irp
0x1400bd02c  call    cs:__imp_IofCallDriver
0x1400bd033  nop     dword ptr [rax+rax+00h]
0x1400bd038  xor     edi, edi
0x1400bd03a  xor     ebp, ebp
0x1400bd03c  xor     r14d, r14d
0x1400bd03f  mov     r9, r14
0x1400bd042  mov     byte ptr [rsp+0A8h+Irp], r13b
0x1400bd047  mov     r8, rbp
0x1400bd04a  mov     rdx, rdi
0x1400bd04d  mov     rcx, rsi
0x1400bd050  call    FveReleaseInlineResources
0x1400bd055  mov     eax, ebx
0x1400bd057  mov     rbx, [rsp+0A8h+arg_0]
0x1400bd05f  add     rsp, 70h
0x1400bd063  pop     r15
0x1400bd065  pop     r14
0x1400bd067  pop     r13
0x1400bd069  pop     r12
0x1400bd06b  pop     rdi
0x1400bd06c  pop     rsi
0x1400bd06d  pop     rbp
0x1400bd06e  retn
```
