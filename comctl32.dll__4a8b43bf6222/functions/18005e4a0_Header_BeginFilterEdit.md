# Header_BeginFilterEdit

- ea: `0x18005e4a0`
- end: `0x18005e79d`
- name: `Header_BeginFilterEdit`
- size: `765`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180060e18`
- `0x180061f10`

## callees

- `0x1800115f0`
- `0x18001ac40`
- `0x18002fd4c`
- `0x18005e4a0`
- `0x18005fc74`
- `0x180060924`
- `0x180060990`

## import_xrefs

- `USER32!SendMessageW` at `0x18005e720`
- `USER32!SendMessageW` at `0x18005e739`
- `USER32!SendMessageW` at `0x18005e750`
- `USER32!SendMessageW` at `0x18005e720`
- `USER32!SendMessageW` at `0x18005e739`
- `USER32!SendMessageW` at `0x18005e750`
- `USER32!RedrawWindow` at `0x18005e6ea`
- `USER32!RedrawWindow` at `0x18005e6ea`
- `USER32!SetWindowLongPtrW` at `0x18005e701`
- `USER32!SetWindowLongPtrW` at `0x18005e701`
- `USER32!CreateWindowExW` at `0x18005e64e`
- `USER32!CreateWindowExW` at `0x18005e64e`
- `USER32!SetFocus` at `0x18005e75d`
- `USER32!SetFocus` at `0x18005e75d`

## pseudocode

```c
_BOOL8 __fastcall Header_BeginFilterEdit(__int64 a1, int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdi
  int v6; // kr00_4
  WCHAR *v7; // r15
  int v8; // r13d
  DWORD v9; // r12d
  const WCHAR *v10; // r8
  HWND Window; // rax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  int v14; // kr04_4
  HWND v15; // rcx
  LONG_PTR v16; // rax
  HWND v17; // rcx
  RECT rcUpdate; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h] BYREF
  WCHAR WindowName[264]; // [rsp+80h] [rbp-80h] BYREF

  v20 = 0;
  rcUpdate = 0;
  if ( a2 < 0 )
    return 0;
  v4 = *(_QWORD *)(a1 + 88);
  if ( a2 >= *(_DWORD *)v4 )
    return 0;
  v5 = *(_QWORD *)(v4 + 8) + (unsigned int)(*(_DWORD *)(v4 + 20) * a2);
  if ( !v5 )
    return 0;
  Header_OnGetItemRect(a1, (unsigned int)a2, &v20);
  rcUpdate.left = v20;
  v6 = HIDWORD(v20) - DWORD1(v20) - 1;
  rcUpdate.right = DWORD2(v20) - 4 * g_cxBorder - 13;
  rcUpdate.bottom = v6 / 2 + DWORD1(v20) + v6 / 2;
  rcUpdate.top = v6 / 2 + DWORD1(v20);
  *(_DWORD *)(a1 + 208) = *(_DWORD *)(v5 + 64);
  if ( (*(_DWORD *)(v5 + 64) & 0xF) == 0 )
  {
    v9 = 1409286272;
    Str_Set(a1 + 216, *(_QWORD *)(v5 + 72));
    v7 = *(WCHAR **)(v5 + 72);
    v8 = *(_DWORD *)(v5 + 80);
    goto LABEL_8;
  }
  if ( (*(_DWORD *)(v5 + 64) & 0xF) != 1 )
    return 0;
  *(_DWORD *)(a1 + 224) = *(_DWORD *)(v5 + 88);
  v7 = WindowName;
  StringCchPrintfW(WindowName, 0x104u, L"%d", *(unsigned int *)(v5 + 88));
  v8 = 11;
  v9 = 1409294464;
LABEL_8:
  v10 = &::WindowName;
  if ( (*(_DWORD *)(v5 + 64) & 0x8000) == 0 )
    v10 = v7;
  Window = CreateWindowExW(
             0,
             L"EDIT",
             v10,
             v9,
             rcUpdate.left + 2 * g_cxLabelMargin + g_cxLabelMargin,
             rcUpdate.top + g_cyEdge,
             rcUpdate.right - 6 * g_cxLabelMargin - rcUpdate.left,
             rcUpdate.bottom - 2 * g_cyEdge - rcUpdate.top,
             *(HWND *)a1,
             0,
             g_hinst,
             0);
  *(_QWORD *)(a1 + 192) = Window;
  if ( Window )
  {
    v12 = *(_DWORD *)(a1 + 172);
    *(_DWORD *)(a1 + 176) = a2;
    *(_DWORD *)(a1 + 172) = Header_OnGetItemOrder(a1, (unsigned int)a2);
    v13 = Header_ItemOrderToIndex(a1, v12);
    Header_OnGetItemRect(a1, v13, &v20);
    rcUpdate.left = v20;
    v14 = HIDWORD(v20) - DWORD1(v20) - 1;
    v15 = *(HWND *)a1;
    rcUpdate.top = v14 / 2 + DWORD1(v20);
    rcUpdate.right = DWORD2(v20) - 4 * g_cxBorder - 13;
    rcUpdate.bottom = rcUpdate.top + v14 / 2;
    RedrawWindow(v15, &rcUpdate, 0, 5u);
    v16 = SetWindowLongPtrW(*(HWND *)(a1 + 192), -4, (LONG_PTR)Header_EditWndProc);
    v17 = *(HWND *)(a1 + 192);
    *(_QWORD *)(a1 + 200) = v16;
    SendMessageW(v17, 0xC5u, v8, 0);
    SendMessageW(*(HWND *)(a1 + 192), 0xB1u, 0, -1);
    SendMessageW(*(HWND *)(a1 + 192), 0x30u, *(_QWORD *)(a1 + 72), 0);
    SetFocus(*(HWND *)(a1 + 192));
  }
  return *(_QWORD *)(a1 + 192) != 0;
}

```

## disassembly

```asm
0x18005e4a0  mov     [rsp-8+arg_10], rbx
0x18005e4a5  push    rbp
0x18005e4a6  push    rsi
0x18005e4a7  push    rdi
0x18005e4a8  push    r12
0x18005e4aa  push    r13
0x18005e4ac  push    r14
0x18005e4ae  push    r15
0x18005e4b0  lea     rbp, [rsp-1A0h]
0x18005e4b8  sub     rsp, 2A0h
0x18005e4bf  mov     rax, cs:__security_cookie
0x18005e4c6  xor     rax, rsp
0x18005e4c9  mov     [rbp+1D0h+var_40], rax
0x18005e4d0  xorps   xmm0, xmm0
0x18005e4d3  xorps   xmm1, xmm1
0x18005e4d6  mov     r14d, edx
0x18005e4d9  mov     rsi, rcx
0x18005e4dc  movups  [rsp+2D0h+var_260], xmm0
0x18005e4e1  movups  xmmword ptr [rsp+2D0h+rcUpdate.left], xmm1
0x18005e4e6  test    edx, edx
0x18005e4e8  js      loc_18005E771
0x18005e4ee  mov     rdx, [rcx+58h]
0x18005e4f2  cmp     r14d, [rdx]
0x18005e4f5  jge     loc_18005E771
0x18005e4fb  mov     edi, r14d
0x18005e4fe  imul    edi, [rdx+14h]
0x18005e502  add     rdi, [rdx+8]
0x18005e506  jz      loc_18005E771
0x18005e50c  lea     r8, [rsp+2D0h+var_260]
0x18005e511  mov     edx, r14d
0x18005e514  call    Header_OnGetItemRect
0x18005e519  mov     r8d, dword ptr [rsp+2D0h+var_260+4]
0x18005e51e  mov     ecx, dword ptr [rsp+2D0h+var_260]
0x18005e522  mov     eax, dword ptr [rsp+2D0h+var_260+0Ch]
0x18005e526  sub     eax, r8d
0x18005e529  mov     [rsp+2D0h+rcUpdate.left], ecx
0x18005e52d  mov     ecx, cs:g_cxBorder
0x18005e533  dec     eax
0x18005e535  cdq
0x18005e536  shl     ecx, 2
0x18005e539  sub     eax, edx
0x18005e53b  mov     edx, dword ptr [rsp+2D0h+var_260+8]
0x18005e53f  sar     eax, 1
0x18005e541  sub     edx, ecx
0x18005e543  add     r8d, eax
0x18005e546  sub     edx, 0Dh
0x18005e549  add     eax, r8d
0x18005e54c  mov     [rsp+2D0h+rcUpdate.right], edx
0x18005e550  mov     [rsp+2D0h+rcUpdate.bottom], eax
0x18005e554  mov     [rsp+2D0h+rcUpdate.top], r8d
0x18005e559  mov     eax, [rdi+40h]
0x18005e55c  mov     [rsi+0D0h], eax
0x18005e562  mov     eax, [rdi+40h]
0x18005e565  and     eax, 0Fh
0x18005e568  jz      short loc_18005E5A7
0x18005e56a  cmp     eax, 1
0x18005e56d  jnz     loc_18005E771
0x18005e573  mov     eax, [rdi+58h]
0x18005e576  lea     r8, aD; "%d"
0x18005e57d  mov     [rsi+0E0h], eax
0x18005e583  lea     rcx, [rbp+1D0h+WindowName]; Buffer
0x18005e587  mov     r9d, [rdi+58h]
0x18005e58b  lea     r15, [rbp+1D0h+WindowName]
0x18005e58f  mov     edx, 104h; unsigned __int64
0x18005e594  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005e599  mov     r13d, 0Bh
0x18005e59f  mov     r12d, 54002080h
0x18005e5a5  jmp     short loc_18005E5C5
0x18005e5a7  mov     rdx, [rdi+48h]
0x18005e5ab  lea     rcx, [rsi+0D8h]
0x18005e5b2  mov     r12d, 54000080h
0x18005e5b8  call    Str_Set
0x18005e5bd  mov     r15, [rdi+48h]
0x18005e5c1  mov     r13d, [rdi+50h]
0x18005e5c5  mov     ebx, cs:g_cxLabelMargin
0x18005e5cb  lea     r8, WindowName
0x18005e5d2  mov     edx, [rsp+2D0h+rcUpdate.left]
0x18005e5d6  mov     r9d, r12d; dwStyle
0x18005e5d9  mov     ecx, cs:g_cyEdge
0x18005e5df  mov     r11d, [rsp+2D0h+rcUpdate.right]
0x18005e5e4  mov     r10d, [rsp+2D0h+rcUpdate.bottom]
0x18005e5e9  lea     eax, [rbx+rbx*2]
0x18005e5ec  add     eax, eax
0x18005e5ee  sub     r11d, eax
0x18005e5f1  lea     eax, [rcx+rcx]
0x18005e5f4  sub     r10d, eax
0x18005e5f7  sub     r11d, edx
0x18005e5fa  sub     r10d, [rsp+2D0h+rcUpdate.top]
0x18005e5ff  lea     eax, [rdx+rbx*2]
0x18005e602  test    dword ptr [rdi+40h], 8000h
0x18005e609  lea     rdx, aEdit; "EDIT"
0x18005e610  cmovz   r8, r15; lpWindowName
0x18005e614  add     ecx, [rsp+2D0h+rcUpdate.top]
0x18005e618  add     ebx, eax
0x18005e61a  xor     edi, edi
0x18005e61c  mov     rax, cs:g_hinst
0x18005e623  mov     [rsp+2D0h+lpParam], rdi; lpParam
0x18005e628  mov     [rsp+2D0h+hInstance], rax; hInstance
0x18005e62d  mov     rax, [rsi]
0x18005e630  mov     [rsp+2D0h+hMenu], rdi; hMenu
0x18005e635  mov     [rsp+2D0h+hWndParent], rax; hWndParent
0x18005e63a  mov     [rsp+2D0h+nHeight], r10d; nHeight
0x18005e63f  mov     [rsp+2D0h+nWidth], r11d; nWidth
0x18005e644  mov     [rsp+2D0h+Y], ecx; Y
0x18005e648  xor     ecx, ecx; dwExStyle
0x18005e64a  mov     [rsp+2D0h+X], ebx; X
0x18005e64e  call    cs:__imp_CreateWindowExW
0x18005e654  mov     [rsi+0C0h], rax
0x18005e65b  test    rax, rax
0x18005e65e  jz      loc_18005E763
0x18005e664  mov     ebx, [rsi+0ACh]
0x18005e66a  mov     edx, r14d
0x18005e66d  mov     rcx, rsi
0x18005e670  mov     [rsi+0B0h], r14d
0x18005e677  call    Header_OnGetItemOrder
0x18005e67c  mov     edx, ebx
0x18005e67e  mov     [rsi+0ACh], eax
0x18005e684  mov     rcx, rsi
0x18005e687  call    Header_ItemOrderToIndex
0x18005e68c  mov     edx, eax
0x18005e68e  lea     r8, [rsp+2D0h+var_260]
0x18005e693  mov     rcx, rsi
0x18005e696  call    Header_OnGetItemRect
0x18005e69b  mov     r8d, dword ptr [rsp+2D0h+var_260+4]
0x18005e6a0  lea     r9d, [rdi+5]; flags
0x18005e6a4  mov     ecx, dword ptr [rsp+2D0h+var_260]
0x18005e6a8  mov     eax, dword ptr [rsp+2D0h+var_260+0Ch]
0x18005e6ac  sub     eax, r8d
0x18005e6af  mov     [rsp+2D0h+rcUpdate.left], ecx
0x18005e6b3  mov     ecx, cs:g_cxBorder
0x18005e6b9  dec     eax
0x18005e6bb  cdq
0x18005e6bc  shl     ecx, 2
0x18005e6bf  sub     eax, edx
0x18005e6c1  mov     edx, dword ptr [rsp+2D0h+var_260+8]
0x18005e6c5  sub     edx, ecx
0x18005e6c7  sar     eax, 1
0x18005e6c9  mov     rcx, [rsi]; hWnd
0x18005e6cc  add     r8d, eax
0x18005e6cf  sub     edx, 0Dh
0x18005e6d2  mov     [rsp+2D0h+rcUpdate.top], r8d
0x18005e6d7  add     eax, r8d
0x18005e6da  mov     [rsp+2D0h+rcUpdate.right], edx
0x18005e6de  lea     rdx, [rsp+2D0h+rcUpdate]; lprcUpdate
0x18005e6e3  mov     [rsp+2D0h+rcUpdate.bottom], eax
0x18005e6e7  xor     r8d, r8d; hrgnUpdate
0x18005e6ea  call    cs:__imp_RedrawWindow
0x18005e6f0  mov     rcx, [rsi+0C0h]; hWnd
0x18005e6f7  lea     r8, Header_EditWndProc; dwNewLong
0x18005e6fe  lea     edx, [rdi-4]; nIndex
0x18005e701  call    cs:__imp_SetWindowLongPtrW
0x18005e707  mov     rcx, [rsi+0C0h]; hWnd
0x18005e70e  xor     r9d, r9d; lParam
0x18005e711  movsxd  r8, r13d; wParam
0x18005e714  mov     edx, 0C5h; Msg
0x18005e719  mov     [rsi+0C8h], rax
0x18005e720  call    cs:__imp_SendMessageW
0x18005e726  mov     rcx, [rsi+0C0h]; hWnd
0x18005e72d  or      r9, 0FFFFFFFFFFFFFFFFh; lParam
0x18005e731  xor     r8d, r8d; wParam
0x18005e734  mov     edx, 0B1h; Msg
0x18005e739  call    cs:__imp_SendMessageW
0x18005e73f  mov     r8, [rsi+48h]; wParam
0x18005e743  lea     edx, [rdi+30h]; Msg
0x18005e746  mov     rcx, [rsi+0C0h]; hWnd
0x18005e74d  xor     r9d, r9d; lParam
0x18005e750  call    cs:__imp_SendMessageW
0x18005e756  mov     rcx, [rsi+0C0h]; hWnd
0x18005e75d  call    cs:__imp_SetFocus
0x18005e763  cmp     [rsi+0C0h], rdi
0x18005e76a  mov     eax, edi
0x18005e76c  setnz   al
0x18005e76f  jmp     short loc_18005E773
0x18005e771  xor     eax, eax
0x18005e773  mov     rcx, [rbp+1D0h+var_40]
0x18005e77a  xor     rcx, rsp; StackCookie
0x18005e77d  call    __security_check_cookie
0x18005e782  mov     rbx, [rsp+2D0h+arg_10]
0x18005e78a  add     rsp, 2A0h
0x18005e791  pop     r15
0x18005e793  pop     r14
0x18005e795  pop     r13
0x18005e797  pop     r12
0x18005e799  pop     rdi
0x18005e79a  pop     rsi
0x18005e79b  pop     rbp
0x18005e79c  retn
```
