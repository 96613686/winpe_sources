# ComDebugFormatter::GetStringForVariant(tagVARIANT *,ulong,ushort * *)

- ea: `0x18008c100`
- end: `0x18008c56c`
- name: `?GetStringForVariant@ComDebugFormatter@@UEAAJPEAUtagVARIANT@@KPEAPEAG@Z`
- size: `1132`
- prototype: `__int64 __fastcall(ComDebugFormatter *__hidden this, struct tagVARIANT *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x180004c64`
- `0x180004d40`
- `0x18003e134`
- `0x18005f2ac`
- `0x1800705cc`
- `0x18008be7c`
- `0x18008c100`
- `0x18008c574`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18008c4d2`
- `msvcrt!_ultow_s` at `0x18008c4d2`
- `msvcrt!_ltow` at `0x18008c504`
- `msvcrt!_ltow` at `0x18008c504`
- `OLEAUT32!__imp_VariantClear` at `0x18008c2e4`
- `OLEAUT32!__imp_VariantClear` at `0x18008c447`
- `OLEAUT32!__imp_VariantClear` at `0x18008c533`
- `OLEAUT32!__imp_VariantClear` at `0x18008c2e4`
- `OLEAUT32!__imp_VariantClear` at `0x18008c447`
- `OLEAUT32!__imp_VariantClear` at `0x18008c533`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008c18a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18008c18a`

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
  OLECHAR *bstrVal; // rsi
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
  bstrVal = (OLECHAR *)&::String;
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
          bstrVal = (OLECHAR *)L"Infinity";
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
0x18008c100  mov     [rsp-8+arg_0], rbx
0x18008c105  push    rbp
0x18008c106  push    rsi
0x18008c107  push    rdi
0x18008c108  push    r14
0x18008c10a  push    r15
0x18008c10c  lea     rbp, [rsp-20h]
0x18008c111  sub     rsp, 120h
0x18008c118  mov     rax, cs:__security_cookie
0x18008c11f  xor     rax, rsp
0x18008c122  mov     [rbp+40h+var_30], rax
0x18008c126  mov     r14, r9
0x18008c129  mov     r15d, r8d
0x18008c12c  mov     rbx, rdx
0x18008c12f  test    r9, r9
0x18008c132  jnz     short loc_18008C13E
0x18008c134  mov     eax, 80004003h
0x18008c139  jmp     loc_18008C548
0x18008c13e  mov     qword ptr [r9], 0
0x18008c145  test    rdx, rdx
0x18008c148  jnz     short loc_18008C154
0x18008c14a  mov     eax, 80070057h
0x18008c14f  jmp     loc_18008C548
0x18008c154  cmp     r15d, 10h
0x18008c158  jz      short loc_18008C16A
0x18008c15a  cmp     r15d, 0Ah
0x18008c15e  jz      short loc_18008C16A
0x18008c160  mov     eax, 80004001h
0x18008c165  jmp     loc_18008C548
0x18008c16a  xor     eax, eax
0x18008c16c  xor     edi, edi
0x18008c16e  mov     qword ptr [rsp+140h+pvarDest+10h], rax
0x18008c173  xorps   xmm0, xmm0
0x18008c176  mov     eax, 4000h
0x18008c17b  movups  xmmword ptr [rsp+140h+pvarDest], xmm0
0x18008c180  test    [rdx], ax
0x18008c183  jz      short loc_18008C1A5
0x18008c185  lea     rcx, [rsp+140h+pvarDest]; pvarDest
0x18008c18a  call    cs:__imp_VariantCopyInd
0x18008c191  nop     dword ptr [rax+rax+00h]
0x18008c196  mov     edi, eax
0x18008c198  test    eax, eax
0x18008c19a  js      loc_18008C548
0x18008c1a0  lea     rbx, [rsp+140h+pvarDest]
0x18008c1a5  lea     rsi, String
0x18008c1ac  xor     edx, edx; Val
0x18008c1ae  lea     rcx, [rbp+40h+Buffer]; void *
0x18008c1b2  mov     r8d, 82h; Size
0x18008c1b8  call    memset_0
0x18008c1bd  movzx   ecx, word ptr [rbx]
0x18008c1c0  cmp     ecx, 0Bh
0x18008c1c3  ja      short loc_18008C214
0x18008c1c5  jz      loc_18008C3DF
0x18008c1cb  test    ecx, ecx
0x18008c1cd  jz      loc_18008C3D3
0x18008c1d3  sub     ecx, 1
0x18008c1d6  jz      loc_18008C3C7
0x18008c1dc  sub     ecx, 1
0x18008c1df  jz      loc_18008C3BE
0x18008c1e5  sub     ecx, 1
0x18008c1e8  jz      loc_18008C4AF
0x18008c1ee  sub     ecx, 1
0x18008c1f1  jz      loc_18008C34D
0x18008c1f7  sub     ecx, 1
0x18008c1fa  jz      loc_18008C346
0x18008c200  sub     ecx, 3
0x18008c203  jz      loc_18008C32A
0x18008c209  cmp     ecx, 1
0x18008c20c  jnz     loc_18008C49E
0x18008c212  jmp     short loc_18008C21D
0x18008c214  sub     ecx, 0Dh
0x18008c217  jnz     loc_18008C480
0x18008c21d  mov     rbx, [rbx+8]
0x18008c221  test    rbx, rbx
0x18008c224  jz      loc_18008C3C7
0x18008c22a  mov     [rsp+140h+var_F8], 0
0x18008c233  lea     r8, [rsp+140h+var_F8]
0x18008c238  mov     rax, [rbx]
0x18008c23b  lea     rdx, IID_IJsDateObj
0x18008c242  mov     rcx, rbx
0x18008c245  mov     rax, [rax]
0x18008c248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c24d  test    eax, eax
0x18008c24f  jns     loc_18008C412
0x18008c255  mov     [rsp+140h+var_100], 0
0x18008c25e  lea     r8, [rsp+140h+var_100]
0x18008c263  mov     rax, [rbx]
0x18008c266  lea     rdx, IID_IJsRegExpObj
0x18008c26d  mov     rcx, rbx
0x18008c270  mov     rax, [rax]
0x18008c273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c278  test    eax, eax
0x18008c27a  jns     loc_18008C3FC
0x18008c280  mov     [rsp+140h+var_108], 0
0x18008c289  lea     r8, [rsp+140h+var_108]
0x18008c28e  mov     rax, [rbx]
0x18008c291  lea     rdx, IID_INameTbl
0x18008c298  mov     rcx, rbx
0x18008c29b  mov     rax, [rax]
0x18008c29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2a3  test    eax, eax
0x18008c2a5  js      loc_18008C514
0x18008c2ab  mov     rcx, [rsp+140h+var_108]
0x18008c2b0  lea     rdx, [rsp+140h+var_D8]
0x18008c2b5  mov     rax, [rcx]
0x18008c2b8  mov     rax, [rax+148h]
0x18008c2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2c4  mov     rcx, [rsp+140h+var_108]
0x18008c2c9  mov     edi, eax
0x18008c2cb  mov     rax, [rcx]
0x18008c2ce  mov     rax, [rax+10h]
0x18008c2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2d7  test    edi, edi
0x18008c2d9  js      loc_18008C52E
0x18008c2df  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008c2e4  call    cs:__imp_VariantClear
0x18008c2eb  nop     dword ptr [rax+rax+00h]
0x18008c2f0  lea     rdx, [rsp+140h+pvarDest]; struct tagVARIANT *
0x18008c2f5  lea     rcx, [rsp+140h+var_D8]; this
0x18008c2fa  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18008c2ff  mov     edi, eax
0x18008c301  test    eax, eax
0x18008c303  js      loc_18008C52E
0x18008c309  movzx   eax, word ptr [rsp+140h+pvarDest]
0x18008c30e  cmp     eax, 9
0x18008c311  jz      loc_18008C514
0x18008c317  cmp     eax, 0Dh
0x18008c31a  jz      loc_18008C514
0x18008c320  lea     rbx, [rsp+140h+pvarDest]
0x18008c325  jmp     loc_18008C1AC
0x18008c32a  cmp     qword ptr [rbx+8], 0
0x18008c32f  mov     rdx, r14
0x18008c332  cmovnz  rsi, [rbx+8]
0x18008c337  mov     rcx, rsi
0x18008c33a  call    GetStringLiteral
0x18008c33f  mov     edi, eax
0x18008c341  jmp     loc_18008C52E
0x18008c346  movsd   xmm1, qword ptr [rbx+8]
0x18008c34b  jmp     short loc_18008C355
0x18008c34d  movss   xmm1, dword ptr [rbx+8]
0x18008c352  cvtps2pd xmm1, xmm1
0x18008c355  movq    rax, xmm1
0x18008c35a  movaps  xmm0, xmm1; double
0x18008c35d  shr     rax, 20h
0x18008c361  not     eax
0x18008c363  test    eax, 7FF00000h
0x18008c368  jz      short loc_18008C38B
0x18008c36a  mov     r8d, 41h ; 'A'; int
0x18008c370  lea     rdx, [rbp+40h+Buffer]; unsigned __int16 *
0x18008c374  call    ?FDblToStr@@YAHNPEAGH@Z; FDblToStr(double,ushort *,int)
0x18008c379  test    eax, eax
0x18008c37b  jnz     loc_18008C510
0x18008c381  mov     edi, 8007000Eh
0x18008c386  jmp     loc_18008C52E
0x18008c38b  call    ?FNan@@YAHN@Z; FNan(double)
0x18008c390  test    eax, eax
0x18008c392  jz      short loc_18008C3A0
0x18008c394  lea     rsi, aNan; "NaN"
0x18008c39b  jmp     loc_18008C514
0x18008c3a0  xorps   xmm0, xmm0
0x18008c3a3  lea     rsi, aInfinity_0; "-Infinity"
0x18008c3aa  comisd  xmm0, xmm1
0x18008c3ae  lea     rax, aInfinity; "Infinity"
0x18008c3b5  cmovbe  rsi, rax
0x18008c3b9  jmp     loc_18008C514
0x18008c3be  movsx   ecx, word ptr [rbx+8]
0x18008c3c2  jmp     loc_18008C4E4
0x18008c3c7  lea     rsi, aNull; "null"
0x18008c3ce  jmp     loc_18008C514
0x18008c3d3  lea     rsi, aUndefined; "undefined"
0x18008c3da  jmp     loc_18008C514
0x18008c3df  xor     eax, eax
0x18008c3e1  lea     rcx, aTrue; "true"
0x18008c3e8  cmp     ax, [rbx+8]
0x18008c3ec  lea     rsi, aFalse; "false"
0x18008c3f3  cmovnz  rsi, rcx
0x18008c3f7  jmp     loc_18008C514
0x18008c3fc  mov     rcx, [rsp+140h+var_100]; this
0x18008c401  lea     rdx, [rsp+140h+var_F0]; struct VAR *
0x18008c406  call    ?GetString@RegExpObj@@QEAAJPEAVVAR@@@Z; RegExpObj::GetString(VAR *)
0x18008c40b  mov     rcx, [rsp+140h+var_100]
0x18008c410  jmp     short loc_18008C42C
0x18008c412  mov     rcx, [rsp+140h+var_F8]; this
0x18008c417  lea     rdx, [rsp+140h+var_F0]; struct VAR *
0x18008c41c  xor     r9d, r9d; unsigned int
0x18008c41f  xor     r8d, r8d; int
0x18008c422  call    ?GetString@DateObj@@QEAAJPEAVVAR@@HK@Z; DateObj::GetString(VAR *,int,ulong)
0x18008c427  mov     rcx, [rsp+140h+var_F8]
0x18008c42c  mov     edi, eax
0x18008c42e  mov     rax, [rcx]
0x18008c431  mov     rax, [rax+10h]
0x18008c435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c43a  test    edi, edi
0x18008c43c  js      loc_18008C52E
0x18008c442  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008c447  call    cs:__imp_VariantClear
0x18008c44e  nop     dword ptr [rax+rax+00h]
0x18008c453  lea     rdx, [rsp+140h+pvarDest]; struct tagVARIANT *
0x18008c458  lea     rcx, [rsp+140h+var_F0]; this
0x18008c45d  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18008c462  mov     edi, eax
0x18008c464  test    eax, eax
0x18008c466  js      loc_18008C52E
0x18008c46c  mov     rax, qword ptr [rsp+140h+pvarDest+8]
0x18008c471  mov     [r14], rax
0x18008c474  xor     eax, eax
0x18008c476  mov     word ptr [rsp+140h+pvarDest], ax
0x18008c47b  jmp     loc_18008C52E
0x18008c480  sub     ecx, 3
0x18008c483  jz      short loc_18008C4E0
0x18008c485  sub     ecx, 1
0x18008c488  jz      short loc_18008C4BA
0x18008c48a  sub     ecx, 1
0x18008c48d  jz      short loc_18008C4B4
0x18008c48f  sub     ecx, 1
0x18008c492  jz      short loc_18008C4AA
0x18008c494  sub     ecx, 3
0x18008c497  jz      short loc_18008C4AF
0x18008c499  cmp     ecx, 1
0x18008c49c  jz      short loc_18008C4AA
0x18008c49e  mov     qword ptr [r14], 0
0x18008c4a5  jmp     loc_18008C52E
0x18008c4aa  mov     ecx, [rbx+8]
0x18008c4ad  jmp     short loc_18008C4BE
0x18008c4af  mov     ecx, [rbx+8]
0x18008c4b2  jmp     short loc_18008C4E4
0x18008c4b4  movzx   ecx, word ptr [rbx+8]
0x18008c4b8  jmp     short loc_18008C4BE
0x18008c4ba  movzx   ecx, byte ptr [rbx+8]; Value
0x18008c4be  cmp     r15d, 10h
0x18008c4c2  jz      short loc_18008C4EA
0x18008c4c4  mov     r9d, 0Ah; Radix
0x18008c4ca  lea     rdx, [rbp+40h+Buffer]; Buffer
0x18008c4ce  lea     r8d, [r9+37h]; BufferCount
0x18008c4d2  call    cs:__imp__ultow_s
0x18008c4d9  nop     dword ptr [rax+rax+00h]
0x18008c4de  jmp     short loc_18008C510
0x18008c4e0  movsx   ecx, byte ptr [rbx+8]; Value
0x18008c4e4  cmp     r15d, 10h
0x18008c4e8  jnz     short loc_18008C4FA
0x18008c4ea  mov     rdx, r14
0x18008c4ed  mov     rcx, rbx
0x18008c4f0  call    GetHexLiteral
0x18008c4f5  jmp     loc_18008C33F
0x18008c4fa  mov     r8d, 0Ah; Radix
0x18008c500  lea     rdx, [rbp+40h+Buffer]; Buffer
0x18008c504  call    cs:__imp__ltow
0x18008c50b  nop     dword ptr [rax+rax+00h]
0x18008c510  lea     rsi, [rbp+40h+Buffer]
0x18008c514  mov     rcx, rsi; strIn
0x18008c517  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x18008c51c  mov     ecx, edi
0x18008c51e  mov     [r14], rax
0x18008c521  mov     edi, 8007000Eh
0x18008c526  test    rax, rax
0x18008c529  cmovz   ecx, edi
0x18008c52c  mov     edi, ecx
0x18008c52e  lea     rcx, [rsp+140h+pvarDest]; pvarg
0x18008c533  call    cs:__imp_VariantClear
0x18008c53a  nop     dword ptr [rax+rax+00h]
0x18008c53f  xor     eax, eax
0x18008c541  test    edi, edi
0x18008c543  cmovns  edi, eax
0x18008c546  mov     eax, edi
0x18008c548  mov     rcx, [rbp+40h+var_30]
0x18008c54c  xor     rcx, rsp; StackCookie
0x18008c54f  call    __security_check_cookie
0x18008c554  mov     rbx, [rsp+140h+arg_0]
0x18008c55c  add     rsp, 120h
0x18008c563  pop     r15
0x18008c565  pop     r14
0x18008c567  pop     rdi
0x18008c568  pop     rsi
0x18008c569  pop     rbp
0x18008c56a  retn
```
