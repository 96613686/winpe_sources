# IsSingleServerInstance(void)

- ea: `0x1800741ec`
- end: `0x1800742f3`
- name: `?IsSingleServerInstance@@YAHXZ`
- size: `263`
- prototype: `int __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180075340`

## callees

- `0x180046460`
- `0x1800741ec`

## import_xrefs

- `KERNELBASE!lstrcmpW` at `0x18007428d`
- `KERNELBASE!lstrcmpW` at `0x18007428d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007423b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007423b`
- `USER32!GetWindowThreadProcessId` at `0x180074253`
- `USER32!GetWindowThreadProcessId` at `0x180074253`
- `USER32!GetClassNameW` at `0x180074271`
- `USER32!GetClassNameW` at `0x180074271`
- `USER32!GetWindow` at `0x18007422c`
- `USER32!GetWindow` at `0x1800742a8`
- `USER32!GetWindow` at `0x18007422c`
- `USER32!GetWindow` at `0x1800742a8`
- `USER32!GetDesktopWindow` at `0x18007421a`
- `USER32!GetDesktopWindow` at `0x18007421a`

## pseudocode

```c
__int64 __fastcall IsSingleServerInstance()
{
  unsigned int v0; // ebx
  __int16 v1; // di
  HWND DesktopWindow; // rax
  HWND Window; // rsi
  DWORD CurrentThreadId; // ebp
  wchar_t buf[128]; // [rsp+20h] [rbp-118h] BYREF

  v0 = 0;
  v1 = 0;
  DesktopWindow = GetDesktopWindow();
  Window = GetWindow(DesktopWindow, 5u);
  CurrentThreadId = GetCurrentThreadId();
  if ( !Window )
    return 0;
  do
  {
    if ( CurrentThreadId == GetWindowThreadProcessId(Window, 0)
      && GetClassNameW(Window, buf, 124)
      && !lstrcmpW(buf, L"SrvrWndClass") )
    {
      ++v1;
    }
    Window = GetWindow(Window, 2u);
  }
  while ( Window );
  LOBYTE(v0) = v1 == 1;
  return v0;
}

```

## disassembly

```asm
0x1800741ec  mov     [rsp+arg_0], rbx
0x1800741f1  mov     [rsp+arg_8], rbp
0x1800741f6  mov     [rsp+arg_10], rsi
0x1800741fb  push    rdi
0x1800741fc  sub     rsp, 130h
0x180074203  mov     rax, cs:__security_cookie
0x18007420a  xor     rax, rsp
0x18007420d  mov     [rsp+138h+var_18], rax
0x180074215  xor     ebx, ebx
0x180074217  movzx   edi, bx
0x18007421a  call    cs:__imp_GetDesktopWindow
0x180074221  nop     dword ptr [rax+rax+00h]
0x180074226  mov     rcx, rax; hWnd
0x180074229  lea     edx, [rbx+5]; uCmd
0x18007422c  call    cs:__imp_GetWindow
0x180074233  nop     dword ptr [rax+rax+00h]
0x180074238  mov     rsi, rax
0x18007423b  call    cs:__imp_GetCurrentThreadId
0x180074242  nop     dword ptr [rax+rax+00h]
0x180074247  mov     ebp, eax
0x180074249  test    rsi, rsi
0x18007424c  jz      short loc_1800742C7
0x18007424e  xor     edx, edx; lpdwProcessId
0x180074250  mov     rcx, rsi; hWnd
0x180074253  call    cs:__imp_GetWindowThreadProcessId
0x18007425a  nop     dword ptr [rax+rax+00h]
0x18007425f  cmp     ebp, eax
0x180074261  jnz     short loc_1800742A0
0x180074263  mov     r8d, 7Ch ; '|'; nMaxCount
0x180074269  lea     rdx, [rsp+138h+buf]; lpClassName
0x18007426e  mov     rcx, rsi; hWnd
0x180074271  call    cs:__imp_GetClassNameW
0x180074278  nop     dword ptr [rax+rax+00h]
0x18007427d  test    eax, eax
0x18007427f  jz      short loc_1800742A0
0x180074281  lea     rdx, aSrvrwndclass; "SrvrWndClass"
0x180074288  lea     rcx, [rsp+138h+buf]; lpString1
0x18007428d  call    cs:__imp_lstrcmpW
0x180074294  nop     dword ptr [rax+rax+00h]
0x180074299  test    eax, eax
0x18007429b  jnz     short loc_1800742A0
0x18007429d  inc     di
0x1800742a0  mov     edx, 2; uCmd
0x1800742a5  mov     rcx, rsi; hWnd
0x1800742a8  call    cs:__imp_GetWindow
0x1800742af  nop     dword ptr [rax+rax+00h]
0x1800742b4  mov     rsi, rax
0x1800742b7  test    rax, rax
0x1800742ba  jnz     short loc_18007424E
0x1800742bc  cmp     di, 1
0x1800742c0  setz    bl
0x1800742c3  mov     eax, ebx
0x1800742c5  jmp     short loc_1800742C9
0x1800742c7  xor     eax, eax
0x1800742c9  mov     rcx, [rsp+138h+var_18]
0x1800742d1  xor     rcx, rsp; StackCookie
0x1800742d4  call    __security_check_cookie
0x1800742d9  lea     r11, [rsp+138h+var_8]
0x1800742e1  mov     rbx, [r11+10h]
0x1800742e5  mov     rbp, [r11+18h]
0x1800742e9  mov     rsi, [r11+20h]
0x1800742ed  mov     rsp, r11
0x1800742f0  pop     rdi
0x1800742f1  retn
```
