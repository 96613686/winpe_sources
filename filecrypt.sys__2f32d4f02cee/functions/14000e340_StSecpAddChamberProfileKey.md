# StSecpAddChamberProfileKey

- ea: `0x14000e340`
- end: `0x14000e5d4`
- name: `StSecpAddChamberProfileKey`
- size: `660`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000d9a8`

## callees

- `0x140001110`
- `0x140001190`
- `0x140003b80`
- `0x14000dcd8`
- `0x14000e340`
- `0x1400122e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e3a9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3f9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e431`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3a9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e3f9`
- `ntoskrnl!ExAllocatePool2` at `0x14000e431`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e477`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e477`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e51e`
- `ntoskrnl!RtlDeleteElementGenericTable` at `0x14000e51e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e53c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e53c`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14000e498`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14000e498`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000e4c9`
- `ntoskrnl!RtlNumberGenericTableElements` at `0x14000e4c9`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000e4e9`
- `ntoskrnl!RtlGetElementGenericTable` at `0x14000e4e9`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000e580`
- `FLTMGR!FltQueueGenericWorkItem` at `0x14000e580`

## pseudocode

```c
__int64 __fastcall StSecpAddChamberProfileKey(NTSTRSAFE_PCWSTR pszSrc, const void *a2, const void *a3, unsigned int a4)
{
  size_t v4; // rdi
  NTSTATUS v6; // esi
  size_t v7; // rbx
  wchar_t *Pool2; // rax
  wchar_t *v9; // r15
  void *v10; // r14
  void *v11; // r12
  void *v12; // rax
  void *v13; // rax
  __int64 v14; // rbx
  _QWORD *inserted; // rax
  ULONG v16; // r13d
  _QWORD *ElementGenericTable; // rbx
  unsigned __int8 NewElement[8]; // [rsp+30h] [rbp-40h] BYREF
  size_t pcbLength; // [rsp+38h] [rbp-38h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h]
  __int64 v23; // [rsp+60h] [rbp-10h]

  v4 = a4;
  v23 = 0;
  NewElement[0] = 0;
  Buffer = 0;
  pcbLength = 0;
  v22 = 0;
  v6 = RtlStringCbLengthW(pszSrc, (size_t)a2, &pcbLength);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v7 = pcbLength;
  Pool2 = (wchar_t *)ExAllocatePool2(256, pcbLength + 2, 1884517459);
  v9 = Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  v10 = 0;
  v11 = 0;
  v6 = RtlStringCbCopyW(Pool2, v7 + 2, pszSrc);
  if ( v6 >= 0 )
  {
    v12 = (void *)ExAllocatePool2(64, v4, 1850963027);
    v10 = v12;
    if ( v12 && (memmove(v12, a2, v4), v13 = (void *)ExAllocatePool2(64, v4, 1850963027), (v11 = v13) != 0) )
    {
      memmove(v13, a3, v4);
      *((_QWORD *)&Buffer + 1) = v9;
      *(_QWORD *)&v22 = v10;
      *((_QWORD *)&v22 + 1) = v11;
      LODWORD(v23) = v4;
      v14 = MEMORY[0xFFFFF78000000320];
      ExAcquireFastMutex(&g_StSecKeyMutex);
      inserted = RtlInsertElementGenericTable(&g_StSecCacheGenericTable, &Buffer, 0x28u, NewElement);
      if ( inserted )
      {
        if ( NewElement[0] )
        {
          v9 = 0;
          v10 = 0;
          v11 = 0;
        }
        *inserted = v14;
      }
      else
      {
        v6 = -1073741823;
      }
      v16 = RtlNumberGenericTableElements(&g_StSecCacheGenericTable);
      if ( v16 > g_CacheMaxSize )
      {
        ElementGenericTable = RtlGetElementGenericTable(&g_StSecCacheGenericTable, 0);
        v4 = ElementGenericTable[1];
        StSecpFreeNonPaged(ElementGenericTable[2], *((unsigned int *)ElementGenericTable + 8));
        StSecpFreeNonPaged(ElementGenericTable[3], *((unsigned int *)ElementGenericTable + 8));
        RtlDeleteElementGenericTable(&g_StSecCacheGenericTable, ElementGenericTable);
        StSecFree(v4);
        LODWORD(v4) = a4;
      }
      ExReleaseFastMutex(&g_StSecKeyMutex);
      if ( v16 > g_CacheCleanupTriggerSize && !_InterlockedCompareExchange(&g_WorkItemQueued, 1, 0) )
        v6 = FltQueueGenericWorkItem(
               g_WorkItem,
               g_FilterObject,
               (PFLT_GENERIC_WORKITEM_ROUTINE)StSecpCacheCleanupWorkItem,
               DelayedWorkQueue,
               0);
      if ( !v9 )
        goto LABEL_20;
    }
    else
    {
      v6 = -1073741801;
    }
  }
  StSecFree(v9);
LABEL_20:
  if ( v10 )
    StSecpFreeNonPaged(v10, (unsigned int)v4);
  if ( v11 )
    StSecpFreeNonPaged(v11, (unsigned int)v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e340  mov     rax, rsp
0x14000e343  mov     [rax+8], rbx
0x14000e347  mov     [rax+20h], r9d
0x14000e34b  mov     [rax+18h], r8
0x14000e34f  mov     [rax+10h], rdx
0x14000e353  push    rbp
0x14000e354  push    rsi
0x14000e355  push    rdi
0x14000e356  push    r12
0x14000e358  push    r13
0x14000e35a  push    r14
0x14000e35c  push    r15
0x14000e35e  mov     rbp, rsp
0x14000e361  sub     rsp, 70h
0x14000e365  xor     eax, eax
0x14000e367  mov     edi, r9d
0x14000e36a  xorps   xmm0, xmm0
0x14000e36d  mov     [rbp+var_10], rax
0x14000e371  lea     r8, [rbp+pcbLength]; pcbLength
0x14000e375  mov     [rbp+NewElement], al
0x14000e378  movups  [rbp+Buffer], xmm0
0x14000e37c  mov     [rbp+pcbLength], rax
0x14000e380  mov     r13, rcx
0x14000e383  movups  [rbp+var_20], xmm0
0x14000e387  call    RtlStringCbLengthW
0x14000e38c  mov     esi, eax
0x14000e38e  test    eax, eax
0x14000e390  js      loc_14000E5B9
0x14000e396  mov     rbx, [rbp+pcbLength]
0x14000e39a  mov     r8d, 70537453h
0x14000e3a0  mov     ecx, 100h
0x14000e3a5  lea     rdx, [rbx+2]
0x14000e3a9  call    cs:__imp_ExAllocatePool2
0x14000e3b0  nop     dword ptr [rax+rax+00h]
0x14000e3b5  mov     r15, rax
0x14000e3b8  test    rax, rax
0x14000e3bb  jnz     short loc_14000E3C7
0x14000e3bd  mov     esi, 0C0000017h
0x14000e3c2  jmp     loc_14000E5B9
0x14000e3c7  mov     r8, r13; pszSrc
0x14000e3ca  lea     rdx, [rbx+2]; cbDest
0x14000e3ce  mov     rcx, r15; pszDest
0x14000e3d1  xor     r14d, r14d
0x14000e3d4  xor     r12d, r12d
0x14000e3d7  call    RtlStringCbCopyW
0x14000e3dc  mov     esi, eax
0x14000e3de  test    eax, eax
0x14000e3e0  js      loc_14000E593
0x14000e3e6  mov     r13d, 6E537453h
0x14000e3ec  lea     ecx, [r14+40h]
0x14000e3f0  mov     r8d, r13d
0x14000e3f3  mov     rdx, rdi
0x14000e3f6  mov     rbx, rdi
0x14000e3f9  call    cs:__imp_ExAllocatePool2
0x14000e400  nop     dword ptr [rax+rax+00h]
0x14000e405  mov     r14, rax
0x14000e408  test    rax, rax
0x14000e40b  jnz     short loc_14000E417
0x14000e40d  mov     esi, 0C0000017h
0x14000e412  jmp     loc_14000E593
0x14000e417  mov     rdx, [rbp+Src]; Src
0x14000e41b  mov     r8, rbx; Size
0x14000e41e  mov     rcx, r14; void *
0x14000e421  call    memmove
0x14000e426  mov     r8d, r13d
0x14000e429  mov     rdx, rbx
0x14000e42c  mov     ecx, 40h ; '@'
0x14000e431  call    cs:__imp_ExAllocatePool2
0x14000e438  nop     dword ptr [rax+rax+00h]
0x14000e43d  mov     r12, rax
0x14000e440  test    rax, rax
0x14000e443  jz      short loc_14000E40D
0x14000e445  mov     rdx, [rbp+arg_10]; Src
0x14000e449  mov     r8, rbx; Size
0x14000e44c  mov     rcx, rax; void *
0x14000e44f  call    memmove
0x14000e454  mov     qword ptr [rbp+Buffer+8], r15
0x14000e458  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e45f  mov     qword ptr [rbp+var_20], r14
0x14000e463  mov     rbx, 0FFFFF78000000320h
0x14000e46d  mov     qword ptr [rbp+var_20+8], r12
0x14000e471  mov     dword ptr [rbp+var_10], edi
0x14000e474  mov     rbx, [rbx]
0x14000e477  call    cs:__imp_ExAcquireFastMutex
0x14000e47e  nop     dword ptr [rax+rax+00h]
0x14000e483  lea     r9, [rbp+NewElement]; NewElement
0x14000e487  mov     r8d, 28h ; '('; BufferSize
0x14000e48d  lea     rdx, [rbp+Buffer]; Buffer
0x14000e491  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e498  call    cs:__imp_RtlInsertElementGenericTable
0x14000e49f  nop     dword ptr [rax+rax+00h]
0x14000e4a4  test    rax, rax
0x14000e4a7  jnz     short loc_14000E4B0
0x14000e4a9  mov     esi, 0C0000001h
0x14000e4ae  jmp     short loc_14000E4C2
0x14000e4b0  cmp     [rbp+NewElement], 0
0x14000e4b4  jz      short loc_14000E4BF
0x14000e4b6  xor     r15d, r15d
0x14000e4b9  xor     r14d, r14d
0x14000e4bc  xor     r12d, r12d
0x14000e4bf  mov     [rax], rbx
0x14000e4c2  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e4c9  call    cs:__imp_RtlNumberGenericTableElements
0x14000e4d0  nop     dword ptr [rax+rax+00h]
0x14000e4d5  cmp     eax, cs:g_CacheMaxSize
0x14000e4db  mov     r13d, eax
0x14000e4de  jbe     short loc_14000E535
0x14000e4e0  xor     edx, edx; I
0x14000e4e2  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e4e9  call    cs:__imp_RtlGetElementGenericTable
0x14000e4f0  nop     dword ptr [rax+rax+00h]
0x14000e4f5  mov     rbx, rax
0x14000e4f8  mov     edx, [rax+20h]
0x14000e4fb  mov     rcx, [rax+10h]
0x14000e4ff  mov     rdi, [rax+8]
0x14000e503  call    StSecpFreeNonPaged
0x14000e508  mov     edx, [rbx+20h]
0x14000e50b  mov     rcx, [rbx+18h]
0x14000e50f  call    StSecpFreeNonPaged
0x14000e514  mov     rdx, rbx; Buffer
0x14000e517  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e51e  call    cs:__imp_RtlDeleteElementGenericTable
0x14000e525  nop     dword ptr [rax+rax+00h]
0x14000e52a  mov     rcx, rdi
0x14000e52d  call    StSecFree
0x14000e532  mov     edi, [rbp+arg_18]
0x14000e535  lea     rcx, g_StSecKeyMutex; FastMutex
0x14000e53c  call    cs:__imp_ExReleaseFastMutex
0x14000e543  nop     dword ptr [rax+rax+00h]
0x14000e548  cmp     r13d, cs:g_CacheCleanupTriggerSize
0x14000e54f  jbe     short loc_14000E58E
0x14000e551  xor     eax, eax
0x14000e553  lea     r9d, [rax+1]; QueueType
0x14000e557  lock cmpxchg cs:g_WorkItemQueued, r9d
0x14000e560  jnz     short loc_14000E58E
0x14000e562  mov     rdx, cs:g_FilterObject; FltObject
0x14000e569  lea     r8, StSecpCacheCleanupWorkItem; WorkerRoutine
0x14000e570  mov     rcx, cs:g_WorkItem; FltWorkItem
0x14000e577  mov     [rsp+70h+Context], 0; Context
0x14000e580  call    cs:__imp_FltQueueGenericWorkItem
0x14000e587  nop     dword ptr [rax+rax+00h]
0x14000e58c  mov     esi, eax
0x14000e58e  test    r15, r15
0x14000e591  jz      short loc_14000E59B
0x14000e593  mov     rcx, r15
0x14000e596  call    StSecFree
0x14000e59b  test    r14, r14
0x14000e59e  jz      short loc_14000E5AA
0x14000e5a0  mov     edx, edi
0x14000e5a2  mov     rcx, r14
0x14000e5a5  call    StSecpFreeNonPaged
0x14000e5aa  test    r12, r12
0x14000e5ad  jz      short loc_14000E5B9
0x14000e5af  mov     edx, edi
0x14000e5b1  mov     rcx, r12
0x14000e5b4  call    StSecpFreeNonPaged
0x14000e5b9  mov     rbx, [rsp+70h+arg_0]
0x14000e5c1  mov     eax, esi
0x14000e5c3  add     rsp, 70h
0x14000e5c7  pop     r15
0x14000e5c9  pop     r14
0x14000e5cb  pop     r13
0x14000e5cd  pop     r12
0x14000e5cf  pop     rdi
0x14000e5d0  pop     rsi
0x14000e5d1  pop     rbp
0x14000e5d2  retn
```
