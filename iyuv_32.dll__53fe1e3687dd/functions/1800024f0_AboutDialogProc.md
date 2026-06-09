# AboutDialogProc

- ea: `0x1800024f0`
- end: `0x180002685`
- name: `AboutDialogProc`
- size: `405`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001400`
- `0x180001c7e`
- `0x1800024f0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180002649`
- `GDI32!DeleteDC` at `0x180002649`
- `GDI32!CreateCompatibleDC` at `0x1800025c8`
- `GDI32!CreateCompatibleDC` at `0x1800025c8`
- `GDI32!SelectObject` at `0x1800025dc`
- `GDI32!SelectObject` at `0x180002640`
- `GDI32!SelectObject` at `0x1800025dc`
- `GDI32!SelectObject` at `0x180002640`
- `GDI32!BitBlt` at `0x180002634`
- `GDI32!BitBlt` at `0x180002634`
- `GDI32!GetObjectW` at `0x1800025bf`
- `GDI32!GetObjectW` at `0x1800025bf`
- `USER32!BeginPaint` at `0x180002580`
- `USER32!BeginPaint` at `0x180002580`
- `USER32!LoadBitmapW` at `0x1800025a1`
- `USER32!LoadBitmapW` at `0x1800025a1`
- `USER32!GetWindowLongPtrW` at `0x180002591`
- `USER32!GetWindowLongPtrW` at `0x180002591`
- `USER32!GetWindowRect` at `0x1800025ec`
- `USER32!GetWindowRect` at `0x1800025ec`
- `USER32!EndPaint` at `0x180002656`
- `USER32!EndPaint` at `0x180002656`
- `USER32!EndDialog` at `0x180002544`
- `USER32!EndDialog` at `0x180002544`

## pseudocode

```c
INT_PTR __fastcall AboutDialogProc(HWND a1, int a2, __int64 a3)
{
  int v4; // edx
  int v5; // edx
  HDC v7; // r14
  HINSTANCE WindowLongPtrW; // rax
  HBITMAP BitmapW; // rax
  HBITMAP v10; // rbx
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  HGDIOBJ v13; // rbx
  struct tagRECT pv[2]; // [rsp+50h] [rbp-49h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-29h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+80h] [rbp-19h] BYREF

  v4 = a2 - 15;
  if ( !v4 )
  {
    memset(pv, 0, sizeof(pv));
    memset_0(&Paint, 0, sizeof(Paint));
    Rect = 0;
    v7 = BeginPaint(a1, &Paint);
    WindowLongPtrW = (HINSTANCE)GetWindowLongPtrW(a1, -6);
    BitmapW = LoadBitmapW(WindowLongPtrW, L"INDEOLOGO");
    v10 = BitmapW;
    if ( BitmapW )
    {
      GetObjectW(BitmapW, 32, pv);
      CompatibleDC = CreateCompatibleDC(v7);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        v13 = SelectObject(CompatibleDC, v10);
        GetWindowRect(a1, &Rect);
        BitBlt(v7, (Rect.right - pv[0].top - Rect.left) / 2 - 4, 11, pv[0].top, pv[0].right, hdcSrc, 0, 0, 0xCC0020u);
        SelectObject(hdcSrc, v13);
        DeleteDC(hdcSrc);
      }
    }
    EndPaint(a1, &Paint);
    return 1;
  }
  v5 = v4 - 257;
  if ( !v5 )
    return 1;
  if ( v5 != 1 || (unsigned __int64)(a3 - 1) > 1 )
    return 0;
  EndDialog(a1, 1);
  return 1;
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp-8+arg_8], rbx
0x1800024f5  mov     [rsp-8+arg_10], rsi
0x1800024fa  push    rbp
0x1800024fb  push    rdi
0x1800024fc  push    r14
0x1800024fe  lea     rbp, [rsp-47h]
0x180002503  sub     rsp, 0E0h
0x18000250a  mov     rax, cs:__security_cookie
0x180002511  xor     rax, rsp
0x180002514  mov     [rbp+57h+var_20], rax
0x180002518  mov     rdi, rcx
0x18000251b  sub     edx, 0Fh
0x18000251e  jz      short loc_180002558
0x180002520  sub     edx, 101h
0x180002526  jz      loc_18000265C
0x18000252c  cmp     edx, 1
0x18000252f  jnz     short loc_180002551
0x180002531  sub     r8, 1
0x180002535  jz      short loc_18000253D
0x180002537  cmp     r8, 1
0x18000253b  jnz     short loc_180002551
0x18000253d  mov     ebx, 1
0x180002542  mov     edx, ebx; nResult
0x180002544  call    cs:__imp_EndDialog
0x18000254a  mov     eax, ebx
0x18000254c  jmp     loc_180002661
0x180002551  xor     eax, eax
0x180002553  jmp     loc_180002661
0x180002558  xorps   xmm0, xmm0
0x18000255b  lea     rcx, [rbp+57h+Paint]; void *
0x18000255f  xor     edx, edx; Val
0x180002561  movups  [rbp+57h+pv], xmm0
0x180002565  movups  [rbp+57h+var_90], xmm0
0x180002569  lea     r8d, [rdx+48h]; Size
0x18000256d  call    memset_0
0x180002572  xorps   xmm0, xmm0
0x180002575  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180002579  mov     rcx, rdi; hWnd
0x18000257c  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180002580  call    cs:__imp_BeginPaint
0x180002586  mov     edx, 0FFFFFFFAh; nIndex
0x18000258b  mov     rcx, rdi; hWnd
0x18000258e  mov     r14, rax
0x180002591  call    cs:__imp_GetWindowLongPtrW
0x180002597  mov     rcx, rax; hInstance
0x18000259a  lea     rdx, BitmapName; "INDEOLOGO"
0x1800025a1  call    cs:__imp_LoadBitmapW
0x1800025a7  mov     rbx, rax
0x1800025aa  test    rax, rax
0x1800025ad  jz      loc_18000264F
0x1800025b3  lea     r8, [rbp+57h+pv]; pv
0x1800025b7  mov     edx, 20h ; ' '; c
0x1800025bc  mov     rcx, rax; h
0x1800025bf  call    cs:__imp_GetObjectW
0x1800025c5  mov     rcx, r14; hdc
0x1800025c8  call    cs:__imp_CreateCompatibleDC
0x1800025ce  mov     rsi, rax
0x1800025d1  test    rax, rax
0x1800025d4  jz      short loc_18000264F
0x1800025d6  mov     rdx, rbx; h
0x1800025d9  mov     rcx, rax; hdc
0x1800025dc  call    cs:__imp_SelectObject
0x1800025e2  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800025e6  mov     rcx, rdi; hWnd
0x1800025e9  mov     rbx, rax
0x1800025ec  call    cs:__imp_GetWindowRect
0x1800025f2  mov     eax, [rbp+57h+Rect.right]
0x1800025f5  mov     r8d, 0Bh; y
0x1800025fb  mov     ecx, dword ptr [rbp+57h+pv+8]
0x1800025fe  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x180002602  sub     eax, r9d
0x180002605  sub     eax, [rbp+57h+Rect.left]
0x180002608  cdq
0x180002609  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x180002611  sub     eax, edx
0x180002613  mov     [rsp+0F0h+y1], 0; y1
0x18000261b  sar     eax, 1
0x18000261d  mov     [rsp+0F0h+x1], 0; x1
0x180002625  mov     [rsp+0F0h+hdcSrc], rsi; hdcSrc
0x18000262a  mov     [rsp+0F0h+cy], ecx; cy
0x18000262e  mov     rcx, r14; hdc
0x180002631  lea     edx, [rax-4]; x
0x180002634  call    cs:__imp_BitBlt
0x18000263a  mov     rdx, rbx; h
0x18000263d  mov     rcx, rsi; hdc
0x180002640  call    cs:__imp_SelectObject
0x180002646  mov     rcx, rsi; hdc
0x180002649  call    cs:__imp_DeleteDC
0x18000264f  lea     rdx, [rbp+57h+Paint]; lpPaint
0x180002653  mov     rcx, rdi; hWnd
0x180002656  call    cs:__imp_EndPaint
0x18000265c  mov     eax, 1
0x180002661  mov     rcx, [rbp+57h+var_20]
0x180002665  xor     rcx, rsp; StackCookie
0x180002668  call    __security_check_cookie
0x18000266d  lea     r11, [rsp+0F0h+var_10]
0x180002675  mov     rbx, [r11+28h]
0x180002679  mov     rsi, [r11+30h]
0x18000267d  mov     rsp, r11
0x180002680  pop     r14
0x180002682  pop     rdi
0x180002683  pop     rbp
0x180002684  retn
```
