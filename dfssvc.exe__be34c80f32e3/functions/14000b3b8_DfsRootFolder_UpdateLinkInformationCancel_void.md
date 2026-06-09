# DfsRootFolder::UpdateLinkInformationCancel(void)

- ea: `0x14000b3b8`
- end: `0x14000b406`
- name: `?UpdateLinkInformationCancel@DfsRootFolder@@QEAAXXZ`
- size: `78`
- prototype: `void __fastcall(DfsRootFolder *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000a6cc`
- `0x14000b40c`
- `0x140021460`
- `0x1400448ec`

## callees

- `0x14000b3b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000b3d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000b3d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000b3eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000b3eb`

## pseudocode

```c
void __fastcall DfsRootFolder::UpdateLinkInformationCancel(PTP_CLEANUP_GROUP *this)
{
  if ( *((_DWORD *)this + 103) )
  {
    CloseThreadpoolCleanupGroupMembers(this[40], 1, 0);
    CloseThreadpoolCleanupGroup(this[40]);
    this[40] = 0;
  }
}

```

## disassembly

```asm
0x14000b3b8  push    rbx
0x14000b3ba  sub     rsp, 20h
0x14000b3be  cmp     dword ptr [rcx+19Ch], 0
0x14000b3c5  mov     rbx, rcx
0x14000b3c8  jz      short loc_14000B3FF
0x14000b3ca  mov     rcx, [rcx+140h]; ptpcg
0x14000b3d1  xor     r8d, r8d; pvCleanupContext
0x14000b3d4  lea     edx, [r8+1]; fCancelPendingCallbacks
0x14000b3d8  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14000b3df  nop     dword ptr [rax+rax+00h]
0x14000b3e4  mov     rcx, [rbx+140h]; ptpcg
0x14000b3eb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14000b3f2  nop     dword ptr [rax+rax+00h]
0x14000b3f7  and     qword ptr [rbx+140h], 0
0x14000b3ff  add     rsp, 20h
0x14000b403  pop     rbx
0x14000b404  retn
```
