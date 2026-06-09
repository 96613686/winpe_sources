# CreateMirroredBitmap(HBITMAP__ *,int,int)

- ea: `0x1800e252c`
- end: `0x1800e274f`
- name: `?CreateMirroredBitmap@@YAPEAUHBITMAP__@@PEAU1@HH@Z`
- size: `547`
- prototype: `HBITMAP __fastcall(HBITMAP h, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc70`
- `0x18000e1d0`
- `0x18000e650`
- `0x1800e98c0`

## callees

- `0x180027a2c`
- `0x1800e252c`
- `0x180114520`

## import_xrefs

- `GDI32!GetObjectW` at `0x1800e2578`
- `GDI32!GetObjectW` at `0x1800e2578`
- `GDI32!SelectObject` at `0x1800e265e`
- `GDI32!SelectObject` at `0x1800e266e`
- `GDI32!SelectObject` at `0x1800e2717`
- `GDI32!SelectObject` at `0x1800e2724`
- `GDI32!SelectObject` at `0x1800e265e`
- `GDI32!SelectObject` at `0x1800e266e`
- `GDI32!SelectObject` at `0x1800e2717`
- `GDI32!SelectObject` at `0x1800e2724`
- `GDI32!DeleteDC` at `0x1800e25e6`
- `GDI32!DeleteDC` at `0x1800e272d`
- `GDI32!DeleteDC` at `0x1800e2736`
- `GDI32!DeleteDC` at `0x1800e25e6`
- `GDI32!DeleteDC` at `0x1800e272d`
- `GDI32!DeleteDC` at `0x1800e2736`
- `GDI32!CreateCompatibleDC` at `0x1800e2590`
- `GDI32!CreateCompatibleDC` at `0x1800e25d5`
- `GDI32!CreateCompatibleDC` at `0x1800e2590`
- `GDI32!CreateCompatibleDC` at `0x1800e25d5`
- `GDI32!SetLayout` at `0x1800e2680`
- `GDI32!SetLayout` at `0x1800e2680`
- `GDI32!BitBlt` at `0x1800e26c7`
- `GDI32!BitBlt` at `0x1800e270a`
- `GDI32!BitBlt` at `0x1800e26c7`
- `GDI32!BitBlt` at `0x1800e270a`
- `GDI32!CreateDIBSection` at `0x1800e2639`
- `GDI32!CreateDIBSection` at `0x1800e2639`
- `USER32!GetDC` at `0x1800e2584`
- `USER32!GetDC` at `0x1800e2584`
- `USER32!ReleaseDC` at `0x1800e25a3`
- `USER32!ReleaseDC` at `0x1800e2741`
- `USER32!ReleaseDC` at `0x1800e25a3`
- `USER32!ReleaseDC` at `0x1800e2741`

## pseudocode

```c
HBITMAP __fastcall CreateMirroredBitmap(HBITMAP h, int a2, int a3)
{
  HDC DC; // rdi
  HDC CompatibleDC; // rbx
  HDC v9; // r14
  HBITMAP ColorBitmap; // rax
  HBITMAP v11; // rsi
  int v12; // ecx
  int x1; // r15d
  HGDIOBJ ha; // [rsp+50h] [rbp-49h]
  void *ppvBits; // [rsp+58h] [rbp-41h] BYREF
  __int128 pv; // [rsp+60h] [rbp-39h] BYREF
  __int128 v17; // [rsp+70h] [rbp-29h]
  BITMAPINFO pbmi; // [rsp+80h] [rbp-19h] BYREF

  pv = 0;
  v17 = 0;
  if ( !h || !GetObjectW(h, 32, &pv) )
    return 0;
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  if ( !CompatibleDC )
  {
LABEL_4:
    ReleaseDC(0, DC);
    return 0;
  }
  v9 = CreateCompatibleDC(DC);
  if ( !v9 )
  {
    DeleteDC(CompatibleDC);
    goto LABEL_4;
  }
  if ( WORD1(v17) == 32 )
  {
    *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)&pv + 4);
    memset(&pbmi.bmiHeader.biCompression, 0, 28);
    ppvBits = 0;
    pbmi.bmiHeader.biSize = 40;
    *(_DWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    ColorBitmap = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
  }
  else
  {
    ColorBitmap = (HBITMAP)CreateColorBitmap(SDWORD1(pv), SDWORD2(pv));
  }
  v11 = ColorBitmap;
  if ( ColorBitmap )
  {
    ha = SelectObject(CompatibleDC, h);
    ppvBits = SelectObject(v9, v11);
    SetLayout(v9, 1u);
    if ( a2 )
    {
      v12 = DWORD1(pv);
      for ( x1 = 0; x1 < SDWORD1(pv); x1 += a3 )
      {
        BitBlt(v9, v12 - a3 - x1, 0, a3, SDWORD2(pv), CompatibleDC, x1, 0, 0xCC0020u);
        v12 = DWORD1(pv);
      }
    }
    else
    {
      BitBlt(v9, 0, 0, SDWORD1(pv), SDWORD2(pv), CompatibleDC, 0, 0, 0xCC0020u);
    }
    SelectObject(CompatibleDC, ha);
    SelectObject(CompatibleDC, ppvBits);
  }
  DeleteDC(v9);
  DeleteDC(CompatibleDC);
  ReleaseDC(0, DC);
  return v11;
}

```

## disassembly

```asm
0x1800e252c  mov     [rsp-8+arg_8], rbx
0x1800e2531  push    rbp
0x1800e2532  push    rsi
0x1800e2533  push    rdi
0x1800e2534  push    r12
0x1800e2536  push    r13
0x1800e2538  push    r14
0x1800e253a  push    r15
0x1800e253c  lea     rbp, [rsp-27h]
0x1800e2541  sub     rsp, 0C0h
0x1800e2548  mov     rax, cs:__security_cookie
0x1800e254f  xor     rax, rsp
0x1800e2552  mov     [rbp+57h+var_40], rax
0x1800e2556  xorps   xmm0, xmm0
0x1800e2559  xor     esi, esi
0x1800e255b  mov     r12d, r8d
0x1800e255e  mov     r13d, edx
0x1800e2561  mov     r15, rcx
0x1800e2564  movups  [rbp+57h+pv], xmm0
0x1800e2568  movups  [rbp+57h+var_80], xmm0
0x1800e256c  test    rcx, rcx
0x1800e256f  jz      short loc_1800E25A9
0x1800e2571  lea     r8, [rbp+57h+pv]; pv
0x1800e2575  lea     edx, [rsi+20h]; c
0x1800e2578  call    cs:__imp_GetObjectW
0x1800e257e  test    eax, eax
0x1800e2580  jz      short loc_1800E25A9
0x1800e2582  xor     ecx, ecx; hWnd
0x1800e2584  call    cs:__imp_GetDC
0x1800e258a  mov     rcx, rax; hdc
0x1800e258d  mov     rdi, rax
0x1800e2590  call    cs:__imp_CreateCompatibleDC
0x1800e2596  mov     rbx, rax
0x1800e2599  test    rax, rax
0x1800e259c  jnz     short loc_1800E25D2
0x1800e259e  mov     rdx, rdi; hDC
0x1800e25a1  xor     ecx, ecx; hWnd
0x1800e25a3  call    cs:__imp_ReleaseDC
0x1800e25a9  xor     eax, eax
0x1800e25ab  mov     rcx, [rbp+57h+var_40]
0x1800e25af  xor     rcx, rsp; StackCookie
0x1800e25b2  call    __security_check_cookie
0x1800e25b7  mov     rbx, [rsp+0F0h+arg_8]
0x1800e25bf  add     rsp, 0C0h
0x1800e25c6  pop     r15
0x1800e25c8  pop     r14
0x1800e25ca  pop     r13
0x1800e25cc  pop     r12
0x1800e25ce  pop     rdi
0x1800e25cf  pop     rsi
0x1800e25d0  pop     rbp
0x1800e25d1  retn
0x1800e25d2  mov     rcx, rdi; hdc
0x1800e25d5  call    cs:__imp_CreateCompatibleDC
0x1800e25db  mov     r14, rax
0x1800e25de  test    rax, rax
0x1800e25e1  jnz     short loc_1800E25EE
0x1800e25e3  mov     rcx, rbx; hdc
0x1800e25e6  call    cs:__imp_DeleteDC
0x1800e25ec  jmp     short loc_1800E259E
0x1800e25ee  mov     ecx, 20h ; ' '
0x1800e25f3  cmp     word ptr [rbp+57h+var_80+2], cx
0x1800e25f7  jnz     short loc_1800E2641
0x1800e25f9  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800e25fc  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800e2600  xorps   xmm0, xmm0
0x1800e2603  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800e2606  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800e2609  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800e260d  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm0
0x1800e2611  mov     [rsp+0F0h+offset], esi; offset
0x1800e2615  xor     r8d, r8d; usage
0x1800e2618  mov     rcx, rdi; hdc
0x1800e261b  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800e261e  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x1800e2622  mov     [rbp+57h+ppvBits], rsi
0x1800e2626  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800e262d  mov     dword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800e2634  mov     [rsp+0F0h+hSection], rsi; hSection
0x1800e2639  call    cs:__imp_CreateDIBSection
0x1800e263f  jmp     short loc_1800E264C
0x1800e2641  mov     edx, dword ptr [rbp+57h+pv+8]; cy
0x1800e2644  mov     ecx, dword ptr [rbp+57h+pv+4]; cx
0x1800e2647  call    CreateColorBitmap
0x1800e264c  mov     rsi, rax
0x1800e264f  test    rsi, rsi
0x1800e2652  jz      loc_1800E272A
0x1800e2658  mov     rdx, r15; h
0x1800e265b  mov     rcx, rbx; hdc
0x1800e265e  call    cs:__imp_SelectObject
0x1800e2664  mov     rdx, rsi; h
0x1800e2667  mov     rcx, r14; hdc
0x1800e266a  mov     [rbp+57h+h], rax
0x1800e266e  call    cs:__imp_SelectObject
0x1800e2674  mov     edx, 1; l
0x1800e2679  mov     rcx, r14; hdc
0x1800e267c  mov     [rbp+57h+ppvBits], rax
0x1800e2680  call    cs:__imp_SetLayout
0x1800e2686  test    r13d, r13d
0x1800e2689  jz      short loc_1800E26DA
0x1800e268b  mov     ecx, dword ptr [rbp+57h+pv+4]
0x1800e268e  xor     r15d, r15d
0x1800e2691  test    ecx, ecx
0x1800e2693  jle     short loc_1800E2710
0x1800e2695  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800e2698  sub     ecx, r12d
0x1800e269b  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1800e26a3  sub     ecx, r15d
0x1800e26a6  mov     [rsp+0F0h+y1], 0; y1
0x1800e26ae  mov     edx, ecx; x
0x1800e26b0  mov     [rsp+0F0h+x1], r15d; x1
0x1800e26b5  mov     rcx, r14; hdc
0x1800e26b8  mov     qword ptr [rsp+0F0h+offset], rbx; hdcSrc
0x1800e26bd  mov     r9d, r12d; cx
0x1800e26c0  xor     r8d, r8d; y
0x1800e26c3  mov     dword ptr [rsp+0F0h+hSection], eax; cy
0x1800e26c7  call    cs:__imp_BitBlt
0x1800e26cd  mov     ecx, dword ptr [rbp+57h+pv+4]
0x1800e26d0  add     r15d, r12d
0x1800e26d3  cmp     r15d, ecx
0x1800e26d6  jl      short loc_1800E2695
0x1800e26d8  jmp     short loc_1800E2710
0x1800e26da  mov     eax, dword ptr [rbp+57h+pv+8]
0x1800e26dd  xor     r8d, r8d; y
0x1800e26e0  mov     r9d, dword ptr [rbp+57h+pv+4]; cx
0x1800e26e4  xor     edx, edx; x
0x1800e26e6  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1800e26ee  mov     rcx, r14; hdc
0x1800e26f1  mov     [rsp+0F0h+y1], 0; y1
0x1800e26f9  mov     [rsp+0F0h+x1], 0; x1
0x1800e2701  mov     qword ptr [rsp+0F0h+offset], rbx; hdcSrc
0x1800e2706  mov     dword ptr [rsp+0F0h+hSection], eax; cy
0x1800e270a  call    cs:__imp_BitBlt
0x1800e2710  mov     rdx, [rbp+57h+h]; h
0x1800e2714  mov     rcx, rbx; hdc
0x1800e2717  call    cs:__imp_SelectObject
0x1800e271d  mov     rdx, [rbp+57h+ppvBits]; h
0x1800e2721  mov     rcx, rbx; hdc
0x1800e2724  call    cs:__imp_SelectObject
0x1800e272a  mov     rcx, r14; hdc
0x1800e272d  call    cs:__imp_DeleteDC
0x1800e2733  mov     rcx, rbx; hdc
0x1800e2736  call    cs:__imp_DeleteDC
0x1800e273c  mov     rdx, rdi; hDC
0x1800e273f  xor     ecx, ecx; hWnd
0x1800e2741  call    cs:__imp_ReleaseDC
0x1800e2747  mov     rax, rsi
0x1800e274a  jmp     loc_1800E25AB
```
