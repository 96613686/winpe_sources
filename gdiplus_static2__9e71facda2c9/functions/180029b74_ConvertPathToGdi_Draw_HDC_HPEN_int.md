# ConvertPathToGdi::Draw(HDC__ *,HPEN__ *,int)

- ea: `0x180029b74`
- end: `0x18002a0ba`
- name: `?Draw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHPEN__@@H@Z`
- size: `1350`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HPEN h, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18003cc70`
- `0x18003d400`

## callees

- `0x180029b74`
- `0x18002aae8`
- `0x18002abc0`
- `0x1800d9598`

## import_xrefs

- `GDI32!PolyPolyline` at `0x180029d6f`
- `GDI32!PolyPolyline` at `0x180029d6f`
- `GDI32!Polyline` at `0x180029c70`
- `GDI32!Polyline` at `0x180029f5f`
- `GDI32!Polyline` at `0x180029c70`
- `GDI32!Polyline` at `0x180029f5f`
- `GDI32!PolyBezier` at `0x180029d25`
- `GDI32!PolyBezier` at `0x180029d25`
- `GDI32!LineTo` at `0x180029e18`
- `GDI32!LineTo` at `0x180029eb9`
- `GDI32!LineTo` at `0x180029fca`
- `GDI32!LineTo` at `0x180029e18`
- `GDI32!LineTo` at `0x180029eb9`
- `GDI32!LineTo` at `0x180029fca`
- `GDI32!StrokePath` at `0x18002a09f`
- `GDI32!StrokePath` at `0x18002a09f`
- `GDI32!EndPath` at `0x18002a08c`
- `GDI32!EndPath` at `0x18002a08c`
- `GDI32!MoveToEx` at `0x180029dd7`
- `GDI32!MoveToEx` at `0x180029e7e`
- `GDI32!MoveToEx` at `0x180029f9e`
- `GDI32!MoveToEx` at `0x180029dd7`
- `GDI32!MoveToEx` at `0x180029e7e`
- `GDI32!MoveToEx` at `0x180029f9e`
- `GDI32!BeginPath` at `0x18002a06a`
- `GDI32!BeginPath` at `0x18002a06a`
- `GDI32!PolyPolygon` at `0x18002a01e`
- `GDI32!PolyPolygon` at `0x18002a01e`
- `GDI32!Polygon` at `0x180029e34`
- `GDI32!Polygon` at `0x180029f41`
- `GDI32!Polygon` at `0x180029e34`
- `GDI32!Polygon` at `0x180029f41`
- `GDI32!GetStockObject` at `0x180029bed`
- `GDI32!GetStockObject` at `0x180029bed`
- `GDI32!SelectObject` at `0x180029bd6`
- `GDI32!SelectObject` at `0x180029bff`
- `GDI32!SelectObject` at `0x180029c9f`
- `GDI32!SelectObject` at `0x180029cb1`
- `GDI32!SelectObject` at `0x180029bd6`
- `GDI32!SelectObject` at `0x180029bff`
- `GDI32!SelectObject` at `0x180029c9f`
- `GDI32!SelectObject` at `0x180029cb1`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::Draw(ConvertPathToGdi *this, HDC a2, HPEN h, int a4)
{
  unsigned int v8; // esi
  int v9; // r15d
  int v10; // ebx
  void *v11; // r14
  HGDIOBJ StockObject; // rax
  void *v13; // r12
  int v14; // ebx
  int v15; // r8d
  const POINT *v16; // rdx
  BOOL v17; // eax
  __int64 v19; // r15
  int i; // r14d
  BOOL v21; // eax
  const POINT *v22; // r15
  int v23; // r12d
  __int64 v24; // r14
  _DWORD *v25; // rcx
  BOOL v26; // eax
  __int64 v27; // rcx
  HGDIOBJ v28; // [rsp+28h] [rbp-60h]
  HGDIOBJ v29; // [rsp+30h] [rbp-58h]
  int v30; // [rsp+90h] [rbp+8h]
  unsigned int v31; // [rsp+90h] [rbp+8h]

  v8 = 1;
  if ( *((int *)this + 106) > 0 )
  {
    v9 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
    v30 = v9;
    v10 = _mm_getcsr();
    _mm_setcsr(v10 & 0xFFFFFFC0);
    v28 = SelectObject(a2, h);
    v11 = v28;
    StockObject = GetStockObject(5);
    v29 = SelectObject(a2, StockObject);
    v13 = v29;
    _mm_setcsr(v10 & 0xFFFFFFC0);
    if ( (*((_BYTE *)this + 436) & 1) == 0 )
    {
      if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
      {
        v31 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v31);
        v8 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
        _mm_setcsr(v31);
      }
      else if ( !BeginPath(a2) || !ConvertPathToGdi::DrawMixedPath(this, a2) || !EndPath(a2) || !StrokePath(a2) )
      {
        v8 = 0;
      }
      goto LABEL_7;
    }
    v14 = _mm_getcsr();
    _mm_setcsr(v14 & 0xFFFFFFC0);
    if ( *((_DWORD *)this + 107) == 1 )
    {
      v15 = *((_DWORD *)this + 106);
      v16 = (const POINT *)*((_QWORD *)this + 51);
      if ( (*((_BYTE *)this + 436) & 0x20) == 0 )
      {
        v17 = Polyline(a2, v16, v15);
        v8 = v17;
        if ( a4 )
        {
          if ( !v17
            || (v8 = 1,
                !MoveToEx(
                   a2,
                   *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1)),
                   *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1) + 4),
                   0))
            || !LineTo(
                  a2,
                  *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1)) + 1,
                  *(_DWORD *)(*((_QWORD *)this + 51) + 8LL * (*((_DWORD *)this + 106) - 1) + 4)) )
          {
            v8 = 0;
          }
        }
        goto LABEL_6;
      }
      v21 = Polygon(a2, v16, v15);
      goto LABEL_44;
    }
    if ( (*((_BYTE *)this + 436) & 0x20) == 0 )
    {
      v8 = PolyPolyline(a2, *((const POINT **)this + 51), *((const DWORD **)this + 52), *((_DWORD *)this + 107));
      if ( !a4 )
      {
LABEL_6:
        _mm_setcsr(v14 & 0xFFFFFFC0);
LABEL_7:
        SelectObject(a2, v11);
        SelectObject(a2, v13);
        CleanupForIncreasedResolution(*((_DWORD *)this + 111), v9, a2);
        return v8;
      }
      v19 = *((_QWORD *)this + 51);
      for ( i = 0; i < *((_DWORD *)this + 107); v19 += 8LL * *(int *)(*((_QWORD *)this + 52) + 4 * v27) )
      {
        v8 = v8
          && MoveToEx(
               a2,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1)),
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1) + 4),
               0)
          && LineTo(
               a2,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1)) + 1,
               *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(*((_QWORD *)this + 52) + 4LL * i) - 1) + 4));
        v27 = i++;
      }
LABEL_47:
      v11 = v28;
LABEL_48:
      v9 = v30;
      goto LABEL_6;
    }
    if ( (*((_BYTE *)this + 436) & 0x40) == 0 )
    {
      v21 = PolyPolygon(a2, *((const POINT **)this + 51), *((const INT **)this + 52), *((_DWORD *)this + 107));
LABEL_44:
      v8 = v21;
      goto LABEL_6;
    }
    v22 = (const POINT *)*((_QWORD *)this + 51);
    v23 = 0;
    if ( *((int *)this + 107) <= 0 )
    {
      v13 = v29;
      goto LABEL_48;
    }
    while ( 1 )
    {
      v24 = **((int **)this + 52);
      v25 = (_DWORD *)*((_QWORD *)this + 51);
      if ( *v25 == v25[2 * (int)v24 - 2] && v25[1] == v25[2 * (int)v24 - 1] )
      {
        if ( !v8 )
          goto LABEL_40;
        v26 = Polygon(a2, v22, v24);
      }
      else
      {
        v8 = v8 && Polyline(a2, v22, v24);
        if ( !a4 )
          goto LABEL_41;
        if ( !v8 || !MoveToEx(a2, v22[(int)v24 - 1].x, v22[(int)v24 - 1].y, 0) )
        {
LABEL_40:
          v8 = 0;
          goto LABEL_41;
        }
        v26 = LineTo(a2, v22[(int)v24 - 1].x + 1, v22[(int)v24 - 1].y);
      }
      if ( !v26 )
        goto LABEL_40;
      v8 = 1;
LABEL_41:
      *((_QWORD *)this + 52) += 4LL;
      v22 += v24;
      if ( ++v23 >= *((_DWORD *)this + 107) )
      {
        v13 = v29;
        goto LABEL_47;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180029b74  push    rbx
0x180029b76  push    rbp
0x180029b77  push    rsi
0x180029b78  push    rdi
0x180029b79  push    r12
0x180029b7b  push    r13
0x180029b7d  push    r14
0x180029b7f  push    r15
0x180029b81  sub     rsp, 48h
0x180029b85  xor     ebx, ebx
0x180029b87  mov     r13d, r9d
0x180029b8a  mov     r14, r8
0x180029b8d  mov     rbp, rdx
0x180029b90  mov     rdi, rcx
0x180029b93  mov     esi, 1
0x180029b98  cmp     [rcx+1A8h], ebx
0x180029b9e  jle     loc_180029CCE
0x180029ba4  mov     ecx, [rcx+1BCh]; int
0x180029baa  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x180029baf  mov     r15d, eax
0x180029bb2  mov     [rsp+88h+arg_0], eax
0x180029bb9  stmxcsr [rsp+88h+var_68]
0x180029bbe  mov     ebx, [rsp+88h+var_68]
0x180029bc2  mov     rdx, r14; h
0x180029bc5  mov     eax, ebx
0x180029bc7  mov     rcx, rbp; hdc
0x180029bca  and     eax, 0FFFFFFC0h
0x180029bcd  mov     [rsp+88h+var_68], eax
0x180029bd1  ldmxcsr [rsp+88h+var_68]
0x180029bd6  call    cs:__imp_SelectObject
0x180029bdd  nop     dword ptr [rax+rax+00h]
0x180029be2  lea     ecx, [rsi+4]; i
0x180029be5  mov     [rsp+88h+var_60], rax
0x180029bea  mov     r14, rax
0x180029bed  call    cs:__imp_GetStockObject
0x180029bf4  nop     dword ptr [rax+rax+00h]
0x180029bf9  mov     rdx, rax; h
0x180029bfc  mov     rcx, rbp; hdc
0x180029bff  call    cs:__imp_SelectObject
0x180029c06  nop     dword ptr [rax+rax+00h]
0x180029c0b  mov     ecx, 0FFFFFFC0h
0x180029c10  mov     [rsp+88h+var_58], rax
0x180029c15  and     ebx, ecx
0x180029c17  mov     r12, rax
0x180029c1a  mov     [rsp+88h+var_68], ebx
0x180029c1e  ldmxcsr [rsp+88h+var_68]
0x180029c23  test    [rdi+1B4h], sil
0x180029c2a  jz      loc_180029CE2
0x180029c30  stmxcsr [rsp+88h+var_68]
0x180029c35  mov     ebx, [rsp+88h+var_68]
0x180029c39  mov     eax, ebx
0x180029c3b  and     eax, ecx
0x180029c3d  mov     [rsp+88h+var_68], eax
0x180029c41  ldmxcsr [rsp+88h+var_68]
0x180029c46  cmp     [rdi+1ACh], esi
0x180029c4c  jnz     loc_180029D4A
0x180029c52  test    byte ptr [rdi+1B4h], 20h
0x180029c59  mov     rcx, rbp; hdc
0x180029c5c  mov     r8d, [rdi+1A8h]; cpt
0x180029c63  mov     rdx, [rdi+198h]; apt
0x180029c6a  jnz     loc_180029E34
0x180029c70  call    cs:__imp_Polyline
0x180029c77  nop     dword ptr [rax+rax+00h]
0x180029c7c  mov     esi, eax
0x180029c7e  test    r13d, r13d
0x180029c81  jnz     loc_180029E45
0x180029c87  and     ebx, 0FFFFFFC0h
0x180029c8a  mov     [rsp+88h+arg_0], ebx
0x180029c91  ldmxcsr [rsp+88h+arg_0]
0x180029c99  mov     rdx, r14; h
0x180029c9c  mov     rcx, rbp; hdc
0x180029c9f  call    cs:__imp_SelectObject
0x180029ca6  nop     dword ptr [rax+rax+00h]
0x180029cab  mov     rdx, r12; h
0x180029cae  mov     rcx, rbp; hdc
0x180029cb1  call    cs:__imp_SelectObject
0x180029cb8  nop     dword ptr [rax+rax+00h]
0x180029cbd  mov     ecx, [rdi+1BCh]; int
0x180029cc3  mov     r8, rbp; HDC
0x180029cc6  mov     edx, r15d; int
0x180029cc9  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x180029cce  mov     eax, esi
0x180029cd0  add     rsp, 48h
0x180029cd4  pop     r15
0x180029cd6  pop     r14
0x180029cd8  pop     r13
0x180029cda  pop     r12
0x180029cdc  pop     rdi
0x180029cdd  pop     rsi
0x180029cde  pop     rbp
0x180029cdf  pop     rbx
0x180029ce0  retn
0x180029ce2  test    byte ptr [rdi+1B4h], 10h
0x180029ce9  jz      loc_18002A067
0x180029cef  stmxcsr [rsp+88h+arg_0]
0x180029cf7  mov     ebx, [rsp+88h+arg_0]
0x180029cfe  mov     r13d, ecx
0x180029d01  mov     r8d, [rdi+1A8h]; cpt
0x180029d08  mov     eax, ebx
0x180029d0a  mov     rdx, [rdi+198h]; apt
0x180029d11  and     eax, ecx
0x180029d13  mov     [rsp+88h+arg_0], eax
0x180029d1a  mov     rcx, rbp; hdc
0x180029d1d  ldmxcsr [rsp+88h+arg_0]
0x180029d25  call    cs:__imp_PolyBezier
0x180029d2c  nop     dword ptr [rax+rax+00h]
0x180029d31  and     ebx, r13d
0x180029d34  mov     esi, eax
0x180029d36  mov     [rsp+88h+arg_0], ebx
0x180029d3d  ldmxcsr [rsp+88h+arg_0]
0x180029d45  jmp     loc_180029C99
0x180029d4a  test    byte ptr [rdi+1B4h], 20h
0x180029d51  jnz     loc_180029ED4
0x180029d57  mov     r9d, [rdi+1ACh]; csz
0x180029d5e  mov     rcx, rbp; hdc
0x180029d61  mov     r8, [rdi+1A0h]; asz
0x180029d68  mov     rdx, [rdi+198h]; apt
0x180029d6f  call    cs:__imp_PolyPolyline
0x180029d76  nop     dword ptr [rax+rax+00h]
0x180029d7b  mov     esi, eax
0x180029d7d  test    r13d, r13d
0x180029d80  jz      loc_180029C87
0x180029d86  mov     r15, [rdi+198h]
0x180029d8d  xor     r14d, r14d
0x180029d90  cmp     [rdi+1ACh], r14d
0x180029d97  jle     loc_18002A055
0x180029d9d  lea     r13d, [r14+1]
0x180029da1  test    esi, esi
0x180029da3  jz      loc_18002A031
0x180029da9  mov     rax, [rdi+1A0h]
0x180029db0  xor     r9d, r9d; lppt
0x180029db3  movsxd  rcx, r14d
0x180029db6  mov     edx, [rax+rcx*4]
0x180029db9  sub     edx, r13d
0x180029dbc  movsxd  rcx, r14d
0x180029dbf  movsxd  r8, edx
0x180029dc2  mov     edx, [rax+rcx*4]
0x180029dc5  mov     rcx, rbp; hdc
0x180029dc8  mov     r8d, [r15+r8*8+4]; y
0x180029dcd  sub     edx, r13d
0x180029dd0  movsxd  rdx, edx
0x180029dd3  mov     edx, [r15+rdx*8]; x
0x180029dd7  call    cs:__imp_MoveToEx
0x180029dde  nop     dword ptr [rax+rax+00h]
0x180029de3  test    eax, eax
0x180029de5  jz      loc_18002A031
0x180029deb  mov     rax, [rdi+1A0h]
0x180029df2  movsxd  rcx, r14d
0x180029df5  mov     edx, [rax+rcx*4]
0x180029df8  sub     edx, r13d
0x180029dfb  movsxd  rcx, r14d
0x180029dfe  movsxd  r8, edx
0x180029e01  mov     eax, [rax+rcx*4]
0x180029e04  mov     rcx, rbp; hdc
0x180029e07  mov     r8d, [r15+r8*8+4]; y
0x180029e0c  sub     eax, r13d
0x180029e0f  cdqe
0x180029e11  mov     edx, [r15+rax*8]
0x180029e15  add     edx, r13d; x
0x180029e18  call    cs:__imp_LineTo
0x180029e1f  nop     dword ptr [rax+rax+00h]
0x180029e24  test    eax, eax
0x180029e26  jz      loc_18002A031
0x180029e2c  mov     esi, r13d
0x180029e2f  jmp     loc_18002A033
0x180029e34  call    cs:__imp_Polygon
0x180029e3b  nop     dword ptr [rax+rax+00h]
0x180029e40  jmp     loc_18002A02A
0x180029e45  test    eax, eax
0x180029e47  jz      loc_180029ECD
0x180029e4d  mov     r8, [rdi+198h]
0x180029e54  mov     esi, 1
0x180029e59  mov     eax, [rdi+1A8h]
0x180029e5f  xor     r9d, r9d; lppt
0x180029e62  sub     eax, esi
0x180029e64  movsxd  r10, eax
0x180029e67  mov     eax, [rdi+1A8h]
0x180029e6d  sub     eax, esi
0x180029e6f  movsxd  rcx, eax
0x180029e72  mov     edx, [r8+rcx*8]; x
0x180029e76  mov     rcx, rbp; hdc
0x180029e79  mov     r8d, [r8+r10*8+4]; y
0x180029e7e  call    cs:__imp_MoveToEx
0x180029e85  nop     dword ptr [rax+rax+00h]
0x180029e8a  test    eax, eax
0x180029e8c  jz      short loc_180029ECD
0x180029e8e  mov     r8, [rdi+198h]
0x180029e95  mov     eax, [rdi+1A8h]
0x180029e9b  sub     eax, esi
0x180029e9d  movsxd  r9, eax
0x180029ea0  mov     eax, [rdi+1A8h]
0x180029ea6  sub     eax, esi
0x180029ea8  movsxd  rcx, eax
0x180029eab  mov     edx, [r8+rcx*8]
0x180029eaf  mov     rcx, rbp; hdc
0x180029eb2  mov     r8d, [r8+r9*8+4]; y
0x180029eb7  add     edx, esi; x
0x180029eb9  call    cs:__imp_LineTo
0x180029ec0  nop     dword ptr [rax+rax+00h]
0x180029ec5  test    eax, eax
0x180029ec7  jnz     loc_180029C87
0x180029ecd  xor     esi, esi
0x180029ecf  jmp     loc_180029C87
0x180029ed4  test    byte ptr [rdi+1B4h], 40h
0x180029edb  jz      loc_18002A006
0x180029ee1  mov     r15, [rdi+198h]
0x180029ee8  xor     r12d, r12d
0x180029eeb  cmp     [rdi+1ACh], r12d
0x180029ef2  jg      short loc_180029EFE
0x180029ef4  mov     r12, [rsp+88h+var_58]
0x180029ef9  jmp     loc_18002A05A
0x180029efe  mov     rax, [rdi+1A0h]
0x180029f05  movsxd  r14, dword ptr [rax]
0x180029f08  lea     eax, [r14-1]
0x180029f0c  movsxd  rdx, eax
0x180029f0f  mov     rax, [rdi+198h]
0x180029f16  mov     rcx, rax
0x180029f19  mov     eax, [rax+rdx*8]
0x180029f1c  cmp     [rcx], eax
0x180029f1e  jnz     short loc_180029F52
0x180029f20  lea     eax, [r14-1]
0x180029f24  movsxd  rdx, eax
0x180029f27  mov     eax, [rcx+rdx*8+4]
0x180029f2b  cmp     [rcx+4], eax
0x180029f2e  jnz     short loc_180029F52
0x180029f30  test    esi, esi
0x180029f32  jz      loc_180029FE1
0x180029f38  mov     r8d, r14d; cpt
0x180029f3b  mov     rdx, r15; apt
0x180029f3e  mov     rcx, rbp; hdc
0x180029f41  call    cs:__imp_Polygon
0x180029f48  nop     dword ptr [rax+rax+00h]
0x180029f4d  jmp     loc_180029FD6
0x180029f52  test    esi, esi
0x180029f54  jz      short loc_180029F76
0x180029f56  mov     r8d, r14d; cpt
0x180029f59  mov     rdx, r15; apt
0x180029f5c  mov     rcx, rbp; hdc
0x180029f5f  call    cs:__imp_Polyline
0x180029f66  nop     dword ptr [rax+rax+00h]
0x180029f6b  test    eax, eax
0x180029f6d  jz      short loc_180029F76
0x180029f6f  mov     esi, 1
0x180029f74  jmp     short loc_180029F78
0x180029f76  xor     esi, esi
0x180029f78  test    r13d, r13d
0x180029f7b  jz      short loc_180029FE3
0x180029f7d  test    esi, esi
0x180029f7f  jz      short loc_180029FE1
0x180029f81  lea     eax, [r14-1]
0x180029f85  xor     r9d, r9d; lppt
0x180029f88  movsxd  r8, eax
0x180029f8b  mov     rcx, rbp; hdc
0x180029f8e  lea     eax, [r14-1]
0x180029f92  movsxd  rdx, eax
0x180029f95  mov     r8d, [r15+r8*8+4]; y
0x180029f9a  mov     edx, [r15+rdx*8]; x
0x180029f9e  call    cs:__imp_MoveToEx
0x180029fa5  nop     dword ptr [rax+rax+00h]
0x180029faa  test    eax, eax
0x180029fac  jz      short loc_180029FE1
0x180029fae  lea     eax, [r14-1]
0x180029fb2  movsxd  r8, eax
0x180029fb5  lea     eax, [r14-1]
0x180029fb9  movsxd  rcx, eax
0x180029fbc  mov     r8d, [r15+r8*8+4]; y
0x180029fc1  mov     edx, [r15+rcx*8]
0x180029fc5  mov     rcx, rbp; hdc
0x180029fc8  inc     edx; x
0x180029fca  call    cs:__imp_LineTo
0x180029fd1  nop     dword ptr [rax+rax+00h]
0x180029fd6  test    eax, eax
0x180029fd8  jz      short loc_180029FE1
0x180029fda  mov     esi, 1
0x180029fdf  jmp     short loc_180029FE3
0x180029fe1  xor     esi, esi
0x180029fe3  add     qword ptr [rdi+1A0h], 4
0x180029feb  lea     r15, [r15+r14*8]
0x180029fef  inc     r12d
0x180029ff2  cmp     r12d, [rdi+1ACh]
0x180029ff9  jl      loc_180029EFE
0x180029fff  mov     r12, [rsp+88h+var_58]
0x18002a004  jmp     short loc_18002A055
0x18002a006  mov     r9d, [rdi+1ACh]; csz
0x18002a00d  mov     rcx, rbp; hdc
0x18002a010  mov     r8, [rdi+1A0h]; asz
0x18002a017  mov     rdx, [rdi+198h]; apt
0x18002a01e  call    cs:__imp_PolyPolygon
0x18002a025  nop     dword ptr [rax+rax+00h]
0x18002a02a  mov     esi, eax
0x18002a02c  jmp     loc_180029C87
0x18002a031  xor     esi, esi
0x18002a033  mov     rax, [rdi+1A0h]
0x18002a03a  movsxd  rcx, r14d
0x18002a03d  add     r14d, r13d
0x18002a040  movsxd  rcx, dword ptr [rax+rcx*4]
0x18002a044  lea     r15, [r15+rcx*8]
0x18002a048  cmp     r14d, [rdi+1ACh]
0x18002a04f  jl      loc_180029DA1
0x18002a055  mov     r14, [rsp+88h+var_60]
  ... truncated ...
```
