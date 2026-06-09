# FltpAllocateIrpCtrlInternal

- ea: `0x18000a360`
- end: `0x18000a802`
- name: `FltpAllocateIrpCtrlInternal`
- size: `1186`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, PSLIST_ENTRY *, int, __int64)`
- caller_count: `12`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180002a40`
- `0x1800034c0`
- `0x180003950`
- `0x180003b40`
- `0x180008000`
- `0x18000a340`
- `0x18000bec0`
- `0x18000c950`
- `0x180018400`
- `0x180019520`
- `0x18001b800`
- `0x180022370`

## callees

- `0x1800016f0`
- `0x18000a360`
- `0x18000c330`
- `0x18001baa0`
- `0x18001e490`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x18002586d`
- `ntoskrnl!ExReleaseFastMutex` at `0x18002586d`
- `ntoskrnl!ExQueueWorkItem` at `0x18000a76c`
- `ntoskrnl!ExQueueWorkItem` at `0x18000a76c`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000a745`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000a745`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x18000a43c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x18000a43c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7a7`
- `ntoskrnl!ExAllocatePool2` at `0x18000a46d`
- `ntoskrnl!ExAllocatePool2` at `0x18000a46d`
- `ntoskrnl!KeInitializeEvent` at `0x18000a4f8`
- `ntoskrnl!KeInitializeEvent` at `0x18000a4f8`
- `ntoskrnl!ExGetPreviousMode` at `0x18000a5b3`
- `ntoskrnl!ExGetPreviousMode` at `0x18000a63a`
- `ntoskrnl!ExGetPreviousMode` at `0x18000a5b3`
- `ntoskrnl!ExGetPreviousMode` at `0x18000a63a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000a55b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000a55b`
- `ntoskrnl!IoGetRequestorProcess` at `0x18000a535`
- `ntoskrnl!IoGetRequestorProcess` at `0x18000a535`
- `ntoskrnl!PsGetProcessId` at `0x18000a54d`
- `ntoskrnl!PsGetProcessId` at `0x18000a54d`

## pseudocode

```c
__int64 __fastcall FltpAllocateIrpCtrlInternal(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        PSLIST_ENTRY *a4,
        int a5,
        __int64 a6)
{
  int v6; // r15d
  __int64 v7; // r13
  __int64 v9; // rax
  __int64 v10; // r14
  unsigned __int8 v11; // bp
  unsigned __int64 v12; // rdi
  unsigned __int8 v13; // r8
  unsigned __int8 v14; // dl
  unsigned __int8 v15; // cl
  unsigned __int16 v16; // r12
  __int64 v17; // r13
  PSLIST_ENTRY Pool2; // rbx
  struct _SLIST_ENTRY *Next; // rcx
  __int64 v20; // rdi
  IRP *v21; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  unsigned int v24; // esi
  __int64 v25; // rcx
  __int64 v26; // rax
  unsigned int v27; // eax
  unsigned __int8 v28; // al
  __int64 BackPocketIrpCtrl; // rax
  unsigned int v33; // [rsp+80h] [rbp+28h]

  v6 = 0;
  v7 = a3;
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 80LL);
  v10 = *(_QWORD *)(v9 + 104);
  v11 = *(_DWORD *)(v9 + 312);
  if ( !v11 )
    v11 = 1;
  if ( (*(_DWORD *)(v10 + 972) & 3) == 3 && v11 < 0xAu )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 4LL * v11 + 712));
    if ( v11 >= 2u )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 976));
      if ( *(_DWORD *)(v10 + 976) > 0x7D0u )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(v10 + 912));
        if ( (*(_DWORD *)(v10 + 968) & 7) == 1 )
        {
          ExQueueWorkItem((PWORK_QUEUE_ITEM)(v10 + 880), DelayedWorkQueue);
          *(_DWORD *)(v10 + 968) |= 2u;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(v10 + 912));
      }
    }
  }
  v12 = *(_QWORD *)(v10 + 680) + ((unsigned __int64)(HIDWORD(KeGetPcr()[1].LockArray) % dword_18003E760) << 6);
  while ( 1 )
  {
    v13 = *(_BYTE *)(v10 + 65);
    if ( v11 > *(_BYTE *)(v10 + 64) )
    {
      v16 = (v11 << 7) + 400;
      goto LABEL_10;
    }
    v6 |= 0x10000000u;
    v14 = v11;
    v15 = *(_BYTE *)(v10 + 65);
    if ( v11 > v13 )
      v15 = *(_BYTE *)(v10 + 64);
    v11 = v15;
    v16 = (v15 << 7) + 400;
    v17 = *(_QWORD *)((v13 < v14 ? 0x10 : 0) + v12);
    _InterlockedIncrement((volatile signed __int32 *)(v17 + 20));
    Pool2 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17);
    if ( !Pool2 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 24));
      v7 = a3;
      goto LABEL_10;
    }
    if ( (*(_DWORD *)(v10 + 972) & 1) == 0 )
      goto LABEL_11;
    if ( *((_QWORD *)&Pool2[16].Next + 1) >= (unsigned __int64)v16 )
      break;
    ExFreePoolWithTag(Pool2, 0);
    v7 = a3;
LABEL_10:
    Pool2 = (PSLIST_ENTRY)ExAllocatePool2(64, v16, 1667845446);
    if ( Pool2 )
      goto LABEL_11;
    v27 = FltpDetermineStaticOperationType(a2, v7);
    v33 = v27;
    if ( v27 == -1 )
    {
      if ( a2 == 1 )
      {
        if ( (*(_BYTE *)(v7 + 71) & 0x20) == 0 )
          goto LABEL_34;
      }
      else if ( a2 != 3 || (*((_BYTE *)FltpOperationFlags + (unsigned __int8)(*(_BYTE *)(v7 + 4) + 22)) & 8) == 0 )
      {
LABEL_34:
        *a4 = 0;
        return 3221225626LL;
      }
      BackPocketIrpCtrl = FltpAllocateBackPocketIrpCtrl(v10, a6);
    }
    else
    {
      BackPocketIrpCtrl = FltpAllocateStaticIrpCtrl(v10, v27);
    }
    Pool2 = (PSLIST_ENTRY)BackPocketIrpCtrl;
    if ( BackPocketIrpCtrl )
    {
      v28 = *(_BYTE *)(BackPocketIrpCtrl + 14);
      if ( v11 > v28 )
        v11 = v28;
      goto LABEL_12;
    }
    if ( v33 + 1 <= 2 )
      goto LABEL_34;
  }
  v16 = *((_QWORD *)&Pool2[16].Next + 1);
LABEL_11:
  memset(Pool2, 0, 0x190u);
  HIDWORD(Pool2->Next) |= v6;
  v7 = a3;
  Pool2[1].Next = Pool2 + 25;
LABEL_12:
  Next = Pool2[1].Next;
  v20 = (__int64)(v12 - *(_QWORD *)(v10 + 680)) >> 6;
  LOWORD(Pool2->Next) = -3836;
  WORD1(Pool2->Next) = v16;
  *((_QWORD *)&Pool2[6].Next + 1) = a1;
  *((_BYTE *)&Pool2->Next + 14) = v11;
  memset(Next, 0, (unsigned __int64)v11 << 7);
  *((_QWORD *)&Pool2[15].Next + 1) = Pool2 + 20;
  KeInitializeEvent((PRKEVENT)(&Pool2[1].Next + 1), SynchronizationEvent, 0);
  if ( a2 == 1 )
  {
    *((_DWORD *)&Pool2[14].Next + 2) |= 1u;
    Pool2[3].Next = (struct _SLIST_ENTRY *)v7;
    FltpMoveIrpToCallbackData(Pool2, v7);
  }
  else if ( a2 )
  {
    v24 = a2 - 2;
    if ( v24 )
    {
      if ( v24 == 1 )
      {
        *((_DWORD *)&Pool2[14].Next + 2) |= 4u;
        Pool2[15].Next = (struct _SLIST_ENTRY *)KeGetCurrentThread();
        *((_BYTE *)&Pool2[19].Next + 8) = ExGetPreviousMode();
        Pool2[3].Next = (struct _SLIST_ENTRY *)v7;
        *(_BYTE *)(*((_QWORD *)&Pool2[15].Next + 1) + 4LL) = *(_BYTE *)(v7 + 4);
        v25 = *((_QWORD *)&Pool2[15].Next + 1);
        *((_BYTE *)&Pool2->Next + 12) = *(_BYTE *)(v25 + 4);
        *(_BYTE *)(v25 + 5) = 0;
        Pool2[7].Next = *(struct _SLIST_ENTRY **)(v7 + 16);
        *((_QWORD *)&Pool2[6].Next + 1) = *(_QWORD *)(v7 + 8);
        v26 = *((_QWORD *)&Pool2[15].Next + 1);
        *(_OWORD *)(v26 + 24) = *(_OWORD *)(v7 + 24);
        *(_OWORD *)(v26 + 40) = *(_OWORD *)(v7 + 40);
        *(_QWORD *)(v26 + 56) = *(_QWORD *)(v7 + 56);
      }
    }
    else
    {
      *((_DWORD *)&Pool2[14].Next + 2) |= 2u;
      Pool2[15].Next = (struct _SLIST_ENTRY *)KeGetCurrentThread();
      *((_BYTE *)&Pool2[19].Next + 8) = ExGetPreviousMode();
    }
  }
  else
  {
    *((_DWORD *)&Pool2[14].Next + 2) |= 0x10001u;
  }
  if ( (*(_DWORD *)(&Pool2[14].Next + 1) & 1) != 0 && (v21 = (IRP *)Pool2[3].Next) != 0 )
  {
    RequestorProcess = IoGetRequestorProcess(v21);
    if ( RequestorProcess )
      LODWORD(RequestorProcess) = (unsigned int)PsGetProcessId(RequestorProcess);
  }
  else
  {
    LODWORD(RequestorProcess) = (unsigned int)PsGetCurrentProcessId();
  }
  HIDWORD(Pool2[14].Next) = (_DWORD)RequestorProcess;
  HIDWORD(Pool2->Next) |= 4u;
  *((_DWORD *)&Pool2->Next + 2) = v20;
  *a4 = Pool2;
  return 0;
}

```

## disassembly

```asm
0x18000a360  mov     [rsp+arg_18], r9
0x18000a365  mov     [rsp+arg_10], r8
0x18000a36a  mov     [rsp+arg_0], rcx
0x18000a36f  push    rbx
0x18000a370  push    rbp
0x18000a371  push    rsi
0x18000a372  push    rdi
0x18000a373  push    r13
0x18000a375  push    r14
0x18000a377  push    r15
0x18000a379  sub     rsp, 20h
0x18000a37d  mov     rax, [rcx+40h]
0x18000a381  xor     r15d, r15d
0x18000a384  mov     edi, 1
0x18000a389  mov     r13, r8
0x18000a38c  mov     esi, edx
0x18000a38e  mov     rax, [rax+50h]
0x18000a392  mov     r14, [rax+68h]
0x18000a396  mov     eax, [rax+138h]
0x18000a39c  movzx   ebp, al
0x18000a39f  cmp     bpl, dil
0x18000a3a2  mov     eax, [r14+3CCh]
0x18000a3a9  cmovb   ebp, edi
0x18000a3ac  and     eax, 3
0x18000a3af  cmp     al, 3
0x18000a3b1  jz      loc_18000A703
0x18000a3b7  mov     eax, gs:1A4h
0x18000a3bf  xor     edx, edx
0x18000a3c1  div     cs:dword_18003E760
0x18000a3c7  mov     [rsp+58h+arg_8], r12
0x18000a3cc  mov     edi, edx
0x18000a3ce  shl     rdi, 6
0x18000a3d2  add     rdi, [r14+2A8h]
0x18000a3d9  mov     r9d, 190h
0x18000a3df  mov     r10d, 80h
0x18000a3e5  nop     word ptr [rax+rax+00000000h]
0x18000a3f0  movzx   eax, byte ptr [r14+40h]
0x18000a3f5  movzx   r8d, byte ptr [r14+41h]
0x18000a3fa  cmp     bpl, al
0x18000a3fd  ja      loc_18000A5F6
0x18000a403  bts     r15d, 1Ch
0x18000a408  movzx   edx, bpl
0x18000a40c  cmp     bpl, r8b
0x18000a40f  mov     ecx, r8d
0x18000a412  cmova   ecx, eax
0x18000a415  movzx   ebp, cl
0x18000a418  mov     r12d, ebp
0x18000a41b  movzx   ecx, r10w
0x18000a41f  imul    r12d, ecx
0x18000a423  add     r12w, r9w
0x18000a427  cmp     r8b, dl
0x18000a42a  sbb     rax, rax
0x18000a42d  and     eax, 10h
0x18000a430  mov     r13, [rax+rdi]
0x18000a434  lock inc dword ptr [r13+14h]
0x18000a439  mov     rcx, r13; ListHead
0x18000a43c  call    cs:__imp_ExpInterlockedPopEntrySList
0x18000a443  nop     dword ptr [rax+rax+00h]
0x18000a448  mov     rbx, rax
0x18000a44b  test    rax, rax
0x18000a44e  jnz     loc_18000A5CA
0x18000a454  lock inc dword ptr [r13+18h]
0x18000a459  mov     r13, [rsp+58h+arg_10]
0x18000a45e  movzx   edx, r12w
0x18000a462  mov     ecx, 40h ; '@'
0x18000a467  mov     r8d, 63694D46h
0x18000a46d  call    cs:__imp_ExAllocatePool2
0x18000a474  nop     dword ptr [rax+rax+00h]
0x18000a479  mov     rbx, rax
0x18000a47c  test    rax, rax
0x18000a47f  jz      loc_18000A6AA
0x18000a485  xor     edx, edx; Val
0x18000a487  mov     r8d, 190h; Size
0x18000a48d  mov     rcx, rbx; void *
0x18000a490  call    memset
0x18000a495  or      [rbx+4], r15d
0x18000a499  lea     rax, [rbx+190h]
0x18000a4a0  mov     r13, [rsp+58h+arg_10]
0x18000a4a5  mov     [rbx+10h], rax
0x18000a4a9  sub     rdi, [r14+2A8h]
0x18000a4b0  xor     edx, edx; Val
0x18000a4b2  mov     rax, [rsp+58h+arg_0]
0x18000a4b7  mov     rcx, [rbx+10h]; void *
0x18000a4bb  movzx   r8d, bpl
0x18000a4bf  shl     r8, 7; Size
0x18000a4c3  sar     rdi, 6
0x18000a4c7  mov     word ptr [rbx], 0F104h
0x18000a4cc  mov     [rbx+2], r12w
0x18000a4d1  mov     [rbx+68h], rax
0x18000a4d5  mov     [rbx+0Eh], bpl
0x18000a4d9  call    memset
0x18000a4de  lea     rax, [rbx+140h]
0x18000a4e5  xor     r8d, r8d; State
0x18000a4e8  lea     rcx, [rbx+18h]; Event
0x18000a4ec  mov     [rbx+0F8h], rax
0x18000a4f3  mov     edx, 1; Type
0x18000a4f8  call    cs:__imp_KeInitializeEvent
0x18000a4ff  nop     dword ptr [rax+rax+00h]
0x18000a504  cmp     esi, 1
0x18000a507  jnz     loc_18000A593
0x18000a50d  or      [rbx+0E8h], esi
0x18000a513  mov     rdx, r13
0x18000a516  mov     rcx, rbx
0x18000a519  mov     [rbx+30h], r13
0x18000a51d  call    FltpMoveIrpToCallbackData
0x18000a522  mov     eax, [rbx+0E8h]
0x18000a528  test    al, 1
0x18000a52a  jz      short loc_18000A55B
0x18000a52c  mov     rcx, [rbx+30h]; Irp
0x18000a530  test    rcx, rcx
0x18000a533  jz      short loc_18000A55B
0x18000a535  call    cs:__imp_IoGetRequestorProcess
0x18000a53c  nop     dword ptr [rax+rax+00h]
0x18000a541  test    rax, rax
0x18000a544  jz      loc_18000A7FD
0x18000a54a  mov     rcx, rax; Process
0x18000a54d  call    cs:__imp_PsGetProcessId
0x18000a554  nop     dword ptr [rax+rax+00h]
0x18000a559  jmp     short loc_18000A567
0x18000a55b  call    cs:__imp_PsGetCurrentProcessId
0x18000a562  nop     dword ptr [rax+rax+00h]
0x18000a567  mov     [rbx+0E4h], eax
0x18000a56d  mov     rax, [rsp+58h+arg_18]
0x18000a572  or      dword ptr [rbx+4], 4
0x18000a576  mov     [rbx+8], edi
0x18000a579  mov     [rax], rbx
0x18000a57c  xor     eax, eax
0x18000a57e  mov     r12, [rsp+58h+arg_8]
0x18000a583  add     rsp, 20h
0x18000a587  pop     r15
0x18000a589  pop     r14
0x18000a58b  pop     r13
0x18000a58d  pop     rdi
0x18000a58e  pop     rsi
0x18000a58f  pop     rbp
0x18000a590  pop     rbx
0x18000a591  retn
0x18000a593  test    esi, esi
0x18000a595  jz      short loc_18000A60B
0x18000a597  sub     esi, 2
0x18000a59a  jnz     short loc_18000A61A
0x18000a59c  or      dword ptr [rbx+0E8h], 2
0x18000a5a3  mov     rax, gs:188h
0x18000a5ac  mov     [rbx+0F0h], rax
0x18000a5b3  call    cs:__imp_ExGetPreviousMode
0x18000a5ba  nop     dword ptr [rax+rax+00h]
0x18000a5bf  mov     [rbx+138h], al
0x18000a5c5  jmp     loc_18000A522
0x18000a5ca  mov     eax, [r14+3CCh]
0x18000a5d1  test    al, 1
0x18000a5d3  jz      loc_18000A485
0x18000a5d9  mov     rcx, [rbx+108h]
0x18000a5e0  movzx   eax, r12w
0x18000a5e4  cmp     rcx, rax
0x18000a5e7  jb      loc_18000A7A2
0x18000a5ed  movzx   r12d, cx
0x18000a5f1  jmp     loc_18000A485
0x18000a5f6  movzx   r12d, bpl
0x18000a5fa  movzx   ecx, r10w
0x18000a5fe  imul    r12d, ecx
0x18000a602  add     r12w, r9w
0x18000a606  jmp     loc_18000A45E
0x18000a60b  or      dword ptr [rbx+0E8h], 10001h
0x18000a615  jmp     loc_18000A522
0x18000a61a  cmp     esi, 1
0x18000a61d  jnz     loc_18000A522
0x18000a623  or      dword ptr [rbx+0E8h], 4
0x18000a62a  mov     rax, gs:188h
0x18000a633  mov     [rbx+0F0h], rax
0x18000a63a  call    cs:__imp_ExGetPreviousMode
0x18000a641  nop     dword ptr [rax+rax+00h]
0x18000a646  mov     [rbx+138h], al
0x18000a64c  mov     [rbx+30h], r13
0x18000a650  movzx   eax, byte ptr [r13+4]
0x18000a655  mov     rcx, [rbx+0F8h]
0x18000a65c  mov     [rcx+4], al
0x18000a65f  mov     rcx, [rbx+0F8h]
0x18000a666  movzx   eax, byte ptr [rcx+4]
0x18000a66a  mov     [rbx+0Ch], al
0x18000a66d  mov     byte ptr [rcx+5], 0
0x18000a671  mov     rax, [r13+10h]
0x18000a675  mov     [rbx+70h], rax
0x18000a679  mov     rax, [r13+8]
0x18000a67d  mov     [rbx+68h], rax
0x18000a681  movups  xmm0, xmmword ptr [r13+18h]
0x18000a686  mov     rax, [rbx+0F8h]
0x18000a68d  movups  xmmword ptr [rax+18h], xmm0
0x18000a691  movups  xmm1, xmmword ptr [r13+28h]
0x18000a696  movups  xmmword ptr [rax+28h], xmm1
0x18000a69a  movsd   xmm0, qword ptr [r13+38h]
0x18000a6a0  movsd   qword ptr [rax+38h], xmm0
0x18000a6a5  jmp     loc_18000A522
0x18000a6aa  mov     rdx, r13
0x18000a6ad  mov     ecx, esi
0x18000a6af  call    FltpDetermineStaticOperationType
0x18000a6b4  mov     [rsp+58h+arg_20], eax
0x18000a6bb  cmp     eax, 0FFFFFFFFh
0x18000a6be  jnz     loc_18000A7BD
0x18000a6c4  cmp     esi, 1
0x18000a6c7  jz      loc_18000A7C9
0x18000a6cd  cmp     esi, 3
0x18000a6d0  jnz     short loc_18000A6ED
0x18000a6d2  movzx   eax, byte ptr [r13+4]
0x18000a6d7  lea     rcx, FltpOperationFlags
0x18000a6de  add     al, 16h
0x18000a6e0  movzx   eax, al
0x18000a6e3  test    byte ptr [rax+rcx], 8
0x18000a6e7  jnz     loc_18000A7D4
0x18000a6ed  mov     rax, [rsp+58h+arg_18]
0x18000a6f2  mov     qword ptr [rax], 0
0x18000a6f9  mov     eax, 0C000009Ah
0x18000a6fe  jmp     loc_18000A57E
0x18000a703  cmp     bpl, 0Ah
0x18000a707  jnb     loc_18000A3B7
0x18000a70d  movzx   eax, bpl
0x18000a711  lock inc dword ptr [r14+rax*4+2C8h]
0x18000a71a  cmp     bpl, 2
0x18000a71e  jb      loc_18000A3B7
0x18000a724  lock inc dword ptr [r14+3D0h]
0x18000a72c  mov     eax, [r14+3D0h]
0x18000a733  cmp     eax, 7D0h
0x18000a738  jbe     loc_18000A3B7
0x18000a73e  lea     rcx, [r14+390h]; FastMutex
0x18000a745  call    cs:__imp_ExAcquireFastMutex
0x18000a74c  nop     dword ptr [rax+rax+00h]
0x18000a751  mov     eax, [r14+3C8h]
0x18000a758  and     al, 7
0x18000a75a  cmp     al, dil
0x18000a75d  jnz     loc_180025866
0x18000a763  lea     rcx, [r14+370h]; WorkItem
0x18000a76a  mov     edx, edi; QueueType
0x18000a76c  call    cs:__imp_ExQueueWorkItem
0x18000a773  nop     dword ptr [rax+rax+00h]
0x18000a778  or      dword ptr [r14+3C8h], 2
0x18000a780  jmp     loc_180025866
0x18000a785  mov     rbx, rax
0x18000a788  test    rax, rax
0x18000a78b  jz      short loc_18000A7E6
0x18000a78d  movzx   eax, byte ptr [rax+0Eh]
0x18000a791  cmp     bpl, al
0x18000a794  jbe     loc_18000A4A9
0x18000a79a  movzx   ebp, al
0x18000a79d  jmp     loc_18000A4A9
0x18000a7a2  xor     edx, edx; Tag
0x18000a7a4  mov     rcx, rbx; P
0x18000a7a7  call    cs:__imp_ExFreePoolWithTag
0x18000a7ae  nop     dword ptr [rax+rax+00h]
0x18000a7b3  mov     r13, [rsp+58h+arg_10]
0x18000a7b8  jmp     loc_18000A45E
0x18000a7bd  mov     edx, eax
0x18000a7bf  mov     rcx, r14
0x18000a7c2  call    FltpAllocateStaticIrpCtrl
0x18000a7c7  jmp     short loc_18000A785
0x18000a7c9  test    byte ptr [r13+47h], 20h
0x18000a7ce  jz      loc_18000A6ED
0x18000a7d4  mov     rdx, [rsp+58h+arg_28]
0x18000a7dc  mov     rcx, r14
0x18000a7df  call    FltpAllocateBackPocketIrpCtrl
0x18000a7e4  jmp     short loc_18000A785
0x18000a7e6  mov     eax, [rsp+58h+arg_20]
0x18000a7ed  inc     eax
0x18000a7ef  cmp     eax, 2
0x18000a7f2  jbe     loc_18000A6ED
0x18000a7f8  jmp     loc_18000A3D9
0x18000a7fd  jmp     loc_18000A567
0x180025866  lea     rcx, [r14+390h]; FastMutex
0x18002586d  call    cs:__imp_ExReleaseFastMutex
0x180025874  nop     dword ptr [rax+rax+00h]
0x180025879  nop
0x18002587a  jmp     loc_18000A3B7
```
