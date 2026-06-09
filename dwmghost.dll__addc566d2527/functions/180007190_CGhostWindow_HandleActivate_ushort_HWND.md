# CGhostWindow::HandleActivate(ushort,HWND__ *)

- ea: `0x180007190`
- end: `0x18000726c`
- name: `?HandleActivate@CGhostWindow@@MEAAHGPEAUHWND__@@@Z`
- size: `220`
- prototype: `__int64 __fastcall(CGhostWindow *__hidden this, unsigned __int16, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x1800060e0`
- `0x180007190`
- `0x1800075e0`
- `0x180009190`
- `0x180009944`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-4!HungWindowFromGhostWindow` at `0x180007216`
- `ext-ms-win-ntuser-window-l1-1-4!HungWindowFromGhostWindow` at `0x180007216`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180007229`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180007229`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1800071f3`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x1800071f3`

## pseudocode

```c
__int64 __fastcall CGhostWindow::HandleActivate(LPARAM *this, unsigned __int16 a2, HWND a3)
{
  HWND v5; // rbx
  HWND v6; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    if ( (unsigned int)a2 - 1 <= 1 )
    {
      CGhostWindow::AddWarningText((CGhostWindow *)this);
      if ( !(unsigned int)CGhostWindow::ShowErrorReportingDlg(this) )
        CGhostProcess::FrostSiblings(this[2]);
    }
  }
  else if ( !a3 || (v5 = (HWND)this[6], GetWindow(a3, 4u) != v5) )
  {
    if ( !*(_DWORD *)(this[2] + 136) )
    {
      dwProcessId = 0;
      v6 = (HWND)HungWindowFromGhostWindow(a3);
      if ( (!v6 || !GetWindowThreadProcessId(v6, &dwProcessId) || dwProcessId != *(_DWORD *)(this[2] + 56))
        && !(unsigned int)CGhostWindow::ShowErrorReportingDlg(this) )
      {
        CGhostProcess::UnfrostSiblings((CGhostProcess *)this[2]);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180007190  mov     [rsp+arg_0], rbx
0x180007195  mov     [rsp+arg_10], rsi
0x18000719a  push    rdi
0x18000719b  sub     rsp, 20h
0x18000719f  mov     rdi, rcx
0x1800071a2  mov     rsi, r8
0x1800071a5  movzx   ecx, dx
0x1800071a8  test    ecx, ecx
0x1800071aa  jz      short loc_1800071E2
0x1800071ac  sub     ecx, 1
0x1800071af  jz      short loc_1800071BA
0x1800071b1  cmp     ecx, 1
0x1800071b4  jnz     loc_180007257
0x1800071ba  mov     rcx, rdi; this
0x1800071bd  call    ?AddWarningText@CGhostWindow@@AEAAHXZ; CGhostWindow::AddWarningText(void)
0x1800071c2  mov     edx, 1
0x1800071c7  mov     rcx, rdi
0x1800071ca  call    ?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z; CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)
0x1800071cf  test    eax, eax
0x1800071d1  jnz     loc_180007257
0x1800071d7  mov     rcx, [rdi+10h]; lParam
0x1800071db  call    ?FrostSiblings@CGhostProcess@@QEAAHXZ; CGhostProcess::FrostSiblings(void)
0x1800071e0  jmp     short loc_180007257
0x1800071e2  test    rsi, rsi
0x1800071e5  jz      short loc_1800071FE
0x1800071e7  mov     rbx, [rdi+30h]
0x1800071eb  mov     edx, 4; uCmd
0x1800071f0  mov     rcx, rsi; hWnd
0x1800071f3  call    cs:__imp_GetWindow
0x1800071f9  cmp     rax, rbx
0x1800071fc  jz      short loc_180007257
0x1800071fe  mov     rax, [rdi+10h]
0x180007202  cmp     dword ptr [rax+88h], 0
0x180007209  jnz     short loc_180007257
0x18000720b  mov     rcx, rsi
0x18000720e  mov     [rsp+28h+dwProcessId], 0
0x180007216  call    cs:__imp_HungWindowFromGhostWindow
0x18000721c  test    rax, rax
0x18000721f  jz      short loc_180007240
0x180007221  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180007226  mov     rcx, rax; hWnd
0x180007229  call    cs:__imp_GetWindowThreadProcessId
0x18000722f  test    eax, eax
0x180007231  jz      short loc_180007240
0x180007233  mov     rax, [rdi+10h]
0x180007237  mov     ecx, [rax+38h]
0x18000723a  cmp     [rsp+28h+dwProcessId], ecx
0x18000723e  jz      short loc_180007257
0x180007240  xor     edx, edx
0x180007242  mov     rcx, rdi
0x180007245  call    ?ShowErrorReportingDlg@CGhostWindow@@IEAAJW4WERDLGSHOW@@@Z; CGhostWindow::ShowErrorReportingDlg(WERDLGSHOW)
0x18000724a  test    eax, eax
0x18000724c  jnz     short loc_180007257
0x18000724e  mov     rcx, [rdi+10h]; this
0x180007252  call    ?UnfrostSiblings@CGhostProcess@@QEAAHXZ; CGhostProcess::UnfrostSiblings(void)
0x180007257  mov     rbx, [rsp+28h+arg_0]
0x18000725c  mov     eax, 1
0x180007261  mov     rsi, [rsp+28h+arg_10]
0x180007266  add     rsp, 20h
0x18000726a  pop     rdi
0x18000726b  retn
```
