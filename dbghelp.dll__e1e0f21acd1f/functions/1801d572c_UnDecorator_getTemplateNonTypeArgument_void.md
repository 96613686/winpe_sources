# UnDecorator::getTemplateNonTypeArgument(void)

- ea: `0x1801d572c`
- end: `0x1801d5bdd`
- name: `?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `1201`
- prototype: ``
- caller_count: `8`
- callee_count: `28`
- tags: ``

## callers

- `0x18001c204`
- `0x180020688`
- `0x1801d49e8`
- `0x1801d4a94`
- `0x1801d4b4c`
- `0x1801d5284`
- `0x1801d572c`
- `0x1801d5be4`

## callees

- `0x1800105c0`
- `0x1800106ac`
- `0x180010860`
- `0x180010bf0`
- `0x180010d00`
- `0x180010f98`
- `0x18001aa78`
- `0x18001bea8`
- `0x18001c0e8`
- `0x18001c204`
- `0x18001c884`
- `0x18001d2d0`
- `0x18001ed64`
- `0x1800208a0`
- `0x180022904`
- `0x18019b9f0`
- `0x1801d46c0`
- `0x1801d49e8`
- `0x1801d4a94`
- `0x1801d4d44`
- `0x1801d5190`
- `0x1801d5284`
- `0x1801d54c0`
- `0x1801d5674`
- `0x1801d572c`
- `0x1801d5be4`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x1801d5aff`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x1801d5aff`

## string_xrefs

- `0x1801d5bd4`: ``template-type-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateNonTypeArgument(__int64 a1, __int64 a2)
{
  char current_character_and_increment_buffer; // al
  __int64 v5; // rcx
  int v6; // edi
  _BYTE *v7; // rax
  const char *v8; // rax
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 DecoratedName; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 SignedDimension; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int128 *v31; // rcx
  __int16 v33; // bx
  __int64 (__fastcall *v34)(_QWORD); // rax
  __int64 v35; // rax
  int v36; // edi
  int v37; // edi
  int v38; // edi
  const char *v39; // rax
  __int64 v40; // rax
  __int128 v41; // [rsp+20h] [rbp-49h] BYREF
  int v42; // [rsp+30h] [rbp-39h]
  _BYTE v43[24]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v44[24]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v45[32]; // [rsp+70h] [rbp+7h] BYREF
  char String[16]; // [rsp+90h] [rbp+27h] BYREF

  current_character_and_increment_buffer = UnDecorator::get_current_character_and_increment_buffer((UnDecorator *)a1);
  v6 = current_character_and_increment_buffer;
  if ( current_character_and_increment_buffer > 70 )
  {
    if ( current_character_and_increment_buffer <= 80 )
    {
      switch ( current_character_and_increment_buffer )
      {
        case 'P':
          UnDecorator::getDimension(v5, v43, 0);
          v8 = "lambda";
          *(_QWORD *)&String[8] = 6;
          goto LABEL_18;
        case 'G':
        case 'H':
        case 'I':
        case 'J':
LABEL_45:
          *((_QWORD *)&v41 + 1) = a1;
          *(_QWORD *)&v41 = 0;
          v42 = 0;
          DName::doPchar((DName *)&v41, 123);
          if ( v6 == 72 || (unsigned int)(v6 - 73) <= 1 )
          {
            DecoratedName = UnDecorator::getDecoratedName(a1, v43);
            DName::operator+=(&v41, DecoratedName, v13, v14);
            LOBYTE(v15) = 44;
            DName::operator+=(&v41, v15);
          }
          v16 = v6 - 70;
          if ( !v16 )
            goto LABEL_54;
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( !v18 )
            {
LABEL_55:
              SignedDimension = UnDecorator::getSignedDimension(a1, v43);
              DName::operator+=(&v41, SignedDimension, v29, v30);
              goto LABEL_56;
            }
            v19 = v18 - 1;
            if ( !v19 )
            {
LABEL_54:
              v24 = UnDecorator::getSignedDimension(a1, v43);
              DName::operator+=(&v41, v24, v25, v26);
              LOBYTE(v27) = 44;
              DName::operator+=(&v41, v27);
              goto LABEL_55;
            }
            if ( v19 != 1 )
            {
LABEL_56:
              LOBYTE(v11) = 125;
              v31 = &v41;
LABEL_57:
              DName::operator+(v31, a2, v11);
              return a2;
            }
          }
          v20 = UnDecorator::getSignedDimension(a1, v43);
          DName::operator+=(&v41, v20, v21, v22);
          LOBYTE(v23) = 44;
          DName::operator+=(&v41, v23);
          goto LABEL_54;
        case 'M':
          UnDecorator::getTemplateTypeArgument(a1, (DName *)v44);
          if ( v44[16] <= 1 )
          {
            UnDecorator::getTemplateNonTypeArgument(a1, a2);
            return a2;
          }
          break;
        case 'N':
          v8 = "nullptr";
          *(_QWORD *)&String[8] = 7;
LABEL_18:
          *(_QWORD *)String = v8;
          v41 = *(_OWORD *)String;
          DName::DName((DName *)a2, (struct UnDecorator *)a1, (const struct StringLiteral *)&v41);
          return a2;
      }
LABEL_64:
      v10 = 2;
      goto LABEL_65;
    }
    if ( current_character_and_increment_buffer == 81 )
      goto LABEL_64;
    if ( current_character_and_increment_buffer != 82 )
    {
      if ( current_character_and_increment_buffer == 83 )
      {
        *(_QWORD *)(a2 + 8) = a1;
        *(_QWORD *)a2 = 0;
        *(_DWORD *)(a2 + 16) = 0;
        return a2;
      }
      if ( current_character_and_increment_buffer != 84
        && (unsigned int)(current_character_and_increment_buffer - 85) >= 2 )
      {
        goto LABEL_64;
      }
    }
    UnDecorator::getSignedDimension(a1, v43);
    *(_OWORD *)String = 0;
    DName::getString((DName *)v43, String, 16);
    v33 = atol(String);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) != 0 )
    {
      v34 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
      if ( v34 )
      {
        v35 = v34(v33 & 0xFFF);
        if ( v35 )
        {
          DName::DName(a2, a1, v35);
          return a2;
        }
      }
    }
    sprintf_s(String, 0x10u, "%d", v33 & 0xFFF);
    DName::DName(v44, a1, String);
    v36 = v6 - 82;
    if ( v36 && (v37 = v36 - 2) != 0 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        if ( v38 != 1 )
          goto LABEL_64;
        v39 = "`generic-method-parameter-";
        *((_QWORD *)&v41 + 1) = 26;
LABEL_77:
        *(_QWORD *)&v41 = v39;
        v40 = operator+((DName *)v45);
        LOBYTE(v11) = 39;
        v31 = (__int128 *)v40;
        goto LABEL_57;
      }
      v39 = "`generic-class-parameter-";
    }
    else
    {
      v39 = "`template-type-parameter-";
    }
    *((_QWORD *)&v41 + 1) = 25;
    goto LABEL_77;
  }
  if ( current_character_and_increment_buffer == 70 )
    goto LABEL_45;
  if ( current_character_and_increment_buffer > 55 )
  {
    switch ( current_character_and_increment_buffer )
    {
      case '8':
        UnDecorator::getPointerToMember(a1, a2);
        return a2;
      case 'A':
      case 'B':
        UnDecorator::getFloatingPoint(a1, a2, (unsigned int)current_character_and_increment_buffer);
        return a2;
      case 'C':
        UnDecorator::getArrayAccess(a1, a2);
        return a2;
      case 'D':
        UnDecorator::getEnumEncoding(a1, a2);
        return a2;
      case 'E':
        UnDecorator::getDecoratedName(a1, a2);
        return a2;
    }
    goto LABEL_64;
  }
  switch ( current_character_and_increment_buffer )
  {
    case 55:
      UnDecorator::getUnionObject(v5, a2);
      return a2;
    case 0:
      v10 = 1;
LABEL_65:
      DName::DName(a2, a1, v10);
      return a2;
    case 48:
      UnDecorator::getSignedDimension(v5, a2);
      return a2;
    case 49:
      v7 = *(_BYTE **)(v5 + 256);
      if ( *v7 != 64 )
      {
        *((_QWORD *)&v41 + 1) = a1;
        *(_QWORD *)&v41 = 0;
        v42 = 0;
        DName::doPchar((DName *)&v41, 38);
        v9 = UnDecorator::getDecoratedName(a1, v43);
        DName::operator+(&v41, a2, v9);
        return a2;
      }
      *(_QWORD *)&String[8] = 4;
      *(_QWORD *)(v5 + 256) = v7 + 1;
      v8 = "NULL";
      goto LABEL_18;
    case 50:
      UnDecorator::getValueObject(v5, a2);
      return a2;
    case 52:
      UnDecorator::getStringObject(v5, a2);
      return a2;
    case 53:
      UnDecorator::getAddressOf(v5, a2);
      return a2;
  }
  if ( current_character_and_increment_buffer != 54 )
    goto LABEL_64;
  UnDecorator::getMemberAccess(v5, a2);
  return a2;
}

```

## disassembly

```asm
0x1801d572c  mov     [rsp-8+arg_10], rbx
0x1801d5731  mov     [rsp-8+arg_18], rsi
0x1801d5736  push    rbp
0x1801d5737  push    rdi
0x1801d5738  push    r14
0x1801d573a  lea     rbp, [rsp-47h]
0x1801d573f  sub     rsp, 0B0h
0x1801d5746  mov     rax, cs:__security_cookie
0x1801d574d  xor     rax, rsp
0x1801d5750  mov     [rbp+57h+var_20], rax
0x1801d5754  mov     rsi, rdx
0x1801d5757  mov     r14, rcx
0x1801d575a  call    ?get_current_character_and_increment_buffer@UnDecorator@@AEAADXZ; UnDecorator::get_current_character_and_increment_buffer(void)
0x1801d575f  movsx   edi, al
0x1801d5762  cmp     edi, 46h ; 'F'
0x1801d5765  jg      loc_1801D5902
0x1801d576b  jz      loc_1801D596F
0x1801d5771  cmp     edi, 37h ; '7'
0x1801d5774  jg      loc_1801D588B
0x1801d577a  jz      loc_1801D587E
0x1801d5780  test    al, al
0x1801d5782  jz      loc_1801D5873
0x1801d5788  sub     edi, 30h ; '0'
0x1801d578b  jz      loc_1801D5866
0x1801d5791  sub     edi, 1
0x1801d5794  jz      short loc_1801D57E2
0x1801d5796  sub     edi, 1
0x1801d5799  jz      short loc_1801D57D5
0x1801d579b  sub     edi, 2
0x1801d579e  jz      short loc_1801D57C8
0x1801d57a0  sub     edi, 1
0x1801d57a3  jz      short loc_1801D57BB
0x1801d57a5  cmp     edi, 1
0x1801d57a8  jnz     loc_1801D5A89
0x1801d57ae  mov     rdx, rsi
0x1801d57b1  call    ?getMemberAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getMemberAccess(void)
0x1801d57b6  jmp     loc_1801D5A9A
0x1801d57bb  mov     rdx, rsi
0x1801d57be  call    ?getAddressOf@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getAddressOf(void)
0x1801d57c3  jmp     loc_1801D5A9A
0x1801d57c8  mov     rdx, rsi
0x1801d57cb  call    ?getStringObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getStringObject(void)
0x1801d57d0  jmp     loc_1801D5A9A
0x1801d57d5  mov     rdx, rsi
0x1801d57d8  call    ?getValueObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getValueObject(void)
0x1801d57dd  jmp     loc_1801D5A9A
0x1801d57e2  mov     rax, [rcx+100h]
0x1801d57e9  cmp     byte ptr [rax], 40h ; '@'
0x1801d57ec  jnz     short loc_1801D5828
0x1801d57ee  inc     rax
0x1801d57f1  mov     qword ptr [rbp+57h+String+8], 4
0x1801d57f9  mov     [rcx+100h], rax
0x1801d5800  lea     rax, aNull; "NULL"
0x1801d5807  mov     qword ptr [rbp+57h+String], rax
0x1801d580b  lea     r8, [rbp+57h+var_A0]; struct StringLiteral *
0x1801d580f  movaps  xmm0, xmmword ptr [rbp+57h+String]
0x1801d5813  mov     rdx, r14; struct UnDecorator *
0x1801d5816  mov     rcx, rsi; this
0x1801d5819  movdqa  [rbp+57h+var_A0], xmm0
0x1801d581e  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x1801d5823  jmp     loc_1801D5A9A
0x1801d5828  mov     dl, 26h ; '&'; char
0x1801d582a  mov     qword ptr [rbp+57h+var_A0+8], r14
0x1801d582e  lea     rcx, [rbp+57h+var_A0]; this
0x1801d5832  mov     qword ptr [rbp+57h+var_A0], 0
0x1801d583a  mov     [rbp+57h+var_90], 0
0x1801d5841  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x1801d5846  lea     rdx, [rbp+57h+var_80]
0x1801d584a  mov     rcx, r14
0x1801d584d  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x1801d5852  mov     r8, rax
0x1801d5855  lea     rcx, [rbp+57h+var_A0]
0x1801d5859  mov     rdx, rsi
0x1801d585c  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x1801d5861  jmp     loc_1801D5A9A
0x1801d5866  mov     rdx, rsi
0x1801d5869  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1801d586e  jmp     loc_1801D5A9A
0x1801d5873  mov     r8d, 1
0x1801d5879  jmp     loc_1801D5A8F
0x1801d587e  mov     rdx, rsi
0x1801d5881  call    ?getUnionObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getUnionObject(void)
0x1801d5886  jmp     loc_1801D5A9A
0x1801d588b  mov     ecx, edi
0x1801d588d  sub     ecx, 38h ; '8'
0x1801d5890  jz      short loc_1801D58F2
0x1801d5892  sub     ecx, 9
0x1801d5895  jz      short loc_1801D58DF
0x1801d5897  sub     ecx, 1
0x1801d589a  jz      short loc_1801D58DF
0x1801d589c  sub     ecx, 1
0x1801d589f  jz      short loc_1801D58CF
0x1801d58a1  sub     ecx, 1
0x1801d58a4  jz      short loc_1801D58BF
0x1801d58a6  cmp     ecx, 1
0x1801d58a9  jnz     loc_1801D5A89
0x1801d58af  mov     rdx, rsi
0x1801d58b2  mov     rcx, r14
0x1801d58b5  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x1801d58ba  jmp     loc_1801D5A9A
0x1801d58bf  mov     rdx, rsi
0x1801d58c2  mov     rcx, r14
0x1801d58c5  call    ?getEnumEncoding@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getEnumEncoding(void)
0x1801d58ca  jmp     loc_1801D5A9A
0x1801d58cf  mov     rdx, rsi
0x1801d58d2  mov     rcx, r14
0x1801d58d5  call    ?getArrayAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getArrayAccess(void)
0x1801d58da  jmp     loc_1801D5A9A
0x1801d58df  mov     r8d, edi
0x1801d58e2  mov     rdx, rsi
0x1801d58e5  mov     rcx, r14
0x1801d58e8  call    ?getFloatingPoint@UnDecorator@@AEAA?AVDName@@H@Z; UnDecorator::getFloatingPoint(int)
0x1801d58ed  jmp     loc_1801D5A9A
0x1801d58f2  mov     rdx, rsi
0x1801d58f5  mov     rcx, r14
0x1801d58f8  call    ?getPointerToMember@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getPointerToMember(void)
0x1801d58fd  jmp     loc_1801D5A9A
0x1801d5902  cmp     edi, 50h ; 'P'
0x1801d5905  jg      loc_1801D5A69
0x1801d590b  jz      loc_1801D5A49
0x1801d5911  mov     ecx, edi
0x1801d5913  sub     ecx, 47h ; 'G'
0x1801d5916  jz      short loc_1801D596F
0x1801d5918  sub     ecx, 1
0x1801d591b  jz      short loc_1801D596F
0x1801d591d  sub     ecx, 1
0x1801d5920  jz      short loc_1801D596F
0x1801d5922  sub     ecx, 1
0x1801d5925  jz      short loc_1801D596F
0x1801d5927  sub     ecx, 3
0x1801d592a  jz      short loc_1801D5949
0x1801d592c  cmp     ecx, 1
0x1801d592f  jnz     loc_1801D5A89
0x1801d5935  lea     rax, aNullptr; "nullptr"
0x1801d593c  mov     qword ptr [rbp+57h+String+8], 7
0x1801d5944  jmp     loc_1801D5807
0x1801d5949  lea     rdx, [rbp+57h+var_68]
0x1801d594d  mov     rcx, r14
0x1801d5950  call    ?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateTypeArgument(void)
0x1801d5955  cmp     [rbp+57h+var_58], 1
0x1801d5959  jg      loc_1801D5A89
0x1801d595f  mov     rdx, rsi
0x1801d5962  mov     rcx, r14
0x1801d5965  call    ?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateNonTypeArgument(void)
0x1801d596a  jmp     loc_1801D5A9A
0x1801d596f  mov     dl, 7Bh ; '{'; char
0x1801d5971  mov     qword ptr [rbp+57h+var_A0+8], r14
0x1801d5975  lea     rcx, [rbp+57h+var_A0]; this
0x1801d5979  mov     qword ptr [rbp+57h+var_A0], 0
0x1801d5981  mov     [rbp+57h+var_90], 0
0x1801d5988  call    ?doPchar@DName@@AEAAXD@Z; DName::doPchar(char)
0x1801d598d  mov     ecx, edi
0x1801d598f  sub     ecx, 48h ; 'H'
0x1801d5992  jz      short loc_1801D599E
0x1801d5994  sub     ecx, 1
0x1801d5997  jz      short loc_1801D599E
0x1801d5999  cmp     ecx, 1
0x1801d599c  jnz     short loc_1801D59C1
0x1801d599e  lea     rdx, [rbp+57h+var_80]
0x1801d59a2  mov     rcx, r14
0x1801d59a5  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x1801d59aa  mov     rdx, rax
0x1801d59ad  lea     rcx, [rbp+57h+var_A0]
0x1801d59b1  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801d59b6  mov     dl, 2Ch ; ','
0x1801d59b8  lea     rcx, [rbp+57h+var_A0]
0x1801d59bc  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1801d59c1  sub     edi, 46h ; 'F'
0x1801d59c4  jz      short loc_1801D59FD
0x1801d59c6  sub     edi, 1
0x1801d59c9  jz      short loc_1801D59DA
0x1801d59cb  sub     edi, 1
0x1801d59ce  jz      short loc_1801D5A20
0x1801d59d0  sub     edi, 1
0x1801d59d3  jz      short loc_1801D59FD
0x1801d59d5  cmp     edi, 1
0x1801d59d8  jnz     short loc_1801D5A38
0x1801d59da  lea     rdx, [rbp+57h+var_80]
0x1801d59de  mov     rcx, r14
0x1801d59e1  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1801d59e6  mov     rdx, rax
0x1801d59e9  lea     rcx, [rbp+57h+var_A0]
0x1801d59ed  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801d59f2  mov     dl, 2Ch ; ','
0x1801d59f4  lea     rcx, [rbp+57h+var_A0]
0x1801d59f8  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1801d59fd  lea     rdx, [rbp+57h+var_80]
0x1801d5a01  mov     rcx, r14
0x1801d5a04  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1801d5a09  mov     rdx, rax
0x1801d5a0c  lea     rcx, [rbp+57h+var_A0]
0x1801d5a10  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801d5a15  mov     dl, 2Ch ; ','
0x1801d5a17  lea     rcx, [rbp+57h+var_A0]
0x1801d5a1b  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x1801d5a20  lea     rdx, [rbp+57h+var_80]
0x1801d5a24  mov     rcx, r14
0x1801d5a27  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1801d5a2c  mov     rdx, rax
0x1801d5a2f  lea     rcx, [rbp+57h+var_A0]
0x1801d5a33  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x1801d5a38  mov     r8b, 7Dh ; '}'
0x1801d5a3b  lea     rcx, [rbp+57h+var_A0]
0x1801d5a3f  mov     rdx, rsi
0x1801d5a42  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x1801d5a47  jmp     short loc_1801D5A9A
0x1801d5a49  xor     r8d, r8d
0x1801d5a4c  lea     rdx, [rbp+57h+var_80]
0x1801d5a50  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x1801d5a55  lea     rax, aLambda; "lambda"
0x1801d5a5c  mov     qword ptr [rbp+57h+String+8], 6
0x1801d5a64  jmp     loc_1801D5807
0x1801d5a69  mov     ecx, edi
0x1801d5a6b  sub     ecx, 51h ; 'Q'
0x1801d5a6e  jz      short loc_1801D5A89
0x1801d5a70  sub     ecx, 1
0x1801d5a73  jz      short loc_1801D5AD5
0x1801d5a75  sub     ecx, 1
0x1801d5a78  jz      short loc_1801D5AC1
0x1801d5a7a  sub     ecx, 1
0x1801d5a7d  jz      short loc_1801D5AD5
0x1801d5a7f  sub     ecx, 1
0x1801d5a82  jz      short loc_1801D5AD5
0x1801d5a84  cmp     ecx, 1
0x1801d5a87  jz      short loc_1801D5AD5
0x1801d5a89  mov     r8d, 2
0x1801d5a8f  mov     rdx, r14
0x1801d5a92  mov     rcx, rsi
0x1801d5a95  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x1801d5a9a  mov     rax, rsi
0x1801d5a9d  mov     rcx, [rbp+57h+var_20]
0x1801d5aa1  xor     rcx, rsp; StackCookie
0x1801d5aa4  call    __security_check_cookie
0x1801d5aa9  lea     r11, [rsp+0C0h+var_10]
0x1801d5ab1  mov     rbx, [r11+30h]
0x1801d5ab5  mov     rsi, [r11+38h]
0x1801d5ab9  mov     rsp, r11
0x1801d5abc  pop     r14
0x1801d5abe  pop     rdi
0x1801d5abf  pop     rbp
0x1801d5ac0  retn
0x1801d5ac1  mov     [rsi+8], r14
0x1801d5ac5  mov     qword ptr [rsi], 0
0x1801d5acc  mov     dword ptr [rsi+10h], 0
0x1801d5ad3  jmp     short loc_1801D5A9A
0x1801d5ad5  lea     rdx, [rbp+57h+var_80]
0x1801d5ad9  mov     rcx, r14
0x1801d5adc  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x1801d5ae1  xorps   xmm0, xmm0
0x1801d5ae4  lea     rdx, [rbp+57h+String]; char *
0x1801d5ae8  mov     r8d, 10h; int
0x1801d5aee  lea     rcx, [rbp+57h+var_80]; this
0x1801d5af2  movups  xmmword ptr [rbp+57h+String], xmm0
0x1801d5af6  call    ?getString@DName@@QEBAPEADPEADH@Z; DName::getString(char *,int)
0x1801d5afb  lea     rcx, [rbp+57h+String]; String
0x1801d5aff  call    cs:__imp_atol
0x1801d5b05  test    dword ptr [r14+110h], 4000h
0x1801d5b10  mov     ebx, eax
0x1801d5b12  jz      short loc_1801D5B45
0x1801d5b14  mov     rax, [r14+118h]
0x1801d5b1b  test    rax, rax
0x1801d5b1e  jz      short loc_1801D5B45
0x1801d5b20  mov     ecx, ebx
0x1801d5b22  and     ecx, 0FFFh
0x1801d5b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5b2d  test    rax, rax
0x1801d5b30  jz      short loc_1801D5B45
0x1801d5b32  mov     r8, rax
0x1801d5b35  mov     rdx, r14
0x1801d5b38  mov     rcx, rsi
0x1801d5b3b  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x1801d5b40  jmp     loc_1801D5A9A
0x1801d5b45  and     ebx, 0FFFh
0x1801d5b4b  lea     r8, aD; "%d"
0x1801d5b52  mov     r9d, ebx
0x1801d5b55  lea     rcx, [rbp+57h+String]; Buffer
0x1801d5b59  mov     edx, 10h; BufferCount
0x1801d5b5e  call    sprintf_s
0x1801d5b63  lea     r8, [rbp+57h+String]
0x1801d5b67  mov     rdx, r14
0x1801d5b6a  lea     rcx, [rbp+57h+var_68]
0x1801d5b6e  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x1801d5b73  sub     edi, 52h ; 'R'
0x1801d5b76  jz      short loc_1801D5BD4
0x1801d5b78  sub     edi, 2
0x1801d5b7b  jz      short loc_1801D5BD4
0x1801d5b7d  sub     edi, 1
0x1801d5b80  jz      short loc_1801D5BC3
0x1801d5b82  cmp     edi, 1
0x1801d5b85  jnz     loc_1801D5A89
0x1801d5b8b  lea     rax, aGenericMethodP; "`generic-method-parameter-"
0x1801d5b92  mov     qword ptr [rbp+57h+var_A0+8], 1Ah
0x1801d5b9a  mov     qword ptr [rbp+57h+var_A0], rax
0x1801d5b9e  lea     r8, [rbp+57h+var_68]
0x1801d5ba2  movaps  xmm0, [rbp+57h+var_A0]
0x1801d5ba6  lea     rdx, [rbp+57h+var_A0]
0x1801d5baa  lea     rcx, [rbp+57h+var_50]; this
0x1801d5bae  movdqa  [rbp+57h+var_A0], xmm0
0x1801d5bb3  call    ??H@YA?AVDName@@AEBUStringLiteral@@AEBV0@@Z; operator+(StringLiteral const &,DName const &)
0x1801d5bb8  mov     r8b, 27h ; '''
  ... truncated ...
```
