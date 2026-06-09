# XPathParser::parsePrimaryExpr(Query *,BaseQuery::Cardinality)

- ea: `0x180053c34`
- end: `0x1800541fd`
- name: `?parsePrimaryExpr@XPathParser@@AEAAPEAVOperand@@PEAVQuery@@W4Cardinality@BaseQuery@@@Z`
- size: `1481`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x1800966e8`

## callees

- `0x180016334`
- `0x1800306f4`
- `0x18003adb4`
- `0x1800471c4`
- `0x18004a63c`
- `0x18004a664`
- `0x18004a8fc`
- `0x18004ab2c`
- `0x18004abb8`
- `0x180053c34`
- `0x180064034`
- `0x1800950f0`
- `0x180095208`
- `0x18009b6b4`
- `0x18009ba08`
- `0x18009ba94`
- `0x18009bac4`
- `0x18009f400`
- `0x18009f650`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800540d6`
- `msvcrt!_resetstkoflw` at `0x1800540d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054129`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054129`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800540c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180054155`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800540c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180054155`

## pseudocode

```c
__int64 __fastcall XPathParser::parsePrimaryExpr(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // r15d
  _DWORD *v6; // rsi
  char v7; // r14
  const unsigned __int16 *v8; // rbx
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  struct Atom *v15; // rcx
  const unsigned __int16 *v16; // r15
  struct Name *v17; // rax
  struct ConstantOperand *v18; // rax
  __int64 v19; // rcx
  bool v20; // cf
  bool v21; // dl
  struct String *v22; // rcx
  struct ConstantOperand *v23; // rbx
  struct Operand *v24; // rbx
  XQLParser *v25; // rbx
  __int64 v26; // rbx
  struct Vector *v27; // r14
  struct Name *v28; // r13
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-58h]
  XQLParser *v31; // [rsp+80h] [rbp+8h] BYREF
  struct Vector *v32; // [rsp+98h] [rbp+20h] BYREF

  v31 = (XQLParser *)a1;
  v3 = a3;
  v6 = (_DWORD *)(a1 + 136);
  v7 = 1;
  if ( (int)++*(_DWORD *)(a1 + 136) > 1024 )
    Exception::throwHR(-2147024882);
  v8 = *(const unsigned __int16 **)(a1 + 56);
  v9 = *(_DWORD *)(a1 + 64);
  if ( v9 == -4 )
  {
    v9 = *(_DWORD *)(a1 + 160);
    *(_DWORD *)(a1 + 64) = v9;
  }
  switch ( v9 )
  {
    case -112:
      v27 = Vector::newVector(4, -112);
      v32 = v27;
      v28 = Name::create(*(struct Atom **)(a1 + 96), *(struct Atom **)(a1 + 80));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XPathParser::argumentsHelper(a1, 0, &v32, a2, v3);
      v29 = *(_QWORD *)(a1 + 152);
      if ( !v29 )
        XQLParser::throwE((XQLParser *)a1, -1072897147, v8, 0, 0);
      v11 = (*(__int64 (__fastcall **)(__int64, struct Name *, struct Vector *))(*(_QWORD *)v29 + 8LL))(v29, v28, v27);
      goto LABEL_47;
    case -97:
      v25 = Vector::newVector(2, -97);
      v31 = v25;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XPathParser::argumentsHelper(a1, 2, &v31, a2, v3);
      v26 = ComplexMethodOperand::newComplexMethodOperand(v25, 1);
      XQLParser::checkToken(a1, 41);
      v19 = v26 + 16;
      v20 = v26 != 0;
      goto LABEL_41;
    case -96:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XQLParser::checkToken(a1, 40);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      if ( *(_DWORD *)(a1 + 64) == 41 )
        XQLParser::throwE((XQLParser *)a1, -1072896510, v8, 0, 0);
      v24 = (struct Operand *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, 0, v3);
      XQLParser::checkToken(a1, 41);
      v18 = NotExpr::newNotExpr(v24);
      goto LABEL_32;
    case -95:
      v21 = 0;
      v22 = (struct String *)&OperandValue::s_cstrFalseXP;
      goto LABEL_36;
    case -94:
      v21 = 1;
      v22 = (struct String *)&OperandValue::s_cstrTrueXP;
LABEL_36:
      v23 = ConstantOperand::newBool(v22, v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XQLParser::checkToken(a1, 40);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XQLParser::checkToken(a1, 41);
      v11 = ((unsigned __int64)v23 + 16) & -(__int64)(v23 != 0);
      break;
    case -6:
      v18 = ConstantOperand::newR8(*(struct String **)(a1 + 72), *(double *)(a1 + 120));
      goto LABEL_32;
    case -5:
      v18 = ConstantOperand::newString(*(struct String **)(a1 + 72));
LABEL_32:
      v19 = (__int64)v18 + 16;
      v20 = v18 != 0;
LABEL_41:
      v11 = v19 & -(__int64)v20;
      break;
    case 36:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      XQLParser::checkToken(a1, 4294967292LL);
      v15 = *(struct Atom **)(a1 + 96);
      if ( !v15 )
        XQLParser::throwE((XQLParser *)a1, -1072896763, v8, 0, 0);
      if ( !*(_QWORD *)(a1 + 152) )
        XQLParser::throwE((XQLParser *)a1, -1072896507, v8, 0, 0);
      if ( (*(_BYTE *)(a1 + 144) & 0x10) != 0 )
        XQLParser::throwE((XQLParser *)a1, -1072896496, v8, 0, 0);
      v16 = *(const unsigned __int16 **)(a1 + 56);
      v17 = Name::create(v15, *(struct Atom **)(a1 + 80));
      v11 = (***(__int64 (__fastcall ****)(_QWORD, struct Name *))(a1 + 152))(*(_QWORD *)(a1 + 152), v17);
      if ( !v11 )
        XQLParser::throwE((XQLParser *)a1, -1072896507, v16, 0, 0);
      break;
    case 40:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
      result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, a2, v3);
      v11 = result;
      if ( !result )
      {
        --*v6;
        return result;
      }
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)result + 152LL))(result);
      if ( v13 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 200LL))(v13, 0);
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 152LL))(v14);
      }
      XQLParser::checkToken(a1, 41);
      break;
    default:
      if ( (unsigned int)(v9 + 93) <= 2 )
      {
        v10 = XPathParser::constructCast();
      }
      else
      {
        v30 = a3;
        LOBYTE(a3) = 1;
        v10 = XQLParser::parseMethod(a1, 0, a3, 0, v30);
      }
      v11 = v10;
      v7 = 0;
      break;
  }
  if ( v7 )
LABEL_47:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 160LL))(a1);
  result = v11;
  --*v6;
  return result;
}

```

## disassembly

```asm
0x180053c34  mov     [rsp+arg_8], rbx
0x180053c39  mov     [rsp+arg_10], rsi
0x180053c3e  mov     [rsp+arg_0], rcx
0x180053c43  push    rdi
0x180053c44  push    r12
0x180053c46  push    r13
0x180053c48  push    r14
0x180053c4a  push    r15
0x180053c4c  sub     rsp, 50h
0x180053c50  mov     r15d, r8d
0x180053c53  mov     r12, rdx
0x180053c56  mov     rdi, rcx
0x180053c59  lea     rsi, [rcx+88h]
0x180053c60  mov     [rsp+78h+var_38], rsi
0x180053c65  mov     r14d, 1
0x180053c6b  add     [rsi], r14d
0x180053c6e  cmp     dword ptr [rsi], 400h
0x180053c74  jle     short loc_180053C81
0x180053c76  mov     ecx, 8007000Eh; int
0x180053c7b  call    ?throwHR@Exception@@SAXJ@Z; Exception::throwHR(long)
0x180053c81  mov     rbx, [rcx+38h]
0x180053c85  mov     [rsp+78h+var_48], rbx
0x180053c8a  mov     edx, [rcx+40h]
0x180053c8d  cmp     edx, 0FFFFFFFCh
0x180053c90  jnz     short loc_180053C9B
0x180053c92  mov     edx, [rcx+0A0h]; int
0x180053c98  mov     [rcx+40h], edx
0x180053c9b  cmp     edx, 0FFFFFF90h
0x180053c9e  jz      loc_180054017
0x180053ca4  cmp     edx, 0FFFFFF9Fh
0x180053ca7  jz      loc_180053F8B
0x180053cad  cmp     edx, 0FFFFFFA0h
0x180053cb0  jz      loc_180053F09
0x180053cb6  cmp     edx, 0FFFFFFA1h
0x180053cb9  jz      loc_180053EA8
0x180053cbf  cmp     edx, 0FFFFFFA2h
0x180053cc2  jz      loc_180053E9C
0x180053cc8  cmp     edx, 0FFFFFFFAh
0x180053ccb  jz      loc_180053E8C
0x180053cd1  cmp     edx, 0FFFFFFFBh
0x180053cd4  jz      loc_180053E77
0x180053cda  cmp     edx, 24h ; '$'
0x180053cdd  jz      loc_180053DA2
0x180053ce3  cmp     edx, 28h ; '('
0x180053ce6  jz      short loc_180053D14
0x180053ce8  lea     eax, [rdx+5Dh]
0x180053ceb  cmp     eax, 2
0x180053cee  jbe     short loc_180053D04
0x180053cf0  mov     [rsp+78h+var_58], r15d
0x180053cf5  xor     r9d, r9d
0x180053cf8  mov     r8b, r14b
0x180053cfb  xor     edx, edx
0x180053cfd  call    ?parseMethod@XQLParser@@IEAAPEAVOperand@@PEAVQuery@@_N1W4Cardinality@BaseQuery@@@Z; XQLParser::parseMethod(Query *,bool,bool,BaseQuery::Cardinality)
0x180053d02  jmp     short loc_180053D09
0x180053d04  call    ?constructCast@XPathParser@@IEAAPEAVOperand@@W4xqlTokenType@@@Z; XPathParser::constructCast(xqlTokenType)
0x180053d09  mov     rbx, rax
0x180053d0c  xor     r14b, r14b
0x180053d0f  jmp     loc_180054009
0x180053d14  mov     rax, [rcx]
0x180053d17  mov     rax, [rax+0A0h]
0x180053d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d23  mov     rax, [rdi]
0x180053d26  mov     r8d, r15d
0x180053d29  mov     rdx, r12
0x180053d2c  mov     rcx, rdi
0x180053d2f  mov     rax, [rax+98h]
0x180053d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d3b  mov     rbx, rax
0x180053d3e  test    rax, rax
0x180053d41  jnz     short loc_180053D4A
0x180053d43  dec     dword ptr [rsi]
0x180053d45  jmp     loc_1800541E3
0x180053d4a  mov     rax, [rax]
0x180053d4d  mov     rcx, rbx
0x180053d50  mov     rax, [rax+98h]
0x180053d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d5c  mov     r8, rax
0x180053d5f  test    rax, rax
0x180053d62  jz      short loc_180053D90
0x180053d64  mov     rcx, [rax]
0x180053d67  mov     rax, [rcx+0C8h]
0x180053d6e  xor     edx, edx
0x180053d70  mov     rcx, r8
0x180053d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d78  mov     rdx, rax
0x180053d7b  mov     rcx, [rax]
0x180053d7e  mov     rax, [rcx+98h]
0x180053d85  mov     rcx, rdx
0x180053d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d8d  mov     rbx, rax
0x180053d90  mov     edx, 29h ; ')'
0x180053d95  mov     rcx, rdi
0x180053d98  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053d9d  jmp     loc_180054009
0x180053da2  mov     rax, [rcx]
0x180053da5  mov     rax, [rax+0A0h]
0x180053dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053db1  mov     edx, 0FFFFFFFCh
0x180053db6  mov     rcx, rdi
0x180053db9  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053dbe  mov     rcx, [rdi+60h]; struct Atom *
0x180053dc2  test    rcx, rcx
0x180053dc5  jnz     short loc_180053DE0
0x180053dc7  mov     qword ptr [rsp+78h+var_58], rcx; unsigned __int16 *
0x180053dcc  xor     r9d, r9d; unsigned __int16 *
0x180053dcf  mov     r8, rbx; unsigned __int16 *
0x180053dd2  mov     edx, 0C00CE505h; int
0x180053dd7  mov     rcx, rdi; this
0x180053dda  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x180053de0  cmp     qword ptr [rdi+98h], 0
0x180053de8  jnz     short loc_180053E07
0x180053dea  mov     qword ptr [rsp+78h+var_58], 0; unsigned __int16 *
0x180053df3  xor     r9d, r9d; unsigned __int16 *
0x180053df6  mov     r8, rbx; unsigned __int16 *
0x180053df9  mov     edx, 0C00CE605h; int
0x180053dfe  mov     rcx, rdi; this
0x180053e01  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x180053e07  test    byte ptr [rdi+90h], 10h
0x180053e0e  jz      short loc_180053E2D
0x180053e10  mov     qword ptr [rsp+78h+var_58], 0; unsigned __int16 *
0x180053e19  xor     r9d, r9d; unsigned __int16 *
0x180053e1c  mov     r8, rbx; unsigned __int16 *
0x180053e1f  mov     edx, 0C00CE610h; int
0x180053e24  mov     rcx, rdi; this
0x180053e27  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x180053e2d  mov     r15, [rdi+38h]
0x180053e31  mov     rdx, [rdi+50h]; struct Atom *
0x180053e35  call    ?create@Name@@SAPEAV1@PEAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x180053e3a  mov     r9, rax
0x180053e3d  mov     rcx, [rdi+98h]
0x180053e44  mov     rdx, [rcx]
0x180053e47  mov     rax, [rdx]
0x180053e4a  mov     rdx, r9
0x180053e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e52  mov     rbx, rax
0x180053e55  test    rax, rax
0x180053e58  jnz     loc_180054009
0x180053e5e  mov     qword ptr [rsp+78h+var_58], rax; unsigned __int16 *
0x180053e63  xor     r9d, r9d; unsigned __int16 *
0x180053e66  mov     r8, r15; unsigned __int16 *
0x180053e69  mov     edx, 0C00CE605h; int
0x180053e6e  mov     rcx, rdi; this
0x180053e71  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x180053e77  mov     rcx, [rcx+48h]; struct String *
0x180053e7b  call    ?newString@ConstantOperand@@SAPEAV1@PEAVString@@@Z; ConstantOperand::newString(String *)
0x180053e80  lea     rcx, [rax+10h]
0x180053e84  neg     rax
0x180053e87  jmp     loc_180054003
0x180053e8c  movsd   xmm1, qword ptr [rcx+78h]; double
0x180053e91  mov     rcx, [rcx+48h]; struct String *
0x180053e95  call    ?newR8@ConstantOperand@@SAPEAV1@PEAVString@@N@Z; ConstantOperand::newR8(String *,double)
0x180053e9a  jmp     short loc_180053E80
0x180053e9c  mov     dl, r14b
0x180053e9f  lea     rcx, ?s_cstrTrueXP@OperandValue@@2V_CodebaseString@@B; _CodebaseString const OperandValue::s_cstrTrueXP
0x180053ea6  jmp     short loc_180053EB1
0x180053ea8  xor     edx, edx; bool
0x180053eaa  lea     rcx, ?s_cstrFalseXP@OperandValue@@2V_CodebaseString@@B; struct String *
0x180053eb1  call    ?newBool@ConstantOperand@@SAPEAV1@PEAVString@@_N@Z; ConstantOperand::newBool(String *,bool)
0x180053eb6  mov     rbx, rax
0x180053eb9  mov     rcx, [rdi]
0x180053ebc  mov     rax, [rcx+0A0h]
0x180053ec3  mov     rcx, rdi
0x180053ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ecb  mov     edx, 28h ; '('
0x180053ed0  mov     rcx, rdi
0x180053ed3  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053ed8  mov     rcx, [rdi]
0x180053edb  mov     rax, [rcx+0A0h]
0x180053ee2  mov     rcx, rdi
0x180053ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053eea  mov     edx, 29h ; ')'
0x180053eef  mov     rcx, rdi
0x180053ef2  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053ef7  lea     rax, [rbx+10h]
0x180053efb  neg     rbx
0x180053efe  sbb     rbx, rbx
0x180053f01  and     rbx, rax
0x180053f04  jmp     loc_180054009
0x180053f09  mov     rax, [rcx]
0x180053f0c  mov     rax, [rax+0A0h]
0x180053f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f18  mov     edx, 28h ; '('
0x180053f1d  mov     rcx, rdi
0x180053f20  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053f25  mov     rax, [rdi]
0x180053f28  mov     rcx, rdi
0x180053f2b  mov     rax, [rax+0A0h]
0x180053f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f37  mov     rcx, rdi; this
0x180053f3a  cmp     dword ptr [rdi+40h], 29h ; ')'
0x180053f3e  jnz     short loc_180053F5A
0x180053f40  mov     qword ptr [rsp+78h+var_58], 0; unsigned __int16 *
0x180053f49  xor     r9d, r9d; unsigned __int16 *
0x180053f4c  mov     r8, rbx; unsigned __int16 *
0x180053f4f  mov     edx, 0C00CE602h; int
0x180053f54  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x180053f5a  mov     rax, [rdi]
0x180053f5d  mov     r8d, r15d
0x180053f60  xor     edx, edx
0x180053f62  mov     rax, [rax+98h]
0x180053f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f6e  mov     rbx, rax
0x180053f71  mov     edx, 29h ; ')'
0x180053f76  mov     rcx, rdi
0x180053f79  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053f7e  mov     rcx, rbx; struct Operand *
0x180053f81  call    ?newNotExpr@NotExpr@@SAPEAV1@PEAVOperand@@@Z; NotExpr::newNotExpr(Operand *)
0x180053f86  jmp     loc_180053E80
0x180053f8b  mov     ecx, 2; int
0x180053f90  call    ?newVector@Vector@@SAPEAV1@HH@Z; Vector::newVector(int,int)
0x180053f95  mov     rbx, rax
0x180053f98  mov     [rsp+78h+arg_0], rax
0x180053fa0  mov     rcx, [rdi]
0x180053fa3  mov     rax, [rcx+0A0h]
0x180053faa  mov     rcx, rdi
0x180053fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fb2  mov     rcx, [rdi]
0x180053fb5  mov     rax, [rcx+0A0h]
0x180053fbc  mov     rcx, rdi
0x180053fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fc4  mov     [rsp+78h+var_58], r15d
0x180053fc9  mov     r9, r12
0x180053fcc  lea     r8, [rsp+78h+arg_0]
0x180053fd4  mov     edx, 2
0x180053fd9  mov     rcx, rdi
0x180053fdc  call    ?argumentsHelper@XPathParser@@AEAAXHPEAPEAVVector@@PEAVQuery@@W4Cardinality@BaseQuery@@@Z; XPathParser::argumentsHelper(int,Vector * *,Query *,BaseQuery::Cardinality)
0x180053fe1  mov     edx, r14d
0x180053fe4  mov     rcx, rbx
0x180053fe7  call    ?newComplexMethodOperand@ComplexMethodOperand@@SAPEAV1@PEAVVector@@W4ComplexMethodType@1@@Z; ComplexMethodOperand::newComplexMethodOperand(Vector *,ComplexMethodOperand::ComplexMethodType)
0x180053fec  mov     rbx, rax
0x180053fef  mov     edx, 29h ; ')'
0x180053ff4  mov     rcx, rdi
0x180053ff7  call    ?checkToken@XQLParser@@IEAAXW4xqlTokenType@@@Z; XQLParser::checkToken(xqlTokenType)
0x180053ffc  lea     rcx, [rbx+10h]
0x180054000  neg     rbx
0x180054003  sbb     rbx, rbx
0x180054006  and     rbx, rcx
0x180054009  test    r14b, r14b
0x18005400c  jz      loc_1800541DE
0x180054012  jmp     loc_1800541CC
0x180054017  mov     ecx, 4; int
0x18005401c  call    ?newVector@Vector@@SAPEAV1@HH@Z; Vector::newVector(int,int)
0x180054021  mov     r14, rax
0x180054024  mov     [rsp+78h+arg_18], rax
0x18005402c  mov     rdx, [rdi+50h]; struct Atom *
0x180054030  mov     rcx, [rdi+60h]; struct Atom *
0x180054034  call    ?create@Name@@SAPEAV1@PEAVAtom@@0@Z; Name::create(Atom *,Atom *)
0x180054039  mov     r13, rax
0x18005403c  mov     rcx, [rdi]
0x18005403f  mov     rax, [rcx+0A0h]
0x180054046  mov     rcx, rdi
0x180054049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005404e  mov     rcx, [rdi]
0x180054051  mov     rax, [rcx+0A0h]
0x180054058  mov     rcx, rdi
0x18005405b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054060  mov     [rsp+78h+var_58], r15d
0x180054065  mov     r9, r12
0x180054068  lea     r8, [rsp+78h+arg_18]
0x180054070  xor     edx, edx
0x180054072  mov     rcx, rdi
0x180054075  call    ?argumentsHelper@XPathParser@@AEAAXHPEAPEAVVector@@PEAVQuery@@W4Cardinality@BaseQuery@@@Z; XPathParser::argumentsHelper(int,Vector * *,Query *,BaseQuery::Cardinality)
0x18005407a  mov     rcx, [rdi+98h]
0x180054081  test    rcx, rcx
0x180054084  jnz     short loc_18005409F
0x180054086  mov     qword ptr [rsp+78h+var_58], rcx; unsigned __int16 *
0x18005408b  xor     r9d, r9d; unsigned __int16 *
0x18005408e  mov     r8, rbx; unsigned __int16 *
0x180054091  mov     edx, 0C00CE385h; int
0x180054096  mov     rcx, rdi; this
0x180054099  call    ?throwE@XQLParser@@IEAAXJPEBG00@Z; XQLParser::throwE(long,ushort const *,ushort const *,ushort const *)
0x18005409f  mov     rax, [rcx]
0x1800540a2  mov     r8, r14
0x1800540a5  mov     rdx, r13
0x1800540a8  mov     rax, [rax+8]
0x1800540ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540b1  mov     rbx, rax
0x1800540b4  mov     [rsp+78h+var_40], rax
0x1800540b9  jmp     loc_1800541CC
0x1800540be  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800540c4  call    cs:__imp_TlsGetValue
0x1800540ca  mov     rbx, rax
0x1800540cd  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800540d4  jnz     short loc_18005414F
0x1800540d6  call    cs:__imp__resetstkoflw
0x1800540dc  test    eax, eax
0x1800540de  jnz     short loc_180054131
0x1800540e0  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800540e7  test    rcx, rcx
0x1800540ea  jz      short loc_1800540FE
0x1800540ec  cmp     [rcx+50h], rbx
0x1800540f0  jnz     short loc_1800540FE
0x1800540f2  mov     rax, [rcx]
0x1800540f5  mov     rax, [rax+20h]
0x1800540f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540fe  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180054105  test    rcx, rcx
0x180054108  jz      short loc_18005411C
0x18005410a  cmp     [rcx+50h], rbx
0x18005410e  jnz     short loc_18005411C
  ... truncated ...
```
