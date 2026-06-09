# RegExpExec::ReplaceUsingCallable(CSession *,VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,void *,long (*)(void *,VAR *,int,VAR *))

- ea: `0x180008338`
- end: `0x180008953`
- name: `?ReplaceUsingCallable@RegExpExec@@IEAAJPEAVCSession@@PEAVVAR@@1PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAXP6AJ71H1@Z@Z`
- size: `1563`
- prototype: `__int64 __fastcall(_JBTYPE *this, struct CSession *, struct VAR *, struct VAR *, unsigned __int16 *, int, unsigned __int8 **, unsigned __int8 *Buf1, int, struct REGrpRange **, unsigned int, struct BuildString *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x180004a44`

## callees

- `0x180002e38`
- `0x1800082fc`
- `0x180008338`
- `0x18000895c`
- `0x1800089ec`
- `0x18000a500`
- `0x18000ad6c`
- `0x18000e788`
- `0x18000f1c0`
- `0x18000f430`
- `0x180010430`
- `0x180041c38`
- `0x18004b254`
- `0x1800576e0`
- `0x1800576ec`
- `0x180094276`
- `0x180094282`
- `0x18009429a`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x18000894b`
- `msvcrt!free` at `0x18000894b`
- `msvcrt!malloc` at `0x1800083e3`
- `msvcrt!malloc` at `0x1800083e3`
- `OLEAUT32!__imp_VariantInit` at `0x18000839b`
- `OLEAUT32!__imp_VariantInit` at `0x18000839b`

## pseudocode

```c
__int64 __fastcall RegExpExec::ReplaceUsingCallable(
        _JBTYPE *this,
        struct CSession *a2,
        struct VAR *a3,
        struct VAR *a4,
        unsigned __int16 *a5,
        int a6,
        unsigned __int8 **a7,
        unsigned __int8 *Buf1,
        int a9,
        struct REGrpRange **a10,
        unsigned int a11,
        struct BuildString *a12,
        void *a13)
{
  signed int v14; // r15d
  CIndexedNameList::IndexedEntry *v16; // rsi
  void *v17; // r12
  void *v18; // rdx
  int v19; // r8d
  int v20; // r9d
  void *v21; // rax
  struct REGrpRange *v22; // r13
  int v23; // ebx
  __int64 v24; // rbx
  CIndexedNameList::IndexedEntry *v25; // rax
  RegExpExec *v26; // rcx
  CIndexedNameList::IndexedEntry *v27; // rdi
  __int64 v28; // rax
  signed int j; // edx
  __int64 v30; // rdi
  int v31; // r8d
  _QWORD *k; // rdx
  int v33; // ebx
  int v34; // r15d
  int m; // edi
  struct VAR *v36; // r14
  const unsigned __int16 *v37; // rcx
  __int64 v38; // r13
  int v39; // ecx
  int v40; // ecx
  __int64 v41; // rbx
  struct CSession *v42; // rdi
  struct VAR *v43; // rax
  struct VAR *v44; // r15
  char *v45; // rdi
  size_t v46; // rbx
  int v47; // r14d
  unsigned int v48; // eax
  const unsigned __int16 *v49; // rcx
  int v50; // ecx
  int v51; // eax
  int v52; // [rsp+20h] [rbp-118h]
  struct VAR *p_pvarg; // [rsp+48h] [rbp-F0h] BYREF
  _QWORD *v54; // [rsp+50h] [rbp-E8h]
  int v55; // [rsp+58h] [rbp-E0h]
  int v56; // [rsp+5Ch] [rbp-DCh]
  int v57; // [rsp+60h] [rbp-D8h]
  int v58; // [rsp+64h] [rbp-D4h]
  struct REGrpRange *v59; // [rsp+68h] [rbp-D0h]
  int v60; // [rsp+70h] [rbp-C8h]
  __int64 v61; // [rsp+78h] [rbp-C0h]
  CIndexedNameList::IndexedEntry *i; // [rsp+80h] [rbp-B8h]
  __int64 v63; // [rsp+88h] [rbp-B0h]
  size_t Size; // [rsp+90h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+98h] [rbp-A0h] BYREF
  char v66[8]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v67; // [rsp+B8h] [rbp-80h]
  CIndexedNameList::IndexedEntry *v68; // [rsp+D0h] [rbp-68h]
  unsigned int v69; // [rsp+D8h] [rbp-60h]
  __int64 v70; // [rsp+DCh] [rbp-5Ch]
  void *v71; // [rsp+E8h] [rbp-50h]
  CIndexedNameList::IndexedEntry *v72; // [rsp+F0h] [rbp-48h]
  int v77; // [rsp+1A8h] [rbp+70h]

  p_pvarg = 0;
  v14 = a11 + 2;
  if ( a11 + 2 < a11 || (unsigned int)v14 > 0x7FFFFFFF )
    return 2147942934LL;
  v16 = 0;
  v77 = 0;
  v17 = 0;
  VariantInit(&pvarg);
  p_pvarg = 0;
  ScavVarList::ScavVarList((ScavVarList *)v66, v18, v19, v20, v52);
  if ( a9 <= 0 || !a7 && !MEMORY[0] )
  {
    v23 = -2147024809;
    goto LABEL_65;
  }
  Size = a9;
  v21 = malloc(a9);
  v17 = v21;
  v71 = v21;
  if ( !v21 )
    goto LABEL_61;
  memset_0(v21, 0, a9);
  memcpy_0(v17, *a7, a9);
  v22 = *a10;
  v59 = v22;
  v23 = RegExpExec::Exec(this, a5, a6, 0, Buf1, a9, v22);
  if ( v23 )
    goto LABEL_65;
  v24 = v14;
  v25 = (CIndexedNameList::IndexedEntry *)operator new[](saturated_mul(v14, 0x18u));
  v16 = v25;
  if ( v25 )
  {
    v61 = v14;
    v27 = v25;
    for ( i = v25; ; i = v27 )
    {
      v28 = v24--;
      v61 = v24;
      if ( !v28 )
        break;
      CIndexedNameList::IndexedEntry::IndexedEntry(v27);
      v27 = (CIndexedNameList::IndexedEntry *)((char *)v27 + 24);
    }
  }
  else
  {
    v16 = 0;
  }
  v72 = v16;
  if ( !v16 )
  {
LABEL_61:
    v23 = -2147024882;
    goto LABEL_65;
  }
  for ( j = 0; j < v14; ++j )
  {
    v26 = (RegExpExec *)(3LL * j);
    *((_WORD *)v16 + 12 * j) = 0;
  }
  LODWORD(v30) = 0;
  v58 = RegExpExec::FGlobal(v26, Buf1, 0);
  for ( k = (_QWORD *)((char *)a4 + 8); ; k = v54 )
  {
    v54 = k;
    v33 = *(_DWORD *)v22;
    v57 = v33;
    v56 = *((_DWORD *)v22 + 1);
    if ( (int)v30 < v33 )
    {
      BuildString::AppendSz(a12, (const unsigned __int16 *)(*k + 2LL * (int)v30), v33 - v30);
      k = v54;
      v31 = 0;
    }
    *(_OWORD *)v16 = *(_OWORD *)a3;
    *((_QWORD *)v16 + 2) = *((_QWORD *)a3 + 2);
    *((_WORD *)v16 + 12) = 3;
    *((_DWORD *)v16 + 8) = v33;
    v34 = 2;
    for ( m = a11 - 1; ; --m )
    {
      v55 = m;
      v36 = (CIndexedNameList::IndexedEntry *)((char *)v16 + 24 * v34);
      v37 = (const unsigned __int16 *)*k;
      v63 = *k;
      if ( m <= 0 )
        break;
      ++v34;
      v23 = PvarAllocFromSubstr(a2, (struct REGrpRange *)((char *)v22 + 8 * m), v37, v36);
      v31 = 0;
      if ( v23 < 0 )
        goto LABEL_65;
      k = v54;
    }
    v38 = *(int *)v22;
    v39 = *((_DWORD *)v59 + 1);
    *(_WORD *)v36 = v31;
    if ( (_DWORD)v38 != -1 || v39 != -1 )
    {
      v40 = v39 - v38;
      if ( v40 < 0 || (v41 = v40, (unsigned __int64)v40 > 0x3FFFFFFF) )
      {
        v23 = -2147024882;
        goto LABEL_28;
      }
      if ( v40 )
      {
        v42 = a2;
        v43 = PvarAllocBstrLen(v40, a2);
        v44 = v43;
        if ( !v43 )
        {
          v23 = -2147024882;
          goto LABEL_29;
        }
        v45 = (char *)*((_QWORD *)v43 + 1);
        v46 = 2 * v41;
        memcpy_0(v45, (const void *)(v63 + 2 * v38), v46);
        v31 = 0;
        *(_WORD *)&v45[v46] = 0;
        *(_WORD *)v36 = 128;
        *((_QWORD *)v36 + 1) = v44;
      }
      else
      {
        *(_WORD *)v36 = 128;
        *((_QWORD *)v36 + 1) = &cbstrEmpty;
      }
    }
    v23 = v31;
LABEL_28:
    v42 = a2;
LABEL_29:
    if ( v23 < 0 )
      goto LABEL_65;
    v68 = v16;
    v47 = a11;
    v69 = a11 + 2;
    v70 = 24;
    if ( (int)(a11 + 2) > 0 )
      IScavengerBase::LinkToGc((IScavengerBase *)v66);
    else
      IScavengerBase::UnlinkFromGc((IScavengerBase *)v66);
    v23 = RegExpExec::CallEntryPoint(a13, (struct VAR *)&pvarg, a11 + 2, v16);
    if ( v23 < 0 )
      goto LABEL_65;
    if ( pvarg.vt )
    {
      p_pvarg = (struct VAR *)&pvarg;
      v23 = ConvertToString(v42, &p_pvarg, (struct VAR *)&pvarg, 1);
      if ( v23 < 0 )
        goto LABEL_65;
      v48 = CbBstr(*((const unsigned __int16 **)p_pvarg + 1));
      BuildString::AppendSz(a12, v49, v48 >> 1);
    }
    if ( !Buf1 || *a7 != Buf1 || memcmp_0(Buf1, v17, Size) )
    {
      v23 = -2147467259;
      goto LABEL_65;
    }
    v50 = v56;
    v30 = v56;
    if ( v56 <= v57 )
      v50 = v57 + 1;
    if ( !v58 || v50 > a6 )
      goto LABEL_47;
    v77 = 1 - v77;
    v51 = RegExpExec::Exec(this, a5, a6, v50, Buf1, a9, a10[v77]);
    v23 = v51;
    v31 = 0;
    if ( v51 )
      break;
    v60 = v77;
    v22 = a10[v77];
    v59 = v22;
  }
  if ( v51 < 0 )
    goto LABEL_65;
  v47 = a11;
LABEL_47:
  if ( (int)v30 < a6 )
    BuildString::AppendSz(a12, (const unsigned __int16 *)(*v54 + 2 * v30), a6 - v30);
  if ( v59 != *a10 )
    memcpy_0(*a10, a10[1], 8LL * v47);
  v23 = 0;
LABEL_65:
  if ( v16 )
    operator delete[](v16);
  if ( v67 && (*(_BYTE *)(v67 + 12) & 8) == 0 )
    IScavengerBase::Close((IScavengerBase *)v66);
  if ( v17 )
    free(v17);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180008338  mov     [rsp+arg_10], r8
0x18000833d  mov     [rsp+arg_8], rdx
0x180008342  mov     [rsp+Buf], rcx
0x180008347  push    rbx
0x180008348  push    rsi
0x180008349  push    rdi
0x18000834a  push    r12
0x18000834c  push    r13
0x18000834e  push    r14
0x180008350  push    r15
0x180008352  sub     rsp, 100h
0x180008359  mov     r14, r9
0x18000835c  xor     ebx, ebx
0x18000835e  mov     [rsp+138h+var_F0], rbx
0x180008363  mov     eax, [rsp+138h+arg_50]
0x18000836a  lea     r15d, [rax+2]
0x18000836e  cmp     r15d, eax
0x180008371  jb      short loc_18000837C
0x180008373  cmp     r15d, 7FFFFFFFh
0x18000837a  jbe     short loc_180008386
0x18000837c  mov     eax, 80070216h
0x180008381  jmp     loc_18000891C
0x180008386  mov     rsi, rbx
0x180008389  mov     dword ptr [rsp+138h+arg_68], ebx
0x180008390  mov     r12, rbx
0x180008393  lea     rcx, [rsp+138h+pvarg]; pvarg
0x18000839b  call    cs:__imp_VariantInit
0x1800083a1  mov     [rsp+138h+var_F0], rbx
0x1800083a6  lea     rcx, [rsp+138h+var_88]; this
0x1800083ae  call    ??0ScavVarList@@QEAA@PEAXJJJ@Z; ScavVarList::ScavVarList(void *,long,long,long)
0x1800083b3  nop
0x1800083b4  movsxd  rdi, [rsp+138h+arg_40]
0x1800083bc  xor     r8d, r8d
0x1800083bf  test    edi, edi
0x1800083c1  jle     loc_1800088CD
0x1800083c7  mov     rbx, [rsp+138h+arg_30]
0x1800083cf  test    rbx, rbx
0x1800083d2  jz      loc_1800088C4
0x1800083d8  mov     [rsp+138h+Size], rdi
0x1800083e0  mov     rcx, rdi; Size
0x1800083e3  call    cs:__imp_malloc
0x1800083e9  mov     r12, rax
0x1800083ec  mov     [rsp+138h+var_50], rax
0x1800083f4  test    rax, rax
0x1800083f7  jz      loc_1800088D4
0x1800083fd  mov     r8, rdi; Size
0x180008400  xor     edx, edx; Val
0x180008402  mov     rcx, rax; void *
0x180008405  call    memset_0
0x18000840a  mov     r8, rdi; Size
0x18000840d  mov     rdx, [rbx]; Src
0x180008410  mov     rcx, r12; void *
0x180008413  call    memcpy_0
0x180008418  mov     r13, [rsp+138h+arg_48]
0x180008420  mov     r13, [r13+0]
0x180008424  mov     [rsp+138h+var_D0], r13
0x180008429  mov     [rsp+138h+var_108], r13; struct REGrpRange *
0x18000842e  mov     [rsp+138h+var_110], edi; int
0x180008432  mov     rax, [rsp+138h+Buf1]
0x18000843a  mov     [rsp+138h+var_118], rax; unsigned __int8 *
0x18000843f  xor     r9d, r9d; int
0x180008442  mov     r8d, [rsp+138h+arg_28]; int
0x18000844a  mov     rdx, [rsp+138h+arg_20]; unsigned __int16 *
0x180008452  mov     rcx, [rsp+138h+Buf]; Buf
0x18000845a  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18000845f  mov     ebx, eax
0x180008461  test    eax, eax
0x180008463  jnz     loc_1800088FD
0x180008469  movsxd  rbx, r15d
0x18000846c  mov     eax, 18h
0x180008471  mul     rbx
0x180008474  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000847b  cmovb   rax, rcx
0x18000847f  mov     rcx, rax; unsigned __int64
0x180008482  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180008487  mov     rsi, rax
0x18000848a  xor     r8d, r8d; int
0x18000848d  test    rax, rax
0x180008490  jz      short loc_1800084CB
0x180008492  mov     [rsp+138h+var_C0], rbx
0x180008497  mov     rdi, rax
0x18000849a  mov     [rsp+138h+var_B8], rax
0x1800084a2  mov     rax, rbx
0x1800084a5  dec     rbx
0x1800084a8  mov     [rsp+138h+var_C0], rbx
0x1800084ad  test    rax, rax
0x1800084b0  jz      short loc_1800084CE
0x1800084b2  mov     rcx, rdi; this
0x1800084b5  call    ??0IndexedEntry@CIndexedNameList@@QEAA@XZ; CIndexedNameList::IndexedEntry::IndexedEntry(void)
0x1800084ba  add     rdi, 18h
0x1800084be  mov     [rsp+138h+var_B8], rdi
0x1800084c6  xor     r8d, r8d
0x1800084c9  jmp     short loc_1800084A2
0x1800084cb  mov     rsi, r8
0x1800084ce  mov     [rsp+138h+var_48], rsi
0x1800084d6  test    rsi, rsi
0x1800084d9  jz      loc_1800088D4
0x1800084df  mov     edx, r8d
0x1800084e2  mov     [rsp+138h+var_F8], edx
0x1800084e6  cmp     edx, r15d
0x1800084e9  jl      loc_1800088DB
0x1800084ef  mov     edi, r8d
0x1800084f2  mov     rdx, [rsp+138h+Buf1]; unsigned __int8 *
0x1800084fa  call    ?FGlobal@RegExpExec@@QEAAHPEAEJ@Z; RegExpExec::FGlobal(uchar *,long)
0x1800084ff  mov     [rsp+138h+var_D4], eax
0x180008503  lea     rdx, [r14+8]
0x180008507  mov     [rsp+138h+var_E8], rdx
0x18000850c  mov     ebx, [r13+0]
0x180008510  mov     [rsp+138h+var_D8], ebx
0x180008514  mov     ecx, [r13+4]
0x180008518  mov     [rsp+138h+var_DC], ecx
0x18000851c  cmp     edi, ebx
0x18000851e  jge     short loc_180008545
0x180008520  mov     r8d, ebx
0x180008523  sub     r8d, edi; int
0x180008526  movsxd  rcx, edi
0x180008529  mov     rax, [rdx]
0x18000852c  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x180008530  mov     rcx, [rsp+138h+arg_58]; this
0x180008538  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18000853d  mov     rdx, [rsp+138h+var_E8]
0x180008542  xor     r8d, r8d
0x180008545  mov     rax, [rsp+138h+arg_10]
0x18000854d  movups  xmm0, xmmword ptr [rax]
0x180008550  movups  xmmword ptr [rsi], xmm0
0x180008553  movsd   xmm1, qword ptr [rax+10h]
0x180008558  movsd   qword ptr [rsi+10h], xmm1
0x18000855d  mov     eax, 3
0x180008562  mov     [rsi+18h], ax
0x180008566  mov     [rsi+20h], ebx
0x180008569  lea     r15d, [rax-1]
0x18000856d  mov     [rsp+138h+var_F8], r15d
0x180008572  mov     edi, [rsp+138h+arg_50]
0x180008579  dec     edi
0x18000857b  mov     [rsp+138h+var_E0], edi
0x18000857f  movsxd  rax, r15d
0x180008582  lea     rcx, [rax+rax*2]
0x180008586  lea     r14, [rsi+rcx*8]
0x18000858a  mov     rcx, [rdx]
0x18000858d  mov     [rsp+138h+var_B0], rcx
0x180008595  test    edi, edi
0x180008597  jg      loc_18000886D
0x18000859d  movsxd  r13, dword ptr [r13+0]
0x1800085a1  mov     rcx, [rsp+138h+var_D0]
0x1800085a6  mov     ecx, [rcx+4]
0x1800085a9  mov     [r14], r8w
0x1800085ad  cmp     r13d, 0FFFFFFFFh
0x1800085b1  jz      loc_180008855
0x1800085b7  sub     ecx, r13d; int
0x1800085ba  js      loc_1800088EE
0x1800085c0  movsxd  rbx, ecx
0x1800085c3  cmp     rbx, 3FFFFFFFh
0x1800085ca  ja      loc_1800088EE
0x1800085d0  test    ecx, ecx
0x1800085d2  jz      loc_1800088AB
0x1800085d8  mov     rdi, [rsp+138h+arg_8]
0x1800085e0  mov     rdx, rdi; struct CSession *
0x1800085e3  call    ?PvarAllocBstrLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrLen(long,CSession *)
0x1800085e8  mov     r15, rax
0x1800085eb  test    rax, rax
0x1800085ee  jz      loc_18000884B
0x1800085f4  mov     rdi, [rax+8]
0x1800085f8  add     rbx, rbx
0x1800085fb  mov     rcx, [rsp+138h+var_B0]
0x180008603  lea     rdx, [rcx+r13*2]; Src
0x180008607  mov     r8, rbx; Size
0x18000860a  mov     rcx, rdi; void *
0x18000860d  call    memcpy_0
0x180008612  xor     r8d, r8d
0x180008615  mov     [rbx+rdi], r8w
0x18000861a  mov     eax, 80h
0x18000861f  mov     [r14], ax
0x180008623  mov     [r14+8], r15
0x180008627  mov     ebx, r8d
0x18000862a  mov     rdi, [rsp+138h+arg_8]
0x180008632  test    ebx, ebx
0x180008634  js      loc_1800088FD
0x18000863a  mov     [rsp+138h+var_68], rsi
0x180008642  mov     r14d, [rsp+138h+arg_50]
0x18000864a  lea     r15d, [r14+2]
0x18000864e  mov     [rsp+138h+var_60], r15d
0x180008656  mov     [rsp+138h+var_5C], 18h
0x180008662  lea     rcx, [rsp+138h+var_88]; this
0x18000866a  test    r15d, r15d
0x18000866d  jg      loc_180008863
0x180008673  call    ?UnlinkFromGc@IScavengerBase@@QEAAXXZ; IScavengerBase::UnlinkFromGc(void)
0x180008678  mov     r9, rsi
0x18000867b  mov     r8d, r15d
0x18000867e  lea     rdx, [rsp+138h+pvarg]
0x180008686  mov     rcx, [rsp+138h+arg_60]
0x18000868e  lea     rax, ?CallEntryPoint@RegExpExec@@KAJPEAXPEAVVAR@@H1@Z; RegExpExec::CallEntryPoint(void *,VAR *,int,VAR *)
0x180008695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000869a  mov     ebx, eax
0x18000869c  xor     r8d, r8d
0x18000869f  test    eax, eax
0x1800086a1  js      loc_1800088FD
0x1800086a7  cmp     word ptr [rsp+138h+pvarg], r8w
0x1800086b0  jz      short loc_180008705
0x1800086b2  lea     rax, [rsp+138h+pvarg]
0x1800086ba  mov     [rsp+138h+var_F0], rax
0x1800086bf  lea     r9d, [r8+1]; int
0x1800086c3  lea     r8, [rsp+138h+pvarg]; struct VAR *
0x1800086cb  lea     rdx, [rsp+138h+var_F0]; struct VAR **
0x1800086d0  mov     rcx, rdi; struct CSession *
0x1800086d3  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x1800086d8  mov     ebx, eax
0x1800086da  test    eax, eax
0x1800086dc  js      loc_1800088FD
0x1800086e2  mov     rax, [rsp+138h+var_F0]
0x1800086e7  mov     rcx, [rax+8]; unsigned __int16 *
0x1800086eb  call    ?CbBstr@@YAKPEBG@Z; CbBstr(ushort const *)
0x1800086f0  shr     eax, 1
0x1800086f2  mov     r8d, eax; int
0x1800086f5  mov     rdx, rcx; unsigned __int16 *
0x1800086f8  mov     rcx, [rsp+138h+arg_58]; this
0x180008700  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180008705  mov     rbx, [rsp+138h+Buf1]
0x18000870d  test    rbx, rbx
0x180008710  jz      loc_1800088F8
0x180008716  mov     rax, [rsp+138h+arg_30]
0x18000871e  cmp     [rax], rbx
0x180008721  jnz     loc_1800088F8
0x180008727  mov     r8, [rsp+138h+Size]; Size
0x18000872f  mov     rdx, r12; Buf2
0x180008732  mov     rcx, rbx; Buf1
0x180008735  call    memcmp_0
0x18000873a  xor     r8d, r8d
0x18000873d  test    eax, eax
0x18000873f  jnz     loc_1800088F8
0x180008745  movsxd  rcx, [rsp+138h+var_DC]
0x18000874a  mov     rdi, rcx
0x18000874d  mov     eax, [rsp+138h+var_D8]
0x180008751  cmp     ecx, eax
0x180008753  jg      short loc_180008758
0x180008755  lea     ecx, [rax+1]
0x180008758  mov     r15d, [rsp+138h+arg_28]
0x180008760  mov     r13, [rsp+138h+arg_48]
0x180008768  cmp     [rsp+138h+var_D4], r8d
0x18000876d  jz      loc_1800087FD
0x180008773  cmp     ecx, r15d
0x180008776  jg      loc_1800087FD
0x18000877c  mov     eax, 1
0x180008781  sub     eax, dword ptr [rsp+138h+arg_68]
0x180008788  mov     dword ptr [rsp+138h+arg_68], eax
0x18000878f  movsxd  r14, eax
0x180008792  mov     rax, [r13+r14*8+0]
0x180008797  mov     [rsp+138h+var_108], rax; struct REGrpRange *
0x18000879c  mov     eax, [rsp+138h+arg_40]
0x1800087a3  mov     [rsp+138h+var_110], eax; int
0x1800087a7  mov     [rsp+138h+var_118], rbx; unsigned __int8 *
0x1800087ac  mov     r9d, ecx; int
0x1800087af  mov     r8d, r15d; int
0x1800087b2  mov     rdx, [rsp+138h+arg_20]; unsigned __int16 *
0x1800087ba  mov     rcx, [rsp+138h+Buf]; Buf
0x1800087c2  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x1800087c7  mov     ebx, eax
0x1800087c9  xor     r8d, r8d
0x1800087cc  test    eax, eax
0x1800087ce  jnz     short loc_1800087EF
0x1800087d0  mov     eax, dword ptr [rsp+138h+arg_68]
0x1800087d7  mov     [rsp+138h+var_C8], eax
0x1800087db  mov     r13, [r13+r14*8+0]
0x1800087e0  mov     [rsp+138h+var_D0], r13
0x1800087e5  mov     rdx, [rsp+138h+var_E8]
0x1800087ea  jmp     loc_180008507
0x1800087ef  js      loc_1800088FD
0x1800087f5  mov     r14d, [rsp+138h+arg_50]
0x1800087fd  cmp     edi, r15d
0x180008800  jge     short loc_180008821
0x180008802  sub     r15d, edi
0x180008805  mov     rax, [rsp+138h+var_E8]
0x18000880a  mov     rax, [rax]
0x18000880d  lea     rdx, [rax+rdi*2]; unsigned __int16 *
0x180008811  mov     r8d, r15d; int
0x180008814  mov     rcx, [rsp+138h+arg_58]; this
0x18000881c  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180008821  mov     rax, [rsp+138h+var_D0]
0x180008826  cmp     rax, [r13+0]
0x18000882a  jz      short loc_180008840
0x18000882c  movsxd  r8, r14d
0x18000882f  shl     r8, 3; Size
0x180008833  mov     rdx, [r13+8]; Src
0x180008837  mov     rcx, [r13+0]; void *
0x18000883b  call    memcpy_0
0x180008840  xor     r8d, r8d
0x180008843  mov     ebx, r8d
0x180008846  jmp     loc_1800088FD
0x18000884b  mov     ebx, 8007000Eh
0x180008850  jmp     loc_180008632
0x180008855  cmp     ecx, 0FFFFFFFFh
0x180008858  jz      loc_180008627
0x18000885e  jmp     loc_1800085B7
0x180008863  call    ?LinkToGc@IScavengerBase@@QEAAXXZ; IScavengerBase::LinkToGc(void)
0x180008868  jmp     loc_180008678
0x18000886d  inc     r15d
0x180008870  mov     [rsp+138h+var_F8], r15d
0x180008875  movsxd  rax, edi
0x180008878  lea     rdx, ds:0[rax*8]
0x180008880  add     rdx, r13; struct REGrpRange *
0x180008883  mov     r9, r14; struct VAR *
  ... truncated ...
```
