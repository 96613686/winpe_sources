# ListView_SetNetworkComponentImageList

- ea: `0x180046964`
- end: `0x180046a35`
- name: `ListView_SetNetworkComponentImageList`
- size: `209`
- prototype: `LRESULT __fastcall(HWND, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180032a04`

## callees

- `0x1800395ec`
- `0x180039780`
- `0x180046964`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800469bb`
- `GDI32!DeleteObject` at `0x1800469e5`
- `GDI32!DeleteObject` at `0x180046a0f`
- `GDI32!DeleteObject` at `0x1800469bb`
- `GDI32!DeleteObject` at `0x1800469e5`
- `GDI32!DeleteObject` at `0x180046a0f`
- `USER32!LoadIconW` at `0x18004699f`
- `USER32!LoadIconW` at `0x1800469c9`
- `USER32!LoadIconW` at `0x1800469f3`
- `USER32!LoadIconW` at `0x18004699f`
- `USER32!LoadIconW` at `0x1800469c9`
- `USER32!LoadIconW` at `0x1800469f3`
- `USER32!SendMessageW` at `0x180046a2e`
- `USER32!GetSystemMetrics` at `0x180046978`
- `USER32!GetSystemMetrics` at `0x180046985`
- `USER32!GetSystemMetrics` at `0x180046978`
- `USER32!GetSystemMetrics` at `0x180046985`

## pseudocode

```c
LRESULT __fastcall ListView_SetNetworkComponentImageList(HWND a1, HINSTANCE a2)
{
  int SystemMetrics; // ebx
  int v5; // eax
  UINT v6; // r8d
  int v7; // r9d
  struct _IMAGELIST *v8; // rbx
  HICON IconW; // rax
  int v10; // edx
  HICON v11; // rdi
  HICON v12; // rax
  int v13; // edx
  HICON v14; // rdi
  HICON v15; // rax
  int v16; // edx
  HICON v17; // rdi
  int v19; // [rsp+20h] [rbp-38h]

  SystemMetrics = GetSystemMetrics(50);
  v5 = GetSystemMetrics(49);
  v8 = ImageList_Create(v5, SystemMetrics, v6, v7, v19);
  IconW = LoadIconW(a2, (LPCWSTR)0x3A);
  v11 = IconW;
  if ( IconW )
  {
    ImageList_ReplaceIcon(v8, v10, IconW);
    DeleteObject(v11);
  }
  v12 = LoadIconW(a2, (LPCWSTR)0x3B);
  v14 = v12;
  if ( v12 )
  {
    ImageList_ReplaceIcon(v8, v13, v12);
    DeleteObject(v14);
  }
  v15 = LoadIconW(a2, (LPCWSTR)0x39);
  v17 = v15;
  if ( v15 )
  {
    ImageList_ReplaceIcon(v8, v16, v15);
    DeleteObject(v17);
  }
  return SendMessageW(a1, 0x1003u, 1u, (LPARAM)v8);
}

```

## disassembly

```asm
0x180046964  push    rbx
0x180046966  push    rbp
0x180046967  push    rsi
0x180046968  push    rdi
0x180046969  sub     rsp, 38h
0x18004696d  mov     rbp, rcx
0x180046970  mov     rsi, rdx
0x180046973  mov     ecx, 32h ; '2'; nIndex
0x180046978  call    cs:__imp_GetSystemMetrics
0x18004697e  mov     ecx, 31h ; '1'; nIndex
0x180046983  mov     ebx, eax
0x180046985  call    cs:__imp_GetSystemMetrics
0x18004698b  mov     ecx, eax; cx
0x18004698d  mov     edx, ebx; cy
0x18004698f  call    ImageList_Create
0x180046994  mov     edx, 3Ah ; ':'; lpIconName
0x180046999  mov     rcx, rsi; hInstance
0x18004699c  mov     rbx, rax
0x18004699f  call    cs:__imp_LoadIconW
0x1800469a5  mov     rdi, rax
0x1800469a8  test    rax, rax
0x1800469ab  jz      short loc_1800469C1
0x1800469ad  mov     r8, rax; hicon
0x1800469b0  mov     rcx, rbx; himl
0x1800469b3  call    ImageList_ReplaceIcon
0x1800469b8  mov     rcx, rdi; ho
0x1800469bb  call    cs:__imp_DeleteObject
0x1800469c1  mov     edx, 3Bh ; ';'; lpIconName
0x1800469c6  mov     rcx, rsi; hInstance
0x1800469c9  call    cs:__imp_LoadIconW
0x1800469cf  mov     rdi, rax
0x1800469d2  test    rax, rax
0x1800469d5  jz      short loc_1800469EB
0x1800469d7  mov     r8, rax; hicon
0x1800469da  mov     rcx, rbx; himl
0x1800469dd  call    ImageList_ReplaceIcon
0x1800469e2  mov     rcx, rdi; ho
0x1800469e5  call    cs:__imp_DeleteObject
0x1800469eb  mov     edx, 39h ; '9'; lpIconName
0x1800469f0  mov     rcx, rsi; hInstance
0x1800469f3  call    cs:__imp_LoadIconW
0x1800469f9  mov     rdi, rax
0x1800469fc  test    rax, rax
0x1800469ff  jz      short loc_180046A15
0x180046a01  mov     r8, rax; hicon
0x180046a04  mov     rcx, rbx; himl
0x180046a07  call    ImageList_ReplaceIcon
0x180046a0c  mov     rcx, rdi; ho
0x180046a0f  call    cs:__imp_DeleteObject
0x180046a15  mov     r9, rbx
0x180046a18  mov     edx, 1003h
0x180046a1d  mov     r8d, 1
0x180046a23  mov     rcx, rbp
0x180046a26  add     rsp, 38h
0x180046a2a  pop     rdi
0x180046a2b  pop     rsi
0x180046a2c  pop     rbp
0x180046a2d  pop     rbx
0x180046a2e  jmp     cs:__imp_SendMessageW
```
