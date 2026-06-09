# EmfEnumState::SelectObject(void)

- ea: `0x18006920c`
- end: `0x1800693a5`
- name: `?SelectObject@EmfEnumState@@QEAAXXZ`
- size: `409`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180068a30`

## callees

- `0x180069098`
- `0x18006920c`
- `0x180069950`
- `0x18006b070`
- `0x180105d40`
- `0x180172010`

## import_xrefs

- `GDI32!CreatePenIndirect` at `0x180069300`
- `GDI32!CreatePenIndirect` at `0x180069300`
- `GDI32!CreateBrushIndirect` at `0x1800692ce`
- `GDI32!CreateBrushIndirect` at `0x1800692ce`
- `GDI32!GetStockObject` at `0x180069357`
- `GDI32!GetStockObject` at `0x180069357`
- `GDI32!SelectObject` at `0x180069333`
- `GDI32!SelectObject` at `0x180069333`

## pseudocode

```c
void __fastcall EmfEnumState::SelectObject(HDC *this)
{
  int v2; // edi
  unsigned int v3; // edi
  const struct RecolorStockObject near *const *v4; // rsi
  __int64 v5; // rbp
  HDC *v6; // r14
  HFONT PenIndirect; // rax
  __int64 v8; // rdx
  COLORREF v9; // eax
  COLORREF v10; // eax
  __int64 v11; // rax
  __int64 v12; // rsi
  HFONT StockObject; // rax
  LOGBRUSH plbrush; // [rsp+20h] [rbp-38h] BYREF

  if ( (*((unsigned int (__fastcall **)(HDC *))*this + 6))(this) >= 0xC )
  {
    v2 = EmfEnumState::GetPartialRecord((EmfEnumState *)this)->dParm[0];
    if ( v2 < 0 )
    {
      v3 = v2 & 0x7FFFFFFF;
      if ( v3 <= 7 && this[18] )
      {
        v4 = &RecolorStockObjectList;
        plbrush = 0;
        v5 = 0;
        while ( 1 )
        {
          if ( *(_DWORD *)v4 == v3 )
          {
            v6 = &this[v5];
            PenIndirect = (HFONT)v6[289];
            if ( PenIndirect )
              goto LABEL_14;
            v8 = *((unsigned int *)v4 + 1);
            if ( *((_DWORD *)v4 + 2) )
            {
              v9 = MfEnumState::ModifyColor(this, v8, 2);
              plbrush.lbStyle = 0;
              plbrush.lbColor = v9;
              plbrush.lbHatch = 0;
              PenIndirect = (HFONT)CreateBrushIndirect(&plbrush);
            }
            else
            {
              v10 = MfEnumState::ModifyColor(this, v8, 3);
              plbrush.lbStyle = 0;
              LODWORD(plbrush.lbHatch) = 0;
              plbrush.lbColor = v10;
              PenIndirect = (HFONT)CreatePenIndirect((const LOGPEN *)&plbrush);
            }
            v6[289] = (HDC)PenIndirect;
            if ( PenIndirect )
              goto LABEL_14;
          }
          v5 = (unsigned int)(v5 + 1);
          v4 = (const struct RecolorStockObject near *const *)((char *)v4 + 12);
          if ( (int)v5 >= 7 )
            goto LABEL_18;
        }
      }
      v11 = v3 - 10;
      if ( (unsigned int)v11 <= 7 )
      {
        v12 = (unsigned int)v11;
        PenIndirect = (HFONT)this[v11 + 9];
        if ( PenIndirect
          || (StockObject = (HFONT)GetStockObject(v3),
              PenIndirect = CreateTrueTypeFont(StockObject),
              (this[v12 + 9] = (HDC)PenIndirect) != 0) )
        {
LABEL_14:
          SelectObject(this[2], PenIndirect);
          return;
        }
      }
    }
LABEL_18:
    (*((void (__fastcall **)(HDC *))*this + 3))(this);
  }
}

```

## disassembly

```asm
0x18006920c  mov     [rsp+arg_8], rbx
0x180069211  mov     [rsp+arg_10], rbp
0x180069216  push    rsi
0x180069217  push    rdi
0x180069218  push    r14
0x18006921a  sub     rsp, 40h
0x18006921e  mov     rax, cs:__security_cookie
0x180069225  xor     rax, rsp
0x180069228  mov     [rsp+58h+var_28], rax
0x18006922d  mov     rax, [rcx]
0x180069230  mov     rbx, rcx
0x180069233  mov     rax, [rax+30h]
0x180069237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006923c  cmp     eax, 0Ch
0x18006923f  jb      loc_180069384
0x180069245  mov     rcx, rbx; this
0x180069248  call    ?GetPartialRecord@EmfEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; EmfEnumState::GetPartialRecord(void)
0x18006924d  mov     edi, [rax+8]
0x180069250  test    edi, edi
0x180069252  jns     loc_180069375
0x180069258  btr     edi, 1Fh
0x18006925c  cmp     edi, 7
0x18006925f  ja      loc_180069341
0x180069265  cmp     qword ptr [rbx+90h], 0
0x18006926d  jz      loc_180069341
0x180069273  xorps   xmm0, xmm0
0x180069276  lea     rsi, ?RecolorStockObjectList@@3QBURecolorStockObject@@B; RecolorStockObject const near * const RecolorStockObjectList
0x18006927d  movups  xmmword ptr [rsp+58h+plbrush.lbStyle], xmm0
0x180069282  xor     ebp, ebp
0x180069284  cmp     [rsi], edi
0x180069286  jnz     loc_18006931B
0x18006928c  lea     r14, [rbx+rbp*8]
0x180069290  mov     rax, [r14+908h]
0x180069297  test    rax, rax
0x18006929a  jnz     loc_18006932C
0x1800692a0  mov     rcx, rbx
0x1800692a3  mov     edx, [rsi+4]
0x1800692a6  cmp     [rsi+8], eax
0x1800692a9  jz      short loc_1800692DC
0x1800692ab  lea     r8d, [rax+2]
0x1800692af  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x1800692b4  lea     rcx, [rsp+58h+plbrush]; plbrush
0x1800692b9  mov     [rsp+58h+plbrush.lbStyle], 0
0x1800692c1  mov     [rsp+58h+plbrush.lbColor], eax
0x1800692c5  mov     [rsp+58h+plbrush.lbHatch], 0
0x1800692ce  call    cs:__imp_CreateBrushIndirect
0x1800692d5  nop     dword ptr [rax+rax+00h]
0x1800692da  jmp     short loc_18006930C
0x1800692dc  mov     r8d, 3
0x1800692e2  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x1800692e7  lea     rcx, [rsp+58h+plbrush]; plpen
0x1800692ec  mov     [rsp+58h+plbrush.lbStyle], 0
0x1800692f4  mov     dword ptr [rsp+58h+plbrush.lbHatch], 0
0x1800692fc  mov     [rsp+58h+plbrush.lbColor], eax
0x180069300  call    cs:__imp_CreatePenIndirect
0x180069307  nop     dword ptr [rax+rax+00h]
0x18006930c  mov     [r14+908h], rax
0x180069313  mov     rcx, rax
0x180069316  test    rax, rax
0x180069319  jnz     short loc_18006932C
0x18006931b  inc     ebp
0x18006931d  add     rsi, 0Ch
0x180069321  cmp     ebp, 7
0x180069324  jl      loc_180069284
0x18006932a  jmp     short loc_180069375
0x18006932c  mov     rcx, [rbx+10h]; hdc
0x180069330  mov     rdx, rax; h
0x180069333  call    cs:__imp_SelectObject
0x18006933a  nop     dword ptr [rax+rax+00h]
0x18006933f  jmp     short loc_180069384
0x180069341  lea     eax, [rdi-0Ah]
0x180069344  cmp     eax, 7
0x180069347  ja      short loc_180069375
0x180069349  mov     esi, eax
0x18006934b  mov     rax, [rbx+rax*8+48h]
0x180069350  test    rax, rax
0x180069353  jnz     short loc_18006932C
0x180069355  mov     ecx, edi; i
0x180069357  call    cs:__imp_GetStockObject
0x18006935e  nop     dword ptr [rax+rax+00h]
0x180069363  mov     rcx, rax; h
0x180069366  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x18006936b  mov     [rbx+rsi*8+48h], rax
0x180069370  test    rax, rax
0x180069373  jnz     short loc_18006932C
0x180069375  mov     rax, [rbx]
0x180069378  mov     rcx, rbx
0x18006937b  mov     rax, [rax+18h]
0x18006937f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069384  mov     rcx, [rsp+58h+var_28]
0x180069389  xor     rcx, rsp; StackCookie
0x18006938c  call    __security_check_cookie
0x180069391  mov     rbx, [rsp+58h+arg_8]
0x180069396  mov     rbp, [rsp+58h+arg_10]
0x18006939b  add     rsp, 40h
0x18006939f  pop     r14
0x1800693a1  pop     rdi
0x1800693a2  pop     rsi
0x1800693a3  retn
```
