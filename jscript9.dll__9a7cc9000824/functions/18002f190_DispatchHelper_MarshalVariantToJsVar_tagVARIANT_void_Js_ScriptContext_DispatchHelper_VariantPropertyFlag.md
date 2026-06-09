# DispatchHelper::MarshalVariantToJsVar(tagVARIANT *,void * *,Js::ScriptContext *,DispatchHelper::VariantPropertyFlag)

- ea: `0x18002f190`
- end: `0x18002f514`
- name: `?MarshalVariantToJsVar@DispatchHelper@@SAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@W4VariantPropertyFlag@1@@Z`
- size: `900`
- prototype: `HRESULT __fastcall(VARIANTARG *, void **, struct Js::ScriptContext *, char)`
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180020ddc`
- `0x18002e49c`
- `0x18002ee60`
- `0x18002f560`
- `0x1800dfd74`
- `0x180161fd0`
- `0x180174fe0`
- `0x18019dfa0`
- `0x1801ebd88`
- `0x1801ebea8`
- `0x1801f7f70`
- `0x1801f90d4`
- `0x1801ffab0`
- `0x180203844`

## callees

- `0x18002f190`
- `0x18002f520`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002f203`
- `OLEAUT32!__imp_VariantInit` at `0x18002f48b`
- `OLEAUT32!__imp_VariantInit` at `0x18002f203`
- `OLEAUT32!__imp_VariantInit` at `0x18002f48b`
- `OLEAUT32!__imp_VariantClear` at `0x18002f2a0`
- `OLEAUT32!__imp_VariantClear` at `0x18002f2a0`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f217`
- `OLEAUT32!__imp_VariantCopy` at `0x18002f217`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002f49f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18002f49f`

## pseudocode

```c
HRESULT __fastcall DispatchHelper::MarshalVariantToJsVar(
        VARIANTARG *a1,
        void **a2,
        struct Js::ScriptContext *a3,
        char a4)
{
  VARIANTARG *p_pvarg; // rbx
  int vt; // ecx
  HRESULT result; // eax
  LONG iVal; // eax
  int v10; // esi
  _QWORD *v11; // rax
  int lVal; // eax
  double Hi; // xmm1_8
  LONGLONG v14; // rdx
  unsigned __int64 ullVal; // rax
  int v16; // eax
  __int16 v17; // ax
  int Hi32; // eax
  double v19; // xmm2_8
  double llVal; // xmm0_8
  double v21; // xmm2_8
  DOUBLE v22; // xmm0_8
  DOUBLE fltVal; // xmm0_8
  unsigned int v24; // edx
  VARIANTARG pvarg; // [rsp+28h] [rbp-40h] BYREF

  p_pvarg = a1;
  if ( !a1 || !a2 )
    return -2147024809;
  if ( (a4 & 1) != 0 && (a1->vt & 0x4000) != 0 )
    return -2147352571;
  vt = a1->vt;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( (vt & 0x4000) != 0 )
  {
    v24 = vt & 0xFFFFBFFF;
    if ( (vt & 0xFFFFBFFF) != 0x2000 && v24 != 8 && v24 != 12 )
    {
      if ( v24 >= 2 )
      {
        VariantInit(&pvarg);
        result = VariantCopyInd(&pvarg, p_pvarg);
        goto LABEL_8;
      }
      return -2147024809;
    }
  }
  if ( (a4 & 1) != 0 )
    goto LABEL_10;
  if ( vt == 8 )
  {
    LOWORD(vt) = 8;
    goto LABEL_10;
  }
  VariantInit(&pvarg);
  result = VariantCopy(&pvarg, p_pvarg);
LABEL_8:
  if ( result < 0 )
    return result;
  LOWORD(vt) = pvarg.vt;
  p_pvarg = &pvarg;
LABEL_10:
  if ( (unsigned __int16)vt != 17 )
  {
    switch ( (__int16)vt )
    {
      case 2:
        iVal = p_pvarg->iVal;
        goto LABEL_12;
      case 4:
        fltVal = p_pvarg->fltVal;
        p_pvarg->vt = 5;
        p_pvarg->dblVal = fltVal;
        goto LABEL_14;
      case 6:
        lVal = p_pvarg->lVal;
        Hi = (double)p_pvarg->cyVal.Hi;
        p_pvarg->vt = 5;
        p_pvarg->dblVal = (Hi * 4294967296.0 + (double)lVal) / 10000.0;
        goto LABEL_14;
      case 14:
        Hi32 = p_pvarg->decVal.Hi32;
        if ( p_pvarg->cyVal.Hi >= 0 )
        {
          llVal = (double)(int)p_pvarg->llVal;
          v19 = (double)Hi32 * 1.844674407370955e19;
        }
        else
        {
          v19 = (double)(int)p_pvarg->llVal + 1.844674407370955e19;
          llVal = (double)Hi32 * 1.844674407370955e19;
        }
        v21 = (v19 + llVal) / *(double *)&qword_1803B7800[p_pvarg->decVal.scale];
        if ( p_pvarg->decVal.sign )
          *(_QWORD *)&v21 ^= _xmm;
        p_pvarg->dblVal = v21;
        p_pvarg->vt = 5;
        goto LABEL_14;
      case 16:
        iVal = p_pvarg->cVal;
        goto LABEL_12;
      case 18:
        iVal = p_pvarg->uiVal;
        goto LABEL_12;
      case 19:
      case 23:
        goto LABEL_29;
      case 20:
        v14 = p_pvarg->llVal;
        if ( (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF )
          goto LABEL_14;
        p_pvarg->lVal = v14;
        goto LABEL_13;
      case 21:
        ullVal = p_pvarg->ullVal;
        if ( ullVal > 0xFFFFFFFF )
          goto LABEL_14;
        p_pvarg->lVal = ullVal;
LABEL_29:
        v16 = p_pvarg->lVal;
        if ( (unsigned int)v16 > 0x7FFFFFFF )
        {
          v22 = (double)v16;
          v17 = 5;
          p_pvarg->dblVal = v22;
        }
        else
        {
          p_pvarg->lVal = v16;
          v17 = 3;
        }
        p_pvarg->vt = v17;
        goto LABEL_14;
      case 22:
        goto LABEL_13;
      default:
        goto LABEL_14;
    }
  }
  iVal = p_pvarg->bVal;
LABEL_12:
  p_pvarg->lVal = iVal;
LABEL_13:
  p_pvarg->vt = 3;
LABEL_14:
  v10 = DispatchHelper::MarshalVariantToJsVarDerefedNoThrow(p_pvarg, a2, a3);
  if ( v10 >= 0 )
  {
    v11 = *a2;
    if ( (unsigned __int64)*a2 >> 48 != 1
      && (unsigned __int64)v11 < 0x4000000000000LL
      && *(_DWORD *)v11[1] == 11
      && (a4 & 2) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)(v11[3] + 16LL) + 8LL) |= 8u;
    }
  }
  if ( p_pvarg == &pvarg )
    VariantClear(p_pvarg);
  return v10;
}

```

## disassembly

```asm
0x18002f190  mov     rax, rsp
0x18002f193  mov     [rax+20h], r9d
0x18002f197  mov     [rax+18h], r8
0x18002f19b  mov     [rax+10h], rdx
0x18002f19f  mov     [rax+8], rcx
0x18002f1a3  push    rbx
0x18002f1a4  push    rbp
0x18002f1a5  push    rdi
0x18002f1a6  sub     rsp, 50h
0x18002f1aa  mov     rbx, rcx
0x18002f1ad  test    rcx, rcx
0x18002f1b0  jz      loc_18002F453
0x18002f1b6  mov     rdi, rdx
0x18002f1b9  test    rdx, rdx
0x18002f1bc  jz      loc_18002F453
0x18002f1c2  mov     eax, r9d
0x18002f1c5  mov     ebp, r9d
0x18002f1c8  mov     edx, 4000h
0x18002f1cd  and     eax, 1
0x18002f1d0  jnz     loc_18002F43C
0x18002f1d6  xor     ecx, ecx
0x18002f1d8  xorps   xmm0, xmm0
0x18002f1db  mov     qword ptr [rsp+68h+pvarg+10h], rcx
0x18002f1e0  movzx   ecx, word ptr [rbx]
0x18002f1e3  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18002f1e8  test    dx, cx
0x18002f1eb  jnz     loc_18002F45D
0x18002f1f1  test    eax, eax
0x18002f1f3  jnz     short loc_18002F235
0x18002f1f5  cmp     ecx, 8
0x18002f1f8  jz      loc_18002F314
0x18002f1fe  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002f203  call    cs:__imp_VariantInit
0x18002f20a  nop     dword ptr [rax+rax+00h]
0x18002f20f  mov     rdx, rbx; pvargSrc
0x18002f212  lea     rcx, [rsp+68h+pvarg]; pvargDest
0x18002f217  call    cs:__imp_VariantCopy
0x18002f21e  nop     dword ptr [rax+rax+00h]
0x18002f223  test    eax, eax
0x18002f225  js      loc_18002F2B3
0x18002f22b  movzx   ecx, word ptr [rsp+68h+pvarg]
0x18002f230  lea     rbx, [rsp+68h+pvarg]
0x18002f235  movzx   eax, cx
0x18002f238  mov     [rsp+68h+var_20], rsi
0x18002f23d  cmp     eax, 11h
0x18002f240  jnz     short loc_18002F2BC
0x18002f242  movzx   eax, byte ptr [rbx+8]
0x18002f246  mov     [rbx+8], eax
0x18002f249  mov     word ptr [rbx], 3; jumptable 000000018002F2D7 case 22
0x18002f24e  mov     r8, [rsp+68h+arg_10]; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f256  mov     rdx, rdi; void **
0x18002f259  mov     rcx, rbx; struct tagVARIANT *
0x18002f25c  call    ?MarshalVariantToJsVarDerefedNoThrow@DispatchHelper@@CAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@@Z; DispatchHelper::MarshalVariantToJsVarDerefedNoThrow(tagVARIANT *,void * *,Js::ScriptContext *)
0x18002f261  mov     esi, eax
0x18002f263  test    eax, eax
0x18002f265  js      short loc_18002F293
0x18002f267  mov     rax, [rdi]
0x18002f26a  mov     rcx, rax
0x18002f26d  shr     rcx, 30h
0x18002f271  cmp     rcx, 1
0x18002f275  jz      short loc_18002F293
0x18002f277  mov     rcx, 4000000000000h
0x18002f281  cmp     rax, rcx
0x18002f284  jnb     short loc_18002F293
0x18002f286  mov     rcx, [rax+8]
0x18002f28a  cmp     dword ptr [rcx], 0Bh
0x18002f28d  jz      loc_18002F40A
0x18002f293  lea     rax, [rsp+68h+pvarg]
0x18002f298  cmp     rbx, rax
0x18002f29b  jnz     short loc_18002F2AC
0x18002f29d  mov     rcx, rbx; pvarg
0x18002f2a0  call    cs:__imp_VariantClear
0x18002f2a7  nop     dword ptr [rax+rax+00h]
0x18002f2ac  mov     eax, esi
0x18002f2ae  mov     rsi, [rsp+68h+var_20]
0x18002f2b3  add     rsp, 50h
0x18002f2b7  pop     rdi
0x18002f2b8  pop     rbp
0x18002f2b9  pop     rbx
0x18002f2ba  retn
0x18002f2bc  add     eax, 0FFFFFFFEh; switch 22 cases
0x18002f2bf  cmp     eax, 15h
0x18002f2c2  ja      short def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f2c4  cdqe
0x18002f2c6  lea     rcx, __ImageBase
0x18002f2cd  mov     eax, ds:(jpt_18002F2D7 - 180000000h)[rcx+rax*4]
0x18002f2d4  add     rax, rcx
0x18002f2d7  jmp     rax; switch jump
0x18002f2dd  movd    xmm1, dword ptr [rbx+0Ch]; jumptable 000000018002F2D7 case 6
0x18002f2e2  xorps   xmm0, xmm0
0x18002f2e5  mov     eax, [rbx+8]
0x18002f2e8  cvtdq2pd xmm1, xmm1
0x18002f2ec  mov     word ptr [rbx], 5
0x18002f2f1  cvtsi2sd xmm0, rax
0x18002f2f6  mulsd   xmm1, cs:__real@41f0000000000000
0x18002f2fe  addsd   xmm1, xmm0
0x18002f302  divsd   xmm1, cs:__real@40c3880000000000
0x18002f30a  movsd   qword ptr [rbx+8], xmm1
0x18002f30f  jmp     def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f314  mov     ecx, 8
0x18002f319  jmp     loc_18002F235
0x18002f31e  mov     rdx, [rbx+8]; jumptable 000000018002F2D7 case 20
0x18002f322  mov     eax, 80000000h
0x18002f327  add     rax, rdx
0x18002f32a  mov     ecx, 0FFFFFFFFh
0x18002f32f  cmp     rax, rcx
0x18002f332  ja      def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f338  mov     [rbx+8], edx
0x18002f33b  jmp     loc_18002F249; jumptable 000000018002F2D7 case 22
0x18002f340  mov     rax, [rbx+8]; jumptable 000000018002F2D7 case 21
0x18002f344  mov     ecx, 0FFFFFFFFh
0x18002f349  cmp     rax, rcx
0x18002f34c  ja      def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f352  mov     [rbx+8], eax
0x18002f355  mov     eax, [rbx+8]; jumptable 000000018002F2D7 cases 19,23
0x18002f358  cmp     eax, 7FFFFFFFh
0x18002f35d  ja      short loc_18002F3DE
0x18002f35f  mov     [rbx+8], eax
0x18002f362  mov     eax, 3
0x18002f367  mov     [rbx], ax
0x18002f36a  jmp     def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f36f  movsx   eax, word ptr [rbx+8]; jumptable 000000018002F2D7 case 2
0x18002f373  jmp     loc_18002F246
0x18002f378  movsx   eax, byte ptr [rbx+8]; jumptable 000000018002F2D7 case 16
0x18002f37c  jmp     loc_18002F246
0x18002f381  movzx   eax, word ptr [rbx+8]; jumptable 000000018002F2D7 case 18
0x18002f385  jmp     loc_18002F246
0x18002f38a  cmp     dword ptr [rbx+0Ch], 0; jumptable 000000018002F2D7 case 14
0x18002f38e  xorps   xmm2, xmm2
0x18002f391  mov     eax, [rbx+4]
0x18002f394  xorps   xmm0, xmm0
0x18002f397  jge     short loc_18002F3F5
0x18002f399  cvtsi2sd xmm2, qword ptr [rbx+8]
0x18002f39f  cvtsi2sd xmm0, rax
0x18002f3a4  addsd   xmm2, cs:qword_1803F44A0
0x18002f3ac  mulsd   xmm0, cs:qword_1803F44A0
0x18002f3b4  cmp     byte ptr [rbx+3], 0
0x18002f3b8  addsd   xmm2, xmm0
0x18002f3bc  movzx   eax, byte ptr [rbx+2]
0x18002f3c0  divsd   xmm2, ds:rva qword_1803B7800[rcx+rax*8]
0x18002f3c9  jnz     loc_18002F4B0
0x18002f3cf  movsd   qword ptr [rbx+8], xmm2
0x18002f3d4  mov     word ptr [rbx], 5
0x18002f3d9  jmp     def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f3de  xorps   xmm0, xmm0
0x18002f3e1  cvtsi2sd xmm0, rax
0x18002f3e6  mov     eax, 5
0x18002f3eb  movsd   qword ptr [rbx+8], xmm0
0x18002f3f0  jmp     loc_18002F367
0x18002f3f5  cvtsi2sd xmm0, qword ptr [rbx+8]
0x18002f3fb  cvtsi2sd xmm2, rax
0x18002f400  mulsd   xmm2, cs:qword_1803F44A0
0x18002f408  jmp     short loc_18002F3B4
0x18002f40a  test    bpl, 2
0x18002f40e  jz      loc_18002F293
0x18002f414  mov     rax, [rax+18h]
0x18002f418  mov     rdx, [rax+10h]
0x18002f41c  or      dword ptr [rdx+8], 8
0x18002f420  jmp     loc_18002F293
0x18002f425  movss   xmm0, dword ptr [rbx+8]; jumptable 000000018002F2D7 case 4
0x18002f42a  cvtps2pd xmm0, xmm0
0x18002f42d  mov     word ptr [rbx], 5
0x18002f432  movsd   qword ptr [rbx+8], xmm0
0x18002f437  jmp     def_18002F2D7; jumptable 000000018002F2D7 default case, cases 3,5,7-13,15,17
0x18002f43c  test    [rbx], dx
0x18002f43f  jz      loc_18002F1D6
0x18002f445  mov     eax, 80020005h
0x18002f44a  add     rsp, 50h
0x18002f44e  pop     rdi
0x18002f44f  pop     rbp
0x18002f450  pop     rbx
0x18002f451  retn
0x18002f453  mov     eax, 80070057h
0x18002f458  jmp     loc_18002F2B3
0x18002f45d  mov     edx, ecx
0x18002f45f  btr     edx, 0Eh
0x18002f463  cmp     edx, 2000h
0x18002f469  jz      loc_18002F1F1
0x18002f46f  cmp     edx, 8
0x18002f472  jz      loc_18002F1F1
0x18002f478  cmp     edx, 0Ch
0x18002f47b  jz      loc_18002F1F1
0x18002f481  cmp     edx, 2
0x18002f484  jb      short loc_18002F453
0x18002f486  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002f48b  call    cs:__imp_VariantInit
0x18002f492  nop     dword ptr [rax+rax+00h]
0x18002f497  mov     rdx, rbx; pvargSrc
0x18002f49a  lea     rcx, [rsp+68h+pvarg]; pvarDest
0x18002f49f  call    cs:__imp_VariantCopyInd
0x18002f4a6  nop     dword ptr [rax+rax+00h]
0x18002f4ab  jmp     loc_18002F223
0x18002f4b0  xorps   xmm2, cs:__xmm@80000000000000008000000000000000
0x18002f4b7  jmp     loc_18002F3CF
```
