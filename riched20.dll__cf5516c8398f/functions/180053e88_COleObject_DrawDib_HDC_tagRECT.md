# COleObject::DrawDib(HDC__ *,tagRECT *)

- ea: `0x180053e88`
- end: `0x180053f4d`
- name: `?DrawDib@COleObject@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `197`
- prototype: `void(COleObject *__hidden this, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004a23c`

## callees

- `0x1800538fc`
- `0x180053e88`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x180053f33`
- `KERNEL32!GlobalUnlock` at `0x180053f33`
- `KERNEL32!LocalLock` at `0x180053ec9`
- `KERNEL32!LocalLock` at `0x180053ec9`
- `GDI32!DeleteDC` at `0x180053f3c`
- `GDI32!DeleteDC` at `0x180053f3c`
- `GDI32!StretchBlt` at `0x180053f2a`
- `GDI32!StretchBlt` at `0x180053f2a`
- `GDI32!CreateCompatibleDC` at `0x180053ebc`
- `GDI32!CreateCompatibleDC` at `0x180053ebc`
- `GDI32!SelectObject` at `0x180053edc`
- `GDI32!SelectObject` at `0x180053edc`

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
0x180053e88  push    rbx
0x180053e8a  push    rbp
0x180053e8b  push    rsi
0x180053e8c  push    rdi
0x180053e8d  push    r14
0x180053e8f  sub     rsp, 60h
0x180053e93  cmp     qword ptr [rcx+80h], 0
0x180053e9b  mov     r14, r8
0x180053e9e  mov     rbp, rdx
0x180053ea1  mov     rsi, rcx
0x180053ea4  jnz     short loc_180053EAB
0x180053ea6  call    ?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z; COleObject::CreateDib(HDC__ *)
0x180053eab  cmp     qword ptr [rsi+80h], 0
0x180053eb3  jz      loc_180053F42
0x180053eb9  mov     rcx, rbp; hdc
0x180053ebc  call    cs:__imp_CreateCompatibleDC
0x180053ec2  mov     rcx, [rsi+78h]; hMem
0x180053ec6  mov     rdi, rax
0x180053ec9  call    cs:__imp_LocalLock
0x180053ecf  mov     rdx, [rsi+80h]; h
0x180053ed6  mov     rcx, rdi; hdc
0x180053ed9  mov     rbx, rax
0x180053edc  call    cs:__imp_SelectObject
0x180053ee2  mov     ecx, [rbx+8]
0x180053ee5  mov     r10d, [r14+0Ch]
0x180053ee9  mov     r8d, [r14+4]; yDest
0x180053eed  sub     r10d, r8d
0x180053ef0  mov     r9d, [r14+8]
0x180053ef4  sub     r9d, [r14]; wDest
0x180053ef7  mov     edx, [r14]; xDest
0x180053efa  mov     [rsp+88h+rop], 0CC0020h; rop
0x180053f02  mov     [rsp+88h+hSrc], ecx; hSrc
0x180053f06  mov     ecx, [rbx+4]
0x180053f09  mov     [rsp+88h+wSrc], ecx; wSrc
0x180053f0d  mov     rcx, rbp; hdcDest
0x180053f10  mov     [rsp+88h+ySrc], 0; ySrc
0x180053f18  mov     [rsp+88h+xSrc], 0; xSrc
0x180053f20  mov     [rsp+88h+hdcSrc], rdi; hdcSrc
0x180053f25  mov     [rsp+88h+hDest], r10d; hDest
0x180053f2a  call    cs:__imp_StretchBlt
0x180053f30  mov     rcx, rbx; hMem
0x180053f33  call    cs:__imp_GlobalUnlock
0x180053f39  mov     rcx, rdi; hdc
0x180053f3c  call    cs:__imp_DeleteDC
0x180053f42  add     rsp, 60h
0x180053f46  pop     r14
0x180053f48  pop     rdi
0x180053f49  pop     rsi
0x180053f4a  pop     rbp
0x180053f4b  pop     rbx
0x180053f4c  retn
```
