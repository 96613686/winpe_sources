# COleObject::DrawDib(HDC__ *,tagRECT *)

- ea: `0x18005530c`
- end: `0x1800553f6`
- name: `?DrawDib@COleObject@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `234`
- prototype: `void(COleObject *__hidden this, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004b3ac`

## callees

- `0x180054d70`
- `0x18005530c`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x1800553cf`
- `KERNEL32!GlobalUnlock` at `0x1800553cf`
- `KERNEL32!LocalLock` at `0x180055353`
- `KERNEL32!LocalLock` at `0x180055353`
- `GDI32!DeleteDC` at `0x1800553de`
- `GDI32!DeleteDC` at `0x1800553de`
- `GDI32!StretchBlt` at `0x1800553c0`
- `GDI32!StretchBlt` at `0x1800553c0`
- `GDI32!CreateCompatibleDC` at `0x180055340`
- `GDI32!CreateCompatibleDC` at `0x180055340`
- `GDI32!SelectObject` at `0x18005536c`
- `GDI32!SelectObject` at `0x18005536c`

## pseudocode

```c
void __fastcall COleObject::DrawDib(HLOCAL *this, HDC a2, struct tagRECT *a3)
{
  HDC hdcSrc; // rdi
  int *v7; // rbx

  if ( !this[16] )
    COleObject::CreateDib((COleObject *)this, a2);
  if ( this[16] )
  {
    hdcSrc = CreateCompatibleDC(a2);
    v7 = (int *)LocalLock(this[15]);
    SelectObject(hdcSrc, this[16]);
    StretchBlt(a2, a3->left, a3->top, a3->right - a3->left, a3->bottom - a3->top, hdcSrc, 0, 0, v7[1], v7[2], 0xCC0020u);
    GlobalUnlock(v7);
    DeleteDC(hdcSrc);
  }
}

```

## disassembly

```asm
0x18005530c  push    rbx
0x18005530e  push    rbp
0x18005530f  push    rsi
0x180055310  push    rdi
0x180055311  push    r14
0x180055313  sub     rsp, 60h
0x180055317  cmp     qword ptr [rcx+80h], 0
0x18005531f  mov     r14, r8
0x180055322  mov     rbp, rdx
0x180055325  mov     rsi, rcx
0x180055328  jnz     short loc_18005532F
0x18005532a  call    ?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z; COleObject::CreateDib(HDC__ *)
0x18005532f  cmp     qword ptr [rsi+80h], 0
0x180055337  jz      loc_1800553EA
0x18005533d  mov     rcx, rbp; hdc
0x180055340  call    cs:__imp_CreateCompatibleDC
0x180055347  nop     dword ptr [rax+rax+00h]
0x18005534c  mov     rcx, [rsi+78h]; hMem
0x180055350  mov     rdi, rax
0x180055353  call    cs:__imp_LocalLock
0x18005535a  nop     dword ptr [rax+rax+00h]
0x18005535f  mov     rdx, [rsi+80h]; h
0x180055366  mov     rcx, rdi; hdc
0x180055369  mov     rbx, rax
0x18005536c  call    cs:__imp_SelectObject
0x180055373  nop     dword ptr [rax+rax+00h]
0x180055378  mov     ecx, [rbx+8]
0x18005537b  mov     r10d, [r14+0Ch]
0x18005537f  mov     r8d, [r14+4]; yDest
0x180055383  sub     r10d, r8d
0x180055386  mov     r9d, [r14+8]
0x18005538a  sub     r9d, [r14]; wDest
0x18005538d  mov     edx, [r14]; xDest
0x180055390  mov     [rsp+88h+rop], 0CC0020h; rop
0x180055398  mov     [rsp+88h+hSrc], ecx; hSrc
0x18005539c  mov     ecx, [rbx+4]
0x18005539f  mov     [rsp+88h+wSrc], ecx; wSrc
0x1800553a3  mov     rcx, rbp; hdcDest
0x1800553a6  mov     [rsp+88h+ySrc], 0; ySrc
0x1800553ae  mov     [rsp+88h+xSrc], 0; xSrc
0x1800553b6  mov     [rsp+88h+hdcSrc], rdi; hdcSrc
0x1800553bb  mov     [rsp+88h+hDest], r10d; hDest
0x1800553c0  call    cs:__imp_StretchBlt
0x1800553c7  nop     dword ptr [rax+rax+00h]
0x1800553cc  mov     rcx, rbx; hMem
0x1800553cf  call    cs:__imp_GlobalUnlock
0x1800553d6  nop     dword ptr [rax+rax+00h]
0x1800553db  mov     rcx, rdi; hdc
0x1800553de  call    cs:__imp_DeleteDC
0x1800553e5  nop     dword ptr [rax+rax+00h]
0x1800553ea  add     rsp, 60h
0x1800553ee  pop     r14
0x1800553f0  pop     rdi
0x1800553f1  pop     rsi
0x1800553f2  pop     rbp
0x1800553f3  pop     rbx
0x1800553f4  retn
```
