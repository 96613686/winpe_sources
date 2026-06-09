# DoExtSelectClipRgn

- ea: `0x1801443b8`
- end: `0x18014466b`
- name: `DoExtSelectClipRgn`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18013fb70`

## callees

- `0x1800afb24`
- `0x1800afe7c`
- `0x1800b12a8`
- `0x1800b2190`
- `0x1800b2b34`
- `0x18013e8d0`
- `0x18013ec88`
- `0x18013f024`
- `0x1801443b8`
- `0x180145360`

## import_xrefs

- `GDI32!ExtCreateRegion` at `0x180144601`
- `GDI32!ExtCreateRegion` at `0x180144601`
- `GDI32!ExtSelectClipRgn` at `0x18014454d`
- `GDI32!ExtSelectClipRgn` at `0x1801445b0`
- `GDI32!ExtSelectClipRgn` at `0x18014461f`
- `GDI32!ExtSelectClipRgn` at `0x18014454d`
- `GDI32!ExtSelectClipRgn` at `0x1801445b0`
- `GDI32!ExtSelectClipRgn` at `0x18014461f`
- `GDI32!DeleteObject` at `0x1801445c1`
- `GDI32!DeleteObject` at `0x180144630`
- `GDI32!DeleteObject` at `0x1801445c1`
- `GDI32!DeleteObject` at `0x180144630`
- `GDI32!CreateRectRgn` at `0x18014458b`
- `GDI32!CreateRectRgn` at `0x18014458b`

## pseudocode

```c
__int64 __fastcall DoExtSelectClipRgn(__int64 a1, DWORD a2, const RGNDATA *a3, int a4)
{
  int v4; // eax
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // ebp
  int v12; // eax
  __int64 v14; // rdx
  int v15; // r15d
  HRGN RectRgn; // rax
  HRGN v17; // r15
  int v18; // ebx
  const XFORM *v19; // rcx
  HRGN Region; // rax
  HRGN v21; // rbp
  int v22; // ebx
  __int16 v23; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 484);
  if ( v4 == 1 )
  {
    *(_DWORD *)(a1 + 484) = 2;
    if ( (unsigned int)DoRemoveObjects() )
    {
      DoRestoreDC(a1, (unsigned int)(*(_DWORD *)(a1 + 488) - *(_DWORD *)(a1 + 452)), v9);
      v10 = DoMoveTo(a1, *(unsigned int *)(a1 + 476), *(unsigned int *)(a1 + 480));
      v23 = 0;
      v11 = v10;
      if ( (unsigned int)bEmitWin16Escape(a1, 38, 2, &v23) )
      {
        v23 = 0;
        v12 = bEmitWin16Escape(a1, 4097, 2, &v23);
        goto LABEL_5;
      }
    }
    return 0;
  }
  v23 = 1;
  if ( v4 == 3 )
  {
    v14 = *(unsigned int *)(a1 + 472);
    *(_DWORD *)(a1 + 484) = 0;
    *(_QWORD *)(a1 + 528) = 0;
    v11 = DoSetRop2(a1, v14);
    if ( (unsigned int)bEmitWin16Escape(a1, 4097, 2, &v23) )
    {
      v12 = bW16Emit5(a1, 1574, 263, 20560, 20052, 6, 15);
LABEL_5:
      if ( v12 )
        return v11;
    }
    return 0;
  }
  v15 = bNoDCRgn(a1, 1);
  while ( *(int *)(a1 + 456) > 0 )
  {
    bEmitWin16Escape(a1, 4097, 2, &v23);
    --*(_DWORD *)(a1 + 456);
  }
  if ( a2 )
  {
    if ( v15 )
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
  if ( v15 )
    return 1;
  ExtSelectClipRgn(*(HDC *)(a1 + 40), 0, a4);
  return bW16Emit1(a1, 300, 0);
}

```

## disassembly

```asm
0x1801443b8  mov     [rsp+arg_8], rbx
0x1801443bd  mov     [rsp+arg_10], rbp
0x1801443c2  mov     [rsp+arg_18], rsi
0x1801443c7  push    rdi
0x1801443c8  push    r12
0x1801443ca  push    r13
0x1801443cc  push    r14
0x1801443ce  push    r15
0x1801443d0  sub     rsp, 40h
0x1801443d4  mov     eax, [rcx+1E4h]
0x1801443da  mov     r12d, 1
0x1801443e0  mov     r13d, r9d
0x1801443e3  mov     rbp, r8
0x1801443e6  mov     r14d, edx
0x1801443e9  mov     rdi, rcx
0x1801443ec  cmp     eax, r12d
0x1801443ef  jnz     loc_180144483
0x1801443f5  lea     ebx, [r12+1]
0x1801443fa  mov     [rcx+1E4h], ebx
0x180144400  call    DoRemoveObjects
0x180144405  xor     esi, esi
0x180144407  test    eax, eax
0x180144409  jz      loc_18014464A
0x18014440f  mov     edx, [rdi+1E8h]
0x180144415  mov     rcx, rdi
0x180144418  sub     edx, [rdi+1C4h]
0x18014441e  call    DoRestoreDC
0x180144423  mov     r8d, [rdi+1E0h]
0x18014442a  mov     rcx, rdi
0x18014442d  mov     edx, [rdi+1DCh]
0x180144433  call    DoMoveTo
0x180144438  mov     r8d, ebx
0x18014443b  mov     [rsp+68h+arg_0], si
0x180144440  lea     edx, [rbx+24h]
0x180144443  mov     rcx, rdi
0x180144446  lea     r9, [rsp+68h+arg_0]
0x18014444b  mov     ebp, eax
0x18014444d  call    bEmitWin16Escape
0x180144452  test    eax, eax
0x180144454  jz      loc_18014464A
0x18014445a  mov     r8d, ebx
0x18014445d  mov     [rsp+68h+arg_0], si
0x180144462  mov     edx, 1001h
0x180144467  lea     r9, [rsp+68h+arg_0]
0x18014446c  mov     rcx, rdi
0x18014446f  call    bEmitWin16Escape
0x180144474  test    eax, eax
0x180144476  jz      loc_18014464A
0x18014447c  mov     eax, ebp
0x18014447e  jmp     loc_18014464C
0x180144483  mov     [rsp+68h+arg_0], r12w
0x180144489  cmp     eax, 3
0x18014448c  jnz     short loc_1801444FB
0x18014448e  mov     edx, [rcx+1D8h]
0x180144494  xor     esi, esi
0x180144496  mov     [rcx+1E4h], esi
0x18014449c  mov     [rcx+210h], rsi
0x1801444a3  call    DoSetRop2
0x1801444a8  mov     edx, 1001h
0x1801444ad  lea     r8d, [rsi+2]
0x1801444b1  lea     r9, [rsp+68h+arg_0]
0x1801444b6  mov     rcx, rdi
0x1801444b9  mov     ebp, eax
0x1801444bb  call    bEmitWin16Escape
0x1801444c0  test    eax, eax
0x1801444c2  jz      loc_18014464A
0x1801444c8  mov     [rsp+68h+var_38], 0Fh
0x1801444cf  mov     edx, 626h
0x1801444d4  mov     [rsp+68h+var_40], 6
0x1801444db  mov     r9d, 5050h
0x1801444e1  mov     r8d, 107h
0x1801444e7  mov     [rsp+68h+var_48], 4E54h
0x1801444ee  mov     rcx, rdi
0x1801444f1  call    bW16Emit5
0x1801444f6  jmp     loc_180144474
0x1801444fb  mov     edx, r12d
0x1801444fe  call    bNoDCRgn
0x180144503  mov     r15d, eax
0x180144506  xor     esi, esi
0x180144508  mov     ebx, 2
0x18014450d  jmp     short loc_18014452A
0x18014450f  mov     r8d, ebx
0x180144512  lea     r9, [rsp+68h+arg_0]
0x180144517  mov     edx, 1001h
0x18014451c  mov     rcx, rdi
0x18014451f  call    bEmitWin16Escape
0x180144524  dec     dword ptr [rdi+1C8h]
0x18014452a  cmp     [rdi+1C8h], esi
0x180144530  jg      short loc_18014450F
0x180144532  test    r14d, r14d
0x180144535  jnz     short loc_18014456E
0x180144537  test    r15d, r15d
0x18014453a  jz      short loc_180144544
0x18014453c  mov     eax, r12d
0x18014453f  jmp     loc_18014464C
0x180144544  mov     rcx, [rdi+28h]; hdc
0x180144548  mov     r8d, r13d; mode
0x18014454b  xor     edx, edx; hrgn
0x18014454d  call    cs:__imp_ExtSelectClipRgn
0x180144554  nop     dword ptr [rax+rax+00h]
0x180144559  xor     r8d, r8d
0x18014455c  mov     edx, 12Ch
0x180144561  mov     rcx, rdi
0x180144564  call    bW16Emit1
0x180144569  jmp     loc_18014464C
0x18014456e  test    r15d, r15d
0x180144571  jz      short loc_1801445D1
0x180144573  lea     eax, [r13-2]
0x180144577  cmp     eax, ebx
0x180144579  ja      short loc_1801445D1
0x18014457b  mov     r8d, 7FFFh; x2
0x180144581  mov     ecx, 0FFFF8000h; x1
0x180144586  mov     r9d, r8d; y2
0x180144589  mov     edx, ecx; y1
0x18014458b  call    cs:__imp_CreateRectRgn
0x180144592  nop     dword ptr [rax+rax+00h]
0x180144597  mov     r15, rax
0x18014459a  test    rax, rax
0x18014459d  jz      loc_18014464A
0x1801445a3  mov     rcx, [rdi+28h]; hdc
0x1801445a7  mov     r8d, 5; mode
0x1801445ad  mov     rdx, rax; hrgn
0x1801445b0  call    cs:__imp_ExtSelectClipRgn
0x1801445b7  nop     dword ptr [rax+rax+00h]
0x1801445bc  mov     rcx, r15; ho
0x1801445bf  mov     ebx, eax
0x1801445c1  call    cs:__imp_DeleteObject
0x1801445c8  nop     dword ptr [rax+rax+00h]
0x1801445cd  test    ebx, ebx
0x1801445cf  jz      short loc_18014464A
0x1801445d1  cmp     cs:pfnSetVirtualResolution, rsi
0x1801445d8  jz      short loc_1801445DE
0x1801445da  xor     ecx, ecx
0x1801445dc  jmp     short loc_1801445FB
0x1801445de  cmp     r14d, 20h ; ' '
0x1801445e2  jb      short loc_18014464A
0x1801445e4  mov     eax, [rbp+18h]
0x1801445e7  cmp     [rbp+10h], eax
0x1801445ea  jg      short loc_18014464A
0x1801445ec  mov     eax, [rbp+1Ch]
0x1801445ef  cmp     [rbp+14h], eax
0x1801445f2  jg      short loc_18014464A
0x1801445f4  lea     rcx, [rdi+12Ch]; lpx
0x1801445fb  mov     r8, rbp; lpData
0x1801445fe  mov     edx, r14d; nCount
0x180144601  call    cs:__imp_ExtCreateRegion
0x180144608  nop     dword ptr [rax+rax+00h]
0x18014460d  mov     rbp, rax
0x180144610  test    rax, rax
0x180144613  jz      short loc_18014464A
0x180144615  mov     rcx, [rdi+28h]; hdc
0x180144619  mov     r8d, r13d; mode
0x18014461c  mov     rdx, rax; hrgn
0x18014461f  call    cs:__imp_ExtSelectClipRgn
0x180144626  nop     dword ptr [rax+rax+00h]
0x18014462b  mov     rcx, rbp; ho
0x18014462e  mov     ebx, eax
0x180144630  call    cs:__imp_DeleteObject
0x180144637  nop     dword ptr [rax+rax+00h]
0x18014463c  test    ebx, ebx
0x18014463e  jz      short loc_18014464A
0x180144640  mov     rcx, rdi
0x180144643  call    bDumpDCClipping
0x180144648  jmp     short loc_18014464C
0x18014464a  xor     eax, eax
0x18014464c  lea     r11, [rsp+68h+var_28]
0x180144651  mov     rbx, [r11+38h]
0x180144655  mov     rbp, [r11+40h]
0x180144659  mov     rsi, [r11+48h]
0x18014465d  mov     rsp, r11
0x180144660  pop     r15
0x180144662  pop     r14
0x180144664  pop     r13
0x180144666  pop     r12
0x180144668  pop     rdi
0x180144669  retn
```
