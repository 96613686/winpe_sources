# CAMCHeaderCtrl::DrawSortArrow(CDC *,tagRECT const &,_HD_ITEMW const &)

- ea: `0x1400a0e54`
- end: `0x1400a1019`
- name: `?DrawSortArrow@CAMCHeaderCtrl@@AEAAXPEAVCDC@@AEBUtagRECT@@AEBU_HD_ITEMW@@@Z`
- size: `453`
- prototype: `void __fastcall(CAMCHeaderCtrl *__hidden this, struct CDC *, const struct tagRECT *, const struct _HD_ITEMW *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400a3080`

## callees

- `0x1400a0e54`
- `0x1400e9e10`

## import_xrefs

- `GDI32!GetTextColor` at `0x1400a0e84`
- `GDI32!GetTextColor` at `0x1400a0e84`
- `GDI32!GetTextMetricsW` at `0x1400a0eb4`
- `GDI32!GetTextMetricsW` at `0x1400a0eb4`
- `GDI32!CreatePen` at `0x1400a0f2c`
- `GDI32!CreatePen` at `0x1400a0f2c`
- `GDI32!SelectObject` at `0x1400a0f3c`
- `GDI32!SelectObject` at `0x1400a0fe5`
- `GDI32!SelectObject` at `0x1400a0f3c`
- `GDI32!SelectObject` at `0x1400a0fe5`
- `GDI32!MoveToEx` at `0x1400a0f5e`
- `GDI32!MoveToEx` at `0x1400a0f80`
- `GDI32!MoveToEx` at `0x1400a0fa2`
- `GDI32!MoveToEx` at `0x1400a0fc4`
- `GDI32!MoveToEx` at `0x1400a0f5e`
- `GDI32!MoveToEx` at `0x1400a0f80`
- `GDI32!MoveToEx` at `0x1400a0fa2`
- `GDI32!MoveToEx` at `0x1400a0fc4`
- `GDI32!LineTo` at `0x1400a0f6d`
- `GDI32!LineTo` at `0x1400a0fb1`
- `GDI32!LineTo` at `0x1400a0fd3`
- `GDI32!LineTo` at `0x1400a0f6d`
- `GDI32!LineTo` at `0x1400a0fb1`
- `GDI32!LineTo` at `0x1400a0fd3`
- `GDI32!DeleteObject` at `0x1400a0fee`
- `GDI32!DeleteObject` at `0x1400a0fee`

## pseudocode

```c
void __fastcall CAMCHeaderCtrl::DrawSortArrow(
        CAMCHeaderCtrl *this,
        HDC *a2,
        const struct tagRECT *a3,
        const struct _HD_ITEMW *a4)
{
  COLORREF TextColor; // eax
  LONG left; // edi
  LONG top; // esi
  HDC v10; // rcx
  COLORREF v11; // ebp
  LONG right; // ebx
  unsigned int v13; // r8d
  int v14; // ecx
  unsigned int v15; // r8d
  int v16; // esi
  int v17; // ebx
  int v18; // edi
  int v19; // r13d
  int v20; // eax
  int v21; // r12d
  HPEN Pen; // rbp
  HGDIOBJ v23; // rax
  int v24; // r8d
  HGDIOBJ v25; // [rsp+20h] [rbp-88h]
  struct tagTEXTMETRICW tm; // [rsp+28h] [rbp-80h] BYREF

  TextColor = GetTextColor(a2[2]);
  left = a3->left;
  top = a3->top;
  v10 = a2[2];
  v11 = TextColor;
  right = a3->right;
  memset(&tm, 0, sizeof(tm));
  GetTextMetricsW(v10, &tm);
  v13 = tm.tmHeight / 2;
  if ( tm.tmHeight / 2 < 6 )
    v13 = 6;
  v14 = tm.tmHeight / 4;
  if ( tm.tmHeight / 4 < 3 )
    v14 = 3;
  v15 = v13 >> 1;
  v16 = top + 2;
  v17 = (right - left) / 2 + left;
  v18 = v16 + v14;
  v19 = v17 + v15;
  v20 = tm.tmHeight / 16;
  v21 = v17 - v15;
  if ( tm.tmHeight / 16 < 1 )
    v20 = 1;
  Pen = CreatePen(0, v20, v11);
  v23 = SelectObject(a2[1], Pen);
  v25 = v23;
  if ( (a4->fmt & 0x400) != 0 )
  {
    MoveToEx(a2[1], v21, v18, 0);
    LineTo(a2[1], v17, v16);
    MoveToEx(a2[1], v19, v18, 0);
    v24 = v16;
LABEL_11:
    LineTo(a2[1], v17, v24);
    v23 = v25;
    goto LABEL_12;
  }
  if ( (a4->fmt & 0x200) != 0 )
  {
    MoveToEx(a2[1], v21, v16, 0);
    LineTo(a2[1], v17, v18);
    MoveToEx(a2[1], v19, v16, 0);
    v24 = v18;
    goto LABEL_11;
  }
LABEL_12:
  SelectObject(a2[1], v23);
  DeleteObject(Pen);
}

```

## disassembly

```asm
0x1400a0e54  mov     [rsp+arg_0], rbx
0x1400a0e59  push    rbp
0x1400a0e5a  push    rsi
0x1400a0e5b  push    rdi
0x1400a0e5c  push    r12
0x1400a0e5e  push    r13
0x1400a0e60  push    r14
0x1400a0e62  push    r15
0x1400a0e64  sub     rsp, 70h
0x1400a0e68  mov     rax, cs:__security_cookie
0x1400a0e6f  xor     rax, rsp
0x1400a0e72  mov     [rsp+0A8h+var_40], rax
0x1400a0e77  mov     rcx, [rdx+10h]; hdc
0x1400a0e7b  mov     r14, r9
0x1400a0e7e  mov     rbx, r8
0x1400a0e81  mov     r15, rdx
0x1400a0e84  call    cs:__imp_GetTextColor
0x1400a0e8a  mov     edi, [rbx]
0x1400a0e8c  lea     rdx, [rsp+0A8h+tm]; lptm
0x1400a0e91  mov     esi, [rbx+4]
0x1400a0e94  xorps   xmm0, xmm0
0x1400a0e97  mov     rcx, [r15+10h]; hdc
0x1400a0e9b  mov     ebp, eax
0x1400a0e9d  mov     ebx, [rbx+8]
0x1400a0ea0  movups  xmmword ptr [rsp+0A8h+tm.tmOverhang], xmm0
0x1400a0ea5  movups  xmmword ptr [rsp+0A8h+tm.tmFirstChar], xmm0
0x1400a0eaa  movups  xmmword ptr [rsp+0A8h+tm.tmHeight], xmm0
0x1400a0eaf  movups  xmmword ptr [rsp+0A8h+tm.tmExternalLeading], xmm0
0x1400a0eb4  call    cs:__imp_GetTextMetricsW
0x1400a0eba  mov     r9d, [rsp+0A8h+tm.tmHeight]
0x1400a0ebf  mov     r10d, 3
0x1400a0ec5  mov     eax, r9d
0x1400a0ec8  cdq
0x1400a0ec9  sub     eax, edx
0x1400a0ecb  sar     eax, 1
0x1400a0ecd  mov     r8d, eax
0x1400a0ed0  mov     eax, 6
0x1400a0ed5  cmp     r8d, eax
0x1400a0ed8  cmovl   r8d, eax
0x1400a0edc  mov     eax, r9d
0x1400a0edf  cdq
0x1400a0ee0  and     edx, r10d
0x1400a0ee3  add     eax, edx
0x1400a0ee5  sar     eax, 2
0x1400a0ee8  cmp     eax, r10d
0x1400a0eeb  mov     ecx, eax
0x1400a0eed  cmovl   ecx, r10d
0x1400a0ef1  shr     r8d, 1
0x1400a0ef4  sub     ebx, edi
0x1400a0ef6  add     esi, 2
0x1400a0ef9  mov     eax, ebx
0x1400a0efb  cdq
0x1400a0efc  sub     eax, edx
0x1400a0efe  sar     eax, 1
0x1400a0f00  lea     ebx, [rax+rdi]
0x1400a0f03  mov     eax, r9d
0x1400a0f06  cdq
0x1400a0f07  lea     edi, [rsi+rcx]
0x1400a0f0a  and     edx, 0Fh
0x1400a0f0d  lea     ecx, [r10-2]
0x1400a0f11  add     eax, edx
0x1400a0f13  lea     r13d, [rbx+r8]
0x1400a0f17  sar     eax, 4
0x1400a0f1a  mov     r12d, ebx
0x1400a0f1d  sub     r12d, r8d
0x1400a0f20  mov     r8d, ebp; color
0x1400a0f23  cmp     eax, ecx
0x1400a0f25  cmovl   eax, ecx
0x1400a0f28  xor     ecx, ecx; iStyle
0x1400a0f2a  mov     edx, eax; cWidth
0x1400a0f2c  call    cs:__imp_CreatePen
0x1400a0f32  mov     rcx, [r15+8]; hdc
0x1400a0f36  mov     rdx, rax; h
0x1400a0f39  mov     rbp, rax
0x1400a0f3c  call    cs:__imp_SelectObject
0x1400a0f42  test    dword ptr [r14+1Ch], 400h
0x1400a0f4a  mov     [rsp+0A8h+var_88], rax
0x1400a0f4f  jz      short loc_1400A0F8B
0x1400a0f51  mov     rcx, [r15+8]; hdc
0x1400a0f55  xor     r9d, r9d; lppt
0x1400a0f58  mov     r8d, edi; y
0x1400a0f5b  mov     edx, r12d; x
0x1400a0f5e  call    cs:__imp_MoveToEx
0x1400a0f64  mov     rcx, [r15+8]; hdc
0x1400a0f68  mov     r8d, esi; y
0x1400a0f6b  mov     edx, ebx; x
0x1400a0f6d  call    cs:__imp_LineTo
0x1400a0f73  mov     rcx, [r15+8]; hdc
0x1400a0f77  xor     r9d, r9d; lppt
0x1400a0f7a  mov     r8d, edi; y
0x1400a0f7d  mov     edx, r13d; x
0x1400a0f80  call    cs:__imp_MoveToEx
0x1400a0f86  mov     r8d, esi
0x1400a0f89  jmp     short loc_1400A0FCD
0x1400a0f8b  test    dword ptr [r14+1Ch], 200h
0x1400a0f93  jz      short loc_1400A0FDE
0x1400a0f95  mov     rcx, [r15+8]; hdc
0x1400a0f99  xor     r9d, r9d; lppt
0x1400a0f9c  mov     r8d, esi; y
0x1400a0f9f  mov     edx, r12d; x
0x1400a0fa2  call    cs:__imp_MoveToEx
0x1400a0fa8  mov     rcx, [r15+8]; hdc
0x1400a0fac  mov     r8d, edi; y
0x1400a0faf  mov     edx, ebx; x
0x1400a0fb1  call    cs:__imp_LineTo
0x1400a0fb7  mov     rcx, [r15+8]; hdc
0x1400a0fbb  xor     r9d, r9d; lppt
0x1400a0fbe  mov     r8d, esi; y
0x1400a0fc1  mov     edx, r13d; x
0x1400a0fc4  call    cs:__imp_MoveToEx
0x1400a0fca  mov     r8d, edi; y
0x1400a0fcd  mov     rcx, [r15+8]; hdc
0x1400a0fd1  mov     edx, ebx; x
0x1400a0fd3  call    cs:__imp_LineTo
0x1400a0fd9  mov     rax, [rsp+0A8h+var_88]
0x1400a0fde  mov     rcx, [r15+8]; hdc
0x1400a0fe2  mov     rdx, rax; h
0x1400a0fe5  call    cs:__imp_SelectObject
0x1400a0feb  mov     rcx, rbp; ho
0x1400a0fee  call    cs:__imp_DeleteObject
0x1400a0ff4  mov     rcx, [rsp+0A8h+var_40]
0x1400a0ff9  xor     rcx, rsp; StackCookie
0x1400a0ffc  call    __security_check_cookie
0x1400a1001  mov     rbx, [rsp+0A8h+arg_0]
0x1400a1009  add     rsp, 70h
0x1400a100d  pop     r15
0x1400a100f  pop     r14
0x1400a1011  pop     r13
0x1400a1013  pop     r12
0x1400a1015  pop     rdi
0x1400a1016  pop     rsi
0x1400a1017  pop     rbp
0x1400a1018  retn
```
