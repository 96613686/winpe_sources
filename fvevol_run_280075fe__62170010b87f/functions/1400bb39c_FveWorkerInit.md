# FveWorkerInit

- ea: `0x1400bb39c`
- end: `0x1400bba6c`
- name: `FveWorkerInit`
- size: `1744`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14009ec2c`
- `0x1400a9158`
- `0x1400c9248`
- `0x1400e9244`

## callees

- `0x140021d00`
- `0x140071c10`
- `0x1400734d0`
- `0x1400bb028`
- `0x1400bb39c`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400bb7d3`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400bb7d3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bb46b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bb72c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bb46b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bb72c`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400bb569`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400bb569`
- `ntoskrnl!KeReleaseMutex` at `0x1400bba23`
- `ntoskrnl!KeReleaseMutex` at `0x1400bba23`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bb59e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bb59e`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400bb8ff`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400bb8ff`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bb5f6`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bb5f6`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400bb620`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400bb620`
- `ntoskrnl!KeQueryNodeActiveProcessorCount` at `0x1400bb67d`
- `ntoskrnl!KeQueryNodeActiveProcessorCount` at `0x1400bb67d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400bb82f`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400bb82f`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1400bb84c`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1400bb84c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bb41b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bba49`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bb41b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bba49`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb49d`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb522`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb549`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb642`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb6dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb7f4`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb49d`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb4fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb522`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb549`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb642`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb6dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb7f4`

## pseudocode

```c
__int64 __fastcall FveWorkerInit(__int64 a1)
{
  unsigned int v1; // r13d
  __int64 v2; // rdi
  __int64 v3; // r14
  int v4; // ebx
  __int64 v5; // r8
  unsigned int *v6; // r15
  __int64 Pool2; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  ULONG v11; // eax
  __int64 i; // rbx
  _QWORD *v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rax
  unsigned int v16; // esi
  unsigned int v17; // r12d
  int NodeActiveProcessorCount; // eax
  __int64 v19; // rbx
  unsigned int v20; // eax
  __int64 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r15
  __int64 v26; // r14
  __int64 v27; // rbx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  __int64 ActiveProcessorCount; // r13
  __int64 v32; // rax
  ULONG j; // esi
  NTSTATUS v34; // eax
  __int64 v35; // r8
  ULONG NodeNumber; // ecx
  unsigned __int64 v37; // r9
  __int64 v38; // r10
  __int64 v39; // rax
  unsigned __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r12
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 **v48; // rcx
  __int64 *v49; // rax
  __int64 v50; // rcx
  int v51; // eax
  unsigned int v52; // r12d
  unsigned int v54; // [rsp+40h] [rbp-79h]
  unsigned int v55; // [rsp+48h] [rbp-71h]
  __int64 v56; // [rsp+48h] [rbp-71h]
  unsigned int v57; // [rsp+50h] [rbp-69h]
  __int64 v58; // [rsp+58h] [rbp-61h]
  PVOID Object; // [rsp+60h] [rbp-59h] BYREF
  __int64 v60; // [rsp+68h] [rbp-51h]
  __int64 v61; // [rsp+70h] [rbp-49h]
  __int64 v62; // [rsp+78h] [rbp-41h]
  _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX Information; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v65; // [rsp+120h] [rbp+67h]
  char v66; // [rsp+128h] [rbp+6Fh]
  ULONG Length; // [rsp+130h] [rbp+77h] BYREF
  _PROCESSOR_NUMBER ProcNumber; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *(_DWORD *)(a1 + 1324);
  v2 = *(_QWORD *)(a1 + 8);
  v3 = a1;
  Length = 0;
  v57 = v1;
  Object = 0;
  memset(&Information, 0, sizeof(Information));
  ProcNumber = 0;
  if ( v1 >= *(_DWORD *)(v2 + 264) )
    return (unsigned int)-1073741811;
  v4 = KeWaitForSingleObject((PVOID)(v2 + 296), Executive, 0, 0, 0);
  if ( v4 < 0 )
    return (unsigned int)v4;
  if ( *(_QWORD *)(v2 + 224) )
  {
    v66 = 0;
    v6 = (unsigned int *)(v2 + 232);
    goto LABEL_42;
  }
  FvePowerRegisterFveCleanup(*(PVOID *)v2);
  v6 = (unsigned int *)(v2 + 232);
  *(_DWORD *)(v2 + 236) = 0;
  *(_DWORD *)(v2 + 232) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)(v2 + 288));
  *(_QWORD *)(v2 + 256) = v2 + 248;
  *(_QWORD *)(v2 + 248) = v2 + 248;
  Pool2 = ExAllocatePool2(64, 4LL * *(unsigned int *)(v2 + 264), 2001032774);
  *(_QWORD *)(v2 + 224) = Pool2;
  if ( !Pool2 )
    goto LABEL_6;
  *(_QWORD *)(v2 + 240) = ExAllocatePool2(64, *(unsigned int *)(v2 + 264), 2001032774);
  if ( !*(_QWORD *)(v2 + 240) )
    goto LABEL_6;
  v8 = ExAllocatePool2(64, 16LL * *(unsigned int *)(v2 + 264), 2001032774);
  *(_QWORD *)(v2 + 272) = v8;
  if ( !v8 )
    goto LABEL_6;
  v9 = ExAllocatePool2(64, 32LL * *(unsigned int *)(v2 + 264), 2001032774);
  *(_QWORD *)(v2 + 280) = v9;
  if ( !v9 )
    goto LABEL_6;
  v10 = ExAllocatePool2(64, 128, 2001032774);
  *(_QWORD *)(v2 + 352) = v10;
  if ( !v10 )
    goto LABEL_6;
  v66 = 1;
  v11 = IoSizeofWorkItem();
  ExInitializeNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v2 + 352), 0, 0, 0x200u, v11 + 184, 0x77455646u, 0);
  for ( i = 0; (unsigned int)i < *(_DWORD *)(v2 + 264); i = (unsigned int)(i + 1) )
  {
    *(_DWORD *)(*(_QWORD *)(v2 + 224) + 4 * i) = 0;
    *(_BYTE *)(*(_QWORD *)(v2 + 240) + i) = 0;
    v13 = (_QWORD *)(*(_QWORD *)(v2 + 272) + 16LL * (unsigned int)i);
    v13[1] = v13;
    *v13 = v13;
    KeInitializeSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v2 + 280) + 32LL * (unsigned int)i), 0, 0x7FFFFFFF);
  }
  if ( !*(_DWORD *)(v2 + 4LL * *(unsigned int *)(v2 + 884) + 1128) )
    goto LABEL_42;
  v14 = KeQueryHighestNodeNumber() + 1;
  v55 = v14;
  v15 = ExAllocatePool2(64, (unsigned __int64)v14 << 6, 2001032774);
  *(_QWORD *)(v2 + 656) = v15;
  if ( !v15 )
    goto LABEL_6;
  v16 = 0;
  v17 = *(_DWORD *)(v2 + 4LL * *(unsigned int *)(v2 + 884) + 1140);
  v54 = v17;
  while ( v16 < v14 )
  {
    NodeActiveProcessorCount = KeQueryNodeActiveProcessorCount((unsigned __int16)v16);
    v19 = v16;
    if ( !NodeActiveProcessorCount )
      NodeActiveProcessorCount = 1;
    v20 = (v17 + NodeActiveProcessorCount - 1) / v17;
    v21 = 0;
    *(_DWORD *)(*(_QWORD *)(v2 + 656) + ((unsigned __int64)v16 << 6)) = v20;
    while ( (unsigned int)v21 < 7 )
    {
      v22 = ExAllocatePool2(
              64,
              80LL * *(unsigned int *)(*(_QWORD *)(v2 + 656) + ((unsigned __int64)v16 << 6)),
              2001032774);
      v23 = v21 + 8 * v19;
      *(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v23 + 8) = v22;
      v24 = *(_QWORD *)(v2 + 656);
      if ( !*(_QWORD *)(v24 + 8 * v23 + 8) )
        goto LABEL_6;
      if ( *(_DWORD *)(v24 + ((unsigned __int64)v16 << 6)) )
      {
        v25 = 0;
        v26 = v21 + 8 * v19;
        do
        {
          v27 = 80 * v25;
          KeInitializeSpinLock((PKSPIN_LOCK)(80 * v25 + *(_QWORD *)(v24 + 8 * v26 + 8)));
          v25 = (unsigned int)(v25 + 1);
          v28 = (_QWORD *)(v27 + *(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v26 + 8) + 8LL);
          v28[1] = v28;
          *v28 = v28;
          v29 = (_QWORD *)(v27 + *(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v26 + 8) + 24LL);
          v29[1] = v29;
          *v29 = v29;
          v30 = (_QWORD *)(v27 + *(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v26 + 8) + 40LL);
          v30[1] = v30;
          *v30 = v30;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v26 + 8) + v27 + 56) = v21;
          v24 = *(_QWORD *)(v2 + 656);
        }
        while ( (unsigned int)v25 < *(_DWORD *)(v24 + ((unsigned __int64)v16 << 6)) );
        v3 = a1;
        v6 = (unsigned int *)(v2 + 232);
        v19 = v16;
      }
      v21 = (unsigned int)(v21 + 1);
    }
    v14 = v55;
    ++v16;
    v17 = v54;
  }
  ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
  v32 = ExAllocatePool2(64, 232 * ActiveProcessorCount, 2001032774);
  *(_QWORD *)(v2 + 664) = v32;
  if ( !v32 )
  {
LABEL_6:
    v4 = -1073741670;
LABEL_52:
    FveWorkerFinalCleanup(v2);
    goto LABEL_53;
  }
  *(_DWORD *)(v2 + 648) = ActiveProcessorCount;
  for ( j = 0; j < (unsigned int)ActiveProcessorCount; ++j )
  {
    Length = 80;
    KeGetProcessorNumberFromIndex(j, &ProcNumber);
    v34 = KeQueryLogicalProcessorRelationship(&ProcNumber, RelationNumaNode, &Information, &Length);
    v35 = *(_QWORD *)(v2 + 656);
    NodeNumber = 0;
    if ( v34 >= 0 )
      NodeNumber = Information.NumaNode.NodeNumber;
    v37 = (unsigned __int64)NodeNumber << 6;
    v38 = NodeNumber;
    v61 = NodeNumber;
    v39 = *(_DWORD *)(v35 + v37 + 4) / v17;
    ++*(_DWORD *)(v35 + v37 + 4);
    v40 = v37 + *(_QWORD *)(v2 + 656);
    v5 = 232LL * j;
    v41 = *(_QWORD *)(v2 + 664);
    v42 = 0;
    v65 = v39;
    v62 = v5;
    *(_QWORD *)(v5 + v41) = v40;
    while ( (unsigned int)v42 < 7 )
    {
      v43 = 5 * v39;
      v44 = *(_QWORD *)(v2 + 656);
      v60 = 16 * v43;
      v56 = v42 + 8 * v38;
      v58 = 32LL * (unsigned int)v42 + v5;
      *(_QWORD *)(v58 + *(_QWORD *)(v2 + 664) + 24) = *(_QWORD *)(v44 + 8 * v56 + 8) + 16 * v43;
      v45 = *(_QWORD *)(v2 + 664);
      *(_QWORD *)(v58 + v45 + 32) = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(v2 + 8));
      v46 = *(_QWORD *)(v2 + 664);
      if ( !*(_QWORD *)(v58 + v46 + 32) )
        goto LABEL_6;
      v47 = *(_QWORD *)(*(_QWORD *)(v2 + 656) + 8 * v56 + 8) + v60 + 24;
      v48 = *(__int64 ***)(v47 + 8);
      if ( *v48 != (__int64 *)v47 )
        __fastfail(3u);
      v38 = v61;
      v5 = v62;
      v49 = (__int64 *)(v46 + v58 + 8);
      v42 = (unsigned int)(v42 + 1);
      *v49 = v47;
      v49[1] = (__int64)v48;
      *v48 = v49;
      *(_QWORD *)(v47 + 8) = v49;
      v39 = v65;
    }
    v17 = v54;
  }
  v1 = v57;
LABEL_42:
  if ( (*(_BYTE *)(v3 + 4400) & 0x10) != 0 )
  {
LABEL_43:
    v4 = 0;
    goto LABEL_50;
  }
  v50 = *(_QWORD *)(v2 + 224);
  v51 = *(_DWORD *)(v50 + 4LL * v1);
  if ( v51 )
  {
    *(_DWORD *)(v50 + 4LL * v1) = v51 + 1;
    *(_BYTE *)(v3 + 4400) |= 0x10u;
    goto LABEL_43;
  }
  *(_BYTE *)(*(_QWORD *)(v2 + 240) + v1) = 0;
  v52 = *v6;
  v4 = FveAddWorkerThread(v2, v1, v5, &Object);
  if ( v4 >= 0 )
  {
    if ( *v6 > v52 )
    {
      ++*(_DWORD *)(*(_QWORD *)(v2 + 224) + 4LL * v1);
      *(_BYTE *)(v3 + 4400) |= 0x10u;
    }
    else
    {
      v4 = -1073741823;
    }
  }
LABEL_50:
  if ( v66 && v4 < 0 )
    goto LABEL_52;
LABEL_53:
  KeReleaseMutex((PRKMUTEX)(v2 + 296), 0);
  if ( Object )
    KeWaitForSingleObject(Object, Executive, 0, 0, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400bb39c  mov     [rsp-8+arg_0], rcx
0x1400bb3a1  push    rbp
0x1400bb3a2  push    rbx
0x1400bb3a3  push    rsi
0x1400bb3a4  push    rdi
0x1400bb3a5  push    r12
0x1400bb3a7  push    r13
0x1400bb3a9  push    r14
0x1400bb3ab  push    r15
0x1400bb3ad  lea     rbp, [rsp-1Fh]
0x1400bb3b2  sub     rsp, 0D8h
0x1400bb3b9  mov     r13d, [rcx+52Ch]
0x1400bb3c0  xor     edx, edx; Val
0x1400bb3c2  mov     rdi, [rcx+8]
0x1400bb3c6  mov     r14, rcx
0x1400bb3c9  lea     rcx, [rbp+57h+Information]; void *
0x1400bb3cd  mov     [rbp+57h+Length], 0
0x1400bb3d4  mov     [rbp+57h+var_C0], r13d
0x1400bb3d8  lea     r8d, [rdx+50h]; Size
0x1400bb3dc  mov     [rbp+57h+Object], 0
0x1400bb3e4  call    memset
0x1400bb3e9  mov     dword ptr [rbp+57h+ProcNumber.Group], 0
0x1400bb3f0  cmp     r13d, [rdi+108h]
0x1400bb3f7  jb      short loc_1400BB403
0x1400bb3f9  mov     ebx, 0C000000Dh
0x1400bb3fe  jmp     loc_1400BBA55
0x1400bb403  lea     rcx, [rdi+128h]; Object
0x1400bb40a  mov     [rsp+110h+Timeout], 0; Timeout
0x1400bb413  xor     r9d, r9d; Alertable
0x1400bb416  xor     r8d, r8d; WaitMode
0x1400bb419  xor     edx, edx; WaitReason
0x1400bb41b  call    cs:__imp_KeWaitForSingleObject
0x1400bb422  nop     dword ptr [rax+rax+00h]
0x1400bb427  mov     ebx, eax
0x1400bb429  test    eax, eax
0x1400bb42b  js      loc_1400BBA55
0x1400bb431  cmp     qword ptr [rdi+0E0h], 0
0x1400bb439  mov     esi, 1
0x1400bb43e  jnz     loc_1400BB982
0x1400bb444  mov     rcx, [rdi]; Object
0x1400bb447  call    FvePowerRegisterFveCleanup
0x1400bb44c  lea     r15, [rdi+0E8h]
0x1400bb453  mov     dword ptr [rdi+0ECh], 0
0x1400bb45d  lea     rcx, [rdi+120h]; SpinLock
0x1400bb464  mov     dword ptr [r15], 0
0x1400bb46b  call    cs:__imp_KeInitializeSpinLock
0x1400bb472  nop     dword ptr [rax+rax+00h]
0x1400bb477  lea     rax, [rdi+0F8h]
0x1400bb47e  mov     r12d, 77455646h
0x1400bb484  mov     [rax+8], rax
0x1400bb488  lea     ebx, [rsi+3Fh]
0x1400bb48b  mov     [rax], rax
0x1400bb48e  mov     r8d, r12d
0x1400bb491  mov     edx, [rdi+108h]
0x1400bb497  mov     ecx, ebx
0x1400bb499  shl     rdx, 2
0x1400bb49d  call    cs:__imp_ExAllocatePool2
0x1400bb4a4  nop     dword ptr [rax+rax+00h]
0x1400bb4a9  mov     [rdi+0E0h], rax
0x1400bb4b0  test    rax, rax
0x1400bb4b3  jnz     short loc_1400BB4BF
0x1400bb4b5  mov     ebx, 0C000009Ah
0x1400bb4ba  jmp     loc_1400BBA12
0x1400bb4bf  mov     edx, [rdi+108h]
0x1400bb4c5  mov     r8d, r12d
0x1400bb4c8  mov     rcx, rbx
0x1400bb4cb  call    cs:__imp_ExAllocatePool2
0x1400bb4d2  nop     dword ptr [rax+rax+00h]
0x1400bb4d7  mov     [rdi+0F0h], rax
0x1400bb4de  mov     rax, [rdi+0F0h]
0x1400bb4e5  test    rax, rax
0x1400bb4e8  jz      short loc_1400BB4B5
0x1400bb4ea  mov     edx, [rdi+108h]
0x1400bb4f0  mov     r8d, r12d
0x1400bb4f3  shl     rdx, 4
0x1400bb4f7  mov     rcx, rbx
0x1400bb4fa  call    cs:__imp_ExAllocatePool2
0x1400bb501  nop     dword ptr [rax+rax+00h]
0x1400bb506  mov     [rdi+110h], rax
0x1400bb50d  test    rax, rax
0x1400bb510  jz      short loc_1400BB4B5
0x1400bb512  mov     edx, [rdi+108h]
0x1400bb518  mov     r8d, r12d
0x1400bb51b  shl     rdx, 5
0x1400bb51f  mov     rcx, rbx
0x1400bb522  call    cs:__imp_ExAllocatePool2
0x1400bb529  nop     dword ptr [rax+rax+00h]
0x1400bb52e  mov     [rdi+118h], rax
0x1400bb535  test    rax, rax
0x1400bb538  jz      loc_1400BB4B5
0x1400bb53e  mov     r8d, r12d
0x1400bb541  mov     edx, 80h
0x1400bb546  mov     rcx, rbx
0x1400bb549  call    cs:__imp_ExAllocatePool2
0x1400bb550  nop     dword ptr [rax+rax+00h]
0x1400bb555  mov     [rdi+160h], rax
0x1400bb55c  test    rax, rax
0x1400bb55f  jz      loc_1400BB4B5
0x1400bb565  mov     [rbp+57h+arg_8], sil
0x1400bb569  call    cs:__imp_IoSizeofWorkItem
0x1400bb570  nop     dword ptr [rax+rax+00h]
0x1400bb575  mov     r9d, 200h; Flags
0x1400bb57b  xor     r8d, r8d; Free
0x1400bb57e  xor     edx, edx; Allocate
0x1400bb580  lea     ecx, [rax+0B8h]
0x1400bb586  xor     eax, eax
0x1400bb588  mov     [rsp+110h+Depth], ax; Depth
0x1400bb58d  mov     [rsp+110h+Tag], r12d; Tag
0x1400bb592  mov     [rsp+110h+Timeout], rcx; Size
0x1400bb597  mov     rcx, [rdi+160h]; Lookaside
0x1400bb59e  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400bb5a5  nop     dword ptr [rax+rax+00h]
0x1400bb5aa  xor     ebx, ebx
0x1400bb5ac  cmp     [rdi+108h], ebx
0x1400bb5b2  jbe     short loc_1400BB60C
0x1400bb5b4  mov     rax, [rdi+0E0h]
0x1400bb5bb  mov     r8d, 7FFFFFFFh; Limit
0x1400bb5c1  mov     edx, ebx
0x1400bb5c3  shl     rdx, 4
0x1400bb5c7  mov     ecx, ebx
0x1400bb5c9  mov     dword ptr [rax+rbx*4], 0
0x1400bb5d0  mov     rax, [rdi+0F0h]
0x1400bb5d7  shl     rcx, 5
0x1400bb5db  mov     byte ptr [rax+rbx], 0
0x1400bb5df  add     rdx, [rdi+110h]
0x1400bb5e6  mov     [rdx+8], rdx
0x1400bb5ea  mov     [rdx], rdx
0x1400bb5ed  xor     edx, edx; Count
0x1400bb5ef  add     rcx, [rdi+118h]; Semaphore
0x1400bb5f6  call    cs:__imp_KeInitializeSemaphore
0x1400bb5fd  nop     dword ptr [rax+rax+00h]
0x1400bb602  add     ebx, esi
0x1400bb604  cmp     ebx, [rdi+108h]
0x1400bb60a  jb      short loc_1400BB5B4
0x1400bb60c  mov     eax, [rdi+374h]
0x1400bb612  cmp     dword ptr [rdi+rax*4+468h], 0
0x1400bb61a  jz      loc_1400BB993
0x1400bb620  call    cs:__imp_KeQueryHighestNodeNumber
0x1400bb627  nop     dword ptr [rax+rax+00h]
0x1400bb62c  movzx   ebx, ax
0x1400bb62f  mov     r8d, r12d
0x1400bb632  add     ebx, esi
0x1400bb634  mov     ecx, 40h ; '@'
0x1400bb639  mov     edx, ebx
0x1400bb63b  shl     rdx, 6
0x1400bb63f  mov     dword ptr [rbp+57h+var_C8], ebx
0x1400bb642  call    cs:__imp_ExAllocatePool2
0x1400bb649  nop     dword ptr [rax+rax+00h]
0x1400bb64e  mov     [rdi+290h], rax
0x1400bb655  test    rax, rax
0x1400bb658  jz      loc_1400BB4B5
0x1400bb65e  mov     eax, [rdi+374h]
0x1400bb664  xor     esi, esi
0x1400bb666  mov     r12d, [rdi+rax*4+474h]
0x1400bb66e  mov     [rbp+57h+var_D0], r12d
0x1400bb672  cmp     esi, ebx
0x1400bb674  jnb     loc_1400BB7CE
0x1400bb67a  movzx   ecx, si
0x1400bb67d  call    cs:__imp_KeQueryNodeActiveProcessorCount
0x1400bb684  nop     dword ptr [rax+rax+00h]
0x1400bb689  mov     ecx, 1
0x1400bb68e  mov     r13d, esi
0x1400bb691  test    eax, eax
0x1400bb693  mov     ebx, esi
0x1400bb695  cmovz   eax, ecx
0x1400bb698  mov     rcx, [rdi+290h]
0x1400bb69f  dec     eax
0x1400bb6a1  shl     r13, 6
0x1400bb6a5  add     eax, r12d
0x1400bb6a8  xor     edx, edx
0x1400bb6aa  div     r12d
0x1400bb6ad  xor     r12d, r12d
0x1400bb6b0  mov     [rcx+r13], eax
0x1400bb6b4  cmp     r12d, 7
0x1400bb6b8  jnb     loc_1400BB7C0
0x1400bb6be  mov     rax, [rdi+290h]
0x1400bb6c5  mov     r8d, 77455646h
0x1400bb6cb  mov     ecx, [rax+r13]
0x1400bb6cf  lea     rdx, [rcx+rcx*4]
0x1400bb6d3  mov     ecx, 40h ; '@'
0x1400bb6d8  shl     rdx, 4
0x1400bb6dc  call    cs:__imp_ExAllocatePool2
0x1400bb6e3  nop     dword ptr [rax+rax+00h]
0x1400bb6e8  mov     rcx, [rdi+290h]
0x1400bb6ef  lea     rdx, [r12+rbx*8]
0x1400bb6f3  mov     [rcx+rdx*8+8], rax
0x1400bb6f8  mov     rcx, [rdi+290h]
0x1400bb6ff  cmp     qword ptr [rcx+rdx*8+8], 0
0x1400bb705  jz      loc_1400BB4B5
0x1400bb70b  cmp     dword ptr [rcx+r13], 0
0x1400bb710  jbe     loc_1400BB7B8
0x1400bb716  xor     r15d, r15d
0x1400bb719  mov     r14, rdx
0x1400bb71c  mov     rcx, [rcx+r14*8+8]
0x1400bb721  lea     rbx, [r15+r15*4]
0x1400bb725  shl     rbx, 4
0x1400bb729  add     rcx, rbx; SpinLock
0x1400bb72c  call    cs:__imp_KeInitializeSpinLock
0x1400bb733  nop     dword ptr [rax+rax+00h]
0x1400bb738  mov     rax, [rdi+290h]
0x1400bb73f  inc     r15d
0x1400bb742  mov     rax, [rax+r14*8+8]
0x1400bb747  add     rax, 8
0x1400bb74b  add     rax, rbx
0x1400bb74e  mov     [rax+8], rax
0x1400bb752  mov     [rax], rax
0x1400bb755  mov     rax, [rdi+290h]
0x1400bb75c  mov     rax, [rax+r14*8+8]
0x1400bb761  add     rax, 18h
0x1400bb765  add     rax, rbx
0x1400bb768  mov     [rax+8], rax
0x1400bb76c  mov     [rax], rax
0x1400bb76f  mov     rax, [rdi+290h]
0x1400bb776  mov     rax, [rax+r14*8+8]
0x1400bb77b  add     rax, 28h ; '('
0x1400bb77f  add     rax, rbx
0x1400bb782  mov     [rax+8], rax
0x1400bb786  mov     [rax], rax
0x1400bb789  mov     rax, [rdi+290h]
0x1400bb790  mov     rcx, [rax+r14*8+8]
0x1400bb795  mov     [rcx+rbx+38h], r12d
0x1400bb79a  mov     rcx, [rdi+290h]
0x1400bb7a1  cmp     r15d, [rcx+r13]
0x1400bb7a5  jb      loc_1400BB71C
0x1400bb7ab  mov     r14, [rbp+57h+arg_0]
0x1400bb7af  lea     r15, [rdi+0E8h]
0x1400bb7b6  mov     ebx, esi
0x1400bb7b8  inc     r12d
0x1400bb7bb  jmp     loc_1400BB6B4
0x1400bb7c0  mov     ebx, dword ptr [rbp+57h+var_C8]
0x1400bb7c3  inc     esi
0x1400bb7c5  mov     r12d, [rbp+57h+var_D0]
0x1400bb7c9  jmp     loc_1400BB672
0x1400bb7ce  mov     ecx, 0FFFFh; GroupNumber
0x1400bb7d3  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400bb7da  nop     dword ptr [rax+rax+00h]
0x1400bb7df  mov     r13d, eax
0x1400bb7e2  mov     ecx, 40h ; '@'
0x1400bb7e7  mov     r8d, 77455646h
0x1400bb7ed  imul    rdx, r13, 0E8h
0x1400bb7f4  call    cs:__imp_ExAllocatePool2
0x1400bb7fb  nop     dword ptr [rax+rax+00h]
0x1400bb800  mov     [rdi+298h], rax
0x1400bb807  test    rax, rax
0x1400bb80a  jz      loc_1400BB4B5
0x1400bb810  mov     [rdi+288h], r13d
0x1400bb817  xor     esi, esi
0x1400bb819  cmp     esi, r13d
0x1400bb81c  jnb     loc_1400BB98F
0x1400bb822  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1400bb826  mov     [rbp+57h+Length], 50h ; 'P'
0x1400bb82d  mov     ecx, esi; ProcIndex
0x1400bb82f  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400bb836  nop     dword ptr [rax+rax+00h]
0x1400bb83b  lea     r9, [rbp+57h+Length]; Length
0x1400bb83f  mov     edx, 1; RelationshipType
0x1400bb844  lea     r8, [rbp+57h+Information]; Information
0x1400bb848  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x1400bb84c  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x1400bb853  nop     dword ptr [rax+rax+00h]
0x1400bb858  mov     r8, [rdi+290h]
0x1400bb85f  xor     ecx, ecx
0x1400bb861  test    eax, eax
0x1400bb863  cmovns  ecx, dword ptr [rbp+57h+Information.8]
0x1400bb867  xor     edx, edx
0x1400bb869  mov     r9d, ecx
0x1400bb86c  shl     r9, 6
0x1400bb870  mov     r10d, ecx
0x1400bb873  mov     [rbp+57h+var_A0], r10
0x1400bb877  mov     ecx, [r8+r9+4]
0x1400bb87c  mov     eax, ecx
0x1400bb87e  div     r12d
0x1400bb881  inc     ecx
0x1400bb883  mov     [r8+r9+4], ecx
0x1400bb888  mov     rdx, [rdi+290h]
0x1400bb88f  mov     ecx, esi
0x1400bb891  add     rdx, r9
0x1400bb894  imul    r8, rcx, 0E8h
0x1400bb89b  mov     rcx, [rdi+298h]
0x1400bb8a2  xor     r12d, r12d
0x1400bb8a5  mov     dword ptr [rbp+57h+arg_0], eax
0x1400bb8a8  mov     [rbp+57h+var_98], r8
0x1400bb8ac  mov     [r8+rcx], rdx
0x1400bb8b0  cmp     r12d, 7
0x1400bb8b4  jnb     loc_1400BB970
0x1400bb8ba  lea     rdx, [rax+rax*4]
0x1400bb8be  mov     ecx, r12d
0x1400bb8c1  mov     rax, [rdi+290h]
0x1400bb8c8  lea     r9, [r12+r10*8]
0x1400bb8cc  shl     rdx, 4
0x1400bb8d0  shl     rcx, 5
0x1400bb8d4  add     r8, rcx
0x1400bb8d7  mov     [rbp+57h+var_A8], rdx
0x1400bb8db  add     rdx, [rax+r9*8+8]
0x1400bb8e0  mov     rax, [rdi+298h]
0x1400bb8e7  mov     [rbp+57h+var_C8], r9
0x1400bb8eb  mov     [rbp+57h+var_B8], r8
0x1400bb8ef  mov     [r8+rax+18h], rdx
0x1400bb8f4  mov     rcx, [rdi+8]; DeviceObject
0x1400bb8f8  mov     rbx, [rdi+298h]
  ... truncated ...
```
