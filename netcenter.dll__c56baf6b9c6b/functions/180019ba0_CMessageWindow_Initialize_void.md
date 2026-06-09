# CMessageWindow::Initialize(void)

- ea: `0x180019ba0`
- end: `0x180019cf0`
- name: `?Initialize@CMessageWindow@@QEAAJXZ`
- size: `336`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bf2c`

## callees

- `0x180002c2c`
- `0x180014274`
- `0x180019ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c21`
- `USER32!GetClassInfoExW` at `0x180019bd9`
- `USER32!GetClassInfoExW` at `0x180019bd9`
- `USER32!RegisterClassExW` at `0x180019c16`
- `USER32!RegisterClassExW` at `0x180019c16`
- `USER32!CreateWindowExW` at `0x180019c74`
- `USER32!CreateWindowExW` at `0x180019c74`
- `USER32!SetWindowLongPtrW` at `0x180019c8c`
- `USER32!SetWindowLongPtrW` at `0x180019ca1`
- `USER32!SetWindowLongPtrW` at `0x180019c8c`
- `USER32!SetWindowLongPtrW` at `0x180019ca1`
- `USER32!DefWindowProcW` at `0x180019bf6`

## pseudocode

```c
__int64 __fastcall CMessageWindow::Initialize(HWND *dwNewLong)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  HWND Window; // rax
  HWND v5; // rdi
  tagWNDCLASSEXW wcx; // [rsp+60h] [rbp-78h] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  if ( GetClassInfoExW(g_hinst, L"Network Center Message Window", &wcx) )
    goto LABEL_6;
  wcx.hInstance = g_hinst;
  wcx.lpfnWndProc = DefWindowProcW;
  wcx.cbSize = 80;
  wcx.cbWndExtra = 8;
  wcx.lpszClassName = L"Network Center Message Window";
  if ( RegisterClassExW(&wcx) )
    goto LABEL_6;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( (v3 & 0x80000000) == 0 )
  {
LABEL_6:
    Window = CreateWindowExW(0, L"Network Center Message Window", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, g_hinst, 0);
    v5 = Window;
    if ( Window )
    {
      v3 = 0;
      SetWindowLongPtrW(Window, 0, (LONG_PTR)dwNewLong);
      SetWindowLongPtrW(v5, -4, (LONG_PTR)CMessageWindow::s_WndProc);
      *dwNewLong = v5;
    }
    else
    {
      v3 = -2147467259;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180019ba0  push    rbx
0x180019ba2  push    rbp
0x180019ba3  push    rsi
0x180019ba4  push    rdi
0x180019ba5  sub     rsp, 0B8h
0x180019bac  mov     rsi, rcx
0x180019baf  mov     ebx, 50h ; 'P'
0x180019bb4  mov     r8d, ebx; Size
0x180019bb7  lea     rcx, [rsp+0D8h+wcx]; void *
0x180019bbc  xor     edx, edx; Val
0x180019bbe  call    memset_0
0x180019bc3  mov     rcx, cs:g_hinst; hInstance
0x180019bca  lea     rdi, ClassName; "Network Center Message Window"
0x180019bd1  mov     rdx, rdi; lpszClass
0x180019bd4  lea     r8, [rsp+0D8h+wcx]; lpwcx
0x180019bd9  call    cs:__imp_GetClassInfoExW
0x180019bdf  xor     ebp, ebp
0x180019be1  test    eax, eax
0x180019be3  jnz     short loc_180019C3A
0x180019be5  mov     rax, cs:g_hinst
0x180019bec  lea     rcx, [rsp+0D8h+wcx]; WNDCLASSEXW *
0x180019bf1  mov     [rsp+0D8h+wcx.hInstance], rax
0x180019bf6  mov     rax, cs:__imp_DefWindowProcW
0x180019bfd  mov     [rsp+0D8h+wcx.lpfnWndProc], rax
0x180019c02  mov     [rsp+0D8h+wcx.cbSize], ebx
0x180019c06  mov     [rsp+0D8h+wcx.cbWndExtra], 8
0x180019c0e  mov     [rsp+0D8h+wcx.lpszClassName], rdi
0x180019c16  call    cs:__imp_RegisterClassExW
0x180019c1c  test    ax, ax
0x180019c1f  jnz     short loc_180019C3A
0x180019c21  call    cs:__imp_GetLastError
0x180019c27  mov     ebx, eax
0x180019c29  test    eax, eax
0x180019c2b  jle     short loc_180019C36
0x180019c2d  movzx   ebx, ax
0x180019c30  or      ebx, 80070000h
0x180019c36  test    ebx, ebx
0x180019c38  js      short loc_180019CB1
0x180019c3a  mov     rax, cs:g_hinst
0x180019c41  xor     r9d, r9d; dwStyle
0x180019c44  mov     [rsp+0D8h+lpParam], rbp; lpParam
0x180019c49  xor     r8d, r8d; lpWindowName
0x180019c4c  mov     [rsp+0D8h+hInstance], rax; hInstance
0x180019c51  mov     rdx, rdi; lpClassName
0x180019c54  mov     [rsp+0D8h+hMenu], rbp; hMenu
0x180019c59  xor     ecx, ecx; dwExStyle
0x180019c5b  mov     [rsp+0D8h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x180019c64  mov     [rsp+0D8h+nHeight], ebp; nHeight
0x180019c68  mov     [rsp+0D8h+nWidth], ebp; nWidth
0x180019c6c  mov     [rsp+0D8h+Y], ebp; Y
0x180019c70  mov     [rsp+0D8h+X], ebp; X
0x180019c74  call    cs:__imp_CreateWindowExW
0x180019c7a  mov     rdi, rax
0x180019c7d  test    rax, rax
0x180019c80  jz      short loc_180019CAC
0x180019c82  mov     r8, rsi; dwNewLong
0x180019c85  xor     edx, edx; nIndex
0x180019c87  mov     rcx, rax; hWnd
0x180019c8a  mov     ebx, ebp
0x180019c8c  call    cs:__imp_SetWindowLongPtrW
0x180019c92  lea     r8, ?s_WndProc@CMessageWindow@@SA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180019c99  mov     edx, 0FFFFFFFCh; nIndex
0x180019c9e  mov     rcx, rdi; hWnd
0x180019ca1  call    cs:__imp_SetWindowLongPtrW
0x180019ca7  mov     [rsi], rdi
0x180019caa  jmp     short loc_180019CB1
0x180019cac  mov     ebx, 80004005h
0x180019cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cb8  lea     rax, WPP_GLOBAL_Control
0x180019cbf  cmp     rcx, rax
0x180019cc2  jz      short loc_180019CE2
0x180019cc4  test    byte ptr [rcx+1Ch], 8
0x180019cc8  jz      short loc_180019CE2
0x180019cca  mov     rcx, [rcx+10h]
0x180019cce  lea     r8, WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids
0x180019cd5  mov     edx, 0Ah
0x180019cda  mov     r9d, ebx
0x180019cdd  call    WPP_SF_d
0x180019ce2  mov     eax, ebx
0x180019ce4  add     rsp, 0B8h
0x180019ceb  pop     rdi
0x180019cec  pop     rsi
0x180019ced  pop     rbp
0x180019cee  pop     rbx
0x180019cef  retn
```
