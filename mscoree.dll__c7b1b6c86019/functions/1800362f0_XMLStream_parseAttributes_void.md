# XMLStream::parseAttributes(void)

- ea: `0x1800362f0`
- end: `0x1800365f1`
- name: `?parseAttributes@XMLStream@@AEAAJXZ`
- size: `769`
- prototype: `__int64 __fastcall(XMLStream *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800362f0`
- `0x180037720`
- `0x1800382a8`
- `0x180038320`
- `0x1800383d0`
- `0x180038f2c`

## pseudocode

```c
__int64 __fastcall XMLStream::parseAttributes(XMLStream *this)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 result; // rax
  int v11; // ecx
  __int16 v12; // ax
  BufferedStream *v13; // rcx
  __int16 v14; // ax
  _DWORD *v15; // r8
  int v16; // edx
  int v17; // ecx
  int v18; // ecx
  __int16 v19; // ax

  v2 = *((__int16 *)this + 4);
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        v5 = v4 - 1;
        if ( v5 )
        {
          v6 = v5 - 1;
          if ( v6 )
          {
            v7 = v6 - 1;
            if ( v7 )
            {
              v8 = v7 - 1;
              if ( v8 )
              {
                v9 = v8 - 1;
                if ( v9 )
                {
                  if ( v9 != 1 )
                    return 3222070546LL;
LABEL_14:
                  if ( !*((_BYTE *)this + 130) )
                  {
                    v11 = *(_DWORD *)(*((_QWORD *)this + 11) + 28LL) - *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) + 1;
                    *((_WORD *)this + 4) = 2;
                    *((_DWORD *)this + 28) += v11;
                    return 0;
                  }
                  return 3222070622LL;
                }
                *((_DWORD *)this + 28) = *(_DWORD *)(*((_QWORD *)this + 11) + 16LL)
                                       + ~*(_DWORD *)(*((_QWORD *)this + 11) + 28LL);
                result = XMLStream::push((__int64)this, (__int64)XMLStream::skipWhiteSpace, 8);
                if ( !(_DWORD)result )
                {
                  result = XMLStream::skipWhiteSpace(this);
                  if ( !(_DWORD)result )
                  {
                    *((_WORD *)this + 4) = 8;
                    goto LABEL_14;
                  }
                }
              }
              else
              {
                if ( *((_BYTE *)this + 130) )
                  return 3222070622LL;
                v12 = *((_WORD *)this + 61);
                if ( v12 == *((_WORD *)this + 64) || v12 == 62 )
                {
                  result = XMLStream::pop(this, 1);
                  if ( (_DWORD)result )
                    return result;
                  return 0;
                }
                if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
                {
                  result = 0;
                  *((_WORD *)this + 4) = 0;
                }
                else
                {
                  return 3222070537LL;
                }
              }
              return result;
            }
            goto LABEL_33;
          }
        }
        else
        {
          if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
            return 3222070547LL;
          *((_BYTE *)this + 124) = 0;
          *((_WORD *)this + 4) = 4;
        }
        if ( *((_WORD *)this + 61) != 61 )
          return 3222070529LL;
        result = BufferedStream::nextChar(
                   *((BufferedStream **)this + 11),
                   (unsigned __int16 *)this + 61,
                   (bool *)this + 130);
        if ( (_DWORD)result )
          return result;
        if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
        {
          result = XMLStream::push((__int64)this, (__int64)XMLStream::skipWhiteSpace, 5);
          if ( (_DWORD)result )
            return result;
          result = XMLStream::skipWhiteSpace(this);
          if ( (_DWORD)result )
            return result;
        }
        *((_WORD *)this + 4) = 5;
LABEL_33:
        v13 = (BufferedStream *)*((_QWORD *)this + 11);
        if ( *((_DWORD *)v13 + 20) != *((_DWORD *)v13 + 4) )
        {
          v14 = *((_WORD *)this + 61);
          if ( v14 != 34 && v14 != 39 )
            return 3222070530LL;
          *((_WORD *)this + 63) = v14;
          result = BufferedStream::nextChar(v13, (unsigned __int16 *)this + 61, (bool *)this + 130);
          if ( !(_DWORD)result )
          {
            v15 = (_DWORD *)*((_QWORD *)this + 11);
            v16 = v15[4];
            v17 = v16 - 1;
            if ( v16 <= 0 )
              v17 = 0;
            v15[7] = v17;
            v18 = v15[11];
            if ( v18 != v16 )
            {
              v15[12] = v15[10];
              v15[13] = v18;
            }
            return XMLStream::push((__int64)this, (__int64)XMLStream::parseAttrValue, 6);
          }
          return result;
        }
        return 3222070547LL;
      }
LABEL_55:
      if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) == *(_DWORD *)(*((_QWORD *)this + 11) + 16LL) )
      {
        *((_WORD *)this + 4) = 7;
        return 0;
      }
      if ( !*((_BYTE *)this + 130) )
      {
        *((_DWORD *)this + 27) = 2;
        *((_WORD *)this + 4) = 3;
        return 0;
      }
      return 3222070622LL;
    }
  }
  else
  {
    *((_BYTE *)this + 203) = 0;
    result = XMLStream::push((__int64)this, (__int64)XMLStream::skipWhiteSpace, 1);
    if ( (_DWORD)result )
      return result;
    result = XMLStream::skipWhiteSpace(this);
    if ( (_DWORD)result )
      return result;
    *((_WORD *)this + 4) = 1;
  }
  v19 = *((_WORD *)this + 61);
  if ( v19 == *((_WORD *)this + 64) || v19 == 62 )
    return XMLStream::pop(this, 1);
  result = XMLStream::push((__int64)this, (__int64)XMLStream::parseName, 2);
  if ( !(_DWORD)result )
  {
    result = XMLStream::parseName(this);
    if ( !(_DWORD)result )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 11) + 80LL) != *(_DWORD *)(*((_QWORD *)this + 11) + 16LL)
        && *((_WORD *)this + 61) != 61 )
      {
        return 3222070533LL;
      }
      *((_WORD *)this + 4) = 2;
      goto LABEL_55;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800362f0  push    rbx
0x1800362f2  push    rbp
0x1800362f3  push    rsi
0x1800362f4  push    r14
0x1800362f6  sub     rsp, 28h
0x1800362fa  mov     ebp, 2
0x1800362ff  mov     rbx, rcx
0x180036302  movsx   ecx, word ptr [rcx+8]
0x180036306  lea     esi, [rbp-1]
0x180036309  test    ecx, ecx
0x18003630b  jz      loc_180036523
0x180036311  sub     ecx, esi
0x180036313  jz      loc_180036558
0x180036319  sub     ecx, esi
0x18003631b  jz      loc_1800365AB
0x180036321  sub     ecx, esi
0x180036323  jz      loc_180036411
0x180036329  sub     ecx, esi
0x18003632b  jz      loc_18003642B
0x180036331  sub     ecx, esi
0x180036333  jz      loc_180036496
0x180036339  sub     ecx, esi
0x18003633b  jz      short loc_1800363B8
0x18003633d  sub     ecx, esi
0x18003633f  jz      short loc_18003634F
0x180036341  cmp     ecx, esi
0x180036343  jz      short loc_180036393
0x180036345  mov     eax, 0C00CE512h
0x18003634a  jmp     loc_1800365E7
0x18003634f  mov     rax, [rbx+58h]
0x180036353  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18003635a  mov     r14d, 8
0x180036360  mov     r8d, r14d
0x180036363  mov     ecx, [rax+1Ch]
0x180036366  not     ecx
0x180036368  add     ecx, [rax+10h]
0x18003636b  mov     [rbx+70h], ecx
0x18003636e  mov     rcx, rbx
0x180036371  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180036376  test    eax, eax
0x180036378  jnz     loc_1800365E7
0x18003637e  mov     rcx, rbx; this
0x180036381  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180036386  test    eax, eax
0x180036388  jnz     loc_1800365E7
0x18003638e  mov     [rbx+8], r14w
0x180036393  cmp     byte ptr [rbx+82h], 0
0x18003639a  jnz     loc_1800365CA
0x1800363a0  mov     rax, [rbx+58h]
0x1800363a4  mov     ecx, [rax+1Ch]
0x1800363a7  sub     ecx, [rax+10h]
0x1800363aa  add     ecx, esi
0x1800363ac  mov     [rbx+8], bp
0x1800363b0  add     [rbx+70h], ecx
0x1800363b3  jmp     loc_1800365BD
0x1800363b8  cmp     byte ptr [rbx+82h], 0
0x1800363bf  jnz     loc_1800365CA
0x1800363c5  movzx   eax, word ptr [rbx+7Ah]
0x1800363c9  cmp     ax, [rbx+80h]
0x1800363d0  jz      short loc_1800363F9
0x1800363d2  cmp     ax, 3Eh ; '>'
0x1800363d6  jz      short loc_1800363F9
0x1800363d8  mov     rcx, [rbx+58h]
0x1800363dc  mov     eax, [rcx+10h]
0x1800363df  cmp     [rcx+50h], eax
0x1800363e2  jz      short loc_1800363EE
0x1800363e4  mov     eax, 0C00CE509h
0x1800363e9  jmp     loc_1800365E7
0x1800363ee  xor     eax, eax
0x1800363f0  mov     [rbx+8], ax
0x1800363f4  jmp     loc_1800365E7
0x1800363f9  mov     dl, sil; bool
0x1800363fc  mov     rcx, rbx; this
0x1800363ff  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x180036404  test    eax, eax
0x180036406  jnz     loc_1800365E7
0x18003640c  jmp     loc_1800365BD
0x180036411  mov     rcx, [rbx+58h]
0x180036415  mov     eax, [rcx+10h]
0x180036418  cmp     [rcx+50h], eax
0x18003641b  jz      loc_180036519
0x180036421  mov     byte ptr [rbx+7Ch], 0
0x180036425  mov     word ptr [rbx+8], 4
0x18003642b  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x18003642f  cmp     word ptr [rdx], 3Dh ; '='
0x180036433  jz      short loc_18003643F
0x180036435  mov     eax, 0C00CE501h
0x18003643a  jmp     loc_1800365E7
0x18003643f  mov     rcx, [rbx+58h]; this
0x180036443  lea     r8, [rbx+82h]; bool *
0x18003644a  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x18003644f  test    eax, eax
0x180036451  jnz     loc_1800365E7
0x180036457  mov     rcx, [rbx+58h]
0x18003645b  mov     esi, 5
0x180036460  mov     eax, [rcx+10h]
0x180036463  cmp     [rcx+50h], eax
0x180036466  jnz     short loc_180036492
0x180036468  mov     r8d, esi
0x18003646b  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180036472  mov     rcx, rbx
0x180036475  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x18003647a  test    eax, eax
0x18003647c  jnz     loc_1800365E7
0x180036482  mov     rcx, rbx; this
0x180036485  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18003648a  test    eax, eax
0x18003648c  jnz     loc_1800365E7
0x180036492  mov     [rbx+8], si
0x180036496  mov     rcx, [rbx+58h]; this
0x18003649a  mov     eax, [rcx+10h]
0x18003649d  cmp     [rcx+50h], eax
0x1800364a0  jz      short loc_180036519
0x1800364a2  lea     rdx, [rbx+7Ah]; unsigned __int16 *
0x1800364a6  movzx   eax, word ptr [rdx]
0x1800364a9  cmp     ax, 22h ; '"'
0x1800364ad  jz      short loc_1800364BF
0x1800364af  cmp     ax, 27h ; '''
0x1800364b3  jz      short loc_1800364BF
0x1800364b5  mov     eax, 0C00CE502h
0x1800364ba  jmp     loc_1800365E7
0x1800364bf  lea     r8, [rbx+82h]; bool *
0x1800364c6  mov     [rbx+7Eh], ax
0x1800364ca  call    ?nextChar@BufferedStream@@QEAAJPEAGPEA_N@Z; BufferedStream::nextChar(ushort *,bool *)
0x1800364cf  test    eax, eax
0x1800364d1  jnz     loc_1800365E7
0x1800364d7  mov     r8, [rbx+58h]
0x1800364db  mov     edx, [r8+10h]
0x1800364df  test    edx, edx
0x1800364e1  lea     ecx, [rdx-1]
0x1800364e4  cmovle  ecx, eax
0x1800364e7  mov     [r8+1Ch], ecx
0x1800364eb  mov     ecx, [r8+2Ch]
0x1800364ef  cmp     ecx, edx
0x1800364f1  jz      short loc_1800364FF
0x1800364f3  mov     eax, [r8+28h]
0x1800364f7  mov     [r8+30h], eax
0x1800364fb  mov     [r8+34h], ecx
0x1800364ff  mov     r8d, 6
0x180036505  lea     rdx, ?parseAttrValue@XMLStream@@AEAAJXZ; XMLStream::parseAttrValue(void)
0x18003650c  mov     rcx, rbx
0x18003650f  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x180036514  jmp     loc_1800365E7
0x180036519  mov     eax, 0C00CE513h
0x18003651e  jmp     loc_1800365E7
0x180036523  mov     r8d, esi
0x180036526  mov     byte ptr [rbx+0CBh], 0
0x18003652d  lea     rdx, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180036534  mov     rcx, rbx
0x180036537  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x18003653c  test    eax, eax
0x18003653e  jnz     loc_1800365E7
0x180036544  mov     rcx, rbx; this
0x180036547  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18003654c  test    eax, eax
0x18003654e  jnz     loc_1800365E7
0x180036554  mov     [rbx+8], si
0x180036558  movzx   eax, word ptr [rbx+7Ah]
0x18003655c  cmp     ax, [rbx+80h]
0x180036563  jz      short loc_1800365DC
0x180036565  cmp     ax, 3Eh ; '>'
0x180036569  jz      short loc_1800365DC
0x18003656b  mov     r8d, ebp
0x18003656e  lea     rdx, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180036575  mov     rcx, rbx
0x180036578  call    ?push@XMLStream@@AEAAJP81@EAAJXZF@Z; XMLStream::push(long (XMLStream::*)(void),short)
0x18003657d  test    eax, eax
0x18003657f  jnz     short loc_1800365E7
0x180036581  mov     rcx, rbx; this
0x180036584  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180036589  test    eax, eax
0x18003658b  jnz     short loc_1800365E7
0x18003658d  mov     rcx, [rbx+58h]
0x180036591  mov     eax, [rcx+10h]
0x180036594  cmp     [rcx+50h], eax
0x180036597  jz      short loc_1800365A7
0x180036599  cmp     word ptr [rbx+7Ah], 3Dh ; '='
0x18003659e  jz      short loc_1800365A7
0x1800365a0  mov     eax, 0C00CE505h
0x1800365a5  jmp     short loc_1800365E7
0x1800365a7  mov     [rbx+8], bp
0x1800365ab  mov     rcx, [rbx+58h]
0x1800365af  mov     eax, [rcx+10h]
0x1800365b2  cmp     [rcx+50h], eax
0x1800365b5  jnz     short loc_1800365C1
0x1800365b7  mov     word ptr [rbx+8], 7
0x1800365bd  xor     eax, eax
0x1800365bf  jmp     short loc_1800365E7
0x1800365c1  cmp     byte ptr [rbx+82h], 0
0x1800365c8  jz      short loc_1800365D1
0x1800365ca  mov     eax, 0C00CE55Eh
0x1800365cf  jmp     short loc_1800365E7
0x1800365d1  mov     [rbx+6Ch], ebp
0x1800365d4  mov     word ptr [rbx+8], 3
0x1800365da  jmp     short loc_1800365BD
0x1800365dc  mov     dl, sil; bool
0x1800365df  mov     rcx, rbx; this
0x1800365e2  call    ?pop@XMLStream@@AEAAJ_N@Z; XMLStream::pop(bool)
0x1800365e7  add     rsp, 28h
0x1800365eb  pop     r14
0x1800365ed  pop     rsi
0x1800365ee  pop     rbp
0x1800365ef  pop     rbx
0x1800365f0  retn
```
