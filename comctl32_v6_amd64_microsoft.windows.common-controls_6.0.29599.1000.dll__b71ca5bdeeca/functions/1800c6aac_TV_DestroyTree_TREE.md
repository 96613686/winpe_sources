# TV_DestroyTree(_TREE *)

- ea: `0x1800c6aac`
- end: `0x1800c6d4b`
- name: `?TV_DestroyTree@@YAXPEAU_TREE@@@Z`
- size: `671`
- prototype: `void __fastcall(struct _TREE *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d900`

## callees

- `0x18001fb68`
- `0x180022044`
- `0x180022130`
- `0x1800240cc`
- `0x180034b4c`
- `0x18006cfe0`
- `0x18006ea30`
- `0x1800c6aac`
- `0x1800c6e9c`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c6cc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6bdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6cd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6bbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6bdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c6cd2`
- `GDI32!DeleteObject` at `0x1800c6ad4`
- `GDI32!DeleteObject` at `0x1800c6b00`
- `GDI32!DeleteObject` at `0x1800c6b19`
- `GDI32!DeleteObject` at `0x1800c6c11`
- `GDI32!DeleteObject` at `0x1800c6c4c`
- `GDI32!DeleteObject` at `0x1800c6c65`
- `GDI32!DeleteObject` at `0x1800c6ad4`
- `GDI32!DeleteObject` at `0x1800c6b00`
- `GDI32!DeleteObject` at `0x1800c6b19`
- `GDI32!DeleteObject` at `0x1800c6c11`
- `GDI32!DeleteObject` at `0x1800c6c4c`
- `GDI32!DeleteObject` at `0x1800c6c65`
- `GDI32!SelectObject` at `0x1800c6c04`
- `GDI32!SelectObject` at `0x1800c6c04`
- `GDI32!DeleteDC` at `0x1800c6c25`
- `GDI32!DeleteDC` at `0x1800c6c25`
- `USER32!DestroyWindow` at `0x1800c6b57`
- `USER32!DestroyWindow` at `0x1800c6b7c`
- `USER32!DestroyWindow` at `0x1800c6b57`
- `USER32!DestroyWindow` at `0x1800c6b7c`
- `USER32!SetWindowLongPtrW` at `0x1800c6d35`
- `USER32!SetWindowLongPtrW` at `0x1800c6d35`
- `USER32!IsWindow` at `0x1800c6b46`
- `USER32!IsWindow` at `0x1800c6b6b`
- `USER32!IsWindow` at `0x1800c6b46`
- `USER32!IsWindow` at `0x1800c6b6b`
- `USER32!DestroyCursor` at `0x1800c6b32`
- `USER32!DestroyCursor` at `0x1800c6b32`
- `UxTheme!CloseThemeData` at `0x1800c6d07`
- `UxTheme!CloseThemeData` at `0x1800c6d20`
- `UxTheme!CloseThemeData` at `0x1800c6d07`
- `UxTheme!CloseThemeData` at `0x1800c6d20`

## pseudocode

```c
void __fastcall TV_DestroyTree(struct _TREE *a1)
{
  HWND v2; // rsi
  int v3; // eax
  void *v4; // rcx
  void *v5; // rcx
  HCURSOR v6; // rcx
  HWND v7; // rcx
  struct _TREEITEM *v8; // rdx
  __int64 v9; // rcx
  void *v10; // r8
  HDC v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx
  struct _DPA *v15; // rcx
  void *v16; // rdi
  HANDLE ProcessHeap; // rax
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  void *v19; // rcx
  void *v20; // rcx

  *((_DWORD *)a1 + 16) &= ~0x10u;
  v2 = *(HWND *)a1;
  v3 = *((_DWORD *)a1 + 16);
  if ( *((_DWORD *)a1 + 83) != -1 )
  {
    DeleteObject(*((HGDIOBJ *)a1 + 28));
    v3 = *((_DWORD *)a1 + 16);
  }
  *((_DWORD *)a1 + 83) = -1;
  *((_DWORD *)a1 + 16) = v3 | 0x40000;
  TV_CreateIndentBmps(a1);
  v4 = (void *)*((_QWORD *)a1 + 38);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)a1 + 38) = 0;
  }
  v5 = (void *)*((_QWORD *)a1 + 39);
  if ( v5 )
  {
    DeleteObject(v5);
    *((_QWORD *)a1 + 39) = 0;
  }
  v6 = (HCURSOR)*((_QWORD *)a1 + 25);
  if ( v6 )
  {
    DestroyCursor(v6);
    *((_QWORD *)a1 + 25) = 0;
  }
  if ( IsWindow(*((HWND *)a1 + 54)) )
    DestroyWindow(*((HWND *)a1 + 54));
  v7 = (HWND)*((_QWORD *)a1 + 52);
  *((_QWORD *)a1 + 54) = 0;
  if ( IsWindow(v7) )
    DestroyWindow(*((HWND *)a1 + 52));
  v8 = (struct _TREEITEM *)*((_QWORD *)a1 + 9);
  *((_QWORD *)a1 + 52) = 0;
  TV_DeleteItem(a1, v8, 6u);
  v9 = *((_QWORD *)a1 + 9);
  if ( v9 )
  {
    Str_Set(v9 + 32, 0);
    HeapFree(*((HANDLE *)a1 + 37), 0, *((LPVOID *)a1 + 9));
    *((_QWORD *)a1 + 9) = 0;
  }
  v10 = (void *)*((_QWORD *)a1 + 71);
  if ( v10 )
  {
    HeapFree(*((HANDLE *)a1 + 37), 0, v10);
    *((_QWORD *)a1 + 71) = 0;
  }
  v11 = (HDC)*((_QWORD *)a1 + 35);
  if ( v11 )
  {
    if ( *((_QWORD *)a1 + 34) )
    {
      SelectObject(v11, *((HGDIOBJ *)a1 + 33));
      DeleteObject(*((HGDIOBJ *)a1 + 34));
      *((_QWORD *)a1 + 34) = 0;
    }
    DeleteDC(*((HDC *)a1 + 35));
    *((_QWORD *)a1 + 35) = 0;
  }
  TV_ExpandoFadeDestroyDCs(a1);
  if ( (*((_BYTE *)a1 + 64) & 0x40) != 0 )
  {
    v12 = (void *)*((_QWORD *)a1 + 29);
    if ( v12 )
    {
      DeleteObject(v12);
      *((_QWORD *)a1 + 29) = 0;
    }
  }
  v13 = (void *)*((_QWORD *)a1 + 31);
  if ( v13 )
  {
    DeleteObject(v13);
    *((_QWORD *)a1 + 31) = 0;
  }
  Str_Set((char *)a1 + 440, 0);
  v14 = *((_QWORD *)a1 + 56);
  if ( v14 )
  {
    FreeProducedString(v14);
    *((_QWORD *)a1 + 56) = 0;
  }
  TV_DeleteHotFonts(a1);
  v15 = (struct _DPA *)*((_QWORD *)a1 + 21);
  if ( v15 )
  {
    DPA_Destroy(v15);
    *((_QWORD *)a1 + 21) = 0;
  }
  v16 = (void *)*((_QWORD *)a1 + 58);
  if ( v16 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)a1 + 73);
  if ( v18 )
    (**v18)(v18, 1);
  v19 = (void *)*((_QWORD *)a1 + 61);
  *((_QWORD *)a1 + 73) = 0;
  if ( v19 )
  {
    CloseThemeData(v19);
    *((_QWORD *)a1 + 61) = 0;
  }
  v20 = (void *)*((_QWORD *)a1 + 74);
  if ( v20 )
  {
    CloseThemeData(v20);
    *((_QWORD *)a1 + 74) = 0;
  }
  SetWindowLongPtrW(v2, 0, 0);
  TV_UnlockTree(a1);
}

```

## disassembly

```asm
0x1800c6aac  push    rbx
0x1800c6aae  push    rbp
0x1800c6aaf  push    rsi
0x1800c6ab0  push    rdi
0x1800c6ab1  sub     rsp, 28h
0x1800c6ab5  and     dword ptr [rcx+40h], 0FFFFFFEFh
0x1800c6ab9  or      edi, 0FFFFFFFFh
0x1800c6abc  mov     rbx, rcx
0x1800c6abf  mov     rsi, [rcx]
0x1800c6ac2  mov     eax, [rcx+40h]
0x1800c6ac5  cmp     [rcx+14Ch], edi
0x1800c6acb  jz      short loc_1800C6ADD
0x1800c6acd  mov     rcx, [rcx+0E0h]; ho
0x1800c6ad4  call    cs:__imp_DeleteObject
0x1800c6ada  mov     eax, [rbx+40h]
0x1800c6add  bts     eax, 12h
0x1800c6ae1  mov     [rbx+14Ch], edi
0x1800c6ae7  mov     rcx, rbx; struct _TREE *
0x1800c6aea  mov     [rbx+40h], eax
0x1800c6aed  call    ?TV_CreateIndentBmps@@YAXPEAU_TREE@@@Z; TV_CreateIndentBmps(_TREE *)
0x1800c6af2  mov     rcx, [rbx+130h]; ho
0x1800c6af9  xor     ebp, ebp
0x1800c6afb  test    rcx, rcx
0x1800c6afe  jz      short loc_1800C6B0D
0x1800c6b00  call    cs:__imp_DeleteObject
0x1800c6b06  mov     [rbx+130h], rbp
0x1800c6b0d  mov     rcx, [rbx+138h]; ho
0x1800c6b14  test    rcx, rcx
0x1800c6b17  jz      short loc_1800C6B26
0x1800c6b19  call    cs:__imp_DeleteObject
0x1800c6b1f  mov     [rbx+138h], rbp
0x1800c6b26  mov     rcx, [rbx+0C8h]; hCursor
0x1800c6b2d  test    rcx, rcx
0x1800c6b30  jz      short loc_1800C6B3F
0x1800c6b32  call    cs:__imp_DestroyCursor
0x1800c6b38  mov     [rbx+0C8h], rbp
0x1800c6b3f  mov     rcx, [rbx+1B0h]; hWnd
0x1800c6b46  call    cs:__imp_IsWindow
0x1800c6b4c  test    eax, eax
0x1800c6b4e  jz      short loc_1800C6B5D
0x1800c6b50  mov     rcx, [rbx+1B0h]; hWnd
0x1800c6b57  call    cs:__imp_DestroyWindow
0x1800c6b5d  mov     rcx, [rbx+1A0h]; hWnd
0x1800c6b64  mov     [rbx+1B0h], rbp
0x1800c6b6b  call    cs:__imp_IsWindow
0x1800c6b71  test    eax, eax
0x1800c6b73  jz      short loc_1800C6B82
0x1800c6b75  mov     rcx, [rbx+1A0h]; hWnd
0x1800c6b7c  call    cs:__imp_DestroyWindow
0x1800c6b82  mov     rdx, [rbx+48h]; struct _TREEITEM *
0x1800c6b86  mov     r8d, 6; unsigned int
0x1800c6b8c  mov     rcx, rbx; struct _TREE *
0x1800c6b8f  mov     [rbx+1A0h], rbp
0x1800c6b96  call    ?TV_DeleteItem@@YAHPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_DeleteItem(_TREE *,_TREEITEM *,uint)
0x1800c6b9b  mov     rcx, [rbx+48h]
0x1800c6b9f  test    rcx, rcx
0x1800c6ba2  jz      short loc_1800C6BC6
0x1800c6ba4  add     rcx, 20h ; ' '
0x1800c6ba8  xor     edx, edx
0x1800c6baa  call    Str_Set
0x1800c6baf  mov     r8, [rbx+48h]; lpMem
0x1800c6bb3  xor     edx, edx; dwFlags
0x1800c6bb5  mov     rcx, [rbx+128h]; hHeap
0x1800c6bbc  call    cs:__imp_HeapFree
0x1800c6bc2  mov     [rbx+48h], rbp
0x1800c6bc6  mov     r8, [rbx+238h]; lpMem
0x1800c6bcd  test    r8, r8
0x1800c6bd0  jz      short loc_1800C6BE8
0x1800c6bd2  mov     rcx, [rbx+128h]; hHeap
0x1800c6bd9  xor     edx, edx; dwFlags
0x1800c6bdb  call    cs:__imp_HeapFree
0x1800c6be1  mov     [rbx+238h], rbp
0x1800c6be8  mov     rcx, [rbx+118h]; hdc
0x1800c6bef  test    rcx, rcx
0x1800c6bf2  jz      short loc_1800C6C32
0x1800c6bf4  cmp     [rbx+110h], rbp
0x1800c6bfb  jz      short loc_1800C6C1E
0x1800c6bfd  mov     rdx, [rbx+108h]; h
0x1800c6c04  call    cs:__imp_SelectObject
0x1800c6c0a  mov     rcx, [rbx+110h]; ho
0x1800c6c11  call    cs:__imp_DeleteObject
0x1800c6c17  mov     [rbx+110h], rbp
0x1800c6c1e  mov     rcx, [rbx+118h]; hdc
0x1800c6c25  call    cs:__imp_DeleteDC
0x1800c6c2b  mov     [rbx+118h], rbp
0x1800c6c32  mov     rcx, rbx; struct _TREE *
0x1800c6c35  call    ?TV_ExpandoFadeDestroyDCs@@YAXPEAU_TREE@@@Z; TV_ExpandoFadeDestroyDCs(_TREE *)
0x1800c6c3a  test    byte ptr [rbx+40h], 40h
0x1800c6c3e  jz      short loc_1800C6C59
0x1800c6c40  mov     rcx, [rbx+0E8h]; ho
0x1800c6c47  test    rcx, rcx
0x1800c6c4a  jz      short loc_1800C6C59
0x1800c6c4c  call    cs:__imp_DeleteObject
0x1800c6c52  mov     [rbx+0E8h], rbp
0x1800c6c59  mov     rcx, [rbx+0F8h]; ho
0x1800c6c60  test    rcx, rcx
0x1800c6c63  jz      short loc_1800C6C72
0x1800c6c65  call    cs:__imp_DeleteObject
0x1800c6c6b  mov     [rbx+0F8h], rbp
0x1800c6c72  lea     rcx, [rbx+1B8h]
0x1800c6c79  xor     edx, edx
0x1800c6c7b  call    Str_Set
0x1800c6c80  mov     rcx, [rbx+1C0h]
0x1800c6c87  test    rcx, rcx
0x1800c6c8a  jz      short loc_1800C6C98
0x1800c6c8c  call    FreeProducedString
0x1800c6c91  mov     [rbx+1C0h], rbp
0x1800c6c98  mov     rcx, rbx; struct _TREE *
0x1800c6c9b  call    ?TV_DeleteHotFonts@@YAXPEAU_TREE@@@Z; TV_DeleteHotFonts(_TREE *)
0x1800c6ca0  mov     rcx, [rbx+0A8h]; hdpa
0x1800c6ca7  test    rcx, rcx
0x1800c6caa  jz      short loc_1800C6CB8
0x1800c6cac  call    DPA_Destroy
0x1800c6cb1  mov     [rbx+0A8h], rbp
0x1800c6cb8  mov     rdi, [rbx+1D0h]
0x1800c6cbf  test    rdi, rdi
0x1800c6cc2  jz      short loc_1800C6CD8
0x1800c6cc4  call    cs:__imp_GetProcessHeap
0x1800c6cca  mov     r8, rdi; lpMem
0x1800c6ccd  xor     edx, edx; dwFlags
0x1800c6ccf  mov     rcx, rax; hHeap
0x1800c6cd2  call    cs:__imp_HeapFree
0x1800c6cd8  mov     rcx, [rbx+248h]
0x1800c6cdf  test    rcx, rcx
0x1800c6ce2  jz      short loc_1800C6CF4
0x1800c6ce4  mov     rax, [rcx]
0x1800c6ce7  mov     edx, 1
0x1800c6cec  mov     rax, [rax]
0x1800c6cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cf4  mov     rcx, [rbx+1E8h]; hTheme
0x1800c6cfb  mov     [rbx+248h], rbp
0x1800c6d02  test    rcx, rcx
0x1800c6d05  jz      short loc_1800C6D14
0x1800c6d07  call    cs:__imp_CloseThemeData
0x1800c6d0d  mov     [rbx+1E8h], rbp
0x1800c6d14  mov     rcx, [rbx+250h]; hTheme
0x1800c6d1b  test    rcx, rcx
0x1800c6d1e  jz      short loc_1800C6D2D
0x1800c6d20  call    cs:__imp_CloseThemeData
0x1800c6d26  mov     [rbx+250h], rbp
0x1800c6d2d  xor     r8d, r8d; dwNewLong
0x1800c6d30  xor     edx, edx; nIndex
0x1800c6d32  mov     rcx, rsi; hWnd
0x1800c6d35  call    cs:__imp_SetWindowLongPtrW
0x1800c6d3b  mov     rcx, rbx; struct _TREE *
0x1800c6d3e  add     rsp, 28h
0x1800c6d42  pop     rdi
0x1800c6d43  pop     rsi
0x1800c6d44  pop     rbp
0x1800c6d45  pop     rbx
0x1800c6d46  jmp     ?TV_UnlockTree@@YAXPEAU_TREE@@@Z; TV_UnlockTree(_TREE *)
```
