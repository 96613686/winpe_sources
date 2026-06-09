# FveCreateSealedTpmData

- ea: `0x180119580`
- end: `0x180119a62`
- name: `FveCreateSealedTpmData`
- size: `1250`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18011d6f0`
- `0x18011ddc4`
- `0x18011e648`

## callees

- `0x18001b260`
- `0x18001ee3c`
- `0x180030060`
- `0x1800476f0`
- `0x180118c58`
- `0x180118d54`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`
- `0x180119580`
- `0x18011bea8`
- `0x180129010`

## string_xrefs

- `0x1801195a7`: `FveCreateSealedTpmData`
- `0x18011972b`: `FveCreateSealedTpmData`
- `0x1801197e7`: `FveCreateSealedTpmData`
- `0x180119875`: `FveCreateSealedTpmData`
- `0x180119a2c`: `FveCreateSealedTpmData`
- `0x1801195d7`: `minkernel\ngscb\cornerstone\fvevollib\tpmdatumscommon.c`
- `0x18011973c`: `minkernel\ngscb\cornerstone\fvevollib\tpmdatumscommon.c`
- `0x1801197f8`: `minkernel\ngscb\cornerstone\fvevollib\tpmdatumscommon.c`
- `0x180119886`: `minkernel\ngscb\cornerstone\fvevollib\tpmdatumscommon.c`
- `0x180119a38`: `minkernel\ngscb\cornerstone\fvevollib\tpmdatumscommon.c`

## pseudocode

```c
__int64 __fastcall FveCreateSealedTpmData(
        char a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        unsigned __int64 *a8,
        _QWORD *a9,
        _DWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _WORD *a13)
{
  __int64 v13; // rbx
  __int64 v16; // r15
  __int64 v17; // rdi
  int MustBe; // ebx
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, __int64, __int64, _QWORD, __int64); // rax
  __int64 v22; // r12
  __int64 (__fastcall *v23)(__int64, __int64, __int64, __int64, char *); // rax
  __int64 v24; // rdi
  bool v25; // al
  __int64 v26; // rcx
  int v27; // ecx
  unsigned __int16 i; // di
  unsigned __int16 v29; // si
  unsigned __int16 j; // r15
  __int64 v31; // rcx
  char v33; // [rsp+30h] [rbp-A1h]
  char *v34; // [rsp+30h] [rbp-A1h]
  char v35[4]; // [rsp+88h] [rbp-49h] BYREF
  __int16 v36; // [rsp+8Ch] [rbp-45h] BYREF
  _WORD v37[2]; // [rsp+90h] [rbp-41h] BYREF
  __int16 v38; // [rsp+94h] [rbp-3Dh]
  __int64 v39; // [rsp+98h] [rbp-39h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-31h]
  __int64 v41; // [rsp+A8h] [rbp-29h]
  __int64 v42; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-19h] BYREF
  int v44; // [rsp+C0h] [rbp-11h]
  __int64 v45; // [rsp+C8h] [rbp-9h]

  LOWORD(v13) = 0;
  v36 = 0;
  v40 = 0;
  *(_DWORD *)v35 = 0;
  v16 = 0;
  v39 = 0;
  v17 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v38 = 0;
  v41 = 0;
  v37[0] = 0;
  FveLibTraceEntryHelper("minkernel\\ngscb\\cornerstone\\fvevollib\\tpmdatumscommon.c", 128, "FveCreateSealedTpmData");
  if ( !a2 || !a8 || !a9 )
  {
    MustBe = -1073741811;
    goto LABEL_45;
  }
  *a9 = 0;
  if ( !a1 && (a11 || a12 || a13) )
    goto LABEL_8;
  if ( a4 )
  {
    MustBe = FveDatumMustBe(a4, 1);
    if ( MustBe < 0 )
      goto LABEL_47;
    MustBe = FveDatumGetDataSegment(a4, &v42, &v36);
    if ( MustBe < 0 )
      goto LABEL_47;
    v16 = v42;
    LOWORD(v13) = v36;
  }
  v13 = (unsigned __int16)v13;
  v45 = (unsigned __int16)v13;
  v42 = *a3;
  if ( a1 )
  {
    v20 = a6;
    v34 = v35;
    MustBe = FveLibTpmOperation(a5, 0, a2, v16, (unsigned __int16)v13);
    goto LABEL_18;
  }
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\tpmdatumscommon.c",
    208,
    (int)"FveCreateSealedTpmData",
    0,
    "Using Seal2",
    v33);
  v20 = a6;
  if ( qword_180174CE0
    && (v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, __int64))(qword_180174CE0 + 112)) != 0 )
  {
    v22 = a2 + 8;
    v34 = v35;
    MustBe = v21(a2, a5, v16, (unsigned __int16)v13, a2 + 8);
    if ( MustBe != -1073741702 )
    {
LABEL_18:
      if ( MustBe < 0 )
        goto LABEL_47;
      goto LABEL_25;
    }
    v13 = v45;
  }
  else
  {
    v22 = a2 + 8;
  }
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\tpmdatumscommon.c",
    225,
    (int)"FveCreateSealedTpmData",
    0,
    "Using Seal",
    (char)v34);
  if ( !qword_180174CE0
    || (v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, char *))(qword_180174CE0 + 24)) == 0 )
  {
    MustBe = -1073741702;
    goto LABEL_47;
  }
  LOBYTE(v34) = (_BYTE)a3;
  MustBe = v23(a5, v16, v13, v22, v35);
  if ( MustBe < 0 )
    goto LABEL_47;
LABEL_25:
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib\\tpmdatumscommon.c",
    265,
    (int)"FveCreateSealedTpmData",
    0,
    "Successfully sealed",
    (char)v34);
  if ( v40 > 0x200 )
  {
LABEL_8:
    MustBe = -1073741811;
    goto LABEL_47;
  }
  MustBe = FveDatumAllPurposeArrayCreate(v20, v40, 41, &v43);
  if ( MustBe >= 0 )
  {
    v24 = v39;
    v25 = 0;
    if ( !v39 || v35[0] >= 0 )
      goto LABEL_31;
    MustBe = FveLibIndexOfPcrInBitmap(*(unsigned int *)v35, 7, v37);
    if ( MustBe >= 0 )
    {
      v25 = (*(_BYTE *)(*(_QWORD *)(v24 + 8LL * v37[0]) + 6LL) & 4) != 0;
LABEL_31:
      v26 = v43;
      if ( v25 )
        *(_WORD *)(v43 + 6) |= 4u;
      *a8 = v40;
      *a9 = v26;
      if ( a10 )
        *a10 = *(_DWORD *)v35;
      if ( a11 )
      {
        *a11 = v39;
        v39 = 0;
      }
      if ( a13 )
        *a13 = v38;
      if ( a12 )
      {
        *a12 = v41;
        v41 = 0;
      }
      goto LABEL_47;
    }
  }
  v17 = v43;
LABEL_45:
  if ( v17 )
    FveDatumFree(v17);
LABEL_47:
  if ( v39 )
  {
    v27 = *(_DWORD *)v35;
    for ( i = 0; v27; v27 &= v27 - 1 )
      ++i;
    v29 = 0;
    for ( j = i; v29 < i; ++v29 )
    {
      v31 = *(_QWORD *)(v39 + 8LL * v29);
      if ( v31 )
      {
        FveDatumFree(v31);
        *(_QWORD *)(v39 + 8LL * v29) = 0;
      }
    }
    FveLibFreeWithTag(v39, 8LL * i, 2);
    v39 = 0;
  }
  else
  {
    j = v44;
  }
  if ( v41 )
  {
    FveLibFreeWithTag(v41, 68LL * j, 2);
    v41 = 0;
  }
  FveLibTraceExitHelper("minkernel\\ngscb\\cornerstone\\fvevollib\\tpmdatumscommon.c", 379, "FveCreateSealedTpmData");
  return (unsigned int)MustBe;
}

```

## disassembly

```asm
0x180119580  mov     rax, rsp
0x180119583  mov     [rax+8], rbx
0x180119587  mov     [rax+18h], r8
0x18011958b  mov     [rax+10h], rdx
0x18011958f  push    rbp
0x180119590  push    rsi
0x180119591  push    rdi
0x180119592  push    r12
0x180119594  push    r13
0x180119596  push    r14
0x180119598  push    r15
0x18011959a  lea     rbp, [rax-3Fh]
0x18011959e  sub     rsp, 0D0h
0x1801195a5  xor     ebx, ebx
0x1801195a7  lea     r8, aFvecreateseale; "FveCreateSealedTpmData"
0x1801195ae  xor     eax, eax
0x1801195b0  mov     [rbp+37h+var_7C], bx
0x1801195b4  mov     r14, rdx
0x1801195b7  mov     [rbp+37h+var_68], rbx
0x1801195bb  mov     r12b, cl
0x1801195be  mov     dword ptr [rbp+37h+var_80], ebx
0x1801195c1  xor     r15d, r15d
0x1801195c4  mov     [rbp+37h+var_70], rbx
0x1801195c8  xor     edi, edi
0x1801195ca  mov     [rbp+37h+var_58], r15
0x1801195ce  mov     edx, 80h
0x1801195d3  mov     [rbp+37h+var_50], rdi
0x1801195d7  lea     rcx, aMinkernelNgscb_26; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801195de  mov     [rbp+37h+var_48], ebx
0x1801195e1  mov     [rbp+37h+var_74], ax
0x1801195e5  mov     rsi, r9
0x1801195e8  mov     [rbp+37h+var_60], rax
0x1801195ec  mov     [rbp+37h+var_78], ax
0x1801195f0  mov     [rbp+37h+arg_30], al
0x1801195f3  call    FveLibTraceEntryHelper
0x1801195f8  test    r14, r14
0x1801195fb  jz      loc_18011997A
0x180119601  cmp     [rbp+37h+arg_38], rbx
0x180119605  jz      loc_18011997A
0x18011960b  mov     rax, [rbp+37h+arg_40]
0x180119612  test    rax, rax
0x180119615  jz      loc_18011997A
0x18011961b  mov     r13, [rbp+37h+arg_60]
0x180119622  mov     r14, [rbp+37h+arg_50]
0x180119629  mov     [rax], rbx
0x18011962c  test    r12b, r12b
0x18011962f  jnz     short loc_18011964E
0x180119631  test    r14, r14
0x180119634  jnz     short loc_180119644
0x180119636  cmp     [rbp+37h+arg_58], rbx
0x18011963d  jnz     short loc_180119644
0x18011963f  test    r13, r13
0x180119642  jz      short loc_18011964E
0x180119644  mov     ebx, 0C000000Dh
0x180119649  jmp     loc_18011998C
0x18011964e  test    rsi, rsi
0x180119651  jz      short loc_18011968C
0x180119653  mov     edx, 1
0x180119658  mov     rcx, rsi
0x18011965b  call    FveDatumMustBe
0x180119660  mov     ebx, eax
0x180119662  test    eax, eax
0x180119664  js      loc_18011998C
0x18011966a  lea     r8, [rbp+37h+var_7C]
0x18011966e  mov     rcx, rsi
0x180119671  lea     rdx, [rbp+37h+var_58]
0x180119675  call    FveDatumGetDataSegment
0x18011967a  mov     ebx, eax
0x18011967c  test    eax, eax
0x18011967e  js      loc_18011998C
0x180119684  mov     r15, [rbp+37h+var_58]
0x180119688  movzx   ebx, [rbp+37h+var_7C]
0x18011968c  mov     r8, qword ptr [rbp+37h+arg_10]
0x180119690  movzx   ebx, bx
0x180119693  mov     [rbp+37h+var_40], rbx
0x180119697  movzx   edx, word ptr [r8]
0x18011969b  mov     [rbp+37h+var_58], rdx
0x18011969f  test    r12b, r12b
0x1801196a2  jz      short loc_180119721
0x1801196a4  mov     rsi, [rbp+37h+arg_28]
0x1801196a8  mov     rax, r14
0x1801196ab  neg     rax
0x1801196ae  mov     edi, 200h
0x1801196b3  lea     rax, [rbp+37h+var_70]
0x1801196b7  mov     r9, r15
0x1801196ba  sbb     rcx, rcx
0x1801196bd  and     rcx, rax
0x1801196c0  lea     rax, [rbp+37h+arg_30]
0x1801196c4  mov     [rsp+70h], rax
0x1801196c9  lea     rax, [rbp+37h+var_74]
0x1801196cd  mov     [rsp+100h+var_98], rax
0x1801196d2  lea     rax, [rbp+37h+var_60]
0x1801196d6  mov     [rsp+100h+var_A0], rax
0x1801196db  lea     rax, [rbp+37h+var_68]
0x1801196df  mov     [rsp+100h+var_A8], rcx
0x1801196e4  mov     rcx, [rbp+37h+arg_20]
0x1801196e8  mov     [rsp+100h+var_B0], rax
0x1801196ed  lea     rax, [rbp+37h+var_80]
0x1801196f1  mov     [rsp+100h+var_B8], rdi
0x1801196f6  mov     [rsp+100h+var_C0], rsi
0x1801196fb  mov     [rsp+100h+var_C8], rdx
0x180119700  xor     edx, edx
0x180119702  mov     [rsp+100h+var_D0], r8
0x180119707  mov     r8, [rbp+37h+arg_8]
0x18011970b  mov     qword ptr [rsp+100h+var_D8], rax
0x180119710  mov     [rsp+100h+Format], rbx
0x180119715  call    FveLibTpmOperation
0x18011971a  mov     ebx, eax
0x18011971c  jmp     loc_1801197C2
0x180119721  lea     rax, aUsingSeal2; "Using Seal2"
0x180119728  xor     r9d, r9d; int
0x18011972b  lea     r8, aFvecreateseale; "FveCreateSealedTpmData"
0x180119732  mov     [rsp+100h+Format], rax; Format
0x180119737  mov     edx, 0D0h; int
0x18011973c  lea     rcx, aMinkernelNgscb_26; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x180119743  call    FveLibTraceHelper
0x180119748  mov     rax, cs:qword_180174CE0
0x18011974f  mov     edi, 200h
0x180119754  mov     rsi, [rbp+37h+arg_28]
0x180119758  test    rax, rax
0x18011975b  jz      short loc_1801197CF
0x18011975d  mov     rax, [rax+70h]
0x180119761  test    rax, rax
0x180119764  jz      short loc_1801197CF
0x180119766  mov     rcx, [rbp+37h+arg_8]
0x18011976a  lea     rdx, [rbp+37h+arg_30]
0x18011976e  mov     [rsp+100h+var_A8], rdx
0x180119773  mov     r9, rbx
0x180119776  lea     rdx, [rbp+37h+var_68]
0x18011977a  mov     r8, r15
0x18011977d  mov     [rsp+100h+var_B0], rdx
0x180119782  mov     rdx, [rbp+37h+var_58]
0x180119786  lea     r12, [rcx+8]
0x18011978a  mov     [rsp+100h+var_B8], rdi
0x18011978f  mov     [rsp+100h+var_C0], rsi
0x180119794  mov     [rsp+100h+var_C8], rdx
0x180119799  mov     rdx, qword ptr [rbp+37h+arg_10]
0x18011979d  mov     [rsp+100h+var_D0], rdx
0x1801197a2  lea     rdx, [rbp+37h+var_80]
0x1801197a6  mov     qword ptr [rsp+100h+var_D8], rdx; char
0x1801197ab  mov     rdx, [rbp+37h+arg_20]
0x1801197af  mov     [rsp+100h+Format], r12
0x1801197b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801197b9  mov     ebx, eax
0x1801197bb  cmp     eax, 0C000007Ah
0x1801197c0  jz      short loc_1801197D9
0x1801197c2  test    ebx, ebx
0x1801197c4  jns     loc_18011986B
0x1801197ca  jmp     loc_18011998C
0x1801197cf  mov     r12, [rbp+37h+arg_8]
0x1801197d3  add     r12, 8
0x1801197d7  jmp     short loc_1801197DD
0x1801197d9  mov     rbx, [rbp+37h+var_40]
0x1801197dd  lea     rax, aUsingSeal; "Using Seal"
0x1801197e4  xor     r9d, r9d; int
0x1801197e7  lea     r8, aFvecreateseale; "FveCreateSealedTpmData"
0x1801197ee  mov     [rsp+100h+Format], rax; Format
0x1801197f3  mov     edx, 0E1h; int
0x1801197f8  lea     rcx, aMinkernelNgscb_26; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x1801197ff  call    FveLibTraceHelper
0x180119804  mov     rax, cs:qword_180174CE0
0x18011980b  test    rax, rax
0x18011980e  jz      loc_180119973
0x180119814  mov     rax, [rax+18h]
0x180119818  test    rax, rax
0x18011981b  jz      loc_180119973
0x180119821  lea     rcx, [rbp+37h+var_68]
0x180119825  mov     r9, r12
0x180119828  mov     [rsp+100h+var_B8], rcx
0x18011982d  mov     r8, rbx
0x180119830  mov     rcx, [rbp+37h+var_58]
0x180119834  mov     rdx, r15
0x180119837  mov     [rsp+100h+var_C0], rdi
0x18011983c  mov     [rsp+100h+var_C8], rsi
0x180119841  mov     [rsp+100h+var_D0], rcx
0x180119846  mov     rcx, qword ptr [rbp+37h+arg_10]
0x18011984a  mov     qword ptr [rsp+100h+var_D8], rcx; char
0x18011984f  lea     rcx, [rbp+37h+var_80]
0x180119853  mov     [rsp+100h+Format], rcx
0x180119858  mov     rcx, [rbp+37h+arg_20]
0x18011985c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119861  mov     ebx, eax
0x180119863  test    eax, eax
0x180119865  js      loc_18011998C
0x18011986b  lea     rax, aSuccessfullySe; "Successfully sealed"
0x180119872  xor     r9d, r9d; int
0x180119875  lea     r8, aFvecreateseale; "FveCreateSealedTpmData"
0x18011987c  mov     [rsp+100h+Format], rax; Format
0x180119881  mov     edx, 109h; int
0x180119886  lea     rcx, aMinkernelNgscb_26; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18011988d  call    FveLibTraceHelper
0x180119892  mov     rdx, [rbp+37h+var_68]
0x180119896  cmp     rdx, rdi
0x180119899  ja      loc_180119644
0x18011989f  mov     r8d, 29h ; ')'
0x1801198a5  lea     r9, [rbp+37h+var_50]
0x1801198a9  mov     rcx, rsi
0x1801198ac  call    FveDatumAllPurposeArrayCreate
0x1801198b1  mov     ebx, eax
0x1801198b3  test    eax, eax
0x1801198b5  js      loc_18011996D
0x1801198bb  mov     rdi, [rbp+37h+var_70]
0x1801198bf  xor     al, al
0x1801198c1  test    rdi, rdi
0x1801198c4  jz      short loc_1801198F5
0x1801198c6  mov     ecx, dword ptr [rbp+37h+var_80]
0x1801198c9  test    cl, cl
0x1801198cb  jns     short loc_1801198F5
0x1801198cd  mov     edx, 7
0x1801198d2  lea     r8, [rbp+37h+var_78]
0x1801198d6  call    FveLibIndexOfPcrInBitmap
0x1801198db  mov     ebx, eax
0x1801198dd  test    eax, eax
0x1801198df  js      loc_18011996D
0x1801198e5  movzx   eax, [rbp+37h+var_78]
0x1801198e9  mov     rcx, [rdi+rax*8]
0x1801198ed  mov     al, [rcx+6]
0x1801198f0  shr     al, 2
0x1801198f3  and     al, 1
0x1801198f5  cmp     [rbp+37h+arg_30], 0
0x1801198f9  mov     rcx, [rbp+37h+var_50]
0x1801198fd  jnz     short loc_180119903
0x1801198ff  test    al, al
0x180119901  jz      short loc_180119908
0x180119903  or      word ptr [rcx+6], 4
0x180119908  mov     rax, [rbp+37h+var_68]
0x18011990c  mov     rdx, [rbp+37h+arg_38]
0x180119910  mov     [rdx], rax
0x180119913  mov     rax, [rbp+37h+arg_40]
0x18011991a  mov     [rax], rcx
0x18011991d  mov     rcx, [rbp+37h+arg_48]
0x180119924  test    rcx, rcx
0x180119927  jz      short loc_18011992E
0x180119929  mov     eax, dword ptr [rbp+37h+var_80]
0x18011992c  mov     [rcx], eax
0x18011992e  test    r14, r14
0x180119931  jz      short loc_180119942
0x180119933  mov     rax, [rbp+37h+var_70]
0x180119937  mov     [r14], rax
0x18011993a  mov     [rbp+37h+var_70], 0
0x180119942  test    r13, r13
0x180119945  jz      short loc_180119950
0x180119947  movzx   eax, [rbp+37h+var_74]
0x18011994b  mov     [r13+0], ax
0x180119950  mov     rcx, [rbp+37h+arg_58]
0x180119957  test    rcx, rcx
0x18011995a  jz      short loc_18011998C
0x18011995c  mov     rax, [rbp+37h+var_60]
0x180119960  mov     [rcx], rax
0x180119963  mov     [rbp+37h+var_60], 0
0x18011996b  jmp     short loc_18011998C
0x18011996d  mov     rdi, [rbp+37h+var_50]
0x180119971  jmp     short loc_18011997F
0x180119973  mov     ebx, 0C000007Ah
0x180119978  jmp     short loc_18011998C
0x18011997a  mov     ebx, 0C000000Dh
0x18011997f  test    rdi, rdi
0x180119982  jz      short loc_18011998C
0x180119984  mov     rcx, rdi
0x180119987  call    FveDatumFree
0x18011998c  cmp     [rbp+37h+var_70], 0
0x180119991  mov     r12d, 2
0x180119997  jz      short loc_180119A07
0x180119999  mov     ecx, dword ptr [rbp+37h+var_80]
0x18011999c  lea     r13d, [r12-1]
0x1801199a1  xor     edi, edi
0x1801199a3  test    ecx, ecx
0x1801199a5  jz      short loc_1801199B2
0x1801199a7  add     di, r13w
0x1801199ab  lea     eax, [rcx-1]
0x1801199ae  and     ecx, eax
0x1801199b0  jnz     short loc_1801199A7
0x1801199b2  xor     esi, esi
0x1801199b4  xor     eax, eax
0x1801199b6  movzx   r15d, di
0x1801199ba  cmp     ax, di
0x1801199bd  jnb     short loc_1801199EA
0x1801199bf  mov     rax, [rbp+37h+var_70]
0x1801199c3  movzx   r14d, si
0x1801199c7  mov     rcx, [rax+r14*8]
0x1801199cb  test    rcx, rcx
0x1801199ce  jz      short loc_1801199E1
0x1801199d0  call    FveDatumFree
0x1801199d5  mov     rax, [rbp+37h+var_70]
0x1801199d9  mov     qword ptr [rax+r14*8], 0
0x1801199e1  add     si, r13w
0x1801199e5  cmp     si, di
0x1801199e8  jb      short loc_1801199BF
0x1801199ea  mov     rcx, [rbp+37h+var_70]
0x1801199ee  mov     r8d, r12d
0x1801199f1  movzx   edx, di
0x1801199f4  shl     rdx, 3
0x1801199f8  call    FveLibFreeWithTag
0x1801199fd  mov     [rbp+37h+var_70], 0
0x180119a05  jmp     short loc_180119A0B
0x180119a07  mov     r15d, [rbp+37h+var_48]
0x180119a0b  mov     rcx, [rbp+37h+var_60]
0x180119a0f  test    rcx, rcx
0x180119a12  jz      short loc_180119A2C
0x180119a14  movzx   eax, r15w
  ... truncated ...
```
