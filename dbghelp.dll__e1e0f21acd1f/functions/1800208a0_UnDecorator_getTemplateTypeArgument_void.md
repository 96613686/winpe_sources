# UnDecorator::getTemplateTypeArgument(void)

- ea: `0x1800208a0`
- end: `0x180020a24`
- name: `?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `388`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c204`
- `0x180020688`
- `0x1801d4b4c`
- `0x1801d4d44`
- `0x1801d572c`
- `0x1801d5be4`

## callees

- `0x1800106ac`
- `0x180010860`
- `0x18001aa78`
- `0x18001bea8`
- `0x1800208a0`
- `0x180020b5c`
- `0x1801d46c0`
- `0x1801d54c0`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180020962`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180020962`

## string_xrefs

- `0x18002098f`: ``template-parameter`
- `0x1800209c4`: ``template-parameter`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateTypeArgument(__int64 a1, DName *a2)
{
  _BYTE *v2; // rax
  __int64 (__fastcall *v5)(_QWORD); // rbx
  unsigned int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  __int128 v11; // [rsp+20h] [rbp-60h]
  __int128 v12; // [rsp+20h] [rbp-60h]
  _QWORD v13[2]; // [rsp+30h] [rbp-50h] BYREF
  int v14; // [rsp+40h] [rbp-40h]
  _BYTE v15[24]; // [rsp+48h] [rbp-38h] BYREF
  char String[16]; // [rsp+60h] [rbp-20h] BYREF

  v2 = *(_BYTE **)(a1 + 256);
  if ( *v2 != 88 )
  {
    if ( *v2 != 63 )
    {
      v13[1] = a1;
      v13[0] = 0;
      v14 = 0;
      UnDecorator::getPrimaryDataType(a1, a2, v13);
      return a2;
    }
    UnDecorator::getSignedDimension(a1, v13);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) != 0 && *(_QWORD *)(a1 + 280) )
    {
      *(_OWORD *)String = 0;
      DName::getString((DName *)v13, String, 16);
      v5 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
      v6 = atol(String);
      v7 = v5(v6);
      if ( v7 )
      {
        DName::DName(a2, a1, v7);
        return a2;
      }
    }
    else
    {
      *((_QWORD *)&v12 + 1) = 19;
      *(_QWORD *)&v12 = "`template-parameter";
      *(_OWORD *)String = v12;
    }
    v8 = operator+((DName *)v15);
    LOBYTE(v9) = 39;
    DName::operator+(v8, a2, v9);
    return a2;
  }
  *((_QWORD *)&v11 + 1) = 4;
  *(_QWORD *)(a1 + 256) = v2 + 1;
  *(_QWORD *)&v11 = "void";
  *(_OWORD *)String = v11;
  DName::DName(a2, (struct UnDecorator *)a1, (const struct StringLiteral *)String);
  return a2;
}

```

## disassembly

```asm
0x1800208a0  mov     [rsp-18h+arg_10], rbx
0x1800208a5  push    rbp
0x1800208a6  push    rsi
0x1800208a7  push    rdi
0x1800208a8  mov     rbp, rsp
0x1800208ab  sub     rsp, 80h
0x1800208b2  mov     rax, cs:__security_cookie
0x1800208b9  xor     rax, rsp
0x1800208bc  mov     [rbp+var_10], rax
0x1800208c0  mov     rax, [rcx+100h]
0x1800208c7  mov     rsi, rdx
0x1800208ca  mov     rdi, rcx
0x1800208cd  cmp     byte ptr [rax], 58h ; 'X'
0x1800208d0  jnz     short loc_18002090D
0x1800208d2  lea     rcx, [rax+1]
0x1800208d6  mov     qword ptr [rbp+var_60+8], 4
0x1800208de  lea     rax, aVoid_1; "void"
0x1800208e5  mov     [rdi+100h], rcx
0x1800208ec  mov     qword ptr [rbp+var_60], rax
0x1800208f0  lea     r8, [rbp+String]; struct StringLiteral *
0x1800208f4  movaps  xmm0, [rbp+var_60]
0x1800208f8  mov     rdx, rdi; struct UnDecorator *
0x1800208fb  mov     rcx, rsi; this
0x1800208fe  movdqa  xmmword ptr [rbp+String], xmm0
0x180020903  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x180020908  jmp     loc_180020A02
0x18002090d  cmp     byte ptr [rax], 3Fh ; '?'
0x180020910  jnz     loc_1800209E6
0x180020916  lea     rdx, [rbp+var_50]
0x18002091a  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002091f  test    dword ptr [rdi+110h], 4000h
0x180020929  jz      loc_1800209C4
0x18002092f  cmp     qword ptr [rdi+118h], 0
0x180020937  jz      loc_1800209C4
0x18002093d  xorps   xmm0, xmm0
0x180020940  lea     rdx, [rbp+String]; char *
0x180020944  mov     r8d, 10h; int
0x18002094a  lea     rcx, [rbp+var_50]; this
0x18002094e  movups  xmmword ptr [rbp+String], xmm0
0x180020952  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x180020957  mov     rbx, [rdi+118h]
0x18002095e  lea     rcx, [rbp+String]; String
0x180020962  call    cs:__imp_atol
0x180020968  mov     ecx, eax
0x18002096a  mov     rax, rbx
0x18002096d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020972  test    rax, rax
0x180020975  jz      short loc_180020987
0x180020977  mov     r8, rax
0x18002097a  mov     rdx, rdi
0x18002097d  mov     rcx, rsi
0x180020980  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x180020985  jmp     short loc_180020A02
0x180020987  mov     qword ptr [rbp+var_60+8], 13h
0x18002098f  lea     rax, aTemplateParame; "`template-parameter"
0x180020996  mov     qword ptr [rbp+var_60], rax
0x18002099a  lea     rdx, [rbp+var_60]
0x18002099e  movaps  xmm0, [rbp+var_60]
0x1800209a2  movdqa  [rbp+var_60], xmm0
0x1800209a7  lea     r8, [rbp+var_50]
0x1800209ab  lea     rcx, [rbp+var_38]; this
0x1800209af  call    ??H@YA?AVDName@@AEBUStringLiteral@@AEBV0@@Z; operator+(StringLiteral const &,DName const &)
0x1800209b4  mov     r8b, 27h ; '''
0x1800209b7  mov     rdx, rsi
0x1800209ba  mov     rcx, rax
0x1800209bd  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x1800209c2  jmp     short loc_180020A02
0x1800209c4  lea     rax, aTemplateParame; "`template-parameter"
0x1800209cb  mov     qword ptr [rbp+var_60+8], 13h
0x1800209d3  mov     qword ptr [rbp+var_60], rax
0x1800209d7  lea     rdx, [rbp+String]
0x1800209db  movaps  xmm0, [rbp+var_60]
0x1800209df  movdqa  xmmword ptr [rbp+String], xmm0
0x1800209e4  jmp     short loc_1800209A7
0x1800209e6  lea     r8, [rbp+var_50]
0x1800209ea  mov     [rbp+var_48], rdi
0x1800209ee  mov     [rbp+var_50], 0
0x1800209f6  mov     [rbp+var_40], 0
0x1800209fd  call    ?getPrimaryDataType@UnDecorator@@AEAA?AVDName@@AEBV2@@Z; UnDecorator::getPrimaryDataType(DName const &)
0x180020a02  mov     rax, rsi
0x180020a05  mov     rcx, [rbp+var_10]
0x180020a09  xor     rcx, rsp; StackCookie
0x180020a0c  call    __security_check_cookie
0x180020a11  mov     rbx, [rsp+80h+arg_10]
0x180020a19  add     rsp, 80h
0x180020a20  pop     rdi
0x180020a21  pop     rsi
0x180020a22  pop     rbp
0x180020a23  retn
```
