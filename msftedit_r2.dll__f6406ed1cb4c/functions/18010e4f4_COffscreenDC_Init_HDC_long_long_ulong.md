# COffscreenDC::Init(HDC__ *,long,long,ulong)

- ea: `0x18010e4f4`
- end: `0x18010e5ac`
- name: `?Init@COffscreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z`
- size: `184`
- prototype: `HDC __fastcall(COffscreenDC *__hidden this, HDC hdc, int cx, int cy, COLORREF color)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ff310`
- `0x18016300c`

## callees

- `0x18004e418`
- `0x18010e4f4`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010e528`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010e528`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010e560`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010e560`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18010e57c`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18010e57c`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010e545`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010e545`

## pseudocode

```c
HDC __fastcall COffscreenDC::Init(COffscreenDC *this, HDC hdc, int cx, int cy, COLORREF color)
{
  HDC result; // rax
  __int64 v10; // rdi
  HDC CompatibleDC; // rax
  __int64 v12; // rdx
  int v13; // r8d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v15; // rax

  result = *(HDC *)this;
  if ( !*(_QWORD *)this )
  {
    v10 = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
    CompatibleDC = CreateCompatibleDC(hdc);
    *(_QWORD *)this = CompatibleDC;
    if ( !CompatibleDC
      || (CompatibleBitmap = CreateCompatibleBitmap(hdc, cx, cy), (*((_QWORD *)this + 2) = CompatibleBitmap) == 0)
      || (v15 = SelectObject(*(HDC *)this, CompatibleBitmap), (*((_QWORD *)this + 1) = v15) == 0)
      || SetBkColor(*(HDC *)this, color) == -1
      || (v10 = *(_QWORD *)this) == 0 )
    {
      COffscreenDC::FreeData(this, v12, v13);
    }
    return (HDC)v10;
  }
  return result;
}

```

## disassembly

```asm
0x18010e4f4  push    rbx
0x18010e4f6  push    rbp
0x18010e4f7  push    rsi
0x18010e4f8  push    rdi
0x18010e4f9  push    r14
0x18010e4fb  sub     rsp, 20h
0x18010e4ff  mov     rax, [rcx]
0x18010e502  mov     ebp, r9d
0x18010e505  mov     r14d, r8d
0x18010e508  mov     rsi, rdx
0x18010e50b  mov     rbx, rcx
0x18010e50e  test    rax, rax
0x18010e511  jnz     loc_18010E5A0
0x18010e517  xor     edi, edi
0x18010e519  mov     [rcx+8], rdi
0x18010e51d  mov     [rcx+10h], rdi
0x18010e521  mov     [rcx+18h], rdi
0x18010e525  mov     rcx, rdx; hdc
0x18010e528  call    cs:__imp_CreateCompatibleDC
0x18010e52f  nop     dword ptr [rax+rax+00h]
0x18010e534  mov     [rbx], rax
0x18010e537  test    rax, rax
0x18010e53a  jz      short loc_18010E595
0x18010e53c  mov     r8d, ebp; cy
0x18010e53f  mov     edx, r14d; cx
0x18010e542  mov     rcx, rsi; hdc
0x18010e545  call    cs:__imp_CreateCompatibleBitmap
0x18010e54c  nop     dword ptr [rax+rax+00h]
0x18010e551  mov     [rbx+10h], rax
0x18010e555  test    rax, rax
0x18010e558  jz      short loc_18010E595
0x18010e55a  mov     rcx, [rbx]; hdc
0x18010e55d  mov     rdx, rax; h
0x18010e560  call    cs:__imp_SelectObject
0x18010e567  nop     dword ptr [rax+rax+00h]
0x18010e56c  mov     [rbx+8], rax
0x18010e570  test    rax, rax
0x18010e573  jz      short loc_18010E595
0x18010e575  mov     edx, [rsp+48h+color]; color
0x18010e579  mov     rcx, [rbx]; hdc
0x18010e57c  call    cs:__imp_SetBkColor
0x18010e583  nop     dword ptr [rax+rax+00h]
0x18010e588  cmp     eax, 0FFFFFFFFh
0x18010e58b  jz      short loc_18010E595
0x18010e58d  mov     rdi, [rbx]
0x18010e590  test    rdi, rdi
0x18010e593  jnz     short loc_18010E59D
0x18010e595  mov     rcx, rbx; this
0x18010e598  call    ?FreeData@COffscreenDC@@AEAAXXZ; COffscreenDC::FreeData(void)
0x18010e59d  mov     rax, rdi
0x18010e5a0  add     rsp, 20h
0x18010e5a4  pop     r14
0x18010e5a6  pop     rdi
0x18010e5a7  pop     rsi
0x18010e5a8  pop     rbp
0x18010e5a9  pop     rbx
0x18010e5aa  retn
```
