# ListView_SetDeviceImageList

- ea: `0x180046838`
- end: `0x18004695d`
- name: `ListView_SetDeviceImageList`
- size: `293`
- prototype: `LRESULT __fastcall(HWND, HINSTANCE)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180005cfc`
- `0x1800176f8`
- `0x180020e60`
- `0x180028920`
- `0x18002f6f8`

## callees

- `0x1800395ec`
- `0x180039780`
- `0x180046838`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004688f`
- `GDI32!DeleteObject` at `0x1800468b9`
- `GDI32!DeleteObject` at `0x1800468e3`
- `GDI32!DeleteObject` at `0x18004690d`
- `GDI32!DeleteObject` at `0x180046937`
- `GDI32!DeleteObject` at `0x18004688f`
- `GDI32!DeleteObject` at `0x1800468b9`
- `GDI32!DeleteObject` at `0x1800468e3`
- `GDI32!DeleteObject` at `0x18004690d`
- `GDI32!DeleteObject` at `0x180046937`
- `USER32!LoadIconW` at `0x180046873`
- `USER32!LoadIconW` at `0x18004689d`
- `USER32!LoadIconW` at `0x1800468c7`
- `USER32!LoadIconW` at `0x1800468f1`
- `USER32!LoadIconW` at `0x18004691b`
- `USER32!LoadIconW` at `0x180046873`
- `USER32!LoadIconW` at `0x18004689d`
- `USER32!LoadIconW` at `0x1800468c7`
- `USER32!LoadIconW` at `0x1800468f1`
- `USER32!LoadIconW` at `0x18004691b`
- `USER32!SendMessageW` at `0x180046956`
- `USER32!GetSystemMetrics` at `0x18004684c`
- `USER32!GetSystemMetrics` at `0x180046859`
- `USER32!GetSystemMetrics` at `0x18004684c`
- `USER32!GetSystemMetrics` at `0x180046859`

## pseudocode

```c
LRESULT __fastcall ListView_SetDeviceImageList(HWND a1, HINSTANCE a2)
{
  int SystemMetrics; // ebx
  int v5; // eax
  UINT v6; // r8d
  int v7; // r9d
  struct _IMAGELIST *v8; // rbx
  HICON IconW; // rax
  int v10; // edx
  HICON v11; // rsi
  HICON v12; // rax
  int v13; // edx
  HICON v14; // rsi
  HICON v15; // rax
  int v16; // edx
  HICON v17; // rsi
  HICON v18; // rax
  int v19; // edx
  HICON v20; // rsi
  HICON v21; // rax
  int v22; // edx
  HICON v23; // rdi
  int v25; // [rsp+20h] [rbp-38h]

  SystemMetrics = GetSystemMetrics(50);
  v5 = GetSystemMetrics(49);
  v8 = ImageList_Create(v5, SystemMetrics, v6, v7, v25);
  IconW = LoadIconW(a2, (LPCWSTR)0x34);
  v11 = IconW;
  if ( IconW )
  {
    ImageList_ReplaceIcon(v8, v10, IconW);
    DeleteObject(v11);
  }
  v12 = LoadIconW(a2, (LPCWSTR)0x35);
  v14 = v12;
  if ( v12 )
  {
    ImageList_ReplaceIcon(v8, v13, v12);
    DeleteObject(v14);
  }
  v15 = LoadIconW(a2, (LPCWSTR)0x36);
  v17 = v15;
  if ( v15 )
  {
    ImageList_ReplaceIcon(v8, v16, v15);
    DeleteObject(v17);
  }
  v18 = LoadIconW(a2, (LPCWSTR)0x37);
  v20 = v18;
  if ( v18 )
  {
    ImageList_ReplaceIcon(v8, v19, v18);
    DeleteObject(v20);
  }
  v21 = LoadIconW(a2, (LPCWSTR)0x40);
  v23 = v21;
  if ( v21 )
  {
    ImageList_ReplaceIcon(v8, v22, v21);
    DeleteObject(v23);
  }
  return SendMessageW(a1, 0x1003u, 1u, (LPARAM)v8);
}

```

## disassembly

```asm
0x180046838  push    rbx
0x18004683a  push    rbp
0x18004683b  push    rsi
0x18004683c  push    rdi
0x18004683d  sub     rsp, 38h
0x180046841  mov     rbp, rcx
0x180046844  mov     rdi, rdx
0x180046847  mov     ecx, 32h ; '2'; nIndex
0x18004684c  call    cs:__imp_GetSystemMetrics
0x180046852  mov     ecx, 31h ; '1'; nIndex
0x180046857  mov     ebx, eax
0x180046859  call    cs:__imp_GetSystemMetrics
0x18004685f  mov     ecx, eax; cx
0x180046861  mov     edx, ebx; cy
0x180046863  call    ImageList_Create
0x180046868  mov     edx, 34h ; '4'; lpIconName
0x18004686d  mov     rcx, rdi; hInstance
0x180046870  mov     rbx, rax
0x180046873  call    cs:__imp_LoadIconW
0x180046879  mov     rsi, rax
0x18004687c  test    rax, rax
0x18004687f  jz      short loc_180046895
0x180046881  mov     r8, rax; hicon
0x180046884  mov     rcx, rbx; himl
0x180046887  call    ImageList_ReplaceIcon
0x18004688c  mov     rcx, rsi; ho
0x18004688f  call    cs:__imp_DeleteObject
0x180046895  mov     edx, 35h ; '5'; lpIconName
0x18004689a  mov     rcx, rdi; hInstance
0x18004689d  call    cs:__imp_LoadIconW
0x1800468a3  mov     rsi, rax
0x1800468a6  test    rax, rax
0x1800468a9  jz      short loc_1800468BF
0x1800468ab  mov     r8, rax; hicon
0x1800468ae  mov     rcx, rbx; himl
0x1800468b1  call    ImageList_ReplaceIcon
0x1800468b6  mov     rcx, rsi; ho
0x1800468b9  call    cs:__imp_DeleteObject
0x1800468bf  mov     edx, 36h ; '6'; lpIconName
0x1800468c4  mov     rcx, rdi; hInstance
0x1800468c7  call    cs:__imp_LoadIconW
0x1800468cd  mov     rsi, rax
0x1800468d0  test    rax, rax
0x1800468d3  jz      short loc_1800468E9
0x1800468d5  mov     r8, rax; hicon
0x1800468d8  mov     rcx, rbx; himl
0x1800468db  call    ImageList_ReplaceIcon
0x1800468e0  mov     rcx, rsi; ho
0x1800468e3  call    cs:__imp_DeleteObject
0x1800468e9  mov     edx, 37h ; '7'; lpIconName
0x1800468ee  mov     rcx, rdi; hInstance
0x1800468f1  call    cs:__imp_LoadIconW
0x1800468f7  mov     rsi, rax
0x1800468fa  test    rax, rax
0x1800468fd  jz      short loc_180046913
0x1800468ff  mov     r8, rax; hicon
0x180046902  mov     rcx, rbx; himl
0x180046905  call    ImageList_ReplaceIcon
0x18004690a  mov     rcx, rsi; ho
0x18004690d  call    cs:__imp_DeleteObject
0x180046913  mov     edx, 40h ; '@'; lpIconName
0x180046918  mov     rcx, rdi; hInstance
0x18004691b  call    cs:__imp_LoadIconW
0x180046921  mov     rdi, rax
0x180046924  test    rax, rax
0x180046927  jz      short loc_18004693D
0x180046929  mov     r8, rax; hicon
0x18004692c  mov     rcx, rbx; himl
0x18004692f  call    ImageList_ReplaceIcon
0x180046934  mov     rcx, rdi; ho
0x180046937  call    cs:__imp_DeleteObject
0x18004693d  mov     r9, rbx
0x180046940  mov     edx, 1003h
0x180046945  mov     r8d, 1
0x18004694b  mov     rcx, rbp
0x18004694e  add     rsp, 38h
0x180046952  pop     rdi
0x180046953  pop     rsi
0x180046954  pop     rbp
0x180046955  pop     rbx
0x180046956  jmp     cs:__imp_SendMessageW
```
