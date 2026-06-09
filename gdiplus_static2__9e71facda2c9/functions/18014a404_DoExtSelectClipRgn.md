# DoExtSelectClipRgn

- ea: `0x18014a404`
- end: `0x18014a6be`
- name: `DoExtSelectClipRgn`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180147be0`

## callees

- `0x1800c5768`
- `0x1800c5a78`
- `0x1800c6048`
- `0x1800c807c`
- `0x1800c8944`
- `0x1800f3550`
- `0x1801470b8`
- `0x1801471ec`
- `0x18014a404`
- `0x18014b344`

## import_xrefs

- `GDI32!ExtCreateRegion` at `0x18014a661`
- `GDI32!ExtCreateRegion` at `0x18014a661`
- `GDI32!ExtSelectClipRgn` at `0x18014a5ad`
- `GDI32!ExtSelectClipRgn` at `0x18014a610`
- `GDI32!ExtSelectClipRgn` at `0x18014a67f`
- `GDI32!ExtSelectClipRgn` at `0x18014a5ad`
- `GDI32!ExtSelectClipRgn` at `0x18014a610`
- `GDI32!ExtSelectClipRgn` at `0x18014a67f`
- `GDI32!DeleteObject` at `0x18014a621`
- `GDI32!DeleteObject` at `0x18014a690`
- `GDI32!DeleteObject` at `0x18014a621`
- `GDI32!DeleteObject` at `0x18014a690`
- `GDI32!CreateRectRgn` at `0x18014a5eb`
- `GDI32!CreateRectRgn` at `0x18014a5eb`

## pseudocode

```c
__int64 __fastcall DoExtSelectClipRgn(__int64 a1, DWORD a2, const RGNDATA *a3, int a4)
{
  int v4; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebp
  int v11; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  HRGN RectRgn; // rax
  HRGN v17; // r15
  int v18; // ebx
  const XFORM *v19; // rcx
  HRGN Region; // rax
  HRGN v21; // rbp
  int v22; // ebx
  __int16 v23; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 484);
  if ( v4 == 1 )
  {
    *(_DWORD *)(a1 + 484) = 2;
    if ( (unsigned int)DoRemoveObjects() )
    {
      DoRestoreDC(a1, (unsigned int)(*(_DWORD *)(a1 + 488) - *(_DWORD *)(a1 + 452)));
      v9 = DoMoveTo(a1, *(unsigned int *)(a1 + 476), *(unsigned int *)(a1 + 480));
      v23 = 0;
      v10 = v9;
      if ( (unsigned int)bEmitWin16Escape(a1, 38, 2, &v23) )
      {
        v23 = 0;
        v11 = bEmitWin16Escape(a1, 4097, 2, &v23);
        goto LABEL_5;
      }
    }
    return 0;
  }
  v23 = 1;
  if ( v4 == 3 )
  {
    v13 = *(unsigned int *)(a1 + 472);
    *(_DWORD *)(a1 + 484) = 0;
    *(_QWORD *)(a1 + 528) = 0;
    v10 = DoSetRop2(a1, v13);
    if ( (unsigned int)bEmitWin16Escape(a1, 4097, 2, &v23) )
    {
      v11 = bW16Emit5(a1, 1574, 263, 20560, 20052, 6, 15);
LABEL_5:
      if ( v11 )
        return v10;
    }
    return 0;
  }
  v14 = bNoDCRgn(a1, 1);
  if ( *(int *)(a1 + 456) > 0 )
  {
    do
    {
      bEmitWin16Escape(a1, 4097, 2, &v23);
      v15 = *(_DWORD *)(a1 + 456) - 1;
      *(_DWORD *)(a1 + 456) = v15;
    }
    while ( v15 > 0 );
  }
  if ( a2 )
  {
    if ( v14 )
    {
      if ( (unsigned int)(a4 - 2) <= 2 )
      {
        RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
        v17 = RectRgn;
        if ( !RectRgn )
          return 0;
        v18 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
        DeleteObject(v17);
        if ( !v18 )
          return 0;
      }
    }
    if ( pfnSetVirtualResolution )
    {
      v19 = 0;
    }
    else
    {
      if ( a2 < 0x20 || a3->rdh.rcBound.left > a3->rdh.rcBound.right || a3->rdh.rcBound.top > a3->rdh.rcBound.bottom )
        return 0;
      v19 = (const XFORM *)(a1 + 300);
    }
    Region = ExtCreateRegion(v19, a2, a3);
    v21 = Region;
    if ( Region )
    {
      v22 = ExtSelectClipRgn(*(HDC *)(a1 + 40), Region, a4);
      DeleteObject(v21);
      if ( v22 )
        return bDumpDCClipping(a1);
    }
    return 0;
  }
  if ( v14 )
    return 1;
  ExtSelectClipRgn(*(HDC *)(a1 + 40), 0, a4);
  return bW16Emit1(a1, 300, 0);
}

```

## disassembly

```asm
0x18014a404  push    rbx
0x18014a406  push    rbp
0x18014a407  push    rsi
0x18014a408  push    rdi
0x18014a409  push    r12
0x18014a40b  push    r13
0x18014a40d  push    r14
0x18014a40f  push    r15
0x18014a411  sub     rsp, 48h
0x18014a415  mov     eax, [rcx+1E4h]
0x18014a41b  mov     r12d, 1
0x18014a421  mov     r13d, r9d
0x18014a424  mov     rbp, r8
0x18014a427  mov     r14d, edx
0x18014a42a  mov     rdi, rcx
0x18014a42d  cmp     eax, r12d
0x18014a430  jnz     loc_18014A4D0
0x18014a436  lea     ebx, [r12+1]
0x18014a43b  mov     [rcx+1E4h], ebx
0x18014a441  call    DoRemoveObjects
0x18014a446  xor     esi, esi
0x18014a448  test    eax, eax
0x18014a44a  jz      loc_18014A6AA
0x18014a450  mov     edx, [rdi+1E8h]
0x18014a456  mov     rcx, rdi
0x18014a459  sub     edx, [rdi+1C4h]
0x18014a45f  call    DoRestoreDC
0x18014a464  mov     r8d, [rdi+1E0h]
0x18014a46b  mov     rcx, rdi
0x18014a46e  mov     edx, [rdi+1DCh]
0x18014a474  call    DoMoveTo
0x18014a479  mov     r8d, ebx
0x18014a47c  mov     [rsp+88h+arg_0], si
0x18014a484  lea     edx, [rbx+24h]
0x18014a487  mov     rcx, rdi
0x18014a48a  lea     r9, [rsp+88h+arg_0]
0x18014a492  mov     ebp, eax
0x18014a494  call    bEmitWin16Escape
0x18014a499  test    eax, eax
0x18014a49b  jz      loc_18014A6AA
0x18014a4a1  mov     r8d, ebx
0x18014a4a4  mov     [rsp+88h+arg_0], si
0x18014a4ac  mov     edx, 1001h
0x18014a4b1  lea     r9, [rsp+88h+arg_0]
0x18014a4b9  mov     rcx, rdi
0x18014a4bc  call    bEmitWin16Escape
0x18014a4c1  test    eax, eax
0x18014a4c3  jz      loc_18014A6AA
0x18014a4c9  mov     eax, ebp
0x18014a4cb  jmp     loc_18014A6AC
0x18014a4d0  mov     [rsp+88h+arg_0], r12w
0x18014a4d9  cmp     eax, 3
0x18014a4dc  jnz     short loc_18014A54E
0x18014a4de  mov     edx, [rcx+1D8h]
0x18014a4e4  xor     esi, esi
0x18014a4e6  mov     [rcx+1E4h], esi
0x18014a4ec  mov     [rcx+210h], rsi
0x18014a4f3  call    DoSetRop2
0x18014a4f8  mov     edx, 1001h
0x18014a4fd  lea     r8d, [rsi+2]
0x18014a501  lea     r9, [rsp+88h+arg_0]
0x18014a509  mov     rcx, rdi
0x18014a50c  mov     ebp, eax
0x18014a50e  call    bEmitWin16Escape
0x18014a513  test    eax, eax
0x18014a515  jz      loc_18014A6AA
0x18014a51b  mov     [rsp+88h+var_58], 0Fh
0x18014a522  mov     edx, 626h
0x18014a527  mov     [rsp+88h+var_60], 6
0x18014a52e  mov     r9d, 5050h
0x18014a534  mov     r8d, 107h
0x18014a53a  mov     [rsp+88h+var_68], 4E54h
0x18014a541  mov     rcx, rdi
0x18014a544  call    bW16Emit5
0x18014a549  jmp     loc_18014A4C1
0x18014a54e  mov     edx, r12d
0x18014a551  call    bNoDCRgn
0x18014a556  xor     esi, esi
0x18014a558  mov     r15d, eax
0x18014a55b  mov     ebx, 2
0x18014a560  cmp     [rdi+1C8h], esi
0x18014a566  jle     short loc_18014A592
0x18014a568  mov     r8d, ebx
0x18014a56b  lea     r9, [rsp+88h+arg_0]
0x18014a573  mov     edx, 1001h
0x18014a578  mov     rcx, rdi
0x18014a57b  call    bEmitWin16Escape
0x18014a580  mov     ecx, [rdi+1C8h]
0x18014a586  dec     ecx
0x18014a588  mov     [rdi+1C8h], ecx
0x18014a58e  test    ecx, ecx
0x18014a590  jg      short loc_18014A568
0x18014a592  test    r14d, r14d
0x18014a595  jnz     short loc_18014A5CE
0x18014a597  test    r15d, r15d
0x18014a59a  jz      short loc_18014A5A4
0x18014a59c  mov     eax, r12d
0x18014a59f  jmp     loc_18014A6AC
0x18014a5a4  mov     rcx, [rdi+28h]; hdc
0x18014a5a8  mov     r8d, r13d; mode
0x18014a5ab  xor     edx, edx; hrgn
0x18014a5ad  call    cs:__imp_ExtSelectClipRgn
0x18014a5b4  nop     dword ptr [rax+rax+00h]
0x18014a5b9  xor     r8d, r8d
0x18014a5bc  mov     edx, 12Ch
0x18014a5c1  mov     rcx, rdi
0x18014a5c4  call    bW16Emit1
0x18014a5c9  jmp     loc_18014A6AC
0x18014a5ce  test    r15d, r15d
0x18014a5d1  jz      short loc_18014A631
0x18014a5d3  lea     eax, [r13-2]
0x18014a5d7  cmp     eax, ebx
0x18014a5d9  ja      short loc_18014A631
0x18014a5db  mov     r8d, 7FFFh; x2
0x18014a5e1  mov     ecx, 0FFFF8000h; x1
0x18014a5e6  mov     r9d, r8d; y2
0x18014a5e9  mov     edx, ecx; y1
0x18014a5eb  call    cs:__imp_CreateRectRgn
0x18014a5f2  nop     dword ptr [rax+rax+00h]
0x18014a5f7  mov     r15, rax
0x18014a5fa  test    rax, rax
0x18014a5fd  jz      loc_18014A6AA
0x18014a603  mov     rcx, [rdi+28h]; hdc
0x18014a607  mov     r8d, 5; mode
0x18014a60d  mov     rdx, rax; hrgn
0x18014a610  call    cs:__imp_ExtSelectClipRgn
0x18014a617  nop     dword ptr [rax+rax+00h]
0x18014a61c  mov     rcx, r15; ho
0x18014a61f  mov     ebx, eax
0x18014a621  call    cs:__imp_DeleteObject
0x18014a628  nop     dword ptr [rax+rax+00h]
0x18014a62d  test    ebx, ebx
0x18014a62f  jz      short loc_18014A6AA
0x18014a631  cmp     cs:pfnSetVirtualResolution, rsi
0x18014a638  jz      short loc_18014A63E
0x18014a63a  xor     ecx, ecx
0x18014a63c  jmp     short loc_18014A65B
0x18014a63e  cmp     r14d, 20h ; ' '
0x18014a642  jb      short loc_18014A6AA
0x18014a644  mov     eax, [rbp+18h]
0x18014a647  cmp     [rbp+10h], eax
0x18014a64a  jg      short loc_18014A6AA
0x18014a64c  mov     eax, [rbp+1Ch]
0x18014a64f  cmp     [rbp+14h], eax
0x18014a652  jg      short loc_18014A6AA
0x18014a654  lea     rcx, [rdi+12Ch]; lpx
0x18014a65b  mov     r8, rbp; lpData
0x18014a65e  mov     edx, r14d; nCount
0x18014a661  call    cs:__imp_ExtCreateRegion
0x18014a668  nop     dword ptr [rax+rax+00h]
0x18014a66d  mov     rbp, rax
0x18014a670  test    rax, rax
0x18014a673  jz      short loc_18014A6AA
0x18014a675  mov     rcx, [rdi+28h]; hdc
0x18014a679  mov     r8d, r13d; mode
0x18014a67c  mov     rdx, rax; hrgn
0x18014a67f  call    cs:__imp_ExtSelectClipRgn
0x18014a686  nop     dword ptr [rax+rax+00h]
0x18014a68b  mov     rcx, rbp; ho
0x18014a68e  mov     ebx, eax
0x18014a690  call    cs:__imp_DeleteObject
0x18014a697  nop     dword ptr [rax+rax+00h]
0x18014a69c  test    ebx, ebx
0x18014a69e  jz      short loc_18014A6AA
0x18014a6a0  mov     rcx, rdi
0x18014a6a3  call    bDumpDCClipping
0x18014a6a8  jmp     short loc_18014A6AC
0x18014a6aa  xor     eax, eax
0x18014a6ac  add     rsp, 48h
0x18014a6b0  pop     r15
0x18014a6b2  pop     r14
0x18014a6b4  pop     r13
0x18014a6b6  pop     r12
0x18014a6b8  pop     rdi
0x18014a6b9  pop     rsi
0x18014a6ba  pop     rbp
0x18014a6bb  pop     rbx
0x18014a6bc  retn
```
