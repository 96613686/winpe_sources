# CGhostWindow::DestroyGhostWindow(void)

- ea: `0x180006494`
- end: `0x180006531`
- name: `?DestroyGhostWindow@CGhostWindow@@QEAAHXZ`
- size: `157`
- prototype: `_BOOL8 __fastcall(HWND *this)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800061fc`
- `0x180007e64`
- `0x1800084c8`
- `0x1800086b8`
- `0x180008fb4`
- `0x180009944`
- `0x18000a020`

## callees

- `0x1800061a4`
- `0x180006494`
- `0x180006bac`
- `0x1800075d0`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800064ea`
- `USER32!SetWindowLongPtrW` at `0x1800064ea`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x180006513`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageW` at `0x180006513`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800064ca`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800064ca`

## pseudocode

```c
_BOOL8 __fastcall CGhostWindow::DestroyGhostWindow(HWND *this)
{
  int State; // eax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  DWORD v7; // ecx

  State = CGhostWindow::GetState(this);
  if ( State )
  {
    v4 = State - 1;
    if ( v4 && (v5 = v4 - 1) != 0 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 1 )
          return (unsigned int)CGhostWindow::GetState(this) == 4;
        goto LABEL_12;
      }
    }
    else
    {
      CGhostWindow::SetState(v3, 3);
    }
    if ( DestroyWindow(*(HWND *)(v3 + 48)) && (unsigned int)CGhostWindow::GetState(this) != 4 )
    {
      SetWindowLongPtrW(this[6], 0, 0);
      CGhostWindow::CleanupGhost((CGhostWindow *)this);
    }
  }
  else
  {
    CGhostWindow::SetState(v3, 4);
  }
LABEL_12:
  v7 = *((_DWORD *)this + 14);
  if ( v7 )
    PostThreadMessageW(v7, 0, 0, 0);
  return (unsigned int)CGhostWindow::GetState(this) == 4;
}

```

## disassembly

```asm
0x180006494  push    rbx
0x180006496  sub     rsp, 20h
0x18000649a  mov     rbx, rcx
0x18000649d  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x1800064a2  test    eax, eax
0x1800064a4  jz      short loc_1800064FA
0x1800064a6  sub     eax, 1
0x1800064a9  jz      short loc_1800064BC
0x1800064ab  sub     eax, 1
0x1800064ae  jz      short loc_1800064BC
0x1800064b0  sub     eax, 1
0x1800064b3  jz      short loc_1800064C6
0x1800064b5  cmp     eax, 1
0x1800064b8  jz      short loc_180006504
0x1800064ba  jmp     short loc_180006519
0x1800064bc  mov     edx, 3
0x1800064c1  call    ?SetState@CGhostWindow@@AEAA?AW4GHOSTSTATE@@W42@@Z; CGhostWindow::SetState(GHOSTSTATE)
0x1800064c6  mov     rcx, [rcx+30h]; hWnd
0x1800064ca  call    cs:__imp_DestroyWindow
0x1800064d0  test    eax, eax
0x1800064d2  jz      short loc_180006504
0x1800064d4  mov     rcx, rbx
0x1800064d7  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x1800064dc  cmp     eax, 4
0x1800064df  jz      short loc_180006504
0x1800064e1  mov     rcx, [rbx+30h]; hWnd
0x1800064e5  xor     r8d, r8d; dwNewLong
0x1800064e8  xor     edx, edx; nIndex
0x1800064ea  call    cs:__imp_SetWindowLongPtrW
0x1800064f0  mov     rcx, rbx; this
0x1800064f3  call    ?CleanupGhost@CGhostWindow@@AEAAXXZ; CGhostWindow::CleanupGhost(void)
0x1800064f8  jmp     short loc_180006504
0x1800064fa  mov     edx, 4
0x1800064ff  call    ?SetState@CGhostWindow@@AEAA?AW4GHOSTSTATE@@W42@@Z; CGhostWindow::SetState(GHOSTSTATE)
0x180006504  mov     ecx, [rbx+38h]; idThread
0x180006507  test    ecx, ecx
0x180006509  jz      short loc_180006519
0x18000650b  xor     r9d, r9d; lParam
0x18000650e  xor     r8d, r8d; wParam
0x180006511  xor     edx, edx; Msg
0x180006513  call    cs:__imp_PostThreadMessageW
0x180006519  mov     rcx, rbx
0x18000651c  call    ?GetState@CGhostWindow@@QEBA?AW4GHOSTSTATE@@XZ; CGhostWindow::GetState(void)
0x180006521  xor     ecx, ecx
0x180006523  cmp     eax, 4
0x180006526  setz    cl
0x180006529  mov     eax, ecx
0x18000652b  add     rsp, 20h
0x18000652f  pop     rbx
0x180006530  retn
```
