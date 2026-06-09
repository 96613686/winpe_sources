# FatDeallocateDiskSpace

- ea: `0x1400210d0`
- end: `0x1400216eb`
- name: `FatDeallocateDiskSpace`
- size: `1563`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x140004554`
- `0x140020458`
- `0x140020734`
- `0x140023ad4`
- `0x140034678`
- `0x1400356f0`
- `0x140035e50`
- `0x1400412a8`

## callees

- `0x140001dd8`
- `0x140005288`
- `0x1400210d0`
- `0x140022870`
- `0x140022c48`
- `0x14003f50c`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x1400215f3`
- `ntoskrnl!RtlClearBits` at `0x1400215f3`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140021124`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x14002140e`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x140021124`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x14002140e`
- `ntoskrnl!KeInitializeEvent` at `0x140021199`
- `ntoskrnl!KeInitializeEvent` at `0x140021199`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140021252`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140021252`
- `ntoskrnl!KeClearEvent` at `0x140021295`
- `ntoskrnl!KeClearEvent` at `0x140021295`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400212dc`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400212dc`
- `ntoskrnl!IofCallDriver` at `0x140021302`
- `ntoskrnl!IofCallDriver` at `0x140021302`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002132a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002132a`
- `ntoskrnl!MmUnmapLockedPages` at `0x140021373`
- `ntoskrnl!MmUnmapLockedPages` at `0x14005b12b`
- `ntoskrnl!MmUnmapLockedPages` at `0x140021373`
- `ntoskrnl!MmUnmapLockedPages` at `0x14005b12b`
- `ntoskrnl!IoFreeMdl` at `0x140021382`
- `ntoskrnl!IoFreeMdl` at `0x14005b13b`
- `ntoskrnl!IoFreeMdl` at `0x140021382`
- `ntoskrnl!IoFreeMdl` at `0x14005b13b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400216cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b18f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400216cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b18f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400216b6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400216b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400214da`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400214da`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400213ff`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400213ff`

## pseudocode

```c
void __fastcall FatDeallocateDiskSpace(__int64 a1, __int64 a2, LARGE_MCB *a3, char a4)
{
  LARGE_MCB *v5; // r13
  __int64 v7; // r15
  unsigned int *v8; // r12
  unsigned __int8 v9; // r14
  ULONG v10; // r13d
  __int64 v11; // rcx
  ULONG v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rsi
  PVOID v16; // rax
  ULONG v17; // r15d
  PIRP v18; // rax
  NTSTATUS Status; // eax
  ULONG v20; // eax
  ULONG v21; // esi
  ULONG v22; // r9d
  __int64 v23; // r8
  ULONG v24; // r13d
  ULONG v25; // esi
  LONGLONG v26; // rax
  unsigned int v27; // r14d
  unsigned int *v28; // rdx
  unsigned int v29; // r8d
  unsigned int v30; // ecx
  unsigned int v31; // eax
  unsigned int v32; // r15d
  unsigned int v33; // r8d
  ULONG v34; // r8d
  unsigned int v35; // r15d
  unsigned int *v36; // rcx
  unsigned int j; // edx
  int v38; // r8d
  ULONG Length; // [rsp+44h] [rbp-D4h] BYREF
  ULONG i; // [rsp+48h] [rbp-D0h]
  unsigned __int8 v41; // [rsp+4Ch] [rbp-CCh]
  unsigned __int8 v42; // [rsp+4Dh] [rbp-CBh]
  unsigned int v43; // [rsp+50h] [rbp-C8h]
  unsigned int v44; // [rsp+54h] [rbp-C4h]
  ULONG v45; // [rsp+58h] [rbp-C0h]
  union _LARGE_INTEGER StartingOffset; // [rsp+60h] [rbp-B8h] BYREF
  LONGLONG v47; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE *v48; // [rsp+70h] [rbp-A8h]
  ULONG v49; // [rsp+78h] [rbp-A0h]
  ULONG v50; // [rsp+7Ch] [rbp-9Ch]
  PVOID Buffer; // [rsp+80h] [rbp-98h]
  __int64 v52; // [rsp+88h] [rbp-90h]
  unsigned int *v53; // [rsp+90h] [rbp-88h]
  unsigned int *v54; // [rsp+98h] [rbp-80h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-60h]
  PFAST_MUTEX FastMutex; // [rsp+C0h] [rbp-58h]
  struct _KEVENT Event; // [rsp+C8h] [rbp-50h] BYREF

  v5 = a3;
  v7 = a1;
  StartingOffset.QuadPart = 0;
  Length = 0;
  i = 0;
  v8 = (unsigned int *)(a2 + 378);
  v48 = (_BYTE *)(a2 + 378);
  v9 = *(_BYTE *)(a2 + 378);
  v41 = v9;
  v45 = FsRtlNumberOfRunsInLargeMcb(a3);
  if ( v45 )
  {
    v54 = v8;
    v56 = a2;
    v42 = v9;
    if ( a4 )
    {
      memset(&Event, 0, sizeof(Event));
      IoStatusBlock = 0;
      v52 = 0;
      v49 = 0;
      v50 = 0;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v10 = 0;
      for ( i = 0; v10 < v45; i = v10 )
      {
        FatGetNextMcbEntry(a2, a3, v10, &v47, &StartingOffset, &Length);
        v12 = Length;
        if ( Length <= 0x100000 )
        {
          v12 = -*(unsigned __int16 *)(a2 + 288) & (*(unsigned __int16 *)(a2 + 288) + Length - 1);
          Length = v12;
          v13 = v12;
        }
        else
        {
          v13 = 0x100000;
        }
        v14 = FatBuildZeroMdl(v11, v13);
        v15 = v14;
        v52 = v14;
        if ( !v14 )
          break;
        if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
          v16 = *(PVOID *)(v14 + 24);
        else
          v16 = MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0x40000020u);
        Buffer = v16;
        if ( v16 )
        {
          v17 = *(_DWORD *)(v15 + 40);
          if ( v12 < v17 )
            v17 = v12;
          v50 = v17;
          v49 = v12;
          while ( v12 )
          {
            KeClearEvent(&Event);
            v18 = IoBuildSynchronousFsdRequest(
                    4u,
                    *(PDEVICE_OBJECT *)(a2 + 136),
                    Buffer,
                    v17,
                    &StartingOffset,
                    &Event,
                    &IoStatusBlock);
            if ( !v18 )
              break;
            v18->Tail.Overlay.CurrentStackLocation[-1].Flags |= 4u;
            Status = IofCallDriver(*(PDEVICE_OBJECT *)(a2 + 136), v18);
            if ( Status == 259 )
            {
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              Status = IoStatusBlock.Status;
            }
            if ( Status < 0 )
              break;
            StartingOffset.QuadPart += v17;
            v12 -= v17;
            v49 = v12;
            if ( v12 < v17 )
              v17 = v12;
            v50 = v17;
          }
        }
        if ( (*(_BYTE *)(v15 + 10) & 5) == 1 )
          MmUnmapLockedPages(*(PVOID *)(v15 + 24), (PMDL)v15);
        IoFreeMdl((PMDL)v15);
        ++v10;
      }
      v9 = v41;
      v7 = a1;
      v5 = a3;
    }
    IoStatusBlock.Pointer = (PVOID)(a2 + 624);
    ExAcquireResourceSharedLite((PERESOURCE)(a2 + 624), 1u);
    v20 = FsRtlNumberOfRunsInLargeMcb(v5);
    v45 = v20;
    v21 = 0;
    i = 0;
    LODWORD(Buffer) = v9;
    while ( v21 < v20 )
    {
      FatGetNextMcbEntry(a2, v5, v21, &v47, &StartingOffset, &Length);
      if ( Length == -1 )
        v22 = 1 << (32 - v9);
      else
        v22 = Length >> v9;
      v23 = (unsigned int)((StartingOffset.QuadPart - *(_QWORD *)(a2 + 352)) >> *v48) + 2;
      if ( v22 == 1 )
        FatSetFatEntry(v7, a2, v23, 0);
      else
        FatSetFatRun(v7, a2, v23, v22, 0);
      i = ++v21;
      v20 = v45;
    }
    FastMutex = (PFAST_MUTEX)(a2 + 464);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 464));
    v24 = 0;
    i = 0;
    while ( 1 )
    {
      if ( v24 >= v45 )
      {
        ExReleaseFastMutexUnsafe(FastMutex);
        ExReleaseResourceLite((PERESOURCE)IoStatusBlock.Pointer);
        return;
      }
      v44 = 0;
      v43 = 0;
      FatGetNextMcbEntry(a2, a3, v24, &v47, &StartingOffset, &Length);
      if ( Length == -1 )
        v25 = 1 << (32 - v9);
      else
        v25 = Length >> v9;
      v26 = (StartingOffset.QuadPart - *(_QWORD *)(a2 + 352)) >> *v48;
      v47 = v26;
      v27 = v26 + 2;
      v28 = *(unsigned int **)(a2 + 232);
      v54 = v28;
      v53 = v28;
      v29 = v28[1];
      if ( (int)v26 + 2 > v29 )
        goto LABEL_57;
      v30 = v27 + v25 - 1;
      v31 = *v28;
      if ( v30 >= *v28 )
        break;
LABEL_56:
      LODWORD(v26) = v47;
LABEL_57:
      v36 = *(unsigned int **)(v56 + 224);
      if ( *(_BYTE *)(a2 + 376) == 32 )
        v36 += 3 * ((unsigned __int64)(unsigned int)v26 >> 16);
      v53 = v36;
      v44 = v27;
      for ( j = v25; ; j -= v38 )
      {
        v43 = j;
        if ( !j )
          break;
        v38 = j;
        if ( v36[1] - v27 + 1 < j )
          v38 = v36[1] - v27 + 1;
        v36[2] += v38;
        if ( j != v38 )
        {
          v36 += 3;
          v53 = v36;
          v27 = *v36;
          v44 = *v36;
        }
      }
      *(_DWORD *)(a2 + 368) += v25;
LABEL_67:
      i = ++v24;
      v9 = (unsigned __int8)Buffer;
    }
    if ( v27 < v31 )
    {
      if ( v30 > v29 )
      {
LABEL_46:
        v44 = *v28;
        v32 = v31;
        v33 = v29 - v31;
        goto LABEL_52;
      }
      if ( v27 < v31 )
      {
        v29 = v27 + v25 - 1;
        goto LABEL_46;
      }
    }
    v32 = v27;
    v44 = v27;
    if ( v30 <= v29 )
    {
      v34 = v25;
      v43 = v25;
LABEL_53:
      if ( !v34 )
        goto LABEL_67;
      RtlClearBits((PRTL_BITMAP)(a2 + 448), v32 - v31, v34);
      v35 = v32 - *v54 + 2;
      if ( v35 < *(_DWORD *)(a2 + 760) )
        *(_DWORD *)(a2 + 760) = v35;
      goto LABEL_56;
    }
    v33 = v29 - v27;
LABEL_52:
    v34 = v33 + 1;
    v43 = v34;
    goto LABEL_53;
  }
}

```

## disassembly

```asm
0x1400210d0  mov     [rsp+Mcb], r8
0x1400210d5  mov     [rsp+arg_8], rdx
0x1400210da  mov     [rsp+arg_0], rcx
0x1400210df  push    rbx
0x1400210e0  push    rsi
0x1400210e1  push    rdi
0x1400210e2  push    r12
0x1400210e4  push    r13
0x1400210e6  push    r14
0x1400210e8  push    r15
0x1400210ea  sub     rsp, 0E0h
0x1400210f1  mov     sil, r9b
0x1400210f4  mov     r13, r8
0x1400210f7  mov     rdi, rdx
0x1400210fa  mov     r15, rcx
0x1400210fd  xor     ebx, ebx
0x1400210ff  mov     qword ptr [rsp+118h+StartingOffset], rbx
0x140021104  mov     [rsp+118h+Length], ebx
0x140021108  mov     [rsp+118h+var_D0], ebx
0x14002110c  lea     r12, [rdx+17Ah]
0x140021113  mov     [rsp+118h+var_A8], r12
0x140021118  mov     r14b, [r12]
0x14002111c  mov     [rsp+118h+var_CC], r14b
0x140021121  mov     rcx, r8; Mcb
0x140021124  call    cs:__imp_FsRtlNumberOfRunsInLargeMcb
0x14002112b  nop     dword ptr [rax+rax+00h]
0x140021130  mov     [rsp+118h+var_C0], eax
0x140021134  test    eax, eax
0x140021136  jz      loc_1400216D7
0x14002113c  mov     [rsp+118h+var_80], r12
0x140021144  mov     [rsp+118h+var_60], rdi
0x14002114c  mov     [rsp+118h+var_D8], r14b
0x140021151  mov     [rsp+118h+var_CB], r14b
0x140021156  test    sil, sil
0x140021159  jz      loc_1400213E4
0x14002115f  xorps   xmm0, xmm0
0x140021162  xor     eax, eax
0x140021164  movups  xmmword ptr [rsp+118h+Event.Header], xmm0
0x14002116c  mov     [rsp+118h+Event.Header.WaitListHead.Blink], rax
0x140021174  movups  xmmword ptr [rsp+118h+var_78], xmm0
0x14002117c  mov     [rsp+118h+var_90], rbx
0x140021184  mov     [rsp+118h+var_A0], ebx
0x140021188  mov     [rsp+118h+var_9C], ebx
0x14002118c  xor     r8d, r8d; State
0x14002118f  xor     edx, edx; Type
0x140021191  lea     rcx, [rsp+118h+Event]; Event
0x140021199  call    cs:__imp_KeInitializeEvent
0x1400211a0  nop     dword ptr [rax+rax+00h]
0x1400211a5  mov     r13d, ebx
0x1400211a8  mov     [rsp+118h+var_D0], ebx
0x1400211ac  lea     r12d, [rbx+1]
0x1400211b0  cmp     r13d, [rsp+118h+var_C0]
0x1400211b5  jnb     loc_14002139B
0x1400211bb  lea     rax, [rsp+118h+Length]
0x1400211c0  mov     qword ptr [rsp+118h+Priority], rax
0x1400211c5  lea     rax, [rsp+118h+StartingOffset]
0x1400211ca  mov     qword ptr [rsp+118h+BugCheckOnFailure], rax
0x1400211cf  lea     r9, [rsp+118h+var_B0]
0x1400211d4  mov     r8d, r13d
0x1400211d7  mov     rdx, [rsp+118h+Mcb]
0x1400211df  mov     rcx, rdi
0x1400211e2  call    FatGetNextMcbEntry
0x1400211e7  mov     r14d, [rsp+118h+Length]
0x1400211ec  cmp     r14d, 100000h
0x1400211f3  jbe     short loc_1400211FC
0x1400211f5  mov     edx, 100000h
0x1400211fa  jmp     short loc_140021216
0x1400211fc  movzx   eax, word ptr [rdi+120h]
0x140021203  dec     r14d
0x140021206  add     r14d, eax
0x140021209  neg     eax
0x14002120b  and     r14d, eax
0x14002120e  mov     [rsp+118h+Length], r14d
0x140021213  mov     edx, r14d
0x140021216  call    FatBuildZeroMdl
0x14002121b  mov     rsi, rax
0x14002121e  mov     [rsp+118h+var_90], rax
0x140021226  test    rax, rax
0x140021229  jz      loc_14002139B
0x14002122f  test    byte ptr [rax+0Ah], 5
0x140021233  jz      short loc_14002123B
0x140021235  mov     rax, [rax+18h]
0x140021239  jmp     short loc_14002125E
0x14002123b  mov     [rsp+118h+Priority], 40000020h; Priority
0x140021243  mov     [rsp+118h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x140021247  xor     r9d, r9d; RequestedAddress
0x14002124a  mov     r8d, r12d; CacheType
0x14002124d  xor     edx, edx; AccessMode
0x14002124f  mov     rcx, rsi; MemoryDescriptorList
0x140021252  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140021259  nop     dword ptr [rax+rax+00h]
0x14002125e  mov     [rsp+118h+Buffer], rax
0x140021266  test    rax, rax
0x140021269  jz      loc_140021362
0x14002126f  mov     r15d, [rsi+28h]
0x140021273  cmp     r14d, r15d
0x140021276  cmovb   r15d, r14d
0x14002127a  mov     [rsp+118h+var_9C], r15d
0x14002127f  mov     [rsp+118h+var_A0], r14d
0x140021284  test    r14d, r14d
0x140021287  jz      loc_140021362
0x14002128d  lea     rcx, [rsp+118h+Event]; Event
0x140021295  call    cs:__imp_KeClearEvent
0x14002129c  nop     dword ptr [rax+rax+00h]
0x1400212a1  lea     rax, [rsp+118h+var_78]
0x1400212a9  mov     [rsp+118h+IoStatusBlock], rax; IoStatusBlock
0x1400212ae  lea     rax, [rsp+118h+Event]
0x1400212b6  mov     qword ptr [rsp+118h+Priority], rax; Event
0x1400212bb  lea     rax, [rsp+118h+StartingOffset]
0x1400212c0  mov     qword ptr [rsp+118h+BugCheckOnFailure], rax; StartingOffset
0x1400212c5  mov     r9d, r15d; Length
0x1400212c8  mov     r8, [rsp+118h+Buffer]; Buffer
0x1400212d0  mov     rdx, [rdi+88h]; DeviceObject
0x1400212d7  mov     ecx, 4; MajorFunction
0x1400212dc  call    cs:__imp_IoBuildSynchronousFsdRequest
0x1400212e3  nop     dword ptr [rax+rax+00h]
0x1400212e8  test    rax, rax
0x1400212eb  jz      short loc_140021362
0x1400212ed  mov     rcx, [rax+0B8h]
0x1400212f4  or      byte ptr [rcx-46h], 4
0x1400212f8  mov     rdx, rax; Irp
0x1400212fb  mov     rcx, [rdi+88h]; DeviceObject
0x140021302  call    cs:__imp_IofCallDriver
0x140021309  nop     dword ptr [rax+rax+00h]
0x14002130e  cmp     eax, 103h
0x140021313  jnz     short loc_14002133D
0x140021315  mov     qword ptr [rsp+118h+BugCheckOnFailure], rbx; Timeout
0x14002131a  xor     r9d, r9d; Alertable
0x14002131d  xor     r8d, r8d; WaitMode
0x140021320  xor     edx, edx; WaitReason
0x140021322  lea     rcx, [rsp+118h+Event]; Object
0x14002132a  call    cs:__imp_KeWaitForSingleObject
0x140021331  nop     dword ptr [rax+rax+00h]
0x140021336  mov     eax, dword ptr [rsp+118h+var_78]
0x14002133d  test    eax, eax
0x14002133f  js      short loc_140021362
0x140021341  mov     eax, r15d
0x140021344  add     qword ptr [rsp+118h+StartingOffset], rax
0x140021349  sub     r14d, r15d
0x14002134c  mov     [rsp+118h+var_A0], r14d
0x140021351  cmp     r14d, r15d
0x140021354  cmovb   r15d, r14d
0x140021358  mov     [rsp+118h+var_9C], r15d
0x14002135d  jmp     loc_140021284
0x140021362  mov     al, [rsi+0Ah]
0x140021365  and     al, 5
0x140021367  cmp     al, r12b
0x14002136a  jnz     short loc_14002137F
0x14002136c  mov     rdx, rsi; MemoryDescriptorList
0x14002136f  mov     rcx, [rsi+18h]; BaseAddress
0x140021373  call    cs:__imp_MmUnmapLockedPages
0x14002137a  nop     dword ptr [rax+rax+00h]
0x14002137f  mov     rcx, rsi; Mdl
0x140021382  call    cs:__imp_IoFreeMdl
0x140021389  nop     dword ptr [rax+rax+00h]
0x14002138e  add     r13d, r12d
0x140021391  mov     [rsp+118h+var_D0], r13d
0x140021396  jmp     loc_1400211B0
0x14002139b  mov     r14b, [rsp+118h+var_CC]
0x1400213a0  mov     r15, [rsp+118h+arg_0]
0x1400213a8  mov     r13, [rsp+118h+Mcb]
0x1400213b0  jmp     short loc_1400213EA
0x1400213b2  xor     ebx, ebx
0x1400213b4  lea     r12d, [rbx+1]
0x1400213b8  mov     rdi, [rsp+118h+arg_8]
0x1400213c0  mov     rax, [rsp+118h+var_80]
0x1400213c8  mov     [rsp+118h+var_A8], rax
0x1400213cd  mov     r14b, [rsp+118h+var_CB]
0x1400213d2  mov     r15, [rsp+118h+arg_0]
0x1400213da  mov     r13, [rsp+118h+Mcb]
0x1400213e2  jmp     short loc_1400213EA
0x1400213e4  mov     r12d, 1
0x1400213ea  lea     rax, [rdi+270h]
0x1400213f1  mov     qword ptr [rsp+118h+var_78], rax
0x1400213f9  mov     dl, r12b; Wait
0x1400213fc  mov     rcx, rax; Resource
0x1400213ff  call    cs:__imp_ExAcquireResourceSharedLite
0x140021406  nop     dword ptr [rax+rax+00h]
0x14002140b  mov     rcx, r13; Mcb
0x14002140e  call    cs:__imp_FsRtlNumberOfRunsInLargeMcb
0x140021415  nop     dword ptr [rax+rax+00h]
0x14002141a  mov     [rsp+118h+var_C0], eax
0x14002141e  mov     esi, ebx
0x140021420  mov     [rsp+118h+var_D0], ebx
0x140021424  movzx   r14d, r14b
0x140021428  mov     dword ptr [rsp+118h+Buffer], r14d
0x140021430  cmp     esi, eax
0x140021432  jnb     loc_1400214C8
0x140021438  lea     rax, [rsp+118h+Length]
0x14002143d  mov     qword ptr [rsp+118h+Priority], rax
0x140021442  lea     rax, [rsp+118h+StartingOffset]
0x140021447  mov     qword ptr [rsp+118h+BugCheckOnFailure], rax
0x14002144c  lea     r9, [rsp+118h+var_B0]
0x140021451  mov     r8d, esi
0x140021454  mov     rdx, r13
0x140021457  mov     rcx, rdi
0x14002145a  call    FatGetNextMcbEntry
0x14002145f  mov     r9d, [rsp+118h+Length]
0x140021464  cmp     r9d, 0FFFFFFFFh
0x140021468  jnz     short loc_14002147A
0x14002146a  mov     ecx, 20h ; ' '
0x14002146f  sub     ecx, r14d
0x140021472  mov     r9d, r12d
0x140021475  shl     r9d, cl
0x140021478  jmp     short loc_140021480
0x14002147a  mov     ecx, r14d
0x14002147d  shr     r9d, cl
0x140021480  mov     r8, qword ptr [rsp+118h+StartingOffset]
0x140021485  sub     r8, [rdi+160h]
0x14002148c  mov     rcx, [rsp+118h+var_A8]
0x140021491  mov     cl, [rcx]
0x140021493  sar     r8, cl
0x140021496  add     r8d, 2
0x14002149a  mov     rdx, rdi
0x14002149d  mov     rcx, r15
0x1400214a0  cmp     r9d, r12d
0x1400214a3  jnz     short loc_1400214AF
0x1400214a5  xor     r9d, r9d
0x1400214a8  call    FatSetFatEntry
0x1400214ad  jmp     short loc_1400214B8
0x1400214af  mov     byte ptr [rsp+118h+BugCheckOnFailure], bl
0x1400214b3  call    FatSetFatRun
0x1400214b8  add     esi, r12d
0x1400214bb  mov     [rsp+118h+var_D0], esi
0x1400214bf  mov     eax, [rsp+118h+var_C0]
0x1400214c3  jmp     loc_140021430
0x1400214c8  lea     rsi, [rdi+1D0h]
0x1400214cf  mov     [rsp+118h+FastMutex], rsi
0x1400214d7  mov     rcx, rsi; FastMutex
0x1400214da  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400214e1  nop     dword ptr [rax+rax+00h]
0x1400214e6  mov     r13d, ebx
0x1400214e9  mov     [rsp+118h+var_D0], ebx
0x1400214ed  cmp     r13d, [rsp+118h+var_C0]
0x1400214f2  jnb     loc_1400216AE
0x1400214f8  mov     [rsp+118h+var_C4], ebx
0x1400214fc  mov     [rsp+118h+var_C8], ebx
0x140021500  lea     rax, [rsp+118h+Length]
0x140021505  mov     qword ptr [rsp+118h+Priority], rax
0x14002150a  lea     rax, [rsp+118h+StartingOffset]
0x14002150f  mov     qword ptr [rsp+118h+BugCheckOnFailure], rax
0x140021514  lea     r9, [rsp+118h+var_B0]
0x140021519  mov     r8d, r13d
0x14002151c  mov     rdx, [rsp+118h+Mcb]
0x140021524  mov     rcx, rdi
0x140021527  call    FatGetNextMcbEntry
0x14002152c  mov     esi, [rsp+118h+Length]
0x140021530  cmp     esi, 0FFFFFFFFh
0x140021533  jnz     short loc_140021544
0x140021535  mov     ecx, 20h ; ' '
0x14002153a  sub     ecx, r14d
0x14002153d  mov     esi, r12d
0x140021540  shl     esi, cl
0x140021542  jmp     short loc_140021549
0x140021544  mov     ecx, r14d
0x140021547  shr     esi, cl
0x140021549  mov     rax, qword ptr [rsp+118h+StartingOffset]
0x14002154e  sub     rax, [rdi+160h]
0x140021555  mov     rcx, [rsp+118h+var_A8]
0x14002155a  mov     cl, [rcx]
0x14002155c  sar     rax, cl
0x14002155f  mov     [rsp+118h+var_B0], rax
0x140021564  lea     r14d, [rax+2]
0x140021568  mov     rdx, [rdi+0E8h]
0x14002156f  mov     [rsp+118h+var_80], rdx
0x140021577  mov     [rsp+118h+var_88], rdx
0x14002157f  mov     r8d, [rdx+4]
0x140021583  cmp     r14d, r8d
0x140021586  ja      loc_140021623
0x14002158c  lea     ecx, [rsi-1]
0x14002158f  add     ecx, r14d
0x140021592  mov     eax, [rdx]
0x140021594  cmp     ecx, eax
0x140021596  jb      loc_14002161E
0x14002159c  cmp     r14d, eax
0x14002159f  jnb     short loc_1400215BC
0x1400215a1  cmp     ecx, r8d
0x1400215a4  jbe     short loc_1400215B2
0x1400215a6  mov     [rsp+118h+var_C4], eax
0x1400215aa  mov     r15d, eax
0x1400215ad  sub     r8d, eax
0x1400215b0  jmp     short loc_1400215D5
0x1400215b2  cmp     r14d, eax
0x1400215b5  jnb     short loc_1400215BC
0x1400215b7  mov     r8d, ecx
0x1400215ba  jmp     short loc_1400215A6
0x1400215bc  mov     r15d, r14d
0x1400215bf  mov     [rsp+118h+var_C4], r14d
0x1400215c4  cmp     ecx, r8d
0x1400215c7  ja      short loc_1400215D2
0x1400215c9  mov     r8d, esi
0x1400215cc  mov     [rsp+118h+var_C8], esi
0x1400215d0  jmp     short loc_1400215DD
0x1400215d2  sub     r8d, r14d
0x1400215d5  add     r8d, r12d; NumberToClear
0x1400215d8  mov     [rsp+118h+var_C8], r8d
0x1400215dd  test    r8d, r8d
0x1400215e0  jnz     short loc_1400215E7
0x1400215e2  jmp     loc_140021699
0x1400215e7  mov     edx, r15d
  ... truncated ...
```
