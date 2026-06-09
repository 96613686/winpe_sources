# DpContext::CleanTheHdc(HDC__ *)

- ea: `0x18002f21c`
- end: `0x18002f456`
- name: `?CleanTheHdc@DpContext@@QEAAXPEAUHDC__@@@Z`
- size: `570`
- prototype: `void(DpContext *__hidden this, HDC)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f12c`
- `0x18002fb10`
- `0x180041178`
- `0x18004341c`

## callees

- `0x18002f21c`

## import_xrefs

- `GDI32!GetClipRgn` at `0x18002f3c6`
- `GDI32!GetClipRgn` at `0x18002f3c6`
- `GDI32!ModifyWorldTransform` at `0x18002f2c1`
- `GDI32!ModifyWorldTransform` at `0x18002f2c1`
- `GDI32!SetROP2` at `0x18002f2ad`
- `GDI32!SetROP2` at `0x18002f445`
- `GDI32!SetROP2` at `0x18002f2ad`
- `GDI32!SetROP2` at `0x18002f445`
- `GDI32!GetROP2` at `0x18002f36a`
- `GDI32!GetROP2` at `0x18002f36a`
- `GDI32!GetWindowOrgEx` at `0x18002f34b`
- `GDI32!GetWindowOrgEx` at `0x18002f34b`
- `GDI32!GetMapMode` at `0x18002f2f6`
- `GDI32!GetMapMode` at `0x18002f2f6`
- `GDI32!SelectClipRgn` at `0x18002f2d2`
- `GDI32!SelectClipRgn` at `0x18002f2d2`
- `GDI32!SetViewportOrgEx` at `0x18002f282`
- `GDI32!SetViewportOrgEx` at `0x18002f413`
- `GDI32!SetViewportOrgEx` at `0x18002f282`
- `GDI32!SetViewportOrgEx` at `0x18002f413`
- `GDI32!SetWindowOrgEx` at `0x18002f299`
- `GDI32!SetWindowOrgEx` at `0x18002f42c`
- `GDI32!SetWindowOrgEx` at `0x18002f299`
- `GDI32!SetWindowOrgEx` at `0x18002f42c`
- `GDI32!SetMapMode` at `0x18002f26b`
- `GDI32!SetMapMode` at `0x18002f3fa`
- `GDI32!SetMapMode` at `0x18002f26b`
- `GDI32!SetMapMode` at `0x18002f3fa`
- `GDI32!DeleteObject` at `0x18002f3dd`
- `GDI32!DeleteObject` at `0x18002f3dd`
- `GDI32!GetViewportOrgEx` at `0x18002f316`
- `GDI32!GetViewportOrgEx` at `0x18002f316`
- `GDI32!CreateRectRgn` at `0x18002f383`
- `GDI32!CreateRectRgn` at `0x18002f383`
- `GDI32!SetICMMode` at `0x18002f24d`
- `GDI32!SetICMMode` at `0x18002f24d`

## pseudocode

```c
void __fastcall DpContext::CleanTheHdc(DpContext *this, HDC a2)
{
  BOOL v2; // ebp
  bool v4; // zf
  int v7; // edx
  int MapMode; // eax
  int v9; // r15d
  BOOL v10; // esi
  BOOL v11; // edi
  int ROP2; // r12d
  HRGN RectRgn; // rax
  HRGN v14; // r14
  struct tagPOINT point; // [rsp+50h] [rbp+8h] BYREF

  v2 = 1;
  v4 = *((_DWORD *)this + 160) == 1;
  v7 = 2;
  if ( !v4 )
    v7 = 1;
  SetICMMode(a2, v7);
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
  point = 0;
  v9 = MapMode;
  GetViewportOrgEx(a2, &point);
  v10 = point != 0;
  point = 0;
  GetWindowOrgEx(a2, &point);
  v11 = point != 0;
  ROP2 = GetROP2(a2);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v14 = RectRgn;
  if ( RectRgn )
  {
    v2 = GetClipRgn(a2, RectRgn) != 0;
    DeleteObject(v14);
  }
  if ( v9 != 1 )
    SetMapMode(a2, 1);
  if ( v10 )
    SetViewportOrgEx(a2, 0, 0, 0);
  if ( v11 )
    SetWindowOrgEx(a2, 0, 0, 0);
  if ( ROP2 != 13 )
    SetROP2(a2, 13);
  if ( v2 )
    goto LABEL_5;
}

```

## disassembly

```asm
0x18002f21c  mov     [rsp+arg_8], rbx
0x18002f221  mov     [rsp+arg_10], rbp
0x18002f226  push    rsi
0x18002f227  push    rdi
0x18002f228  push    r12
0x18002f22a  push    r14
0x18002f22c  push    r15
0x18002f22e  sub     rsp, 20h
0x18002f232  mov     ebp, 1
0x18002f237  mov     rdi, rcx
0x18002f23a  cmp     [rcx+280h], ebp
0x18002f240  mov     rbx, rdx
0x18002f243  mov     rcx, rdx; hdc
0x18002f246  lea     edx, [rbp+1]
0x18002f249  jz      short loc_18002F24D
0x18002f24b  mov     edx, ebp; mode
0x18002f24d  call    cs:__imp_SetICMMode
0x18002f254  nop     dword ptr [rax+rax+00h]
0x18002f259  cmp     dword ptr [rdi+284h], 0
0x18002f260  mov     rcx, rbx; hdc
0x18002f263  jnz     loc_18002F2F6
0x18002f269  mov     edx, ebp; iMode
0x18002f26b  call    cs:__imp_SetMapMode
0x18002f272  nop     dword ptr [rax+rax+00h]
0x18002f277  xor     r9d, r9d; lppt
0x18002f27a  xor     r8d, r8d; y
0x18002f27d  xor     edx, edx; x
0x18002f27f  mov     rcx, rbx; hdc
0x18002f282  call    cs:__imp_SetViewportOrgEx
0x18002f289  nop     dword ptr [rax+rax+00h]
0x18002f28e  xor     r9d, r9d; lppt
0x18002f291  xor     r8d, r8d; y
0x18002f294  xor     edx, edx; x
0x18002f296  mov     rcx, rbx; hdc
0x18002f299  call    cs:__imp_SetWindowOrgEx
0x18002f2a0  nop     dword ptr [rax+rax+00h]
0x18002f2a5  mov     edx, 0Dh; rop2
0x18002f2aa  mov     rcx, rbx; hdc
0x18002f2ad  call    cs:__imp_SetROP2
0x18002f2b4  nop     dword ptr [rax+rax+00h]
0x18002f2b9  mov     r8d, ebp; mode
0x18002f2bc  xor     edx, edx; lpxf
0x18002f2be  mov     rcx, rbx; hdc
0x18002f2c1  call    cs:__imp_ModifyWorldTransform
0x18002f2c8  nop     dword ptr [rax+rax+00h]
0x18002f2cd  xor     edx, edx; hrgn
0x18002f2cf  mov     rcx, rbx; hdc
0x18002f2d2  call    cs:__imp_SelectClipRgn
0x18002f2d9  nop     dword ptr [rax+rax+00h]
0x18002f2de  mov     rbx, [rsp+48h+arg_8]
0x18002f2e3  mov     rbp, [rsp+48h+arg_10]
0x18002f2e8  add     rsp, 20h
0x18002f2ec  pop     r15
0x18002f2ee  pop     r14
0x18002f2f0  pop     r12
0x18002f2f2  pop     rdi
0x18002f2f3  pop     rsi
0x18002f2f4  retn
0x18002f2f6  call    cs:__imp_GetMapMode
0x18002f2fd  nop     dword ptr [rax+rax+00h]
0x18002f302  lea     rdx, [rsp+48h+point]; lppoint
0x18002f307  mov     qword ptr [rsp+48h+point.x], 0
0x18002f310  mov     rcx, rbx; hdc
0x18002f313  mov     r15d, eax
0x18002f316  call    cs:__imp_GetViewportOrgEx
0x18002f31d  nop     dword ptr [rax+rax+00h]
0x18002f322  cmp     [rsp+48h+point.x], 0
0x18002f327  jnz     loc_18002F3EB
0x18002f32d  cmp     [rsp+48h+point.y], 0
0x18002f332  jnz     loc_18002F3EB
0x18002f338  xor     esi, esi
0x18002f33a  lea     rdx, [rsp+48h+point]; lppoint
0x18002f33f  mov     qword ptr [rsp+48h+point.x], 0
0x18002f348  mov     rcx, rbx; hdc
0x18002f34b  call    cs:__imp_GetWindowOrgEx
0x18002f352  nop     dword ptr [rax+rax+00h]
0x18002f357  cmp     [rsp+48h+point.x], 0
0x18002f35c  jnz     short loc_18002F3BC
0x18002f35e  cmp     [rsp+48h+point.y], 0
0x18002f363  jnz     short loc_18002F3BC
0x18002f365  xor     edi, edi
0x18002f367  mov     rcx, rbx; hdc
0x18002f36a  call    cs:__imp_GetROP2
0x18002f371  nop     dword ptr [rax+rax+00h]
0x18002f376  xor     r9d, r9d; y2
0x18002f379  xor     r8d, r8d; x2
0x18002f37c  xor     edx, edx; y1
0x18002f37e  xor     ecx, ecx; x1
0x18002f380  mov     r12d, eax
0x18002f383  call    cs:__imp_CreateRectRgn
0x18002f38a  nop     dword ptr [rax+rax+00h]
0x18002f38f  mov     r14, rax
0x18002f392  test    rax, rax
0x18002f395  jnz     short loc_18002F3C0
0x18002f397  cmp     r15d, 1
0x18002f39b  jnz     short loc_18002F3F2
0x18002f39d  test    esi, esi
0x18002f39f  jnz     short loc_18002F408
0x18002f3a1  test    edi, edi
0x18002f3a3  jnz     short loc_18002F421
0x18002f3a5  cmp     r12d, 0Dh
0x18002f3a9  jnz     loc_18002F43D
0x18002f3af  test    ebp, ebp
0x18002f3b1  jnz     loc_18002F2CD
0x18002f3b7  jmp     loc_18002F2DE
0x18002f3bc  mov     edi, ebp
0x18002f3be  jmp     short loc_18002F367
0x18002f3c0  mov     rdx, r14; hrgn
0x18002f3c3  mov     rcx, rbx; hdc
0x18002f3c6  call    cs:__imp_GetClipRgn
0x18002f3cd  nop     dword ptr [rax+rax+00h]
0x18002f3d2  xor     ebp, ebp
0x18002f3d4  mov     rcx, r14; ho
0x18002f3d7  test    eax, eax
0x18002f3d9  setnz   bpl
0x18002f3dd  call    cs:__imp_DeleteObject
0x18002f3e4  nop     dword ptr [rax+rax+00h]
0x18002f3e9  jmp     short loc_18002F397
0x18002f3eb  mov     esi, ebp
0x18002f3ed  jmp     loc_18002F33A
0x18002f3f2  mov     edx, 1; iMode
0x18002f3f7  mov     rcx, rbx; hdc
0x18002f3fa  call    cs:__imp_SetMapMode
0x18002f401  nop     dword ptr [rax+rax+00h]
0x18002f406  jmp     short loc_18002F39D
0x18002f408  xor     r9d, r9d; lppt
0x18002f40b  xor     r8d, r8d; y
0x18002f40e  xor     edx, edx; x
0x18002f410  mov     rcx, rbx; hdc
0x18002f413  call    cs:__imp_SetViewportOrgEx
0x18002f41a  nop     dword ptr [rax+rax+00h]
0x18002f41f  jmp     short loc_18002F3A1
0x18002f421  xor     r9d, r9d; lppt
0x18002f424  xor     r8d, r8d; y
0x18002f427  xor     edx, edx; x
0x18002f429  mov     rcx, rbx; hdc
0x18002f42c  call    cs:__imp_SetWindowOrgEx
0x18002f433  nop     dword ptr [rax+rax+00h]
0x18002f438  jmp     loc_18002F3A5
0x18002f43d  mov     edx, 0Dh; rop2
0x18002f442  mov     rcx, rbx; hdc
0x18002f445  call    cs:__imp_SetROP2
0x18002f44c  nop     dword ptr [rax+rax+00h]
0x18002f451  jmp     loc_18002F3AF
```
