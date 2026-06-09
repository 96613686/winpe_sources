# MCNcDestroyHandler

- ea: `0x1800451c8`
- end: `0x180045298`
- name: `MCNcDestroyHandler`
- size: `208`
- prototype: `__int64 __fastcall(HWND hWnd, HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046d90`

## callees

- `0x180042f3c`
- `0x1800451c8`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800451f2`
- `GDI32!DeleteObject` at `0x180045204`
- `GDI32!DeleteObject` at `0x1800451f2`
- `GDI32!DeleteObject` at `0x180045204`
- `KERNEL32!LocalFree` at `0x180045267`
- `KERNEL32!LocalFree` at `0x180045267`
- `USER32!SetWindowLongPtrW` at `0x180045275`
- `USER32!SetWindowLongPtrW` at `0x180045275`
- `USER32!DefWindowProcW` at `0x180045291`
- `USER32!KillTimer` at `0x18004523d`
- `USER32!KillTimer` at `0x180045252`
- `USER32!KillTimer` at `0x18004523d`
- `USER32!KillTimer` at `0x180045252`
- `USER32!DestroyMenu` at `0x180045216`
- `USER32!DestroyMenu` at `0x180045228`
- `USER32!DestroyMenu` at `0x180045216`
- `USER32!DestroyMenu` at `0x180045228`

## pseudocode

```c
LRESULT __fastcall MCNcDestroyHandler(HWND hWnd, HWND *hMem, WPARAM a3, LPARAM a4)
{
  HWND v8; // rcx
  HWND v9; // rcx
  HMENU v10; // rcx
  HMENU v11; // rcx
  UINT_PTR v12; // rdx
  UINT_PTR v13; // rdx

  if ( hMem )
  {
    v8 = hMem[208];
    if ( v8 )
      DeleteObject(v8);
    v9 = hMem[210];
    if ( v9 )
      DeleteObject(v9);
    v10 = (HMENU)hMem[219];
    if ( v10 )
      DestroyMenu(v10);
    v11 = (HMENU)hMem[220];
    if ( v11 )
      DestroyMenu(v11);
    v12 = (UINT_PTR)hMem[246];
    if ( v12 )
      KillTimer(*hMem, v12);
    v13 = (UINT_PTR)hMem[247];
    if ( v13 )
      KillTimer(*hMem, v13);
    MCFreeCalendarInfo(hMem + 295);
    LocalFree(hMem);
  }
  SetWindowLongPtrW(hWnd, 0, 0);
  return DefWindowProcW(hWnd, 0x82u, a3, a4);
}

```

## disassembly

```asm
0x1800451c8  push    rbx
0x1800451ca  push    rbp
0x1800451cb  push    rsi
0x1800451cc  push    rdi
0x1800451cd  sub     rsp, 28h
0x1800451d1  mov     rsi, r9
0x1800451d4  mov     rbp, r8
0x1800451d7  mov     rbx, rdx
0x1800451da  mov     rdi, rcx
0x1800451dd  test    rdx, rdx
0x1800451e0  jz      loc_18004526D
0x1800451e6  mov     rcx, [rdx+680h]; ho
0x1800451ed  test    rcx, rcx
0x1800451f0  jz      short loc_1800451F8
0x1800451f2  call    cs:__imp_DeleteObject
0x1800451f8  mov     rcx, [rbx+690h]; ho
0x1800451ff  test    rcx, rcx
0x180045202  jz      short loc_18004520A
0x180045204  call    cs:__imp_DeleteObject
0x18004520a  mov     rcx, [rbx+6D8h]; hMenu
0x180045211  test    rcx, rcx
0x180045214  jz      short loc_18004521C
0x180045216  call    cs:__imp_DestroyMenu
0x18004521c  mov     rcx, [rbx+6E0h]; hMenu
0x180045223  test    rcx, rcx
0x180045226  jz      short loc_18004522E
0x180045228  call    cs:__imp_DestroyMenu
0x18004522e  mov     rdx, [rbx+7B0h]; uIDEvent
0x180045235  test    rdx, rdx
0x180045238  jz      short loc_180045243
0x18004523a  mov     rcx, [rbx]; hWnd
0x18004523d  call    cs:__imp_KillTimer
0x180045243  mov     rdx, [rbx+7B8h]; uIDEvent
0x18004524a  test    rdx, rdx
0x18004524d  jz      short loc_180045258
0x18004524f  mov     rcx, [rbx]; hWnd
0x180045252  call    cs:__imp_KillTimer
0x180045258  lea     rcx, [rbx+938h]
0x18004525f  call    MCFreeCalendarInfo
0x180045264  mov     rcx, rbx; hMem
0x180045267  call    cs:__imp_LocalFree
0x18004526d  xor     r8d, r8d; dwNewLong
0x180045270  xor     edx, edx; nIndex
0x180045272  mov     rcx, rdi; hWnd
0x180045275  call    cs:__imp_SetWindowLongPtrW
0x18004527b  mov     r9, rsi
0x18004527e  mov     r8, rbp
0x180045281  mov     edx, 82h
0x180045286  mov     rcx, rdi
0x180045289  add     rsp, 28h
0x18004528d  pop     rdi
0x18004528e  pop     rsi
0x18004528f  pop     rbp
0x180045290  pop     rbx
0x180045291  jmp     cs:__imp_DefWindowProcW
```
