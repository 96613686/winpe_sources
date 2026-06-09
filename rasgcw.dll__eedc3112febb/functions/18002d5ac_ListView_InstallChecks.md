# ListView_InstallChecks

- ea: `0x18002d5ac`
- end: `0x18002d762`
- name: `ListView_InstallChecks`
- size: `438`
- prototype: `__int64 __fastcall(HWND hWnd, HINSTANCE hInstance)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180022850`
- `0x18002439c`
- `0x180025878`

## callees

- `0x18002d5ac`
- `0x18002ec04`
- `0x18002ed4c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002d655`
- `GDI32!DeleteObject` at `0x18002d68c`
- `GDI32!DeleteObject` at `0x18002d6b9`
- `GDI32!DeleteObject` at `0x18002d6ee`
- `GDI32!DeleteObject` at `0x18002d655`
- `GDI32!DeleteObject` at `0x18002d68c`
- `GDI32!DeleteObject` at `0x18002d6b9`
- `GDI32!DeleteObject` at `0x18002d6ee`
- `USER32!SetWindowLongPtrW` at `0x18002d73c`
- `USER32!SetWindowLongPtrW` at `0x18002d73c`
- `USER32!SetPropW` at `0x18002d74f`
- `USER32!SetPropW` at `0x18002d74f`
- `USER32!SendMessageW` at `0x18002d705`
- `USER32!SendMessageW` at `0x18002d705`
- `USER32!GetSystemMetrics` at `0x18002d5fd`
- `USER32!GetSystemMetrics` at `0x18002d60a`
- `USER32!GetSystemMetrics` at `0x18002d5fd`
- `USER32!GetSystemMetrics` at `0x18002d60a`
- `USER32!LoadIconW` at `0x18002d636`
- `USER32!LoadIconW` at `0x18002d66d`
- `USER32!LoadIconW` at `0x18002d69a`
- `USER32!LoadIconW` at `0x18002d6cf`
- `USER32!LoadIconW` at `0x18002d636`
- `USER32!LoadIconW` at `0x18002d66d`
- `USER32!LoadIconW` at `0x18002d69a`
- `USER32!LoadIconW` at `0x18002d6cf`
- `USER32!GetWindowLongW` at `0x18002d5e8`
- `USER32!GetWindowLongW` at `0x18002d5e8`
- `USER32!GetWindowLongPtrW` at `0x18002d5c4`
- `USER32!GetWindowLongPtrW` at `0x18002d5c4`
- `KERNEL32!GlobalAddAtomW` at `0x18002d71c`
- `KERNEL32!GlobalAddAtomW` at `0x18002d71c`

## pseudocode

```c
int __fastcall ListView_InstallChecks(HWND hWnd, HINSTANCE hInstance)
{
  const WCHAR *v4; // rax
  int v5; // r14d
  int SystemMetrics; // ebx
  int v7; // eax
  struct _IMAGELIST *v8; // rbx
  HICON IconW; // rax
  HICON v10; // rsi
  HICON v11; // rax
  HICON v12; // rsi
  HICON v13; // rax
  HICON v14; // rsi
  HICON v15; // rax
  HICON v16; // rsi
  void *v17; // rax

  if ( (__int64 (__fastcall *)(HWND, UINT, WPARAM))GetWindowLongPtrW(hWnd, -4) == LvxcbProc )
  {
    LODWORD(v4) = 1;
  }
  else
  {
    v5 = GetWindowLongW(hWnd, -20) & 0x400000;
    SystemMetrics = GetSystemMetrics(50);
    v7 = GetSystemMetrics(49);
    v8 = ImageList_Create(v7, SystemMetrics, 1u, 2, 2);
    IconW = LoadIconW(hInstance, (LPCWSTR)0x33);
    v10 = IconW;
    if ( IconW )
    {
      ImageList_ReplaceIcon(v8, -1, IconW);
      DeleteObject(v10);
    }
    v11 = LoadIconW(hInstance, (LPCWSTR)(v5 != 0 ? 62LL : 50LL));
    v12 = v11;
    if ( v11 )
    {
      ImageList_ReplaceIcon(v8, -1, v11);
      DeleteObject(v12);
    }
    v13 = LoadIconW(hInstance, (LPCWSTR)0x3C);
    v14 = v13;
    if ( v13 )
    {
      ImageList_ReplaceIcon(v8, -1, v13);
      DeleteObject(v14);
    }
    v15 = LoadIconW(hInstance, (LPCWSTR)(v5 != 0 ? 63LL : 61LL));
    v16 = v15;
    if ( v15 )
    {
      ImageList_ReplaceIcon(v8, -1, v15);
      DeleteObject(v16);
    }
    SendMessageW(hWnd, 0x1003u, 2u, (LPARAM)v8);
    if ( qword_18004DC50 || (v4 = (const WCHAR *)GlobalAddAtomW(L"RASLVXCB"), qword_18004DC50 = v4, (_WORD)v4) )
    {
      v17 = (void *)SetWindowLongPtrW(hWnd, -4, (LONG_PTR)LvxcbProc);
      LODWORD(v4) = SetPropW(hWnd, qword_18004DC50, v17);
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18002d5ac  push    rbx
0x18002d5ae  push    rbp
0x18002d5af  push    rsi
0x18002d5b0  push    rdi
0x18002d5b1  push    r13
0x18002d5b3  push    r14
0x18002d5b5  sub     rsp, 38h
0x18002d5b9  mov     rbp, rdx
0x18002d5bc  mov     rdi, rcx
0x18002d5bf  mov     edx, 0FFFFFFFCh; nIndex
0x18002d5c4  call    cs:__imp_GetWindowLongPtrW
0x18002d5ca  lea     r13, LvxcbProc
0x18002d5d1  cmp     rax, r13
0x18002d5d4  jnz     short loc_18002D5E0
0x18002d5d6  mov     eax, 1
0x18002d5db  jmp     loc_18002D755
0x18002d5e0  mov     edx, 0FFFFFFECh; nIndex
0x18002d5e5  mov     rcx, rdi; hWnd
0x18002d5e8  call    cs:__imp_GetWindowLongW
0x18002d5ee  mov     r14d, eax
0x18002d5f1  mov     ecx, 32h ; '2'; nIndex
0x18002d5f6  and     r14d, 400000h
0x18002d5fd  call    cs:__imp_GetSystemMetrics
0x18002d603  mov     ecx, 31h ; '1'; nIndex
0x18002d608  mov     ebx, eax
0x18002d60a  call    cs:__imp_GetSystemMetrics
0x18002d610  mov     r9d, 2; cInitial
0x18002d616  mov     [rsp+68h+cGrow], 2; cGrow
0x18002d61e  mov     ecx, eax; cx
0x18002d620  mov     edx, ebx; cy
0x18002d622  lea     r8d, [r9-1]; flags
0x18002d626  call    ImageList_Create
0x18002d62b  mov     edx, 33h ; '3'; lpIconName
0x18002d630  mov     rcx, rbp; hInstance
0x18002d633  mov     rbx, rax
0x18002d636  call    cs:__imp_LoadIconW
0x18002d63c  mov     rsi, rax
0x18002d63f  test    rax, rax
0x18002d642  jz      short loc_18002D65B
0x18002d644  mov     r8, rax; hicon
0x18002d647  or      edx, 0FFFFFFFFh; i
0x18002d64a  mov     rcx, rbx; himl
0x18002d64d  call    ImageList_ReplaceIcon
0x18002d652  mov     rcx, rsi; ho
0x18002d655  call    cs:__imp_DeleteObject
0x18002d65b  mov     eax, r14d
0x18002d65e  mov     rcx, rbp; hInstance
0x18002d661  neg     eax
0x18002d663  sbb     rdx, rdx
0x18002d666  and     edx, 0Ch
0x18002d669  add     rdx, 32h ; '2'; lpIconName
0x18002d66d  call    cs:__imp_LoadIconW
0x18002d673  mov     rsi, rax
0x18002d676  test    rax, rax
0x18002d679  jz      short loc_18002D692
0x18002d67b  mov     r8, rax; hicon
0x18002d67e  or      edx, 0FFFFFFFFh; i
0x18002d681  mov     rcx, rbx; himl
0x18002d684  call    ImageList_ReplaceIcon
0x18002d689  mov     rcx, rsi; ho
0x18002d68c  call    cs:__imp_DeleteObject
0x18002d692  mov     edx, 3Ch ; '<'; lpIconName
0x18002d697  mov     rcx, rbp; hInstance
0x18002d69a  call    cs:__imp_LoadIconW
0x18002d6a0  mov     rsi, rax
0x18002d6a3  test    rax, rax
0x18002d6a6  jz      short loc_18002D6BF
0x18002d6a8  mov     r8, rax; hicon
0x18002d6ab  or      edx, 0FFFFFFFFh; i
0x18002d6ae  mov     rcx, rbx; himl
0x18002d6b1  call    ImageList_ReplaceIcon
0x18002d6b6  mov     rcx, rsi; ho
0x18002d6b9  call    cs:__imp_DeleteObject
0x18002d6bf  neg     r14d
0x18002d6c2  mov     rcx, rbp; hInstance
0x18002d6c5  sbb     rdx, rdx
0x18002d6c8  and     edx, 2
0x18002d6cb  add     rdx, 3Dh ; '='; lpIconName
0x18002d6cf  call    cs:__imp_LoadIconW
0x18002d6d5  mov     rsi, rax
0x18002d6d8  test    rax, rax
0x18002d6db  jz      short loc_18002D6F4
0x18002d6dd  mov     r8, rax; hicon
0x18002d6e0  or      edx, 0FFFFFFFFh; i
0x18002d6e3  mov     rcx, rbx; himl
0x18002d6e6  call    ImageList_ReplaceIcon
0x18002d6eb  mov     rcx, rsi; ho
0x18002d6ee  call    cs:__imp_DeleteObject
0x18002d6f4  mov     r9, rbx; lParam
0x18002d6f7  mov     edx, 1003h; Msg
0x18002d6fc  mov     r8d, 2; wParam
0x18002d702  mov     rcx, rdi; hWnd
0x18002d705  call    cs:__imp_SendMessageW
0x18002d70b  cmp     cs:qword_18004DC50, 0
0x18002d713  jnz     short loc_18002D731
0x18002d715  lea     rcx, aRaslvxcb; "RASLVXCB"
0x18002d71c  call    cs:__imp_GlobalAddAtomW
0x18002d722  movzx   eax, ax
0x18002d725  mov     cs:qword_18004DC50, rax
0x18002d72c  test    rax, rax
0x18002d72f  jz      short loc_18002D755
0x18002d731  mov     r8, r13; dwNewLong
0x18002d734  mov     edx, 0FFFFFFFCh; nIndex
0x18002d739  mov     rcx, rdi; hWnd
0x18002d73c  call    cs:__imp_SetWindowLongPtrW
0x18002d742  mov     rdx, cs:qword_18004DC50; lpString
0x18002d749  mov     rcx, rdi; hWnd
0x18002d74c  mov     r8, rax; hData
0x18002d74f  call    cs:__imp_SetPropW
0x18002d755  add     rsp, 38h
0x18002d759  pop     r14
0x18002d75b  pop     r13
0x18002d75d  pop     rdi
0x18002d75e  pop     rsi
0x18002d75f  pop     rbp
0x18002d760  pop     rbx
0x18002d761  retn
```
