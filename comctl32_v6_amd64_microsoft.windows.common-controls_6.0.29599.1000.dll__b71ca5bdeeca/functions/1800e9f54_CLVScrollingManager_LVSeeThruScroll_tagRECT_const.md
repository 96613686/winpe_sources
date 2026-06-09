# CLVScrollingManager::LVSeeThruScroll(tagRECT const *)

- ea: `0x1800e9f54`
- end: `0x1800ea05e`
- name: `?LVSeeThruScroll@CLVScrollingManager@@QEAAXPEBUtagRECT@@@Z`
- size: `266`
- prototype: `void __fastcall(CLVScrollingManager *__hidden this, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003e490`
- `0x1801c6f50`

## callees

- `0x1800e9f54`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800ea057`
- `GDI32!SelectObject` at `0x1800e9fdb`
- `GDI32!SelectObject` at `0x1800e9fdb`
- `GDI32!DeleteDC` at `0x1800ea03e`
- `GDI32!DeleteDC` at `0x1800ea03e`
- `GDI32!CreateCompatibleDC` at `0x1800e9faf`
- `GDI32!CreateCompatibleDC` at `0x1800e9faf`
- `GDI32!CreateCompatibleBitmap` at `0x1800e9fcc`
- `GDI32!CreateCompatibleBitmap` at `0x1800e9fcc`
- `GDI32!BitBlt` at `0x1800ea024`
- `GDI32!BitBlt` at `0x1800ea024`
- `USER32!GetDC` at `0x1800e9f73`
- `USER32!GetDC` at `0x1800e9f73`
- `USER32!SendMessageW` at `0x1800e9ff7`
- `USER32!SendMessageW` at `0x1800e9ff7`
- `USER32!ReleaseDC` at `0x1800ea035`
- `USER32!ReleaseDC` at `0x1800ea035`

## pseudocode

```c
void __fastcall CLVScrollingManager::LVSeeThruScroll(CLVScrollingManager *this, const struct tagRECT *a2)
{
  HDC DC; // rax
  HDC v5; // r13
  __int64 v6; // rdx
  LONG y1; // r15d
  LONG x1; // r12d
  int v9; // esi
  int cy; // ebp
  HDC hdcSrc; // rdi
  HBITMAP CompatibleBitmap; // rbx

  DC = GetDC(*(HWND *)(*((_QWORD *)this + 3) + 96LL));
  v5 = DC;
  if ( a2 )
  {
    x1 = a2->left;
    v9 = a2->right - a2->left;
    y1 = a2->top;
    cy = a2->bottom - y1;
  }
  else
  {
    v6 = *((_QWORD *)this + 3);
    y1 = 0;
    x1 = 0;
    v9 = *(_DWORD *)(v6 + 220);
    cy = *(_DWORD *)(v6 + 224);
  }
  hdcSrc = CreateCompatibleDC(DC);
  CompatibleBitmap = CreateCompatibleBitmap(
                       v5,
                       *(_DWORD *)(*((_QWORD *)this + 3) + 220LL),
                       *(_DWORD *)(*((_QWORD *)this + 3) + 224LL));
  SelectObject(hdcSrc, CompatibleBitmap);
  SendMessageW(*(HWND *)(*((_QWORD *)this + 3) + 96LL), 0x317u, (WPARAM)hdcSrc, 12);
  BitBlt(v5, x1, y1, v9, cy, hdcSrc, x1, y1, 0xCC0020u);
  ReleaseDC(*(HWND *)(*((_QWORD *)this + 3) + 96LL), v5);
  DeleteDC(hdcSrc);
  DeleteObject(CompatibleBitmap);
}

```

## disassembly

```asm
0x1800e9f54  push    rbx
0x1800e9f56  push    rbp
0x1800e9f57  push    rsi
0x1800e9f58  push    rdi
0x1800e9f59  push    r12
0x1800e9f5b  push    r13
0x1800e9f5d  push    r14
0x1800e9f5f  push    r15
0x1800e9f61  sub     rsp, 58h
0x1800e9f65  mov     r14, rcx
0x1800e9f68  mov     rbx, rdx
0x1800e9f6b  mov     rcx, [rcx+18h]
0x1800e9f6f  mov     rcx, [rcx+60h]; hWnd
0x1800e9f73  call    cs:__imp_GetDC
0x1800e9f79  mov     r13, rax
0x1800e9f7c  test    rbx, rbx
0x1800e9f7f  jnz     short loc_1800E9F99
0x1800e9f81  mov     rdx, [r14+18h]
0x1800e9f85  xor     r15d, r15d
0x1800e9f88  xor     r12d, r12d
0x1800e9f8b  mov     esi, [rdx+0DCh]
0x1800e9f91  mov     ebp, [rdx+0E0h]
0x1800e9f97  jmp     short loc_1800E9FAC
0x1800e9f99  mov     esi, [rbx+8]
0x1800e9f9c  mov     r12d, [rbx]
0x1800e9f9f  sub     esi, r12d
0x1800e9fa2  mov     ebp, [rbx+0Ch]
0x1800e9fa5  mov     r15d, [rbx+4]
0x1800e9fa9  sub     ebp, r15d
0x1800e9fac  mov     rcx, r13; hdc
0x1800e9faf  call    cs:__imp_CreateCompatibleDC
0x1800e9fb5  mov     rdx, [r14+18h]
0x1800e9fb9  mov     rcx, r13; hdc
0x1800e9fbc  mov     rdi, rax
0x1800e9fbf  mov     r8d, [rdx+0E0h]; cy
0x1800e9fc6  mov     edx, [rdx+0DCh]; cx
0x1800e9fcc  call    cs:__imp_CreateCompatibleBitmap
0x1800e9fd2  mov     rdx, rax; h
0x1800e9fd5  mov     rcx, rdi; hdc
0x1800e9fd8  mov     rbx, rax
0x1800e9fdb  call    cs:__imp_SelectObject
0x1800e9fe1  mov     rcx, [r14+18h]
0x1800e9fe5  mov     r9d, 0Ch; lParam
0x1800e9feb  mov     r8, rdi; wParam
0x1800e9fee  mov     edx, 317h; Msg
0x1800e9ff3  mov     rcx, [rcx+60h]; hWnd
0x1800e9ff7  call    cs:__imp_SendMessageW
0x1800e9ffd  mov     [rsp+98h+rop], 0CC0020h; rop
0x1800ea005  mov     r9d, esi; cx
0x1800ea008  mov     [rsp+98h+y1], r15d; y1
0x1800ea00d  mov     r8d, r15d; y
0x1800ea010  mov     [rsp+98h+x1], r12d; x1
0x1800ea015  mov     edx, r12d; x
0x1800ea018  mov     [rsp+98h+hdcSrc], rdi; hdcSrc
0x1800ea01d  mov     rcx, r13; hdc
0x1800ea020  mov     [rsp+98h+cy], ebp; cy
0x1800ea024  call    cs:__imp_BitBlt
0x1800ea02a  mov     rcx, [r14+18h]
0x1800ea02e  mov     rdx, r13; hDC
0x1800ea031  mov     rcx, [rcx+60h]; hWnd
0x1800ea035  call    cs:__imp_ReleaseDC
0x1800ea03b  mov     rcx, rdi; hdc
0x1800ea03e  call    cs:__imp_DeleteDC
0x1800ea044  mov     rcx, rbx
0x1800ea047  add     rsp, 58h
0x1800ea04b  pop     r15
0x1800ea04d  pop     r14
0x1800ea04f  pop     r13
0x1800ea051  pop     r12
0x1800ea053  pop     rdi
0x1800ea054  pop     rsi
0x1800ea055  pop     rbp
0x1800ea056  pop     rbx
0x1800ea057  jmp     cs:__imp_DeleteObject
```
