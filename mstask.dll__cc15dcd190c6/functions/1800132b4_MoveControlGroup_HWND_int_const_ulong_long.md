# MoveControlGroup(HWND__ *,int * const,ulong,long)

- ea: `0x1800132b4`
- end: `0x18001337d`
- name: `?MoveControlGroup@@YAXPEAUHWND__@@QEAHKJ@Z`
- size: `201`
- prototype: `void __fastcall(HWND hWndTo, int *const, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015570`

## callees

- `0x1800132b4`
- `0x18001aac0`

## import_xrefs

- `USER32!GetDlgItem` at `0x1800132f1`
- `USER32!GetDlgItem` at `0x1800132f1`
- `USER32!SetWindowPos` at `0x180013350`
- `USER32!SetWindowPos` at `0x180013350`
- `USER32!GetWindowRect` at `0x18001330a`
- `USER32!GetWindowRect` at `0x18001330a`
- `USER32!MapWindowPoints` at `0x180013320`
- `USER32!MapWindowPoints` at `0x180013320`

## pseudocode

```c
void __fastcall MoveControlGroup(HWND hWndTo, int *const a2, unsigned int a3, int a4)
{
  __int64 v8; // rsi
  HWND DlgItem; // rbx
  struct tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  if ( a3 )
  {
    v8 = 0;
    do
    {
      DlgItem = GetDlgItem(hWndTo, a2[v8]);
      Rect = 0;
      GetWindowRect(DlgItem, &Rect);
      MapWindowPoints(0, hWndTo, (LPPOINT)&Rect, 2u);
      SetWindowPos(DlgItem, 0, Rect.left - a4, Rect.top, 0, 0, 0x71Du);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < a3 );
  }
}

```

## disassembly

```asm
0x1800132b4  test    r8d, r8d
0x1800132b7  jz      locret_18001337C
0x1800132bd  mov     [rsp+arg_10], rbx
0x1800132c2  push    rbp
0x1800132c3  push    rsi
0x1800132c4  push    rdi
0x1800132c5  push    r14
0x1800132c7  push    r15
0x1800132c9  sub     rsp, 60h
0x1800132cd  mov     rax, cs:__security_cookie
0x1800132d4  xor     rax, rsp
0x1800132d7  mov     [rsp+88h+var_38], rax
0x1800132dc  mov     r15d, r9d
0x1800132df  mov     edi, r8d
0x1800132e2  mov     r14, rdx
0x1800132e5  mov     rbp, rcx
0x1800132e8  xor     esi, esi
0x1800132ea  mov     edx, [r14+rsi*4]; nIDDlgItem
0x1800132ee  mov     rcx, rbp; hDlg
0x1800132f1  call    cs:__imp_GetDlgItem
0x1800132f7  xorps   xmm0, xmm0
0x1800132fa  lea     rdx, [rsp+88h+Rect]; lpRect
0x1800132ff  mov     rcx, rax; hWnd
0x180013302  mov     rbx, rax
0x180013305  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x18001330a  call    cs:__imp_GetWindowRect
0x180013310  mov     r9d, 2; cPoints
0x180013316  lea     r8, [rsp+88h+Rect]; lpPoints
0x18001331b  mov     rdx, rbp; hWndTo
0x18001331e  xor     ecx, ecx; hWndFrom
0x180013320  call    cs:__imp_MapWindowPoints
0x180013326  mov     r8d, [rsp+88h+Rect.left]
0x18001332b  xor     edx, edx; hWndInsertAfter
0x18001332d  mov     r9d, [rsp+88h+Rect.top]; Y
0x180013332  sub     r8d, r15d; X
0x180013335  mov     [rsp+88h+uFlags], 71Dh; uFlags
0x18001333d  mov     rcx, rbx; hWnd
0x180013340  mov     [rsp+88h+cy], 0; cy
0x180013348  mov     [rsp+88h+var_68], 0; cx
0x180013350  call    cs:__imp_SetWindowPos
0x180013356  inc     esi
0x180013358  cmp     esi, edi
0x18001335a  jb      short loc_1800132EA
0x18001335c  mov     rcx, [rsp+88h+var_38]
0x180013361  xor     rcx, rsp; StackCookie
0x180013364  call    __security_check_cookie
0x180013369  mov     rbx, [rsp+88h+arg_10]
0x180013371  add     rsp, 60h
0x180013375  pop     r15
0x180013377  pop     r14
0x180013379  pop     rdi
0x18001337a  pop     rsi
0x18001337b  pop     rbp
0x18001337c  retn
```
