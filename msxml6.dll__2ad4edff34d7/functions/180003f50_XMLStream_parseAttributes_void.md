# XMLStream::parseAttributes(void)

- ea: `0x180003f50`
- end: `0x1800049dc`
- name: `?parseAttributes@XMLStream@@AEAAJXZ`
- size: `2700`
- prototype: `HRESULT __fastcall(XMLStream *this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003010`
- `0x18000398c`
- `0x180003f50`
- `0x1800049f0`
- `0x180004ba0`
- `0x180005bec`
- `0x180005d70`
- `0x1800060fc`
- `0x18000632c`
- `0x180006370`
- `0x180006414`
- `0x180007230`

## string_xrefs

- `0x180004584`: `xml:space`
- `0x1800045a1`: `xml:lang`
- `0x1800045c3`: `xmlns`
- `0x1800045d9`: `xmlns`
- `0x18000496d`: `xmlns`

## pseudocode

```c
HRESULT __fastcall XMLStream::parseAttributes(XMLStream *this)
{
  unsigned int sSubState; // eax
  wchar_t v3; // ax
  HRESULT result; // eax
  int v5; // esi
  unsigned int ncUsed; // r8d
  __int64 v7; // rcx
  char *v8; // rcx
  wchar_t chLookahead; // ax
  unsigned int v10; // r8d
  __int64 v11; // rcx
  char *v12; // rcx
  BufferedStream *p; // rax
  int lCurrent; // ecx
  wchar_t *p_chLookahead; // r8
  BufferedStream *v16; // rdi
  int lUsed; // r9d
  __int64 v18; // rdx
  unsigned int v19; // r9d
  int v20; // edx
  bool v21; // zf
  BufferedStream *v22; // rdi
  wchar_t v23; // ax
  int v24; // r9d
  __int64 v25; // rdx
  unsigned int v26; // r8d
  int v27; // edx
  bool v28; // zf
  BufferedStream *v29; // rcx
  int v30; // eax
  int v31; // edx
  int lLinepos; // edx
  char *v33; // rax
  unsigned int v34; // eax
  char *v35; // r8
  _rawstack<XMLStream::StateInfo> *p_pStack; // rcx
  unsigned int v37; // eax
  char *v38; // r8
  wchar_t *pchBuffer; // rdx
  __int64 lMark; // rsi
  const wchar_t *v41; // rdi
  int v42; // esi
  int v43; // eax
  int NewStart; // eax
  BufferedStream *v45; // rax
  int v46; // ecx
  int v47; // ecx
  __int128 v48; // [rsp+20h] [rbp-18h] BYREF

  sSubState = this->_sSubState;
  if ( !sSubState )
  {
    result = this->_hrErr;
    v5 = 0;
    this->_nAttrType = 0;
    this->_fCheckAttribute = 0;
    if ( result )
    {
      if ( result < 0 )
        return result;
    }
    else
    {
      ncUsed = this->_pStack._ncUsed;
      if ( this->_pStack._ncSize == ncUsed )
      {
        v8 = RawStack::__push(&this->_pStack);
      }
      else
      {
        v7 = this->_pStack._lEntrySize * ncUsed;
        this->_pStack._ncUsed = ncUsed + 1;
        v8 = &this->_pStack._pStack[v7];
      }
      if ( !v8 )
        return -2147024882;
      *((_DWORD *)v8 + 4) = 1;
      *(_OWORD *)v8 = this->_fnState;
      *((_QWORD *)v8 + 3) = this->_pTable;
      *((_DWORD *)v8 + 8) = this->_lEOFError;
      *((_DWORD *)v8 + 9) = this->_cStreamDepth;
      *(_QWORD *)&this->_fnState = XMLStream::skipWhiteSpace;
      HIDWORD(this->_fnState) = HIDWORD(v48);
      this->_sSubState = 0;
      DWORD2(this->_fnState) = 0;
    }
    result = XMLStream::skipWhiteSpace(this);
    if ( result < 0 )
      return result;
    this->_sSubState = 1;
LABEL_16:
    chLookahead = this->_chLookahead;
    if ( chLookahead == this->_chEndChar || chLookahead == 62 )
    {
      v37 = this->_pStack._ncUsed;
      if ( v37 )
      {
        v38 = &this->_pStack._pStack[this->_pStack._lEntrySize * (v37 - 1)];
        if ( v38 )
        {
          result = this->_hrErr;
          if ( result )
          {
            if ( result < 0 )
              return result;
            return 0;
          }
          if ( !this->_fDTD
            || this->_fParsingAttDef
            || this->_fParseLiteral
            || this->_cStreamDepth == *((_DWORD *)v38 + 9) )
          {
            p_pStack = &this->_pStack;
            this->_fnState = *(_OWORD *)v38;
            this->_sSubState = *((_DWORD *)v38 + 4);
            this->_pTable = (const StateEntry *)*((_QWORD *)v38 + 3);
            this->_lEOFError = *((_DWORD *)v38 + 8);
            goto LABEL_96;
          }
          return -1072896677;
        }
      }
      return -1072896750;
    }
    if ( chLookahead == 120 )
      this->_fCheckAttribute = 1;
    result = this->_hrErr;
    if ( result )
    {
      if ( result < 0 )
        return result;
    }
    else
    {
      v10 = this->_pStack._ncUsed;
      if ( this->_pStack._ncSize == v10 )
      {
        v12 = RawStack::__push(&this->_pStack);
      }
      else
      {
        v11 = this->_pStack._lEntrySize * v10;
        this->_pStack._ncUsed = v10 + 1;
        v12 = &this->_pStack._pStack[v11];
      }
      if ( !v12 )
        return -2147024882;
      *((_DWORD *)v12 + 4) = 2;
      *(_OWORD *)v12 = this->_fnState;
      *((_QWORD *)v12 + 3) = this->_pTable;
      *((_DWORD *)v12 + 8) = this->_lEOFError;
      *((_DWORD *)v12 + 9) = this->_cStreamDepth;
      *(_QWORD *)&this->_fnState = XMLStream::parseName;
      HIDWORD(this->_fnState) = HIDWORD(v48);
      this->_sSubState = 0;
      DWORD2(this->_fnState) = 0;
    }
    result = XMLStream::parseName(this);
    if ( result < 0 )
      return result;
    if ( this->_pInput._p->_lLastWhiteSpace != this->_pInput._p->_lCurrent && this->_chLookahead != 61 )
      return -1072896763;
    this->_sSubState = 2;
LABEL_29:
    p = this->_pInput._p;
    lCurrent = p->_lCurrent;
    if ( p->_lLastWhiteSpace == lCurrent )
    {
      this->_sSubState = 7;
      return 0;
    }
    if ( this->_fEOF )
      return -1072896674;
    if ( this->_fCheckAttribute )
    {
      pchBuffer = p->_pchBuffer;
      if ( pchBuffer )
      {
        lMark = p->_lMark;
        v41 = &pchBuffer[lMark];
        v5 = lCurrent + ~(_DWORD)lMark;
      }
      else
      {
        v41 = &pwchNamespaceUri;
      }
      v42 = this->_lLengthDelta + v5;
      if ( StringEquals(L"xml:space", v41, v42) )
      {
        this->_nToken = 32;
        goto LABEL_33;
      }
      if ( StringEquals(L"xml:lang", v41, v42) )
      {
        this->_nToken = 33;
        goto LABEL_33;
      }
      if ( this->_lNslen == 5 && StringEquals(L"xmlns", v41, 5) || StringEquals(L"xmlns", v41, v42) )
      {
        if ( v42 == 11 && StringEquals(L"xmlns", v41 + 6, 5) )
          return -1072896664;
        this->_nToken = 31;
        goto LABEL_33;
      }
    }
    this->_nToken = 2;
LABEL_33:
    this->_sSubState = 3;
    return 0;
  }
  if ( sSubState == 3 )
  {
    if ( this->_pInput._p->_lLastWhiteSpace == this->_pInput._p->_lCurrent )
      return -1072896749;
    this->_fWhitespace = 0;
    this->_sSubState = 4;
$LN61:
    p_chLookahead = &this->_chLookahead;
    if ( this->_chLookahead != 61 )
      return -1072896767;
    if ( this->_fDTD )
    {
      result = XMLStream::DTDAdvance(this);
      goto LABEL_47;
    }
    v16 = this->_pInput._p;
    lUsed = v16->_lUsed;
    if ( v16->_lCurrent >= lUsed )
    {
      if ( v16->_fEof )
      {
        this->_fEOF = 1;
        result = 0;
        goto LABEL_47;
      }
      if ( !v16->_fNotified
        && lUsed > 0
        && ((v16->_fNotified = 1, !v16->_fFrozen) ? (v43 = BufferedStream::getNewStart(v16)) : (v43 = 0),
            result = XMLStream::ErrorCallback(v16->_pXMLStream, (v43 + v16->_lSize - lUsed < 4097) - 1072896512),
            v21 = result == 0,
            result < 0)
        || (result = BufferedStream::fillBuffer(v16), v21 = result == 0, result < 0) )
      {
LABEL_48:
        if ( !v21 )
          return result;
        if ( this->_pInput._p->_lLastWhiteSpace == this->_pInput._p->_lCurrent )
        {
          DWORD2(v48) = 0;
          *(_QWORD *)&v48 = XMLStream::skipWhiteSpace;
          result = XMLStream::push(this, &v48, 5u);
          if ( result < 0 )
            return result;
          result = XMLStream::skipWhiteSpace(this);
          if ( result < 0 )
            return result;
        }
        this->_sSubState = 5;
LABEL_51:
        v22 = this->_pInput._p;
        if ( v22->_lLastWhiteSpace != v22->_lCurrent )
        {
          v23 = this->_chLookahead;
          if ( v23 != 34 && v23 != 39 )
            return -1072896766;
          v21 = !this->_fDTD;
          this->_chTerminator = v23;
          if ( !v21 )
          {
            result = XMLStream::DTDAdvance(this);
            goto LABEL_62;
          }
          v24 = v22->_lUsed;
          if ( v22->_lCurrent >= v24 )
          {
            if ( v22->_fEof )
            {
              this->_fEOF = 1;
              result = 0;
              goto LABEL_62;
            }
            if ( !v22->_fNotified
              && v24 > 0
              && ((v21 = !v22->_fFrozen, v22->_fNotified = 1, v21)
                ? (NewStart = BufferedStream::getNewStart(v22))
                : (NewStart = 0),
                  result = XMLStream::ErrorCallback(
                             v22->_pXMLStream,
                             (NewStart + v22->_lSize - v24 < 4097) - 1072896512),
                  v28 = result == 0,
                  result < 0)
              || (result = BufferedStream::fillBuffer(v22), v28 = result == 0, result < 0) )
            {
LABEL_63:
              if ( !v28 )
                return result;
              v29 = this->_pInput._p;
              v30 = v29->_lCurrent;
              if ( v30 <= 0 )
                v31 = 0;
              else
                v31 = v30 - 1;
              v29->_lMark = v31;
              lLinepos = v29->_lLinepos;
              if ( lLinepos != v30 )
              {
                v29->_lMarkedline = v29->_lLine;
                v29->_lMarkedlinepos = lLinepos;
              }
              result = this->_hrErr;
              if ( result )
                return result;
              v33 = RawStack::_push(&this->_pStack);
              if ( v33 )
              {
                *((_DWORD *)v33 + 4) = 6;
                *(_OWORD *)v33 = this->_fnState;
                *((_QWORD *)v33 + 3) = this->_pTable;
                *((_DWORD *)v33 + 8) = this->_lEOFError;
                *((_DWORD *)v33 + 9) = this->_cStreamDepth;
                *(_QWORD *)&this->_fnState = XMLStream::parseAttrValue;
                HIDWORD(this->_fnState) = HIDWORD(v48);
                result = 0;
                this->_sSubState = 0;
                DWORD2(this->_fnState) = 0;
                return result;
              }
              return -2147024882;
            }
            if ( v22->_fEof )
            {
              this->_fEOF = 1;
              result = 0;
              goto LABEL_62;
            }
            v22->_fNotified = 0;
          }
          v25 = v22->_lCurrent;
          v26 = v22->_pchBuffer[v25];
          v27 = v25 + 1;
          v22->_lCurrent = v27;
          if ( v26 <= 0x20 )
          {
            if ( v26 != 32 && v26 != 9 )
            {
              if ( v26 != 10 && v26 != 13 )
                goto LABEL_60;
              if ( v26 == 13 || v22->_chLast != 13 )
                ++v22->_lLine;
              v22->_lLinepos = v27;
              v22->_chLast = v26;
            }
            v22->_lLastWhiteSpace = v27;
            goto LABEL_84;
          }
          if ( v26 - 65534 <= 1 )
            goto LABEL_61;
LABEL_60:
          if ( v26 < 0x20 )
          {
LABEL_61:
            result = -1072896760;
LABEL_62:
            v28 = result == 0;
            goto LABEL_63;
          }
LABEL_84:
          this->_chLookahead = v26;
          result = 0;
          goto LABEL_62;
        }
        return -1072896749;
      }
      if ( v16->_fEof )
      {
        this->_fEOF = 1;
        result = 0;
        goto LABEL_47;
      }
      v16->_fNotified = 0;
      p_chLookahead = &this->_chLookahead;
    }
    v18 = v16->_lCurrent;
    v19 = v16->_pchBuffer[v18];
    v20 = v18 + 1;
    v16->_lCurrent = v20;
    if ( v19 <= 0x20 )
    {
      if ( v19 != 32 && v19 != 9 )
      {
        if ( v19 != 10 && v19 != 13 )
          goto LABEL_45;
        if ( v19 == 13 || v16->_chLast != 13 )
        {
          ++v16->_lLine;
          p_chLookahead = &this->_chLookahead;
        }
        v16->_lLinepos = v20;
        v16->_chLast = v19;
      }
      v16->_lLastWhiteSpace = v20;
      goto LABEL_79;
    }
    if ( v19 - 65534 <= 1 )
      goto LABEL_46;
LABEL_45:
    if ( v19 < 0x20 )
    {
LABEL_46:
      result = -1072896760;
LABEL_47:
      v21 = result == 0;
      goto LABEL_48;
    }
LABEL_79:
    *p_chLookahead = v19;
    result = 0;
    goto LABEL_47;
  }
  if ( sSubState != 6 )
  {
    switch ( sSubState )
    {
      case 1u:
        v5 = 0;
        goto LABEL_16;
      case 2u:
        v5 = 0;
        goto LABEL_29;
      case 4u:
        goto $LN61;
      case 5u:
        goto LABEL_51;
      case 7u:
        v45 = this->_pInput._p;
        DWORD2(v48) = 0;
        v46 = v45->_lCurrent + ~v45->_lMark;
        *(_QWORD *)&v48 = XMLStream::skipWhiteSpace;
        LODWORD(v45) = HIDWORD(v48);
        this->_lLengthDelta = v46;
        HIDWORD(v48) = (_DWORD)v45;
        result = XMLStream::push(this, &v48, 8u);
        if ( result < 0 )
          return result;
        result = XMLStream::skipWhiteSpace(this);
        if ( result < 0 )
          return result;
        this->_sSubState = 8;
$LN80:
        if ( this->_fEOF )
          return -1072896674;
        v47 = this->_pInput._p->_lMark - this->_pInput._p->_lCurrent + 1;
        this->_sSubState = 2;
        this->_lLengthDelta += v47;
        result = 0;
        break;
      case 8u:
        goto $LN80;
      default:
        return -1072896750;
    }
    return result;
  }
  if ( this->_fEOF )
    return -1072896674;
  v3 = this->_chLookahead;
  if ( v3 != this->_chEndChar && v3 != 62 )
  {
    if ( this->_pInput._p->_lLastWhiteSpace != this->_pInput._p->_lCurrent )
      return -1072896759;
    this->_sSubState = 0;
    return 0;
  }
  v34 = this->_pStack._ncUsed;
  if ( !v34 )
    return -1072896750;
  v35 = &this->_pStack._pStack[this->_pStack._lEntrySize * (v34 - 1)];
  if ( !v35 )
    return -1072896750;
  result = this->_hrErr;
  if ( !result )
  {
    if ( !this->_fDTD || this->_fParsingAttDef || this->_fParseLiteral || this->_cStreamDepth == *((_DWORD *)v35 + 9) )
    {
      this->_fnState = *(_OWORD *)v35;
      this->_sSubState = *((_DWORD *)v35 + 4);
      this->_pTable = (const StateEntry *)*((_QWORD *)v35 + 3);
      this->_lEOFError = *((_DWORD *)v35 + 8);
      p_pStack = &this->_pStack;
LABEL_96:
      RawStack::_pop(p_pStack);
      return 0;
    }
    return -1072896677;
  }
  if ( result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180003f50  mov     [rsp+arg_0], rbx
0x180003f55  mov     [rsp+arg_8], rsi
0x180003f5a  push    rdi
0x180003f5b  sub     rsp, 30h
0x180003f5f  mov     eax, [this+28h]
0x180003f62  mov     rbx, this
0x180003f65  test    eax, eax
0x180003f67  jz      short loc_180003FCD
0x180003f69  cmp     eax, 3
0x180003f6c  jz      loc_180004183
0x180003f72  cmp     eax, 6
0x180003f75  jnz     loc_180004376
0x180003f7b  cmp     byte ptr [this+0A4h], 0
0x180003f82  jnz     loc_180004674
0x180003f88  movzx   eax, word ptr [this+9Ah]
0x180003f8f  cmp     ax, [this+0A2h]
0x180003f96  jz      loc_180004436
0x180003f9c  cmp     ax, 3Eh ; '>'
0x180003fa0  jz      loc_180004436
0x180003fa6  mov     this, [this+78h]
0x180003faa  mov     eax, [this+28h]
0x180003fad  cmp     [this+64h], eax
0x180003fb0  jnz     loc_180004546
0x180003fb6  xor     esi, esi
0x180003fb8  mov     [rbx+28h], esi
0x180003fbb  xor     eax, eax
0x180003fbd  mov     rbx, [rsp+38h+arg_0]
0x180003fc2  mov     rsi, [rsp+38h+arg_8]
0x180003fc7  add     rsp, 30h
0x180003fcb  pop     rdi
0x180003fcc  retn
0x180003fcd  mov     eax, [this+128h]
0x180003fd3  xor     esi, esi
0x180003fd5  mov     [this+0C8h], esi
0x180003fdb  mov     [this+101h], sil
0x180003fe2  test    eax, eax
0x180003fe4  jnz     loc_180004411
0x180003fea  mov     r8d, [this+40h]
0x180003fee  cmp     [this+44h], r8d
0x180003ff2  jz      loc_180004654
0x180003ff8  mov     ecx, r8d
0x180003ffb  lea     eax, [r8+1]
0x180003fff  imul    ecx, [rbx+30h]
0x180004003  mov     [rbx+40h], eax
0x180004006  add     this, [rbx+38h]
0x18000400a  test    this, this
0x18000400d  jz      loc_180004959
0x180004013  mov     dword ptr [this+10h], 1
0x18000401a  movups  xmm0, xmmword ptr [rbx+18h]
0x18000401e  movups  xmmword ptr [this], xmm0
0x180004021  mov     rax, [rbx+0E0h]
0x180004028  mov     [this+18h], rax
0x18000402c  mov     eax, [rbx+0E8h]
0x180004032  mov     [this+20h], eax
0x180004035  mov     eax, [rbx+70h]
0x180004038  mov     [this+24h], eax
0x18000403b  lea     rax, ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x180004042  mov     [rbx+18h], rax
0x180004046  mov     eax, [rsp+38h+var_C]
0x18000404a  mov     [rbx+24h], eax
0x18000404d  mov     [rbx+28h], esi
0x180004050  mov     [rbx+20h], esi
0x180004053  mov     this, rbx; this
0x180004056  call    ?skipWhiteSpace@XMLStream@@AEAAJXZ; XMLStream::skipWhiteSpace(void)
0x18000405b  test    eax, eax
0x18000405d  js      loc_180004173
0x180004063  mov     dword ptr [rbx+28h], 1
0x18000406a  movzx   eax, word ptr [rbx+9Ah]
0x180004071  cmp     ax, [rbx+0A2h]
0x180004078  jz      loc_1800044E9
0x18000407e  cmp     ax, 3Eh ; '>'
0x180004082  jz      loc_1800044E9
0x180004088  cmp     ax, 78h ; 'x'
0x18000408c  jz      loc_1800044DD
0x180004092  mov     eax, [rbx+128h]
0x180004098  test    eax, eax
0x18000409a  jnz     loc_18000439B
0x1800040a0  mov     r8d, [rbx+40h]
0x1800040a4  cmp     [rbx+44h], r8d
0x1800040a8  jz      loc_180004643
0x1800040ae  mov     ecx, r8d
0x1800040b1  lea     eax, [r8+1]
0x1800040b5  imul    ecx, [rbx+30h]
0x1800040b9  mov     [rbx+40h], eax
0x1800040bc  add     this, [rbx+38h]
0x1800040c0  test    this, this
0x1800040c3  jz      loc_180004959
0x1800040c9  mov     dword ptr [this+10h], 2
0x1800040d0  movups  xmm0, xmmword ptr [rbx+18h]
0x1800040d4  movups  xmmword ptr [this], xmm0
0x1800040d7  mov     rax, [rbx+0E0h]
0x1800040de  mov     [this+18h], rax
0x1800040e2  mov     eax, [rbx+0E8h]
0x1800040e8  mov     [this+20h], eax
0x1800040eb  mov     eax, [rbx+70h]
0x1800040ee  mov     [this+24h], eax
0x1800040f1  lea     rax, ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x1800040f8  mov     [rbx+18h], rax
0x1800040fc  mov     eax, [rsp+38h+var_C]
0x180004100  mov     [rbx+24h], eax
0x180004103  mov     [rbx+28h], esi
0x180004106  mov     [rbx+20h], esi
0x180004109  mov     this, rbx; this
0x18000410c  call    ?parseName@XMLStream@@AEAAJXZ; XMLStream::parseName(void)
0x180004111  test    eax, eax
0x180004113  js      short loc_180004173
0x180004115  mov     this, [rbx+78h]
0x180004119  mov     eax, [this+28h]
0x18000411c  cmp     [this+64h], eax
0x18000411f  jz      short loc_18000412F
0x180004121  cmp     word ptr [rbx+9Ah], 3Dh ; '='
0x180004129  jnz     loc_180004696
0x18000412f  mov     dword ptr [rbx+28h], 2
0x180004136  mov     rax, [rbx+78h]
0x18000413a  mov     ecx, [rax+28h]
0x18000413d  cmp     [rax+64h], ecx
0x180004140  jz      loc_1800046C0
0x180004146  cmp     byte ptr [rbx+0A4h], 0
0x18000414d  jnz     loc_180004674
0x180004153  cmp     byte ptr [rbx+101h], 0
0x18000415a  jnz     loc_180004565
0x180004160  mov     dword ptr [rbx+8Ch], 2
0x18000416a  mov     dword ptr [rbx+28h], 3
0x180004171  xor     eax, eax
0x180004173  mov     rbx, [rsp+38h+arg_0]
0x180004178  mov     rsi, [rsp+38h+arg_8]
0x18000417d  add     rsp, 30h
0x180004181  pop     rdi
0x180004182  retn
0x180004183  mov     this, [this+78h]
0x180004187  mov     eax, [this+28h]
0x18000418a  cmp     [this+64h], eax
0x18000418d  jz      loc_1800046AB
0x180004193  mov     byte ptr [rbx+9Ch], 0
0x18000419a  mov     dword ptr [rbx+28h], 4
0x1800041a1  lea     r8, [rbx+9Ah]; jumptable 0000000180004392 case 4
0x1800041a8  cmp     word ptr [r8], 3Dh ; '='
0x1800041ad  jnz     loc_180004907
0x1800041b3  xor     esi, esi
0x1800041b5  cmp     [rbx+102h], sil
0x1800041bc  jnz     loc_180004636
0x1800041c2  mov     rdi, [rbx+78h]
0x1800041c6  mov     r9d, [rdi+34h]
0x1800041ca  cmp     [rdi+28h], r9d
0x1800041ce  jge     loc_1800044AD
0x1800041d4  movsxd  rdx, dword ptr [rdi+28h]
0x1800041d8  mov     rax, [rdi+20h]
0x1800041dc  movzx   r9d, word ptr [rax+rdx*2]
0x1800041e1  inc     edx
0x1800041e3  mov     [rdi+28h], edx
0x1800041e6  mov     ecx, r9d
0x1800041e9  cmp     r9d, 20h ; ' '
0x1800041ed  ja      loc_1800043F7
0x1800041f3  jz      loc_1800043C2
0x1800041f9  sub     ecx, 9
0x1800041fc  jz      loc_1800043C2
0x180004202  sub     ecx, 1
0x180004205  jz      loc_1800043A6
0x18000420b  cmp     ecx, 3
0x18000420e  jz      loc_1800043A6
0x180004214  cmp     r9d, 20h ; ' '
0x180004218  jnb     loc_1800043C5
0x18000421e  mov     eax, 0C00CE508h
0x180004223  test    eax, eax
0x180004225  jnz     loc_180004173
0x18000422b  mov     this, [rbx+78h]
0x18000422f  mov     eax, [this+28h]
0x180004232  cmp     [this+64h], eax
0x180004235  jz      loc_180004911
0x18000423b  mov     dword ptr [rbx+28h], 5
0x180004242  mov     rdi, [rbx+78h]
0x180004246  mov     eax, [rdi+28h]
0x180004249  cmp     [rdi+64h], eax
0x18000424c  jz      loc_1800046AB
0x180004252  movzx   eax, word ptr [rbx+9Ah]
0x180004259  cmp     ax, 22h ; '"'
0x18000425d  jnz     loc_180004617
0x180004263  cmp     byte ptr [rbx+102h], 0
0x18000426a  mov     [rbx+9Eh], ax
0x180004271  jnz     loc_180004689
0x180004277  mov     r9d, [rdi+34h]
0x18000427b  cmp     [rdi+28h], r9d
0x18000427f  jge     loc_1800044C5
0x180004285  movsxd  rdx, dword ptr [rdi+28h]
0x180004289  mov     rax, [rdi+20h]
0x18000428d  movzx   r8d, word ptr [rax+rdx*2]
0x180004292  inc     edx
0x180004294  mov     [rdi+28h], edx
0x180004297  mov     ecx, r8d
0x18000429a  cmp     r8d, 20h ; ' '
0x18000429e  ja      loc_18000441C
0x1800042a4  jz      loc_1800043E5
0x1800042aa  sub     ecx, 9
0x1800042ad  jz      loc_1800043E5
0x1800042b3  sub     ecx, 1
0x1800042b6  jz      loc_1800043D0
0x1800042bc  cmp     ecx, 3
0x1800042bf  jz      loc_1800043D0
0x1800042c5  cmp     r8d, 20h ; ' '
0x1800042c9  jnb     loc_1800043E8
0x1800042cf  mov     eax, 0C00CE508h
0x1800042d4  test    eax, eax
0x1800042d6  jnz     loc_180004173
0x1800042dc  mov     this, [rbx+78h]
0x1800042e0  mov     eax, [this+28h]
0x1800042e3  test    eax, eax
0x1800042e5  jle     loc_1800046D9
0x1800042eb  lea     edx, [rax-1]
0x1800042ee  mov     [this+30h], edx
0x1800042f1  mov     edx, [this+40h]
0x1800042f4  cmp     edx, eax
0x1800042f6  jz      short loc_180004301
0x1800042f8  mov     eax, [this+3Ch]
0x1800042fb  mov     [this+44h], eax
0x1800042fe  mov     [this+48h], edx
0x180004301  mov     eax, [rbx+128h]
0x180004307  test    eax, eax
0x180004309  jnz     loc_180004173
0x18000430f  lea     this, [rbx+30h]; this
0x180004313  call    ?_push@RawStack@@IEAAPEADXZ; RawStack::_push(void)
0x180004318  mov     this, rax
0x18000431b  test    rax, rax
0x18000431e  jz      loc_180004959
0x180004324  mov     dword ptr [rax+10h], 6
0x18000432b  movups  xmm0, xmmword ptr [rbx+18h]
0x18000432f  movups  xmmword ptr [rax], xmm0
0x180004332  mov     rax, [rbx+0E0h]
0x180004339  mov     [this+18h], rax
0x18000433d  mov     eax, [rbx+0E8h]
0x180004343  mov     [this+20h], eax
0x180004346  mov     eax, [rbx+70h]
0x180004349  mov     [this+24h], eax
0x18000434c  lea     rax, ?parseAttrValue@XMLStream@@AEAAJXZ; XMLStream::parseAttrValue(void)
0x180004353  mov     [rbx+18h], rax
0x180004357  mov     eax, [rsp+38h+var_C]
0x18000435b  mov     [rbx+24h], eax
0x18000435e  mov     eax, esi
0x180004360  mov     [rbx+28h], esi
0x180004363  mov     [rbx+20h], esi
0x180004366  mov     rbx, [rsp+38h+arg_0]
0x18000436b  mov     rsi, [rsp+38h+arg_8]
0x180004370  add     rsp, 30h
0x180004374  pop     rdi
0x180004375  retn
0x180004376  dec     eax; switch 8 cases
0x180004378  cmp     eax, 7
0x18000437b  ja      def_180004392; jumptable 0000000180004392 default case, cases 3,6
0x180004381  lea     this, __ImageBase
0x180004388  mov     eax, ds:(jpt_180004392 - 180000000h)[this+rax*4]
0x18000438f  add     rax, this
0x180004392  jmp     rax; switch jump
0x180004394  xor     esi, esi; jumptable 0000000180004392 case 1
0x180004396  jmp     loc_18000406A
0x18000439b  js      loc_180004173
0x1800043a1  jmp     loc_180004109
0x1800043a6  cmp     r9d, 0Dh
0x1800043aa  jnz     loc_1800047E5
0x1800043b0  inc     dword ptr [rdi+3Ch]
0x1800043b3  lea     r8, [rbx+9Ah]
0x1800043ba  mov     [rdi+40h], edx
0x1800043bd  mov     [rdi+38h], r9w
0x1800043c2  mov     [rdi+64h], edx
0x1800043c5  mov     [r8], r9w
0x1800043c9  mov     eax, esi
0x1800043cb  jmp     loc_180004223
0x1800043d0  cmp     r8d, 0Dh
0x1800043d4  jnz     loc_1800047F5
0x1800043da  inc     dword ptr [rdi+3Ch]
0x1800043dd  mov     [rdi+40h], edx
0x1800043e0  mov     [rdi+38h], r8w
0x1800043e5  mov     [rdi+64h], edx
0x1800043e8  mov     [rbx+9Ah], r8w
0x1800043f0  mov     eax, esi
0x1800043f2  jmp     loc_1800042D4
0x1800043f7  sub     ecx, 0FFFEh
0x1800043fd  jz      loc_18000421E
0x180004403  cmp     ecx, 1
0x180004406  jnz     loc_180004214
0x18000440c  jmp     loc_18000421E
0x180004411  jns     loc_180004053
0x180004417  jmp     loc_180004173
0x18000441c  sub     ecx, 0FFFEh
0x180004422  jz      loc_1800042CF
0x180004428  cmp     ecx, 1
0x18000442b  jnz     loc_1800042C5
0x180004431  jmp     loc_1800042CF
0x180004436  mov     eax, [this+40h]
0x180004439  test    eax, eax
0x18000443b  jz      def_180004392; jumptable 0000000180004392 default case, cases 3,6
0x180004441  lea     r8d, [rax-1]
0x180004445  imul    r8d, [this+30h]
0x18000444a  add     r8, [this+38h]
0x18000444e  jz      def_180004392; jumptable 0000000180004392 default case, cases 3,6
0x180004454  mov     eax, [this+128h]
0x18000445a  test    eax, eax
0x18000445c  jnz     loc_18000481F
0x180004462  cmp     [this+102h], al
0x180004468  jnz     loc_1800048DB
0x18000446e  movups  xmm0, xmmword ptr [r8]
0x180004472  movups  xmmword ptr [this+18h], xmm0
  ... truncated ...
```
