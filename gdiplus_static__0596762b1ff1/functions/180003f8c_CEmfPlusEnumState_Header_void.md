# CEmfPlusEnumState::Header(void)

- ea: `0x180003f8c`
- end: `0x180004367`
- name: `?Header@CEmfPlusEnumState@@QEAAXXZ`
- size: `987`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180003720`

## callees

- `0x180003494`
- `0x180003f8c`
- `0x18000506c`
- `0x18000584c`
- `0x1800058d0`
- `0x180005914`
- `0x180063cd8`
- `0x180105d40`
- `0x18010673c`
- `0x180171428`
- `0x180172010`

## import_xrefs

- `GDI32!GetPolyFillMode` at `0x1800041b7`
- `GDI32!GetPolyFillMode` at `0x1800041b7`
- `GDI32!GetArcDirection` at `0x1800041a1`
- `GDI32!GetArcDirection` at `0x1800041a1`
- `GDI32!GetTextAlign` at `0x18000415f`
- `GDI32!GetTextAlign` at `0x18000415f`
- `GDI32!GetBkMode` at `0x180004149`
- `GDI32!GetBkMode` at `0x180004149`
- `GDI32!GetMiterLimit` at `0x180004131`
- `GDI32!GetMiterLimit` at `0x180004131`
- `GDI32!GetWindowExtEx` at `0x1800040ef`
- `GDI32!GetWindowExtEx` at `0x1800040ef`
- `GDI32!GetViewportExtEx` at `0x1800040d8`
- `GDI32!GetViewportExtEx` at `0x1800040d8`
- `GDI32!GetWindowOrgEx` at `0x1800040c1`
- `GDI32!GetWindowOrgEx` at `0x1800040c1`
- `GDI32!GetMapMode` at `0x18000408d`
- `GDI32!GetMapMode` at `0x18000408d`
- `GDI32!SelectClipRgn` at `0x180004303`
- `GDI32!SelectClipRgn` at `0x180004303`
- `GDI32!SetBrushOrgEx` at `0x180003ff5`
- `GDI32!SetBrushOrgEx` at `0x180003ff5`
- `GDI32!GetTextColor` at `0x180004175`
- `GDI32!GetTextColor` at `0x180004175`
- `GDI32!GetBkColor` at `0x18000418b`
- `GDI32!GetBkColor` at `0x18000418b`
- `GDI32!GetPaletteEntries` at `0x180004275`
- `GDI32!GetPaletteEntries` at `0x180004275`
- `GDI32!GetObjectW` at `0x180004202`
- `GDI32!GetObjectW` at `0x180004202`
- `GDI32!SelectPalette` at `0x18000433c`
- `GDI32!SelectPalette` at `0x18000433c`
- `GDI32!GetCurrentObject` at `0x1800041ec`
- `GDI32!GetCurrentObject` at `0x1800041ec`
- `GDI32!DeleteObject` at `0x180004316`
- `GDI32!DeleteObject` at `0x180004316`
- `GDI32!GetViewportOrgEx` at `0x1800040aa`
- `GDI32!GetViewportOrgEx` at `0x1800040aa`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::Header(CEmfPlusEnumState *this)
{
  unsigned __int16 *PartialRecord; // rdi
  size_t v3; // r8
  HRGN v4; // rdx
  HPALETTE v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rsi
  __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  bool v10; // cf
  __int64 v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  int MapMode; // eax
  HDC v15; // rcx
  int BkMode; // eax
  HDC v17; // rcx
  UINT TextAlign; // eax
  HDC v19; // rcx
  COLORREF TextColor; // eax
  HDC v21; // rcx
  COLORREF BkColor; // eax
  HDC v23; // rcx
  int ArcDirection; // eax
  HDC v25; // rcx
  HGDIOBJ CurrentObject; // rax
  int lfUnderline; // edi
  int lfStrikeOut; // esi
  CEmfFont *v29; // rax
  volatile signed __int32 *v30; // rdi
  CEmfFont *v31; // rsi
  __int64 v32; // rax
  volatile signed __int32 *v33; // [rsp+30h] [rbp-D0h] BYREF
  struct tagLOGFONTW pv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[112]; // [rsp+A0h] [rbp-60h] BYREF

  PartialRecord = (unsigned __int16 *)CEmfPlusEnumState::GetPartialRecord(this);
  memset_0(v35, 0, 0x6Cu);
  v3 = (*(unsigned int (__fastcall **)(CEmfPlusEnumState *))(*(_QWORD *)this + 48LL))(this);
  if ( v3 < 0x6C )
  {
    memcpy_0(v35, PartialRecord, v3);
    PartialRecord = (unsigned __int16 *)v35;
  }
  SetBrushOrgEx(*((HDC *)this + 2), *((_DWORD *)this + 622), *((_DWORD *)this + 623), 0);
  v4 = (HRGN)*((_QWORD *)this + 297);
  if ( v4 )
  {
    SelectClipRgn(*((HDC *)this + 2), v4);
    DeleteObject(*((HGDIOBJ *)this + 297));
    *((_QWORD *)this + 297) = 0;
  }
  v5 = (HPALETTE)*((_QWORD *)this + 298);
  if ( v5 )
    SelectPalette(*((HDC *)this + 2), v5, 1);
  v6 = PartialRecord[28];
  *((_DWORD *)this + 797) = v6;
  v7 = v6;
  v9 = v6;
  v8 = 8LL * v6;
  if ( !is_mul_ok(v9, 8u) )
    v8 = -1;
  v10 = __CFADD__(v8, 8);
  v11 = v8 + 8;
  if ( v10 )
    v11 = -1;
  v12 = (_QWORD *)GpMallocEx(v11, 0);
  if ( v12 )
  {
    v13 = v12 + 1;
    *v12 = v7;
    `vector constructor iterator'(v12 + 1, 8u, (unsigned int)v7, (void *(*)(void *))CharacterRange::CharacterRange);
  }
  else
  {
    v13 = 0;
  }
  *((_QWORD *)this + 337) = v13;
  if ( !v13 )
    *((_DWORD *)this + 797) = 0;
  MapMode = GetMapMode(*((HDC *)this + 2));
  v15 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 601) = MapMode;
  GetViewportOrgEx(v15, (LPPOINT)this + 301);
  GetWindowOrgEx(*((HDC *)this + 2), (LPPOINT)this + 302);
  GetViewportExtEx(*((HDC *)this + 2), (LPSIZE)this + 303);
  GetWindowExtEx(*((HDC *)this + 2), (LPSIZE)this + 304);
  GpGraphics::SetPageTransform(*((_QWORD *)this + 299), 1);
  (*(void (__fastcall **)(CEmfPlusEnumState *))(*(_QWORD *)this + 72LL))(this);
  if ( !GetMiterLimit(*((HDC *)this + 2), (PFLOAT)this + 626) )
    *((_DWORD *)this + 626) = 1092616192;
  BkMode = GetBkMode(*((HDC *)this + 2));
  v17 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 625) = BkMode;
  TextAlign = GetTextAlign(v17);
  v19 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 618) = TextAlign;
  TextColor = GetTextColor(v19);
  v21 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 616) = TextColor;
  BkColor = GetBkColor(v21);
  v23 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 617) = BkColor;
  ArcDirection = GetArcDirection(v23);
  v25 = (HDC)*((_QWORD *)this + 2);
  *((_DWORD *)this + 624) = ArcDirection;
  *((_DWORD *)this + 619) = GetPolyFillMode(v25) != 1;
  memset_0(&pv, 0, sizeof(pv));
  CurrentObject = GetCurrentObject(*((HDC *)this + 2), 6u);
  if ( GetObjectW(CurrentObject, 92, &pv) > 0 )
  {
    lfUnderline = pv.lfUnderline;
    lfStrikeOut = pv.lfStrikeOut;
    pv.lfOutPrecision = 7;
    *(_WORD *)&pv.lfUnderline = 0;
    v29 = (CEmfFont *)GpMallocEx(72, 0);
    if ( v29
      && (v31 = CEmfFont::CEmfFont(v29, *((HDC *)this + 2), &pv, lfUnderline, lfStrikeOut)) != 0
      && (v32 = GpMallocEx(16, 0), (v30 = (volatile signed __int32 *)v32) != 0) )
    {
      *(_DWORD *)v32 = 1;
      *(_QWORD *)(v32 + 8) = v31;
    }
    else
    {
      v30 = 0;
    }
    v33 = v30;
    if ( v30 )
      _InterlockedIncrement(v30);
    CSmartGpObject::Release((CEmfPlusEnumState *)((char *)this + 2528));
    *((_QWORD *)this + 316) = v30;
    CSmartGpObject::Release((CSmartGpObject *)&v33);
  }
  GetPaletteEntries(*((HPALETTE *)this + 7), 0, 0x100u, (LPPALETTEENTRY)this + 798);
}

```

## disassembly

```asm
0x180003f8c  push    rbp
0x180003f8e  push    rbx
0x180003f8f  push    rsi
0x180003f90  push    rdi
0x180003f91  lea     rbp, [rsp-28h]
0x180003f96  sub     rsp, 128h
0x180003f9d  mov     rax, cs:__security_cookie
0x180003fa4  xor     rax, rsp
0x180003fa7  mov     [rbp+40h+var_30], rax
0x180003fab  mov     rbx, rcx
0x180003fae  call    ?GetPartialRecord@CEmfPlusEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; CEmfPlusEnumState::GetPartialRecord(void)
0x180003fb3  xor     edx, edx; Val
0x180003fb5  lea     rcx, [rbp+40h+var_A0]; void *
0x180003fb9  mov     rdi, rax
0x180003fbc  lea     r8d, [rdx+6Ch]; Size
0x180003fc0  call    memset_0
0x180003fc5  mov     rcx, [rbx]
0x180003fc8  mov     rax, [rcx+30h]
0x180003fcc  mov     rcx, rbx
0x180003fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd4  mov     r8d, eax; Size
0x180003fd7  cmp     r8, 6Ch ; 'l'
0x180003fdb  jb      loc_1800042EA
0x180003fe1  mov     r8d, [rbx+9BCh]; y
0x180003fe8  xor     r9d, r9d; lppt
0x180003feb  mov     edx, [rbx+9B8h]; x
0x180003ff1  mov     rcx, [rbx+10h]; hdc
0x180003ff5  call    cs:__imp_SetBrushOrgEx
0x180003ffc  nop     dword ptr [rax+rax+00h]
0x180004001  mov     rdx, [rbx+948h]; hrgn
0x180004008  test    rdx, rdx
0x18000400b  jnz     loc_1800042FF
0x180004011  mov     rdx, [rbx+950h]; hPal
0x180004018  test    rdx, rdx
0x18000401b  jnz     loc_180004332
0x180004021  movzx   eax, word ptr [rdi+38h]
0x180004025  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000402c  mov     [rbx+0C74h], eax
0x180004032  mov     esi, eax
0x180004034  mov     eax, 8
0x180004039  mul     rsi
0x18000403c  cmovb   rax, rcx
0x180004040  add     rax, 8
0x180004044  cmovb   rax, rcx
0x180004048  xor     edx, edx
0x18000404a  mov     rcx, rax
0x18000404d  call    GpMallocEx
0x180004052  test    rax, rax
0x180004055  jz      loc_18000429A
0x18000405b  lea     rdi, [rax+8]
0x18000405f  mov     [rax], rsi
0x180004062  mov     rcx, rdi; void *
0x180004065  lea     r9, ??0CharacterRange@@QEAA@XZ; void *(*)(void *)
0x18000406c  mov     r8d, esi; unsigned __int64
0x18000406f  mov     edx, 8; unsigned __int64
0x180004074  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180004079  mov     [rbx+0A88h], rdi
0x180004080  test    rdi, rdi
0x180004083  jz      loc_18000434D
0x180004089  mov     rcx, [rbx+10h]; hdc
0x18000408d  call    cs:__imp_GetMapMode
0x180004094  nop     dword ptr [rax+rax+00h]
0x180004099  mov     rcx, [rbx+10h]; hdc
0x18000409d  lea     rdx, [rbx+968h]; lppoint
0x1800040a4  mov     [rbx+964h], eax
0x1800040aa  call    cs:__imp_GetViewportOrgEx
0x1800040b1  nop     dword ptr [rax+rax+00h]
0x1800040b6  mov     rcx, [rbx+10h]; hdc
0x1800040ba  lea     rdx, [rbx+970h]; lppoint
0x1800040c1  call    cs:__imp_GetWindowOrgEx
0x1800040c8  nop     dword ptr [rax+rax+00h]
0x1800040cd  mov     rcx, [rbx+10h]; hdc
0x1800040d1  lea     rdx, [rbx+978h]; lpsize
0x1800040d8  call    cs:__imp_GetViewportExtEx
0x1800040df  nop     dword ptr [rax+rax+00h]
0x1800040e4  mov     rcx, [rbx+10h]; hdc
0x1800040e8  lea     rdx, [rbx+980h]; lpsize
0x1800040ef  call    cs:__imp_GetWindowExtEx
0x1800040f6  nop     dword ptr [rax+rax+00h]
0x1800040fb  movss   xmm2, cs:__real@3f800000
0x180004103  mov     edx, 1
0x180004108  mov     rcx, [rbx+958h]
0x18000410f  call    ?SetPageTransform@GpGraphics@@QEAA?AW4Status@@W4Unit@@M@Z; GpGraphics::SetPageTransform(Unit,float)
0x180004114  mov     rax, [rbx]
0x180004117  mov     rcx, rbx
0x18000411a  mov     rax, [rax+48h]
0x18000411e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004123  mov     rcx, [rbx+10h]; hdc
0x180004127  lea     rdi, [rbx+9C8h]
0x18000412e  mov     rdx, rdi; plimit
0x180004131  call    cs:__imp_GetMiterLimit
0x180004138  nop     dword ptr [rax+rax+00h]
0x18000413d  test    eax, eax
0x18000413f  jz      loc_18000435C
0x180004145  mov     rcx, [rbx+10h]; hdc
0x180004149  call    cs:__imp_GetBkMode
0x180004150  nop     dword ptr [rax+rax+00h]
0x180004155  mov     rcx, [rbx+10h]; hdc
0x180004159  mov     [rbx+9C4h], eax
0x18000415f  call    cs:__imp_GetTextAlign
0x180004166  nop     dword ptr [rax+rax+00h]
0x18000416b  mov     rcx, [rbx+10h]; hdc
0x18000416f  mov     [rbx+9A8h], eax
0x180004175  call    cs:__imp_GetTextColor
0x18000417c  nop     dword ptr [rax+rax+00h]
0x180004181  mov     rcx, [rbx+10h]; hdc
0x180004185  mov     [rbx+9A0h], eax
0x18000418b  call    cs:__imp_GetBkColor
0x180004192  nop     dword ptr [rax+rax+00h]
0x180004197  mov     rcx, [rbx+10h]; hdc
0x18000419b  mov     [rbx+9A4h], eax
0x1800041a1  call    cs:__imp_GetArcDirection
0x1800041a8  nop     dword ptr [rax+rax+00h]
0x1800041ad  mov     rcx, [rbx+10h]; hdc
0x1800041b1  mov     [rbx+9C0h], eax
0x1800041b7  call    cs:__imp_GetPolyFillMode
0x1800041be  nop     dword ptr [rax+rax+00h]
0x1800041c3  xor     ecx, ecx
0x1800041c5  mov     edi, 5Ch ; '\'
0x1800041ca  cmp     eax, 1
0x1800041cd  mov     r8d, edi; Size
0x1800041d0  setnz   cl
0x1800041d3  xor     edx, edx; Val
0x1800041d5  mov     [rbx+9ACh], ecx
0x1800041db  lea     rcx, [rsp+140h+pv]; void *
0x1800041e0  call    memset_0
0x1800041e5  mov     rcx, [rbx+10h]; hdc
0x1800041e9  lea     edx, [rdi-56h]; type
0x1800041ec  call    cs:__imp_GetCurrentObject
0x1800041f3  nop     dword ptr [rax+rax+00h]
0x1800041f8  lea     r8, [rsp+140h+pv]; pv
0x1800041fd  mov     edx, edi; c
0x1800041ff  mov     rcx, rax; h
0x180004202  call    cs:__imp_GetObjectW
0x180004209  nop     dword ptr [rax+rax+00h]
0x18000420e  test    eax, eax
0x180004210  jle     short loc_180004262
0x180004212  movzx   edi, byte ptr [rsp+140h+var_EB]
0x180004217  xor     edx, edx
0x180004219  movzx   esi, byte ptr [rsp+140h+var_EB+1]
0x18000421e  mov     [rsp+140h+var_E8], 7
0x180004223  mov     [rsp+140h+var_EB], 0
0x18000422a  lea     ecx, [rdx+48h]
0x18000422d  call    GpMallocEx
0x180004232  test    rax, rax
0x180004235  jnz     short loc_1800042A1
0x180004237  xor     edi, edi
0x180004239  mov     [rsp+140h+var_110], rdi
0x18000423e  lea     rsi, [rbx+9E0h]
0x180004245  test    rdi, rdi
0x180004248  jz      short loc_18000424D
0x18000424a  lock inc dword ptr [rdi]
0x18000424d  mov     rcx, rsi; this
0x180004250  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x180004255  lea     rcx, [rsp+140h+var_110]; this
0x18000425a  mov     [rsi], rdi
0x18000425d  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x180004262  mov     rcx, [rbx+38h]; hpal
0x180004266  lea     r9, [rbx+0C78h]; pPalEntries
0x18000426d  xor     edx, edx; iStart
0x18000426f  mov     r8d, 100h; cEntries
0x180004275  call    cs:__imp_GetPaletteEntries
0x18000427c  nop     dword ptr [rax+rax+00h]
0x180004281  mov     rcx, [rbp+40h+var_30]
0x180004285  xor     rcx, rsp; StackCookie
0x180004288  call    __security_check_cookie
0x18000428d  add     rsp, 128h
0x180004294  pop     rdi
0x180004295  pop     rsi
0x180004296  pop     rbx
0x180004297  pop     rbp
0x180004298  retn
0x18000429a  xor     edi, edi
0x18000429c  jmp     loc_180004079
0x1800042a1  mov     rdx, [rbx+10h]; HDC
0x1800042a5  lea     r8, [rsp+140h+pv]; struct tagLOGFONTW *
0x1800042aa  mov     r9d, edi; int
0x1800042ad  mov     [rsp+140h+var_120], esi; int
0x1800042b1  mov     rcx, rax; this
0x1800042b4  call    ??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z; CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)
0x1800042b9  mov     rsi, rax
0x1800042bc  test    rax, rax
0x1800042bf  jz      loc_180004237
0x1800042c5  xor     edx, edx
0x1800042c7  lea     ecx, [rdx+10h]
0x1800042ca  call    GpMallocEx
0x1800042cf  mov     rdi, rax
0x1800042d2  test    rax, rax
0x1800042d5  jz      loc_180004237
0x1800042db  mov     dword ptr [rax], 1
0x1800042e1  mov     [rax+8], rsi
0x1800042e5  jmp     loc_180004239
0x1800042ea  mov     rdx, rdi; Src
0x1800042ed  lea     rcx, [rbp+40h+var_A0]; void *
0x1800042f1  call    memcpy_0
0x1800042f6  lea     rdi, [rbp+40h+var_A0]
0x1800042fa  jmp     loc_180003FE1
0x1800042ff  mov     rcx, [rbx+10h]; hdc
0x180004303  call    cs:__imp_SelectClipRgn
0x18000430a  nop     dword ptr [rax+rax+00h]
0x18000430f  mov     rcx, [rbx+948h]; ho
0x180004316  call    cs:__imp_DeleteObject
0x18000431d  nop     dword ptr [rax+rax+00h]
0x180004322  mov     qword ptr [rbx+948h], 0
0x18000432d  jmp     loc_180004011
0x180004332  mov     rcx, [rbx+10h]; hdc
0x180004336  mov     r8d, 1; bForceBkgd
0x18000433c  call    cs:__imp_SelectPalette
0x180004343  nop     dword ptr [rax+rax+00h]
0x180004348  jmp     loc_180004021
0x18000434d  mov     dword ptr [rbx+0C74h], 0
0x180004357  jmp     loc_180004089
0x18000435c  mov     dword ptr [rdi], 41200000h
0x180004362  jmp     loc_180004145
```
