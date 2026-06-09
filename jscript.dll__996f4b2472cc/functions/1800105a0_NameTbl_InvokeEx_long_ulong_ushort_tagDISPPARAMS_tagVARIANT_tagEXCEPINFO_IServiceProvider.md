# NameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x1800105a0`
- end: `0x180010d5a`
- name: `?InvokeEx@NameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `1978`
- prototype: `__int64 __fastcall(struct CSession **this, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagDISPPARAMS *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x1800104e0`

## callees

- `0x180002ba8`
- `0x180004d40`
- `0x1800076e0`
- `0x18000d190`
- `0x18000e778`
- `0x18000eea4`
- `0x18000fd70`
- `0x1800105a0`
- `0x180011240`
- `0x18001128c`
- `0x180011a60`
- `0x180011a88`
- `0x180011dac`
- `0x1800169f0`
- `0x180016a44`
- `0x18002faa0`
- `0x18003cb80`
- `0x18005388c`
- `0x180096692`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x180010bda`
- `msvcrt!free` at `0x180010bda`
- `msvcrt!malloc` at `0x180010acd`
- `msvcrt!malloc` at `0x180010acd`
- `OLEAUT32!__imp_VariantClear` at `0x180010bcb`
- `OLEAUT32!__imp_VariantClear` at `0x180010bcb`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180010822`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180010822`

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
  HRESULT RecordedError; // ebx
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
  VAR *llVal; // rcx
  struct VAR *v33; // rax
  struct IDispatch *v34; // r15
  _WORD *v35; // r8
  VARIANTARG *v36; // r10
  VARTYPE v37; // bx
  VARIANTARG *v38; // r14
  VARIANTARG *v39; // rcx
  VARIANTARG *v40; // rbx
  struct tagDISPPARAMS *v41; // rbx
  unsigned int v42; // r9d
  int v43; // eax
  const struct _GUID *v44; // r9
  struct VVAL *v45; // [rsp+50h] [rbp-A8h] BYREF
  VARIANTARG *pvarg[2]; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-90h]
  int v48; // [rsp+70h] [rbp-88h]
  VARIANTARG v49; // [rsp+78h] [rbp-80h] BYREF
  struct CSession *v50; // [rsp+90h] [rbp-68h] BYREF
  VARIANT *pvarDest[2]; // [rsp+98h] [rbp-60h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-50h]
  const VARIANTARG *v53; // [rsp+B0h] [rbp-48h]
  __int128 v54; // [rsp+B8h] [rbp-40h] BYREF
  __int64 v55; // [rsp+C8h] [rbp-30h]

  v8 = a4;
  v45 = 0;
  v54 = 0;
  v55 = 0;
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
    v43 = NameTbl::InvokeDef((NameTbl *)this, a2, v8, a5, v11, a8);
    RecordedError = NameTbl::GetRecordedError((NameTbl *)this, v43, a7);
    (*((void (__fastcall **)(struct CSession **))*this + 2))(this);
    return (unsigned int)RecordedError;
  }
  RecordedError = (*((__int64 (__fastcall **)(struct CSession **, _QWORD, struct VVAL **, _QWORD))v13 + 53))(
                    this,
                    (unsigned int)a2,
                    &v45,
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
        LODWORD(v55) = a5->cArgs - 1;
        *(_QWORD *)&v54 = a5->rgvarg + 1;
        HIDWORD(v55) = cNamedArgs - 1;
        *((_QWORD *)&v54 + 1) = rgdispidNamedArgs + 1;
        v18 = (struct tagDISPPARAMS *)&v54;
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
      RecordedError = NameTbl::GetValCore((NameTbl *)this, v45, (struct VAR *)&v49);
      if ( RecordedError >= 0 && v11 )
        RecordedError = VAR::GetStdVar((VAR *)&v49, v11);
      goto LABEL_57;
    }
    v20 = (volatile signed __int32 *)this[3];
    _InterlockedAdd(v20, 1u);
    v50 = (struct CSession *)v20;
    *(_OWORD *)pvarDest = 0;
    v52 = 0;
    cArgs = (int)v18->cArgs;
    if ( (int)cArgs < 0 )
    {
      RecordedError = -2147024809;
    }
    else
    {
      rgvarg = v18->rgvarg;
      v53 = 0;
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
          v49 = *pvarDest[1];
          if ( (v8 & 8) != 0 )
            goto LABEL_51;
          v28 = (unsigned __int16)_mm_cvtsi128_si32(v27);
          if ( v28 == 128 )
            v28 = *(unsigned __int16 *)_mm_srli_si128(v27, 8).m128i_u16[0];
          if ( ((unsigned int)(v28 - 129) > 0xF || (v29 = 32865, !_bittest(&v29, v28 - 129))) && v28 != 9
            || (RecordedError = VAR::InvokeByDispID((VAR *)&v49, this[3], 0, 2u, &v49, (int)v15, v15, v15),
                RecordedError >= 0) )
          {
LABEL_51:
            RecordedError = NameTbl::SetValCore((NameTbl *)this, v45, (struct VAR *)&v49);
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
          v53 = v25;
          while ( 1 )
          {
            v26 = v25--;
            v53 = v25;
            if ( v26 <= rgvarg )
              break;
            --pvarDest[1];
            pvarDest[1]->vt = 0;
            RecordedError = VariantCopyInd(pvarDest[1], v25);
            v15 = 0;
            if ( RecordedError >= 0 )
            {
              RecordedError = VAR::Import((VAR *)pvarDest[1], v50);
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
    VarList::Close((VarList *)&v50);
    goto LABEL_57;
  }
  *(_OWORD *)pvarg = 0;
  v47 = 0;
  RecordedError = NameTbl::GetValCore((NameTbl *)this, v45, (struct VAR *)&v49);
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
  llVal = (VAR *)&v49;
  if ( v49.vt == 16396 )
    llVal = (VAR *)v49.llVal;
  v33 = VAR::PvarCutHeap(llVal);
  v34 = (struct IDispatch *)*((_QWORD *)v33 + 1);
  if ( !v34 || !(unsigned int)VAR::IsIDispatch(v33) )
    return 2147614723LL;
  v37 = (_WORD)v36 + 9;
  if ( (_WORD)v36 + 9 == *v35 || (_WORD)v36 + 134 == *v35 )
  {
    ((void (__fastcall *)(struct IDispatch *))v34->lpVtbl->AddRef)(v34);
    RecordedError = IDispatchInvoke(this[3], v34, 0, v44, a3, v8, v18, v11, a7, 0);
    ((void (__fastcall *)(struct IDispatch *))v34->lpVtbl->Release)(v34);
    return (unsigned int)RecordedError;
  }
  if ( a5 != v18 )
  {
    v38 = v36;
    v41 = a5;
LABEL_82:
    a6 = v41;
    ((void (__fastcall *)(struct IDispatch *))v34->lpVtbl->AddRef)(v34);
    RecordedError = IDispatchExInvokeEx(this[3], (struct IDispatchEx *)v34, 0, v42, v8, v41, v11, a7, a8);
    ((void (__fastcall *)(struct IDispatch *))v34->lpVtbl->Release)(v34);
    if ( a5 != a6 )
    {
      VariantClear(pvarg[0]);
      free(v38);
    }
    goto LABEL_57;
  }
  LODWORD(v47) = a5->cArgs + 1;
  HIDWORD(v47) = a5->cNamedArgs + 1;
  LODWORD(a6) = 24 * v47;
  v48 = 4 * HIDWORD(v47);
  v38 = (VARIANTARG *)malloc(4 * HIDWORD(v47) + 24 * (int)v47);
  if ( v38 )
  {
    pvarg[0] = v38;
    v39 = (VARIANTARG *)((char *)v38 + (int)a6);
    pvarg[1] = v39;
    if ( a5->cArgs )
    {
      memcpy_0(&v38[1], a5->rgvarg, (int)a6 - 24LL);
      v39 = pvarg[1];
    }
    if ( a5->cNamedArgs )
      memcpy_0(&v39->decVal.Hi32, a5->rgdispidNamedArgs, v48 - 4LL);
    pvarg[0]->vt = v37;
    v40 = pvarg[0];
    v40->llVal = (*((__int64 (__fastcall **)(struct CSession **))*this + 36))(this);
    (*(void (__fastcall **)(LONGLONG))(*pvarg[0]->pllVal + 8))(pvarg[0]->llVal);
    *(_DWORD *)pvarg[1] = -613;
    v41 = (struct tagDISPPARAMS *)pvarg;
    goto LABEL_82;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800105a0  mov     r11, rsp
0x1800105a3  mov     [r11+8], rbx
0x1800105a7  mov     [r11+10h], rsi
0x1800105ab  mov     [r11+18h], r8d
0x1800105af  push    rdi
0x1800105b0  push    r12
0x1800105b2  push    r13
0x1800105b4  push    r14
0x1800105b6  push    r15
0x1800105b8  sub     rsp, 0D0h
0x1800105bf  movzx   r12d, r9w
0x1800105c3  mov     r14d, edx
0x1800105c6  mov     rsi, rcx
0x1800105c9  xor     ebx, ebx
0x1800105cb  mov     [rsp+0F8h+var_A8], rbx
0x1800105d0  xorps   xmm0, xmm0
0x1800105d3  xor     eax, eax
0x1800105d5  movups  xmmword ptr [r11-40h], xmm0
0x1800105da  mov     [r11-30h], rax
0x1800105de  mov     r13, [rsp+0F8h+arg_28]
0x1800105e6  test    r13, r13
0x1800105e9  jz      short loc_1800105F0
0x1800105eb  mov     [r13+0], bx
0x1800105f0  mov     rax, [rsp+0F8h+arg_30]
0x1800105f8  test    rax, rax
0x1800105fb  jnz     loc_1800109B2
0x180010601  mov     rcx, rsi; this
0x180010604  call    ?FBaseThread@NameTbl@@IEAAHXZ; NameTbl::FBaseThread(void)
0x180010609  test    eax, eax
0x18001060b  jz      loc_180010C49
0x180010611  mov     rdi, [rsp+0F8h+arg_20]
0x180010619  test    rdi, rdi
0x18001061c  jz      short loc_180010657
0x18001061e  mov     eax, [rdi+14h]
0x180010621  cmp     [rdi+10h], eax
0x180010624  jb      short loc_180010657
0x180010626  mov     ebx, r12d
0x180010629  test    r12d, 0FFFFBFF0h
0x180010630  setz    cl
0x180010633  mov     eax, 400Fh
0x180010638  test    ax, r12w
0x18001063c  setnz   al
0x18001063f  test    al, cl
0x180010641  jz      short loc_180010657
0x180010643  test    ebx, 0FFFFFFFCh
0x180010649  setnz   cl
0x18001064c  test    r12b, 3
0x180010650  setnz   al
0x180010653  test    al, cl
0x180010655  jz      short loc_180010661
0x180010657  mov     eax, 80070057h
0x18001065c  jmp     loc_180010954
0x180010661  movzx   r15d, r12w
0x180010665  and     r15w, 0Ch
0x18001066a  jz      short loc_180010674
0x18001066c  test    ebx, 0FFFFFFF3h
0x180010672  jnz     short loc_180010657
0x180010674  mov     ecx, 4000h
0x180010679  movzx   eax, r12w
0x18001067d  and     ax, cx
0x180010680  mov     word ptr [rsp+0F8h+arg_28], ax
0x180010688  jz      short loc_180010692
0x18001068a  test    ebx, 0FFFFBFFFh
0x180010690  jnz     short loc_180010657
0x180010692  mov     rax, [rsi]
0x180010695  mov     rcx, rsi
0x180010698  test    r14d, r14d
0x18001069b  jle     loc_180010BEB
0x1800106a1  xor     r9d, r9d
0x1800106a4  lea     r8, [rsp+0F8h+var_A8]
0x1800106a9  mov     edx, r14d
0x1800106ac  mov     rax, [rax+1A8h]
0x1800106b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106b8  mov     ebx, eax
0x1800106ba  xor     r10d, r10d
0x1800106bd  test    eax, eax
0x1800106bf  js      loc_180010943
0x1800106c5  mov     r8d, [rdi+14h]
0x1800106c9  test    r8d, r8d
0x1800106cc  jz      short loc_1800106DF
0x1800106ce  mov     r9, [rdi+8]
0x1800106d2  cmp     dword ptr [r9], 0FFFFFD9Bh
0x1800106d9  jz      loc_180010C53
0x1800106df  mov     r14, rdi
0x1800106e2  movzx   ecx, r12w
0x1800106e6  mov     edx, 1
0x1800106eb  and     cx, dx
0x1800106ee  movzx   eax, r15w
0x1800106f2  test    r15w, r15w
0x1800106f6  jz      short loc_18001070F
0x1800106f8  cmp     [r14+14h], r10d
0x1800106fc  jz      loc_180010C3F
0x180010702  mov     rax, [r14+8]
0x180010706  cmp     dword ptr [rax], 0FFFFFFFDh
0x180010709  jnz     loc_180010C3F
0x18001070f  movzx   eax, r12w
0x180010713  and     ax, 2
0x180010717  jnz     loc_180010A09
0x18001071d  test    cx, cx
0x180010720  jnz     loc_1800109FE
0x180010726  test    r15w, r15w
0x18001072a  jz      short loc_180010736
0x18001072c  cmp     [r14+10h], edx
0x180010730  jnz     loc_180010A13
0x180010736  cmp     word ptr [rsp+0F8h+arg_28], r10w
0x18001073f  jnz     loc_180010A13
0x180010745  test    ax, ax
0x180010748  jnz     loc_1800109C5
0x18001074e  mov     rcx, [rsi+18h]; this
0x180010752  lock add [rcx], edx
0x180010755  mov     [rsp+0F8h+var_68], rcx
0x18001075d  xorps   xmm0, xmm0
0x180010760  movdqu  xmmword ptr [rsp+0F8h+pvarDest], xmm0
0x180010769  mov     [rsp+0F8h+var_50], r10
0x180010771  movsxd  rdi, dword ptr [r14+10h]
0x180010775  test    edi, edi
0x180010777  js      loc_180010910
0x18001077d  mov     r15, [r14]
0x180010780  mov     [rsp+0F8h+var_48], r10
0x180010788  test    edi, edi
0x18001078a  jz      loc_180010917
0x180010790  call    ?GetVarStack@CSession@@QEAAPEAVVarStack@@XZ; CSession::GetVarStack(void)
0x180010795  mov     r14, rax
0x180010798  test    rax, rax
0x18001079b  jz      loc_18001091F
0x1800107a1  lea     r8, [rsp+0F8h+pvarDest+8]; struct VAR **
0x1800107a9  mov     edx, edi; int
0x1800107ab  mov     rcx, rax; this
0x1800107ae  call    ?SetMasterSp@VarStack@@QEAAJJPEAPEAVVAR@@@Z; VarStack::SetMasterSp(long,VAR * *)
0x1800107b3  mov     ebx, eax
0x1800107b5  xor     r10d, r10d
0x1800107b8  test    eax, eax
0x1800107ba  js      loc_180010929
0x1800107c0  mov     [rsp+0F8h+pvarDest], r14
0x1800107c8  mov     ebx, r10d
0x1800107cb  test    ebx, ebx
0x1800107cd  js      loc_180010936
0x1800107d3  test    edi, edi
0x1800107d5  jz      loc_18001085E
0x1800107db  lea     rcx, [rdi+rdi*2]
0x1800107df  lea     rdi, [r15+rcx*8]
0x1800107e3  mov     [rsp+0F8h+var_48], rdi
0x1800107eb  mov     rax, rdi
0x1800107ee  sub     rdi, 18h
0x1800107f2  mov     [rsp+0F8h+var_48], rdi
0x1800107fa  cmp     rax, r15
0x1800107fd  jbe     short loc_18001085B
0x1800107ff  mov     rcx, [rsp+0F8h+pvarDest+8]
0x180010807  sub     rcx, 18h
0x18001080b  mov     [rsp+0F8h+pvarDest+8], rcx
0x180010813  mov     [rcx], r10w
0x180010817  mov     rdx, rdi; pvargSrc
0x18001081a  mov     rcx, [rsp+0F8h+pvarDest+8]; pvarDest
0x180010822  call    cs:__imp_VariantCopyInd
0x180010829  nop     dword ptr [rax+rax+00h]
0x18001082e  mov     ebx, eax
0x180010830  xor     r10d, r10d
0x180010833  test    eax, eax
0x180010835  js      short loc_180010851
0x180010837  mov     rdx, [rsp+0F8h+var_68]; struct CSession *
0x18001083f  mov     rcx, [rsp+0F8h+pvarDest+8]; this
0x180010847  call    ?Import@VAR@@QEAAJPEAVCSession@@@Z; VAR::Import(CSession *)
0x18001084c  mov     ebx, eax
0x18001084e  xor     r10d, r10d
0x180010851  test    ebx, ebx
0x180010853  js      loc_180010936
0x180010859  jmp     short loc_1800107EB
0x18001085b  mov     ebx, r10d
0x18001085e  test    ebx, ebx
0x180010860  js      loc_180010936
0x180010866  mov     rax, [rsp+0F8h+pvarDest+8]
0x18001086e  movups  xmm1, xmmword ptr [rax]
0x180010871  movups  xmmword ptr [rsp+0F8h+var_80], xmm1
0x180010876  movsd   xmm0, qword ptr [rax+10h]
0x18001087b  movsd   qword ptr [rsp+0F8h+var_80+10h], xmm0
0x180010884  test    r12b, 8
0x180010888  jnz     short loc_1800108FA
0x18001088a  movd    eax, xmm1
0x18001088e  movzx   ecx, ax
0x180010891  cmp     ecx, 80h
0x180010897  jnz     short loc_1800108A6
0x180010899  psrldq  xmm1, 8
0x18001089e  movq    rax, xmm1
0x1800108a3  movzx   ecx, word ptr [rax]
0x1800108a6  lea     eax, [rcx-81h]
0x1800108ac  cmp     eax, 0Fh
0x1800108af  ja      short loc_1800108BB
0x1800108b1  mov     edx, 8061h
0x1800108b6  bt      edx, eax
0x1800108b9  jb      short loc_1800108C4
0x1800108bb  mov     ebx, 9
0x1800108c0  cmp     ecx, ebx
0x1800108c2  jnz     short loc_1800108FA
0x1800108c4  mov     [rsp+0F8h+var_C0], r10; struct VAR *
0x1800108c9  mov     [rsp+0F8h+var_C8], r10; struct VAR *
0x1800108ce  mov     dword ptr [rsp+0F8h+var_D0], r10d; int
0x1800108d3  lea     rax, [rsp+0F8h+var_80]
0x1800108d8  mov     [rsp+0F8h+var_D8], rax; pvarg
0x1800108dd  mov     r9d, 2; unsigned int
0x1800108e3  xor     r8d, r8d; int
0x1800108e6  mov     rdx, [rsi+18h]; struct CSession *
0x1800108ea  lea     rcx, [rsp+0F8h+var_80]; this
0x1800108ef  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x1800108f4  mov     ebx, eax
0x1800108f6  test    eax, eax
0x1800108f8  js      short loc_180010936
0x1800108fa  lea     r8, [rsp+0F8h+var_80]; struct VAR *
0x1800108ff  mov     rdx, [rsp+0F8h+var_A8]; struct VVAL *
0x180010904  mov     rcx, rsi; this
0x180010907  call    ?SetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::SetValCore(VVAL *,VAR *)
0x18001090c  mov     ebx, eax
0x18001090e  jmp     short loc_180010936
0x180010910  mov     ebx, 80070057h
0x180010915  jmp     short loc_180010936
0x180010917  mov     ebx, r10d
0x18001091a  jmp     loc_1800107D3
0x18001091f  mov     ebx, 80004005h
0x180010924  jmp     loc_18001085E
0x180010929  mov     [rsp+0F8h+pvarDest+8], r10
0x180010931  jmp     loc_1800107CB
0x180010936  lea     rcx, [rsp+0F8h+var_68]; this
0x18001093e  call    ?Close@VarList@@QEAAXXZ; VarList::Close(void)
0x180010943  mov     dword ptr [rsp+0F8h+arg_28], ebx
0x18001094a  cmp     ebx, 86664004h
0x180010950  jz      short loc_180010972
0x180010952  mov     eax, ebx
0x180010954  lea     r11, [rsp+0F8h+var_28]
0x18001095c  mov     rbx, [r11+30h]
0x180010960  mov     rsi, [r11+38h]
0x180010964  mov     rsp, r11
0x180010967  pop     r15
0x180010969  pop     r14
0x18001096b  pop     r13
0x18001096d  pop     r12
0x18001096f  pop     rdi
0x180010970  retn
0x180010972  mov     rax, [rsi+18h]
0x180010976  mov     rbx, [rax+440h]
0x18001097d  test    rbx, rbx
0x180010980  jnz     short loc_180010989
0x180010982  lea     rbx, [rax+448h]
0x180010989  mov     r8, [rsp+0F8h+arg_30]; struct tagEXCEPINFO *
0x180010991  lea     rdx, [rsp+0F8h+arg_28]; int *
0x180010999  mov     rcx, rbx; this
0x18001099c  call    ?GetError@ScriptException@@QEAAXPEAJPEAUtagEXCEPINFO@@@Z; ScriptException::GetError(long *,tagEXCEPINFO *)
0x1800109a1  mov     rcx, rbx; this
0x1800109a4  call    ?Free@RuntimeScriptException@@QEAAXXZ; RuntimeScriptException::Free(void)
0x1800109a9  mov     ebx, dword ptr [rsp+0F8h+arg_28]
0x1800109b0  jmp     short loc_180010952
0x1800109b2  xor     edx, edx; Val
0x1800109b4  lea     r8d, [rdx+40h]; Size
0x1800109b8  mov     rcx, rax; void *
0x1800109bb  call    memset_0
0x1800109c0  jmp     loc_180010601
0x1800109c5  lea     r8, [rsp+0F8h+var_80]; struct VAR *
0x1800109ca  mov     rdx, [rsp+0F8h+var_A8]; struct VVAL *
0x1800109cf  mov     rcx, rsi; this
0x1800109d2  call    ?GetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::GetValCore(VVAL *,VAR *)
0x1800109d7  mov     ebx, eax
0x1800109d9  test    eax, eax
0x1800109db  js      loc_180010943
0x1800109e1  test    r13, r13
0x1800109e4  jz      loc_180010943
0x1800109ea  mov     rdx, r13; struct tagVARIANT *
0x1800109ed  lea     rcx, [rsp+0F8h+var_80]; this
0x1800109f2  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x1800109f7  mov     ebx, eax
0x1800109f9  jmp     loc_180010943
0x1800109fe  test    ax, ax
0x180010a01  jnz     loc_180010726
0x180010a07  jmp     short loc_180010A13
0x180010a09  cmp     [r14+10h], r10d
0x180010a0d  jz      loc_18001071D
0x180010a13  xorps   xmm0, xmm0
0x180010a16  xor     eax, eax
0x180010a18  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x180010a1d  mov     [rsp+0F8h+var_90], rax
0x180010a22  lea     r8, [rsp+0F8h+var_80]; struct VAR *
0x180010a27  mov     rdx, [rsp+0F8h+var_A8]; struct VVAL *
0x180010a2c  mov     rcx, rsi; this
0x180010a2f  call    ?GetValCore@NameTbl@@QEAAJPEAUVVAL@@PEAVVAR@@@Z; NameTbl::GetValCore(VVAL *,VAR *)
0x180010a34  mov     ebx, eax
0x180010a36  xor     r10d, r10d
0x180010a39  test    eax, eax
0x180010a3b  js      loc_180010943
0x180010a41  lea     rcx, [rsp+0F8h+var_80]
0x180010a46  mov     eax, 400Ch
0x180010a4b  cmp     word ptr [rsp+0F8h+var_80], ax
0x180010a50  cmovz   rcx, qword ptr [rsp+0F8h+var_80+8]; this
0x180010a59  call    ?PvarCutHeap@VAR@@QEAAPEAV1@XZ; VAR::PvarCutHeap(void)
0x180010a5e  mov     r8, rax
0x180010a61  mov     r15, [rax+8]
0x180010a65  test    r15, r15
0x180010a68  jz      loc_180010CAF
0x180010a6e  mov     rcx, rax; this
0x180010a71  call    ?IsIDispatch@VAR@@QEAAHXZ; VAR::IsIDispatch(void)
0x180010a76  test    eax, eax
0x180010a78  jz      loc_180010CAF
0x180010a7e  lea     ebx, [r10+9]
0x180010a82  cmp     bx, [r8]
  ... truncated ...
```
