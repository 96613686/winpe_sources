# SetWindowMetrics(HWND__ *,unsigned __int64,__int64)

- ea: `0x10051f4c4`
- end: `0x10051f5ac`
- name: `?SetWindowMetrics@@YAXPEAUHWND__@@_K_J@Z`
- size: `232`
- prototype: `void __fastcall(HWND hWnd, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1005143c0`

## callees

- `0x10051d0b8`
- `0x10051f4c4`
- `0x100548210`
- `0x1005494b8`

## import_xrefs

- `USER32!GetParent` at `0x10051f529`
- `USER32!GetParent` at `0x10051f529`
- `USER32!GetWindowLongPtrW` at `0x10051f515`
- `USER32!GetWindowLongPtrW` at `0x10051f515`
- `USER32!GetWindowRect` at `0x10051f549`
- `USER32!GetWindowRect` at `0x10051f549`
- `USER32!MoveWindow` at `0x10051f582`
- `USER32!MoveWindow` at `0x10051f582`

## pseudocode

```c
void __fastcall SetWindowMetrics(HWND hWnd, __int64 a2, const wchar_t *a3)
{
  __int64 v4; // rbx
  int CaptionHeight; // edi
  HWND Parent; // rax
  HWND v7; // rsi
  struct tagRECT Rect; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 == 42 )
  {
    if ( a3 )
    {
      if ( !wcscmp_0(a3, L"WindowMetrics") )
      {
        v4 = *(_QWORD *)(GetWindowLongPtrW(hWnd, -21) + 48);
        CaptionHeight = GetCaptionHeight();
        Parent = GetParent(hWnd);
        v7 = Parent;
        if ( v4 )
        {
          if ( Parent && *(_DWORD *)(v4 + 96) < CaptionHeight && GetWindowRect(Parent, &Rect) )
          {
            _mm_lfence();
            if ( MoveWindow(
                   v7,
                   Rect.left,
                   Rect.top,
                   Rect.right - Rect.left,
                   CaptionHeight + Rect.bottom - *(_DWORD *)(v4 + 96) - Rect.top,
                   1) )
            {
              *(_DWORD *)(v4 + 96) = CaptionHeight;
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x10051f4c4  cmp     rdx, 2Ah ; '*'
0x10051f4c8  jnz     locret_10051F5AB
0x10051f4ce  mov     [rsp+arg_8], rbx
0x10051f4d3  mov     [rsp+arg_10], rsi
0x10051f4d8  push    rdi
0x10051f4d9  sub     rsp, 50h
0x10051f4dd  mov     rax, cs:__security_cookie
0x10051f4e4  xor     rax, rsp
0x10051f4e7  mov     [rsp+58h+var_18], rax
0x10051f4ec  mov     rsi, rcx
0x10051f4ef  test    r8, r8
0x10051f4f2  jz      loc_10051F58F
0x10051f4f8  lea     rdx, aWindowmetrics; "WindowMetrics"
0x10051f4ff  mov     rcx, r8; String1
0x10051f502  call    wcscmp_0
0x10051f507  test    eax, eax
0x10051f509  jnz     loc_10051F58F
0x10051f50f  lea     edx, [rax-15h]; nIndex
0x10051f512  mov     rcx, rsi; hWnd
0x10051f515  call    cs:__imp_GetWindowLongPtrW
0x10051f51b  mov     rbx, [rax+30h]
0x10051f51f  call    ?GetCaptionHeight@@YAHXZ; GetCaptionHeight(void)
0x10051f524  mov     rcx, rsi; hWnd
0x10051f527  mov     edi, eax
0x10051f529  call    cs:__imp_GetParent
0x10051f52f  mov     rsi, rax
0x10051f532  test    rbx, rbx
0x10051f535  jz      short loc_10051F58F
0x10051f537  test    rax, rax
0x10051f53a  jz      short loc_10051F58F
0x10051f53c  cmp     [rbx+60h], edi
0x10051f53f  jge     short loc_10051F58F
0x10051f541  lea     rdx, [rsp+58h+Rect]; lpRect
0x10051f546  mov     rcx, rax; hWnd
0x10051f549  call    cs:__imp_GetWindowRect
0x10051f54f  test    eax, eax
0x10051f551  jz      short loc_10051F58F
0x10051f553  lfence
0x10051f556  mov     eax, [rsp+58h+Rect.bottom]
0x10051f55a  mov     rcx, rsi; hWnd
0x10051f55d  sub     eax, [rbx+60h]
0x10051f560  mov     r8d, [rsp+58h+Rect.top]; Y
0x10051f565  sub     eax, r8d
0x10051f568  mov     r9d, [rsp+58h+Rect.right]
0x10051f56d  add     eax, edi
0x10051f56f  mov     edx, [rsp+58h+Rect.left]; X
0x10051f573  sub     r9d, edx; nWidth
0x10051f576  mov     [rsp+58h+bRepaint], 1; bRepaint
0x10051f57e  mov     [rsp+58h+nHeight], eax; nHeight
0x10051f582  call    cs:__imp_MoveWindow
0x10051f588  test    eax, eax
0x10051f58a  jz      short loc_10051F58F
0x10051f58c  mov     [rbx+60h], edi
0x10051f58f  mov     rcx, [rsp+58h+var_18]
0x10051f594  xor     rcx, rsp; StackCookie
0x10051f597  call    __security_check_cookie
0x10051f59c  mov     rbx, [rsp+58h+arg_8]
0x10051f5a1  mov     rsi, [rsp+58h+arg_10]
0x10051f5a6  add     rsp, 50h
0x10051f5aa  pop     rdi
0x10051f5ab  retn
```
