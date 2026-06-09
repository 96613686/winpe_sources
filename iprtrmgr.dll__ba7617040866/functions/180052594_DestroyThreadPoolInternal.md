# DestroyThreadPoolInternal

- ea: `0x180052594`
- end: `0x1800525e7`
- name: `DestroyThreadPoolInternal`
- size: `83`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c054`
- `0x1800525f0`

## callees

- `0x180052594`

## import_xrefs

- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800525b1`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800525b1`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800525bb`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800525bb`
- `KERNEL32!CloseThreadpool` at `0x1800525c9`
- `KERNEL32!CloseThreadpool` at `0x1800525c9`
- `KERNEL32!HeapFree` at `0x1800525db`
- `KERNEL32!HeapFree` at `0x1800525db`

## pseudocode

```c
BOOL __fastcall DestroyThreadPoolInternal(LPVOID lpMem)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  BOOL result; // eax

  if ( lpMem )
  {
    v2 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)lpMem + 1);
    if ( v2 )
    {
      CloseThreadpoolCleanupGroupMembers(v2, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)lpMem + 1));
    }
    if ( *(_QWORD *)lpMem )
      CloseThreadpool(*(PTP_POOL *)lpMem);
    return HeapFree(IPRouterHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180052594  test    rcx, rcx
0x180052597  jz      short locret_1800525E6
0x180052599  push    rbx
0x18005259a  sub     rsp, 20h
0x18005259e  mov     rbx, rcx
0x1800525a1  mov     rcx, [rcx+8]; ptpcg
0x1800525a5  test    rcx, rcx
0x1800525a8  jz      short loc_1800525C1
0x1800525aa  xor     r8d, r8d; pvCleanupContext
0x1800525ad  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800525b1  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800525b7  mov     rcx, [rbx+8]; ptpcg
0x1800525bb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800525c1  mov     rcx, [rbx]; ptpp
0x1800525c4  test    rcx, rcx
0x1800525c7  jz      short loc_1800525CF
0x1800525c9  call    cs:__imp_CloseThreadpool
0x1800525cf  mov     rcx, cs:IPRouterHeap; hHeap
0x1800525d6  mov     r8, rbx; lpMem
0x1800525d9  xor     edx, edx; dwFlags
0x1800525db  call    cs:__imp_HeapFree
0x1800525e1  add     rsp, 20h
0x1800525e5  pop     rbx
0x1800525e6  retn
```
