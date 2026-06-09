# CEmfPlusEnumState::Header(void)

- ea: `0x18005e880`
- end: `0x18005ec70`
- name: `?Header@CEmfPlusEnumState@@QEAAXXZ`
- size: `1008`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18005df70`

## callees

- `0x180019b98`
- `0x18005512c`
- `0x18005e880`
- `0x1800603cc`
- `0x180060564`
- `0x1800e4fc0`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `GDI32!GetPolyFillMode` at `0x18005eab5`
- `GDI32!GetPolyFillMode` at `0x18005eab5`
- `GDI32!GetArcDirection` at `0x18005ea9f`
- `GDI32!GetArcDirection` at `0x18005ea9f`
- `GDI32!GetTextAlign` at `0x18005ea5d`
- `GDI32!GetTextAlign` at `0x18005ea5d`
- `GDI32!GetBkMode` at `0x18005ea47`
- `GDI32!GetBkMode` at `0x18005ea47`
- `GDI32!GetMiterLimit` at `0x18005ea2f`
- `GDI32!GetMiterLimit` at `0x18005ea2f`
- `GDI32!GetWindowExtEx` at `0x18005e9ed`
- `GDI32!GetWindowExtEx` at `0x18005e9ed`
- `GDI32!GetViewportExtEx` at `0x18005e9d6`
- `GDI32!GetViewportExtEx` at `0x18005e9d6`
- `GDI32!GetWindowOrgEx` at `0x18005e9bf`
- `GDI32!GetWindowOrgEx` at `0x18005e9bf`
- `GDI32!GetMapMode` at `0x18005e98b`
- `GDI32!GetMapMode` at `0x18005e98b`
- `GDI32!SelectClipRgn` at `0x18005ec12`
- `GDI32!SelectClipRgn` at `0x18005ec12`
- `GDI32!SetBrushOrgEx` at `0x18005e8f3`
- `GDI32!SetBrushOrgEx` at `0x18005e8f3`
- `GDI32!GetTextColor` at `0x18005ea73`
- `GDI32!GetTextColor` at `0x18005ea73`
- `GDI32!GetBkColor` at `0x18005ea89`
- `GDI32!GetBkColor` at `0x18005ea89`
- `GDI32!GetPaletteEntries` at `0x18005eb77`
- `GDI32!GetPaletteEntries` at `0x18005eb77`
- `GDI32!GetObjectW` at `0x18005eb00`
- `GDI32!GetObjectW` at `0x18005eb00`
- `GDI32!SelectPalette` at `0x18005ec48`
- `GDI32!SelectPalette` at `0x18005ec48`
- `GDI32!GetCurrentObject` at `0x18005eaea`
- `GDI32!GetCurrentObject` at `0x18005eaea`
- `GDI32!DeleteObject` at `0x18005ec25`
- `GDI32!DeleteObject` at `0x18005ec25`
- `GDI32!GetViewportOrgEx` at `0x18005e9a8`
- `GDI32!GetViewportOrgEx` at `0x18005e9a8`

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
  CEmfFont *v31; // rsi
  __int64 v32; // rax
  volatile signed __int32 *v33; // [rsp+38h] [rbp-D0h] BYREF
  struct tagLOGFONTW pv; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v35[112]; // [rsp+A8h] [rbp-60h] BYREF

  PartialRecord = (unsigned __int16 *)EmfEnumState::GetPartialRecord(this);
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
    `vector constructor iterator'(v12 + 1, 8u, (unsigned int)v7, (void *(*)(void *))CSmartGpObject::CSmartGpObject);
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
    *(_WORD *)&pv.lfUnderline = 0;
    pv.lfOutPrecision = 7;
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
    {
      _InterlockedIncrement(v30);
      v30 = v33;
    }
    CSmartGpObject::Release((CEmfPlusEnumState *)((char *)this + 2528));
    *((_QWORD *)this + 316) = v30;
    CSmartGpObject::Release((CSmartGpObject *)&v33);
  }
  GetPaletteEntries(*((HPALETTE *)this + 7), 0, 0x100u, (LPPALETTEENTRY)this + 798);
}

```

## disassembly

```asm
0x18005e880  mov     rax, rsp
0x18005e883  mov     [rax+10h], rbx
0x18005e887  mov     [rax+18h], rsi
0x18005e88b  mov     [rax+20h], rdi
0x18005e88f  push    rbp
0x18005e890  lea     rbp, [rax-28h]
0x18005e894  sub     rsp, 120h
0x18005e89b  mov     rax, cs:__security_cookie
0x18005e8a2  xor     rax, rsp
0x18005e8a5  mov     [rbp+20h+var_10], rax
0x18005e8a9  mov     rdi, rcx
0x18005e8ac  call    ?GetPartialRecord@EmfEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; EmfEnumState::GetPartialRecord(void)
0x18005e8b1  xor     edx, edx; Val
0x18005e8b3  lea     rcx, [rbp+20h+var_80]; void *
0x18005e8b7  mov     rbx, rax
0x18005e8ba  lea     r8d, [rdx+6Ch]; Size
0x18005e8be  call    memset_0
0x18005e8c3  mov     rcx, [rdi]
0x18005e8c6  mov     rax, [rcx+30h]
0x18005e8ca  mov     rcx, rdi
0x18005e8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8d2  mov     r8d, eax; Size
0x18005e8d5  cmp     r8, 6Ch ; 'l'
0x18005e8d9  jb      loc_18005EBF9
0x18005e8df  mov     r8d, [rdi+9BCh]; y
0x18005e8e6  xor     r9d, r9d; lppt
0x18005e8e9  mov     edx, [rdi+9B8h]; x
0x18005e8ef  mov     rcx, [rdi+10h]; hdc
0x18005e8f3  call    cs:__imp_SetBrushOrgEx
0x18005e8fa  nop     dword ptr [rax+rax+00h]
0x18005e8ff  mov     rdx, [rdi+948h]; hrgn
0x18005e906  test    rdx, rdx
0x18005e909  jnz     loc_18005EC0E
0x18005e90f  mov     rdx, [rdi+950h]; hPal
0x18005e916  test    rdx, rdx
0x18005e919  jnz     loc_18005EC3E
0x18005e91f  movzx   eax, word ptr [rbx+38h]
0x18005e923  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005e92a  mov     [rdi+0C74h], eax
0x18005e930  mov     esi, eax
0x18005e932  mov     eax, 8
0x18005e937  mul     rsi
0x18005e93a  cmovo   rax, rcx
0x18005e93e  add     rax, 8
0x18005e942  cmovb   rax, rcx
0x18005e946  xor     edx, edx
0x18005e948  mov     rcx, rax
0x18005e94b  call    GpMallocEx
0x18005e950  test    rax, rax
0x18005e953  jz      loc_18005EBA9
0x18005e959  lea     rbx, [rax+8]
0x18005e95d  mov     [rax], rsi
0x18005e960  mov     rcx, rbx; void *
0x18005e963  lea     r9, ??0CSmartGpObject@@QEAA@XZ; void *(*)(void *)
0x18005e96a  mov     r8d, esi; unsigned __int64
0x18005e96d  mov     edx, 8; unsigned __int64
0x18005e972  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18005e977  mov     [rdi+0A88h], rbx
0x18005e97e  test    rbx, rbx
0x18005e981  jz      loc_18005EC59
0x18005e987  mov     rcx, [rdi+10h]; hdc
0x18005e98b  call    cs:__imp_GetMapMode
0x18005e992  nop     dword ptr [rax+rax+00h]
0x18005e997  mov     rcx, [rdi+10h]; hdc
0x18005e99b  lea     rdx, [rdi+968h]; lppoint
0x18005e9a2  mov     [rdi+964h], eax
0x18005e9a8  call    cs:__imp_GetViewportOrgEx
0x18005e9af  nop     dword ptr [rax+rax+00h]
0x18005e9b4  mov     rcx, [rdi+10h]; hdc
0x18005e9b8  lea     rdx, [rdi+970h]; lppoint
0x18005e9bf  call    cs:__imp_GetWindowOrgEx
0x18005e9c6  nop     dword ptr [rax+rax+00h]
0x18005e9cb  mov     rcx, [rdi+10h]; hdc
0x18005e9cf  lea     rdx, [rdi+978h]; lpsize
0x18005e9d6  call    cs:__imp_GetViewportExtEx
0x18005e9dd  nop     dword ptr [rax+rax+00h]
0x18005e9e2  mov     rcx, [rdi+10h]; hdc
0x18005e9e6  lea     rdx, [rdi+980h]; lpsize
0x18005e9ed  call    cs:__imp_GetWindowExtEx
0x18005e9f4  nop     dword ptr [rax+rax+00h]
0x18005e9f9  movss   xmm2, cs:__real@3f800000
0x18005ea01  mov     edx, 1
0x18005ea06  mov     rcx, [rdi+958h]
0x18005ea0d  call    ?SetPageTransform@GpGraphics@@QEAA?AW4Status@@W4Unit@@M@Z; GpGraphics::SetPageTransform(Unit,float)
0x18005ea12  mov     rax, [rdi]
0x18005ea15  mov     rcx, rdi
0x18005ea18  mov     rax, [rax+48h]
0x18005ea1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea21  mov     rcx, [rdi+10h]; hdc
0x18005ea25  lea     rbx, [rdi+9C8h]
0x18005ea2c  mov     rdx, rbx; plimit
0x18005ea2f  call    cs:__imp_GetMiterLimit
0x18005ea36  nop     dword ptr [rax+rax+00h]
0x18005ea3b  test    eax, eax
0x18005ea3d  jz      loc_18005EC65
0x18005ea43  mov     rcx, [rdi+10h]; hdc
0x18005ea47  call    cs:__imp_GetBkMode
0x18005ea4e  nop     dword ptr [rax+rax+00h]
0x18005ea53  mov     rcx, [rdi+10h]; hdc
0x18005ea57  mov     [rdi+9C4h], eax
0x18005ea5d  call    cs:__imp_GetTextAlign
0x18005ea64  nop     dword ptr [rax+rax+00h]
0x18005ea69  mov     rcx, [rdi+10h]; hdc
0x18005ea6d  mov     [rdi+9A8h], eax
0x18005ea73  call    cs:__imp_GetTextColor
0x18005ea7a  nop     dword ptr [rax+rax+00h]
0x18005ea7f  mov     rcx, [rdi+10h]; hdc
0x18005ea83  mov     [rdi+9A0h], eax
0x18005ea89  call    cs:__imp_GetBkColor
0x18005ea90  nop     dword ptr [rax+rax+00h]
0x18005ea95  mov     rcx, [rdi+10h]; hdc
0x18005ea99  mov     [rdi+9A4h], eax
0x18005ea9f  call    cs:__imp_GetArcDirection
0x18005eaa6  nop     dword ptr [rax+rax+00h]
0x18005eaab  mov     rcx, [rdi+10h]; hdc
0x18005eaaf  mov     [rdi+9C0h], eax
0x18005eab5  call    cs:__imp_GetPolyFillMode
0x18005eabc  nop     dword ptr [rax+rax+00h]
0x18005eac1  xor     ecx, ecx
0x18005eac3  mov     ebx, 5Ch ; '\'
0x18005eac8  cmp     eax, 1
0x18005eacb  mov     r8d, ebx; Size
0x18005eace  setnz   cl
0x18005ead1  xor     edx, edx; Val
0x18005ead3  mov     [rdi+9ACh], ecx
0x18005ead9  lea     rcx, [rsp+120h+pv]; void *
0x18005eade  call    memset_0
0x18005eae3  mov     rcx, [rdi+10h]; hdc
0x18005eae7  lea     edx, [rbx-56h]; type
0x18005eaea  call    cs:__imp_GetCurrentObject
0x18005eaf1  nop     dword ptr [rax+rax+00h]
0x18005eaf6  lea     r8, [rsp+120h+pv]; pv
0x18005eafb  mov     edx, ebx; c
0x18005eafd  mov     rcx, rax; h
0x18005eb00  call    cs:__imp_GetObjectW
0x18005eb07  nop     dword ptr [rax+rax+00h]
0x18005eb0c  test    eax, eax
0x18005eb0e  jle     short loc_18005EB64
0x18005eb10  movzx   ebx, byte ptr [rsp+120h+var_CB]
0x18005eb15  xor     edx, edx
0x18005eb17  movzx   esi, byte ptr [rsp+120h+var_CB+1]
0x18005eb1c  and     [rsp+120h+var_CB], 0
0x18005eb22  mov     [rsp+120h+var_C8], 7
0x18005eb27  lea     ecx, [rdx+48h]
0x18005eb2a  call    GpMallocEx
0x18005eb2f  test    rax, rax
0x18005eb32  jnz     short loc_18005EBB0
0x18005eb34  xor     ebx, ebx
0x18005eb36  mov     [rsp+120h+var_F0], rbx
0x18005eb3b  lea     rsi, [rdi+9E0h]
0x18005eb42  test    rbx, rbx
0x18005eb45  jz      short loc_18005EB4F
0x18005eb47  lock inc dword ptr [rbx]
0x18005eb4a  mov     rbx, [rsp+120h+var_F0]
0x18005eb4f  mov     rcx, rsi; this
0x18005eb52  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x18005eb57  lea     rcx, [rsp+120h+var_F0]; this
0x18005eb5c  mov     [rsi], rbx
0x18005eb5f  call    ?Release@CSmartGpObject@@AEAAXXZ; CSmartGpObject::Release(void)
0x18005eb64  mov     rcx, [rdi+38h]; hpal
0x18005eb68  lea     r9, [rdi+0C78h]; pPalEntries
0x18005eb6f  xor     edx, edx; iStart
0x18005eb71  mov     r8d, 100h; cEntries
0x18005eb77  call    cs:__imp_GetPaletteEntries
0x18005eb7e  nop     dword ptr [rax+rax+00h]
0x18005eb83  mov     rcx, [rbp+20h+var_10]
0x18005eb87  xor     rcx, rsp; StackCookie
0x18005eb8a  call    __security_check_cookie
0x18005eb8f  lea     r11, [rsp+120h+var_s0]
0x18005eb97  mov     rbx, [r11+18h]
0x18005eb9b  mov     rsi, [r11+20h]
0x18005eb9f  mov     rdi, [r11+28h]
0x18005eba3  mov     rsp, r11
0x18005eba6  pop     rbp
0x18005eba7  retn
0x18005eba9  xor     ebx, ebx
0x18005ebab  jmp     loc_18005E977
0x18005ebb0  mov     rdx, [rdi+10h]; HDC
0x18005ebb4  lea     r8, [rsp+120h+pv]; struct tagLOGFONTW *
0x18005ebb9  mov     r9d, ebx; int
0x18005ebbc  mov     [rsp+120h+var_100], esi; int
0x18005ebc0  mov     rcx, rax; this
0x18005ebc3  call    ??0CEmfFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@HH@Z; CEmfFont::CEmfFont(HDC__ *,tagLOGFONTW *,int,int)
0x18005ebc8  mov     rsi, rax
0x18005ebcb  test    rax, rax
0x18005ebce  jz      loc_18005EB34
0x18005ebd4  xor     edx, edx
0x18005ebd6  lea     ecx, [rdx+10h]
0x18005ebd9  call    GpMallocEx
0x18005ebde  mov     rbx, rax
0x18005ebe1  test    rax, rax
0x18005ebe4  jz      loc_18005EB34
0x18005ebea  mov     dword ptr [rax], 1
0x18005ebf0  mov     [rax+8], rsi
0x18005ebf4  jmp     loc_18005EB36
0x18005ebf9  mov     rdx, rbx; Src
0x18005ebfc  lea     rcx, [rbp+20h+var_80]; void *
0x18005ec00  call    memcpy_0
0x18005ec05  lea     rbx, [rbp+20h+var_80]
0x18005ec09  jmp     loc_18005E8DF
0x18005ec0e  mov     rcx, [rdi+10h]; hdc
0x18005ec12  call    cs:__imp_SelectClipRgn
0x18005ec19  nop     dword ptr [rax+rax+00h]
0x18005ec1e  mov     rcx, [rdi+948h]; ho
0x18005ec25  call    cs:__imp_DeleteObject
0x18005ec2c  nop     dword ptr [rax+rax+00h]
0x18005ec31  and     qword ptr [rdi+948h], 0
0x18005ec39  jmp     loc_18005E90F
0x18005ec3e  mov     rcx, [rdi+10h]; hdc
0x18005ec42  mov     r8d, 1; bForceBkgd
0x18005ec48  call    cs:__imp_SelectPalette
0x18005ec4f  nop     dword ptr [rax+rax+00h]
0x18005ec54  jmp     loc_18005E91F
0x18005ec59  and     dword ptr [rdi+0C74h], 0
0x18005ec60  jmp     loc_18005E987
0x18005ec65  mov     dword ptr [rbx], 41200000h
0x18005ec6b  jmp     loc_18005EA43
```
