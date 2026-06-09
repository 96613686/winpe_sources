# RemoveFilterFromFilterHashtable

- ea: `0x1400342b0`
- end: `0x1400343dc`
- name: `RemoveFilterFromFilterHashtable`
- size: `300`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001b4e8`
- `0x14004bd30`
- `0x14006896c`

## callees

- `0x140009520`
- `0x140009e00`
- `0x1400342b0`
- `0x1400343f0`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140034327`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140034327`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034341`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034341`
- `NDIS!NdisReleaseRWLock` at `0x140034360`
- `NDIS!NdisReleaseRWLock` at `0x14003438e`
- `NDIS!NdisReleaseRWLock` at `0x140034360`
- `NDIS!NdisReleaseRWLock` at `0x14003438e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400342ea`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400342ea`

## string_xrefs

- `0x1400343cb`: `RemoveFilterFromFilterHashtable`
- `0x1400343b4`: `RtlRemoveEntryHashTable`

## pseudocode

```c
__int64 __fastcall RemoveFilterFromFilterHashtable(unsigned __int16 a1, __int64 a2)
{
  __int64 EntryFromFilterHashtable; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v5; // rdi
  __int64 v6; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+18h] BYREF
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+48h] [rbp+20h] BYREF

  Entry = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
  EntryFromFilterHashtable = FindEntryFromFilterHashtable(a1, a2, &Entry);
  if ( !EntryFromFilterHashtable )
  {
    v5 = Entry;
    if ( RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)&gWfpGlobal[3].L.Depth, Entry, 0) )
    {
      if ( v5 )
      {
        ExFreePoolWithTag(v5, 0);
        NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
        return 0;
      }
    }
    else
    {
      EntryFromFilterHashtable = WfpReportSysErrorAsNtStatus(v6, "RtlRemoveEntryHashTable", 3221225473LL, 1);
    }
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
  if ( EntryFromFilterHashtable )
    WfpReportError(EntryFromFilterHashtable, "RemoveFilterFromFilterHashtable");
  return EntryFromFilterHashtable;
}

```

## disassembly

```asm
0x1400342b0  mov     [rsp+arg_0], rbx
0x1400342b5  push    rdi
0x1400342b6  sub     rsp, 20h
0x1400342ba  movzx   edi, cx
0x1400342bd  mov     [rsp+28h+Entry], 0
0x1400342c6  mov     rcx, cs:gWfpGlobal
0x1400342cd  xor     eax, eax
0x1400342cf  mov     rbx, rdx
0x1400342d2  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400342d7  mov     [rsp+28h+LockState.Flags], al
0x1400342db  lea     rdx, [rsp+28h+LockState]; LockState
0x1400342e0  mov     r8b, 1; Flags
0x1400342e3  mov     rcx, [rcx+6C0h]; Lock
0x1400342ea  call    cs:__imp_NdisAcquireRWLockWrite
0x1400342f1  nop     dword ptr [rax+rax+00h]
0x1400342f6  lea     r8, [rsp+28h+Entry]
0x1400342fb  mov     rdx, rbx
0x1400342fe  movzx   ecx, di
0x140034301  call    FindEntryFromFilterHashtable
0x140034306  mov     rbx, rax
0x140034309  test    rax, rax
0x14003430c  jnz     short loc_14003437B
0x14003430e  mov     rcx, cs:gWfpGlobal
0x140034315  xor     r8d, r8d; Context
0x140034318  mov     rdi, [rsp+28h+Entry]
0x14003431d  mov     rdx, rdi; Entry
0x140034320  mov     rcx, [rcx+190h]; HashTable
0x140034327  call    cs:__imp_RtlRemoveEntryHashTable
0x14003432e  nop     dword ptr [rax+rax+00h]
0x140034333  test    al, al
0x140034335  jz      short loc_1400343AE
0x140034337  test    rdi, rdi
0x14003433a  jz      short loc_14003437B
0x14003433c  xor     edx, edx; Tag
0x14003433e  mov     rcx, rdi; P
0x140034341  call    cs:__imp_ExFreePoolWithTag
0x140034348  nop     dword ptr [rax+rax+00h]
0x14003434d  mov     rcx, cs:gWfpGlobal
0x140034354  lea     rdx, [rsp+28h+LockState]; LockState
0x140034359  mov     rcx, [rcx+6C0h]; Lock
0x140034360  call    cs:__imp_NdisReleaseRWLock
0x140034367  nop     dword ptr [rax+rax+00h]
0x14003436c  mov     rax, rbx
0x14003436f  mov     rbx, [rsp+28h+arg_0]
0x140034374  add     rsp, 20h
0x140034378  pop     rdi
0x140034379  retn
0x14003437b  mov     rcx, cs:gWfpGlobal
0x140034382  lea     rdx, [rsp+28h+LockState]; LockState
0x140034387  mov     rcx, [rcx+6C0h]; Lock
0x14003438e  call    cs:__imp_NdisReleaseRWLock
0x140034395  nop     dword ptr [rax+rax+00h]
0x14003439a  test    rbx, rbx
0x14003439d  jnz     short loc_1400343CB
0x14003439f  mov     rax, rbx
0x1400343a2  mov     rbx, [rsp+28h+arg_0]
0x1400343a7  add     rsp, 20h
0x1400343ab  pop     rdi
0x1400343ac  retn
0x1400343ae  mov     r9d, 1
0x1400343b4  lea     rdx, aRtlremoveentry; "RtlRemoveEntryHashTable"
0x1400343bb  mov     r8d, 0C0000001h
0x1400343c1  call    WfpReportSysErrorAsNtStatus
0x1400343c6  mov     rbx, rax
0x1400343c9  jmp     short loc_14003437B
0x1400343cb  lea     rdx, aRemovefilterfr; "RemoveFilterFromFilterHashtable"
0x1400343d2  mov     rcx, rbx
0x1400343d5  call    WfpReportError
0x1400343da  jmp     short loc_14003439F
```
