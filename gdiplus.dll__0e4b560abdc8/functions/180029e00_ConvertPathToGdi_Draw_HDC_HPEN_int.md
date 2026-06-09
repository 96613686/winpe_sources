# ConvertPathToGdi::Draw(HDC__ *,HPEN__ *,int)

- ea: `0x180029e00`
- end: `0x18002a324`
- name: `?Draw@ConvertPathToGdi@@QEAAHPEAUHDC__@@PEAUHPEN__@@H@Z`
- size: `1316`
- prototype: `__int64 __fastcall(ConvertPathToGdi *__hidden this, HDC, HPEN h, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180029070`
- `0x1800e6300`

## callees

- `0x180029e00`
- `0x18003bb1c`
- `0x18003bbec`
- `0x1800bd49c`

## import_xrefs

- `GDI32!PolyPolyline` at `0x180029ff8`
- `GDI32!PolyPolyline` at `0x180029ff8`
- `GDI32!Polyline` at `0x180029f04`
- `GDI32!Polyline` at `0x18002a1fc`
- `GDI32!Polyline` at `0x180029f04`
- `GDI32!Polyline` at `0x18002a1fc`
- `GDI32!PolyBezier` at `0x180029fb4`
- `GDI32!PolyBezier` at `0x180029fb4`
- `GDI32!LineTo` at `0x18002a090`
- `GDI32!LineTo` at `0x18002a159`
- `GDI32!LineTo` at `0x18002a267`
- `GDI32!LineTo` at `0x18002a090`
- `GDI32!LineTo` at `0x18002a159`
- `GDI32!LineTo` at `0x18002a267`
- `GDI32!StrokePath` at `0x18002a309`
- `GDI32!StrokePath` at `0x18002a309`
- `GDI32!EndPath` at `0x18002a2f6`
- `GDI32!EndPath` at `0x18002a2f6`
- `GDI32!MoveToEx` at `0x18002a05a`
- `GDI32!MoveToEx` at `0x18002a11e`
- `GDI32!MoveToEx` at `0x18002a23b`
- `GDI32!MoveToEx` at `0x18002a05a`
- `GDI32!MoveToEx` at `0x18002a11e`
- `GDI32!MoveToEx` at `0x18002a23b`
- `GDI32!BeginPath` at `0x18002a2d4`
- `GDI32!BeginPath` at `0x18002a2d4`
- `GDI32!PolyPolygon` at `0x18002a2be`
- `GDI32!PolyPolygon` at `0x18002a2be`
- `GDI32!Polygon` at `0x18002a0d4`
- `GDI32!Polygon` at `0x18002a1de`
- `GDI32!Polygon` at `0x18002a0d4`
- `GDI32!Polygon` at `0x18002a1de`
- `GDI32!GetStockObject` at `0x180029e81`
- `GDI32!GetStockObject` at `0x180029e81`
- `GDI32!SelectObject` at `0x180029e6a`
- `GDI32!SelectObject` at `0x180029e93`
- `GDI32!SelectObject` at `0x180029f2d`
- `GDI32!SelectObject` at `0x180029f3f`
- `GDI32!SelectObject` at `0x180029e6a`
- `GDI32!SelectObject` at `0x180029e93`
- `GDI32!SelectObject` at `0x180029f2d`
- `GDI32!SelectObject` at `0x180029f3f`

## pseudocode

```c
__int64 __fastcall ConvertPathToGdi::Draw(ConvertPathToGdi *this, HDC a2, HPEN h, int a4)
{
  __int64 v4; // r14
  unsigned int v8; // esi
  int v9; // r12d
  int v10; // ebx
  void *v11; // r15
  HGDIOBJ StockObject; // rax
  void *v13; // r13
  int v14; // ebx
  int v15; // r8d
  const POINT *v16; // rdx
  BOOL v17; // eax
  __int64 v19; // r15
  int v20; // r12d
  __int64 v21; // r14
  __int64 v22; // rcx
  BOOL v23; // eax
  const POINT *v24; // r15
  int v25; // r12d
  __int64 v26; // r13
  __int64 v27; // r14
  _DWORD *v28; // rcx
  BOOL v29; // eax
  HGDIOBJ v30; // [rsp+28h] [rbp-40h]
  HGDIOBJ v31; // [rsp+30h] [rbp-38h]
  int v32; // [rsp+70h] [rbp+8h]
  unsigned int v33; // [rsp+70h] [rbp+8h]

  v4 = a4;
  v8 = 1;
  if ( *((int *)this + 106) > 0 )
  {
    v9 = SetupForIncreasedResolution(*((_DWORD *)this + 111), a2);
    v32 = v9;
    v10 = _mm_getcsr();
    _mm_setcsr(v10 & 0xFFFFFFC0);
    v30 = SelectObject(a2, h);
    v11 = v30;
    StockObject = GetStockObject(5);
    v31 = SelectObject(a2, StockObject);
    v13 = v31;
    _mm_setcsr(v10 & 0xFFFFFFC0);
    if ( (*((_BYTE *)this + 436) & 1) == 0 )
    {
      if ( (*((_BYTE *)this + 436) & 0x10) != 0 )
      {
        v33 = _mm_getcsr() & 0xFFFFFFC0;
        _mm_setcsr(v33);
        v8 = PolyBezier(a2, *((const POINT **)this + 51), *((_DWORD *)this + 106));
        _mm_setcsr(v33);
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
        if ( (_DWORD)v4 )
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
      v23 = Polygon(a2, v16, v15);
LABEL_47:
      v8 = v23;
LABEL_6:
      _mm_setcsr(v14 & 0xFFFFFFC0);
LABEL_7:
      SelectObject(a2, v11);
      SelectObject(a2, v13);
      CleanupForIncreasedResolution(*((_DWORD *)this + 111), v9, a2);
      return v8;
    }
    if ( (*((_BYTE *)this + 436) & 0x20) == 0 )
    {
      v8 = PolyPolyline(a2, *((const POINT **)this + 51), *((const DWORD **)this + 52), *((_DWORD *)this + 107));
      if ( (_DWORD)v4 )
      {
        v19 = *((_QWORD *)this + 51);
        v20 = 0;
        if ( *((int *)this + 107) > 0 )
        {
          v21 = 0;
          do
          {
            if ( !v8
              || (v8 = 1,
                  !MoveToEx(
                     a2,
                     *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(v21 + *((_QWORD *)this + 52)) - 1)),
                     *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(v21 + *((_QWORD *)this + 52)) - 1) + 4),
                     0))
              || !LineTo(
                    a2,
                    *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(v21 + *((_QWORD *)this + 52)) - 1)) + 1,
                    *(_DWORD *)(v19 + 8LL * (*(_DWORD *)(v21 + *((_QWORD *)this + 52)) - 1) + 4)) )
            {
              v8 = 0;
            }
            ++v20;
            v22 = *(int *)(v21 + *((_QWORD *)this + 52));
            v21 += 4;
            v19 += 8 * v22;
          }
          while ( v20 < *((_DWORD *)this + 107) );
        }
LABEL_20:
        v11 = v30;
        v9 = v32;
      }
      goto LABEL_6;
    }
    if ( (*((_BYTE *)this + 436) & 0x40) == 0 )
    {
      v23 = PolyPolygon(a2, *((const POINT **)this + 51), *((const INT **)this + 52), *((_DWORD *)this + 107));
      goto LABEL_47;
    }
    v24 = (const POINT *)*((_QWORD *)this + 51);
    v25 = 0;
    if ( *((int *)this + 107) <= 0 )
      goto LABEL_20;
    v26 = v4;
    while ( 1 )
    {
      v27 = **((int **)this + 52);
      v28 = (_DWORD *)*((_QWORD *)this + 51);
      if ( *v28 == v28[2 * (int)v27 - 2] && v28[1] == v28[2 * (int)v27 - 1] )
      {
        if ( !v8 )
          goto LABEL_43;
        v29 = Polygon(a2, v24, v27);
      }
      else
      {
        v8 = v8 && Polyline(a2, v24, v27);
        if ( !v26 )
          goto LABEL_44;
        if ( !v8 || !MoveToEx(a2, v24[(int)v27 - 1].x, v24[(int)v27 - 1].y, 0) )
        {
LABEL_43:
          v8 = 0;
          goto LABEL_44;
        }
        v29 = LineTo(a2, v24[(int)v27 - 1].x + 1, v24[(int)v27 - 1].y);
      }
      if ( !v29 )
        goto LABEL_43;
      v8 = 1;
LABEL_44:
      *((_QWORD *)this + 52) += 4LL;
      v24 += v27;
      if ( ++v25 >= *((_DWORD *)this + 107) )
      {
        v13 = v31;
        goto LABEL_20;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180029e00  mov     [rsp+arg_8], rbx
0x180029e05  mov     [rsp+arg_10], rbp
0x180029e0a  mov     [rsp+arg_18], rsi
0x180029e0f  push    rdi
0x180029e10  push    r12
0x180029e12  push    r13
0x180029e14  push    r14
0x180029e16  push    r15
0x180029e18  sub     rsp, 40h
0x180029e1c  xor     ebx, ebx
0x180029e1e  movsxd  r14, r9d
0x180029e21  mov     r15, r8
0x180029e24  mov     rbp, rdx
0x180029e27  mov     rdi, rcx
0x180029e2a  mov     esi, 1
0x180029e2f  cmp     [rcx+1A8h], ebx
0x180029e35  jle     loc_180029F5C
0x180029e3b  mov     ecx, [rcx+1BCh]; int
0x180029e41  call    ?SetupForIncreasedResolution@@YAHHPEAUHDC__@@@Z; SetupForIncreasedResolution(int,HDC__ *)
0x180029e46  mov     r12d, eax
0x180029e49  mov     [rsp+68h+arg_0], eax
0x180029e4d  stmxcsr [rsp+68h+var_48]
0x180029e52  mov     ebx, [rsp+68h+var_48]
0x180029e56  mov     rdx, r15; h
0x180029e59  mov     eax, ebx
0x180029e5b  mov     rcx, rbp; hdc
0x180029e5e  and     eax, 0FFFFFFC0h
0x180029e61  mov     [rsp+68h+var_48], eax
0x180029e65  ldmxcsr [rsp+68h+var_48]
0x180029e6a  call    cs:__imp_SelectObject
0x180029e71  nop     dword ptr [rax+rax+00h]
0x180029e76  lea     ecx, [rsi+4]; i
0x180029e79  mov     [rsp+68h+var_40], rax
0x180029e7e  mov     r15, rax
0x180029e81  call    cs:__imp_GetStockObject
0x180029e88  nop     dword ptr [rax+rax+00h]
0x180029e8d  mov     rdx, rax; h
0x180029e90  mov     rcx, rbp; hdc
0x180029e93  call    cs:__imp_SelectObject
0x180029e9a  nop     dword ptr [rax+rax+00h]
0x180029e9f  mov     ecx, 0FFFFFFC0h
0x180029ea4  mov     [rsp+68h+var_38], rax
0x180029ea9  and     ebx, ecx
0x180029eab  mov     r13, rax
0x180029eae  mov     [rsp+68h+var_48], ebx
0x180029eb2  ldmxcsr [rsp+68h+var_48]
0x180029eb7  test    [rdi+1B4h], sil
0x180029ebe  jz      loc_180029F7D
0x180029ec4  stmxcsr [rsp+68h+var_48]
0x180029ec9  mov     ebx, [rsp+68h+var_48]
0x180029ecd  mov     eax, ebx
0x180029ecf  and     eax, ecx
0x180029ed1  mov     [rsp+68h+var_48], eax
0x180029ed5  ldmxcsr [rsp+68h+var_48]
0x180029eda  cmp     [rdi+1ACh], esi
0x180029ee0  jnz     loc_180029FD3
0x180029ee6  test    byte ptr [rdi+1B4h], 20h
0x180029eed  mov     rcx, rbp; hdc
0x180029ef0  mov     r8d, [rdi+1A8h]; cpt
0x180029ef7  mov     rdx, [rdi+198h]; apt
0x180029efe  jnz     loc_18002A0D4
0x180029f04  call    cs:__imp_Polyline
0x180029f0b  nop     dword ptr [rax+rax+00h]
0x180029f10  mov     esi, eax
0x180029f12  test    r14d, r14d
0x180029f15  jnz     loc_18002A0E5
0x180029f1b  and     ebx, 0FFFFFFC0h
0x180029f1e  mov     [rsp+68h+arg_0], ebx
0x180029f22  ldmxcsr [rsp+68h+arg_0]
0x180029f27  mov     rdx, r15; h
0x180029f2a  mov     rcx, rbp; hdc
0x180029f2d  call    cs:__imp_SelectObject
0x180029f34  nop     dword ptr [rax+rax+00h]
0x180029f39  mov     rdx, r13; h
0x180029f3c  mov     rcx, rbp; hdc
0x180029f3f  call    cs:__imp_SelectObject
0x180029f46  nop     dword ptr [rax+rax+00h]
0x180029f4b  mov     ecx, [rdi+1BCh]; int
0x180029f51  mov     r8, rbp; HDC
0x180029f54  mov     edx, r12d; int
0x180029f57  call    ?CleanupForIncreasedResolution@@YAXHHPEAUHDC__@@@Z; CleanupForIncreasedResolution(int,int,HDC__ *)
0x180029f5c  lea     r11, [rsp+68h+var_28]
0x180029f61  mov     eax, esi
0x180029f63  mov     rbx, [r11+38h]
0x180029f67  mov     rbp, [r11+40h]
0x180029f6b  mov     rsi, [r11+48h]
0x180029f6f  mov     rsp, r11
0x180029f72  pop     r15
0x180029f74  pop     r14
0x180029f76  pop     r13
0x180029f78  pop     r12
0x180029f7a  pop     rdi
0x180029f7b  retn
0x180029f7d  test    byte ptr [rdi+1B4h], 10h
0x180029f84  jz      loc_18002A2D1
0x180029f8a  stmxcsr [rsp+68h+arg_0]
0x180029f8f  mov     ebx, [rsp+68h+arg_0]
0x180029f93  mov     r14d, ecx
0x180029f96  mov     r8d, [rdi+1A8h]; cpt
0x180029f9d  mov     eax, ebx
0x180029f9f  mov     rdx, [rdi+198h]; apt
0x180029fa6  and     eax, ecx
0x180029fa8  mov     [rsp+68h+arg_0], eax
0x180029fac  mov     rcx, rbp; hdc
0x180029faf  ldmxcsr [rsp+68h+arg_0]
0x180029fb4  call    cs:__imp_PolyBezier
0x180029fbb  nop     dword ptr [rax+rax+00h]
0x180029fc0  and     ebx, r14d
0x180029fc3  mov     esi, eax
0x180029fc5  mov     [rsp+68h+arg_0], ebx
0x180029fc9  ldmxcsr [rsp+68h+arg_0]
0x180029fce  jmp     loc_180029F27
0x180029fd3  test    byte ptr [rdi+1B4h], 20h
0x180029fda  jnz     loc_18002A174
0x180029fe0  mov     r9d, [rdi+1ACh]; csz
0x180029fe7  mov     rcx, rbp; hdc
0x180029fea  mov     r8, [rdi+1A0h]; asz
0x180029ff1  mov     rdx, [rdi+198h]; apt
0x180029ff8  call    cs:__imp_PolyPolyline
0x180029fff  nop     dword ptr [rax+rax+00h]
0x18002a004  mov     esi, eax
0x18002a006  test    r14d, r14d
0x18002a009  jz      loc_180029F1B
0x18002a00f  mov     r15, [rdi+198h]
0x18002a016  xor     r12d, r12d
0x18002a019  cmp     [rdi+1ACh], r12d
0x18002a020  jle     loc_18002A0C5
0x18002a026  xor     r14d, r14d
0x18002a029  test    esi, esi
0x18002a02b  jz      short loc_18002A0A0
0x18002a02d  mov     rax, [rdi+1A0h]
0x18002a034  mov     esi, 1
0x18002a039  xor     r9d, r9d; lppt
0x18002a03c  mov     ecx, [r14+rax]
0x18002a040  sub     ecx, esi
0x18002a042  movsxd  r8, ecx
0x18002a045  mov     ecx, [r14+rax]
0x18002a049  sub     ecx, esi
0x18002a04b  movsxd  rdx, ecx
0x18002a04e  mov     rcx, rbp; hdc
0x18002a051  mov     r8d, [r15+r8*8+4]; y
0x18002a056  mov     edx, [r15+rdx*8]; x
0x18002a05a  call    cs:__imp_MoveToEx
0x18002a061  nop     dword ptr [rax+rax+00h]
0x18002a066  test    eax, eax
0x18002a068  jz      short loc_18002A0A0
0x18002a06a  mov     rax, [rdi+1A0h]
0x18002a071  mov     ecx, [r14+rax]
0x18002a075  mov     eax, [r14+rax]
0x18002a079  sub     ecx, esi
0x18002a07b  movsxd  r8, ecx
0x18002a07e  sub     eax, esi
0x18002a080  cdqe
0x18002a082  mov     rcx, rbp; hdc
0x18002a085  mov     r8d, [r15+r8*8+4]; y
0x18002a08a  mov     edx, [r15+rax*8]
0x18002a08e  add     edx, esi; x
0x18002a090  call    cs:__imp_LineTo
0x18002a097  nop     dword ptr [rax+rax+00h]
0x18002a09c  test    eax, eax
0x18002a09e  jnz     short loc_18002A0A2
0x18002a0a0  xor     esi, esi
0x18002a0a2  mov     rax, [rdi+1A0h]
0x18002a0a9  inc     r12d
0x18002a0ac  movsxd  rcx, dword ptr [r14+rax]
0x18002a0b0  add     r14, 4
0x18002a0b4  lea     r15, [r15+rcx*8]
0x18002a0b8  cmp     r12d, [rdi+1ACh]
0x18002a0bf  jl      loc_18002A029
0x18002a0c5  mov     r15, [rsp+68h+var_40]
0x18002a0ca  mov     r12d, [rsp+68h+arg_0]
0x18002a0cf  jmp     loc_180029F1B
0x18002a0d4  call    cs:__imp_Polygon
0x18002a0db  nop     dword ptr [rax+rax+00h]
0x18002a0e0  jmp     loc_18002A2CA
0x18002a0e5  test    eax, eax
0x18002a0e7  jz      loc_18002A16D
0x18002a0ed  mov     r8, [rdi+198h]
0x18002a0f4  mov     esi, 1
0x18002a0f9  mov     eax, [rdi+1A8h]
0x18002a0ff  xor     r9d, r9d; lppt
0x18002a102  sub     eax, esi
0x18002a104  movsxd  r10, eax
0x18002a107  mov     eax, [rdi+1A8h]
0x18002a10d  sub     eax, esi
0x18002a10f  movsxd  rcx, eax
0x18002a112  mov     edx, [r8+rcx*8]; x
0x18002a116  mov     rcx, rbp; hdc
0x18002a119  mov     r8d, [r8+r10*8+4]; y
0x18002a11e  call    cs:__imp_MoveToEx
0x18002a125  nop     dword ptr [rax+rax+00h]
0x18002a12a  test    eax, eax
0x18002a12c  jz      short loc_18002A16D
0x18002a12e  mov     r8, [rdi+198h]
0x18002a135  mov     eax, [rdi+1A8h]
0x18002a13b  sub     eax, esi
0x18002a13d  movsxd  r9, eax
0x18002a140  mov     eax, [rdi+1A8h]
0x18002a146  sub     eax, esi
0x18002a148  movsxd  rcx, eax
0x18002a14b  mov     edx, [r8+rcx*8]
0x18002a14f  mov     rcx, rbp; hdc
0x18002a152  mov     r8d, [r8+r9*8+4]; y
0x18002a157  add     edx, esi; x
0x18002a159  call    cs:__imp_LineTo
0x18002a160  nop     dword ptr [rax+rax+00h]
0x18002a165  test    eax, eax
0x18002a167  jnz     loc_180029F1B
0x18002a16d  xor     esi, esi
0x18002a16f  jmp     loc_180029F1B
0x18002a174  test    byte ptr [rdi+1B4h], 40h
0x18002a17b  jz      loc_18002A2A6
0x18002a181  mov     r15, [rdi+198h]
0x18002a188  xor     r12d, r12d
0x18002a18b  cmp     [rdi+1ACh], r12d
0x18002a192  jle     loc_18002A0C5
0x18002a198  mov     r13, r14
0x18002a19b  mov     rax, [rdi+1A0h]
0x18002a1a2  movsxd  r14, dword ptr [rax]
0x18002a1a5  lea     eax, [r14-1]
0x18002a1a9  movsxd  rdx, eax
0x18002a1ac  mov     rax, [rdi+198h]
0x18002a1b3  mov     rcx, rax
0x18002a1b6  mov     eax, [rax+rdx*8]
0x18002a1b9  cmp     [rcx], eax
0x18002a1bb  jnz     short loc_18002A1EF
0x18002a1bd  lea     eax, [r14-1]
0x18002a1c1  movsxd  rdx, eax
0x18002a1c4  mov     eax, [rcx+rdx*8+4]
0x18002a1c8  cmp     [rcx+4], eax
0x18002a1cb  jnz     short loc_18002A1EF
0x18002a1cd  test    esi, esi
0x18002a1cf  jz      loc_18002A27E
0x18002a1d5  mov     r8d, r14d; cpt
0x18002a1d8  mov     rdx, r15; apt
0x18002a1db  mov     rcx, rbp; hdc
0x18002a1de  call    cs:__imp_Polygon
0x18002a1e5  nop     dword ptr [rax+rax+00h]
0x18002a1ea  jmp     loc_18002A273
0x18002a1ef  test    esi, esi
0x18002a1f1  jz      short loc_18002A213
0x18002a1f3  mov     r8d, r14d; cpt
0x18002a1f6  mov     rdx, r15; apt
0x18002a1f9  mov     rcx, rbp; hdc
0x18002a1fc  call    cs:__imp_Polyline
0x18002a203  nop     dword ptr [rax+rax+00h]
0x18002a208  test    eax, eax
0x18002a20a  jz      short loc_18002A213
0x18002a20c  mov     esi, 1
0x18002a211  jmp     short loc_18002A215
0x18002a213  xor     esi, esi
0x18002a215  test    r13, r13
0x18002a218  jz      short loc_18002A280
0x18002a21a  test    esi, esi
0x18002a21c  jz      short loc_18002A27E
0x18002a21e  lea     eax, [r14-1]
0x18002a222  xor     r9d, r9d; lppt
0x18002a225  movsxd  r8, eax
0x18002a228  mov     rcx, rbp; hdc
0x18002a22b  lea     eax, [r14-1]
0x18002a22f  movsxd  rdx, eax
0x18002a232  mov     r8d, [r15+r8*8+4]; y
0x18002a237  mov     edx, [r15+rdx*8]; x
0x18002a23b  call    cs:__imp_MoveToEx
0x18002a242  nop     dword ptr [rax+rax+00h]
0x18002a247  test    eax, eax
0x18002a249  jz      short loc_18002A27E
0x18002a24b  lea     eax, [r14-1]
0x18002a24f  movsxd  r8, eax
0x18002a252  lea     eax, [r14-1]
0x18002a256  movsxd  rcx, eax
0x18002a259  mov     r8d, [r15+r8*8+4]; y
0x18002a25e  mov     edx, [r15+rcx*8]
0x18002a262  mov     rcx, rbp; hdc
0x18002a265  inc     edx; x
0x18002a267  call    cs:__imp_LineTo
0x18002a26e  nop     dword ptr [rax+rax+00h]
0x18002a273  test    eax, eax
0x18002a275  jz      short loc_18002A27E
0x18002a277  mov     esi, 1
0x18002a27c  jmp     short loc_18002A280
0x18002a27e  xor     esi, esi
0x18002a280  add     qword ptr [rdi+1A0h], 4
0x18002a288  lea     r15, [r15+r14*8]
0x18002a28c  inc     r12d
0x18002a28f  cmp     r12d, [rdi+1ACh]
0x18002a296  jl      loc_18002A19B
0x18002a29c  mov     r13, [rsp+68h+var_38]
0x18002a2a1  jmp     loc_18002A0C5
0x18002a2a6  mov     r9d, [rdi+1ACh]; csz
0x18002a2ad  mov     rcx, rbp; hdc
0x18002a2b0  mov     r8, [rdi+1A0h]; asz
0x18002a2b7  mov     rdx, [rdi+198h]; apt
0x18002a2be  call    cs:__imp_PolyPolygon
0x18002a2c5  nop     dword ptr [rax+rax+00h]
0x18002a2ca  mov     esi, eax
0x18002a2cc  jmp     loc_180029F1B
0x18002a2d1  mov     rcx, rbp; hdc
0x18002a2d4  call    cs:__imp_BeginPath
0x18002a2db  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
