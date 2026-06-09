# DispatchHelper::MarshalVariantToJsVar(tagVARIANT *,void * *,Js::ScriptContext *,DispatchHelper::VariantPropertyFlag)

- ea: `0x180023f60`
- end: `0x1800242c0`
- name: `?MarshalVariantToJsVar@DispatchHelper@@SAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@W4VariantPropertyFlag@1@@Z`
- size: `864`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800232c0`
- `0x180023c30`
- `0x180024310`
- `0x180029350`
- `0x18006817c`
- `0x180166210`
- `0x180174d60`
- `0x18019bf50`
- `0x1801e8954`
- `0x1801e8a74`
- `0x1801f4a30`
- `0x1801f5b34`
- `0x1801fc860`
- `0x1802004fc`

## callees

- `0x180023f60`
- `0x1800242d0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023fd3`
- `OLEAUT32!__imp_VariantInit` at `0x180024243`
- `OLEAUT32!__imp_VariantInit` at `0x180023fd3`
- `OLEAUT32!__imp_VariantInit` at `0x180024243`
- `OLEAUT32!__imp_VariantClear` at `0x180024064`
- `OLEAUT32!__imp_VariantClear` at `0x180024064`
- `OLEAUT32!__imp_VariantCopy` at `0x180023fe1`
- `OLEAUT32!__imp_VariantCopy` at `0x180023fe1`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180024251`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180024251`

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
        v21 = (v19 + llVal) / qword_1803B18E0[p_pvarg->decVal.scale];
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
0x180023f60  mov     rax, rsp
0x180023f63  mov     [rax+20h], r9d
0x180023f67  mov     [rax+18h], r8
0x180023f6b  mov     [rax+10h], rdx
0x180023f6f  mov     [rax+8], rcx
0x180023f73  push    rbx
0x180023f74  push    rbp
0x180023f75  push    rdi
0x180023f76  sub     rsp, 50h
0x180023f7a  mov     rbx, rcx
0x180023f7d  test    rcx, rcx
0x180023f80  jz      loc_18002420B
0x180023f86  mov     rdi, rdx
0x180023f89  test    rdx, rdx
0x180023f8c  jz      loc_18002420B
0x180023f92  mov     eax, r9d
0x180023f95  mov     ebp, r9d
0x180023f98  mov     edx, 4000h
0x180023f9d  and     eax, 1
0x180023fa0  jnz     loc_1800241F5
0x180023fa6  xor     ecx, ecx
0x180023fa8  xorps   xmm0, xmm0
0x180023fab  mov     qword ptr [rsp+68h+pvarg+10h], rcx
0x180023fb0  movzx   ecx, word ptr [rbx]
0x180023fb3  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180023fb8  test    dx, cx
0x180023fbb  jnz     loc_180024215
0x180023fc1  test    eax, eax
0x180023fc3  jnz     short loc_180023FF9
0x180023fc5  cmp     ecx, 8
0x180023fc8  jz      loc_1800240CD
0x180023fce  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180023fd3  call    cs:__imp_VariantInit
0x180023fd9  mov     rdx, rbx; pvargSrc
0x180023fdc  lea     rcx, [rsp+68h+pvarg]; pvargDest
0x180023fe1  call    cs:__imp_VariantCopy
0x180023fe7  test    eax, eax
0x180023fe9  js      loc_180024071
0x180023fef  movzx   ecx, word ptr [rsp+68h+pvarg]
0x180023ff4  lea     rbx, [rsp+68h+pvarg]
0x180023ff9  movzx   eax, cx
0x180023ffc  mov     [rsp+68h+var_20], rsi
0x180024001  cmp     eax, 11h
0x180024004  jnz     short loc_180024079
0x180024006  movzx   eax, byte ptr [rbx+8]
0x18002400a  mov     [rbx+8], eax
0x18002400d  mov     word ptr [rbx], 3; jumptable 0000000180024094 case 22
0x180024012  mov     r8, [rsp+68h+arg_10]; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x18002401a  mov     rdx, rdi; void **
0x18002401d  mov     rcx, rbx; struct tagVARIANT *
0x180024020  call    ?MarshalVariantToJsVarDerefedNoThrow@DispatchHelper@@CAJPEAUtagVARIANT@@PEAPEAXPEAVScriptContext@Js@@@Z; DispatchHelper::MarshalVariantToJsVarDerefedNoThrow(tagVARIANT *,void * *,Js::ScriptContext *)
0x180024025  mov     esi, eax
0x180024027  test    eax, eax
0x180024029  js      short loc_180024057
0x18002402b  mov     rax, [rdi]
0x18002402e  mov     rcx, rax
0x180024031  shr     rcx, 30h
0x180024035  cmp     rcx, 1
0x180024039  jz      short loc_180024057
0x18002403b  mov     rcx, 4000000000000h
0x180024045  cmp     rax, rcx
0x180024048  jnb     short loc_180024057
0x18002404a  mov     rcx, [rax+8]
0x18002404e  cmp     dword ptr [rcx], 0Bh
0x180024051  jz      loc_1800241C3
0x180024057  lea     rax, [rsp+68h+pvarg]
0x18002405c  cmp     rbx, rax
0x18002405f  jnz     short loc_18002406A
0x180024061  mov     rcx, rbx; pvarg
0x180024064  call    cs:__imp_VariantClear
0x18002406a  mov     eax, esi
0x18002406c  mov     rsi, [rsp+68h+var_20]
0x180024071  add     rsp, 50h
0x180024075  pop     rdi
0x180024076  pop     rbp
0x180024077  pop     rbx
0x180024078  retn
0x180024079  add     eax, 0FFFFFFFEh; switch 22 cases
0x18002407c  cmp     eax, 15h
0x18002407f  ja      short def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x180024081  cdqe
0x180024083  lea     rcx, __ImageBase
0x18002408a  mov     eax, ds:(jpt_180024094 - 180000000h)[rcx+rax*4]
0x180024091  add     rax, rcx
0x180024094  jmp     rax; switch jump
0x180024096  movd    xmm1, dword ptr [rbx+0Ch]; jumptable 0000000180024094 case 6
0x18002409b  xorps   xmm0, xmm0
0x18002409e  mov     eax, [rbx+8]
0x1800240a1  cvtdq2pd xmm1, xmm1
0x1800240a5  mov     word ptr [rbx], 5
0x1800240aa  cvtsi2sd xmm0, rax
0x1800240af  mulsd   xmm1, cs:__real@41f0000000000000
0x1800240b7  addsd   xmm1, xmm0
0x1800240bb  divsd   xmm1, cs:__real@40c3880000000000
0x1800240c3  movsd   qword ptr [rbx+8], xmm1
0x1800240c8  jmp     def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x1800240cd  mov     ecx, 8
0x1800240d2  jmp     loc_180023FF9
0x1800240d7  mov     rdx, [rbx+8]; jumptable 0000000180024094 case 20
0x1800240db  mov     eax, 80000000h
0x1800240e0  add     rax, rdx
0x1800240e3  mov     ecx, 0FFFFFFFFh
0x1800240e8  cmp     rax, rcx
0x1800240eb  ja      def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x1800240f1  mov     [rbx+8], edx
0x1800240f4  jmp     loc_18002400D; jumptable 0000000180024094 case 22
0x1800240f9  mov     rax, [rbx+8]; jumptable 0000000180024094 case 21
0x1800240fd  mov     ecx, 0FFFFFFFFh
0x180024102  cmp     rax, rcx
0x180024105  ja      def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x18002410b  mov     [rbx+8], eax
0x18002410e  mov     eax, [rbx+8]; jumptable 0000000180024094 cases 19,23
0x180024111  cmp     eax, 7FFFFFFFh
0x180024116  ja      short loc_180024197
0x180024118  mov     [rbx+8], eax
0x18002411b  mov     eax, 3
0x180024120  mov     [rbx], ax
0x180024123  jmp     def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x180024128  movsx   eax, word ptr [rbx+8]; jumptable 0000000180024094 case 2
0x18002412c  jmp     loc_18002400A
0x180024131  movsx   eax, byte ptr [rbx+8]; jumptable 0000000180024094 case 16
0x180024135  jmp     loc_18002400A
0x18002413a  movzx   eax, word ptr [rbx+8]; jumptable 0000000180024094 case 18
0x18002413e  jmp     loc_18002400A
0x180024143  cmp     dword ptr [rbx+0Ch], 0; jumptable 0000000180024094 case 14
0x180024147  xorps   xmm2, xmm2
0x18002414a  mov     eax, [rbx+4]
0x18002414d  xorps   xmm0, xmm0
0x180024150  jge     short loc_1800241AE
0x180024152  cvtsi2sd xmm2, qword ptr [rbx+8]
0x180024158  cvtsi2sd xmm0, rax
0x18002415d  addsd   xmm2, cs:qword_1803EE4E0
0x180024165  mulsd   xmm0, cs:qword_1803EE4E0
0x18002416d  cmp     byte ptr [rbx+3], 0
0x180024171  addsd   xmm2, xmm0
0x180024175  movzx   eax, byte ptr [rbx+2]
0x180024179  divsd   xmm2, ds:rva qword_1803B18E0[rcx+rax*8]
0x180024182  jnz     loc_18002425C
0x180024188  movsd   qword ptr [rbx+8], xmm2
0x18002418d  mov     word ptr [rbx], 5
0x180024192  jmp     def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x180024197  xorps   xmm0, xmm0
0x18002419a  cvtsi2sd xmm0, rax
0x18002419f  mov     eax, 5
0x1800241a4  movsd   qword ptr [rbx+8], xmm0
0x1800241a9  jmp     loc_180024120
0x1800241ae  cvtsi2sd xmm0, qword ptr [rbx+8]
0x1800241b4  cvtsi2sd xmm2, rax
0x1800241b9  mulsd   xmm2, cs:qword_1803EE4E0
0x1800241c1  jmp     short loc_18002416D
0x1800241c3  test    bpl, 2
0x1800241c7  jz      loc_180024057
0x1800241cd  mov     rax, [rax+18h]
0x1800241d1  mov     rdx, [rax+10h]
0x1800241d5  or      dword ptr [rdx+8], 8
0x1800241d9  jmp     loc_180024057
0x1800241de  movss   xmm0, dword ptr [rbx+8]; jumptable 0000000180024094 case 4
0x1800241e3  cvtps2pd xmm0, xmm0
0x1800241e6  mov     word ptr [rbx], 5
0x1800241eb  movsd   qword ptr [rbx+8], xmm0
0x1800241f0  jmp     def_180024094; jumptable 0000000180024094 default case, cases 3,5,7-13,15,17
0x1800241f5  test    [rbx], dx
0x1800241f8  jz      loc_180023FA6
0x1800241fe  mov     eax, 80020005h
0x180024203  add     rsp, 50h
0x180024207  pop     rdi
0x180024208  pop     rbp
0x180024209  pop     rbx
0x18002420a  retn
0x18002420b  mov     eax, 80070057h
0x180024210  jmp     loc_180024071
0x180024215  mov     edx, ecx
0x180024217  btr     edx, 0Eh
0x18002421b  cmp     edx, 2000h
0x180024221  jz      loc_180023FC1
0x180024227  cmp     edx, 8
0x18002422a  jz      loc_180023FC1
0x180024230  cmp     edx, 0Ch
0x180024233  jz      loc_180023FC1
0x180024239  cmp     edx, 2
0x18002423c  jb      short loc_18002420B
0x18002423e  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180024243  call    cs:__imp_VariantInit
0x180024249  mov     rdx, rbx; pvargSrc
0x18002424c  lea     rcx, [rsp+68h+pvarg]; pvarDest
0x180024251  call    cs:__imp_VariantCopyInd
0x180024257  jmp     loc_180023FE7
0x18002425c  xorps   xmm2, cs:__xmm@80000000000000008000000000000000
0x180024263  jmp     loc_180024188
```
