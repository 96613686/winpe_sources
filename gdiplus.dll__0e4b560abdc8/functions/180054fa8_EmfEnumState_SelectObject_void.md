# EmfEnumState::SelectObject(void)

- ea: `0x180054fa8`
- end: `0x180055126`
- name: `?SelectObject@EmfEnumState@@QEAAXXZ`
- size: `382`
- prototype: `void __fastcall(EmfEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180054990`

## callees

- `0x180054fa8`
- `0x18005512c`
- `0x180055938`
- `0x1800567c0`
- `0x1800e9380`
- `0x180175010`

## import_xrefs

- `GDI32!CreatePenIndirect` at `0x1800550fa`
- `GDI32!CreatePenIndirect` at `0x1800550fa`
- `GDI32!CreateBrushIndirect` at `0x1800550ce`
- `GDI32!CreateBrushIndirect` at `0x1800550ce`
- `GDI32!GetStockObject` at `0x180055045`
- `GDI32!GetStockObject` at `0x180055045`
- `GDI32!SelectObject` at `0x180055035`
- `GDI32!SelectObject` at `0x180055035`

## pseudocode

```c
void __fastcall EmfEnumState::SelectObject(HDC *this)
{
  __int64 v2; // rcx
  int v3; // edi
  unsigned int v4; // edi
  HFONT PenIndirect; // rax
  HFONT StockObject; // rax
  int *v7; // rsi
  __int64 i; // r14
  __int64 v9; // rdx
  COLORREF v10; // eax
  COLORREF v11; // eax
  LOGBRUSH plbrush; // [rsp+20h] [rbp-28h] BYREF

  v3 = EmfEnumState::GetPartialRecord((EmfEnumState *)this)->dParm[0];
  if ( v3 >= 0 )
    goto LABEL_2;
  v4 = v3 & 0x7FFFFFFF;
  if ( v4 <= 7 )
  {
    if ( *(_QWORD *)(v2 + 144) )
    {
      v7 = &dword_18018B954;
      plbrush = 0;
      for ( i = 289; i < 296; ++i )
      {
        if ( *(v7 - 1) == v4 )
        {
          PenIndirect = (HFONT)this[i];
          if ( PenIndirect )
            goto LABEL_6;
          v9 = (unsigned int)*v7;
          if ( v7[1] )
          {
            v10 = MfEnumState::ModifyColor(this, v9, 2);
            plbrush.lbStyle = 0;
            plbrush.lbHatch = 0;
            plbrush.lbColor = v10;
            PenIndirect = (HFONT)CreateBrushIndirect(&plbrush);
          }
          else
          {
            v11 = MfEnumState::ModifyColor(this, v9, 3);
            plbrush.lbStyle = 0;
            LODWORD(plbrush.lbHatch) = 0;
            plbrush.lbColor = v11;
            PenIndirect = (HFONT)CreatePenIndirect((const LOGPEN *)&plbrush);
          }
          this[i] = (HDC)PenIndirect;
          if ( PenIndirect )
            goto LABEL_6;
        }
        v7 += 3;
      }
    }
    goto LABEL_2;
  }
  if ( v4 - 10 > 7
    || (PenIndirect = *(HFONT *)(v2 + 8LL * (v4 - 10) + 72)) == 0
    && (StockObject = (HFONT)GetStockObject(v4),
        PenIndirect = CreateTrueTypeFont(StockObject),
        (this[v4 - 1] = (HDC)PenIndirect) == 0) )
  {
LABEL_2:
    (*((void (__fastcall **)(HDC *))*this + 3))(this);
    return;
  }
LABEL_6:
  SelectObject(this[2], PenIndirect);
}

```

## disassembly

```asm
0x180054fa8  mov     [rsp+arg_8], rbx
0x180054fad  mov     [rsp+arg_10], rsi
0x180054fb2  mov     [rsp+arg_18], rdi
0x180054fb7  push    r14
0x180054fb9  sub     rsp, 40h
0x180054fbd  mov     rax, cs:__security_cookie
0x180054fc4  xor     rax, rsp
0x180054fc7  mov     [rsp+48h+var_18], rax
0x180054fcc  mov     rbx, rcx
0x180054fcf  call    ?GetPartialRecord@EmfEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; EmfEnumState::GetPartialRecord(void)
0x180054fd4  mov     edi, [rax+8]
0x180054fd7  test    edi, edi
0x180054fd9  js      short loc_18005500E
0x180054fdb  mov     rax, [rbx]
0x180054fde  mov     rcx, rbx
0x180054fe1  mov     rax, [rax+18h]
0x180054fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fea  mov     rcx, [rsp+48h+var_18]
0x180054fef  xor     rcx, rsp; StackCookie
0x180054ff2  call    __security_check_cookie
0x180054ff7  mov     rbx, [rsp+48h+arg_8]
0x180054ffc  mov     rsi, [rsp+48h+arg_10]
0x180055001  mov     rdi, [rsp+48h+arg_18]
0x180055006  add     rsp, 40h
0x18005500a  pop     r14
0x18005500c  retn
0x18005500e  btr     edi, 1Fh
0x180055012  cmp     edi, 7
0x180055015  jbe     short loc_180055069
0x180055017  lea     eax, [rdi-0Ah]
0x18005501a  cmp     eax, 7
0x18005501d  ja      short loc_180054FDB
0x18005501f  lea     eax, [rdi-0Ah]
0x180055022  mov     esi, eax
0x180055024  mov     rax, [rcx+rax*8+48h]
0x180055029  test    rax, rax
0x18005502c  jz      short loc_180055043
0x18005502e  mov     rcx, [rbx+10h]; hdc
0x180055032  mov     rdx, rax; h
0x180055035  call    cs:__imp_SelectObject
0x18005503c  nop     dword ptr [rax+rax+00h]
0x180055041  jmp     short loc_180054FEA
0x180055043  mov     ecx, edi; i
0x180055045  call    cs:__imp_GetStockObject
0x18005504c  nop     dword ptr [rax+rax+00h]
0x180055051  mov     rcx, rax; h
0x180055054  call    ?CreateTrueTypeFont@@YAPEAUHFONT__@@PEAU1@@Z; CreateTrueTypeFont(HFONT__ *)
0x180055059  mov     [rbx+rsi*8+48h], rax
0x18005505e  test    rax, rax
0x180055061  jz      loc_180054FDB
0x180055067  jmp     short loc_18005502E
0x180055069  cmp     qword ptr [rcx+90h], 0
0x180055071  jz      loc_180054FDB
0x180055077  xorps   xmm0, xmm0
0x18005507a  lea     rsi, dword_18018B954
0x180055081  movups  xmmword ptr [rsp+48h+plbrush.lbStyle], xmm0
0x180055086  mov     r14d, 908h
0x18005508c  cmp     r14, 940h
0x180055093  jge     loc_180054FDB
0x180055099  cmp     [rsi-4], edi
0x18005509c  jnz     short loc_180055119
0x18005509e  mov     rax, [r14+rbx]
0x1800550a2  test    rax, rax
0x1800550a5  jnz     short loc_18005502E
0x1800550a7  mov     rcx, rbx
0x1800550aa  mov     edx, [rsi]
0x1800550ac  cmp     [rsi+4], eax
0x1800550af  jz      short loc_1800550DC
0x1800550b1  lea     r8d, [rax+2]
0x1800550b5  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x1800550ba  and     [rsp+48h+plbrush.lbStyle], 0
0x1800550bf  lea     rcx, [rsp+48h+plbrush]; plbrush
0x1800550c4  and     [rsp+48h+plbrush.lbHatch], 0
0x1800550ca  mov     [rsp+48h+plbrush.lbColor], eax
0x1800550ce  call    cs:__imp_CreateBrushIndirect
0x1800550d5  nop     dword ptr [rax+rax+00h]
0x1800550da  jmp     short loc_180055106
0x1800550dc  mov     r8d, 3
0x1800550e2  call    ?ModifyColor@MfEnumState@@IEAAKKW4ColorAdjustType@@@Z; MfEnumState::ModifyColor(ulong,ColorAdjustType)
0x1800550e7  and     [rsp+48h+plbrush.lbStyle], 0
0x1800550ec  lea     rcx, [rsp+48h+plbrush]; plpen
0x1800550f1  and     dword ptr [rsp+48h+plbrush.lbHatch], 0
0x1800550f6  mov     [rsp+48h+plbrush.lbColor], eax
0x1800550fa  call    cs:__imp_CreatePenIndirect
0x180055101  nop     dword ptr [rax+rax+00h]
0x180055106  mov     rcx, r14
0x180055109  mov     rdx, rbx
0x18005510c  mov     [rbx+rcx], rax
0x180055110  test    rax, rax
0x180055113  jnz     loc_18005502E
0x180055119  add     r14, 8
0x18005511d  add     rsi, 0Ch
0x180055121  jmp     loc_18005508C
```
