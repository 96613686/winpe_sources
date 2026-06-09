# CEmfPlusEnumState::Header(void)

- ea: `0x18001226c`
- end: `0x1800125bc`
- name: `?Header@CEmfPlusEnumState@@QEAAXXZ`
- size: `848`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180011a00`

## callees

- `0x1800067bc`
- `0x18001226c`
- `0x180013270`
- `0x1800139fc`
- `0x180013a54`
- `0x180013ad0`
- `0x180013dbc`
- `0x180014474`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180168478`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124bb`
- `GDI32!GetPolyFillMode` at `0x18001244f`
- `GDI32!GetPolyFillMode` at `0x18001244f`
- `GDI32!GetArcDirection` at `0x18001243f`
- `GDI32!GetArcDirection` at `0x18001243f`
- `GDI32!GetTextAlign` at `0x18001240f`
- `GDI32!GetTextAlign` at `0x18001240f`
- `GDI32!GetBkMode` at `0x1800123ff`
- `GDI32!GetBkMode` at `0x1800123ff`
- `GDI32!GetMiterLimit` at `0x1800123ed`
- `GDI32!GetMiterLimit` at `0x1800123ed`
- `GDI32!GetWindowExtEx` at `0x1800123b1`
- `GDI32!GetWindowExtEx` at `0x1800123b1`
- `GDI32!GetViewportExtEx` at `0x1800123a0`
- `GDI32!GetViewportExtEx` at `0x1800123a0`
- `GDI32!GetWindowOrgEx` at `0x18001238f`
- `GDI32!GetWindowOrgEx` at `0x18001238f`
- `GDI32!GetMapMode` at `0x180012367`
- `GDI32!GetMapMode` at `0x180012367`
- `GDI32!SelectClipRgn` at `0x18001256a`
- `GDI32!SelectClipRgn` at `0x18001256a`
- `GDI32!SetBrushOrgEx` at `0x1800122d5`
- `GDI32!SetBrushOrgEx` at `0x1800122d5`
- `GDI32!GetTextColor` at `0x18001241f`
- `GDI32!GetTextColor` at `0x18001241f`
- `GDI32!GetBkColor` at `0x18001242f`
- `GDI32!GetBkColor` at `0x18001242f`
- `GDI32!GetPaletteEntries` at `0x18001250f`
- `GDI32!GetPaletteEntries` at `0x18001250f`
- `GDI32!GetObjectW` at `0x18001248e`
- `GDI32!GetObjectW` at `0x18001248e`
- `GDI32!SelectPalette` at `0x180012597`
- `GDI32!SelectPalette` at `0x180012597`
- `GDI32!GetCurrentObject` at `0x18001247e`
- `GDI32!GetCurrentObject` at `0x18001247e`
- `GDI32!DeleteObject` at `0x180012577`
- `GDI32!DeleteObject` at `0x180012577`
- `GDI32!GetViewportOrgEx` at `0x18001237e`
- `GDI32!GetViewportOrgEx` at `0x18001237e`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::Header(CEmfPlusEnumState *this)
{
  unsigned __int16 *PartialRecord; // rbx
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
  _QWORD *v13; // rbx
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
  int lfUnderline; // ebx
  int lfStrikeOut; // esi
  CEmfFont *v29; // rax
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct tagLOGFONTW pv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v33[112]; // [rsp+A0h] [rbp-60h] BYREF

  PartialRecord = (unsigned __int16 *)CEmfPlusEnumState::GetPartialRecord(this);
  memset_0(v33, 0, 0x6Cu);
  v3 = (*(unsigned int (__fastcall **)(CEmfPlusEnumState *))(*(_QWORD *)this + 48LL))(this);
  if ( v3 < 0x6C )
  {
    memcpy_0(v33, PartialRecord, v3);
    PartialRecord = (unsigned __int16 *)v33;
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
    v29 = (CEmfFont *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x48u);
    if ( v29 )
      v29 = CEmfFont::CEmfFont(v29, *((HDC *)this + 2), &pv, lfUnderline, lfStrikeOut);
    CSmartGpObject::CSmartGpObject((CSmartGpObject *)v31, v29);
    v30 = v31[0];
    if ( v31[0] )
      _InterlockedIncrement(v31[0]);
    CSmartGpObject::Release((CEmfPlusEnumState *)((char *)this + 2528));
    *((_QWORD *)this + 316) = v30;
    CSmartGpObject::Release((CSmartGpObject *)v31);
  }
  GetPaletteEntries(*((HPALETTE *)this + 7), 0, 0x100u, (LPPALETTEENTRY)this + 798);
}

```

## disassembly

```asm
0x18001226c  push    rbp
0x18001226e  push    rbx
0x18001226f  push    rsi
0x180012270  push    rdi
0x180012271  lea     rbp, [rsp-28h]
0x180012276  sub     rsp, 128h
0x18001227d  mov     rax, cs:__security_cookie
0x180012284  xor     rax, rsp
0x180012287  mov     [rbp+40h+var_30], rax
0x18001228b  mov     rdi, rcx
0x18001228e  call    ?GetPartialRecord@CEmfPlusEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; CEmfPlusEnumState::GetPartialRecord(void)
0x180012293  xor     edx, edx; Val
0x180012295  lea     rcx, [rbp+40h+var_A0]; void *
0x180012299  mov     rbx, rax
0x18001229c  lea     r8d, [rdx+6Ch]; Size
0x1800122a0  call    memset_0
0x1800122a5  mov     rax, [rdi]
0x1800122a8  mov     rcx, rdi
0x1800122ab  mov     rax, [rax+30h]
0x1800122af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b4  mov     r8d, eax; Size
0x1800122b7  cmp     r8, 6Ch ; 'l'
0x1800122bb  jb      loc_180012551
0x1800122c1  mov     r8d, [rdi+9BCh]; y
0x1800122c8  xor     r9d, r9d; lppt
0x1800122cb  mov     edx, [rdi+9B8h]; x
0x1800122d1  mov     rcx, [rdi+10h]; hdc
0x1800122d5  call    cs:__imp_SetBrushOrgEx
0x1800122db  mov     rdx, [rdi+948h]; hrgn
0x1800122e2  test    rdx, rdx
0x1800122e5  jnz     loc_180012566
0x1800122eb  mov     rdx, [rdi+950h]; hPal
0x1800122f2  test    rdx, rdx
0x1800122f5  jnz     loc_18001258D
0x1800122fb  movzx   eax, word ptr [rbx+38h]
0x1800122ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012306  mov     [rdi+0C74h], eax
0x18001230c  mov     esi, eax
0x18001230e  mov     eax, 8
0x180012313  mul     rsi
0x180012316  cmovb   rax, rcx
0x18001231a  add     rax, 8
0x18001231e  cmovb   rax, rcx
0x180012322  xor     edx, edx
0x180012324  mov     rcx, rax
0x180012327  call    GpMallocEx
0x18001232c  test    rax, rax
0x18001232f  jz      loc_18001252D
0x180012335  lea     rbx, [rax+8]
0x180012339  mov     [rax], rsi
0x18001233c  mov     rcx, rbx; void *
0x18001233f  lea     r9, ??0CharacterRange@@QEAA@XZ; void *(*)(void *)
0x180012346  mov     r8d, esi; unsigned __int64
0x180012349  mov     edx, 8; unsigned __int64
0x18001234e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180012353  mov     [rdi+0A88h], rbx
0x18001235a  test    rbx, rbx
0x18001235d  jz      loc_1800125A2
0x180012363  mov     rcx, [rdi+10h]; hdc
0x180012367  call    cs:__imp_GetMapMode
0x18001236d  mov     rcx, [rdi+10h]; hdc
0x180012371  lea     rdx, [rdi+968h]; lppoint
0x180012378  mov     [rdi+964h], eax
0x18001237e  call    cs:__imp_GetViewportOrgEx
0x180012384  mov     rcx, [rdi+10h]; hdc
0x180012388  lea     rdx, [rdi+970h]; lppoint
0x18001238f  call    cs:__imp_GetWindowOrgEx
0x180012395  mov     rcx, [rdi+10h]; hdc
0x180012399  lea     rdx, [rdi+978h]; lpsize
0x1800123a0  call    cs:__imp_GetViewportExtEx
0x1800123a6  mov     rcx, [rdi+10h]; hdc
0x1800123aa  lea     rdx, [rdi+980h]; lpsize
0x1800123b1  call    cs:__imp_GetWindowExtEx
0x1800123b7  movss   xmm2, cs:__real@3f800000
0x1800123bf  mov     edx, 1
0x1800123c4  mov     rcx, [rdi+958h]
0x1800123cb  call    ?SetPageTransform@GpGraphics@@QEAA?AW4Status@@W4Unit@@M@Z; GpGraphics::SetPageTransform(Unit,float)
0x1800123d0  mov     rax, [rdi]
0x1800123d3  mov     rcx, rdi
0x1800123d6  mov     rax, [rax+48h]
0x1800123da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123df  mov     rcx, [rdi+10h]; hdc
0x1800123e3  lea     rbx, [rdi+9C8h]
0x1800123ea  mov     rdx, rbx; plimit
0x1800123ed  call    cs:__imp_GetMiterLimit
0x1800123f3  test    eax, eax
0x1800123f5  jz      loc_1800125B1
0x1800123fb  mov     rcx, [rdi+10h]; hdc
0x1800123ff  call    cs:__imp_GetBkMode
0x180012405  mov     rcx, [rdi+10h]; hdc
0x180012409  mov     [rdi+9C4h], eax
0x18001240f  call    cs:__imp_GetTextAlign
0x180012415  mov     rcx, [rdi+10h]; hdc
0x180012419  mov     [rdi+9A8h], eax
0x18001241f  call    cs:__imp_GetTextColor
0x180012425  mov     rcx, [rdi+10h]; hdc
0x180012429  mov     [rdi+9A0h], eax
0x18001242f  call    cs:__imp_GetBkColor
0x180012435  mov     rcx, [rdi+10h]; hdc
0x180012439  mov     [rdi+9A4h], eax
0x18001243f  call    cs:__imp_GetArcDirection
0x180012445  mov     rcx, [rdi+10h]; hdc
0x180012449  mov     [rdi+9C0h], eax
0x18001244f  call    cs:__imp_GetPolyFillMode
0x180012455  xor     ecx, ecx
0x180012457  mov     ebx, 5Ch ; '\'
0x18001245c  cmp     eax, 1
0x18001245f  mov     r8d, ebx; Size
0x180012462  setnz   cl
0x180012465  xor     edx, edx; Val
0x180012467  mov     [rdi+9ACh], ecx
0x18001246d  lea     rcx, [rsp+140h+pv]; void *
0x180012472  call    memset_0
0x180012477  mov     rcx, [rdi+10h]; hdc
0x18001247b  lea     edx, [rbx-56h]; type
0x18001247e  call    cs:__imp_GetCurrentObject
0x180012484  lea     r8, [rsp+140h+pv]; pv
0x180012489  mov     edx, ebx; c
0x18001248b  mov     rcx, rax; h
0x18001248e  call    cs:__imp_GetObjectW
0x180012494  test    eax, eax
0x180012496  jle     short loc_1800124FC
0x180012498  movzx   ebx, byte ptr [rsp+140h+var_EB]
0x18001249d  xor     edx, edx; dwFlags
0x18001249f  movzx   esi, byte ptr [rsp+140h+var_EB+1]
0x1800124a4  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800124ab  mov     [rsp+140h+var_E8], 7
0x1800124b0  lea     r8d, [rdx+48h]; dwBytes
0x1800124b4  mov     [rsp+140h+var_EB], 0
0x1800124bb  call    cs:__imp_HeapAlloc
0x1800124c1  test    rax, rax
0x1800124c4  jnz     short loc_180012534
0x1800124c6  mov     rdx, rax; struct GpObject *
0x1800124c9  lea     rcx, [rsp+140h+var_110]; this
0x1800124ce  call    ??0CSmartGpObject@@QEAA@PEAVGpObject@@@Z; CSmartGpObject::CSmartGpObject(GpObject *)
0x1800124d3  mov     rbx, [rsp+140h+var_110]
0x1800124d8  lea     rsi, [rdi+9E0h]
0x1800124df  test    rbx, rbx
0x1800124e2  jz      short loc_1800124E7
0x1800124e4  lock inc dword ptr [rbx]
0x1800124e7  mov     rcx, rsi; this
0x1800124ea  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x1800124ef  lea     rcx, [rsp+140h+var_110]; this
0x1800124f4  mov     [rsi], rbx
0x1800124f7  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x1800124fc  mov     rcx, [rdi+38h]; hpal
0x180012500  lea     r9, [rdi+0C78h]; pPalEntries
0x180012507  xor     edx, edx; iStart
0x180012509  mov     r8d, 100h; cEntries
0x18001250f  call    cs:__imp_GetPaletteEntries
0x180012515  mov     rcx, [rbp+40h+var_30]
0x180012519  xor     rcx, rsp; StackCookie
0x18001251c  call    __security_check_cookie
0x180012521  add     rsp, 128h
0x180012528  pop     rdi
0x180012529  pop     rsi
0x18001252a  pop     rbx
0x18001252b  pop     rbp
0x18001252c  retn
0x18001252d  xor     ebx, ebx
0x18001252f  jmp     loc_180012353
0x180012534  mov     rdx, [rdi+10h]; HDC
0x180012538  lea     r8, [rsp+140h+pv]; struct tagLOGFONTW *
0x18001253d  mov     r9d, ebx; int
0x180012540  mov     [rsp+140h+var_120], esi; int
0x180012544  mov     rcx, rax; this
0x180012547  call    ??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z; CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)
0x18001254c  jmp     loc_1800124C6
0x180012551  mov     rdx, rbx; Src
0x180012554  lea     rcx, [rbp+40h+var_A0]; void *
0x180012558  call    memcpy_0
0x18001255d  lea     rbx, [rbp+40h+var_A0]
0x180012561  jmp     loc_1800122C1
0x180012566  mov     rcx, [rdi+10h]; hdc
0x18001256a  call    cs:__imp_SelectClipRgn
0x180012570  mov     rcx, [rdi+948h]; ho
0x180012577  call    cs:__imp_DeleteObject
0x18001257d  mov     qword ptr [rdi+948h], 0
0x180012588  jmp     loc_1800122EB
0x18001258d  mov     rcx, [rdi+10h]; hdc
0x180012591  mov     r8d, 1; bForceBkgd
0x180012597  call    cs:__imp_SelectPalette
0x18001259d  jmp     loc_1800122FB
0x1800125a2  mov     dword ptr [rdi+0C74h], 0
0x1800125ac  jmp     loc_180012363
0x1800125b1  mov     dword ptr [rbx], 41200000h
0x1800125b7  jmp     loc_1800123FB
```
