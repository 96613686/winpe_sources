# CCicLibMenuItem::CreateBitmap(HBITMAP__ *)

- ea: `0x1800d9524`
- end: `0x1800d9670`
- name: `?CreateBitmap@CCicLibMenuItem@@SAPEAUHBITMAP__@@PEAU2@@Z`
- size: `332`
- prototype: `HBITMAP __fastcall(HBITMAP h)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800afd50`

## callees

- `0x1800d9524`

## import_xrefs

- `GDI32!CreateDCW` at `0x1800d954c`
- `GDI32!CreateDCW` at `0x1800d954c`
- `GDI32!CreateCompatibleDC` at `0x1800d9584`
- `GDI32!CreateCompatibleDC` at `0x1800d95a4`
- `GDI32!CreateCompatibleDC` at `0x1800d9584`
- `GDI32!CreateCompatibleDC` at `0x1800d95a4`
- `GDI32!DeleteDC` at `0x1800d963a`
- `GDI32!DeleteDC` at `0x1800d9648`
- `GDI32!DeleteDC` at `0x1800d9656`
- `GDI32!DeleteDC` at `0x1800d963a`
- `GDI32!DeleteDC` at `0x1800d9648`
- `GDI32!DeleteDC` at `0x1800d9656`
- `GDI32!SelectObject` at `0x1800d9598`
- `GDI32!SelectObject` at `0x1800d95cd`
- `GDI32!SelectObject` at `0x1800d9620`
- `GDI32!SelectObject` at `0x1800d9631`
- `GDI32!SelectObject` at `0x1800d9598`
- `GDI32!SelectObject` at `0x1800d95cd`
- `GDI32!SelectObject` at `0x1800d9620`
- `GDI32!SelectObject` at `0x1800d9631`
- `GDI32!GetObjectW` at `0x1800d9578`
- `GDI32!GetObjectW` at `0x1800d9578`
- `GDI32!BitBlt` at `0x1800d960f`
- `GDI32!BitBlt` at `0x1800d960f`
- `GDI32!CreateCompatibleBitmap` at `0x1800d95be`
- `GDI32!CreateCompatibleBitmap` at `0x1800d95be`

## pseudocode

```c
HBITMAP __fastcall CCicLibMenuItem::CreateBitmap(HBITMAP h)
{
  HDC DCW; // rsi
  HGDIOBJ v3; // r15
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HDC v6; // rbx
  HBITMAP CompatibleBitmap; // r14
  HGDIOBJ v8; // rbp
  _OWORD pv[5]; // [rsp+50h] [rbp-58h] BYREF

  if ( !h )
    return 0;
  DCW = CreateDCW(L"DISPLAY", 0, 0, 0);
  if ( !DCW )
    return 0;
  memset(pv, 0, 32);
  GetObjectW(h, 32, pv);
  v3 = 0;
  CompatibleDC = CreateCompatibleDC(DCW);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
    v3 = SelectObject(CompatibleDC, h);
  v6 = CreateCompatibleDC(DCW);
  if ( v6 )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DCW, SDWORD1(pv[0]), SDWORD2(pv[0]));
    v8 = SelectObject(v6, CompatibleBitmap);
  }
  else
  {
    CompatibleBitmap = 0;
    v8 = 0;
  }
  BitBlt(v6, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
  if ( v3 )
    SelectObject(hdcSrc, v3);
  if ( v8 )
    SelectObject(v6, v8);
  DeleteDC(DCW);
  if ( hdcSrc )
    DeleteDC(hdcSrc);
  if ( v6 )
    DeleteDC(v6);
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x1800d9524  push    rbx
0x1800d9526  push    rbp
0x1800d9527  push    rsi
0x1800d9528  push    rdi
0x1800d9529  push    r14
0x1800d952b  push    r15
0x1800d952d  sub     rsp, 78h
0x1800d9531  mov     rbx, rcx
0x1800d9534  test    rcx, rcx
0x1800d9537  jz      loc_1800D9661
0x1800d953d  xor     r9d, r9d; pdm
0x1800d9540  lea     rcx, pwszDriver; "DISPLAY"
0x1800d9547  xor     r8d, r8d; pszPort
0x1800d954a  xor     edx, edx; pwszDevice
0x1800d954c  call    cs:__imp_CreateDCW
0x1800d9552  mov     rsi, rax
0x1800d9555  test    rax, rax
0x1800d9558  jz      loc_1800D9661
0x1800d955e  xorps   xmm0, xmm0
0x1800d9561  lea     r8, [rsp+0A8h+pv]; pv
0x1800d9566  mov     edx, 20h ; ' '; c
0x1800d956b  mov     rcx, rbx; h
0x1800d956e  movups  [rsp+0A8h+pv], xmm0
0x1800d9573  movups  [rsp+0A8h+var_48], xmm0
0x1800d9578  call    cs:__imp_GetObjectW
0x1800d957e  mov     rcx, rsi; hdc
0x1800d9581  xor     r15d, r15d
0x1800d9584  call    cs:__imp_CreateCompatibleDC
0x1800d958a  mov     rdi, rax
0x1800d958d  test    rax, rax
0x1800d9590  jz      short loc_1800D95A1
0x1800d9592  mov     rdx, rbx; h
0x1800d9595  mov     rcx, rax; hdc
0x1800d9598  call    cs:__imp_SelectObject
0x1800d959e  mov     r15, rax
0x1800d95a1  mov     rcx, rsi; hdc
0x1800d95a4  call    cs:__imp_CreateCompatibleDC
0x1800d95aa  mov     rbx, rax
0x1800d95ad  test    rax, rax
0x1800d95b0  jz      short loc_1800D95D8
0x1800d95b2  mov     r8d, dword ptr [rsp+0A8h+pv+8]; cy
0x1800d95b7  mov     rcx, rsi; hdc
0x1800d95ba  mov     edx, dword ptr [rsp+0A8h+pv+4]; cx
0x1800d95be  call    cs:__imp_CreateCompatibleBitmap
0x1800d95c4  mov     rdx, rax; h
0x1800d95c7  mov     rcx, rbx; hdc
0x1800d95ca  mov     r14, rax
0x1800d95cd  call    cs:__imp_SelectObject
0x1800d95d3  mov     rbp, rax
0x1800d95d6  jmp     short loc_1800D95DD
0x1800d95d8  xor     r14d, r14d
0x1800d95db  xor     ebp, ebp
0x1800d95dd  mov     eax, dword ptr [rsp+0A8h+pv+8]
0x1800d95e1  xor     r8d, r8d; y
0x1800d95e4  mov     r9d, dword ptr [rsp+0A8h+pv+4]; cx
0x1800d95e9  xor     edx, edx; x
0x1800d95eb  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1800d95f3  mov     rcx, rbx; hdc
0x1800d95f6  mov     [rsp+0A8h+y1], 0; y1
0x1800d95fe  mov     [rsp+0A8h+x1], 0; x1
0x1800d9606  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x1800d960b  mov     [rsp+0A8h+cy], eax; cy
0x1800d960f  call    cs:__imp_BitBlt
0x1800d9615  test    r15, r15
0x1800d9618  jz      short loc_1800D9626
0x1800d961a  mov     rdx, r15; h
0x1800d961d  mov     rcx, rdi; hdc
0x1800d9620  call    cs:__imp_SelectObject
0x1800d9626  test    rbp, rbp
0x1800d9629  jz      short loc_1800D9637
0x1800d962b  mov     rdx, rbp; h
0x1800d962e  mov     rcx, rbx; hdc
0x1800d9631  call    cs:__imp_SelectObject
0x1800d9637  mov     rcx, rsi; hdc
0x1800d963a  call    cs:__imp_DeleteDC
0x1800d9640  test    rdi, rdi
0x1800d9643  jz      short loc_1800D964E
0x1800d9645  mov     rcx, rdi; hdc
0x1800d9648  call    cs:__imp_DeleteDC
0x1800d964e  test    rbx, rbx
0x1800d9651  jz      short loc_1800D965C
0x1800d9653  mov     rcx, rbx; hdc
0x1800d9656  call    cs:__imp_DeleteDC
0x1800d965c  mov     rax, r14
0x1800d965f  jmp     short loc_1800D9663
0x1800d9661  xor     eax, eax
0x1800d9663  add     rsp, 78h
0x1800d9667  pop     r15
0x1800d9669  pop     r14
0x1800d966b  pop     rdi
0x1800d966c  pop     rsi
0x1800d966d  pop     rbp
0x1800d966e  pop     rbx
0x1800d966f  retn
```
