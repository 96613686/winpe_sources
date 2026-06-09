# GetTopOwnerHwnd(void)

- ea: `0x1800cb6fc`
- end: `0x1800cb80a`
- name: `?GetTopOwnerHwnd@@YAPEAUHWND__@@XZ`
- size: `270`
- prototype: `HWND(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006ef20`

## callees

- `0x1800cb6fc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800cb70e`
- `KERNEL32!GetCurrentProcessId` at `0x1800cb70e`
- `USER32!GetWindowLongW` at `0x1800cb758`
- `USER32!GetWindowLongW` at `0x1800cb758`
- `USER32!GetWindowThreadProcessId` at `0x1800cb785`
- `USER32!GetWindowThreadProcessId` at `0x1800cb785`
- `USER32!GetWindow` at `0x1800cb738`
- `USER32!GetWindow` at `0x1800cb79f`
- `USER32!GetWindow` at `0x1800cb738`
- `USER32!GetWindow` at `0x1800cb79f`
- `USER32!IsWindowVisible` at `0x1800cb76d`
- `USER32!IsWindowVisible` at `0x1800cb76d`
- `USER32!GetWindowLongPtrW` at `0x1800cb7d9`
- `USER32!GetWindowLongPtrW` at `0x1800cb7d9`
- `USER32!GetDesktopWindow` at `0x1800cb724`
- `USER32!GetDesktopWindow` at `0x1800cb7bd`
- `USER32!GetDesktopWindow` at `0x1800cb7f2`
- `USER32!GetDesktopWindow` at `0x1800cb724`
- `USER32!GetDesktopWindow` at `0x1800cb7bd`
- `USER32!GetDesktopWindow` at `0x1800cb7f2`

## pseudocode

```c
HWND GetTopOwnerHwnd(void)
{
  DWORD CurrentProcessId; // edi
  HWND DesktopWindow; // rax
  HWND Window; // rbx
  HWND i; // rcx
  HWND WindowLongPtrW; // rdi
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF

  dwProcessId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !CurrentProcessId )
    return GetDesktopWindow();
  DesktopWindow = GetDesktopWindow();
  Window = GetWindow(DesktopWindow, 5u);
  if ( !Window )
    return GetDesktopWindow();
  do
  {
    if ( (GetWindowLongW(Window, -16) & 0x40000000) == 0 )
    {
      if ( IsWindowVisible(Window) )
      {
        GetWindowThreadProcessId(Window, &dwProcessId);
        if ( dwProcessId == CurrentProcessId )
          break;
      }
    }
    Window = GetWindow(Window, 2u);
  }
  while ( Window );
  if ( !Window )
    return GetDesktopWindow();
  for ( i = Window; ; i = WindowLongPtrW )
  {
    WindowLongPtrW = (HWND)GetWindowLongPtrW(i, -8);
    if ( !WindowLongPtrW || WindowLongPtrW == GetDesktopWindow() )
      break;
    Window = WindowLongPtrW;
  }
  return Window;
}

```

## disassembly

```asm
0x1800cb6fc  mov     [rsp+arg_8], rbx
0x1800cb701  push    rdi
0x1800cb702  sub     rsp, 20h
0x1800cb706  mov     [rsp+28h+dwProcessId], 0
0x1800cb70e  call    cs:__imp_GetCurrentProcessId
0x1800cb715  nop     dword ptr [rax+rax+00h]
0x1800cb71a  mov     edi, eax
0x1800cb71c  test    eax, eax
0x1800cb71e  jz      loc_1800CB7F2
0x1800cb724  call    cs:__imp_GetDesktopWindow
0x1800cb72b  nop     dword ptr [rax+rax+00h]
0x1800cb730  mov     rcx, rax; hWnd
0x1800cb733  mov     edx, 5; uCmd
0x1800cb738  call    cs:__imp_GetWindow
0x1800cb73f  nop     dword ptr [rax+rax+00h]
0x1800cb744  mov     rbx, rax
0x1800cb747  test    rax, rax
0x1800cb74a  jz      loc_1800CB7F2
0x1800cb750  mov     edx, 0FFFFFFF0h; nIndex
0x1800cb755  mov     rcx, rbx; hWnd
0x1800cb758  call    cs:__imp_GetWindowLongW
0x1800cb75f  nop     dword ptr [rax+rax+00h]
0x1800cb764  bt      eax, 1Eh
0x1800cb768  jb      short loc_1800CB797
0x1800cb76a  mov     rcx, rbx; hWnd
0x1800cb76d  call    cs:__imp_IsWindowVisible
0x1800cb774  nop     dword ptr [rax+rax+00h]
0x1800cb779  test    eax, eax
0x1800cb77b  jz      short loc_1800CB797
0x1800cb77d  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x1800cb782  mov     rcx, rbx; hWnd
0x1800cb785  call    cs:__imp_GetWindowThreadProcessId
0x1800cb78c  nop     dword ptr [rax+rax+00h]
0x1800cb791  cmp     [rsp+28h+dwProcessId], edi
0x1800cb795  jz      short loc_1800CB7B3
0x1800cb797  mov     edx, 2; uCmd
0x1800cb79c  mov     rcx, rbx; hWnd
0x1800cb79f  call    cs:__imp_GetWindow
0x1800cb7a6  nop     dword ptr [rax+rax+00h]
0x1800cb7ab  mov     rbx, rax
0x1800cb7ae  test    rax, rax
0x1800cb7b1  jnz     short loc_1800CB750
0x1800cb7b3  test    rbx, rbx
0x1800cb7b6  jz      short loc_1800CB7F2
0x1800cb7b8  mov     rcx, rbx
0x1800cb7bb  jmp     short loc_1800CB7D4
0x1800cb7bd  call    cs:__imp_GetDesktopWindow
0x1800cb7c4  nop     dword ptr [rax+rax+00h]
0x1800cb7c9  cmp     rdi, rax
0x1800cb7cc  jz      short loc_1800CB7ED
0x1800cb7ce  mov     rbx, rdi
0x1800cb7d1  mov     rcx, rdi; hWnd
0x1800cb7d4  mov     edx, 0FFFFFFF8h; nIndex
0x1800cb7d9  call    cs:__imp_GetWindowLongPtrW
0x1800cb7e0  nop     dword ptr [rax+rax+00h]
0x1800cb7e5  mov     rdi, rax
0x1800cb7e8  test    rax, rax
0x1800cb7eb  jnz     short loc_1800CB7BD
0x1800cb7ed  mov     rax, rbx
0x1800cb7f0  jmp     short loc_1800CB7FE
0x1800cb7f2  call    cs:__imp_GetDesktopWindow
0x1800cb7f9  nop     dword ptr [rax+rax+00h]
0x1800cb7fe  mov     rbx, [rsp+28h+arg_8]
0x1800cb803  add     rsp, 20h
0x1800cb807  pop     rdi
0x1800cb808  retn
```
