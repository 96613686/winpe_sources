# FlpCreateInterface

- ea: `0x140148ad0`
- end: `0x140148f1b`
- name: `FlpCreateInterface`
- size: `1099`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140147f80`
- `0x14014a040`
- `0x1401bed7c`

## callees

- `0x14004e530`
- `0x140054138`
- `0x1400c80d8`
- `0x140148ad0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140148d10`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140148d10`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140148b2c`
- `ntoskrnl!ExInitializeRundownProtection` at `0x140148b2c`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148e90`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148ea5`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148eba`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148e90`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148ea5`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140148eba`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b42`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b5c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b76`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b42`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b5c`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140148b76`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d20`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d30`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d40`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d20`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d30`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140148d40`
- `ntoskrnl!IoAllocateWorkItem` at `0x140148bda`
- `ntoskrnl!IoAllocateWorkItem` at `0x140148bda`
- `ntoskrnl!IoFreeWorkItem` at `0x140148e7b`
- `ntoskrnl!IoFreeWorkItem` at `0x140148e7b`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148e29`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148e41`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148e29`
- `ntoskrnl!RtlDeleteHashTable` at `0x140148e41`
- `ntoskrnl!RtlCreateHashTable` at `0x140148c61`
- `ntoskrnl!RtlCreateHashTable` at `0x140148ca0`
- `ntoskrnl!RtlCreateHashTable` at `0x140148c61`
- `ntoskrnl!RtlCreateHashTable` at `0x140148ca0`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140148af2`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140148af2`
- `ntoskrnl!KeInitializeEvent` at `0x140148d77`
- `ntoskrnl!KeInitializeEvent` at `0x140148d8f`
- `ntoskrnl!KeInitializeEvent` at `0x140148d77`
- `ntoskrnl!KeInitializeEvent` at `0x140148d8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148ef9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148ef9`
- `NETIO!NetioInitializeWorkQueue` at `0x140148c1d`
- `NETIO!NetioInitializeWorkQueue` at `0x140148c1d`
- `NETIO!NetioShutdownWorkQueue` at `0x140148ecf`
- `NETIO!NetioShutdownWorkQueue` at `0x140148ecf`
- `NDIS!NdisFreeRWLock` at `0x140148ee4`
- `NDIS!NdisFreeRWLock` at `0x140148ee4`
- `NDIS!NdisAllocateRWLock` at `0x140148ba5`
- `NDIS!NdisAllocateRWLock` at `0x140148ba5`

## pseudocode

```c
struct _EX_RUNDOWN_REF *__fastcall FlpCreateInterface(ULONG_PTR a1)
{
  ULONG MaximumProcessorCount; // eax
  struct _EX_RUNDOWN_REF *Memory; // rax
  struct _EX_RUNDOWN_REF *v4; // rbx
  char v5; // di
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  __int64 v7; // r8
  PNDIS_RW_LOCK_EX RWLock; // rax
  const wchar_t *v9; // r9
  PIO_WORKITEM WorkItem; // rax
  __int64 v11; // r8
  char v12; // si
  __int64 v13; // rdx
  __int64 v14; // rcx
  struct _EX_RUNDOWN_REF *v15; // rax
  struct _EX_RUNDOWN_REF *result; // rax
  unsigned int v17; // ecx
  struct _IO_WORKITEM *Count; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v19; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v20; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v21; // rcx
  struct _NDIS_RW_LOCK_EX *v22; // rcx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+48h] [rbp+10h] BYREF

  HashTable = 0;
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  Memory = (struct _EX_RUNDOWN_REF *)FlpAllocateMemory(32 * MaximumProcessorCount + 1608);
  v4 = Memory;
  if ( !Memory )
    return 0;
  Memory[124].Count = (ULONG_PTR)&Memory[201];
  v5 = 0;
  ExInitializeRundownProtection(Memory + 7);
  v4[8].Count = (ULONG_PTR)ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  v4[9].Count = (ULONG_PTR)ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x49706C46u);
  v4[10].Count = (ULONG_PTR)CacheAwareRundownProtection;
  if ( !v4[8].Count || !v4[9].Count || !CacheAwareRundownProtection )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      v9 = L"interface locks (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  RWLock = NdisAllocateRWLock(0);
  v4[5].Count = (ULONG_PTR)RWLock;
  if ( !RWLock )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      v9 = L"Ndislock (FLNG)";
LABEL_29:
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v7, v9);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  WorkItem = IoAllocateWorkItem(FlpDeviceObject);
  v4[12].Count = (ULONG_PTR)WorkItem;
  if ( !WorkItem )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      v9 = L"interface work item (FLNG)";
      goto LABEL_29;
    }
LABEL_30:
    Count = (struct _IO_WORKITEM *)v4[12].Count;
    if ( Count )
      IoFreeWorkItem(Count);
    v19 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[8].Count;
    if ( v19 )
      ExFreeCacheAwareRundownProtection(v19);
    v20 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[9].Count;
    if ( v20 )
      ExFreeCacheAwareRundownProtection(v20);
    v21 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v4[10].Count;
    if ( v21 )
      ExFreeCacheAwareRundownProtection(v21);
    if ( v5 )
      NetioShutdownWorkQueue(&v4[15]);
    v22 = (struct _NDIS_RW_LOCK_EX *)v4[5].Count;
    if ( v22 )
    {
      NdisFreeRWLock(v22);
      v4[5].Count = 0;
    }
    ExFreePoolWithTag(v4, 0);
    return 0;
  }
  if ( (int)NetioInitializeWorkQueue(&v4[15], FlIfProviderQuerySystemWorker, WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0) < 0 )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      v9 = L"Virtual If work queue (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)&v4[26];
  v5 = 1;
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
    {
      v9 = L"IsolationIdClientInterfaceTable (FLNG)";
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)&v4[31];
  if ( !RtlCreateHashTable(&HashTable, 0, 0) )
  {
    v12 = 0;
    if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
      McTemplateK0z_EtwWriteTransfer(
        &MICROSOFT_TCPIP_PROVIDER_Context,
        TCPIP_MEMORY_FAILURES,
        v11,
        L"IfIndexClientInterfaceTable (FLNG)");
    goto LABEL_25;
  }
  if ( !(unsigned __int8)RoReferenceEx(*(_QWORD *)(a1 + 216) + 32LL) )
  {
    v12 = 1;
LABEL_25:
    RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)&v4[26]);
    if ( v12 )
      RtlDeleteHashTable((PRTL_DYNAMIC_HASH_TABLE)&v4[31]);
    goto LABEL_30;
  }
  v4[4].Count = a1;
  v4[3].Count = (ULONG_PTR)&v4[2];
  v4[2].Count = (ULONG_PTR)&v4[2];
  LODWORD(v4[6].Count) = 1;
  LODWORD(v4[11].Count) = 1;
  ExWaitForRundownProtectionRelease(v4 + 7);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[8].Count);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[9].Count);
  ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v4[10].Count);
  HIDWORD(v4[107].Ptr) = 1;
  v4[112].Count = (ULONG_PTR)&v4[111];
  v4[111].Count = (ULONG_PTR)&v4[111];
  v4[14].Count = (ULONG_PTR)&v4[13];
  v4[13].Count = (ULONG_PTR)&v4[13];
  KeInitializeEvent((PRKEVENT)&v4[21], SynchronizationEvent, 0);
  KeInitializeEvent((PRKEVENT)&v4[108], SynchronizationEvent, 0);
  v13 = 0;
  LODWORD(v4[24].Count) = 0;
  v14 = 0;
  LODWORD(v4[40].Count) = -1;
  LODWORD(v4[41].Count) = 0;
  do
  {
    ++v13;
    v15 = &v4[v14 + 42];
    v4[v14 + 43].Count = (ULONG_PTR)v15;
    v4[v14 + 42].Count = (ULONG_PTR)v15;
    v14 += 2;
  }
  while ( v13 != 29 );
  BYTE1(v4[155].Count) = 1;
  result = v4;
  BYTE3(v4[155].Ptr) = 64;
  BYTE4(v4[155].Ptr) = *(_BYTE *)(a1 + 384);
  v17 = HIDWORD(v4[158].Ptr) & 0xFFFFFBFF;
  v4[157].Count = 0;
  HIDWORD(v4[158].Ptr) = v17 | 0x1FF;
  return result;
}

```

## disassembly

```asm
0x140148ad0  mov     [rsp+arg_0], rbx
0x140148ad5  mov     [rsp+arg_10], rbp
0x140148ada  push    rsi
0x140148adb  push    rdi
0x140148adc  push    r12
0x140148ade  sub     rsp, 20h
0x140148ae2  mov     rsi, rcx
0x140148ae5  xor     r12d, r12d
0x140148ae8  mov     ecx, 0FFFFh; GroupNumber
0x140148aed  mov     [rsp+38h+HashTable], r12
0x140148af2  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140148af9  nop     dword ptr [rax+rax+00h]
0x140148afe  shl     eax, 5
0x140148b01  lea     ecx, [rax+648h]
0x140148b07  call    FlpAllocateMemory
0x140148b0c  mov     rbx, rax
0x140148b0f  test    rax, rax
0x140148b12  jz      loc_140148F05
0x140148b18  add     rax, 648h
0x140148b1e  lea     rcx, [rbx+38h]; RunRef
0x140148b22  mov     [rbx+3E0h], rax
0x140148b29  mov     dil, r12b
0x140148b2c  call    cs:__imp_ExInitializeRundownProtection
0x140148b33  nop     dword ptr [rax+rax+00h]
0x140148b38  mov     edx, 49706C46h; PoolTag
0x140148b3d  mov     ecx, 200h; PoolType
0x140148b42  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140148b49  nop     dword ptr [rax+rax+00h]
0x140148b4e  mov     edx, 49706C46h; PoolTag
0x140148b53  mov     ecx, 200h; PoolType
0x140148b58  mov     [rbx+40h], rax
0x140148b5c  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140148b63  nop     dword ptr [rax+rax+00h]
0x140148b68  mov     edx, 49706C46h; PoolTag
0x140148b6d  mov     ecx, 200h; PoolType
0x140148b72  mov     [rbx+48h], rax
0x140148b76  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140148b7d  nop     dword ptr [rax+rax+00h]
0x140148b82  mov     [rbx+50h], rax
0x140148b86  cmp     [rbx+40h], r12
0x140148b8a  jz      loc_140148E4F
0x140148b90  cmp     [rbx+48h], r12
0x140148b94  jz      loc_140148E4F
0x140148b9a  test    rax, rax
0x140148b9d  jz      loc_140148E4F
0x140148ba3  xor     ecx, ecx; NdisHandle
0x140148ba5  call    cs:__imp_NdisAllocateRWLock
0x140148bac  nop     dword ptr [rax+rax+00h]
0x140148bb1  mov     [rbx+28h], rax
0x140148bb5  test    rax, rax
0x140148bb8  jnz     short loc_140148BD3
0x140148bba  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148bc1  jge     loc_140148E72
0x140148bc7  lea     r9, aNdislockFlng; "Ndislock (FLNG)"
0x140148bce  jmp     loc_140148E5F
0x140148bd3  mov     rcx, cs:FlpDeviceObject; DeviceObject
0x140148bda  call    cs:__imp_IoAllocateWorkItem
0x140148be1  nop     dword ptr [rax+rax+00h]
0x140148be6  mov     [rbx+60h], rax
0x140148bea  test    rax, rax
0x140148bed  jnz     short loc_140148C08
0x140148bef  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148bf6  jge     loc_140148E72
0x140148bfc  lea     r9, aInterfaceWorkI; "interface work item (FLNG)"
0x140148c03  jmp     loc_140148E5F
0x140148c08  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140148c0f  lea     rcx, [rbx+78h]
0x140148c13  xor     r9d, r9d
0x140148c16  lea     rdx, FlIfProviderQuerySystemWorker
0x140148c1d  call    cs:__imp_NetioInitializeWorkQueue
0x140148c24  nop     dword ptr [rax+rax+00h]
0x140148c29  test    eax, eax
0x140148c2b  jns     short loc_140148C46
0x140148c2d  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148c34  jge     loc_140148E72
0x140148c3a  lea     r9, aVirtualIfWorkQ; "Virtual If work queue (FLNG)"
0x140148c41  jmp     loc_140148E5F
0x140148c46  lea     rax, [rbx+0D0h]
0x140148c4d  xor     r8d, r8d; Flags
0x140148c50  xor     edx, edx; Shift
0x140148c52  mov     [rsp+38h+HashTable], rax
0x140148c57  lea     rcx, [rsp+38h+HashTable]; HashTable
0x140148c5c  mov     edi, 1
0x140148c61  call    cs:__imp_RtlCreateHashTable
0x140148c68  nop     dword ptr [rax+rax+00h]
0x140148c6d  test    al, al
0x140148c6f  jnz     short loc_140148C8A
0x140148c71  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148c78  jge     loc_140148E72
0x140148c7e  lea     r9, aIsolationidcli; "IsolationIdClientInterfaceTable (FLNG)"
0x140148c85  jmp     loc_140148E5F
0x140148c8a  lea     rax, [rbx+0F8h]
0x140148c91  xor     r8d, r8d; Flags
0x140148c94  xor     edx, edx; Shift
0x140148c96  mov     [rsp+38h+HashTable], rax
0x140148c9b  lea     rcx, [rsp+38h+HashTable]; HashTable
0x140148ca0  call    cs:__imp_RtlCreateHashTable
0x140148ca7  nop     dword ptr [rax+rax+00h]
0x140148cac  test    al, al
0x140148cae  jnz     short loc_140148CDF
0x140148cb0  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148cb7  mov     sil, r12b
0x140148cba  jge     loc_140148E22
0x140148cc0  lea     r9, aIfindexclienti; "IfIndexClientInterfaceTable (FLNG)"
0x140148cc7  lea     rdx, TCPIP_MEMORY_FAILURES
0x140148cce  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140148cd5  call    McTemplateK0z_EtwWriteTransfer
0x140148cda  jmp     loc_140148E22
0x140148cdf  mov     rcx, [rsi+0D8h]
0x140148ce6  add     rcx, 20h ; ' '
0x140148cea  call    RoReferenceEx
0x140148cef  test    al, al
0x140148cf1  jz      loc_140148E1F
0x140148cf7  lea     rax, [rbx+10h]
0x140148cfb  mov     [rbx+20h], rsi
0x140148cff  mov     [rax+8], rax
0x140148d03  lea     rcx, [rbx+38h]; RunRef
0x140148d07  mov     [rax], rax
0x140148d0a  mov     [rbx+30h], edi
0x140148d0d  mov     [rbx+58h], edi
0x140148d10  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140148d17  nop     dword ptr [rax+rax+00h]
0x140148d1c  mov     rcx, [rbx+40h]; RunRef
0x140148d20  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148d27  nop     dword ptr [rax+rax+00h]
0x140148d2c  mov     rcx, [rbx+48h]; RunRef
0x140148d30  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148d37  nop     dword ptr [rax+rax+00h]
0x140148d3c  mov     rcx, [rbx+50h]; RunRef
0x140148d40  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140148d47  nop     dword ptr [rax+rax+00h]
0x140148d4c  lea     rax, [rbx+378h]
0x140148d53  mov     [rbx+35Ch], edi
0x140148d59  mov     [rax+8], rax
0x140148d5d  lea     rcx, [rbx+0A8h]; Event
0x140148d64  mov     [rax], rax
0x140148d67  xor     r8d, r8d; State
0x140148d6a  lea     rax, [rbx+68h]
0x140148d6e  mov     edx, edi; Type
0x140148d70  mov     [rax+8], rax
0x140148d74  mov     [rax], rax
0x140148d77  call    cs:__imp_KeInitializeEvent
0x140148d7e  nop     dword ptr [rax+rax+00h]
0x140148d83  lea     rcx, [rbx+360h]; Event
0x140148d8a  xor     r8d, r8d; State
0x140148d8d  mov     edx, edi; Type
0x140148d8f  call    cs:__imp_KeInitializeEvent
0x140148d96  nop     dword ptr [rax+rax+00h]
0x140148d9b  mov     rdx, r12
0x140148d9e  mov     [rbx+0C0h], r12d
0x140148da5  mov     rcx, r12
0x140148da8  mov     dword ptr [rbx+140h], 0FFFFFFFFh
0x140148db2  mov     [rbx+148h], r12d
0x140148db9  lea     rax, [rbx+150h]
0x140148dc0  add     rdx, rdi
0x140148dc3  add     rax, rcx
0x140148dc6  mov     [rbx+rcx+158h], rax
0x140148dce  mov     [rbx+rcx+150h], rax
0x140148dd6  add     rcx, 10h
0x140148dda  cmp     rdx, 1Dh
0x140148dde  jnz     short loc_140148DB9
0x140148de0  mov     [rbx+4D9h], dil
0x140148de7  mov     rax, rbx
0x140148dea  mov     byte ptr [rbx+4DBh], 40h ; '@'
0x140148df1  mov     cl, [rsi+180h]
0x140148df7  mov     [rbx+4DCh], cl
0x140148dfd  mov     ecx, [rbx+4F4h]
0x140148e03  btr     ecx, 0Ah
0x140148e07  mov     [rbx+4E8h], r12
0x140148e0e  or      ecx, 1FFh
0x140148e14  mov     [rbx+4F4h], ecx
0x140148e1a  jmp     loc_140148F07
0x140148e1f  mov     sil, dil
0x140148e22  lea     rcx, [rbx+0D0h]; HashTable
0x140148e29  call    cs:__imp_RtlDeleteHashTable
0x140148e30  nop     dword ptr [rax+rax+00h]
0x140148e35  test    sil, sil
0x140148e38  jz      short loc_140148E72
0x140148e3a  lea     rcx, [rbx+0F8h]; HashTable
0x140148e41  call    cs:__imp_RtlDeleteHashTable
0x140148e48  nop     dword ptr [rax+rax+00h]
0x140148e4d  jmp     short loc_140148E72
0x140148e4f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, r12b
0x140148e56  jge     short loc_140148E72
0x140148e58  lea     r9, aInterfaceLocks; "interface locks (FLNG)"
0x140148e5f  lea     rdx, TCPIP_MEMORY_FAILURES
0x140148e66  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140148e6d  call    McTemplateK0z_EtwWriteTransfer
0x140148e72  mov     rcx, [rbx+60h]; IoWorkItem
0x140148e76  test    rcx, rcx
0x140148e79  jz      short loc_140148E87
0x140148e7b  call    cs:__imp_IoFreeWorkItem
0x140148e82  nop     dword ptr [rax+rax+00h]
0x140148e87  mov     rcx, [rbx+40h]; RunRefCacheAware
0x140148e8b  test    rcx, rcx
0x140148e8e  jz      short loc_140148E9C
0x140148e90  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148e97  nop     dword ptr [rax+rax+00h]
0x140148e9c  mov     rcx, [rbx+48h]; RunRefCacheAware
0x140148ea0  test    rcx, rcx
0x140148ea3  jz      short loc_140148EB1
0x140148ea5  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148eac  nop     dword ptr [rax+rax+00h]
0x140148eb1  mov     rcx, [rbx+50h]; RunRefCacheAware
0x140148eb5  test    rcx, rcx
0x140148eb8  jz      short loc_140148EC6
0x140148eba  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140148ec1  nop     dword ptr [rax+rax+00h]
0x140148ec6  test    dil, dil
0x140148ec9  jz      short loc_140148EDB
0x140148ecb  lea     rcx, [rbx+78h]
0x140148ecf  call    cs:__imp_NetioShutdownWorkQueue
0x140148ed6  nop     dword ptr [rax+rax+00h]
0x140148edb  mov     rcx, [rbx+28h]; Lock
0x140148edf  test    rcx, rcx
0x140148ee2  jz      short loc_140148EF4
0x140148ee4  call    cs:__imp_NdisFreeRWLock
0x140148eeb  nop     dword ptr [rax+rax+00h]
0x140148ef0  mov     [rbx+28h], r12
0x140148ef4  xor     edx, edx; Tag
0x140148ef6  mov     rcx, rbx; P
0x140148ef9  call    cs:__imp_ExFreePoolWithTag
0x140148f00  nop     dword ptr [rax+rax+00h]
0x140148f05  xor     eax, eax
0x140148f07  mov     rbx, [rsp+38h+arg_0]
0x140148f0c  mov     rbp, [rsp+38h+arg_10]
0x140148f11  add     rsp, 20h
0x140148f15  pop     r12
0x140148f17  pop     rdi
0x140148f18  pop     rsi
0x140148f19  retn
```
