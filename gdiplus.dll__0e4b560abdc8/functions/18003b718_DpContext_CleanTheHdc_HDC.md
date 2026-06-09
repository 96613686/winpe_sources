# DpContext::CleanTheHdc(HDC__ *)

- ea: `0x18003b718`
- end: `0x18003b963`
- name: `?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z`
- size: `587`
- prototype: `void(DpContext *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005364`
- `0x180007458`
- `0x180017f74`
- `0x18003b634`

## callees

- `0x18003b718`

## import_xrefs

- `GDI32!GetClipRgn` at `0x18003b8cd`
- `GDI32!GetClipRgn` at `0x18003b8cd`
- `GDI32!ModifyWorldTransform` at `0x18003b7bd`
- `GDI32!ModifyWorldTransform` at `0x18003b7bd`
- `GDI32!SetROP2` at `0x18003b7a9`
- `GDI32!SetROP2` at `0x18003b952`
- `GDI32!SetROP2` at `0x18003b7a9`
- `GDI32!SetROP2` at `0x18003b952`
- `GDI32!GetROP2` at `0x18003b869`
- `GDI32!GetROP2` at `0x18003b869`
- `GDI32!GetWindowOrgEx` at `0x18003b84a`
- `GDI32!GetWindowOrgEx` at `0x18003b84a`
- `GDI32!GetMapMode` at `0x18003b7f2`
- `GDI32!GetMapMode` at `0x18003b7f2`
- `GDI32!SelectClipRgn` at `0x18003b7ce`
- `GDI32!SelectClipRgn` at `0x18003b7ce`
- `GDI32!SetViewportOrgEx` at `0x18003b77e`
- `GDI32!SetViewportOrgEx` at `0x18003b91d`
- `GDI32!SetViewportOrgEx` at `0x18003b77e`
- `GDI32!SetViewportOrgEx` at `0x18003b91d`
- `GDI32!SetWindowOrgEx` at `0x18003b795`
- `GDI32!SetWindowOrgEx` at `0x18003b939`
- `GDI32!SetWindowOrgEx` at `0x18003b795`
- `GDI32!SetWindowOrgEx` at `0x18003b939`
- `GDI32!SetMapMode` at `0x18003b767`
- `GDI32!SetMapMode` at `0x18003b904`
- `GDI32!SetMapMode` at `0x18003b767`
- `GDI32!SetMapMode` at `0x18003b904`
- `GDI32!DeleteObject` at `0x18003b8de`
- `GDI32!DeleteObject` at `0x18003b8de`
- `GDI32!GetViewportOrgEx` at `0x18003b813`
- `GDI32!GetViewportOrgEx` at `0x18003b813`
- `GDI32!CreateRectRgn` at `0x18003b882`
- `GDI32!CreateRectRgn` at `0x18003b882`
- `GDI32!SetICMMode` at `0x18003b749`
- `GDI32!SetICMMode` at `0x18003b749`

## pseudocode

```c
void __fastcall DpContext::CleanTheHdc(DpContext *this, HDC a2)
{
  bool v3; // zf
  int v6; // edx
  int MapMode; // eax
  int v8; // r15d
  BOOL v9; // r14d
  BOOL v10; // ebp
  int ROP2; // r12d
  HRGN RectRgn; // rax
  HRGN v13; // rsi
  BOOL v14; // esi
  int ClipRgn; // ebx
  tagPOINT point; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 160) == 1;
  v6 = 2;
  if ( !v3 )
    v6 = 1;
  SetICMMode(a2, v6);
  if ( !*((_DWORD *)this + 161) )
  {
    SetMapMode(a2, 1);
    SetViewportOrgEx(a2, 0, 0, 0);
    SetWindowOrgEx(a2, 0, 0, 0);
    SetROP2(a2, 13);
    ModifyWorldTransform(a2, 0, 1u);
LABEL_5:
    SelectClipRgn(a2, 0);
    return;
  }
  MapMode = GetMapMode(a2);
  point.x = 0;
  point.y = 0;
  v8 = MapMode;
  GetViewportOrgEx(a2, &point);
  v9 = point.x || point.y;
  point.x = 0;
  point.y = 0;
  GetWindowOrgEx(a2, &point);
  v10 = point.x || point.y;
  ROP2 = GetROP2(a2);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v13 = RectRgn;
  if ( RectRgn )
  {
    ClipRgn = GetClipRgn(a2, RectRgn);
    DeleteObject(v13);
    v14 = ClipRgn != 0;
  }
  else
  {
    v14 = 1;
  }
  if ( v8 != 1 )
    SetMapMode(a2, 1);
  if ( v9 )
    SetViewportOrgEx(a2, 0, 0, 0);
  if ( v10 )
    SetWindowOrgEx(a2, 0, 0, 0);
  if ( ROP2 != 13 )
    SetROP2(a2, 13);
  if ( v14 )
    goto LABEL_5;
}

```

## disassembly

```asm
0x18003b718  mov     [rsp+arg_8], rbx
0x18003b71d  mov     [rsp+arg_10], rbp
0x18003b722  push    rsi
0x18003b723  push    rdi
0x18003b724  push    r12
0x18003b726  push    r14
0x18003b728  push    r15
0x18003b72a  sub     rsp, 20h
0x18003b72e  mov     esi, 1
0x18003b733  mov     rbx, rcx
0x18003b736  cmp     [rcx+280h], esi
0x18003b73c  mov     rdi, rdx
0x18003b73f  mov     rcx, rdx; hdc
0x18003b742  lea     edx, [rsi+1]
0x18003b745  jz      short loc_18003B749
0x18003b747  mov     edx, esi; mode
0x18003b749  call    cs:__imp_SetICMMode
0x18003b750  nop     dword ptr [rax+rax+00h]
0x18003b755  cmp     dword ptr [rbx+284h], 0
0x18003b75c  mov     rcx, rdi; hdc
0x18003b75f  jnz     loc_18003B7F2
0x18003b765  mov     edx, esi; iMode
0x18003b767  call    cs:__imp_SetMapMode
0x18003b76e  nop     dword ptr [rax+rax+00h]
0x18003b773  xor     r9d, r9d; lppt
0x18003b776  xor     r8d, r8d; y
0x18003b779  xor     edx, edx; x
0x18003b77b  mov     rcx, rdi; hdc
0x18003b77e  call    cs:__imp_SetViewportOrgEx
0x18003b785  nop     dword ptr [rax+rax+00h]
0x18003b78a  xor     r9d, r9d; lppt
0x18003b78d  xor     r8d, r8d; y
0x18003b790  xor     edx, edx; x
0x18003b792  mov     rcx, rdi; hdc
0x18003b795  call    cs:__imp_SetWindowOrgEx
0x18003b79c  nop     dword ptr [rax+rax+00h]
0x18003b7a1  mov     edx, 0Dh; rop2
0x18003b7a6  mov     rcx, rdi; hdc
0x18003b7a9  call    cs:__imp_SetROP2
0x18003b7b0  nop     dword ptr [rax+rax+00h]
0x18003b7b5  mov     r8d, esi; mode
0x18003b7b8  xor     edx, edx; lpxf
0x18003b7ba  mov     rcx, rdi; hdc
0x18003b7bd  call    cs:__imp_ModifyWorldTransform
0x18003b7c4  nop     dword ptr [rax+rax+00h]
0x18003b7c9  xor     edx, edx; hrgn
0x18003b7cb  mov     rcx, rdi; hdc
0x18003b7ce  call    cs:__imp_SelectClipRgn
0x18003b7d5  nop     dword ptr [rax+rax+00h]
0x18003b7da  mov     rbx, [rsp+48h+arg_8]
0x18003b7df  mov     rbp, [rsp+48h+arg_10]
0x18003b7e4  add     rsp, 20h
0x18003b7e8  pop     r15
0x18003b7ea  pop     r14
0x18003b7ec  pop     r12
0x18003b7ee  pop     rdi
0x18003b7ef  pop     rsi
0x18003b7f0  retn
0x18003b7f2  call    cs:__imp_GetMapMode
0x18003b7f9  nop     dword ptr [rax+rax+00h]
0x18003b7fe  and     [rsp+48h+point.x], 0
0x18003b803  lea     rdx, [rsp+48h+point]; lppoint
0x18003b808  and     [rsp+48h+point.y], 0
0x18003b80d  mov     rcx, rdi; hdc
0x18003b810  mov     r15d, eax
0x18003b813  call    cs:__imp_GetViewportOrgEx
0x18003b81a  nop     dword ptr [rax+rax+00h]
0x18003b81f  cmp     [rsp+48h+point.x], 0
0x18003b824  jnz     loc_18003B8F4
0x18003b82a  cmp     [rsp+48h+point.y], 0
0x18003b82f  jnz     loc_18003B8F4
0x18003b835  xor     r14d, r14d
0x18003b838  and     [rsp+48h+point.x], 0
0x18003b83d  lea     rdx, [rsp+48h+point]; lppoint
0x18003b842  and     [rsp+48h+point.y], 0
0x18003b847  mov     rcx, rdi; hdc
0x18003b84a  call    cs:__imp_GetWindowOrgEx
0x18003b851  nop     dword ptr [rax+rax+00h]
0x18003b856  cmp     [rsp+48h+point.x], 0
0x18003b85b  jnz     short loc_18003B8C3
0x18003b85d  cmp     [rsp+48h+point.y], 0
0x18003b862  jnz     short loc_18003B8C3
0x18003b864  xor     ebp, ebp
0x18003b866  mov     rcx, rdi; hdc
0x18003b869  call    cs:__imp_GetROP2
0x18003b870  nop     dword ptr [rax+rax+00h]
0x18003b875  xor     r9d, r9d; y2
0x18003b878  xor     r8d, r8d; x2
0x18003b87b  xor     edx, edx; y1
0x18003b87d  xor     ecx, ecx; x1
0x18003b87f  mov     r12d, eax
0x18003b882  call    cs:__imp_CreateRectRgn
0x18003b889  nop     dword ptr [rax+rax+00h]
0x18003b88e  mov     rsi, rax
0x18003b891  test    rax, rax
0x18003b894  jnz     short loc_18003B8C7
0x18003b896  lea     esi, [rax+1]
0x18003b899  cmp     r15d, 1
0x18003b89d  jnz     short loc_18003B8FC
0x18003b89f  test    r14d, r14d
0x18003b8a2  jnz     short loc_18003B912
0x18003b8a4  test    ebp, ebp
0x18003b8a6  jnz     loc_18003B92E
0x18003b8ac  cmp     r12d, 0Dh
0x18003b8b0  jnz     loc_18003B94A
0x18003b8b6  test    esi, esi
0x18003b8b8  jnz     loc_18003B7C9
0x18003b8be  jmp     loc_18003B7DA
0x18003b8c3  mov     ebp, esi
0x18003b8c5  jmp     short loc_18003B866
0x18003b8c7  mov     rdx, rsi; hrgn
0x18003b8ca  mov     rcx, rdi; hdc
0x18003b8cd  call    cs:__imp_GetClipRgn
0x18003b8d4  nop     dword ptr [rax+rax+00h]
0x18003b8d9  mov     rcx, rsi; ho
0x18003b8dc  mov     ebx, eax
0x18003b8de  call    cs:__imp_DeleteObject
0x18003b8e5  nop     dword ptr [rax+rax+00h]
0x18003b8ea  xor     esi, esi
0x18003b8ec  test    ebx, ebx
0x18003b8ee  setnz   sil
0x18003b8f2  jmp     short loc_18003B899
0x18003b8f4  mov     r14d, esi
0x18003b8f7  jmp     loc_18003B838
0x18003b8fc  mov     edx, 1; iMode
0x18003b901  mov     rcx, rdi; hdc
0x18003b904  call    cs:__imp_SetMapMode
0x18003b90b  nop     dword ptr [rax+rax+00h]
0x18003b910  jmp     short loc_18003B89F
0x18003b912  xor     r9d, r9d; lppt
0x18003b915  xor     r8d, r8d; y
0x18003b918  xor     edx, edx; x
0x18003b91a  mov     rcx, rdi; hdc
0x18003b91d  call    cs:__imp_SetViewportOrgEx
0x18003b924  nop     dword ptr [rax+rax+00h]
0x18003b929  jmp     loc_18003B8A4
0x18003b92e  xor     r9d, r9d; lppt
0x18003b931  xor     r8d, r8d; y
0x18003b934  xor     edx, edx; x
0x18003b936  mov     rcx, rdi; hdc
0x18003b939  call    cs:__imp_SetWindowOrgEx
0x18003b940  nop     dword ptr [rax+rax+00h]
0x18003b945  jmp     loc_18003B8AC
0x18003b94a  mov     edx, 0Dh; rop2
0x18003b94f  mov     rcx, rdi; hdc
0x18003b952  call    cs:__imp_SetROP2
0x18003b959  nop     dword ptr [rax+rax+00h]
0x18003b95e  jmp     loc_18003B8B6
```
