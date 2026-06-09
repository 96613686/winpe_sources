# TV_DestroyTree

- ea: `0x18007e9d4`
- end: `0x18007eb81`
- name: `TV_DestroyTree`
- size: `429`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18006bbb0`

## callees

- `0x18002ec60`
- `0x18002fd4c`
- `0x18007b364`
- `0x18007e574`
- `0x18007e5c4`
- `0x18007e9d4`

## import_xrefs

- `GDI32!SelectObject` at `0x18007eaca`
- `GDI32!SelectObject` at `0x18007eaca`
- `GDI32!DeleteObject` at `0x18007e9f8`
- `GDI32!DeleteObject` at `0x18007ead7`
- `GDI32!DeleteObject` at `0x18007eafc`
- `GDI32!DeleteObject` at `0x18007eb0e`
- `GDI32!DeleteObject` at `0x18007e9f8`
- `GDI32!DeleteObject` at `0x18007ead7`
- `GDI32!DeleteObject` at `0x18007eafc`
- `GDI32!DeleteObject` at `0x18007eb0e`
- `GDI32!DeleteDC` at `0x18007eae4`
- `GDI32!DeleteDC` at `0x18007eae4`
- `KERNEL32!HeapFree` at `0x18007eaa7`
- `KERNEL32!HeapFree` at `0x18007eaa7`
- `KERNEL32!LocalFree` at `0x18007eb2e`
- `KERNEL32!LocalFree` at `0x18007eb59`
- `KERNEL32!LocalFree` at `0x18007eb62`
- `KERNEL32!LocalFree` at `0x18007eb2e`
- `KERNEL32!LocalFree` at `0x18007eb59`
- `KERNEL32!LocalFree` at `0x18007eb62`
- `USER32!IsWindow` at `0x18007ea29`
- `USER32!IsWindow` at `0x18007ea52`
- `USER32!IsWindow` at `0x18007ea29`
- `USER32!IsWindow` at `0x18007ea52`
- `USER32!DestroyWindow` at `0x18007ea3a`
- `USER32!DestroyWindow` at `0x18007ea63`
- `USER32!DestroyWindow` at `0x18007ea3a`
- `USER32!DestroyWindow` at `0x18007ea63`
- `USER32!SetWindowLongPtrW` at `0x18007eb7a`
- `USER32!DestroyCursor` at `0x18007ea1c`
- `USER32!DestroyCursor` at `0x18007ea1c`

## pseudocode

```c
LONG_PTR __fastcall TV_DestroyTree(char *hMem)
{
  HWND v2; // rdi
  HCURSOR v3; // rcx
  HWND v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  HDC v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  struct _DPA *v11; // rcx
  void *v12; // rcx

  *((_DWORD *)hMem + 14) &= ~0x10u;
  v2 = *(HWND *)hMem;
  if ( *((_DWORD *)hMem + 71) != -1 )
    DeleteObject(*((HGDIOBJ *)hMem + 24));
  *((_DWORD *)hMem + 71) = -1;
  TV_CreateIndentBmps((__int64)hMem);
  v3 = (HCURSOR)*((_QWORD *)hMem + 21);
  if ( v3 )
    DestroyCursor(v3);
  if ( IsWindow(*((HWND *)hMem + 45)) )
    DestroyWindow(*((HWND *)hMem + 45));
  v4 = (HWND)*((_QWORD *)hMem + 43);
  *((_QWORD *)hMem + 45) = 0;
  if ( IsWindow(v4) )
    DestroyWindow(*((HWND *)hMem + 43));
  v5 = *((_QWORD *)hMem + 8);
  *((_QWORD *)hMem + 43) = 0;
  TV_DeleteItem(hMem, v5, 6);
  v6 = *((_QWORD *)hMem + 8);
  if ( v6 )
  {
    Str_Set(v6 + 24, 0);
    HeapFree(*((HANDLE *)hMem + 33), 0, *((LPVOID *)hMem + 8));
  }
  v7 = (HDC)*((_QWORD *)hMem + 31);
  if ( v7 )
  {
    if ( *((_QWORD *)hMem + 30) )
    {
      SelectObject(v7, *((HGDIOBJ *)hMem + 29));
      DeleteObject(*((HGDIOBJ *)hMem + 30));
    }
    DeleteDC(*((HDC *)hMem + 31));
  }
  if ( (hMem[56] & 0x40) != 0 )
  {
    v8 = (void *)*((_QWORD *)hMem + 25);
    if ( v8 )
      DeleteObject(v8);
  }
  v9 = (void *)*((_QWORD *)hMem + 27);
  if ( v9 )
    DeleteObject(v9);
  Str_Set(hMem + 368, 0);
  v10 = (void *)*((_QWORD *)hMem + 47);
  if ( v10 )
    LocalFree(v10);
  TV_DeleteHotFonts(hMem);
  v11 = (struct _DPA *)*((_QWORD *)hMem + 18);
  if ( v11 )
    DPA_Destroy(v11);
  v12 = (void *)*((_QWORD *)hMem + 49);
  if ( v12 )
    LocalFree(v12);
  LocalFree(hMem);
  return SetWindowLongPtrW(v2, 0, 0);
}

```

## disassembly

```asm
0x18007e9d4  mov     [rsp+arg_0], rbx
0x18007e9d9  push    rdi
0x18007e9da  sub     rsp, 20h
0x18007e9de  and     dword ptr [rcx+38h], 0FFFFFFEFh
0x18007e9e2  mov     rbx, rcx
0x18007e9e5  cmp     dword ptr [rcx+11Ch], 0FFFFFFFFh
0x18007e9ec  mov     rdi, [rcx]
0x18007e9ef  jz      short loc_18007E9FE
0x18007e9f1  mov     rcx, [rcx+0C0h]; ho
0x18007e9f8  call    cs:__imp_DeleteObject
0x18007e9fe  mov     rcx, rbx
0x18007ea01  mov     dword ptr [rbx+11Ch], 0FFFFFFFFh
0x18007ea0b  call    TV_CreateIndentBmps
0x18007ea10  mov     rcx, [rbx+0A8h]; hCursor
0x18007ea17  test    rcx, rcx
0x18007ea1a  jz      short loc_18007EA22
0x18007ea1c  call    cs:__imp_DestroyCursor
0x18007ea22  mov     rcx, [rbx+168h]; hWnd
0x18007ea29  call    cs:__imp_IsWindow
0x18007ea2f  test    eax, eax
0x18007ea31  jz      short loc_18007EA40
0x18007ea33  mov     rcx, [rbx+168h]; hWnd
0x18007ea3a  call    cs:__imp_DestroyWindow
0x18007ea40  mov     rcx, [rbx+158h]; hWnd
0x18007ea47  mov     qword ptr [rbx+168h], 0
0x18007ea52  call    cs:__imp_IsWindow
0x18007ea58  test    eax, eax
0x18007ea5a  jz      short loc_18007EA69
0x18007ea5c  mov     rcx, [rbx+158h]; hWnd
0x18007ea63  call    cs:__imp_DestroyWindow
0x18007ea69  mov     rdx, [rbx+40h]
0x18007ea6d  mov     r8d, 6
0x18007ea73  mov     rcx, rbx
0x18007ea76  mov     qword ptr [rbx+158h], 0
0x18007ea81  call    TV_DeleteItem
0x18007ea86  mov     rcx, [rbx+40h]
0x18007ea8a  test    rcx, rcx
0x18007ea8d  jz      short loc_18007EAAD
0x18007ea8f  add     rcx, 18h
0x18007ea93  xor     edx, edx
0x18007ea95  call    Str_Set
0x18007ea9a  mov     r8, [rbx+40h]; lpMem
0x18007ea9e  xor     edx, edx; dwFlags
0x18007eaa0  mov     rcx, [rbx+108h]; hHeap
0x18007eaa7  call    cs:__imp_HeapFree
0x18007eaad  mov     rcx, [rbx+0F8h]; hdc
0x18007eab4  test    rcx, rcx
0x18007eab7  jz      short loc_18007EAEA
0x18007eab9  cmp     qword ptr [rbx+0F0h], 0
0x18007eac1  jz      short loc_18007EADD
0x18007eac3  mov     rdx, [rbx+0E8h]; h
0x18007eaca  call    cs:__imp_SelectObject
0x18007ead0  mov     rcx, [rbx+0F0h]; ho
0x18007ead7  call    cs:__imp_DeleteObject
0x18007eadd  mov     rcx, [rbx+0F8h]; hdc
0x18007eae4  call    cs:__imp_DeleteDC
0x18007eaea  test    byte ptr [rbx+38h], 40h
0x18007eaee  jz      short loc_18007EB02
0x18007eaf0  mov     rcx, [rbx+0C8h]; ho
0x18007eaf7  test    rcx, rcx
0x18007eafa  jz      short loc_18007EB02
0x18007eafc  call    cs:__imp_DeleteObject
0x18007eb02  mov     rcx, [rbx+0D8h]; ho
0x18007eb09  test    rcx, rcx
0x18007eb0c  jz      short loc_18007EB14
0x18007eb0e  call    cs:__imp_DeleteObject
0x18007eb14  lea     rcx, [rbx+170h]
0x18007eb1b  xor     edx, edx
0x18007eb1d  call    Str_Set
0x18007eb22  mov     rcx, [rbx+178h]; hMem
0x18007eb29  test    rcx, rcx
0x18007eb2c  jz      short loc_18007EB34
0x18007eb2e  call    cs:__imp_LocalFree
0x18007eb34  mov     rcx, rbx
0x18007eb37  call    TV_DeleteHotFonts
0x18007eb3c  mov     rcx, [rbx+90h]; hdpa
0x18007eb43  test    rcx, rcx
0x18007eb46  jz      short loc_18007EB4D
0x18007eb48  call    DPA_Destroy
0x18007eb4d  mov     rcx, [rbx+188h]; hMem
0x18007eb54  test    rcx, rcx
0x18007eb57  jz      short loc_18007EB5F
0x18007eb59  call    cs:__imp_LocalFree
0x18007eb5f  mov     rcx, rbx; hMem
0x18007eb62  call    cs:__imp_LocalFree
0x18007eb68  xor     r8d, r8d
0x18007eb6b  xor     edx, edx
0x18007eb6d  mov     rcx, rdi
0x18007eb70  mov     rbx, [rsp+28h+arg_0]
0x18007eb75  add     rsp, 20h
0x18007eb79  pop     rdi
0x18007eb7a  jmp     cs:__imp_SetWindowLongPtrW
```
