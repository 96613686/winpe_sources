# NameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180013350`
- end: `0x180013b08`
- name: `?InvokeEx@NameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `1976`
- prototype: `__int64 __usercall@<rax>(NameTbl *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, unsigned __int16@<r9w>, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180013290`

## callees

- `0x180001d90`
- `0x18000ff30`
- `0x18001154c`
- `0x180011c70`
- `0x180012ae4`
- `0x180013350`
- `0x180013f20`
- `0x180013f64`
- `0x18001471c`
- `0x180014740`
- `0x180014fac`
- `0x1800199d0`
- `0x180019a24`
- `0x180031430`
- `0x180032b50`
- `0x18003390c`
- `0x180052ac8`
- `0x180094282`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x18001398e`
- `msvcrt!free` at `0x18001398e`
- `msvcrt!malloc` at `0x18001388d`
- `msvcrt!malloc` at `0x18001388d`
- `OLEAUT32!__imp_VariantClear` at `0x180013985`
- `OLEAUT32!__imp_VariantClear` at `0x180013985`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800135cb`
- `OLEAUT32!__imp_VariantCopyInd` at `0x1800135cb`

## pseudocode

```c
__int64 __fastcall NameTbl::InvokeEx(
        struct CSession **this,
        int a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct tagDISPPARAMS *a5,
        struct tagDISPPARAMS *a6,
        struct tagEXCEPINFO *a7,
        struct IServiceProvider *a8)
{
  unsigned int v8; // r12d
  struct tagVARIANT *v11; // r13
  struct CSession *v13; // rax
  int RecordedError; // ebx
  struct VAR *v15; // r10
  UINT cNamedArgs; // r8d
  DISPID *rgdispidNamedArgs; // r9
  struct tagDISPPARAMS *v18; // r14
  __int16 v19; // cx
  volatile signed __int32 *v20; // rcx
  __int64 cArgs; // rdi
  VARIANTARG *rgvarg; // r15
  VarStack *VarStack; // rax
  VARIANT *v24; // r14
  const VARIANTARG *v25; // rdi
  const VARIANTARG *v26; // rax
  __m128i v27; // xmm1
  int v28; // ecx
  int v29; // edx
  struct CSession *v30; // rax
  ScriptException *v31; // rbx
  VAR *v32; // r8
  struct IDispatch *v33; // r15
  _WORD *v34; // r8
  VARIANTARG *v35; // r10
  VARIANTARG *v36; // r14
  VARIANTARG *v37; // rcx
  VARIANTARG *v38; // rbx
  struct tagDISPPARAMS *v39; // rbx
  unsigned int v40; // r9d
  int v41; // eax
  const struct _GUID *v42; // r9
  struct VVAL *v43; // [rsp+50h] [rbp-C8h] BYREF
  VARIANTARG *pvarg[2]; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-B0h]
  int v46; // [rsp+70h] [rbp-A8h]
  struct CSession *v47; // [rsp+78h] [rbp-A0h] BYREF
  VARIANT *pvarDest[2]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v49; // [rsp+90h] [rbp-88h]
  const VARIANTARG *v50; // [rsp+98h] [rbp-80h]
  __int128 v51; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-68h]
  VARIANT v53; // [rsp+B8h] [rbp-60h] BYREF
  __int16 v54; // [rsp+D0h] [rbp-48h] BYREF
  VAR *v55; // [rsp+D8h] [rbp-40h]

  v8 = a4;
  v43 = 0;
  v51 = 0;
  v52 = 0;
  v11 = (struct tagVARIANT *)a6;
  if ( a6 )
    LOWORD(a6->rgvarg) = 0;
  if ( a7 )
    memset_0(a7, 0, sizeof(struct tagEXCEPINFO));
  if ( !(unsigned int)NameTbl::FBaseThread((NameTbl *)this) )
    return 2147549183LL;
  if ( !a5
    || a5->cArgs < a5->cNamedArgs
    || (v8 & 0xFFFFBFF0) != 0
    || (v8 & 0x400F) == 0
    || (v8 & 0xFFFFFFFC) != 0 && (v8 & 3) != 0
    || (v8 & 0xC) != 0 && (v8 & 0xFFFFFFF3) != 0 )
  {
    return 2147942487LL;
  }
  LOWORD(a6) = v8 & 0x4000;
  if ( (v8 & 0x4000) != 0 && (v8 & 0xFFFFBFFF) != 0 )
    return 2147942487LL;
  v13 = *this;
  if ( a2 <= 0 )
  {
    (*((void (__fastcall **)(struct CSession **))v13 + 1))(this);
    v41 = NameTbl::InvokeDef((NameTbl *)this, a2, v8, a5, v11, a8);
    RecordedError = NameTbl::GetRecordedError((NameTbl *)this, v41, a7);
    (*((void (__fastcall **)(struct CSession **))*this + 2))(this);
    return (unsigned int)RecordedError;
  }
  RecordedError = (*((__int64 (__fastcall **)(struct CSession **, _QWORD, struct VVAL **, _QWORD))v13 + 53))(
                    this,
                    (unsigned int)a2,
                    &v43,
                    0);
  v15 = 0;
  if ( RecordedError < 0 )
    goto LABEL_57;
  cNamedArgs = a5->cNamedArgs;
  if ( cNamedArgs )
  {
    rgdispidNamedArgs = a5->rgdispidNamedArgs;
    if ( *rgdispidNamedArgs == -613 )
    {
      v19 = v8 & 1;
      if ( (v8 & 1) != 0 )
      {
        LODWORD(v52) = a5->cArgs - 1;
        *(_QWORD *)&v51 = a5->rgvarg + 1;
        HIDWORD(v52) = cNamedArgs - 1;
        *((_QWORD *)&v51 + 1) = rgdispidNamedArgs + 1;
        v18 = (struct tagDISPPARAMS *)&v51;
        goto LABEL_20;
      }
      return 2147942487LL;
    }
  }
  v18 = a5;
  v19 = v8 & 1;
LABEL_20:
  if ( (v8 & 0xC) != 0 && (!v18->cNamedArgs || *v18->rgdispidNamedArgs != -3) )
    return 2147614735LL;
  if ( ((v8 & 2) == 0 || !v18->cArgs) && (!v19 || (v8 & 2) != 0) && ((v8 & 0xC) == 0 || v18->cArgs == 1) && !(_WORD)a6 )
  {
    if ( (v8 & 2) != 0 )
    {
      RecordedError = NameTbl::GetValCore((NameTbl *)this, v43, (struct VAR *)&v53);
      if ( RecordedError >= 0 && v11 )
        RecordedError = VAR::GetStdVar((VAR *)&v53, v11);
      goto LABEL_57;
    }
    v20 = (volatile signed __int32 *)this[3];
    _InterlockedAdd(v20, 1u);
    v47 = (struct CSession *)v20;
    *(_OWORD *)pvarDest = 0;
    v49 = 0;
    cArgs = (int)v18->cArgs;
    if ( (int)cArgs < 0 )
    {
      RecordedError = -2147024809;
    }
    else
    {
      rgvarg = v18->rgvarg;
      v50 = 0;
      if ( !(_DWORD)cArgs )
      {
        RecordedError = 0;
        goto LABEL_35;
      }
      VarStack = CSession::GetVarStack((CSession *)v20);
      v24 = (VARIANT *)VarStack;
      if ( !VarStack )
      {
        RecordedError = -2147467259;
LABEL_43:
        if ( RecordedError >= 0 )
        {
          v27 = *(__m128i *)pvarDest[1];
          v53 = *pvarDest[1];
          if ( (v8 & 8) != 0 )
            goto LABEL_51;
          v28 = (unsigned __int16)_mm_cvtsi128_si32(v27);
          if ( v28 == 128 )
            v28 = *(unsigned __int16 *)_mm_srli_si128(v27, 8).m128i_u16[0];
          if ( ((unsigned int)(v28 - 129) > 0xF || (v29 = 32865, !_bittest(&v29, v28 - 129))) && v28 != 9
            || (RecordedError = VAR::InvokeByDispID((VAR *)&v53, this[3], 0, 2u, (struct VAR *)&v53, (int)v15, v15, v15),
                RecordedError >= 0) )
          {
LABEL_51:
            RecordedError = NameTbl::SetValCore((NameTbl *)this, v43, (struct VAR *)&v53);
          }
        }
        goto LABEL_56;
      }
      RecordedError = VarStack::SetMasterSp(VarStack, cArgs, (struct VAR **)&pvarDest[1]);
      v15 = 0;
      if ( RecordedError < 0 )
      {
        pvarDest[1] = 0;
      }
      else
      {
        pvarDest[0] = v24;
        RecordedError = 0;
      }
      if ( RecordedError >= 0 )
      {
LABEL_35:
        if ( (_DWORD)cArgs )
        {
          v25 = &rgvarg[cArgs];
          v50 = v25;
          while ( 1 )
          {
            v26 = v25--;
            v50 = v25;
            if ( v26 <= rgvarg )
              break;
            --pvarDest[1];
            pvarDest[1]->vt = 0;
            RecordedError = VariantCopyInd(pvarDest[1], v25);
            v15 = 0;
            if ( RecordedError >= 0 )
            {
              RecordedError = VAR::Import((VAR *)pvarDest[1], v47);
              v15 = 0;
            }
            if ( RecordedError < 0 )
              goto LABEL_56;
          }
          RecordedError = 0;
        }
        goto LABEL_43;
      }
    }
LABEL_56:
    VarList::Close((VarList *)&v47);
    goto LABEL_57;
  }
  *(_OWORD *)pvarg = 0;
  v45 = 0;
  RecordedError = NameTbl::GetValCore((NameTbl *)this, v43, (struct VAR *)&v54);
  if ( RecordedError < 0 )
  {
LABEL_57:
    LODWORD(a6) = RecordedError;
    if ( RecordedError == -2040119292 )
    {
      v30 = this[3];
      v31 = (ScriptException *)*((_QWORD *)v30 + 136);
      if ( !v31 )
        v31 = (struct CSession *)((char *)v30 + 1096);
      ScriptException::GetError(v31, (int *)&a6, a7);
      RuntimeScriptException::Free(v31);
      return (unsigned int)a6;
    }
    return (unsigned int)RecordedError;
  }
  v32 = (VAR *)&v54;
  if ( v54 == 16396 )
    v32 = v55;
  if ( *(_WORD *)v32 == 128 )
    v32 = (VAR *)*((_QWORD *)v32 + 1);
  v33 = (struct IDispatch *)*((_QWORD *)v32 + 1);
  if ( !v33 || !(unsigned int)VAR::IsIDispatch(v32) )
    return 2147614723LL;
  if ( *v34 == 9 || *v34 == 134 )
  {
    ((void (__fastcall *)(struct IDispatch *))v33->lpVtbl->AddRef)(v33);
    RecordedError = IDispatchInvoke((struct ThreadGlobals **)this[3], v33, 0, v42, a3, v8, v18, v11, a7, 0);
    ((void (__fastcall *)(struct IDispatch *))v33->lpVtbl->Release)(v33);
    return (unsigned int)RecordedError;
  }
  if ( a5 != v18 )
  {
    v36 = v35;
    v39 = a5;
LABEL_84:
    a6 = v39;
    ((void (__fastcall *)(struct IDispatch *))v33->lpVtbl->AddRef)(v33);
    RecordedError = IDispatchExInvokeEx(this[3], (struct IDispatchEx *)v33, 0, v40, v8, v39, v11, a7, a8);
    ((void (__fastcall *)(struct IDispatch *))v33->lpVtbl->Release)(v33);
    if ( a5 != a6 )
    {
      VariantClear(pvarg[0]);
      free(v36);
    }
    goto LABEL_57;
  }
  LODWORD(v45) = a5->cArgs + 1;
  HIDWORD(v45) = a5->cNamedArgs + 1;
  LODWORD(a6) = 24 * v45;
  v46 = 4 * HIDWORD(v45);
  v36 = (VARIANTARG *)malloc(4 * HIDWORD(v45) + 24 * (int)v45);
  if ( v36 )
  {
    pvarg[0] = v36;
    v37 = (VARIANTARG *)((char *)v36 + (int)a6);
    pvarg[1] = v37;
    if ( a5->cArgs )
    {
      memcpy_0(&v36[1], a5->rgvarg, (int)a6 - 24LL);
      v37 = pvarg[1];
    }
    if ( a5->cNamedArgs )
      memcpy_0(&v37->decVal.Hi32, a5->rgdispidNamedArgs, v46 - 4LL);
    pvarg[0]->vt = 9;
    v38 = pvarg[0];
    v38->llVal = (*((__int64 (__fastcall **)(struct CSession **))*this + 36))(this);
    (*(void (__fastcall **)(LONGLONG))(*pvarg[0]->pllVal + 8))(pvarg[0]->llVal);
    *(_DWORD *)pvarg[1] = -613;
    v39 = (struct tagDISPPARAMS *)pvarg;
    goto LABEL_84;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180013350  mov     r11, rsp
0x180013353  mov     [r11+8], rbx
0x180013357  mov     [r11+10h], rsi
0x18001335b  mov     [r11+18h], r8d
0x18001335f  push    rdi
0x180013360  push    r12
0x180013362  push    r13
0x180013364  push    r14
0x180013366  push    r15
0x180013368  sub     rsp, 0F0h
0x18001336f  movzx   r12d, r9w
0x180013373  mov     r14d, edx
0x180013376  mov     rsi, rcx
0x180013379  xor     ebx, ebx
0x18001337b  mov     [rsp+118h+var_C8], rbx
0x180013380  xorps   xmm0, xmm0
0x180013383  xor     eax, eax
0x180013385  movups  xmmword ptr [r11-78h], xmm0
0x18001338a  mov     [r11-68h], rax
0x18001338e  mov     r13, [rsp+118h+arg_28]
0x180013396  test    r13, r13
0x180013399  jz      short loc_1800133A0
0x18001339b  mov     [r13+0], bx
0x1800133a0  mov     rax, [rsp+118h+arg_30]
0x1800133a8  test    rax, rax
0x1800133ab  jnz     loc_18001375B
0x1800133b1  mov     rcx, rsi; this
0x1800133b4  call    ?FBaseThread@NameTbl@@IEAAHXZ; NameTbl::FBaseThread(void)
0x1800133b9  test    eax, eax
0x1800133bb  jz      loc_1800139F7
0x1800133c1  mov     rdi, [rsp+118h+arg_20]
0x1800133c9  test    rdi, rdi
0x1800133cc  jz      short loc_180013407
0x1800133ce  mov     eax, [rdi+14h]
0x1800133d1  cmp     [rdi+10h], eax
0x1800133d4  jb      short loc_180013407
0x1800133d6  mov     ebx, r12d
0x1800133d9  test    r12d, 0FFFFBFF0h
0x1800133e0  setz    cl
0x1800133e3  mov     eax, 400Fh
0x1800133e8  test    ax, r12w
0x1800133ec  setnz   al
0x1800133ef  test    al, cl
0x1800133f1  jz      short loc_180013407
0x1800133f3  test    ebx, 0FFFFFFFCh
0x1800133f9  setnz   cl
0x1800133fc  test    r12b, 3
0x180013400  setnz   al
0x180013403  test    al, cl
0x180013405  jz      short loc_180013411
0x180013407  mov     eax, 80070057h
0x18001340c  jmp     loc_1800136FE
0x180013411  movzx   r15d, r12w
0x180013415  and     r15w, 0Ch
0x18001341a  jz      short loc_180013424
0x18001341c  test    ebx, 0FFFFFFF3h
0x180013422  jnz     short loc_180013407
0x180013424  mov     ecx, 4000h
0x180013429  movzx   eax, r12w
0x18001342d  and     ax, cx
0x180013430  mov     word ptr [rsp+118h+arg_28], ax
0x180013438  jz      short loc_180013442
0x18001343a  test    ebx, 0FFFFBFFFh
0x180013440  jnz     short loc_180013407
0x180013442  mov     rax, [rsi]
0x180013445  mov     rcx, rsi
0x180013448  test    r14d, r14d
0x18001344b  jle     loc_180013999
0x180013451  xor     r9d, r9d
0x180013454  lea     r8, [rsp+118h+var_C8]
0x180013459  mov     edx, r14d
0x18001345c  mov     rax, [rax+1A8h]
0x180013463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013468  mov     ebx, eax
0x18001346a  xor     r10d, r10d
0x18001346d  test    eax, eax
0x18001346f  js      loc_1800136ED
0x180013475  mov     r8d, [rdi+14h]
0x180013479  test    r8d, r8d
0x18001347c  jz      short loc_18001348F
0x18001347e  mov     r9, [rdi+8]
0x180013482  cmp     dword ptr [r9], 0FFFFFD9Bh
0x180013489  jz      loc_180013A01
0x18001348f  mov     r14, rdi
0x180013492  movzx   ecx, r12w
0x180013496  mov     edx, 1
0x18001349b  and     cx, dx
0x18001349e  movzx   eax, r15w
0x1800134a2  test    r15w, r15w
0x1800134a6  jz      short loc_1800134BF
0x1800134a8  cmp     [r14+14h], r10d
0x1800134ac  jz      loc_1800139ED
0x1800134b2  mov     rax, [r14+8]
0x1800134b6  cmp     dword ptr [rax], 0FFFFFFFDh
0x1800134b9  jnz     loc_1800139ED
0x1800134bf  movzx   eax, r12w
0x1800134c3  and     ax, 2
0x1800134c7  jnz     loc_1800137B8
0x1800134cd  test    cx, cx
0x1800134d0  jnz     loc_1800137AD
0x1800134d6  test    r15w, r15w
0x1800134da  jz      short loc_1800134E6
0x1800134dc  cmp     [r14+10h], edx
0x1800134e0  jnz     loc_1800137C2
0x1800134e6  cmp     word ptr [rsp+118h+arg_28], r10w
0x1800134ef  jnz     loc_1800137C2
0x1800134f5  test    ax, ax
0x1800134f8  jnz     loc_18001376E
0x1800134fe  mov     rcx, [rsi+18h]; this
0x180013502  lock add [rcx], edx
0x180013505  mov     [rsp+118h+var_A0], rcx
0x18001350a  xorps   xmm0, xmm0
0x18001350d  movdqu  xmmword ptr [rsp+118h+pvarDest], xmm0
0x180013516  mov     [rsp+118h+var_88], r10
0x18001351e  movsxd  rdi, dword ptr [r14+10h]
0x180013522  test    edi, edi
0x180013524  js      loc_1800136BD
0x18001352a  mov     r15, [r14]
0x18001352d  mov     [rsp+118h+var_80], r10
0x180013535  test    edi, edi
0x180013537  jz      loc_1800136C4
0x18001353d  call    ?GetVarStack@CSession@@QEAAPEAVVarStack@@XZ; CSession::GetVarStack(void)
0x180013542  mov     r14, rax
0x180013545  test    rax, rax
0x180013548  jz      loc_1800136CC
0x18001354e  lea     r8, [rsp+118h+pvarDest+8]; struct VAR **
0x180013556  mov     edx, edi; int
0x180013558  mov     rcx, rax; this
0x18001355b  call    ?SetMasterSp@VarStack@@QEAAJJPEAPEAVVAR@@@Z; VarStack::SetMasterSp(long,VAR * *)
0x180013560  mov     ebx, eax
0x180013562  xor     r10d, r10d
0x180013565  test    eax, eax
0x180013567  js      loc_1800136D6
0x18001356d  mov     [rsp+118h+pvarDest], r14
0x180013575  mov     ebx, r10d
0x180013578  test    ebx, ebx
0x18001357a  js      loc_1800136E3
0x180013580  test    edi, edi
0x180013582  jz      short loc_1800135FE
0x180013584  lea     rcx, [rdi+rdi*2]
0x180013588  lea     rdi, [r15+rcx*8]
0x18001358c  mov     [rsp+118h+var_80], rdi
0x180013594  mov     rax, rdi
0x180013597  sub     rdi, 18h
0x18001359b  mov     [rsp+118h+var_80], rdi
0x1800135a3  cmp     rax, r15
0x1800135a6  jbe     short loc_1800135FB
0x1800135a8  mov     rcx, [rsp+118h+pvarDest+8]
0x1800135b0  sub     rcx, 18h
0x1800135b4  mov     [rsp+118h+pvarDest+8], rcx
0x1800135bc  mov     [rcx], r10w
0x1800135c0  mov     rdx, rdi; pvargSrc
0x1800135c3  mov     rcx, [rsp+118h+pvarDest+8]; pvarDest
0x1800135cb  call    cs:__imp_VariantCopyInd
0x1800135d1  mov     ebx, eax
0x1800135d3  xor     r10d, r10d
0x1800135d6  test    eax, eax
0x1800135d8  js      short loc_1800135F1
0x1800135da  mov     rdx, [rsp+118h+var_A0]; struct CSession *
0x1800135df  mov     rcx, [rsp+118h+pvarDest+8]; this
0x1800135e7  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x1800135ec  mov     ebx, eax
0x1800135ee  xor     r10d, r10d
0x1800135f1  test    ebx, ebx
0x1800135f3  js      loc_1800136E3
0x1800135f9  jmp     short loc_180013594
0x1800135fb  mov     ebx, r10d
0x1800135fe  test    ebx, ebx
0x180013600  js      loc_1800136E3
0x180013606  mov     rax, [rsp+118h+pvarDest+8]
0x18001360e  movups  xmm1, xmmword ptr [rax]
0x180013611  movups  [rsp+118h+var_60], xmm1
0x180013619  movsd   xmm0, qword ptr [rax+10h]
0x18001361e  movsd   [rsp+118h+var_50], xmm0
0x180013627  test    r12b, 8
0x18001362b  jnz     short loc_1800136A4
0x18001362d  movd    eax, xmm1
0x180013631  movzx   ecx, ax
0x180013634  mov     eax, 80h
0x180013639  cmp     ecx, eax
0x18001363b  jnz     short loc_18001364A
0x18001363d  psrldq  xmm1, 8
0x180013642  movq    rax, xmm1
0x180013647  movzx   ecx, word ptr [rax]
0x18001364a  lea     eax, [rcx-81h]
0x180013650  cmp     eax, 0Fh
0x180013653  ja      short loc_18001365F
0x180013655  mov     edx, 8061h
0x18001365a  bt      edx, eax
0x18001365d  jb      short loc_180013668
0x18001365f  mov     ebx, 9
0x180013664  cmp     ecx, ebx
0x180013666  jnz     short loc_1800136A4
0x180013668  mov     [rsp+118h+var_E0], r10; struct VAR *
0x18001366d  mov     [rsp+118h+var_E8], r10; struct VAR *
0x180013672  mov     dword ptr [rsp+118h+var_F0], r10d; int
0x180013677  lea     rax, [rsp+118h+var_60]
0x18001367f  mov     [rsp+118h+var_F8], rax; struct VAR *
0x180013684  mov     r9d, 2; unsigned int
0x18001368a  xor     r8d, r8d; int
0x18001368d  mov     rdx, [rsi+18h]; struct CSession *
0x180013691  lea     rcx, [rsp+118h+var_60]; this
0x180013699  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18001369e  mov     ebx, eax
0x1800136a0  test    eax, eax
0x1800136a2  js      short loc_1800136E3
0x1800136a4  lea     r8, [rsp+118h+var_60]; struct VAR *
0x1800136ac  mov     rdx, [rsp+118h+var_C8]; struct VVAL *
0x1800136b1  mov     rcx, rsi; this
0x1800136b4  call    ?SetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::SetValCore(VVAL *,VAR *)
0x1800136b9  mov     ebx, eax
0x1800136bb  jmp     short loc_1800136E3
0x1800136bd  mov     ebx, 80070057h
0x1800136c2  jmp     short loc_1800136E3
0x1800136c4  mov     ebx, r10d
0x1800136c7  jmp     loc_180013580
0x1800136cc  mov     ebx, 80004005h
0x1800136d1  jmp     loc_1800135FE
0x1800136d6  mov     [rsp+118h+pvarDest+8], r10
0x1800136de  jmp     loc_180013578
0x1800136e3  lea     rcx, [rsp+118h+var_A0]; this
0x1800136e8  call    ?Close@VarList@@QEAAXXZ; VarList::Close(void)
0x1800136ed  mov     dword ptr [rsp+118h+arg_28], ebx
0x1800136f4  cmp     ebx, 86664004h
0x1800136fa  jz      short loc_18001371B
0x1800136fc  mov     eax, ebx
0x1800136fe  lea     r11, [rsp+118h+var_28]
0x180013706  mov     rbx, [r11+30h]
0x18001370a  mov     rsi, [r11+38h]
0x18001370e  mov     rsp, r11
0x180013711  pop     r15
0x180013713  pop     r14
0x180013715  pop     r13
0x180013717  pop     r12
0x180013719  pop     rdi
0x18001371a  retn
0x18001371b  mov     rax, [rsi+18h]
0x18001371f  mov     rbx, [rax+440h]
0x180013726  test    rbx, rbx
0x180013729  jnz     short loc_180013732
0x18001372b  lea     rbx, [rax+448h]
0x180013732  mov     r8, [rsp+118h+arg_30]; struct tagEXCEPINFO *
0x18001373a  lea     rdx, [rsp+118h+arg_28]; int *
0x180013742  mov     rcx, rbx; this
0x180013745  call    ?GetError@ScriptException@@QEAAXPEAJPEAUtagEXCEPINFO@@@Z; ScriptException::GetError(long *,tagEXCEPINFO *)
0x18001374a  mov     rcx, rbx; this
0x18001374d  call    ?Free@RuntimeScriptException@@QEAAXXZ; RuntimeScriptException::Free(void)
0x180013752  mov     ebx, dword ptr [rsp+118h+arg_28]
0x180013759  jmp     short loc_1800136FC
0x18001375b  xor     edx, edx; Val
0x18001375d  lea     r8d, [rdx+40h]; Size
0x180013761  mov     rcx, rax; void *
0x180013764  call    memset_0
0x180013769  jmp     loc_1800133B1
0x18001376e  lea     r8, [rsp+118h+var_60]; struct VAR *
0x180013776  mov     rdx, [rsp+118h+var_C8]; struct VVAL *
0x18001377b  mov     rcx, rsi; this
0x18001377e  call    ?GetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::GetValCore(VVAL *,VAR *)
0x180013783  mov     ebx, eax
0x180013785  test    eax, eax
0x180013787  js      loc_1800136ED
0x18001378d  test    r13, r13
0x180013790  jz      loc_1800136ED
0x180013796  mov     rdx, r13; struct tagVARIANT *
0x180013799  lea     rcx, [rsp+118h+var_60]; this
0x1800137a1  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x1800137a6  mov     ebx, eax
0x1800137a8  jmp     loc_1800136ED
0x1800137ad  test    ax, ax
0x1800137b0  jnz     loc_1800134D6
0x1800137b6  jmp     short loc_1800137C2
0x1800137b8  cmp     [r14+10h], r10d
0x1800137bc  jz      loc_1800134CD
0x1800137c2  xorps   xmm0, xmm0
0x1800137c5  xor     eax, eax
0x1800137c7  movups  xmmword ptr [rsp+118h+pvarg], xmm0
0x1800137cc  mov     [rsp+118h+var_B0], rax
0x1800137d1  lea     r8, [rsp+118h+var_48]; struct VAR *
0x1800137d9  mov     rdx, [rsp+118h+var_C8]; struct VVAL *
0x1800137de  mov     rcx, rsi; this
0x1800137e1  call    ?GetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::GetValCore(VVAL *,VAR *)
0x1800137e6  mov     ebx, eax
0x1800137e8  xor     r10d, r10d
0x1800137eb  test    eax, eax
0x1800137ed  js      loc_1800136ED
0x1800137f3  lea     r8, [rsp+118h+var_48]
0x1800137fb  mov     eax, 400Ch
0x180013800  cmp     [rsp+118h+var_48], ax
0x180013808  cmovz   r8, [rsp+118h+var_40]
0x180013811  mov     eax, 80h
0x180013816  cmp     [r8], ax
0x18001381a  jnz     short loc_180013820
0x18001381c  mov     r8, [r8+8]
0x180013820  mov     r15, [r8+8]
0x180013824  test    r15, r15
0x180013827  jz      loc_180013A5D
0x18001382d  mov     rcx, r8; this
0x180013830  call    ?IsIDispatch@VAR@@QEAAHXZ; VAR::IsIDispatch(void)
0x180013835  test    eax, eax
0x180013837  jz      loc_180013A5D
  ... truncated ...
```
