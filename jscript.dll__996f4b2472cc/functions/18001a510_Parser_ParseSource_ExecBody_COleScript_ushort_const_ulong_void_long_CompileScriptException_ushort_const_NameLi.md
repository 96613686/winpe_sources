# Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,NameList * *)

- ea: `0x18001a510`
- end: `0x18001aee6`
- name: `?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@2PEAPEAVNameList@@@Z`
- size: `2518`
- prototype: `__int64 __fastcall(Parser *this, struct ExecBody **, struct COleScript *, unsigned __int16 *, unsigned int, char *, unsigned int, struct CompileScriptException *, const unsigned __int16 *, struct NameList **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001868c`

## callees

- `0x18001a3c4`
- `0x18001a418`
- `0x18001a480`
- `0x18001a4c0`
- `0x18001a510`
- `0x18001aef0`
- `0x18001b330`
- `0x18001c430`
- `0x18001d9e4`
- `0x1800585c4`
- `0x1800585d0`
- `0x1800757dc`
- `0x180096662`

## import_xrefs

- `msvcrt!_controlfp` at `0x18001a550`
- `msvcrt!_controlfp` at `0x18001a569`
- `msvcrt!_controlfp` at `0x18001aa82`
- `msvcrt!_controlfp` at `0x18001a550`
- `msvcrt!_controlfp` at `0x18001a569`
- `msvcrt!_controlfp` at `0x18001aa82`
- `msvcrt!free` at `0x18001ae86`
- `msvcrt!free` at `0x18001ae86`
- `msvcrt!malloc` at `0x18001aaf4`
- `msvcrt!malloc` at `0x18001ab6f`
- `msvcrt!malloc` at `0x18001ac8d`
- `msvcrt!malloc` at `0x18001ad48`
- `msvcrt!malloc` at `0x18001ad73`
- `msvcrt!malloc` at `0x18001adcf`
- `msvcrt!malloc` at `0x18001aaf4`
- `msvcrt!malloc` at `0x18001ab6f`
- `msvcrt!malloc` at `0x18001ac8d`
- `msvcrt!malloc` at `0x18001ad48`
- `msvcrt!malloc` at `0x18001ad73`
- `msvcrt!malloc` at `0x18001adcf`

## pseudocode

```c
__int64 __fastcall Parser::ParseSource(
        Parser *this,
        struct ExecBody **a2,
        struct COleScript *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        char *a6,
        unsigned int a7,
        struct CompileScriptException *a8,
        const unsigned __int16 *a9,
        struct NameList **a10)
{
  HashTbl *v13; // rax
  unsigned int v14; // edx
  HashTbl *v15; // rbx
  Scanner *v16; // rax
  Scanner *v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // r9
  const unsigned __int16 *v20; // r11
  unsigned __int16 v21; // ax
  int v22; // r10d
  const unsigned __int16 *v23; // rdx
  int v24; // r8d
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // r8
  __int64 v27; // r8
  _DWORD *v28; // rax
  __int64 v29; // rax
  int *v30; // rdi
  int v31; // r14d
  int v32; // esi
  __int64 v33; // r15
  __int64 v34; // r12
  __int64 v35; // rbx
  struct ParseNode **v36; // r15
  __int64 v37; // rax
  Parser *v38; // r10
  __int64 v39; // r13
  int v40; // r12d
  int v41; // r14d
  struct ParseNode *v42; // rsi
  __int64 v43; // r13
  struct ParseNode **v44; // r12
  __int64 v45; // rax
  struct ParseNode *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rsi
  Scanner *v50; // rdi
  struct ExecBody *v51; // rax
  struct ExecBody *v52; // rdx
  unsigned int v53; // ebx
  int v55; // ebx
  int v56; // eax
  int v57; // eax
  _QWORD *v58; // rcx
  int v59; // esi
  int v60; // eax
  int v61; // eax
  _QWORD *v62; // rax
  int v63; // r15d
  int v64; // r14d
  struct ParseNode *v65; // r13
  __int64 v66; // rdx
  __int64 v67; // rcx
  int v68; // edx
  int v69; // edi
  int v70; // eax
  int v71; // eax
  _QWORD *v72; // rax
  _QWORD *v73; // rax
  _QWORD *v74; // rcx
  _QWORD *v75; // rax
  _QWORD *v76; // rcx
  _QWORD *v77; // rax
  _QWORD *v78; // rcx
  void *v79; // rcx
  unsigned __int16 *v80; // [rsp+20h] [rbp-71h]
  unsigned int NewValue; // [rsp+48h] [rbp-49h]
  struct ParseNode **v82; // [rsp+50h] [rbp-41h] BYREF
  struct ParseNode *v83; // [rsp+58h] [rbp-39h]
  struct ParseNode *v84; // [rsp+60h] [rbp-31h]
  int v85; // [rsp+68h] [rbp-29h]
  unsigned __int16 *v86; // [rsp+70h] [rbp-21h]
  __int64 v87; // [rsp+78h] [rbp-19h]
  __int64 v88; // [rsp+80h] [rbp-11h]
  __int64 v89; // [rsp+88h] [rbp-9h]

  v83 = 0;
  NewValue = _controlfp(0, 0);
  _controlfp(0x1Fu, 0x30F031Fu);
  *((_QWORD *)this + 47) = *((_QWORD *)a3 + 84);
  *((_DWORD *)this + 134) = *((_DWORD *)a3 + 240);
  *a2 = 0;
  if ( a8 )
  {
    *(_OWORD *)a8 = 0;
    *((_OWORD *)a8 + 1) = 0;
    *((_OWORD *)a8 + 2) = 0;
    *((_OWORD *)a8 + 3) = 0;
    *((_OWORD *)a8 + 4) = 0;
    *((_OWORD *)a8 + 5) = 0;
    *((_QWORD *)a8 + 12) = 0;
  }
  if ( !setjmp_0((_JBTYPE *)this + 2) )
  {
    v13 = (HashTbl *)operator new(0x30u);
    v15 = v13;
    if ( v13 )
    {
      *(_QWORD *)v13 = 0;
      *((_QWORD *)v13 + 1) = 0;
      *((_DWORD *)v13 + 4) = 256;
      *((_DWORD *)v13 + 5) = 0x4000;
      *((_QWORD *)v13 + 3) = 0;
      *((_QWORD *)v13 + 5) = (char *)this + 32;
    }
    else
    {
      v15 = 0;
    }
    if ( v15 )
    {
      if ( (unsigned int)HashTbl::Init(v15, v14) )
        goto LABEL_10;
      NoRelAlloc::FreeAll(v15);
      operator delete(v15);
    }
    v15 = 0;
LABEL_10:
    *(_QWORD *)this = v15;
    if ( !v15 )
      Parser::Error(this, 1001);
    v16 = (Scanner *)operator new(0x1A0u);
    if ( v16 )
      v17 = Scanner::Scanner(v16, v15, (Parser *)((char *)this + 320), (Parser *)((char *)this + 32));
    else
      v17 = 0;
    *((_QWORD *)this + 42) = v17;
    if ( !v17 )
      Parser::Error(this, 1001);
    *((_QWORD *)v17 + 11) = a10;
    v18 = a5 & 0xFFFFFFBF;
    v19 = *((_QWORD *)this + 42);
    v20 = a4;
    *((_DWORD *)this + 79) = a5 & 0xFFFFFFBF;
    *((_QWORD *)this + 49) = 0;
    v86 = a4;
    v21 = *a4;
    v82 = 0;
    if ( v21 == 0xFEFF || v21 == 0xFFFE )
      v20 = a4 + 1;
    *(_QWORD *)(v19 + 16) = v20;
    v22 = 0;
    *(_QWORD *)(v19 + 32) = v20;
    v23 = v20;
    *(_QWORD *)(v19 + 24) = v20;
    *(_QWORD *)(v19 + 40) = v20;
    *(_QWORD *)(v19 + 48) = v20;
    *(_DWORD *)(v19 + 68) = 0;
    while ( 1 )
    {
      v24 = *v23;
      v25 = v23 + 1;
      *(_QWORD *)(v19 + 40) = v23 + 1;
      if ( !v24 )
        break;
      if ( v24 == 10 || v24 == 13 || (unsigned int)(v24 - 8232) < 2 )
      {
        if ( v24 == 13 && *v25 == 10 )
        {
          v23 += 2;
          *(_QWORD *)(v19 + 40) = v23;
          v26 = v23;
        }
        else
        {
          ++v23;
          v26 = v25;
        }
        v27 = ((__int64)v26 - *(_QWORD *)(v19 + 24)) >> 1;
        *(_QWORD *)(v19 + 24) = v23;
        v85 = ((v27 & 0xFFE00000) != 0)
            + ((v27 & 0xFFFFC000) != 0)
            + ((v27 & 0xFFFFFF80) != 0)
            + 1
            + ((v27 & 0xF0000000) != 0);
        v22 += v85;
      }
      else
      {
        ++v23;
      }
    }
    v28 = *(_DWORD **)(v19 + 8);
    *(_QWORD *)(v19 + 40) = v20;
    *(_QWORD *)(v19 + 24) = v20;
    *(_DWORD *)(v19 + 68) = v22;
    *(_DWORD *)(v19 + 408) = 0;
    *v28 = 0;
    LODWORD(v28) = *(_DWORD *)(v19 + 64) ^ v18;
    *(_DWORD *)(v19 + 96) &= 0xFFFFFFC7;
    *(_DWORD *)(v19 + 64) = v18 ^ (unsigned int)v28 & 0xFFFFFFFE;
    *(_DWORD *)(v19 + 96) |= (v18 >> 2) & 0x20;
    Scanner::Scan(*((_QWORD *)this + 42));
    v29 = *((_QWORD *)this + 42);
    v30 = (int *)((char *)this + 28);
    v31 = *((_DWORD *)this + 5);
    v32 = *((_DWORD *)this + 4);
    v33 = *(_QWORD *)(v29 + 32);
    v34 = *(_QWORD *)(v29 + 16);
    if ( v31 - v32 >= 104 )
      goto LABEL_28;
    if ( *v30 <= 104 )
    {
      v73 = malloc(0x70u);
      if ( v73 )
      {
        v74 = (_QWORD *)*((_QWORD *)this + 1);
        if ( v32 < v31 )
        {
          *v73 = *v74;
          *v74 = v73;
        }
        else
        {
          *v73 = v74;
          *((_QWORD *)this + 1) = v73;
        }
        v35 = (__int64)(v73 + 1);
        goto LABEL_29;
      }
    }
    else
    {
      v55 = *((_DWORD *)this + 6);
      v56 = 104;
      if ( v31 > 104 )
        v56 = *((_DWORD *)this + 5);
      v57 = 2 * v56;
      if ( v55 <= v57 )
        v55 = v57;
      if ( v55 > *v30 )
        v55 = *v30;
      if ( v55 < 104 )
      {
        v35 = 0;
        goto LABEL_29;
      }
      if ( v55 + 8 > v55 && v55 + 8 >= 104 )
      {
        v58 = malloc(v55 + 8LL);
        if ( v58 )
        {
          v32 = 0;
          *v58 = *((_QWORD *)this + 1);
          *((_QWORD *)this + 1) = v58;
          *((_DWORD *)this + 5) = v55;
LABEL_28:
          v35 = v32 + *((_QWORD *)this + 1) + 8LL;
          *((_DWORD *)this + 4) = v32 + 104;
          goto LABEL_29;
        }
        v35 = 0;
LABEL_29:
        if ( !v35 )
          Parser::Error(this, 1001);
        *(_QWORD *)v35 = 70;
        v87 = v35;
        *(_DWORD *)(v35 + 8) = (v33 - v34) >> 1;
        v36 = (struct ParseNode **)(v35 + 80);
        *(_DWORD *)(v35 + 12) = (__int64)(*(_QWORD *)(*((_QWORD *)this + 42) + 40LL)
                                        - *(_QWORD *)(*((_QWORD *)this + 42) + 16LL)) >> 1;
        *(_DWORD *)(v35 + 88) = 0;
        *((_DWORD *)this + 92) = 1;
        *(_QWORD *)(v35 + 48) = 0;
        *(_DWORD *)(v35 + 4) = 0;
        *(_QWORD *)(v35 + 32) = 0;
        *(_QWORD *)(v35 + 24) = 0;
        *(_DWORD *)(v35 + 96) = 0;
        *(_QWORD *)(v35 + 40) = 0;
        *(_QWORD *)(v35 + 16) = 0;
        *((_QWORD *)this + 44) = v35 + 48;
        *((_QWORD *)this + 43) = 0;
        *((_DWORD *)this + 78) = 1;
        *(_QWORD *)(v35 + 64) = 0;
        *(_QWORD *)(v35 + 56) = 0;
        *((_QWORD *)this + 50) = 0;
        *((_QWORD *)this + 45) = v35 + 64;
        Parser::ParseStmtList(this, (struct ParseNode **)(v35 + 80), &v82);
        if ( *((_DWORD *)this + 80) != 127 )
          Parser::Error(this, 1002);
        v37 = *((_QWORD *)this + 42);
        v38 = this;
        v39 = *(_QWORD *)(v37 + 32);
        v40 = *((_DWORD *)this + 5);
        v41 = *((_DWORD *)this + 4);
        v84 = *(struct ParseNode **)(v37 + 16);
        if ( v40 - v41 >= 16 )
          goto LABEL_32;
        if ( *v30 <= 16 )
        {
          v75 = malloc(0x18u);
          v38 = this;
          if ( v75 )
          {
            v76 = (_QWORD *)*((_QWORD *)this + 1);
            if ( v41 >= v40 )
            {
              *v75 = v76;
              *((_QWORD *)this + 1) = v75;
            }
            else
            {
              *v75 = *v76;
              *v76 = v75;
            }
            v42 = (struct ParseNode *)(v75 + 1);
            goto LABEL_33;
          }
        }
        else
        {
          v59 = *((_DWORD *)this + 6);
          v60 = 16;
          if ( v40 > 16 )
            v60 = v40;
          v61 = 2 * v60;
          if ( v59 <= v61 )
            v59 = v61;
          if ( v59 > *v30 )
            v59 = *v30;
          if ( v59 < 16 )
          {
            v42 = 0;
            goto LABEL_33;
          }
          if ( v59 + 8 > v59 && v59 + 8 >= 16 )
          {
            v62 = malloc(v59 + 8LL);
            v38 = this;
            if ( v62 )
            {
              v41 = 0;
              *v62 = *((_QWORD *)this + 1);
              *((_QWORD *)this + 1) = v62;
              *((_DWORD *)this + 5) = v59;
LABEL_32:
              v42 = (struct ParseNode *)(v41 + *((_QWORD *)v38 + 1) + 8LL);
              *((_DWORD *)v38 + 4) = v41 + 16;
              goto LABEL_33;
            }
            v42 = 0;
LABEL_33:
            if ( !v42 )
              Parser::Error(v38, 1001);
            v43 = v39 - (_QWORD)v84;
            v44 = v82;
            *(_QWORD *)v42 = 71;
            *((_DWORD *)v42 + 2) = v43 >> 1;
            v45 = *((_QWORD *)v38 + 42);
            v84 = v42;
            *((_DWORD *)v42 + 3) = (__int64)(*(_QWORD *)(v45 + 40) - *(_QWORD *)(v45 + 16)) >> 1;
            if ( !v44 )
            {
              *v36 = v42;
LABEL_36:
              *((_DWORD *)v42 + 2) = 0;
              v46 = *v36;
              v82 = v36;
              v89 = v35;
              v83 = (struct ParseNode *)v35;
              *((_DWORD *)v46 + 3) = 0;
              *(_DWORD *)(v35 + 12) = (__int64)(*(_QWORD *)(*((_QWORD *)v38 + 42) + 40LL)
                                              - *(_QWORD *)(*((_QWORD *)v38 + 42) + 16LL)) >> 1;
              *(_QWORD *)(v35 + 72) = **((_QWORD **)v38 + 45);
              **((_QWORD **)v38 + 45) = 0;
              v47 = *((_QWORD *)v38 + 42);
              v48 = *(_QWORD *)(v47 + 384);
              v49 = (__int64)(*(_QWORD *)(v47 + 32) - *(_QWORD *)(v47 + 16)) >> 1;
              *((_DWORD *)v38 + 138) = *(_DWORD *)(v47 + 392) - v48;
              *(_QWORD *)(v47 + 400) = 0;
              *(_QWORD *)(v47 + 392) = 0;
              *(_QWORD *)(v47 + 384) = 0;
              v50 = (Scanner *)*((_QWORD *)v38 + 42);
              *((_QWORD *)v38 + 68) = v48;
              if ( v50 )
              {
                Scanner::~Scanner(v50);
                operator delete(v50);
                v38 = this;
              }
              v80 = v86;
              *((_QWORD *)v38 + 42) = 0;
              Parser::GenerateCode(v38, (struct ParseNode *)v35, a6, a7, v80, v49, a9);
              v51 = (struct ExecBody *)operator new(0x10u);
              v52 = v51;
              if ( v51 )
              {
                *(_QWORD *)v51 = *((_QWORD *)this + 38);
                *((_DWORD *)v51 + 2) = 1;
              }
              else
              {
                v52 = 0;
              }
              *a2 = v52;
              if ( !v52 )
                Parser::Error(this, 1001);
              *((_QWORD *)this + 38) = 0;
              v53 = 0;
              goto LABEL_42;
            }
            v63 = *((_DWORD *)v38 + 5);
            v64 = *((_DWORD *)v38 + 4);
            v65 = *v44;
            if ( v63 - v64 >= 40 )
              goto LABEL_69;
            v68 = *v30;
            if ( *v30 <= 40 )
            {
              v77 = malloc(0x30u);
              v38 = this;
              if ( v77 )
              {
                v78 = (_QWORD *)*((_QWORD *)this + 1);
                if ( v64 >= v63 )
                {
                  *v77 = v78;
                  *((_QWORD *)this + 1) = v77;
                }
                else
                {
                  *v77 = *v78;
                  *v78 = v77;
                }
                v66 = (__int64)(v77 + 1);
                goto LABEL_70;
              }
            }
            else
            {
              v69 = *((_DWORD *)v38 + 6);
              v70 = 40;
              if ( v63 > 40 )
                v70 = *((_DWORD *)v38 + 5);
              v71 = 2 * v70;
              if ( v69 <= v71 )
                v69 = v71;
              if ( v69 > v68 )
                v69 = v68;
              if ( v69 < 40 )
              {
                v66 = 0;
                goto LABEL_70;
              }
              if ( v69 + 8 > v69 && v69 + 8 >= 40 )
              {
                v72 = malloc(v69 + 8LL);
                v38 = this;
                if ( !v72 )
                {
                  v66 = 0;
                  goto LABEL_70;
                }
                v64 = 0;
                *v72 = *((_QWORD *)this + 1);
                *((_QWORD *)this + 1) = v72;
                *((_DWORD *)this + 5) = v69;
LABEL_69:
                v66 = v64 + *((_QWORD *)v38 + 1) + 8LL;
                *((_DWORD *)v38 + 4) = v64 + 40;
LABEL_70:
                if ( !v66 )
                  Parser::Error(v38, 1001);
                *(_QWORD *)(v66 + 32) = v42;
                v36 = (struct ParseNode **)(v66 + 32);
                *(_QWORD *)v66 = 67;
                *(_QWORD *)(v66 + 16) = 0;
                *(_QWORD *)(v66 + 24) = v65;
                if ( v65 )
                {
                  *(_DWORD *)(v66 + 8) = *((_DWORD *)v65 + 2);
                  LODWORD(v67) = *((_DWORD *)v42 + 3);
                }
                else
                {
                  *(_DWORD *)(v66 + 8) = (__int64)(*(_QWORD *)(*((_QWORD *)v38 + 42) + 32LL)
                                                 - *(_QWORD *)(*((_QWORD *)v38 + 42) + 16LL)) >> 1;
                  v67 = (__int64)(*(_QWORD *)(*((_QWORD *)v38 + 42) + 40LL) - *(_QWORD *)(*((_QWORD *)v38 + 42) + 16LL)) >> 1;
                }
                *(_DWORD *)(v66 + 12) = v67;
                *v44 = (struct ParseNode *)v66;
                v42 = *v36;
                v88 = v66;
                goto LABEL_36;
              }
            }
            v66 = 0;
            goto LABEL_70;
          }
        }
        v42 = 0;
        goto LABEL_33;
      }
    }
    v35 = 0;
    goto LABEL_29;
  }
  v79 = (void *)*((_QWORD *)this + 38);
  if ( v79 )
  {
    free(v79);
    *((_QWORD *)this + 38) = 0;
  }
  NoRelAlloc::FreeAll((Parser *)((char *)this + 8));
  v53 = CompileScriptException::ProcessError(
          a8,
          a3,
          *((struct Scanner **)this + 42),
          (Parser *)((char *)this + 32),
          v83,
          a7,
          a6,
          a4);
LABEL_42:
  _controlfp(NewValue, 0xFFFFFFFF);
  return v53;
}

```

## disassembly

```asm
0x18001a510  mov     [rsp-8+arg_18], r9
0x18001a515  mov     [rsp-8+arg_10], r8
0x18001a51a  mov     [rsp-8+arg_8], rdx
0x18001a51f  mov     [rsp-8+arg_0], rcx
0x18001a524  push    rbp
0x18001a525  push    rbx
0x18001a526  push    rsi
0x18001a527  push    rdi
0x18001a528  push    r12
0x18001a52a  push    r13
0x18001a52c  push    r14
0x18001a52e  push    r15
0x18001a530  lea     rbp, [rsp-7]
0x18001a535  sub     rsp, 98h
0x18001a53c  mov     rdi, rdx
0x18001a53f  mov     rsi, rcx
0x18001a542  xor     r14d, r14d
0x18001a545  xor     edx, edx; Mask
0x18001a547  xor     ecx, ecx; NewValue
0x18001a549  mov     [rbp+3Fh+var_78], r14
0x18001a54d  mov     rbx, r8
0x18001a550  call    cs:__imp__controlfp
0x18001a557  nop     dword ptr [rax+rax+00h]
0x18001a55c  mov     edx, 30F031Fh; Mask
0x18001a561  mov     ecx, 1Fh; NewValue
0x18001a566  mov     [rbp+3Fh+NewValue], eax
0x18001a569  call    cs:__imp__controlfp
0x18001a570  nop     dword ptr [rax+rax+00h]
0x18001a575  mov     rax, [rbx+2A0h]
0x18001a57c  mov     [rsi+178h], rax
0x18001a583  mov     eax, [rbx+3C0h]
0x18001a589  mov     [rsi+218h], eax
0x18001a58f  mov     rax, [rbp+3Fh+arg_38]
0x18001a596  mov     [rdi], r14
0x18001a599  test    rax, rax
0x18001a59c  jnz     loc_18001AC1D
0x18001a5a2  lea     rcx, [rsi+20h]; Buf
0x18001a5a6  mov     rdx, rsp
0x18001a5a9  call    _setjmp_0
0x18001a5ae  test    eax, eax
0x18001a5b0  jnz     loc_18001AE76
0x18001a5b6  mov     ecx, 30h ; '0'; Size
0x18001a5bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a5c0  mov     r13, [rbp+3Fh+arg_0]
0x18001a5c4  mov     rbx, rax
0x18001a5c7  mov     [rbp+3Fh+var_90], r13
0x18001a5cb  test    rax, rax
0x18001a5ce  jz      loc_18001ACDA
0x18001a5d4  mov     [rax], r14
0x18001a5d7  mov     [rax+8], r14
0x18001a5db  mov     dword ptr [rax+10h], 100h
0x18001a5e2  mov     dword ptr [rax+14h], 4000h
0x18001a5e9  mov     [rax+18h], r14
0x18001a5ed  lea     rax, [r13+20h]
0x18001a5f1  mov     [rbx+28h], rax
0x18001a5f5  test    rbx, rbx
0x18001a5f8  jz      short loc_18001A616
0x18001a5fa  mov     rcx, rbx; this
0x18001a5fd  call    ?Init@HashTbl@@AEAAHI@Z; HashTbl::Init(uint)
0x18001a602  test    eax, eax
0x18001a604  jnz     short loc_18001A619
0x18001a606  mov     rcx, rbx; this
0x18001a609  call    ?FreeAll@NoRelAlloc@@QEAAXXZ; NoRelAlloc::FreeAll(void)
0x18001a60e  mov     rcx, rbx; Block
0x18001a611  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a616  mov     rbx, r14
0x18001a619  mov     [r13+0], rbx
0x18001a61d  test    rbx, rbx
0x18001a620  jz      loc_18001AE0B
0x18001a626  mov     ecx, 1A0h; Size
0x18001a62b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a630  test    rax, rax
0x18001a633  jz      loc_18001ACBC
0x18001a639  lea     r9, [r13+20h]; struct ErrHandler *
0x18001a63d  mov     rdx, rbx; struct HashTbl *
0x18001a640  lea     r8, [r13+140h]; struct Token *
0x18001a647  mov     rcx, rax; this
0x18001a64a  call    ??0Scanner@@AEAA@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Scanner(HashTbl *,Token *,ErrHandler *)
0x18001a64f  mov     rcx, rax
0x18001a652  mov     [r13+150h], rcx
0x18001a659  test    rcx, rcx
0x18001a65c  jz      loc_18001AE19
0x18001a662  mov     rax, [rbp+3Fh+arg_48]
0x18001a669  mov     ebx, [rbp+3Fh+arg_20]
0x18001a66c  mov     [rcx+58h], rax
0x18001a670  and     ebx, 0FFFFFFBFh
0x18001a673  mov     rax, [rbp+3Fh+arg_18]
0x18001a677  mov     ecx, 0FEFFh
0x18001a67c  mov     r9, [r13+150h]
0x18001a683  mov     r11, rax
0x18001a686  mov     [r13+13Ch], ebx
0x18001a68d  mov     [r13+188h], r14
0x18001a694  mov     [rbp+3Fh+var_60], rax
0x18001a698  movzx   eax, word ptr [rax]
0x18001a69b  mov     [rbp+3Fh+var_80], r14
0x18001a69f  cmp     cx, ax
0x18001a6a2  jz      loc_18001AE27
0x18001a6a8  mov     ecx, 0FFFEh
0x18001a6ad  cmp     cx, ax
0x18001a6b0  jz      loc_18001AE27
0x18001a6b6  mov     [r9+10h], r11
0x18001a6ba  mov     r10d, r14d
0x18001a6bd  mov     [r9+20h], r11
0x18001a6c1  mov     rdx, r11
0x18001a6c4  mov     [r9+18h], r11
0x18001a6c8  mov     [r9+28h], r11
0x18001a6cc  mov     [r9+30h], r11
0x18001a6d0  mov     [r9+44h], r14d
0x18001a6d4  nop     dword ptr [rax+00h]
0x18001a6d8  nop     dword ptr [rax+rax+00000000h]
0x18001a6e0  movzx   r8d, word ptr [rdx]
0x18001a6e4  lea     rcx, [rdx+2]
0x18001a6e8  mov     [r9+28h], rcx
0x18001a6ec  mov     eax, r8d
0x18001a6ef  test    r8d, r8d
0x18001a6f2  jz      loc_18001A784
0x18001a6f8  sub     eax, 0Ah
0x18001a6fb  jz      short loc_18001A713
0x18001a6fd  sub     eax, 3
0x18001a700  jz      short loc_18001A713
0x18001a702  sub     eax, 201Bh
0x18001a707  jz      short loc_18001A713
0x18001a709  cmp     eax, 1
0x18001a70c  jz      short loc_18001A713
0x18001a70e  mov     rdx, rcx
0x18001a711  jmp     short loc_18001A6E0
0x18001a713  cmp     r8d, 0Dh
0x18001a717  jnz     short loc_18001A77C
0x18001a719  cmp     word ptr [rcx], 0Ah
0x18001a71d  jnz     short loc_18001A77C
0x18001a71f  add     rdx, 4
0x18001a723  mov     [r9+28h], rdx
0x18001a727  mov     r8, rdx
0x18001a72a  sub     r8, [r9+18h]
0x18001a72e  mov     ecx, r14d
0x18001a731  sar     r8, 1
0x18001a734  mov     eax, r14d
0x18001a737  test    r8d, 0F0000000h
0x18001a73e  mov     [r9+18h], rdx
0x18001a742  setnz   cl
0x18001a745  test    r8d, 0FFFFFF80h
0x18001a74c  setnz   al
0x18001a74f  inc     eax
0x18001a751  add     ecx, eax
0x18001a753  mov     eax, r14d
0x18001a756  test    r8d, 0FFFFC000h
0x18001a75d  setnz   al
0x18001a760  add     ecx, eax
0x18001a762  mov     eax, r14d
0x18001a765  test    r8d, 0FFE00000h
0x18001a76c  setnz   al
0x18001a76f  add     ecx, eax
0x18001a771  mov     [rbp+3Fh+var_68], ecx
0x18001a774  add     r10d, ecx
0x18001a777  jmp     loc_18001A6E0
0x18001a77c  mov     rdx, rcx
0x18001a77f  mov     r8, rcx
0x18001a782  jmp     short loc_18001A72A
0x18001a784  mov     rax, [r9+8]
0x18001a788  mov     [r9+28h], r11
0x18001a78c  mov     [r9+18h], r11
0x18001a790  mov     [r9+44h], r10d
0x18001a794  mov     [r9+198h], r14d
0x18001a79b  mov     [rax], r14d
0x18001a79e  mov     eax, ebx
0x18001a7a0  xor     eax, [r9+40h]
0x18001a7a4  and     dword ptr [r9+60h], 0FFFFFFC7h
0x18001a7a9  and     eax, 0FFFFFFFEh
0x18001a7ac  xor     eax, ebx
0x18001a7ae  shr     ebx, 2
0x18001a7b1  mov     [r9+40h], eax
0x18001a7b5  and     ebx, 20h
0x18001a7b8  or      [r9+60h], ebx
0x18001a7bc  mov     rcx, [r13+150h]
0x18001a7c3  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18001a7c8  mov     rax, [r13+150h]
0x18001a7cf  lea     rdi, [r13+1Ch]
0x18001a7d3  mov     r14d, [r13+14h]
0x18001a7d7  mov     esi, [r13+10h]
0x18001a7db  mov     r15, [rax+20h]
0x18001a7df  mov     r12, [rax+10h]
0x18001a7e3  mov     eax, r14d
0x18001a7e6  sub     eax, esi
0x18001a7e8  cmp     eax, 68h ; 'h'
0x18001a7eb  jl      loc_18001AAA9
0x18001a7f1  xor     edx, edx
0x18001a7f3  mov     rbx, [r13+8]
0x18001a7f7  lea     eax, [rsi+68h]
0x18001a7fa  add     rbx, 8
0x18001a7fe  movsxd  rcx, esi
0x18001a801  add     rbx, rcx
0x18001a804  mov     [r13+10h], eax
0x18001a808  test    rbx, rbx
0x18001a80b  jz      loc_18001AE30
0x18001a811  mov     qword ptr [rbx], 46h ; 'F'
0x18001a818  lea     r8, [rbp+3Fh+var_80]; struct ParseNode ***
0x18001a81c  sub     r15, r12
0x18001a81f  mov     [rbp+3Fh+var_58], rbx
0x18001a823  sar     r15, 1
0x18001a826  mov     [rbx+8], r15d
0x18001a82a  lea     r15, [rbx+50h]
0x18001a82e  mov     rax, [r13+150h]
0x18001a835  mov     rcx, [rax+28h]
0x18001a839  sub     rcx, [rax+10h]
0x18001a83d  lea     rax, [rbx+30h]
0x18001a841  sar     rcx, 1
0x18001a844  mov     [rbx+0Ch], ecx
0x18001a847  mov     rcx, r13; this
0x18001a84a  mov     [rbx+58h], edx
0x18001a84d  mov     dword ptr [r13+170h], 1
0x18001a858  mov     [rax], rdx
0x18001a85b  mov     [rbx+4], edx
0x18001a85e  mov     [rbx+20h], rdx
0x18001a862  mov     [rbx+18h], rdx
0x18001a866  mov     [rbx+60h], edx
0x18001a869  mov     [rbx+28h], rdx
0x18001a86d  mov     [rbx+10h], rdx
0x18001a871  mov     [r13+160h], rax
0x18001a878  lea     rax, [rbx+40h]
0x18001a87c  mov     [r13+158h], rdx
0x18001a883  mov     dword ptr [r13+138h], 1
0x18001a88e  mov     [rax], rdx
0x18001a891  mov     [rbx+38h], rdx
0x18001a895  mov     [r13+190h], rdx
0x18001a89c  mov     rdx, r15; struct ParseNode **
0x18001a89f  mov     [r13+168h], rax
0x18001a8a6  call    ?ParseStmtList@Parser@@AEAAXPEAPEAUParseNode@@PEAPEAPEAU2@@Z; Parser::ParseStmtList(ParseNode * *,ParseNode * * *)
0x18001a8ab  cmp     dword ptr [r13+140h], 7Fh
0x18001a8b3  jnz     loc_18001AE3E
0x18001a8b9  mov     rax, [r13+150h]
0x18001a8c0  mov     r10, [rbp+3Fh+var_90]
0x18001a8c4  mov     r13, [rax+20h]
0x18001a8c8  mov     rax, [rax+10h]
0x18001a8cc  mov     r12d, [r10+14h]
0x18001a8d0  mov     r14d, [r10+10h]
0x18001a8d4  mov     [rbp+3Fh+var_70], rax
0x18001a8d8  mov     eax, r12d
0x18001a8db  sub     eax, r14d
0x18001a8de  cmp     eax, 10h
0x18001a8e1  jl      loc_18001AB24
0x18001a8e7  mov     rsi, [r10+8]
0x18001a8eb  lea     eax, [r14+10h]
0x18001a8ef  add     rsi, 8
0x18001a8f3  movsxd  rcx, r14d
0x18001a8f6  add     rsi, rcx
0x18001a8f9  mov     [r10+10h], eax
0x18001a8fd  test    rsi, rsi
0x18001a900  jz      loc_18001AE4C
0x18001a906  sub     r13, [rbp+3Fh+var_70]
0x18001a90a  mov     r12, [rbp+3Fh+var_80]
0x18001a90e  mov     qword ptr [rsi], 47h ; 'G'
0x18001a915  sar     r13, 1
0x18001a918  mov     [rsi+8], r13d
0x18001a91c  mov     rax, [r10+150h]
0x18001a923  mov     [rbp+3Fh+var_70], rsi
0x18001a927  mov     rcx, [rax+28h]
0x18001a92b  sub     rcx, [rax+10h]
0x18001a92f  sar     rcx, 1
0x18001a932  mov     [rsi+0Ch], ecx
0x18001a935  test    r12, r12
0x18001a938  jnz     loc_18001ABA2
0x18001a93e  mov     [r15], rsi
0x18001a941  mov     dword ptr [rsi+8], 0
0x18001a948  mov     rax, [r15]
0x18001a94b  mov     [rbp+3Fh+var_80], r15
0x18001a94f  mov     [rbp+3Fh+var_48], rbx
0x18001a953  mov     [rbp+3Fh+var_78], rbx
0x18001a957  mov     dword ptr [rax+0Ch], 0
0x18001a95e  mov     rax, [r10+150h]
0x18001a965  mov     rcx, [rax+28h]
0x18001a969  sub     rcx, [rax+10h]
0x18001a96d  sar     rcx, 1
0x18001a970  mov     [rbx+0Ch], ecx
0x18001a973  mov     rax, [r10+168h]
0x18001a97a  mov     rcx, [rax]
0x18001a97d  mov     [rbx+48h], rcx
0x18001a981  mov     rax, [r10+168h]
0x18001a988  mov     qword ptr [rax], 0
0x18001a98f  mov     rdx, [r10+150h]
0x18001a996  mov     rsi, [rdx+20h]
0x18001a99a  sub     rsi, [rdx+10h]
0x18001a99e  mov     rcx, [rdx+180h]
0x18001a9a5  mov     eax, [rdx+188h]
0x18001a9ab  sub     eax, ecx
0x18001a9ad  sar     rsi, 1
0x18001a9b0  mov     [r10+228h], eax
0x18001a9b7  mov     qword ptr [rdx+190h], 0
0x18001a9c2  mov     qword ptr [rdx+188h], 0
0x18001a9cd  mov     qword ptr [rdx+180h], 0
0x18001a9d8  mov     rdi, [r10+150h]
0x18001a9df  mov     [r10+220h], rcx
0x18001a9e6  test    rdi, rdi
0x18001a9e9  jz      short loc_18001A9FF
0x18001a9eb  mov     rcx, rdi; this
0x18001a9ee  call    ??1Scanner@@AEAA@XZ; Scanner::~Scanner(void)
0x18001a9f3  mov     rcx, rdi; Block
0x18001a9f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a9fb  mov     r10, [rbp+3Fh+var_90]
0x18001a9ff  mov     rax, [rbp+3Fh+arg_40]
0x18001aa06  mov     rdx, rbx; struct ParseNode *
  ... truncated ...
```
