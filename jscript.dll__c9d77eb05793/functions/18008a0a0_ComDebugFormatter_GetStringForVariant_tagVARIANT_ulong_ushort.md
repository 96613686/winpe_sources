# ComDebugFormatter::GetStringForVariant(tagVARIANT *,ulong,ushort * *)

- ea: `0x18008a0a0`
- end: `0x18008a4e4`
- name: `?GetStringForVariant@ComDebugFormatter@@UEAAJPEAUtagVARIANT@@KPEAPEAG@Z`
- size: `1092`
- prototype: `__int64 __fastcall(ComDebugFormatter *__hidden this, struct tagVARIANT *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005a80`
- `0x18003390c`
- `0x180039580`
- `0x18003c260`
- `0x18005e0ec`
- `0x18006f1dc`
- `0x180089e28`
- `0x18008a0a0`
- `0x18008a4ec`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18008a45d`
- `msvcrt!_ultow_s` at `0x18008a45d`
- `msvcrt!_ltow` at `0x18008a489`
- `msvcrt!_ltow` at `0x18008a489`
- `OLEAUT32!__imp_VariantClear` at `0x18008a27e`
- `OLEAUT32!__imp_VariantClear` at `0x18008a3db`
- `OLEAUT32!__imp_VariantClear` at `0x18008a4b2`
- `OLEAUT32!__imp_VariantClear` at `0x18008a27e`
- `OLEAUT32!__imp_VariantClear` at `0x18008a3db`
- `OLEAUT32!__imp_VariantClear` at `0x18008a4b2`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008a12a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008a12a`

## pseudocode

```c
HRESULT __fastcall ComDebugFormatter::GetStringForVariant(
        ComDebugFormatter *this,
        struct tagVARIANT *a2,
        int a3,
        unsigned __int16 **a4)
{
  VARIANT *p_pvarDest; // rbx
  HRESULT result; // eax
  int StdVar; // edi
  wchar_t *bstrVal; // rsi
  unsigned int vt; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  int (__fastcall ***llVal)(_QWORD, GUID *, DateObj **); // rbx
  int HexLiteral; // eax
  double fltVal; // xmm1_8
  int lVal; // ecx
  int String; // eax
  RegExpObj *v23; // rcx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int Lo; // ecx
  unsigned __int16 *v30; // rax
  int v31; // ecx
  VARIANT pvarDest; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  RegExpObj *v34; // [rsp+40h] [rbp-C0h] BYREF
  DateObj *v35; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v36[24]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[24]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[72]; // [rsp+80h] [rbp-80h] BYREF

  p_pvarDest = a2;
  if ( !a4 )
    return -2147467261;
  *a4 = 0;
  if ( !a2 )
    return -2147024809;
  if ( a3 != 16 && a3 != 10 )
    return -2147467263;
  StdVar = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( (a2->vt & 0x4000) != 0 )
  {
    result = VariantCopyInd(&pvarDest, a2);
    StdVar = result;
    if ( result < 0 )
      return result;
    p_pvarDest = &pvarDest;
  }
  bstrVal = (wchar_t *)&::String;
  while ( 1 )
  {
    memset_0(Buffer, 0, 0x82u);
    vt = p_pvarDest->vt;
    if ( vt > 0xB )
    {
      v17 = vt - 13;
      if ( !v17 )
        goto LABEL_24;
      v24 = v17 - 3;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( !v27 )
            {
LABEL_65:
              Lo = p_pvarDest->cyVal.Lo;
              goto LABEL_69;
            }
            v28 = v27 - 3;
            if ( v28 )
            {
              if ( v28 != 1 )
              {
LABEL_64:
                *a4 = 0;
                goto LABEL_79;
              }
              goto LABEL_65;
            }
LABEL_66:
            lVal = p_pvarDest->lVal;
LABEL_72:
            if ( a3 != 16 )
            {
              _ltow(lVal, Buffer, 10);
              goto LABEL_75;
            }
LABEL_73:
            HexLiteral = GetHexLiteral(p_pvarDest, a4);
LABEL_36:
            StdVar = HexLiteral;
            goto LABEL_79;
          }
          Lo = p_pvarDest->uiVal;
        }
        else
        {
          Lo = p_pvarDest->bVal;
        }
LABEL_69:
        if ( a3 != 16 )
        {
          _ultow_s(Lo, Buffer, 0x41u, 10);
          goto LABEL_75;
        }
        goto LABEL_73;
      }
      lVal = p_pvarDest->cVal;
      goto LABEL_72;
    }
    if ( vt == 11 )
    {
      bstrVal = L"false";
      if ( p_pvarDest->iVal )
        bstrVal = L"true";
      goto LABEL_76;
    }
    if ( !p_pvarDest->vt )
    {
      bstrVal = L"undefined";
LABEL_76:
      v30 = _SysAllocString(bstrVal);
      v31 = StdVar;
      *a4 = v30;
      if ( !v30 )
        v31 = -2147024882;
      StdVar = v31;
      goto LABEL_79;
    }
    v11 = vt - 1;
    if ( !v11 )
      goto LABEL_48;
    v12 = v11 - 1;
    if ( !v12 )
    {
      lVal = p_pvarDest->iVal;
      goto LABEL_72;
    }
    v13 = v12 - 1;
    if ( !v13 )
      goto LABEL_66;
    v14 = v13 - 1;
    if ( !v14 )
    {
      fltVal = p_pvarDest->fltVal;
LABEL_39:
      if ( (~HIDWORD(fltVal) & 0x7FF00000) != 0 )
      {
        if ( !FDblToStr(fltVal, Buffer, 65) )
        {
          StdVar = -2147024882;
          goto LABEL_79;
        }
LABEL_75:
        bstrVal = Buffer;
      }
      else if ( (unsigned int)FNan(fltVal) )
      {
        bstrVal = L"NaN";
      }
      else
      {
        bstrVal = L"-Infinity";
        if ( fltVal >= 0.0 )
          bstrVal = (wchar_t *)L"Infinity";
      }
      goto LABEL_76;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      fltVal = p_pvarDest->dblVal;
      goto LABEL_39;
    }
    v16 = v15 - 3;
    if ( !v16 )
    {
      if ( p_pvarDest->llVal )
        bstrVal = p_pvarDest->bstrVal;
      HexLiteral = GetStringLiteral(bstrVal, a4);
      goto LABEL_36;
    }
    if ( v16 != 1 )
      goto LABEL_64;
LABEL_24:
    llVal = (int (__fastcall ***)(_QWORD, GUID *, DateObj **))p_pvarDest->llVal;
    if ( !llVal )
    {
LABEL_48:
      bstrVal = L"null";
      goto LABEL_76;
    }
    v35 = 0;
    if ( (**llVal)(llVal, &IID_IJsDateObj, &v35) >= 0 )
      break;
    v34 = 0;
    if ( (**llVal)(llVal, &IID_IJsRegExpObj, &v34) >= 0 )
    {
      String = RegExpObj::GetString(v34, (struct VAR *)v36);
      v23 = v34;
      goto LABEL_55;
    }
    v33 = 0;
    if ( (**llVal)(llVal, &IID_INameTbl, (DateObj **)&v33) < 0 )
      goto LABEL_76;
    StdVar = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v33 + 328LL))(v33, v37);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( StdVar < 0 )
      goto LABEL_79;
    VariantClear(&pvarDest);
    StdVar = VAR::GetStdVar((VAR *)v37, &pvarDest);
    if ( StdVar < 0 )
      goto LABEL_79;
    if ( pvarDest.vt == 9 || pvarDest.vt == 13 )
      goto LABEL_76;
    p_pvarDest = &pvarDest;
  }
  String = DateObj::GetString(v35, (struct VAR *)v36, 0, 0);
  v23 = v35;
LABEL_55:
  StdVar = String;
  (*(void (__fastcall **)(RegExpObj *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( StdVar >= 0 )
  {
    VariantClear(&pvarDest);
    StdVar = VAR::GetStdVar((VAR *)v36, &pvarDest);
    if ( StdVar >= 0 )
    {
      *a4 = pvarDest.bstrVal;
      pvarDest.vt = 0;
    }
  }
LABEL_79:
  VariantClear(&pvarDest);
  if ( StdVar >= 0 )
    return 0;
  return StdVar;
}

```

## disassembly

```asm
0x18008a0a0  mov     [rsp-8+arg_0], rbx
0x18008a0a5  push    rbp
0x18008a0a6  push    rsi
0x18008a0a7  push    rdi
0x18008a0a8  push    r14
0x18008a0aa  push    r15
0x18008a0ac  lea     rbp, [rsp-20h]
0x18008a0b1  sub     rsp, 120h
0x18008a0b8  mov     rax, cs:__security_cookie
0x18008a0bf  xor     rax, rsp
0x18008a0c2  mov     [rbp+40h+var_30], rax
0x18008a0c6  mov     r14, r9
0x18008a0c9  mov     r15d, r8d
0x18008a0cc  mov     rbx, rdx
0x18008a0cf  test    r9, r9
0x18008a0d2  jnz     short loc_18008A0DE
0x18008a0d4  mov     eax, 80004003h
0x18008a0d9  jmp     loc_18008A4C1
0x18008a0de  mov     qword ptr [r9], 0
0x18008a0e5  test    rdx, rdx
0x18008a0e8  jnz     short loc_18008A0F4
0x18008a0ea  mov     eax, 80070057h
0x18008a0ef  jmp     loc_18008A4C1
0x18008a0f4  cmp     r15d, 10h
0x18008a0f8  jz      short loc_18008A10A
0x18008a0fa  cmp     r15d, 0Ah
0x18008a0fe  jz      short loc_18008A10A
0x18008a100  mov     eax, 80004001h
0x18008a105  jmp     loc_18008A4C1
0x18008a10a  xor     eax, eax
0x18008a10c  xor     edi, edi
0x18008a10e  mov     qword ptr [rsp+140h+pvarDest+10h], rax
0x18008a113  xorps   xmm0, xmm0
0x18008a116  mov     eax, 4000h
0x18008a11b  movups  xmmword ptr [rsp+140h+pvarDest], xmm0
0x18008a120  test    [rdx], ax
0x18008a123  jz      short loc_18008A13F
0x18008a125  lea     rcx, [rsp+140h+pvarDest]; pvarDest
0x18008a12a  call    cs:__imp_VariantCopyInd
0x18008a130  mov     edi, eax
0x18008a132  test    eax, eax
0x18008a134  js      loc_18008A4C1
0x18008a13a  lea     rbx, [rsp+140h+pvarDest]
0x18008a13f  lea     rsi, String
0x18008a146  xor     edx, edx; Val
0x18008a148  lea     rcx, [rbp+40h+Buffer]; void *
0x18008a14c  mov     r8d, 82h; Size
0x18008a152  call    memset_0
0x18008a157  movzx   ecx, word ptr [rbx]
0x18008a15a  cmp     ecx, 0Bh
0x18008a15d  ja      short loc_18008A1AE
0x18008a15f  jz      loc_18008A373
0x18008a165  test    ecx, ecx
0x18008a167  jz      loc_18008A367
0x18008a16d  sub     ecx, 1
0x18008a170  jz      loc_18008A35B
0x18008a176  sub     ecx, 1
0x18008a179  jz      loc_18008A352
0x18008a17f  sub     ecx, 1
0x18008a182  jz      loc_18008A43A
0x18008a188  sub     ecx, 1
0x18008a18b  jz      loc_18008A2E1
0x18008a191  sub     ecx, 1
0x18008a194  jz      loc_18008A2DA
0x18008a19a  sub     ecx, 3
0x18008a19d  jz      loc_18008A2BE
0x18008a1a3  cmp     ecx, 1
0x18008a1a6  jnz     loc_18008A42C
0x18008a1ac  jmp     short loc_18008A1B7
0x18008a1ae  sub     ecx, 0Dh
0x18008a1b1  jnz     loc_18008A40E
0x18008a1b7  mov     rbx, [rbx+8]
0x18008a1bb  test    rbx, rbx
0x18008a1be  jz      loc_18008A35B
0x18008a1c4  mov     [rsp+140h+var_F8], 0
0x18008a1cd  lea     r8, [rsp+140h+var_F8]
0x18008a1d2  mov     rax, [rbx]
0x18008a1d5  lea     rdx, IID_IJsDateObj
0x18008a1dc  mov     rcx, rbx
0x18008a1df  mov     rax, [rax]
0x18008a1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1e7  test    eax, eax
0x18008a1e9  jns     loc_18008A3A6
0x18008a1ef  mov     [rsp+140h+var_100], 0
0x18008a1f8  lea     r8, [rsp+140h+var_100]
0x18008a1fd  mov     rax, [rbx]
0x18008a200  lea     rdx, IID_IJsRegExpObj
0x18008a207  mov     rcx, rbx
0x18008a20a  mov     rax, [rax]
0x18008a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a212  test    eax, eax
0x18008a214  jns     loc_18008A390
0x18008a21a  mov     [rsp+140h+var_108], 0
0x18008a223  lea     r8, [rsp+140h+var_108]
0x18008a228  mov     rax, [rbx]
0x18008a22b  lea     rdx, IID_INameTbl
0x18008a232  mov     rcx, rbx
0x18008a235  mov     rax, [rax]
0x18008a238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a23d  test    eax, eax
0x18008a23f  js      loc_18008A493
0x18008a245  mov     rcx, [rsp+140h+var_108]
0x18008a24a  lea     rdx, [rsp+140h+var_D8]
0x18008a24f  mov     rax, [rcx]
0x18008a252  mov     rax, [rax+148h]
0x18008a259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a25e  mov     rcx, [rsp+140h+var_108]
0x18008a263  mov     edi, eax
0x18008a265  mov     rax, [rcx]
0x18008a268  mov     rax, [rax+10h]
0x18008a26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a271  test    edi, edi
0x18008a273  js      loc_18008A4AD
0x18008a279  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008a27e  call    cs:__imp_VariantClear
0x18008a284  lea     rdx, [rsp+140h+pvarDest]; struct tagVARIANT *
0x18008a289  lea     rcx, [rsp+140h+var_D8]; this
0x18008a28e  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18008a293  mov     edi, eax
0x18008a295  test    eax, eax
0x18008a297  js      loc_18008A4AD
0x18008a29d  movzx   eax, word ptr [rsp+140h+pvarDest]
0x18008a2a2  cmp     eax, 9
0x18008a2a5  jz      loc_18008A493
0x18008a2ab  cmp     eax, 0Dh
0x18008a2ae  jz      loc_18008A493
0x18008a2b4  lea     rbx, [rsp+140h+pvarDest]
0x18008a2b9  jmp     loc_18008A146
0x18008a2be  cmp     qword ptr [rbx+8], 0
0x18008a2c3  mov     rdx, r14
0x18008a2c6  cmovnz  rsi, [rbx+8]
0x18008a2cb  mov     rcx, rsi
0x18008a2ce  call    GetStringLiteral
0x18008a2d3  mov     edi, eax
0x18008a2d5  jmp     loc_18008A4AD
0x18008a2da  movsd   xmm1, qword ptr [rbx+8]
0x18008a2df  jmp     short loc_18008A2E9
0x18008a2e1  movss   xmm1, dword ptr [rbx+8]
0x18008a2e6  cvtps2pd xmm1, xmm1
0x18008a2e9  movq    rax, xmm1
0x18008a2ee  movaps  xmm0, xmm1; double
0x18008a2f1  shr     rax, 20h
0x18008a2f5  not     eax
0x18008a2f7  test    eax, 7FF00000h
0x18008a2fc  jz      short loc_18008A31F
0x18008a2fe  mov     r8d, 41h ; 'A'; int
0x18008a304  lea     rdx, [rbp+40h+Buffer]; unsigned __int16 *
0x18008a308  call    ?FDblToStr@@YAHNPEAGH@Z; FDblToStr(double,ushort *,int)
0x18008a30d  test    eax, eax
0x18008a30f  jnz     loc_18008A48F
0x18008a315  mov     edi, 8007000Eh
0x18008a31a  jmp     loc_18008A4AD
0x18008a31f  call    ?FNan@@YAHN@Z; FNan(double)
0x18008a324  test    eax, eax
0x18008a326  jz      short loc_18008A334
0x18008a328  lea     rsi, aNan; "NaN"
0x18008a32f  jmp     loc_18008A493
0x18008a334  xorps   xmm0, xmm0
0x18008a337  lea     rsi, aInfinity_0; "-Infinity"
0x18008a33e  comisd  xmm0, xmm1
0x18008a342  lea     rax, aInfinity; "Infinity"
0x18008a349  cmovbe  rsi, rax
0x18008a34d  jmp     loc_18008A493
0x18008a352  movsx   ecx, word ptr [rbx+8]
0x18008a356  jmp     loc_18008A469
0x18008a35b  lea     rsi, aNull; "null"
0x18008a362  jmp     loc_18008A493
0x18008a367  lea     rsi, aUndefined; "undefined"
0x18008a36e  jmp     loc_18008A493
0x18008a373  xor     eax, eax
0x18008a375  lea     rcx, aTrue; "true"
0x18008a37c  cmp     ax, [rbx+8]
0x18008a380  lea     rsi, aFalse; "false"
0x18008a387  cmovnz  rsi, rcx
0x18008a38b  jmp     loc_18008A493
0x18008a390  mov     rcx, [rsp+140h+var_100]; this
0x18008a395  lea     rdx, [rsp+140h+var_F0]; struct VAR *
0x18008a39a  call    ?GetString@RegExpObj@@QEAAJPEAVVAR@@@Z; RegExpObj::GetString(VAR *)
0x18008a39f  mov     rcx, [rsp+140h+var_100]
0x18008a3a4  jmp     short loc_18008A3C0
0x18008a3a6  mov     rcx, [rsp+140h+var_F8]; this
0x18008a3ab  lea     rdx, [rsp+140h+var_F0]; struct VAR *
0x18008a3b0  xor     r9d, r9d; unsigned int
0x18008a3b3  xor     r8d, r8d; int
0x18008a3b6  call    ?GetString@DateObj@@QEAAJPEAVVAR@@HK@Z; DateObj::GetString(VAR *,int,ulong)
0x18008a3bb  mov     rcx, [rsp+140h+var_F8]
0x18008a3c0  mov     edi, eax
0x18008a3c2  mov     rax, [rcx]
0x18008a3c5  mov     rax, [rax+10h]
0x18008a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a3ce  test    edi, edi
0x18008a3d0  js      loc_18008A4AD
0x18008a3d6  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008a3db  call    cs:__imp_VariantClear
0x18008a3e1  lea     rdx, [rsp+140h+pvarDest]; struct tagVARIANT *
0x18008a3e6  lea     rcx, [rsp+140h+var_F0]; this
0x18008a3eb  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18008a3f0  mov     edi, eax
0x18008a3f2  test    eax, eax
0x18008a3f4  js      loc_18008A4AD
0x18008a3fa  mov     rax, qword ptr [rsp+140h+pvarDest+8]
0x18008a3ff  mov     [r14], rax
0x18008a402  xor     eax, eax
0x18008a404  mov     word ptr [rsp+140h+pvarDest], ax
0x18008a409  jmp     loc_18008A4AD
0x18008a40e  sub     ecx, 3
0x18008a411  jz      short loc_18008A465
0x18008a413  sub     ecx, 1
0x18008a416  jz      short loc_18008A445
0x18008a418  sub     ecx, 1
0x18008a41b  jz      short loc_18008A43F
0x18008a41d  sub     ecx, 1
0x18008a420  jz      short loc_18008A435
0x18008a422  sub     ecx, 3
0x18008a425  jz      short loc_18008A43A
0x18008a427  cmp     ecx, 1
0x18008a42a  jz      short loc_18008A435
0x18008a42c  mov     qword ptr [r14], 0
0x18008a433  jmp     short loc_18008A4AD
0x18008a435  mov     ecx, [rbx+8]
0x18008a438  jmp     short loc_18008A449
0x18008a43a  mov     ecx, [rbx+8]
0x18008a43d  jmp     short loc_18008A469
0x18008a43f  movzx   ecx, word ptr [rbx+8]
0x18008a443  jmp     short loc_18008A449
0x18008a445  movzx   ecx, byte ptr [rbx+8]; Value
0x18008a449  cmp     r15d, 10h
0x18008a44d  jz      short loc_18008A46F
0x18008a44f  mov     r9d, 0Ah; Radix
0x18008a455  lea     rdx, [rbp+40h+Buffer]; Buffer
0x18008a459  lea     r8d, [r9+37h]; BufferCount
0x18008a45d  call    cs:__imp__ultow_s
0x18008a463  jmp     short loc_18008A48F
0x18008a465  movsx   ecx, byte ptr [rbx+8]; Value
0x18008a469  cmp     r15d, 10h
0x18008a46d  jnz     short loc_18008A47F
0x18008a46f  mov     rdx, r14
0x18008a472  mov     rcx, rbx
0x18008a475  call    GetHexLiteral
0x18008a47a  jmp     loc_18008A2D3
0x18008a47f  mov     r8d, 0Ah; Radix
0x18008a485  lea     rdx, [rbp+40h+Buffer]; Buffer
0x18008a489  call    cs:__imp__ltow
0x18008a48f  lea     rsi, [rbp+40h+Buffer]
0x18008a493  mov     rcx, rsi; strIn
0x18008a496  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x18008a49b  mov     ecx, edi
0x18008a49d  mov     [r14], rax
0x18008a4a0  mov     edi, 8007000Eh
0x18008a4a5  test    rax, rax
0x18008a4a8  cmovz   ecx, edi
0x18008a4ab  mov     edi, ecx
0x18008a4ad  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008a4b2  call    cs:__imp_VariantClear
0x18008a4b8  xor     eax, eax
0x18008a4ba  test    edi, edi
0x18008a4bc  cmovns  edi, eax
0x18008a4bf  mov     eax, edi
0x18008a4c1  mov     rcx, [rbp+40h+var_30]
0x18008a4c5  xor     rcx, rsp; StackCookie
0x18008a4c8  call    __security_check_cookie
0x18008a4cd  mov     rbx, [rsp+140h+arg_0]
0x18008a4d5  add     rsp, 120h
0x18008a4dc  pop     r15
0x18008a4de  pop     r14
0x18008a4e0  pop     rdi
0x18008a4e1  pop     rsi
0x18008a4e2  pop     rbp
0x18008a4e3  retn
```
