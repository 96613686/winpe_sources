# CGhostWindow::CleanupGhost(void)

- ea: `0x1800061a4`
- end: `0x1800061f5`
- name: `?CleanupGhost@CGhostWindow@@AEAAXXZ`
- size: `81`
- prototype: `void __fastcall(CGhostWindow *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180006494`
- `0x180006bb8`

## callees

- `0x1800061a4`
- `0x1800075a0`
- `0x1800075d0`
- `0x180009468`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061d9`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x1800061ee`

## pseudocode

```c
void __fastcall CGhostWindow::CleanupGhost(CGhostWindow *this)
{
  CGhostProcess **v2; // rcx
  DWORD CurrentThreadId; // eax

  *((_QWORD *)this + 6) = 0;
  CGhostWindow::SetState(this, 4);
  CGhostProcess::NotifyHideGhost(v2[2], (struct CGhostWindow *)v2);
  if ( *((_DWORD *)this + 8) )
    CGhostWindow::RemoveGhostFromProcess(this);
  CurrentThreadId = GetCurrentThreadId();
  PostThreadMessageW(CurrentThreadId, 0, 0, 0);
}

```

## disassembly

```asm
0x1800061a4  push    rbx
0x1800061a6  sub     rsp, 20h
0x1800061aa  mov     edx, 4
0x1800061af  mov     qword ptr [rcx+30h], 0
0x1800061b7  mov     rbx, rcx
0x1800061ba  call    ?SetState@CGhostWindow@@AEAA?AW4GHOSTSTATE@@W42@@Z; CGhostWindow::SetState(GHOSTSTATE)
0x1800061bf  mov     rdx, rcx; struct CGhostWindow *
0x1800061c2  mov     rcx, [rcx+10h]; this
0x1800061c6  call    ?NotifyHideGhost@CGhostProcess@@QEAAHPEAVCGhostWindow@@@Z; CGhostProcess::NotifyHideGhost(CGhostWindow *)
0x1800061cb  cmp     dword ptr [rbx+20h], 0
0x1800061cf  jz      short loc_1800061D9
0x1800061d1  mov     rcx, rbx; this
0x1800061d4  call    ?RemoveGhostFromProcess@CGhostWindow@@AEAAHXZ; CGhostWindow::RemoveGhostFromProcess(void)
0x1800061d9  call    cs:__imp_GetCurrentThreadId
0x1800061df  xor     r9d, r9d
0x1800061e2  xor     r8d, r8d
0x1800061e5  mov     ecx, eax
0x1800061e7  xor     edx, edx
0x1800061e9  add     rsp, 20h
0x1800061ed  pop     rbx
0x1800061ee  jmp     cs:__imp_PostThreadMessageW
```
