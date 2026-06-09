# CTray::SavePosEnumProc(HWND__ *,__int64)

- ea: `0x1400622f0`
- end: `0x140062512`
- name: `?SavePosEnumProc@CTray@@KAHPEAUHWND__@@_J@Z`
- size: `546`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140024058`
- `0x1400622f0`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x14006231f`
- `api-ms-win-rtcore-ntuser-private-l1-1-0!GetWindowBand` at `0x14006231f`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x14006247a`
- `api-ms-win-ntuser-rectangle-l1-1-0!IntersectRect` at `0x14006247a`
- `GDI32!DeleteObject` at `0x1400624ea`
- `GDI32!DeleteObject` at `0x1400624ea`
- `GDI32!CreateRectRgn` at `0x14006242c`
- `GDI32!CreateRectRgn` at `0x14006242c`
- `GDI32!SetRectRgn` at `0x140062495`
- `GDI32!SetRectRgn` at `0x140062495`
- `GDI32!OffsetRgn` at `0x140062466`
- `GDI32!OffsetRgn` at `0x140062466`
- `GDI32!CombineRgn` at `0x1400624ab`
- `GDI32!CombineRgn` at `0x1400624e1`
- `GDI32!CombineRgn` at `0x1400624ab`
- `GDI32!CombineRgn` at `0x1400624e1`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x140062451`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x140062451`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140062337`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindowVisible` at `0x140062337`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x140062441`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x140062441`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x1400624c5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x1400624c5`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x1400623a0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-1!GetWindowPlacement` at `0x1400623a0`

## pseudocode

```c
__int64 __fastcall CTray::SavePosEnumProc(HWND a1, __int64 a2)
{
  void (__fastcall *v5)(__int64, __int64, __int128 *); // rax
  __int64 v6; // rbx
  HRGN RectRgn; // rsi
  int v8; // [rsp+30h] [rbp-19h] BYREF
  __int128 v9; // [rsp+38h] [rbp-11h] BYREF
  __int128 wndpl_4; // [rsp+48h] [rbp-1h]
  __int128 wndpl_20; // [rsp+58h] [rbp+Fh]
  __int64 wndpl_36; // [rsp+68h] [rbp+1Fh]
  struct tagRECT Rect; // [rsp+70h] [rbp+27h] BYREF

  v8 = 0;
  if ( (unsigned int)GetWindowBand(a1, &v8)
    && ((unsigned int)(v8 - 1) <= 1 || v8 == 16)
    && IsWindowVisible(a1)
    && (!*(_QWORD *)(a2 + 16) || v8 == 1)
    && a1 != *(HWND *)a2
    && a1 != v_hwndDesktop )
  {
    v9 = 0;
    HIDWORD(v9) = 44;
    wndpl_4 = 0;
    wndpl_36 = 0;
    wndpl_20 = 0;
    GetWindowPlacement(a1, (WINDOWPLACEMENT *)((char *)&v9 + 12));
    if ( DWORD1(wndpl_4) != 2 )
    {
      if ( *(_QWORD *)(a2 + 16) && v8 == 1 )
      {
        *(_QWORD *)&v9 = a1;
        Rect = 0;
        RectRgn = CreateRectRgn(0, 0, 0, 0);
        if ( RectRgn )
        {
          if ( GetWindowRect(a1, &Rect) )
          {
            if ( (unsigned int)GetWindowRgn(a1, RectRgn) <= 1 )
            {
              IntersectRect(&Rect, &Rect, *(const RECT **)(a2 + 24));
              SetRectRgn(RectRgn, Rect.left, Rect.top, Rect.right, Rect.bottom);
            }
            else
            {
              OffsetRgn(RectRgn, Rect.left, Rect.top);
            }
          }
          if ( CombineRgn(RectRgn, RectRgn, *(HRGN *)(a2 + 16), 4) != 1 )
          {
            DWORD2(v9) = 1;
            if ( (GetWindowLongW(a1, -20) & 0x80000) == 0 )
              CombineRgn(*(HRGN *)(a2 + 16), *(HRGN *)(a2 + 16), RectRgn, 2);
          }
          DeleteObject(RectRgn);
        }
      }
      else
      {
        *(_QWORD *)&v9 = a1;
        DWORD2(v9) = 1;
      }
      v5 = (void (__fastcall *)(__int64, __int64, __int128 *))qword_140252980;
      v6 = *(_QWORD *)(a2 + 8);
      if ( qword_140252980 == -1 )
      {
        GetProcFromComCtl32(&qword_140252980, 324);
        v5 = (void (__fastcall *)(__int64, __int64, __int128 *))qword_140252980;
      }
      if ( v5 )
        v5(v6, 0x7FFFFFFF, &v9);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400622f0  push    rbp
0x1400622f2  push    rbx
0x1400622f3  push    rdi
0x1400622f4  lea     rbp, [rsp-47h]
0x1400622f9  sub     rsp, 90h
0x140062300  mov     rax, cs:__security_cookie
0x140062307  xor     rax, rsp
0x14006230a  mov     [rbp+57h+var_20], rax
0x14006230e  mov     rdi, rdx
0x140062311  mov     [rbp+57h+var_70], 0
0x140062318  lea     rdx, [rbp+57h+var_70]
0x14006231c  mov     rbx, rcx
0x14006231f  call    cs:__imp_GetWindowBand
0x140062325  test    eax, eax
0x140062327  jz      short loc_140062341
0x140062329  mov     ecx, [rbp+57h+var_70]
0x14006232c  lea     eax, [rcx-1]
0x14006232f  cmp     eax, 1
0x140062332  ja      short loc_14006235D
0x140062334  mov     rcx, rbx; hWnd
0x140062337  call    cs:__imp_IsWindowVisible
0x14006233d  test    eax, eax
0x14006233f  jnz     short loc_140062364
0x140062341  mov     eax, 1
0x140062346  mov     rcx, [rbp+57h+var_20]
0x14006234a  xor     rcx, rsp; StackCookie
0x14006234d  call    __security_check_cookie
0x140062352  add     rsp, 90h
0x140062359  pop     rdi
0x14006235a  pop     rbx
0x14006235b  pop     rbp
0x14006235c  retn
0x14006235d  cmp     ecx, 10h
0x140062360  jnz     short loc_140062341
0x140062362  jmp     short loc_140062334
0x140062364  cmp     qword ptr [rdi+10h], 0
0x140062369  jnz     loc_140062402
0x14006236f  cmp     rbx, [rdi]
0x140062372  jz      short loc_140062341
0x140062374  cmp     rbx, cs:?v_hwndDesktop@@3PEAUHWND__@@EA; HWND__ * v_hwndDesktop
0x14006237b  jz      short loc_140062341
0x14006237d  xorps   xmm0, xmm0
0x140062380  lea     rdx, [rbp+57h+wndpl]; lpwndpl
0x140062384  xor     eax, eax
0x140062386  mov     rcx, rbx; hWnd
0x140062389  movups  xmmword ptr [rbp-11h], xmm0
0x14006238d  mov     [rbp+57h+wndpl.length], 2Ch ; ','
0x140062394  movups  xmmword ptr [rbp+57h+wndpl.flags], xmm0
0x140062398  mov     qword ptr [rbp+57h+wndpl.rcNormalPosition.right], rax
0x14006239c  movups  xmmword ptr [rbp+57h+wndpl.ptMaxPosition.x], xmm0
0x1400623a0  call    cs:__imp_GetWindowPlacement
0x1400623a6  cmp     [rbp+57h+wndpl.showCmd], 2
0x1400623aa  jz      short loc_140062341
0x1400623ac  cmp     qword ptr [rdi+10h], 0
0x1400623b1  mov     [rsp+0A0h+arg_10], rsi
0x1400623b9  jnz     short loc_140062411
0x1400623bb  mov     [rbp+57h+var_68], rbx
0x1400623bf  mov     [rbp+57h+var_60], 1
0x1400623c6  mov     rax, cs:qword_140252980
0x1400623cd  mov     rbx, [rdi+8]
0x1400623d1  mov     rsi, [rsp+0A0h+arg_10]
0x1400623d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400623dd  jz      loc_1400624F5
0x1400623e3  test    rax, rax
0x1400623e6  jz      loc_140062341
0x1400623ec  lea     r8, [rbp+57h+var_68]
0x1400623f0  mov     edx, 7FFFFFFFh
0x1400623f5  mov     rcx, rbx
0x1400623f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400623fd  jmp     loc_140062341
0x140062402  cmp     [rbp+57h+var_70], 1
0x140062406  jz      loc_14006236F
0x14006240c  jmp     loc_140062341
0x140062411  cmp     [rbp+57h+var_70], 1
0x140062415  jnz     short loc_1400623BB
0x140062417  xorps   xmm0, xmm0
0x14006241a  mov     [rbp+57h+var_68], rbx
0x14006241e  xor     r9d, r9d; y2
0x140062421  xor     r8d, r8d; x2
0x140062424  xor     edx, edx; y1
0x140062426  xor     ecx, ecx; x1
0x140062428  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x14006242c  call    cs:__imp_CreateRectRgn
0x140062432  mov     rsi, rax
0x140062435  test    rax, rax
0x140062438  jz      short loc_1400623C6
0x14006243a  lea     rdx, [rbp+57h+Rect]; lpRect
0x14006243e  mov     rcx, rbx; hWnd
0x140062441  call    cs:__imp_GetWindowRect
0x140062447  test    eax, eax
0x140062449  jz      short loc_14006249B
0x14006244b  mov     rdx, rsi; hRgn
0x14006244e  mov     rcx, rbx; hWnd
0x140062451  call    cs:__imp_GetWindowRgn
0x140062457  cmp     eax, 1
0x14006245a  jbe     short loc_14006246E
0x14006245c  mov     r8d, [rbp+57h+Rect.top]; y
0x140062460  mov     rcx, rsi; hrgn
0x140062463  mov     edx, [rbp+57h+Rect.left]; x
0x140062466  call    cs:__imp_OffsetRgn
0x14006246c  jmp     short loc_14006249B
0x14006246e  mov     r8, [rdi+18h]; lprcSrc2
0x140062472  lea     rdx, [rbp+57h+Rect]; lprcSrc1
0x140062476  lea     rcx, [rbp+57h+Rect]; lprcDst
0x14006247a  call    cs:__imp_IntersectRect
0x140062480  mov     eax, [rbp+57h+Rect.bottom]
0x140062483  mov     rcx, rsi; hrgn
0x140062486  mov     r9d, [rbp+57h+Rect.right]; right
0x14006248a  mov     r8d, [rbp+57h+Rect.top]; top
0x14006248e  mov     edx, [rbp+57h+Rect.left]; left
0x140062491  mov     [rsp+0A0h+bottom], eax; bottom
0x140062495  call    cs:__imp_SetRectRgn
0x14006249b  mov     r8, [rdi+10h]; hrgnSrc2
0x14006249f  mov     r9d, 4; iMode
0x1400624a5  mov     rdx, rsi; hrgnSrc1
0x1400624a8  mov     rcx, rsi; hrgnDst
0x1400624ab  call    cs:__imp_CombineRgn
0x1400624b1  cmp     eax, 1
0x1400624b4  jz      short loc_1400624E7
0x1400624b6  mov     edx, 0FFFFFFECh; nIndex
0x1400624bb  mov     [rbp+57h+var_60], 1
0x1400624c2  mov     rcx, rbx; hWnd
0x1400624c5  call    cs:__imp_GetWindowLongW
0x1400624cb  bt      eax, 13h
0x1400624cf  jb      short loc_1400624E7
0x1400624d1  mov     rcx, [rdi+10h]; hrgnDst
0x1400624d5  mov     r9d, 2; iMode
0x1400624db  mov     rdx, rcx; hrgnSrc1
0x1400624de  mov     r8, rsi; hrgnSrc2
0x1400624e1  call    cs:__imp_CombineRgn
0x1400624e7  mov     rcx, rsi; ho
0x1400624ea  call    cs:__imp_DeleteObject
0x1400624f0  jmp     loc_1400623C6
0x1400624f5  mov     edx, 144h
0x1400624fa  lea     rcx, qword_140252980
0x140062501  call    _GetProcFromComCtl32
0x140062506  mov     rax, cs:qword_140252980
0x14006250d  jmp     loc_1400623E3
```
