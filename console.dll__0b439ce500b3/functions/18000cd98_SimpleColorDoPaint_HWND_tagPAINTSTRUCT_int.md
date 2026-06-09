# SimpleColorDoPaint(HWND__ *,tagPAINTSTRUCT &,int)

- ea: `0x18000cd98`
- end: `0x18000ce9a`
- name: `?SimpleColorDoPaint@@YAXPEAUHWND__@@AEAUtagPAINTSTRUCT@@H@Z`
- size: `258`
- prototype: `void __fastcall(HWND, struct tagPAINTSTRUCT *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c440`
- `0x18000ccb0`

## callees

- `0x1800015b0`
- `0x18000cd98`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18000cdc5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18000cdc5`
- `api-ms-win-ntuser-rectangle-l1-1-0!InflateRect` at `0x18000ce52`
- `api-ms-win-ntuser-rectangle-l1-1-0!InflateRect` at `0x18000ce52`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000ce33`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000ce33`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000ce69`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000ce69`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000ce78`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000ce78`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000ce25`
- `ext-ms-win-gdi-internal-desktop-l1-1-0!GetNearestColor` at `0x18000ce25`

## pseudocode

```c
void __fastcall SimpleColorDoPaint(HWND a1, struct tagPAINTSTRUCT *a2, int a3)
{
  char v5; // si
  COLORREF v6; // edx
  COLORREF NearestColor; // eax
  HBRUSH SolidBrush; // rbx
  struct tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF

  Rect = 0;
  v5 = a3;
  GetClientRect(a1, &Rect);
  if ( (unsigned int)(a3 - 405) > 0xF )
  {
    if ( a3 == 609 )
    {
      v6 = g_fakeForegroundColor;
    }
    else if ( a3 == 610 )
    {
      v6 = g_fakeBackgroundColor;
    }
    else
    {
      v6 = 16711935;
      if ( a3 == 613 )
        v6 = g_fakeCursorColor;
    }
  }
  else
  {
    v6 = *((_DWORD *)gpStateInfo + ((v5 - 5) & 0xF) + 28);
  }
  NearestColor = GetNearestColor(a2->hdc, v6);
  SolidBrush = CreateSolidBrush(NearestColor);
  if ( SolidBrush )
  {
    InflateRect(&Rect, -1, -1);
    FillRect(a2->hdc, &Rect, SolidBrush);
    DeleteObject(SolidBrush);
  }
}

```

## disassembly

```asm
0x18000cd98  push    rbx
0x18000cd9a  push    rsi
0x18000cd9b  push    rdi
0x18000cd9c  sub     rsp, 40h
0x18000cda0  mov     rax, cs:__security_cookie
0x18000cda7  xor     rax, rsp
0x18000cdaa  mov     [rsp+58h+var_28], rax
0x18000cdaf  mov     rdi, rdx
0x18000cdb2  xorps   xmm0, xmm0
0x18000cdb5  lea     rdx, [rsp+58h+Rect]; lpRect
0x18000cdba  mov     ebx, r8d
0x18000cdbd  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x18000cdc2  mov     esi, r8d
0x18000cdc5  call    cs:__imp_GetClientRect
0x18000cdcc  nop     dword ptr [rax+rax+00h]
0x18000cdd1  lea     eax, [rbx-195h]
0x18000cdd7  cmp     eax, 0Fh
0x18000cdda  ja      short loc_18000CDF0
0x18000cddc  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000cde3  lea     rcx, [rsi-5]
0x18000cde7  and     ecx, 0Fh
0x18000cdea  mov     edx, [rax+rcx*4+70h]
0x18000cdee  jmp     short loc_18000CE22
0x18000cdf0  cmp     ebx, 261h
0x18000cdf6  jnz     short loc_18000CE00
0x18000cdf8  mov     edx, cs:?g_fakeForegroundColor@@3KA; ulong g_fakeForegroundColor
0x18000cdfe  jmp     short loc_18000CE22
0x18000ce00  cmp     ebx, 262h
0x18000ce06  jnz     short loc_18000CE10
0x18000ce08  mov     edx, cs:?g_fakeBackgroundColor@@3KA; ulong g_fakeBackgroundColor
0x18000ce0e  jmp     short loc_18000CE22
0x18000ce10  cmp     ebx, 265h
0x18000ce16  mov     edx, 0FF00FFh
0x18000ce1b  cmovz   edx, cs:?g_fakeCursorColor@@3KA; color
0x18000ce22  mov     rcx, [rdi]; hdc
0x18000ce25  call    cs:__imp_GetNearestColor
0x18000ce2c  nop     dword ptr [rax+rax+00h]
0x18000ce31  mov     ecx, eax; color
0x18000ce33  call    cs:__imp_CreateSolidBrush
0x18000ce3a  nop     dword ptr [rax+rax+00h]
0x18000ce3f  mov     rbx, rax
0x18000ce42  test    rax, rax
0x18000ce45  jz      short loc_18000CE84
0x18000ce47  or      edx, 0FFFFFFFFh; dx
0x18000ce4a  lea     rcx, [rsp+58h+Rect]; lprc
0x18000ce4f  mov     r8d, edx; dy
0x18000ce52  call    cs:__imp_InflateRect
0x18000ce59  nop     dword ptr [rax+rax+00h]
0x18000ce5e  mov     rcx, [rdi]; hDC
0x18000ce61  lea     rdx, [rsp+58h+Rect]; lprc
0x18000ce66  mov     r8, rbx; hbr
0x18000ce69  call    cs:__imp_FillRect
0x18000ce70  nop     dword ptr [rax+rax+00h]
0x18000ce75  mov     rcx, rbx; ho
0x18000ce78  call    cs:__imp_DeleteObject
0x18000ce7f  nop     dword ptr [rax+rax+00h]
0x18000ce84  mov     rcx, [rsp+58h+var_28]
0x18000ce89  xor     rcx, rsp; StackCookie
0x18000ce8c  call    __security_check_cookie
0x18000ce91  add     rsp, 40h
0x18000ce95  pop     rdi
0x18000ce96  pop     rsi
0x18000ce97  pop     rbx
0x18000ce98  retn
```
