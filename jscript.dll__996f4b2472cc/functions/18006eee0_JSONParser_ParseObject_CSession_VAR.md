# JSONParser::ParseObject(CSession *,VAR *)

- ea: `0x18006eee0`
- end: `0x18006f527`
- name: `?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z`
- size: `1607`
- prototype: `void __fastcall(JSONParser *__hidden this, struct CSession *, struct VAR *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x18006eee0`
- `0x18006f530`

## callees

- `0x180005660`
- `0x180007e68`
- `0x1800090b0`
- `0x18000b0e0`
- `0x18000bc50`
- `0x1800132f8`
- `0x1800153d4`
- `0x180015c38`
- `0x18001c430`
- `0x18002d9d0`
- `0x180041fdc`
- `0x180049794`
- `0x1800585d0`
- `0x18006a26c`
- `0x18006af44`
- `0x18006eee0`
- `0x180096692`
- `0x18009669e`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x18006f202`
- `msvcrt!free` at `0x18006f24b`
- `msvcrt!free` at `0x18006f262`
- `msvcrt!free` at `0x18006f202`
- `msvcrt!free` at `0x18006f24b`
- `msvcrt!free` at `0x18006f262`
- `msvcrt!malloc` at `0x18006f16e`
- `msvcrt!malloc` at `0x18006f16e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f482`
- `OLEAUT32!__imp_SysFreeString` at `0x18006f482`

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
  struct NameTbl *v42; // [rsp+40h] [rbp-40h] BYREF
  int *v43; // [rsp+48h] [rbp-38h]
  __int128 Src; // [rsp+50h] [rbp-30h] BYREF
  __int64 v45; // [rsp+60h] [rbp-20h]
  __int128 v46; // [rsp+68h] [rbp-18h] BYREF
  __int64 v47; // [rsp+78h] [rbp-8h]
  int v50; // [rsp+D8h] [rbp+58h]
  char *v51; // [rsp+D8h] [rbp+58h]

  v42 = 0;
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
      v43 = (int *)v11;
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
            v21 = v43;
            do
            {
              memcpy_0(&Src, (const void *)(*((_QWORD *)v10 + 2) + v20 * *v21), *v21);
              v22 = v45;
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
                  &v42,
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
          v27 = v42;
          v28 = VAR::SetHeapJsObj(v4, *((struct CSession **)this + 39), v42);
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
      v50 = v15;
      v43 = v10 + 3;
      v16 = v14 * (v15 + 1);
      if ( v16 > v10[6] )
      {
        if ( !(unsigned int)GL::FEnsureSize((GL *)v10, v16) )
          goto LABEL_30;
        v15 = v50;
      }
      v17 = (char *)(v15 * (int)v14 + *((_QWORD *)v10 + 2));
      v51 = v17;
      if ( v15 < *v12 )
      {
        memmove_0(&v17[v14], v17, v16 - v15 * (int)v14 - (int)v14);
        v17 = v51;
      }
      memcpy_0(v17, &Src, v14);
      ++*v12;
LABEL_30:
      if ( *((_DWORD *)this + 72) != 81 )
        goto LABEL_33;
      Scanner::Scan(*((_QWORD *)this + 38));
      if ( *((_DWORD *)this + 72) == 78 )
        goto LABEL_49;
      v11 = (char *)v43;
      v5 = a2;
    }
  }
  v29 = CSession::GetTypeProto(*((CSession **)this + 39), 5, v4);
  if ( v29 < 0 )
    JSONParser::Error(this, v29);
  v31 = NameTbl::Create(&v42, *((struct CSession **)this + 39), v4, v30);
  if ( v31 < 0 )
    JSONParser::Error(this, v31);
  v32 = v42;
  v33 = VAR::SetHeapJsObj(v4, *((struct CSession **)this + 39), v42);
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
    v46 = 0;
    v47 = 0;
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
      SYM::InitFromPsz((SYM *)&v46, v38);
    }
    else
    {
      v40 = _SysAllocStringLen((const unsigned __int16 *)(v35 + 44), v36);
      v39 = (OLECHAR *)v40;
      if ( !v40 )
        JSONParser::Error(this, 1001);
      SYM::InitFromBstr((SYM *)&v46, v40);
    }
    v41 = (*(__int64 (__fastcall **)(struct NameTbl *, __int128 *, __int128 *))(*(_QWORD *)v32 + 272LL))(
            v32,
            &v46,
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
0x18006eee0  mov     [rsp-38h+arg_0], rbx
0x18006eee5  mov     [rsp-38h+arg_10], r8
0x18006eeea  mov     [rsp-38h+arg_8], rdx
0x18006eeef  push    rbp
0x18006eef0  push    rsi
0x18006eef1  push    rdi
0x18006eef2  push    r12
0x18006eef4  push    r13
0x18006eef6  push    r14
0x18006eef8  push    r15
0x18006eefa  mov     rbp, rsp
0x18006eefd  sub     rsp, 80h
0x18006ef04  mov     rdi, rcx
0x18006ef07  xor     r14d, r14d
0x18006ef0a  mov     ecx, 10000h; unsigned int
0x18006ef0f  mov     [rbp+var_40], r14
0x18006ef13  mov     rbx, r8
0x18006ef16  mov     r13, rdx
0x18006ef19  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18006ef1e  test    eax, eax
0x18006ef20  jz      loc_18006F519
0x18006ef26  mov     ecx, [rdi+120h]
0x18006ef2c  sub     ecx, 18h
0x18006ef2f  jz      loc_18006F50A
0x18006ef35  sub     ecx, 15h
0x18006ef38  jz      loc_18006F500
0x18006ef3e  sub     ecx, 12h
0x18006ef41  jz      loc_18006F4F0
0x18006ef47  sub     ecx, 10h
0x18006ef4a  jz      loc_18006F31F
0x18006ef50  sub     ecx, 22h ; '"'
0x18006ef53  jz      loc_18006F2A8
0x18006ef59  sub     ecx, 9
0x18006ef5c  jz      loc_18006F038
0x18006ef62  sub     ecx, 6
0x18006ef65  jz      loc_18006EFF1
0x18006ef6b  sub     ecx, 1
0x18006ef6e  jz      short loc_18006EFCE
0x18006ef70  cmp     ecx, 1
0x18006ef73  jnz     loc_18006F2FF
0x18006ef79  mov     rax, [rdi+130h]
0x18006ef80  test    byte ptr [rax+60h], 2
0x18006ef84  jz      loc_18006F2FF
0x18006ef8a  mov     rax, [rdi+128h]
0x18006ef91  mov     rdx, r13; struct CSession *
0x18006ef94  mov     esi, [rax+28h]
0x18006ef97  add     esi, esi
0x18006ef99  mov     ecx, esi; len
0x18006ef9b  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x18006efa0  mov     r14, rax
0x18006efa3  test    rax, rax
0x18006efa6  jz      loc_18006F519
0x18006efac  mov     rdx, [rdi+128h]
0x18006efb3  mov     rcx, [rax+8]; void *
0x18006efb7  add     rdx, 2Ch ; ','; Src
0x18006efbb  movsxd  r8, esi; Size
0x18006efbe  call    memcpy_0
0x18006efc3  mov     word ptr [rbx], 80h
0x18006efc8  mov     [rbx+8], r14
0x18006efcc  jmp     short loc_18006F010
0x18006efce  mov     rax, [rdi+130h]
0x18006efd5  test    byte ptr [rax+60h], 4
0x18006efd9  jnz     loc_18006F2FF
0x18006efdf  mov     word ptr [rbx], 5
0x18006efe4  mov     rax, [rdi+128h]
0x18006efeb  mov     [rbx+8], rax
0x18006efef  jmp     short loc_18006F010
0x18006eff1  mov     rax, [rdi+130h]
0x18006eff8  test    byte ptr [rax+60h], 4
0x18006effc  jnz     loc_18006F2FF
0x18006f002  mov     word ptr [rbx], 3
0x18006f007  mov     eax, [rdi+128h]
0x18006f00d  mov     [rbx+8], eax
0x18006f010  mov     rcx, [rdi+130h]
0x18006f017  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006f01c  mov     rbx, [rsp+80h+arg_0]
0x18006f024  add     rsp, 80h
0x18006f02b  pop     r15
0x18006f02d  pop     r14
0x18006f02f  pop     r13
0x18006f031  pop     r12
0x18006f033  pop     rdi
0x18006f034  pop     rsi
0x18006f035  pop     rbp
0x18006f036  retn
0x18006f038  mov     ecx, 20h ; ' '; Size
0x18006f03d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f042  mov     rsi, rax
0x18006f045  test    rax, rax
0x18006f048  jz      loc_18006F519
0x18006f04e  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18006f055  mov     dword ptr [rsi+0Ch], 18h
0x18006f05c  mov     [rsi], rax
0x18006f05f  mov     r12d, 1
0x18006f065  mov     [rsi+8], r12d
0x18006f069  mov     [rsi+10h], r14
0x18006f06d  mov     [rsi+18h], r14
0x18006f071  mov     rcx, [rdi+130h]
0x18006f078  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006f07d  lea     rax, [rsi+0Ch]
0x18006f081  lea     r14, [rsi+1Ch]
0x18006f085  cmp     dword ptr [rdi+120h], 4Eh ; 'N'
0x18006f08c  mov     [rbp+var_38], rax
0x18006f090  jz      loc_18006F150
0x18006f096  lea     r8, [rbp+Src]; struct VAR *
0x18006f09a  mov     rdx, r13; struct CSession *
0x18006f09d  mov     rcx, rdi; this
0x18006f0a0  call    ?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z; JSONParser::ParseObject(CSession *,VAR *)
0x18006f0a5  lea     rax, [rsi+0Ch]
0x18006f0a9  movsxd  r13, dword ptr [rax]
0x18006f0ac  lea     r14, [rsi+1Ch]
0x18006f0b0  mov     r8d, [r14]
0x18006f0b3  mov     dword ptr [rbp+arg_18], r8d
0x18006f0b7  mov     [rbp+var_38], rax
0x18006f0bb  lea     r15d, [r8+1]
0x18006f0bf  imul    r15d, r13d
0x18006f0c3  cmp     r15d, [rsi+18h]
0x18006f0c7  jle     short loc_18006F0DC
0x18006f0c9  mov     edx, r15d; int
0x18006f0cc  mov     rcx, rsi; this
0x18006f0cf  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18006f0d4  test    eax, eax
0x18006f0d6  jz      short loc_18006F121
0x18006f0d8  mov     r8d, dword ptr [rbp+arg_18]
0x18006f0dc  mov     rax, [rsi+10h]
0x18006f0e0  mov     edx, r13d
0x18006f0e3  imul    edx, r8d
0x18006f0e7  movsxd  rcx, edx
0x18006f0ea  add     rax, rcx
0x18006f0ed  mov     [rbp+arg_18], rax
0x18006f0f1  cmp     r8d, [r14]
0x18006f0f4  jge     short loc_18006F10F
0x18006f0f6  sub     r15d, edx
0x18006f0f9  lea     rcx, [rax+r13]; void *
0x18006f0fd  sub     r15d, r13d
0x18006f100  mov     rdx, rax; Src
0x18006f103  movsxd  r8, r15d; Size
0x18006f106  call    memmove_0
0x18006f10b  mov     rax, [rbp+arg_18]
0x18006f10f  mov     r8, r13; Size
0x18006f112  lea     rdx, [rbp+Src]; Src
0x18006f116  mov     rcx, rax; void *
0x18006f119  call    memcpy_0
0x18006f11e  add     [r14], r12d
0x18006f121  cmp     dword ptr [rdi+120h], 51h ; 'Q'
0x18006f128  jnz     short loc_18006F150
0x18006f12a  mov     rcx, [rdi+130h]
0x18006f131  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006f136  cmp     dword ptr [rdi+120h], 4Eh ; 'N'
0x18006f13d  jz      loc_18006F2FF
0x18006f143  mov     rax, [rbp+var_38]
0x18006f147  mov     r13, [rbp+arg_8]
0x18006f14b  jmp     loc_18006F085
0x18006f150  mov     edx, 4Eh ; 'N'; int
0x18006f155  mov     r8d, 3EFh; int
0x18006f15b  mov     rcx, rdi; this
0x18006f15e  call    ?ChkCurTok@JSONParser@@AEAAXHH@Z; JSONParser::ChkCurTok(int,int)
0x18006f163  movsxd  r15, dword ptr [r14]
0x18006f166  lea     rcx, [r15+r15*2]
0x18006f16a  shl     rcx, 3; Size
0x18006f16e  call    cs:__imp_malloc
0x18006f175  nop     dword ptr [rax+rax+00h]
0x18006f17a  mov     r14, rax
0x18006f17d  xor     eax, eax
0x18006f17f  test    r14, r14
0x18006f182  jz      loc_18006F519
0x18006f188  mov     r13d, eax
0x18006f18b  test    r15d, r15d
0x18006f18e  jle     short loc_18006F1DC
0x18006f190  mov     rbx, [rbp+var_38]
0x18006f194  movsxd  rcx, dword ptr [rbx]
0x18006f197  mov     r8, rcx; Size
0x18006f19a  imul    ecx, r13d
0x18006f19e  movsxd  rdx, ecx
0x18006f1a1  lea     rcx, [rbp+Src]; void *
0x18006f1a5  add     rdx, [rsi+10h]; Src
0x18006f1a9  call    memcpy_0
0x18006f1ae  movups  xmm0, [rbp+Src]
0x18006f1b2  mov     eax, r15d
0x18006f1b5  movsd   xmm1, [rbp+var_20]
0x18006f1ba  sub     eax, r13d
0x18006f1bd  cdqe
0x18006f1bf  add     r13d, r12d
0x18006f1c2  lea     rdx, [rax+rax*2]
0x18006f1c6  movups  xmmword ptr [r14+rdx*8-18h], xmm0
0x18006f1cc  movsd   qword ptr [r14+rdx*8-8], xmm1
0x18006f1d3  cmp     r13d, r15d
0x18006f1d6  jl      short loc_18006F194
0x18006f1d8  mov     rbx, [rbp+arg_10]
0x18006f1dc  mov     rcx, rsi; this
0x18006f1df  call    ?Release@GL@@QEAAXXZ; GL::Release(void)
0x18006f1e4  mov     rcx, [rdi+138h]; this
0x18006f1eb  lea     r8, [rbp+Src]; struct VAR *
0x18006f1ef  xor     edx, edx; int
0x18006f1f1  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x18006f1f6  xor     r12d, r12d
0x18006f1f9  mov     esi, eax
0x18006f1fb  test    eax, eax
0x18006f1fd  jns     short loc_18006F219
0x18006f1ff  mov     rcx, r14; Block
0x18006f202  call    cs:__imp_free
0x18006f209  nop     dword ptr [rax+rax+00h]
0x18006f20e  mov     edx, esi; int
0x18006f210  mov     rcx, rdi; this
0x18006f213  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f219  mov     rdx, [rdi+138h]; struct CSession *
0x18006f220  lea     rax, [rbp+Src]
0x18006f224  mov     [rsp+80h+var_50], r12d; int
0x18006f229  lea     rcx, [rbp+var_40]; struct ArrayObj **
0x18006f22d  mov     [rsp+80h+var_58], r12d; int
0x18006f232  mov     r9, r14; struct VAR *
0x18006f235  mov     r8d, r15d; int
0x18006f238  mov     [rsp+80h+var_60], rax; struct VAR *
0x18006f23d  call    ?Create@ArrayObj@@SAJPEAPEAV1@PEAVCSession@@HPEAVVAR@@2HH@Z; ArrayObj::Create(ArrayObj * *,CSession *,int,VAR *,VAR *,int,int)
0x18006f242  mov     esi, eax
0x18006f244  mov     rcx, r14; Block
0x18006f247  test    eax, eax
0x18006f249  jns     short loc_18006F262
0x18006f24b  call    cs:__imp_free
0x18006f252  nop     dword ptr [rax+rax+00h]
0x18006f257  mov     edx, esi; int
0x18006f259  mov     rcx, rdi; this
0x18006f25c  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f262  call    cs:__imp_free
0x18006f269  nop     dword ptr [rax+rax+00h]
0x18006f26e  mov     rsi, [rbp+var_40]
0x18006f272  mov     rcx, rbx; this
0x18006f275  mov     rdx, [rdi+138h]; struct CSession *
0x18006f27c  mov     r8, rsi; struct NameTbl *
0x18006f27f  call    ?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z; VAR::SetHeapJsObj(CSession *,NameTbl *)
0x18006f284  mov     ebx, eax
0x18006f286  test    eax, eax
0x18006f288  jns     loc_18006F01C
0x18006f28e  mov     rdx, [rsi]
0x18006f291  mov     rcx, rsi
0x18006f294  mov     rax, [rdx+10h]
0x18006f298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f29d  mov     edx, ebx; int
0x18006f29f  mov     rcx, rdi; this
0x18006f2a2  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f2a8  mov     rcx, [rdi+130h]
0x18006f2af  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006f2b4  mov     ecx, [rdi+120h]
0x18006f2ba  sub     ecx, 80h
0x18006f2c0  jz      short loc_18006F2F2
0x18006f2c2  cmp     ecx, 1
0x18006f2c5  jnz     short loc_18006F2FF
0x18006f2c7  mov     rax, [rdi+130h]
0x18006f2ce  test    byte ptr [rax+60h], 4
0x18006f2d2  jnz     short loc_18006F2FF
0x18006f2d4  mov     word ptr [rbx], 5
0x18006f2d9  movsd   xmm0, qword ptr [rdi+128h]
0x18006f2e1  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18006f2e8  movsd   qword ptr [rbx+8], xmm0
0x18006f2ed  jmp     loc_18006F010
0x18006f2f2  mov     rax, [rdi+130h]
0x18006f2f9  test    byte ptr [rax+60h], 4
0x18006f2fd  jz      short loc_18006F30D
0x18006f2ff  mov     edx, 3EAh; int
0x18006f304  mov     rcx, rdi; this
0x18006f307  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f30d  mov     word ptr [rbx], 3
0x18006f312  mov     eax, [rdi+128h]
0x18006f318  neg     eax
0x18006f31a  jmp     loc_18006F00D
0x18006f31f  mov     rcx, [rdi+138h]; this
0x18006f326  mov     r8, rbx; struct VAR *
0x18006f329  mov     edx, 5; int
0x18006f32e  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x18006f333  test    eax, eax
0x18006f335  jns     short loc_18006F342
0x18006f337  mov     edx, eax; int
0x18006f339  mov     rcx, rdi; this
0x18006f33c  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f342  mov     rdx, [rdi+138h]; struct CSession *
0x18006f349  lea     rcx, [rbp+var_40]; struct NameTbl **
0x18006f34d  mov     r8, rbx; struct VAR *
0x18006f350  call    ?Create@NameTbl@@SAJPEAPEAV1@PEAVCSession@@PEAVVAR@@2H@Z; NameTbl::Create(NameTbl * *,CSession *,VAR *,VAR *,int)
0x18006f355  test    eax, eax
0x18006f357  jns     short loc_18006F364
0x18006f359  mov     edx, eax; int
0x18006f35b  mov     rcx, rdi; this
0x18006f35e  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f364  mov     rsi, [rbp+var_40]
0x18006f368  mov     rcx, rbx; this
0x18006f36b  mov     rdx, [rdi+138h]; struct CSession *
0x18006f372  mov     r8, rsi; struct NameTbl *
0x18006f375  call    ?SetHeapJsObj@VAR@@QEAAJPEAVCSession@@PEAVNameTbl@@@Z; VAR::SetHeapJsObj(CSession *,NameTbl *)
0x18006f37a  mov     ebx, eax
0x18006f37c  test    eax, eax
0x18006f37e  jns     short loc_18006F39A
0x18006f380  mov     rdx, [rsi]
0x18006f383  mov     rcx, rsi
0x18006f386  mov     rax, [rdx+10h]
0x18006f38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f38f  mov     edx, ebx; int
0x18006f391  mov     rcx, rdi; this
0x18006f394  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f39a  mov     rcx, [rdi+130h]
0x18006f3a1  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
  ... truncated ...
```
