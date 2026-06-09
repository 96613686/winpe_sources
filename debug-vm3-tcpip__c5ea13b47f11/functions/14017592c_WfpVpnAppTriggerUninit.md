# WfpVpnAppTriggerUninit

- ea: `0x14017592c`
- end: `0x140175c7a`
- name: `WfpVpnAppTriggerUninit`
- size: `846`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14016edb4`
- `0x14016f394`

## callees

- `0x140056c80`
- `0x140056cf0`
- `0x1400eee30`
- `0x140119fe8`
- `0x140174b50`
- `0x140174b8c`
- `0x140174bc8`
- `0x140174e14`
- `0x14017592c`
- `0x140176064`
- `0x140176f94`

## import_xrefs

- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401759c0`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401759c0`
- `ntoskrnl!KeCancelTimer` at `0x14017599b`
- `ntoskrnl!KeCancelTimer` at `0x14017599b`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175b02`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175bc4`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175b02`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x140175bc4`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175ab4`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175b76`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175ab4`
- `ntoskrnl!RtlInitEnumerationHashTable` at `0x140175b76`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175ad4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175b96`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175ad4`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140175b96`
- `ntoskrnl!KeWaitForSingleObject` at `0x140175a21`
- `ntoskrnl!KeWaitForSingleObject` at `0x140175a21`
- `NETIO!NetioShutdownWorkQueue` at `0x140175a34`
- `NETIO!NetioShutdownWorkQueue` at `0x140175a34`
- `NDIS!NdisFreeRWLock` at `0x140175a7e`
- `NDIS!NdisFreeRWLock` at `0x140175b40`
- `NDIS!NdisFreeRWLock` at `0x140175c02`
- `NDIS!NdisFreeRWLock` at `0x140175c4f`
- `NDIS!NdisFreeRWLock` at `0x140175a7e`
- `NDIS!NdisFreeRWLock` at `0x140175b40`
- `NDIS!NdisFreeRWLock` at `0x140175c02`
- `NDIS!NdisFreeRWLock` at `0x140175c4f`
- `fwpkclnt!FwpmEngineClose0` at `0x140175a64`
- `fwpkclnt!FwpmEngineClose0` at `0x140175a64`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140175a4c`
- `fwpkclnt!FwpmBfeStateUnsubscribeChanges0` at `0x140175a4c`

## pseudocode

```c
void WfpVpnAppTriggerUninit()
{
  bool v0; // bl
  __int64 v1; // rdx
  __int64 v2; // r8
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v4; // rbx
  PRTL_DYNAMIC_HASH_TABLE Enumerator[6]; // [rsp+30h] [rbp-30h] BYREF
  __int16 v6; // [rsp+80h] [rbp+20h] BYREF
  char v7; // [rsp+82h] [rbp+22h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+88h] [rbp+28h] BYREF

  v6 = 0;
  v7 = 0;
  memset(Enumerator, 0, sizeof(Enumerator));
  Entry = 0;
  if ( vpnAppTriggerModuleStarted )
  {
    v0 = 0;
    WfpAcquireFastWriteLock(&vpnTriggerLock, &v6);
    byte_1402233F8 = 1;
    _InterlockedDecrement(&dword_1402244AC);
    if ( byte_140223421 )
      v0 = KeCancelTimer(&Timer) == 0;
    WfpReleaseFastWriteLock(&vpnTriggerLock, &v6);
    if ( v0 )
      KeFlushQueuedDpcs();
    if ( nrptTriggerContext )
    {
      LOBYTE(v1) = 1;
      WfpVpnUninitNrptTriggers(0, v1, v2);
    }
    WfpVpnCalloutUninit();
    if ( nrptEventSecurity )
    {
      WfpNrptSDFree();
      nrptEventSecurity = 0;
    }
    if ( _InterlockedDecrement(&workItemRef) != 1 )
      KeWaitForSingleObject(&shutDownEvent, Executive, 0, 0, 0);
    NetioShutdownWorkQueue(appTriggerWorkQueue);
    if ( bfeChangeHandle )
      FwpmBfeStateUnsubscribeChanges0(bfeChangeHandle);
    if ( bfeSessionHandle )
    {
      FwpmEngineClose0(bfeSessionHandle);
      bfeSessionHandle = 0;
    }
    NdisFreeRWLock(vpnTriggerLock);
    vpnTriggerLock = 0;
    WfpAcquireFastWriteLock(&filePathTableLock, &v6);
    v3 = filePathTable;
    if ( filePathTable )
    {
      RtlInitEnumerationHashTable(filePathTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      Enumerator[0] = v3;
      while ( (unsigned int)WfpHashtableIteratorGetNext(Enumerator, &Entry) )
      {
        RtlRemoveEntryHashTable(filePathTable, Entry, 0);
        WfpFreeFilePathEntry(Entry);
      }
      RtlEndEnumerationHashTable(Enumerator[0], (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      WfpHashtableDestroy(filePathTable, 0);
      filePathTable = 0;
      numFilePathTableEntries = 0;
    }
    WfpReleaseFastWriteLock(&filePathTableLock, &v6);
    NdisFreeRWLock(filePathTableLock);
    filePathTableLock = 0;
    WfpAcquireFastWriteLock(&appSidTableLock, &v6);
    v4 = appSidTable;
    if ( appSidTable )
    {
      RtlInitEnumerationHashTable(appSidTable, (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      Enumerator[0] = v4;
      while ( (unsigned int)WfpHashtableIteratorGetNext(Enumerator, &Entry) )
      {
        RtlRemoveEntryHashTable(appSidTable, Entry, 0);
        WfpFreeAppSidEntry(Entry);
      }
      RtlEndEnumerationHashTable(Enumerator[0], (PRTL_DYNAMIC_HASH_TABLE_ENUMERATOR)&Enumerator[1]);
      WfpHashtableDestroy(appSidTable, 0);
      appSidTable = 0;
      numAppSidTableEntries = 0;
    }
    WfpReleaseFastWriteLock(&appSidTableLock, &v6);
    NdisFreeRWLock(appSidTableLock);
    appSidTableLock = 0;
    WfpAcquireFastWriteLock(&Lock, &v6);
    WfpFreeSecurityDescriptorEntry(qword_1402234A0);
    qword_1402234A0 = 0;
    WfpReleaseFastWriteLock(&Lock, &v6);
    NdisFreeRWLock(Lock);
    Lock = 0;
    vpnAppTriggerModuleStarted = 0;
  }
}

```

## disassembly

```asm
0x14017592c  mov     [rsp-18h+arg_10], rbx
0x140175931  push    rbp
0x140175932  push    rsi
0x140175933  push    rdi
0x140175934  mov     rbp, rsp
0x140175937  sub     rsp, 60h
0x14017593b  xor     eax, eax
0x14017593d  xorps   xmm0, xmm0
0x140175940  xor     edi, edi
0x140175942  mov     [rbp+arg_0], ax
0x140175946  cmp     cs:vpnAppTriggerModuleStarted, dil
0x14017594d  mov     [rbp+arg_2], al
0x140175950  movups  xmmword ptr [rbp+Enumerator], xmm0
0x140175954  mov     [rbp+Entry], rdi
0x140175958  movups  xmmword ptr [rbp+Enumerator+10h], xmm0
0x14017595c  movups  xmmword ptr [rbp+Enumerator+20h], xmm0
0x140175960  jz      loc_140175C69
0x140175966  lea     rdx, [rbp+arg_0]
0x14017596a  movzx   ebx, dil
0x14017596e  lea     rcx, vpnTriggerLock
0x140175975  call    WfpAcquireFastWriteLock
0x14017597a  lea     esi, [rdi+1]
0x14017597d  mov     cs:byte_1402233F8, sil
0x140175984  lock dec cs:dword_1402244AC
0x14017598b  cmp     cs:byte_140223421, dil
0x140175992  jz      short loc_1401759AC
0x140175994  lea     rcx, Timer; PKTIMER
0x14017599b  call    cs:__imp_KeCancelTimer
0x1401759a2  nop     dword ptr [rax+rax+00h]
0x1401759a7  test    al, al
0x1401759a9  cmovz   ebx, esi
0x1401759ac  lea     rdx, [rbp+arg_0]
0x1401759b0  lea     rcx, vpnTriggerLock
0x1401759b7  call    WfpReleaseFastWriteLock
0x1401759bc  test    bl, bl
0x1401759be  jz      short loc_1401759CC
0x1401759c0  call    cs:__imp_KeFlushQueuedDpcs
0x1401759c7  nop     dword ptr [rax+rax+00h]
0x1401759cc  cmp     cs:nrptTriggerContext, rdi
0x1401759d3  jz      short loc_1401759DF
0x1401759d5  mov     dl, sil
0x1401759d8  xor     ecx, ecx
0x1401759da  call    WfpVpnUninitNrptTriggers
0x1401759df  call    WfpVpnCalloutUninit
0x1401759e4  mov     rcx, cs:nrptEventSecurity
0x1401759eb  test    rcx, rcx
0x1401759ee  jz      short loc_1401759FC
0x1401759f0  call    WfpNrptSDFree
0x1401759f5  mov     cs:nrptEventSecurity, rdi
0x1401759fc  or      eax, 0FFFFFFFFh
0x1401759ff  lock xadd cs:workItemRef, eax
0x140175a07  dec     eax
0x140175a09  cmp     eax, esi
0x140175a0b  jz      short loc_140175A2D
0x140175a0d  xor     r9d, r9d; Alertable
0x140175a10  mov     [rsp+60h+Timeout], rdi; Timeout
0x140175a15  xor     r8d, r8d; WaitMode
0x140175a18  lea     rcx, shutDownEvent; Object
0x140175a1f  xor     edx, edx; WaitReason
0x140175a21  call    cs:__imp_KeWaitForSingleObject
0x140175a28  nop     dword ptr [rax+rax+00h]
0x140175a2d  lea     rcx, appTriggerWorkQueue
0x140175a34  call    cs:__imp_NetioShutdownWorkQueue
0x140175a3b  nop     dword ptr [rax+rax+00h]
0x140175a40  mov     rcx, cs:bfeChangeHandle; changeHandle
0x140175a47  test    rcx, rcx
0x140175a4a  jz      short loc_140175A58
0x140175a4c  call    cs:__imp_FwpmBfeStateUnsubscribeChanges0
0x140175a53  nop     dword ptr [rax+rax+00h]
0x140175a58  mov     rcx, cs:bfeSessionHandle; engineHandle
0x140175a5f  test    rcx, rcx
0x140175a62  jz      short loc_140175A77
0x140175a64  call    cs:__imp_FwpmEngineClose0
0x140175a6b  nop     dword ptr [rax+rax+00h]
0x140175a70  mov     cs:bfeSessionHandle, rdi
0x140175a77  mov     rcx, cs:vpnTriggerLock; Lock
0x140175a7e  call    cs:__imp_NdisFreeRWLock
0x140175a85  nop     dword ptr [rax+rax+00h]
0x140175a8a  lea     rdx, [rbp+arg_0]
0x140175a8e  mov     cs:vpnTriggerLock, rdi
0x140175a95  lea     rcx, filePathTableLock
0x140175a9c  call    WfpAcquireFastWriteLock
0x140175aa1  mov     rbx, cs:filePathTable
0x140175aa8  test    rbx, rbx
0x140175aab  jz      short loc_140175B29
0x140175aad  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175ab1  mov     rcx, rbx; HashTable
0x140175ab4  call    cs:__imp_RtlInitEnumerationHashTable
0x140175abb  nop     dword ptr [rax+rax+00h]
0x140175ac0  mov     qword ptr [rbp+Enumerator], rbx
0x140175ac4  jmp     short loc_140175AE9
0x140175ac6  mov     rdx, [rbp+Entry]; Entry
0x140175aca  xor     r8d, r8d; Context
0x140175acd  mov     rcx, cs:filePathTable; HashTable
0x140175ad4  call    cs:__imp_RtlRemoveEntryHashTable
0x140175adb  nop     dword ptr [rax+rax+00h]
0x140175ae0  mov     rcx, [rbp+Entry]
0x140175ae4  call    WfpFreeFilePathEntry
0x140175ae9  lea     rdx, [rbp+Entry]
0x140175aed  lea     rcx, [rbp+Enumerator]
0x140175af1  call    WfpHashtableIteratorGetNext
0x140175af6  test    eax, eax
0x140175af8  jnz     short loc_140175AC6
0x140175afa  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x140175afe  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175b02  call    cs:__imp_RtlEndEnumerationHashTable
0x140175b09  nop     dword ptr [rax+rax+00h]
0x140175b0e  mov     rcx, cs:filePathTable; HashTable
0x140175b15  xor     edx, edx
0x140175b17  call    WfpHashtableDestroy
0x140175b1c  mov     cs:filePathTable, rdi
0x140175b23  mov     cs:numFilePathTableEntries, edi
0x140175b29  lea     rdx, [rbp+arg_0]
0x140175b2d  lea     rcx, filePathTableLock
0x140175b34  call    WfpReleaseFastWriteLock
0x140175b39  mov     rcx, cs:filePathTableLock; Lock
0x140175b40  call    cs:__imp_NdisFreeRWLock
0x140175b47  nop     dword ptr [rax+rax+00h]
0x140175b4c  lea     rdx, [rbp+arg_0]
0x140175b50  mov     cs:filePathTableLock, rdi
0x140175b57  lea     rcx, appSidTableLock
0x140175b5e  call    WfpAcquireFastWriteLock
0x140175b63  mov     rbx, cs:appSidTable
0x140175b6a  test    rbx, rbx
0x140175b6d  jz      short loc_140175BEB
0x140175b6f  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175b73  mov     rcx, rbx; HashTable
0x140175b76  call    cs:__imp_RtlInitEnumerationHashTable
0x140175b7d  nop     dword ptr [rax+rax+00h]
0x140175b82  mov     qword ptr [rbp+Enumerator], rbx
0x140175b86  jmp     short loc_140175BAB
0x140175b88  mov     rdx, [rbp+Entry]; Entry
0x140175b8c  xor     r8d, r8d; Context
0x140175b8f  mov     rcx, cs:appSidTable; HashTable
0x140175b96  call    cs:__imp_RtlRemoveEntryHashTable
0x140175b9d  nop     dword ptr [rax+rax+00h]
0x140175ba2  mov     rcx, [rbp+Entry]
0x140175ba6  call    WfpFreeAppSidEntry
0x140175bab  lea     rdx, [rbp+Entry]
0x140175baf  lea     rcx, [rbp+Enumerator]
0x140175bb3  call    WfpHashtableIteratorGetNext
0x140175bb8  test    eax, eax
0x140175bba  jnz     short loc_140175B88
0x140175bbc  mov     rcx, qword ptr [rbp+Enumerator]; HashTable
0x140175bc0  lea     rdx, [rbp+Enumerator+8]; Enumerator
0x140175bc4  call    cs:__imp_RtlEndEnumerationHashTable
0x140175bcb  nop     dword ptr [rax+rax+00h]
0x140175bd0  mov     rcx, cs:appSidTable; HashTable
0x140175bd7  xor     edx, edx
0x140175bd9  call    WfpHashtableDestroy
0x140175bde  mov     cs:appSidTable, rdi
0x140175be5  mov     cs:numAppSidTableEntries, edi
0x140175beb  lea     rdx, [rbp+arg_0]
0x140175bef  lea     rcx, appSidTableLock
0x140175bf6  call    WfpReleaseFastWriteLock
0x140175bfb  mov     rcx, cs:appSidTableLock; Lock
0x140175c02  call    cs:__imp_NdisFreeRWLock
0x140175c09  nop     dword ptr [rax+rax+00h]
0x140175c0e  lea     rdx, [rbp+arg_0]
0x140175c12  mov     cs:appSidTableLock, rdi
0x140175c19  lea     rcx, Lock
0x140175c20  call    WfpAcquireFastWriteLock
0x140175c25  mov     rcx, cs:qword_1402234A0
0x140175c2c  call    WfpFreeSecurityDescriptorEntry
0x140175c31  lea     rdx, [rbp+arg_0]
0x140175c35  mov     cs:qword_1402234A0, rdi
0x140175c3c  lea     rcx, Lock
0x140175c43  call    WfpReleaseFastWriteLock
0x140175c48  mov     rcx, cs:Lock; Lock
0x140175c4f  call    cs:__imp_NdisFreeRWLock
0x140175c56  nop     dword ptr [rax+rax+00h]
0x140175c5b  mov     cs:Lock, rdi
0x140175c62  mov     cs:vpnAppTriggerModuleStarted, dil
0x140175c69  mov     rbx, [rsp+60h+arg_10]
0x140175c71  add     rsp, 60h
0x140175c75  pop     rdi
0x140175c76  pop     rsi
0x140175c77  pop     rbp
0x140175c78  retn
```
