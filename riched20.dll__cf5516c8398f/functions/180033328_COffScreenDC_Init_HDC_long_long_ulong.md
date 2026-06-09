# COffScreenDC::Init(HDC__ *,long,long,ulong)

- ea: `0x180033328`
- end: `0x1800333bb`
- name: `?Init@COffScreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z`
- size: `147`
- prototype: `HDC __fastcall(COffScreenDC *__hidden this, HDC hdc, int cx, int cy, COLORREF color)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180056fb0`
- `0x1800597a0`

## callees

- `0x180033328`
- `0x180033a94`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180033350`
- `GDI32!CreateCompatibleDC` at `0x180033350`
- `GDI32!SelectObject` at `0x18003337c`
- `GDI32!SelectObject` at `0x18003337c`
- `GDI32!SetBkColor` at `0x180033392`
- `GDI32!SetBkColor` at `0x180033392`
- `GDI32!CreateCompatibleBitmap` at `0x180033367`
- `GDI32!CreateCompatibleBitmap` at `0x180033367`

## pseudocode

```c
__int64 __fastcall COffScreenDC::Init(COffScreenDC *this, HDC hdc, int cx, int cy, COLORREF color)
{
  __int64 v5; // rdi
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v12; // rax

  v5 = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  CompatibleDC = CreateCompatibleDC(hdc);
  *(_QWORD *)this = CompatibleDC;
  if ( !CompatibleDC
    || (CompatibleBitmap = CreateCompatibleBitmap(hdc, cx, cy), (*((_QWORD *)this + 2) = CompatibleBitmap) == 0)
    || (v12 = SelectObject(*(HDC *)this, CompatibleBitmap), (*((_QWORD *)this + 1) = v12) == 0)
    || SetBkColor(*(HDC *)this, color) == -1
    || (v5 = *(_QWORD *)this) == 0 )
  {
    COffScreenDC::FreeData(this);
  }
  return v5;
}

```

## disassembly

```asm
0x180033328  push    rbx
0x18003332a  push    rbp
0x18003332b  push    rsi
0x18003332c  push    rdi
0x18003332d  push    r14
0x18003332f  sub     rsp, 20h
0x180033333  xor     edi, edi
0x180033335  mov     rbx, rcx
0x180033338  mov     [rcx+8], rdi
0x18003333c  mov     ebp, r9d
0x18003333f  mov     [rcx+10h], rdi
0x180033343  mov     r14d, r8d
0x180033346  mov     [rcx+18h], rdi
0x18003334a  mov     rsi, rdx
0x18003334d  mov     rcx, rdx; hdc
0x180033350  call    cs:__imp_CreateCompatibleDC
0x180033356  mov     [rbx], rax
0x180033359  test    rax, rax
0x18003335c  jz      short loc_1800333A5
0x18003335e  mov     r8d, ebp; cy
0x180033361  mov     edx, r14d; cx
0x180033364  mov     rcx, rsi; hdc
0x180033367  call    cs:__imp_CreateCompatibleBitmap
0x18003336d  mov     [rbx+10h], rax
0x180033371  test    rax, rax
0x180033374  jz      short loc_1800333A5
0x180033376  mov     rcx, [rbx]; hdc
0x180033379  mov     rdx, rax; h
0x18003337c  call    cs:__imp_SelectObject
0x180033382  mov     [rbx+8], rax
0x180033386  test    rax, rax
0x180033389  jz      short loc_1800333A5
0x18003338b  mov     edx, [rsp+48h+color]; color
0x18003338f  mov     rcx, [rbx]; hdc
0x180033392  call    cs:__imp_SetBkColor
0x180033398  cmp     eax, 0FFFFFFFFh
0x18003339b  jz      short loc_1800333A5
0x18003339d  mov     rdi, [rbx]
0x1800333a0  test    rdi, rdi
0x1800333a3  jnz     short loc_1800333AD
0x1800333a5  mov     rcx, rbx; this
0x1800333a8  call    ?FreeData@COffScreenDC@@AEAAXXZ; COffScreenDC::FreeData(void)
0x1800333ad  mov     rax, rdi
0x1800333b0  add     rsp, 20h
0x1800333b4  pop     r14
0x1800333b6  pop     rdi
0x1800333b7  pop     rsi
0x1800333b8  pop     rbp
0x1800333b9  pop     rbx
0x1800333ba  retn
```
