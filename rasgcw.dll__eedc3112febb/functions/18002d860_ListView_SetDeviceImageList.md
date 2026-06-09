# ListView_SetDeviceImageList

- ea: `0x18002d860`
- end: `0x18002d9ab`
- name: `ListView_SetDeviceImageList`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022408`

## callees

- `0x18002d860`
- `0x18002ec04`
- `0x18002ed4c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002d8cf`
- `GDI32!DeleteObject` at `0x18002d8fc`
- `GDI32!DeleteObject` at `0x18002d929`
- `GDI32!DeleteObject` at `0x18002d956`
- `GDI32!DeleteObject` at `0x18002d983`
- `GDI32!DeleteObject` at `0x18002d8cf`
- `GDI32!DeleteObject` at `0x18002d8fc`
- `GDI32!DeleteObject` at `0x18002d929`
- `GDI32!DeleteObject` at `0x18002d956`
- `GDI32!DeleteObject` at `0x18002d983`
- `USER32!SendMessageW` at `0x18002d9a4`
- `USER32!GetSystemMetrics` at `0x18002d876`
- `USER32!GetSystemMetrics` at `0x18002d883`
- `USER32!GetSystemMetrics` at `0x18002d876`
- `USER32!GetSystemMetrics` at `0x18002d883`
- `USER32!LoadIconW` at `0x18002d8ac`
- `USER32!LoadIconW` at `0x18002d8dd`
- `USER32!LoadIconW` at `0x18002d90a`
- `USER32!LoadIconW` at `0x18002d937`
- `USER32!LoadIconW` at `0x18002d964`
- `USER32!LoadIconW` at `0x18002d8ac`
- `USER32!LoadIconW` at `0x18002d8dd`
- `USER32!LoadIconW` at `0x18002d90a`
- `USER32!LoadIconW` at `0x18002d937`
- `USER32!LoadIconW` at `0x18002d964`

## pseudocode

```c
LRESULT __fastcall ListView_SetDeviceImageList(HWND a1, HINSTANCE a2)
{
  int SystemMetrics; // ebx
  int v5; // eax
  struct _IMAGELIST *v6; // rbx
  HICON IconW; // rax
  HICON v8; // rsi
  HICON v9; // rax
  HICON v10; // rsi
  HICON v11; // rax
  HICON v12; // rsi
  HICON v13; // rax
  HICON v14; // rsi
  HICON v15; // rax
  HICON v16; // rdi

  SystemMetrics = GetSystemMetrics(50);
  v5 = GetSystemMetrics(49);
  v6 = ImageList_Create(v5, SystemMetrics, 1u, 2, 2);
  IconW = LoadIconW(a2, (LPCWSTR)0x34);
  v8 = IconW;
  if ( IconW )
  {
    ImageList_ReplaceIcon(v6, -1, IconW);
    DeleteObject(v8);
  }
  v9 = LoadIconW(a2, (LPCWSTR)0x35);
  v10 = v9;
  if ( v9 )
  {
    ImageList_ReplaceIcon(v6, -1, v9);
    DeleteObject(v10);
  }
  v11 = LoadIconW(a2, (LPCWSTR)0x36);
  v12 = v11;
  if ( v11 )
  {
    ImageList_ReplaceIcon(v6, -1, v11);
    DeleteObject(v12);
  }
  v13 = LoadIconW(a2, (LPCWSTR)0x37);
  v14 = v13;
  if ( v13 )
  {
    ImageList_ReplaceIcon(v6, -1, v13);
    DeleteObject(v14);
  }
  v15 = LoadIconW(a2, (LPCWSTR)0x40);
  v16 = v15;
  if ( v15 )
  {
    ImageList_ReplaceIcon(v6, -1, v15);
    DeleteObject(v16);
  }
  return SendMessageW(a1, 0x1003u, 1u, (LPARAM)v6);
}

```

## disassembly

```asm
0x18002d860  push    rbx
0x18002d862  push    rbp
0x18002d863  push    rsi
0x18002d864  push    rdi
0x18002d865  push    r14
0x18002d867  sub     rsp, 30h
0x18002d86b  mov     rbp, rcx
0x18002d86e  mov     rdi, rdx
0x18002d871  mov     ecx, 32h ; '2'; nIndex
0x18002d876  call    cs:__imp_GetSystemMetrics
0x18002d87c  mov     ecx, 31h ; '1'; nIndex
0x18002d881  mov     ebx, eax
0x18002d883  call    cs:__imp_GetSystemMetrics
0x18002d889  mov     r9d, 2; cInitial
0x18002d88f  mov     edx, ebx; cy
0x18002d891  mov     ecx, eax; cx
0x18002d893  mov     [rsp+58h+cGrow], r9d; cGrow
0x18002d898  lea     r8d, [r9-1]; flags
0x18002d89c  call    ImageList_Create
0x18002d8a1  mov     edx, 34h ; '4'; lpIconName
0x18002d8a6  mov     rcx, rdi; hInstance
0x18002d8a9  mov     rbx, rax
0x18002d8ac  call    cs:__imp_LoadIconW
0x18002d8b2  or      r14d, 0FFFFFFFFh
0x18002d8b6  mov     rsi, rax
0x18002d8b9  test    rax, rax
0x18002d8bc  jz      short loc_18002D8D5
0x18002d8be  mov     r8, rax; hicon
0x18002d8c1  mov     edx, r14d; i
0x18002d8c4  mov     rcx, rbx; himl
0x18002d8c7  call    ImageList_ReplaceIcon
0x18002d8cc  mov     rcx, rsi; ho
0x18002d8cf  call    cs:__imp_DeleteObject
0x18002d8d5  mov     edx, 35h ; '5'; lpIconName
0x18002d8da  mov     rcx, rdi; hInstance
0x18002d8dd  call    cs:__imp_LoadIconW
0x18002d8e3  mov     rsi, rax
0x18002d8e6  test    rax, rax
0x18002d8e9  jz      short loc_18002D902
0x18002d8eb  mov     r8, rax; hicon
0x18002d8ee  mov     edx, r14d; i
0x18002d8f1  mov     rcx, rbx; himl
0x18002d8f4  call    ImageList_ReplaceIcon
0x18002d8f9  mov     rcx, rsi; ho
0x18002d8fc  call    cs:__imp_DeleteObject
0x18002d902  mov     edx, 36h ; '6'; lpIconName
0x18002d907  mov     rcx, rdi; hInstance
0x18002d90a  call    cs:__imp_LoadIconW
0x18002d910  mov     rsi, rax
0x18002d913  test    rax, rax
0x18002d916  jz      short loc_18002D92F
0x18002d918  mov     r8, rax; hicon
0x18002d91b  mov     edx, r14d; i
0x18002d91e  mov     rcx, rbx; himl
0x18002d921  call    ImageList_ReplaceIcon
0x18002d926  mov     rcx, rsi; ho
0x18002d929  call    cs:__imp_DeleteObject
0x18002d92f  mov     edx, 37h ; '7'; lpIconName
0x18002d934  mov     rcx, rdi; hInstance
0x18002d937  call    cs:__imp_LoadIconW
0x18002d93d  mov     rsi, rax
0x18002d940  test    rax, rax
0x18002d943  jz      short loc_18002D95C
0x18002d945  mov     r8, rax; hicon
0x18002d948  mov     edx, r14d; i
0x18002d94b  mov     rcx, rbx; himl
0x18002d94e  call    ImageList_ReplaceIcon
0x18002d953  mov     rcx, rsi; ho
0x18002d956  call    cs:__imp_DeleteObject
0x18002d95c  mov     edx, 40h ; '@'; lpIconName
0x18002d961  mov     rcx, rdi; hInstance
0x18002d964  call    cs:__imp_LoadIconW
0x18002d96a  mov     rdi, rax
0x18002d96d  test    rax, rax
0x18002d970  jz      short loc_18002D989
0x18002d972  mov     r8, rax; hicon
0x18002d975  mov     edx, r14d; i
0x18002d978  mov     rcx, rbx; himl
0x18002d97b  call    ImageList_ReplaceIcon
0x18002d980  mov     rcx, rdi; ho
0x18002d983  call    cs:__imp_DeleteObject
0x18002d989  mov     r9, rbx
0x18002d98c  mov     edx, 1003h
0x18002d991  mov     r8d, 1
0x18002d997  mov     rcx, rbp
0x18002d99a  add     rsp, 30h
0x18002d99e  pop     r14
0x18002d9a0  pop     rdi
0x18002d9a1  pop     rsi
0x18002d9a2  pop     rbp
0x18002d9a3  pop     rbx
0x18002d9a4  jmp     cs:__imp_SendMessageW
```
