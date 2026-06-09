# OleUIDrawShading(tagRECT *,HDC__ *)

- ea: `0x18008f214`
- end: `0x18008f3b3`
- name: `?OleUIDrawShading@@YAXPEAUtagRECT@@PEAUHDC__@@@Z`
- size: `415`
- prototype: `void(struct tagRECT *, HDC)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004b3ac`

## callees

- `0x180093c00`

## import_xrefs

- `USER32!GetSysColor` at `0x18008f2c7`
- `USER32!GetSysColor` at `0x18008f2eb`
- `USER32!GetSysColor` at `0x18008f2c7`
- `USER32!GetSysColor` at `0x18008f2eb`
- `GDI32!DeleteObject` at `0x18008f370`
- `GDI32!DeleteObject` at `0x18008f381`
- `GDI32!DeleteObject` at `0x18008f370`
- `GDI32!DeleteObject` at `0x18008f381`
- `GDI32!SelectObject` at `0x18008f2a6`
- `GDI32!SelectObject` at `0x18008f361`
- `GDI32!SelectObject` at `0x18008f2a6`
- `GDI32!SelectObject` at `0x18008f361`
- `GDI32!SetTextColor` at `0x18008f2d8`
- `GDI32!SetTextColor` at `0x18008f33e`
- `GDI32!SetTextColor` at `0x18008f2d8`
- `GDI32!SetTextColor` at `0x18008f33e`
- `GDI32!SetBkColor` at `0x18008f2fc`
- `GDI32!SetBkColor` at `0x18008f34f`
- `GDI32!SetBkColor` at `0x18008f2fc`
- `GDI32!SetBkColor` at `0x18008f34f`
- `GDI32!PatBlt` at `0x18008f32d`
- `GDI32!PatBlt` at `0x18008f32d`
- `GDI32!CreateBitmap` at `0x18008f27d`
- `GDI32!CreateBitmap` at `0x18008f27d`
- `GDI32!CreatePatternBrush` at `0x18008f291`
- `GDI32!CreatePatternBrush` at `0x18008f291`

## pseudocode

```c
void __fastcall OleUIDrawShading(struct tagRECT *a1, HDC a2)
{
  HDC v2; // rbx
  HBRUSH PatternBrush; // r13
  HGDIOBJ v5; // rax
  LONG left; // r15d
  LONG top; // r14d
  void *v8; // r12
  LONG right; // ebp
  COLORREF SysColor; // eax
  COLORREF v11; // edi
  COLORREF v12; // eax
  HBITMAP ho; // [rsp+38h] [rbp-60h]
  _DWORD Bits[4]; // [rsp+40h] [rbp-58h] BYREF

  Bits[0] = 2228241;
  v2 = a2;
  Bits[1] = 8912964;
  Bits[2] = 2228241;
  Bits[3] = 8912964;
  ho = CreateBitmap(8, 8, 1u, 1u, Bits);
  PatternBrush = CreatePatternBrush(ho);
  v5 = SelectObject(v2, PatternBrush);
  left = a1->left;
  top = a1->top;
  v8 = v5;
  right = a1->right;
  LODWORD(a1) = a1->bottom;
  SysColor = GetSysColor(5);
  v11 = SetTextColor(v2, SysColor);
  v12 = GetSysColor(8);
  LODWORD(v2) = SetBkColor(v2, v12);
  PatBlt(a2, left, top, right - left, (_DWORD)a1 - top, 0xA000C9u);
  SetTextColor(a2, v11);
  SetBkColor(a2, (COLORREF)v2);
  SelectObject(a2, v8);
  DeleteObject(PatternBrush);
  DeleteObject(ho);
}

```

## disassembly

```asm
0x18008f214  mov     [rsp+arg_10], rbx
0x18008f219  push    rbp
0x18008f21a  push    rsi
0x18008f21b  push    rdi
0x18008f21c  push    r12
0x18008f21e  push    r13
0x18008f220  push    r14
0x18008f222  push    r15
0x18008f224  sub     rsp, 60h
0x18008f228  mov     rax, cs:__security_cookie
0x18008f22f  xor     rax, rsp
0x18008f232  mov     [rsp+98h+var_48], rax
0x18008f237  mov     r8d, 1; nPlanes
0x18008f23d  mov     [rsp+98h+hdc], rdx
0x18008f242  lea     rax, [rsp+98h+Bits]
0x18008f247  mov     [rsp+98h+Bits], 220011h
0x18008f24f  mov     [rsp+98h+lpBits], rax; lpBits
0x18008f254  mov     rbx, rdx
0x18008f257  mov     rsi, rcx
0x18008f25a  mov     [rsp+98h+var_54], 880044h
0x18008f262  lea     eax, [r8+7]
0x18008f266  mov     [rsp+98h+var_50], 220011h
0x18008f26e  mov     edx, eax; nHeight
0x18008f270  mov     [rsp+98h+var_4C], 880044h
0x18008f278  mov     ecx, eax; nWidth
0x18008f27a  mov     r9d, r8d; nBitCount
0x18008f27d  call    cs:__imp_CreateBitmap
0x18008f284  nop     dword ptr [rax+rax+00h]
0x18008f289  mov     rcx, rax; hbm
0x18008f28c  mov     [rsp+98h+ho], rax
0x18008f291  call    cs:__imp_CreatePatternBrush
0x18008f298  nop     dword ptr [rax+rax+00h]
0x18008f29d  mov     rdx, rax; h
0x18008f2a0  mov     rcx, rbx; hdc
0x18008f2a3  mov     r13, rax
0x18008f2a6  call    cs:__imp_SelectObject
0x18008f2ad  nop     dword ptr [rax+rax+00h]
0x18008f2b2  mov     r15d, [rsi]
0x18008f2b5  mov     ecx, 5; nIndex
0x18008f2ba  mov     r14d, [rsi+4]
0x18008f2be  mov     r12, rax
0x18008f2c1  mov     ebp, [rsi+8]
0x18008f2c4  mov     esi, [rsi+0Ch]
0x18008f2c7  call    cs:__imp_GetSysColor
0x18008f2ce  nop     dword ptr [rax+rax+00h]
0x18008f2d3  mov     edx, eax; color
0x18008f2d5  mov     rcx, rbx; hdc
0x18008f2d8  call    cs:__imp_SetTextColor
0x18008f2df  nop     dword ptr [rax+rax+00h]
0x18008f2e4  mov     ecx, 8; nIndex
0x18008f2e9  mov     edi, eax
0x18008f2eb  call    cs:__imp_GetSysColor
0x18008f2f2  nop     dword ptr [rax+rax+00h]
0x18008f2f7  mov     edx, eax; color
0x18008f2f9  mov     rcx, rbx; hdc
0x18008f2fc  call    cs:__imp_SetBkColor
0x18008f303  nop     dword ptr [rax+rax+00h]
0x18008f308  sub     esi, r14d
0x18008f30b  mov     [rsp+98h+rop], 0A000C9h; rop
0x18008f313  mov     dword ptr [rsp+98h+lpBits], esi; h
0x18008f317  sub     ebp, r15d
0x18008f31a  mov     rsi, [rsp+98h+hdc]
0x18008f31f  mov     r9d, ebp; w
0x18008f322  mov     rcx, rsi; hdc
0x18008f325  mov     r8d, r14d; y
0x18008f328  mov     edx, r15d; x
0x18008f32b  mov     ebx, eax
0x18008f32d  call    cs:__imp_PatBlt
0x18008f334  nop     dword ptr [rax+rax+00h]
0x18008f339  mov     edx, edi; color
0x18008f33b  mov     rcx, rsi; hdc
0x18008f33e  call    cs:__imp_SetTextColor
0x18008f345  nop     dword ptr [rax+rax+00h]
0x18008f34a  mov     edx, ebx; color
0x18008f34c  mov     rcx, rsi; hdc
0x18008f34f  call    cs:__imp_SetBkColor
0x18008f356  nop     dword ptr [rax+rax+00h]
0x18008f35b  mov     rdx, r12; h
0x18008f35e  mov     rcx, rsi; hdc
0x18008f361  call    cs:__imp_SelectObject
0x18008f368  nop     dword ptr [rax+rax+00h]
0x18008f36d  mov     rcx, r13; ho
0x18008f370  call    cs:__imp_DeleteObject
0x18008f377  nop     dword ptr [rax+rax+00h]
0x18008f37c  mov     rcx, [rsp+98h+ho]; ho
0x18008f381  call    cs:__imp_DeleteObject
0x18008f388  nop     dword ptr [rax+rax+00h]
0x18008f38d  mov     rcx, [rsp+98h+var_48]
0x18008f392  xor     rcx, rsp; StackCookie
0x18008f395  call    __security_check_cookie
0x18008f39a  mov     rbx, [rsp+98h+arg_10]
0x18008f3a2  add     rsp, 60h
0x18008f3a6  pop     r15
0x18008f3a8  pop     r14
0x18008f3aa  pop     r13
0x18008f3ac  pop     r12
0x18008f3ae  pop     rdi
0x18008f3af  pop     rsi
0x18008f3b0  pop     rbp
0x18008f3b1  retn
```
