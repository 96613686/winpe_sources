# RegExpExec::ReplaceUsingCallable(CSession *,VAR *,VAR *,ushort *,long,uchar * *,uchar *,long,REGrpRange * *,int,BuildString *,void *,long (*)(void *,VAR *,int,VAR *))

- ea: `0x180034f48`
- end: `0x180035576`
- name: `?ReplaceUsingCallable@RegExpExec@@IEAAJPEAVCSession@@PEAVVAR@@1PEAGJPEAPEAEPEAEJPEAPEAUREGrpRange@@HPEAVBuildString@@PEAXP6AJ71H1@Z@Z`
- size: `1582`
- prototype: `__int64 __fastcall(_JBTYPE *this, struct CSession *, struct VAR *, struct VAR *, unsigned __int16 *, int, unsigned __int8 **, unsigned __int8 *Buf1, int, struct REGrpRange **, unsigned int, struct BuildString *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update`

## callers

- `0x1800328b0`

## callees

- `0x1800064ac`
- `0x1800075bc`
- `0x180007e9c`
- `0x18000a35c`
- `0x18000b9ac`
- `0x18000c430`
- `0x18000c6a0`
- `0x18000d6a0`
- `0x180034f48`
- `0x18003557c`
- `0x18003560c`
- `0x180036bcc`
- `0x18004b3a0`
- `0x180058610`
- `0x18005861c`
- `0x180096686`
- `0x180096692`
- `0x1800966aa`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x180035568`
- `msvcrt!free` at `0x180035568`
- `msvcrt!malloc` at `0x180034ff9`
- `msvcrt!malloc` at `0x180034ff9`
- `OLEAUT32!__imp_VariantInit` at `0x180034fab`
- `OLEAUT32!__imp_VariantInit` at `0x180034fab`

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
      v23 = ConvertToString(v42, (struct IDispatch ***)&p_pvarg, &pvarg, 1);
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
0x180034f48  mov     [rsp+arg_10], r8
0x180034f4d  mov     [rsp+arg_8], rdx
0x180034f52  mov     [rsp+Buf], rcx
0x180034f57  push    rbx
0x180034f58  push    rsi
0x180034f59  push    rdi
0x180034f5a  push    r12
0x180034f5c  push    r13
0x180034f5e  push    r14
0x180034f60  push    r15
0x180034f62  sub     rsp, 100h
0x180034f69  mov     r14, r9
0x180034f6c  xor     ebx, ebx
0x180034f6e  mov     [rsp+138h+var_F0], rbx
0x180034f73  mov     eax, [rsp+138h+arg_50]
0x180034f7a  lea     r15d, [rax+2]
0x180034f7e  cmp     r15d, eax
0x180034f81  jb      short loc_180034F8C
0x180034f83  cmp     r15d, 7FFFFFFFh
0x180034f8a  jbe     short loc_180034F96
0x180034f8c  mov     eax, 80070216h
0x180034f91  jmp     loc_180035538
0x180034f96  mov     rsi, rbx
0x180034f99  mov     dword ptr [rsp+138h+arg_68], ebx
0x180034fa0  mov     r12, rbx
0x180034fa3  lea     rcx, [rsp+138h+pvarg]; pvarg
0x180034fab  call    cs:__imp_VariantInit
0x180034fb2  nop     dword ptr [rax+rax+00h]
0x180034fb7  mov     [rsp+138h+var_F0], rbx
0x180034fbc  lea     rcx, [rsp+138h+var_88]; this
0x180034fc4  call    ??0ScavVarList@@QEAA@PEAXJJJ@Z; ScavVarList::ScavVarList(void *,long,long,long)
0x180034fc9  nop
0x180034fca  movsxd  rdi, [rsp+138h+arg_40]
0x180034fd2  xor     r8d, r8d
0x180034fd5  test    edi, edi
0x180034fd7  jle     loc_1800354E9
0x180034fdd  mov     rbx, [rsp+138h+arg_30]
0x180034fe5  test    rbx, rbx
0x180034fe8  jz      loc_1800354E0
0x180034fee  mov     [rsp+138h+Size], rdi
0x180034ff6  mov     rcx, rdi; Size
0x180034ff9  call    cs:__imp_malloc
0x180035000  nop     dword ptr [rax+rax+00h]
0x180035005  mov     r12, rax
0x180035008  mov     [rsp+138h+var_50], rax
0x180035010  test    rax, rax
0x180035013  jz      loc_1800354F0
0x180035019  mov     r8, rdi; Size
0x18003501c  xor     edx, edx; Val
0x18003501e  mov     rcx, rax; void *
0x180035021  call    memset_0
0x180035026  mov     r8, rdi; Size
0x180035029  mov     rdx, [rbx]; Src
0x18003502c  mov     rcx, r12; void *
0x18003502f  call    memcpy_0
0x180035034  mov     r13, [rsp+138h+arg_48]
0x18003503c  mov     r13, [r13+0]
0x180035040  mov     [rsp+138h+var_D0], r13
0x180035045  mov     [rsp+138h+var_108], r13; struct REGrpRange *
0x18003504a  mov     [rsp+138h+var_110], edi; int
0x18003504e  mov     rax, [rsp+138h+Buf1]
0x180035056  mov     [rsp+138h+var_118], rax; unsigned __int8 *
0x18003505b  xor     r9d, r9d; int
0x18003505e  mov     r8d, [rsp+138h+arg_28]; int
0x180035066  mov     rdx, [rsp+138h+arg_20]; unsigned __int16 *
0x18003506e  mov     rcx, [rsp+138h+Buf]; Buf
0x180035076  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x18003507b  mov     ebx, eax
0x18003507d  test    eax, eax
0x18003507f  jnz     loc_180035519
0x180035085  movsxd  rbx, r15d
0x180035088  mov     eax, 18h
0x18003508d  mul     rbx
0x180035090  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180035097  cmovb   rax, rcx
0x18003509b  mov     rcx, rax; unsigned __int64
0x18003509e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800350a3  mov     rsi, rax
0x1800350a6  xor     r8d, r8d; int
0x1800350a9  test    rax, rax
0x1800350ac  jz      short loc_1800350E7
0x1800350ae  mov     [rsp+138h+var_C0], rbx
0x1800350b3  mov     rdi, rax
0x1800350b6  mov     [rsp+138h+var_B8], rax
0x1800350be  mov     rax, rbx
0x1800350c1  dec     rbx
0x1800350c4  mov     [rsp+138h+var_C0], rbx
0x1800350c9  test    rax, rax
0x1800350cc  jz      short loc_1800350EA
0x1800350ce  mov     rcx, rdi; this
0x1800350d1  call    ??0IndexedEntry@CIndexedNameList@@QEAA@XZ; CIndexedNameList::IndexedEntry::IndexedEntry(void)
0x1800350d6  add     rdi, 18h
0x1800350da  mov     [rsp+138h+var_B8], rdi
0x1800350e2  xor     r8d, r8d
0x1800350e5  jmp     short loc_1800350BE
0x1800350e7  mov     rsi, r8
0x1800350ea  mov     [rsp+138h+var_48], rsi
0x1800350f2  test    rsi, rsi
0x1800350f5  jz      loc_1800354F0
0x1800350fb  mov     edx, r8d
0x1800350fe  mov     [rsp+138h+var_F8], edx
0x180035102  cmp     edx, r15d
0x180035105  jl      loc_1800354F7
0x18003510b  mov     edi, r8d
0x18003510e  mov     rdx, [rsp+138h+Buf1]; unsigned __int8 *
0x180035116  call    ?FGlobal@RegExpExec@@QEAAHPEAEJ@Z; RegExpExec::FGlobal(uchar *,long)
0x18003511b  mov     [rsp+138h+var_D4], eax
0x18003511f  lea     rdx, [r14+8]
0x180035123  mov     [rsp+138h+var_E8], rdx
0x180035128  mov     ebx, [r13+0]
0x18003512c  mov     [rsp+138h+var_D8], ebx
0x180035130  mov     ecx, [r13+4]
0x180035134  mov     [rsp+138h+var_DC], ecx
0x180035138  cmp     edi, ebx
0x18003513a  jge     short loc_180035161
0x18003513c  mov     r8d, ebx
0x18003513f  sub     r8d, edi; int
0x180035142  movsxd  rcx, edi
0x180035145  mov     rax, [rdx]
0x180035148  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18003514c  mov     rcx, [rsp+138h+arg_58]; this
0x180035154  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180035159  mov     rdx, [rsp+138h+var_E8]
0x18003515e  xor     r8d, r8d
0x180035161  mov     rax, [rsp+138h+arg_10]
0x180035169  movups  xmm0, xmmword ptr [rax]
0x18003516c  movups  xmmword ptr [rsi], xmm0
0x18003516f  movsd   xmm1, qword ptr [rax+10h]
0x180035174  movsd   qword ptr [rsi+10h], xmm1
0x180035179  mov     eax, 3
0x18003517e  mov     [rsi+18h], ax
0x180035182  mov     [rsi+20h], ebx
0x180035185  lea     r15d, [rax-1]
0x180035189  mov     [rsp+138h+var_F8], r15d
0x18003518e  mov     edi, [rsp+138h+arg_50]
0x180035195  dec     edi
0x180035197  mov     [rsp+138h+var_E0], edi
0x18003519b  movsxd  rax, r15d
0x18003519e  lea     rcx, [rax+rax*2]
0x1800351a2  lea     r14, [rsi+rcx*8]
0x1800351a6  mov     rcx, [rdx]
0x1800351a9  mov     [rsp+138h+var_B0], rcx
0x1800351b1  test    edi, edi
0x1800351b3  jg      loc_180035489
0x1800351b9  movsxd  r13, dword ptr [r13+0]
0x1800351bd  mov     rcx, [rsp+138h+var_D0]
0x1800351c2  mov     ecx, [rcx+4]
0x1800351c5  mov     [r14], r8w
0x1800351c9  cmp     r13d, 0FFFFFFFFh
0x1800351cd  jz      loc_180035471
0x1800351d3  sub     ecx, r13d; int
0x1800351d6  js      loc_18003550A
0x1800351dc  movsxd  rbx, ecx
0x1800351df  cmp     rbx, 3FFFFFFFh
0x1800351e6  ja      loc_18003550A
0x1800351ec  test    ecx, ecx
0x1800351ee  jz      loc_1800354C7
0x1800351f4  mov     rdi, [rsp+138h+arg_8]
0x1800351fc  mov     rdx, rdi; struct CSession *
0x1800351ff  call    ?PvarAllocBstrLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrLen(long,CSession *)
0x180035204  mov     r15, rax
0x180035207  test    rax, rax
0x18003520a  jz      loc_180035467
0x180035210  mov     rdi, [rax+8]
0x180035214  add     rbx, rbx
0x180035217  mov     rcx, [rsp+138h+var_B0]
0x18003521f  lea     rdx, [rcx+r13*2]; Src
0x180035223  mov     r8, rbx; Size
0x180035226  mov     rcx, rdi; void *
0x180035229  call    memcpy_0
0x18003522e  xor     r8d, r8d
0x180035231  mov     [rbx+rdi], r8w
0x180035236  mov     eax, 80h
0x18003523b  mov     [r14], ax
0x18003523f  mov     [r14+8], r15
0x180035243  mov     ebx, r8d
0x180035246  mov     rdi, [rsp+138h+arg_8]
0x18003524e  test    ebx, ebx
0x180035250  js      loc_180035519
0x180035256  mov     [rsp+138h+var_68], rsi
0x18003525e  mov     r14d, [rsp+138h+arg_50]
0x180035266  lea     r15d, [r14+2]
0x18003526a  mov     [rsp+138h+var_60], r15d
0x180035272  mov     [rsp+138h+var_5C], 18h
0x18003527e  lea     rcx, [rsp+138h+var_88]; this
0x180035286  test    r15d, r15d
0x180035289  jg      loc_18003547F
0x18003528f  call    ?UnlinkFromGc@IScavengerBase@@QEAAXXZ; IScavengerBase::UnlinkFromGc(void)
0x180035294  mov     r9, rsi
0x180035297  mov     r8d, r15d
0x18003529a  lea     rdx, [rsp+138h+pvarg]
0x1800352a2  mov     rcx, [rsp+138h+arg_60]
0x1800352aa  lea     rax, ?CallEntryPoint@RegExpExec@@KAJPEAXPEAVVAR@@H1@Z; RegExpExec::CallEntryPoint(void *,VAR *,int,VAR *)
0x1800352b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352b6  mov     ebx, eax
0x1800352b8  xor     r8d, r8d
0x1800352bb  test    eax, eax
0x1800352bd  js      loc_180035519
0x1800352c3  cmp     word ptr [rsp+138h+pvarg], r8w
0x1800352cc  jz      short loc_180035321
0x1800352ce  lea     rax, [rsp+138h+pvarg]
0x1800352d6  mov     [rsp+138h+var_F0], rax
0x1800352db  lea     r9d, [r8+1]; int
0x1800352df  lea     r8, [rsp+138h+pvarg]; struct VAR *
0x1800352e7  lea     rdx, [rsp+138h+var_F0]; struct VAR **
0x1800352ec  mov     rcx, rdi; struct CSession *
0x1800352ef  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x1800352f4  mov     ebx, eax
0x1800352f6  test    eax, eax
0x1800352f8  js      loc_180035519
0x1800352fe  mov     rax, [rsp+138h+var_F0]
0x180035303  mov     rcx, [rax+8]; unsigned __int16 *
0x180035307  call    ?CbBstr@@YAKPEBG@Z; CbBstr(ushort const *)
0x18003530c  shr     eax, 1
0x18003530e  mov     r8d, eax; int
0x180035311  mov     rdx, rcx; unsigned __int16 *
0x180035314  mov     rcx, [rsp+138h+arg_58]; this
0x18003531c  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180035321  mov     rbx, [rsp+138h+Buf1]
0x180035329  test    rbx, rbx
0x18003532c  jz      loc_180035514
0x180035332  mov     rax, [rsp+138h+arg_30]
0x18003533a  cmp     [rax], rbx
0x18003533d  jnz     loc_180035514
0x180035343  mov     r8, [rsp+138h+Size]; Size
0x18003534b  mov     rdx, r12; Buf2
0x18003534e  mov     rcx, rbx; Buf1
0x180035351  call    memcmp_0
0x180035356  xor     r8d, r8d
0x180035359  test    eax, eax
0x18003535b  jnz     loc_180035514
0x180035361  movsxd  rcx, [rsp+138h+var_DC]
0x180035366  mov     rdi, rcx
0x180035369  mov     eax, [rsp+138h+var_D8]
0x18003536d  cmp     ecx, eax
0x18003536f  jg      short loc_180035374
0x180035371  lea     ecx, [rax+1]
0x180035374  mov     r15d, [rsp+138h+arg_28]
0x18003537c  mov     r13, [rsp+138h+arg_48]
0x180035384  cmp     [rsp+138h+var_D4], r8d
0x180035389  jz      loc_180035419
0x18003538f  cmp     ecx, r15d
0x180035392  jg      loc_180035419
0x180035398  mov     eax, 1
0x18003539d  sub     eax, dword ptr [rsp+138h+arg_68]
0x1800353a4  mov     dword ptr [rsp+138h+arg_68], eax
0x1800353ab  movsxd  r14, eax
0x1800353ae  mov     rax, [r13+r14*8+0]
0x1800353b3  mov     [rsp+138h+var_108], rax; struct REGrpRange *
0x1800353b8  mov     eax, [rsp+138h+arg_40]
0x1800353bf  mov     [rsp+138h+var_110], eax; int
0x1800353c3  mov     [rsp+138h+var_118], rbx; unsigned __int8 *
0x1800353c8  mov     r9d, ecx; int
0x1800353cb  mov     r8d, r15d; int
0x1800353ce  mov     rdx, [rsp+138h+arg_20]; unsigned __int16 *
0x1800353d6  mov     rcx, [rsp+138h+Buf]; Buf
0x1800353de  call    ?Exec@RegExpExec@@QEAAJPEBGJJPEAEJPEAUREGrpRange@@@Z; RegExpExec::Exec(ushort const *,long,long,uchar *,long,REGrpRange *)
0x1800353e3  mov     ebx, eax
0x1800353e5  xor     r8d, r8d
0x1800353e8  test    eax, eax
0x1800353ea  jnz     short loc_18003540B
0x1800353ec  mov     eax, dword ptr [rsp+138h+arg_68]
0x1800353f3  mov     [rsp+138h+var_C8], eax
0x1800353f7  mov     r13, [r13+r14*8+0]
0x1800353fc  mov     [rsp+138h+var_D0], r13
0x180035401  mov     rdx, [rsp+138h+var_E8]
0x180035406  jmp     loc_180035123
0x18003540b  js      loc_180035519
0x180035411  mov     r14d, [rsp+138h+arg_50]
0x180035419  cmp     edi, r15d
0x18003541c  jge     short loc_18003543D
0x18003541e  sub     r15d, edi
0x180035421  mov     rax, [rsp+138h+var_E8]
0x180035426  mov     rax, [rax]
0x180035429  lea     rdx, [rax+rdi*2]; unsigned __int16 *
0x18003542d  mov     r8d, r15d; int
0x180035430  mov     rcx, [rsp+138h+arg_58]; this
0x180035438  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18003543d  mov     rax, [rsp+138h+var_D0]
0x180035442  cmp     rax, [r13+0]
0x180035446  jz      short loc_18003545C
0x180035448  movsxd  r8, r14d
0x18003544b  shl     r8, 3; Size
0x18003544f  mov     rdx, [r13+8]; Src
0x180035453  mov     rcx, [r13+0]; void *
0x180035457  call    memcpy_0
0x18003545c  xor     r8d, r8d
0x18003545f  mov     ebx, r8d
0x180035462  jmp     loc_180035519
0x180035467  mov     ebx, 8007000Eh
0x18003546c  jmp     loc_18003524E
0x180035471  cmp     ecx, 0FFFFFFFFh
0x180035474  jz      loc_180035243
0x18003547a  jmp     loc_1800351D3
0x18003547f  call    ?LinkToGc@IScavengerBase@@QEAAXXZ; IScavengerBase::LinkToGc(void)
0x180035484  jmp     loc_180035294
0x180035489  inc     r15d
0x18003548c  mov     [rsp+138h+var_F8], r15d
0x180035491  movsxd  rax, edi
0x180035494  lea     rdx, ds:0[rax*8]
  ... truncated ...
```
