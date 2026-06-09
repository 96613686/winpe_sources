# DrawInsertMark

- ea: `0x180025164`
- end: `0x180025362`
- name: `DrawInsertMark`
- size: `510`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180028594`
- `0x18007c6c8`

## callees

- `0x1800115f0`
- `0x180025164`

## import_xrefs

- `GDI32!SelectObject` at `0x1800251bc`
- `GDI32!SelectObject` at `0x18002532f`
- `GDI32!SelectObject` at `0x1800251bc`
- `GDI32!SelectObject` at `0x18002532f`
- `GDI32!DeleteObject` at `0x180025338`
- `GDI32!DeleteObject` at `0x180025338`
- `GDI32!GetStockObject` at `0x1800251ad`
- `GDI32!GetStockObject` at `0x1800251ad`
- `GDI32!CreatePen` at `0x18002519c`
- `GDI32!CreatePen` at `0x18002519c`
- `GDI32!Polyline` at `0x180025213`
- `GDI32!Polyline` at `0x18002524a`
- `GDI32!Polyline` at `0x1800252b6`
- `GDI32!Polyline` at `0x1800252ed`
- `GDI32!Polyline` at `0x180025322`
- `GDI32!Polyline` at `0x180025213`
- `GDI32!Polyline` at `0x18002524a`
- `GDI32!Polyline` at `0x1800252b6`
- `GDI32!Polyline` at `0x1800252ed`
- `GDI32!Polyline` at `0x180025322`

## pseudocode

```c
BOOL __fastcall DrawInsertMark(HDC hdc, LONG *a2, int a3, COLORREF a4)
{
  void *Pen; // r15
  int v8; // eax
  LONG v9; // r14d
  LONG v10; // esi
  int v11; // ebx
  int v12; // edi
  int v13; // eax
  LONG v14; // eax
  int v15; // eax
  LONG v16; // r14d
  int v17; // esi
  int v18; // edi
  int v19; // ebx
  int v20; // eax
  LONG v21; // eax
  HGDIOBJ h; // [rsp+20h] [rbp-30h]
  POINT apt; // [rsp+28h] [rbp-28h] BYREF
  int v25; // [rsp+30h] [rbp-20h]
  int v26; // [rsp+34h] [rbp-1Ch]
  int v27; // [rsp+38h] [rbp-18h]
  int v28; // [rsp+3Ch] [rbp-14h]
  int x; // [rsp+40h] [rbp-10h]
  LONG y; // [rsp+44h] [rbp-Ch]

  Pen = CreatePen(0, 1, a4);
  if ( !Pen )
    Pen = GetStockObject(7);
  h = SelectObject(hdc, Pen);
  if ( a3 )
  {
    v8 = a2[2] + *a2;
    v26 = a2[1];
    v28 = v26;
    apt.y = v26 + 2;
    y = v26 + 2;
    v9 = v8 / 2;
    x = v8 / 2;
    v10 = v8 / 2 + 1;
    v11 = v8 / 2 + 3;
    apt.x = v10;
    v12 = v8 / 2 - 2;
    v25 = v11;
    v27 = v12;
    Polyline(hdc, &apt, 4);
    v13 = a2[3] - 1;
    apt.y = a2[1];
    y = apt.y;
    v26 = v13;
    v28 = v13;
    apt.x = v9;
    v25 = v9;
    v27 = v10;
    x = v10;
    Polyline(hdc, &apt, 4);
    v14 = a2[3];
    apt.x = v10;
    v25 = v11;
    v27 = v12;
    x = v9;
    apt.y = v14 - 3;
    v26 = v14 - 1;
    v28 = v14 - 1;
    y = v14 - 3;
  }
  else
  {
    v15 = a2[1] + a2[3];
    v25 = *a2;
    v27 = v25;
    apt.x = v25 + 2;
    x = v25 + 2;
    v16 = v15 / 2;
    apt.y = v15 / 2;
    v17 = v15 / 2 - 2;
    v18 = v15 / 2 + 3;
    v26 = v17;
    v19 = v15 / 2 + 1;
    v28 = v18;
    y = v19;
    Polyline(hdc, &apt, 4);
    v20 = a2[2] - 1;
    apt.x = *a2;
    x = apt.x;
    v25 = v20;
    v27 = v20;
    apt.y = v16;
    v26 = v16;
    v28 = v19;
    y = v19;
    Polyline(hdc, &apt, 4);
    v21 = a2[2];
    apt.y = v16;
    v26 = v17;
    v28 = v18;
    y = v19;
    apt.x = v21 - 3;
    v25 = v21 - 1;
    v27 = v21 - 1;
    x = v21 - 3;
  }
  Polyline(hdc, &apt, 4);
  SelectObject(hdc, h);
  return DeleteObject(Pen);
}

```

## disassembly

```asm
0x180025164  mov     [rsp-38h+arg_8], rbx
0x180025169  push    rbp
0x18002516a  push    rsi
0x18002516b  push    rdi
0x18002516c  push    r12
0x18002516e  push    r13
0x180025170  push    r14
0x180025172  push    r15
0x180025174  mov     rbp, rsp
0x180025177  sub     rsp, 50h
0x18002517b  mov     rax, cs:__security_cookie
0x180025182  xor     rax, rsp
0x180025185  mov     [rbp+var_8], rax
0x180025189  mov     ebx, r8d
0x18002518c  mov     r13, rdx
0x18002518f  mov     r12, rcx
0x180025192  mov     r8d, r9d; color
0x180025195  mov     edx, 1; cWidth
0x18002519a  xor     ecx, ecx; iStyle
0x18002519c  call    cs:__imp_CreatePen
0x1800251a2  mov     r15, rax
0x1800251a5  test    rax, rax
0x1800251a8  jnz     short loc_1800251B6
0x1800251aa  lea     ecx, [rax+7]; i
0x1800251ad  call    cs:__imp_GetStockObject
0x1800251b3  mov     r15, rax
0x1800251b6  mov     rdx, r15; h
0x1800251b9  mov     rcx, r12; hdc
0x1800251bc  call    cs:__imp_SelectObject
0x1800251c2  mov     [rbp+h], rax
0x1800251c6  mov     r8d, 4; cpt
0x1800251cc  test    ebx, ebx
0x1800251ce  jz      loc_180025277
0x1800251d4  mov     ecx, [r13+4]
0x1800251d8  mov     eax, [r13+0]
0x1800251dc  add     eax, [r13+8]
0x1800251e0  cdq
0x1800251e1  mov     [rbp+var_1C], ecx
0x1800251e4  sub     eax, edx
0x1800251e6  mov     [rbp+var_14], ecx
0x1800251e9  sar     eax, 1
0x1800251eb  lea     edx, [rcx+2]
0x1800251ee  mov     [rbp+apt.y], edx
0x1800251f1  mov     rcx, r12; hdc
0x1800251f4  mov     [rbp+var_C], edx
0x1800251f7  mov     r14d, eax
0x1800251fa  lea     rdx, [rbp+apt]; apt
0x1800251fe  mov     [rbp+var_10], eax
0x180025201  lea     esi, [rax+1]
0x180025204  lea     ebx, [rax+3]
0x180025207  mov     [rbp+apt.x], esi
0x18002520a  lea     edi, [rax-2]
0x18002520d  mov     [rbp+var_20], ebx
0x180025210  mov     [rbp+var_18], edi
0x180025213  call    cs:__imp_Polyline
0x180025219  mov     ecx, [r13+4]
0x18002521d  lea     rdx, [rbp+apt]; apt
0x180025221  mov     eax, [r13+0Ch]
0x180025225  mov     r8d, 4; cpt
0x18002522b  dec     eax
0x18002522d  mov     [rbp+apt.y], ecx
0x180025230  mov     [rbp+var_C], ecx
0x180025233  mov     rcx, r12; hdc
0x180025236  mov     [rbp+var_1C], eax
0x180025239  mov     [rbp+var_14], eax
0x18002523c  mov     [rbp+apt.x], r14d
0x180025240  mov     [rbp+var_20], r14d
0x180025244  mov     [rbp+var_18], esi
0x180025247  mov     [rbp+var_10], esi
0x18002524a  call    cs:__imp_Polyline
0x180025250  mov     eax, [r13+0Ch]
0x180025254  mov     [rbp+apt.x], esi
0x180025257  mov     [rbp+var_20], ebx
0x18002525a  mov     [rbp+var_18], edi
0x18002525d  lea     ecx, [rax-3]
0x180025260  mov     [rbp+var_10], r14d
0x180025264  dec     eax
0x180025266  mov     [rbp+apt.y], ecx
0x180025269  mov     [rbp+var_1C], eax
0x18002526c  mov     [rbp+var_14], eax
0x18002526f  mov     [rbp+var_C], ecx
0x180025272  jmp     loc_180025315
0x180025277  mov     ecx, [r13+0]
0x18002527b  mov     eax, [r13+0Ch]
0x18002527f  add     eax, [r13+4]
0x180025283  cdq
0x180025284  mov     [rbp+var_20], ecx
0x180025287  sub     eax, edx
0x180025289  mov     [rbp+var_18], ecx
0x18002528c  sar     eax, 1
0x18002528e  lea     edx, [rcx+2]
0x180025291  mov     [rbp+apt.x], edx
0x180025294  mov     rcx, r12; hdc
0x180025297  mov     [rbp+var_10], edx
0x18002529a  mov     r14d, eax
0x18002529d  lea     rdx, [rbp+apt]; apt
0x1800252a1  mov     [rbp+apt.y], eax
0x1800252a4  lea     esi, [rax-2]
0x1800252a7  lea     edi, [rax+3]
0x1800252aa  mov     [rbp+var_1C], esi
0x1800252ad  lea     ebx, [rax+1]
0x1800252b0  mov     [rbp+var_14], edi
0x1800252b3  mov     [rbp+var_C], ebx
0x1800252b6  call    cs:__imp_Polyline
0x1800252bc  mov     ecx, [r13+0]
0x1800252c0  lea     rdx, [rbp+apt]; apt
0x1800252c4  mov     eax, [r13+8]
0x1800252c8  mov     r8d, 4; cpt
0x1800252ce  dec     eax
0x1800252d0  mov     [rbp+apt.x], ecx
0x1800252d3  mov     [rbp+var_10], ecx
0x1800252d6  mov     rcx, r12; hdc
0x1800252d9  mov     [rbp+var_20], eax
0x1800252dc  mov     [rbp+var_18], eax
0x1800252df  mov     [rbp+apt.y], r14d
0x1800252e3  mov     [rbp+var_1C], r14d
0x1800252e7  mov     [rbp+var_14], ebx
0x1800252ea  mov     [rbp+var_C], ebx
0x1800252ed  call    cs:__imp_Polyline
0x1800252f3  mov     eax, [r13+8]
0x1800252f7  mov     [rbp+apt.y], r14d
0x1800252fb  mov     [rbp+var_1C], esi
0x1800252fe  mov     [rbp+var_14], edi
0x180025301  lea     edx, [rax-3]
0x180025304  mov     [rbp+var_C], ebx
0x180025307  dec     eax
0x180025309  mov     [rbp+apt.x], edx
0x18002530c  mov     [rbp+var_20], eax
0x18002530f  mov     [rbp+var_18], eax
0x180025312  mov     [rbp+var_10], edx
0x180025315  mov     r8d, 4; cpt
0x18002531b  lea     rdx, [rbp+apt]; apt
0x18002531f  mov     rcx, r12; hdc
0x180025322  call    cs:__imp_Polyline
0x180025328  mov     rdx, [rbp+h]; h
0x18002532c  mov     rcx, r12; hdc
0x18002532f  call    cs:__imp_SelectObject
0x180025335  mov     rcx, r15; ho
0x180025338  call    cs:__imp_DeleteObject
0x18002533e  mov     rcx, [rbp+var_8]
0x180025342  xor     rcx, rsp; StackCookie
0x180025345  call    __security_check_cookie
0x18002534a  mov     rbx, [rsp+50h+arg_8]
0x180025352  add     rsp, 50h
0x180025356  pop     r15
0x180025358  pop     r14
0x18002535a  pop     r13
0x18002535c  pop     r12
0x18002535e  pop     rdi
0x18002535f  pop     rsi
0x180025360  pop     rbp
0x180025361  retn
```
