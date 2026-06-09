# DrvSurfaceComplete

- ea: `0x14000e710`
- end: `0x14000e77e`
- name: `DrvSurfaceComplete`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000e710`
- `0x14000fbb4`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000e72f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000e72f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e75b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000e75b`

## pseudocode

```c
__int64 __fastcall DrvSurfaceComplete(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi

  v2 = *(_QWORD *)(a1 + 5488);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v2);
  *(_QWORD *)(a1 + 3648) = a2;
  LODWORD(a2) = (int)CddIssueCommand(a1, 20) >= 0;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v2);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x14000e710  mov     [rsp+arg_0], rbx
0x14000e715  mov     [rsp+arg_8], rsi
0x14000e71a  push    rdi
0x14000e71b  sub     rsp, 20h
0x14000e71f  mov     rsi, [rcx+1570h]
0x14000e726  mov     rdi, rcx
0x14000e729  mov     rcx, rsi
0x14000e72c  mov     rbx, rdx
0x14000e72f  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000e736  nop     dword ptr [rax+rax+00h]
0x14000e73b  mov     edx, 14h
0x14000e740  mov     [rdi+0E40h], rbx
0x14000e747  mov     rcx, rdi
0x14000e74a  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x14000e74f  test    eax, eax
0x14000e751  js      short loc_14000E77A
0x14000e753  mov     ebx, 1
0x14000e758  mov     rcx, rsi
0x14000e75b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14000e762  nop     dword ptr [rax+rax+00h]
0x14000e767  mov     rsi, [rsp+28h+arg_8]
0x14000e76c  mov     eax, ebx
0x14000e76e  mov     rbx, [rsp+28h+arg_0]
0x14000e773  add     rsp, 20h
0x14000e777  pop     rdi
0x14000e778  retn
0x14000e77a  xor     ebx, ebx
0x14000e77c  jmp     short loc_14000E758
```
