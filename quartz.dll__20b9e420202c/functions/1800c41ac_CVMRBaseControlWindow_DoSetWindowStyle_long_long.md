# CVMRBaseControlWindow::DoSetWindowStyle(long,long)

- ea: `0x1800c41ac`
- end: `0x1800c4371`
- name: `?DoSetWindowStyle@CVMRBaseControlWindow@@QEAAJJJ@Z`
- size: `453`
- prototype: `int(CVMRBaseControlWindow *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800c74c0`
- `0x1800c7530`
- `0x180148ee0`
- `0x180148f30`

## callees

- `0x1800388a0`
- `0x1800c41ac`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800c4253`
- `USER32!GetSystemMetrics` at `0x1800c4263`
- `USER32!GetSystemMetrics` at `0x1800c4253`
- `USER32!GetSystemMetrics` at `0x1800c4263`
- `USER32!IsWindowVisible` at `0x1800c41db`
- `USER32!IsWindowVisible` at `0x1800c41db`
- `USER32!GetWindowRect` at `0x1800c41f2`
- `USER32!GetWindowRect` at `0x1800c41f2`
- `USER32!MapWindowPoints` at `0x1800c4315`
- `USER32!MapWindowPoints` at `0x1800c4315`
- `USER32!GetParent` at `0x1800c42e4`
- `USER32!GetParent` at `0x1800c42f9`
- `USER32!GetParent` at `0x1800c42e4`
- `USER32!GetParent` at `0x1800c42f9`
- `USER32!SetWindowLongW` at `0x1800c4207`
- `USER32!SetWindowLongW` at `0x1800c4207`
- `USER32!MoveWindow` at `0x1800c4292`
- `USER32!MoveWindow` at `0x1800c4345`
- `USER32!MoveWindow` at `0x1800c4292`
- `USER32!MoveWindow` at `0x1800c4345`
- `USER32!ShowWindow` at `0x1800c42d4`
- `USER32!ShowWindow` at `0x1800c42d4`
- `USER32!SetWindowPos` at `0x1800c4240`
- `USER32!SetWindowPos` at `0x1800c42c2`
- `USER32!SetWindowPos` at `0x1800c4240`
- `USER32!SetWindowPos` at `0x1800c42c2`

## pseudocode

```c
__int64 __fastcall CVMRBaseControlWindow::DoSetWindowStyle(CVMRBaseControlWindow *this, LONG a2, int a3)
{
  HWND v4; // rcx
  BOOL v7; // ebx
  int SystemMetrics; // ebx
  int v9; // eax
  HWND Parent; // rax
  struct tagRECT Rect; // [rsp+40h] [rbp-38h] BYREF

  v4 = (HWND)*((_QWORD *)this + 7);
  Rect = 0;
  v7 = IsWindowVisible(v4);
  GetWindowRect(*((HWND *)this + 7), &Rect);
  SetWindowLongW(*((HWND *)this + 7), a3, a2);
  if ( v7 )
  {
    SetWindowPos(*((HWND *)this + 7), 0, 0, 0, 0, 0, 0x77u);
  }
  else
  {
    SystemMetrics = GetSystemMetrics(1);
    v9 = GetSystemMetrics(0);
    MoveWindow(*((HWND *)this + 7), v9, SystemMetrics, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
    SetWindowPos(*((HWND *)this + 7), 0, 0, 0, 0, 0, 0x77u);
    ShowWindow(*((HWND *)this + 7), 0);
    if ( GetParent(*((HWND *)this + 7)) )
    {
      Parent = GetParent(*((HWND *)this + 7));
      MapWindowPoints(0, Parent, (LPPOINT)&Rect, 2u);
    }
    MoveWindow(*((HWND *)this + 7), Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c41ac  mov     [rsp+arg_18], rbx
0x1800c41b1  push    rbp
0x1800c41b2  push    rsi
0x1800c41b3  push    rdi
0x1800c41b4  sub     rsp, 60h
0x1800c41b8  mov     rax, cs:__security_cookie
0x1800c41bf  xor     rax, rsp
0x1800c41c2  mov     [rsp+78h+var_28], rax
0x1800c41c7  mov     rbp, rcx
0x1800c41ca  xorps   xmm0, xmm0
0x1800c41cd  mov     rcx, [rcx+38h]; hWnd
0x1800c41d1  mov     esi, r8d
0x1800c41d4  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x1800c41d9  mov     edi, edx
0x1800c41db  call    cs:__imp_IsWindowVisible
0x1800c41e2  nop     dword ptr [rax+rax+00h]
0x1800c41e7  mov     rcx, [rbp+38h]; hWnd
0x1800c41eb  lea     rdx, [rsp+78h+Rect]; lpRect
0x1800c41f0  mov     ebx, eax
0x1800c41f2  call    cs:__imp_GetWindowRect
0x1800c41f9  nop     dword ptr [rax+rax+00h]
0x1800c41fe  mov     rcx, [rbp+38h]; hWnd
0x1800c4202  mov     r8d, edi; dwNewLong
0x1800c4205  mov     edx, esi; nIndex
0x1800c4207  call    cs:__imp_SetWindowLongW
0x1800c420e  nop     dword ptr [rax+rax+00h]
0x1800c4213  mov     edi, 1
0x1800c4218  cmp     ebx, edi
0x1800c421a  jnz     short loc_1800C4251
0x1800c421c  mov     rcx, [rbp+38h]; hWnd
0x1800c4220  xor     r9d, r9d; Y
0x1800c4223  mov     [rsp+78h+uFlags], 77h ; 'w'; uFlags
0x1800c422b  xor     r8d, r8d; X
0x1800c422e  mov     [rsp+78h+cy], 0; cy
0x1800c4236  xor     edx, edx; hWndInsertAfter
0x1800c4238  mov     [rsp+78h+nHeight], 0; cx
0x1800c4240  call    cs:__imp_SetWindowPos
0x1800c4247  nop     dword ptr [rax+rax+00h]
0x1800c424c  jmp     loc_1800C4351
0x1800c4251  mov     ecx, edi; nIndex
0x1800c4253  call    cs:__imp_GetSystemMetrics
0x1800c425a  nop     dword ptr [rax+rax+00h]
0x1800c425f  xor     ecx, ecx; nIndex
0x1800c4261  mov     ebx, eax
0x1800c4263  call    cs:__imp_GetSystemMetrics
0x1800c426a  nop     dword ptr [rax+rax+00h]
0x1800c426f  mov     ecx, [rsp+78h+Rect.bottom]
0x1800c4273  mov     r8d, ebx; Y
0x1800c4276  sub     ecx, [rsp+78h+Rect.top]
0x1800c427a  mov     edx, eax; X
0x1800c427c  mov     r9d, [rsp+78h+Rect.right]
0x1800c4281  sub     r9d, [rsp+78h+Rect.left]; nWidth
0x1800c4286  mov     [rsp+78h+cy], edi; bRepaint
0x1800c428a  mov     [rsp+78h+nHeight], ecx; nHeight
0x1800c428e  mov     rcx, [rbp+38h]; hWnd
0x1800c4292  call    cs:__imp_MoveWindow
0x1800c4299  nop     dword ptr [rax+rax+00h]
0x1800c429e  mov     rcx, [rbp+38h]; hWnd
0x1800c42a2  xor     r9d, r9d; Y
0x1800c42a5  mov     [rsp+78h+uFlags], 77h ; 'w'; uFlags
0x1800c42ad  xor     r8d, r8d; X
0x1800c42b0  mov     [rsp+78h+cy], 0; cy
0x1800c42b8  xor     edx, edx; hWndInsertAfter
0x1800c42ba  mov     [rsp+78h+nHeight], 0; cx
0x1800c42c2  call    cs:__imp_SetWindowPos
0x1800c42c9  nop     dword ptr [rax+rax+00h]
0x1800c42ce  mov     rcx, [rbp+38h]; hWnd
0x1800c42d2  xor     edx, edx; nCmdShow
0x1800c42d4  call    cs:__imp_ShowWindow
0x1800c42db  nop     dword ptr [rax+rax+00h]
0x1800c42e0  mov     rcx, [rbp+38h]; hWnd
0x1800c42e4  call    cs:__imp_GetParent
0x1800c42eb  nop     dword ptr [rax+rax+00h]
0x1800c42f0  test    rax, rax
0x1800c42f3  jz      short loc_1800C4321
0x1800c42f5  mov     rcx, [rbp+38h]; hWnd
0x1800c42f9  call    cs:__imp_GetParent
0x1800c4300  nop     dword ptr [rax+rax+00h]
0x1800c4305  mov     r9d, 2; cPoints
0x1800c430b  lea     r8, [rsp+78h+Rect]; lpPoints
0x1800c4310  mov     rdx, rax; hWndTo
0x1800c4313  xor     ecx, ecx; hWndFrom
0x1800c4315  call    cs:__imp_MapWindowPoints
0x1800c431c  nop     dword ptr [rax+rax+00h]
0x1800c4321  mov     eax, [rsp+78h+Rect.bottom]
0x1800c4325  mov     r8d, [rsp+78h+Rect.top]; Y
0x1800c432a  sub     eax, r8d
0x1800c432d  mov     r9d, [rsp+78h+Rect.right]
0x1800c4332  mov     edx, [rsp+78h+Rect.left]; X
0x1800c4336  sub     r9d, edx; nWidth
0x1800c4339  mov     rcx, [rbp+38h]; hWnd
0x1800c433d  mov     [rsp+78h+cy], edi; bRepaint
0x1800c4341  mov     [rsp+78h+nHeight], eax; nHeight
0x1800c4345  call    cs:__imp_MoveWindow
0x1800c434c  nop     dword ptr [rax+rax+00h]
0x1800c4351  xor     eax, eax
0x1800c4353  mov     rcx, [rsp+78h+var_28]
0x1800c4358  xor     rcx, rsp; StackCookie
0x1800c435b  call    __security_check_cookie
0x1800c4360  mov     rbx, [rsp+78h+arg_18]
0x1800c4368  add     rsp, 60h
0x1800c436c  pop     rdi
0x1800c436d  pop     rsi
0x1800c436e  pop     rbp
0x1800c436f  retn
```
