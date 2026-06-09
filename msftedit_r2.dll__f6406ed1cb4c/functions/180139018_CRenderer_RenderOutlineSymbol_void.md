# CRenderer::RenderOutlineSymbol(void)

- ea: `0x180139018`
- end: `0x1801392ce`
- name: `?RenderOutlineSymbol@CRenderer@@QEAAHXZ`
- size: `694`
- prototype: `__int64 __fastcall(CRenderer *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18002c668`

## callees

- `0x18001668c`
- `0x1800187f0`
- `0x180040110`
- `0x180043f2c`
- `0x180045af4`
- `0x1800501ac`
- `0x1800e9918`
- `0x180112598`
- `0x180122b20`
- `0x180139018`
- `0x1801392d4`
- `0x18014eb54`
- `0x1801694b4`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801392aa`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801392aa`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18013909e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18013909e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801391b3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18013929b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801391b3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18013929b`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180139289`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x180139289`

## pseudocode

```c
__int64 __fastcall CRenderer::RenderOutlineSymbol(CRenderer *this)
{
  const struct CParaFormat *PF; // rax
  int v3; // eax
  LONG v4; // ecx
  HDC v5; // rax
  HDC hdcSrc; // r12
  const struct CParaFormat *v8; // rax
  unsigned int v9; // r15d
  HGDIOBJ v10; // rdi
  int v11; // ebx
  int CchLeft; // eax
  int EOP; // r11d
  __int64 v14; // xmm1_8
  __int128 v15; // xmm0
  const struct CParaFormat *v16; // rax
  int v17; // ebx
  bool v18; // cc
  HGDIOBJ v19; // rsi
  int hDest; // edi
  int Ascent; // eax
  int v22; // r8d
  int v23; // ecx
  int v24; // eax
  CDisplay *v25; // rcx
  int v26; // ebx
  HDC v27; // rax
  int v28; // [rsp+60h] [rbp-39h]
  _BYTE v29[24]; // [rsp+68h] [rbp-31h] BYREF
  __int128 v30; // [rsp+80h] [rbp-19h] BYREF
  __int64 v31; // [rsp+90h] [rbp-9h]
  __int128 v32; // [rsp+98h] [rbp-1h]
  int wSrc; // [rsp+100h] [rbp+67h]
  struct tagPOINT xDest; // [rsp+108h] [rbp+6Fh] BYREF
  int v35; // [rsp+110h] [rbp+77h] BYREF
  int v36; // [rsp+114h] [rbp+7Bh]
  int v37; // [rsp+118h] [rbp+7Fh]

  PF = (const struct CParaFormat *)*((_QWORD *)this + 37);
  if ( !PF )
    PF = CRchTxtPtr::GetPF(this);
  v3 = CMeasurerNoFC::LUtoDUZ(this, 360 * (unsigned int)*((unsigned __int8 *)PF + 35));
  v4 = *((_DWORD *)this + 128);
  v37 = v3;
  v35 = *((_DWORD *)this + 25);
  v28 = *((_DWORD *)this + 129);
  xDest.x = v4;
  if ( !h && (unsigned int)InitializeOutlineBitmaps() )
    return 0;
  v5 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
  hdcSrc = CreateCompatibleDC(v5);
  if ( !hdcSrc )
    return 0;
  v8 = (const struct CParaFormat *)*((_QWORD *)this + 37);
  if ( !v8 )
    v8 = CRchTxtPtr::GetPF(this);
  v9 = 1;
  if ( (*((_BYTE *)v8 + 35) & 1) != 0 )
  {
    v10 = h;
    v11 = 4;
    wSrc = 4;
  }
  else
  {
    v10 = (HGDIOBJ)qword_1802E4548;
    v11 = 10;
    wSrc = 10;
    CPFRunPtr::CPFRunPtr((CPFRunPtr *)v29, this);
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)v29);
    if ( EOP < CchLeft )
    {
      v14 = *((_QWORD *)this + 4);
      v30 = *((_OWORD *)this + 1);
      v15 = *(_OWORD *)((char *)this + 40);
      v31 = v14;
      v32 = v15;
      EOP = CTxtPtrEx::FindEOP((CTxtPtrEx *)&v30, 0x3FFFFFFF, 0, 0);
    }
    CRunPtrBase::Move((CRunPtrBase *)v29, EOP);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)v29) )
    {
      v10 = qword_1802E4550;
    }
    else
    {
      v16 = (const struct CParaFormat *)*((_QWORD *)this + 37);
      if ( !v16 )
        v16 = CRchTxtPtr::GetPF(this);
      v17 = *((unsigned __int8 *)v16 + 35);
      v18 = v17 < (int)CPFRunPtr::GetOutlineLevel((CPFRunPtr *)v29);
      v11 = 10;
      if ( v18 )
        v10 = qword_1802E4558;
    }
  }
  if ( v10 )
  {
    v19 = SelectObject(hdcSrc, v10);
    hDest = CDisplay::Zoom(*((CDisplay **)this + 19), v11);
    Ascent = CLine::GetAscent((CRenderer *)((char *)this + 96), 0, 0);
    v22 = Ascent - hDest;
    v23 = hDest - Ascent;
    v35 = v37 + xDest.x - v35;
    xDest = 0;
    v24 = (Ascent - hDest) / 2;
    if ( v22 <= 0 )
      v24 = v23;
    v25 = (CDisplay *)*((_QWORD *)this + 19);
    v36 = v28 + v24;
    CDisplay::PointFromPointuv(v25, &xDest, (const struct Ptls6::tagLSPOINTUV *)&v35, 0, 0);
    v26 = CDisplay::Zoom(*((CDisplay **)this + 19), v11);
    v27 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
    StretchBlt(v27, xDest.x, xDest.y, v26, hDest, hdcSrc, 0, 0, wSrc, wSrc, 0xCC0020u);
    SelectObject(hdcSrc, v19);
  }
  else
  {
    v9 = 0;
  }
  DeleteDC(hdcSrc);
  return v9;
}

```

## disassembly

```asm
0x180139018  push    rbp
0x18013901a  push    rbx
0x18013901b  push    rsi
0x18013901c  push    rdi
0x18013901d  push    r12
0x18013901f  push    r13
0x180139021  push    r14
0x180139023  push    r15
0x180139025  lea     rbp, [rsp-1Fh]
0x18013902a  sub     rsp, 0B8h
0x180139031  mov     rax, [rcx+128h]
0x180139038  mov     r14, rcx
0x18013903b  test    rax, rax
0x18013903e  jnz     short loc_180139045
0x180139040  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180139045  movzx   eax, byte ptr [rax+23h]
0x180139049  mov     rcx, r14; this
0x18013904c  imul    edx, eax, 168h; int
0x180139052  call    ?LUtoDUZ@CMeasurerNoFC@@QEBAJJ@Z; CMeasurerNoFC::LUtoDUZ(long)
0x180139057  cmp     cs:h, 0
0x18013905f  mov     ecx, [r14+200h]
0x180139066  mov     [rbp+57h+arg_18], eax
0x180139069  mov     eax, [r14+64h]
0x18013906d  mov     [rbp+57h+arg_10], eax
0x180139070  mov     eax, [r14+204h]
0x180139077  mov     [rbp+57h+var_90], eax
0x18013907a  mov     dword ptr [rbp+57h+xDest], ecx
0x18013907d  jnz     short loc_180139088
0x18013907f  call    ?InitializeOutlineBitmaps@@YAJXZ; InitializeOutlineBitmaps(void)
0x180139084  test    eax, eax
0x180139086  jnz     short loc_1801390B2
0x180139088  mov     rcx, [r14+150h]
0x18013908f  mov     rax, [rcx]
0x180139092  mov     rax, [rax+30h]
0x180139096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013909b  mov     rcx, rax; hdc
0x18013909e  call    cs:__imp_CreateCompatibleDC
0x1801390a5  nop     dword ptr [rax+rax+00h]
0x1801390aa  mov     r12, rax
0x1801390ad  test    rax, rax
0x1801390b0  jnz     short loc_1801390B9
0x1801390b2  xor     eax, eax
0x1801390b4  jmp     loc_1801392B9
0x1801390b9  mov     rax, [r14+128h]
0x1801390c0  test    rax, rax
0x1801390c3  jnz     short loc_1801390CD
0x1801390c5  mov     rcx, r14; this
0x1801390c8  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1801390cd  mov     r15d, 1
0x1801390d3  test    [rax+23h], r15b
0x1801390d7  jz      short loc_1801390EC
0x1801390d9  mov     rdi, cs:h
0x1801390e0  lea     ebx, [r15+3]
0x1801390e4  mov     [rbp+57h+arg_0], ebx
0x1801390e7  jmp     loc_1801391A0
0x1801390ec  mov     rdi, cs:qword_1802E4548
0x1801390f3  lea     rcx, [rbp+57h+var_88]; this
0x1801390f7  mov     ebx, 0Ah
0x1801390fc  mov     rdx, r14; struct CRchTxtPtr *
0x1801390ff  mov     [rbp+57h+arg_0], ebx
0x180139102  call    ??0CPFRunPtr@@QEAA@AEBVCRchTxtPtr@@@Z; CPFRunPtr::CPFRunPtr(CRchTxtPtr const &)
0x180139107  mov     r11d, [r14+60h]
0x18013910b  lea     rcx, [rbp+57h+var_88]; this
0x18013910f  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x180139114  cmp     r11d, eax
0x180139117  jge     short loc_18013914E
0x180139119  movups  xmm0, xmmword ptr [r14+10h]
0x18013911e  lea     rcx, [rbp+57h+var_70]; this
0x180139122  xor     r9d, r9d; int
0x180139125  movsd   xmm1, qword ptr [r14+20h]
0x18013912b  xor     r8d, r8d; int *
0x18013912e  movups  [rbp+57h+var_70], xmm0
0x180139132  mov     edx, 3FFFFFFFh; int
0x180139137  movups  xmm0, xmmword ptr [r14+28h]
0x18013913c  movsd   [rbp+57h+var_60], xmm1
0x180139141  movdqu  [rbp+57h+var_58], xmm0
0x180139146  call    ?FindEOP@CTxtPtrEx@@QEAAJJPEAJH@Z; CTxtPtrEx::FindEOP(long,long *,int)
0x18013914b  mov     r11d, eax
0x18013914e  mov     edx, r11d; int
0x180139151  lea     rcx, [rbp+57h+var_88]; this
0x180139155  call    ?Move@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::Move(long)
0x18013915a  lea     rcx, [rbp+57h+var_88]; this
0x18013915e  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180139163  test    eax, eax
0x180139165  jz      short loc_180139170
0x180139167  mov     rdi, cs:qword_1802E4550
0x18013916e  jmp     short loc_1801391A0
0x180139170  mov     rax, [r14+128h]
0x180139177  test    rax, rax
0x18013917a  jnz     short loc_180139184
0x18013917c  mov     rcx, r14; this
0x18013917f  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180139184  movzx   ebx, byte ptr [rax+23h]
0x180139188  lea     rcx, [rbp+57h+var_88]; this
0x18013918c  call    ?GetOutlineLevel@CPFRunPtr@@QEAAJXZ; CPFRunPtr::GetOutlineLevel(void)
0x180139191  cmp     ebx, eax
0x180139193  mov     ebx, 0Ah
0x180139198  cmovl   rdi, cs:qword_1802E4558
0x1801391a0  test    rdi, rdi
0x1801391a3  jnz     short loc_1801391AD
0x1801391a5  xor     r15d, r15d
0x1801391a8  jmp     loc_1801392A7
0x1801391ad  mov     rdx, rdi; h
0x1801391b0  mov     rcx, r12; hdc
0x1801391b3  call    cs:__imp_SelectObject
0x1801391ba  nop     dword ptr [rax+rax+00h]
0x1801391bf  mov     rcx, [r14+98h]; this
0x1801391c6  mov     edx, ebx; int
0x1801391c8  mov     rsi, rax
0x1801391cb  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x1801391d0  xor     r8d, r8d; struct CDisplay *
0x1801391d3  lea     rcx, [r14+60h]; this
0x1801391d7  xor     edx, edx; bool
0x1801391d9  mov     edi, eax
0x1801391db  call    ?GetAscent@CLine@@QEBAJ_NPEBVCDisplay@@@Z; CLine::GetAscent(bool,CDisplay const *)
0x1801391e0  mov     r8d, eax
0x1801391e3  mov     r9d, 2
0x1801391e9  mov     eax, dword ptr [rbp+57h+xDest]
0x1801391ec  sub     r8d, edi
0x1801391ef  sub     eax, [rbp+57h+arg_10]
0x1801391f2  mov     ecx, r8d
0x1801391f5  add     eax, [rbp+57h+arg_18]
0x1801391f8  neg     ecx
0x1801391fa  mov     [rbp+57h+arg_10], eax
0x1801391fd  xor     r13d, r13d
0x180139200  mov     eax, r8d
0x180139203  mov     [rbp+57h+xDest], r13
0x180139207  cdq
0x180139208  mov     byte ptr [rsp+0F0h+hDest], r13b; bool
0x18013920d  idiv    r9d
0x180139210  test    r8d, r8d
0x180139213  lea     rdx, [rbp+57h+xDest]; struct tagPOINT *
0x180139217  lea     r8, [rbp+57h+arg_10]; struct Ptls6::tagLSPOINTUV *
0x18013921b  cmovle  eax, ecx
0x18013921e  mov     rcx, [r14+98h]; this
0x180139225  add     eax, [rbp+57h+var_90]
0x180139228  xor     r9d, r9d; bool
0x18013922b  mov     [rbp+57h+arg_14], eax
0x18013922e  call    ?PointFromPointuv@CDisplay@@QEBAXAEAUtagPOINT@@AEBUtagLSPOINTUV@Ptls6@@_N2@Z; CDisplay::PointFromPointuv(tagPOINT &,Ptls6::tagLSPOINTUV const &,bool,bool)
0x180139233  mov     rcx, [r14+98h]; this
0x18013923a  mov     edx, ebx; int
0x18013923c  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180139241  mov     rcx, [r14+150h]
0x180139248  mov     ebx, eax
0x18013924a  mov     rdx, [rcx]
0x18013924d  mov     rax, [rdx+30h]
0x180139251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139256  mov     ecx, [rbp+57h+arg_0]
0x180139259  mov     r9d, ebx; wDest
0x18013925c  mov     r8d, dword ptr [rbp+57h+xDest+4]; yDest
0x180139260  mov     edx, dword ptr [rbp+57h+xDest]; xDest
0x180139263  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18013926b  mov     [rsp+0F0h+hSrc], ecx; hSrc
0x18013926f  mov     [rsp+0F0h+wSrc], ecx; wSrc
0x180139273  mov     rcx, rax; hdcDest
0x180139276  mov     [rsp+0F0h+ySrc], r13d; ySrc
0x18013927b  mov     [rsp+0F0h+xSrc], r13d; xSrc
0x180139280  mov     [rsp+0F0h+hdcSrc], r12; hdcSrc
0x180139285  mov     [rsp+0F0h+hDest], edi; hDest
0x180139289  call    cs:__imp_StretchBlt
0x180139290  nop     dword ptr [rax+rax+00h]
0x180139295  mov     rdx, rsi; h
0x180139298  mov     rcx, r12; hdc
0x18013929b  call    cs:__imp_SelectObject
0x1801392a2  nop     dword ptr [rax+rax+00h]
0x1801392a7  mov     rcx, r12; hdc
0x1801392aa  call    cs:__imp_DeleteDC
0x1801392b1  nop     dword ptr [rax+rax+00h]
0x1801392b6  mov     eax, r15d
0x1801392b9  add     rsp, 0B8h
0x1801392c0  pop     r15
0x1801392c2  pop     r14
0x1801392c4  pop     r13
0x1801392c6  pop     r12
0x1801392c8  pop     rdi
0x1801392c9  pop     rsi
0x1801392ca  pop     rbx
0x1801392cb  pop     rbp
0x1801392cc  retn
```
