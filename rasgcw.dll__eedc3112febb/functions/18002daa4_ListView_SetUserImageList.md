# ListView_SetUserImageList

- ea: `0x18002daa4`
- end: `0x18002db33`
- name: `ListView_SetUserImageList`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800235f8`

## callees

- `0x18002daa4`
- `0x18002ec04`
- `0x18002ed4c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002db0d`
- `GDI32!DeleteObject` at `0x18002db0d`
- `USER32!SendMessageW` at `0x18002db2c`
- `USER32!GetSystemMetrics` at `0x18002dab8`
- `USER32!GetSystemMetrics` at `0x18002dac5`
- `USER32!GetSystemMetrics` at `0x18002dab8`
- `USER32!GetSystemMetrics` at `0x18002dac5`
- `USER32!LoadIconW` at `0x18002daee`
- `USER32!LoadIconW` at `0x18002daee`

## pseudocode

```c
LRESULT __fastcall ListView_SetUserImageList(HWND a1, HINSTANCE a2)
{
  int SystemMetrics; // ebx
  int v5; // eax
  struct _IMAGELIST *v6; // rsi
  HICON IconW; // rax
  HICON v8; // rbx

  SystemMetrics = GetSystemMetrics(50);
  v5 = GetSystemMetrics(49);
  v6 = ImageList_Create(v5, SystemMetrics, 1u, 2, 2);
  IconW = LoadIconW(a2, (LPCWSTR)0x38);
  v8 = IconW;
  if ( IconW )
  {
    ImageList_ReplaceIcon(v6, -1, IconW);
    DeleteObject(v8);
  }
  return SendMessageW(a1, 0x1003u, 1u, (LPARAM)v6);
}

```

## disassembly

```asm
0x18002daa4  push    rbx
0x18002daa6  push    rbp
0x18002daa7  push    rsi
0x18002daa8  push    rdi
0x18002daa9  sub     rsp, 38h
0x18002daad  mov     rbp, rcx
0x18002dab0  mov     rdi, rdx
0x18002dab3  mov     ecx, 32h ; '2'; nIndex
0x18002dab8  call    cs:__imp_GetSystemMetrics
0x18002dabe  mov     ecx, 31h ; '1'; nIndex
0x18002dac3  mov     ebx, eax
0x18002dac5  call    cs:__imp_GetSystemMetrics
0x18002dacb  mov     r9d, 2; cInitial
0x18002dad1  mov     edx, ebx; cy
0x18002dad3  mov     ecx, eax; cx
0x18002dad5  mov     [rsp+58h+cGrow], r9d; cGrow
0x18002dada  lea     r8d, [r9-1]; flags
0x18002dade  call    ImageList_Create
0x18002dae3  mov     edx, 38h ; '8'; lpIconName
0x18002dae8  mov     rcx, rdi; hInstance
0x18002daeb  mov     rsi, rax
0x18002daee  call    cs:__imp_LoadIconW
0x18002daf4  mov     rbx, rax
0x18002daf7  test    rax, rax
0x18002dafa  jz      short loc_18002DB13
0x18002dafc  mov     r8, rax; hicon
0x18002daff  or      edx, 0FFFFFFFFh; i
0x18002db02  mov     rcx, rsi; himl
0x18002db05  call    ImageList_ReplaceIcon
0x18002db0a  mov     rcx, rbx; ho
0x18002db0d  call    cs:__imp_DeleteObject
0x18002db13  mov     r9, rsi
0x18002db16  mov     edx, 1003h
0x18002db1b  mov     r8d, 1
0x18002db21  mov     rcx, rbp
0x18002db24  add     rsp, 38h
0x18002db28  pop     rdi
0x18002db29  pop     rsi
0x18002db2a  pop     rbp
0x18002db2b  pop     rbx
0x18002db2c  jmp     cs:__imp_SendMessageW
```
