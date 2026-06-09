# CGhostProcess::IsCurrentWerDlgOwnerValid(HWND__ * *)

- ea: `0x1800092fc`
- end: `0x18000937e`
- name: `?IsCurrentWerDlgOwnerValid@CGhostProcess@@AEAAJPEAPEAUHWND__@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this, HWND *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800096f0`
- `0x1800097dc`

## callees

- `0x180006784`
- `0x1800092fc`
- `0x1800094b8`
- `0x180009678`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000935b`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18000935b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009337`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009337`

## pseudocode

```c
__int64 __fastcall CGhostProcess::IsCurrentWerDlgOwnerValid(CGhostProcess *this, HWND *a2)
{
  unsigned int v4; // ebp
  CGhostWindow *v5; // rcx
  HWND GhostHwnd; // rax
  HWND v7; // rdi

  v4 = -2147467259;
  if ( a2 )
    *a2 = 0;
  v5 = (CGhostWindow *)*((_QWORD *)this + 13);
  if ( v5 )
  {
    GhostHwnd = CGhostWindow::GetGhostHwnd(v5);
    v7 = GhostHwnd;
    if ( GhostHwnd && GetWindowThreadProcessId(GhostHwnd, 0) )
    {
      if ( (int)CGhostProcess::SetWerDlgOwnerHwnd(this, v7) >= 0 && a2 )
        *a2 = v7;
      return !IsWindow(v7);
    }
    else
    {
      CGhostProcess::ReleaseCurrentWerDlgOwner(this);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800092fc  push    rbx
0x1800092fe  push    rbp
0x1800092ff  push    rsi
0x180009300  push    rdi
0x180009301  sub     rsp, 28h
0x180009305  mov     rbx, rdx
0x180009308  mov     rsi, rcx
0x18000930b  mov     ebp, 80004005h
0x180009310  test    rdx, rdx
0x180009313  jz      short loc_18000931C
0x180009315  mov     qword ptr [rdx], 0
0x18000931c  mov     rcx, [rcx+68h]; this
0x180009320  test    rcx, rcx
0x180009323  jz      short loc_180009373
0x180009325  call    ?GetGhostHwnd@CGhostWindow@@QEAAPEAUHWND__@@XZ; CGhostWindow::GetGhostHwnd(void)
0x18000932a  mov     rdi, rax
0x18000932d  test    rax, rax
0x180009330  jz      short loc_18000936B
0x180009332  xor     edx, edx; lpdwProcessId
0x180009334  mov     rcx, rax; hWnd
0x180009337  call    cs:__imp_GetWindowThreadProcessId
0x18000933d  test    eax, eax
0x18000933f  jz      short loc_18000936B
0x180009341  mov     rdx, rdi; HWND
0x180009344  mov     rcx, rsi; this
0x180009347  call    ?SetWerDlgOwnerHwnd@CGhostProcess@@AEAAJPEAUHWND__@@@Z; CGhostProcess::SetWerDlgOwnerHwnd(HWND__ *)
0x18000934c  test    eax, eax
0x18000934e  js      short loc_180009358
0x180009350  test    rbx, rbx
0x180009353  jz      short loc_180009358
0x180009355  mov     [rbx], rdi
0x180009358  mov     rcx, rdi; hWnd
0x18000935b  call    cs:__imp_IsWindow
0x180009361  xor     ebp, ebp
0x180009363  test    eax, eax
0x180009365  setz    bpl
0x180009369  jmp     short loc_180009373
0x18000936b  mov     rcx, rsi; this
0x18000936e  call    ?ReleaseCurrentWerDlgOwner@CGhostProcess@@AEAAHXZ; CGhostProcess::ReleaseCurrentWerDlgOwner(void)
0x180009373  mov     eax, ebp
0x180009375  add     rsp, 28h
0x180009379  pop     rdi
0x18000937a  pop     rsi
0x18000937b  pop     rbp
0x18000937c  pop     rbx
0x18000937d  retn
```
