# fsc_CalcGrayMapGdiCompatible(GlyphBitMap *,GlyphBitMap *,ushort)

- ea: `0x1400275c4`
- end: `0x1400277c1`
- name: `?fsc_CalcGrayMapGdiCompatible@@YAHPEAUGlyphBitMap@@0G@Z`
- size: `509`
- prototype: `__int64 __fastcall(struct GlyphBitMap *, struct GlyphBitMap *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011f54`

## callees

- `0x14000fee4`
- `0x1400275c4`
- `0x1400277c8`
- `0x140029244`
- `0x140072578`
- `0x14007680c`

## pseudocode

```c
__int64 __fastcall fsc_CalcGrayMapGdiCompatible(unsigned __int64 a1, void **a2, __int16 a3)
{
  int v3; // r15d
  struct GlyphBitMap *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // rax
  __int64 *v12; // rax
  __int64 v13; // r12
  __int64 v14; // rcx
  __int16 v15; // di
  __int16 v16; // ax
  __int16 v17; // bx
  __int16 v18; // cx
  __int16 v19; // cx
  __int64 v20; // r12
  __int16 v21; // ax
  int v22; // ecx
  char *v23; // r13
  __int16 v24; // si
  unsigned __int16 v26; // ax
  _QWORD v27[2]; // [rsp+20h] [rbp-40h] BYREF
  __int16 v28; // [rsp+30h] [rbp-30h]
  __int16 v29; // [rsp+32h] [rbp-2Eh]
  __int16 v30; // [rsp+34h] [rbp-2Ch]
  __int16 v31; // [rsp+36h] [rbp-2Ah]
  void *v32; // [rsp+38h] [rbp-28h]
  __int64 v33; // [rsp+40h] [rbp-20h]
  void *v34; // [rsp+48h] [rbp-18h]
  __int64 v35; // [rsp+50h] [rbp-10h]
  struct GlyphBitMap *v36; // [rsp+A0h] [rbp+40h]
  void *v37; // [rsp+A8h] [rbp+48h] BYREF

  v36 = (struct GlyphBitMap *)a1;
  v3 = a3;
  v27[0] = 0;
  v31 = 0;
  v5 = (struct GlyphBitMap *)a1;
  v6 = (unsigned int)(*((__int16 *)a2 + 1) - *((__int16 *)a2 + 3));
  if ( (int)v6 < 0 )
    goto LABEL_17;
  a1 = *(__int16 *)a2 * (unsigned __int64)(unsigned int)v6;
  if ( a1 > 0xFFFFFFFF )
    goto LABEL_17;
  memset_0(a2[4], 0, a1 & 0xFFFFFFFC);
  v7 = *((unsigned int *)v5 + 7);
  v32 = (void *)*((_QWORD *)v5 + 4);
  v37 = v32;
  v29 = v3;
  v8 = (__int64 *)operator+=<char,int,SafeIntExceptionHandler<SafeIntRasterizerException>>(&v37, v7);
  v9 = *((unsigned int *)a2 + 7);
  v10 = *v8;
  v11 = a2[4];
  v33 = v10;
  v34 = v11;
  v37 = v11;
  v12 = (__int64 *)operator+=<char,int,SafeIntExceptionHandler<SafeIntRasterizerException>>(&v37, v9);
  v13 = *((_QWORD *)v5 + 4);
  v14 = *v12;
  LODWORD(v12) = *((__int16 *)v5 + 3);
  v35 = v14;
  SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(
    (unsigned int)(*((__int16 *)v5 + 1) - (_DWORD)v12),
    &v37);
  v15 = (__int16)v37;
  a1 = (unsigned int)(*((__int16 *)a2 + 1) * v3);
  v16 = *((_WORD *)v5 + 1) - *((_WORD *)a2 + 1) * v3;
  if ( v16 < 0 )
  {
    v26 = *((_WORD *)a2 + 1) * v3 - *((_WORD *)v5 + 1);
    if ( v26 <= (unsigned __int16)v3 )
    {
      v17 = v3 - v26;
      goto LABEL_5;
    }
LABEL_17:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, v6);
    JUMPOUT(0x1400277C0LL);
  }
  v17 = v3;
  v13 += v16 * *(__int16 *)v5;
  SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(
    (unsigned int)((__int16)v37 - v16),
    &v37);
  v15 = (__int16)v37;
LABEL_5:
  v18 = *((_WORD *)a2 + 4);
  v28 = v18 - *((_WORD *)a2 + 2);
  v19 = v3 * v18 - *((_WORD *)v5 + 2);
  v20 = ((__int64)(v19 - 1) >> 3) + v13;
  v21 = 7 - ((v19 - 1) & 7);
  v22 = *((__int16 *)a2 + 1);
  v30 = v21;
  v23 = (char *)a2[4] + v28 - 1;
  SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(
    (unsigned int)(v22 - 1),
    &v37);
  v24 = (__int16)v37;
  a1 = 4294934528LL;
  while ( *((__int16 *)a2 + 3) <= v24 )
  {
    v27[1] = v23;
    while ( v17 && v15 > 0 )
    {
      v27[0] = v20;
      fsc_CalcGrayRow((struct GrayScaleParam *)v27);
      a1 = 4294934528LL;
      v20 += *(__int16 *)v36;
      --v17;
      --v15;
    }
    if ( v24 == (__int16)0x8000 )
      goto LABEL_17;
    v17 = v3;
    v23 += *(__int16 *)a2;
    --v24;
  }
  return 0;
}

```

## disassembly

```asm
0x1400275c4  mov     [rsp-38h+arg_10], rbx
0x1400275c9  mov     [rsp-38h+arg_0], rcx
0x1400275ce  push    rbp
0x1400275cf  push    rsi
0x1400275d0  push    rdi
0x1400275d1  push    r12
0x1400275d3  push    r13
0x1400275d5  push    r14
0x1400275d7  push    r15
0x1400275d9  mov     rbp, rsp
0x1400275dc  sub     rsp, 60h
0x1400275e0  xor     eax, eax
0x1400275e2  movsx   r15d, r8w
0x1400275e6  mov     r14, rdx
0x1400275e9  mov     [rbp+var_40], rax
0x1400275ed  mov     [rbp+var_2A], ax
0x1400275f1  mov     rsi, rcx
0x1400275f4  movsx   eax, word ptr [rdx+6]
0x1400275f8  movsx   edx, word ptr [rdx+2]
0x1400275fc  sub     edx, eax
0x1400275fe  js      loc_1400277BB
0x140027604  movsx   rax, word ptr [r14]
0x140027608  mov     ecx, edx
0x14002760a  imul    rcx, rax
0x14002760e  mov     eax, 0FFFFFFFFh
0x140027613  cmp     rcx, rax
0x140027616  ja      loc_1400277BB
0x14002761c  mov     r8d, ecx
0x14002761f  xor     edx, edx; Val
0x140027621  mov     rcx, [r14+20h]; void *
0x140027625  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x140027629  call    memset_0
0x14002762e  mov     rax, [rsi+20h]
0x140027632  lea     rcx, [rbp+arg_8]
0x140027636  mov     edx, [rsi+1Ch]
0x140027639  mov     [rbp+var_28], rax
0x14002763d  mov     [rbp+arg_8], rax
0x140027641  mov     [rbp+var_2E], r15w
0x140027646  call    ??$?YDHV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEADAEAPEADV?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<char,int,SafeIntExceptionHandler<SafeIntRasterizerException>>(char * &,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14002764b  mov     edx, [r14+1Ch]
0x14002764f  mov     rcx, [rax]
0x140027652  mov     rax, [r14+20h]
0x140027656  mov     [rbp+var_20], rcx
0x14002765a  lea     rcx, [rbp+arg_8]
0x14002765e  mov     [rbp+var_18], rax
0x140027662  mov     [rbp+arg_8], rax
0x140027666  call    ??$?YDHV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEADAEAPEADV?$SafeInt@HV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<char,int,SafeIntExceptionHandler<SafeIntRasterizerException>>(char * &,SafeInt<int,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14002766b  mov     r12, [rsi+20h]
0x14002766f  lea     rdx, [rbp+arg_8]
0x140027673  mov     rcx, [rax]
0x140027676  movsx   eax, word ptr [rsi+6]
0x14002767a  mov     [rbp+var_10], rcx
0x14002767e  movsx   ecx, word ptr [rsi+2]
0x140027682  sub     ecx, eax
0x140027684  call    ??$CastThrow@V?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@?$SafeCastHelper@FH$03@@SAXHAEAF@Z; SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(int,short &)
0x140027689  movsx   eax, word ptr [r14+2]
0x14002768e  mov     ecx, r15d
0x140027691  movsx   edi, word ptr [rbp+arg_8]
0x140027695  imul    ecx, eax
0x140027698  movzx   eax, word ptr [rsi+2]
0x14002769c  mov     word ptr [rbp+arg_8], di
0x1400276a0  sub     ax, cx
0x1400276a3  js      loc_1400277A6
0x1400276a9  movsx   edx, ax
0x1400276ac  movzx   ebx, r15w
0x1400276b0  movsx   eax, word ptr [rsi]
0x1400276b3  imul    eax, edx
0x1400276b6  movsxd  rcx, eax
0x1400276b9  add     r12, rcx
0x1400276bc  mov     ecx, edi
0x1400276be  sub     ecx, edx
0x1400276c0  lea     rdx, [rbp+arg_8]
0x1400276c4  call    ??$CastThrow@V?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@?$SafeCastHelper@FH$03@@SAXHAEAF@Z; SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(int,short &)
0x1400276c9  movzx   edi, word ptr [rbp+arg_8]
0x1400276cd  movsx   edx, word ptr [r14+8]
0x1400276d2  mov     r8d, 1
0x1400276d8  mov     ecx, edx
0x1400276da  sub     dx, [r14+4]
0x1400276df  imul    ecx, r15d
0x1400276e3  mov     [rbp+var_30], dx
0x1400276e7  sub     cx, [rsi+4]
0x1400276eb  movsx   eax, cx
0x1400276ee  sub     cx, r8w
0x1400276f2  sub     eax, r8d
0x1400276f5  cdqe
0x1400276f7  sar     rax, 3
0x1400276fb  add     r12, rax
0x1400276fe  lea     eax, [r8+6]
0x140027702  and     cx, ax
0x140027705  sub     ax, cx
0x140027708  movsx   ecx, word ptr [r14+2]
0x14002770d  mov     [rbp+var_2C], ax
0x140027711  sub     ecx, r8d
0x140027714  movsx   eax, dx
0x140027717  lea     rdx, [rbp+arg_8]
0x14002771b  sub     eax, r8d
0x14002771e  movsxd  r13, eax
0x140027721  add     r13, [r14+20h]
0x140027725  call    ??$CastThrow@V?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@?$SafeCastHelper@FH$03@@SAXHAEAF@Z; SafeCastHelper<short,int,4>::CastThrow<SafeIntExceptionHandler<SafeIntRasterizerException>>(int,short &)
0x14002772a  movzx   esi, word ptr [rbp+arg_8]
0x14002772e  mov     ecx, 0FFFF8000h
0x140027733  cmp     [r14+6], si
0x140027738  jg      short loc_14002778C
0x14002773a  mov     [rbp+var_38], r13
0x14002773e  test    bx, bx
0x140027741  jz      short loc_140027748
0x140027743  test    di, di
0x140027746  jg      short loc_14002775D
0x140027748  cmp     si, cx
0x14002774b  jz      short loc_1400277BB
0x14002774d  movsx   rax, word ptr [r14]
0x140027751  movzx   ebx, r15w
0x140027755  add     r13, rax
0x140027758  dec     si
0x14002775b  jmp     short loc_140027733
0x14002775d  lea     rcx, [rbp+var_40]; struct GrayScaleParam *
0x140027761  mov     [rbp+var_40], r12
0x140027765  call    ?fsc_CalcGrayRow@@YAXPEAUGrayScaleParam@@@Z; fsc_CalcGrayRow(GrayScaleParam *)
0x14002776a  mov     ecx, 0FFFF8000h
0x14002776f  cmp     di, cx
0x140027772  jz      short loc_1400277BB
0x140027774  mov     rax, [rbp+arg_0]
0x140027778  movsx   rax, word ptr [rax]
0x14002777c  add     r12, rax
0x14002777f  mov     eax, 0FFFFh
0x140027784  add     bx, ax
0x140027787  dec     di
0x14002778a  jmp     short loc_14002773E
0x14002778c  mov     rbx, [rsp+60h+arg_10]
0x140027794  xor     eax, eax
0x140027796  add     rsp, 60h
0x14002779a  pop     r15
0x14002779c  pop     r14
0x14002779e  pop     r13
0x1400277a0  pop     r12
0x1400277a2  pop     rdi
0x1400277a3  pop     rsi
0x1400277a4  pop     rbp
0x1400277a5  retn
0x1400277a6  neg     ax
0x1400277a9  cmp     ax, r15w
0x1400277ad  ja      short loc_1400277BB
0x1400277af  movzx   ebx, r15w
0x1400277b3  sub     bx, ax
0x1400277b6  jmp     loc_1400276CD
0x1400277bb  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
```
