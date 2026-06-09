# _PaginateControls(HWND__ *,uint,ushort const *,uint *,uint,uint)

- ea: `0x140048024`
- end: `0x1400481ca`
- name: `?_PaginateControls@@YAXPEAUHWND__@@IPEBGPEAIII@Z`
- size: `422`
- prototype: `void __fastcall(HWND, unsigned int nIDDlgItem, LPCWSTR lpchText, unsigned int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400471e4`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x140048024`
- `0x1400481d0`
- `0x1400482b8`
- `0x140113390`

## import_xrefs

- `USER32!DrawTextW` at `0x1400480d5`
- `USER32!DrawTextW` at `0x1400480d5`
- `USER32!GetClientRect` at `0x14004808a`
- `USER32!GetClientRect` at `0x14004808a`
- `USER32!GetDlgItem` at `0x14004806e`
- `USER32!GetDlgItem` at `0x14004806e`
- `USER32!SendMessageW` at `0x1400480a4`
- `USER32!SendMessageW` at `0x1400480a4`
- `GDI32!CreateCompatibleDC` at `0x140048057`
- `GDI32!CreateCompatibleDC` at `0x140048057`
- `GDI32!SelectObject` at `0x1400480b5`
- `GDI32!SelectObject` at `0x1400480ee`
- `GDI32!SelectObject` at `0x1400480b5`
- `GDI32!SelectObject` at `0x1400480ee`
- `GDI32!DeleteObject` at `0x1400480f7`
- `GDI32!DeleteObject` at `0x1400480f7`

## pseudocode

```c
void __fastcall _PaginateControls(HWND a1, int nIDDlgItem, LPCWSTR lpchText, unsigned int *a4, unsigned int a5)
{
  HDC CompatibleDC; // rdi
  HWND DlgItem; // rax
  HWND v11; // rbx
  HGDIOBJ v12; // rsi
  int v13; // ebp
  void *v14; // rax
  int v15; // ebx
  int v16; // edx
  PVOID *v17; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v19; // eax
  int v20; // ebx
  unsigned int v21; // edx
  int v22; // r8d
  struct tagRECT Rect; // [rsp+30h] [rbp-58h] BYREF

  Rect = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    DlgItem = GetDlgItem(a1, nIDDlgItem);
    v11 = DlgItem;
    if ( DlgItem )
    {
      v12 = 0;
      GetClientRect(DlgItem, &Rect);
      v13 = Rect.bottom - Rect.top;
      v14 = (void *)SendMessageW(v11, 0x31u, 0, 0);
      if ( v14 )
        v12 = SelectObject(CompatibleDC, v14);
      DrawTextW(CompatibleDC, lpchText, -1, &Rect, 0x410u);
      v15 = Rect.bottom - Rect.top;
      if ( v12 )
        SelectObject(CompatibleDC, v12);
      DeleteObject(CompatibleDC);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
            CurrentThreadActivityIdPrefix,
            v15);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 5u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b2859179a69931166002029bec6a3d1f_Traceguids, v19, v13);
        }
      }
      if ( v15 <= v13 )
      {
        v20 = v15 - v13;
        _RepositionControls(a1, v16, v20, a4, a5);
        _ResizeComponent(a1, v21, v22, v20);
      }
    }
  }
}

```

## disassembly

```asm
0x140048024  push    rbx
0x140048026  push    rbp
0x140048027  push    rsi
0x140048028  push    rdi
0x140048029  push    r12
0x14004802b  push    r14
0x14004802d  push    r15
0x14004802f  sub     rsp, 50h
0x140048033  mov     rax, cs:__security_cookie
0x14004803a  xor     rax, rsp
0x14004803d  mov     [rsp+88h+var_48], rax
0x140048042  mov     r14, rcx
0x140048045  xorps   xmm0, xmm0
0x140048048  xor     ecx, ecx; hdc
0x14004804a  mov     r12, r9
0x14004804d  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x140048052  mov     r15, r8
0x140048055  mov     ebx, edx
0x140048057  call    cs:__imp_CreateCompatibleDC
0x14004805d  mov     rdi, rax
0x140048060  test    rax, rax
0x140048063  jz      loc_1400481AE
0x140048069  mov     edx, ebx; nIDDlgItem
0x14004806b  mov     rcx, r14; hDlg
0x14004806e  call    cs:__imp_GetDlgItem
0x140048074  mov     rbx, rax
0x140048077  test    rax, rax
0x14004807a  jz      loc_1400481AE
0x140048080  lea     rdx, [rsp+88h+Rect]; lpRect
0x140048085  mov     rcx, rax; hWnd
0x140048088  xor     esi, esi
0x14004808a  call    cs:__imp_GetClientRect
0x140048090  mov     ebp, [rsp+88h+Rect.bottom]
0x140048094  lea     edx, [rsi+31h]; Msg
0x140048097  sub     ebp, [rsp+88h+Rect.top]
0x14004809b  xor     r9d, r9d; lParam
0x14004809e  xor     r8d, r8d; wParam
0x1400480a1  mov     rcx, rbx; hWnd
0x1400480a4  call    cs:__imp_SendMessageW
0x1400480aa  test    rax, rax
0x1400480ad  jz      short loc_1400480BE
0x1400480af  mov     rdx, rax; h
0x1400480b2  mov     rcx, rdi; hdc
0x1400480b5  call    cs:__imp_SelectObject
0x1400480bb  mov     rsi, rax
0x1400480be  lea     r9, [rsp+88h+Rect]; lprc
0x1400480c3  mov     [rsp+88h+format], 410h; format
0x1400480cb  or      r8d, 0FFFFFFFFh; cchText
0x1400480cf  mov     rdx, r15; lpchText
0x1400480d2  mov     rcx, rdi; hdc
0x1400480d5  call    cs:__imp_DrawTextW
0x1400480db  mov     ebx, [rsp+88h+Rect.bottom]
0x1400480df  sub     ebx, [rsp+88h+Rect.top]
0x1400480e3  test    rsi, rsi
0x1400480e6  jz      short loc_1400480F4
0x1400480e8  mov     rdx, rsi; h
0x1400480eb  mov     rcx, rdi; hdc
0x1400480ee  call    cs:__imp_SelectObject
0x1400480f4  mov     rcx, rdi; ho
0x1400480f7  call    cs:__imp_DeleteObject
0x1400480fd  mov     rax, cs:WPP_GLOBAL_Control
0x140048104  lea     rdi, WPP_GLOBAL_Control
0x14004810b  cmp     rax, rdi
0x14004810e  jz      short loc_140048184
0x140048110  test    byte ptr [rax+1Ch], 1
0x140048114  jz      short loc_14004814B
0x140048116  cmp     byte ptr [rax+19h], 5
0x14004811a  jb      short loc_14004814B
0x14004811c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048121  mov     rcx, cs:WPP_GLOBAL_Control
0x140048128  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x14004812f  mov     edx, 0Fh
0x140048134  mov     [rsp+88h+format], ebx
0x140048138  mov     r9d, eax
0x14004813b  mov     rcx, [rcx+10h]
0x14004813f  call    WPP_SF_Dd
0x140048144  mov     rax, cs:WPP_GLOBAL_Control
0x14004814b  cmp     rax, rdi
0x14004814e  jz      short loc_140048184
0x140048150  test    byte ptr [rax+1Ch], 1
0x140048154  jz      short loc_140048184
0x140048156  cmp     byte ptr [rax+19h], 5
0x14004815a  jb      short loc_140048184
0x14004815c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048161  mov     rcx, cs:WPP_GLOBAL_Control
0x140048168  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x14004816f  mov     edx, 10h
0x140048174  mov     [rsp+88h+format], ebp
0x140048178  mov     r9d, eax
0x14004817b  mov     rcx, [rcx+10h]
0x14004817f  call    WPP_SF_Dd
0x140048184  cmp     ebx, ebp
0x140048186  jg      short loc_1400481AE
0x140048188  mov     eax, [rsp+88h+arg_20]
0x14004818f  sub     ebx, ebp
0x140048191  mov     r8d, ebx; int
0x140048194  mov     [rsp+88h+format], eax; int
0x140048198  mov     r9, r12; unsigned int *
0x14004819b  mov     rcx, r14; hWndTo
0x14004819e  call    ?_RepositionControls@@YAXPEAUHWND__@@HHPEAIH@Z; _RepositionControls(HWND__ *,int,int,uint *,int)
0x1400481a3  mov     r9d, ebx; int
0x1400481a6  mov     rcx, r14; HWND
0x1400481a9  call    ?_ResizeComponent@@YAHPEAUHWND__@@IHH@Z; _ResizeComponent(HWND__ *,uint,int,int)
0x1400481ae  mov     rcx, [rsp+88h+var_48]
0x1400481b3  xor     rcx, rsp; StackCookie
0x1400481b6  call    __security_check_cookie
0x1400481bb  add     rsp, 50h
0x1400481bf  pop     r15
0x1400481c1  pop     r14
0x1400481c3  pop     r12
0x1400481c5  pop     rdi
0x1400481c6  pop     rsi
0x1400481c7  pop     rbp
0x1400481c8  pop     rbx
0x1400481c9  retn
```
