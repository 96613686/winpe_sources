# CGhostProcess::SetErrorReportingHwnd(HWND__ *)

- ea: `0x1800095fc`
- end: `0x18000966f`
- name: `?SetErrorReportingHwnd@CGhostProcess@@QEAAHPEAUHWND__@@@Z`
- size: `115`
- prototype: `int(CGhostProcess *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180007e64`

## callees

- `0x180006784`
- `0x1800095fc`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180009659`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x180009659`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009612`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180009612`

## pseudocode

```c
__int64 __fastcall CGhostProcess::SetErrorReportingHwnd(CGhostProcess *this, HWND a2)
{
  HWND GhostHwnd; // rbx
  CGhostWindow *v5; // rcx

  GhostHwnd = 0;
  if ( GetWindowThreadProcessId(a2, 0) )
  {
    CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
    v5 = (CGhostWindow *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 16) = a2;
    if ( v5 )
      GhostHwnd = CGhostWindow::GetGhostHwnd(v5);
    CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
    if ( GhostHwnd )
      PostMessageW(GhostHwnd, 0x500u, 0, 0);
    LODWORD(GhostHwnd) = 1;
  }
  return (unsigned int)GhostHwnd;
}

```

## disassembly

```asm
0x1800095fc  push    rbx
0x1800095fe  push    rbp
0x1800095ff  push    rsi
0x180009600  push    rdi
0x180009601  sub     rsp, 28h
0x180009605  mov     rbp, rdx
0x180009608  mov     rdi, rcx
0x18000960b  mov     rcx, rbp; hWnd
0x18000960e  xor     edx, edx; lpdwProcessId
0x180009610  xor     ebx, ebx
0x180009612  call    cs:__imp_GetWindowThreadProcessId
0x180009618  test    eax, eax
0x18000961a  jz      short loc_180009664
0x18000961c  lea     rcx, [rdi+10h]; lpCriticalSection
0x180009620  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180009625  mov     rcx, [rdi+68h]; this
0x180009629  mov     [rdi+80h], rbp
0x180009630  test    rcx, rcx
0x180009633  jz      short loc_18000963D
0x180009635  call    ?GetGhostHwnd@CGhostWindow@@QEAAPEAUHWND__@@XZ; CGhostWindow::GetGhostHwnd(void)
0x18000963a  mov     rbx, rax
0x18000963d  lea     rcx, [rdi+10h]; lpCriticalSection
0x180009641  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180009646  test    rbx, rbx
0x180009649  jz      short loc_18000965F
0x18000964b  xor     r9d, r9d; lParam
0x18000964e  xor     r8d, r8d; wParam
0x180009651  mov     edx, 500h; Msg
0x180009656  mov     rcx, rbx; hWnd
0x180009659  call    cs:__imp_PostMessageW
0x18000965f  mov     ebx, 1
0x180009664  mov     eax, ebx
0x180009666  add     rsp, 28h
0x18000966a  pop     rdi
0x18000966b  pop     rsi
0x18000966c  pop     rbp
0x18000966d  pop     rbx
0x18000966e  retn
```
