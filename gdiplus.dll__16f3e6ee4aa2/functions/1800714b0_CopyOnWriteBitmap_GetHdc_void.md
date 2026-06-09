# CopyOnWriteBitmap::GetHdc(void)

- ea: `0x1800714b0`
- end: `0x18007164b`
- name: `?GetHdc@CopyOnWriteBitmap@@AEAAPEAUHDC__@@XZ`
- size: `411`
- prototype: `HDC __fastcall(CopyOnWriteBitmap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007146c`

## callees

- `0x1800714b0`
- `0x1800fe680`
- `0x1800ff04c`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180071599`
- `GDI32!CreateDIBSection` at `0x180071599`
- `GDI32!DeleteDC` at `0x180071618`
- `GDI32!DeleteDC` at `0x180071618`
- `GDI32!SelectObject` at `0x1800715d8`
- `GDI32!SelectObject` at `0x1800715d8`
- `GDI32!CreateCompatibleDC` at `0x18007152e`
- `GDI32!CreateCompatibleDC` at `0x18007152e`
- `GDI32!GetObjectA` at `0x1800715c2`
- `GDI32!GetObjectA` at `0x1800715c2`
- `GDI32!DeleteObject` at `0x18007162d`
- `GDI32!DeleteObject` at `0x18007162d`

## pseudocode

```c
HDC __fastcall CopyOnWriteBitmap::GetHdc(CopyOnWriteBitmap *this)
{
  _DWORD *v2; // rcx
  _DWORD *v3; // rdx
  int v4; // eax
  LONG v6; // r14d
  int v7; // r15d
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HBITMAP v10; // rdi
  __int64 v11; // rax
  _DWORD *v12; // rdi
  __int64 i; // rcx
  BITMAPINFO pbmi; // [rsp+30h] [rbp-89h] BYREF
  _BYTE pv[12]; // [rsp+60h] [rbp-59h] BYREF
  int v16; // [rsp+6Ch] [rbp-4Dh]
  int v17; // [rsp+80h] [rbp-39h]

  if ( !*((_QWORD *)this + 27) )
  {
    v6 = *((_DWORD *)this + 41);
    v7 = *((_DWORD *)this + 42);
    CompatibleDC = CreateCompatibleDC(0);
    v9 = CompatibleDC;
    if ( CompatibleDC )
    {
      pbmi.bmiHeader.biHeight = -v7;
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v6;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      v10 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)this + 29, 0, 0);
      memset_0(pv, 0, 0x68u);
      if ( v10 && GetObjectA(v10, 104, pv) && v17 && SelectObject(v9, v10) )
      {
        v11 = v16;
        v3 = (_DWORD *)((char *)this + 248);
        v2 = (_DWORD *)((char *)this + 252);
        *((_DWORD *)this + 62) = v6;
        *((_DWORD *)this + 63) = v7;
        *((_QWORD *)this + 30) = v11;
        *((_QWORD *)this + 27) = v9;
        *((_QWORD *)this + 28) = v10;
        goto LABEL_3;
      }
      DeleteDC(v9);
      if ( v10 )
        DeleteObject(v10);
    }
    return 0;
  }
  v2 = (_DWORD *)((char *)this + 252);
  v3 = (_DWORD *)((char *)this + 248);
LABEL_3:
  v4 = *v3 * *v2;
  if ( v4 )
  {
    v12 = (_DWORD *)*((_QWORD *)this + 29);
    for ( i = v4; i; --i )
      *v12++ = 854796;
  }
  return (HDC)*((_QWORD *)this + 27);
}

```

## disassembly

```asm
0x1800714b0  push    rbp
0x1800714b2  push    rbx
0x1800714b3  push    rsi
0x1800714b4  push    rdi
0x1800714b5  push    r14
0x1800714b7  push    r15
0x1800714b9  lea     rbp, [rsp-2Fh]
0x1800714be  sub     rsp, 0E8h
0x1800714c5  mov     rax, cs:__security_cookie
0x1800714cc  xor     rax, rsp
0x1800714cf  mov     [rbp+57h+var_40], rax
0x1800714d3  cmp     qword ptr [rcx+0D8h], 0
0x1800714db  mov     rbx, rcx
0x1800714de  jz      short loc_18007151E
0x1800714e0  add     rcx, 0FCh
0x1800714e7  lea     rdx, [rbx+0F8h]
0x1800714ee  mov     eax, [rcx]
0x1800714f0  imul    eax, [rdx]
0x1800714f3  test    eax, eax
0x1800714f5  jnz     loc_180071635
0x1800714fb  mov     rax, [rbx+0D8h]
0x180071502  mov     rcx, [rbp+57h+var_40]
0x180071506  xor     rcx, rsp; StackCookie
0x180071509  call    __security_check_cookie
0x18007150e  add     rsp, 0E8h
0x180071515  pop     r15
0x180071517  pop     r14
0x180071519  pop     rdi
0x18007151a  pop     rsi
0x18007151b  pop     rbx
0x18007151c  pop     rbp
0x18007151d  retn
0x18007151e  mov     r14d, [rcx+0A4h]
0x180071525  mov     r15d, [rcx+0A8h]
0x18007152c  xor     ecx, ecx; hdc
0x18007152e  call    cs:__imp_CreateCompatibleDC
0x180071534  mov     rsi, rax
0x180071537  test    rax, rax
0x18007153a  jz      loc_180071623
0x180071540  mov     ecx, r15d
0x180071543  mov     [rsp+110h+offset], 0; offset
0x18007154b  neg     ecx
0x18007154d  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x180071555  mov     [rsp+110h+pbmi.bmiHeader.biHeight], ecx
0x180071559  lea     r9, [rbx+0E8h]; ppvBits
0x180071560  mov     rcx, rax; hdc
0x180071563  mov     [rsp+110h+pbmi.bmiHeader.biSize], 28h ; '('
0x18007156b  xor     r8d, r8d; usage
0x18007156e  mov     [rsp+110h+pbmi.bmiHeader.biWidth], r14d
0x180071573  lea     rdx, [rsp+110h+pbmi]; pbmi
0x180071578  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180071580  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], 0
0x180071588  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], 0
0x180071590  mov     [rsp+110h+hSection], 0; hSection
0x180071599  call    cs:__imp_CreateDIBSection
0x18007159f  xor     edx, edx; Val
0x1800715a1  lea     rcx, [rbp+57h+pv]; void *
0x1800715a5  mov     rdi, rax
0x1800715a8  lea     r8d, [rdx+68h]; Size
0x1800715ac  call    memset_0
0x1800715b1  test    rdi, rdi
0x1800715b4  jz      short loc_180071615
0x1800715b6  lea     r8, [rbp+57h+pv]; pv
0x1800715ba  mov     edx, 68h ; 'h'; c
0x1800715bf  mov     rcx, rdi; h
0x1800715c2  call    cs:__imp_GetObjectA
0x1800715c8  test    eax, eax
0x1800715ca  jz      short loc_180071615
0x1800715cc  cmp     [rbp+57h+var_90], 0
0x1800715d0  jz      short loc_180071615
0x1800715d2  mov     rdx, rdi; h
0x1800715d5  mov     rcx, rsi; hdc
0x1800715d8  call    cs:__imp_SelectObject
0x1800715de  test    rax, rax
0x1800715e1  jz      short loc_180071615
0x1800715e3  movsxd  rax, [rbp+57h+var_A4]
0x1800715e7  lea     rdx, [rbx+0F8h]
0x1800715ee  lea     rcx, [rbx+0FCh]
0x1800715f5  mov     [rdx], r14d
0x1800715f8  mov     [rcx], r15d
0x1800715fb  mov     [rbx+0F0h], rax
0x180071602  mov     [rbx+0D8h], rsi
0x180071609  mov     [rbx+0E0h], rdi
0x180071610  jmp     loc_1800714EE
0x180071615  mov     rcx, rsi; hdc
0x180071618  call    cs:__imp_DeleteDC
0x18007161e  test    rdi, rdi
0x180071621  jnz     short loc_18007162A
0x180071623  xor     eax, eax
0x180071625  jmp     loc_180071502
0x18007162a  mov     rcx, rdi; ho
0x18007162d  call    cs:__imp_DeleteObject
0x180071633  jmp     short loc_180071623
0x180071635  mov     rdi, [rbx+0E8h]
0x18007163c  movsxd  rcx, eax
0x18007163f  mov     eax, 0D0B0Ch
0x180071644  rep stosd
0x180071646  jmp     loc_1800714FB
```
