# I_CreateStubWindow(void)

- ea: `0x18000fe24`
- end: `0x18000ff27`
- name: `?I_CreateStubWindow@@YAPEAUHWND__@@XZ`
- size: `259`
- prototype: `HWND(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ff30`

## callees

- `0x18000fe24`
- `0x18001aa9a`

## import_xrefs

- `USER32!LoadCursorW` at `0x18000fe99`
- `USER32!LoadCursorW` at `0x18000fe99`
- `USER32!RegisterClassW` at `0x18000febb`
- `USER32!RegisterClassW` at `0x18000febb`
- `USER32!GetClassInfoW` at `0x18000fe5f`
- `USER32!GetClassInfoW` at `0x18000fe5f`
- `USER32!CreateWindowExW` at `0x18000ff0c`
- `USER32!CreateWindowExW` at `0x18000ff0c`
- `GDI32!GetStockObject` at `0x18000fea5`
- `GDI32!GetStockObject` at `0x18000fea5`

## pseudocode

```c
HWND I_CreateStubWindow(void)
{
  HBRUSH StockObject; // rax
  tagWNDCLASSW WndClass; // [rsp+60h] [rbp+7h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( GetClassInfoW(g_hInstance, L"JobPropWnd", &WndClass) )
    return CreateWindowExW(0x80u, L"JobPropWnd", &WindowName, 0, 0x80000000, 0x80000000, 0, 0, 0, 0, g_hInstance, 0);
  WndClass.style = 0;
  WndClass.lpfnWndProc = (WNDPROC)StubWndProc;
  WndClass.hInstance = g_hInstance;
  WndClass.cbClsExtra = 0;
  WndClass.cbWndExtra = 16;
  WndClass.hIcon = 0;
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  StockObject = (HBRUSH)GetStockObject(0);
  WndClass.lpszMenuName = 0;
  WndClass.hbrBackground = StockObject;
  WndClass.lpszClassName = L"JobPropWnd";
  if ( RegisterClassW(&WndClass) )
    return CreateWindowExW(0x80u, L"JobPropWnd", &WindowName, 0, 0x80000000, 0x80000000, 0, 0, 0, 0, g_hInstance, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x18000fe24  mov     [rsp-8+arg_0], rbx
0x18000fe29  mov     [rsp-8+arg_8], rdi
0x18000fe2e  push    rbp
0x18000fe2f  lea     rbp, [rsp-57h]
0x18000fe34  sub     rsp, 0B0h
0x18000fe3b  xor     edx, edx; Val
0x18000fe3d  lea     rcx, [rbp+57h+WndClass]; void *
0x18000fe41  lea     r8d, [rdx+48h]; Size
0x18000fe45  call    memset_0
0x18000fe4a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000fe51  lea     rdi, ClassName; "JobPropWnd"
0x18000fe58  mov     rdx, rdi; lpClassName
0x18000fe5b  lea     r8, [rbp+57h+WndClass]; lpWndClass
0x18000fe5f  call    cs:__imp_GetClassInfoW
0x18000fe65  xor     ebx, ebx
0x18000fe67  test    eax, eax
0x18000fe69  jnz     short loc_18000FECA
0x18000fe6b  lea     rax, ?StubWndProc@@YA_JPEAUHWND__@@I_K_J@Z; StubWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000fe72  mov     [rbp+57h+WndClass.style], ebx
0x18000fe75  mov     [rbp+57h+WndClass.lpfnWndProc], rax
0x18000fe79  mov     edx, 7F00h; lpCursorName
0x18000fe7e  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000fe85  xor     ecx, ecx; hInstance
0x18000fe87  mov     [rbp+57h+WndClass.hInstance], rax
0x18000fe8b  mov     [rbp+57h+WndClass.cbClsExtra], ebx
0x18000fe8e  mov     [rbp+57h+WndClass.cbWndExtra], 10h
0x18000fe95  mov     [rbp+57h+WndClass.hIcon], rbx
0x18000fe99  call    cs:__imp_LoadCursorW
0x18000fe9f  xor     ecx, ecx; i
0x18000fea1  mov     [rbp+57h+WndClass.hCursor], rax
0x18000fea5  call    cs:__imp_GetStockObject
0x18000feab  lea     rcx, [rbp+57h+WndClass]; lpWndClass
0x18000feaf  mov     [rbp+57h+WndClass.lpszMenuName], rbx
0x18000feb3  mov     [rbp+57h+WndClass.hbrBackground], rax
0x18000feb7  mov     [rbp+57h+WndClass.lpszClassName], rdi
0x18000febb  call    cs:__imp_RegisterClassW
0x18000fec1  test    ax, ax
0x18000fec4  jnz     short loc_18000FECA
0x18000fec6  xor     eax, eax
0x18000fec8  jmp     short loc_18000FF12
0x18000feca  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000fed1  lea     r8, WindowName; lpWindowName
0x18000fed8  mov     [rsp+0B0h+lpParam], rbx; lpParam
0x18000fedd  xor     r9d, r9d; dwStyle
0x18000fee0  mov     [rsp+0B0h+hInstance], rax; hInstance
0x18000fee5  mov     rdx, rdi; lpClassName
0x18000fee8  mov     [rsp+0B0h+hMenu], rbx; hMenu
0x18000feed  mov     eax, 80000000h
0x18000fef2  mov     [rsp+0B0h+hWndParent], rbx; hWndParent
0x18000fef7  mov     ecx, 80h; dwExStyle
0x18000fefc  mov     [rsp+0B0h+nHeight], ebx; nHeight
0x18000ff00  mov     [rsp+0B0h+nWidth], ebx; nWidth
0x18000ff04  mov     [rsp+0B0h+Y], eax; Y
0x18000ff08  mov     [rsp+0B0h+X], eax; X
0x18000ff0c  call    cs:__imp_CreateWindowExW
0x18000ff12  lea     r11, [rsp+0B0h+var_s0]
0x18000ff1a  mov     rbx, [r11+10h]
0x18000ff1e  mov     rdi, [r11+18h]
0x18000ff22  mov     rsp, r11
0x18000ff25  pop     rbp
0x18000ff26  retn
```
