# Marshal::JsonParser::SkipValue(void)

- ea: `0x14001e274`
- end: `0x14001e796`
- name: `?SkipValue@JsonParser@Marshal@@QEAA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@XZ`
- size: `1314`
- prototype: `__int64 __fastcall(Marshal::JsonParser *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14001a3c4`

## callees

- `0x140002d4e`
- `0x1400129e8`
- `0x1400158ec`
- `0x140018068`
- `0x14001a31c`
- `0x14001aebc`
- `0x14001af8c`
- `0x14001b384`
- `0x14001b484`
- `0x14001b8a8`
- `0x14001e274`
- `0x1400201e4`
- `0x14002036c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Marshal::JsonParser::SkipValue(Marshal::JsonParser *this, _QWORD *a2)
{
  __int64 v4; // rsi
  int v5; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r9
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r10
  unsigned __int64 v16; // rax
  bool v17; // cf
  __int64 v18; // rax
  __int64 v19; // r10
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int64 v26; // rax
  int *v27; // rdx
  int v28; // eax
  char Element; // al
  __int64 v30; // r8
  unsigned __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // r8
  unsigned __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  _QWORD v39[2]; // [rsp+20h] [rbp-29h] BYREF
  _QWORD v40[2]; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v41[2]; // [rsp+40h] [rbp-9h] BYREF
  char v42[16]; // [rsp+50h] [rbp+7h] BYREF
  char v43[16]; // [rsp+60h] [rbp+17h] BYREF
  __int128 v44; // [rsp+70h] [rbp+27h] BYREF
  __int64 v45; // [rsp+80h] [rbp+37h]
  __int64 v46; // [rsp+88h] [rbp+3Fh]
  int pExceptionObject; // [rsp+B0h] [rbp+67h] BYREF

  v4 = *((_QWORD *)this + 2);
  v44 = 0;
  v45 = 0;
  v46 = 0;
  while ( 1 )
  {
    v5 = Marshal::JsonParser::PeekValueType(this);
    if ( !v5 )
    {
      Marshal::JsonParser::ParseNumber(this, v42);
      goto LABEL_57;
    }
    v9 = v5 - 1;
    if ( !v9 )
    {
      Marshal::JsonParser::ParseString(this);
      goto LABEL_57;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      LOBYTE(v7) = 93;
      LOBYTE(v6) = 91;
      if ( !(unsigned __int8)Marshal::JsonParser::BeginAggregate(this, v6, v7, 7) )
        goto LABEL_57;
      LOBYTE(pExceptionObject) = 0;
      goto LABEL_50;
    }
    v11 = v10 - 1;
    if ( v11 )
      break;
    LOBYTE(v7) = 125;
    LOBYTE(v6) = 123;
    if ( !(unsigned __int8)Marshal::JsonParser::BeginAggregate(this, v6, v7, 9) )
      goto LABEL_57;
    Marshal::JsonParser::ParseObjectKey(this);
    LOBYTE(pExceptionObject) = 1;
LABEL_50:
    std::vector<bool>::push_back(&v44, &pExceptionObject);
LABEL_51:
    if ( !v46 )
      goto LABEL_52;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 1 )
      Marshal::JsonParser::ParseNull(this);
    goto LABEL_57;
  }
  v13 = *((_QWORD *)this + 1);
  v7 = *((_QWORD *)this + 2);
  if ( v7 >= v13 )
    goto LABEL_94;
  if ( *(_WORD *)(*(_QWORD *)this + 2 * v7) != 116 )
  {
    if ( *(_WORD *)(*(_QWORD *)this + 2 * v7) == 102 && v7 + 1 < v13 )
    {
      v18 = *(_QWORD *)this;
      if ( *(_WORD *)(*(_QWORD *)this + 2 * v7 + 2) == 97
        && v7 + 2 < v13
        && *(_WORD *)(v18 + 2 * (v7 + 2)) == 108
        && v7 + 3 < v13
        && *(_WORD *)(v18 + 2 * (v7 + 3)) == 115
        && v7 + 4 < v13
        && *(_WORD *)(v18 + 2 * (v7 + 4)) == 101 )
      {
        v19 = 5;
        v20 = *((_QWORD *)this + 1);
        if ( v13 >= v7 + 5 )
          v20 = v7 + 5;
        *((_QWORD *)this + 3) = v20;
        while ( 1 )
        {
          v8 = v7 + v19;
          v17 = v13 < v7 + v19;
          if ( v13 <= v7 + v19 )
            goto LABEL_45;
          if ( *(_WORD *)(*(_QWORD *)this + 2 * v8) != 9
            && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 10
            && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 13
            && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 32 )
          {
LABEL_44:
            v17 = v13 < v8;
            goto LABEL_45;
          }
          ++v19;
        }
      }
    }
LABEL_94:
    pExceptionObject = 6;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  if ( v7 + 1 >= v13
    || (v14 = *(_QWORD *)this, *(_WORD *)(*(_QWORD *)this + 2 * v7 + 2) != 114)
    || v7 + 2 >= v13
    || *(_WORD *)(v14 + 2 * (v7 + 2)) != 117
    || v7 + 3 >= v13
    || *(_WORD *)(v14 + 2 * (v7 + 3)) != 101 )
  {
    pExceptionObject = 6;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  v15 = 4;
  v16 = *((_QWORD *)this + 1);
  if ( v13 >= v7 + 4 )
    v16 = v7 + 4;
  *((_QWORD *)this + 3) = v16;
  while ( 1 )
  {
    v8 = v7 + v15;
    v17 = v13 < v7 + v15;
    if ( v13 <= v7 + v15 )
      break;
    if ( *(_WORD *)(*(_QWORD *)this + 2 * v8) != 9
      && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 10
      && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 13
      && *(_WORD *)(*(_QWORD *)this + 2 * v8) != 32 )
    {
      goto LABEL_44;
    }
    ++v15;
  }
LABEL_45:
  if ( !v17 )
    v13 = v8;
  *((_QWORD *)this + 2) = v13;
LABEL_57:
  v23 = v46;
  v21 = v44;
  while ( v23 )
  {
    if ( v23 >= 0 )
      v24 = v21 + 4 * ((unsigned __int64)v23 >> 5);
    else
      v24 = v21 - (4 * ((unsigned __int64)~v23 >> 5) + 4);
    v25 = v23 & 0x1F;
    v26 = v25 - 1;
    if ( v25 )
      v27 = (int *)(v24 + 4 * (v26 >> 5));
    else
      v27 = (int *)(v24 - (4 * (~v26 >> 5) + 4));
    v28 = *v27;
    if ( _bittest(&v28, ((_BYTE)v25 - 1) & 0x1F) )
    {
      LOBYTE(v27) = 125;
      Element = Marshal::JsonParser::NextElement(this, v27, 10);
      if ( Element )
      {
        Marshal::JsonParser::ParseObjectKey(this);
        Element = 1;
      }
    }
    else
    {
      LOBYTE(v27) = 93;
      Element = Marshal::JsonParser::NextElement(this, v27, 8);
    }
    if ( Element )
      goto LABEL_51;
    if ( v46 >= 0 )
      v30 = v44 + 4 * ((unsigned __int64)v46 >> 5);
    else
      v30 = v44 - (4 * ((unsigned __int64)~v46 >> 5) + 4);
    v31 = (v46 & 0x1F) - 1;
    if ( (v46 & 0x1F) != 0 )
      v32 = v30 + 4 * (v31 >> 5);
    else
      v32 = v30 - (4 * (~v31 >> 5) + 4);
    if ( v46 )
    {
      v33 = 32 * ((v32 - (__int64)v44) >> 2) + (((v46 & 0x1F) - 1) & 0x1F);
      if ( v33 >= 0 )
        v34 = v44 + 4 * ((unsigned __int64)v33 >> 5);
      else
        v34 = v44 - (4 * ((unsigned __int64)~v33 >> 5) + 4);
      v35 = v33 & 0x1F;
    }
    else
    {
      v35 = 0;
      v34 = v44;
    }
    if ( v46 >= 0 )
      v36 = v44 + 4 * ((unsigned __int64)v46 >> 5);
    else
      v36 = v44 - (4 * ((unsigned __int64)~v46 >> 5) + 4);
    v39[0] = v34;
    v39[1] = v35;
    v40[0] = v36;
    v40[1] = v46 & 0x1F;
    if ( v35 >= 0x1F )
      v34 += 4;
    v41[0] = v34;
    v41[1] = (v35 + 1) & -(__int64)(v35 < 0x1F);
    ((void (__fastcall *)(char *, _QWORD *, _QWORD *, _QWORD *))std::_Copy_vbool<std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>,std::_Vb_iterator<std::_Wrap_alloc<std::allocator<unsigned int>>>>)(
      v43,
      v41,
      v40,
      v39);
    v23 = v46 - 1;
    if ( (unsigned __int64)(v46 - 1) > 0x7FFFFFFFFFFFFFFFLL )
      std::vector<bool>::_Xlen(v23, v37, v38, v8);
    v7 = (unsigned __int64)(v23 + 31) >> 5;
    v21 = v44;
    if ( v7 < (__int64)(*((_QWORD *)&v44 + 1) - v44) >> 2 && (_QWORD)v44 + 4 * v7 != *((_QWORD *)&v44 + 1) )
      *((_QWORD *)&v44 + 1) = v44 + 4 * v7;
    --v46;
    if ( (v23 & 0x1F) != 0 )
    {
      *(_DWORD *)(v44 + 4 * v7 - 4) &= (1 << (v23 & 0x1F)) - 1;
      v23 = v46;
      v21 = v44;
    }
  }
LABEL_52:
  *a2 = *(_QWORD *)this + 2 * v4;
  a2[1] = *((_QWORD *)this + 3) - v4;
  std::vector<unsigned int>::~vector<unsigned int>(&v44, v21, v7, v8);
  return a2;
}

```

## disassembly

```asm
0x14001e274  mov     [rsp-8+arg_8], rbx
0x14001e279  mov     [rsp-8+arg_10], rsi
0x14001e27e  push    rbp
0x14001e27f  push    rdi
0x14001e280  push    r15
0x14001e282  lea     rbp, [rsp-47h]
0x14001e287  sub     rsp, 90h
0x14001e28e  mov     rdi, rdx
0x14001e291  mov     rbx, rcx
0x14001e294  mov     rsi, [rcx+10h]
0x14001e298  xorps   xmm0, xmm0
0x14001e29b  movdqu  [rbp+57h+var_30], xmm0
0x14001e2a0  mov     [rbp+57h+var_20], 0
0x14001e2a8  mov     [rbp+57h+var_18], 0
0x14001e2b0  mov     r15d, 1Fh
0x14001e2b6  mov     rcx, rbx
0x14001e2b9  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001e2be  test    eax, eax
0x14001e2c0  jz      loc_14001E516
0x14001e2c6  sub     eax, 1
0x14001e2c9  jz      loc_14001E50C
0x14001e2cf  sub     eax, 1
0x14001e2d2  jz      loc_14001E4EF
0x14001e2d8  sub     eax, 1
0x14001e2db  jz      loc_14001E476
0x14001e2e1  sub     eax, 1
0x14001e2e4  jz      short loc_14001E2FC
0x14001e2e6  cmp     eax, 1
0x14001e2e9  jnz     loc_14001E522
0x14001e2ef  mov     rcx, rbx; this
0x14001e2f2  call    ?ParseNull@JsonParser@Marshal@@QEAAXXZ; Marshal::JsonParser::ParseNull(void)
0x14001e2f7  jmp     loc_14001E522
0x14001e2fc  mov     rdx, [rbx+8]
0x14001e300  mov     r8, [rbx+10h]
0x14001e304  cmp     r8, rdx
0x14001e307  jnb     loc_14001E760
0x14001e30d  mov     rax, [rbx]
0x14001e310  cmp     word ptr [rax+r8*2], 74h ; 't'
0x14001e316  jnz     loc_14001E3B3
0x14001e31c  lea     rax, [r8+1]
0x14001e320  cmp     rax, rdx
0x14001e323  jnb     loc_14001E77E
0x14001e329  mov     rax, [rbx]
0x14001e32c  cmp     word ptr [rax+r8*2+2], 72h ; 'r'
0x14001e333  jnz     loc_14001E77E
0x14001e339  lea     rcx, [r8+2]
0x14001e33d  cmp     rcx, rdx
0x14001e340  jnb     loc_14001E77E
0x14001e346  cmp     word ptr [rax+rcx*2], 75h ; 'u'
0x14001e34b  jnz     loc_14001E77E
0x14001e351  lea     rcx, [r8+3]
0x14001e355  cmp     rcx, rdx
0x14001e358  jnb     loc_14001E77E
0x14001e35e  cmp     word ptr [rax+rcx*2], 65h ; 'e'
0x14001e363  jnz     loc_14001E77E
0x14001e369  mov     r10d, 4
0x14001e36f  lea     rcx, [r8+4]
0x14001e373  mov     rax, rdx
0x14001e376  cmp     rdx, rcx
0x14001e379  cmovnb  rax, rcx
0x14001e37d  mov     [rbx+18h], rax
0x14001e381  lea     r9, [r8+r10]
0x14001e385  cmp     rdx, r9
0x14001e388  jbe     loc_14001E469
0x14001e38e  mov     rax, [rbx]
0x14001e391  movzx   ecx, word ptr [rax+r9*2]
0x14001e396  sub     ecx, 9
0x14001e399  jz      short loc_14001E3AE
0x14001e39b  sub     ecx, 1
0x14001e39e  jz      short loc_14001E3AE
0x14001e3a0  sub     ecx, 3
0x14001e3a3  jz      short loc_14001E3AE
0x14001e3a5  cmp     ecx, 13h
0x14001e3a8  jnz     loc_14001E466
0x14001e3ae  inc     r10
0x14001e3b1  jmp     short loc_14001E381
0x14001e3b3  cmp     word ptr [rax+r8*2], 66h ; 'f'
0x14001e3b9  jnz     loc_14001E760
0x14001e3bf  lea     rax, [r8+1]
0x14001e3c3  cmp     rax, rdx
0x14001e3c6  jnb     loc_14001E760
0x14001e3cc  mov     rax, [rbx]
0x14001e3cf  cmp     word ptr [rax+r8*2+2], 61h ; 'a'
0x14001e3d6  jnz     loc_14001E760
0x14001e3dc  lea     rcx, [r8+2]
0x14001e3e0  cmp     rcx, rdx
0x14001e3e3  jnb     loc_14001E760
0x14001e3e9  cmp     word ptr [rax+rcx*2], 6Ch ; 'l'
0x14001e3ee  jnz     loc_14001E760
0x14001e3f4  lea     rcx, [r8+3]
0x14001e3f8  cmp     rcx, rdx
0x14001e3fb  jnb     loc_14001E760
0x14001e401  cmp     word ptr [rax+rcx*2], 73h ; 's'
0x14001e406  jnz     loc_14001E760
0x14001e40c  lea     rcx, [r8+4]
0x14001e410  cmp     rcx, rdx
0x14001e413  jnb     loc_14001E760
0x14001e419  cmp     word ptr [rax+rcx*2], 65h ; 'e'
0x14001e41e  jnz     loc_14001E760
0x14001e424  mov     r10d, 5
0x14001e42a  lea     rcx, [r8+5]
0x14001e42e  mov     rax, rdx
0x14001e431  cmp     rdx, rcx
0x14001e434  cmovnb  rax, rcx
0x14001e438  mov     [rbx+18h], rax
0x14001e43c  lea     r9, [r8+r10]
0x14001e440  cmp     rdx, r9
0x14001e443  jbe     short loc_14001E469
0x14001e445  mov     rax, [rbx]
0x14001e448  movzx   ecx, word ptr [rax+r9*2]
0x14001e44d  sub     ecx, 9
0x14001e450  jz      short loc_14001E461
0x14001e452  sub     ecx, 1
0x14001e455  jz      short loc_14001E461
0x14001e457  sub     ecx, 3
0x14001e45a  jz      short loc_14001E461
0x14001e45c  cmp     ecx, 13h
0x14001e45f  jnz     short loc_14001E466
0x14001e461  inc     r10
0x14001e464  jmp     short loc_14001E43C
0x14001e466  cmp     rdx, r9
0x14001e469  cmovnb  rdx, r9
0x14001e46d  mov     [rbx+10h], rdx
0x14001e471  jmp     loc_14001E522
0x14001e476  mov     r9d, 9
0x14001e47c  mov     r8b, 7Dh ; '}'
0x14001e47f  mov     dl, 7Bh ; '{'
0x14001e481  mov     rcx, rbx
0x14001e484  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14001e489  test    al, al
0x14001e48b  jz      loc_14001E522
0x14001e491  mov     rcx, rbx; this
0x14001e494  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14001e499  mov     byte ptr [rbp+57h+pExceptionObject], 1
0x14001e49d  lea     rdx, [rbp+57h+pExceptionObject]
0x14001e4a1  lea     rcx, [rbp+57h+var_30]
0x14001e4a5  call    ?push_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXAEB_N@Z; std::vector<bool>::push_back(bool const &)
0x14001e4aa  cmp     [rbp+57h+var_18], 0
0x14001e4af  jnz     loc_14001E2B6
0x14001e4b5  mov     rax, [rbx]
0x14001e4b8  lea     rcx, [rax+rsi*2]
0x14001e4bc  mov     [rdi], rcx
0x14001e4bf  mov     rax, [rbx+18h]
0x14001e4c3  sub     rax, rsi
0x14001e4c6  mov     [rdi+8], rax
0x14001e4ca  lea     rcx, [rbp+57h+var_30]
0x14001e4ce  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x14001e4d3  mov     rax, rdi
0x14001e4d6  lea     r11, [rsp+0A0h+var_10]
0x14001e4de  mov     rbx, [r11+28h]
0x14001e4e2  mov     rsi, [r11+30h]
0x14001e4e6  mov     rsp, r11
0x14001e4e9  pop     r15
0x14001e4eb  pop     rdi
0x14001e4ec  pop     rbp
0x14001e4ed  retn
0x14001e4ef  mov     r9d, 7
0x14001e4f5  mov     r8b, 5Dh ; ']'
0x14001e4f8  mov     dl, 5Bh ; '['
0x14001e4fa  mov     rcx, rbx
0x14001e4fd  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x14001e502  test    al, al
0x14001e504  jz      short loc_14001E522
0x14001e506  mov     byte ptr [rbp+57h+pExceptionObject], 0
0x14001e50a  jmp     short loc_14001E49D
0x14001e50c  mov     rcx, rbx
0x14001e50f  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x14001e514  jmp     short loc_14001E522
0x14001e516  lea     rdx, [rbp+57h+var_50]
0x14001e51a  mov     rcx, rbx
0x14001e51d  call    ?ParseNumber@JsonParser@Marshal@@QEAA?AUNumber@12@XZ; Marshal::JsonParser::ParseNumber(void)
0x14001e522  mov     rcx, [rbp+57h+var_18]
0x14001e526  mov     rdx, qword ptr [rbp+57h+var_30]
0x14001e52a  test    rcx, rcx
0x14001e52d  jz      short loc_14001E4B5
0x14001e52f  jns     short loc_14001E550
0x14001e531  mov     rax, rcx
0x14001e534  neg     rax
0x14001e537  jz      short loc_14001E550
0x14001e539  mov     rax, rcx
0x14001e53c  not     rax
0x14001e53f  shr     rax, 5
0x14001e543  lea     rax, ds:4[rax*4]
0x14001e54b  sub     rdx, rax
0x14001e54e  jmp     short loc_14001E55B
0x14001e550  mov     rax, rcx
0x14001e553  shr     rax, 5
0x14001e557  lea     rdx, [rdx+rax*4]
0x14001e55b  mov     rax, r15
0x14001e55e  and     rcx, rax
0x14001e561  lea     r8, [rcx-1]
0x14001e565  mov     rax, r8
0x14001e568  cmp     rcx, 1
0x14001e56c  jnb     short loc_14001E582
0x14001e56e  not     rax
0x14001e571  shr     rax, 5
0x14001e575  lea     rax, ds:4[rax*4]
0x14001e57d  sub     rdx, rax
0x14001e580  jmp     short loc_14001E58A
0x14001e582  shr     rax, 5
0x14001e586  lea     rdx, [rdx+rax*4]
0x14001e58a  mov     al, r8b
0x14001e58d  and     al, r15b
0x14001e590  movzx   ecx, al
0x14001e593  mov     eax, [rdx]
0x14001e595  bt      eax, ecx
0x14001e598  mov     rcx, rbx
0x14001e59b  jnb     short loc_14001E5BA
0x14001e59d  mov     r8d, 0Ah
0x14001e5a3  mov     dl, 7Dh ; '}'
0x14001e5a5  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14001e5aa  test    al, al
0x14001e5ac  jz      short loc_14001E5C7
0x14001e5ae  mov     rcx, rbx; this
0x14001e5b1  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x14001e5b6  mov     al, 1
0x14001e5b8  jmp     short loc_14001E5C7
0x14001e5ba  mov     r8d, 8
0x14001e5c0  mov     dl, 5Dh ; ']'
0x14001e5c2  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x14001e5c7  test    al, al
0x14001e5c9  jnz     loc_14001E4AA
0x14001e5cf  mov     rdx, qword ptr [rbp+57h+var_30]
0x14001e5d3  mov     rcx, [rbp+57h+var_18]
0x14001e5d7  test    rcx, rcx
0x14001e5da  jns     short loc_14001E5FE
0x14001e5dc  mov     rax, rcx
0x14001e5df  neg     rax
0x14001e5e2  jz      short loc_14001E5FE
0x14001e5e4  mov     rax, rcx
0x14001e5e7  not     rax
0x14001e5ea  shr     rax, 5
0x14001e5ee  lea     rax, ds:4[rax*4]
0x14001e5f6  mov     r8, rdx
0x14001e5f9  sub     r8, rax
0x14001e5fc  jmp     short loc_14001E609
0x14001e5fe  mov     rax, rcx
0x14001e601  shr     rax, 5
0x14001e605  lea     r8, [rdx+rax*4]
0x14001e609  mov     rax, r15
0x14001e60c  mov     r10, rcx
0x14001e60f  and     r10, rax
0x14001e612  lea     r9, [r10-1]
0x14001e616  mov     rax, r9
0x14001e619  cmp     r10, 1
0x14001e61d  jnb     short loc_14001E633
0x14001e61f  not     rax
0x14001e622  shr     rax, 5
0x14001e626  lea     rax, ds:4[rax*4]
0x14001e62e  sub     r8, rax
0x14001e631  jmp     short loc_14001E63B
0x14001e633  shr     rax, 5
0x14001e637  lea     r8, [r8+rax*4]
0x14001e63b  test    rcx, rcx
0x14001e63e  jz      short loc_14001E685
0x14001e640  sub     r8, rdx
0x14001e643  sar     r8, 2
0x14001e647  shl     r8, 5
0x14001e64b  and     r9, r15
0x14001e64e  add     r9, r8
0x14001e651  jns     short loc_14001E678
0x14001e653  mov     rax, r9
0x14001e656  neg     rax
0x14001e659  jz      short loc_14001E678
0x14001e65b  mov     rax, r9
0x14001e65e  not     rax
0x14001e661  shr     rax, 5
0x14001e665  lea     rax, ds:4[rax*4]
0x14001e66d  mov     r8, rdx
0x14001e670  sub     r8, rax
0x14001e673  and     r9, r15
0x14001e676  jmp     short loc_14001E68B
0x14001e678  mov     rax, r9
0x14001e67b  shr     rax, 5
0x14001e67f  lea     r8, [rdx+rax*4]
0x14001e683  jmp     short loc_14001E673
0x14001e685  xor     r9d, r9d
0x14001e688  mov     r8, rdx
0x14001e68b  test    rcx, rcx
0x14001e68e  jns     short loc_14001E6AC
0x14001e690  mov     rax, rcx
0x14001e693  neg     rax
0x14001e696  jz      short loc_14001E6AC
0x14001e698  not     rcx
0x14001e69b  shr     rcx, 5
0x14001e69f  lea     rax, ds:4[rcx*4]
0x14001e6a7  sub     rdx, rax
0x14001e6aa  jmp     short loc_14001E6B4
0x14001e6ac  shr     rcx, 5
0x14001e6b0  lea     rdx, [rdx+rcx*4]
0x14001e6b4  mov     [rbp+57h+var_80], r8
0x14001e6b8  mov     [rbp+57h+var_78], r9
0x14001e6bc  mov     [rbp+57h+var_70], rdx
0x14001e6c0  mov     [rbp+57h+var_68], r10
0x14001e6c4  lea     rax, [r8+4]
0x14001e6c8  cmp     r9, r15
0x14001e6cb  cmovnb  r8, rax
0x14001e6cf  mov     [rbp+57h+var_60], r8
0x14001e6d3  lea     rcx, [r9+1]
0x14001e6d7  sbb     rax, rax
  ... truncated ...
```
