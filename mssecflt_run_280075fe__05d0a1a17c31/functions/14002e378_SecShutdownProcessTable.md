# SecShutdownProcessTable

- ea: `0x14002e378`
- end: `0x14002e414`
- name: `SecShutdownProcessTable`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a5e8`

## callees

- `0x140009b80`
- `0x140010593`
- `0x14002c4f4`
- `0x14002e0f0`
- `0x14002e378`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002e3ba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002e3d1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002e3ba`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002e3d1`

## pseudocode

```c
__int64 SecShutdownProcessTable()
{
  void *v0; // rcx
  __int64 result; // rax

  if ( SecProcessTable )
  {
    SecCleanupProcessContexts();
    v0 = (void *)*((_QWORD *)SecProcessTable + 40);
    if ( v0 )
      SecFreePool(v0, 0x54706353u);
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)SecProcessTable + 192));
    ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)SecProcessTable + 64));
    FltDeletePushLock_0((PULONG_PTR)SecProcessTable + 1);
    SecFreePool(SecProcessTable, 0x54706353u);
    SecProcessTable = 0;
    return SecReleasePhase1InitCompleteCallback();
  }
  return result;
}

```

## disassembly

```asm
0x14002e378  sub     rsp, 28h
0x14002e37c  cmp     cs:SecProcessTable, 0
0x14002e384  jz      loc_14002E40E
0x14002e38a  call    SecCleanupProcessContexts
0x14002e38f  mov     rax, cs:SecProcessTable
0x14002e396  mov     rcx, [rax+140h]; P
0x14002e39d  test    rcx, rcx
0x14002e3a0  jz      short loc_14002E3AC
0x14002e3a2  mov     edx, 54706353h; Tag
0x14002e3a7  call    SecFreePool
0x14002e3ac  mov     rcx, cs:SecProcessTable
0x14002e3b3  add     rcx, 0C0h; Lookaside
0x14002e3ba  call    cs:__imp_ExDeletePagedLookasideList
0x14002e3c1  nop     dword ptr [rax+rax+00h]
0x14002e3c6  mov     rcx, cs:SecProcessTable
0x14002e3cd  add     rcx, 40h ; '@'; Lookaside
0x14002e3d1  call    cs:__imp_ExDeletePagedLookasideList
0x14002e3d8  nop     dword ptr [rax+rax+00h]
0x14002e3dd  mov     rcx, cs:SecProcessTable
0x14002e3e4  add     rcx, 8; PushLock
0x14002e3e8  call    FltDeletePushLock_0
0x14002e3ed  mov     rcx, cs:SecProcessTable; P
0x14002e3f4  mov     edx, 54706353h; Tag
0x14002e3f9  call    SecFreePool
0x14002e3fe  mov     cs:SecProcessTable, 0
0x14002e409  call    SecReleasePhase1InitCompleteCallback
0x14002e40e  add     rsp, 28h
0x14002e412  retn
```
