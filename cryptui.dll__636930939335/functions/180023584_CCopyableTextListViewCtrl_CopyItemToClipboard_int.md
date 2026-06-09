# CCopyableTextListViewCtrl::CopyItemToClipboard(int)

- ea: `0x180023584`
- end: `0x180023689`
- name: `?CopyItemToClipboard@CCopyableTextListViewCtrl@@QEAAXH@Z`
- size: `261`
- prototype: `void __fastcall(CCopyableTextListViewCtrl *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025ecc`

## callees

- `0x180023584`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023677`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180023677`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800235ec`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800235ec`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023648`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023648`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800235fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800235fd`
- `USER32!SetClipboardData` at `0x180023656`
- `USER32!SetClipboardData` at `0x180023656`
- `USER32!EmptyClipboard` at `0x1800235cf`
- `USER32!EmptyClipboard` at `0x1800235cf`
- `USER32!CloseClipboard` at `0x180023661`
- `USER32!CloseClipboard` at `0x180023669`
- `USER32!CloseClipboard` at `0x180023661`
- `USER32!CloseClipboard` at `0x180023669`
- `USER32!OpenClipboard` at `0x1800235c1`
- `USER32!OpenClipboard` at `0x1800235c1`
- `USER32!SendMessageA` at `0x1800235a7`
- `USER32!SendMessageA` at `0x18002363f`
- `USER32!SendMessageA` at `0x1800235a7`
- `USER32!SendMessageA` at `0x18002363f`

## pseudocode

```c
void __fastcall CCopyableTextListViewCtrl::CopyItemToClipboard(HWND *this, int a2)
{
  WPARAM v2; // rbp
  void *v4; // rbx
  int v5; // eax
  HGLOBAL v6; // rax
  _WORD *v7; // rax
  void *v8; // rsi
  int v9; // ecx
  LPARAM lParam[4]; // [rsp+20h] [rbp-88h] BYREF
  int v11; // [rsp+40h] [rbp-68h]

  v2 = a2;
  v4 = 0;
  v5 = SendMessageA(this[1], 0x1004u, 0, 0);
  if ( (v2 & 0x80000000) != 0LL )
    goto LABEL_9;
  if ( (int)v2 >= v5 )
    goto LABEL_9;
  if ( !OpenClipboard(this[1]) )
    goto LABEL_9;
  if ( !EmptyClipboard() )
    goto LABEL_9;
  v6 = GlobalAlloc(0x42u, 2LL * (*((_DWORD *)this + 19) + 2));
  v4 = v6;
  if ( !v6 )
    goto LABEL_9;
  v7 = GlobalLock(v6);
  v8 = v7;
  if ( !v7 )
    goto LABEL_9;
  *v7 = 0;
  memset_0(lParam, 0, 0x58u);
  v9 = *((_DWORD *)this + 19) + 1;
  lParam[3] = (LPARAM)v8;
  v11 = v9;
  SendMessageA(this[1], 0x1073u, v2, (LPARAM)lParam);
  GlobalUnlock(v4);
  if ( SetClipboardData(0xDu, v8) )
  {
    CloseClipboard();
  }
  else
  {
LABEL_9:
    CloseClipboard();
    if ( v4 )
      GlobalFree(v4);
  }
}

```

## disassembly

```asm
0x180023584  push    rbx
0x180023586  push    rbp
0x180023587  push    rsi
0x180023588  push    rdi
0x180023589  sub     rsp, 88h
0x180023590  movsxd  rbp, edx
0x180023593  mov     rdi, rcx
0x180023596  mov     rcx, [rcx+8]; hWnd
0x18002359a  mov     edx, 1004h; Msg
0x18002359f  xor     r9d, r9d; lParam
0x1800235a2  xor     r8d, r8d; wParam
0x1800235a5  xor     ebx, ebx
0x1800235a7  call    cs:__imp_SendMessageA
0x1800235ad  test    ebp, ebp
0x1800235af  js      loc_180023669
0x1800235b5  cmp     ebp, eax
0x1800235b7  jge     loc_180023669
0x1800235bd  mov     rcx, [rdi+8]; hWndNewOwner
0x1800235c1  call    cs:__imp_OpenClipboard
0x1800235c7  test    eax, eax
0x1800235c9  jz      loc_180023669
0x1800235cf  call    cs:__imp_EmptyClipboard
0x1800235d5  test    eax, eax
0x1800235d7  jz      loc_180023669
0x1800235dd  mov     eax, [rdi+4Ch]
0x1800235e0  lea     ecx, [rbx+42h]; uFlags
0x1800235e3  add     eax, 2
0x1800235e6  movsxd  rdx, eax
0x1800235e9  add     rdx, rdx; dwBytes
0x1800235ec  call    cs:__imp_GlobalAlloc
0x1800235f2  mov     rbx, rax
0x1800235f5  test    rax, rax
0x1800235f8  jz      short loc_180023669
0x1800235fa  mov     rcx, rax; hMem
0x1800235fd  call    cs:__imp_GlobalLock
0x180023603  mov     rsi, rax
0x180023606  test    rax, rax
0x180023609  jz      short loc_180023669
0x18002360b  xor     ecx, ecx
0x18002360d  xor     edx, edx; Val
0x18002360f  mov     [rax], cx
0x180023612  lea     r8d, [rcx+58h]; Size
0x180023616  lea     rcx, [rsp+0A8h+lParam]; void *
0x18002361b  call    memset_0
0x180023620  mov     ecx, [rdi+4Ch]
0x180023623  lea     r9, [rsp+0A8h+lParam]; lParam
0x180023628  inc     ecx
0x18002362a  mov     [rsp+0A8h+var_70], rsi
0x18002362f  mov     [rsp+0A8h+var_68], ecx
0x180023633  mov     r8, rbp; wParam
0x180023636  mov     rcx, [rdi+8]; hWnd
0x18002363a  mov     edx, 1073h; Msg
0x18002363f  call    cs:__imp_SendMessageA
0x180023645  mov     rcx, rbx; hMem
0x180023648  call    cs:__imp_GlobalUnlock
0x18002364e  mov     rdx, rsi; hMem
0x180023651  mov     ecx, 0Dh; uFormat
0x180023656  call    cs:__imp_SetClipboardData
0x18002365c  test    rax, rax
0x18002365f  jz      short loc_180023669
0x180023661  call    cs:__imp_CloseClipboard
0x180023667  jmp     short loc_18002367D
0x180023669  call    cs:__imp_CloseClipboard
0x18002366f  test    rbx, rbx
0x180023672  jz      short loc_18002367D
0x180023674  mov     rcx, rbx; hMem
0x180023677  call    cs:__imp_GlobalFree
0x18002367d  add     rsp, 88h
0x180023684  pop     rdi
0x180023685  pop     rsi
0x180023686  pop     rbp
0x180023687  pop     rbx
0x180023688  retn
```
