# XMLStream::parseEntityRef(void)

- ea: `0x180037050`
- end: `0x18003762e`
- name: `?parseEntityRef@XMLStream@@AEAAJXZ`
- size: `1502`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180035ed0`
- `0x180035f64`
- `0x180037050`
- `0x180037720`
- `0x1800382a8`
- `0x180038320`
- `0x180038960`
- `0x180038b30`
- `0x180038ef8`
- `0x180038f2c`

## pseudocode

```c
__int64 __fastcall XMLStream::parseEntityRef(XMLStream *this)
{
  int v1; // edi
  int v3; // edx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  BufferedStream *v8; // rcx
  __int16 v9; // ax
  unsigned int Char; // r8d
  __int64 v11; // r10
  unsigned int v12; // r8d
  __int64 v13; // r9
  int v14; // ecx
  __int64 result; // rax
  BufferedStream *v16; // rcx
  unsigned int v17; // edx
  __int64 v18; // r8
  __int64 v19; // r10
  unsigned __int16 *v20; // r10
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  bool v26; // zf
  _DWORD *v27; // rcx
  int v28; // eax
  int v29; // r8d
  int v30; // ecx
  int v31; // eax
  BufferedStream *v32; // rcx
  int v33; // r10d
  __int64 v34; // r10
  unsigned __int16 v35; // ax
  __int64 v36; // r8
  int v37; // edx
  int v38; // ecx
  int v39; // ecx
  __int64 v40; // rax
  unsigned __int16 v41; // dx
  _DWORD *v42; // r9
  int v43; // r8d
  int v44; // ecx
  int v45; // ecx
  int v46; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v47; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v47 = 0;
  v3 = 1;
  while ( 1 )
  {
    v4 = *((__int16 *)this + 4);
    if ( v4 <= 5 )
      break;
    v23 = v4 - 6;
    if ( v23 )
    {
      v24 = v23 - 2;
      if ( !v24 )
      {
        v42 = (_DWORD *)*((_QWORD *)this + 11);
        v43 = v42[4];
        v44 = v43 - 1;
        if ( v43 <= 0 )
          v44 = 0;
        v42[7] = v44;
        v45 = v42[11];
        if ( v45 != v43 )
        {
          v42[12] = v42[10];
          v42[13] = v45;
        }
        return XMLStream::pop(this, 1);
      }
      v25 = v24 - 2;
      if ( v25 )
      {
        v39 = v25 - 1;
        if ( !v39 )
        {
          v40 = *((int *)this + 48);
          v41 = *((_WORD *)this + 104);
          *((_BYTE *)this + 201) = 1;
          if ( (int)v40 >= *((_DWORD *)this + 49) )
          {
            XMLStream::_PushChar(this, v41);
          }
          else
          {
            *(_WORD *)(*((_QWORD *)this + 23) + 2 * v40) = v41;
            ++*((_DWORD *)this + 48);
          }
          *((_DWORD *)this + 27) = *((_DWORD *)this + 26);
          *((_WORD *)this + 4) = 12;
          return 0;
        }
        if ( v39 != 1 )
          return 3222070546LL;
        result = BufferedStream::nextChar(
                   *((BufferedStream **)this + 11),
                   (unsigned __int16 *)this + 61,
                   (bool *)this + 130);
        if ( !(_DWORD)result )
        {
          *((_WORD *)this + 4) = 8;
          return 0;
        }
        return result;
      }
      v26 = *((_DWORD *)this + 26) == 0;
      *((_DWORD *)this + 26) = *((_DWORD *)this + 27);
      if ( !v26 )
      {
        *((_DWORD *)this + 27) = 13;
        *((_DWORD *)this + 28) = -v1;
        *((_DWORD *)this + 29) = v1 - v3;
        *((_WORD *)this + 4) = 11;
        return 0;
      }
      v27 = (_DWORD *)*((_QWORD *)this + 11);
      if ( v27[4] <= v1 - v3 )
        v28 = 0;
      else
        v28 = v27[4] + ~(v1 - v3);
      v29 = v27[11];
      v27[7] = v28;
      if ( v29 != v27[4] )
      {
        v27[12] = v27[10];
        v27[13] = v29;
      }
      *((_WORD *)this + 4) = 11;
    }
    else
    {
      if ( *((_BYTE *)this + 130) )
        return 3222070617LL;
      if ( *((_WORD *)this + 61) != 59 )
        goto LABEL_99;
      v30 = *((_DWORD *)this + 33);
      if ( v30 <= 0 )
        v31 = 0;
      else
        v31 = v30 + ~*((_DWORD *)this + 35);
      v32 = (BufferedStream *)*((_QWORD *)this + 11);
      v33 = *((_DWORD *)this + 35);
      *((_DWORD *)this + 41) = v31;
      *((_BYTE *)this + 201) = 0;
      v1 = *((_DWORD *)v32 + 4) + ~*((_DWORD *)v32 + 7) - v33;
      BufferedStream::getToken(v32, (const unsigned __int16 **)&v47, &v46);
      v35 = BuiltinEntity(&v47[v34 + 1], v1 - 1);
      *((_WORD *)this + 104) = v35;
      if ( !v35 )
        return 3222070541LL;
      v3 = 1;
      *((_DWORD *)this + 27) = 60;
LABEL_25:
      *((_WORD *)this + 4) = 10;
    }
  }
  if ( v4 == 5 )
  {
    result = XMLStream::ScanHexDigits(this);
    if ( (_DWORD)result )
      return result;
    if ( *((_WORD *)this + 61) == 59 )
    {
      v16 = (BufferedStream *)*((_QWORD *)this + 11);
      v1 = *((_DWORD *)v16 + 4) + ~*((_DWORD *)v16 + 7) - *((_DWORD *)this + 35);
      BufferedStream::getToken(v16, (const unsigned __int16 **)&v47, &v46);
      v17 = 0;
      v18 = 0;
      v20 = &v47[v19];
      while ( 1 )
      {
        if ( (unsigned int)v18 >= v1 - 3 )
        {
          if ( v17 )
          {
            *((_WORD *)this + 104) = v17;
            v3 = 3;
            *((_DWORD *)this + 27) = 59;
            goto LABEL_25;
          }
          return 3222070559LL;
        }
        v21 = v20[v18 + 3];
        if ( (unsigned __int16)(v21 - 97) > 5u )
        {
          if ( (unsigned __int16)(v21 - 65) > 5u )
          {
            if ( (unsigned __int16)(v21 - 48) > 9u )
              return 3222070558LL;
            v22 = v21 - 48;
          }
          else
          {
            v22 = v21 - 55;
          }
        }
        else
        {
          v22 = v21 - 87;
        }
        if ( v17 >= (unsigned int)(0xFFFF - v22) >> 4 )
          return 3222070559LL;
        v17 = v22 + 16 * v17;
        v18 = (unsigned int)(v18 + 1);
      }
    }
LABEL_99:
    *((_WORD *)this + 4) = 9;
    return 0;
  }
  if ( !*((_WORD *)this + 4) )
  {
    v36 = *((_QWORD *)this + 11);
    *((_DWORD *)this + 26) = 0;
    v37 = *(_DWORD *)(v36 + 16) + ~*(_DWORD *)(v36 + 28);
    *((_DWORD *)this + 35) = v37;
    *((_BYTE *)this + 144) = v37 > 0;
    if ( v37 > 0 )
    {
      *((_DWORD *)this + 27) = *((_BYTE *)this + 124) != 0 ? 18 : 13;
      v38 = *(_DWORD *)(v36 + 16) + ~*(_DWORD *)(v36 + 28) - v37;
      *((_DWORD *)this + 29) = v38;
      *((_BYTE *)this + 144) = 0;
      *((_DWORD *)this + 28) = -v38;
      *((_QWORD *)this + 13) = *((unsigned int *)this + 27);
      *((_BYTE *)this + 124) = 1;
    }
    *((_WORD *)this + 4) = 1;
LABEL_70:
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    *((_WORD *)this + 4) = 2;
LABEL_72:
    if ( *((_BYTE *)this + 130) )
      return 3222070617LL;
    if ( *((_WORD *)this + 61) != 35 )
    {
      if ( (unsigned int)isStartNameChar(*((_WORD *)this + 61)) )
      {
        result = XMLStream::push(this, XMLStream::parseName, 6);
        if ( !(_DWORD)result )
        {
          *((_WORD *)this + 4) = 1;
          return XMLStream::parseName(this);
        }
      }
      else
      {
        result = 3222070532LL;
        if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
          return 3222070547LL;
      }
      return result;
    }
    result = BufferedStream::nextChar(
               *((BufferedStream **)this + 11),
               (unsigned __int16 *)this + 61,
               (bool *)this + 130);
    if ( (_DWORD)result )
      return result;
    *((_WORD *)this + 4) = 3;
    return 0;
  }
  v5 = v4 - 1;
  if ( !v5 )
    goto LABEL_70;
  v6 = v5 - 1;
  if ( !v6 )
    goto LABEL_72;
  v7 = v6 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 3222070546LL;
    while ( 1 )
    {
LABEL_13:
      if ( *((_BYTE *)this + 130) )
        return (unsigned int)-1072896679;
      v8 = (BufferedStream *)*((_QWORD *)this + 11);
      v9 = *((_WORD *)this + 61);
      if ( v9 == 59 )
        break;
      if ( (unsigned __int16)(v9 - 48) > 9u )
      {
        Char = -1072896749;
        if ( *((_DWORD *)v8 + 20) != *((_DWORD *)v8 + 4) )
          return (unsigned int)-1072896754;
        return Char;
      }
      Char = BufferedStream::nextChar(v8, (unsigned __int16 *)this + 61, (bool *)this + 130);
      if ( Char )
        return Char;
    }
    v1 = *((_DWORD *)v8 + 4) + ~*((_DWORD *)v8 + 7) - *((_DWORD *)this + 35);
    BufferedStream::getToken(v8, (const unsigned __int16 **)&v47, &v46);
    v12 = 0;
    v13 = 0;
    while ( (unsigned int)v13 < v1 - 2 )
    {
      v14 = v47[v11 + 2 + v13];
      if ( (unsigned __int16)(v14 - 48) > 9u )
        return 3222070557LL;
      if ( v12 >= (0xFFFF - (v14 - 48)) / 0xAu )
        return 3222070559LL;
      v13 = (unsigned int)(v13 + 1);
      v12 = v14 - 48 + 10 * v12;
    }
    if ( !v12 )
      return 3222070559LL;
    *((_WORD *)this + 104) = v12;
    v3 = 2;
    *((_DWORD *)this + 27) = 58;
    goto LABEL_25;
  }
  if ( *((_BYTE *)this + 130) )
    return 3222070617LL;
  if ( *((_WORD *)this + 61) != 120 )
  {
    *((_WORD *)this + 4) = 4;
    goto LABEL_13;
  }
  result = BufferedStream::nextChar(*((BufferedStream **)this + 11), (unsigned __int16 *)this + 61, (bool *)this + 130);
  if ( !(_DWORD)result )
  {
    *((_WORD *)this + 4) = 5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180037050  mov     [rsp+arg_10], rbx
0x180037055  mov     [rsp+arg_18], rsi
0x18003705a  push    rdi
0x18003705b  push    r12
0x18003705d  push    r13
0x18003705f  push    r14
0x180037061  push    r15
0x180037063  sub     rsp, 20h
0x180037067  xor     edi, edi
0x180037069  mov     rbx, rcx
0x18003706c  mov     [rsp+48h+arg_8], rdi
0x180037071  lea     r14d, [rdi+1]
0x180037075  mov     edx, r14d
0x180037078  lea     esi, [rdi+2]
0x18003707b  lea     r15d, [rdi+5]
0x18003707f  lea     r12d, [rdi+3Bh]
0x180037083  lea     r13d, [rdi+9]
0x180037087  mov     r9d, 0Bh
0x18003708d  mov     r8d, 30h ; '0'
0x180037093  movsx   ecx, word ptr [rbx+8]
0x180037097  cmp     ecx, r15d
0x18003709a  jg      loc_1800372B4
0x1800370a0  jz      loc_1800371E8
0x1800370a6  test    ecx, ecx
0x1800370a8  jz      loc_1800373FB
0x1800370ae  sub     ecx, r14d
0x1800370b1  jz      loc_180037468
0x1800370b7  sub     ecx, r14d
0x1800370ba  jz      loc_180037488
0x1800370c0  sub     ecx, r14d
0x1800370c3  jz      short loc_1800370D0
0x1800370c5  cmp     ecx, r14d
0x1800370c8  jnz     loc_180037548
0x1800370ce  jmp     short loc_1800370FB
0x1800370d0  lea     r8, [rbx+82h]; bool *
0x1800370d7  cmp     byte ptr [r8], 0
0x1800370db  jnz     loc_180037611
0x1800370e1  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x1800370e5  cmp     word ptr [rdx], 78h ; 'x'
0x1800370e9  jz      loc_1800373DE
0x1800370ef  mov     word ptr [rbx+8], 4
0x1800370f5  mov     r8d, 30h ; '0'
0x1800370fb  lea     rdi, [rbx+82h]
0x180037102  cmp     byte ptr [rdi], 0
0x180037105  jnz     loc_1800373D0
0x18003710b  mov     rcx, [rbx+58h]; this
0x18003710f  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037113  movzx   eax, word ptr [rdx]
0x180037116  cmp     ax, r12w
0x18003711a  jz      short loc_180037143
0x18003711c  sub     ax, r8w
0x180037120  cmp     ax, r13w
0x180037124  ja      loc_1800373A7
0x18003712a  mov     r8, rdi; bool *
0x18003712d  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x180037132  mov     r8d, eax
0x180037135  test    eax, eax
0x180037137  jnz     loc_1800373D6
0x18003713d  lea     r8d, [rax+30h]
0x180037141  jmp     short loc_180037102
0x180037143  mov     edi, [rcx+1Ch]
0x180037146  lea     r8, [rsp+48h+arg_0]; int *
0x18003714b  movsxd  r10, dword ptr [rbx+8Ch]
0x180037152  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 **
0x180037157  not     edi
0x180037159  add     edi, [rcx+10h]
0x18003715c  sub     edi, r10d
0x18003715f  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180037164  mov     rax, [rsp+48h+arg_8]
0x180037169  lea     r11d, [rdi-2]
0x18003716d  xor     r8d, r8d
0x180037170  xor     r9d, r9d
0x180037173  lea     rsi, [rax+r10*2]
0x180037177  cmp     r9d, r11d
0x18003717a  jnb     short loc_1800371BE
0x18003717c  movzx   ecx, word ptr [rsi+r9*2+4]
0x180037182  lea     eax, [rcx-30h]
0x180037185  cmp     ax, r13w
0x180037189  ja      loc_1800373BC
0x18003718f  mov     r10d, ecx
0x180037192  mov     eax, 0CCCCCCCDh
0x180037197  add     r10d, 0FFFFFFD0h
0x18003719b  mov     ecx, 0FFFFh
0x1800371a0  sub     ecx, r10d
0x1800371a3  mul     ecx
0x1800371a5  shr     edx, 3
0x1800371a8  cmp     r8d, edx
0x1800371ab  jnb     loc_1800373C6
0x1800371b1  lea     eax, [r8+r8*4]
0x1800371b5  add     r9d, r14d
0x1800371b8  lea     r8d, [r10+rax*2]
0x1800371bc  jmp     short loc_180037177
0x1800371be  test    r8d, r8d
0x1800371c1  jz      loc_1800373C6
0x1800371c7  mov     esi, 2
0x1800371cc  mov     [rbx+0D0h], r8w
0x1800371d4  mov     edx, esi
0x1800371d6  mov     dword ptr [rbx+6Ch], 3Ah ; ':'
0x1800371dd  mov     word ptr [rbx+8], 0Ah
0x1800371e3  jmp     loc_180037087
0x1800371e8  mov     rcx, rbx; this
0x1800371eb  call    ?ScanHexDigits@XMLStream@@AEAAJXZ; XMLStream::ScanHexDigits(void)
0x1800371f0  test    eax, eax
0x1800371f2  jnz     loc_180037616
0x1800371f8  cmp     [rbx+7Ah], r12w
0x1800371fd  jnz     loc_180037607
0x180037203  mov     rcx, [rbx+58h]; this
0x180037207  lea     r8, [rsp+48h+arg_0]; int *
0x18003720c  movsxd  r10, dword ptr [rbx+8Ch]
0x180037213  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 **
0x180037218  mov     edi, [rcx+1Ch]
0x18003721b  not     edi
0x18003721d  add     edi, [rcx+10h]
0x180037220  sub     edi, r10d
0x180037223  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180037228  mov     rax, [rsp+48h+arg_8]
0x18003722d  lea     r9d, [rdi-3]
0x180037231  xor     edx, edx
0x180037233  xor     r8d, r8d
0x180037236  lea     r10, [rax+r10*2]
0x18003723a  cmp     r8d, r9d
0x18003723d  jnb     short loc_180037297
0x18003723f  movzx   ecx, word ptr [r10+r8*2+6]
0x180037245  lea     eax, [rcx-61h]
0x180037248  cmp     ax, r15w
0x18003724c  ja      short loc_180037253
0x18003724e  sub     ecx, 57h ; 'W'
0x180037251  jmp     short loc_18003727B
0x180037253  lea     eax, [rcx-41h]
0x180037256  cmp     ax, r15w
0x18003725a  ja      short loc_180037261
0x18003725c  sub     ecx, 37h ; '7'
0x18003725f  jmp     short loc_18003727B
0x180037261  movzx   eax, cx
0x180037264  mov     r11d, 30h ; '0'
0x18003726a  sub     ax, r11w
0x18003726e  cmp     ax, r13w
0x180037272  ja      loc_180037519
0x180037278  sub     ecx, r11d
0x18003727b  mov     eax, 0FFFFh
0x180037280  sub     eax, ecx
0x180037282  shr     eax, 4
0x180037285  cmp     edx, eax
0x180037287  jnb     loc_1800373C6
0x18003728d  shl     edx, 4
0x180037290  add     edx, ecx
0x180037292  add     r8d, r14d
0x180037295  jmp     short loc_18003723A
0x180037297  test    edx, edx
0x180037299  jz      loc_1800373C6
0x18003729f  mov     [rbx+0D0h], dx
0x1800372a6  mov     edx, 3
0x1800372ab  mov     [rbx+6Ch], r12d
0x1800372af  jmp     loc_1800371DD
0x1800372b4  sub     ecx, 6
0x1800372b7  jz      short loc_18003730F
0x1800372b9  sub     ecx, esi
0x1800372bb  jz      loc_1800375C6
0x1800372c1  sub     ecx, esi
0x1800372c3  jnz     loc_18003753E
0x1800372c9  mov     eax, [rbx+6Ch]
0x1800372cc  cmp     [rbx+68h], ecx
0x1800372cf  mov     [rbx+68h], eax
0x1800372d2  mov     eax, edi
0x1800372d4  jnz     loc_180037523
0x1800372da  mov     rcx, [rbx+58h]
0x1800372de  sub     eax, edx
0x1800372e0  cmp     [rcx+10h], eax
0x1800372e3  jle     short loc_1800372EC
0x1800372e5  not     eax
0x1800372e7  add     eax, [rcx+10h]
0x1800372ea  jmp     short loc_1800372EE
0x1800372ec  xor     eax, eax
0x1800372ee  mov     r8d, [rcx+2Ch]
0x1800372f2  mov     [rcx+1Ch], eax
0x1800372f5  cmp     r8d, [rcx+10h]
0x1800372f9  jz      short loc_180037305
0x1800372fb  mov     eax, [rcx+28h]
0x1800372fe  mov     [rcx+30h], eax
0x180037301  mov     [rcx+34h], r8d
0x180037305  mov     [rbx+8], r9w
0x18003730a  jmp     loc_18003708D
0x18003730f  cmp     byte ptr [rbx+82h], 0
0x180037316  jnz     loc_180037611
0x18003731c  cmp     [rbx+7Ah], r12w
0x180037321  jnz     loc_180037607
0x180037327  mov     ecx, [rbx+84h]
0x18003732d  test    ecx, ecx
0x18003732f  jle     short loc_18003733D
0x180037331  mov     eax, [rbx+8Ch]
0x180037337  not     eax
0x180037339  add     eax, ecx
0x18003733b  jmp     short loc_18003733F
0x18003733d  xor     eax, eax
0x18003733f  mov     rcx, [rbx+58h]; this
0x180037343  lea     r8, [rsp+48h+arg_0]; int *
0x180037348  movsxd  r10, dword ptr [rbx+8Ch]
0x18003734f  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 **
0x180037354  mov     [rbx+0A4h], eax
0x18003735a  mov     byte ptr [rbx+0C9h], 0
0x180037361  mov     edi, [rcx+1Ch]
0x180037364  not     edi
0x180037366  add     edi, [rcx+10h]
0x180037369  sub     edi, r10d
0x18003736c  call    ?getToken@BufferedStream@@QEAAJPEAPEBGPEAJ@Z; BufferedStream::getToken(ushort const * *,long *)
0x180037371  mov     rax, [rsp+48h+arg_8]
0x180037376  lea     edx, [rdi-1]; unsigned int
0x180037379  add     rax, 2
0x18003737d  lea     rcx, [rax+r10*2]; Buf2
0x180037381  call    ?BuiltinEntity@@YAGPEBGK@Z; BuiltinEntity(ushort const *,ulong)
0x180037386  xor     ecx, ecx
0x180037388  mov     [rbx+0D0h], ax
0x18003738f  cmp     cx, ax
0x180037392  jz      loc_180037600
0x180037398  mov     edx, r14d
0x18003739b  mov     dword ptr [rbx+6Ch], 3Ch ; '<'
0x1800373a2  jmp     loc_1800371DD
0x1800373a7  mov     eax, [rcx+10h]
0x1800373aa  mov     edx, 0C00CE50Eh
0x1800373af  cmp     [rcx+50h], eax
0x1800373b2  lea     r8d, [rdx+5]
0x1800373b6  cmovnz  r8d, edx
0x1800373ba  jmp     short loc_1800373D6
0x1800373bc  mov     eax, 0C00CE51Dh
0x1800373c1  jmp     loc_180037616
0x1800373c6  mov     eax, 0C00CE51Fh
0x1800373cb  jmp     loc_180037616
0x1800373d0  mov     r8d, 0C00CE559h
0x1800373d6  mov     eax, r8d
0x1800373d9  jmp     loc_180037616
0x1800373de  mov     rcx, [rbx+58h]; this
0x1800373e2  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800373e7  test    eax, eax
0x1800373e9  jnz     loc_180037616
0x1800373ef  mov     [rbx+8], r15w
0x1800373f4  xor     eax, eax
0x1800373f6  jmp     loc_180037616
0x1800373fb  mov     r8, [rbx+58h]
0x1800373ff  mov     dword ptr [rbx+68h], 0
0x180037406  mov     edx, [r8+1Ch]
0x18003740a  not     edx
0x18003740c  add     edx, [r8+10h]
0x180037410  test    edx, edx
0x180037412  mov     [rbx+8Ch], edx
0x180037418  setnle  al
0x18003741b  mov     [rbx+90h], al
0x180037421  test    edx, edx
0x180037423  jle     short loc_180037463
0x180037425  mov     al, [rbx+7Ch]
0x180037428  neg     al
0x18003742a  sbb     ecx, ecx
0x18003742c  and     ecx, r15d
0x18003742f  add     ecx, 0Dh
0x180037432  mov     [rbx+6Ch], ecx
0x180037435  mov     ecx, [r8+1Ch]
0x180037439  not     ecx
0x18003743b  sub     ecx, edx
0x18003743d  add     ecx, [r8+10h]
0x180037441  mov     eax, ecx
0x180037443  mov     [rbx+74h], ecx
0x180037446  neg     eax
0x180037448  mov     byte ptr [rbx+90h], 0
0x18003744f  mov     [rbx+70h], eax
0x180037452  mov     eax, [rbx+6Ch]
0x180037455  mov     [rbx+68h], eax
0x180037458  mov     dword ptr [rbx+6Ch], 0
0x18003745f  mov     [rbx+7Ch], r14b
0x180037463  mov     [rbx+8], r14w
0x180037468  mov     rcx, [rbx+58h]; this
0x18003746c  lea     r8, [rbx+82h]; bool *
0x180037473  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x180037477  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x18003747c  test    eax, eax
0x18003747e  jnz     loc_180037616
0x180037484  mov     [rbx+8], si
0x180037488  lea     r8, [rbx+82h]; bool *
0x18003748f  cmp     byte ptr [r8], 0
0x180037493  jnz     loc_180037611
0x180037499  lea     rcx, [rbx+7Ah]
0x18003749d  cmp     word ptr [rcx], 23h ; '#'
0x1800374a1  jnz     short loc_1800374C2
0x1800374a3  mov     rdx, rcx; unsigned __int16 *
0x1800374a6  mov     rcx, [rbx+58h]; this
0x1800374aa  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800374af  test    eax, eax
0x1800374b1  jnz     loc_180037616
0x1800374b7  mov     word ptr [rbx+8], 3
0x1800374bd  jmp     loc_1800373F4
0x1800374c2  movzx   ecx, word ptr [rcx]; unsigned __int16
0x1800374c5  call    ?isStartNameChar@@YAHG@Z; isStartNameChar(ushort)
0x1800374ca  test    eax, eax
0x1800374cc  jnz     short loc_1800374EA
0x1800374ce  mov     rdx, [rbx+58h]
0x1800374d2  mov     eax, 0C00CE504h
0x1800374d7  mov     ecx, [rdx+10h]
0x1800374da  lea     r8d, [rax+0Fh]
0x1800374de  cmp     [rdx+50h], ecx
0x1800374e1  cmovz   eax, r8d
0x1800374e5  jmp     loc_180037616
0x1800374ea  mov     r8d, 6
  ... truncated ...
```
