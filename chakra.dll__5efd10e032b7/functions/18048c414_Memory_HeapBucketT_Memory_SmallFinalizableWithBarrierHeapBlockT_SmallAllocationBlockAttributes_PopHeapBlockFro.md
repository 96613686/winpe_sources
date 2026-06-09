# Memory::HeapBucketT<Memory::SmallFinalizableWithBarrierHeapBlockT<SmallAllocationBlockAttributes>>::PopHeapBlockFromSList(_SLIST_HEADER *)

- ea: `0x18048c414`
- end: `0x18048c453`
- name: `?PopHeapBlockFromSList@?$HeapBucketT@V?$SmallFinalizableWithBarrierHeapBlockT@VSmallAllocationBlockAttributes@@@Memory@@@Memory@@KAPEAV?$SmallFinalizableWithBarrierHeapBlockT@VSmallAllocationBlockAttributes@@@2@PEAT_SLIST_HEADER@@@Z`
- size: `63`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1800226d0`
- `0x180023360`
- `0x180028150`
- `0x1800787cc`
- `0x180078dd4`
- `0x180079538`
- `0x1800a84d0`
- `0x1800ae054`
- `0x1800aeb20`
- `0x1800b79ac`
- `0x18017e100`
- `0x18017e620`
- `0x180219828`
- `0x1802c76c0`
- `0x1802c7c54`
- `0x1802c7fa8`
- `0x1802c8d50`
- `0x1802c9b38`
- `0x1802c9de4`
- `0x1802ca9b8`
- `0x1802cafdc`
- `0x1802cb914`
- `0x18048b9b4`
- `0x18048ba9c`
- `0x18048bbd4`
- `0x18048bd0c`
- `0x18048be44`
- `0x18048bf7c`
- `0x18048c0b4`
- `0x18048c6ac`
- `0x18048c7e8`

## callees

- `0x18048c414`

## import_xrefs

- `msvcrt!_aligned_free` at `0x18048c43d`
- `msvcrt!_aligned_free` at `0x18048c43d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18048c425`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18048c425`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall Memory::HeapBucketT<Memory::SmallFinalizableWithBarrierHeapBlockT<SmallAllocationBlockAttributes>>::PopHeapBlockFromSList(
        union _SLIST_HEADER *a1)
{
  struct _SLIST_ENTRY *Next; // rbx
  PSLIST_ENTRY v2; // rax

  Next = 0;
  v2 = InterlockedPopEntrySList(a1);
  if ( v2 )
  {
    Next = v2[1].Next;
    _aligned_free(v2);
  }
  return Next;
}

```

## disassembly

```asm
0x18048c414  mov     [rsp+ListHead], rcx
0x18048c419  push    rbx
0x18048c41a  sub     rsp, 20h
0x18048c41e  mov     rcx, [rsp+28h+ListHead]; ListHead
0x18048c423  xor     ebx, ebx
0x18048c425  call    cs:__imp_InterlockedPopEntrySList
0x18048c42c  nop     dword ptr [rax+rax+00h]
0x18048c431  test    rax, rax
0x18048c434  jz      short loc_18048C449
0x18048c436  mov     rbx, [rax+10h]
0x18048c43a  mov     rcx, rax; Block
0x18048c43d  call    cs:__imp__aligned_free
0x18048c444  nop     dword ptr [rax+rax+00h]
0x18048c449  mov     rax, rbx
0x18048c44c  add     rsp, 20h
0x18048c450  pop     rbx
0x18048c451  retn
```
