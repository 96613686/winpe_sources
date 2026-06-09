# DrawGrip(HDC__ *,tagRECT const *,int)

- ea: `0x180237548`
- end: `0x180237851`
- name: `?DrawGrip@@YAHPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `777`
- prototype: `__int64 __fastcall(HDC hdc, const struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18023c8d0`

## callees

- `0x180237548`

## import_xrefs

- `GDI32!PatBlt` at `0x180237606`
- `GDI32!PatBlt` at `0x180237606`
- `GDI32!CreatePen` at `0x180237642`
- `GDI32!CreatePen` at `0x1802376e1`
- `GDI32!CreatePen` at `0x18023777a`
- `GDI32!CreatePen` at `0x180237642`
- `GDI32!CreatePen` at `0x1802376e1`
- `GDI32!CreatePen` at `0x18023777a`
- `GDI32!DeleteObject` at `0x1802376c6`
- `GDI32!DeleteObject` at `0x18023775e`
- `GDI32!DeleteObject` at `0x180237828`
- `GDI32!DeleteObject` at `0x1802376c6`
- `GDI32!DeleteObject` at `0x18023775e`
- `GDI32!DeleteObject` at `0x180237828`
- `GDI32!SelectObject` at `0x1802375d5`
- `GDI32!SelectObject` at `0x180237618`
- `GDI32!SelectObject` at `0x180237660`
- `GDI32!SelectObject` at `0x1802376b7`
- `GDI32!SelectObject` at `0x1802376ff`
- `GDI32!SelectObject` at `0x18023774f`
- `GDI32!SelectObject` at `0x180237798`
- `GDI32!SelectObject` at `0x180237819`
- `GDI32!SelectObject` at `0x1802375d5`
- `GDI32!SelectObject` at `0x180237618`
- `GDI32!SelectObject` at `0x180237660`
- `GDI32!SelectObject` at `0x1802376b7`
- `GDI32!SelectObject` at `0x1802376ff`
- `GDI32!SelectObject` at `0x18023774f`
- `GDI32!SelectObject` at `0x180237798`
- `GDI32!SelectObject` at `0x180237819`
- `GDI32!MoveToEx` at `0x180237686`
- `GDI32!MoveToEx` at `0x18023771e`
- `GDI32!MoveToEx` at `0x1802377bc`
- `GDI32!MoveToEx` at `0x1802377e8`
- `GDI32!MoveToEx` at `0x180237686`
- `GDI32!MoveToEx` at `0x18023771e`
- `GDI32!MoveToEx` at `0x1802377bc`
- `GDI32!MoveToEx` at `0x1802377e8`
- `GDI32!LineTo` at `0x18023769a`
- `GDI32!LineTo` at `0x180237732`
- `GDI32!LineTo` at `0x1802377d0`
- `GDI32!LineTo` at `0x1802377fd`
- `GDI32!LineTo` at `0x18023769a`
- `GDI32!LineTo` at `0x180237732`
- `GDI32!LineTo` at `0x1802377d0`
- `GDI32!LineTo` at `0x1802377fd`
- `USER32!GetSysColor` at `0x1802375a4`
- `USER32!GetSysColor` at `0x1802375bb`
- `USER32!GetSysColor` at `0x18023762c`
- `USER32!GetSysColor` at `0x1802375a4`
- `USER32!GetSysColor` at `0x1802375bb`
- `USER32!GetSysColor` at `0x18023762c`
- `USER32!GetSysColorBrush` at `0x180237591`
- `USER32!GetSysColorBrush` at `0x180237591`

## pseudocode

```c
__int64 __fastcall DrawGrip(HDC hdc, const struct tagRECT *a2, int a3)
{
  LONG top; // r11d
  int v5; // eax
  int v8; // ebp
  int v9; // r12d
  HBRUSH SysColorBrush; // r14
  HGDIOBJ v11; // rbx
  COLORREF v12; // eax
  HPEN Pen; // rax
  HPEN v14; // r15
  HGDIOBJ v15; // r13
  int v16; // r14d
  int i; // ebx
  HPEN v18; // rax
  HPEN v19; // r14
  HGDIOBJ v20; // rax
  LONG v21; // r15d
  void *v22; // r13
  LONG j; // ebx
  HPEN v24; // rax
  HPEN v25; // r14
  HGDIOBJ v26; // r15
  int v27; // ebx
  int v28; // edi
  DWORD SysColor; // [rsp+78h] [rbp+10h]
  DWORD color; // [rsp+80h] [rbp+18h]

  top = a2->top;
  v5 = a2->right - a2->left;
  if ( v5 >= a2->bottom - top )
    v5 = a2->bottom - top;
  v8 = v5 + a2->left;
  v9 = v5 + top;
  SysColorBrush = GetSysColorBrush(15);
  color = GetSysColor(20);
  SysColor = GetSysColor(16);
  if ( a3 )
  {
    v11 = SelectObject(hdc, SysColorBrush);
    PatBlt(hdc, a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0xF00021u);
    SelectObject(hdc, v11);
  }
  else
  {
    v12 = GetSysColor(15);
    Pen = CreatePen(0, 1, v12);
    v14 = Pen;
    if ( !Pen )
      return 0;
    v15 = SelectObject(hdc, Pen);
    v16 = a2->top + 3;
    for ( i = a2->left + 3; i < v8; i += 4 )
    {
      MoveToEx(hdc, i, v9, 0);
      LineTo(hdc, v8, v16);
      v16 += 4;
    }
    SelectObject(hdc, v15);
    DeleteObject(v14);
  }
  v18 = CreatePen(0, 1, color);
  v19 = v18;
  if ( !v18 )
    return 0;
  v20 = SelectObject(hdc, v18);
  v21 = a2->top;
  v22 = v20;
  for ( j = a2->left; j < v8; j += 4 )
  {
    MoveToEx(hdc, j, v9, 0);
    LineTo(hdc, v8, v21);
    v21 += 4;
  }
  SelectObject(hdc, v22);
  DeleteObject(v19);
  v24 = CreatePen(0, 1, SysColor);
  v25 = v24;
  if ( !v24 )
    return 0;
  v26 = SelectObject(hdc, v24);
  v27 = a2->left + 1;
  v28 = a2->top + 1;
  while ( v27 < v8 )
  {
    MoveToEx(hdc, v27, v9, 0);
    LineTo(hdc, v8, v28);
    MoveToEx(hdc, v27 + 1, v9, 0);
    LineTo(hdc, v8, v28 + 1);
    v27 += 4;
    v28 += 4;
  }
  SelectObject(hdc, v26);
  DeleteObject(v25);
  return 1;
}

```

## disassembly

```asm
0x180237548  mov     [rsp+arg_0], rbx
0x18023754d  push    rbp
0x18023754e  push    rsi
0x18023754f  push    rdi
0x180237550  push    r12
0x180237552  push    r13
0x180237554  push    r14
0x180237556  push    r15
0x180237558  sub     rsp, 30h
0x18023755c  mov     r11d, [rdx+4]
0x180237560  mov     rsi, rcx
0x180237563  mov     r9d, [rdx]
0x180237566  mov     r15d, 0Fh
0x18023756c  mov     r10d, [rdx+0Ch]
0x180237570  mov     ecx, r15d; nIndex
0x180237573  mov     eax, [rdx+8]
0x180237576  sub     r10d, r11d
0x180237579  sub     eax, r9d
0x18023757c  mov     ebx, r8d
0x18023757f  cmp     eax, r10d
0x180237582  mov     rdi, rdx
0x180237585  cmovge  eax, r10d
0x180237589  lea     ebp, [rax+r9]
0x18023758d  lea     r12d, [rax+r11]
0x180237591  call    cs:__imp_GetSysColorBrush
0x180237598  nop     dword ptr [rax+rax+00h]
0x18023759d  lea     ecx, [r15+5]; nIndex
0x1802375a1  mov     r14, rax
0x1802375a4  call    cs:__imp_GetSysColor
0x1802375ab  nop     dword ptr [rax+rax+00h]
0x1802375b0  lea     ecx, [r15+1]; nIndex
0x1802375b4  mov     [rsp+68h+color], eax
0x1802375bb  call    cs:__imp_GetSysColor
0x1802375c2  nop     dword ptr [rax+rax+00h]
0x1802375c7  mov     [rsp+68h+arg_8], eax
0x1802375cb  test    ebx, ebx
0x1802375cd  jz      short loc_180237629
0x1802375cf  mov     rdx, r14; h
0x1802375d2  mov     rcx, rsi; hdc
0x1802375d5  call    cs:__imp_SelectObject
0x1802375dc  nop     dword ptr [rax+rax+00h]
0x1802375e1  mov     ecx, [rdi+0Ch]
0x1802375e4  mov     rbx, rax
0x1802375e7  mov     r8d, [rdi+4]; y
0x1802375eb  sub     ecx, r8d
0x1802375ee  mov     r9d, [rdi+8]
0x1802375f2  sub     r9d, [rdi]; w
0x1802375f5  mov     edx, [rdi]; x
0x1802375f7  mov     [rsp+68h+rop], 0F00021h; rop
0x1802375ff  mov     [rsp+68h+h], ecx; h
0x180237603  mov     rcx, rsi; hdc
0x180237606  call    cs:__imp_PatBlt
0x18023760d  nop     dword ptr [rax+rax+00h]
0x180237612  mov     rdx, rbx; h
0x180237615  mov     rcx, rsi; hdc
0x180237618  call    cs:__imp_SelectObject
0x18023761f  nop     dword ptr [rax+rax+00h]
0x180237624  jmp     loc_1802376D2
0x180237629  mov     ecx, r15d; nIndex
0x18023762c  call    cs:__imp_GetSysColor
0x180237633  nop     dword ptr [rax+rax+00h]
0x180237638  mov     edx, 1; cWidth
0x18023763d  xor     ecx, ecx; iStyle
0x18023763f  mov     r8d, eax; color
0x180237642  call    cs:__imp_CreatePen
0x180237649  nop     dword ptr [rax+rax+00h]
0x18023764e  mov     r15, rax
0x180237651  test    rax, rax
0x180237654  jz      loc_180237839
0x18023765a  mov     rdx, rax; h
0x18023765d  mov     rcx, rsi; hdc
0x180237660  call    cs:__imp_SelectObject
0x180237667  nop     dword ptr [rax+rax+00h]
0x18023766c  mov     r14d, [rdi+4]
0x180237670  mov     r13, rax
0x180237673  mov     ebx, [rdi]
0x180237675  add     r14d, 3
0x180237679  add     ebx, 3
0x18023767c  jmp     short loc_1802376AD
0x18023767e  xor     r9d, r9d; lppt
0x180237681  mov     r8d, r12d; y
0x180237684  mov     edx, ebx; x
0x180237686  call    cs:__imp_MoveToEx
0x18023768d  nop     dword ptr [rax+rax+00h]
0x180237692  mov     r8d, r14d; y
0x180237695  mov     edx, ebp; x
0x180237697  mov     rcx, rsi; hdc
0x18023769a  call    cs:__imp_LineTo
0x1802376a1  nop     dword ptr [rax+rax+00h]
0x1802376a6  add     ebx, 4
0x1802376a9  add     r14d, 4
0x1802376ad  mov     rcx, rsi; hdc
0x1802376b0  cmp     ebx, ebp
0x1802376b2  jl      short loc_18023767E
0x1802376b4  mov     rdx, r13; h
0x1802376b7  call    cs:__imp_SelectObject
0x1802376be  nop     dword ptr [rax+rax+00h]
0x1802376c3  mov     rcx, r15; ho
0x1802376c6  call    cs:__imp_DeleteObject
0x1802376cd  nop     dword ptr [rax+rax+00h]
0x1802376d2  mov     r8d, [rsp+68h+color]; color
0x1802376da  mov     edx, 1; cWidth
0x1802376df  xor     ecx, ecx; iStyle
0x1802376e1  call    cs:__imp_CreatePen
0x1802376e8  nop     dword ptr [rax+rax+00h]
0x1802376ed  mov     r14, rax
0x1802376f0  test    rax, rax
0x1802376f3  jz      loc_180237839
0x1802376f9  mov     rdx, rax; h
0x1802376fc  mov     rcx, rsi; hdc
0x1802376ff  call    cs:__imp_SelectObject
0x180237706  nop     dword ptr [rax+rax+00h]
0x18023770b  mov     r15d, [rdi+4]
0x18023770f  mov     r13, rax
0x180237712  mov     ebx, [rdi]
0x180237714  jmp     short loc_180237745
0x180237716  xor     r9d, r9d; lppt
0x180237719  mov     r8d, r12d; y
0x18023771c  mov     edx, ebx; x
0x18023771e  call    cs:__imp_MoveToEx
0x180237725  nop     dword ptr [rax+rax+00h]
0x18023772a  mov     r8d, r15d; y
0x18023772d  mov     edx, ebp; x
0x18023772f  mov     rcx, rsi; hdc
0x180237732  call    cs:__imp_LineTo
0x180237739  nop     dword ptr [rax+rax+00h]
0x18023773e  add     ebx, 4
0x180237741  add     r15d, 4
0x180237745  mov     rcx, rsi; hdc
0x180237748  cmp     ebx, ebp
0x18023774a  jl      short loc_180237716
0x18023774c  mov     rdx, r13; h
0x18023774f  call    cs:__imp_SelectObject
0x180237756  nop     dword ptr [rax+rax+00h]
0x18023775b  mov     rcx, r14; ho
0x18023775e  call    cs:__imp_DeleteObject
0x180237765  nop     dword ptr [rax+rax+00h]
0x18023776a  mov     r8d, [rsp+68h+arg_8]; color
0x18023776f  mov     r13d, 1
0x180237775  mov     edx, r13d; cWidth
0x180237778  xor     ecx, ecx; iStyle
0x18023777a  call    cs:__imp_CreatePen
0x180237781  nop     dword ptr [rax+rax+00h]
0x180237786  mov     r14, rax
0x180237789  test    rax, rax
0x18023778c  jz      loc_180237839
0x180237792  mov     rdx, rax; h
0x180237795  mov     rcx, rsi; hdc
0x180237798  call    cs:__imp_SelectObject
0x18023779f  nop     dword ptr [rax+rax+00h]
0x1802377a4  mov     ebx, [rdi]
0x1802377a6  mov     r15, rax
0x1802377a9  mov     edi, [rdi+4]
0x1802377ac  add     ebx, r13d
0x1802377af  add     edi, r13d
0x1802377b2  jmp     short loc_18023780F
0x1802377b4  xor     r9d, r9d; lppt
0x1802377b7  mov     r8d, r12d; y
0x1802377ba  mov     edx, ebx; x
0x1802377bc  call    cs:__imp_MoveToEx
0x1802377c3  nop     dword ptr [rax+rax+00h]
0x1802377c8  mov     r8d, edi; y
0x1802377cb  mov     edx, ebp; x
0x1802377cd  mov     rcx, rsi; hdc
0x1802377d0  call    cs:__imp_LineTo
0x1802377d7  nop     dword ptr [rax+rax+00h]
0x1802377dc  xor     r9d, r9d; lppt
0x1802377df  lea     edx, [rbx+1]; x
0x1802377e2  mov     r8d, r12d; y
0x1802377e5  mov     rcx, rsi; hdc
0x1802377e8  call    cs:__imp_MoveToEx
0x1802377ef  nop     dword ptr [rax+rax+00h]
0x1802377f4  lea     r8d, [rdi+1]; y
0x1802377f8  mov     edx, ebp; x
0x1802377fa  mov     rcx, rsi; hdc
0x1802377fd  call    cs:__imp_LineTo
0x180237804  nop     dword ptr [rax+rax+00h]
0x180237809  add     ebx, 4
0x18023780c  add     edi, 4
0x18023780f  mov     rcx, rsi; hdc
0x180237812  cmp     ebx, ebp
0x180237814  jl      short loc_1802377B4
0x180237816  mov     rdx, r15; h
0x180237819  call    cs:__imp_SelectObject
0x180237820  nop     dword ptr [rax+rax+00h]
0x180237825  mov     rcx, r14; ho
0x180237828  call    cs:__imp_DeleteObject
0x18023782f  nop     dword ptr [rax+rax+00h]
0x180237834  mov     eax, r13d
0x180237837  jmp     short loc_18023783B
0x180237839  xor     eax, eax
0x18023783b  mov     rbx, [rsp+68h+arg_0]
0x180237840  add     rsp, 30h
0x180237844  pop     r15
0x180237846  pop     r14
0x180237848  pop     r13
0x18023784a  pop     r12
0x18023784c  pop     rdi
0x18023784d  pop     rsi
0x18023784e  pop     rbp
0x18023784f  retn
```
