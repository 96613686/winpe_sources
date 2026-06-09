# COffScreenDC::Init(HDC__ *,long,long,ulong)

- ea: `0x18002dfac`
- end: `0x18002e058`
- name: `?Init@COffScreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z`
- size: `172`
- prototype: `HDC __fastcall(COffScreenDC *__hidden this, HDC hdc, int cx, int cy, COLORREF color)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180058554`
- `0x18005ad80`

## callees

- `0x18002dfac`
- `0x18002e76c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18002dfd4`
- `GDI32!CreateCompatibleDC` at `0x18002dfd4`
- `GDI32!SelectObject` at `0x18002e00c`
- `GDI32!SelectObject` at `0x18002e00c`
- `GDI32!SetBkColor` at `0x18002e028`
- `GDI32!SetBkColor` at `0x18002e028`
- `GDI32!CreateCompatibleBitmap` at `0x18002dff1`
- `GDI32!CreateCompatibleBitmap` at `0x18002dff1`

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
0x18002dfac  push    rbx
0x18002dfae  push    rbp
0x18002dfaf  push    rsi
0x18002dfb0  push    rdi
0x18002dfb1  push    r14
0x18002dfb3  sub     rsp, 20h
0x18002dfb7  xor     edi, edi
0x18002dfb9  mov     rbx, rcx
0x18002dfbc  mov     [rcx+8], rdi
0x18002dfc0  mov     ebp, r9d
0x18002dfc3  mov     [rcx+10h], rdi
0x18002dfc7  mov     r14d, r8d
0x18002dfca  mov     [rcx+18h], rdi
0x18002dfce  mov     rsi, rdx
0x18002dfd1  mov     rcx, rdx; hdc
0x18002dfd4  call    cs:__imp_CreateCompatibleDC
0x18002dfdb  nop     dword ptr [rax+rax+00h]
0x18002dfe0  mov     [rbx], rax
0x18002dfe3  test    rax, rax
0x18002dfe6  jz      short loc_18002E041
0x18002dfe8  mov     r8d, ebp; cy
0x18002dfeb  mov     edx, r14d; cx
0x18002dfee  mov     rcx, rsi; hdc
0x18002dff1  call    cs:__imp_CreateCompatibleBitmap
0x18002dff8  nop     dword ptr [rax+rax+00h]
0x18002dffd  mov     [rbx+10h], rax
0x18002e001  test    rax, rax
0x18002e004  jz      short loc_18002E041
0x18002e006  mov     rcx, [rbx]; hdc
0x18002e009  mov     rdx, rax; h
0x18002e00c  call    cs:__imp_SelectObject
0x18002e013  nop     dword ptr [rax+rax+00h]
0x18002e018  mov     [rbx+8], rax
0x18002e01c  test    rax, rax
0x18002e01f  jz      short loc_18002E041
0x18002e021  mov     edx, [rsp+48h+color]; color
0x18002e025  mov     rcx, [rbx]; hdc
0x18002e028  call    cs:__imp_SetBkColor
0x18002e02f  nop     dword ptr [rax+rax+00h]
0x18002e034  cmp     eax, 0FFFFFFFFh
0x18002e037  jz      short loc_18002E041
0x18002e039  mov     rdi, [rbx]
0x18002e03c  test    rdi, rdi
0x18002e03f  jnz     short loc_18002E049
0x18002e041  mov     rcx, rbx; this
0x18002e044  call    ?FreeData@COffScreenDC@@AEAAXXZ; COffScreenDC::FreeData(void)
0x18002e049  mov     rax, rdi
0x18002e04c  add     rsp, 20h
0x18002e050  pop     r14
0x18002e052  pop     rdi
0x18002e053  pop     rsi
0x18002e054  pop     rbp
0x18002e055  pop     rbx
0x18002e056  retn
```
