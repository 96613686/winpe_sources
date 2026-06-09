# CMapiPreviewer::CreateTooltip(HWND__ *)

- ea: `0x180022e14`
- end: `0x180022fad`
- name: `?CreateTooltip@CMapiPreviewer@@AEAAJPEAUHWND__@@@Z`
- size: `409`
- prototype: `int(CMapiPreviewer *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023020`

## callees

- `0x18000557c`
- `0x180006270`
- `0x180022e14`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180022ec2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180022ec2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180022f65`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180022f65`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022f4d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022f9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022f4d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022f9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180022e80`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180022e80`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::CreateTooltip(CMapiPreviewer *this, HWND hWndParent)
{
  int Error; // ebx
  HWND Window; // rdi
  LPARAM lParam[10]; // [rsp+60h] [rbp-78h] BYREF

  Error = 0;
  Window = CreateWindowExW(
             8u,
             L"tooltips_class32",
             0,
             0x80000002,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             off_180053498,
             0);
  if ( Window || (Error = ResultFromLastError(), Error >= 0) )
  {
    if ( !SetWindowPos(Window, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u) )
      Error = ResultFromLastError();
    if ( Error >= 0 )
    {
      lParam[5] = (LPARAM)off_180053498;
      lParam[3] = 0;
      lParam[4] = 0;
      lParam[0] = 0x1100000048LL;
      lParam[1] = (LPARAM)hWndParent;
      lParam[2] = (LPARAM)hWndParent;
      memset(&lParam[6], 0, 24);
      if ( SendMessageW(Window, 0x432u, 0, (LPARAM)lParam) )
      {
        SendMessageW(Window, 0x401u, 0, 0);
        *((_QWORD *)this + 23) = Window;
        return (unsigned int)Error;
      }
      Error = -2147467259;
    }
    if ( Window )
      DestroyWindow(Window);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180022e14  mov     [rsp+arg_10], rbx
0x180022e19  push    rbp
0x180022e1a  push    rsi
0x180022e1b  push    rdi
0x180022e1c  sub     rsp, 0C0h
0x180022e23  mov     rax, cs:__security_cookie
0x180022e2a  xor     rax, rsp
0x180022e2d  mov     [rsp+0D8h+var_28], rax
0x180022e35  mov     rax, cs:off_180053498
0x180022e3c  xor     ebx, ebx
0x180022e3e  mov     [rsp+0D8h+lpParam], rbx; lpParam
0x180022e43  mov     rsi, rdx
0x180022e46  mov     [rsp+0D8h+hInstance], rax; hInstance
0x180022e4b  mov     rbp, rcx
0x180022e4e  mov     [rsp+0D8h+hMenu], rbx; hMenu
0x180022e53  mov     eax, 80000000h
0x180022e58  mov     [rsp+0D8h+hWndParent], rdx; hWndParent
0x180022e5d  lea     ecx, [rbx+8]; dwExStyle
0x180022e60  mov     [rsp+0D8h+nHeight], eax; nHeight
0x180022e64  lea     rdx, ClassName; "tooltips_class32"
0x180022e6b  mov     [rsp+0D8h+nWidth], eax; nWidth
0x180022e6f  mov     r9d, 80000002h; dwStyle
0x180022e75  mov     [rsp+0D8h+Y], eax; Y
0x180022e79  xor     r8d, r8d; lpWindowName
0x180022e7c  mov     [rsp+0D8h+X], eax; X
0x180022e80  call    cs:__imp_CreateWindowExW
0x180022e86  mov     rdi, rax
0x180022e89  test    rax, rax
0x180022e8c  jnz     short loc_180022E9D
0x180022e8e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022e93  mov     ebx, eax
0x180022e95  test    eax, eax
0x180022e97  js      loc_180022F6B
0x180022e9d  mov     [rsp+0D8h+nWidth], 13h; uFlags
0x180022ea5  xor     r9d, r9d; Y
0x180022ea8  mov     [rsp+0D8h+Y], 0; cy
0x180022eb0  xor     r8d, r8d; X
0x180022eb3  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180022eb7  mov     [rsp+0D8h+X], 0; cx
0x180022ebf  mov     rcx, rdi; hWnd
0x180022ec2  call    cs:__imp_SetWindowPos
0x180022ec8  test    eax, eax
0x180022eca  jnz     short loc_180022ED3
0x180022ecc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022ed1  mov     ebx, eax
0x180022ed3  test    ebx, ebx
0x180022ed5  js      loc_180022F5D
0x180022edb  mov     rax, cs:off_180053498
0x180022ee2  lea     r9, [rsp+0D8h+lParam]; lParam
0x180022ee7  xor     r8d, r8d; wParam
0x180022eea  mov     [rsp+0D8h+var_50], rax
0x180022ef2  mov     edx, 432h; Msg
0x180022ef7  mov     [rsp+0D8h+var_60], 0
0x180022f00  mov     rcx, rdi; hWnd
0x180022f03  mov     [rsp+0D8h+var_58], 0
0x180022f0f  mov     [rsp+0D8h+var_40], 0
0x180022f1b  mov     [rsp+0D8h+var_38], 0
0x180022f27  mov     dword ptr [rsp+0D8h+lParam], 48h ; 'H'
0x180022f2f  mov     dword ptr [rsp+0D8h+lParam+4], 11h
0x180022f37  mov     [rsp+0D8h+var_70], rsi
0x180022f3c  mov     [rsp+0D8h+var_68], rsi
0x180022f41  mov     [rsp+0D8h+var_48], 0
0x180022f4d  call    cs:__imp_SendMessageW
0x180022f53  test    rax, rax
0x180022f56  jnz     short loc_180022F90
0x180022f58  mov     ebx, 80004005h
0x180022f5d  test    rdi, rdi
0x180022f60  jz      short loc_180022F6B
0x180022f62  mov     rcx, rdi; hWnd
0x180022f65  call    cs:__imp_DestroyWindow
0x180022f6b  mov     eax, ebx
0x180022f6d  mov     rcx, [rsp+0D8h+var_28]
0x180022f75  xor     rcx, rsp; StackCookie
0x180022f78  call    __security_check_cookie
0x180022f7d  mov     rbx, [rsp+0D8h+arg_10]
0x180022f85  add     rsp, 0C0h
0x180022f8c  pop     rdi
0x180022f8d  pop     rsi
0x180022f8e  pop     rbp
0x180022f8f  retn
0x180022f90  xor     r9d, r9d; lParam
0x180022f93  xor     r8d, r8d; wParam
0x180022f96  mov     edx, 401h; Msg
0x180022f9b  mov     rcx, rdi; hWnd
0x180022f9e  call    cs:__imp_SendMessageW
0x180022fa4  mov     [rbp+0B8h], rdi
0x180022fab  jmp     short loc_180022F6B
```
