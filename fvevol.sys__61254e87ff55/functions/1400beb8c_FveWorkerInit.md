# FveWorkerInit

- ea: `0x1400beb8c`
- end: `0x1400bf25c`
- name: `FveWorkerInit`
- size: `1744`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14009fb70`
- `0x1400aa0b8`
- `0x1400ccd18`
- `0x1400e7934`

## callees

- `0x140023040`
- `0x140073bf0`
- `0x140075500`
- `0x1400be818`
- `0x1400beb8c`

## import_xrefs

- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400befc3`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400befc3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bec5b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bef1c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bec5b`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400bef1c`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400bed59`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400bed59`
- `ntoskrnl!KeReleaseMutex` at `0x1400bf213`
- `ntoskrnl!KeReleaseMutex` at `0x1400bf213`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bed8e`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400bed8e`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400bf0ef`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400bf0ef`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bede6`
- `ntoskrnl!KeInitializeSemaphore` at `0x1400bede6`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400bee10`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400bee10`
- `ntoskrnl!KeQueryNodeActiveProcessorCount` at `0x1400bee6d`
- `ntoskrnl!KeQueryNodeActiveProcessorCount` at `0x1400bee6d`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400bf01f`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x1400bf01f`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1400bf03c`
- `ntoskrnl!KeQueryLogicalProcessorRelationship` at `0x1400bf03c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bec0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bf239`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bec0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bf239`
- `ntoskrnl!ExAllocatePool2` at `0x1400bec8d`
- `ntoskrnl!ExAllocatePool2` at `0x1400becbb`
- `ntoskrnl!ExAllocatePool2` at `0x1400becea`
- `ntoskrnl!ExAllocatePool2` at `0x1400bed12`
- `ntoskrnl!ExAllocatePool2` at `0x1400bed39`
- `ntoskrnl!ExAllocatePool2` at `0x1400bee32`
- `ntoskrnl!ExAllocatePool2` at `0x1400beecc`
- `ntoskrnl!ExAllocatePool2` at `0x1400befe4`
- `ntoskrnl!ExAllocatePool2` at `0x1400bec8d`
- `ntoskrnl!ExAllocatePool2` at `0x1400becbb`
- `ntoskrnl!ExAllocatePool2` at `0x1400becea`
- `ntoskrnl!ExAllocatePool2` at `0x1400bed12`
- `ntoskrnl!ExAllocatePool2` at `0x1400bed39`
- `ntoskrnl!ExAllocatePool2` at `0x1400bee32`
- `ntoskrnl!ExAllocatePool2` at `0x1400beecc`
- `ntoskrnl!ExAllocatePool2` at `0x1400befe4`

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
  if ( (*(_BYTE *)(v3 + 4416) & 0x10) != 0 )
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
    *(_BYTE *)(v3 + 4416) |= 0x10u;
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
      *(_BYTE *)(v3 + 4416) |= 0x10u;
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
0x1400beb8c  mov     [rsp-8+arg_0], rcx
0x1400beb91  push    rbp
0x1400beb92  push    rbx
0x1400beb93  push    rsi
0x1400beb94  push    rdi
0x1400beb95  push    r12
0x1400beb97  push    r13
0x1400beb99  push    r14
0x1400beb9b  push    r15
0x1400beb9d  lea     rbp, [rsp-1Fh]
0x1400beba2  sub     rsp, 0D8h
0x1400beba9  mov     r13d, [rcx+52Ch]
0x1400bebb0  xor     edx, edx; Val
0x1400bebb2  mov     rdi, [rcx+8]
0x1400bebb6  mov     r14, rcx
0x1400bebb9  lea     rcx, [rbp+57h+Information]; void *
0x1400bebbd  mov     [rbp+57h+Length], 0
0x1400bebc4  mov     [rbp+57h+var_C0], r13d
0x1400bebc8  lea     r8d, [rdx+50h]; Size
0x1400bebcc  mov     [rbp+57h+Object], 0
0x1400bebd4  call    memset
0x1400bebd9  mov     dword ptr [rbp+57h+ProcNumber.Group], 0
0x1400bebe0  cmp     r13d, [rdi+108h]
0x1400bebe7  jb      short loc_1400BEBF3
0x1400bebe9  mov     ebx, 0C000000Dh
0x1400bebee  jmp     loc_1400BF245
0x1400bebf3  lea     rcx, [rdi+128h]; Object
0x1400bebfa  mov     [rsp+110h+Timeout], 0; Timeout
0x1400bec03  xor     r9d, r9d; Alertable
0x1400bec06  xor     r8d, r8d; WaitMode
0x1400bec09  xor     edx, edx; WaitReason
0x1400bec0b  call    cs:__imp_KeWaitForSingleObject
0x1400bec12  nop     dword ptr [rax+rax+00h]
0x1400bec17  mov     ebx, eax
0x1400bec19  test    eax, eax
0x1400bec1b  js      loc_1400BF245
0x1400bec21  cmp     qword ptr [rdi+0E0h], 0
0x1400bec29  mov     esi, 1
0x1400bec2e  jnz     loc_1400BF172
0x1400bec34  mov     rcx, [rdi]; Object
0x1400bec37  call    FvePowerRegisterFveCleanup
0x1400bec3c  lea     r15, [rdi+0E8h]
0x1400bec43  mov     dword ptr [rdi+0ECh], 0
0x1400bec4d  lea     rcx, [rdi+120h]; SpinLock
0x1400bec54  mov     dword ptr [r15], 0
0x1400bec5b  call    cs:__imp_KeInitializeSpinLock
0x1400bec62  nop     dword ptr [rax+rax+00h]
0x1400bec67  lea     rax, [rdi+0F8h]
0x1400bec6e  mov     r12d, 77455646h
0x1400bec74  mov     [rax+8], rax
0x1400bec78  lea     ebx, [rsi+3Fh]
0x1400bec7b  mov     [rax], rax
0x1400bec7e  mov     r8d, r12d
0x1400bec81  mov     edx, [rdi+108h]
0x1400bec87  mov     ecx, ebx
0x1400bec89  shl     rdx, 2
0x1400bec8d  call    cs:__imp_ExAllocatePool2
0x1400bec94  nop     dword ptr [rax+rax+00h]
0x1400bec99  mov     [rdi+0E0h], rax
0x1400beca0  test    rax, rax
0x1400beca3  jnz     short loc_1400BECAF
0x1400beca5  mov     ebx, 0C000009Ah
0x1400becaa  jmp     loc_1400BF202
0x1400becaf  mov     edx, [rdi+108h]
0x1400becb5  mov     r8d, r12d
0x1400becb8  mov     rcx, rbx
0x1400becbb  call    cs:__imp_ExAllocatePool2
0x1400becc2  nop     dword ptr [rax+rax+00h]
0x1400becc7  mov     [rdi+0F0h], rax
0x1400becce  mov     rax, [rdi+0F0h]
0x1400becd5  test    rax, rax
0x1400becd8  jz      short loc_1400BECA5
0x1400becda  mov     edx, [rdi+108h]
0x1400bece0  mov     r8d, r12d
0x1400bece3  shl     rdx, 4
0x1400bece7  mov     rcx, rbx
0x1400becea  call    cs:__imp_ExAllocatePool2
0x1400becf1  nop     dword ptr [rax+rax+00h]
0x1400becf6  mov     [rdi+110h], rax
0x1400becfd  test    rax, rax
0x1400bed00  jz      short loc_1400BECA5
0x1400bed02  mov     edx, [rdi+108h]
0x1400bed08  mov     r8d, r12d
0x1400bed0b  shl     rdx, 5
0x1400bed0f  mov     rcx, rbx
0x1400bed12  call    cs:__imp_ExAllocatePool2
0x1400bed19  nop     dword ptr [rax+rax+00h]
0x1400bed1e  mov     [rdi+118h], rax
0x1400bed25  test    rax, rax
0x1400bed28  jz      loc_1400BECA5
0x1400bed2e  mov     r8d, r12d
0x1400bed31  mov     edx, 80h
0x1400bed36  mov     rcx, rbx
0x1400bed39  call    cs:__imp_ExAllocatePool2
0x1400bed40  nop     dword ptr [rax+rax+00h]
0x1400bed45  mov     [rdi+160h], rax
0x1400bed4c  test    rax, rax
0x1400bed4f  jz      loc_1400BECA5
0x1400bed55  mov     [rbp+57h+arg_8], sil
0x1400bed59  call    cs:__imp_IoSizeofWorkItem
0x1400bed60  nop     dword ptr [rax+rax+00h]
0x1400bed65  mov     r9d, 200h; Flags
0x1400bed6b  xor     r8d, r8d; Free
0x1400bed6e  xor     edx, edx; Allocate
0x1400bed70  lea     ecx, [rax+0B8h]
0x1400bed76  xor     eax, eax
0x1400bed78  mov     [rsp+110h+Depth], ax; Depth
0x1400bed7d  mov     [rsp+110h+Tag], r12d; Tag
0x1400bed82  mov     [rsp+110h+Timeout], rcx; Size
0x1400bed87  mov     rcx, [rdi+160h]; Lookaside
0x1400bed8e  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400bed95  nop     dword ptr [rax+rax+00h]
0x1400bed9a  xor     ebx, ebx
0x1400bed9c  cmp     [rdi+108h], ebx
0x1400beda2  jbe     short loc_1400BEDFC
0x1400beda4  mov     rax, [rdi+0E0h]
0x1400bedab  mov     r8d, 7FFFFFFFh; Limit
0x1400bedb1  mov     edx, ebx
0x1400bedb3  shl     rdx, 4
0x1400bedb7  mov     ecx, ebx
0x1400bedb9  mov     dword ptr [rax+rbx*4], 0
0x1400bedc0  mov     rax, [rdi+0F0h]
0x1400bedc7  shl     rcx, 5
0x1400bedcb  mov     byte ptr [rax+rbx], 0
0x1400bedcf  add     rdx, [rdi+110h]
0x1400bedd6  mov     [rdx+8], rdx
0x1400bedda  mov     [rdx], rdx
0x1400beddd  xor     edx, edx; Count
0x1400beddf  add     rcx, [rdi+118h]; Semaphore
0x1400bede6  call    cs:__imp_KeInitializeSemaphore
0x1400beded  nop     dword ptr [rax+rax+00h]
0x1400bedf2  add     ebx, esi
0x1400bedf4  cmp     ebx, [rdi+108h]
0x1400bedfa  jb      short loc_1400BEDA4
0x1400bedfc  mov     eax, [rdi+374h]
0x1400bee02  cmp     dword ptr [rdi+rax*4+468h], 0
0x1400bee0a  jz      loc_1400BF183
0x1400bee10  call    cs:__imp_KeQueryHighestNodeNumber
0x1400bee17  nop     dword ptr [rax+rax+00h]
0x1400bee1c  movzx   ebx, ax
0x1400bee1f  mov     r8d, r12d
0x1400bee22  add     ebx, esi
0x1400bee24  mov     ecx, 40h ; '@'
0x1400bee29  mov     edx, ebx
0x1400bee2b  shl     rdx, 6
0x1400bee2f  mov     dword ptr [rbp+57h+var_C8], ebx
0x1400bee32  call    cs:__imp_ExAllocatePool2
0x1400bee39  nop     dword ptr [rax+rax+00h]
0x1400bee3e  mov     [rdi+290h], rax
0x1400bee45  test    rax, rax
0x1400bee48  jz      loc_1400BECA5
0x1400bee4e  mov     eax, [rdi+374h]
0x1400bee54  xor     esi, esi
0x1400bee56  mov     r12d, [rdi+rax*4+474h]
0x1400bee5e  mov     [rbp+57h+var_D0], r12d
0x1400bee62  cmp     esi, ebx
0x1400bee64  jnb     loc_1400BEFBE
0x1400bee6a  movzx   ecx, si
0x1400bee6d  call    cs:__imp_KeQueryNodeActiveProcessorCount
0x1400bee74  nop     dword ptr [rax+rax+00h]
0x1400bee79  mov     ecx, 1
0x1400bee7e  mov     r13d, esi
0x1400bee81  test    eax, eax
0x1400bee83  mov     ebx, esi
0x1400bee85  cmovz   eax, ecx
0x1400bee88  mov     rcx, [rdi+290h]
0x1400bee8f  dec     eax
0x1400bee91  shl     r13, 6
0x1400bee95  add     eax, r12d
0x1400bee98  xor     edx, edx
0x1400bee9a  div     r12d
0x1400bee9d  xor     r12d, r12d
0x1400beea0  mov     [rcx+r13], eax
0x1400beea4  cmp     r12d, 7
0x1400beea8  jnb     loc_1400BEFB0
0x1400beeae  mov     rax, [rdi+290h]
0x1400beeb5  mov     r8d, 77455646h
0x1400beebb  mov     ecx, [rax+r13]
0x1400beebf  lea     rdx, [rcx+rcx*4]
0x1400beec3  mov     ecx, 40h ; '@'
0x1400beec8  shl     rdx, 4
0x1400beecc  call    cs:__imp_ExAllocatePool2
0x1400beed3  nop     dword ptr [rax+rax+00h]
0x1400beed8  mov     rcx, [rdi+290h]
0x1400beedf  lea     rdx, [r12+rbx*8]
0x1400beee3  mov     [rcx+rdx*8+8], rax
0x1400beee8  mov     rcx, [rdi+290h]
0x1400beeef  cmp     qword ptr [rcx+rdx*8+8], 0
0x1400beef5  jz      loc_1400BECA5
0x1400beefb  cmp     dword ptr [rcx+r13], 0
0x1400bef00  jbe     loc_1400BEFA8
0x1400bef06  xor     r15d, r15d
0x1400bef09  mov     r14, rdx
0x1400bef0c  mov     rcx, [rcx+r14*8+8]
0x1400bef11  lea     rbx, [r15+r15*4]
0x1400bef15  shl     rbx, 4
0x1400bef19  add     rcx, rbx; SpinLock
0x1400bef1c  call    cs:__imp_KeInitializeSpinLock
0x1400bef23  nop     dword ptr [rax+rax+00h]
0x1400bef28  mov     rax, [rdi+290h]
0x1400bef2f  inc     r15d
0x1400bef32  mov     rax, [rax+r14*8+8]
0x1400bef37  add     rax, 8
0x1400bef3b  add     rax, rbx
0x1400bef3e  mov     [rax+8], rax
0x1400bef42  mov     [rax], rax
0x1400bef45  mov     rax, [rdi+290h]
0x1400bef4c  mov     rax, [rax+r14*8+8]
0x1400bef51  add     rax, 18h
0x1400bef55  add     rax, rbx
0x1400bef58  mov     [rax+8], rax
0x1400bef5c  mov     [rax], rax
0x1400bef5f  mov     rax, [rdi+290h]
0x1400bef66  mov     rax, [rax+r14*8+8]
0x1400bef6b  add     rax, 28h ; '('
0x1400bef6f  add     rax, rbx
0x1400bef72  mov     [rax+8], rax
0x1400bef76  mov     [rax], rax
0x1400bef79  mov     rax, [rdi+290h]
0x1400bef80  mov     rcx, [rax+r14*8+8]
0x1400bef85  mov     [rcx+rbx+38h], r12d
0x1400bef8a  mov     rcx, [rdi+290h]
0x1400bef91  cmp     r15d, [rcx+r13]
0x1400bef95  jb      loc_1400BEF0C
0x1400bef9b  mov     r14, [rbp+57h+arg_0]
0x1400bef9f  lea     r15, [rdi+0E8h]
0x1400befa6  mov     ebx, esi
0x1400befa8  inc     r12d
0x1400befab  jmp     loc_1400BEEA4
0x1400befb0  mov     ebx, dword ptr [rbp+57h+var_C8]
0x1400befb3  inc     esi
0x1400befb5  mov     r12d, [rbp+57h+var_D0]
0x1400befb9  jmp     loc_1400BEE62
0x1400befbe  mov     ecx, 0FFFFh; GroupNumber
0x1400befc3  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1400befca  nop     dword ptr [rax+rax+00h]
0x1400befcf  mov     r13d, eax
0x1400befd2  mov     ecx, 40h ; '@'
0x1400befd7  mov     r8d, 77455646h
0x1400befdd  imul    rdx, r13, 0E8h
0x1400befe4  call    cs:__imp_ExAllocatePool2
0x1400befeb  nop     dword ptr [rax+rax+00h]
0x1400beff0  mov     [rdi+298h], rax
0x1400beff7  test    rax, rax
0x1400beffa  jz      loc_1400BECA5
0x1400bf000  mov     [rdi+288h], r13d
0x1400bf007  xor     esi, esi
0x1400bf009  cmp     esi, r13d
0x1400bf00c  jnb     loc_1400BF17F
0x1400bf012  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x1400bf016  mov     [rbp+57h+Length], 50h ; 'P'
0x1400bf01d  mov     ecx, esi; ProcIndex
0x1400bf01f  call    cs:__imp_KeGetProcessorNumberFromIndex
0x1400bf026  nop     dword ptr [rax+rax+00h]
0x1400bf02b  lea     r9, [rbp+57h+Length]; Length
0x1400bf02f  mov     edx, 1; RelationshipType
0x1400bf034  lea     r8, [rbp+57h+Information]; Information
0x1400bf038  lea     rcx, [rbp+57h+ProcNumber]; ProcessorNumber
0x1400bf03c  call    cs:__imp_KeQueryLogicalProcessorRelationship
0x1400bf043  nop     dword ptr [rax+rax+00h]
0x1400bf048  mov     r8, [rdi+290h]
0x1400bf04f  xor     ecx, ecx
0x1400bf051  test    eax, eax
0x1400bf053  cmovns  ecx, dword ptr [rbp+57h+Information.8]
0x1400bf057  xor     edx, edx
0x1400bf059  mov     r9d, ecx
0x1400bf05c  shl     r9, 6
0x1400bf060  mov     r10d, ecx
0x1400bf063  mov     [rbp+57h+var_A0], r10
0x1400bf067  mov     ecx, [r8+r9+4]
0x1400bf06c  mov     eax, ecx
0x1400bf06e  div     r12d
0x1400bf071  inc     ecx
0x1400bf073  mov     [r8+r9+4], ecx
0x1400bf078  mov     rdx, [rdi+290h]
0x1400bf07f  mov     ecx, esi
0x1400bf081  add     rdx, r9
0x1400bf084  imul    r8, rcx, 0E8h
0x1400bf08b  mov     rcx, [rdi+298h]
0x1400bf092  xor     r12d, r12d
0x1400bf095  mov     dword ptr [rbp+57h+arg_0], eax
0x1400bf098  mov     [rbp+57h+var_98], r8
0x1400bf09c  mov     [r8+rcx], rdx
0x1400bf0a0  cmp     r12d, 7
0x1400bf0a4  jnb     loc_1400BF160
0x1400bf0aa  lea     rdx, [rax+rax*4]
0x1400bf0ae  mov     ecx, r12d
0x1400bf0b1  mov     rax, [rdi+290h]
0x1400bf0b8  lea     r9, [r12+r10*8]
0x1400bf0bc  shl     rdx, 4
0x1400bf0c0  shl     rcx, 5
0x1400bf0c4  add     r8, rcx
0x1400bf0c7  mov     [rbp+57h+var_A8], rdx
0x1400bf0cb  add     rdx, [rax+r9*8+8]
0x1400bf0d0  mov     rax, [rdi+298h]
0x1400bf0d7  mov     [rbp+57h+var_C8], r9
0x1400bf0db  mov     [rbp+57h+var_B8], r8
0x1400bf0df  mov     [r8+rax+18h], rdx
0x1400bf0e4  mov     rcx, [rdi+8]; DeviceObject
0x1400bf0e8  mov     rbx, [rdi+298h]
  ... truncated ...
```
