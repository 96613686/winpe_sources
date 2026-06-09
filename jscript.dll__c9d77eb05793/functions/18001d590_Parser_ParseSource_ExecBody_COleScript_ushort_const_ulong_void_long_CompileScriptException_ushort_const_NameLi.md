# Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,NameList * *)

- ea: `0x18001d590`
- end: `0x18001df25`
- name: `?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@2PEAPEAVNameList@@@Z`
- size: `2453`
- prototype: `__int64 __fastcall(Parser *__hidden this, struct ExecBody **, struct COleScript *, const unsigned __int16 *, unsigned int, LPCSTR, UINT, struct CompileScriptException *, const unsigned __int16 *, struct NameList **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001b560`

## callees

- `0x18001d468`
- `0x18001d4b0`
- `0x18001d510`
- `0x18001d548`
- `0x18001d590`
- `0x18001df30`
- `0x18001e360`
- `0x18001f400`
- `0x1800209a0`
- `0x180057694`
- `0x1800576a0`
- `0x1800742e8`
- `0x180094252`

## import_xrefs

- `msvcrt!_controlfp` at `0x18001d5d0`
- `msvcrt!_controlfp` at `0x18001d5e3`
- `msvcrt!_controlfp` at `0x18001daf2`
- `msvcrt!_controlfp` at `0x18001d5d0`
- `msvcrt!_controlfp` at `0x18001d5e3`
- `msvcrt!_controlfp` at `0x18001daf2`
- `msvcrt!free` at `0x18001decb`
- `msvcrt!free` at `0x18001decb`
- `msvcrt!malloc` at `0x18001db5d`
- `msvcrt!malloc` at `0x18001dbd2`
- `msvcrt!malloc` at `0x18001dcea`
- `msvcrt!malloc` at `0x18001dd9f`
- `msvcrt!malloc` at `0x18001ddc4`
- `msvcrt!malloc` at `0x18001de1a`
- `msvcrt!malloc` at `0x18001db5d`
- `msvcrt!malloc` at `0x18001dbd2`
- `msvcrt!malloc` at `0x18001dcea`
- `msvcrt!malloc` at `0x18001dd9f`
- `msvcrt!malloc` at `0x18001ddc4`
- `msvcrt!malloc` at `0x18001de1a`

## pseudocode

```c
__int64 __fastcall Parser::ParseSource(
        _JBTYPE *this,
        struct ExecBody **a2,
        struct COleScript *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        CHAR *psz,
        UINT len,
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
  unsigned __int64 v19; // r9
  const unsigned __int16 *v20; // r11
  unsigned __int16 v21; // ax
  int v22; // r10d
  const unsigned __int16 *v23; // rdx
  int v24; // r8d
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // r8
  __int64 v27; // r8
  _DWORD *v28; // rax
  unsigned __int64 v29; // rax
  int *v30; // rdi
  int v31; // r14d
  int v32; // esi
  __int64 v33; // r15
  __int64 v34; // r12
  __int64 v35; // rbx
  struct ParseNode **v36; // r15
  unsigned __int64 v37; // rax
  _JBTYPE *v38; // r10
  __int64 v39; // r13
  int v40; // r12d
  int v41; // r14d
  struct ParseNode *v42; // rsi
  __int64 v43; // r13
  struct ParseNode **v44; // r12
  unsigned __int64 v45; // rax
  struct ParseNode *v46; // rax
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rcx
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
  this[23].Part[1] = *((_QWORD *)a3 + 84);
  LODWORD(this[33].Part[1]) = *((_DWORD *)a3 + 240);
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
  if ( !setjmp_0(this + 2) )
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
      *((_QWORD *)v13 + 5) = this + 2;
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
    this->Part[0] = (unsigned __int64)v15;
    if ( !v15 )
      Parser::Error((Parser *)this, 1001);
    v16 = (Scanner *)operator new(0x1A0u);
    if ( v16 )
      v17 = Scanner::Scanner(v16, v15, (struct Token *)&this[20], (struct ErrHandler *)&this[2]);
    else
      v17 = 0;
    this[21].Part[0] = (unsigned __int64)v17;
    if ( !v17 )
      Parser::Error((Parser *)this, 1001);
    *((_QWORD *)v17 + 11) = a10;
    v18 = a5 & 0xFFFFFFBF;
    v19 = this[21].Part[0];
    v20 = a4;
    HIDWORD(this[19].Part[1]) = a5 & 0xFFFFFFBF;
    this[24].Part[1] = 0;
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
    Scanner::Scan(this[21].Part[0], (unsigned __int64)v23);
    v29 = this[21].Part[0];
    v30 = (int *)&this[1].Part[1] + 1;
    v31 = HIDWORD(this[1].Part[0]);
    v32 = this[1].Part[0];
    v33 = *(_QWORD *)(v29 + 32);
    v34 = *(_QWORD *)(v29 + 16);
    if ( v31 - v32 >= 104 )
      goto LABEL_28;
    if ( *v30 <= 104 )
    {
      v73 = malloc(0x70u);
      if ( v73 )
      {
        v74 = (_QWORD *)this->Part[1];
        if ( v32 < v31 )
        {
          *v73 = *v74;
          *v74 = v73;
        }
        else
        {
          *v73 = v74;
          this->Part[1] = (unsigned __int64)v73;
        }
        v35 = (__int64)(v73 + 1);
        goto LABEL_29;
      }
    }
    else
    {
      v55 = this[1].Part[1];
      v56 = 104;
      if ( v31 > 104 )
        v56 = HIDWORD(this[1].Part[0]);
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
          *v58 = this->Part[1];
          this->Part[1] = (unsigned __int64)v58;
          HIDWORD(this[1].Part[0]) = v55;
LABEL_28:
          v35 = v32 + this->Part[1] + 8;
          LODWORD(this[1].Part[0]) = v32 + 104;
          goto LABEL_29;
        }
        v35 = 0;
LABEL_29:
        if ( !v35 )
          Parser::Error((Parser *)this, 1001);
        *(_QWORD *)v35 = 70;
        v87 = v35;
        *(_DWORD *)(v35 + 8) = (v33 - v34) >> 1;
        v36 = (struct ParseNode **)(v35 + 80);
        *(_DWORD *)(v35 + 12) = (__int64)(*(_QWORD *)(this[21].Part[0] + 40) - *(_QWORD *)(this[21].Part[0] + 16)) >> 1;
        *(_DWORD *)(v35 + 88) = 0;
        LODWORD(this[23].Part[0]) = 1;
        *(_QWORD *)(v35 + 48) = 0;
        *(_DWORD *)(v35 + 4) = 0;
        *(_QWORD *)(v35 + 32) = 0;
        *(_QWORD *)(v35 + 24) = 0;
        *(_DWORD *)(v35 + 96) = 0;
        *(_QWORD *)(v35 + 40) = 0;
        *(_QWORD *)(v35 + 16) = 0;
        this[22].Part[0] = v35 + 48;
        this[21].Part[1] = 0;
        LODWORD(this[19].Part[1]) = 1;
        *(_QWORD *)(v35 + 64) = 0;
        *(_QWORD *)(v35 + 56) = 0;
        this[25].Part[0] = 0;
        this[22].Part[1] = v35 + 64;
        Parser::ParseStmtList((Parser *)this, (struct ParseNode **)(v35 + 80), &v82);
        if ( LODWORD(this[20].Part[0]) != 127 )
          Parser::Error((Parser *)this, 1002);
        v37 = this[21].Part[0];
        v38 = this;
        v39 = *(_QWORD *)(v37 + 32);
        v40 = HIDWORD(this[1].Part[0]);
        v41 = this[1].Part[0];
        v84 = *(struct ParseNode **)(v37 + 16);
        if ( v40 - v41 >= 16 )
          goto LABEL_32;
        if ( *v30 <= 16 )
        {
          v75 = malloc(0x18u);
          v38 = this;
          if ( v75 )
          {
            v76 = (_QWORD *)this->Part[1];
            if ( v41 >= v40 )
            {
              *v75 = v76;
              this->Part[1] = (unsigned __int64)v75;
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
          v59 = this[1].Part[1];
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
              *v62 = this->Part[1];
              this->Part[1] = (unsigned __int64)v62;
              HIDWORD(this[1].Part[0]) = v59;
LABEL_32:
              v42 = (struct ParseNode *)(v41 + v38->Part[1] + 8);
              LODWORD(v38[1].Part[0]) = v41 + 16;
              goto LABEL_33;
            }
            v42 = 0;
LABEL_33:
            if ( !v42 )
              Parser::Error((Parser *)v38, 1001);
            v43 = v39 - (_QWORD)v84;
            v44 = v82;
            *(_QWORD *)v42 = 71;
            *((_DWORD *)v42 + 2) = v43 >> 1;
            v45 = v38[21].Part[0];
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
              *(_DWORD *)(v35 + 12) = (__int64)(*(_QWORD *)(v38[21].Part[0] + 40) - *(_QWORD *)(v38[21].Part[0] + 16)) >> 1;
              *(_QWORD *)(v35 + 72) = *(_QWORD *)v38[22].Part[1];
              *(_QWORD *)v38[22].Part[1] = 0;
              v47 = v38[21].Part[0];
              v48 = *(_QWORD *)(v47 + 384);
              v49 = (__int64)(*(_QWORD *)(v47 + 32) - *(_QWORD *)(v47 + 16)) >> 1;
              LODWORD(v38[34].Part[1]) = *(_DWORD *)(v47 + 392) - v48;
              *(_QWORD *)(v47 + 400) = 0;
              *(_QWORD *)(v47 + 392) = 0;
              *(_QWORD *)(v47 + 384) = 0;
              v50 = (Scanner *)v38[21].Part[0];
              v38[34].Part[0] = v48;
              if ( v50 )
              {
                Scanner::~Scanner(v50);
                operator delete(v50);
                v38 = this;
              }
              v80 = v86;
              v38[21].Part[0] = 0;
              Parser::GenerateCode((Parser *)v38, (struct ParseNode *)v35, psz, len, v80, v49, a9);
              v51 = (struct ExecBody *)operator new(0x10u);
              v52 = v51;
              if ( v51 )
              {
                *(_QWORD *)v51 = this[19].Part[0];
                *((_DWORD *)v51 + 2) = 1;
              }
              else
              {
                v52 = 0;
              }
              *a2 = v52;
              if ( !v52 )
                Parser::Error((Parser *)this, 1001);
              this[19].Part[0] = 0;
              v53 = 0;
              goto LABEL_42;
            }
            v63 = HIDWORD(v38[1].Part[0]);
            v64 = v38[1].Part[0];
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
                v78 = (_QWORD *)this->Part[1];
                if ( v64 >= v63 )
                {
                  *v77 = v78;
                  this->Part[1] = (unsigned __int64)v77;
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
              v69 = v38[1].Part[1];
              v70 = 40;
              if ( v63 > 40 )
                v70 = HIDWORD(v38[1].Part[0]);
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
                *v72 = this->Part[1];
                this->Part[1] = (unsigned __int64)v72;
                HIDWORD(this[1].Part[0]) = v69;
LABEL_69:
                v66 = v64 + v38->Part[1] + 8;
                LODWORD(v38[1].Part[0]) = v64 + 40;
LABEL_70:
                if ( !v66 )
                  Parser::Error((Parser *)v38, 1001);
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
                  *(_DWORD *)(v66 + 8) = (__int64)(*(_QWORD *)(v38[21].Part[0] + 32) - *(_QWORD *)(v38[21].Part[0] + 16)) >> 1;
                  v67 = (__int64)(*(_QWORD *)(v38[21].Part[0] + 40) - *(_QWORD *)(v38[21].Part[0] + 16)) >> 1;
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
  v79 = (void *)this[19].Part[0];
  if ( v79 )
  {
    free(v79);
    this[19].Part[0] = 0;
  }
  NoRelAlloc::FreeAll((NoRelAlloc *)&this->Part[1]);
  v53 = CompileScriptException::ProcessError(
          a8,
          a3,
          (struct Scanner *)this[21].Part[0],
          (struct ErrHandler *)&this[2],
          v83,
          len,
          psz,
          a4);
LABEL_42:
  _controlfp(NewValue, 0xFFFFFFFF);
  return v53;
}

```

## disassembly

```asm
0x18001d590  mov     [rsp-8+arg_18], r9
0x18001d595  mov     [rsp-8+arg_10], r8
0x18001d59a  mov     [rsp-8+arg_8], rdx
0x18001d59f  mov     [rsp-8+arg_0], rcx
0x18001d5a4  push    rbp
0x18001d5a5  push    rbx
0x18001d5a6  push    rsi
0x18001d5a7  push    rdi
0x18001d5a8  push    r12
0x18001d5aa  push    r13
0x18001d5ac  push    r14
0x18001d5ae  push    r15
0x18001d5b0  lea     rbp, [rsp-7]
0x18001d5b5  sub     rsp, 98h
0x18001d5bc  mov     rdi, rdx
0x18001d5bf  mov     rsi, rcx
0x18001d5c2  xor     r14d, r14d
0x18001d5c5  xor     edx, edx; Mask
0x18001d5c7  xor     ecx, ecx; NewValue
0x18001d5c9  mov     [rbp+3Fh+var_78], r14
0x18001d5cd  mov     rbx, r8
0x18001d5d0  call    cs:__imp__controlfp
0x18001d5d6  mov     edx, 30F031Fh; Mask
0x18001d5db  mov     ecx, 1Fh; NewValue
0x18001d5e0  mov     [rbp+3Fh+NewValue], eax
0x18001d5e3  call    cs:__imp__controlfp
0x18001d5e9  mov     rax, [rbx+2A0h]
0x18001d5f0  mov     [rsi+178h], rax
0x18001d5f7  mov     eax, [rbx+3C0h]
0x18001d5fd  mov     [rsi+218h], eax
0x18001d603  mov     rax, [rbp+3Fh+arg_38]
0x18001d60a  mov     [rdi], r14
0x18001d60d  test    rax, rax
0x18001d610  jnz     loc_18001DC7A
0x18001d616  lea     rcx, [rsi+20h]; Buf
0x18001d61a  mov     rdx, rsp
0x18001d61d  call    _setjmp_0
0x18001d622  test    eax, eax
0x18001d624  jnz     loc_18001DEBB
0x18001d62a  mov     ecx, 30h ; '0'; Size
0x18001d62f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d634  mov     r13, [rbp+3Fh+arg_0]
0x18001d638  mov     rbx, rax
0x18001d63b  mov     [rbp+3Fh+var_90], r13
0x18001d63f  test    rax, rax
0x18001d642  jz      loc_18001DD31
0x18001d648  mov     [rax], r14
0x18001d64b  mov     [rax+8], r14
0x18001d64f  mov     dword ptr [rax+10h], 100h
0x18001d656  mov     dword ptr [rax+14h], 4000h
0x18001d65d  mov     [rax+18h], r14
0x18001d661  lea     rax, [r13+20h]
0x18001d665  mov     [rbx+28h], rax
0x18001d669  test    rbx, rbx
0x18001d66c  jz      short loc_18001D68A
0x18001d66e  mov     rcx, rbx; this
0x18001d671  call    ?Init@HashTbl@@AEAAHI@Z; HashTbl::Init(uint)
0x18001d676  test    eax, eax
0x18001d678  jnz     short loc_18001D68D
0x18001d67a  mov     rcx, rbx; this
0x18001d67d  call    ?FreeAll@NoRelAlloc@@QEAAXXZ; NoRelAlloc::FreeAll(void)
0x18001d682  mov     rcx, rbx; Block
0x18001d685  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001d68a  mov     rbx, r14
0x18001d68d  mov     [r13+0], rbx
0x18001d691  test    rbx, rbx
0x18001d694  jz      loc_18001DE50
0x18001d69a  mov     ecx, 1A0h; Size
0x18001d69f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d6a4  test    rax, rax
0x18001d6a7  jz      loc_18001DD13
0x18001d6ad  lea     r9, [r13+20h]; struct ErrHandler *
0x18001d6b1  mov     rdx, rbx; struct HashTbl *
0x18001d6b4  lea     r8, [r13+140h]; struct Token *
0x18001d6bb  mov     rcx, rax; this
0x18001d6be  call    ??0Scanner@@AEAA@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Scanner(HashTbl *,Token *,ErrHandler *)
0x18001d6c3  mov     rcx, rax
0x18001d6c6  mov     [r13+150h], rcx
0x18001d6cd  test    rcx, rcx
0x18001d6d0  jz      loc_18001DE5E
0x18001d6d6  mov     rax, [rbp+3Fh+arg_48]
0x18001d6dd  mov     ebx, [rbp+3Fh+arg_20]
0x18001d6e0  mov     [rcx+58h], rax
0x18001d6e4  and     ebx, 0FFFFFFBFh
0x18001d6e7  mov     rax, [rbp+3Fh+arg_18]
0x18001d6eb  mov     ecx, 0FEFFh
0x18001d6f0  mov     r9, [r13+150h]
0x18001d6f7  mov     r11, rax
0x18001d6fa  mov     [r13+13Ch], ebx
0x18001d701  mov     [r13+188h], r14
0x18001d708  mov     [rbp+3Fh+var_60], rax
0x18001d70c  movzx   eax, word ptr [rax]
0x18001d70f  mov     [rbp+3Fh+var_80], r14
0x18001d713  cmp     cx, ax
0x18001d716  jz      loc_18001DE6C
0x18001d71c  mov     ecx, 0FFFEh
0x18001d721  cmp     cx, ax
0x18001d724  jz      loc_18001DE6C
0x18001d72a  mov     [r9+10h], r11
0x18001d72e  mov     r10d, r14d
0x18001d731  mov     [r9+20h], r11
0x18001d735  mov     rdx, r11
0x18001d738  mov     [r9+18h], r11
0x18001d73c  mov     [r9+28h], r11
0x18001d740  mov     [r9+30h], r11
0x18001d744  mov     [r9+44h], r14d
0x18001d748  nop     dword ptr [rax+rax+00000000h]
0x18001d750  movzx   r8d, word ptr [rdx]
0x18001d754  lea     rcx, [rdx+2]
0x18001d758  mov     [r9+28h], rcx
0x18001d75c  mov     eax, r8d
0x18001d75f  test    r8d, r8d
0x18001d762  jz      loc_18001D7F4
0x18001d768  sub     eax, 0Ah
0x18001d76b  jz      short loc_18001D783
0x18001d76d  sub     eax, 3
0x18001d770  jz      short loc_18001D783
0x18001d772  sub     eax, 201Bh
0x18001d777  jz      short loc_18001D783
0x18001d779  cmp     eax, 1
0x18001d77c  jz      short loc_18001D783
0x18001d77e  mov     rdx, rcx
0x18001d781  jmp     short loc_18001D750
0x18001d783  cmp     r8d, 0Dh
0x18001d787  jnz     short loc_18001D7EC
0x18001d789  cmp     word ptr [rcx], 0Ah
0x18001d78d  jnz     short loc_18001D7EC
0x18001d78f  add     rdx, 4
0x18001d793  mov     [r9+28h], rdx
0x18001d797  mov     r8, rdx
0x18001d79a  sub     r8, [r9+18h]
0x18001d79e  mov     ecx, r14d
0x18001d7a1  sar     r8, 1
0x18001d7a4  mov     eax, r14d
0x18001d7a7  test    r8d, 0F0000000h
0x18001d7ae  mov     [r9+18h], rdx
0x18001d7b2  setnz   cl
0x18001d7b5  test    r8d, 0FFFFFF80h
0x18001d7bc  setnz   al
0x18001d7bf  inc     eax
0x18001d7c1  add     ecx, eax
0x18001d7c3  mov     eax, r14d
0x18001d7c6  test    r8d, 0FFFFC000h
0x18001d7cd  setnz   al
0x18001d7d0  add     ecx, eax
0x18001d7d2  mov     eax, r14d
0x18001d7d5  test    r8d, 0FFE00000h
0x18001d7dc  setnz   al
0x18001d7df  add     ecx, eax
0x18001d7e1  mov     [rbp+3Fh+var_68], ecx
0x18001d7e4  add     r10d, ecx
0x18001d7e7  jmp     loc_18001D750
0x18001d7ec  mov     rdx, rcx
0x18001d7ef  mov     r8, rcx
0x18001d7f2  jmp     short loc_18001D79A
0x18001d7f4  mov     rax, [r9+8]
0x18001d7f8  mov     [r9+28h], r11
0x18001d7fc  mov     [r9+18h], r11
0x18001d800  mov     [r9+44h], r10d
0x18001d804  mov     [r9+198h], r14d
0x18001d80b  mov     [rax], r14d
0x18001d80e  mov     eax, ebx
0x18001d810  xor     eax, [r9+40h]
0x18001d814  and     dword ptr [r9+60h], 0FFFFFFC7h
0x18001d819  and     eax, 0FFFFFFFEh
0x18001d81c  xor     eax, ebx
0x18001d81e  shr     ebx, 2
0x18001d821  mov     [r9+40h], eax
0x18001d825  and     ebx, 20h
0x18001d828  or      [r9+60h], ebx
0x18001d82c  mov     rcx, [r13+150h]
0x18001d833  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18001d838  mov     rax, [r13+150h]
0x18001d83f  lea     rdi, [r13+1Ch]
0x18001d843  mov     r14d, [r13+14h]
0x18001d847  mov     esi, [r13+10h]
0x18001d84b  mov     r15, [rax+20h]
0x18001d84f  mov     r12, [rax+10h]
0x18001d853  mov     eax, r14d
0x18001d856  sub     eax, esi
0x18001d858  cmp     eax, 68h ; 'h'
0x18001d85b  jl      loc_18001DB12
0x18001d861  xor     edx, edx
0x18001d863  mov     rbx, [r13+8]
0x18001d867  lea     eax, [rsi+68h]
0x18001d86a  add     rbx, 8
0x18001d86e  movsxd  rcx, esi
0x18001d871  add     rbx, rcx
0x18001d874  mov     [r13+10h], eax
0x18001d878  test    rbx, rbx
0x18001d87b  jz      loc_18001DE75
0x18001d881  mov     qword ptr [rbx], 46h ; 'F'
0x18001d888  lea     r8, [rbp+3Fh+var_80]; struct ParseNode ***
0x18001d88c  sub     r15, r12
0x18001d88f  mov     [rbp+3Fh+var_58], rbx
0x18001d893  sar     r15, 1
0x18001d896  mov     [rbx+8], r15d
0x18001d89a  lea     r15, [rbx+50h]
0x18001d89e  mov     rax, [r13+150h]
0x18001d8a5  mov     rcx, [rax+28h]
0x18001d8a9  sub     rcx, [rax+10h]
0x18001d8ad  lea     rax, [rbx+30h]
0x18001d8b1  sar     rcx, 1
0x18001d8b4  mov     [rbx+0Ch], ecx
0x18001d8b7  mov     rcx, r13; this
0x18001d8ba  mov     [rbx+58h], edx
0x18001d8bd  mov     dword ptr [r13+170h], 1
0x18001d8c8  mov     [rax], rdx
0x18001d8cb  mov     [rbx+4], edx
0x18001d8ce  mov     [rbx+20h], rdx
0x18001d8d2  mov     [rbx+18h], rdx
0x18001d8d6  mov     [rbx+60h], edx
0x18001d8d9  mov     [rbx+28h], rdx
0x18001d8dd  mov     [rbx+10h], rdx
0x18001d8e1  mov     [r13+160h], rax
0x18001d8e8  lea     rax, [rbx+40h]
0x18001d8ec  mov     [r13+158h], rdx
0x18001d8f3  mov     dword ptr [r13+138h], 1
0x18001d8fe  mov     [rax], rdx
0x18001d901  mov     [rbx+38h], rdx
0x18001d905  mov     [r13+190h], rdx
0x18001d90c  mov     rdx, r15; struct ParseNode **
0x18001d90f  mov     [r13+168h], rax
0x18001d916  call    ?ParseStmtList@Parser@@AEAAXPEAPEAUParseNode@@PEAPEAPEAU2@@Z; Parser::ParseStmtList(ParseNode * *,ParseNode * * *)
0x18001d91b  cmp     dword ptr [r13+140h], 7Fh
0x18001d923  jnz     loc_18001DE83
0x18001d929  mov     rax, [r13+150h]
0x18001d930  mov     r10, [rbp+3Fh+var_90]
0x18001d934  mov     r13, [rax+20h]
0x18001d938  mov     rax, [rax+10h]
0x18001d93c  mov     r12d, [r10+14h]
0x18001d940  mov     r14d, [r10+10h]
0x18001d944  mov     [rbp+3Fh+var_70], rax
0x18001d948  mov     eax, r12d
0x18001d94b  sub     eax, r14d
0x18001d94e  cmp     eax, 10h
0x18001d951  jl      loc_18001DB87
0x18001d957  mov     rsi, [r10+8]
0x18001d95b  lea     eax, [r14+10h]
0x18001d95f  add     rsi, 8
0x18001d963  movsxd  rcx, r14d
0x18001d966  add     rsi, rcx
0x18001d969  mov     [r10+10h], eax
0x18001d96d  test    rsi, rsi
0x18001d970  jz      loc_18001DE91
0x18001d976  sub     r13, [rbp+3Fh+var_70]
0x18001d97a  mov     r12, [rbp+3Fh+var_80]
0x18001d97e  mov     qword ptr [rsi], 47h ; 'G'
0x18001d985  sar     r13, 1
0x18001d988  mov     [rsi+8], r13d
0x18001d98c  mov     rax, [r10+150h]
0x18001d993  mov     [rbp+3Fh+var_70], rsi
0x18001d997  mov     rcx, [rax+28h]
0x18001d99b  sub     rcx, [rax+10h]
0x18001d99f  sar     rcx, 1
0x18001d9a2  mov     [rsi+0Ch], ecx
0x18001d9a5  test    r12, r12
0x18001d9a8  jnz     loc_18001DBFF
0x18001d9ae  mov     [r15], rsi
0x18001d9b1  mov     dword ptr [rsi+8], 0
0x18001d9b8  mov     rax, [r15]
0x18001d9bb  mov     [rbp+3Fh+var_80], r15
0x18001d9bf  mov     [rbp+3Fh+var_48], rbx
0x18001d9c3  mov     [rbp+3Fh+var_78], rbx
0x18001d9c7  mov     dword ptr [rax+0Ch], 0
0x18001d9ce  mov     rax, [r10+150h]
0x18001d9d5  mov     rcx, [rax+28h]
0x18001d9d9  sub     rcx, [rax+10h]
0x18001d9dd  sar     rcx, 1
0x18001d9e0  mov     [rbx+0Ch], ecx
0x18001d9e3  mov     rax, [r10+168h]
0x18001d9ea  mov     rcx, [rax]
0x18001d9ed  mov     [rbx+48h], rcx
0x18001d9f1  mov     rax, [r10+168h]
0x18001d9f8  mov     qword ptr [rax], 0
0x18001d9ff  mov     rdx, [r10+150h]
0x18001da06  mov     rsi, [rdx+20h]
0x18001da0a  sub     rsi, [rdx+10h]
0x18001da0e  mov     rcx, [rdx+180h]
0x18001da15  mov     eax, [rdx+188h]
0x18001da1b  sub     eax, ecx
0x18001da1d  sar     rsi, 1
0x18001da20  mov     [r10+228h], eax
0x18001da27  mov     qword ptr [rdx+190h], 0
0x18001da32  mov     qword ptr [rdx+188h], 0
0x18001da3d  mov     qword ptr [rdx+180h], 0
0x18001da48  mov     rdi, [r10+150h]
0x18001da4f  mov     [r10+220h], rcx
0x18001da56  test    rdi, rdi
0x18001da59  jz      short loc_18001DA6F
0x18001da5b  mov     rcx, rdi; this
0x18001da5e  call    ??1Scanner@@AEAA@XZ; Scanner::~Scanner(void)
0x18001da63  mov     rcx, rdi; Block
0x18001da66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001da6b  mov     r10, [rbp+3Fh+var_90]
0x18001da6f  mov     rax, [rbp+3Fh+arg_40]
0x18001da76  mov     rdx, rbx; struct ParseNode *
0x18001da79  mov     r9d, [rbp+3Fh+arg_30]; int
0x18001da7d  mov     rcx, r10; this
0x18001da80  mov     r8, [rbp+3Fh+arg_28]; void *
  ... truncated ...
```
