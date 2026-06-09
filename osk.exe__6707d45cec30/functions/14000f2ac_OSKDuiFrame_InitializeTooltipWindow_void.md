# OSKDuiFrame::InitializeTooltipWindow(void)

- ea: `0x14000f2ac`
- end: `0x14000f390`
- name: `?InitializeTooltipWindow@OSKDuiFrame@@AEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(OSKDuiFrame *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f098`

## callees

- `0x14000f2ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f36e`
- `KERNEL32!GetLastError` at `0x14000f36e`
- `USER32!SetWindowPos` at `0x14000f34d`
- `USER32!SetWindowPos` at `0x14000f34d`
- `USER32!CreateWindowExW` at `0x14000f31c`
- `USER32!CreateWindowExW` at `0x14000f31c`
- `USER32!SendMessageW` at `0x14000f366`
- `USER32!SendMessageW` at `0x14000f366`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x14000f2b9`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x14000f2b9`

## pseudocode

```c
__int64 __fastcall OSKDuiFrame::InitializeTooltipWindow(HWND *this)
{
  bool IsRTL; // al
  HWND Window; // rax
  unsigned int v4; // ebx
  signed int LastError; // eax

  IsRTL = DirectUI::Element::IsRTL((DirectUI::Element *)this);
  Window = CreateWindowExW(
             ((unsigned __int8)IsRTL << 22) + 8,
             L"tooltips_class32",
             0,
             0x80000003,
             0,
             0,
             0,
             0,
             0,
             0,
             0,
             0);
  this[26] = Window;
  if ( Window )
  {
    v4 = 0;
    SetWindowPos(Window, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x13u);
    SendMessageW(this[26], 0x403u, 3u, 0);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x14000f2ac  mov     [rsp+arg_0], rbx
0x14000f2b1  push    rdi
0x14000f2b2  sub     rsp, 60h
0x14000f2b6  mov     rdi, rcx
0x14000f2b9  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x14000f2bf  mov     [rsp+68h+lpParam], 0; lpParam
0x14000f2c8  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x14000f2cf  mov     [rsp+68h+hInstance], 0; hInstance
0x14000f2d8  mov     r9d, 80000003h; dwStyle
0x14000f2de  mov     [rsp+68h+hMenu], 0; hMenu
0x14000f2e7  xor     r8d, r8d; lpWindowName
0x14000f2ea  mov     [rsp+68h+hWndParent], 0; hWndParent
0x14000f2f3  mov     [rsp+68h+nHeight], 0; nHeight
0x14000f2fb  movzx   ecx, al
0x14000f2fe  shl     ecx, 16h
0x14000f301  mov     [rsp+68h+nWidth], 0; nWidth
0x14000f309  add     ecx, 8; dwExStyle
0x14000f30c  mov     [rsp+68h+Y], 0; Y
0x14000f314  mov     [rsp+68h+X], 0; X
0x14000f31c  call    cs:__imp_CreateWindowExW
0x14000f322  mov     [rdi+0D0h], rax
0x14000f329  test    rax, rax
0x14000f32c  jz      short loc_14000F36E
0x14000f32e  xor     ebx, ebx
0x14000f330  mov     [rsp+68h+nWidth], 13h; uFlags
0x14000f338  mov     [rsp+68h+Y], ebx; cy
0x14000f33c  xor     r9d, r9d; Y
0x14000f33f  xor     r8d, r8d; X
0x14000f342  mov     [rsp+68h+X], ebx; cx
0x14000f346  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x14000f34a  mov     rcx, rax; hWnd
0x14000f34d  call    cs:__imp_SetWindowPos
0x14000f353  mov     rcx, [rdi+0D0h]; hWnd
0x14000f35a  lea     r8d, [rbx+3]; wParam
0x14000f35e  xor     r9d, r9d; lParam
0x14000f361  mov     edx, 403h; Msg
0x14000f366  call    cs:__imp_SendMessageW
0x14000f36c  jmp     short loc_14000F383
0x14000f36e  call    cs:__imp_GetLastError
0x14000f374  mov     ebx, eax
0x14000f376  test    eax, eax
0x14000f378  jle     short loc_14000F383
0x14000f37a  movzx   ebx, ax
0x14000f37d  or      ebx, 80070000h
0x14000f383  mov     eax, ebx
0x14000f385  mov     rbx, [rsp+68h+arg_0]
0x14000f38a  add     rsp, 60h
0x14000f38e  pop     rdi
0x14000f38f  retn
```
