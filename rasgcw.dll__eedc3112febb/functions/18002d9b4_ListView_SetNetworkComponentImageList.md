# ListView_SetNetworkComponentImageList

- ea: `0x18002d9b4`
- end: `0x18002da9d`
- name: `ListView_SetNetworkComponentImageList`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025878`

## callees

- `0x18002d9b4`
- `0x18002ec04`
- `0x18002ed4c`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002da1d`
- `GDI32!DeleteObject` at `0x18002da4a`
- `GDI32!DeleteObject` at `0x18002da77`
- `GDI32!DeleteObject` at `0x18002da1d`
- `GDI32!DeleteObject` at `0x18002da4a`
- `GDI32!DeleteObject` at `0x18002da77`
- `USER32!SendMessageW` at `0x18002da96`
- `USER32!GetSystemMetrics` at `0x18002d9c8`
- `USER32!GetSystemMetrics` at `0x18002d9d5`
- `USER32!GetSystemMetrics` at `0x18002d9c8`
- `USER32!GetSystemMetrics` at `0x18002d9d5`
- `USER32!LoadIconW` at `0x18002d9fe`
- `USER32!LoadIconW` at `0x18002da2b`
- `USER32!LoadIconW` at `0x18002da58`
- `USER32!LoadIconW` at `0x18002d9fe`
- `USER32!LoadIconW` at `0x18002da2b`
- `USER32!LoadIconW` at `0x18002da58`

## pseudocode

```c
LRESULT __fastcall ListView_SetNetworkComponentImageList(HWND a1, HINSTANCE a2)
{
  int SystemMetrics; // ebx
  int v5; // eax
  struct _IMAGELIST *v6; // rbx
  HICON IconW; // rax
  HICON v8; // rdi
  HICON v9; // rax
  HICON v10; // rdi
  HICON v11; // rax
  HICON v12; // rdi

  SystemMetrics = GetSystemMetrics(50);
  v5 = GetSystemMetrics(49);
  v6 = ImageList_Create(v5, SystemMetrics, 1u, 2, 2);
  IconW = LoadIconW(a2, (LPCWSTR)0x3A);
  v8 = IconW;
  if ( IconW )
  {
    ImageList_ReplaceIcon(v6, -1, IconW);
    DeleteObject(v8);
  }
  v9 = LoadIconW(a2, (LPCWSTR)0x3B);
  v10 = v9;
  if ( v9 )
  {
    ImageList_ReplaceIcon(v6, -1, v9);
    DeleteObject(v10);
  }
  v11 = LoadIconW(a2, (LPCWSTR)0x39);
  v12 = v11;
  if ( v11 )
  {
    ImageList_ReplaceIcon(v6, -1, v11);
    DeleteObject(v12);
  }
  return SendMessageW(a1, 0x1003u, 1u, (LPARAM)v6);
}

```

## disassembly

```asm
0x18002d9b4  push    rbx
0x18002d9b6  push    rbp
0x18002d9b7  push    rsi
0x18002d9b8  push    rdi
0x18002d9b9  sub     rsp, 38h
0x18002d9bd  mov     rbp, rcx
0x18002d9c0  mov     rsi, rdx
0x18002d9c3  mov     ecx, 32h ; '2'; nIndex
0x18002d9c8  call    cs:__imp_GetSystemMetrics
0x18002d9ce  mov     ecx, 31h ; '1'; nIndex
0x18002d9d3  mov     ebx, eax
0x18002d9d5  call    cs:__imp_GetSystemMetrics
0x18002d9db  mov     r9d, 2; cInitial
0x18002d9e1  mov     edx, ebx; cy
0x18002d9e3  mov     ecx, eax; cx
0x18002d9e5  mov     [rsp+58h+cGrow], r9d; cGrow
0x18002d9ea  lea     r8d, [r9-1]; flags
0x18002d9ee  call    ImageList_Create
0x18002d9f3  mov     edx, 3Ah ; ':'; lpIconName
0x18002d9f8  mov     rcx, rsi; hInstance
0x18002d9fb  mov     rbx, rax
0x18002d9fe  call    cs:__imp_LoadIconW
0x18002da04  mov     rdi, rax
0x18002da07  test    rax, rax
0x18002da0a  jz      short loc_18002DA23
0x18002da0c  mov     r8, rax; hicon
0x18002da0f  or      edx, 0FFFFFFFFh; i
0x18002da12  mov     rcx, rbx; himl
0x18002da15  call    ImageList_ReplaceIcon
0x18002da1a  mov     rcx, rdi; ho
0x18002da1d  call    cs:__imp_DeleteObject
0x18002da23  mov     edx, 3Bh ; ';'; lpIconName
0x18002da28  mov     rcx, rsi; hInstance
0x18002da2b  call    cs:__imp_LoadIconW
0x18002da31  mov     rdi, rax
0x18002da34  test    rax, rax
0x18002da37  jz      short loc_18002DA50
0x18002da39  mov     r8, rax; hicon
0x18002da3c  or      edx, 0FFFFFFFFh; i
0x18002da3f  mov     rcx, rbx; himl
0x18002da42  call    ImageList_ReplaceIcon
0x18002da47  mov     rcx, rdi; ho
0x18002da4a  call    cs:__imp_DeleteObject
0x18002da50  mov     edx, 39h ; '9'; lpIconName
0x18002da55  mov     rcx, rsi; hInstance
0x18002da58  call    cs:__imp_LoadIconW
0x18002da5e  mov     rdi, rax
0x18002da61  test    rax, rax
0x18002da64  jz      short loc_18002DA7D
0x18002da66  mov     r8, rax; hicon
0x18002da69  or      edx, 0FFFFFFFFh; i
0x18002da6c  mov     rcx, rbx; himl
0x18002da6f  call    ImageList_ReplaceIcon
0x18002da74  mov     rcx, rdi; ho
0x18002da77  call    cs:__imp_DeleteObject
0x18002da7d  mov     r9, rbx
0x18002da80  mov     edx, 1003h
0x18002da85  mov     r8d, 1
0x18002da8b  mov     rcx, rbp
0x18002da8e  add     rsp, 38h
0x18002da92  pop     rdi
0x18002da93  pop     rsi
0x18002da94  pop     rbp
0x18002da95  pop     rbx
0x18002da96  jmp     cs:__imp_SendMessageW
```
