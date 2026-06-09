# JSONParser::ParseObject(CSession *,VAR *)

- ea: `0x18006db48`
- end: `0x18006e16c`
- name: `?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z`
- size: `1572`
- prototype: `void __fastcall(JSONParser *__hidden this, struct CSession *, struct VAR *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18006db48`
- `0x18006e174`

## callees

- `0x18000ad40`
- `0x18000bf44`
- `0x18000ded0`
- `0x18000ea20`
- `0x180016498`
- `0x180016714`
- `0x180018514`
- `0x180018d68`
- `0x18001f400`
- `0x1800304c0`
- `0x18003efe0`
- `0x1800487e0`
- `0x1800576a0`
- `0x180068f2c`
- `0x180069c04`
- `0x18006db48`
- `0x180094282`
- `0x18009428e`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x18006de63`
- `msvcrt!free` at `0x18006dea6`
- `msvcrt!free` at `0x18006deb7`
- `msvcrt!free` at `0x18006de63`
- `msvcrt!free` at `0x18006dea6`
- `msvcrt!free` at `0x18006deb7`
- `msvcrt!malloc` at `0x18006ddd5`
- `msvcrt!malloc` at `0x18006ddd5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e0cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e0cd`

## pseudocode

```c
void __fastcall JSONParser::ParseObject(JSONParser *this, struct CSession *a2, struct VAR *a3)
{
  struct VAR *v4; // rbx
  struct CSession *v5; // r13
  signed int v6; // esi
  struct VAR *v7; // rax
  struct VAR *v8; // r14
  int v9; // eax
  _DWORD *v10; // rsi
  char *v11; // rax
  int *v12; // r14
  bool v13; // zf
  size_t v14; // r13
  int v15; // r8d
  int v16; // r15d
  char *v17; // rax
  __int64 v18; // r15
  _QWORD *v19; // r14
  int v20; // r13d
  int *v21; // rbx
  __int64 v22; // xmm1_8
  __int64 v23; // rax
  __int64 v24; // rdx
  int TypeProto; // esi
  int v26; // esi
  struct NameTbl *v27; // rsi
  int v28; // ebx
  int v29; // eax
  struct VAR *v30; // r9
  int v31; // eax
  struct NameTbl *v32; // rsi
  int v33; // ebx
  __int64 v34; // rcx
  __int64 v35; // rbx
  __int64 v36; // rdx
  __int64 v37; // rcx
  const unsigned __int16 *v38; // rdx
  OLECHAR *v39; // rbx
  const unsigned __int16 *v40; // rax
  int v41; // r14d
  int v42; // [rsp+20h] [rbp-60h]
  struct NameTbl *v43; // [rsp+40h] [rbp-40h] BYREF
  int *v44; // [rsp+48h] [rbp-38h]
  __int128 Src; // [rsp+50h] [rbp-30h] BYREF
  __int64 v46; // [rsp+60h] [rbp-20h]
  __int128 v47; // [rsp+68h] [rbp-18h] BYREF
  __int64 v48; // [rsp+78h] [rbp-8h]
  int v51; // [rsp+D8h] [rbp+58h]
  char *v52; // [rsp+D8h] [rbp+58h]

  v43 = 0;
  v4 = a3;
  v5 = a2;
  if ( !(unsigned int)FStackAvailable(0x10000u) )
    goto LABEL_78;
  switch ( *((_DWORD *)this + 72) )
  {
    case 0x18:
      *(_WORD *)v4 = 11;
      *((_WORD *)v4 + 4) = 0;
      goto LABEL_19;
    case 0x2D:
      *(_WORD *)v4 = 1;
      goto LABEL_19;
    case 0x3F:
      *(_WORD *)v4 = 11;
      *((_WORD *)v4 + 4) = -1;
      goto LABEL_19;
  }
  if ( *((_DWORD *)this + 72) != 79 )
  {
    if ( *((_DWORD *)this + 72) == 113 )
    {
      Scanner::Scan(*((_QWORD *)this + 38));
      if ( *((_DWORD *)this + 72) != 128 )
      {
        if ( *((_DWORD *)this + 72) == 129 && (*(_BYTE *)(*((_QWORD *)this + 38) + 96LL) & 4) == 0 )
        {
          *(_WORD *)v4 = 5;
          *((_QWORD *)v4 + 1) = *((_QWORD *)this + 37) ^ _xmm;
          goto LABEL_19;
        }
        goto LABEL_49;
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 38) + 96LL) & 4) != 0 )
        goto LABEL_49;
      *(_WORD *)v4 = 3;
      v9 = -*((_DWORD *)this + 74);
LABEL_18:
      *((_DWORD *)v4 + 2) = v9;
      goto LABEL_19;
    }
    if ( *((_DWORD *)this + 72) != 122 )
    {
      if ( *((_DWORD *)this + 72) != 128 )
      {
        if ( *((_DWORD *)this + 72) == 129 )
        {
          if ( (*(_BYTE *)(*((_QWORD *)this + 38) + 96LL) & 4) == 0 )
          {
            *(_WORD *)v4 = 5;
            *((_QWORD *)v4 + 1) = *((_QWORD *)this + 37);
            goto LABEL_19;
          }
        }
        else if ( *((_DWORD *)this + 72) == 130 && (*(_BYTE *)(*((_QWORD *)this + 38) + 96LL) & 2) != 0 )
        {
          v6 = 2 * *(_DWORD *)(*((_QWORD *)this + 37) + 40LL);
          v7 = PvarAllocBstrByteLen(v6, v5);
          v8 = v7;
          if ( !v7 )
            goto LABEL_78;
          memcpy_0(*((void **)v7 + 1), (const void *)(*((_QWORD *)this + 37) + 44LL), v6);
          *(_WORD *)v4 = 128;
          *((_QWORD *)v4 + 1) = v8;
LABEL_19:
          Scanner::Scan(*((_QWORD *)this + 38));
          return;
        }
LABEL_49:
        JSONParser::Error(this, 1002);
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 38) + 96LL) & 4) != 0 )
        goto LABEL_49;
      *(_WORD *)v4 = 3;
      v9 = *((_DWORD *)this + 74);
      goto LABEL_18;
    }
    v10 = operator new(0x20u);
    if ( !v10 )
      goto LABEL_78;
    v10[3] = 24;
    *(_QWORD *)v10 = &GL::`vftable';
    v10[2] = 1;
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    Scanner::Scan(*((_QWORD *)this + 38));
    v11 = (char *)(v10 + 3);
    v12 = v10 + 7;
    while ( 1 )
    {
      v13 = *((_DWORD *)this + 72) == 78;
      v44 = (int *)v11;
      if ( v13 )
      {
LABEL_33:
        JSONParser::ChkCurTok(this, 78, 1007);
        v18 = *v12;
        v19 = malloc(24 * v18);
        if ( v19 )
        {
          v20 = 0;
          if ( (int)v18 > 0 )
          {
            v21 = v44;
            do
            {
              memcpy_0(&Src, (const void *)(*((_QWORD *)v10 + 2) + v20 * *v21), *v21);
              v22 = v46;
              v23 = (int)v18 - v20++;
              v24 = 3 * v23;
              *(_OWORD *)&v19[v24 - 3] = Src;
              v19[v24 - 1] = v22;
            }
            while ( v20 < (int)v18 );
            v4 = a3;
          }
          GL::Release((GL *)v10);
          TypeProto = CSession::GetTypeProto(*((CSession **)this + 39), 0, (struct VAR *)&Src);
          if ( TypeProto < 0 )
          {
            free(v19);
            JSONParser::Error(this, TypeProto);
          }
          v26 = ArrayObj::Create(
                  &v43,
                  *((struct CSession **)this + 39),
                  v18,
                  (struct VAR *)v19,
                  (struct VAR *)&Src,
                  0,
                  0);
          if ( v26 < 0 )
          {
            free(v19);
            JSONParser::Error(this, v26);
          }
          free(v19);
          v27 = v43;
          v28 = VAR::SetHeapJsObj(v4, *((struct CSession **)this + 39), v43);
          if ( v28 < 0 )
          {
            (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v27 + 16LL))(v27);
            JSONParser::Error(this, v28);
          }
          return;
        }
LABEL_78:
        JSONParser::Error(this, 1001);
      }
      JSONParser::ParseObject(this, v5, (struct VAR *)&Src);
      v14 = (int)v10[3];
      v12 = v10 + 7;
      v15 = v10[7];
      v51 = v15;
      v44 = v10 + 3;
      v16 = v14 * (v15 + 1);
      if ( v16 > v10[6] )
      {
        if ( !(unsigned int)GL::FEnsureSize((GL *)v10, v16) )
          goto LABEL_30;
        v15 = v51;
      }
      v17 = (char *)(v15 * (int)v14 + *((_QWORD *)v10 + 2));
      v52 = v17;
      if ( v15 < *v12 )
      {
        memmove_0(&v17[v14], v17, v16 - v15 * (int)v14 - (int)v14);
        v17 = v52;
      }
      memcpy_0(v17, &Src, v14);
      ++*v12;
LABEL_30:
      if ( *((_DWORD *)this + 72) != 81 )
        goto LABEL_33;
      Scanner::Scan(*((_QWORD *)this + 38));
      if ( *((_DWORD *)this + 72) == 78 )
        goto LABEL_49;
      v11 = (char *)v44;
      v5 = a2;
    }
  }
  v29 = CSession::GetTypeProto(*((CSession **)this + 39), 5, v4);
  if ( v29 < 0 )
    JSONParser::Error(this, v29);
  v31 = NameTbl::Create(&v43, *((struct CSession **)this + 39), v4, v30, v42);
  if ( v31 < 0 )
    JSONParser::Error(this, v31);
  v32 = v43;
  v33 = VAR::SetHeapJsObj(v4, *((struct CSession **)this + 39), v43);
  if ( v33 < 0 )
  {
    (*(void (__fastcall **)(struct NameTbl *))(*(_QWORD *)v32 + 16LL))(v32);
    JSONParser::Error(this, v33);
  }
  Scanner::Scan(*((_QWORD *)this + 38));
  if ( *((_DWORD *)this + 72) == 80 )
    goto LABEL_19;
  while ( 1 )
  {
    if ( *((_DWORD *)this + 72) != 130 || (v34 = *((_QWORD *)this + 38), (*(_BYTE *)(v34 + 96) & 2) == 0) )
      JSONParser::Error(this, 1002);
    v35 = *((_QWORD *)this + 37);
    v47 = 0;
    v48 = 0;
    Scanner::Scan(v34);
    JSONParser::ChkCurTok(this, 95, 1003);
    JSONParser::ParseObject(this, v5, (struct VAR *)&Src);
    v36 = *(unsigned int *)(v35 + 40);
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)(v35 + 44 + 2 * v37) );
    if ( v37 == v36 )
    {
      v38 = (const unsigned __int16 *)(v35 + 44);
      v39 = 0;
      SYM::InitFromPsz((SYM *)&v47, v38);
    }
    else
    {
      v40 = _SysAllocStringLen((const unsigned __int16 *)(v35 + 44), v36);
      v39 = (OLECHAR *)v40;
      if ( !v40 )
        JSONParser::Error(this, 1001);
      SYM::InitFromBstr((SYM *)&v47, v40);
    }
    v41 = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, __int128 *))(*(_QWORD *)v32 + 272LL))(
            v32,
            &v47,
            &Src);
    if ( v39 )
      SysFreeString(v39);
    if ( v41 < 0 )
      JSONParser::Error(this, v41);
    if ( *((_DWORD *)this + 72) != 81 )
      break;
    Scanner::Scan(*((_QWORD *)this + 38));
  }
  JSONParser::ChkCurTok(this, 80, 1009);
}

```

## disassembly

```asm
0x18006db48  mov     [rsp-38h+arg_0], rbx
0x18006db4d  mov     [rsp-38h+arg_10], r8
0x18006db52  mov     [rsp-38h+arg_8], rdx
0x18006db57  push    rbp
0x18006db58  push    rsi
0x18006db59  push    rdi
0x18006db5a  push    r12
0x18006db5c  push    r13
0x18006db5e  push    r14
0x18006db60  push    r15
0x18006db62  mov     rbp, rsp
0x18006db65  sub     rsp, 80h
0x18006db6c  mov     rdi, rcx
0x18006db6f  xor     r14d, r14d
0x18006db72  mov     ecx, 10000h; unsigned int
0x18006db77  mov     [rbp+var_40], r14
0x18006db7b  mov     rbx, r8
0x18006db7e  mov     r13, rdx
0x18006db81  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18006db86  test    eax, eax
0x18006db88  jz      loc_18006E15E
0x18006db8e  mov     ecx, [rdi+120h]
0x18006db94  sub     ecx, 18h
0x18006db97  jz      loc_18006E14F
0x18006db9d  sub     ecx, 15h
0x18006dba0  jz      loc_18006E145
0x18006dba6  sub     ecx, 12h
0x18006dba9  jz      loc_18006E135
0x18006dbaf  sub     ecx, 10h
0x18006dbb2  jz      loc_18006DF6E
0x18006dbb8  sub     ecx, 22h ; '"'
0x18006dbbb  jz      loc_18006DEF7
0x18006dbc1  sub     ecx, 9
0x18006dbc4  jz      loc_18006DC9F
0x18006dbca  sub     ecx, 6
0x18006dbcd  jz      loc_18006DC59
0x18006dbd3  sub     ecx, 1
0x18006dbd6  jz      short loc_18006DC36
0x18006dbd8  cmp     ecx, 1
0x18006dbdb  jnz     loc_18006DF4E
0x18006dbe1  mov     rax, [rdi+130h]
0x18006dbe8  test    byte ptr [rax+60h], 2
0x18006dbec  jz      loc_18006DF4E
0x18006dbf2  mov     rax, [rdi+128h]
0x18006dbf9  mov     rdx, r13; struct CSession *
0x18006dbfc  mov     esi, [rax+28h]
0x18006dbff  add     esi, esi
0x18006dc01  mov     ecx, esi; len
0x18006dc03  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x18006dc08  mov     r14, rax
0x18006dc0b  test    rax, rax
0x18006dc0e  jz      loc_18006E15E
0x18006dc14  mov     rdx, [rdi+128h]
0x18006dc1b  mov     rcx, [rax+8]; void *
0x18006dc1f  add     rdx, 2Ch ; ','; Src
0x18006dc23  movsxd  r8, esi; Size
0x18006dc26  call    memcpy_0
0x18006dc2b  mov     word ptr [rbx], 80h
0x18006dc30  mov     [rbx+8], r14
0x18006dc34  jmp     short loc_18006DC78
0x18006dc36  mov     rax, [rdi+130h]
0x18006dc3d  test    byte ptr [rax+60h], 4
0x18006dc41  jnz     loc_18006DF4E
0x18006dc47  mov     word ptr [rbx], 5
0x18006dc4c  mov     rax, [rdi+128h]
0x18006dc53  mov     [rbx+8], rax
0x18006dc57  jmp     short loc_18006DC78
0x18006dc59  mov     rax, [rdi+130h]
0x18006dc60  test    byte ptr [rax+60h], 4
0x18006dc64  jnz     loc_18006DF4E
0x18006dc6a  mov     word ptr [rbx], 3
0x18006dc6f  mov     eax, [rdi+128h]
0x18006dc75  mov     [rbx+8], eax
0x18006dc78  mov     rcx, [rdi+130h]
0x18006dc7f  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006dc84  mov     rbx, [rsp+80h+arg_0]
0x18006dc8c  add     rsp, 80h
0x18006dc93  pop     r15
0x18006dc95  pop     r14
0x18006dc97  pop     r13
0x18006dc99  pop     r12
0x18006dc9b  pop     rdi
0x18006dc9c  pop     rsi
0x18006dc9d  pop     rbp
0x18006dc9e  retn
0x18006dc9f  mov     ecx, 20h ; ' '; Size
0x18006dca4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006dca9  mov     rsi, rax
0x18006dcac  test    rax, rax
0x18006dcaf  jz      loc_18006E15E
0x18006dcb5  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18006dcbc  mov     dword ptr [rsi+0Ch], 18h
0x18006dcc3  mov     [rsi], rax
0x18006dcc6  mov     r12d, 1
0x18006dccc  mov     [rsi+8], r12d
0x18006dcd0  mov     [rsi+10h], r14
0x18006dcd4  mov     [rsi+18h], r14
0x18006dcd8  mov     rcx, [rdi+130h]
0x18006dcdf  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006dce4  lea     rax, [rsi+0Ch]
0x18006dce8  lea     r14, [rsi+1Ch]
0x18006dcec  cmp     dword ptr [rdi+120h], 4Eh ; 'N'
0x18006dcf3  mov     [rbp+var_38], rax
0x18006dcf7  jz      loc_18006DDB7
0x18006dcfd  lea     r8, [rbp+Src]; struct VAR *
0x18006dd01  mov     rdx, r13; struct CSession *
0x18006dd04  mov     rcx, rdi; this
0x18006dd07  call    ?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z; JSONParser::ParseObject(CSession *,VAR *)
0x18006dd0c  lea     rax, [rsi+0Ch]
0x18006dd10  movsxd  r13, dword ptr [rax]
0x18006dd13  lea     r14, [rsi+1Ch]
0x18006dd17  mov     r8d, [r14]
0x18006dd1a  mov     dword ptr [rbp+arg_18], r8d
0x18006dd1e  mov     [rbp+var_38], rax
0x18006dd22  lea     r15d, [r8+1]
0x18006dd26  imul    r15d, r13d
0x18006dd2a  cmp     r15d, [rsi+18h]
0x18006dd2e  jle     short loc_18006DD43
0x18006dd30  mov     edx, r15d; int
0x18006dd33  mov     rcx, rsi; this
0x18006dd36  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18006dd3b  test    eax, eax
0x18006dd3d  jz      short loc_18006DD88
0x18006dd3f  mov     r8d, dword ptr [rbp+arg_18]
0x18006dd43  mov     rax, [rsi+10h]
0x18006dd47  mov     edx, r13d
0x18006dd4a  imul    edx, r8d
0x18006dd4e  movsxd  rcx, edx
0x18006dd51  add     rax, rcx
0x18006dd54  mov     [rbp+arg_18], rax
0x18006dd58  cmp     r8d, [r14]
0x18006dd5b  jge     short loc_18006DD76
0x18006dd5d  sub     r15d, edx
0x18006dd60  lea     rcx, [rax+r13]; void *
0x18006dd64  sub     r15d, r13d
0x18006dd67  mov     rdx, rax; Src
0x18006dd6a  movsxd  r8, r15d; Size
0x18006dd6d  call    memmove_0
0x18006dd72  mov     rax, [rbp+arg_18]
0x18006dd76  mov     r8, r13; Size
0x18006dd79  lea     rdx, [rbp+Src]; Src
0x18006dd7d  mov     rcx, rax; void *
0x18006dd80  call    memcpy_0
0x18006dd85  add     [r14], r12d
0x18006dd88  cmp     dword ptr [rdi+120h], 51h ; 'Q'
0x18006dd8f  jnz     short loc_18006DDB7
0x18006dd91  mov     rcx, [rdi+130h]
0x18006dd98  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006dd9d  cmp     dword ptr [rdi+120h], 4Eh ; 'N'
0x18006dda4  jz      loc_18006DF4E
0x18006ddaa  mov     rax, [rbp+var_38]
0x18006ddae  mov     r13, [rbp+arg_8]
0x18006ddb2  jmp     loc_18006DCEC
0x18006ddb7  mov     edx, 4Eh ; 'N'; int
0x18006ddbc  mov     r8d, 3EFh; int
0x18006ddc2  mov     rcx, rdi; this
0x18006ddc5  call    ?ChkCurTok@JSONParser@@AEAAXHH@Z; JSONParser::ChkCurTok(int,int)
0x18006ddca  movsxd  r15, dword ptr [r14]
0x18006ddcd  lea     rcx, [r15+r15*2]
0x18006ddd1  shl     rcx, 3; Size
0x18006ddd5  call    cs:__imp_malloc
0x18006dddb  mov     r14, rax
0x18006ddde  xor     eax, eax
0x18006dde0  test    r14, r14
0x18006dde3  jz      loc_18006E15E
0x18006dde9  mov     r13d, eax
0x18006ddec  test    r15d, r15d
0x18006ddef  jle     short loc_18006DE3D
0x18006ddf1  mov     rbx, [rbp+var_38]
0x18006ddf5  movsxd  rcx, dword ptr [rbx]
0x18006ddf8  mov     r8, rcx; Size
0x18006ddfb  imul    ecx, r13d
0x18006ddff  movsxd  rdx, ecx
0x18006de02  lea     rcx, [rbp+Src]; void *
0x18006de06  add     rdx, [rsi+10h]; Src
0x18006de0a  call    memcpy_0
0x18006de0f  movups  xmm0, [rbp+Src]
0x18006de13  mov     eax, r15d
0x18006de16  movsd   xmm1, [rbp+var_20]
0x18006de1b  sub     eax, r13d
0x18006de1e  cdqe
0x18006de20  add     r13d, r12d
0x18006de23  lea     rdx, [rax+rax*2]
0x18006de27  movups  xmmword ptr [r14+rdx*8-18h], xmm0
0x18006de2d  movsd   qword ptr [r14+rdx*8-8], xmm1
0x18006de34  cmp     r13d, r15d
0x18006de37  jl      short loc_18006DDF5
0x18006de39  mov     rbx, [rbp+arg_10]
0x18006de3d  mov     rcx, rsi; this
0x18006de40  call    ?Release@GL@@QEAAXXZ; GL::Release(void)
0x18006de45  mov     rcx, [rdi+138h]; this
0x18006de4c  lea     r8, [rbp+Src]; struct VAR *
0x18006de50  xor     edx, edx; int
0x18006de52  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x18006de57  xor     r12d, r12d
0x18006de5a  mov     esi, eax
0x18006de5c  test    eax, eax
0x18006de5e  jns     short loc_18006DE74
0x18006de60  mov     rcx, r14; Block
0x18006de63  call    cs:__imp_free
0x18006de69  mov     edx, esi; int
0x18006de6b  mov     rcx, rdi; this
0x18006de6e  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006de74  mov     rdx, [rdi+138h]; struct CSession *
0x18006de7b  lea     rax, [rbp+Src]
0x18006de7f  mov     [rsp+80h+var_50], r12d; int
0x18006de84  lea     rcx, [rbp+var_40]; struct ArrayObj **
0x18006de88  mov     [rsp+80h+var_58], r12d; int
0x18006de8d  mov     r9, r14; struct VAR *
0x18006de90  mov     r8d, r15d; int
0x18006de93  mov     [rsp+80h+var_60], rax; struct VAR *
0x18006de98  call    ?Create@ArrayObj@@SAJPEAPEAV1@PEAVCSession@@HPEAVVAR@@2HH@Z; ArrayObj::Create(ArrayObj * *,CSession *,int,VAR *,VAR *,int,int)
0x18006de9d  mov     esi, eax
0x18006de9f  mov     rcx, r14; Block
0x18006dea2  test    eax, eax
0x18006dea4  jns     short loc_18006DEB7
0x18006dea6  call    cs:__imp_free
0x18006deac  mov     edx, esi; int
0x18006deae  mov     rcx, rdi; this
0x18006deb1  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006deb7  call    cs:__imp_free
0x18006debd  mov     rsi, [rbp+var_40]
0x18006dec1  mov     rcx, rbx; this
0x18006dec4  mov     rdx, [rdi+138h]; struct CSession *
0x18006decb  mov     r8, rsi; struct NameTbl *
0x18006dece  call    ?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z; VAR::SetHeapJsObj(CSession *,NameTbl *)
0x18006ded3  mov     ebx, eax
0x18006ded5  test    eax, eax
0x18006ded7  jns     loc_18006DC84
0x18006dedd  mov     rdx, [rsi]
0x18006dee0  mov     rcx, rsi
0x18006dee3  mov     rax, [rdx+10h]
0x18006dee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006deec  mov     edx, ebx; int
0x18006deee  mov     rcx, rdi; this
0x18006def1  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006def7  mov     rcx, [rdi+130h]
0x18006defe  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006df03  mov     ecx, [rdi+120h]
0x18006df09  sub     ecx, 80h
0x18006df0f  jz      short loc_18006DF41
0x18006df11  cmp     ecx, 1
0x18006df14  jnz     short loc_18006DF4E
0x18006df16  mov     rax, [rdi+130h]
0x18006df1d  test    byte ptr [rax+60h], 4
0x18006df21  jnz     short loc_18006DF4E
0x18006df23  mov     word ptr [rbx], 5
0x18006df28  movsd   xmm0, qword ptr [rdi+128h]
0x18006df30  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18006df37  movsd   qword ptr [rbx+8], xmm0
0x18006df3c  jmp     loc_18006DC78
0x18006df41  mov     rax, [rdi+130h]
0x18006df48  test    byte ptr [rax+60h], 4
0x18006df4c  jz      short loc_18006DF5C
0x18006df4e  mov     edx, 3EAh; int
0x18006df53  mov     rcx, rdi; this
0x18006df56  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006df5c  mov     word ptr [rbx], 3
0x18006df61  mov     eax, [rdi+128h]
0x18006df67  neg     eax
0x18006df69  jmp     loc_18006DC75
0x18006df6e  mov     rcx, [rdi+138h]; this
0x18006df75  mov     r8, rbx; struct VAR *
0x18006df78  mov     edx, 5; int
0x18006df7d  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x18006df82  test    eax, eax
0x18006df84  jns     short loc_18006DF91
0x18006df86  mov     edx, eax; int
0x18006df88  mov     rcx, rdi; this
0x18006df8b  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006df91  mov     rdx, [rdi+138h]; struct CSession *
0x18006df98  lea     rcx, [rbp+var_40]; struct NameTbl **
0x18006df9c  mov     r8, rbx; struct VAR *
0x18006df9f  call    ?Create@NameTbl@@SAJPEAPEAV1@PEAVCSession@@PEAVVAR@@2H@Z; NameTbl::Create(NameTbl * *,CSession *,VAR *,VAR *,int)
0x18006dfa4  test    eax, eax
0x18006dfa6  jns     short loc_18006DFB3
0x18006dfa8  mov     edx, eax; int
0x18006dfaa  mov     rcx, rdi; this
0x18006dfad  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006dfb3  mov     rsi, [rbp+var_40]
0x18006dfb7  mov     rcx, rbx; this
0x18006dfba  mov     rdx, [rdi+138h]; struct CSession *
0x18006dfc1  mov     r8, rsi; struct NameTbl *
0x18006dfc4  call    ?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z; VAR::SetHeapJsObj(CSession *,NameTbl *)
0x18006dfc9  mov     ebx, eax
0x18006dfcb  test    eax, eax
0x18006dfcd  jns     short loc_18006DFE9
0x18006dfcf  mov     rdx, [rsi]
0x18006dfd2  mov     rcx, rsi
0x18006dfd5  mov     rax, [rdx+10h]
0x18006dfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dfde  mov     edx, ebx; int
0x18006dfe0  mov     rcx, rdi; this
0x18006dfe3  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006dfe9  mov     rcx, [rdi+130h]
0x18006dff0  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006dff5  cmp     dword ptr [rdi+120h], 50h ; 'P'
0x18006dffc  jz      loc_18006DC78
0x18006e002  or      r15, 0FFFFFFFFFFFFFFFFh
0x18006e006  cmp     dword ptr [rdi+120h], 82h
  ... truncated ...
```
