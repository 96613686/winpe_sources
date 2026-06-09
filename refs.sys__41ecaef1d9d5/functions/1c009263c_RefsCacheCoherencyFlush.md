# RefsCacheCoherencyFlush

- ea: `0x1c009263c`
- end: `0x1c0092946`
- name: `RefsCacheCoherencyFlush`
- size: `778`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1c000a190`
- `0x1c000dc80`
- `0x1c0093e78`
- `0x1c018e078`
- `0x1c01ad7d0`

## callees

- `0x1c0001d74`
- `0x1c0004a5c`
- `0x1c000f770`
- `0x1c005c580`
- `0x1c0068168`
- `0x1c009263c`
- `0x1c018fa30`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0092689`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0092689`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c009270f`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c009270f`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c0092773`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c00927bc`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c0092773`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x1c00927bc`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c0092797`
- `ntoskrnl!KeDelayExecutionThread` at `0x1c0092797`

## string_xrefs

- `0x1c0092840`: `CacheSup.c`
- `0x1c00928cc`: `CacheSup.c`

## pseudocode

```c
__int64 __fastcall RefsCacheCoherencyFlush(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        char a6,
        char a7)
{
  unsigned __int64 v7; // r14
  __int64 v9; // rsi
  char v10; // r13
  int v11; // r15d
  PIRP TopLevelIrp; // rdx
  struct _IRP *MasterIrp; // rax
  ULONG Flags; // edi
  union _LARGE_INTEGER *v15; // r12
  ULONG v16; // r13d
  __int64 v17; // rcx
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+30h] [rbp-18h] BYREF
  char v21; // [rsp+98h] [rbp+50h]
  char v22; // [rsp+A0h] [rbp+58h]
  __int64 v23; // [rsp+A8h] [rbp+60h] BYREF

  v7 = a5;
  v23 = a4;
  v9 = a1;
  v10 = 0;
  v22 = 0;
  v11 = 0;
  v21 = 0;
  IoStatus = 0;
  LOBYTE(a5) = 0;
  if ( a6 )
  {
    if ( a4 < 0 )
    {
      RefsAcquireEofLock(a1, a3);
      v23 = *(_QWORD *)(a3 + 32);
      v22 = 1;
    }
    Flags = 0;
  }
  else
  {
    TopLevelIrp = IoGetTopLevelIrp();
    MasterIrp = TopLevelIrp->AssociatedIrp.MasterIrp;
    if ( MasterIrp && (!HIBYTE(TopLevelIrp->Type) || (HIDWORD(MasterIrp->ThreadListEntry.Flink->Flink) & 0x200) == 0) )
      LOBYTE(TopLevelIrp->Type) = 0;
    Flags = 3;
  }
  if ( ++*(_DWORD *)(a3 + 168) > (unsigned int)dword_1C012E6B4 )
  {
    if ( *(_DWORD *)(a3 + 144) == *(_DWORD *)(a3 + 140)
      && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), 0) )
    {
      v10 = 1;
      Flags = 0;
      v21 = 1;
    }
    *(_DWORD *)(a3 + 168) = 0;
  }
  if ( v7 )
  {
    v15 = (union _LARGE_INTEGER *)&v23;
    if ( v10 )
      v15 = 0;
    while ( 1 )
    {
      v16 = v7;
      if ( v7 > 0xFFFFF000 )
        v16 = -4096;
      CcCoherencyFlushAndPurgeCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), v15, v16, &IoStatus, Flags);
      if ( IoStatus.Status != 277 )
        goto LABEL_42;
      KeDelayExecutionThread(0, 0, &RefsShortDelay);
      CcCoherencyFlushAndPurgeCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 240) + 8LL), v15, v16, &IoStatus, Flags);
      if ( IoStatus.Status != 277 )
        goto LABEL_42;
      if ( a7 )
      {
        if ( a6 && *(_DWORD *)(a3 + 160) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_34beff5d47f330610d64a67e096d2140_Traceguids,
              3221226549LL);
          }
          if ( RefsStatusDebugEnabled )
            RefsStatusDebug(-1073740747);
          IoStatus.Status = -1073740747;
          goto LABEL_42;
        }
        _InterlockedOr((volatile signed __int32 *)(a3 + 136), 0x40000000u);
      }
      else if ( v11 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_34beff5d47f330610d64a67e096d2140_Traceguids,
            3221226549LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073740747);
        v11 = -1073740747;
      }
      IoStatus.Status = 0;
LABEL_42:
      if ( !v21 )
      {
        v23 += v16;
        v7 -= v16;
        if ( v7 )
          continue;
      }
      v9 = a1;
      break;
    }
  }
  if ( v22 )
    RefsReleaseEofLock(v9, a3);
  RefsNormalizeAndCleanupTransaction(v9, &IoStatus);
  RefsDeleteInternalAttributeStream(v17, a3, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1c009263c  mov     [rsp-40h+arg_8], rdx
0x1c0092641  mov     [rsp-40h+arg_0], rcx
0x1c0092646  push    rbp
0x1c0092647  push    rbx
0x1c0092648  push    rsi
0x1c0092649  push    rdi
0x1c009264a  push    r12
0x1c009264c  push    r13
0x1c009264e  push    r14
0x1c0092650  push    r15
0x1c0092652  mov     rbp, rsp
0x1c0092655  sub     rsp, 48h
0x1c0092659  mov     r14, [rbp+arg_20]
0x1c009265d  mov     rbx, r8
0x1c0092660  xor     r8d, r8d
0x1c0092663  mov     [rbp+arg_18], r9
0x1c0092667  xorps   xmm0, xmm0
0x1c009266a  mov     rsi, rcx
0x1c009266d  mov     r13b, r8b
0x1c0092670  mov     [rbp+arg_10], r8b
0x1c0092674  mov     r15d, r8d
0x1c0092677  mov     byte ptr [rbp+arg_8], r8b
0x1c009267b  movups  xmmword ptr [rbp+IoStatus], xmm0
0x1c009267f  mov     byte ptr [rbp+arg_20], r8b
0x1c0092683  cmp     [rbp+arg_28], r8b
0x1c0092687  jnz     short loc_1C00926C1
0x1c0092689  call    cs:__imp_IoGetTopLevelIrp
0x1c0092690  nop     dword ptr [rax+rax+00h]
0x1c0092695  mov     rdx, rax
0x1c0092698  xor     r8d, r8d
0x1c009269b  mov     rax, [rax+18h]
0x1c009269f  test    rax, rax
0x1c00926a2  jz      short loc_1C00926BA
0x1c00926a4  cmp     [rdx+1], r8b
0x1c00926a8  jz      short loc_1C00926B7
0x1c00926aa  mov     rax, [rax+20h]
0x1c00926ae  test    dword ptr [rax+4], 200h
0x1c00926b5  jnz     short loc_1C00926BA
0x1c00926b7  mov     [rdx], r8b
0x1c00926ba  mov     edi, 3
0x1c00926bf  jmp     short loc_1C00926E0
0x1c00926c1  test    r9, r9
0x1c00926c4  jns     short loc_1C00926DD
0x1c00926c6  mov     rdx, rbx
0x1c00926c9  call    RefsAcquireEofLock
0x1c00926ce  mov     rax, [rbx+20h]
0x1c00926d2  xor     r8d, r8d
0x1c00926d5  mov     [rbp+arg_18], rax
0x1c00926d9  mov     [rbp+arg_10], 1
0x1c00926dd  mov     edi, r8d
0x1c00926e0  inc     dword ptr [rbx+0A8h]
0x1c00926e6  mov     eax, [rbx+0A8h]
0x1c00926ec  cmp     eax, cs:dword_1C012E6B4
0x1c00926f2  jbe     short loc_1C0092733
0x1c00926f4  mov     eax, [rbx+8Ch]
0x1c00926fa  cmp     [rbx+90h], eax
0x1c0092700  jnz     short loc_1C009272C
0x1c0092702  mov     rcx, [rbx+0F0h]
0x1c0092709  xor     edx, edx; NewFileSize
0x1c009270b  add     rcx, 8; SectionPointer
0x1c009270f  call    cs:__imp_MmCanFileBeTruncated
0x1c0092716  nop     dword ptr [rax+rax+00h]
0x1c009271b  xor     r8d, r8d
0x1c009271e  test    al, al
0x1c0092720  jz      short loc_1C009272C
0x1c0092722  mov     r13b, 1
0x1c0092725  mov     edi, r8d
0x1c0092728  mov     byte ptr [rbp+arg_8], r13b
0x1c009272c  mov     [rbx+0A8h], r8d
0x1c0092733  test    r14, r14
0x1c0092736  jz      loc_1C0092909
0x1c009273c  mov     sil, byte ptr [rbp+arg_8]
0x1c0092740  lea     r12, [rbp+arg_18]
0x1c0092744  test    r13b, r13b
0x1c0092747  mov     ecx, 0FFFFF000h
0x1c009274c  cmovnz  r12, r8
0x1c0092750  cmp     r14, rcx
0x1c0092753  mov     [rsp+48h+Flags], edi; Flags
0x1c0092757  mov     r13d, r14d
0x1c009275a  lea     r9, [rbp+IoStatus]; IoStatus
0x1c009275e  cmova   r13d, ecx
0x1c0092762  mov     rdx, r12; FileOffset
0x1c0092765  mov     rcx, [rbx+0F0h]
0x1c009276c  mov     r8d, r13d; Length
0x1c009276f  add     rcx, 8; SectionObjectPointer
0x1c0092773  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x1c009277a  nop     dword ptr [rax+rax+00h]
0x1c009277f  cmp     dword ptr [rbp+IoStatus], 115h
0x1c0092786  jnz     loc_1C00928E8
0x1c009278c  lea     r8, RefsShortDelay; Interval
0x1c0092793  xor     edx, edx; Alertable
0x1c0092795  xor     ecx, ecx; WaitMode
0x1c0092797  call    cs:__imp_KeDelayExecutionThread
0x1c009279e  nop     dword ptr [rax+rax+00h]
0x1c00927a3  mov     rcx, [rbx+0F0h]
0x1c00927aa  lea     r9, [rbp+IoStatus]; IoStatus
0x1c00927ae  add     rcx, 8; SectionObjectPointer
0x1c00927b2  mov     [rsp+48h+Flags], edi; Flags
0x1c00927b6  mov     r8d, r13d; Length
0x1c00927b9  mov     rdx, r12; FileOffset
0x1c00927bc  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x1c00927c3  nop     dword ptr [rax+rax+00h]
0x1c00927c8  xor     r8d, r8d
0x1c00927cb  cmp     dword ptr [rbp+IoStatus], 115h
0x1c00927d2  jnz     loc_1C00928EB
0x1c00927d8  cmp     [rbp+arg_30], r8b
0x1c00927dc  jz      loc_1C0092874
0x1c00927e2  cmp     [rbp+arg_28], r8b
0x1c00927e6  jz      short loc_1C0092860
0x1c00927e8  cmp     [rbx+0A0h], r8d
0x1c00927ef  jz      short loc_1C0092860
0x1c00927f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00927f8  lea     rax, WPP_GLOBAL_Control
0x1c00927ff  cmp     rcx, rax
0x1c0092802  jz      short loc_1C0092830
0x1c0092804  test    dword ptr [rcx+2Ch], 100h
0x1c009280b  jz      short loc_1C0092830
0x1c009280d  cmp     byte ptr [rcx+29h], 4
0x1c0092811  jb      short loc_1C0092830
0x1c0092813  mov     rcx, [rcx+18h]
0x1c0092817  lea     edx, [r8+13h]
0x1c009281b  lea     r8, WPP_34beff5d47f330610d64a67e096d2140_Traceguids
0x1c0092822  mov     r9d, 0C0000435h
0x1c0092828  call    WPP_SF_D
0x1c009282d  xor     r8d, r8d
0x1c0092830  mov     al, cs:RefsStatusDebugEnabled
0x1c0092836  test    al, al
0x1c0092838  jz      short loc_1C0092854
0x1c009283a  mov     r8d, 549h
0x1c0092840  lea     rdx, aCachesupC; "CacheSup.c"
0x1c0092847  mov     ecx, 0C0000435h; Status
0x1c009284c  call    RefsStatusDebug
0x1c0092851  xor     r8d, r8d
0x1c0092854  mov     dword ptr [rbp+IoStatus], 0C0000435h
0x1c009285b  jmp     loc_1C00928EB
0x1c0092860  lock or dword ptr [rbx+88h], 40000000h
0x1c009286b  mov     al, byte ptr [rbp+arg_20]
0x1c009286e  mov     dword ptr [rbp+IoStatus], r8d
0x1c0092872  jmp     short loc_1C00928EB
0x1c0092874  mov     al, byte ptr [rbp+arg_20]
0x1c0092877  test    r15d, r15d
0x1c009287a  js      short loc_1C009286E
0x1c009287c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0092883  lea     rax, WPP_GLOBAL_Control
0x1c009288a  cmp     rcx, rax
0x1c009288d  jz      short loc_1C00928BC
0x1c009288f  test    dword ptr [rcx+2Ch], 100h
0x1c0092896  jz      short loc_1C00928BC
0x1c0092898  cmp     byte ptr [rcx+29h], 4
0x1c009289c  jb      short loc_1C00928BC
0x1c009289e  mov     rcx, [rcx+18h]
0x1c00928a2  lea     r8, WPP_34beff5d47f330610d64a67e096d2140_Traceguids
0x1c00928a9  mov     edx, 14h
0x1c00928ae  mov     r9d, 0C0000435h
0x1c00928b4  call    WPP_SF_D
0x1c00928b9  xor     r8d, r8d
0x1c00928bc  mov     al, cs:RefsStatusDebugEnabled
0x1c00928c2  test    al, al
0x1c00928c4  jz      short loc_1C00928E0
0x1c00928c6  mov     r8d, 57Bh
0x1c00928cc  lea     rdx, aCachesupC; "CacheSup.c"
0x1c00928d3  mov     ecx, 0C0000435h; Status
0x1c00928d8  call    RefsStatusDebug
0x1c00928dd  xor     r8d, r8d
0x1c00928e0  mov     r15d, 0C0000435h
0x1c00928e6  jmp     short loc_1C009286E
0x1c00928e8  xor     r8d, r8d
0x1c00928eb  test    sil, sil
0x1c00928ee  jnz     short loc_1C0092905
0x1c00928f0  mov     eax, r13d
0x1c00928f3  mov     ecx, 0FFFFF000h
0x1c00928f8  add     [rbp+arg_18], rax
0x1c00928fc  sub     r14, rax
0x1c00928ff  jnz     loc_1C0092750
0x1c0092905  mov     rsi, [rbp+arg_0]
0x1c0092909  cmp     [rbp+arg_10], r8b
0x1c009290d  jz      short loc_1C009291A
0x1c009290f  mov     rdx, rbx
0x1c0092912  mov     rcx, rsi
0x1c0092915  call    RefsReleaseEofLock
0x1c009291a  lea     rdx, [rbp+IoStatus]
0x1c009291e  mov     rcx, rsi
0x1c0092921  call    RefsNormalizeAndCleanupTransaction
0x1c0092926  xor     r8d, r8d
0x1c0092929  mov     rdx, rbx
0x1c009292c  call    RefsDeleteInternalAttributeStream
0x1c0092931  mov     eax, r15d
0x1c0092934  add     rsp, 48h
0x1c0092938  pop     r15
0x1c009293a  pop     r14
0x1c009293c  pop     r13
0x1c009293e  pop     r12
0x1c0092940  pop     rdi
0x1c0092941  pop     rsi
0x1c0092942  pop     rbx
0x1c0092943  pop     rbp
0x1c0092944  retn
```
